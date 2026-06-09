# _lambda_0d447ec4da7fb4a14bef0a6f3dce0c1a_::operator()

- ea: `0x18006cb40`
- end: `0x18006d0a2`
- name: `_lambda_0d447ec4da7fb4a14bef0a6f3dce0c1a_::operator()`
- size: `1378`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18006c400`

## callees

- `0x18000782c`
- `0x180010990`
- `0x180010a94`
- `0x180011810`
- `0x180011c04`
- `0x180012260`
- `0x180013950`
- `0x180021950`
- `0x180022510`
- `0x180028420`
- `0x180028d18`
- `0x180029dd0`
- `0x18002c9d8`
- `0x180034cf8`
- `0x180046d90`
- `0x180059df4`
- `0x18006c8d0`
- `0x18006caa4`
- `0x18006cb40`
- `0x180085048`
- `0x180088c10`
- `0x1800a962c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ce8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ce8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006cfa8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006d06b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006cfa8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006d06b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18006ce78`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18006ce78`

## string_xrefs

- `0x18006cb9d`: `onecore\ds\security\ngc\kspsvc\svc\mgmtsrv.cpp`
- `0x18006cc38`: `onecore\ds\security\ngc\kspsvc\svc\mgmtsrv.cpp`
- `0x18006cd13`: `onecore\ds\security\ngc\kspsvc\svc\mgmtsrv.cpp`
- `0x18006ceac`: `onecore\ds\security\ngc\kspsvc\svc\mgmtsrv.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall lambda_0d447ec4da7fb4a14bef0a6f3dce0c1a_::operator()(__int64 a1)
{
  char IsEnabled; // al
  const WCHAR *v3; // r9
  void *v4; // rcx
  int v5; // eax
  DWORD LastError; // ebx
  int v7; // eax
  int LocalContainer; // eax
  int v9; // eax
  struct NgcKspServer::TransportManager *v10; // rax
  _QWORD *v11; // rax
  __int64 v12; // rbx
  int ContainerMetadata; // edi
  __int64 v14; // rdx
  struct NgcKspServer::TransportManager *v15; // rax
  _QWORD *v16; // rax
  char *v17; // rdx
  BOOL v18; // edi
  HLOCAL v19; // rcx
  struct NgcKspServer::TransportManager *v20; // rax
  _QWORD *v21; // rax
  HLOCAL v22; // rcx
  unsigned int v24; // [rsp+20h] [rbp-E0h]
  void **v25; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v26; // [rsp+38h] [rbp-C8h]
  __int128 v27; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v28; // [rsp+50h] [rbp-B0h]
  HLOCAL *p_hMem; // [rsp+58h] [rbp-A8h] BYREF
  PSID Sid; // [rsp+60h] [rbp-A0h] BYREF
  char v31; // [rsp+68h] [rbp-98h]
  _BYTE v32[4]; // [rsp+70h] [rbp-90h] BYREF
  int v33; // [rsp+74h] [rbp-8Ch]
  __int64 v34; // [rsp+78h] [rbp-88h]
  char v35; // [rsp+80h] [rbp-80h]
  int v36; // [rsp+84h] [rbp-7Ch]
  int v37; // [rsp+88h] [rbp-78h]
  __int128 v38; // [rsp+8Ch] [rbp-74h]
  int v39; // [rsp+9Ch] [rbp-64h]
  __int64 v40; // [rsp+A0h] [rbp-60h]
  int v41; // [rsp+A8h] [rbp-58h]
  __int128 v42; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v43; // [rsp+C0h] [rbp-40h]
  _BYTE v44[24]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v45[32]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v46[128]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]
  DWORD v48; // [rsp+198h] [rbp+98h] BYREF
  HLOCAL hMem; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v50; // [rsp+1A8h] [rbp+A8h] BYREF

  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl);
  v3 = **(const WCHAR ***)(a1 + 8);
  v4 = **(void ***)a1;
  if ( IsEnabled )
  {
    v5 = I_CheckNgcApiAccessRight(v4, 0, 0, v3, 0);
    LastError = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x638,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\mgmtsrv.cpp",
        (const char *)(unsigned int)v5,
        v24);
      return LastError;
    }
LABEL_7:
    v50 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      NgcKspServer::TransportManager::Instance();
      LocalContainer = NgcKspServer::TransportManager::FindLocalContainer(**(const WCHAR ***)(a1 + 8), &v50);
      LastError = LocalContainer;
      if ( LocalContainer < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x64F,
          (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\mgmtsrv.cpp",
          (const char *)(unsigned int)LocalContainer,
          v24);
LABEL_48:
        std::unique_ptr<NgcTransportContainerInfo>::~unique_ptr<NgcTransportContainerInfo>(&v50);
        return LastError;
      }
    }
    else
    {
      NgcKspServer::TransportManager::Instance();
      v9 = NgcKspServer::TransportManager::FindLocalContainer(**(const WCHAR ***)(a1 + 8), &v50);
      LastError = v9;
      if ( v9 < 0 )
      {
        if ( (unsigned int)dword_180122070 > 2 )
        {
          v48 = v9;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (__int64)&dword_180122070,
            (unsigned __int8 *)byte_1800FF41B,
            0,
            0,
            (__int64)&v48);
        }
        goto LABEL_48;
      }
    }
    v27 = 0;
    v28 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      v10 = NgcKspServer::TransportManager::Instance();
      v11 = (_QWORD *)NgcKspServer::TransportManager::LocalTransport(v10, &p_hMem);
      v12 = v50;
      ContainerMetadata = NgcLocalTransport::LocalTransport::GetContainerMetadata(*v11, v50, 2, &v27);
      if ( Sid )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)Sid);
      if ( ContainerMetadata < 0 )
      {
        v14 = 1638;
LABEL_18:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v14,
          (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\mgmtsrv.cpp",
          (const char *)(unsigned int)ContainerMetadata,
          v24);
LABEL_19:
        std::vector<unsigned char>::_Tidy(&v27);
        LastError = ContainerMetadata;
        goto LABEL_48;
      }
    }
    else
    {
      v15 = NgcKspServer::TransportManager::Instance();
      v16 = (_QWORD *)NgcKspServer::TransportManager::LocalTransport(v15, &p_hMem);
      v12 = v50;
      ContainerMetadata = NgcLocalTransport::LocalTransport::GetContainerMetadata(*v16, v50, 2, &v27);
      if ( Sid )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)Sid);
      if ( ContainerMetadata < 0 )
      {
        if ( (unsigned int)dword_180122070 <= 2 )
          goto LABEL_19;
        v17 = &byte_1800FF3E7;
        goto LABEL_25;
      }
    }
    v32[0] = 0;
    v33 = 1;
    v34 = 1;
    v35 = 0;
    v36 = 8;
    v37 = 127;
    v38 = 0;
    v39 = 2;
    v40 = 1;
    v41 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      ContainerMetadata = NgcPolicy::NgcPolicy::Initialize(v32, &v27);
      if ( ContainerMetadata < 0 )
      {
        v14 = 1659;
        goto LABEL_18;
      }
LABEL_32:
      hMem = 0;
      p_hMem = &hMem;
      Sid = 0;
      v31 = 1;
      v18 = ConvertStringSidToSidW(**(LPCWSTR **)(a1 + 8), &Sid);
      wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>((__int64)&p_hMem);
      if ( v18 )
      {
        NgcKspServer::CredUIStringsContext::CredUIStringsContext((NgcKspServer::CredUIStringsContext *)v46, 0, 1);
        v25 = &Microsoft::WRL::Wrappers::HandleT<NgcRpcGestureInfoTraits>::`vftable';
        v26 = 0;
        v42 = 0;
        v43 = 0;
        ContainerMetadata = NgcKspServer::PromptForNewPin(
                              **(_QWORD **)a1,
                              **(_QWORD **)(a1 + 16),
                              1,
                              (unsigned int)v32,
                              (__int64)v46,
                              (__int64)&v25);
        if ( ContainerMetadata < 0 )
        {
          std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v42);
          v25 = &Microsoft::WRL::Wrappers::HandleT<NgcRpcGestureInfoTraits>::`vftable';
          Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v25);
          NgcKspServer::CredUIStringsContext::~CredUIStringsContext((NgcKspServer::CredUIStringsContext *)v46);
          v19 = hMem;
          hMem = 0;
          if ( v19 )
            LocalFree(v19);
          goto LABEL_19;
        }
        std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(
          v45,
          **(_QWORD **)(a1 + 24),
          **(_QWORD **)(a1 + 24) + **(unsigned int **)(a1 + 32));
        std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(
          v44,
          *(_QWORD *)(v26 + 8),
          *(_QWORD *)(v26 + 8) + *(unsigned int *)(v26 + 16));
        v20 = NgcKspServer::TransportManager::Instance();
        v21 = (_QWORD *)NgcKspServer::TransportManager::LocalTransport(v20, &p_hMem);
        LastError = NgcLocalTransport::LocalTransport::RecoverPin(*v21, v12, v45, v44);
        if ( Sid )
          std::_Ref_count_base::_Decref((std::_Ref_count_base *)Sid);
        std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v44);
        std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v45);
        std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v42);
        v25 = &Microsoft::WRL::Wrappers::HandleT<NgcRpcGestureInfoTraits>::`vftable';
        Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v25);
        NgcKspServer::CredUIStringsContext::~CredUIStringsContext((NgcKspServer::CredUIStringsContext *)v46);
      }
      else
      {
        LastError = GetLastError();
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
        {
          wil::details::in1diag3::Log_Win32(
            retaddr,
            (void *)0x692,
            (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\mgmtsrv.cpp",
            (const char *)LastError,
            v24);
        }
        else if ( (unsigned int)dword_180122070 > 2 )
        {
          v48 = LastError;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (__int64)&dword_180122070,
            (unsigned __int8 *)&dword_1800FF384,
            0,
            0,
            (__int64)&v48);
        }
        if ( (int)LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
      }
      v22 = hMem;
      hMem = 0;
      if ( v22 )
        LocalFree(v22);
      std::vector<unsigned char>::_Tidy(&v27);
      goto LABEL_48;
    }
    ContainerMetadata = NgcPolicy::NgcPolicy::Initialize(v32, &v27);
    if ( ContainerMetadata >= 0 )
      goto LABEL_32;
    if ( (unsigned int)dword_180122070 <= 2 )
      goto LABEL_19;
    v17 = &byte_1800FF3B7;
LABEL_25:
    v48 = ContainerMetadata;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_180122070,
      (unsigned __int8 *)v17,
      0,
      0,
      (__int64)&v48);
    goto LABEL_19;
  }
  v7 = I_CheckNgcApiAccessRight(v4, 0, 0, v3, 0);
  LastError = v7;
  if ( v7 >= 0 )
    goto LABEL_7;
  if ( (unsigned int)dword_180122070 > 2 )
  {
    v48 = v7;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_180122070,
      (unsigned __int8 *)&word_1800FF44E,
      0,
      0,
      (__int64)&v48);
  }
  return LastError;
}

```

## disassembly

```asm
0x18006cb40  mov     [rsp-8+arg_0], rbx
0x18006cb45  push    rbp
0x18006cb46  push    rsi
0x18006cb47  push    rdi
0x18006cb48  push    r12
0x18006cb4a  push    r14
0x18006cb4c  lea     rbp, [rsp-60h]
0x18006cb51  sub     rsp, 160h
0x18006cb58  mov     rsi, rcx
0x18006cb5b  lea     r12, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x18006cb62  mov     rcx, r12
0x18006cb65  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18006cb6a  mov     rdx, [rsi+8]
0x18006cb6e  mov     r9, [rdx]
0x18006cb71  mov     rdx, [rsi]
0x18006cb74  mov     rcx, [rdx]
0x18006cb77  xor     r14d, r14d
0x18006cb7a  mov     [rsp+180h+var_160], r14d; unsigned int
0x18006cb7f  xor     r8d, r8d
0x18006cb82  xor     edx, edx
0x18006cb84  test    al, al
0x18006cb86  jz      short loc_18006CBB3
0x18006cb88  call    I_CheckNgcApiAccessRight
0x18006cb8d  mov     ebx, eax
0x18006cb8f  test    eax, eax
0x18006cb91  jns     short loc_18006CBFD
0x18006cb93  mov     rcx, [rbp+88h]; this
0x18006cb9a  mov     r9d, eax; char *
0x18006cb9d  lea     r8, aOnecoreDsSecur_39; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x18006cba4  mov     edx, 638h; void *
0x18006cba9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006cbae  jmp     loc_18006D089
0x18006cbb3  call    I_CheckNgcApiAccessRight
0x18006cbb8  mov     ebx, eax
0x18006cbba  test    eax, eax
0x18006cbbc  jns     short loc_18006CBFD
0x18006cbbe  mov     ecx, cs:dword_180122070
0x18006cbc4  cmp     ecx, 2
0x18006cbc7  jbe     loc_18006D089
0x18006cbcd  mov     [rbp+80h+arg_8], eax
0x18006cbd3  lea     rax, [rbp+80h+arg_8]
0x18006cbda  mov     qword ptr [rsp+180h+var_160], rax
0x18006cbdf  xor     r9d, r9d
0x18006cbe2  xor     r8d, r8d
0x18006cbe5  lea     rdx, word_1800FF44E
0x18006cbec  lea     rcx, dword_180122070
0x18006cbf3  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18006cbf8  jmp     loc_18006D089
0x18006cbfd  mov     [rbp+80h+arg_18], r14
0x18006cc04  mov     rcx, r12
0x18006cc07  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18006cc0c  test    al, al
0x18006cc0e  jz      short loc_18006CC4E
0x18006cc10  call    ?Instance@TransportManager@NgcKspServer@@SAAEAV12@XZ; NgcKspServer::TransportManager::Instance(void)
0x18006cc15  mov     rcx, [rsi+8]
0x18006cc19  lea     rdx, [rbp+80h+arg_18]
0x18006cc20  mov     rcx, [rcx]
0x18006cc23  call    ?FindLocalContainer@TransportManager@NgcKspServer@@SAJPEBGPEAV?$unique_ptr@UNgcTransportContainerInfo@@U?$default_delete@UNgcTransportContainerInfo@@@std@@@std@@@Z; NgcKspServer::TransportManager::FindLocalContainer(ushort const *,std::unique_ptr<NgcTransportContainerInfo> *)
0x18006cc28  mov     ebx, eax
0x18006cc2a  test    eax, eax
0x18006cc2c  jns     short loc_18006CCAB
0x18006cc2e  mov     rcx, [rbp+88h]; this
0x18006cc35  mov     r9d, eax; char *
0x18006cc38  lea     r8, aOnecoreDsSecur_39; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x18006cc3f  mov     edx, 64Fh; void *
0x18006cc44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006cc49  jmp     loc_18006D07D
0x18006cc4e  call    ?Instance@TransportManager@NgcKspServer@@SAAEAV12@XZ; NgcKspServer::TransportManager::Instance(void)
0x18006cc53  mov     rcx, [rsi+8]
0x18006cc57  lea     rdx, [rbp+80h+arg_18]
0x18006cc5e  mov     rcx, [rcx]
0x18006cc61  call    ?FindLocalContainer@TransportManager@NgcKspServer@@SAJPEBGPEAV?$unique_ptr@UNgcTransportContainerInfo@@U?$default_delete@UNgcTransportContainerInfo@@@std@@@std@@@Z; NgcKspServer::TransportManager::FindLocalContainer(ushort const *,std::unique_ptr<NgcTransportContainerInfo> *)
0x18006cc66  mov     ebx, eax
0x18006cc68  test    eax, eax
0x18006cc6a  jns     short loc_18006CCAB
0x18006cc6c  mov     ecx, cs:dword_180122070
0x18006cc72  cmp     ecx, 2
0x18006cc75  jbe     loc_18006D07D
0x18006cc7b  mov     [rbp+80h+arg_8], eax
0x18006cc81  lea     rax, [rbp+80h+arg_8]
0x18006cc88  mov     qword ptr [rsp+180h+var_160], rax
0x18006cc8d  xor     r9d, r9d
0x18006cc90  xor     r8d, r8d
0x18006cc93  lea     rdx, byte_1800FF41B
0x18006cc9a  lea     rcx, dword_180122070
0x18006cca1  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18006cca6  jmp     loc_18006D07D
0x18006ccab  xorps   xmm0, xmm0
0x18006ccae  movdqu  [rsp+180h+var_140], xmm0
0x18006ccb4  mov     [rsp+180h+var_130], r14
0x18006ccb9  mov     rcx, r12
0x18006ccbc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18006ccc1  test    al, al
0x18006ccc3  jz      short loc_18006CD3B
0x18006ccc5  call    ?Instance@TransportManager@NgcKspServer@@SAAEAV12@XZ; NgcKspServer::TransportManager::Instance(void)
0x18006ccca  lea     rdx, [rsp+180h+var_128]
0x18006cccf  mov     rcx, rax
0x18006ccd2  call    ?LocalTransport@TransportManager@NgcKspServer@@QEBA?AV?$shared_ptr@VLocalTransport@NgcLocalTransport@@@std@@XZ; NgcKspServer::TransportManager::LocalTransport(void)
0x18006ccd7  nop
0x18006ccd8  lea     r9, [rsp+180h+var_140]
0x18006ccdd  mov     r8d, 2
0x18006cce3  mov     rbx, [rbp+80h+arg_18]
0x18006ccea  mov     rdx, rbx
0x18006cced  mov     rcx, [rax]
0x18006ccf0  call    ?GetContainerMetadata@LocalTransport@NgcLocalTransport@@UEAAJAEBU_GUID@@W4_NgcContainerMetadataType@@PEAV?$vector@EV?$allocator@E@std@@@std@@@Z; NgcLocalTransport::LocalTransport::GetContainerMetadata(_GUID const &,_NgcContainerMetadataType,std::vector<uchar> *)
0x18006ccf5  mov     edi, eax
0x18006ccf7  mov     rcx, [rsp+180h+Sid]; this
0x18006ccfc  test    rcx, rcx
0x18006ccff  jz      short loc_18006CD06
0x18006cd01  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18006cd06  test    edi, edi
0x18006cd08  jns     loc_18006CDBB
0x18006cd0e  mov     edx, 666h; void *
0x18006cd13  lea     r8, aOnecoreDsSecur_39; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x18006cd1a  mov     r9d, edi; char *
0x18006cd1d  mov     rcx, [rbp+88h]; this
0x18006cd24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006cd29  nop
0x18006cd2a  lea     rcx, [rsp+180h+var_140]
0x18006cd2f  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18006cd34  mov     ebx, edi
0x18006cd36  jmp     loc_18006D07D
0x18006cd3b  call    ?Instance@TransportManager@NgcKspServer@@SAAEAV12@XZ; NgcKspServer::TransportManager::Instance(void)
0x18006cd40  lea     rdx, [rsp+180h+var_128]
0x18006cd45  mov     rcx, rax
0x18006cd48  call    ?LocalTransport@TransportManager@NgcKspServer@@QEBA?AV?$shared_ptr@VLocalTransport@NgcLocalTransport@@@std@@XZ; NgcKspServer::TransportManager::LocalTransport(void)
0x18006cd4d  nop
0x18006cd4e  lea     r9, [rsp+180h+var_140]
0x18006cd53  mov     r8d, 2
0x18006cd59  mov     rbx, [rbp+80h+arg_18]
0x18006cd60  mov     rdx, rbx
0x18006cd63  mov     rcx, [rax]
0x18006cd66  call    ?GetContainerMetadata@LocalTransport@NgcLocalTransport@@UEAAJAEBU_GUID@@W4_NgcContainerMetadataType@@PEAV?$vector@EV?$allocator@E@std@@@std@@@Z; NgcLocalTransport::LocalTransport::GetContainerMetadata(_GUID const &,_NgcContainerMetadataType,std::vector<uchar> *)
0x18006cd6b  mov     edi, eax
0x18006cd6d  mov     rcx, [rsp+180h+Sid]; this
0x18006cd72  test    rcx, rcx
0x18006cd75  jz      short loc_18006CD7C
0x18006cd77  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18006cd7c  test    edi, edi
0x18006cd7e  jns     short loc_18006CDBB
0x18006cd80  mov     ecx, cs:dword_180122070
0x18006cd86  cmp     ecx, 2
0x18006cd89  jbe     short loc_18006CD2A
0x18006cd8b  lea     rdx, byte_1800FF3E7
0x18006cd92  xor     r9d, r9d
0x18006cd95  lea     rax, [rbp+80h+arg_8]
0x18006cd9c  xor     r8d, r8d
0x18006cd9f  mov     qword ptr [rsp+180h+var_160], rax
0x18006cda4  mov     [rbp+80h+arg_8], edi
0x18006cdaa  lea     rcx, dword_180122070
0x18006cdb1  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18006cdb6  jmp     loc_18006CD2A
0x18006cdbb  mov     [rsp+180h+var_110], r14b
0x18006cdc0  mov     [rsp+180h+var_10C], 1
0x18006cdc8  mov     [rsp+180h+var_108], 1
0x18006cdd1  mov     [rbp+80h+var_100], r14b
0x18006cdd5  mov     [rbp+80h+var_FC], 8
0x18006cddc  mov     [rbp+80h+var_F8], 7Fh
0x18006cde3  xorps   xmm0, xmm0
0x18006cde6  movdqu  [rbp+80h+var_F4], xmm0
0x18006cdeb  mov     [rbp+80h+var_E4], 2
0x18006cdf2  mov     [rbp+80h+var_E0], 1
0x18006cdfa  mov     [rbp+80h+var_D8], r14d
0x18006cdfe  mov     rcx, r12
0x18006ce01  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18006ce06  lea     rdx, [rsp+180h+var_140]
0x18006ce0b  lea     rcx, [rsp+180h+var_110]
0x18006ce10  test    al, al
0x18006ce12  jz      short loc_18006CE29
0x18006ce14  call    ?Initialize@NgcPolicy@1@QEAAJAEBV?$vector@EV?$allocator@E@std@@@std@@@Z; NgcPolicy::NgcPolicy::Initialize(std::vector<uchar> const &)
0x18006ce19  mov     edi, eax
0x18006ce1b  test    eax, eax
0x18006ce1d  jns     short loc_18006CE4F
0x18006ce1f  mov     edx, 67Bh
0x18006ce24  jmp     loc_18006CD13
0x18006ce29  call    ?Initialize@NgcPolicy@1@QEAAJAEBV?$vector@EV?$allocator@E@std@@@std@@@Z; NgcPolicy::NgcPolicy::Initialize(std::vector<uchar> const &)
0x18006ce2e  mov     edi, eax
0x18006ce30  test    eax, eax
0x18006ce32  jns     short loc_18006CE4F
0x18006ce34  mov     ecx, cs:dword_180122070
0x18006ce3a  cmp     ecx, 2
0x18006ce3d  jbe     loc_18006CD2A
0x18006ce43  lea     rdx, byte_1800FF3B7
0x18006ce4a  jmp     loc_18006CD92
0x18006ce4f  mov     [rbp+80h+hMem], r14
0x18006ce56  lea     rax, [rbp+80h+hMem]
0x18006ce5d  mov     [rsp+180h+var_128], rax
0x18006ce62  mov     [rsp+180h+Sid], r14
0x18006ce67  mov     [rsp+180h+var_118], 1
0x18006ce6c  mov     rcx, [rsi+8]
0x18006ce70  lea     rdx, [rsp+180h+Sid]; Sid
0x18006ce75  mov     rcx, [rcx]; StringSid
0x18006ce78  call    cs:__imp_ConvertStringSidToSidW
0x18006ce7e  mov     edi, eax
0x18006ce80  lea     rcx, [rsp+180h+var_128]
0x18006ce85  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18006ce8a  test    edi, edi
0x18006ce8c  jnz     short loc_18006CF0B
0x18006ce8e  call    cs:__imp_GetLastError
0x18006ce94  mov     ebx, eax
0x18006ce96  mov     rcx, r12
0x18006ce99  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18006ce9e  test    al, al
0x18006cea0  jz      short loc_18006CEBF
0x18006cea2  mov     rcx, [rbp+88h]; this
0x18006cea9  mov     r9d, ebx; char *
0x18006ceac  lea     r8, aOnecoreDsSecur_39; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x18006ceb3  mov     edx, 692h; void *
0x18006ceb8  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18006cebd  jmp     short loc_18006CEF5
0x18006cebf  mov     eax, cs:dword_180122070
0x18006cec5  cmp     eax, 2
0x18006cec8  jbe     short loc_18006CEF5
0x18006ceca  mov     [rbp+80h+arg_8], ebx
0x18006ced0  lea     rax, [rbp+80h+arg_8]
0x18006ced7  mov     qword ptr [rsp+180h+var_160], rax
0x18006cedc  xor     r9d, r9d
0x18006cedf  xor     r8d, r8d
0x18006cee2  lea     rdx, dword_1800FF384
0x18006cee9  lea     rcx, dword_180122070
0x18006cef0  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18006cef5  test    ebx, ebx
0x18006cef7  jle     loc_18006D058
0x18006cefd  movzx   ebx, bx
0x18006cf00  or      ebx, 80070000h
0x18006cf06  jmp     loc_18006D058
0x18006cf0b  mov     r8b, 1; bool
0x18006cf0e  xor     edx, edx; unsigned __int16 *
0x18006cf10  lea     rcx, [rbp+80h+var_80]; this
0x18006cf14  call    ??0CredUIStringsContext@NgcKspServer@@QEAA@PEBG_N@Z; NgcKspServer::CredUIStringsContext::CredUIStringsContext(ushort const *,bool)
0x18006cf19  nop
0x18006cf1a  lea     r12, ??_7?$HandleT@UNgcRpcGestureInfoTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<NgcRpcGestureInfoTraits>::`vftable'
0x18006cf21  mov     [rsp+180h+var_150], r12
0x18006cf26  mov     [rsp+180h+var_148], r14
0x18006cf2b  xorps   xmm0, xmm0
0x18006cf2e  movdqu  [rbp+80h+var_D0], xmm0
0x18006cf33  mov     [rbp+80h+var_C0], r14
0x18006cf37  mov     rdx, [rsi+10h]
0x18006cf3b  mov     rcx, [rsi]
0x18006cf3e  lea     rax, [rsp+180h+var_150]
0x18006cf43  mov     [rsp+180h+var_158], rax
0x18006cf48  lea     rax, [rbp+80h+var_80]
0x18006cf4c  mov     qword ptr [rsp+180h+var_160], rax
0x18006cf51  lea     r9, [rsp+180h+var_110]
0x18006cf56  mov     r8d, 1
0x18006cf5c  mov     rdx, [rdx]
0x18006cf5f  mov     rcx, [rcx]
0x18006cf62  call    ?PromptForNewPin@NgcKspServer@@YAJQEAXPEAUHWND__@@W4PromptForNewPinScenario@1@AEBVNgcPolicy@4@AEAUCredUIStringsContext@1@PEAV?$HandleT@UNgcRpcGestureInfoTraits@@@Wrappers@WRL@Microsoft@@@Z; NgcKspServer::PromptForNewPin(void * const,HWND__ *,NgcKspServer::PromptForNewPinScenario,NgcPolicy::NgcPolicy const &,NgcKspServer::CredUIStringsContext &,Microsoft::WRL::Wrappers::HandleT<NgcRpcGestureInfoTraits> *)
0x18006cf67  mov     edi, eax
0x18006cf69  test    eax, eax
0x18006cf6b  jns     short loc_18006CFB3
0x18006cf6d  lea     rcx, [rbp+80h+var_D0]
0x18006cf71  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x18006cf76  nop
0x18006cf77  mov     [rsp+180h+var_150], r12
0x18006cf7c  lea     rcx, [rsp+180h+var_150]
0x18006cf81  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x18006cf86  nop
0x18006cf87  lea     rcx, [rbp+80h+var_80]; this
0x18006cf8b  call    ??1CredUIStringsContext@NgcKspServer@@QEAA@XZ; NgcKspServer::CredUIStringsContext::~CredUIStringsContext(void)
0x18006cf90  nop
0x18006cf91  mov     rcx, [rbp+80h+hMem]; hMem
0x18006cf98  mov     [rbp+80h+hMem], r14
0x18006cf9f  test    rcx, rcx
0x18006cfa2  jz      loc_18006CD2A
0x18006cfa8  call    cs:__imp_LocalFree
0x18006cfae  jmp     loc_18006CD2A
0x18006cfb3  mov     rax, [rsi+18h]
0x18006cfb7  mov     rdx, [rax]
0x18006cfba  mov     rax, [rsi+20h]
0x18006cfbe  mov     r8d, [rax]
0x18006cfc1  add     r8, rdx
0x18006cfc4  lea     rcx, [rbp+80h+var_A0]
0x18006cfc8  call    ??$?0PEAE$0A@@?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@PEAE0AEBU?$secure_allocator@E@wil@@@Z; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(uchar *,uchar *,wil::secure_allocator<uchar> const &)
0x18006cfcd  nop
0x18006cfce  mov     rax, [rsp+180h+var_148]
0x18006cfd3  mov     rdx, [rax+8]
0x18006cfd7  mov     r8d, [rax+10h]
0x18006cfdb  add     r8, rdx
0x18006cfde  lea     rcx, [rbp+80h+var_B8]
0x18006cfe2  call    ??$?0PEAE$0A@@?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@PEAE0AEBU?$secure_allocator@E@wil@@@Z; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(uchar *,uchar *,wil::secure_allocator<uchar> const &)
0x18006cfe7  nop
0x18006cfe8  call    ?Instance@TransportManager@NgcKspServer@@SAAEAV12@XZ; NgcKspServer::TransportManager::Instance(void)
0x18006cfed  lea     rdx, [rsp+180h+var_128]
0x18006cff2  mov     rcx, rax
0x18006cff5  call    ?LocalTransport@TransportManager@NgcKspServer@@QEBA?AV?$shared_ptr@VLocalTransport@NgcLocalTransport@@@std@@XZ; NgcKspServer::TransportManager::LocalTransport(void)
0x18006cffa  nop
0x18006cffb  lea     r9, [rbp+80h+var_B8]
0x18006cfff  lea     r8, [rbp+80h+var_A0]
0x18006d003  mov     rdx, rbx
0x18006d006  mov     rcx, [rax]
0x18006d009  call    ?RecoverPin@LocalTransport@NgcLocalTransport@@UEAAJAEBU_GUID@@AEBV?$vector@EU?$secure_allocator@E@wil@@@std@@1@Z; NgcLocalTransport::LocalTransport::RecoverPin(_GUID const &,std::vector<uchar,wil::secure_allocator<uchar>> const &,std::vector<uchar,wil::secure_allocator<uchar>> const &)
0x18006d00e  mov     ebx, eax
0x18006d010  mov     rcx, [rsp+180h+Sid]; this
0x18006d015  test    rcx, rcx
0x18006d018  jz      short loc_18006D020
0x18006d01a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18006d01f  nop
0x18006d020  lea     rcx, [rbp+80h+var_B8]
0x18006d024  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
  ... truncated ...
```
