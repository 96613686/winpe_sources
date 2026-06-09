# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceAmount *,EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceProgress>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x18002da40`
- end: `0x18002dbdb`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAVExpectedAndCurrentResourceAmount@Enrollment@EnterpriseDeviceManagement@@UExpectedAndCurrentResourceProgress@23@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `411`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002de90`

## callees

- `0x18000992c`
- `0x180017154`
- `0x180017838`
- `0x180018eb8`
- `0x180018ff0`
- `0x18001b498`
- `0x18002b5a8`
- `0x18002da40`
- `0x180037b70`
- `0x180037ba0`
- `0x180037c44`
- `0x180038830`
- `0x18003899c`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18002db54`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18002db54`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18002db25`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18002db25`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceAmount *,EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceProgress>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
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
  Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<enum EnterpriseDeviceManagement::Enrollment::MDMProgressMode>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(
    a1,
    1);
  if ( *(int *)(a1 + 136) > 0 && _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 16), v3) + 1 == v3 )
  {
    v9 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))a1;
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(&v9);
    pUnk = 0;
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const AsyncActionAttachAsync,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(a1);
    if ( (int)Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperationWithProgress<EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceAmount *,EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceProgress>>(
                &v9,
                (__int64)&pUnk) >= 0 )
    {
      v12 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v12, *(_DWORD *)(a1 + 56), -2);
      v13 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
      if ( (int)Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceAmount *,EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceProgress>>::CopyLocal(
                  a1 + 120,
                  v4,
                  &v13) >= 0 )
      {
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const RebuildSchedulesAndSyncWithServerAsyncName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(a1);
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
        Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<EnterpriseDeviceManagement::Enrollment::ReflectedEnrollmentResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(a1);
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete();
        AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>>(&ppstm);
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
0x18002da40  push    rbp
0x18002da42  push    rbx
0x18002da43  push    rdi
0x18002da44  mov     rbp, rsp
0x18002da47  sub     rsp, 50h
0x18002da4b  mov     rbx, rcx
0x18002da4e  xor     edi, edi
0x18002da50  lea     edx, [rdi+1]
0x18002da53  call    ?TransitionToState@?$AsyncBase@U?$IAsyncOperationCompletedHandler@W4MDMProgressMode@Enrollment@EnterpriseDeviceManagement@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<EnterpriseDeviceManagement::Enrollment::MDMProgressMode>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x18002da58  cmp     [rbx+88h], edi
0x18002da5e  jle     loc_18002DBD1
0x18002da64  mov     eax, edx
0x18002da66  lock xadd [rbx+10h], eax
0x18002da6b  inc     eax
0x18002da6d  cmp     eax, edx
0x18002da6f  jnz     loc_18002DBD1
0x18002da75  mov     [rbp+var_20], rbx
0x18002da79  lea     rcx, [rbp+var_20]
0x18002da7d  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x18002da82  nop
0x18002da83  mov     [rbp+pUnk], rdi
0x18002da87  mov     rcx, rbx
0x18002da8a  call    ?TraceOperationComplete@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?AsyncActionAttachAsync@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const AsyncActionAttachAsync,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x18002da8f  lea     rdx, [rbp+pUnk]
0x18002da93  lea     rcx, [rbp+var_20]
0x18002da97  call    ??$As@U?$IAsyncOperationWithProgress@PEAVExpectedAndCurrentResourceAmount@Enrollment@EnterpriseDeviceManagement@@UExpectedAndCurrentResourceProgress@23@@Foundation@Windows@@@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IAsyncOperationWithProgress@PEAVExpectedAndCurrentResourceAmount@Enrollment@EnterpriseDeviceManagement@@UExpectedAndCurrentResourceProgress@23@@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperationWithProgress<EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceAmount *,EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceProgress>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationWithProgress<EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceAmount *,EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceProgress>>>)
0x18002da9c  test    eax, eax
0x18002da9e  js      loc_18002DBBE
0x18002daa4  mov     [rbp+arg_0], 0FFFFFFFEh
0x18002daab  mov     ecx, [rbx+38h]
0x18002daae  mov     eax, [rbp+arg_0]
0x18002dab1  lock cmpxchg [rbp+arg_0], ecx
0x18002dab6  mov     [rbp+arg_8], rdi
0x18002daba  lea     rcx, [rbp+arg_8]
0x18002dabe  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002dac3  lea     rcx, [rbx+78h]
0x18002dac7  lea     r8, [rbp+arg_8]
0x18002dacb  call    ?CopyLocal@?$GitPtrSupportsAgile@U?$IAsyncOperationWithProgressCompletedHandler@PEAVExpectedAndCurrentResourceAmount@Enrollment@EnterpriseDeviceManagement@@UExpectedAndCurrentResourceProgress@23@@Foundation@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceAmount *,EnterpriseDeviceManagement::Enrollment::ExpectedAndCurrentResourceProgress>>::CopyLocal(_GUID const &,void * *)
0x18002dad0  test    eax, eax
0x18002dad2  js      loc_18002DBB4
0x18002dad8  mov     rcx, rbx
0x18002dadb  call    ?TraceCompletionNotificationStart@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?RebuildSchedulesAndSyncWithServerAsyncName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const RebuildSchedulesAndSyncWithServerAsyncName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(void)
0x18002dae0  mov     [rbp+arg_10], rdi
0x18002dae4  lea     rcx, [rbp+arg_10]
0x18002dae8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002daed  lea     r8, [rbp+arg_10]; struct IRpcOptions **
0x18002daf1  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x18002daf5  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x18002dafa  mov     [rbp+ppstm], rdi
0x18002dafe  mov     [rbp+var_10], edi
0x18002db01  cmp     [rbp+arg_10], rdi
0x18002db05  jz      short loc_18002DB5F
0x18002db07  cmp     [rbp+arg_8], rdi
0x18002db0b  jz      short loc_18002DB5F
0x18002db0d  mov     rdi, [rbp+pUnk]
0x18002db11  lea     rcx, [rbp+ppstm]
0x18002db15  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002db1a  lea     r8, [rbp+ppstm]; ppstm
0x18002db1e  mov     edx, 1; fDeleteOnRelease
0x18002db23  xor     ecx, ecx; hGlobal
0x18002db25  call    cs:__imp_CreateStreamOnHGlobal
0x18002db2b  mov     [rbp+var_10], eax
0x18002db2e  test    eax, eax
0x18002db30  js      short loc_18002DB66
0x18002db32  mov     [rsp+50h+mshlflags], 1; mshlflags
0x18002db3a  mov     [rsp+50h+pvDestContext], 0; pvDestContext
0x18002db43  xor     r9d, r9d; dwDestContext
0x18002db46  mov     r8, rdi; pUnk
0x18002db49  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18002db50  mov     rcx, [rbp+ppstm]; pStm
0x18002db54  call    cs:__imp_CoMarshalInterface
0x18002db5a  mov     [rbp+var_10], eax
0x18002db5d  jmp     short loc_18002DB66
0x18002db5f  mov     [rbp+var_10], 80004002h
0x18002db66  mov     rcx, [rbp+arg_8]
0x18002db6a  mov     rax, [rcx]
0x18002db6d  mov     r8d, [rbp+arg_0]
0x18002db71  mov     rdx, [rbp+pUnk]
0x18002db75  mov     rax, [rax+18h]
0x18002db79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002db7e  mov     r8, [rbx+80h]
0x18002db85  mov     rdx, [rbp+arg_8]
0x18002db89  mov     ecx, eax
0x18002db8b  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x18002db90  mov     edi, eax
0x18002db92  mov     rcx, rbx
0x18002db95  call    ?UnlockCompleteDelegate@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVReflectedEnrollmentResult@Enrollment@EnterpriseDeviceManagement@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<EnterpriseDeviceManagement::Enrollment::ReflectedEnrollmentResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(void)
0x18002db9a  call    ?TraceCompletionNotificationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(void)
0x18002db9f  nop
0x18002dba0  lea     rcx, [rbp+ppstm]
0x18002dba4  call    ??1?$AutoStubBias@U?$IAsyncOperation@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@23@@@QEAA@XZ; AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>>(void)
0x18002dba9  nop
0x18002dbaa  lea     rcx, [rbp+arg_10]
0x18002dbae  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002dbb3  nop
0x18002dbb4  lea     rcx, [rbp+arg_8]
0x18002dbb8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002dbbd  nop
0x18002dbbe  lea     rcx, [rbp+pUnk]
0x18002dbc2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002dbc7  nop
0x18002dbc8  lea     rcx, [rbp+var_20]
0x18002dbcc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002dbd1  mov     eax, edi
0x18002dbd3  add     rsp, 50h
0x18002dbd7  pop     rdi
0x18002dbd8  pop     rbx
0x18002dbd9  pop     rbp
0x18002dbda  retn
```
