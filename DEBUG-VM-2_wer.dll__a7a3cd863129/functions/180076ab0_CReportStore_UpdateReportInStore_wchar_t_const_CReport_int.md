# CReportStore::UpdateReportInStore(wchar_t const *,CReport *,int)

- ea: `0x180076ab0`
- end: `0x180076d1c`
- name: `?UpdateReportInStore@CReportStore@@UEAAJPEB_WPEAVCReport@@H@Z`
- size: `620`
- prototype: `int(CReportStore *__hidden this, const wchar_t *, struct CReport *, int)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x180075ea0`

## callees

- `0x180007e10`
- `0x180008568`
- `0x18000bc10`
- `0x18000cc74`
- `0x18000dad0`
- `0x18001dfac`
- `0x18002c198`
- `0x18002ffc4`
- `0x18003db78`
- `0x18003e864`
- `0x180072bdc`
- `0x180073970`
- `0x1800740c4`
- `0x18007683c`
- `0x180076ab0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076c62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076c62`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180076c58`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180076c58`

## string_xrefs

- `0x180076b00`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`
- `0x180076b54`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`
- `0x180076bbe`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`
- `0x180076c8c`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`
- `0x180076ca8`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`
- `0x180076cf6`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CReportStore::UpdateReportInStore(CReportStore *this, wchar_t *a2, struct CReport *a3, int a4)
{
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // eax
  int v9; // eax
  __int64 v10; // rdx
  int v11; // r8d
  CReport *v12; // rcx
  DWORD LastError; // ebx
  int v14; // eax
  __int64 v16; // [rsp+20h] [rbp-60h] BYREF
  _QWORD v17[2]; // [rsp+28h] [rbp-58h] BYREF
  char v18; // [rsp+38h] [rbp-48h]
  LPCWSTR lpExistingFileName[4]; // [rsp+40h] [rbp-40h] BYREF
  LPCWSTR lpNewFileName[4]; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]
  int v22; // [rsp+A8h] [rbp+28h] BYREF
  CReport *v23; // [rsp+B0h] [rbp+30h] BYREF

  v23 = a3;
  if ( !a2 || !a3 )
  {
    v7 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5A1,
      (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
      (const char *)0x80070057LL,
      v16);
    return v7;
  }
  v16 = 0;
  v6 = UtilVerifyAndLockDirectory(a2, (__int64)&v16);
  v7 = v6;
  if ( v6 >= 0 )
  {
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpExistingFileName);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpNewFileName);
    v22 = 0;
    if ( !(unsigned int)CReport::IsReportLocked(v23) )
    {
      v8 = CReport::TryReportLock(v23);
      v7 = v8;
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5AE,
          (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
          (const char *)(unsigned int)v8,
          v16);
LABEL_8:
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpNewFileName);
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpExistingFileName);
        goto LABEL_29;
      }
      v22 = 1;
    }
    v17[0] = &v22;
    v17[1] = &v23;
    v18 = 1;
    v9 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
           lpExistingFileName,
           L"%s\\%s",
           a2,
           L"Report.wer.tmp");
    v7 = v9;
    if ( v9 >= 0 )
    {
      v9 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
             lpNewFileName,
             L"%s\\%s",
             a2,
             L"Report.wer");
      v7 = v9;
      if ( v9 >= 0 )
      {
        v12 = v23;
        if ( a4 && !*((_DWORD *)v23 + 1637) )
        {
          v9 = CReport::SaveTemporaryAttachedFiles(v23, a2);
          v7 = v9;
          if ( v9 < 0 )
          {
            v10 = 1478;
            goto LABEL_12;
          }
          v12 = v23;
        }
        v9 = CReport::WriteReportToFile(v12, lpExistingFileName[0], v11, 0);
        v7 = v9;
        if ( v9 >= 0 )
        {
          if ( MoveFileExW(lpExistingFileName[0], lpNewFileName[0], 1u) )
            goto LABEL_28;
          LastError = GetLastError();
          *((_DWORD *)v23 + 1656) = 15;
          v14 = UtilDeleteFilePath(lpExistingFileName[0]);
          if ( v14 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x5D1,
              (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
              (const char *)(unsigned int)v14,
              v16);
          if ( !LastError )
          {
LABEL_28:
            tlx::_UndoSolo__lambda_d550510c0ea602fc073c13b7512821bf___::__UndoSolo__lambda_d550510c0ea602fc073c13b7512821bf___(v17);
            utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpNewFileName);
            utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpExistingFileName);
            v7 = 0;
            goto LABEL_29;
          }
          v7 = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)0x5D3,
                 (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
                 (const char *)LastError,
                 v16);
          goto LABEL_13;
        }
        v10 = 1482;
      }
      else
      {
        v10 = 1468;
      }
    }
    else
    {
      v10 = 1466;
    }
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
      (const char *)(unsigned int)v9,
      v16);
LABEL_13:
    tlx::_UndoSolo__lambda_d550510c0ea602fc073c13b7512821bf___::__UndoSolo__lambda_d550510c0ea602fc073c13b7512821bf___(v17);
    goto LABEL_8;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5A6,
    (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
    (const char *)(unsigned int)v6,
    v16);
LABEL_29:
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v16);
  return v7;
}

```

## disassembly

```asm
0x180076ab0  mov     [rsp-18h+arg_0], rbx
0x180076ab5  mov     [rsp-18h+arg_10], r8
0x180076aba  push    rbp
0x180076abb  push    rsi
0x180076abc  push    rdi
0x180076abd  mov     rbp, rsp
0x180076ac0  sub     rsp, 80h
0x180076ac7  mov     esi, r9d
0x180076aca  mov     rdi, rdx
0x180076acd  test    rdx, rdx
0x180076ad0  jz      loc_180076CEA
0x180076ad6  test    r8, r8
0x180076ad9  jz      loc_180076CEA
0x180076adf  mov     [rbp+var_60], 0
0x180076ae7  lea     rdx, [rbp+var_60]
0x180076aeb  mov     rcx, rdi; wchar_t *
0x180076aee  call    ?UtilVerifyAndLockDirectory@@YAJPEB_WPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; UtilVerifyAndLockDirectory(wchar_t const *,tlx::unique_any<tlx::file_handle_traits> *)
0x180076af3  mov     ebx, eax
0x180076af5  test    eax, eax
0x180076af7  jns     short loc_180076B16
0x180076af9  mov     rcx, [rbp+18h]; this
0x180076afd  mov     r9d, eax; char *
0x180076b00  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x180076b07  mov     edx, 5A6h; void *
0x180076b0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076b11  jmp     loc_180076CDF
0x180076b16  lea     rcx, [rbp+lpExistingFileName]; void *
0x180076b1a  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180076b1f  nop
0x180076b20  lea     rcx, [rbp+lpNewFileName]; void *
0x180076b24  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180076b29  nop
0x180076b2a  mov     [rbp+arg_8], 0
0x180076b31  mov     rcx, [rbp+arg_10]; this
0x180076b35  call    ?IsReportLocked@CReport@@QEAAHXZ; CReport::IsReportLocked(void)
0x180076b3a  test    eax, eax
0x180076b3c  jnz     short loc_180076B85
0x180076b3e  mov     rcx, [rbp+arg_10]; this
0x180076b42  call    ?TryReportLock@CReport@@QEAAJXZ; CReport::TryReportLock(void)
0x180076b47  mov     ebx, eax
0x180076b49  test    eax, eax
0x180076b4b  jns     short loc_180076B7E
0x180076b4d  mov     rcx, [rbp+18h]; this
0x180076b51  mov     r9d, eax; char *
0x180076b54  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x180076b5b  mov     edx, 5AEh; void *
0x180076b60  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076b65  nop
0x180076b66  lea     rcx, [rbp+lpNewFileName]; void *
0x180076b6a  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180076b6f  nop
0x180076b70  lea     rcx, [rbp+lpExistingFileName]; void *
0x180076b74  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180076b79  jmp     loc_180076CDF
0x180076b7e  mov     [rbp+arg_8], 1
0x180076b85  lea     rax, [rbp+arg_8]
0x180076b89  mov     [rbp+var_58], rax
0x180076b8d  lea     rax, [rbp+arg_10]
0x180076b91  mov     [rbp+var_50], rax
0x180076b95  mov     [rbp+var_48], 1
0x180076b99  lea     r9, aReportWerTmp; "Report.wer.tmp"
0x180076ba0  mov     r8, rdi
0x180076ba3  lea     rdx, aSS; "%s\\%s"
0x180076baa  lea     rcx, [rbp+lpExistingFileName]
0x180076bae  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180076bb3  mov     ebx, eax
0x180076bb5  test    eax, eax
0x180076bb7  jns     short loc_180076BDD
0x180076bb9  mov     edx, 5BAh; void *
0x180076bbe  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x180076bc5  mov     r9d, eax; char *
0x180076bc8  mov     rcx, [rbp+18h]; this
0x180076bcc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076bd1  nop
0x180076bd2  lea     rcx, [rbp+var_58]
0x180076bd6  call    tlx___UndoSolo__lambda_d550510c0ea602fc073c13b7512821bf_______UndoSolo__lambda_d550510c0ea602fc073c13b7512821bf___
0x180076bdb  jmp     short loc_180076B66
0x180076bdd  lea     r9, aReportWer; "Report.wer"
0x180076be4  mov     r8, rdi
0x180076be7  lea     rdx, aSS; "%s\\%s"
0x180076bee  lea     rcx, [rbp+lpNewFileName]
0x180076bf2  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180076bf7  mov     ebx, eax
0x180076bf9  test    eax, eax
0x180076bfb  jns     short loc_180076C04
0x180076bfd  mov     edx, 5BCh
0x180076c02  jmp     short loc_180076BBE
0x180076c04  mov     rcx, [rbp+arg_10]; this
0x180076c08  test    esi, esi
0x180076c0a  jz      short loc_180076C2E
0x180076c0c  cmp     dword ptr [rcx+1994h], 0
0x180076c13  jnz     short loc_180076C2E
0x180076c15  mov     rdx, rdi; wchar_t *
0x180076c18  call    ?SaveTemporaryAttachedFiles@CReport@@QEAAJPEB_W@Z; CReport::SaveTemporaryAttachedFiles(wchar_t const *)
0x180076c1d  mov     ebx, eax
0x180076c1f  test    eax, eax
0x180076c21  jns     short loc_180076C2A
0x180076c23  mov     edx, 5C6h
0x180076c28  jmp     short loc_180076BBE
0x180076c2a  mov     rcx, [rbp+arg_10]; this
0x180076c2e  xor     r9d, r9d; unsigned int
0x180076c31  mov     rdx, [rbp+lpExistingFileName]; wchar_t *
0x180076c35  call    ?WriteReportToFile@CReport@@QEAAJPEB_WHK@Z; CReport::WriteReportToFile(wchar_t const *,int,ulong)
0x180076c3a  mov     ebx, eax
0x180076c3c  test    eax, eax
0x180076c3e  jns     short loc_180076C4A
0x180076c40  mov     edx, 5CAh
0x180076c45  jmp     loc_180076BBE
0x180076c4a  mov     r8d, 1; dwFlags
0x180076c50  mov     rdx, [rbp+lpNewFileName]; lpNewFileName
0x180076c54  mov     rcx, [rbp+lpExistingFileName]; lpExistingFileName
0x180076c58  call    cs:__imp_MoveFileExW
0x180076c5e  test    eax, eax
0x180076c60  jnz     short loc_180076CC0
0x180076c62  call    cs:__imp_GetLastError
0x180076c68  mov     ebx, eax
0x180076c6a  mov     rcx, [rbp+arg_10]
0x180076c6e  mov     dword ptr [rcx+19E0h], 0Fh
0x180076c78  mov     rcx, [rbp+lpExistingFileName]; wchar_t *
0x180076c7c  call    ?UtilDeleteFilePath@@YAJPEB_W@Z; UtilDeleteFilePath(wchar_t const *)
0x180076c81  mov     rcx, [rbp+18h]; this
0x180076c85  test    eax, eax
0x180076c87  jns     short loc_180076C9D
0x180076c89  mov     r9d, eax; char *
0x180076c8c  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x180076c93  mov     edx, 5D1h; void *
0x180076c98  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180076c9d  test    ebx, ebx
0x180076c9f  jz      short loc_180076CC0
0x180076ca1  mov     rcx, [rbp+18h]; this
0x180076ca5  mov     r9d, ebx; char *
0x180076ca8  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x180076caf  mov     edx, 5D3h; void *
0x180076cb4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180076cb9  mov     ebx, eax
0x180076cbb  jmp     loc_180076BD2
0x180076cc0  lea     rcx, [rbp+var_58]
0x180076cc4  call    tlx___UndoSolo__lambda_d550510c0ea602fc073c13b7512821bf_______UndoSolo__lambda_d550510c0ea602fc073c13b7512821bf___
0x180076cc9  nop
0x180076cca  lea     rcx, [rbp+lpNewFileName]; void *
0x180076cce  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180076cd3  nop
0x180076cd4  lea     rcx, [rbp+lpExistingFileName]; void *
0x180076cd8  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180076cdd  xor     ebx, ebx
0x180076cdf  lea     rcx, [rbp+var_60]
0x180076ce3  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180076ce8  jmp     short loc_180076D07
0x180076cea  mov     rcx, [rbp+18h]; this
0x180076cee  mov     ebx, 80070057h
0x180076cf3  mov     r9d, ebx; char *
0x180076cf6  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x180076cfd  mov     edx, 5A1h; void *
0x180076d02  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076d07  mov     eax, ebx
0x180076d09  mov     rbx, [rsp+80h+arg_0]
0x180076d11  add     rsp, 80h
0x180076d18  pop     rdi
0x180076d19  pop     rsi
0x180076d1a  pop     rbp
0x180076d1b  retn
```
