# Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireProgress(Windows::System::Diagnostics::DiagnosticActionState)

- ea: `0x18000ae40`
- end: `0x18000b0f2`
- name: `?FireProgress@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@U?$IAsyncOperationProgressHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@23@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@QEAAJW4DiagnosticActionState@Diagnostics@System@3@@Z`
- size: `690`
- prototype: `__int64 __fastcall(_DWORD *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000e530`

## callees

- `0x18000ad58`
- `0x18000ae40`
- `0x18000c2a4`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18000af7b`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18000af7b`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x18000b028`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x18000b028`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18000afa3`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18000afa3`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireProgress(
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
      if ( v6(a1, &GUID_bb5d493e_74e9_57a1_8c4c_923e0dc4565b, &pUnk) >= 0 )
      {
        v8 = *((_QWORD *)a1 + 18);
        v22 = 0;
        if ( v8
          && (*(int (__fastcall **)(__int64, GUID *, struct IUnknown **))(*(_QWORD *)v8 + 24LL))(
               v8,
               &GUID_a0422898_b50a_52e3_b461_53989308be12,
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
0x18000ae40  push    rbp
0x18000ae42  push    rbx
0x18000ae43  push    rsi
0x18000ae44  push    rdi
0x18000ae45  push    r12
0x18000ae47  push    r14
0x18000ae49  push    r15
0x18000ae4b  mov     rbp, rsp
0x18000ae4e  sub     rsp, 70h
0x18000ae52  mov     r14d, edx
0x18000ae55  mov     rbx, rcx
0x18000ae58  xor     r15d, r15d
0x18000ae5b  mov     esi, r15d
0x18000ae5e  mov     [rbp+var_30], rcx
0x18000ae62  test    rcx, rcx
0x18000ae65  jz      short loc_18000AE74
0x18000ae67  mov     rax, [rcx]
0x18000ae6a  mov     rax, [rax+8]
0x18000ae6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae73  nop
0x18000ae74  mov     [rbp+pUnk], r15
0x18000ae78  jmp     short loc_18000AE87
0x18000ae7a  lea     ecx, [rax+1]
0x18000ae7d  lock cmpxchg [rbx+0A0h], ecx
0x18000ae85  jz      short loc_18000AE96
0x18000ae87  mov     eax, [rbx+0A0h]
0x18000ae8d  test    eax, eax
0x18000ae8f  jg      short loc_18000AE7A
0x18000ae91  jmp     loc_18000B0B2
0x18000ae96  mov     rax, [rbx]
0x18000ae99  mov     rdi, [rax]
0x18000ae9c  mov     rcx, [rbp+pUnk]
0x18000aea0  test    rcx, rcx
0x18000aea3  jz      short loc_18000AEB6
0x18000aea5  mov     [rbp+pUnk], r15
0x18000aea9  mov     rax, [rcx]
0x18000aeac  mov     rax, [rax+10h]
0x18000aeb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aeb5  nop
0x18000aeb6  lea     r8, [rbp+pUnk]
0x18000aeba  lea     rdx, _GUID_bb5d493e_74e9_57a1_8c4c_923e0dc4565b
0x18000aec1  mov     rcx, rbx
0x18000aec4  mov     rax, rdi
0x18000aec7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aecc  nop
0x18000aecd  test    eax, eax
0x18000aecf  js      loc_18000B0B2
0x18000aed5  mov     rcx, [rbx+90h]
0x18000aedc  mov     [rbp+arg_0], r15
0x18000aee0  test    rcx, rcx
0x18000aee3  jz      loc_18000B063
0x18000aee9  mov     rax, [rcx]
0x18000aeec  lea     r8, [rbp+arg_0]
0x18000aef0  lea     rdx, _GUID_a0422898_b50a_52e3_b461_53989308be12
0x18000aef7  mov     rax, [rax+18h]
0x18000aefb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af00  nop
0x18000af01  test    eax, eax
0x18000af03  js      loc_18000B063
0x18000af09  mov     r12d, 1
0x18000af0f  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18000af16  test    rcx, rcx
0x18000af19  jz      short loc_18000AF49
0x18000af1b  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x18000af22  movdqu  [rbp+var_10], xmm0
0x18000af27  mov     rax, [rcx]
0x18000af2a  mov     [rsp+70h+mshlflags], r12d
0x18000af2f  mov     [rsp+70h+pvDestContext], rbx
0x18000af34  lea     r9, [rbp+var_10]
0x18000af38  lea     r8d, [r12+1]
0x18000af3d  mov     edx, r12d
0x18000af40  mov     rax, [rax+48h]
0x18000af44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af49  mov     [rbp+arg_18], r15
0x18000af4d  lea     rdx, [rbp+arg_18]; struct IRpcOptions **
0x18000af51  mov     rcx, [rbp+arg_0]; struct IUnknown *
0x18000af55  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@PEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,IRpcOptions * *)
0x18000af5a  mov     [rbp+ppstm], r15
0x18000af5e  mov     [rbp+var_20], r15d
0x18000af62  cmp     [rbp+arg_18], r15
0x18000af66  jz      short loc_18000AFAE
0x18000af68  cmp     [rbp+arg_0], r15
0x18000af6c  jz      short loc_18000AFAE
0x18000af6e  mov     rdi, [rbp+pUnk]
0x18000af72  lea     r8, [rbp+ppstm]; ppstm
0x18000af76  mov     edx, r12d; fDeleteOnRelease
0x18000af79  xor     ecx, ecx; hGlobal
0x18000af7b  call    cs:__imp_CreateStreamOnHGlobal
0x18000af81  mov     [rbp+var_20], eax
0x18000af84  test    eax, eax
0x18000af86  js      short loc_18000AFB5
0x18000af88  mov     [rsp+70h+mshlflags], r12d; mshlflags
0x18000af8d  mov     [rsp+70h+pvDestContext], r15; pvDestContext
0x18000af92  xor     r9d, r9d; dwDestContext
0x18000af95  mov     r8, rdi; pUnk
0x18000af98  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18000af9f  mov     rcx, [rbp+ppstm]; pStm
0x18000afa3  call    cs:__imp_CoMarshalInterface
0x18000afa9  mov     [rbp+var_20], eax
0x18000afac  jmp     short loc_18000AFB5
0x18000afae  mov     [rbp+var_20], 80004002h
0x18000afb5  mov     rcx, [rbp+arg_0]
0x18000afb9  mov     rax, [rcx]
0x18000afbc  mov     r8d, r14d
0x18000afbf  mov     rdx, [rbp+pUnk]
0x18000afc3  mov     rax, [rax+18h]
0x18000afc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afcc  mov     r8, [rbx+98h]
0x18000afd3  mov     rdx, [rbp+arg_0]
0x18000afd7  mov     ecx, eax
0x18000afd9  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x18000afde  mov     esi, eax
0x18000afe0  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18000afe7  test    rcx, rcx
0x18000afea  jz      short loc_18000B005
0x18000afec  mov     r9, [rcx]
0x18000afef  mov     rax, [r9+50h]
0x18000aff3  mov     r9d, r12d
0x18000aff6  mov     r8d, 2
0x18000affc  mov     edx, r12d
0x18000afff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b004  nop
0x18000b005  cmp     [rbp+var_20], r15d
0x18000b009  jl      short loc_18000B02F
0x18000b00b  mov     rcx, [rbp+ppstm]
0x18000b00f  mov     rdx, r15
0x18000b012  mov     rax, [rcx]
0x18000b015  xor     r9d, r9d
0x18000b018  xor     r8d, r8d
0x18000b01b  mov     rax, [rax+28h]
0x18000b01f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b024  mov     rcx, [rbp+ppstm]; pStm
0x18000b028  call    cs:__imp_CoReleaseMarshalData
0x18000b02e  nop
0x18000b02f  mov     rcx, [rbp+ppstm]
0x18000b033  test    rcx, rcx
0x18000b036  jz      short loc_18000B049
0x18000b038  mov     [rbp+ppstm], r15
0x18000b03c  mov     rax, [rcx]
0x18000b03f  mov     rax, [rax+10h]
0x18000b043  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b048  nop
0x18000b049  mov     rcx, [rbp+arg_18]
0x18000b04d  test    rcx, rcx
0x18000b050  jz      short loc_18000B063
0x18000b052  mov     [rbp+arg_18], r15
0x18000b056  mov     rax, [rcx]
0x18000b059  mov     rax, [rax+10h]
0x18000b05d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b062  nop
0x18000b063  or      eax, 0FFFFFFFFh
0x18000b066  lock xadd [rbx+0A0h], eax
0x18000b06e  cmp     eax, 1
0x18000b071  jnz     short loc_18000B098
0x18000b073  lock or [rsp+70h+var_70], r15d
0x18000b078  mov     rcx, [rbx+90h]
0x18000b07f  mov     [rbx+90h], r15
0x18000b086  test    rcx, rcx
0x18000b089  jz      short loc_18000B098
0x18000b08b  mov     rax, [rcx]
0x18000b08e  mov     rax, [rax+10h]
0x18000b092  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b097  nop
0x18000b098  mov     rcx, [rbp+arg_0]
0x18000b09c  test    rcx, rcx
0x18000b09f  jz      short loc_18000B0B2
0x18000b0a1  mov     [rbp+arg_0], r15
0x18000b0a5  mov     rax, [rcx]
0x18000b0a8  mov     rax, [rax+10h]
0x18000b0ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0b1  nop
0x18000b0b2  mov     rcx, [rbp+pUnk]
0x18000b0b6  test    rcx, rcx
0x18000b0b9  jz      short loc_18000B0CC
0x18000b0bb  mov     [rbp+pUnk], r15
0x18000b0bf  mov     rax, [rcx]
0x18000b0c2  mov     rax, [rax+10h]
0x18000b0c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0cb  nop
0x18000b0cc  test    rbx, rbx
0x18000b0cf  jz      short loc_18000B0E1
0x18000b0d1  mov     rax, [rbx]
0x18000b0d4  mov     rcx, rbx
0x18000b0d7  mov     rax, [rax+10h]
0x18000b0db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0e0  nop
0x18000b0e1  mov     eax, esi
0x18000b0e3  add     rsp, 70h
0x18000b0e7  pop     r15
0x18000b0e9  pop     r14
0x18000b0eb  pop     r12
0x18000b0ed  pop     rdi
0x18000b0ee  pop     rsi
0x18000b0ef  pop     rbx
0x18000b0f0  pop     rbp
0x18000b0f1  retn
```
