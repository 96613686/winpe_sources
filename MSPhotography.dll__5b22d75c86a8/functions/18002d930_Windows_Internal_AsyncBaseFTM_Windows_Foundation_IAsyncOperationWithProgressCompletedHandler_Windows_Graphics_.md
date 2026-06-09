# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Graphics::Imaging::Internal::HighDynamicRangeResult *,double>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x18002d930`
- end: `0x18002dac5`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAVHighDynamicRangeResult@Internal@Imaging@Graphics@Windows@@N@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `405`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002dad0`

## callees

- `0x180005660`
- `0x1800280e4`
- `0x18002bb98`
- `0x18002ca8c`
- `0x18002d13c`
- `0x18002d74c`
- `0x18002d930`
- `0x18002dafc`
- `0x18002e00c`
- `0x18002f968`
- `0x18002f998`
- `0x18002fa3c`
- `0x18002fb60`
- `0x18002fca0`
- `0x180142010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18002da43`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18002da43`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18002da14`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18002da14`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Graphics::Imaging::Internal::HighDynamicRangeResult *,double>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
        __int64 a1)
{
  unsigned int v1; // edi
  unsigned int v3; // edx
  signed __int32 v4; // ecx
  __int64 v5; // rdx
  bool v6; // dl
  IUnknown *v7; // rdi
  unsigned int v8; // eax
  __int64 v10; // [rsp+30h] [rbp-20h] BYREF
  LPSTREAM ppstm; // [rsp+38h] [rbp-18h] BYREF
  HRESULT v12; // [rsp+40h] [rbp-10h]
  unsigned int v13; // [rsp+70h] [rbp+20h] BYREF
  struct IUnknown *v14; // [rsp+78h] [rbp+28h] BYREF
  struct IRpcOptions *v15; // [rsp+80h] [rbp+30h] BYREF
  LPUNKNOWN pUnk; // [rsp+88h] [rbp+38h] BYREF

  v1 = 0;
  Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Core::LowLightFusionResult *,double>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(
    a1,
    1);
  if ( *(int *)(a1 + 136) > 0 && _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 16), v3) + 1 == v3 )
  {
    v10 = a1;
    Microsoft::WRL::ComPtr<IAsyncInfo>::InternalAddRef(&v10);
    pUnk = 0;
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Graphics::Imaging::Internal::HighDynamicRangeResult *,double>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(a1);
    if ( (int)Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperationWithProgress<Windows::Graphics::Imaging::Internal::HighDynamicRangeResult *,double>>(
                &v10,
                &pUnk) >= 0 )
    {
      v4 = *(_DWORD *)(a1 + 56);
      v13 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v13, v4, -2);
      v14 = 0;
      Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(&v14);
      if ( (int)Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Graphics::Imaging::Internal::HighDynamicRangeResult *,double>>::CopyLocal(
                  a1 + 120,
                  v5,
                  &v14) >= 0 )
      {
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Core::LowLightFusionResult *,double>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(a1);
        v15 = 0;
        Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(&v15);
        RpcOptionsHelper::GetRpcOptions(v14, v6, &v15);
        ppstm = 0;
        v12 = 0;
        if ( v15 && v14 )
        {
          v7 = pUnk;
          Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(&ppstm);
          v12 = CreateStreamOnHGlobal(0, 1, &ppstm);
          if ( v12 >= 0 )
            v12 = CoMarshalInterface(ppstm, &GUID_00000000_0000_0000_c000_000000000046, v7, 0, 0, 1u);
        }
        else
        {
          v12 = -2147467262;
        }
        v8 = ((__int64 (__fastcall *)(struct IUnknown *, LPUNKNOWN, _QWORD))v14->lpVtbl[1].QueryInterface)(
               v14,
               pUnk,
               v13);
        v1 = Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireCompletionErrorPropagationPolicyFilter(
               v8,
               v14,
               *(_QWORD *)(a1 + 128));
        Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Core::LowLightFusionResult *,double>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(a1);
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Core::LowLightFusionResult *,double>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete();
        AutoStubBias<Windows::Foundation::IAsyncOperationWithProgress<Windows::Graphics::Imaging::Internal::HighDynamicRangeResult *,double>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Graphics::Imaging::Internal::HighDynamicRangeResult *,double>>::~AutoStubBias<Windows::Foundation::IAsyncOperationWithProgress<Windows::Graphics::Imaging::Internal::HighDynamicRangeResult *,double>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Graphics::Imaging::Internal::HighDynamicRangeResult *,double>>(&ppstm);
        Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(&v15);
      }
      Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(&v14);
    }
    Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(&pUnk);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
  }
  return v1;
}

```

## disassembly

```asm
0x18002d930  push    rbp
0x18002d932  push    rbx
0x18002d933  push    rdi
0x18002d934  mov     rbp, rsp
0x18002d937  sub     rsp, 50h
0x18002d93b  xor     edi, edi
0x18002d93d  mov     rbx, rcx
0x18002d940  lea     edx, [rdi+1]
0x18002d943  call    ?TransitionToState@?$AsyncBase@U?$IAsyncOperationWithProgressCompletedHandler@PEAVLowLightFusionResult@Core@Media@Windows@@N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Core::LowLightFusionResult *,double>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x18002d948  cmp     [rbx+88h], edi
0x18002d94e  jle     loc_18002DABB
0x18002d954  mov     eax, edx
0x18002d956  lock xadd [rbx+10h], eax
0x18002d95b  inc     eax
0x18002d95d  cmp     eax, edx
0x18002d95f  jnz     loc_18002DABB
0x18002d965  lea     rcx, [rbp+var_20]
0x18002d969  mov     [rbp+var_20], rbx
0x18002d96d  call    ?InternalAddRef@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IAsyncInfo>::InternalAddRef(void)
0x18002d972  mov     rcx, rbx
0x18002d975  mov     [rbp+pUnk], rdi
0x18002d979  call    ?TraceOperationComplete@?$AsyncBase@U?$IAsyncOperationWithProgressCompletedHandler@PEAVHighDynamicRangeResult@Internal@Imaging@Graphics@Windows@@N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Graphics::Imaging::Internal::HighDynamicRangeResult *,double>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x18002d97e  lea     rdx, [rbp+pUnk]
0x18002d982  lea     rcx, [rbp+var_20]
0x18002d986  call    ??$As@U?$IAsyncOperationWithProgress@PEAVHighDynamicRangeResult@Internal@Imaging@Graphics@Windows@@N@Foundation@Windows@@@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IAsyncOperationWithProgress@PEAVHighDynamicRangeResult@Internal@Imaging@Graphics@Windows@@N@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperationWithProgress<Windows::Graphics::Imaging::Internal::HighDynamicRangeResult *,double>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationWithProgress<Windows::Graphics::Imaging::Internal::HighDynamicRangeResult *,double>>>)
0x18002d98b  test    eax, eax
0x18002d98d  js      loc_18002DAA9
0x18002d993  mov     ecx, [rbx+38h]
0x18002d996  mov     [rbp+arg_0], 0FFFFFFFEh
0x18002d99d  mov     eax, [rbp+arg_0]
0x18002d9a0  lock cmpxchg [rbp+arg_0], ecx
0x18002d9a5  lea     rcx, [rbp+arg_8]
0x18002d9a9  mov     [rbp+arg_8], rdi
0x18002d9ad  call    ?InternalRelease@?$ComPtr@UIMFVideoProcessorControl@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(void)
0x18002d9b2  lea     rcx, [rbx+78h]
0x18002d9b6  lea     r8, [rbp+arg_8]
0x18002d9ba  call    ?CopyLocal@?$GitPtrSupportsAgile@U?$IAsyncOperationWithProgressCompletedHandler@PEAVHighDynamicRangeResult@Internal@Imaging@Graphics@Windows@@N@Foundation@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Graphics::Imaging::Internal::HighDynamicRangeResult *,double>>::CopyLocal(_GUID const &,void * *)
0x18002d9bf  test    eax, eax
0x18002d9c1  js      loc_18002DAA0
0x18002d9c7  mov     rcx, rbx
0x18002d9ca  call    ?TraceCompletionNotificationStart@?$AsyncBase@U?$IAsyncOperationWithProgressCompletedHandler@PEAVLowLightFusionResult@Core@Media@Windows@@N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Core::LowLightFusionResult *,double>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(void)
0x18002d9cf  lea     rcx, [rbp+arg_10]
0x18002d9d3  mov     [rbp+arg_10], rdi
0x18002d9d7  call    ?InternalRelease@?$ComPtr@UIMFVideoProcessorControl@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(void)
0x18002d9dc  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x18002d9e0  lea     r8, [rbp+arg_10]; struct IRpcOptions **
0x18002d9e4  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x18002d9e9  mov     [rbp+ppstm], rdi
0x18002d9ed  mov     [rbp+var_10], edi
0x18002d9f0  cmp     [rbp+arg_10], rdi
0x18002d9f4  jz      short loc_18002DA4E
0x18002d9f6  cmp     [rbp+arg_8], rdi
0x18002d9fa  jz      short loc_18002DA4E
0x18002d9fc  mov     rdi, [rbp+pUnk]
0x18002da00  lea     rcx, [rbp+ppstm]
0x18002da04  call    ?InternalRelease@?$ComPtr@UIMFVideoProcessorControl@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(void)
0x18002da09  lea     r8, [rbp+ppstm]; ppstm
0x18002da0d  mov     edx, 1; fDeleteOnRelease
0x18002da12  xor     ecx, ecx; hGlobal
0x18002da14  call    cs:__imp_CreateStreamOnHGlobal
0x18002da1a  mov     [rbp+var_10], eax
0x18002da1d  test    eax, eax
0x18002da1f  js      short loc_18002DA55
0x18002da21  mov     rcx, [rbp+ppstm]; pStm
0x18002da25  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18002da2c  mov     [rsp+50h+mshlflags], 1; mshlflags
0x18002da34  xor     r9d, r9d; dwDestContext
0x18002da37  mov     r8, rdi; pUnk
0x18002da3a  mov     [rsp+50h+pvDestContext], 0; pvDestContext
0x18002da43  call    cs:__imp_CoMarshalInterface
0x18002da49  mov     [rbp+var_10], eax
0x18002da4c  jmp     short loc_18002DA55
0x18002da4e  mov     [rbp+var_10], 80004002h
0x18002da55  mov     rcx, [rbp+arg_8]
0x18002da59  mov     r8d, [rbp+arg_0]
0x18002da5d  mov     rdx, [rbp+pUnk]
0x18002da61  mov     rax, [rcx]
0x18002da64  mov     rax, [rax+18h]
0x18002da68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002da6d  mov     r8, [rbx+80h]
0x18002da74  mov     ecx, eax
0x18002da76  mov     rdx, [rbp+arg_8]
0x18002da7a  call    ?FireCompletionErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireCompletionErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x18002da7f  mov     rcx, rbx
0x18002da82  mov     edi, eax
0x18002da84  call    ?UnlockCompleteDelegate@?$AsyncBaseFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAVLowLightFusionResult@Core@Media@Windows@@N@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Core::LowLightFusionResult *,double>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(void)
0x18002da89  call    ?TraceCompletionNotificationComplete@?$AsyncBase@U?$IAsyncOperationWithProgressCompletedHandler@PEAVLowLightFusionResult@Core@Media@Windows@@N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Core::LowLightFusionResult *,double>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(void)
0x18002da8e  lea     rcx, [rbp+ppstm]
0x18002da92  call    ??1?$AutoStubBias@U?$IAsyncOperationWithProgress@PEAVHighDynamicRangeResult@Internal@Imaging@Graphics@Windows@@N@Foundation@Windows@@U?$IAsyncOperationWithProgressCompletedHandler@PEAVHighDynamicRangeResult@Internal@Imaging@Graphics@Windows@@N@23@@@QEAA@XZ; AutoStubBias<Windows::Foundation::IAsyncOperationWithProgress<Windows::Graphics::Imaging::Internal::HighDynamicRangeResult *,double>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Graphics::Imaging::Internal::HighDynamicRangeResult *,double>>::~AutoStubBias<Windows::Foundation::IAsyncOperationWithProgress<Windows::Graphics::Imaging::Internal::HighDynamicRangeResult *,double>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Graphics::Imaging::Internal::HighDynamicRangeResult *,double>>(void)
0x18002da97  lea     rcx, [rbp+arg_10]
0x18002da9b  call    ?InternalRelease@?$ComPtr@UIMFVideoProcessorControl@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(void)
0x18002daa0  lea     rcx, [rbp+arg_8]
0x18002daa4  call    ?InternalRelease@?$ComPtr@UIMFVideoProcessorControl@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(void)
0x18002daa9  lea     rcx, [rbp+pUnk]
0x18002daad  call    ?InternalRelease@?$ComPtr@UIMFVideoProcessorControl@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(void)
0x18002dab2  lea     rcx, [rbp+var_20]
0x18002dab6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002dabb  mov     eax, edi
0x18002dabd  add     rsp, 50h
0x18002dac1  pop     rdi
0x18002dac2  pop     rbx
0x18002dac3  pop     rbp
0x18002dac4  retn
```
