# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<bool> *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x18002c7d0`
- end: `0x18002c96b`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@_N@Collections@Foundation@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `411`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002c9b0`

## callees

- `0x180002a3c`
- `0x1800034d0`
- `0x1800035a0`
- `0x180005a30`
- `0x180005f20`
- `0x180006388`
- `0x180006d30`
- `0x180007858`
- `0x18000793c`
- `0x18000815c`
- `0x180009a9c`
- `0x180027adc`
- `0x18002c7d0`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18002c8e4`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18002c8e4`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18002c8b5`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18002c8b5`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<bool> *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
        __int64 a1)
{
  unsigned int v2; // edi
  unsigned int v3; // edx
  __int64 v4; // rcx
  __int64 v5; // rdx
  bool v6; // dl
  IUnknown *v7; // rdi
  unsigned int v8; // eax
  __int64 (__fastcall ***v10)(_QWORD, GUID *, __int64); // [rsp+30h] [rbp-20h] BYREF
  LPSTREAM ppstm; // [rsp+38h] [rbp-18h] BYREF
  HRESULT v12; // [rsp+40h] [rbp-10h]
  unsigned int v13; // [rsp+70h] [rbp+20h] BYREF
  struct IUnknown *v14; // [rsp+78h] [rbp+28h] BYREF
  struct IRpcOptions *v15; // [rsp+80h] [rbp+30h] BYREF
  LPUNKNOWN pUnk; // [rsp+88h] [rbp+38h] BYREF

  v2 = 0;
  Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<bool> *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(
    a1,
    1);
  if ( *(int *)(v4 + 136) > 0 && _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 16), v3) + 1 == v3 )
  {
    v10 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))v4;
    Microsoft::WRL::ComPtr<IAsyncInfo>::InternalAddRef(&v10);
    pUnk = 0;
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const CloudExperienceHostBroker::LocalNgc::CreateLocalPinAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(a1);
    if ( (int)Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<bool> *>>(
                &v10,
                (__int64)&pUnk) >= 0 )
    {
      v13 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v13, *(_DWORD *)(a1 + 56), -2);
      v14 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
      if ( (int)Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<bool> *>>::CopyLocal(
                  a1 + 120,
                  v5,
                  &v14) >= 0 )
      {
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<bool> *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(a1);
        v15 = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
        RpcOptionsHelper::GetRpcOptions(v14, v6, &v15);
        ppstm = 0;
        v12 = 0;
        if ( v15 && v14 )
        {
          v7 = pUnk;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppstm);
          v12 = CreateStreamOnHGlobal(0, 1, &ppstm);
          if ( v12 >= 0 )
            v12 = CoMarshalInterface(ppstm, &GUID_00000000_0000_0000_c000_000000000046, v7, 0, 0, 1u);
        }
        else
        {
          v12 = -2147467262;
        }
        v8 = ((__int64 (__fastcall *)(struct IUnknown *, LPUNKNOWN, _QWORD))v14->lpVtbl[1].QueryInterface)(
               v14,
               pUnk,
               v13);
        v2 = Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireCompletionErrorPropagationPolicyFilter(
               v8,
               v14,
               *(_QWORD *)(a1 + 128));
        Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<bool> *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(a1);
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const CloudExperienceHostBroker::LocalNgc::CreateLocalPinAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete();
        AutoStubBias<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>(&ppstm);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pUnk);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
  }
  return v2;
}

```

## disassembly

```asm
0x18002c7d0  push    rbp
0x18002c7d2  push    rbx
0x18002c7d3  push    rdi
0x18002c7d4  mov     rbp, rsp
0x18002c7d7  sub     rsp, 50h
0x18002c7db  mov     rbx, rcx
0x18002c7de  xor     edi, edi
0x18002c7e0  lea     edx, [rdi+1]
0x18002c7e3  call    ?TransitionToState@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@_N@Collections@Foundation@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<bool> *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x18002c7e8  cmp     [rcx+88h], edi
0x18002c7ee  jle     loc_18002C961
0x18002c7f4  mov     eax, edx
0x18002c7f6  lock xadd [rcx+10h], eax
0x18002c7fb  inc     eax
0x18002c7fd  cmp     eax, edx
0x18002c7ff  jnz     loc_18002C961
0x18002c805  mov     [rbp+var_20], rcx
0x18002c809  lea     rcx, [rbp+var_20]
0x18002c80d  call    ?InternalAddRef@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IAsyncInfo>::InternalAddRef(void)
0x18002c812  nop
0x18002c813  mov     [rbp+pUnk], rdi
0x18002c817  mov     rcx, rbx
0x18002c81a  call    ?TraceOperationComplete@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?CreateLocalPinAsyncActionName@LocalNgc@CloudExperienceHostBroker@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const CloudExperienceHostBroker::LocalNgc::CreateLocalPinAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x18002c81f  lea     rdx, [rbp+pUnk]
0x18002c823  lea     rcx, [rbp+var_20]
0x18002c827  call    ??$As@U?$IAsyncOperation@PEAU?$IVectorView@_N@Collections@Foundation@Windows@@@Foundation@Windows@@@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IAsyncOperation@PEAU?$IVectorView@_N@Collections@Foundation@Windows@@@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<bool> *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<bool> *>>>)
0x18002c82c  test    eax, eax
0x18002c82e  js      loc_18002C94E
0x18002c834  mov     [rbp+arg_0], 0FFFFFFFEh
0x18002c83b  mov     ecx, [rbx+38h]
0x18002c83e  mov     eax, [rbp+arg_0]
0x18002c841  lock cmpxchg [rbp+arg_0], ecx
0x18002c846  mov     [rbp+arg_8], rdi
0x18002c84a  lea     rcx, [rbp+arg_8]
0x18002c84e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002c853  lea     rcx, [rbx+78h]
0x18002c857  lea     r8, [rbp+arg_8]
0x18002c85b  call    ?CopyLocal@?$GitPtrSupportsAgile@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@_N@Collections@Foundation@Windows@@@Foundation@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<bool> *>>::CopyLocal(_GUID const &,void * *)
0x18002c860  test    eax, eax
0x18002c862  js      loc_18002C944
0x18002c868  mov     rcx, rbx
0x18002c86b  call    ?TraceCompletionNotificationStart@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@_N@Collections@Foundation@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<bool> *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(void)
0x18002c870  mov     [rbp+arg_10], rdi
0x18002c874  lea     rcx, [rbp+arg_10]
0x18002c878  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002c87d  lea     r8, [rbp+arg_10]; struct IRpcOptions **
0x18002c881  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x18002c885  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x18002c88a  mov     [rbp+ppstm], rdi
0x18002c88e  mov     [rbp+var_10], edi
0x18002c891  cmp     [rbp+arg_10], rdi
0x18002c895  jz      short loc_18002C8EF
0x18002c897  cmp     [rbp+arg_8], rdi
0x18002c89b  jz      short loc_18002C8EF
0x18002c89d  mov     rdi, [rbp+pUnk]
0x18002c8a1  lea     rcx, [rbp+ppstm]
0x18002c8a5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002c8aa  lea     r8, [rbp+ppstm]; ppstm
0x18002c8ae  mov     edx, 1; fDeleteOnRelease
0x18002c8b3  xor     ecx, ecx; hGlobal
0x18002c8b5  call    cs:__imp_CreateStreamOnHGlobal
0x18002c8bb  mov     [rbp+var_10], eax
0x18002c8be  test    eax, eax
0x18002c8c0  js      short loc_18002C8F6
0x18002c8c2  mov     [rsp+50h+mshlflags], 1; mshlflags
0x18002c8ca  mov     [rsp+50h+pvDestContext], 0; pvDestContext
0x18002c8d3  xor     r9d, r9d; dwDestContext
0x18002c8d6  mov     r8, rdi; pUnk
0x18002c8d9  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18002c8e0  mov     rcx, [rbp+ppstm]; pStm
0x18002c8e4  call    cs:__imp_CoMarshalInterface
0x18002c8ea  mov     [rbp+var_10], eax
0x18002c8ed  jmp     short loc_18002C8F6
0x18002c8ef  mov     [rbp+var_10], 80004002h
0x18002c8f6  mov     rcx, [rbp+arg_8]
0x18002c8fa  mov     rax, [rcx]
0x18002c8fd  mov     r8d, [rbp+arg_0]
0x18002c901  mov     rdx, [rbp+pUnk]
0x18002c905  mov     rax, [rax+18h]
0x18002c909  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c90e  mov     r8, [rbx+80h]
0x18002c915  mov     rdx, [rbp+arg_8]
0x18002c919  mov     ecx, eax
0x18002c91b  call    ?FireCompletionErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireCompletionErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x18002c920  mov     edi, eax
0x18002c922  mov     rcx, rbx
0x18002c925  call    ?UnlockCompleteDelegate@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@_N@Collections@Foundation@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<bool> *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(void)
0x18002c92a  call    ?TraceCompletionNotificationComplete@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?CreateLocalPinAsyncActionName@LocalNgc@CloudExperienceHostBroker@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const CloudExperienceHostBroker::LocalNgc::CreateLocalPinAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(void)
0x18002c92f  nop
0x18002c930  lea     rcx, [rbp+ppstm]
0x18002c934  call    ??1?$AutoStubBias@U?$IAsyncOperation@_N@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@_N@23@@@QEAA@XZ; AutoStubBias<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>(void)
0x18002c939  nop
0x18002c93a  lea     rcx, [rbp+arg_10]
0x18002c93e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002c943  nop
0x18002c944  lea     rcx, [rbp+arg_8]
0x18002c948  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002c94d  nop
0x18002c94e  lea     rcx, [rbp+pUnk]
0x18002c952  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002c957  nop
0x18002c958  lea     rcx, [rbp+var_20]
0x18002c95c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002c961  mov     eax, edi
0x18002c963  add     rsp, 50h
0x18002c967  pop     rdi
0x18002c968  pop     rbx
0x18002c969  pop     rbp
0x18002c96a  retn
```
