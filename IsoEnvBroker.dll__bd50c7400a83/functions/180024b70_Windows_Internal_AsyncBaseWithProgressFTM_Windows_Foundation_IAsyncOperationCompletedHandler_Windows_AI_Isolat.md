# Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::AI::IsolationEnvironment::IsolationProvisionResult *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireProgress(int)

- ea: `0x180024b70`
- end: `0x180024e22`
- name: `?FireProgress@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@PEAVIsolationProvisionResult@IsolationEnvironment@AI@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@QEAAJH@Z`
- size: `690`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180029880`

## callees

- `0x180024a88`
- `0x180024b70`
- `0x180025f14`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x180024d58`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x180024d58`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180024cab`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180024cab`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180024cd3`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180024cd3`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::AI::IsolationEnvironment::IsolationProvisionResult *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireProgress(
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
0x180024b70  push    rbp
0x180024b72  push    rbx
0x180024b73  push    rsi
0x180024b74  push    rdi
0x180024b75  push    r12
0x180024b77  push    r14
0x180024b79  push    r15
0x180024b7b  mov     rbp, rsp
0x180024b7e  sub     rsp, 70h
0x180024b82  mov     r14d, edx
0x180024b85  mov     rbx, rcx
0x180024b88  xor     r15d, r15d
0x180024b8b  mov     esi, r15d
0x180024b8e  mov     [rbp+var_30], rcx
0x180024b92  test    rcx, rcx
0x180024b95  jz      short loc_180024BA4
0x180024b97  mov     rax, [rcx]
0x180024b9a  mov     rax, [rax+8]
0x180024b9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ba3  nop
0x180024ba4  mov     [rbp+pUnk], r15
0x180024ba8  jmp     short loc_180024BB7
0x180024baa  lea     ecx, [rax+1]
0x180024bad  lock cmpxchg [rbx+0A0h], ecx
0x180024bb5  jz      short loc_180024BC6
0x180024bb7  mov     eax, [rbx+0A0h]
0x180024bbd  test    eax, eax
0x180024bbf  jg      short loc_180024BAA
0x180024bc1  jmp     loc_180024DE2
0x180024bc6  mov     rax, [rbx]
0x180024bc9  mov     rdi, [rax]
0x180024bcc  mov     rcx, [rbp+pUnk]
0x180024bd0  test    rcx, rcx
0x180024bd3  jz      short loc_180024BE6
0x180024bd5  mov     [rbp+pUnk], r15
0x180024bd9  mov     rax, [rcx]
0x180024bdc  mov     rax, [rax+10h]
0x180024be0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024be5  nop
0x180024be6  lea     r8, [rbp+pUnk]
0x180024bea  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180024bf1  mov     rcx, rbx
0x180024bf4  mov     rax, rdi
0x180024bf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024bfc  nop
0x180024bfd  test    eax, eax
0x180024bff  js      loc_180024DE2
0x180024c05  mov     rcx, [rbx+90h]
0x180024c0c  mov     [rbp+arg_0], r15
0x180024c10  test    rcx, rcx
0x180024c13  jz      loc_180024D93
0x180024c19  mov     rax, [rcx]
0x180024c1c  lea     r8, [rbp+arg_0]
0x180024c20  lea     rdx, _GUID_2fafaaf9_2986_48ee_919d_98f66edf0a31
0x180024c27  mov     rax, [rax+18h]
0x180024c2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c30  nop
0x180024c31  test    eax, eax
0x180024c33  js      loc_180024D93
0x180024c39  mov     r12d, 1
0x180024c3f  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180024c46  test    rcx, rcx
0x180024c49  jz      short loc_180024C79
0x180024c4b  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x180024c52  movdqu  [rbp+var_10], xmm0
0x180024c57  mov     rax, [rcx]
0x180024c5a  mov     [rsp+70h+mshlflags], r12d
0x180024c5f  mov     [rsp+70h+pvDestContext], rbx
0x180024c64  lea     r9, [rbp+var_10]
0x180024c68  lea     r8d, [r12+1]
0x180024c6d  mov     edx, r12d
0x180024c70  mov     rax, [rax+48h]
0x180024c74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c79  mov     [rbp+arg_18], r15
0x180024c7d  lea     rdx, [rbp+arg_18]; struct IRpcOptions **
0x180024c81  mov     rcx, [rbp+arg_0]; struct IUnknown *
0x180024c85  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@PEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,IRpcOptions * *)
0x180024c8a  mov     [rbp+ppstm], r15
0x180024c8e  mov     [rbp+var_20], r15d
0x180024c92  cmp     [rbp+arg_18], r15
0x180024c96  jz      short loc_180024CDE
0x180024c98  cmp     [rbp+arg_0], r15
0x180024c9c  jz      short loc_180024CDE
0x180024c9e  mov     rdi, [rbp+pUnk]
0x180024ca2  lea     r8, [rbp+ppstm]; ppstm
0x180024ca6  mov     edx, r12d; fDeleteOnRelease
0x180024ca9  xor     ecx, ecx; hGlobal
0x180024cab  call    cs:__imp_CreateStreamOnHGlobal
0x180024cb1  mov     [rbp+var_20], eax
0x180024cb4  test    eax, eax
0x180024cb6  js      short loc_180024CE5
0x180024cb8  mov     [rsp+70h+mshlflags], r12d; mshlflags
0x180024cbd  mov     [rsp+70h+pvDestContext], r15; pvDestContext
0x180024cc2  xor     r9d, r9d; dwDestContext
0x180024cc5  mov     r8, rdi; pUnk
0x180024cc8  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180024ccf  mov     rcx, [rbp+ppstm]; pStm
0x180024cd3  call    cs:__imp_CoMarshalInterface
0x180024cd9  mov     [rbp+var_20], eax
0x180024cdc  jmp     short loc_180024CE5
0x180024cde  mov     [rbp+var_20], 80004002h
0x180024ce5  mov     rcx, [rbp+arg_0]
0x180024ce9  mov     rax, [rcx]
0x180024cec  mov     r8d, r14d
0x180024cef  mov     rdx, [rbp+pUnk]
0x180024cf3  mov     rax, [rax+18h]
0x180024cf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024cfc  mov     r8, [rbx+98h]
0x180024d03  mov     rdx, [rbp+arg_0]
0x180024d07  mov     ecx, eax
0x180024d09  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x180024d0e  mov     esi, eax
0x180024d10  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180024d17  test    rcx, rcx
0x180024d1a  jz      short loc_180024D35
0x180024d1c  mov     r9, [rcx]
0x180024d1f  mov     rax, [r9+50h]
0x180024d23  mov     r9d, r12d
0x180024d26  mov     r8d, 2
0x180024d2c  mov     edx, r12d
0x180024d2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d34  nop
0x180024d35  cmp     [rbp+var_20], r15d
0x180024d39  jl      short loc_180024D5F
0x180024d3b  mov     rcx, [rbp+ppstm]
0x180024d3f  mov     rdx, r15
0x180024d42  mov     rax, [rcx]
0x180024d45  xor     r9d, r9d
0x180024d48  xor     r8d, r8d
0x180024d4b  mov     rax, [rax+28h]
0x180024d4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d54  mov     rcx, [rbp+ppstm]; pStm
0x180024d58  call    cs:__imp_CoReleaseMarshalData
0x180024d5e  nop
0x180024d5f  mov     rcx, [rbp+ppstm]
0x180024d63  test    rcx, rcx
0x180024d66  jz      short loc_180024D79
0x180024d68  mov     [rbp+ppstm], r15
0x180024d6c  mov     rax, [rcx]
0x180024d6f  mov     rax, [rax+10h]
0x180024d73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d78  nop
0x180024d79  mov     rcx, [rbp+arg_18]
0x180024d7d  test    rcx, rcx
0x180024d80  jz      short loc_180024D93
0x180024d82  mov     [rbp+arg_18], r15
0x180024d86  mov     rax, [rcx]
0x180024d89  mov     rax, [rax+10h]
0x180024d8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d92  nop
0x180024d93  or      eax, 0FFFFFFFFh
0x180024d96  lock xadd [rbx+0A0h], eax
0x180024d9e  cmp     eax, 1
0x180024da1  jnz     short loc_180024DC8
0x180024da3  lock or [rsp+70h+var_70], r15d
0x180024da8  mov     rcx, [rbx+90h]
0x180024daf  mov     [rbx+90h], r15
0x180024db6  test    rcx, rcx
0x180024db9  jz      short loc_180024DC8
0x180024dbb  mov     rax, [rcx]
0x180024dbe  mov     rax, [rax+10h]
0x180024dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024dc7  nop
0x180024dc8  mov     rcx, [rbp+arg_0]
0x180024dcc  test    rcx, rcx
0x180024dcf  jz      short loc_180024DE2
0x180024dd1  mov     [rbp+arg_0], r15
0x180024dd5  mov     rax, [rcx]
0x180024dd8  mov     rax, [rax+10h]
0x180024ddc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024de1  nop
0x180024de2  mov     rcx, [rbp+pUnk]
0x180024de6  test    rcx, rcx
0x180024de9  jz      short loc_180024DFC
0x180024deb  mov     [rbp+pUnk], r15
0x180024def  mov     rax, [rcx]
0x180024df2  mov     rax, [rax+10h]
0x180024df6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024dfb  nop
0x180024dfc  test    rbx, rbx
0x180024dff  jz      short loc_180024E11
0x180024e01  mov     rax, [rbx]
0x180024e04  mov     rcx, rbx
0x180024e07  mov     rax, [rax+10h]
0x180024e0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e10  nop
0x180024e11  mov     eax, esi
0x180024e13  add     rsp, 70h
0x180024e17  pop     r15
0x180024e19  pop     r14
0x180024e1b  pop     r12
0x180024e1d  pop     rdi
0x180024e1e  pop     rsi
0x180024e1f  pop     rbx
0x180024e20  pop     rbp
0x180024e21  retn
```
