# System.Windows.OleServicesContext::OleRevokeDragDrop

- ea: `0x2bde0`
- end: `0x2be03`
- name: `System.Windows.OleServicesContext::OleRevokeDragDrop`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1b6d0`

## callees

- `0x2bde0`
- `0x146e40`

## string_xrefs

- `0x2bdec`: `OleServicesContext_ThreadMustBeSTA`

## pseudocode

```c

```

## disassembly

```asm
0x2bde0  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x2bde5  callvirt instance valuetype [mscorlib]System.Threading.ApartmentState [mscorlib]System.Threading.Thread::GetApartmentState()
0x2bdea  brfalse.s loc_2BDFC
0x2bdec  ldstr    aOleservicescon// "OleServicesContext_ThreadMustBeSTA"
0x2bdf1  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x2bdf6  newobj   instance void [mscorlib]System.Threading.ThreadStateException::.ctor(string)
0x2bdfb  throw
0x2bdfc  ldarg.1
0x2bdfd  call     int32 [WindowsBase]MS.Win32.UnsafeNativeMethods::RevokeDragDrop(valuetype [mscorlib]System.Runtime.InteropServices.HandleRef)
0x2be02  ret
```
