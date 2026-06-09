# ??$call@AEAV_lambda_216e461b0f2bafa6414b8faed9d5cbb6_@@@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_216e461b0f2bafa6414b8faed9d5cbb6_@@@Z

- ea: `0x18002ade0`
- end: `0x18002af92`
- name: `??$call@AEAV_lambda_216e461b0f2bafa6414b8faed9d5cbb6_@@@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_216e461b0f2bafa6414b8faed9d5cbb6_@@@Z`
- size: `434`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002afa0`

## callees

- `0x1800040a0`
- `0x180004810`
- `0x180013ed0`
- `0x18002ad40`
- `0x18002ade0`
- `0x180034ef0`
- `0x180039709`
- `0x18003bed0`

## string_xrefs

- `0x18002ae20`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::call<_lambda_216e461b0f2bafa6414b8faed9d5cbb6_ &>(
        __int64 a1,
        _QWORD *a2)
{
  void (__fastcall ***v3)(_QWORD, _QWORD, _QWORD); // rbx
  unsigned __int8 v4; // di
  char *v5; // rdi
  _QWORD *v6; // rsi
  void (__fastcall *v7)(_QWORD, _QWORD, _QWORD); // r14
  int v8; // eax
  void (__fastcall ***v10)(_QWORD, _QWORD, _QWORD); // [rsp+30h] [rbp-50h] BYREF
  _DWORD *v11; // [rsp+38h] [rbp-48h] BYREF
  _DWORD v12[4]; // [rsp+40h] [rbp-40h] BYREF
  const wchar_t *v13; // [rsp+50h] [rbp-30h]
  char v14; // [rsp+58h] [rbp-28h] BYREF
  __int64 *v15; // [rsp+60h] [rbp-20h] BYREF
  void (__fastcall ***v16)(_QWORD, __int64 *, __int64 **); // [rsp+68h] [rbp-18h] BYREF
  _BYTE v17[8]; // [rsp+70h] [rbp-10h] BYREF

  v12[0] = 1;
  v12[1] = 28;
  v13 = L"Windows.Data.Json.JsonObject";
  v11 = v12;
  v16 = 0;
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v15,
    &v11,
    winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonObjectStatics>,
    &v16);
  if ( (int)v15 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v15);
  }
  v3 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v16;
  v10 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v16;
  if ( v16 && (v15 = 0, (**v16)(v16, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v15), v15) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v15);
    v15 = &qword_180059F98;
    _InterlockedIncrement64(&qword_180059F98);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>,
            (signed __int64)v16,
            0) )
    {
      v3 = 0;
      v10 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180059FA0);
    }
    v4 = _lambda_216e461b0f2bafa6414b8faed9d5cbb6_::operator()(
           a2,
           &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>);
    _InterlockedDecrement64(&qword_180059F98);
  }
  else
  {
    v5 = (char *)a2[1];
    v6 = (_QWORD *)*a2;
    v17[0] = 0;
    v7 = (*v3)[7];
    if ( v5 != &v14 )
    {
      if ( *(_QWORD *)v5 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v5);
      *(_QWORD *)v5 = 0;
    }
    v8 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD, _QWORD, _QWORD), _QWORD, char *, _BYTE *))v7)(
           v3,
           *v6,
           v5,
           v17);
    if ( v8 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v8);
    }
    v4 = v17[0];
  }
  if ( v3 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v10);
  return v4;
}

```

## disassembly

```asm
0x18002ade0  mov     [rsp-18h+arg_0], rbx
0x18002ade5  mov     [rsp-18h+arg_10], rsi
0x18002adea  mov     [rsp-18h+arg_18], rdi
0x18002adef  push    rbp
0x18002adf0  push    r14
0x18002adf2  push    r15
0x18002adf4  mov     rbp, rsp
0x18002adf7  sub     rsp, 80h
0x18002adfe  mov     rax, cs:__security_cookie
0x18002ae05  xor     rax, rsp
0x18002ae08  mov     [rbp+var_8], rax
0x18002ae0c  mov     rsi, rdx
0x18002ae0f  xor     r15d, r15d
0x18002ae12  mov     [rbp+var_40], 1
0x18002ae19  mov     [rbp+var_3C], 1Ch
0x18002ae20  lea     rax, aWindowsDataJso; "Windows.Data.Json.JsonObject"
0x18002ae27  mov     [rbp+var_30], rax
0x18002ae2b  lea     rax, [rbp+var_40]
0x18002ae2f  mov     [rbp+var_48], rax
0x18002ae33  mov     [rbp+var_18], r15
0x18002ae37  lea     r9, [rbp+var_18]
0x18002ae3b  lea     r8, ??$guid_v@UIJsonObjectStatics@Json@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonObjectStatics>
0x18002ae42  lea     rdx, [rbp+var_48]
0x18002ae46  lea     rcx, [rbp+var_20]
0x18002ae4a  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18002ae4f  mov     ecx, dword ptr [rbp+var_20]
0x18002ae52  test    ecx, ecx
0x18002ae54  js      loc_18002AF89
0x18002ae5a  mov     rbx, [rbp+var_18]
0x18002ae5e  mov     [rbp+var_50], rbx
0x18002ae62  test    rbx, rbx
0x18002ae65  jz      loc_18002AEF9
0x18002ae6b  mov     [rbp+var_20], r15
0x18002ae6f  mov     rax, [rbx]
0x18002ae72  lea     r8, [rbp+var_20]
0x18002ae76  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18002ae7d  mov     rcx, rbx
0x18002ae80  mov     rax, [rax]
0x18002ae83  call    cs:__guard_dispatch_icall_fptr
0x18002ae89  mov     rax, [rbp+var_20]
0x18002ae8d  mov     [rbp+var_20], rax
0x18002ae91  test    rax, rax
0x18002ae94  jz      short loc_18002AEF9
0x18002ae96  lea     rcx, [rbp+var_20]
0x18002ae9a  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002ae9f  lea     rax, qword_180059F98
0x18002aea6  mov     [rbp+var_20], rax
0x18002aeaa  lock inc cs:qword_180059F98
0x18002aeb2  mov     rdx, [rbp+var_18]
0x18002aeb6  xor     eax, eax
0x18002aeb8  lock cmpxchg cs:??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@12@A, rdx; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>
0x18002aec1  jnz     short loc_18002AEDD
0x18002aec3  mov     ebx, r15d
0x18002aec6  mov     [rbp+var_50], rbx
0x18002aeca  lea     rdx, stru_180059FA0; ListEntry
0x18002aed1  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18002aed8  call    WINRT_IMPL_InterlockedPushEntrySList
0x18002aedd  lea     rdx, ??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>
0x18002aee4  mov     rcx, rsi
0x18002aee7  call    ??R_lambda_216e461b0f2bafa6414b8faed9d5cbb6_@@QEBA@AEBUIJsonObjectStatics@Json@Data@Windows@winrt@@@Z; _lambda_216e461b0f2bafa6414b8faed9d5cbb6_::operator()(winrt::Windows::Data::Json::IJsonObjectStatics const &)
0x18002aeec  movzx   edi, al
0x18002aeef  lock dec cs:qword_180059F98
0x18002aef7  jmp     short loc_18002AF43
0x18002aef9  mov     rdi, [rsi+8]
0x18002aefd  mov     rsi, [rsi]
0x18002af00  mov     [rbp+var_10], 0
0x18002af04  mov     rax, [rbx]
0x18002af07  mov     r14, [rax+38h]
0x18002af0b  lea     rax, [rbp+var_28]
0x18002af0f  cmp     rdi, rax
0x18002af12  jz      short loc_18002AF25
0x18002af14  cmp     qword ptr [rdi], 0
0x18002af18  jz      short loc_18002AF22
0x18002af1a  mov     rcx, rdi
0x18002af1d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002af22  mov     [rdi], r15
0x18002af25  lea     r9, [rbp+var_10]
0x18002af29  mov     r8, rdi
0x18002af2c  mov     rdx, [rsi]
0x18002af2f  mov     rcx, rbx
0x18002af32  mov     rax, r14
0x18002af35  call    cs:__guard_dispatch_icall_fptr
0x18002af3b  test    eax, eax
0x18002af3d  js      short loc_18002AF7E
0x18002af3f  movzx   edi, [rbp+var_10]
0x18002af43  test    rbx, rbx
0x18002af46  jz      short loc_18002AF51
0x18002af48  lea     rcx, [rbp+var_50]
0x18002af4c  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002af51  movzx   eax, dil
0x18002af55  mov     rcx, [rbp+var_8]
0x18002af59  xor     rcx, rsp; StackCookie
0x18002af5c  call    __security_check_cookie
0x18002af61  lea     r11, [rsp+80h+var_s0]
0x18002af69  mov     rbx, [r11+20h]
0x18002af6d  mov     rsi, [r11+30h]
0x18002af71  mov     rdi, [r11+38h]
0x18002af75  mov     rsp, r11
0x18002af78  pop     r15
0x18002af7a  pop     r14
0x18002af7c  pop     rbp
0x18002af7d  retn
0x18002af7e  lfence
0x18002af81  mov     ecx, eax
0x18002af83  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
0x18002af89  lfence
0x18002af8c  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
```
