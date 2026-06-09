# atexit

- ea: `0x180165ef4`
- end: `0x180165f0b`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x1800017b0`
- `0x1800017d0`
- `0x180001830`
- `0x1800018c0`
- `0x180001b30`
- `0x180001c10`
- `0x180001cf0`
- `0x180001e60`
- `0x1800020d0`
- `0x1800021b0`
- `0x180002250`
- `0x180002360`
- `0x1800025d0`
- `0x1800026b0`
- `0x180002770`
- `0x180086660`

## callees

- `0x180165eb4`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (sub_180165EB4((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x180165ef4  sub     rsp, 28h
0x180165ef8  call    sub_180165EB4
0x180165efd  neg     rax
0x180165f00  sbb     eax, eax
0x180165f02  neg     eax
0x180165f04  dec     eax
0x180165f06  add     rsp, 28h
0x180165f0a  retn
```
