# _ATL::CComCreator_ATL::CComObject_CVsShellExtHandler___::CreateInstance_::_1_::dtor$1

- ea: `0x180024da8`
- end: `0x180024db4`
- name: `_ATL::CComCreator_ATL::CComObject_CVsShellExtHandler___::CreateInstance_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800033f4`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator_ATL::CComObject_CVsShellExtHandler___::CreateInstance_::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  return ATL::CComContainedObject<CVsShellExtHandler>::~CComContainedObject<CVsShellExtHandler>(*(_QWORD *)(a2 + 32));
}

```

## disassembly

```asm
0x180024da8  mov     rcx, [rdx+20h]
0x180024daf  jmp     ??1?$CComContainedObject@VCVsShellExtHandler@@@ATL@@QEAA@XZ; ATL::CComContainedObject<CVsShellExtHandler>::~CComContainedObject<CVsShellExtHandler>(void)
```
