# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<CloudExperienceHostAPI::UserIntentRecordResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x1800c6370`
- end: `0x1800c650b`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVUserIntentRecordResult@CloudExperienceHostAPI@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `411`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800c6520`

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
- `0x1800c4904`
- `0x1800c60e8`
- `0x1800c6370`
- `0x1800dc010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800c6455`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800c6455`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x1800c6484`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x1800c6484`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<CloudExperienceHostAPI::UserIntentRecordResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
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
    if ( (int)Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<CloudExperienceHostAPI::UserIntentRecordResult *>>(
                &v9,
                (__int64)&pUnk) >= 0 )
    {
      v12 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v12, *(_DWORD *)(a1 + 56), -2);
      v13 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
      if ( (int)Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<CloudExperienceHostAPI::UserIntentRecordResult *>>::CopyLocal(
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
0x1800c6370  push    rbp
0x1800c6372  push    rbx
0x1800c6373  push    rdi
0x1800c6374  mov     rbp, rsp
0x1800c6377  sub     rsp, 50h
0x1800c637b  mov     rbx, rcx
0x1800c637e  xor     edi, edi
0x1800c6380  lea     edx, [rdi+1]
0x1800c6383  call    ?TransitionToState@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?StopOobeLoggingAsyncActionName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const StopOobeLoggingAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x1800c6388  cmp     [rbx+88h], edi
0x1800c638e  jle     loc_1800C6501
0x1800c6394  mov     eax, edx
0x1800c6396  lock xadd [rbx+10h], eax
0x1800c639b  inc     eax
0x1800c639d  cmp     eax, edx
0x1800c639f  jnz     loc_1800C6501
0x1800c63a5  mov     [rbp+var_20], rbx
0x1800c63a9  lea     rcx, [rbp+var_20]
0x1800c63ad  call    ?InternalAddRef@?$ComPtr@U?$IAsyncOperationWithProgressCompletedHandler@_NN@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<bool,double>>::InternalAddRef(void)
0x1800c63b2  nop
0x1800c63b3  mov     [rbp+pUnk], rdi
0x1800c63b7  mov     rcx, rbx
0x1800c63ba  call    ?TraceOperationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVHostedApplicationResult@CloudExperienceHostAPI@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?ShowHostedAppCoreOperation@CloudExperienceHostAPI@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<CloudExperienceHostAPI::HostedApplicationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const CloudExperienceHostAPI::ShowHostedAppCoreOperation,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x1800c63bf  lea     rdx, [rbp+pUnk]
0x1800c63c3  lea     rcx, [rbp+var_20]
0x1800c63c7  call    ??$As@U?$IAsyncOperation@PEAVUserIntentRecordResult@CloudExperienceHostAPI@@@Foundation@Windows@@@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IAsyncOperation@PEAVUserIntentRecordResult@CloudExperienceHostAPI@@@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<CloudExperienceHostAPI::UserIntentRecordResult *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<CloudExperienceHostAPI::UserIntentRecordResult *>>>)
0x1800c63cc  test    eax, eax
0x1800c63ce  js      loc_1800C64EE
0x1800c63d4  mov     [rbp+arg_0], 0FFFFFFFEh
0x1800c63db  mov     ecx, [rbx+38h]
0x1800c63de  mov     eax, [rbp+arg_0]
0x1800c63e1  lock cmpxchg [rbp+arg_0], ecx
0x1800c63e6  mov     [rbp+arg_8], rdi
0x1800c63ea  lea     rcx, [rbp+arg_8]
0x1800c63ee  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c63f3  lea     rcx, [rbx+78h]
0x1800c63f7  lea     r8, [rbp+arg_8]
0x1800c63fb  call    ?CopyLocal@?$GitPtrSupportsAgile@U?$IAsyncOperationCompletedHandler@PEAVUserIntentRecordResult@CloudExperienceHostAPI@@@Foundation@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<CloudExperienceHostAPI::UserIntentRecordResult *>>::CopyLocal(_GUID const &,void * *)
0x1800c6400  test    eax, eax
0x1800c6402  js      loc_1800C64E4
0x1800c6408  mov     rcx, rbx
0x1800c640b  call    ?TraceCompletionNotificationStart@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?StopOobeLoggingAsyncActionName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const StopOobeLoggingAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(void)
0x1800c6410  mov     [rbp+arg_10], rdi
0x1800c6414  lea     rcx, [rbp+arg_10]
0x1800c6418  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c641d  lea     r8, [rbp+arg_10]; struct IRpcOptions **
0x1800c6421  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x1800c6425  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x1800c642a  mov     [rbp+ppstm], rdi
0x1800c642e  mov     [rbp+var_10], edi
0x1800c6431  cmp     [rbp+arg_10], rdi
0x1800c6435  jz      short loc_1800C648F
0x1800c6437  cmp     [rbp+arg_8], rdi
0x1800c643b  jz      short loc_1800C648F
0x1800c643d  mov     rdi, [rbp+pUnk]
0x1800c6441  lea     rcx, [rbp+ppstm]
0x1800c6445  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c644a  lea     r8, [rbp+ppstm]; ppstm
0x1800c644e  mov     edx, 1; fDeleteOnRelease
0x1800c6453  xor     ecx, ecx; hGlobal
0x1800c6455  call    cs:__imp_CreateStreamOnHGlobal
0x1800c645b  mov     [rbp+var_10], eax
0x1800c645e  test    eax, eax
0x1800c6460  js      short loc_1800C6496
0x1800c6462  mov     [rsp+50h+mshlflags], 1; mshlflags
0x1800c646a  mov     [rsp+50h+pvDestContext], 0; pvDestContext
0x1800c6473  xor     r9d, r9d; dwDestContext
0x1800c6476  mov     r8, rdi; pUnk
0x1800c6479  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x1800c6480  mov     rcx, [rbp+ppstm]; pStm
0x1800c6484  call    cs:__imp_CoMarshalInterface
0x1800c648a  mov     [rbp+var_10], eax
0x1800c648d  jmp     short loc_1800C6496
0x1800c648f  mov     [rbp+var_10], 80004002h
0x1800c6496  mov     rcx, [rbp+arg_8]
0x1800c649a  mov     rax, [rcx]
0x1800c649d  mov     r8d, [rbp+arg_0]
0x1800c64a1  mov     rdx, [rbp+pUnk]
0x1800c64a5  mov     rax, [rax+18h]
0x1800c64a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c64ae  mov     r8, [rbx+80h]
0x1800c64b5  mov     rdx, [rbp+arg_8]
0x1800c64b9  mov     ecx, eax
0x1800c64bb  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x1800c64c0  mov     edi, eax
0x1800c64c2  mov     rcx, rbx
0x1800c64c5  call    ?UnlockCompleteDelegate@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVUserIntentRecordResult@CloudExperienceHostAPI@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<CloudExperienceHostAPI::UserIntentRecordResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(void)
0x1800c64ca  call    ?TraceCompletionNotificationComplete@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?UpdateTimeZoneAsyncActionName@CloudExperienceHostAPI@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const CloudExperienceHostAPI::UpdateTimeZoneAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(void)
0x1800c64cf  nop
0x1800c64d0  lea     rcx, [rbp+ppstm]
0x1800c64d4  call    ??1?$AutoStubBias@U?$IAsyncOperationWithProgress@_NN@Foundation@Windows@@U?$IAsyncOperationProgressHandler@_NN@23@@@QEAA@XZ; AutoStubBias<Windows::Foundation::IAsyncOperationWithProgress<bool,double>,Windows::Foundation::IAsyncOperationProgressHandler<bool,double>>::~AutoStubBias<Windows::Foundation::IAsyncOperationWithProgress<bool,double>,Windows::Foundation::IAsyncOperationProgressHandler<bool,double>>(void)
0x1800c64d9  nop
0x1800c64da  lea     rcx, [rbp+arg_10]
0x1800c64de  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c64e3  nop
0x1800c64e4  lea     rcx, [rbp+arg_8]
0x1800c64e8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c64ed  nop
0x1800c64ee  lea     rcx, [rbp+pUnk]
0x1800c64f2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c64f7  nop
0x1800c64f8  lea     rcx, [rbp+var_20]
0x1800c64fc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c6501  mov     eax, edi
0x1800c6503  add     rsp, 50h
0x1800c6507  pop     rdi
0x1800c6508  pop     rbx
0x1800c6509  pop     rbp
0x1800c650a  retn
```
