# Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::AutoUpdateTimeZoneStatus>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireProgress(int)

- ea: `0x1800156dc`
- end: `0x1800158e3`
- name: `?FireProgress@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@W4AutoUpdateTimeZoneStatus@System@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@QEAAJH@Z`
- size: `519`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180016ca0`

## callees

- `0x180007248`
- `0x180014534`
- `0x180015130`
- `0x180015600`
- `0x1800156dc`
- `0x180015bc0`
- `0x180016054`
- `0x18001728c`
- `0x1800173b8`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800157fa`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800157fa`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180015826`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180015826`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::System::AutoUpdateTimeZoneStatus>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireProgress(
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
  if ( (unsigned __int8)Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::System::AutoUpdateTimeZoneStatus>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryLockProgressDelegate(a1) )
  {
    v5 = **(int (__fastcall ***)(__int64, GUID *, LPUNKNOWN *))a1;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pUnk);
    if ( v5(a1, &GUID_00000000_0000_0000_c000_000000000046, &pUnk) >= 0 )
    {
      v15 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v15);
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
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
        RpcOptionsHelper::GetRpcOptions(v15, v7, &v17);
        ppstm = 0;
        v13 = 0;
        if ( v17 && v15 )
        {
          v8 = pUnk;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppstm);
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
        AutoStubBias<Windows::Foundation::IAsyncOperation<enum Windows::System::AutoUpdateTimeZoneStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::System::AutoUpdateTimeZoneStatus>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<enum Windows::System::AutoUpdateTimeZoneStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::System::AutoUpdateTimeZoneStatus>>((int *)&ppstm);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
      }
      Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::System::AutoUpdateTimeZoneStatus>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockProgressDelegate(a1);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v15);
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pUnk);
  if ( a1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
  return v4;
}

```

## disassembly

```asm
0x1800156dc  mov     [rsp-28h+arg_8], rbx
0x1800156e1  push    rbp
0x1800156e2  push    rsi
0x1800156e3  push    rdi
0x1800156e4  push    r12
0x1800156e6  push    r14
0x1800156e8  mov     rbp, rsp
0x1800156eb  sub     rsp, 70h
0x1800156ef  mov     r14d, edx
0x1800156f2  mov     rdi, rcx
0x1800156f5  xor     esi, esi
0x1800156f7  mov     [rbp+var_30], rcx
0x1800156fb  lea     rcx, [rbp+var_30]
0x1800156ff  call    ?InternalAddRef@?$ComPtr@UIAsyncFireCompletion@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(void)
0x180015704  nop
0x180015705  mov     [rbp+pUnk], rsi
0x180015709  mov     rcx, rdi
0x18001570c  call    ?TryLockProgressDelegate@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@W4AutoUpdateTimeZoneStatus@System@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAA_NXZ; Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::AutoUpdateTimeZoneStatus>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryLockProgressDelegate(void)
0x180015711  test    al, al
0x180015713  jz      loc_1800158AE
0x180015719  mov     rax, [rdi]
0x18001571c  mov     rbx, [rax]
0x18001571f  lea     rcx, [rbp+pUnk]
0x180015723  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180015728  lea     r8, [rbp+pUnk]
0x18001572c  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180015733  mov     rcx, rdi
0x180015736  mov     rax, rbx
0x180015739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001573e  nop
0x18001573f  test    eax, eax
0x180015741  js      loc_1800158AE
0x180015747  mov     [rbp+arg_0], rsi
0x18001574b  lea     rcx, [rbp+arg_0]
0x18001574f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180015754  lea     rcx, [rdi+90h]
0x18001575b  lea     r8, [rbp+arg_0]
0x18001575f  call    ?CopyLocal@?$GitPtrSupportsAgile@UINilDelegate@Internal@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Internal::INilDelegate>::CopyLocal(_GUID const &,void * *)
0x180015764  test    eax, eax
0x180015766  js      loc_18001589B
0x18001576c  lea     r12d, [rsi+1]
0x180015770  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180015777  test    rcx, rcx
0x18001577a  jz      short loc_1800157A9
0x18001577c  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x180015783  movdqu  [rbp+var_10], xmm0
0x180015788  mov     rax, [rcx]
0x18001578b  mov     [rsp+70h+mshlflags], r12d
0x180015790  mov     [rsp+70h+pvDestContext], rdi
0x180015795  lea     r9, [rbp+var_10]
0x180015799  lea     r8d, [rsi+2]
0x18001579d  mov     edx, r12d
0x1800157a0  mov     rax, [rax+48h]
0x1800157a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157a9  mov     [rbp+arg_18], 0
0x1800157b1  lea     rcx, [rbp+arg_18]
0x1800157b5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800157ba  lea     r8, [rbp+arg_18]; struct IRpcOptions **
0x1800157be  mov     rcx, [rbp+arg_0]; struct IUnknown *
0x1800157c2  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x1800157c7  mov     [rbp+ppstm], 0
0x1800157cf  mov     [rbp+var_20], 0
0x1800157d6  cmp     [rbp+arg_18], 0
0x1800157db  jz      short loc_180015831
0x1800157dd  cmp     [rbp+arg_0], 0
0x1800157e2  jz      short loc_180015831
0x1800157e4  mov     rbx, [rbp+pUnk]
0x1800157e8  lea     rcx, [rbp+ppstm]
0x1800157ec  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800157f1  lea     r8, [rbp+ppstm]; ppstm
0x1800157f5  mov     edx, r12d; fDeleteOnRelease
0x1800157f8  xor     ecx, ecx; hGlobal
0x1800157fa  call    cs:__imp_CreateStreamOnHGlobal
0x180015800  mov     [rbp+var_20], eax
0x180015803  test    eax, eax
0x180015805  js      short loc_180015838
0x180015807  mov     [rsp+70h+mshlflags], r12d; mshlflags
0x18001580c  mov     [rsp+70h+pvDestContext], 0; pvDestContext
0x180015815  xor     r9d, r9d; dwDestContext
0x180015818  mov     r8, rbx; pUnk
0x18001581b  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180015822  mov     rcx, [rbp+ppstm]; pStm
0x180015826  call    cs:__imp_CoMarshalInterface
0x18001582c  mov     [rbp+var_20], eax
0x18001582f  jmp     short loc_180015838
0x180015831  mov     [rbp+var_20], 80004002h
0x180015838  mov     rcx, [rbp+arg_0]
0x18001583c  mov     rax, [rcx]
0x18001583f  mov     r8d, r14d
0x180015842  mov     rdx, [rbp+pUnk]
0x180015846  mov     rax, [rax+18h]
0x18001584a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001584f  mov     r8, [rdi+98h]
0x180015856  mov     rdx, [rbp+arg_0]
0x18001585a  mov     ecx, eax
0x18001585c  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x180015861  mov     esi, eax
0x180015863  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18001586a  test    rcx, rcx
0x18001586d  jz      short loc_180015888
0x18001586f  mov     r9, [rcx]
0x180015872  mov     rax, [r9+50h]
0x180015876  mov     r9d, r12d
0x180015879  mov     r8d, 2
0x18001587f  mov     edx, r12d
0x180015882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015887  nop
0x180015888  lea     rcx, [rbp+ppstm]
0x18001588c  call    ??1?$AutoStubBias@U?$IAsyncOperation@W4AutoUpdateTimeZoneStatus@System@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@W4AutoUpdateTimeZoneStatus@System@Windows@@@23@@@QEAA@XZ; AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::System::AutoUpdateTimeZoneStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::AutoUpdateTimeZoneStatus>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::System::AutoUpdateTimeZoneStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::AutoUpdateTimeZoneStatus>>(void)
0x180015891  nop
0x180015892  lea     rcx, [rbp+arg_18]
0x180015896  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001589b  mov     rcx, rdi
0x18001589e  call    ?UnlockProgressDelegate@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@W4AutoUpdateTimeZoneStatus@System@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::AutoUpdateTimeZoneStatus>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockProgressDelegate(void)
0x1800158a3  nop
0x1800158a4  lea     rcx, [rbp+arg_0]
0x1800158a8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800158ad  nop
0x1800158ae  lea     rcx, [rbp+pUnk]
0x1800158b2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800158b7  nop
0x1800158b8  test    rdi, rdi
0x1800158bb  jz      short loc_1800158CD
0x1800158bd  mov     rax, [rdi]
0x1800158c0  mov     rcx, rdi
0x1800158c3  mov     rax, [rax+10h]
0x1800158c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158cc  nop
0x1800158cd  mov     eax, esi
0x1800158cf  mov     rbx, [rsp+70h+arg_8]
0x1800158d7  add     rsp, 70h
0x1800158db  pop     r14
0x1800158dd  pop     r12
0x1800158df  pop     rdi
0x1800158e0  pop     rsi
0x1800158e1  pop     rbp
0x1800158e2  retn
```
