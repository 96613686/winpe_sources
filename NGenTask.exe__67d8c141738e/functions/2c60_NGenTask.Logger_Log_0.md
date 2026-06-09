# NGenTask.Logger::Log_0

- ea: `0x2c60`
- end: `0x2cc1`
- name: `NGenTask.Logger::Log_0`
- size: `97`
- prototype: ``
- caller_count: `36`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x10`
- `0x110`
- `0x160`
- `0x220`
- `0x310`
- `0xf20`
- `0x10b0`
- `0x1120`
- `0x11c0`
- `0x1400`
- `0x19f0`
- `0x1db0`
- `0x1e00`
- `0x1f20`
- `0x1f90`
- `0x20e0`
- `0x21e0`
- `0x2290`
- `0x22e0`
- `0x2330`
- `0x23a0`
- `0x23e0`
- `0x2420`
- `0x24a0`
- `0x2610`
- `0x2790`
- `0x29f0`
- `0x2df0`
- `0x3790`
- `0x3830`
- `0x4270`
- `0x45f0`
- `0x4980`
- `0x4dc0`
- `0x4fe0`
- `0x5310`

## callees

- `0x2c30`
- `0x2c60`

## pseudocode

```c

```

## disassembly

```asm
0x2c60  ldarg.2
0x2c61  ldarg.3
0x2c62  call     string [mscorlib]System.String::Format(string, object[])
0x2c67  stloc.0
0x2c68  ldsfld   valuetype LogLevel NGenTask.Logger::maxLogLevel
0x2c6d  ldc.i4.3
0x2c6e  bge.s    loc_2C94
0x2c70  ldarg.0
0x2c71  ldstr    a0Hresult1// "{0} HRESULT({1})"
0x2c76  ldc.i4.2
0x2c77  newarr   [mscorlib]System.Object
0x2c7c  dup
0x2c7d  ldc.i4.0
0x2c7e  ldloc.0
0x2c7f  stelem.ref
0x2c80  dup
0x2c81  ldc.i4.1
0x2c82  ldarg.1
0x2c83  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetHRForException(class [mscorlib]System.Exception)
0x2c88  box      [mscorlib]System.Int32
0x2c8d  stelem.ref
0x2c8e  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x2c93  ret
0x2c94  ldarg.0
0x2c95  ldstr    a0Hresult1Excep// "{0} HRESULT({1}) Exception Message \"{2"...
0x2c9a  ldc.i4.3
0x2c9b  newarr   [mscorlib]System.Object
0x2ca0  dup
0x2ca1  ldc.i4.0
0x2ca2  ldloc.0
0x2ca3  stelem.ref
0x2ca4  dup
0x2ca5  ldc.i4.1
0x2ca6  ldarg.1
0x2ca7  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetHRForException(class [mscorlib]System.Exception)
0x2cac  box      [mscorlib]System.Int32
0x2cb1  stelem.ref
0x2cb2  dup
0x2cb3  ldc.i4.2
0x2cb4  ldarg.1
0x2cb5  callvirt instance string [mscorlib]System.Exception::get_Message()
0x2cba  stelem.ref
0x2cbb  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x2cc0  ret
```
