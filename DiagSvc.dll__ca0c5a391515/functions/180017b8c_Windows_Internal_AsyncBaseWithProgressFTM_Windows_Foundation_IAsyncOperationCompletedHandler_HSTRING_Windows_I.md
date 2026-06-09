# Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireProgress(int)

- ea: `0x180017b8c`
- end: `0x180017d87`
- name: `?FireProgress@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@QEAAJH@Z`
- size: `507`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800199e0`

## callees

- `0x18000517c`
- `0x1800056d8`
- `0x18001566c`
- `0x180016c40`
- `0x180017ab0`
- `0x180017b8c`
- `0x1800184a8`
- `0x180019cd8`
- `0x180019de0`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180017cd6`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180017cd6`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180017caa`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180017caa`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireProgress(
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
  if ( (unsigned __int8)Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryLockProgressDelegate(a1) )
  {
    v5 = **(int (__fastcall ***)(__int64, GUID *, LPUNKNOWN *))a1;
    Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&pUnk);
    if ( v5(a1, &GUID_00000000_0000_0000_c000_000000000046, &pUnk) >= 0 )
    {
      v15 = 0;
      Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v15);
      if ( (int)Windows::Internal::GitPtrSupportsAgile<Windows::Internal::INilDelegate>::CopyLocal(
                  (__int64 *)(a1 + 144),
                  v6,
                  &v15) >= 0 )
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
        Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v17);
        RpcOptionsHelper::GetRpcOptions(v15, v7, &v17);
        ppstm = 0;
        v13 = 0;
        if ( v17 && v15 )
        {
          v8 = pUnk;
          Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&ppstm);
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
        AutoStubBias<IUnknown,Windows::Internal::INilDelegate>::~AutoStubBias<IUnknown,Windows::Internal::INilDelegate>(&ppstm);
        Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v17);
      }
      Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockProgressDelegate(a1);
      Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v15);
    }
  }
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&pUnk);
  Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v11);
  return v4;
}

```

## disassembly

```asm
0x180017b8c  mov     [rsp-28h+arg_8], rbx
0x180017b91  push    rbp
0x180017b92  push    rsi
0x180017b93  push    rdi
0x180017b94  push    r12
0x180017b96  push    r14
0x180017b98  mov     rbp, rsp
0x180017b9b  sub     rsp, 70h
0x180017b9f  mov     r14d, edx
0x180017ba2  mov     rdi, rcx
0x180017ba5  xor     esi, esi
0x180017ba7  mov     [rbp+var_30], rcx
0x180017bab  lea     rcx, [rbp+var_30]
0x180017baf  call    ?InternalAddRef@?$ComPtr@UIAsyncFireCompletion@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(void)
0x180017bb4  nop
0x180017bb5  mov     [rbp+pUnk], rsi
0x180017bb9  mov     rcx, rdi
0x180017bbc  call    ?TryLockProgressDelegate@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAA_NXZ; Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryLockProgressDelegate(void)
0x180017bc1  test    al, al
0x180017bc3  jz      loc_180017D5E
0x180017bc9  mov     rax, [rdi]
0x180017bcc  mov     rbx, [rax]
0x180017bcf  lea     rcx, [rbp+pUnk]
0x180017bd3  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180017bd8  lea     r8, [rbp+pUnk]
0x180017bdc  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180017be3  mov     rcx, rdi
0x180017be6  mov     rax, rbx
0x180017be9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017bee  nop
0x180017bef  test    eax, eax
0x180017bf1  js      loc_180017D5E
0x180017bf7  mov     [rbp+arg_0], rsi
0x180017bfb  lea     rcx, [rbp+arg_0]
0x180017bff  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180017c04  lea     rcx, [rdi+90h]
0x180017c0b  lea     r8, [rbp+arg_0]
0x180017c0f  call    ?CopyLocal@?$GitPtrSupportsAgile@UINilDelegate@Internal@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Internal::INilDelegate>::CopyLocal(_GUID const &,void * *)
0x180017c14  test    eax, eax
0x180017c16  js      loc_180017D4B
0x180017c1c  lea     r12d, [rsi+1]
0x180017c20  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180017c27  test    rcx, rcx
0x180017c2a  jz      short loc_180017C59
0x180017c2c  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x180017c33  movdqu  [rbp+var_10], xmm0
0x180017c38  mov     rax, [rcx]
0x180017c3b  mov     [rsp+70h+mshlflags], r12d
0x180017c40  mov     [rsp+70h+pvDestContext], rdi
0x180017c45  lea     r9, [rbp+var_10]
0x180017c49  lea     r8d, [rsi+2]
0x180017c4d  mov     edx, r12d
0x180017c50  mov     rax, [rax+48h]
0x180017c54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c59  mov     [rbp+arg_18], 0
0x180017c61  lea     rcx, [rbp+arg_18]
0x180017c65  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180017c6a  lea     r8, [rbp+arg_18]; struct IRpcOptions **
0x180017c6e  mov     rcx, [rbp+arg_0]; struct IUnknown *
0x180017c72  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x180017c77  mov     [rbp+ppstm], 0
0x180017c7f  mov     [rbp+var_20], 0
0x180017c86  cmp     [rbp+arg_18], 0
0x180017c8b  jz      short loc_180017CE1
0x180017c8d  cmp     [rbp+arg_0], 0
0x180017c92  jz      short loc_180017CE1
0x180017c94  mov     rbx, [rbp+pUnk]
0x180017c98  lea     rcx, [rbp+ppstm]
0x180017c9c  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180017ca1  lea     r8, [rbp+ppstm]; ppstm
0x180017ca5  mov     edx, r12d; fDeleteOnRelease
0x180017ca8  xor     ecx, ecx; hGlobal
0x180017caa  call    cs:__imp_CreateStreamOnHGlobal
0x180017cb0  mov     [rbp+var_20], eax
0x180017cb3  test    eax, eax
0x180017cb5  js      short loc_180017CE8
0x180017cb7  mov     [rsp+70h+mshlflags], r12d; mshlflags
0x180017cbc  mov     [rsp+70h+pvDestContext], 0; pvDestContext
0x180017cc5  xor     r9d, r9d; dwDestContext
0x180017cc8  mov     r8, rbx; pUnk
0x180017ccb  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180017cd2  mov     rcx, [rbp+ppstm]; pStm
0x180017cd6  call    cs:__imp_CoMarshalInterface
0x180017cdc  mov     [rbp+var_20], eax
0x180017cdf  jmp     short loc_180017CE8
0x180017ce1  mov     [rbp+var_20], 80004002h
0x180017ce8  mov     rcx, [rbp+arg_0]
0x180017cec  mov     rax, [rcx]
0x180017cef  mov     r8d, r14d
0x180017cf2  mov     rdx, [rbp+pUnk]
0x180017cf6  mov     rax, [rax+18h]
0x180017cfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017cff  mov     r8, [rdi+98h]
0x180017d06  mov     rdx, [rbp+arg_0]
0x180017d0a  mov     ecx, eax
0x180017d0c  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x180017d11  mov     esi, eax
0x180017d13  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180017d1a  test    rcx, rcx
0x180017d1d  jz      short loc_180017D38
0x180017d1f  mov     r9, [rcx]
0x180017d22  mov     rax, [r9+50h]
0x180017d26  mov     r9d, r12d
0x180017d29  mov     r8d, 2
0x180017d2f  mov     edx, r12d
0x180017d32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d37  nop
0x180017d38  lea     rcx, [rbp+ppstm]
0x180017d3c  call    ??1?$AutoStubBias@UIUnknown@@UINilDelegate@Internal@Windows@@@@QEAA@XZ; AutoStubBias<IUnknown,Windows::Internal::INilDelegate>::~AutoStubBias<IUnknown,Windows::Internal::INilDelegate>(void)
0x180017d41  nop
0x180017d42  lea     rcx, [rbp+arg_18]
0x180017d46  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180017d4b  mov     rcx, rdi
0x180017d4e  call    ?UnlockProgressDelegate@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockProgressDelegate(void)
0x180017d53  nop
0x180017d54  lea     rcx, [rbp+arg_0]
0x180017d58  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180017d5d  nop
0x180017d5e  lea     rcx, [rbp+pUnk]
0x180017d62  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180017d67  nop
0x180017d68  lea     rcx, [rbp+var_30]
0x180017d6c  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180017d71  mov     eax, esi
0x180017d73  mov     rbx, [rsp+70h+arg_8]
0x180017d7b  add     rsp, 70h
0x180017d7f  pop     r14
0x180017d81  pop     r12
0x180017d83  pop     rdi
0x180017d84  pop     rsi
0x180017d85  pop     rbp
0x180017d86  retn
```
