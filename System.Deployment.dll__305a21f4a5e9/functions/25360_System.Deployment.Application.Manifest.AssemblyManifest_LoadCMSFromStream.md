# System.Deployment.Application.Manifest.AssemblyManifest::LoadCMSFromStream

- ea: `0x25360`
- end: `0x25628`
- name: `System.Deployment.Application.Manifest.AssemblyManifest::LoadCMSFromStream`
- size: `712`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x24840`
- `0x24880`
- `0x25630`
- `0x25670`

## callees

- `0x37d0`
- `0x147a0`
- `0x147b0`
- `0x23020`
- `0x25360`
- `0x2cba0`
- `0x2cbc0`
- `0x2d880`
- `0x2d8b0`

## string_xrefs

- `0x253a2`: `Ex_ManifestReadException`
- `0x253f4`: `Ex_ManifestParseCMSErrorMessage`
- `0x254b2`: `Ex_ManifestParseCMSErrorMessage`
- `0x25570`: `Ex_ManifestParseCMSErrorMessage`
- `0x25468`: `Ex_ManifestCMSParsingException`
- `0x25526`: `Ex_ManifestCMSParsingException`
- `0x255e4`: `Ex_ManifestCMSParsingException`
- `0x25610`: `Ex_IsoNullCmsCreated`

## pseudocode

```c

```

## disassembly

```asm
0x25360  ldnull
0x25361  stloc.0
0x25362  newobj   instance void ManifestParseErrors::.ctor()
0x25367  stloc.1
0x25368  ldarg.1
0x25369  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x2536e  conv.i4
0x2536f  stloc.2
0x25370  ldarg.0
0x25371  ldloc.2
0x25372  newarr   [mscorlib]System.Byte
0x25377  stfld    unsigned int8[] System.Deployment.Application.Manifest.AssemblyManifest::_rawXmlBytes
0x2537c  ldarg.1
0x2537d  callvirt instance bool [mscorlib]System.IO.Stream::get_CanSeek()
0x25382  brfalse.s loc_2538E
0x25384  ldarg.1
0x25385  ldc.i4.0
0x25386  conv.i8
0x25387  ldc.i4.0
0x25388  callvirt instance int64 [mscorlib]System.IO.Stream::Seek(int64, valuetype [mscorlib]System.IO.SeekOrigin)
0x2538d  pop
0x2538e  ldarg.1
0x2538f  ldarg.0
0x25390  ldfld    unsigned int8[] System.Deployment.Application.Manifest.AssemblyManifest::_rawXmlBytes
0x25395  ldc.i4.0
0x25396  ldloc.2
0x25397  callvirt instance int32 [mscorlib]System.IO.Stream::Read(unsigned int8[], int32, int32)
0x2539c  pop
0x2539d  leave.s  loc_253B3
0x2539f  stloc.3
0x253a0  ldc.i4.s 0xF
0x253a2  ldstr    aExManifestread// "Ex_ManifestReadException"
0x253a7  call     string System.Deployment.Application.Resources::GetString(string s)
0x253ac  ldloc.3
0x253ad  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message, class [mscorlib]System.Exception innerException)
0x253b2  throw
0x253b3  nop
0x253b4  ldarg.0
0x253b5  ldfld    unsigned int8[] System.Deployment.Application.Manifest.AssemblyManifest::_rawXmlBytes
0x253ba  ldloc.2
0x253bb  ldloc.1
0x253bc  ldsflda  valuetype [mscorlib]System.Guid System.Deployment.Internal.Isolation.IsolationInterop::IID_ICMS
0x253c1  call     object System.Deployment.Internal.Isolation.IsolationInterop::CreateCMSFromXml([hasfieldmarshal] unsigned int8[], [in] unsigned int32 buffer, [in] class System.Deployment.Internal.Isolation.IManifestParseErrorCallback bufferSize, [in] valuetype [mscorlib]System.Guid& Callback)
0x253c6  castclass System.Deployment.Internal.Isolation.Manifest.ICMS
0x253cb  stloc.0
0x253cc  leave    loc_2560B
0x253d1  stloc.s  4
0x253d3  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x253d8  stloc.s  5
0x253da  ldloc.1
0x253db  callvirt instance class ParseErrorEnumerator ManifestParseErrors::GetEnumerator()
0x253e0  stloc.s  6
0x253e2  br.s     loc_25441
0x253e4  ldloc.s  6
0x253e6  callvirt instance class ManifestParseError ParseErrorEnumerator::get_Current()
0x253eb  stloc.s  7
0x253ed  ldloc.s  5
0x253ef  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x253f4  ldstr    aExManifestpars// "Ex_ManifestParseCMSErrorMessage"
0x253f9  call     string System.Deployment.Application.Resources::GetString(string s)
0x253fe  ldc.i4.4
0x253ff  newarr   [mscorlib]System.Object
0x25404  dup
0x25405  ldc.i4.0
0x25406  ldloc.s  7
0x25408  ldfld    int32 ManifestParseError::hr
0x2540d  box      [mscorlib]System.Int32
0x25412  stelem.ref
0x25413  dup
0x25414  ldc.i4.1
0x25415  ldloc.s  7
0x25417  ldfld    unsigned int32 ManifestParseError::StartLine
0x2541c  box      [mscorlib]System.UInt32
0x25421  stelem.ref
0x25422  dup
0x25423  ldc.i4.2
0x25424  ldloc.s  7
0x25426  ldfld    unsigned int32 ManifestParseError::nStartColumn
0x2542b  box      [mscorlib]System.UInt32
0x25430  stelem.ref
0x25431  dup
0x25432  ldc.i4.3
0x25433  ldloc.s  7
0x25435  ldfld    string ManifestParseError::ErrorStatusHostFile
0x2543a  stelem.ref
0x2543b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x25440  pop
0x25441  ldloc.s  6
0x25443  callvirt instance bool ParseErrorEnumerator::MoveNext()
0x25448  brtrue.s loc_253E4
0x2544a  leave.s  loc_25461
0x2544c  ldloc.s  6
0x2544e  isinst   [mscorlib]System.IDisposable
0x25453  stloc.s  8
0x25455  ldloc.s  8
0x25457  brfalse.s loc_25460
0x25459  ldloc.s  8
0x2545b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x25460  endfinally
0x25461  ldc.i4.s 0xF
0x25463  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x25468  ldstr    aExManifestcmsp// "Ex_ManifestCMSParsingException"
0x2546d  call     string System.Deployment.Application.Resources::GetString(string s)
0x25472  ldc.i4.1
0x25473  newarr   [mscorlib]System.Object
0x25478  dup
0x25479  ldc.i4.0
0x2547a  ldloc.s  5
0x2547c  callvirt instance string [mscorlib]System.Object::ToString()
0x25481  stelem.ref
0x25482  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x25487  ldloc.s  4
0x25489  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message, class [mscorlib]System.Exception innerException)
0x2548e  throw
0x2548f  stloc.s  9
0x25491  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x25496  stloc.s  0xA
0x25498  ldloc.1
0x25499  callvirt instance class ParseErrorEnumerator ManifestParseErrors::GetEnumerator()
0x2549e  stloc.s  0xB
0x254a0  br.s     loc_254FF
0x254a2  ldloc.s  0xB
0x254a4  callvirt instance class ManifestParseError ParseErrorEnumerator::get_Current()
0x254a9  stloc.s  0xC
0x254ab  ldloc.s  0xA
0x254ad  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x254b2  ldstr    aExManifestpars// "Ex_ManifestParseCMSErrorMessage"
0x254b7  call     string System.Deployment.Application.Resources::GetString(string s)
0x254bc  ldc.i4.4
0x254bd  newarr   [mscorlib]System.Object
0x254c2  dup
0x254c3  ldc.i4.0
0x254c4  ldloc.s  0xC
0x254c6  ldfld    int32 ManifestParseError::hr
0x254cb  box      [mscorlib]System.Int32
0x254d0  stelem.ref
0x254d1  dup
0x254d2  ldc.i4.1
0x254d3  ldloc.s  0xC
0x254d5  ldfld    unsigned int32 ManifestParseError::StartLine
0x254da  box      [mscorlib]System.UInt32
0x254df  stelem.ref
0x254e0  dup
0x254e1  ldc.i4.2
0x254e2  ldloc.s  0xC
0x254e4  ldfld    unsigned int32 ManifestParseError::nStartColumn
0x254e9  box      [mscorlib]System.UInt32
0x254ee  stelem.ref
0x254ef  dup
0x254f0  ldc.i4.3
0x254f1  ldloc.s  0xC
0x254f3  ldfld    string ManifestParseError::ErrorStatusHostFile
0x254f8  stelem.ref
0x254f9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x254fe  pop
0x254ff  ldloc.s  0xB
0x25501  callvirt instance bool ParseErrorEnumerator::MoveNext()
0x25506  brtrue.s loc_254A2
0x25508  leave.s  loc_2551F
0x2550a  ldloc.s  0xB
0x2550c  isinst   [mscorlib]System.IDisposable
0x25511  stloc.s  8
0x25513  ldloc.s  8
0x25515  brfalse.s loc_2551E
0x25517  ldloc.s  8
0x25519  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2551e  endfinally
0x2551f  ldc.i4.s 0xF
0x25521  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x25526  ldstr    aExManifestcmsp// "Ex_ManifestCMSParsingException"
0x2552b  call     string System.Deployment.Application.Resources::GetString(string s)
0x25530  ldc.i4.1
0x25531  newarr   [mscorlib]System.Object
0x25536  dup
0x25537  ldc.i4.0
0x25538  ldloc.s  0xA
0x2553a  callvirt instance string [mscorlib]System.Object::ToString()
0x2553f  stelem.ref
0x25540  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x25545  ldloc.s  9
0x25547  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message, class [mscorlib]System.Exception innerException)
0x2554c  throw
0x2554d  stloc.s  0xD
0x2554f  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x25554  stloc.s  0xE
0x25556  ldloc.1
0x25557  callvirt instance class ParseErrorEnumerator ManifestParseErrors::GetEnumerator()
0x2555c  stloc.s  0xF
0x2555e  br.s     loc_255BD
0x25560  ldloc.s  0xF
0x25562  callvirt instance class ManifestParseError ParseErrorEnumerator::get_Current()
0x25567  stloc.s  0x10
0x25569  ldloc.s  0xE
0x2556b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x25570  ldstr    aExManifestpars// "Ex_ManifestParseCMSErrorMessage"
0x25575  call     string System.Deployment.Application.Resources::GetString(string s)
0x2557a  ldc.i4.4
0x2557b  newarr   [mscorlib]System.Object
0x25580  dup
0x25581  ldc.i4.0
0x25582  ldloc.s  0x10
0x25584  ldfld    int32 ManifestParseError::hr
0x25589  box      [mscorlib]System.Int32
0x2558e  stelem.ref
0x2558f  dup
0x25590  ldc.i4.1
0x25591  ldloc.s  0x10
0x25593  ldfld    unsigned int32 ManifestParseError::StartLine
0x25598  box      [mscorlib]System.UInt32
0x2559d  stelem.ref
0x2559e  dup
0x2559f  ldc.i4.2
0x255a0  ldloc.s  0x10
0x255a2  ldfld    unsigned int32 ManifestParseError::nStartColumn
0x255a7  box      [mscorlib]System.UInt32
0x255ac  stelem.ref
0x255ad  dup
0x255ae  ldc.i4.3
0x255af  ldloc.s  0x10
0x255b1  ldfld    string ManifestParseError::ErrorStatusHostFile
0x255b6  stelem.ref
0x255b7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x255bc  pop
0x255bd  ldloc.s  0xF
0x255bf  callvirt instance bool ParseErrorEnumerator::MoveNext()
0x255c4  brtrue.s loc_25560
0x255c6  leave.s  loc_255DD
0x255c8  ldloc.s  0xF
0x255ca  isinst   [mscorlib]System.IDisposable
0x255cf  stloc.s  8
0x255d1  ldloc.s  8
0x255d3  brfalse.s loc_255DC
0x255d5  ldloc.s  8
0x255d7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x255dc  endfinally
0x255dd  ldc.i4.s 0xF
0x255df  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x255e4  ldstr    aExManifestcmsp// "Ex_ManifestCMSParsingException"
0x255e9  call     string System.Deployment.Application.Resources::GetString(string s)
0x255ee  ldc.i4.1
0x255ef  newarr   [mscorlib]System.Object
0x255f4  dup
0x255f5  ldc.i4.0
0x255f6  ldloc.s  0xE
0x255f8  callvirt instance string [mscorlib]System.Object::ToString()
0x255fd  stelem.ref
0x255fe  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x25603  ldloc.s  0xD
0x25605  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message, class [mscorlib]System.Exception innerException)
0x2560a  throw
0x2560b  ldloc.0
0x2560c  brtrue.s loc_25620
0x2560e  ldc.i4.s 0xF
0x25610  ldstr    aExIsonullcmscr// "Ex_IsoNullCmsCreated"
0x25615  call     string System.Deployment.Application.Resources::GetString(string s)
0x2561a  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x2561f  throw
0x25620  ldarg.0
0x25621  ldloc.0
0x25622  stfld    class System.Deployment.Internal.Isolation.Manifest.ICMS System.Deployment.Application.Manifest.AssemblyManifest::_cms
0x25627  ret
```
