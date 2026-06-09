# __msize

- ea: `0x413c4a`
- end: `0x413c7d`
- name: `__msize`
- size: `51`
- prototype: `size_t __cdecl(void *Block)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x411621`

## callees

- `0x40ec26`
- `0x40ece3`
- `0x413c4a`

## import_xrefs

- `KERNEL32!HeapSize` at `0x413c75`
- `KERNEL32!HeapSize` at `0x413c75`

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
0x413c4a  mov     edi, edi
0x413c4c  push    ebp
0x413c4d  mov     ebp, esp
0x413c4f  cmp     [ebp+lpMem], 0
0x413c53  jnz     short loc_413C6A
0x413c55  call    __errno
0x413c5a  mov     dword ptr [eax], 16h
0x413c60  call    __invalid_parameter_noinfo
0x413c65  or      eax, 0FFFFFFFFh
0x413c68  pop     ebp
0x413c69  retn
0x413c6a  push    [ebp+lpMem]; lpMem
0x413c6d  push    0; dwFlags
0x413c6f  push    hHeap; hHeap
0x413c75  call    ds:HeapSize
0x413c7b  pop     ebp
0x413c7c  retn
```
