# ___scrt_is_ucrt_dll_in_use

- ea: `0x40c207`
- end: `0x40c213`
- name: `___scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `BOOL()`
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x40ba26`
- `0x40ba91`
- `0x40bbac`

## pseudocode

```c
BOOL __scrt_is_ucrt_dll_in_use()
{
  return dword_4184D4 != 0;
}

```

## disassembly

```asm
0x40c207  xor     eax, eax
0x40c209  cmp     dword_4184D4, eax
0x40c20f  setnz   al
0x40c212  retn
```
