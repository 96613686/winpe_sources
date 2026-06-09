# Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireProgress(int)

- ea: `0x18002e170`
- end: `0x18002e35d`
- name: `?FireProgress@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@PEAVApplicationData@Storage@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@QEAAJH@Z`
- size: `493`
- prototype: `HRESULT __fastcall(Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > *this, const int arg)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002efb0`

## callees

- `0x18000332c`
- `0x180003820`
- `0x1800041c8`
- `0x1800042fc`
- `0x18000648c`
- `0x1800240fc`
- `0x18002e170`
- `0x18002efcc`
- `0x18002eff8`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18002e2a6`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18002e2a6`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18002e27e`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18002e27e`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireProgress(
        Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > *this,
        int arg)
{
  unsigned int v4; // esi
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rbx
  const _GUID *v6; // rdx
  HRESULT (__fastcall *TraceSynchronousWorkStart)(Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, Windows::Foundation::Diagnostics::CausalityTraceLevel, Windows::Foundation::Diagnostics::CausalitySource, _GUID, unsigned __int64, Windows::Foundation::Diagnostics::CausalitySynchronousWork); // rax
  bool v8; // dl
  IUnknown *ptr; // rbx
  HRESULT v10; // eax
  AutoStubBias<IUnknown,Windows::Internal::INilDelegate> b1; // [rsp+40h] [rbp-20h] BYREF
  GUID v13; // [rsp+50h] [rbp-10h] BYREF
  Microsoft::WRL::ComPtr<Windows::Internal::INilDelegate> progressedDelegateLocal; // [rsp+90h] [rbp+30h] BYREF
  Microsoft::WRL::ComPtr<IUnknown> operationInterface; // [rsp+A0h] [rbp+40h] BYREF
  Microsoft::WRL::ComPtr<IRpcOptions> spRpcOptions; // [rsp+A8h] [rbp+48h] BYREF

  progressedDelegateLocal.ptr_ = (Windows::Internal::INilDelegate *)this;
  v4 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>>::InternalAddRef((Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler> *)&progressedDelegateLocal);
  operationInterface.ptr_ = 0;
  if ( Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryLockProgressDelegate(this) )
  {
    QueryInterface = this->QueryInterface;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *)&operationInterface);
    if ( QueryInterface(this, &GUID_00000000_0000_0000_c000_000000000046, (void **)&operationInterface.ptr_) >= 0 )
    {
      progressedDelegateLocal.ptr_ = 0;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *)&progressedDelegateLocal);
      if ( (int)Windows::Internal::GitPtrSupportsAgile<Windows::Internal::INilDelegate>::CopyLocal(
                  &this->progressedDelegate_,
                  v6,
                  (void **)&progressedDelegateLocal.ptr_) >= 0 )
      {
        if ( Microsoft::WRL::gCausality )
        {
          TraceSynchronousWorkStart = Microsoft::WRL::gCausality->TraceSynchronousWorkStart;
          v13 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
          ((void (__fastcall *)(Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, __int64, __int64, GUID *, Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > *, int))TraceSynchronousWorkStart)(
            Microsoft::WRL::gCausality,
            1,
            2,
            &v13,
            this,
            1);
        }
        spRpcOptions.ptr_ = 0;
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *)&spRpcOptions);
        RpcOptionsHelper::GetRpcOptions(progressedDelegateLocal.ptr_, v8, &spRpcOptions.ptr_);
        b1.spStream_.ptr_ = 0;
        b1.hr_ = 0;
        if ( spRpcOptions.ptr_ && progressedDelegateLocal.ptr_ )
        {
          ptr = operationInterface.ptr_;
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *)&b1);
          b1.hr_ = CreateStreamOnHGlobal(0, 1, &b1.spStream_.ptr_);
          if ( b1.hr_ >= 0 )
            b1.hr_ = CoMarshalInterface(b1.spStream_.ptr_, &GUID_00000000_0000_0000_c000_000000000046, ptr, 0, 0, 1u);
        }
        else
        {
          b1.hr_ = -2147467262;
        }
        v10 = progressedDelegateLocal.ptr_->Invoke(progressedDelegateLocal.ptr_, operationInterface.ptr_, arg);
        v4 = Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(
               v10,
               progressedDelegateLocal.ptr_,
               this->progressedDelegateBucketAssist_);
        if ( Microsoft::WRL::gCausality )
          Microsoft::WRL::gCausality->TraceSynchronousWorkCompletion(
            Microsoft::WRL::gCausality,
            CausalityTraceLevel_Important,
            CausalitySource_System,
            CausalitySynchronousWork_ProgressNotification);
        AutoStubBias<IUnknown,Windows::Internal::INilDelegate>::~AutoStubBias<IUnknown,Windows::Internal::INilDelegate>(&b1);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *)&spRpcOptions);
      }
      Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockProgressDelegate(this);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *)&progressedDelegateLocal);
    }
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> *)&operationInterface);
  if ( this )
    this->Release(this);
  return v4;
}

```

## disassembly

```asm
0x18002e170  mov     [rsp-28h+arg_8], rbx
0x18002e175  push    rbp
0x18002e176  push    rsi
0x18002e177  push    rdi
0x18002e178  push    r12
0x18002e17a  push    r14
0x18002e17c  mov     rbp, rsp
0x18002e17f  sub     rsp, 60h
0x18002e183  mov     rdi, this
0x18002e186  mov     [rbp+progressedDelegateLocal.ptr_], this
0x18002e18a  lea     this, [rbp+progressedDelegateLocal]; this
0x18002e18e  mov     r14d, arg
0x18002e191  xor     esi, esi
0x18002e193  call    ?InternalAddRef@?$ComPtr@U?$IMapView@PEAUHSTRING__@@PEAVApplicationDataContainer@Storage@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<HSTRING__ *,Windows::Storage::ApplicationDataContainer *>>::InternalAddRef(void)
0x18002e198  mov     this, rdi; this
0x18002e19b  mov     [rbp+operationInterface.ptr_], rsi
0x18002e19f  call    ?TryLockProgressDelegate@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@PEAVApplicationData@Storage@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAA_NXZ; Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryLockProgressDelegate(void)
0x18002e1a4  test    al, al
0x18002e1a6  jz      loc_18002E32A
0x18002e1ac  mov     rax, [rdi]
0x18002e1af  lea     this, [rbp+operationInterface]; this
0x18002e1b3  mov     rbx, [rax]
0x18002e1b6  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002e1bb  lea     r8, [rbp+operationInterface]
0x18002e1bf  mov     this, rdi
0x18002e1c2  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18002e1c9  mov     rax, rbx
0x18002e1cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e1d1  test    eax, eax
0x18002e1d3  js      loc_18002E32A
0x18002e1d9  lea     this, [rbp+progressedDelegateLocal]; this
0x18002e1dd  mov     [rbp+progressedDelegateLocal.ptr_], rsi
0x18002e1e1  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002e1e6  lea     this, [rdi+90h]; this
0x18002e1ed  lea     r8, [rbp+progressedDelegateLocal]; riid
0x18002e1f1  call    ?CopyLocal@?$GitPtrSupportsAgile@UINilDelegate@Internal@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Internal::INilDelegate>::CopyLocal(_GUID const &,void * *)
0x18002e1f6  test    eax, eax
0x18002e1f8  js      loc_18002E319
0x18002e1fe  mov     this, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18002e205  lea     r12d, [rsi+1]
0x18002e209  test    this, this
0x18002e20c  jz      short loc_18002E23B
0x18002e20e  mov     rax, [this]
0x18002e211  lea     r9, [rbp+var_10]
0x18002e215  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x18002e21c  mov     [rsp+60h+mshlflags], r12d
0x18002e221  lea     r8d, [rsi+2]
0x18002e225  mov     arg, r12d
0x18002e228  mov     [rsp+60h+pvDestContext], rdi
0x18002e22d  mov     rax, [rax+48h]
0x18002e231  movdqu  [rbp+var_10], xmm0
0x18002e236  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e23b  lea     this, [rbp+spRpcOptions]; this
0x18002e23f  mov     [rbp+spRpcOptions.ptr_], rsi
0x18002e243  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002e248  mov     this, [rbp+progressedDelegateLocal.ptr_]; pInterface
0x18002e24c  lea     r8, [rbp+spRpcOptions]; pInterface
0x18002e250  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x18002e255  mov     [rbp+b1.spStream_.ptr_], rsi
0x18002e259  mov     [rbp+b1.hr_], esi
0x18002e25c  cmp     [rbp+spRpcOptions.ptr_], rsi
0x18002e260  jz      short loc_18002E2B1
0x18002e262  cmp     [rbp+progressedDelegateLocal.ptr_], rsi
0x18002e266  jz      short loc_18002E2B1
0x18002e268  mov     rbx, [rbp+operationInterface.ptr_]
0x18002e26c  lea     this, [rbp+b1]; this
0x18002e270  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002e275  lea     r8, [rbp+b1]; ppstm
0x18002e279  mov     arg, r12d; fDeleteOnRelease
0x18002e27c  xor     ecx, ecx; hGlobal
0x18002e27e  call    cs:__imp_CreateStreamOnHGlobal
0x18002e284  mov     [rbp+b1.hr_], eax
0x18002e287  test    eax, eax
0x18002e289  js      short loc_18002E2B8
0x18002e28b  mov     this, [rbp+b1.spStream_.ptr_]; pStm
0x18002e28f  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18002e296  mov     [rsp+60h+mshlflags], r12d; mshlflags
0x18002e29b  xor     r9d, r9d; dwDestContext
0x18002e29e  mov     r8, rbx; pUnk
0x18002e2a1  mov     [rsp+60h+pvDestContext], rsi; pvDestContext
0x18002e2a6  call    cs:__imp_CoMarshalInterface
0x18002e2ac  mov     [rbp+b1.hr_], eax
0x18002e2af  jmp     short loc_18002E2B8
0x18002e2b1  mov     [rbp+b1.hr_], 80004002h
0x18002e2b8  mov     this, [rbp+progressedDelegateLocal.ptr_]
0x18002e2bc  mov     r8d, r14d
0x18002e2bf  mov     rdx, [rbp+operationInterface.ptr_]
0x18002e2c3  mov     rax, [this]
0x18002e2c6  mov     rax, [rax+18h]
0x18002e2ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e2cf  mov     r8, [rdi+98h]; pfnBucketAssist
0x18002e2d6  mov     ecx, eax; hrIn
0x18002e2d8  mov     rdx, [rbp+progressedDelegateLocal.ptr_]; handler
0x18002e2dc  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x18002e2e1  mov     this, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18002e2e8  mov     esi, eax
0x18002e2ea  test    this, this
0x18002e2ed  jz      short loc_18002E307
0x18002e2ef  mov     r9, [this]
0x18002e2f2  mov     r8d, 2
0x18002e2f8  mov     arg, r12d
0x18002e2fb  mov     rax, [r9+50h]
0x18002e2ff  mov     r9d, r12d
0x18002e302  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e307  lea     this, [rbp+b1]; this
0x18002e30b  call    ??1?$AutoStubBias@UIUnknown@@UINilDelegate@Internal@Windows@@@@QEAA@XZ; AutoStubBias<IUnknown,Windows::Internal::INilDelegate>::~AutoStubBias<IUnknown,Windows::Internal::INilDelegate>(void)
0x18002e310  lea     this, [rbp+spRpcOptions]; this
0x18002e314  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002e319  mov     this, rdi; this
0x18002e31c  call    ?UnlockProgressDelegate@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@PEAVApplicationData@Storage@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockProgressDelegate(void)
0x18002e321  lea     this, [rbp+progressedDelegateLocal]; this
0x18002e325  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002e32a  lea     this, [rbp+operationInterface]; this
0x18002e32e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002e333  test    rdi, rdi
0x18002e336  jz      short loc_18002E347
0x18002e338  mov     rax, [rdi]
0x18002e33b  mov     this, rdi
0x18002e33e  mov     rax, [rax+10h]
0x18002e342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e347  mov     rbx, [rsp+60h+arg_8]
0x18002e34f  mov     eax, esi
0x18002e351  add     rsp, 60h
0x18002e355  pop     r14
0x18002e357  pop     r12
0x18002e359  pop     rdi
0x18002e35a  pop     rsi
0x18002e35b  pop     rbp
0x18002e35c  retn
```
