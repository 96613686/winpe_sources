# Microsoft.SharePoint.WebPartPages.SPWebPartManager::RegisterRibbonTabsOld

- ea: `0x9edd80`
- end: `0x9ee7d9`
- name: `Microsoft.SharePoint.WebPartPages.SPWebPartManager::RegisterRibbonTabsOld`
- size: `2649`
- prototype: ``
- caller_count: `1`
- callee_count: `60`
- tags: `broker_com_uri`

## callers

- `0x9edad0`

## callees

- `0x19c360`
- `0x19c850`
- `0x19c8c0`
- `0x26f650`
- `0x31fc30`
- `0x342910`
- `0x344c40`
- `0x345a20`
- `0x345d00`
- `0x345f90`
- `0x347ec0`
- `0x4cd720`
- `0x4cd8e0`
- `0x4cde40`
- `0x4cdef0`
- `0x4cdfd0`
- `0x4ce110`
- `0x4ce610`
- `0x4ce640`
- `0x4ceaf0`
- `0x4ceb10`
- `0x5c5830`
- `0x5ce890`
- `0x789100`
- `0x789220`
- `0x807b60`
- `0x807b80`
- `0x807d80`
- `0x832e10`
- `0x850c80`
- `0x869c70`
- `0x869c90`
- `0x869cd0`
- `0x869cf0`
- `0x869d10`
- `0x869d80`
- `0x869d90`
- `0x869da0`
- `0x869db0`
- `0x869dc0`
- `0x869dd0`
- `0x869de0`
- `0x869e00`
- `0x869e20`
- `0x869e50`
- `0x87e7f0`
- `0x96ac70`
- `0x9ebf50`
- `0x9ec870`
- `0x9ecc50`

## string_xrefs

- `0x9ee4ae`: `Ribbon.Read`
- `0x9edfb7`: `",itemPermissions:`
- `0x9edfd1`: `};\n    SP.Ribbon.WebPartComponent.registerWithPageManager(initInfo);\n    var wpcomp = SP.Ribbon.WebPartComponent.get_instance();\n    var hid;\n    hid = document.getElementById("_wpSelected");\n    if (hid != null)\n    {\n        var wpid = hid.value;\n        if (wpid.length > 0)\n        {\n            var zc = document.getElementById(wpid);\n            if (zc != null)\n                wpcomp.selectWebPart(zc, false);\n        }\n    }\n    hid = document.getElementById("_w`
- `0x9edfec`: `wpcompInit`
- `0x9ee178`: `_spWebPartComponents`
- `0x9ee458`: `_spWebPartComponents`
- `0x9ee4cf`: `_spWebPartComponents`
- `0x9ee505`: `_spWebPartComponents`
- `0x9ee799`: `_spWebPartComponents`
- `0x9ee4bf`: `{0}["{1}"].firstTabId = "Ribbon.Read";`
- `0x9ee543`: `.initPageComponentScript = "`
- `0x9ee602`: `.contextualGroupCommands = `
- `0x9ee6d4`: `.pageComponentId = "`

## pseudocode

```c

```

## disassembly

```asm
0x9edd80  ldarg.0
0x9edd81  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x9edd86  call     class Microsoft.SharePoint.WebControls.SPRibbon Microsoft.SharePoint.WebControls.SPRibbon::GetCurrent(class [System.Web]System.Web.UI.Page page)
0x9edd8b  stloc.0
0x9edd8c  ldloc.0
0x9edd8d  brtrue.s loc_9EDD90
0x9edd8f  ret
0x9edd90  ldarg.0
0x9edd91  call     instance class [System.Web]System.Web.UI.WebControls.WebParts.WebPartZoneCollection [System.Web]System.Web.UI.WebControls.WebParts.WebPartManager::get_Zones()
0x9edd96  callvirt instance int32 [mscorlib]System.Collections.ReadOnlyCollectionBase::get_Count()
0x9edd9b  brtrue.s loc_9EDD9E
0x9edd9d  ret
0x9edd9e  call     bool Microsoft.SharePoint.SPContext::get_IsListViewOrListFormPageApproximately()
0x9edda3  stloc.1
0x9edda4  ldarg.0
0x9edda5  call     instance bool Microsoft.SharePoint.WebPartPages.SPWebPartManager::get_InDesignMode()
0x9eddaa  brtrue.s loc_9EDDAF
0x9eddac  ldloc.1
0x9eddad  brtrue.s loc_9EDDBA
0x9eddaf  ldloc.0
0x9eddb0  ldstr    aRibbonWebpartp_0// "Ribbon.WebPartPage"
0x9eddb5  callvirt instance void [Microsoft.Web.CommandUI]Microsoft.Web.CommandUI.Ribbon::MakeTabAvailable(string)
0x9eddba  ldc.i4   0x400
0x9eddbf  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x9eddc4  stloc.2
0x9eddc5  ldloc.2
0x9eddc6  ldstr    aFunctionRegist_2// "\r\nfunction _RegisterWebPartPageCUI()"...
0x9eddcb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x9eddd0  pop
0x9eddd1  ldarg.0
0x9eddd2  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x9eddd7  call     bool Microsoft.SharePoint.WebControls.SiteActions::ShouldShowEditPageMenuItem(class [System.Web]System.Web.UI.Page page)
0x9edddc  stloc.3
0x9edddd  ldloc.2
0x9eddde  ldstr    aEditable// "editable: "
0x9edde3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x9edde8  pop
0x9edde9  ldloc.2
0x9eddea  ldloc.3
0x9eddeb  brtrue.s loc_9EDDF4
0x9edded  ldstr    aFalse// "false"
0x9eddf2  br.s     loc_9EDDF9
0x9eddf4  ldstr    aTrue// "true"
0x9eddf9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x9eddfe  pop
0x9eddff  ldloc.2
0x9ede00  ldstr    aIseditmode// ",isEditMode: "
0x9ede05  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x9ede0a  pop
0x9ede0b  ldloc.2
0x9ede0c  ldarg.0
0x9ede0d  call     instance bool Microsoft.SharePoint.WebPartPages.SPWebPartManager::get_InDesignMode()
0x9ede12  brtrue.s loc_9EDE1B
0x9ede14  ldstr    aFalse// "false"
0x9ede19  br.s     loc_9EDE20
0x9ede1b  ldstr    aTrue// "true"
0x9ede20  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x9ede25  pop
0x9ede26  ldarg.0
0x9ede27  call     instance bool Microsoft.SharePoint.WebPartPages.SPWebPartManager::get_InDesignMode()
0x9ede2c  stloc.s  4
0x9ede2e  ldarg.0
0x9ede2f  call     instance bool Microsoft.SharePoint.WebPartPages.SPWebPartManager::get_PersonalizationMode()
0x9ede34  brfalse.s loc_9EDE4C
0x9ede36  ldarg.0
0x9ede37  call     instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.WebPartPages.SPWebPartManager::get_Web()
0x9ede3c  ldc.i4   0x10000000
0x9ede41  conv.i8
0x9ede42  callvirt instance bool Microsoft.SharePoint.SPSecurableObject::DoesUserHavePermissions(valuetype Microsoft.SharePoint.SPBasePermissions permissionMask)
0x9ede47  brtrue.s loc_9EDE4C
0x9ede49  ldc.i4.0
0x9ede4a  stloc.s  4
0x9ede4c  ldloc.2
0x9ede4d  ldstr    aAllowwebpartad// ",allowWebPartAdder: "
0x9ede52  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x9ede57  pop
0x9ede58  ldloc.2
0x9ede59  ldloc.s  4
0x9ede5b  brtrue.s loc_9EDE64
0x9ede5d  ldstr    aFalse// "false"
0x9ede62  br.s     loc_9EDE69
0x9ede64  ldstr    aTrue// "true"
0x9ede69  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x9ede6e  pop
0x9ede6f  call     bool Microsoft.SharePoint.SPContext::get_IsPageDoclibItem()
0x9ede74  brfalse  loc_9EDFD0
0x9ede79  call     class Microsoft.SharePoint.SPContext Microsoft.SharePoint.SPContext::get_Current()
0x9ede7e  stloc.s  5
0x9ede80  ldloc.2
0x9ede81  ldstr    aListid_12// ",listId: \""
0x9ede86  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x9ede8b  pop
0x9ede8c  ldloc.2
0x9ede8d  ldloc.s  5
0x9ede8f  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPContext::get_ListId()
0x9ede94  stloc.s  0x25
0x9ede96  ldloca.s 0x25
0x9ede98  ldstr    aB// "B"
0x9ede9d  call     instance string [mscorlib]System.Guid::ToString(string)
0x9edea2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x9edea7  pop
0x9edea8  ldloc.2
0x9edea9  ldstr    aItemid_9// "\",itemId: "
0x9edeae  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x9edeb3  pop
0x9edeb4  ldloc.2
0x9edeb5  ldloc.s  5
0x9edeb7  callvirt instance int32 Microsoft.SharePoint.SPContext::get_PageItemId()
0x9edebc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(int32)
0x9edec1  pop
0x9edec2  ldloc.2
0x9edec3  ldstr    aRecyclebinenab_0// ",recycleBinEnabled: "
0x9edec8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x9edecd  pop
0x9edece  ldloc.2
0x9edecf  ldloc.s  5
0x9eded1  callvirt instance class Microsoft.SharePoint.SPSite Microsoft.SharePoint.SPContext::get_Site()
0x9eded6  callvirt instance class Microsoft.SharePoint.Administration.SPWebApplication Microsoft.SharePoint.SPSite::get_WebApplication()
0x9ededb  callvirt instance bool Microsoft.SharePoint.Administration.SPWebApplication::get_RecycleBinEnabled()
0x9edee0  brtrue.s loc_9EDEE9
0x9edee2  ldstr    aFalse// "false"
0x9edee7  br.s     loc_9EDEEE
0x9edee9  ldstr    aTrue// "true"
0x9edeee  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x9edef3  pop
0x9edef4  ldloc.2
0x9edef5  ldstr    aEnableminorver_2// ",enableMinorVersioning: "
0x9edefa  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x9edeff  pop
0x9edf00  ldloc.2
0x9edf01  ldloc.s  5
0x9edf03  callvirt instance class Microsoft.SharePoint.SPList Microsoft.SharePoint.SPContext::get_List()
0x9edf08  callvirt instance bool Microsoft.SharePoint.SPList::get_EnableMinorVersions()
0x9edf0d  brtrue.s loc_9EDF16
0x9edf0f  ldstr    aFalse// "false"
0x9edf14  br.s     loc_9EDF1B
0x9edf16  ldstr    aTrue// "true"
0x9edf1b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x9edf20  pop
0x9edf21  ldloc.2
0x9edf22  ldstr    aEnablemoderati_0// ",enableModeration: "
0x9edf27  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x9edf2c  pop
0x9edf2d  ldloc.2
0x9edf2e  ldloc.s  5
0x9edf30  callvirt instance class Microsoft.SharePoint.SPList Microsoft.SharePoint.SPContext::get_List()
0x9edf35  callvirt instance bool Microsoft.SharePoint.SPList::get_EnableModeration()
0x9edf3a  brtrue.s loc_9EDF43
0x9edf3c  ldstr    aFalse// "false"
0x9edf41  br.s     loc_9EDF48
0x9edf43  ldstr    aTrue// "true"
0x9edf48  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x9edf4d  pop
0x9edf4e  ldloc.2
0x9edf4f  ldstr    aForcecheckout_0// ",forceCheckout: "
0x9edf54  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x9edf59  pop
0x9edf5a  ldloc.2
0x9edf5b  ldloc.s  5
0x9edf5d  callvirt instance class Microsoft.SharePoint.SPList Microsoft.SharePoint.SPContext::get_List()
0x9edf62  callvirt instance bool Microsoft.SharePoint.SPList::get_ForceCheckout()
0x9edf67  brtrue.s loc_9EDF70
0x9edf69  ldstr    aFalse// "false"
0x9edf6e  br.s     loc_9EDF75
0x9edf70  ldstr    aTrue// "true"
0x9edf75  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x9edf7a  pop
0x9edf7b  ldloc.2
0x9edf7c  ldstr    aRootfolderurl_2// ",rootFolderUrl: \""
0x9edf81  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x9edf86  pop
0x9edf87  ldloc.2
0x9edf88  ldloc.s  5
0x9edf8a  callvirt instance class Microsoft.SharePoint.SPList Microsoft.SharePoint.SPContext::get_List()
0x9edf8f  callvirt instance string Microsoft.SharePoint.SPList::get_RootFolderUrl()
0x9edf94  call     string Microsoft.SharePoint.Utilities.SPHttpUtility::EcmaScriptStringLiteralEncode(string scriptLiteralToEncode)
0x9edf99  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x9edf9e  pop
0x9edf9f  ldloc.s  5
0x9edfa1  callvirt instance class Microsoft.SharePoint.SPContextPageInfo Microsoft.SharePoint.SPContext::get_ContextPageInfo()
0x9edfa6  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.SharePoint.SPBasePermissions> Microsoft.SharePoint.SPContextPageInfo::get_BasePermissions()
0x9edfab  stloc.s  0x26
0x9edfad  ldloca.s 0x26
0x9edfaf  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.SharePoint.SPBasePermissions>::get_Value()
0x9edfb4  stloc.s  6
0x9edfb6  ldloc.2
0x9edfb7  ldstr    aItempermission// "\",itemPermissions:"
0x9edfbc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x9edfc1  pop
0x9edfc2  ldloc.2
0x9edfc3  ldloc.s  6
0x9edfc5  call     string Microsoft.SharePoint.Utilities.SPUtility::BasePermissionsToJson(valuetype Microsoft.SharePoint.SPBasePermissions perm)
0x9edfca  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x9edfcf  pop
0x9edfd0  ldloc.2
0x9edfd1  ldstr    aSpRibbonWebpar_0// "};\r\n    SP.Ribbon.WebPartComponent.re"...
0x9edfd6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x9edfdb  pop
0x9edfdc  ldarg.0
0x9edfdd  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x9edfe2  ldtoken  Microsoft.SharePoint.WebPartPages.WebPartPage
0x9edfe7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9edfec  ldstr    aWpcompinit// "wpcompInit"
0x9edff1  ldloc.2
0x9edff2  callvirt instance string [mscorlib]System.Object::ToString()
0x9edff7  call     void Microsoft.SharePoint.WebControls.SPPageContentManager::RegisterStartupScript(class [System.Web]System.Web.UI.Page page, class [mscorlib]System.Type type, string key, string script)
0x9edffc  ldarg.0
0x9edffd  call     instance void Microsoft.SharePoint.WebPartPages.SPWebPartManager::AddPageModeIndicatorStatusIfNecessary()
0x9ee002  ldsfld   string [mscorlib]System.String::Empty
0x9ee007  stloc.s  7
0x9ee009  ldsfld   string [mscorlib]System.String::Empty
0x9ee00e  stloc.s  8
0x9ee010  ldarg.0
0x9ee011  call     instance class [System.Web]System.Web.UI.WebControls.WebParts.WebPartCollection [System.Web]System.Web.UI.WebControls.WebParts.WebPartManager::get_WebParts()
0x9ee016  stloc.s  9
0x9ee018  ldarg.0
0x9ee019  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x9ee01e  callvirt instance bool [System.Web]System.Web.UI.Page::get_IsPostBack()
0x9ee023  brfalse.s loc_9EE08D
0x9ee025  ldarg.0
0x9ee026  call     instance bool Microsoft.SharePoint.WebPartPages.SPWebPartManager::get_InDesignMode()
0x9ee02b  brfalse.s loc_9EE05B
0x9ee02d  ldarg.0
0x9ee02e  ldfld    class Microsoft.SharePoint.WebPartPages.ToolPane Microsoft.SharePoint.WebPartPages.SPWebPartManager::toolPane
0x9ee033  brfalse.s loc_9EE05B
0x9ee035  ldarg.0
0x9ee036  ldfld    class Microsoft.SharePoint.WebPartPages.ToolPane Microsoft.SharePoint.WebPartPages.SPWebPartManager::toolPane
0x9ee03b  callvirt instance class [System.Web]System.Web.UI.WebControls.WebParts.WebPart Microsoft.SharePoint.WebPartPages.ToolPane::get_SelectedAspWebPart()
0x9ee040  stloc.s  0xA
0x9ee042  ldloc.s  0xA
0x9ee044  brfalse.s loc_9EE0B3
0x9ee046  ldstr    aMsozonecell// "MSOZoneCell_"
0x9ee04b  ldloc.s  0xA
0x9ee04d  call     string Microsoft.SharePoint.WebPartPages.SPWebPartManager::GetDomObjectID(class [System.Web]System.Web.UI.WebControls.WebParts.WebPart webPart)
0x9ee052  call     string [mscorlib]System.String::Concat(string, string)
0x9ee057  stloc.s  7
0x9ee059  br.s     loc_9EE0B3
0x9ee05b  ldarg.0
0x9ee05c  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x9ee061  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x9ee066  ldstr    aWpselected// "_wpSelected"
0x9ee06b  ldc.i4.1
0x9ee06c  call     T0x2B000035
0x9ee071  stloc.s  7
0x9ee073  ldarg.0
0x9ee074  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x9ee079  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x9ee07e  ldstr    aWzselected// "_wzSelected"
0x9ee083  ldc.i4.1
0x9ee084  call     T0x2B000035
0x9ee089  stloc.s  8
0x9ee08b  br.s     loc_9EE0B3
0x9ee08d  ldloc.s  9
0x9ee08f  callvirt instance int32 [mscorlib]System.Collections.ReadOnlyCollectionBase::get_Count()
0x9ee094  ldc.i4.1
0x9ee095  bne.un.s loc_9EE0B3
0x9ee097  ldloc.1
0x9ee098  brfalse.s loc_9EE0B3
0x9ee09a  ldstr    aMsozonecell// "MSOZoneCell_"
0x9ee09f  ldloc.s  9
0x9ee0a1  ldc.i4.0
0x9ee0a2  callvirt instance class [System.Web]System.Web.UI.WebControls.WebParts.WebPart [System.Web]System.Web.UI.WebControls.WebParts.WebPartCollection::get_Item(int32)
0x9ee0a7  call     string Microsoft.SharePoint.WebPartPages.SPWebPartManager::GetDomObjectID(class [System.Web]System.Web.UI.WebControls.WebParts.WebPart webPart)
0x9ee0ac  call     string [mscorlib]System.String::Concat(string, string)
0x9ee0b1  stloc.s  7
0x9ee0b3  ldarg.0
0x9ee0b4  call     instance bool Microsoft.SharePoint.WebPartPages.SPWebPartManager::get_InDesignMode()
0x9ee0b9  brfalse.s loc_9EE0FB
0x9ee0bb  ldloc.0
0x9ee0bc  callvirt instance string [Microsoft.Web.CommandUI]Microsoft.Web.CommandUI.Ribbon::get_ActiveTabId()
0x9ee0c1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9ee0c6  brfalse.s loc_9EE0DB
0x9ee0c8  ldloc.1
0x9ee0c9  brtrue.s loc_9EE0DB
0x9ee0cb  ldloc.0
0x9ee0cc  ldstr    aRibbonWebpartp_0// "Ribbon.WebPartPage"
0x9ee0d1  ldstr    aWsswebpartpage// "WSSWebPartPage"
0x9ee0d6  callvirt instance void [Microsoft.Web.CommandUI]Microsoft.Web.CommandUI.Ribbon::SetInitialTabId(string, string)
0x9ee0db  ldloc.0
0x9ee0dc  ldstr    aRibbonWebparti// "Ribbon.WebPartInsert.Tab"
0x9ee0e1  ldstr    aWsswebpartpage// "WSSWebPartPage"
0x9ee0e6  callvirt instance void [Microsoft.Web.CommandUI]Microsoft.Web.CommandUI.Ribbon::MakeTabAvailable(string, string)
0x9ee0eb  ldloc.0
0x9ee0ec  ldstr    aRibbonWebparto// "Ribbon.WebPartOption"
0x9ee0f1  ldstr    aWsswebpartpage// "WSSWebPartPage"
0x9ee0f6  callvirt instance void [Microsoft.Web.CommandUI]Microsoft.Web.CommandUI.Ribbon::MakeTabAvailable(string, string)
0x9ee0fb  ldarg.0
0x9ee0fc  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x9ee101  call     bool Microsoft.SharePoint.Utilities.SPUtility::IsBlogSitePage(class [System.Web]System.Web.UI.Page curPage)
0x9ee106  brfalse.s loc_9EE126
0x9ee108  ldloc.0
0x9ee109  ldstr    aWssfullpage// "WSSFullPage"
0x9ee10e  callvirt instance void [Microsoft.Web.CommandUI]Microsoft.Web.CommandUI.Ribbon::DisableVisibilityContext(string)
0x9ee113  ldarg.0
0x9ee114  call     instance bool Microsoft.SharePoint.WebPartPages.SPWebPartManager::get_InDesignMode()
0x9ee119  brtrue.s loc_9EE126
0x9ee11b  ldloc.0
0x9ee11c  ldstr    aWsswebpartpage// "WSSWebPartPage"
0x9ee121  callvirt instance void [Microsoft.Web.CommandUI]Microsoft.Web.CommandUI.Ribbon::DisableVisibilityContext(string)
0x9ee126  ldarg.0
  ... truncated ...
```
