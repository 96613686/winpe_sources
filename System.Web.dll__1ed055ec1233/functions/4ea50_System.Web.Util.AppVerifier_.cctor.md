# System.Web.Util.AppVerifier::.cctor

- ea: `0x4ea50`
- end: `0x4eba2`
- name: `System.Web.Util.AppVerifier::.cctor`
- size: `338`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x4e5b0`

## string_xrefs

- `0x4ea87`: `AppVerifier_Errors_AsyncCallbackGivenAsyncResultWhichWasNotCompleted`
- `0x4ea93`: `AppVerifier_Errors_AsyncCallbackInvokedSynchronouslyButAsyncResultWasNotMarkedCompletedSynchronously`
- `0x4ea9f`: `AppVerifier_Errors_AsyncCallbackInvokedAsynchronouslyButAsyncResultWasMarkedCompletedSynchronously`
- `0x4eb06`: `AppVerifier_Errors_BeginHandlerReturnedAsyncResultMarkedCompletedSynchronouslyButWhichWasNotCompleted`
- `0x4eb13`: `AppVerifier_Errors_BeginHandlerReturnedAsyncResultMarkedCompletedSynchronouslyButAsyncCallbackNeverCalled`
- `0x4eb3a`: `AppVerifier_Errors_SyncContextSendOrPostCalledAfterRequestCompleted`
- `0x4eb61`: `AppVerifier_Errors_RequestNotificationCompletedSynchronouslyWithNotificationContextPending`
- `0x4eb7b`: `AppVerifier_Errors_PendingProcessRequestNotificationStatusAfterCompletingNestedNotification`

## pseudocode

```c

```

## disassembly

```asm
0x4ea50  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype System.Web.Util.AppVerifierErrorCode, string>::.ctor()
0x4ea55  dup
0x4ea56  ldc.i4.1
0x4ea57  ldstr    aAppverifierErr// "AppVerifier_Errors_HttpApplicationInsta"...
0x4ea5c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype System.Web.Util.AppVerifierErrorCode, string>::Add(var<u1>, !!T0)
0x4ea61  dup
0x4ea62  ldc.i4.2
0x4ea63  ldstr    aAppverifierErr_0// "AppVerifier_Errors_BeginHandlerDelegate"...
0x4ea68  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype System.Web.Util.AppVerifierErrorCode, string>::Add(var<u1>, !!T0)
0x4ea6d  dup
0x4ea6e  ldc.i4.3
0x4ea6f  ldstr    aAppverifierErr_1// "AppVerifier_Errors_AsyncCallbackInvoked"...
0x4ea74  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype System.Web.Util.AppVerifierErrorCode, string>::Add(var<u1>, !!T0)
0x4ea79  dup
0x4ea7a  ldc.i4.4
0x4ea7b  ldstr    aAppverifierErr_2// "AppVerifier_Errors_AsyncCallbackInvoked"...
0x4ea80  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype System.Web.Util.AppVerifierErrorCode, string>::Add(var<u1>, !!T0)
0x4ea85  dup
0x4ea86  ldc.i4.5
0x4ea87  ldstr    aAppverifierErr_3// "AppVerifier_Errors_AsyncCallbackGivenAs"...
0x4ea8c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype System.Web.Util.AppVerifierErrorCode, string>::Add(var<u1>, !!T0)
0x4ea91  dup
0x4ea92  ldc.i4.6
0x4ea93  ldstr    aAppverifierErr_4// "AppVerifier_Errors_AsyncCallbackInvoked"...
0x4ea98  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype System.Web.Util.AppVerifierErrorCode, string>::Add(var<u1>, !!T0)
0x4ea9d  dup
0x4ea9e  ldc.i4.7
0x4ea9f  ldstr    aAppverifierErr_5// "AppVerifier_Errors_AsyncCallbackInvoked"...
0x4eaa4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype System.Web.Util.AppVerifierErrorCode, string>::Add(var<u1>, !!T0)
0x4eaa9  dup
0x4eaaa  ldc.i4.8
0x4eaab  ldstr    aAppverifierErr_6// "AppVerifier_Errors_AsyncCallbackInvoked"...
0x4eab0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype System.Web.Util.AppVerifierErrorCode, string>::Add(var<u1>, !!T0)
0x4eab5  dup
0x4eab6  ldc.i4.s 9
0x4eab8  ldstr    aAppverifierErr_7// "AppVerifier_Errors_AsyncCallbackInvoked"...
0x4eabd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype System.Web.Util.AppVerifierErrorCode, string>::Add(var<u1>, !!T0)
0x4eac2  dup
0x4eac3  ldc.i4.s 0xA
0x4eac5  ldstr    aAppverifierErr_7// "AppVerifier_Errors_AsyncCallbackInvoked"...
0x4eaca  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype System.Web.Util.AppVerifierErrorCode, string>::Add(var<u1>, !!T0)
0x4eacf  dup
0x4ead0  ldc.i4.s 0xB
0x4ead2  ldstr    aAppverifierErr_7// "AppVerifier_Errors_AsyncCallbackInvoked"...
0x4ead7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype System.Web.Util.AppVerifierErrorCode, string>::Add(var<u1>, !!T0)
0x4eadc  dup
0x4eadd  ldc.i4.s 0xC
0x4eadf  ldstr    aAppverifierErr_8// "AppVerifier_Errors_AsyncCallbackInvoked"...
0x4eae4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype System.Web.Util.AppVerifierErrorCode, string>::Add(var<u1>, !!T0)
0x4eae9  dup
0x4eaea  ldc.i4.s 0xD
0x4eaec  ldstr    aAppverifierErr_9// "AppVerifier_Errors_AsyncCallbackCalledA"...
0x4eaf1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype System.Web.Util.AppVerifierErrorCode, string>::Add(var<u1>, !!T0)
0x4eaf6  dup
0x4eaf7  ldc.i4.s 0xE
0x4eaf9  ldstr    aAppverifierErr_10// "AppVerifier_Errors_BeginHandlerReturned"...
0x4eafe  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype System.Web.Util.AppVerifierErrorCode, string>::Add(var<u1>, !!T0)
0x4eb03  dup
0x4eb04  ldc.i4.s 0xF
0x4eb06  ldstr    aAppverifierErr_11// "AppVerifier_Errors_BeginHandlerReturned"...
0x4eb0b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype System.Web.Util.AppVerifierErrorCode, string>::Add(var<u1>, !!T0)
0x4eb10  dup
0x4eb11  ldc.i4.s 0x10
0x4eb13  ldstr    aAppverifierErr_12// "AppVerifier_Errors_BeginHandlerReturned"...
0x4eb18  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype System.Web.Util.AppVerifierErrorCode, string>::Add(var<u1>, !!T0)
0x4eb1d  dup
0x4eb1e  ldc.i4.s 0x11
0x4eb20  ldstr    aAppverifierErr_6// "AppVerifier_Errors_AsyncCallbackInvoked"...
0x4eb25  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype System.Web.Util.AppVerifierErrorCode, string>::Add(var<u1>, !!T0)
0x4eb2a  dup
0x4eb2b  ldc.i4.s 0x12
0x4eb2d  ldstr    aAppverifierErr_13// "AppVerifier_Errors_BeginHandlerReturned"...
0x4eb32  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype System.Web.Util.AppVerifierErrorCode, string>::Add(var<u1>, !!T0)
0x4eb37  dup
0x4eb38  ldc.i4.s 0x13
0x4eb3a  ldstr    aAppverifierErr_14// "AppVerifier_Errors_SyncContextSendOrPos"...
0x4eb3f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype System.Web.Util.AppVerifierErrorCode, string>::Add(var<u1>, !!T0)
0x4eb44  dup
0x4eb45  ldc.i4.s 0x14
0x4eb47  ldstr    aAppverifierErr_15// "AppVerifier_Errors_SyncContextSendOrPos"...
0x4eb4c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype System.Web.Util.AppVerifierErrorCode, string>::Add(var<u1>, !!T0)
0x4eb51  dup
0x4eb52  ldc.i4.s 0x15
0x4eb54  ldstr    aAppverifierErr_16// "AppVerifier_Errors_SyncContextPostCalle"...
0x4eb59  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype System.Web.Util.AppVerifierErrorCode, string>::Add(var<u1>, !!T0)
0x4eb5e  dup
0x4eb5f  ldc.i4.s 0x16
0x4eb61  ldstr    aAppverifierErr_17// "AppVerifier_Errors_RequestNotificationC"...
0x4eb66  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype System.Web.Util.AppVerifierErrorCode, string>::Add(var<u1>, !!T0)
0x4eb6b  dup
0x4eb6c  ldc.i4.s 0x17
0x4eb6e  ldstr    aAppverifierErr_18// "AppVerifier_Errors_NotificationContextH"...
0x4eb73  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype System.Web.Util.AppVerifierErrorCode, string>::Add(var<u1>, !!T0)
0x4eb78  dup
0x4eb79  ldc.i4.s 0x18
0x4eb7b  ldstr    aAppverifierErr_19// "AppVerifier_Errors_PendingProcessReques"...
0x4eb80  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype System.Web.Util.AppVerifierErrorCode, string>::Add(var<u1>, !!T0)
0x4eb85  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype System.Web.Util.AppVerifierErrorCode, string> System.Web.Util.AppVerifier::_errorStringMappings
0x4eb8a  call     class [mscorlib]System.Action`1<class System.Web.Util.AppVerifierException> System.Web.Util.AppVerifier::GetAppVerifierBehaviorFromRegistry()
0x4eb8f  stsfld   class [mscorlib]System.Action`1<class System.Web.Util.AppVerifierException> System.Web.Util.AppVerifier::DefaultAppVerifierBehavior
0x4eb94  ldsfld   class [mscorlib]System.Action`1<class System.Web.Util.AppVerifierException> System.Web.Util.AppVerifier::DefaultAppVerifierBehavior
0x4eb99  ldnull
0x4eb9a  cgt.un
0x4eb9c  stsfld   bool System.Web.Util.AppVerifier::IsAppVerifierEnabled
0x4eba1  ret
```
