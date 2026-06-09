# Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::Initialize

- ea: `0x51500`
- end: `0x516cb`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::Initialize`
- size: `459`
- prototype: ``
- caller_count: `12`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x516d0`
- `0x51790`
- `0x51800`
- `0x51890`
- `0x51920`
- `0x51a00`
- `0x51ae0`
- `0x51b40`
- `0x51ba0`
- `0x51c00`
- `0x51c60`
- `0x52010`

## callees

- `0x12670`
- `0x126b0`
- `0x12840`
- `0x12860`
- `0x13430`
- `0x13510`
- `0x36350`
- `0x38820`
- `0x395e0`
- `0x4d2f0`
- `0x4d310`
- `0x51500`
- `0x51890`

## string_xrefs

- `0x51587`: `Opening publisher Metaadata failed for `

## pseudocode

```c

```

## disassembly

```asm
0x51500  ldarg.0
0x51501  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::initialized
0x51506  stloc.0
0x51507  ldc.i4.s 0x10
0x51509  stloc.1
0x5150a  ldc.i4.0
0x5150b  stloc.2
0x5150c  ldarg.0
0x5150d  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::initialized
0x51512  brtrue   loc_516C9
0x51517  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::PrepareConstrainedRegions()
0x5151c  leave    loc_516C9
0x51521  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x51526  stloc.3
0x51527  ldarg.0
0x51528  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::identifier
0x5152d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x51532  brfalse.s loc_5159F
0x51534  ldarg.0
0x51535  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::context
0x5153a  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::get_Session()
0x5153f  callvirt instance native int Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle::get_Handle()
0x51544  ldarg.0
0x51545  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::identifier
0x5154a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5154f  brtrue.s loc_51559
0x51551  ldarg.0
0x51552  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::identifier
0x51557  br.s     loc_5155A
0x51559  ldnull
0x5155a  ldnull
0x5155b  ldc.i4.0
0x5155c  ldc.i4.0
0x5155d  call     native int Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::OpenPublisherMetadata(native int session, [hasfieldmarshal] string publisherIdentity, [hasfieldmarshal] string logfilePath, int32 locale, int32 flags)
0x51562  stloc.3
0x51563  ldloc.3
0x51564  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x51569  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x5156e  brfalse.s loc_515D5
0x51570  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x51575  stloc.2
0x51576  ldarg.0
0x51577  ldloc.2
0x51578  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32)
0x5157d  callvirt instance string [mscorlib]System.Exception::get_Message()
0x51582  stfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::publisherMetadataError
0x51587  ldstr    aOpeningPublish// "Opening publisher Metaadata failed for "
0x5158c  ldarg.0
0x5158d  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::identifier
0x51592  call     string [mscorlib]System.String::Concat(string, string)
0x51597  ldloc.2
0x51598  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x5159d  br.s     loc_515D5
0x5159f  ldarg.0
0x515a0  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::context
0x515a5  ldarg.0
0x515a6  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::identifier
0x515ab  callvirt instance native int Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::GetPublisherHandle(string publisherIdentifier)
0x515b0  stloc.3
0x515b1  ldloc.3
0x515b2  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x515b7  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x515bc  brfalse.s loc_515D5
0x515be  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x515c3  stloc.2
0x515c4  ldarg.0
0x515c5  ldloc.2
0x515c6  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32)
0x515cb  callvirt instance string [mscorlib]System.Exception::get_Message()
0x515d0  stfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::publisherMetadataError
0x515d5  ldloc.3
0x515d6  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x515db  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x515e0  brfalse  loc_516C8
0x515e5  ldarg.0
0x515e6  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::identifier
0x515eb  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x515f0  brfalse.s loc_515FE
0x515f2  ldarg.0
0x515f3  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::safePublisherHandle
0x515f8  ldloc.3
0x515f9  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle::InitHandle(native int crimsonHandle)
0x515fe  ldloca.s 4
0x51600  initobj  Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x51606  sizeof   Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x5160c  ldloc.1
0x5160d  add
0x5160e  stloc.s  5
0x51610  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.SafeGlobalHandle::.ctor()
0x51615  stloc.s  6
0x51617  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x5161c  stloc.s  7
0x5161e  ldloc.s  5
0x51620  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::AllocHGlobal(int32)
0x51625  stloc.s  7
0x51627  ldc.i4.0
0x51628  stloc.s  8
0x5162a  ldloc.s  7
0x5162c  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x51631  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x51636  brfalse.s loc_51641
0x51638  ldloc.s  6
0x5163a  ldloc.s  7
0x5163c  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.SafeGlobalHandle::InitHandle(native int inHandle)
0x51641  ldloc.3
0x51642  ldc.i4.0
0x51643  ldc.i4.0
0x51644  ldloc.s  5
0x51646  ldloc.s  7
0x51648  ldloca.s 8
0x5164a  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::GetPublisherMetadataPropertyBuffer(native int publisherMetadata, [hasfieldmarshal] valuetype Microsoft.Windows.ManagementUI.CombinedControls.EventPublisherMetadataPropertyID propertyId, int32 flags, int32 bufferSize, native int publisherMetadataPropertyBuffer, int32& publisherMetadataPropertyBufferUsed)
0x5164f  stloc.0
0x51650  ldloc.0
0x51651  brtrue.s loc_51671
0x51653  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x51658  stloc.2
0x51659  ldstr    aPublishermetad_0// "PublisherMetadataPublisherGuid failed "
0x5165e  ldarg.0
0x5165f  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::identifier
0x51664  call     string [mscorlib]System.String::Concat(string, string)
0x51669  ldloc.2
0x5166a  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x5166f  br.s     loc_516B2
0x51671  ldloc.s  7
0x51673  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x51678  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5167d  call     object [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStructure(native int, class [mscorlib]System.Type)
0x51682  unbox.any Microsoft.Windows.ManagementUI.CombinedControls.EventVariant
0x51687  stloc.s  4
0x51689  ldloc.s  4
0x5168b  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::type
0x51690  ldc.i4.s 0xF
0x51692  bne.un.s loc_516A8
0x51694  ldarg.0
0x51695  ldloc.s  4
0x51697  ldfld    native int Microsoft.Windows.ManagementUI.CombinedControls.EventVariant::EvtHandle
0x5169c  call     valuetype [mscorlib]System.Guid Microsoft.Windows.ManagementUI.CombinedControls.CEventsCommon::PtrToGuid(native int guidPtr)
0x516a1  stfld    valuetype [mscorlib]System.Guid Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::publisherGuid
0x516a6  br.s     loc_516B2
0x516a8  ldstr    aWrongTypeRecei// "Wrong type received for PublisherMetada"...
0x516ad  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x516b2  ldloc.s  6
0x516b4  callvirt instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::Close()
0x516b9  ldc.i4.1
0x516ba  stloc.0
0x516bb  ldarg.0
0x516bc  ldc.i4.1
0x516bd  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::initialized
0x516c2  ldarg.0
0x516c3  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::GetPublisherLocalizedName()
0x516c8  endfinally
0x516c9  ldloc.0
0x516ca  ret
```
