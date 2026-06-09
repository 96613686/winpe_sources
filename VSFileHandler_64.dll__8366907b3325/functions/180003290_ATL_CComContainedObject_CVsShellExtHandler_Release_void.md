# ATL::CComContainedObject<CVsShellExtHandler>::Release(void)

- ea: `0x180003290`
- end: `0x18000329b`
- name: `?Release@?$CComContainedObject@VCVsShellExtHandler@@@ATL@@UEAAKXZ`
- size: `11`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003490`
- `0x1800034e0`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CVsShellExtHandler>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 24) + 16LL))(*(_QWORD *)(a1 + 24));
}

```

## disassembly

```asm
0x180003290  mov     rcx, [rcx+18h]
0x180003294  mov     rax, [rcx]
0x180003297  jmp     qword ptr [rax+10h]
```
