# NgcKspServer::NgcUserIdKey::FidoSignHelper(_NGC_RPC_GESTURE_INFO const &,unsigned __int64,NgcKspServer::NgcUserIdKey::NgcSignPaddingOperationData const &,std::vector<uchar,std::allocator<uchar>> *)

- ea: `0x18007a048`
- end: `0x18007a768`
- name: `?FidoSignHelper@NgcUserIdKey@NgcKspServer@@AEAAJAEBU_NGC_RPC_GESTURE_INFO@@_KAEBUNgcSignPaddingOperationData@12@PEAV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `1824`
- prototype: `__int64 __usercall@<rax>(NgcKspServer::NgcUserIdKey *this@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180078510`

## callees

- `0x18000782c`
- `0x180007964`
- `0x180010990`
- `0x180016400`
- `0x180022b00`
- `0x180028900`
- `0x180028ca0`
- `0x180028d18`
- `0x180031c3c`
- `0x180046d90`
- `0x180048394`
- `0x180059108`
- `0x180059404`
- `0x18005cee0`
- `0x1800649b4`
- `0x180065268`
- `0x180065284`
- `0x180076020`
- `0x180079e88`
- `0x18007a048`
- `0x18007d288`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007a374`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007a391`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007a3b4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007a374`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007a391`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007a3b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a16a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007a16a`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18007a15d`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18007a228`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18007a15d`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18007a228`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007a1e7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007a1e7`
- `bcrypt!BCryptHash` at `0x18007a46a`
- `bcrypt!BCryptHash` at `0x18007a46a`
- `webauthn!WebAuthNDecodeAccountInformation` at `0x18007a0ee`
- `webauthn!WebAuthNDecodeAccountInformation` at `0x18007a0ee`

## string_xrefs

- `0x18007a09d`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`
- `0x18007a104`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`
- `0x18007a18c`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`
- `0x18007a239`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`
- `0x18007a2c1`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`
- `0x18007a31e`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`
- `0x18007a3f1`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`
- `0x18007a480`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`
- `0x18007a4ec`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`
- `0x18007a5bc`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`
- `0x18007a65c`: `onecore\ds\security\ngc\kspsvc\svc\ops.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall NgcKspServer::NgcUserIdKey::FidoSignHelper(
        CHAR *this,
        const struct _NGC_RPC_GESTURE_INFO *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  DWORD IncrementedSignCount; // ebx
  int v7; // r12d
  __int64 v8; // rdx
  int v9; // eax
  const WCHAR *v10; // r8
  __int64 v11; // rdi
  __int64 v12; // r9
  int v13; // eax
  int v14; // r15d
  CHAR *v15; // rbx
  const WCHAR *v16; // r8
  __int64 v17; // r9
  const char *v18; // r9
  __int64 *v19; // rcx
  __int64 v20; // rax
  int v21; // eax
  DWORD v22; // r14d
  __int64 v23; // r14
  const WCHAR *v24; // rdi
  int v25; // eax
  const struct _FIDO_AUTHENTICATOR_USER_VERIFICATION_METHOD_FACTOR *v26; // r9
  int HashLen; // eax
  __int64 v28; // rdx
  const struct _FIDO_AUTHENTICATOR_USER_VERIFICATION_METHOD_FACTOR *v29; // r9
  int HashedData; // eax
  int v31; // eax
  int lpMultiByteStr; // [rsp+20h] [rbp-E0h]
  int lpMultiByteStra; // [rsp+20h] [rbp-E0h]
  LPSTR lpMultiByteStrb; // [rsp+20h] [rbp-E0h]
  LPSTR lpMultiByteStrc; // [rsp+20h] [rbp-E0h]
  int lpMultiByteStrd; // [rsp+20h] [rbp-E0h]
  const struct _WEBAUTHN_EXTENSIONS *cbMultiByte; // [rsp+28h] [rbp-D8h]
  LPCCH lpDefaultChar; // [rsp+30h] [rbp-D0h]
  unsigned int v40; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v41; // [rsp+74h] [rbp-8Ch] BYREF
  _QWORD v42[2]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int8 *v43[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v44; // [rsp+98h] [rbp-68h]
  __int64 v45; // [rsp+A0h] [rbp-60h] BYREF
  _DWORD v46[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v47; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v48; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v49; // [rsp+C8h] [rbp-38h]
  __int128 v50; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v51; // [rsp+E0h] [rbp-20h]
  char v52[8]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v53; // [rsp+F0h] [rbp-10h]
  unsigned __int8 *v54; // [rsp+100h] [rbp+0h] BYREF
  int v55; // [rsp+108h] [rbp+8h]
  __int64 v56; // [rsp+118h] [rbp+18h]
  __int64 v57; // [rsp+120h] [rbp+20h]
  unsigned __int8 v58[16]; // [rsp+128h] [rbp+28h] BYREF
  __int128 v59; // [rsp+138h] [rbp+38h]
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v56 = a4;
  v47 = a3;
  v57 = a5;
  IncrementedSignCount = NgcKspServer::NgcUserIdKey::RsaFidoBuildUvmData(
                           (NgcKspServer::NgcUserIdKey *)this,
                           a2,
                           (struct NgcKspServer::NgcUserIdKey::NgcFidoUvmData *)v42);
  v7 = 0;
  if ( (IncrementedSignCount & 0x80000000) == 0 )
  {
    v41 = 0;
    IncrementedSignCount = NgcKspServer::NgcUserIdKey::FidoGetIncrementedSignCount(
                             (NgcKspServer::NgcUserIdKey *)this,
                             &v41);
    if ( (IncrementedSignCount & 0x80000000) != 0 )
    {
      v8 = 8369;
      goto LABEL_3;
    }
    v45 = 0;
    v9 = WebAuthNDecodeAccountInformation(
           *((_DWORD *)this + 104) - (unsigned int)*((_QWORD *)this + 51),
           *((_QWORD *)this + 51),
           &v45);
    IncrementedSignCount = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x20B7,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ops.cpp",
        (const char *)(unsigned int)v9,
        lpMultiByteStr);
LABEL_56:
      wil::details::unique_storage<wil::details::resource_policy<_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,void (*)(_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *),&void WebAuthNFreeDecodedAccountInformation(_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,void (*)(_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *),&void WebAuthNFreeDecodedAccountInformation(_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,0,std::nullptr_t>>(&v45);
      return IncrementedSignCount;
    }
    v10 = *(const WCHAR **)(*(_QWORD *)(v45 + 8) + 8LL);
    v11 = -1;
    v12 = -1;
    do
      ++v12;
    while ( v10[v12] );
    v13 = WideCharToMultiByte(0xFDE9u, 0x80u, v10, v12, 0, 0, 0, 0);
    v14 = v13;
    if ( !v13 )
    {
      IncrementedSignCount = GetLastError();
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
      {
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x20CA,
          (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ops.cpp",
          (const char *)IncrementedSignCount,
          lpMultiByteStra);
      }
      else if ( (unsigned int)dword_180122070 > 2 )
      {
        v41 = IncrementedSignCount;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_180122070,
          (unsigned __int8 *)&dword_18010103C,
          0,
          0,
          (__int64)&v41);
      }
      goto LABEL_56;
    }
    v15 = (CHAR *)LocalAlloc(0x40u, v13 + 1);
    v42[0] = v15;
    v16 = *(const WCHAR **)(*(_QWORD *)(v45 + 8) + 8LL);
    v17 = -1;
    do
      ++v17;
    while ( v16[v17] );
    if ( !WideCharToMultiByte(0xFDE9u, 0x80u, v16, v17, v15, v14, 0, 0) )
    {
      IncrementedSignCount = wil::details::in1diag3::Return_GetLastError(
                               retaddr,
                               (void *)0x20DF,
                               (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ops.cpp",
                               v18);
LABEL_19:
      wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(v42);
      goto LABEL_56;
    }
    v48 = 0;
    v49 = 0;
    v19 = (__int64 *)*((_QWORD *)this + 44);
    v20 = *v19;
    v40 = 8;
    lpMultiByteStrb = this + 104;
    v21 = (*(__int64 (__fastcall **)(__int64 *, CHAR *, CHAR *, CHAR *))(v20 + 216))(
            v19,
            this + 56,
            this + 136,
            this + 72);
    v22 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x20E8,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ops.cpp",
        (const char *)(unsigned int)v21,
        (int)lpMultiByteStrb);
      std::vector<unsigned char>::_Tidy(&v48);
      wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(v42);
      IncrementedSignCount = v22;
      goto LABEL_56;
    }
    v23 = v48;
    do
      ++v11;
    while ( *(_WORD *)(v48 + 2 * v11) );
    if ( !v11 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
      {
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x20EF,
          (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ops.cpp",
          0,
          (int)lpMultiByteStrb);
      }
      else if ( (unsigned int)dword_180122070 > 2 )
      {
        v40 = HResultToSecurityStatus(0);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_180122070,
          (unsigned __int8 *)&unk_180101000,
          0,
          0,
          (__int64)&v40);
      }
    }
    if ( (unsigned int)_o__wcsicmp(v23, L"ECDSA_P256") )
    {
      if ( (unsigned int)_o__wcsicmp(v23, L"ECDSA_P384") )
      {
        if ( (unsigned int)_o__wcsicmp(v23, L"ECDSA_P521") )
        {
          v24 = &sourceString;
          v7 = -2146893783;
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
          {
            wil::details::in1diag3::Log_Hr(
              retaddr,
              (void *)0x210B,
              (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ops.cpp",
              (const char *)0x80090029LL,
              (int)lpMultiByteStrb);
          }
          else if ( (unsigned int)dword_180122070 > 2 )
          {
            v40 = HResultToSecurityStatus(-2146893783);
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
              (__int64)&dword_180122070,
              (unsigned __int8 *)&dword_180100FC4,
              0,
              0,
              (__int64)&v40);
          }
        }
        else
        {
          v24 = L"SHA512";
        }
      }
      else
      {
        v24 = L"SHA384";
      }
    }
    else
    {
      v24 = L"SHA256";
    }
    *(_OWORD *)v58 = 0;
    v59 = 0;
    LODWORD(lpMultiByteStrb) = v14;
    v25 = BCryptHash(65, 0, 0, v15);
    IncrementedSignCount = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2124,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ops.cpp",
        (const char *)(unsigned int)v25,
        v14);
LABEL_41:
      std::vector<unsigned char>::_Tidy(&v48);
      goto LABEL_19;
    }
    *(_OWORD *)v43 = 0;
    v44 = 0;
    v40 = 0;
    HashLen = FidoAuthenticatorGenerateAuthenticatorData(
                v58,
                0x20u,
                v41,
                v26,
                (size_t)lpMultiByteStrb,
                (const struct _WEBAUTHN_EXTENSIONS *)v58,
                0,
                &v40);
    IncrementedSignCount = HashLen;
    if ( HashLen >= 0 )
    {
      std::vector<unsigned char>::_Resize<std::_Value_init_tag>(v43, v40);
      HashLen = FidoAuthenticatorGenerateAuthenticatorData(
                  v58,
                  0x20u,
                  v41,
                  v29,
                  (size_t)lpMultiByteStrc,
                  cbMultiByte,
                  v43[0],
                  &v40);
      IncrementedSignCount = HashLen;
      if ( HashLen >= 0 )
      {
        v41 = 0;
        HashLen = GetHashLen(v24, &v41);
        IncrementedSignCount = HashLen;
        if ( HashLen >= 0 )
        {
          std::vector<unsigned char>::vector<unsigned char>(&v54, v41);
          LODWORD(lpDefaultChar) = v55 - (_DWORD)v54;
          HashedData = FidoAuthenticatorGenerateHashedData(
                         v24,
                         **(const unsigned __int8 ***)(v56 + 8),
                         *(_DWORD *)(*(_QWORD *)(v56 + 8) + 8LL) - (unsigned int)**(_QWORD **)(v56 + 8),
                         v43[0],
                         LODWORD(v43[1]) - LODWORD(v43[0]),
                         v54,
                         (size_t)lpDefaultChar);
          IncrementedSignCount = HashedData;
          if ( HashedData >= 0 )
          {
            v50 = 0;
            v51 = 0;
            v31 = (*(__int64 (__fastcall **)(_QWORD, CHAR *, CHAR *, CHAR *))(**((_QWORD **)this + 44) + 88LL))(
                    *((_QWORD *)this + 44),
                    this + 56,
                    this + 136,
                    this + 72);
            IncrementedSignCount = v31;
            if ( v31 >= 0 )
            {
              v46[0] = LODWORD(v43[1]) - LODWORD(v43[0]);
              v46[1] = DWORD2(v50) - v50;
              std::vector<unsigned char>::vector<unsigned char>(v52, *((_QWORD *)&v50 + 1) - v50 + v43[1] - v43[0] + 8);
              std::vector<unsigned char>::assign<unsigned char *,0>(v52, v46, &v47);
              std::vector<unsigned char>::insert<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<unsigned char>>>,0>(
                (unsigned int)v52,
                (unsigned int)&v47,
                v53,
                v43[0],
                (__int64)v43[1]);
              std::vector<unsigned char>::insert<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<unsigned char>>>,0>(
                (unsigned int)v52,
                (unsigned int)&v47,
                v53,
                v50,
                *((__int64 *)&v50 + 1));
              std::vector<unsigned char>::operator=(v57, v52);
              std::vector<unsigned char>::_Tidy(v52);
              std::vector<unsigned char>::_Tidy(&v50);
              std::vector<unsigned char>::_Tidy(&v54);
              std::vector<unsigned char>::_Tidy(v43);
              std::vector<unsigned char>::_Tidy(&v48);
              wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(v42);
              IncrementedSignCount = v7;
              goto LABEL_56;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2159,
              (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ops.cpp",
              (const char *)(unsigned int)v31,
              (_DWORD)this + 104);
            std::vector<unsigned char>::_Tidy(&v50);
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x214B,
              (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ops.cpp",
              (const char *)(unsigned int)HashedData,
              lpMultiByteStrd);
          }
          std::vector<unsigned char>::_Tidy(&v54);
          goto LABEL_45;
        }
        v28 = 8513;
      }
      else
      {
        v28 = 8507;
      }
    }
    else
    {
      v28 = 8496;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v28,
      (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ops.cpp",
      (const char *)(unsigned int)HashLen,
      (int)lpMultiByteStrc);
LABEL_45:
    std::vector<unsigned char>::_Tidy(v43);
    goto LABEL_41;
  }
  v8 = 8360;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ops.cpp",
    (const char *)IncrementedSignCount,
    lpMultiByteStr);
  return IncrementedSignCount;
}

```

## disassembly

```asm
0x18007a048  push    rbp
0x18007a04a  push    rbx
0x18007a04b  push    rsi
0x18007a04c  push    rdi
0x18007a04d  push    r12
0x18007a04f  push    r13
0x18007a051  push    r14
0x18007a053  push    r15
0x18007a055  lea     rbp, [rsp-58h]
0x18007a05a  sub     rsp, 158h
0x18007a061  mov     rax, cs:__security_cookie
0x18007a068  xor     rax, rsp
0x18007a06b  mov     [rbp+90h+var_48], rax
0x18007a06f  mov     [rbp+90h+var_78], r9
0x18007a073  mov     [rbp+90h+var_E0], r8
0x18007a077  mov     rsi, rcx
0x18007a07a  mov     rax, [rbp+90h+arg_20]
0x18007a081  mov     [rbp+90h+var_70], rax
0x18007a085  lea     r8, [rsp+190h+var_118]; struct NgcKspServer::NgcUserIdKey::NgcFidoUvmData *
0x18007a08a  call    ?RsaFidoBuildUvmData@NgcUserIdKey@NgcKspServer@@AEAA?BJAEBU_NGC_RPC_GESTURE_INFO@@PEAUNgcFidoUvmData@12@@Z; NgcKspServer::NgcUserIdKey::RsaFidoBuildUvmData(_NGC_RPC_GESTURE_INFO const &,NgcKspServer::NgcUserIdKey::NgcFidoUvmData *)
0x18007a08f  mov     ebx, eax
0x18007a091  xor     r12d, r12d
0x18007a094  test    eax, eax
0x18007a096  jns     short loc_18007A0B8
0x18007a098  mov     edx, 20A8h; void *
0x18007a09d  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x18007a0a4  mov     r9d, ebx; char *
0x18007a0a7  mov     rcx, [rbp+98h]; this
0x18007a0ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a0b3  jmp     loc_18007A746
0x18007a0b8  mov     [rsp+190h+var_11C], r12d
0x18007a0bd  lea     rdx, [rsp+190h+var_11C]; unsigned int *
0x18007a0c2  mov     rcx, rsi; this
0x18007a0c5  call    ?FidoGetIncrementedSignCount@NgcUserIdKey@NgcKspServer@@AEAAJPEAK@Z; NgcKspServer::NgcUserIdKey::FidoGetIncrementedSignCount(ulong *)
0x18007a0ca  mov     ebx, eax
0x18007a0cc  test    eax, eax
0x18007a0ce  jns     short loc_18007A0D7
0x18007a0d0  mov     edx, 20B1h
0x18007a0d5  jmp     short loc_18007A09D
0x18007a0d7  mov     [rbp+90h+var_F0], r12
0x18007a0db  mov     rdx, [rsi+198h]
0x18007a0e2  mov     ecx, [rsi+1A0h]
0x18007a0e8  sub     ecx, edx
0x18007a0ea  lea     r8, [rbp+90h+var_F0]
0x18007a0ee  call    cs:__imp_WebAuthNDecodeAccountInformation
0x18007a0f4  mov     ebx, eax
0x18007a0f6  test    eax, eax
0x18007a0f8  jns     short loc_18007A11A
0x18007a0fa  mov     rcx, [rbp+98h]; this
0x18007a101  mov     r9d, eax; char *
0x18007a104  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x18007a10b  mov     edx, 20B7h; void *
0x18007a110  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a115  jmp     loc_18007A73D
0x18007a11a  mov     rax, [rbp+90h+var_F0]
0x18007a11e  mov     rcx, [rax+8]
0x18007a122  mov     r8, [rcx+8]; lpWideCharStr
0x18007a126  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18007a12a  mov     r9, rdi
0x18007a12d  inc     r9; cchWideChar
0x18007a130  cmp     [r8+r9*2], r12w
0x18007a135  jnz     short loc_18007A12D
0x18007a137  mov     [rsp+190h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x18007a13c  mov     [rsp+190h+lpDefaultChar], r12; lpDefaultChar
0x18007a141  mov     [rsp+190h+cbMultiByte], r12d; cbMultiByte
0x18007a146  mov     [rsp+190h+lpMultiByteStr], r12; int
0x18007a14b  mov     r14d, 80h
0x18007a151  mov     edx, r14d; dwFlags
0x18007a154  mov     r13d, 0FDE9h
0x18007a15a  mov     ecx, r13d; CodePage
0x18007a15d  call    cs:__imp_WideCharToMultiByte
0x18007a163  mov     r15d, eax
0x18007a166  test    eax, eax
0x18007a168  jnz     short loc_18007A1DD
0x18007a16a  call    cs:__imp_GetLastError
0x18007a170  mov     ebx, eax
0x18007a172  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x18007a179  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18007a17e  test    al, al
0x18007a180  jz      short loc_18007A1A2
0x18007a182  mov     rcx, [rbp+98h]; this
0x18007a189  mov     r9d, ebx; char *
0x18007a18c  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x18007a193  mov     edx, 20CAh; void *
0x18007a198  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18007a19d  jmp     loc_18007A73D
0x18007a1a2  mov     eax, cs:dword_180122070
0x18007a1a8  cmp     eax, 2
0x18007a1ab  jbe     loc_18007A73D
0x18007a1b1  mov     [rsp+190h+var_11C], ebx
0x18007a1b5  lea     rax, [rsp+190h+var_11C]
0x18007a1ba  mov     [rsp+190h+lpMultiByteStr], rax
0x18007a1bf  xor     r9d, r9d
0x18007a1c2  xor     r8d, r8d
0x18007a1c5  lea     rdx, dword_18010103C
0x18007a1cc  lea     rcx, dword_180122070
0x18007a1d3  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18007a1d8  jmp     loc_18007A73D
0x18007a1dd  inc     eax
0x18007a1df  movsxd  rdx, eax; uBytes
0x18007a1e2  mov     ecx, 40h ; '@'; uFlags
0x18007a1e7  call    cs:__imp_LocalAlloc
0x18007a1ed  mov     rbx, rax
0x18007a1f0  mov     [rsp+190h+var_118], rax
0x18007a1f5  mov     rax, [rbp+90h+var_F0]
0x18007a1f9  mov     rcx, [rax+8]
0x18007a1fd  mov     r8, [rcx+8]; lpWideCharStr
0x18007a201  mov     r9, rdi
0x18007a204  inc     r9; cchWideChar
0x18007a207  cmp     [r8+r9*2], r12w
0x18007a20c  jnz     short loc_18007A204
0x18007a20e  mov     [rsp+190h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x18007a213  mov     [rsp+190h+lpDefaultChar], r12; lpDefaultChar
0x18007a218  mov     [rsp+190h+cbMultiByte], r15d; cbMultiByte
0x18007a21d  mov     [rsp+190h+lpMultiByteStr], rbx; lpMultiByteStr
0x18007a222  mov     edx, r14d; dwFlags
0x18007a225  mov     ecx, r13d; CodePage
0x18007a228  call    cs:__imp_WideCharToMultiByte
0x18007a22e  test    eax, eax
0x18007a230  jnz     short loc_18007A25B
0x18007a232  mov     rcx, [rbp+98h]; this
0x18007a239  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x18007a240  mov     edx, 20DFh; void *
0x18007a245  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18007a24a  mov     ebx, eax
0x18007a24c  lea     rcx, [rsp+190h+var_118]
0x18007a251  call    ??1?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?FidoFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(void)
0x18007a256  jmp     loc_18007A73D
0x18007a25b  xorps   xmm0, xmm0
0x18007a25e  movdqu  [rbp+90h+var_D8], xmm0
0x18007a263  mov     [rbp+90h+var_C8], r12
0x18007a267  mov     rcx, [rsi+160h]
0x18007a26e  mov     rax, [rcx]
0x18007a271  mov     [rsp+190h+var_120], 8
0x18007a279  lea     r13, [rsi+68h]
0x18007a27d  lea     r8, [rsi+88h]
0x18007a284  lea     r9, [rbp+90h+var_D8]
0x18007a288  mov     [rsp+190h+lpDefaultChar], r9
0x18007a28d  lea     r9, [rsp+190h+var_120]
0x18007a292  mov     qword ptr [rsp+190h+cbMultiByte], r9
0x18007a297  mov     [rsp+190h+lpMultiByteStr], r13; int
0x18007a29c  lea     r9, [rsi+48h]
0x18007a2a0  lea     rdx, [rsi+38h]
0x18007a2a4  mov     rax, [rax+0D8h]
0x18007a2ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a2b0  mov     r14d, eax
0x18007a2b3  test    eax, eax
0x18007a2b5  jns     short loc_18007A2EF
0x18007a2b7  mov     rcx, [rbp+98h]; this
0x18007a2be  mov     r9d, eax; char *
0x18007a2c1  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x18007a2c8  mov     edx, 20E8h; void *
0x18007a2cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a2d2  nop
0x18007a2d3  lea     rcx, [rbp+90h+var_D8]
0x18007a2d7  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18007a2dc  nop
0x18007a2dd  lea     rcx, [rsp+190h+var_118]
0x18007a2e2  call    ??1?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?FidoFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<char *,void (*)(void *),&FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>(void)
0x18007a2e7  mov     ebx, r14d
0x18007a2ea  jmp     loc_18007A73D
0x18007a2ef  mov     r14, qword ptr [rbp+90h+var_D8]
0x18007a2f3  xor     eax, eax
0x18007a2f5  inc     rdi
0x18007a2f8  cmp     [r14+rdi*2], ax
0x18007a2fd  jnz     short loc_18007A2F5
0x18007a2ff  test    rdi, rdi
0x18007a302  jnz     short loc_18007A36A
0x18007a304  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x18007a30b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18007a310  test    al, al
0x18007a312  jz      short loc_18007A331
0x18007a314  mov     rcx, [rbp+98h]; this
0x18007a31b  xor     r9d, r9d; char *
0x18007a31e  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x18007a325  mov     edx, 20EFh; void *
0x18007a32a  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18007a32f  jmp     short loc_18007A36A
0x18007a331  mov     eax, cs:dword_180122070
0x18007a337  cmp     eax, 2
0x18007a33a  jbe     short loc_18007A36A
0x18007a33c  xor     ecx, ecx; int
0x18007a33e  call    ?HResultToSecurityStatus@@YAJJ@Z; HResultToSecurityStatus(long)
0x18007a343  mov     [rsp+190h+var_120], eax
0x18007a347  lea     rax, [rsp+190h+var_120]
0x18007a34c  mov     [rsp+190h+lpMultiByteStr], rax; int
0x18007a351  xor     r9d, r9d
0x18007a354  xor     r8d, r8d
0x18007a357  lea     rdx, unk_180101000
0x18007a35e  lea     rcx, dword_180122070
0x18007a365  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18007a36a  lea     rdx, aEcdsaP256; "ECDSA_P256"
0x18007a371  mov     rcx, r14
0x18007a374  call    cs:__imp__o__wcsicmp
0x18007a37a  test    eax, eax
0x18007a37c  jnz     short loc_18007A387
0x18007a37e  lea     rdi, aSha256_0; "SHA256"
0x18007a385  jmp     short loc_18007A3A2
0x18007a387  lea     rdx, aEcdsaP384; "ECDSA_P384"
0x18007a38e  mov     rcx, r14
0x18007a391  call    cs:__imp__o__wcsicmp
0x18007a397  test    eax, eax
0x18007a399  jnz     short loc_18007A3AA
0x18007a39b  lea     rdi, aSha384; "SHA384"
0x18007a3a2  xor     r14d, r14d
0x18007a3a5  jmp     loc_18007A43E
0x18007a3aa  lea     rdx, aEcdsaP521; "ECDSA_P521"
0x18007a3b1  mov     rcx, r14
0x18007a3b4  call    cs:__imp__o__wcsicmp
0x18007a3ba  xor     r14d, r14d
0x18007a3bd  test    eax, eax
0x18007a3bf  jnz     short loc_18007A3CA
0x18007a3c1  lea     rdi, aSha512; "SHA512"
0x18007a3c8  jmp     short loc_18007A43E
0x18007a3ca  lea     rdi, sourceString
0x18007a3d1  mov     r12d, 80090029h
0x18007a3d7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x18007a3de  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18007a3e3  test    al, al
0x18007a3e5  jz      short loc_18007A404
0x18007a3e7  mov     rcx, [rbp+98h]; this
0x18007a3ee  mov     r9d, r12d; char *
0x18007a3f1  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x18007a3f8  mov     edx, 210Bh; void *
0x18007a3fd  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18007a402  jmp     short loc_18007A43E
0x18007a404  mov     eax, cs:dword_180122070
0x18007a40a  cmp     eax, 2
0x18007a40d  jbe     short loc_18007A43E
0x18007a40f  mov     ecx, r12d; int
0x18007a412  call    ?HResultToSecurityStatus@@YAJJ@Z; HResultToSecurityStatus(long)
0x18007a417  mov     [rsp+190h+var_120], eax
0x18007a41b  lea     rax, [rsp+190h+var_120]
0x18007a420  mov     [rsp+190h+lpMultiByteStr], rax
0x18007a425  xor     r9d, r9d
0x18007a428  xor     r8d, r8d
0x18007a42b  lea     rdx, dword_180100FC4
0x18007a432  lea     rcx, dword_180122070
0x18007a439  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18007a43e  xorps   xmm0, xmm0
0x18007a441  movups  xmmword ptr [rbp+90h+var_68], xmm0
0x18007a445  movups  [rbp+90h+var_58], xmm0
0x18007a449  mov     dword ptr [rsp+190h+lpDefaultChar], 20h ; ' '
0x18007a451  lea     rax, [rbp+90h+var_68]
0x18007a455  mov     qword ptr [rsp+190h+cbMultiByte], rax; struct _WEBAUTHN_EXTENSIONS *
0x18007a45a  mov     dword ptr [rsp+190h+lpMultiByteStr], r15d; Size
0x18007a45f  mov     r9, rbx
0x18007a462  xor     r8d, r8d
0x18007a465  xor     edx, edx
0x18007a467  lea     ecx, [rdx+41h]
0x18007a46a  call    cs:__imp_BCryptHash
0x18007a470  mov     ebx, eax
0x18007a472  test    eax, eax
0x18007a474  jns     short loc_18007A4A0
0x18007a476  mov     rcx, [rbp+98h]; this
0x18007a47d  mov     r9d, eax; char *
0x18007a480  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x18007a487  mov     edx, 2124h; void *
0x18007a48c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a491  nop
0x18007a492  lea     rcx, [rbp+90h+var_D8]
0x18007a496  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18007a49b  jmp     loc_18007A24C
0x18007a4a0  xorps   xmm0, xmm0
0x18007a4a3  movdqu  xmmword ptr [rbp+90h+var_108], xmm0
0x18007a4a8  mov     [rbp+90h+var_F8], r14
0x18007a4ac  mov     [rsp+190h+var_120], r14d
0x18007a4b1  lea     rax, [rsp+190h+var_120]
0x18007a4b6  mov     [rsp+190h+lpUsedDefaultChar], rax; unsigned int *
0x18007a4bb  mov     [rsp+190h+lpDefaultChar], r14; unsigned __int8 *
0x18007a4c0  mov     r8d, [rsp+190h+var_11C]; unsigned int
0x18007a4c5  mov     r15d, 20h ; ' '
0x18007a4cb  mov     edx, r15d; unsigned int
0x18007a4ce  lea     rcx, [rbp+90h+var_68]; unsigned __int8 *
0x18007a4d2  call    ?FidoAuthenticatorGenerateAuthenticatorData@@YAJPEBEKKPEBU_FIDO_AUTHENTICATOR_USER_VERIFICATION_METHOD_FACTOR@@KPEBU_WEBAUTHN_EXTENSIONS@@PEAEPEAK@Z; FidoAuthenticatorGenerateAuthenticatorData(uchar const *,ulong,ulong,_FIDO_AUTHENTICATOR_USER_VERIFICATION_METHOD_FACTOR const *,ulong,_WEBAUTHN_EXTENSIONS const *,uchar *,ulong *)
0x18007a4d7  mov     ebx, eax
0x18007a4d9  test    eax, eax
0x18007a4db  jns     short loc_18007A504
0x18007a4dd  mov     edx, 2130h; void *
0x18007a4e2  mov     rcx, [rbp+98h]; this
0x18007a4e9  mov     r9d, eax; char *
0x18007a4ec  lea     r8, aOnecoreDsSecur_43; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x18007a4f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a4f8  nop
0x18007a4f9  lea     rcx, [rbp+90h+var_108]
0x18007a4fd  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18007a502  jmp     short loc_18007A492
0x18007a504  mov     edx, [rsp+190h+var_120]
0x18007a508  lea     rcx, [rbp+90h+var_108]
0x18007a50c  call    ??$_Resize@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18007a511  mov     rax, [rbp+90h+var_108]
0x18007a515  lea     rcx, [rsp+190h+var_120]
0x18007a51a  mov     [rsp+190h+lpUsedDefaultChar], rcx; unsigned int *
0x18007a51f  mov     [rsp+190h+lpDefaultChar], rax; unsigned __int8 *
0x18007a524  mov     r8d, [rsp+190h+var_11C]; unsigned int
0x18007a529  mov     edx, r15d; unsigned int
0x18007a52c  lea     rcx, [rbp+90h+var_68]; unsigned __int8 *
0x18007a530  call    ?FidoAuthenticatorGenerateAuthenticatorData@@YAJPEBEKKPEBU_FIDO_AUTHENTICATOR_USER_VERIFICATION_METHOD_FACTOR@@KPEBU_WEBAUTHN_EXTENSIONS@@PEAEPEAK@Z; FidoAuthenticatorGenerateAuthenticatorData(uchar const *,ulong,ulong,_FIDO_AUTHENTICATOR_USER_VERIFICATION_METHOD_FACTOR const *,ulong,_WEBAUTHN_EXTENSIONS const *,uchar *,ulong *)
0x18007a535  mov     ebx, eax
0x18007a537  test    eax, eax
  ... truncated ...
```
