# System.Windows.Interop.HwndTarget::AttachToHwnd

- ea: `0x628b0`
- end: `0x62965`
- name: `System.Windows.Interop.HwndTarget::AttachToHwnd`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x62520`

## callees

- `0x628b0`
- `0x62970`
- `0x64540`
- `0x106440`
- `0x106460`
- `0x146e40`
- `0x14b3d0`

## string_xrefs

- `0x62909`: `HwndTarget_InvalidWindowThread`
- `0x62935`: `HwndTarget_WindowAlreadyHasContent`

## pseudocode

```c

```

## disassembly

```asm
0x628b0  ldc.i4.0
0x628b1  stloc.2
0x628b2  ldarg.0
0x628b3  ldarg.1
0x628b4  newobj   instance void [mscorlib]System.Runtime.InteropServices.HandleRef::.ctor(object, native int)
0x628b9  ldloca.s 2
0x628bb  call     int32 [WindowsBase]MS.Win32.UnsafeNativeMethods::GetWindowThreadProcessId(valuetype [mscorlib]System.Runtime.InteropServices.HandleRef, int32&)
0x628c0  stloc.1
0x628c1  ldarg.0
0x628c2  ldarg.1
0x628c3  newobj   instance void [mscorlib]System.Runtime.InteropServices.HandleRef::.ctor(object, native int)
0x628c8  call     bool [WindowsBase]MS.Win32.UnsafeNativeMethods::IsWindow(valuetype [mscorlib]System.Runtime.InteropServices.HandleRef)
0x628cd  brtrue.s loc_628E4
0x628cf  ldstr    aHwndtargetInva// "HwndTarget_InvalidWindowHandle"
0x628d4  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x628d9  ldstr    aHwnd// "hwnd"
0x628de  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x628e3  throw
0x628e4  ldloc.2
0x628e5  call     int32 [WindowsBase]MS.Win32.SafeNativeMethods::GetCurrentProcessId()
0x628ea  beq.s    loc_62901
0x628ec  ldstr    aHwndtargetInva_0// "HwndTarget_InvalidWindowProcess"
0x628f1  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x628f6  ldstr    aHwnd// "hwnd"
0x628fb  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x62900  throw
0x62901  ldloc.1
0x62902  call     int32 [WindowsBase]MS.Win32.SafeNativeMethods::GetCurrentThreadId()
0x62907  beq.s    loc_6291E
0x62909  ldstr    aHwndtargetInva_1// "HwndTarget_InvalidWindowThread"
0x6290e  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x62913  ldstr    aHwnd// "hwnd"
0x62918  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x6291d  throw
0x6291e  ldarg.1
0x6291f  call     int32 System.Windows.Interop.HwndTarget::VisualTarget_AttachToHwnd(native int hwnd)
0x62924  stloc.0
0x62925  ldloc.0
0x62926  call     bool MS.Internal.HRESULT::Failed(int32 hr)
0x6292b  brfalse.s loc_6294B
0x6292d  ldloc.0
0x6292e  ldc.i4   0x80070005
0x62933  bne.un.s loc_62945
0x62935  ldstr    aHwndtargetWind// "HwndTarget_WindowAlreadyHasContent"
0x6293a  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x6293f  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x62944  throw
0x62945  ldloc.0
0x62946  call     void MS.Internal.HRESULT::Check(int32 hr)
0x6294b  ldarg.0
0x6294c  call     instance void System.Windows.Interop.HwndTarget::EnsureNotificationWindow()
0x62951  ldsfld   class NotificationWindowHelper System.Windows.Interop.HwndTarget::_notificationWindowHelper
0x62956  ldarg.0
0x62957  callvirt instance void NotificationWindowHelper::AttachHwndTarget(class System.Windows.Interop.HwndTarget hwndTarget)
0x6295c  ldarg.1
0x6295d  ldc.i4.0
0x6295e  call     bool [WindowsBase]MS.Win32.UnsafeNativeMethods::WTSRegisterSessionNotification(native int, unsigned int32)
0x62963  pop
0x62964  ret
```
