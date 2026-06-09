# System.Web.UI.ProfileServiceManager::GenerateInitializationScript

- ea: `0x12170`
- end: `0x122cc`
- name: `System.Web.UI.ProfileServiceManager::GenerateInitializationScript`
- size: `348`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x120a0`

## callees

- `0x12170`
- `0x12310`
- `0x123c0`
- `0x2a6d0`
- `0x39140`

## string_xrefs

- `0x1219c`: `~/Profile_JSON_AppService.axd`
- `0x121db`: `~/Profile_JSON_AppService.axd`
- `0x121a9`: `Sys.Services._ProfileService.DefaultWebServicePath = '`
- `0x12210`: `Sys.Services.ProfileService.set_path('`

## pseudocode

```c

```

## disassembly

```asm
0x12170  ldnull
0x12171  stloc.0
0x12172  ldarg.s  4
0x12174  brfalse.s loc_12182
0x12176  ldarg.s  4
0x12178  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x1217d  ldc.i4.0
0x1217e  cgt
0x12180  br.s     loc_12183
0x12182  ldc.i4.0
0x12183  stloc.1
0x12184  call     bool System.Web.ApplicationServices.ApplicationServiceHelper::get_ProfileServiceEnabled()
0x12189  brfalse.s loc_121CF
0x1218b  ldarg.0
0x1218c  ldind.ref
0x1218d  brtrue.s loc_1219B
0x1218f  ldarg.0
0x12190  ldc.i4   0x80
0x12195  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x1219a  stind.ref
0x1219b  ldarg.2
0x1219c  ldstr    aProfileJsonApp// "~/Profile_JSON_AppService.axd"
0x121a1  callvirt instance string [System.Web]System.Web.UI.Control::ResolveClientUrl(string)
0x121a6  stloc.0
0x121a7  ldarg.0
0x121a8  ldind.ref
0x121a9  ldstr    aSysServicesPro// "Sys.Services._ProfileService.DefaultWeb"...
0x121ae  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x121b3  pop
0x121b4  ldarg.0
0x121b5  ldind.ref
0x121b6  ldloc.0
0x121b7  call     string [System.Web]System.Web.HttpUtility::JavaScriptStringEncode(string)
0x121bc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x121c1  pop
0x121c2  ldarg.0
0x121c3  ldind.ref
0x121c4  ldstr    asc_3FB16// "';\n"
0x121c9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x121ce  pop
0x121cf  ldarg.3
0x121d0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x121d5  brtrue.s loc_12236
0x121d7  ldloc.0
0x121d8  brtrue.s loc_121E6
0x121da  ldarg.2
0x121db  ldstr    aProfileJsonApp// "~/Profile_JSON_AppService.axd"
0x121e0  callvirt instance string [System.Web]System.Web.UI.Control::ResolveClientUrl(string)
0x121e5  stloc.0
0x121e6  ldloc.1
0x121e7  brfalse.s loc_121FE
0x121e9  ldarg.3
0x121ea  ldloc.0
0x121eb  ldc.i4.5
0x121ec  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x121f1  brtrue.s loc_121FE
0x121f3  call     string System.Web.Resources.AtlasWeb::get_ProfileServiceManager_LoadProperitesWithNonDefaultPath()
0x121f8  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x121fd  throw
0x121fe  ldarg.0
0x121ff  ldind.ref
0x12200  brtrue.s loc_1220E
0x12202  ldarg.0
0x12203  ldc.i4   0x80
0x12208  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x1220d  stind.ref
0x1220e  ldarg.0
0x1220f  ldind.ref
0x12210  ldstr    aSysServicesPro_0// "Sys.Services.ProfileService.set_path('"
0x12215  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1221a  pop
0x1221b  ldarg.0
0x1221c  ldind.ref
0x1221d  ldarg.3
0x1221e  call     string [System.Web]System.Web.HttpUtility::JavaScriptStringEncode(string)
0x12223  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12228  pop
0x12229  ldarg.0
0x1222a  ldind.ref
0x1222b  ldstr    asc_3FB7A// "');\n"
0x12230  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12235  pop
0x12236  ldloc.1
0x12237  brfalse  loc_122CB
0x1223c  ldarg.0
0x1223d  ldind.ref
0x1223e  brtrue.s loc_1224C
0x12240  ldarg.0
0x12241  ldc.i4   0x80
0x12246  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x1224b  stind.ref
0x1224c  ldarg.2
0x1224d  callvirt instance bool [System.Web]System.Web.UI.Control::get_DesignMode()
0x12252  brfalse.s loc_12262
0x12254  ldarg.0
0x12255  ldind.ref
0x12256  ldstr    aLoadproperties// "// loadProperties\n"
0x1225b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x12260  pop
0x12261  ret
0x12262  ldarg.1
0x12263  brfalse.s loc_122CB
0x12265  ldarg.s  4
0x12267  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x1226c  newobj   instance void class [System]System.Collections.Generic.SortedList`2<string, object>::.ctor(int32)
0x12271  stloc.2
0x12272  ldnull
0x12273  stloc.3
0x12274  ldarg.1
0x12275  callvirt instance class [System.Web]System.Web.Profile.ProfileBase [System.Web]System.Web.HttpContext::get_Profile()
0x1227a  stloc.s  4
0x1227c  ldarg.s  4
0x1227e  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x12283  stloc.s  5
0x12285  br.s     loc_122A2
0x12287  ldloc.s  5
0x12289  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1228e  castclass [mscorlib]System.String
0x12293  stloc.s  6
0x12295  ldloc.s  4
0x12297  ldloc.s  6
0x12299  ldloc.2
0x1229a  ldloca.s 3
0x1229c  ldc.i4.1
0x1229d  call     void System.Web.UI.ProfileServiceManager::GetSettingsProperty(class [System.Web]System.Web.Profile.ProfileBase profile, string fullPropertyName, class [System]System.Collections.Generic.SortedList`2<string, object> topLevelSettings, class [System]System.Collections.Generic.SortedList`2<string, class [System]System.Collections.Generic.SortedList`2<string, object>>& profileGroups, bool ensureExists)
0x122a2  ldloc.s  5
0x122a4  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x122a9  brtrue.s loc_12287
0x122ab  leave.s  loc_122C2
0x122ad  ldloc.s  5
0x122af  isinst   [mscorlib]System.IDisposable
0x122b4  stloc.s  7
0x122b6  ldloc.s  7
0x122b8  brfalse.s loc_122C1
0x122ba  ldloc.s  7
0x122bc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x122c1  endfinally
0x122c2  ldarg.0
0x122c3  ldind.ref
0x122c4  ldloc.2
0x122c5  ldloc.3
0x122c6  call     void System.Web.UI.ProfileServiceManager::RenderProfileProperties(class [mscorlib]System.Text.StringBuilder sb, class [System]System.Collections.Generic.SortedList`2<string, object> topLevelSettings, class [System]System.Collections.Generic.SortedList`2<string, class [System]System.Collections.Generic.SortedList`2<string, object>> profileGroups)
0x122cb  ret
```
