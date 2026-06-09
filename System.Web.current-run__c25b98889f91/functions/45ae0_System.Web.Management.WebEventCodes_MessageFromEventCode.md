# System.Web.Management.WebEventCodes::MessageFromEventCode

- ea: `0x45ae0`
- end: `0x45eec`
- name: `System.Web.Management.WebEventCodes::MessageFromEventCode`
- size: `1036`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x46ec0`

## callees

- `0x45ae0`
- `0x47000`

## string_xrefs

- `0x45b96`: `Webevent_detail_ApplicationShutdownConfigurationChange`
- `0x45bb6`: `Webevent_detail_ApplicationShutdownChangeInSecurityPolicyFile`
- `0x45bc6`: `Webevent_detail_ApplicationShutdownBinDirChangeOrDirectoryRename`
- `0x45bd6`: `Webevent_detail_ApplicationShutdownBrowsersDirChangeOrDirectoryRename`
- `0x45be6`: `Webevent_detail_ApplicationShutdownCodeDirChangeOrDirectoryRename`
- `0x45bf6`: `Webevent_detail_ApplicationShutdownResourcesDirChangeOrDirectoryRename`
- `0x45c16`: `Webevent_detail_ApplicationShutdownPhysicalApplicationPathChanged`
- `0x45c40`: `Webevent_detail_ApplicationShutdownMaxRecompilationsReached`
- `0x45d72`: `Webevent_msg_ApplicationCompilationStart`
- `0x45d82`: `Webevent_msg_ApplicationCompilationEnd`
- `0x45da2`: `Webevent_msg_RequestTransactionComplete`
- `0x45e22`: `Webevent_msg_WebErrorCompilationError`
- `0x45e32`: `Webevent_msg_WebErrorConfigurationError`
- `0x45e42`: `Webevent_msg_AuditUnhandledSecurityException`
- `0x45ec7`: `Webevent_msg_AuditUnhandledAccessException`

## pseudocode

```c

```

## disassembly

```asm
0x45ae0  ldnull
0x45ae1  stloc.0
0x45ae2  ldnull
0x45ae3  stloc.1
0x45ae4  ldarg.1
0x45ae5  brfalse  loc_45CA6
0x45aea  ldarg.1
0x45aeb  ldc.i4   0xC351
0x45af0  sub
0x45af1  switch   loc_45B66, loc_45B76, loc_45B86, loc_45B96, loc_45BA6, loc_45BB6, loc_45BC6, loc_45BD6, loc_45BE6, loc_45BF6, loc_45C06, loc_45C16, loc_45C26, loc_45C33, loc_45C40, loc_45C5A, loc_45C4D
0x45b3a  ldarg.1
0x45b3b  ldc.i4   0xC419
0x45b40  sub
0x45b41  switch   loc_45C67, loc_45C74, loc_45C81, loc_45C8E
0x45b56  ldarg.1
0x45b57  ldc.i4   0xC47D
0x45b5c  beq      loc_45C9B
0x45b61  br       loc_45CA6
0x45b66  ldstr    aWebeventDetail// "Webevent_detail_ApplicationShutdownUnkn"...
0x45b6b  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x45b70  stloc.1
0x45b71  br       loc_45CA6
0x45b76  ldstr    aWebeventDetail_0// "Webevent_detail_ApplicationShutdownHost"...
0x45b7b  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x45b80  stloc.1
0x45b81  br       loc_45CA6
0x45b86  ldstr    aWebeventDetail_1// "Webevent_detail_ApplicationShutdownChan"...
0x45b8b  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x45b90  stloc.1
0x45b91  br       loc_45CA6
0x45b96  ldstr    aWebeventDetail_2// "Webevent_detail_ApplicationShutdownConf"...
0x45b9b  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x45ba0  stloc.1
0x45ba1  br       loc_45CA6
0x45ba6  ldstr    aWebeventDetail_3// "Webevent_detail_ApplicationShutdownUnlo"...
0x45bab  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x45bb0  stloc.1
0x45bb1  br       loc_45CA6
0x45bb6  ldstr    aWebeventDetail_4// "Webevent_detail_ApplicationShutdownChan"...
0x45bbb  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x45bc0  stloc.1
0x45bc1  br       loc_45CA6
0x45bc6  ldstr    aWebeventDetail_5// "Webevent_detail_ApplicationShutdownBinD"...
0x45bcb  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x45bd0  stloc.1
0x45bd1  br       loc_45CA6
0x45bd6  ldstr    aWebeventDetail_6// "Webevent_detail_ApplicationShutdownBrow"...
0x45bdb  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x45be0  stloc.1
0x45be1  br       loc_45CA6
0x45be6  ldstr    aWebeventDetail_7// "Webevent_detail_ApplicationShutdownCode"...
0x45beb  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x45bf0  stloc.1
0x45bf1  br       loc_45CA6
0x45bf6  ldstr    aWebeventDetail_8// "Webevent_detail_ApplicationShutdownReso"...
0x45bfb  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x45c00  stloc.1
0x45c01  br       loc_45CA6
0x45c06  ldstr    aWebeventDetail_9// "Webevent_detail_ApplicationShutdownIdle"...
0x45c0b  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x45c10  stloc.1
0x45c11  br       loc_45CA6
0x45c16  ldstr    aWebeventDetail_10// "Webevent_detail_ApplicationShutdownPhys"...
0x45c1b  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x45c20  stloc.1
0x45c21  br       loc_45CA6
0x45c26  ldstr    aWebeventDetail_11// "Webevent_detail_ApplicationShutdownHttp"...
0x45c2b  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x45c30  stloc.1
0x45c31  br.s     loc_45CA6
0x45c33  ldstr    aWebeventDetail_12// "Webevent_detail_ApplicationShutdownInit"...
0x45c38  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x45c3d  stloc.1
0x45c3e  br.s     loc_45CA6
0x45c40  ldstr    aWebeventDetail_13// "Webevent_detail_ApplicationShutdownMaxR"...
0x45c45  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x45c4a  stloc.1
0x45c4b  br.s     loc_45CA6
0x45c4d  ldstr    aWebeventDetail_14// "Webevent_detail_ApplicationShutdownBuil"...
0x45c52  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x45c57  stloc.1
0x45c58  br.s     loc_45CA6
0x45c5a  ldstr    aWebeventDetail_15// "Webevent_detail_StateServerConnectionEr"...
0x45c5f  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x45c64  stloc.1
0x45c65  br.s     loc_45CA6
0x45c67  ldstr    aWebeventDetail_16// "Webevent_detail_InvalidTicketFailure"
0x45c6c  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x45c71  stloc.1
0x45c72  br.s     loc_45CA6
0x45c74  ldstr    aWebeventDetail_17// "Webevent_detail_ExpiredTicketFailure"
0x45c79  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x45c7e  stloc.1
0x45c7f  br.s     loc_45CA6
0x45c81  ldstr    aWebeventDetail_18// "Webevent_detail_InvalidViewStateMac"
0x45c86  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x45c8b  stloc.1
0x45c8c  br.s     loc_45CA6
0x45c8e  ldstr    aWebeventDetail_19// "Webevent_detail_InvalidViewState"
0x45c93  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x45c98  stloc.1
0x45c99  br.s     loc_45CA6
0x45c9b  ldstr    aWebeventDetail_20// "Webevent_detail_SqlProviderEventsDroppe"...
0x45ca0  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x45ca5  stloc.1
0x45ca6  ldarg.0
0x45ca7  ldc.i4   0x7D1
0x45cac  bgt.s    loc_45CDE
0x45cae  ldarg.0
0x45caf  ldc.i4   0x3E9
0x45cb4  sub
0x45cb5  switch   loc_45D52, loc_45D62, loc_45D72, loc_45D82, loc_45D92
0x45cce  ldarg.0
0x45ccf  ldc.i4   0x7D1
0x45cd4  beq      loc_45DA2
0x45cd9  br       loc_45ED4
0x45cde  ldarg.0
0x45cdf  ldc.i4   0x7D2
0x45ce4  beq      loc_45DB2
0x45ce9  ldarg.0
0x45cea  ldc.i4   0xBB9
0x45cef  sub
0x45cf0  switch   loc_45DC2, loc_45DD2, loc_45DE2, loc_45DF2, loc_45E02, loc_45E12, loc_45E22, loc_45E32
0x45d15  ldarg.0
0x45d16  ldc.i4   0xFA1
0x45d1b  sub
0x45d1c  switch   loc_45E5F, loc_45EA0, loc_45E6C, loc_45E93, loc_45E86, loc_45EAD, loc_45EBA, loc_45E79, loc_45E52, loc_45E42, loc_45EC7
0x45d4d  br       loc_45ED4
0x45d52  ldstr    aWebeventMsgApp// "Webevent_msg_ApplicationStart"
0x45d57  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x45d5c  stloc.0
0x45d5d  br       loc_45EDA
0x45d62  ldstr    aWebeventMsgApp_0// "Webevent_msg_ApplicationShutdown"
0x45d67  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x45d6c  stloc.0
0x45d6d  br       loc_45EDA
0x45d72  ldstr    aWebeventMsgApp_1// "Webevent_msg_ApplicationCompilationStar"...
0x45d77  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x45d7c  stloc.0
0x45d7d  br       loc_45EDA
0x45d82  ldstr    aWebeventMsgApp_2// "Webevent_msg_ApplicationCompilationEnd"
0x45d87  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x45d8c  stloc.0
0x45d8d  br       loc_45EDA
0x45d92  ldstr    aWebeventMsgApp_3// "Webevent_msg_ApplicationHeartbeat"
0x45d97  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x45d9c  stloc.0
0x45d9d  br       loc_45EDA
0x45da2  ldstr    aWebeventMsgReq// "Webevent_msg_RequestTransactionComplete"
0x45da7  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x45dac  stloc.0
0x45dad  br       loc_45EDA
0x45db2  ldstr    aWebeventMsgReq_0// "Webevent_msg_RequestTransactionAbort"
0x45db7  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x45dbc  stloc.0
0x45dbd  br       loc_45EDA
0x45dc2  ldstr    aWebeventMsgRun// "Webevent_msg_RuntimeErrorRequestAbort"
0x45dc7  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x45dcc  stloc.0
0x45dcd  br       loc_45EDA
0x45dd2  ldstr    aWebeventMsgRun_0// "Webevent_msg_RuntimeErrorViewStateFailu"...
0x45dd7  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x45ddc  stloc.0
0x45ddd  br       loc_45EDA
0x45de2  ldstr    aWebeventMsgRun_1// "Webevent_msg_RuntimeErrorValidationFail"...
0x45de7  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x45dec  stloc.0
0x45ded  br       loc_45EDA
0x45df2  ldstr    aWebeventMsgRun_2// "Webevent_msg_RuntimeErrorPostTooLarge"
0x45df7  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x45dfc  stloc.0
0x45dfd  br       loc_45EDA
0x45e02  ldstr    aWebeventMsgRun_3// "Webevent_msg_RuntimeErrorUnhandledExcep"...
0x45e07  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x45e0c  stloc.0
0x45e0d  br       loc_45EDA
0x45e12  ldstr    aWebeventMsgWeb// "Webevent_msg_WebErrorParserError"
0x45e17  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x45e1c  stloc.0
0x45e1d  br       loc_45EDA
0x45e22  ldstr    aWebeventMsgWeb_0// "Webevent_msg_WebErrorCompilationError"
0x45e27  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x45e2c  stloc.0
0x45e2d  br       loc_45EDA
0x45e32  ldstr    aWebeventMsgWeb_1// "Webevent_msg_WebErrorConfigurationError"
0x45e37  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x45e3c  stloc.0
0x45e3d  br       loc_45EDA
0x45e42  ldstr    aWebeventMsgAud// "Webevent_msg_AuditUnhandledSecurityExce"...
0x45e47  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x45e4c  stloc.0
0x45e4d  br       loc_45EDA
0x45e52  ldstr    aWebeventMsgAud_0// "Webevent_msg_AuditInvalidViewStateFailu"...
0x45e57  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x45e5c  stloc.0
0x45e5d  br.s     loc_45EDA
0x45e5f  ldstr    aWebeventMsgAud_1// "Webevent_msg_AuditFormsAuthenticationSu"...
0x45e64  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x45e69  stloc.0
0x45e6a  br.s     loc_45EDA
0x45e6c  ldstr    aWebeventMsgAud_2// "Webevent_msg_AuditUrlAuthorizationSucce"...
0x45e71  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x45e76  stloc.0
0x45e77  br.s     loc_45EDA
0x45e79  ldstr    aWebeventMsgAud_3// "Webevent_msg_AuditFileAuthorizationFail"...
0x45e7e  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x45e83  stloc.0
0x45e84  br.s     loc_45EDA
0x45e86  ldstr    aWebeventMsgAud_4// "Webevent_msg_AuditFormsAuthenticationFa"...
0x45e8b  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x45e90  stloc.0
0x45e91  br.s     loc_45EDA
0x45e93  ldstr    aWebeventMsgAud_5// "Webevent_msg_AuditFileAuthorizationSucc"...
0x45e98  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x45e9d  stloc.0
0x45e9e  br.s     loc_45EDA
0x45ea0  ldstr    aWebeventMsgAud_6// "Webevent_msg_AuditMembershipAuthenticat"...
0x45ea5  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x45eaa  stloc.0
0x45eab  br.s     loc_45EDA
0x45ead  ldstr    aWebeventMsgAud_7// "Webevent_msg_AuditMembershipAuthenticat"...
0x45eb2  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x45eb7  stloc.0
0x45eb8  br.s     loc_45EDA
0x45eba  ldstr    aWebeventMsgAud_8// "Webevent_msg_AuditUrlAuthorizationFailu"...
0x45ebf  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x45ec4  stloc.0
0x45ec5  br.s     loc_45EDA
0x45ec7  ldstr    aWebeventMsgAud_9// "Webevent_msg_AuditUnhandledAccessExcept"...
0x45ecc  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x45ed1  stloc.0
0x45ed2  br.s     loc_45EDA
0x45ed4  ldsfld   string [mscorlib]System.String::Empty
0x45ed9  ret
0x45eda  ldloc.1
0x45edb  brfalse.s loc_45EEA
0x45edd  ldloc.0
0x45ede  ldstr    asc_1B0CBE// " "
0x45ee3  ldloc.1
0x45ee4  call     string [mscorlib]System.String::Concat(string, string, string)
0x45ee9  stloc.0
0x45eea  ldloc.0
0x45eeb  ret
```
