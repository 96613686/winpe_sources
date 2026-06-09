# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x1800855c0`
- end: `0x18008575b`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `411`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180085950`

## callees

- `0x18000504c`
- `0x1800050b4`
- `0x18000fa5c`
- `0x180014c54`
- `0x18007435c`
- `0x180075f70`
- `0x180076928`
- `0x1800791dc`
- `0x18007920c`
- `0x1800793d0`
- `0x18007f1f8`
- `0x180084e28`
- `0x1800855c0`
- `0x1800dc010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800856a5`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800856a5`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x1800856d4`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x1800856d4`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
        __int64 a1)
{
  unsigned int v2; // edi
  unsigned int v3; // edx
  __int64 v4; // rdx
  bool v5; // dl
  IUnknown *v6; // rdi
  unsigned int v7; // eax
  __int64 (__fastcall ***v9)(_QWORD, GUID *, __int64); // [rsp+30h] [rbp-20h] BYREF
  LPSTREAM ppstm; // [rsp+38h] [rbp-18h] BYREF
  HRESULT v11; // [rsp+40h] [rbp-10h]
  unsigned int v12; // [rsp+70h] [rbp+20h] BYREF
  struct IUnknown *v13; // [rsp+78h] [rbp+28h] BYREF
  struct IRpcOptions *v14; // [rsp+80h] [rbp+30h] BYREF
  LPUNKNOWN pUnk; // [rsp+88h] [rbp+38h] BYREF

  v2 = 0;
  Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const StopOobeLoggingAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(
    a1,
    1);
  if ( *(int *)(a1 + 136) > 0 && _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 16), v3) + 1 == v3 )
  {
    v9 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))a1;
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<bool,double>>::InternalAddRef(&v9);
    pUnk = 0;
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<CloudExperienceHostAPI::HostedApplicationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const CloudExperienceHostAPI::ShowHostedAppCoreOperation,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(a1);
    if ( (int)Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<bool>>(&v9, (__int64)&pUnk) >= 0 )
    {
      v12 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v12, *(_DWORD *)(a1 + 56), -2);
      v13 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
      if ( (int)Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::CopyLocal(
                  a1 + 120,
                  v4,
                  &v13) >= 0 )
      {
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const StopOobeLoggingAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(a1);
        v14 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
        RpcOptionsHelper::GetRpcOptions(v13, v5, &v14);
        ppstm = 0;
        v11 = 0;
        if ( v14 && v13 )
        {
          v6 = pUnk;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppstm);
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
        v2 = Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(
               v7,
               v13,
               *(_QWORD *)(a1 + 128));
        Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<CloudExperienceHostAPI::UserIntentRecordResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(a1);
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const CloudExperienceHostAPI::UpdateTimeZoneAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete();
        AutoStubBias<Windows::Foundation::IAsyncOperationWithProgress<bool,double>,Windows::Foundation::IAsyncOperationProgressHandler<bool,double>>::~AutoStubBias<Windows::Foundation::IAsyncOperationWithProgress<bool,double>,Windows::Foundation::IAsyncOperationProgressHandler<bool,double>>(&ppstm);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pUnk);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v9);
  }
  return v2;
}

```

## disassembly

```asm
0x1800855c0  push    rbp
0x1800855c2  push    rbx
0x1800855c3  push    rdi
0x1800855c4  mov     rbp, rsp
0x1800855c7  sub     rsp, 50h
0x1800855cb  mov     rbx, rcx
0x1800855ce  xor     edi, edi
0x1800855d0  lea     edx, [rdi+1]
0x1800855d3  call    ?TransitionToState@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?StopOobeLoggingAsyncActionName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const StopOobeLoggingAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x1800855d8  cmp     [rbx+88h], edi
0x1800855de  jle     loc_180085751
0x1800855e4  mov     eax, edx
0x1800855e6  lock xadd [rbx+10h], eax
0x1800855eb  inc     eax
0x1800855ed  cmp     eax, edx
0x1800855ef  jnz     loc_180085751
0x1800855f5  mov     [rbp+var_20], rbx
0x1800855f9  lea     rcx, [rbp+var_20]
0x1800855fd  call    ?InternalAddRef@?$ComPtr@U?$IAsyncOperationWithProgressCompletedHandler@_NN@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<bool,double>>::InternalAddRef(void)
0x180085602  nop
0x180085603  mov     [rbp+pUnk], rdi
0x180085607  mov     rcx, rbx
0x18008560a  call    ?TraceOperationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVHostedApplicationResult@CloudExperienceHostAPI@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?ShowHostedAppCoreOperation@CloudExperienceHostAPI@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<CloudExperienceHostAPI::HostedApplicationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const CloudExperienceHostAPI::ShowHostedAppCoreOperation,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x18008560f  lea     rdx, [rbp+pUnk]
0x180085613  lea     rcx, [rbp+var_20]
0x180085617  call    ??$As@U?$IAsyncOperation@_N@Foundation@Windows@@@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IAsyncOperation@_N@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<bool>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<bool>>>)
0x18008561c  test    eax, eax
0x18008561e  js      loc_18008573E
0x180085624  mov     [rbp+arg_0], 0FFFFFFFEh
0x18008562b  mov     ecx, [rbx+38h]
0x18008562e  mov     eax, [rbp+arg_0]
0x180085631  lock cmpxchg [rbp+arg_0], ecx
0x180085636  mov     [rbp+arg_8], rdi
0x18008563a  lea     rcx, [rbp+arg_8]
0x18008563e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180085643  lea     rcx, [rbx+78h]
0x180085647  lea     r8, [rbp+arg_8]
0x18008564b  call    ?CopyLocal@?$GitPtrSupportsAgile@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::CopyLocal(_GUID const &,void * *)
0x180085650  test    eax, eax
0x180085652  js      loc_180085734
0x180085658  mov     rcx, rbx
0x18008565b  call    ?TraceCompletionNotificationStart@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?StopOobeLoggingAsyncActionName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const StopOobeLoggingAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(void)
0x180085660  mov     [rbp+arg_10], rdi
0x180085664  lea     rcx, [rbp+arg_10]
0x180085668  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008566d  lea     r8, [rbp+arg_10]; struct IRpcOptions **
0x180085671  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x180085675  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x18008567a  mov     [rbp+ppstm], rdi
0x18008567e  mov     [rbp+var_10], edi
0x180085681  cmp     [rbp+arg_10], rdi
0x180085685  jz      short loc_1800856DF
0x180085687  cmp     [rbp+arg_8], rdi
0x18008568b  jz      short loc_1800856DF
0x18008568d  mov     rdi, [rbp+pUnk]
0x180085691  lea     rcx, [rbp+ppstm]
0x180085695  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008569a  lea     r8, [rbp+ppstm]; ppstm
0x18008569e  mov     edx, 1; fDeleteOnRelease
0x1800856a3  xor     ecx, ecx; hGlobal
0x1800856a5  call    cs:__imp_CreateStreamOnHGlobal
0x1800856ab  mov     [rbp+var_10], eax
0x1800856ae  test    eax, eax
0x1800856b0  js      short loc_1800856E6
0x1800856b2  mov     [rsp+50h+mshlflags], 1; mshlflags
0x1800856ba  mov     [rsp+50h+pvDestContext], 0; pvDestContext
0x1800856c3  xor     r9d, r9d; dwDestContext
0x1800856c6  mov     r8, rdi; pUnk
0x1800856c9  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x1800856d0  mov     rcx, [rbp+ppstm]; pStm
0x1800856d4  call    cs:__imp_CoMarshalInterface
0x1800856da  mov     [rbp+var_10], eax
0x1800856dd  jmp     short loc_1800856E6
0x1800856df  mov     [rbp+var_10], 80004002h
0x1800856e6  mov     rcx, [rbp+arg_8]
0x1800856ea  mov     rax, [rcx]
0x1800856ed  mov     r8d, [rbp+arg_0]
0x1800856f1  mov     rdx, [rbp+pUnk]
0x1800856f5  mov     rax, [rax+18h]
0x1800856f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800856fe  mov     r8, [rbx+80h]
0x180085705  mov     rdx, [rbp+arg_8]
0x180085709  mov     ecx, eax
0x18008570b  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x180085710  mov     edi, eax
0x180085712  mov     rcx, rbx
0x180085715  call    ?UnlockCompleteDelegate@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVUserIntentRecordResult@CloudExperienceHostAPI@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<CloudExperienceHostAPI::UserIntentRecordResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(void)
0x18008571a  call    ?TraceCompletionNotificationComplete@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?UpdateTimeZoneAsyncActionName@CloudExperienceHostAPI@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const CloudExperienceHostAPI::UpdateTimeZoneAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(void)
0x18008571f  nop
0x180085720  lea     rcx, [rbp+ppstm]
0x180085724  call    ??1?$AutoStubBias@U?$IAsyncOperationWithProgress@_NN@Foundation@Windows@@U?$IAsyncOperationProgressHandler@_NN@23@@@QEAA@XZ; AutoStubBias<Windows::Foundation::IAsyncOperationWithProgress<bool,double>,Windows::Foundation::IAsyncOperationProgressHandler<bool,double>>::~AutoStubBias<Windows::Foundation::IAsyncOperationWithProgress<bool,double>,Windows::Foundation::IAsyncOperationProgressHandler<bool,double>>(void)
0x180085729  nop
0x18008572a  lea     rcx, [rbp+arg_10]
0x18008572e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180085733  nop
0x180085734  lea     rcx, [rbp+arg_8]
0x180085738  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008573d  nop
0x18008573e  lea     rcx, [rbp+pUnk]
0x180085742  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180085747  nop
0x180085748  lea     rcx, [rbp+var_20]
0x18008574c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180085751  mov     eax, edi
0x180085753  add     rsp, 50h
0x180085757  pop     rdi
0x180085758  pop     rbx
0x180085759  pop     rbp
0x18008575a  retn
```
