# System.Windows.OleServicesContext::OnDispatcherShutdown

- ea: `0x2be80`
- end: `0x2bea4`
- name: `System.Windows.OleServicesContext::OnDispatcherShutdown`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update`

## callees

- `0x2be80`
- `0x2bec0`
- `0x146e40`

## string_xrefs

- `0x2be8c`: `OleServicesContext_ThreadMustBeSTA`

## pseudocode

```c

```

## disassembly

```asm
0x2be80  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x2be85  callvirt instance valuetype [mscorlib]System.Threading.ApartmentState [mscorlib]System.Threading.Thread::GetApartmentState()
0x2be8a  brfalse.s loc_2BE9C
0x2be8c  ldstr    aOleservicescon// "OleServicesContext_ThreadMustBeSTA"
0x2be91  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x2be96  newobj   instance void [mscorlib]System.Threading.ThreadStateException::.ctor(string)
0x2be9b  throw
0x2be9c  ldarg.0
0x2be9d  call     instance int32 System.Windows.OleServicesContext::OleUninitialize()
0x2bea2  pop
0x2bea3  ret
```
