# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::SpeechRecognition::SpeechRecognitionResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x180085410`
- end: `0x1800855ab`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVSpeechRecognitionResult@SpeechRecognition@Media@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `411`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180085920`

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
- `0x18007f1a8`
- `0x180084df8`
- `0x180085410`
- `0x1800dc010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800854f5`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800854f5`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180085524`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180085524`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::SpeechRecognition::SpeechRecognitionResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
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
    if ( (int)Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<Windows::Media::SpeechRecognition::SpeechRecognitionResult *>>(
                &v9,
                (__int64)&pUnk) >= 0 )
    {
      v12 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v12, *(_DWORD *)(a1 + 56), -2);
      v13 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
      if ( (int)Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::SpeechRecognition::SpeechRecognitionResult *>>::CopyLocal(
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
0x180085410  push    rbp
0x180085412  push    rbx
0x180085413  push    rdi
0x180085414  mov     rbp, rsp
0x180085417  sub     rsp, 50h
0x18008541b  mov     rbx, rcx
0x18008541e  xor     edi, edi
0x180085420  lea     edx, [rdi+1]
0x180085423  call    ?TransitionToState@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?StopOobeLoggingAsyncActionName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const StopOobeLoggingAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x180085428  cmp     [rbx+88h], edi
0x18008542e  jle     loc_1800855A1
0x180085434  mov     eax, edx
0x180085436  lock xadd [rbx+10h], eax
0x18008543b  inc     eax
0x18008543d  cmp     eax, edx
0x18008543f  jnz     loc_1800855A1
0x180085445  mov     [rbp+var_20], rbx
0x180085449  lea     rcx, [rbp+var_20]
0x18008544d  call    ?InternalAddRef@?$ComPtr@U?$IAsyncOperationWithProgressCompletedHandler@_NN@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<bool,double>>::InternalAddRef(void)
0x180085452  nop
0x180085453  mov     [rbp+pUnk], rdi
0x180085457  mov     rcx, rbx
0x18008545a  call    ?TraceOperationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVHostedApplicationResult@CloudExperienceHostAPI@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?ShowHostedAppCoreOperation@CloudExperienceHostAPI@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<CloudExperienceHostAPI::HostedApplicationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const CloudExperienceHostAPI::ShowHostedAppCoreOperation,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x18008545f  lea     rdx, [rbp+pUnk]
0x180085463  lea     rcx, [rbp+var_20]
0x180085467  call    ??$As@U?$IAsyncOperation@PEAVSpeechRecognitionResult@SpeechRecognition@Media@Windows@@@Foundation@Windows@@@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IAsyncOperation@PEAVSpeechRecognitionResult@SpeechRecognition@Media@Windows@@@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<Windows::Media::SpeechRecognition::SpeechRecognitionResult *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Media::SpeechRecognition::SpeechRecognitionResult *>>>)
0x18008546c  test    eax, eax
0x18008546e  js      loc_18008558E
0x180085474  mov     [rbp+arg_0], 0FFFFFFFEh
0x18008547b  mov     ecx, [rbx+38h]
0x18008547e  mov     eax, [rbp+arg_0]
0x180085481  lock cmpxchg [rbp+arg_0], ecx
0x180085486  mov     [rbp+arg_8], rdi
0x18008548a  lea     rcx, [rbp+arg_8]
0x18008548e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180085493  lea     rcx, [rbx+78h]
0x180085497  lea     r8, [rbp+arg_8]
0x18008549b  call    ?CopyLocal@?$GitPtrSupportsAgile@U?$IAsyncOperationCompletedHandler@PEAVSpeechRecognitionResult@SpeechRecognition@Media@Windows@@@Foundation@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Media::SpeechRecognition::SpeechRecognitionResult *>>::CopyLocal(_GUID const &,void * *)
0x1800854a0  test    eax, eax
0x1800854a2  js      loc_180085584
0x1800854a8  mov     rcx, rbx
0x1800854ab  call    ?TraceCompletionNotificationStart@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?StopOobeLoggingAsyncActionName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const StopOobeLoggingAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(void)
0x1800854b0  mov     [rbp+arg_10], rdi
0x1800854b4  lea     rcx, [rbp+arg_10]
0x1800854b8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800854bd  lea     r8, [rbp+arg_10]; struct IRpcOptions **
0x1800854c1  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x1800854c5  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x1800854ca  mov     [rbp+ppstm], rdi
0x1800854ce  mov     [rbp+var_10], edi
0x1800854d1  cmp     [rbp+arg_10], rdi
0x1800854d5  jz      short loc_18008552F
0x1800854d7  cmp     [rbp+arg_8], rdi
0x1800854db  jz      short loc_18008552F
0x1800854dd  mov     rdi, [rbp+pUnk]
0x1800854e1  lea     rcx, [rbp+ppstm]
0x1800854e5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800854ea  lea     r8, [rbp+ppstm]; ppstm
0x1800854ee  mov     edx, 1; fDeleteOnRelease
0x1800854f3  xor     ecx, ecx; hGlobal
0x1800854f5  call    cs:__imp_CreateStreamOnHGlobal
0x1800854fb  mov     [rbp+var_10], eax
0x1800854fe  test    eax, eax
0x180085500  js      short loc_180085536
0x180085502  mov     [rsp+50h+mshlflags], 1; mshlflags
0x18008550a  mov     [rsp+50h+pvDestContext], 0; pvDestContext
0x180085513  xor     r9d, r9d; dwDestContext
0x180085516  mov     r8, rdi; pUnk
0x180085519  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180085520  mov     rcx, [rbp+ppstm]; pStm
0x180085524  call    cs:__imp_CoMarshalInterface
0x18008552a  mov     [rbp+var_10], eax
0x18008552d  jmp     short loc_180085536
0x18008552f  mov     [rbp+var_10], 80004002h
0x180085536  mov     rcx, [rbp+arg_8]
0x18008553a  mov     rax, [rcx]
0x18008553d  mov     r8d, [rbp+arg_0]
0x180085541  mov     rdx, [rbp+pUnk]
0x180085545  mov     rax, [rax+18h]
0x180085549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008554e  mov     r8, [rbx+80h]
0x180085555  mov     rdx, [rbp+arg_8]
0x180085559  mov     ecx, eax
0x18008555b  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x180085560  mov     edi, eax
0x180085562  mov     rcx, rbx
0x180085565  call    ?UnlockCompleteDelegate@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVUserIntentRecordResult@CloudExperienceHostAPI@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<CloudExperienceHostAPI::UserIntentRecordResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(void)
0x18008556a  call    ?TraceCompletionNotificationComplete@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?UpdateTimeZoneAsyncActionName@CloudExperienceHostAPI@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const CloudExperienceHostAPI::UpdateTimeZoneAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(void)
0x18008556f  nop
0x180085570  lea     rcx, [rbp+ppstm]
0x180085574  call    ??1?$AutoStubBias@U?$IAsyncOperationWithProgress@_NN@Foundation@Windows@@U?$IAsyncOperationProgressHandler@_NN@23@@@QEAA@XZ; AutoStubBias<Windows::Foundation::IAsyncOperationWithProgress<bool,double>,Windows::Foundation::IAsyncOperationProgressHandler<bool,double>>::~AutoStubBias<Windows::Foundation::IAsyncOperationWithProgress<bool,double>,Windows::Foundation::IAsyncOperationProgressHandler<bool,double>>(void)
0x180085579  nop
0x18008557a  lea     rcx, [rbp+arg_10]
0x18008557e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180085583  nop
0x180085584  lea     rcx, [rbp+arg_8]
0x180085588  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008558d  nop
0x18008558e  lea     rcx, [rbp+pUnk]
0x180085592  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180085597  nop
0x180085598  lea     rcx, [rbp+var_20]
0x18008559c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800855a1  mov     eax, edi
0x1800855a3  add     rsp, 50h
0x1800855a7  pop     rdi
0x1800855a8  pop     rbx
0x1800855a9  pop     rbp
0x1800855aa  retn
```
