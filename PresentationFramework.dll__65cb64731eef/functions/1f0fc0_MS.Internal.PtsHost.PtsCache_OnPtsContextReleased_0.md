# MS.Internal.PtsHost.PtsCache::OnPtsContextReleased_0

- ea: `0x1f0fc0`
- end: `0x1f11c8`
- name: `MS.Internal.PtsHost.PtsCache::OnPtsContextReleased_0`
- size: `520`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x1f0e00`
- `0x1f0fb0`

## callees

- `0x1f0fc0`
- `0x1f2330`
- `0x1f2890`
- `0x1f28a0`
- `0x1f3a10`
- `0x206c80`
- `0x206f00`
- `0x206f20`

## string_xrefs

- `0x1f107d`: `PtsContext has been already disposed.`
- `0x1f1156`: `Installed Objects handle is not valid.`

## pseudocode

```c

```

## disassembly

```asm
0x1f0fc0  ldarg.0
0x1f0fc1  ldfld    object MS.Internal.PtsHost.PtsCache::_lock
0x1f0fc6  stloc.1
0x1f0fc7  ldc.i4.0
0x1f0fc8  stloc.2
0x1f0fc9  ldloc.1
0x1f0fca  ldloca.s 2
0x1f0fcc  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x1f0fd1  ldarg.0
0x1f0fd2  ldfld    class [mscorlib]System.Collections.Generic.List`1<class MS.Internal.PtsHost.PtsContext> MS.Internal.PtsHost.PtsCache::_releaseQueue
0x1f0fd7  brfalse  loc_1F10B1
0x1f0fdc  ldarg.0
0x1f0fdd  ldfld    class [mscorlib]System.Collections.Generic.List`1<class MS.Internal.PtsHost.PtsContext> MS.Internal.PtsHost.PtsCache::_releaseQueue
0x1f0fe2  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class MS.Internal.PtsHost.PtsContext>::GetEnumerator()
0x1f0fe7  stloc.3
0x1f0fe8  br       loc_1F108E
0x1f0fed  ldloca.s 3
0x1f0fef  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class MS.Internal.PtsHost.PtsContext>::get_Current()
0x1f0ff4  stloc.s  4
0x1f0ff6  ldc.i4.0
0x1f0ff7  stloc.0
0x1f0ff8  br.s     loc_1F104D
0x1f0ffa  ldarg.0
0x1f0ffb  ldfld    class [mscorlib]System.Collections.Generic.List`1<class ContextDesc> MS.Internal.PtsHost.PtsCache::_contextPool
0x1f1000  ldloc.0
0x1f1001  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class ContextDesc>::get_Item(!!T0)
0x1f1006  ldfld    class MS.Internal.PtsHost.PtsHost ContextDesc::PtsHost
0x1f100b  callvirt instance native int MS.Internal.PtsHost.PtsHost::get_Context()
0x1f1010  ldloc.s  4
0x1f1012  callvirt instance native int MS.Internal.PtsHost.PtsContext::get_Context()
0x1f1017  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x1f101c  brfalse.s loc_1F1049
0x1f101e  ldarg.0
0x1f101f  ldfld    class [mscorlib]System.Collections.Generic.List`1<class ContextDesc> MS.Internal.PtsHost.PtsCache::_contextPool
0x1f1024  ldloc.0
0x1f1025  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class ContextDesc>::get_Item(!!T0)
0x1f102a  ldnull
0x1f102b  newobj   instance void [mscorlib]System.WeakReference::.ctor(object)
0x1f1030  stfld    class [mscorlib]System.WeakReference ContextDesc::Owner
0x1f1035  ldarg.0
0x1f1036  ldfld    class [mscorlib]System.Collections.Generic.List`1<class ContextDesc> MS.Internal.PtsHost.PtsCache::_contextPool
0x1f103b  ldloc.0
0x1f103c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class ContextDesc>::get_Item(!!T0)
0x1f1041  ldc.i4.0
0x1f1042  stfld    bool ContextDesc::InUse
0x1f1047  br.s     loc_1F105B
0x1f1049  ldloc.0
0x1f104a  ldc.i4.1
0x1f104b  add
0x1f104c  stloc.0
0x1f104d  ldloc.0
0x1f104e  ldarg.0
0x1f104f  ldfld    class [mscorlib]System.Collections.Generic.List`1<class ContextDesc> MS.Internal.PtsHost.PtsCache::_contextPool
0x1f1054  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class ContextDesc>::get_Count()
0x1f1059  blt.s    loc_1F0FFA
0x1f105b  ldloc.0
0x1f105c  ldarg.0
0x1f105d  ldfld    class [mscorlib]System.Collections.Generic.List`1<class ContextDesc> MS.Internal.PtsHost.PtsCache::_contextPool
0x1f1062  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class ContextDesc>::get_Count()
0x1f1067  clt
0x1f1069  ldstr    aPtscontextNotF// "PtsContext not found in the context poo"...
0x1f106e  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool, string)
0x1f1073  ldloc.s  4
0x1f1075  callvirt instance bool MS.Internal.PtsHost.PtsContext::get_Disposed()
0x1f107a  ldc.i4.0
0x1f107b  ceq
0x1f107d  ldstr    aPtscontextHasB// "PtsContext has been already disposed."
0x1f1082  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool, string)
0x1f1087  ldloc.s  4
0x1f1089  callvirt instance void MS.Internal.PtsHost.PtsContext::Dispose()
0x1f108e  ldloca.s 3
0x1f1090  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class MS.Internal.PtsHost.PtsContext>::MoveNext()
0x1f1095  brtrue   loc_1F0FED
0x1f109a  leave.s  loc_1F10AA
0x1f109c  ldloca.s 3
0x1f109e  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class MS.Internal.PtsHost.PtsContext>
0x1f10a4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f10a9  endfinally
0x1f10aa  ldarg.0
0x1f10ab  ldnull
0x1f10ac  stfld    class [mscorlib]System.Collections.Generic.List`1<class MS.Internal.PtsHost.PtsContext> MS.Internal.PtsHost.PtsCache::_releaseQueue
0x1f10b1  leave.s  loc_1F10BD
0x1f10b3  ldloc.2
0x1f10b4  brfalse.s loc_1F10BC
0x1f10b6  ldloc.1
0x1f10b7  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x1f10bc  endfinally
0x1f10bd  ldarg.1
0x1f10be  brfalse  loc_1F11C7
0x1f10c3  ldarg.0
0x1f10c4  ldfld    class [mscorlib]System.Collections.Generic.List`1<class ContextDesc> MS.Internal.PtsHost.PtsCache::_contextPool
0x1f10c9  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class ContextDesc>::get_Count()
0x1f10ce  ldc.i4.4
0x1f10cf  ble      loc_1F11C7
0x1f10d4  ldc.i4.4
0x1f10d5  stloc.0
0x1f10d6  br       loc_1F11B6
0x1f10db  ldarg.0
0x1f10dc  ldfld    class [mscorlib]System.Collections.Generic.List`1<class ContextDesc> MS.Internal.PtsHost.PtsCache::_contextPool
0x1f10e1  ldloc.0
0x1f10e2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class ContextDesc>::get_Item(!!T0)
0x1f10e7  ldfld    bool ContextDesc::InUse
0x1f10ec  brtrue   loc_1F11B2
0x1f10f1  ldarg.0
0x1f10f2  ldfld    class [mscorlib]System.Collections.Generic.List`1<class ContextDesc> MS.Internal.PtsHost.PtsCache::_contextPool
0x1f10f7  ldloc.0
0x1f10f8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class ContextDesc>::get_Item(!!T0)
0x1f10fd  ldfld    class MS.Internal.PtsHost.PtsHost ContextDesc::PtsHost
0x1f1102  callvirt instance native int MS.Internal.PtsHost.PtsHost::get_Context()
0x1f1107  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x1f110c  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x1f1111  ldstr    aPtsContextHand// "PTS Context handle is not valid."
0x1f1116  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool, string)
0x1f111b  ldarg.0
0x1f111c  ldfld    class [mscorlib]System.Collections.Generic.List`1<class ContextDesc> MS.Internal.PtsHost.PtsCache::_contextPool
0x1f1121  ldloc.0
0x1f1122  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class ContextDesc>::get_Item(!!T0)
0x1f1127  ldfld    class MS.Internal.PtsHost.PtsHost ContextDesc::PtsHost
0x1f112c  callvirt instance native int MS.Internal.PtsHost.PtsHost::get_Context()
0x1f1131  call     int32 MS.Internal.PtsHost.UnsafeNativeMethods.PTS::DestroyDocContext(native int pfscontext)
0x1f1136  call     void MS.Internal.PtsHost.UnsafeNativeMethods.PTS::Validate(int32 fserr)
0x1f113b  ldarg.0
0x1f113c  ldfld    class [mscorlib]System.Collections.Generic.List`1<class ContextDesc> MS.Internal.PtsHost.PtsCache::_contextPool
0x1f1141  ldloc.0
0x1f1142  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class ContextDesc>::get_Item(!!T0)
0x1f1147  ldfld    native int ContextDesc::InstalledObjects
0x1f114c  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x1f1151  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x1f1156  ldstr    aInstalledObjec// "Installed Objects handle is not valid."
0x1f115b  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool, string)
0x1f1160  ldarg.0
0x1f1161  ldfld    class [mscorlib]System.Collections.Generic.List`1<class ContextDesc> MS.Internal.PtsHost.PtsCache::_contextPool
0x1f1166  ldloc.0
0x1f1167  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class ContextDesc>::get_Item(!!T0)
0x1f116c  ldfld    native int ContextDesc::InstalledObjects
0x1f1171  call     int32 MS.Internal.PtsHost.UnsafeNativeMethods.PTS::DestroyInstalledObjectsInfo(native int pInstalledObjects)
0x1f1176  call     void MS.Internal.PtsHost.UnsafeNativeMethods.PTS::Validate(int32 fserr)
0x1f117b  ldarg.0
0x1f117c  ldfld    class [mscorlib]System.Collections.Generic.List`1<class ContextDesc> MS.Internal.PtsHost.PtsCache::_contextPool
0x1f1181  ldloc.0
0x1f1182  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class ContextDesc>::get_Item(!!T0)
0x1f1187  ldfld    class [PresentationCore]MS.Internal.TextFormatting.TextPenaltyModule ContextDesc::TextPenaltyModule
0x1f118c  brfalse.s loc_1F11A4
0x1f118e  ldarg.0
0x1f118f  ldfld    class [mscorlib]System.Collections.Generic.List`1<class ContextDesc> MS.Internal.PtsHost.PtsCache::_contextPool
0x1f1194  ldloc.0
0x1f1195  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class ContextDesc>::get_Item(!!T0)
0x1f119a  ldfld    class [PresentationCore]MS.Internal.TextFormatting.TextPenaltyModule ContextDesc::TextPenaltyModule
0x1f119f  callvirt instance void [PresentationCore]MS.Internal.TextFormatting.TextPenaltyModule::Dispose()
0x1f11a4  ldarg.0
0x1f11a5  ldfld    class [mscorlib]System.Collections.Generic.List`1<class ContextDesc> MS.Internal.PtsHost.PtsCache::_contextPool
0x1f11aa  ldloc.0
0x1f11ab  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class ContextDesc>::RemoveAt(int32)
0x1f11b0  br.s     loc_1F11B6
0x1f11b2  ldloc.0
0x1f11b3  ldc.i4.1
0x1f11b4  add
0x1f11b5  stloc.0
0x1f11b6  ldloc.0
0x1f11b7  ldarg.0
0x1f11b8  ldfld    class [mscorlib]System.Collections.Generic.List`1<class ContextDesc> MS.Internal.PtsHost.PtsCache::_contextPool
0x1f11bd  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class ContextDesc>::get_Count()
0x1f11c2  blt      loc_1F10DB
0x1f11c7  ret
```
