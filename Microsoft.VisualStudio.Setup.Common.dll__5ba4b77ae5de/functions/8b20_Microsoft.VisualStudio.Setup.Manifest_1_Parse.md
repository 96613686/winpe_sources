# Microsoft.VisualStudio.Setup.Manifest`1::Parse

- ea: `0x8b20`
- end: `0x8bab`
- name: `Microsoft.VisualStudio.Setup.Manifest`1::Parse`
- size: `139`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x8b20`
- `0xc1a0`
- `0xc1d0`
- `0x11900`
- `0x11970`
- `0x11b30`

## string_xrefs

- `0x8b21`: `services`

## pseudocode

```c

```

## disassembly

```asm
0x8b20  ldarg.0
0x8b21  ldstr    aServices// "services"
0x8b26  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x8b2b  ldarg.1
0x8b2c  ldstr    aPath_0// "path"
0x8b31  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNullOrEmpty(string s, string paramName)
0x8b36  ldarg.2
0x8b37  ldstr    aSerializer// "serializer"
0x8b3c  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x8b41  ldarg.0
0x8b42  ldc.i4.1
0x8b43  call     T0x2B00003E
0x8b48  ldarg.0
0x8b49  ldc.i4.0
0x8b4a  call     T0x2B00003F
0x8b4f  stloc.0
0x8b50  dup
0x8b51  ldarg.1
0x8b52  callvirt instance bool Microsoft.VisualStudio.Setup.Services.IFileSystem::FileExists(string path)
0x8b57  brtrue.s loc_8B87
0x8b59  ldstr    aFile// "File "
0x8b5e  ldarg.1
0x8b5f  ldstr    aDoesNotExist// " does not exist."
0x8b64  call     string [mscorlib]System.String::Concat(string, string, string)
0x8b69  ldarg.1
0x8b6a  newobj   instance void [mscorlib]System.IO.FileNotFoundException::.ctor(string, string)
0x8b6f  stloc.1
0x8b70  ldloc.0
0x8b71  brfalse.s loc_8B85
0x8b73  ldloc.0
0x8b74  ldloc.1
0x8b75  ldloc.1
0x8b76  callvirt instance string [mscorlib]System.Exception::get_Message()
0x8b7b  call     T0x2B000016
0x8b80  callvirt instance void Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception ex, string format, object[] args)
0x8b85  ldloc.1
0x8b86  throw
0x8b87  ldarg.2
0x8b88  ldarg.1
0x8b89  callvirt instance void class Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<mvar<u1>>::set_Location(string)
0x8b8e  ldarg.1
0x8b8f  callvirt instance class [mscorlib]System.IO.TextReader Microsoft.VisualStudio.Setup.Services.IFileSystem::OpenText(string path)
0x8b94  stloc.2
0x8b95  ldarg.2
0x8b96  ldloc.2
0x8b97  callvirt instance var<u1> class Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<mvar<u1>>::Deserialize(!!T0)
0x8b9c  stloc.3
0x8b9d  leave.s  loc_8BA9
0x8b9f  ldloc.2
0x8ba0  brfalse.s loc_8BA8
0x8ba2  ldloc.2
0x8ba3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8ba8  endfinally
0x8ba9  ldloc.3
0x8baa  ret
```
