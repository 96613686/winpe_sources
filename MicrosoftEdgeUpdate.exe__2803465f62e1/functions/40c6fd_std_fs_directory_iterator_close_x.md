# __std_fs_directory_iterator_close(x)

- ea: `0x40c6fd`
- end: `0x40c71c`
- name: `___std_fs_directory_iterator_close@4`
- size: `31`
- prototype: `void __stdcall(HANDLE hFindFile)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x40a274`
- `0x40abb0`
- `0x40c71d`

## callees

- `0x40c6fd`
- `0x40f45f`

## import_xrefs

- `KERNEL32!FindClose` at `0x40c709`
- `KERNEL32!FindClose` at `0x40c709`

## pseudocode

```c
void __stdcall __std_fs_directory_iterator_close(HANDLE hFindFile)
{
  if ( hFindFile != (HANDLE)-1 && !FindClose(hFindFile) )
    terminate();
}

```

## disassembly

```asm
0x40c6fd  push    ebp
0x40c6fe  mov     ebp, esp
0x40c700  cmp     [ebp+hFindFile], 0FFFFFFFFh
0x40c704  jz      short loc_40C713
0x40c706  push    [ebp+hFindFile]; hFindFile
0x40c709  call    ds:FindClose
0x40c70f  test    eax, eax
0x40c711  jz      short loc_40C717
0x40c713  pop     ebp
0x40c714  retn    4
0x40c717  call    _terminate
```
