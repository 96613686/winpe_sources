# RequiredLanguageFeaturesInstaller::RequiredLanguageFeaturesInstaller(CbsLanguageSession const &,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::function<DigitizerSupport (void)> const &,std::function<bool (void)> const &,std::function<bool (void)> const &)

- ea: `0x18000afac`
- end: `0x18000b20f`
- name: `??$?0VCbsLanguageSession@@@RequiredLanguageFeaturesInstaller@@QEAA@AEBVCbsLanguageSession@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@1AEBV?$function@$$A6A?AW4DigitizerSupport@@XZ@3@AEBV?$function@$$A6A_NXZ@3@3@Z`
- size: `611`
- prototype: `_QWORD *__fastcall(_QWORD *, int, _QWORD *, _QWORD *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x1800140e0`

## callees

- `0x180003520`
- `0x180005954`
- `0x180006380`
- `0x18000afac`
- `0x18000b6b4`
- `0x18000c15c`
- `0x18000c2ac`
- `0x1800214f4`
- `0x180021590`
- `0x18002a010`

## pseudocode

```c
_QWORD *__fastcall RequiredLanguageFeaturesInstaller::RequiredLanguageFeaturesInstaller(
        _QWORD *a1,
        int a2,
        _QWORD *a3,
        _QWORD *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rbx
  __int64 v18; // rdi
  _QWORD *v19; // rcx
  _QWORD *v20; // rdx
  __int64 (__fastcall ***v21)(_QWORD, __int64); // rcx
  __int64 (__fastcall ***v22)(_QWORD, __int64); // rcx
  __int64 (__fastcall ***v23)(_QWORD, __int64); // rcx
  _QWORD v25[3]; // [rsp+58h] [rbp-A8h] BYREF
  _OWORD v26[2]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD *v27; // [rsp+90h] [rbp-70h]
  _QWORD v28[7]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD *v29; // [rsp+D8h] [rbp-28h]
  _QWORD *v30; // [rsp+E0h] [rbp-20h]
  _QWORD *v31; // [rsp+E8h] [rbp-18h]

  v27 = a1;
  v30 = a3;
  v31 = a4;
  v11 = a3[2];
  a3[2] = 0;
  v12 = a3[1];
  a3[1] = 0;
  v13 = *a3;
  *a3 = 0;
  *a1 = v13;
  a1[1] = v12;
  a1[2] = v11;
  v14 = a4[2];
  a4[2] = 0;
  v15 = a4[1];
  a4[1] = 0;
  v16 = *a4;
  *a4 = 0;
  a1[3] = v16;
  a1[4] = v15;
  a1[5] = v14;
  memset(v26, 0, sizeof(v26));
  std::wstring::_Construct<1,unsigned short const *>(v26);
  CbsSession::FeaturesOfCapability<CbsLanguageFeature,bool (CbsLanguageFeature const &)>(
    a2,
    (unsigned int)v25,
    (unsigned int)v26,
    5,
    (__int64)_scrt_stub_for_acrt_uninitialize_critical);
  std::wstring::~wstring(v26);
  v17 = v25[1];
  v18 = v25[0];
  v28[0] = &std::_Func_impl_no_alloc<_lambda_e8565040e165d3daccfd4cbfb75449a5_,long,unsigned short const *,unsigned short const *,int *>::`vftable';
  v29 = v28;
  BaseLanguageFeaturesRegistrar<CbsLanguageFeature>::VectorFromRange<enum PayloadType const *>(
    a1 + 6,
    qword_18002D090,
    &__WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_2);
  BaseLanguageFeaturesRegistrar<CbsLanguageFeature>::PartitionFeaturesByType<std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<CbsLanguageFeature>>>>(
    a1 + 9,
    v18,
    v17,
    a1 + 6);
  a1[18] = 0;
  v19 = v29;
  if ( v29 )
  {
    a1[18] = (*(__int64 (__fastcall **)(_QWORD *, _QWORD *))*v29)(v29, a1 + 11);
    v19 = v29;
  }
  if ( v19 )
  {
    v20 = v28;
    LOBYTE(v20) = v19 != v28;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v19 + 32LL))(v19, v20);
  }
  std::vector<CbsLanguageFeature>::_Tidy(v25);
  a1[26] = 0;
  v21 = *(__int64 (__fastcall ****)(_QWORD, __int64))(a5 + 56);
  if ( v21 )
    a1[26] = (**v21)(v21, (__int64)(a1 + 19));
  a1[34] = 0;
  v22 = *(__int64 (__fastcall ****)(_QWORD, __int64))(a6 + 56);
  if ( v22 )
    a1[34] = (**v22)(v22, (__int64)(a1 + 27));
  a1[42] = 0;
  v23 = *(__int64 (__fastcall ****)(_QWORD, __int64))(a7 + 56);
  if ( v23 )
    a1[42] = (**v23)(v23, (__int64)(a1 + 35));
  std::vector<std::wstring>::_Tidy(a3);
  std::vector<std::wstring>::_Tidy(a4);
  return a1;
}

```

## disassembly

```asm
0x18000afac  push    rbp
0x18000afae  push    rbx
0x18000afaf  push    rsi
0x18000afb0  push    rdi
0x18000afb1  push    r12
0x18000afb3  push    r13
0x18000afb5  push    r14
0x18000afb7  push    r15
0x18000afb9  lea     rbp, [rsp-8]
0x18000afbe  sub     rsp, 108h
0x18000afc5  mov     rax, cs:__security_cookie
0x18000afcc  xor     rax, rsp
0x18000afcf  mov     [rbp+40h+var_50], rax
0x18000afd3  mov     r12, r9
0x18000afd6  mov     r15, r8
0x18000afd9  mov     rbx, rdx
0x18000afdc  mov     r14, rcx
0x18000afdf  mov     [rbp+40h+var_B0], rcx
0x18000afe3  mov     [rbp+40h+var_60], r8
0x18000afe7  mov     [rbp+40h+var_58], r9
0x18000afeb  mov     r13, [rbp+40h+arg_20]
0x18000afef  mov     rax, [rbp+40h+arg_28]
0x18000aff3  mov     [rsp+140h+var_100], rax
0x18000aff8  mov     rax, [rbp+40h+arg_30]
0x18000afff  mov     [rsp+140h+var_F8], rax
0x18000b004  xor     r8d, r8d
0x18000b007  mov     rdx, [r15+10h]
0x18000b00b  mov     [r15+10h], r8
0x18000b00f  mov     rcx, [r15+8]
0x18000b013  mov     [r15+8], r8
0x18000b017  mov     rax, [r15]
0x18000b01a  mov     [r15], r8
0x18000b01d  mov     [r14], rax
0x18000b020  mov     [r14+8], rcx
0x18000b024  mov     [r14+10h], rdx
0x18000b028  mov     rdx, [r9+10h]
0x18000b02c  mov     [r9+10h], r8
0x18000b030  mov     rcx, [r9+8]
0x18000b034  mov     [r9+8], r8
0x18000b038  mov     rax, [r9]
0x18000b03b  mov     [r9], r8
0x18000b03e  mov     [r14+18h], rax
0x18000b042  mov     [r14+20h], rcx
0x18000b046  mov     [r14+28h], rdx
0x18000b04a  lea     rsi, [r14+30h]
0x18000b04e  mov     [rsp+140h+var_108], rsi
0x18000b053  xorps   xmm0, xmm0
0x18000b056  movups  [rsp+140h+var_D0], xmm0
0x18000b05b  xorps   xmm1, xmm1
0x18000b05e  movdqu  [rbp+40h+var_C0], xmm1
0x18000b063  mov     r8d, 8
0x18000b069  lea     rdx, aLanguage; "Language"
0x18000b070  lea     rcx, [rsp+140h+var_D0]
0x18000b075  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000b07a  nop
0x18000b07b  lea     rax, __scrt_stub_for_acrt_uninitialize_critical
0x18000b082  mov     [rsp+140h+var_120], rax
0x18000b087  mov     r9d, 5
0x18000b08d  lea     r8, [rsp+140h+var_D0]
0x18000b092  lea     rdx, [rsp+140h+var_E8]
0x18000b097  mov     rcx, rbx
0x18000b09a  call    ??$FeaturesOfCapability@VCbsLanguageFeature@@$$A6A_NAEBV1@@Z@CbsSession@@QEBA?AV?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@IA6A_NAEBVCbsLanguageFeature@@@Z@Z; CbsSession::FeaturesOfCapability<CbsLanguageFeature,bool (CbsLanguageFeature const &)>(std::wstring const &,uint,bool (&)(CbsLanguageFeature const &))
0x18000b09f  nop
0x18000b0a0  lea     rcx, [rsp+140h+var_D0]; void *
0x18000b0a5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000b0aa  nop
0x18000b0ab  mov     rbx, [rsp+140h+var_E0]
0x18000b0b0  mov     rdi, [rsp+140h+var_E8]
0x18000b0b5  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_e8565040e165d3daccfd4cbfb75449a5_@@JPEBGPEBGPEAH@std@@6B@; const std::_Func_impl_no_alloc<_lambda_e8565040e165d3daccfd4cbfb75449a5_,long,ushort const *,ushort const *,int *>::`vftable'
0x18000b0bc  mov     [rbp+40h+var_A0], rax
0x18000b0c0  lea     rax, [rbp+40h+var_A0]
0x18000b0c4  mov     [rbp+40h+var_68], rax
0x18000b0c8  lea     rax, [rbp+40h+var_A0]
0x18000b0cc  mov     [rsp+140h+var_F0], rax
0x18000b0d1  lea     r8, ?__WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_2@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_2
0x18000b0d8  lea     rdx, qword_18002D090
0x18000b0df  mov     rcx, rsi
0x18000b0e2  call    ??$VectorFromRange@PEBW4PayloadType@@@?$BaseLanguageFeaturesRegistrar@VCbsLanguageFeature@@@@KA?AV?$vector@W4PayloadType@@V?$allocator@W4PayloadType@@@std@@@std@@PEBW4PayloadType@@0@Z; BaseLanguageFeaturesRegistrar<CbsLanguageFeature>::VectorFromRange<PayloadType const *>(PayloadType const *,PayloadType const *)
0x18000b0e7  nop
0x18000b0e8  lea     rcx, [rsi+18h]
0x18000b0ec  mov     r9, rsi
0x18000b0ef  mov     r8, rbx
0x18000b0f2  mov     rdx, rdi
0x18000b0f5  call    ??$PartitionFeaturesByType@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@VCbsLanguageFeature@@@std@@@std@@@std@@@?$BaseLanguageFeaturesRegistrar@VCbsLanguageFeature@@@@KA?AV?$map@W4PayloadType@@V?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@U?$less@W4PayloadType@@@3@V?$allocator@U?$pair@$$CBW4PayloadType@@V?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@std@@@3@@std@@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@VCbsLanguageFeature@@@std@@@std@@@2@0AEBV?$vector@W4PayloadType@@V?$allocator@W4PayloadType@@@std@@@2@@Z; BaseLanguageFeaturesRegistrar<CbsLanguageFeature>::PartitionFeaturesByType<std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<CbsLanguageFeature>>>>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<CbsLanguageFeature>>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<CbsLanguageFeature>>>,std::vector<PayloadType> const &)
0x18000b0fa  nop
0x18000b0fb  add     rsi, 28h ; '('
0x18000b0ff  mov     [rsp+140h+var_110], rsi
0x18000b104  xor     edi, edi
0x18000b106  mov     [rsi+38h], rdi
0x18000b10a  mov     rcx, [rbp+40h+var_68]
0x18000b10e  test    rcx, rcx
0x18000b111  jz      short loc_18000B129
0x18000b113  mov     rax, [rcx]
0x18000b116  mov     rdx, rsi
0x18000b119  mov     rax, [rax]
0x18000b11c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b121  mov     [rsi+38h], rax
0x18000b125  mov     rcx, [rbp+40h+var_68]
0x18000b129  test    rcx, rcx
0x18000b12c  jz      short loc_18000B145
0x18000b12e  mov     rax, [rcx]
0x18000b131  lea     rdx, [rbp+40h+var_A0]
0x18000b135  cmp     rcx, rdx
0x18000b138  setnz   dl
0x18000b13b  mov     rax, [rax+20h]
0x18000b13f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b144  nop
0x18000b145  lea     rcx, [rsp+140h+var_E8]
0x18000b14a  call    ?_Tidy@?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@AEAAXXZ; std::vector<CbsLanguageFeature>::_Tidy(void)
0x18000b14f  nop
0x18000b150  lea     rbx, [r14+98h]
0x18000b157  mov     [rsp+140h+var_110], rbx
0x18000b15c  mov     [rbx+38h], rdi
0x18000b160  mov     rcx, [r13+38h]
0x18000b164  test    rcx, rcx
0x18000b167  jz      short loc_18000B17B
0x18000b169  mov     rax, [rcx]
0x18000b16c  mov     rdx, rbx
0x18000b16f  mov     rax, [rax]
0x18000b172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b177  mov     [rbx+38h], rax
0x18000b17b  lea     rbx, [r14+0D8h]
0x18000b182  mov     [rsp+140h+var_110], rbx
0x18000b187  mov     [rbx+38h], rdi
0x18000b18b  mov     rcx, [rsp+140h+var_100]
0x18000b190  mov     rcx, [rcx+38h]
0x18000b194  test    rcx, rcx
0x18000b197  jz      short loc_18000B1AB
0x18000b199  mov     rax, [rcx]
0x18000b19c  mov     rdx, rbx
0x18000b19f  mov     rax, [rax]
0x18000b1a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1a7  mov     [rbx+38h], rax
0x18000b1ab  lea     rbx, [r14+118h]
0x18000b1b2  mov     [rsp+140h+var_110], rbx
0x18000b1b7  mov     [rbx+38h], rdi
0x18000b1bb  mov     rcx, [rsp+140h+var_F8]
0x18000b1c0  mov     rcx, [rcx+38h]
0x18000b1c4  test    rcx, rcx
0x18000b1c7  jz      short loc_18000B1DB
0x18000b1c9  mov     rax, [rcx]
0x18000b1cc  mov     rdx, rbx
0x18000b1cf  mov     rax, [rax]
0x18000b1d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1d7  mov     [rbx+38h], rax
0x18000b1db  mov     rcx, r15
0x18000b1de  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18000b1e3  nop
0x18000b1e4  mov     rcx, r12
0x18000b1e7  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18000b1ec  mov     rax, r14
0x18000b1ef  mov     rcx, [rbp+40h+var_50]
0x18000b1f3  xor     rcx, rsp; StackCookie
0x18000b1f6  call    __security_check_cookie
0x18000b1fb  add     rsp, 108h
0x18000b202  pop     r15
0x18000b204  pop     r14
0x18000b206  pop     r13
0x18000b208  pop     r12
0x18000b20a  pop     rdi
0x18000b20b  pop     rsi
0x18000b20c  pop     rbx
0x18000b20d  pop     rbp
0x18000b20e  retn
```
