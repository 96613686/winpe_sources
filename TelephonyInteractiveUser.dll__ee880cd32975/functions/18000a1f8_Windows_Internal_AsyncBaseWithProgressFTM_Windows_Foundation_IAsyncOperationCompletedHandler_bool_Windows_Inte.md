# Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireProgress(int)

- ea: `0x18000a1f8`
- end: `0x18000a4cc`
- name: `?FireProgress@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@QEAAJH@Z`
- size: `724`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000f1a0`

## callees

- `0x180001dc0`
- `0x18000a0f4`
- `0x18000a1f8`
- `0x18000b4d4`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18000a346`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18000a346`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18000a36e`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18000a36e`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x18000a3f5`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x18000a3f5`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireProgress(
        __int64 a1,
        unsigned int a2)
{
  unsigned int v4; // esi
  signed __int32 v5; // eax
  __int64 v6; // rcx
  __int64 v7; // rax
  void (__fastcall *v8)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, __int64, __int64, struct IRpcOptions **, __int64, int); // rax
  struct IRpcOptions *v9; // rdi
  IUnknown *v10; // rsi
  unsigned int v11; // eax
  LPSTREAM v12; // rcx
  __int64 v13; // rcx
  struct IUnknown *v14; // rcx
  LPUNKNOWN v15; // rcx
  signed __int32 v17[8]; // [rsp+0h] [rbp-80h] BYREF
  LPVOID pvDestContext; // [rsp+20h] [rbp-60h]
  DWORD mshlflags; // [rsp+28h] [rbp-58h]
  struct IRpcOptions *v20[2]; // [rsp+40h] [rbp-40h] BYREF
  struct IUnknown *v21; // [rsp+50h] [rbp-30h] BYREF
  LPUNKNOWN pUnk; // [rsp+58h] [rbp-28h] BYREF
  LPSTREAM ppstm; // [rsp+60h] [rbp-20h] BYREF
  __int64 v24; // [rsp+68h] [rbp-18h]

  v4 = 0;
  if ( a1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  pUnk = 0;
  while ( 1 )
  {
    v5 = *(_DWORD *)(a1 + 160);
    if ( v5 <= 0 )
      break;
    if ( v5 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 160), v5 + 1, v5) )
    {
      if ( (**(int (__fastcall ***)(__int64, GUID *, LPUNKNOWN *))a1)(
             a1,
             &GUID_00000000_0000_0000_c000_000000000046,
             &pUnk) >= 0 )
      {
        v6 = *(_QWORD *)(a1 + 144);
        v21 = 0;
        if ( v6
          && (*(int (__fastcall **)(__int64, GUID *, struct IUnknown **))(*(_QWORD *)v6 + 24LL))(
               v6,
               &GUID_2fafaaf9_2986_48ee_919d_98f66edf0a31,
               &v21) >= 0 )
        {
          if ( Microsoft::WRL::gCausality )
          {
            v7 = *(_QWORD *)Microsoft::WRL::gCausality;
            mshlflags = 1;
            pvDestContext = (LPVOID)a1;
            v8 = *(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, __int64, __int64, struct IRpcOptions **, __int64, int))(v7 + 72);
            *(GUID *)v20 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
            v8(Microsoft::WRL::gCausality, 1, 2, v20, a1, 1);
          }
          v20[0] = 0;
          RpcOptionsHelper::GetRpcOptions(v21, v20);
          v9 = v20[0];
          v24 = 0;
          ppstm = 0;
          if ( v20[0] && v21 )
          {
            v10 = pUnk;
            LODWORD(v24) = CreateStreamOnHGlobal(0, 1, &ppstm);
            if ( (int)v24 >= 0 )
              LODWORD(v24) = CoMarshalInterface(ppstm, &GUID_00000000_0000_0000_c000_000000000046, v10, 0, 0, 1u);
          }
          else
          {
            LODWORD(v24) = -2147467262;
          }
          v11 = ((__int64 (__fastcall *)(struct IUnknown *, LPUNKNOWN, _QWORD))v21->lpVtbl[1].QueryInterface)(
                  v21,
                  pUnk,
                  a2);
          v4 = Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(
                 v11,
                 v21,
                 *(_QWORD *)(a1 + 152));
          if ( Microsoft::WRL::gCausality )
            (*(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, __int64, __int64, __int64))(*(_QWORD *)Microsoft::WRL::gCausality + 80LL))(
              Microsoft::WRL::gCausality,
              1,
              2,
              1);
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
          if ( v9 )
            ((void (__fastcall *)(struct IRpcOptions *))v9->lpVtbl->Release)(v9);
        }
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 160), 0xFFFFFFFF) == 1 )
        {
          _InterlockedOr(v17, 0);
          v13 = *(_QWORD *)(a1 + 144);
          *(_QWORD *)(a1 + 144) = 0;
          if ( v13 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        }
        v14 = v21;
        if ( v21 )
        {
          v21 = 0;
          ((void (__fastcall *)(struct IUnknown *))v14->lpVtbl->Release)(v14);
        }
      }
      break;
    }
  }
  v15 = pUnk;
  if ( pUnk )
  {
    pUnk = 0;
    ((void (__fastcall *)(LPUNKNOWN))v15->lpVtbl->Release)(v15);
  }
  if ( a1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
  return v4;
}

```

## disassembly

```asm
0x18000a1f8  mov     [rsp-28h+arg_10], rbx
0x18000a1fd  mov     [rsp-28h+arg_18], rsi
0x18000a202  push    rbp
0x18000a203  push    rdi
0x18000a204  push    r12
0x18000a206  push    r14
0x18000a208  push    r15
0x18000a20a  mov     rbp, rsp
0x18000a20d  sub     rsp, 80h
0x18000a214  mov     rax, cs:__security_cookie
0x18000a21b  xor     rax, rsp
0x18000a21e  mov     [rbp+var_10], rax
0x18000a222  xor     r15d, r15d
0x18000a225  mov     r14d, edx
0x18000a228  mov     rbx, rcx
0x18000a22b  mov     esi, r15d
0x18000a22e  test    rcx, rcx
0x18000a231  jz      short loc_18000A23F
0x18000a233  mov     rax, [rcx]
0x18000a236  mov     rax, [rax+8]
0x18000a23a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a23f  mov     [rbp+pUnk], r15
0x18000a243  jmp     short loc_18000A252
0x18000a245  lea     ecx, [rax+1]
0x18000a248  lock cmpxchg [rbx+0A0h], ecx
0x18000a250  jz      short loc_18000A261
0x18000a252  mov     eax, [rbx+0A0h]
0x18000a258  test    eax, eax
0x18000a25a  jg      short loc_18000A245
0x18000a25c  jmp     loc_18000A475
0x18000a261  mov     rax, [rbx]
0x18000a264  mov     rcx, [rbp+pUnk]
0x18000a268  mov     rdi, [rax]
0x18000a26b  test    rcx, rcx
0x18000a26e  jz      short loc_18000A280
0x18000a270  mov     [rbp+pUnk], r15
0x18000a274  mov     rax, [rcx]
0x18000a277  mov     rax, [rax+10h]
0x18000a27b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a280  lea     r8, [rbp+pUnk]
0x18000a284  mov     rcx, rbx
0x18000a287  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000a28e  mov     rax, rdi
0x18000a291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a296  test    eax, eax
0x18000a298  js      loc_18000A475
0x18000a29e  mov     rcx, [rbx+90h]
0x18000a2a5  mov     [rbp+var_30], r15
0x18000a2a9  test    rcx, rcx
0x18000a2ac  jz      loc_18000A428
0x18000a2b2  mov     rax, [rcx]
0x18000a2b5  lea     r8, [rbp+var_30]
0x18000a2b9  lea     rdx, _GUID_2fafaaf9_2986_48ee_919d_98f66edf0a31
0x18000a2c0  mov     rax, [rax+18h]
0x18000a2c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2c9  test    eax, eax
0x18000a2cb  js      loc_18000A428
0x18000a2d1  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18000a2d8  mov     r12d, 1
0x18000a2de  test    rcx, rcx
0x18000a2e1  jz      short loc_18000A311
0x18000a2e3  mov     rax, [rcx]
0x18000a2e6  lea     r9, [rbp+var_40]
0x18000a2ea  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x18000a2f1  mov     [rsp+80h+mshlflags], r12d
0x18000a2f6  lea     r8d, [r12+1]
0x18000a2fb  mov     edx, r12d
0x18000a2fe  mov     [rsp+80h+pvDestContext], rbx
0x18000a303  mov     rax, [rax+48h]
0x18000a307  movdqu  xmmword ptr [rbp+var_40], xmm0
0x18000a30c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a311  mov     rcx, [rbp+var_30]; struct IUnknown *
0x18000a315  lea     rdx, [rbp+var_40]; struct IRpcOptions **
0x18000a319  mov     [rbp+var_40], r15
0x18000a31d  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@PEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,IRpcOptions * *)
0x18000a322  mov     rdi, [rbp+var_40]
0x18000a326  mov     [rbp+var_18], r15
0x18000a32a  mov     [rbp+ppstm], r15
0x18000a32e  test    rdi, rdi
0x18000a331  jz      short loc_18000A379
0x18000a333  cmp     [rbp+var_30], r15
0x18000a337  jz      short loc_18000A379
0x18000a339  mov     rsi, [rbp+pUnk]
0x18000a33d  lea     r8, [rbp+ppstm]; ppstm
0x18000a341  mov     edx, r12d; fDeleteOnRelease
0x18000a344  xor     ecx, ecx; hGlobal
0x18000a346  call    cs:__imp_CreateStreamOnHGlobal
0x18000a34c  mov     dword ptr [rbp+var_18], eax
0x18000a34f  test    eax, eax
0x18000a351  js      short loc_18000A380
0x18000a353  mov     rcx, [rbp+ppstm]; pStm
0x18000a357  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18000a35e  mov     [rsp+80h+mshlflags], r12d; mshlflags
0x18000a363  xor     r9d, r9d; dwDestContext
0x18000a366  mov     r8, rsi; pUnk
0x18000a369  mov     [rsp+80h+pvDestContext], r15; pvDestContext
0x18000a36e  call    cs:__imp_CoMarshalInterface
0x18000a374  mov     dword ptr [rbp+var_18], eax
0x18000a377  jmp     short loc_18000A380
0x18000a379  mov     dword ptr [rbp+var_18], 80004002h
0x18000a380  mov     rcx, [rbp+var_30]
0x18000a384  mov     r8d, r14d
0x18000a387  mov     rdx, [rbp+pUnk]
0x18000a38b  mov     rax, [rcx]
0x18000a38e  mov     rax, [rax+18h]
0x18000a392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a397  mov     r8, [rbx+98h]
0x18000a39e  mov     ecx, eax
0x18000a3a0  mov     rdx, [rbp+var_30]
0x18000a3a4  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x18000a3a9  mov     r10, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18000a3b0  mov     esi, eax
0x18000a3b2  test    r10, r10
0x18000a3b5  jz      short loc_18000A3D2
0x18000a3b7  mov     rcx, [r10]
0x18000a3ba  mov     r9d, r12d
0x18000a3bd  mov     r8d, 2
0x18000a3c3  mov     edx, r12d
0x18000a3c6  mov     rax, [rcx+50h]
0x18000a3ca  mov     rcx, r10
0x18000a3cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3d2  cmp     dword ptr [rbp+var_18], r15d
0x18000a3d6  jl      short loc_18000A3FB
0x18000a3d8  mov     rcx, [rbp+ppstm]
0x18000a3dc  mov     rdx, r15
0x18000a3df  xor     r9d, r9d
0x18000a3e2  xor     r8d, r8d
0x18000a3e5  mov     rax, [rcx]
0x18000a3e8  mov     rax, [rax+28h]
0x18000a3ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3f1  mov     rcx, [rbp+ppstm]; pStm
0x18000a3f5  call    cs:__imp_CoReleaseMarshalData
0x18000a3fb  mov     rcx, [rbp+ppstm]
0x18000a3ff  test    rcx, rcx
0x18000a402  jz      short loc_18000A414
0x18000a404  mov     [rbp+ppstm], r15
0x18000a408  mov     rax, [rcx]
0x18000a40b  mov     rax, [rax+10h]
0x18000a40f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a414  test    rdi, rdi
0x18000a417  jz      short loc_18000A428
0x18000a419  mov     rax, [rdi]
0x18000a41c  mov     rcx, rdi
0x18000a41f  mov     rax, [rax+10h]
0x18000a423  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a428  or      eax, 0FFFFFFFFh
0x18000a42b  lock xadd [rbx+0A0h], eax
0x18000a433  cmp     eax, 1
0x18000a436  jnz     short loc_18000A45C
0x18000a438  lock or [rsp+80h+var_80], r15d
0x18000a43d  mov     rcx, [rbx+90h]
0x18000a444  mov     [rbx+90h], r15
0x18000a44b  test    rcx, rcx
0x18000a44e  jz      short loc_18000A45C
0x18000a450  mov     rax, [rcx]
0x18000a453  mov     rax, [rax+10h]
0x18000a457  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a45c  mov     rcx, [rbp+var_30]
0x18000a460  test    rcx, rcx
0x18000a463  jz      short loc_18000A475
0x18000a465  mov     [rbp+var_30], r15
0x18000a469  mov     rax, [rcx]
0x18000a46c  mov     rax, [rax+10h]
0x18000a470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a475  mov     rcx, [rbp+pUnk]
0x18000a479  test    rcx, rcx
0x18000a47c  jz      short loc_18000A48E
0x18000a47e  mov     [rbp+pUnk], r15
0x18000a482  mov     rax, [rcx]
0x18000a485  mov     rax, [rax+10h]
0x18000a489  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a48e  test    rbx, rbx
0x18000a491  jz      short loc_18000A4A2
0x18000a493  mov     rax, [rbx]
0x18000a496  mov     rcx, rbx
0x18000a499  mov     rax, [rax+10h]
0x18000a49d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4a2  mov     eax, esi
0x18000a4a4  mov     rcx, [rbp+var_10]
0x18000a4a8  xor     rcx, rsp; StackCookie
0x18000a4ab  call    __security_check_cookie
0x18000a4b0  lea     r11, [rsp+80h+var_s0]
0x18000a4b8  mov     rbx, [r11+40h]
0x18000a4bc  mov     rsi, [r11+48h]
0x18000a4c0  mov     rsp, r11
0x18000a4c3  pop     r15
0x18000a4c5  pop     r14
0x18000a4c7  pop     r12
0x18000a4c9  pop     rdi
0x18000a4ca  pop     rbp
0x18000a4cb  retn
```
