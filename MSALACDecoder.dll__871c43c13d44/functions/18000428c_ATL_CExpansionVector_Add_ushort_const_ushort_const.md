# ATL::CExpansionVector::Add(ushort const *,ushort const *)

- ea: `0x18000428c`
- end: `0x180004487`
- name: `?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z`
- size: `507`
- prototype: `int(ATL::CExpansionVector *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800045c0`
- `0x180006bcc`
- `0x180006ef4`

## callees

- `0x180001144`
- `0x180001150`
- `0x18000428c`
- `0x180007274`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x1800043ff`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x18000441e`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x1800043ff`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x18000441e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CExpansionVector::Add(
        ATL::CExpansionVector *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  const unsigned __int16 *v3; // r12
  const unsigned __int16 *v4; // r13
  ATL::CExpansionVector *v5; // r14
  __int64 v6; // rax
  unsigned __int64 v7; // rax
  ATL::Checked *v8; // r15
  __int64 v9; // rcx
  ATL::Checked *v10; // rbx
  unsigned int v11; // r12d
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rdx
  ATL::Checked **v15; // rcx
  ATL::Checked **v16; // rcx
  ATL::Checked *v17; // rdi
  unsigned __int64 v19; // [rsp+20h] [rbp-58h]
  unsigned __int64 v21; // [rsp+20h] [rbp-58h]
  void *v22; // [rsp+28h] [rbp-50h]
  ATL::Checked *v23; // [rsp+30h] [rbp-48h]
  unsigned __int64 v25; // [rsp+38h] [rbp-40h]
  ATL::Checked *v35; // [rsp+98h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  v5 = this;
  if ( !a2 || !a3 )
    return 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v25 = 2 * v6 + 2;
  v7 = 2 * v25;
  if ( !is_mul_ok(v25, 2u) )
    v7 = -1;
  try
  {
    v8 = (ATL::Checked *)operator new[](v7);
    v35 = v8;
  }
  catch ( ... )
  {
    v5 = this;
    v3 = a3;
    v4 = a2;
    v8 = v35;
  }
  try
  {
    v17 = v8;
    v23 = v8;
    v9 = -1;
    do
      ++v9;
    while ( v3[v9] );
    v22 = (void *)(2LL * ((int)v9 + 1));
    v10 = (ATL::Checked *)operator new[](saturated_mul((unsigned __int64)v22, 2u));
    v19 = (unsigned __int64)v10;
  }
  catch ( ... )
  {
    v5 = this;
    v3 = a3;
    v4 = a2;
    v8 = v35;
    v17 = v23;
    v10 = (ATL::Checked *)v19;
  }
  if ( v8
    && v10
    && (ATL::Checked::memcpy_s(v8, (void *)v25, (unsigned __int64)v4, (const void *)v25, v19),
        ATL::Checked::memcpy_s(v10, v22, (unsigned __int64)v3, v22, v21),
        v11 = 1,
        (v12 = _o__recalloc(*(_QWORD *)v5, *((_DWORD *)v5 + 4) + 1, 8)) != 0)
    && (*(_QWORD *)v5 = v12, (v13 = _o__recalloc(*((_QWORD *)v5 + 1), *((_DWORD *)v5 + 4) + 1, 8)) != 0) )
  {
    *((_QWORD *)v5 + 1) = v13;
    v14 = *((int *)v5 + 4);
    v15 = (ATL::Checked **)(*(_QWORD *)v5 + 8 * v14);
    if ( v15 )
      *v15 = v8;
    v16 = (ATL::Checked **)(*((_QWORD *)v5 + 1) + 8 * v14);
    if ( v16 )
      *v16 = v10;
    ++*((_DWORD *)v5 + 4);
    v17 = 0;
    v10 = 0;
  }
  else
  {
    v11 = 0;
  }
  operator delete(v10);
  operator delete(v17);
  return v11;
}

```

## disassembly

```asm
0x18000428c  mov     [rsp+arg_10], r8
0x180004291  mov     [rsp+arg_8], rdx
0x180004296  mov     [rsp+arg_0], rcx
0x18000429b  push    rbx
0x18000429c  push    rsi
0x18000429d  push    rdi
0x18000429e  push    r12
0x1800042a0  push    r13
0x1800042a2  push    r14
0x1800042a4  push    r15
0x1800042a6  sub     rsp, 40h
0x1800042aa  mov     r12, r8
0x1800042ad  mov     r13, rdx
0x1800042b0  mov     r14, rcx
0x1800042b3  xor     esi, esi
0x1800042b5  test    rdx, rdx
0x1800042b8  jz      loc_180004475
0x1800042be  test    r8, r8
0x1800042c1  jz      loc_180004475
0x1800042c7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800042cb  mov     rax, rbx
0x1800042ce  inc     rax
0x1800042d1  cmp     [rdx+rax*2], si
0x1800042d5  jnz     short loc_1800042CE
0x1800042d7  lea     rcx, ds:2[rax*2]
0x1800042df  mov     [rsp+78h+var_40], rcx
0x1800042e4  mov     [rsp+78h+arg_18], rsi
0x1800042ec  mov     eax, 2
0x1800042f1  mul     rcx
0x1800042f4  cmovb   rax, rbx
0x1800042f8  mov     rcx, rax; unsigned __int64
0x1800042fb  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180004300  mov     r15, rax
0x180004303  mov     [rsp+78h+arg_18], rax
0x18000430b  jmp     short loc_180004333
0x18000430d  xor     esi, esi
0x18000430f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180004313  mov     r14, [rsp+78h+arg_0]
0x18000431b  mov     r12, [rsp+78h+arg_10]
0x180004323  mov     r13, [rsp+78h+arg_8]
0x18000432b  mov     r15, [rsp+78h+arg_18]
0x180004333  mov     rdi, r15
0x180004336  mov     [rsp+78h+var_48], r15
0x18000433b  mov     rcx, rbx
0x18000433e  inc     rcx
0x180004341  cmp     [r12+rcx*2], si
0x180004346  jnz     short loc_18000433E
0x180004348  inc     ecx
0x18000434a  movsxd  rcx, ecx
0x18000434d  add     rcx, rcx
0x180004350  mov     [rsp+78h+var_50], rcx
0x180004355  mov     [rsp+78h+var_58], rsi
0x18000435a  mov     eax, 2
0x18000435f  mul     rcx
0x180004362  cmovb   rax, rbx
0x180004366  mov     rcx, rax; unsigned __int64
0x180004369  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000436e  mov     rbx, rax
0x180004371  mov     [rsp+78h+var_58], rax
0x180004376  jmp     short loc_1800043A4
0x180004378  xor     esi, esi
0x18000437a  mov     r14, [rsp+78h+arg_0]
0x180004382  mov     r12, [rsp+78h+arg_10]
0x18000438a  mov     r13, [rsp+78h+arg_8]
0x180004392  mov     r15, [rsp+78h+arg_18]
0x18000439a  mov     rdi, [rsp+78h+var_48]
0x18000439f  mov     rbx, [rsp+78h+var_58]
0x1800043a4  mov     [rsp+78h+arg_8], rbx
0x1800043ac  test    r15, r15
0x1800043af  jz      loc_18000445C
0x1800043b5  test    rbx, rbx
0x1800043b8  jz      loc_18000445C
0x1800043be  mov     rdx, [rsp+78h+var_40]; void *
0x1800043c3  mov     r9, rdx; void *
0x1800043c6  mov     r8, r13; unsigned __int64
0x1800043c9  mov     rcx, r15; this
0x1800043cc  call    ?memcpy_s@Checked@ATL@@YAXPEAX_KPEBX1@Z; ATL::Checked::memcpy_s(void *,unsigned __int64,void const *,unsigned __int64)
0x1800043d1  mov     r9, [rsp+78h+var_50]; void *
0x1800043d6  mov     r8, r12; unsigned __int64
0x1800043d9  mov     rdx, r9; void *
0x1800043dc  mov     rcx, rbx; this
0x1800043df  call    ?memcpy_s@Checked@ATL@@YAXPEAX_KPEBX1@Z; ATL::Checked::memcpy_s(void *,unsigned __int64,void const *,unsigned __int64)
0x1800043e4  mov     eax, [r14+10h]
0x1800043e8  mov     r12d, 1
0x1800043ee  add     eax, r12d
0x1800043f1  movsxd  rdx, eax
0x1800043f4  lea     r13d, [r12+7]
0x1800043f9  mov     r8d, r13d
0x1800043fc  mov     rcx, [r14]
0x1800043ff  call    cs:__imp__o__recalloc
0x180004405  test    rax, rax
0x180004408  jz      short loc_18000445C
0x18000440a  mov     [r14], rax
0x18000440d  mov     eax, [r14+10h]
0x180004411  add     eax, r12d
0x180004414  movsxd  rdx, eax
0x180004417  mov     r8d, r13d
0x18000441a  mov     rcx, [r14+8]
0x18000441e  call    cs:__imp__o__recalloc
0x180004424  test    rax, rax
0x180004427  jz      short loc_18000445C
0x180004429  mov     [r14+8], rax
0x18000442d  movsxd  rdx, dword ptr [r14+10h]
0x180004431  mov     rax, [r14]
0x180004434  lea     rcx, [rax+rdx*8]
0x180004438  test    rcx, rcx
0x18000443b  jz      short loc_180004440
0x18000443d  mov     [rcx], r15
0x180004440  mov     rax, [r14+8]
0x180004444  lea     rcx, [rax+rdx*8]
0x180004448  test    rcx, rcx
0x18000444b  jz      short loc_180004450
0x18000444d  mov     [rcx], rbx
0x180004450  add     [r14+10h], r12d
0x180004454  mov     rdi, rsi
0x180004457  mov     rbx, rsi
0x18000445a  jmp     short loc_18000445F
0x18000445c  mov     r12d, esi
0x18000445f  mov     rcx, rbx; Block
0x180004462  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004467  nop
0x180004468  mov     rcx, rdi; Block
0x18000446b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004470  mov     eax, r12d
0x180004473  jmp     short loc_180004477
0x180004475  xor     eax, eax
0x180004477  add     rsp, 40h
0x18000447b  pop     r15
0x18000447d  pop     r14
0x18000447f  pop     r13
0x180004481  pop     r12
0x180004483  pop     rdi
0x180004484  pop     rsi
0x180004485  pop     rbx
0x180004486  retn
```
