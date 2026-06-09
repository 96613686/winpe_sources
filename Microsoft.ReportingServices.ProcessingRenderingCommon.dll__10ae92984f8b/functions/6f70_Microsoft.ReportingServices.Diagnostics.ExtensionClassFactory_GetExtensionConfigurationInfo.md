# Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::GetExtensionConfigurationInfo

- ea: `0x6f70`
- end: `0x7277`
- name: `Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::GetExtensionConfigurationInfo`
- size: `775`
- prototype: ``
- caller_count: `4`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x68e0`
- `0x6920`
- `0x6940`
- `0x7610`

## callees

- `0x51d0`
- `0x51e0`
- `0x51f0`
- `0x5200`
- `0x5220`
- `0x5230`
- `0x5240`
- `0x5250`
- `0x5260`
- `0x5270`
- `0x5280`
- `0x5290`
- `0x52d0`
- `0x6160`
- `0x6f70`
- `0x10150`
- `0x15740`

## string_xrefs

- `0x7089`: `Security`

## pseudocode

```c

```

## disassembly

```asm
0x6f70  ldnull
0x6f71  stloc.0
0x6f72  call     class Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_Configuration()
0x6f77  brfalse  loc_7275
0x6f7c  call     class Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_Configuration()
0x6f81  callvirt instance class Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration::get_Extensions()
0x6f86  brfalse  loc_7275
0x6f8b  ldarg.1
0x6f8c  brfalse  loc_7275
0x6f91  ldarg.1
0x6f92  call     instance int32 [mscorlib]System.String::get_Length()
0x6f97  stloc.1
0x6f98  ldloc.1
0x6f99  ldc.i4.4
0x6f9a  sub
0x6f9b  switch   loc_701F, loc_7275, loc_70B2, loc_7275, loc_7000, loc_7275, loc_70DC, loc_70F1, loc_7275, loc_705E, loc_70C7, loc_6FE9, loc_7275, loc_7275, loc_7106
0x6fdc  ldloc.1
0x6fdd  ldc.i4.s 0x1D
0x6fdf  beq      loc_711B
0x6fe4  br       loc_7275
0x6fe9  ldarg.1
0x6fea  ldc.i4.0
0x6feb  call     instance char [mscorlib]System.String::get_Chars(int32)
0x6ff0  stloc.2
0x6ff1  ldloc.2
0x6ff2  ldc.i4.s 0x45
0x6ff4  beq.s    loc_7049
0x6ff6  ldloc.2
0x6ff7  ldc.i4.s 0x4D
0x6ff9  beq.s    loc_7034
0x6ffb  br       loc_7275
0x7000  ldarg.1
0x7001  ldc.i4.2
0x7002  call     instance char [mscorlib]System.String::get_Chars(int32)
0x7007  stloc.2
0x7008  ldloc.2
0x7009  ldc.i4.s 0x63
0x700b  beq.s    loc_7088
0x700d  ldloc.2
0x700e  ldc.i4.s 0x6C
0x7010  beq.s    loc_7073
0x7012  ldloc.2
0x7013  ldc.i4.s 0x73
0x7015  beq      loc_709D
0x701a  br       loc_7275
0x701f  ldarg.1
0x7020  ldstr    aData// "Data"
0x7025  call     bool [mscorlib]System.String::op_Equality(string, string)
0x702a  brtrue   loc_7130
0x702f  br       loc_7275
0x7034  ldarg.1
0x7035  ldstr    aModelgeneratio// "ModelGeneration"
0x703a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x703f  brtrue   loc_714B
0x7044  br       loc_7275
0x7049  ldarg.1
0x704a  ldstr    aEventprocessin// "EventProcessing"
0x704f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7054  brtrue   loc_719C
0x7059  br       loc_7275
0x705e  ldarg.1
0x705f  ldstr    aSemanticquery// "SemanticQuery"
0x7064  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7069  brtrue   loc_7166
0x706e  br       loc_7275
0x7073  ldarg.1
0x7074  ldstr    aDelivery// "Delivery"
0x7079  call     bool [mscorlib]System.String::op_Equality(string, string)
0x707e  brtrue   loc_7181
0x7083  br       loc_7275
0x7088  ldarg.1
0x7089  ldstr    aSecurity// "Security"
0x708e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7093  brtrue   loc_71D2
0x7098  br       loc_7275
0x709d  ldarg.1
0x709e  ldstr    aDesigner// "Designer"
0x70a3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x70a8  brtrue   loc_721D
0x70ad  br       loc_7275
0x70b2  ldarg.1
0x70b3  ldstr    aRender// "Render"
0x70b8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x70bd  brtrue   loc_71B7
0x70c2  br       loc_7275
0x70c7  ldarg.1
0x70c8  ldstr    aAuthentication// "Authentication"
0x70cd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x70d2  brtrue   loc_71ED
0x70d7  br       loc_7275
0x70dc  ldarg.1
0x70dd  ldstr    aDeliveryui// "DeliveryUI"
0x70e2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x70e7  brtrue   loc_7205
0x70ec  br       loc_7275
0x70f1  ldarg.1
0x70f2  ldstr    aReportitems// "ReportItems"
0x70f7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x70fc  brtrue   loc_7235
0x7101  br       loc_7275
0x7106  ldarg.1
0x7107  ldstr    aReportitemdesi// "ReportItemDesigner"
0x710c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7111  brtrue   loc_724D
0x7116  br       loc_7275
0x711b  ldarg.1
0x711c  ldstr    aReportdefiniti// "ReportDefinitionCustomization"
0x7121  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7126  brtrue   loc_7265
0x712b  br       loc_7275
0x7130  call     class Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_Configuration()
0x7135  callvirt instance class Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration::get_Extensions()
0x713a  callvirt instance class ExtensionArray Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::get_Data()
0x713f  ldarg.2
0x7140  callvirt instance class Microsoft.ReportingServices.Diagnostics.Extension ExtensionArray::get_Item(string extensionName)
0x7145  stloc.0
0x7146  br       loc_7275
0x714b  call     class Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_Configuration()
0x7150  callvirt instance class Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration::get_Extensions()
0x7155  callvirt instance class ExtensionArray Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::get_ModelGeneration()
0x715a  ldarg.2
0x715b  callvirt instance class Microsoft.ReportingServices.Diagnostics.Extension ExtensionArray::get_Item(string extensionName)
0x7160  stloc.0
0x7161  br       loc_7275
0x7166  call     class Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_Configuration()
0x716b  callvirt instance class Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration::get_Extensions()
0x7170  callvirt instance class ExtensionArray Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::get_SemanticQuery()
0x7175  ldarg.2
0x7176  callvirt instance class Microsoft.ReportingServices.Diagnostics.Extension ExtensionArray::get_Item(string extensionName)
0x717b  stloc.0
0x717c  br       loc_7275
0x7181  call     class Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_Configuration()
0x7186  callvirt instance class Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration::get_Extensions()
0x718b  callvirt instance class ExtensionArray Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::get_Delivery()
0x7190  ldarg.2
0x7191  callvirt instance class Microsoft.ReportingServices.Diagnostics.Extension ExtensionArray::get_Item(string extensionName)
0x7196  stloc.0
0x7197  br       loc_7275
0x719c  call     class Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_Configuration()
0x71a1  callvirt instance class Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration::get_Extensions()
0x71a6  callvirt instance class ExtensionArray Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::get_Event()
0x71ab  ldarg.2
0x71ac  callvirt instance class Microsoft.ReportingServices.Diagnostics.Extension ExtensionArray::get_Item(string extensionName)
0x71b1  stloc.0
0x71b2  br       loc_7275
0x71b7  call     class Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_Configuration()
0x71bc  callvirt instance class Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration::get_Extensions()
0x71c1  callvirt instance class ExtensionArray Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::get_Renderer()
0x71c6  ldarg.2
0x71c7  callvirt instance class Microsoft.ReportingServices.Diagnostics.Extension ExtensionArray::get_Item(string extensionName)
0x71cc  stloc.0
0x71cd  br       loc_7275
0x71d2  call     class Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_Configuration()
0x71d7  callvirt instance class Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration::get_Extensions()
0x71dc  callvirt instance class ExtensionArray Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::get_Security()
0x71e1  ldarg.2
0x71e2  callvirt instance class Microsoft.ReportingServices.Diagnostics.Extension ExtensionArray::get_Item(string extensionName)
0x71e7  stloc.0
0x71e8  br       loc_7275
0x71ed  call     class Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_Configuration()
0x71f2  callvirt instance class Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration::get_Extensions()
0x71f7  callvirt instance class ExtensionArray Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::get_Authentication()
0x71fc  ldarg.2
0x71fd  callvirt instance class Microsoft.ReportingServices.Diagnostics.Extension ExtensionArray::get_Item(string extensionName)
0x7202  stloc.0
0x7203  br.s     loc_7275
0x7205  call     class Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_Configuration()
0x720a  callvirt instance class Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration::get_Extensions()
0x720f  callvirt instance class ExtensionArray Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::get_DeliveryUI()
0x7214  ldarg.2
0x7215  callvirt instance class Microsoft.ReportingServices.Diagnostics.Extension ExtensionArray::get_Item(string extensionName)
0x721a  stloc.0
0x721b  br.s     loc_7275
0x721d  call     class Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_Configuration()
0x7222  callvirt instance class Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration::get_Extensions()
0x7227  callvirt instance class ExtensionArray Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::get_Designer()
0x722c  ldarg.2
0x722d  callvirt instance class Microsoft.ReportingServices.Diagnostics.Extension ExtensionArray::get_Item(string extensionName)
0x7232  stloc.0
0x7233  br.s     loc_7275
0x7235  call     class Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_Configuration()
0x723a  callvirt instance class Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration::get_Extensions()
0x723f  callvirt instance class ExtensionArray Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::get_ReportItems()
0x7244  ldarg.2
0x7245  callvirt instance class Microsoft.ReportingServices.Diagnostics.Extension ExtensionArray::get_Item(string extensionName)
0x724a  stloc.0
0x724b  br.s     loc_7275
0x724d  call     class Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_Configuration()
0x7252  callvirt instance class Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration::get_Extensions()
0x7257  callvirt instance class ExtensionArray Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::get_ReportItemDesigner()
0x725c  ldarg.2
0x725d  callvirt instance class Microsoft.ReportingServices.Diagnostics.Extension ExtensionArray::get_Item(string extensionName)
0x7262  stloc.0
0x7263  br.s     loc_7275
0x7265  call     class Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_Configuration()
0x726a  callvirt instance class Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration::get_Extensions()
0x726f  callvirt instance class Microsoft.ReportingServices.Diagnostics.Extension Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration::get_ReportDefinitionCustomization()
0x7274  stloc.0
0x7275  ldloc.0
0x7276  ret
```
