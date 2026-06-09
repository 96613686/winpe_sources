# CReportStore::UpdateReportInStore(wchar_t const *,CReport *,int)

- ea: `0x180076b00`
- end: `0x180076d6c`
- name: `?UpdateReportInStore@CReportStore@@UEAAJPEB_WPEAVCReport@@H@Z`
- size: `620`
- prototype: `int(CReportStore *__hidden this, const wchar_t *, struct CReport *, int)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x180075ef0`

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
- `0x180072c2c`
- `0x1800739c0`
- `0x180074114`
- `0x18007688c`
- `0x180076b00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076cb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076cb2`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180076ca8`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180076ca8`

## string_xrefs

- `0x180076b50`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`
- `0x180076ba4`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`
- `0x180076c0e`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`
- `0x180076cdc`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`
- `0x180076cf8`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`
- `0x180076d46`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`

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
0x180076b00  mov     [rsp-18h+arg_0], rbx
0x180076b05  mov     [rsp-18h+arg_10], r8
0x180076b0a  push    rbp
0x180076b0b  push    rsi
0x180076b0c  push    rdi
0x180076b0d  mov     rbp, rsp
0x180076b10  sub     rsp, 80h
0x180076b17  mov     esi, r9d
0x180076b1a  mov     rdi, rdx
0x180076b1d  test    rdx, rdx
0x180076b20  jz      loc_180076D3A
0x180076b26  test    r8, r8
0x180076b29  jz      loc_180076D3A
0x180076b2f  mov     [rbp+var_60], 0
0x180076b37  lea     rdx, [rbp+var_60]
0x180076b3b  mov     rcx, rdi; wchar_t *
0x180076b3e  call    ?UtilVerifyAndLockDirectory@@YAJPEB_WPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; UtilVerifyAndLockDirectory(wchar_t const *,tlx::unique_any<tlx::file_handle_traits> *)
0x180076b43  mov     ebx, eax
0x180076b45  test    eax, eax
0x180076b47  jns     short loc_180076B66
0x180076b49  mov     rcx, [rbp+18h]; this
0x180076b4d  mov     r9d, eax; char *
0x180076b50  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x180076b57  mov     edx, 5A6h; void *
0x180076b5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076b61  jmp     loc_180076D2F
0x180076b66  lea     rcx, [rbp+lpExistingFileName]; void *
0x180076b6a  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180076b6f  nop
0x180076b70  lea     rcx, [rbp+lpNewFileName]; void *
0x180076b74  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180076b79  nop
0x180076b7a  mov     [rbp+arg_8], 0
0x180076b81  mov     rcx, [rbp+arg_10]; this
0x180076b85  call    ?IsReportLocked@CReport@@QEAAHXZ; CReport::IsReportLocked(void)
0x180076b8a  test    eax, eax
0x180076b8c  jnz     short loc_180076BD5
0x180076b8e  mov     rcx, [rbp+arg_10]; this
0x180076b92  call    ?TryReportLock@CReport@@QEAAJXZ; CReport::TryReportLock(void)
0x180076b97  mov     ebx, eax
0x180076b99  test    eax, eax
0x180076b9b  jns     short loc_180076BCE
0x180076b9d  mov     rcx, [rbp+18h]; this
0x180076ba1  mov     r9d, eax; char *
0x180076ba4  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x180076bab  mov     edx, 5AEh; void *
0x180076bb0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076bb5  nop
0x180076bb6  lea     rcx, [rbp+lpNewFileName]; void *
0x180076bba  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180076bbf  nop
0x180076bc0  lea     rcx, [rbp+lpExistingFileName]; void *
0x180076bc4  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180076bc9  jmp     loc_180076D2F
0x180076bce  mov     [rbp+arg_8], 1
0x180076bd5  lea     rax, [rbp+arg_8]
0x180076bd9  mov     [rbp+var_58], rax
0x180076bdd  lea     rax, [rbp+arg_10]
0x180076be1  mov     [rbp+var_50], rax
0x180076be5  mov     [rbp+var_48], 1
0x180076be9  lea     r9, aReportWerTmp; "Report.wer.tmp"
0x180076bf0  mov     r8, rdi
0x180076bf3  lea     rdx, aSS; "%s\\%s"
0x180076bfa  lea     rcx, [rbp+lpExistingFileName]
0x180076bfe  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180076c03  mov     ebx, eax
0x180076c05  test    eax, eax
0x180076c07  jns     short loc_180076C2D
0x180076c09  mov     edx, 5BAh; void *
0x180076c0e  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x180076c15  mov     r9d, eax; char *
0x180076c18  mov     rcx, [rbp+18h]; this
0x180076c1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076c21  nop
0x180076c22  lea     rcx, [rbp+var_58]
0x180076c26  call    tlx___UndoSolo__lambda_d550510c0ea602fc073c13b7512821bf_______UndoSolo__lambda_d550510c0ea602fc073c13b7512821bf___
0x180076c2b  jmp     short loc_180076BB6
0x180076c2d  lea     r9, aReportWer; "Report.wer"
0x180076c34  mov     r8, rdi
0x180076c37  lea     rdx, aSS; "%s\\%s"
0x180076c3e  lea     rcx, [rbp+lpNewFileName]
0x180076c42  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180076c47  mov     ebx, eax
0x180076c49  test    eax, eax
0x180076c4b  jns     short loc_180076C54
0x180076c4d  mov     edx, 5BCh
0x180076c52  jmp     short loc_180076C0E
0x180076c54  mov     rcx, [rbp+arg_10]; this
0x180076c58  test    esi, esi
0x180076c5a  jz      short loc_180076C7E
0x180076c5c  cmp     dword ptr [rcx+1994h], 0
0x180076c63  jnz     short loc_180076C7E
0x180076c65  mov     rdx, rdi; wchar_t *
0x180076c68  call    ?SaveTemporaryAttachedFiles@CReport@@QEAAJPEB_W@Z; CReport::SaveTemporaryAttachedFiles(wchar_t const *)
0x180076c6d  mov     ebx, eax
0x180076c6f  test    eax, eax
0x180076c71  jns     short loc_180076C7A
0x180076c73  mov     edx, 5C6h
0x180076c78  jmp     short loc_180076C0E
0x180076c7a  mov     rcx, [rbp+arg_10]; this
0x180076c7e  xor     r9d, r9d; unsigned int
0x180076c81  mov     rdx, [rbp+lpExistingFileName]; wchar_t *
0x180076c85  call    ?WriteReportToFile@CReport@@QEAAJPEB_WHK@Z; CReport::WriteReportToFile(wchar_t const *,int,ulong)
0x180076c8a  mov     ebx, eax
0x180076c8c  test    eax, eax
0x180076c8e  jns     short loc_180076C9A
0x180076c90  mov     edx, 5CAh
0x180076c95  jmp     loc_180076C0E
0x180076c9a  mov     r8d, 1; dwFlags
0x180076ca0  mov     rdx, [rbp+lpNewFileName]; lpNewFileName
0x180076ca4  mov     rcx, [rbp+lpExistingFileName]; lpExistingFileName
0x180076ca8  call    cs:__imp_MoveFileExW
0x180076cae  test    eax, eax
0x180076cb0  jnz     short loc_180076D10
0x180076cb2  call    cs:__imp_GetLastError
0x180076cb8  mov     ebx, eax
0x180076cba  mov     rcx, [rbp+arg_10]
0x180076cbe  mov     dword ptr [rcx+19E0h], 0Fh
0x180076cc8  mov     rcx, [rbp+lpExistingFileName]; wchar_t *
0x180076ccc  call    ?UtilDeleteFilePath@@YAJPEB_W@Z; UtilDeleteFilePath(wchar_t const *)
0x180076cd1  mov     rcx, [rbp+18h]; this
0x180076cd5  test    eax, eax
0x180076cd7  jns     short loc_180076CED
0x180076cd9  mov     r9d, eax; char *
0x180076cdc  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x180076ce3  mov     edx, 5D1h; void *
0x180076ce8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180076ced  test    ebx, ebx
0x180076cef  jz      short loc_180076D10
0x180076cf1  mov     rcx, [rbp+18h]; this
0x180076cf5  mov     r9d, ebx; char *
0x180076cf8  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x180076cff  mov     edx, 5D3h; void *
0x180076d04  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180076d09  mov     ebx, eax
0x180076d0b  jmp     loc_180076C22
0x180076d10  lea     rcx, [rbp+var_58]
0x180076d14  call    tlx___UndoSolo__lambda_d550510c0ea602fc073c13b7512821bf_______UndoSolo__lambda_d550510c0ea602fc073c13b7512821bf___
0x180076d19  nop
0x180076d1a  lea     rcx, [rbp+lpNewFileName]; void *
0x180076d1e  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180076d23  nop
0x180076d24  lea     rcx, [rbp+lpExistingFileName]; void *
0x180076d28  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180076d2d  xor     ebx, ebx
0x180076d2f  lea     rcx, [rbp+var_60]
0x180076d33  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180076d38  jmp     short loc_180076D57
0x180076d3a  mov     rcx, [rbp+18h]; this
0x180076d3e  mov     ebx, 80070057h
0x180076d43  mov     r9d, ebx; char *
0x180076d46  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x180076d4d  mov     edx, 5A1h; void *
0x180076d52  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076d57  mov     eax, ebx
0x180076d59  mov     rbx, [rsp+80h+arg_0]
0x180076d61  add     rsp, 80h
0x180076d68  pop     rdi
0x180076d69  pop     rsi
0x180076d6a  pop     rbp
0x180076d6b  retn
```
