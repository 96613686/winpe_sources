# Win32FileSystem::FindFileNamesMatchingSpec<bool (*)(_WIN32_FIND_DATAW const &)>(ushort const *,_FINDEX_SEARCH_OPS,bool (*const &)(_WIN32_FIND_DATAW const &))

- ea: `0x18003b060`
- end: `0x18003b18e`
- name: `??$FindFileNamesMatchingSpec@P6A_NAEBU_WIN32_FIND_DATAW@@@Z@Win32FileSystem@@CA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEBGW4_FINDEX_SEARCH_OPS@@AEBQ6A_NAEBU_WIN32_FIND_DATAW@@@Z@Z`
- size: `302`
- prototype: `_QWORD *__fastcall(_QWORD *, const WCHAR *, FINDEX_SEARCH_OPS, unsigned __int8 (__fastcall **)(struct _WIN32_FIND_DATAW *))`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18003b000`

## callees

- `0x18001ee7c`
- `0x1800202e4`
- `0x180021920`
- `0x18003b060`
- `0x180061320`
- `0x180062314`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18003b150`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18003b150`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18003b167`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18003b167`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x18003b0f2`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x18003b0f2`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripPathW` at `0x18003b11b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripPathW` at `0x18003b11b`

## pseudocode

```c
_QWORD *__fastcall Win32FileSystem::FindFileNamesMatchingSpec<bool (*)(_WIN32_FIND_DATAW const &)>(
        _QWORD *a1,
        const WCHAR *a2,
        FINDEX_SEARCH_OPS a3,
        unsigned __int8 (__fastcall **a4)(struct _WIN32_FIND_DATAW *))
{
  char *FirstFile; // rbx
  _BYTE v10[40]; // [rsp+48h] [rbp-B8h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+70h] [rbp-90h] BYREF

  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFile = (char *)FindFirstFileExW(a2, FindExInfoBasic, &FindFileData, a3, 0, 0);
  if ( FirstFile != (char *)-1LL )
  {
    do
    {
      if ( (*a4)(&FindFileData) )
      {
        PathStripPathW(FindFileData.cFileName);
        std::wstring::wstring(v10, FindFileData.cFileName);
        std::vector<std::wstring>::push_back(a1, v10);
        std::wstring::_Tidy_deallocate(v10);
      }
    }
    while ( FindNextFileW(FirstFile, &FindFileData) );
  }
  if ( (unsigned __int64)(FirstFile - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    FindClose(FirstFile);
  return a1;
}

```

## disassembly

```asm
0x18003b060  push    rbp
0x18003b062  push    rbx
0x18003b063  push    rsi
0x18003b064  push    rdi
0x18003b065  push    r14
0x18003b067  lea     rbp, [rsp-1D0h]
0x18003b06f  sub     rsp, 2D0h
0x18003b076  mov     rax, cs:__security_cookie
0x18003b07d  xor     rax, rsp
0x18003b080  mov     [rbp+1F0h+var_30], rax
0x18003b087  mov     r14, r9
0x18003b08a  mov     ebx, r8d
0x18003b08d  mov     rdi, rdx
0x18003b090  mov     rsi, rcx
0x18003b093  mov     [rsp+2F0h+var_2B8], rcx
0x18003b098  mov     [rsp+2F0h+var_2C0], 0
0x18003b0a0  mov     qword ptr [rcx], 0
0x18003b0a7  mov     qword ptr [rcx+8], 0
0x18003b0af  mov     qword ptr [rcx+10h], 0
0x18003b0b7  mov     [rsp+2F0h+var_2C0], 1
0x18003b0bf  xor     edx, edx; Val
0x18003b0c1  mov     r8d, 250h; Size
0x18003b0c7  lea     rcx, [rsp+2F0h+FindFileData]; void *
0x18003b0cc  call    memset_0
0x18003b0d1  mov     [rsp+2F0h+dwAdditionalFlags], 0; dwAdditionalFlags
0x18003b0d9  mov     [rsp+2F0h+lpSearchFilter], 0; lpSearchFilter
0x18003b0e2  mov     r9d, ebx; fSearchOp
0x18003b0e5  lea     r8, [rsp+2F0h+FindFileData]; lpFindFileData
0x18003b0ea  mov     edx, 1; fInfoLevelId
0x18003b0ef  mov     rcx, rdi; lpFileName
0x18003b0f2  call    cs:__imp_FindFirstFileExW
0x18003b0f8  mov     rbx, rax
0x18003b0fb  mov     [rsp+2F0h+var_2B0], rax
0x18003b100  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003b104  jz      short loc_18003B15A
0x18003b106  lea     rcx, [rsp+2F0h+FindFileData]
0x18003b10b  mov     rax, [r14]
0x18003b10e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b113  test    al, al
0x18003b115  jz      short loc_18003B148
0x18003b117  lea     rcx, [rbp+1F0h+pszPath]; pszPath
0x18003b11b  call    cs:__imp_PathStripPathW
0x18003b121  lea     rdx, [rbp+1F0h+pszPath]
0x18003b125  lea     rcx, [rsp+2F0h+var_2A8]
0x18003b12a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003b12f  nop
0x18003b130  lea     rdx, [rsp+2F0h+var_2A8]
0x18003b135  mov     rcx, rsi
0x18003b138  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x18003b13d  nop
0x18003b13e  lea     rcx, [rsp+2F0h+var_2A8]
0x18003b143  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003b148  lea     rdx, [rsp+2F0h+FindFileData]; lpFindFileData
0x18003b14d  mov     rcx, rbx; hFindFile
0x18003b150  call    cs:__imp_FindNextFileW
0x18003b156  test    eax, eax
0x18003b158  jnz     short loc_18003B106
0x18003b15a  lea     rcx, [rbx-1]
0x18003b15e  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18003b162  ja      short loc_18003B16D
0x18003b164  mov     rcx, rbx; hFindFile
0x18003b167  call    cs:__imp_FindClose
0x18003b16d  mov     rax, rsi
0x18003b170  mov     rcx, [rbp+1F0h+var_30]
0x18003b177  xor     rcx, rsp; StackCookie
0x18003b17a  call    __security_check_cookie
0x18003b17f  add     rsp, 2D0h
0x18003b186  pop     r14
0x18003b188  pop     rdi
0x18003b189  pop     rsi
0x18003b18a  pop     rbx
0x18003b18b  pop     rbp
0x18003b18c  retn
```
