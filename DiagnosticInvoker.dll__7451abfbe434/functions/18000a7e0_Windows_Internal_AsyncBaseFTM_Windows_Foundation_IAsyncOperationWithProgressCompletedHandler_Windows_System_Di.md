# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x18000a7e0`
- end: `0x18000ab04`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `804`
- prototype: `__int64 __fastcall(signed __int32 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000ab10`
- `0x18000c800`
- `0x18000e7fc`

## callees

- `0x18000a7e0`
- `0x18000ad58`
- `0x18000c2a4`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18000a997`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18000a997`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x18000aa71`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x18000aa71`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18000a9bf`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18000a9bf`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
        signed __int32 *a1)
{
  unsigned int v2; // esi
  LPUNKNOWN v3; // rcx
  int (__fastcall *v4)(signed __int32 *, GUID *, LPUNKNOWN *); // rdi
  __int64 v5; // rcx
  IUnknown *v6; // rdi
  unsigned int v7; // eax
  __int64 v8; // rcx
  LPSTREAM v9; // rcx
  struct IRpcOptions *v10; // rcx
  struct IUnknown *v11; // rcx
  LPUNKNOWN v12; // rcx
  signed __int32 v14[8]; // [rsp+0h] [rbp-78h] BYREF
  signed __int32 *v15; // [rsp+40h] [rbp-38h]
  LPSTREAM ppstm[2]; // [rsp+50h] [rbp-28h] BYREF
  GUID v17; // [rsp+60h] [rbp-18h] BYREF
  unsigned int v18; // [rsp+B0h] [rbp+38h] BYREF
  struct IUnknown *v19; // [rsp+B8h] [rbp+40h] BYREF
  LPUNKNOWN pUnk; // [rsp+C0h] [rbp+48h] BYREF
  struct IRpcOptions *v21; // [rsp+C8h] [rbp+50h] BYREF

  v2 = 0;
  v18 = -2;
  _InterlockedCompareExchange((volatile signed __int32 *)&v18, a1[14], -2);
  if ( !v18 )
    _InterlockedCompareExchange(a1 + 14, 1, 0);
  if ( a1[34] > 0 && _InterlockedIncrement(a1 + 4) == 1 )
  {
    v15 = a1;
    if ( a1 )
      (*(void (__fastcall **)(signed __int32 *))(*(_QWORD *)a1 + 8LL))(a1);
    v3 = 0;
    pUnk = 0;
    if ( Microsoft::WRL::gCausality )
    {
      v18 = 0;
      _InterlockedCompareExchange((volatile signed __int32 *)&v18, a1[14], 0);
      *(GUID *)ppstm = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
      (*(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, _QWORD, __int64, LPSTREAM *, signed __int32 *, unsigned int))(*(_QWORD *)Microsoft::WRL::gCausality + 56LL))(
        Microsoft::WRL::gCausality,
        0,
        2,
        ppstm,
        a1,
        v18);
      v3 = pUnk;
    }
    v4 = **(int (__fastcall ***)(signed __int32 *, GUID *, LPUNKNOWN *))a1;
    if ( v3 )
    {
      pUnk = 0;
      ((void (__fastcall *)(LPUNKNOWN))v3->lpVtbl->Release)(v3);
    }
    if ( v4(a1, &GUID_bb5d493e_74e9_57a1_8c4c_923e0dc4565b, &pUnk) >= 0 )
    {
      v18 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v18, a1[14], -2);
      v5 = *((_QWORD *)a1 + 15);
      if ( v5 )
      {
        v19 = 0;
        if ( (*(int (__fastcall **)(__int64, GUID *, struct IUnknown **))(*(_QWORD *)v5 + 24LL))(
               v5,
               &GUID_390b0091_caf7_5b64_839d_4990ae7f753c,
               &v19) >= 0 )
        {
          if ( Microsoft::WRL::gCausality )
          {
            v17 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
            (*(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, _QWORD, __int64, GUID *, signed __int32 *, _DWORD))(*(_QWORD *)Microsoft::WRL::gCausality + 72LL))(
              Microsoft::WRL::gCausality,
              0,
              2,
              &v17,
              a1,
              0);
          }
          v21 = 0;
          RpcOptionsHelper::GetRpcOptions(v19, &v21);
          ppstm[0] = 0;
          LODWORD(ppstm[1]) = 0;
          if ( v21 && v19 )
          {
            v6 = pUnk;
            LODWORD(ppstm[1]) = CreateStreamOnHGlobal(0, 1, ppstm);
            if ( SLODWORD(ppstm[1]) >= 0 )
              LODWORD(ppstm[1]) = CoMarshalInterface(ppstm[0], &GUID_00000000_0000_0000_c000_000000000046, v6, 0, 0, 1u);
          }
          else
          {
            LODWORD(ppstm[1]) = -2147467262;
          }
          v7 = ((__int64 (__fastcall *)(struct IUnknown *, LPUNKNOWN, _QWORD))v19->lpVtbl[1].QueryInterface)(
                 v19,
                 pUnk,
                 v18);
          v2 = Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(
                 v7,
                 v19,
                 *((_QWORD *)a1 + 16));
          if ( _InterlockedExchangeAdd(a1 + 34, 0xFFFFFFFF) == 1 )
          {
            _InterlockedOr(v14, 0);
            v8 = *((_QWORD *)a1 + 15);
            *((_QWORD *)a1 + 15) = 0;
            if ( v8 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
          }
          if ( Microsoft::WRL::gCausality )
            (*(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, _QWORD, __int64))(*(_QWORD *)Microsoft::WRL::gCausality + 80LL))(
              Microsoft::WRL::gCausality,
              0,
              2);
          if ( SLODWORD(ppstm[1]) >= 0 )
          {
            (*(void (__fastcall **)(LPSTREAM, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppstm[0] + 40LL))(ppstm[0], 0, 0, 0);
            CoReleaseMarshalData(ppstm[0]);
          }
          v9 = ppstm[0];
          if ( ppstm[0] )
          {
            ppstm[0] = 0;
            (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)v9 + 16LL))(v9);
          }
          v10 = v21;
          if ( v21 )
          {
            v21 = 0;
            ((void (__fastcall *)(struct IRpcOptions *))v10->lpVtbl->Release)(v10);
          }
        }
        v11 = v19;
      }
      else
      {
        v11 = 0;
      }
      if ( v11 )
      {
        v19 = 0;
        ((void (__fastcall *)(struct IUnknown *))v11->lpVtbl->Release)(v11);
      }
    }
    v12 = pUnk;
    if ( pUnk )
    {
      pUnk = 0;
      ((void (__fastcall *)(LPUNKNOWN))v12->lpVtbl->Release)(v12);
    }
    (*(void (__fastcall **)(signed __int32 *))(*(_QWORD *)a1 + 16LL))(a1);
  }
  return v2;
}

```

## disassembly

```asm
0x18000a7e0  push    rbp
0x18000a7e2  push    rbx
0x18000a7e3  push    rsi
0x18000a7e4  push    rdi
0x18000a7e5  push    r14
0x18000a7e7  push    r15
0x18000a7e9  mov     rbp, rsp
0x18000a7ec  sub     rsp, 78h
0x18000a7f0  mov     rbx, rcx
0x18000a7f3  xor     r14d, r14d
0x18000a7f6  mov     esi, r14d
0x18000a7f9  mov     [rbp+arg_0], 0FFFFFFFEh
0x18000a800  mov     edx, [rcx+38h]
0x18000a803  mov     eax, [rbp+arg_0]
0x18000a806  lock cmpxchg [rbp+arg_0], edx
0x18000a80b  lea     r15d, [r14+1]
0x18000a80f  cmp     [rbp+arg_0], r14d
0x18000a813  jnz     short loc_18000A81D
0x18000a815  xor     eax, eax
0x18000a817  lock cmpxchg [rcx+38h], r15d
0x18000a81d  cmp     [rcx+88h], r14d
0x18000a824  jle     loc_18000AAF5
0x18000a82a  mov     eax, r15d
0x18000a82d  lock xadd [rcx+10h], eax
0x18000a832  add     eax, r15d
0x18000a835  cmp     eax, r15d
0x18000a838  jnz     loc_18000AAF5
0x18000a83e  mov     [rbp+var_38], rbx
0x18000a842  test    rbx, rbx
0x18000a845  jz      short loc_18000A854
0x18000a847  mov     rax, [rcx]
0x18000a84a  mov     rax, [rax+8]
0x18000a84e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a853  nop
0x18000a854  mov     rcx, r14
0x18000a857  mov     [rbp+pUnk], rcx
0x18000a85b  cmp     cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA, r14; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18000a862  jz      short loc_18000A8AF
0x18000a864  mov     [rbp+arg_0], r14d
0x18000a868  mov     ecx, [rbx+38h]
0x18000a86b  mov     eax, [rbp+arg_0]
0x18000a86e  lock cmpxchg [rbp+arg_0], ecx
0x18000a873  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x18000a87a  movdqu  xmmword ptr [rbp+ppstm], xmm0
0x18000a87f  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18000a886  mov     rax, [rcx]
0x18000a889  mov     r10, [rax+38h]
0x18000a88d  mov     eax, [rbp+arg_0]
0x18000a890  mov     [rsp+78h+mshlflags], eax
0x18000a894  mov     [rsp+78h+pvDestContext], rbx
0x18000a899  lea     r9, [rbp+ppstm]
0x18000a89d  xor     edx, edx
0x18000a89f  lea     r8d, [rdx+2]
0x18000a8a3  mov     rax, r10
0x18000a8a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8ab  mov     rcx, [rbp+pUnk]
0x18000a8af  mov     rax, [rbx]
0x18000a8b2  mov     rdi, [rax]
0x18000a8b5  test    rcx, rcx
0x18000a8b8  jz      short loc_18000A8CB
0x18000a8ba  mov     [rbp+pUnk], r14
0x18000a8be  mov     rax, [rcx]
0x18000a8c1  mov     rax, [rax+10h]
0x18000a8c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8ca  nop
0x18000a8cb  lea     r8, [rbp+pUnk]
0x18000a8cf  lea     rdx, _GUID_bb5d493e_74e9_57a1_8c4c_923e0dc4565b
0x18000a8d6  mov     rcx, rbx
0x18000a8d9  mov     rax, rdi
0x18000a8dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8e1  nop
0x18000a8e2  test    eax, eax
0x18000a8e4  js      loc_18000AACB
0x18000a8ea  mov     [rbp+arg_0], 0FFFFFFFEh
0x18000a8f1  mov     ecx, [rbx+38h]
0x18000a8f4  mov     eax, [rbp+arg_0]
0x18000a8f7  lock cmpxchg [rbp+arg_0], ecx
0x18000a8fc  mov     rcx, [rbx+78h]
0x18000a900  test    rcx, rcx
0x18000a903  jz      loc_18000AAB2
0x18000a909  mov     [rbp+arg_8], r14
0x18000a90d  mov     rax, [rcx]
0x18000a910  lea     r8, [rbp+arg_8]
0x18000a914  lea     rdx, _GUID_390b0091_caf7_5b64_839d_4990ae7f753c
0x18000a91b  mov     rax, [rax+18h]
0x18000a91f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a924  nop
0x18000a925  test    eax, eax
0x18000a927  js      loc_18000AAAC
0x18000a92d  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18000a934  test    rcx, rcx
0x18000a937  jz      short loc_18000A965
0x18000a939  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x18000a940  movdqu  xmmword ptr [rbp+var_18.Data1], xmm0
0x18000a945  mov     rax, [rcx]
0x18000a948  mov     [rsp+78h+mshlflags], r14d
0x18000a94d  mov     [rsp+78h+pvDestContext], rbx
0x18000a952  lea     r9, [rbp+var_18]
0x18000a956  xor     edx, edx
0x18000a958  lea     r8d, [rdx+2]
0x18000a95c  mov     rax, [rax+48h]
0x18000a960  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a965  mov     [rbp+arg_18], r14
0x18000a969  lea     rdx, [rbp+arg_18]; struct IRpcOptions **
0x18000a96d  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x18000a971  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@PEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,IRpcOptions * *)
0x18000a976  mov     [rbp+ppstm], r14
0x18000a97a  mov     dword ptr [rbp+ppstm+8], r14d
0x18000a97e  cmp     [rbp+arg_18], r14
0x18000a982  jz      short loc_18000A9CA
0x18000a984  cmp     [rbp+arg_8], r14
0x18000a988  jz      short loc_18000A9CA
0x18000a98a  mov     rdi, [rbp+pUnk]
0x18000a98e  lea     r8, [rbp+ppstm]; ppstm
0x18000a992  mov     edx, r15d; fDeleteOnRelease
0x18000a995  xor     ecx, ecx; hGlobal
0x18000a997  call    cs:__imp_CreateStreamOnHGlobal
0x18000a99d  mov     dword ptr [rbp+ppstm+8], eax
0x18000a9a0  test    eax, eax
0x18000a9a2  js      short loc_18000A9D1
0x18000a9a4  mov     [rsp+78h+mshlflags], r15d; mshlflags
0x18000a9a9  mov     [rsp+78h+pvDestContext], r14; pvDestContext
0x18000a9ae  xor     r9d, r9d; dwDestContext
0x18000a9b1  mov     r8, rdi; pUnk
0x18000a9b4  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18000a9bb  mov     rcx, [rbp+ppstm]; pStm
0x18000a9bf  call    cs:__imp_CoMarshalInterface
0x18000a9c5  mov     dword ptr [rbp+ppstm+8], eax
0x18000a9c8  jmp     short loc_18000A9D1
0x18000a9ca  mov     dword ptr [rbp+ppstm+8], 80004002h
0x18000a9d1  mov     rcx, [rbp+arg_8]
0x18000a9d5  mov     rax, [rcx]
0x18000a9d8  mov     r8d, [rbp+arg_0]
0x18000a9dc  mov     rdx, [rbp+pUnk]
0x18000a9e0  mov     rax, [rax+18h]
0x18000a9e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9e9  mov     r8, [rbx+80h]
0x18000a9f0  mov     rdx, [rbp+arg_8]
0x18000a9f4  mov     ecx, eax
0x18000a9f6  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x18000a9fb  mov     esi, eax
0x18000a9fd  or      ecx, 0FFFFFFFFh
0x18000aa00  lock xadd [rbx+88h], ecx
0x18000aa08  cmp     ecx, 1
0x18000aa0b  jnz     short loc_18000AA2C
0x18000aa0d  lock or [rsp+78h+var_78], r14d
0x18000aa12  mov     rcx, [rbx+78h]
0x18000aa16  mov     [rbx+78h], r14
0x18000aa1a  test    rcx, rcx
0x18000aa1d  jz      short loc_18000AA2C
0x18000aa1f  mov     rax, [rcx]
0x18000aa22  mov     rax, [rax+10h]
0x18000aa26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa2b  nop
0x18000aa2c  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18000aa33  test    rcx, rcx
0x18000aa36  jz      short loc_18000AA4E
0x18000aa38  mov     rax, [rcx]
0x18000aa3b  xor     r9d, r9d
0x18000aa3e  xor     edx, edx
0x18000aa40  lea     r8d, [r9+2]
0x18000aa44  mov     rax, [rax+50h]
0x18000aa48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa4d  nop
0x18000aa4e  cmp     dword ptr [rbp+ppstm+8], r14d
0x18000aa52  jl      short loc_18000AA78
0x18000aa54  mov     rcx, [rbp+ppstm]
0x18000aa58  mov     rdx, r14
0x18000aa5b  mov     rax, [rcx]
0x18000aa5e  xor     r9d, r9d
0x18000aa61  xor     r8d, r8d
0x18000aa64  mov     rax, [rax+28h]
0x18000aa68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa6d  mov     rcx, [rbp+ppstm]; pStm
0x18000aa71  call    cs:__imp_CoReleaseMarshalData
0x18000aa77  nop
0x18000aa78  mov     rcx, [rbp+ppstm]
0x18000aa7c  test    rcx, rcx
0x18000aa7f  jz      short loc_18000AA92
0x18000aa81  mov     [rbp+ppstm], r14
0x18000aa85  mov     rax, [rcx]
0x18000aa88  mov     rax, [rax+10h]
0x18000aa8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa91  nop
0x18000aa92  mov     rcx, [rbp+arg_18]
0x18000aa96  test    rcx, rcx
0x18000aa99  jz      short loc_18000AAAC
0x18000aa9b  mov     [rbp+arg_18], r14
0x18000aa9f  mov     rax, [rcx]
0x18000aaa2  mov     rax, [rax+10h]
0x18000aaa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aaab  nop
0x18000aaac  mov     rcx, [rbp+arg_8]
0x18000aab0  jmp     short loc_18000AAB5
0x18000aab2  mov     rcx, r14
0x18000aab5  test    rcx, rcx
0x18000aab8  jz      short loc_18000AACB
0x18000aaba  mov     [rbp+arg_8], r14
0x18000aabe  mov     rax, [rcx]
0x18000aac1  mov     rax, [rax+10h]
0x18000aac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aaca  nop
0x18000aacb  mov     rcx, [rbp+pUnk]
0x18000aacf  test    rcx, rcx
0x18000aad2  jz      short loc_18000AAE5
0x18000aad4  mov     [rbp+pUnk], r14
0x18000aad8  mov     rax, [rcx]
0x18000aadb  mov     rax, [rax+10h]
0x18000aadf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aae4  nop
0x18000aae5  mov     rax, [rbx]
0x18000aae8  mov     rcx, rbx
0x18000aaeb  mov     rax, [rax+10h]
0x18000aaef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aaf4  nop
0x18000aaf5  mov     eax, esi
0x18000aaf7  add     rsp, 78h
0x18000aafb  pop     r15
0x18000aafd  pop     r14
0x18000aaff  pop     rdi
0x18000ab00  pop     rsi
0x18000ab01  pop     rbx
0x18000ab02  pop     rbp
0x18000ab03  retn
```
