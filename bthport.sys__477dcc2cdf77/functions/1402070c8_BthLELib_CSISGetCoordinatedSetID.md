# BthLELib_CSISGetCoordinatedSetID

- ea: `0x1402070c8`
- end: `0x1402074c2`
- name: `BthLELib_CSISGetCoordinatedSetID`
- size: `1018`
- prototype: `__int64 __fastcall(BCRYPT_HANDLE hObject, PUCHAR pbInput)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x14001acd4`

## callees

- `0x140004044`
- `0x14000434c`
- `0x1400054dc`
- `0x140005558`
- `0x14015f274`
- `0x14015f368`
- `0x14015fa50`
- `0x1402070c8`

## import_xrefs

- `ksecdd!BCryptGetProperty` at `0x140207112`
- `ksecdd!BCryptGetProperty` at `0x14020732d`
- `ksecdd!BCryptGetProperty` at `0x140207112`
- `ksecdd!BCryptGetProperty` at `0x14020732d`
- `ksecdd!BCryptCreateHash` at `0x1402071ff`
- `ksecdd!BCryptCreateHash` at `0x1402071ff`
- `ksecdd!BCryptHashData` at `0x14020726a`
- `ksecdd!BCryptHashData` at `0x14020729f`
- `ksecdd!BCryptHashData` at `0x1402072db`
- `ksecdd!BCryptHashData` at `0x14020726a`
- `ksecdd!BCryptHashData` at `0x14020729f`
- `ksecdd!BCryptHashData` at `0x1402072db`
- `ksecdd!BCryptFinishHash` at `0x1402073dc`
- `ksecdd!BCryptFinishHash` at `0x1402073dc`

## pseudocode

```c
__int64 __fastcall BthLELib_CSISGetCoordinatedSetID(BCRYPT_HANDLE hObject, PUCHAR pbInput, __int64 a3, __int64 a4)
{
  __int64 v7; // rdx
  NTSTATUS Property; // ebx
  __int64 v9; // r8
  __int64 v11; // r14
  __int64 v12; // rbx
  UCHAR *v13; // rdi
  signed __int64 v14; // rsi
  UCHAR *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rdx
  int v19; // r8d
  int v20; // r9d
  unsigned __int64 v21; // r8
  __int64 v22; // rdi
  UCHAR *v23; // rbx
  signed __int64 v24; // rsi
  UCHAR *v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rcx
  int v28; // edx
  NTSTATUS v29; // edi
  int v30; // r8d
  UCHAR pbOutput[4]; // [rsp+40h] [rbp-29h] BYREF
  ULONG pcbResult; // [rsp+44h] [rbp-25h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-21h] BYREF
  PUCHAR v34; // [rsp+50h] [rbp-19h] BYREF
  UCHAR *v35; // [rsp+58h] [rbp-11h]
  PUCHAR pbHashObject; // [rsp+68h] [rbp-1h] BYREF
  UCHAR *v37; // [rsp+70h] [rbp+7h]
  __int64 pbInputa; // [rsp+E0h] [rbp+77h] BYREF

  pbInputa = a3;
  *(_DWORD *)pbOutput = 0;
  pcbResult = 0;
  Property = BCryptGetProperty(hObject, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
  if ( Property < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_sd(
        WPP_GLOBAL_Control->DeviceExtension,
        v7,
        v9,
        51,
        (__int64)WPP_272f78d0e0f932ff6a8fef96cae1cc50_Traceguids);
    return (unsigned int)Property;
  }
  if ( pcbResult != 4 )
    return 3221225990LL;
  utl::vector<utl::shared_ptr<CentralConnectedStream>,utl::allocator<utl::shared_ptr<CentralConnectedStream>>>::vector<utl::shared_ptr<CentralConnectedStream>,utl::allocator<utl::shared_ptr<CentralConnectedStream>>>(
    &pbHashObject,
    v7,
    v9);
  v11 = *(unsigned int *)pbOutput;
  v12 = *(unsigned int *)pbOutput;
  v13 = pbHashObject;
  v14 = v37 - pbHashObject;
  if ( *(unsigned int *)pbOutput > (unsigned __int64)(v37 - pbHashObject) )
  {
    if ( !(unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(
                             &pbHashObject,
                             *(unsigned int *)pbOutput)
      || !(unsigned __int8)utl::_RangeFillApc<utl::allocator<unsigned char>>(v17, v16, v37, v12 - v14) )
    {
      goto LABEL_41;
    }
    v13 = pbHashObject;
    v15 = &pbHashObject[v11];
    LODWORD(v11) = *(_DWORD *)pbOutput;
  }
  else
  {
    v15 = &pbHashObject[*(unsigned int *)pbOutput];
  }
  v37 = v15;
  phHash = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &phHash,
    0);
  Property = BCryptCreateHash(hObject, &phHash, v13, v11, 0, 0, 0);
  if ( Property >= 0 )
  {
    Property = BCryptHashData(phHash, (PUCHAR)&GUID_CSIS_SET_ID_NAMESPACE, 0x10u, 0);
    if ( Property < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_15;
      v20 = 53;
      goto LABEL_14;
    }
    Property = BCryptHashData(phHash, pbInput, 0x10u, 0);
    if ( Property < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_15;
      v20 = 54;
      goto LABEL_14;
    }
    Property = BCryptHashData(phHash, (PUCHAR)&pbInputa, 8u, 0);
    if ( Property < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_15;
      v20 = 55;
      goto LABEL_14;
    }
    Property = BCryptGetProperty(hObject, L"HashDigestLength", pbOutput, 4u, &pcbResult, 0);
    if ( Property < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_15;
      v20 = 56;
      goto LABEL_14;
    }
    if ( pcbResult != 4 || *(_DWORD *)pbOutput < 0x10u )
    {
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phHash);
      Property = -1073741811;
      goto LABEL_42;
    }
    utl::vector<utl::shared_ptr<CentralConnectedStream>,utl::allocator<utl::shared_ptr<CentralConnectedStream>>>::vector<utl::shared_ptr<CentralConnectedStream>,utl::allocator<utl::shared_ptr<CentralConnectedStream>>>(
      &v34,
      v18,
      *(unsigned int *)pbOutput);
    v22 = (unsigned int)v21;
    v23 = v34;
    v24 = v35 - v34;
    if ( v21 <= v35 - v34 )
    {
      v25 = &v34[v21];
      goto LABEL_35;
    }
    if ( (unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(&v34, (unsigned int)v21)
      && (unsigned __int8)utl::_RangeFillApc<utl::allocator<unsigned char>>(v27, v26, v35, v22 - v24) )
    {
      v23 = v34;
      LODWORD(v21) = *(_DWORD *)pbOutput;
      v25 = &v34[v22];
LABEL_35:
      v35 = v25;
      v29 = BCryptFinishHash(phHash, v23, v21, 0);
      if ( v29 >= 0 )
      {
        *(_OWORD *)a4 = *(_OWORD *)v23;
        *(_WORD *)(a4 + 6) = *(_WORD *)(a4 + 6) & 0xFFF | 0x5000;
        *(_BYTE *)(a4 + 8) = *(_BYTE *)(a4 + 8) & 0x3F | 0x80;
        utl::vector<enum utl::byte,utl::allocator<enum utl::byte>>::_Uninit(&v34);
        wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phHash);
        Property = 0;
      }
      else
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_sd(
            WPP_GLOBAL_Control->DeviceExtension,
            v28,
            v30,
            57,
            (__int64)WPP_272f78d0e0f932ff6a8fef96cae1cc50_Traceguids);
        utl::vector<enum utl::byte,utl::allocator<enum utl::byte>>::_Uninit(&v34);
        wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phHash);
        Property = v29;
      }
      goto LABEL_42;
    }
    utl::vector<enum utl::byte,utl::allocator<enum utl::byte>>::_Uninit(&v34);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phHash);
LABEL_41:
    Property = -1073741670;
    goto LABEL_42;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v20 = 52;
LABEL_14:
    WPP_RECORDER_SF_sd(
      WPP_GLOBAL_Control->DeviceExtension,
      v18,
      v19,
      v20,
      (__int64)WPP_272f78d0e0f932ff6a8fef96cae1cc50_Traceguids);
  }
LABEL_15:
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phHash);
LABEL_42:
  utl::vector<enum utl::byte,utl::allocator<enum utl::byte>>::_Uninit(&pbHashObject);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x1402070c8  mov     [rsp-8+pbInput], r8
0x1402070cd  push    rbp
0x1402070ce  push    rbx
0x1402070cf  push    rsi
0x1402070d0  push    rdi
0x1402070d1  push    r12
0x1402070d3  push    r13
0x1402070d5  push    r14
0x1402070d7  push    r15
0x1402070d9  lea     rbp, [rsp-1Fh]
0x1402070de  sub     rsp, 88h
0x1402070e5  xor     edi, edi
0x1402070e7  lea     rax, [rbp+57h+var_7C]
0x1402070eb  mov     r13, r9
0x1402070ee  mov     [rsp+0C0h+dwFlags], edi; dwFlags
0x1402070f2  mov     r12, rdx
0x1402070f5  mov     dword ptr [rbp+57h+pbOutput], edi
0x1402070f8  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x1402070fc  mov     [rbp+57h+var_7C], edi
0x1402070ff  lea     r9d, [rdi+4]; cbOutput
0x140207103  mov     [rsp+0C0h+pcbResult], rax; pcbResult
0x140207108  lea     rdx, pszProperty; "ObjectLength"
0x14020710f  mov     r15, rcx
0x140207112  call    cs:__imp_BCryptGetProperty
0x140207119  nop     dword ptr [rax+rax+00h]
0x14020711e  mov     ebx, eax
0x140207120  test    eax, eax
0x140207122  jns     short loc_140207161
0x140207124  lea     rcx, WPP_RECORDER_INITIALIZED
0x14020712b  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140207132  jz      loc_14020749B
0x140207138  lea     rcx, WPP_272f78d0e0f932ff6a8fef96cae1cc50_Traceguids
0x14020713f  mov     [rsp+0C0h+var_90], eax
0x140207143  mov     [rsp+0C0h+pcbResult], rcx
0x140207148  lea     r9d, [rdi+33h]
0x14020714c  mov     rcx, cs:WPP_GLOBAL_Control
0x140207153  mov     rcx, [rcx+40h]
0x140207157  call    WPP_RECORDER_SF_sd
0x14020715c  jmp     loc_14020749B
0x140207161  cmp     [rbp+57h+var_7C], 4
0x140207165  jz      short loc_140207171
0x140207167  mov     eax, 0C0000206h
0x14020716c  jmp     loc_14020749D
0x140207171  lea     rcx, [rbp+57h+pbHashObject]
0x140207175  call    ??0?$vector@V?$shared_ptr@VCentralConnectedStream@@@utl@@V?$allocator@V?$shared_ptr@VCentralConnectedStream@@@utl@@@2@@utl@@QEAA@XZ; utl::vector<utl::shared_ptr<CentralConnectedStream>,utl::allocator<utl::shared_ptr<CentralConnectedStream>>>::vector<utl::shared_ptr<CentralConnectedStream>,utl::allocator<utl::shared_ptr<CentralConnectedStream>>>(void)
0x14020717a  mov     r14d, dword ptr [rbp+57h+pbOutput]
0x14020717e  mov     rsi, [rbp+57h+var_50]
0x140207182  mov     ebx, r14d
0x140207185  mov     rdi, [rbp+57h+pbHashObject]
0x140207189  sub     rsi, rdi
0x14020718c  cmp     r14, rsi
0x14020718f  ja      short loc_140207199
0x140207191  lea     rax, [r14+rdi]
0x140207195  xor     esi, esi
0x140207197  jmp     short loc_1402071D2
0x140207199  mov     rdx, rbx
0x14020719c  lea     rcx, [rbp+57h+pbHashObject]
0x1402071a0  call    ?reserve@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::reserve(unsigned __int64)
0x1402071a5  test    al, al
0x1402071a7  jz      loc_14020748D
0x1402071ad  mov     r8, [rbp+57h+var_50]
0x1402071b1  mov     r9, rbx
0x1402071b4  sub     r9, rsi
0x1402071b7  call    ??$_RangeFillApc@V?$allocator@E@utl@@@utl@@YA_NU?$integral_constant@_N$00@0@AEAV?$allocator@E@0@PEAE_K@Z; utl::_RangeFillApc<utl::allocator<uchar>>(utl::integral_constant<bool,1>,utl::allocator<uchar> &,uchar *,unsigned __int64)
0x1402071bc  xor     esi, esi
0x1402071be  test    al, al
0x1402071c0  jz      loc_14020748D
0x1402071c6  mov     rdi, [rbp+57h+pbHashObject]
0x1402071ca  lea     rax, [r14+rdi]
0x1402071ce  mov     r14d, dword ptr [rbp+57h+pbOutput]
0x1402071d2  xor     edx, edx
0x1402071d4  mov     [rbp+57h+var_50], rax
0x1402071d8  lea     rcx, [rbp+57h+phHash]
0x1402071dc  mov     [rbp+57h+phHash], rsi
0x1402071e0  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1402071e5  mov     [rsp+0C0h+var_90], esi; dwFlags
0x1402071e9  lea     rdx, [rbp+57h+phHash]; phHash
0x1402071ed  mov     [rsp+0C0h+dwFlags], esi; cbSecret
0x1402071f1  mov     r9d, r14d; cbHashObject
0x1402071f4  mov     r8, rdi; pbHashObject
0x1402071f7  mov     [rsp+0C0h+pcbResult], rsi; pbSecret
0x1402071fc  mov     rcx, r15; hAlgorithm
0x1402071ff  call    cs:__imp_BCryptCreateHash
0x140207206  nop     dword ptr [rax+rax+00h]
0x14020720b  mov     ebx, eax
0x14020720d  test    eax, eax
0x14020720f  jns     short loc_140207255
0x140207211  lea     rcx, WPP_RECORDER_INITIALIZED
0x140207218  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14020721f  jz      short loc_140207247
0x140207221  mov     r9d, 34h ; '4'
0x140207227  lea     rcx, WPP_272f78d0e0f932ff6a8fef96cae1cc50_Traceguids
0x14020722e  mov     [rsp+0C0h+var_90], eax
0x140207232  mov     [rsp+0C0h+pcbResult], rcx
0x140207237  mov     rcx, cs:WPP_GLOBAL_Control
0x14020723e  mov     rcx, [rcx+40h]
0x140207242  call    WPP_RECORDER_SF_sd
0x140207247  lea     rcx, [rbp+57h+phHash]
0x14020724b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140207250  jmp     loc_140207492
0x140207255  mov     rcx, [rbp+57h+phHash]; hHash
0x140207259  lea     rdx, GUID_CSIS_SET_ID_NAMESPACE; pbInput
0x140207260  xor     r9d, r9d; dwFlags
0x140207263  lea     edi, [r9+10h]
0x140207267  mov     r8d, edi; cbInput
0x14020726a  call    cs:__imp_BCryptHashData
0x140207271  nop     dword ptr [rax+rax+00h]
0x140207276  mov     ebx, eax
0x140207278  test    eax, eax
0x14020727a  jns     short loc_140207292
0x14020727c  lea     rcx, WPP_RECORDER_INITIALIZED
0x140207283  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14020728a  jz      short loc_140207247
0x14020728c  lea     r9d, [rdi+25h]
0x140207290  jmp     short loc_140207227
0x140207292  mov     rcx, [rbp+57h+phHash]; hHash
0x140207296  xor     r9d, r9d; dwFlags
0x140207299  mov     r8d, edi; cbInput
0x14020729c  mov     rdx, r12; pbInput
0x14020729f  call    cs:__imp_BCryptHashData
0x1402072a6  nop     dword ptr [rax+rax+00h]
0x1402072ab  mov     ebx, eax
0x1402072ad  test    eax, eax
0x1402072af  jns     short loc_1402072CC
0x1402072b1  lea     rcx, WPP_RECORDER_INITIALIZED
0x1402072b8  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1402072bf  jz      short loc_140207247
0x1402072c1  mov     r9d, 36h ; '6'
0x1402072c7  jmp     loc_140207227
0x1402072cc  mov     rcx, [rbp+57h+phHash]; hHash
0x1402072d0  lea     rdx, [rbp+57h+pbInput]; pbInput
0x1402072d4  xor     r9d, r9d; dwFlags
0x1402072d7  lea     r8d, [r9+8]; cbInput
0x1402072db  call    cs:__imp_BCryptHashData
0x1402072e2  nop     dword ptr [rax+rax+00h]
0x1402072e7  mov     ebx, eax
0x1402072e9  test    eax, eax
0x1402072eb  jns     short loc_14020730C
0x1402072ed  lea     rcx, WPP_RECORDER_INITIALIZED
0x1402072f4  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1402072fb  jz      loc_140207247
0x140207301  mov     r9d, 37h ; '7'
0x140207307  jmp     loc_140207227
0x14020730c  lea     rax, [rbp+57h+var_7C]
0x140207310  mov     [rsp+0C0h+dwFlags], esi; dwFlags
0x140207314  mov     r9d, 4; cbOutput
0x14020731a  mov     [rsp+0C0h+pcbResult], rax; pcbResult
0x14020731f  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x140207323  mov     rcx, r15; hObject
0x140207326  lea     rdx, aHashdigestleng; "HashDigestLength"
0x14020732d  call    cs:__imp_BCryptGetProperty
0x140207334  nop     dword ptr [rax+rax+00h]
0x140207339  mov     ebx, eax
0x14020733b  test    eax, eax
0x14020733d  jns     short loc_14020735E
0x14020733f  lea     rcx, WPP_RECORDER_INITIALIZED
0x140207346  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14020734d  jz      loc_140207247
0x140207353  mov     r9d, 38h ; '8'
0x140207359  jmp     loc_140207227
0x14020735e  cmp     [rbp+57h+var_7C], 4
0x140207362  jnz     loc_1402074B2
0x140207368  mov     r8d, dword ptr [rbp+57h+pbOutput]
0x14020736c  cmp     r8d, edi
0x14020736f  jb      loc_1402074B2
0x140207375  lea     rcx, [rbp+57h+var_70]
0x140207379  call    ??0?$vector@V?$shared_ptr@VCentralConnectedStream@@@utl@@V?$allocator@V?$shared_ptr@VCentralConnectedStream@@@utl@@@2@@utl@@QEAA@XZ; utl::vector<utl::shared_ptr<CentralConnectedStream>,utl::allocator<utl::shared_ptr<CentralConnectedStream>>>::vector<utl::shared_ptr<CentralConnectedStream>,utl::allocator<utl::shared_ptr<CentralConnectedStream>>>(void)
0x14020737e  mov     rsi, [rbp+57h+var_68]
0x140207382  mov     edi, r8d
0x140207385  mov     rbx, [rbp+57h+var_70]
0x140207389  sub     rsi, rbx
0x14020738c  cmp     r8, rsi
0x14020738f  ja      short loc_140207397
0x140207391  lea     rax, [r8+rbx]
0x140207395  jmp     short loc_1402073CE
0x140207397  mov     rdx, rdi
0x14020739a  lea     rcx, [rbp+57h+var_70]
0x14020739e  call    ?reserve@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::reserve(unsigned __int64)
0x1402073a3  test    al, al
0x1402073a5  jz      loc_14020747B
0x1402073ab  mov     r8, [rbp+57h+var_68]
0x1402073af  mov     r9, rdi
0x1402073b2  sub     r9, rsi
0x1402073b5  call    ??$_RangeFillApc@V?$allocator@E@utl@@@utl@@YA_NU?$integral_constant@_N$00@0@AEAV?$allocator@E@0@PEAE_K@Z; utl::_RangeFillApc<utl::allocator<uchar>>(utl::integral_constant<bool,1>,utl::allocator<uchar> &,uchar *,unsigned __int64)
0x1402073ba  test    al, al
0x1402073bc  jz      loc_14020747B
0x1402073c2  mov     rbx, [rbp+57h+var_70]
0x1402073c6  mov     r8d, dword ptr [rbp+57h+pbOutput]; cbOutput
0x1402073ca  lea     rax, [rdi+rbx]
0x1402073ce  mov     rcx, [rbp+57h+phHash]; hHash
0x1402073d2  xor     r9d, r9d; dwFlags
0x1402073d5  mov     rdx, rbx; pbOutput
0x1402073d8  mov     [rbp+57h+var_68], rax
0x1402073dc  call    cs:__imp_BCryptFinishHash
0x1402073e3  nop     dword ptr [rax+rax+00h]
0x1402073e8  mov     edi, eax
0x1402073ea  test    eax, eax
0x1402073ec  jns     short loc_14020743A
0x1402073ee  lea     rcx, WPP_RECORDER_INITIALIZED
0x1402073f5  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1402073fc  jz      short loc_140207424
0x1402073fe  lea     rcx, WPP_272f78d0e0f932ff6a8fef96cae1cc50_Traceguids
0x140207405  mov     [rsp+0C0h+var_90], eax
0x140207409  mov     [rsp+0C0h+pcbResult], rcx
0x14020740e  mov     r9d, 39h ; '9'
0x140207414  mov     rcx, cs:WPP_GLOBAL_Control
0x14020741b  mov     rcx, [rcx+40h]
0x14020741f  call    WPP_RECORDER_SF_sd
0x140207424  lea     rcx, [rbp+57h+var_70]
0x140207428  call    ?_Uninit@?$vector@W4byte@utl@@V?$allocator@W4byte@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::byte,utl::allocator<utl::byte>>::_Uninit(void)
0x14020742d  lea     rcx, [rbp+57h+phHash]
0x140207431  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140207436  mov     ebx, edi
0x140207438  jmp     short loc_140207492
0x14020743a  movups  xmm0, xmmword ptr [rbx]
0x14020743d  mov     ecx, 0FFFh
0x140207442  movdqu  xmmword ptr [r13+0], xmm0
0x140207448  movzx   eax, word ptr [r13+6]
0x14020744d  and     ax, cx
0x140207450  lea     rcx, [rbp+57h+var_70]
0x140207454  or      ax, 5000h
0x140207458  mov     [r13+6], ax
0x14020745d  mov     al, [r13+8]
0x140207461  and     al, 3Fh
0x140207463  or      al, 80h
0x140207465  mov     [r13+8], al
0x140207469  call    ?_Uninit@?$vector@W4byte@utl@@V?$allocator@W4byte@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::byte,utl::allocator<utl::byte>>::_Uninit(void)
0x14020746e  lea     rcx, [rbp+57h+phHash]
0x140207472  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140207477  xor     ebx, ebx
0x140207479  jmp     short loc_140207492
0x14020747b  lea     rcx, [rbp+57h+var_70]
0x14020747f  call    ?_Uninit@?$vector@W4byte@utl@@V?$allocator@W4byte@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::byte,utl::allocator<utl::byte>>::_Uninit(void)
0x140207484  lea     rcx, [rbp+57h+phHash]
0x140207488  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14020748d  mov     ebx, 0C000009Ah
0x140207492  lea     rcx, [rbp+57h+pbHashObject]
0x140207496  call    ?_Uninit@?$vector@W4byte@utl@@V?$allocator@W4byte@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::byte,utl::allocator<utl::byte>>::_Uninit(void)
0x14020749b  mov     eax, ebx
0x14020749d  add     rsp, 88h
0x1402074a4  pop     r15
0x1402074a6  pop     r14
0x1402074a8  pop     r13
0x1402074aa  pop     r12
0x1402074ac  pop     rdi
0x1402074ad  pop     rsi
0x1402074ae  pop     rbx
0x1402074af  pop     rbp
0x1402074b0  retn
0x1402074b2  lea     rcx, [rbp+57h+phHash]
0x1402074b6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1402074bb  mov     ebx, 0C000000Dh
0x1402074c0  jmp     short loc_140207492
```
