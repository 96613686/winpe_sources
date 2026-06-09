# __msize

- ea: `0x413c9a`
- end: `0x413ccd`
- name: `__msize`
- size: `51`
- prototype: `size_t __cdecl(void *Block)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x410456`

## callees

- `0x410369`
- `0x410443`
- `0x413c9a`

## import_xrefs

- `KERNEL32!HeapSize` at `0x413cc5`
- `KERNEL32!HeapSize` at `0x413cc5`

## pseudocode

```c
size_t __cdecl _msize(void *Block)
{
  if ( Block )
    return HeapSize(hHeap, 0, Block);
  *_errno() = 22;
  _invalid_parameter_noinfo();
  return -1;
}

```

## disassembly

```asm
0x413c9a  mov     edi, edi
0x413c9c  push    ebp
0x413c9d  mov     ebp, esp
0x413c9f  cmp     [ebp+lpMem], 0
0x413ca3  jnz     short loc_413CBA
0x413ca5  call    __errno
0x413caa  mov     dword ptr [eax], 16h
0x413cb0  call    __invalid_parameter_noinfo
0x413cb5  or      eax, 0FFFFFFFFh
0x413cb8  pop     ebp
0x413cb9  retn
0x413cba  push    [ebp+lpMem]; lpMem
0x413cbd  push    0; dwFlags
0x413cbf  push    hHeap; hHeap
0x413cc5  call    ds:HeapSize
0x413ccb  pop     ebp
0x413ccc  retn
```
