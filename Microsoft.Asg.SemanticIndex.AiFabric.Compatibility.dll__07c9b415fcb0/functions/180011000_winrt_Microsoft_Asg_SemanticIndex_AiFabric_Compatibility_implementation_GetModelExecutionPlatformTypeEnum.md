# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::GetModelExecutionPlatformTypeEnum

- ea: `0x180011000`
- end: `0x1800114d0`
- name: `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::GetModelExecutionPlatformTypeEnum`
- size: `1232`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800114d0`

## callees

- `0x180007de0`
- `0x180011000`
- `0x180011680`
- `0x1800116e0`
- `0x180011710`
- `0x18007aef0`
- `0x18007b3e0`
- `0x1801f7110`
- `0x18022ae9c`
- `0x180242120`

## import_xrefs

- `KERNEL32!ProcessIdToSessionId` at `0x18001104f`
- `KERNEL32!ProcessIdToSessionId` at `0x18001104f`
- `KERNEL32!GetCurrentProcessId` at `0x180011042`
- `KERNEL32!GetCurrentProcessId` at `0x180011042`
- `ext-ms-win-dxcore-l1-1-0!DXCoreCreateAdapterFactory` at `0x180011119`
- `ext-ms-win-dxcore-l1-1-0!DXCoreCreateAdapterFactory` at `0x180011119`

## string_xrefs

- `0x180011290`: `Detected unknown Qualcomm NPU device: vendor 0x%X device 0x%X`

## pseudocode

```c
__int64 winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::GetModelExecutionPlatformTypeEnum()
{
  unsigned int v0; // r14d
  DWORD CurrentProcessId; // eax
  char IsEnabled; // r15
  int v4; // ebx
  __int64 *v5; // r12
  int v6; // esi
  __int64 v7; // rdi
  unsigned int i; // edi
  int v9; // [rsp+28h] [rbp-D8h]
  DWORD pSessionId[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v11; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID v12; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v13; // [rsp+48h] [rbp-B8h] BYREF
  int v14[4]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v15; // [rsp+60h] [rbp-A0h]
  int v16[4]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v17; // [rsp+80h] [rbp-80h]
  int v18[8]; // [rsp+90h] [rbp-70h] BYREF
  char v19; // [rsp+B0h] [rbp-50h]
  IID rclsid; // [rsp+C8h] [rbp-38h] BYREF
  LPVOID ppv[2]; // [rsp+D8h] [rbp-28h] BYREF
  _OWORD v22[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v23; // [rsp+108h] [rbp+8h] BYREF

  v0 = 0;
  if ( !(unsigned __int8)asg::IsFeatureEnabled<wil::Feature<__WilFeatureTraits_Feature_57003568>>() )
    goto LABEL_8;
  CurrentProcessId = GetCurrentProcessId();
  if ( !ProcessIdToSessionId(CurrentProcessId, pSessionId) )
    goto LABEL_8;
  v12 = 0;
  ppv[0] = 0;
  if ( pSessionId[0] )
  {
    rclsid.Data1 = 1404625999;
    *(_DWORD *)&rclsid.Data2 = 1203190916;
    *(_DWORD *)rclsid.Data4 = 879052420;
    *(_DWORD *)&rclsid.Data4[4] = -1848953998;
  }
  else
  {
    rclsid.Data1 = -1660147340;
    *(_DWORD *)&rclsid.Data2 = 1108319961;
    *(_DWORD *)rclsid.Data4 = -456345442;
    *(_DWORD *)&rclsid.Data4[4] = -813877218;
  }
  CoCreateInstance_0(&rclsid, 0, 4u, &winrt::impl::guid_v<IHCFContractManager>, ppv);
  v12 = ppv[0];
  if ( ppv[0] )
  {
    winrt::com_ptr<IDXCoreAdapter>::unconditional_release_ref(&v12);
    return 4;
  }
  else
  {
LABEL_8:
    v11 = 0;
    v13 = 0;
    if ( (int)DXCoreCreateAdapterFactory(&GUID_78ee5945_c36e_4b13_a669_005dd11c0f06, &v13) < 0 )
      goto LABEL_58;
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_60237387>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60237387>::GetImpl'::`2'::impl);
    v4 = 0;
    v22[0] = DXCORE_HARDWARE_TYPE_ATTRIBUTE_NPU;
    v22[1] = DXCORE_ADAPTER_ATTRIBUTE_D3D12_GENERIC_ML;
    v5 = (__int64 *)v22;
    v6 = 3;
    do
    {
      *(_OWORD *)ppv = *(_OWORD *)v5;
      v7 = v13;
      if ( v11 )
        winrt::com_ptr<IDXCoreAdapter>::unconditional_release_ref(&v11);
      if ( (*(int (__fastcall **)(__int64, __int64, LPVOID *, GUID *, __int64 *, int))(*(_QWORD *)v7 + 24LL))(
             v7,
             1,
             ppv,
             &GUID_526c7776_40e9_459b_b711_f32ad76dfc28,
             &v11,
             v9) >= 0 )
      {
        for ( i = 0; i < (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v11 + 32LL))(v11); ++i )
        {
          *(_QWORD *)pSessionId = 0;
          if ( (*(int (__fastcall **)(__int64, _QWORD, GUID *, DWORD *))(*(_QWORD *)v11 + 24LL))(
                 v11,
                 i,
                 &GUID_f0db4c7f_fe5a_42a2_bd62_f2a6cf6fc83e,
                 pSessionId) >= 0 )
          {
            rclsid = 0;
            if ( (*(int (__fastcall **)(_QWORD, __int64, __int64, IID *))(**(_QWORD **)pSessionId + 48LL))(
                   *(_QWORD *)pSessionId,
                   3,
                   16,
                   &rclsid) >= 0 )
            {
              if ( IsEnabled )
              {
                switch ( rclsid.Data1 )
                {
                  case 0x1022u:
                    if ( *(_DWORD *)&rclsid.Data2 == 6128 )
                      goto LABEL_63;
                    BYTE8(v17) = 0;
                    *(_OWORD *)v14 = *(_OWORD *)v16;
                    v15 = v17;
                    v9 = *(_DWORD *)&rclsid.Data2;
                    asg::details::_asg_Log<std::integral_constant<bool,1>>(
                      (int)v18,
                      (int)v14,
                      1,
                      (int)L"Detected unknown AMD NPU device: vendor 0x%X device 0x%X",
                      34);
                    if ( v19 )
                      std::basic_string<char16_t>::_Tidy_deallocate(v18);
                    if ( !v4 )
                      v4 = 2;
                    break;
                  case 0x8086u:
                    if ( *(_DWORD *)&rclsid.Data2 == 25662 )
                      goto LABEL_46;
                    BYTE8(v17) = 0;
                    *(_OWORD *)v14 = *(_OWORD *)v16;
                    v15 = v17;
                    v9 = *(_DWORD *)&rclsid.Data2;
                    asg::details::_asg_Log<std::integral_constant<bool,1>>(
                      (int)v18,
                      (int)v14,
                      1,
                      (int)L"Detected unknown Intel NPU device: vendor 0x%X device 0x%X",
                      134);
                    if ( v19 )
                      std::basic_string<char16_t>::_Tidy_deallocate(v18);
                    if ( !v4 )
                      v4 = 1;
                    break;
                  case 0x4D4F4351u:
                    if ( *(_DWORD *)&rclsid.Data2 == 909325872 || *(_DWORD *)&rclsid.Data2 == 1093682224 )
                      goto LABEL_64;
                    BYTE8(v15) = 0;
                    *(_OWORD *)v16 = *(_OWORD *)v14;
                    v17 = v15;
                    v9 = *(_DWORD *)&rclsid.Data2;
                    asg::details::_asg_Log<std::integral_constant<bool,1>>(
                      (int)v18,
                      (int)v16,
                      1,
                      (int)L"Detected unknown Qualcomm NPU device: vendor 0x%X device 0x%X",
                      81);
                    if ( v19 )
                      std::basic_string<char16_t>::_Tidy_deallocate(v18);
                    if ( !v4 )
                      v4 = 3;
                    break;
                }
              }
              else if ( rclsid.Data1 == 4130 )
              {
                if ( *(_DWORD *)&rclsid.Data2 == 6128 )
                {
LABEL_63:
                  v6 = 2;
LABEL_64:
                  if ( *(_QWORD *)pSessionId )
                    winrt::com_ptr<IDXCoreAdapter>::unconditional_release_ref(pSessionId);
LABEL_57:
                  v0 = v6;
                  goto LABEL_58;
                }
              }
              else if ( rclsid.Data1 == 32902 )
              {
                if ( *(_DWORD *)&rclsid.Data2 == 25662 )
                {
LABEL_46:
                  v6 = 1;
                  goto LABEL_64;
                }
              }
              else if ( rclsid.Data1 == 1297040209
                     && (*(_DWORD *)&rclsid.Data2 == 909325872 || *(_DWORD *)&rclsid.Data2 == 1093682224) )
              {
                goto LABEL_64;
              }
            }
          }
          if ( *(_QWORD *)pSessionId )
            winrt::com_ptr<IDXCoreAdapter>::unconditional_release_ref(pSessionId);
        }
      }
      v5 += 2;
    }
    while ( v5 != &v23 );
    if ( IsEnabled && v4 )
    {
      BYTE8(v17) = 0;
      *(_OWORD *)v14 = *(_OWORD *)v16;
      v15 = v17;
      asg::details::_asg_Log<std::integral_constant<bool,0>>(
        v18,
        v14,
        3,
        L"Did not detect known NPU device; falling back to vendor-only detection.");
      if ( v19 )
        std::basic_string<char16_t>::_Tidy_deallocate(v18);
      v6 = v4;
      goto LABEL_57;
    }
LABEL_58:
    if ( v13 )
      winrt::com_ptr<IDXCoreAdapter>::unconditional_release_ref(&v13);
    if ( v11 )
      winrt::com_ptr<IDXCoreAdapter>::unconditional_release_ref(&v11);
    return v0;
  }
}

```

## disassembly

```asm
0x180011000  mov     [rsp-8+arg_0], rbx
0x180011005  mov     [rsp-8+arg_8], rsi
0x18001100a  mov     [rsp-8+arg_10], rdi
0x18001100f  push    rbp
0x180011010  push    r12
0x180011012  push    r13
0x180011014  push    r14
0x180011016  push    r15
0x180011018  lea     rbp, [rsp-10h]
0x18001101d  sub     rsp, 110h
0x180011024  mov     rax, cs:__security_cookie
0x18001102b  xor     rax, rsp
0x18001102e  mov     [rbp+30h+var_28], rax
0x180011032  xor     r14d, r14d
0x180011035  call    ??$IsFeatureEnabled@V?$Feature@U__WilFeatureTraits_Feature_57003568@@@wil@@@asg@@YA_NXZ; asg::IsFeatureEnabled<wil::Feature<__WilFeatureTraits_Feature_57003568>>(void)
0x18001103a  test    al, al
0x18001103c  jz      loc_180011103
0x180011042  call    cs:__imp_GetCurrentProcessId
0x180011048  mov     ecx, eax; dwProcessId
0x18001104a  lea     rdx, [rsp+130h+pSessionId]; pSessionId
0x18001104f  call    cs:__imp_ProcessIdToSessionId
0x180011055  test    eax, eax
0x180011057  jz      loc_180011103
0x18001105d  mov     [rsp+130h+var_F0], r14
0x180011062  mov     [rbp+30h+var_58], r14
0x180011066  lea     rax, [rbp+30h+var_58]
0x18001106a  lea     r9, ??$guid_v@UIHCFContractManager@@@impl@winrt@@3Uguid@2@B; riid
0x180011071  xor     edx, edx; pUnkOuter
0x180011073  mov     r8d, 4; dwClsContext
0x180011079  lea     rcx, [rbp+30h+rclsid]; rclsid
0x18001107d  mov     [rsp+130h+ppv], rax; ppv
0x180011082  cmp     [rsp+130h+pSessionId], edx
0x180011086  jnz     short loc_1800110A6
0x180011088  mov     [rbp+30h+rclsid.Data1], 9D0C2974h
0x18001108f  mov     dword ptr [rbp+30h+rclsid.Data2], 420F9ED9h
0x180011096  mov     dword ptr [rbp+30h+rclsid.Data4], 0E4CCB89Eh
0x18001109d  mov     dword ptr [rbp+30h+rclsid.Data4+4], 0CF7D381Eh
0x1800110a4  jmp     short loc_1800110C2
0x1800110a6  mov     [rbp+30h+rclsid.Data1], 53B8E44Fh
0x1800110ad  mov     dword ptr [rbp+30h+rclsid.Data2], 47B73C84h
0x1800110b4  mov     dword ptr [rbp+30h+rclsid.Data4], 34654684h
0x1800110bb  mov     dword ptr [rbp+30h+rclsid.Data4+4], 91CB3372h
0x1800110c2  call    CoCreateInstance_0
0x1800110c7  mov     rax, [rbp+30h+var_58]
0x1800110cb  mov     rdx, rax
0x1800110ce  mov     rcx, rax
0x1800110d1  mov     [rsp+130h+var_F0], rax
0x1800110d6  test    rax, rax
0x1800110d9  jz      short loc_1800110F4
0x1800110db  test    rax, rax
0x1800110de  jz      short loc_1800110EA
0x1800110e0  lea     rcx, [rsp+130h+var_F0]
0x1800110e5  call    ?unconditional_release_ref@?$com_ptr@UIDXCoreAdapter@@@winrt@@AEAAXXZ; winrt::com_ptr<IDXCoreAdapter>::unconditional_release_ref(void)
0x1800110ea  mov     eax, 4
0x1800110ef  jmp     loc_180011489
0x1800110f4  test    rdx, rdx
0x1800110f7  jz      short loc_180011103
0x1800110f9  lea     rcx, [rsp+130h+var_F0]
0x1800110fe  call    ?unconditional_release_ref@?$com_ptr@UIDXCoreAdapter@@@winrt@@AEAAXXZ; winrt::com_ptr<IDXCoreAdapter>::unconditional_release_ref(void)
0x180011103  mov     [rsp+130h+var_F8], r14
0x180011108  mov     [rsp+130h+var_E8], r14
0x18001110d  lea     rdx, [rsp+130h+var_E8]
0x180011112  lea     rcx, _GUID_78ee5945_c36e_4b13_a669_005dd11c0f06
0x180011119  call    cs:__imp_DXCoreCreateAdapterFactory
0x18001111f  test    eax, eax
0x180011121  js      loc_180011461
0x180011127  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_60237387@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_60237387@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60237387> `wil::Feature<__WilFeatureTraits_Feature_60237387>::GetImpl(void)'::`2'::impl
0x18001112e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_60237387@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60237387>::__private_IsEnabled(void)
0x180011133  movzx   r15d, al
0x180011137  mov     ebx, r14d
0x18001113a  movups  xmm0, cs:DXCORE_HARDWARE_TYPE_ATTRIBUTE_NPU
0x180011141  movups  [rbp+30h+var_48], xmm0
0x180011145  movups  xmm1, cs:DXCORE_ADAPTER_ATTRIBUTE_D3D12_GENERIC_ML
0x18001114c  movups  [rbp+30h+var_38], xmm1
0x180011150  lea     r12, [rbp+30h+var_48]
0x180011154  mov     esi, 3
0x180011159  mov     r13d, 1
0x18001115f  nop
0x180011160  movups  xmm0, xmmword ptr [r12]
0x180011165  movups  xmmword ptr [rbp+30h+var_58], xmm0
0x180011169  mov     rdi, [rsp+130h+var_E8]
0x18001116e  cmp     [rsp+130h+var_F8], 0
0x180011174  jz      short loc_180011180
0x180011176  lea     rcx, [rsp+130h+var_F8]
0x18001117b  call    ?unconditional_release_ref@?$com_ptr@UIDXCoreAdapter@@@winrt@@AEAAXXZ; winrt::com_ptr<IDXCoreAdapter>::unconditional_release_ref(void)
0x180011180  mov     rax, [rdi]
0x180011183  lea     rcx, [rsp+130h+var_F8]
0x180011188  mov     [rsp+130h+ppv], rcx
0x18001118d  lea     r9, _GUID_526c7776_40e9_459b_b711_f32ad76dfc28
0x180011194  lea     r8, [rbp+30h+var_58]
0x180011198  mov     edx, r13d
0x18001119b  mov     rcx, rdi
0x18001119e  mov     rax, [rax+18h]
0x1800111a2  call    cs:__guard_dispatch_icall_fptr
0x1800111a8  test    eax, eax
0x1800111aa  js      loc_180011404
0x1800111b0  mov     edi, r14d
0x1800111b3  mov     rcx, [rsp+130h+var_F8]
0x1800111b8  mov     rax, [rcx]
0x1800111bb  mov     rax, [rax+20h]
0x1800111bf  call    cs:__guard_dispatch_icall_fptr
0x1800111c5  test    eax, eax
0x1800111c7  jz      loc_180011404
0x1800111cd  nop     dword ptr [rax]
0x1800111d0  mov     qword ptr [rsp+130h+pSessionId], r14
0x1800111d5  mov     rcx, [rsp+130h+var_F8]
0x1800111da  mov     rax, [rcx]
0x1800111dd  lea     r9, [rsp+130h+pSessionId]
0x1800111e2  lea     r8, _GUID_f0db4c7f_fe5a_42a2_bd62_f2a6cf6fc83e
0x1800111e9  mov     edx, edi
0x1800111eb  mov     rax, [rax+18h]
0x1800111ef  call    cs:__guard_dispatch_icall_fptr
0x1800111f5  test    eax, eax
0x1800111f7  js      loc_1800113D6
0x1800111fd  xorps   xmm0, xmm0
0x180011200  movups  xmmword ptr [rbp+30h+rclsid.Data1], xmm0
0x180011204  mov     rcx, qword ptr [rsp+130h+pSessionId]
0x180011209  mov     rax, [rcx]
0x18001120c  lea     r9, [rbp+30h+rclsid]
0x180011210  mov     r8d, 10h
0x180011216  mov     edx, esi
0x180011218  mov     rax, [rax+30h]
0x18001121c  call    cs:__guard_dispatch_icall_fptr
0x180011222  test    eax, eax
0x180011224  js      loc_1800113D6
0x18001122a  mov     eax, [rbp+30h+rclsid.Data1]
0x18001122d  test    r15b, r15b
0x180011230  jz      loc_180011388
0x180011236  cmp     eax, 1022h
0x18001123b  jz      loc_180011324
0x180011241  cmp     eax, 8086h
0x180011246  jz      short loc_1800112C1
0x180011248  cmp     eax, 4D4F4351h
0x18001124d  jnz     loc_1800113D6
0x180011253  mov     eax, dword ptr [rbp+30h+rclsid.Data2]
0x180011256  cmp     eax, 36333630h
0x18001125b  jz      loc_1800114BB
0x180011261  cmp     eax, 41304430h
0x180011266  jz      loc_1800114BB
0x18001126c  mov     [rsp+130h+var_C8], 0
0x180011271  movups  xmm0, xmmword ptr [rsp+130h+var_E0]
0x180011276  movaps  xmmword ptr [rsp+130h+var_C0], xmm0
0x18001127b  movups  xmm1, xmmword ptr [rsp+60h]
0x180011280  movaps  [rbp+30h+var_B0], xmm1
0x180011284  mov     [rsp+130h+var_108], eax
0x180011288  mov     dword ptr [rsp+130h+ppv], 4D4F4351h; ArgList
0x180011290  lea     r9, aDetectedUnknow; "Detected unknown Qualcomm NPU device: v"...
0x180011297  mov     r8d, r13d; int
0x18001129a  lea     rdx, [rsp+130h+var_C0]; int
0x18001129f  lea     rcx, [rbp+30h+var_A0]; int
0x1800112a3  call    ??$_asg_Log@U?$integral_constant@_N$00@std@@@details@asg@@YA?AULogStringView@1@V?$optional@Usource_location@std@@@std@@W4LogLevel@1@PEB_SZZ; asg::details::_asg_Log<std::integral_constant<bool,1>>(std::optional<std::source_location>,asg::LogLevel,char16_t const *,...)
0x1800112a8  cmp     [rbp+30h+var_80], 0
0x1800112ac  jz      short loc_1800112B7
0x1800112ae  lea     rcx, [rbp+30h+var_A0]
0x1800112b2  call    ?_Tidy_deallocate@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXXZ; std::basic_string<char16_t>::_Tidy_deallocate(void)
0x1800112b7  test    ebx, ebx
0x1800112b9  cmovz   ebx, esi
0x1800112bc  jmp     loc_1800113D6
0x1800112c1  mov     eax, dword ptr [rbp+30h+rclsid.Data2]
0x1800112c4  cmp     eax, 643Eh
0x1800112c9  jz      loc_1800113C1
0x1800112cf  mov     byte ptr [rbp+30h+var_B0+8], 0
0x1800112d3  movups  xmm0, xmmword ptr [rsp+130h+var_C0]
0x1800112d8  movaps  xmmword ptr [rsp+130h+var_E0], xmm0
0x1800112dd  movups  xmm1, [rbp+30h+var_B0]
0x1800112e1  movaps  xmmword ptr [rsp+60h], xmm1
0x1800112e6  mov     [rsp+130h+var_108], eax
0x1800112ea  mov     dword ptr [rsp+130h+ppv], 8086h; ArgList
0x1800112f2  lea     r9, aDetectedUnknow_1; "Detected unknown Intel NPU device: vend"...
0x1800112f9  mov     r8d, r13d; int
0x1800112fc  lea     rdx, [rsp+130h+var_E0]; int
0x180011301  lea     rcx, [rbp+30h+var_A0]; int
0x180011305  call    ??$_asg_Log@U?$integral_constant@_N$00@std@@@details@asg@@YA?AULogStringView@1@V?$optional@Usource_location@std@@@std@@W4LogLevel@1@PEB_SZZ; asg::details::_asg_Log<std::integral_constant<bool,1>>(std::optional<std::source_location>,asg::LogLevel,char16_t const *,...)
0x18001130a  cmp     [rbp+30h+var_80], 0
0x18001130e  jz      short loc_180011319
0x180011310  lea     rcx, [rbp+30h+var_A0]
0x180011314  call    ?_Tidy_deallocate@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXXZ; std::basic_string<char16_t>::_Tidy_deallocate(void)
0x180011319  test    ebx, ebx
0x18001131b  cmovz   ebx, r13d
0x18001131f  jmp     loc_1800113D6
0x180011324  mov     eax, dword ptr [rbp+30h+rclsid.Data2]
0x180011327  cmp     eax, 17F0h
0x18001132c  jz      loc_1800114B6
0x180011332  mov     byte ptr [rbp+30h+var_B0+8], 0
0x180011336  movups  xmm0, xmmword ptr [rsp+130h+var_C0]
0x18001133b  movaps  xmmword ptr [rsp+130h+var_E0], xmm0
0x180011340  movups  xmm1, [rbp+30h+var_B0]
0x180011344  movaps  xmmword ptr [rsp+60h], xmm1
0x180011349  mov     [rsp+130h+var_108], eax
0x18001134d  mov     dword ptr [rsp+130h+ppv], 1022h; ArgList
0x180011355  lea     r9, aDetectedUnknow_0; "Detected unknown AMD NPU device: vendor"...
0x18001135c  mov     r8d, r13d; int
0x18001135f  lea     rdx, [rsp+130h+var_E0]; int
0x180011364  lea     rcx, [rbp+30h+var_A0]; int
0x180011368  call    ??$_asg_Log@U?$integral_constant@_N$00@std@@@details@asg@@YA?AULogStringView@1@V?$optional@Usource_location@std@@@std@@W4LogLevel@1@PEB_SZZ; asg::details::_asg_Log<std::integral_constant<bool,1>>(std::optional<std::source_location>,asg::LogLevel,char16_t const *,...)
0x18001136d  cmp     [rbp+30h+var_80], 0
0x180011371  jz      short loc_18001137C
0x180011373  lea     rcx, [rbp+30h+var_A0]
0x180011377  call    ?_Tidy_deallocate@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXXZ; std::basic_string<char16_t>::_Tidy_deallocate(void)
0x18001137c  test    ebx, ebx
0x18001137e  mov     eax, 2
0x180011383  cmovz   ebx, eax
0x180011386  jmp     short loc_1800113D6
0x180011388  cmp     eax, 1022h
0x18001138d  jz      short loc_1800113C9
0x18001138f  cmp     eax, 8086h
0x180011394  jz      short loc_1800113B8
0x180011396  cmp     eax, 4D4F4351h
0x18001139b  jnz     short loc_1800113D6
0x18001139d  mov     eax, dword ptr [rbp+30h+rclsid.Data2]
0x1800113a0  cmp     eax, 36333630h
0x1800113a5  jz      loc_1800114BB
0x1800113ab  cmp     eax, 41304430h
0x1800113b0  jz      loc_1800114BB
0x1800113b6  jmp     short loc_1800113D6
0x1800113b8  cmp     dword ptr [rbp+30h+rclsid.Data2], 643Eh
0x1800113bf  jnz     short loc_1800113D6
0x1800113c1  mov     esi, r13d
0x1800113c4  jmp     loc_1800114BB
0x1800113c9  cmp     dword ptr [rbp+30h+rclsid.Data2], 17F0h
0x1800113d0  jz      loc_1800114B6
0x1800113d6  cmp     qword ptr [rsp+130h+pSessionId], 0
0x1800113dc  jz      short loc_1800113E8
0x1800113de  lea     rcx, [rsp+130h+pSessionId]
0x1800113e3  call    ?unconditional_release_ref@?$com_ptr@UIDXCoreAdapter@@@winrt@@AEAAXXZ; winrt::com_ptr<IDXCoreAdapter>::unconditional_release_ref(void)
0x1800113e8  inc     edi
0x1800113ea  mov     rcx, [rsp+130h+var_F8]
0x1800113ef  mov     rax, [rcx]
0x1800113f2  mov     rax, [rax+20h]
0x1800113f6  call    cs:__guard_dispatch_icall_fptr
0x1800113fc  cmp     edi, eax
0x1800113fe  jb      loc_1800111D0
0x180011404  add     r12, 10h
0x180011408  lea     rax, [rbp+30h+var_28]
0x18001140c  cmp     r12, rax
0x18001140f  jnz     loc_180011160
0x180011415  test    r15b, r15b
0x180011418  jz      short loc_180011461
0x18001141a  test    ebx, ebx
0x18001141c  jz      short loc_180011461
0x18001141e  mov     byte ptr [rbp+30h+var_B0+8], 0
0x180011422  movups  xmm0, xmmword ptr [rsp+130h+var_C0]
0x180011427  movaps  xmmword ptr [rsp+130h+var_E0], xmm0
0x18001142c  movups  xmm1, [rbp+30h+var_B0]
0x180011430  movaps  xmmword ptr [rsp+60h], xmm1
0x180011435  lea     r9, aDidNotDetectKn; "Did not detect known NPU device; fallin"...
0x18001143c  mov     r8d, esi
0x18001143f  lea     rdx, [rsp+130h+var_E0]
0x180011444  lea     rcx, [rbp+30h+var_A0]
0x180011448  call    ??$_asg_Log@U?$integral_constant@_N$0A@@std@@@details@asg@@YA?AULogStringView@1@V?$optional@Usource_location@std@@@std@@W4LogLevel@1@PEB_SZZ; asg::details::_asg_Log<std::integral_constant<bool,0>>(std::optional<std::source_location>,asg::LogLevel,char16_t const *,...)
0x18001144d  cmp     [rbp+30h+var_80], 0
0x180011451  jz      short loc_18001145C
0x180011453  lea     rcx, [rbp+30h+var_A0]
0x180011457  call    ?_Tidy_deallocate@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXXZ; std::basic_string<char16_t>::_Tidy_deallocate(void)
0x18001145c  mov     esi, ebx
0x18001145e  mov     r14d, esi
0x180011461  cmp     [rsp+130h+var_E8], 0
0x180011467  jz      short loc_180011474
0x180011469  lea     rcx, [rsp+130h+var_E8]
0x18001146e  call    ?unconditional_release_ref@?$com_ptr@UIDXCoreAdapter@@@winrt@@AEAAXXZ; winrt::com_ptr<IDXCoreAdapter>::unconditional_release_ref(void)
0x180011473  nop
0x180011474  cmp     [rsp+130h+var_F8], 0
0x18001147a  jz      short loc_180011486
0x18001147c  lea     rcx, [rsp+130h+var_F8]
0x180011481  call    ?unconditional_release_ref@?$com_ptr@UIDXCoreAdapter@@@winrt@@AEAAXXZ; winrt::com_ptr<IDXCoreAdapter>::unconditional_release_ref(void)
0x180011486  mov     eax, r14d
0x180011489  mov     rcx, [rbp+30h+var_28]
0x18001148d  xor     rcx, rsp; StackCookie
0x180011490  call    __security_check_cookie
0x180011495  lea     r11, [rsp+130h+var_20]
0x18001149d  mov     rbx, [r11+30h]
0x1800114a1  mov     rsi, [r11+38h]
0x1800114a5  mov     rdi, [r11+40h]
0x1800114a9  mov     rsp, r11
0x1800114ac  pop     r15
0x1800114ae  pop     r14
0x1800114b0  pop     r13
0x1800114b2  pop     r12
0x1800114b4  pop     rbp
0x1800114b5  retn
0x1800114b6  mov     esi, 2
0x1800114bb  cmp     qword ptr [rsp+130h+pSessionId], 0
0x1800114c1  jz      short loc_18001145E
0x1800114c3  lea     rcx, [rsp+130h+pSessionId]
0x1800114c8  call    ?unconditional_release_ref@?$com_ptr@UIDXCoreAdapter@@@winrt@@AEAAXXZ; winrt::com_ptr<IDXCoreAdapter>::unconditional_release_ref(void)
0x1800114cd  jmp     short loc_18001145E
```
