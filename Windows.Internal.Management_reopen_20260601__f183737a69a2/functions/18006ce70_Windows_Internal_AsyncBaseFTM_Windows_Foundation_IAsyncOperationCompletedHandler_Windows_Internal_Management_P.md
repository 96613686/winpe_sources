# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::ConfigurationResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x18006ce70`
- end: `0x18006d018`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVConfigurationResult@Provision@Management@Internal@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `424`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006d020`

## callees

- `0x180009be4`
- `0x180017944`
- `0x180017fc0`
- `0x1800180fc`
- `0x18001823c`
- `0x180036e18`
- `0x180036e4c`
- `0x180036ef0`
- `0x180037adc`
- `0x180037c4c`
- `0x18006b80c`
- `0x18006ccf8`
- `0x18006ce70`
- `0x1800bb010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18006cf55`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18006cf55`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18006cf8a`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18006cf8a`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::ConfigurationResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
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
    if ( (int)Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Provision::ConfigurationResult *>>(
                &v9,
                &pUnk) >= 0 )
    {
      v12 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v12, *(_DWORD *)(a1 + 56), -2);
      v13 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
      if ( (int)Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::ConfigurationResult *>>::CopyLocal(
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
0x18006ce70  push    rbp
0x18006ce72  push    rbx
0x18006ce73  push    rdi
0x18006ce74  mov     rbp, rsp
0x18006ce77  sub     rsp, 50h
0x18006ce7b  mov     rbx, rcx
0x18006ce7e  xor     edi, edi
0x18006ce80  lea     edx, [rdi+1]
0x18006ce83  call    ?TransitionToState@?$AsyncBase@U?$IAsyncOperationCompletedHandler@W4MDMProgressMode@Enrollment@EnterpriseDeviceManagement@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<EnterpriseDeviceManagement::Enrollment::MDMProgressMode>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x18006ce88  cmp     [rbx+88h], edi
0x18006ce8e  jle     loc_18006D00D
0x18006ce94  mov     eax, edx
0x18006ce96  lock xadd [rbx+10h], eax
0x18006ce9b  inc     eax
0x18006ce9d  cmp     eax, edx
0x18006ce9f  jnz     loc_18006D00D
0x18006cea5  mov     [rbp+var_20], rbx
0x18006cea9  lea     rcx, [rbp+var_20]
0x18006cead  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x18006ceb2  nop
0x18006ceb3  mov     [rbp+pUnk], rdi
0x18006ceb7  mov     rcx, rbx
0x18006ceba  call    ?TraceOperationComplete@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?AsyncActionAttachAsync@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const AsyncActionAttachAsync,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x18006cebf  lea     rdx, [rbp+pUnk]
0x18006cec3  lea     rcx, [rbp+var_20]
0x18006cec7  call    ??$As@U?$IAsyncOperation@PEAVConfigurationResult@Provision@Management@Internal@Windows@@@Foundation@Windows@@@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IAsyncOperation@PEAVConfigurationResult@Provision@Management@Internal@Windows@@@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Provision::ConfigurationResult *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Provision::ConfigurationResult *>>>)
0x18006cecc  test    eax, eax
0x18006cece  js      loc_18006CFFA
0x18006ced4  mov     [rbp+arg_0], 0FFFFFFFEh
0x18006cedb  mov     ecx, [rbx+38h]
0x18006cede  mov     eax, [rbp+arg_0]
0x18006cee1  lock cmpxchg [rbp+arg_0], ecx
0x18006cee6  mov     [rbp+arg_8], rdi
0x18006ceea  lea     rcx, [rbp+arg_8]
0x18006ceee  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006cef3  lea     rcx, [rbx+78h]
0x18006cef7  lea     r8, [rbp+arg_8]
0x18006cefb  call    ?CopyLocal@?$GitPtrSupportsAgile@U?$IAsyncOperationCompletedHandler@PEAVConfigurationResult@Provision@Management@Internal@Windows@@@Foundation@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Provision::ConfigurationResult *>>::CopyLocal(_GUID const &,void * *)
0x18006cf00  test    eax, eax
0x18006cf02  js      loc_18006CFF0
0x18006cf08  mov     rcx, rbx
0x18006cf0b  call    ?TraceCompletionNotificationStart@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?RebuildSchedulesAndSyncWithServerAsyncName@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const RebuildSchedulesAndSyncWithServerAsyncName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(void)
0x18006cf10  mov     [rbp+arg_10], rdi
0x18006cf14  lea     rcx, [rbp+arg_10]
0x18006cf18  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006cf1d  lea     r8, [rbp+arg_10]; struct IRpcOptions **
0x18006cf21  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x18006cf25  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x18006cf2a  mov     [rbp+ppstm], rdi
0x18006cf2e  mov     [rbp+var_10], edi
0x18006cf31  cmp     [rbp+arg_10], rdi
0x18006cf35  jz      short loc_18006CF9B
0x18006cf37  cmp     [rbp+arg_8], rdi
0x18006cf3b  jz      short loc_18006CF9B
0x18006cf3d  mov     rdi, [rbp+pUnk]
0x18006cf41  lea     rcx, [rbp+ppstm]
0x18006cf45  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006cf4a  lea     r8, [rbp+ppstm]; ppstm
0x18006cf4e  mov     edx, 1; fDeleteOnRelease
0x18006cf53  xor     ecx, ecx; hGlobal
0x18006cf55  call    cs:__imp_CreateStreamOnHGlobal
0x18006cf5c  nop     dword ptr [rax+rax+00h]
0x18006cf61  mov     [rbp+var_10], eax
0x18006cf64  test    eax, eax
0x18006cf66  js      short loc_18006CFA2
0x18006cf68  mov     [rsp+50h+mshlflags], 1; mshlflags
0x18006cf70  mov     [rsp+50h+pvDestContext], 0; pvDestContext
0x18006cf79  xor     r9d, r9d; dwDestContext
0x18006cf7c  mov     r8, rdi; pUnk
0x18006cf7f  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18006cf86  mov     rcx, [rbp+ppstm]; pStm
0x18006cf8a  call    cs:__imp_CoMarshalInterface
0x18006cf91  nop     dword ptr [rax+rax+00h]
0x18006cf96  mov     [rbp+var_10], eax
0x18006cf99  jmp     short loc_18006CFA2
0x18006cf9b  mov     [rbp+var_10], 80004002h
0x18006cfa2  mov     rcx, [rbp+arg_8]
0x18006cfa6  mov     rax, [rcx]
0x18006cfa9  mov     r8d, [rbp+arg_0]
0x18006cfad  mov     rdx, [rbp+pUnk]
0x18006cfb1  mov     rax, [rax+18h]
0x18006cfb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cfba  mov     r8, [rbx+80h]
0x18006cfc1  mov     rdx, [rbp+arg_8]
0x18006cfc5  mov     ecx, eax
0x18006cfc7  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x18006cfcc  mov     edi, eax
0x18006cfce  mov     rcx, rbx
0x18006cfd1  call    ?UnlockCompleteDelegate@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVReflectedEnrollmentResult@Enrollment@EnterpriseDeviceManagement@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<EnterpriseDeviceManagement::Enrollment::ReflectedEnrollmentResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(void)
0x18006cfd6  call    ?TraceCompletionNotificationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(void)
0x18006cfdb  nop
0x18006cfdc  lea     rcx, [rbp+ppstm]
0x18006cfe0  call    ??1?$AutoStubBias@U?$IAsyncOperation@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@23@@@QEAA@XZ; AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>>(void)
0x18006cfe5  nop
0x18006cfe6  lea     rcx, [rbp+arg_10]
0x18006cfea  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006cfef  nop
0x18006cff0  lea     rcx, [rbp+arg_8]
0x18006cff4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006cff9  nop
0x18006cffa  lea     rcx, [rbp+pUnk]
0x18006cffe  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006d003  nop
0x18006d004  lea     rcx, [rbp+var_20]
0x18006d008  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006d00d  mov     eax, edi
0x18006d00f  add     rsp, 50h
0x18006d013  pop     rdi
0x18006d014  pop     rbx
0x18006d015  pop     rbp
0x18006d016  retn
```
