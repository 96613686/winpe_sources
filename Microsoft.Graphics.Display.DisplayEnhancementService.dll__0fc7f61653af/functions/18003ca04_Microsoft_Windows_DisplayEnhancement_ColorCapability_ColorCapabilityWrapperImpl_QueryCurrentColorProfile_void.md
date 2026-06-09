# Microsoft::Windows::DisplayEnhancement::ColorCapability::ColorCapabilityWrapperImpl::QueryCurrentColorProfile(void)

- ea: `0x18003ca04`
- end: `0x18003d1c7`
- name: `?QueryCurrentColorProfile@ColorCapabilityWrapperImpl@ColorCapability@DisplayEnhancement@Windows@Microsoft@@AEAAXXZ`
- size: `1987`
- prototype: `void __fastcall(Microsoft::Windows::DisplayEnhancement::ColorCapability::ColorCapabilityWrapperImpl *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003bf30`

## callees

- `0x180005860`
- `0x180005cac`
- `0x1800074a4`
- `0x180009a84`
- `0x1800121d0`
- `0x18002774c`
- `0x18003b1f0`
- `0x18003b948`
- `0x18003ba14`
- `0x18003bc5c`
- `0x18003c6d4`
- `0x18003ca04`
- `0x18003d700`
- `0x18003e034`
- `0x18003e0e8`
- `0x1800753fc`
- `0x1800754ac`

## import_xrefs

- `mscms!WcsOpenColorProfileW` at `0x18003cc99`
- `mscms!WcsOpenColorProfileW` at `0x18003cc99`
- `mscms!GetColorProfileElement` at `0x18003cd52`
- `mscms!GetColorProfileElement` at `0x18003ce00`
- `mscms!GetColorProfileElement` at `0x18003ceae`
- `mscms!GetColorProfileElement` at `0x18003cf5c`
- `mscms!GetColorProfileElement` at `0x18003cfed`
- `mscms!GetColorProfileElement` at `0x18003d089`
- `mscms!GetColorProfileElement` at `0x18003cd52`
- `mscms!GetColorProfileElement` at `0x18003ce00`
- `mscms!GetColorProfileElement` at `0x18003ceae`
- `mscms!GetColorProfileElement` at `0x18003cf5c`
- `mscms!GetColorProfileElement` at `0x18003cfed`
- `mscms!GetColorProfileElement` at `0x18003d089`

## string_xrefs

- `0x18003cb4a`: `Microsoft.Graphics.Display.DisplayEnhancementService.dll`
- `0x18003ca5e`: `onecoreuap\drivers\mobilepc\displayenhancement\service\common\colorcapabilitywrapper\lib\colorcapabilitywrapper.cpp`
- `0x18003cb81`: `onecoreuap\drivers\mobilepc\displayenhancement\service\common\colorcapabilitywrapper\lib\colorcapabilitywrapper.cpp`

## pseudocode

```c
void __fastcall Microsoft::Windows::DisplayEnhancement::ColorCapability::ColorCapabilityWrapperImpl::QueryCurrentColorProfile(
        Microsoft::Windows::DisplayEnhancement::ColorCapability::ColorCapabilityWrapperImpl *this)
{
  int v2; // r14d
  __int64 v3; // rax
  __int64 v4; // rdx
  __int64 v5; // rdx
  int v6; // r12d
  int v7; // esi
  __int64 v8; // rbx
  char v9; // r15
  unsigned __int8 v10; // al
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  HPROFILE v13; // rbx
  _DWORD *XYZFromByteArray; // rax
  _DWORD *v15; // rax
  _DWORD *v16; // rax
  int v17; // xmm6_4
  char v18; // al
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  DWORD pcbElement[2]; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v22; // [rsp+50h] [rbp-B8h] BYREF
  _QWORD v23[2]; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v24; // [rsp+68h] [rbp-A0h] BYREF
  __int64 (__fastcall **v25)(); // [rsp+70h] [rbp-98h] BYREF
  __int64 *v26; // [rsp+78h] [rbp-90h]
  void *v27; // [rsp+88h] [rbp-80h] BYREF
  const char *v28; // [rsp+90h] [rbp-78h]
  __int64 v29; // [rsp+98h] [rbp-70h]
  __int16 v30; // [rsp+A0h] [rbp-68h]
  _BYTE v31[8]; // [rsp+A8h] [rbp-60h] BYREF
  PROFILE pCDMPProfile; // [rsp+B0h] [rbp-58h] BYREF
  __int128 pElement; // [rsp+C8h] [rbp-40h] BYREF
  int v34; // [rsp+D8h] [rbp-30h]
  _BYTE v35[8]; // [rsp+E8h] [rbp-20h] BYREF
  int v36; // [rsp+F0h] [rbp-18h]
  int v37; // [rsp+F4h] [rbp-14h]
  int v38; // [rsp+F8h] [rbp-10h]
  int v39; // [rsp+108h] [rbp+0h]
  int v40; // [rsp+10Ch] [rbp+4h]
  int v41; // [rsp+110h] [rbp+8h]
  int v42; // [rsp+120h] [rbp+18h]
  int v43; // [rsp+124h] [rbp+1Ch]
  int v44; // [rsp+128h] [rbp+20h]
  void *retaddr; // [rsp+180h] [rbp+78h]

  v2 = 0;
  LODWORD(v23[0]) = 0;
  v24 = 0;
  v3 = lambda_41cc18e1948b5b0af9c7633853752ecc_::_lambda_41cc18e1948b5b0af9c7633853752ecc_(v23, &v24, this);
  v27 = retaddr;
  v28 = "onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\common\\colorcapabilitywrapper\\lib\\colorcapabilitywrapper.cpp";
  v29 = 0;
  v30 = 85;
  v25 = off_1800EFC88;
  v26 = (__int64 *)v3;
  v6 = wil::details::ResultFromException(&v27, v4, &v25);
  v7 = 1;
  if ( v6 < 0 )
  {
    v8 = v23[0];
    goto LABEL_5;
  }
  v8 = 0;
  v23[0] = 0;
  v2 = 1;
  if ( (unsigned __int8)winrt::Windows::Foundation::operator==(&v24, v23) )
  {
LABEL_5:
    v9 = 1;
    goto LABEL_6;
  }
  v9 = 0;
LABEL_6:
  if ( (v2 & 1) != 0 )
  {
    v2 &= ~1u;
    if ( v8 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v23);
  }
  if ( !v9 )
  {
    v22 = 0;
    v25 = (__int64 (__fastcall **)())&v22;
    v26 = &v24;
    v27 = retaddr;
    v28 = "onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\common\\colorcapabilitywrapper\\lib\\colorcapabilitywrapper.cpp";
    v29 = 0;
    v30 = 124;
    v23[0] = off_1800EFC90;
    v23[1] = &v25;
    if ( (int)wil::details::ResultFromException(&v27, v5, v23) < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_82;
      }
      v12 = 12;
      goto LABEL_25;
    }
    if ( !v22 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_82;
      }
      v12 = 13;
LABEL_25:
      WPP_SF_sq(v11[2], v12, WPP_9f9642024ac8370c0fdf26f787115e6b_Traceguids);
LABEL_82:
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v22);
      goto LABEL_83;
    }
    memset(&pCDMPProfile, 0, sizeof(pCDMPProfile));
    pCDMPProfile.dwType = 1;
    pCDMPProfile.pProfileData = *(PVOID *)(v22 + 16);
    pCDMPProfile.cbDataSize = 2 * *(_DWORD *)(v22 + 4) + 2;
    v13 = WcsOpenColorProfileW(&pCDMPProfile, 0, 0, 1u, 1u, 3u, 0);
    v23[0] = v13;
    if ( !v13 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_9f9642024ac8370c0fdf26f787115e6b_Traceguids);
      }
      MicrosoftTelemetryAssertTriggeredNoArgs();
      goto LABEL_81;
    }
    pElement = 0;
    v34 = 0;
    pcbElement[0] = 20;
    pcbElement[1] = 0;
    `eh vector constructor iterator'(
      v35,
      0x18u,
      3u,
      (void (*)(void *))Microsoft::Windows::DisplayEnhancement::Foundation::XYZ::XYZ,
      (void (*)(void *))Microsoft::Windows::DisplayEnhancement::Foundation::XYZ::~XYZ);
    if ( !GetColorProfileElement(v13, 0x7258595Au, 0, pcbElement, &pElement, (PBOOL)&pcbElement[1]) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_9f9642024ac8370c0fdf26f787115e6b_Traceguids);
      }
LABEL_61:
      `eh vector destructor iterator'(
        v35,
        0x18u,
        3u,
        (void (*)(void *))Microsoft::Windows::DisplayEnhancement::Foundation::XYZ::~XYZ);
LABEL_81:
      wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseColorProfile(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseColorProfile(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v23);
      goto LABEL_82;
    }
    XYZFromByteArray = (_DWORD *)Microsoft::Windows::DisplayEnhancement::ColorCapability::ColorCapabilityWrapper::GetXYZFromByteArray(
                                   &v25,
                                   &pElement);
    v36 = XYZFromByteArray[2];
    v37 = XYZFromByteArray[3];
    v38 = XYZFromByteArray[4];
    if ( !GetColorProfileElement(v13, 0x6758595Au, 0, pcbElement, &pElement, (PBOOL)&pcbElement[1]) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_9f9642024ac8370c0fdf26f787115e6b_Traceguids);
      }
      goto LABEL_61;
    }
    v15 = (_DWORD *)Microsoft::Windows::DisplayEnhancement::ColorCapability::ColorCapabilityWrapper::GetXYZFromByteArray(
                      &v25,
                      &pElement);
    v39 = v15[2];
    v40 = v15[3];
    v41 = v15[4];
    if ( !GetColorProfileElement(v13, 0x6258595Au, 0, pcbElement, &pElement, (PBOOL)&pcbElement[1]) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_9f9642024ac8370c0fdf26f787115e6b_Traceguids);
      }
      goto LABEL_61;
    }
    v16 = (_DWORD *)Microsoft::Windows::DisplayEnhancement::ColorCapability::ColorCapabilityWrapper::GetXYZFromByteArray(
                      &v25,
                      &pElement);
    v42 = v16[2];
    v43 = v16[3];
    v44 = v16[4];
    if ( !GetColorProfileElement(v13, 0x77747074u, 0, pcbElement, &pElement, (PBOOL)&pcbElement[1]) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_9f9642024ac8370c0fdf26f787115e6b_Traceguids);
      }
      goto LABEL_61;
    }
    Microsoft::Windows::DisplayEnhancement::ColorCapability::ColorCapabilityWrapper::GetXYZFromByteArray(
      &v25,
      &pElement);
    if ( !GetColorProfileElement(v13, 0x6C756D69u, 0, pcbElement, &pElement, (PBOOL)&pcbElement[1]) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_9f9642024ac8370c0fdf26f787115e6b_Traceguids);
      }
      goto LABEL_61;
    }
    v17 = *(_DWORD *)(Microsoft::Windows::DisplayEnhancement::ColorCapability::ColorCapabilityWrapper::GetXYZFromByteArray(
                        &v27,
                        &pElement)
                    + 12);
    pcbElement[0] = 12;
    if ( !GetColorProfileElement(v13, 0x41434649u, 0, pcbElement, &pElement, (PBOOL)&pcbElement[1]) )
    {
      v7 = 0;
LABEL_80:
      Microsoft::Windows::DisplayEnhancement::Foundation::ExclusiveSRWLockguard::ExclusiveSRWLockguard(
        (Microsoft::Windows::DisplayEnhancement::Foundation::ExclusiveSRWLockguard *)v31,
        (Microsoft::Windows::DisplayEnhancement::ColorCapability::ColorCapabilityWrapperImpl *)((char *)this + 72));
      *((_DWORD *)this + 42) = v7;
      *((_DWORD *)this + 41) = v17;
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v31);
      `eh vector destructor iterator'(
        v35,
        0x18u,
        3u,
        (void (*)(void *))Microsoft::Windows::DisplayEnhancement::Foundation::XYZ::~XYZ);
      goto LABEL_81;
    }
    v18 = BYTE11(pElement) & 2;
    if ( (BYTE11(pElement) & 1) != 0 )
    {
      if ( !v18 )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
        {
          goto LABEL_80;
        }
        v20 = 20;
        goto LABEL_79;
      }
    }
    else if ( v18 )
    {
      v7 = 2;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_80;
      }
      v20 = 21;
LABEL_79:
      WPP_SF_sq(v19[2], v20, WPP_9f9642024ac8370c0fdf26f787115e6b_Traceguids);
      goto LABEL_80;
    }
    v7 = 0;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      goto LABEL_80;
    }
    v20 = 22;
    goto LABEL_79;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_9f9642024ac8370c0fdf26f787115e6b_Traceguids);
  }
  v25 = 0;
  LODWORD(v23[0]) = v2 | 2;
  v10 = winrt::Windows::Foundation::operator==(&v24, &v25);
  MicrosoftTelemetryAssertTriggeredArgs(
    "Microsoft.Graphics.Display.DisplayEnhancementService.dll",
    (unsigned int)v6,
    v10);
LABEL_83:
  winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>::~IAsyncOperation<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>(&v24);
}

```

## disassembly

```asm
0x18003ca04  mov     rax, rsp
0x18003ca07  mov     [rax+10h], rbx
0x18003ca0b  mov     [rax+18h], rsi
0x18003ca0f  push    rbp
0x18003ca10  push    rdi
0x18003ca11  push    r12
0x18003ca13  push    r14
0x18003ca15  push    r15
0x18003ca17  lea     rbp, [rax-78h]
0x18003ca1b  sub     rsp, 150h
0x18003ca22  movaps  xmmword ptr [rax-38h], xmm6
0x18003ca26  mov     rax, cs:__security_cookie
0x18003ca2d  xor     rax, rsp
0x18003ca30  mov     [rbp+70h+var_40], rax
0x18003ca34  mov     rdi, rcx
0x18003ca37  xor     r14d, r14d
0x18003ca3a  mov     dword ptr [rsp+170h+var_120], r14d
0x18003ca3f  mov     [rsp+170h+var_110], r14
0x18003ca44  mov     r8, rcx
0x18003ca47  lea     rdx, [rsp+170h+var_110]
0x18003ca4c  lea     rcx, [rsp+170h+var_120]
0x18003ca51  call    _lambda_41cc18e1948b5b0af9c7633853752ecc____lambda_41cc18e1948b5b0af9c7633853752ecc_
0x18003ca56  mov     rcx, [rbp+78h]
0x18003ca5a  mov     [rbp+70h+var_F0], rcx
0x18003ca5e  lea     rcx, aOnecoreuapDriv_12; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x18003ca65  mov     [rbp+70h+var_E8], rcx
0x18003ca69  mov     [rbp+70h+var_E0], r14
0x18003ca6d  lea     ecx, [r14+55h]
0x18003ca71  mov     [rbp+70h+var_D8], cx
0x18003ca75  lea     rcx, off_1800EFC88
0x18003ca7c  mov     [rsp+170h+var_108], rcx
0x18003ca81  mov     [rsp+170h+var_100], rax
0x18003ca86  lea     r8, [rsp+170h+var_108]
0x18003ca8b  lea     rcx, [rbp+70h+var_F0]
0x18003ca8f  call    ?ResultFromException@details@wil@@YAJAEBUDiagnosticsInfo@2@W4SupportedExceptions@2@AEAUIFunctor@12@@Z; wil::details::ResultFromException(wil::DiagnosticsInfo const &,wil::SupportedExceptions,wil::details::IFunctor &)
0x18003ca94  mov     r12d, eax
0x18003ca97  lea     esi, [r14+1]
0x18003ca9b  test    eax, eax
0x18003ca9d  js      short loc_18003CAC1
0x18003ca9f  xor     ebx, ebx
0x18003caa1  mov     [rsp+170h+var_120], rbx
0x18003caa6  mov     r14d, esi
0x18003caa9  lea     rdx, [rsp+170h+var_120]
0x18003caae  lea     rcx, [rsp+170h+var_110]
0x18003cab3  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x18003cab8  test    al, al
0x18003caba  jnz     short loc_18003CAC6
0x18003cabc  xor     r15b, r15b
0x18003cabf  jmp     short loc_18003CAC9
0x18003cac1  mov     rbx, [rsp+170h+var_120]
0x18003cac6  mov     r15b, sil
0x18003cac9  test    sil, r14b
0x18003cacc  jz      short loc_18003CAE1
0x18003cace  and     r14d, 0FFFFFFFEh
0x18003cad2  test    rbx, rbx
0x18003cad5  jz      short loc_18003CAE1
0x18003cad7  lea     rcx, [rsp+170h+var_120]
0x18003cadc  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18003cae1  test    r15b, r15b
0x18003cae4  jz      short loc_18003CB5C
0x18003cae6  lea     rax, WPP_GLOBAL_Control
0x18003caed  mov     rcx, cs:WPP_GLOBAL_Control
0x18003caf4  cmp     rcx, rax
0x18003caf7  jz      short loc_18003CB22
0x18003caf9  test    dword ptr [rcx+1Ch], 8000000h
0x18003cb00  jz      short loc_18003CB22
0x18003cb02  cmp     byte ptr [rcx+19h], 2
0x18003cb06  jb      short loc_18003CB22
0x18003cb08  mov     edx, 0Bh
0x18003cb0d  mov     qword ptr [rsp+170h+dwShareMode], rdi
0x18003cb12  lea     r8, WPP_9f9642024ac8370c0fdf26f787115e6b_Traceguids
0x18003cb19  mov     rcx, [rcx+10h]
0x18003cb1d  call    WPP_SF_sq
0x18003cb22  mov     [rsp+170h+var_108], 0
0x18003cb2b  or      r14d, 2
0x18003cb2f  mov     dword ptr [rsp+170h+var_120], r14d
0x18003cb34  lea     rdx, [rsp+170h+var_108]
0x18003cb39  lea     rcx, [rsp+170h+var_110]
0x18003cb3e  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x18003cb43  movzx   r8d, al
0x18003cb47  mov     edx, r12d
0x18003cb4a  lea     rcx, aMicrosoftGraph_0; "Microsoft.Graphics.Display.DisplayEnhan"...
0x18003cb51  call    MicrosoftTelemetryAssertTriggeredArgs
0x18003cb56  nop
0x18003cb57  jmp     loc_18003D190
0x18003cb5c  mov     [rsp+170h+var_128], 0
0x18003cb65  lea     rax, [rsp+170h+var_128]
0x18003cb6a  mov     [rsp+170h+var_108], rax
0x18003cb6f  lea     rax, [rsp+170h+var_110]
0x18003cb74  mov     [rsp+170h+var_100], rax
0x18003cb79  mov     rax, [rbp+78h]
0x18003cb7d  mov     [rbp+70h+var_F0], rax
0x18003cb81  lea     rax, aOnecoreuapDriv_12; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x18003cb88  mov     [rbp+70h+var_E8], rax
0x18003cb8c  mov     [rbp+70h+var_E0], 0
0x18003cb94  mov     eax, 7Ch ; '|'
0x18003cb99  mov     [rbp+70h+var_D8], ax
0x18003cb9d  lea     rax, off_1800EFC90
0x18003cba4  mov     [rsp+170h+var_120], rax
0x18003cba9  lea     rax, [rsp+170h+var_108]
0x18003cbae  mov     [rsp+170h+var_118], rax
0x18003cbb3  lea     r8, [rsp+170h+var_120]
0x18003cbb8  lea     rcx, [rbp+70h+var_F0]
0x18003cbbc  call    ?ResultFromException@details@wil@@YAJAEBUDiagnosticsInfo@2@W4SupportedExceptions@2@AEAUIFunctor@12@@Z; wil::details::ResultFromException(wil::DiagnosticsInfo const &,wil::SupportedExceptions,wil::details::IFunctor &)
0x18003cbc1  test    eax, eax
0x18003cbc3  jns     short loc_18003CBFA
0x18003cbc5  lea     rax, WPP_GLOBAL_Control
0x18003cbcc  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cbd3  cmp     rcx, rax
0x18003cbd6  jz      loc_18003D185
0x18003cbdc  test    dword ptr [rcx+1Ch], 8000000h
0x18003cbe3  jz      loc_18003D185
0x18003cbe9  cmp     byte ptr [rcx+19h], 4
0x18003cbed  jb      loc_18003D185
0x18003cbf3  mov     edx, 0Ch
0x18003cbf8  jmp     short loc_18003CC37
0x18003cbfa  mov     rax, [rsp+170h+var_128]
0x18003cbff  test    rax, rax
0x18003cc02  jnz     short loc_18003CC51
0x18003cc04  lea     rax, WPP_GLOBAL_Control
0x18003cc0b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cc12  cmp     rcx, rax
0x18003cc15  jz      loc_18003D185
0x18003cc1b  test    dword ptr [rcx+1Ch], 8000000h
0x18003cc22  jz      loc_18003D185
0x18003cc28  cmp     byte ptr [rcx+19h], 2
0x18003cc2c  jb      loc_18003D185
0x18003cc32  mov     edx, 0Dh
0x18003cc37  mov     qword ptr [rsp+170h+dwShareMode], rdi
0x18003cc3c  lea     r8, WPP_9f9642024ac8370c0fdf26f787115e6b_Traceguids
0x18003cc43  mov     rcx, [rcx+10h]
0x18003cc47  call    WPP_SF_sq
0x18003cc4c  jmp     loc_18003D185
0x18003cc51  xorps   xmm0, xmm0
0x18003cc54  xor     ecx, ecx
0x18003cc56  movups  xmmword ptr [rbp+70h+pCDMPProfile.dwType], xmm0
0x18003cc5a  mov     qword ptr [rbp+70h+pCDMPProfile.cbDataSize], rcx
0x18003cc5e  mov     [rbp+70h+pCDMPProfile.dwType], esi
0x18003cc61  mov     rcx, [rax+10h]
0x18003cc65  mov     [rbp+70h+pCDMPProfile.pProfileData], rcx
0x18003cc69  mov     ecx, [rax+4]
0x18003cc6c  lea     ecx, ds:2[rcx*2]
0x18003cc73  mov     [rbp+70h+pCDMPProfile.cbDataSize], ecx
0x18003cc76  mov     [rsp+170h+dwFlags], 0; dwFlags
0x18003cc7e  mov     r14d, 3
0x18003cc84  mov     [rsp+170h+dwCreationMode], r14d; dwCreationMode
0x18003cc89  mov     [rsp+170h+dwShareMode], esi; dwShareMode
0x18003cc8d  mov     r9d, esi; dwDesireAccess
0x18003cc90  xor     r8d, r8d; pGMMPProfile
0x18003cc93  xor     edx, edx; pCAMPProfile
0x18003cc95  lea     rcx, [rbp+70h+pCDMPProfile]; pCDMPProfile
0x18003cc99  call    cs:__imp_WcsOpenColorProfileW
0x18003cc9f  mov     rbx, rax
0x18003cca2  mov     [rsp+170h+var_120], rax
0x18003cca7  test    rax, rax
0x18003ccaa  jnz     short loc_18003CCF0
0x18003ccac  lea     rax, WPP_GLOBAL_Control
0x18003ccb3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ccba  cmp     rcx, rax
0x18003ccbd  jz      short loc_18003CCE6
0x18003ccbf  test    dword ptr [rcx+1Ch], 8000000h
0x18003ccc6  jz      short loc_18003CCE6
0x18003ccc8  cmp     byte ptr [rcx+19h], 2
0x18003cccc  jb      short loc_18003CCE6
0x18003ccce  lea     edx, [rbx+0Eh]
0x18003ccd1  mov     qword ptr [rsp+170h+dwShareMode], rdi
0x18003ccd6  lea     r8, WPP_9f9642024ac8370c0fdf26f787115e6b_Traceguids
0x18003ccdd  mov     rcx, [rcx+10h]
0x18003cce1  call    WPP_SF_sq
0x18003cce6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003cceb  jmp     loc_18003D17A
0x18003ccf0  xorps   xmm0, xmm0
0x18003ccf3  xor     eax, eax
0x18003ccf5  movups  [rbp+70h+pElement], xmm0
0x18003ccf9  mov     [rbp+70h+var_A0], eax
0x18003ccfc  mov     [rsp+170h+pcbElement], 14h
0x18003cd04  mov     [rsp+170h+pcbElement+4], eax
0x18003cd08  lea     r15, ??1XYZ@Foundation@DisplayEnhancement@Windows@Microsoft@@UEAA@XZ; Microsoft::Windows::DisplayEnhancement::Foundation::XYZ::~XYZ(void)
0x18003cd0f  mov     qword ptr [rsp+170h+dwShareMode], r15; void (*)(void *)
0x18003cd14  lea     r9, ??0XYZ@Foundation@DisplayEnhancement@Windows@Microsoft@@QEAA@XZ; void (*)(void *)
0x18003cd1b  mov     r8, r14; unsigned __int64
0x18003cd1e  lea     r12d, [rax+18h]
0x18003cd22  mov     edx, r12d; unsigned __int64
0x18003cd25  lea     rcx, [rbp+70h+var_90]; void *
0x18003cd29  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18003cd2e  nop
0x18003cd2f  lea     rax, [rsp+170h+pcbElement+4]
0x18003cd34  mov     qword ptr [rsp+170h+dwCreationMode], rax; pbReference
0x18003cd39  lea     rax, [rbp+70h+pElement]
0x18003cd3d  mov     qword ptr [rsp+170h+dwShareMode], rax; pElement
0x18003cd42  lea     r9, [rsp+170h+pcbElement]; pcbElement
0x18003cd47  xor     r8d, r8d; dwOffset
0x18003cd4a  mov     edx, 7258595Ah; tag
0x18003cd4f  mov     rcx, rbx; hProfile
0x18003cd52  call    cs:__imp_GetColorProfileElement
0x18003cd58  test    eax, eax
0x18003cd5a  jnz     short loc_18003CDB1
0x18003cd5c  lea     rax, WPP_GLOBAL_Control
0x18003cd63  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cd6a  cmp     rcx, rax
0x18003cd6d  jz      short loc_18003CD99
0x18003cd6f  test    dword ptr [rcx+1Ch], 8000000h
0x18003cd76  jz      short loc_18003CD99
0x18003cd78  cmp     byte ptr [rcx+19h], 2
0x18003cd7c  jb      short loc_18003CD99
0x18003cd7e  lea     edx, [r12-9]
0x18003cd83  mov     qword ptr [rsp+170h+dwShareMode], rdi
0x18003cd88  lea     r8, WPP_9f9642024ac8370c0fdf26f787115e6b_Traceguids
0x18003cd8f  mov     rcx, [rcx+10h]
0x18003cd93  call    WPP_SF_sq
0x18003cd98  nop
0x18003cd99  mov     r9, r15; void (*)(void *)
0x18003cd9c  mov     r8, r14; unsigned __int64
0x18003cd9f  mov     rdx, r12; unsigned __int64
0x18003cda2  lea     rcx, [rbp+70h+var_90]; void *
0x18003cda6  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18003cdab  nop
0x18003cdac  jmp     loc_18003D17A
0x18003cdb1  lea     rdx, [rbp+70h+pElement]
0x18003cdb5  lea     rcx, [rsp+170h+var_108]
0x18003cdba  call    ?GetXYZFromByteArray@ColorCapabilityWrapper@ColorCapability@DisplayEnhancement@Windows@Microsoft@@SA?AVXYZ@Foundation@345@AEBV?$array@E$0BE@@std@@@Z; Microsoft::Windows::DisplayEnhancement::ColorCapability::ColorCapabilityWrapper::GetXYZFromByteArray(std::array<uchar,20> const &)
0x18003cdbf  movss   xmm0, dword ptr [rax+8]
0x18003cdc4  movss   [rbp+70h+var_88], xmm0
0x18003cdc9  movss   xmm1, dword ptr [rax+0Ch]
0x18003cdce  movss   [rbp+70h+var_84], xmm1
0x18003cdd3  movss   xmm0, dword ptr [rax+10h]
0x18003cdd8  movss   [rbp+70h+var_80], xmm0
0x18003cddd  lea     rax, [rsp+170h+pcbElement+4]
0x18003cde2  mov     qword ptr [rsp+170h+dwCreationMode], rax; pbReference
0x18003cde7  lea     rax, [rbp+70h+pElement]
0x18003cdeb  mov     qword ptr [rsp+170h+dwShareMode], rax; pElement
0x18003cdf0  lea     r9, [rsp+170h+pcbElement]; pcbElement
0x18003cdf5  xor     r8d, r8d; dwOffset
0x18003cdf8  mov     edx, 6758595Ah; tag
0x18003cdfd  mov     rcx, rbx; hProfile
0x18003ce00  call    cs:__imp_GetColorProfileElement
0x18003ce06  test    eax, eax
0x18003ce08  jnz     short loc_18003CE5F
0x18003ce0a  lea     rax, WPP_GLOBAL_Control
0x18003ce11  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ce18  cmp     rcx, rax
0x18003ce1b  jz      short loc_18003CE47
0x18003ce1d  test    dword ptr [rcx+1Ch], 8000000h
0x18003ce24  jz      short loc_18003CE47
0x18003ce26  cmp     byte ptr [rcx+19h], 2
0x18003ce2a  jb      short loc_18003CE47
0x18003ce2c  mov     edx, 10h
0x18003ce31  mov     qword ptr [rsp+170h+dwShareMode], rdi
0x18003ce36  lea     r8, WPP_9f9642024ac8370c0fdf26f787115e6b_Traceguids
0x18003ce3d  mov     rcx, [rcx+10h]
0x18003ce41  call    WPP_SF_sq
0x18003ce46  nop
0x18003ce47  mov     r9, r15; void (*)(void *)
0x18003ce4a  mov     r8, r14; unsigned __int64
0x18003ce4d  mov     rdx, r12; unsigned __int64
0x18003ce50  lea     rcx, [rbp+70h+var_90]; void *
0x18003ce54  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18003ce59  nop
0x18003ce5a  jmp     loc_18003D17A
0x18003ce5f  lea     rdx, [rbp+70h+pElement]
0x18003ce63  lea     rcx, [rsp+170h+var_108]
0x18003ce68  call    ?GetXYZFromByteArray@ColorCapabilityWrapper@ColorCapability@DisplayEnhancement@Windows@Microsoft@@SA?AVXYZ@Foundation@345@AEBV?$array@E$0BE@@std@@@Z; Microsoft::Windows::DisplayEnhancement::ColorCapability::ColorCapabilityWrapper::GetXYZFromByteArray(std::array<uchar,20> const &)
0x18003ce6d  movss   xmm0, dword ptr [rax+8]
0x18003ce72  movss   [rbp+70h+var_70], xmm0
0x18003ce77  movss   xmm1, dword ptr [rax+0Ch]
0x18003ce7c  movss   [rbp+70h+var_6C], xmm1
0x18003ce81  movss   xmm0, dword ptr [rax+10h]
0x18003ce86  movss   [rbp+70h+var_68], xmm0
0x18003ce8b  lea     rax, [rsp+170h+pcbElement+4]
0x18003ce90  mov     qword ptr [rsp+170h+dwCreationMode], rax; pbReference
0x18003ce95  lea     rax, [rbp+70h+pElement]
0x18003ce99  mov     qword ptr [rsp+170h+dwShareMode], rax; pElement
0x18003ce9e  lea     r9, [rsp+170h+pcbElement]; pcbElement
0x18003cea3  xor     r8d, r8d; dwOffset
0x18003cea6  mov     edx, 6258595Ah; tag
0x18003ceab  mov     rcx, rbx; hProfile
0x18003ceae  call    cs:__imp_GetColorProfileElement
0x18003ceb4  test    eax, eax
0x18003ceb6  jnz     short loc_18003CF0D
0x18003ceb8  lea     rax, WPP_GLOBAL_Control
0x18003cebf  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cec6  cmp     rcx, rax
0x18003cec9  jz      short loc_18003CEF5
0x18003cecb  test    dword ptr [rcx+1Ch], 8000000h
0x18003ced2  jz      short loc_18003CEF5
0x18003ced4  cmp     byte ptr [rcx+19h], 2
0x18003ced8  jb      short loc_18003CEF5
0x18003ceda  mov     edx, 11h
0x18003cedf  mov     qword ptr [rsp+170h+dwShareMode], rdi
0x18003cee4  lea     r8, WPP_9f9642024ac8370c0fdf26f787115e6b_Traceguids
0x18003ceeb  mov     rcx, [rcx+10h]
0x18003ceef  call    WPP_SF_sq
0x18003cef4  nop
0x18003cef5  mov     r9, r15; void (*)(void *)
0x18003cef8  mov     r8, r14; unsigned __int64
0x18003cefb  mov     rdx, r12; unsigned __int64
0x18003cefe  lea     rcx, [rbp+70h+var_90]; void *
0x18003cf02  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18003cf07  nop
0x18003cf08  jmp     loc_18003D17A
  ... truncated ...
```
