# BingFilterDS::GetCandidates(IMtfSuggestionInputQuery *,IMtfSuggestionList * *)

- ea: `0x180009250`
- end: `0x1800097d5`
- name: `?GetCandidates@BingFilterDS@@UEAAJPEAUIMtfSuggestionInputQuery@@PEAPEAUIMtfSuggestionList@@@Z`
- size: `1413`
- prototype: `__int64 __fastcall(BingFilterDS *__hidden this, struct IMtfSuggestionInputQuery *, struct IMtfSuggestionList **)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180001da8`
- `0x180001fa8`
- `0x180008778`
- `0x180008e50`
- `0x18000904c`
- `0x18000919c`
- `0x180009250`
- `0x18000a05c`
- `0x18000a15c`
- `0x18000a180`
- `0x18000a43c`
- `0x18000ab00`
- `0x18000ac8c`
- `0x18000afa0`
- `0x18000c530`
- `0x18000e010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800096fe`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800096fe`

## string_xrefs

- `0x180009791`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
__int64 __fastcall BingFilterDS::GetCandidates(
        BingFilterDS *this,
        struct IMtfSuggestionInputQuery *a2,
        struct IMtfSuggestionList **a3)
{
  int Instance; // eax
  __int64 v7; // rax
  bool v8; // di
  BOOL v9; // eax
  _QWORD *v10; // rax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  void *v15; // rdx
  __int64 v16; // r8
  void **v17; // r8
  __int64 v18; // rcx
  int v19; // eax
  struct IMtfSuggestionList *v20; // rax
  unsigned int v21; // r8d
  const char *v22; // r9
  __int64 result; // rax
  __int64 v24; // [rsp+0h] [rbp-108h] BYREF
  int v25[2]; // [rsp+20h] [rbp-E8h]
  char v26; // [rsp+30h] [rbp-D8h] BYREF
  bool v27; // [rsp+31h] [rbp-D7h] BYREF
  __int64 v28; // [rsp+38h] [rbp-D0h] BYREF
  int v29; // [rsp+40h] [rbp-C8h] BYREF
  unsigned int v30[2]; // [rsp+48h] [rbp-C0h] BYREF
  unsigned int v31; // [rsp+50h] [rbp-B8h] BYREF
  struct IMtfSuggestionList *v32; // [rsp+58h] [rbp-B0h] BYREF
  unsigned int v33; // [rsp+60h] [rbp-A8h] BYREF
  int v34; // [rsp+64h] [rbp-A4h] BYREF
  __int64 v35; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v36; // [rsp+70h] [rbp-98h] BYREF
  void *Src; // [rsp+78h] [rbp-90h] BYREF
  __int128 v38; // [rsp+80h] [rbp-88h] BYREF
  __int128 v39; // [rsp+90h] [rbp-78h]
  _BYTE v40[16]; // [rsp+A0h] [rbp-68h] BYREF
  void *v41[2]; // [rsp+B0h] [rbp-58h] BYREF
  unsigned __int64 v42; // [rsp+C0h] [rbp-48h]
  unsigned __int64 v43; // [rsp+C8h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  *a3 = 0;
  v32 = 0;
  *(_QWORD *)v25 = &v32;
  try
  {
    Instance = Hooked_CoCreateInstance(
                 &CLSID_MtfSuggestionList,
                 0,
                 1u,
                 &GUID_7f445657_d12f_426f_a09d_f8df369d9a50,
                 *(void ***)v25);
    if ( Instance < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x153,
        (int)"mincore\\textinput\\dev\\mtf\\datasources\\bingfilterds\\lib\\bingfilterds.cpp",
        (const char *)(unsigned int)Instance,
        v25[0]);
    Src = 0;
    v33 = 0;
    (*(void (__fastcall **)(struct IMtfSuggestionInputQuery *, void **, unsigned int *))(*(_QWORD *)a2 + 64LL))(
      a2,
      &Src,
      &v33);
    v43 = 7;
    v42 = 0;
    LOWORD(v41[0]) = 0;
    if ( Src )
      std::wstring::assign(v41, (char *)Src, (unsigned __int64)v33 >> 1);
    GenerateFilterDisplayList(v40, v41, a2);
    v7 = *(_QWORD *)a2;
    v35 = 0;
    (*(void (__fastcall **)(struct IMtfSuggestionInputQuery *, __int64 *))(v7 + 48))(a2, &v35);
    LODWORD(v28) = 0;
    (*(void (__fastcall **)(__int64, __int64 *, __int64 *, __int64))(*(_QWORD *)v35 + 40LL))(
      v35,
      MTF_PROPBAG_KEY_BINGFILTERDS_FILTER_BY_READING_LENGTH,
      &v28,
      4);
    v27 = (_DWORD)v28 != 0;
    LODWORD(v28) = 0;
    (*(void (__fastcall **)(__int64, __int64 *, __int64 *, __int64))(*(_QWORD *)v35 + 40LL))(
      v35,
      MTF_PROPBAG_KEY_BINGFILTERDS_ALLOW_READING_MISMATCH,
      &v28,
      4);
    v8 = (_DWORD)v28 != 0;
    v34 = 0;
    (*(void (__fastcall **)(__int64, __int64 *, int *, __int64))(*(_QWORD *)v35 + 40LL))(
      v35,
      MTF_PROPBAG_KEY_BINGASDS_RUNTIME_DUPCOUNT,
      &v34,
      4);
    v36 = 0;
    v26 = 0;
    LODWORD(v28) = 0;
    v9 = (*(int (__fastcall **)(struct IMtfSuggestionInputQuery *, __int64 *))(*(_QWORD *)a2 + 96LL))(a2, &v28) >= 0
      && (_DWORD)v28
      && (v38 = 0,
          v39 = 0,
          (*(int (__fastcall **)(struct IMtfSuggestionInputQuery *, _QWORD, __int128 *))(*(_QWORD *)a2 + 104LL))(
            a2,
            0,
            &v38) >= 0)
      && *((_QWORD *)&v39 + 1)
      && (v30[0] = 0,
          (*(int (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)&v39 + 1) + 24LL))(*((_QWORD *)&v39 + 1), v30) >= 0)
      && v30[0] != 0;
    v31 = v9 + 1;
    *(_QWORD *)v30 = &v38;
    *((_QWORD *)&v39 + 1) = 0;
    v10 = operator new(0x50u);
    if ( !v10 )
      std::_Xbad_alloc();
    *v10 = off_18000FCF8;
    v10[1] = v40;
    v10[2] = &v31;
    v10[3] = v41;
    v10[4] = &v36;
    v10[5] = &v27;
    v10[6] = &v34;
    v10[7] = &v26;
    v10[8] = &v32;
    *((_QWORD *)&v39 + 1) = v10;
    ForEachFormerCandidate((__int64)a2, (__int64)&v38);
    v29 = 0;
    v11 = (*(__int64 (__fastcall **)(struct IMtfSuggestionList *, int *))(*(_QWORD *)v32 + 24LL))(v32, &v29);
    if ( v11 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1A5,
        (int)"mincore\\textinput\\dev\\mtf\\datasources\\bingfilterds\\lib\\bingfilterds.cpp",
        (const char *)(unsigned int)v11,
        v25[0]);
    if ( !v29 )
    {
      if ( v8 && v36 )
      {
        *(_QWORD *)v30 = 0;
        v12 = (**(__int64 (__fastcall ***)(__int64, GUID *, unsigned int *))v36)(
                v36,
                &GUID_c4445657_6908_45eb_a6b9_2f1ea4b2a03a,
                v30);
        if ( v12 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x1CBE,
            (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
            (const char *)(unsigned int)v12,
            v25[0]);
        UpdateNoLearnFlag(*(_QWORD *)v30);
        if ( *(_QWORD *)v30 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v30 + 16LL))(*(_QWORD *)v30);
        v13 = (*(__int64 (__fastcall **)(struct IMtfSuggestionList *, __int64))(*(_QWORD *)v32 + 48LL))(v32, v36);
        if ( v13 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x1AB,
            (int)"mincore\\textinput\\dev\\mtf\\datasources\\bingfilterds\\lib\\bingfilterds.cpp",
            (const char *)(unsigned int)v13,
            v25[0]);
        v31 = 6;
      }
      else if ( v26 )
      {
        v30[0] = 0;
        v14 = ULongLongToUInt(v42, v30);
        if ( v14 < 0 )
          wil::details::in1diag3::_FailFast_Hr(retaddr, v15, v16, (const char *)(unsigned int)v14, v25[0]);
        v17 = v41;
        if ( v43 >= 8 )
          v17 = (void **)v41[0];
        BingFilterDS::TryGetPreviousCandidateWithSameReading(this, &v28, v17, v30[0]);
        v18 = v28;
        if ( v28 )
        {
          v19 = (*(__int64 (__fastcall **)(struct IMtfSuggestionList *, __int64))(*(_QWORD *)v32 + 48LL))(v32, v28);
          if ( v19 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x1B8,
              (int)"mincore\\textinput\\dev\\mtf\\datasources\\bingfilterds\\lib\\bingfilterds.cpp",
              (const char *)(unsigned int)v19,
              v25[0]);
          v31 = 7;
          v18 = v28;
        }
        if ( v18 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      }
    }
    BingFilterDS::UpdateCandidateCache(this, v32);
    v20 = v32;
    v32 = 0;
    *a3 = v20;
    BingFilterDSTelemetry::FilterStatistics(v31);
    if ( v36 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    if ( v35 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v40);
    if ( v43 >= 8 )
      operator delete(v41[0]);
    v43 = 7;
    v42 = 0;
    LOWORD(v41[0]) = 0;
    if ( v32 )
      (*(void (__fastcall **)(struct IMtfSuggestionList *))(*(_QWORD *)v32 + 16LL))(v32);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, &v24, v21, v22);
  }
  return result;
}

```

## disassembly

```asm
0x180009250  push    rbx
0x180009252  push    rsi
0x180009253  push    rdi
0x180009254  push    r14
0x180009256  push    r15
0x180009258  sub     rsp, 0E0h
0x18000925f  mov     rax, cs:__security_cookie
0x180009266  xor     rax, rsp
0x180009269  mov     [rsp+108h+var_38], rax
0x180009271  mov     r14, r8
0x180009274  mov     rbx, rdx
0x180009277  mov     rsi, rcx
0x18000927a  xor     r15d, r15d
0x18000927d  mov     [r8], r15
0x180009280  mov     [rsp+108h+var_B0], r15
0x180009285  lea     rax, [rsp+108h+var_B0]
0x18000928a  mov     qword ptr [rsp+108h+var_E8], rax; int
0x18000928f  lea     r9, _GUID_7f445657_d12f_426f_a09d_f8df369d9a50
0x180009296  xor     edx, edx
0x180009298  lea     r8d, [r15+1]
0x18000929c  lea     rcx, CLSID_MtfSuggestionList
0x1800092a3  mov     rax, cs:?Hooked_CoCreateInstance@@3P6AJAEBU_GUID@@PEAUIUnknown@@K0PEAPEAX@ZEA; long (*Hooked_CoCreateInstance)(_GUID const &,IUnknown *,ulong,_GUID const &,void * *)
0x1800092aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092af  mov     rcx, [rsp+108h]; this
0x1800092b7  test    eax, eax
0x1800092b9  js      loc_18000975F
0x1800092bf  mov     [rsp+108h+Src], r15
0x1800092c4  mov     [rsp+108h+var_A8], r15d
0x1800092c9  mov     rax, [rbx]
0x1800092cc  lea     r8, [rsp+108h+var_A8]
0x1800092d1  lea     rdx, [rsp+108h+Src]
0x1800092d6  mov     rcx, rbx
0x1800092d9  mov     rax, [rax+40h]
0x1800092dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092e2  mov     [rsp+108h+var_40], 7
0x1800092ee  mov     [rsp+108h+var_48], r15
0x1800092f6  mov     word ptr [rsp+108h+var_58], r15w
0x1800092ff  mov     rdx, [rsp+108h+Src]; Src
0x180009304  test    rdx, rdx
0x180009307  jz      short loc_18000931E
0x180009309  mov     r8d, [rsp+108h+var_A8]
0x18000930e  shr     r8, 1
0x180009311  lea     rcx, [rsp+108h+var_58]; void *
0x180009319  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18000931e  mov     r8, rbx
0x180009321  lea     rdx, [rsp+108h+var_58]
0x180009329  lea     rcx, [rsp+108h+var_68]
0x180009331  call    GenerateFilterDisplayList
0x180009336  nop
0x180009337  mov     rax, [rbx]
0x18000933a  mov     [rsp+108h+var_A0], r15
0x18000933f  lea     rdx, [rsp+108h+var_A0]
0x180009344  mov     rcx, rbx
0x180009347  mov     rax, [rax+30h]
0x18000934b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009350  mov     rcx, [rsp+108h+var_A0]
0x180009355  mov     dword ptr [rsp+108h+var_D0], r15d
0x18000935a  mov     rax, [rcx]
0x18000935d  mov     r9d, 4
0x180009363  lea     r8, [rsp+108h+var_D0]
0x180009368  lea     rdx, MTF_PROPBAG_KEY_BINGFILTERDS_FILTER_BY_READING_LENGTH
0x18000936f  mov     rax, [rax+28h]
0x180009373  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009378  cmp     dword ptr [rsp+108h+var_D0], r15d
0x18000937d  setnz   [rsp+108h+var_D7]
0x180009382  mov     rcx, [rsp+108h+var_A0]
0x180009387  mov     dword ptr [rsp+108h+var_D0], r15d
0x18000938c  mov     rax, [rcx]
0x18000938f  mov     r9d, 4
0x180009395  lea     r8, [rsp+108h+var_D0]
0x18000939a  lea     rdx, MTF_PROPBAG_KEY_BINGFILTERDS_ALLOW_READING_MISMATCH
0x1800093a1  mov     rax, [rax+28h]
0x1800093a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093aa  cmp     dword ptr [rsp+108h+var_D0], r15d
0x1800093af  setnz   dil
0x1800093b3  mov     [rsp+108h+var_A4], r15d
0x1800093b8  mov     rcx, [rsp+108h+var_A0]
0x1800093bd  mov     rax, [rcx]
0x1800093c0  mov     r9d, 4
0x1800093c6  lea     r8, [rsp+108h+var_A4]
0x1800093cb  lea     rdx, MTF_PROPBAG_KEY_BINGASDS_RUNTIME_DUPCOUNT
0x1800093d2  mov     rax, [rax+28h]
0x1800093d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093db  mov     [rsp+108h+var_98], r15
0x1800093e0  mov     [rsp+108h+var_D8], r15b
0x1800093e5  mov     dword ptr [rsp+108h+var_D0], r15d
0x1800093ea  mov     rax, [rbx]
0x1800093ed  lea     rdx, [rsp+108h+var_D0]
0x1800093f2  mov     rcx, rbx
0x1800093f5  mov     rax, [rax+60h]
0x1800093f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093fe  test    eax, eax
0x180009400  js      short loc_18000946D
0x180009402  cmp     dword ptr [rsp+108h+var_D0], r15d
0x180009407  jbe     short loc_18000946D
0x180009409  xorps   xmm0, xmm0
0x18000940c  movups  [rsp+108h+var_88], xmm0
0x180009414  movups  [rsp+108h+var_78], xmm0
0x18000941c  mov     rax, [rbx]
0x18000941f  lea     r8, [rsp+108h+var_88]
0x180009427  xor     edx, edx
0x180009429  mov     rcx, rbx
0x18000942c  mov     rax, [rax+68h]
0x180009430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009435  test    eax, eax
0x180009437  js      short loc_18000946D
0x180009439  mov     rcx, qword ptr [rsp+108h+var_78+8]
0x180009441  test    rcx, rcx
0x180009444  jz      short loc_18000946D
0x180009446  mov     [rsp+108h+var_C0], r15d
0x18000944b  mov     rax, [rcx]
0x18000944e  lea     rdx, [rsp+108h+var_C0]
0x180009453  mov     rax, [rax+18h]
0x180009457  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000945c  test    eax, eax
0x18000945e  js      short loc_18000946D
0x180009460  mov     eax, r15d
0x180009463  cmp     [rsp+108h+var_C0], r15d
0x180009468  setnbe  al
0x18000946b  jmp     short loc_180009470
0x18000946d  mov     eax, r15d
0x180009470  inc     eax
0x180009472  mov     [rsp+108h+var_B8], eax
0x180009476  lea     rax, [rsp+108h+var_88]
0x18000947e  mov     qword ptr [rsp+108h+var_C0], rax
0x180009483  mov     qword ptr [rsp+108h+var_78+8], r15
0x18000948b  mov     ecx, 50h ; 'P'; Size
0x180009490  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009495  test    rax, rax
0x180009498  jz      loc_180009774
0x18000949e  lea     rcx, off_18000FCF8
0x1800094a5  mov     [rax], rcx
0x1800094a8  lea     rcx, [rsp+108h+var_68]
0x1800094b0  mov     [rax+8], rcx
0x1800094b4  lea     rcx, [rsp+108h+var_B8]
0x1800094b9  mov     [rax+10h], rcx
0x1800094bd  lea     rcx, [rsp+108h+var_58]
0x1800094c5  mov     [rax+18h], rcx
0x1800094c9  lea     rcx, [rsp+108h+var_98]
0x1800094ce  mov     [rax+20h], rcx
0x1800094d2  lea     rcx, [rsp+108h+var_D7]
0x1800094d7  mov     [rax+28h], rcx
0x1800094db  lea     rcx, [rsp+108h+var_A4]
0x1800094e0  mov     [rax+30h], rcx
0x1800094e4  lea     rcx, [rsp+108h+var_D8]
0x1800094e9  mov     [rax+38h], rcx
0x1800094ed  lea     rcx, [rsp+108h+var_B0]
0x1800094f2  mov     [rax+40h], rcx
0x1800094f6  mov     qword ptr [rsp+108h+var_78+8], rax
0x1800094fe  lea     rdx, [rsp+108h+var_88]
0x180009506  mov     rcx, rbx
0x180009509  call    ?ForEachFormerCandidate@@YAXPEAUIMtfSuggestionInputQuery@@V?$function@$$A6AXAEBU_MTF_FORMER_RESULT@@PEAUIMtfSuggestionListElement@@@Z@std@@@Z; ForEachFormerCandidate(IMtfSuggestionInputQuery *,std::function<void (_MTF_FORMER_RESULT const &,IMtfSuggestionListElement *)>)
0x18000950e  mov     [rsp+108h+var_C8], r15d
0x180009513  mov     rcx, [rsp+108h+var_B0]
0x180009518  mov     rax, [rcx]
0x18000951b  lea     rdx, [rsp+108h+var_C8]
0x180009520  mov     rax, [rax+18h]
0x180009524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009529  mov     rcx, [rsp+108h]; this
0x180009531  test    eax, eax
0x180009533  js      loc_18000977A
0x180009539  cmp     [rsp+108h+var_C8], r15d
0x18000953e  jnz     loc_18000968B
0x180009544  test    dil, dil
0x180009547  jz      loc_1800095DC
0x18000954d  mov     rcx, [rsp+108h+var_98]
0x180009552  test    rcx, rcx
0x180009555  jz      loc_1800095DC
0x18000955b  mov     qword ptr [rsp+108h+var_C0], r15
0x180009560  mov     rax, [rcx]
0x180009563  lea     r8, [rsp+108h+var_C0]
0x180009568  lea     rdx, _GUID_c4445657_6908_45eb_a6b9_2f1ea4b2a03a
0x18000956f  mov     rax, [rax]
0x180009572  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009577  mov     rcx, [rsp+108h]; this
0x18000957f  test    eax, eax
0x180009581  js      loc_18000978E
0x180009587  mov     rcx, qword ptr [rsp+108h+var_C0]
0x18000958c  call    UpdateNoLearnFlag
0x180009591  nop
0x180009592  mov     rcx, qword ptr [rsp+108h+var_C0]
0x180009597  test    rcx, rcx
0x18000959a  jz      short loc_1800095A9
0x18000959c  mov     rax, [rcx]
0x18000959f  mov     rax, [rax+10h]
0x1800095a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095a8  nop
0x1800095a9  mov     rcx, [rsp+108h+var_B0]
0x1800095ae  mov     rax, [rcx]
0x1800095b1  mov     rdx, [rsp+108h+var_98]
0x1800095b6  mov     rax, [rax+30h]
0x1800095ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095bf  mov     rcx, [rsp+108h]; this
0x1800095c7  test    eax, eax
0x1800095c9  js      loc_1800097A2
0x1800095cf  mov     [rsp+108h+var_B8], 6
0x1800095d7  jmp     loc_18000968B
0x1800095dc  cmp     [rsp+108h+var_D8], r15b
0x1800095e1  jz      loc_18000968B
0x1800095e7  mov     [rsp+108h+var_C0], r15d
0x1800095ec  lea     rdx, [rsp+108h+var_C0]; unsigned int *
0x1800095f1  mov     rcx, [rsp+108h+var_48]; unsigned __int64
0x1800095f9  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800095fe  mov     rcx, [rsp+108h]; this
0x180009606  test    eax, eax
0x180009608  js      loc_1800097B6
0x18000960e  lea     r8, [rsp+108h+var_58]
0x180009616  cmp     [rsp+108h+var_40], 8
0x18000961f  cmovnb  r8, [rsp+108h+var_58]
0x180009628  mov     r9d, [rsp+108h+var_C0]
0x18000962d  lea     rdx, [rsp+108h+var_D0]
0x180009632  mov     rcx, rsi
0x180009635  call    ?TryGetPreviousCandidateWithSameReading@BingFilterDS@@IEAA?AV?$com_ptr_t@UIMtfSuggestionListElement@@Uerr_exception_policy@wil@@@wil@@PEBGI@Z; BingFilterDS::TryGetPreviousCandidateWithSameReading(ushort const *,uint)
0x18000963a  nop
0x18000963b  mov     rcx, [rsp+108h+var_D0]
0x180009640  test    rcx, rcx
0x180009643  jz      short loc_180009679
0x180009645  mov     r8, [rsp+108h+var_B0]
0x18000964a  mov     rax, [r8]
0x18000964d  mov     rdx, rcx
0x180009650  mov     rcx, r8
0x180009653  mov     rax, [rax+30h]
0x180009657  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000965c  mov     rcx, [rsp+108h]; this
0x180009664  test    eax, eax
0x180009666  js      loc_1800097BF
0x18000966c  mov     [rsp+108h+var_B8], 7
0x180009674  mov     rcx, [rsp+108h+var_D0]
0x180009679  test    rcx, rcx
0x18000967c  jz      short loc_18000968B
0x18000967e  mov     rax, [rcx]
0x180009681  mov     rax, [rax+10h]
0x180009685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000968a  nop
0x18000968b  mov     rdx, [rsp+108h+var_B0]; struct IMtfSuggestionList *
0x180009690  mov     rcx, rsi; this
0x180009693  call    ?UpdateCandidateCache@BingFilterDS@@IEAAXPEAUIMtfSuggestionList@@@Z; BingFilterDS::UpdateCandidateCache(IMtfSuggestionList *)
0x180009698  mov     rax, [rsp+108h+var_B0]
0x18000969d  mov     [rsp+108h+var_B0], r15
0x1800096a2  mov     [r14], rax
0x1800096a5  mov     ecx, [rsp+108h+var_B8]
0x1800096a9  call    ?FilterStatistics@BingFilterDSTelemetry@@SAXW4FilterResult@@@Z; BingFilterDSTelemetry::FilterStatistics(FilterResult)
0x1800096ae  nop
0x1800096af  mov     rcx, [rsp+108h+var_98]
0x1800096b4  test    rcx, rcx
0x1800096b7  jz      short loc_1800096C6
0x1800096b9  mov     rax, [rcx]
0x1800096bc  mov     rax, [rax+10h]
0x1800096c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096c5  nop
0x1800096c6  mov     rcx, [rsp+108h+var_A0]
0x1800096cb  test    rcx, rcx
0x1800096ce  jz      short loc_1800096DD
0x1800096d0  mov     rax, [rcx]
0x1800096d3  mov     rax, [rax+10h]
0x1800096d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096dc  nop
0x1800096dd  lea     rcx, [rsp+108h+var_68]
0x1800096e5  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x1800096ea  nop
0x1800096eb  cmp     [rsp+108h+var_40], 8
0x1800096f4  jb      short loc_180009704
0x1800096f6  mov     rcx, [rsp+108h+var_58]
0x1800096fe  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180009704  mov     [rsp+108h+var_40], 7
0x180009710  mov     [rsp+108h+var_48], r15
0x180009718  mov     word ptr [rsp+108h+var_58], r15w
0x180009721  mov     rcx, [rsp+108h+var_B0]
0x180009726  test    rcx, rcx
0x180009729  jz      short loc_180009738
0x18000972b  mov     rax, [rcx]
0x18000972e  mov     rax, [rax+10h]
0x180009732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009737  nop
0x180009738  xor     eax, eax
0x18000973a  jmp     short loc_180009740
0x18000973c  mov     eax, [rsp+108h+var_C8]
0x180009740  mov     rcx, [rsp+108h+var_38]
0x180009748  xor     rcx, rsp; StackCookie
0x18000974b  call    __security_check_cookie
0x180009750  add     rsp, 0E0h
0x180009757  pop     r15
0x180009759  pop     r14
0x18000975b  pop     rdi
0x18000975c  pop     rsi
0x18000975d  pop     rbx
0x18000975e  retn
0x18000975f  mov     r9d, eax; char *
0x180009762  lea     r8, aMincoreTextinp; "mincore\\textinput\\dev\\mtf\\datasourc"...
0x180009769  mov     edx, 153h; void *
0x18000976e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180009774  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000977a  mov     r9d, eax; char *
0x18000977d  lea     r8, aMincoreTextinp; "mincore\\textinput\\dev\\mtf\\datasourc"...
0x180009784  mov     edx, 1A5h; void *
0x180009789  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000978e  mov     r9d, eax; char *
0x180009791  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180009798  mov     edx, 1CBEh; void *
0x18000979d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
  ... truncated ...
```
