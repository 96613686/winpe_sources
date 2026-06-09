# atexit

- ea: `0x18000e5f4`
- end: `0x18000e60b`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180001980`
- `0x1800019e0`
- `0x180001a20`
- `0x180001a40`
- `0x180001a60`
- `0x180001a80`
- `0x180001aa0`
- `0x180008200`
- `0x180008790`

## callees

- `0x18000e558`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit_0((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x18000e5f4  sub     rsp, 28h
0x18000e5f8  call    _onexit_0
0x18000e5fd  neg     rax
0x18000e600  sbb     eax, eax
0x18000e602  neg     eax
0x18000e604  dec     eax
0x18000e606  add     rsp, 28h
0x18000e60a  retn
```
