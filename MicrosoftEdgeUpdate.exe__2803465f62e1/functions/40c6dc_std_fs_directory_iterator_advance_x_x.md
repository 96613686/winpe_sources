# __std_fs_directory_iterator_advance(x,x)

- ea: `0x40c6dc`
- end: `0x40c6fd`
- name: `___std_fs_directory_iterator_advance@8`
- size: `33`
- prototype: `DWORD __stdcall(HANDLE hFindFile, LPWIN32_FIND_DATAW lpFindFileData)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x408b7c`
- `0x40949c`

## callees

- `0x40c6dc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x40c6f3`
- `KERNEL32!GetLastError` at `0x40c6f3`
- `KERNEL32!FindNextFileW` at `0x40c6e5`
- `KERNEL32!FindNextFileW` at `0x40c6e5`

## pseudocode

```c
DWORD __stdcall __std_fs_directory_iterator_advance(HANDLE hFindFile, LPWIN32_FIND_DATAW lpFindFileData)
{
  if ( FindNextFileW(hFindFile, lpFindFileData) )
    return 0;
  else
    return GetLastError();
}

```

## disassembly

```asm
0x40c6dc  push    ebp
0x40c6dd  mov     ebp, esp
0x40c6df  push    [ebp+lpFindFileData]; lpFindFileData
0x40c6e2  push    [ebp+hFindFile]; hFindFile
0x40c6e5  call    ds:FindNextFileW
0x40c6eb  test    eax, eax
0x40c6ed  jz      short loc_40C6F3
0x40c6ef  xor     eax, eax
0x40c6f1  jmp     short loc_40C6F9
0x40c6f3  call    ds:GetLastError
0x40c6f9  pop     ebp
0x40c6fa  retn    8
```
