# atexit

- ea: `0x180001ac8`
- end: `0x180001adf`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180001010`
- `0x1800010b0`
- `0x1800010f0`
- `0x180001130`

## callees

- `0x180001a2c`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit_0((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x180001ac8  sub     rsp, 28h
0x180001acc  call    _onexit_0
0x180001ad1  neg     rax
0x180001ad4  sbb     eax, eax
0x180001ad6  neg     eax
0x180001ad8  dec     eax
0x180001ada  add     rsp, 28h
0x180001ade  retn
```
