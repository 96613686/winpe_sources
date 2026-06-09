# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> *,tagCOWAIT_FLAGS,void *)

- ea: `0x180006a58`
- end: `0x180006be4`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `396`
- prototype: `__int64 __fastcall(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> *pOperation, HRESULT, void *flags)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800054bc`

## callees

- `0x180006060`
- `0x180006a58`
- `0x1800162bc`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180006afb`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180006afb`

## pseudocode

```c
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *>>(
        Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> *pOperation,
        HRESULT a2,
        void *flags)
{
  unsigned int v4; // edi
  WaitForCompletion::__l2::FTMEventDelegate *ptr; // rbx
  Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *>_vtbl *v6; // rax
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rdi
  HRESULT (__fastcall *v8)(IUnknown *, const _GUID *, void **); // rbx
  void *rgHandles[2]; // [rsp+30h] [rbp-18h] BYREF
  Microsoft::WRL::ComPtr<IAsyncInfo> spAsyncInfo; // [rsp+70h] [rbp+28h] BYREF
  HRESULT hr; // [rsp+78h] [rbp+30h] BYREF
  void *dwHandleIndex; // [rsp+80h] [rbp+38h] BYREF
  Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> >'::`2'::FTMEventDelegate> spCallback; // [rsp+88h] [rbp+40h] BYREF

  dwHandleIndex = flags;
  hr = a2;
  if ( pOperation )
    pOperation->AddRef(pOperation);
  spCallback.ptr_ = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&spCallback);
  hr = ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVAppServiceResponse_AppService_ApplicationModel_Windows___Foundation_Windows__U__IAsyncOperation_PEAVAppServiceResponse_AppService_ApplicationModel_Windows___23___YAJPEAU__IAsyncOperation_PEAVAppServiceResponse_AppService_ApplicationModel_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVAppServiceResponse_AppService_ApplicationModel_Windows___Foundation_Windows__U__IAsyncOperation_PEAVAppServiceResponse_AppService_ApplicationModel_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVAppServiceResponse_AppService_ApplicationModel_Windows___Foundation_Windows__U__IAsyncOperation_PEAVAppServiceResponse_AppService_ApplicationModel_Windows___23___YAJPEAU__IAsyncOperation_PEAVAppServiceResponse_AppService_ApplicationModel_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(&spCallback.ptr_);
  v4 = hr;
  if ( hr >= 0 )
  {
    ptr = spCallback.ptr_;
    hr = pOperation->put_Completed(
           pOperation,
           (Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *> *)spCallback.ptr_);
    v4 = hr;
    if ( hr >= 0 )
    {
      rgHandles[0] = ptr->_hEventCompleted;
      rgHandles[1] = 0;
      LODWORD(dwHandleIndex) = 0;
      hr = CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, rgHandles, (LPDWORD)&dwHandleIndex);
      if ( hr >= 0 && (_DWORD)dwHandleIndex )
      {
        v6 = pOperation->lpVtbl;
        hr = -2147023673;
        spAsyncInfo.ptr_ = 0;
        QueryInterface = v6->QueryInterface;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&spAsyncInfo);
        if ( QueryInterface(pOperation, &GUID_00000036_0000_0000_c000_000000000046, (void **)&spAsyncInfo.ptr_) >= 0 )
          spAsyncInfo.ptr_->Cancel(spAsyncInfo.ptr_);
      }
      else
      {
        spAsyncInfo.ptr_ = 0;
      }
      if ( hr >= 0 && ptr->_status != Completed )
      {
        if ( spAsyncInfo.ptr_
          || (v8 = pOperation->QueryInterface,
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&spAsyncInfo),
              v8(pOperation, &GUID_00000036_0000_0000_c000_000000000046, (void **)&spAsyncInfo.ptr_) >= 0) )
        {
          spAsyncInfo.ptr_->get_ErrorCode(spAsyncInfo.ptr_, &hr);
        }
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&spAsyncInfo);
      v4 = hr;
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&spCallback);
  if ( pOperation )
    pOperation->Release(pOperation);
  return v4;
}

```

## disassembly

```asm
0x180006a58  mov     [rsp-20h+dwHandleIndex], r8
0x180006a5d  mov     [rsp-20h+hr], edx
0x180006a61  push    rbp
0x180006a62  push    rbx
0x180006a63  push    rsi
0x180006a64  push    rdi
0x180006a65  mov     rbp, rsp
0x180006a68  sub     rsp, 48h
0x180006a6c  mov     rsi, pOperation
0x180006a6f  test    pOperation, pOperation
0x180006a72  jz      short loc_180006A80
0x180006a74  mov     rax, [pOperation]
0x180006a77  mov     rax, [rax+8]
0x180006a7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a80  lea     pOperation, [rbp+spCallback]; this
0x180006a84  mov     [rbp+spCallback.ptr_], 0
0x180006a8c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180006a91  lea     pOperation, [rbp+spCallback]; result
0x180006a95  call    ??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z; Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)
0x180006a9a  mov     [rbp+hr], eax
0x180006a9d  mov     edi, eax
0x180006a9f  test    eax, eax
0x180006aa1  js      loc_180006BBC
0x180006aa7  mov     rax, [rsi]
0x180006aaa  mov     pOperation, rsi
0x180006aad  mov     rbx, [rbp+spCallback.ptr_]
0x180006ab1  mov     rdx, rbx
0x180006ab4  mov     rax, [rax+30h]
0x180006ab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006abd  mov     [rbp+hr], eax
0x180006ac0  mov     edi, eax
0x180006ac2  test    eax, eax
0x180006ac4  js      loc_180006BBC
0x180006aca  mov     rax, [rbx+38h]
0x180006ace  lea     r9, [rbp+rgHandles]; pHandles
0x180006ad2  mov     r8d, 1; cHandles
0x180006ad8  mov     [rbp+rgHandles], rax
0x180006adc  lea     rax, [rbp+dwHandleIndex]
0x180006ae0  mov     [rbp+rgHandles+8], 0
0x180006ae8  or      edx, 0FFFFFFFFh; dwTimeout
0x180006aeb  mov     dword ptr [rbp+dwHandleIndex], 0
0x180006af2  mov     [rsp+48h+lpdwindex], rax; lpdwindex
0x180006af7  lea     ecx, [r8+7]; dwFlags
0x180006afb  call    cs:__imp_CoWaitForMultipleHandles
0x180006b01  mov     [rbp+hr], eax
0x180006b04  test    eax, eax
0x180006b06  js      short loc_180006B58
0x180006b08  cmp     dword ptr [rbp+dwHandleIndex], 0
0x180006b0c  jz      short loc_180006B58
0x180006b0e  mov     rax, [rsi]
0x180006b11  lea     pOperation, [rbp+spAsyncInfo]; this
0x180006b15  mov     [rbp+hr], 800704C7h
0x180006b1c  mov     [rbp+spAsyncInfo.ptr_], 0
0x180006b24  mov     rdi, [rax]
0x180006b27  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180006b2c  lea     r8, [rbp+spAsyncInfo]
0x180006b30  mov     pOperation, rsi
0x180006b33  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180006b3a  mov     rax, rdi
0x180006b3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b42  test    eax, eax
0x180006b44  js      short loc_180006B60
0x180006b46  mov     pOperation, [rbp+spAsyncInfo.ptr_]
0x180006b4a  mov     rax, [pOperation]
0x180006b4d  mov     rax, [rax+48h]
0x180006b51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b56  jmp     short loc_180006B60
0x180006b58  mov     [rbp+spAsyncInfo.ptr_], 0
0x180006b60  cmp     [rbp+hr], 0
0x180006b64  jl      short loc_180006BB0
0x180006b66  cmp     dword ptr [rbx+30h], 1
0x180006b6a  jz      short loc_180006BB0
0x180006b6c  cmp     [rbp+spAsyncInfo.ptr_], 0
0x180006b71  jnz     short loc_180006B9C
0x180006b73  mov     rax, [rsi]
0x180006b76  lea     pOperation, [rbp+spAsyncInfo]; this
0x180006b7a  mov     rbx, [rax]
0x180006b7d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180006b82  lea     r8, [rbp+spAsyncInfo]
0x180006b86  mov     pOperation, rsi
0x180006b89  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180006b90  mov     rax, rbx
0x180006b93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b98  test    eax, eax
0x180006b9a  js      short loc_180006BB0
0x180006b9c  mov     pOperation, [rbp+spAsyncInfo.ptr_]
0x180006ba0  lea     rdx, [rbp+hr]
0x180006ba4  mov     rax, [pOperation]
0x180006ba7  mov     rax, [rax+40h]
0x180006bab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bb0  lea     pOperation, [rbp+spAsyncInfo]; this
0x180006bb4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180006bb9  mov     edi, [rbp+hr]
0x180006bbc  lea     pOperation, [rbp+spCallback]; this
0x180006bc0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180006bc5  test    rsi, rsi
0x180006bc8  jz      short loc_180006BD9
0x180006bca  mov     pOperation, [rsi]
0x180006bcd  mov     rax, [pOperation+10h]
0x180006bd1  mov     pOperation, rsi
0x180006bd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bd9  mov     eax, edi
0x180006bdb  add     rsp, 48h
0x180006bdf  pop     rdi
0x180006be0  pop     rsi
0x180006be1  pop     rbx
0x180006be2  pop     rbp
0x180006be3  retn
```
