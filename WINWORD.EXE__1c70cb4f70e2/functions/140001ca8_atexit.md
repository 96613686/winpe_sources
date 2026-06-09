# atexit

- ea: `0x140001ca8`
- end: `0x140001cbf`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140001040`
- `0x140001070`
- `0x1400017f0`
- `0x140005714`

## callees

- `0x140001c6c`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x140001ca8  sub     rsp, 28h
0x140001cac  call    _onexit
0x140001cb1  neg     rax
0x140001cb4  sbb     eax, eax
0x140001cb6  neg     eax
0x140001cb8  dec     eax
0x140001cba  add     rsp, 28h
0x140001cbe  retn
```
