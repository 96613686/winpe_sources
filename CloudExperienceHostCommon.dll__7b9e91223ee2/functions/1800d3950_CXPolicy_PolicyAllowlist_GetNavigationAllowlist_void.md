# CXPolicy::PolicyAllowlist::GetNavigationAllowlist(void)

- ea: `0x1800d3950`
- end: `0x1800d3b99`
- name: `?GetNavigationAllowlist@PolicyAllowlist@CXPolicy@@UEAA?BV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ`
- size: `585`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800d7de0`

## callees

- `0x1800052ac`
- `0x180010c8c`
- `0x1800128e8`
- `0x1800135ec`
- `0x180016634`
- `0x18001a540`
- `0x18001b838`
- `0x18001c8a0`
- `0x1800227ac`
- `0x1800cc2f4`
- `0x1800cc47c`
- `0x1800cc618`
- `0x1800ccdd0`
- `0x1800d3950`

## import_xrefs

- `ext-ms-win-devmgmt-policy-l1-1-1!PolicyManager_GetPolicy` at `0x1800d39d4`
- `ext-ms-win-devmgmt-policy-l1-1-1!PolicyManager_GetPolicy` at `0x1800d39d4`

## string_xrefs

- `0x1800d39ec`: `onecore\ds\security\cfl\policy\lib\allowlistimpl.cpp`
- `0x1800d3a44`: `onecore\ds\security\cfl\policy\lib\allowlistimpl.cpp`
- `0x1800d3b84`: `onecore\ds\security\cfl\policy\lib\allowlistimpl.cpp`
- `0x1800d39c6`: `ConfigureWebSignInAllowedUrls`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall CXPolicy::PolicyAllowlist::GetNavigationAllowlist(__int64 a1, _QWORD *a2)
{
  int Policy; // eax
  __int64 v4; // rbx
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 trivial_2; // rbx
  __int64 i; // rsi
  __int64 v9; // rax
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rax
  int v18; // [rsp+20h] [rbp-39h]
  char *v19; // [rsp+30h] [rbp-29h]
  int v20; // [rsp+38h] [rbp-21h]
  __int64 v21; // [rsp+40h] [rbp-19h] BYREF
  __int64 v22; // [rsp+48h] [rbp-11h] BYREF
  __int128 v23; // [rsp+50h] [rbp-9h] BYREF
  __int64 v24; // [rsp+60h] [rbp+7h]
  __int128 v25; // [rsp+70h] [rbp+17h] BYREF
  __m128i si128; // [rsp+80h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v22 = (__int64)a2;
  v25 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v25) = 0;
  if ( !(unsigned __int8)IsPolicyManager_GetPolicyPresent() )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xAE,
      (unsigned int)"onecore\\ds\\security\\cfl\\policy\\lib\\allowlistimpl.cpp",
      (const char *)0x80004001LL,
      v18);
  v22 = 0x200000001LL;
  v21 = 0;
  Policy = PolicyManager_GetPolicy(L"Authentication", L"ConfigureWebSignInAllowedUrls", &v22, &v21);
  if ( Policy >= 0 )
  {
    v4 = v21;
    v20 = *(_DWORD *)(v21 + 8);
    LODWORD(v19) = *(_DWORD *)(v21 + 4);
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0xBE,
      (unsigned int)"onecore\\ds\\security\\cfl\\policy\\lib\\allowlistimpl.cpp",
      (const char *)0x8000FFFFLL,
      v20 != 2,
      (bool)"state: %u, type: %u",
      v19,
      v20);
    v5 = *(_QWORD *)(v4 + 16);
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)(v5 + 2 * v6) );
    std::wstring::_Assign<unsigned short>(&v25, v5, v6);
    wil::details::unique_storage<wil::details::resource_policy<PMPolicyRetrievedInfo *,long (*)(PMPolicyRetrievedInfo *),&long PolicyManager_FreeGetPolicyData(PMPolicyRetrievedInfo *),wistd::integral_constant<unsigned __int64,0>,PMPolicyRetrievedInfo *,PMPolicyRetrievedInfo *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<PMPolicyRetrievedInfo *,long (*)(PMPolicyRetrievedInfo *),&long PolicyManager_FreeGetPolicyData(PMPolicyRetrievedInfo *),wistd::integral_constant<unsigned __int64,0>,PMPolicyRetrievedInfo *,PMPolicyRetrievedInfo *,0,std::nullptr_t>>(&v21);
    v23 = 0;
    v24 = 0;
    trivial_2 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v25);
    v21 = trivial_2;
    for ( i = trivial_2; ; i = trivial_2 )
    {
      v9 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v25);
      v12 = v9 + 2 * v11;
      if ( i == v12 )
        break;
      trivial_2 = _std_find_trivial_2(trivial_2, v12, 59);
      v22 = trivial_2;
      if ( i != trivial_2 )
      {
        if ( *((_QWORD *)&v23 + 1) == v24 )
        {
          std::vector<std::wstring>::_Emplace_reallocate<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>> &,std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>> &>(
            &v23,
            *((_QWORD *)&v23 + 1),
            &v21,
            &v22);
          trivial_2 = v22;
        }
        else
        {
          std::_Default_allocator_traits<std::allocator<std::wstring>>::construct<std::wstring,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>> &,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>> &>(
            v13,
            *((_QWORD *)&v23 + 1),
            &v21,
            &v22);
          *((_QWORD *)&v23 + 1) += 32LL;
        }
      }
      v21 = trivial_2;
      v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v25);
      if ( trivial_2 != v14 + 2 * si128.m128i_i64[0] )
      {
        trivial_2 += 2;
        v21 = trivial_2;
      }
    }
    v24 = 0;
    v15 = *((_QWORD *)&v23 + 1);
    v16 = v23;
    v23 = 0u;
    *a2 = v16;
    a2[1] = v15;
    a2[2] = v10;
    std::vector<std::wstring>::_Tidy(&v23);
  }
  else
  {
    if ( Policy != -2147024894 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xB9,
        (unsigned int)"onecore\\ds\\security\\cfl\\policy\\lib\\allowlistimpl.cpp",
        (const char *)(unsigned int)Policy,
        v18);
    *a2 = 0;
    a2[1] = 0;
    a2[2] = 0;
    wil::details::unique_storage<wil::details::resource_policy<PMPolicyRetrievedInfo *,long (*)(PMPolicyRetrievedInfo *),&long PolicyManager_FreeGetPolicyData(PMPolicyRetrievedInfo *),wistd::integral_constant<unsigned __int64,0>,PMPolicyRetrievedInfo *,PMPolicyRetrievedInfo *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<PMPolicyRetrievedInfo *,long (*)(PMPolicyRetrievedInfo *),&long PolicyManager_FreeGetPolicyData(PMPolicyRetrievedInfo *),wistd::integral_constant<unsigned __int64,0>,PMPolicyRetrievedInfo *,PMPolicyRetrievedInfo *,0,std::nullptr_t>>(&v21);
  }
  std::wstring::_Tidy_deallocate(&v25);
  return a2;
}

```

## disassembly

```asm
0x1800d3950  mov     [rsp-8+arg_0], rbx
0x1800d3955  mov     [rsp-8+arg_10], rsi
0x1800d395a  push    rbp
0x1800d395b  push    rdi
0x1800d395c  push    r14
0x1800d395e  lea     rbp, [rsp-47h]
0x1800d3963  sub     rsp, 0A0h
0x1800d396a  mov     rax, cs:__security_cookie
0x1800d3971  xor     rax, rsp
0x1800d3974  mov     [rbp+57h+var_20], rax
0x1800d3978  mov     rdi, rdx
0x1800d397b  mov     [rbp+57h+var_68], rdx
0x1800d397f  xor     r14d, r14d
0x1800d3982  xorps   xmm0, xmm0
0x1800d3985  movups  [rbp+57h+var_40], xmm0
0x1800d3989  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800d3991  movdqu  [rbp+57h+var_30], xmm1
0x1800d3996  mov     word ptr [rbp+57h+var_40], r14w
0x1800d399b  mov     rbx, [rbp+5Fh]
0x1800d399f  call    IsPolicyManager_GetPolicyPresent
0x1800d39a4  test    al, al
0x1800d39a6  jz      loc_1800D3B7E
0x1800d39ac  mov     dword ptr [rbp+57h+var_68], 1
0x1800d39b3  mov     dword ptr [rbp+57h+var_68+4], 2
0x1800d39ba  mov     [rbp+57h+var_70], r14
0x1800d39be  lea     r9, [rbp+57h+var_70]
0x1800d39c2  lea     r8, [rbp+57h+var_68]
0x1800d39c6  lea     rdx, aConfigurewebsi; "ConfigureWebSignInAllowedUrls"
0x1800d39cd  lea     rcx, aAuthentication; "Authentication"
0x1800d39d4  call    cs:__imp_PolicyManager_GetPolicy
0x1800d39da  mov     rcx, [rbp+5Fh]; this
0x1800d39de  test    eax, eax
0x1800d39e0  jns     short loc_1800D3A16
0x1800d39e2  cmp     eax, 80070002h
0x1800d39e7  jz      short loc_1800D39FD
0x1800d39e9  mov     r9d, eax; char *
0x1800d39ec  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\policy\\lib"...
0x1800d39f3  mov     edx, 0B9h; void *
0x1800d39f8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800d39fd  mov     [rdi], r14
0x1800d3a00  mov     [rdi+8], r14
0x1800d3a04  mov     [rdi+10h], r14
0x1800d3a08  lea     rcx, [rbp+57h+var_70]
0x1800d3a0c  call    ??1?$unique_storage@U?$resource_policy@PEAUPMPolicyRetrievedInfo@@P6AJPEAU1@@Z$1?PolicyManager_FreeGetPolicyData@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<PMPolicyRetrievedInfo *,long (*)(PMPolicyRetrievedInfo *),&PolicyManager_FreeGetPolicyData(PMPolicyRetrievedInfo *),wistd::integral_constant<unsigned __int64,0>,PMPolicyRetrievedInfo *,PMPolicyRetrievedInfo *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<PMPolicyRetrievedInfo *,long (*)(PMPolicyRetrievedInfo *),&PolicyManager_FreeGetPolicyData(PMPolicyRetrievedInfo *),wistd::integral_constant<unsigned __int64,0>,PMPolicyRetrievedInfo *,PMPolicyRetrievedInfo *,0,std::nullptr_t>>(void)
0x1800d3a11  jmp     loc_1800D3B4E
0x1800d3a16  mov     rbx, [rbp+57h+var_70]
0x1800d3a1a  mov     eax, [rbx+8]
0x1800d3a1d  cmp     eax, 2
0x1800d3a20  setnz   dl
0x1800d3a23  mov     [rsp+0B0h+var_78], eax
0x1800d3a27  mov     eax, [rbx+4]
0x1800d3a2a  mov     dword ptr [rsp+0B0h+var_80], eax; char *
0x1800d3a2e  lea     rax, aStateUTypeU; "state: %u, type: %u"
0x1800d3a35  mov     qword ptr [rsp+0B0h+var_88], rax; bool
0x1800d3a3a  mov     [rsp+0B0h+var_90], dl; char
0x1800d3a3e  mov     r9d, 8000FFFFh; char *
0x1800d3a44  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\policy\\lib"...
0x1800d3a4b  mov     edx, 0BEh; void *
0x1800d3a50  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800d3a55  mov     rdx, [rbx+10h]
0x1800d3a59  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800d3a5d  inc     r8
0x1800d3a60  cmp     [rdx+r8*2], r14w
0x1800d3a65  jnz     short loc_1800D3A5D
0x1800d3a67  lea     rcx, [rbp+57h+var_40]
0x1800d3a6b  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800d3a70  nop
0x1800d3a71  lea     rcx, [rbp+57h+var_70]
0x1800d3a75  call    ??1?$unique_storage@U?$resource_policy@PEAUPMPolicyRetrievedInfo@@P6AJPEAU1@@Z$1?PolicyManager_FreeGetPolicyData@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<PMPolicyRetrievedInfo *,long (*)(PMPolicyRetrievedInfo *),&PolicyManager_FreeGetPolicyData(PMPolicyRetrievedInfo *),wistd::integral_constant<unsigned __int64,0>,PMPolicyRetrievedInfo *,PMPolicyRetrievedInfo *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<PMPolicyRetrievedInfo *,long (*)(PMPolicyRetrievedInfo *),&PolicyManager_FreeGetPolicyData(PMPolicyRetrievedInfo *),wistd::integral_constant<unsigned __int64,0>,PMPolicyRetrievedInfo *,PMPolicyRetrievedInfo *,0,std::nullptr_t>>(void)
0x1800d3a7a  xorps   xmm0, xmm0
0x1800d3a7d  movdqu  [rbp+57h+var_60], xmm0
0x1800d3a82  mov     r8, r14
0x1800d3a85  mov     [rbp+57h+var_50], r14
0x1800d3a89  lea     rcx, [rbp+57h+var_40]
0x1800d3a8d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800d3a92  mov     rbx, rax
0x1800d3a95  mov     [rbp+57h+var_70], rax
0x1800d3a99  mov     rsi, rax
0x1800d3a9c  mov     rdx, qword ptr [rbp+57h+var_30]
0x1800d3aa0  lea     rcx, [rbp+57h+var_40]
0x1800d3aa4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800d3aa9  lea     rdx, [rax+rdx*2]
0x1800d3aad  cmp     rsi, rdx
0x1800d3ab0  jz      short loc_1800D3B25
0x1800d3ab2  mov     r8d, 3Bh ; ';'
0x1800d3ab8  mov     rcx, rbx
0x1800d3abb  call    __std_find_trivial_2
0x1800d3ac0  mov     rbx, rax
0x1800d3ac3  mov     [rbp+57h+var_68], rax
0x1800d3ac7  cmp     rsi, rax
0x1800d3aca  jz      short loc_1800D3AF7
0x1800d3acc  mov     rdx, qword ptr [rbp+57h+var_60+8]
0x1800d3ad0  lea     r9, [rbp+57h+var_68]
0x1800d3ad4  lea     r8, [rbp+57h+var_70]
0x1800d3ad8  cmp     rdx, [rbp+57h+var_50]
0x1800d3adc  jz      short loc_1800D3AEA
0x1800d3ade  call    ??$construct@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@AEAV32@@?$_Default_allocator_traits@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@SAXAEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEAV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@1@2@Z; std::_Default_allocator_traits<std::allocator<std::wstring>>::construct<std::wstring,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>> &,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>> &>(std::allocator<std::wstring> &,std::wstring * const,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>> &,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>> &)
0x1800d3ae3  add     qword ptr [rbp+57h+var_60+8], 20h ; ' '
0x1800d3ae8  jmp     short loc_1800D3AF7
0x1800d3aea  lea     rcx, [rbp+57h+var_60]
0x1800d3aee  call    ??$_Emplace_reallocate@AEAV?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@AEAV12@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEAV?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@1@1@Z; std::vector<std::wstring>::_Emplace_reallocate<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>> &,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>> &>(std::wstring * const,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>> &,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>> &)
0x1800d3af3  mov     rbx, [rbp+57h+var_68]
0x1800d3af7  mov     [rbp+57h+var_70], rbx
0x1800d3afb  lea     rcx, [rbp+57h+var_40]
0x1800d3aff  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800d3b04  mov     rdx, qword ptr [rbp+57h+var_30]
0x1800d3b08  lea     rax, [rax+rdx*2]
0x1800d3b0c  cmp     rbx, rax
0x1800d3b0f  jz      short loc_1800D3B19
0x1800d3b11  add     rbx, 2
0x1800d3b15  mov     [rbp+57h+var_70], rbx
0x1800d3b19  mov     rsi, rbx
0x1800d3b1c  mov     r8, [rbp+57h+var_50]
0x1800d3b20  jmp     loc_1800D3AA0
0x1800d3b25  mov     [rbp+57h+var_50], r14
0x1800d3b29  mov     rcx, qword ptr [rbp+57h+var_60+8]
0x1800d3b2d  mov     qword ptr [rbp+57h+var_60+8], r14
0x1800d3b31  mov     rax, qword ptr [rbp+57h+var_60]
0x1800d3b35  mov     qword ptr [rbp+57h+var_60], r14
0x1800d3b39  mov     [rdi], rax
0x1800d3b3c  mov     [rdi+8], rcx
0x1800d3b40  mov     [rdi+10h], r8
0x1800d3b44  lea     rcx, [rbp+57h+var_60]
0x1800d3b48  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800d3b4d  nop
0x1800d3b4e  lea     rcx, [rbp+57h+var_40]
0x1800d3b52  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800d3b57  mov     rax, rdi
0x1800d3b5a  mov     rcx, [rbp+57h+var_20]
0x1800d3b5e  xor     rcx, rsp; StackCookie
0x1800d3b61  call    __security_check_cookie
0x1800d3b66  lea     r11, [rsp+0B0h+var_10]
0x1800d3b6e  mov     rbx, [r11+20h]
0x1800d3b72  mov     rsi, [r11+30h]
0x1800d3b76  mov     rsp, r11
0x1800d3b79  pop     r14
0x1800d3b7b  pop     rdi
0x1800d3b7c  pop     rbp
0x1800d3b7d  retn
0x1800d3b7e  mov     r9d, 80004001h; char *
0x1800d3b84  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\policy\\lib"...
0x1800d3b8b  mov     edx, 0AEh; void *
0x1800d3b90  mov     rcx, rbx; this
0x1800d3b93  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
