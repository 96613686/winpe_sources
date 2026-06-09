# atexit

- ea: `0x1800021bc`
- end: `0x1800021d3`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180001840`
- `0x180001860`
- `0x180001880`
- `0x180005820`

## callees

- `0x18000217c`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x1800021bc  sub     rsp, 28h
0x1800021c0  call    _onexit
0x1800021c5  neg     rax
0x1800021c8  sbb     eax, eax
0x1800021ca  neg     eax
0x1800021cc  dec     eax
0x1800021ce  add     rsp, 28h
0x1800021d2  retn
```
