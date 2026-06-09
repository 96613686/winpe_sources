# atexit

- ea: `0x18000ef20`
- end: `0x18000ef37`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180001160`
- `0x180001180`
- `0x1800011a0`
- `0x180001280`
- `0x1800012a0`
- `0x1800012c0`
- `0x18000e5e0`
- `0x18000f690`
- `0x1800170a0`

## callees

- `0x18000eee0`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x18000ef20  sub     rsp, 28h
0x18000ef24  call    _onexit
0x18000ef29  neg     rax
0x18000ef2c  sbb     eax, eax
0x18000ef2e  neg     eax
0x18000ef30  dec     eax
0x18000ef32  add     rsp, 28h
0x18000ef36  retn
```
