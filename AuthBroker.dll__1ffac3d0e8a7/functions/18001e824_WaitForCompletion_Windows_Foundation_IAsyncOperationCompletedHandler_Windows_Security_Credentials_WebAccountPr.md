# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *)

- ea: `0x18001e824`
- end: `0x18001e9a9`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `389`
- prototype: `__int64 __fastcall(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *pOperation, HRESULT, void *flags)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001ed50`

## callees

- `0x180006060`
- `0x18001e5ac`
- `0x18001e824`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18001e8cb`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18001e8cb`

## pseudocode

```c
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(
        Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *pOperation,
        HRESULT a2,
        void *flags)
{
  unsigned int v4; // edi
  WaitForCompletion::__l2::FTMEventDelegate *ptr; // rbx
  Windows::Foundation::IAsyncOperation_impl<Windows::Foundation::Internal::AggregateType<Windows::Security::Credentials::WebAccountProvider *,Windows::Security::Credentials::IWebAccountProvider *> >_vtbl *v6; // rax
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rdi
  HRESULT (__fastcall *v8)(IUnknown *, const _GUID *, void **); // rbx
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> > spOperation; // [rsp+30h] [rbp-28h] BYREF
  void *rgHandles[2]; // [rsp+38h] [rbp-20h] BYREF
  Microsoft::WRL::ComPtr<IAsyncInfo> spAsyncInfo; // [rsp+80h] [rbp+28h] BYREF
  HRESULT hr; // [rsp+88h] [rbp+30h] BYREF
  void *dwHandleIndex; // [rsp+90h] [rbp+38h] BYREF
  Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> >'::`2'::FTMEventDelegate> spCallback; // [rsp+98h] [rbp+40h] BYREF

  dwHandleIndex = flags;
  hr = a2;
  spOperation.ptr_ = pOperation;
  if ( pOperation )
    pOperation->AddRef(pOperation);
  spCallback.ptr_ = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&spCallback);
  hr = ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebAccountProvider_Credentials_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebAccountProvider_Credentials_Security_Windows___23___YAJPEAU__IAsyncOperation_PEAVWebAccountProvider_Credentials_Security_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebAccountProvider_Credentials_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebAccountProvider_Credentials_Security_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebAccountProvider_Credentials_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebAccountProvider_Credentials_Security_Windows___23___YAJPEAU__IAsyncOperation_PEAVWebAccountProvider_Credentials_Security_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(&spCallback.ptr_);
  v4 = hr;
  if ( hr >= 0 )
  {
    ptr = spCallback.ptr_;
    hr = pOperation->put_Completed(pOperation, spCallback.ptr_);
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
0x18001e824  mov     [rsp-20h+dwHandleIndex], r8
0x18001e829  mov     [rsp-20h+hr], edx
0x18001e82d  push    rbp
0x18001e82e  push    rbx
0x18001e82f  push    rsi
0x18001e830  push    rdi
0x18001e831  mov     rbp, rsp
0x18001e834  sub     rsp, 58h
0x18001e838  mov     [rbp+spOperation.ptr_], pOperation
0x18001e83c  mov     rsi, pOperation
0x18001e83f  test    pOperation, pOperation
0x18001e842  jz      short loc_18001E850
0x18001e844  mov     rax, [pOperation]
0x18001e847  mov     rax, [rax+8]
0x18001e84b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e850  lea     pOperation, [rbp+spCallback]; this
0x18001e854  mov     [rbp+spCallback.ptr_], 0
0x18001e85c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e861  lea     pOperation, [rbp+spCallback]; result
0x18001e865  call    ??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z; Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)
0x18001e86a  mov     [rbp+hr], eax
0x18001e86d  mov     edi, eax
0x18001e86f  test    eax, eax
0x18001e871  js      loc_18001E98C
0x18001e877  mov     rax, [rsi]
0x18001e87a  mov     pOperation, rsi
0x18001e87d  mov     rbx, [rbp+spCallback.ptr_]
0x18001e881  mov     rdx, rbx
0x18001e884  mov     rax, [rax+30h]
0x18001e888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e88d  mov     [rbp+hr], eax
0x18001e890  mov     edi, eax
0x18001e892  test    eax, eax
0x18001e894  js      loc_18001E98C
0x18001e89a  mov     rax, [rbx+38h]
0x18001e89e  lea     r9, [rbp+rgHandles]; pHandles
0x18001e8a2  mov     r8d, 1; cHandles
0x18001e8a8  mov     [rbp+rgHandles], rax
0x18001e8ac  lea     rax, [rbp+dwHandleIndex]
0x18001e8b0  mov     [rbp+rgHandles+8], 0
0x18001e8b8  or      edx, 0FFFFFFFFh; dwTimeout
0x18001e8bb  mov     dword ptr [rbp+dwHandleIndex], 0
0x18001e8c2  mov     [rsp+58h+lpdwindex], rax; lpdwindex
0x18001e8c7  lea     ecx, [r8+7]; dwFlags
0x18001e8cb  call    cs:__imp_CoWaitForMultipleHandles
0x18001e8d1  mov     [rbp+hr], eax
0x18001e8d4  test    eax, eax
0x18001e8d6  js      short loc_18001E928
0x18001e8d8  cmp     dword ptr [rbp+dwHandleIndex], 0
0x18001e8dc  jz      short loc_18001E928
0x18001e8de  mov     rax, [rsi]
0x18001e8e1  lea     pOperation, [rbp+spAsyncInfo]; this
0x18001e8e5  mov     [rbp+hr], 800704C7h
0x18001e8ec  mov     [rbp+spAsyncInfo.ptr_], 0
0x18001e8f4  mov     rdi, [rax]
0x18001e8f7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e8fc  lea     r8, [rbp+spAsyncInfo]
0x18001e900  mov     pOperation, rsi
0x18001e903  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18001e90a  mov     rax, rdi
0x18001e90d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e912  test    eax, eax
0x18001e914  js      short loc_18001E930
0x18001e916  mov     pOperation, [rbp+spAsyncInfo.ptr_]
0x18001e91a  mov     rax, [pOperation]
0x18001e91d  mov     rax, [rax+48h]
0x18001e921  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e926  jmp     short loc_18001E930
0x18001e928  mov     [rbp+spAsyncInfo.ptr_], 0
0x18001e930  cmp     [rbp+hr], 0
0x18001e934  jl      short loc_18001E980
0x18001e936  cmp     dword ptr [rbx+30h], 1
0x18001e93a  jz      short loc_18001E980
0x18001e93c  cmp     [rbp+spAsyncInfo.ptr_], 0
0x18001e941  jnz     short loc_18001E96C
0x18001e943  mov     rax, [rsi]
0x18001e946  lea     pOperation, [rbp+spAsyncInfo]; this
0x18001e94a  mov     rbx, [rax]
0x18001e94d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e952  lea     r8, [rbp+spAsyncInfo]
0x18001e956  mov     pOperation, rsi
0x18001e959  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18001e960  mov     rax, rbx
0x18001e963  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e968  test    eax, eax
0x18001e96a  js      short loc_18001E980
0x18001e96c  mov     pOperation, [rbp+spAsyncInfo.ptr_]
0x18001e970  lea     rdx, [rbp+hr]
0x18001e974  mov     rax, [pOperation]
0x18001e977  mov     rax, [rax+40h]
0x18001e97b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e980  lea     pOperation, [rbp+spAsyncInfo]; this
0x18001e984  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e989  mov     edi, [rbp+hr]
0x18001e98c  lea     pOperation, [rbp+spCallback]; this
0x18001e990  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e995  lea     pOperation, [rbp+spOperation]; this
0x18001e999  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e99e  mov     eax, edi
0x18001e9a0  add     rsp, 58h
0x18001e9a4  pop     rdi
0x18001e9a5  pop     rsi
0x18001e9a6  pop     rbx
0x18001e9a7  pop     rbp
0x18001e9a8  retn
```
