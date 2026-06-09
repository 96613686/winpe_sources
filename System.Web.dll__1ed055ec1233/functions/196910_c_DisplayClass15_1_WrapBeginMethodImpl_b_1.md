# <>c__DisplayClass15_1::<WrapBeginMethodImpl>b__1

- ea: `0x196910`
- end: `0x196be5`
- name: `<>c__DisplayClass15_1::<WrapBeginMethodImpl>b__1`
- size: `725`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x4e980`
- `0x4ea10`
- `0x4ea30`
- `0x4ebe0`
- `0x1962d0`
- `0x196390`
- `0x196910`

## string_xrefs

- `0x1969e4`: `AppVerifier_BasicInfo_ThreadInfo`
- `0x196adb`: `AppVerifier_BeginMethodInfo_ThreadInfo`
- `0x196b6f`: `AppVerifier_AsyncCallbackInfo_FirstInvocation_ThreadInfo`

## pseudocode

```c

```

## disassembly

```asm
0x196910  ldc.i4.1
0x196911  conv.i8
0x196912  ldarg.2
0x196913  ldc.i4.s 0x3F
0x196915  and
0x196916  shl
0x196917  stloc.0
0x196918  ldsfld   int64 System.Web.Util.AppVerifier::AppVerifierErrorCodeEnableAssertMask
0x19691d  ldloc.0
0x19691e  and
0x19691f  ldloc.0
0x196920  ceq
0x196922  stloc.1
0x196923  ldarg.1
0x196924  ldc.i4.0
0x196925  ceq
0x196927  ldloc.1
0x196928  and
0x196929  brfalse  loc_196BE4
0x19692e  ldsfld   int64 System.Web.Util.AppVerifier::AppVerifierErrorCodeCollectCallStackMask
0x196933  ldloc.0
0x196934  and
0x196935  ldloc.0
0x196936  ceq
0x196938  stloc.2
0x196939  ldloc.2
0x19693a  call     class InvocationInfo InvocationInfo::Capture(bool captureStack)
0x19693f  stloc.3
0x196940  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x196945  stloc.s  4
0x196947  ldloc.s  4
0x196949  ldstr    aAppverifierTit// "AppVerifier_Title"
0x19694e  ldc.i4.0
0x19694f  newarr   [mscorlib]System.Object
0x196954  call     string System.Web.Util.AppVerifier::FormatErrorString(string name, object[] args)
0x196959  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x19695e  pop
0x19695f  ldloc.s  4
0x196961  ldstr    aAppverifierSub// "AppVerifier_Subtitle"
0x196966  ldc.i4.0
0x196967  newarr   [mscorlib]System.Object
0x19696c  call     string System.Web.Util.AppVerifier::FormatErrorString(string name, object[] args)
0x196971  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x196976  pop
0x196977  ldloc.s  4
0x196979  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x19697e  pop
0x19697f  ldloc.s  4
0x196981  ldstr    aAppverifierBas// "AppVerifier_BasicInfo_URL"
0x196986  ldc.i4.1
0x196987  newarr   [mscorlib]System.Object
0x19698c  dup
0x19698d  ldc.i4.0
0x19698e  ldarg.0
0x19698f  ldfld    string <>c__DisplayClass15_1::requestUrl
0x196994  stelem.ref
0x196995  call     string System.Web.Util.AppVerifier::FormatErrorString(string name, object[] args)
0x19699a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x19699f  pop
0x1969a0  ldloc.s  4
0x1969a2  ldstr    aAppverifierBas_0// "AppVerifier_BasicInfo_ErrorCode"
0x1969a7  ldc.i4.1
0x1969a8  newarr   [mscorlib]System.Object
0x1969ad  dup
0x1969ae  ldc.i4.0
0x1969af  ldarg.2
0x1969b0  box      [mscorlib]System.Int32
0x1969b5  stelem.ref
0x1969b6  call     string System.Web.Util.AppVerifier::FormatErrorString(string name, object[] args)
0x1969bb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1969c0  pop
0x1969c1  ldloc.s  4
0x1969c3  ldstr    aAppverifierBas_1// "AppVerifier_BasicInfo_Description"
0x1969c8  ldc.i4.1
0x1969c9  newarr   [mscorlib]System.Object
0x1969ce  dup
0x1969cf  ldc.i4.0
0x1969d0  ldarg.2
0x1969d1  call     string System.Web.Util.AppVerifier::GetLocalizedDescriptionStringForError(valuetype System.Web.Util.AppVerifierErrorCode errorCode)
0x1969d6  stelem.ref
0x1969d7  call     string System.Web.Util.AppVerifier::FormatErrorString(string name, object[] args)
0x1969dc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1969e1  pop
0x1969e2  ldloc.s  4
0x1969e4  ldstr    aAppverifierBas_2// "AppVerifier_BasicInfo_ThreadInfo"
0x1969e9  ldc.i4.2
0x1969ea  newarr   [mscorlib]System.Object
0x1969ef  dup
0x1969f0  ldc.i4.0
0x1969f1  ldloc.3
0x1969f2  ldfld    int32 InvocationInfo::ThreadId
0x1969f7  box      [mscorlib]System.Int32
0x1969fc  stelem.ref
0x1969fd  dup
0x1969fe  ldc.i4.1
0x1969ff  ldloc.3
0x196a00  ldfld    valuetype [mscorlib]System.DateTimeOffset InvocationInfo::Timestamp
0x196a05  stloc.s  8
0x196a07  ldloca.s 8
0x196a09  call     instance valuetype [mscorlib]System.DateTimeOffset [mscorlib]System.DateTimeOffset::ToLocalTime()
0x196a0e  box      [mscorlib]System.DateTimeOffset
0x196a13  stelem.ref
0x196a14  call     string System.Web.Util.AppVerifier::FormatErrorString(string name, object[] args)
0x196a19  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x196a1e  pop
0x196a1f  ldloc.s  4
0x196a21  ldloc.3
0x196a22  ldfld    string InvocationInfo::StackTrace
0x196a27  callvirt instance string [mscorlib]System.Object::ToString()
0x196a2c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x196a31  pop
0x196a32  ldloc.s  4
0x196a34  ldstr    aAppverifierBeg// "AppVerifier_BeginMethodInfo_EntryMethod"
0x196a39  ldc.i4.1
0x196a3a  newarr   [mscorlib]System.Object
0x196a3f  dup
0x196a40  ldc.i4.0
0x196a41  ldarg.0
0x196a42  ldfld    class <>c__DisplayClass15_0 <>c__DisplayClass15_1::CS$<>8__locals1
0x196a47  ldfld    class [mscorlib]System.Delegate <>c__DisplayClass15_0::originalDelegate
0x196a4c  call     string System.Web.Util.AppVerifier::PrettyPrintDelegate(class [mscorlib]System.Delegate del)
0x196a51  stelem.ref
0x196a52  call     string System.Web.Util.AppVerifier::FormatErrorString(string name, object[] args)
0x196a57  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x196a5c  pop
0x196a5d  ldarg.0
0x196a5e  ldflda   valuetype [mscorlib]System.Nullable`1<valuetype System.Web.RequestNotification> <>c__DisplayClass15_1::currentNotification
0x196a63  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype System.Web.RequestNotification>::get_HasValue()
0x196a68  brfalse.s loc_196AA0
0x196a6a  ldloc.s  4
0x196a6c  ldstr    aAppverifierBeg_0// "AppVerifier_BeginMethodInfo_RequestNoti"...
0x196a71  ldc.i4.2
0x196a72  newarr   [mscorlib]System.Object
0x196a77  dup
0x196a78  ldc.i4.0
0x196a79  ldarg.0
0x196a7a  ldfld    valuetype [mscorlib]System.Nullable`1<valuetype System.Web.RequestNotification> <>c__DisplayClass15_1::currentNotification
0x196a7f  box      valuetype [mscorlib]System.Nullable`1<valuetype System.Web.RequestNotification>
0x196a84  stelem.ref
0x196a85  dup
0x196a86  ldc.i4.1
0x196a87  ldarg.0
0x196a88  ldfld    bool <>c__DisplayClass15_1::isPostNotification
0x196a8d  box      [mscorlib]System.Boolean
0x196a92  stelem.ref
0x196a93  call     string System.Web.Util.AppVerifier::FormatErrorString(string name, object[] args)
0x196a98  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x196a9d  pop
0x196a9e  br.s     loc_196AB8
0x196aa0  ldloc.s  4
0x196aa2  ldstr    aAppverifierBeg_1// "AppVerifier_BeginMethodInfo_RequestNoti"...
0x196aa7  ldc.i4.0
0x196aa8  newarr   [mscorlib]System.Object
0x196aad  call     string System.Web.Util.AppVerifier::FormatErrorString(string name, object[] args)
0x196ab2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x196ab7  pop
0x196ab8  ldloc.s  4
0x196aba  ldstr    aAppverifierBeg_2// "AppVerifier_BeginMethodInfo_CurrentHand"...
0x196abf  ldc.i4.1
0x196ac0  newarr   [mscorlib]System.Object
0x196ac5  dup
0x196ac6  ldc.i4.0
0x196ac7  ldarg.0
0x196ac8  ldfld    class [mscorlib]System.Type <>c__DisplayClass15_1::httpHandlerType
0x196acd  stelem.ref
0x196ace  call     string System.Web.Util.AppVerifier::FormatErrorString(string name, object[] args)
0x196ad3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x196ad8  pop
0x196ad9  ldloc.s  4
0x196adb  ldstr    aAppverifierBeg_3// "AppVerifier_BeginMethodInfo_ThreadInfo"
0x196ae0  ldc.i4.2
0x196ae1  newarr   [mscorlib]System.Object
0x196ae6  dup
0x196ae7  ldc.i4.0
0x196ae8  ldarg.0
0x196ae9  ldfld    class InvocationInfo <>c__DisplayClass15_1::beginHandlerInvocationInfo
0x196aee  ldfld    int32 InvocationInfo::ThreadId
0x196af3  box      [mscorlib]System.Int32
0x196af8  stelem.ref
0x196af9  dup
0x196afa  ldc.i4.1
0x196afb  ldarg.0
0x196afc  ldfld    class InvocationInfo <>c__DisplayClass15_1::beginHandlerInvocationInfo
0x196b01  ldfld    valuetype [mscorlib]System.DateTimeOffset InvocationInfo::Timestamp
0x196b06  stloc.s  8
0x196b08  ldloca.s 8
0x196b0a  call     instance valuetype [mscorlib]System.DateTimeOffset [mscorlib]System.DateTimeOffset::ToLocalTime()
0x196b0f  box      [mscorlib]System.DateTimeOffset
0x196b14  stelem.ref
0x196b15  call     string System.Web.Util.AppVerifier::FormatErrorString(string name, object[] args)
0x196b1a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x196b1f  pop
0x196b20  ldloc.s  4
0x196b22  ldarg.0
0x196b23  ldfld    class InvocationInfo <>c__DisplayClass15_1::beginHandlerInvocationInfo
0x196b28  ldfld    string InvocationInfo::StackTrace
0x196b2d  callvirt instance string [mscorlib]System.Object::ToString()
0x196b32  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x196b37  pop
0x196b38  ldarg.0
0x196b39  ldfld    class AsyncCallbackInvocationHelper <>c__DisplayClass15_1::asyncCallbackInvocationHelper
0x196b3e  ldloca.s 5
0x196b40  callvirt instance class InvocationInfo AsyncCallbackInvocationHelper::GetFirstInvocationInfo([out] int32& totalInvocationCount)
0x196b45  stloc.s  6
0x196b47  ldloc.s  4
0x196b49  ldstr    aAppverifierAsy// "AppVerifier_AsyncCallbackInfo_Invocatio"...
0x196b4e  ldc.i4.1
0x196b4f  newarr   [mscorlib]System.Object
0x196b54  dup
0x196b55  ldc.i4.0
0x196b56  ldloc.s  5
0x196b58  box      [mscorlib]System.Int32
0x196b5d  stelem.ref
0x196b5e  call     string System.Web.Util.AppVerifier::FormatErrorString(string name, object[] args)
0x196b63  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x196b68  pop
0x196b69  ldloc.s  6
0x196b6b  brfalse.s loc_196BC0
0x196b6d  ldloc.s  4
0x196b6f  ldstr    aAppverifierAsy_0// "AppVerifier_AsyncCallbackInfo_FirstInvo"...
0x196b74  ldc.i4.2
0x196b75  newarr   [mscorlib]System.Object
0x196b7a  dup
0x196b7b  ldc.i4.0
0x196b7c  ldloc.s  6
0x196b7e  ldfld    int32 InvocationInfo::ThreadId
0x196b83  box      [mscorlib]System.Int32
0x196b88  stelem.ref
0x196b89  dup
0x196b8a  ldc.i4.1
0x196b8b  ldloc.s  6
0x196b8d  ldfld    valuetype [mscorlib]System.DateTimeOffset InvocationInfo::Timestamp
0x196b92  stloc.s  8
0x196b94  ldloca.s 8
0x196b96  call     instance valuetype [mscorlib]System.DateTimeOffset [mscorlib]System.DateTimeOffset::ToLocalTime()
0x196b9b  box      [mscorlib]System.DateTimeOffset
0x196ba0  stelem.ref
0x196ba1  call     string System.Web.Util.AppVerifier::FormatErrorString(string name, object[] args)
0x196ba6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x196bab  pop
0x196bac  ldloc.s  4
0x196bae  ldloc.s  6
0x196bb0  ldfld    string InvocationInfo::StackTrace
0x196bb5  callvirt instance string [mscorlib]System.Object::ToString()
0x196bba  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x196bbf  pop
0x196bc0  ldarg.2
0x196bc1  ldloc.s  4
0x196bc3  callvirt instance string [mscorlib]System.Object::ToString()
0x196bc8  newobj   instance void System.Web.Util.AppVerifierException::.ctor(valuetype System.Web.Util.AppVerifierErrorCode errorCode, string message)
0x196bcd  stloc.s  7
0x196bcf  ldarg.0
0x196bd0  ldfld    class <>c__DisplayClass15_0 <>c__DisplayClass15_1::CS$<>8__locals1
0x196bd5  ldfld    class [mscorlib]System.Action`1<class System.Web.Util.AppVerifierException> <>c__DisplayClass15_0::errorHandler
0x196bda  ldloc.s  7
0x196bdc  callvirt instance void class [mscorlib]System.Action`1<class System.Web.Util.AppVerifierException>::Invoke(var<u1>)
0x196be1  ldloc.s  7
0x196be3  throw
0x196be4  ret
```
