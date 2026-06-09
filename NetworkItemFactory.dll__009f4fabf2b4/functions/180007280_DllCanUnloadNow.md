# DllCanUnloadNow

- ea: `0x180007280`
- end: `0x18000728c`
- name: `DllCanUnloadNow`
- size: `12`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  return g_cRefThisDll != 0;
}

```

## disassembly

```asm
0x180007280  xor     eax, eax
0x180007282  cmp     cs:?g_cRefThisDll@@3JA, eax; long g_cRefThisDll
0x180007288  setnz   al
0x18000728b  retn
```
