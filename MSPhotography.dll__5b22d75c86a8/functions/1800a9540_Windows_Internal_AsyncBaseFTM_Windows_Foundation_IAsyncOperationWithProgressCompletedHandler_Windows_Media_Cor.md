# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Core::LowLightFusionResult *,double>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x1800a9540`
- end: `0x1800a96db`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAVLowLightFusionResult@Core@Media@Windows@@N@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `411`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800a96f0`

## callees

- `0x180005660`
- `0x1800280e4`
- `0x18002bb98`
- `0x18002dafc`
- `0x18002e00c`
- `0x18002f968`
- `0x18002f998`
- `0x18002fa3c`
- `0x18002fb60`
- `0x18002fca0`
- `0x1800a891c`
- `0x1800a8fe0`
- `0x1800a9410`
- `0x1800a9540`
- `0x180142010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x1800a9654`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x1800a9654`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800a9625`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800a9625`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Core::LowLightFusionResult *,double>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
        __int64 a1)
{
  unsigned int v2; // edi
  unsigned int v3; // edx
  __int64 v4; // rdx
  bool v5; // dl
  IUnknown *v6; // rdi
  unsigned int v7; // eax
  __int64 v9; // [rsp+30h] [rbp-20h] BYREF
  LPSTREAM ppstm; // [rsp+38h] [rbp-18h] BYREF
  HRESULT v11; // [rsp+40h] [rbp-10h]
  unsigned int v12; // [rsp+70h] [rbp+20h] BYREF
  struct IUnknown *v13; // [rsp+78h] [rbp+28h] BYREF
  struct IRpcOptions *v14; // [rsp+80h] [rbp+30h] BYREF
  LPUNKNOWN pUnk; // [rsp+88h] [rbp+38h] BYREF

  v2 = 0;
  Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Core::LowLightFusionResult *,double>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(
    a1,
    1);
  if ( *(int *)(a1 + 136) > 0 && _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 16), v3) + 1 == v3 )
  {
    v9 = a1;
    Microsoft::WRL::ComPtr<IAsyncInfo>::InternalAddRef(&v9);
    pUnk = 0;
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Graphics::Imaging::Internal::HighDynamicRangeResult *,double>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(a1);
    if ( (int)Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperationWithProgress<Windows::Media::Core::LowLightFusionResult *,double>>(
                &v9,
                &pUnk) >= 0 )
    {
      v12 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v12, *(_DWORD *)(a1 + 56), -2);
      v13 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
      if ( (int)Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Core::LowLightFusionResult *,double>>::CopyLocal(
                  a1 + 120,
                  v4,
                  &v13) >= 0 )
      {
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Core::LowLightFusionResult *,double>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(a1);
        v14 = 0;
        Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(&v14);
        RpcOptionsHelper::GetRpcOptions(v13, v5, &v14);
        ppstm = 0;
        v11 = 0;
        if ( v14 && v13 )
        {
          v6 = pUnk;
          Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(&ppstm);
          v11 = CreateStreamOnHGlobal(0, 1, &ppstm);
          if ( v11 >= 0 )
            v11 = CoMarshalInterface(ppstm, &GUID_00000000_0000_0000_c000_000000000046, v6, 0, 0, 1u);
        }
        else
        {
          v11 = -2147467262;
        }
        v7 = ((__int64 (__fastcall *)(struct IUnknown *, LPUNKNOWN, _QWORD))v13->lpVtbl[1].QueryInterface)(
               v13,
               pUnk,
               v12);
        v2 = Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireCompletionErrorPropagationPolicyFilter(
               v7,
               v13,
               *(_QWORD *)(a1 + 128));
        Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Core::LowLightFusionResult *,double>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(a1);
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Core::LowLightFusionResult *,double>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete();
        AutoStubBias<Windows::Foundation::IAsyncOperationWithProgress<Windows::Media::Core::LowLightFusionResult *,double>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Core::LowLightFusionResult *,double>>::~AutoStubBias<Windows::Foundation::IAsyncOperationWithProgress<Windows::Media::Core::LowLightFusionResult *,double>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Core::LowLightFusionResult *,double>>(&ppstm);
        Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(&v14);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pUnk);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
  }
  return v2;
}

```

## disassembly

```asm
0x1800a9540  push    rbp
0x1800a9542  push    rbx
0x1800a9543  push    rdi
0x1800a9544  mov     rbp, rsp
0x1800a9547  sub     rsp, 50h
0x1800a954b  mov     rbx, rcx
0x1800a954e  xor     edi, edi
0x1800a9550  lea     edx, [rdi+1]
0x1800a9553  call    ?TransitionToState@?$AsyncBase@U?$IAsyncOperationWithProgressCompletedHandler@PEAVLowLightFusionResult@Core@Media@Windows@@N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Core::LowLightFusionResult *,double>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x1800a9558  cmp     [rbx+88h], edi
0x1800a955e  jle     loc_1800A96D1
0x1800a9564  mov     eax, edx
0x1800a9566  lock xadd [rbx+10h], eax
0x1800a956b  inc     eax
0x1800a956d  cmp     eax, edx
0x1800a956f  jnz     loc_1800A96D1
0x1800a9575  mov     [rbp+var_20], rbx
0x1800a9579  lea     rcx, [rbp+var_20]
0x1800a957d  call    ?InternalAddRef@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IAsyncInfo>::InternalAddRef(void)
0x1800a9582  nop
0x1800a9583  mov     [rbp+pUnk], rdi
0x1800a9587  mov     rcx, rbx
0x1800a958a  call    ?TraceOperationComplete@?$AsyncBase@U?$IAsyncOperationWithProgressCompletedHandler@PEAVHighDynamicRangeResult@Internal@Imaging@Graphics@Windows@@N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Graphics::Imaging::Internal::HighDynamicRangeResult *,double>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x1800a958f  lea     rdx, [rbp+pUnk]
0x1800a9593  lea     rcx, [rbp+var_20]
0x1800a9597  call    ??$As@U?$IAsyncOperationWithProgress@PEAVLowLightFusionResult@Core@Media@Windows@@N@Foundation@Windows@@@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IAsyncOperationWithProgress@PEAVLowLightFusionResult@Core@Media@Windows@@N@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperationWithProgress<Windows::Media::Core::LowLightFusionResult *,double>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationWithProgress<Windows::Media::Core::LowLightFusionResult *,double>>>)
0x1800a959c  test    eax, eax
0x1800a959e  js      loc_1800A96BE
0x1800a95a4  mov     [rbp+arg_0], 0FFFFFFFEh
0x1800a95ab  mov     ecx, [rbx+38h]
0x1800a95ae  mov     eax, [rbp+arg_0]
0x1800a95b1  lock cmpxchg [rbp+arg_0], ecx
0x1800a95b6  mov     [rbp+arg_8], rdi
0x1800a95ba  lea     rcx, [rbp+arg_8]
0x1800a95be  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a95c3  lea     rcx, [rbx+78h]
0x1800a95c7  lea     r8, [rbp+arg_8]
0x1800a95cb  call    ?CopyLocal@?$GitPtrSupportsAgile@U?$IAsyncOperationWithProgressCompletedHandler@PEAVLowLightFusionResult@Core@Media@Windows@@N@Foundation@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Core::LowLightFusionResult *,double>>::CopyLocal(_GUID const &,void * *)
0x1800a95d0  test    eax, eax
0x1800a95d2  js      loc_1800A96B4
0x1800a95d8  mov     rcx, rbx
0x1800a95db  call    ?TraceCompletionNotificationStart@?$AsyncBase@U?$IAsyncOperationWithProgressCompletedHandler@PEAVLowLightFusionResult@Core@Media@Windows@@N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Core::LowLightFusionResult *,double>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(void)
0x1800a95e0  mov     [rbp+arg_10], rdi
0x1800a95e4  lea     rcx, [rbp+arg_10]
0x1800a95e8  call    ?InternalRelease@?$ComPtr@UIMFVideoProcessorControl@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(void)
0x1800a95ed  lea     r8, [rbp+arg_10]; struct IRpcOptions **
0x1800a95f1  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x1800a95f5  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x1800a95fa  mov     [rbp+ppstm], rdi
0x1800a95fe  mov     [rbp+var_10], edi
0x1800a9601  cmp     [rbp+arg_10], rdi
0x1800a9605  jz      short loc_1800A965F
0x1800a9607  cmp     [rbp+arg_8], rdi
0x1800a960b  jz      short loc_1800A965F
0x1800a960d  mov     rdi, [rbp+pUnk]
0x1800a9611  lea     rcx, [rbp+ppstm]
0x1800a9615  call    ?InternalRelease@?$ComPtr@UIMFVideoProcessorControl@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(void)
0x1800a961a  lea     r8, [rbp+ppstm]; ppstm
0x1800a961e  mov     edx, 1; fDeleteOnRelease
0x1800a9623  xor     ecx, ecx; hGlobal
0x1800a9625  call    cs:__imp_CreateStreamOnHGlobal
0x1800a962b  mov     [rbp+var_10], eax
0x1800a962e  test    eax, eax
0x1800a9630  js      short loc_1800A9666
0x1800a9632  mov     [rsp+50h+mshlflags], 1; mshlflags
0x1800a963a  mov     [rsp+50h+pvDestContext], 0; pvDestContext
0x1800a9643  xor     r9d, r9d; dwDestContext
0x1800a9646  mov     r8, rdi; pUnk
0x1800a9649  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x1800a9650  mov     rcx, [rbp+ppstm]; pStm
0x1800a9654  call    cs:__imp_CoMarshalInterface
0x1800a965a  mov     [rbp+var_10], eax
0x1800a965d  jmp     short loc_1800A9666
0x1800a965f  mov     [rbp+var_10], 80004002h
0x1800a9666  mov     rcx, [rbp+arg_8]
0x1800a966a  mov     rax, [rcx]
0x1800a966d  mov     r8d, [rbp+arg_0]
0x1800a9671  mov     rdx, [rbp+pUnk]
0x1800a9675  mov     rax, [rax+18h]
0x1800a9679  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a967e  mov     r8, [rbx+80h]
0x1800a9685  mov     rdx, [rbp+arg_8]
0x1800a9689  mov     ecx, eax
0x1800a968b  call    ?FireCompletionErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireCompletionErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x1800a9690  mov     edi, eax
0x1800a9692  mov     rcx, rbx
0x1800a9695  call    ?UnlockCompleteDelegate@?$AsyncBaseFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAVLowLightFusionResult@Core@Media@Windows@@N@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Core::LowLightFusionResult *,double>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(void)
0x1800a969a  call    ?TraceCompletionNotificationComplete@?$AsyncBase@U?$IAsyncOperationWithProgressCompletedHandler@PEAVLowLightFusionResult@Core@Media@Windows@@N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Core::LowLightFusionResult *,double>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(void)
0x1800a969f  nop
0x1800a96a0  lea     rcx, [rbp+ppstm]
0x1800a96a4  call    ??1?$AutoStubBias@U?$IAsyncOperationWithProgress@PEAVLowLightFusionResult@Core@Media@Windows@@N@Foundation@Windows@@U?$IAsyncOperationWithProgressCompletedHandler@PEAVLowLightFusionResult@Core@Media@Windows@@N@23@@@QEAA@XZ; AutoStubBias<Windows::Foundation::IAsyncOperationWithProgress<Windows::Media::Core::LowLightFusionResult *,double>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Core::LowLightFusionResult *,double>>::~AutoStubBias<Windows::Foundation::IAsyncOperationWithProgress<Windows::Media::Core::LowLightFusionResult *,double>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Core::LowLightFusionResult *,double>>(void)
0x1800a96a9  nop
0x1800a96aa  lea     rcx, [rbp+arg_10]
0x1800a96ae  call    ?InternalRelease@?$ComPtr@UIMFVideoProcessorControl@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(void)
0x1800a96b3  nop
0x1800a96b4  lea     rcx, [rbp+arg_8]
0x1800a96b8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a96bd  nop
0x1800a96be  lea     rcx, [rbp+pUnk]
0x1800a96c2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a96c7  nop
0x1800a96c8  lea     rcx, [rbp+var_20]
0x1800a96cc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a96d1  mov     eax, edi
0x1800a96d3  add     rsp, 50h
0x1800a96d7  pop     rdi
0x1800a96d8  pop     rbx
0x1800a96d9  pop     rbp
0x1800a96da  retn
```
