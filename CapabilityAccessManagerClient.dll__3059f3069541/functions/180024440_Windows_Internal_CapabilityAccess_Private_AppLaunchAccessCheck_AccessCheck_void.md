# Windows::Internal::CapabilityAccess::Private::AppLaunchAccessCheck::AccessCheck(void)

- ea: `0x180024440`
- end: `0x1800247f6`
- name: `?AccessCheck@AppLaunchAccessCheck@Private@CapabilityAccess@Internal@Windows@@QEAA?AW4AccessCheckStatus@2345@XZ`
- size: `950`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180020290`

## callees

- `0x180003c80`
- `0x18000a248`
- `0x18000c6c8`
- `0x18000f9e4`
- `0x180010500`
- `0x180011df8`
- `0x18001238c`
- `0x18001b218`
- `0x18001b444`
- `0x18001b5ac`
- `0x18001c330`
- `0x18002177c`
- `0x180022460`
- `0x180022d2c`
- `0x18002392c`
- `0x1800242c0`
- `0x180024358`
- `0x180024440`
- `0x180024aa4`
- `0x180029960`
- `0x18002bab4`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800246cf`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800246cf`

## string_xrefs

- `0x1800247a5`: `onecore\base\devices\cam\core\applaunchaccesscheck.cpp`
- `0x1800247ba`: `onecore\base\devices\cam\core\applaunchaccesscheck.cpp`
- `0x1800247cf`: `onecore\base\devices\cam\core\applaunchaccesscheck.cpp`
- `0x1800247e4`: `onecore\base\devices\cam\core\applaunchaccesscheck.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Windows::Internal::CapabilityAccess::Private::AppLaunchAccessCheck::AccessCheck(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v4; // r8
  __int64 v5; // rdx
  __int64 v6; // rbx
  __int64 UserSidStringFromProcessId; // rax
  __int64 AppLaunchRequiredCapabilities; // rax
  __int64 v9; // r12
  unsigned int v11; // r15d
  const unsigned __int16 *v12; // rdx
  __int64 v13; // rbx
  __int64 v14; // rdi
  char v15; // bl
  __int64 v16; // rbx
  __int64 *v17; // rax
  int v18; // eax
  __int64 (__fastcall *v19)(__int64, _QWORD, HSTRING, _QWORD); // r14
  int v20; // edi
  unsigned int v21; // esi
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  const unsigned __int16 *v25; // rax
  int v26; // eax
  HRESULT v27; // eax
  int v28; // eax
  DWORD dwAuthnLevel; // [rsp+20h] [rbp-B9h]
  int v30; // [rsp+40h] [rbp-99h] BYREF
  IUnknown *pProxy; // [rsp+48h] [rbp-91h] BYREF
  __int64 v32; // [rsp+50h] [rbp-89h] BYREF
  __int128 v33; // [rsp+58h] [rbp-81h] BYREF
  __int64 v34; // [rsp+68h] [rbp-71h]
  __int64 v35; // [rsp+70h] [rbp-69h] BYREF
  std::_Ref_count_base *v36; // [rsp+78h] [rbp-61h]
  _BYTE v37[32]; // [rsp+88h] [rbp-51h] BYREF
  _BYTE v38[32]; // [rsp+A8h] [rbp-31h] BYREF
  HSTRING string[4]; // [rsp+C8h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_5294eca8c9eb3f2e32adbecd8e777ec1_Traceguids);
  }
  LOBYTE(a3) = 3;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_CUASupport>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_CAM_CUASupport>::GetImpl'::`2'::impl,
    a2,
    a3);
  std::call_once__lambda_8185b7846b2f00949d85e0e1ec755921___();
  Windows::Internal::CapabilityAccess::Private::GetPackageFamilyNameFromProcessId((__int64)v38, *(_DWORD *)(a1 + 8));
  v33 = 0;
  v34 = 0;
  LOBYTE(v4) = 3;
  LOBYTE(v5) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_CUASupport>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_CAM_CUASupport>::GetImpl'::`2'::impl,
    v5,
    v4);
  v6 = *(_QWORD *)(a1 + 16);
  UserSidStringFromProcessId = Windows::Internal::CapabilityAccess::Private::GetUserSidStringFromProcessId(
                                 v37,
                                 *(unsigned int *)(a1 + 8));
  AppLaunchRequiredCapabilities = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::GetAppLaunchRequiredCapabilities(
                                    v6,
                                    &v35,
                                    v38,
                                    UserSidStringFromProcessId);
  std::vector<std::wstring>::operator=(&v33, AppLaunchRequiredCapabilities);
  std::vector<std::wstring>::_Tidy(&v35);
  std::wstring::_Tidy_deallocate(v37);
  v9 = v33;
  if ( *((_QWORD *)&v33 + 1) == (_QWORD)v33 )
  {
    std::vector<std::wstring>::_Tidy(&v33);
    std::wstring::_Tidy_deallocate(v38);
    return 3;
  }
  v11 = 3;
  v32 = 0;
  do
  {
    if ( !Windows::Internal::CapabilityAccess::Private::CheckProcessCapability(*(_DWORD *)(a1 + 8), v9) )
    {
      Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicy(*(_QWORD *)(a1 + 16), &v35, v9);
      v13 = *(_QWORD *)(v35 + 384);
      v14 = *(_QWORD *)(v35 + 392);
      while ( v13 != v14 )
      {
        if ( Windows::Internal::CapabilityAccess::Private::CheckProcessCapability(*(_DWORD *)(a1 + 8), v13) )
          goto LABEL_16;
        v13 += 32;
      }
      std::wstring::wstring((__int64)v37, (__int64)L"runFullTrust");
      v15 = Windows::Internal::CapabilityAccess::Private::CheckProcessCapability(*(_DWORD *)(a1 + 8), (__int64)v37);
      std::wstring::_Tidy_deallocate(v37);
      if ( !v15 )
      {
        if ( v36 )
          std::_Ref_count_base::_Decref(v36);
        goto LABEL_34;
      }
LABEL_16:
      if ( v36 )
        std::_Ref_count_base::_Decref(v36);
    }
    v16 = v32;
    if ( !v32 )
    {
      v17 = (__int64 *)Windows::Internal::StringReference::StringReference(string, (const unsigned __int16 (*)[51])v12);
      v18 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>>(
              *v17,
              (__int64)&v32);
      if ( v18 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x61,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\applaunchaccesscheck.cpp",
          (const char *)(unsigned int)v18,
          dwAuthnLevel);
      v16 = v32;
    }
    pProxy = 0;
    v19 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING, _QWORD))(*(_QWORD *)v16 + 56LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&pProxy);
    v20 = *(_DWORD *)(a1 + 12);
    v21 = *(_DWORD *)(a1 + 8);
    v25 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v9, v22, v23, v24);
    Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)string, v25);
    v26 = v19(v16, 0, string[0], v21);
    if ( v26 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6A,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\applaunchaccesscheck.cpp",
        (const char *)(unsigned int)v26,
        v20);
    v27 = CoSetProxyBlanket(
            pProxy,
            0xFFFFFFFF,
            0xFFFFFFFF,
            (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
            0,
            3u,
            (RPC_AUTH_IDENTITY_HANDLE)0xFFFFFFFFFFFFFFFFLL,
            0x40u);
    if ( v27 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x75,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\applaunchaccesscheck.cpp",
        (const char *)(unsigned int)v27,
        dwAuthnLevel);
    v30 = 3;
    v28 = ((__int64 (__fastcall *)(IUnknown *, int *))pProxy->lpVtbl[6].AddRef)(pProxy, &v30);
    if ( v28 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x78,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\applaunchaccesscheck.cpp",
        (const char *)(unsigned int)v28,
        dwAuthnLevel);
    if ( v30 != 3 )
    {
      switch ( v30 )
      {
        case 0:
          goto LABEL_32;
        case 1:
          v11 = 1;
          break;
        case 2:
          v11 = 2;
          break;
        case 4:
          v11 = 4;
          break;
        default:
LABEL_32:
          v11 = 0;
          break;
      }
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&pProxy);
LABEL_34:
    v9 += 32;
  }
  while ( v9 != *((_QWORD *)&v33 + 1) );
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v32);
  std::vector<std::wstring>::_Tidy(&v33);
  std::wstring::_Tidy_deallocate(v38);
  return v11;
}

```

## disassembly

```asm
0x180024440  push    rbp
0x180024442  push    rbx
0x180024443  push    rsi
0x180024444  push    rdi
0x180024445  push    r12
0x180024447  push    r13
0x180024449  push    r14
0x18002444b  push    r15
0x18002444d  lea     rbp, [rsp-1Fh]
0x180024452  sub     rsp, 0F8h
0x180024459  mov     rax, cs:__security_cookie
0x180024460  xor     rax, rsp
0x180024463  mov     [rbp+57h+var_48], rax
0x180024467  mov     r13, rcx
0x18002446a  lea     rax, WPP_GLOBAL_Control
0x180024471  mov     rcx, cs:WPP_GLOBAL_Control
0x180024478  cmp     rcx, rax
0x18002447b  jz      short loc_18002449E
0x18002447d  test    byte ptr [rcx+1Ch], 1
0x180024481  jz      short loc_18002449E
0x180024483  cmp     byte ptr [rcx+19h], 5
0x180024487  jb      short loc_18002449E
0x180024489  mov     edx, 0Bh
0x18002448e  lea     r8, WPP_5294eca8c9eb3f2e32adbecd8e777ec1_Traceguids
0x180024495  mov     rcx, [rcx+10h]
0x180024499  call    WPP_SF_
0x18002449e  mov     edi, 3
0x1800244a3  mov     r8b, dil
0x1800244a6  mov     dl, 1
0x1800244a8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CAM_CUASupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CAM_CUASupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_CUASupport> `wil::Feature<__WilFeatureTraits_Feature_CAM_CUASupport>::GetImpl(void)'::`2'::impl
0x1800244af  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_CAM_CUASupport@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_CUASupport>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800244b4  call    std__call_once__lambda_8185b7846b2f00949d85e0e1ec755921___
0x1800244b9  mov     edx, [r13+8]
0x1800244bd  lea     rcx, [rbp+57h+var_88]
0x1800244c1  call    ?GetPackageFamilyNameFromProcessId@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; Windows::Internal::CapabilityAccess::Private::GetPackageFamilyNameFromProcessId(ulong)
0x1800244c6  nop
0x1800244c7  xorps   xmm0, xmm0
0x1800244ca  movdqu  [rsp+130h+var_D8], xmm0
0x1800244d0  mov     [rbp+57h+var_C8], 0
0x1800244d8  mov     r8b, dil
0x1800244db  mov     dl, 1
0x1800244dd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CAM_CUASupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CAM_CUASupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_CUASupport> `wil::Feature<__WilFeatureTraits_Feature_CAM_CUASupport>::GetImpl(void)'::`2'::impl
0x1800244e4  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_CAM_CUASupport@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_CUASupport>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800244e9  mov     rbx, [r13+10h]
0x1800244ed  mov     edx, [r13+8]
0x1800244f1  lea     rcx, [rbp+57h+var_A8]
0x1800244f5  call    ?GetUserSidStringFromProcessId@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; Windows::Internal::CapabilityAccess::Private::GetUserSidStringFromProcessId(ulong)
0x1800244fa  nop
0x1800244fb  mov     r9, rax
0x1800244fe  lea     r8, [rbp+57h+var_88]
0x180024502  lea     rdx, [rbp+57h+var_C0]
0x180024506  mov     rcx, rbx
0x180024509  call    ?GetAppLaunchRequiredCapabilities@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@QEAA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@0@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::GetAppLaunchRequiredCapabilities(std::wstring const &,std::wstring const &)
0x18002450e  mov     rdx, rax
0x180024511  lea     rcx, [rsp+130h+var_D8]
0x180024516  call    ??4?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<std::wstring>::operator=(std::vector<std::wstring> &&)
0x18002451b  lea     rcx, [rbp+57h+var_C0]
0x18002451f  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180024524  nop
0x180024525  lea     rcx, [rbp+57h+var_A8]
0x180024529  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002452e  mov     r12, qword ptr [rsp+130h+var_D8]
0x180024533  cmp     qword ptr [rbp+57h+var_D8+8], r12
0x180024537  jnz     short loc_180024554
0x180024539  lea     rcx, [rsp+130h+var_D8]
0x18002453e  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180024543  nop
0x180024544  lea     rcx, [rbp+57h+var_88]
0x180024548  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002454d  mov     eax, edi
0x18002454f  jmp     loc_180024782
0x180024554  mov     r15d, edi
0x180024557  mov     [rsp+130h+var_E0], 0
0x180024560  jz      loc_180024760
0x180024566  mov     rdx, r12
0x180024569  mov     ecx, [r13+8]
0x18002456d  call    ?CheckProcessCapability@Private@CapabilityAccess@Internal@Windows@@YA_NKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::CheckProcessCapability(ulong,std::wstring const &)
0x180024572  test    al, al
0x180024574  jnz     loc_18002460A
0x18002457a  mov     r8, r12
0x18002457d  lea     rdx, [rbp+57h+var_C0]
0x180024581  mov     rcx, [r13+10h]
0x180024585  call    ?ReadPolicy@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@QEBA?AV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicy(std::wstring const &)
0x18002458a  nop
0x18002458b  mov     rax, [rbp+57h+var_C0]
0x18002458f  mov     rbx, [rax+180h]
0x180024596  mov     rdi, [rax+188h]
0x18002459d  jmp     short loc_1800245B3
0x18002459f  mov     rdx, rbx
0x1800245a2  mov     ecx, [r13+8]
0x1800245a6  call    ?CheckProcessCapability@Private@CapabilityAccess@Internal@Windows@@YA_NKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::CheckProcessCapability(ulong,std::wstring const &)
0x1800245ab  test    al, al
0x1800245ad  jnz     short loc_1800245FC
0x1800245af  add     rbx, 20h ; ' '
0x1800245b3  cmp     rbx, rdi
0x1800245b6  jnz     short loc_18002459F
0x1800245b8  lea     rdx, aRunfulltrust; "runFullTrust"
0x1800245bf  lea     rcx, [rbp+57h+var_A8]
0x1800245c3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800245c8  nop
0x1800245c9  lea     rdx, [rbp+57h+var_A8]
0x1800245cd  mov     ecx, [r13+8]
0x1800245d1  call    ?CheckProcessCapability@Private@CapabilityAccess@Internal@Windows@@YA_NKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::CheckProcessCapability(ulong,std::wstring const &)
0x1800245d6  mov     bl, al
0x1800245d8  lea     rcx, [rbp+57h+var_A8]
0x1800245dc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800245e1  test    bl, bl
0x1800245e3  jnz     short loc_1800245FC
0x1800245e5  mov     rcx, [rbp+57h+var_B8]; this
0x1800245e9  test    rcx, rcx
0x1800245ec  jz      loc_180024752
0x1800245f2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800245f7  jmp     loc_180024752
0x1800245fc  mov     rcx, [rbp+57h+var_B8]; this
0x180024600  test    rcx, rcx
0x180024603  jz      short loc_18002460A
0x180024605  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002460a  mov     rbx, [rsp+130h+var_E0]
0x18002460f  test    rbx, rbx
0x180024612  jnz     short loc_18002463B
0x180024614  lea     rcx, [rbp+57h+string]; string
0x180024618  call    ??$?0$0DD@@StringReference@Internal@Windows@@QEAA@AEAY0DD@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[51])
0x18002461d  lea     rdx, [rsp+130h+var_E0]
0x180024622  mov     rcx, [rax]
0x180024625  call    ??$GetActivationFactory@V?$ComPtr@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>>)
0x18002462a  mov     rcx, [rbp+5Fh]; this
0x18002462e  test    eax, eax
0x180024630  js      loc_1800247CC
0x180024636  mov     rbx, [rsp+130h+var_E0]
0x18002463b  mov     [rsp+130h+pProxy], 0
0x180024644  mov     rax, [rbx]
0x180024647  mov     r14, [rax+38h]
0x18002464b  lea     rcx, [rsp+130h+pProxy]
0x180024650  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180024655  mov     edi, [r13+0Ch]
0x180024659  mov     esi, [r13+8]
0x18002465d  mov     rcx, r12
0x180024660  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180024665  mov     rdx, rax; unsigned __int16 *
0x180024668  lea     rcx, [rbp+57h+string]; this
0x18002466c  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x180024671  lea     rax, [rsp+130h+pProxy]
0x180024676  mov     qword ptr [rsp+130h+dwImpLevel], rax
0x18002467b  mov     [rsp+130h+dwAuthnLevel], edi; int
0x18002467f  mov     r9d, esi
0x180024682  mov     r8, [rbp+57h+string]
0x180024686  xor     edx, edx
0x180024688  mov     rcx, rbx
0x18002468b  mov     rax, r14
0x18002468e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024693  mov     rcx, [rbp+5Fh]; this
0x180024697  test    eax, eax
0x180024699  js      loc_1800247B7
0x18002469f  mov     [rsp+130h+dwCapabilities], 40h ; '@'; dwCapabilities
0x1800246a7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800246ab  mov     [rsp+130h+pAuthInfo], rbx; pAuthInfo
0x1800246b0  lea     edi, [rbx+4]
0x1800246b3  mov     [rsp+130h+dwImpLevel], edi; dwImpLevel
0x1800246b7  mov     [rsp+130h+dwAuthnLevel], 0; int
0x1800246bf  mov     r9, rbx; pServerPrincName
0x1800246c2  or      ebx, 0FFFFFFFFh
0x1800246c5  mov     r8d, ebx; dwAuthzSvc
0x1800246c8  mov     edx, ebx; dwAuthnSvc
0x1800246ca  mov     rcx, [rsp+130h+pProxy]; pProxy
0x1800246cf  call    cs:__imp_CoSetProxyBlanket
0x1800246d5  mov     rcx, [rbp+5Fh]; this
0x1800246d9  test    eax, eax
0x1800246db  js      loc_1800247A2
0x1800246e1  mov     [rsp+130h+var_F0], edi
0x1800246e5  mov     rcx, [rsp+130h+pProxy]
0x1800246ea  mov     rax, [rcx]
0x1800246ed  lea     rdx, [rsp+130h+var_F0]
0x1800246f2  mov     rax, [rax+98h]
0x1800246f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800246fe  mov     rcx, [rbp+5Fh]; this
0x180024702  test    eax, eax
0x180024704  js      loc_1800247E1
0x18002470a  mov     ecx, [rsp+130h+var_F0]
0x18002470e  cmp     ecx, edi
0x180024710  jz      short loc_180024748
0x180024712  test    ecx, ecx
0x180024714  jz      short loc_180024745
0x180024716  sub     ecx, 1
0x180024719  jz      short loc_18002473D
0x18002471b  sub     ecx, 1
0x18002471e  jz      short loc_180024735
0x180024720  sub     ecx, 1
0x180024723  jz      short loc_180024730
0x180024725  cmp     ecx, 1
0x180024728  jnz     short loc_180024745
0x18002472a  lea     r15d, [rdi+1]
0x18002472e  jmp     short loc_180024748
0x180024730  mov     r15d, edi
0x180024733  jmp     short loc_180024748
0x180024735  mov     r15d, 2
0x18002473b  jmp     short loc_180024748
0x18002473d  mov     r15d, 1
0x180024743  jmp     short loc_180024748
0x180024745  xor     r15d, r15d
0x180024748  lea     rcx, [rsp+130h+pProxy]
0x18002474d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180024752  add     r12, 20h ; ' '
0x180024756  cmp     r12, qword ptr [rbp+57h+var_D8+8]
0x18002475a  jnz     loc_180024566
0x180024760  lea     rcx, [rsp+130h+var_E0]
0x180024765  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002476a  nop
0x18002476b  lea     rcx, [rsp+130h+var_D8]
0x180024770  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180024775  nop
0x180024776  lea     rcx, [rbp+57h+var_88]
0x18002477a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002477f  mov     eax, r15d
0x180024782  mov     rcx, [rbp+57h+var_48]
0x180024786  xor     rcx, rsp; StackCookie
0x180024789  call    __security_check_cookie
0x18002478e  add     rsp, 0F8h
0x180024795  pop     r15
0x180024797  pop     r14
0x180024799  pop     r13
0x18002479b  pop     r12
0x18002479d  pop     rdi
0x18002479e  pop     rsi
0x18002479f  pop     rbx
0x1800247a0  pop     rbp
0x1800247a1  retn
0x1800247a2  mov     r9d, eax; char *
0x1800247a5  lea     r8, aOnecoreBaseDev_11; "onecore\\base\\devices\\cam\\core\\appl"...
0x1800247ac  mov     edx, 75h ; 'u'; void *
0x1800247b1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800247b7  mov     r9d, eax; char *
0x1800247ba  lea     r8, aOnecoreBaseDev_11; "onecore\\base\\devices\\cam\\core\\appl"...
0x1800247c1  mov     edx, 6Ah ; 'j'; void *
0x1800247c6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800247cc  mov     r9d, eax; char *
0x1800247cf  lea     r8, aOnecoreBaseDev_11; "onecore\\base\\devices\\cam\\core\\appl"...
0x1800247d6  mov     edx, 61h ; 'a'; void *
0x1800247db  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800247e1  mov     r9d, eax; char *
0x1800247e4  lea     r8, aOnecoreBaseDev_11; "onecore\\base\\devices\\cam\\core\\appl"...
0x1800247eb  mov     edx, 78h ; 'x'; void *
0x1800247f0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
