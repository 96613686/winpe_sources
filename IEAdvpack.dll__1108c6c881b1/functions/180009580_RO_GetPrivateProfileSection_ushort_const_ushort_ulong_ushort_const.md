# RO_GetPrivateProfileSection(ushort const *,ushort *,ulong,ushort const *)

- ea: `0x180009580`
- end: `0x1800096e9`
- name: `?RO_GetPrivateProfileSection@@YAKPEBGPEAGK0@Z`
- size: `361`
- prototype: `__int64 __fastcall(LPCWSTR lpAppName, LPWSTR lpReturnedString, DWORD nSize, LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180006e54`
- `0x1800071c0`

## callees

- `0x180008524`
- `0x180009580`
- `0x18001b980`

## import_xrefs

- `KERNEL32!GetTempPath2W` at `0x1800095ed`
- `KERNEL32!GetTempPath2W` at `0x1800095ed`
- `KERNEL32!GetWindowsDirectoryW` at `0x180009619`
- `KERNEL32!GetWindowsDirectoryW` at `0x180009619`
- `KERNEL32!GetTempFileNameW` at `0x180009636`
- `KERNEL32!GetTempFileNameW` at `0x180009636`
- `KERNEL32!DeleteFileW` at `0x180009655`
- `KERNEL32!DeleteFileW` at `0x180009697`
- `KERNEL32!DeleteFileW` at `0x180009655`
- `KERNEL32!DeleteFileW` at `0x180009697`
- `KERNEL32!GetFileAttributesW` at `0x1800095af`
- `KERNEL32!GetFileAttributesW` at `0x1800095af`
- `KERNEL32!SetFileAttributesW` at `0x1800095d2`
- `KERNEL32!SetFileAttributesW` at `0x18000964a`
- `KERNEL32!SetFileAttributesW` at `0x180009676`
- `KERNEL32!SetFileAttributesW` at `0x1800096c3`
- `KERNEL32!SetFileAttributesW` at `0x1800095d2`
- `KERNEL32!SetFileAttributesW` at `0x18000964a`
- `KERNEL32!SetFileAttributesW` at `0x180009676`
- `KERNEL32!SetFileAttributesW` at `0x1800096c3`
- `KERNEL32!CopyFileW` at `0x180009666`
- `KERNEL32!CopyFileW` at `0x180009666`
- `KERNEL32!GetPrivateProfileSectionW` at `0x18000968a`
- `KERNEL32!GetPrivateProfileSectionW` at `0x1800096ab`
- `KERNEL32!GetPrivateProfileSectionW` at `0x18000968a`
- `KERNEL32!GetPrivateProfileSectionW` at `0x1800096ab`

## pseudocode

```c
__int64 __fastcall RO_GetPrivateProfileSection(
        LPCWSTR lpAppName,
        LPWSTR lpReturnedString,
        DWORD nSize,
        LPCWSTR lpFileName)
{
  DWORD FileAttributesW; // edi
  DWORD PrivateProfileSectionW; // ebx
  WCHAR TempFileName[264]; // [rsp+20h] [rbp-458h] BYREF
  WCHAR Buffer[264]; // [rsp+230h] [rbp-248h] BYREF

  FileAttributesW = GetFileAttributesW(lpFileName);
  if ( FileAttributesW != -1
    && (FileAttributesW & 1) != 0
    && !SetFileAttributesW(lpFileName, 0x80u)
    && (unsigned int)GetTempPath2W(260, Buffer) )
  {
    if ( !(unsigned int)IsGoodDir(Buffer) )
      GetWindowsDirectoryW(Buffer, 0x104u);
    if ( GetTempFileNameW(Buffer, L"INF", 0, TempFileName) )
    {
      SetFileAttributesW(TempFileName, 0x80u);
      DeleteFileW(TempFileName);
      CopyFileW(lpFileName, TempFileName, 0);
      SetFileAttributesW(TempFileName, 0x80u);
      PrivateProfileSectionW = GetPrivateProfileSectionW(lpAppName, lpReturnedString, nSize, TempFileName);
      DeleteFileW(TempFileName);
LABEL_11:
      SetFileAttributesW(lpFileName, FileAttributesW);
      return PrivateProfileSectionW;
    }
  }
  PrivateProfileSectionW = GetPrivateProfileSectionW(lpAppName, lpReturnedString, nSize, lpFileName);
  if ( FileAttributesW != -1 && (FileAttributesW & 1) != 0 )
    goto LABEL_11;
  return PrivateProfileSectionW;
}

```

## disassembly

```asm
0x180009580  push    rbx
0x180009582  push    rbp
0x180009583  push    rsi
0x180009584  push    rdi
0x180009585  push    r14
0x180009587  sub     rsp, 450h
0x18000958e  mov     rax, cs:__security_cookie
0x180009595  xor     rax, rsp
0x180009598  mov     [rsp+478h+var_38], rax
0x1800095a0  mov     rbx, rcx
0x1800095a3  mov     rsi, r9
0x1800095a6  mov     rcx, r9; lpFileName
0x1800095a9  mov     r14d, r8d
0x1800095ac  mov     rbp, rdx
0x1800095af  call    cs:__imp_GetFileAttributesW
0x1800095b5  mov     edi, eax
0x1800095b7  cmp     eax, 0FFFFFFFFh
0x1800095ba  jz      loc_18000969F
0x1800095c0  test    dil, 1
0x1800095c4  jz      loc_18000969F
0x1800095ca  mov     edx, 80h; dwFileAttributes
0x1800095cf  mov     rcx, rsi; lpFileName
0x1800095d2  call    cs:__imp_SetFileAttributesW
0x1800095d8  test    eax, eax
0x1800095da  jnz     loc_18000969F
0x1800095e0  lea     rdx, [rsp+478h+Buffer]
0x1800095e8  mov     ecx, 104h
0x1800095ed  call    cs:__imp_GetTempPath2W
0x1800095f3  test    eax, eax
0x1800095f5  jz      loc_18000969F
0x1800095fb  lea     rcx, [rsp+478h+Buffer]; unsigned __int16 *
0x180009603  call    ?IsGoodDir@@YAHPEBG@Z; IsGoodDir(ushort const *)
0x180009608  test    eax, eax
0x18000960a  jnz     short loc_18000961F
0x18000960c  mov     edx, 104h; uSize
0x180009611  lea     rcx, [rsp+478h+Buffer]; lpBuffer
0x180009619  call    cs:__imp_GetWindowsDirectoryW
0x18000961f  lea     r9, [rsp+478h+TempFileName]; lpTempFileName
0x180009624  xor     r8d, r8d; uUnique
0x180009627  lea     rdx, aInf; "INF"
0x18000962e  lea     rcx, [rsp+478h+Buffer]; lpPathName
0x180009636  call    cs:__imp_GetTempFileNameW
0x18000963c  test    eax, eax
0x18000963e  jz      short loc_18000969F
0x180009640  mov     edx, 80h; dwFileAttributes
0x180009645  lea     rcx, [rsp+478h+TempFileName]; lpFileName
0x18000964a  call    cs:__imp_SetFileAttributesW
0x180009650  lea     rcx, [rsp+478h+TempFileName]; lpFileName
0x180009655  call    cs:__imp_DeleteFileW
0x18000965b  xor     r8d, r8d; bFailIfExists
0x18000965e  lea     rdx, [rsp+478h+TempFileName]; lpNewFileName
0x180009663  mov     rcx, rsi; lpExistingFileName
0x180009666  call    cs:__imp_CopyFileW
0x18000966c  mov     edx, 80h; dwFileAttributes
0x180009671  lea     rcx, [rsp+478h+TempFileName]; lpFileName
0x180009676  call    cs:__imp_SetFileAttributesW
0x18000967c  lea     r9, [rsp+478h+TempFileName]; lpFileName
0x180009681  mov     r8d, r14d; nSize
0x180009684  mov     rdx, rbp; lpReturnedString
0x180009687  mov     rcx, rbx; lpAppName
0x18000968a  call    cs:__imp_GetPrivateProfileSectionW
0x180009690  lea     rcx, [rsp+478h+TempFileName]; lpFileName
0x180009695  mov     ebx, eax
0x180009697  call    cs:__imp_DeleteFileW
0x18000969d  jmp     short loc_1800096BE
0x18000969f  mov     r9, rsi; lpFileName
0x1800096a2  mov     r8d, r14d; nSize
0x1800096a5  mov     rdx, rbp; lpReturnedString
0x1800096a8  mov     rcx, rbx; lpAppName
0x1800096ab  call    cs:__imp_GetPrivateProfileSectionW
0x1800096b1  mov     ebx, eax
0x1800096b3  cmp     edi, 0FFFFFFFFh
0x1800096b6  jz      short loc_1800096C9
0x1800096b8  test    dil, 1
0x1800096bc  jz      short loc_1800096C9
0x1800096be  mov     edx, edi; dwFileAttributes
0x1800096c0  mov     rcx, rsi; lpFileName
0x1800096c3  call    cs:__imp_SetFileAttributesW
0x1800096c9  mov     eax, ebx
0x1800096cb  mov     rcx, [rsp+478h+var_38]
0x1800096d3  xor     rcx, rsp; StackCookie
0x1800096d6  call    __security_check_cookie
0x1800096db  add     rsp, 450h
0x1800096e2  pop     r14
0x1800096e4  pop     rdi
0x1800096e5  pop     rsi
0x1800096e6  pop     rbp
0x1800096e7  pop     rbx
0x1800096e8  retn
```
