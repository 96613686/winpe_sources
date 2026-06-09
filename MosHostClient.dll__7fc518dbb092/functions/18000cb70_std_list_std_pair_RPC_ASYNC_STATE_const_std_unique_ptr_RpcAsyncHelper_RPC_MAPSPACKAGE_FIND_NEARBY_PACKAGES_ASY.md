# std::list<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>>,std::allocator<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>>>>::~list<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>>,std::allocator<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>>>>(void)

- ea: `0x18000cb70`
- end: `0x18000cbde`
- name: `??1?$list@U?$pair@QEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC@@@@@std@@@std@@@std@@V?$allocator@U?$pair@QEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC@@@@@std@@@std@@@std@@@2@@std@@QEAA@XZ`
- size: `110`
- prototype: `void __fastcall(void **)`
- caller_count: `6`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000cc14`
- `0x180011533`
- `0x180011770`
- `0x1800117b0`
- `0x1800117f0`
- `0x180011830`

## callees

- `0x180002534`
- `0x1800029b4`
- `0x18000cb70`

## pseudocode

```c
void __fastcall std::list<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>>>::~list<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>>>(
        void **a1)
{
  _QWORD **v1; // rdx
  _QWORD *v3; // rbx
  _QWORD *v4; // rdi
  _QWORD *v5; // rbp
  void *v6; // rcx

  v1 = (_QWORD **)*a1;
  **((_QWORD **)*a1 + 1) = 0;
  v3 = *v1;
  if ( *v1 )
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
  operator delete(*a1);
}

```

## disassembly

```asm
0x18000cb70  push    rbx
0x18000cb72  push    rbp
0x18000cb73  push    rsi
0x18000cb74  push    rdi
0x18000cb75  sub     rsp, 28h
0x18000cb79  mov     rdx, [rcx]
0x18000cb7c  mov     rsi, rcx
0x18000cb7f  mov     rax, [rdx+8]
0x18000cb83  mov     qword ptr [rax], 0
0x18000cb8a  mov     rbx, [rdx]
0x18000cb8d  test    rbx, rbx
0x18000cb90  jz      short loc_18000CBC9
0x18000cb92  mov     rdi, [rbx+18h]
0x18000cb96  mov     rbp, [rbx]
0x18000cb99  test    rdi, rdi
0x18000cb9c  jz      short loc_18000CBB4
0x18000cb9e  mov     rcx, [rdi+10h]; Block
0x18000cba2  test    rcx, rcx
0x18000cba5  jz      short loc_18000CBAC
0x18000cba7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000cbac  mov     rcx, rdi; Block
0x18000cbaf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000cbb4  mov     edx, 20h ; ' '
0x18000cbb9  mov     rcx, rbx; Block
0x18000cbbc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000cbc1  mov     rbx, rbp
0x18000cbc4  test    rbp, rbp
0x18000cbc7  jnz     short loc_18000CB92
0x18000cbc9  mov     rcx, [rsi]; Block
0x18000cbcc  mov     edx, 20h ; ' '
0x18000cbd1  add     rsp, 28h
0x18000cbd5  pop     rdi
0x18000cbd6  pop     rsi
0x18000cbd7  pop     rbp
0x18000cbd8  pop     rbx
0x18000cbd9  jmp     ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
```
