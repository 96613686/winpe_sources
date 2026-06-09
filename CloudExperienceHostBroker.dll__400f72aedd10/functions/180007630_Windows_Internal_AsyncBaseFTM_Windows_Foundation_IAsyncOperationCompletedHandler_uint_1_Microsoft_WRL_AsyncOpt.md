# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<uint>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x180007630`
- end: `0x18000784f`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@I@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `543`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002c980`

## callees

- `0x180002a3c`
- `0x1800034d0`
- `0x1800035a0`
- `0x180005ee4`
- `0x180006388`
- `0x180007630`
- `0x180007858`
- `0x1800078a8`
- `0x1800078f0`
- `0x18000793c`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180007765`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180007765`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18000773a`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18000773a`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x1800077d4`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x1800077d4`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<unsigned int>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
        __int64 a1)
{
  unsigned int v2; // esi
  __int64 v3; // rcx
  int (__fastcall *v4)(__int64, GUID *, LPUNKNOWN *); // rbx
  __int64 v5; // rdx
  bool v6; // dl
  IUnknown *v7; // rbx
  unsigned int v8; // eax
  struct IRpcOptions *v9; // rcx
  struct IUnknown *v10; // rcx
  LPUNKNOWN v11; // rcx
  LPSTREAM ppstm; // [rsp+38h] [rbp-18h] BYREF
  HRESULT v14; // [rsp+40h] [rbp-10h]
  unsigned int v15; // [rsp+80h] [rbp+30h] BYREF
  struct IUnknown *v16; // [rsp+88h] [rbp+38h] BYREF
  LPUNKNOWN pUnk; // [rsp+90h] [rbp+40h] BYREF
  struct IRpcOptions *v18; // [rsp+98h] [rbp+48h] BYREF

  v2 = 0;
  Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToCompleted();
  if ( *(int *)(v3 + 136) > 0 && _InterlockedIncrement((volatile signed __int32 *)(v3 + 16)) == 1 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
    pUnk = 0;
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const CloudExperienceHostBroker::LocalNgc::CreateLocalPinAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(a1);
    v4 = **(int (__fastcall ***)(__int64, GUID *, LPUNKNOWN *))a1;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pUnk);
    if ( v4(a1, &GUID_ef60385f_be78_584b_aaef_7829ada2b0de, &pUnk) >= 0 )
    {
      v15 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v15, *(_DWORD *)(a1 + 56), -2);
      v16 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
      if ( (int)Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<unsigned int>>::CopyLocal(
                  a1 + 120,
                  v5,
                  &v16) >= 0 )
      {
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<bool> *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(a1);
        v18 = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
        RpcOptionsHelper::GetRpcOptions(v16, v6, &v18);
        ppstm = 0;
        v14 = 0;
        if ( v18 && v16 )
        {
          v7 = pUnk;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppstm);
          v14 = CreateStreamOnHGlobal(0, 1, &ppstm);
          if ( v14 >= 0 )
            v14 = CoMarshalInterface(ppstm, &GUID_00000000_0000_0000_c000_000000000046, v7, 0, 0, 1u);
        }
        else
        {
          v14 = -2147467262;
        }
        v8 = ((__int64 (__fastcall *)(struct IUnknown *, LPUNKNOWN, _QWORD))v16->lpVtbl[1].QueryInterface)(
               v16,
               pUnk,
               v15);
        v2 = Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireCompletionErrorPropagationPolicyFilter(
               v8,
               v16,
               *(_QWORD *)(a1 + 128));
        Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<unsigned int>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(a1);
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const CloudExperienceHostBroker::LocalNgc::CreateLocalPinAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete();
        if ( v14 >= 0 )
        {
          (*(void (__fastcall **)(LPSTREAM, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppstm + 40LL))(ppstm, 0, 0, 0);
          CoReleaseMarshalData(ppstm);
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppstm);
        v9 = v18;
        if ( v18 )
        {
          v18 = 0;
          ((void (__fastcall *)(struct IRpcOptions *))v9->lpVtbl->Release)(v9);
        }
      }
      v10 = v16;
      if ( v16 )
      {
        v16 = 0;
        ((void (__fastcall *)(struct IUnknown *))v10->lpVtbl->Release)(v10);
      }
    }
    v11 = pUnk;
    if ( pUnk )
    {
      pUnk = 0;
      ((void (__fastcall *)(LPUNKNOWN))v11->lpVtbl->Release)(v11);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
  }
  return v2;
}

```

## disassembly

```asm
0x180007630  push    rbp
0x180007632  push    rbx
0x180007633  push    rsi
0x180007634  push    rdi
0x180007635  push    r14
0x180007637  mov     rbp, rsp
0x18000763a  sub     rsp, 50h
0x18000763e  mov     rdi, rcx
0x180007641  xor     r14d, r14d
0x180007644  mov     esi, r14d
0x180007647  call    ?TryTransitionToCompleted@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NW4CancelTransitionPolicy@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToCompleted(Microsoft::WRL::CancelTransitionPolicy)
0x18000764c  cmp     [rcx+88h], r14d
0x180007653  jle     loc_180007842
0x180007659  lea     eax, [r14+1]
0x18000765d  lock xadd [rcx+10h], eax
0x180007662  inc     eax
0x180007664  cmp     eax, 1
0x180007667  jnz     loc_180007842
0x18000766d  mov     [rbp+var_20], rcx
0x180007671  mov     rax, [rcx]
0x180007674  mov     rax, [rax+8]
0x180007678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000767d  nop
0x18000767e  mov     [rbp+pUnk], r14
0x180007682  mov     rcx, rdi
0x180007685  call    ?TraceOperationComplete@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?CreateLocalPinAsyncActionName@LocalNgc@CloudExperienceHostBroker@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const CloudExperienceHostBroker::LocalNgc::CreateLocalPinAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x18000768a  nop
0x18000768b  mov     rax, [rdi]
0x18000768e  mov     rbx, [rax]
0x180007691  lea     rcx, [rbp+pUnk]
0x180007695  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000769a  lea     r8, [rbp+pUnk]
0x18000769e  lea     rdx, _GUID_ef60385f_be78_584b_aaef_7829ada2b0de
0x1800076a5  mov     rcx, rdi
0x1800076a8  mov     rax, rbx
0x1800076ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076b0  nop
0x1800076b1  test    eax, eax
0x1800076b3  js      loc_180007818
0x1800076b9  mov     [rbp+arg_0], 0FFFFFFFEh
0x1800076c0  mov     ecx, [rdi+38h]
0x1800076c3  mov     eax, [rbp+arg_0]
0x1800076c6  lock cmpxchg [rbp+arg_0], ecx
0x1800076cb  mov     [rbp+arg_8], r14
0x1800076cf  lea     rcx, [rbp+arg_8]
0x1800076d3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800076d8  lea     rcx, [rdi+78h]
0x1800076dc  lea     r8, [rbp+arg_8]
0x1800076e0  call    ?CopyLocal@?$GitPtrSupportsAgile@U?$IAsyncOperationCompletedHandler@I@Foundation@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<uint>>::CopyLocal(_GUID const &,void * *)
0x1800076e5  test    eax, eax
0x1800076e7  js      loc_1800077FE
0x1800076ed  mov     rcx, rdi
0x1800076f0  call    ?TraceCompletionNotificationStart@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@_N@Collections@Foundation@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<bool> *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(void)
0x1800076f5  mov     [rbp+arg_18], r14
0x1800076f9  lea     rcx, [rbp+arg_18]
0x1800076fd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180007702  lea     r8, [rbp+arg_18]; struct IRpcOptions **
0x180007706  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x18000770a  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x18000770f  mov     [rbp+ppstm], r14
0x180007713  mov     [rbp+var_10], r14d
0x180007717  cmp     [rbp+arg_18], r14
0x18000771b  jz      short loc_180007770
0x18000771d  cmp     [rbp+arg_8], r14
0x180007721  jz      short loc_180007770
0x180007723  mov     rbx, [rbp+pUnk]
0x180007727  lea     rcx, [rbp+ppstm]
0x18000772b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180007730  lea     r8, [rbp+ppstm]; ppstm
0x180007734  lea     edx, [r14+1]; fDeleteOnRelease
0x180007738  xor     ecx, ecx; hGlobal
0x18000773a  call    cs:__imp_CreateStreamOnHGlobal
0x180007740  mov     [rbp+var_10], eax
0x180007743  test    eax, eax
0x180007745  js      short loc_180007777
0x180007747  mov     [rsp+50h+mshlflags], 1; mshlflags
0x18000774f  mov     [rsp+50h+pvDestContext], r14; pvDestContext
0x180007754  xor     r9d, r9d; dwDestContext
0x180007757  mov     r8, rbx; pUnk
0x18000775a  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180007761  mov     rcx, [rbp+ppstm]; pStm
0x180007765  call    cs:__imp_CoMarshalInterface
0x18000776b  mov     [rbp+var_10], eax
0x18000776e  jmp     short loc_180007777
0x180007770  mov     [rbp+var_10], 80004002h
0x180007777  mov     rcx, [rbp+arg_8]
0x18000777b  mov     rax, [rcx]
0x18000777e  mov     r8d, [rbp+arg_0]
0x180007782  mov     rdx, [rbp+pUnk]
0x180007786  mov     rax, [rax+18h]
0x18000778a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000778f  mov     r8, [rdi+80h]
0x180007796  mov     rdx, [rbp+arg_8]
0x18000779a  mov     ecx, eax
0x18000779c  call    ?FireCompletionErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireCompletionErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x1800077a1  mov     esi, eax
0x1800077a3  mov     rcx, rdi
0x1800077a6  call    ?UnlockCompleteDelegate@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@I@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<uint>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(void)
0x1800077ab  call    ?TraceCompletionNotificationComplete@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?CreateLocalPinAsyncActionName@LocalNgc@CloudExperienceHostBroker@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const CloudExperienceHostBroker::LocalNgc::CreateLocalPinAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(void)
0x1800077b0  nop
0x1800077b1  cmp     [rbp+var_10], r14d
0x1800077b5  jl      short loc_1800077DA
0x1800077b7  mov     rcx, [rbp+ppstm]
0x1800077bb  mov     rdx, r14
0x1800077be  mov     r8, [rcx]
0x1800077c1  mov     rax, [r8+28h]
0x1800077c5  xor     r9d, r9d
0x1800077c8  xor     r8d, r8d
0x1800077cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077d0  mov     rcx, [rbp+ppstm]; pStm
0x1800077d4  call    cs:__imp_CoReleaseMarshalData
0x1800077da  lea     rcx, [rbp+ppstm]
0x1800077de  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800077e3  nop
0x1800077e4  mov     rcx, [rbp+arg_18]
0x1800077e8  test    rcx, rcx
0x1800077eb  jz      short loc_1800077FE
0x1800077ed  mov     [rbp+arg_18], r14
0x1800077f1  mov     rax, [rcx]
0x1800077f4  mov     rax, [rax+10h]
0x1800077f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077fd  nop
0x1800077fe  mov     rcx, [rbp+arg_8]
0x180007802  test    rcx, rcx
0x180007805  jz      short loc_180007818
0x180007807  mov     [rbp+arg_8], r14
0x18000780b  mov     rax, [rcx]
0x18000780e  mov     rax, [rax+10h]
0x180007812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007817  nop
0x180007818  mov     rcx, [rbp+pUnk]
0x18000781c  test    rcx, rcx
0x18000781f  jz      short loc_180007832
0x180007821  mov     [rbp+pUnk], r14
0x180007825  mov     rax, [rcx]
0x180007828  mov     rax, [rax+10h]
0x18000782c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007831  nop
0x180007832  mov     rax, [rdi]
0x180007835  mov     rcx, rdi
0x180007838  mov     rax, [rax+10h]
0x18000783c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007841  nop
0x180007842  mov     eax, esi
0x180007844  add     rsp, 50h
0x180007848  pop     r14
0x18000784a  pop     rdi
0x18000784b  pop     rsi
0x18000784c  pop     rbx
0x18000784d  pop     rbp
0x18000784e  retn
```
