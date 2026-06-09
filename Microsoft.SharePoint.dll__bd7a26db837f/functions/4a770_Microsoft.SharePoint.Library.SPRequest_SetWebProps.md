# Microsoft.SharePoint.Library.SPRequest::SetWebProps

- ea: `0x4a770`
- end: `0x4b8c9`
- name: `Microsoft.SharePoint.Library.SPRequest::SetWebProps`
- size: `4441`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x5c8310`

## callees

- `0x30b0`
- `0x4a770`
- `0x4727e0`
- `0x472800`
- `0x4729d0`
- `0x472c90`
- `0x472d60`
- `0x7b4dd0`
- `0x7c78d0`
- `0x7c89b0`
- `0x957470`

## string_xrefs

- `0x4a953`: `dtTimeCreated`
- `0x4ac9c`: `dtTimeCreated`
- `0x4afe6`: `dtTimeCreated`
- `0x4b347`: `dtTimeCreated`
- `0x4b69d`: `dtTimeCreated`
- `0x4a949`: `bUpdateTimeCreated`
- `0x4ac92`: `bUpdateTimeCreated`
- `0x4afdc`: `bUpdateTimeCreated`
- `0x4b33d`: `bUpdateTimeCreated`
- `0x4b693`: `bUpdateTimeCreated`
- `0x4a95d`: `bUpdateTimeLastModified`
- `0x4aca6`: `bUpdateTimeLastModified`
- `0x4aff0`: `bUpdateTimeLastModified`
- `0x4b351`: `bUpdateTimeLastModified`
- `0x4b6a7`: `bUpdateTimeLastModified`
- `0x4a971`: `bOverwriteMUICultures`
- `0x4acba`: `bOverwriteMUICultures`
- `0x4b004`: `bOverwriteMUICultures`
- `0x4b365`: `bOverwriteMUICultures`
- `0x4b6bb`: `bOverwriteMUICultures`

## pseudocode

```c

```

## disassembly

```asm
0x4a770  ldc.i4   0x66366C37
0x4a775  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x4a77a  ldc.i4.s 0x64
0x4a77c  ldstr    aSprequestSetwe// "SPRequest.SetWebProps"
0x4a781  ldc.i4.1
0x4a782  ldc.i4.2
0x4a783  newarr   Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x4a788  stloc.s  5
0x4a78a  ldloc.s  5
0x4a78c  ldc.i4.0
0x4a78d  ldc.i4   0x96
0x4a792  newobj   instance void Microsoft.SharePoint.Utilities.SPExecutionTimeCounter::.ctor(unsigned int32 maxValue)
0x4a797  stelem.ref
0x4a798  ldloc.s  5
0x4a79a  ldc.i4.1
0x4a79b  newobj   instance void Microsoft.SharePoint.Utilities.SPSqlQueryCounter::.ctor()
0x4a7a0  stelem.ref
0x4a7a1  ldloc.s  5
0x4a7a3  call     class [mscorlib]System.IDisposable Microsoft.SharePoint.Utilities.SPMonitoredScopeFactory::Create(unsigned int32 tagId, class Microsoft.SharePoint.Diagnostics.ULSCatBase category, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string name, valuetype SPMonitoredScopeOutputFlags flags, class Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[] monitors)
0x4a7a8  stloc.s  6
0x4a7aa  ldarg.0
0x4a7ab  dup
0x4a7ac  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x4a7b1  ldc.i4.1
0x4a7b2  add
0x4a7b3  stfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x4a7b8  ldarg.0
0x4a7b9  call     instance void Microsoft.SharePoint.Library.SPRequest::EnsureRightsPropagated()
0x4a7be  ldarg.0
0x4a7bf  ldfld    class [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass Microsoft.SharePoint.Library.SPRequest::m_SPRequest
0x4a7c4  ldarg.1
0x4a7c5  ldarg.2
0x4a7c6  ldarg.3
0x4a7c7  ldarg.s  4
0x4a7c9  ldarg.s  5
0x4a7cb  ldarg.s  6
0x4a7cd  ldarg.s  7
0x4a7cf  ldarg.s  8
0x4a7d1  ldarg.s  9
0x4a7d3  ldarg.s  0xA
0x4a7d5  ldarg.s  0xB
0x4a7d7  ldarg.s  0xC
0x4a7d9  ldarg.s  0xD
0x4a7db  ldarg.s  0xE
0x4a7dd  ldarg.s  0xF
0x4a7df  ldarg.s  0x10
0x4a7e1  ldarg.s  0x11
0x4a7e3  ldarg.s  0x12
0x4a7e5  ldarg.s  0x13
0x4a7e7  ldarg.s  0x14
0x4a7e9  ldarg.s  0x15
0x4a7eb  ldarg.s  0x16
0x4a7ed  ldarg.s  0x17
0x4a7ef  ldarg.s  0x18
0x4a7f1  ldarg.s  0x19
0x4a7f3  ldarg.s  0x1A
0x4a7f5  ldarg.s  0x1B
0x4a7f7  ldarg.s  0x1C
0x4a7f9  ldarg.s  0x1D
0x4a7fb  ldarg.s  0x1E
0x4a7fd  ldarg.s  0x1F
0x4a7ff  ldarg.s  0x20
0x4a801  ldarg.s  0x21
0x4a803  ldarg.s  0x22
0x4a805  ldarg.s  0x23
0x4a807  ldarg.s  0x24
0x4a809  ldarg.s  0x25
0x4a80b  ldarg.s  0x26
0x4a80d  ldarg.s  0x27
0x4a80f  ldarg.s  0x28
0x4a811  callvirt instance void [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass::SetWebProps(string, string, string, unsigned int32, unsigned int16, bool, int16, int16, int16, bool, int16, int16, int16, int16, int16, int32, int32, int16, unsigned int32, valuetype [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.StorePath, string, string, string, valuetype [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.StorePath, valuetype [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.StorePath, string, string, string, bool, valuetype [mscorlib]System.DateTime, bool, valuetype [mscorlib]System.DateTime, bool, bool, string, int32, int16, valuetype [mscorlib]System.Guid, int64, unsigned int32&)
0x4a816  leave    loc_4B8A9
0x4a81b  stloc.0
0x4a81c  ldstr    aSetwebprops// "SetWebProps"
0x4a821  ldarg.0
0x4a822  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x4a827  ldarg.0
0x4a828  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x4a82d  ldc.i4.s 0x27
0x4a82f  newarr   [mscorlib]System.String
0x4a834  stloc.s  7
0x4a836  ldloc.s  7
0x4a838  ldc.i4.0
0x4a839  ldstr    aBstrurl// "bstrUrl"
0x4a83e  stelem.ref
0x4a83f  ldloc.s  7
0x4a841  ldc.i4.1
0x4a842  ldstr    aBstrtitle// "bstrTitle"
0x4a847  stelem.ref
0x4a848  ldloc.s  7
0x4a84a  ldc.i4.2
0x4a84b  ldstr    aBstrdescriptio// "bstrDescription"
0x4a850  stelem.ref
0x4a851  ldloc.s  7
0x4a853  ldc.i4.3
0x4a854  ldstr    aNlocale// "nLocale"
0x4a859  stelem.ref
0x4a85a  ldloc.s  7
0x4a85c  ldc.i4.4
0x4a85d  ldstr    aNtimezone// "nTimeZone"
0x4a862  stelem.ref
0x4a863  ldloc.s  7
0x4a865  ldc.i4.5
0x4a866  ldstr    aBtime24// "bTime24"
0x4a86b  stelem.ref
0x4a86c  ldloc.s  7
0x4a86e  ldc.i4.6
0x4a86f  ldstr    aNcalendartype// "nCalendarType"
0x4a874  stelem.ref
0x4a875  ldloc.s  7
0x4a877  ldc.i4.7
0x4a878  ldstr    aNadjusthijrida// "nAdjustHijriDays"
0x4a87d  stelem.ref
0x4a87e  ldloc.s  7
0x4a880  ldc.i4.8
0x4a881  ldstr    aNaltcalendarty// "nAltCalendarType"
0x4a886  stelem.ref
0x4a887  ldloc.s  7
0x4a889  ldc.i4.s 9
0x4a88b  ldstr    aBshowweeks// "bShowWeeks"
0x4a890  stelem.ref
0x4a891  ldloc.s  7
0x4a893  ldc.i4.s 0xA
0x4a895  ldstr    aNfirstweekofye// "nFirstWeekOfYear"
0x4a89a  stelem.ref
0x4a89b  ldloc.s  7
0x4a89d  ldc.i4.s 0xB
0x4a89f  ldstr    aNfirstdayofwee// "nFirstDayOfWeek"
0x4a8a4  stelem.ref
0x4a8a5  ldloc.s  7
0x4a8a7  ldc.i4.s 0xC
0x4a8a9  ldstr    aNworkdays// "nWorkDays"
0x4a8ae  stelem.ref
0x4a8af  ldloc.s  7
0x4a8b1  ldc.i4.s 0xD
0x4a8b3  ldstr    aNworkdaystarth// "nWorkDayStartHour"
0x4a8b8  stelem.ref
0x4a8b9  ldloc.s  7
0x4a8bb  ldc.i4.s 0xE
0x4a8bd  ldstr    aNworkdayendhou// "nWorkDayEndHour"
0x4a8c2  stelem.ref
0x4a8c3  ldloc.s  7
0x4a8c5  ldc.i4.s 0xF
0x4a8c7  ldstr    aLflags// "lFlags"
0x4a8cc  stelem.ref
0x4a8cd  ldloc.s  7
0x4a8cf  ldc.i4.s 0x10
0x4a8d1  ldstr    aLdontignorefla// "lDontIgnoreFlagsMask"
0x4a8d6  stelem.ref
0x4a8d7  ldloc.s  7
0x4a8d9  ldc.i4.s 0x11
0x4a8db  ldstr    aNcollation// "nCollation"
0x4a8e0  stelem.ref
0x4a8e1  ldloc.s  7
0x4a8e3  ldc.i4.s 0x12
0x4a8e5  ldstr    aNauthor// "nAuthor"
0x4a8ea  stelem.ref
0x4a8eb  ldloc.s  7
0x4a8ed  ldc.i4.s 0x13
0x4a8ef  ldstr    aSpthemedcssfol// "spThemedCssFolderUrl"
0x4a8f4  stelem.ref
0x4a8f5  ldloc.s  7
0x4a8f7  ldc.i4.s 0x14
0x4a8f9  ldstr    aBstrcustomized// "bstrCustomizedCssFileList"
0x4a8fe  stelem.ref
0x4a8ff  ldloc.s  7
0x4a901  ldc.i4.s 0x15
0x4a903  ldstr    aBstralternatec// "bstrAlternateCssUrl"
0x4a908  stelem.ref
0x4a909  ldloc.s  7
0x4a90b  ldc.i4.s 0x16
0x4a90d  ldstr    aBstralternateh// "bstrAlternateHeaderUrl"
0x4a912  stelem.ref
0x4a913  ldloc.s  7
0x4a915  ldc.i4.s 0x17
0x4a917  ldstr    aSpmasterurl// "spMasterUrl"
0x4a91c  stelem.ref
0x4a91d  ldloc.s  7
0x4a91f  ldc.i4.s 0x18
0x4a921  ldstr    aSpcustommaster// "spCustomMasterUrl"
0x4a926  stelem.ref
0x4a927  ldloc.s  7
0x4a929  ldc.i4.s 0x19
0x4a92b  ldstr    aBstrcustomjsur// "bstrCustomJSUrl"
0x4a930  stelem.ref
0x4a931  ldloc.s  7
0x4a933  ldc.i4.s 0x1A
0x4a935  ldstr    aBstrsitelogour// "bstrSiteLogoUrl"
0x4a93a  stelem.ref
0x4a93b  ldloc.s  7
0x4a93d  ldc.i4.s 0x1B
0x4a93f  ldstr    aBstrsitelogode// "bstrSiteLogoDescription"
0x4a944  stelem.ref
0x4a945  ldloc.s  7
0x4a947  ldc.i4.s 0x1C
0x4a949  ldstr    aBupdatetimecre// "bUpdateTimeCreated"
0x4a94e  stelem.ref
0x4a94f  ldloc.s  7
0x4a951  ldc.i4.s 0x1D
0x4a953  ldstr    aDttimecreated// "dtTimeCreated"
0x4a958  stelem.ref
0x4a959  ldloc.s  7
0x4a95b  ldc.i4.s 0x1E
0x4a95d  ldstr    aBupdatetimelas// "bUpdateTimeLastModified"
0x4a962  stelem.ref
0x4a963  ldloc.s  7
0x4a965  ldc.i4.s 0x1F
0x4a967  ldstr    aDttimelastmodi// "dtTimeLastModified"
0x4a96c  stelem.ref
0x4a96d  ldloc.s  7
0x4a96f  ldc.i4.s 0x20
0x4a971  ldstr    aBoverwritemuic// "bOverwriteMUICultures"
0x4a976  stelem.ref
0x4a977  ldloc.s  7
0x4a979  ldc.i4.s 0x21
0x4a97b  ldstr    aBmuienabled// "bMUIEnabled"
0x4a980  stelem.ref
0x4a981  ldloc.s  7
0x4a983  ldc.i4.s 0x22
0x4a985  ldstr    aBstralternatem// "bstrAlternateMUICultures"
0x4a98a  stelem.ref
0x4a98b  ldloc.s  7
0x4a98d  ldc.i4.s 0x23
0x4a98f  ldstr    aUiversion// "uiVersion"
0x4a994  stelem.ref
0x4a995  ldloc.s  7
0x4a997  ldc.i4.s 0x24
0x4a999  ldstr    aNclienttag// "nClientTag"
0x4a99e  stelem.ref
0x4a99f  ldloc.s  7
0x4a9a1  ldc.i4.s 0x25
0x4a9a3  ldstr    aGuiddesignpack// "guidDesignPackage"
0x4a9a8  stelem.ref
0x4a9a9  ldloc.s  7
0x4a9ab  ldc.i4.s 0x26
0x4a9ad  ldstr    aLlflags2// "llFlags2"
0x4a9b2  stelem.ref
0x4a9b3  ldloc.s  7
0x4a9b5  ldc.i4.s 0x27
0x4a9b7  newarr   [mscorlib]System.Object
0x4a9bc  stloc.s  8
0x4a9be  ldloc.s  8
0x4a9c0  ldc.i4.0
0x4a9c1  ldarg.1
0x4a9c2  stelem.ref
0x4a9c3  ldloc.s  8
0x4a9c5  ldc.i4.1
0x4a9c6  ldarg.2
0x4a9c7  stelem.ref
0x4a9c8  ldloc.s  8
0x4a9ca  ldc.i4.2
0x4a9cb  ldarg.3
0x4a9cc  stelem.ref
0x4a9cd  ldloc.s  8
0x4a9cf  ldc.i4.3
0x4a9d0  ldarg.s  4
0x4a9d2  box      [mscorlib]System.UInt32
0x4a9d7  stelem.ref
0x4a9d8  ldloc.s  8
0x4a9da  ldc.i4.4
0x4a9db  ldarg.s  5
0x4a9dd  box      [mscorlib]System.UInt16
0x4a9e2  stelem.ref
0x4a9e3  ldloc.s  8
0x4a9e5  ldc.i4.5
0x4a9e6  ldarg.s  6
0x4a9e8  box      [mscorlib]System.Boolean
0x4a9ed  stelem.ref
0x4a9ee  ldloc.s  8
0x4a9f0  ldc.i4.6
0x4a9f1  ldarg.s  7
0x4a9f3  box      [mscorlib]System.Int16
0x4a9f8  stelem.ref
0x4a9f9  ldloc.s  8
0x4a9fb  ldc.i4.7
0x4a9fc  ldarg.s  8
0x4a9fe  box      [mscorlib]System.Int16
0x4aa03  stelem.ref
0x4aa04  ldloc.s  8
0x4aa06  ldc.i4.8
0x4aa07  ldarg.s  9
0x4aa09  box      [mscorlib]System.Int16
0x4aa0e  stelem.ref
0x4aa0f  ldloc.s  8
0x4aa11  ldc.i4.s 9
0x4aa13  ldarg.s  0xA
0x4aa15  box      [mscorlib]System.Boolean
0x4aa1a  stelem.ref
0x4aa1b  ldloc.s  8
0x4aa1d  ldc.i4.s 0xA
0x4aa1f  ldarg.s  0xB
0x4aa21  box      [mscorlib]System.Int16
0x4aa26  stelem.ref
0x4aa27  ldloc.s  8
0x4aa29  ldc.i4.s 0xB
0x4aa2b  ldarg.s  0xC
0x4aa2d  box      [mscorlib]System.Int16
0x4aa32  stelem.ref
0x4aa33  ldloc.s  8
0x4aa35  ldc.i4.s 0xC
  ... truncated ...
```
