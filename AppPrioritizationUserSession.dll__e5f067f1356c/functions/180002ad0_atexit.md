# atexit

- ea: `0x180002ad0`
- end: `0x180002ae7`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180001920`
- `0x180001a60`
- `0x180001a80`
- `0x180001aa0`
- `0x180001ad0`
- `0x180001af0`

## callees

- `0x180002a90`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x180002ad0  sub     rsp, 28h
0x180002ad4  call    _onexit
0x180002ad9  neg     rax
0x180002adc  sbb     eax, eax
0x180002ade  neg     eax
0x180002ae0  dec     eax
0x180002ae2  add     rsp, 28h
0x180002ae6  retn
```
