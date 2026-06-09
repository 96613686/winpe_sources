# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x18000a5e0`
- end: `0x18000a7d8`
- name: `?FireCompletion@?$AsyncBase@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@UEAAJXZ`
- size: `504`
- prototype: `__int64 __fastcall(signed __int32 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000a5e0`
- `0x18000ad58`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
        signed __int32 *a1)
{
  unsigned int v2; // edi
  __int64 v3; // rcx
  int (__fastcall *v4)(signed __int32 *, GUID *, __int64 *); // rsi
  unsigned int v5; // eax
  __int64 v6; // rcx
  __int64 v7; // rcx
  GUID v9; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v10; // [rsp+70h] [rbp+20h] BYREF
  __int64 v11; // [rsp+78h] [rbp+28h] BYREF
  signed __int32 *v12; // [rsp+80h] [rbp+30h]

  v2 = 0;
  v10 = -2;
  _InterlockedCompareExchange((volatile signed __int32 *)&v10, a1[14], -2);
  if ( !v10 )
    _InterlockedCompareExchange(a1 + 14, 1, 0);
  if ( *((_QWORD *)a1 + 3) && !_InterlockedCompareExchange(a1 + 4, 1, 0) )
  {
    v12 = a1;
    (*(void (__fastcall **)(signed __int32 *))(*(_QWORD *)a1 + 8LL))(a1);
    v3 = 0;
    v11 = 0;
    if ( Microsoft::WRL::gCausality )
    {
      v10 = 0;
      _InterlockedCompareExchange((volatile signed __int32 *)&v10, a1[14], 0);
      v9 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
      (*(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, _QWORD, __int64, GUID *, signed __int32 *, unsigned int))(*(_QWORD *)Microsoft::WRL::gCausality + 56LL))(
        Microsoft::WRL::gCausality,
        0,
        2,
        &v9,
        a1,
        v10);
      v3 = v11;
    }
    v4 = **(int (__fastcall ***)(signed __int32 *, GUID *, __int64 *))a1;
    if ( v3 )
    {
      v11 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    }
    if ( v4(a1, &GUID_bb5d493e_74e9_57a1_8c4c_923e0dc4565b, &v11) >= 0 )
    {
      v10 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v10, a1[14], -2);
      if ( Microsoft::WRL::gCausality )
      {
        v9 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
        (*(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, _QWORD, __int64, GUID *, signed __int32 *, _DWORD))(*(_QWORD *)Microsoft::WRL::gCausality + 72LL))(
          Microsoft::WRL::gCausality,
          0,
          2,
          &v9,
          a1,
          0);
      }
      v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)a1 + 3) + 24LL))(
             *((_QWORD *)a1 + 3),
             v11,
             v10);
      v2 = Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(
             v5,
             *((_QWORD *)a1 + 3),
             *((_QWORD *)a1 + 5));
      if ( _InterlockedExchangeAdd(a1 + 8, 0xFFFFFFFF) == 1 )
      {
        v6 = *((_QWORD *)a1 + 3);
        if ( v6 )
        {
          *((_QWORD *)a1 + 3) = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
        }
      }
      if ( Microsoft::WRL::gCausality )
        (*(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, _QWORD, __int64))(*(_QWORD *)Microsoft::WRL::gCausality + 80LL))(
          Microsoft::WRL::gCausality,
          0,
          2);
    }
    v7 = v11;
    if ( v11 )
    {
      v11 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
    (*(void (__fastcall **)(signed __int32 *))(*(_QWORD *)a1 + 16LL))(a1);
  }
  return v2;
}

```

## disassembly

```asm
0x18000a5e0  mov     [rsp-18h+arg_18], rbx
0x18000a5e5  push    rbp
0x18000a5e6  push    rsi
0x18000a5e7  push    rdi
0x18000a5e8  mov     rbp, rsp
0x18000a5eb  sub     rsp, 50h
0x18000a5ef  mov     rbx, rcx
0x18000a5f2  xor     edi, edi
0x18000a5f4  mov     [rbp+arg_0], 0FFFFFFFEh
0x18000a5fb  mov     edx, [rcx+38h]
0x18000a5fe  mov     eax, [rbp+arg_0]
0x18000a601  lock cmpxchg [rbp+arg_0], edx
0x18000a606  lea     ecx, [rdi+1]
0x18000a609  cmp     [rbp+arg_0], edi
0x18000a60c  jnz     short loc_18000A615
0x18000a60e  xor     eax, eax
0x18000a610  lock cmpxchg [rbx+38h], ecx
0x18000a615  cmp     [rbx+18h], rdi
0x18000a619  jz      loc_18000A7C6
0x18000a61f  xor     eax, eax
0x18000a621  lock cmpxchg [rbx+10h], ecx
0x18000a626  jnz     loc_18000A7C6
0x18000a62c  mov     [rbp+arg_10], rbx
0x18000a630  mov     rax, [rbx]
0x18000a633  mov     rcx, rbx
0x18000a636  mov     rax, [rax+8]
0x18000a63a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a63f  nop
0x18000a640  xor     ecx, ecx
0x18000a642  mov     [rbp+arg_8], rcx
0x18000a646  cmp     cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA, rcx; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18000a64d  jz      short loc_18000A696
0x18000a64f  mov     [rbp+arg_0], ecx
0x18000a652  mov     ecx, [rbx+38h]
0x18000a655  mov     eax, [rbp+arg_0]
0x18000a658  lock cmpxchg [rbp+arg_0], ecx
0x18000a65d  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x18000a664  movdqu  [rbp+var_10], xmm0
0x18000a669  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18000a670  mov     rax, [rcx]
0x18000a673  mov     edx, [rbp+arg_0]
0x18000a676  mov     [rsp+50h+var_28], edx
0x18000a67a  mov     [rsp+50h+var_30], rbx
0x18000a67f  lea     r9, [rbp+var_10]
0x18000a683  xor     edx, edx
0x18000a685  lea     r8d, [rdx+2]
0x18000a689  mov     rax, [rax+38h]
0x18000a68d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a692  mov     rcx, [rbp+arg_8]
0x18000a696  mov     rax, [rbx]
0x18000a699  mov     rsi, [rax]
0x18000a69c  test    rcx, rcx
0x18000a69f  jz      short loc_18000A6B6
0x18000a6a1  mov     [rbp+arg_8], 0
0x18000a6a9  mov     rdx, [rcx]
0x18000a6ac  mov     rax, [rdx+10h]
0x18000a6b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6b5  nop
0x18000a6b6  lea     r8, [rbp+arg_8]
0x18000a6ba  lea     rdx, _GUID_bb5d493e_74e9_57a1_8c4c_923e0dc4565b
0x18000a6c1  mov     rcx, rbx
0x18000a6c4  mov     rax, rsi
0x18000a6c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6cc  nop
0x18000a6cd  test    eax, eax
0x18000a6cf  js      loc_18000A798
0x18000a6d5  mov     [rbp+arg_0], 0FFFFFFFEh
0x18000a6dc  mov     ecx, [rbx+38h]
0x18000a6df  mov     eax, [rbp+arg_0]
0x18000a6e2  lock cmpxchg [rbp+arg_0], ecx
0x18000a6e7  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18000a6ee  test    rcx, rcx
0x18000a6f1  jz      short loc_18000A722
0x18000a6f3  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x18000a6fa  movdqu  [rbp+var_10], xmm0
0x18000a6ff  mov     rax, [rcx]
0x18000a702  mov     [rsp+50h+var_28], 0
0x18000a70a  mov     [rsp+50h+var_30], rbx
0x18000a70f  lea     r9, [rbp+var_10]
0x18000a713  xor     edx, edx
0x18000a715  lea     r8d, [rdx+2]
0x18000a719  mov     rax, [rax+48h]
0x18000a71d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a722  mov     rcx, [rbx+18h]
0x18000a726  mov     rax, [rcx]
0x18000a729  mov     r8d, [rbp+arg_0]
0x18000a72d  mov     rdx, [rbp+arg_8]
0x18000a731  mov     rax, [rax+18h]
0x18000a735  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a73a  mov     r8, [rbx+28h]
0x18000a73e  mov     rdx, [rbx+18h]
0x18000a742  mov     ecx, eax
0x18000a744  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x18000a749  mov     edi, eax
0x18000a74b  or      ecx, 0FFFFFFFFh
0x18000a74e  lock xadd [rbx+20h], ecx
0x18000a753  cmp     ecx, 1
0x18000a756  jnz     short loc_18000A776
0x18000a758  mov     rcx, [rbx+18h]
0x18000a75c  test    rcx, rcx
0x18000a75f  jz      short loc_18000A776
0x18000a761  mov     qword ptr [rbx+18h], 0
0x18000a769  mov     rax, [rcx]
0x18000a76c  mov     rax, [rax+10h]
0x18000a770  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a775  nop
0x18000a776  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18000a77d  test    rcx, rcx
0x18000a780  jz      short loc_18000A798
0x18000a782  mov     rax, [rcx]
0x18000a785  xor     r9d, r9d
0x18000a788  xor     edx, edx
0x18000a78a  lea     r8d, [r9+2]
0x18000a78e  mov     rax, [rax+50h]
0x18000a792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a797  nop
0x18000a798  mov     rcx, [rbp+arg_8]
0x18000a79c  test    rcx, rcx
0x18000a79f  jz      short loc_18000A7B6
0x18000a7a1  mov     [rbp+arg_8], 0
0x18000a7a9  mov     rax, [rcx]
0x18000a7ac  mov     rax, [rax+10h]
0x18000a7b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7b5  nop
0x18000a7b6  mov     rax, [rbx]
0x18000a7b9  mov     rcx, rbx
0x18000a7bc  mov     rax, [rax+10h]
0x18000a7c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7c5  nop
0x18000a7c6  mov     eax, edi
0x18000a7c8  mov     rbx, [rsp+50h+arg_18]
0x18000a7d0  add     rsp, 50h
0x18000a7d4  pop     rdi
0x18000a7d5  pop     rsi
0x18000a7d6  pop     rbp
0x18000a7d7  retn
```
