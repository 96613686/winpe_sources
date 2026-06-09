# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x180009720`
- end: `0x1800098bf`
- name: `?FireCompletion@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@UEAAJXZ`
- size: `415`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001dc0`
- `0x180009720`
- `0x18000a0f4`
- `0x18000f610`
- `0x18000f720`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
        __int64 a1)
{
  unsigned int v1; // edi
  signed __int32 v3; // edx
  signed __int32 v4; // ecx
  void (__fastcall *v5)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, _QWORD, __int64, GUID *, __int64, _DWORD); // rax
  unsigned int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // rcx
  GUID v10; // [rsp+40h] [rbp-38h] BYREF
  unsigned int v11; // [rsp+50h] [rbp-28h] BYREF
  __int64 v12; // [rsp+58h] [rbp-20h] BYREF

  v1 = 0;
  Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(
    a1,
    1);
  if ( *(_QWORD *)(a1 + 24) && !_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 16), v3, 0) )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
    v12 = 0;
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(a1);
    if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))a1)(a1, &GUID_cdb5efb3_5788_509d_9be1_71ccb8a3362a, &v12) >= 0 )
    {
      v4 = *(_DWORD *)(a1 + 56);
      v11 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v11, v4, -2);
      if ( Microsoft::WRL::gCausality )
      {
        v5 = *(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, _QWORD, __int64, GUID *, __int64, _DWORD))(*(_QWORD *)Microsoft::WRL::gCausality + 72LL);
        v10 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
        v5(Microsoft::WRL::gCausality, 0, 2, &v10, a1, 0);
      }
      v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(a1 + 24) + 24LL))(
             *(_QWORD *)(a1 + 24),
             v12,
             v11);
      v1 = Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(
             v6,
             *(_QWORD *)(a1 + 24),
             *(_QWORD *)(a1 + 40));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 32), 0xFFFFFFFF) == 1 )
      {
        v7 = *(_QWORD *)(a1 + 24);
        if ( v7 )
        {
          *(_QWORD *)(a1 + 24) = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
        }
      }
      if ( Microsoft::WRL::gCausality )
        (*(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, _QWORD, __int64, _QWORD))(*(_QWORD *)Microsoft::WRL::gCausality + 80LL))(
          Microsoft::WRL::gCausality,
          0,
          2,
          0);
    }
    v8 = v12;
    if ( v12 )
    {
      v12 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
  }
  return v1;
}

```

## disassembly

```asm
0x180009720  push    rbp
0x180009722  push    rbx
0x180009723  push    rsi
0x180009724  push    rdi
0x180009725  mov     rbp, rsp
0x180009728  sub     rsp, 78h
0x18000972c  mov     rax, cs:__security_cookie
0x180009733  xor     rax, rsp
0x180009736  mov     [rbp+var_18], rax
0x18000973a  xor     edi, edi
0x18000973c  mov     rbx, rcx
0x18000973f  lea     edx, [rdi+1]
0x180009742  call    ?TransitionToState@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x180009747  cmp     [rbx+18h], rdi
0x18000974b  jz      loc_1800098A8
0x180009751  xor     eax, eax
0x180009753  lock cmpxchg [rbx+10h], edx
0x180009758  jnz     loc_1800098A8
0x18000975e  mov     rax, [rbx]
0x180009761  mov     rcx, rbx
0x180009764  mov     rax, [rax+8]
0x180009768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000976d  mov     rcx, rbx
0x180009770  mov     [rbp+var_20], rdi
0x180009774  call    ?TraceOperationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x180009779  mov     rax, [rbx]
0x18000977c  mov     rdx, [rbp+var_20]
0x180009780  mov     rsi, [rax]
0x180009783  test    rdx, rdx
0x180009786  jz      short loc_18000979B
0x180009788  mov     [rbp+var_20], rdi
0x18000978c  mov     rcx, [rdx]
0x18000978f  mov     rax, [rcx+10h]
0x180009793  mov     rcx, rdx
0x180009796  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000979b  lea     r8, [rbp+var_20]
0x18000979f  mov     rcx, rbx
0x1800097a2  lea     rdx, _GUID_cdb5efb3_5788_509d_9be1_71ccb8a3362a
0x1800097a9  mov     rax, rsi
0x1800097ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097b1  test    eax, eax
0x1800097b3  js      loc_18000987C
0x1800097b9  mov     ecx, [rbx+38h]
0x1800097bc  mov     [rbp+var_28], 0FFFFFFFEh
0x1800097c3  mov     eax, [rbp+var_28]
0x1800097c6  lock cmpxchg [rbp+var_28], ecx
0x1800097cb  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x1800097d2  mov     esi, 2
0x1800097d7  test    rcx, rcx
0x1800097da  jz      short loc_180009806
0x1800097dc  mov     rax, [rcx]
0x1800097df  lea     r9, [rbp+var_38]
0x1800097e3  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x1800097ea  mov     [rsp+78h+var_50], edi
0x1800097ee  mov     r8d, esi
0x1800097f1  xor     edx, edx
0x1800097f3  mov     [rsp+78h+var_58], rbx
0x1800097f8  mov     rax, [rax+48h]
0x1800097fc  movdqu  [rbp+var_38], xmm0
0x180009801  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009806  mov     rcx, [rbx+18h]
0x18000980a  mov     r8d, [rbp+var_28]
0x18000980e  mov     rdx, [rbp+var_20]
0x180009812  mov     rax, [rcx]
0x180009815  mov     rax, [rax+18h]
0x180009819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000981e  mov     r8, [rbx+28h]
0x180009822  mov     ecx, eax
0x180009824  mov     rdx, [rbx+18h]
0x180009828  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x18000982d  mov     edi, eax
0x18000982f  or      ecx, 0FFFFFFFFh
0x180009832  lock xadd [rbx+20h], ecx
0x180009837  cmp     ecx, 1
0x18000983a  jnz     short loc_18000985C
0x18000983c  mov     rdx, [rbx+18h]
0x180009840  test    rdx, rdx
0x180009843  jz      short loc_18000985C
0x180009845  mov     qword ptr [rbx+18h], 0
0x18000984d  mov     rcx, [rdx]
0x180009850  mov     rax, [rcx+10h]
0x180009854  mov     rcx, rdx
0x180009857  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000985c  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180009863  test    rcx, rcx
0x180009866  jz      short loc_18000987C
0x180009868  mov     rax, [rcx]
0x18000986b  xor     r9d, r9d
0x18000986e  mov     r8d, esi
0x180009871  xor     edx, edx
0x180009873  mov     rax, [rax+50h]
0x180009877  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000987c  mov     rcx, [rbp+var_20]
0x180009880  test    rcx, rcx
0x180009883  jz      short loc_180009899
0x180009885  mov     [rbp+var_20], 0
0x18000988d  mov     rax, [rcx]
0x180009890  mov     rax, [rax+10h]
0x180009894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009899  mov     rax, [rbx]
0x18000989c  mov     rcx, rbx
0x18000989f  mov     rax, [rax+10h]
0x1800098a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098a8  mov     eax, edi
0x1800098aa  mov     rcx, [rbp+var_18]
0x1800098ae  xor     rcx, rsp; StackCookie
0x1800098b1  call    __security_check_cookie
0x1800098b6  add     rsp, 78h
0x1800098ba  pop     rdi
0x1800098bb  pop     rsi
0x1800098bc  pop     rbx
0x1800098bd  pop     rbp
0x1800098be  retn
```
