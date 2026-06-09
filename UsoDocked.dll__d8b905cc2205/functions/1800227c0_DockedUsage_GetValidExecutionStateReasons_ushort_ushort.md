# DockedUsage::GetValidExecutionStateReasons(ushort * *,ushort * *)

- ea: `0x1800227c0`
- end: `0x180022f59`
- name: `?GetValidExecutionStateReasons@DockedUsage@@UEAAJPEAPEAG0@Z`
- size: `1945`
- prototype: `__int64 __fastcall(DockedUsage *__hidden this, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `16`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x180007660`
- `0x1800183f4`
- `0x18001ba70`
- `0x18001ee04`
- `0x18001ee70`
- `0x180020ce4`
- `0x18002107c`
- `0x18002183c`
- `0x180021bf0`
- `0x180022198`
- `0x1800225b8`
- `0x1800227c0`
- `0x180023060`
- `0x180023a34`
- `0x180045bd4`
- `0x180071010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180022e3a`
- `OLEAUT32!__imp_SysAllocString` at `0x180022e81`
- `OLEAUT32!__imp_SysAllocString` at `0x180022e3a`
- `OLEAUT32!__imp_SysAllocString` at `0x180022e81`

## string_xrefs

- `0x180022f34`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180022f46`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180022819`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedusage.cpp`
- `0x180022846`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedusage.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall DockedUsage::GetValidExecutionStateReasons(
        DockedUsage *this,
        unsigned __int16 **a2,
        unsigned __int16 **a3)
{
  int v3; // edi
  __int64 result; // rax
  _QWORD *v5; // rsi
  __int64 v6; // rax
  int v7; // r14d
  int v8; // r15d
  char *v9; // rbx
  char v10; // r13
  __int64 v11; // rdx
  __int64 v12; // r8
  _QWORD *v13; // r9
  _QWORD *v14; // r9
  _QWORD *v15; // r9
  _QWORD *System; // rax
  BSTR **v17; // rax
  BSTR *v18; // rbx
  const wchar_t *v19; // rdx
  __int64 v20; // r8
  const wchar_t *v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rax
  void *v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rax
  volatile signed __int32 *v27; // rbx
  volatile signed __int32 *v28; // rbx
  __int64 *i; // r12
  const OLECHAR *v30; // rcx
  BSTR v31; // rax
  const char *v32; // r9
  const OLECHAR *v33; // rcx
  BSTR v34; // rax
  const char *v35; // r9
  const char *v36; // r9
  int v37; // [rsp+20h] [rbp-218h]
  __int128 v38; // [rsp+48h] [rbp-1F0h] BYREF
  __int128 v39; // [rsp+58h] [rbp-1E0h]
  BSTR v40; // [rsp+68h] [rbp-1D0h]
  unsigned __int16 **v41; // [rsp+70h] [rbp-1C8h]
  unsigned __int16 **v42; // [rsp+78h] [rbp-1C0h]
  __int128 v43; // [rsp+80h] [rbp-1B8h] BYREF
  __int128 v44; // [rsp+90h] [rbp-1A8h]
  _OWORD v45[2]; // [rsp+A0h] [rbp-198h] BYREF
  _OWORD v46[2]; // [rsp+C0h] [rbp-178h] BYREF
  char v47[8]; // [rsp+E0h] [rbp-158h] BYREF
  volatile signed __int32 *v48; // [rsp+E8h] [rbp-150h]
  char v49[8]; // [rsp+F0h] [rbp-148h] BYREF
  volatile signed __int32 *v50; // [rsp+F8h] [rbp-140h]
  _OWORD v51[2]; // [rsp+100h] [rbp-138h] BYREF
  _BYTE v52[32]; // [rsp+120h] [rbp-118h] BYREF
  _QWORD v53[2]; // [rsp+140h] [rbp-F8h] BYREF
  __int64 v54; // [rsp+150h] [rbp-E8h]
  unsigned __int64 v55; // [rsp+158h] [rbp-E0h]
  __int64 v56; // [rsp+160h] [rbp-D8h]
  OLECHAR *psz[2]; // [rsp+168h] [rbp-D0h] BYREF
  __int64 v58; // [rsp+178h] [rbp-C0h]
  unsigned __int64 v59; // [rsp+180h] [rbp-B8h]
  OLECHAR *v60[2]; // [rsp+188h] [rbp-B0h] BYREF
  __int64 v61; // [rsp+198h] [rbp-A0h]
  unsigned __int64 v62; // [rsp+1A0h] [rbp-98h]
  __int128 Src; // [rsp+1A8h] [rbp-90h] BYREF
  __int64 v64; // [rsp+1B8h] [rbp-80h]
  __int64 v65; // [rsp+1C0h] [rbp-78h]
  __int128 v66; // [rsp+1C8h] [rbp-70h] BYREF
  __int64 v67; // [rsp+1D8h] [rbp-60h]
  __int64 v68; // [rsp+1E0h] [rbp-58h]
  __int64 v69[3]; // [rsp+1F0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+0h]

  v42 = a3;
  v41 = a2;
  v3 = 0;
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CF,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedusage.cpp",
      (const char *)0x80004003LL,
      v37);
    return 2147500035LL;
  }
  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D0,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedusage.cpp",
      (const char *)0x80004003LL,
      v37);
    return 2147500035LL;
  }
  v56 = 0;
  *(_OWORD *)psz = 0;
  v58 = 0;
  v59 = 7;
  LOWORD(psz[0]) = 0;
  *(_OWORD *)v60 = 0;
  v61 = 0;
  v62 = 7;
  LOWORD(v60[0]) = 0;
  Src = 0;
  v64 = 0;
  v65 = 7;
  LOWORD(Src) = 0;
  v66 = 0;
  v67 = 0;
  v68 = 7;
  LOWORD(v66) = 0;
  try
  {
    GetPowerInformation(v69, 0x2Du);
    v5 = (_QWORD *)v69[0];
    for ( i = (__int64 *)(v69[0] + 8); ; ++i )
    {
      if ( i >= &v5[*v5 + 1] )
      {
        v30 = (const OLECHAR *)psz;
        if ( v59 > 7 )
          v30 = psz[0];
        v31 = SysAllocString(v30);
        v40 = v31;
        if ( !v31 )
          wil::details::in1diag3::_Throw_NullAlloc(
            retaddr,
            (void *)0x15F3,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v32);
        *v41 = v31;
        v33 = (const OLECHAR *)v60;
        if ( v62 > 7 )
          v33 = v60[0];
        v34 = SysAllocString(v33);
        v41 = (unsigned __int16 **)v34;
        if ( !v34 )
          wil::details::in1diag3::_Throw_NullAlloc(
            retaddr,
            (void *)0x15F3,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v35);
        *v42 = v34;
        std::vector<unsigned char>::~vector<unsigned char>(v69);
        std::wstring::_Tidy_deallocate(&v66);
        std::wstring::_Tidy_deallocate(&Src);
        std::wstring::_Tidy_deallocate(v60);
        std::wstring::_Tidy_deallocate(psz);
        return 0;
      }
      v6 = *i;
      if ( *i )
      {
        v7 = *(_DWORD *)((char *)v5 + v6 + 8);
        if ( *(_QWORD *)((char *)v5 + v6 + 4) )
          break;
      }
LABEL_45:
      ;
    }
    v8 = *(_DWORD *)((char *)v5 + v6 + 4);
    v9 = (char *)v5 + v6;
    v10 = IsPowerRequestIgnorable((const struct _DIAGNOSTIC_BUFFER *)((char *)v5 + v6 + 32));
    GetDetails((__int64)v53, (__int64)(v9 + 32));
    if ( v10 )
    {
      if ( 0x7FFFFFFFFFFFFFFELL == v54 )
        std::_Xlen_string();
      v13 = v53;
      if ( v55 > 7 )
        v13 = (_QWORD *)v53[0];
      std::wstring::wstring(&v38, v54, v12, v13);
      v3 |= 1u;
      std::wstring::_Append<unsigned short>(&Src);
    }
    else
    {
      if ( v7 > 0 )
      {
        if ( v54 == 0x7FFFFFFFFFFFFFFELL )
          std::_Xlen_string();
        v14 = v53;
        if ( v55 > 7 )
          v14 = (_QWORD *)v53[0];
        std::wstring::wstring(&v38, v11, v12, v14);
        v3 |= 2u;
        std::wstring::_Append<unsigned short>(psz);
        std::wstring::_Tidy_deallocate(&v38);
      }
      if ( v8 <= 0 )
        goto LABEL_25;
      if ( v54 == 0x7FFFFFFFFFFFFFFELL )
        std::_Xlen_string();
      v15 = v53;
      if ( v55 > 7 )
        v15 = (_QWORD *)v53[0];
      std::wstring::wstring(&v38, v11, v12, v15);
      v3 |= 4u;
      std::wstring::_Append<unsigned short>(v60);
    }
    std::wstring::_Tidy_deallocate(&v38);
LABEL_25:
    System = (_QWORD *)SystemInterface::Service::GetSystem(v49);
    v17 = (BSTR **)(*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*System + 96LL))(*System, v47);
    v18 = *v17;
    v40 = **v17;
    if ( v7 <= 0 )
    {
      v19 = L"display";
    }
    else
    {
      v19 = L"system and display";
      if ( v8 <= 0 )
        v19 = L"system";
    }
    memset(v46, 0, sizeof(v46));
    v20 = -1;
    do
      ++v20;
    while ( v19[v20] );
    std::wstring::_Construct<1,unsigned short const *>(v46, v19);
    v21 = L"Ignored";
    if ( !v10 )
      v21 = L"Honored";
    memset(v45, 0, sizeof(v45));
    v22 = -1;
    do
      ++v22;
    while ( v21[v22] );
    std::wstring::_Construct<1,unsigned short const *>(v45, v21);
    v23 = std::wstring::_Append<unsigned short>(v45);
    v51[0] = *(_OWORD *)v23;
    v51[1] = *(_OWORD *)(v23 + 16);
    *(_QWORD *)(v23 + 16) = 0;
    *(_QWORD *)(v23 + 24) = 7;
    *(_WORD *)v23 = 0;
    v24 = (void *)std::operator+<unsigned short>(v52, v51, v46);
    v25 = std::wstring::_Append<unsigned short>(v24);
    v43 = 0;
    v44 = 0;
    v43 = *(_OWORD *)v25;
    v44 = *(_OWORD *)(v25 + 16);
    *(_QWORD *)(v25 + 16) = 0;
    *(_QWORD *)(v25 + 24) = 7;
    *(_WORD *)v25 = 0;
    v26 = std::wstring::_Append<unsigned short>(&v43);
    v38 = 0;
    v39 = 0;
    v38 = *(_OWORD *)v26;
    v39 = *(_OWORD *)(v26 + 16);
    *(_QWORD *)(v26 + 16) = 0;
    *(_QWORD *)(v26 + 24) = 7;
    *(_WORD *)v26 = 0;
    v3 |= 0x38u;
    (*((void (__fastcall **)(BSTR *, __int128 *, __int64))v40 + 14))(v18, &v38, 1);
    std::wstring::_Tidy_deallocate(&v38);
    std::wstring::_Tidy_deallocate(&v43);
    std::wstring::_Tidy_deallocate(v52);
    std::wstring::_Tidy_deallocate(v51);
    std::wstring::_Tidy_deallocate(v45);
    std::wstring::_Tidy_deallocate(v46);
    v27 = v48;
    if ( v48 )
    {
      if ( _InterlockedExchangeAdd(v48 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
        if ( _InterlockedExchangeAdd(v27 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
      }
    }
    v28 = v50;
    if ( v50 && _InterlockedExchangeAdd(v50 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v28)(v28);
      if ( _InterlockedExchangeAdd(v28 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
    }
    std::wstring::_Tidy_deallocate(v53);
    goto LABEL_45;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x209,
                           (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\d"
                                         "ll\\dockedusage.cpp",
                           v36);
  }
  return result;
}

```

## disassembly

```asm
0x1800227c0  mov     [rsp+arg_0], rbx
0x1800227c5  mov     [rsp+arg_18], rsi
0x1800227ca  push    rdi
0x1800227cb  push    r12
0x1800227cd  push    r13
0x1800227cf  push    r14
0x1800227d1  push    r15
0x1800227d3  sub     rsp, 210h
0x1800227da  mov     rax, cs:__security_cookie
0x1800227e1  xor     rax, rsp
0x1800227e4  mov     [rsp+238h+var_30], rax
0x1800227ec  mov     rbx, r8
0x1800227ef  mov     [rsp+238h+var_1C0], rbx
0x1800227f4  mov     [rsp+238h+var_1C8], rdx
0x1800227f9  xor     r15d, r15d
0x1800227fc  mov     edi, r15d
0x1800227ff  mov     [rsp+238h+var_1F8], r15d
0x180022804  test    rdx, rdx
0x180022807  jnz     short loc_180022831
0x180022809  mov     rcx, [rsp+238h]; this
0x180022811  mov     ebx, 80004003h
0x180022816  mov     r9d, ebx; char *
0x180022819  lea     r8, aOnecoreEnduser_4; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180022820  mov     edx, 1CFh; void *
0x180022825  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002282a  mov     eax, ebx
0x18002282c  jmp     loc_180022EF7
0x180022831  test    rbx, rbx
0x180022834  jnz     short loc_18002285E
0x180022836  mov     rcx, [rsp+238h]; this
0x18002283e  mov     ebx, 80004003h
0x180022843  mov     r9d, ebx; char *
0x180022846  lea     r8, aOnecoreEnduser_4; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18002284d  mov     edx, 1D0h; void *
0x180022852  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022857  mov     eax, ebx
0x180022859  jmp     loc_180022EF7
0x18002285e  xor     eax, eax
0x180022860  mov     [rsp+238h+var_D8], rax
0x180022868  xorps   xmm0, xmm0
0x18002286b  movups  xmmword ptr [rsp+238h+psz], xmm0
0x180022873  mov     [rsp+238h+var_C0], r15
0x18002287b  lea     r14d, [rax+7]
0x18002287f  mov     [rsp+238h+var_B8], r14
0x180022887  mov     word ptr [rsp+238h+psz], r15w
0x180022890  movups  xmmword ptr [rsp+238h+var_B0], xmm0
0x180022898  mov     [rsp+238h+var_A0], r15
0x1800228a0  mov     [rsp+238h+var_98], r14
0x1800228a8  mov     word ptr [rsp+238h+var_B0], r15w
0x1800228b1  movups  [rsp+238h+Src], xmm0
0x1800228b9  mov     [rsp+238h+var_80], r15
0x1800228c1  mov     [rsp+238h+var_78], r14
0x1800228c9  mov     word ptr [rsp+238h+Src], r15w
0x1800228d2  movups  [rsp+238h+var_70], xmm0
0x1800228da  mov     [rsp+238h+var_60], r15
0x1800228e2  mov     [rsp+238h+var_58], r14
0x1800228ea  mov     word ptr [rsp+238h+var_70], r15w
0x1800228f3  lea     edx, [rax+2Dh]
0x1800228f6  lea     rcx, [rsp+238h+var_48]
0x1800228fe  call    ?GetPowerInformation@@YA?AV?$vector@EV?$allocator@E@std@@@std@@W4POWER_INFORMATION_LEVEL@@@Z; GetPowerInformation(POWER_INFORMATION_LEVEL)
0x180022903  nop
0x180022904  mov     rsi, [rsp+238h+var_48]
0x18002290c  lea     r12, [rsi+8]
0x180022910  mov     rcx, [rsi]
0x180022913  inc     rcx
0x180022916  lea     rcx, [rsi+rcx*8]
0x18002291a  cmp     r12, rcx
0x18002291d  jnb     loc_180022E21
0x180022923  mov     rax, [r12]
0x180022927  test    rax, rax
0x18002292a  jz      loc_180022E18
0x180022930  mov     r14d, [rax+rsi+8]
0x180022935  lea     rcx, [rax+rsi]
0x180022939  test    r14d, r14d
0x18002293c  jnz     short loc_180022948
0x18002293e  cmp     [rcx+4], r15d
0x180022942  jz      loc_180022E12
0x180022948  mov     r15d, [rcx+4]
0x18002294c  lea     rbx, [rax+rsi]
0x180022950  lea     rcx, [rbx+20h]; struct _DIAGNOSTIC_BUFFER *
0x180022954  call    ?IsPowerRequestIgnorable@@YA_NAEBU_DIAGNOSTIC_BUFFER@@@Z; IsPowerRequestIgnorable(_DIAGNOSTIC_BUFFER const &)
0x180022959  mov     r13b, al
0x18002295c  lea     rdx, [rbx+20h]
0x180022960  lea     rcx, [rsp+238h+var_F8]
0x180022968  call    ?GetDetails@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_DIAGNOSTIC_BUFFER@@@Z; GetDetails(_DIAGNOSTIC_BUFFER const &)
0x18002296d  nop
0x18002296e  mov     rbx, 7FFFFFFFFFFFFFFEh
0x180022978  test    r13b, r13b
0x18002297b  jz      short loc_1800229FC
0x18002297d  mov     rdx, [rsp+238h+var_E8]
0x180022985  sub     rbx, rdx
0x180022988  cmp     rbx, 1
0x18002298c  jb      loc_180022F24
0x180022992  lea     r9, [rsp+238h+var_F8]
0x18002299a  cmp     [rsp+238h+var_E0], 7
0x1800229a3  cmova   r9, [rsp+238h+var_F8]
0x1800229ac  mov     [rsp+238h+var_208], 1
0x1800229b5  lea     rax, asc_180079CF8; ";"
0x1800229bc  mov     [rsp+238h+var_210], rax
0x1800229c1  mov     [rsp+238h+var_218], rdx
0x1800229c6  lea     rcx, [rsp+238h+var_1F0]
0x1800229cb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1800229d0  or      edi, 1
0x1800229d3  lea     rdx, [rsp+238h+var_1F0]
0x1800229d8  cmp     qword ptr [rsp+238h+var_1E0+8], 7
0x1800229de  cmova   rdx, qword ptr [rsp+238h+var_1F0]
0x1800229e4  mov     r8, qword ptr [rsp+238h+var_1E0]
0x1800229e9  lea     rcx, [rsp+238h+Src]; Src
0x1800229f1  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800229f6  nop
0x1800229f7  jmp     loc_180022B12
0x1800229fc  test    r14d, r14d
0x1800229ff  jle     loc_180022A8C
0x180022a05  mov     rcx, [rsp+238h+var_E8]
0x180022a0d  mov     rax, rbx
0x180022a10  sub     rax, rcx
0x180022a13  cmp     rax, 1
0x180022a17  jb      loc_180022F29
0x180022a1d  lea     r9, [rsp+238h+var_F8]
0x180022a25  cmp     [rsp+238h+var_E0], 7
0x180022a2e  cmova   r9, [rsp+238h+var_F8]
0x180022a37  mov     [rsp+238h+var_208], 1
0x180022a40  lea     rax, asc_180079CF8; ";"
0x180022a47  mov     [rsp+238h+var_210], rax
0x180022a4c  mov     [rsp+238h+var_218], rcx
0x180022a51  lea     rcx, [rsp+238h+var_1F0]
0x180022a56  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180022a5b  or      edi, 2
0x180022a5e  lea     rdx, [rsp+238h+var_1F0]
0x180022a63  cmp     qword ptr [rsp+238h+var_1E0+8], 7
0x180022a69  cmova   rdx, qword ptr [rsp+238h+var_1F0]
0x180022a6f  mov     r8, qword ptr [rsp+238h+var_1E0]
0x180022a74  lea     rcx, [rsp+238h+psz]; Src
0x180022a7c  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180022a81  nop
0x180022a82  lea     rcx, [rsp+238h+var_1F0]
0x180022a87  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022a8c  test    r15d, r15d
0x180022a8f  jle     loc_180022B1C
0x180022a95  mov     rcx, [rsp+238h+var_E8]
0x180022a9d  mov     rax, rbx
0x180022aa0  sub     rax, rcx
0x180022aa3  cmp     rax, 1
0x180022aa7  jb      loc_180022F2E
0x180022aad  lea     r9, [rsp+238h+var_F8]
0x180022ab5  cmp     [rsp+238h+var_E0], 7
0x180022abe  cmova   r9, [rsp+238h+var_F8]
0x180022ac7  mov     [rsp+238h+var_208], 1
0x180022ad0  lea     rax, asc_180079CF8; ";"
0x180022ad7  mov     [rsp+238h+var_210], rax
0x180022adc  mov     [rsp+238h+var_218], rcx
0x180022ae1  lea     rcx, [rsp+238h+var_1F0]
0x180022ae6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180022aeb  or      edi, 4
0x180022aee  lea     rdx, [rsp+238h+var_1F0]
0x180022af3  cmp     qword ptr [rsp+238h+var_1E0+8], 7
0x180022af9  cmova   rdx, qword ptr [rsp+238h+var_1F0]
0x180022aff  mov     r8, qword ptr [rsp+238h+var_1E0]
0x180022b04  lea     rcx, [rsp+238h+var_B0]; Src
0x180022b0c  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180022b11  nop
0x180022b12  lea     rcx, [rsp+238h+var_1F0]
0x180022b17  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022b1c  lea     rcx, [rsp+238h+var_148]
0x180022b24  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x180022b29  nop
0x180022b2a  mov     rcx, [rax]
0x180022b2d  mov     rax, [rcx]
0x180022b30  lea     rdx, [rsp+238h+var_158]
0x180022b38  mov     rax, [rax+60h]
0x180022b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022b41  nop
0x180022b42  mov     rbx, [rax]
0x180022b45  mov     rax, [rbx]
0x180022b48  mov     [rsp+238h+var_1D0], rax
0x180022b4d  test    r14d, r14d
0x180022b50  jle     short loc_180022B69
0x180022b52  lea     rax, aSystem; "system"
0x180022b59  lea     rdx, aSystemAndDispl; "system and display"
0x180022b60  test    r15d, r15d
0x180022b63  cmovle  rdx, rax
0x180022b67  jmp     short loc_180022B70
0x180022b69  lea     rdx, aDisplay; "display"
0x180022b70  xorps   xmm0, xmm0
0x180022b73  movups  [rsp+238h+var_178], xmm0
0x180022b7b  xorps   xmm1, xmm1
0x180022b7e  movdqu  [rsp+238h+var_168], xmm1
0x180022b87  or      r8, 0FFFFFFFFFFFFFFFFh
0x180022b8b  xor     r15d, r15d
0x180022b8e  inc     r8
0x180022b91  cmp     [rdx+r8*2], r15w
0x180022b96  jnz     short loc_180022B8E
0x180022b98  lea     rcx, [rsp+238h+var_178]
0x180022ba0  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180022ba5  nop
0x180022ba6  lea     rax, aHonored; "Honored"
0x180022bad  lea     rdx, aIgnored; "Ignored"
0x180022bb4  test    r13b, r13b
0x180022bb7  cmovz   rdx, rax
0x180022bbb  xorps   xmm0, xmm0
0x180022bbe  movups  [rsp+238h+var_198], xmm0
0x180022bc6  xorps   xmm1, xmm1
0x180022bc9  movdqu  [rsp+238h+var_188], xmm1
0x180022bd2  or      r13, 0FFFFFFFFFFFFFFFFh
0x180022bd6  mov     r8, r13
0x180022bd9  inc     r8
0x180022bdc  cmp     [rdx+r8*2], r15w
0x180022be1  jnz     short loc_180022BD9
0x180022be3  lea     rcx, [rsp+238h+var_198]
0x180022beb  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180022bf0  nop
0x180022bf1  mov     r8d, 1
0x180022bf7  lea     rdx, asc_180079D60; " "
0x180022bfe  lea     rcx, [rsp+238h+var_198]; Src
0x180022c06  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180022c0b  movups  xmm0, xmmword ptr [rax]
0x180022c0e  movups  [rsp+238h+var_138], xmm0
0x180022c16  movups  xmm1, xmmword ptr [rax+10h]
0x180022c1a  movups  [rsp+238h+var_128], xmm1
0x180022c22  mov     [rax+10h], r15
0x180022c26  mov     r14d, 7
0x180022c2c  mov     [rax+18h], r14
0x180022c30  mov     [rax], r15w
0x180022c34  or      edi, 8
0x180022c37  lea     r8, [rsp+238h+var_178]
0x180022c3f  lea     rdx, [rsp+238h+var_138]
0x180022c47  lea     rcx, [rsp+238h+var_118]
0x180022c4f  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x180022c54  nop
0x180022c55  lea     r8d, [r14+2]
0x180022c59  lea     rdx, aReason; " reason: "
0x180022c60  mov     rcx, rax; Src
0x180022c63  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180022c68  xorps   xmm0, xmm0
0x180022c6b  movups  [rsp+238h+var_1B8], xmm0
0x180022c73  xorps   xmm1, xmm1
0x180022c76  movdqu  [rsp+238h+var_1A8], xmm1
0x180022c7f  movups  xmm0, xmmword ptr [rax]
0x180022c82  movups  [rsp+238h+var_1B8], xmm0
0x180022c8a  movups  xmm1, xmmword ptr [rax+10h]
0x180022c8e  movups  [rsp+238h+var_1A8], xmm1
0x180022c96  mov     [rax+10h], r15
0x180022c9a  mov     [rax+18h], r14
0x180022c9e  mov     [rax], r15w
0x180022ca2  or      edi, 10h
0x180022ca5  mov     [rsp+238h+var_1F8], edi
0x180022ca9  lea     rdx, [rsp+238h+var_F8]
0x180022cb1  cmp     [rsp+238h+var_E0], r14
0x180022cb9  setnbe  al
0x180022cbc  test    al, al
0x180022cbe  cmovnz  rdx, [rsp+238h+var_F8]
0x180022cc7  mov     r8, [rsp+238h+var_E8]
0x180022ccf  lea     rcx, [rsp+238h+var_1B8]; Src
0x180022cd7  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180022cdc  xorps   xmm0, xmm0
0x180022cdf  movups  [rsp+238h+var_1F0], xmm0
0x180022ce4  xorps   xmm1, xmm1
0x180022ce7  movdqu  [rsp+238h+var_1E0], xmm1
0x180022ced  movups  xmm0, xmmword ptr [rax]
0x180022cf0  movups  [rsp+238h+var_1F0], xmm0
0x180022cf5  movups  xmm1, xmmword ptr [rax+10h]
0x180022cf9  movups  [rsp+238h+var_1E0], xmm1
0x180022cfe  mov     [rax+10h], r15
0x180022d02  mov     [rax+18h], r14
0x180022d06  mov     [rax], r15w
0x180022d0a  or      edi, 20h
0x180022d0d  lea     r8d, [r14-6]
0x180022d11  lea     rdx, [rsp+238h+var_1F0]
0x180022d16  mov     rcx, rbx
0x180022d19  mov     rax, [rsp+238h+var_1D0]
0x180022d1e  mov     rax, [rax+70h]
0x180022d22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022d27  nop
0x180022d28  lea     rcx, [rsp+238h+var_1F0]
0x180022d2d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022d32  nop
0x180022d33  lea     rcx, [rsp+238h+var_1B8]
0x180022d3b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022d40  nop
0x180022d41  lea     rcx, [rsp+238h+var_118]
0x180022d49  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022d4e  nop
0x180022d4f  lea     rcx, [rsp+238h+var_138]
0x180022d57  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022d5c  nop
0x180022d5d  lea     rcx, [rsp+238h+var_198]
0x180022d65  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022d6a  nop
0x180022d6b  lea     rcx, [rsp+238h+var_178]
0x180022d73  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022d78  nop
0x180022d79  mov     rbx, [rsp+238h+var_150]
0x180022d81  test    rbx, rbx
0x180022d84  jz      short loc_180022DBE
0x180022d86  mov     eax, r13d
0x180022d89  lock xadd [rbx+8], eax
0x180022d8e  add     eax, r13d
0x180022d91  jnz     short loc_180022DBE
0x180022d93  mov     rax, [rbx]
0x180022d96  mov     rcx, rbx
  ... truncated ...
```
