# atexit

- ea: `0x180001fe0`
- end: `0x180001ff7`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x180001040`
- `0x1800010d0`
- `0x180001100`
- `0x180001130`
- `0x180001160`
- `0x180001190`
- `0x1800011b0`
- `0x1800011e0`
- `0x180001210`
- `0x180001270`

## callees

- `0x180001f44`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit_0((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x180001fe0  sub     rsp, 28h
0x180001fe4  call    _onexit_0
0x180001fe9  neg     rax
0x180001fec  sbb     eax, eax
0x180001fee  neg     eax
0x180001ff0  dec     eax
0x180001ff2  add     rsp, 28h
0x180001ff6  retn
```
