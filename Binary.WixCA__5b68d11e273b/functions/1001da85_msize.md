# __msize

- ea: `0x1001da85`
- end: `0x1001dab8`
- name: `__msize`
- size: `51`
- prototype: `size_t __cdecl(void *Block)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1001a0ba`

## callees

- `0x10015cbc`
- `0x10015d79`
- `0x1001da85`

## import_xrefs

- `KERNEL32!HeapSize` at `0x1001dab0`
- `KERNEL32!HeapSize` at `0x1001dab0`

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
0x1001da85  mov     edi, edi
0x1001da87  push    ebp
0x1001da88  mov     ebp, esp
0x1001da8a  cmp     [ebp+lpMem], 0
0x1001da8e  jnz     short loc_1001DAA5
0x1001da90  call    __errno
0x1001da95  mov     dword ptr [eax], 16h
0x1001da9b  call    __invalid_parameter_noinfo
0x1001daa0  or      eax, 0FFFFFFFFh
0x1001daa3  pop     ebp
0x1001daa4  retn
0x1001daa5  push    [ebp+lpMem]; lpMem
0x1001daa8  push    0; dwFlags
0x1001daaa  push    hHeap; hHeap
0x1001dab0  call    ds:HeapSize
0x1001dab6  pop     ebp
0x1001dab7  retn
```
