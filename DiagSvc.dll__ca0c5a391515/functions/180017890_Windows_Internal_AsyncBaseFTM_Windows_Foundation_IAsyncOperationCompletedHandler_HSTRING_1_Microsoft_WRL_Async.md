# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x180017890`
- end: `0x180017a2b`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `411`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180017a40`

## callees

- `0x18000517c`
- `0x1800056d8`
- `0x180014150`
- `0x18001566c`
- `0x180016bf8`
- `0x180017890`
- `0x180017ab0`
- `0x1800184a8`
- `0x180019a78`
- `0x180019aa8`
- `0x180019b4c`
- `0x180019c70`
- `0x180019d94`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x1800179a4`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x1800179a4`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180017975`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180017975`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
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
  Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(a1);
  if ( *(int *)(a1 + 136) > 0 && _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 16), v3) + 1 == v3 )
  {
    v9 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))a1;
    Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(&v9);
    pUnk = 0;
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(a1);
    if ( (int)Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<HSTRING__ *>>(
                &v9,
                (__int64)&pUnk) >= 0 )
    {
      v12 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v12, *(_DWORD *)(a1 + 56), -2);
      v13 = 0;
      Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v13);
      if ( (int)Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>>::CopyLocal(
                  (__int64 *)(a1 + 120),
                  v4,
                  &v13) >= 0 )
      {
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(a1);
        v14 = 0;
        Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v14);
        RpcOptionsHelper::GetRpcOptions(v13, v5, &v14);
        ppstm = 0;
        v11 = 0;
        if ( v14 && v13 )
        {
          v6 = pUnk;
          Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&ppstm);
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
        Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(a1);
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete();
        AutoStubBias<IUnknown,Windows::Internal::INilDelegate>::~AutoStubBias<IUnknown,Windows::Internal::INilDelegate>(&ppstm);
        Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v14);
      }
      Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v13);
    }
    Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&pUnk);
    Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v9);
  }
  return v2;
}

```

## disassembly

```asm
0x180017890  push    rbp
0x180017892  push    rbx
0x180017893  push    rdi
0x180017894  mov     rbp, rsp
0x180017897  sub     rsp, 50h
0x18001789b  mov     rbx, rcx
0x18001789e  xor     edi, edi
0x1800178a0  lea     edx, [rdi+1]
0x1800178a3  call    ?TransitionToState@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x1800178a8  cmp     [rbx+88h], edi
0x1800178ae  jle     loc_180017A21
0x1800178b4  mov     eax, edx
0x1800178b6  lock xadd [rbx+10h], eax
0x1800178bb  inc     eax
0x1800178bd  cmp     eax, edx
0x1800178bf  jnz     loc_180017A21
0x1800178c5  mov     [rbp+var_20], rbx
0x1800178c9  lea     rcx, [rbp+var_20]
0x1800178cd  call    ?InternalAddRef@?$ComPtr@UIAsyncFireCompletion@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(void)
0x1800178d2  nop
0x1800178d3  mov     [rbp+pUnk], rdi
0x1800178d7  mov     rcx, rbx
0x1800178da  call    ?TraceOperationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x1800178df  lea     rdx, [rbp+pUnk]
0x1800178e3  lea     rcx, [rbp+var_20]
0x1800178e7  call    ??$As@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<HSTRING__ *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<HSTRING__ *>>>)
0x1800178ec  test    eax, eax
0x1800178ee  js      loc_180017A0E
0x1800178f4  mov     [rbp+arg_0], 0FFFFFFFEh
0x1800178fb  mov     ecx, [rbx+38h]
0x1800178fe  mov     eax, [rbp+arg_0]
0x180017901  lock cmpxchg [rbp+arg_0], ecx
0x180017906  mov     [rbp+arg_8], rdi
0x18001790a  lea     rcx, [rbp+arg_8]
0x18001790e  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180017913  lea     rcx, [rbx+78h]
0x180017917  lea     r8, [rbp+arg_8]
0x18001791b  call    ?CopyLocal@?$GitPtrSupportsAgile@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>>::CopyLocal(_GUID const &,void * *)
0x180017920  test    eax, eax
0x180017922  js      loc_180017A04
0x180017928  mov     rcx, rbx
0x18001792b  call    ?TraceCompletionNotificationStart@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(void)
0x180017930  mov     [rbp+arg_10], rdi
0x180017934  lea     rcx, [rbp+arg_10]
0x180017938  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18001793d  lea     r8, [rbp+arg_10]; struct IRpcOptions **
0x180017941  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x180017945  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x18001794a  mov     [rbp+ppstm], rdi
0x18001794e  mov     [rbp+var_10], edi
0x180017951  cmp     [rbp+arg_10], rdi
0x180017955  jz      short loc_1800179AF
0x180017957  cmp     [rbp+arg_8], rdi
0x18001795b  jz      short loc_1800179AF
0x18001795d  mov     rdi, [rbp+pUnk]
0x180017961  lea     rcx, [rbp+ppstm]
0x180017965  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18001796a  lea     r8, [rbp+ppstm]; ppstm
0x18001796e  mov     edx, 1; fDeleteOnRelease
0x180017973  xor     ecx, ecx; hGlobal
0x180017975  call    cs:__imp_CreateStreamOnHGlobal
0x18001797b  mov     [rbp+var_10], eax
0x18001797e  test    eax, eax
0x180017980  js      short loc_1800179B6
0x180017982  mov     [rsp+50h+mshlflags], 1; mshlflags
0x18001798a  mov     [rsp+50h+pvDestContext], 0; pvDestContext
0x180017993  xor     r9d, r9d; dwDestContext
0x180017996  mov     r8, rdi; pUnk
0x180017999  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x1800179a0  mov     rcx, [rbp+ppstm]; pStm
0x1800179a4  call    cs:__imp_CoMarshalInterface
0x1800179aa  mov     [rbp+var_10], eax
0x1800179ad  jmp     short loc_1800179B6
0x1800179af  mov     [rbp+var_10], 80004002h
0x1800179b6  mov     rcx, [rbp+arg_8]
0x1800179ba  mov     rax, [rcx]
0x1800179bd  mov     r8d, [rbp+arg_0]
0x1800179c1  mov     rdx, [rbp+pUnk]
0x1800179c5  mov     rax, [rax+18h]
0x1800179c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800179ce  mov     r8, [rbx+80h]
0x1800179d5  mov     rdx, [rbp+arg_8]
0x1800179d9  mov     ecx, eax
0x1800179db  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x1800179e0  mov     edi, eax
0x1800179e2  mov     rcx, rbx
0x1800179e5  call    ?UnlockCompleteDelegate@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(void)
0x1800179ea  call    ?TraceCompletionNotificationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(void)
0x1800179ef  nop
0x1800179f0  lea     rcx, [rbp+ppstm]
0x1800179f4  call    ??1?$AutoStubBias@UIUnknown@@UINilDelegate@Internal@Windows@@@@QEAA@XZ; AutoStubBias<IUnknown,Windows::Internal::INilDelegate>::~AutoStubBias<IUnknown,Windows::Internal::INilDelegate>(void)
0x1800179f9  nop
0x1800179fa  lea     rcx, [rbp+arg_10]
0x1800179fe  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180017a03  nop
0x180017a04  lea     rcx, [rbp+arg_8]
0x180017a08  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180017a0d  nop
0x180017a0e  lea     rcx, [rbp+pUnk]
0x180017a12  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180017a17  nop
0x180017a18  lea     rcx, [rbp+var_20]
0x180017a1c  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180017a21  mov     eax, edi
0x180017a23  add     rsp, 50h
0x180017a27  pop     rdi
0x180017a28  pop     rbx
0x180017a29  pop     rbp
0x180017a2a  retn
```
