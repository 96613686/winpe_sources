# Microsoft::Windows::Autopilot::HardwareInfo::GetTpmEkPubByteData(std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x18001bd78`
- end: `0x18001c068`
- name: `?GetTpmEkPubByteData@HardwareInfo@Autopilot@Windows@Microsoft@@SAJAEAV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `752`
- prototype: `__int64 __fastcall(PBYTE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b940`

## callees

- `0x180010764`
- `0x1800193c0`
- `0x180019928`
- `0x18001bd78`
- `0x18001d444`
- `0x18002f010`

## import_xrefs

- `ncrypt!NCryptOpenStorageProvider` at `0x18001bdd8`
- `ncrypt!NCryptOpenStorageProvider` at `0x18001bdd8`
- `ncrypt!NCryptGetProperty` at `0x18001be83`
- `ncrypt!NCryptGetProperty` at `0x18001bfa7`
- `ncrypt!NCryptGetProperty` at `0x18001be83`
- `ncrypt!NCryptGetProperty` at `0x18001bfa7`

## string_xrefs

- `0x18001bda0`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001bdf2`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001be9d`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001bf24`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001bfc1`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`

## pseudocode

```c
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
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
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
0x18001bd78  push    rbx
0x18001bd7a  push    rsi
0x18001bd7b  push    rdi
0x18001bd7c  sub     rsp, 40h
0x18001bd80  mov     rdi, rcx
0x18001bd83  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x18001bd8a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x18001bd8f  test    al, al
0x18001bd91  jnz     short loc_18001BDB8
0x18001bd93  mov     rcx, [rsp+58h]; this
0x18001bd98  mov     ebx, 80004001h
0x18001bd9d  mov     r9d, ebx; char *
0x18001bda0  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001bda7  mov     edx, 109h; void *
0x18001bdac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bdb1  mov     eax, ebx
0x18001bdb3  jmp     loc_18001C05F
0x18001bdb8  xorps   xmm1, xmm1
0x18001bdbb  movdqu  [rsp+58h+var_28], xmm1
0x18001bdc1  lea     rcx, [rsp+58h+var_28]
0x18001bdc6  call    ??I?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAAPEA_KXZ; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>>>::operator&(void)
0x18001bdcb  xor     r8d, r8d; dwFlags
0x18001bdce  lea     rdx, pszProviderName; "Microsoft Platform Crypto Provider"
0x18001bdd5  mov     rcx, rax; phProvider
0x18001bdd8  call    cs:__imp_NCryptOpenStorageProvider
0x18001bddf  nop     dword ptr [rax+rax+00h]
0x18001bde4  mov     esi, eax
0x18001bde6  test    eax, eax
0x18001bde8  jns     short loc_18001BE4B
0x18001bdea  mov     rcx, [rsp+58h]; this
0x18001bdef  mov     r9d, eax; char *
0x18001bdf2  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001bdf9  mov     edx, 115h; void *
0x18001bdfe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001be03  nop
0x18001be04  mov     rdi, qword ptr [rsp+58h+var_28+8]
0x18001be09  test    rdi, rdi
0x18001be0c  jz      short loc_18001BE44
0x18001be0e  or      ebx, 0FFFFFFFFh
0x18001be11  mov     eax, ebx
0x18001be13  lock xadd [rdi+8], eax
0x18001be18  add     eax, ebx
0x18001be1a  jnz     short loc_18001BE44
0x18001be1c  mov     rax, [rdi]
0x18001be1f  mov     rcx, rdi
0x18001be22  mov     rax, [rax]
0x18001be25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be2a  mov     eax, ebx
0x18001be2c  lock xadd [rdi+0Ch], eax
0x18001be31  add     eax, ebx
0x18001be33  jnz     short loc_18001BE44
0x18001be35  mov     rax, [rdi]
0x18001be38  mov     rcx, rdi
0x18001be3b  mov     rax, [rax+8]
0x18001be3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be44  mov     eax, esi
0x18001be46  jmp     loc_18001C05F
0x18001be4b  mov     [rsp+58h+cbOutput], 0
0x18001be53  mov     rbx, qword ptr [rsp+58h+var_28]
0x18001be58  test    rbx, rbx
0x18001be5b  jz      short loc_18001BE62
0x18001be5d  mov     rcx, [rbx]
0x18001be60  jmp     short loc_18001BE64
0x18001be62  xor     ecx, ecx; hObject
0x18001be64  mov     [rsp+58h+dwFlags], 0; dwFlags
0x18001be6c  lea     rax, [rsp+58h+cbOutput]
0x18001be71  mov     [rsp+58h+pcbResult], rax; int
0x18001be76  xor     r9d, r9d; cbOutput
0x18001be79  xor     r8d, r8d; pbOutput
0x18001be7c  lea     rdx, pszProperty; "PCP_EKPUB"
0x18001be83  call    cs:__imp_NCryptGetProperty
0x18001be8a  nop     dword ptr [rax+rax+00h]
0x18001be8f  mov     esi, eax
0x18001be91  test    eax, eax
0x18001be93  jns     short loc_18001BEF6
0x18001be95  mov     rcx, [rsp+58h]; this
0x18001be9a  mov     r9d, eax; char *
0x18001be9d  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001bea4  mov     edx, 118h; void *
0x18001bea9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001beae  nop
0x18001beaf  mov     rdi, qword ptr [rsp+58h+var_28+8]
0x18001beb4  test    rdi, rdi
0x18001beb7  jz      short loc_18001BEEF
0x18001beb9  or      ebx, 0FFFFFFFFh
0x18001bebc  mov     eax, ebx
0x18001bebe  lock xadd [rdi+8], eax
0x18001bec3  add     eax, ebx
0x18001bec5  jnz     short loc_18001BEEF
0x18001bec7  mov     rax, [rdi]
0x18001beca  mov     rcx, rdi
0x18001becd  mov     rax, [rax]
0x18001bed0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bed5  mov     eax, ebx
0x18001bed7  lock xadd [rdi+0Ch], eax
0x18001bedc  add     eax, ebx
0x18001bede  jnz     short loc_18001BEEF
0x18001bee0  mov     rax, [rdi]
0x18001bee3  mov     rcx, rdi
0x18001bee6  mov     rax, [rax+8]
0x18001beea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001beef  mov     eax, esi
0x18001bef1  jmp     loc_18001C05F
0x18001bef6  mov     [rsp+58h+arg_18], 0
0x18001befe  mov     edx, [rsp+58h+cbOutput]
0x18001bf02  lea     r8, [rsp+58h+arg_8]
0x18001bf07  mov     rcx, rdi
0x18001bf0a  call    ??$_Resize@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18001bf0f  mov     r8, [rdi]; pbOutput
0x18001bf12  test    r8, r8
0x18001bf15  jnz     short loc_18001BF7D
0x18001bf17  mov     rcx, [rsp+58h]; this
0x18001bf1c  mov     esi, 8007000Eh
0x18001bf21  mov     r9d, esi; char *
0x18001bf24  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001bf2b  mov     edx, 11Ch; void *
0x18001bf30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bf35  nop
0x18001bf36  mov     rdi, qword ptr [rsp+58h+var_28+8]
0x18001bf3b  test    rdi, rdi
0x18001bf3e  jz      short loc_18001BF76
0x18001bf40  or      ebx, 0FFFFFFFFh
0x18001bf43  mov     eax, ebx
0x18001bf45  lock xadd [rdi+8], eax
0x18001bf4a  add     eax, ebx
0x18001bf4c  jnz     short loc_18001BF76
0x18001bf4e  mov     rax, [rdi]
0x18001bf51  mov     rcx, rdi
0x18001bf54  mov     rax, [rax]
0x18001bf57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf5c  mov     edx, ebx
0x18001bf5e  lock xadd [rdi+0Ch], edx
0x18001bf63  add     edx, ebx
0x18001bf65  jnz     short loc_18001BF76
0x18001bf67  mov     rdx, [rdi]
0x18001bf6a  mov     rcx, rdi
0x18001bf6d  mov     rax, [rdx+8]
0x18001bf71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf76  mov     eax, esi
0x18001bf78  jmp     loc_18001C05F
0x18001bf7d  test    rbx, rbx
0x18001bf80  jz      short loc_18001BF87
0x18001bf82  mov     rcx, [rbx]
0x18001bf85  jmp     short loc_18001BF89
0x18001bf87  xor     ecx, ecx; hObject
0x18001bf89  mov     [rsp+58h+dwFlags], 0; dwFlags
0x18001bf91  lea     rax, [rsp+58h+arg_18]
0x18001bf96  mov     [rsp+58h+pcbResult], rax; int
0x18001bf9b  mov     r9d, [rsp+58h+cbOutput]; cbOutput
0x18001bfa0  lea     rdx, pszProperty; "PCP_EKPUB"
0x18001bfa7  call    cs:__imp_NCryptGetProperty
0x18001bfae  nop     dword ptr [rax+rax+00h]
0x18001bfb3  mov     esi, eax
0x18001bfb5  test    eax, eax
0x18001bfb7  jns     short loc_18001C017
0x18001bfb9  mov     rcx, [rsp+58h]; this
0x18001bfbe  mov     r9d, eax; char *
0x18001bfc1  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001bfc8  mov     edx, 11Eh; void *
0x18001bfcd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bfd2  nop
0x18001bfd3  mov     rdi, qword ptr [rsp+58h+var_28+8]
0x18001bfd8  test    rdi, rdi
0x18001bfdb  jz      short loc_18001C013
0x18001bfdd  or      ebx, 0FFFFFFFFh
0x18001bfe0  mov     eax, ebx
0x18001bfe2  lock xadd [rdi+8], eax
0x18001bfe7  add     eax, ebx
0x18001bfe9  jnz     short loc_18001C013
0x18001bfeb  mov     rax, [rdi]
0x18001bfee  mov     rcx, rdi
0x18001bff1  mov     rax, [rax]
0x18001bff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bff9  mov     eax, ebx
0x18001bffb  lock xadd [rdi+0Ch], eax
0x18001c000  add     eax, ebx
0x18001c002  jnz     short loc_18001C013
0x18001c004  mov     rax, [rdi]
0x18001c007  mov     rcx, rdi
0x18001c00a  mov     rax, [rax+8]
0x18001c00e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c013  mov     eax, esi
0x18001c015  jmp     short loc_18001C05F
0x18001c017  mov     rdi, qword ptr [rsp+58h+var_28+8]
0x18001c01c  test    rdi, rdi
0x18001c01f  jz      short loc_18001C057
0x18001c021  or      ebx, 0FFFFFFFFh
0x18001c024  mov     eax, ebx
0x18001c026  lock xadd [rdi+8], eax
0x18001c02b  add     eax, ebx
0x18001c02d  jnz     short loc_18001C057
0x18001c02f  mov     rax, [rdi]
0x18001c032  mov     rcx, rdi
0x18001c035  mov     rax, [rax]
0x18001c038  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c03d  mov     eax, ebx
0x18001c03f  lock xadd [rdi+0Ch], eax
0x18001c044  add     eax, ebx
0x18001c046  jnz     short loc_18001C057
0x18001c048  mov     rax, [rdi]
0x18001c04b  mov     rcx, rdi
0x18001c04e  mov     rax, [rax+8]
0x18001c052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c057  xor     eax, eax
0x18001c059  jmp     short loc_18001C05F
0x18001c05b  mov     eax, [rsp+58h+arg_8]
0x18001c05f  add     rsp, 40h
0x18001c063  pop     rdi
0x18001c064  pop     rsi
0x18001c065  pop     rbx
0x18001c066  retn
```
