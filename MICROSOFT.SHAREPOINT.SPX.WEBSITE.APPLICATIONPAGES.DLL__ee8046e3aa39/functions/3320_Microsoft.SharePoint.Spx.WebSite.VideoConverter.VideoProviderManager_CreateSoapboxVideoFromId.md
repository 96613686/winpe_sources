# Microsoft.SharePoint.Spx.WebSite.VideoConverter.VideoProviderManager::CreateSoapboxVideoFromId

- ea: `0x3320`
- end: `0x3355`
- name: `Microsoft.SharePoint.Spx.WebSite.VideoConverter.VideoProviderManager::CreateSoapboxVideoFromId`
- size: `53`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x2a90`
- `0x2c50`
- `0x2d30`
- `0x3320`

## pseudocode

```c

```

## disassembly

```asm
0x3320  call     class Microsoft.SharePoint.Spx.WebSite.VideoConverter.VideoProvider[] Microsoft.SharePoint.Spx.WebSite.VideoConverter.VideoProviderHelper::get_VideoProviders()
0x3325  stloc.0
0x3326  ldloc.0
0x3327  stloc.3
0x3328  ldc.i4.0
0x3329  stloc.s  4
0x332b  br.s     loc_334A
0x332d  ldloc.3
0x332e  ldloc.s  4
0x3330  ldelem.ref
0x3331  stloc.1
0x3332  ldloc.1
0x3333  callvirt instance bool Microsoft.SharePoint.Spx.WebSite.VideoConverter.VideoProvider::get_IsSoapbox()
0x3338  brfalse.s loc_3344
0x333a  ldloc.1
0x333b  ldarg.0
0x333c  callvirt instance class Microsoft.SharePoint.Spx.WebSite.VideoConverter.Video Microsoft.SharePoint.Spx.WebSite.VideoConverter.VideoProvider::VideoFromId(string id)
0x3341  stloc.2
0x3342  leave.s  loc_3353
0x3344  ldloc.s  4
0x3346  ldc.i4.1
0x3347  add
0x3348  stloc.s  4
0x334a  ldloc.s  4
0x334c  ldloc.3
0x334d  ldlen
0x334e  conv.i4
0x334f  blt.s    loc_332D
0x3351  ldnull
0x3352  ret
0x3353  ldloc.2
0x3354  ret
```
