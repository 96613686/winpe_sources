# Microsoft.ReportingServices.Portal.Services.SystemResources.UniversalBrandProcessor::Process

- ea: `0xbf70`
- end: `0xc075`
- name: `Microsoft.ReportingServices.Portal.Services.SystemResources.UniversalBrandProcessor::Process`
- size: `261`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0xa8e0`
- `0xbf20`
- `0xbf70`
- `0xc0e0`
- `0xc120`
- `0xd4c0`

## pseudocode

```c

```

## disassembly

```asm
0xbf70  ldarg.1
0xbf71  callvirt instance string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResource::get_TypeName()
0xbf76  call     valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.SystemResourceType Microsoft.ReportingServices.Portal.Services.SystemResources.SystemResourceService::GetSystemResourceType(string typeName)
0xbf7b  ldc.i4.3
0xbf7c  beq.s    loc_BF7F
0xbf7e  ret
0xbf7f  ldarg.0
0xbf80  ldarg.1
0xbf81  call     instance bool Microsoft.ReportingServices.Portal.Services.SystemResources.UniversalBrandProcessor::IsProcessed(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResource resource)
0xbf86  brfalse.s loc_BFAD
0xbf88  ldarg.1
0xbf89  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResource::get_Items()
0xbf8e  ldstr    aStylesheet// "stylesheet"
0xbf93  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xbf98  stloc.s  6
0xbf9a  ldloca.s 6
0xbf9c  constrained. [mscorlib]System.Guid
0xbfa2  callvirt instance string [mscorlib]System.Object::ToString()
0xbfa7  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xbfac  ret
0xbfad  ldnull
0xbfae  stloc.0
0xbfaf  ldarg.2
0xbfb0  ldstr    aColors// "colors"
0xbfb5  ldloca.s 0
0xbfb7  call     bool Microsoft.ReportingServices.Portal.Services.SystemResources.UniversalBrandProcessor::TryLoadFile(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ISystemResourceManager> resourceManagers, string itemName, [out] unsigned int8[]& bytes)
0xbfbc  brtrue.s loc_BFBF
0xbfbe  ret
0xbfbf  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0xbfc4  ldloc.0
0xbfc5  callvirt instance string [mscorlib]System.Text.Encoding::GetString(unsigned int8[])
0xbfca  stloc.1
0xbfcb  ldloc.1
0xbfcc  call     string Microsoft.ReportingServices.Portal.Services.SystemResources.UniversalBrandProcessor::ConvertColorsToLess(string colorsFileJson)
0xbfd1  stloc.2
0xbfd2  leave.s  loc_BFE0
0xbfd4  pop
0xbfd5  call     string Microsoft.ReportingServices.Portal.Services.SR::get_Error_UniversalBrandInvalidColorsFile()
0xbfda  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Exceptions.SystemResourceProcessingException::.ctor(string)
0xbfdf  throw
0xbfe0  ldarg.0
0xbfe1  ldfld    string Microsoft.ReportingServices.Portal.Services.SystemResources.UniversalBrandProcessor::_lessTemplate
0xbfe6  ldstr    aInterfaceColor// "/* interface:colors */"
0xbfeb  ldloc.2
0xbfec  callvirt instance string [mscorlib]System.String::Replace(string, string)
0xbff1  stloc.3
0xbff2  ldarg.1
0xbff3  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResource::get_Items()
0xbff8  ldstr    aLogo// "logo"
0xbffd  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::ContainsKey(var<u1>)
0xc002  brfalse.s loc_C015
0xc004  ldloc.3
0xc005  ldstr    aShowlogoFalse// "@showLogo:false;"
0xc00a  ldstr    aShowlogoTrue// "@showLogo:true;"
0xc00f  callvirt instance string [mscorlib]System.String::Replace(string, string)
0xc014  stloc.3
0xc015  newobj   instance void [dotless.Core]dotless.Core.configuration.DotlessConfiguration::.ctor()
0xc01a  dup
0xc01b  ldc.i4.1
0xc01c  callvirt instance void [dotless.Core]dotless.Core.configuration.DotlessConfiguration::set_MinifyOutput(bool)
0xc021  stloc.s  4
0xc023  ldloc.3
0xc024  ldloc.s  4
0xc026  call     string [dotless.Core]dotless.Core.Less::Parse(string, class [dotless.Core]dotless.Core.configuration.DotlessConfiguration)
0xc02b  stloc.s  5
0xc02d  ldarg.0
0xc02e  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0xc033  ldloc.s  5
0xc035  callvirt instance unsigned int8[] [mscorlib]System.Text.Encoding::GetBytes(string)
0xc03a  stfld    unsigned int8[] Microsoft.ReportingServices.Portal.Services.SystemResources.UniversalBrandProcessor::_processedStylesheet
0xc03f  ldarg.0
0xc040  ldarg.1
0xc041  callvirt instance valuetype [mscorlib]System.Guid [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResource::get_Id()
0xc046  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0xc04b  stfld    valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.ReportingServices.Portal.Services.SystemResources.UniversalBrandProcessor::_processedResourceId
0xc050  ldarg.1
0xc051  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResource::get_Items()
0xc056  ldstr    aStylesheet// "stylesheet"
0xc05b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xc060  stloc.s  6
0xc062  ldloca.s 6
0xc064  constrained. [mscorlib]System.Guid
0xc06a  callvirt instance string [mscorlib]System.Object::ToString()
0xc06f  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xc074  ret
```
