# DllCanUnloadNow

- ea: `0x1800027b0`
- end: `0x1800027b3`
- name: `DllCanUnloadNow`
- size: `3`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  return 0;
}

```

## disassembly

```asm
0x1800027b0  xor     eax, eax
0x1800027b2  retn
```
