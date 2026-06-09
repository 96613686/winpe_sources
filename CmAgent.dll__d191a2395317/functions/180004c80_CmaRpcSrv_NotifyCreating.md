# CmaRpcSrv_NotifyCreating

- ea: `0x180004c80`
- end: `0x180004e28`
- name: `CmaRpcSrv_NotifyCreating`
- size: `424`
- prototype: `RPC_STATUS __fastcall(PRPC_ASYNC_STATE pAsync, __int64, __int128 *, __int128 *, __int64, int, __int64, __int64, int Reply)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004c80`
- `0x1800178e0`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x180004e11`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180004e11`

## pseudocode

```c
RPC_STATUS __fastcall CmaRpcSrv_NotifyCreating(
        PRPC_ASYNC_STATE pAsync,
        __int64 a2,
        __int128 *a3,
        __int128 *a4,
        __int64 a5,
        int a6,
        __int64 a7,
        __int64 a8,
        int Reply)
{
  __int128 v10; // xmm1
  int v11; // edx
  __int128 v12; // xmm2
  int v13; // r8d
  __int128 v14; // xmm0
  int v15; // eax
  __int64 v16; // r9
  __int128 v18; // [rsp+40h] [rbp-68h] BYREF
  int v19; // [rsp+50h] [rbp-58h]
  __int128 v20; // [rsp+60h] [rbp-48h] BYREF
  int v21; // [rsp+70h] [rbp-38h]
  __int128 v22; // [rsp+80h] [rbp-28h] BYREF
  int v23; // [rsp+90h] [rbp-18h]

  v10 = 0;
  v11 = 0;
  v18 = 0;
  v19 = 0;
  if ( a3 )
  {
    v18 = *a3;
    LOBYTE(v19) = 1;
    v11 = v19;
    v10 = v18;
  }
  v12 = 0;
  v13 = 0;
  v18 = 0;
  v19 = 0;
  if ( a4 )
  {
    v18 = *a4;
    LOBYTE(v19) = 1;
    v13 = v19;
    v12 = v18;
  }
  v14 = 0;
  v15 = 0;
  v18 = 0;
  v19 = 0;
  v16 = 0;
  if ( a5 )
  {
    LOBYTE(v18) = *(_BYTE *)a5;
    *(_QWORD *)((char *)&v18 + 1) = *(_QWORD *)(a5 + 1);
    *(_DWORD *)((char *)&v18 + 9) = *(_DWORD *)(a5 + 9);
    *(_WORD *)((char *)&v18 + 13) = *(_WORD *)(a5 + 13);
    HIBYTE(v18) = *(_BYTE *)(a5 + 15);
    LOBYTE(v19) = 1;
    LODWORD(a5) = a6;
    BYTE4(a5) = 1;
    v16 = a5;
    v15 = v19;
    v14 = v18;
  }
  v18 = v14;
  v19 = v15;
  v20 = v12;
  v21 = v13;
  v22 = v10;
  v23 = v11;
  Reply = Container::Manager::Agent::Core::NotifyCreating(&v22, &v20, &v18, v16, a7, a8, Reply != 0);
  return RpcAsyncCompleteCall(pAsync, &Reply);
}

```

## disassembly

```asm
0x180004c80  push    rbx
0x180004c82  sub     rsp, 0A0h
0x180004c89  mov     rbx, rcx
0x180004c8c  xorps   xmm1, xmm1
0x180004c8f  xor     edx, edx
0x180004c91  movups  [rsp+0A8h+var_68], xmm1
0x180004c96  mov     [rsp+0A8h+var_58], edx
0x180004c9a  test    r8, r8
0x180004c9d  jz      short loc_180004CDA
0x180004c9f  mov     al, [r8]
0x180004ca2  mov     byte ptr [rsp+0A8h+var_68], al
0x180004ca6  movsd   xmm0, qword ptr [r8+1]
0x180004cac  movsd   qword ptr [rsp+0A8h+var_68+1], xmm0
0x180004cb2  mov     eax, [r8+9]
0x180004cb6  mov     dword ptr [rsp+0A8h+var_68+9], eax
0x180004cba  movzx   eax, word ptr [r8+0Dh]
0x180004cbf  mov     word ptr [rsp+0A8h+var_68+0Dh], ax
0x180004cc4  mov     al, [r8+0Fh]
0x180004cc8  mov     byte ptr [rsp+0A8h+var_68+0Fh], al
0x180004ccc  mov     byte ptr [rsp+0A8h+var_58], 1
0x180004cd1  mov     edx, [rsp+0A8h+var_58]
0x180004cd5  movups  xmm1, [rsp+0A8h+var_68]
0x180004cda  xorps   xmm2, xmm2
0x180004cdd  xor     r8d, r8d
0x180004ce0  movups  [rsp+0A8h+var_68], xmm2
0x180004ce5  mov     [rsp+0A8h+var_58], r8d
0x180004cea  test    r9, r9
0x180004ced  jz      short loc_180004D2B
0x180004cef  mov     al, [r9]
0x180004cf2  mov     byte ptr [rsp+0A8h+var_68], al
0x180004cf6  movsd   xmm0, qword ptr [r9+1]
0x180004cfc  movsd   qword ptr [rsp+0A8h+var_68+1], xmm0
0x180004d02  mov     eax, [r9+9]
0x180004d06  mov     dword ptr [rsp+0A8h+var_68+9], eax
0x180004d0a  movzx   eax, word ptr [r9+0Dh]
0x180004d0f  mov     word ptr [rsp+0A8h+var_68+0Dh], ax
0x180004d14  mov     al, [r9+0Fh]
0x180004d18  mov     byte ptr [rsp+0A8h+var_68+0Fh], al
0x180004d1c  mov     byte ptr [rsp+0A8h+var_58], 1
0x180004d21  mov     r8d, [rsp+0A8h+var_58]
0x180004d26  movups  xmm2, [rsp+0A8h+var_68]
0x180004d2b  xorps   xmm0, xmm0
0x180004d2e  xor     eax, eax
0x180004d30  movups  [rsp+0A8h+var_68], xmm0
0x180004d35  mov     [rsp+0A8h+var_58], eax
0x180004d39  xor     r9d, r9d
0x180004d3c  mov     rcx, [rsp+0A8h+arg_20]
0x180004d44  test    rcx, rcx
0x180004d47  jz      short loc_180004D9D
0x180004d49  mov     al, [rcx]
0x180004d4b  mov     byte ptr [rsp+0A8h+var_68], al
0x180004d4f  movsd   xmm0, qword ptr [rcx+1]
0x180004d54  movsd   qword ptr [rsp+0A8h+var_68+1], xmm0
0x180004d5a  mov     eax, [rcx+9]
0x180004d5d  mov     dword ptr [rsp+0A8h+var_68+9], eax
0x180004d61  movzx   eax, word ptr [rcx+0Dh]
0x180004d65  mov     word ptr [rsp+0A8h+var_68+0Dh], ax
0x180004d6a  mov     al, [rcx+0Fh]
0x180004d6d  mov     byte ptr [rsp+0A8h+var_68+0Fh], al
0x180004d71  mov     byte ptr [rsp+0A8h+var_58], 1
0x180004d76  mov     eax, [rsp+0A8h+arg_28]
0x180004d7d  mov     dword ptr [rsp+0A8h+arg_20], eax
0x180004d84  mov     byte ptr [rsp+0A8h+arg_20+4], 1
0x180004d8c  mov     r9, [rsp+0A8h+arg_20]
0x180004d94  mov     eax, [rsp+0A8h+var_58]
0x180004d98  movups  xmm0, [rsp+0A8h+var_68]
0x180004d9d  movaps  [rsp+0A8h+var_68], xmm0
0x180004da2  mov     [rsp+0A8h+var_58], eax
0x180004da6  movaps  [rsp+0A8h+var_48], xmm2
0x180004dab  mov     [rsp+0A8h+var_38], r8d
0x180004db0  movaps  [rsp+0A8h+var_28], xmm1
0x180004db8  mov     [rsp+0A8h+var_18], edx
0x180004dbf  cmp     [rsp+0A8h+Reply], 0
0x180004dc7  setnz   al
0x180004dca  mov     [rsp+0A8h+var_78], al
0x180004dce  mov     rax, [rsp+0A8h+arg_38]
0x180004dd6  mov     [rsp+0A8h+var_80], rax
0x180004ddb  mov     rax, [rsp+0A8h+arg_30]
0x180004de3  mov     [rsp+0A8h+var_88], rax
0x180004de8  lea     r8, [rsp+0A8h+var_68]
0x180004ded  lea     rdx, [rsp+0A8h+var_48]
0x180004df2  lea     rcx, [rsp+0A8h+var_28]
0x180004dfa  call    ?NotifyCreating@Core@Agent@Manager@Container@@YAJV?$optional@U_GUID@@@utl@@00V?$optional@K@6@PEAU_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION@@PEAU_CMA_HOT_PATCH_MIRRORING_INFORMATION@@_N@Z; Container::Manager::Agent::Core::NotifyCreating(utl::optional<_GUID>,utl::optional<_GUID>,utl::optional<_GUID>,utl::optional<ulong>,_CMA_RUNTIME_VELOCITY_MIRRORING_INFORMATION *,_CMA_HOT_PATCH_MIRRORING_INFORMATION *,bool)
0x180004dff  mov     [rsp+0A8h+Reply], eax
0x180004e06  lea     rdx, [rsp+0A8h+Reply]; Reply
0x180004e0e  mov     rcx, rbx; pAsync
0x180004e11  call    cs:__imp_RpcAsyncCompleteCall
0x180004e18  nop     dword ptr [rax+rax+00h]
0x180004e1d  nop
0x180004e1e  add     rsp, 0A0h
0x180004e25  pop     rbx
0x180004e26  retn
```
