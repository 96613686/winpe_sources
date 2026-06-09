# System.Web.Configuration.BrowserCapabilitiesFactory::DefaultProcess

- ea: `0x135a20`
- end: `0x136136`
- name: `System.Web.Configuration.BrowserCapabilitiesFactory::DefaultProcess`
- size: `1814`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1348d0`

## callees

- `0x135060`
- `0x135270`
- `0x135a00`
- `0x135a10`
- `0x135a20`
- `0x136440`
- `0x1364c0`
- `0x136bb0`
- `0x136d20`
- `0x136df0`
- `0x137de0`
- `0x145890`
- `0x147670`

## string_xrefs

- `0x136058`: `tagwriter`
- `0x135e98`: `supportsAccesskeyAttribute`
- `0x135a78`: `canCombineFormsInDeck`
- `0x135e38`: `requiresUniqueFilePathSuffix`
- `0x135ed8`: `supportsCacheControlMetaTag`
- `0x13605d`: `System.Web.UI.Html32TextWriter`

## pseudocode

```c

```

## disassembly

```asm
0x135a20  ldarg.2
0x135a21  callvirt instance class [mscorlib]System.Collections.IDictionary System.Web.Configuration.HttpCapabilitiesBase::get_Capabilities()
0x135a26  stloc.0
0x135a27  ldloc.0
0x135a28  ldstr    aActivexcontrol// "activexcontrols"
0x135a2d  ldstr    aFalse// "false"
0x135a32  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135a37  ldloc.0
0x135a38  ldstr    aAol// "aol"
0x135a3d  ldstr    aFalse// "false"
0x135a42  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135a47  ldloc.0
0x135a48  ldstr    aBackgroundsoun// "backgroundsounds"
0x135a4d  ldstr    aFalse// "false"
0x135a52  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135a57  ldloc.0
0x135a58  ldstr    aBeta_0// "beta"
0x135a5d  ldstr    aFalse// "false"
0x135a62  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135a67  ldloc.0
0x135a68  ldstr    aBrowser// "browser"
0x135a6d  ldstr    aUnknown// "Unknown"
0x135a72  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135a77  ldloc.0
0x135a78  ldstr    aCancombineform// "canCombineFormsInDeck"
0x135a7d  ldstr    aTrue// "true"
0x135a82  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135a87  ldloc.0
0x135a88  ldstr    aCaninitiatevoi// "canInitiateVoiceCall"
0x135a8d  ldstr    aFalse// "false"
0x135a92  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135a97  ldloc.0
0x135a98  ldstr    aCanrenderafter// "canRenderAfterInputOrSelectElement"
0x135a9d  ldstr    aTrue// "true"
0x135aa2  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135aa7  ldloc.0
0x135aa8  ldstr    aCanrenderempty// "canRenderEmptySelects"
0x135aad  ldstr    aTrue// "true"
0x135ab2  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135ab7  ldloc.0
0x135ab8  ldstr    aCanrenderinput// "canRenderInputAndSelectElementsTogether"
0x135abd  ldstr    aTrue// "true"
0x135ac2  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135ac7  ldloc.0
0x135ac8  ldstr    aCanrendermixed// "canRenderMixedSelects"
0x135acd  ldstr    aTrue// "true"
0x135ad2  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135ad7  ldloc.0
0x135ad8  ldstr    aCanrenderoneve// "canRenderOneventAndPrevElementsTogether"
0x135add  ldstr    aTrue// "true"
0x135ae2  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135ae7  ldloc.0
0x135ae8  ldstr    aCanrenderpostb// "canRenderPostBackCards"
0x135aed  ldstr    aTrue// "true"
0x135af2  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135af7  ldloc.0
0x135af8  ldstr    aCanrendersetva// "canRenderSetvarZeroWithMultiSelectionLi"...
0x135afd  ldstr    aTrue// "true"
0x135b02  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135b07  ldloc.0
0x135b08  ldstr    aCansendmail// "canSendMail"
0x135b0d  ldstr    aTrue// "true"
0x135b12  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135b17  ldloc.0
0x135b18  ldstr    aCdf// "cdf"
0x135b1d  ldstr    aFalse// "false"
0x135b22  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135b27  ldloc.0
0x135b28  ldstr    aCookies// "cookies"
0x135b2d  ldstr    aTrue// "true"
0x135b32  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135b37  ldloc.0
0x135b38  ldstr    aCrawler// "crawler"
0x135b3d  ldstr    aFalse// "false"
0x135b42  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135b47  ldloc.0
0x135b48  ldstr    aDefaultsubmitb// "defaultSubmitButtonLimit"
0x135b4d  ldstr    a1_0// "1"
0x135b52  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135b57  ldloc.0
0x135b58  ldstr    aEcmascriptvers// "ecmascriptversion"
0x135b5d  ldstr    a00_1// "0.0"
0x135b62  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135b67  ldloc.0
0x135b68  ldstr    aFrames// "frames"
0x135b6d  ldstr    aFalse// "false"
0x135b72  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135b77  ldloc.0
0x135b78  ldstr    aGatewaymajorve// "gatewayMajorVersion"
0x135b7d  ldstr    a0// "0"
0x135b82  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135b87  ldloc.0
0x135b88  ldstr    aGatewayminorve// "gatewayMinorVersion"
0x135b8d  ldstr    a0// "0"
0x135b92  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135b97  ldloc.0
0x135b98  ldstr    aGatewayversion// "gatewayVersion"
0x135b9d  ldstr    aNone_0// "None"
0x135ba2  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135ba7  ldloc.0
0x135ba8  ldstr    aHasbackbutton// "hasBackButton"
0x135bad  ldstr    aTrue// "true"
0x135bb2  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135bb7  ldloc.0
0x135bb8  ldstr    aHidesrightalig// "hidesRightAlignedMultiselectScrollbars"
0x135bbd  ldstr    aFalse// "false"
0x135bc2  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135bc7  ldloc.0
0x135bc8  ldstr    aInputtype// "inputType"
0x135bcd  ldstr    aTelephonekeypa// "telephoneKeypad"
0x135bd2  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135bd7  ldloc.0
0x135bd8  ldstr    aIscolor// "isColor"
0x135bdd  ldstr    aFalse// "false"
0x135be2  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135be7  ldloc.0
0x135be8  ldstr    aIsmobiledevice// "isMobileDevice"
0x135bed  ldstr    aFalse// "false"
0x135bf2  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135bf7  ldloc.0
0x135bf8  ldstr    aJavaapplets// "javaapplets"
0x135bfd  ldstr    aFalse// "false"
0x135c02  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135c07  ldloc.0
0x135c08  ldstr    aJavascript_0// "javascript"
0x135c0d  ldstr    aFalse// "false"
0x135c12  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135c17  ldloc.0
0x135c18  ldstr    aJscriptversion// "jscriptversion"
0x135c1d  ldstr    a00_1// "0.0"
0x135c22  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135c27  ldloc.0
0x135c28  ldstr    aMajorversion// "majorversion"
0x135c2d  ldstr    a0// "0"
0x135c32  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135c37  ldloc.0
0x135c38  ldstr    aMaximumhreflen// "maximumHrefLength"
0x135c3d  ldstr    a10000// "10000"
0x135c42  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135c47  ldloc.0
0x135c48  ldstr    aMaximumrendere// "maximumRenderedPageSize"
0x135c4d  ldstr    a2000// "2000"
0x135c52  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135c57  ldloc.0
0x135c58  ldstr    aMaximumsoftkey// "maximumSoftkeyLabelLength"
0x135c5d  ldstr    a5// "5"
0x135c62  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135c67  ldloc.0
0x135c68  ldstr    aMinorversion// "minorversion"
0x135c6d  ldstr    a0// "0"
0x135c72  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135c77  ldloc.0
0x135c78  ldstr    aMobiledevicema// "mobileDeviceManufacturer"
0x135c7d  ldstr    aUnknown// "Unknown"
0x135c82  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135c87  ldloc.0
0x135c88  ldstr    aMobiledevicemo// "mobileDeviceModel"
0x135c8d  ldstr    aUnknown// "Unknown"
0x135c92  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135c97  ldloc.0
0x135c98  ldstr    aMsdomversion// "msdomversion"
0x135c9d  ldstr    a00_1// "0.0"
0x135ca2  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135ca7  ldloc.0
0x135ca8  ldstr    aNumberofsoftke// "numberOfSoftkeys"
0x135cad  ldstr    a0// "0"
0x135cb2  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135cb7  ldloc.0
0x135cb8  ldstr    aPlatform// "platform"
0x135cbd  ldstr    aUnknown// "Unknown"
0x135cc2  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135cc7  ldloc.0
0x135cc8  ldstr    aPreferredimage// "preferredImageMime"
0x135ccd  ldstr    aImageGif// "image/gif"
0x135cd2  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135cd7  ldloc.0
0x135cd8  ldstr    aPreferredrende_0// "preferredRenderingMime"
0x135cdd  ldstr    aTextHtml// "text/html"
0x135ce2  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135ce7  ldloc.0
0x135ce8  ldstr    aPreferredrende// "preferredRenderingType"
0x135ced  ldstr    aHtml32// "html32"
0x135cf2  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135cf7  ldloc.0
0x135cf8  ldstr    aRendersbreakbe// "rendersBreakBeforeWmlSelectAndInput"
0x135cfd  ldstr    aFalse// "false"
0x135d02  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135d07  ldloc.0
0x135d08  ldstr    aRendersbreaksa// "rendersBreaksAfterHtmlLists"
0x135d0d  ldstr    aTrue// "true"
0x135d12  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135d17  ldloc.0
0x135d18  ldstr    aRendersbreaksa_0// "rendersBreaksAfterWmlAnchor"
0x135d1d  ldstr    aFalse// "false"
0x135d22  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135d27  ldloc.0
0x135d28  ldstr    aRendersbreaksa_1// "rendersBreaksAfterWmlInput"
0x135d2d  ldstr    aFalse// "false"
0x135d32  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135d37  ldloc.0
0x135d38  ldstr    aRenderswmldoac// "rendersWmlDoAcceptsInline"
0x135d3d  ldstr    aTrue// "true"
0x135d42  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135d47  ldloc.0
0x135d48  ldstr    aRenderswmlsele// "rendersWmlSelectsAsMenuCards"
0x135d4d  ldstr    aFalse// "false"
0x135d52  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135d57  ldloc.0
0x135d58  ldstr    aRequiredmetata// "requiredMetaTagNameValue"
0x135d5d  ldstr    asc_1B98A4// ""
0x135d62  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135d67  ldloc.0
0x135d68  ldstr    aRequiresabsolu// "requiresAbsolutePostbackUrl"
0x135d6d  ldstr    aFalse// "false"
0x135d72  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135d77  ldloc.0
0x135d78  ldstr    aRequiresadapti// "requiresAdaptiveErrorReporting"
0x135d7d  ldstr    aFalse// "false"
0x135d82  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135d87  ldloc.0
0x135d88  ldstr    aRequiresattrib// "requiresAttributeColonSubstitution"
0x135d8d  ldstr    aFalse// "false"
0x135d92  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135d97  ldloc.0
0x135d98  ldstr    aRequiresconten// "requiresContentTypeMetaTag"
0x135d9d  ldstr    aFalse// "false"
0x135da2  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135da7  ldloc.0
0x135da8  ldstr    aRequirescontro// "requiresControlStateInSession"
0x135dad  ldstr    aFalse// "false"
0x135db2  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135db7  ldloc.0
0x135db8  ldstr    aRequiresdbcsch// "requiresDBCSCharacter"
0x135dbd  ldstr    aFalse// "false"
0x135dc2  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135dc7  ldloc.0
0x135dc8  ldstr    aRequiresfullyq// "requiresFullyQualifiedRedirectUrl"
0x135dcd  ldstr    aFalse// "false"
0x135dd2  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135dd7  ldloc.0
0x135dd8  ldstr    aRequiresleadin// "requiresLeadingPageBreak"
0x135ddd  ldstr    aFalse// "false"
0x135de2  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135de7  ldloc.0
0x135de8  ldstr    aRequiresnobrea// "requiresNoBreakInFormatting"
0x135ded  ldstr    aFalse// "false"
0x135df2  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135df7  ldloc.0
0x135df8  ldstr    aRequiresoutput// "requiresOutputOptimization"
0x135dfd  ldstr    aFalse// "false"
0x135e02  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135e07  ldloc.0
0x135e08  ldstr    aRequiresphonen// "requiresPhoneNumbersAsPlainText"
0x135e0d  ldstr    aFalse// "false"
0x135e12  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135e17  ldloc.0
0x135e18  ldstr    aRequirespostre// "requiresPostRedirectionHandling"
0x135e1d  ldstr    aFalse// "false"
0x135e22  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135e27  ldloc.0
0x135e28  ldstr    aRequiresspecia// "requiresSpecialViewStateEncoding"
0x135e2d  ldstr    aFalse// "false"
0x135e32  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135e37  ldloc.0
0x135e38  ldstr    aRequiresunique_0// "requiresUniqueFilePathSuffix"
0x135e3d  ldstr    aFalse// "false"
0x135e42  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135e47  ldloc.0
0x135e48  ldstr    aRequiresunique_1// "requiresUniqueHtmlCheckboxNames"
0x135e4d  ldstr    aFalse// "false"
0x135e52  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135e57  ldloc.0
0x135e58  ldstr    aRequiresunique_2// "requiresUniqueHtmlInputNames"
0x135e5d  ldstr    aFalse// "false"
0x135e62  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135e67  ldloc.0
0x135e68  ldstr    aRequiresurlenc// "requiresUrlEncodedPostfieldValues"
0x135e6d  ldstr    aFalse// "false"
0x135e72  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135e77  ldloc.0
0x135e78  ldstr    aRequiresxhtmlc// "requiresXhtmlCssSuppression"
0x135e7d  ldstr    aFalse// "false"
0x135e82  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135e87  ldloc.0
0x135e88  ldstr    aScreenbitdepth// "screenBitDepth"
0x135e8d  ldstr    a1_0// "1"
0x135e92  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135e97  ldloc.0
0x135e98  ldstr    aSupportsaccess_0// "supportsAccesskeyAttribute"
0x135e9d  ldstr    aFalse// "false"
0x135ea2  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135ea7  ldloc.0
0x135ea8  ldstr    aSupportsbodyco// "supportsBodyColor"
0x135ead  ldstr    aTrue// "true"
0x135eb2  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135eb7  ldloc.0
0x135eb8  ldstr    aSupportsbold// "supportsBold"
0x135ebd  ldstr    aFalse// "false"
0x135ec2  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x135ec7  ldloc.0
  ... truncated ...
```
