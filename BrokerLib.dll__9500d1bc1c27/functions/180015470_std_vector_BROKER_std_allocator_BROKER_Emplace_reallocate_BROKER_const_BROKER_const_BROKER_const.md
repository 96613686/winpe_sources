# std::vector<_BROKER *,std::allocator<_BROKER *>>::_Emplace_reallocate<_BROKER * const &>(_BROKER * * const,_BROKER * const &)

- ea: `0x180015470`
- end: `0x1800155cd`
- name: `??$_Emplace_reallocate@AEBQEAU_BROKER@@@?$vector@PEAU_BROKER@@V?$allocator@PEAU_BROKER@@@std@@@std@@AEAAPEAPEAU_BROKER@@QEAPEAU2@AEBQEAU2@@Z`
- size: `349`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001364c`

## callees

- `0x180004be0`
- `0x180004e38`
- `0x1800117dc`
- `0x180015470`
- `0x1800155d4`
- `0x1800165b6`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800154b0`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800154b0`

## pseudocode

```c
char *__fastcall std::vector<_BROKER *>::_Emplace_reallocate<_BROKER * const &>(__int64 a1, _BYTE *a2, __int64 *a3)
{
  __int64 v4; // rbx
  __int64 v6; // rax
  unsigned __int64 v7; // rsi
  unsigned __int64 v8; // rcx
  __int64 v9; // r14
  unsigned __int64 v10; // rdx
  __int64 size_of; // rax
  char *v12; // rax
  __int64 v13; // rcx
  char *v14; // rdi
  char *v15; // r14
  const void *v16; // rdx
  void *v17; // rcx
  size_t v18; // r8
  _QWORD v20[3]; // [rsp+20h] [rbp-68h] BYREF
  char *v21; // [rsp+38h] [rbp-50h]
  _QWORD *v22; // [rsp+40h] [rbp-48h]

  v4 = 0x1FFFFFFFFFFFFFFFLL;
  v6 = (__int64)(xmmword_180028998 - (_QWORD)Broker::g_DeletedBrokers) >> 3;
  if ( v6 == 0x1FFFFFFFFFFFFFFFLL )
    std::_Xlength_error("vector too long");
  v7 = v6 + 1;
  v8 = (__int64)(*((_QWORD *)&xmmword_180028998 + 1) - (_QWORD)Broker::g_DeletedBrokers) >> 3;
  v9 = (a2 - (_BYTE *)Broker::g_DeletedBrokers) >> 3;
  v10 = v8 >> 1;
  if ( v8 <= 0x1FFFFFFFFFFFFFFFLL - (v8 >> 1) )
  {
    v4 = v10 + v8;
    if ( v10 + v8 < v7 )
      v4 = v6 + 1;
  }
  size_of = std::_Get_size_of_n<8>(v4);
  v12 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  v13 = *a3;
  v14 = v12;
  v20[2] = v4;
  v15 = &v12[8 * v9];
  *(_QWORD *)v15 = v13;
  v16 = Broker::g_DeletedBrokers;
  v17 = v12;
  v20[0] = &Broker::g_DeletedBrokers;
  v22 = v15 + 8;
  v21 = v15;
  if ( a2 == (_BYTE *)xmmword_180028998 )
  {
    v18 = xmmword_180028998 - (_QWORD)Broker::g_DeletedBrokers;
  }
  else
  {
    memmove_0(v12, Broker::g_DeletedBrokers, a2 - (_BYTE *)Broker::g_DeletedBrokers);
    v16 = a2;
    v18 = xmmword_180028998 - (_QWORD)a2;
    v21 = v14;
    v17 = v15 + 8;
  }
  memmove_0(v17, v16, v18);
  v20[1] = 0;
  if ( Broker::g_DeletedBrokers )
    std::_Deallocate<16>(
      Broker::g_DeletedBrokers,
      (*((_QWORD *)&xmmword_180028998 + 1) - (_QWORD)Broker::g_DeletedBrokers) & 0xFFFFFFFFFFFFFFF8uLL);
  Broker::g_DeletedBrokers = v14;
  *(_QWORD *)&xmmword_180028998 = &v14[8 * v7];
  *((_QWORD *)&xmmword_180028998 + 1) = &v14[8 * v4];
  std::vector<unsigned __int64>::_Reallocation_guard::~_Reallocation_guard(v20);
  return v15;
}

```

## disassembly

```asm
0x180015470  push    rbx
0x180015472  push    rbp
0x180015473  push    rsi
0x180015474  push    rdi
0x180015475  push    r12
0x180015477  push    r14
0x180015479  push    r15
0x18001547b  sub     rsp, 50h
0x18001547f  mov     rax, qword ptr cs:xmmword_180028998
0x180015486  mov     rbp, rdx
0x180015489  mov     rdx, cs:?g_DeletedBrokers@Broker@@3V?$vector@PEAU_BROKER@@V?$allocator@PEAU_BROKER@@@std@@@std@@A; std::vector<_BROKER *> Broker::g_DeletedBrokers
0x180015490  mov     rbx, 1FFFFFFFFFFFFFFFh
0x18001549a  sub     rax, rdx
0x18001549d  mov     r12, r8
0x1800154a0  sar     rax, 3
0x1800154a4  cmp     rax, rbx
0x1800154a7  jnz     short loc_1800154B7
0x1800154a9  lea     rcx, aVectorTooLong; "vector too long"
0x1800154b0  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800154b7  mov     rcx, qword ptr cs:xmmword_180028998+8
0x1800154be  lea     rsi, [rax+1]
0x1800154c2  sub     rcx, rdx
0x1800154c5  mov     r14, rbp
0x1800154c8  sub     r14, rdx
0x1800154cb  sar     rcx, 3
0x1800154cf  mov     rdx, rcx
0x1800154d2  sar     r14, 3
0x1800154d6  shr     rdx, 1
0x1800154d9  mov     rax, rbx
0x1800154dc  sub     rax, rdx
0x1800154df  cmp     rcx, rax
0x1800154e2  ja      short loc_1800154EF
0x1800154e4  lea     rbx, [rdx+rcx]
0x1800154e8  cmp     rbx, rsi
0x1800154eb  cmovb   rbx, rsi
0x1800154ef  mov     rcx, rbx
0x1800154f2  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x1800154f7  mov     rcx, rax
0x1800154fa  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800154ff  mov     rcx, [r12]
0x180015503  mov     rdi, rax
0x180015506  mov     [rsp+88h+var_58], rbx
0x18001550b  lea     r14, [rax+r14*8]
0x18001550f  mov     [r14], rcx
0x180015512  lea     r15, [r14+8]
0x180015516  mov     r8, qword ptr cs:xmmword_180028998
0x18001551d  lea     rax, ?g_DeletedBrokers@Broker@@3V?$vector@PEAU_BROKER@@V?$allocator@PEAU_BROKER@@@std@@@std@@A; std::vector<_BROKER *> Broker::g_DeletedBrokers
0x180015524  mov     rdx, cs:?g_DeletedBrokers@Broker@@3V?$vector@PEAU_BROKER@@V?$allocator@PEAU_BROKER@@@std@@@std@@A; Src
0x18001552b  mov     rcx, rdi; void *
0x18001552e  mov     [rsp+88h+var_68], rax
0x180015533  mov     [rsp+88h+var_48], r15
0x180015538  mov     [rsp+88h+var_50], r14
0x18001553d  cmp     rbp, r8
0x180015540  jnz     short loc_180015547
0x180015542  sub     r8, rdx
0x180015545  jmp     short loc_180015567
0x180015547  mov     r8, rbp
0x18001554a  sub     r8, rdx; Size
0x18001554d  call    memmove_0
0x180015552  mov     r8, qword ptr cs:xmmword_180028998
0x180015559  mov     rdx, rbp; Src
0x18001555c  sub     r8, rbp; Size
0x18001555f  mov     [rsp+88h+var_50], rdi
0x180015564  mov     rcx, r15; void *
0x180015567  call    memmove_0
0x18001556c  mov     rcx, cs:?g_DeletedBrokers@Broker@@3V?$vector@PEAU_BROKER@@V?$allocator@PEAU_BROKER@@@std@@@std@@A; std::vector<_BROKER *> Broker::g_DeletedBrokers
0x180015573  mov     [rsp+88h+var_60], 0
0x18001557c  test    rcx, rcx
0x18001557f  jz      short loc_180015594
0x180015581  mov     rdx, qword ptr cs:xmmword_180028998+8
0x180015588  sub     rdx, rcx
0x18001558b  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18001558f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180015594  lea     rcx, [rdi+rsi*8]
0x180015598  mov     cs:?g_DeletedBrokers@Broker@@3V?$vector@PEAU_BROKER@@V?$allocator@PEAU_BROKER@@@std@@@std@@A, rdi; std::vector<_BROKER *> Broker::g_DeletedBrokers
0x18001559f  mov     qword ptr cs:xmmword_180028998, rcx
0x1800155a6  lea     rcx, [rdi+rbx*8]
0x1800155aa  mov     qword ptr cs:xmmword_180028998+8, rcx
0x1800155b1  lea     rcx, [rsp+88h+var_68]
0x1800155b6  call    ??1_Reallocation_guard@?$vector@_KV?$allocator@_K@std@@@std@@QEAA@XZ; std::vector<unsigned __int64>::_Reallocation_guard::~_Reallocation_guard(void)
0x1800155bb  mov     rax, r14
0x1800155be  add     rsp, 50h
0x1800155c2  pop     r15
0x1800155c4  pop     r14
0x1800155c6  pop     r12
0x1800155c8  pop     rdi
0x1800155c9  pop     rsi
0x1800155ca  pop     rbp
0x1800155cb  pop     rbx
0x1800155cc  retn
```
