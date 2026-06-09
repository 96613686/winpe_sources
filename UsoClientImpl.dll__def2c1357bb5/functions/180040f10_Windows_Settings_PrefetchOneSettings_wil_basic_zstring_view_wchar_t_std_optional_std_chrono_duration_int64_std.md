# Windows::Settings::PrefetchOneSettings(wil::basic_zstring_view<wchar_t>,std::optional<std::chrono::duration<__int64,std::ratio<1,1>>>)

- ea: `0x180040f10`
- end: `0x1800411e8`
- name: `?PrefetchOneSettings@Settings@Windows@@UEAAXV?$basic_zstring_view@_W@wil@@V?$optional@V?$duration@_JU?$ratio@$00$00@std@@@chrono@std@@@std@@@Z`
- size: `728`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18002d1a4`
- `0x180035a50`
- `0x18003a7dc`
- `0x18003ac98`
- `0x180040f10`
- `0x1800411f0`
- `0x180042b28`
- `0x180045514`
- `0x180047ff8`
- `0x1800563c8`
- `0x180056500`
- `0x18005c5e0`

## string_xrefs

- `0x180040f54`: `WindowsUdk.Management.Update.ManagementUpdateContract`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Settings::PrefetchOneSettings(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 result; // rax
  const char *v6; // r9
  __int64 v7; // rcx
  char v8; // bl
  const wchar_t *v9; // rdx
  __int64 v10; // rcx
  int *v11; // r8
  int v12; // eax
  __int64 v13; // rax
  int *v14; // [rsp+38h] [rbp-70h] BYREF
  int *v15; // [rsp+40h] [rbp-68h] BYREF
  int v16; // [rsp+48h] [rbp-60h] BYREF
  int v17; // [rsp+4Ch] [rbp-5Ch]
  const wchar_t *v18; // [rsp+58h] [rbp-50h]
  __int64 v19; // [rsp+60h] [rbp-48h] BYREF
  int *v20; // [rsp+68h] [rbp-40h] BYREF
  _DWORD v21[4]; // [rsp+70h] [rbp-38h] BYREF
  const wchar_t *v22; // [rsp+80h] [rbp-28h]
  __int64 v23; // [rsp+88h] [rbp-20h] BYREF
  char v24[8]; // [rsp+90h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  result = Windows::UdkVersionChecker::_anonymous_namespace_::IsUdkSupported(a1);
  try
  {
    if ( (_BYTE)result )
    {
      v7 = -1;
      do
        ++v7;
      while ( winrt::WindowsUdk::Management::Update::ManagementUpdateContractName[v7] );
      if ( (_DWORD)v7 )
      {
        if ( winrt::WindowsUdk::Management::Update::ManagementUpdateContractName[(unsigned int)v7] )
          abort();
        v16 = 1;
        v17 = v7;
        v18 = L"WindowsUdk.Management.Update.ManagementUpdateContract";
        v15 = &v16;
      }
      else
      {
        v15 = 0;
      }
      v8 = 3;
      result = winrt::WindowsUdk::Foundation::Metadata::ApiInformation::IsApiContractPresent(
                 (const struct winrt::param::hstring *)&v15,
                 3u);
      if ( (_BYTE)result )
      {
        winrt::single_threaded_map<winrt::hstring,winrt::hstring,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::hstring>>>(&v14);
        v9 = *(const wchar_t **)a2;
        v10 = *(unsigned int *)(a2 + 8);
        if ( (_DWORD)v10 )
        {
          if ( v9[v10] )
            abort();
          v16 = 1;
          v17 = v10;
          v18 = v9;
          v15 = &v16;
          v11 = &v16;
        }
        else
        {
          v15 = 0;
          v11 = 0;
        }
        v21[0] = 1;
        v21[1] = 9;
        v22 = L"OSVersion";
        v20 = v21;
        v24[0] = 0;
        v12 = (*(__int64 (__fastcall **)(int *, _DWORD *, int *, char *))(*(_QWORD *)v14 + 80LL))(v14, v21, v11, v24);
        if ( v12 < 0 )
          winrt::throw_hresult((unsigned int)v12);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_PackageContainment_53093331>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_PackageContainment_53093331>::GetImpl'::`2'::impl) )
        {
          if ( *(_BYTE *)(a3 + 8) )
          {
            LOBYTE(v16) = 0;
            v15 = v14;
            v13 = winrt::WindowsUdk::Management::Update::FeatureStagingManager::StageCloudFeatureConfigurationsAsync(
                    &v19,
                    &v15);
            result = winrt::impl::wait_for_completed<winrt::Windows::Foundation::IAsyncOperation<bool>>(
                       v13,
                       (unsigned int)(1000 * *(_DWORD *)a3));
          }
          else
          {
            LOBYTE(v21[0]) = 0;
            v20 = v14;
            result = winrt::WindowsUdk::Management::Update::FeatureStagingManager::StageCloudFeatureConfigurationsAsync(
                       &v23,
                       &v20);
            v8 = 12;
          }
          if ( (v8 & 8) != 0 )
          {
            v8 &= ~8u;
            if ( v23 )
              result = winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v23);
          }
          if ( (v8 & 4) != 0 )
          {
            v8 &= ~4u;
            if ( LOBYTE(v21[0]) )
            {
              result = (__int64)v20;
            }
            else
            {
              result = 0;
              v20 = 0;
            }
            if ( result )
              result = winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v20);
          }
          if ( (v8 & 2) != 0 )
          {
            v8 &= ~2u;
            if ( v19 )
              result = winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v19);
          }
          if ( (v8 & 1) == 0 )
            goto LABEL_40;
        }
        else
        {
          LOBYTE(v16) = 0;
          v15 = v14;
          winrt::WindowsUdk::Management::Update::FeatureStagingManager::StageCloudFeatureConfigurationsAsync(&v19, &v15);
          if ( v19 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v19);
        }
        if ( (_BYTE)v16 )
        {
          result = (__int64)v15;
        }
        else
        {
          result = 0;
          v15 = 0;
        }
        if ( result )
          result = winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v15);
LABEL_40:
        if ( v14 )
          result = winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v14);
      }
    }
  }
  catch ( ... )
  {
    return wil::details::in1diag3::Log_CaughtException(
             retaddr,
             (void *)0x12D,
             (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Settings.cpp",
             v6);
  }
  return result;
}

```

## disassembly

```asm
0x180040f10  mov     r11, rsp
0x180040f13  mov     [r11+8], rbx
0x180040f17  mov     [r11+10h], rsi
0x180040f1b  mov     [r11+18h], r14
0x180040f1f  push    r15
0x180040f21  sub     rsp, 0A0h
0x180040f28  mov     rax, cs:__security_cookie
0x180040f2f  xor     rax, rsp
0x180040f32  mov     [rsp+0A8h+var_10], rax
0x180040f3a  mov     r14, r8
0x180040f3d  mov     rsi, rdx
0x180040f40  xor     r15d, r15d
0x180040f43  mov     [r11-78h], r15d
0x180040f47  call    Windows__UdkVersionChecker___anonymous_namespace___IsUdkSupported
0x180040f4c  test    al, al
0x180040f4e  jz      loc_1800411D1
0x180040f54  lea     rdx, ?ManagementUpdateContractName@Update@Management@WindowsUdk@winrt@@3QB_WB; "WindowsUdk.Management.Update.Management"...
0x180040f5b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180040f5f  inc     rcx
0x180040f62  cmp     [rdx+rcx*2], r15w
0x180040f67  jnz     short loc_180040F5F
0x180040f69  test    ecx, ecx
0x180040f6b  jnz     short loc_180040F74
0x180040f6d  mov     [rsp+0A8h+var_68], r15
0x180040f72  jmp     short loc_180040F9C
0x180040f74  mov     eax, ecx
0x180040f76  cmp     [rdx+rax*2], r15w
0x180040f7b  jnz     loc_1800411D3
0x180040f81  mov     [rsp+0A8h+var_60], 1
0x180040f89  mov     [rsp+0A8h+var_5C], ecx
0x180040f8d  mov     [rsp+0A8h+var_50], rdx
0x180040f92  lea     rax, [rsp+0A8h+var_60]
0x180040f97  mov     [rsp+0A8h+var_68], rax
0x180040f9c  mov     ebx, 3
0x180040fa1  mov     edx, ebx; unsigned __int16
0x180040fa3  lea     rcx, [rsp+0A8h+var_68]; struct winrt::param::hstring *
0x180040fa8  call    ?IsApiContractPresent@ApiInformation@Metadata@Foundation@WindowsUdk@winrt@@SA@AEBUhstring@param@5@G@Z; winrt::WindowsUdk::Foundation::Metadata::ApiInformation::IsApiContractPresent(winrt::param::hstring const &,ushort)
0x180040fad  test    al, al
0x180040faf  jz      loc_1800411D1
0x180040fb5  lea     rcx, [rsp+0A8h+var_70]
0x180040fba  call    ??$single_threaded_map@Uhstring@winrt@@U12@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@U12@@std@@@4@@winrt@@YA?AU?$IMap@Uhstring@winrt@@U12@@Collections@Foundation@Windows@0@XZ; winrt::single_threaded_map<winrt::hstring,winrt::hstring,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::hstring>>>(void)
0x180040fbf  nop
0x180040fc0  mov     rdx, [rsi]
0x180040fc3  mov     ecx, [rsi+8]
0x180040fc6  test    ecx, ecx
0x180040fc8  jnz     short loc_180040FD4
0x180040fca  mov     [rsp+0A8h+var_68], r15
0x180040fcf  mov     r8, r15
0x180040fd2  jmp     short loc_180040FFF
0x180040fd4  cmp     [rdx+rcx*2], r15w
0x180040fd9  jnz     loc_1800411D9
0x180040fdf  mov     [rsp+0A8h+var_60], 1
0x180040fe7  mov     [rsp+0A8h+var_5C], ecx
0x180040feb  mov     [rsp+0A8h+var_50], rdx
0x180040ff0  lea     rax, [rsp+0A8h+var_60]
0x180040ff5  mov     [rsp+0A8h+var_68], rax
0x180040ffa  lea     r8, [rsp+0A8h+var_60]
0x180040fff  mov     [rsp+0A8h+var_38], 1
0x180041007  mov     [rsp+0A8h+var_34], 9
0x18004100f  lea     rax, aOsversion; "OSVersion"
0x180041016  mov     [rsp+0A8h+var_28], rax
0x18004101e  lea     rax, [rsp+0A8h+var_38]
0x180041023  mov     [rsp+0A8h+var_40], rax
0x180041028  mov     [rsp+0A8h+var_18], r15b
0x180041030  mov     rcx, [rsp+0A8h+var_70]
0x180041035  mov     rax, [rcx]
0x180041038  lea     r9, [rsp+0A8h+var_18]
0x180041040  lea     rdx, [rsp+0A8h+var_38]
0x180041045  mov     rax, [rax+50h]
0x180041049  call    _guard_dispatch_icall
0x18004104e  test    eax, eax
0x180041050  js      loc_1800411DF
0x180041056  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_PackageContainment_53093331@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_PackageContainment_53093331@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_PackageContainment_53093331> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_PackageContainment_53093331>::GetImpl(void)'::`2'::impl
0x18004105d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_PackageContainment_53093331@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_PackageContainment_53093331>::__private_IsEnabled(void)
0x180041062  test    al, al
0x180041064  mov     rax, [rsp+0A8h+var_70]
0x180041069  jz      loc_180041144
0x18004106f  cmp     [r14+8], r15b
0x180041073  jz      short loc_1800410AC
0x180041075  mov     byte ptr [rsp+0A8h+var_60], r15b
0x18004107a  mov     [rsp+0A8h+var_68], rax
0x18004107f  mov     [rsp+0A8h+var_78], 1
0x180041087  lea     rdx, [rsp+0A8h+var_68]
0x18004108c  lea     rcx, [rsp+0A8h+var_48]
0x180041091  call    ?StageCloudFeatureConfigurationsAsync@FeatureStagingManager@Update@Management@WindowsUdk@winrt@@SA@AEBU?$map@Uhstring@winrt@@U12@@param@5@@Z; winrt::WindowsUdk::Management::Update::FeatureStagingManager::StageCloudFeatureConfigurationsAsync(winrt::param::map<winrt::hstring,winrt::hstring> const &)
0x180041096  nop
0x180041097  mov     [rsp+0A8h+var_78], ebx
0x18004109b  imul    edx, [r14], 3E8h
0x1800410a2  mov     rcx, rax
0x1800410a5  call    ??$wait_for_completed@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@_N@Foundation@Windows@1@I@Z
0x1800410aa  jmp     short loc_1800410D5
0x1800410ac  mov     byte ptr [rsp+0A8h+var_38], r15b
0x1800410b1  mov     [rsp+0A8h+var_40], rax
0x1800410b6  mov     [rsp+0A8h+var_78], 4
0x1800410be  lea     rdx, [rsp+0A8h+var_40]
0x1800410c3  lea     rcx, [rsp+0A8h+var_20]
0x1800410cb  call    ?StageCloudFeatureConfigurationsAsync@FeatureStagingManager@Update@Management@WindowsUdk@winrt@@SA@AEBU?$map@Uhstring@winrt@@U12@@param@5@@Z; winrt::WindowsUdk::Management::Update::FeatureStagingManager::StageCloudFeatureConfigurationsAsync(winrt::param::map<winrt::hstring,winrt::hstring> const &)
0x1800410d0  mov     ebx, 0Ch
0x1800410d5  test    bl, 8
0x1800410d8  jz      short loc_1800410F5
0x1800410da  and     ebx, 0FFFFFFF7h
0x1800410dd  cmp     [rsp+0A8h+var_20], r15
0x1800410e5  jz      short loc_1800410F5
0x1800410e7  lea     rcx, [rsp+0A8h+var_20]
0x1800410ef  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800410f4  nop
0x1800410f5  test    bl, 4
0x1800410f8  jz      short loc_180041123
0x1800410fa  and     ebx, 0FFFFFFFBh
0x1800410fd  cmp     byte ptr [rsp+0A8h+var_38], r15b
0x180041102  jnz     short loc_18004110E
0x180041104  mov     rax, r15
0x180041107  mov     [rsp+0A8h+var_40], rax
0x18004110c  jmp     short loc_180041113
0x18004110e  mov     rax, [rsp+0A8h+var_40]
0x180041113  test    rax, rax
0x180041116  jz      short loc_180041123
0x180041118  lea     rcx, [rsp+0A8h+var_40]
0x18004111d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180041122  nop
0x180041123  test    bl, 2
0x180041126  jz      short loc_18004113D
0x180041128  and     ebx, 0FFFFFFFDh
0x18004112b  cmp     [rsp+0A8h+var_48], r15
0x180041130  jz      short loc_18004113D
0x180041132  lea     rcx, [rsp+0A8h+var_48]
0x180041137  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18004113c  nop
0x18004113d  test    bl, 1
0x180041140  jz      short loc_180041195
0x180041142  jmp     short loc_18004116F
0x180041144  mov     byte ptr [rsp+0A8h+var_60], r15b
0x180041149  mov     [rsp+0A8h+var_68], rax
0x18004114e  lea     rdx, [rsp+0A8h+var_68]
0x180041153  lea     rcx, [rsp+0A8h+var_48]
0x180041158  call    ?StageCloudFeatureConfigurationsAsync@FeatureStagingManager@Update@Management@WindowsUdk@winrt@@SA@AEBU?$map@Uhstring@winrt@@U12@@param@5@@Z; winrt::WindowsUdk::Management::Update::FeatureStagingManager::StageCloudFeatureConfigurationsAsync(winrt::param::map<winrt::hstring,winrt::hstring> const &)
0x18004115d  cmp     [rsp+0A8h+var_48], r15
0x180041162  jz      short loc_18004116F
0x180041164  lea     rcx, [rsp+0A8h+var_48]
0x180041169  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18004116e  nop
0x18004116f  cmp     byte ptr [rsp+0A8h+var_60], r15b
0x180041174  jnz     short loc_180041180
0x180041176  mov     rax, r15
0x180041179  mov     [rsp+0A8h+var_68], rax
0x18004117e  jmp     short loc_180041185
0x180041180  mov     rax, [rsp+0A8h+var_68]
0x180041185  test    rax, rax
0x180041188  jz      short loc_180041195
0x18004118a  lea     rcx, [rsp+0A8h+var_68]
0x18004118f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180041194  nop
0x180041195  cmp     [rsp+0A8h+var_70], r15
0x18004119a  jz      short loc_1800411A7
0x18004119c  lea     rcx, [rsp+0A8h+var_70]
0x1800411a1  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800411a6  nop
0x1800411a7  mov     rcx, [rsp+0A8h+var_10]
0x1800411af  xor     rcx, rsp; StackCookie
0x1800411b2  call    __security_check_cookie
0x1800411b7  lea     r11, [rsp+0A8h+var_8]
0x1800411bf  mov     rbx, [r11+10h]
0x1800411c3  mov     rsi, [r11+18h]
0x1800411c7  mov     r14, [r11+20h]
0x1800411cb  mov     rsp, r11
0x1800411ce  pop     r15
0x1800411d0  retn
0x1800411d1  jmp     short loc_1800411A7
0x1800411d3  call    abort
0x1800411d9  call    abort
0x1800411df  mov     ecx, eax
0x1800411e1  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
```
