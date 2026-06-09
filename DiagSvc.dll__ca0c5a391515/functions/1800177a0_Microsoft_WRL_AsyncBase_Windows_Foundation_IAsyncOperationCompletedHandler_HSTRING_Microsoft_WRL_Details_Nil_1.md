# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x1800177a0`
- end: `0x18001787f`
- name: `?FireCompletion@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@UEAAJXZ`
- size: `223`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000517c`
- `0x1800056d8`
- `0x180014150`
- `0x1800177a0`
- `0x180017ab0`
- `0x180019a78`
- `0x180019aa8`
- `0x180019b4c`
- `0x180019c70`
- `0x180027010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
        __int64 a1)
{
  unsigned int v2; // esi
  signed __int32 v3; // edx
  _QWORD *v4; // rdi
  unsigned int v5; // eax
  unsigned int v7; // [rsp+40h] [rbp+20h] BYREF
  __int64 v8; // [rsp+48h] [rbp+28h] BYREF
  __int64 (__fastcall ***v9)(_QWORD, GUID *, __int64); // [rsp+50h] [rbp+30h] BYREF

  v2 = 0;
  Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(a1);
  v4 = (_QWORD *)(a1 + 24);
  if ( *(_QWORD *)(a1 + 24) && !_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 16), v3, 0) )
  {
    v9 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))a1;
    Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(&v9);
    v8 = 0;
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(a1);
    if ( (int)Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<HSTRING__ *>>(
                &v9,
                (__int64)&v8) >= 0 )
    {
      v7 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v7, *(_DWORD *)(a1 + 56), -2);
      Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(a1);
      v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(*(_QWORD *)*v4 + 24LL))(*v4, v8, v7);
      v2 = Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(
             v5,
             *v4,
             *(_QWORD *)(a1 + 40));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 32), 0xFFFFFFFF) == 1 )
        Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease((__int64 *)(a1 + 24));
      Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete();
    }
    Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v8);
    Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease((__int64 *)&v9);
  }
  return v2;
}

```

## disassembly

```asm
0x1800177a0  mov     [rsp-18h+arg_18], rbx
0x1800177a5  push    rbp
0x1800177a6  push    rsi
0x1800177a7  push    rdi
0x1800177a8  mov     rbp, rsp
0x1800177ab  sub     rsp, 20h
0x1800177af  mov     rbx, rcx
0x1800177b2  xor     esi, esi
0x1800177b4  lea     edx, [rsi+1]
0x1800177b7  call    ?TransitionToState@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x1800177bc  lea     rdi, [rbx+18h]
0x1800177c0  cmp     [rdi], rsi
0x1800177c3  jz      loc_180017870
0x1800177c9  xor     eax, eax
0x1800177cb  lock cmpxchg [rbx+10h], edx
0x1800177d0  jnz     loc_180017870
0x1800177d6  mov     [rbp+arg_10], rbx
0x1800177da  lea     rcx, [rbp+arg_10]
0x1800177de  call    ?InternalAddRef@?$ComPtr@UIAsyncFireCompletion@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(void)
0x1800177e3  nop
0x1800177e4  mov     [rbp+arg_8], rsi
0x1800177e8  mov     rcx, rbx
0x1800177eb  call    ?TraceOperationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x1800177f0  lea     rdx, [rbp+arg_8]
0x1800177f4  lea     rcx, [rbp+arg_10]
0x1800177f8  call    ??$As@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<HSTRING__ *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<HSTRING__ *>>>)
0x1800177fd  test    eax, eax
0x1800177ff  js      short loc_18001785D
0x180017801  mov     [rbp+arg_0], 0FFFFFFFEh
0x180017808  mov     ecx, [rbx+38h]
0x18001780b  mov     eax, [rbp+arg_0]
0x18001780e  lock cmpxchg [rbp+arg_0], ecx
0x180017813  mov     rcx, rbx
0x180017816  call    ?TraceCompletionNotificationStart@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(void)
0x18001781b  mov     rcx, [rdi]
0x18001781e  mov     rax, [rcx]
0x180017821  mov     r8d, [rbp+arg_0]
0x180017825  mov     rdx, [rbp+arg_8]
0x180017829  mov     rax, [rax+18h]
0x18001782d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017832  mov     r8, [rbx+28h]
0x180017836  mov     rdx, [rdi]
0x180017839  mov     ecx, eax
0x18001783b  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x180017840  mov     esi, eax
0x180017842  or      edx, 0FFFFFFFFh
0x180017845  lock xadd [rbx+20h], edx
0x18001784a  cmp     edx, 1
0x18001784d  jnz     short loc_180017857
0x18001784f  mov     rcx, rdi
0x180017852  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180017857  call    ?TraceCompletionNotificationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(void)
0x18001785c  nop
0x18001785d  lea     rcx, [rbp+arg_8]
0x180017861  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180017866  nop
0x180017867  lea     rcx, [rbp+arg_10]
0x18001786b  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180017870  mov     eax, esi
0x180017872  mov     rbx, [rsp+20h+arg_18]
0x180017877  add     rsp, 20h
0x18001787b  pop     rdi
0x18001787c  pop     rsi
0x18001787d  pop     rbp
0x18001787e  retn
```
