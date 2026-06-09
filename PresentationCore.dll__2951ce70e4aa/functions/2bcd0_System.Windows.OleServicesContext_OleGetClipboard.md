# System.Windows.OleServicesContext::OleGetClipboard

- ea: `0x2bcd0`
- end: `0x2bcf3`
- name: `System.Windows.OleServicesContext::OleGetClipboard`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x15a00`

## callees

- `0x2bcd0`
- `0x146e40`

## string_xrefs

- `0x2bcdc`: `OleServicesContext_ThreadMustBeSTA`

## pseudocode

```c

```

## disassembly

```asm
0x2bcd0  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x2bcd5  callvirt instance valuetype [mscorlib]System.Threading.ApartmentState [mscorlib]System.Threading.Thread::GetApartmentState()
0x2bcda  brfalse.s loc_2BCEC
0x2bcdc  ldstr    aOleservicescon// "OleServicesContext_ThreadMustBeSTA"
0x2bce1  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x2bce6  newobj   instance void [mscorlib]System.Threading.ThreadStateException::.ctor(string)
0x2bceb  throw
0x2bcec  ldarg.1
0x2bced  call     int32 [WindowsBase]MS.Win32.UnsafeNativeMethods::OleGetClipboard(class [System]System.Runtime.InteropServices.ComTypes.IDataObject&)
0x2bcf2  ret
```
