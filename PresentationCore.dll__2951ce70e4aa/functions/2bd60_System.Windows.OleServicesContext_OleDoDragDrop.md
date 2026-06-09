# System.Windows.OleServicesContext::OleDoDragDrop

- ea: `0x2bd60`
- end: `0x2bdaf`
- name: `System.Windows.OleServicesContext::OleDoDragDrop`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1b730`

## callees

- `0x2bd60`
- `0x39c10`
- `0x146e40`

## string_xrefs

- `0x2bd6c`: `OleServicesContext_ThreadMustBeSTA`

## pseudocode

```c

```

## disassembly

```asm
0x2bd60  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x2bd65  callvirt instance valuetype [mscorlib]System.Threading.ApartmentState [mscorlib]System.Threading.Thread::GetApartmentState()
0x2bd6a  brfalse.s loc_2BD7C
0x2bd6c  ldstr    aOleservicescon// "OleServicesContext_ThreadMustBeSTA"
0x2bd71  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x2bd76  newobj   instance void [mscorlib]System.Threading.ThreadStateException::.ctor(string)
0x2bd7b  throw
0x2bd7c  call     class [WindowsBase]System.Windows.Threading.Dispatcher [WindowsBase]System.Windows.Threading.Dispatcher::get_CurrentDispatcher()
0x2bd81  callvirt instance object [WindowsBase]System.Windows.Threading.Dispatcher::get_InputManager()
0x2bd86  castclass System.Windows.Input.InputManager
0x2bd8b  stloc.0
0x2bd8c  ldloc.0
0x2bd8d  brfalse.s loc_2BD96
0x2bd8f  ldloc.0
0x2bd90  ldc.i4.1
0x2bd91  callvirt instance void System.Windows.Input.InputManager::set_InDragDrop(bool value)
0x2bd96  nop
0x2bd97  ldarg.1
0x2bd98  ldarg.2
0x2bd99  ldarg.3
0x2bd9a  ldarg.s  4
0x2bd9c  call     void [WindowsBase]MS.Win32.UnsafeNativeMethods::DoDragDrop(class [System]System.Runtime.InteropServices.ComTypes.IDataObject, class [WindowsBase]MS.Win32.UnsafeNativeMethods/IOleDropSource, int32, int32[])
0x2bda1  leave.s  loc_2BDAE
0x2bda3  ldloc.0
0x2bda4  brfalse.s loc_2BDAD
0x2bda6  ldloc.0
0x2bda7  ldc.i4.0
0x2bda8  callvirt instance void System.Windows.Input.InputManager::set_InDragDrop(bool value)
0x2bdad  endfinally
0x2bdae  ret
```
