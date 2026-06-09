# _msize_base

- ea: `0x14001b3d0`
- end: `0x14001b409`
- name: `_msize_base`
- size: `57`
- prototype: `size_t __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140018130`
- `0x14001b410`

## callees

- `0x14000bf5c`
- `0x1400120dc`
- `0x14001b3d0`

## import_xrefs

- `KERNEL32!HeapSize` at `0x14001b402`

## pseudocode

```c
size_t __cdecl msize_base(void *Block)
{
  if ( Block )
    return HeapSize(_acrt_heap, 0, Block);
  *errno() = 22;
  invalid_parameter_noinfo();
  return -1;
}

```

## disassembly

```asm
0x14001b3d0  sub     rsp, 28h
0x14001b3d4  test    rcx, rcx
0x14001b3d7  jnz     short loc_14001B3F2
0x14001b3d9  call    _errno
0x14001b3de  mov     dword ptr [rax], 16h
0x14001b3e4  call    _invalid_parameter_noinfo
0x14001b3e9  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001b3ed  add     rsp, 28h
0x14001b3f1  retn
0x14001b3f2  mov     r8, rcx
0x14001b3f5  xor     edx, edx
0x14001b3f7  mov     rcx, cs:__acrt_heap
0x14001b3fe  add     rsp, 28h
0x14001b402  jmp     cs:__imp_HeapSize
```
