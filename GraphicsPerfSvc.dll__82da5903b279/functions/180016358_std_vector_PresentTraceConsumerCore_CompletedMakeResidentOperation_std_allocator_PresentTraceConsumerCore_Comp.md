# std::vector<PresentTraceConsumerCore::CompletedMakeResidentOperation,std::allocator<PresentTraceConsumerCore::CompletedMakeResidentOperation>>::_Emplace_reallocate<PresentTraceConsumerCore::CompletedMakeResidentOperation>(PresentTraceConsumerCore::CompletedMakeResidentOperation * const,PresentTraceConsumerCore::CompletedMakeResidentOperation &&)

- ea: `0x180016358`
- end: `0x180016490`
- name: `??$_Emplace_reallocate@UCompletedMakeResidentOperation@PresentTraceConsumerCore@@@?$vector@UCompletedMakeResidentOperation@PresentTraceConsumerCore@@V?$allocator@UCompletedMakeResidentOperation@PresentTraceConsumerCore@@@std@@@std@@AEAAPEAUCompletedMakeResidentOperation@PresentTraceConsumerCore@@QEAU23@$$QEAU23@@Z`
- size: `312`
- prototype: `_OWORD *__fastcall(const void **, _BYTE *, __int128 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001aab8`

## callees

- `0x180004b41`
- `0x18000b550`
- `0x18000c1b8`
- `0x18000c284`
- `0x180015984`
- `0x180016358`
- `0x180018768`

## pseudocode

```c
_OWORD *__fastcall std::vector<PresentTraceConsumerCore::CompletedMakeResidentOperation>::_Emplace_reallocate<PresentTraceConsumerCore::CompletedMakeResidentOperation>(
        const void **a1,
        _BYTE *a2,
        __int128 *a3)
{
  __int64 v3; // rbx
  __int64 v5; // rsi
  signed __int64 v8; // r14
  unsigned __int64 v9; // rsi
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rdx
  size_t size_of; // rax
  _QWORD *v13; // rax
  __int128 v14; // xmm0
  _OWORD *v15; // r14
  _QWORD *v16; // rbp
  void *v17; // rcx
  _BYTE *v18; // r8
  _BYTE *v19; // rdx
  size_t v20; // r8
  void *v21; // rcx
  _QWORD v23[3]; // [rsp+20h] [rbp-78h] BYREF
  _OWORD *v24; // [rsp+38h] [rbp-60h]
  _OWORD *v25; // [rsp+40h] [rbp-58h]

  v3 = 0xFFFFFFFFFFFFFFFLL;
  v5 = ((_BYTE *)a1[1] - (_BYTE *)*a1) >> 4;
  if ( v5 == 0xFFFFFFFFFFFFFFFLL )
    std::vector<std::pair<enum PresentTraceConsumerCore::TimeoutReason,std::shared_ptr<IPresentEventConsumer>>>::_Xlength();
  v8 = a2 - (_BYTE *)*a1;
  v9 = v5 + 1;
  v10 = ((_BYTE *)a1[2] - (_BYTE *)*a1) >> 4;
  v11 = v10 >> 1;
  if ( v10 <= 0xFFFFFFFFFFFFFFFLL - (v10 >> 1) )
  {
    v3 = v11 + v10;
    if ( v11 + v10 < v9 )
      v3 = v9;
  }
  size_of = std::_Get_size_of_n<16>(v3);
  v13 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  v14 = *a3;
  v23[0] = a1;
  v15 = (_OWORD *)((char *)v13 + (v8 & 0xFFFFFFFFFFFFFFF0uLL));
  v23[2] = v3;
  v16 = v13;
  v24 = v15;
  v17 = v13;
  *v15 = v14;
  v18 = a1[1];
  v19 = *a1;
  v25 = v15 + 1;
  if ( a2 == v18 )
  {
    v20 = v18 - v19;
  }
  else
  {
    memmove_0(v13, v19, a2 - (_BYTE *)*a1);
    v19 = a2;
    v20 = (_BYTE *)a1[1] - a2;
    v24 = v16;
    v17 = v15 + 1;
  }
  memmove_0(v17, v19, v20);
  v21 = (void *)*a1;
  v23[1] = 0;
  if ( v21 )
    std::_Deallocate<16>(v21, ((_BYTE *)a1[2] - (_BYTE *)v21) & 0xFFFFFFFFFFFFFFF0uLL);
  *a1 = v16;
  a1[1] = &v16[2 * v9];
  a1[2] = &v16[2 * v3];
  std::vector<PresentTraceConsumerCore::CompletedMakeResidentOperation>::_Reallocation_guard::~_Reallocation_guard(v23);
  return v15;
}

```

## disassembly

```asm
0x180016358  push    rbx
0x18001635a  push    rbp
0x18001635b  push    rsi
0x18001635c  push    rdi
0x18001635d  push    r12
0x18001635f  push    r13
0x180016361  push    r14
0x180016363  push    r15
0x180016365  sub     rsp, 58h
0x180016369  mov     rsi, [rcx+8]
0x18001636d  mov     rbx, 0FFFFFFFFFFFFFFFh
0x180016377  sub     rsi, [rcx]
0x18001637a  mov     r13, r8
0x18001637d  sar     rsi, 4
0x180016381  mov     r15, rdx
0x180016384  mov     rdi, rcx
0x180016387  cmp     rsi, rbx
0x18001638a  jz      loc_18001648A
0x180016390  mov     r14, rdx
0x180016393  mov     rax, rbx
0x180016396  sub     r14, [rcx]
0x180016399  mov     rcx, [rcx+10h]
0x18001639d  inc     rsi
0x1800163a0  sub     rcx, [rdi]
0x1800163a3  sar     rcx, 4
0x1800163a7  mov     rdx, rcx
0x1800163aa  shr     rdx, 1
0x1800163ad  sub     rax, rdx
0x1800163b0  cmp     rcx, rax
0x1800163b3  ja      short loc_1800163C0
0x1800163b5  lea     rbx, [rdx+rcx]
0x1800163b9  cmp     rbx, rsi
0x1800163bc  cmovb   rbx, rsi
0x1800163c0  mov     rcx, rbx
0x1800163c3  call    ??$_Get_size_of_n@$0BA@@std@@YA_K_K@Z; std::_Get_size_of_n<16>(unsigned __int64)
0x1800163c8  mov     rcx, rax
0x1800163cb  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800163d0  movups  xmm0, xmmword ptr [r13+0]
0x1800163d5  and     r14, 0FFFFFFFFFFFFFFF0h
0x1800163d9  mov     [rsp+98h+var_78], rdi
0x1800163de  add     r14, rax
0x1800163e1  mov     [rsp+98h+var_68], rbx
0x1800163e6  mov     rbp, rax
0x1800163e9  mov     [rsp+98h+var_60], r14
0x1800163ee  mov     rcx, rax; void *
0x1800163f1  movdqu  xmmword ptr [r14], xmm0
0x1800163f6  mov     r8, [rdi+8]
0x1800163fa  lea     r12, [r14+10h]
0x1800163fe  mov     rdx, [rdi]; Src
0x180016401  mov     [rsp+98h+var_58], r12
0x180016406  cmp     r15, r8
0x180016409  jnz     short loc_180016410
0x18001640b  sub     r8, rdx
0x18001640e  jmp     short loc_18001642D
0x180016410  mov     r8, r15
0x180016413  sub     r8, [rdi]; Size
0x180016416  call    memmove_0
0x18001641b  mov     r8, [rdi+8]
0x18001641f  mov     rdx, r15; Src
0x180016422  sub     r8, r15; Size
0x180016425  mov     [rsp+98h+var_60], rbp
0x18001642a  mov     rcx, r12; void *
0x18001642d  call    memmove_0
0x180016432  mov     rcx, [rdi]
0x180016435  mov     [rsp+98h+var_70], 0
0x18001643e  test    rcx, rcx
0x180016441  jz      short loc_180016453
0x180016443  mov     rdx, [rdi+10h]
0x180016447  sub     rdx, rcx
0x18001644a  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18001644e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180016453  mov     [rdi], rbp
0x180016456  lea     rcx, [rsp+98h+var_78]
0x18001645b  shl     rsi, 4
0x18001645f  shl     rbx, 4
0x180016463  add     rsi, rbp
0x180016466  add     rbx, rbp
0x180016469  mov     [rdi+8], rsi
0x18001646d  mov     [rdi+10h], rbx
0x180016471  call    ??1_Reallocation_guard@?$vector@UCompletedMakeResidentOperation@PresentTraceConsumerCore@@V?$allocator@UCompletedMakeResidentOperation@PresentTraceConsumerCore@@@std@@@std@@QEAA@XZ; std::vector<PresentTraceConsumerCore::CompletedMakeResidentOperation>::_Reallocation_guard::~_Reallocation_guard(void)
0x180016476  mov     rax, r14
0x180016479  add     rsp, 58h
0x18001647d  pop     r15
0x18001647f  pop     r14
0x180016481  pop     r13
0x180016483  pop     r12
0x180016485  pop     rdi
0x180016486  pop     rsi
0x180016487  pop     rbp
0x180016488  pop     rbx
0x180016489  retn
0x18001648a  call    ?_Xlength@?$vector@U?$pair@W4TimeoutReason@PresentTraceConsumerCore@@V?$shared_ptr@UIPresentEventConsumer@@@std@@@std@@V?$allocator@U?$pair@W4TimeoutReason@PresentTraceConsumerCore@@V?$shared_ptr@UIPresentEventConsumer@@@std@@@std@@@2@@std@@CAXXZ; std::vector<std::pair<PresentTraceConsumerCore::TimeoutReason,std::shared_ptr<IPresentEventConsumer>>>::_Xlength(void)
```
