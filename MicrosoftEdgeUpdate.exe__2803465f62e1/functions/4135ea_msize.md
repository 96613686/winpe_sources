# __msize

- ea: `0x4135ea`
- end: `0x41361d`
- name: `__msize`
- size: `51`
- prototype: `size_t __cdecl(void *Block)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x411fa6`

## callees

- `0x40de54`
- `0x40ffa9`
- `0x4135ea`

## import_xrefs

- `KERNEL32!HeapSize` at `0x413615`
- `KERNEL32!HeapSize` at `0x413615`

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
0x4135ea  mov     edi, edi
0x4135ec  push    ebp
0x4135ed  mov     ebp, esp
0x4135ef  cmp     [ebp+lpMem], 0
0x4135f3  jnz     short loc_41360A
0x4135f5  call    __errno
0x4135fa  mov     dword ptr [eax], 16h
0x413600  call    __invalid_parameter_noinfo
0x413605  or      eax, 0FFFFFFFFh
0x413608  pop     ebp
0x413609  retn
0x41360a  push    [ebp+lpMem]; lpMem
0x41360d  push    0; dwFlags
0x41360f  push    hHeap; hHeap
0x413615  call    ds:HeapSize
0x41361b  pop     ebp
0x41361c  retn
```
