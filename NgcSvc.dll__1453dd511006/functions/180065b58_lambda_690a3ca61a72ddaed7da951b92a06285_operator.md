# _lambda_690a3ca61a72ddaed7da951b92a06285_::operator()

- ea: `0x180065b58`
- end: `0x180066168`
- name: `_lambda_690a3ca61a72ddaed7da951b92a06285_::operator()`
- size: `1552`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180064da4`

## callees

- `0x18000782c`
- `0x180010990`
- `0x180010a94`
- `0x180011810`
- `0x1800157b0`
- `0x180028d18`
- `0x180046d90`
- `0x180048394`
- `0x180065b58`
- `0x180068b54`
- `0x1800cd010`

## import_xrefs

- `ncrypt!NCryptVerifyClaim` at `0x18006607f`
- `ncrypt!NCryptVerifyClaim` at `0x180066095`
- `ncrypt!NCryptVerifyClaim` at `0x18006607f`
- `ncrypt!NCryptVerifyClaim` at `0x180066095`
- `ncrypt!NCryptImportKey` at `0x180065e43`
- `ncrypt!NCryptImportKey` at `0x180065eb8`
- `ncrypt!NCryptImportKey` at `0x180065f70`
- `ncrypt!NCryptImportKey` at `0x180065fd9`
- `ncrypt!NCryptImportKey` at `0x180065e43`
- `ncrypt!NCryptImportKey` at `0x180065eb8`
- `ncrypt!NCryptImportKey` at `0x180065f70`
- `ncrypt!NCryptImportKey` at `0x180065fd9`
- `ncrypt!NCryptOpenStorageProvider` at `0x180065d38`
- `ncrypt!NCryptOpenStorageProvider` at `0x180065d90`
- `ncrypt!NCryptOpenStorageProvider` at `0x180065d38`
- `ncrypt!NCryptOpenStorageProvider` at `0x180065d90`

## string_xrefs

- `0x180065d4f`: `onecore\ds\security\ngc\kspsvc\svc\kspsrv.cpp`
- `0x180065e5a`: `onecore\ds\security\ngc\kspsvc\svc\kspsrv.cpp`
- `0x180065f85`: `onecore\ds\security\ngc\kspsvc\svc\kspsrv.cpp`
- `0x180066101`: `onecore\ds\security\ngc\kspsvc\svc\kspsrv.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall lambda_690a3ca61a72ddaed7da951b92a06285_::operator()(__int64 a1)
{
  unsigned int v2; // ebx
  __int64 v3; // rdx
  unsigned __int8 *v4; // rdx
  SECURITY_STATUS v5; // esi
  char IsEnabled; // al
  DWORD v8; // ebx
  SECURITY_STATUS v9; // eax
  char v10; // al
  DWORD v11; // r15d
  BYTE *v12; // rdi
  int v13; // ebx
  SECURITY_STATUS v14; // eax
  char v15; // al
  DWORD v16; // r15d
  BYTE *v17; // rdi
  int v18; // ebx
  __int64 v19; // rdx
  unsigned __int8 *v20; // rdx
  char v21; // al
  __int64 v22; // r9
  int phKey; // [rsp+20h] [rbp-89h]
  int phKeya; // [rsp+20h] [rbp-89h]
  int phKeyb; // [rsp+20h] [rbp-89h]
  NCRYPT_KEY_HANDLE *phKeyc; // [rsp+20h] [rbp-89h]
  int pbData; // [rsp+28h] [rbp-81h]
  DWORD dwFlags; // [rsp+38h] [rbp-71h]
  void **v29; // [rsp+40h] [rbp-69h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+48h] [rbp-61h] BYREF
  void **v31; // [rsp+50h] [rbp-59h] BYREF
  NCRYPT_KEY_HANDLE v32; // [rsp+58h] [rbp-51h] BYREF
  void **v33; // [rsp+60h] [rbp-49h] BYREF
  NCRYPT_KEY_HANDLE v34; // [rsp+68h] [rbp-41h] BYREF
  __int64 v35; // [rsp+70h] [rbp-39h] BYREF
  std::_Ref_count_base *v36; // [rsp+78h] [rbp-31h]
  __int64 v37; // [rsp+80h] [rbp-29h] BYREF
  std::_Ref_count_base *v38; // [rsp+88h] [rbp-21h]
  PBYTE v39[2]; // [rsp+90h] [rbp-19h] BYREF
  __int64 v40; // [rsp+A0h] [rbp-9h]
  PBYTE v41[2]; // [rsp+A8h] [rbp-1h] BYREF
  __int64 v42; // [rsp+B8h] [rbp+Fh]
  __int128 v43; // [rsp+C0h] [rbp+17h] BYREF
  __int128 *v44; // [rsp+D0h] [rbp+27h] BYREF
  __int16 v45; // [rsp+D8h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]
  int v47; // [rsp+110h] [rbp+67h] BYREF

  if ( !**(_QWORD **)a1
    || !**(_QWORD **)(a1 + 8)
    || !**(_QWORD **)(a1 + 16)
    || !**(_DWORD **)(a1 + 24)
    || !**(_QWORD **)(a1 + 32) )
  {
    v2 = -2146893785;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      v3 = 3207;
      goto LABEL_57;
    }
    if ( (unsigned int)dword_180122070 <= 2 )
      return v2;
    v47 = -2146893785;
    v4 = (unsigned __int8 *)byte_1800FD611;
LABEL_60:
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_180122070,
      v4,
      0,
      0,
      (__int64)&v47);
    return v2;
  }
  if ( (**(_DWORD **)(a1 + 40) & 0xFFFFEFBF) != 0 )
  {
    v2 = -2146893815;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      v3 = 3227;
LABEL_57:
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)v3,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\kspsrv.cpp",
        (const char *)v2,
        phKey);
      return v2;
    }
    if ( (unsigned int)dword_180122070 <= 2 )
      return v2;
    v47 = -2146893815;
    v4 = (unsigned __int8 *)&word_1800FD5E6;
    goto LABEL_60;
  }
  std::shared_ptr<NgcTransport>::shared_ptr<NgcTransport>(&v37);
  std::shared_ptr<NgcTransport>::shared_ptr<NgcTransport>(&v35);
  *(_OWORD *)v39 = 0;
  v40 = 0;
  v2 = (*(__int64 (__fastcall **)(__int64, const WCHAR *, PBYTE *))(*(_QWORD *)v37 + 48LL))(v37, L"RSAPUBLICBLOB", v39);
  if ( (v2 & 0x80000000) != 0 )
  {
LABEL_12:
    std::vector<unsigned char>::_Tidy(v39);
    if ( v36 )
      std::_Ref_count_base::_Decref(v36);
    if ( v38 )
      std::_Ref_count_base::_Decref(v38);
    return v2;
  }
  *(_OWORD *)v41 = 0;
  v42 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, const WCHAR *, PBYTE *))(*(_QWORD *)v35 + 48LL))(v35, L"RSAPUBLICBLOB", v41);
  if ( v5 >= 0 )
  {
    **(_DWORD **)(a1 + 40) |= 0x1000u;
    v29 = &Microsoft::WRL::Wrappers::HandleT<NCryptProvHandleTraits>::`vftable';
    phProvider = 0;
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl);
    v8 = **(_DWORD **)(a1 + 40);
    if ( IsEnabled )
    {
      Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v29);
      v9 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Platform Crypto Provider", v8);
      v2 = v9;
      if ( v9 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xCC4,
          (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\kspsrv.cpp",
          (const char *)(unsigned int)v9,
          phKey);
        v29 = &Microsoft::WRL::Wrappers::HandleT<NCryptProvHandleTraits>::`vftable';
LABEL_25:
        Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v29);
        std::vector<unsigned char>::_Tidy(v41);
        goto LABEL_12;
      }
    }
    else
    {
      Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v29);
      v5 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Platform Crypto Provider", v8);
      if ( v5 < 0 )
      {
        if ( (unsigned int)dword_180122070 > 2 )
        {
          v47 = v5;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (__int64)&dword_180122070,
            (unsigned __int8 *)&unk_1800FD5B8,
            0,
            0,
            (__int64)&v47);
        }
        v29 = &Microsoft::WRL::Wrappers::HandleT<NCryptProvHandleTraits>::`vftable';
        goto LABEL_30;
      }
    }
    v31 = &Microsoft::WRL::Wrappers::HandleT<NCryptProvHandleTraits>::`vftable';
    v32 = 0;
    v10 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl);
    v11 = **(_DWORD **)(a1 + 40);
    v12 = v39[0];
    v13 = (int)v39[1];
    if ( v10 )
    {
      Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v31);
      v14 = NCryptImportKey(phProvider, 0, L"RSAPUBLICBLOB", 0, &v32, v12, v13 - (_DWORD)v12, v11);
      v2 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xCE1,
          (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\kspsrv.cpp",
          (const char *)(unsigned int)v14,
          phKeya);
LABEL_34:
        v31 = &Microsoft::WRL::Wrappers::HandleT<NCryptProvHandleTraits>::`vftable';
        Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v31);
        v29 = &Microsoft::WRL::Wrappers::HandleT<NCryptProvHandleTraits>::`vftable';
        goto LABEL_25;
      }
    }
    else
    {
      Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v31);
      v5 = NCryptImportKey(phProvider, 0, L"RSAPUBLICBLOB", 0, &v32, v12, v13 - (_DWORD)v12, v11);
      if ( v5 < 0 )
      {
        if ( (unsigned int)dword_180122070 > 2 )
        {
          v47 = v5;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (__int64)&dword_180122070,
            (unsigned __int8 *)byte_1800FD589,
            0,
            0,
            (__int64)&v47);
        }
        goto LABEL_38;
      }
    }
    v33 = &Microsoft::WRL::Wrappers::HandleT<NCryptProvHandleTraits>::`vftable';
    v34 = 0;
    v15 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl);
    v16 = **(_DWORD **)(a1 + 40);
    v17 = v41[0];
    v18 = (int)v41[1];
    if ( v15 )
    {
      Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v33);
      v2 = NCryptImportKey(phProvider, 0, L"RSAPUBLICBLOB", 0, &v34, v17, v18 - (_DWORD)v17, v16);
      if ( (v2 & 0x80000000) != 0 )
      {
        v19 = 3331;
LABEL_42:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v19,
          (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\kspsrv.cpp",
          (const char *)v2,
          phKeyb);
        v33 = &Microsoft::WRL::Wrappers::HandleT<NCryptProvHandleTraits>::`vftable';
        Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v33);
        goto LABEL_34;
      }
    }
    else
    {
      Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v33);
      v5 = NCryptImportKey(phProvider, 0, L"RSAPUBLICBLOB", 0, &v34, v17, v18 - (_DWORD)v17, v16);
      if ( v5 < 0 )
      {
        if ( (unsigned int)dword_180122070 > 2 )
        {
          v20 = (unsigned __int8 *)&word_1800FD556;
LABEL_46:
          v47 = v5;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (__int64)&dword_180122070,
            v20,
            0,
            0,
            (__int64)&v47);
        }
LABEL_47:
        v33 = &Microsoft::WRL::Wrappers::HandleT<NCryptProvHandleTraits>::`vftable';
        Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v33);
LABEL_38:
        v31 = &Microsoft::WRL::Wrappers::HandleT<NCryptProvHandleTraits>::`vftable';
        Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v31);
        v29 = &Microsoft::WRL::Wrappers::HandleT<NCryptProvHandleTraits>::`vftable';
LABEL_30:
        Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v29);
        goto LABEL_17;
      }
    }
    v43 = 0;
    v21 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl);
    dwFlags = **(_DWORD **)(a1 + 40);
    v22 = **(_QWORD **)(a1 + 48);
    pbData = **(_DWORD **)(a1 + 24);
    phKeyc = **(NCRYPT_KEY_HANDLE ***)(a1 + 16);
    if ( v21 )
    {
      v2 = NCryptVerifyClaim(v34, v32, 2, v22, phKeyc, pbData, &v43, dwFlags, v29);
      if ( (v2 & 0x80000000) != 0 )
      {
        v19 = 3365;
        goto LABEL_42;
      }
      goto LABEL_54;
    }
    v5 = NCryptVerifyClaim(v34, v32, 2, v22, phKeyc, pbData, &v43, dwFlags, v29);
    if ( v5 >= 0 )
    {
LABEL_54:
      v44 = &v43;
      v45 = 0;
      *(_OWORD *)**(_QWORD **)(a1 + 32) = v43;
      wil::details::ScopeExitFnGuard__lambda_8d8fc70d3cd43acde535b2cc2e329241___::operator()(&v44);
      goto LABEL_47;
    }
    if ( (unsigned int)dword_180122070 > 2 )
    {
      v20 = (unsigned __int8 *)&unk_1800FD528;
      goto LABEL_46;
    }
    goto LABEL_47;
  }
LABEL_17:
  std::vector<unsigned char>::_Tidy(v41);
  std::vector<unsigned char>::_Tidy(v39);
  if ( v36 )
    std::_Ref_count_base::_Decref(v36);
  if ( v38 )
    std::_Ref_count_base::_Decref(v38);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180065b58  mov     [rsp-8+arg_8], rbx
0x180065b5d  mov     [rsp-8+arg_10], rsi
0x180065b62  push    rbp
0x180065b63  push    rdi
0x180065b64  push    r13
0x180065b66  push    r14
0x180065b68  push    r15
0x180065b6a  lea     rbp, [rsp-37h]
0x180065b6f  sub     rsp, 0E0h
0x180065b76  mov     r14, rcx
0x180065b79  mov     rax, [rcx]
0x180065b7c  cmp     qword ptr [rax], 0
0x180065b80  jz      loc_1800660E7
0x180065b86  mov     rax, [rcx+8]
0x180065b8a  mov     rdx, [rax]
0x180065b8d  test    rdx, rdx
0x180065b90  jz      loc_1800660E7
0x180065b96  mov     rax, [rcx+10h]
0x180065b9a  cmp     qword ptr [rax], 0
0x180065b9e  jz      loc_1800660E7
0x180065ba4  mov     rax, [rcx+18h]
0x180065ba8  cmp     dword ptr [rax], 0
0x180065bab  jz      loc_1800660E7
0x180065bb1  mov     rax, [rcx+20h]
0x180065bb5  cmp     qword ptr [rax], 0
0x180065bb9  jz      loc_1800660E7
0x180065bbf  mov     rax, [rcx+28h]
0x180065bc3  test    dword ptr [rax], 0FFFFEFBFh
0x180065bc9  jz      short loc_180065C0C
0x180065bcb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x180065bd2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x180065bd7  mov     ebx, 80090009h
0x180065bdc  test    al, al
0x180065bde  jz      short loc_180065BEA
0x180065be0  mov     edx, 0C9Bh
0x180065be5  jmp     loc_180066101
0x180065bea  mov     eax, cs:dword_180122070
0x180065bf0  cmp     eax, 2
0x180065bf3  jbe     loc_18006614A
0x180065bf9  mov     [rbp+57h+arg_0], 80090009h
0x180065c00  lea     rdx, word_1800FD5E6
0x180065c07  jmp     loc_18006612F
0x180065c0c  lea     rcx, [rbp+57h+var_80]
0x180065c10  call    ??0?$shared_ptr@VNgcTransport@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<NgcTransport>::shared_ptr<NgcTransport>(std::shared_ptr<NgcTransport> const &)
0x180065c15  nop
0x180065c16  mov     rdx, [r14]
0x180065c19  mov     rdx, [rdx]
0x180065c1c  lea     rcx, [rbp+57h+var_90]
0x180065c20  call    ??0?$shared_ptr@VNgcTransport@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<NgcTransport>::shared_ptr<NgcTransport>(std::shared_ptr<NgcTransport> const &)
0x180065c25  nop
0x180065c26  xorps   xmm0, xmm0
0x180065c29  movdqu  xmmword ptr [rbp+57h+var_70], xmm0
0x180065c2e  mov     [rbp+57h+var_60], 0
0x180065c36  mov     rcx, [rbp+57h+var_80]
0x180065c3a  mov     rax, [rcx]
0x180065c3d  lea     r8, [rbp+57h+var_70]
0x180065c41  lea     rdx, aRsapublicblob; "RSAPUBLICBLOB"
0x180065c48  mov     rax, [rax+30h]
0x180065c4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065c51  mov     ebx, eax
0x180065c53  test    eax, eax
0x180065c55  jns     short loc_180065C87
0x180065c57  lea     rcx, [rbp+57h+var_70]
0x180065c5b  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180065c60  nop
0x180065c61  mov     rcx, [rbp+57h+var_88]; this
0x180065c65  test    rcx, rcx
0x180065c68  jz      short loc_180065C70
0x180065c6a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180065c6f  nop
0x180065c70  mov     rcx, [rbp+57h+var_78]; this
0x180065c74  test    rcx, rcx
0x180065c77  jz      loc_18006614A
0x180065c7d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180065c82  jmp     loc_18006614A
0x180065c87  xorps   xmm0, xmm0
0x180065c8a  movdqu  xmmword ptr [rbp+57h+var_58], xmm0
0x180065c8f  mov     [rbp+57h+var_48], 0
0x180065c97  mov     rcx, [rbp+57h+var_90]
0x180065c9b  mov     rax, [rcx]
0x180065c9e  lea     r8, [rbp+57h+var_58]
0x180065ca2  lea     rdx, aRsapublicblob; "RSAPUBLICBLOB"
0x180065ca9  mov     rax, [rax+30h]
0x180065cad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065cb2  mov     esi, eax
0x180065cb4  test    eax, eax
0x180065cb6  jns     short loc_180065CF0
0x180065cb8  lea     rcx, [rbp+57h+var_58]
0x180065cbc  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180065cc1  nop
0x180065cc2  lea     rcx, [rbp+57h+var_70]
0x180065cc6  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180065ccb  nop
0x180065ccc  mov     rcx, [rbp+57h+var_88]; this
0x180065cd0  test    rcx, rcx
0x180065cd3  jz      short loc_180065CDB
0x180065cd5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180065cda  nop
0x180065cdb  mov     rcx, [rbp+57h+var_78]; this
0x180065cdf  test    rcx, rcx
0x180065ce2  jz      short loc_180065CE9
0x180065ce4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180065ce9  mov     eax, esi
0x180065ceb  jmp     loc_18006614C
0x180065cf0  mov     rax, [r14+28h]
0x180065cf4  bts     dword ptr [rax], 0Ch
0x180065cf8  lea     rdi, ??_7?$HandleT@UNCryptProvHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<NCryptProvHandleTraits>::`vftable'
0x180065cff  mov     [rbp+57h+var_C0], rdi
0x180065d03  mov     [rbp+57h+phProvider], 0
0x180065d0b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x180065d12  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x180065d17  mov     rcx, [r14+28h]
0x180065d1b  mov     ebx, [rcx]
0x180065d1d  lea     rcx, [rbp+57h+var_C0]
0x180065d21  test    al, al
0x180065d23  jz      short loc_180065D7D
0x180065d25  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x180065d2a  mov     r8d, ebx; dwFlags
0x180065d2d  lea     rdx, aMicrosoftPlatf; "Microsoft Platform Crypto Provider"
0x180065d34  lea     rcx, [rbp+57h+phProvider]; phProvider
0x180065d38  call    cs:__imp_NCryptOpenStorageProvider
0x180065d3e  mov     ebx, eax
0x180065d40  test    eax, eax
0x180065d42  jns     loc_180065DDF
0x180065d48  mov     rcx, [rbp+5Fh]; this
0x180065d4c  mov     r9d, eax; char *
0x180065d4f  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x180065d56  mov     edx, 0CC4h; void *
0x180065d5b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065d60  nop
0x180065d61  mov     [rbp+57h+var_C0], rdi
0x180065d65  lea     rcx, [rbp+57h+var_C0]
0x180065d69  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x180065d6e  nop
0x180065d6f  lea     rcx, [rbp+57h+var_58]
0x180065d73  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180065d78  jmp     loc_180065C57
0x180065d7d  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x180065d82  mov     r8d, ebx; dwFlags
0x180065d85  lea     rdx, aMicrosoftPlatf; "Microsoft Platform Crypto Provider"
0x180065d8c  lea     rcx, [rbp+57h+phProvider]; phProvider
0x180065d90  call    cs:__imp_NCryptOpenStorageProvider
0x180065d96  mov     esi, eax
0x180065d98  test    eax, eax
0x180065d9a  jns     short loc_180065DDF
0x180065d9c  mov     eax, cs:dword_180122070
0x180065da2  cmp     eax, 2
0x180065da5  jbe     short loc_180065DCD
0x180065da7  mov     [rbp+57h+arg_0], esi
0x180065daa  lea     rax, [rbp+57h+arg_0]
0x180065dae  mov     [rsp+100h+phKey], rax
0x180065db3  xor     r9d, r9d
0x180065db6  xor     r8d, r8d
0x180065db9  lea     rdx, unk_1800FD5B8
0x180065dc0  lea     rcx, dword_180122070
0x180065dc7  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180065dcc  nop
0x180065dcd  mov     [rbp+57h+var_C0], rdi
0x180065dd1  lea     rcx, [rbp+57h+var_C0]
0x180065dd5  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x180065dda  jmp     loc_180065CB8
0x180065ddf  lea     r13, ??_7?$HandleT@UNCryptProvHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<NCryptProvHandleTraits>::`vftable'
0x180065de6  mov     [rbp+57h+var_B0], r13
0x180065dea  mov     [rbp+57h+var_A8], 0
0x180065df2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x180065df9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x180065dfe  mov     rcx, [r14+28h]
0x180065e02  mov     r15d, [rcx]
0x180065e05  mov     rdi, [rbp+57h+var_70]
0x180065e09  mov     rbx, [rbp+57h+var_70+8]
0x180065e0d  lea     rcx, [rbp+57h+var_B0]
0x180065e11  test    al, al
0x180065e13  jz      short loc_180065E8A
0x180065e15  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x180065e1a  sub     ebx, edi
0x180065e1c  mov     [rsp+100h+dwFlags], r15d; dwFlags
0x180065e21  mov     [rsp+100h+cbData], ebx; cbData
0x180065e25  mov     [rsp+100h+pbData], rdi; pbData
0x180065e2a  lea     rax, [rbp+57h+var_A8]
0x180065e2e  mov     [rsp+100h+phKey], rax; int
0x180065e33  xor     r9d, r9d; pParameterList
0x180065e36  lea     r8, aRsapublicblob; "RSAPUBLICBLOB"
0x180065e3d  xor     edx, edx; hImportKey
0x180065e3f  mov     rcx, [rbp+57h+phProvider]; hProvider
0x180065e43  call    cs:__imp_NCryptImportKey
0x180065e49  mov     ebx, eax
0x180065e4b  test    eax, eax
0x180065e4d  jns     loc_180065F13
0x180065e53  mov     rcx, [rbp+5Fh]; this
0x180065e57  mov     r9d, eax; char *
0x180065e5a  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x180065e61  mov     edx, 0CE1h; void *
0x180065e66  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065e6b  nop
0x180065e6c  mov     [rbp+57h+var_B0], r13
0x180065e70  lea     rcx, [rbp+57h+var_B0]
0x180065e74  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x180065e79  nop
0x180065e7a  lea     rax, ??_7?$HandleT@UNCryptProvHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<NCryptProvHandleTraits>::`vftable'
0x180065e81  mov     [rbp+57h+var_C0], rax
0x180065e85  jmp     loc_180065D65
0x180065e8a  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x180065e8f  sub     ebx, edi
0x180065e91  mov     [rsp+100h+dwFlags], r15d; dwFlags
0x180065e96  mov     [rsp+100h+cbData], ebx; cbData
0x180065e9a  mov     [rsp+100h+pbData], rdi; pbData
0x180065e9f  lea     rax, [rbp+57h+var_A8]
0x180065ea3  mov     [rsp+100h+phKey], rax; phKey
0x180065ea8  xor     r9d, r9d; pParameterList
0x180065eab  lea     r8, aRsapublicblob; "RSAPUBLICBLOB"
0x180065eb2  xor     edx, edx; hImportKey
0x180065eb4  mov     rcx, [rbp+57h+phProvider]; hProvider
0x180065eb8  call    cs:__imp_NCryptImportKey
0x180065ebe  mov     esi, eax
0x180065ec0  test    eax, eax
0x180065ec2  jns     short loc_180065F13
0x180065ec4  mov     eax, cs:dword_180122070
0x180065eca  cmp     eax, 2
0x180065ecd  jbe     short loc_180065EF5
0x180065ecf  mov     [rbp+57h+arg_0], esi
0x180065ed2  lea     rax, [rbp+57h+arg_0]
0x180065ed6  mov     [rsp+100h+phKey], rax
0x180065edb  xor     r9d, r9d
0x180065ede  xor     r8d, r8d
0x180065ee1  lea     rdx, byte_1800FD589
0x180065ee8  lea     rcx, dword_180122070
0x180065eef  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180065ef4  nop
0x180065ef5  mov     [rbp+57h+var_B0], r13
0x180065ef9  lea     rcx, [rbp+57h+var_B0]
0x180065efd  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x180065f02  nop
0x180065f03  lea     rax, ??_7?$HandleT@UNCryptProvHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<NCryptProvHandleTraits>::`vftable'
0x180065f0a  mov     [rbp+57h+var_C0], rax
0x180065f0e  jmp     loc_180065DD1
0x180065f13  mov     [rbp+57h+var_A0], r13
0x180065f17  mov     [rbp+57h+var_98], 0
0x180065f1f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x180065f26  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x180065f2b  mov     rcx, [r14+28h]
0x180065f2f  mov     r15d, [rcx]
0x180065f32  mov     rdi, [rbp+57h+var_58]
0x180065f36  mov     rbx, [rbp+57h+var_58+8]
0x180065f3a  lea     rcx, [rbp+57h+var_A0]
0x180065f3e  test    al, al
0x180065f40  jz      short loc_180065FAB
0x180065f42  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x180065f47  sub     ebx, edi
0x180065f49  mov     [rsp+100h+dwFlags], r15d; dwFlags
0x180065f4e  mov     [rsp+100h+cbData], ebx; cbData
0x180065f52  mov     [rsp+100h+pbData], rdi; pbData
0x180065f57  lea     rax, [rbp+57h+var_98]
0x180065f5b  mov     [rsp+100h+phKey], rax; int
0x180065f60  xor     r9d, r9d; pParameterList
0x180065f63  lea     r8, aRsapublicblob; "RSAPUBLICBLOB"
0x180065f6a  xor     edx, edx; hImportKey
0x180065f6c  mov     rcx, [rbp+57h+phProvider]; hProvider
0x180065f70  call    cs:__imp_NCryptImportKey
0x180065f76  mov     ebx, eax
0x180065f78  test    eax, eax
0x180065f7a  jns     loc_180066028
0x180065f80  mov     edx, 0D03h; void *
0x180065f85  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x180065f8c  mov     r9d, ebx; char *
0x180065f8f  mov     rcx, [rbp+5Fh]; this
0x180065f93  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065f98  nop
0x180065f99  mov     [rbp+57h+var_A0], r13
0x180065f9d  lea     rcx, [rbp+57h+var_A0]
0x180065fa1  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x180065fa6  jmp     loc_180065E6C
0x180065fab  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x180065fb0  sub     ebx, edi
0x180065fb2  mov     [rsp+100h+dwFlags], r15d; dwFlags
0x180065fb7  mov     [rsp+100h+cbData], ebx; cbData
0x180065fbb  mov     [rsp+100h+pbData], rdi; pbData
0x180065fc0  lea     rax, [rbp+57h+var_98]
0x180065fc4  mov     [rsp+100h+phKey], rax; phKey
0x180065fc9  xor     r9d, r9d; pParameterList
0x180065fcc  lea     r8, aRsapublicblob; "RSAPUBLICBLOB"
0x180065fd3  xor     edx, edx; hImportKey
0x180065fd5  mov     rcx, [rbp+57h+phProvider]; hProvider
0x180065fd9  call    cs:__imp_NCryptImportKey
0x180065fdf  mov     esi, eax
0x180065fe1  test    eax, eax
0x180065fe3  jns     short loc_180066028
0x180065fe5  mov     eax, cs:dword_180122070
0x180065feb  cmp     eax, 2
0x180065fee  jbe     short loc_180066016
0x180065ff0  lea     rdx, word_1800FD556
0x180065ff7  xor     r9d, r9d
0x180065ffa  lea     rax, [rbp+57h+arg_0]
0x180065ffe  xor     r8d, r8d
0x180066001  mov     [rsp+100h+phKey], rax
0x180066006  mov     [rbp+57h+arg_0], esi
0x180066009  lea     rcx, dword_180122070
0x180066010  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180066015  nop
0x180066016  mov     [rbp+57h+var_A0], r13
0x18006601a  lea     rcx, [rbp+57h+var_A0]
  ... truncated ...
```
