# std::_Hash<std::_Umap_traits<_RPC_ASYNC_STATE *,std::unique_ptr<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>,std::_Uhash_compare<_RPC_ASYNC_STATE *,std::hash<_RPC_ASYNC_STATE *>,std::equal_to<_RPC_ASYNC_STATE *>>,std::allocator<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>>>,0>>::_Clear_guard::~_Clear_guard(void)

- ea: `0x18000cc3c`
- end: `0x18000cd17`
- name: `??1_Clear_guard@?$_Hash@V?$_Umap_traits@PEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_ODML_FIND_NEARBY_PACKAGES_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_ODML_FIND_NEARBY_PACKAGES_ASYNC@@@@@std@@@std@@V?$_Uhash_compare@PEAU_RPC_ASYNC_STATE@@U?$hash@PEAU_RPC_ASYNC_STATE@@@std@@U?$equal_to@PEAU_RPC_ASYNC_STATE@@@3@@3@V?$allocator@U?$pair@QEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_ODML_FIND_NEARBY_PACKAGES_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_ODML_FIND_NEARBY_PACKAGES_ASYNC@@@@@std@@@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ`
- size: `219`
- prototype: `void __fastcall(unsigned __int64 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000dd80`

## callees

- `0x180002534`
- `0x1800029b4`
- `0x18000cc3c`
- `0x18000dfac`

## pseudocode

```c
void __fastcall std::_Hash<std::_Umap_traits<_RPC_ASYNC_STATE *,std::unique_ptr<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>,std::_Uhash_compare<_RPC_ASYNC_STATE *,std::hash<_RPC_ASYNC_STATE *>,std::equal_to<_RPC_ASYNC_STATE *>>,std::allocator<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>>>,0>>::_Clear_guard::~_Clear_guard(
        unsigned __int64 **a1)
{
  unsigned __int64 *v1; // rdi
  unsigned __int64 v2; // rbx
  _QWORD *v3; // rbx
  _QWORD *v4; // rsi
  _QWORD *v5; // rbp
  void *v6; // rcx
  void *v7; // r8
  unsigned __int64 v8; // rcx

  v1 = *a1;
  if ( *a1 && v1[2] )
  {
    v2 = v1[1];
    if ( v1[7] >> 3 <= v1[2] )
    {
      **(_QWORD **)(v2 + 8) = 0;
      v3 = *(_QWORD **)v2;
      if ( v3 )
      {
        do
        {
          v4 = (_QWORD *)v3[3];
          v5 = (_QWORD *)*v3;
          if ( v4 )
          {
            v6 = (void *)v4[2];
            if ( v6 )
              operator delete(v6);
            operator delete(v4);
          }
          operator delete(v3);
          v3 = v5;
        }
        while ( v5 );
      }
      *(_QWORD *)v1[1] = v1[1];
      *(_QWORD *)(v1[1] + 8) = v1[1];
      v1[2] = 0;
      v7 = (void *)v1[3];
      v8 = (v1[4] - (unsigned __int64)v7 + 7) >> 3;
      if ( (unsigned __int64)v7 > v1[4] )
        v8 = 0;
      if ( v8 )
        memset64(v7, v1[1], v8);
    }
    else
    {
      std::_Hash<std::_Umap_traits<_RPC_ASYNC_STATE *,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA>>,std::_Uhash_compare<_RPC_ASYNC_STATE *,std::hash<_RPC_ASYNC_STATE *>,std::equal_to<_RPC_ASYNC_STATE *>>,std::allocator<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA>>>>,0>>::_Unchecked_erase(
        *a1,
        *(_QWORD *)v2,
        v1[1]);
    }
  }
}

```

## disassembly

```asm
0x18000cc3c  push    rbx
0x18000cc3e  push    rbp
0x18000cc3f  push    rsi
0x18000cc40  push    rdi
0x18000cc41  sub     rsp, 28h
0x18000cc45  mov     rdi, [rcx]
0x18000cc48  test    rdi, rdi
0x18000cc4b  jz      loc_18000CD0E
0x18000cc51  cmp     qword ptr [rdi+10h], 0
0x18000cc56  jz      loc_18000CD0E
0x18000cc5c  mov     rax, [rdi+38h]
0x18000cc60  mov     rbx, [rdi+8]
0x18000cc64  shr     rax, 3
0x18000cc68  cmp     rax, [rdi+10h]
0x18000cc6c  jbe     short loc_18000CC81
0x18000cc6e  mov     rdx, [rbx]
0x18000cc71  mov     r8, rbx
0x18000cc74  mov     rcx, rdi
0x18000cc77  call    ?_Unchecked_erase@?$_Hash@V?$_Umap_traits@PEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC@@@@@std@@@std@@V?$_Uhash_compare@PEAU_RPC_ASYNC_STATE@@U?$hash@PEAU_RPC_ASYNC_STATE@@@std@@U?$equal_to@PEAU_RPC_ASYNC_STATE@@@3@@3@V?$allocator@U?$pair@QEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC@@@@@std@@@std@@@std@@@3@$0A@@std@@@std@@AEAAPEAU?$_List_node@U?$pair@QEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC@@@@@std@@@std@@@std@@PEAX@2@PEAU32@QEAU32@@Z; std::_Hash<std::_Umap_traits<_RPC_ASYNC_STATE *,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA>>,std::_Uhash_compare<_RPC_ASYNC_STATE *,std::hash<_RPC_ASYNC_STATE *>,std::equal_to<_RPC_ASYNC_STATE *>>,std::allocator<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA>>>>,0>>::_Unchecked_erase(std::_List_node<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA>>>,void *> *,std::_List_node<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA>>>,void *> * const)
0x18000cc7c  jmp     loc_18000CD0E
0x18000cc81  mov     rax, [rbx+8]
0x18000cc85  mov     qword ptr [rax], 0
0x18000cc8c  mov     rbx, [rbx]
0x18000cc8f  test    rbx, rbx
0x18000cc92  jz      short loc_18000CCCB
0x18000cc94  mov     rsi, [rbx+18h]
0x18000cc98  mov     rbp, [rbx]
0x18000cc9b  test    rsi, rsi
0x18000cc9e  jz      short loc_18000CCB6
0x18000cca0  mov     rcx, [rsi+10h]; Block
0x18000cca4  test    rcx, rcx
0x18000cca7  jz      short loc_18000CCAE
0x18000cca9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ccae  mov     rcx, rsi; Block
0x18000ccb1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ccb6  mov     edx, 20h ; ' '
0x18000ccbb  mov     rcx, rbx; Block
0x18000ccbe  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000ccc3  mov     rbx, rbp
0x18000ccc6  test    rbp, rbp
0x18000ccc9  jnz     short loc_18000CC94
0x18000cccb  mov     rax, [rdi+8]
0x18000cccf  xor     edx, edx
0x18000ccd1  mov     [rax], rax
0x18000ccd4  mov     rax, [rdi+8]
0x18000ccd8  mov     [rax+8], rax
0x18000ccdc  mov     qword ptr [rdi+10h], 0
0x18000cce4  mov     r8, [rdi+18h]
0x18000cce8  mov     rcx, [rdi+20h]
0x18000ccec  mov     rax, [rdi+8]
0x18000ccf0  sub     rcx, r8
0x18000ccf3  add     rcx, 7
0x18000ccf7  shr     rcx, 3
0x18000ccfb  cmp     r8, [rdi+20h]
0x18000ccff  cmova   rcx, rdx
0x18000cd03  test    rcx, rcx
0x18000cd06  jz      short loc_18000CD0E
0x18000cd08  mov     rdi, r8
0x18000cd0b  rep stosq
0x18000cd0e  add     rsp, 28h
0x18000cd12  pop     rdi
0x18000cd13  pop     rsi
0x18000cd14  pop     rbp
0x18000cd15  pop     rbx
0x18000cd16  retn
```
