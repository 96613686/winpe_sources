# __std_fs_directory_iterator_open(x,x,x)

- ea: `0x40c71d`
- end: `0x40c77d`
- name: `___std_fs_directory_iterator_open@12`
- size: `96`
- prototype: `int __stdcall(LPCWSTR lpFileName, HANDLE *, LPVOID lpFindFileData)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x408b7c`

## callees

- `0x40c6fd`
- `0x40c71d`

## import_xrefs

- `KERNEL32!GetLastError` at `0x40c746`
- `KERNEL32!GetLastError` at `0x40c76d`
- `KERNEL32!GetLastError` at `0x40c746`
- `KERNEL32!GetLastError` at `0x40c76d`
- `KERNEL32!FindFirstFileExW` at `0x40c739`
- `KERNEL32!FindFirstFileExW` at `0x40c760`
- `KERNEL32!FindFirstFileExW` at `0x40c739`
- `KERNEL32!FindFirstFileExW` at `0x40c760`

## pseudocode

```c
int __stdcall __std_fs_directory_iterator_open(LPCWSTR lpFileName, HANDLE *a2, LPVOID lpFindFileData)
{
  HANDLE FirstFile; // eax
  int result; // eax
  HANDLE v5; // eax

  __std_fs_directory_iterator_close(*a2);
  FirstFile = FindFirstFileExW(lpFileName, FindExInfoBasic, lpFindFileData, FindExSearchNameMatch, 0, 0);
  *a2 = FirstFile;
  if ( FirstFile != (HANDLE)-1 )
    return 0;
  result = GetLastError();
  if ( result == 50 || result == 87 )
  {
    v5 = FindFirstFileExW(lpFileName, FindExInfoStandard, lpFindFileData, FindExSearchNameMatch, 0, 0);
    *a2 = v5;
    if ( v5 == (HANDLE)-1 )
      return GetLastError();
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x40c71d  push    ebp
0x40c71e  mov     ebp, esp
0x40c720  push    esi
0x40c721  mov     esi, [ebp+arg_4]
0x40c724  push    edi
0x40c725  push    dword ptr [esi]; hFindFile
0x40c727  call    ___std_fs_directory_iterator_close@4
0x40c72c  xor     edi, edi
0x40c72e  push    edi; dwAdditionalFlags
0x40c72f  push    edi; lpSearchFilter
0x40c730  push    edi; fSearchOp
0x40c731  push    [ebp+lpFindFileData]; lpFindFileData
0x40c734  push    1; fInfoLevelId
0x40c736  push    [ebp+lpFileName]; lpFileName
0x40c739  call    ds:FindFirstFileExW
0x40c73f  mov     [esi], eax
0x40c741  cmp     eax, 0FFFFFFFFh
0x40c744  jnz     short loc_40C775
0x40c746  call    ds:GetLastError
0x40c74c  cmp     eax, 32h ; '2'
0x40c74f  jz      short loc_40C756
0x40c751  cmp     eax, 57h ; 'W'
0x40c754  jnz     short loc_40C777
0x40c756  push    edi; dwAdditionalFlags
0x40c757  push    edi; lpSearchFilter
0x40c758  push    edi; fSearchOp
0x40c759  push    [ebp+lpFindFileData]; lpFindFileData
0x40c75c  push    edi; fInfoLevelId
0x40c75d  push    [ebp+lpFileName]; lpFileName
0x40c760  call    ds:FindFirstFileExW
0x40c766  mov     [esi], eax
0x40c768  cmp     eax, 0FFFFFFFFh
0x40c76b  jnz     short loc_40C775
0x40c76d  call    ds:GetLastError
0x40c773  jmp     short loc_40C777
0x40c775  xor     eax, eax
0x40c777  pop     edi
0x40c778  pop     esi
0x40c779  pop     ebp
0x40c77a  retn    0Ch
```
