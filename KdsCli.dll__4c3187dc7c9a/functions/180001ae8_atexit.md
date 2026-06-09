# atexit

- ea: `0x180001ae8`
- end: `0x180001aff`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180001010`
- `0x180001030`
- `0x180001200`
- `0x180001220`

## callees

- `0x180001aa8`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x180001ae8  sub     rsp, 28h
0x180001aec  call    _onexit
0x180001af1  neg     rax
0x180001af4  sbb     eax, eax
0x180001af6  neg     eax
0x180001af8  dec     eax
0x180001afa  add     rsp, 28h
0x180001afe  retn
```
