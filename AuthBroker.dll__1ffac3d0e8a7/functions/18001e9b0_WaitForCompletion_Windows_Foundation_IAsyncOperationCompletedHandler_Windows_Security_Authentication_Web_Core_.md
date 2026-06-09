# WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)

- ea: `0x18001e9b0`
- end: `0x18001eb35`
- name: `??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z`
- size: `389`
- prototype: `__int64 __fastcall(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *pOperation, HRESULT, void *flags)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001f2c8`

## callees

- `0x180006060`
- `0x18001e6e8`
- `0x18001e9b0`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18001ea57`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18001ea57`

## pseudocode

```c
__int64 __fastcall WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(
        Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *pOperation,
        HRESULT a2,
        void *flags)
{
  unsigned int v4; // edi
  WaitForCompletion::__l2::FTMEventDelegate *ptr; // rbx
  Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>_vtbl *v6; // rax
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rdi
  HRESULT (__fastcall *v8)(IUnknown *, const _GUID *, void **); // rbx
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> > spOperation; // [rsp+30h] [rbp-28h] BYREF
  void *rgHandles[2]; // [rsp+38h] [rbp-20h] BYREF
  Microsoft::WRL::ComPtr<IAsyncInfo> spAsyncInfo; // [rsp+80h] [rbp+28h] BYREF
  HRESULT hr; // [rsp+88h] [rbp+30h] BYREF
  void *dwHandleIndex; // [rsp+90h] [rbp+38h] BYREF
  Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> spCallback; // [rsp+98h] [rbp+40h] BYREF

  dwHandleIndex = flags;
  hr = a2;
  spOperation.ptr_ = pOperation;
  if ( pOperation )
    pOperation->AddRef(pOperation);
  spCallback.ptr_ = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&spCallback);
  hr = ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___23___YAJPEAU__IAsyncOperation_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___Foundation_Windows__U__IAsyncOperation_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___23___YAJPEAU__IAsyncOperation_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(&spCallback.ptr_);
  v4 = hr;
  if ( hr >= 0 )
  {
    ptr = spCallback.ptr_;
    hr = pOperation->put_Completed(
           pOperation,
           (Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *)spCallback.ptr_);
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
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&spCallback);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)&spOperation);
  return v4;
}

```

## disassembly

```asm
0x18001e9b0  mov     [rsp-20h+dwHandleIndex], r8
0x18001e9b5  mov     [rsp-20h+hr], edx
0x18001e9b9  push    rbp
0x18001e9ba  push    rbx
0x18001e9bb  push    rsi
0x18001e9bc  push    rdi
0x18001e9bd  mov     rbp, rsp
0x18001e9c0  sub     rsp, 58h
0x18001e9c4  mov     [rbp+spOperation.ptr_], pOperation
0x18001e9c8  mov     rsi, pOperation
0x18001e9cb  test    pOperation, pOperation
0x18001e9ce  jz      short loc_18001E9DC
0x18001e9d0  mov     rax, [pOperation]
0x18001e9d3  mov     rax, [rax+8]
0x18001e9d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e9dc  lea     pOperation, [rbp+spCallback]; this
0x18001e9e0  mov     [rbp+spCallback.ptr_], 0
0x18001e9e8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001e9ed  lea     pOperation, [rbp+spCallback]; result
0x18001e9f1  call    ??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z; Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)
0x18001e9f6  mov     [rbp+hr], eax
0x18001e9f9  mov     edi, eax
0x18001e9fb  test    eax, eax
0x18001e9fd  js      loc_18001EB18
0x18001ea03  mov     rax, [rsi]
0x18001ea06  mov     pOperation, rsi
0x18001ea09  mov     rbx, [rbp+spCallback.ptr_]
0x18001ea0d  mov     rdx, rbx
0x18001ea10  mov     rax, [rax+30h]
0x18001ea14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea19  mov     [rbp+hr], eax
0x18001ea1c  mov     edi, eax
0x18001ea1e  test    eax, eax
0x18001ea20  js      loc_18001EB18
0x18001ea26  mov     rax, [rbx+38h]
0x18001ea2a  lea     r9, [rbp+rgHandles]; pHandles
0x18001ea2e  mov     r8d, 1; cHandles
0x18001ea34  mov     [rbp+rgHandles], rax
0x18001ea38  lea     rax, [rbp+dwHandleIndex]
0x18001ea3c  mov     [rbp+rgHandles+8], 0
0x18001ea44  or      edx, 0FFFFFFFFh; dwTimeout
0x18001ea47  mov     dword ptr [rbp+dwHandleIndex], 0
0x18001ea4e  mov     [rsp+58h+lpdwindex], rax; lpdwindex
0x18001ea53  lea     ecx, [r8+7]; dwFlags
0x18001ea57  call    cs:__imp_CoWaitForMultipleHandles
0x18001ea5d  mov     [rbp+hr], eax
0x18001ea60  test    eax, eax
0x18001ea62  js      short loc_18001EAB4
0x18001ea64  cmp     dword ptr [rbp+dwHandleIndex], 0
0x18001ea68  jz      short loc_18001EAB4
0x18001ea6a  mov     rax, [rsi]
0x18001ea6d  lea     pOperation, [rbp+spAsyncInfo]; this
0x18001ea71  mov     [rbp+hr], 800704C7h
0x18001ea78  mov     [rbp+spAsyncInfo.ptr_], 0
0x18001ea80  mov     rdi, [rax]
0x18001ea83  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ea88  lea     r8, [rbp+spAsyncInfo]
0x18001ea8c  mov     pOperation, rsi
0x18001ea8f  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18001ea96  mov     rax, rdi
0x18001ea99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea9e  test    eax, eax
0x18001eaa0  js      short loc_18001EABC
0x18001eaa2  mov     pOperation, [rbp+spAsyncInfo.ptr_]
0x18001eaa6  mov     rax, [pOperation]
0x18001eaa9  mov     rax, [rax+48h]
0x18001eaad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eab2  jmp     short loc_18001EABC
0x18001eab4  mov     [rbp+spAsyncInfo.ptr_], 0
0x18001eabc  cmp     [rbp+hr], 0
0x18001eac0  jl      short loc_18001EB0C
0x18001eac2  cmp     dword ptr [rbx+30h], 1
0x18001eac6  jz      short loc_18001EB0C
0x18001eac8  cmp     [rbp+spAsyncInfo.ptr_], 0
0x18001eacd  jnz     short loc_18001EAF8
0x18001eacf  mov     rax, [rsi]
0x18001ead2  lea     pOperation, [rbp+spAsyncInfo]; this
0x18001ead6  mov     rbx, [rax]
0x18001ead9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001eade  lea     r8, [rbp+spAsyncInfo]
0x18001eae2  mov     pOperation, rsi
0x18001eae5  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18001eaec  mov     rax, rbx
0x18001eaef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eaf4  test    eax, eax
0x18001eaf6  js      short loc_18001EB0C
0x18001eaf8  mov     pOperation, [rbp+spAsyncInfo.ptr_]
0x18001eafc  lea     rdx, [rbp+hr]
0x18001eb00  mov     rax, [pOperation]
0x18001eb03  mov     rax, [rax+40h]
0x18001eb07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb0c  lea     pOperation, [rbp+spAsyncInfo]; this
0x18001eb10  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001eb15  mov     edi, [rbp+hr]
0x18001eb18  lea     pOperation, [rbp+spCallback]; this
0x18001eb1c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001eb21  lea     pOperation, [rbp+spOperation]; this
0x18001eb25  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001eb2a  mov     eax, edi
0x18001eb2c  add     rsp, 58h
0x18001eb30  pop     rdi
0x18001eb31  pop     rsi
0x18001eb32  pop     rbx
0x18001eb33  pop     rbp
0x18001eb34  retn
```
