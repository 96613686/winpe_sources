# _ATL::CComCreator_ATL::CComAggObject_CVsShellExtHandler___::CreateInstance_::_1_::dtor$1

- ea: `0x180024d5b`
- end: `0x180024d6b`
- name: `_ATL::CComCreator_ATL::CComAggObject_CVsShellExtHandler___::CreateInstance_::_1_::dtor$1`
- size: `16`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800033f4`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator_ATL::CComAggObject_CVsShellExtHandler___::CreateInstance_::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  return ATL::CComContainedObject<CVsShellExtHandler>::~CComContainedObject<CVsShellExtHandler>(*(_QWORD *)(a2 + 40) + 16LL);
}

```

## disassembly

```asm
0x180024d5b  mov     rcx, [rdx+28h]
0x180024d62  add     rcx, 10h
0x180024d66  jmp     ??1?$CComContainedObject@VCVsShellExtHandler@@@ATL@@QEAA@XZ; ATL::CComContainedObject<CVsShellExtHandler>::~CComContainedObject<CVsShellExtHandler>(void)
```
