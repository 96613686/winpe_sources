# Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireProgress(int)

- ea: `0x1800b68c0`
- end: `0x1800b6ac7`
- name: `?FireProgress@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@QEAAJH@Z`
- size: `519`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800b7af0`

## callees

- `0x18000892c`
- `0x1800583d8`
- `0x180058c84`
- `0x180058eb0`
- `0x1800837a0`
- `0x1800854b8`
- `0x1800b68c0`
- `0x1800b7b0c`
- `0x1800b7bc8`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800b69de`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800b69de`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x1800b6a0a`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x1800b6a0a`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireProgress(
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
  if ( (unsigned __int8)Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryLockProgressDelegate(a1) )
  {
    v5 = **(int (__fastcall ***)(__int64, GUID *, LPUNKNOWN *))a1;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&pUnk);
    if ( v5(a1, &GUID_00000000_0000_0000_c000_000000000046, &pUnk) >= 0 )
    {
      v15 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v15);
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
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v17);
        RpcOptionsHelper::GetRpcOptions(v15, v7, &v17);
        ppstm = 0;
        v13 = 0;
        if ( v17 && v15 )
        {
          v8 = pUnk;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&ppstm);
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
        AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>>(&ppstm);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v17);
      }
      Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockProgressDelegate(a1);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v15);
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&pUnk);
  if ( a1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
  return v4;
}

```

## disassembly

```asm
0x1800b68c0  mov     [rsp-28h+arg_8], rbx
0x1800b68c5  push    rbp
0x1800b68c6  push    rsi
0x1800b68c7  push    rdi
0x1800b68c8  push    r12
0x1800b68ca  push    r14
0x1800b68cc  mov     rbp, rsp
0x1800b68cf  sub     rsp, 70h
0x1800b68d3  mov     r14d, edx
0x1800b68d6  mov     rdi, rcx
0x1800b68d9  xor     esi, esi
0x1800b68db  mov     [rbp+var_30], rcx
0x1800b68df  lea     rcx, [rbp+var_30]
0x1800b68e3  call    ?InternalAddRef@?$ComPtr@UIAsyncFireCompletion@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(void)
0x1800b68e8  nop
0x1800b68e9  mov     [rbp+pUnk], rsi
0x1800b68ed  mov     rcx, rdi
0x1800b68f0  call    ?TryLockProgressDelegate@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAA_NXZ; Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryLockProgressDelegate(void)
0x1800b68f5  test    al, al
0x1800b68f7  jz      loc_1800B6A92
0x1800b68fd  mov     rax, [rdi]
0x1800b6900  mov     rbx, [rax]
0x1800b6903  lea     rcx, [rbp+pUnk]
0x1800b6907  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800b690c  lea     r8, [rbp+pUnk]
0x1800b6910  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800b6917  mov     rcx, rdi
0x1800b691a  mov     rax, rbx
0x1800b691d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6922  nop
0x1800b6923  test    eax, eax
0x1800b6925  js      loc_1800B6A92
0x1800b692b  mov     [rbp+arg_0], rsi
0x1800b692f  lea     rcx, [rbp+arg_0]
0x1800b6933  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800b6938  lea     rcx, [rdi+90h]
0x1800b693f  lea     r8, [rbp+arg_0]
0x1800b6943  call    ?CopyLocal@?$GitPtrSupportsAgile@UINilDelegate@Internal@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Internal::INilDelegate>::CopyLocal(_GUID const &,void * *)
0x1800b6948  test    eax, eax
0x1800b694a  js      loc_1800B6A7F
0x1800b6950  lea     r12d, [rsi+1]
0x1800b6954  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x1800b695b  test    rcx, rcx
0x1800b695e  jz      short loc_1800B698D
0x1800b6960  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x1800b6967  movdqu  [rbp+var_10], xmm0
0x1800b696c  mov     rax, [rcx]
0x1800b696f  mov     [rsp+70h+mshlflags], r12d
0x1800b6974  mov     [rsp+70h+pvDestContext], rdi
0x1800b6979  lea     r9, [rbp+var_10]
0x1800b697d  lea     r8d, [rsi+2]
0x1800b6981  mov     edx, r12d
0x1800b6984  mov     rax, [rax+48h]
0x1800b6988  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b698d  mov     [rbp+arg_18], 0
0x1800b6995  lea     rcx, [rbp+arg_18]
0x1800b6999  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800b699e  lea     r8, [rbp+arg_18]; struct IRpcOptions **
0x1800b69a2  mov     rcx, [rbp+arg_0]; struct IUnknown *
0x1800b69a6  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x1800b69ab  mov     [rbp+ppstm], 0
0x1800b69b3  mov     [rbp+var_20], 0
0x1800b69ba  cmp     [rbp+arg_18], 0
0x1800b69bf  jz      short loc_1800B6A15
0x1800b69c1  cmp     [rbp+arg_0], 0
0x1800b69c6  jz      short loc_1800B6A15
0x1800b69c8  mov     rbx, [rbp+pUnk]
0x1800b69cc  lea     rcx, [rbp+ppstm]
0x1800b69d0  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800b69d5  lea     r8, [rbp+ppstm]; ppstm
0x1800b69d9  mov     edx, r12d; fDeleteOnRelease
0x1800b69dc  xor     ecx, ecx; hGlobal
0x1800b69de  call    cs:__imp_CreateStreamOnHGlobal
0x1800b69e4  mov     [rbp+var_20], eax
0x1800b69e7  test    eax, eax
0x1800b69e9  js      short loc_1800B6A1C
0x1800b69eb  mov     [rsp+70h+mshlflags], r12d; mshlflags
0x1800b69f0  mov     [rsp+70h+pvDestContext], 0; pvDestContext
0x1800b69f9  xor     r9d, r9d; dwDestContext
0x1800b69fc  mov     r8, rbx; pUnk
0x1800b69ff  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x1800b6a06  mov     rcx, [rbp+ppstm]; pStm
0x1800b6a0a  call    cs:__imp_CoMarshalInterface
0x1800b6a10  mov     [rbp+var_20], eax
0x1800b6a13  jmp     short loc_1800B6A1C
0x1800b6a15  mov     [rbp+var_20], 80004002h
0x1800b6a1c  mov     rcx, [rbp+arg_0]
0x1800b6a20  mov     rax, [rcx]
0x1800b6a23  mov     r8d, r14d
0x1800b6a26  mov     rdx, [rbp+pUnk]
0x1800b6a2a  mov     rax, [rax+18h]
0x1800b6a2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6a33  mov     r8, [rdi+98h]
0x1800b6a3a  mov     rdx, [rbp+arg_0]
0x1800b6a3e  mov     ecx, eax
0x1800b6a40  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x1800b6a45  mov     esi, eax
0x1800b6a47  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x1800b6a4e  test    rcx, rcx
0x1800b6a51  jz      short loc_1800B6A6C
0x1800b6a53  mov     r9, [rcx]
0x1800b6a56  mov     rax, [r9+50h]
0x1800b6a5a  mov     r9d, r12d
0x1800b6a5d  mov     r8d, 2
0x1800b6a63  mov     edx, r12d
0x1800b6a66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6a6b  nop
0x1800b6a6c  lea     rcx, [rbp+ppstm]
0x1800b6a70  call    ??1?$AutoStubBias@U?$IAsyncOperation@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUIRandomAccessStream@Streams@Storage@Windows@@@23@@@QEAA@XZ; AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>>(void)
0x1800b6a75  nop
0x1800b6a76  lea     rcx, [rbp+arg_18]
0x1800b6a7a  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800b6a7f  mov     rcx, rdi
0x1800b6a82  call    ?UnlockProgressDelegate@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockProgressDelegate(void)
0x1800b6a87  nop
0x1800b6a88  lea     rcx, [rbp+arg_0]
0x1800b6a8c  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800b6a91  nop
0x1800b6a92  lea     rcx, [rbp+pUnk]
0x1800b6a96  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800b6a9b  nop
0x1800b6a9c  test    rdi, rdi
0x1800b6a9f  jz      short loc_1800B6AB1
0x1800b6aa1  mov     rax, [rdi]
0x1800b6aa4  mov     rcx, rdi
0x1800b6aa7  mov     rax, [rax+10h]
0x1800b6aab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6ab0  nop
0x1800b6ab1  mov     eax, esi
0x1800b6ab3  mov     rbx, [rsp+70h+arg_8]
0x1800b6abb  add     rsp, 70h
0x1800b6abf  pop     r14
0x1800b6ac1  pop     r12
0x1800b6ac3  pop     rdi
0x1800b6ac4  pop     rsi
0x1800b6ac5  pop     rbp
0x1800b6ac6  retn
```
