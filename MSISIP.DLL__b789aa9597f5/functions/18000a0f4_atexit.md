# atexit

- ea: `0x18000a0f4`
- end: `0x18000a10b`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180001170`
- `0x1800068a0`
- `0x180007300`

## callees

- `0x18000a058`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit_0((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x18000a0f4  sub     rsp, 28h
0x18000a0f8  call    _onexit_0
0x18000a0fd  neg     rax
0x18000a100  sbb     eax, eax
0x18000a102  neg     eax
0x18000a104  dec     eax
0x18000a106  add     rsp, 28h
0x18000a10a  retn
```
