# Microsoft::Windows::Autopilot::HardwareInfo::GetTpmEkPub(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001b290`
- end: `0x18001b64d`
- name: `?GetTpmEkPub@HardwareInfo@Autopilot@Windows@Microsoft@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `957`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180009957`
- `0x1800105f4`
- `0x1800182f4`
- `0x180018cd0`
- `0x18001b290`
- `0x18001b654`
- `0x18001cc40`
- `0x18001ccc4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b3f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b426`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b562`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b3f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b426`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b562`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b408`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b575`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b408`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b575`
- `ncrypt!NCryptOpenStorageProvider` at `0x18001b2d3`
- `ncrypt!NCryptOpenStorageProvider` at `0x18001b2d3`
- `ncrypt!NCryptGetProperty` at `0x18001b304`
- `ncrypt!NCryptGetProperty` at `0x18001b38c`
- `ncrypt!NCryptGetProperty` at `0x18001b304`
- `ncrypt!NCryptGetProperty` at `0x18001b38c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b319`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b319`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b3dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b3e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b400`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b4d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b4dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b56d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b5ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b623`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b3dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b3e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b400`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b4d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b4dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b56d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b5ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b623`
- `DMCmnUtils!EncodeBase64W` at `0x18001b41c`
- `DMCmnUtils!EncodeBase64W` at `0x18001b58c`
- `DMCmnUtils!EncodeBase64W` at `0x18001b41c`
- `DMCmnUtils!EncodeBase64W` at `0x18001b58c`

## string_xrefs

- `0x18001b351`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001b3c1`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001b4b7`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001b5a0`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::Windows::Autopilot::HardwareInfo::GetTpmEkPub(void **a1)
{
  int Property; // edi
  unsigned int v3; // eax
  __int64 v4; // rbx
  BYTE *v5; // rax
  BYTE *v6; // r15
  BYTE *i; // rcx
  unsigned int v8; // ebx
  unsigned __int64 v9; // r14
  __int64 v10; // r8
  HLOCAL v11; // r12
  DWORD LastError; // ebx
  void *v13; // r13
  bool v14; // sf
  unsigned __int64 v16; // rax
  __int64 v17; // rcx
  unsigned __int64 v18; // r14
  unsigned __int16 *v19; // rdi
  __int64 v20; // r9
  __int64 v21; // rdx
  DWORD v22; // ebx
  int v23; // eax
  __int64 v24; // r8
  unsigned __int16 *v25; // r9
  void *v26; // rdi
  int pcbResult; // [rsp+20h] [rbp-40h]
  NCRYPT_PROV_HANDLE phProvider[2]; // [rsp+30h] [rbp-30h] BYREF
  __int128 v29; // [rsp+40h] [rbp-20h] BYREF
  __int64 v30; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  unsigned __int16 *cbOutput; // [rsp+A8h] [rbp+48h] BYREF
  DWORD v33; // [rsp+B0h] [rbp+50h] BYREF
  HLOCAL hMem; // [rsp+B8h] [rbp+58h] BYREF

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
  {
    phProvider[0] = 0;
    Property = NCryptOpenStorageProvider(phProvider, L"Microsoft Platform Crypto Provider", 0);
    v3 = 0;
    LODWORD(cbOutput) = 0;
    if ( Property >= 0 )
    {
      Property = NCryptGetProperty(phProvider[0], L"PCP_EKPUB", 0, 0, (DWORD *)&cbOutput, 0);
      v3 = (unsigned int)cbOutput;
    }
    v33 = 0;
    v4 = v3;
    v5 = (BYTE *)LocalAlloc(0, v3);
    v6 = v5;
    phProvider[1] = (NCRYPT_PROV_HANDLE)v5;
    if ( v5 )
    {
      for ( i = &v5[v4]; v5 != i; ++v5 )
        *v5 = 0;
    }
    if ( !v6 )
    {
      v8 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x146,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
        (const char *)0x8007000ELL,
        pcbResult);
      return v8;
    }
    if ( Property >= 0 )
      Property = NCryptGetProperty(phProvider[0], L"PCP_EKPUB", v6, (DWORD)cbOutput, &v33, 0);
    v9 = -1;
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &hMem,
      &dword_1800360F4,
      -1);
    v11 = hMem;
    if ( !hMem )
    {
      v8 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x14D,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
        (const char *)0x8007000ELL,
        pcbResult);
      if ( hMem )
        LocalFree(hMem);
      LocalFree(v6);
      return v8;
    }
    if ( Property >= 0 )
    {
      LastError = GetLastError();
      LocalFree(v11);
      SetLastError(LastError);
      hMem = 0;
      if ( (int)EncodeBase64W(v6, (_DWORD)cbOutput, (unsigned __int16 **)&hMem) >= 0 )
      {
        v11 = hMem;
        do
LABEL_22:
          ++v9;
        while ( *((_WORD *)v11 + v9) );
        if ( v9 > (unsigned __int64)a1[3] )
        {
          std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
            a1,
            v9,
            v10,
            v11);
        }
        else
        {
          if ( (unsigned __int64)a1[3] <= 7 )
            v13 = a1;
          else
            v13 = *a1;
          a1[2] = (void *)v9;
          memmove_0(v13, v11, 2 * v9);
          *((_WORD *)v13 + v9) = 0;
        }
        v14 = Property < 0;
        if ( Property > 0 )
        {
          Property = (unsigned __int16)Property | 0x80070000;
          v14 = Property < 0;
        }
        if ( v14 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x15E,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
            (const char *)(unsigned int)Property,
            pcbResult);
        if ( hMem )
          LocalFree(hMem);
        LocalFree(v6);
        return (unsigned int)Property;
      }
      Property = GetLastError();
      v11 = hMem;
    }
    if ( Property == -2146893776 || Property == -2146893807 || Property == -2146893771 )
      Property = 0;
    goto LABEL_22;
  }
  v29 = 0;
  v30 = 0;
  v16 = (unsigned int)Microsoft::Windows::Autopilot::HardwareInfo::GetTpmEkPubByteData((PBYTE *)&v29) + 2146893807;
  if ( (unsigned int)v16 <= 0x24 )
  {
    v17 = 0x1080000001LL;
    if ( _bittest64(&v17, v16) )
    {
      a1[2] = 0;
      if ( (unsigned __int64)a1[3] > 7 )
        a1 = (void **)*a1;
      *(_WORD *)a1 = 0;
      v8 = 0;
LABEL_48:
      std::vector<unsigned char>::_Tidy(&v29);
      return v8;
    }
  }
  v18 = -1;
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &cbOutput,
    &dword_1800360F4,
    -1);
  v19 = cbOutput;
  if ( !cbOutput )
  {
    v8 = -2147024882;
    v20 = 2147942414LL;
    v21 = 306;
    goto LABEL_46;
  }
  v22 = GetLastError();
  LocalFree(v19);
  SetLastError(v22);
  cbOutput = 0;
  v23 = EncodeBase64W((const unsigned __int8 *)v29, DWORD2(v29) - v29, &cbOutput);
  v8 = v23;
  if ( v23 < 0 )
  {
    v20 = (unsigned int)v23;
    v21 = 308;
LABEL_46:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
      (const char *)v20,
      pcbResult);
    if ( cbOutput )
      LocalFree(cbOutput);
    goto LABEL_48;
  }
  v25 = cbOutput;
  do
    ++v18;
  while ( cbOutput[v18] );
  if ( v18 > (unsigned __int64)a1[3] )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
      a1,
      v18,
      v24,
      cbOutput);
  }
  else
  {
    if ( (unsigned __int64)a1[3] <= 7 )
      v26 = a1;
    else
      v26 = *a1;
    a1[2] = (void *)v18;
    memmove_0(v26, v25, 2 * v18);
    *((_WORD *)v26 + v18) = 0;
  }
  if ( cbOutput )
    LocalFree(cbOutput);
  std::vector<unsigned char>::_Tidy(&v29);
  return 0;
}

```

## disassembly

```asm
0x18001b290  mov     [rsp-38h+arg_0], rbx
0x18001b295  push    rbp
0x18001b296  push    rsi
0x18001b297  push    rdi
0x18001b298  push    r12
0x18001b29a  push    r13
0x18001b29c  push    r14
0x18001b29e  push    r15
0x18001b2a0  mov     rbp, rsp
0x18001b2a3  sub     rsp, 60h
0x18001b2a7  mov     rsi, rcx
0x18001b2aa  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x18001b2b1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x18001b2b6  xor     r13d, r13d
0x18001b2b9  test    al, al
0x18001b2bb  jnz     loc_18001B4E9
0x18001b2c1  mov     [rbp+phProvider], r13
0x18001b2c5  xor     r8d, r8d; dwFlags
0x18001b2c8  lea     rdx, pszProviderName; "Microsoft Platform Crypto Provider"
0x18001b2cf  lea     rcx, [rbp+phProvider]; phProvider
0x18001b2d3  call    cs:__imp_NCryptOpenStorageProvider
0x18001b2d9  mov     edi, eax
0x18001b2db  mov     eax, r13d
0x18001b2de  mov     dword ptr [rbp+cbOutput], eax
0x18001b2e1  test    edi, edi
0x18001b2e3  js      short loc_18001B30F
0x18001b2e5  mov     [rsp+60h+dwFlags], r13d; dwFlags
0x18001b2ea  lea     rax, [rbp+cbOutput]
0x18001b2ee  mov     [rsp+60h+pcbResult], rax; int
0x18001b2f3  xor     r9d, r9d; cbOutput
0x18001b2f6  xor     r8d, r8d; pbOutput
0x18001b2f9  lea     rdx, pszProperty; "PCP_EKPUB"
0x18001b300  mov     rcx, [rbp+phProvider]; hObject
0x18001b304  call    cs:__imp_NCryptGetProperty
0x18001b30a  mov     edi, eax
0x18001b30c  mov     eax, dword ptr [rbp+cbOutput]
0x18001b30f  mov     [rbp+arg_10], r13d
0x18001b313  mov     ebx, eax
0x18001b315  mov     edx, eax; uBytes
0x18001b317  xor     ecx, ecx; uFlags
0x18001b319  call    cs:__imp_LocalAlloc
0x18001b31f  mov     r15, rax
0x18001b322  mov     [rbp+var_28], rax
0x18001b326  test    rax, rax
0x18001b329  jz      short loc_18001B340
0x18001b32b  lea     rcx, [rbx+rax]
0x18001b32f  cmp     rax, rcx
0x18001b332  jz      short loc_18001B340
0x18001b334  xor     edx, edx
0x18001b336  mov     [rax], dl
0x18001b338  inc     rax
0x18001b33b  cmp     rax, rcx
0x18001b33e  jnz     short loc_18001B334
0x18001b340  test    r15, r15
0x18001b343  jnz     short loc_18001B368
0x18001b345  mov     rcx, [rbp+38h]; this
0x18001b349  mov     ebx, 8007000Eh
0x18001b34e  mov     r9d, ebx; char *
0x18001b351  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001b358  mov     edx, 146h; void *
0x18001b35d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b362  nop
0x18001b363  jmp     loc_18001B5CA
0x18001b368  test    edi, edi
0x18001b36a  js      short loc_18001B394
0x18001b36c  mov     [rsp+60h+dwFlags], r13d; dwFlags
0x18001b371  lea     rax, [rbp+arg_10]
0x18001b375  mov     [rsp+60h+pcbResult], rax; int
0x18001b37a  mov     r9d, dword ptr [rbp+cbOutput]; cbOutput
0x18001b37e  mov     r8, r15; pbOutput
0x18001b381  lea     rdx, pszProperty; "PCP_EKPUB"
0x18001b388  mov     rcx, [rbp+phProvider]; hObject
0x18001b38c  call    cs:__imp_NCryptGetProperty
0x18001b392  mov     edi, eax
0x18001b394  or      r14, 0FFFFFFFFFFFFFFFFh
0x18001b398  mov     r8, r14
0x18001b39b  lea     rdx, dword_1800360F4
0x18001b3a2  lea     rcx, [rbp+hMem]
0x18001b3a6  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18001b3ab  nop
0x18001b3ac  mov     r12, [rbp+hMem]
0x18001b3b0  test    r12, r12
0x18001b3b3  jnz     short loc_18001B3F1
0x18001b3b5  mov     rcx, [rbp+38h]; this
0x18001b3b9  mov     ebx, 8007000Eh
0x18001b3be  mov     r9d, ebx; char *
0x18001b3c1  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001b3c8  mov     edx, 14Dh; void *
0x18001b3cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b3d2  nop
0x18001b3d3  mov     rcx, [rbp+hMem]; hMem
0x18001b3d7  test    rcx, rcx
0x18001b3da  jz      short loc_18001B3E3
0x18001b3dc  call    cs:__imp_LocalFree
0x18001b3e2  nop
0x18001b3e3  mov     rcx, r15; hMem
0x18001b3e6  call    cs:__imp_LocalFree
0x18001b3ec  jmp     loc_18001B5CA
0x18001b3f1  test    edi, edi
0x18001b3f3  js      short loc_18001B432
0x18001b3f5  call    cs:__imp_GetLastError
0x18001b3fb  mov     ebx, eax
0x18001b3fd  mov     rcx, r12; hMem
0x18001b400  call    cs:__imp_LocalFree
0x18001b406  mov     ecx, ebx; dwErrCode
0x18001b408  call    cs:__imp_SetLastError
0x18001b40e  mov     [rbp+hMem], r13
0x18001b412  lea     r8, [rbp+hMem]
0x18001b416  mov     edx, dword ptr [rbp+cbOutput]
0x18001b419  mov     rcx, r15
0x18001b41c  call    cs:__imp_?EncodeBase64W@@YAJPEBEHPEAPEAG@Z; EncodeBase64W(uchar const *,int,ushort * *)
0x18001b422  test    eax, eax
0x18001b424  jns     short loc_18001B469
0x18001b426  call    cs:__imp_GetLastError
0x18001b42c  mov     edi, eax
0x18001b42e  mov     r12, [rbp+hMem]
0x18001b432  cmp     edi, 80090030h
0x18001b438  jz      short loc_18001B44A
0x18001b43a  cmp     edi, 80090011h
0x18001b440  jz      short loc_18001B44A
0x18001b442  cmp     edi, 80090035h
0x18001b448  jnz     short loc_18001B44D
0x18001b44a  mov     edi, r13d
0x18001b44d  inc     r14
0x18001b450  cmp     [r12+r14*2], r13w
0x18001b455  jnz     short loc_18001B44D
0x18001b457  cmp     r14, [rsi+18h]
0x18001b45b  ja      short loc_18001B491
0x18001b45d  cmp     qword ptr [rsi+18h], 7
0x18001b462  jbe     short loc_18001B46F
0x18001b464  mov     r13, [rsi]
0x18001b467  jmp     short loc_18001B472
0x18001b469  mov     r12, [rbp+hMem]
0x18001b46d  jmp     short loc_18001B44D
0x18001b46f  mov     r13, rsi
0x18001b472  mov     [rsi+10h], r14
0x18001b476  lea     rbx, [r14+r14]
0x18001b47a  mov     r8, rbx; Size
0x18001b47d  mov     rdx, r12; Src
0x18001b480  mov     rcx, r13; void *
0x18001b483  call    memmove_0
0x18001b488  xor     eax, eax
0x18001b48a  mov     [rbx+r13], ax
0x18001b48f  jmp     short loc_18001B49F
0x18001b491  mov     r9, r12
0x18001b494  mov     rdx, r14
0x18001b497  mov     rcx, rsi
0x18001b49a  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18001b49f  test    edi, edi
0x18001b4a1  jle     short loc_18001B4AE
0x18001b4a3  movzx   edi, di
0x18001b4a6  or      edi, 80070000h
0x18001b4ac  test    edi, edi
0x18001b4ae  jns     short loc_18001B4C9
0x18001b4b0  mov     rcx, [rbp+38h]; this
0x18001b4b4  mov     r9d, edi; char *
0x18001b4b7  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001b4be  mov     edx, 15Eh; void *
0x18001b4c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b4c8  nop
0x18001b4c9  mov     rcx, [rbp+hMem]; hMem
0x18001b4cd  test    rcx, rcx
0x18001b4d0  jz      short loc_18001B4D9
0x18001b4d2  call    cs:__imp_LocalFree
0x18001b4d8  nop
0x18001b4d9  mov     rcx, r15; hMem
0x18001b4dc  call    cs:__imp_LocalFree
0x18001b4e2  mov     eax, edi
0x18001b4e4  jmp     loc_18001B635
0x18001b4e9  xorps   xmm0, xmm0
0x18001b4ec  movdqu  [rbp+var_20], xmm0
0x18001b4f1  mov     [rbp+var_10], r13
0x18001b4f5  lea     rcx, [rbp+var_20]
0x18001b4f9  call    ?GetTpmEkPubByteData@HardwareInfo@Autopilot@Windows@Microsoft@@SAJAEAV?$vector@EV?$allocator@E@std@@@std@@@Z; Microsoft::Windows::Autopilot::HardwareInfo::GetTpmEkPubByteData(std::vector<uchar> &)
0x18001b4fe  add     eax, 7FF6FFEFh
0x18001b503  cmp     eax, 24h ; '$'
0x18001b506  ja      short loc_18001B532
0x18001b508  mov     rcx, 1080000001h
0x18001b512  bt      rcx, rax
0x18001b516  jnb     short loc_18001B532
0x18001b518  mov     [rsi+10h], r13
0x18001b51c  cmp     qword ptr [rsi+18h], 7
0x18001b521  jbe     short loc_18001B526
0x18001b523  mov     rsi, [rsi]
0x18001b526  mov     [rsi], r13w
0x18001b52a  mov     ebx, r13d
0x18001b52d  jmp     loc_18001B5C1
0x18001b532  or      r14, 0FFFFFFFFFFFFFFFFh
0x18001b536  mov     r8, r14
0x18001b539  lea     rdx, dword_1800360F4
0x18001b540  lea     rcx, [rbp+cbOutput]
0x18001b544  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18001b549  nop
0x18001b54a  mov     rdi, [rbp+cbOutput]
0x18001b54e  test    rdi, rdi
0x18001b551  jnz     short loc_18001B562
0x18001b553  mov     ebx, 8007000Eh
0x18001b558  mov     r9d, ebx
0x18001b55b  mov     edx, 132h
0x18001b560  jmp     short loc_18001B5A0
0x18001b562  call    cs:__imp_GetLastError
0x18001b568  mov     ebx, eax
0x18001b56a  mov     rcx, rdi; hMem
0x18001b56d  call    cs:__imp_LocalFree
0x18001b573  mov     ecx, ebx; dwErrCode
0x18001b575  call    cs:__imp_SetLastError
0x18001b57b  mov     [rbp+cbOutput], r13
0x18001b57f  mov     rcx, qword ptr [rbp+var_20]
0x18001b583  mov     edx, dword ptr [rbp+var_20+8]
0x18001b586  sub     edx, ecx
0x18001b588  lea     r8, [rbp+cbOutput]
0x18001b58c  call    cs:__imp_?EncodeBase64W@@YAJPEBEHPEAPEAG@Z; EncodeBase64W(uchar const *,int,ushort * *)
0x18001b592  mov     ebx, eax
0x18001b594  test    eax, eax
0x18001b596  jns     short loc_18001B5CE
0x18001b598  mov     r9d, eax; char *
0x18001b59b  mov     edx, 134h; void *
0x18001b5a0  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001b5a7  mov     rcx, [rbp+38h]; this
0x18001b5ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b5b0  nop
0x18001b5b1  mov     rcx, [rbp+cbOutput]; hMem
0x18001b5b5  test    rcx, rcx
0x18001b5b8  jz      short loc_18001B5C1
0x18001b5ba  call    cs:__imp_LocalFree
0x18001b5c0  nop
0x18001b5c1  lea     rcx, [rbp+var_20]
0x18001b5c5  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18001b5ca  mov     eax, ebx
0x18001b5cc  jmp     short loc_18001B635
0x18001b5ce  mov     r9, [rbp+cbOutput]
0x18001b5d2  inc     r14
0x18001b5d5  cmp     [r9+r14*2], r13w
0x18001b5da  jnz     short loc_18001B5D2
0x18001b5dc  cmp     r14, [rsi+18h]
0x18001b5e0  ja      short loc_18001B60E
0x18001b5e2  cmp     qword ptr [rsi+18h], 7
0x18001b5e7  jbe     short loc_18001B5EE
0x18001b5e9  mov     rdi, [rsi]
0x18001b5ec  jmp     short loc_18001B5F1
0x18001b5ee  mov     rdi, rsi
0x18001b5f1  mov     [rsi+10h], r14
0x18001b5f5  lea     rbx, [r14+r14]
0x18001b5f9  mov     r8, rbx; Size
0x18001b5fc  mov     rdx, r9; Src
0x18001b5ff  mov     rcx, rdi; void *
0x18001b602  call    memmove_0
0x18001b607  mov     [rbx+rdi], r13w
0x18001b60c  jmp     short loc_18001B61A
0x18001b60e  mov     rdx, r14
0x18001b611  mov     rcx, rsi
0x18001b614  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18001b619  nop
0x18001b61a  mov     rcx, [rbp+cbOutput]; hMem
0x18001b61e  test    rcx, rcx
0x18001b621  jz      short loc_18001B62A
0x18001b623  call    cs:__imp_LocalFree
0x18001b629  nop
0x18001b62a  lea     rcx, [rbp+var_20]
0x18001b62e  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18001b633  xor     eax, eax
0x18001b635  mov     rbx, [rsp+60h+arg_0]
0x18001b63d  add     rsp, 60h
0x18001b641  pop     r15
0x18001b643  pop     r14
0x18001b645  pop     r13
0x18001b647  pop     r12
0x18001b649  pop     rdi
0x18001b64a  pop     rsi
0x18001b64b  pop     rbp
0x18001b64c  retn
```
