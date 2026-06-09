# Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthHelper::GetIdTokenFromResponseString

- ea: `0x35910`
- end: `0x3598d`
- name: `Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthHelper::GetIdTokenFromResponseString`
- size: `125`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x36080`
- `0x36410`

## callees

- `0x35910`
- `0x35b20`

## string_xrefs

- `0x35975`: `Failed to extract ServiceIdToken from Authentication Token`

## pseudocode

```c

```

## disassembly

```asm
0x35910  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x35915  ldarg.0
0x35916  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3591b  ldc.i4.0
0x3591c  ceq
0x3591e  ldstr    aAadResponsestr// "AAD: responseString is null"
0x35923  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x35928  ldarg.0
0x35929  ldc.i4.1
0x3592a  newarr   [mscorlib]System.Char
0x3592f  dup
0x35930  ldc.i4.0
0x35931  ldc.i4.s 0x2E
0x35933  stelem.i2
0x35934  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x35939  stloc.0
0x3593a  ldloc.0
0x3593b  ldlen
0x3593c  conv.i4
0x3593d  ldc.i4.3
0x3593e  bne.un.s loc_35980
0x35940  ldloc.0
0x35941  ldc.i4.1
0x35942  ldelem.ref
0x35943  call     unsigned int8[] Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthHelper::Base64UrlDecode(string chars)
0x35948  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor(unsigned int8[])
0x3594d  stloc.1
0x3594e  ldtoken  Microsoft.ReportingServices.Hybrid.OAuth.ServiceIdToken
0x35953  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x35958  newobj   instance void [System.Runtime.Serialization]System.Runtime.Serialization.Json.DataContractJsonSerializer::.ctor(class [mscorlib]System.Type)
0x3595d  ldloc.1
0x3595e  callvirt instance object [System.Runtime.Serialization]System.Runtime.Serialization.XmlObjectSerializer::ReadObject(class [mscorlib]System.IO.Stream)
0x35963  castclass Microsoft.ReportingServices.Hybrid.OAuth.ServiceIdToken
0x35968  stloc.2
0x35969  leave.s  loc_3598B
0x3596b  ldloc.1
0x3596c  brfalse.s loc_35974
0x3596e  ldloc.1
0x3596f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x35974  endfinally
0x35975  ldstr    aFailedToExtrac// "Failed to extract ServiceIdToken from A"...
0x3597a  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(class [mscorlib]System.Exception, string)
0x3597f  throw
0x35980  ldstr    aThereWasAnErro// "There was an error while trying to sign"...
0x35985  newobj   instance void [mscorlib]System.UnauthorizedAccessException::.ctor(string)
0x3598a  throw
0x3598b  ldloc.2
0x3598c  ret
```
