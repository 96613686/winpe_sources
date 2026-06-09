# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<int>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x18002b8e0`
- end: `0x18002ba88`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@H@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `424`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002c7b0`

## callees

- `0x180009be4`
- `0x180017944`
- `0x180017fc0`
- `0x1800180fc`
- `0x18001823c`
- `0x180019720`
- `0x180029dc8`
- `0x18002b8e0`
- `0x180036e18`
- `0x180036e4c`
- `0x180036ef0`
- `0x180037adc`
- `0x180037c4c`
- `0x1800bb010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18002b9c5`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18002b9c5`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18002b9fa`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18002b9fa`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<int>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
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
  Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<enum EnterpriseDeviceManagement::Enrollment::MDMProgressMode>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(
    a1,
    1);
  if ( *(int *)(a1 + 136) > 0 && _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 16), v3) + 1 == v3 )
  {
    v9 = a1;
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(&v9);
    pUnk = 0;
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const AsyncActionAttachAsync,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(a1);
    if ( (int)Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<int>>(&v9, &pUnk) >= 0 )
    {
      v12 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v12, *(_DWORD *)(a1 + 56), -2);
      v13 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
      if ( (int)Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<int>>::CopyLocal(
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
0x18002b8e0  push    rbp
0x18002b8e2  push    rbx
0x18002b8e3  push    rdi
0x18002b8e4  mov     rbp, rsp
0x18002b8e7  sub     rsp, 50h
0x18002b8eb  mov     rbx, rcx
0x18002b8ee  xor     edi, edi
0x18002b8f0  lea     edx, [rdi+1]
0x18002b8f3  call    ?TransitionToState@?$AsyncBase@U?$IAsyncOperationCompletedHandler@W4MDMProgressMode@Enrollment@EnterpriseDeviceManagement@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<EnterpriseDeviceManagement::Enrollment::MDMProgressMode>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x18002b8f8  cmp     [rbx+88h], edi
0x18002b8fe  jle     loc_18002BA7D
0x18002b904  mov     eax, edx
0x18002b906  lock xadd [rbx+10h], eax
0x18002b90b  inc     eax
0x18002b90d  cmp     eax, edx
0x18002b90f  jnz     loc_18002BA7D
0x18002b915  mov     [rbp+var_20], rbx
0x18002b919  lea     rcx, [rbp+var_20]
0x18002b91d  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x18002b922  nop
0x18002b923  mov     [rbp+pUnk], rdi
0x18002b927  mov     rcx, rbx
0x18002b92a  call    ?TraceOperationComplete@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?AsyncActionAttachAsync@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const AsyncActionAttachAsync,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x18002b92f  lea     rdx, [rbp+pUnk]
0x18002b933  lea     rcx, [rbp+var_20]
0x18002b937  call    ??$As@U?$IAsyncOperation@H@Foundation@Windows@@@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IAsyncOperation@H@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<int>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<int>>>)
0x18002b93c  test    eax, eax
0x18002b93e  js      loc_18002BA6A
0x18002b944  mov     [rbp+arg_0], 0FFFFFFFEh
0x18002b94b  mov     ecx, [rbx+38h]
0x18002b94e  mov     eax, [rbp+arg_0]
0x18002b951  lock cmpxchg [rbp+arg_0], ecx
0x18002b956  mov     [rbp+arg_8], rdi
0x18002b95a  lea     rcx, [rbp+arg_8]
0x18002b95e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b963  lea     rcx, [rbx+78h]
0x18002b967  lea     r8, [rbp+arg_8]
0x18002b96b  call    ?CopyLocal@?$GitPtrSupportsAgile@U?$IAsyncOperationCompletedHandler@H@Foundation@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<int>>::CopyLocal(_GUID const &,void * *)
0x18002b970  test    eax, eax
0x18002b972  js      loc_18002BA60
0x18002b978  mov     rcx, rbx
0x18002b97b  call    ?TraceCompletionNotificationStart@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?RebuildSchedulesAndSyncWithServerAsyncName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const RebuildSchedulesAndSyncWithServerAsyncName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(void)
0x18002b980  mov     [rbp+arg_10], rdi
0x18002b984  lea     rcx, [rbp+arg_10]
0x18002b988  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b98d  lea     r8, [rbp+arg_10]; struct IRpcOptions **
0x18002b991  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x18002b995  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x18002b99a  mov     [rbp+ppstm], rdi
0x18002b99e  mov     [rbp+var_10], edi
0x18002b9a1  cmp     [rbp+arg_10], rdi
0x18002b9a5  jz      short loc_18002BA0B
0x18002b9a7  cmp     [rbp+arg_8], rdi
0x18002b9ab  jz      short loc_18002BA0B
0x18002b9ad  mov     rdi, [rbp+pUnk]
0x18002b9b1  lea     rcx, [rbp+ppstm]
0x18002b9b5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b9ba  lea     r8, [rbp+ppstm]; ppstm
0x18002b9be  mov     edx, 1; fDeleteOnRelease
0x18002b9c3  xor     ecx, ecx; hGlobal
0x18002b9c5  call    cs:__imp_CreateStreamOnHGlobal
0x18002b9cc  nop     dword ptr [rax+rax+00h]
0x18002b9d1  mov     [rbp+var_10], eax
0x18002b9d4  test    eax, eax
0x18002b9d6  js      short loc_18002BA12
0x18002b9d8  mov     [rsp+50h+mshlflags], 1; mshlflags
0x18002b9e0  mov     [rsp+50h+pvDestContext], 0; pvDestContext
0x18002b9e9  xor     r9d, r9d; dwDestContext
0x18002b9ec  mov     r8, rdi; pUnk
0x18002b9ef  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18002b9f6  mov     rcx, [rbp+ppstm]; pStm
0x18002b9fa  call    cs:__imp_CoMarshalInterface
0x18002ba01  nop     dword ptr [rax+rax+00h]
0x18002ba06  mov     [rbp+var_10], eax
0x18002ba09  jmp     short loc_18002BA12
0x18002ba0b  mov     [rbp+var_10], 80004002h
0x18002ba12  mov     rcx, [rbp+arg_8]
0x18002ba16  mov     rax, [rcx]
0x18002ba19  mov     r8d, [rbp+arg_0]
0x18002ba1d  mov     rdx, [rbp+pUnk]
0x18002ba21  mov     rax, [rax+18h]
0x18002ba25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba2a  mov     r8, [rbx+80h]
0x18002ba31  mov     rdx, [rbp+arg_8]
0x18002ba35  mov     ecx, eax
0x18002ba37  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x18002ba3c  mov     edi, eax
0x18002ba3e  mov     rcx, rbx
0x18002ba41  call    ?UnlockCompleteDelegate@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVReflectedEnrollmentResult@Enrollment@EnterpriseDeviceManagement@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<EnterpriseDeviceManagement::Enrollment::ReflectedEnrollmentResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(void)
0x18002ba46  call    ?TraceCompletionNotificationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(void)
0x18002ba4b  nop
0x18002ba4c  lea     rcx, [rbp+ppstm]
0x18002ba50  call    ??1?$AutoStubBias@U?$IAsyncOperation@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@23@@@QEAA@XZ; AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>>(void)
0x18002ba55  nop
0x18002ba56  lea     rcx, [rbp+arg_10]
0x18002ba5a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002ba5f  nop
0x18002ba60  lea     rcx, [rbp+arg_8]
0x18002ba64  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002ba69  nop
0x18002ba6a  lea     rcx, [rbp+pUnk]
0x18002ba6e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002ba73  nop
0x18002ba74  lea     rcx, [rbp+var_20]
0x18002ba78  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002ba7d  mov     eax, edi
0x18002ba7f  add     rsp, 50h
0x18002ba83  pop     rdi
0x18002ba84  pop     rbx
0x18002ba85  pop     rbp
0x18002ba86  retn
```
