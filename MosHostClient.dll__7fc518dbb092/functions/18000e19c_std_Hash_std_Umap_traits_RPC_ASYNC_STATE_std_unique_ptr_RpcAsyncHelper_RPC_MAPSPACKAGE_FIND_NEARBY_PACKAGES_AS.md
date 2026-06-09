# std::_Hash<std::_Umap_traits<_RPC_ASYNC_STATE *,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>,std::_Uhash_compare<_RPC_ASYNC_STATE *,std::hash<_RPC_ASYNC_STATE *>,std::equal_to<_RPC_ASYNC_STATE *>>,std::allocator<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>>>,0>>::erase(_RPC_ASYNC_STATE * const &)

- ea: `0x18000e19c`
- end: `0x18000e2af`
- name: `?erase@?$_Hash@V?$_Umap_traits@PEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC@@@@@std@@@std@@V?$_Uhash_compare@PEAU_RPC_ASYNC_STATE@@U?$hash@PEAU_RPC_ASYNC_STATE@@@std@@U?$equal_to@PEAU_RPC_ASYNC_STATE@@@3@@3@V?$allocator@U?$pair@QEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC@@@@@std@@@std@@@std@@@3@$0A@@std@@@std@@QEAA_KAEBQEAU_RPC_ASYNC_STATE@@@Z`
- size: `275`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *)`
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000cd98`
- `0x18000e2c0`
- `0x18000e5f8`
- `0x18000e908`
- `0x18000f6f4`

## callees

- `0x180002534`
- `0x1800029b4`
- `0x18000e19c`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<_RPC_ASYNC_STATE *,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>,std::_Uhash_compare<_RPC_ASYNC_STATE *,std::hash<_RPC_ASYNC_STATE *>,std::equal_to<_RPC_ASYNC_STATE *>>,std::allocator<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>>>,0>>::erase(
        _QWORD *a1,
        _QWORD *a2)
{
  unsigned __int64 v2; // r9
  __int64 v5; // r8
  __int64 v6; // rsi
  __int64 v7; // rax
  __int64 v8; // r8
  __int64 v9; // rdx
  _QWORD *v10; // r9
  _QWORD *v11; // rbx
  __int64 v12; // rcx
  __int64 v13; // rcx
  _QWORD *v14; // rdi
  void *v15; // rcx

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
  v11 = *(_QWORD **)(v9 + 16 * v8 + 8);
  if ( v11 == v10 )
  {
LABEL_7:
    v11 = 0;
  }
  else
  {
    while ( *a2 != v11[2] )
    {
      if ( v11 == *(_QWORD **)(v9 + 16 * v8) )
        goto LABEL_7;
      v11 = (_QWORD *)v11[1];
    }
  }
  if ( !v11 )
    return 0;
  v12 = 16 * v8;
  if ( *(_QWORD **)(v9 + 16 * v8 + 8) == v11 )
  {
    if ( *(_QWORD **)(v12 + v9) == v11 )
      *(_QWORD *)(v12 + v9) = v10;
    else
      v10 = (_QWORD *)v11[1];
    *(_QWORD *)(v9 + 16 * v8 + 8) = v10;
  }
  else if ( *(_QWORD **)(v12 + v9) == v11 )
  {
    *(_QWORD *)(v12 + v9) = *v11;
  }
  v13 = *v11;
  --a1[2];
  *(_QWORD *)v11[1] = v13;
  *(_QWORD *)(v13 + 8) = v11[1];
  v14 = (_QWORD *)v11[3];
  if ( v14 )
  {
    v15 = (void *)v14[2];
    if ( v15 )
      operator delete(v15);
    operator delete(v14);
  }
  operator delete(v11);
  return v6;
}

```

## disassembly

```asm
0x18000e19c  mov     [rsp+arg_0], rbx
0x18000e1a1  mov     [rsp+arg_8], rsi
0x18000e1a6  push    rdi
0x18000e1a7  sub     rsp, 20h
0x18000e1ab  xor     r9d, r9d
0x18000e1ae  mov     r10, rdx
0x18000e1b1  mov     r11, rcx
0x18000e1b4  mov     r8, 0CBF29CE484222325h
0x18000e1be  lea     esi, [r9+1]
0x18000e1c2  movzx   eax, byte ptr [rdx+r9]
0x18000e1c7  mov     rcx, 100000001B3h
0x18000e1d1  xor     r8, rax
0x18000e1d4  add     r9, rsi
0x18000e1d7  imul    r8, rcx
0x18000e1db  cmp     r9, 8
0x18000e1df  jb      short loc_18000E1C2
0x18000e1e1  and     r8, [r11+30h]
0x18000e1e5  mov     rdx, [r11+18h]
0x18000e1e9  mov     rdi, r8
0x18000e1ec  mov     r9, [r11+8]
0x18000e1f0  add     rdi, rdi
0x18000e1f3  mov     rbx, [rdx+rdi*8+8]
0x18000e1f8  cmp     rbx, r9
0x18000e1fb  jz      short loc_18000E21B
0x18000e1fd  mov     rax, r8
0x18000e200  add     rax, rax
0x18000e203  mov     rcx, [rdx+rax*8]
0x18000e207  mov     rax, [r10]
0x18000e20a  cmp     rax, [rbx+10h]
0x18000e20e  jz      short loc_18000E21D
0x18000e210  cmp     rbx, rcx
0x18000e213  jz      short loc_18000E21B
0x18000e215  mov     rbx, [rbx+8]
0x18000e219  jmp     short loc_18000E20A
0x18000e21b  xor     ebx, ebx
0x18000e21d  mov     ecx, 10h
0x18000e222  test    rbx, rbx
0x18000e225  jz      short loc_18000E29A
0x18000e227  imul    rcx, r8
0x18000e22b  cmp     [rdx+rdi*8+8], rbx
0x18000e230  jnz     short loc_18000E249
0x18000e232  cmp     [rcx+rdx], rbx
0x18000e236  jnz     short loc_18000E23E
0x18000e238  mov     [rcx+rdx], r9
0x18000e23c  jmp     short loc_18000E242
0x18000e23e  mov     r9, [rbx+8]
0x18000e242  mov     [rdx+rdi*8+8], r9
0x18000e247  jmp     short loc_18000E256
0x18000e249  cmp     [rcx+rdx], rbx
0x18000e24d  jnz     short loc_18000E256
0x18000e24f  mov     rax, [rbx]
0x18000e252  mov     [rcx+rdx], rax
0x18000e256  mov     rcx, [rbx]
0x18000e259  dec     qword ptr [r11+10h]
0x18000e25d  mov     rax, [rbx+8]
0x18000e261  mov     [rax], rcx
0x18000e264  mov     rax, [rbx+8]
0x18000e268  mov     [rcx+8], rax
0x18000e26c  mov     rdi, [rbx+18h]
0x18000e270  test    rdi, rdi
0x18000e273  jz      short loc_18000E28B
0x18000e275  mov     rcx, [rdi+10h]; Block
0x18000e279  test    rcx, rcx
0x18000e27c  jz      short loc_18000E283
0x18000e27e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e283  mov     rcx, rdi; Block
0x18000e286  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e28b  mov     edx, 20h ; ' '
0x18000e290  mov     rcx, rbx; Block
0x18000e293  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000e298  jmp     short loc_18000E29C
0x18000e29a  xor     esi, esi
0x18000e29c  mov     rbx, [rsp+28h+arg_0]
0x18000e2a1  mov     rax, rsi
0x18000e2a4  mov     rsi, [rsp+28h+arg_8]
0x18000e2a9  add     rsp, 20h
0x18000e2ad  pop     rdi
0x18000e2ae  retn
```
