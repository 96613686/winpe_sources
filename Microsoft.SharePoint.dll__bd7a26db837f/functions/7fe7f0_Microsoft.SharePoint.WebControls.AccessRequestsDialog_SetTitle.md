# Microsoft.SharePoint.WebControls.AccessRequestsDialog::SetTitle

- ea: `0x7fe7f0`
- end: `0x7fea0a`
- name: `Microsoft.SharePoint.WebControls.AccessRequestsDialog::SetTitle`
- size: `538`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0xbe7ef0`

## callees

- `0x342910`
- `0x577070`
- `0x7fe4b0`
- `0x7fe7f0`
- `0x7fea70`

## string_xrefs

- `0x7fe82d`: `AccessDeniedPage_SomeSiteAccess`
- `0x7fe941`: `AccessDeniedPage_SomeSiteAccess`
- `0x7fe842`: `AccessDeniedPage_SiteNotShared`
- `0x7fe916`: `AccessDeniedPage_SiteNotShared`
- `0x7fe956`: `AccessDeniedPage_SiteNotShared`
- `0x7fe9f4`: `AccessDeniedPage_SiteNotShared`
- `0x7fe863`: `AccessDeniedPage_ReqAccItem`
- `0x7fe977`: `AccessDeniedPage_ReqAccItem`
- `0x7fe878`: `AccessDeniedPage_ItemNotShared`
- `0x7fe98c`: `AccessDeniedPage_ItemNotShared`
- `0x7fe8a4`: `AccessDeniedPage_ReqAccList`
- `0x7fe9ad`: `AccessDeniedPage_ReqAccList`
- `0x7fe8ab`: `AccessDeniedPage_ReqAccGroup`
- `0x7fe8f8`: `AccessDeniedPage_ReqAccGroup`
- `0x7fe8c9`: `AccessDeniedPage_ListNotShared`
- `0x7fe9c2`: `AccessDeniedPage_ListNotShared`
- `0x7fe8f1`: `AccessDeniedPage_ReqAccSite`
- `0x7fe9df`: `AccessDeniedPage_ReqAccSite`

## pseudocode

```c

```

## disassembly

```asm
0x7fe7f0  ldarg.0
0x7fe7f1  call     instance bool Microsoft.SharePoint.WebControls.AccessRequestsDialog::get_ShowTitle()
0x7fe7f6  brfalse  loc_7FEA09
0x7fe7fb  ldarg.0
0x7fe7fc  ldfld    bool Microsoft.SharePoint.WebControls.AccessRequestsDialog::groupAccessDeniedFlightEnabled
0x7fe801  brfalse  loc_7FE92C
0x7fe806  ldarg.0
0x7fe807  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.WebControls.AccessRequestsDialog::groupId
0x7fe80c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x7fe811  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x7fe816  brfalse.s loc_7FE858
0x7fe818  ldarg.2
0x7fe819  ldc.i4   0x1000
0x7fe81e  conv.i8
0x7fe81f  callvirt instance bool Microsoft.SharePoint.SPSecurableObject::DoesUserHavePermissions(valuetype Microsoft.SharePoint.SPBasePermissions permissionMask)
0x7fe824  brfalse.s loc_7FE858
0x7fe826  ldarg.0
0x7fe827  ldarg.3
0x7fe828  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x7fe82d  ldstr    aAccessdeniedpa// "AccessDeniedPage_SomeSiteAccess"
0x7fe832  ldc.i4.0
0x7fe833  newarr   [mscorlib]System.Object
0x7fe838  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x7fe83d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x7fe842  ldstr    aAccessdeniedpa_0// "AccessDeniedPage_SiteNotShared"
0x7fe847  ldc.i4.0
0x7fe848  newarr   [mscorlib]System.Object
0x7fe84d  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x7fe852  call     instance void Microsoft.SharePoint.WebControls.AccessRequestsDialog::SetPageTitleInTitleArea(bool shouldAllow, string allowTitle, string disallowTitle)
0x7fe857  ret
0x7fe858  ldarg.1
0x7fe859  ldc.i4.2
0x7fe85a  bne.un.s loc_7FE88E
0x7fe85c  ldarg.0
0x7fe85d  ldarg.3
0x7fe85e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x7fe863  ldstr    aAccessdeniedpa_1// "AccessDeniedPage_ReqAccItem"
0x7fe868  ldc.i4.0
0x7fe869  newarr   [mscorlib]System.Object
0x7fe86e  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x7fe873  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x7fe878  ldstr    aAccessdeniedpa_2// "AccessDeniedPage_ItemNotShared"
0x7fe87d  ldc.i4.0
0x7fe87e  newarr   [mscorlib]System.Object
0x7fe883  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x7fe888  call     instance void Microsoft.SharePoint.WebControls.AccessRequestsDialog::SetPageTitleInTitleArea(bool shouldAllow, string allowTitle, string disallowTitle)
0x7fe88d  ret
0x7fe88e  ldarg.1
0x7fe88f  ldc.i4.1
0x7fe890  bne.un.s loc_7FE8DF
0x7fe892  ldarg.0
0x7fe893  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.WebControls.AccessRequestsDialog::groupId
0x7fe898  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x7fe89d  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x7fe8a2  brtrue.s loc_7FE8AB
0x7fe8a4  ldstr    aAccessdeniedpa_3// "AccessDeniedPage_ReqAccList"
0x7fe8a9  br.s     loc_7FE8B0
0x7fe8ab  ldstr    aAccessdeniedpa_4// "AccessDeniedPage_ReqAccGroup"
0x7fe8b0  stloc.0
0x7fe8b1  ldarg.0
0x7fe8b2  ldarg.3
0x7fe8b3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x7fe8b8  ldloc.0
0x7fe8b9  ldc.i4.0
0x7fe8ba  newarr   [mscorlib]System.Object
0x7fe8bf  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x7fe8c4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x7fe8c9  ldstr    aAccessdeniedpa_5// "AccessDeniedPage_ListNotShared"
0x7fe8ce  ldc.i4.0
0x7fe8cf  newarr   [mscorlib]System.Object
0x7fe8d4  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x7fe8d9  call     instance void Microsoft.SharePoint.WebControls.AccessRequestsDialog::SetPageTitleInTitleArea(bool shouldAllow, string allowTitle, string disallowTitle)
0x7fe8de  ret
0x7fe8df  ldarg.0
0x7fe8e0  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.WebControls.AccessRequestsDialog::groupId
0x7fe8e5  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x7fe8ea  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x7fe8ef  brtrue.s loc_7FE8F8
0x7fe8f1  ldstr    aAccessdeniedpa_6// "AccessDeniedPage_ReqAccSite"
0x7fe8f6  br.s     loc_7FE8FD
0x7fe8f8  ldstr    aAccessdeniedpa_4// "AccessDeniedPage_ReqAccGroup"
0x7fe8fd  stloc.1
0x7fe8fe  ldarg.0
0x7fe8ff  ldarg.3
0x7fe900  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x7fe905  ldloc.1
0x7fe906  ldc.i4.0
0x7fe907  newarr   [mscorlib]System.Object
0x7fe90c  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x7fe911  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x7fe916  ldstr    aAccessdeniedpa_0// "AccessDeniedPage_SiteNotShared"
0x7fe91b  ldc.i4.0
0x7fe91c  newarr   [mscorlib]System.Object
0x7fe921  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x7fe926  call     instance void Microsoft.SharePoint.WebControls.AccessRequestsDialog::SetPageTitleInTitleArea(bool shouldAllow, string allowTitle, string disallowTitle)
0x7fe92b  ret
0x7fe92c  ldarg.2
0x7fe92d  ldc.i4   0x1000
0x7fe932  conv.i8
0x7fe933  callvirt instance bool Microsoft.SharePoint.SPSecurableObject::DoesUserHavePermissions(valuetype Microsoft.SharePoint.SPBasePermissions permissionMask)
0x7fe938  brfalse.s loc_7FE96C
0x7fe93a  ldarg.0
0x7fe93b  ldarg.3
0x7fe93c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x7fe941  ldstr    aAccessdeniedpa// "AccessDeniedPage_SomeSiteAccess"
0x7fe946  ldc.i4.0
0x7fe947  newarr   [mscorlib]System.Object
0x7fe94c  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x7fe951  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x7fe956  ldstr    aAccessdeniedpa_0// "AccessDeniedPage_SiteNotShared"
0x7fe95b  ldc.i4.0
0x7fe95c  newarr   [mscorlib]System.Object
0x7fe961  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x7fe966  call     instance void Microsoft.SharePoint.WebControls.AccessRequestsDialog::SetPageTitleInTitleArea(bool shouldAllow, string allowTitle, string disallowTitle)
0x7fe96b  ret
0x7fe96c  ldarg.1
0x7fe96d  ldc.i4.2
0x7fe96e  bne.un.s loc_7FE9A2
0x7fe970  ldarg.0
0x7fe971  ldarg.3
0x7fe972  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x7fe977  ldstr    aAccessdeniedpa_1// "AccessDeniedPage_ReqAccItem"
0x7fe97c  ldc.i4.0
0x7fe97d  newarr   [mscorlib]System.Object
0x7fe982  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x7fe987  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x7fe98c  ldstr    aAccessdeniedpa_2// "AccessDeniedPage_ItemNotShared"
0x7fe991  ldc.i4.0
0x7fe992  newarr   [mscorlib]System.Object
0x7fe997  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x7fe99c  call     instance void Microsoft.SharePoint.WebControls.AccessRequestsDialog::SetPageTitleInTitleArea(bool shouldAllow, string allowTitle, string disallowTitle)
0x7fe9a1  ret
0x7fe9a2  ldarg.1
0x7fe9a3  ldc.i4.1
0x7fe9a4  bne.un.s loc_7FE9D8
0x7fe9a6  ldarg.0
0x7fe9a7  ldarg.3
0x7fe9a8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x7fe9ad  ldstr    aAccessdeniedpa_3// "AccessDeniedPage_ReqAccList"
0x7fe9b2  ldc.i4.0
0x7fe9b3  newarr   [mscorlib]System.Object
0x7fe9b8  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x7fe9bd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x7fe9c2  ldstr    aAccessdeniedpa_5// "AccessDeniedPage_ListNotShared"
0x7fe9c7  ldc.i4.0
0x7fe9c8  newarr   [mscorlib]System.Object
0x7fe9cd  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x7fe9d2  call     instance void Microsoft.SharePoint.WebControls.AccessRequestsDialog::SetPageTitleInTitleArea(bool shouldAllow, string allowTitle, string disallowTitle)
0x7fe9d7  ret
0x7fe9d8  ldarg.0
0x7fe9d9  ldarg.3
0x7fe9da  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x7fe9df  ldstr    aAccessdeniedpa_6// "AccessDeniedPage_ReqAccSite"
0x7fe9e4  ldc.i4.0
0x7fe9e5  newarr   [mscorlib]System.Object
0x7fe9ea  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x7fe9ef  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x7fe9f4  ldstr    aAccessdeniedpa_0// "AccessDeniedPage_SiteNotShared"
0x7fe9f9  ldc.i4.0
0x7fe9fa  newarr   [mscorlib]System.Object
0x7fe9ff  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x7fea04  call     instance void Microsoft.SharePoint.WebControls.AccessRequestsDialog::SetPageTitleInTitleArea(bool shouldAllow, string allowTitle, string disallowTitle)
0x7fea09  ret
```
