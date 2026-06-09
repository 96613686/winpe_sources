# ATL::CExpansionVector::Add(ushort const *,ushort const *)

- ea: `0x18001f0bc`
- end: `0x18001f2b7`
- name: `?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z`
- size: `507`
- prototype: `int(ATL::CExpansionVector *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18001f430`
- `0x180021f9c`
- `0x1800222c4`

## callees

- `0x180001434`
- `0x180001440`
- `0x18001f0bc`
- `0x180022644`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x18001f22f`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x18001f24e`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x18001f22f`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x18001f24e`

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
0x18001f0bc  mov     [rsp+arg_10], r8
0x18001f0c1  mov     [rsp+arg_8], rdx
0x18001f0c6  mov     [rsp+arg_0], rcx
0x18001f0cb  push    rbx
0x18001f0cc  push    rsi
0x18001f0cd  push    rdi
0x18001f0ce  push    r12
0x18001f0d0  push    r13
0x18001f0d2  push    r14
0x18001f0d4  push    r15
0x18001f0d6  sub     rsp, 40h
0x18001f0da  mov     r12, r8
0x18001f0dd  mov     r13, rdx
0x18001f0e0  mov     r14, rcx
0x18001f0e3  xor     esi, esi
0x18001f0e5  test    rdx, rdx
0x18001f0e8  jz      loc_18001F2A5
0x18001f0ee  test    r8, r8
0x18001f0f1  jz      loc_18001F2A5
0x18001f0f7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001f0fb  mov     rax, rbx
0x18001f0fe  inc     rax
0x18001f101  cmp     [rdx+rax*2], si
0x18001f105  jnz     short loc_18001F0FE
0x18001f107  lea     rcx, ds:2[rax*2]
0x18001f10f  mov     [rsp+78h+var_40], rcx
0x18001f114  mov     [rsp+78h+arg_18], rsi
0x18001f11c  mov     eax, 2
0x18001f121  mul     rcx
0x18001f124  cmovb   rax, rbx
0x18001f128  mov     rcx, rax; unsigned __int64
0x18001f12b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001f130  mov     r15, rax
0x18001f133  mov     [rsp+78h+arg_18], rax
0x18001f13b  jmp     short loc_18001F163
0x18001f13d  xor     esi, esi
0x18001f13f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001f143  mov     r14, [rsp+78h+arg_0]
0x18001f14b  mov     r12, [rsp+78h+arg_10]
0x18001f153  mov     r13, [rsp+78h+arg_8]
0x18001f15b  mov     r15, [rsp+78h+arg_18]
0x18001f163  mov     rdi, r15
0x18001f166  mov     [rsp+78h+var_48], r15
0x18001f16b  mov     rcx, rbx
0x18001f16e  inc     rcx
0x18001f171  cmp     [r12+rcx*2], si
0x18001f176  jnz     short loc_18001F16E
0x18001f178  inc     ecx
0x18001f17a  movsxd  rcx, ecx
0x18001f17d  add     rcx, rcx
0x18001f180  mov     [rsp+78h+var_50], rcx
0x18001f185  mov     [rsp+78h+var_58], rsi
0x18001f18a  mov     eax, 2
0x18001f18f  mul     rcx
0x18001f192  cmovb   rax, rbx
0x18001f196  mov     rcx, rax; unsigned __int64
0x18001f199  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001f19e  mov     rbx, rax
0x18001f1a1  mov     [rsp+78h+var_58], rax
0x18001f1a6  jmp     short loc_18001F1D4
0x18001f1a8  xor     esi, esi
0x18001f1aa  mov     r14, [rsp+78h+arg_0]
0x18001f1b2  mov     r12, [rsp+78h+arg_10]
0x18001f1ba  mov     r13, [rsp+78h+arg_8]
0x18001f1c2  mov     r15, [rsp+78h+arg_18]
0x18001f1ca  mov     rdi, [rsp+78h+var_48]
0x18001f1cf  mov     rbx, [rsp+78h+var_58]
0x18001f1d4  mov     [rsp+78h+arg_8], rbx
0x18001f1dc  test    r15, r15
0x18001f1df  jz      loc_18001F28C
0x18001f1e5  test    rbx, rbx
0x18001f1e8  jz      loc_18001F28C
0x18001f1ee  mov     rdx, [rsp+78h+var_40]; void *
0x18001f1f3  mov     r9, rdx; void *
0x18001f1f6  mov     r8, r13; unsigned __int64
0x18001f1f9  mov     rcx, r15; this
0x18001f1fc  call    ?memcpy_s@Checked@ATL@@YAXPEAX_KPEBX1@Z; ATL::Checked::memcpy_s(void *,unsigned __int64,void const *,unsigned __int64)
0x18001f201  mov     r9, [rsp+78h+var_50]; void *
0x18001f206  mov     r8, r12; unsigned __int64
0x18001f209  mov     rdx, r9; void *
0x18001f20c  mov     rcx, rbx; this
0x18001f20f  call    ?memcpy_s@Checked@ATL@@YAXPEAX_KPEBX1@Z; ATL::Checked::memcpy_s(void *,unsigned __int64,void const *,unsigned __int64)
0x18001f214  mov     eax, [r14+10h]
0x18001f218  mov     r12d, 1
0x18001f21e  add     eax, r12d
0x18001f221  movsxd  rdx, eax
0x18001f224  lea     r13d, [r12+7]
0x18001f229  mov     r8d, r13d
0x18001f22c  mov     rcx, [r14]
0x18001f22f  call    cs:__imp__o__recalloc
0x18001f235  test    rax, rax
0x18001f238  jz      short loc_18001F28C
0x18001f23a  mov     [r14], rax
0x18001f23d  mov     eax, [r14+10h]
0x18001f241  add     eax, r12d
0x18001f244  movsxd  rdx, eax
0x18001f247  mov     r8d, r13d
0x18001f24a  mov     rcx, [r14+8]
0x18001f24e  call    cs:__imp__o__recalloc
0x18001f254  test    rax, rax
0x18001f257  jz      short loc_18001F28C
0x18001f259  mov     [r14+8], rax
0x18001f25d  movsxd  rdx, dword ptr [r14+10h]
0x18001f261  mov     rax, [r14]
0x18001f264  lea     rcx, [rax+rdx*8]
0x18001f268  test    rcx, rcx
0x18001f26b  jz      short loc_18001F270
0x18001f26d  mov     [rcx], r15
0x18001f270  mov     rax, [r14+8]
0x18001f274  lea     rcx, [rax+rdx*8]
0x18001f278  test    rcx, rcx
0x18001f27b  jz      short loc_18001F280
0x18001f27d  mov     [rcx], rbx
0x18001f280  add     [r14+10h], r12d
0x18001f284  mov     rdi, rsi
0x18001f287  mov     rbx, rsi
0x18001f28a  jmp     short loc_18001F28F
0x18001f28c  mov     r12d, esi
0x18001f28f  mov     rcx, rbx; Block
0x18001f292  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001f297  nop
0x18001f298  mov     rcx, rdi; Block
0x18001f29b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001f2a0  mov     eax, r12d
0x18001f2a3  jmp     short loc_18001F2A7
0x18001f2a5  xor     eax, eax
0x18001f2a7  add     rsp, 40h
0x18001f2ab  pop     r15
0x18001f2ad  pop     r14
0x18001f2af  pop     r13
0x18001f2b1  pop     r12
0x18001f2b3  pop     rdi
0x18001f2b4  pop     rsi
0x18001f2b5  pop     rbx
0x18001f2b6  retn
```
