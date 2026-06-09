# Microsoft.VisualStudio.Setup.Serialization.FeedParser`1::Parse

- ea: `0xef90`
- end: `0xf121`
- name: `Microsoft.VisualStudio.Setup.Serialization.FeedParser`1::Parse`
- size: `401`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0xc1a0`
- `0xc1d0`
- `0xef90`
- `0x10c20`
- `0x110c0`
- `0x11900`
- `0x11940`
- `0x11b30`

## string_xrefs

- `0xef91`: `services`
- `0xf0cb`: `Failed to deserialize `

## pseudocode

```c

```

## disassembly

```asm
0xef90  ldarg.0
0xef91  ldstr    aServices// "services"
0xef96  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0xef9b  ldarg.1
0xef9c  ldstr    aSerializer// "serializer"
0xefa1  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0xefa6  ldarg.2
0xefa7  ldstr    aPath_0// "path"
0xefac  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNullOrEmpty(string s, string paramName)
0xefb1  ldarg.0
0xefb2  ldc.i4.1
0xefb3  call     T0x2B00003E
0xefb8  stloc.0
0xefb9  ldarg.0
0xefba  ldc.i4.0
0xefbb  call     T0x2B00003F
0xefc0  stloc.1
0xefc1  ldloc.0
0xefc2  ldarg.2
0xefc3  callvirt instance bool Microsoft.VisualStudio.Setup.Services.IFileSystem::FileExists(string path)
0xefc8  brtrue.s loc_EFF8
0xefca  ldstr    aFile// "File "
0xefcf  ldarg.2
0xefd0  ldstr    aDoesNotExist// " does not exist."
0xefd5  call     string [mscorlib]System.String::Concat(string, string, string)
0xefda  ldarg.2
0xefdb  newobj   instance void [mscorlib]System.IO.FileNotFoundException::.ctor(string, string)
0xefe0  stloc.2
0xefe1  ldloc.1
0xefe2  brfalse.s loc_EFF6
0xefe4  ldloc.1
0xefe5  ldloc.2
0xefe6  ldloc.2
0xefe7  callvirt instance string [mscorlib]System.Exception::get_Message()
0xefec  call     T0x2B000016
0xeff1  callvirt instance void Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception ex, string format, object[] args)
0xeff6  ldloc.2
0xeff7  throw
0xeff8  ldarg.3
0xeff9  brfalse  loc_F0A0
0xeffe  ldloc.0
0xefff  ldarg.2
0xf000  callvirt instance class [mscorlib]System.IO.Stream Microsoft.VisualStudio.Setup.Services.IFileSystem::OpenFile(string path)
0xf005  stloc.3
0xf006  ldarg.0
0xf007  ldc.i4.1
0xf008  call     T0x2B000071
0xf00d  ldloc.3
0xf00e  ldarg.2
0xf00f  ldnull
0xf010  callvirt instance class Microsoft.VisualStudio.Setup.Security.VerificationInformation Microsoft.VisualStudio.Setup.Security.ISignatureVerifierManager::Verify(class [mscorlib]System.IO.Stream file, [opt] string path, [opt] class Microsoft.VisualStudio.Setup.VerificationContext verificationContext)
0xf015  stloc.s  4
0xf017  ldloc.s  4
0xf019  brtrue.s loc_F027
0xf01b  ldloca.s 6
0xf01d  initobj  valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Security.VerificationResult>
0xf023  ldloc.s  6
0xf025  br.s     loc_F033
0xf027  ldloc.s  4
0xf029  call     instance valuetype Microsoft.VisualStudio.Setup.Security.VerificationResult Microsoft.VisualStudio.Setup.Security.VerificationInformation::get_Result()
0xf02e  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Security.VerificationResult>::.ctor(var<u1>)
0xf033  stloc.s  5
0xf035  ldloca.s 5
0xf037  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Security.VerificationResult>::get_HasValue()
0xf03c  brfalse.s loc_F047
0xf03e  ldloca.s 5
0xf040  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Security.VerificationResult>::GetValueOrDefault()
0xf045  brfalse.s loc_F094
0xf047  ldstr    aFile0DidNotPas// "File {0} did not pass signature validat"...
0xf04c  ldarg.2
0xf04d  ldloc.s  4
0xf04f  brtrue.s loc_F05D
0xf051  ldloca.s 5
0xf053  initobj  valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Security.VerificationResult>
0xf059  ldloc.s  5
0xf05b  br.s     loc_F069
0xf05d  ldloc.s  4
0xf05f  call     instance valuetype Microsoft.VisualStudio.Setup.Security.VerificationResult Microsoft.VisualStudio.Setup.Security.VerificationInformation::get_Result()
0xf064  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Security.VerificationResult>::.ctor(var<u1>)
0xf069  box      valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Security.VerificationResult>
0xf06e  call     string [mscorlib]System.String::Format(string, object, object)
0xf073  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xf078  stloc.s  7
0xf07a  ldloc.1
0xf07b  brfalse.s loc_F091
0xf07d  ldloc.1
0xf07e  ldloc.s  7
0xf080  ldloc.s  7
0xf082  callvirt instance string [mscorlib]System.Exception::get_Message()
0xf087  call     T0x2B000016
0xf08c  callvirt instance void Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception ex, string format, object[] args)
0xf091  ldloc.s  7
0xf093  throw
0xf094  leave.s  loc_F0A0
0xf096  ldloc.3
0xf097  brfalse.s loc_F09F
0xf099  ldloc.3
0xf09a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf09f  endfinally
0xf0a0  ldloc.0
0xf0a1  ldarg.2
0xf0a2  callvirt instance class [mscorlib]System.IO.Stream Microsoft.VisualStudio.Setup.Services.IFileSystem::OpenFile(string path)
0xf0a7  stloc.s  8
0xf0a9  ldloc.s  8
0xf0ab  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(class [mscorlib]System.IO.Stream)
0xf0b0  stloc.s  9
0xf0b2  ldarg.1
0xf0b3  ldloc.s  9
0xf0b5  callvirt instance var<u1> class Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<var<u1>>::Deserialize(!!T0)
0xf0ba  dup
0xf0bb  box      var<u1>
0xf0c0  brtrue.s loc_F102
0xf0c2  pop
0xf0c3  ldc.i4.5
0xf0c4  newarr   [mscorlib]System.String
0xf0c9  dup
0xf0ca  ldc.i4.0
0xf0cb  ldstr    aFailedToDeseri// "Failed to deserialize "
0xf0d0  stelem.ref
0xf0d1  dup
0xf0d2  ldc.i4.1
0xf0d3  ldtoken  var<u1>
0xf0d8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xf0dd  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xf0e2  stelem.ref
0xf0e3  dup
0xf0e4  ldc.i4.2
0xf0e5  ldstr    aFrom// " from '"
0xf0ea  stelem.ref
0xf0eb  dup
0xf0ec  ldc.i4.3
0xf0ed  ldarg.2
0xf0ee  stelem.ref
0xf0ef  dup
0xf0f0  ldc.i4.4
0xf0f1  ldstr    asc_21DE4// "'."
0xf0f6  stelem.ref
0xf0f7  call     string [mscorlib]System.String::Concat(string[])
0xf0fc  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializationException::.ctor(string)
0xf101  throw
0xf102  stloc.s  0xA
0xf104  leave.s  loc_F11E
0xf106  ldloc.s  9
0xf108  brfalse.s loc_F111
0xf10a  ldloc.s  9
0xf10c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf111  endfinally
0xf112  ldloc.s  8
0xf114  brfalse.s loc_F11D
0xf116  ldloc.s  8
0xf118  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf11d  endfinally
0xf11e  ldloc.s  0xA
0xf120  ret
```
