# atexit

- ea: `0x180001c4c`
- end: `0x180001c63`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180001010`
- `0x1800011d0`
- `0x1800011f0`
- `0x180001210`
- `0x1800012b0`
- `0x1800012f0`
- `0x180001330`
- `0x180001cb0`

## callees

- `0x180001c0c`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x180001c4c  sub     rsp, 28h
0x180001c50  call    _onexit
0x180001c55  neg     rax
0x180001c58  sbb     eax, eax
0x180001c5a  neg     eax
0x180001c5c  dec     eax
0x180001c5e  add     rsp, 28h
0x180001c62  retn
```
