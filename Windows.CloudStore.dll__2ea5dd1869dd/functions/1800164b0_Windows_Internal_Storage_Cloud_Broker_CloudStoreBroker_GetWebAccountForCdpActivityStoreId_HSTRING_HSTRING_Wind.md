# Windows::Internal::Storage::Cloud::Broker::CloudStoreBroker::GetWebAccountForCdpActivityStoreId(HSTRING__ *,HSTRING__ *,Windows::Security::Credentials::IWebAccount * *)

- ea: `0x1800164b0`
- end: `0x1800169da`
- name: `?GetWebAccountForCdpActivityStoreId@CloudStoreBroker@Broker@Cloud@Storage@Internal@Windows@@UEAAJPEAUHSTRING__@@0PEAPEAUIWebAccount@Credentials@Security@6@@Z`
- size: `1322`
- prototype: `__int64 __fastcall(Windows::Internal::Storage::Cloud::Broker::CloudStoreBroker *this, HSTRING, HSTRING, struct Windows::Security::Credentials::IWebAccount **)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000e84c`
- `0x180015d58`
- `0x180015dbc`
- `0x1800164b0`
- `0x1800169e0`
- `0x180016cf4`
- `0x180019720`
- `0x180021e20`
- `0x1800238d0`
- `0x180023fd4`
- `0x180024fd0`
- `0x18002e010`
- `0x18002ec7c`
- `0x1800313f0`
- `0x180042e50`
- `0x1800f5410`
- `0x1801201a0`
- `0x180208010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800164ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800166b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800164ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800166b1`

## string_xrefs

- `0x180016556`: `Windows.Internal.Security.Authentication.Web.TokenBrokerInternal`
- `0x180016631`: `onecoreuap\shell\cloudstore\store\api\src\cloudstorebroker.cpp`
- `0x180016978`: `onecoreuap\shell\cloudstore\store\api\src\cloudstorebroker.cpp`
- `0x18001698d`: `onecoreuap\shell\cloudstore\store\api\src\cloudstorebroker.cpp`
- `0x1800169a2`: `onecoreuap\shell\cloudstore\store\api\src\cloudstorebroker.cpp`
- `0x1800169b7`: `onecoreuap\shell\cloudstore\store\api\src\cloudstorebroker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::Storage::Cloud::Broker::CloudStoreBroker::GetWebAccountForCdpActivityStoreId(
        Windows::Internal::Storage::Cloud::Broker::CloudStoreBroker *this,
        HSTRING a2,
        HSTRING a3,
        struct Windows::Security::Credentials::IWebAccount **a4)
{
  __int64 v7; // rax
  int v8; // eax
  std::_Ref_count_base *v9; // rcx
  __int64 *v10; // rbx
  int v11; // eax
  unsigned int i; // esi
  __int64 v13; // rax
  int v14; // eax
  const unsigned __int16 *StringRawBuffer; // rax
  struct Windows::Security::Credentials::IWebAccount *v16; // r14
  __int64 ObjectFactory; // rax
  __int64 v18; // rdi
  void (__fastcall *v19)(__int64, std::_Ref_count_base ***, __int64, __int64); // r14
  __int64 v20; // rax
  std::_Ref_count_base *v21; // rax
  int v22; // eax
  struct Windows::Security::Credentials::IWebAccount *v23; // rcx
  unsigned __int8 *v24; // rdi
  __int64 v25; // rax
  int v26; // edx
  int v27; // ecx
  struct Windows::Security::Credentials::IWebAccount *v28; // rcx
  const char *v29; // r9
  __int64 result; // rax
  int v31; // [rsp+20h] [rbp-148h]
  unsigned int v32; // [rsp+34h] [rbp-134h] BYREF
  struct Windows::Security::Credentials::IWebAccount *v33; // [rsp+38h] [rbp-130h] BYREF
  __int64 v34; // [rsp+40h] [rbp-128h] BYREF
  __int64 v35; // [rsp+48h] [rbp-120h] BYREF
  std::_Ref_count_base **v36; // [rsp+50h] [rbp-118h] BYREF
  std::_Ref_count_base *v37; // [rsp+58h] [rbp-110h] BYREF
  char v38; // [rsp+60h] [rbp-108h]
  __int64 *v39; // [rsp+68h] [rbp-100h] BYREF
  _QWORD v40[3]; // [rsp+70h] [rbp-F8h] BYREF
  struct Windows::Security::Credentials::IWebAccount **v41; // [rsp+88h] [rbp-E0h] BYREF
  struct Windows::Security::Credentials::IWebAccount *v42; // [rsp+90h] [rbp-D8h] BYREF
  __m128i si128; // [rsp+98h] [rbp-D0h]
  _QWORD v44[5]; // [rsp+A8h] [rbp-C0h] BYREF
  _BYTE v45[32]; // [rsp+D0h] [rbp-98h] BYREF
  _BYTE v46[32]; // [rsp+F0h] [rbp-78h] BYREF
  PSRWLOCK SRWLock; // [rsp+110h] [rbp-58h]
  std::_Ref_count_base *v48; // [rsp+118h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  *a4 = 0;
  WindowsGetStringRawBuffer(a2, 0);
  try
  {
    std::wstring::wstring();
    WideStringToUtf8String(v44, &v41);
    if ( si128.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>(v41, 2 * si128.m128i_i64[1] + 2);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v41) = 0;
    wil::GetActivationFactory<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics>(
      v40,
      L"Windows.Internal.Security.Authentication.Web.TokenBrokerInternal");
    v35 = 0;
    v7 = *(_QWORD *)v40[0];
    v36 = (std::_Ref_count_base **)&v35;
    v37 = 0;
    v38 = 1;
    v8 = (*(__int64 (__fastcall **)(_QWORD, std::_Ref_count_base **))(v7 + 96))(v40[0], &v37);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x78,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorebroker.cpp",
        (const char *)(unsigned int)v8,
        v31);
    if ( v38 )
    {
      v9 = *v36;
      *v36 = v37;
      if ( v9 )
        (*(void (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v9 + 16LL))(v9);
    }
    wil::wait_for_completion<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *>>>(
      &v39,
      v35);
    v10 = v39;
    v39 = 0;
    v40[2] = v10;
    v32 = 0;
    v11 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v10 + 56))(v10, &v32);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7C,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorebroker.cpp",
        (const char *)(unsigned int)v11,
        v31);
    for ( i = 0; ; ++i )
    {
      if ( i >= v32 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x91,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorebroker.cpp",
          (const char *)0x80070490LL,
          v31);
      v33 = 0;
      v13 = *v10;
      v41 = &v33;
      v42 = 0;
      si128.m128i_i8[0] = 1;
      v14 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, struct Windows::Security::Credentials::IWebAccount **))(v13 + 48))(
              v10,
              i,
              &v42);
      if ( v14 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x80,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorebroker.cpp",
          (const char *)(unsigned int)v14,
          v31);
      if ( si128.m128i_i8[0] )
        wil::com_ptr_t<Windows::Internal::Storage::Cloud::State::ICloudStoreStateManager,wil::err_exception_policy>::attach(
          v41,
          v42);
      StringRawBuffer = WindowsGetStringRawBuffer(a3, 0);
      v16 = v33;
      EffectiveWebAccountContext::EffectiveWebAccountContext(
        (EffectiveWebAccountContext *)v45,
        (Windows::Internal::Storage::Cloud::Broker::CloudStoreBroker *)((char *)this + 88),
        StringRawBuffer);
      wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::operator=(&SRWLock[1], v16);
      ObjectFactory = EffectiveUserContext::GetObjectFactory((char *)this + 88);
      v18 = *(_QWORD *)ObjectFactory;
      v19 = *(void (__fastcall **)(__int64, std::_Ref_count_base ***, __int64, __int64))(**(_QWORD **)ObjectFactory + 8LL);
      v40[1] = v45;
      v20 = EnsureMemberWithReturnType_std::shared_ptr_Windows::Internal::Storage::Cloud::Core::CloudStoreAccount__const___std::shared_ptr_Windows::Internal::Storage::Cloud::Core::CloudStoreAccount___lambda_023b433145e571973f82c66908a08866___(SRWLock);
      v19(v18, &v36, v20, 30000);
      v34 = 0;
      v21 = *v36;
      v41 = (struct Windows::Security::Credentials::IWebAccount **)&v34;
      v42 = 0;
      si128.m128i_i8[0] = 1;
      v22 = (*((__int64 (__fastcall **)(std::_Ref_count_base **, struct Windows::Security::Credentials::IWebAccount **))v21
             + 34))(
              v36,
              &v42);
      if ( v22 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x8A,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorebroker.cpp",
          (const char *)(unsigned int)v22,
          v31);
      if ( si128.m128i_i8[0] )
      {
        v23 = *v41;
        *v41 = v42;
        if ( v23 )
          (*(void (__fastcall **)(struct Windows::Security::Credentials::IWebAccount *))(*(_QWORD *)v23 + 16LL))(v23);
      }
      v24 = (unsigned __int8 *)v44;
      if ( v44[3] > 0xFu )
        v24 = (unsigned __int8 *)v44[0];
      v25 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v34 + 24LL))(v34) - (_QWORD)v24;
      do
      {
        v26 = v24[v25];
        v27 = *v24 - v26;
        if ( v27 )
          break;
        ++v24;
      }
      while ( v26 );
      if ( !v27 )
        break;
      if ( v34 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
      if ( v37 )
        std::_Ref_count_base::_Decref(v37);
      if ( v48 )
        std::_Ref_count_base::_Decref(v48);
      std::wstring::~wstring(v46);
      EffectiveUserContext::~EffectiveUserContext((EffectiveUserContext *)v45);
      if ( v33 )
        (*(void (__fastcall **)(struct Windows::Security::Credentials::IWebAccount *))(*(_QWORD *)v33 + 16LL))(v33);
    }
    v28 = v33;
    if ( v33 )
    {
      *a4 = v33;
      (*(void (__fastcall **)(struct Windows::Security::Credentials::IWebAccount *))(*(_QWORD *)v28 + 8LL))(v28);
    }
    else
    {
      *a4 = 0;
    }
    if ( v34 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    if ( v37 )
      std::_Ref_count_base::_Decref(v37);
    if ( v48 )
      std::_Ref_count_base::_Decref(v48);
    std::wstring::~wstring(v46);
    EffectiveUserContext::~EffectiveUserContext((EffectiveUserContext *)v45);
    if ( v33 )
      (*(void (__fastcall **)(struct Windows::Security::Credentials::IWebAccount *))(*(_QWORD *)v33 + 16LL))(v33);
    (*(void (__fastcall **)(__int64 *))(*v10 + 16))(v10);
    if ( v35 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    if ( v40[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v40[0] + 16LL))(v40[0]);
    std::string::_Tidy_deallocate(v44);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x93,
                           (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorebroker.cpp",
                           v29);
  }
  return result;
}

```

## disassembly

```asm
0x1800164b0  push    rbx
0x1800164b2  push    rsi
0x1800164b3  push    rdi
0x1800164b4  push    r12
0x1800164b6  push    r13
0x1800164b8  push    r14
0x1800164ba  push    r15
0x1800164bc  sub     rsp, 130h
0x1800164c3  mov     rax, cs:__security_cookie
0x1800164ca  xor     rax, rsp
0x1800164cd  mov     [rsp+168h+var_48], rax
0x1800164d5  mov     r15, r9
0x1800164d8  mov     r12, r8
0x1800164db  mov     rax, rdx
0x1800164de  mov     r13, rcx
0x1800164e1  xor     r14d, r14d
0x1800164e4  mov     [r9], r14
0x1800164e7  xor     edx, edx; length
0x1800164e9  mov     rcx, rax; string
0x1800164ec  call    cs:__imp_WindowsGetStringRawBuffer
0x1800164f2  mov     rdx, rax
0x1800164f5  lea     rcx, [rsp+168h+var_E0]
0x1800164fd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180016502  nop
0x180016503  lea     rdx, [rsp+168h+var_E0]
0x18001650b  lea     rcx, [rsp+168h+var_C0]
0x180016513  call    ?WideStringToUtf8String@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; WideStringToUtf8String(std::wstring const &)
0x180016518  nop
0x180016519  mov     rdx, [rsp+168h+var_C8]
0x180016521  cmp     rdx, 7
0x180016525  jbe     short loc_18001653C
0x180016527  lea     rdx, ds:2[rdx*2]
0x18001652f  mov     rcx, [rsp+168h+var_E0]
0x180016537  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001653c  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180016544  movdqu  xmmword ptr [rsp+98h], xmm0
0x18001654d  mov     word ptr [rsp+168h+var_E0], r14w
0x180016556  lea     rdx, ?RuntimeClass_Windows_Internal_Security_Authentication_Web_TokenBrokerInternal@@3QBGB; "Windows.Internal.Security.Authenticatio"...
0x18001655d  lea     rcx, [rsp+168h+var_F8]
0x180016562  call    ??$GetActivationFactory@UITokenBrokerInternalStatics@Web@Authentication@Security@Internal@Windows@@@wil@@YA?AV?$com_ptr_t@UITokenBrokerInternalStatics@Web@Authentication@Security@Internal@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics>(ushort const *)
0x180016567  nop
0x180016568  mov     [rsp+168h+var_120], r14
0x18001656d  mov     rcx, [rsp+168h+var_F8]
0x180016572  mov     rax, [rcx]
0x180016575  lea     rdx, [rsp+168h+var_120]
0x18001657a  mov     [rsp+168h+var_118], rdx
0x18001657f  mov     [rsp+168h+var_110], r14
0x180016584  mov     [rsp+168h+var_108], 1
0x180016589  lea     rdx, [rsp+168h+var_110]
0x18001658e  mov     rax, [rax+60h]
0x180016592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016597  mov     rcx, [rsp+168h]; this
0x18001659f  test    eax, eax
0x1800165a1  js      loc_180016975
0x1800165a7  cmp     [rsp+168h+var_108], r14b
0x1800165ac  jz      short loc_1800165D0
0x1800165ae  mov     rdx, [rsp+168h+var_110]
0x1800165b3  mov     rax, [rsp+168h+var_118]
0x1800165b8  mov     rcx, [rax]
0x1800165bb  mov     [rax], rdx
0x1800165be  test    rcx, rcx
0x1800165c1  jz      short loc_1800165D0
0x1800165c3  mov     rax, [rcx]
0x1800165c6  mov     rax, [rax+10h]
0x1800165ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165cf  nop
0x1800165d0  mov     rdx, [rsp+168h+var_120]
0x1800165d5  lea     rcx, [rsp+168h+var_100]
0x1800165da  call    ??$wait_for_completion@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@V?$ComPtr@U?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@wil@@YA?AV?$ComPtr@U?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@PEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@@Z; wil::wait_for_completion<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *>>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *> *,tagCOWAIT_FLAGS)
0x1800165df  mov     rbx, [rsp+168h+var_100]
0x1800165e4  mov     [rsp+168h+var_100], r14
0x1800165e9  mov     [rsp+168h+var_E8], rbx
0x1800165f1  mov     [rsp+168h+var_134], r14d
0x1800165f6  mov     rax, [rbx]
0x1800165f9  lea     rdx, [rsp+168h+var_134]
0x1800165fe  mov     rcx, rbx
0x180016601  mov     rax, [rax+38h]
0x180016605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001660a  mov     rcx, [rsp+168h]; this
0x180016612  test    eax, eax
0x180016614  js      loc_18001698A
0x18001661a  mov     esi, r14d
0x18001661d  cmp     esi, [rsp+168h+var_134]
0x180016621  jb      short loc_180016642
0x180016623  mov     rcx, [rsp+168h]; this
0x18001662b  mov     r9d, 80070490h; char *
0x180016631  lea     r8, aOnecoreuapShel_41; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x180016638  mov     edx, 91h; void *
0x18001663d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180016642  mov     [rsp+168h+var_130], r14
0x180016647  mov     rax, [rbx]
0x18001664a  lea     rcx, [rsp+168h+var_130]
0x18001664f  mov     [rsp+168h+var_E0], rcx
0x180016657  mov     [rsp+168h+var_D8], r14
0x18001665f  mov     [rsp+168h+var_D0], 1
0x180016667  lea     r8, [rsp+168h+var_D8]
0x18001666f  mov     edx, esi
0x180016671  mov     rcx, rbx
0x180016674  mov     rax, [rax+30h]
0x180016678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001667d  mov     rcx, [rsp+168h]; this
0x180016685  test    eax, eax
0x180016687  js      loc_18001699F
0x18001668d  cmp     [rsp+168h+var_D0], r14b
0x180016695  jz      short loc_1800166AC
0x180016697  mov     rdx, [rsp+168h+var_D8]
0x18001669f  mov     rcx, [rsp+168h+var_E0]
0x1800166a7  call    ?attach@?$com_ptr_t@VICloudStoreStateManager@State@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAXPEAVICloudStoreStateManager@State@Cloud@Storage@Internal@Windows@@@Z; wil::com_ptr_t<Windows::Internal::Storage::Cloud::State::ICloudStoreStateManager,wil::err_exception_policy>::attach(Windows::Internal::Storage::Cloud::State::ICloudStoreStateManager *)
0x1800166ac  xor     edx, edx; length
0x1800166ae  mov     rcx, r12; string
0x1800166b1  call    cs:__imp_WindowsGetStringRawBuffer
0x1800166b7  mov     r14, [rsp+168h+var_130]
0x1800166bc  mov     r8, rax; unsigned __int16 *
0x1800166bf  lea     rdx, [r13+58h]; struct EffectiveUserContext *
0x1800166c3  lea     rcx, [rsp+168h+var_98]; this
0x1800166cb  call    ??0EffectiveWebAccountContext@@AEAA@AEBVEffectiveUserContext@@PEBG@Z; EffectiveWebAccountContext::EffectiveWebAccountContext(EffectiveUserContext const &,ushort const *)
0x1800166d0  mov     rcx, [rsp+168h+SRWLock]
0x1800166d8  add     rcx, 8
0x1800166dc  mov     rdx, r14
0x1800166df  call    ??4?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@PEAUIWebAccount@Credentials@Security@Windows@@@Z; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::operator=(Windows::Security::Credentials::IWebAccount *)
0x1800166e4  nop
0x1800166e5  lea     rcx, [r13+58h]
0x1800166e9  call    ?GetObjectFactory@EffectiveUserContext@@QEBAAEBV?$shared_ptr@VUserObjectFactory@Core@Cloud@Storage@Internal@Windows@@@std@@XZ; EffectiveUserContext::GetObjectFactory(void)
0x1800166ee  mov     rdi, [rax]
0x1800166f1  mov     rax, [rdi]
0x1800166f4  mov     r14, [rax+8]
0x1800166f8  lea     rax, [rsp+168h+var_98]
0x180016700  mov     [rsp+168h+var_F0], rax
0x180016705  mov     rcx, [rsp+168h+SRWLock]; SRWLock
0x18001670d  mov     [rsp+168h+var_138], 0
0x180016712  lea     rdx, [rcx+10h]
0x180016716  lea     r9, [rsp+168h+var_F0]
0x18001671b  lea     r8, [rsp+168h+var_138]
0x180016720  call    EnsureMemberWithReturnType_std__shared_ptr_Windows__Internal__Storage__Cloud__Core__CloudStoreAccount__const___std__shared_ptr_Windows__Internal__Storage__Cloud__Core__CloudStoreAccount___lambda_023b433145e571973f82c66908a08866___
0x180016725  mov     r9d, 7530h
0x18001672b  mov     r8, rax
0x18001672e  lea     rdx, [rsp+168h+var_118]
0x180016733  mov     rcx, rdi
0x180016736  mov     rax, r14
0x180016739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001673e  nop
0x18001673f  xor     r14d, r14d
0x180016742  mov     [rsp+168h+var_128], r14
0x180016747  mov     rcx, [rsp+168h+var_118]
0x18001674c  mov     rax, [rcx]
0x18001674f  lea     rdx, [rsp+168h+var_128]
0x180016754  mov     [rsp+168h+var_E0], rdx
0x18001675c  mov     [rsp+168h+var_D8], r14
0x180016764  mov     [rsp+168h+var_D0], 1
0x18001676c  lea     rdx, [rsp+168h+var_D8]
0x180016774  mov     rax, [rax+110h]
0x18001677b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016780  mov     rcx, [rsp+168h]; this
0x180016788  test    eax, eax
0x18001678a  js      loc_1800169B4
0x180016790  cmp     [rsp+168h+var_D0], r14b
0x180016798  jz      short loc_1800167C2
0x18001679a  mov     rdx, [rsp+168h+var_D8]
0x1800167a2  mov     rax, [rsp+168h+var_E0]
0x1800167aa  mov     rcx, [rax]
0x1800167ad  mov     [rax], rdx
0x1800167b0  test    rcx, rcx
0x1800167b3  jz      short loc_1800167C2
0x1800167b5  mov     rax, [rcx]
0x1800167b8  mov     rax, [rax+10h]
0x1800167bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167c1  nop
0x1800167c2  mov     rcx, [rsp+168h+var_128]
0x1800167c7  lea     rdi, [rsp+168h+var_C0]
0x1800167cf  cmp     [rsp+168h+var_A8], 0Fh
0x1800167d8  cmova   rdi, [rsp+168h+var_C0]
0x1800167e1  mov     rax, [rcx]
0x1800167e4  mov     rax, [rax+18h]
0x1800167e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167ed  sub     rax, rdi
0x1800167f0  movzx   ecx, byte ptr [rdi]
0x1800167f3  movzx   edx, byte ptr [rdi+rax]
0x1800167f7  sub     ecx, edx
0x1800167f9  jnz     short loc_180016802
0x1800167fb  inc     rdi
0x1800167fe  test    edx, edx
0x180016800  jnz     short loc_1800167F0
0x180016802  test    ecx, ecx
0x180016804  jnz     loc_180016903
0x18001680a  mov     rcx, [rsp+168h+var_130]
0x18001680f  test    rcx, rcx
0x180016812  jz      loc_1800169C9
0x180016818  mov     [r15], rcx
0x18001681b  mov     rax, [rcx]
0x18001681e  mov     rax, [rax+8]
0x180016822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016827  nop
0x180016828  mov     rcx, [rsp+168h+var_128]
0x18001682d  test    rcx, rcx
0x180016830  jz      short loc_18001683F
0x180016832  mov     rax, [rcx]
0x180016835  mov     rax, [rax+10h]
0x180016839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001683e  nop
0x18001683f  mov     rcx, [rsp+168h+var_110]; this
0x180016844  test    rcx, rcx
0x180016847  jz      short loc_18001684F
0x180016849  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001684e  nop
0x18001684f  mov     rcx, [rsp+168h+var_50]; this
0x180016857  test    rcx, rcx
0x18001685a  jz      short loc_180016861
0x18001685c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180016861  lea     rcx, [rsp+168h+var_78]
0x180016869  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001686e  lea     rcx, [rsp+168h+var_98]; this
0x180016876  call    ??1EffectiveUserContext@@QEAA@XZ; EffectiveUserContext::~EffectiveUserContext(void)
0x18001687b  nop
0x18001687c  mov     rcx, [rsp+168h+var_130]
0x180016881  test    rcx, rcx
0x180016884  jz      short loc_180016893
0x180016886  mov     rax, [rcx]
0x180016889  mov     rax, [rax+10h]
0x18001688d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016892  nop
0x180016893  mov     rax, [rbx]
0x180016896  mov     rcx, rbx
0x180016899  mov     rax, [rax+10h]
0x18001689d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168a2  nop
0x1800168a3  mov     rcx, [rsp+168h+var_120]
0x1800168a8  test    rcx, rcx
0x1800168ab  jz      short loc_1800168BA
0x1800168ad  mov     rax, [rcx]
0x1800168b0  mov     rax, [rax+10h]
0x1800168b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168b9  nop
0x1800168ba  mov     rcx, [rsp+168h+var_F8]
0x1800168bf  test    rcx, rcx
0x1800168c2  jz      short loc_1800168D1
0x1800168c4  mov     rax, [rcx]
0x1800168c7  mov     rax, [rax+10h]
0x1800168cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168d0  nop
0x1800168d1  lea     rcx, [rsp+168h+var_C0]; void *
0x1800168d9  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800168de  xor     eax, eax
0x1800168e0  mov     rcx, [rsp+168h+var_48]
0x1800168e8  xor     rcx, rsp; StackCookie
0x1800168eb  call    __security_check_cookie
0x1800168f0  add     rsp, 130h
0x1800168f7  pop     r15
0x1800168f9  pop     r14
0x1800168fb  pop     r13
0x1800168fd  pop     r12
0x1800168ff  pop     rdi
0x180016900  pop     rsi
0x180016901  pop     rbx
0x180016902  retn
0x180016903  mov     rcx, [rsp+168h+var_128]
0x180016908  test    rcx, rcx
0x18001690b  jz      short loc_18001691A
0x18001690d  mov     rax, [rcx]
0x180016910  mov     rax, [rax+10h]
0x180016914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016919  nop
0x18001691a  mov     rcx, [rsp+168h+var_110]; this
0x18001691f  test    rcx, rcx
0x180016922  jz      short loc_18001692A
0x180016924  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180016929  nop
0x18001692a  mov     rcx, [rsp+168h+var_50]; this
0x180016932  test    rcx, rcx
0x180016935  jz      short loc_18001693C
0x180016937  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001693c  lea     rcx, [rsp+168h+var_78]
0x180016944  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180016949  lea     rcx, [rsp+168h+var_98]; this
0x180016951  call    ??1EffectiveUserContext@@QEAA@XZ; EffectiveUserContext::~EffectiveUserContext(void)
0x180016956  nop
0x180016957  mov     rcx, [rsp+168h+var_130]
0x18001695c  test    rcx, rcx
0x18001695f  jz      short loc_18001696E
0x180016961  mov     rax, [rcx]
0x180016964  mov     rax, [rax+10h]
0x180016968  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001696d  nop
0x18001696e  inc     esi
0x180016970  jmp     loc_18001661D
0x180016975  mov     r9d, eax; char *
0x180016978  lea     r8, aOnecoreuapShel_41; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18001697f  mov     edx, 78h ; 'x'; void *
0x180016984  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001698a  mov     r9d, eax; char *
0x18001698d  lea     r8, aOnecoreuapShel_41; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x180016994  mov     edx, 7Ch ; '|'; void *
0x180016999  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001699f  mov     r9d, eax; char *
0x1800169a2  lea     r8, aOnecoreuapShel_41; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x1800169a9  mov     edx, 80h; void *
0x1800169ae  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800169b4  mov     r9d, eax; char *
0x1800169b7  lea     r8, aOnecoreuapShel_41; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x1800169be  mov     edx, 8Ah; void *
0x1800169c3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
  ... truncated ...
```
