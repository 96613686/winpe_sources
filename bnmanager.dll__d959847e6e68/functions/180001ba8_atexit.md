# atexit

- ea: `0x180001ba8`
- end: `0x180001bbf`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180001010`
- `0x1800011d0`
- `0x1800011f0`
- `0x180001210`

## callees

- `0x180001b68`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x180001ba8  sub     rsp, 28h
0x180001bac  call    _onexit
0x180001bb1  neg     rax
0x180001bb4  sbb     eax, eax
0x180001bb6  neg     eax
0x180001bb8  dec     eax
0x180001bba  add     rsp, 28h
0x180001bbe  retn
```
