# std::_Hash<std::_Umap_traits<_RPC_ASYNC_STATE *,std::unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>,std::_Uhash_compare<_RPC_ASYNC_STATE *,std::hash<_RPC_ASYNC_STATE *>,std::equal_to<_RPC_ASYNC_STATE *>>,std::allocator<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>>>,0>>::erase(_RPC_ASYNC_STATE * const &)

- ea: `0x18000c138`
- end: `0x18000c268`
- name: `?erase@?$_Hash@V?$_Umap_traits@PEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@@std@@@std@@V?$_Uhash_compare@PEAU_RPC_ASYNC_STATE@@U?$hash@PEAU_RPC_ASYNC_STATE@@@std@@U?$equal_to@PEAU_RPC_ASYNC_STATE@@@3@@3@V?$allocator@U?$pair@QEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@@std@@@std@@@std@@@3@$0A@@std@@@std@@QEAA_KAEBQEAU_RPC_ASYNC_STATE@@@Z`
- size: `304`
- prototype: `__int64 __fastcall(_QWORD *, __int64 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009798`
- `0x18000c270`

## callees

- `0x180002534`
- `0x1800029b4`
- `0x18000c138`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<_RPC_ASYNC_STATE *,std::unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>,std::_Uhash_compare<_RPC_ASYNC_STATE *,std::hash<_RPC_ASYNC_STATE *>,std::equal_to<_RPC_ASYNC_STATE *>>,std::allocator<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>>>,0>>::erase(
        _QWORD *a1,
        __int64 *a2)
{
  unsigned __int64 v2; // r9
  __int64 v5; // r8
  __int64 v6; // rbp
  __int64 v7; // rax
  __int64 v8; // r8
  __int64 v9; // rcx
  _QWORD *v10; // rdx
  __int64 v11; // r9
  _QWORD *v12; // rbx
  __int64 v13; // r11
  __int64 v14; // r8
  __int64 v15; // rcx
  _QWORD *v16; // rsi
  _QWORD *v17; // rdi
  _QWORD *v18; // rcx

  v2 = 0;
  v5 = 0xCBF29CE484222325uLL;
  v6 = 1;
  do
  {
    v7 = *((unsigned __int8 *)a2 + v2++);
    v5 = 0x100000001B3LL * (v7 ^ v5);
  }
  while ( v2 < 8 );
  v8 = a1[6] & v5;
  v9 = a1[3];
  v10 = (_QWORD *)a1[1];
  v11 = 2 * v8;
  v12 = *(_QWORD **)(v9 + 16 * v8 + 8);
  if ( v12 == v10 )
  {
LABEL_8:
    v12 = 0;
  }
  else
  {
    v13 = *a2;
    while ( v13 != v12[2] )
    {
      if ( v12 == *(_QWORD **)(v9 + 16 * v8) )
        goto LABEL_8;
      v12 = (_QWORD *)v12[1];
    }
  }
  if ( !v12 )
    return 0;
  v14 = 16 * v8;
  if ( *(_QWORD **)(v9 + 8 * v11 + 8) == v12 )
  {
    if ( *(_QWORD **)(v14 + v9) == v12 )
      *(_QWORD *)(v14 + v9) = v10;
    else
      v10 = (_QWORD *)v12[1];
    *(_QWORD *)(v9 + 8 * v11 + 8) = v10;
  }
  else if ( *(_QWORD **)(v14 + v9) == v12 )
  {
    *(_QWORD *)(v14 + v9) = *v12;
  }
  v15 = *v12;
  --a1[2];
  *(_QWORD *)v12[1] = v15;
  *(_QWORD *)(v15 + 8) = v12[1];
  v16 = (_QWORD *)v12[3];
  if ( v16 )
  {
    v17 = (_QWORD *)v16[2];
    if ( v17 )
    {
      v18 = (_QWORD *)v17[7];
      if ( v18 )
      {
        LOBYTE(v10) = v18 != v17;
        (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v18 + 32LL))(v18, v10);
        v17[7] = 0;
      }
      operator delete(v17);
    }
    operator delete(v16);
  }
  operator delete(v12);
  return v6;
}

```

## disassembly

```asm
0x18000c138  push    rbx
0x18000c13a  push    rbp
0x18000c13b  push    rsi
0x18000c13c  push    rdi
0x18000c13d  sub     rsp, 28h
0x18000c141  xor     r9d, r9d
0x18000c144  mov     r11, rdx
0x18000c147  mov     r10, rcx
0x18000c14a  mov     r8, 0CBF29CE484222325h
0x18000c154  lea     ebp, [r9+1]
0x18000c158  movzx   eax, byte ptr [rdx+r9]
0x18000c15d  mov     rcx, 100000001B3h
0x18000c167  xor     r8, rax
0x18000c16a  add     r9, rbp
0x18000c16d  imul    r8, rcx
0x18000c171  cmp     r9, 8
0x18000c175  jb      short loc_18000C158
0x18000c177  and     r8, [r10+30h]
0x18000c17b  mov     rcx, [r10+18h]
0x18000c17f  mov     r9, r8
0x18000c182  mov     rdx, [r10+8]
0x18000c186  add     r9, r9
0x18000c189  mov     rbx, [rcx+r9*8+8]
0x18000c18e  cmp     rbx, rdx
0x18000c191  jz      short loc_18000C1B1
0x18000c193  mov     r11, [r11]
0x18000c196  mov     rax, r8
0x18000c199  add     rax, rax
0x18000c19c  mov     rax, [rcx+rax*8]
0x18000c1a0  cmp     r11, [rbx+10h]
0x18000c1a4  jz      short loc_18000C1B3
0x18000c1a6  cmp     rbx, rax
0x18000c1a9  jz      short loc_18000C1B1
0x18000c1ab  mov     rbx, [rbx+8]
0x18000c1af  jmp     short loc_18000C1A0
0x18000c1b1  xor     ebx, ebx
0x18000c1b3  mov     eax, 10h
0x18000c1b8  test    rbx, rbx
0x18000c1bb  jz      loc_18000C25A
0x18000c1c1  imul    r8, rax
0x18000c1c5  cmp     [rcx+r9*8+8], rbx
0x18000c1ca  jnz     short loc_18000C1E3
0x18000c1cc  cmp     [r8+rcx], rbx
0x18000c1d0  jnz     short loc_18000C1D8
0x18000c1d2  mov     [r8+rcx], rdx
0x18000c1d6  jmp     short loc_18000C1DC
0x18000c1d8  mov     rdx, [rbx+8]
0x18000c1dc  mov     [rcx+r9*8+8], rdx
0x18000c1e1  jmp     short loc_18000C1F0
0x18000c1e3  cmp     [r8+rcx], rbx
0x18000c1e7  jnz     short loc_18000C1F0
0x18000c1e9  mov     rax, [rbx]
0x18000c1ec  mov     [r8+rcx], rax
0x18000c1f0  mov     rcx, [rbx]
0x18000c1f3  dec     qword ptr [r10+10h]
0x18000c1f7  mov     rax, [rbx+8]
0x18000c1fb  mov     [rax], rcx
0x18000c1fe  mov     rax, [rbx+8]
0x18000c202  mov     [rcx+8], rax
0x18000c206  mov     rsi, [rbx+18h]
0x18000c20a  test    rsi, rsi
0x18000c20d  jz      short loc_18000C24B
0x18000c20f  mov     rdi, [rsi+10h]
0x18000c213  test    rdi, rdi
0x18000c216  jz      short loc_18000C243
0x18000c218  mov     rcx, [rdi+38h]
0x18000c21c  test    rcx, rcx
0x18000c21f  jz      short loc_18000C23B
0x18000c221  mov     rax, [rcx]
0x18000c224  cmp     rcx, rdi
0x18000c227  setnz   dl
0x18000c22a  mov     rax, [rax+20h]
0x18000c22e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c233  mov     qword ptr [rdi+38h], 0
0x18000c23b  mov     rcx, rdi; Block
0x18000c23e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c243  mov     rcx, rsi; Block
0x18000c246  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c24b  mov     edx, 20h ; ' '
0x18000c250  mov     rcx, rbx; Block
0x18000c253  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000c258  jmp     short loc_18000C25C
0x18000c25a  xor     ebp, ebp
0x18000c25c  mov     rax, rbp
0x18000c25f  add     rsp, 28h
0x18000c263  pop     rdi
0x18000c264  pop     rsi
0x18000c265  pop     rbp
0x18000c266  pop     rbx
0x18000c267  retn
```
