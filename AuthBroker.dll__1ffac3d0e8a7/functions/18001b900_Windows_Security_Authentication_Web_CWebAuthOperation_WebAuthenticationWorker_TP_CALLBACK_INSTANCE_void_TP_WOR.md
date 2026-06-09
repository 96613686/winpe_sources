# Windows::Security::Authentication::Web::CWebAuthOperation::WebAuthenticationWorker(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x18001b900`
- end: `0x18001b9e1`
- name: `?WebAuthenticationWorker@CWebAuthOperation@Web@Authentication@Security@Windows@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `225`
- prototype: `void __fastcall(_TP_CALLBACK_INSTANCE *pci, void *lpParam, _TP_WORK *__formal)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180015f40`
- `0x180019030`
- `0x180019484`
- `0x18001b7c8`
- `0x18001b900`
- `0x18001f5c4`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001b92c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001b92c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001b96f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001b96f`
- `api-ms-win-core-threadpool-l1-2-0!FreeLibraryWhenCallbackReturns` at `0x18001b9ce`
- `api-ms-win-core-threadpool-l1-2-0!FreeLibraryWhenCallbackReturns` at `0x18001b9ce`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18001b9c0`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18001b9c0`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18001b937`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18001b937`

## pseudocode

```c
void __fastcall Windows::Security::Authentication::Web::CWebAuthOperation::WebAuthenticationWorker(
        _TP_CALLBACK_INSTANCE *pci,
        Windows::Security::Authentication::Web::CWebAuthOperation *lpParam,
        _TP_WORK *__formal)
{
  signed __int32 v5; // eax
  Microsoft::WRL::CancelTransitionPolicy v6; // r8d
  void *v7; // r9
  void *m_hThreadReady; // rsi
  int v9; // edi
  Windows::Security::Authentication::Web::CWebAuthOperation_vtbl *v10; // rcx
  bool isBridgeableOperation; // [rsp+48h] [rbp+10h] BYREF
  HINSTANCE__ *hModule; // [rsp+58h] [rbp+20h] BYREF

  hModule = 0;
  GetModuleHandleExW(
    4u,
    (LPCWSTR)Windows::Security::Authentication::Web::CWebAuthOperation::WebAuthenticationWorker,
    &hModule);
  v5 = RoInitialize(1);
  m_hThreadReady = lpParam->m_hThreadReady;
  v9 = v5;
  if ( v5 < 0 )
  {
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(
      &lpParam->Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > > >,
      v5,
      v6,
      v7);
    v10 = lpParam->Microsoft::WRL::RuntimeClass<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > >::Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > >::Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::WebAuthenticationResult *>,IWeakReferenceSource,Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > >::Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::WebAuthenticationResult *>::Windows::Foundation::IAsyncOperation_impl<Windows::Foundation::Internal::AggregateType<Windows::Security::Authentication::Web::WebAuthenticationResult *,Windows::Security::Authentication::Web::IWebAuthenticationResult *> >::IInspectable::IUnknown::lpVtbl;
    lpParam->hrThreadInit = v9;
    v10->Release(lpParam);
    lpParam = 0;
  }
  SetEvent(m_hThreadReady);
  if ( v9 >= 0 )
  {
    isBridgeableOperation = Windows::Security::Authentication::Web::CWebAuthOperation::IsWAMBridgeableWABOperation(lpParam);
    WebAuthBridgeTelemetry::WamBridgeBrokerActivity::IsBridgeableOperation<bool>(
      &lpParam->m_WamBridgeBrokerActivity,
      &isBridgeableOperation);
    if ( Windows::Security::Authentication::Web::CWebAuthOperation::IsWAMBridgeableWABOperation(lpParam) )
      Windows::Security::Authentication::Web::CWebAuthOperation::LaunchWAMBridge(lpParam);
    else
      Windows::Security::Authentication::Web::CWebAuthOperation::LaunchAppContainerWorker(lpParam);
    lpParam->Release(lpParam);
    RoUninitialize();
  }
  FreeLibraryWhenCallbackReturns(pci, hModule);
}

```

## disassembly

```asm
0x18001b900  mov     [rsp+arg_0], rbx
0x18001b905  push    rbp
0x18001b906  push    rsi
0x18001b907  push    rdi
0x18001b908  sub     rsp, 20h
0x18001b90c  mov     rbx, lpParam
0x18001b90f  mov     [rsp+38h+hModule], 0
0x18001b918  mov     rbp, pci
0x18001b91b  lea     lpParam, ?WebAuthenticationWorker@CWebAuthOperation@Web@Authentication@Security@Windows@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; lpModuleName
0x18001b922  mov     ecx, 4; dwFlags
0x18001b927  lea     __formal, [rsp+38h+hModule]; phModule
0x18001b92c  call    cs:__imp_GetModuleHandleExW
0x18001b932  mov     ecx, 1
0x18001b937  call    cs:__imp_RoInitialize
0x18001b93d  mov     rsi, [rbx+0B0h]
0x18001b944  mov     edi, eax
0x18001b946  test    eax, eax
0x18001b948  jns     short loc_18001B96C
0x18001b94a  lea     pci, [rbx+10h]; this
0x18001b94e  mov     edx, eax; error
0x18001b950  call    ?TryTransitionToError@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVWebAuthenticationResult@Web@Authentication@Security@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::WebAuthenticationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)
0x18001b955  mov     pci, [rbx]
0x18001b958  mov     [rbx+0B8h], edi
0x18001b95e  mov     rax, [pci+10h]
0x18001b962  mov     pci, rbx
0x18001b965  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b96a  xor     ebx, ebx
0x18001b96c  mov     pci, rsi; hEvent
0x18001b96f  call    cs:__imp_SetEvent
0x18001b975  test    edi, edi
0x18001b977  js      short loc_18001B9C6
0x18001b979  mov     pci, rbx; this
0x18001b97c  call    ?IsWAMBridgeableWABOperation@CWebAuthOperation@Web@Authentication@Security@Windows@@AEAA_NXZ; Windows::Security::Authentication::Web::CWebAuthOperation::IsWAMBridgeableWABOperation(void)
0x18001b981  lea     pci, [rbx+118h]; this
0x18001b988  mov     [rsp+38h+isBridgeableOperation], al
0x18001b98c  lea     lpParam, [rsp+38h+isBridgeableOperation]; isBridgeableOperation
0x18001b991  call    ??$IsBridgeableOperation@_N@WamBridgeBrokerActivity@WebAuthBridgeTelemetry@@QEAAX$$QEA_N@Z; WebAuthBridgeTelemetry::WamBridgeBrokerActivity::IsBridgeableOperation<bool>(bool &&)
0x18001b996  mov     pci, rbx; this
0x18001b999  call    ?IsWAMBridgeableWABOperation@CWebAuthOperation@Web@Authentication@Security@Windows@@AEAA_NXZ; Windows::Security::Authentication::Web::CWebAuthOperation::IsWAMBridgeableWABOperation(void)
0x18001b99e  mov     pci, rbx; this
0x18001b9a1  test    al, al
0x18001b9a3  jz      short loc_18001B9AC
0x18001b9a5  call    ?LaunchWAMBridge@CWebAuthOperation@Web@Authentication@Security@Windows@@QEAAXXZ; Windows::Security::Authentication::Web::CWebAuthOperation::LaunchWAMBridge(void)
0x18001b9aa  jmp     short loc_18001B9B1
0x18001b9ac  call    ?LaunchAppContainerWorker@CWebAuthOperation@Web@Authentication@Security@Windows@@QEAAXXZ; Windows::Security::Authentication::Web::CWebAuthOperation::LaunchAppContainerWorker(void)
0x18001b9b1  mov     rax, [rbx]
0x18001b9b4  mov     pci, rbx
0x18001b9b7  mov     rax, [rax+10h]
0x18001b9bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b9c0  call    cs:__imp_RoUninitialize
0x18001b9c6  mov     lpParam, [rsp+38h+hModule]; mod
0x18001b9cb  mov     pci, rbp; pci
0x18001b9ce  call    cs:__imp_FreeLibraryWhenCallbackReturns
0x18001b9d4  mov     rbx, [rsp+38h+arg_0]
0x18001b9d9  add     rsp, 20h
0x18001b9dd  pop     rdi
0x18001b9de  pop     rsi
0x18001b9df  pop     rbp
0x18001b9e0  retn
```
