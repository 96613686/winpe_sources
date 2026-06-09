# FetchLanguageOverlayPackageForFirstLogonForUser(LanguageOverlayTraceProvider::LogonOverlayBootstrappingForUserActivity const &,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>)

- ea: `0x180034120`
- end: `0x1800346f5`
- name: `?FetchLanguageOverlayPackageForFirstLogonForUser@@YAJAEBVLogonOverlayBootstrappingForUserActivity@LanguageOverlayTraceProvider@@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z`
- size: `1493`
- prototype: `__int64 __fastcall(LanguageOverlayTraceProvider::LogonOverlayBootstrappingForUserActivity *, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800196c0`

## callees

- `0x180003a00`
- `0x180003ea0`
- `0x1800044b8`
- `0x180005db4`
- `0x180009084`
- `0x180014720`
- `0x180014ed0`
- `0x180027818`
- `0x18003404c`
- `0x180034120`
- `0x1800346fc`
- `0x18005fcc0`
- `0x18006142c`
- `0x180061cb8`
- `0x18006a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18003422b`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18003438d`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18003422b`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18003438d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800343ba`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800343ba`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180034238`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180034238`
- `ext-ms-win-resources-languageoverlay-l1-1-4!ShouldInstallOverlayPackageDuringLogonForLanguage` at `0x1800342a7`
- `ext-ms-win-resources-languageoverlay-l1-1-4!ShouldInstallOverlayPackageDuringLogonForLanguage` at `0x1800342a7`

## string_xrefs

- `0x1800342bf`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageoverlaylogontask.cpp`
- `0x1800343d2`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageoverlaylogontask.cpp`
- `0x18003445c`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageoverlaylogontask.cpp`
- `0x1800344d3`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageoverlaylogontask.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FetchLanguageOverlayPackageForFirstLogonForUser(
        LanguageOverlayTraceProvider::LogonOverlayBootstrappingForUserActivity *a1,
        __int64 a2)
{
  char *v3; // r14
  __int64 v4; // rax
  __int64 *v5; // rcx
  __int64 v6; // rdx
  _QWORD *v7; // r8
  volatile signed __int32 *v8; // rbx
  _QWORD *v9; // rcx
  int v10; // eax
  unsigned int v11; // r12d
  const char *v12; // r9
  volatile signed __int32 *v13; // rbx
  __int64 result; // rax
  _QWORD *v15; // rbx
  _QWORD *v16; // r8
  HRESULT v17; // eax
  int v18; // r12d
  LPVOID v19; // rcx
  _QWORD *v20; // r8
  int v21; // eax
  LPVOID v22; // rcx
  LPVOID v23; // rcx
  volatile signed __int32 *v24; // rbx
  const unsigned __int16 *v25; // r11
  volatile signed __int32 *v26; // rbx
  volatile signed __int32 *v27; // rbx
  int ppv; // [rsp+20h] [rbp-138h]
  int ppva; // [rsp+20h] [rbp-138h]
  _BYTE v30[4]; // [rsp+60h] [rbp-F8h] BYREF
  unsigned int v31; // [rsp+64h] [rbp-F4h] BYREF
  LPVOID v32; // [rsp+68h] [rbp-F0h] BYREF
  __int128 v33; // [rsp+70h] [rbp-E8h] BYREF
  LanguageOverlayTraceProvider::LogonOverlayBootstrappingForUserActivity *v34; // [rsp+80h] [rbp-D8h]
  __int64 v35; // [rsp+88h] [rbp-D0h]
  char *v36; // [rsp+90h] [rbp-C8h]
  _QWORD v37[3]; // [rsp+98h] [rbp-C0h] BYREF
  unsigned __int64 v38; // [rsp+B0h] [rbp-A8h]
  _QWORD v39[3]; // [rsp+B8h] [rbp-A0h] BYREF
  unsigned __int64 v40; // [rsp+D0h] [rbp-88h]
  unsigned __int16 *v41[4]; // [rsp+D8h] [rbp-80h] BYREF
  _BYTE Src[40]; // [rsp+F8h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+0h]

  try
  {
    v34 = a1;
    v35 = a2;
    v3 = (char *)operator new(0x278u);
    memset_0(v3, 0, 0x278u);
    v36 = v3;
    *((_DWORD *)v3 + 86) = 2;
    *((_DWORD *)v3 + 87) = 2;
    *((_DWORD *)v3 + 88) = 2;
    *((_DWORD *)v3 + 156) = 3;
    *((_DWORD *)v3 + 157) = 1;
    v33 = 0;
    v4 = *(_QWORD *)(a2 + 8);
    if ( v4 )
      _InterlockedIncrement((volatile signed __int32 *)(v4 + 8));
    v5 = *(__int64 **)a2;
    *(_QWORD *)&v33 = v5;
    *((_QWORD *)&v33 + 1) = *(_QWORD *)(a2 + 8);
    v32 = &v33;
    if ( v5 )
      v6 = *v5;
    else
      v6 = 0;
    raii::ImpersonateLoggedOnUser(v30, v6);
    GetUserDefaultUILanguageTag(v37);
    v7 = v37;
    if ( v38 > 7 )
      v7 = (_QWORD *)v37[0];
    _o_wcsncpy_s(v3, 85, v7, -1);
    if ( v30[0] )
      RevertToSelf();
    v8 = (volatile signed __int32 *)*((_QWORD *)&v33 + 1);
    if ( *((_QWORD *)&v33 + 1) )
    {
      if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v33 + 1) + 8LL)) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
        if ( !_InterlockedDecrement(v8 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
      }
    }
    v31 = 0;
    v9 = v37;
    if ( v38 > 7 )
      v9 = (_QWORD *)v37[0];
    v10 = ShouldInstallOverlayPackageDuringLogonForLanguage(v9, &v31, v3);
    v11 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x36,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageoverlaylogontask.cpp",
        (const char *)(unsigned int)v10,
        ppv);
      std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v37);
      operator delete(v3, 0x278u);
      v13 = *(volatile signed __int32 **)(a2 + 8);
      if ( v13 )
      {
        if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
          if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
        }
      }
      return v11;
    }
    if ( !v31 )
    {
LABEL_47:
      std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(
        v41,
        &qword_180070100);
      bcp47::TryConvertLcidToMuiForm(Src);
      if ( Src[32] )
        std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::operator=(
          v41,
          Src);
      v25 = (const unsigned __int16 *)v41;
      if ( v41[3] > (unsigned __int16 *)7 )
        v25 = v41[0];
      LanguageOverlayTraceProvider::LogonOverlayBootstrappingForUserActivity::LogBootstrappingInfo(
        v34,
        *((_DWORD *)v3 + 157),
        (const unsigned __int16 *)v3,
        (const unsigned __int16 *)v3 + 85,
        v25,
        *((_DWORD *)v3 + 86),
        *((_DWORD *)v3 + 87),
        *((_DWORD *)v3 + 88),
        (const struct PACKAGE_VERSION *)(v3 + 356),
        (const unsigned __int16 *)v3 + 182,
        *((_DWORD *)v3 + 156));
      std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(Src);
      std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v41);
      std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v37);
      operator delete(v3, 0x278u);
      v26 = *(volatile signed __int32 **)(a2 + 8);
      if ( v26 )
      {
        if ( _InterlockedExchangeAdd(v26 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v26)(v26);
          if ( _InterlockedExchangeAdd(v26 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
        }
      }
      return 0;
    }
    v15 = v37;
    if ( v38 > 7 )
      v15 = (_QWORD *)v37[0];
    GenerateCorrelationVector(v39);
    v16 = v39;
    if ( v40 > 7 )
      v16 = (_QWORD *)v39[0];
    _o_wcsncpy_s(v3 + 364, 129, v16, -1);
    v32 = 0;
    v17 = CoCreateInstance(
            &GUID_191d3786_5e45_44e2_95d6_15572789ca31,
            0,
            0x17u,
            &GUID_c8ef8e70_fdfc_461d_a470_cc79b97c717d,
            &v32);
    v18 = v17;
    if ( v17 >= 0 )
    {
      v20 = v39;
      if ( v40 > 7 )
        v20 = (_QWORD *)v39[0];
      v21 = (*(__int64 (__fastcall **)(LPVOID, _QWORD *, _QWORD *, __int64))(*(_QWORD *)v32 + 32LL))(v32, v15, v20, 3);
      v18 = v21;
      if ( v21 >= 0 )
      {
        v23 = v32;
        if ( v32 )
        {
          v32 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v23 + 16LL))(v23);
        }
        std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v39);
        v18 = 0;
LABEL_41:
        if ( v18 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3A,
            (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageoverlaylogontask.cpp",
            (const char *)(unsigned int)v18,
            ppva);
          std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v37);
          operator delete(v3, 0x278u);
          v24 = *(volatile signed __int32 **)(a2 + 8);
          if ( v24 )
          {
            if ( _InterlockedExchangeAdd(v24 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
              if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
            }
          }
          return (unsigned int)v18;
        }
        goto LABEL_47;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x24,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageoverlaylogontask.cpp",
        (const char *)(unsigned int)v21,
        ppva);
      v22 = v32;
      if ( v32 )
      {
        v32 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v22 + 16LL))(v22);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1F,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageoverlaylogontask.cpp",
        (const char *)(unsigned int)v17,
        ppva);
      v19 = v32;
      if ( v32 )
      {
        v32 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v19 + 16LL))(v19);
      }
    }
    std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v39);
    goto LABEL_41;
  }
  catch ( ... )
  {
    v31 = wil::details::in1diag3::Return_CaughtException(
            retaddr,
            (void *)0x52,
            (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageoverlaylogontask.cpp",
            v12);
    v27 = *(volatile signed __int32 **)(v35 + 8);
    if ( v27 && _InterlockedExchangeAdd(v27 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
      if ( _InterlockedExchangeAdd(v27 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
    }
    return v31;
  }
  return result;
}

```

## disassembly

```asm
0x180034120  mov     [rsp+arg_10], rbx
0x180034125  push    rdi
0x180034126  push    r12
0x180034128  push    r13
0x18003412a  push    r14
0x18003412c  push    r15
0x18003412e  sub     rsp, 130h
0x180034135  mov     rax, cs:__security_cookie
0x18003413c  xor     rax, rsp
0x18003413f  mov     [rsp+158h+var_38], rax
0x180034147  mov     r15, rdx
0x18003414a  mov     [rsp+158h+var_D8], rcx
0x180034152  mov     [rsp+158h+var_D0], rdx
0x18003415a  mov     r13d, 278h
0x180034160  mov     ecx, r13d; Size
0x180034163  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180034168  mov     r14, rax
0x18003416b  mov     r8d, r13d; Size
0x18003416e  xor     edx, edx; Val
0x180034170  mov     rcx, rax; void *
0x180034173  call    memset_0
0x180034178  mov     [rsp+158h+var_C8], r14
0x180034180  mov     eax, 2
0x180034185  mov     [r14+158h], eax
0x18003418c  mov     [r14+15Ch], eax
0x180034193  mov     [r14+160h], eax
0x18003419a  mov     dword ptr [r14+270h], 3
0x1800341a5  mov     dword ptr [r14+274h], 1
0x1800341b0  xorps   xmm0, xmm0
0x1800341b3  movdqu  [rsp+158h+var_E8], xmm0
0x1800341b9  mov     rax, [r15+8]
0x1800341bd  test    rax, rax
0x1800341c0  jz      short loc_1800341C6
0x1800341c2  lock inc dword ptr [rax+8]
0x1800341c6  mov     rcx, [r15]
0x1800341c9  mov     qword ptr [rsp+158h+var_E8], rcx
0x1800341ce  mov     rax, [r15+8]
0x1800341d2  mov     qword ptr [rsp+158h+var_E8+8], rax
0x1800341d7  lea     rax, [rsp+158h+var_E8]
0x1800341dc  mov     [rsp+158h+var_F0], rax
0x1800341e1  test    rcx, rcx
0x1800341e4  jz      short loc_1800341EB
0x1800341e6  mov     rdx, [rcx]
0x1800341e9  jmp     short loc_1800341ED
0x1800341eb  xor     edx, edx
0x1800341ed  lea     rcx, [rsp+158h+var_F8]
0x1800341f2  call    ?ImpersonateLoggedOnUser@raii@@YA?AV?$unique_call@P6AHXZ$1?RevertToSelf@@YAHXZ$00@wil@@PEAX@Z; raii::ImpersonateLoggedOnUser(void *)
0x1800341f7  lea     rcx, [rsp+158h+var_C0]
0x1800341ff  call    ?GetUserDefaultUILanguageTag@@YA?AV?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@XZ; GetUserDefaultUILanguageTag(void)
0x180034204  lea     r8, [rsp+158h+var_C0]
0x18003420c  cmp     [rsp+158h+var_A8], 7
0x180034215  cmova   r8, [rsp+158h+var_C0]
0x18003421e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180034222  mov     r9, rdi
0x180034225  lea     edx, [rdi+56h]
0x180034228  mov     rcx, r14
0x18003422b  call    cs:__imp__o_wcsncpy_s
0x180034231  cmp     [rsp+158h+var_F8], 0
0x180034236  jz      short loc_18003423F
0x180034238  call    cs:__imp_RevertToSelf
0x18003423e  nop
0x18003423f  mov     rbx, qword ptr [rsp+158h+var_E8+8]
0x180034244  test    rbx, rbx
0x180034247  jz      short loc_18003427D
0x180034249  mov     eax, edi
0x18003424b  lock xadd [rbx+8], eax
0x180034250  add     eax, edi
0x180034252  jnz     short loc_18003427D
0x180034254  mov     rax, [rbx]
0x180034257  mov     rcx, rbx
0x18003425a  mov     rax, [rax]
0x18003425d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034262  mov     eax, edi
0x180034264  lock xadd [rbx+0Ch], eax
0x180034269  add     eax, edi
0x18003426b  jnz     short loc_18003427D
0x18003426d  mov     rax, [rbx]
0x180034270  mov     rcx, rbx
0x180034273  mov     rax, [rax+8]
0x180034277  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003427c  nop
0x18003427d  mov     [rsp+158h+var_F4], 0
0x180034285  lea     rcx, [rsp+158h+var_C0]
0x18003428d  cmp     [rsp+158h+var_A8], 7
0x180034296  cmova   rcx, [rsp+158h+var_C0]
0x18003429f  mov     r8, r14
0x1800342a2  lea     rdx, [rsp+158h+var_F4]
0x1800342a7  call    cs:__imp_ShouldInstallOverlayPackageDuringLogonForLanguage
0x1800342ad  mov     r12d, eax
0x1800342b0  test    eax, eax
0x1800342b2  jns     short loc_18003432F
0x1800342b4  mov     rcx, [rsp+158h]; this
0x1800342bc  mov     r9d, eax; char *
0x1800342bf  lea     r8, aOnecoreBaseLan_13; "onecore\\base\\languageoverlay\\service"...
0x1800342c6  mov     edx, 36h ; '6'; void *
0x1800342cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800342d0  nop
0x1800342d1  lea     rcx, [rsp+158h+var_C0]; void *
0x1800342d9  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x1800342de  nop
0x1800342df  mov     rdx, r13; unsigned __int64
0x1800342e2  mov     rcx, r14; void *
0x1800342e5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800342ea  nop
0x1800342eb  mov     rbx, [r15+8]
0x1800342ef  test    rbx, rbx
0x1800342f2  jz      short loc_180034327
0x1800342f4  mov     eax, edi
0x1800342f6  lock xadd [rbx+8], eax
0x1800342fb  add     eax, edi
0x1800342fd  jnz     short loc_180034327
0x1800342ff  mov     rax, [rbx]
0x180034302  mov     rcx, rbx
0x180034305  mov     rax, [rax]
0x180034308  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003430d  mov     eax, edi
0x18003430f  lock xadd [rbx+0Ch], eax
0x180034314  add     eax, edi
0x180034316  jnz     short loc_180034327
0x180034318  mov     rax, [rbx]
0x18003431b  mov     rcx, rbx
0x18003431e  mov     rax, [rax+8]
0x180034322  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034327  mov     eax, r12d
0x18003432a  jmp     loc_1800346CC
0x18003432f  lea     r13, [r14+16Ch]
0x180034336  cmp     [rsp+158h+var_F4], 0
0x18003433b  jz      loc_180034545
0x180034341  lea     rbx, [rsp+158h+var_C0]
0x180034349  cmp     [rsp+158h+var_A8], 7
0x180034352  cmova   rbx, [rsp+158h+var_C0]
0x18003435b  lea     rcx, [rsp+158h+var_A0]
0x180034363  call    ?GenerateCorrelationVector@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; GenerateCorrelationVector(void)
0x180034368  lea     r8, [rsp+158h+var_A0]
0x180034370  cmp     [rsp+158h+var_88], 7
0x180034379  cmova   r8, [rsp+158h+var_A0]
0x180034382  mov     r9, rdi
0x180034385  mov     edx, 81h
0x18003438a  mov     rcx, r13
0x18003438d  call    cs:__imp__o_wcsncpy_s
0x180034393  mov     [rsp+158h+var_F0], 0
0x18003439c  lea     rax, [rsp+158h+var_F0]
0x1800343a1  mov     [rsp+158h+ppv], rax; int
0x1800343a6  lea     r9, _GUID_c8ef8e70_fdfc_461d_a470_cc79b97c717d; riid
0x1800343ad  xor     edx, edx; pUnkOuter
0x1800343af  lea     r8d, [rdx+17h]; dwClsContext
0x1800343b3  lea     rcx, _GUID_191d3786_5e45_44e2_95d6_15572789ca31; rclsid
0x1800343ba  call    cs:__imp_CoCreateInstance
0x1800343c0  mov     r12d, eax
0x1800343c3  test    eax, eax
0x1800343c5  jns     short loc_180034416
0x1800343c7  mov     rcx, [rsp+158h]; this
0x1800343cf  mov     r9d, eax; char *
0x1800343d2  lea     r8, aOnecoreBaseLan_13; "onecore\\base\\languageoverlay\\service"...
0x1800343d9  mov     edx, 1Fh; void *
0x1800343de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800343e3  nop
0x1800343e4  mov     rcx, [rsp+158h+var_F0]
0x1800343e9  test    rcx, rcx
0x1800343ec  jz      short loc_180034404
0x1800343ee  mov     [rsp+158h+var_F0], 0
0x1800343f7  mov     rax, [rcx]
0x1800343fa  mov     rax, [rax+10h]
0x1800343fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034403  nop
0x180034404  lea     rcx, [rsp+158h+var_A0]; void *
0x18003440c  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180034411  jmp     loc_1800344C3
0x180034416  mov     rcx, [rsp+158h+var_F0]
0x18003441b  mov     rax, [rcx]
0x18003441e  lea     r8, [rsp+158h+var_A0]
0x180034426  cmp     [rsp+158h+var_88], 7
0x18003442f  cmova   r8, [rsp+158h+var_A0]
0x180034438  mov     r9d, 3
0x18003443e  mov     rdx, rbx
0x180034441  mov     rax, [rax+20h]
0x180034445  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003444a  mov     r12d, eax
0x18003444d  test    eax, eax
0x18003444f  jns     short loc_180034493
0x180034451  mov     rcx, [rsp+158h]; this
0x180034459  mov     r9d, eax; char *
0x18003445c  lea     r8, aOnecoreBaseLan_13; "onecore\\base\\languageoverlay\\service"...
0x180034463  mov     edx, 24h ; '$'; void *
0x180034468  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003446d  nop
0x18003446e  mov     rcx, [rsp+158h+var_F0]
0x180034473  test    rcx, rcx
0x180034476  jz      short loc_18003448E
0x180034478  mov     [rsp+158h+var_F0], 0
0x180034481  mov     rax, [rcx]
0x180034484  mov     rax, [rax+10h]
0x180034488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003448d  nop
0x18003448e  jmp     loc_180034404
0x180034493  mov     rcx, [rsp+158h+var_F0]
0x180034498  test    rcx, rcx
0x18003449b  jz      short loc_1800344B3
0x18003449d  mov     [rsp+158h+var_F0], 0
0x1800344a6  mov     rax, [rcx]
0x1800344a9  mov     rax, [rax+10h]
0x1800344ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800344b2  nop
0x1800344b3  lea     rcx, [rsp+158h+var_A0]; void *
0x1800344bb  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x1800344c0  xor     r12d, r12d
0x1800344c3  test    r12d, r12d
0x1800344c6  jns     short loc_180034545
0x1800344c8  mov     rcx, [rsp+158h]; this
0x1800344d0  mov     r9d, r12d; char *
0x1800344d3  lea     r8, aOnecoreBaseLan_13; "onecore\\base\\languageoverlay\\service"...
0x1800344da  mov     edx, 3Ah ; ':'; void *
0x1800344df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800344e4  nop
0x1800344e5  lea     rcx, [rsp+158h+var_C0]; void *
0x1800344ed  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x1800344f2  nop
0x1800344f3  mov     edx, 278h; unsigned __int64
0x1800344f8  mov     rcx, r14; void *
0x1800344fb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180034500  nop
0x180034501  mov     rbx, [r15+8]
0x180034505  test    rbx, rbx
0x180034508  jz      short loc_18003453D
0x18003450a  mov     eax, edi
0x18003450c  lock xadd [rbx+8], eax
0x180034511  add     eax, edi
0x180034513  jnz     short loc_18003453D
0x180034515  mov     rax, [rbx]
0x180034518  mov     rcx, rbx
0x18003451b  mov     rax, [rax]
0x18003451e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034523  mov     ecx, edi
0x180034525  lock xadd [rbx+0Ch], ecx
0x18003452a  add     ecx, edi
0x18003452c  jnz     short loc_18003453D
0x18003452e  mov     rcx, [rbx]
0x180034531  mov     rax, [rcx+8]
0x180034535  mov     rcx, rbx
0x180034538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003453d  mov     eax, r12d
0x180034540  jmp     loc_1800346CC
0x180034545  lea     rdx, qword_180070100
0x18003454c  lea     rcx, [rsp+158h+var_80]
0x180034554  call    ??0?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@QEBG@Z; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(ushort const * const)
0x180034559  movzx   edx, word ptr [r14+154h]
0x180034561  lea     rcx, [rsp+158h+Src]; void *
0x180034569  call    ?TryConvertLcidToMuiForm@bcp47@@YA?AU?$pair@V?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@_N@std@@K@Z; bcp47::TryConvertLcidToMuiForm(ulong)
0x18003456e  cmp     [rsp+158h+var_40], 0
0x180034576  jz      short loc_18003458D
0x180034578  lea     rdx, [rsp+158h+Src]; Src
0x180034580  lea     rcx, [rsp+158h+var_80]; void *
0x180034588  call    ??4?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::operator=(std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>> &&)
0x18003458d  lea     r9, [r14+0AAh]; unsigned __int16 *
0x180034594  lea     rbx, [r14+164h]
0x18003459b  mov     eax, [r14+270h]
0x1800345a2  mov     edx, [r14+160h]
0x1800345a9  mov     r8d, [r14+15Ch]
0x1800345b0  mov     r10d, [r14+158h]
0x1800345b7  lea     r11, [rsp+158h+var_80]
0x1800345bf  cmp     [rsp+158h+var_68], 7
0x1800345c8  cmova   r11, [rsp+158h+var_80]
0x1800345d1  mov     [rsp+158h+var_108], eax; int
0x1800345d5  mov     [rsp+158h+var_110], r13; unsigned __int16 *
0x1800345da  mov     [rsp+158h+var_118], rbx; struct PACKAGE_VERSION *
0x1800345df  mov     [rsp+158h+var_120], edx; int
0x1800345e3  mov     [rsp+158h+var_128], r8d; int
0x1800345e8  mov     [rsp+158h+var_130], r10d; int
0x1800345ed  mov     [rsp+158h+ppv], r11; unsigned __int16 *
0x1800345f2  mov     r8, r14; unsigned __int16 *
0x1800345f5  mov     edx, [r14+274h]; int
0x1800345fc  mov     rcx, [rsp+158h+var_D8]; this
0x180034604  call    ?LogBootstrappingInfo@LogonOverlayBootstrappingForUserActivity@LanguageOverlayTraceProvider@@QEBAXHPEBG00HHHAEBUPACKAGE_VERSION@@0H@Z; LanguageOverlayTraceProvider::LogonOverlayBootstrappingForUserActivity::LogBootstrappingInfo(int,ushort const *,ushort const *,ushort const *,int,int,int,PACKAGE_VERSION const &,ushort const *,int)
0x180034609  lea     rcx, [rsp+158h+Src]; void *
0x180034611  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180034616  lea     rcx, [rsp+158h+var_80]; void *
0x18003461e  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180034623  nop
0x180034624  lea     rcx, [rsp+158h+var_C0]; void *
0x18003462c  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180034631  nop
0x180034632  mov     edx, 278h; unsigned __int64
0x180034637  mov     rcx, r14; void *
0x18003463a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003463f  nop
0x180034640  mov     rbx, [r15+8]
0x180034644  test    rbx, rbx
0x180034647  jz      short loc_18003467C
0x180034649  mov     eax, edi
0x18003464b  lock xadd [rbx+8], eax
0x180034650  add     eax, edi
0x180034652  jnz     short loc_18003467C
0x180034654  mov     rax, [rbx]
0x180034657  mov     rcx, rbx
0x18003465a  mov     rax, [rax]
0x18003465d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034662  mov     eax, edi
0x180034664  lock xadd [rbx+0Ch], eax
0x180034669  add     eax, edi
0x18003466b  jnz     short loc_18003467C
  ... truncated ...
```
