# CDevNotify::GetNotification(_RPC_ASYNC_STATE *,__MIDL_DsmRpcNotify_0002 *)

- ea: `0x180027e48`
- end: `0x180027fb1`
- name: `?GetNotification@CDevNotify@@QEAAXPEAU_RPC_ASYNC_STATE@@PEAU__MIDL_DsmRpcNotify_0002@@@Z`
- size: `361`
- prototype: `void __fastcall(CDevNotify *__hidden this, PRPC_ASYNC_STATE pAsync, struct __MIDL_DsmRpcNotify_0002 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002dc60`

## callees

- `0x180022070`
- `0x180027e48`
- `0x180028588`
- `0x180028984`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180027f3c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180027f3c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180027e69`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180027e69`
- `RPCRT4!RpcAsyncAbortCall` at `0x180027f94`
- `RPCRT4!RpcAsyncAbortCall` at `0x180027f94`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180027f57`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180027f57`

## pseudocode

```c
void __fastcall CDevNotify::GetNotification(
        RTL_SRWLOCK *this,
        PRPC_ASYNC_STATE pAsync,
        struct __MIDL_DsmRpcNotify_0002 *a3)
{
  struct _RPC_ASYNC_STATE *v3; // rsi
  PRPC_ASYNC_STATE v7; // rbp
  PVOID *v8; // rcx
  PVOID Ptr; // r9
  unsigned int v10; // eax
  int v11; // [rsp+20h] [rbp-28h]
  int v12; // [rsp+28h] [rbp-20h]
  int Reply; // [rsp+50h] [rbp+8h] BYREF

  v3 = 0;
  AcquireSRWLockExclusive(this);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_i(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_f604d5904fe1351d0eb0f737344b07e9_Traceguids, this, v11, v12);
  if ( (int)CDevNotify::_SupplyNotification((CDevNotify *)this, a3) < 0 )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    v7 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      WPP_SF_i(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        &WPP_f604d5904fe1351d0eb0f737344b07e9_Traceguids,
        pAsync,
        v11,
        v12);
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    Ptr = this[2].Ptr;
    if ( Ptr )
    {
      if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x20) != 0 )
        WPP_SF_i(v8[2], 15, &WPP_f604d5904fe1351d0eb0f737344b07e9_Traceguids, Ptr, v11, v12);
      v3 = (struct _RPC_ASYNC_STATE *)this[2].Ptr;
    }
    this[2].Ptr = pAsync;
    this[1].Ptr = a3;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_i(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        &WPP_f604d5904fe1351d0eb0f737344b07e9_Traceguids,
        pAsync,
        v11,
        v12);
    v7 = pAsync;
  }
  ReleaseSRWLockExclusive(this);
  if ( v7 )
  {
    Reply = 0;
    v10 = RpcAsyncCompleteCall(pAsync, &Reply);
    if ( v10 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_f604d5904fe1351d0eb0f737344b07e9_Traceguids, v10);
    }
  }
  if ( v3 )
    RpcAsyncAbortCall(v3, 0x80004004);
}

```

## disassembly

```asm
0x180027e48  mov     [rsp+arg_8], rbx
0x180027e4d  mov     [rsp+arg_10], rbp
0x180027e52  push    rsi
0x180027e53  push    rdi
0x180027e54  push    r12
0x180027e56  push    r13
0x180027e58  push    r14
0x180027e5a  sub     rsp, 20h
0x180027e5e  xor     esi, esi
0x180027e60  mov     r14, r8
0x180027e63  mov     rdi, rdx
0x180027e66  mov     rbx, rcx
0x180027e69  call    cs:__imp_AcquireSRWLockExclusive
0x180027e6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180027e76  lea     r12, WPP_GLOBAL_Control
0x180027e7d  lea     r13, WPP_f604d5904fe1351d0eb0f737344b07e9_Traceguids
0x180027e84  cmp     rcx, r12
0x180027e87  jz      short loc_180027EA1
0x180027e89  test    byte ptr [rcx+1Ch], 20h
0x180027e8d  jz      short loc_180027EA1
0x180027e8f  mov     rcx, [rcx+10h]
0x180027e93  lea     edx, [rsi+0Ch]
0x180027e96  mov     r9, rbx
0x180027e99  mov     r8, r13
0x180027e9c  call    WPP_SF_i
0x180027ea1  mov     rdx, r14; struct __MIDL_DsmRpcNotify_0002 *
0x180027ea4  mov     rcx, rbx; this
0x180027ea7  call    ?_SupplyNotification@CDevNotify@@AEAAJPEAU__MIDL_DsmRpcNotify_0002@@@Z; CDevNotify::_SupplyNotification(__MIDL_DsmRpcNotify_0002 *)
0x180027eac  test    eax, eax
0x180027eae  js      short loc_180027EDB
0x180027eb0  mov     rcx, cs:WPP_GLOBAL_Control
0x180027eb7  cmp     rcx, r12
0x180027eba  jz      short loc_180027ED6
0x180027ebc  test    byte ptr [rcx+1Ch], 20h
0x180027ec0  jz      short loc_180027ED6
0x180027ec2  mov     rcx, [rcx+10h]
0x180027ec6  mov     edx, 0Dh
0x180027ecb  mov     r9, rdi
0x180027ece  mov     r8, r13
0x180027ed1  call    WPP_SF_i
0x180027ed6  mov     rbp, rdi
0x180027ed9  jmp     short loc_180027F39
0x180027edb  mov     rcx, cs:WPP_GLOBAL_Control
0x180027ee2  xor     ebp, ebp
0x180027ee4  cmp     rcx, r12
0x180027ee7  jz      short loc_180027F08
0x180027ee9  test    byte ptr [rcx+1Ch], 20h
0x180027eed  jz      short loc_180027F08
0x180027eef  mov     rcx, [rcx+10h]
0x180027ef3  lea     edx, [rbp+0Eh]
0x180027ef6  mov     r9, rdi
0x180027ef9  mov     r8, r13
0x180027efc  call    WPP_SF_i
0x180027f01  mov     rcx, cs:WPP_GLOBAL_Control
0x180027f08  mov     r9, [rbx+10h]
0x180027f0c  test    r9, r9
0x180027f0f  jz      short loc_180027F31
0x180027f11  cmp     rcx, r12
0x180027f14  jz      short loc_180027F2D
0x180027f16  test    byte ptr [rcx+1Ch], 20h
0x180027f1a  jz      short loc_180027F2D
0x180027f1c  mov     rcx, [rcx+10h]
0x180027f20  mov     edx, 0Fh
0x180027f25  mov     r8, r13
0x180027f28  call    WPP_SF_i
0x180027f2d  mov     rsi, [rbx+10h]
0x180027f31  mov     [rbx+10h], rdi
0x180027f35  mov     [rbx+8], r14
0x180027f39  mov     rcx, rbx; SRWLock
0x180027f3c  call    cs:__imp_ReleaseSRWLockExclusive
0x180027f42  test    rbp, rbp
0x180027f45  jz      short loc_180027F87
0x180027f47  lea     rdx, [rsp+48h+Reply]; Reply
0x180027f4c  mov     [rsp+48h+Reply], 0
0x180027f54  mov     rcx, rdi; pAsync
0x180027f57  call    cs:__imp_RpcAsyncCompleteCall
0x180027f5d  test    eax, eax
0x180027f5f  jz      short loc_180027F87
0x180027f61  mov     rcx, cs:WPP_GLOBAL_Control
0x180027f68  cmp     rcx, r12
0x180027f6b  jz      short loc_180027F87
0x180027f6d  test    byte ptr [rcx+1Ch], 20h
0x180027f71  jz      short loc_180027F87
0x180027f73  mov     rcx, [rcx+10h]
0x180027f77  mov     edx, 10h
0x180027f7c  mov     r9d, eax
0x180027f7f  mov     r8, r13
0x180027f82  call    WPP_SF_d
0x180027f87  test    rsi, rsi
0x180027f8a  jz      short loc_180027F9A
0x180027f8c  mov     edx, 80004004h; ExceptionCode
0x180027f91  mov     rcx, rsi; pAsync
0x180027f94  call    cs:__imp_RpcAsyncAbortCall
0x180027f9a  mov     rbx, [rsp+48h+arg_8]
0x180027f9f  mov     rbp, [rsp+48h+arg_10]
0x180027fa4  add     rsp, 20h
0x180027fa8  pop     r14
0x180027faa  pop     r13
0x180027fac  pop     r12
0x180027fae  pop     rdi
0x180027faf  pop     rsi
0x180027fb0  retn
```
