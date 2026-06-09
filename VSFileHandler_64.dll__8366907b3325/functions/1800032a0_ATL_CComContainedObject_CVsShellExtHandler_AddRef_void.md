# ATL::CComContainedObject<CVsShellExtHandler>::AddRef(void)

- ea: `0x1800032a0`
- end: `0x1800032ab`
- name: `?AddRef@?$CComContainedObject@VCVsShellExtHandler@@@ATL@@UEAAKXZ`
- size: `11`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003470`
- `0x1800034a0`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CVsShellExtHandler>::AddRef(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 24) + 8LL))(*(_QWORD *)(a1 + 24));
}

```

## disassembly

```asm
0x1800032a0  mov     rcx, [rcx+18h]
0x1800032a4  mov     rax, [rcx]
0x1800032a7  jmp     qword ptr [rax+8]
```
