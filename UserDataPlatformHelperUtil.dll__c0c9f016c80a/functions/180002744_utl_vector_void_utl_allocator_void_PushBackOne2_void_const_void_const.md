# utl::vector<void *,utl::allocator<void *>>::_PushBackOne2<void * const &>(void * const &)

- ea: `0x180002744`
- end: `0x18000284f`
- name: `??$_PushBackOne2@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@utl@@@utl@@AEAA_NAEBQEAX@Z`
- size: `267`
- prototype: `char __fastcall(__int64, char *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180002a20`
- `0x180002f70`
- `0x180003050`

## callees

- `0x180001178`
- `0x1800016e8`
- `0x180002744`
- `0x18000a142`

## pseudocode

```c
char __fastcall utl::vector<void *,utl::allocator<void *>>::_PushBackOne2<void * const &>(__int64 a1, char *a2)
{
  __int64 v4; // rcx
  _BYTE *v5; // rbp
  unsigned __int64 v6; // rcx
  unsigned __int64 v7; // rax
  __int64 v8; // r15
  char *v9; // rax
  char *v10; // rdi
  unsigned __int64 v11; // r14
  char *v12; // rbp
  void *v13; // rcx
  char *v14; // r15
  char result; // al

  v4 = *(_QWORD *)(a1 + 16);
  if ( *(_QWORD *)(a1 + 8) != v4 )
    return 0;
  v5 = *(_BYTE **)a1;
  v6 = (v4 - *(_QWORD *)a1) >> 3;
  v7 = 7 * (v6 >> 2) + 8;
  if ( v7 > 0xFFFFFFFFFFFFFFFLL )
    v7 = 0xFFFFFFFFFFFFFFFLL;
  if ( v6 >= v7 )
    return 0;
  v8 = 8 * v7;
  v9 = (char *)operator new(8 * v7, (const struct std::nothrow_t *)&std::nothrow);
  v10 = v9;
  if ( (unsigned __int64)(v9 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    return 0;
  v11 = a2 - v5;
  v12 = &v9[v8];
  memcpy_0(v9, *(const void **)a1, (*(_QWORD *)(a1 + 8) - *(_QWORD *)a1) & 0xFFFFFFFFFFFFFFF8uLL);
  v13 = *(void **)a1;
  v14 = &v10[8 * ((__int64)(*(_QWORD *)(a1 + 8) - *(_QWORD *)a1) >> 3)];
  if ( *(_QWORD *)a1 != -1 )
  {
    *(_QWORD *)(a1 + 8) = v13;
    operator delete(v13);
  }
  *(_QWORD *)a1 = v10;
  *(_QWORD *)(a1 + 8) = v14;
  *(_QWORD *)(a1 + 16) = v12;
  if ( v11 < v14 - v10 )
    a2 = &v10[v11];
  *(_QWORD *)v14 = *(_QWORD *)a2;
  result = 1;
  *(_QWORD *)(a1 + 8) += 8LL;
  return result;
}

```

## disassembly

```asm
0x180002744  push    rbx
0x180002746  push    rbp
0x180002747  push    rsi
0x180002748  push    rdi
0x180002749  push    r14
0x18000274b  push    r15
0x18000274d  sub     rsp, 28h
0x180002751  mov     rbx, rcx
0x180002754  mov     rsi, rdx
0x180002757  mov     rcx, [rcx+10h]
0x18000275b  cmp     [rbx+8], rcx
0x18000275f  jnz     loc_180002840
0x180002765  mov     rbp, [rbx]
0x180002768  mov     rdx, 0FFFFFFFFFFFFFFFh
0x180002772  sub     rcx, rbp
0x180002775  sar     rcx, 3
0x180002779  mov     rax, rcx
0x18000277c  shr     rax, 2
0x180002780  imul    rax, 7
0x180002784  add     rax, 8
0x180002788  cmp     rax, rdx
0x18000278b  cmova   rax, rdx
0x18000278f  cmp     rcx, rax
0x180002792  jnb     loc_180002840
0x180002798  mov     rcx, 1FFFFFFFFFFFFFFFh
0x1800027a2  cmp     rax, rcx
0x1800027a5  ja      loc_180002840
0x1800027ab  lea     r15, ds:0[rax*8]
0x1800027b3  mov     rcx, r15; unsigned __int64
0x1800027b6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800027bd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800027c2  mov     rdi, rax
0x1800027c5  lea     rcx, [rax-1]
0x1800027c9  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800027cd  ja      short loc_180002840
0x1800027cf  mov     r8, [rbx+8]
0x1800027d3  mov     r14, rsi
0x1800027d6  sub     r8, [rbx]
0x1800027d9  sub     r14, rbp
0x1800027dc  mov     rdx, [rbx]; Src
0x1800027df  lea     rbp, [r15+rax]
0x1800027e3  and     r8, 0FFFFFFFFFFFFFFF8h; Size
0x1800027e7  mov     rcx, rax; void *
0x1800027ea  call    memcpy_0
0x1800027ef  mov     rcx, [rbx]; Block
0x1800027f2  mov     rax, [rbx+8]
0x1800027f6  sub     rax, rcx
0x1800027f9  sar     rax, 3
0x1800027fd  lea     r15, [rdi+rax*8]
0x180002801  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180002805  jz      short loc_180002817
0x180002807  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18000280e  mov     [rbx+8], rcx
0x180002812  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180002817  mov     rax, r15
0x18000281a  mov     [rbx], rdi
0x18000281d  sub     rax, rdi
0x180002820  mov     [rbx+8], r15
0x180002824  mov     [rbx+10h], rbp
0x180002828  cmp     r14, rax
0x18000282b  jnb     short loc_180002831
0x18000282d  lea     rsi, [r14+rdi]
0x180002831  mov     rax, [rsi]
0x180002834  mov     [r15], rax
0x180002837  mov     al, 1
0x180002839  add     qword ptr [rbx+8], 8
0x18000283e  jmp     short loc_180002842
0x180002840  xor     al, al
0x180002842  add     rsp, 28h
0x180002846  pop     r15
0x180002848  pop     r14
0x18000284a  pop     rdi
0x18000284b  pop     rsi
0x18000284c  pop     rbp
0x18000284d  pop     rbx
0x18000284e  retn
```
