# ATL::CComAggObject<CVsShellExtHandler>::AddRef(void)

- ea: `0x180003370`
- end: `0x180003379`
- name: `?AddRef@?$CComAggObject@VCVsShellExtHandler@@@ATL@@UEAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CVsShellExtHandler>::AddRef(__int64 a1)
{
  __int64 result; // rax

  result = (unsigned int)(*(_DWORD *)(a1 + 8) + 1);
  *(_DWORD *)(a1 + 8) = result;
  return result;
}

```

## disassembly

```asm
0x180003370  mov     eax, [rcx+8]
0x180003373  inc     eax
0x180003375  mov     [rcx+8], eax
0x180003378  retn
```
