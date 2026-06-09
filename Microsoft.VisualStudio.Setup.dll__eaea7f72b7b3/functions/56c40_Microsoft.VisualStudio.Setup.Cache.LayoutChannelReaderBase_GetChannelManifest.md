# Microsoft.VisualStudio.Setup.Cache.LayoutChannelReaderBase::GetChannelManifest

- ea: `0x56c40`
- end: `0x56ce6`
- name: `Microsoft.VisualStudio.Setup.Cache.LayoutChannelReaderBase::GetChannelManifest`
- size: `166`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x566f0`

## callees

- `0x568d0`
- `0x56c40`

## string_xrefs

- `0x56c5c`: `No channel Manifest found at {0}`
- `0x56c8c`: `No channel Manifest found at {0}`
- `0x56cc8`: `Channel manifest signature verified failed.`

## pseudocode

```c

```

## disassembly

```asm
0x56c40  ldarg.0
0x56c41  ldarg.1
0x56c42  callvirt instance string Microsoft.VisualStudio.Setup.Cache.LayoutChannelReaderBase::DownloadChannelManifest(class [System]System.Uri channelUri)
0x56c47  stloc.0
0x56c48  ldloc.0
0x56c49  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x56c4e  brfalse.s loc_56C72
0x56c50  ldarg.0
0x56c51  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Cache.LayoutChannelReaderBase::logger
0x56c56  dup
0x56c57  brtrue.s loc_56C5C
0x56c59  pop
0x56c5a  br.s     loc_56C70
0x56c5c  ldstr    aNoChannelManif// "No channel Manifest found at {0}"
0x56c61  ldc.i4.1
0x56c62  newarr   [mscorlib]System.Object
0x56c67  dup
0x56c68  ldc.i4.0
0x56c69  ldloc.0
0x56c6a  stelem.ref
0x56c6b  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x56c70  ldnull
0x56c71  ret
0x56c72  ldarg.0
0x56c73  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Cache.LayoutChannelReaderBase::fileSystem
0x56c78  ldloc.0
0x56c79  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::FileExists(string)
0x56c7e  brtrue.s loc_56CA2
0x56c80  ldarg.0
0x56c81  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Cache.LayoutChannelReaderBase::logger
0x56c86  dup
0x56c87  brtrue.s loc_56C8C
0x56c89  pop
0x56c8a  br.s     loc_56CA0
0x56c8c  ldstr    aNoChannelManif// "No channel Manifest found at {0}"
0x56c91  ldc.i4.1
0x56c92  newarr   [mscorlib]System.Object
0x56c97  dup
0x56c98  ldc.i4.0
0x56c99  ldloc.0
0x56c9a  stelem.ref
0x56c9b  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x56ca0  ldnull
0x56ca1  ret
0x56ca2  ldarg.0
0x56ca3  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.ISignatureVerifierManager Microsoft.VisualStudio.Setup.Cache.LayoutChannelReaderBase::signatureVerifierManager
0x56ca8  ldloc.0
0x56ca9  ldnull
0x56caa  ldnull
0x56cab  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.ISignatureVerifierManager::Verify(string, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VerificationContext, string)
0x56cb0  stloc.1
0x56cb1  ldloc.1
0x56cb2  brfalse.s loc_56CBC
0x56cb4  ldloc.1
0x56cb5  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationInformation::get_Result()
0x56cba  brfalse.s loc_56CD9
0x56cbc  ldarg.0
0x56cbd  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Cache.LayoutChannelReaderBase::logger
0x56cc2  dup
0x56cc3  brtrue.s loc_56CC8
0x56cc5  pop
0x56cc6  br.s     loc_56CD7
0x56cc8  ldstr    aChannelManifes_1// "Channel manifest signature verified fai"...
0x56ccd  call     T0x2B000003
0x56cd2  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x56cd7  ldnull
0x56cd8  ret
0x56cd9  ldarg.0
0x56cda  ldfld    class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Cache.LayoutChannelReaderBase::services
0x56cdf  ldloc.0
0x56ce0  call     class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifest [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ChannelSets.ChannelManifest::Parse(class [mscorlib]System.IServiceProvider, string)
0x56ce5  ret
```
