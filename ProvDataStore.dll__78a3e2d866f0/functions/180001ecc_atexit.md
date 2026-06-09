# atexit

- ea: `0x180001ecc`
- end: `0x180001ee3`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180001690`
- `0x1800016b0`
- `0x1800016d0`
- `0x1800016f0`
- `0x180001830`
- `0x180001850`

## callees

- `0x180001e30`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit_0((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x180001ecc  sub     rsp, 28h
0x180001ed0  call    _onexit_0
0x180001ed5  neg     rax
0x180001ed8  sbb     eax, eax
0x180001eda  neg     eax
0x180001edc  dec     eax
0x180001ede  add     rsp, 28h
0x180001ee2  retn
```
