# avcodec_is_open

- ea: `0x180004140`
- end: `0x18000414a`
- name: `avcodec_is_open`
- size: `10`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180007080`
- `0x1800097f0`
- `0x180009880`

## pseudocode

```c
_BOOL8 __fastcall avcodec_is_open(__int64 a1)
{
  return *(_QWORD *)(a1 + 40) != 0;
}

```

## disassembly

```asm
0x180004140  xor     eax, eax
0x180004142  cmp     [rcx+28h], rax
0x180004146  setnz   al
0x180004149  retn
```
