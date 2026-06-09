# DllCanUnloadNow

- ea: `0x180002ee0`
- end: `0x180002eef`
- name: `DllCanUnloadNow`
- size: `15`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  return g_dwObjectCount != 0;
}

```

## disassembly

```asm
0x180002ee0  xor     eax, eax
0x180002ee2  cmp     cs:?g_dwObjectCount@@3JA, eax; long g_dwObjectCount
0x180002ee8  lea     ecx, [rax+1]
0x180002eeb  cmovnz  eax, ecx
0x180002eee  retn
```
