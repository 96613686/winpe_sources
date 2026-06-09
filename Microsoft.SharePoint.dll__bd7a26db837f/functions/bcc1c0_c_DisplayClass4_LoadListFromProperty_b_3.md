# <>c__DisplayClass4::<LoadListFromProperty>b__3

- ea: `0xbcc1c0`
- end: `0xbcc467`
- name: `<>c__DisplayClass4::<LoadListFromProperty>b__3`
- size: `679`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x26b840`
- `0x26fa60`
- `0x342910`
- `0x578140`
- `0x578160`
- `0x5c3f30`
- `0x6c9890`
- `0x93dae0`
- `0x957470`
- `0xbcc1c0`

## string_xrefs

- `0xbcc285`: `youtube.com`
- `0xbcc295`: `youtube-nocookie.com`
- `0xbcc2a5`: `player.vimeo.com`
- `0xbcc2b5`: `bing.com`
- `0xbcc2c5`: `office.microsoft.com`
- `0xbcc2d5`: `officeclient.microsoft.com`
- `0xbcc2e5`: `store.office.com`
- `0xbcc2f5`: `skydrive.live.com`
- `0xbcc305`: `powerbi.com`
- `0xbcc315`: `sway.com`
- `0xbcc325`: `docs.com`
- `0xbcc335`: `microsoftstream.com`
- `0xbcc345`: `powerapps.com`
- `0xbcc355`: `flow.microsoft.com`
- `0xbcc365`: `app.smartsheet.com`
- `0xbcc375`: `publish.smartsheet.com`
- `0xbcc3a5`: `read.amazon.com`
- `0xbcc3b5`: `onedrive.live.com`
- `0xbcc3c5`: `www.microsoft.com`
- `0xbcc3e5`: `support.office.com`
- `0xbcc3f5`: `embed.ted.com`
- `0xbcc405`: `channel9.msdn.com`
- `0xbcc415`: `forms.office.com`

## pseudocode

```c

```

## disassembly

```asm
0xbcc1c0  ldarg.2
0xbcc1c1  callvirt instance class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.SPWeb::get_AllProperties()
0xbcc1c6  ldarg.0
0xbcc1c7  ldfld    string <>c__DisplayClass4::propertyToRead
0xbcc1cc  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0xbcc1d1  isinst   [mscorlib]System.String
0xbcc1d6  stloc.0
0xbcc1d7  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.ScriptSafeLoader::customizedDomainImprovementSafeKillSwitch
0xbcc1dc  ldstr    a07152017// "07/15/2017"
0xbcc1e1  ldstr    aUseCustomizedD// "Use customized domain allow list with m"...
0xbcc1e6  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0xbcc1eb  stloc.1
0xbcc1ec  ldloc.0
0xbcc1ed  brfalse.s loc_BCC220
0xbcc1ef  ldloc.1
0xbcc1f0  brtrue.s loc_BCC213
0xbcc1f2  ldarg.0
0xbcc1f3  ldfld    class Microsoft.SharePoint.SPSite <>c__DisplayClass4::site
0xbcc1f8  callvirt instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPSite::get_RootWeb()
0xbcc1fd  ldc.i4   0x40000
0xbcc202  conv.i8
0xbcc203  callvirt instance bool Microsoft.SharePoint.SPSecurableObject::DoesUserHavePermissions(valuetype Microsoft.SharePoint.SPBasePermissions permissionMask)
0xbcc208  brtrue.s loc_BCC213
0xbcc20a  ldarg.0
0xbcc20b  ldfld    valuetype Microsoft.SharePoint.ScriptSafeRecordTypes <>c__DisplayClass4::type
0xbcc210  ldc.i4.2
0xbcc211  bne.un.s loc_BCC220
0xbcc213  ldarg.0
0xbcc214  ldloc.0
0xbcc215  call     class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.SharePoint.ScriptSafeLoader::CreateListFromString(string value)
0xbcc21a  stfld    class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass4::result
0xbcc21f  ret
0xbcc220  ldc.i4   0x11515
0xbcc225  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0xbcc22a  ldc.i4.s 0x64
0xbcc22c  ldstr    aScriptSafeProp// "Script safe property {0} was not found "...
0xbcc231  ldc.i4.2
0xbcc232  newarr   [mscorlib]System.Object
0xbcc237  stloc.2
0xbcc238  ldloc.2
0xbcc239  ldc.i4.0
0xbcc23a  ldarg.0
0xbcc23b  ldfld    string <>c__DisplayClass4::propertyToRead
0xbcc240  stelem.ref
0xbcc241  ldloc.2
0xbcc242  ldc.i4.1
0xbcc243  ldarg.0
0xbcc244  ldfld    class Microsoft.SharePoint.SPSite <>c__DisplayClass4::site
0xbcc249  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSite::get_ID()
0xbcc24e  box      [mscorlib]System.Guid
0xbcc253  stelem.ref
0xbcc254  ldloc.2
0xbcc255  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0xbcc25a  ldarg.0
0xbcc25b  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0xbcc260  stfld    class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass4::result
0xbcc265  ldarg.0
0xbcc266  ldfld    valuetype Microsoft.SharePoint.ScriptSafeRecordTypes <>c__DisplayClass4::type
0xbcc26b  brfalse.s loc_BCC27F
0xbcc26d  ldloc.1
0xbcc26e  brtrue   loc_BCC431
0xbcc273  ldarg.0
0xbcc274  ldfld    valuetype Microsoft.SharePoint.ScriptSafeRecordTypes <>c__DisplayClass4::type
0xbcc279  ldc.i4.2
0xbcc27a  bne.un   loc_BCC431
0xbcc27f  ldarg.0
0xbcc280  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass4::result
0xbcc285  ldstr    aYoutubeCom// "youtube.com"
0xbcc28a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xbcc28f  ldarg.0
0xbcc290  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass4::result
0xbcc295  ldstr    aYoutubeNocooki// "youtube-nocookie.com"
0xbcc29a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xbcc29f  ldarg.0
0xbcc2a0  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass4::result
0xbcc2a5  ldstr    aPlayerVimeoCom// "player.vimeo.com"
0xbcc2aa  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xbcc2af  ldarg.0
0xbcc2b0  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass4::result
0xbcc2b5  ldstr    aBingCom// "bing.com"
0xbcc2ba  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xbcc2bf  ldarg.0
0xbcc2c0  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass4::result
0xbcc2c5  ldstr    aOfficeMicrosof// "office.microsoft.com"
0xbcc2ca  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xbcc2cf  ldarg.0
0xbcc2d0  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass4::result
0xbcc2d5  ldstr    aOfficeclientMi// "officeclient.microsoft.com"
0xbcc2da  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xbcc2df  ldarg.0
0xbcc2e0  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass4::result
0xbcc2e5  ldstr    aStoreOfficeCom// "store.office.com"
0xbcc2ea  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xbcc2ef  ldarg.0
0xbcc2f0  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass4::result
0xbcc2f5  ldstr    aSkydriveLiveCo// "skydrive.live.com"
0xbcc2fa  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xbcc2ff  ldarg.0
0xbcc300  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass4::result
0xbcc305  ldstr    aPowerbiCom// "powerbi.com"
0xbcc30a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xbcc30f  ldarg.0
0xbcc310  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass4::result
0xbcc315  ldstr    aSwayCom// "sway.com"
0xbcc31a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xbcc31f  ldarg.0
0xbcc320  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass4::result
0xbcc325  ldstr    aDocsCom// "docs.com"
0xbcc32a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xbcc32f  ldarg.0
0xbcc330  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass4::result
0xbcc335  ldstr    aMicrosoftstrea// "microsoftstream.com"
0xbcc33a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xbcc33f  ldarg.0
0xbcc340  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass4::result
0xbcc345  ldstr    aPowerappsCom_0// "powerapps.com"
0xbcc34a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xbcc34f  ldarg.0
0xbcc350  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass4::result
0xbcc355  ldstr    aFlowMicrosoftC// "flow.microsoft.com"
0xbcc35a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xbcc35f  ldarg.0
0xbcc360  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass4::result
0xbcc365  ldstr    aAppSmartsheetC// "app.smartsheet.com"
0xbcc36a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xbcc36f  ldarg.0
0xbcc370  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass4::result
0xbcc375  ldstr    aPublishSmartsh// "publish.smartsheet.com"
0xbcc37a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xbcc37f  ldarg.0
0xbcc380  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass4::result
0xbcc385  ldstr    aWwwSlideshareN// "www.slideshare.net"
0xbcc38a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xbcc38f  ldarg.0
0xbcc390  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass4::result
0xbcc395  ldstr    aYoutuBe// "youtu.be"
0xbcc39a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xbcc39f  ldarg.0
0xbcc3a0  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass4::result
0xbcc3a5  ldstr    aReadAmazonCom// "read.amazon.com"
0xbcc3aa  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xbcc3af  ldarg.0
0xbcc3b0  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass4::result
0xbcc3b5  ldstr    aOnedriveLiveCo_0// "onedrive.live.com"
0xbcc3ba  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xbcc3bf  ldarg.0
0xbcc3c0  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass4::result
0xbcc3c5  ldstr    aWwwMicrosoftCo// "www.microsoft.com"
0xbcc3ca  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xbcc3cf  ldarg.0
0xbcc3d0  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass4::result
0xbcc3d5  ldstr    aFormsOffice365// "forms.office365.us"
0xbcc3da  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xbcc3df  ldarg.0
0xbcc3e0  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass4::result
0xbcc3e5  ldstr    aSupportOfficeC// "support.office.com"
0xbcc3ea  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xbcc3ef  ldarg.0
0xbcc3f0  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass4::result
0xbcc3f5  ldstr    aEmbedTedCom// "embed.ted.com"
0xbcc3fa  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xbcc3ff  ldarg.0
0xbcc400  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass4::result
0xbcc405  ldstr    aChannel9MsdnCo// "channel9.msdn.com"
0xbcc40a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xbcc40f  ldarg.0
0xbcc410  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass4::result
0xbcc415  ldstr    aFormsOfficeCom// "forms.office.com"
0xbcc41a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xbcc41f  ldarg.0
0xbcc420  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass4::result
0xbcc425  ldstr    aVideoplayercdn// "videoplayercdn.osi.office.net"
0xbcc42a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xbcc42f  br.s     loc_BCC44A
0xbcc431  ldarg.0
0xbcc432  ldfld    valuetype Microsoft.SharePoint.ScriptSafeRecordTypes <>c__DisplayClass4::type
0xbcc437  ldc.i4.1
0xbcc438  bne.un.s loc_BCC44A
0xbcc43a  ldarg.0
0xbcc43b  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass4::result
0xbcc440  ldstr    aWopiframeAspx_0// "WopiFrame.aspx"
0xbcc445  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xbcc44a  ldarg.2
0xbcc44b  callvirt instance class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.SPWeb::get_AllProperties()
0xbcc450  ldarg.0
0xbcc451  ldfld    string <>c__DisplayClass4::propertyToRead
0xbcc456  ldarg.0
0xbcc457  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass4::result
0xbcc45c  call     string Microsoft.SharePoint.ScriptSafeLoader::CreateStringFromList(class [mscorlib]System.Collections.Generic.IEnumerable`1<string> values)
0xbcc461  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0xbcc466  ret
```
