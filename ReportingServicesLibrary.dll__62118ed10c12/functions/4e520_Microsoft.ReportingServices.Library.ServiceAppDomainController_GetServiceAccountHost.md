# Microsoft.ReportingServices.Library.ServiceAppDomainController::GetServiceAccountHost

- ea: `0x4e520`
- end: `0x4e7b0`
- name: `Microsoft.ReportingServices.Library.ServiceAppDomainController::GetServiceAccountHost`
- size: `656`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x4e450`

## callees

- `0x4e520`

## string_xrefs

- `0x4e57e`: `NT Service\`
- `0x4e5d6`: `(&(ObjectSID={0}))`
- `0x4e62a`: `servicePrincipalName`
- `0x4e65a`: `SPN for the service account is {0}`
- `0x4e6c8`: `The UserAccountControl value for the service account is {0}`

## pseudocode

```c

```

## disassembly

```asm
0x4e520  ldnull
0x4e521  stloc.0
0x4e522  ldnull
0x4e523  stloc.1
0x4e524  call     class [mscorlib]System.Security.Principal.WindowsIdentity [mscorlib]System.Security.Principal.WindowsIdentity::GetCurrent()
0x4e529  dup
0x4e52a  callvirt instance string [mscorlib]System.Security.Claims.ClaimsIdentity::get_Name()
0x4e52f  stloc.2
0x4e530  callvirt instance class [mscorlib]System.Security.Principal.SecurityIdentifier [mscorlib]System.Security.Principal.WindowsIdentity::get_User()
0x4e535  stloc.3
0x4e536  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x4e53b  stloc.s  4
0x4e53d  ldloc.2
0x4e53e  ldc.i4.s 0x5C
0x4e540  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x4e545  stloc.s  5
0x4e547  ldc.i4.m1
0x4e548  ldloc.s  5
0x4e54a  bne.un.s loc_4E554
0x4e54c  newobj   instance void [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::.ctor()
0x4e551  stloc.0
0x4e552  br.s     loc_4E5D0
0x4e554  ldloc.2
0x4e555  ldc.i4.0
0x4e556  ldloc.s  5
0x4e558  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x4e55d  stloc.s  6
0x4e55f  ldloc.3
0x4e560  ldc.i4.s 0x18
0x4e562  callvirt instance bool [mscorlib]System.Security.Principal.SecurityIdentifier::IsWellKnown(valuetype [mscorlib]System.Security.Principal.WellKnownSidType)
0x4e567  brtrue.s loc_4E58B
0x4e569  ldloc.3
0x4e56a  ldc.i4.s 0x16
0x4e56c  callvirt instance bool [mscorlib]System.Security.Principal.SecurityIdentifier::IsWellKnown(valuetype [mscorlib]System.Security.Principal.WellKnownSidType)
0x4e571  brtrue.s loc_4E58B
0x4e573  ldloc.3
0x4e574  ldc.i4.s 0x17
0x4e576  callvirt instance bool [mscorlib]System.Security.Principal.SecurityIdentifier::IsWellKnown(valuetype [mscorlib]System.Security.Principal.WellKnownSidType)
0x4e57b  brtrue.s loc_4E58B
0x4e57d  ldloc.2
0x4e57e  ldstr    aNtService// "NT Service\\"
0x4e583  ldc.i4.5
0x4e584  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x4e589  brfalse.s loc_4E5B4
0x4e58b  call     class [System.DirectoryServices]System.DirectoryServices.ActiveDirectory.Domain [System.DirectoryServices]System.DirectoryServices.ActiveDirectory.Domain::GetComputerDomain()
0x4e590  callvirt instance string [System.DirectoryServices]System.DirectoryServices.ActiveDirectory.ActiveDirectoryPartition::get_Name()
0x4e595  stloc.s  6
0x4e597  ldloc.s  6
0x4e599  ldloc.2
0x4e59a  newobj   instance void [mscorlib]System.Security.Principal.NTAccount::.ctor(string, string)
0x4e59f  ldtoken  [mscorlib]System.Security.Principal.SecurityIdentifier
0x4e5a4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4e5a9  callvirt instance class [mscorlib]System.Security.Principal.IdentityReference [mscorlib]System.Security.Principal.IdentityReference::Translate(class [mscorlib]System.Type)
0x4e5ae  castclass [mscorlib]System.Security.Principal.SecurityIdentifier
0x4e5b3  stloc.3
0x4e5b4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4e5b9  ldstr    aLdap0// "LDAP://{0}"
0x4e5be  ldloc.s  6
0x4e5c0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x4e5c5  newobj   instance void [System.DirectoryServices]System.DirectoryServices.DirectoryEntry::.ctor(string)
0x4e5ca  newobj   instance void [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::.ctor(class [System.DirectoryServices]System.DirectoryServices.DirectoryEntry)
0x4e5cf  stloc.0
0x4e5d0  ldloc.0
0x4e5d1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4e5d6  ldstr    aObjectsid0// "(&(ObjectSID={0}))"
0x4e5db  ldloc.3
0x4e5dc  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x4e5e1  callvirt instance void [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::set_Filter(string)
0x4e5e6  ldloc.0
0x4e5e7  ldc.i4.2
0x4e5e8  callvirt instance void [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::set_SearchScope(valuetype [System.DirectoryServices]System.DirectoryServices.SearchScope)
0x4e5ed  ldloc.0
0x4e5ee  ldc.i4.0
0x4e5ef  ldc.i4.0
0x4e5f0  ldc.i4.3
0x4e5f1  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x4e5f6  callvirt instance void [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::set_ClientTimeout(valuetype [mscorlib]System.TimeSpan)
0x4e5fb  ldloc.0
0x4e5fc  callvirt instance class [System.DirectoryServices]System.DirectoryServices.SearchResultCollection [System.DirectoryServices]System.DirectoryServices.DirectorySearcher::FindAll()
0x4e601  stloc.1
0x4e602  ldloc.1
0x4e603  brfalse  loc_4E798
0x4e608  ldloc.1
0x4e609  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.DirectoryServices]System.DirectoryServices.SearchResultCollection::GetEnumerator()
0x4e60e  stloc.s  7
0x4e610  br       loc_4E775
0x4e615  ldloc.s  7
0x4e617  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x4e61c  castclass [System.DirectoryServices]System.DirectoryServices.SearchResult
0x4e621  stloc.s  8
0x4e623  ldloc.s  8
0x4e625  callvirt instance class [System.DirectoryServices]System.DirectoryServices.ResultPropertyCollection [System.DirectoryServices]System.DirectoryServices.SearchResult::get_Properties()
0x4e62a  ldstr    aServiceprincip// "servicePrincipalName"
0x4e62f  callvirt instance class [System.DirectoryServices]System.DirectoryServices.ResultPropertyValueCollection [System.DirectoryServices]System.DirectoryServices.ResultPropertyCollection::get_Item(string)
0x4e634  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ReadOnlyCollectionBase::GetEnumerator()
0x4e639  stloc.s  9
0x4e63b  br.s     loc_4E66F
0x4e63d  ldloc.s  9
0x4e63f  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x4e644  castclass [mscorlib]System.String
0x4e649  stloc.s  0xA
0x4e64b  ldloc.s  4
0x4e64d  ldloc.s  0xA
0x4e64f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x4e654  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_AppDomainManagerTracer()
0x4e659  ldc.i4.3
0x4e65a  ldstr    aSpnForTheServi// "SPN for the service account is {0}"
0x4e65f  ldc.i4.1
0x4e660  newarr   [mscorlib]System.Object
0x4e665  dup
0x4e666  ldc.i4.0
0x4e667  ldloc.s  0xA
0x4e669  stelem.ref
0x4e66a  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x4e66f  ldloc.s  9
0x4e671  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4e676  brtrue.s loc_4E63D
0x4e678  leave.s  loc_4E68F
0x4e67a  ldloc.s  9
0x4e67c  isinst   [mscorlib]System.IDisposable
0x4e681  stloc.s  0xB
0x4e683  ldloc.s  0xB
0x4e685  brfalse.s loc_4E68E
0x4e687  ldloc.s  0xB
0x4e689  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4e68e  endfinally
0x4e68f  ldloc.s  8
0x4e691  callvirt instance class [System.DirectoryServices]System.DirectoryServices.ResultPropertyCollection [System.DirectoryServices]System.DirectoryServices.SearchResult::get_Properties()
0x4e696  ldstr    aUseraccountcon// "userAccountControl"
0x4e69b  callvirt instance class [System.DirectoryServices]System.DirectoryServices.ResultPropertyValueCollection [System.DirectoryServices]System.DirectoryServices.ResultPropertyCollection::get_Item(string)
0x4e6a0  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ReadOnlyCollectionBase::GetEnumerator()
0x4e6a5  stloc.s  9
0x4e6a7  br.s     loc_4E6E2
0x4e6a9  ldloc.s  9
0x4e6ab  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x4e6b0  stloc.s  0xC
0x4e6b2  ldloc.s  0xC
0x4e6b4  brfalse.s loc_4E6E2
0x4e6b6  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_AppDomainManagerTracer()
0x4e6bb  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x4e6c0  brfalse.s loc_4E6E2
0x4e6c2  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_AppDomainManagerTracer()
0x4e6c7  ldc.i4.3
0x4e6c8  ldstr    aTheUseraccount// "The UserAccountControl value for the se"...
0x4e6cd  ldc.i4.1
0x4e6ce  newarr   [mscorlib]System.Object
0x4e6d3  dup
0x4e6d4  ldc.i4.0
0x4e6d5  ldloc.s  0xC
0x4e6d7  callvirt instance string [mscorlib]System.Object::ToString()
0x4e6dc  stelem.ref
0x4e6dd  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x4e6e2  ldloc.s  9
0x4e6e4  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4e6e9  brtrue.s loc_4E6A9
0x4e6eb  leave.s  loc_4E702
0x4e6ed  ldloc.s  9
0x4e6ef  isinst   [mscorlib]System.IDisposable
0x4e6f4  stloc.s  0xB
0x4e6f6  ldloc.s  0xB
0x4e6f8  brfalse.s loc_4E701
0x4e6fa  ldloc.s  0xB
0x4e6fc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4e701  endfinally
0x4e702  ldloc.s  8
0x4e704  callvirt instance class [System.DirectoryServices]System.DirectoryServices.ResultPropertyCollection [System.DirectoryServices]System.DirectoryServices.SearchResult::get_Properties()
0x4e709  ldstr    aMsdsAllowedtod// "msDS-AllowedToDelegateTo"
0x4e70e  callvirt instance class [System.DirectoryServices]System.DirectoryServices.ResultPropertyValueCollection [System.DirectoryServices]System.DirectoryServices.ResultPropertyCollection::get_Item(string)
0x4e713  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ReadOnlyCollectionBase::GetEnumerator()
0x4e718  stloc.s  9
0x4e71a  br.s     loc_4E755
0x4e71c  ldloc.s  9
0x4e71e  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x4e723  castclass [mscorlib]System.String
0x4e728  stloc.s  0xD
0x4e72a  ldloc.s  0xD
0x4e72c  brfalse.s loc_4E755
0x4e72e  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_AppDomainManagerTracer()
0x4e733  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x4e738  brfalse.s loc_4E755
0x4e73a  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_AppDomainManagerTracer()
0x4e73f  ldc.i4.3
0x4e740  ldstr    aSpnsAllowedFor// "SPNs allowed for constrained delegation"...
0x4e745  ldc.i4.1
0x4e746  newarr   [mscorlib]System.Object
0x4e74b  dup
0x4e74c  ldc.i4.0
0x4e74d  ldloc.s  0xD
0x4e74f  stelem.ref
0x4e750  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x4e755  ldloc.s  9
0x4e757  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4e75c  brtrue.s loc_4E71C
0x4e75e  leave.s  loc_4E775
0x4e760  ldloc.s  9
0x4e762  isinst   [mscorlib]System.IDisposable
0x4e767  stloc.s  0xB
0x4e769  ldloc.s  0xB
0x4e76b  brfalse.s loc_4E774
0x4e76d  ldloc.s  0xB
0x4e76f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4e774  endfinally
0x4e775  ldloc.s  7
0x4e777  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4e77c  brtrue   loc_4E615
0x4e781  leave.s  loc_4E79B
0x4e783  ldloc.s  7
0x4e785  isinst   [mscorlib]System.IDisposable
0x4e78a  stloc.s  0xB
0x4e78c  ldloc.s  0xB
0x4e78e  brfalse.s loc_4E797
0x4e790  ldloc.s  0xB
0x4e792  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4e797  endfinally
0x4e798  ldnull
0x4e799  stloc.s  4
0x4e79b  leave.s  loc_4E7AD
0x4e79d  pop
0x4e79e  ldnull
0x4e79f  stloc.s  4
0x4e7a1  leave.s  loc_4E7AD
0x4e7a3  ldloc.0
0x4e7a4  brfalse.s loc_4E7AC
0x4e7a6  ldloc.0
0x4e7a7  callvirt instance void [System]System.ComponentModel.Component::Dispose()
0x4e7ac  endfinally
0x4e7ad  ldloc.s  4
0x4e7af  ret
```
