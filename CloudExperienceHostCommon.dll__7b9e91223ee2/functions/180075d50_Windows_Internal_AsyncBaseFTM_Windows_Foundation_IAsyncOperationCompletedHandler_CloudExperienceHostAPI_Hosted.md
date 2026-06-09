# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<CloudExperienceHostAPI::HostedApplicationResult *>,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const CloudExperienceHostAPI::ShowHostedAppCoreOperation,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x180075d50`
- end: `0x180075eeb`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVHostedApplicationResult@CloudExperienceHostAPI@@@Foundation@Windows@@$00U?$AsyncCausalityOptions@$1?ShowHostedAppCoreOperation@CloudExperienceHostAPI@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `411`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180075f00`

## callees

- `0x18000504c`
- `0x1800050b4`
- `0x18000fa5c`
- `0x180014c54`
- `0x180072b04`
- `0x18007435c`
- `0x180075918`
- `0x180075d50`
- `0x180075f70`
- `0x180076928`
- `0x1800791dc`
- `0x18007920c`
- `0x1800793d0`
- `0x1800dc010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180075e35`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180075e35`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180075e64`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180075e64`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<CloudExperienceHostAPI::HostedApplicationResult *>,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const CloudExperienceHostAPI::ShowHostedAppCoreOperation,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
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
    if ( (int)Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<CloudExperienceHostAPI::HostedApplicationResult *>>(
                &v9,
                (__int64)&pUnk) >= 0 )
    {
      v12 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v12, *(_DWORD *)(a1 + 56), -2);
      v13 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
      if ( (int)Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<CloudExperienceHostAPI::HostedApplicationResult *>>::CopyLocal(
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
0x180075d50  push    rbp
0x180075d52  push    rbx
0x180075d53  push    rdi
0x180075d54  mov     rbp, rsp
0x180075d57  sub     rsp, 50h
0x180075d5b  mov     rbx, rcx
0x180075d5e  xor     edi, edi
0x180075d60  lea     edx, [rdi+1]
0x180075d63  call    ?TransitionToState@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?StopOobeLoggingAsyncActionName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const StopOobeLoggingAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x180075d68  cmp     [rbx+88h], edi
0x180075d6e  jle     loc_180075EE1
0x180075d74  mov     eax, edx
0x180075d76  lock xadd [rbx+10h], eax
0x180075d7b  inc     eax
0x180075d7d  cmp     eax, edx
0x180075d7f  jnz     loc_180075EE1
0x180075d85  mov     [rbp+var_20], rbx
0x180075d89  lea     rcx, [rbp+var_20]
0x180075d8d  call    ?InternalAddRef@?$ComPtr@U?$IAsyncOperationWithProgressCompletedHandler@_NN@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<bool,double>>::InternalAddRef(void)
0x180075d92  nop
0x180075d93  mov     [rbp+pUnk], rdi
0x180075d97  mov     rcx, rbx
0x180075d9a  call    ?TraceOperationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVHostedApplicationResult@CloudExperienceHostAPI@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?ShowHostedAppCoreOperation@CloudExperienceHostAPI@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<CloudExperienceHostAPI::HostedApplicationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const CloudExperienceHostAPI::ShowHostedAppCoreOperation,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x180075d9f  lea     rdx, [rbp+pUnk]
0x180075da3  lea     rcx, [rbp+var_20]
0x180075da7  call    ??$As@U?$IAsyncOperation@PEAVHostedApplicationResult@CloudExperienceHostAPI@@@Foundation@Windows@@@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IAsyncOperation@PEAVHostedApplicationResult@CloudExperienceHostAPI@@@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<CloudExperienceHostAPI::HostedApplicationResult *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<CloudExperienceHostAPI::HostedApplicationResult *>>>)
0x180075dac  test    eax, eax
0x180075dae  js      loc_180075ECE
0x180075db4  mov     [rbp+arg_0], 0FFFFFFFEh
0x180075dbb  mov     ecx, [rbx+38h]
0x180075dbe  mov     eax, [rbp+arg_0]
0x180075dc1  lock cmpxchg [rbp+arg_0], ecx
0x180075dc6  mov     [rbp+arg_8], rdi
0x180075dca  lea     rcx, [rbp+arg_8]
0x180075dce  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180075dd3  lea     rcx, [rbx+78h]
0x180075dd7  lea     r8, [rbp+arg_8]
0x180075ddb  call    ?CopyLocal@?$GitPtrSupportsAgile@U?$IAsyncOperationCompletedHandler@PEAVHostedApplicationResult@CloudExperienceHostAPI@@@Foundation@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<CloudExperienceHostAPI::HostedApplicationResult *>>::CopyLocal(_GUID const &,void * *)
0x180075de0  test    eax, eax
0x180075de2  js      loc_180075EC4
0x180075de8  mov     rcx, rbx
0x180075deb  call    ?TraceCompletionNotificationStart@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?StopOobeLoggingAsyncActionName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const StopOobeLoggingAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(void)
0x180075df0  mov     [rbp+arg_10], rdi
0x180075df4  lea     rcx, [rbp+arg_10]
0x180075df8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180075dfd  lea     r8, [rbp+arg_10]; struct IRpcOptions **
0x180075e01  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x180075e05  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x180075e0a  mov     [rbp+ppstm], rdi
0x180075e0e  mov     [rbp+var_10], edi
0x180075e11  cmp     [rbp+arg_10], rdi
0x180075e15  jz      short loc_180075E6F
0x180075e17  cmp     [rbp+arg_8], rdi
0x180075e1b  jz      short loc_180075E6F
0x180075e1d  mov     rdi, [rbp+pUnk]
0x180075e21  lea     rcx, [rbp+ppstm]
0x180075e25  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180075e2a  lea     r8, [rbp+ppstm]; ppstm
0x180075e2e  mov     edx, 1; fDeleteOnRelease
0x180075e33  xor     ecx, ecx; hGlobal
0x180075e35  call    cs:__imp_CreateStreamOnHGlobal
0x180075e3b  mov     [rbp+var_10], eax
0x180075e3e  test    eax, eax
0x180075e40  js      short loc_180075E76
0x180075e42  mov     [rsp+50h+mshlflags], 1; mshlflags
0x180075e4a  mov     [rsp+50h+pvDestContext], 0; pvDestContext
0x180075e53  xor     r9d, r9d; dwDestContext
0x180075e56  mov     r8, rdi; pUnk
0x180075e59  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180075e60  mov     rcx, [rbp+ppstm]; pStm
0x180075e64  call    cs:__imp_CoMarshalInterface
0x180075e6a  mov     [rbp+var_10], eax
0x180075e6d  jmp     short loc_180075E76
0x180075e6f  mov     [rbp+var_10], 80004002h
0x180075e76  mov     rcx, [rbp+arg_8]
0x180075e7a  mov     rax, [rcx]
0x180075e7d  mov     r8d, [rbp+arg_0]
0x180075e81  mov     rdx, [rbp+pUnk]
0x180075e85  mov     rax, [rax+18h]
0x180075e89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075e8e  mov     r8, [rbx+80h]
0x180075e95  mov     rdx, [rbp+arg_8]
0x180075e99  mov     ecx, eax
0x180075e9b  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x180075ea0  mov     edi, eax
0x180075ea2  mov     rcx, rbx
0x180075ea5  call    ?UnlockCompleteDelegate@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVUserIntentRecordResult@CloudExperienceHostAPI@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<CloudExperienceHostAPI::UserIntentRecordResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(void)
0x180075eaa  call    ?TraceCompletionNotificationComplete@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?UpdateTimeZoneAsyncActionName@CloudExperienceHostAPI@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const CloudExperienceHostAPI::UpdateTimeZoneAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(void)
0x180075eaf  nop
0x180075eb0  lea     rcx, [rbp+ppstm]
0x180075eb4  call    ??1?$AutoStubBias@U?$IAsyncOperationWithProgress@_NN@Foundation@Windows@@U?$IAsyncOperationProgressHandler@_NN@23@@@QEAA@XZ; AutoStubBias<Windows::Foundation::IAsyncOperationWithProgress<bool,double>,Windows::Foundation::IAsyncOperationProgressHandler<bool,double>>::~AutoStubBias<Windows::Foundation::IAsyncOperationWithProgress<bool,double>,Windows::Foundation::IAsyncOperationProgressHandler<bool,double>>(void)
0x180075eb9  nop
0x180075eba  lea     rcx, [rbp+arg_10]
0x180075ebe  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180075ec3  nop
0x180075ec4  lea     rcx, [rbp+arg_8]
0x180075ec8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180075ecd  nop
0x180075ece  lea     rcx, [rbp+pUnk]
0x180075ed2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180075ed7  nop
0x180075ed8  lea     rcx, [rbp+var_20]
0x180075edc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180075ee1  mov     eax, edi
0x180075ee3  add     rsp, 50h
0x180075ee7  pop     rdi
0x180075ee8  pop     rbx
0x180075ee9  pop     rbp
0x180075eea  retn
```
