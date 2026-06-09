# DllCanUnloadNow

- ea: `0x1800226d0`
- end: `0x1800226dc`
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
  return dword_18003538C != 0;
}

```

## disassembly

```asm
0x1800226d0  xor     eax, eax
0x1800226d2  cmp     cs:dword_18003538C, eax
0x1800226d8  setnz   al
0x1800226db  retn
```
