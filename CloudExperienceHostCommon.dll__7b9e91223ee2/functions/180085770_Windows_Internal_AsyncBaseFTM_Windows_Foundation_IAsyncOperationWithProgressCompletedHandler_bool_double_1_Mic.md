# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<bool,double>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x180085770`
- end: `0x18008590b`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationWithProgressCompletedHandler@_NN@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `411`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180085980`

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
- `0x18007f248`
- `0x180084e88`
- `0x180085770`
- `0x1800dc010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180085855`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180085855`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180085884`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180085884`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<bool,double>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
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
    if ( (int)Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperationWithProgress<bool,double>>(
                &v9,
                (__int64)&pUnk) >= 0 )
    {
      v12 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v12, *(_DWORD *)(a1 + 56), -2);
      v13 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
      if ( (int)Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<bool,double>>::CopyLocal(
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
0x180085770  push    rbp
0x180085772  push    rbx
0x180085773  push    rdi
0x180085774  mov     rbp, rsp
0x180085777  sub     rsp, 50h
0x18008577b  mov     rbx, rcx
0x18008577e  xor     edi, edi
0x180085780  lea     edx, [rdi+1]
0x180085783  call    ?TransitionToState@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?StopOobeLoggingAsyncActionName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const StopOobeLoggingAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x180085788  cmp     [rbx+88h], edi
0x18008578e  jle     loc_180085901
0x180085794  mov     eax, edx
0x180085796  lock xadd [rbx+10h], eax
0x18008579b  inc     eax
0x18008579d  cmp     eax, edx
0x18008579f  jnz     loc_180085901
0x1800857a5  mov     [rbp+var_20], rbx
0x1800857a9  lea     rcx, [rbp+var_20]
0x1800857ad  call    ?InternalAddRef@?$ComPtr@U?$IAsyncOperationWithProgressCompletedHandler@_NN@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<bool,double>>::InternalAddRef(void)
0x1800857b2  nop
0x1800857b3  mov     [rbp+pUnk], rdi
0x1800857b7  mov     rcx, rbx
0x1800857ba  call    ?TraceOperationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVHostedApplicationResult@CloudExperienceHostAPI@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?ShowHostedAppCoreOperation@CloudExperienceHostAPI@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<CloudExperienceHostAPI::HostedApplicationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const CloudExperienceHostAPI::ShowHostedAppCoreOperation,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x1800857bf  lea     rdx, [rbp+pUnk]
0x1800857c3  lea     rcx, [rbp+var_20]
0x1800857c7  call    ??$As@U?$IAsyncOperationWithProgress@_NN@Foundation@Windows@@@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IAsyncOperationWithProgress@_NN@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperationWithProgress<bool,double>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationWithProgress<bool,double>>>)
0x1800857cc  test    eax, eax
0x1800857ce  js      loc_1800858EE
0x1800857d4  mov     [rbp+arg_0], 0FFFFFFFEh
0x1800857db  mov     ecx, [rbx+38h]
0x1800857de  mov     eax, [rbp+arg_0]
0x1800857e1  lock cmpxchg [rbp+arg_0], ecx
0x1800857e6  mov     [rbp+arg_8], rdi
0x1800857ea  lea     rcx, [rbp+arg_8]
0x1800857ee  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800857f3  lea     rcx, [rbx+78h]
0x1800857f7  lea     r8, [rbp+arg_8]
0x1800857fb  call    ?CopyLocal@?$GitPtrSupportsAgile@U?$IAsyncOperationWithProgressCompletedHandler@_NN@Foundation@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<bool,double>>::CopyLocal(_GUID const &,void * *)
0x180085800  test    eax, eax
0x180085802  js      loc_1800858E4
0x180085808  mov     rcx, rbx
0x18008580b  call    ?TraceCompletionNotificationStart@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?StopOobeLoggingAsyncActionName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const StopOobeLoggingAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(void)
0x180085810  mov     [rbp+arg_10], rdi
0x180085814  lea     rcx, [rbp+arg_10]
0x180085818  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008581d  lea     r8, [rbp+arg_10]; struct IRpcOptions **
0x180085821  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x180085825  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x18008582a  mov     [rbp+ppstm], rdi
0x18008582e  mov     [rbp+var_10], edi
0x180085831  cmp     [rbp+arg_10], rdi
0x180085835  jz      short loc_18008588F
0x180085837  cmp     [rbp+arg_8], rdi
0x18008583b  jz      short loc_18008588F
0x18008583d  mov     rdi, [rbp+pUnk]
0x180085841  lea     rcx, [rbp+ppstm]
0x180085845  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008584a  lea     r8, [rbp+ppstm]; ppstm
0x18008584e  mov     edx, 1; fDeleteOnRelease
0x180085853  xor     ecx, ecx; hGlobal
0x180085855  call    cs:__imp_CreateStreamOnHGlobal
0x18008585b  mov     [rbp+var_10], eax
0x18008585e  test    eax, eax
0x180085860  js      short loc_180085896
0x180085862  mov     [rsp+50h+mshlflags], 1; mshlflags
0x18008586a  mov     [rsp+50h+pvDestContext], 0; pvDestContext
0x180085873  xor     r9d, r9d; dwDestContext
0x180085876  mov     r8, rdi; pUnk
0x180085879  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180085880  mov     rcx, [rbp+ppstm]; pStm
0x180085884  call    cs:__imp_CoMarshalInterface
0x18008588a  mov     [rbp+var_10], eax
0x18008588d  jmp     short loc_180085896
0x18008588f  mov     [rbp+var_10], 80004002h
0x180085896  mov     rcx, [rbp+arg_8]
0x18008589a  mov     rax, [rcx]
0x18008589d  mov     r8d, [rbp+arg_0]
0x1800858a1  mov     rdx, [rbp+pUnk]
0x1800858a5  mov     rax, [rax+18h]
0x1800858a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800858ae  mov     r8, [rbx+80h]
0x1800858b5  mov     rdx, [rbp+arg_8]
0x1800858b9  mov     ecx, eax
0x1800858bb  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x1800858c0  mov     edi, eax
0x1800858c2  mov     rcx, rbx
0x1800858c5  call    ?UnlockCompleteDelegate@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVUserIntentRecordResult@CloudExperienceHostAPI@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<CloudExperienceHostAPI::UserIntentRecordResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(void)
0x1800858ca  call    ?TraceCompletionNotificationComplete@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?UpdateTimeZoneAsyncActionName@CloudExperienceHostAPI@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const CloudExperienceHostAPI::UpdateTimeZoneAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(void)
0x1800858cf  nop
0x1800858d0  lea     rcx, [rbp+ppstm]
0x1800858d4  call    ??1?$AutoStubBias@U?$IAsyncOperationWithProgress@_NN@Foundation@Windows@@U?$IAsyncOperationProgressHandler@_NN@23@@@QEAA@XZ; AutoStubBias<Windows::Foundation::IAsyncOperationWithProgress<bool,double>,Windows::Foundation::IAsyncOperationProgressHandler<bool,double>>::~AutoStubBias<Windows::Foundation::IAsyncOperationWithProgress<bool,double>,Windows::Foundation::IAsyncOperationProgressHandler<bool,double>>(void)
0x1800858d9  nop
0x1800858da  lea     rcx, [rbp+arg_10]
0x1800858de  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800858e3  nop
0x1800858e4  lea     rcx, [rbp+arg_8]
0x1800858e8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800858ed  nop
0x1800858ee  lea     rcx, [rbp+pUnk]
0x1800858f2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800858f7  nop
0x1800858f8  lea     rcx, [rbp+var_20]
0x1800858fc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180085901  mov     eax, edi
0x180085903  add     rsp, 50h
0x180085907  pop     rdi
0x180085908  pop     rbx
0x180085909  pop     rbp
0x18008590a  retn
```
