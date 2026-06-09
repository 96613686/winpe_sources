# ATL::CComObject<CVsShellExtHandler>::AddRef(void)

- ea: `0x180003270`
- end: `0x180003279`
- name: `?AddRef@?$CComObject@VCVsShellExtHandler@@@ATL@@UEAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003480`
- `0x180003520`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CVsShellExtHandler>::AddRef(__int64 a1)
{
  __int64 result; // rax

  result = (unsigned int)(*(_DWORD *)(a1 + 24) + 1);
  *(_DWORD *)(a1 + 24) = result;
  return result;
}

```

## disassembly

```asm
0x180003270  mov     eax, [rcx+18h]
0x180003273  inc     eax
0x180003275  mov     [rcx+18h], eax
0x180003278  retn
```
