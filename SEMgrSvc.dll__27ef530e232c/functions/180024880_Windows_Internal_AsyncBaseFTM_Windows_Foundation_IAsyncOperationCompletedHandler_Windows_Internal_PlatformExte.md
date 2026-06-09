# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::IShellActivationResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x180024880`
- end: `0x180024ba4`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAUIShellActivationResult@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `804`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180024bb0`
- `0x180027460`
- `0x18002d7dc`

## callees

- `0x180024880`
- `0x180024df8`
- `0x1800263e4`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180024a5f`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180024a5f`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x180024b11`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x180024b11`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180024a37`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180024a37`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::IShellActivationResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
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
    if ( v4(a1, &GUID_7166eb1a_cced_5493_b8a7_6a13ec300676, &pUnk) >= 0 )
    {
      v18 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v18, a1[14], -2);
      v5 = *((_QWORD *)a1 + 15);
      if ( v5 )
      {
        v19 = 0;
        if ( (*(int (__fastcall **)(__int64, GUID *, struct IUnknown **))(*(_QWORD *)v5 + 24LL))(
               v5,
               &GUID_39ba58cc_84c6_5bfc_91e2_84dde41dc481,
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
0x180024880  push    rbp
0x180024882  push    rbx
0x180024883  push    rsi
0x180024884  push    rdi
0x180024885  push    r14
0x180024887  push    r15
0x180024889  mov     rbp, rsp
0x18002488c  sub     rsp, 78h
0x180024890  mov     rbx, rcx
0x180024893  xor     r14d, r14d
0x180024896  mov     esi, r14d
0x180024899  mov     [rbp+arg_0], 0FFFFFFFEh
0x1800248a0  mov     edx, [rcx+38h]
0x1800248a3  mov     eax, [rbp+arg_0]
0x1800248a6  lock cmpxchg [rbp+arg_0], edx
0x1800248ab  lea     r15d, [r14+1]
0x1800248af  cmp     [rbp+arg_0], r14d
0x1800248b3  jnz     short loc_1800248BD
0x1800248b5  xor     eax, eax
0x1800248b7  lock cmpxchg [rcx+38h], r15d
0x1800248bd  cmp     [rcx+88h], r14d
0x1800248c4  jle     loc_180024B95
0x1800248ca  mov     eax, r15d
0x1800248cd  lock xadd [rcx+10h], eax
0x1800248d2  add     eax, r15d
0x1800248d5  cmp     eax, r15d
0x1800248d8  jnz     loc_180024B95
0x1800248de  mov     [rbp+var_38], rbx
0x1800248e2  test    rbx, rbx
0x1800248e5  jz      short loc_1800248F4
0x1800248e7  mov     rax, [rcx]
0x1800248ea  mov     rax, [rax+8]
0x1800248ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800248f3  nop
0x1800248f4  mov     rcx, r14
0x1800248f7  mov     [rbp+pUnk], rcx
0x1800248fb  cmp     cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA, r14; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180024902  jz      short loc_18002494F
0x180024904  mov     [rbp+arg_0], r14d
0x180024908  mov     ecx, [rbx+38h]
0x18002490b  mov     eax, [rbp+arg_0]
0x18002490e  lock cmpxchg [rbp+arg_0], ecx
0x180024913  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x18002491a  movdqu  xmmword ptr [rbp+ppstm], xmm0
0x18002491f  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180024926  mov     rax, [rcx]
0x180024929  mov     r10, [rax+38h]
0x18002492d  mov     eax, [rbp+arg_0]
0x180024930  mov     [rsp+78h+mshlflags], eax
0x180024934  mov     [rsp+78h+pvDestContext], rbx
0x180024939  lea     r9, [rbp+ppstm]
0x18002493d  xor     edx, edx
0x18002493f  lea     r8d, [rdx+2]
0x180024943  mov     rax, r10
0x180024946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002494b  mov     rcx, [rbp+pUnk]
0x18002494f  mov     rax, [rbx]
0x180024952  mov     rdi, [rax]
0x180024955  test    rcx, rcx
0x180024958  jz      short loc_18002496B
0x18002495a  mov     [rbp+pUnk], r14
0x18002495e  mov     rax, [rcx]
0x180024961  mov     rax, [rax+10h]
0x180024965  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002496a  nop
0x18002496b  lea     r8, [rbp+pUnk]
0x18002496f  lea     rdx, _GUID_7166eb1a_cced_5493_b8a7_6a13ec300676
0x180024976  mov     rcx, rbx
0x180024979  mov     rax, rdi
0x18002497c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024981  nop
0x180024982  test    eax, eax
0x180024984  js      loc_180024B6B
0x18002498a  mov     [rbp+arg_0], 0FFFFFFFEh
0x180024991  mov     ecx, [rbx+38h]
0x180024994  mov     eax, [rbp+arg_0]
0x180024997  lock cmpxchg [rbp+arg_0], ecx
0x18002499c  mov     rcx, [rbx+78h]
0x1800249a0  test    rcx, rcx
0x1800249a3  jz      loc_180024B52
0x1800249a9  mov     [rbp+arg_8], r14
0x1800249ad  mov     rax, [rcx]
0x1800249b0  lea     r8, [rbp+arg_8]
0x1800249b4  lea     rdx, _GUID_39ba58cc_84c6_5bfc_91e2_84dde41dc481
0x1800249bb  mov     rax, [rax+18h]
0x1800249bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800249c4  nop
0x1800249c5  test    eax, eax
0x1800249c7  js      loc_180024B4C
0x1800249cd  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x1800249d4  test    rcx, rcx
0x1800249d7  jz      short loc_180024A05
0x1800249d9  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x1800249e0  movdqu  xmmword ptr [rbp+var_18.Data1], xmm0
0x1800249e5  mov     rax, [rcx]
0x1800249e8  mov     [rsp+78h+mshlflags], r14d
0x1800249ed  mov     [rsp+78h+pvDestContext], rbx
0x1800249f2  lea     r9, [rbp+var_18]
0x1800249f6  xor     edx, edx
0x1800249f8  lea     r8d, [rdx+2]
0x1800249fc  mov     rax, [rax+48h]
0x180024a00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a05  mov     [rbp+arg_18], r14
0x180024a09  lea     rdx, [rbp+arg_18]; struct IRpcOptions **
0x180024a0d  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x180024a11  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@PEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,IRpcOptions * *)
0x180024a16  mov     [rbp+ppstm], r14
0x180024a1a  mov     dword ptr [rbp+ppstm+8], r14d
0x180024a1e  cmp     [rbp+arg_18], r14
0x180024a22  jz      short loc_180024A6A
0x180024a24  cmp     [rbp+arg_8], r14
0x180024a28  jz      short loc_180024A6A
0x180024a2a  mov     rdi, [rbp+pUnk]
0x180024a2e  lea     r8, [rbp+ppstm]; ppstm
0x180024a32  mov     edx, r15d; fDeleteOnRelease
0x180024a35  xor     ecx, ecx; hGlobal
0x180024a37  call    cs:__imp_CreateStreamOnHGlobal
0x180024a3d  mov     dword ptr [rbp+ppstm+8], eax
0x180024a40  test    eax, eax
0x180024a42  js      short loc_180024A71
0x180024a44  mov     [rsp+78h+mshlflags], r15d; mshlflags
0x180024a49  mov     [rsp+78h+pvDestContext], r14; pvDestContext
0x180024a4e  xor     r9d, r9d; dwDestContext
0x180024a51  mov     r8, rdi; pUnk
0x180024a54  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180024a5b  mov     rcx, [rbp+ppstm]; pStm
0x180024a5f  call    cs:__imp_CoMarshalInterface
0x180024a65  mov     dword ptr [rbp+ppstm+8], eax
0x180024a68  jmp     short loc_180024A71
0x180024a6a  mov     dword ptr [rbp+ppstm+8], 80004002h
0x180024a71  mov     rcx, [rbp+arg_8]
0x180024a75  mov     rax, [rcx]
0x180024a78  mov     r8d, [rbp+arg_0]
0x180024a7c  mov     rdx, [rbp+pUnk]
0x180024a80  mov     rax, [rax+18h]
0x180024a84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a89  mov     r8, [rbx+80h]
0x180024a90  mov     rdx, [rbp+arg_8]
0x180024a94  mov     ecx, eax
0x180024a96  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x180024a9b  mov     esi, eax
0x180024a9d  or      ecx, 0FFFFFFFFh
0x180024aa0  lock xadd [rbx+88h], ecx
0x180024aa8  cmp     ecx, 1
0x180024aab  jnz     short loc_180024ACC
0x180024aad  lock or [rsp+78h+var_78], r14d
0x180024ab2  mov     rcx, [rbx+78h]
0x180024ab6  mov     [rbx+78h], r14
0x180024aba  test    rcx, rcx
0x180024abd  jz      short loc_180024ACC
0x180024abf  mov     rax, [rcx]
0x180024ac2  mov     rax, [rax+10h]
0x180024ac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024acb  nop
0x180024acc  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180024ad3  test    rcx, rcx
0x180024ad6  jz      short loc_180024AEE
0x180024ad8  mov     rax, [rcx]
0x180024adb  xor     r9d, r9d
0x180024ade  xor     edx, edx
0x180024ae0  lea     r8d, [r9+2]
0x180024ae4  mov     rax, [rax+50h]
0x180024ae8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024aed  nop
0x180024aee  cmp     dword ptr [rbp+ppstm+8], r14d
0x180024af2  jl      short loc_180024B18
0x180024af4  mov     rcx, [rbp+ppstm]
0x180024af8  mov     rdx, r14
0x180024afb  mov     rax, [rcx]
0x180024afe  xor     r9d, r9d
0x180024b01  xor     r8d, r8d
0x180024b04  mov     rax, [rax+28h]
0x180024b08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024b0d  mov     rcx, [rbp+ppstm]; pStm
0x180024b11  call    cs:__imp_CoReleaseMarshalData
0x180024b17  nop
0x180024b18  mov     rcx, [rbp+ppstm]
0x180024b1c  test    rcx, rcx
0x180024b1f  jz      short loc_180024B32
0x180024b21  mov     [rbp+ppstm], r14
0x180024b25  mov     rax, [rcx]
0x180024b28  mov     rax, [rax+10h]
0x180024b2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024b31  nop
0x180024b32  mov     rcx, [rbp+arg_18]
0x180024b36  test    rcx, rcx
0x180024b39  jz      short loc_180024B4C
0x180024b3b  mov     [rbp+arg_18], r14
0x180024b3f  mov     rax, [rcx]
0x180024b42  mov     rax, [rax+10h]
0x180024b46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024b4b  nop
0x180024b4c  mov     rcx, [rbp+arg_8]
0x180024b50  jmp     short loc_180024B55
0x180024b52  mov     rcx, r14
0x180024b55  test    rcx, rcx
0x180024b58  jz      short loc_180024B6B
0x180024b5a  mov     [rbp+arg_8], r14
0x180024b5e  mov     rax, [rcx]
0x180024b61  mov     rax, [rax+10h]
0x180024b65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024b6a  nop
0x180024b6b  mov     rcx, [rbp+pUnk]
0x180024b6f  test    rcx, rcx
0x180024b72  jz      short loc_180024B85
0x180024b74  mov     [rbp+pUnk], r14
0x180024b78  mov     rax, [rcx]
0x180024b7b  mov     rax, [rax+10h]
0x180024b7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024b84  nop
0x180024b85  mov     rax, [rbx]
0x180024b88  mov     rcx, rbx
0x180024b8b  mov     rax, [rax+10h]
0x180024b8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024b94  nop
0x180024b95  mov     eax, esi
0x180024b97  add     rsp, 78h
0x180024b9b  pop     r15
0x180024b9d  pop     r14
0x180024b9f  pop     rdi
0x180024ba0  pop     rsi
0x180024ba1  pop     rbx
0x180024ba2  pop     rbp
0x180024ba3  retn
```
