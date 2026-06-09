# Microsoft.SharePoint.WebControls.TemplatePicker::RegisterClientCallBackCode

- ea: `0x3fd920`
- end: `0x3fdb6d`
- name: `Microsoft.SharePoint.WebControls.TemplatePicker::RegisterClientCallBackCode`
- size: `589`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x3fcd90`

## callees

- `0x3fc8a0`
- `0x3fcb70`
- `0x3fd920`
- `0x807b80`

## string_xrefs

- `0x3fda34`: `GetWebTemplates`
- `0x3fd93b`: `var compatddl=document.getElementById('`
- `0x3fd959`: `InvalidDdSiteCompatibilityLevelId`
- `0x3fdab1`: `InvalidDdSiteCompatibilityLevelId`
- `0x3fd962`: `'); if (compatddl != null) {GetWebTemplates(this.options[this.selectedIndex].value +'&'+ compatddl.options[compatddl.selectedIndex].value +'&', 'context');} else {GetWebTemplates(this.options[this.selectedIndex].value +'&'+`
- `0x3fd9c7`: `'); if (langddl != null) {GetWebTemplates(langddl.options[langddl.selectedIndex].value + '&' + this.options[this.selectedIndex].value +'&', 'context');} else {GetWebTemplates(`
- `0x3fd9f8`: `lcidcompatvalue`
- `0x3fda13`: `function GetWebTemplates(lcidcompatvalue, context){`
- `0x3fda63`: `");\n                var numchilds = tabsdiv.childNodes.length;\n                for (var i = 0; i< numchilds; i++) {\n                    tabsdiv.removeChild(tabsdiv.childNodes[0]);\n                }\n\n                var tabsandtemplates = result.split('=');\n                var langddl = document.getElementById("`
- `0x3fda7b`: `");  \n\n                if (langddl != null)\n                {\n                    var numlangchilds = langddl.childNodes.length;\n                    for (var i = 0; i< numlangchilds; i++)\n                    {\n                        langddl.removeChild(langddl.childNodes[0]);\n                    }\n\n                    var langrows = tabsandtemplates[0].split('?'); \n                    for (var i = 0; i < (langrows.length -1 ); ++i)\n                    {\n               `
- `0x3fda93`: `");  \n                    var lcid = "";\n                    if (langddl != null)\n                        lcid = langddl.options[langddl.selectedIndex].value;\n                    var compatddl = document.getElementById("`
- `0x3fdaba`: `");  \n                    var compatLevel = "`
- `0x3fdad4`: `";\n                    if (compatddl != null)\n                        compatLevel = compatddl.options[compatddl.selectedIndex].value;\n                    tab.id = "tabid" + i;\n                    tab.href="javascript:GetWebTemplates('"+lcid+"&"+compatLevel+"&"+escapeProperly(STSScriptEncode(unescapeProperly(value)))+"', 'context') ";                   \n                    var textname = document.createTextNode(unescapeProperly(value));\n                    tab.appendChild(textname);\`
- `0x3fdb08`: `").value = unescapeProperly(value);\n                           selectedTab = i;\n                       }\n                    }\n                    else\n                    {\n                       outerdiv.className="ms-templatepickerunselected";\n                    }\n                    innerdiv.appendChild(tab);\n                    outerdiv.appendChild(innerdiv);\n                    tabsdiv.appendChild(outerdiv);\n                }\n\n                if(selectedTab != -1`
- `0x3fdb22`: `");\n                if(!templateListBox)\n                    return;\n                templateListBox.length = 0;\n                var rows = tabsandtemplates[2].split('?'); \n                for (var i = 0; i < (rows.length -1 ); ++i)\n                {\n                    var values = rows[i].split('#;#');\n                    var option = document.createElement("OPTION");\n                    option.value = unescapeProperly(values[0]);\n                    var textname = document`
- `0x3fdb4b`: `\n            // <![CDATA[\n            function ClientCallbackError(result, clientsideString)\n            { \n                alert(result); \n            }\n            // ]]>\n`

## pseudocode

```c

```

## disassembly

```asm
0x3fd920  ldarg.0
0x3fd921  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlSelect Microsoft.SharePoint.WebControls.TemplatePicker::DdLanguageWebTemplate
0x3fd926  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x3fd92b  ldstr    aOnchange// "onchange"
0x3fd930  ldc.i4.5
0x3fd931  newarr   [mscorlib]System.Object
0x3fd936  stloc.s  4
0x3fd938  ldloc.s  4
0x3fd93a  ldc.i4.0
0x3fd93b  ldstr    aVarCompatddlDo// "var compatddl=document.getElementById('"
0x3fd940  stelem.ref
0x3fd941  ldloc.s  4
0x3fd943  ldc.i4.1
0x3fd944  ldarg.0
0x3fd945  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlSelect Microsoft.SharePoint.WebControls.TemplatePicker::DdSiteCompatibilityLevel
0x3fd94a  brfalse.s loc_3FD959
0x3fd94c  ldarg.0
0x3fd94d  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlSelect Microsoft.SharePoint.WebControls.TemplatePicker::DdSiteCompatibilityLevel
0x3fd952  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x3fd957  br.s     loc_3FD95E
0x3fd959  ldstr    aInvalidddsitec// "InvalidDdSiteCompatibilityLevelId"
0x3fd95e  stelem.ref
0x3fd95f  ldloc.s  4
0x3fd961  ldc.i4.2
0x3fd962  ldstr    aIfCompatddlNul// "'); if (compatddl != null) {GetWebTempl"...
0x3fd967  stelem.ref
0x3fd968  ldloc.s  4
0x3fd96a  ldc.i4.3
0x3fd96b  ldarg.0
0x3fd96c  call     instance int32 Microsoft.SharePoint.WebControls.TemplatePicker::get_DefaultSiteCreationCompatibilityLevel()
0x3fd971  box      [mscorlib]System.Int32
0x3fd976  stelem.ref
0x3fd977  ldloc.s  4
0x3fd979  ldc.i4.4
0x3fd97a  ldstr    aContext_2// "+'&', 'context');}"
0x3fd97f  stelem.ref
0x3fd980  ldloc.s  4
0x3fd982  call     string [mscorlib]System.String::Concat(object[])
0x3fd987  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x3fd98c  ldarg.0
0x3fd98d  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlSelect Microsoft.SharePoint.WebControls.TemplatePicker::DdSiteCompatibilityLevel
0x3fd992  brfalse.s loc_3FD9EC
0x3fd994  ldarg.0
0x3fd995  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlSelect Microsoft.SharePoint.WebControls.TemplatePicker::DdSiteCompatibilityLevel
0x3fd99a  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x3fd99f  ldstr    aOnchange// "onchange"
0x3fd9a4  ldc.i4.5
0x3fd9a5  newarr   [mscorlib]System.String
0x3fd9aa  stloc.s  5
0x3fd9ac  ldloc.s  5
0x3fd9ae  ldc.i4.0
0x3fd9af  ldstr    aVarLangddlDocu// "var langddl=document.getElementById('"
0x3fd9b4  stelem.ref
0x3fd9b5  ldloc.s  5
0x3fd9b7  ldc.i4.1
0x3fd9b8  ldarg.0
0x3fd9b9  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlSelect Microsoft.SharePoint.WebControls.TemplatePicker::DdLanguageWebTemplate
0x3fd9be  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x3fd9c3  stelem.ref
0x3fd9c4  ldloc.s  5
0x3fd9c6  ldc.i4.2
0x3fd9c7  ldstr    aIfLangddlNullG// "'); if (langddl != null) {GetWebTemplat"...
0x3fd9cc  stelem.ref
0x3fd9cd  ldloc.s  5
0x3fd9cf  ldc.i4.3
0x3fd9d0  ldarg.0
0x3fd9d1  call     instance string Microsoft.SharePoint.WebControls.TemplatePicker::get_SelectedWebLanguage()
0x3fd9d6  stelem.ref
0x3fd9d7  ldloc.s  5
0x3fd9d9  ldc.i4.4
0x3fd9da  ldstr    aThisOptionsThi// "+'&' + this.options[this.selectedIndex]"...
0x3fd9df  stelem.ref
0x3fd9e0  ldloc.s  5
0x3fd9e2  call     string [mscorlib]System.String::Concat(string[])
0x3fd9e7  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x3fd9ec  ldarg.0
0x3fd9ed  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x3fd9f2  callvirt instance class [System.Web]System.Web.UI.ClientScriptManager [System.Web]System.Web.UI.Page::get_ClientScript()
0x3fd9f7  ldarg.0
0x3fd9f8  ldstr    aLcidcompatvalu// "lcidcompatvalue"
0x3fd9fd  ldstr    aClientcallback// "ClientCallback"
0x3fda02  ldstr    aContext// "context"
0x3fda07  ldstr    aClientcallback_0// "ClientCallbackError"
0x3fda0c  ldc.i4.0
0x3fda0d  callvirt instance string [System.Web]System.Web.UI.ClientScriptManager::GetCallbackEventReference(class [System.Web]System.Web.UI.Control, string, string, string, string, bool)
0x3fda12  stloc.0
0x3fda13  ldstr    aFunctionGetweb// "function GetWebTemplates(lcidcompatvalu"...
0x3fda18  ldloc.0
0x3fda19  ldstr    asc_E5E02A// "; }"
0x3fda1e  call     string [mscorlib]System.String::Concat(string, string, string)
0x3fda23  stloc.1
0x3fda24  ldarg.0
0x3fda25  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x3fda2a  ldtoken  Microsoft.SharePoint.WebControls.TemplatePicker
0x3fda2f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3fda34  ldstr    aGetwebtemplate// "GetWebTemplates"
0x3fda39  ldloc.1
0x3fda3a  call     void Microsoft.SharePoint.WebControls.SPPageContentManager::RegisterClientScriptBlock(class [System.Web]System.Web.UI.Page page, class [mscorlib]System.Type type, string key, string script)
0x3fda3f  ldc.i4.s 0x11
0x3fda41  newarr   [mscorlib]System.Object
0x3fda46  stloc.s  6
0x3fda48  ldloc.s  6
0x3fda4a  ldc.i4.0
0x3fda4b  ldstr    aCdataFunctionC// "\r\n          // <![CDATA[\r\n         "...
0x3fda50  stelem.ref
0x3fda51  ldloc.s  6
0x3fda53  ldc.i4.1
0x3fda54  ldarg.0
0x3fda55  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.SharePoint.WebControls.TemplatePicker::FilterTabs
0x3fda5a  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x3fda5f  stelem.ref
0x3fda60  ldloc.s  6
0x3fda62  ldc.i4.2
0x3fda63  ldstr    aVarNumchildsTa// "\");\r\n                var numchilds ="...
0x3fda68  stelem.ref
0x3fda69  ldloc.s  6
0x3fda6b  ldc.i4.3
0x3fda6c  ldarg.0
0x3fda6d  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlSelect Microsoft.SharePoint.WebControls.TemplatePicker::DdLanguageWebTemplate
0x3fda72  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x3fda77  stelem.ref
0x3fda78  ldloc.s  6
0x3fda7a  ldc.i4.4
0x3fda7b  ldstr    aIfLangddlNull// "\");  \r\n\r\n                if (langd"...
0x3fda80  stelem.ref
0x3fda81  ldloc.s  6
0x3fda83  ldc.i4.5
0x3fda84  ldarg.0
0x3fda85  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlSelect Microsoft.SharePoint.WebControls.TemplatePicker::DdLanguageWebTemplate
0x3fda8a  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x3fda8f  stelem.ref
0x3fda90  ldloc.s  6
0x3fda92  ldc.i4.6
0x3fda93  ldstr    aVarLcidI// "\");  \r\n                    var lcid "...
0x3fda98  stelem.ref
0x3fda99  ldloc.s  6
0x3fda9b  ldc.i4.7
0x3fda9c  ldarg.0
0x3fda9d  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlSelect Microsoft.SharePoint.WebControls.TemplatePicker::DdSiteCompatibilityLevel
0x3fdaa2  brfalse.s loc_3FDAB1
0x3fdaa4  ldarg.0
0x3fdaa5  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlSelect Microsoft.SharePoint.WebControls.TemplatePicker::DdSiteCompatibilityLevel
0x3fdaaa  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x3fdaaf  br.s     loc_3FDAB6
0x3fdab1  ldstr    aInvalidddsitec// "InvalidDdSiteCompatibilityLevelId"
0x3fdab6  stelem.ref
0x3fdab7  ldloc.s  6
0x3fdab9  ldc.i4.8
0x3fdaba  ldstr    aVarCompatlevel// "\");  \r\n                    var compa"...
0x3fdabf  stelem.ref
0x3fdac0  ldloc.s  6
0x3fdac2  ldc.i4.s 9
0x3fdac4  ldarg.0
0x3fdac5  call     instance int32 Microsoft.SharePoint.WebControls.TemplatePicker::get_DefaultSiteCreationCompatibilityLevel()
0x3fdaca  box      [mscorlib]System.Int32
0x3fdacf  stelem.ref
0x3fdad0  ldloc.s  6
0x3fdad2  ldc.i4.s 0xA
0x3fdad4  ldstr    aIfCompatddlNul_0// "\";\r\n                    if (compatdd"...
0x3fdad9  stelem.ref
0x3fdada  ldloc.s  6
0x3fdadc  ldc.i4.s 0xB
0x3fdade  ldarg.0
0x3fdadf  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputHidden Microsoft.SharePoint.WebControls.TemplatePicker::HiddenSelectedCategory
0x3fdae4  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x3fdae9  stelem.ref
0x3fdaea  ldloc.s  6
0x3fdaec  ldc.i4.s 0xC
0x3fdaee  ldstr    aNull_6// "\") != null)\r\n                       "...
0x3fdaf3  stelem.ref
0x3fdaf4  ldloc.s  6
0x3fdaf6  ldc.i4.s 0xD
0x3fdaf8  ldarg.0
0x3fdaf9  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputHidden Microsoft.SharePoint.WebControls.TemplatePicker::HiddenSelectedCategory
0x3fdafe  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x3fdb03  stelem.ref
0x3fdb04  ldloc.s  6
0x3fdb06  ldc.i4.s 0xE
0x3fdb08  ldstr    aValueUnescapep// "\").value = unescapeProperly(value);\r"...
0x3fdb0d  stelem.ref
0x3fdb0e  ldloc.s  6
0x3fdb10  ldc.i4.s 0xF
0x3fdb12  ldarg.0
0x3fdb13  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlSelect Microsoft.SharePoint.WebControls.TemplatePicker::LbWebTemplate
0x3fdb18  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x3fdb1d  stelem.ref
0x3fdb1e  ldloc.s  6
0x3fdb20  ldc.i4.s 0x10
0x3fdb22  ldstr    aIfTemplatelist// "\");\r\n                if(!templateLis"...
0x3fdb27  stelem.ref
0x3fdb28  ldloc.s  6
0x3fdb2a  call     string [mscorlib]System.String::Concat(object[])
0x3fdb2f  stloc.2
0x3fdb30  ldarg.0
0x3fdb31  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x3fdb36  ldtoken  Microsoft.SharePoint.WebControls.TemplatePicker
0x3fdb3b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3fdb40  ldstr    aClientcallback// "ClientCallback"
0x3fdb45  ldloc.2
0x3fdb46  call     void Microsoft.SharePoint.WebControls.SPPageContentManager::RegisterClientScriptBlock(class [System.Web]System.Web.UI.Page page, class [mscorlib]System.Type type, string key, string script)
0x3fdb4b  ldstr    aCdataFunctionC_0// "\r\n            // <![CDATA[\r\n       "...
0x3fdb50  stloc.3
0x3fdb51  ldarg.0
0x3fdb52  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x3fdb57  ldtoken  Microsoft.SharePoint.WebControls.TemplatePicker
0x3fdb5c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3fdb61  ldstr    aClientcallback_0// "ClientCallbackError"
0x3fdb66  ldloc.3
0x3fdb67  call     void Microsoft.SharePoint.WebControls.SPPageContentManager::RegisterClientScriptBlock(class [System.Web]System.Web.UI.Page page, class [mscorlib]System.Type type, string key, string script)
0x3fdb6c  ret
```
