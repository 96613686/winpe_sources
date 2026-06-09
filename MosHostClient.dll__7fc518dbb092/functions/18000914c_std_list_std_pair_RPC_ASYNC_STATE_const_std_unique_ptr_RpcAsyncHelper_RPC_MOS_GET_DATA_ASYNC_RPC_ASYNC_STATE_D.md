# std::list<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>>,std::allocator<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>>>>::~list<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>>,std::allocator<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>>>>(void)

- ea: `0x18000914c`
- end: `0x1800091e4`
- name: `??1?$list@U?$pair@QEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@@std@@@std@@@std@@V?$allocator@U?$pair@QEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@@std@@@std@@@std@@@2@@std@@QEAA@XZ`
- size: `152`
- prototype: `void __fastcall(void **)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800092dc`
- `0x18001137b`
- `0x1800116f0`
- `0x180011730`

## callees

- `0x180002534`
- `0x1800029b4`
- `0x18000914c`
- `0x180012010`

## pseudocode

```c
void __fastcall std::list<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>>>::~list<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>>>(
        void **a1)
{
  _QWORD **v1; // rdx
  _QWORD *v3; // rbx
  _QWORD *v4; // rsi
  _QWORD *v5; // rbp
  _QWORD *v6; // rdi
  _QWORD *v7; // rcx

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
        v6 = (_QWORD *)v4[2];
        if ( v6 )
        {
          v7 = (_QWORD *)v6[7];
          if ( v7 )
          {
            LOBYTE(v1) = v7 != v6;
            (*(void (__fastcall **)(_QWORD *, _QWORD **))(*v7 + 32LL))(v7, v1);
            v6[7] = 0;
          }
          operator delete(v6);
        }
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
0x18000914c  push    rbx
0x18000914e  push    rbp
0x18000914f  push    rsi
0x180009150  push    rdi
0x180009151  push    r14
0x180009153  sub     rsp, 20h
0x180009157  mov     rdx, [rcx]
0x18000915a  mov     r14, rcx
0x18000915d  mov     rax, [rdx+8]
0x180009161  mov     qword ptr [rax], 0
0x180009168  mov     rbx, [rdx]
0x18000916b  test    rbx, rbx
0x18000916e  jz      short loc_1800091CD
0x180009170  mov     rsi, [rbx+18h]
0x180009174  mov     rbp, [rbx]
0x180009177  test    rsi, rsi
0x18000917a  jz      short loc_1800091B8
0x18000917c  mov     rdi, [rsi+10h]
0x180009180  test    rdi, rdi
0x180009183  jz      short loc_1800091B0
0x180009185  mov     rcx, [rdi+38h]
0x180009189  test    rcx, rcx
0x18000918c  jz      short loc_1800091A8
0x18000918e  mov     rax, [rcx]
0x180009191  cmp     rcx, rdi
0x180009194  setnz   dl
0x180009197  mov     rax, [rax+20h]
0x18000919b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091a0  mov     qword ptr [rdi+38h], 0
0x1800091a8  mov     rcx, rdi; Block
0x1800091ab  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800091b0  mov     rcx, rsi; Block
0x1800091b3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800091b8  mov     edx, 20h ; ' '
0x1800091bd  mov     rcx, rbx; Block
0x1800091c0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800091c5  mov     rbx, rbp
0x1800091c8  test    rbp, rbp
0x1800091cb  jnz     short loc_180009170
0x1800091cd  mov     rcx, [r14]; Block
0x1800091d0  mov     edx, 20h ; ' '
0x1800091d5  add     rsp, 20h
0x1800091d9  pop     r14
0x1800091db  pop     rdi
0x1800091dc  pop     rsi
0x1800091dd  pop     rbp
0x1800091de  pop     rbx
0x1800091df  jmp     ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
```
