# System.Web.UI.Page::InitOutputCache_1

- ea: `0x74750`
- end: `0x74ce9`
- name: `System.Web.UI.Page::InitOutputCache_1`
- size: `1433`
- prototype: ``
- caller_count: `2`
- callee_count: `56`
- tags: `registry_config`

## callers

- `0x74700`
- `0x17a9a0`

## callees

- `0x12af0`
- `0x12b80`
- `0x14200`
- `0x14230`
- `0x14310`
- `0x14320`
- `0x14330`
- `0x14340`
- `0x14410`
- `0x14440`
- `0x144b0`
- `0x145d0`
- `0x146e0`
- `0x14be0`
- `0x14d90`
- `0x16a00`
- `0x18990`
- `0x1ed30`
- `0x1fbf0`
- `0x34f20`
- `0x34fa0`
- `0x58d50`
- `0x5ef80`
- `0x71030`
- `0x71070`
- `0x710a0`
- `0x710d0`
- `0x71100`
- `0x71130`
- `0x71160`
- `0x71190`
- `0x711c0`
- `0x711f0`
- `0x71220`
- `0x721b0`
- `0x74750`
- `0x77070`
- `0x87b40`
- `0x87b50`
- `0x14eb30`
- `0x14eb70`
- `0x14ebb0`
- `0x14ebf0`
- `0x14ec20`
- `0x14ec50`
- `0x14ec80`
- `0x14ecb0`
- `0x14ece0`
- `0x14ed10`
- `0x14eda0`

## string_xrefs

- `0x747ce`: `CacheProfile_Not_Found`
- `0x7497e`: `Missing_output_cache_attr`
- `0x749c6`: `Missing_output_cache_attr`
- `0x74a37`: `cacheSettings`
- `0x74a3c`: `Invalid_cache_settings_location`

## pseudocode

```c

```

## disassembly

```asm
0x74750  ldarg.0
0x74751  ldfld    bool System.Web.UI.Page::_isCrossPagePostBack
0x74756  brfalse.s loc_74759
0x74758  ret
0x74759  ldnull
0x7475a  stloc.1
0x7475b  ldarg.0
0x7475c  call     instance class System.Web.HttpResponse System.Web.UI.Page::get_Response()
0x74761  callvirt instance class System.Web.HttpCachePolicy System.Web.HttpResponse::get_Cache()
0x74766  stloc.2
0x74767  ldc.i4.m1
0x74768  stloc.s  4
0x7476a  ldc.i4.0
0x7476b  stloc.s  5
0x7476d  ldnull
0x7476e  stloc.s  6
0x74770  ldnull
0x74771  stloc.s  7
0x74773  ldnull
0x74774  stloc.s  8
0x74776  ldnull
0x74777  stloc.s  9
0x74779  ldnull
0x7477a  stloc.s  0xA
0x7477c  ldnull
0x7477d  stloc.s  0xB
0x7477f  ldc.i4.0
0x74780  stloc.s  0xC
0x74782  call     class System.Web.Configuration.RuntimeConfig System.Web.Configuration.RuntimeConfig::GetAppConfig()
0x74787  stloc.s  0xD
0x74789  ldloc.s  0xD
0x7478b  callvirt instance class System.Web.Configuration.OutputCacheSection System.Web.Configuration.RuntimeConfig::get_OutputCache()
0x74790  stloc.s  0xE
0x74792  ldloc.s  0xE
0x74794  callvirt instance bool System.Web.Configuration.OutputCacheSection::get_EnableOutputCache()
0x74799  brtrue.s loc_7479C
0x7479b  ret
0x7479c  ldarg.1
0x7479d  callvirt instance string System.Web.UI.OutputCacheParameters::get_CacheProfile()
0x747a2  brfalse.s loc_747F6
0x747a4  ldarg.1
0x747a5  callvirt instance string System.Web.UI.OutputCacheParameters::get_CacheProfile()
0x747aa  callvirt instance int32 [mscorlib]System.String::get_Length()
0x747af  brfalse.s loc_747F6
0x747b1  ldloc.s  0xD
0x747b3  callvirt instance class System.Web.Configuration.OutputCacheSettingsSection System.Web.Configuration.RuntimeConfig::get_OutputCacheSettings()
0x747b8  stloc.0
0x747b9  ldloc.0
0x747ba  callvirt instance class System.Web.Configuration.OutputCacheProfileCollection System.Web.Configuration.OutputCacheSettingsSection::get_OutputCacheProfiles()
0x747bf  ldarg.1
0x747c0  callvirt instance string System.Web.UI.OutputCacheParameters::get_CacheProfile()
0x747c5  callvirt instance class System.Web.Configuration.OutputCacheProfile System.Web.Configuration.OutputCacheProfileCollection::get_Item(string name)
0x747ca  stloc.1
0x747cb  ldloc.1
0x747cc  brtrue.s loc_747ED
0x747ce  ldstr    aCacheprofileNo// "CacheProfile_Not_Found"
0x747d3  ldc.i4.1
0x747d4  newarr   [mscorlib]System.Object
0x747d9  dup
0x747da  ldc.i4.0
0x747db  ldarg.1
0x747dc  callvirt instance string System.Web.UI.OutputCacheParameters::get_CacheProfile()
0x747e1  stelem.ref
0x747e2  call     string System.Web.SR::GetString(string name, object[] args)
0x747e7  newobj   instance void System.Web.HttpException::.ctor(string message)
0x747ec  throw
0x747ed  ldloc.1
0x747ee  callvirt instance bool System.Web.Configuration.OutputCacheProfile::get_Enabled()
0x747f3  brtrue.s loc_747F6
0x747f5  ret
0x747f6  ldloc.1
0x747f7  brfalse  loc_748A2
0x747fc  ldloc.1
0x747fd  callvirt instance int32 System.Web.Configuration.OutputCacheProfile::get_Duration()
0x74802  stloc.s  5
0x74804  ldloc.1
0x74805  callvirt instance string System.Web.Configuration.OutputCacheProfile::get_VaryByContentEncoding()
0x7480a  stloc.s  6
0x7480c  ldloc.1
0x7480d  callvirt instance string System.Web.Configuration.OutputCacheProfile::get_VaryByHeader()
0x74812  stloc.s  7
0x74814  ldloc.1
0x74815  callvirt instance string System.Web.Configuration.OutputCacheProfile::get_VaryByCustom()
0x7481a  stloc.s  8
0x7481c  ldloc.1
0x7481d  callvirt instance string System.Web.Configuration.OutputCacheProfile::get_VaryByParam()
0x74822  stloc.s  9
0x74824  ldloc.1
0x74825  callvirt instance string System.Web.Configuration.OutputCacheProfile::get_SqlDependency()
0x7482a  stloc.s  0xA
0x7482c  ldloc.1
0x7482d  callvirt instance bool System.Web.Configuration.OutputCacheProfile::get_NoStore()
0x74832  stloc.s  0xC
0x74834  ldloc.1
0x74835  callvirt instance string System.Web.Configuration.OutputCacheProfile::get_VaryByControl()
0x7483a  stloc.s  0xB
0x7483c  ldloc.1
0x7483d  callvirt instance valuetype System.Web.UI.OutputCacheLocation System.Web.Configuration.OutputCacheProfile::get_Location()
0x74842  stloc.s  4
0x74844  ldloc.s  6
0x74846  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7484b  brfalse.s loc_74850
0x7484d  ldnull
0x7484e  stloc.s  6
0x74850  ldloc.s  7
0x74852  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x74857  brfalse.s loc_7485C
0x74859  ldnull
0x7485a  stloc.s  7
0x7485c  ldloc.s  8
0x7485e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x74863  brfalse.s loc_74868
0x74865  ldnull
0x74866  stloc.s  8
0x74868  ldloc.s  9
0x7486a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7486f  brfalse.s loc_74874
0x74871  ldnull
0x74872  stloc.s  9
0x74874  ldloc.s  0xB
0x74876  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7487b  brfalse.s loc_74880
0x7487d  ldnull
0x7487e  stloc.s  0xB
0x74880  ldloc.s  9
0x74882  ldstr    aNone// "none"
0x74887  call     bool System.Web.Util.StringUtil::EqualsIgnoreCase(string s1, string s2)
0x7488c  brfalse.s loc_74891
0x7488e  ldnull
0x7488f  stloc.s  9
0x74891  ldloc.s  0xB
0x74893  ldstr    aNone// "none"
0x74898  call     bool System.Web.Util.StringUtil::EqualsIgnoreCase(string s1, string s2)
0x7489d  brfalse.s loc_748A2
0x7489f  ldnull
0x748a0  stloc.s  0xB
0x748a2  ldarg.1
0x748a3  ldc.i4.2
0x748a4  callvirt instance bool System.Web.UI.OutputCacheParameters::IsParameterSet(valuetype System.Web.UI.OutputCacheParameter value)
0x748a9  brfalse.s loc_748B3
0x748ab  ldarg.1
0x748ac  callvirt instance int32 System.Web.UI.OutputCacheParameters::get_Duration()
0x748b1  stloc.s  5
0x748b3  ldarg.1
0x748b4  ldc.i4   0x400
0x748b9  callvirt instance bool System.Web.UI.OutputCacheParameters::IsParameterSet(valuetype System.Web.UI.OutputCacheParameter value)
0x748be  brfalse.s loc_748C8
0x748c0  ldarg.1
0x748c1  callvirt instance string System.Web.UI.OutputCacheParameters::get_VaryByContentEncoding()
0x748c6  stloc.s  6
0x748c8  ldarg.1
0x748c9  ldc.i4   0x100
0x748ce  callvirt instance bool System.Web.UI.OutputCacheParameters::IsParameterSet(valuetype System.Web.UI.OutputCacheParameter value)
0x748d3  brfalse.s loc_748DD
0x748d5  ldarg.1
0x748d6  callvirt instance string System.Web.UI.OutputCacheParameters::get_VaryByHeader()
0x748db  stloc.s  7
0x748dd  ldarg.1
0x748de  ldc.i4   0x80
0x748e3  callvirt instance bool System.Web.UI.OutputCacheParameters::IsParameterSet(valuetype System.Web.UI.OutputCacheParameter value)
0x748e8  brfalse.s loc_748F2
0x748ea  ldarg.1
0x748eb  callvirt instance string System.Web.UI.OutputCacheParameters::get_VaryByCustom()
0x748f0  stloc.s  8
0x748f2  ldarg.1
0x748f3  ldc.i4.s 0x40
0x748f5  callvirt instance bool System.Web.UI.OutputCacheParameters::IsParameterSet(valuetype System.Web.UI.OutputCacheParameter value)
0x748fa  brfalse.s loc_74904
0x748fc  ldarg.1
0x748fd  callvirt instance string System.Web.UI.OutputCacheParameters::get_VaryByControl()
0x74902  stloc.s  0xB
0x74904  ldarg.1
0x74905  ldc.i4   0x200
0x7490a  callvirt instance bool System.Web.UI.OutputCacheParameters::IsParameterSet(valuetype System.Web.UI.OutputCacheParameter value)
0x7490f  brfalse.s loc_74919
0x74911  ldarg.1
0x74912  callvirt instance string System.Web.UI.OutputCacheParameters::get_VaryByParam()
0x74917  stloc.s  9
0x74919  ldarg.1
0x7491a  ldc.i4.s 0x20
0x7491c  callvirt instance bool System.Web.UI.OutputCacheParameters::IsParameterSet(valuetype System.Web.UI.OutputCacheParameter value)
0x74921  brfalse.s loc_7492B
0x74923  ldarg.1
0x74924  callvirt instance string System.Web.UI.OutputCacheParameters::get_SqlDependency()
0x74929  stloc.s  0xA
0x7492b  ldarg.1
0x7492c  ldc.i4.s 0x10
0x7492e  callvirt instance bool System.Web.UI.OutputCacheParameters::IsParameterSet(valuetype System.Web.UI.OutputCacheParameter value)
0x74933  brfalse.s loc_7493D
0x74935  ldarg.1
0x74936  callvirt instance bool System.Web.UI.OutputCacheParameters::get_NoStore()
0x7493b  stloc.s  0xC
0x7493d  ldarg.1
0x7493e  ldc.i4.8
0x7493f  callvirt instance bool System.Web.UI.OutputCacheParameters::IsParameterSet(valuetype System.Web.UI.OutputCacheParameter value)
0x74944  brfalse.s loc_7494E
0x74946  ldarg.1
0x74947  callvirt instance valuetype System.Web.UI.OutputCacheLocation System.Web.UI.OutputCacheParameters::get_Location()
0x7494c  stloc.s  4
0x7494e  ldloc.s  4
0x74950  ldc.i4.m1
0x74951  bne.un.s loc_74956
0x74953  ldc.i4.0
0x74954  stloc.s  4
0x74956  ldloc.s  4
0x74958  ldc.i4.4
0x74959  beq      loc_749E4
0x7495e  ldloc.1
0x7495f  brfalse.s loc_74969
0x74961  ldloc.1
0x74962  callvirt instance bool System.Web.Configuration.OutputCacheProfile::get_Enabled()
0x74967  brfalse.s loc_749E4
0x74969  ldloc.1
0x7496a  brfalse.s loc_74975
0x7496c  ldloc.1
0x7496d  callvirt instance int32 System.Web.Configuration.OutputCacheProfile::get_Duration()
0x74972  ldc.i4.m1
0x74973  bne.un.s loc_7499C
0x74975  ldarg.1
0x74976  ldc.i4.2
0x74977  callvirt instance bool System.Web.UI.OutputCacheParameters::IsParameterSet(valuetype System.Web.UI.OutputCacheParameter value)
0x7497c  brtrue.s loc_7499C
0x7497e  ldstr    aMissingOutputC// "Missing_output_cache_attr"
0x74983  ldc.i4.1
0x74984  newarr   [mscorlib]System.Object
0x74989  dup
0x7498a  ldc.i4.0
0x7498b  ldstr    aDuration_0// "duration"
0x74990  stelem.ref
0x74991  call     string System.Web.SR::GetString(string name, object[] args)
0x74996  newobj   instance void System.Web.HttpException::.ctor(string message)
0x7499b  throw
0x7499c  ldloc.1
0x7499d  brfalse.s loc_749AF
0x7499f  ldloc.1
0x749a0  callvirt instance string System.Web.Configuration.OutputCacheProfile::get_VaryByParam()
0x749a5  brtrue.s loc_749E4
0x749a7  ldloc.1
0x749a8  callvirt instance string System.Web.Configuration.OutputCacheProfile::get_VaryByControl()
0x749ad  brtrue.s loc_749E4
0x749af  ldarg.1
0x749b0  ldc.i4   0x200
0x749b5  callvirt instance bool System.Web.UI.OutputCacheParameters::IsParameterSet(valuetype System.Web.UI.OutputCacheParameter value)
0x749ba  brtrue.s loc_749E4
0x749bc  ldarg.1
0x749bd  ldc.i4.s 0x40
0x749bf  callvirt instance bool System.Web.UI.OutputCacheParameters::IsParameterSet(valuetype System.Web.UI.OutputCacheParameter value)
0x749c4  brtrue.s loc_749E4
0x749c6  ldstr    aMissingOutputC// "Missing_output_cache_attr"
0x749cb  ldc.i4.1
0x749cc  newarr   [mscorlib]System.Object
0x749d1  dup
0x749d2  ldc.i4.0
0x749d3  ldstr    aVarybyparam// "varyByParam"
0x749d8  stelem.ref
0x749d9  call     string System.Web.SR::GetString(string name, object[] args)
0x749de  newobj   instance void System.Web.HttpException::.ctor(string message)
0x749e3  throw
0x749e4  ldloc.s  0xC
0x749e6  brfalse.s loc_749F8
0x749e8  ldarg.0
0x749e9  call     instance class System.Web.HttpResponse System.Web.UI.Page::get_Response()
0x749ee  callvirt instance class System.Web.HttpCachePolicy System.Web.HttpResponse::get_Cache()
0x749f3  callvirt instance void System.Web.HttpCachePolicy::SetNoStore()
0x749f8  ldloc.s  4
0x749fa  switch   loc_74A19, loc_74A25, loc_74A29, loc_74A1D, loc_74A33, loc_74A21
0x74a17  br.s     loc_74A37
0x74a19  ldc.i4.4
0x74a1a  stloc.3
0x74a1b  br.s     loc_74A4C
0x74a1d  ldc.i4.3
0x74a1e  stloc.3
0x74a1f  br.s     loc_74A4C
0x74a21  ldc.i4.5
0x74a22  stloc.3
0x74a23  br.s     loc_74A4C
0x74a25  ldc.i4.2
0x74a26  stloc.3
0x74a27  br.s     loc_74A4C
0x74a29  ldc.i4.4
0x74a2a  stloc.3
0x74a2b  ldloc.2
0x74a2c  callvirt instance void System.Web.HttpCachePolicy::SetNoServerCaching()
0x74a31  br.s     loc_74A4C
0x74a33  ldc.i4.1
0x74a34  stloc.3
0x74a35  br.s     loc_74A4C
0x74a37  ldstr    aCachesettings// "cacheSettings"
0x74a3c  ldstr    aInvalidCacheSe// "Invalid_cache_settings_location"
0x74a41  call     string System.Web.SR::GetString(string name)
0x74a46  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string, string)
0x74a4b  throw
0x74a4c  ldloc.2
0x74a4d  ldloc.3
0x74a4e  callvirt instance void System.Web.HttpCachePolicy::SetCacheability(valuetype System.Web.HttpCacheability cacheability)
0x74a53  ldloc.s  4
0x74a55  ldc.i4.4
0x74a56  beq      loc_74CE8
0x74a5b  ldloc.2
0x74a5c  ldarg.0
  ... truncated ...
```
