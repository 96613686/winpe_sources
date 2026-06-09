# atexit

- ea: `0x180001b4c`
- end: `0x180001b63`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180001010`
- `0x180001070`
- `0x180001090`
- `0x1800010b0`
- `0x1800010d0`
- `0x180001240`
- `0x180001260`
- `0x180001280`
- `0x1800012a0`

## callees

- `0x180001b0c`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x180001b4c  sub     rsp, 28h
0x180001b50  call    _onexit
0x180001b55  neg     rax
0x180001b58  sbb     eax, eax
0x180001b5a  neg     eax
0x180001b5c  dec     eax
0x180001b5e  add     rsp, 28h
0x180001b62  retn
```
