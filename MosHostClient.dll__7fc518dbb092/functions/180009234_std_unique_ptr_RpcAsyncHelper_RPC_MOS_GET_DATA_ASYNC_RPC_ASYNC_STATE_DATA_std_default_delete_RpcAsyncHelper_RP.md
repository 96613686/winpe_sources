# std::unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>::~unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>(void)

- ea: `0x180009234`
- end: `0x18000928d`
- name: `??1?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@@std@@@std@@QEAA@XZ`
- size: `89`
- prototype: `void __fastcall(_QWORD **, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800113b9`

## callees

- `0x180002534`
- `0x180009234`
- `0x180012010`

## pseudocode

```c
void __fastcall std::unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>::~unique_ptr<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::RPC_ASYNC_STATE_DATA>>(
        _QWORD **a1,
        __int64 a2)
{
  _QWORD *v2; // rdi
  _QWORD *v3; // rbx
  _QWORD *v4; // rcx

  v2 = *a1;
  if ( *a1 )
  {
    v3 = (_QWORD *)v2[2];
    if ( v3 )
    {
      v4 = (_QWORD *)v3[7];
      if ( v4 )
      {
        LOBYTE(a2) = v4 != v3;
        (*(void (__fastcall **)(_QWORD *, __int64))(*v4 + 32LL))(v4, a2);
        v3[7] = 0;
      }
      operator delete(v3);
    }
    operator delete(v2);
  }
}

```

## disassembly

```asm
0x180009234  mov     [rsp+arg_0], rbx
0x180009239  push    rdi
0x18000923a  sub     rsp, 20h
0x18000923e  mov     rdi, [rcx]
0x180009241  test    rdi, rdi
0x180009244  jz      short loc_180009282
0x180009246  mov     rbx, [rdi+10h]
0x18000924a  test    rbx, rbx
0x18000924d  jz      short loc_18000927A
0x18000924f  mov     rcx, [rbx+38h]
0x180009253  test    rcx, rcx
0x180009256  jz      short loc_180009272
0x180009258  mov     rax, [rcx]
0x18000925b  cmp     rcx, rbx
0x18000925e  setnz   dl
0x180009261  mov     rax, [rax+20h]
0x180009265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000926a  mov     qword ptr [rbx+38h], 0
0x180009272  mov     rcx, rbx; Block
0x180009275  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000927a  mov     rcx, rdi; Block
0x18000927d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009282  mov     rbx, [rsp+28h+arg_0]
0x180009287  add     rsp, 20h
0x18000928b  pop     rdi
0x18000928c  retn
```
