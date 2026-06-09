# Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::Refresh

- ea: `0x516d0`
- end: `0x51766`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::Refresh`
- size: `150`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x50b80`

## callees

- `0x12860`
- `0x13510`
- `0x38820`
- `0x4d110`
- `0x4d2f0`
- `0x51500`
- `0x516d0`

## string_xrefs

- `0x51717`: `Opening publisher Metaadata failed for `
- `0x51750`: `Unable to close temporary publisher handle in EventPublisher:Refresh`

## pseudocode

```c

```

## disassembly

```asm
0x516d0  ldc.i4.0
0x516d1  stloc.0
0x516d2  ldarg.0
0x516d3  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::initialized
0x516d8  brfalse  loc_5175D
0x516dd  ldarg.0
0x516de  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::isArchivedPublisher
0x516e3  brtrue.s loc_5175D
0x516e5  ldarg.0
0x516e6  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::context
0x516eb  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext::get_Session()
0x516f0  callvirt instance native int Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle::get_Handle()
0x516f5  ldarg.0
0x516f6  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::identifier
0x516fb  ldnull
0x516fc  ldc.i4.0
0x516fd  ldc.i4.0
0x516fe  call     native int Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::OpenPublisherMetadata(native int session, [hasfieldmarshal] string publisherIdentity, [hasfieldmarshal] string logfilePath, int32 locale, int32 flags)
0x51703  stloc.1
0x51704  ldloc.1
0x51705  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x5170a  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x5170f  brfalse.s loc_51740
0x51711  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x51716  stloc.2
0x51717  ldstr    aOpeningPublish// "Opening publisher Metaadata failed for "
0x5171c  ldarg.0
0x5171d  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::identifier
0x51722  call     string [mscorlib]System.String::Concat(string, string)
0x51727  ldloc.2
0x51728  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x5172d  ldarg.0
0x5172e  ldloc.2
0x5172f  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32)
0x51734  callvirt instance string [mscorlib]System.Exception::get_Message()
0x51739  stfld    string Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::publisherMetadataError
0x5173e  br.s     loc_51764
0x51740  ldc.i4.1
0x51741  stloc.0
0x51742  ldloc.1
0x51743  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::CloseHandle(native int eventHandle)
0x51748  brtrue.s loc_51764
0x5174a  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x5174f  stloc.3
0x51750  ldstr    aUnableToCloseT_6// "Unable to close temporary publisher han"...
0x51755  ldloc.3
0x51756  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x5175b  br.s     loc_51764
0x5175d  ldarg.0
0x5175e  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.EventPublisher::Initialize()
0x51763  stloc.0
0x51764  ldloc.0
0x51765  ret
```
