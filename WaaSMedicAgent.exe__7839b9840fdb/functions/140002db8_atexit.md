# atexit

- ea: `0x140002db8`
- end: `0x140002dcf`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `18`
- callee_count: `1`
- tags: ``

## callers

- `0x1400020e0`
- `0x140002120`
- `0x140002160`
- `0x140002290`
- `0x1400022b0`
- `0x1400022d0`
- `0x140002310`
- `0x140002350`
- `0x140002390`
- `0x1400023d0`
- `0x140002410`
- `0x140002450`
- `0x140002490`
- `0x140002600`
- `0x140002780`
- `0x1400037e0`
- `0x14000885c`
- `0x14000ceb0`

## callees

- `0x140002d78`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x140002db8  sub     rsp, 28h
0x140002dbc  call    _onexit
0x140002dc1  neg     rax
0x140002dc4  sbb     eax, eax
0x140002dc6  neg     eax
0x140002dc8  dec     eax
0x140002dca  add     rsp, 28h
0x140002dce  retn
```
