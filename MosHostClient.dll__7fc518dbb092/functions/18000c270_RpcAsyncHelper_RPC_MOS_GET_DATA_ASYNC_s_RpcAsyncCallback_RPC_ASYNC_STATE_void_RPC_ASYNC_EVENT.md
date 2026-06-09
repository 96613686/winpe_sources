# RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::s_RpcAsyncCallback(_RPC_ASYNC_STATE *,void *,_RPC_ASYNC_EVENT)

- ea: `0x18000c270`
- end: `0x18000c413`
- name: `?s_RpcAsyncCallback@?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@CAXPEAU_RPC_ASYNC_STATE@@PEAXW4_RPC_ASYNC_EVENT@@@Z`
- size: `419`
- prototype: `void __fastcall(struct _RPC_ASYNC_STATE *Block, __int64, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002534`
- `0x18000819c`
- `0x180009c54`
- `0x18000c138`
- `0x18000c270`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c370`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c370`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c2be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c2be`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000c37e`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000c37e`

## pseudocode

```c
void __fastcall RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::s_RpcAsyncCallback(
        struct _RPC_ASYNC_STATE *Block,
        __int64 a2,
        int a3)
{
  struct _RTL_CRITICAL_SECTION *UserInfo; // rdi
  __int64 v6; // rdx
  unsigned __int64 i; // rcx
  __int64 v8; // rcx
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rdx
  __int64 v10; // rax
  char *v11; // rax
  char v12; // r12
  _QWORD *v13; // rbx
  RPC_STATUS v14; // eax
  void *v15; // rdx
  unsigned int v16; // r8d
  __int64 v17; // rcx
  __int64 v18; // rdx
  _QWORD *v19; // rcx
  int v20; // [rsp+20h] [rbp-30h]
  char v21[24]; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  PRPC_ASYNC_STATE pAsync; // [rsp+90h] [rbp+40h] BYREF
  unsigned int Reply; // [rsp+A0h] [rbp+50h] BYREF
  _QWORD *v25; // [rsp+A8h] [rbp+58h]

  UserInfo = (struct _RTL_CRITICAL_SECTION *)Block->UserInfo;
  pAsync = Block;
  if ( (unsigned int)(a3 - 1) <= 1 )
    __int2c();
  Reply = 0;
  v20 = (int)Block;
  v25 = 0;
  EnterCriticalSection(UserInfo + 2);
  v6 = 0xCBF29CE484222325uLL;
  for ( i = 0; i < 8; ++i )
    v6 = 0x100000001B3LL * (*((unsigned __int8 *)&pAsync + i) ^ (unsigned __int64)v6);
  v8 = 2 * (v6 & (__int64)UserInfo[1].LockSemaphore);
  DebugInfo = UserInfo[1].DebugInfo;
  v10 = *((_QWORD *)&DebugInfo->CriticalSection + v8);
  if ( (HANDLE)v10 == UserInfo->LockSemaphore )
  {
LABEL_9:
    v10 = 0;
  }
  else
  {
    while ( pAsync != *(PRPC_ASYNC_STATE *)(v10 + 16) )
    {
      if ( v10 == *((_QWORD *)&DebugInfo->Type + v8) )
        goto LABEL_9;
      v10 = *(_QWORD *)(v10 + 8);
    }
  }
  if ( !v10 || (HANDLE)v10 == UserInfo->LockSemaphore )
    __int2c();
  v11 = *(char **)(*(_QWORD *)std::_Hash<std::_Umap_traits<_RPC_ASYNC_STATE *,std::unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>,std::_Uhash_compare<_RPC_ASYNC_STATE *,std::hash<_RPC_ASYNC_STATE *>,std::equal_to<_RPC_ASYNC_STATE *>>,std::allocator<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>>>,0>>::_Try_emplace<_RPC_ASYNC_STATE * const &,>(
                                (__int64)&UserInfo->OwningThread,
                                (__int64)v21,
                                &pAsync)
                 + 24LL);
  v12 = *v11;
  v13 = (_QWORD *)*((_QWORD *)v11 + 2);
  *((_QWORD *)v11 + 2) = 0;
  v25 = v13;
  std::_Hash<std::_Umap_traits<_RPC_ASYNC_STATE *,std::unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>,std::_Uhash_compare<_RPC_ASYNC_STATE *,std::hash<_RPC_ASYNC_STATE *>,std::equal_to<_RPC_ASYNC_STATE *>>,std::allocator<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>>>,0>>::erase(
    &UserInfo->OwningThread,
    (__int64 *)&pAsync);
  LeaveCriticalSection(UserInfo + 2);
  v14 = RpcAsyncCompleteCall(pAsync, &Reply);
  if ( v14 && v14 != 1818 )
    wil::details::in1diag3::Log_Hr(retaddr, v15, v16, (const char *)(v14 | 0x80010000), v20);
  if ( a3 )
  {
    v17 = 2147551002LL;
    Reply = -2147416294;
  }
  else
  {
    v17 = Reply;
  }
  LOBYTE(v15) = v12;
  (*(void (__fastcall **)(__int64, void *, _QWORD *))&UserInfo->LockCount)(v17, v15, v13);
  if ( v13 )
  {
    v19 = (_QWORD *)v13[7];
    if ( v19 )
    {
      LOBYTE(v18) = v19 != v13;
      (*(void (__fastcall **)(_QWORD *, __int64))(*v19 + 32LL))(v19, v18);
      v13[7] = 0;
    }
    operator delete(v13);
  }
  operator delete(Block);
}

```

## disassembly

```asm
0x18000c270  mov     [rsp-38h+arg_8], rbx
0x18000c275  push    rbp
0x18000c276  push    rsi
0x18000c277  push    rdi
0x18000c278  push    r12
0x18000c27a  push    r13
0x18000c27c  push    r14
0x18000c27e  push    r15
0x18000c280  mov     rbp, rsp
0x18000c283  sub     rsp, 50h
0x18000c287  mov     r14d, r8d
0x18000c28a  mov     rsi, rcx
0x18000c28d  mov     rdi, [rcx+18h]
0x18000c291  mov     [rbp+pAsync], rcx
0x18000c295  lea     eax, [r8-1]
0x18000c299  cmp     eax, 1
0x18000c29c  ja      short loc_18000C2A0
0x18000c29e  int     2Ch; Windows NT - assertion failure
0x18000c2a0  mov     [rbp+Reply], 0
0x18000c2a7  mov     [rbp+var_30], rsi
0x18000c2ab  mov     [rbp+arg_18], 0
0x18000c2b3  lea     r15, [rdi+50h]
0x18000c2b7  mov     [rbp+var_28], r15
0x18000c2bb  mov     rcx, r15; lpCriticalSection
0x18000c2be  call    cs:__imp_EnterCriticalSection
0x18000c2c4  mov     [rbp+var_20], 1
0x18000c2c8  mov     rdx, 0CBF29CE484222325h
0x18000c2d2  xor     ecx, ecx
0x18000c2d4  movzx   eax, byte ptr [rbp+rcx+pAsync]
0x18000c2d9  xor     rdx, rax
0x18000c2dc  mov     r8, 100000001B3h
0x18000c2e6  imul    rdx, r8
0x18000c2ea  inc     rcx
0x18000c2ed  cmp     rcx, 8
0x18000c2f1  jb      short loc_18000C2D4
0x18000c2f3  mov     rcx, [rdi+40h]
0x18000c2f7  and     rcx, rdx
0x18000c2fa  add     rcx, rcx
0x18000c2fd  mov     rdx, [rdi+28h]
0x18000c301  mov     rax, [rdx+rcx*8+8]
0x18000c306  cmp     rax, [rdi+18h]
0x18000c30a  jz      short loc_18000C325
0x18000c30c  mov     r8, [rdx+rcx*8]
0x18000c310  mov     rcx, [rbp+pAsync]
0x18000c314  cmp     rcx, [rax+10h]
0x18000c318  jz      short loc_18000C327
0x18000c31a  cmp     rax, r8
0x18000c31d  jz      short loc_18000C325
0x18000c31f  mov     rax, [rax+8]
0x18000c323  jmp     short loc_18000C314
0x18000c325  xor     eax, eax
0x18000c327  test    rax, rax
0x18000c32a  jz      short loc_18000C332
0x18000c32c  cmp     rax, [rdi+18h]
0x18000c330  jnz     short loc_18000C334
0x18000c332  int     2Ch; Windows NT - assertion failure
0x18000c334  lea     r8, [rbp+pAsync]
0x18000c338  lea     rdx, [rbp+var_18]
0x18000c33c  lea     rcx, [rdi+10h]
0x18000c340  call    ??$_Try_emplace@AEBQEAU_RPC_ASYNC_STATE@@$$V@?$_Hash@V?$_Umap_traits@PEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@@std@@@std@@V?$_Uhash_compare@PEAU_RPC_ASYNC_STATE@@U?$hash@PEAU_RPC_ASYNC_STATE@@@std@@U?$equal_to@PEAU_RPC_ASYNC_STATE@@@3@@3@V?$allocator@U?$pair@QEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@@std@@@std@@@std@@@3@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@QEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@@std@@@std@@@std@@PEAX@std@@_N@1@AEBQEAU_RPC_ASYNC_STATE@@@Z; std::_Hash<std::_Umap_traits<_RPC_ASYNC_STATE *,std::unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>,std::_Uhash_compare<_RPC_ASYNC_STATE *,std::hash<_RPC_ASYNC_STATE *>,std::equal_to<_RPC_ASYNC_STATE *>>,std::allocator<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>>>,0>>::_Try_emplace<_RPC_ASYNC_STATE * const &,>(_RPC_ASYNC_STATE * const &)
0x18000c345  mov     rdx, [rax]
0x18000c348  mov     rax, [rdx+18h]
0x18000c34c  mov     r12b, [rax]
0x18000c34f  mov     rbx, [rax+10h]
0x18000c353  mov     qword ptr [rax+10h], 0
0x18000c35b  mov     [rbp+arg_18], rbx
0x18000c35f  lea     rdx, [rbp+pAsync]
0x18000c363  lea     rcx, [rdi+10h]
0x18000c367  call    ?erase@?$_Hash@V?$_Umap_traits@PEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@@std@@@std@@V?$_Uhash_compare@PEAU_RPC_ASYNC_STATE@@U?$hash@PEAU_RPC_ASYNC_STATE@@@std@@U?$equal_to@PEAU_RPC_ASYNC_STATE@@@3@@3@V?$allocator@U?$pair@QEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@@std@@@std@@@std@@@3@$0A@@std@@@std@@QEAA_KAEBQEAU_RPC_ASYNC_STATE@@@Z; std::_Hash<std::_Umap_traits<_RPC_ASYNC_STATE *,std::unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>,std::_Uhash_compare<_RPC_ASYNC_STATE *,std::hash<_RPC_ASYNC_STATE *>,std::equal_to<_RPC_ASYNC_STATE *>>,std::allocator<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>>>,0>>::erase(_RPC_ASYNC_STATE * const &)
0x18000c36c  nop
0x18000c36d  mov     rcx, r15; lpCriticalSection
0x18000c370  call    cs:__imp_LeaveCriticalSection
0x18000c376  lea     rdx, [rbp+Reply]; Reply
0x18000c37a  mov     rcx, [rbp+pAsync]; pAsync
0x18000c37e  call    cs:__imp_RpcAsyncCompleteCall
0x18000c384  test    eax, eax
0x18000c386  jz      short loc_18000C3A0
0x18000c388  cmp     eax, 71Ah
0x18000c38d  jz      short loc_18000C3A0
0x18000c38f  or      eax, 80010000h
0x18000c394  mov     rcx, [rbp+38h]; this
0x18000c398  mov     r9d, eax; char *
0x18000c39b  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18000c3a0  test    r14d, r14d
0x18000c3a3  jz      short loc_18000C3AF
0x18000c3a5  mov     ecx, 8001071Ah
0x18000c3aa  mov     [rbp+Reply], ecx
0x18000c3ad  jmp     short loc_18000C3B2
0x18000c3af  mov     ecx, [rbp+Reply]
0x18000c3b2  mov     r8, rbx
0x18000c3b5  mov     dl, r12b
0x18000c3b8  mov     rax, [rdi+8]
0x18000c3bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3c1  nop
0x18000c3c2  test    rbx, rbx
0x18000c3c5  jz      short loc_18000C3F3
0x18000c3c7  mov     rcx, [rbx+38h]
0x18000c3cb  test    rcx, rcx
0x18000c3ce  jz      short loc_18000C3EA
0x18000c3d0  mov     rax, [rcx]
0x18000c3d3  cmp     rcx, rbx
0x18000c3d6  setnz   dl
0x18000c3d9  mov     rax, [rax+20h]
0x18000c3dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3e2  mov     qword ptr [rbx+38h], 0
0x18000c3ea  mov     rcx, rbx; Block
0x18000c3ed  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c3f2  nop
0x18000c3f3  mov     rcx, rsi; Block
0x18000c3f6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c3fb  mov     rbx, [rsp+50h+arg_8]
0x18000c403  add     rsp, 50h
0x18000c407  pop     r15
0x18000c409  pop     r14
0x18000c40b  pop     r13
0x18000c40d  pop     r12
0x18000c40f  pop     rdi
0x18000c410  pop     rsi
0x18000c411  pop     rbp
0x18000c412  retn
```
