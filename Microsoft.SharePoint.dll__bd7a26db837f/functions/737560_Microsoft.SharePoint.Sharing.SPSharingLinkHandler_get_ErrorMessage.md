# Microsoft.SharePoint.Sharing.SPSharingLinkHandler::get_ErrorMessage

- ea: `0x737560`
- end: `0x737865`
- name: `Microsoft.SharePoint.Sharing.SPSharingLinkHandler::get_ErrorMessage`
- size: `773`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x577070`
- `0x6c9890`
- `0x7372c0`
- `0x7374d0`
- `0x737560`

## string_xrefs

- `0x73762e`: `ShareByLink_ParseError`
- `0x737799`: `ShareByLink_ParseError`
- `0x737686`: `ShareByLink_InvalidPassword`
- `0x737807`: `ShareByLink_InvalidPassword`
- `0x737644`: `ShareByLink_InvalidToken`
- `0x7377af`: `ShareByLink_InvalidToken`
- `0x73765a`: `ShareByLink_ExpiredLinkWithTitle`
- `0x7377db`: `ShareByLink_ExpiredLinkWithTitle`
- `0x737670`: `ShareByLink_ExternalUserTitle`
- `0x7377f1`: `ShareByLink_ExternalUserTitle`
- `0x73769c`: `ShareByLink_AccountNotInvited`
- `0x73781d`: `ShareByLink_AccountNotInvited`
- `0x7376bd`: `ShareByLink_SessionsOverQuota`
- `0x73783e`: `ShareByLink_SessionsOverQuota`
- `0x7376d3`: `ShareByLink_MissingFile`
- `0x737854`: `ShareByLink_MissingFile`
- `0x7377c5`: `ShareByLink_DisabledLink`

## pseudocode

```c

```

## disassembly

```asm
0x737560  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Sharing.SPSharingLinkHandler::ChangeSharingErrorMessagesKillswitchId
0x737565  ldstr    a222018// "2/2/2018"
0x73756a  ldstr    aSharingChanges// "Sharing_ChangeSharingErrorMessages"
0x73756f  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x737574  brfalse  loc_7376E4
0x737579  ldarg.0
0x73757a  callvirt instance valuetype ErrorReason Microsoft.SharePoint.Sharing.SPSharingLinkHandler::get_Error()
0x73757f  stloc.0
0x737580  ldloc.0
0x737581  ldc.i4.2
0x737582  sub
0x737583  switch   loc_737629, loc_737629, loc_737629, loc_737629, loc_737629, loc_737629, loc_737629, loc_737629, loc_7376CE, loc_73763F, loc_73763F, loc_73763F, loc_73763F, loc_737655, loc_73763F, loc_73763F, loc_73763F, loc_737655, loc_73763F, loc_7376CE, loc_7376CE, loc_73766B, loc_7376CE, loc_73763F, loc_7376CE, loc_7376CE, loc_737629, loc_7376CE, loc_7376CE, loc_737681, loc_7376CE, loc_7376CE, loc_7376CE, loc_7376CE, loc_7376CE, loc_737697, loc_7376CE, loc_7376CE, loc_7376B8
0x737624  br       loc_7376CE
0x737629  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x73762e  ldstr    aSharebylinkPar// "ShareByLink_ParseError"
0x737633  ldc.i4.0
0x737634  newarr   [mscorlib]System.Object
0x737639  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x73763e  ret
0x73763f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x737644  ldstr    aSharebylinkInv_0// "ShareByLink_InvalidToken"
0x737649  ldc.i4.0
0x73764a  newarr   [mscorlib]System.Object
0x73764f  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x737654  ret
0x737655  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x73765a  ldstr    aSharebylinkExp// "ShareByLink_ExpiredLinkWithTitle"
0x73765f  ldc.i4.0
0x737660  newarr   [mscorlib]System.Object
0x737665  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x73766a  ret
0x73766b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x737670  ldstr    aSharebylinkExt// "ShareByLink_ExternalUserTitle"
0x737675  ldc.i4.0
0x737676  newarr   [mscorlib]System.Object
0x73767b  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x737680  ret
0x737681  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x737686  ldstr    aSharebylinkInv// "ShareByLink_InvalidPassword"
0x73768b  ldc.i4.0
0x73768c  newarr   [mscorlib]System.Object
0x737691  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x737696  ret
0x737697  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x73769c  ldstr    aSharebylinkAcc// "ShareByLink_AccountNotInvited"
0x7376a1  ldc.i4.1
0x7376a2  newarr   [mscorlib]System.Object
0x7376a7  stloc.1
0x7376a8  ldloc.1
0x7376a9  ldc.i4.0
0x7376aa  ldarg.0
0x7376ab  callvirt instance string Microsoft.SharePoint.Sharing.SPSharingLinkHandler::get_InvitationCheckedAddress()
0x7376b0  stelem.ref
0x7376b1  ldloc.1
0x7376b2  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x7376b7  ret
0x7376b8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x7376bd  ldstr    aSharebylinkSes// "ShareByLink_SessionsOverQuota"
0x7376c2  ldc.i4.0
0x7376c3  newarr   [mscorlib]System.Object
0x7376c8  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x7376cd  ret
0x7376ce  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x7376d3  ldstr    aSharebylinkMis// "ShareByLink_MissingFile"
0x7376d8  ldc.i4.0
0x7376d9  newarr   [mscorlib]System.Object
0x7376de  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x7376e3  ret
0x7376e4  ldarg.0
0x7376e5  callvirt instance valuetype ErrorReason Microsoft.SharePoint.Sharing.SPSharingLinkHandler::get_Error()
0x7376ea  stloc.2
0x7376eb  ldloc.2
0x7376ec  ldc.i4.2
0x7376ed  sub
0x7376ee  switch   loc_737794, loc_737794, loc_737794, loc_737794, loc_737794, loc_737794, loc_737794, loc_737794, loc_73784F, loc_7377C0, loc_7377C0, loc_7377AA, loc_7377AA, loc_7377D6, loc_7377AA, loc_7377AA, loc_7377AA, loc_7377D6, loc_7377AA, loc_73784F, loc_73784F, loc_7377EC, loc_73784F, loc_7377AA, loc_73784F, loc_73784F, loc_737794, loc_73784F, loc_73784F, loc_737802, loc_73784F, loc_73784F, loc_73784F, loc_73784F, loc_73784F, loc_737818, loc_73784F, loc_73784F, loc_737839
0x73778f  br       loc_73784F
0x737794  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x737799  ldstr    aSharebylinkPar// "ShareByLink_ParseError"
0x73779e  ldc.i4.0
0x73779f  newarr   [mscorlib]System.Object
0x7377a4  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x7377a9  ret
0x7377aa  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x7377af  ldstr    aSharebylinkInv_0// "ShareByLink_InvalidToken"
0x7377b4  ldc.i4.0
0x7377b5  newarr   [mscorlib]System.Object
0x7377ba  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x7377bf  ret
0x7377c0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x7377c5  ldstr    aSharebylinkDis_1// "ShareByLink_DisabledLink"
0x7377ca  ldc.i4.0
0x7377cb  newarr   [mscorlib]System.Object
0x7377d0  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x7377d5  ret
0x7377d6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x7377db  ldstr    aSharebylinkExp// "ShareByLink_ExpiredLinkWithTitle"
0x7377e0  ldc.i4.0
0x7377e1  newarr   [mscorlib]System.Object
0x7377e6  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x7377eb  ret
0x7377ec  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x7377f1  ldstr    aSharebylinkExt// "ShareByLink_ExternalUserTitle"
0x7377f6  ldc.i4.0
0x7377f7  newarr   [mscorlib]System.Object
0x7377fc  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x737801  ret
0x737802  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x737807  ldstr    aSharebylinkInv// "ShareByLink_InvalidPassword"
0x73780c  ldc.i4.0
0x73780d  newarr   [mscorlib]System.Object
0x737812  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x737817  ret
0x737818  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x73781d  ldstr    aSharebylinkAcc// "ShareByLink_AccountNotInvited"
0x737822  ldc.i4.1
0x737823  newarr   [mscorlib]System.Object
0x737828  stloc.3
0x737829  ldloc.3
0x73782a  ldc.i4.0
0x73782b  ldarg.0
0x73782c  callvirt instance string Microsoft.SharePoint.Sharing.SPSharingLinkHandler::get_InvitationCheckedAddress()
0x737831  stelem.ref
0x737832  ldloc.3
0x737833  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x737838  ret
0x737839  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x73783e  ldstr    aSharebylinkSes// "ShareByLink_SessionsOverQuota"
0x737843  ldc.i4.0
0x737844  newarr   [mscorlib]System.Object
0x737849  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x73784e  ret
0x73784f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x737854  ldstr    aSharebylinkMis// "ShareByLink_MissingFile"
0x737859  ldc.i4.0
0x73785a  newarr   [mscorlib]System.Object
0x73785f  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x737864  ret
```
