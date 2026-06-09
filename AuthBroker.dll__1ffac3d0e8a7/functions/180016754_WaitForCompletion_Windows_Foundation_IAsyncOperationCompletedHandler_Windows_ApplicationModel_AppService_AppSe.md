# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus> *,tagCOWAIT_FLAGS,void *)

- ea: `0x180016754`
- end: `0x1800168d9`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `389`
- prototype: `__int64 __fastcall(Windows::Foundation::IAsyncOperation<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus> *pOperation, HRESULT, void *flags)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800054bc`

## callees

- `0x180006060`
- `0x1800163f8`
- `0x180016754`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800167fb`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800167fb`

## pseudocode

```c
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus>,Windows::Foundation::IAsyncOperation<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus>>(
        Windows::Foundation::IAsyncOperation<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus> *pOperation,
        HRESULT a2,
        void *flags)
{
  unsigned int v4; // edi
  WaitForCompletion::__l2::FTMEventDelegate *ptr; // rbx
  Windows::Foundation::IAsyncOperation<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus>_vtbl *v6; // rax
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rdi
  HRESULT (__fastcall *v8)(IUnknown *, const _GUID *, void **); // rbx
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus> > spOperation; // [rsp+30h] [rbp-28h] BYREF
  void *rgHandles[2]; // [rsp+38h] [rbp-20h] BYREF
  Microsoft::WRL::ComPtr<IAsyncInfo> spAsyncInfo; // [rsp+80h] [rbp+28h] BYREF
  HRESULT hr; // [rsp+88h] [rbp+30h] BYREF
  void *dwHandleIndex; // [rsp+90h] [rbp+38h] BYREF
  Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus>,Windows::Foundation::IAsyncOperation<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus> >'::`2'::FTMEventDelegate> spCallback; // [rsp+98h] [rbp+40h] BYREF

  dwHandleIndex = flags;
  hr = a2;
  spOperation.ptr_ = pOperation;
  if ( pOperation )
    pOperation->AddRef(pOperation);
  spCallback.ptr_ = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&spCallback);
  hr = ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_W4AppServiceConnectionStatus_AppService_ApplicationModel_Windows___Foundation_Windows__U__IAsyncOperation_W4AppServiceConnectionStatus_AppService_ApplicationModel_Windows___23___YAJPEAU__IAsyncOperation_W4AppServiceConnectionStatus_AppService_ApplicationModel_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_W4AppServiceConnectionStatus_AppService_ApplicationModel_Windows___Foundation_Windows__U__IAsyncOperation_W4AppServiceConnectionStatus_AppService_ApplicationModel_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_W4AppServiceConnectionStatus_AppService_ApplicationModel_Windows___Foundation_Windows__U__IAsyncOperation_W4AppServiceConnectionStatus_AppService_ApplicationModel_Windows___23___YAJPEAU__IAsyncOperation_W4AppServiceConnectionStatus_AppService_ApplicationModel_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(&spCallback.ptr_);
  v4 = hr;
  if ( hr >= 0 )
  {
    ptr = spCallback.ptr_;
    hr = pOperation->put_Completed(
           pOperation,
           (Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus> *)spCallback.ptr_);
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
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&spOperation);
  return v4;
}

```

## disassembly

```asm
0x180016754  mov     [rsp-20h+dwHandleIndex], r8
0x180016759  mov     [rsp-20h+hr], edx
0x18001675d  push    rbp
0x18001675e  push    rbx
0x18001675f  push    rsi
0x180016760  push    rdi
0x180016761  mov     rbp, rsp
0x180016764  sub     rsp, 58h
0x180016768  mov     [rbp+spOperation.ptr_], pOperation
0x18001676c  mov     rsi, pOperation
0x18001676f  test    pOperation, pOperation
0x180016772  jz      short loc_180016780
0x180016774  mov     rax, [pOperation]
0x180016777  mov     rax, [rax+8]
0x18001677b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016780  lea     pOperation, [rbp+spCallback]; this
0x180016784  mov     [rbp+spCallback.ptr_], 0
0x18001678c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180016791  lea     pOperation, [rbp+spCallback]; result
0x180016795  call    ??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z; Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)
0x18001679a  mov     [rbp+hr], eax
0x18001679d  mov     edi, eax
0x18001679f  test    eax, eax
0x1800167a1  js      loc_1800168BC
0x1800167a7  mov     rax, [rsi]
0x1800167aa  mov     pOperation, rsi
0x1800167ad  mov     rbx, [rbp+spCallback.ptr_]
0x1800167b1  mov     rdx, rbx
0x1800167b4  mov     rax, [rax+30h]
0x1800167b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167bd  mov     [rbp+hr], eax
0x1800167c0  mov     edi, eax
0x1800167c2  test    eax, eax
0x1800167c4  js      loc_1800168BC
0x1800167ca  mov     rax, [rbx+38h]
0x1800167ce  lea     r9, [rbp+rgHandles]; pHandles
0x1800167d2  mov     r8d, 1; cHandles
0x1800167d8  mov     [rbp+rgHandles], rax
0x1800167dc  lea     rax, [rbp+dwHandleIndex]
0x1800167e0  mov     [rbp+rgHandles+8], 0
0x1800167e8  or      edx, 0FFFFFFFFh; dwTimeout
0x1800167eb  mov     dword ptr [rbp+dwHandleIndex], 0
0x1800167f2  mov     [rsp+58h+lpdwindex], rax; lpdwindex
0x1800167f7  lea     ecx, [r8+7]; dwFlags
0x1800167fb  call    cs:__imp_CoWaitForMultipleHandles
0x180016801  mov     [rbp+hr], eax
0x180016804  test    eax, eax
0x180016806  js      short loc_180016858
0x180016808  cmp     dword ptr [rbp+dwHandleIndex], 0
0x18001680c  jz      short loc_180016858
0x18001680e  mov     rax, [rsi]
0x180016811  lea     pOperation, [rbp+spAsyncInfo]; this
0x180016815  mov     [rbp+hr], 800704C7h
0x18001681c  mov     [rbp+spAsyncInfo.ptr_], 0
0x180016824  mov     rdi, [rax]
0x180016827  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001682c  lea     r8, [rbp+spAsyncInfo]
0x180016830  mov     pOperation, rsi
0x180016833  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18001683a  mov     rax, rdi
0x18001683d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016842  test    eax, eax
0x180016844  js      short loc_180016860
0x180016846  mov     pOperation, [rbp+spAsyncInfo.ptr_]
0x18001684a  mov     rax, [pOperation]
0x18001684d  mov     rax, [rax+48h]
0x180016851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016856  jmp     short loc_180016860
0x180016858  mov     [rbp+spAsyncInfo.ptr_], 0
0x180016860  cmp     [rbp+hr], 0
0x180016864  jl      short loc_1800168B0
0x180016866  cmp     dword ptr [rbx+30h], 1
0x18001686a  jz      short loc_1800168B0
0x18001686c  cmp     [rbp+spAsyncInfo.ptr_], 0
0x180016871  jnz     short loc_18001689C
0x180016873  mov     rax, [rsi]
0x180016876  lea     pOperation, [rbp+spAsyncInfo]; this
0x18001687a  mov     rbx, [rax]
0x18001687d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180016882  lea     r8, [rbp+spAsyncInfo]
0x180016886  mov     pOperation, rsi
0x180016889  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180016890  mov     rax, rbx
0x180016893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016898  test    eax, eax
0x18001689a  js      short loc_1800168B0
0x18001689c  mov     pOperation, [rbp+spAsyncInfo.ptr_]
0x1800168a0  lea     rdx, [rbp+hr]
0x1800168a4  mov     rax, [pOperation]
0x1800168a7  mov     rax, [rax+40h]
0x1800168ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168b0  lea     pOperation, [rbp+spAsyncInfo]; this
0x1800168b4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800168b9  mov     edi, [rbp+hr]
0x1800168bc  lea     pOperation, [rbp+spCallback]; this
0x1800168c0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800168c5  lea     pOperation, [rbp+spOperation]; this
0x1800168c9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800168ce  mov     eax, edi
0x1800168d0  add     rsp, 58h
0x1800168d4  pop     rdi
0x1800168d5  pop     rsi
0x1800168d6  pop     rbx
0x1800168d7  pop     rbp
0x1800168d8  retn
```
