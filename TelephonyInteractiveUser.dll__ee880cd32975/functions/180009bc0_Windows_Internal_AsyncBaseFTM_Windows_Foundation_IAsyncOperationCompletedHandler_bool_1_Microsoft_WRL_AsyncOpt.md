# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x180009bc0`
- end: `0x180009e9c`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `732`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180009eb0`
- `0x18000c900`
- `0x180010478`

## callees

- `0x180001dc0`
- `0x180009bc0`
- `0x18000a0f4`
- `0x18000b4d4`
- `0x18000f610`
- `0x18000f720`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180009d24`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180009d24`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180009d4f`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180009d4f`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x180009e02`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x180009e02`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
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
  Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(
    a1,
    1);
  if ( *(int *)(a1 + 136) > 0 && _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 16), v3) + 1 == v3 )
  {
    if ( a1 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
    pUnk = 0;
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(a1);
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
0x180009bc0  mov     [rsp-18h+arg_8], rbx
0x180009bc5  mov     [rsp-18h+arg_10], rsi
0x180009bca  push    rbp
0x180009bcb  push    rdi
0x180009bcc  push    r14
0x180009bce  mov     rbp, rsp
0x180009bd1  sub     rsp, 80h
0x180009bd8  mov     rax, cs:__security_cookie
0x180009bdf  xor     rax, rsp
0x180009be2  mov     [rbp+var_8], rax
0x180009be6  xor     r14d, r14d
0x180009be9  mov     rbx, rcx
0x180009bec  mov     esi, r14d
0x180009bef  lea     edx, [r14+1]
0x180009bf3  call    ?TransitionToState@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x180009bf8  cmp     [rbx+88h], r14d
0x180009bff  jle     loc_180009E76
0x180009c05  mov     eax, edx
0x180009c07  lock xadd [rbx+10h], eax
0x180009c0c  inc     eax
0x180009c0e  cmp     eax, edx
0x180009c10  jnz     loc_180009E76
0x180009c16  test    rbx, rbx
0x180009c19  jz      short loc_180009C2A
0x180009c1b  mov     rax, [rbx]
0x180009c1e  mov     rcx, rbx
0x180009c21  mov     rax, [rax+8]
0x180009c25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c2a  mov     rcx, rbx
0x180009c2d  mov     [rbp+pUnk], r14
0x180009c31  call    ?TraceOperationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x180009c36  mov     rax, [rbx]
0x180009c39  mov     rcx, [rbp+pUnk]
0x180009c3d  mov     rdi, [rax]
0x180009c40  test    rcx, rcx
0x180009c43  jz      short loc_180009C55
0x180009c45  mov     [rbp+pUnk], r14
0x180009c49  mov     rax, [rcx]
0x180009c4c  mov     rax, [rax+10h]
0x180009c50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c55  lea     r8, [rbp+pUnk]
0x180009c59  mov     rcx, rbx
0x180009c5c  lea     rdx, _GUID_cdb5efb3_5788_509d_9be1_71ccb8a3362a
0x180009c63  mov     rax, rdi
0x180009c66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c6b  test    eax, eax
0x180009c6d  js      loc_180009E4E
0x180009c73  mov     ecx, [rbx+38h]
0x180009c76  mov     [rbp+var_30], 0FFFFFFFEh
0x180009c7d  mov     eax, [rbp+var_30]
0x180009c80  lock cmpxchg [rbp+var_30], ecx
0x180009c85  mov     rcx, [rbx+78h]
0x180009c89  mov     [rbp+var_28], r14
0x180009c8d  test    rcx, rcx
0x180009c90  jz      loc_180009E35
0x180009c96  mov     rax, [rcx]
0x180009c99  lea     r8, [rbp+var_28]
0x180009c9d  lea     rdx, _GUID_c1d3d1a2_ae17_5a5f_b5a2_bdcc8844889a
0x180009ca4  mov     rax, [rax+18h]
0x180009ca8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009cad  test    eax, eax
0x180009caf  js      loc_180009E35
0x180009cb5  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180009cbc  test    rcx, rcx
0x180009cbf  jz      short loc_180009CED
0x180009cc1  mov     rax, [rcx]
0x180009cc4  lea     r9, [rbp+var_40]
0x180009cc8  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x180009ccf  xor     edx, edx
0x180009cd1  mov     [rsp+80h+mshlflags], r14d
0x180009cd6  mov     [rsp+80h+pvDestContext], rbx
0x180009cdb  mov     rax, [rax+48h]
0x180009cdf  movdqu  xmmword ptr [rbp+var_40], xmm0
0x180009ce4  lea     r8d, [rdx+2]
0x180009ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ced  mov     rcx, [rbp+var_28]; struct IUnknown *
0x180009cf1  lea     rdx, [rbp+var_40]; struct IRpcOptions **
0x180009cf5  mov     [rbp+var_40], r14
0x180009cf9  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@PEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,IRpcOptions * *)
0x180009cfe  mov     rdi, [rbp+var_40]
0x180009d02  mov     [rbp+var_10], r14
0x180009d06  mov     [rbp+ppstm], r14
0x180009d0a  test    rdi, rdi
0x180009d0d  jz      short loc_180009D5A
0x180009d0f  cmp     [rbp+var_28], r14
0x180009d13  jz      short loc_180009D5A
0x180009d15  mov     rsi, [rbp+pUnk]
0x180009d19  lea     r8, [rbp+ppstm]; ppstm
0x180009d1d  mov     edx, 1; fDeleteOnRelease
0x180009d22  xor     ecx, ecx; hGlobal
0x180009d24  call    cs:__imp_CreateStreamOnHGlobal
0x180009d2a  mov     dword ptr [rbp+var_10], eax
0x180009d2d  test    eax, eax
0x180009d2f  js      short loc_180009D61
0x180009d31  mov     rcx, [rbp+ppstm]; pStm
0x180009d35  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180009d3c  mov     [rsp+80h+mshlflags], 1; mshlflags
0x180009d44  xor     r9d, r9d; dwDestContext
0x180009d47  mov     r8, rsi; pUnk
0x180009d4a  mov     [rsp+80h+pvDestContext], r14; pvDestContext
0x180009d4f  call    cs:__imp_CoMarshalInterface
0x180009d55  mov     dword ptr [rbp+var_10], eax
0x180009d58  jmp     short loc_180009D61
0x180009d5a  mov     dword ptr [rbp+var_10], 80004002h
0x180009d61  mov     rcx, [rbp+var_28]
0x180009d65  mov     r8d, [rbp+var_30]
0x180009d69  mov     rdx, [rbp+pUnk]
0x180009d6d  mov     rax, [rcx]
0x180009d70  mov     rax, [rax+18h]
0x180009d74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d79  mov     r8, [rbx+80h]
0x180009d80  mov     ecx, eax
0x180009d82  mov     rdx, [rbp+var_28]
0x180009d86  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x180009d8b  mov     esi, eax
0x180009d8d  or      ecx, 0FFFFFFFFh
0x180009d90  lock xadd [rbx+88h], ecx
0x180009d98  cmp     ecx, 1
0x180009d9b  jnz     short loc_180009DBE
0x180009d9d  lock or [rsp+80h+var_80], r14d
0x180009da2  mov     rdx, [rbx+78h]
0x180009da6  mov     [rbx+78h], r14
0x180009daa  test    rdx, rdx
0x180009dad  jz      short loc_180009DBE
0x180009daf  mov     rcx, [rdx]
0x180009db2  mov     rax, [rcx+10h]
0x180009db6  mov     rcx, rdx
0x180009db9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009dbe  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180009dc5  test    rcx, rcx
0x180009dc8  jz      short loc_180009DDF
0x180009dca  mov     rax, [rcx]
0x180009dcd  xor     r9d, r9d
0x180009dd0  xor     edx, edx
0x180009dd2  mov     rax, [rax+50h]
0x180009dd6  lea     r8d, [r9+2]
0x180009dda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ddf  cmp     dword ptr [rbp+var_10], r14d
0x180009de3  jl      short loc_180009E08
0x180009de5  mov     rcx, [rbp+ppstm]
0x180009de9  mov     rdx, r14
0x180009dec  xor     r9d, r9d
0x180009def  xor     r8d, r8d
0x180009df2  mov     rax, [rcx]
0x180009df5  mov     rax, [rax+28h]
0x180009df9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009dfe  mov     rcx, [rbp+ppstm]; pStm
0x180009e02  call    cs:__imp_CoReleaseMarshalData
0x180009e08  mov     rcx, [rbp+ppstm]
0x180009e0c  test    rcx, rcx
0x180009e0f  jz      short loc_180009E21
0x180009e11  mov     [rbp+ppstm], r14
0x180009e15  mov     rax, [rcx]
0x180009e18  mov     rax, [rax+10h]
0x180009e1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e21  test    rdi, rdi
0x180009e24  jz      short loc_180009E35
0x180009e26  mov     rax, [rdi]
0x180009e29  mov     rcx, rdi
0x180009e2c  mov     rax, [rax+10h]
0x180009e30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e35  mov     rcx, [rbp+var_28]
0x180009e39  test    rcx, rcx
0x180009e3c  jz      short loc_180009E4E
0x180009e3e  mov     [rbp+var_28], r14
0x180009e42  mov     rax, [rcx]
0x180009e45  mov     rax, [rax+10h]
0x180009e49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e4e  mov     rcx, [rbp+pUnk]
0x180009e52  test    rcx, rcx
0x180009e55  jz      short loc_180009E67
0x180009e57  mov     [rbp+pUnk], r14
0x180009e5b  mov     rax, [rcx]
0x180009e5e  mov     rax, [rax+10h]
0x180009e62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e67  mov     rax, [rbx]
0x180009e6a  mov     rcx, rbx
0x180009e6d  mov     rax, [rax+10h]
0x180009e71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e76  mov     eax, esi
0x180009e78  mov     rcx, [rbp+var_8]
0x180009e7c  xor     rcx, rsp; StackCookie
0x180009e7f  call    __security_check_cookie
0x180009e84  lea     r11, [rsp+80h+var_s0]
0x180009e8c  mov     rbx, [r11+28h]
0x180009e90  mov     rsi, [r11+30h]
0x180009e94  mov     rsp, r11
0x180009e97  pop     r14
0x180009e99  pop     rdi
0x180009e9a  pop     rbp
0x180009e9b  retn
```
