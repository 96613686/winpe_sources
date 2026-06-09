# atexit

- ea: `0x140001cc4`
- end: `0x140001cdb`
- name: `atexit`
- size: `23`
- prototype: `int __cdecl(void (__cdecl *)())`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x140001010`
- `0x140001030`
- `0x140001050`
- `0x140001070`
- `0x1400011d0`
- `0x1400011f0`
- `0x1400013f0`
- `0x140001410`
- `0x140001430`
- `0x140001470`
- `0x1400014b0`

## callees

- `0x140001c28`

## pseudocode

```c
int __cdecl atexit(void (__cdecl *a1)())
{
  return (onexit_0((_onexit_t)a1) != 0) - 1;
}

```

## disassembly

```asm
0x140001cc4  sub     rsp, 28h
0x140001cc8  call    _onexit_0
0x140001ccd  neg     rax
0x140001cd0  sbb     eax, eax
0x140001cd2  neg     eax
0x140001cd4  dec     eax
0x140001cd6  add     rsp, 28h
0x140001cda  retn
```
