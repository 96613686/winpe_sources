# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x180003c60`
- end: `0x180003e71`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVApplicationData@Storage@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `529`
- prototype: `HRESULT __fastcall(Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,1,Microsoft::WRL::AsyncOptions<-1,0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > *this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180004100`

## callees

- `0x180003820`
- `0x180003c60`
- `0x180004058`
- `0x18000412c`
- `0x180004198`
- `0x1800041c8`
- `0x1800042ac`
- `0x180004340`
- `0x18002206c`
- `0x180022178`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180003d8d`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180003d8d`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180003d5e`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180003d5e`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x180003dfa`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x180003dfa`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
        Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,1,Microsoft::WRL::AsyncOptions<-1,0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > *this,
        Microsoft::WRL::CancelTransitionPolicy a2)
{
  unsigned int v3; // esi
  __int64 v4; // rcx
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rbx
  volatile Microsoft::WRL::Details::AsyncStatusInternal currentStatus; // ecx
  const _GUID *v7; // rdx
  bool v8; // dl
  IRpcOptions *ptr; // rbx
  Windows::Foundation::IAsyncOperation<Windows::Storage::ApplicationData *> *v10; // rsi
  HRESULT v11; // eax
  Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&Windows::Storage::StateABIImplementation::ClearOperationDefaultName,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > *v12; // rcx
  Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *> *v13; // rcx
  Windows::Foundation::IAsyncOperation<Windows::Storage::ApplicationData *> *v14; // rcx
  AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Storage::ApplicationData *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *> > b1; // [rsp+30h] [rbp-18h] BYREF
  Microsoft::WRL::Details::AsyncStatusInternal current; // [rsp+70h] [rbp+28h] BYREF
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *> > completedDelegateLocal; // [rsp+78h] [rbp+30h] BYREF
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::ApplicationData *> > operationInterface; // [rsp+80h] [rbp+38h] BYREF
  Microsoft::WRL::ComPtr<IRpcOptions> spRpcOptions; // [rsp+88h] [rbp+40h] BYREF

  v3 = 0;
  Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToCompleted(
    this,
    a2);
  if ( *(int *)(v4 + 136) > 0 && _InterlockedIncrement((volatile signed __int32 *)(v4 + 16)) == 1 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
    operationInterface.ptr_ = 0;
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::Storage::StateABIImplementation::SetVersionAsyncOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete((Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&Windows::Storage::StateABIImplementation::ClearOperationDefaultName,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > *)this);
    QueryInterface = this->QueryInterface;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *)&operationInterface);
    if ( QueryInterface(this, &GUID_31456b58_a5cb_5c5b_bd6e_ccce3a7bf4b4, (void **)&operationInterface.ptr_) >= 0 )
    {
      currentStatus = this->currentStatus_;
      current = _Undefined;
      _InterlockedCompareExchange((volatile signed __int32 *)&current, currentStatus, -2);
      completedDelegateLocal.ptr_ = 0;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *)&completedDelegateLocal);
      if ( (int)Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>>::CopyLocal(
                  &this->completedDelegate_,
                  v7,
                  (void **)&completedDelegateLocal.ptr_) >= 0 )
      {
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::Storage::StateABIImplementation::SetVersionAsyncOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart((Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&Windows::Storage::StateABIImplementation::ClearOperationDefaultName,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > *)this);
        spRpcOptions.ptr_ = 0;
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *)&spRpcOptions);
        RpcOptionsHelper::GetRpcOptions(completedDelegateLocal.ptr_, v8, &spRpcOptions.ptr_);
        ptr = spRpcOptions.ptr_;
        b1.spStream_.ptr_ = 0;
        b1.hr_ = 0;
        if ( spRpcOptions.ptr_ && completedDelegateLocal.ptr_ )
        {
          v10 = operationInterface.ptr_;
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *)&b1);
          b1.hr_ = CreateStreamOnHGlobal(0, 1, &b1.spStream_.ptr_);
          if ( b1.hr_ >= 0 )
            b1.hr_ = CoMarshalInterface(b1.spStream_.ptr_, &GUID_00000000_0000_0000_c000_000000000046, v10, 0, 0, 1u);
        }
        else
        {
          b1.hr_ = -2147467262;
        }
        v11 = completedDelegateLocal.ptr_->Invoke(
                completedDelegateLocal.ptr_,
                operationInterface.ptr_,
                (ABI::Windows::Foundation::AsyncStatus)current);
        v3 = Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireCompletionErrorPropagationPolicyFilter(
               v11,
               completedDelegateLocal.ptr_,
               this->completedDelegateBucketAssist_);
        Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(this);
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::Storage::StateABIImplementation::SetVersionAsyncOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(v12);
        if ( b1.hr_ >= 0 )
        {
          ((void (__fastcall *)(IStream *, _QWORD, _QWORD, _QWORD))b1.spStream_.ptr_->Seek)(b1.spStream_.ptr_, 0, 0, 0);
          CoReleaseMarshalData(b1.spStream_.ptr_);
        }
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *)&b1);
        if ( ptr )
          ptr->Release(ptr);
      }
      v13 = completedDelegateLocal.ptr_;
      if ( completedDelegateLocal.ptr_ )
      {
        completedDelegateLocal.ptr_ = 0;
        v13->Release(v13);
      }
    }
    v14 = operationInterface.ptr_;
    if ( operationInterface.ptr_ )
    {
      operationInterface.ptr_ = 0;
      v14->Release(v14);
    }
    this->Release(this);
  }
  return v3;
}

```

## disassembly

```asm
0x180003c60  push    rbp
0x180003c62  push    rbx
0x180003c63  push    rsi
0x180003c64  push    rdi
0x180003c65  mov     rbp, rsp
0x180003c68  sub     rsp, 48h
0x180003c6c  mov     rdi, this
0x180003c6f  xor     esi, esi
0x180003c71  call    ?TryTransitionToCompleted@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVApplicationData@Storage@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NW4CancelTransitionPolicy@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToCompleted(Microsoft::WRL::CancelTransitionPolicy)
0x180003c76  cmp     [this+88h], esi
0x180003c7c  jle     loc_180003E66
0x180003c82  lea     eax, [rsi+1]
0x180003c85  lock xadd [this+10h], eax
0x180003c8a  inc     eax
0x180003c8c  cmp     eax, 1
0x180003c8f  jnz     loc_180003E66
0x180003c95  mov     rax, [this]
0x180003c98  mov     rax, [rax+8]
0x180003c9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ca1  mov     this, rdi; this
0x180003ca4  mov     [rbp+operationInterface.ptr_], rsi
0x180003ca8  call    ?TraceOperationComplete@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?SetVersionAsyncOperationName@StateABIImplementation@Storage@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::Storage::StateABIImplementation::SetVersionAsyncOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x180003cad  mov     rax, [rdi]
0x180003cb0  lea     this, [rbp+operationInterface]; this
0x180003cb4  mov     rbx, [rax]
0x180003cb7  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180003cbc  lea     r8, [rbp+operationInterface]
0x180003cc0  mov     this, rdi
0x180003cc3  lea     rdx, _GUID_31456b58_a5cb_5c5b_bd6e_ccce3a7bf4b4
0x180003cca  mov     rax, rbx
0x180003ccd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cd2  test    eax, eax
0x180003cd4  js      loc_180003E3A
0x180003cda  mov     ecx, [rdi+38h]
0x180003cdd  mov     [rbp+current], 0FFFFFFFEh
0x180003ce4  mov     eax, [rbp+current]
0x180003ce7  lock cmpxchg [rbp+current], ecx
0x180003cec  lea     this, [rbp+completedDelegateLocal]; this
0x180003cf0  mov     [rbp+completedDelegateLocal.ptr_], rsi
0x180003cf4  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180003cf9  lea     this, [rdi+78h]; this
0x180003cfd  lea     r8, [rbp+completedDelegateLocal]; riid
0x180003d01  call    ?CopyLocal@?$GitPtrSupportsAgile@U?$IAsyncOperationCompletedHandler@PEAVApplicationData@Storage@Windows@@@Foundation@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>>::CopyLocal(_GUID const &,void * *)
0x180003d06  test    eax, eax
0x180003d08  js      loc_180003E1D
0x180003d0e  mov     this, rdi; this
0x180003d11  call    ?TraceCompletionNotificationStart@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?SetVersionAsyncOperationName@StateABIImplementation@Storage@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::Storage::StateABIImplementation::SetVersionAsyncOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(void)
0x180003d16  lea     this, [rbp+spRpcOptions]; this
0x180003d1a  mov     [rbp+spRpcOptions.ptr_], rsi
0x180003d1e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180003d23  mov     this, [rbp+completedDelegateLocal.ptr_]; pInterface
0x180003d27  lea     r8, [rbp+spRpcOptions]; pInterface
0x180003d2b  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x180003d30  mov     rbx, [rbp+spRpcOptions.ptr_]
0x180003d34  mov     [rbp+b1.spStream_.ptr_], rsi
0x180003d38  mov     [rbp+b1.hr_], esi
0x180003d3b  test    rbx, rbx
0x180003d3e  jz      short loc_180003D98
0x180003d40  cmp     [rbp+completedDelegateLocal.ptr_], rsi
0x180003d44  jz      short loc_180003D98
0x180003d46  mov     rsi, [rbp+operationInterface.ptr_]
0x180003d4a  lea     this, [rbp+b1]; this
0x180003d4e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180003d53  lea     r8, [rbp+b1]; ppstm
0x180003d57  mov     edx, 1; fDeleteOnRelease
0x180003d5c  xor     ecx, ecx; hGlobal
0x180003d5e  call    cs:__imp_CreateStreamOnHGlobal
0x180003d64  mov     [rbp+b1.hr_], eax
0x180003d67  test    eax, eax
0x180003d69  js      short loc_180003D9F
0x180003d6b  mov     this, [rbp+b1.spStream_.ptr_]; pStm
0x180003d6f  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180003d76  mov     [rsp+48h+mshlflags], 1; mshlflags
0x180003d7e  xor     r9d, r9d; dwDestContext
0x180003d81  mov     r8, rsi; pUnk
0x180003d84  mov     [rsp+48h+pvDestContext], 0; pvDestContext
0x180003d8d  call    cs:__imp_CoMarshalInterface
0x180003d93  mov     [rbp+b1.hr_], eax
0x180003d96  jmp     short loc_180003D9F
0x180003d98  mov     [rbp+b1.hr_], 80004002h
0x180003d9f  mov     this, [rbp+completedDelegateLocal.ptr_]
0x180003da3  mov     r8d, [rbp+current]
0x180003da7  mov     rdx, [rbp+operationInterface.ptr_]
0x180003dab  mov     rax, [this]
0x180003dae  mov     rax, [rax+18h]
0x180003db2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003db7  mov     r8, [rdi+80h]; pfnBucketAssist
0x180003dbe  mov     ecx, eax; hrIn
0x180003dc0  mov     rdx, [rbp+completedDelegateLocal.ptr_]; handler
0x180003dc4  call    ?FireCompletionErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireCompletionErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x180003dc9  mov     this, rdi; this
0x180003dcc  mov     esi, eax
0x180003dce  call    ?UnlockCompleteDelegate@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVApplicationData@Storage@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(void)
0x180003dd3  call    ?TraceCompletionNotificationComplete@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?SetVersionAsyncOperationName@StateABIImplementation@Storage@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::Storage::StateABIImplementation::SetVersionAsyncOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(void)
0x180003dd8  cmp     [rbp+b1.hr_], 0
0x180003ddc  jl      short loc_180003E00
0x180003dde  mov     this, [rbp+b1.spStream_.ptr_]
0x180003de2  xor     edx, edx
0x180003de4  xor     r9d, r9d
0x180003de7  mov     r8, [this]
0x180003dea  mov     rax, [r8+28h]
0x180003dee  xor     r8d, r8d
0x180003df1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003df6  mov     this, [rbp+b1.spStream_.ptr_]; pStm
0x180003dfa  call    cs:__imp_CoReleaseMarshalData
0x180003e00  lea     this, [rbp+b1]; this
0x180003e04  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180003e09  test    rbx, rbx
0x180003e0c  jz      short loc_180003E1D
0x180003e0e  mov     rax, [rbx]
0x180003e11  mov     this, rbx
0x180003e14  mov     rax, [rax+10h]
0x180003e18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e1d  mov     this, [rbp+completedDelegateLocal.ptr_]
0x180003e21  test    this, this
0x180003e24  jz      short loc_180003E3A
0x180003e26  mov     [rbp+completedDelegateLocal.ptr_], 0
0x180003e2e  mov     rax, [this]
0x180003e31  mov     rax, [rax+10h]
0x180003e35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e3a  mov     this, [rbp+operationInterface.ptr_]
0x180003e3e  test    this, this
0x180003e41  jz      short loc_180003E57
0x180003e43  mov     [rbp+operationInterface.ptr_], 0
0x180003e4b  mov     rax, [this]
0x180003e4e  mov     rax, [rax+10h]
0x180003e52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e57  mov     rax, [rdi]
0x180003e5a  mov     this, rdi
0x180003e5d  mov     rax, [rax+10h]
0x180003e61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e66  mov     eax, esi
0x180003e68  add     rsp, 48h
0x180003e6c  pop     rdi
0x180003e6d  pop     rsi
0x180003e6e  pop     rbx
0x180003e6f  pop     rbp
0x180003e70  retn
```
