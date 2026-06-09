# atexit

- ea: `0x180001ccc`
- end: `0x180001ce3`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180001300`
- `0x180001350`
- `0x180001390`
- `0x1800013c0`

## callees

- `0x180001c8c`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x180001ccc  sub     rsp, 28h
0x180001cd0  call    _onexit
0x180001cd5  neg     rax
0x180001cd8  sbb     eax, eax
0x180001cda  neg     eax
0x180001cdc  dec     eax
0x180001cde  add     rsp, 28h
0x180001ce2  retn
```
