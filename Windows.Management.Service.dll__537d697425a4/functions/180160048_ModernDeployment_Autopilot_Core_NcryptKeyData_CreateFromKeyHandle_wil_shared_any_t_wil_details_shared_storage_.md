# ModernDeployment::Autopilot::Core::NcryptKeyData::CreateFromKeyHandle(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>>> &,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>>> &,ModernDeployment::Autopilot::Core::NcryptKeyData &)

- ea: `0x180160048`
- end: `0x180160418`
- name: `?CreateFromKeyHandle@NcryptKeyData@Core@Autopilot@ModernDeployment@@SAJAEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@0AEAV1234@@Z`
- size: `976`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18013b524`

## callees

- `0x18000b8f0`
- `0x180067e54`
- `0x18006ee48`
- `0x180077c04`
- `0x180077de0`
- `0x180080bac`
- `0x180080c10`
- `0x180081f38`
- `0x18008d290`
- `0x18008d6d8`
- `0x180094ce0`
- `0x1801405e4`
- `0x180160048`

## import_xrefs

- `ncrypt!NCryptGetProperty` at `0x1801600de`
- `ncrypt!NCryptGetProperty` at `0x1801601bc`
- `ncrypt!NCryptGetProperty` at `0x18016027c`
- `ncrypt!NCryptGetProperty` at `0x1801600de`
- `ncrypt!NCryptGetProperty` at `0x1801601bc`
- `ncrypt!NCryptGetProperty` at `0x18016027c`

## string_xrefs

- `0x180160090`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\ncryptkeydata.cpp`
- `0x1801600fb`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\ncryptkeydata.cpp`
- `0x180160166`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\ncryptkeydata.cpp`
- `0x1801601d9`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\ncryptkeydata.cpp`
- `0x180160216`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\ncryptkeydata.cpp`
- `0x180160299`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\ncryptkeydata.cpp`
- `0x1801602d3`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\ncryptkeydata.cpp`
- `0x18016030e`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\ncryptkeydata.cpp`
- `0x180160353`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\ncryptkeydata.cpp`

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
0x180160048  mov     [rsp+arg_18], rbx
0x18016004d  push    rsi
0x18016004e  push    rdi
0x18016004f  push    r14
0x180160051  sub     rsp, 80h
0x180160058  mov     rax, cs:__security_cookie
0x18016005f  xor     rax, rsp
0x180160062  mov     [rsp+98h+var_28], rax
0x180160067  mov     rbx, r8
0x18016006a  mov     rdi, rdx
0x18016006d  mov     r14, rcx
0x180160070  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x180160077  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x18016007c  test    al, al
0x18016007e  jnz     short loc_1801600A8
0x180160080  mov     rcx, [rsp+98h]; this
0x180160088  mov     ebx, 80004001h
0x18016008d  mov     r9d, ebx; char *
0x180160090  lea     r8, aOnecoreuapAdmi_62; "onecoreuap\\admin\\moderndeployment\\au"...
0x180160097  mov     edx, 2Bh ; '+'; void *
0x18016009c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801600a1  mov     eax, ebx
0x1801600a3  jmp     loc_1801603F6
0x1801600a8  mov     [rsp+98h+cbOutput], 0
0x1801600b0  mov     rax, [rdi]
0x1801600b3  test    rax, rax
0x1801600b6  jz      short loc_1801600BD
0x1801600b8  mov     rcx, [rax]
0x1801600bb  jmp     short loc_1801600BF
0x1801600bd  xor     ecx, ecx; hObject
0x1801600bf  mov     [rsp+98h+dwFlags], 0; dwFlags
0x1801600c7  lea     rax, [rsp+98h+cbOutput]
0x1801600cc  mov     [rsp+98h+pcbResult], rax; int
0x1801600d1  xor     r9d, r9d; cbOutput
0x1801600d4  xor     r8d, r8d; pbOutput
0x1801600d7  lea     rdx, aAlgorithmName; "Algorithm Name"
0x1801600de  call    cs:__imp_NCryptGetProperty
0x1801600e5  nop     dword ptr [rax+rax+00h]
0x1801600ea  mov     esi, eax
0x1801600ec  test    eax, eax
0x1801600ee  jns     short loc_180160113
0x1801600f0  mov     rcx, [rsp+98h]; this
0x1801600f8  mov     r9d, eax; char *
0x1801600fb  lea     r8, aOnecoreuapAdmi_62; "onecoreuap\\admin\\moderndeployment\\au"...
0x180160102  mov     edx, 36h ; '6'; void *
0x180160107  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016010c  mov     eax, esi
0x18016010e  jmp     loc_1801603F6
0x180160113  xorps   xmm0, xmm0
0x180160116  movups  [rsp+98h+var_48], xmm0
0x18016011b  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180160123  movdqu  [rsp+98h+var_38], xmm1
0x180160129  xor     eax, eax
0x18016012b  mov     word ptr [rsp+98h+var_48], ax
0x180160130  xor     r8d, r8d
0x180160133  mov     edx, [rsp+98h+cbOutput]
0x180160137  shr     rdx, 1
0x18016013a  lea     rcx, [rsp+98h+var_48]
0x18016013f  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180160144  lea     rcx, [rsp+98h+var_48]
0x180160149  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18016014e  mov     r8, rax; pbOutput
0x180160151  test    rax, rax
0x180160154  jnz     short loc_180160187
0x180160156  mov     rcx, [rsp+98h]; this
0x18016015e  mov     ebx, 8007000Eh
0x180160163  mov     r9d, ebx; char *
0x180160166  lea     r8, aOnecoreuapAdmi_62; "onecoreuap\\admin\\moderndeployment\\au"...
0x18016016d  lea     edx, [rax+3Ah]; void *
0x180160170  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180160175  nop
0x180160176  lea     rcx, [rsp+98h+var_48]
0x18016017b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180160180  mov     eax, ebx
0x180160182  jmp     loc_1801603F6
0x180160187  mov     [rsp+98h+var_58], 0
0x18016018f  mov     rax, [rdi]
0x180160192  test    rax, rax
0x180160195  jz      short loc_18016019C
0x180160197  mov     rcx, [rax]
0x18016019a  jmp     short loc_18016019E
0x18016019c  xor     ecx, ecx; hObject
0x18016019e  mov     [rsp+98h+dwFlags], 0; dwFlags
0x1801601a6  lea     rax, [rsp+98h+var_58]
0x1801601ab  mov     [rsp+98h+pcbResult], rax; int
0x1801601b0  mov     r9d, [rsp+98h+cbOutput]; cbOutput
0x1801601b5  lea     rdx, aAlgorithmName; "Algorithm Name"
0x1801601bc  call    cs:__imp_NCryptGetProperty
0x1801601c3  nop     dword ptr [rax+rax+00h]
0x1801601c8  mov     esi, eax
0x1801601ca  test    eax, eax
0x1801601cc  jns     short loc_1801601FC
0x1801601ce  mov     rcx, [rsp+98h]; this
0x1801601d6  mov     r9d, eax; char *
0x1801601d9  lea     r8, aOnecoreuapAdmi_62; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801601e0  mov     edx, 43h ; 'C'; void *
0x1801601e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801601ea  nop
0x1801601eb  lea     rcx, [rsp+98h+var_48]
0x1801601f0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801601f5  mov     eax, esi
0x1801601f7  jmp     loc_1801603F6
0x1801601fc  mov     eax, [rsp+98h+cbOutput]
0x180160200  cmp     [rsp+98h+var_58], eax
0x180160204  jz      short loc_180160239
0x180160206  mov     rcx, [rsp+98h]; this
0x18016020e  mov     ebx, 8000FFFFh
0x180160213  mov     r9d, ebx; char *
0x180160216  lea     r8, aOnecoreuapAdmi_62; "onecoreuap\\admin\\moderndeployment\\au"...
0x18016021d  mov     edx, 44h ; 'D'; void *
0x180160222  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180160227  nop
0x180160228  lea     rcx, [rsp+98h+var_48]
0x18016022d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180160232  mov     eax, ebx
0x180160234  jmp     loc_1801603F6
0x180160239  mov     [rsp+98h+var_58], 0
0x180160241  mov     dword ptr [rsp+98h+pbOutput], 0
0x180160249  mov     rax, [rdi]
0x18016024c  test    rax, rax
0x18016024f  jz      short loc_180160256
0x180160251  mov     rcx, [rax]
0x180160254  jmp     short loc_180160258
0x180160256  xor     ecx, ecx; hObject
0x180160258  mov     [rsp+98h+dwFlags], 0; dwFlags
0x180160260  lea     rax, [rsp+98h+var_58]
0x180160265  mov     [rsp+98h+pcbResult], rax; int
0x18016026a  mov     r9d, 4; cbOutput
0x180160270  lea     r8, [rsp+98h+pbOutput]; pbOutput
0x180160275  lea     rdx, aLength; "Length"
0x18016027c  call    cs:__imp_NCryptGetProperty
0x180160283  nop     dword ptr [rax+rax+00h]
0x180160288  mov     esi, eax
0x18016028a  test    eax, eax
0x18016028c  jns     short loc_1801602BC
0x18016028e  mov     rcx, [rsp+98h]; this
0x180160296  mov     r9d, eax; char *
0x180160299  lea     r8, aOnecoreuapAdmi_62; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801602a0  mov     edx, 4Eh ; 'N'; void *
0x1801602a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801602aa  nop
0x1801602ab  lea     rcx, [rsp+98h+var_48]
0x1801602b0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801602b5  mov     eax, esi
0x1801602b7  jmp     loc_1801603F6
0x1801602bc  cmp     [rsp+98h+var_58], 4
0x1801602c1  jz      short loc_1801602F6
0x1801602c3  mov     rcx, [rsp+98h]; this
0x1801602cb  mov     ebx, 8000FFFFh
0x1801602d0  mov     r9d, ebx; char *
0x1801602d3  lea     r8, aOnecoreuapAdmi_62; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801602da  mov     edx, 4Fh ; 'O'; void *
0x1801602df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801602e4  nop
0x1801602e5  lea     rcx, [rsp+98h+var_48]
0x1801602ea  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801602ef  mov     eax, ebx
0x1801602f1  jmp     loc_1801603F6
0x1801602f6  mov     edx, dword ptr [rsp+98h+pbOutput]
0x1801602fa  test    edx, edx
0x1801602fc  jnz     short loc_180160331
0x1801602fe  mov     rcx, [rsp+98h]; this
0x180160306  mov     ebx, 8000FFFFh
0x18016030b  mov     r9d, ebx; char *
0x18016030e  lea     r8, aOnecoreuapAdmi_62; "onecoreuap\\admin\\moderndeployment\\au"...
0x180160315  mov     edx, 50h ; 'P'; void *
0x18016031a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016031f  nop
0x180160320  lea     rcx, [rsp+98h+var_48]
0x180160325  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18016032a  mov     eax, ebx
0x18016032c  jmp     loc_1801603F6
0x180160331  lea     r8, [rbx+0B8h]
0x180160338  lea     rcx, [rsp+98h+var_48]
0x18016033d  call    ?GetKeyTypeFromAlgorithmId@TpmKeyTypes@Core@Autopilot@ModernDeployment@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KAEAW4IdkKeyType@1234@@Z; ModernDeployment::Autopilot::Core::TpmKeyTypes::GetKeyTypeFromAlgorithmId(std::wstring const &,ulong,ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType &)
0x180160342  mov     esi, eax
0x180160344  test    eax, eax
0x180160346  jns     short loc_180160376
0x180160348  mov     rcx, [rsp+98h]; this
0x180160350  mov     r9d, eax; char *
0x180160353  lea     r8, aOnecoreuapAdmi_62; "onecoreuap\\admin\\moderndeployment\\au"...
0x18016035a  mov     edx, 52h ; 'R'; void *
0x18016035f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180160364  nop
0x180160365  lea     rcx, [rsp+98h+var_48]
0x18016036a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18016036f  mov     eax, esi
0x180160371  jmp     loc_1801603F6
0x180160376  mov     rdx, r14
0x180160379  lea     rcx, [rsp+98h+var_68]
0x18016037e  call    ??0?$shared_ptr@VAutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>(std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager> const &)
0x180160383  mov     rdx, [rax]
0x180160386  mov     rcx, [rbx]
0x180160389  mov     [rax], rcx
0x18016038c  mov     [rbx], rdx
0x18016038f  mov     r8, [rax+8]
0x180160393  mov     rcx, [rbx+8]
0x180160397  mov     [rax+8], rcx
0x18016039b  mov     [rbx+8], r8
0x18016039f  mov     rcx, [rsp+98h+var_60]; this
0x1801603a4  test    rcx, rcx
0x1801603a7  jz      short loc_1801603AE
0x1801603a9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801603ae  lea     rcx, [rbx+10h]
0x1801603b2  cmp     rcx, rdi
0x1801603b5  jz      short loc_1801603BF
0x1801603b7  mov     rdx, rdi
0x1801603ba  call    ??4?$shared_ptr@VEtwProcessingDataEntry@Diagnostics@Autopilot@Windows@Microsoft@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Microsoft::Windows::Autopilot::Diagnostics::EtwProcessingDataEntry>::operator=(std::shared_ptr<Microsoft::Windows::Autopilot::Diagnostics::EtwProcessingDataEntry> &&)
0x1801603bf  lea     rcx, [rbx+40h]
0x1801603c3  lea     rdx, [rsp+98h+var_48]
0x1801603c8  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1801603cd  lea     rcx, [rbx+60h]
0x1801603d1  lea     rdx, aSha256_0; "SHA256"
0x1801603d8  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1801603dd  mov     byte ptr [rbx+0BCh], 1
0x1801603e4  lea     rcx, [rsp+98h+var_48]
0x1801603e9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801603ee  xor     eax, eax
0x1801603f0  jmp     short loc_1801603F6
0x1801603f2  mov     eax, dword ptr [rsp+98h+pbOutput]
0x1801603f6  mov     rcx, [rsp+98h+var_28]
0x1801603fb  xor     rcx, rsp; StackCookie
0x1801603fe  call    __security_check_cookie
0x180160403  mov     rbx, [rsp+98h+arg_18]
0x18016040b  add     rsp, 80h
0x180160412  pop     r14
0x180160414  pop     rdi
0x180160415  pop     rsi
0x180160416  retn
```
