# AppXDeleteHardlinkSafely(ushort const *)

- ea: `0x180184c80`
- end: `0x180184d8d`
- name: `?AppXDeleteHardlinkSafely@@YAJPEBG@Z`
- size: `269`
- prototype: `__int64 __fastcall(LPCWSTR lpExistingFileName)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x18006d5dc`
- `0x18006deb8`
- `0x1800791dc`
- `0x18008b854`

## callees

- `0x18000669c`
- `0x1800aed10`
- `0x180184c80`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180184d4a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180184d4a`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180184d2e`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180184d65`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180184d2e`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180184d65`
- `KERNEL32!GetVolumePathNameW` at `0x180184cc4`
- `KERNEL32!GetVolumePathNameW` at `0x180184cc4`
- `KERNEL32!GetTempFileNameW` at `0x180184d09`
- `KERNEL32!GetTempFileNameW` at `0x180184d09`
- `SHLWAPI!PathFileExistsW` at `0x180184c9e`
- `SHLWAPI!PathFileExistsW` at `0x180184c9e`

## string_xrefs

- `0x180184ce1`: `onecore\admin\appmodel\common\appxdeletefile.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall AppXDeleteHardlinkSafely(LPCWSTR lpExistingFileName)
{
  const char *v2; // r9
  __int64 v3; // rdx
  WCHAR TempFileName[264]; // [rsp+20h] [rbp-438h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+230h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+458h] [rbp+0h]

  if ( PathFileExistsW(lpExistingFileName) )
  {
    if ( !GetVolumePathNameW(lpExistingFileName, szVolumePathName, 0x104u) )
    {
      v3 = 171;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v3,
               (unsigned int)"onecore\\admin\\appmodel\\common\\appxdeletefile.cpp",
               v2);
    }
    if ( !GetTempFileNameW(szVolumePathName, L"tmp", 0, TempFileName) )
    {
      v3 = 172;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v3,
               (unsigned int)"onecore\\admin\\appmodel\\common\\appxdeletefile.cpp",
               v2);
    }
    if ( !MoveFileExW(lpExistingFileName, TempFileName, 1u) )
    {
      v3 = 175;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v3,
               (unsigned int)"onecore\\admin\\appmodel\\common\\appxdeletefile.cpp",
               v2);
    }
    if ( !DeleteFileW(TempFileName) )
      MoveFileExW(TempFileName, 0, 4u);
  }
  return 0;
}

```

## disassembly

```asm
0x180184c80  push    rbx
0x180184c82  sub     rsp, 450h
0x180184c89  mov     rax, cs:__security_cookie
0x180184c90  xor     rax, rsp
0x180184c93  mov     [rsp+458h+var_18], rax
0x180184c9b  mov     rbx, rcx
0x180184c9e  call    cs:__imp_PathFileExistsW
0x180184ca5  nop     dword ptr [rax+rax+00h]
0x180184caa  cmp     eax, 1
0x180184cad  jnz     loc_180184D71
0x180184cb3  mov     r8d, 104h; cchBufferLength
0x180184cb9  lea     rdx, [rsp+458h+szVolumePathName]; lpszVolumePathName
0x180184cc1  mov     rcx, rbx; lpszFileName
0x180184cc4  call    cs:__imp_GetVolumePathNameW
0x180184ccb  nop     dword ptr [rax+rax+00h]
0x180184cd0  test    eax, eax
0x180184cd2  jnz     short loc_180184CF2
0x180184cd4  mov     edx, 0ABh; void *
0x180184cd9  mov     rcx, [rsp+458h]; this
0x180184ce1  lea     r8, aOnecoreAdminAp_60; "onecore\\admin\\appmodel\\common\\appxd"...
0x180184ce8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180184ced  jmp     loc_180184D73
0x180184cf2  lea     r9, [rsp+458h+TempFileName]; lpTempFileName
0x180184cf7  xor     r8d, r8d; uUnique
0x180184cfa  lea     rdx, PrefixString; "tmp"
0x180184d01  lea     rcx, [rsp+458h+szVolumePathName]; lpPathName
0x180184d09  call    cs:__imp_GetTempFileNameW
0x180184d10  nop     dword ptr [rax+rax+00h]
0x180184d15  test    eax, eax
0x180184d17  jnz     short loc_180184D20
0x180184d19  mov     edx, 0ACh
0x180184d1e  jmp     short loc_180184CD9
0x180184d20  mov     r8d, 1; dwFlags
0x180184d26  lea     rdx, [rsp+458h+TempFileName]; lpNewFileName
0x180184d2b  mov     rcx, rbx; lpExistingFileName
0x180184d2e  call    cs:__imp_MoveFileExW
0x180184d35  nop     dword ptr [rax+rax+00h]
0x180184d3a  test    eax, eax
0x180184d3c  jnz     short loc_180184D45
0x180184d3e  mov     edx, 0AFh
0x180184d43  jmp     short loc_180184CD9
0x180184d45  lea     rcx, [rsp+458h+TempFileName]; lpFileName
0x180184d4a  call    cs:__imp_DeleteFileW
0x180184d51  nop     dword ptr [rax+rax+00h]
0x180184d56  test    eax, eax
0x180184d58  jnz     short loc_180184D71
0x180184d5a  xor     edx, edx; lpNewFileName
0x180184d5c  lea     r8d, [rax+4]; dwFlags
0x180184d60  lea     rcx, [rsp+458h+TempFileName]; lpExistingFileName
0x180184d65  call    cs:__imp_MoveFileExW
0x180184d6c  nop     dword ptr [rax+rax+00h]
0x180184d71  xor     eax, eax
0x180184d73  mov     rcx, [rsp+458h+var_18]
0x180184d7b  xor     rcx, rsp; StackCookie
0x180184d7e  call    __security_check_cookie
0x180184d83  add     rsp, 450h
0x180184d8a  pop     rbx
0x180184d8b  retn
```
