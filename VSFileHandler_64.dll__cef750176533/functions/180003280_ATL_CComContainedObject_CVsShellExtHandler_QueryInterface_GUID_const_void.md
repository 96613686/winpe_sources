# ATL::CComContainedObject<CVsShellExtHandler>::QueryInterface(_GUID const &,void * *)

- ea: `0x180003280`
- end: `0x18000328a`
- name: `?QueryInterface@?$CComContainedObject@VCVsShellExtHandler@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `10`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800034c0`
- `0x180003500`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CVsShellExtHandler>::QueryInterface(__int64 a1)
{
  return (***(__int64 (__fastcall ****)(_QWORD))(a1 + 24))(*(_QWORD *)(a1 + 24));
}

```

## disassembly

```asm
0x180003280  mov     rcx, [rcx+18h]
0x180003284  mov     rax, [rcx]
0x180003287  jmp     qword ptr [rax]
```
