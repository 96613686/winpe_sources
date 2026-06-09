# Microsoft::Windows::Autopilot::HardwareInfo::GetTpmEkPub(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001b940`
- end: `0x18001bd70`
- name: `?GetTpmEkPub@HardwareInfo@Autopilot@Windows@Microsoft@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1072`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800098e7`
- `0x180010764`
- `0x180018854`
- `0x1800192a4`
- `0x18001b940`
- `0x18001bd78`
- `0x18001d3b8`
- `0x18001d444`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bac9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bb12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bc60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bac9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bb12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bc60`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bae8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bc7f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bae8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bc7f`
- `ncrypt!NCryptOpenStorageProvider` at `0x18001b983`
- `ncrypt!NCryptOpenStorageProvider` at `0x18001b983`
- `ncrypt!NCryptGetProperty` at `0x18001b9ba`
- `ncrypt!NCryptGetProperty` at `0x18001ba4e`
- `ncrypt!NCryptGetProperty` at `0x18001b9ba`
- `ncrypt!NCryptGetProperty` at `0x18001ba4e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b9d5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b9d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001baa4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bab4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bada`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bbc4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bbd4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bc71`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bcd0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bd3f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001baa4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bab4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bada`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bbc4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bbd4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bc71`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bcd0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bd3f`
- `DMCmnUtils!EncodeBase64W` at `0x18001bb02`
- `DMCmnUtils!EncodeBase64W` at `0x18001bc9c`
- `DMCmnUtils!EncodeBase64W` at `0x18001bb02`
- `DMCmnUtils!EncodeBase64W` at `0x18001bc9c`

## string_xrefs

- `0x18001ba13`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001ba89`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001bba9`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001bcb6`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::HardwareInfo::GetTpmEkPub(char *a1)
{
  int Property; // edi
  unsigned int v3; // eax
  __int64 v4; // rbx
  BYTE *v5; // rax
  const char *v6; // r9
  BYTE *v7; // r15
  BYTE *i; // rcx
  unsigned int v9; // ebx
  unsigned __int64 v10; // r14
  __int64 v11; // r8
  HLOCAL v12; // r12
  DWORD LastError; // ebx
  char *v14; // r13
  bool v15; // sf
  unsigned __int64 v17; // rax
  const char *v18; // r9
  __int64 v19; // rcx
  unsigned __int64 v20; // r14
  unsigned __int16 *v21; // rdi
  __int64 v22; // r9
  __int64 v23; // rdx
  DWORD v24; // ebx
  int v25; // eax
  __int64 v26; // r8
  unsigned __int16 *v27; // r9
  char *v28; // rdi
  int pcbResult; // [rsp+20h] [rbp-40h]
  NCRYPT_PROV_HANDLE phProvider[2]; // [rsp+30h] [rbp-30h] BYREF
  __int128 v31; // [rsp+40h] [rbp-20h] BYREF
  __int64 v32; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  unsigned __int16 *cbOutput; // [rsp+A8h] [rbp+48h] BYREF
  DWORD v35; // [rsp+B0h] [rbp+50h] BYREF
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
    v35 = 0;
    v4 = v3;
    v5 = (BYTE *)LocalAlloc(0, v3);
    v7 = v5;
    phProvider[1] = (NCRYPT_PROV_HANDLE)v5;
    if ( v5 )
    {
      for ( i = &v5[v4]; v5 != i; ++v5 )
        *v5 = 0;
    }
    if ( !v7 )
    {
      v9 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x146,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
        (const char *)0x8007000ELL,
        pcbResult);
      return v9;
    }
    if ( Property >= 0 )
      Property = NCryptGetProperty(phProvider[0], L"PCP_EKPUB", v7, (DWORD)cbOutput, &v35, 0);
    v10 = -1;
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &hMem,
      (char *)&dword_180037114,
      0xFFFFFFFFFFFFFFFFuLL,
      v6);
    v12 = hMem;
    if ( !hMem )
    {
      v9 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x14D,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
        (const char *)0x8007000ELL,
        pcbResult);
      if ( hMem )
        LocalFree(hMem);
      LocalFree(v7);
      return v9;
    }
    if ( Property >= 0 )
    {
      LastError = GetLastError();
      LocalFree(v12);
      SetLastError(LastError);
      hMem = 0;
      if ( (int)EncodeBase64W(v7, (_DWORD)cbOutput, (unsigned __int16 **)&hMem) >= 0 )
      {
        v12 = hMem;
        do
LABEL_22:
          ++v10;
        while ( *((_WORD *)v12 + v10) );
        if ( v10 > *((_QWORD *)a1 + 3) )
        {
          std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
            (char **)a1,
            v10,
            v11,
            v12);
        }
        else
        {
          if ( *((_QWORD *)a1 + 3) <= 7u )
            v14 = a1;
          else
            v14 = *(char **)a1;
          *((_QWORD *)a1 + 2) = v10;
          memmove_0(v14, v12, 2 * v10);
          *(_WORD *)&v14[2 * v10] = 0;
        }
        v15 = Property < 0;
        if ( Property > 0 )
        {
          Property = (unsigned __int16)Property | 0x80070000;
          v15 = Property < 0;
        }
        if ( v15 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x15E,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
            (const char *)(unsigned int)Property,
            pcbResult);
        if ( hMem )
          LocalFree(hMem);
        LocalFree(v7);
        return (unsigned int)Property;
      }
      Property = GetLastError();
      v12 = hMem;
    }
    if ( Property == -2146893776 || Property == -2146893807 || Property == -2146893771 )
      Property = 0;
    goto LABEL_22;
  }
  v31 = 0;
  v32 = 0;
  v17 = (unsigned int)Microsoft::Windows::Autopilot::HardwareInfo::GetTpmEkPubByteData(&v31) + 2146893807;
  if ( (unsigned int)v17 <= 0x24 )
  {
    v19 = 0x1080000001LL;
    if ( _bittest64(&v19, v17) )
    {
      *((_QWORD *)a1 + 2) = 0;
      if ( *((_QWORD *)a1 + 3) > 7u )
        a1 = *(char **)a1;
      *(_WORD *)a1 = 0;
      v9 = 0;
LABEL_48:
      std::vector<unsigned char>::_Tidy(&v31);
      return v9;
    }
  }
  v20 = -1;
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &cbOutput,
    (char *)&dword_180037114,
    0xFFFFFFFFFFFFFFFFuLL,
    v18);
  v21 = cbOutput;
  if ( !cbOutput )
  {
    v9 = -2147024882;
    v22 = 2147942414LL;
    v23 = 306;
    goto LABEL_46;
  }
  v24 = GetLastError();
  LocalFree(v21);
  SetLastError(v24);
  cbOutput = 0;
  v25 = EncodeBase64W((const unsigned __int8 *)v31, DWORD2(v31) - v31, &cbOutput);
  v9 = v25;
  if ( v25 < 0 )
  {
    v22 = (unsigned int)v25;
    v23 = 308;
LABEL_46:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
      (const char *)v22,
      pcbResult);
    if ( cbOutput )
      LocalFree(cbOutput);
    goto LABEL_48;
  }
  v27 = cbOutput;
  do
    ++v20;
  while ( cbOutput[v20] );
  if ( v20 > *((_QWORD *)a1 + 3) )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
      (char **)a1,
      v20,
      v26,
      cbOutput);
  }
  else
  {
    if ( *((_QWORD *)a1 + 3) <= 7u )
      v28 = a1;
    else
      v28 = *(char **)a1;
    *((_QWORD *)a1 + 2) = v20;
    memmove_0(v28, v27, 2 * v20);
    *(_WORD *)&v28[2 * v20] = 0;
  }
  if ( cbOutput )
    LocalFree(cbOutput);
  std::vector<unsigned char>::_Tidy(&v31);
  return 0;
}

```

## disassembly

```asm
0x18001b940  mov     [rsp-38h+arg_0], rbx
0x18001b945  push    rbp
0x18001b946  push    rsi
0x18001b947  push    rdi
0x18001b948  push    r12
0x18001b94a  push    r13
0x18001b94c  push    r14
0x18001b94e  push    r15
0x18001b950  mov     rbp, rsp
0x18001b953  sub     rsp, 60h
0x18001b957  mov     rsi, rcx
0x18001b95a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x18001b961  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x18001b966  xor     r13d, r13d
0x18001b969  test    al, al
0x18001b96b  jnz     loc_18001BBE7
0x18001b971  mov     [rbp+phProvider], r13
0x18001b975  xor     r8d, r8d; dwFlags
0x18001b978  lea     rdx, pszProviderName; "Microsoft Platform Crypto Provider"
0x18001b97f  lea     rcx, [rbp+phProvider]; phProvider
0x18001b983  call    cs:__imp_NCryptOpenStorageProvider
0x18001b98a  nop     dword ptr [rax+rax+00h]
0x18001b98f  mov     edi, eax
0x18001b991  mov     eax, r13d
0x18001b994  mov     dword ptr [rbp+cbOutput], eax
0x18001b997  test    edi, edi
0x18001b999  js      short loc_18001B9CB
0x18001b99b  mov     [rsp+60h+dwFlags], r13d; dwFlags
0x18001b9a0  lea     rax, [rbp+cbOutput]
0x18001b9a4  mov     [rsp+60h+pcbResult], rax; int
0x18001b9a9  xor     r9d, r9d; cbOutput
0x18001b9ac  xor     r8d, r8d; pbOutput
0x18001b9af  lea     rdx, pszProperty; "PCP_EKPUB"
0x18001b9b6  mov     rcx, [rbp+phProvider]; hObject
0x18001b9ba  call    cs:__imp_NCryptGetProperty
0x18001b9c1  nop     dword ptr [rax+rax+00h]
0x18001b9c6  mov     edi, eax
0x18001b9c8  mov     eax, dword ptr [rbp+cbOutput]
0x18001b9cb  mov     [rbp+arg_10], r13d
0x18001b9cf  mov     ebx, eax
0x18001b9d1  mov     edx, eax; uBytes
0x18001b9d3  xor     ecx, ecx; uFlags
0x18001b9d5  call    cs:__imp_LocalAlloc
0x18001b9dc  nop     dword ptr [rax+rax+00h]
0x18001b9e1  mov     r15, rax
0x18001b9e4  mov     [rbp+var_28], rax
0x18001b9e8  test    rax, rax
0x18001b9eb  jz      short loc_18001BA02
0x18001b9ed  lea     rcx, [rbx+rax]
0x18001b9f1  cmp     rax, rcx
0x18001b9f4  jz      short loc_18001BA02
0x18001b9f6  xor     edx, edx
0x18001b9f8  mov     [rax], dl
0x18001b9fa  inc     rax
0x18001b9fd  cmp     rax, rcx
0x18001ba00  jnz     short loc_18001B9F6
0x18001ba02  test    r15, r15
0x18001ba05  jnz     short loc_18001BA2A
0x18001ba07  mov     rcx, [rbp+38h]; this
0x18001ba0b  mov     ebx, 8007000Eh
0x18001ba10  mov     r9d, ebx; char *
0x18001ba13  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001ba1a  mov     edx, 146h; void *
0x18001ba1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ba24  nop
0x18001ba25  jmp     loc_18001BCE6
0x18001ba2a  test    edi, edi
0x18001ba2c  js      short loc_18001BA5C
0x18001ba2e  mov     [rsp+60h+dwFlags], r13d; dwFlags
0x18001ba33  lea     rax, [rbp+arg_10]
0x18001ba37  mov     [rsp+60h+pcbResult], rax; int
0x18001ba3c  mov     r9d, dword ptr [rbp+cbOutput]; cbOutput
0x18001ba40  mov     r8, r15; pbOutput
0x18001ba43  lea     rdx, pszProperty; "PCP_EKPUB"
0x18001ba4a  mov     rcx, [rbp+phProvider]; hObject
0x18001ba4e  call    cs:__imp_NCryptGetProperty
0x18001ba55  nop     dword ptr [rax+rax+00h]
0x18001ba5a  mov     edi, eax
0x18001ba5c  or      r14, 0FFFFFFFFFFFFFFFFh
0x18001ba60  mov     r8, r14
0x18001ba63  lea     rdx, dword_180037114
0x18001ba6a  lea     rcx, [rbp+hMem]
0x18001ba6e  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18001ba73  nop
0x18001ba74  mov     r12, [rbp+hMem]
0x18001ba78  test    r12, r12
0x18001ba7b  jnz     short loc_18001BAC5
0x18001ba7d  mov     rcx, [rbp+38h]; this
0x18001ba81  mov     ebx, 8007000Eh
0x18001ba86  mov     r9d, ebx; char *
0x18001ba89  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001ba90  mov     edx, 14Dh; void *
0x18001ba95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ba9a  nop
0x18001ba9b  mov     rcx, [rbp+hMem]; hMem
0x18001ba9f  test    rcx, rcx
0x18001baa2  jz      short loc_18001BAB1
0x18001baa4  call    cs:__imp_LocalFree
0x18001baab  nop     dword ptr [rax+rax+00h]
0x18001bab0  nop
0x18001bab1  mov     rcx, r15; hMem
0x18001bab4  call    cs:__imp_LocalFree
0x18001babb  nop     dword ptr [rax+rax+00h]
0x18001bac0  jmp     loc_18001BCE6
0x18001bac5  test    edi, edi
0x18001bac7  js      short loc_18001BB24
0x18001bac9  call    cs:__imp_GetLastError
0x18001bad0  nop     dword ptr [rax+rax+00h]
0x18001bad5  mov     ebx, eax
0x18001bad7  mov     rcx, r12; hMem
0x18001bada  call    cs:__imp_LocalFree
0x18001bae1  nop     dword ptr [rax+rax+00h]
0x18001bae6  mov     ecx, ebx; dwErrCode
0x18001bae8  call    cs:__imp_SetLastError
0x18001baef  nop     dword ptr [rax+rax+00h]
0x18001baf4  mov     [rbp+hMem], r13
0x18001baf8  lea     r8, [rbp+hMem]
0x18001bafc  mov     edx, dword ptr [rbp+cbOutput]
0x18001baff  mov     rcx, r15
0x18001bb02  call    cs:__imp_?EncodeBase64W@@YAJPEBEHPEAPEAG@Z; EncodeBase64W(uchar const *,int,ushort * *)
0x18001bb09  nop     dword ptr [rax+rax+00h]
0x18001bb0e  test    eax, eax
0x18001bb10  jns     short loc_18001BB5B
0x18001bb12  call    cs:__imp_GetLastError
0x18001bb19  nop     dword ptr [rax+rax+00h]
0x18001bb1e  mov     edi, eax
0x18001bb20  mov     r12, [rbp+hMem]
0x18001bb24  cmp     edi, 80090030h
0x18001bb2a  jz      short loc_18001BB3C
0x18001bb2c  cmp     edi, 80090011h
0x18001bb32  jz      short loc_18001BB3C
0x18001bb34  cmp     edi, 80090035h
0x18001bb3a  jnz     short loc_18001BB3F
0x18001bb3c  mov     edi, r13d
0x18001bb3f  inc     r14
0x18001bb42  cmp     [r12+r14*2], r13w
0x18001bb47  jnz     short loc_18001BB3F
0x18001bb49  cmp     r14, [rsi+18h]
0x18001bb4d  ja      short loc_18001BB83
0x18001bb4f  cmp     qword ptr [rsi+18h], 7
0x18001bb54  jbe     short loc_18001BB61
0x18001bb56  mov     r13, [rsi]
0x18001bb59  jmp     short loc_18001BB64
0x18001bb5b  mov     r12, [rbp+hMem]
0x18001bb5f  jmp     short loc_18001BB3F
0x18001bb61  mov     r13, rsi
0x18001bb64  mov     [rsi+10h], r14
0x18001bb68  lea     rbx, [r14+r14]
0x18001bb6c  mov     r8, rbx; Size
0x18001bb6f  mov     rdx, r12; Src
0x18001bb72  mov     rcx, r13; void *
0x18001bb75  call    memmove_0
0x18001bb7a  xor     eax, eax
0x18001bb7c  mov     [rbx+r13], ax
0x18001bb81  jmp     short loc_18001BB91
0x18001bb83  mov     r9, r12
0x18001bb86  mov     rdx, r14
0x18001bb89  mov     rcx, rsi
0x18001bb8c  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18001bb91  test    edi, edi
0x18001bb93  jle     short loc_18001BBA0
0x18001bb95  movzx   edi, di
0x18001bb98  or      edi, 80070000h
0x18001bb9e  test    edi, edi
0x18001bba0  jns     short loc_18001BBBB
0x18001bba2  mov     rcx, [rbp+38h]; this
0x18001bba6  mov     r9d, edi; char *
0x18001bba9  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001bbb0  mov     edx, 15Eh; void *
0x18001bbb5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bbba  nop
0x18001bbbb  mov     rcx, [rbp+hMem]; hMem
0x18001bbbf  test    rcx, rcx
0x18001bbc2  jz      short loc_18001BBD1
0x18001bbc4  call    cs:__imp_LocalFree
0x18001bbcb  nop     dword ptr [rax+rax+00h]
0x18001bbd0  nop
0x18001bbd1  mov     rcx, r15; hMem
0x18001bbd4  call    cs:__imp_LocalFree
0x18001bbdb  nop     dword ptr [rax+rax+00h]
0x18001bbe0  mov     eax, edi
0x18001bbe2  jmp     loc_18001BD57
0x18001bbe7  xorps   xmm0, xmm0
0x18001bbea  movdqu  [rbp+var_20], xmm0
0x18001bbef  mov     [rbp+var_10], r13
0x18001bbf3  lea     rcx, [rbp+var_20]
0x18001bbf7  call    ?GetTpmEkPubByteData@HardwareInfo@Autopilot@Windows@Microsoft@@SAJAEAV?$vector@EV?$allocator@E@std@@@std@@@Z; Microsoft::Windows::Autopilot::HardwareInfo::GetTpmEkPubByteData(std::vector<uchar> &)
0x18001bbfc  add     eax, 7FF6FFEFh
0x18001bc01  cmp     eax, 24h ; '$'
0x18001bc04  ja      short loc_18001BC30
0x18001bc06  mov     rcx, 1080000001h
0x18001bc10  bt      rcx, rax
0x18001bc14  jnb     short loc_18001BC30
0x18001bc16  mov     [rsi+10h], r13
0x18001bc1a  cmp     qword ptr [rsi+18h], 7
0x18001bc1f  jbe     short loc_18001BC24
0x18001bc21  mov     rsi, [rsi]
0x18001bc24  mov     [rsi], r13w
0x18001bc28  mov     ebx, r13d
0x18001bc2b  jmp     loc_18001BCDD
0x18001bc30  or      r14, 0FFFFFFFFFFFFFFFFh
0x18001bc34  mov     r8, r14
0x18001bc37  lea     rdx, dword_180037114
0x18001bc3e  lea     rcx, [rbp+cbOutput]
0x18001bc42  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18001bc47  nop
0x18001bc48  mov     rdi, [rbp+cbOutput]
0x18001bc4c  test    rdi, rdi
0x18001bc4f  jnz     short loc_18001BC60
0x18001bc51  mov     ebx, 8007000Eh
0x18001bc56  mov     r9d, ebx
0x18001bc59  mov     edx, 132h
0x18001bc5e  jmp     short loc_18001BCB6
0x18001bc60  call    cs:__imp_GetLastError
0x18001bc67  nop     dword ptr [rax+rax+00h]
0x18001bc6c  mov     ebx, eax
0x18001bc6e  mov     rcx, rdi; hMem
0x18001bc71  call    cs:__imp_LocalFree
0x18001bc78  nop     dword ptr [rax+rax+00h]
0x18001bc7d  mov     ecx, ebx; dwErrCode
0x18001bc7f  call    cs:__imp_SetLastError
0x18001bc86  nop     dword ptr [rax+rax+00h]
0x18001bc8b  mov     [rbp+cbOutput], r13
0x18001bc8f  mov     rcx, qword ptr [rbp+var_20]
0x18001bc93  mov     edx, dword ptr [rbp+var_20+8]
0x18001bc96  sub     edx, ecx
0x18001bc98  lea     r8, [rbp+cbOutput]
0x18001bc9c  call    cs:__imp_?EncodeBase64W@@YAJPEBEHPEAPEAG@Z; EncodeBase64W(uchar const *,int,ushort * *)
0x18001bca3  nop     dword ptr [rax+rax+00h]
0x18001bca8  mov     ebx, eax
0x18001bcaa  test    eax, eax
0x18001bcac  jns     short loc_18001BCEA
0x18001bcae  mov     r9d, eax; char *
0x18001bcb1  mov     edx, 134h; void *
0x18001bcb6  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001bcbd  mov     rcx, [rbp+38h]; this
0x18001bcc1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bcc6  nop
0x18001bcc7  mov     rcx, [rbp+cbOutput]; hMem
0x18001bccb  test    rcx, rcx
0x18001bcce  jz      short loc_18001BCDD
0x18001bcd0  call    cs:__imp_LocalFree
0x18001bcd7  nop     dword ptr [rax+rax+00h]
0x18001bcdc  nop
0x18001bcdd  lea     rcx, [rbp+var_20]
0x18001bce1  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18001bce6  mov     eax, ebx
0x18001bce8  jmp     short loc_18001BD57
0x18001bcea  mov     r9, [rbp+cbOutput]
0x18001bcee  inc     r14
0x18001bcf1  cmp     [r9+r14*2], r13w
0x18001bcf6  jnz     short loc_18001BCEE
0x18001bcf8  cmp     r14, [rsi+18h]
0x18001bcfc  ja      short loc_18001BD2A
0x18001bcfe  cmp     qword ptr [rsi+18h], 7
0x18001bd03  jbe     short loc_18001BD0A
0x18001bd05  mov     rdi, [rsi]
0x18001bd08  jmp     short loc_18001BD0D
0x18001bd0a  mov     rdi, rsi
0x18001bd0d  mov     [rsi+10h], r14
0x18001bd11  lea     rbx, [r14+r14]
0x18001bd15  mov     r8, rbx; Size
0x18001bd18  mov     rdx, r9; Src
0x18001bd1b  mov     rcx, rdi; void *
0x18001bd1e  call    memmove_0
0x18001bd23  mov     [rbx+rdi], r13w
0x18001bd28  jmp     short loc_18001BD36
0x18001bd2a  mov     rdx, r14
0x18001bd2d  mov     rcx, rsi
0x18001bd30  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18001bd35  nop
0x18001bd36  mov     rcx, [rbp+cbOutput]; hMem
0x18001bd3a  test    rcx, rcx
0x18001bd3d  jz      short loc_18001BD4C
0x18001bd3f  call    cs:__imp_LocalFree
0x18001bd46  nop     dword ptr [rax+rax+00h]
0x18001bd4b  nop
0x18001bd4c  lea     rcx, [rbp+var_20]
0x18001bd50  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18001bd55  xor     eax, eax
0x18001bd57  mov     rbx, [rsp+60h+arg_0]
0x18001bd5f  add     rsp, 60h
0x18001bd63  pop     r15
0x18001bd65  pop     r14
0x18001bd67  pop     r13
0x18001bd69  pop     r12
0x18001bd6b  pop     rdi
0x18001bd6c  pop     rsi
0x18001bd6d  pop     rbp
0x18001bd6e  retn
```
