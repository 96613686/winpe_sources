# Pal::IOImplWin32Base::deleteFolderRecursive(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180016940`
- end: `0x180016aed`
- name: `?deleteFolderRecursive@IOImplWin32Base@Pal@@AEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `429`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x1800168e0`
- `0x180016940`

## callees

- `0x1800094a0`
- `0x18000a074`
- `0x18000ba50`
- `0x18000c2f8`
- `0x18000c354`
- `0x18000cf90`
- `0x18000cfcc`
- `0x180010354`
- `0x180011628`
- `0x180011ddc`
- `0x180016940`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180016a83`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180016ae4`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180016a83`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180016ae4`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180016a98`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180016a98`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180016a72`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180016a72`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800169bb`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800169bb`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180016a61`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180016a61`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180016a46`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180016a46`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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

  std::wstring::wstring((__int64)v13);
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
0x180016940  mov     [rsp-8+arg_10], rbx
0x180016945  push    rbp
0x180016946  push    rsi
0x180016947  push    rdi
0x180016948  lea     rbp, [rsp-210h]
0x180016950  sub     rsp, 310h
0x180016957  mov     rax, cs:__security_cookie
0x18001695e  xor     rax, rsp
0x180016961  mov     [rbp+220h+var_20], rax
0x180016968  mov     rdi, rdx
0x18001696b  mov     rsi, rcx
0x18001696e  lea     rcx, [rsp+320h+var_2F8]
0x180016973  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180016978  nop
0x180016979  xor     edx, edx; Val
0x18001697b  mov     r8d, 250h; Size
0x180016981  lea     rcx, [rbp+220h+FindFileData]; void *
0x180016985  call    memset_0
0x18001698a  lea     rcx, [rsp+320h+var_300]
0x18001698f  call    ??0CallingStateTracker@@QEAA@W4CallingState@@@Z; CallingStateTracker::CallingStateTracker(CallingState)
0x180016994  nop
0x180016995  lea     r8, asc_180048770; "\\*.*"
0x18001699c  mov     rdx, rdi
0x18001699f  lea     rcx, [rsp+320h+var_2D8]
0x1800169a4  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x1800169a9  nop
0x1800169aa  lea     rcx, [rsp+320h+var_2D8]
0x1800169af  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800169b4  mov     rcx, rax; lpFileName
0x1800169b7  lea     rdx, [rbp+220h+FindFileData]; lpFindFileData
0x1800169bb  call    cs:__imp_FindFirstFileW
0x1800169c1  mov     rbx, rax
0x1800169c4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800169c8  jz      loc_180016A9F
0x1800169ce  cmp     [rbp+220h+FindFileData.cFileName], 2Eh ; '.'
0x1800169d3  jz      loc_180016A6B
0x1800169d9  lea     r8, asc_18004876C; "\\"
0x1800169e0  mov     rdx, rdi
0x1800169e3  lea     rcx, [rbp+220h+var_298]
0x1800169e7  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x1800169ec  nop
0x1800169ed  lea     r8, [rbp+220h+FindFileData.cFileName]
0x1800169f1  mov     rdx, rax
0x1800169f4  lea     rcx, [rsp+320h+var_2B8]
0x1800169f9  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800169fe  mov     rdx, rax
0x180016a01  lea     rcx, [rsp+320h+var_2F8]
0x180016a06  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180016a0b  lea     rcx, [rsp+320h+var_2B8]
0x180016a10  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180016a15  nop
0x180016a16  lea     rcx, [rbp+220h+var_298]
0x180016a1a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180016a1f  test    byte ptr [rbp+220h+FindFileData.dwFileAttributes], 10h
0x180016a23  jz      short loc_180016A34
0x180016a25  lea     rdx, [rsp+320h+var_2F8]
0x180016a2a  mov     rcx, rsi
0x180016a2d  call    ?deleteFolderRecursive@IOImplWin32Base@Pal@@AEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Pal::IOImplWin32Base::deleteFolderRecursive(std::wstring const &)
0x180016a32  jmp     short loc_180016A6B
0x180016a34  lea     rcx, [rsp+320h+var_2F8]
0x180016a39  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180016a3e  mov     rcx, rax; lpFileName
0x180016a41  mov     edx, 80h; dwFileAttributes
0x180016a46  call    cs:__imp_SetFileAttributesW
0x180016a4c  test    eax, eax
0x180016a4e  jz      loc_180016AE1
0x180016a54  lea     rcx, [rsp+320h+var_2F8]
0x180016a59  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180016a5e  mov     rcx, rax; lpFileName
0x180016a61  call    cs:__imp_DeleteFileW
0x180016a67  test    eax, eax
0x180016a69  jz      short loc_180016AE1
0x180016a6b  lea     rdx, [rbp+220h+FindFileData]; lpFindFileData
0x180016a6f  mov     rcx, rbx; hFindFile
0x180016a72  call    cs:__imp_FindNextFileW
0x180016a78  test    eax, eax
0x180016a7a  jnz     loc_1800169CE
0x180016a80  mov     rcx, rbx; hFindFile
0x180016a83  call    cs:__imp_FindClose
0x180016a89  test    eax, eax
0x180016a8b  jz      short loc_180016A9F
0x180016a8d  mov     rcx, rdi
0x180016a90  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180016a95  mov     rcx, rax; lpPathName
0x180016a98  call    cs:__imp_RemoveDirectoryW
0x180016a9e  nop
0x180016a9f  lea     rcx, [rsp+320h+var_2D8]
0x180016aa4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180016aa9  nop
0x180016aaa  lea     rcx, [rsp+320h+var_300]; this
0x180016aaf  call    ??1CallingStateTracker@@QEAA@XZ; CallingStateTracker::~CallingStateTracker(void)
0x180016ab4  nop
0x180016ab5  lea     rcx, [rsp+320h+var_2F8]
0x180016aba  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180016abf  mov     rcx, [rbp+220h+var_20]
0x180016ac6  xor     rcx, rsp; StackCookie
0x180016ac9  call    __security_check_cookie
0x180016ace  mov     rbx, [rsp+320h+arg_10]
0x180016ad6  add     rsp, 310h
0x180016add  pop     rdi
0x180016ade  pop     rsi
0x180016adf  pop     rbp
0x180016ae0  retn
0x180016ae1  mov     rcx, rbx; hFindFile
0x180016ae4  call    cs:__imp_FindClose
0x180016aea  jmp     short loc_180016A9F
```
