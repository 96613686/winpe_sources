# Microsoft.ReportingServices.Library.BufferedCompressedReadStream::ReadFromBuffer

- ea: `0x64a00`
- end: `0x64ab4`
- name: `Microsoft.ReportingServices.Library.BufferedCompressedReadStream::ReadFromBuffer`
- size: `180`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x64a00`
- `0x64b20`

## string_xrefs

- `0x64a03`: `Buffer can't be null on read`
- `0x64a21`: `Number of bytes to read must be a positive number`

## pseudocode

```c

```

## disassembly

```asm
0x64a00  ldarg.1
0x64a01  brtrue.s loc_64A0E
0x64a03  ldstr    aBufferCanTBeNu// "Buffer can't be null on read"
0x64a08  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x64a0d  throw
0x64a0e  ldarg.2
0x64a0f  ldc.i4.0
0x64a10  bge.s    loc_64A1D
0x64a12  ldstr    aOffsetMustBeNo// "Offset must be non-negative"
0x64a17  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x64a1c  throw
0x64a1d  ldarg.3
0x64a1e  ldc.i4.0
0x64a1f  bge.s    loc_64A2C
0x64a21  ldstr    aNumberOfBytesT// "Number of bytes to read must be a posit"...
0x64a26  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x64a2b  throw
0x64a2c  ldarg.3
0x64a2d  brtrue.s loc_64A31
0x64a2f  ldc.i4.0
0x64a30  ret
0x64a31  ldc.i4.0
0x64a32  stloc.0
0x64a33  ldarg.0
0x64a34  ldfld    int32 Microsoft.ReportingServices.Library.BufferedCompressedReadStream::m_positionInBuffer
0x64a39  ldarg.0
0x64a3a  ldfld    int32 Microsoft.ReportingServices.Library.BufferedCompressedReadStream::m_bytesInBuffer
0x64a3f  blt.s    loc_64A59
0x64a41  ldarg.0
0x64a42  ldfld    int32 Microsoft.ReportingServices.Library.BufferedCompressedReadStream::m_positionInBuffer
0x64a47  ldarg.0
0x64a48  ldfld    int32 Microsoft.ReportingServices.Library.BufferedCompressedReadStream::m_bytesInBuffer
0x64a4d  sub
0x64a4e  stloc.0
0x64a4f  ldarg.0
0x64a50  call     instance bool Microsoft.ReportingServices.Library.BufferedCompressedReadStream::FillBuffer()
0x64a55  brtrue.s loc_64A59
0x64a57  ldc.i4.m1
0x64a58  ret
0x64a59  ldarg.0
0x64a5a  ldfld    int32 Microsoft.ReportingServices.Library.BufferedCompressedReadStream::m_bytesInBuffer
0x64a5f  ldarg.0
0x64a60  ldfld    int32 Microsoft.ReportingServices.Library.BufferedCompressedReadStream::m_positionInBuffer
0x64a65  sub
0x64a66  stloc.1
0x64a67  ldloc.1
0x64a68  ldarg.3
0x64a69  blt.s    loc_64A6E
0x64a6b  ldarg.3
0x64a6c  br.s     loc_64A6F
0x64a6e  ldloc.1
0x64a6f  stloc.2
0x64a70  ldarg.0
0x64a71  ldfld    unsigned int8[] Microsoft.ReportingServices.Library.BufferedCompressedReadStream::m_buffer
0x64a76  ldarg.0
0x64a77  ldfld    int32 Microsoft.ReportingServices.Library.BufferedCompressedReadStream::m_positionInBuffer
0x64a7c  ldarg.1
0x64a7d  ldarg.2
0x64a7e  ldloc.2
0x64a7f  call     void [mscorlib]System.Array::Copy(class [mscorlib]System.Array, int32, class [mscorlib]System.Array, int32, int32)
0x64a84  ldarg.0
0x64a85  ldarg.0
0x64a86  ldfld    int32 Microsoft.ReportingServices.Library.BufferedCompressedReadStream::m_positionInBuffer
0x64a8b  ldloc.2
0x64a8c  add
0x64a8d  stfld    int32 Microsoft.ReportingServices.Library.BufferedCompressedReadStream::m_positionInBuffer
0x64a92  ldarg.0
0x64a93  ldarg.0
0x64a94  ldfld    int64 Microsoft.ReportingServices.Library.BufferedCompressedReadStream::m_bytesReadTotal
0x64a99  ldloc.2
0x64a9a  conv.i8
0x64a9b  add
0x64a9c  stfld    int64 Microsoft.ReportingServices.Library.BufferedCompressedReadStream::m_bytesReadTotal
0x64aa1  ldarg.0
0x64aa2  ldarg.0
0x64aa3  ldfld    int64 Microsoft.ReportingServices.Library.BufferedCompressedReadStream::m_bytesReadFromBuffer
0x64aa8  ldloc.2
0x64aa9  ldloc.0
0x64aaa  sub
0x64aab  conv.i8
0x64aac  add
0x64aad  stfld    int64 Microsoft.ReportingServices.Library.BufferedCompressedReadStream::m_bytesReadFromBuffer
0x64ab2  ldloc.2
0x64ab3  ret
```
