# System.Windows.OleServicesContext::OleIsCurrentClipboard

- ea: `0x2bd30`
- end: `0x2bd53`
- name: `System.Windows.OleServicesContext::OleIsCurrentClipboard`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x15790`

## callees

- `0x2bd30`
- `0x146e40`

## string_xrefs

- `0x2bd3c`: `OleServicesContext_ThreadMustBeSTA`

## pseudocode

```c

```

## disassembly

```asm
0x2bd30  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x2bd35  callvirt instance valuetype [mscorlib]System.Threading.ApartmentState [mscorlib]System.Threading.Thread::GetApartmentState()
0x2bd3a  brfalse.s loc_2BD4C
0x2bd3c  ldstr    aOleservicescon// "OleServicesContext_ThreadMustBeSTA"
0x2bd41  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x2bd46  newobj   instance void [mscorlib]System.Threading.ThreadStateException::.ctor(string)
0x2bd4b  throw
0x2bd4c  ldarg.1
0x2bd4d  call     int32 [WindowsBase]MS.Win32.UnsafeNativeMethods::OleIsCurrentClipboard(class [System]System.Runtime.InteropServices.ComTypes.IDataObject)
0x2bd52  ret
```
