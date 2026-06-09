# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<EnterpriseDeviceManagement::Enrollment::CustomAllDonePageResults *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x1800586b0`
- end: `0x18005884b`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVCustomAllDonePageResults@Enrollment@EnterpriseDeviceManagement@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `411`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180058bc0`

## callees

- `0x18000992c`
- `0x180017154`
- `0x180017838`
- `0x180018eb8`
- `0x180018ff0`
- `0x180037b70`
- `0x180037ba0`
- `0x180037c44`
- `0x180038830`
- `0x18003899c`
- `0x180040f80`
- `0x18004c08c`
- `0x1800586b0`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x1800587c4`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x1800587c4`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180058795`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180058795`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<EnterpriseDeviceManagement::Enrollment::CustomAllDonePageResults *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
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
    if ( (int)Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<EnterpriseDeviceManagement::Enrollment::CustomAllDonePageResults *>>(
                &v9,
                (__int64)&pUnk) >= 0 )
    {
      v12 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v12, *(_DWORD *)(a1 + 56), -2);
      v13 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
      if ( (int)Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<EnterpriseDeviceManagement::Enrollment::CustomAllDonePageResults *>>::CopyLocal(
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
0x1800586b0  push    rbp
0x1800586b2  push    rbx
0x1800586b3  push    rdi
0x1800586b4  mov     rbp, rsp
0x1800586b7  sub     rsp, 50h
0x1800586bb  mov     rbx, rcx
0x1800586be  xor     edi, edi
0x1800586c0  lea     edx, [rdi+1]
0x1800586c3  call    ?TransitionToState@?$AsyncBase@U?$IAsyncOperationCompletedHandler@W4MDMProgressMode@Enrollment@EnterpriseDeviceManagement@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<EnterpriseDeviceManagement::Enrollment::MDMProgressMode>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x1800586c8  cmp     [rbx+88h], edi
0x1800586ce  jle     loc_180058841
0x1800586d4  mov     eax, edx
0x1800586d6  lock xadd [rbx+10h], eax
0x1800586db  inc     eax
0x1800586dd  cmp     eax, edx
0x1800586df  jnz     loc_180058841
0x1800586e5  mov     [rbp+var_20], rbx
0x1800586e9  lea     rcx, [rbp+var_20]
0x1800586ed  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x1800586f2  nop
0x1800586f3  mov     [rbp+pUnk], rdi
0x1800586f7  mov     rcx, rbx
0x1800586fa  call    ?TraceOperationComplete@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?AsyncActionAttachAsync@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const AsyncActionAttachAsync,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x1800586ff  lea     rdx, [rbp+pUnk]
0x180058703  lea     rcx, [rbp+var_20]
0x180058707  call    ??$As@U?$IAsyncOperation@PEAVCustomAllDonePageResults@Enrollment@EnterpriseDeviceManagement@@@Foundation@Windows@@@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IAsyncOperation@PEAVCustomAllDonePageResults@Enrollment@EnterpriseDeviceManagement@@@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<EnterpriseDeviceManagement::Enrollment::CustomAllDonePageResults *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<EnterpriseDeviceManagement::Enrollment::CustomAllDonePageResults *>>>)
0x18005870c  test    eax, eax
0x18005870e  js      loc_18005882E
0x180058714  mov     [rbp+arg_0], 0FFFFFFFEh
0x18005871b  mov     ecx, [rbx+38h]
0x18005871e  mov     eax, [rbp+arg_0]
0x180058721  lock cmpxchg [rbp+arg_0], ecx
0x180058726  mov     [rbp+arg_8], rdi
0x18005872a  lea     rcx, [rbp+arg_8]
0x18005872e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180058733  lea     rcx, [rbx+78h]
0x180058737  lea     r8, [rbp+arg_8]
0x18005873b  call    ?CopyLocal@?$GitPtrSupportsAgile@U?$IAsyncOperationCompletedHandler@PEAVCustomAllDonePageResults@Enrollment@EnterpriseDeviceManagement@@@Foundation@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<EnterpriseDeviceManagement::Enrollment::CustomAllDonePageResults *>>::CopyLocal(_GUID const &,void * *)
0x180058740  test    eax, eax
0x180058742  js      loc_180058824
0x180058748  mov     rcx, rbx
0x18005874b  call    ?TraceCompletionNotificationStart@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?RebuildSchedulesAndSyncWithServerAsyncName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const RebuildSchedulesAndSyncWithServerAsyncName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(void)
0x180058750  mov     [rbp+arg_10], rdi
0x180058754  lea     rcx, [rbp+arg_10]
0x180058758  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005875d  lea     r8, [rbp+arg_10]; struct IRpcOptions **
0x180058761  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x180058765  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x18005876a  mov     [rbp+ppstm], rdi
0x18005876e  mov     [rbp+var_10], edi
0x180058771  cmp     [rbp+arg_10], rdi
0x180058775  jz      short loc_1800587CF
0x180058777  cmp     [rbp+arg_8], rdi
0x18005877b  jz      short loc_1800587CF
0x18005877d  mov     rdi, [rbp+pUnk]
0x180058781  lea     rcx, [rbp+ppstm]
0x180058785  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005878a  lea     r8, [rbp+ppstm]; ppstm
0x18005878e  mov     edx, 1; fDeleteOnRelease
0x180058793  xor     ecx, ecx; hGlobal
0x180058795  call    cs:__imp_CreateStreamOnHGlobal
0x18005879b  mov     [rbp+var_10], eax
0x18005879e  test    eax, eax
0x1800587a0  js      short loc_1800587D6
0x1800587a2  mov     [rsp+50h+mshlflags], 1; mshlflags
0x1800587aa  mov     [rsp+50h+pvDestContext], 0; pvDestContext
0x1800587b3  xor     r9d, r9d; dwDestContext
0x1800587b6  mov     r8, rdi; pUnk
0x1800587b9  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x1800587c0  mov     rcx, [rbp+ppstm]; pStm
0x1800587c4  call    cs:__imp_CoMarshalInterface
0x1800587ca  mov     [rbp+var_10], eax
0x1800587cd  jmp     short loc_1800587D6
0x1800587cf  mov     [rbp+var_10], 80004002h
0x1800587d6  mov     rcx, [rbp+arg_8]
0x1800587da  mov     rax, [rcx]
0x1800587dd  mov     r8d, [rbp+arg_0]
0x1800587e1  mov     rdx, [rbp+pUnk]
0x1800587e5  mov     rax, [rax+18h]
0x1800587e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800587ee  mov     r8, [rbx+80h]
0x1800587f5  mov     rdx, [rbp+arg_8]
0x1800587f9  mov     ecx, eax
0x1800587fb  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x180058800  mov     edi, eax
0x180058802  mov     rcx, rbx
0x180058805  call    ?UnlockCompleteDelegate@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVReflectedEnrollmentResult@Enrollment@EnterpriseDeviceManagement@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<EnterpriseDeviceManagement::Enrollment::ReflectedEnrollmentResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(void)
0x18005880a  call    ?TraceCompletionNotificationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(void)
0x18005880f  nop
0x180058810  lea     rcx, [rbp+ppstm]
0x180058814  call    ??1?$AutoStubBias@U?$IAsyncOperation@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@23@@@QEAA@XZ; AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>>(void)
0x180058819  nop
0x18005881a  lea     rcx, [rbp+arg_10]
0x18005881e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180058823  nop
0x180058824  lea     rcx, [rbp+arg_8]
0x180058828  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005882d  nop
0x18005882e  lea     rcx, [rbp+pUnk]
0x180058832  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180058837  nop
0x180058838  lea     rcx, [rbp+var_20]
0x18005883c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180058841  mov     eax, edi
0x180058843  add     rsp, 50h
0x180058847  pop     rdi
0x180058848  pop     rbx
0x180058849  pop     rbp
0x18005884a  retn
```
