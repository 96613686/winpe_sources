# DeleteCorruptedReportFromStore(wchar_t const *)

- ea: `0x1400058ec`
- end: `0x140005ce5`
- name: `?DeleteCorruptedReportFromStore@@YAJPEB_W@Z`
- size: `1017`
- prototype: `__int64 __fastcall(const wchar_t *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x140005f98`

## callees

- `0x140003224`
- `0x1400045bc`
- `0x1400047bc`
- `0x1400048f0`
- `0x1400058ec`
- `0x140008c40`
- `0x140008c88`
- `0x14000be08`
- `0x140018e8c`
- `0x1400192b0`
- `0x14001a8bc`
- `0x14001c4a8`

## string_xrefs

- `0x1400059ad`: `Failed to build the path to Report.wer`
- `0x1400059be`: `DeleteCorruptedReportFromStore`
- `0x140005a6b`: `DeleteCorruptedReportFromStore`
- `0x140005ae3`: `DeleteCorruptedReportFromStore`
- `0x140005b5b`: `DeleteCorruptedReportFromStore`
- `0x140005b9f`: `DeleteCorruptedReportFromStore`
- `0x140005c49`: `DeleteCorruptedReportFromStore`
- `0x1400059fa`: `Parser ReadFromFile failed (path=%ws)`
- `0x140005b8f`: `Could not read report size from disk`
- `0x140005c33`: `Unable to delete report folder (path=%ws)`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall DeleteCorruptedReportFromStore(wchar_t *a1)
{
  unsigned int v2; // r8d
  int v3; // r14d
  const char *v4; // rax
  __int64 v5; // rdx
  int DirectorySizeRecursive; // eax
  const struct _tlgProvider_t *v7; // rcx
  unsigned __int64 v8; // r14
  const wchar_t *v9; // rdx
  __int64 v10; // rax
  unsigned __int64 v11; // rax
  __int64 v12; // r8
  int v13; // edx
  const wchar_t *v14; // r8
  const wchar_t *v15; // r9
  wil::details *v17; // [rsp+20h] [rbp-E0h]
  wil::details *v18; // [rsp+20h] [rbp-E0h]
  wil::details *v19; // [rsp+20h] [rbp-E0h]
  wil::details *v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+20h] [rbp-E0h]
  int v22; // [rsp+28h] [rbp-D8h]
  wchar_t *v23; // [rsp+30h] [rbp-D0h]
  wchar_t *v24; // [rsp+30h] [rbp-D0h]
  wchar_t *v25; // [rsp+30h] [rbp-D0h]
  wchar_t *v26; // [rsp+30h] [rbp-D0h]
  wchar_t *v27; // [rsp+30h] [rbp-D0h]
  wchar_t **v28; // [rsp+40h] [rbp-C0h] BYREF
  char v29; // [rsp+48h] [rbp-B8h]
  int v30; // [rsp+49h] [rbp-B7h]
  __int16 v31; // [rsp+4Dh] [rbp-B3h]
  char v32; // [rsp+4Fh] [rbp-B1h]
  _QWORD *v33; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *v34; // [rsp+58h] [rbp-A8h]
  wchar_t *v35[2]; // [rsp+60h] [rbp-A0h] BYREF
  _WORD v36[8]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t *v37[2]; // [rsp+80h] [rbp-80h] BYREF
  _WORD v38[8]; // [rsp+90h] [rbp-70h] BYREF
  wchar_t *v39[2]; // [rsp+A0h] [rbp-60h] BYREF
  _WORD v40[8]; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t *v41[2]; // [rsp+C0h] [rbp-40h] BYREF
  _WORD v42[8]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v43[3]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v44[9]; // [rsp+F8h] [rbp-8h] BYREF
  wil::details::in1diag4 *retaddr; // [rsp+148h] [rbp+48h]
  unsigned __int64 v46; // [rsp+158h] [rbp+58h] BYREF

  v41[0] = v42;
  v41[1] = v42;
  v42[0] = 0;
  v39[0] = v40;
  v39[1] = v40;
  v40[0] = 0;
  v37[0] = v38;
  v37[1] = v38;
  v38[0] = 0;
  v35[0] = v36;
  v35[1] = v36;
  v36[0] = 0;
  v43[0] = v43;
  v43[1] = v43;
  v43[2] = 0;
  v44[0] = v44;
  v44[1] = v44;
  v44[2] = v44;
  v44[3] = 0;
  v46 = 0;
  v3 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v35, L"%ls\\Report.wer", a1);
  if ( v3 < 0 )
  {
    LODWORD(v17) = v3;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x365,
      (unsigned int)"onecore\\windows\\feedback\\core\\wermgr\\lib\\wermgr.cpp",
      "DeleteCorruptedReportFromStore",
      v17,
      (int)"Failed to build the path to Report.wer",
      (const char *)v23);
    goto LABEL_19;
  }
  v3 = CIniParser::ReadFromFile((CIniParser *)v43, v35[0], v2);
  if ( v3 < 0 )
  {
    v24 = v35[0];
    v4 = "Parser ReadFromFile failed (path=%ws)";
    v5 = 876;
LABEL_18:
    LODWORD(v17) = v3;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\windows\\feedback\\core\\wermgr\\lib\\wermgr.cpp",
      "DeleteCorruptedReportFromStore",
      v17,
      (int)v4,
      (const char *)v24);
    goto LABEL_19;
  }
  v28 = v41;
  v29 = 0;
  v33 = v43;
  v34 = L"EventType";
  LODWORD(v17) = utl::visit__lambda_74b528fc722e3374e92520241ac7e7d4__utl::variant_utl::basic_string_wchar_t_utl::char_traits_wchar_t__utl::allocator_wchar_t______unsigned_long___unsigned___int64___utl::vector_unsigned_char_utl::allocator_unsigned_char______utl::basic_string_view_wchar_t_utl::char_traits_wchar_t____const___utl::span_unsigned_char_const___1__const______long_(
                   &v33,
                   &v28);
  wil::details::in1diag4::Log_IfFailedMsg(
    retaddr,
    (void *)0x371,
    (unsigned int)"onecore\\windows\\feedback\\core\\wermgr\\lib\\wermgr.cpp",
    "DeleteCorruptedReportFromStore",
    (const char *)v17,
    (int)"Unable to get event name",
    (const char *)v23);
  v28 = v39;
  v29 = 0;
  v30 = *(_DWORD *)((char *)&v34 + 1);
  v31 = *(_WORD *)((char *)&v34 + 5);
  v32 = HIBYTE(v34);
  v33 = v43;
  v34 = L"ReportIdentifier";
  LODWORD(v18) = utl::visit__lambda_74b528fc722e3374e92520241ac7e7d4__utl::variant_utl::basic_string_wchar_t_utl::char_traits_wchar_t__utl::allocator_wchar_t______unsigned_long___unsigned___int64___utl::vector_unsigned_char_utl::allocator_unsigned_char______utl::basic_string_view_wchar_t_utl::char_traits_wchar_t____const___utl::span_unsigned_char_const___1__const______long_(
                   &v33,
                   &v28);
  wil::details::in1diag4::Log_IfFailedMsg(
    retaddr,
    (void *)0x374,
    (unsigned int)"onecore\\windows\\feedback\\core\\wermgr\\lib\\wermgr.cpp",
    "DeleteCorruptedReportFromStore",
    (const char *)v18,
    (int)"Unable to get Report Id",
    (const char *)v25);
  v28 = v37;
  v29 = 0;
  v30 = *(_DWORD *)((char *)&v34 + 1);
  v31 = *(_WORD *)((char *)&v34 + 5);
  v32 = HIBYTE(v34);
  v33 = v43;
  v34 = L"IntegratorReportIdentifier";
  LODWORD(v19) = utl::visit__lambda_74b528fc722e3374e92520241ac7e7d4__utl::variant_utl::basic_string_wchar_t_utl::char_traits_wchar_t__utl::allocator_wchar_t______unsigned_long___unsigned___int64___utl::vector_unsigned_char_utl::allocator_unsigned_char______utl::basic_string_view_wchar_t_utl::char_traits_wchar_t____const___utl::span_unsigned_char_const___1__const______long_(
                   &v33,
                   &v28);
  wil::details::in1diag4::Log_IfFailedMsg(
    retaddr,
    (void *)0x377,
    (unsigned int)"onecore\\windows\\feedback\\core\\wermgr\\lib\\wermgr.cpp",
    "DeleteCorruptedReportFromStore",
    (const char *)v19,
    (int)"Unable to get Report Integrator Id",
    (const char *)v26);
  DirectorySizeRecursive = CPath::GetDirectorySizeRecursive(a1, 0, &v46, 0);
  if ( DirectorySizeRecursive >= 0 )
  {
    v8 = v46;
  }
  else
  {
    v8 = 0;
    LODWORD(v20) = DirectorySizeRecursive;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x37D,
      (unsigned int)"onecore\\windows\\feedback\\core\\wermgr\\lib\\wermgr.cpp",
      "DeleteCorruptedReportFromStore",
      v20,
      (int)"Could not read report size from disk",
      (const char *)v27);
  }
  if ( a1 )
  {
    v10 = -1;
    do
      ++v10;
    while ( a1[v10] );
    v7 = (const struct _tlgProvider_t *)&a1[v10];
    while ( 1 )
    {
      v9 = (const wchar_t *)v7;
      if ( v7 <= (const struct _tlgProvider_t *)a1 )
        break;
      v7 = (const struct _tlgProvider_t *)((char *)v7 - 2);
      v11 = *(unsigned __int16 *)v7;
      LOWORD(v11) = v11 - 47;
      if ( (unsigned __int16)v11 <= 0x2Du )
      {
        v12 = 0x200000000801LL;
        if ( _bittest64(&v12, v11) )
          break;
      }
    }
  }
  else
  {
    v9 = 0;
  }
  UtilFireWerReportPrunedEvent(v7, v41[0], v39[0], v37[0], (int)v20, v22, v9, v8);
  v3 = UtilRecursiveRemoveDirectory(a1, v13, v14, v15, v21);
  if ( v3 < 0 )
  {
    v24 = a1;
    v4 = "Unable to delete report folder (path=%ws)";
    v5 = 910;
    goto LABEL_18;
  }
LABEL_19:
  utl::_Tree<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::pair<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const,utl::_DlistIt<utl::_DlistNode<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const,utl::_DlistIt<utl::_DlistNode<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>>>,0>::~_Tree<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::pair<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const,utl::_DlistIt<utl::_DlistNode<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const,utl::_DlistIt<utl::_DlistNode<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>>>,0>(v44);
  utl::list<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>>::~list<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>>(v43);
  if ( v35[0] != v36 )
    operator delete(v35[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v37[0] != v38 )
    operator delete(v37[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v39[0] != v40 )
    operator delete(v39[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v41[0] != v42 )
    operator delete(v41[0], (const struct std::nothrow_t *)&std::nothrow);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1400058ec  push    rbp
0x1400058ee  push    rbx
0x1400058ef  push    r14
0x1400058f1  push    r15
0x1400058f3  lea     rbp, [rsp-28h]
0x1400058f8  sub     rsp, 128h
0x1400058ff  mov     rbx, rcx
0x140005902  lea     rax, [rbp+40h+var_70]
0x140005906  mov     [rbp+40h+var_80], rax
0x14000590a  lea     rax, [rbp+40h+var_70]
0x14000590e  mov     [rbp+40h+var_78], rax
0x140005912  xor     r15d, r15d
0x140005915  mov     [rbp+40h+var_70], r15w
0x14000591a  lea     rax, [rbp+40h+var_90]
0x14000591e  mov     [rbp+40h+var_A0], rax
0x140005922  lea     rax, [rbp+40h+var_90]
0x140005926  mov     [rbp+40h+var_98], rax
0x14000592a  mov     [rbp+40h+var_90], r15w
0x14000592f  lea     rax, [rbp+40h+var_B0]
0x140005933  mov     [rbp+40h+var_C0], rax
0x140005937  lea     rax, [rbp+40h+var_B0]
0x14000593b  mov     [rbp+40h+var_B8], rax
0x14000593f  mov     [rbp+40h+var_B0], r15w
0x140005944  lea     rax, [rsp+140h+var_D0]
0x140005949  mov     [rsp+140h+var_E0], rax
0x14000594e  lea     rax, [rsp+140h+var_D0]
0x140005953  mov     [rsp+140h+var_D8], rax
0x140005958  mov     [rsp+140h+var_D0], r15w
0x14000595e  lea     rax, [rbp+40h+var_60]
0x140005962  mov     [rbp+40h+var_60], rax
0x140005966  lea     rax, [rbp+40h+var_60]
0x14000596a  mov     [rbp+40h+var_58], rax
0x14000596e  mov     [rbp+40h+var_50], r15
0x140005972  lea     rax, [rbp+40h+var_48]
0x140005976  mov     [rbp+40h+var_48], rax
0x14000597a  lea     rax, [rbp+40h+var_48]
0x14000597e  mov     [rbp+40h+var_40], rax
0x140005982  mov     [rbp+40h+var_38], rax
0x140005986  mov     [rbp+40h+var_30], r15
0x14000598a  mov     [rbp+40h+arg_8], r15
0x14000598e  mov     r8, rcx
0x140005991  lea     rdx, aLsReportWer; "%ls\\Report.wer"
0x140005998  lea     rcx, [rsp+140h+var_E0]
0x14000599d  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x1400059a2  mov     r14d, eax
0x1400059a5  test    eax, eax
0x1400059a7  jns     short loc_1400059DB
0x1400059a9  mov     rcx, [rbp+48h]; this
0x1400059ad  lea     rax, aFailedToBuildT; "Failed to build the path to Report.wer"
0x1400059b4  mov     qword ptr [rsp+140h+var_118], rax; int
0x1400059b9  mov     dword ptr [rsp+140h+var_120], r14d; wil::details *
0x1400059be  lea     r9, aDeletecorrupte; "DeleteCorruptedReportFromStore"
0x1400059c5  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\wermg"...
0x1400059cc  mov     edx, 365h; void *
0x1400059d1  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x1400059d6  jmp     loc_140005C61
0x1400059db  mov     rdx, [rsp+140h+var_E0]; wchar_t *
0x1400059e0  lea     rcx, [rbp+40h+var_60]; this
0x1400059e4  call    ?ReadFromFile@CIniParser@@QEAAJPEB_WH@Z; CIniParser::ReadFromFile(wchar_t const *,int)
0x1400059e9  mov     r14d, eax
0x1400059ec  test    eax, eax
0x1400059ee  jns     short loc_140005A0B
0x1400059f0  mov     rdx, [rsp+140h+var_E0]
0x1400059f5  mov     [rsp+140h+var_110], rdx
0x1400059fa  lea     rax, aParserReadfrom; "Parser ReadFromFile failed (path=%ws)"
0x140005a01  mov     edx, 36Ch
0x140005a06  jmp     loc_140005C3F
0x140005a0b  lea     rax, [rbp+40h+var_80]
0x140005a0f  mov     [rsp+140h+var_100], rax
0x140005a14  mov     [rsp+140h+var_F8], r15b
0x140005a19  mov     eax, [rsp+140h+var_F7]
0x140005a1d  mov     [rsp+140h+var_F7], eax
0x140005a21  movzx   eax, [rsp+140h+var_F3]
0x140005a26  mov     [rsp+140h+var_F3], ax
0x140005a2b  mov     al, [rsp+140h+var_F1]
0x140005a2f  mov     [rsp+140h+var_F1], al
0x140005a33  lea     rax, [rbp+40h+var_60]
0x140005a37  mov     [rsp+140h+var_F0], rax
0x140005a3c  lea     rax, aEventtype; "EventType"
0x140005a43  mov     [rsp+140h+var_E8], rax
0x140005a48  lea     rdx, [rsp+140h+var_100]
0x140005a4d  lea     rcx, [rsp+140h+var_F0]
0x140005a52  call    utl__visit__lambda_74b528fc722e3374e92520241ac7e7d4__utl__variant_utl__basic_string_wchar_t_utl__char_traits_wchar_t__utl__allocator_wchar_t______unsigned_long___unsigned___int64___utl__vector_unsigned_char_utl__allocator_unsigned_char______utl__basic_string_view_wchar_t_utl__char_traits_wchar_t____const___utl__span_unsigned_char_const___1__const______long_
0x140005a57  mov     rcx, [rbp+48h]; this
0x140005a5b  lea     rdx, aUnableToGetEve; "Unable to get event name"
0x140005a62  mov     qword ptr [rsp+140h+var_118], rdx; int
0x140005a67  mov     dword ptr [rsp+140h+var_120], eax; char *
0x140005a6b  lea     r9, aDeletecorrupte; "DeleteCorruptedReportFromStore"
0x140005a72  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\wermg"...
0x140005a79  mov     edx, 371h; void *
0x140005a7e  call    ?Log_IfFailedMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_IfFailedMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140005a83  lea     rax, [rbp+40h+var_A0]
0x140005a87  mov     [rsp+140h+var_100], rax
0x140005a8c  mov     [rsp+140h+var_F8], r15b
0x140005a91  mov     eax, dword ptr [rsp+140h+var_E8+1]
0x140005a95  mov     [rsp+140h+var_F7], eax
0x140005a99  movzx   eax, word ptr [rsp+140h+var_E8+5]
0x140005a9e  mov     [rsp+140h+var_F3], ax
0x140005aa3  mov     al, byte ptr [rsp+140h+var_E8+7]
0x140005aa7  mov     [rsp+140h+var_F1], al
0x140005aab  lea     rax, [rbp+40h+var_60]
0x140005aaf  mov     [rsp+140h+var_F0], rax
0x140005ab4  lea     rax, aReportidentifi; "ReportIdentifier"
0x140005abb  mov     [rsp+140h+var_E8], rax
0x140005ac0  lea     rdx, [rsp+140h+var_100]
0x140005ac5  lea     rcx, [rsp+140h+var_F0]
0x140005aca  call    utl__visit__lambda_74b528fc722e3374e92520241ac7e7d4__utl__variant_utl__basic_string_wchar_t_utl__char_traits_wchar_t__utl__allocator_wchar_t______unsigned_long___unsigned___int64___utl__vector_unsigned_char_utl__allocator_unsigned_char______utl__basic_string_view_wchar_t_utl__char_traits_wchar_t____const___utl__span_unsigned_char_const___1__const______long_
0x140005acf  mov     rcx, [rbp+48h]; this
0x140005ad3  lea     rdx, aUnableToGetRep_0; "Unable to get Report Id"
0x140005ada  mov     qword ptr [rsp+140h+var_118], rdx; int
0x140005adf  mov     dword ptr [rsp+140h+var_120], eax; char *
0x140005ae3  lea     r9, aDeletecorrupte; "DeleteCorruptedReportFromStore"
0x140005aea  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\wermg"...
0x140005af1  mov     edx, 374h; void *
0x140005af6  call    ?Log_IfFailedMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_IfFailedMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140005afb  lea     rax, [rbp+40h+var_C0]
0x140005aff  mov     [rsp+140h+var_100], rax
0x140005b04  mov     [rsp+140h+var_F8], r15b
0x140005b09  mov     eax, dword ptr [rsp+140h+var_E8+1]
0x140005b0d  mov     [rsp+140h+var_F7], eax
0x140005b11  movzx   eax, word ptr [rsp+140h+var_E8+5]
0x140005b16  mov     [rsp+140h+var_F3], ax
0x140005b1b  mov     al, byte ptr [rsp+140h+var_E8+7]
0x140005b1f  mov     [rsp+140h+var_F1], al
0x140005b23  lea     rax, [rbp+40h+var_60]
0x140005b27  mov     [rsp+140h+var_F0], rax
0x140005b2c  lea     rax, aIntegratorrepo; "IntegratorReportIdentifier"
0x140005b33  mov     [rsp+140h+var_E8], rax
0x140005b38  lea     rdx, [rsp+140h+var_100]
0x140005b3d  lea     rcx, [rsp+140h+var_F0]
0x140005b42  call    utl__visit__lambda_74b528fc722e3374e92520241ac7e7d4__utl__variant_utl__basic_string_wchar_t_utl__char_traits_wchar_t__utl__allocator_wchar_t______unsigned_long___unsigned___int64___utl__vector_unsigned_char_utl__allocator_unsigned_char______utl__basic_string_view_wchar_t_utl__char_traits_wchar_t____const___utl__span_unsigned_char_const___1__const______long_
0x140005b47  mov     rcx, [rbp+48h]; this
0x140005b4b  lea     rdx, aUnableToGetRep; "Unable to get Report Integrator Id"
0x140005b52  mov     qword ptr [rsp+140h+var_118], rdx; int
0x140005b57  mov     dword ptr [rsp+140h+var_120], eax; char *
0x140005b5b  lea     r9, aDeletecorrupte; "DeleteCorruptedReportFromStore"
0x140005b62  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\wermg"...
0x140005b69  mov     edx, 377h; void *
0x140005b6e  call    ?Log_IfFailedMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_IfFailedMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140005b73  xor     r9d, r9d; unsigned int *
0x140005b76  lea     r8, [rbp+40h+arg_8]; unsigned __int64 *
0x140005b7a  xor     edx, edx; unsigned int
0x140005b7c  mov     rcx, rbx; wchar_t *
0x140005b7f  call    ?GetDirectorySizeRecursive@CPath@@SAJPEB_WKPEA_KPEAK@Z; CPath::GetDirectorySizeRecursive(wchar_t const *,ulong,unsigned __int64 *,ulong *)
0x140005b84  test    eax, eax
0x140005b86  jns     short loc_140005BB9
0x140005b88  mov     r14, r15
0x140005b8b  mov     rcx, [rbp+48h]; this
0x140005b8f  lea     rdx, aCouldNotReadRe; "Could not read report size from disk"
0x140005b96  mov     qword ptr [rsp+140h+var_118], rdx; int
0x140005b9b  mov     dword ptr [rsp+140h+var_120], eax; wil::details *
0x140005b9f  lea     r9, aDeletecorrupte; "DeleteCorruptedReportFromStore"
0x140005ba6  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\wermg"...
0x140005bad  mov     edx, 37Dh; void *
0x140005bb2  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140005bb7  jmp     short loc_140005BBD
0x140005bb9  mov     r14, [rbp+40h+arg_8]
0x140005bbd  test    rbx, rbx
0x140005bc0  jnz     short loc_140005BC7
0x140005bc2  mov     rdx, r15
0x140005bc5  jmp     short loc_140005C04
0x140005bc7  or      rax, 0FFFFFFFFFFFFFFFFh
0x140005bcb  inc     rax
0x140005bce  cmp     [rbx+rax*2], r15w
0x140005bd3  jnz     short loc_140005BCB
0x140005bd5  lea     rcx, [rbx+rax*2]
0x140005bd9  jmp     short loc_140005BFC
0x140005bdb  sub     rcx, 2; struct _tlgProvider_t *
0x140005bdf  movzx   eax, word ptr [rcx]
0x140005be2  sub     ax, 2Fh ; '/'
0x140005be6  cmp     ax, 2Dh ; '-'
0x140005bea  ja      short loc_140005BFC
0x140005bec  mov     r8, 200000000801h
0x140005bf6  bt      r8, rax
0x140005bfa  jb      short loc_140005C04
0x140005bfc  mov     rdx, rcx
0x140005bff  cmp     rcx, rbx
0x140005c02  ja      short loc_140005BDB
0x140005c04  mov     [rsp+140h+var_108], r14; unsigned __int64
0x140005c09  mov     [rsp+140h+var_110], rdx; wchar_t *
0x140005c0e  mov     r9, [rbp+40h+var_C0]; wchar_t *
0x140005c12  mov     r8, [rbp+40h+var_A0]; wchar_t *
0x140005c16  mov     rdx, [rbp+40h+var_80]; wchar_t *
0x140005c1a  call    ?UtilFireWerReportPrunedEvent@@YAXQEBU_tlgProvider_t@@QEB_W11HH1_K@Z; UtilFireWerReportPrunedEvent(_tlgProvider_t const * const,wchar_t const * const,wchar_t const * const,wchar_t const * const,int,int,wchar_t const * const,unsigned __int64)
0x140005c1f  mov     rcx, rbx; wchar_t *
0x140005c22  call    ?UtilRecursiveRemoveDirectory@@YAJPEB_WH00H@Z; UtilRecursiveRemoveDirectory(wchar_t const *,int,wchar_t const *,wchar_t const *,int)
0x140005c27  mov     r14d, eax
0x140005c2a  test    eax, eax
0x140005c2c  jns     short loc_140005C61
0x140005c2e  mov     [rsp+140h+var_110], rbx; char *
0x140005c33  lea     rax, aUnableToDelete; "Unable to delete report folder (path=%w"...
0x140005c3a  mov     edx, 38Eh; void *
0x140005c3f  mov     qword ptr [rsp+140h+var_118], rax; int
0x140005c44  mov     dword ptr [rsp+140h+var_120], r14d; wil::details *
0x140005c49  lea     r9, aDeletecorrupte; "DeleteCorruptedReportFromStore"
0x140005c50  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\wermg"...
0x140005c57  mov     rcx, [rbp+48h]; this
0x140005c5b  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140005c60  nop
0x140005c61  lea     rcx, [rbp+40h+var_48]
0x140005c65  call    ??1?$_Tree@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@V?$_DlistIt@U?$_DlistNode@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@utl@@@utl@@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@2@@2@@2@Uistring_less_ordinal@tlx@@V?$allocator@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@V?$_DlistIt@U?$_DlistNode@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@utl@@@utl@@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@2@@2@@utl@@@2@$0A@@utl@@IEAA@XZ; utl::_Tree<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::pair<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const,utl::_DlistIt<utl::_DlistNode<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const,utl::_DlistIt<utl::_DlistNode<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>>>,0>::~_Tree<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::pair<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const,utl::_DlistIt<utl::_DlistNode<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>>,tlx::istring_less_ordinal,utl::allocator<utl::pair<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const,utl::_DlistIt<utl::_DlistNode<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>,utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>>>,0>(void)
0x140005c6a  lea     rcx, [rbp+40h+var_60]
0x140005c6e  call    ??1?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@utl@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@utl@@@2@@utl@@QEAA@XZ; utl::list<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>>::~list<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,utl::allocator<utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>>(void)
0x140005c73  nop
0x140005c74  lea     rax, [rsp+140h+var_D0]
0x140005c79  mov     rcx, [rsp+140h+var_E0]; void *
0x140005c7e  cmp     rcx, rax
0x140005c81  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x140005c88  jz      short loc_140005C93
0x140005c8a  mov     rdx, rbx; struct std::nothrow_t *
0x140005c8d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140005c92  nop
0x140005c93  lea     rax, [rbp+40h+var_B0]
0x140005c97  mov     rcx, [rbp+40h+var_C0]; void *
0x140005c9b  cmp     rcx, rax
0x140005c9e  jz      short loc_140005CA9
0x140005ca0  mov     rdx, rbx; struct std::nothrow_t *
0x140005ca3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140005ca8  nop
0x140005ca9  lea     rax, [rbp+40h+var_90]
0x140005cad  mov     rcx, [rbp+40h+var_A0]; void *
0x140005cb1  cmp     rcx, rax
0x140005cb4  jz      short loc_140005CBF
0x140005cb6  mov     rdx, rbx; struct std::nothrow_t *
0x140005cb9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140005cbe  nop
0x140005cbf  lea     rax, [rbp+40h+var_70]
0x140005cc3  mov     rcx, [rbp+40h+var_80]; void *
0x140005cc7  cmp     rcx, rax
0x140005cca  jz      short loc_140005CD4
0x140005ccc  mov     rdx, rbx; struct std::nothrow_t *
0x140005ccf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140005cd4  mov     eax, r14d
0x140005cd7  add     rsp, 128h
0x140005cde  pop     r15
0x140005ce0  pop     r14
0x140005ce2  pop     rbx
0x140005ce3  pop     rbp
0x140005ce4  retn
```
