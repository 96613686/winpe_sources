# Microsoft.ReportingServices.Library.BufferedReadWriteStream::Write

- ea: `0x640a0`
- end: `0x64232`
- name: `Microsoft.ReportingServices.Library.BufferedReadWriteStream::Write`
- size: `402`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x640a0`
- `0x64520`
- `0x64570`
- `0x64600`
- `0x64610`
- `0x64620`
- `0x646a0`

## string_xrefs

- `0x640a3`: `Buffer can't be null on write.`
- `0x640c1`: `Number of bytes to write must be non-negative (0 or more)`

## pseudocode

```c

```

## disassembly

```asm
0x640a0  ldarg.1
0x640a1  brtrue.s loc_640AE
0x640a3  ldstr    aBufferCanTBeNu_0// "Buffer can't be null on write."
0x640a8  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x640ad  throw
0x640ae  ldarg.2
0x640af  ldc.i4.0
0x640b0  bge.s    loc_640BD
0x640b2  ldstr    aOffsetMustBeNo_0// "Offset must be non-negative."
0x640b7  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x640bc  throw
0x640bd  ldarg.3
0x640be  ldc.i4.0
0x640bf  bge.s    loc_640CC
0x640c1  ldstr    aNumberOfBytesT_0// "Number of bytes to write must be non-ne"...
0x640c6  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x640cb  throw
0x640cc  ldarg.3
0x640cd  brtrue.s loc_640D0
0x640cf  ret
0x640d0  ldarg.0
0x640d1  ldc.i4.4
0x640d2  call     instance bool Microsoft.ReportingServices.Library.BufferedReadWriteStream::IsFlagsSet(valuetype StreamFlags flags)
0x640d7  brfalse.s loc_640E7
0x640d9  ldarg.0
0x640da  ldc.i4.s 0xC
0x640dc  call     instance void Microsoft.ReportingServices.Library.BufferedReadWriteStream::UnsetFlags(valuetype StreamFlags flags)
0x640e1  ldarg.0
0x640e2  call     instance void Microsoft.ReportingServices.Library.BufferedReadWriteStream::OnStreamFirstWrite()
0x640e7  ldarg.0
0x640e8  ldfld    unsigned int8[] Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_buffer
0x640ed  ldlen
0x640ee  conv.i4
0x640ef  ldarg.0
0x640f0  ldfld    int32 Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_positionInBuffer
0x640f5  sub
0x640f6  stloc.0
0x640f7  ldarg.3
0x640f8  ldloc.0
0x640f9  sub
0x640fa  stloc.1
0x640fb  ldloc.1
0x640fc  ldc.i4.0
0x640fd  bgt.s    loc_64140
0x640ff  ldarg.1
0x64100  ldarg.2
0x64101  ldarg.0
0x64102  ldfld    unsigned int8[] Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_buffer
0x64107  ldarg.0
0x64108  ldfld    int32 Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_positionInBuffer
0x6410d  ldarg.3
0x6410e  call     void [mscorlib]System.Array::Copy(class [mscorlib]System.Array, int32, class [mscorlib]System.Array, int32, int32)
0x64113  ldarg.0
0x64114  ldarg.0
0x64115  ldfld    int32 Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_positionInBuffer
0x6411a  ldarg.3
0x6411b  add
0x6411c  stfld    int32 Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_positionInBuffer
0x64121  ldarg.0
0x64122  ldarg.0
0x64123  ldfld    int32 Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_positionInBuffer
0x64128  ldarg.0
0x64129  ldfld    int32 Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_bytesInBuffer
0x6412e  call     int32 [mscorlib]System.Math::Max(int32, int32)
0x64133  stfld    int32 Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_bytesInBuffer
0x64138  ldarg.0
0x64139  ldc.i4.2
0x6413a  call     instance void Microsoft.ReportingServices.Library.BufferedReadWriteStream::SetFlags(valuetype StreamFlags flags)
0x6413f  ret
0x64140  ldarg.0
0x64141  ldfld    int32 Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_bytesInBuffer
0x64146  brtrue.s loc_6417A
0x64148  ldarg.0
0x64149  ldfld    class [mscorlib]System.IO.Stream Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_store
0x6414e  ldarg.0
0x6414f  callvirt instance int64 [mscorlib]System.IO.Stream::get_Position()
0x64154  ldarg.1
0x64155  ldarg.2
0x64156  ldarg.3
0x64157  call     void Microsoft.ReportingServices.Library.BufferedReadWriteStream::WriteExternalBuffer(class [mscorlib]System.IO.Stream store, int64 absolutePosition, unsigned int8[] buffer, int32 offset, int32 count)
0x6415c  ldarg.0
0x6415d  ldc.i4.0
0x6415e  stfld    int32 Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_positionInBuffer
0x64163  ldarg.0
0x64164  ldc.i4.0
0x64165  stfld    int32 Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_bytesInBuffer
0x6416a  ldarg.0
0x6416b  ldarg.0
0x6416c  ldfld    int64 Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_bufferStartPosition
0x64171  ldarg.3
0x64172  conv.i8
0x64173  add
0x64174  stfld    int64 Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_bufferStartPosition
0x64179  ret
0x6417a  ldloc.1
0x6417b  ldarg.0
0x6417c  ldfld    unsigned int8[] Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_buffer
0x64181  ldlen
0x64182  conv.i4
0x64183  bge.s    loc_641E4
0x64185  ldarg.1
0x64186  ldarg.2
0x64187  ldarg.0
0x64188  ldfld    unsigned int8[] Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_buffer
0x6418d  ldarg.0
0x6418e  ldfld    int32 Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_positionInBuffer
0x64193  ldloc.0
0x64194  call     void [mscorlib]System.Array::Copy(class [mscorlib]System.Array, int32, class [mscorlib]System.Array, int32, int32)
0x64199  ldarg.0
0x6419a  ldarg.0
0x6419b  ldfld    int32 Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_bytesInBuffer
0x641a0  ldloc.0
0x641a1  add
0x641a2  stfld    int32 Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_bytesInBuffer
0x641a7  ldarg.0
0x641a8  call     instance void Microsoft.ReportingServices.Library.BufferedReadWriteStream::WriteBuffer()
0x641ad  ldarg.1
0x641ae  ldarg.2
0x641af  ldloc.0
0x641b0  add
0x641b1  ldarg.0
0x641b2  ldfld    unsigned int8[] Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_buffer
0x641b7  ldc.i4.0
0x641b8  ldloc.1
0x641b9  call     void [mscorlib]System.Array::Copy(class [mscorlib]System.Array, int32, class [mscorlib]System.Array, int32, int32)
0x641be  ldarg.0
0x641bf  ldloc.1
0x641c0  stfld    int32 Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_positionInBuffer
0x641c5  ldarg.0
0x641c6  ldarg.0
0x641c7  ldfld    int32 Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_positionInBuffer
0x641cc  ldarg.0
0x641cd  ldfld    int32 Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_bytesInBuffer
0x641d2  call     int32 [mscorlib]System.Math::Max(int32, int32)
0x641d7  stfld    int32 Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_bytesInBuffer
0x641dc  ldarg.0
0x641dd  ldc.i4.2
0x641de  call     instance void Microsoft.ReportingServices.Library.BufferedReadWriteStream::SetFlags(valuetype StreamFlags flags)
0x641e3  ret
0x641e4  ldarg.1
0x641e5  ldarg.2
0x641e6  ldarg.0
0x641e7  ldfld    unsigned int8[] Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_buffer
0x641ec  ldarg.0
0x641ed  ldfld    int32 Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_positionInBuffer
0x641f2  ldloc.0
0x641f3  call     void [mscorlib]System.Array::Copy(class [mscorlib]System.Array, int32, class [mscorlib]System.Array, int32, int32)
0x641f8  ldarg.0
0x641f9  ldarg.0
0x641fa  ldfld    unsigned int8[] Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_buffer
0x641ff  ldlen
0x64200  conv.i4
0x64201  stfld    int32 Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_bytesInBuffer
0x64206  ldarg.0
0x64207  call     instance void Microsoft.ReportingServices.Library.BufferedReadWriteStream::WriteBuffer()
0x6420c  ldarg.0
0x6420d  ldfld    class [mscorlib]System.IO.Stream Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_store
0x64212  ldarg.0
0x64213  callvirt instance int64 [mscorlib]System.IO.Stream::get_Position()
0x64218  ldarg.1
0x64219  ldarg.2
0x6421a  ldloc.0
0x6421b  add
0x6421c  ldloc.1
0x6421d  call     void Microsoft.ReportingServices.Library.BufferedReadWriteStream::WriteExternalBuffer(class [mscorlib]System.IO.Stream store, int64 absolutePosition, unsigned int8[] buffer, int32 offset, int32 count)
0x64222  ldarg.0
0x64223  ldarg.0
0x64224  ldfld    int64 Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_bufferStartPosition
0x64229  ldloc.1
0x6422a  conv.i8
0x6422b  add
0x6422c  stfld    int64 Microsoft.ReportingServices.Library.BufferedReadWriteStream::m_bufferStartPosition
0x64231  ret
```
