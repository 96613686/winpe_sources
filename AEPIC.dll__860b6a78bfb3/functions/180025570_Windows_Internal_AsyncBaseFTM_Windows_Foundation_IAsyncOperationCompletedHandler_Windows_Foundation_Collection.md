# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x180025570`
- end: `0x180025712`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVInstalledDesktopApp@Inventory@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `418`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180025720`

## callees

- `0x18000a2d4`
- `0x180023378`
- `0x1800241f0`
- `0x1800251e0`
- `0x180025570`
- `0x180025790`
- `0x1800265f8`
- `0x180026bc0`
- `0x180027f20`
- `0x180027f50`
- `0x180027ff4`
- `0x180028118`
- `0x18002823c`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180025684`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180025684`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180025655`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180025655`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
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
  Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(
    a1,
    1);
  if ( *(int *)(a1 + 136) > 0 && _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 16), v3) + 1 == v3 )
  {
    v9 = a1;
    Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(&v9);
    pUnk = 0;
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(a1);
    if ( (int)Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>>(
                &v9,
                &pUnk) >= 0 )
    {
      v12 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v12, *(_DWORD *)(a1 + 56), -2);
      v13 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
      if ( (int)Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>>::CopyLocal(
                  a1 + 120,
                  v4,
                  &v13) >= 0 )
      {
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(a1);
        v14 = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
        RpcOptionsHelper::GetRpcOptions(v13, v5, &v14);
        ppstm = 0;
        v11 = 0;
        if ( v14 && v13 )
        {
          v6 = pUnk;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppstm);
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
        Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(a1);
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete();
        AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>>(&ppstm);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pUnk);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
  }
  return v2;
}

```

## disassembly

```asm
0x180025570  push    rbp
0x180025572  push    rbx
0x180025573  push    rdi
0x180025574  mov     rbp, rsp
0x180025577  sub     rsp, 50h
0x18002557b  mov     rbx, rcx
0x18002557e  xor     edi, edi
0x180025580  lea     edx, [rdi+1]
0x180025583  call    ?TransitionToState@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVInstalledDesktopApp@Inventory@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x180025588  cmp     [rbx+88h], edi
0x18002558e  jle     loc_180025708
0x180025594  mov     eax, edx
0x180025596  lock xadd [rbx+10h], eax
0x18002559b  inc     eax
0x18002559d  cmp     eax, edx
0x18002559f  jnz     loc_180025708
0x1800255a5  mov     [rbp+var_20], rbx
0x1800255a9  lea     rcx, [rbp+var_20]
0x1800255ad  call    ?InternalAddRef@?$ComPtr@UIAsyncFireCompletion@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(void)
0x1800255b2  nop
0x1800255b3  mov     [rbp+pUnk], rdi
0x1800255b7  mov     rcx, rbx
0x1800255ba  call    ?TraceOperationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVInstalledDesktopApp@Inventory@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x1800255bf  lea     rdx, [rbp+pUnk]
0x1800255c3  lea     rcx, [rbp+var_20]
0x1800255c7  call    ??$As@U?$IAsyncOperation@PEAU?$IVectorView@PEAVInstalledDesktopApp@Inventory@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IAsyncOperation@PEAU?$IVectorView@PEAVInstalledDesktopApp@Inventory@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>>>)
0x1800255cc  test    eax, eax
0x1800255ce  js      loc_1800256EE
0x1800255d4  mov     [rbp+arg_0], 0FFFFFFFEh
0x1800255db  mov     ecx, [rbx+38h]
0x1800255de  mov     eax, [rbp+arg_0]
0x1800255e1  lock cmpxchg [rbp+arg_0], ecx
0x1800255e6  mov     [rbp+arg_8], rdi
0x1800255ea  lea     rcx, [rbp+arg_8]
0x1800255ee  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800255f3  lea     rcx, [rbx+78h]
0x1800255f7  lea     r8, [rbp+arg_8]
0x1800255fb  call    ?CopyLocal@?$GitPtrSupportsAgile@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVInstalledDesktopApp@Inventory@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>>::CopyLocal(_GUID const &,void * *)
0x180025600  test    eax, eax
0x180025602  js      loc_1800256E4
0x180025608  mov     rcx, rbx
0x18002560b  call    ?TraceCompletionNotificationStart@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVInstalledDesktopApp@Inventory@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(void)
0x180025610  mov     [rbp+arg_10], rdi
0x180025614  lea     rcx, [rbp+arg_10]
0x180025618  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002561d  lea     r8, [rbp+arg_10]; struct IRpcOptions **
0x180025621  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x180025625  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x18002562a  mov     [rbp+ppstm], rdi
0x18002562e  mov     [rbp+var_10], edi
0x180025631  cmp     [rbp+arg_10], rdi
0x180025635  jz      short loc_18002568F
0x180025637  cmp     [rbp+arg_8], rdi
0x18002563b  jz      short loc_18002568F
0x18002563d  mov     rdi, [rbp+pUnk]
0x180025641  lea     rcx, [rbp+ppstm]
0x180025645  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002564a  lea     r8, [rbp+ppstm]; ppstm
0x18002564e  mov     edx, 1; fDeleteOnRelease
0x180025653  xor     ecx, ecx; hGlobal
0x180025655  call    cs:__imp_CreateStreamOnHGlobal
0x18002565b  mov     [rbp+var_10], eax
0x18002565e  test    eax, eax
0x180025660  js      short loc_180025696
0x180025662  mov     [rsp+50h+mshlflags], 1; mshlflags
0x18002566a  mov     [rsp+50h+pvDestContext], 0; pvDestContext
0x180025673  xor     r9d, r9d; dwDestContext
0x180025676  mov     r8, rdi; pUnk
0x180025679  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180025680  mov     rcx, [rbp+ppstm]; pStm
0x180025684  call    cs:__imp_CoMarshalInterface
0x18002568a  mov     [rbp+var_10], eax
0x18002568d  jmp     short loc_180025696
0x18002568f  mov     [rbp+var_10], 80004002h
0x180025696  mov     rcx, [rbp+arg_8]
0x18002569a  mov     rax, [rcx]
0x18002569d  mov     r8d, [rbp+arg_0]
0x1800256a1  mov     rdx, [rbp+pUnk]
0x1800256a5  mov     rax, [rax+18h]
0x1800256a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800256ae  mov     r8, [rbx+80h]
0x1800256b5  mov     rdx, [rbp+arg_8]
0x1800256b9  mov     ecx, eax
0x1800256bb  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x1800256c0  mov     edi, eax
0x1800256c2  mov     rcx, rbx
0x1800256c5  call    ?UnlockCompleteDelegate@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVInstalledDesktopApp@Inventory@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(void)
0x1800256ca  call    ?TraceCompletionNotificationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVInstalledDesktopApp@Inventory@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(void)
0x1800256cf  nop
0x1800256d0  lea     rcx, [rbp+ppstm]
0x1800256d4  call    ??1?$AutoStubBias@U?$IAsyncOperation@PEAU?$IVectorView@PEAVInstalledDesktopApp@Inventory@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVInstalledDesktopApp@Inventory@System@Windows@@@Collections@Foundation@Windows@@@23@@@QEAA@XZ; AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>>(void)
0x1800256d9  nop
0x1800256da  lea     rcx, [rbp+arg_10]
0x1800256de  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800256e3  nop
0x1800256e4  lea     rcx, [rbp+arg_8]
0x1800256e8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800256ed  nop
0x1800256ee  lea     rcx, [rbp+pUnk]
0x1800256f2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800256f7  nop
0x1800256f8  mov     rax, [rbx]
0x1800256fb  mov     rcx, rbx
0x1800256fe  mov     rax, [rax+10h]
0x180025702  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025707  nop
0x180025708  mov     eax, edi
0x18002570a  add     rsp, 50h
0x18002570e  pop     rdi
0x18002570f  pop     rbx
0x180025710  pop     rbp
0x180025711  retn
```
