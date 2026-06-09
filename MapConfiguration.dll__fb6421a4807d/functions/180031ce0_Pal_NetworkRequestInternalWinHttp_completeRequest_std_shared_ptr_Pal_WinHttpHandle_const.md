# Pal::NetworkRequestInternalWinHttp::completeRequest(std::shared_ptr<Pal::WinHttpHandle> const &)

- ea: `0x180031ce0`
- end: `0x180031f11`
- name: `?completeRequest@NetworkRequestInternalWinHttp@Pal@@AEAAXAEBV?$shared_ptr@VWinHttpHandle@Pal@@@std@@@Z`
- size: `561`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800094a0`
- `0x180009988`
- `0x18000cb24`
- `0x18000fac4`
- `0x180010f34`
- `0x18001154c`
- `0x180011f04`
- `0x180012438`
- `0x180013da8`
- `0x180014de4`
- `0x180016d1c`
- `0x18002a30c`
- `0x18002dd88`
- `0x18002dfa8`
- `0x18002e8fc`
- `0x18002f6e8`
- `0x180031ce0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031d83`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031e82`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031d83`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031e82`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031e6f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031eb0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031e6f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031eb0`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall Pal::NetworkRequestInternalWinHttp::completeRequest(__int64 a1, _QWORD *a2)
{
  __int64 v4; // rbx
  __int64 v5; // rax
  __int64 *v6; // rax
  __int64 v7; // rax
  _QWORD *v8; // rdi
  _QWORD *v9; // rax
  __int64 v10; // r8
  std::_Ref_count_base *v11; // rdi
  _QWORD *v12; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v13; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v14; // [rsp+50h] [rbp-B0h] BYREF
  std::_Ref_count_base *v15[2]; // [rsp+58h] [rbp-A8h] BYREF
  std::_Ref_count_base *v16[2]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v17[40]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v18[144]; // [rsp+A0h] [rbp-60h] BYREF

  *(_OWORD *)v16 = 0;
  v4 = 0;
  v14 = 0;
  if ( *(_DWORD *)(a1 + 36) )
  {
    v5 = PalWindows::errorMessageFromHResult(v17);
    v6 = std::make_unique<Pal::NetworkException,std::string,0>(&v12, v5);
    std::unique_ptr<Pal::NetworkException>::operator=<std::default_delete<Pal::NetworkException>,0>(&v14, v6);
    std::unique_ptr<Pal::NetworkRequestImpl>::~unique_ptr<Pal::NetworkRequestImpl>(&v12);
    std::string::_Tidy_deallocate(v17);
    v4 = v14;
  }
  else
  {
    std::shared_ptr<std::vector<unsigned char> const>::operator=<std::vector<unsigned char>,std::default_delete<std::vector<unsigned char>>,0>(
      v16,
      (__int64 *)(a1 + 24));
  }
  v15[0] = (std::_Ref_count_base *)(a1 + 352);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 352));
  if ( *(_DWORD *)(a1 + 392) != 2 )
  {
    *(_DWORD *)(a1 + 392) = 3;
    v7 = 0;
    v13 = 0;
    if ( *a2 )
    {
      v8 = (_QWORD *)Core::requirePresent<MapControl::LocaleMapConfiguration>((__int64)v17, a2);
      v9 = operator new(0x18u);
      v12 = v9;
      *v9 = &Pal::NetworkResponseHeadersWinHttp::`vftable';
      std::shared_ptr<Pal::Detail::WrlTimerWrapper>::shared_ptr<Pal::Detail::WrlTimerWrapper>(v9 + 1, v8);
      v12 = (_QWORD *)v10;
      std::unique_ptr<Pal::NetworkException>::operator=<std::default_delete<Pal::NetworkException>,0>(
        &v13,
        (__int64 *)&v12);
      std::unique_ptr<Pal::NetworkRequestImpl>::~unique_ptr<Pal::NetworkRequestImpl>(&v12);
      Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(v17);
      v7 = v13;
    }
    v13 = 0;
    v12 = (_QWORD *)v7;
    Pal::NetworkResponse::NetworkResponse((__int64)v18, a1 + 224, v16, &v12, v4, 0);
    std::_Func_class<void,>::operator()(a1 + 400, v18);
    Pal::NetworkResponse::~NetworkResponse((Pal::NetworkResponse *)v18);
    std::unique_ptr<Pal::NetworkRequestImpl>::~unique_ptr<Pal::NetworkRequestImpl>(&v13);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 352));
  *(_OWORD *)v15 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 96));
  v11 = *(std::_Ref_count_base **)(a1 + 144);
  *(_QWORD *)(a1 + 136) = 0;
  *(_QWORD *)(a1 + 144) = 0;
  std::shared_ptr<Pal::NetworkRequestInternalWinHttp>::operator=(a1 + 136, v15);
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 96));
  if ( v15[1] )
    std::_Ref_count_base::_Decref(v15[1]);
  if ( v11 )
    std::_Ref_count_base::_Decref(v11);
  std::unique_ptr<Pal::NetworkRequestImpl>::~unique_ptr<Pal::NetworkRequestImpl>(&v14);
  if ( v16[1] )
    std::_Ref_count_base::_Decref(v16[1]);
}

```

## disassembly

```asm
0x180031ce0  mov     [rsp-8+arg_10], rbx
0x180031ce5  mov     [rsp-8+arg_18], rsi
0x180031cea  push    rbp
0x180031ceb  push    rdi
0x180031cec  push    r14
0x180031cee  lea     rbp, [rsp-40h]
0x180031cf3  sub     rsp, 140h
0x180031cfa  mov     rax, cs:__security_cookie
0x180031d01  xor     rax, rsp
0x180031d04  mov     [rbp+50h+var_20], rax
0x180031d08  mov     rdi, rdx
0x180031d0b  mov     rsi, rcx
0x180031d0e  xorps   xmm0, xmm0
0x180031d11  movdqu  xmmword ptr [rsp+150h+var_E8], xmm0
0x180031d17  xor     ebx, ebx
0x180031d19  mov     [rsp+150h+var_100], rbx
0x180031d1e  mov     edx, [rcx+24h]
0x180031d21  test    edx, edx
0x180031d23  jnz     short loc_180031D35
0x180031d25  lea     rdx, [rcx+18h]
0x180031d29  lea     rcx, [rsp+150h+var_E8]
0x180031d2e  call    ??$?4V?$vector@EV?$allocator@E@std@@@std@@U?$default_delete@V?$vector@EV?$allocator@E@std@@@std@@@1@$0A@@?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@QEAAAEAV01@$$QEAV?$unique_ptr@V?$vector@EV?$allocator@E@std@@@std@@U?$default_delete@V?$vector@EV?$allocator@E@std@@@std@@@2@@1@@Z; std::shared_ptr<std::vector<uchar> const>::operator=<std::vector<uchar>,std::default_delete<std::vector<uchar>>,0>(std::unique_ptr<std::vector<uchar>> &&)
0x180031d33  jmp     short loc_180031D74
0x180031d35  lea     rcx, [rsp+150h+var_D8]
0x180031d3a  call    ?errorMessageFromHResult@PalWindows@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@J@Z; PalWindows::errorMessageFromHResult(long)
0x180031d3f  nop
0x180031d40  mov     rdx, rax
0x180031d43  lea     rcx, [rsp+150h+var_110]
0x180031d48  call    ??$make_unique@VNetworkException@Pal@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$0A@@std@@YA?AV?$unique_ptr@VNetworkException@Pal@@U?$default_delete@VNetworkException@Pal@@@std@@@0@$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@@Z; std::make_unique<Pal::NetworkException,std::string,0>(std::string &&)
0x180031d4d  mov     rdx, rax
0x180031d50  lea     rcx, [rsp+150h+var_100]
0x180031d55  call    ??$?4U?$default_delete@VNetworkException@Pal@@@std@@$0A@@?$unique_ptr@VNetworkException@Pal@@U?$default_delete@VNetworkException@Pal@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Pal::NetworkException>::operator=<std::default_delete<Pal::NetworkException>,0>(std::unique_ptr<Pal::NetworkException> &&)
0x180031d5a  lea     rcx, [rsp+150h+var_110]
0x180031d5f  call    ??1?$unique_ptr@VNetworkRequestImpl@Pal@@U?$default_delete@VNetworkRequestImpl@Pal@@@std@@@std@@QEAA@XZ; std::unique_ptr<Pal::NetworkRequestImpl>::~unique_ptr<Pal::NetworkRequestImpl>(void)
0x180031d64  nop
0x180031d65  lea     rcx, [rsp+150h+var_D8]
0x180031d6a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180031d6f  mov     rbx, [rsp+150h+var_100]
0x180031d74  lea     r14, [rsi+160h]
0x180031d7b  mov     [rsp+150h+var_F8], r14
0x180031d80  mov     rcx, r14; lpCriticalSection
0x180031d83  call    cs:__imp_EnterCriticalSection
0x180031d89  nop
0x180031d8a  cmp     dword ptr [rsi+188h], 2
0x180031d91  jz      loc_180031E6C
0x180031d97  mov     dword ptr [rsi+188h], 3
0x180031da1  xor     eax, eax
0x180031da3  mov     [rsp+150h+var_108], rax
0x180031da8  cmp     [rdi], rax
0x180031dab  jz      short loc_180031E13
0x180031dad  mov     rdx, rdi
0x180031db0  lea     rcx, [rsp+150h+var_D8]
0x180031db5  call    ??$requirePresent@VLocaleMapConfiguration@MapControl@@@Core@@YA?AV?$PresentSharedPtr@VLocaleMapConfiguration@MapControl@@@0@AEBV?$shared_ptr@VLocaleMapConfiguration@MapControl@@@std@@@Z; Core::requirePresent<MapControl::LocaleMapConfiguration>(std::shared_ptr<MapControl::LocaleMapConfiguration> const &)
0x180031dba  mov     rdi, rax
0x180031dbd  mov     ecx, 18h; Size
0x180031dc2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180031dc7  mov     r8, rax
0x180031dca  mov     [rsp+150h+var_110], rax
0x180031dcf  lea     rax, ??_7NetworkResponseHeadersWinHttp@Pal@@6B@; const Pal::NetworkResponseHeadersWinHttp::`vftable'
0x180031dd6  mov     [r8], rax
0x180031dd9  lea     rcx, [r8+8]
0x180031ddd  mov     rdx, rdi
0x180031de0  call    ??0?$shared_ptr@VWrlTimerWrapper@Detail@Pal@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Pal::Detail::WrlTimerWrapper>::shared_ptr<Pal::Detail::WrlTimerWrapper>(std::shared_ptr<Pal::Detail::WrlTimerWrapper> const &)
0x180031de5  mov     [rsp+150h+var_110], r8
0x180031dea  lea     rdx, [rsp+150h+var_110]
0x180031def  lea     rcx, [rsp+150h+var_108]
0x180031df4  call    ??$?4U?$default_delete@VNetworkException@Pal@@@std@@$0A@@?$unique_ptr@VNetworkException@Pal@@U?$default_delete@VNetworkException@Pal@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Pal::NetworkException>::operator=<std::default_delete<Pal::NetworkException>,0>(std::unique_ptr<Pal::NetworkException> &&)
0x180031df9  lea     rcx, [rsp+150h+var_110]
0x180031dfe  call    ??1?$unique_ptr@VNetworkRequestImpl@Pal@@U?$default_delete@VNetworkRequestImpl@Pal@@@std@@@std@@QEAA@XZ; std::unique_ptr<Pal::NetworkRequestImpl>::~unique_ptr<Pal::NetworkRequestImpl>(void)
0x180031e03  nop
0x180031e04  lea     rcx, [rsp+150h+var_D8]
0x180031e09  call    ??1?$PresentSharedPtr@V?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@@Core@@QEAA@XZ; Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(void)
0x180031e0e  mov     rax, [rsp+150h+var_108]
0x180031e13  mov     [rsp+150h+var_108], 0
0x180031e1c  mov     [rsp+150h+var_110], rax
0x180031e21  lea     rdx, [rsi+0E0h]
0x180031e28  mov     [rsp+150h+var_128], 0
0x180031e2d  mov     [rsp+150h+var_130], rbx
0x180031e32  lea     r9, [rsp+150h+var_110]
0x180031e37  lea     r8, [rsp+150h+var_E8]
0x180031e3c  lea     rcx, [rbp+50h+var_B0]
0x180031e40  call    ??0NetworkResponse@Pal@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@3@V?$unique_ptr@VNetworkResponseHeaders@Pal@@U?$default_delete@VNetworkResponseHeaders@Pal@@@std@@@3@PEBVNetworkException@1@_N4@Z; Pal::NetworkResponse::NetworkResponse(std::wstring const &,std::shared_ptr<std::vector<uchar> const> const &,std::unique_ptr<Pal::NetworkResponseHeaders>,Pal::NetworkException const *,bool,bool)
0x180031e45  nop
0x180031e46  lea     rcx, [rsi+190h]
0x180031e4d  lea     rdx, [rbp+50h+var_B0]
0x180031e51  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x180031e56  nop
0x180031e57  lea     rcx, [rbp+50h+var_B0]; this
0x180031e5b  call    ??1NetworkResponse@Pal@@QEAA@XZ; Pal::NetworkResponse::~NetworkResponse(void)
0x180031e60  nop
0x180031e61  lea     rcx, [rsp+150h+var_108]
0x180031e66  call    ??1?$unique_ptr@VNetworkRequestImpl@Pal@@U?$default_delete@VNetworkRequestImpl@Pal@@@std@@@std@@QEAA@XZ; std::unique_ptr<Pal::NetworkRequestImpl>::~unique_ptr<Pal::NetworkRequestImpl>(void)
0x180031e6b  nop
0x180031e6c  mov     rcx, r14; lpCriticalSection
0x180031e6f  call    cs:__imp_LeaveCriticalSection
0x180031e75  xorps   xmm0, xmm0
0x180031e78  movdqu  xmmword ptr [rsp+150h+var_F8], xmm0
0x180031e7e  lea     rcx, [rsi+60h]; lpCriticalSection
0x180031e82  call    cs:__imp_EnterCriticalSection
0x180031e88  lea     rcx, [rsi+88h]
0x180031e8f  mov     rdi, [rcx+8]
0x180031e93  mov     qword ptr [rcx], 0
0x180031e9a  mov     qword ptr [rcx+8], 0
0x180031ea2  lea     rdx, [rsp+150h+var_F8]
0x180031ea7  call    ??4?$shared_ptr@VNetworkRequestInternalWinHttp@Pal@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Pal::NetworkRequestInternalWinHttp>::operator=(std::shared_ptr<Pal::NetworkRequestInternalWinHttp> &&)
0x180031eac  lea     rcx, [rsi+60h]; lpCriticalSection
0x180031eb0  call    cs:__imp_LeaveCriticalSection
0x180031eb6  mov     rcx, [rsp+150h+var_F8+8]; this
0x180031ebb  test    rcx, rcx
0x180031ebe  jz      short loc_180031EC5
0x180031ec0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180031ec5  test    rdi, rdi
0x180031ec8  jz      short loc_180031ED3
0x180031eca  mov     rcx, rdi; this
0x180031ecd  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180031ed2  nop
0x180031ed3  lea     rcx, [rsp+150h+var_100]
0x180031ed8  call    ??1?$unique_ptr@VNetworkRequestImpl@Pal@@U?$default_delete@VNetworkRequestImpl@Pal@@@std@@@std@@QEAA@XZ; std::unique_ptr<Pal::NetworkRequestImpl>::~unique_ptr<Pal::NetworkRequestImpl>(void)
0x180031edd  nop
0x180031ede  mov     rcx, [rsp+150h+var_E8+8]; this
0x180031ee3  test    rcx, rcx
0x180031ee6  jz      short loc_180031EED
0x180031ee8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180031eed  mov     rcx, [rbp+50h+var_20]
0x180031ef1  xor     rcx, rsp; StackCookie
0x180031ef4  call    __security_check_cookie
0x180031ef9  lea     r11, [rsp+150h+var_10]
0x180031f01  mov     rbx, [r11+30h]
0x180031f05  mov     rsi, [r11+38h]
0x180031f09  mov     rsp, r11
0x180031f0c  pop     r14
0x180031f0e  pop     rdi
0x180031f0f  pop     rbp
0x180031f10  retn
```
