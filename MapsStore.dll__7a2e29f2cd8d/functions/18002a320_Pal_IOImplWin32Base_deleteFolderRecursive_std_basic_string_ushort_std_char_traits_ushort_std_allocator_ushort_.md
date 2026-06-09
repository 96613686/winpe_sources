# Pal::IOImplWin32Base::deleteFolderRecursive(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18002a320`
- end: `0x18002a4cd`
- name: `?deleteFolderRecursive@IOImplWin32Base@Pal@@AEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `429`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x18002a2c0`
- `0x18002a320`

## callees

- `0x18000d090`
- `0x18000dcb0`
- `0x180011b58`
- `0x1800126c4`
- `0x180012720`
- `0x180016548`
- `0x1800179ac`
- `0x180021fb8`
- `0x180024c14`
- `0x180025c68`
- `0x18002a320`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18002a478`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18002a478`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18002a452`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18002a452`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18002a426`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18002a426`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002a441`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002a441`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18002a39b`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18002a39b`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002a463`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002a4c4`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002a463`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002a4c4`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Pal::IOImplWin32Base::deleteFolderRecursive(__int64 a1, __int64 a2)
{
  const WCHAR *v4; // rax
  HANDLE FirstFileW; // rbx
  __int64 v6; // rax
  __int64 v7; // rax
  const WCHAR *v8; // rax
  const WCHAR *v9; // rax
  const WCHAR *v10; // rax
  _BYTE v12[8]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v13[32]; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v14[32]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v15[32]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v16[40]; // [rsp+88h] [rbp-78h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+B0h] [rbp-50h] BYREF

  std::wstring::wstring(v13);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  CallingStateTracker::CallingStateTracker(v12);
  std::operator+<unsigned short>(v14, a2, L"\\*.*");
  v4 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v14);
  FirstFileW = FindFirstFileW(v4, &FindFileData);
  if ( FirstFileW != (HANDLE)-1LL )
  {
    do
    {
      if ( FindFileData.cFileName[0] != 46 )
      {
        v6 = std::operator+<unsigned short>(v16, a2, L"\\");
        v7 = std::operator+<unsigned short>(v15, v6, FindFileData.cFileName);
        std::wstring::operator=(v13, v7);
        std::wstring::_Tidy_deallocate(v15);
        std::wstring::_Tidy_deallocate(v16);
        if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
        {
          Pal::IOImplWin32Base::deleteFolderRecursive(a1, v13);
        }
        else
        {
          v8 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v13);
          if ( !SetFileAttributesW(v8, 0x80u)
            || (v9 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v13), !DeleteFileW(v9)) )
          {
            FindClose(FirstFileW);
            goto LABEL_10;
          }
        }
      }
    }
    while ( FindNextFileW(FirstFileW, &FindFileData) );
    if ( FindClose(FirstFileW) )
    {
      v10 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
      RemoveDirectoryW(v10);
    }
  }
LABEL_10:
  std::wstring::_Tidy_deallocate(v14);
  CallingStateTracker::~CallingStateTracker((CallingStateTracker *)v12);
  return std::wstring::_Tidy_deallocate(v13);
}

```

## disassembly

```asm
0x18002a320  mov     [rsp-8+arg_10], rbx
0x18002a325  push    rbp
0x18002a326  push    rsi
0x18002a327  push    rdi
0x18002a328  lea     rbp, [rsp-210h]
0x18002a330  sub     rsp, 310h
0x18002a337  mov     rax, cs:__security_cookie
0x18002a33e  xor     rax, rsp
0x18002a341  mov     [rbp+220h+var_20], rax
0x18002a348  mov     rdi, rdx
0x18002a34b  mov     rsi, rcx
0x18002a34e  lea     rcx, [rsp+320h+var_2F8]
0x18002a353  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002a358  nop
0x18002a359  xor     edx, edx; Val
0x18002a35b  mov     r8d, 250h; Size
0x18002a361  lea     rcx, [rbp+220h+FindFileData]; void *
0x18002a365  call    memset_0
0x18002a36a  lea     rcx, [rsp+320h+var_300]
0x18002a36f  call    ??0CallingStateTracker@@QEAA@W4CallingState@@@Z; CallingStateTracker::CallingStateTracker(CallingState)
0x18002a374  nop
0x18002a375  lea     r8, asc_1800A4EC0; "\\*.*"
0x18002a37c  mov     rdx, rdi
0x18002a37f  lea     rcx, [rsp+320h+var_2D8]
0x18002a384  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18002a389  nop
0x18002a38a  lea     rcx, [rsp+320h+var_2D8]
0x18002a38f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002a394  mov     rcx, rax; lpFileName
0x18002a397  lea     rdx, [rbp+220h+FindFileData]; lpFindFileData
0x18002a39b  call    cs:__imp_FindFirstFileW
0x18002a3a1  mov     rbx, rax
0x18002a3a4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002a3a8  jz      loc_18002A47F
0x18002a3ae  cmp     [rbp+220h+FindFileData.cFileName], 2Eh ; '.'
0x18002a3b3  jz      loc_18002A44B
0x18002a3b9  lea     r8, asc_1800A4EBC; "\\"
0x18002a3c0  mov     rdx, rdi
0x18002a3c3  lea     rcx, [rbp+220h+var_298]
0x18002a3c7  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18002a3cc  nop
0x18002a3cd  lea     r8, [rbp+220h+FindFileData.cFileName]
0x18002a3d1  mov     rdx, rax
0x18002a3d4  lea     rcx, [rsp+320h+var_2B8]
0x18002a3d9  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18002a3de  mov     rdx, rax
0x18002a3e1  lea     rcx, [rsp+320h+var_2F8]
0x18002a3e6  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002a3eb  lea     rcx, [rsp+320h+var_2B8]
0x18002a3f0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a3f5  nop
0x18002a3f6  lea     rcx, [rbp+220h+var_298]
0x18002a3fa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a3ff  test    byte ptr [rbp+220h+FindFileData.dwFileAttributes], 10h
0x18002a403  jz      short loc_18002A414
0x18002a405  lea     rdx, [rsp+320h+var_2F8]
0x18002a40a  mov     rcx, rsi
0x18002a40d  call    ?deleteFolderRecursive@IOImplWin32Base@Pal@@AEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Pal::IOImplWin32Base::deleteFolderRecursive(std::wstring const &)
0x18002a412  jmp     short loc_18002A44B
0x18002a414  lea     rcx, [rsp+320h+var_2F8]
0x18002a419  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002a41e  mov     rcx, rax; lpFileName
0x18002a421  mov     edx, 80h; dwFileAttributes
0x18002a426  call    cs:__imp_SetFileAttributesW
0x18002a42c  test    eax, eax
0x18002a42e  jz      loc_18002A4C1
0x18002a434  lea     rcx, [rsp+320h+var_2F8]
0x18002a439  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002a43e  mov     rcx, rax; lpFileName
0x18002a441  call    cs:__imp_DeleteFileW
0x18002a447  test    eax, eax
0x18002a449  jz      short loc_18002A4C1
0x18002a44b  lea     rdx, [rbp+220h+FindFileData]; lpFindFileData
0x18002a44f  mov     rcx, rbx; hFindFile
0x18002a452  call    cs:__imp_FindNextFileW
0x18002a458  test    eax, eax
0x18002a45a  jnz     loc_18002A3AE
0x18002a460  mov     rcx, rbx; hFindFile
0x18002a463  call    cs:__imp_FindClose
0x18002a469  test    eax, eax
0x18002a46b  jz      short loc_18002A47F
0x18002a46d  mov     rcx, rdi
0x18002a470  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002a475  mov     rcx, rax; lpPathName
0x18002a478  call    cs:__imp_RemoveDirectoryW
0x18002a47e  nop
0x18002a47f  lea     rcx, [rsp+320h+var_2D8]
0x18002a484  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a489  nop
0x18002a48a  lea     rcx, [rsp+320h+var_300]; this
0x18002a48f  call    ??1CallingStateTracker@@QEAA@XZ; CallingStateTracker::~CallingStateTracker(void)
0x18002a494  nop
0x18002a495  lea     rcx, [rsp+320h+var_2F8]
0x18002a49a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a49f  mov     rcx, [rbp+220h+var_20]
0x18002a4a6  xor     rcx, rsp; StackCookie
0x18002a4a9  call    __security_check_cookie
0x18002a4ae  mov     rbx, [rsp+320h+arg_10]
0x18002a4b6  add     rsp, 310h
0x18002a4bd  pop     rdi
0x18002a4be  pop     rsi
0x18002a4bf  pop     rbp
0x18002a4c0  retn
0x18002a4c1  mov     rcx, rbx; hFindFile
0x18002a4c4  call    cs:__imp_FindClose
0x18002a4ca  jmp     short loc_18002A47F
```
