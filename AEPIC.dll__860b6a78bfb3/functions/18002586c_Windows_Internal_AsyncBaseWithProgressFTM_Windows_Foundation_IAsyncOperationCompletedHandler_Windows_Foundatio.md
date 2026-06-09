# Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireProgress(int)

- ea: `0x18002586c`
- end: `0x180025a73`
- name: `?FireProgress@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVInstalledDesktopApp@Inventory@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@QEAAJH@Z`
- size: `519`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180027e10`

## callees

- `0x18000a2d4`
- `0x1800241f0`
- `0x180025228`
- `0x180025790`
- `0x18002586c`
- `0x1800265f8`
- `0x180026bc0`
- `0x180028180`
- `0x180028288`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x1800259b6`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x1800259b6`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18002598a`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18002598a`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireProgress(
        __int64 a1,
        unsigned int a2)
{
  unsigned int v4; // esi
  int (__fastcall *v5)(__int64, GUID *, LPUNKNOWN *); // rbx
  __int64 v6; // rdx
  bool v7; // dl
  IUnknown *v8; // rbx
  unsigned int v9; // eax
  __int64 v11; // [rsp+40h] [rbp-30h] BYREF
  LPSTREAM ppstm; // [rsp+48h] [rbp-28h] BYREF
  HRESULT v13; // [rsp+50h] [rbp-20h]
  GUID v14; // [rsp+60h] [rbp-10h] BYREF
  struct IUnknown *v15; // [rsp+A0h] [rbp+30h] BYREF
  LPUNKNOWN pUnk; // [rsp+B0h] [rbp+40h] BYREF
  struct IRpcOptions *v17; // [rsp+B8h] [rbp+48h] BYREF

  v4 = 0;
  v11 = a1;
  Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(&v11);
  pUnk = 0;
  if ( (unsigned __int8)Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryLockProgressDelegate(a1) )
  {
    v5 = **(int (__fastcall ***)(__int64, GUID *, LPUNKNOWN *))a1;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pUnk);
    if ( v5(a1, &GUID_00000000_0000_0000_c000_000000000046, &pUnk) >= 0 )
    {
      v15 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
      if ( (int)Windows::Internal::GitPtrSupportsAgile<Windows::Internal::INilDelegate>::CopyLocal(a1 + 144, v6, &v15) >= 0 )
      {
        if ( Microsoft::WRL::gCausality )
        {
          v14 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
          (*(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, __int64, __int64, GUID *, __int64, int))(*(_QWORD *)Microsoft::WRL::gCausality + 72LL))(
            Microsoft::WRL::gCausality,
            1,
            2,
            &v14,
            a1,
            1);
        }
        v17 = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
        RpcOptionsHelper::GetRpcOptions(v15, v7, &v17);
        ppstm = 0;
        v13 = 0;
        if ( v17 && v15 )
        {
          v8 = pUnk;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppstm);
          v13 = CreateStreamOnHGlobal(0, 1, &ppstm);
          if ( v13 >= 0 )
            v13 = CoMarshalInterface(ppstm, &GUID_00000000_0000_0000_c000_000000000046, v8, 0, 0, 1u);
        }
        else
        {
          v13 = -2147467262;
        }
        v9 = ((__int64 (__fastcall *)(struct IUnknown *, LPUNKNOWN, _QWORD))v15->lpVtbl[1].QueryInterface)(
               v15,
               pUnk,
               a2);
        v4 = Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(
               v9,
               v15,
               *(_QWORD *)(a1 + 152));
        if ( Microsoft::WRL::gCausality )
          (*(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, __int64, __int64, __int64))(*(_QWORD *)Microsoft::WRL::gCausality + 80LL))(
            Microsoft::WRL::gCausality,
            1,
            2,
            1);
        AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>>(&ppstm);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
      }
      Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockProgressDelegate(a1);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pUnk);
  if ( a1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
  return v4;
}

```

## disassembly

```asm
0x18002586c  mov     [rsp-28h+arg_8], rbx
0x180025871  push    rbp
0x180025872  push    rsi
0x180025873  push    rdi
0x180025874  push    r12
0x180025876  push    r14
0x180025878  mov     rbp, rsp
0x18002587b  sub     rsp, 70h
0x18002587f  mov     r14d, edx
0x180025882  mov     rdi, rcx
0x180025885  xor     esi, esi
0x180025887  mov     [rbp+var_30], rcx
0x18002588b  lea     rcx, [rbp+var_30]
0x18002588f  call    ?InternalAddRef@?$ComPtr@UIAsyncFireCompletion@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(void)
0x180025894  nop
0x180025895  mov     [rbp+pUnk], rsi
0x180025899  mov     rcx, rdi
0x18002589c  call    ?TryLockProgressDelegate@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVInstalledDesktopApp@Inventory@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAA_NXZ; Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryLockProgressDelegate(void)
0x1800258a1  test    al, al
0x1800258a3  jz      loc_180025A3E
0x1800258a9  mov     rax, [rdi]
0x1800258ac  mov     rbx, [rax]
0x1800258af  lea     rcx, [rbp+pUnk]
0x1800258b3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800258b8  lea     r8, [rbp+pUnk]
0x1800258bc  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800258c3  mov     rcx, rdi
0x1800258c6  mov     rax, rbx
0x1800258c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800258ce  nop
0x1800258cf  test    eax, eax
0x1800258d1  js      loc_180025A3E
0x1800258d7  mov     [rbp+arg_0], rsi
0x1800258db  lea     rcx, [rbp+arg_0]
0x1800258df  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800258e4  lea     rcx, [rdi+90h]
0x1800258eb  lea     r8, [rbp+arg_0]
0x1800258ef  call    ?CopyLocal@?$GitPtrSupportsAgile@UINilDelegate@Internal@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Internal::INilDelegate>::CopyLocal(_GUID const &,void * *)
0x1800258f4  test    eax, eax
0x1800258f6  js      loc_180025A2B
0x1800258fc  lea     r12d, [rsi+1]
0x180025900  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180025907  test    rcx, rcx
0x18002590a  jz      short loc_180025939
0x18002590c  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x180025913  movdqu  [rbp+var_10], xmm0
0x180025918  mov     rax, [rcx]
0x18002591b  mov     [rsp+70h+mshlflags], r12d
0x180025920  mov     [rsp+70h+pvDestContext], rdi
0x180025925  lea     r9, [rbp+var_10]
0x180025929  lea     r8d, [rsi+2]
0x18002592d  mov     edx, r12d
0x180025930  mov     rax, [rax+48h]
0x180025934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025939  mov     [rbp+arg_18], 0
0x180025941  lea     rcx, [rbp+arg_18]
0x180025945  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002594a  lea     r8, [rbp+arg_18]; struct IRpcOptions **
0x18002594e  mov     rcx, [rbp+arg_0]; struct IUnknown *
0x180025952  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x180025957  mov     [rbp+ppstm], 0
0x18002595f  mov     [rbp+var_20], 0
0x180025966  cmp     [rbp+arg_18], 0
0x18002596b  jz      short loc_1800259C1
0x18002596d  cmp     [rbp+arg_0], 0
0x180025972  jz      short loc_1800259C1
0x180025974  mov     rbx, [rbp+pUnk]
0x180025978  lea     rcx, [rbp+ppstm]
0x18002597c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025981  lea     r8, [rbp+ppstm]; ppstm
0x180025985  mov     edx, r12d; fDeleteOnRelease
0x180025988  xor     ecx, ecx; hGlobal
0x18002598a  call    cs:__imp_CreateStreamOnHGlobal
0x180025990  mov     [rbp+var_20], eax
0x180025993  test    eax, eax
0x180025995  js      short loc_1800259C8
0x180025997  mov     [rsp+70h+mshlflags], r12d; mshlflags
0x18002599c  mov     [rsp+70h+pvDestContext], 0; pvDestContext
0x1800259a5  xor     r9d, r9d; dwDestContext
0x1800259a8  mov     r8, rbx; pUnk
0x1800259ab  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x1800259b2  mov     rcx, [rbp+ppstm]; pStm
0x1800259b6  call    cs:__imp_CoMarshalInterface
0x1800259bc  mov     [rbp+var_20], eax
0x1800259bf  jmp     short loc_1800259C8
0x1800259c1  mov     [rbp+var_20], 80004002h
0x1800259c8  mov     rcx, [rbp+arg_0]
0x1800259cc  mov     rax, [rcx]
0x1800259cf  mov     r8d, r14d
0x1800259d2  mov     rdx, [rbp+pUnk]
0x1800259d6  mov     rax, [rax+18h]
0x1800259da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800259df  mov     r8, [rdi+98h]
0x1800259e6  mov     rdx, [rbp+arg_0]
0x1800259ea  mov     ecx, eax
0x1800259ec  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x1800259f1  mov     esi, eax
0x1800259f3  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x1800259fa  test    rcx, rcx
0x1800259fd  jz      short loc_180025A18
0x1800259ff  mov     r9, [rcx]
0x180025a02  mov     rax, [r9+50h]
0x180025a06  mov     r9d, r12d
0x180025a09  mov     r8d, 2
0x180025a0f  mov     edx, r12d
0x180025a12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025a17  nop
0x180025a18  lea     rcx, [rbp+ppstm]
0x180025a1c  call    ??1?$AutoStubBias@U?$IAsyncOperation@PEAU?$IVectorView@PEAVInstalledDesktopApp@Inventory@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVInstalledDesktopApp@Inventory@System@Windows@@@Collections@Foundation@Windows@@@23@@@QEAA@XZ; AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>>(void)
0x180025a21  nop
0x180025a22  lea     rcx, [rbp+arg_18]
0x180025a26  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025a2b  mov     rcx, rdi
0x180025a2e  call    ?UnlockProgressDelegate@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVInstalledDesktopApp@Inventory@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::Inventory::InstalledDesktopApp *> *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockProgressDelegate(void)
0x180025a33  nop
0x180025a34  lea     rcx, [rbp+arg_0]
0x180025a38  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025a3d  nop
0x180025a3e  lea     rcx, [rbp+pUnk]
0x180025a42  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025a47  nop
0x180025a48  test    rdi, rdi
0x180025a4b  jz      short loc_180025A5D
0x180025a4d  mov     rax, [rdi]
0x180025a50  mov     rcx, rdi
0x180025a53  mov     rax, [rax+10h]
0x180025a57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025a5c  nop
0x180025a5d  mov     eax, esi
0x180025a5f  mov     rbx, [rsp+70h+arg_8]
0x180025a67  add     rsp, 70h
0x180025a6b  pop     r14
0x180025a6d  pop     r12
0x180025a6f  pop     rdi
0x180025a70  pop     rsi
0x180025a71  pop     rbp
0x180025a72  retn
```
