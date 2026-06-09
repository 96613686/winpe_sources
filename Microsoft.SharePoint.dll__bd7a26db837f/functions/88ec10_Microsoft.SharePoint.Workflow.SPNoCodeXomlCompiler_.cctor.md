# Microsoft.SharePoint.Workflow.SPNoCodeXomlCompiler::.cctor

- ea: `0x88ec10`
- end: `0x8906da`
- name: `Microsoft.SharePoint.Workflow.SPNoCodeXomlCompiler::.cctor`
- size: `6858`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## string_xrefs

- `0x88f31c`: `overwrite`
- `0x88f513`: `overwrite`
- `0x88f45c`: `xmlns`
- `0x88fd09`: `xmlns`
- `0x890330`: `xmlns`
- `0x890302`: `comment`
- `0x88ed84`: `ontaskdeleted`
- `0x88ed94`: `settaskprocessitemmoderationstatus`
- `0x88edaf`: `comments`
- `0x88ef8e`: `comments`
- `0x88f1e6`: `comments`
- `0x88f6a3`: `comments`
- `0x88f810`: `comments`
- `0x88fa91`: `comments`
- `0x88ff51`: `comments`
- `0x8900a8`: `comments`
- `0x88edcf`: `onworkflowactivated.correlationtoken`
- `0x88eddf`: `endtaskprocess`
- `0x88edff`: `buildassignmentsxmlactivity`
- `0x88eeca`: `collectfeedbacktaskprocess`
- `0x88eeff`: `deletetasksoncomplete`
- `0x88f157`: `deletetasksoncomplete`
- `0x88f774`: `deletetasksoncomplete`
- `0x88ef26`: `taskprocessowner`
- `0x88f17e`: `taskprocessowner`
- `0x88f79b`: `taskprocessowner`
- `0x88ef4d`: `senddefaulttasknotifications`
- `0x88f1a5`: `senddefaulttasknotifications`
- `0x88f7c2`: `senddefaulttasknotifications`
- `0x88ef5a`: `taskdeletedoutcome`
- `0x88f1b2`: `taskdeletedoutcome`
- `0x88f7cf`: `taskdeletedoutcome`
- `0x88ef67`: `taskprocessname`
- `0x88f1bf`: `taskprocessname`
- `0x88f7dc`: `taskprocessname`
- `0x88eff6`: `outcomes`
- `0x88f24e`: `outcomes`
- `0x88f885`: `outcomes`
- `0x88f052`: `historyoutcome`
- `0x88f0a6`: `ontaskassigning`
- `0x88f12f`: `approvaltaskprocess`
- `0x88f2e7`: `createitemactivity`
- `0x88f2f5`: `itemproperties`
- `0x88fe42`: `itemproperties`
- `0x88f34c`: `ontaskpending`
- `0x88f3a4`: `groupassignedtask`
- `0x88f4eb`: `copyitemactivity`
- `0x88f5bd`: `todoitemtask`
- `0x88f605`: `commentactivity`
- `0x88f613`: `commenttext`
- `0x88f73f`: `officetask`
- `0x88f74d`: `deletedtaskcount`
- `0x88f878`: `taskprocesswascanceled`
- `0x88f99d`: `ontaskprocesspending`
- `0x88f9dd`: `ontaskexpired`
- `0x88fa59`: `ontaskcompleted`
- `0x88fc4a`: `correlationtoken`
- `0x88fc78`: `deletepreviousversionsactivity`
- `0x88fd4c`: `waitforitemdeleted`
- `0x88fdd2`: `deleteitemactivity`
- `0x88fe0d`: `updateitemactivity`
- `0x88ff9f`: `collectdatatask`
- `0x88ffe1`: `taskid`
- `0x8900c8`: `ontaskprocesscompleted`
- `0x8900f9`: `sendtaskemail`
- `0x890168`: `ontaskprocesscanceled`
- `0x8901b7`: `deletedraftsactivity`
- `0x8902a9`: `ontaskprocessstarted`
- `0x890443`: `addlistitempermissionsactivity`
- `0x890498`: `impersonationsequenceactivity`
- `0x89051e`: `replacelistitempermissionsactivity`
- `0x8905a1`: `removelistitempermissionsactivity`
- `0x890674`: `forwardtask`
- `0x890694`: `inheritlistitemparentpermissionsactivity`
- `0x8906b4`: `rescindtask`
- `0x8906c4`: `settaskfield`

## pseudocode

```c

```

## disassembly

```asm
0x88ec10  ldstr    aF4424303B0564a// "F4424303-B056-4A65-9707-A1289683A8EC"
0x88ec15  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x88ec1a  stsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Workflow.SPNoCodeXomlCompiler::SPNoCodeXomlCompilerNoNewAppDomainKillSwitch
0x88ec1f  ldstr    a2cea8af4903f4e// "2CEA8AF4-903F-4E04-B0E0-1982BEA3B8C3"
0x88ec24  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x88ec29  stsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Workflow.SPNoCodeXomlCompiler::SPNoCodeXomlCompilerDomainUnloadKillSwitch
0x88ec2e  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor()
0x88ec33  stloc.0
0x88ec34  ldloc.0
0x88ec35  ldstr    aNs0// "ns0"
0x88ec3a  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88ec3f  pop
0x88ec40  ldloc.0
0x88ec41  ldstr    aNs1// "ns1"
0x88ec46  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88ec4b  pop
0x88ec4c  ldloc.0
0x88ec4d  ldstr    aNs2// "ns2"
0x88ec52  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88ec57  pop
0x88ec58  ldloc.0
0x88ec59  ldstr    aNs3// "ns3"
0x88ec5e  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88ec63  pop
0x88ec64  ldloc.0
0x88ec65  ldstr    aName// "name"
0x88ec6a  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88ec6f  pop
0x88ec70  ldloc.0
0x88ec71  ldstr    aDescription_1// "description"
0x88ec76  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88ec7b  pop
0x88ec7c  ldloc.0
0x88ec7d  ldstr    aP4// "p4"
0x88ec82  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88ec87  pop
0x88ec88  ldloc.0
0x88ec89  ldstr    aP5// "p5"
0x88ec8e  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88ec93  pop
0x88ec94  ldloc.0
0x88ec95  stsfld   class [System.Core]System.Collections.Generic.HashSet`1<string> Microsoft.SharePoint.Workflow.SPNoCodeXomlCompiler::commonAuthorizedAttributes
0x88ec9a  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Core]System.Collections.Generic.HashSet`1<string>>::.ctor()
0x88ec9f  stloc.1
0x88eca0  ldloc.1
0x88eca1  ldstr    aLookupactivity// "lookupactivity"
0x88eca6  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor()
0x88ecab  stloc.2
0x88ecac  ldloc.2
0x88ecad  ldstr    aContext_4// "__context"
0x88ecb2  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88ecb7  pop
0x88ecb8  ldloc.2
0x88ecb9  ldstr    aListid_3// "listid"
0x88ecbe  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88ecc3  pop
0x88ecc4  ldloc.2
0x88ecc5  ldstr    aFieldname_4// "fieldname"
0x88ecca  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88eccf  pop
0x88ecd0  ldloc.2
0x88ecd1  ldstr    aListitem_1// "listitem"
0x88ecd6  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88ecdb  pop
0x88ecdc  ldloc.2
0x88ecdd  ldstr    aLookupfunction// "lookupfunction"
0x88ece2  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88ece7  pop
0x88ece8  ldloc.2
0x88ece9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Core]System.Collections.Generic.HashSet`1<string>>::Add(var<u1>, !!T0)
0x88ecee  ldloc.1
0x88ecef  ldstr    aEmailactivity// "emailactivity"
0x88ecf4  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor()
0x88ecf9  stloc.3
0x88ecfa  ldloc.3
0x88ecfb  ldstr    aContext_4// "__context"
0x88ed00  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88ed05  pop
0x88ed06  ldloc.3
0x88ed07  ldstr    aBcc// "bcc"
0x88ed0c  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88ed11  pop
0x88ed12  ldloc.3
0x88ed13  ldstr    aTo// "to"
0x88ed18  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88ed1d  pop
0x88ed1e  ldloc.3
0x88ed1f  ldstr    aBody// "body"
0x88ed24  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88ed29  pop
0x88ed2a  ldloc.3
0x88ed2b  ldstr    aCc// "cc"
0x88ed30  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88ed35  pop
0x88ed36  ldloc.3
0x88ed37  ldstr    aSubject// "subject"
0x88ed3c  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88ed41  pop
0x88ed42  ldloc.3
0x88ed43  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Core]System.Collections.Generic.HashSet`1<string>>::Add(var<u1>, !!T0)
0x88ed48  ldloc.1
0x88ed49  ldstr    aCheckoutitemac// "checkoutitemactivity"
0x88ed4e  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor()
0x88ed53  stloc.s  4
0x88ed55  ldloc.s  4
0x88ed57  ldstr    aContext_4// "__context"
0x88ed5c  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88ed61  pop
0x88ed62  ldloc.s  4
0x88ed64  ldstr    aListid_3// "listid"
0x88ed69  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88ed6e  pop
0x88ed6f  ldloc.s  4
0x88ed71  ldstr    aListitem_1// "listitem"
0x88ed76  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88ed7b  pop
0x88ed7c  ldloc.s  4
0x88ed7e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Core]System.Collections.Generic.HashSet`1<string>>::Add(var<u1>, !!T0)
0x88ed83  ldloc.1
0x88ed84  ldstr    aOntaskdeleted// "ontaskdeleted"
0x88ed89  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor()
0x88ed8e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Core]System.Collections.Generic.HashSet`1<string>>::Add(var<u1>, !!T0)
0x88ed93  ldloc.1
0x88ed94  ldstr    aSettaskprocess// "settaskprocessitemmoderationstatus"
0x88ed99  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor()
0x88ed9e  stloc.s  5
0x88eda0  ldloc.s  5
0x88eda2  ldstr    aContext_4// "__context"
0x88eda7  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88edac  pop
0x88edad  ldloc.s  5
0x88edaf  ldstr    aComments_0// "comments"
0x88edb4  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88edb9  pop
0x88edba  ldloc.s  5
0x88edbc  ldstr    aModerationstat_7// "moderationstatus"
0x88edc1  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88edc6  pop
0x88edc7  ldloc.s  5
0x88edc9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Core]System.Collections.Generic.HashSet`1<string>>::Add(var<u1>, !!T0)
0x88edce  ldloc.1
0x88edcf  ldstr    aOnworkflowacti// "onworkflowactivated.correlationtoken"
0x88edd4  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor()
0x88edd9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Core]System.Collections.Generic.HashSet`1<string>>::Add(var<u1>, !!T0)
0x88edde  ldloc.1
0x88eddf  ldstr    aEndtaskprocess// "endtaskprocess"
0x88ede4  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor()
0x88ede9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Core]System.Collections.Generic.HashSet`1<string>>::Add(var<u1>, !!T0)
0x88edee  ldloc.1
0x88edef  ldstr    aString// "string"
0x88edf4  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor()
0x88edf9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Core]System.Collections.Generic.HashSet`1<string>>::Add(var<u1>, !!T0)
0x88edfe  ldloc.1
0x88edff  ldstr    aBuildassignmen// "buildassignmentsxmlactivity"
0x88ee04  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor()
0x88ee09  stloc.s  6
0x88ee0b  ldloc.s  6
0x88ee0d  ldstr    aContext_4// "__context"
0x88ee12  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88ee17  pop
0x88ee18  ldloc.s  6
0x88ee1a  ldstr    aValue_2// "value"
0x88ee1f  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88ee24  pop
0x88ee25  ldloc.s  6
0x88ee27  ldstr    aReturnvalue_4// "returnvalue"
0x88ee2c  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88ee31  pop
0x88ee32  ldloc.s  6
0x88ee34  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Core]System.Collections.Generic.HashSet`1<string>>::Add(var<u1>, !!T0)
0x88ee39  ldloc.1
0x88ee3a  ldstr    aHtlookupactivi// "htlookupactivity"
0x88ee3f  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor()
0x88ee44  stloc.s  7
0x88ee46  ldloc.s  7
0x88ee48  ldstr    aContext_4// "__context"
0x88ee4d  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88ee52  pop
0x88ee53  ldloc.s  7
0x88ee55  ldstr    aCollection_0// "collection"
0x88ee5a  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88ee5f  pop
0x88ee60  ldloc.s  7
0x88ee62  ldstr    aName// "name"
0x88ee67  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88ee6c  pop
0x88ee6d  ldloc.s  7
0x88ee6f  ldstr    aFieldname_4// "fieldname"
0x88ee74  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88ee79  pop
0x88ee7a  ldloc.s  7
0x88ee7c  ldstr    aLookupfunction// "lookupfunction"
0x88ee81  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88ee86  pop
0x88ee87  ldloc.s  7
0x88ee89  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Core]System.Collections.Generic.HashSet`1<string>>::Add(var<u1>, !!T0)
0x88ee8e  ldloc.1
0x88ee8f  ldstr    aUndeclarerecor// "undeclarerecordactivity"
0x88ee94  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor()
0x88ee99  stloc.s  8
0x88ee9b  ldloc.s  8
0x88ee9d  ldstr    aContext_4// "__context"
0x88eea2  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88eea7  pop
0x88eea8  ldloc.s  8
0x88eeaa  ldstr    aListitem_2// "__listitem"
0x88eeaf  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88eeb4  pop
0x88eeb5  ldloc.s  8
0x88eeb7  ldstr    aListid_10// "__listid"
0x88eebc  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88eec1  pop
0x88eec2  ldloc.s  8
0x88eec4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Core]System.Collections.Generic.HashSet`1<string>>::Add(var<u1>, !!T0)
0x88eec9  ldloc.1
0x88eeca  ldstr    aCollectfeedbac// "collectfeedbacktaskprocess"
0x88eecf  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor()
0x88eed4  stloc.s  9
0x88eed6  ldloc.s  9
0x88eed8  ldstr    aDescription_1// "description"
0x88eedd  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88eee2  pop
0x88eee3  ldloc.s  9
0x88eee5  ldstr    aOverduerepeat// "overduerepeat"
0x88eeea  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88eeef  pop
0x88eef0  ldloc.s  9
0x88eef2  ldstr    aAllowreassign// "allowreassign"
0x88eef7  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88eefc  pop
0x88eefd  ldloc.s  9
0x88eeff  ldstr    aDeletetasksonc// "deletetasksoncomplete"
0x88ef04  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88ef09  pop
0x88ef0a  ldloc.s  9
0x88ef0c  ldstr    aContenttypeid_5// "contenttypeid"
0x88ef11  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88ef16  pop
0x88ef17  ldloc.s  9
0x88ef19  ldstr    aDuration_0// "duration"
0x88ef1e  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88ef23  pop
0x88ef24  ldloc.s  9
0x88ef26  ldstr    aTaskprocessown// "taskprocessowner"
0x88ef2b  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88ef30  pop
0x88ef31  ldloc.s  9
0x88ef33  ldstr    aDurationunit// "durationunit"
0x88ef38  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88ef3d  pop
0x88ef3e  ldloc.s  9
0x88ef40  ldstr    aSubject// "subject"
0x88ef45  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88ef4a  pop
0x88ef4b  ldloc.s  9
0x88ef4d  ldstr    aSenddefaulttas// "senddefaulttasknotifications"
0x88ef52  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88ef57  pop
0x88ef58  ldloc.s  9
0x88ef5a  ldstr    aTaskdeletedout// "taskdeletedoutcome"
0x88ef5f  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88ef64  pop
0x88ef65  ldloc.s  9
0x88ef67  ldstr    aTaskprocessnam// "taskprocessname"
0x88ef6c  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88ef71  pop
0x88ef72  ldloc.s  9
0x88ef74  ldstr    aCc// "cc"
0x88ef79  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88ef7e  pop
0x88ef7f  ldloc.s  9
0x88ef81  ldstr    aExpandgroups// "expandgroups"
0x88ef86  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88ef8b  pop
0x88ef8c  ldloc.s  9
0x88ef8e  ldstr    aComments_0// "comments"
0x88ef93  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88ef98  pop
0x88ef99  ldloc.s  9
0x88ef9b  ldstr    aContext_4// "__context"
0x88efa0  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88efa5  pop
0x88efa6  ldloc.s  9
0x88efa8  ldstr    aAssignedto_0// "assignedto"
0x88efad  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88efb2  pop
0x88efb3  ldloc.s  9
0x88efb5  ldstr    aAllowchangereq// "allowchangerequest"
0x88efba  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88efbf  pop
0x88efc0  ldloc.s  9
0x88efc2  ldstr    aListid_3// "listid"
0x88efc7  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88efcc  pop
0x88efcd  ldloc.s  9
0x88efcf  ldstr    aActivationprop_0// "__activationproperties"
0x88efd4  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x88efd9  pop
0x88efda  ldloc.s  9
0x88efdc  ldstr    aPermissionset_0// "permissionset"
  ... truncated ...
```
