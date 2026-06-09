# CodeIntegrity::Management::detail::LoadTokens(void)

- ea: `0x18001c714`
- end: `0x18001cb8a`
- name: `?LoadTokens@detail@Management@CodeIntegrity@@YA?AV?$unique_ptr@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@@2@@std@@U?$default_delete@V?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@@2@@std@@@2@@std@@XZ`
- size: `1142`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `33`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180014ee0`

## callees

- `0x180002a90`
- `0x180002ab4`
- `0x180002e84`
- `0x18000303c`
- `0x1800030a4`
- `0x180004a98`
- `0x180005494`
- `0x180008474`
- `0x18000a2c0`
- `0x18000d470`
- `0x180010cdc`
- `0x1800110a0`
- `0x1800159fc`
- `0x180015a54`
- `0x180018834`
- `0x1800196c0`
- `0x180019728`
- `0x18001a094`
- `0x18001a1a4`
- `0x18001a990`
- `0x18001b524`
- `0x18001b574`
- `0x18001b9a8`
- `0x18001b9c0`
- `0x18001bc48`
- `0x18001bdc0`
- `0x18001be74`
- `0x18001c3cc`
- `0x18001c714`
- `0x18001d404`
- `0x18001d438`
- `0x180020e20`
- `0x180022a30`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cad8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cb33`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cb49`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cad8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cb33`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cb49`

## string_xrefs

- `0x18001c7aa`: `onecore\base\ci\management\dll\tokenmgmt.cpp`
- `0x18001c82d`: `onecore\base\ci\management\dll\tokenmgmt.cpp`
- `0x18001cb78`: `onecore\base\ci\management\dll\tokenmgmt.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 **__fastcall CodeIntegrity::Management::detail::LoadTokens(__int64 **a1)
{
  __int64 *v2; // rbx
  int v3; // r12d
  int v4; // edx
  int v5; // ecx
  int v6; // eax
  __int64 v7; // rax
  int v8; // edx
  int v9; // eax
  unsigned int v10; // esi
  _DWORD *v11; // r14
  int v12; // eax
  int v13; // edx
  char v14; // bl
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rdx
  __int64 v19; // rax
  _QWORD *v20; // r10
  int v21; // eax
  __int64 *v22; // rbx
  __int64 v23; // rax
  _QWORD *v24; // rbx
  __int64 AuthorizationToken; // rax
  HLOCAL v26; // rcx
  HLOCAL v27; // rcx
  HLOCAL v28; // rcx
  int v30; // [rsp+20h] [rbp-E0h]
  int v31; // [rsp+20h] [rbp-E0h]
  int v32; // [rsp+20h] [rbp-E0h]
  int v33; // [rsp+40h] [rbp-C0h] BYREF
  int v34; // [rsp+44h] [rbp-BCh]
  HLOCAL v35; // [rsp+48h] [rbp-B8h] BYREF
  HLOCAL v36; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-A8h] BYREF
  __int64 *v38; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v39; // [rsp+68h] [rbp-98h] BYREF
  _QWORD *v40[2]; // [rsp+70h] [rbp-90h] BYREF
  HLOCAL *p_hMem; // [rsp+80h] [rbp-80h] BYREF
  __int64 v42; // [rsp+88h] [rbp-78h] BYREF
  char v43; // [rsp+90h] [rbp-70h]
  __int64 v44; // [rsp+A0h] [rbp-60h] BYREF
  char v45; // [rsp+A8h] [rbp-58h]
  _QWORD *v46[5]; // [rsp+B0h] [rbp-50h] BYREF
  char v47; // [rsp+D8h] [rbp-28h]
  __int128 v48; // [rsp+E0h] [rbp-20h]
  char v49; // [rsp+F0h] [rbp-10h]
  __int64 v50; // [rsp+F8h] [rbp-8h]
  __int64 v51; // [rsp+100h] [rbp+0h]
  char v52; // [rsp+108h] [rbp+8h]
  __int64 **v53; // [rsp+110h] [rbp+10h]
  __int64 v54; // [rsp+118h] [rbp+18h] BYREF
  char v55[16]; // [rsp+120h] [rbp+20h] BYREF
  char v56[16]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v57[32]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v58[32]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v59[32]; // [rsp+180h] [rbp+80h] BYREF
  void *v60[34]; // [rsp+1A0h] [rbp+A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+208h]

  v53 = a1;
  v2 = (__int64 *)operator new(0x10u);
  v38 = v2;
  *v2 = 0;
  v2[1] = 0;
  std::_Tree<std::_Tmap_traits<std::wstring,std::set<CodeIntegrity::Management::AuthorizationToken>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>>,0>>::_Alloc_sentinel_and_proxy(v2);
  *a1 = v2;
  v3 = 3;
  v34 = 3;
  v33 = 0;
  v6 = SIPolicyPmEnumerateTokens(v5, v4, 0, 0, 0, (__int64)&v33);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x26,
      (int)"onecore\\base\\ci\\management\\dll\\tokenmgmt.cpp",
      (const char *)(unsigned int)v6,
      v30);
  CodeIntegrity::make_unique_si_ptr<unsigned short * [0]>(&v36);
  CodeIntegrity::make_unique_si_ptr<_SIPOLICY_FILE_ITEM [0]>(&v35);
  v7 = lambda_e1cafc5aced2217f935c41e2dd6f7f30_::_lambda_e1cafc5aced2217f935c41e2dd6f7f30_(&p_hMem, &v33, &v36, &v35);
  wil::ScopeExit__lambda_e1cafc5aced2217f935c41e2dd6f7f30___(v57, v7);
  v9 = SIPolicyPmEnumerateTokens((unsigned int)&v33, v8, (_DWORD)v35, (_DWORD)v36, v33, (__int64)&v33);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x3B,
      (int)"onecore\\base\\ci\\management\\dll\\tokenmgmt.cpp",
      (const char *)(unsigned int)v9,
      v31);
  if ( v33 )
  {
    v10 = 0;
    v11 = (_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL);
    do
    {
      if ( dword_180039848 > *v11 )
      {
        Init_thread_header(&dword_180039848);
        if ( dword_180039848 == -1 )
        {
          std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::basic_regex<unsigned short,std::regex_traits<unsigned short>>();
          atexit(CodeIntegrity::Management::detail::LoadTokens_::_5_::_dynamic_atexit_destructor_for__tokenNameRegex__);
          Init_thread_footer(&dword_180039848);
        }
      }
      v44 = 0;
      v45 = 0;
      std::vector<_GUID>::vector<_GUID>(v46);
      v46[3] = 0;
      v46[4] = 0;
      v47 = 0;
      v48 = 0;
      v49 = 0;
      v50 = 0;
      v51 = 0;
      v52 = 0;
      v12 = std::_WChar_traits<unsigned short>::length(*((_QWORD *)v36 + v10));
      if ( *(_QWORD *)&qword_180039850 )
      {
        std::_Matcher2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>,unsigned short const *,void>::_Matcher2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>,unsigned short const *,void>(
          (unsigned int)v60,
          v13,
          v13 + 2 * v12,
          (unsigned int)&qword_180039858,
          *(__int64 *)&qword_180039850,
          *(_DWORD *)(*(_QWORD *)&qword_180039850 + 40LL),
          *(_DWORD *)(*(_QWORD *)&qword_180039850 + 32LL));
        v14 = std::_Matcher2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>,unsigned short const *,void>::_Match<std::allocator<std::sub_match<unsigned short const *>>>(
                v60,
                &v44);
        std::_Matcher2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>,unsigned short const *,void>::~_Matcher2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>,unsigned short const *,void>(v60);
        if ( v14 )
        {
          hMem = 0;
          v38 = 0;
          v15 = std::match_results<unsigned short const *>::operator[](&v44, 1);
          if ( *(_BYTE *)(v15 + 16) )
          {
            v16 = *(_QWORD *)v15;
            v17 = *(_QWORD *)(v15 + 8);
          }
          else
          {
            v16 = 0;
            v17 = 0;
          }
          std::wstring::wstring(v58, v16, v17);
          v3 |= 0x10u;
          v34 = v3;
          std::match_results<unsigned short const *>::operator[](&v44, 2);
          v19 = std::match_results<unsigned short const *>::operator[](&v44, v18);
          std::wstring::wstring(v59, *v20, *(_QWORD *)(v19 + 8));
          p_hMem = &hMem;
          v42 = 0;
          v43 = 1;
          v21 = SIPolicyPmReadPolicy(3LL * v10, (struct _UNICODE_STRING *)((char *)v35 + 24 * v10), &v42, (ULONG *)&v38);
          if ( v21 < 0 )
            wil::details::in1diag3::_Throw_NtStatus(
              retaddr,
              (void *)0x4F,
              (int)"onecore\\base\\ci\\management\\dll\\tokenmgmt.cpp",
              (const char *)(unsigned int)v21,
              v32);
          wil::details::out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void SIPolicyFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void SIPolicyFree(void *)>>>((__int64)&p_hMem);
          std::_Tree<std::_Tmap_traits<std::wstring,std::set<CodeIntegrity::Management::AuthorizationToken>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>>,0>>::find(
            *a1,
            &v39,
            (__int64)v58);
          v22 = *a1;
          v23 = v39;
          if ( v39 == **a1 )
          {
            v40[0] = 0;
            v40[1] = 0;
            std::_Tree<std::_Tset_traits<CodeIntegrity::Management::AuthorizationToken,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationToken>,0>>::_Alloc_sentinel_and_proxy(v40);
            std::_Tree<std::_Tmap_traits<std::wstring,std::set<CodeIntegrity::Management::AuthorizationToken>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>>,0>>::_Emplace<std::wstring &,std::set<CodeIntegrity::Management::AuthorizationToken>>(
              v22,
              (__int64)v55,
              (__int64)v58,
              (__int64)v40);
            std::_Tree<std::_Tset_traits<CodeIntegrity::Management::AuthorizationToken,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationToken>,0>>::~_Tree<std::_Tset_traits<CodeIntegrity::Management::AuthorizationToken,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationToken>,0>>(v40);
            v23 = *std::_Tree<std::_Tmap_traits<std::wstring,std::set<CodeIntegrity::Management::AuthorizationToken>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>>,0>>::find(
                     *a1,
                     &v54,
                     (__int64)v58);
            v39 = v23;
          }
          v24 = (_QWORD *)(v23 + 64);
          AuthorizationToken = CodeIntegrity::Management::AuthorizationToken::CreateAuthorizationToken(
                                 (__int64)v60,
                                 (__int64)v58,
                                 (__int64)v59,
                                 (__int64)hMem,
                                 (__int64)v38);
          std::_Tree<std::_Tset_traits<CodeIntegrity::Management::AuthorizationToken,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationToken>,0>>::_Emplace<CodeIntegrity::Management::AuthorizationToken>(
            v24,
            (__int64)v56,
            AuthorizationToken);
          CodeIntegrity::Management::AuthorizationToken::~AuthorizationToken(v60);
          std::wstring::_Tidy_deallocate((__int64)v59);
          std::wstring::_Tidy_deallocate((__int64)v58);
          v26 = hMem;
          hMem = 0;
          if ( v26 )
            LocalFree(v26);
        }
      }
      if ( v46[0] )
        std::_Deallocate<16>(v46[0], 8 * (v46[2] - v46[0]));
      ++v10;
    }
    while ( v10 < v33 );
  }
  wil::details::ScopeExitFn__lambda_e1cafc5aced2217f935c41e2dd6f7f30___::_ScopeExitFn__lambda_e1cafc5aced2217f935c41e2dd6f7f30___(v57);
  v27 = v35;
  v35 = 0;
  if ( v27 )
    LocalFree(v27);
  v28 = v36;
  v36 = 0;
  if ( v28 )
    LocalFree(v28);
  return a1;
}

```

## disassembly

```asm
0x18001c714  push    rbp
0x18001c716  push    rbx
0x18001c717  push    rsi
0x18001c718  push    rdi
0x18001c719  push    r12
0x18001c71b  push    r13
0x18001c71d  push    r14
0x18001c71f  push    r15
0x18001c721  lea     rbp, [rsp-1C8h]
0x18001c729  sub     rsp, 2C8h
0x18001c730  mov     rax, cs:__security_cookie
0x18001c737  xor     rax, rsp
0x18001c73a  mov     [rbp+200h+var_50], rax
0x18001c741  mov     rdi, rcx
0x18001c744  mov     [rbp+200h+var_1F0], rcx
0x18001c748  xor     r13d, r13d
0x18001c74b  mov     [rsp+300h+var_2BC], r13d
0x18001c750  lea     ecx, [r13+10h]; Size
0x18001c754  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c759  mov     rbx, rax
0x18001c75c  mov     [rsp+300h+var_2A0], rax
0x18001c761  mov     [rax], r13
0x18001c764  mov     [rax+8], r13
0x18001c768  mov     rcx, rax
0x18001c76b  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,std::set<CodeIntegrity::Management::AuthorizationToken>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>>,0>>::_Alloc_sentinel_and_proxy(void)
0x18001c770  nop
0x18001c771  mov     [rdi], rbx
0x18001c774  lea     r12d, [r13+3]
0x18001c778  mov     [rsp+300h+var_2BC], r12d
0x18001c77d  mov     [rsp+300h+var_2C0], r13d
0x18001c782  lea     rax, [rsp+300h+var_2C0]
0x18001c787  mov     [rsp+300h+var_2D8], rax
0x18001c78c  mov     [rsp+300h+var_2E0], r13d; int
0x18001c791  xor     r9d, r9d
0x18001c794  xor     r8d, r8d
0x18001c797  call    SIPolicyPmEnumerateTokens
0x18001c79c  mov     rcx, [rbp+208h]; this
0x18001c7a3  test    eax, eax
0x18001c7a5  jns     short loc_18001C7BB
0x18001c7a7  mov     r9d, eax; char *
0x18001c7aa  lea     r8, aOnecoreBaseCiM_4; "onecore\\base\\ci\\management\\dll\\tok"...
0x18001c7b1  lea     edx, [r13+26h]; void *
0x18001c7b5  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18001c7bb  mov     edx, [rsp+300h+var_2C0]
0x18001c7bf  lea     rcx, [rsp+300h+var_2B0]
0x18001c7c4  call    ??$make_unique_si_ptr@$$BY0A@PEAG@CodeIntegrity@@YA?AV?$unique_ptr@$$BY0A@PEAGU?$function_deleter@P6AXPEAX@Z$1?SIPolicyFree@@YAX0@Z@wil@@@wistd@@_K@Z; CodeIntegrity::make_unique_si_ptr<ushort * [0]>(unsigned __int64)
0x18001c7c9  nop
0x18001c7ca  mov     edx, [rsp+300h+var_2C0]
0x18001c7ce  lea     rcx, [rsp+300h+var_2B8]
0x18001c7d3  call    ??$make_unique_si_ptr@$$BY0A@U_SIPOLICY_FILE_ITEM@@@CodeIntegrity@@YA?AV?$unique_ptr@$$BY0A@U_SIPOLICY_FILE_ITEM@@U?$function_deleter@P6AXPEAX@Z$1?SIPolicyFree@@YAX0@Z@wil@@@wistd@@_K@Z; CodeIntegrity::make_unique_si_ptr<_SIPOLICY_FILE_ITEM [0]>(unsigned __int64)
0x18001c7d8  nop
0x18001c7d9  lea     r9, [rsp+300h+var_2B8]
0x18001c7de  lea     r8, [rsp+300h+var_2B0]
0x18001c7e3  lea     rdx, [rsp+300h+var_2C0]
0x18001c7e8  lea     rcx, [rbp+200h+var_280]
0x18001c7ec  call    _lambda_e1cafc5aced2217f935c41e2dd6f7f30____lambda_e1cafc5aced2217f935c41e2dd6f7f30_
0x18001c7f1  mov     rdx, rax
0x18001c7f4  lea     rcx, [rbp+200h+var_1C0]
0x18001c7f8  call    wil__ScopeExit__lambda_e1cafc5aced2217f935c41e2dd6f7f30___
0x18001c7fd  nop
0x18001c7fe  mov     eax, [rsp+300h+var_2C0]
0x18001c802  lea     rcx, [rsp+300h+var_2C0]
0x18001c807  mov     [rsp+300h+var_2D8], rcx
0x18001c80c  mov     [rsp+300h+var_2E0], eax; int
0x18001c810  mov     r9, [rsp+300h+var_2B0]
0x18001c815  mov     r8, [rsp+300h+var_2B8]
0x18001c81a  call    SIPolicyPmEnumerateTokens
0x18001c81f  test    eax, eax
0x18001c821  jns     short loc_18001C83F
0x18001c823  mov     rcx, [rbp+208h]; this
0x18001c82a  mov     r9d, eax; char *
0x18001c82d  lea     r8, aOnecoreBaseCiM_4; "onecore\\base\\ci\\management\\dll\\tok"...
0x18001c834  mov     edx, 3Bh ; ';'; void *
0x18001c839  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18001c83f  cmp     [rsp+300h+var_2C0], r13d
0x18001c844  jbe     loc_18001CB1A
0x18001c84a  mov     esi, r13d
0x18001c84d  mov     ecx, cs:_tls_index
0x18001c853  mov     rax, gs:58h
0x18001c85c  mov     r14d, 4
0x18001c862  add     r14, [rax+rcx*8]
0x18001c866  mov     eax, [r14]
0x18001c869  cmp     cs:dword_180039848, eax
0x18001c86f  jle     short loc_18001C8A4
0x18001c871  lea     rcx, dword_180039848
0x18001c878  call    _Init_thread_header
0x18001c87d  cmp     cs:dword_180039848, 0FFFFFFFFh
0x18001c884  jnz     short loc_18001C8A4
0x18001c886  call    ??0?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@PEBGW4syntax_option_type@regex_constants@1@@Z; std::basic_regex<ushort,std::regex_traits<ushort>>::basic_regex<ushort,std::regex_traits<ushort>>(ushort const *,std::regex_constants::syntax_option_type)
0x18001c88b  lea     rcx, _CodeIntegrity__Management__detail__LoadTokens____5____dynamic_atexit_destructor_for__tokenNameRegex__; void (__cdecl *)()
0x18001c892  call    atexit
0x18001c897  nop
0x18001c898  lea     rcx, dword_180039848
0x18001c89f  call    _Init_thread_footer
0x18001c8a4  mov     [rbp+200h+var_260], r13
0x18001c8a8  mov     [rbp+200h+var_258], r13b
0x18001c8ac  lea     rcx, [rbp+200h+var_250]
0x18001c8b0  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x18001c8b5  mov     [rbp+200h+var_238], r13
0x18001c8b9  mov     [rbp+200h+var_230], r13
0x18001c8bd  mov     [rbp+200h+var_228], r13b
0x18001c8c1  xorps   xmm0, xmm0
0x18001c8c4  movdqa  [rbp+200h+var_220], xmm0
0x18001c8c9  mov     [rbp+200h+var_210], r13b
0x18001c8cd  mov     [rbp+200h+var_208], r13
0x18001c8d1  mov     [rbp+200h+var_200], r13
0x18001c8d5  mov     [rbp+200h+var_1F8], r13b
0x18001c8d9  mov     r15d, esi
0x18001c8dc  mov     rax, [rsp+300h+var_2B0]
0x18001c8e1  mov     rdx, [rax+r15*8]
0x18001c8e5  mov     rcx, rdx
0x18001c8e8  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001c8ed  mov     rcx, cs:qword_180039850
0x18001c8f4  test    rcx, rcx
0x18001c8f7  jz      loc_18001CADF
0x18001c8fd  lea     r8, [rdx+rax*2]
0x18001c901  mov     eax, [rcx+20h]
0x18001c904  mov     [rsp+300h+var_2D0], eax
0x18001c908  mov     eax, [rcx+28h]
0x18001c90b  mov     dword ptr [rsp+300h+var_2D8], eax
0x18001c90f  mov     qword ptr [rsp+300h+var_2E0], rcx; int
0x18001c914  lea     r9, qword_180039858
0x18001c91b  lea     rcx, [rbp+200h+var_160]
0x18001c922  call    ??0?$_Matcher2@PEBGGV?$regex_traits@G@std@@PEBGX@std@@QEAA@PEBG0AEBV?$regex_traits@G@1@PEAV_Root_node@1@IW4syntax_option_type@regex_constants@1@W4match_flag_type@51@@Z; std::_Matcher2<ushort const *,ushort,std::regex_traits<ushort>,ushort const *,void>::_Matcher2<ushort const *,ushort,std::regex_traits<ushort>,ushort const *,void>(ushort const *,ushort const *,std::regex_traits<ushort> const &,std::_Root_node *,uint,std::regex_constants::syntax_option_type,std::regex_constants::match_flag_type)
0x18001c927  nop
0x18001c928  lea     rdx, [rbp+200h+var_260]
0x18001c92c  lea     rcx, [rbp+200h+var_160]
0x18001c933  call    ??$_Match@V?$allocator@V?$sub_match@PEBG@std@@@std@@@?$_Matcher2@PEBGGV?$regex_traits@G@std@@PEBGX@std@@QEAA_NPEAV?$match_results@PEBGV?$allocator@V?$sub_match@PEBG@std@@@std@@@1@_N@Z; std::_Matcher2<ushort const *,ushort,std::regex_traits<ushort>,ushort const *,void>::_Match<std::allocator<std::sub_match<ushort const *>>>(std::match_results<ushort const *> *,bool)
0x18001c938  mov     bl, al
0x18001c93a  lea     rcx, [rbp+200h+var_160]
0x18001c941  call    ??1?$_Matcher2@PEBGGV?$regex_traits@G@std@@PEBGX@std@@QEAA@XZ; std::_Matcher2<ushort const *,ushort,std::regex_traits<ushort>,ushort const *,void>::~_Matcher2<ushort const *,ushort,std::regex_traits<ushort>,ushort const *,void>(void)
0x18001c946  test    bl, bl
0x18001c948  jz      loc_18001CADF
0x18001c94e  mov     [rsp+300h+hMem], r13
0x18001c953  mov     [rsp+300h+var_2A0], r13
0x18001c958  mov     edx, 1
0x18001c95d  lea     rcx, [rbp+200h+var_260]
0x18001c961  call    ??A?$match_results@PEBGV?$allocator@V?$sub_match@PEBG@std@@@std@@@std@@QEBAAEBV?$sub_match@PEBG@1@_K@Z; std::match_results<ushort const *>::operator[](unsigned __int64)
0x18001c966  cmp     [rax+10h], r13b
0x18001c96a  jz      short loc_18001C975
0x18001c96c  mov     rdx, [rax]
0x18001c96f  mov     r8, [rax+8]
0x18001c973  jmp     short loc_18001C97B
0x18001c975  mov     rdx, r13
0x18001c978  mov     r8, r13
0x18001c97b  lea     rcx, [rbp+200h+var_1A0]
0x18001c97f  call    ??$?0PEBG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort const *,ushort const *,std::allocator<ushort> const &)
0x18001c984  or      r12d, 10h
0x18001c988  mov     [rsp+300h+var_2BC], r12d
0x18001c98d  mov     edx, 2
0x18001c992  lea     rcx, [rbp+200h+var_260]
0x18001c996  call    ??A?$match_results@PEBGV?$allocator@V?$sub_match@PEBG@std@@@std@@@std@@QEBAAEBV?$sub_match@PEBG@1@_K@Z; std::match_results<ushort const *>::operator[](unsigned __int64)
0x18001c99b  mov     r10, rax
0x18001c99e  lea     rcx, [rbp+200h+var_260]
0x18001c9a2  call    ??A?$match_results@PEBGV?$allocator@V?$sub_match@PEBG@std@@@std@@@std@@QEBAAEBV?$sub_match@PEBG@1@_K@Z; std::match_results<ushort const *>::operator[](unsigned __int64)
0x18001c9a7  mov     r8, [rax+8]
0x18001c9ab  mov     rdx, [r10]
0x18001c9ae  lea     rcx, [rbp+200h+var_180]
0x18001c9b5  call    ??$?0PEBG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort const *,ushort const *,std::allocator<ushort> const &)
0x18001c9ba  nop
0x18001c9bb  lea     rax, [rsp+300h+hMem]
0x18001c9c0  mov     [rbp+200h+var_280], rax
0x18001c9c4  mov     [rbp+200h+var_278], r13
0x18001c9c8  mov     [rbp+200h+var_270], 1
0x18001c9cc  lea     rcx, [r15+r15*2]
0x18001c9d0  mov     rax, [rsp+300h+var_2B8]
0x18001c9d5  lea     rdx, [rax+rcx*8]
0x18001c9d9  lea     r9, [rsp+300h+var_2A0]
0x18001c9de  lea     r8, [rbp+200h+var_278]
0x18001c9e2  call    SIPolicyPmReadPolicy
0x18001c9e7  mov     rcx, [rbp+208h]; this
0x18001c9ee  test    eax, eax
0x18001c9f0  js      loc_18001CB75
0x18001c9f6  lea     rcx, [rbp+200h+var_280]
0x18001c9fa  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?SIPolicyFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&SIPolicyFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&SIPolicyFree(void *)>>>(void)
0x18001c9ff  lea     r8, [rbp+200h+var_1A0]
0x18001ca03  lea     rdx, [rsp+300h+var_298]
0x18001ca08  mov     rcx, [rdi]
0x18001ca0b  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::set<CodeIntegrity::Management::AuthorizationToken>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>>,0>>::find(std::wstring const &)
0x18001ca10  mov     rbx, [rdi]
0x18001ca13  mov     rax, [rsp+300h+var_298]
0x18001ca18  cmp     rax, [rbx]
0x18001ca1b  jnz     short loc_18001CA6A
0x18001ca1d  mov     [rsp+300h+var_290], r13
0x18001ca22  mov     [rsp+300h+var_288], r13
0x18001ca27  lea     rcx, [rsp+300h+var_290]
0x18001ca2c  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tset_traits@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tset_traits<CodeIntegrity::Management::AuthorizationToken,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationToken>,0>>::_Alloc_sentinel_and_proxy(void)
0x18001ca31  nop
0x18001ca32  lea     r9, [rsp+300h+var_290]
0x18001ca37  lea     r8, [rbp+200h+var_1A0]
0x18001ca3b  lea     rdx, [rbp+200h+var_1E0]
0x18001ca3f  mov     rcx, rbx
0x18001ca42  call    ??$_Emplace@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@PEAX@std@@_N@1@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::set<CodeIntegrity::Management::AuthorizationToken>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>>,0>>::_Emplace<std::wstring &,std::set<CodeIntegrity::Management::AuthorizationToken>>(std::wstring &,std::set<CodeIntegrity::Management::AuthorizationToken> &&)
0x18001ca47  nop
0x18001ca48  lea     rcx, [rsp+300h+var_290]
0x18001ca4d  call    ??1?$_Tree@V?$_Tset_traits@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<CodeIntegrity::Management::AuthorizationToken,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationToken>,0>>::~_Tree<std::_Tset_traits<CodeIntegrity::Management::AuthorizationToken,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationToken>,0>>(void)
0x18001ca52  lea     r8, [rbp+200h+var_1A0]
0x18001ca56  lea     rdx, [rbp+200h+var_1E8]
0x18001ca5a  mov     rcx, [rdi]
0x18001ca5d  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::set<CodeIntegrity::Management::AuthorizationToken>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::set<CodeIntegrity::Management::AuthorizationToken>>>,0>>::find(std::wstring const &)
0x18001ca62  mov     rax, [rax]
0x18001ca65  mov     [rsp+300h+var_298], rax
0x18001ca6a  lea     rbx, [rax+40h]
0x18001ca6e  mov     rax, [rsp+300h+var_2A0]
0x18001ca73  mov     qword ptr [rsp+300h+var_2E0], rax
0x18001ca78  mov     r9, [rsp+300h+hMem]
0x18001ca7d  lea     r8, [rbp+200h+var_180]
0x18001ca84  lea     rdx, [rbp+200h+var_1A0]
0x18001ca88  lea     rcx, [rbp+200h+var_160]
0x18001ca8f  call    ?CreateAuthorizationToken@AuthorizationToken@Management@CodeIntegrity@@SA?AV123@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0PEBE_K@Z; CodeIntegrity::Management::AuthorizationToken::CreateAuthorizationToken(std::wstring const &,std::wstring const &,uchar const *,unsigned __int64)
0x18001ca94  nop
0x18001ca95  mov     r8, rax
0x18001ca98  lea     rdx, [rbp+200h+var_1D0]
0x18001ca9c  mov     rcx, rbx
0x18001ca9f  call    ??$_Emplace@VAuthorizationToken@Management@CodeIntegrity@@@?$_Tree@V?$_Tset_traits@VAuthorizationToken@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@VAuthorizationToken@Management@CodeIntegrity@@@5@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@VAuthorizationToken@Management@CodeIntegrity@@PEAX@std@@_N@1@$$QEAVAuthorizationToken@Management@CodeIntegrity@@@Z; std::_Tree<std::_Tset_traits<CodeIntegrity::Management::AuthorizationToken,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationToken>,0>>::_Emplace<CodeIntegrity::Management::AuthorizationToken>(CodeIntegrity::Management::AuthorizationToken &&)
0x18001caa4  nop
0x18001caa5  lea     rcx, [rbp+200h+var_160]; this
0x18001caac  call    ??1AuthorizationToken@Management@CodeIntegrity@@QEAA@XZ; CodeIntegrity::Management::AuthorizationToken::~AuthorizationToken(void)
0x18001cab1  nop
0x18001cab2  lea     rcx, [rbp+200h+var_180]
0x18001cab9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001cabe  nop
0x18001cabf  lea     rcx, [rbp+200h+var_1A0]
0x18001cac3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001cac8  nop
0x18001cac9  mov     rcx, [rsp+300h+hMem]; hMem
0x18001cace  mov     [rsp+300h+hMem], r13
0x18001cad3  test    rcx, rcx
0x18001cad6  jz      short loc_18001CADF
0x18001cad8  call    cs:__imp_LocalFree
0x18001cade  nop
0x18001cadf  mov     rcx, [rbp+200h+var_250]
0x18001cae3  test    rcx, rcx
0x18001cae6  jz      short loc_18001CB0E
0x18001cae8  mov     rax, [rbp+200h+var_240]
0x18001caec  sub     rax, rcx
0x18001caef  sar     rax, 3
0x18001caf3  mov     rdx, 0AAAAAAAAAAAAAAABh
0x18001cafd  imul    rax, rdx
0x18001cb01  lea     rdx, [rax+rax*2]
0x18001cb05  shl     rdx, 3
0x18001cb09  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001cb0e  inc     esi
0x18001cb10  cmp     esi, [rsp+300h+var_2C0]
0x18001cb14  jb      loc_18001C866
0x18001cb1a  lea     rcx, [rbp+200h+var_1C0]
0x18001cb1e  call    wil__details__ScopeExitFn__lambda_e1cafc5aced2217f935c41e2dd6f7f30______ScopeExitFn__lambda_e1cafc5aced2217f935c41e2dd6f7f30___
0x18001cb23  nop
0x18001cb24  mov     rcx, [rsp+300h+var_2B8]; hMem
0x18001cb29  mov     [rsp+300h+var_2B8], r13
0x18001cb2e  test    rcx, rcx
0x18001cb31  jz      short loc_18001CB3A
0x18001cb33  call    cs:__imp_LocalFree
0x18001cb39  nop
0x18001cb3a  mov     rcx, [rsp+300h+var_2B0]; hMem
0x18001cb3f  mov     [rsp+300h+var_2B0], r13
0x18001cb44  test    rcx, rcx
0x18001cb47  jz      short loc_18001CB4F
0x18001cb49  call    cs:__imp_LocalFree
0x18001cb4f  mov     rax, rdi
0x18001cb52  mov     rcx, [rbp+200h+var_50]
0x18001cb59  xor     rcx, rsp; StackCookie
0x18001cb5c  call    __security_check_cookie
0x18001cb61  add     rsp, 2C8h
0x18001cb68  pop     r15
0x18001cb6a  pop     r14
0x18001cb6c  pop     r13
0x18001cb6e  pop     r12
0x18001cb70  pop     rdi
0x18001cb71  pop     rsi
0x18001cb72  pop     rbx
0x18001cb73  pop     rbp
0x18001cb74  retn
0x18001cb75  mov     r9d, eax; char *
0x18001cb78  lea     r8, aOnecoreBaseCiM_4; "onecore\\base\\ci\\management\\dll\\tok"...
0x18001cb7f  mov     edx, 4Fh ; 'O'; void *
0x18001cb84  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
```
