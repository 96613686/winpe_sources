# System.Windows.OleServicesContext::SetDispatcherThread

- ea: `0x2be10`
- end: `0x2be71`
- name: `System.Windows.OleServicesContext::SetDispatcherThread`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x2bc60`

## callees

- `0x2be10`
- `0x2beb0`
- `0x146e40`
- `0x146e70`

## string_xrefs

- `0x2be1c`: `OleServicesContext_ThreadMustBeSTA`
- `0x2be3b`: `OleServicesContext_oleInitializeFailure`

## pseudocode

```c

```

## disassembly

```asm
0x2be10  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x2be15  callvirt instance valuetype [mscorlib]System.Threading.ApartmentState [mscorlib]System.Threading.Thread::GetApartmentState()
0x2be1a  brfalse.s loc_2BE2C
0x2be1c  ldstr    aOleservicescon// "OleServicesContext_ThreadMustBeSTA"
0x2be21  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x2be26  newobj   instance void [mscorlib]System.Threading.ThreadStateException::.ctor(string)
0x2be2b  throw
0x2be2c  ldarg.0
0x2be2d  call     instance int32 System.Windows.OleServicesContext::OleInitialize()
0x2be32  stloc.0
0x2be33  ldloc.0
0x2be34  call     bool [WindowsBase]MS.Win32.NativeMethods::Succeeded(int32)
0x2be39  brtrue.s loc_2BE5A
0x2be3b  ldstr    aOleservicescon_0// "OleServicesContext_oleInitializeFailure"
0x2be40  ldc.i4.1
0x2be41  newarr   [mscorlib]System.Object
0x2be46  dup
0x2be47  ldc.i4.0
0x2be48  ldloc.0
0x2be49  box      [mscorlib]System.Int32
0x2be4e  stelem.ref
0x2be4f  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x2be54  newobj   instance void [mscorlib]System.SystemException::.ctor(string)
0x2be59  throw
0x2be5a  call     class [WindowsBase]System.Windows.Threading.Dispatcher [WindowsBase]System.Windows.Threading.Dispatcher::get_CurrentDispatcher()
0x2be5f  ldarg.0
0x2be60  ldftn    instance void System.Windows.OleServicesContext::OnDispatcherShutdown(object sender, class [mscorlib]System.EventArgs args)
0x2be66  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x2be6b  callvirt instance void [WindowsBase]System.Windows.Threading.Dispatcher::add_ShutdownFinished(class [mscorlib]System.EventHandler)
0x2be70  ret
```
