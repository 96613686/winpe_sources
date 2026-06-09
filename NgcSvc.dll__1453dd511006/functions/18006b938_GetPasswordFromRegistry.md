# GetPasswordFromRegistry

- ea: `0x18006b938`
- end: `0x18006bfc7`
- name: `GetPasswordFromRegistry`
- size: `1679`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180069f50`

## callees

- `0x180020a0c`
- `0x180028d18`
- `0x180030eac`
- `0x180034cf8`
- `0x180046d90`
- `0x180048394`
- `0x180050b30`
- `0x180053064`
- `0x180069b58`
- `0x180069c60`
- `0x18006b938`
- `0x18006c320`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bdcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bf78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bf93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bfad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bdcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bf78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bf93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bfad`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006ba5f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006bcdc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006ba5f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006bcdc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006b9ff`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006b9ff`
- `CRYPT32!CryptUnprotectData` at `0x18006bdbf`
- `CRYPT32!CryptUnprotectData` at `0x18006bdbf`

## string_xrefs

- `0x18006b9f1`: `Software\Microsoft\Security\UserAccount\BootstrapData`
- `0x18006ba83`: `onecore\ds\security\ngc\kspsvc\svc\localaccount.cpp`
- `0x18006bd06`: `onecore\ds\security\ngc\kspsvc\svc\localaccount.cpp`
- `0x18006bdef`: `onecore\ds\security\ngc\kspsvc\svc\localaccount.cpp`
- `0x18006bee1`: `onecore\ds\security\ngc\kspsvc\svc\localaccount.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall GetPasswordFromRegistry(LPCWSTR lpValueName, _QWORD *a2, DWORD *a3)
{
  int v6; // ebx
  __int64 v7; // rdx
  unsigned __int8 *v8; // rdx
  __int64 v9; // rcx
  int JoinInfo; // eax
  unsigned int v11; // edi
  DWORD v12; // esi
  _QWORD *unique_hlocal_secure; // rax
  _OWORD *v14; // rbx
  _QWORD *v15; // rax
  BYTE *v16; // rbx
  int v17; // edi
  signed int v19; // eax
  int v20; // edx
  unsigned int v21; // r8d
  signed int v22; // eax
  int v23; // edx
  unsigned int v24; // r8d
  signed int LastError; // eax
  int v26; // edx
  unsigned int v27; // r8d
  unsigned int dwOptions; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-E0h]
  BYTE *pbData; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD *v32; // [rsp+58h] [rbp-A8h] BYREF
  LPBYTE lpData; // [rsp+60h] [rbp-A0h] BYREF
  void **v34; // [rsp+68h] [rbp-98h] BYREF
  _DWORD *v35; // [rsp+70h] [rbp-90h] BYREF
  void **v36; // [rsp+78h] [rbp-88h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-80h] BYREF
  DATA_BLOB pDataOut; // [rsp+88h] [rbp-78h] BYREF
  DATA_BLOB pOptionalEntropy; // [rsp+98h] [rbp-68h] BYREF
  DATA_BLOB pDataIn; // [rsp+A8h] [rbp-58h] BYREF
  _OWORD v41[7]; // [rsp+100h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]
  DWORD cbData; // [rsp+1D8h] [rbp+D8h] BYREF

  v36 = &Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable';
  hKey = 0;
  v41[0] = *(_OWORD *)L"F5302ECA3C9}";
  *(_OWORD *)((char *)v41 + 10) = *(_OWORD *)L"ECA3C9}";
  Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::Close(&v36);
  v6 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Security\\UserAccount\\BootstrapData",
         0,
         0,
         0,
         0x20019u,
         0,
         &hKey,
         0);
  if ( v6 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      v7 = 1099;
LABEL_9:
      wil::details::in1diag3::Log_Win32(
        retaddr,
        (void *)v7,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\localaccount.cpp",
        (const char *)(unsigned int)v6,
        dwOptions);
      goto LABEL_13;
    }
    if ( (unsigned int)dword_180122070 <= 2 )
      goto LABEL_13;
    v8 = (unsigned __int8 *)byte_1800FE46B;
    goto LABEL_12;
  }
  cbData = 0;
  v6 = RegQueryValueExW(hKey, lpValueName, 0, 0, 0, &cbData);
  if ( (v6 & 0xFFFFFFFD) != 0 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      v7 = 1130;
      goto LABEL_9;
    }
    if ( (unsigned int)dword_180122070 <= 2 )
    {
LABEL_13:
      if ( v6 > 0 )
        v6 = (unsigned __int16)v6 | 0x80070000;
      goto LABEL_64;
    }
    v8 = (unsigned __int8 *)&dword_1800FE444;
LABEL_12:
    LODWORD(pbData) = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_180122070,
      v8,
      0,
      0,
      (__int64)&pbData);
    goto LABEL_13;
  }
  v32 = 0;
  if ( v6 == 2 )
  {
    v34 = &Microsoft::WRL::Wrappers::HandleT<DsrJoinInfoHandleTraits>::`vftable';
    v35 = 0;
    JoinInfo = DsrGetJoinInfo(v9, &v35);
    v11 = JoinInfo;
    if ( JoinInfo < 0 )
    {
      if ( (unsigned int)dword_180122070 > 3 )
      {
        LODWORD(pbData) = JoinInfo;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_180122070,
          (unsigned __int8 *)word_1800FE40A,
          0,
          0,
          (__int64)&pbData);
      }
      v11 = 0;
    }
    if ( v35 && *v35 == 1 )
    {
      v12 = 90;
      unique_hlocal_secure = wil::make_unique_hlocal_secure_nothrow<unsigned char [0]>(&lpData, 0x5Au);
      wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::operator=(&v32, unique_hlocal_secure);
      wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&lpData);
      v14 = v32;
      if ( !v32 )
      {
        v34 = &Microsoft::WRL::Wrappers::HandleT<DsrJoinInfoHandleTraits>::`vftable';
        if ( v35 )
        {
          if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<DsrJoinInfoHandleTraits>::InternalClose(&v34) )
          {
            LastError = GetLastError();
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v26, v27);
            JUMPOUT(0x18006BFC6LL);
          }
          v35 = 0;
        }
        goto LABEL_26;
      }
      *v32 = *(_OWORD *)L"_TBAL_{68EDDCF5-0AEB-4C28-A770-AF5302ECA3C9}";
      v14[1] = *(_OWORD *)L"8EDDCF5-0AEB-4C28-A770-AF5302ECA3C9}";
      v14[2] = *(_OWORD *)L"0AEB-4C28-A770-AF5302ECA3C9}";
      v14[3] = *(_OWORD *)L"8-A770-AF5302ECA3C9}";
      v14[4] = v41[0];
      *(_OWORD *)((char *)v14 + 74) = *(_OWORD *)L"ECA3C9}";
    }
    else
    {
      v15 = wil::make_unique_hlocal_secure_nothrow<unsigned char [0]>(&lpData, 2u);
      wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::operator=(&v32, v15);
      wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&lpData);
      v14 = v32;
      if ( !v32 )
      {
        v34 = &Microsoft::WRL::Wrappers::HandleT<DsrJoinInfoHandleTraits>::`vftable';
        if ( v35 )
        {
          if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<DsrJoinInfoHandleTraits>::InternalClose(&v34) )
          {
            v19 = GetLastError();
            if ( v19 > 0 )
              v19 = (unsigned __int16)v19 | 0x80070000;
            Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v19, v20, v21);
            __debugbreak();
          }
          v35 = 0;
        }
        goto LABEL_26;
      }
      *(_WORD *)v32 = 0;
      v12 = 2;
    }
    v34 = &Microsoft::WRL::Wrappers::HandleT<DsrJoinInfoHandleTraits>::`vftable';
    if ( v35 && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<DsrJoinInfoHandleTraits>::InternalClose(&v34) )
    {
      v22 = GetLastError();
      if ( v22 > 0 )
        v22 = (unsigned __int16)v22 | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v22, v23, v24);
      __debugbreak();
    }
LABEL_58:
    v32 = 0;
    *a2 = v14;
    *a3 = v12;
    wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&v32);
    v36 = &Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable';
    Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::Close(&v36);
    return v11;
  }
  if ( !cbData || (cbData & 1) != 0 )
  {
    v6 = -2147418113;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x4B0,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\localaccount.cpp",
        (const char *)0x8000FFFFLL,
        dwOptions);
    }
    else if ( (unsigned int)dword_180122070 > 2 )
    {
      LODWORD(pbData) = -2147418113;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_180122070,
        (unsigned __int8 *)byte_1800FE3DB,
        0,
        0,
        (__int64)&pbData);
    }
    goto LABEL_63;
  }
  wil::make_unique_hlocal_secure_nothrow<unsigned char [0]>(&lpData, cbData);
  v16 = lpData;
  if ( lpData )
  {
    v17 = RegQueryValueExW(hKey, lpValueName, 0, 0, lpData, &cbData);
    if ( v17 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
      {
        wil::details::in1diag3::Log_Win32(
          retaddr,
          (void *)0x4CE,
          (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\localaccount.cpp",
          (const char *)(unsigned int)v17,
          dwOptionsa);
      }
      else if ( (unsigned int)dword_180122070 > 2 )
      {
        LODWORD(pbData) = v17;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_180122070,
          (unsigned __int8 *)&dword_1800FE3B4,
          0,
          0,
          (__int64)&pbData);
      }
      if ( v17 > 0 )
        v17 = (unsigned __int16)v17 | 0x80070000;
      wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&lpData);
      wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&v32);
      v6 = v17;
      goto LABEL_64;
    }
    *(&pDataIn.cbData + 1) = 0;
    *(_QWORD *)&pOptionalEntropy.cbData = 16;
    pDataOut = 0;
    pDataIn.cbData = cbData;
    pDataIn.pbData = v16;
    pOptionalEntropy.pbData = (BYTE *)&g_guidEntropy;
    if ( CryptUnprotectData(&pDataIn, 0, &pOptionalEntropy, 0, 0, 0, &pDataOut) )
    {
      v11 = 0;
      pbData = pDataOut.pbData;
      wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::operator=(&v32, &pbData);
      wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&pbData);
      v12 = pDataOut.cbData;
      pDataOut.pbData = 0;
      pDataOut.cbData = 0;
      wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&lpData);
      v14 = v32;
      goto LABEL_58;
    }
    v6 = GetLastError();
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      wil::details::in1diag3::Log_Win32(
        retaddr,
        (void *)0x4F0,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\localaccount.cpp",
        (const char *)(unsigned int)v6,
        dwOptionsb);
    }
    else if ( (unsigned int)dword_180122070 > 2 )
    {
      LODWORD(pbData) = v6;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_180122070,
        (unsigned __int8 *)word_1800FE38A,
        0,
        0,
        (__int64)&pbData);
    }
    if ( v6 > 0 )
      v6 = (unsigned __int16)v6 | 0x80070000;
    wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&lpData);
LABEL_63:
    wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&v32);
    goto LABEL_64;
  }
  wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&lpData);
LABEL_26:
  wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&v32);
  v6 = -2147024882;
LABEL_64:
  v36 = &Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::Close(&v36);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18006b938  mov     rax, rsp
0x18006b93b  push    rbp
0x18006b93c  push    rbx
0x18006b93d  push    rsi
0x18006b93e  push    rdi
0x18006b93f  push    r12
0x18006b941  push    r13
0x18006b943  push    r14
0x18006b945  push    r15
0x18006b947  lea     rbp, [rsp-78h]
0x18006b94c  sub     rsp, 178h
0x18006b953  movaps  xmmword ptr [rax-58h], xmm6
0x18006b957  movaps  xmmword ptr [rax-68h], xmm7
0x18006b95b  movaps  xmmword ptr [rax-78h], xmm8
0x18006b960  movaps  xmmword ptr [rax-88h], xmm9
0x18006b968  movaps  xmmword ptr [rax-98h], xmm10
0x18006b970  mov     r14, r8
0x18006b973  mov     r15, rdx
0x18006b976  mov     rdi, rcx
0x18006b979  lea     rsi, ??_7?$HandleT@URegKeyHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable'
0x18006b980  mov     [rsp+1B0h+var_138], rsi
0x18006b985  xor     r12d, r12d
0x18006b988  mov     [rbp+0B0h+hKey], r12
0x18006b98c  movaps  xmm7, xmmword ptr cs:aTbal68eddcf50a; "_TBAL_{68EDDCF5-0AEB-4C28-A770-AF5302EC"...
0x18006b993  movaps  xmm8, xmmword ptr cs:aTbal68eddcf50a+10h; "8EDDCF5-0AEB-4C28-A770-AF5302ECA3C9}"
0x18006b99b  movaps  xmm9, xmmword ptr cs:aTbal68eddcf50a+20h; "0AEB-4C28-A770-AF5302ECA3C9}"
0x18006b9a3  movaps  xmm10, xmmword ptr cs:aTbal68eddcf50a+30h; "8-A770-AF5302ECA3C9}"
0x18006b9ab  movaps  xmm0, xmmword ptr cs:aTbal68eddcf50a+40h; "F5302ECA3C9}"
0x18006b9b2  movaps  [rbp+0B0h+var_B0], xmm0
0x18006b9b6  movups  xmm6, xmmword ptr cs:aTbal68eddcf50a+4Ah; "ECA3C9}"
0x18006b9bd  movups  [rbp+0B0h+var_B0+0Ah], xmm6
0x18006b9c1  lea     rcx, [rsp+1B0h+var_138]
0x18006b9c6  call    ?Close@?$HandleT@URegKeyHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::Close(void)
0x18006b9cb  mov     [rsp+1B0h+lpdwDisposition], r12; lpdwDisposition
0x18006b9d0  lea     rax, [rbp+0B0h+hKey]
0x18006b9d4  mov     [rsp+1B0h+phkResult], rax; phkResult
0x18006b9d9  mov     [rsp+1B0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18006b9de  mov     [rsp+1B0h+samDesired], 20019h; samDesired
0x18006b9e6  mov     [rsp+1B0h+dwOptions], r12d; dwOptions
0x18006b9eb  xor     r9d, r9d; lpClass
0x18006b9ee  xor     r8d, r8d; Reserved
0x18006b9f1  lea     rdx, aSoftwareMicros_11; "Software\\Microsoft\\Security\\UserAcco"...
0x18006b9f8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006b9ff  call    cs:__imp_RegCreateKeyExW
0x18006ba05  mov     ebx, eax
0x18006ba07  test    eax, eax
0x18006ba09  jz      short loc_18006BA3A
0x18006ba0b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x18006ba12  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18006ba17  test    al, al
0x18006ba19  jz      short loc_18006BA22
0x18006ba1b  mov     edx, 44Bh
0x18006ba20  jmp     short loc_18006BA83
0x18006ba22  mov     eax, cs:dword_180122070
0x18006ba28  cmp     eax, 2
0x18006ba2b  jbe     loc_18006BACD
0x18006ba31  lea     rdx, byte_1800FE46B
0x18006ba38  jmp     short loc_18006BAAD
0x18006ba3a  mov     [rbp+0B0h+cbData], r12d
0x18006ba41  lea     rax, [rbp+0B0h+cbData]
0x18006ba48  mov     qword ptr [rsp+1B0h+samDesired], rax; lpcbData
0x18006ba4d  mov     qword ptr [rsp+1B0h+dwOptions], r12; int
0x18006ba52  xor     r9d, r9d; lpType
0x18006ba55  xor     r8d, r8d; lpReserved
0x18006ba58  mov     rdx, rdi; lpValueName
0x18006ba5b  mov     rcx, [rbp+0B0h+hKey]; hKey
0x18006ba5f  call    cs:__imp_RegQueryValueExW
0x18006ba65  mov     ebx, eax
0x18006ba67  test    eax, 0FFFFFFFDh
0x18006ba6c  jz      short loc_18006BAE3
0x18006ba6e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x18006ba75  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18006ba7a  test    al, al
0x18006ba7c  jz      short loc_18006BA9B
0x18006ba7e  mov     edx, 46Ah; void *
0x18006ba83  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x18006ba8a  mov     r9d, ebx; char *
0x18006ba8d  mov     rcx, [rbp+0B8h]; this
0x18006ba94  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18006ba99  jmp     short loc_18006BACD
0x18006ba9b  mov     eax, cs:dword_180122070
0x18006baa1  cmp     eax, 2
0x18006baa4  jbe     short loc_18006BACD
0x18006baa6  lea     rdx, dword_1800FE444
0x18006baad  xor     r9d, r9d
0x18006bab0  lea     rax, [rsp+1B0h+var_160]
0x18006bab5  xor     r8d, r8d
0x18006bab8  mov     qword ptr [rsp+1B0h+dwOptions], rax
0x18006babd  mov     dword ptr [rsp+1B0h+var_160], ebx
0x18006bac1  lea     rcx, dword_180122070
0x18006bac8  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18006bacd  test    ebx, ebx
0x18006bacf  jle     loc_18006BF36
0x18006bad5  movzx   ebx, bx
0x18006bad8  or      ebx, 80070000h
0x18006bade  jmp     loc_18006BF36
0x18006bae3  mov     [rsp+1B0h+var_158], r12
0x18006bae8  cmp     ebx, 2
0x18006baeb  jnz     loc_18006BC85
0x18006baf1  lea     r13, ??_7?$HandleT@UDsrJoinInfoHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<DsrJoinInfoHandleTraits>::`vftable'
0x18006baf8  mov     [rsp+1B0h+var_148], r13
0x18006bafd  mov     [rsp+1B0h+var_140], r12
0x18006bb02  lea     rdx, [rsp+1B0h+var_140]
0x18006bb07  call    DsrGetJoinInfo
0x18006bb0c  mov     edi, eax
0x18006bb0e  test    eax, eax
0x18006bb10  jns     short loc_18006BB47
0x18006bb12  mov     ecx, cs:dword_180122070
0x18006bb18  cmp     ecx, 3
0x18006bb1b  jbe     short loc_18006BB44
0x18006bb1d  mov     dword ptr [rsp+1B0h+var_160], eax
0x18006bb21  lea     rax, [rsp+1B0h+var_160]
0x18006bb26  mov     qword ptr [rsp+1B0h+dwOptions], rax
0x18006bb2b  xor     r9d, r9d
0x18006bb2e  xor     r8d, r8d
0x18006bb31  lea     rdx, word_1800FE40A
0x18006bb38  lea     rcx, dword_180122070
0x18006bb3f  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18006bb44  mov     edi, r12d
0x18006bb47  mov     rax, [rsp+1B0h+var_140]
0x18006bb4c  test    rax, rax
0x18006bb4f  jz      loc_18006BBEE
0x18006bb55  cmp     dword ptr [rax], 1
0x18006bb58  jnz     loc_18006BBEE
0x18006bb5e  mov     esi, 5Ah ; 'Z'
0x18006bb63  mov     edx, esi
0x18006bb65  lea     rcx, [rsp+1B0h+lpData]
0x18006bb6a  call    ??$make_unique_hlocal_secure_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_secure_nothrow<uchar [0]>(unsigned __int64)
0x18006bb6f  mov     rdx, rax
0x18006bb72  lea     rcx, [rsp+1B0h+var_158]
0x18006bb77  call    ??4?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::operator=(wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter> &&)
0x18006bb7c  lea     rcx, [rsp+1B0h+lpData]
0x18006bb81  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x18006bb86  mov     rbx, [rsp+1B0h+var_158]
0x18006bb8b  test    rbx, rbx
0x18006bb8e  jnz     short loc_18006BBCE
0x18006bb90  mov     [rsp+1B0h+var_148], r13
0x18006bb95  cmp     [rsp+1B0h+var_140], r12
0x18006bb9a  jz      short loc_18006BBB3
0x18006bb9c  lea     rcx, [rsp+1B0h+var_148]
0x18006bba1  call    ?InternalClose@?$HandleT@UDsrJoinInfoHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<DsrJoinInfoHandleTraits>::InternalClose(void)
0x18006bba6  test    al, al
0x18006bba8  jz      loc_18006BFAD
0x18006bbae  mov     [rsp+1B0h+var_140], r12
0x18006bbb3  lea     rcx, [rsp+1B0h+var_158]
0x18006bbb8  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x18006bbbd  mov     ebx, 8007000Eh
0x18006bbc2  lea     rsi, ??_7?$HandleT@URegKeyHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable'
0x18006bbc9  jmp     loc_18006BF36
0x18006bbce  movups  xmmword ptr [rbx], xmm7
0x18006bbd1  movups  xmmword ptr [rbx+10h], xmm8
0x18006bbd6  movups  xmmword ptr [rbx+20h], xmm9
0x18006bbdb  movups  xmmword ptr [rbx+30h], xmm10
0x18006bbe0  movaps  xmm0, [rbp+0B0h+var_B0]
0x18006bbe4  movups  xmmword ptr [rbx+40h], xmm0
0x18006bbe8  movups  xmmword ptr [rbx+4Ah], xmm6
0x18006bbec  jmp     short loc_18006BC5E
0x18006bbee  mov     edx, 2
0x18006bbf3  lea     rcx, [rsp+1B0h+lpData]
0x18006bbf8  call    ??$make_unique_hlocal_secure_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_secure_nothrow<uchar [0]>(unsigned __int64)
0x18006bbfd  mov     rdx, rax
0x18006bc00  lea     rcx, [rsp+1B0h+var_158]
0x18006bc05  call    ??4?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::operator=(wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter> &&)
0x18006bc0a  lea     rcx, [rsp+1B0h+lpData]
0x18006bc0f  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x18006bc14  mov     rbx, [rsp+1B0h+var_158]
0x18006bc19  test    rbx, rbx
0x18006bc1c  jnz     short loc_18006BC55
0x18006bc1e  mov     [rsp+1B0h+var_148], r13
0x18006bc23  cmp     [rsp+1B0h+var_140], r12
0x18006bc28  jz      short loc_18006BC41
0x18006bc2a  lea     rcx, [rsp+1B0h+var_148]
0x18006bc2f  call    ?InternalClose@?$HandleT@UDsrJoinInfoHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<DsrJoinInfoHandleTraits>::InternalClose(void)
0x18006bc34  test    al, al
0x18006bc36  jz      loc_18006BF78
0x18006bc3c  mov     [rsp+1B0h+var_140], r12
0x18006bc41  lea     rcx, [rsp+1B0h+var_158]
0x18006bc46  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x18006bc4b  mov     ebx, 8007000Eh
0x18006bc50  jmp     loc_18006BF36
0x18006bc55  mov     [rbx], r12w
0x18006bc59  mov     esi, 2
0x18006bc5e  mov     [rsp+1B0h+var_148], r13
0x18006bc63  cmp     [rsp+1B0h+var_140], r12
0x18006bc68  jz      loc_18006BE8F
0x18006bc6e  lea     rcx, [rsp+1B0h+var_148]
0x18006bc73  call    ?InternalClose@?$HandleT@UDsrJoinInfoHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<DsrJoinInfoHandleTraits>::InternalClose(void)
0x18006bc78  test    al, al
0x18006bc7a  jz      loc_18006BF93
0x18006bc80  jmp     loc_18006BE8F
0x18006bc85  mov     eax, [rbp+0B0h+cbData]
0x18006bc8b  test    eax, eax
0x18006bc8d  jz      loc_18006BEC2
0x18006bc93  test    al, 1
0x18006bc95  jnz     loc_18006BEC2
0x18006bc9b  mov     edx, eax
0x18006bc9d  lea     rcx, [rsp+1B0h+lpData]
0x18006bca2  call    ??$make_unique_hlocal_secure_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_secure_nothrow<uchar [0]>(unsigned __int64)
0x18006bca7  nop
0x18006bca8  mov     rbx, [rsp+1B0h+lpData]
0x18006bcad  test    rbx, rbx
0x18006bcb0  jnz     short loc_18006BCBE
0x18006bcb2  lea     rcx, [rsp+1B0h+lpData]
0x18006bcb7  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x18006bcbc  jmp     short loc_18006BC41
0x18006bcbe  lea     rax, [rbp+0B0h+cbData]
0x18006bcc5  mov     qword ptr [rsp+1B0h+samDesired], rax; lpcbData
0x18006bcca  mov     qword ptr [rsp+1B0h+dwOptions], rbx; unsigned int
0x18006bccf  xor     r9d, r9d; lpType
0x18006bcd2  xor     r8d, r8d; lpReserved
0x18006bcd5  mov     rdx, rdi; lpValueName
0x18006bcd8  mov     rcx, [rbp+0B0h+hKey]; hKey
0x18006bcdc  call    cs:__imp_RegQueryValueExW
0x18006bce2  mov     edi, eax
0x18006bce4  test    eax, eax
0x18006bce6  jz      loc_18006BD74
0x18006bcec  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x18006bcf3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18006bcf8  test    al, al
0x18006bcfa  jz      short loc_18006BD19
0x18006bcfc  mov     rcx, [rbp+0B8h]; this
0x18006bd03  mov     r9d, edi; char *
0x18006bd06  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x18006bd0d  mov     edx, 4CEh; void *
0x18006bd12  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18006bd17  jmp     short loc_18006BD4B
0x18006bd19  mov     eax, cs:dword_180122070
0x18006bd1f  cmp     eax, 2
0x18006bd22  jbe     short loc_18006BD4B
0x18006bd24  mov     dword ptr [rsp+1B0h+var_160], edi
0x18006bd28  lea     rax, [rsp+1B0h+var_160]
0x18006bd2d  mov     qword ptr [rsp+1B0h+dwOptions], rax
0x18006bd32  xor     r9d, r9d
0x18006bd35  xor     r8d, r8d
0x18006bd38  lea     rdx, dword_1800FE3B4
0x18006bd3f  lea     rcx, dword_180122070
0x18006bd46  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18006bd4b  test    edi, edi
0x18006bd4d  jle     short loc_18006BD58
0x18006bd4f  movzx   edi, di
0x18006bd52  or      edi, 80070000h
0x18006bd58  lea     rcx, [rsp+1B0h+lpData]
0x18006bd5d  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x18006bd62  nop
0x18006bd63  lea     rcx, [rsp+1B0h+var_158]
0x18006bd68  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x18006bd6d  mov     ebx, edi
0x18006bd6f  jmp     loc_18006BF36
0x18006bd74  mov     dword ptr [rbp+0B0h+pDataIn+4], r12d
0x18006bd78  mov     qword ptr [rbp+0B0h+pOptionalEntropy.cbData], 10h
0x18006bd80  xorps   xmm0, xmm0
0x18006bd83  movups  xmmword ptr [rbp+0B0h+pDataOut.cbData], xmm0
0x18006bd87  mov     eax, [rbp+0B0h+cbData]
0x18006bd8d  mov     [rbp+0B0h+pDataIn.cbData], eax
0x18006bd90  mov     [rbp+0B0h+pDataIn.pbData], rbx
0x18006bd94  lea     rax, ?g_guidEntropy@@3U_GUID@@A; _GUID g_guidEntropy
0x18006bd9b  mov     [rbp+0B0h+pOptionalEntropy.pbData], rax
0x18006bd9f  lea     rax, [rbp+0B0h+pDataOut]
0x18006bda3  mov     [rsp+1B0h+lpSecurityAttributes], rax; pDataOut
0x18006bda8  mov     [rsp+1B0h+samDesired], r12d; dwFlags
0x18006bdad  mov     qword ptr [rsp+1B0h+dwOptions], r12; unsigned int
0x18006bdb2  xor     r9d, r9d; pvReserved
0x18006bdb5  lea     r8, [rbp+0B0h+pOptionalEntropy]; pOptionalEntropy
0x18006bdb9  xor     edx, edx; ppszDataDescr
0x18006bdbb  lea     rcx, [rbp+0B0h+pDataIn]; pDataIn
0x18006bdbf  call    cs:__imp_CryptUnprotectData
0x18006bdc5  test    eax, eax
0x18006bdc7  jnz     loc_18006BE50
0x18006bdcd  call    cs:__imp_GetLastError
0x18006bdd3  mov     ebx, eax
0x18006bdd5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x18006bddc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18006bde1  test    al, al
0x18006bde3  jz      short loc_18006BE02
0x18006bde5  mov     rcx, [rbp+0B8h]; this
0x18006bdec  mov     r9d, ebx; char *
0x18006bdef  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x18006bdf6  mov     edx, 4F0h; void *
0x18006bdfb  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18006be00  jmp     short loc_18006BE34
0x18006be02  mov     eax, cs:dword_180122070
0x18006be08  cmp     eax, 2
0x18006be0b  jbe     short loc_18006BE34
0x18006be0d  mov     dword ptr [rsp+1B0h+var_160], ebx
0x18006be11  lea     rax, [rsp+1B0h+var_160]
0x18006be16  mov     qword ptr [rsp+1B0h+dwOptions], rax
0x18006be1b  xor     r9d, r9d
0x18006be1e  xor     r8d, r8d
0x18006be21  lea     rdx, word_1800FE38A
0x18006be28  lea     rcx, dword_180122070
0x18006be2f  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18006be34  test    ebx, ebx
0x18006be36  jle     short loc_18006BE41
0x18006be38  movzx   ebx, bx
0x18006be3b  or      ebx, 80070000h
0x18006be41  lea     rcx, [rsp+1B0h+lpData]
0x18006be46  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x18006be4b  jmp     loc_18006BF2B
0x18006be50  mov     edi, r12d
0x18006be53  mov     rax, [rbp+0B0h+pDataOut.pbData]
  ... truncated ...
```
