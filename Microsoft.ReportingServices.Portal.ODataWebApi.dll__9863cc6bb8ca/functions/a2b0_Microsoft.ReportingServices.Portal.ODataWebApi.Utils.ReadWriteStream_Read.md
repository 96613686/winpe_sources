# Microsoft.ReportingServices.Portal.ODataWebApi.Utils.ReadWriteStream::Read

- ea: `0xa2b0`
- end: `0xa333`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Utils.ReadWriteStream::Read`
- size: `131`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xa2b0`

## pseudocode

```c

```

## disassembly

```asm
0xa2b0  ldarg.2
0xa2b1  brfalse.s loc_A2C3
0xa2b3  ldstr    aOffsetMustBeZe// "Offset must be zero."
0xa2b8  ldstr    aCount// "count"
0xa2bd  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0xa2c2  throw
0xa2c3  ldarg.0
0xa2c4  ldfld    int32 Microsoft.ReportingServices.Portal.ODataWebApi.Utils.ReadWriteStream::_readOffset
0xa2c9  brtrue.s loc_A2D7
0xa2cb  ldarg.0
0xa2cc  ldfld    class [mscorlib]System.Threading.AutoResetEvent Microsoft.ReportingServices.Portal.ODataWebApi.Utils.ReadWriteStream::_writeDone
0xa2d1  callvirt instance bool [mscorlib]System.Threading.WaitHandle::WaitOne()
0xa2d6  pop
0xa2d7  ldarg.0
0xa2d8  ldfld    int32 Microsoft.ReportingServices.Portal.ODataWebApi.Utils.ReadWriteStream::_bytesInBuffer
0xa2dd  ldarg.0
0xa2de  ldfld    int32 Microsoft.ReportingServices.Portal.ODataWebApi.Utils.ReadWriteStream::_readOffset
0xa2e3  sub
0xa2e4  stloc.0
0xa2e5  ldarg.3
0xa2e6  ldloc.0
0xa2e7  blt.s    loc_A2EC
0xa2e9  ldloc.0
0xa2ea  br.s     loc_A2ED
0xa2ec  ldarg.3
0xa2ed  stloc.1
0xa2ee  ldarg.0
0xa2ef  ldfld    unsigned int8[] Microsoft.ReportingServices.Portal.ODataWebApi.Utils.ReadWriteStream::_buffer
0xa2f4  ldarg.0
0xa2f5  ldfld    int32 Microsoft.ReportingServices.Portal.ODataWebApi.Utils.ReadWriteStream::_readOffset
0xa2fa  ldarg.1
0xa2fb  ldc.i4.0
0xa2fc  ldloc.1
0xa2fd  call     void [mscorlib]System.Array::Copy(class [mscorlib]System.Array, int32, class [mscorlib]System.Array, int32, int32)
0xa302  ldarg.0
0xa303  ldarg.0
0xa304  ldfld    int32 Microsoft.ReportingServices.Portal.ODataWebApi.Utils.ReadWriteStream::_readOffset
0xa309  ldloc.1
0xa30a  add
0xa30b  stfld    int32 Microsoft.ReportingServices.Portal.ODataWebApi.Utils.ReadWriteStream::_readOffset
0xa310  ldarg.0
0xa311  ldfld    int32 Microsoft.ReportingServices.Portal.ODataWebApi.Utils.ReadWriteStream::_readOffset
0xa316  ldarg.0
0xa317  ldfld    int32 Microsoft.ReportingServices.Portal.ODataWebApi.Utils.ReadWriteStream::_bytesInBuffer
0xa31c  blt.s    loc_A331
0xa31e  ldarg.0
0xa31f  ldc.i4.0
0xa320  stfld    int32 Microsoft.ReportingServices.Portal.ODataWebApi.Utils.ReadWriteStream::_readOffset
0xa325  ldarg.0
0xa326  ldfld    class [mscorlib]System.Threading.AutoResetEvent Microsoft.ReportingServices.Portal.ODataWebApi.Utils.ReadWriteStream::_readDone
0xa32b  callvirt instance bool [mscorlib]System.Threading.EventWaitHandle::Set()
0xa330  pop
0xa331  ldloc.1
0xa332  ret
```
