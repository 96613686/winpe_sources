# atexit

- ea: `0x180002cc0`
- end: `0x180002cd7`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800024e0`
- `0x180002500`
- `0x1800068cc`

## callees

- `0x180002c80`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x180002cc0  sub     rsp, 28h
0x180002cc4  call    _onexit
0x180002cc9  neg     rax
0x180002ccc  sbb     eax, eax
0x180002cce  neg     eax
0x180002cd0  dec     eax
0x180002cd2  add     rsp, 28h
0x180002cd6  retn
```
