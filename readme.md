# Dmusic

> Dmusic

## Build Setup

``` bash
# install dependencies
npm install

supervisor bin/www

npm run build --report
```

## API
- AudioContext
  - audio上下文对象，绝大数情况下，一个document中只有一个AudioContext
```  bash
    var ac =  new Window.AudioContext();
    # 方法
    decodeAudioData(arrayBuffer, succ(buffer), err),#异步解码包含在arrayBuffer中的与i尿频数据

    createBufferSource(), #创建audioBufferSourceNode对象
    createAnalyser() #创建AnalyserNode对象
    createGain()# 创建GainNode对象
```
- AudioBufferSourceNode
 - 表示内存中的一段音频资源，其音频数据存在于AudioBuffer中(其buffer属性)
 ```bash
    var buffersource = ac.createBufferSource()
```
  - 属性
    buffer
    loop
    onended
  - 方法
    start/noteOn(when = ac.currentTime, offset = 0,duration = buffer.duration-offset)
    stop/noteOff(when = ac.currentTime)
- GainNode
 - 改变音量
 ```
 var gainNode = ac.createGain()/ac.createGainNode();
 ```
- AnalyserNode 
  - 实时的分析音频资源的频域和时域信息，但不会对音频流做任何处理
  ```
   var analyser = ac.createAnalyser()
  ```
   - fftSize 设置FFT大小，用于分析得到频域，实时得到的音频频域的数据个数为fftSize的一半
   - frequencyBinCount, FFT值的一半，即实时得到的云品频域的数据个数
   - getByteFrequencyData(unit8Array),复制音频当前的频域数据到Unit8Array中


For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).
