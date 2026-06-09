# DllCanUnloadNow

- ea: `0x1800070f0`
- end: `0x1800070fc`
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
  return dword_1800128AC != 0;
}

```

## disassembly

```asm
0x1800070f0  xor     eax, eax
0x1800070f2  cmp     cs:dword_1800128AC, eax
0x1800070f8  setnz   al
0x1800070fb  retn
```
