# DllCanUnloadNow

- ea: `0x180005ea0`
- end: `0x180005eac`
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
0x180005ea0  xor     eax, eax
0x180005ea2  cmp     cs:?g_cRefThisDll@@3JA, eax; long g_cRefThisDll
0x180005ea8  setnz   al
0x180005eab  retn
```
