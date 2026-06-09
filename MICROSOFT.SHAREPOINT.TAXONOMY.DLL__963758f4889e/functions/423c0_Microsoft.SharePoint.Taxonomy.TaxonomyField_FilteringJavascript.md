# Microsoft.SharePoint.Taxonomy.TaxonomyField::FilteringJavascript

- ea: `0x423c0`
- end: `0x42477`
- name: `Microsoft.SharePoint.Taxonomy.TaxonomyField::FilteringJavascript`
- size: `183`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x251b0`
- `0x2acd0`
- `0x423c0`

## string_xrefs

- `0x423dc`: `var listId;\n            var fieldId;\n            var currentFilteredId;\n            var webServiceUrl;\n            var currentFilterMenu;\n            var isIncludeDescendants;\n\n            function RemoveGroupStringAndIsGroupRender(strUrl)\n            {\n                var groupString = /GroupString=[^&]*/gi;\n                strUrl = strUrl.replace(groupString, '');\n                var groupRender = /&IsGroupRender=TRUE/gi;\n                strUrl = strUrl.replace(groupRen`
- `0x423f6`: `';\n                currentFilterMenu = window.parent.currentFilterMenu;\n\n                var strUrl = window.parent.DeferCall('GetSource2', null, window.parent.ctxFilter != null ? window.parent.ctxFilter.clvp : null, true);\n                if (strUrl == null)\n                    strUrl = window.parent.window.location.href;\n                var url = strUrl;\n                var arrayField = url.match('FilterField([0-9]+)='+fieldName);\n                if (arrayField !=null)\n      `
- `0x42420`: `images/' + (isIncludeDescendants?'IncludeDescendantsSelected':'IncludeDescendants') + '.png');\n                if (enabled)\n                {\n                    var descendantUrl = GetFilterString(view, fieldName, descendantsKey, termId, !isIncludeDescendants);\n                    if (descendantUrl.length < 2048)\n                    {\n                        includeMenu.setAttribute('onMenuClick', "javascript:window.parent.HandleFilter(window.parent.event, '"+STSScriptEncode(descend`
- `0x42436`: `var listId;\n            var fieldId;\n            var currentFilteredId;\n            var webServiceUrl;\n            var currentFilterMenu;\n            var isIncludeDescendants;\n            function GetFilterString(view, fieldName, key, termId, localIncludeDescendants)\n            {\n                var strUrl = window.parent.DeferCall('GetSource2', null, window.parent.ctxFilter != null ? window.parent.ctxFilter.clvp : null);\n                if (strUrl == null)\n                 `
- `0x42450`: `';\n                currentFilterMenu = window.parent.currentFilterMenu;\n\n                var strUrl = window.parent.DeferCall('GetSource2', null, window.parent.ctxFilter != null ? window.parent.ctxFilter.clvp : null);\n                if (strUrl == null)\n                    strUrl = window.parent.window.location.href;\n                var url = strUrl;\n                var arrayField = url.match('FilterField([0-9]+)='+fieldName);\n                if (arrayField !=null)\n            `
- `0x4246a`: `';\n                            isIncludeDescendants = true;\n                        }\n                    }\n                }\n                includeMenu=window.parent.CAMOpt(parentMenu, text, "javascript:alert('Menu not set');", '/_layouts/images/' + (isIncludeDescendants?'IncludeDescendantsSelected':'IncludeDescendants') + '.png');\n                if (enabled)\n                {\n                    var descendantUrl = GetFilterString(view, fieldName, descendantsKey, termId, !isI`

## pseudocode

```c

```

## disassembly

```asm
0x423c0  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Current()
0x423c5  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite [Microsoft.SharePoint]Microsoft.SharePoint.SPContext::get_Site()
0x423ca  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_CompatibilityLevel()
0x423cf  ldc.i4.s 0xE
0x423d1  ble.s    loc_4242D
0x423d3  ldc.i4.7
0x423d4  newarr   [mscorlib]System.String
0x423d9  stloc.0
0x423da  ldloc.0
0x423db  ldc.i4.0
0x423dc  ldstr    aVarListidVarFi// "var listId;\r\n            var fieldId;"...
0x423e1  stelem.ref
0x423e2  ldloc.0
0x423e3  ldc.i4.1
0x423e4  ldstr    aFiltermenueinc// "FilterMenueIncludeDescendants"
0x423e9  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x423ee  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPEncode::ScriptEncode(string)
0x423f3  stelem.ref
0x423f4  ldloc.0
0x423f5  ldc.i4.2
0x423f6  ldstr    aCurrentfilterm// "';\r\n                currentFilterMenu"...
0x423fb  stelem.ref
0x423fc  ldloc.0
0x423fd  ldc.i4.3
0x423fe  ldstr    aFiltermenueexc// "FilterMenueExcludeDescendants"
0x42403  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x42408  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPEncode::ScriptEncode(string)
0x4240d  stelem.ref
0x4240e  ldloc.0
0x4240f  ldc.i4.4
0x42410  ldstr    aIsincludedesce// "';\r\n                            isInc"...
0x42415  stelem.ref
0x42416  ldloc.0
0x42417  ldc.i4.5
0x42418  call     string Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::get_LayoutsVersionUrl()
0x4241d  stelem.ref
0x4241e  ldloc.0
0x4241f  ldc.i4.6
0x42420  ldstr    aImagesIsinclud// "images/' + (isIncludeDescendants?'Inclu"...
0x42425  stelem.ref
0x42426  ldloc.0
0x42427  call     string [mscorlib]System.String::Concat(string[])
0x4242c  ret
0x4242d  ldc.i4.5
0x4242e  newarr   [mscorlib]System.String
0x42433  stloc.1
0x42434  ldloc.1
0x42435  ldc.i4.0
0x42436  ldstr    aVarListidVarFi_0// "var listId;\r\n            var fieldId;"...
0x4243b  stelem.ref
0x4243c  ldloc.1
0x4243d  ldc.i4.1
0x4243e  ldstr    aFiltermenueinc// "FilterMenueIncludeDescendants"
0x42443  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x42448  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPEncode::ScriptEncode(string)
0x4244d  stelem.ref
0x4244e  ldloc.1
0x4244f  ldc.i4.2
0x42450  ldstr    aCurrentfilterm_0// "';\r\n                currentFilterMenu"...
0x42455  stelem.ref
0x42456  ldloc.1
0x42457  ldc.i4.3
0x42458  ldstr    aFiltermenueexc// "FilterMenueExcludeDescendants"
0x4245d  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x42462  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPEncode::ScriptEncode(string)
0x42467  stelem.ref
0x42468  ldloc.1
0x42469  ldc.i4.4
0x4246a  ldstr    aIsincludedesce_0// "';\r\n                            isInc"...
0x4246f  stelem.ref
0x42470  ldloc.1
0x42471  call     string [mscorlib]System.String::Concat(string[])
0x42476  ret
```
