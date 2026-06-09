# atexit

- ea: `0x180001dc4`
- end: `0x180001ddb`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180001300`
- `0x180001320`
- `0x180001340`
- `0x180001440`
- `0x180001460`
- `0x180001480`
- `0x1800014e0`

## callees

- `0x180001d28`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit_0((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x180001dc4  sub     rsp, 28h
0x180001dc8  call    _onexit_0
0x180001dcd  neg     rax
0x180001dd0  sbb     eax, eax
0x180001dd2  neg     eax
0x180001dd4  dec     eax
0x180001dd6  add     rsp, 28h
0x180001dda  retn
```
