# Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::ParseSetting

- ea: `0x77e0`
- end: `0x7d14`
- name: `Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::ParseSetting`
- size: `1332`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x7390`

## callees

- `0x1710`
- `0x17c0`
- `0x17d0`
- `0x1820`
- `0x77e0`
- `0x100d0`

## string_xrefs

- `0x7a0b`: `ProcessTimeoutGcExtension`
- `0x7ac8`: `AlertingDataCleanupMinutes`
- `0x7b85`: `DisplayErrorLink`
- `0x7baf`: `WebServiceUseFileShareStorage`
- `0x7bd9`: `UsernameSIDRefreshMinutes`
- `0x7bc4`: `RequestCacheSlots`

## pseudocode

```c

```

## disassembly

```asm
0x77e0  ldarg.0
0x77e1  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x77e6  ldstr    aKey// "Key"
0x77eb  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x77f0  ldarg.0
0x77f1  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x77f6  ldstr    aValue// "Value"
0x77fb  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x7800  stloc.0
0x7801  dup
0x7802  brfalse.s loc_7807
0x7804  ldloc.0
0x7805  brtrue.s loc_7812
0x7807  call     string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Exceptions.ErrorStrings::get_InvalidKeyValue()
0x780c  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x7811  pop
0x7812  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x7817  stloc.1
0x7818  ldc.i4.0
0x7819  stloc.2
0x781a  ldloc.1
0x781b  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x7820  stloc.3
0x7821  ldloc.3
0x7822  ldc.i4   0x90FF0D74
0x7827  bgt.un   loc_78F4
0x782c  ldloc.3
0x782d  ldc.i4   0x54DDED13
0x7832  bgt.un.s loc_7888
0x7834  ldloc.3
0x7835  ldc.i4   0x4BB5C879
0x783a  bgt.un.s loc_7862
0x783c  ldloc.3
0x783d  ldc.i4   0x403E80C0
0x7842  beq      loc_7B30
0x7847  ldloc.3
0x7848  ldc.i4   0x4472E528
0x784d  beq      loc_7A5E
0x7852  ldloc.3
0x7853  ldc.i4   0x4BB5C879
0x7858  beq      loc_79CB
0x785d  br       loc_7CB4
0x7862  ldloc.3
0x7863  ldc.i4   0x50461F70
0x7868  beq      loc_7A9D
0x786d  ldloc.3
0x786e  ldc.i4   0x51FC6B95
0x7873  beq      loc_7B84
0x7878  ldloc.3
0x7879  ldc.i4   0x54DDED13
0x787e  beq      loc_7A49
0x7883  br       loc_7CB4
0x7888  ldloc.3
0x7889  ldc.i4   0x60290407
0x788e  bgt.un.s loc_78B6
0x7890  ldloc.3
0x7891  ldc.i4   0x560207DE
0x7896  beq      loc_7B6F
0x789b  ldloc.3
0x789c  ldc.i4   0x5612A23C
0x78a1  beq      loc_7B45
0x78a6  ldloc.3
0x78a7  ldc.i4   0x60290407
0x78ac  beq      loc_7B5A
0x78b1  br       loc_7CB4
0x78b6  ldloc.3
0x78b7  ldc.i4   0x69FC9431
0x78bc  bgt.un.s loc_78D9
0x78be  ldloc.3
0x78bf  ldc.i4   0x645E195E
0x78c4  beq      loc_7AB2
0x78c9  ldloc.3
0x78ca  ldc.i4   0x69FC9431
0x78cf  beq      loc_7BAE
0x78d4  br       loc_7CB4
0x78d9  ldloc.3
0x78da  ldc.i4   0x76631CBE
0x78df  beq      loc_7A73
0x78e4  ldloc.3
0x78e5  ldc.i4   0x90FF0D74
0x78ea  beq      loc_7BED
0x78ef  br       loc_7CB4
0x78f4  ldloc.3
0x78f5  ldc.i4   0xDAEF4933
0x78fa  bgt.un.s loc_7968
0x78fc  ldloc.3
0x78fd  ldc.i4   0xC44037FD
0x7902  bgt.un.s loc_792A
0x7904  ldloc.3
0x7905  ldc.i4   0x9A30E262
0x790a  beq      loc_7ADC
0x790f  ldloc.3
0x7910  ldc.i4   0xA2727BFF
0x7915  beq      loc_7A1F
0x791a  ldloc.3
0x791b  ldc.i4   0xC44037FD
0x7920  beq      loc_7BC3
0x7925  br       loc_7CB4
0x792a  ldloc.3
0x792b  ldc.i4   0xCEC61ADB
0x7930  bgt.un.s loc_794D
0x7932  ldloc.3
0x7933  ldc.i4   0xCC06B47D
0x7938  beq      loc_7A88
0x793d  ldloc.3
0x793e  ldc.i4   0xCEC61ADB
0x7943  beq      loc_7B06
0x7948  br       loc_7CB4
0x794d  ldloc.3
0x794e  ldc.i4   0xD9781963
0x7953  beq      loc_7B99
0x7958  ldloc.3
0x7959  ldc.i4   0xDAEF4933
0x795e  beq      loc_7BD8
0x7963  br       loc_7CB4
0x7968  ldloc.3
0x7969  ldc.i4   0xE12B0B27
0x796e  bgt.un.s loc_7993
0x7970  ldloc.3
0x7971  ldc.i4   0xDE4CC772
0x7976  beq      loc_7AC7
0x797b  ldloc.3
0x797c  ldc.i4   0xDEEA098D
0x7981  beq.s    loc_79F5
0x7983  ldloc.3
0x7984  ldc.i4   0xE12B0B27
0x7989  beq      loc_7A34
0x798e  br       loc_7CB4
0x7993  ldloc.3
0x7994  ldc.i4   0xEF205377
0x7999  bgt.un.s loc_79B3
0x799b  ldloc.3
0x799c  ldc.i4   0xEA694AE8
0x79a1  beq      loc_7AF1
0x79a6  ldloc.3
0x79a7  ldc.i4   0xEF205377
0x79ac  beq.s    loc_79E0
0x79ae  br       loc_7CB4
0x79b3  ldloc.3
0x79b4  ldc.i4   0xFA152AF0
0x79b9  beq.s    loc_7A0A
0x79bb  ldloc.3
0x79bc  ldc.i4   0xFF62F5B7
0x79c1  beq      loc_7B1B
0x79c6  br       loc_7CB4
0x79cb  ldloc.1
0x79cc  ldstr    aMaxschedulewai// "MaxScheduleWait"
0x79d1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x79d6  brtrue   loc_7C02
0x79db  br       loc_7CB4
0x79e0  ldloc.1
0x79e1  ldstr    aDatabasequeryt// "DatabaseQueryTimeout"
0x79e6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x79eb  brtrue   loc_7C0A
0x79f0  br       loc_7CB4
0x79f5  ldloc.1
0x79f6  ldstr    aProcesstimeout// "ProcessTimeout"
0x79fb  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7a00  brtrue   loc_7C12
0x7a05  br       loc_7CB4
0x7a0a  ldloc.1
0x7a0b  ldstr    aProcesstimeout_1// "ProcessTimeoutGcExtension"
0x7a10  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7a15  brtrue   loc_7C1A
0x7a1a  br       loc_7CB4
0x7a1f  ldloc.1
0x7a20  ldstr    aDatabasecleanu// "DatabaseCleanupTimeout"
0x7a25  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7a2a  brtrue   loc_7C22
0x7a2f  br       loc_7CB4
0x7a34  ldloc.1
0x7a35  ldstr    aDatabasecleanu_0// "DatabaseCleanupBatchFactor"
0x7a3a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7a3f  brtrue   loc_7C2A
0x7a44  br       loc_7CB4
0x7a49  ldloc.1
0x7a4a  ldstr    aProcessrecycle// "ProcessRecycleOptions"
0x7a4f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7a54  brtrue   loc_7D02
0x7a59  br       loc_7CB4
0x7a5e  ldloc.1
0x7a5f  ldstr    aRunningrequest// "RunningRequestsScavengerCycle"
0x7a64  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7a69  brtrue   loc_7C32
0x7a6e  br       loc_7CB4
0x7a73  ldloc.1
0x7a74  ldstr    aRunningrequest_0// "RunningRequestsDbCycle"
0x7a79  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7a7e  brtrue   loc_7C3A
0x7a83  br       loc_7CB4
0x7a88  ldloc.1
0x7a89  ldstr    aRunningrequest_1// "RunningRequestsAge"
0x7a8e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7a93  brtrue   loc_7C42
0x7a98  br       loc_7CB4
0x7a9d  ldloc.1
0x7a9e  ldstr    aCleanupcyclemi// "CleanupCycleMinutes"
0x7aa3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7aa8  brtrue   loc_7C4A
0x7aad  br       loc_7CB4
0x7ab2  ldloc.1
0x7ab3  ldstr    aAlertingcleanu// "AlertingCleanupCycleMinutes"
0x7ab8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7abd  brtrue   loc_7C52
0x7ac2  br       loc_7CB4
0x7ac7  ldloc.1
0x7ac8  ldstr    aAlertingdatacl// "AlertingDataCleanupMinutes"
0x7acd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7ad2  brtrue   loc_7C5A
0x7ad7  br       loc_7CB4
0x7adc  ldloc.1
0x7add  ldstr    aAlertingexecut// "AlertingExecutionLogCleanupMinutes"
0x7ae2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7ae7  brtrue   loc_7C62
0x7aec  br       loc_7CB4
0x7af1  ldloc.1
0x7af2  ldstr    aAlertingmaxdat// "AlertingMaxDataRetentionDays"
0x7af7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7afc  brtrue   loc_7C6A
0x7b01  br       loc_7CB4
0x7b06  ldloc.1
0x7b07  ldstr    aMaxactivereqfo// "MaxActiveReqForOneUser"
0x7b0c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7b11  brtrue   loc_7C72
0x7b16  br       loc_7CB4
0x7b1b  ldloc.1
0x7b1c  ldstr    aDailycleanupmi// "DailyCleanupMinuteOfDay"
0x7b21  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7b26  brtrue   loc_7C7A
0x7b2b  br       loc_7CB4
0x7b30  ldloc.1
0x7b31  ldstr    aWatsonflags// "WatsonFlags"
0x7b36  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7b3b  brtrue   loc_7C82
0x7b40  br       loc_7CB4
0x7b45  ldloc.1
0x7b46  ldstr    aWatsondumponex// "WatsonDumpOnExceptions"
0x7b4b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7b50  brtrue   loc_7C87
0x7b55  br       loc_7CB4
0x7b5a  ldloc.1
0x7b5b  ldstr    aWatsondumpexcl// "WatsonDumpExcludeIfContainsExceptions"
0x7b60  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7b65  brtrue   loc_7C8C
0x7b6a  br       loc_7CB4
0x7b6f  ldloc.1
0x7b70  ldstr    aSecureconnecti// "SecureConnectionLevel"
0x7b75  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7b7a  brtrue   loc_7C91
0x7b7f  br       loc_7CB4
0x7b84  ldloc.1
0x7b85  ldstr    aDisplayerrorli// "DisplayErrorLink"
0x7b8a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7b8f  brtrue   loc_7C96
0x7b94  br       loc_7CB4
0x7b99  ldloc.1
0x7b9a  ldstr    aDisablesecuref// "DisableSecureFormsAuthenticationCookie"
0x7b9f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7ba4  brtrue   loc_7C9B
0x7ba9  br       loc_7CB4
0x7bae  ldloc.1
0x7baf  ldstr    aWebserviceusef// "WebServiceUseFileShareStorage"
0x7bb4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7bb9  brtrue   loc_7CA0
0x7bbe  br       loc_7CB4
0x7bc3  ldloc.1
0x7bc4  ldstr    aRequestcachesl// "RequestCacheSlots"
0x7bc9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7bce  brtrue   loc_7CA5
0x7bd3  br       loc_7CB4
0x7bd8  ldloc.1
0x7bd9  ldstr    aUsernamesidref// "UsernameSIDRefreshMinutes"
0x7bde  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7be3  brtrue   loc_7CAA
0x7be8  br       loc_7CB4
0x7bed  ldloc.1
0x7bee  ldstr    aConnectiontime// "ConnectionTimeout"
0x7bf3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7bf8  brtrue   loc_7CAF
0x7bfd  br       loc_7CB4
0x7c02  ldc.i4.s 0x37
0x7c04  stloc.2
0x7c05  br       loc_7D02
0x7c0a  ldc.i4.s 0x41
0x7c0c  stloc.2
0x7c0d  br       loc_7D02
0x7c12  ldc.i4.s 0x42
0x7c14  stloc.2
0x7c15  br       loc_7D02
0x7c1a  ldc.i4.s 0x43
0x7c1c  stloc.2
0x7c1d  br       loc_7D02
0x7c22  ldc.i4.s 0x44
0x7c24  stloc.2
0x7c25  br       loc_7D02
0x7c2a  ldc.i4.s 0x45
0x7c2c  stloc.2
0x7c2d  br       loc_7D02
0x7c32  ldc.i4.s 0x34
0x7c34  stloc.2
  ... truncated ...
```
