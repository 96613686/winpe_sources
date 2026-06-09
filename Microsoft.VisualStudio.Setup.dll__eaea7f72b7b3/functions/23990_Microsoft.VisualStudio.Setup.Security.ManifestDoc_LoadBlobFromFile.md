# Microsoft.VisualStudio.Setup.Security.ManifestDoc::LoadBlobFromFile

- ea: `0x23990`
- end: `0x23c69`
- name: `Microsoft.VisualStudio.Setup.Security.ManifestDoc::LoadBlobFromFile`
- size: `729`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x23880`

## callees

- `0x238d0`
- `0x238e0`
- `0x23900`
- `0x23910`
- `0x23920`
- `0x23960`
- `0x23970`
- `0x23990`

## string_xrefs

- `0x23bfb`: `Bad_Manifest_Format`
- `0x23c56`: `Invalid Manifest File `

## pseudocode

```c

```

## disassembly

```asm
0x23990  ldarg.0
0x23991  call     instance class [mscorlib]System.IO.FileStream Microsoft.VisualStudio.Setup.Security.ManifestDoc::get_ManifestStream()
0x23996  ldc.i4.0
0x23997  conv.i8
0x23998  ldc.i4.0
0x23999  callvirt instance int64 [mscorlib]System.IO.Stream::Seek(int64, valuetype [mscorlib]System.IO.SeekOrigin)
0x2399e  pop
0x2399f  ldarg.0
0x239a0  call     instance class [mscorlib]System.IO.FileStream Microsoft.VisualStudio.Setup.Security.ManifestDoc::get_ManifestStream()
0x239a5  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x239aa  conv.ovf.i
0x239ab  newarr   [mscorlib]System.Byte
0x239b0  stloc.0
0x239b1  ldarg.0
0x239b2  call     instance class [mscorlib]System.IO.FileStream Microsoft.VisualStudio.Setup.Security.ManifestDoc::get_ManifestStream()
0x239b7  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x239bc  conv.i4
0x239bd  stloc.1
0x239be  ldc.i4.0
0x239bf  stloc.2
0x239c0  ldc.i4.0
0x239c1  stloc.3
0x239c2  br.s     loc_239C8
0x239c4  ldloc.2
0x239c5  ldloc.3
0x239c6  add
0x239c7  stloc.2
0x239c8  ldarg.0
0x239c9  call     instance class [mscorlib]System.IO.FileStream Microsoft.VisualStudio.Setup.Security.ManifestDoc::get_ManifestStream()
0x239ce  ldloc.0
0x239cf  ldloc.2
0x239d0  ldloc.1
0x239d1  ldloc.2
0x239d2  sub
0x239d3  callvirt instance int32 [mscorlib]System.IO.Stream::Read(unsigned int8[], int32, int32)
0x239d8  dup
0x239d9  stloc.3
0x239da  ldc.i4.0
0x239db  bgt.s    loc_239C4
0x239dd  ldc.i4.0
0x239de  newobj   instance void [mscorlib]System.Text.UTF8Encoding::.ctor(bool)
0x239e3  ldloc.0
0x239e4  callvirt instance string [mscorlib]System.Text.Encoding::GetString(unsigned int8[])
0x239e9  stloc.s  4
0x239eb  ldarg.0
0x239ec  call     instance class [mscorlib]System.IO.FileStream Microsoft.VisualStudio.Setup.Security.ManifestDoc::get_ManifestStream()
0x239f1  ldc.i4.1
0x239f2  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(class [mscorlib]System.IO.Stream, bool)
0x239f7  stloc.s  6
0x239f9  ldloc.s  6
0x239fb  callvirt instance int32 [mscorlib]System.IO.TextReader::Read()
0x23a00  pop
0x23a01  ldloc.s  6
0x23a03  callvirt instance class [mscorlib]System.Text.Encoding [mscorlib]System.IO.StreamReader::get_CurrentEncoding()
0x23a08  stloc.s  7
0x23a0a  ldloc.s  7
0x23a0c  callvirt instance unsigned int8[] [mscorlib]System.Text.Encoding::GetPreamble()
0x23a11  ldlen
0x23a12  brfalse.s loc_23A3B
0x23a14  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x23a19  ldloc.s  7
0x23a1b  callvirt instance unsigned int8[] [mscorlib]System.Text.Encoding::GetPreamble()
0x23a20  callvirt instance string [mscorlib]System.Text.Encoding::GetString(unsigned int8[])
0x23a25  stloc.s  8
0x23a27  ldloc.s  4
0x23a29  ldloc.s  8
0x23a2b  ldc.i4.5
0x23a2c  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x23a31  brfalse.s loc_23A3B
0x23a33  ldarg.0
0x23a34  ldloc.s  8
0x23a36  call     instance void Microsoft.VisualStudio.Setup.Security.ManifestDoc::set_Bom(string value)
0x23a3b  leave.s  loc_23A49
0x23a3d  ldloc.s  6
0x23a3f  brfalse.s loc_23A48
0x23a41  ldloc.s  6
0x23a43  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x23a48  endfinally
0x23a49  ldc.i4.0
0x23a4a  stloc.s  5
0x23a4c  ldloc.s  4
0x23a4e  ldarg.0
0x23a4f  ldfld    string Microsoft.VisualStudio.Setup.Security.ManifestDoc::ps1SignatureBeginTag
0x23a54  callvirt instance bool [mscorlib]System.String::Contains(string)
0x23a59  brfalse  loc_23B5E
0x23a5e  ldloc.s  4
0x23a60  ldarg.0
0x23a61  ldfld    string Microsoft.VisualStudio.Setup.Security.ManifestDoc::ps1SignatureBeginTag
0x23a66  ldc.i4.5
0x23a67  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x23a6c  stloc.s  5
0x23a6e  ldarg.0
0x23a6f  ldloc.s  4
0x23a71  ldc.i4.0
0x23a72  ldloc.s  4
0x23a74  ldc.i4.s 0x7D
0x23a76  callvirt instance int32 [mscorlib]System.String::LastIndexOf(char)
0x23a7b  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x23a80  call     instance void Microsoft.VisualStudio.Setup.Security.ManifestDoc::set_ContentBlob(string value)
0x23a85  ldarg.0
0x23a86  call     instance string Microsoft.VisualStudio.Setup.Security.ManifestDoc::get_ContentBlob()
0x23a8b  call     T0x2B000151
0x23a90  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x23a95  callvirt instance int32 [mscorlib]System.String::get_Length()
0x23a9a  stloc.s  9
0x23a9c  ldloc.s  9
0x23a9e  ldarg.0
0x23a9f  call     instance string Microsoft.VisualStudio.Setup.Security.ManifestDoc::get_ContentBlob()
0x23aa4  callvirt instance int32 [mscorlib]System.String::get_Length()
0x23aa9  beq.s    loc_23ACC
0x23aab  ldarg.0
0x23aac  ldarg.0
0x23aad  call     instance string Microsoft.VisualStudio.Setup.Security.ManifestDoc::get_ContentBlob()
0x23ab2  ldloc.s  9
0x23ab4  ldarg.0
0x23ab5  call     instance string Microsoft.VisualStudio.Setup.Security.ManifestDoc::get_ContentBlob()
0x23aba  callvirt instance int32 [mscorlib]System.String::get_Length()
0x23abf  ldloc.s  9
0x23ac1  sub
0x23ac2  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x23ac7  call     instance void Microsoft.VisualStudio.Setup.Security.ManifestDoc::set_ContentWhiteSpace(string value)
0x23acc  ldarg.0
0x23acd  ldarg.0
0x23ace  call     instance string Microsoft.VisualStudio.Setup.Security.ManifestDoc::get_ContentBlob()
0x23ad3  call     T0x2B000151
0x23ad8  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x23add  call     instance void Microsoft.VisualStudio.Setup.Security.ManifestDoc::set_ContentBlob(string value)
0x23ae2  ldarg.0
0x23ae3  ldarg.0
0x23ae4  call     instance string Microsoft.VisualStudio.Setup.Security.ManifestDoc::get_ContentBlob()
0x23ae9  ldarg.0
0x23aea  ldfld    string Microsoft.VisualStudio.Setup.Security.ManifestDoc::comma
0x23aef  call     string [mscorlib]System.String::Concat(string, string)
0x23af4  call     instance void Microsoft.VisualStudio.Setup.Security.ManifestDoc::set_ContentBlob(string value)
0x23af9  ldarg.0
0x23afa  ldloc.s  4
0x23afc  ldloc.s  5
0x23afe  ldarg.0
0x23aff  ldfld    string Microsoft.VisualStudio.Setup.Security.ManifestDoc::ps1SignatureBeginTag
0x23b04  callvirt instance int32 [mscorlib]System.String::get_Length()
0x23b09  add
0x23b0a  callvirt instance string [mscorlib]System.String::Substring(int32)
0x23b0f  call     instance void Microsoft.VisualStudio.Setup.Security.ManifestDoc::set_SignatureBlob(string value)
0x23b14  ldarg.0
0x23b15  ldarg.0
0x23b16  call     instance string Microsoft.VisualStudio.Setup.Security.ManifestDoc::get_SignatureBlob()
0x23b1b  ldc.i4.0
0x23b1c  ldarg.0
0x23b1d  call     instance string Microsoft.VisualStudio.Setup.Security.ManifestDoc::get_SignatureBlob()
0x23b22  callvirt instance int32 [mscorlib]System.String::get_Length()
0x23b27  ldarg.0
0x23b28  ldfld    string Microsoft.VisualStudio.Setup.Security.ManifestDoc::ps1SignatureEndTag
0x23b2d  callvirt instance int32 [mscorlib]System.String::get_Length()
0x23b32  sub
0x23b33  ldc.i4.2
0x23b34  sub
0x23b35  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x23b3a  call     instance void Microsoft.VisualStudio.Setup.Security.ManifestDoc::set_SignatureBlob(string value)
0x23b3f  ldarg.0
0x23b40  ldarg.0
0x23b41  ldfld    string Microsoft.VisualStudio.Setup.Security.ManifestDoc::lBracket
0x23b46  ldloc.s  4
0x23b48  ldloc.s  5
0x23b4a  callvirt instance string [mscorlib]System.String::Substring(int32)
0x23b4f  call     string [mscorlib]System.String::Concat(string, string)
0x23b54  call     instance void Microsoft.VisualStudio.Setup.Security.ManifestDoc::set_SignatureBlob(string value)
0x23b59  br       loc_23C52
0x23b5e  ldloc.s  4
0x23b60  ldstr    aSignature// "\"signature\""
0x23b65  callvirt instance bool [mscorlib]System.String::Contains(string)
0x23b6a  brfalse.s loc_23BCB
0x23b6c  ldloc.s  4
0x23b6e  ldstr    aSignature// "\"signature\""
0x23b73  ldc.i4.5
0x23b74  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x23b79  stloc.s  5
0x23b7b  ldarg.0
0x23b7c  ldloc.s  4
0x23b7e  ldc.i4.0
0x23b7f  ldloc.s  5
0x23b81  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x23b86  call     instance void Microsoft.VisualStudio.Setup.Security.ManifestDoc::set_ContentBlob(string value)
0x23b8b  ldarg.0
0x23b8c  ldarg.0
0x23b8d  call     instance string Microsoft.VisualStudio.Setup.Security.ManifestDoc::get_ContentBlob()
0x23b92  ldc.i4.0
0x23b93  ldarg.0
0x23b94  call     instance string Microsoft.VisualStudio.Setup.Security.ManifestDoc::get_ContentBlob()
0x23b99  ldc.i4.s 0x2C
0x23b9b  callvirt instance int32 [mscorlib]System.String::LastIndexOf(char)
0x23ba0  ldc.i4.1
0x23ba1  add
0x23ba2  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x23ba7  call     instance void Microsoft.VisualStudio.Setup.Security.ManifestDoc::set_ContentBlob(string value)
0x23bac  ldarg.0
0x23bad  ldarg.0
0x23bae  ldfld    string Microsoft.VisualStudio.Setup.Security.ManifestDoc::lBracket
0x23bb3  ldloc.s  4
0x23bb5  ldloc.s  5
0x23bb7  callvirt instance string [mscorlib]System.String::Substring(int32)
0x23bbc  call     string [mscorlib]System.String::Concat(string, string)
0x23bc1  call     instance void Microsoft.VisualStudio.Setup.Security.ManifestDoc::set_SignatureBlob(string value)
0x23bc6  br       loc_23C52
0x23bcb  ldarg.0
0x23bcc  ldloc.s  4
0x23bce  call     instance void Microsoft.VisualStudio.Setup.Security.ManifestDoc::set_ContentBlob(string value)
0x23bd3  ldarg.0
0x23bd4  ldarg.0
0x23bd5  call     instance string Microsoft.VisualStudio.Setup.Security.ManifestDoc::get_ContentBlob()
0x23bda  call     T0x2B000151
0x23bdf  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x23be4  call     instance void Microsoft.VisualStudio.Setup.Security.ManifestDoc::set_ContentBlob(string value)
0x23be9  ldarg.0
0x23bea  call     instance string Microsoft.VisualStudio.Setup.Security.ManifestDoc::get_ContentBlob()
0x23bef  ldstr    asc_8C4FA// "}"
0x23bf4  callvirt instance bool [mscorlib]System.String::Contains(string)
0x23bf9  brtrue.s loc_23C06
0x23bfb  ldstr    aBadManifestFor// "Bad_Manifest_Format"
0x23c00  newobj   instance void [mscorlib]System.ApplicationException::.ctor(string)
0x23c05  throw
0x23c06  ldarg.0
0x23c07  ldarg.0
0x23c08  call     instance string Microsoft.VisualStudio.Setup.Security.ManifestDoc::get_ContentBlob()
0x23c0d  ldc.i4.0
0x23c0e  ldarg.0
0x23c0f  call     instance string Microsoft.VisualStudio.Setup.Security.ManifestDoc::get_ContentBlob()
0x23c14  ldc.i4.s 0x7D
0x23c16  callvirt instance int32 [mscorlib]System.String::LastIndexOf(char)
0x23c1b  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x23c20  call     instance void Microsoft.VisualStudio.Setup.Security.ManifestDoc::set_ContentBlob(string value)
0x23c25  ldarg.0
0x23c26  ldarg.0
0x23c27  call     instance string Microsoft.VisualStudio.Setup.Security.ManifestDoc::get_ContentBlob()
0x23c2c  call     T0x2B000151
0x23c31  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x23c36  call     instance void Microsoft.VisualStudio.Setup.Security.ManifestDoc::set_ContentBlob(string value)
0x23c3b  ldarg.0
0x23c3c  ldarg.0
0x23c3d  call     instance string Microsoft.VisualStudio.Setup.Security.ManifestDoc::get_ContentBlob()
0x23c42  ldarg.0
0x23c43  ldfld    string Microsoft.VisualStudio.Setup.Security.ManifestDoc::comma
0x23c48  call     string [mscorlib]System.String::Concat(string, string)
0x23c4d  call     instance void Microsoft.VisualStudio.Setup.Security.ManifestDoc::set_ContentBlob(string value)
0x23c52  leave.s  loc_23C68
0x23c54  stloc.s  0xA
0x23c56  ldstr    aInvalidManifes// "Invalid Manifest File "
0x23c5b  ldloc.s  0xA
0x23c5d  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x23c62  newobj   instance void [mscorlib]System.Exception::.ctor(string, class [mscorlib]System.Exception)
0x23c67  throw
0x23c68  ret
```
