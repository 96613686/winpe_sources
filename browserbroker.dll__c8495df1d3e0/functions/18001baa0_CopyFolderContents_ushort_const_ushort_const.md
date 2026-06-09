# CopyFolderContents(ushort const *,ushort const *)

- ea: `0x18001baa0`
- end: `0x18001bc4c`
- name: `?CopyFolderContents@@YAJPEBG0@Z`
- size: `428`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180007c50`
- `0x18001baa0`

## callees

- `0x180002ce0`
- `0x1800037ac`
- `0x18001b7f8`
- `0x18001baa0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bae3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bc0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bae3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bc0f`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001bb4f`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001bb4f`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001bc07`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001bc07`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001bad9`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001bad9`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001bbf6`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001bbf6`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18001bb39`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18001bb80`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18001bbad`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18001bb39`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18001bb80`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18001bbad`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CopyFolderContents(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  signed int v4; // ebx
  signed int v5; // eax
  __int64 FirstFileW; // rdi
  signed int LastError; // eax
  _WIN32_FIND_DATAW FindFileData; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR pszPathIn[264]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR pszPathOut[264]; // [rsp+480h] [rbp+380h] BYREF
  WCHAR PathName[264]; // [rsp+690h] [rbp+590h] BYREF

  v4 = 0;
  if ( CreateDirectoryW(a2, 0)
    || (v5 = GetLastError(), v5 == 183)
    || (v5 > 0 ? (v4 = (unsigned __int16)v5 | 0x80070000) : (v4 = v5), v4 >= 0) )
  {
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    FirstFileW = -1;
    if ( PathCchCombine(pszPathOut, 0x104u, a1, L"*") >= 0 )
      FirstFileW = (__int64)FindFirstFileW(pszPathOut, &FindFileData);
    if ( FirstFileW != -1 )
    {
      while ( 1 )
      {
        if ( FindFileData.cFileName[0] != 46
          && PathCchCombine(pszPathIn, 0x104u, a1, FindFileData.cFileName) >= 0
          && (FindFileData.dwFileAttributes & 0x400) == 0 )
        {
          if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
          {
            if ( PathCchCombine(PathName, 0x104u, a2, FindFileData.cFileName) >= 0 && FindFileData.cFileName[0] != 46 )
            {
              v4 = CopyFolderContents(pszPathIn, PathName);
              if ( v4 < 0 )
              {
LABEL_20:
                FindClose((HANDLE)FirstFileW);
                return (unsigned int)v4;
              }
            }
          }
          else
          {
            CopyAsTwoFiles(pszPathIn, a2, FindFileData.cFileName);
          }
        }
        if ( !FindNextFileW((HANDLE)FirstFileW, &FindFileData) )
          goto LABEL_20;
      }
    }
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001baa0  mov     [rsp-8+arg_10], rbx
0x18001baa5  push    rbp
0x18001baa6  push    rsi
0x18001baa7  push    rdi
0x18001baa8  push    r12
0x18001baaa  push    r14
0x18001baac  lea     rbp, [rsp-7B0h]
0x18001bab4  sub     rsp, 8B0h
0x18001babb  mov     rax, cs:__security_cookie
0x18001bac2  xor     rax, rsp
0x18001bac5  mov     [rbp+7D0h+var_30], rax
0x18001bacc  mov     rsi, rdx
0x18001bacf  mov     r14, rcx
0x18001bad2  mov     rcx, rsi; lpPathName
0x18001bad5  xor     edx, edx; lpSecurityAttributes
0x18001bad7  xor     ebx, ebx
0x18001bad9  call    cs:__imp_CreateDirectoryW
0x18001badf  test    eax, eax
0x18001bae1  jnz     short loc_18001BB09
0x18001bae3  call    cs:__imp_GetLastError
0x18001bae9  cmp     eax, 0B7h
0x18001baee  jz      short loc_18001BB09
0x18001baf0  test    eax, eax
0x18001baf2  jg      short loc_18001BAF8
0x18001baf4  mov     ebx, eax
0x18001baf6  jmp     short loc_18001BB01
0x18001baf8  movzx   ebx, ax
0x18001bafb  or      ebx, 80070000h
0x18001bb01  test    ebx, ebx
0x18001bb03  js      loc_18001BC24
0x18001bb09  xor     edx, edx; Val
0x18001bb0b  lea     rcx, [rsp+8D0h+FindFileData]; void *
0x18001bb10  mov     r8d, 250h; Size
0x18001bb16  call    memset_0
0x18001bb1b  mov     r12d, 104h
0x18001bb21  lea     r9, asc_180032548; "*"
0x18001bb28  mov     edx, r12d; cchPathOut
0x18001bb2b  lea     rcx, [rbp+7D0h+pszPathOut]; pszPathOut
0x18001bb32  mov     r8, r14; pszPathIn
0x18001bb35  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001bb39  call    cs:__imp_PathCchCombine
0x18001bb3f  test    eax, eax
0x18001bb41  js      short loc_18001BB58
0x18001bb43  lea     rdx, [rsp+8D0h+FindFileData]; lpFindFileData
0x18001bb48  lea     rcx, [rbp+7D0h+pszPathOut]; lpFileName
0x18001bb4f  call    cs:__imp_FindFirstFileW
0x18001bb55  mov     rdi, rax
0x18001bb58  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18001bb5c  jz      loc_18001BC0F
0x18001bb62  cmp     [rsp+8D0h+FindFileData.cFileName], 2Eh ; '.'
0x18001bb68  jz      loc_18001BBEE
0x18001bb6e  lea     r9, [rsp+8D0h+FindFileData.cFileName]; pszMore
0x18001bb73  mov     r8, r14; pszPathIn
0x18001bb76  mov     rdx, r12; cchPathOut
0x18001bb79  lea     rcx, [rbp+7D0h+pszPathIn]; pszPathOut
0x18001bb80  call    cs:__imp_PathCchCombine
0x18001bb86  test    eax, eax
0x18001bb88  js      short loc_18001BBEE
0x18001bb8a  test    [rsp+8D0h+FindFileData.dwFileAttributes], 400h
0x18001bb92  jnz     short loc_18001BBEE
0x18001bb94  test    byte ptr [rsp+8D0h+FindFileData.dwFileAttributes], 10h
0x18001bb99  jz      short loc_18001BBDA
0x18001bb9b  lea     r9, [rsp+8D0h+FindFileData.cFileName]; pszMore
0x18001bba0  mov     r8, rsi; pszPathIn
0x18001bba3  mov     rdx, r12; cchPathOut
0x18001bba6  lea     rcx, [rbp+7D0h+PathName]; pszPathOut
0x18001bbad  call    cs:__imp_PathCchCombine
0x18001bbb3  test    eax, eax
0x18001bbb5  js      short loc_18001BBEE
0x18001bbb7  cmp     [rsp+8D0h+FindFileData.cFileName], 2Eh ; '.'
0x18001bbbd  jz      short loc_18001BBEE
0x18001bbbf  lea     rdx, [rbp+7D0h+PathName]; unsigned __int16 *
0x18001bbc6  lea     rcx, [rbp+7D0h+pszPathIn]; unsigned __int16 *
0x18001bbcd  call    ?CopyFolderContents@@YAJPEBG0@Z; CopyFolderContents(ushort const *,ushort const *)
0x18001bbd2  mov     ebx, eax
0x18001bbd4  test    eax, eax
0x18001bbd6  js      short loc_18001BC04
0x18001bbd8  jmp     short loc_18001BBEE
0x18001bbda  lea     r8, [rsp+8D0h+FindFileData.cFileName]; unsigned __int16 *
0x18001bbdf  mov     rdx, rsi; pszPathIn
0x18001bbe2  lea     rcx, [rbp+7D0h+pszPathIn]; lpExistingFileName
0x18001bbe9  call    ?CopyAsTwoFiles@@YAJPEBG00@Z; CopyAsTwoFiles(ushort const *,ushort const *,ushort const *)
0x18001bbee  lea     rdx, [rsp+8D0h+FindFileData]; lpFindFileData
0x18001bbf3  mov     rcx, rdi; hFindFile
0x18001bbf6  call    cs:__imp_FindNextFileW
0x18001bbfc  test    eax, eax
0x18001bbfe  jnz     loc_18001BB62
0x18001bc04  mov     rcx, rdi; hFindFile
0x18001bc07  call    cs:__imp_FindClose
0x18001bc0d  jmp     short loc_18001BC24
0x18001bc0f  call    cs:__imp_GetLastError
0x18001bc15  mov     ebx, eax
0x18001bc17  test    eax, eax
0x18001bc19  jle     short loc_18001BC24
0x18001bc1b  movzx   ebx, ax
0x18001bc1e  or      ebx, 80070000h
0x18001bc24  mov     eax, ebx
0x18001bc26  mov     rcx, [rbp+7D0h+var_30]
0x18001bc2d  xor     rcx, rsp; StackCookie
0x18001bc30  call    __security_check_cookie
0x18001bc35  mov     rbx, [rsp+8D0h+arg_10]
0x18001bc3d  add     rsp, 8B0h
0x18001bc44  pop     r14
0x18001bc46  pop     r12
0x18001bc48  pop     rdi
0x18001bc49  pop     rsi
0x18001bc4a  pop     rbp
0x18001bc4b  retn
```
