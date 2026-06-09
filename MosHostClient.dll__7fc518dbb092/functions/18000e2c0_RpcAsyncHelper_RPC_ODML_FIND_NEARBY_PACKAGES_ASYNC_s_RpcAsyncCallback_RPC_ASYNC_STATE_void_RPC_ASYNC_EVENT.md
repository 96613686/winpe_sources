# RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::s_RpcAsyncCallback(_RPC_ASYNC_STATE *,void *,_RPC_ASYNC_EVENT)

- ea: `0x18000e2c0`
- end: `0x18000e440`
- name: `?s_RpcAsyncCallback@?$RpcAsyncHelper@URPC_ODML_FIND_NEARBY_PACKAGES_ASYNC@@@@CAXPEAU_RPC_ASYNC_STATE@@PEAXW4_RPC_ASYNC_EVENT@@@Z`
- size: `384`
- prototype: `void __fastcall(struct _RPC_ASYNC_STATE *Block, __int64, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002534`
- `0x180009c54`
- `0x18000c580`
- `0x18000e19c`
- `0x18000e2c0`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e3c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e3c0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e30e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e30e`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000e3ce`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000e3ce`

## pseudocode

```c
void __fastcall RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::s_RpcAsyncCallback(
        struct _RPC_ASYNC_STATE *Block,
        __int64 a2,
        int a3)
{
  struct _RTL_CRITICAL_SECTION *UserInfo; // rbx
  __int64 v6; // rdx
  unsigned __int64 i; // rcx
  __int64 v8; // rcx
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rdx
  __int64 v10; // rax
  char *v11; // rax
  char v12; // r12
  void *v13; // rsi
  RPC_STATUS v14; // eax
  void *v15; // rdx
  unsigned int v16; // r8d
  __int64 v17; // rcx
  int v18; // [rsp+20h] [rbp-30h]
  char v19[24]; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  PRPC_ASYNC_STATE pAsync; // [rsp+90h] [rbp+40h] BYREF
  unsigned int Reply; // [rsp+A0h] [rbp+50h] BYREF
  void *v23; // [rsp+A8h] [rbp+58h]

  UserInfo = (struct _RTL_CRITICAL_SECTION *)Block->UserInfo;
  pAsync = Block;
  if ( (unsigned int)(a3 - 1) <= 1 )
    __int2c();
  Reply = 0;
  v18 = (int)Block;
  v23 = 0;
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
  v11 = *(char **)(*(_QWORD *)std::_Hash<std::_Umap_traits<_RPC_ASYNC_STATE *,std::unique_ptr<RpcAsyncHelper<RPC_MAPS_STORAGE_VALIDATE_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPS_STORAGE_VALIDATE_ASYNC>::RPC_ASYNC_STATE_DATA>>,std::_Uhash_compare<_RPC_ASYNC_STATE *,std::hash<_RPC_ASYNC_STATE *>,std::equal_to<_RPC_ASYNC_STATE *>>,std::allocator<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MAPS_STORAGE_VALIDATE_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPS_STORAGE_VALIDATE_ASYNC>::RPC_ASYNC_STATE_DATA>>>>,0>>::_Try_emplace<_RPC_ASYNC_STATE * const &,>(
                                (__int64)&UserInfo->OwningThread,
                                (__int64)v19,
                                &pAsync)
                 + 24LL);
  v12 = *v11;
  v13 = (void *)*((_QWORD *)v11 + 2);
  *((_QWORD *)v11 + 2) = 0;
  v23 = v13;
  std::_Hash<std::_Umap_traits<_RPC_ASYNC_STATE *,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>,std::_Uhash_compare<_RPC_ASYNC_STATE *,std::hash<_RPC_ASYNC_STATE *>,std::equal_to<_RPC_ASYNC_STATE *>>,std::allocator<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>>>,0>>::erase(
    &UserInfo->OwningThread,
    &pAsync);
  LeaveCriticalSection(UserInfo + 2);
  v14 = RpcAsyncCompleteCall(pAsync, &Reply);
  if ( v14 && v14 != 1818 )
    wil::details::in1diag3::Log_Hr(retaddr, v15, v16, (const char *)(v14 | 0x80010000), v18);
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
  (*(void (__fastcall **)(__int64, void *, void *))&UserInfo->LockCount)(v17, v15, v13);
  if ( v13 )
    operator delete(v13);
  operator delete(Block);
}

```

## disassembly

```asm
0x18000e2c0  mov     [rsp-38h+arg_8], rbx
0x18000e2c5  push    rbp
0x18000e2c6  push    rsi
0x18000e2c7  push    rdi
0x18000e2c8  push    r12
0x18000e2ca  push    r13
0x18000e2cc  push    r14
0x18000e2ce  push    r15
0x18000e2d0  mov     rbp, rsp
0x18000e2d3  sub     rsp, 50h
0x18000e2d7  mov     r14d, r8d
0x18000e2da  mov     rdi, rcx
0x18000e2dd  mov     rbx, [rcx+18h]
0x18000e2e1  mov     [rbp+pAsync], rcx
0x18000e2e5  lea     eax, [r8-1]
0x18000e2e9  cmp     eax, 1
0x18000e2ec  ja      short loc_18000E2F0
0x18000e2ee  int     2Ch; Windows NT - assertion failure
0x18000e2f0  mov     [rbp+Reply], 0
0x18000e2f7  mov     [rbp+var_30], rdi
0x18000e2fb  mov     [rbp+arg_18], 0
0x18000e303  lea     r15, [rbx+50h]
0x18000e307  mov     [rbp+var_28], r15
0x18000e30b  mov     rcx, r15; lpCriticalSection
0x18000e30e  call    cs:__imp_EnterCriticalSection
0x18000e314  mov     [rbp+var_20], 1
0x18000e318  mov     rdx, 0CBF29CE484222325h
0x18000e322  xor     ecx, ecx
0x18000e324  movzx   eax, byte ptr [rbp+rcx+pAsync]
0x18000e329  xor     rdx, rax
0x18000e32c  mov     r8, 100000001B3h
0x18000e336  imul    rdx, r8
0x18000e33a  inc     rcx
0x18000e33d  cmp     rcx, 8
0x18000e341  jb      short loc_18000E324
0x18000e343  mov     rcx, [rbx+40h]
0x18000e347  and     rcx, rdx
0x18000e34a  add     rcx, rcx
0x18000e34d  mov     rdx, [rbx+28h]
0x18000e351  mov     rax, [rdx+rcx*8+8]
0x18000e356  cmp     rax, [rbx+18h]
0x18000e35a  jz      short loc_18000E375
0x18000e35c  mov     r8, [rdx+rcx*8]
0x18000e360  mov     rcx, [rbp+pAsync]
0x18000e364  cmp     rcx, [rax+10h]
0x18000e368  jz      short loc_18000E377
0x18000e36a  cmp     rax, r8
0x18000e36d  jz      short loc_18000E375
0x18000e36f  mov     rax, [rax+8]
0x18000e373  jmp     short loc_18000E364
0x18000e375  xor     eax, eax
0x18000e377  test    rax, rax
0x18000e37a  jz      short loc_18000E382
0x18000e37c  cmp     rax, [rbx+18h]
0x18000e380  jnz     short loc_18000E384
0x18000e382  int     2Ch; Windows NT - assertion failure
0x18000e384  lea     r8, [rbp+pAsync]
0x18000e388  lea     rdx, [rbp+var_18]
0x18000e38c  lea     rcx, [rbx+10h]
0x18000e390  call    ??$_Try_emplace@AEBQEAU_RPC_ASYNC_STATE@@$$V@?$_Hash@V?$_Umap_traits@PEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPS_STORAGE_VALIDATE_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPS_STORAGE_VALIDATE_ASYNC@@@@@std@@@std@@V?$_Uhash_compare@PEAU_RPC_ASYNC_STATE@@U?$hash@PEAU_RPC_ASYNC_STATE@@@std@@U?$equal_to@PEAU_RPC_ASYNC_STATE@@@3@@3@V?$allocator@U?$pair@QEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPS_STORAGE_VALIDATE_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPS_STORAGE_VALIDATE_ASYNC@@@@@std@@@std@@@std@@@3@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@QEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPS_STORAGE_VALIDATE_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPS_STORAGE_VALIDATE_ASYNC@@@@@std@@@std@@@std@@PEAX@std@@_N@1@AEBQEAU_RPC_ASYNC_STATE@@@Z; std::_Hash<std::_Umap_traits<_RPC_ASYNC_STATE *,std::unique_ptr<RpcAsyncHelper<RPC_MAPS_STORAGE_VALIDATE_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPS_STORAGE_VALIDATE_ASYNC>::RPC_ASYNC_STATE_DATA>>,std::_Uhash_compare<_RPC_ASYNC_STATE *,std::hash<_RPC_ASYNC_STATE *>,std::equal_to<_RPC_ASYNC_STATE *>>,std::allocator<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MAPS_STORAGE_VALIDATE_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPS_STORAGE_VALIDATE_ASYNC>::RPC_ASYNC_STATE_DATA>>>>,0>>::_Try_emplace<_RPC_ASYNC_STATE * const &,>(_RPC_ASYNC_STATE * const &)
0x18000e395  mov     rdx, [rax]
0x18000e398  mov     rax, [rdx+18h]
0x18000e39c  mov     r12b, [rax]
0x18000e39f  mov     rsi, [rax+10h]
0x18000e3a3  mov     qword ptr [rax+10h], 0
0x18000e3ab  mov     [rbp+arg_18], rsi
0x18000e3af  lea     rdx, [rbp+pAsync]
0x18000e3b3  lea     rcx, [rbx+10h]
0x18000e3b7  call    ?erase@?$_Hash@V?$_Umap_traits@PEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC@@@@@std@@@std@@V?$_Uhash_compare@PEAU_RPC_ASYNC_STATE@@U?$hash@PEAU_RPC_ASYNC_STATE@@@std@@U?$equal_to@PEAU_RPC_ASYNC_STATE@@@3@@3@V?$allocator@U?$pair@QEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC@@@@@std@@@std@@@std@@@3@$0A@@std@@@std@@QEAA_KAEBQEAU_RPC_ASYNC_STATE@@@Z; std::_Hash<std::_Umap_traits<_RPC_ASYNC_STATE *,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>,std::_Uhash_compare<_RPC_ASYNC_STATE *,std::hash<_RPC_ASYNC_STATE *>,std::equal_to<_RPC_ASYNC_STATE *>>,std::allocator<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>>>,0>>::erase(_RPC_ASYNC_STATE * const &)
0x18000e3bc  nop
0x18000e3bd  mov     rcx, r15; lpCriticalSection
0x18000e3c0  call    cs:__imp_LeaveCriticalSection
0x18000e3c6  lea     rdx, [rbp+Reply]; Reply
0x18000e3ca  mov     rcx, [rbp+pAsync]; pAsync
0x18000e3ce  call    cs:__imp_RpcAsyncCompleteCall
0x18000e3d4  test    eax, eax
0x18000e3d6  jz      short loc_18000E3F0
0x18000e3d8  cmp     eax, 71Ah
0x18000e3dd  jz      short loc_18000E3F0
0x18000e3df  or      eax, 80010000h
0x18000e3e4  mov     rcx, [rbp+38h]; this
0x18000e3e8  mov     r9d, eax; char *
0x18000e3eb  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18000e3f0  test    r14d, r14d
0x18000e3f3  jz      short loc_18000E3FF
0x18000e3f5  mov     ecx, 8001071Ah
0x18000e3fa  mov     [rbp+Reply], ecx
0x18000e3fd  jmp     short loc_18000E402
0x18000e3ff  mov     ecx, [rbp+Reply]
0x18000e402  mov     r8, rsi
0x18000e405  mov     dl, r12b
0x18000e408  mov     rax, [rbx+8]
0x18000e40c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e411  nop
0x18000e412  test    rsi, rsi
0x18000e415  jz      short loc_18000E420
0x18000e417  mov     rcx, rsi; Block
0x18000e41a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e41f  nop
0x18000e420  mov     rcx, rdi; Block
0x18000e423  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e428  mov     rbx, [rsp+50h+arg_8]
0x18000e430  add     rsp, 50h
0x18000e434  pop     r15
0x18000e436  pop     r14
0x18000e438  pop     r13
0x18000e43a  pop     r12
0x18000e43c  pop     rdi
0x18000e43d  pop     rsi
0x18000e43e  pop     rbp
0x18000e43f  retn
```
