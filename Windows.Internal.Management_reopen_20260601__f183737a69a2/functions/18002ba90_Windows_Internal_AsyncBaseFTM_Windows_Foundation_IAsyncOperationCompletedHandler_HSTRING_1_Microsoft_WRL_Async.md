# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x18002ba90`
- end: `0x18002bc38`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `424`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002c7e0`

## callees

- `0x180009be4`
- `0x180017944`
- `0x180017fc0`
- `0x1800180fc`
- `0x18001823c`
- `0x180019770`
- `0x180029dfc`
- `0x18002ba90`
- `0x180036e18`
- `0x180036e4c`
- `0x180036ef0`
- `0x180037adc`
- `0x180037c4c`
- `0x1800bb010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18002bb75`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18002bb75`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18002bbaa`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18002bbaa`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
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
    if ( (int)Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<HSTRING__ *>>(&v9, &pUnk) >= 0 )
    {
      v12 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v12, *(_DWORD *)(a1 + 56), -2);
      v13 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
      if ( (int)Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>>::CopyLocal(
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
0x18002ba90  push    rbp
0x18002ba92  push    rbx
0x18002ba93  push    rdi
0x18002ba94  mov     rbp, rsp
0x18002ba97  sub     rsp, 50h
0x18002ba9b  mov     rbx, rcx
0x18002ba9e  xor     edi, edi
0x18002baa0  lea     edx, [rdi+1]
0x18002baa3  call    ?TransitionToState@?$AsyncBase@U?$IAsyncOperationCompletedHandler@W4MDMProgressMode@Enrollment@EnterpriseDeviceManagement@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<EnterpriseDeviceManagement::Enrollment::MDMProgressMode>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x18002baa8  cmp     [rbx+88h], edi
0x18002baae  jle     loc_18002BC2D
0x18002bab4  mov     eax, edx
0x18002bab6  lock xadd [rbx+10h], eax
0x18002babb  inc     eax
0x18002babd  cmp     eax, edx
0x18002babf  jnz     loc_18002BC2D
0x18002bac5  mov     [rbp+var_20], rbx
0x18002bac9  lea     rcx, [rbp+var_20]
0x18002bacd  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x18002bad2  nop
0x18002bad3  mov     [rbp+pUnk], rdi
0x18002bad7  mov     rcx, rbx
0x18002bada  call    ?TraceOperationComplete@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?AsyncActionAttachAsync@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const AsyncActionAttachAsync,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x18002badf  lea     rdx, [rbp+pUnk]
0x18002bae3  lea     rcx, [rbp+var_20]
0x18002bae7  call    ??$As@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<HSTRING__ *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<HSTRING__ *>>>)
0x18002baec  test    eax, eax
0x18002baee  js      loc_18002BC1A
0x18002baf4  mov     [rbp+arg_0], 0FFFFFFFEh
0x18002bafb  mov     ecx, [rbx+38h]
0x18002bafe  mov     eax, [rbp+arg_0]
0x18002bb01  lock cmpxchg [rbp+arg_0], ecx
0x18002bb06  mov     [rbp+arg_8], rdi
0x18002bb0a  lea     rcx, [rbp+arg_8]
0x18002bb0e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002bb13  lea     rcx, [rbx+78h]
0x18002bb17  lea     r8, [rbp+arg_8]
0x18002bb1b  call    ?CopyLocal@?$GitPtrSupportsAgile@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>>::CopyLocal(_GUID const &,void * *)
0x18002bb20  test    eax, eax
0x18002bb22  js      loc_18002BC10
0x18002bb28  mov     rcx, rbx
0x18002bb2b  call    ?TraceCompletionNotificationStart@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?RebuildSchedulesAndSyncWithServerAsyncName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const RebuildSchedulesAndSyncWithServerAsyncName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(void)
0x18002bb30  mov     [rbp+arg_10], rdi
0x18002bb34  lea     rcx, [rbp+arg_10]
0x18002bb38  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002bb3d  lea     r8, [rbp+arg_10]; struct IRpcOptions **
0x18002bb41  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x18002bb45  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x18002bb4a  mov     [rbp+ppstm], rdi
0x18002bb4e  mov     [rbp+var_10], edi
0x18002bb51  cmp     [rbp+arg_10], rdi
0x18002bb55  jz      short loc_18002BBBB
0x18002bb57  cmp     [rbp+arg_8], rdi
0x18002bb5b  jz      short loc_18002BBBB
0x18002bb5d  mov     rdi, [rbp+pUnk]
0x18002bb61  lea     rcx, [rbp+ppstm]
0x18002bb65  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002bb6a  lea     r8, [rbp+ppstm]; ppstm
0x18002bb6e  mov     edx, 1; fDeleteOnRelease
0x18002bb73  xor     ecx, ecx; hGlobal
0x18002bb75  call    cs:__imp_CreateStreamOnHGlobal
0x18002bb7c  nop     dword ptr [rax+rax+00h]
0x18002bb81  mov     [rbp+var_10], eax
0x18002bb84  test    eax, eax
0x18002bb86  js      short loc_18002BBC2
0x18002bb88  mov     [rsp+50h+mshlflags], 1; mshlflags
0x18002bb90  mov     [rsp+50h+pvDestContext], 0; pvDestContext
0x18002bb99  xor     r9d, r9d; dwDestContext
0x18002bb9c  mov     r8, rdi; pUnk
0x18002bb9f  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18002bba6  mov     rcx, [rbp+ppstm]; pStm
0x18002bbaa  call    cs:__imp_CoMarshalInterface
0x18002bbb1  nop     dword ptr [rax+rax+00h]
0x18002bbb6  mov     [rbp+var_10], eax
0x18002bbb9  jmp     short loc_18002BBC2
0x18002bbbb  mov     [rbp+var_10], 80004002h
0x18002bbc2  mov     rcx, [rbp+arg_8]
0x18002bbc6  mov     rax, [rcx]
0x18002bbc9  mov     r8d, [rbp+arg_0]
0x18002bbcd  mov     rdx, [rbp+pUnk]
0x18002bbd1  mov     rax, [rax+18h]
0x18002bbd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bbda  mov     r8, [rbx+80h]
0x18002bbe1  mov     rdx, [rbp+arg_8]
0x18002bbe5  mov     ecx, eax
0x18002bbe7  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x18002bbec  mov     edi, eax
0x18002bbee  mov     rcx, rbx
0x18002bbf1  call    ?UnlockCompleteDelegate@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVReflectedEnrollmentResult@Enrollment@EnterpriseDeviceManagement@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<EnterpriseDeviceManagement::Enrollment::ReflectedEnrollmentResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(void)
0x18002bbf6  call    ?TraceCompletionNotificationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(void)
0x18002bbfb  nop
0x18002bbfc  lea     rcx, [rbp+ppstm]
0x18002bc00  call    ??1?$AutoStubBias@U?$IAsyncOperation@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@23@@@QEAA@XZ; AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>>(void)
0x18002bc05  nop
0x18002bc06  lea     rcx, [rbp+arg_10]
0x18002bc0a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002bc0f  nop
0x18002bc10  lea     rcx, [rbp+arg_8]
0x18002bc14  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002bc19  nop
0x18002bc1a  lea     rcx, [rbp+pUnk]
0x18002bc1e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002bc23  nop
0x18002bc24  lea     rcx, [rbp+var_20]
0x18002bc28  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002bc2d  mov     eax, edi
0x18002bc2f  add     rsp, 50h
0x18002bc33  pop     rdi
0x18002bc34  pop     rbx
0x18002bc35  pop     rbp
0x18002bc36  retn
```
