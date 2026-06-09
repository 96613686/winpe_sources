# DllCanUnloadNow

- ea: `0x180003350`
- end: `0x18000335c`
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
  return g_cRefModule != 0;
}

```

## disassembly

```asm
0x180003350  xor     eax, eax
0x180003352  cmp     cs:?g_cRefModule@@3JA, eax; long g_cRefModule
0x180003358  setnz   al
0x18000335b  retn
```
