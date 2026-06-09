# CReportQueue::GetPathToZipFileOfReport(CReport *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x180076528`
- end: `0x180076705`
- name: `?GetPathToZipFileOfReport@CReportQueue@@QEAAJPEAVCReport@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `477`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x18003afa0`

## callees

- `0x18000bc10`
- `0x18000cc74`
- `0x18000dad0`
- `0x18000ea64`
- `0x18003db78`
- `0x18003e864`
- `0x180045bdc`
- `0x18004bc2c`
- `0x18004ee10`
- `0x180076528`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18007663d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180076682`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18007663d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180076682`

## string_xrefs

- `0x18007654c`: `onecore\windows\feedback\core\werdll\lib\reportqueue.cpp`
- `0x180076590`: `onecore\windows\feedback\core\werdll\lib\reportqueue.cpp`
- `0x180076615`: `onecore\windows\feedback\core\werdll\lib\reportqueue.cpp`
- `0x180076668`: `onecore\windows\feedback\core\werdll\lib\reportqueue.cpp`
- `0x180076694`: `onecore\windows\feedback\core\werdll\lib\reportqueue.cpp`
- `0x1800766d8`: `onecore\windows\feedback\core\werdll\lib\reportqueue.cpp`

## pseudocode

```c
__int64 __fastcall CReportQueue::GetPathToZipFileOfReport(wchar_t *a1, CReport *a2, __int64 a3)
{
  __int64 v5; // rdx
  unsigned int v6; // ebx
  int UniqueIdentifier; // eax
  wchar_t *v8; // rbx
  int v9; // eax
  unsigned int v10; // edi
  int v11; // eax
  LPCWSTR pszPath[4]; // [rsp+20h] [rbp-48h] BYREF
  _QWORD v14[5]; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+20h]
  wchar_t *v16; // [rsp+90h] [rbp+28h] BYREF

  v16 = a1;
  if ( a2 )
  {
    if ( !a3 )
    {
      v5 = 235;
      goto LABEL_3;
    }
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v14);
    UniqueIdentifier = CReport::GetUniqueIdentifier(a2, v14);
    v6 = UniqueIdentifier;
    if ( UniqueIdentifier < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF1,
        (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportqueue.cpp",
        (const char *)(unsigned int)UniqueIdentifier,
        (int)pszPath[0]);
LABEL_22:
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v14);
      return v6;
    }
    v16 = 0;
    if ( ((int)CReport::GetStorePath(a2, (const wchar_t **)&v16) < 0 || (v8 = v16) == 0)
      && ((int)CReport::GetReservedStorePath(a2, (const wchar_t **)&v16) < 0 || (v8 = v16) == 0) )
    {
      v6 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xFA,
             (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportqueue.cpp",
             (const char *)3,
             (unsigned int)pszPath[0]);
      goto LABEL_22;
    }
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(pszPath);
    v9 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
           pszPath,
           L"%s\\%s.zip",
           v8,
           v14[0]);
    v10 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xFF,
        (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportqueue.cpp",
        (const char *)(unsigned int)v9,
        (int)pszPath[0]);
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(pszPath);
      v6 = v10;
      goto LABEL_22;
    }
    if ( !PathFileExistsW(pszPath[0]) )
    {
      v11 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
              pszPath,
              L"%s\\%s.cab",
              v8,
              v14[0]);
      v6 = v11;
      if ( v11 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x103,
          (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportqueue.cpp",
          (const char *)(unsigned int)v11,
          (int)pszPath[0]);
LABEL_19:
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(pszPath);
        goto LABEL_22;
      }
      if ( !PathFileExistsW(pszPath[0]) )
      {
        v6 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x107,
               (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportqueue.cpp",
               (const char *)2,
               (unsigned int)pszPath[0]);
        goto LABEL_19;
      }
    }
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(a3, pszPath);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(pszPath);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v14);
    return 0;
  }
  v5 = 234;
LABEL_3:
  v6 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportqueue.cpp",
    (const char *)0x80070057LL,
    (int)pszPath[0]);
  return v6;
}

```

## disassembly

```asm
0x180076528  mov     [rsp-20h+arg_0], rcx
0x18007652d  push    rbp
0x18007652e  push    rbx
0x18007652f  push    rsi
0x180076530  push    rdi
0x180076531  mov     rbp, rsp
0x180076534  sub     rsp, 68h
0x180076538  mov     rsi, r8
0x18007653b  mov     rdi, rdx
0x18007653e  test    rdx, rdx
0x180076541  jnz     short loc_180076565
0x180076543  mov     edx, 0EAh; void *
0x180076548  mov     rcx, [rbp+20h]; this
0x18007654c  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werdl"...
0x180076553  mov     ebx, 80070057h
0x180076558  mov     r9d, ebx; char *
0x18007655b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076560  jmp     loc_1800766FA
0x180076565  test    rsi, rsi
0x180076568  jnz     short loc_180076571
0x18007656a  mov     edx, 0EBh
0x18007656f  jmp     short loc_180076548
0x180076571  lea     rcx, [rbp+var_28]; void *
0x180076575  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18007657a  lea     rdx, [rbp+var_28]
0x18007657e  mov     rcx, rdi
0x180076581  call    ?GetUniqueIdentifier@CReport@@QEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReport::GetUniqueIdentifier(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180076586  mov     ebx, eax
0x180076588  test    eax, eax
0x18007658a  jns     short loc_1800765A9
0x18007658c  mov     rcx, [rbp+20h]; this
0x180076590  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werdl"...
0x180076597  mov     r9d, eax; char *
0x18007659a  mov     edx, 0F1h; void *
0x18007659f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800765a4  jmp     loc_1800766F1
0x1800765a9  lea     rdx, [rbp+arg_0]; wchar_t **
0x1800765ad  mov     [rbp+arg_0], 0
0x1800765b5  mov     rcx, rdi; this
0x1800765b8  call    ?GetStorePath@CReport@@QEAAJPEAPEB_W@Z; CReport::GetStorePath(wchar_t const * *)
0x1800765bd  test    eax, eax
0x1800765bf  js      short loc_1800765CA
0x1800765c1  mov     rbx, [rbp+arg_0]
0x1800765c5  test    rbx, rbx
0x1800765c8  jnz     short loc_1800765EB
0x1800765ca  lea     rdx, [rbp+arg_0]; wchar_t **
0x1800765ce  mov     rcx, rdi; this
0x1800765d1  call    ?GetReservedStorePath@CReport@@QEAAJPEAPEB_W@Z; CReport::GetReservedStorePath(wchar_t const * *)
0x1800765d6  test    eax, eax
0x1800765d8  js      loc_1800766D4
0x1800765de  mov     rbx, [rbp+arg_0]
0x1800765e2  test    rbx, rbx
0x1800765e5  jz      loc_1800766D4
0x1800765eb  lea     rcx, [rbp+pszPath]; void *
0x1800765ef  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800765f4  mov     r9, [rbp+var_28]
0x1800765f8  lea     rdx, aSSZip; "%s\\%s.zip"
0x1800765ff  mov     r8, rbx
0x180076602  lea     rcx, [rbp+pszPath]
0x180076606  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18007660b  mov     edi, eax
0x18007660d  test    eax, eax
0x18007660f  jns     short loc_180076639
0x180076611  mov     rcx, [rbp+20h]; this
0x180076615  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werdl"...
0x18007661c  mov     r9d, eax; char *
0x18007661f  mov     edx, 0FFh; void *
0x180076624  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076629  lea     rcx, [rbp+pszPath]; void *
0x18007662d  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180076632  mov     ebx, edi
0x180076634  jmp     loc_1800766F1
0x180076639  mov     rcx, [rbp+pszPath]; pszPath
0x18007663d  call    cs:__imp_PathFileExistsW
0x180076643  test    eax, eax
0x180076645  jnz     short loc_1800766B2
0x180076647  mov     r9, [rbp+var_28]
0x18007664b  lea     rdx, aSSCab_0; "%s\\%s.cab"
0x180076652  mov     r8, rbx
0x180076655  lea     rcx, [rbp+pszPath]
0x180076659  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18007665e  mov     ebx, eax
0x180076660  test    eax, eax
0x180076662  jns     short loc_18007667E
0x180076664  mov     rcx, [rbp+20h]; this
0x180076668  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werdl"...
0x18007666f  mov     r9d, eax; char *
0x180076672  mov     edx, 103h; void *
0x180076677  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007667c  jmp     short loc_1800766A7
0x18007667e  mov     rcx, [rbp+pszPath]; pszPath
0x180076682  call    cs:__imp_PathFileExistsW
0x180076688  test    eax, eax
0x18007668a  jnz     short loc_1800766B2
0x18007668c  mov     rcx, [rbp+20h]; this
0x180076690  lea     r9d, [rax+2]; char *
0x180076694  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werdl"...
0x18007669b  mov     edx, 107h; void *
0x1800766a0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800766a5  mov     ebx, eax
0x1800766a7  lea     rcx, [rbp+pszPath]; void *
0x1800766ab  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800766b0  jmp     short loc_1800766F1
0x1800766b2  lea     rdx, [rbp+pszPath]
0x1800766b6  mov     rcx, rsi
0x1800766b9  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x1800766be  lea     rcx, [rbp+pszPath]; void *
0x1800766c2  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800766c7  lea     rcx, [rbp+var_28]; void *
0x1800766cb  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800766d0  xor     eax, eax
0x1800766d2  jmp     short loc_1800766FC
0x1800766d4  mov     rcx, [rbp+20h]; this
0x1800766d8  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werdl"...
0x1800766df  mov     r9d, 3; char *
0x1800766e5  mov     edx, 0FAh; void *
0x1800766ea  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800766ef  mov     ebx, eax
0x1800766f1  lea     rcx, [rbp+var_28]; void *
0x1800766f5  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800766fa  mov     eax, ebx
0x1800766fc  add     rsp, 68h
0x180076700  pop     rdi
0x180076701  pop     rsi
0x180076702  pop     rbx
0x180076703  pop     rbp
0x180076704  retn
```
