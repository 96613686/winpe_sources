# utl::vector<Comms::RpcClient::Binders,utl::allocator<Comms::RpcClient::Binders>>::~vector<Comms::RpcClient::Binders,utl::allocator<Comms::RpcClient::Binders>>(void)

- ea: `0x1800031bc`
- end: `0x18000321e`
- name: `??1?$vector@UBinders@RpcClient@Comms@@V?$allocator@UBinders@RpcClient@Comms@@@utl@@@utl@@QEAA@XZ`
- size: `98`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180003260`
- `0x1800035f8`

## callees

- `0x180001178`
- `0x1800031bc`
- `0x180003224`

## pseudocode

```c
void __fastcall utl::vector<Comms::RpcClient::Binders,utl::allocator<Comms::RpcClient::Binders>>::~vector<Comms::RpcClient::Binders,utl::allocator<Comms::RpcClient::Binders>>(
        __int64 a1)
{
  RPC_WSTR *v1; // rsi
  __int64 v3; // rbx
  __int64 i; // rbx

  v1 = *(RPC_WSTR **)a1;
  if ( *(_QWORD *)a1 != -1 )
  {
    v3 = *(_QWORD *)(a1 + 8) - (_QWORD)v1;
    *(_QWORD *)(a1 + 8) = v1;
    for ( i = v3 >> 4; i; Comms::RpcClient::Binders::~Binders(&v1[2 * i]) )
      --i;
    operator delete(*(void **)a1);
  }
}

```

## disassembly

```asm
0x1800031bc  mov     [rsp+arg_0], rbx
0x1800031c1  mov     [rsp+arg_8], rsi
0x1800031c6  push    rdi
0x1800031c7  sub     rsp, 20h
0x1800031cb  mov     rsi, [rcx]
0x1800031ce  mov     rdi, rcx
0x1800031d1  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800031d5  jz      short loc_18000320E
0x1800031d7  mov     rbx, [rcx+8]
0x1800031db  sub     rbx, rsi
0x1800031de  mov     [rcx+8], rsi
0x1800031e2  sar     rbx, 4
0x1800031e6  jmp     short loc_1800031FA
0x1800031e8  dec     rbx
0x1800031eb  mov     rcx, rbx
0x1800031ee  shl     rcx, 4
0x1800031f2  add     rcx, rsi; String
0x1800031f5  call    ??1Binders@RpcClient@Comms@@QEAA@XZ; Comms::RpcClient::Binders::~Binders(void)
0x1800031fa  test    rbx, rbx
0x1800031fd  jnz     short loc_1800031E8
0x1800031ff  mov     rcx, [rdi]; Block
0x180003202  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180003209  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000320e  mov     rbx, [rsp+28h+arg_0]
0x180003213  mov     rsi, [rsp+28h+arg_8]
0x180003218  add     rsp, 20h
0x18000321c  pop     rdi
0x18000321d  retn
```
