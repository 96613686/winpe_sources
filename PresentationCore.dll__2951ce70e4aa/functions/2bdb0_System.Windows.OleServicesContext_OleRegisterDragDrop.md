# System.Windows.OleServicesContext::OleRegisterDragDrop

- ea: `0x2bdb0`
- end: `0x2bdd4`
- name: `System.Windows.OleServicesContext::OleRegisterDragDrop`
- size: `36`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1b6a0`

## callees

- `0x2bdb0`
- `0x146e40`

## string_xrefs

- `0x2bdbc`: `OleServicesContext_ThreadMustBeSTA`

## pseudocode

```c

```

## disassembly

```asm
0x2bdb0  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x2bdb5  callvirt instance valuetype [mscorlib]System.Threading.ApartmentState [mscorlib]System.Threading.Thread::GetApartmentState()
0x2bdba  brfalse.s loc_2BDCC
0x2bdbc  ldstr    aOleservicescon// "OleServicesContext_ThreadMustBeSTA"
0x2bdc1  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x2bdc6  newobj   instance void [mscorlib]System.Threading.ThreadStateException::.ctor(string)
0x2bdcb  throw
0x2bdcc  ldarg.1
0x2bdcd  ldarg.2
0x2bdce  call     int32 [WindowsBase]MS.Win32.UnsafeNativeMethods::RegisterDragDrop(valuetype [mscorlib]System.Runtime.InteropServices.HandleRef, class [WindowsBase]MS.Win32.UnsafeNativeMethods/IOleDropTarget)
0x2bdd3  ret
```
