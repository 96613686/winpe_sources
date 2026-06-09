# Microsoft.SharePoint.Upgrade.TightenAuthorizedTypesConfig::.ctor

- ea: `0xa74370`
- end: `0xa746bb`
- name: `Microsoft.SharePoint.Upgrade.TightenAuthorizedTypesConfig::.ctor`
- size: `843`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0xa6d360`

## string_xrefs

- `0xa743e8`: `ExternalDataExchangeService`
- `0xa743f1`: `ExternalDataExchangeserviceSection`
- `0xa7448a`: `WorkflowSubscriptionService`
- `0xa744a1`: `ActiveDirectoryRole`
- `0xa744a9`: `ActiveDirectoryRoleFactory`
- `0xa744c1`: `CompensatableSequenceActivity`
- `0xa744d1`: `InvokeWebServiceActivity`
- `0xa744d9`: `InvokeWebServiceEventArgs`
- `0xa74532`: `WebServiceFaultActivity`
- `0xa7453b`: `WebServiceInputActivity`
- `0xa74544`: `WebServiceOutputActivity`
- `0xa7454d`: `WorkflowWebService`
- `0xa745c8`: `CompositeActivity`
- `0xa74610`: `RemovedActivityAction`
- `0xa7466a`: `NullExtension`
- `0xa74680`: `CompensatableTransactionScopeActivity`
- `0xa74688`: `CompensateActivity`
- `0xa74690`: `CompensationHandlerActivity`

## pseudocode

```c

```

## disassembly

```asm
0xa74370  ldarg.0
0xa74371  ldc.i4.s 0x20
0xa74373  newarr   [mscorlib]System.String
0xa74378  stloc.0
0xa74379  ldloc.0
0xa7437a  ldc.i4.0
0xa7437b  ldstr    aCallexternalme// "CallExternalMethodActivity"
0xa74380  stelem.ref
0xa74381  ldloc.0
0xa74382  ldc.i4.1
0xa74383  ldstr    aCallexternalme_0// "CallExternalMethodActivityValidator"
0xa74388  stelem.ref
0xa74389  ldloc.0
0xa7438a  ldc.i4.2
0xa7438b  ldstr    aCorrelationali// "CorrelationAliasAttribute"
0xa74390  stelem.ref
0xa74391  ldloc.0
0xa74392  ldc.i4.3
0xa74393  ldstr    aCorrelationini// "CorrelationInitializerAttribute"
0xa74398  stelem.ref
0xa74399  ldloc.0
0xa7439a  ldc.i4.4
0xa7439b  ldstr    aCorrelationpar// "CorrelationParameterAttribute"
0xa743a0  stelem.ref
0xa743a1  ldloc.0
0xa743a2  ldc.i4.5
0xa743a3  ldstr    aDelayactivity// "DelayActivity"
0xa743a8  stelem.ref
0xa743a9  ldloc.0
0xa743aa  ldc.i4.6
0xa743ab  ldstr    aEventdeliveryf// "EventDeliveryFailedException"
0xa743b0  stelem.ref
0xa743b1  ldloc.0
0xa743b2  ldc.i4.7
0xa743b3  ldstr    aEventdrivenact// "EventDrivenActivity"
0xa743b8  stelem.ref
0xa743b9  ldloc.0
0xa743ba  ldc.i4.8
0xa743bb  ldstr    aEventhandlersa// "EventHandlersActivity"
0xa743c0  stelem.ref
0xa743c1  ldloc.0
0xa743c2  ldc.i4.s 9
0xa743c4  ldstr    aEventhandlings// "EventHandlingScopeActivity"
0xa743c9  stelem.ref
0xa743ca  ldloc.0
0xa743cb  ldc.i4.s 0xA
0xa743cd  ldstr    aEventqueuename// "EventQueueName"
0xa743d2  stelem.ref
0xa743d3  ldloc.0
0xa743d4  ldc.i4.s 0xB
0xa743d6  ldstr    aExternaldataev// "ExternalDataEventArgs"
0xa743db  stelem.ref
0xa743dc  ldloc.0
0xa743dd  ldc.i4.s 0xC
0xa743df  ldstr    aExternaldataex// "ExternalDataExchangeAttribute"
0xa743e4  stelem.ref
0xa743e5  ldloc.0
0xa743e6  ldc.i4.s 0xD
0xa743e8  ldstr    aExternaldataex_0// "ExternalDataExchangeService"
0xa743ed  stelem.ref
0xa743ee  ldloc.0
0xa743ef  ldc.i4.s 0xE
0xa743f1  ldstr    aExternaldataex_1// "ExternalDataExchangeserviceSection"
0xa743f6  stelem.ref
0xa743f7  ldloc.0
0xa743f8  ldc.i4.s 0xF
0xa743fa  ldstr    aHandleexternal// "HandleExternalEventActivity"
0xa743ff  stelem.ref
0xa74400  ldloc.0
0xa74401  ldc.i4.s 0x10
0xa74403  ldstr    aHandleexternal_0// "HandleExternalEventActivityValidator"
0xa74408  stelem.ref
0xa74409  ldloc.0
0xa7440a  ldc.i4.s 0x11
0xa7440c  ldstr    aIfelseactivity_0// "IfElseActivity"
0xa74411  stelem.ref
0xa74412  ldloc.0
0xa74413  ldc.i4.s 0x12
0xa74415  ldstr    aIfelsebranchac_1// "IfElseBranchActivity"
0xa7441a  stelem.ref
0xa7441b  ldloc.0
0xa7441c  ldc.i4.s 0x13
0xa7441e  ldstr    aListenactivity// "ListenActivity"
0xa74423  stelem.ref
0xa74424  ldloc.0
0xa74425  ldc.i4.s 0x14
0xa74427  ldstr    aMessageeventsu// "MessageEventSubscription"
0xa7442c  stelem.ref
0xa7442d  ldloc.0
0xa7442e  ldc.i4.s 0x15
0xa74430  ldstr    aParallelactivi_0// "ParallelActivity"
0xa74435  stelem.ref
0xa74436  ldloc.0
0xa74437  ldc.i4.s 0x16
0xa74439  ldstr    aPolicyactivity// "PolicyActivity"
0xa7443e  stelem.ref
0xa7443f  ldloc.0
0xa74440  ldc.i4.s 0x17
0xa74442  ldstr    aReplicatorchil// "ReplicatorChildEventArgs"
0xa74447  stelem.ref
0xa74448  ldloc.0
0xa74449  ldc.i4.s 0x18
0xa7444b  ldstr    aRuleconditionr_0// "RuleConditionReference"
0xa74450  stelem.ref
0xa74451  ldloc.0
0xa74452  ldc.i4.s 0x19
0xa74454  ldstr    aSequenceactivi_0// "SequenceActivity"
0xa74459  stelem.ref
0xa7445a  ldloc.0
0xa7445b  ldc.i4.s 0x1A
0xa7445d  ldstr    aSequentialwork// "SequentialWorkflowActivity"
0xa74462  stelem.ref
0xa74463  ldloc.0
0xa74464  ldc.i4.s 0x1B
0xa74466  ldstr    aWebworkflowrol// "WebWorkflowRole"
0xa7446b  stelem.ref
0xa7446c  ldloc.0
0xa7446d  ldc.i4.s 0x1C
0xa7446f  ldstr    aWorkflowauthor// "WorkflowAuthorizationException"
0xa74474  stelem.ref
0xa74475  ldloc.0
0xa74476  ldc.i4.s 0x1D
0xa74478  ldstr    aWorkflowrole// "WorkflowRole"
0xa7447d  stelem.ref
0xa7447e  ldloc.0
0xa7447f  ldc.i4.s 0x1E
0xa74481  ldstr    aWorkflowroleco// "WorkflowRoleCollection"
0xa74486  stelem.ref
0xa74487  ldloc.0
0xa74488  ldc.i4.s 0x1F
0xa7448a  ldstr    aWorkflowsubscr// "WorkflowSubscriptionService"
0xa7448f  stelem.ref
0xa74490  ldloc.0
0xa74491  stfld    string[] Microsoft.SharePoint.Upgrade.TightenAuthorizedTypesConfig::safeAuthorizedTypesInSysWFActivities
0xa74496  ldarg.0
0xa74497  ldc.i4.s 0x15
0xa74499  newarr   [mscorlib]System.String
0xa7449e  stloc.1
0xa7449f  ldloc.1
0xa744a0  ldc.i4.0
0xa744a1  ldstr    aActivedirector// "ActiveDirectoryRole"
0xa744a6  stelem.ref
0xa744a7  ldloc.1
0xa744a8  ldc.i4.1
0xa744a9  ldstr    aActivedirector_0// "ActiveDirectoryRoleFactory"
0xa744ae  stelem.ref
0xa744af  ldloc.1
0xa744b0  ldc.i4.2
0xa744b1  ldstr    aCodeactivity// "CodeActivity"
0xa744b6  stelem.ref
0xa744b7  ldloc.1
0xa744b8  ldc.i4.3
0xa744b9  ldstr    aCodecondition// "CodeCondition"
0xa744be  stelem.ref
0xa744bf  ldloc.1
0xa744c0  ldc.i4.4
0xa744c1  ldstr    aCompensatables// "CompensatableSequenceActivity"
0xa744c6  stelem.ref
0xa744c7  ldloc.1
0xa744c8  ldc.i4.5
0xa744c9  ldstr    aConditionaleve// "ConditionalEventArgs"
0xa744ce  stelem.ref
0xa744cf  ldloc.1
0xa744d0  ldc.i4.6
0xa744d1  ldstr    aInvokewebservi// "InvokeWebServiceActivity"
0xa744d6  stelem.ref
0xa744d7  ldloc.1
0xa744d8  ldc.i4.7
0xa744d9  ldstr    aInvokewebservi_0// "InvokeWebServiceEventArgs"
0xa744de  stelem.ref
0xa744df  ldloc.1
0xa744e0  ldc.i4.8
0xa744e1  ldstr    aInvokeworkflow// "InvokeWorkflowActivity"
0xa744e6  stelem.ref
0xa744e7  ldloc.1
0xa744e8  ldc.i4.s 9
0xa744ea  ldstr    aSetstateactivi// "SetStateActivity"
0xa744ef  stelem.ref
0xa744f0  ldloc.1
0xa744f1  ldc.i4.s 0xA
0xa744f3  ldstr    aSetstateeventa// "SetStateEventArgs"
0xa744f8  stelem.ref
0xa744f9  ldloc.1
0xa744fa  ldc.i4.s 0xB
0xa744fc  ldstr    aStateactivity// "StateActivity"
0xa74501  stelem.ref
0xa74502  ldloc.1
0xa74503  ldc.i4.s 0xC
0xa74505  ldstr    aStateactivityv// "StateActivityValidator"
0xa7450a  stelem.ref
0xa7450b  ldloc.1
0xa7450c  ldc.i4.s 0xD
0xa7450e  ldstr    aStatefinalizat// "StateFinalizationActivity"
0xa74513  stelem.ref
0xa74514  ldloc.1
0xa74515  ldc.i4.s 0xE
0xa74517  ldstr    aStateinitializ// "StateInitializationActivity"
0xa7451c  stelem.ref
0xa7451d  ldloc.1
0xa7451e  ldc.i4.s 0xF
0xa74520  ldstr    aStatemachinewo// "StateMachineWorkflowActivity"
0xa74525  stelem.ref
0xa74526  ldloc.1
0xa74527  ldc.i4.s 0x10
0xa74529  ldstr    aStatemachinewo_0// "StateMachineWorkflowInstance"
0xa7452e  stelem.ref
0xa7452f  ldloc.1
0xa74530  ldc.i4.s 0x11
0xa74532  ldstr    aWebservicefaul// "WebServiceFaultActivity"
0xa74537  stelem.ref
0xa74538  ldloc.1
0xa74539  ldc.i4.s 0x12
0xa7453b  ldstr    aWebserviceinpu// "WebServiceInputActivity"
0xa74540  stelem.ref
0xa74541  ldloc.1
0xa74542  ldc.i4.s 0x13
0xa74544  ldstr    aWebserviceoutp// "WebServiceOutputActivity"
0xa74549  stelem.ref
0xa7454a  ldloc.1
0xa7454b  ldc.i4.s 0x14
0xa7454d  ldstr    aWorkflowwebser// "WorkflowWebService"
0xa74552  stelem.ref
0xa74553  ldloc.1
0xa74554  stfld    string[] Microsoft.SharePoint.Upgrade.TightenAuthorizedTypesConfig::unSafeAuthorizedTypesInSysWFActivities
0xa74559  ldarg.0
0xa7455a  ldc.i4.s 0x1F
0xa7455c  newarr   [mscorlib]System.String
0xa74561  stloc.2
0xa74562  ldloc.2
0xa74563  ldc.i4.0
0xa74564  ldstr    aActivity_0// "Activity"
0xa74569  stelem.ref
0xa7456a  ldloc.2
0xa7456b  ldc.i4.1
0xa7456c  ldstr    aActivitybind_1// "ActivityBind"
0xa74571  stelem.ref
0xa74572  ldloc.2
0xa74573  ldc.i4.2
0xa74574  ldstr    aActivitychange// "ActivityChangeAction"
0xa74579  stelem.ref
0xa7457a  ldloc.2
0xa7457b  ldc.i4.3
0xa7457c  ldstr    aActivitycollec// "ActivityCollection"
0xa74581  stelem.ref
0xa74582  ldloc.2
0xa74583  ldc.i4.4
0xa74584  ldstr    aActivitycollec_0// "ActivityCollectionChangeEventArgs"
0xa74589  stelem.ref
0xa7458a  ldloc.2
0xa7458b  ldc.i4.5
0xa7458c  ldstr    aActivitycondit// "ActivityCondition"
0xa74591  stelem.ref
0xa74592  ldloc.2
0xa74593  ldc.i4.6
0xa74594  ldstr    aActivityexecut// "ActivityExecutionContext"
0xa74599  stelem.ref
0xa7459a  ldloc.2
0xa7459b  ldc.i4.7
0xa7459c  ldstr    aActivityexecut_0// "ActivityExecutionContextManager"
0xa745a1  stelem.ref
0xa745a2  ldloc.2
0xa745a3  ldc.i4.8
0xa745a4  ldstr    aActivityexecut_1// "ActivityExecutionStatusChangedEventArgs"
0xa745a9  stelem.ref
0xa745aa  ldloc.2
0xa745ab  ldc.i4.s 9
0xa745ad  ldstr    aAddedactivitya// "AddedActivityAction"
0xa745b2  stelem.ref
0xa745b3  ldloc.2
0xa745b4  ldc.i4.s 0xA
0xa745b6  ldstr    aAlternateflowa// "AlternateFlowActivityAttribute"
0xa745bb  stelem.ref
0xa745bc  ldloc.2
0xa745bd  ldc.i4.s 0xB
0xa745bf  ldstr    aCancellationha// "CancellationHandlerActivity"
0xa745c4  stelem.ref
0xa745c5  ldloc.2
0xa745c6  ldc.i4.s 0xC
0xa745c8  ldstr    aCompositeactiv// "CompositeActivity"
0xa745cd  stelem.ref
0xa745ce  ldloc.2
0xa745cf  ldc.i4.s 0xD
0xa745d1  ldstr    aDependencyobje// "DependencyObject"
0xa745d6  stelem.ref
0xa745d7  ldloc.2
0xa745d8  ldc.i4.s 0xE
0xa745da  ldstr    aDependencyprop// "DependencyProperty"
0xa745df  stelem.ref
0xa745e0  ldloc.2
0xa745e1  ldc.i4.s 0xF
0xa745e3  ldstr    aFaulthandlerac// "FaultHandlerActivity"
0xa745e8  stelem.ref
0xa745e9  ldloc.2
0xa745ea  ldc.i4.s 0x10
0xa745ec  ldstr    aFaulthandlersa// "FaultHandlersActivity"
0xa745f1  stelem.ref
0xa745f2  ldloc.2
0xa745f3  ldc.i4.s 0x11
0xa745f5  ldstr    aPersistonclose_0// "PersistOnCloseAttribute"
0xa745fa  stelem.ref
  ... truncated ...
```
