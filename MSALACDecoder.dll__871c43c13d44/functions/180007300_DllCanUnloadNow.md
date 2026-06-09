# DllCanUnloadNow

- ea: `0x180007300`
- end: `0x18000730c`
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
  return dword_18000F33C != 0;
}

```

## disassembly

```asm
0x180007300  xor     eax, eax
0x180007302  cmp     cs:dword_18000F33C, eax
0x180007308  setnz   al
0x18000730b  retn
```
