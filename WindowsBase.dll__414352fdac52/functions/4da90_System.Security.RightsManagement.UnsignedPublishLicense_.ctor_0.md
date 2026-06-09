# System.Security.RightsManagement.UnsignedPublishLicense::.ctor_0

- ea: `0x4da90`
- end: `0x4dae1`
- name: `System.Security.RightsManagement.UnsignedPublishLicense::.ctor_0`
- size: `81`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x125e0`
- `0x14450`
- `0x146a0`
- `0x2b6f0`
- `0x4da60`
- `0x4da90`

## string_xrefs

- `0x4da9e`: `publishLicenseTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x4da90  ldarg.0
0x4da91  call     instance void System.Security.RightsManagement.UnsignedPublishLicense::.ctor()
0x4da96  call     void MS.Internal.WindowsBase.SecurityHelper::DemandRightsManagementPermission()
0x4da9b  ldarg.1
0x4da9c  brtrue.s loc_4DAA9
0x4da9e  ldstr    aPublishlicense_2// "publishLicenseTemplate"
0x4daa3  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4daa8  throw
0x4daa9  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x4daae  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MaxValue
0x4dab3  ldnull
0x4dab4  ldnull
0x4dab5  ldnull
0x4dab6  ldarg.1
0x4dab7  call     class MS.Internal.Security.RightsManagement.SafeRightsManagementHandle MS.Internal.Security.RightsManagement.SafeRightsManagementHandle::get_InvalidHandle()
0x4dabc  ldarg.0
0x4dabd  ldfld    valuetype [mscorlib]System.Guid System.Security.RightsManagement.UnsignedPublishLicense::_contentId
0x4dac2  ldnull
0x4dac3  ldnull
0x4dac4  ldnull
0x4dac5  ldc.i4.0
0x4dac6  ldnull
0x4dac7  newobj   instance void MS.Internal.Security.RightsManagement.IssuanceLicense::.ctor(valuetype [mscorlib]System.DateTime validFrom, valuetype [mscorlib]System.DateTime validUntil, string referralInfoName, class [System]System.Uri referralInfoUri, class System.Security.RightsManagement.ContentUser owner, string issuanceLicense, class MS.Internal.Security.RightsManagement.SafeRightsManagementHandle boundLicenseHandle, valuetype [mscorlib]System.Guid contentId, class [mscorlib]System.Collections.Generic.ICollection`1<class System.Security.RightsManagement.ContentGrant> grantCollection, class [mscorlib]System.Collections.Generic.IDictionary`2<int32, class System.Security.RightsManagement.LocalizedNameDescriptionPair> localizedNameDescriptionDictionary, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> applicationSpecificDataDictionary, int32 rightValidityIntervalDays, class MS.Internal.Security.RightsManagement.RevocationPoint revocationPoint)
0x4dacc  stloc.0
0x4dacd  ldloc.0
0x4dace  ldarg.0
0x4dacf  callvirt instance void MS.Internal.Security.RightsManagement.IssuanceLicense::UpdateUnsignedPublishLicense(class System.Security.RightsManagement.UnsignedPublishLicense unsignedPublishLicense)
0x4dad4  leave.s  loc_4DAE0
0x4dad6  ldloc.0
0x4dad7  brfalse.s loc_4DADF
0x4dad9  ldloc.0
0x4dada  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4dadf  endfinally
0x4dae0  ret
```
