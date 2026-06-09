# Windows::Internal::AsyncBaseFTM_Windows::Foundation::IAsyncOperationCompletedHandler_bool__1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::FireCompletion

- ea: `0x1800098d0`
- end: `0x180009bac`
- name: `Windows::Internal::AsyncBaseFTM_Windows::Foundation::IAsyncOperationCompletedHandler_bool__1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::FireCompletion`
- size: `732`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001dc0`
- `0x1800098d0`
- `0x18000a0f4`
- `0x18000b4d4`
- `0x18000f588`
- `0x18000f698`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180009a34`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180009a34`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180009a5f`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180009a5f`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x180009b12`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x180009b12`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM_Windows::Foundation::IAsyncOperationCompletedHandler_bool__1_Microsoft::WRL::AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::FireCompletion(
        __int64 a1)
{
  unsigned int v2; // esi
  unsigned int v3; // edx
  signed __int32 v4; // ecx
  __int64 v5; // rcx
  __int64 v6; // rax
  void (__fastcall *v7)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, _QWORD, __int64, struct IRpcOptions **, __int64, _DWORD); // rax
  struct IRpcOptions *v8; // rdi
  IUnknown *v9; // rsi
  unsigned int v10; // eax
  __int64 v11; // rdx
  LPSTREAM v12; // rcx
  struct IUnknown *v13; // rcx
  LPUNKNOWN v14; // rcx
  signed __int32 v16[8]; // [rsp+0h] [rbp-80h] BYREF
  LPVOID pvDestContext; // [rsp+20h] [rbp-60h]
  DWORD mshlflags; // [rsp+28h] [rbp-58h]
  struct IRpcOptions *v19[2]; // [rsp+40h] [rbp-40h] BYREF
  unsigned int v20; // [rsp+50h] [rbp-30h] BYREF
  struct IUnknown *v21; // [rsp+58h] [rbp-28h] BYREF
  LPUNKNOWN pUnk; // [rsp+60h] [rbp-20h] BYREF
  LPSTREAM ppstm; // [rsp+68h] [rbp-18h] BYREF
  __int64 v24; // [rsp+70h] [rbp-10h]

  v2 = 0;
  Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::TransitionToState(
    a1,
    1);
  if ( *(int *)(a1 + 136) > 0 && _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 16), v3) + 1 == v3 )
  {
    if ( a1 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
    pUnk = 0;
    Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::TraceOperationComplete(a1);
    if ( (**(int (__fastcall ***)(__int64, GUID *, LPUNKNOWN *))a1)(
           a1,
           &GUID_cdb5efb3_5788_509d_9be1_71ccb8a3362a,
           &pUnk) >= 0 )
    {
      v4 = *(_DWORD *)(a1 + 56);
      v20 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v20, v4, -2);
      v5 = *(_QWORD *)(a1 + 120);
      v21 = 0;
      if ( v5
        && (*(int (__fastcall **)(__int64, GUID *, struct IUnknown **))(*(_QWORD *)v5 + 24LL))(
             v5,
             &GUID_c1d3d1a2_ae17_5a5f_b5a2_bdcc8844889a,
             &v21) >= 0 )
      {
        if ( Microsoft::WRL::gCausality )
        {
          v6 = *(_QWORD *)Microsoft::WRL::gCausality;
          mshlflags = 0;
          pvDestContext = (LPVOID)a1;
          v7 = *(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, _QWORD, __int64, struct IRpcOptions **, __int64, _DWORD))(v6 + 72);
          *(GUID *)v19 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
          v7(Microsoft::WRL::gCausality, 0, 2, v19, a1, 0);
        }
        v19[0] = 0;
        RpcOptionsHelper::GetRpcOptions(v21, v19);
        v8 = v19[0];
        v24 = 0;
        ppstm = 0;
        if ( v19[0] && v21 )
        {
          v9 = pUnk;
          LODWORD(v24) = CreateStreamOnHGlobal(0, 1, &ppstm);
          if ( (int)v24 >= 0 )
            LODWORD(v24) = CoMarshalInterface(ppstm, &GUID_00000000_0000_0000_c000_000000000046, v9, 0, 0, 1u);
        }
        else
        {
          LODWORD(v24) = -2147467262;
        }
        v10 = ((__int64 (__fastcall *)(struct IUnknown *, LPUNKNOWN, _QWORD))v21->lpVtbl[1].QueryInterface)(
                v21,
                pUnk,
                v20);
        v2 = Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(
               v10,
               v21,
               *(_QWORD *)(a1 + 128));
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 136), 0xFFFFFFFF) == 1 )
        {
          _InterlockedOr(v16, 0);
          v11 = *(_QWORD *)(a1 + 120);
          *(_QWORD *)(a1 + 120) = 0;
          if ( v11 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
        }
        if ( Microsoft::WRL::gCausality )
          (*(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, _QWORD, __int64))(*(_QWORD *)Microsoft::WRL::gCausality + 80LL))(
            Microsoft::WRL::gCausality,
            0,
            2);
        if ( (int)v24 >= 0 )
        {
          (*(void (__fastcall **)(LPSTREAM, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppstm + 40LL))(ppstm, 0, 0, 0);
          CoReleaseMarshalData(ppstm);
        }
        v12 = ppstm;
        if ( ppstm )
        {
          ppstm = 0;
          (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)v12 + 16LL))(v12);
        }
        if ( v8 )
          ((void (__fastcall *)(struct IRpcOptions *))v8->lpVtbl->Release)(v8);
      }
      v13 = v21;
      if ( v21 )
      {
        v21 = 0;
        ((void (__fastcall *)(struct IUnknown *))v13->lpVtbl->Release)(v13);
      }
    }
    v14 = pUnk;
    if ( pUnk )
    {
      pUnk = 0;
      ((void (__fastcall *)(LPUNKNOWN))v14->lpVtbl->Release)(v14);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
  }
  return v2;
}

```

## disassembly

```asm
0x1800098d0  mov     [rsp-18h+arg_8], rbx
0x1800098d5  mov     [rsp-18h+arg_10], rsi
0x1800098da  push    rbp
0x1800098db  push    rdi
0x1800098dc  push    r14
0x1800098de  mov     rbp, rsp
0x1800098e1  sub     rsp, 80h
0x1800098e8  mov     rax, cs:__security_cookie
0x1800098ef  xor     rax, rsp
0x1800098f2  mov     [rbp+var_8], rax
0x1800098f6  xor     r14d, r14d
0x1800098f9  mov     rbx, rcx
0x1800098fc  mov     esi, r14d
0x1800098ff  lea     edx, [r14+1]
0x180009903  call    Microsoft__WRL__AsyncBase_Windows__Foundation__IAsyncOperationCompletedHandler_bool__Microsoft__WRL__Details__Nil_1_Microsoft__WRL__AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2_____TransitionToState
0x180009908  cmp     [rbx+88h], r14d
0x18000990f  jle     loc_180009B86
0x180009915  mov     eax, edx
0x180009917  lock xadd [rbx+10h], eax
0x18000991c  inc     eax
0x18000991e  cmp     eax, edx
0x180009920  jnz     loc_180009B86
0x180009926  test    rbx, rbx
0x180009929  jz      short loc_18000993A
0x18000992b  mov     rax, [rbx]
0x18000992e  mov     rcx, rbx
0x180009931  mov     rax, [rax+8]
0x180009935  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000993a  mov     rcx, rbx
0x18000993d  mov     [rbp+pUnk], r14
0x180009941  call    Microsoft__WRL__AsyncBase_Windows__Foundation__IAsyncOperationCompletedHandler_bool__Microsoft__WRL__Details__Nil_1_Microsoft__WRL__AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2_____TraceOperationComplete
0x180009946  mov     rax, [rbx]
0x180009949  mov     rcx, [rbp+pUnk]
0x18000994d  mov     rdi, [rax]
0x180009950  test    rcx, rcx
0x180009953  jz      short loc_180009965
0x180009955  mov     [rbp+pUnk], r14
0x180009959  mov     rax, [rcx]
0x18000995c  mov     rax, [rax+10h]
0x180009960  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009965  lea     r8, [rbp+pUnk]
0x180009969  mov     rcx, rbx
0x18000996c  lea     rdx, _GUID_cdb5efb3_5788_509d_9be1_71ccb8a3362a
0x180009973  mov     rax, rdi
0x180009976  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000997b  test    eax, eax
0x18000997d  js      loc_180009B5E
0x180009983  mov     ecx, [rbx+38h]
0x180009986  mov     [rbp+var_30], 0FFFFFFFEh
0x18000998d  mov     eax, [rbp+var_30]
0x180009990  lock cmpxchg [rbp+var_30], ecx
0x180009995  mov     rcx, [rbx+78h]
0x180009999  mov     [rbp+var_28], r14
0x18000999d  test    rcx, rcx
0x1800099a0  jz      loc_180009B45
0x1800099a6  mov     rax, [rcx]
0x1800099a9  lea     r8, [rbp+var_28]
0x1800099ad  lea     rdx, _GUID_c1d3d1a2_ae17_5a5f_b5a2_bdcc8844889a
0x1800099b4  mov     rax, [rax+18h]
0x1800099b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099bd  test    eax, eax
0x1800099bf  js      loc_180009B45
0x1800099c5  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x1800099cc  test    rcx, rcx
0x1800099cf  jz      short loc_1800099FD
0x1800099d1  mov     rax, [rcx]
0x1800099d4  lea     r9, [rbp+var_40]
0x1800099d8  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x1800099df  xor     edx, edx
0x1800099e1  mov     [rsp+80h+mshlflags], r14d
0x1800099e6  mov     [rsp+80h+pvDestContext], rbx
0x1800099eb  mov     rax, [rax+48h]
0x1800099ef  movdqu  xmmword ptr [rbp+var_40], xmm0
0x1800099f4  lea     r8d, [rdx+2]
0x1800099f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099fd  mov     rcx, [rbp+var_28]; struct IUnknown *
0x180009a01  lea     rdx, [rbp+var_40]; struct IRpcOptions **
0x180009a05  mov     [rbp+var_40], r14
0x180009a09  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@PEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,IRpcOptions * *)
0x180009a0e  mov     rdi, [rbp+var_40]
0x180009a12  mov     [rbp+var_10], r14
0x180009a16  mov     [rbp+ppstm], r14
0x180009a1a  test    rdi, rdi
0x180009a1d  jz      short loc_180009A6A
0x180009a1f  cmp     [rbp+var_28], r14
0x180009a23  jz      short loc_180009A6A
0x180009a25  mov     rsi, [rbp+pUnk]
0x180009a29  lea     r8, [rbp+ppstm]; ppstm
0x180009a2d  mov     edx, 1; fDeleteOnRelease
0x180009a32  xor     ecx, ecx; hGlobal
0x180009a34  call    cs:__imp_CreateStreamOnHGlobal
0x180009a3a  mov     dword ptr [rbp+var_10], eax
0x180009a3d  test    eax, eax
0x180009a3f  js      short loc_180009A71
0x180009a41  mov     rcx, [rbp+ppstm]; pStm
0x180009a45  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180009a4c  mov     [rsp+80h+mshlflags], 1; mshlflags
0x180009a54  xor     r9d, r9d; dwDestContext
0x180009a57  mov     r8, rsi; pUnk
0x180009a5a  mov     [rsp+80h+pvDestContext], r14; pvDestContext
0x180009a5f  call    cs:__imp_CoMarshalInterface
0x180009a65  mov     dword ptr [rbp+var_10], eax
0x180009a68  jmp     short loc_180009A71
0x180009a6a  mov     dword ptr [rbp+var_10], 80004002h
0x180009a71  mov     rcx, [rbp+var_28]
0x180009a75  mov     r8d, [rbp+var_30]
0x180009a79  mov     rdx, [rbp+pUnk]
0x180009a7d  mov     rax, [rcx]
0x180009a80  mov     rax, [rax+18h]
0x180009a84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a89  mov     r8, [rbx+80h]
0x180009a90  mov     ecx, eax
0x180009a92  mov     rdx, [rbp+var_28]
0x180009a96  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x180009a9b  mov     esi, eax
0x180009a9d  or      ecx, 0FFFFFFFFh
0x180009aa0  lock xadd [rbx+88h], ecx
0x180009aa8  cmp     ecx, 1
0x180009aab  jnz     short loc_180009ACE
0x180009aad  lock or [rsp+80h+var_80], r14d
0x180009ab2  mov     rdx, [rbx+78h]
0x180009ab6  mov     [rbx+78h], r14
0x180009aba  test    rdx, rdx
0x180009abd  jz      short loc_180009ACE
0x180009abf  mov     rcx, [rdx]
0x180009ac2  mov     rax, [rcx+10h]
0x180009ac6  mov     rcx, rdx
0x180009ac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ace  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180009ad5  test    rcx, rcx
0x180009ad8  jz      short loc_180009AEF
0x180009ada  mov     rax, [rcx]
0x180009add  xor     r9d, r9d
0x180009ae0  xor     edx, edx
0x180009ae2  mov     rax, [rax+50h]
0x180009ae6  lea     r8d, [r9+2]
0x180009aea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009aef  cmp     dword ptr [rbp+var_10], r14d
0x180009af3  jl      short loc_180009B18
0x180009af5  mov     rcx, [rbp+ppstm]
0x180009af9  mov     rdx, r14
0x180009afc  xor     r9d, r9d
0x180009aff  xor     r8d, r8d
0x180009b02  mov     rax, [rcx]
0x180009b05  mov     rax, [rax+28h]
0x180009b09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b0e  mov     rcx, [rbp+ppstm]; pStm
0x180009b12  call    cs:__imp_CoReleaseMarshalData
0x180009b18  mov     rcx, [rbp+ppstm]
0x180009b1c  test    rcx, rcx
0x180009b1f  jz      short loc_180009B31
0x180009b21  mov     [rbp+ppstm], r14
0x180009b25  mov     rax, [rcx]
0x180009b28  mov     rax, [rax+10h]
0x180009b2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b31  test    rdi, rdi
0x180009b34  jz      short loc_180009B45
0x180009b36  mov     rax, [rdi]
0x180009b39  mov     rcx, rdi
0x180009b3c  mov     rax, [rax+10h]
0x180009b40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b45  mov     rcx, [rbp+var_28]
0x180009b49  test    rcx, rcx
0x180009b4c  jz      short loc_180009B5E
0x180009b4e  mov     [rbp+var_28], r14
0x180009b52  mov     rax, [rcx]
0x180009b55  mov     rax, [rax+10h]
0x180009b59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b5e  mov     rcx, [rbp+pUnk]
0x180009b62  test    rcx, rcx
0x180009b65  jz      short loc_180009B77
0x180009b67  mov     [rbp+pUnk], r14
0x180009b6b  mov     rax, [rcx]
0x180009b6e  mov     rax, [rax+10h]
0x180009b72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b77  mov     rax, [rbx]
0x180009b7a  mov     rcx, rbx
0x180009b7d  mov     rax, [rax+10h]
0x180009b81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b86  mov     eax, esi
0x180009b88  mov     rcx, [rbp+var_8]
0x180009b8c  xor     rcx, rsp; StackCookie
0x180009b8f  call    __security_check_cookie
0x180009b94  lea     r11, [rsp+80h+var_s0]
0x180009b9c  mov     rbx, [r11+28h]
0x180009ba0  mov     rsi, [r11+30h]
0x180009ba4  mov     rsp, r11
0x180009ba7  pop     r14
0x180009ba9  pop     rdi
0x180009baa  pop     rbp
0x180009bab  retn
```
