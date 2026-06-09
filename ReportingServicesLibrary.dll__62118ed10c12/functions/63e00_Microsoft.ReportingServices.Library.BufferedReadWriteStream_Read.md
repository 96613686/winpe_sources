# Microsoft.ReportingServices.Library.BufferedReadWriteStream::Read

- ea: `0x63e00`
- end: `0x63f34`
- name: `Microsoft.ReportingServices.Library.BufferedReadWriteStream::Read`
- size: `308`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x63e00`
- `0x644a0`
- `0x64500`
- `0x64570`
- `0x64600`
- `0x64620`

## string_xrefs

- `0x63e03`: `Buffer can't be null on read`
- `0x63e21`: `Number of bytes to read must be a positive number`

## pseudocode

```c

```

## disassembly

```asm
0x63e00  ldarg.1
0x63e01  brtrue.s loc_63E0E
0x63e03  ldstr    aBufferCanTBeNu// "Buffer can't be null on read"
0x63e08  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x63e0d  throw
0x63e0e  ldarg.2
0x63e0f  ldc.i4.0
0x63e10  bge.s    loc_63E1D
0x63e12  ldstr    aOffsetMustBeNo// "Offset must be non-negative"
0x63e17  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x63e1c  throw
0x63e1d  ldarg.3
0x63e1e  ldc.i4.0
0x63e1f  bge.s    loc_63E2C
0x63e21  ldstr    aNumberOfBytesT// "Number of bytes to read must be a posit"...
0x63e26  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x63e2b  throw
0x63e2c  ldarg.3
0x63e2d  brtrue.s loc_63E31
0x63e2f  ldc.i4.0
0x63e30  ret
0x63e31  ldc.i4.0
0x63e32  stloc.0
0x63e33  ldarg.0
0x63e34  ldfld    int32 Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_positionInBuffer
0x63e39  ldarg.0
0x63e3a  ldfld    int32 Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_bytesInBuffer
0x63e3f  blt      loc_63EDC
0x63e44  ldarg.0
0x63e45  callvirt instance int64 [mscorlib]System.IO.Stream::get_Position()
0x63e4a  ldarg.0
0x63e4b  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x63e50  blt.s    loc_63E54
0x63e52  ldc.i4.0
0x63e53  ret
0x63e54  ldarg.0
0x63e55  ldc.i4.2
0x63e56  call     instance bool Microsoft.ReportingServices.Library.BufferedReadWriteStream::IsFlagsSet(valuetype StreamFlags flags)
0x63e5b  brfalse.s loc_63E82
0x63e5d  ldarg.0
0x63e5e  ldfld    class [mscorlib]System.IO.Stream Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_store
0x63e63  ldarg.0
0x63e64  ldfld    int64 Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_bufferStartPosition
0x63e69  ldarg.0
0x63e6a  ldfld    unsigned int8[] Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_buffer
0x63e6f  ldc.i4.0
0x63e70  ldarg.0
0x63e71  ldfld    int32 Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_bytesInBuffer
0x63e76  call     void Microsoft.ReportingServices.Library.BufferedReadWriteStream::WriteExternalBuffer(class [mscorlib]System.IO.Stream store, int64 absolutePosition, unsigned int8[] buffer, int32 offset, int32 count)
0x63e7b  ldarg.0
0x63e7c  ldc.i4.2
0x63e7d  call     instance void Microsoft.ReportingServices.Library.BufferedReadWriteStream::UnsetFlags(valuetype StreamFlags flags)
0x63e82  ldarg.3
0x63e83  ldarg.0
0x63e84  ldfld    unsigned int8[] Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_buffer
0x63e89  ldlen
0x63e8a  conv.i4
0x63e8b  blt.s    loc_63ED0
0x63e8d  ldarg.0
0x63e8e  ldfld    class [mscorlib]System.IO.Stream Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_store
0x63e93  ldarg.0
0x63e94  callvirt instance int64 [mscorlib]System.IO.Stream::get_Position()
0x63e99  ldarg.1
0x63e9a  ldarg.2
0x63e9b  ldarg.3
0x63e9c  call     int32 Microsoft.ReportingServices.Library.BufferedReadWriteStream::ReadExternalBuffer(class [mscorlib]System.IO.Stream store, int64 absolutePosition, unsigned int8[] buffer, int32 offset, int32 count)
0x63ea1  stloc.2
0x63ea2  ldarg.0
0x63ea3  ldarg.0
0x63ea4  callvirt instance int64 [mscorlib]System.IO.Stream::get_Position()
0x63ea9  ldloc.2
0x63eaa  conv.i8
0x63eab  add
0x63eac  stfld    int64 Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_bufferStartPosition
0x63eb1  ldarg.0
0x63eb2  ldc.i4.0
0x63eb3  stfld    int32 Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_bytesInBuffer
0x63eb8  ldarg.0
0x63eb9  ldc.i4.0
0x63eba  stfld    int32 Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_positionInBuffer
0x63ebf  ldarg.0
0x63ec0  ldarg.0
0x63ec1  ldfld    int64 Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_bytesReadTotal
0x63ec6  ldloc.2
0x63ec7  conv.i8
0x63ec8  add
0x63ec9  stfld    int64 Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_bytesReadTotal
0x63ece  ldloc.2
0x63ecf  ret
0x63ed0  ldarg.0
0x63ed1  ldloca.s 0
0x63ed3  call     instance bool Microsoft.ReportingServices.Library.BufferedReadWriteStream::FillBuffer([out] int32& bytesRead)
0x63ed8  brtrue.s loc_63EDC
0x63eda  ldc.i4.0
0x63edb  ret
0x63edc  ldarg.3
0x63edd  ldarg.0
0x63ede  ldfld    int32 Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_bytesInBuffer
0x63ee3  ldarg.0
0x63ee4  ldfld    int32 Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_positionInBuffer
0x63ee9  sub
0x63eea  call     int32 [mscorlib]System.Math::Min(int32, int32)
0x63eef  stloc.1
0x63ef0  ldarg.0
0x63ef1  ldfld    unsigned int8[] Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_buffer
0x63ef6  ldarg.0
0x63ef7  ldfld    int32 Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_positionInBuffer
0x63efc  ldarg.1
0x63efd  ldarg.2
0x63efe  ldloc.1
0x63eff  call     void [mscorlib]System.Array::Copy(class [mscorlib]System.Array, int32, class [mscorlib]System.Array, int32, int32)
0x63f04  ldarg.0
0x63f05  ldarg.0
0x63f06  ldfld    int32 Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_positionInBuffer
0x63f0b  ldloc.1
0x63f0c  add
0x63f0d  stfld    int32 Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_positionInBuffer
0x63f12  ldarg.0
0x63f13  ldarg.0
0x63f14  ldfld    int64 Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_bytesReadTotal
0x63f19  ldloc.1
0x63f1a  ldloc.0
0x63f1b  add
0x63f1c  conv.i8
0x63f1d  add
0x63f1e  stfld    int64 Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_bytesReadTotal
0x63f23  ldarg.0
0x63f24  ldarg.0
0x63f25  ldfld    int64 Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_bytesReadFromBuffer
0x63f2a  ldloc.1
0x63f2b  conv.i8
0x63f2c  add
0x63f2d  stfld    int64 Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_bytesReadFromBuffer
0x63f32  ldloc.1
0x63f33  ret
```
