# ModernDeployment::Autopilot::Core::NcryptKeyData::CreateFromKeyHandle(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>>> &,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>>> &,ModernDeployment::Autopilot::Core::NcryptKeyData &)

- ea: `0x18015bd64`
- end: `0x18015c122`
- name: `?CreateFromKeyHandle@NcryptKeyData@Core@Autopilot@ModernDeployment@@SAJAEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@0AEAV1234@@Z`
- size: `958`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801375a8`

## callees

- `0x18000b820`
- `0x180067a54`
- `0x18006e89c`
- `0x180077384`
- `0x18007755c`
- `0x18008019c`
- `0x1800801fc`
- `0x1800814a8`
- `0x18008c244`
- `0x18008c630`
- `0x180093a28`
- `0x18013c55c`
- `0x18015bd64`

## import_xrefs

- `ncrypt!NCryptGetProperty` at `0x18015bdfa`
- `ncrypt!NCryptGetProperty` at `0x18015bed2`
- `ncrypt!NCryptGetProperty` at `0x18015bf8c`
- `ncrypt!NCryptGetProperty` at `0x18015bdfa`
- `ncrypt!NCryptGetProperty` at `0x18015bed2`
- `ncrypt!NCryptGetProperty` at `0x18015bf8c`

## string_xrefs

- `0x18015bdac`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\ncryptkeydata.cpp`
- `0x18015be11`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\ncryptkeydata.cpp`
- `0x18015be7c`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\ncryptkeydata.cpp`
- `0x18015bee9`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\ncryptkeydata.cpp`
- `0x18015bf26`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\ncryptkeydata.cpp`
- `0x18015bfa3`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\ncryptkeydata.cpp`
- `0x18015bfdd`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\ncryptkeydata.cpp`
- `0x18015c018`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\ncryptkeydata.cpp`
- `0x18015c05d`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\ncryptkeydata.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ModernDeployment::Autopilot::Core::NcryptKeyData::CreateFromKeyHandle(
        __int64 a1,
        NCRYPT_HANDLE **a2,
        __int64 a3)
{
  const char *v6; // r9
  __int64 result; // rax
  NCRYPT_HANDLE v8; // rcx
  SECURITY_STATUS Property; // eax
  unsigned int v10; // esi
  BYTE *v11; // r8
  NCRYPT_HANDLE v12; // rcx
  SECURITY_STATUS v13; // eax
  unsigned int v14; // esi
  NCRYPT_HANDLE v15; // rcx
  SECURITY_STATUS v16; // eax
  unsigned int v17; // esi
  int KeyTypeFromAlgorithmId; // eax
  unsigned int v19; // esi
  __int64 *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // r8
  int pcbResult; // [rsp+20h] [rbp-78h]
  int pcbResulta; // [rsp+20h] [rbp-78h]
  int pcbResultb; // [rsp+20h] [rbp-78h]
  int pcbResultc; // [rsp+20h] [rbp-78h]
  _BYTE v27[8]; // [rsp+30h] [rbp-68h] BYREF
  std::_Ref_count_base *v28; // [rsp+38h] [rbp-60h]
  DWORD v29; // [rsp+40h] [rbp-58h] BYREF
  DWORD cbOutput; // [rsp+44h] [rbp-54h] BYREF
  BYTE pbOutput[4]; // [rsp+48h] [rbp-50h] BYREF
  _OWORD v32[2]; // [rsp+50h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  try
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
    {
      cbOutput = 0;
      if ( *a2 )
        v8 = **a2;
      else
        v8 = 0;
      Property = NCryptGetProperty(v8, L"Algorithm Name", 0, 0, &cbOutput, 0);
      v10 = Property;
      if ( Property >= 0 )
      {
        v32[0] = 0;
        v32[1] = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v32[0]) = 0;
        std::wstring::resize(v32, (unsigned __int64)cbOutput >> 1, 0);
        v11 = (BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v32);
        if ( v11 )
        {
          v29 = 0;
          if ( *a2 )
            v12 = **a2;
          else
            v12 = 0;
          v13 = NCryptGetProperty(v12, L"Algorithm Name", v11, cbOutput, &v29, 0);
          v14 = v13;
          if ( v13 >= 0 )
          {
            if ( v29 == cbOutput )
            {
              v29 = 0;
              *(_DWORD *)pbOutput = 0;
              if ( *a2 )
                v15 = **a2;
              else
                v15 = 0;
              v16 = NCryptGetProperty(v15, L"Length", pbOutput, 4u, &v29, 0);
              v17 = v16;
              if ( v16 >= 0 )
              {
                if ( v29 == 4 )
                {
                  if ( *(_DWORD *)pbOutput )
                  {
                    KeyTypeFromAlgorithmId = ModernDeployment::Autopilot::Core::TpmKeyTypes::GetKeyTypeFromAlgorithmId(
                                               v32,
                                               *(unsigned int *)pbOutput,
                                               a3 + 184);
                    v19 = KeyTypeFromAlgorithmId;
                    if ( KeyTypeFromAlgorithmId >= 0 )
                    {
                      v20 = (__int64 *)std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>(
                                         v27,
                                         a1);
                      v21 = *v20;
                      *v20 = *(_QWORD *)a3;
                      *(_QWORD *)a3 = v21;
                      v22 = v20[1];
                      v20[1] = *(_QWORD *)(a3 + 8);
                      *(_QWORD *)(a3 + 8) = v22;
                      if ( v28 )
                        std::_Ref_count_base::_Decref(v28);
                      if ( (NCRYPT_HANDLE **)(a3 + 16) != a2 )
                        std::shared_ptr<Microsoft::Windows::Autopilot::Diagnostics::EtwProcessingDataEntry>::operator=(
                          a3 + 16,
                          a2);
                      std::wstring::operator=(a3 + 64, v32);
                      std::wstring::assign(a3 + 96, L"SHA256");
                      *(_BYTE *)(a3 + 188) = 1;
                      std::wstring::_Tidy_deallocate(v32);
                      result = 0;
                    }
                    else
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x52,
                        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\ncryptkeydata.cpp",
                        (const char *)(unsigned int)KeyTypeFromAlgorithmId,
                        pcbResultc);
                      std::wstring::_Tidy_deallocate(v32);
                      result = v19;
                    }
                  }
                  else
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x50,
                      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\ncryptkeydata.cpp",
                      (const char *)0x8000FFFFLL,
                      pcbResultc);
                    std::wstring::_Tidy_deallocate(v32);
                    result = 2147549183LL;
                  }
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x4F,
                    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\ncryptkeydata.cpp",
                    (const char *)0x8000FFFFLL,
                    pcbResultc);
                  std::wstring::_Tidy_deallocate(v32);
                  result = 2147549183LL;
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x4E,
                  (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\ncryptkeydata.cpp",
                  (const char *)(unsigned int)v16,
                  pcbResultc);
                std::wstring::_Tidy_deallocate(v32);
                result = v17;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x44,
                (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\ncryptkeydata.cpp",
                (const char *)0x8000FFFFLL,
                pcbResultb);
              std::wstring::_Tidy_deallocate(v32);
              result = 2147549183LL;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x43,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\ncryptkeydata.cpp",
              (const char *)(unsigned int)v13,
              pcbResultb);
            std::wstring::_Tidy_deallocate(v32);
            result = v14;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3A,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\ncryptkeydata.cpp",
            (const char *)0x8007000ELL,
            pcbResulta);
          std::wstring::_Tidy_deallocate(v32);
          result = 2147942414LL;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x36,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\ncryptkeydata.cpp",
          (const char *)(unsigned int)Property,
          pcbResulta);
        result = v10;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2B,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\ncryptkeydata.cpp",
        (const char *)0x80004001LL,
        pcbResult);
      result = 2147500033LL;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x5C,
                           (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\ncryptkeydata.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x18015bd64  mov     [rsp+arg_18], rbx
0x18015bd69  push    rsi
0x18015bd6a  push    rdi
0x18015bd6b  push    r14
0x18015bd6d  sub     rsp, 80h
0x18015bd74  mov     rax, cs:__security_cookie
0x18015bd7b  xor     rax, rsp
0x18015bd7e  mov     [rsp+98h+var_28], rax
0x18015bd83  mov     rbx, r8
0x18015bd86  mov     rdi, rdx
0x18015bd89  mov     r14, rcx
0x18015bd8c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x18015bd93  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x18015bd98  test    al, al
0x18015bd9a  jnz     short loc_18015BDC4
0x18015bd9c  mov     rcx, [rsp+98h]; this
0x18015bda4  mov     ebx, 80004001h
0x18015bda9  mov     r9d, ebx; char *
0x18015bdac  lea     r8, aOnecoreuapAdmi_62; "onecoreuap\\admin\\moderndeployment\\au"...
0x18015bdb3  mov     edx, 2Bh ; '+'; void *
0x18015bdb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015bdbd  mov     eax, ebx
0x18015bdbf  jmp     loc_18015C100
0x18015bdc4  mov     [rsp+98h+cbOutput], 0
0x18015bdcc  mov     rax, [rdi]
0x18015bdcf  test    rax, rax
0x18015bdd2  jz      short loc_18015BDD9
0x18015bdd4  mov     rcx, [rax]
0x18015bdd7  jmp     short loc_18015BDDB
0x18015bdd9  xor     ecx, ecx; hObject
0x18015bddb  mov     [rsp+98h+dwFlags], 0; dwFlags
0x18015bde3  lea     rax, [rsp+98h+cbOutput]
0x18015bde8  mov     [rsp+98h+pcbResult], rax; int
0x18015bded  xor     r9d, r9d; cbOutput
0x18015bdf0  xor     r8d, r8d; pbOutput
0x18015bdf3  lea     rdx, aAlgorithmName; "Algorithm Name"
0x18015bdfa  call    cs:__imp_NCryptGetProperty
0x18015be00  mov     esi, eax
0x18015be02  test    eax, eax
0x18015be04  jns     short loc_18015BE29
0x18015be06  mov     rcx, [rsp+98h]; this
0x18015be0e  mov     r9d, eax; char *
0x18015be11  lea     r8, aOnecoreuapAdmi_62; "onecoreuap\\admin\\moderndeployment\\au"...
0x18015be18  mov     edx, 36h ; '6'; void *
0x18015be1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015be22  mov     eax, esi
0x18015be24  jmp     loc_18015C100
0x18015be29  xorps   xmm0, xmm0
0x18015be2c  movups  [rsp+98h+var_48], xmm0
0x18015be31  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18015be39  movdqu  [rsp+98h+var_38], xmm1
0x18015be3f  xor     eax, eax
0x18015be41  mov     word ptr [rsp+98h+var_48], ax
0x18015be46  xor     r8d, r8d
0x18015be49  mov     edx, [rsp+98h+cbOutput]
0x18015be4d  shr     rdx, 1
0x18015be50  lea     rcx, [rsp+98h+var_48]
0x18015be55  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18015be5a  lea     rcx, [rsp+98h+var_48]
0x18015be5f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18015be64  mov     r8, rax; pbOutput
0x18015be67  test    rax, rax
0x18015be6a  jnz     short loc_18015BE9D
0x18015be6c  mov     rcx, [rsp+98h]; this
0x18015be74  mov     ebx, 8007000Eh
0x18015be79  mov     r9d, ebx; char *
0x18015be7c  lea     r8, aOnecoreuapAdmi_62; "onecoreuap\\admin\\moderndeployment\\au"...
0x18015be83  lea     edx, [rax+3Ah]; void *
0x18015be86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015be8b  nop
0x18015be8c  lea     rcx, [rsp+98h+var_48]
0x18015be91  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18015be96  mov     eax, ebx
0x18015be98  jmp     loc_18015C100
0x18015be9d  mov     [rsp+98h+var_58], 0
0x18015bea5  mov     rax, [rdi]
0x18015bea8  test    rax, rax
0x18015beab  jz      short loc_18015BEB2
0x18015bead  mov     rcx, [rax]
0x18015beb0  jmp     short loc_18015BEB4
0x18015beb2  xor     ecx, ecx; hObject
0x18015beb4  mov     [rsp+98h+dwFlags], 0; dwFlags
0x18015bebc  lea     rax, [rsp+98h+var_58]
0x18015bec1  mov     [rsp+98h+pcbResult], rax; int
0x18015bec6  mov     r9d, [rsp+98h+cbOutput]; cbOutput
0x18015becb  lea     rdx, aAlgorithmName; "Algorithm Name"
0x18015bed2  call    cs:__imp_NCryptGetProperty
0x18015bed8  mov     esi, eax
0x18015beda  test    eax, eax
0x18015bedc  jns     short loc_18015BF0C
0x18015bede  mov     rcx, [rsp+98h]; this
0x18015bee6  mov     r9d, eax; char *
0x18015bee9  lea     r8, aOnecoreuapAdmi_62; "onecoreuap\\admin\\moderndeployment\\au"...
0x18015bef0  mov     edx, 43h ; 'C'; void *
0x18015bef5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015befa  nop
0x18015befb  lea     rcx, [rsp+98h+var_48]
0x18015bf00  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18015bf05  mov     eax, esi
0x18015bf07  jmp     loc_18015C100
0x18015bf0c  mov     eax, [rsp+98h+cbOutput]
0x18015bf10  cmp     [rsp+98h+var_58], eax
0x18015bf14  jz      short loc_18015BF49
0x18015bf16  mov     rcx, [rsp+98h]; this
0x18015bf1e  mov     ebx, 8000FFFFh
0x18015bf23  mov     r9d, ebx; char *
0x18015bf26  lea     r8, aOnecoreuapAdmi_62; "onecoreuap\\admin\\moderndeployment\\au"...
0x18015bf2d  mov     edx, 44h ; 'D'; void *
0x18015bf32  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015bf37  nop
0x18015bf38  lea     rcx, [rsp+98h+var_48]
0x18015bf3d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18015bf42  mov     eax, ebx
0x18015bf44  jmp     loc_18015C100
0x18015bf49  mov     [rsp+98h+var_58], 0
0x18015bf51  mov     dword ptr [rsp+98h+pbOutput], 0
0x18015bf59  mov     rax, [rdi]
0x18015bf5c  test    rax, rax
0x18015bf5f  jz      short loc_18015BF66
0x18015bf61  mov     rcx, [rax]
0x18015bf64  jmp     short loc_18015BF68
0x18015bf66  xor     ecx, ecx; hObject
0x18015bf68  mov     [rsp+98h+dwFlags], 0; dwFlags
0x18015bf70  lea     rax, [rsp+98h+var_58]
0x18015bf75  mov     [rsp+98h+pcbResult], rax; int
0x18015bf7a  mov     r9d, 4; cbOutput
0x18015bf80  lea     r8, [rsp+98h+pbOutput]; pbOutput
0x18015bf85  lea     rdx, aLength; "Length"
0x18015bf8c  call    cs:__imp_NCryptGetProperty
0x18015bf92  mov     esi, eax
0x18015bf94  test    eax, eax
0x18015bf96  jns     short loc_18015BFC6
0x18015bf98  mov     rcx, [rsp+98h]; this
0x18015bfa0  mov     r9d, eax; char *
0x18015bfa3  lea     r8, aOnecoreuapAdmi_62; "onecoreuap\\admin\\moderndeployment\\au"...
0x18015bfaa  mov     edx, 4Eh ; 'N'; void *
0x18015bfaf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015bfb4  nop
0x18015bfb5  lea     rcx, [rsp+98h+var_48]
0x18015bfba  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18015bfbf  mov     eax, esi
0x18015bfc1  jmp     loc_18015C100
0x18015bfc6  cmp     [rsp+98h+var_58], 4
0x18015bfcb  jz      short loc_18015C000
0x18015bfcd  mov     rcx, [rsp+98h]; this
0x18015bfd5  mov     ebx, 8000FFFFh
0x18015bfda  mov     r9d, ebx; char *
0x18015bfdd  lea     r8, aOnecoreuapAdmi_62; "onecoreuap\\admin\\moderndeployment\\au"...
0x18015bfe4  mov     edx, 4Fh ; 'O'; void *
0x18015bfe9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015bfee  nop
0x18015bfef  lea     rcx, [rsp+98h+var_48]
0x18015bff4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18015bff9  mov     eax, ebx
0x18015bffb  jmp     loc_18015C100
0x18015c000  mov     edx, dword ptr [rsp+98h+pbOutput]
0x18015c004  test    edx, edx
0x18015c006  jnz     short loc_18015C03B
0x18015c008  mov     rcx, [rsp+98h]; this
0x18015c010  mov     ebx, 8000FFFFh
0x18015c015  mov     r9d, ebx; char *
0x18015c018  lea     r8, aOnecoreuapAdmi_62; "onecoreuap\\admin\\moderndeployment\\au"...
0x18015c01f  mov     edx, 50h ; 'P'; void *
0x18015c024  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015c029  nop
0x18015c02a  lea     rcx, [rsp+98h+var_48]
0x18015c02f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18015c034  mov     eax, ebx
0x18015c036  jmp     loc_18015C100
0x18015c03b  lea     r8, [rbx+0B8h]
0x18015c042  lea     rcx, [rsp+98h+var_48]
0x18015c047  call    ?GetKeyTypeFromAlgorithmId@TpmKeyTypes@Core@Autopilot@ModernDeployment@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KAEAW4IdkKeyType@1234@@Z; ModernDeployment::Autopilot::Core::TpmKeyTypes::GetKeyTypeFromAlgorithmId(std::wstring const &,ulong,ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType &)
0x18015c04c  mov     esi, eax
0x18015c04e  test    eax, eax
0x18015c050  jns     short loc_18015C080
0x18015c052  mov     rcx, [rsp+98h]; this
0x18015c05a  mov     r9d, eax; char *
0x18015c05d  lea     r8, aOnecoreuapAdmi_62; "onecoreuap\\admin\\moderndeployment\\au"...
0x18015c064  mov     edx, 52h ; 'R'; void *
0x18015c069  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015c06e  nop
0x18015c06f  lea     rcx, [rsp+98h+var_48]
0x18015c074  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18015c079  mov     eax, esi
0x18015c07b  jmp     loc_18015C100
0x18015c080  mov     rdx, r14
0x18015c083  lea     rcx, [rsp+98h+var_68]
0x18015c088  call    ??0?$shared_ptr@VAutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>(std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager> const &)
0x18015c08d  mov     rdx, [rax]
0x18015c090  mov     rcx, [rbx]
0x18015c093  mov     [rax], rcx
0x18015c096  mov     [rbx], rdx
0x18015c099  mov     r8, [rax+8]
0x18015c09d  mov     rcx, [rbx+8]
0x18015c0a1  mov     [rax+8], rcx
0x18015c0a5  mov     [rbx+8], r8
0x18015c0a9  mov     rcx, [rsp+98h+var_60]; this
0x18015c0ae  test    rcx, rcx
0x18015c0b1  jz      short loc_18015C0B8
0x18015c0b3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18015c0b8  lea     rcx, [rbx+10h]
0x18015c0bc  cmp     rcx, rdi
0x18015c0bf  jz      short loc_18015C0C9
0x18015c0c1  mov     rdx, rdi
0x18015c0c4  call    ??4?$shared_ptr@VEtwProcessingDataEntry@Diagnostics@Autopilot@Windows@Microsoft@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Microsoft::Windows::Autopilot::Diagnostics::EtwProcessingDataEntry>::operator=(std::shared_ptr<Microsoft::Windows::Autopilot::Diagnostics::EtwProcessingDataEntry> &&)
0x18015c0c9  lea     rcx, [rbx+40h]
0x18015c0cd  lea     rdx, [rsp+98h+var_48]
0x18015c0d2  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18015c0d7  lea     rcx, [rbx+60h]
0x18015c0db  lea     rdx, aSha256_0; "SHA256"
0x18015c0e2  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18015c0e7  mov     byte ptr [rbx+0BCh], 1
0x18015c0ee  lea     rcx, [rsp+98h+var_48]
0x18015c0f3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18015c0f8  xor     eax, eax
0x18015c0fa  jmp     short loc_18015C100
0x18015c0fc  mov     eax, dword ptr [rsp+98h+pbOutput]
0x18015c100  mov     rcx, [rsp+98h+var_28]
0x18015c105  xor     rcx, rsp; StackCookie
0x18015c108  call    __security_check_cookie
0x18015c10d  mov     rbx, [rsp+98h+arg_18]
0x18015c115  add     rsp, 80h
0x18015c11c  pop     r14
0x18015c11e  pop     rdi
0x18015c11f  pop     rsi
0x18015c120  retn
```
