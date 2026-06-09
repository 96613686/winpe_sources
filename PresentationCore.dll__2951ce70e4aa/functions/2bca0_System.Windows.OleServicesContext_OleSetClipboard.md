# System.Windows.OleServicesContext::OleSetClipboard

- ea: `0x2bca0`
- end: `0x2bcc3`
- name: `System.Windows.OleServicesContext::OleSetClipboard`
- size: `35`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x153d0`
- `0x15840`

## callees

- `0x2bca0`
- `0x146e40`

## string_xrefs

- `0x2bcac`: `OleServicesContext_ThreadMustBeSTA`

## pseudocode

```c

```

## disassembly

```asm
0x2bca0  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x2bca5  callvirt instance valuetype [mscorlib]System.Threading.ApartmentState [mscorlib]System.Threading.Thread::GetApartmentState()
0x2bcaa  brfalse.s loc_2BCBC
0x2bcac  ldstr    aOleservicescon// "OleServicesContext_ThreadMustBeSTA"
0x2bcb1  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x2bcb6  newobj   instance void [mscorlib]System.Threading.ThreadStateException::.ctor(string)
0x2bcbb  throw
0x2bcbc  ldarg.1
0x2bcbd  call     int32 [WindowsBase]MS.Win32.UnsafeNativeMethods::OleSetClipboard(class [System]System.Runtime.InteropServices.ComTypes.IDataObject)
0x2bcc2  ret
```
