# Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::RequestConsentFromUser(unsigned __int64,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,DeviceAccessConsentType)

- ea: `0x180070824`
- end: `0x180070c59`
- name: `?RequestConsentFromUser@CapabilityAccessManager@Private@CapabilityAccess@Internal@Windows@@QEAA?AW4CapabilityConsentValue@2345@_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N1W4DeviceAccessConsentType@@@Z`
- size: `1077`
- prototype: ``
- caller_count: `2`
- callee_count: `27`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006c2bc`
- `0x18006f230`

## callees

- `0x1800094c0`
- `0x18001649c`
- `0x180016d54`
- `0x18001c3b4`
- `0x18001d00c`
- `0x18001f5f4`
- `0x180020fcc`
- `0x18002392c`
- `0x1800257a4`
- `0x180025b6c`
- `0x180029408`
- `0x18002949c`
- `0x18002e704`
- `0x18002f978`
- `0x180044930`
- `0x1800581a8`
- `0x1800652f0`
- `0x180065774`
- `0x180066f0c`
- `0x18006e8c0`
- `0x18006e8f0`
- `0x18006ecc8`
- `0x180070124`
- `0x180070824`
- `0x180071430`
- `0x1800719f8`
- `0x1800c7010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180070ac4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180070ac4`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x1800709fa`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x1800709fa`

## string_xrefs

- `0x180070bf0`: `onecore\base\devices\cam\core\capabilityaccessmanager.cpp`
- `0x180070c08`: `onecore\base\devices\cam\core\capabilityaccessmanager.cpp`
- `0x180070c1d`: `onecore\base\devices\cam\core\capabilityaccessmanager.cpp`
- `0x180070c32`: `onecore\base\devices\cam\core\capabilityaccessmanager.cpp`
- `0x180070c47`: `onecore\base\devices\cam\core\capabilityaccessmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::RequestConsentFromUser(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        char a4,
        __int64 a5,
        int a6)
{
  __int64 v9; // rax
  unsigned int ConsentResponse; // ebx
  Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager *v11; // rcx
  int ConsentPromptObject; // eax
  __int64 v13; // rdx
  __int64 v14; // rdx
  Windows::Internal::CapabilityAccess::Private *v15; // rcx
  int v16; // eax
  int v17; // esi
  bool IsSystemXbox; // al
  int v19; // eax
  struct IDeviceConsentProvider *v20; // rbx
  __int64 v21; // rax
  int v22; // eax
  __int64 v23; // rbx
  unsigned int v24; // r8d
  int v25; // r9d
  int v27; // [rsp+20h] [rbp-E0h]
  struct IDeviceConsentProvider *v28; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v29; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v30; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v31[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v32; // [rsp+68h] [rbp-98h] BYREF
  __int128 v33; // [rsp+78h] [rbp-88h]
  __int128 v34; // [rsp+88h] [rbp-78h]
  __int64 v35; // [rsp+98h] [rbp-68h]
  _BYTE v36[8]; // [rsp+A0h] [rbp-60h] BYREF
  std::_Ref_count_base *v37; // [rsp+A8h] [rbp-58h]
  _OWORD v38[2]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v39[16]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v40; // [rsp+F0h] [rbp-10h]
  _BYTE v41[40]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v42[32]; // [rsp+120h] [rbp+20h] BYREF
  int v43; // [rsp+140h] [rbp+40h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v30 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_5da0b0c25a7f3c0e58e9dfe16e60c1dc_Traceguids);
  }
  v29 = 0;
  v9 = *(_QWORD *)(a1 + 128);
  if ( v9 && *(_BYTE *)(v9 + 152) )
  {
    if ( !*(_DWORD *)(v9 + 148) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8AA,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanager.cpp",
        (const char *)0x80070057LL,
        v27);
    std::enable_shared_from_this<Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager>::shared_from_this(
      a1 + 8,
      v36);
    std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
      v39,
      v36);
    v40 = v30;
    std::wstring::wstring(v41, a3);
    v41[32] = a4;
    std::wstring::wstring(v42, a5);
    v43 = a6;
    std::thread::thread__lambda_da9a721693307c798dff4ae75b69f353__0_(v31, v39);
    lambda_da9a721693307c798dff4ae75b69f353_::__lambda_da9a721693307c798dff4ae75b69f353_(v39);
    std::thread::detach((std::thread *)v31);
    ConsentResponse = *(_DWORD *)(*(_QWORD *)(a1 + 128) + 148LL);
    std::thread::~thread((std::thread *)v31);
    if ( v37 )
      std::_Ref_count_base::_Decref(v37);
  }
  else
  {
    v28 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
    ConsentPromptObject = Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::GetConsentPromptObject(
                            v11,
                            &v28);
    if ( ConsentPromptObject < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x91A,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanager.cpp",
        (const char *)(unsigned int)ConsentPromptObject,
        v27);
    v38[0] = 0;
    v38[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v38[0]) = 0;
    v13 = *(_QWORD *)(a1 + 128);
    if ( !v13 || (v14 = v13 + 104, !*(_QWORD *)(v14 + 16)) )
      v14 = a1 + 296;
    std::wstring::operator=(v38, v14);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline>::GetImpl'::`2'::impl)
      && *(_BYTE *)(a1 + 40) )
    {
      v16 = UMgrQueryUserContext(*(_QWORD *)(*(_QWORD *)(a1 + 80) + 240LL), &v30);
      v15 = retaddr;
      if ( v16 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x93A,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanager.cpp",
          (const char *)(unsigned int)v16,
          v27);
      v17 = 0;
    }
    else
    {
      v17 = *(_DWORD *)(a1 + 48);
    }
    v32 = 0;
    v33 = 0;
    v34 = 0;
    v35 = 0;
    DWORD2(v32) = a6;
    HIDWORD(v33) = *(unsigned __int8 *)(a1 + 30);
    if ( !a4
      || (IsSystemXbox = Windows::Internal::CapabilityAccess::Private::IsSystemXbox(v15), DWORD1(v34) = 1, !IsSystemXbox) )
    {
      DWORD1(v34) = 0;
    }
    DWORD2(v33) = 0;
    *(_QWORD *)&v32 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v38);
    LODWORD(v34) = Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::MustShowUsernameInConsentPrompt();
    *(_QWORD *)&v33 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3);
    *((_QWORD *)&v34 + 1) = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a5);
    LODWORD(v35) = Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::GetDeviceConsentAppType(a1);
    v19 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::CapabilityAccess::Private::ConsentProviderCallback,IConsentResponseCallback,>(&v29);
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x951,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanager.cpp",
        (const char *)(unsigned int)v19,
        v27);
    AcquireSRWLockExclusive(&Windows::Internal::CapabilityAccess::Private::Globals::SrwLockManager::m_consentPromptLock);
    v31[0] = &Windows::Internal::CapabilityAccess::Private::Globals::SrwLockManager::m_consentPromptLock;
    v20 = v28;
    v21 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 168);
    v22 = (*(__int64 (__fastcall **)(struct IDeviceConsentProvider *, __int64, __int64, __int128 *))(*(_QWORD *)v20 + 24LL))(
            v20,
            v30,
            v21,
            &v32);
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x95F,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanager.cpp",
        (const char *)(unsigned int)v22,
        v17);
    v23 = v29;
    std::wstring::wstring(v36, L"Waiting for consent response");
    std::wstring::_Tidy_deallocate(v36);
    if ( wil::handle_wait(*(wil **)(v23 + 48), (void *)0xFFFFFFFFLL, v24, v25) )
    {
      ConsentResponse = Windows::Internal::CapabilityAccess::Private::ConsentProviderCallback::GetConsentResponse(v23);
      std::wstring::wstring(v36, L"Returning with '%ws'");
      std::wstring::_Tidy_deallocate(v36);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v31);
      std::wstring::_Tidy_deallocate(v38);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
    }
    else
    {
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v31);
      std::wstring::_Tidy_deallocate(v38);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
      ConsentResponse = 3;
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
  return ConsentResponse;
}

```

## disassembly

```asm
0x180070824  mov     [rsp-8+arg_18], rbx
0x180070829  push    rbp
0x18007082a  push    rsi
0x18007082b  push    rdi
0x18007082c  push    r14
0x18007082e  push    r15
0x180070830  lea     rbp, [rsp-60h]
0x180070835  sub     rsp, 160h
0x18007083c  mov     rax, cs:__security_cookie
0x180070843  xor     rax, rsp
0x180070846  mov     [rbp+80h+var_30], rax
0x18007084a  mov     bl, r9b
0x18007084d  mov     r14, r8
0x180070850  mov     rdi, rcx
0x180070853  mov     [rsp+180h+var_130], rdx
0x180070858  mov     r15, [rbp+80h+arg_20]
0x18007085f  lea     rax, WPP_GLOBAL_Control
0x180070866  mov     rcx, cs:WPP_GLOBAL_Control
0x18007086d  cmp     rcx, rax
0x180070870  jz      short loc_180070893
0x180070872  test    byte ptr [rcx+1Ch], 1
0x180070876  jz      short loc_180070893
0x180070878  cmp     byte ptr [rcx+19h], 5
0x18007087c  jb      short loc_180070893
0x18007087e  mov     edx, 24h ; '$'
0x180070883  lea     r8, WPP_5da0b0c25a7f3c0e58e9dfe16e60c1dc_Traceguids
0x18007088a  mov     rcx, [rcx+10h]
0x18007088e  call    WPP_SF_
0x180070893  mov     [rsp+180h+var_138], 0
0x18007089c  mov     rax, [rdi+80h]
0x1800708a3  test    rax, rax
0x1800708a6  jz      loc_180070968
0x1800708ac  cmp     byte ptr [rax+98h], 0
0x1800708b3  jz      loc_180070968
0x1800708b9  mov     rcx, [rbp+88h]; this
0x1800708c0  cmp     dword ptr [rax+94h], 0
0x1800708c7  jz      loc_180070C02
0x1800708cd  lea     rcx, [rdi+8]
0x1800708d1  lea     rdx, [rbp+80h+var_E0]
0x1800708d5  call    ?shared_from_this@?$enable_shared_from_this@VCapabilityAccessManager@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA?AV?$shared_ptr@VCapabilityAccessManager@Private@CapabilityAccess@Internal@Windows@@@2@XZ; std::enable_shared_from_this<Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager>::shared_from_this(void)
0x1800708da  nop
0x1800708db  lea     rdx, [rbp+80h+var_E0]
0x1800708df  lea     rcx, [rbp+80h+var_A0]
0x1800708e3  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x1800708e8  nop
0x1800708e9  mov     rax, [rsp+180h+var_130]
0x1800708ee  mov     [rbp+80h+var_90], rax
0x1800708f2  mov     rdx, r14
0x1800708f5  lea     rcx, [rbp+80h+var_88]
0x1800708f9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800708fe  nop
0x1800708ff  mov     [rbp+80h+var_68], bl
0x180070902  mov     rdx, r15
0x180070905  lea     rcx, [rbp+80h+var_60]
0x180070909  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18007090e  mov     eax, [rbp+80h+arg_28]
0x180070914  mov     [rbp+80h+var_40], eax
0x180070917  lea     rdx, [rbp+80h+var_A0]
0x18007091b  lea     rcx, [rsp+180h+var_128]
0x180070920  call    std__thread__thread__lambda_da9a721693307c798dff4ae75b69f353__0_
0x180070925  nop
0x180070926  lea     rcx, [rbp+80h+var_A0]
0x18007092a  call    _lambda_da9a721693307c798dff4ae75b69f353_____lambda_da9a721693307c798dff4ae75b69f353_
0x18007092f  lea     rcx, [rsp+180h+var_128]; this
0x180070934  call    ?detach@thread@std@@QEAAXXZ; std::thread::detach(void)
0x180070939  mov     rax, [rdi+80h]
0x180070940  mov     ebx, [rax+94h]
0x180070946  lea     rcx, [rsp+180h+var_128]; this
0x18007094b  call    ??1thread@std@@QEAA@XZ; std::thread::~thread(void)
0x180070950  nop
0x180070951  mov     rcx, [rbp+80h+var_D8]; this
0x180070955  test    rcx, rcx
0x180070958  jz      loc_180070BBE
0x18007095e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180070963  jmp     loc_180070BBE
0x180070968  mov     [rsp+180h+var_140], 0
0x180070971  lea     rcx, [rsp+180h+var_140]
0x180070976  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007097b  lea     rdx, [rsp+180h+var_140]; struct IDeviceConsentProvider **
0x180070980  call    ?GetConsentPromptObject@CapabilityAccessManager@Private@CapabilityAccess@Internal@Windows@@QEAAJPEAPEAUIDeviceConsentProvider@@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::GetConsentPromptObject(IDeviceConsentProvider * *)
0x180070985  mov     rcx, [rbp+88h]; this
0x18007098c  test    eax, eax
0x18007098e  js      loc_180070C1A
0x180070994  xorps   xmm0, xmm0
0x180070997  movups  [rbp+80h+var_C0], xmm0
0x18007099b  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800709a3  movdqu  [rbp+80h+var_B0], xmm1
0x1800709a8  xor     eax, eax
0x1800709aa  mov     word ptr [rbp+80h+var_C0], ax
0x1800709ae  mov     rdx, [rdi+80h]
0x1800709b5  test    rdx, rdx
0x1800709b8  jz      short loc_1800709C4
0x1800709ba  add     rdx, 68h ; 'h'
0x1800709be  cmp     [rdx+10h], rax
0x1800709c2  jnz     short loc_1800709CB
0x1800709c4  lea     rdx, [rdi+128h]
0x1800709cb  lea     rcx, [rbp+80h+var_C0]
0x1800709cf  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800709d4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline> `wil::Feature<__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline>::GetImpl(void)'::`2'::impl
0x1800709db  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline>::__private_IsEnabled(void)
0x1800709e0  test    al, al
0x1800709e2  jz      short loc_180070A13
0x1800709e4  cmp     byte ptr [rdi+28h], 0
0x1800709e8  jz      short loc_180070A13
0x1800709ea  mov     rcx, [rdi+50h]
0x1800709ee  lea     rdx, [rsp+180h+var_130]
0x1800709f3  mov     rcx, [rcx+0F0h]
0x1800709fa  call    cs:__imp_UMgrQueryUserContext
0x180070a00  mov     rcx, [rbp+88h]; this
0x180070a07  test    eax, eax
0x180070a09  js      loc_180070C2F
0x180070a0f  xor     esi, esi
0x180070a11  jmp     short loc_180070A16
0x180070a13  mov     esi, [rdi+30h]
0x180070a16  xorps   xmm0, xmm0
0x180070a19  xor     eax, eax
0x180070a1b  movups  [rsp+180h+var_118], xmm0
0x180070a20  movups  [rsp+180h+var_108], xmm0
0x180070a25  movups  [rbp+80h+var_F8], xmm0
0x180070a29  mov     [rbp+80h+var_E8], rax
0x180070a2d  mov     eax, [rbp+80h+arg_28]
0x180070a33  mov     dword ptr [rsp+180h+var_118+8], eax
0x180070a37  movzx   eax, byte ptr [rdi+1Eh]
0x180070a3b  mov     dword ptr [rbp+80h+var_108+0Ch], eax
0x180070a3e  test    bl, bl
0x180070a40  jz      short loc_180070A52
0x180070a42  call    ?IsSystemXbox@Private@CapabilityAccess@Internal@Windows@@YA_NXZ; Windows::Internal::CapabilityAccess::Private::IsSystemXbox(void)
0x180070a47  test    al, al
0x180070a49  mov     dword ptr [rbp+80h+var_F8+4], 1
0x180070a50  jnz     short loc_180070A59
0x180070a52  mov     dword ptr [rbp+80h+var_F8+4], 0
0x180070a59  mov     dword ptr [rbp+80h+var_108+8], 0
0x180070a60  lea     rcx, [rbp+80h+var_C0]
0x180070a64  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180070a69  mov     qword ptr [rsp+180h+var_118], rax
0x180070a6e  call    ?MustShowUsernameInConsentPrompt@CapabilityAccessManager@Private@CapabilityAccess@Internal@Windows@@CA_NXZ; Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::MustShowUsernameInConsentPrompt(void)
0x180070a73  xor     ecx, ecx
0x180070a75  test    al, al
0x180070a77  setnz   cl
0x180070a7a  mov     dword ptr [rbp+80h+var_F8], ecx
0x180070a7d  mov     rcx, r14
0x180070a80  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180070a85  mov     qword ptr [rsp+180h+var_108], rax
0x180070a8a  mov     rcx, r15
0x180070a8d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180070a92  mov     qword ptr [rbp+80h+var_F8+8], rax
0x180070a96  mov     rcx, rdi
0x180070a99  call    ?GetDeviceConsentAppType@CapabilityAccessManager@Private@CapabilityAccess@Internal@Windows@@AEAA?AW4__MIDL_IDeviceConsentProvider_0001@@XZ; Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::GetDeviceConsentAppType(void)
0x180070a9e  mov     dword ptr [rbp+80h+var_E8], eax
0x180070aa1  lea     rcx, [rsp+180h+var_138]
0x180070aa6  call    ??$MakeAndInitialize@VConsentProviderCallback@Private@CapabilityAccess@Internal@Windows@@UIConsentResponseCallback@@$$V@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@UIConsentResponseCallback@@@WRL@Microsoft@@@012@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::CapabilityAccess::Private::ConsentProviderCallback,IConsentResponseCallback,>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IConsentResponseCallback>>)
0x180070aab  mov     rcx, [rbp+88h]; this
0x180070ab2  test    eax, eax
0x180070ab4  js      loc_180070C44
0x180070aba  lea     rbx, ?m_consentPromptLock@SrwLockManager@Globals@Private@CapabilityAccess@Internal@Windows@@0Vsrwlock@wil@@A; wil::srwlock Windows::Internal::CapabilityAccess::Private::Globals::SrwLockManager::m_consentPromptLock
0x180070ac1  mov     rcx, rbx; SRWLock
0x180070ac4  call    cs:__imp_AcquireSRWLockExclusive
0x180070aca  mov     [rsp+180h+var_128], rbx
0x180070acf  mov     rbx, [rsp+180h+var_140]
0x180070ad4  mov     r8, [rsp+180h+var_138]
0x180070ad9  lea     rcx, [rdi+0A8h]
0x180070ae0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180070ae5  mov     r10, rax
0x180070ae8  mov     rax, [rbx]
0x180070aeb  mov     r11, [rax+18h]
0x180070aef  mov     [rsp+180h+var_150], r8
0x180070af4  mov     eax, [rdi+34h]
0x180070af7  mov     [rsp+180h+var_158], eax
0x180070afb  mov     [rsp+180h+var_160], esi; int
0x180070aff  lea     r9, [rsp+180h+var_118]
0x180070b04  mov     r8, r10
0x180070b07  mov     rdx, [rsp+180h+var_130]
0x180070b0c  mov     rcx, rbx
0x180070b0f  mov     rax, r11
0x180070b12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070b17  mov     rcx, [rbp+88h]; this
0x180070b1e  test    eax, eax
0x180070b20  js      loc_180070BED
0x180070b26  mov     rbx, [rsp+180h+var_138]
0x180070b2b  lea     rdx, aWaitingForCons; "Waiting for consent response"
0x180070b32  lea     rcx, [rbp+80h+var_E0]
0x180070b36  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180070b3b  lea     rcx, [rbp+80h+var_E0]
0x180070b3f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180070b44  or      edx, 0FFFFFFFFh; void *
0x180070b47  mov     rcx, [rbx+30h]; this
0x180070b4b  call    ?handle_wait@wil@@YA_NPEAXKH@Z; wil::handle_wait(void *,ulong,int)
0x180070b50  test    al, al
0x180070b52  jnz     short loc_180070B7A
0x180070b54  lea     rcx, [rsp+180h+var_128]
0x180070b59  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180070b5e  nop
0x180070b5f  lea     rcx, [rbp+80h+var_C0]
0x180070b63  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180070b68  nop
0x180070b69  lea     rcx, [rsp+180h+var_140]
0x180070b6e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180070b73  mov     ebx, 3
0x180070b78  jmp     short loc_180070BBE
0x180070b7a  mov     rcx, rbx
0x180070b7d  call    ?GetConsentResponse@ConsentProviderCallback@Private@CapabilityAccess@Internal@Windows@@QEAA?AW4CapabilityConsentValue@2345@XZ; Windows::Internal::CapabilityAccess::Private::ConsentProviderCallback::GetConsentResponse(void)
0x180070b82  mov     ebx, eax
0x180070b84  lea     rdx, aReturningWithW; "Returning with '%ws'"
0x180070b8b  lea     rcx, [rbp+80h+var_E0]
0x180070b8f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180070b94  lea     rcx, [rbp+80h+var_E0]
0x180070b98  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180070b9d  nop
0x180070b9e  lea     rcx, [rsp+180h+var_128]
0x180070ba3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180070ba8  nop
0x180070ba9  lea     rcx, [rbp+80h+var_C0]
0x180070bad  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180070bb2  nop
0x180070bb3  lea     rcx, [rsp+180h+var_140]
0x180070bb8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180070bbd  nop
0x180070bbe  lea     rcx, [rsp+180h+var_138]
0x180070bc3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180070bc8  mov     eax, ebx
0x180070bca  mov     rcx, [rbp+80h+var_30]
0x180070bce  xor     rcx, rsp; StackCookie
0x180070bd1  call    __security_check_cookie
0x180070bd6  mov     rbx, [rsp+180h+arg_18]
0x180070bde  add     rsp, 160h
0x180070be5  pop     r15
0x180070be7  pop     r14
0x180070be9  pop     rdi
0x180070bea  pop     rsi
0x180070beb  pop     rbp
0x180070bec  retn
0x180070bed  mov     r9d, eax; char *
0x180070bf0  lea     r8, aOnecoreBaseDev_58; "onecore\\base\\devices\\cam\\core\\capa"...
0x180070bf7  mov     edx, 95Fh; void *
0x180070bfc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180070c02  mov     r9d, 80070057h; char *
0x180070c08  lea     r8, aOnecoreBaseDev_58; "onecore\\base\\devices\\cam\\core\\capa"...
0x180070c0f  mov     edx, 8AAh; void *
0x180070c14  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180070c1a  mov     r9d, eax; char *
0x180070c1d  lea     r8, aOnecoreBaseDev_58; "onecore\\base\\devices\\cam\\core\\capa"...
0x180070c24  mov     edx, 91Ah; void *
0x180070c29  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180070c2f  mov     r9d, eax; char *
0x180070c32  lea     r8, aOnecoreBaseDev_58; "onecore\\base\\devices\\cam\\core\\capa"...
0x180070c39  mov     edx, 93Ah; void *
0x180070c3e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180070c44  mov     r9d, eax; char *
0x180070c47  lea     r8, aOnecoreBaseDev_58; "onecore\\base\\devices\\cam\\core\\capa"...
0x180070c4e  mov     edx, 951h; void *
0x180070c53  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
