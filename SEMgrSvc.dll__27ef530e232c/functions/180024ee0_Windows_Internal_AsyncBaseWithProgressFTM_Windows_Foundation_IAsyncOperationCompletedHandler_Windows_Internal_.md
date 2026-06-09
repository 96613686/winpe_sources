# Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::IShellActivationResult *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireProgress(int)

- ea: `0x180024ee0`
- end: `0x180025192`
- name: `?FireProgress@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@PEAUIShellActivationResult@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@QEAAJH@Z`
- size: `690`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002a450`

## callees

- `0x180024df8`
- `0x180024ee0`
- `0x1800263e4`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180025043`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180025043`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x1800250c8`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x1800250c8`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18002501b`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18002501b`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::IShellActivationResult *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireProgress(
        _DWORD *a1,
        unsigned int a2)
{
  unsigned int v4; // esi
  signed __int32 v5; // eax
  int (__fastcall *v6)(_DWORD *, GUID *, LPUNKNOWN *); // rdi
  LPUNKNOWN v7; // rcx
  __int64 v8; // rcx
  IUnknown *v9; // rdi
  unsigned int v10; // eax
  LPSTREAM v11; // rcx
  struct IRpcOptions *v12; // rcx
  __int64 v13; // rcx
  struct IUnknown *v14; // rcx
  LPUNKNOWN v15; // rcx
  signed __int32 v17[8]; // [rsp+0h] [rbp-70h] BYREF
  _DWORD *v18; // [rsp+40h] [rbp-30h]
  LPSTREAM ppstm; // [rsp+48h] [rbp-28h] BYREF
  HRESULT v20; // [rsp+50h] [rbp-20h]
  GUID v21; // [rsp+60h] [rbp-10h] BYREF
  struct IUnknown *v22; // [rsp+B0h] [rbp+40h] BYREF
  LPUNKNOWN pUnk; // [rsp+C0h] [rbp+50h] BYREF
  struct IRpcOptions *v24; // [rsp+C8h] [rbp+58h] BYREF

  v4 = 0;
  v18 = a1;
  if ( a1 )
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)a1 + 8LL))(a1);
  pUnk = 0;
  while ( 1 )
  {
    v5 = a1[40];
    if ( v5 <= 0 )
      break;
    if ( v5 == _InterlockedCompareExchange(a1 + 40, v5 + 1, v5) )
    {
      v6 = **(int (__fastcall ***)(_DWORD *, GUID *, LPUNKNOWN *))a1;
      v7 = pUnk;
      if ( pUnk )
      {
        pUnk = 0;
        ((void (__fastcall *)(LPUNKNOWN))v7->lpVtbl->Release)(v7);
      }
      if ( v6(a1, &GUID_00000000_0000_0000_c000_000000000046, &pUnk) >= 0 )
      {
        v8 = *((_QWORD *)a1 + 18);
        v22 = 0;
        if ( v8
          && (*(int (__fastcall **)(__int64, GUID *, struct IUnknown **))(*(_QWORD *)v8 + 24LL))(
               v8,
               &GUID_2fafaaf9_2986_48ee_919d_98f66edf0a31,
               &v22) >= 0 )
        {
          if ( Microsoft::WRL::gCausality )
          {
            v21 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
            (*(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, __int64, __int64, GUID *, _DWORD *, int))(*(_QWORD *)Microsoft::WRL::gCausality + 72LL))(
              Microsoft::WRL::gCausality,
              1,
              2,
              &v21,
              a1,
              1);
          }
          v24 = 0;
          RpcOptionsHelper::GetRpcOptions(v22, &v24);
          ppstm = 0;
          v20 = 0;
          if ( v24 && v22 )
          {
            v9 = pUnk;
            v20 = CreateStreamOnHGlobal(0, 1, &ppstm);
            if ( v20 >= 0 )
              v20 = CoMarshalInterface(ppstm, &GUID_00000000_0000_0000_c000_000000000046, v9, 0, 0, 1u);
          }
          else
          {
            v20 = -2147467262;
          }
          v10 = ((__int64 (__fastcall *)(struct IUnknown *, LPUNKNOWN, _QWORD))v22->lpVtbl[1].QueryInterface)(
                  v22,
                  pUnk,
                  a2);
          v4 = Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(
                 v10,
                 v22,
                 *((_QWORD *)a1 + 19));
          if ( Microsoft::WRL::gCausality )
            (*(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, __int64, __int64, __int64))(*(_QWORD *)Microsoft::WRL::gCausality + 80LL))(
              Microsoft::WRL::gCausality,
              1,
              2,
              1);
          if ( v20 >= 0 )
          {
            (*(void (__fastcall **)(LPSTREAM, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppstm + 40LL))(ppstm, 0, 0, 0);
            CoReleaseMarshalData(ppstm);
          }
          v11 = ppstm;
          if ( ppstm )
          {
            ppstm = 0;
            (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)v11 + 16LL))(v11);
          }
          v12 = v24;
          if ( v24 )
          {
            v24 = 0;
            ((void (__fastcall *)(struct IRpcOptions *))v12->lpVtbl->Release)(v12);
          }
        }
        if ( _InterlockedExchangeAdd(a1 + 40, 0xFFFFFFFF) == 1 )
        {
          _InterlockedOr(v17, 0);
          v13 = *((_QWORD *)a1 + 18);
          *((_QWORD *)a1 + 18) = 0;
          if ( v13 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        }
        v14 = v22;
        if ( v22 )
        {
          v22 = 0;
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
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)a1 + 16LL))(a1);
  return v4;
}

```

## disassembly

```asm
0x180024ee0  push    rbp
0x180024ee2  push    rbx
0x180024ee3  push    rsi
0x180024ee4  push    rdi
0x180024ee5  push    r12
0x180024ee7  push    r14
0x180024ee9  push    r15
0x180024eeb  mov     rbp, rsp
0x180024eee  sub     rsp, 70h
0x180024ef2  mov     r14d, edx
0x180024ef5  mov     rbx, rcx
0x180024ef8  xor     r15d, r15d
0x180024efb  mov     esi, r15d
0x180024efe  mov     [rbp+var_30], rcx
0x180024f02  test    rcx, rcx
0x180024f05  jz      short loc_180024F14
0x180024f07  mov     rax, [rcx]
0x180024f0a  mov     rax, [rax+8]
0x180024f0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f13  nop
0x180024f14  mov     [rbp+pUnk], r15
0x180024f18  jmp     short loc_180024F27
0x180024f1a  lea     ecx, [rax+1]
0x180024f1d  lock cmpxchg [rbx+0A0h], ecx
0x180024f25  jz      short loc_180024F36
0x180024f27  mov     eax, [rbx+0A0h]
0x180024f2d  test    eax, eax
0x180024f2f  jg      short loc_180024F1A
0x180024f31  jmp     loc_180025152
0x180024f36  mov     rax, [rbx]
0x180024f39  mov     rdi, [rax]
0x180024f3c  mov     rcx, [rbp+pUnk]
0x180024f40  test    rcx, rcx
0x180024f43  jz      short loc_180024F56
0x180024f45  mov     [rbp+pUnk], r15
0x180024f49  mov     rax, [rcx]
0x180024f4c  mov     rax, [rax+10h]
0x180024f50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f55  nop
0x180024f56  lea     r8, [rbp+pUnk]
0x180024f5a  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180024f61  mov     rcx, rbx
0x180024f64  mov     rax, rdi
0x180024f67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f6c  nop
0x180024f6d  test    eax, eax
0x180024f6f  js      loc_180025152
0x180024f75  mov     rcx, [rbx+90h]
0x180024f7c  mov     [rbp+arg_0], r15
0x180024f80  test    rcx, rcx
0x180024f83  jz      loc_180025103
0x180024f89  mov     rax, [rcx]
0x180024f8c  lea     r8, [rbp+arg_0]
0x180024f90  lea     rdx, _GUID_2fafaaf9_2986_48ee_919d_98f66edf0a31
0x180024f97  mov     rax, [rax+18h]
0x180024f9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024fa0  nop
0x180024fa1  test    eax, eax
0x180024fa3  js      loc_180025103
0x180024fa9  mov     r12d, 1
0x180024faf  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180024fb6  test    rcx, rcx
0x180024fb9  jz      short loc_180024FE9
0x180024fbb  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x180024fc2  movdqu  [rbp+var_10], xmm0
0x180024fc7  mov     rax, [rcx]
0x180024fca  mov     [rsp+70h+mshlflags], r12d
0x180024fcf  mov     [rsp+70h+pvDestContext], rbx
0x180024fd4  lea     r9, [rbp+var_10]
0x180024fd8  lea     r8d, [r12+1]
0x180024fdd  mov     edx, r12d
0x180024fe0  mov     rax, [rax+48h]
0x180024fe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024fe9  mov     [rbp+arg_18], r15
0x180024fed  lea     rdx, [rbp+arg_18]; struct IRpcOptions **
0x180024ff1  mov     rcx, [rbp+arg_0]; struct IUnknown *
0x180024ff5  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@PEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,IRpcOptions * *)
0x180024ffa  mov     [rbp+ppstm], r15
0x180024ffe  mov     [rbp+var_20], r15d
0x180025002  cmp     [rbp+arg_18], r15
0x180025006  jz      short loc_18002504E
0x180025008  cmp     [rbp+arg_0], r15
0x18002500c  jz      short loc_18002504E
0x18002500e  mov     rdi, [rbp+pUnk]
0x180025012  lea     r8, [rbp+ppstm]; ppstm
0x180025016  mov     edx, r12d; fDeleteOnRelease
0x180025019  xor     ecx, ecx; hGlobal
0x18002501b  call    cs:__imp_CreateStreamOnHGlobal
0x180025021  mov     [rbp+var_20], eax
0x180025024  test    eax, eax
0x180025026  js      short loc_180025055
0x180025028  mov     [rsp+70h+mshlflags], r12d; mshlflags
0x18002502d  mov     [rsp+70h+pvDestContext], r15; pvDestContext
0x180025032  xor     r9d, r9d; dwDestContext
0x180025035  mov     r8, rdi; pUnk
0x180025038  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18002503f  mov     rcx, [rbp+ppstm]; pStm
0x180025043  call    cs:__imp_CoMarshalInterface
0x180025049  mov     [rbp+var_20], eax
0x18002504c  jmp     short loc_180025055
0x18002504e  mov     [rbp+var_20], 80004002h
0x180025055  mov     rcx, [rbp+arg_0]
0x180025059  mov     rax, [rcx]
0x18002505c  mov     r8d, r14d
0x18002505f  mov     rdx, [rbp+pUnk]
0x180025063  mov     rax, [rax+18h]
0x180025067  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002506c  mov     r8, [rbx+98h]
0x180025073  mov     rdx, [rbp+arg_0]
0x180025077  mov     ecx, eax
0x180025079  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x18002507e  mov     esi, eax
0x180025080  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180025087  test    rcx, rcx
0x18002508a  jz      short loc_1800250A5
0x18002508c  mov     r9, [rcx]
0x18002508f  mov     rax, [r9+50h]
0x180025093  mov     r9d, r12d
0x180025096  mov     r8d, 2
0x18002509c  mov     edx, r12d
0x18002509f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800250a4  nop
0x1800250a5  cmp     [rbp+var_20], r15d
0x1800250a9  jl      short loc_1800250CF
0x1800250ab  mov     rcx, [rbp+ppstm]
0x1800250af  mov     rdx, r15
0x1800250b2  mov     rax, [rcx]
0x1800250b5  xor     r9d, r9d
0x1800250b8  xor     r8d, r8d
0x1800250bb  mov     rax, [rax+28h]
0x1800250bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800250c4  mov     rcx, [rbp+ppstm]; pStm
0x1800250c8  call    cs:__imp_CoReleaseMarshalData
0x1800250ce  nop
0x1800250cf  mov     rcx, [rbp+ppstm]
0x1800250d3  test    rcx, rcx
0x1800250d6  jz      short loc_1800250E9
0x1800250d8  mov     [rbp+ppstm], r15
0x1800250dc  mov     rax, [rcx]
0x1800250df  mov     rax, [rax+10h]
0x1800250e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800250e8  nop
0x1800250e9  mov     rcx, [rbp+arg_18]
0x1800250ed  test    rcx, rcx
0x1800250f0  jz      short loc_180025103
0x1800250f2  mov     [rbp+arg_18], r15
0x1800250f6  mov     rax, [rcx]
0x1800250f9  mov     rax, [rax+10h]
0x1800250fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025102  nop
0x180025103  or      eax, 0FFFFFFFFh
0x180025106  lock xadd [rbx+0A0h], eax
0x18002510e  cmp     eax, 1
0x180025111  jnz     short loc_180025138
0x180025113  lock or [rsp+70h+var_70], r15d
0x180025118  mov     rcx, [rbx+90h]
0x18002511f  mov     [rbx+90h], r15
0x180025126  test    rcx, rcx
0x180025129  jz      short loc_180025138
0x18002512b  mov     rax, [rcx]
0x18002512e  mov     rax, [rax+10h]
0x180025132  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025137  nop
0x180025138  mov     rcx, [rbp+arg_0]
0x18002513c  test    rcx, rcx
0x18002513f  jz      short loc_180025152
0x180025141  mov     [rbp+arg_0], r15
0x180025145  mov     rax, [rcx]
0x180025148  mov     rax, [rax+10h]
0x18002514c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025151  nop
0x180025152  mov     rcx, [rbp+pUnk]
0x180025156  test    rcx, rcx
0x180025159  jz      short loc_18002516C
0x18002515b  mov     [rbp+pUnk], r15
0x18002515f  mov     rax, [rcx]
0x180025162  mov     rax, [rax+10h]
0x180025166  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002516b  nop
0x18002516c  test    rbx, rbx
0x18002516f  jz      short loc_180025181
0x180025171  mov     rax, [rbx]
0x180025174  mov     rcx, rbx
0x180025177  mov     rax, [rax+10h]
0x18002517b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025180  nop
0x180025181  mov     eax, esi
0x180025183  add     rsp, 70h
0x180025187  pop     r15
0x180025189  pop     r14
0x18002518b  pop     r12
0x18002518d  pop     rdi
0x18002518e  pop     rsi
0x18002518f  pop     rbx
0x180025190  pop     rbp
0x180025191  retn
```
