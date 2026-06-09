# System.Windows.Media.MediaPlayerState::OpenMedia

- ea: `0xa0d30`
- end: `0xa0e1f`
- name: `System.Windows.Media.MediaPlayerState::OpenMedia`
- size: `239`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0xa0fc0`

## callees

- `0x2fbb0`
- `0x9f600`
- `0xa0d30`
- `0xa0e40`
- `0xa0e60`
- `0x106440`
- `0x1064b0`
- `0x107700`
- `0x107730`
- `0x107d30`
- `0x145eb0`
- `0x146e70`

## string_xrefs

- `0xa0d69`: `Media_PackURIsAreNotSupported`

## pseudocode

```c

```

## disassembly

```asm
0xa0d30  ldnull
0xa0d31  stloc.2
0xa0d32  ldarg.1
0xa0d33  ldnull
0xa0d34  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0xa0d39  brfalse.s loc_A0D80
0xa0d3b  ldarg.1
0xa0d3c  callvirt instance bool [System]System.Uri::get_IsAbsoluteUri()
0xa0d41  brfalse.s loc_A0D80
0xa0d43  ldarg.1
0xa0d44  callvirt instance string [System]System.Uri::get_Scheme()
0xa0d49  ldsfld   string [WindowsBase]System.IO.Packaging.PackUriHelper::UriSchemePack
0xa0d4e  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa0d53  brfalse.s loc_A0D80
0xa0d55  ldarg.1
0xa0d56  call     class [System]System.Uri System.Windows.Navigation.BaseUriHelper::ConvertPackUriToAbsoluteExternallyVisibleUri(class [System]System.Uri packUri)
0xa0d5b  starg.s  1
0xa0d5d  leave.s  loc_A0D80
0xa0d5f  pop
0xa0d60  ldnull
0xa0d61  starg.s  1
0xa0d63  ldarg.0
0xa0d64  ldfld    class System.Windows.Media.MediaEventsHelper System.Windows.Media.MediaPlayerState::_mediaEventsHelper
0xa0d69  ldstr    aMediaPackurisa// "Media_PackURIsAreNotSupported"
0xa0d6e  ldnull
0xa0d6f  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0xa0d74  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0xa0d79  callvirt instance void System.Windows.Media.MediaEventsHelper::RaiseMediaFailed(class [mscorlib]System.Exception e)
0xa0d7e  leave.s  loc_A0D80
0xa0d80  ldarg.1
0xa0d81  ldnull
0xa0d82  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0xa0d87  brfalse  loc_A0E0B
0xa0d8c  ldc.i4.0
0xa0d8d  stloc.1
0xa0d8e  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0xa0d93  call     class [System]System.Uri MS.Internal.SecurityHelper::GetBaseDirectory(class [mscorlib]System.AppDomain domain)
0xa0d98  stloc.3
0xa0d99  ldarg.0
0xa0d9a  ldarg.1
0xa0d9b  ldloc.3
0xa0d9c  call     instance class [System]System.Uri System.Windows.Media.MediaPlayerState::ResolveUri(class [System]System.Uri uri, class [System]System.Uri appBase)
0xa0da1  stloc.0
0xa0da2  ldloc.0
0xa0da3  callvirt instance string [System]System.Uri::get_Scheme()
0xa0da8  ldsfld   string [System]System.Uri::UriSchemeHttps
0xa0dad  call     bool MS.Internal.SecurityHelper::AreStringTypesEqual(string m1, string m2)
0xa0db2  brfalse.s loc_A0DE4
0xa0db4  call     class [System]System.Uri MS.Internal.SecurityHelper::ExtractUriForClickOnceDeployedApp()
0xa0db9  stloc.s  4
0xa0dbb  ldloc.s  4
0xa0dbd  callvirt instance string [System]System.Uri::get_Scheme()
0xa0dc2  ldsfld   string [System]System.Uri::UriSchemeHttps
0xa0dc7  call     bool MS.Internal.SecurityHelper::AreStringTypesEqual(string m1, string m2)
0xa0dcc  brtrue.s loc_A0DF7
0xa0dce  ldc.i4.s 0x40
0xa0dd0  ldloc.0
0xa0dd1  call     string MS.Internal.PresentationCore.BindUriHelper::UriToString(class [System]System.Uri uri)
0xa0dd6  newobj   instance void [System]System.Net.WebPermission::.ctor(valuetype [System]System.Net.NetworkAccess, string)
0xa0ddb  call     instance void [mscorlib]System.Security.CodeAccessPermission::Assert()
0xa0de0  ldc.i4.1
0xa0de1  stloc.1
0xa0de2  br.s     loc_A0DF7
0xa0de4  ldc.i4.1
0xa0de5  ldloc.3
0xa0de6  callvirt instance string [System]System.Uri::get_LocalPath()
0xa0deb  newobj   instance void [mscorlib]System.Security.Permissions.FileIOPermission::.ctor(valuetype [mscorlib]System.Security.Permissions.FileIOPermissionAccess, string)
0xa0df0  call     instance void [mscorlib]System.Security.CodeAccessPermission::Assert()
0xa0df5  ldc.i4.1
0xa0df6  stloc.1
0xa0df7  nop
0xa0df8  ldarg.0
0xa0df9  ldloc.0
0xa0dfa  call     instance string System.Windows.Media.MediaPlayerState::DemandPermissions(class [System]System.Uri absoluteUri)
0xa0dff  stloc.2
0xa0e00  leave.s  loc_A0E0D
0xa0e02  ldloc.1
0xa0e03  brfalse.s loc_A0E0A
0xa0e05  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0xa0e0a  endfinally
0xa0e0b  ldnull
0xa0e0c  stloc.2
0xa0e0d  ldarg.0
0xa0e0e  ldfld    class System.Windows.Media.SafeMediaHandle System.Windows.Media.MediaPlayerState::_nativeMedia
0xa0e13  ldloc.2
0xa0e14  call     int32 MS.Internal.MILMedia::Open(class System.Windows.Media.SafeMediaHandle THIS_PTR, [in] [hasfieldmarshal] string src)
0xa0e19  call     void MS.Internal.HRESULT::Check(int32 hr)
0xa0e1e  ret
```
