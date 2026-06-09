# System.Windows.OleServicesContext::OleFlushClipboard

- ea: `0x2bd00`
- end: `0x2bd22`
- name: `System.Windows.OleServicesContext::OleFlushClipboard`
- size: `34`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x154b0`

## callees

- `0x2bd00`
- `0x146e40`

## string_xrefs

- `0x2bd0c`: `OleServicesContext_ThreadMustBeSTA`

## pseudocode

```c

```

## disassembly

```asm
0x2bd00  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x2bd05  callvirt instance valuetype [mscorlib]System.Threading.ApartmentState [mscorlib]System.Threading.Thread::GetApartmentState()
0x2bd0a  brfalse.s loc_2BD1C
0x2bd0c  ldstr    aOleservicescon// "OleServicesContext_ThreadMustBeSTA"
0x2bd11  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x2bd16  newobj   instance void [mscorlib]System.Threading.ThreadStateException::.ctor(string)
0x2bd1b  throw
0x2bd1c  call     int32 [WindowsBase]MS.Win32.UnsafeNativeMethods::OleFlushClipboard()
0x2bd21  ret
```
