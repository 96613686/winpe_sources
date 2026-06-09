# System.Deployment.Application.ManifestReader::FromDocument

- ea: `0x19e90`
- end: `0x1a058`
- name: `System.Deployment.Application.ManifestReader::FromDocument`
- size: `456`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x139e0`
- `0x13b90`

## callees

- `0x40`
- `0x146b0`
- `0x147b0`
- `0x17cd0`
- `0x17d40`
- `0x19e90`
- `0x1a0f0`
- `0x22b20`
- `0x23020`
- `0x23380`
- `0x233b0`
- `0x233e0`
- `0x24840`
- `0x250e0`
- `0x25a00`

## string_xrefs

- `0x19ea0`: `ManifestReader.FromDocument(`
- `0x19eca`: `Ex_ManifestFileTooLarge`
- `0x19f29`: `Manifest is parsed successfully.`
- `0x19f77`: `Ex_ManifestFromDocument`
- `0x19fbb`: `Ex_ManifestFromDocument`
- `0x19fff`: `Ex_ManifestFromDocument`

## pseudocode

```c

```

## disassembly

```asm
0x19e90  call     class Microsoft.Internal.Performance.CodeMarkers System.Deployment.Application.CodeMarker_Singleton::get_Instance()
0x19e95  ldc.i4   0x1C86
0x19e9a  callvirt instance bool Microsoft.Internal.Performance.CodeMarkers::CodeMarker(int32 nTimerID)
0x19e9f  pop
0x19ea0  ldstr    aManifestreader// "ManifestReader.FromDocument("
0x19ea5  ldarg.0
0x19ea6  ldstr    aCalled// ") called."
0x19eab  call     string [mscorlib]System.String::Concat(string, string, string)
0x19eb0  call     void System.Deployment.Application.Logger::AddMethodCall(string message)
0x19eb5  ldarg.0
0x19eb6  newobj   instance void [mscorlib]System.IO.FileInfo::.ctor(string)
0x19ebb  stloc.1
0x19ebc  ldloc.1
0x19ebd  callvirt instance int64 [mscorlib]System.IO.FileInfo::get_Length()
0x19ec2  ldc.i4   0x1000000
0x19ec7  conv.i8
0x19ec8  ble.s    loc_19EDA
0x19eca  ldstr    aExManifestfile// "Ex_ManifestFileTooLarge"
0x19ecf  call     string System.Deployment.Application.Resources::GetString(string s)
0x19ed4  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(string message)
0x19ed9  throw
0x19eda  ldarg.0
0x19edb  ldc.i4.3
0x19edc  ldc.i4.1
0x19edd  newobj   instance void [mscorlib]System.IO.FileStream::.ctor(string, valuetype [mscorlib]System.IO.FileMode, valuetype [mscorlib]System.IO.FileAccess)
0x19ee2  stloc.2
0x19ee3  newobj   instance void [System.Xml]System.Xml.XmlReaderSettings::.ctor()
0x19ee8  stloc.3
0x19ee9  ldloc.3
0x19eea  ldc.i4.0
0x19eeb  callvirt instance void [System.Xml]System.Xml.XmlReaderSettings::set_DtdProcessing(valuetype [System.Xml]System.Xml.DtdProcessing)
0x19ef0  ldloc.3
0x19ef1  ldnull
0x19ef2  callvirt instance void [System.Xml]System.Xml.XmlReaderSettings::set_XmlResolver(class [System.Xml]System.Xml.XmlResolver)
0x19ef7  call     bool System.Deployment.Application.PolicyKeys::SkipSchemaValidation()
0x19efc  brtrue.s loc_19F06
0x19efe  ldloc.2
0x19eff  call     class [System.Xml]System.Xml.XmlReader System.Deployment.Application.ManifestValidatingReader::Create(class [mscorlib]System.IO.Stream stream)
0x19f04  br.s     loc_19F0D
0x19f06  ldloc.2
0x19f07  ldloc.3
0x19f08  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.Stream, class [System.Xml]System.Xml.XmlReaderSettings)
0x19f0d  stloc.s  4
0x19f0f  ldloc.s  4
0x19f11  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x19f16  brtrue.s loc_19F0F
0x19f18  ldstr    aSchemaValidati// "Schema validation passed."
0x19f1d  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x19f22  ldloc.2
0x19f23  newobj   instance void System.Deployment.Application.Manifest.AssemblyManifest::.ctor(class [mscorlib]System.IO.FileStream fileStream)
0x19f28  stloc.0
0x19f29  ldstr    aManifestIsPars// "Manifest is parsed successfully."
0x19f2e  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x19f33  call     bool System.Deployment.Application.PolicyKeys::SkipSemanticValidation()
0x19f38  brtrue.s loc_19F41
0x19f3a  ldloc.0
0x19f3b  ldarg.1
0x19f3c  callvirt instance void System.Deployment.Application.Manifest.AssemblyManifest::ValidateSemantics(valuetype ManifestType manifestType)
0x19f41  ldstr    aSemanticValida// "Semantic validation passed."
0x19f46  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x19f4b  call     bool System.Deployment.Application.PolicyKeys::SkipSignatureValidation()
0x19f50  brtrue.s loc_19F61
0x19f52  ldloc.2
0x19f53  ldc.i4.0
0x19f54  conv.i8
0x19f55  callvirt instance void [mscorlib]System.IO.Stream::set_Position(int64)
0x19f5a  ldloc.0
0x19f5b  ldloc.2
0x19f5c  callvirt instance void System.Deployment.Application.Manifest.AssemblyManifest::ValidateSignature(class [mscorlib]System.IO.Stream s)
0x19f61  ldstr    aSignatureValid// "Signature validation passed."
0x19f66  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x19f6b  leave    loc_1A046
0x19f70  stloc.s  5
0x19f72  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x19f77  ldstr    aExManifestfrom// "Ex_ManifestFromDocument"
0x19f7c  call     string System.Deployment.Application.Resources::GetString(string s)
0x19f81  ldc.i4.1
0x19f82  newarr   [mscorlib]System.Object
0x19f87  dup
0x19f88  ldc.i4.0
0x19f89  ldarg.2
0x19f8a  ldnull
0x19f8b  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x19f90  brtrue.s loc_19F9A
0x19f92  ldarg.0
0x19f93  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x19f98  br.s     loc_19FA0
0x19f9a  ldarg.2
0x19f9b  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x19fa0  stelem.ref
0x19fa1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x19fa6  stloc.s  6
0x19fa8  ldc.i4.s 0xF
0x19faa  ldloc.s  6
0x19fac  ldloc.s  5
0x19fae  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message, class [mscorlib]System.Exception innerException)
0x19fb3  throw
0x19fb4  stloc.s  7
0x19fb6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x19fbb  ldstr    aExManifestfrom// "Ex_ManifestFromDocument"
0x19fc0  call     string System.Deployment.Application.Resources::GetString(string s)
0x19fc5  ldc.i4.1
0x19fc6  newarr   [mscorlib]System.Object
0x19fcb  dup
0x19fcc  ldc.i4.0
0x19fcd  ldarg.2
0x19fce  ldnull
0x19fcf  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x19fd4  brtrue.s loc_19FDE
0x19fd6  ldarg.0
0x19fd7  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x19fdc  br.s     loc_19FE4
0x19fde  ldarg.2
0x19fdf  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x19fe4  stelem.ref
0x19fe5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x19fea  stloc.s  8
0x19fec  ldc.i4.s 0xF
0x19fee  ldloc.s  8
0x19ff0  ldloc.s  7
0x19ff2  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message, class [mscorlib]System.Exception innerException)
0x19ff7  throw
0x19ff8  stloc.s  9
0x19ffa  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x19fff  ldstr    aExManifestfrom// "Ex_ManifestFromDocument"
0x1a004  call     string System.Deployment.Application.Resources::GetString(string s)
0x1a009  ldc.i4.1
0x1a00a  newarr   [mscorlib]System.Object
0x1a00f  dup
0x1a010  ldc.i4.0
0x1a011  ldarg.2
0x1a012  ldnull
0x1a013  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x1a018  brtrue.s loc_1A022
0x1a01a  ldarg.0
0x1a01b  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x1a020  br.s     loc_1A028
0x1a022  ldarg.2
0x1a023  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x1a028  stelem.ref
0x1a029  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1a02e  stloc.s  0xA
0x1a030  ldc.i4.s 0xF
0x1a032  ldloc.s  0xA
0x1a034  ldloc.s  9
0x1a036  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message, class [mscorlib]System.Exception innerException)
0x1a03b  throw
0x1a03c  ldloc.2
0x1a03d  brfalse.s loc_1A045
0x1a03f  ldloc.2
0x1a040  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1a045  endfinally
0x1a046  call     class Microsoft.Internal.Performance.CodeMarkers System.Deployment.Application.CodeMarker_Singleton::get_Instance()
0x1a04b  ldc.i4   0x1C87
0x1a050  callvirt instance bool Microsoft.Internal.Performance.CodeMarkers::CodeMarker(int32 nTimerID)
0x1a055  pop
0x1a056  ldloc.0
0x1a057  ret
```
