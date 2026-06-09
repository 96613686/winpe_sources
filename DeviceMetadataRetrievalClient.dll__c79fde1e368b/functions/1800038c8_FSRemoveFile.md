# FSRemoveFile

- ea: `0x1800038c8`
- end: `0x1800039c8`
- name: `FSRemoveFile`
- size: `256`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180004b04`
- `0x18000cc50`
- `0x18000d060`

## callees

- `0x1800038c8`
- `0x1800039d0`
- `0x18000eed0`
- `0x180013700`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180003989`
- `KERNEL32!GetProcessHeap` at `0x180003989`
- `KERNEL32!HeapFree` at `0x180003997`
- `KERNEL32!HeapFree` at `0x180003997`
- `KERNEL32!GetFileAttributesW` at `0x1800038ef`
- `KERNEL32!GetFileAttributesW` at `0x1800038ef`
- `KERNEL32!SetFileAttributesW` at `0x18000392d`
- `KERNEL32!SetFileAttributesW` at `0x18000392d`
- `KERNEL32!DeleteFileW` at `0x180003936`
- `KERNEL32!DeleteFileW` at `0x180003936`
- `KERNEL32!GetTempFileNameW` at `0x180003952`
- `KERNEL32!GetTempFileNameW` at `0x180003952`
- `KERNEL32!MoveFileExW` at `0x180003967`
- `KERNEL32!MoveFileExW` at `0x180003981`
- `KERNEL32!MoveFileExW` at `0x180003967`
- `KERNEL32!MoveFileExW` at `0x180003981`

## pseudocode

```c
__int64 __fastcall FSRemoveFile(unsigned __int16 *a1)
{
  DWORD FileAttributesW; // eax
  unsigned __int16 *v3; // rax
  WCHAR *v4; // rdi
  unsigned int v5; // esi
  BOOL v6; // eax
  WCHAR *v7; // rcx
  HANDLE ProcessHeap; // rax
  WCHAR TempFileName[264]; // [rsp+20h] [rbp-228h] BYREF

  FileAttributesW = GetFileAttributesW(a1);
  if ( FileAttributesW == -1 )
    return 0;
  if ( (FileAttributesW & 0x10) != 0 )
    return 0;
  v3 = MemMallocAndCopy(a1);
  v4 = v3;
  if ( !v3 )
    return 0;
  v5 = 1;
  FSSplitFileName(v3);
  SetFileAttributesW(a1, 0x80u);
  if ( !DeleteFileW(a1) )
  {
    if ( !GetTempFileNameW(v4, L"DEL", 0, TempFileName)
      || (v6 = MoveFileExW(a1, TempFileName, 1u), v7 = TempFileName, !v6) )
    {
      v7 = a1;
    }
    MoveFileExW(v7, 0, 4u);
    v5 = 0;
  }
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, v4);
  return v5;
}

```

## disassembly

```asm
0x1800038c8  mov     [rsp+arg_8], rbx
0x1800038cd  mov     [rsp+arg_10], rsi
0x1800038d2  push    rdi
0x1800038d3  sub     rsp, 240h
0x1800038da  mov     rax, cs:__security_cookie
0x1800038e1  xor     rax, rsp
0x1800038e4  mov     [rsp+248h+var_18], rax
0x1800038ec  mov     rbx, rcx
0x1800038ef  call    cs:__imp_GetFileAttributesW
0x1800038f5  cmp     eax, 0FFFFFFFFh
0x1800038f8  jz      loc_1800039A1
0x1800038fe  test    al, 10h
0x180003900  jnz     loc_1800039A1
0x180003906  mov     rcx, rbx; unsigned __int16 *
0x180003909  call    ?MemMallocAndCopy@@YAPEAGPEBG@Z; MemMallocAndCopy(ushort const *)
0x18000390e  mov     rdi, rax
0x180003911  test    rax, rax
0x180003914  jz      loc_1800039A1
0x18000391a  mov     rcx, rax
0x18000391d  mov     esi, 1
0x180003922  call    FSSplitFileName
0x180003927  lea     edx, [rsi+7Fh]; dwFileAttributes
0x18000392a  mov     rcx, rbx; lpFileName
0x18000392d  call    cs:__imp_SetFileAttributesW
0x180003933  mov     rcx, rbx; lpFileName
0x180003936  call    cs:__imp_DeleteFileW
0x18000393c  test    eax, eax
0x18000393e  jnz     short loc_180003989
0x180003940  lea     r9, [rsp+248h+TempFileName]; lpTempFileName
0x180003945  xor     r8d, r8d; uUnique
0x180003948  lea     rdx, PrefixString; "DEL"
0x18000394f  mov     rcx, rdi; lpPathName
0x180003952  call    cs:__imp_GetTempFileNameW
0x180003958  test    eax, eax
0x18000395a  jz      short loc_180003976
0x18000395c  mov     r8d, esi; dwFlags
0x18000395f  lea     rdx, [rsp+248h+TempFileName]; lpNewFileName
0x180003964  mov     rcx, rbx; lpExistingFileName
0x180003967  call    cs:__imp_MoveFileExW
0x18000396d  lea     rcx, [rsp+248h+TempFileName]
0x180003972  test    eax, eax
0x180003974  jnz     short loc_180003979
0x180003976  mov     rcx, rbx; lpExistingFileName
0x180003979  mov     r8d, 4; dwFlags
0x18000397f  xor     edx, edx; lpNewFileName
0x180003981  call    cs:__imp_MoveFileExW
0x180003987  xor     esi, esi
0x180003989  call    cs:__imp_GetProcessHeap
0x18000398f  mov     r8, rdi; lpMem
0x180003992  xor     edx, edx; dwFlags
0x180003994  mov     rcx, rax; hHeap
0x180003997  call    cs:__imp_HeapFree
0x18000399d  mov     eax, esi
0x18000399f  jmp     short loc_1800039A3
0x1800039a1  xor     eax, eax
0x1800039a3  mov     rcx, [rsp+248h+var_18]
0x1800039ab  xor     rcx, rsp; StackCookie
0x1800039ae  call    __security_check_cookie
0x1800039b3  lea     r11, [rsp+248h+var_8]
0x1800039bb  mov     rbx, [r11+18h]
0x1800039bf  mov     rsi, [r11+20h]
0x1800039c3  mov     rsp, r11
0x1800039c6  pop     rdi
0x1800039c7  retn
```
