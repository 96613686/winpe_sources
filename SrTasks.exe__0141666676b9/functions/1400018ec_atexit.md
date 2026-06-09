# atexit

- ea: `0x1400018ec`
- end: `0x140001903`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140001010`
- `0x1400011a0`
- `0x1400011c0`

## callees

- `0x140001850`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit_0((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x1400018ec  sub     rsp, 28h
0x1400018f0  call    _onexit_0
0x1400018f5  neg     rax
0x1400018f8  sbb     eax, eax
0x1400018fa  neg     eax
0x1400018fc  dec     eax
0x1400018fe  add     rsp, 28h
0x140001902  retn
```
