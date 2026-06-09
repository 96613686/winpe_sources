# DllCanUnloadNow

- ea: `0x180003fb0`
- end: `0x180003fbc`
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
  return g_cLocks != 0;
}

```

## disassembly

```asm
0x180003fb0  xor     eax, eax
0x180003fb2  cmp     cs:?g_cLocks@@3KA, eax; ulong g_cLocks
0x180003fb8  setnz   al
0x180003fbb  retn
```
