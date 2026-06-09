# utl::vector<Comms::RpcClient::Binders,utl::allocator<Comms::RpcClient::Binders>>::_SetCapacity(unsigned __int64)

- ea: `0x1800035f8`
- end: `0x180003731`
- name: `?_SetCapacity@?$vector@UBinders@RpcClient@Comms@@V?$allocator@UBinders@RpcClient@Comms@@@utl@@@utl@@AEAA_N_K@Z`
- size: `313`
- prototype: `char __fastcall(__int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180003738`

## callees

- `0x180001178`
- `0x1800016e8`
- `0x1800031bc`
- `0x180003224`
- `0x1800035f8`

## pseudocode

```c
char __fastcall utl::vector<Comms::RpcClient::Binders,utl::allocator<Comms::RpcClient::Binders>>::_SetCapacity(
        __int64 a1,
        unsigned __int64 a2)
{
  __int64 v3; // rbx
  _OWORD *v4; // rdi
  char *v5; // r12
  char v6; // bp
  _OWORD *v7; // r8
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rax
  _OWORD *v11; // r15
  __int64 v12; // rbx
  char *v13; // r14
  __m128i si128; // [rsp+20h] [rbp-58h] BYREF
  __int64 v16; // [rsp+30h] [rbp-48h]

  if ( a2 > 0xFFFFFFFFFFFFFFFLL )
  {
    v4 = 0;
    v3 = a2;
  }
  else
  {
    v3 = a2;
    v4 = operator new(16 * a2, (const struct std::nothrow_t *)&std::nothrow);
  }
  si128.m128i_i64[0] = (__int64)v4;
  if ( !v4 )
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
    v16 = -1;
LABEL_7:
    v6 = 0;
    goto LABEL_16;
  }
  si128.m128i_i64[1] = (__int64)v4;
  v5 = (char *)&v4[v3];
  v16 = (__int64)&v4[v3];
  if ( v4 == (_OWORD *)-1LL )
    goto LABEL_7;
  v7 = *(_OWORD **)a1;
  v8 = 0;
  v9 = (__int64)(*(_QWORD *)(a1 + 8) - *(_QWORD *)a1) >> 4;
  v6 = 1;
  if ( v9 )
  {
    do
    {
      v10 = v8++;
      v4[v10] = v7[v10];
    }
    while ( v8 != v9 );
  }
  v11 = *(_OWORD **)a1;
  v12 = (__int64)(*(_QWORD *)(a1 + 8) - *(_QWORD *)a1) >> 4;
  v13 = (char *)&v4[v12];
  if ( *(_QWORD *)a1 != -1 )
  {
    *(_QWORD *)(a1 + 8) = v11;
    while ( v12 )
      Comms::RpcClient::Binders::~Binders((RPC_WSTR *)&v11[--v12]);
    operator delete(*(void **)a1);
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  *(_QWORD *)a1 = v4;
  *(_QWORD *)(a1 + 8) = v13;
  *(_QWORD *)(a1 + 16) = v5;
  v16 = -1;
LABEL_16:
  utl::vector<Comms::RpcClient::Binders,utl::allocator<Comms::RpcClient::Binders>>::~vector<Comms::RpcClient::Binders,utl::allocator<Comms::RpcClient::Binders>>((__int64)&si128);
  return v6;
}

```

## disassembly

```asm
0x1800035f8  push    rbx
0x1800035fa  push    rbp
0x1800035fb  push    rsi
0x1800035fc  push    rdi
0x1800035fd  push    r12
0x1800035ff  push    r14
0x180003601  push    r15
0x180003603  sub     rsp, 40h
0x180003607  mov     rax, 0FFFFFFFFFFFFFFFh
0x180003611  mov     rbx, rdx
0x180003614  mov     rsi, rcx
0x180003617  cmp     rdx, rax
0x18000361a  ja      short loc_180003634
0x18000361c  shl     rbx, 4
0x180003620  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180003627  mov     rcx, rbx; unsigned __int64
0x18000362a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000362f  mov     rdi, rax
0x180003632  jmp     short loc_18000363A
0x180003634  xor     edi, edi
0x180003636  shl     rbx, 4
0x18000363a  mov     qword ptr [rsp+78h+var_58], rdi
0x18000363f  test    rdi, rdi
0x180003642  jnz     short loc_18000365D
0x180003644  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18000364c  movdqu  [rsp+78h+var_58], xmm0
0x180003652  mov     [rsp+78h+var_48], 0FFFFFFFFFFFFFFFFh
0x18000365b  jmp     short loc_180003671
0x18000365d  mov     qword ptr [rsp+78h+var_58+8], rdi
0x180003662  lea     r12, [rbx+rdi]
0x180003666  mov     [rsp+78h+var_48], r12
0x18000366b  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18000366f  jnz     short loc_180003679
0x180003671  xor     bpl, bpl
0x180003674  jmp     loc_180003715
0x180003679  mov     r8, [rsi]
0x18000367c  xor     edx, edx
0x18000367e  mov     rcx, [rsi+8]
0x180003682  sub     rcx, r8
0x180003685  sar     rcx, 4
0x180003689  lea     ebp, [rdx+1]
0x18000368c  test    rcx, rcx
0x18000368f  jz      short loc_1800036A9
0x180003691  mov     rax, rdx
0x180003694  add     rdx, rbp
0x180003697  add     rax, rax
0x18000369a  movups  xmm0, xmmword ptr [r8+rax*8]
0x18000369f  movdqu  xmmword ptr [rdi+rax*8], xmm0
0x1800036a4  cmp     rdx, rcx
0x1800036a7  jnz     short loc_180003691
0x1800036a9  mov     r15, [rsi]
0x1800036ac  mov     rbx, [rsi+8]
0x1800036b0  sub     rbx, r15
0x1800036b3  sar     rbx, 4
0x1800036b7  mov     r14, rbx
0x1800036ba  shl     r14, 4
0x1800036be  add     r14, rdi
0x1800036c1  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x1800036c5  jz      short loc_1800036F3
0x1800036c7  mov     [rsi+8], r15
0x1800036cb  jmp     short loc_1800036DF
0x1800036cd  sub     rbx, rbp
0x1800036d0  mov     rcx, rbx
0x1800036d3  shl     rcx, 4
0x1800036d7  add     rcx, r15; String
0x1800036da  call    ??1Binders@RpcClient@Comms@@QEAA@XZ; Comms::RpcClient::Binders::~Binders(void)
0x1800036df  test    rbx, rbx
0x1800036e2  jnz     short loc_1800036CD
0x1800036e4  mov     rcx, [rsi]; Block
0x1800036e7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800036ee  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800036f3  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1800036fb  movdqu  [rsp+78h+var_58], xmm0
0x180003701  mov     [rsi], rdi
0x180003704  mov     [rsi+8], r14
0x180003708  mov     [rsi+10h], r12
0x18000370c  mov     [rsp+78h+var_48], 0FFFFFFFFFFFFFFFFh
0x180003715  lea     rcx, [rsp+78h+var_58]
0x18000371a  call    ??1?$vector@UBinders@RpcClient@Comms@@V?$allocator@UBinders@RpcClient@Comms@@@utl@@@utl@@QEAA@XZ; utl::vector<Comms::RpcClient::Binders,utl::allocator<Comms::RpcClient::Binders>>::~vector<Comms::RpcClient::Binders,utl::allocator<Comms::RpcClient::Binders>>(void)
0x18000371f  mov     al, bpl
0x180003722  add     rsp, 40h
0x180003726  pop     r15
0x180003728  pop     r14
0x18000372a  pop     r12
0x18000372c  pop     rdi
0x18000372d  pop     rsi
0x18000372e  pop     rbp
0x18000372f  pop     rbx
0x180003730  retn
```
