# atexit

- ea: `0x140001af4`
- end: `0x140001b0b`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140001310`
- `0x140001330`
- `0x140001350`
- `0x140001480`
- `0x1400014a0`

## callees

- `0x140001a58`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit_0((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x140001af4  sub     rsp, 28h
0x140001af8  call    _onexit_0
0x140001afd  neg     rax
0x140001b00  sbb     eax, eax
0x140001b02  neg     eax
0x140001b04  dec     eax
0x140001b06  add     rsp, 28h
0x140001b0a  retn
```
