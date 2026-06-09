# Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::Page_Load

- ea: `0x2e480`
- end: `0x2e564`
- name: `Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::Page_Load`
- size: `228`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x2e2b0`
- `0x2e2f0`
- `0x2e480`
- `0x2e6d0`
- `0x2e810`

## string_xrefs

- `0x2e530`: `;\n                                var jsonValue = JSON.stringify(value);\n                                window.parent.postMessage(jsonValue, window.parent.location);\n                            }\n                        };\n                        postToParent();`

## pseudocode

```c

```

## disassembly

```asm
0x2e480  ldarg.0
0x2e481  call     instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ISubscriptionBaseUIUserControl Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::get_DeliveryProviderCustomControl()
0x2e486  brfalse  loc_2E563
0x2e48b  ldarg.0
0x2e48c  call     instance bool [System.Web]System.Web.UI.Page::get_IsPostBack()
0x2e491  brfalse  loc_2E563
0x2e496  ldarg.0
0x2e497  ldfld    class [System.Web]System.Web.UI.WebControls.HiddenField Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::m_hiddenPostOperation
0x2e49c  callvirt instance string [System.Web]System.Web.UI.WebControls.HiddenField::get_Value()
0x2e4a1  ldstr    aLoad// "Load"
0x2e4a6  ldc.i4.5
0x2e4a7  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x2e4ac  brfalse.s loc_2E4E3
0x2e4ae  ldarg.0
0x2e4af  ldarg.0
0x2e4b0  ldfld    class [System.Web]System.Web.UI.WebControls.HiddenField Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::m_hiddenUserDataJson
0x2e4b5  callvirt instance string [System.Web]System.Web.UI.WebControls.HiddenField::get_Value()
0x2e4ba  ldloca.s 0
0x2e4bc  call     instance bool Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::TryLoadSettingsFromJson(string jsonContent, [out] class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[]& settings)
0x2e4c1  brfalse  loc_2E563
0x2e4c6  ldarg.0
0x2e4c7  call     instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ISubscriptionBaseUIUserControl Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::get_DeliveryProviderCustomControl()
0x2e4cc  ldloc.0
0x2e4cd  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ISubscriptionBaseUIUserControl::set_UserData(class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[])
0x2e4d2  ldarg.0
0x2e4d3  ldfld    class [System.Web]System.Web.UI.WebControls.HiddenField Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::m_hiddenPostOperation
0x2e4d8  ldsfld   string [mscorlib]System.String::Empty
0x2e4dd  callvirt instance void [System.Web]System.Web.UI.WebControls.HiddenField::set_Value(string)
0x2e4e2  ret
0x2e4e3  ldarg.0
0x2e4e4  ldfld    class [System.Web]System.Web.UI.WebControls.HiddenField Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::m_hiddenPostOperation
0x2e4e9  callvirt instance string [System.Web]System.Web.UI.WebControls.HiddenField::get_Value()
0x2e4ee  ldstr    aSave// "Save"
0x2e4f3  ldc.i4.5
0x2e4f4  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x2e4f9  brfalse.s loc_2E563
0x2e4fb  ldstr    aNull_1// "null"
0x2e500  stloc.1
0x2e501  ldarg.0
0x2e502  call     instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ISubscriptionBaseUIUserControl Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::get_DeliveryProviderCustomControl()
0x2e507  callvirt instance bool [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ISubscriptionBaseUIUserControl::Validate()
0x2e50c  brfalse.s loc_2E52A
0x2e50e  ldarg.0
0x2e50f  call     instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ISubscriptionBaseUIUserControl Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::get_DeliveryProviderCustomControl()
0x2e514  callvirt instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ISubscriptionBaseUIUserControl::get_UserData()
0x2e519  stloc.3
0x2e51a  ldloc.3
0x2e51b  brfalse.s loc_2E52A
0x2e51d  ldarg.0
0x2e51e  call     instance string Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::get_DeliveryExtensionName()
0x2e523  ldloc.3
0x2e524  call     string Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::SettingToExtensionSettingsJson(string deliveryExtension, class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] settings)
0x2e529  stloc.1
0x2e52a  ldstr    aFunctionPostto// "\r\n                        function po"...
0x2e52f  ldloc.1
0x2e530  ldstr    aVarJsonvalueJs// ";\r\n                                va"...
0x2e535  call     string [mscorlib]System.String::Concat(string, string, string)
0x2e53a  stloc.2
0x2e53b  ldarg.0
0x2e53c  ldfld    class [System.Web.Extensions]System.Web.UI.UpdatePanel Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::m_updatePanel
0x2e541  ldarg.0
0x2e542  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2e547  ldstr    aScript_0// "script"
0x2e54c  ldloc.2
0x2e54d  ldc.i4.1
0x2e54e  call     void [System.Web.Extensions]System.Web.UI.ScriptManager::RegisterStartupScript(class [System.Web]System.Web.UI.Control, class [mscorlib]System.Type, string, string, bool)
0x2e553  ldarg.0
0x2e554  ldfld    class [System.Web]System.Web.UI.WebControls.HiddenField Microsoft.ReportingServices.WebServer.DeliveryExtensionUI::m_hiddenPostOperation
0x2e559  ldsfld   string [mscorlib]System.String::Empty
0x2e55e  callvirt instance void [System.Web]System.Web.UI.WebControls.HiddenField::set_Value(string)
0x2e563  ret
```
