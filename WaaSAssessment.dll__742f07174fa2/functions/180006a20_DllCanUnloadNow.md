# DllCanUnloadNow

- ea: `0x180006a20`
- end: `0x180006a2c`
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
  return dword_180027CEC != 0;
}

```

## disassembly

```asm
0x180006a20  xor     eax, eax
0x180006a22  cmp     cs:dword_180027CEC, eax
0x180006a28  setnz   al
0x180006a2b  retn
```
