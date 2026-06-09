# DllCanUnloadNow

- ea: `0x180002000`
- end: `0x18000200c`
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
  return g_cRef != 0;
}

```

## disassembly

```asm
0x180002000  xor     eax, eax
0x180002002  cmp     cs:?g_cRef@@3KA, eax; ulong g_cRef
0x180002008  setnz   al
0x18000200b  retn
```
