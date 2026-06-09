# atexit

- ea: `0x180001cc4`
- end: `0x180001cdb`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x1800011e0`
- `0x180001200`
- `0x180001220`
- `0x180001240`
- `0x180001260`
- `0x180001460`
- `0x180001480`
- `0x1800014a0`

## callees

- `0x180001c28`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit_0((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x180001cc4  sub     rsp, 28h
0x180001cc8  call    _onexit_0
0x180001ccd  neg     rax
0x180001cd0  sbb     eax, eax
0x180001cd2  neg     eax
0x180001cd4  dec     eax
0x180001cd6  add     rsp, 28h
0x180001cda  retn
```
