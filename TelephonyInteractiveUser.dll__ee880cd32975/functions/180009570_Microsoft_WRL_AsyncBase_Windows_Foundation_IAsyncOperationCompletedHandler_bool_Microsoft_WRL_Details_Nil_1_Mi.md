# Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::FireCompletion

- ea: `0x180009570`
- end: `0x18000970f`
- name: `Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::FireCompletion`
- size: `415`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001dc0`
- `0x180009570`
- `0x18000a0f4`
- `0x18000f588`
- `0x18000f698`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::FireCompletion(
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
  Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::TransitionToState(
    a1,
    1);
  if ( *(_QWORD *)(a1 + 24) && !_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 16), v3, 0) )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
    v12 = 0;
    Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::TraceOperationComplete(a1);
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
0x180009570  push    rbp
0x180009572  push    rbx
0x180009573  push    rsi
0x180009574  push    rdi
0x180009575  mov     rbp, rsp
0x180009578  sub     rsp, 78h
0x18000957c  mov     rax, cs:__security_cookie
0x180009583  xor     rax, rsp
0x180009586  mov     [rbp+var_18], rax
0x18000958a  xor     edi, edi
0x18000958c  mov     rbx, rcx
0x18000958f  lea     edx, [rdi+1]
0x180009592  call    Microsoft__WRL__AsyncBase_Windows__Foundation__IAsyncOperationCompletedHandler_bool__Microsoft__WRL__Details__Nil_1_Microsoft__WRL__AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2_____TransitionToState
0x180009597  cmp     [rbx+18h], rdi
0x18000959b  jz      loc_1800096F8
0x1800095a1  xor     eax, eax
0x1800095a3  lock cmpxchg [rbx+10h], edx
0x1800095a8  jnz     loc_1800096F8
0x1800095ae  mov     rax, [rbx]
0x1800095b1  mov     rcx, rbx
0x1800095b4  mov     rax, [rax+8]
0x1800095b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095bd  mov     rcx, rbx
0x1800095c0  mov     [rbp+var_20], rdi
0x1800095c4  call    Microsoft__WRL__AsyncBase_Windows__Foundation__IAsyncOperationCompletedHandler_bool__Microsoft__WRL__Details__Nil_1_Microsoft__WRL__AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2_____TraceOperationComplete
0x1800095c9  mov     rax, [rbx]
0x1800095cc  mov     rdx, [rbp+var_20]
0x1800095d0  mov     rsi, [rax]
0x1800095d3  test    rdx, rdx
0x1800095d6  jz      short loc_1800095EB
0x1800095d8  mov     [rbp+var_20], rdi
0x1800095dc  mov     rcx, [rdx]
0x1800095df  mov     rax, [rcx+10h]
0x1800095e3  mov     rcx, rdx
0x1800095e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095eb  lea     r8, [rbp+var_20]
0x1800095ef  mov     rcx, rbx
0x1800095f2  lea     rdx, _GUID_cdb5efb3_5788_509d_9be1_71ccb8a3362a
0x1800095f9  mov     rax, rsi
0x1800095fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009601  test    eax, eax
0x180009603  js      loc_1800096CC
0x180009609  mov     ecx, [rbx+38h]
0x18000960c  mov     [rbp+var_28], 0FFFFFFFEh
0x180009613  mov     eax, [rbp+var_28]
0x180009616  lock cmpxchg [rbp+var_28], ecx
0x18000961b  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180009622  mov     esi, 2
0x180009627  test    rcx, rcx
0x18000962a  jz      short loc_180009656
0x18000962c  mov     rax, [rcx]
0x18000962f  lea     r9, [rbp+var_38]
0x180009633  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x18000963a  mov     [rsp+78h+var_50], edi
0x18000963e  mov     r8d, esi
0x180009641  xor     edx, edx
0x180009643  mov     [rsp+78h+var_58], rbx
0x180009648  mov     rax, [rax+48h]
0x18000964c  movdqu  [rbp+var_38], xmm0
0x180009651  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009656  mov     rcx, [rbx+18h]
0x18000965a  mov     r8d, [rbp+var_28]
0x18000965e  mov     rdx, [rbp+var_20]
0x180009662  mov     rax, [rcx]
0x180009665  mov     rax, [rax+18h]
0x180009669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000966e  mov     r8, [rbx+28h]
0x180009672  mov     ecx, eax
0x180009674  mov     rdx, [rbx+18h]
0x180009678  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x18000967d  mov     edi, eax
0x18000967f  or      ecx, 0FFFFFFFFh
0x180009682  lock xadd [rbx+20h], ecx
0x180009687  cmp     ecx, 1
0x18000968a  jnz     short loc_1800096AC
0x18000968c  mov     rdx, [rbx+18h]
0x180009690  test    rdx, rdx
0x180009693  jz      short loc_1800096AC
0x180009695  mov     qword ptr [rbx+18h], 0
0x18000969d  mov     rcx, [rdx]
0x1800096a0  mov     rax, [rcx+10h]
0x1800096a4  mov     rcx, rdx
0x1800096a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096ac  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x1800096b3  test    rcx, rcx
0x1800096b6  jz      short loc_1800096CC
0x1800096b8  mov     rax, [rcx]
0x1800096bb  xor     r9d, r9d
0x1800096be  mov     r8d, esi
0x1800096c1  xor     edx, edx
0x1800096c3  mov     rax, [rax+50h]
0x1800096c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096cc  mov     rcx, [rbp+var_20]
0x1800096d0  test    rcx, rcx
0x1800096d3  jz      short loc_1800096E9
0x1800096d5  mov     [rbp+var_20], 0
0x1800096dd  mov     rax, [rcx]
0x1800096e0  mov     rax, [rax+10h]
0x1800096e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096e9  mov     rax, [rbx]
0x1800096ec  mov     rcx, rbx
0x1800096ef  mov     rax, [rax+10h]
0x1800096f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096f8  mov     eax, edi
0x1800096fa  mov     rcx, [rbp+var_18]
0x1800096fe  xor     rcx, rsp; StackCookie
0x180009701  call    __security_check_cookie
0x180009706  add     rsp, 78h
0x18000970a  pop     rdi
0x18000970b  pop     rsi
0x18000970c  pop     rbx
0x18000970d  pop     rbp
0x18000970e  retn
```
