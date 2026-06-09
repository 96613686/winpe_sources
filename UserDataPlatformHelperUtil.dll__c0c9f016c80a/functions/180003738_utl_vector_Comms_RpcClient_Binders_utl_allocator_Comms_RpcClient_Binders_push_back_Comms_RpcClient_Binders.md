# utl::vector<Comms::RpcClient::Binders,utl::allocator<Comms::RpcClient::Binders>>::push_back(Comms::RpcClient::Binders &&)

- ea: `0x180003738`
- end: `0x1800037dd`
- name: `?push_back@?$vector@UBinders@RpcClient@Comms@@V?$allocator@UBinders@RpcClient@Comms@@@utl@@@utl@@QEAA_N$$QEAUBinders@RpcClient@Comms@@@Z`
- size: `165`
- prototype: `char __fastcall(__int64 *, _OWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003330`

## callees

- `0x1800035f8`
- `0x180003738`

## pseudocode

```c
char __fastcall utl::vector<Comms::RpcClient::Binders,utl::allocator<Comms::RpcClient::Binders>>::push_back(
        __int64 *a1,
        _OWORD *a2)
{
  _OWORD *v2; // rax
  _OWORD *v4; // rcx
  _OWORD *v5; // rdi
  __int64 v6; // rsi
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // rdx

  v2 = (_OWORD *)a1[1];
  v4 = (_OWORD *)a1[2];
  v5 = a2;
  if ( v2 != v4 )
  {
    *v2 = *a2;
LABEL_10:
    a1[1] += 16;
    return 1;
  }
  v6 = *a1;
  v7 = ((__int64)v4 - *a1) >> 4;
  v8 = 7 * (v7 >> 2) + 8;
  if ( v8 > 0x7FFFFFFFFFFFFFFLL )
    v8 = 0x7FFFFFFFFFFFFFFLL;
  if ( v7 < v8
    && utl::vector<Comms::RpcClient::Binders,utl::allocator<Comms::RpcClient::Binders>>::_SetCapacity((__int64)a1, v8) )
  {
    if ( (unsigned __int64)v5 - v6 < a1[1] - *a1 )
      v5 = (_OWORD *)((char *)v5 + *a1 - v6);
    *(_OWORD *)a1[1] = *v5;
    goto LABEL_10;
  }
  return 0;
}

```

## disassembly

```asm
0x180003738  mov     [rsp+arg_0], rbx
0x18000373d  mov     [rsp+arg_8], rsi
0x180003742  push    rdi
0x180003743  sub     rsp, 20h
0x180003747  mov     rax, [rcx+8]
0x18000374b  mov     rbx, rcx
0x18000374e  mov     rcx, [rcx+10h]
0x180003752  mov     rdi, rdx
0x180003755  cmp     rax, rcx
0x180003758  jz      short loc_180003763
0x18000375a  movups  xmm0, xmmword ptr [rdx]
0x18000375d  movdqu  xmmword ptr [rax], xmm0
0x180003761  jmp     short loc_1800037C2
0x180003763  mov     rsi, [rbx]
0x180003766  sub     rcx, rsi
0x180003769  sar     rcx, 4
0x18000376d  mov     rax, rcx
0x180003770  shr     rax, 2
0x180003774  imul    rdx, rax, 7
0x180003778  mov     rax, 7FFFFFFFFFFFFFFh
0x180003782  add     rdx, 8
0x180003786  cmp     rdx, rax
0x180003789  cmova   rdx, rax
0x18000378d  cmp     rcx, rdx
0x180003790  jnb     short loc_1800037CB
0x180003792  mov     rcx, rbx
0x180003795  call    ?_SetCapacity@?$vector@UBinders@RpcClient@Comms@@V?$allocator@UBinders@RpcClient@Comms@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<Comms::RpcClient::Binders,utl::allocator<Comms::RpcClient::Binders>>::_SetCapacity(unsigned __int64)
0x18000379a  test    al, al
0x18000379c  jz      short loc_1800037CB
0x18000379e  mov     r8, [rbx+8]
0x1800037a2  mov     rcx, rdi
0x1800037a5  mov     rdx, [rbx]
0x1800037a8  mov     rax, r8
0x1800037ab  sub     rax, rdx
0x1800037ae  sub     rcx, rsi
0x1800037b1  cmp     rcx, rax
0x1800037b4  jnb     short loc_1800037BA
0x1800037b6  lea     rdi, [rcx+rdx]
0x1800037ba  movups  xmm0, xmmword ptr [rdi]
0x1800037bd  movdqu  xmmword ptr [r8], xmm0
0x1800037c2  add     qword ptr [rbx+8], 10h
0x1800037c7  mov     al, 1
0x1800037c9  jmp     short loc_1800037CD
0x1800037cb  xor     al, al
0x1800037cd  mov     rbx, [rsp+28h+arg_0]
0x1800037d2  mov     rsi, [rsp+28h+arg_8]
0x1800037d7  add     rsp, 20h
0x1800037db  pop     rdi
0x1800037dc  retn
```
