# std::_Hash<std::_Umap_traits<_RPC_ASYNC_STATE *,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA>>,std::_Uhash_compare<_RPC_ASYNC_STATE *,std::hash<_RPC_ASYNC_STATE *>,std::equal_to<_RPC_ASYNC_STATE *>>,std::allocator<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA>>>>,0>>::_Unchecked_erase(std::_List_node<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA>>>,void *> *,std::_List_node<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA>>>,void *> * const)

- ea: `0x18000dfac`
- end: `0x18000e193`
- name: `?_Unchecked_erase@?$_Hash@V?$_Umap_traits@PEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC@@@@@std@@@std@@V?$_Uhash_compare@PEAU_RPC_ASYNC_STATE@@U?$hash@PEAU_RPC_ASYNC_STATE@@@std@@U?$equal_to@PEAU_RPC_ASYNC_STATE@@@3@@3@V?$allocator@U?$pair@QEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC@@@@@std@@@std@@@std@@@3@$0A@@std@@@std@@AEAAPEAU?$_List_node@U?$pair@QEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC@@@@@std@@@std@@@std@@PEAX@2@PEAU32@QEAU32@@Z`
- size: `487`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000cc3c`

## callees

- `0x180002534`
- `0x1800029b4`
- `0x18000dfac`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::_Umap_traits<_RPC_ASYNC_STATE *,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA>>,std::_Uhash_compare<_RPC_ASYNC_STATE *,std::hash<_RPC_ASYNC_STATE *>,std::equal_to<_RPC_ASYNC_STATE *>>,std::allocator<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA>>>>,0>>::_Unchecked_erase(
        _QWORD *a1,
        _QWORD *a2,
        _QWORD *a3)
{
  _QWORD *v6; // rbx
  _QWORD *v7; // rsi
  __int64 v8; // r14
  __int64 v9; // r15
  unsigned __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // r14
  _QWORD *v13; // r12
  void *v14; // rcx
  _QWORD *v16; // rax
  __int64 v17; // rcx
  unsigned __int64 i; // rdx
  __int64 v19; // rax
  _QWORD *v20; // rbp
  void *v21; // r12
  void *v22; // rcx
  _QWORD *v23; // [rsp+20h] [rbp-58h]
  _QWORD *v24; // [rsp+28h] [rbp-50h]
  _QWORD *v25; // [rsp+30h] [rbp-48h]
  _QWORD *v26; // [rsp+88h] [rbp+10h]
  _QWORD *v27; // [rsp+90h] [rbp+18h]
  void *Block; // [rsp+98h] [rbp+20h]
  void *Blocka; // [rsp+98h] [rbp+20h]

  if ( a2 != a3 )
  {
    v6 = a2;
    v7 = (_QWORD *)a2[1];
    v8 = 0xCBF29CE484222325uLL;
    v9 = a1[3];
    v27 = (_QWORD *)a1[1];
    v10 = 0;
    v25 = v7;
    do
    {
      v11 = *((unsigned __int8 *)a2 + v10 + 16);
      ++v10;
      v8 = 0x100000001B3LL * (v11 ^ v8);
    }
    while ( v10 < 8 );
    v12 = 2 * (a1[6] & v8);
    v26 = *(_QWORD **)(v9 + 8 * v12);
    v23 = *(_QWORD **)(v9 + 8 * v12 + 8);
    while ( 1 )
    {
      v13 = (_QWORD *)v6[3];
      v24 = v6;
      Block = v6;
      v6 = (_QWORD *)*v6;
      if ( v13 )
      {
        v14 = (void *)v13[2];
        if ( v14 )
          operator delete(v14);
        operator delete(v13);
      }
      operator delete(Block);
      --a1[2];
      if ( v24 == v23 )
        break;
      if ( v6 == a3 )
      {
        if ( v26 == a2 )
LABEL_12:
          *(_QWORD *)(v9 + 8 * v12) = v6;
        goto LABEL_13;
      }
    }
    if ( v26 == a2 )
    {
      *(_QWORD *)(v9 + 8 * v12) = v27;
      v16 = v27;
    }
    else
    {
      v16 = v7;
    }
    while ( 1 )
    {
      *(_QWORD *)(v9 + 8 * v12 + 8) = v16;
      if ( v6 == a3 )
        break;
      v17 = 0xCBF29CE484222325uLL;
      for ( i = 0; i < 8; ++i )
      {
        v19 = *((unsigned __int8 *)v6 + i + 16);
        v17 = 0x100000001B3LL * (v19 ^ v17);
      }
      v7 = v25;
      v12 = 2 * (v17 & a1[6]);
      Blocka = *(void **)(v9 + 16 * (v17 & a1[6]) + 8);
      while ( 1 )
      {
        v20 = (_QWORD *)v6[3];
        v21 = v6;
        v6 = (_QWORD *)*v6;
        if ( v20 )
        {
          v22 = (void *)v20[2];
          if ( v22 )
            operator delete(v22);
          operator delete(v20);
        }
        operator delete(v21);
        --a1[2];
        if ( v21 == Blocka )
          break;
        if ( v6 == a3 )
          goto LABEL_12;
      }
      v16 = v27;
      *(_QWORD *)(v9 + 8 * v12) = v27;
    }
LABEL_13:
    *v7 = v6;
    v6[1] = v7;
  }
  return a3;
}

```

## disassembly

```asm
0x18000dfac  mov     [rsp+arg_0], rbx
0x18000dfb1  push    rbp
0x18000dfb2  push    rsi
0x18000dfb3  push    rdi
0x18000dfb4  push    r12
0x18000dfb6  push    r13
0x18000dfb8  push    r14
0x18000dfba  push    r15
0x18000dfbc  sub     rsp, 40h
0x18000dfc0  mov     rdi, r8
0x18000dfc3  mov     rbp, rdx
0x18000dfc6  mov     r13, rcx
0x18000dfc9  cmp     rdx, r8
0x18000dfcc  jz      loc_18000E0A2
0x18000dfd2  mov     rax, [rcx+8]
0x18000dfd6  mov     rbx, rdx
0x18000dfd9  mov     rsi, [rdx+8]
0x18000dfdd  mov     r14, 0CBF29CE484222325h
0x18000dfe7  mov     r15, [rcx+18h]
0x18000dfeb  mov     rdx, 100000001B3h
0x18000dff5  mov     [rsp+78h+arg_10], rax
0x18000dffd  xor     ecx, ecx
0x18000dfff  mov     [rsp+78h+var_48], rsi
0x18000e004  movzx   eax, byte ptr [rcx+rbp+10h]
0x18000e009  inc     rcx
0x18000e00c  xor     r14, rax
0x18000e00f  imul    r14, rdx
0x18000e013  cmp     rcx, 8
0x18000e017  jb      short loc_18000E004
0x18000e019  and     r14, [r13+30h]
0x18000e01d  add     r14, r14
0x18000e020  mov     rax, [r15+r14*8]
0x18000e024  mov     [rsp+78h+arg_8], rax
0x18000e02c  mov     rax, [r15+r14*8+8]
0x18000e031  mov     [rsp+78h+var_58], rax
0x18000e036  mov     r12, [rbx+18h]
0x18000e03a  mov     [rsp+78h+var_50], rbx
0x18000e03f  mov     [rsp+78h+Block], rbx
0x18000e047  mov     rbx, [rbx]
0x18000e04a  test    r12, r12
0x18000e04d  jz      short loc_18000E066
0x18000e04f  mov     rcx, [r12+10h]; Block
0x18000e054  test    rcx, rcx
0x18000e057  jz      short loc_18000E05E
0x18000e059  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e05e  mov     rcx, r12; Block
0x18000e061  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e066  mov     rcx, [rsp+78h+Block]; Block
0x18000e06e  mov     edx, 20h ; ' '
0x18000e073  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000e078  mov     rax, [rsp+78h+var_58]
0x18000e07d  dec     qword ptr [r13+10h]
0x18000e081  cmp     [rsp+78h+var_50], rax
0x18000e086  jz      short loc_18000E0BD
0x18000e088  cmp     rbx, rdi
0x18000e08b  jnz     short loc_18000E036
0x18000e08d  cmp     [rsp+78h+arg_8], rbp
0x18000e095  jnz     short loc_18000E09B
0x18000e097  mov     [r15+r14*8], rbx
0x18000e09b  mov     [rsi], rbx
0x18000e09e  mov     [rbx+8], rsi
0x18000e0a2  mov     rbx, [rsp+78h+arg_0]
0x18000e0aa  mov     rax, rdi
0x18000e0ad  add     rsp, 40h
0x18000e0b1  pop     r15
0x18000e0b3  pop     r14
0x18000e0b5  pop     r13
0x18000e0b7  pop     r12
0x18000e0b9  pop     rdi
0x18000e0ba  pop     rsi
0x18000e0bb  pop     rbp
0x18000e0bc  retn
0x18000e0bd  cmp     [rsp+78h+arg_8], rbp
0x18000e0c5  jnz     short loc_18000E0DB
0x18000e0c7  mov     r8, [rsp+78h+arg_10]
0x18000e0cf  mov     [r15+r14*8], r8
0x18000e0d3  mov     rax, r8
0x18000e0d6  jmp     loc_18000E180
0x18000e0db  mov     rax, rsi
0x18000e0de  jmp     loc_18000E180
0x18000e0e3  mov     rcx, 0CBF29CE484222325h
0x18000e0ed  xor     edx, edx
0x18000e0ef  mov     rsi, 100000001B3h
0x18000e0f9  movzx   eax, byte ptr [rbx+rdx+10h]
0x18000e0fe  inc     rdx
0x18000e101  xor     rcx, rax
0x18000e104  imul    rcx, rsi
0x18000e108  cmp     rdx, 8
0x18000e10c  jb      short loc_18000E0F9
0x18000e10e  mov     r14, [r13+30h]
0x18000e112  mov     rsi, [rsp+78h+var_48]
0x18000e117  and     r14, rcx
0x18000e11a  add     r14, r14
0x18000e11d  mov     rax, [r15+r14*8+8]
0x18000e122  mov     [rsp+78h+Block], rax
0x18000e12a  mov     rbp, [rbx+18h]
0x18000e12e  mov     r12, rbx
0x18000e131  mov     rbx, [rbx]
0x18000e134  test    rbp, rbp
0x18000e137  jz      short loc_18000E14F
0x18000e139  mov     rcx, [rbp+10h]; Block
0x18000e13d  test    rcx, rcx
0x18000e140  jz      short loc_18000E147
0x18000e142  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e147  mov     rcx, rbp; Block
0x18000e14a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e14f  mov     edx, 20h ; ' '
0x18000e154  mov     rcx, r12; Block
0x18000e157  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000e15c  dec     qword ptr [r13+10h]
0x18000e160  cmp     r12, [rsp+78h+Block]
0x18000e168  jz      short loc_18000E174
0x18000e16a  cmp     rbx, rdi
0x18000e16d  jnz     short loc_18000E12A
0x18000e16f  jmp     loc_18000E097
0x18000e174  mov     rax, [rsp+78h+arg_10]
0x18000e17c  mov     [r15+r14*8], rax
0x18000e180  mov     [r15+r14*8+8], rax
0x18000e185  cmp     rbx, rdi
0x18000e188  jnz     loc_18000E0E3
0x18000e18e  jmp     loc_18000E09B
```
