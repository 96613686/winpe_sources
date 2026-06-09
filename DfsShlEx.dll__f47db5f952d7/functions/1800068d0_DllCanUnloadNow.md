# DllCanUnloadNow

- ea: `0x1800068d0`
- end: `0x1800068dc`
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
  return dword_1800139CC != 0;
}

```

## disassembly

```asm
0x1800068d0  xor     eax, eax
0x1800068d2  cmp     cs:dword_1800139CC, eax
0x1800068d8  setnz   al
0x1800068db  retn
```
