# atexit

- ea: `0x180001ff4`
- end: `0x18000200b`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180001790`
- `0x1800017b0`
- `0x1800017d0`
- `0x1800017f0`

## callees

- `0x180001fb4`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x180001ff4  sub     rsp, 28h
0x180001ff8  call    _onexit
0x180001ffd  neg     rax
0x180002000  sbb     eax, eax
0x180002002  neg     eax
0x180002004  dec     eax
0x180002006  add     rsp, 28h
0x18000200a  retn
```
