# NgcKspServer::NgcAuthorityKey::GetAikPubFromAikCertificate(std::vector<uchar,std::allocator<uchar>> const &,std::unique_ptr<NgcUtils::RsaKey,std::default_delete<NgcUtils::RsaKey>> *)

- ea: `0x18007ad60`
- end: `0x18007b1f2`
- name: `?GetAikPubFromAikCertificate@NgcAuthorityKey@NgcKspServer@@CAJAEBV?$vector@EV?$allocator@E@std@@@std@@PEAV?$unique_ptr@URsaKey@NgcUtils@@U?$default_delete@URsaKey@NgcUtils@@@std@@@4@@Z`
- size: `1170`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180010ff0`

## callees

- `0x180010990`
- `0x180010a94`
- `0x180028ca0`
- `0x180028d18`
- `0x180031c3c`
- `0x180034cf8`
- `0x180046d90`
- `0x180053064`
- `0x18005d2ec`
- `0x180064b30`
- `0x180068b78`
- `0x18007ad60`
- `0x18007c9e0`
- `0x18008a044`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007adab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ae8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b176`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b190`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b1a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b1c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b1d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007adab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ae8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b176`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b190`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b1a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b1c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b1d8`
- `bcrypt!BCryptExportKey` at `0x18007af6a`
- `bcrypt!BCryptExportKey` at `0x18007b04b`
- `bcrypt!BCryptExportKey` at `0x18007af6a`
- `bcrypt!BCryptExportKey` at `0x18007b04b`
- `CRYPT32!CertCreateCertificateContext` at `0x18007ad8d`
- `CRYPT32!CertCreateCertificateContext` at `0x18007ad8d`
- `CRYPT32!CryptImportPublicKeyInfoEx2` at `0x18007ae80`
- `CRYPT32!CryptImportPublicKeyInfoEx2` at `0x18007ae80`

## string_xrefs

- `0x18007adca`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`
- `0x18007aead`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`
- `0x18007af91`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`
- `0x18007b072`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall NgcKspServer::NgcAuthorityKey::GetAikPubFromAikCertificate(__int64 a1, __int64 *a2)
{
  PCCERT_CONTEXT CertificateContext; // rax
  signed int LastError; // edi
  unsigned int v5; // edi
  signed int v7; // edi
  NTSTATUS v8; // ebx
  unsigned int v9; // ebx
  NTSTATUS v10; // ebx
  __int64 v11; // rax
  __int64 v12; // rdx
  signed int v13; // eax
  int v14; // edx
  unsigned int v15; // r8d
  signed int v16; // eax
  int v17; // edx
  unsigned int v18; // r8d
  signed int v19; // eax
  int v20; // edx
  unsigned int v21; // r8d
  signed int v22; // eax
  int v23; // edx
  unsigned int v24; // r8d
  unsigned int phKey; // [rsp+20h] [rbp-60h]
  unsigned int phKeya; // [rsp+20h] [rbp-60h]
  int phKeyb; // [rsp+20h] [rbp-60h]
  int phKeyc; // [rsp+20h] [rbp-60h]
  void **v29; // [rsp+40h] [rbp-40h] BYREF
  PCCERT_CONTEXT v30; // [rsp+48h] [rbp-38h]
  void **v31; // [rsp+50h] [rbp-30h] BYREF
  BCRYPT_KEY_HANDLE hKey; // [rsp+58h] [rbp-28h] BYREF
  PUCHAR pbOutput; // [rsp+60h] [rbp-20h] BYREF
  int v34; // [rsp+68h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]
  ULONG pcbResult; // [rsp+A0h] [rbp+20h] BYREF
  void *v37; // [rsp+B0h] [rbp+30h] BYREF

  CertificateContext = CertCreateCertificateContext(0x10001u, *(const BYTE **)a1, *(_DWORD *)(a1 + 8) - *(_DWORD *)a1);
  v29 = &Microsoft::WRL::Wrappers::HandleT<CertContextTraits>::`vftable';
  v30 = CertificateContext;
  if ( !CertificateContext )
  {
    LastError = GetLastError();
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      wil::details::in1diag3::Log_Win32(
        retaddr,
        (void *)0x2617,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ops.cpp",
        (const char *)(unsigned int)LastError,
        phKey);
    }
    else if ( (unsigned int)dword_180122070 > 2 )
    {
      LODWORD(v37) = LastError;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_180122070,
        (unsigned __int8 *)&unk_180100B70,
        0,
        0,
        (__int64)&v37);
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v5 = HResultToSecurityStatus(LastError);
    v29 = &Microsoft::WRL::Wrappers::HandleT<CertContextTraits>::`vftable';
    return v5;
  }
  v31 = &Microsoft::WRL::Wrappers::HandleT<BCryptKeyHandleTraits>::`vftable';
  hKey = 0;
  Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v31);
  if ( !CryptImportPublicKeyInfoEx2(0x10001u, &v30->pCertInfo->SubjectPublicKeyInfo, 0, 0, &hKey) )
  {
    v7 = GetLastError();
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      wil::details::in1diag3::Log_Win32(
        retaddr,
        (void *)0x2630,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ops.cpp",
        (const char *)(unsigned int)v7,
        phKeya);
    }
    else if ( (unsigned int)dword_180122070 > 2 )
    {
      LODWORD(v37) = v7;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_180122070,
        (unsigned __int8 *)&unk_180100B30,
        0,
        0,
        (__int64)&v37);
    }
    if ( v7 > 0 )
      v7 = (unsigned __int16)v7 | 0x80070000;
    v5 = HResultToSecurityStatus(v7);
    v31 = &Microsoft::WRL::Wrappers::HandleT<BCryptKeyHandleTraits>::`vftable';
    Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v31);
    v29 = &Microsoft::WRL::Wrappers::HandleT<CertContextTraits>::`vftable';
    if ( v30 && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<CertContextTraits>::InternalClose(&v29) )
    {
      v16 = GetLastError();
      if ( v16 > 0 )
        v16 = (unsigned __int16)v16 | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v16, v17, v18);
      __debugbreak();
    }
    return v5;
  }
  pcbResult = 0;
  v8 = BCryptExportKey(hKey, 0, L"PUBLICBLOB", 0, 0, &pcbResult, 0);
  if ( v8 < 0 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      wil::details::in1diag3::Log_NtStatus(
        retaddr,
        (void *)0x264B,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ops.cpp",
        (const char *)(unsigned int)v8,
        phKeyb);
    }
    else if ( (unsigned int)dword_180122070 > 2 )
    {
      LODWORD(v37) = v8;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_180122070,
        (unsigned __int8 *)byte_180100AF7,
        0,
        0,
        (__int64)&v37);
    }
    v9 = HResultToSecurityStatus(v8 | 0x10000000u);
    v31 = &Microsoft::WRL::Wrappers::HandleT<BCryptKeyHandleTraits>::`vftable';
    Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v31);
    v29 = &Microsoft::WRL::Wrappers::HandleT<CertContextTraits>::`vftable';
    if ( v30 && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<CertContextTraits>::InternalClose(&v29) )
    {
      v22 = GetLastError();
      if ( v22 > 0 )
        v22 = (unsigned __int16)v22 | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v22, v23, v24);
      JUMPOUT(0x18007B1F1LL);
    }
    return v9;
  }
  std::vector<unsigned char>::vector<unsigned char>(&pbOutput, pcbResult);
  v10 = BCryptExportKey(hKey, 0, L"PUBLICBLOB", pbOutput, v34 - (_DWORD)pbOutput, &pcbResult, 0);
  if ( v10 < 0 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      wil::details::in1diag3::Log_NtStatus(
        retaddr,
        (void *)0x2666,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ops.cpp",
        (const char *)(unsigned int)v10,
        phKeyc);
    }
    else if ( (unsigned int)dword_180122070 > 2 )
    {
      LODWORD(v37) = v10;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_180122070,
        (unsigned __int8 *)&word_180100ABE,
        0,
        0,
        (__int64)&v37);
    }
    v9 = HResultToSecurityStatus(v10 | 0x10000000u);
    std::vector<unsigned char>::_Tidy(&pbOutput);
    v31 = &Microsoft::WRL::Wrappers::HandleT<BCryptKeyHandleTraits>::`vftable';
    Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v31);
    v29 = &Microsoft::WRL::Wrappers::HandleT<CertContextTraits>::`vftable';
    if ( v30 && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<CertContextTraits>::InternalClose(&v29) )
    {
      v19 = GetLastError();
      if ( v19 > 0 )
        v19 = (unsigned __int16)v19 | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v19, v20, v21);
      __debugbreak();
    }
    return v9;
  }
  v37 = operator new(0x38u);
  v11 = NgcUtils::RsaKey::RsaKey(v37, &pbOutput);
  v12 = *a2;
  *a2 = v11;
  if ( v12 )
    std::default_delete<NgcUtils::RsaKey>::operator()();
  std::vector<unsigned char>::_Tidy(&pbOutput);
  v31 = &Microsoft::WRL::Wrappers::HandleT<BCryptKeyHandleTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v31);
  v29 = &Microsoft::WRL::Wrappers::HandleT<CertContextTraits>::`vftable';
  if ( v30 && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<CertContextTraits>::InternalClose(&v29) )
  {
    v13 = GetLastError();
    if ( v13 > 0 )
      v13 = (unsigned __int16)v13 | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v13, v14, v15);
    __debugbreak();
  }
  return 0;
}

```

## disassembly

```asm
0x18007ad60  mov     [rsp-18h+arg_8], rbx
0x18007ad65  mov     [rsp-18h+arg_18], rdi
0x18007ad6a  push    rbp
0x18007ad6b  push    r14
0x18007ad6d  push    r15
0x18007ad6f  mov     rbp, rsp
0x18007ad72  sub     rsp, 80h
0x18007ad79  mov     rdi, rdx
0x18007ad7c  mov     r8d, [rcx+8]
0x18007ad80  sub     r8d, [rcx]; cbCertEncoded
0x18007ad83  mov     rdx, [rcx]; pbCertEncoded
0x18007ad86  mov     ebx, 10001h
0x18007ad8b  mov     ecx, ebx; dwCertEncodingType
0x18007ad8d  call    cs:__imp_CertCreateCertificateContext
0x18007ad93  lea     r14, ??_7?$HandleT@UCertContextTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CertContextTraits>::`vftable'
0x18007ad9a  mov     [rbp+var_40], r14
0x18007ad9e  mov     [rbp+var_38], rax
0x18007ada2  test    rax, rax
0x18007ada5  jnz     loc_18007AE47
0x18007adab  call    cs:__imp_GetLastError
0x18007adb1  mov     edi, eax
0x18007adb3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x18007adba  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18007adbf  test    al, al
0x18007adc1  jz      short loc_18007ADDD
0x18007adc3  mov     rcx, [rbp+18h]; this
0x18007adc7  mov     r9d, edi; char *
0x18007adca  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x18007add1  mov     edx, 2617h; void *
0x18007add6  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18007addb  jmp     short loc_18007AE0D
0x18007addd  mov     eax, cs:dword_180122070
0x18007ade3  cmp     eax, 2
0x18007ade6  jbe     short loc_18007AE0D
0x18007ade8  mov     dword ptr [rbp+arg_10], edi
0x18007adeb  lea     rax, [rbp+arg_10]
0x18007adef  mov     [rsp+80h+phKey], rax
0x18007adf4  xor     r9d, r9d
0x18007adf7  xor     r8d, r8d
0x18007adfa  lea     rdx, unk_180100B70
0x18007ae01  lea     rcx, dword_180122070
0x18007ae08  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18007ae0d  mov     ebx, 80070000h
0x18007ae12  test    edi, edi
0x18007ae14  jle     short loc_18007AE1B
0x18007ae16  movzx   edi, di
0x18007ae19  or      edi, ebx
0x18007ae1b  mov     ecx, edi; int
0x18007ae1d  call    ?HResultToSecurityStatus@@YAJJ@Z; HResultToSecurityStatus(long)
0x18007ae22  mov     edi, eax
0x18007ae24  mov     [rbp+var_40], r14
0x18007ae28  cmp     [rbp+var_38], 0
0x18007ae2d  jz      short loc_18007AE40
0x18007ae2f  lea     rcx, [rbp+var_40]
0x18007ae33  call    ?InternalClose@?$HandleT@UCertContextTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<CertContextTraits>::InternalClose(void)
0x18007ae38  test    al, al
0x18007ae3a  jz      loc_18007B1C1
0x18007ae40  mov     eax, edi
0x18007ae42  jmp     loc_18007B15D
0x18007ae47  lea     r15, ??_7?$HandleT@UBCryptKeyHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<BCryptKeyHandleTraits>::`vftable'
0x18007ae4e  mov     [rbp+var_30], r15
0x18007ae52  mov     [rbp+hKey], 0
0x18007ae5a  lea     rcx, [rbp+var_30]
0x18007ae5e  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x18007ae63  mov     rax, [rbp+var_38]
0x18007ae67  mov     rdx, [rax+18h]
0x18007ae6b  add     rdx, 60h ; '`'; pInfo
0x18007ae6f  lea     rax, [rbp+hKey]
0x18007ae73  mov     [rsp+80h+phKey], rax; unsigned int
0x18007ae78  xor     r9d, r9d; pvAuxInfo
0x18007ae7b  xor     r8d, r8d; dwFlags
0x18007ae7e  mov     ecx, ebx; dwCertEncodingType
0x18007ae80  call    cs:__imp_CryptImportPublicKeyInfoEx2
0x18007ae86  test    eax, eax
0x18007ae88  jnz     loc_18007AF3A
0x18007ae8e  call    cs:__imp_GetLastError
0x18007ae94  mov     edi, eax
0x18007ae96  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x18007ae9d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18007aea2  test    al, al
0x18007aea4  jz      short loc_18007AEC0
0x18007aea6  mov     rcx, [rbp+18h]; this
0x18007aeaa  mov     r9d, edi; char *
0x18007aead  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x18007aeb4  mov     edx, 2630h; void *
0x18007aeb9  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18007aebe  jmp     short loc_18007AEF0
0x18007aec0  mov     eax, cs:dword_180122070
0x18007aec6  cmp     eax, 2
0x18007aec9  jbe     short loc_18007AEF0
0x18007aecb  mov     dword ptr [rbp+arg_10], edi
0x18007aece  lea     rax, [rbp+arg_10]
0x18007aed2  mov     [rsp+80h+phKey], rax
0x18007aed7  xor     r9d, r9d
0x18007aeda  xor     r8d, r8d
0x18007aedd  lea     rdx, unk_180100B30
0x18007aee4  lea     rcx, dword_180122070
0x18007aeeb  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18007aef0  mov     ebx, 80070000h
0x18007aef5  test    edi, edi
0x18007aef7  jle     short loc_18007AEFE
0x18007aef9  movzx   edi, di
0x18007aefc  or      edi, ebx
0x18007aefe  mov     ecx, edi; int
0x18007af00  call    ?HResultToSecurityStatus@@YAJJ@Z; HResultToSecurityStatus(long)
0x18007af05  mov     edi, eax
0x18007af07  mov     [rbp+var_30], r15
0x18007af0b  lea     rcx, [rbp+var_30]
0x18007af0f  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x18007af14  nop
0x18007af15  mov     [rbp+var_40], r14
0x18007af19  cmp     [rbp+var_38], 0
0x18007af1e  jz      loc_18007AE40
0x18007af24  lea     rcx, [rbp+var_40]
0x18007af28  call    ?InternalClose@?$HandleT@UCertContextTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<CertContextTraits>::InternalClose(void)
0x18007af2d  test    al, al
0x18007af2f  jz      loc_18007B190
0x18007af35  jmp     loc_18007AE40
0x18007af3a  mov     [rbp+arg_0], 0
0x18007af41  mov     [rsp+80h+dwFlags], 0; dwFlags
0x18007af49  lea     rax, [rbp+arg_0]
0x18007af4d  mov     [rsp+80h+pcbResult], rax; pcbResult
0x18007af52  mov     dword ptr [rsp+80h+phKey], 0; int
0x18007af5a  xor     r9d, r9d; pbOutput
0x18007af5d  lea     r8, aPublicblob; "PUBLICBLOB"
0x18007af64  xor     edx, edx; hExportKey
0x18007af66  mov     rcx, [rbp+hKey]; hKey
0x18007af6a  call    cs:__imp_BCryptExportKey
0x18007af70  mov     ebx, eax
0x18007af72  test    eax, eax
0x18007af74  jns     loc_18007B012
0x18007af7a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x18007af81  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18007af86  test    al, al
0x18007af88  jz      short loc_18007AFA4
0x18007af8a  mov     rcx, [rbp+18h]; this
0x18007af8e  mov     r9d, ebx; char *
0x18007af91  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x18007af98  mov     edx, 264Bh; void *
0x18007af9d  call    ?Log_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_NtStatus(void *,uint,char const *,long)
0x18007afa2  jmp     short loc_18007AFD4
0x18007afa4  mov     eax, cs:dword_180122070
0x18007afaa  cmp     eax, 2
0x18007afad  jbe     short loc_18007AFD4
0x18007afaf  mov     dword ptr [rbp+arg_10], ebx
0x18007afb2  lea     rax, [rbp+arg_10]
0x18007afb6  mov     [rsp+80h+phKey], rax
0x18007afbb  xor     r9d, r9d
0x18007afbe  xor     r8d, r8d
0x18007afc1  lea     rdx, byte_180100AF7
0x18007afc8  lea     rcx, dword_180122070
0x18007afcf  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18007afd4  bts     ebx, 1Ch
0x18007afd8  mov     ecx, ebx; int
0x18007afda  call    ?HResultToSecurityStatus@@YAJJ@Z; HResultToSecurityStatus(long)
0x18007afdf  mov     ebx, eax
0x18007afe1  mov     [rbp+var_30], r15
0x18007afe5  lea     rcx, [rbp+var_30]
0x18007afe9  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x18007afee  nop
0x18007afef  mov     [rbp+var_40], r14
0x18007aff3  cmp     [rbp+var_38], 0
0x18007aff8  jz      short loc_18007B00B
0x18007affa  lea     rcx, [rbp+var_40]
0x18007affe  call    ?InternalClose@?$HandleT@UCertContextTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<CertContextTraits>::InternalClose(void)
0x18007b003  test    al, al
0x18007b005  jz      loc_18007B1D8
0x18007b00b  mov     eax, ebx
0x18007b00d  jmp     loc_18007B15D
0x18007b012  mov     edx, [rbp+arg_0]
0x18007b015  lea     rcx, [rbp+pbOutput]
0x18007b019  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18007b01e  nop
0x18007b01f  mov     eax, [rbp+var_18]
0x18007b022  mov     r9, [rbp+pbOutput]; pbOutput
0x18007b026  sub     eax, r9d
0x18007b029  mov     [rsp+80h+dwFlags], 0; dwFlags
0x18007b031  lea     rcx, [rbp+arg_0]
0x18007b035  mov     [rsp+80h+pcbResult], rcx; pcbResult
0x18007b03a  mov     dword ptr [rsp+80h+phKey], eax; int
0x18007b03e  lea     r8, aPublicblob; "PUBLICBLOB"
0x18007b045  xor     edx, edx; hExportKey
0x18007b047  mov     rcx, [rbp+hKey]; hKey
0x18007b04b  call    cs:__imp_BCryptExportKey
0x18007b051  mov     ebx, eax
0x18007b053  test    eax, eax
0x18007b055  jns     loc_18007B0FF
0x18007b05b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x18007b062  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18007b067  test    al, al
0x18007b069  jz      short loc_18007B085
0x18007b06b  mov     rcx, [rbp+18h]; this
0x18007b06f  mov     r9d, ebx; char *
0x18007b072  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x18007b079  mov     edx, 2666h; void *
0x18007b07e  call    ?Log_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_NtStatus(void *,uint,char const *,long)
0x18007b083  jmp     short loc_18007B0B5
0x18007b085  mov     eax, cs:dword_180122070
0x18007b08b  cmp     eax, 2
0x18007b08e  jbe     short loc_18007B0B5
0x18007b090  mov     dword ptr [rbp+arg_10], ebx
0x18007b093  lea     rax, [rbp+arg_10]
0x18007b097  mov     [rsp+80h+phKey], rax
0x18007b09c  xor     r9d, r9d
0x18007b09f  xor     r8d, r8d
0x18007b0a2  lea     rdx, word_180100ABE
0x18007b0a9  lea     rcx, dword_180122070
0x18007b0b0  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18007b0b5  bts     ebx, 1Ch
0x18007b0b9  mov     ecx, ebx; int
0x18007b0bb  call    ?HResultToSecurityStatus@@YAJJ@Z; HResultToSecurityStatus(long)
0x18007b0c0  mov     ebx, eax
0x18007b0c2  lea     rcx, [rbp+pbOutput]
0x18007b0c6  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18007b0cb  nop
0x18007b0cc  mov     [rbp+var_30], r15
0x18007b0d0  lea     rcx, [rbp+var_30]
0x18007b0d4  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x18007b0d9  nop
0x18007b0da  mov     [rbp+var_40], r14
0x18007b0de  cmp     [rbp+var_38], 0
0x18007b0e3  jz      loc_18007B00B
0x18007b0e9  lea     rcx, [rbp+var_40]
0x18007b0ed  call    ?InternalClose@?$HandleT@UCertContextTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<CertContextTraits>::InternalClose(void)
0x18007b0f2  test    al, al
0x18007b0f4  jz      loc_18007B1A7
0x18007b0fa  jmp     loc_18007B00B
0x18007b0ff  mov     ecx, 38h ; '8'; Size
0x18007b104  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007b109  mov     [rbp+arg_10], rax
0x18007b10d  lea     rdx, [rbp+pbOutput]
0x18007b111  mov     rcx, rax
0x18007b114  call    ??0RsaKey@NgcUtils@@QEAA@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z; NgcUtils::RsaKey::RsaKey(std::vector<uchar> const &)
0x18007b119  nop
0x18007b11a  mov     rdx, [rdi]
0x18007b11d  mov     [rdi], rax
0x18007b120  test    rdx, rdx
0x18007b123  jz      short loc_18007B12B
0x18007b125  call    ??R?$default_delete@URsaKey@NgcUtils@@@std@@QEBAXPEAURsaKey@NgcUtils@@@Z; std::default_delete<NgcUtils::RsaKey>::operator()(NgcUtils::RsaKey *)
0x18007b12a  nop
0x18007b12b  lea     rcx, [rbp+pbOutput]
0x18007b12f  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18007b134  nop
0x18007b135  mov     [rbp+var_30], r15
0x18007b139  lea     rcx, [rbp+var_30]
0x18007b13d  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x18007b142  nop
0x18007b143  mov     [rbp+var_40], r14
0x18007b147  cmp     [rbp+var_38], 0
0x18007b14c  jz      short loc_18007B15B
0x18007b14e  lea     rcx, [rbp+var_40]
0x18007b152  call    ?InternalClose@?$HandleT@UCertContextTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<CertContextTraits>::InternalClose(void)
0x18007b157  test    al, al
0x18007b159  jz      short loc_18007B176
0x18007b15b  xor     eax, eax
0x18007b15d  lea     r11, [rsp+80h+var_s0]
0x18007b165  mov     rbx, [r11+28h]
0x18007b169  mov     rdi, [r11+38h]
0x18007b16d  mov     rsp, r11
0x18007b170  pop     r15
0x18007b172  pop     r14
0x18007b174  pop     rbp
0x18007b175  retn
0x18007b176  call    cs:__imp_GetLastError
0x18007b17c  test    eax, eax
0x18007b17e  jle     short loc_18007B188
0x18007b180  movzx   eax, ax
0x18007b183  or      eax, 80070000h
0x18007b188  mov     ecx, eax; this
0x18007b18a  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18007b18f  int     3; Trap to Debugger
0x18007b190  call    cs:__imp_GetLastError
0x18007b196  test    eax, eax
0x18007b198  jle     short loc_18007B19F
0x18007b19a  movzx   eax, ax
0x18007b19d  or      eax, ebx
0x18007b19f  mov     ecx, eax; this
0x18007b1a1  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18007b1a6  int     3; Trap to Debugger
0x18007b1a7  call    cs:__imp_GetLastError
0x18007b1ad  test    eax, eax
0x18007b1af  jle     short loc_18007B1B9
0x18007b1b1  movzx   eax, ax
0x18007b1b4  or      eax, 80070000h
0x18007b1b9  mov     ecx, eax; this
0x18007b1bb  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18007b1c0  int     3; Trap to Debugger
0x18007b1c1  call    cs:__imp_GetLastError
0x18007b1c7  test    eax, eax
0x18007b1c9  jle     short loc_18007B1D0
0x18007b1cb  movzx   eax, ax
0x18007b1ce  or      eax, ebx
0x18007b1d0  mov     ecx, eax; this
0x18007b1d2  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18007b1d7  int     3; Trap to Debugger
0x18007b1d8  call    cs:__imp_GetLastError
0x18007b1de  test    eax, eax
0x18007b1e0  jle     short loc_18007B1EA
0x18007b1e2  movzx   eax, ax
0x18007b1e5  or      eax, 80070000h
  ... truncated ...
```
