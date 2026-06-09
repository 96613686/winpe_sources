# Microsoft::Windows::Autopilot::HardwareInfo::GetTpmEkPubByteData(std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x18001b654`
- end: `0x18001b932`
- name: `?GetTpmEkPubByteData@HardwareInfo@Autopilot@Windows@Microsoft@@SAJAEAV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `734`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b290`

## callees

- `0x1800105f4`
- `0x180018dec`
- `0x18001932c`
- `0x18001b654`
- `0x18001ccc4`
- `0x18002e010`

## import_xrefs

- `ncrypt!NCryptOpenStorageProvider` at `0x18001b6b4`
- `ncrypt!NCryptOpenStorageProvider` at `0x18001b6b4`
- `ncrypt!NCryptGetProperty` at `0x18001b759`
- `ncrypt!NCryptGetProperty` at `0x18001b877`
- `ncrypt!NCryptGetProperty` at `0x18001b759`
- `ncrypt!NCryptGetProperty` at `0x18001b877`

## string_xrefs

- `0x18001b67c`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001b6c8`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001b76d`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001b7f4`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001b88b`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::Autopilot::HardwareInfo::GetTpmEkPubByteData(PBYTE *a1)
{
  const char *v2; // r9
  __int64 result; // rax
  NCRYPT_PROV_HANDLE *v4; // rax
  SECURITY_STATUS v5; // eax
  unsigned int v6; // esi
  volatile signed __int32 *v7; // rdi
  NCRYPT_HANDLE *v8; // rbx
  NCRYPT_HANDLE v9; // rcx
  SECURITY_STATUS Property; // eax
  unsigned int v11; // esi
  volatile signed __int32 *v12; // rdi
  volatile signed __int32 *v13; // rdi
  NCRYPT_HANDLE v14; // rcx
  SECURITY_STATUS v15; // eax
  unsigned int v16; // esi
  volatile signed __int32 *v17; // rdi
  volatile signed __int32 *v18; // rdi
  int pcbResult; // [rsp+20h] [rbp-38h]
  int pcbResulta; // [rsp+20h] [rbp-38h]
  int pcbResultb; // [rsp+20h] [rbp-38h]
  __int128 v22; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int v24; // [rsp+68h] [rbp+10h] BYREF
  DWORD cbOutput; // [rsp+70h] [rbp+18h] BYREF
  DWORD v26; // [rsp+78h] [rbp+20h] BYREF

  try
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled() )
    {
      v22 = 0;
      v4 = (NCRYPT_PROV_HANDLE *)wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>>>::operator&(&v22);
      v5 = NCryptOpenStorageProvider(v4, L"Microsoft Platform Crypto Provider", 0);
      v6 = v5;
      if ( v5 >= 0 )
      {
        cbOutput = 0;
        v8 = (NCRYPT_HANDLE *)v22;
        if ( (_QWORD)v22 )
          v9 = *(_QWORD *)v22;
        else
          v9 = 0;
        Property = NCryptGetProperty(v9, L"PCP_EKPUB", 0, 0, &cbOutput, 0);
        v11 = Property;
        if ( Property >= 0 )
        {
          v26 = 0;
          std::vector<unsigned char>::_Resize<std::_Value_init_tag>(a1, cbOutput, &v24);
          if ( *a1 )
          {
            if ( v8 )
              v14 = *v8;
            else
              v14 = 0;
            v15 = NCryptGetProperty(v14, L"PCP_EKPUB", *a1, cbOutput, &v26, 0);
            v16 = v15;
            if ( v15 >= 0 )
            {
              v18 = (volatile signed __int32 *)*((_QWORD *)&v22 + 1);
              if ( *((_QWORD *)&v22 + 1) )
              {
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v22 + 1) + 8LL), 0xFFFFFFFF) == 1 )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
                  if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
                }
              }
              result = 0;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x11E,
                (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
                (const char *)(unsigned int)v15,
                pcbResultb);
              v17 = (volatile signed __int32 *)*((_QWORD *)&v22 + 1);
              if ( *((_QWORD *)&v22 + 1) )
              {
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v22 + 1) + 8LL), 0xFFFFFFFF) == 1 )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
                  if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
                }
              }
              result = v16;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x11C,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
              (const char *)0x8007000ELL,
              pcbResulta);
            v13 = (volatile signed __int32 *)*((_QWORD *)&v22 + 1);
            if ( *((_QWORD *)&v22 + 1) )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v22 + 1) + 8LL), 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
                if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
              }
            }
            result = 2147942414LL;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x118,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
            (const char *)(unsigned int)Property,
            pcbResulta);
          v12 = (volatile signed __int32 *)*((_QWORD *)&v22 + 1);
          if ( *((_QWORD *)&v22 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v22 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
              if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
            }
          }
          result = v11;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x115,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
          (const char *)(unsigned int)v5,
          pcbResult);
        v7 = (volatile signed __int32 *)*((_QWORD *)&v22 + 1);
        if ( *((_QWORD *)&v22 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v22 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
            if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
          }
        }
        result = v6;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x109,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
        (const char *)0x80004001LL,
        pcbResult);
      result = 2147500033LL;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x122,
                           (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
                           v2);
  }
  return result;
}

```

## disassembly

```asm
0x18001b654  push    rbx
0x18001b656  push    rsi
0x18001b657  push    rdi
0x18001b658  sub     rsp, 40h
0x18001b65c  mov     rdi, rcx
0x18001b65f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x18001b666  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x18001b66b  test    al, al
0x18001b66d  jnz     short loc_18001B694
0x18001b66f  mov     rcx, [rsp+58h]; this
0x18001b674  mov     ebx, 80004001h
0x18001b679  mov     r9d, ebx; char *
0x18001b67c  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001b683  mov     edx, 109h; void *
0x18001b688  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b68d  mov     eax, ebx
0x18001b68f  jmp     loc_18001B929
0x18001b694  xorps   xmm1, xmm1
0x18001b697  movdqu  [rsp+58h+var_28], xmm1
0x18001b69d  lea     rcx, [rsp+58h+var_28]
0x18001b6a2  call    ??I?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAAPEA_KXZ; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>>>::operator&(void)
0x18001b6a7  xor     r8d, r8d; dwFlags
0x18001b6aa  lea     rdx, pszProviderName; "Microsoft Platform Crypto Provider"
0x18001b6b1  mov     rcx, rax; phProvider
0x18001b6b4  call    cs:__imp_NCryptOpenStorageProvider
0x18001b6ba  mov     esi, eax
0x18001b6bc  test    eax, eax
0x18001b6be  jns     short loc_18001B721
0x18001b6c0  mov     rcx, [rsp+58h]; this
0x18001b6c5  mov     r9d, eax; char *
0x18001b6c8  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001b6cf  mov     edx, 115h; void *
0x18001b6d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b6d9  nop
0x18001b6da  mov     rdi, qword ptr [rsp+58h+var_28+8]
0x18001b6df  test    rdi, rdi
0x18001b6e2  jz      short loc_18001B71A
0x18001b6e4  or      ebx, 0FFFFFFFFh
0x18001b6e7  mov     eax, ebx
0x18001b6e9  lock xadd [rdi+8], eax
0x18001b6ee  add     eax, ebx
0x18001b6f0  jnz     short loc_18001B71A
0x18001b6f2  mov     rax, [rdi]
0x18001b6f5  mov     rcx, rdi
0x18001b6f8  mov     rax, [rax]
0x18001b6fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b700  mov     eax, ebx
0x18001b702  lock xadd [rdi+0Ch], eax
0x18001b707  add     eax, ebx
0x18001b709  jnz     short loc_18001B71A
0x18001b70b  mov     rax, [rdi]
0x18001b70e  mov     rcx, rdi
0x18001b711  mov     rax, [rax+8]
0x18001b715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b71a  mov     eax, esi
0x18001b71c  jmp     loc_18001B929
0x18001b721  mov     [rsp+58h+cbOutput], 0
0x18001b729  mov     rbx, qword ptr [rsp+58h+var_28]
0x18001b72e  test    rbx, rbx
0x18001b731  jz      short loc_18001B738
0x18001b733  mov     rcx, [rbx]
0x18001b736  jmp     short loc_18001B73A
0x18001b738  xor     ecx, ecx; hObject
0x18001b73a  mov     [rsp+58h+dwFlags], 0; dwFlags
0x18001b742  lea     rax, [rsp+58h+cbOutput]
0x18001b747  mov     [rsp+58h+pcbResult], rax; int
0x18001b74c  xor     r9d, r9d; cbOutput
0x18001b74f  xor     r8d, r8d; pbOutput
0x18001b752  lea     rdx, pszProperty; "PCP_EKPUB"
0x18001b759  call    cs:__imp_NCryptGetProperty
0x18001b75f  mov     esi, eax
0x18001b761  test    eax, eax
0x18001b763  jns     short loc_18001B7C6
0x18001b765  mov     rcx, [rsp+58h]; this
0x18001b76a  mov     r9d, eax; char *
0x18001b76d  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001b774  mov     edx, 118h; void *
0x18001b779  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b77e  nop
0x18001b77f  mov     rdi, qword ptr [rsp+58h+var_28+8]
0x18001b784  test    rdi, rdi
0x18001b787  jz      short loc_18001B7BF
0x18001b789  or      ebx, 0FFFFFFFFh
0x18001b78c  mov     eax, ebx
0x18001b78e  lock xadd [rdi+8], eax
0x18001b793  add     eax, ebx
0x18001b795  jnz     short loc_18001B7BF
0x18001b797  mov     rax, [rdi]
0x18001b79a  mov     rcx, rdi
0x18001b79d  mov     rax, [rax]
0x18001b7a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b7a5  mov     eax, ebx
0x18001b7a7  lock xadd [rdi+0Ch], eax
0x18001b7ac  add     eax, ebx
0x18001b7ae  jnz     short loc_18001B7BF
0x18001b7b0  mov     rax, [rdi]
0x18001b7b3  mov     rcx, rdi
0x18001b7b6  mov     rax, [rax+8]
0x18001b7ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b7bf  mov     eax, esi
0x18001b7c1  jmp     loc_18001B929
0x18001b7c6  mov     [rsp+58h+arg_18], 0
0x18001b7ce  mov     edx, [rsp+58h+cbOutput]
0x18001b7d2  lea     r8, [rsp+58h+arg_8]
0x18001b7d7  mov     rcx, rdi
0x18001b7da  call    ??$_Resize@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18001b7df  mov     r8, [rdi]; pbOutput
0x18001b7e2  test    r8, r8
0x18001b7e5  jnz     short loc_18001B84D
0x18001b7e7  mov     rcx, [rsp+58h]; this
0x18001b7ec  mov     esi, 8007000Eh
0x18001b7f1  mov     r9d, esi; char *
0x18001b7f4  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001b7fb  mov     edx, 11Ch; void *
0x18001b800  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b805  nop
0x18001b806  mov     rdi, qword ptr [rsp+58h+var_28+8]
0x18001b80b  test    rdi, rdi
0x18001b80e  jz      short loc_18001B846
0x18001b810  or      ebx, 0FFFFFFFFh
0x18001b813  mov     eax, ebx
0x18001b815  lock xadd [rdi+8], eax
0x18001b81a  add     eax, ebx
0x18001b81c  jnz     short loc_18001B846
0x18001b81e  mov     rax, [rdi]
0x18001b821  mov     rcx, rdi
0x18001b824  mov     rax, [rax]
0x18001b827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b82c  mov     edx, ebx
0x18001b82e  lock xadd [rdi+0Ch], edx
0x18001b833  add     edx, ebx
0x18001b835  jnz     short loc_18001B846
0x18001b837  mov     rdx, [rdi]
0x18001b83a  mov     rcx, rdi
0x18001b83d  mov     rax, [rdx+8]
0x18001b841  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b846  mov     eax, esi
0x18001b848  jmp     loc_18001B929
0x18001b84d  test    rbx, rbx
0x18001b850  jz      short loc_18001B857
0x18001b852  mov     rcx, [rbx]
0x18001b855  jmp     short loc_18001B859
0x18001b857  xor     ecx, ecx; hObject
0x18001b859  mov     [rsp+58h+dwFlags], 0; dwFlags
0x18001b861  lea     rax, [rsp+58h+arg_18]
0x18001b866  mov     [rsp+58h+pcbResult], rax; int
0x18001b86b  mov     r9d, [rsp+58h+cbOutput]; cbOutput
0x18001b870  lea     rdx, pszProperty; "PCP_EKPUB"
0x18001b877  call    cs:__imp_NCryptGetProperty
0x18001b87d  mov     esi, eax
0x18001b87f  test    eax, eax
0x18001b881  jns     short loc_18001B8E1
0x18001b883  mov     rcx, [rsp+58h]; this
0x18001b888  mov     r9d, eax; char *
0x18001b88b  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001b892  mov     edx, 11Eh; void *
0x18001b897  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b89c  nop
0x18001b89d  mov     rdi, qword ptr [rsp+58h+var_28+8]
0x18001b8a2  test    rdi, rdi
0x18001b8a5  jz      short loc_18001B8DD
0x18001b8a7  or      ebx, 0FFFFFFFFh
0x18001b8aa  mov     eax, ebx
0x18001b8ac  lock xadd [rdi+8], eax
0x18001b8b1  add     eax, ebx
0x18001b8b3  jnz     short loc_18001B8DD
0x18001b8b5  mov     rax, [rdi]
0x18001b8b8  mov     rcx, rdi
0x18001b8bb  mov     rax, [rax]
0x18001b8be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b8c3  mov     eax, ebx
0x18001b8c5  lock xadd [rdi+0Ch], eax
0x18001b8ca  add     eax, ebx
0x18001b8cc  jnz     short loc_18001B8DD
0x18001b8ce  mov     rax, [rdi]
0x18001b8d1  mov     rcx, rdi
0x18001b8d4  mov     rax, [rax+8]
0x18001b8d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b8dd  mov     eax, esi
0x18001b8df  jmp     short loc_18001B929
0x18001b8e1  mov     rdi, qword ptr [rsp+58h+var_28+8]
0x18001b8e6  test    rdi, rdi
0x18001b8e9  jz      short loc_18001B921
0x18001b8eb  or      ebx, 0FFFFFFFFh
0x18001b8ee  mov     eax, ebx
0x18001b8f0  lock xadd [rdi+8], eax
0x18001b8f5  add     eax, ebx
0x18001b8f7  jnz     short loc_18001B921
0x18001b8f9  mov     rax, [rdi]
0x18001b8fc  mov     rcx, rdi
0x18001b8ff  mov     rax, [rax]
0x18001b902  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b907  mov     eax, ebx
0x18001b909  lock xadd [rdi+0Ch], eax
0x18001b90e  add     eax, ebx
0x18001b910  jnz     short loc_18001B921
0x18001b912  mov     rax, [rdi]
0x18001b915  mov     rcx, rdi
0x18001b918  mov     rax, [rax+8]
0x18001b91c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b921  xor     eax, eax
0x18001b923  jmp     short loc_18001B929
0x18001b925  mov     eax, [rsp+58h+arg_8]
0x18001b929  add     rsp, 40h
0x18001b92d  pop     rdi
0x18001b92e  pop     rsi
0x18001b92f  pop     rbx
0x18001b930  retn
```
