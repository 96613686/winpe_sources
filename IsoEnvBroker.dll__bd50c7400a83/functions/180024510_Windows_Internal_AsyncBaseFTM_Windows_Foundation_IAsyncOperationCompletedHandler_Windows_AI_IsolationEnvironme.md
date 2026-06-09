# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::AI::IsolationEnvironment::IsolationProvisionResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x180024510`
- end: `0x180024834`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVIsolationProvisionResult@IsolationEnvironment@AI@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `804`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180024840`
- `0x180026720`
- `0x18002a774`

## callees

- `0x180024510`
- `0x180024a88`
- `0x180025f14`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x1800247a1`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x1800247a1`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800246c7`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800246c7`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x1800246ef`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x1800246ef`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::AI::IsolationEnvironment::IsolationProvisionResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
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
    if ( v4(a1, &GUID_9905d8f4_e9ba_5c1f_ab38_d656a2e44381, &pUnk) >= 0 )
    {
      v18 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v18, a1[14], -2);
      v5 = *((_QWORD *)a1 + 15);
      if ( v5 )
      {
        v19 = 0;
        if ( (*(int (__fastcall **)(__int64, GUID *, struct IUnknown **))(*(_QWORD *)v5 + 24LL))(
               v5,
               &GUID_7698777b_bdd8_5fc1_990f_6caed35fe1e7,
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
0x180024510  push    rbp
0x180024512  push    rbx
0x180024513  push    rsi
0x180024514  push    rdi
0x180024515  push    r14
0x180024517  push    r15
0x180024519  mov     rbp, rsp
0x18002451c  sub     rsp, 78h
0x180024520  mov     rbx, rcx
0x180024523  xor     r14d, r14d
0x180024526  mov     esi, r14d
0x180024529  mov     [rbp+arg_0], 0FFFFFFFEh
0x180024530  mov     edx, [rcx+38h]
0x180024533  mov     eax, [rbp+arg_0]
0x180024536  lock cmpxchg [rbp+arg_0], edx
0x18002453b  lea     r15d, [r14+1]
0x18002453f  cmp     [rbp+arg_0], r14d
0x180024543  jnz     short loc_18002454D
0x180024545  xor     eax, eax
0x180024547  lock cmpxchg [rcx+38h], r15d
0x18002454d  cmp     [rcx+88h], r14d
0x180024554  jle     loc_180024825
0x18002455a  mov     eax, r15d
0x18002455d  lock xadd [rcx+10h], eax
0x180024562  add     eax, r15d
0x180024565  cmp     eax, r15d
0x180024568  jnz     loc_180024825
0x18002456e  mov     [rbp+var_38], rbx
0x180024572  test    rbx, rbx
0x180024575  jz      short loc_180024584
0x180024577  mov     rax, [rcx]
0x18002457a  mov     rax, [rax+8]
0x18002457e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024583  nop
0x180024584  mov     rcx, r14
0x180024587  mov     [rbp+pUnk], rcx
0x18002458b  cmp     cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA, r14; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180024592  jz      short loc_1800245DF
0x180024594  mov     [rbp+arg_0], r14d
0x180024598  mov     ecx, [rbx+38h]
0x18002459b  mov     eax, [rbp+arg_0]
0x18002459e  lock cmpxchg [rbp+arg_0], ecx
0x1800245a3  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x1800245aa  movdqu  xmmword ptr [rbp+ppstm], xmm0
0x1800245af  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x1800245b6  mov     rax, [rcx]
0x1800245b9  mov     r10, [rax+38h]
0x1800245bd  mov     eax, [rbp+arg_0]
0x1800245c0  mov     [rsp+78h+mshlflags], eax
0x1800245c4  mov     [rsp+78h+pvDestContext], rbx
0x1800245c9  lea     r9, [rbp+ppstm]
0x1800245cd  xor     edx, edx
0x1800245cf  lea     r8d, [rdx+2]
0x1800245d3  mov     rax, r10
0x1800245d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800245db  mov     rcx, [rbp+pUnk]
0x1800245df  mov     rax, [rbx]
0x1800245e2  mov     rdi, [rax]
0x1800245e5  test    rcx, rcx
0x1800245e8  jz      short loc_1800245FB
0x1800245ea  mov     [rbp+pUnk], r14
0x1800245ee  mov     rax, [rcx]
0x1800245f1  mov     rax, [rax+10h]
0x1800245f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800245fa  nop
0x1800245fb  lea     r8, [rbp+pUnk]
0x1800245ff  lea     rdx, _GUID_9905d8f4_e9ba_5c1f_ab38_d656a2e44381
0x180024606  mov     rcx, rbx
0x180024609  mov     rax, rdi
0x18002460c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024611  nop
0x180024612  test    eax, eax
0x180024614  js      loc_1800247FB
0x18002461a  mov     [rbp+arg_0], 0FFFFFFFEh
0x180024621  mov     ecx, [rbx+38h]
0x180024624  mov     eax, [rbp+arg_0]
0x180024627  lock cmpxchg [rbp+arg_0], ecx
0x18002462c  mov     rcx, [rbx+78h]
0x180024630  test    rcx, rcx
0x180024633  jz      loc_1800247E2
0x180024639  mov     [rbp+arg_8], r14
0x18002463d  mov     rax, [rcx]
0x180024640  lea     r8, [rbp+arg_8]
0x180024644  lea     rdx, _GUID_7698777b_bdd8_5fc1_990f_6caed35fe1e7
0x18002464b  mov     rax, [rax+18h]
0x18002464f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024654  nop
0x180024655  test    eax, eax
0x180024657  js      loc_1800247DC
0x18002465d  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180024664  test    rcx, rcx
0x180024667  jz      short loc_180024695
0x180024669  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x180024670  movdqu  xmmword ptr [rbp+var_18.Data1], xmm0
0x180024675  mov     rax, [rcx]
0x180024678  mov     [rsp+78h+mshlflags], r14d
0x18002467d  mov     [rsp+78h+pvDestContext], rbx
0x180024682  lea     r9, [rbp+var_18]
0x180024686  xor     edx, edx
0x180024688  lea     r8d, [rdx+2]
0x18002468c  mov     rax, [rax+48h]
0x180024690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024695  mov     [rbp+arg_18], r14
0x180024699  lea     rdx, [rbp+arg_18]; struct IRpcOptions **
0x18002469d  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x1800246a1  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@PEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,IRpcOptions * *)
0x1800246a6  mov     [rbp+ppstm], r14
0x1800246aa  mov     dword ptr [rbp+ppstm+8], r14d
0x1800246ae  cmp     [rbp+arg_18], r14
0x1800246b2  jz      short loc_1800246FA
0x1800246b4  cmp     [rbp+arg_8], r14
0x1800246b8  jz      short loc_1800246FA
0x1800246ba  mov     rdi, [rbp+pUnk]
0x1800246be  lea     r8, [rbp+ppstm]; ppstm
0x1800246c2  mov     edx, r15d; fDeleteOnRelease
0x1800246c5  xor     ecx, ecx; hGlobal
0x1800246c7  call    cs:__imp_CreateStreamOnHGlobal
0x1800246cd  mov     dword ptr [rbp+ppstm+8], eax
0x1800246d0  test    eax, eax
0x1800246d2  js      short loc_180024701
0x1800246d4  mov     [rsp+78h+mshlflags], r15d; mshlflags
0x1800246d9  mov     [rsp+78h+pvDestContext], r14; pvDestContext
0x1800246de  xor     r9d, r9d; dwDestContext
0x1800246e1  mov     r8, rdi; pUnk
0x1800246e4  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x1800246eb  mov     rcx, [rbp+ppstm]; pStm
0x1800246ef  call    cs:__imp_CoMarshalInterface
0x1800246f5  mov     dword ptr [rbp+ppstm+8], eax
0x1800246f8  jmp     short loc_180024701
0x1800246fa  mov     dword ptr [rbp+ppstm+8], 80004002h
0x180024701  mov     rcx, [rbp+arg_8]
0x180024705  mov     rax, [rcx]
0x180024708  mov     r8d, [rbp+arg_0]
0x18002470c  mov     rdx, [rbp+pUnk]
0x180024710  mov     rax, [rax+18h]
0x180024714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024719  mov     r8, [rbx+80h]
0x180024720  mov     rdx, [rbp+arg_8]
0x180024724  mov     ecx, eax
0x180024726  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x18002472b  mov     esi, eax
0x18002472d  or      ecx, 0FFFFFFFFh
0x180024730  lock xadd [rbx+88h], ecx
0x180024738  cmp     ecx, 1
0x18002473b  jnz     short loc_18002475C
0x18002473d  lock or [rsp+78h+var_78], r14d
0x180024742  mov     rcx, [rbx+78h]
0x180024746  mov     [rbx+78h], r14
0x18002474a  test    rcx, rcx
0x18002474d  jz      short loc_18002475C
0x18002474f  mov     rax, [rcx]
0x180024752  mov     rax, [rax+10h]
0x180024756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002475b  nop
0x18002475c  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180024763  test    rcx, rcx
0x180024766  jz      short loc_18002477E
0x180024768  mov     rax, [rcx]
0x18002476b  xor     r9d, r9d
0x18002476e  xor     edx, edx
0x180024770  lea     r8d, [r9+2]
0x180024774  mov     rax, [rax+50h]
0x180024778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002477d  nop
0x18002477e  cmp     dword ptr [rbp+ppstm+8], r14d
0x180024782  jl      short loc_1800247A8
0x180024784  mov     rcx, [rbp+ppstm]
0x180024788  mov     rdx, r14
0x18002478b  mov     rax, [rcx]
0x18002478e  xor     r9d, r9d
0x180024791  xor     r8d, r8d
0x180024794  mov     rax, [rax+28h]
0x180024798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002479d  mov     rcx, [rbp+ppstm]; pStm
0x1800247a1  call    cs:__imp_CoReleaseMarshalData
0x1800247a7  nop
0x1800247a8  mov     rcx, [rbp+ppstm]
0x1800247ac  test    rcx, rcx
0x1800247af  jz      short loc_1800247C2
0x1800247b1  mov     [rbp+ppstm], r14
0x1800247b5  mov     rax, [rcx]
0x1800247b8  mov     rax, [rax+10h]
0x1800247bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800247c1  nop
0x1800247c2  mov     rcx, [rbp+arg_18]
0x1800247c6  test    rcx, rcx
0x1800247c9  jz      short loc_1800247DC
0x1800247cb  mov     [rbp+arg_18], r14
0x1800247cf  mov     rax, [rcx]
0x1800247d2  mov     rax, [rax+10h]
0x1800247d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800247db  nop
0x1800247dc  mov     rcx, [rbp+arg_8]
0x1800247e0  jmp     short loc_1800247E5
0x1800247e2  mov     rcx, r14
0x1800247e5  test    rcx, rcx
0x1800247e8  jz      short loc_1800247FB
0x1800247ea  mov     [rbp+arg_8], r14
0x1800247ee  mov     rax, [rcx]
0x1800247f1  mov     rax, [rax+10h]
0x1800247f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800247fa  nop
0x1800247fb  mov     rcx, [rbp+pUnk]
0x1800247ff  test    rcx, rcx
0x180024802  jz      short loc_180024815
0x180024804  mov     [rbp+pUnk], r14
0x180024808  mov     rax, [rcx]
0x18002480b  mov     rax, [rax+10h]
0x18002480f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024814  nop
0x180024815  mov     rax, [rbx]
0x180024818  mov     rcx, rbx
0x18002481b  mov     rax, [rax+10h]
0x18002481f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024824  nop
0x180024825  mov     eax, esi
0x180024827  add     rsp, 78h
0x18002482b  pop     r15
0x18002482d  pop     r14
0x18002482f  pop     rdi
0x180024830  pop     rsi
0x180024831  pop     rbx
0x180024832  pop     rbp
0x180024833  retn
```
