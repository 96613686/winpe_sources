# CReportQueue::GetPathToZipFileOfReport(CReport *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x1800764d8`
- end: `0x1800766b5`
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
- `0x1800764d8`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800765ed`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180076632`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800765ed`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180076632`

## string_xrefs

- `0x1800764fc`: `onecore\windows\feedback\core\werdll\lib\reportqueue.cpp`
- `0x180076540`: `onecore\windows\feedback\core\werdll\lib\reportqueue.cpp`
- `0x1800765c5`: `onecore\windows\feedback\core\werdll\lib\reportqueue.cpp`
- `0x180076618`: `onecore\windows\feedback\core\werdll\lib\reportqueue.cpp`
- `0x180076644`: `onecore\windows\feedback\core\werdll\lib\reportqueue.cpp`
- `0x180076688`: `onecore\windows\feedback\core\werdll\lib\reportqueue.cpp`

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
0x1800764d8  mov     [rsp-20h+arg_0], rcx
0x1800764dd  push    rbp
0x1800764de  push    rbx
0x1800764df  push    rsi
0x1800764e0  push    rdi
0x1800764e1  mov     rbp, rsp
0x1800764e4  sub     rsp, 68h
0x1800764e8  mov     rsi, r8
0x1800764eb  mov     rdi, rdx
0x1800764ee  test    rdx, rdx
0x1800764f1  jnz     short loc_180076515
0x1800764f3  mov     edx, 0EAh; void *
0x1800764f8  mov     rcx, [rbp+20h]; this
0x1800764fc  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werdl"...
0x180076503  mov     ebx, 80070057h
0x180076508  mov     r9d, ebx; char *
0x18007650b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076510  jmp     loc_1800766AA
0x180076515  test    rsi, rsi
0x180076518  jnz     short loc_180076521
0x18007651a  mov     edx, 0EBh
0x18007651f  jmp     short loc_1800764F8
0x180076521  lea     rcx, [rbp+var_28]; void *
0x180076525  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18007652a  lea     rdx, [rbp+var_28]
0x18007652e  mov     rcx, rdi
0x180076531  call    ?GetUniqueIdentifier@CReport@@QEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReport::GetUniqueIdentifier(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180076536  mov     ebx, eax
0x180076538  test    eax, eax
0x18007653a  jns     short loc_180076559
0x18007653c  mov     rcx, [rbp+20h]; this
0x180076540  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werdl"...
0x180076547  mov     r9d, eax; char *
0x18007654a  mov     edx, 0F1h; void *
0x18007654f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076554  jmp     loc_1800766A1
0x180076559  lea     rdx, [rbp+arg_0]; wchar_t **
0x18007655d  mov     [rbp+arg_0], 0
0x180076565  mov     rcx, rdi; this
0x180076568  call    ?GetStorePath@CReport@@QEAAJPEAPEB_W@Z; CReport::GetStorePath(wchar_t const * *)
0x18007656d  test    eax, eax
0x18007656f  js      short loc_18007657A
0x180076571  mov     rbx, [rbp+arg_0]
0x180076575  test    rbx, rbx
0x180076578  jnz     short loc_18007659B
0x18007657a  lea     rdx, [rbp+arg_0]; wchar_t **
0x18007657e  mov     rcx, rdi; this
0x180076581  call    ?GetReservedStorePath@CReport@@QEAAJPEAPEB_W@Z; CReport::GetReservedStorePath(wchar_t const * *)
0x180076586  test    eax, eax
0x180076588  js      loc_180076684
0x18007658e  mov     rbx, [rbp+arg_0]
0x180076592  test    rbx, rbx
0x180076595  jz      loc_180076684
0x18007659b  lea     rcx, [rbp+pszPath]; void *
0x18007659f  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800765a4  mov     r9, [rbp+var_28]
0x1800765a8  lea     rdx, aSSZip; "%s\\%s.zip"
0x1800765af  mov     r8, rbx
0x1800765b2  lea     rcx, [rbp+pszPath]
0x1800765b6  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x1800765bb  mov     edi, eax
0x1800765bd  test    eax, eax
0x1800765bf  jns     short loc_1800765E9
0x1800765c1  mov     rcx, [rbp+20h]; this
0x1800765c5  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werdl"...
0x1800765cc  mov     r9d, eax; char *
0x1800765cf  mov     edx, 0FFh; void *
0x1800765d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800765d9  lea     rcx, [rbp+pszPath]; void *
0x1800765dd  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800765e2  mov     ebx, edi
0x1800765e4  jmp     loc_1800766A1
0x1800765e9  mov     rcx, [rbp+pszPath]; pszPath
0x1800765ed  call    cs:__imp_PathFileExistsW
0x1800765f3  test    eax, eax
0x1800765f5  jnz     short loc_180076662
0x1800765f7  mov     r9, [rbp+var_28]
0x1800765fb  lea     rdx, aSSCab_0; "%s\\%s.cab"
0x180076602  mov     r8, rbx
0x180076605  lea     rcx, [rbp+pszPath]
0x180076609  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18007660e  mov     ebx, eax
0x180076610  test    eax, eax
0x180076612  jns     short loc_18007662E
0x180076614  mov     rcx, [rbp+20h]; this
0x180076618  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werdl"...
0x18007661f  mov     r9d, eax; char *
0x180076622  mov     edx, 103h; void *
0x180076627  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007662c  jmp     short loc_180076657
0x18007662e  mov     rcx, [rbp+pszPath]; pszPath
0x180076632  call    cs:__imp_PathFileExistsW
0x180076638  test    eax, eax
0x18007663a  jnz     short loc_180076662
0x18007663c  mov     rcx, [rbp+20h]; this
0x180076640  lea     r9d, [rax+2]; char *
0x180076644  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werdl"...
0x18007664b  mov     edx, 107h; void *
0x180076650  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180076655  mov     ebx, eax
0x180076657  lea     rcx, [rbp+pszPath]; void *
0x18007665b  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180076660  jmp     short loc_1800766A1
0x180076662  lea     rdx, [rbp+pszPath]
0x180076666  mov     rcx, rsi
0x180076669  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x18007666e  lea     rcx, [rbp+pszPath]; void *
0x180076672  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180076677  lea     rcx, [rbp+var_28]; void *
0x18007667b  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180076680  xor     eax, eax
0x180076682  jmp     short loc_1800766AC
0x180076684  mov     rcx, [rbp+20h]; this
0x180076688  lea     r8, aOnecoreWindows_7; "onecore\\windows\\feedback\\core\\werdl"...
0x18007668f  mov     r9d, 3; char *
0x180076695  mov     edx, 0FAh; void *
0x18007669a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18007669f  mov     ebx, eax
0x1800766a1  lea     rcx, [rbp+var_28]; void *
0x1800766a5  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800766aa  mov     eax, ebx
0x1800766ac  add     rsp, 68h
0x1800766b0  pop     rdi
0x1800766b1  pop     rsi
0x1800766b2  pop     rbx
0x1800766b3  pop     rbp
0x1800766b4  retn
```
