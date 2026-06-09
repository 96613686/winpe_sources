# SnapInHostingOptions::get_ModalLoopEndNowPromptInterval

- ea: `0x25c0`
- end: `0x25e4`
- name: `SnapInHostingOptions::get_ModalLoopEndNowPromptInterval`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x2710`

## string_xrefs

- `0x25c0`: `modalLoopEndNowPromptInterval`

## pseudocode

```c

```

## disassembly

```asm
0x25c0  ldstr    aModalloopendno// "modalLoopEndNowPromptInterval"
0x25c5  ldc.i4.0
0x25c6  ldc.i4.0
0x25c7  ldc.i4.s 0x14
0x25c9  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x25ce  ldc.i4.0
0x25cf  ldc.i4.0
0x25d0  ldc.i4.5
0x25d1  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x25d6  ldc.i4.0
0x25d7  ldc.i4.5
0x25d8  ldc.i4.0
0x25d9  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x25de  call     valuetype [mscorlib]System.TimeSpan SnapInHostingOptions::ReadTimeSpanSetting(string settingKey, valuetype [mscorlib]System.TimeSpan defaultValue, valuetype [mscorlib]System.TimeSpan minValue, valuetype [mscorlib]System.TimeSpan maxValue)
0x25e3  ret
```
