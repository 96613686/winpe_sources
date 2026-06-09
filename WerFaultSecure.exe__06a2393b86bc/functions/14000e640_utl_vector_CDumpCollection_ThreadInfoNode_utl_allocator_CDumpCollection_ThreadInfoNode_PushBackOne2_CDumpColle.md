# utl::vector<CDumpCollection::ThreadInfoNode,utl::allocator<CDumpCollection::ThreadInfoNode>>::_PushBackOne2<CDumpCollection::ThreadInfoNode>(CDumpCollection::ThreadInfoNode &&)

- ea: `0x14000e640`
- end: `0x14000e74a`
- name: `??$_PushBackOne2@UThreadInfoNode@CDumpCollection@@@?$vector@UThreadInfoNode@CDumpCollection@@V?$allocator@UThreadInfoNode@CDumpCollection@@@utl@@@utl@@AEAA_N$$QEAUThreadInfoNode@CDumpCollection@@@Z`
- size: `266`
- prototype: `char __fastcall(__int64, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14000fb3c`

## callees

- `0x1400023f4`
- `0x140002440`
- `0x14000e640`
- `0x14001130c`

## pseudocode

```c
char __fastcall utl::vector<CDumpCollection::ThreadInfoNode,utl::allocator<CDumpCollection::ThreadInfoNode>>::_PushBackOne2<CDumpCollection::ThreadInfoNode>(
        __int64 a1,
        char *a2)
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
  v6 = (v4 - *(_QWORD *)a1) >> 2;
  v7 = 7 * (v6 >> 2) + 8;
  if ( v7 > 0x1FFFFFFFFFFFFFFFLL )
    v7 = 0x1FFFFFFFFFFFFFFFLL;
  if ( v6 >= v7 )
    return 0;
  v8 = 4 * v7;
  v9 = (char *)operator new(4 * v7, (const struct std::nothrow_t *)&std::nothrow);
  v10 = v9;
  if ( (unsigned __int64)(v9 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    return 0;
  v11 = a2 - v5;
  v12 = &v9[v8];
  memcpy_0(v9, *(const void **)a1, (*(_QWORD *)(a1 + 8) - *(_QWORD *)a1) & 0xFFFFFFFFFFFFFFFCuLL);
  v13 = *(void **)a1;
  v14 = &v10[4 * ((__int64)(*(_QWORD *)(a1 + 8) - *(_QWORD *)a1) >> 2)];
  if ( *(_QWORD *)a1 != -1 )
  {
    *(_QWORD *)(a1 + 8) = v13;
    operator delete(v13, (const struct std::nothrow_t *)&std::nothrow);
  }
  *(_QWORD *)a1 = v10;
  *(_QWORD *)(a1 + 8) = v14;
  *(_QWORD *)(a1 + 16) = v12;
  if ( v11 < v14 - v10 )
    a2 = &v10[v11];
  *(_DWORD *)v14 = *(_DWORD *)a2;
  result = 1;
  *(_QWORD *)(a1 + 8) += 4LL;
  return result;
}

```

## disassembly

```asm
0x14000e640  push    rbx
0x14000e642  push    rbp
0x14000e643  push    rsi
0x14000e644  push    rdi
0x14000e645  push    r14
0x14000e647  push    r15
0x14000e649  sub     rsp, 28h
0x14000e64d  mov     rbx, rcx
0x14000e650  mov     rsi, rdx
0x14000e653  mov     rcx, [rcx+10h]
0x14000e657  cmp     [rbx+8], rcx
0x14000e65b  jnz     loc_14000E73B
0x14000e661  mov     rbp, [rbx]
0x14000e664  mov     rdx, 1FFFFFFFFFFFFFFFh
0x14000e66e  sub     rcx, rbp
0x14000e671  sar     rcx, 2
0x14000e675  mov     rax, rcx
0x14000e678  shr     rax, 2
0x14000e67c  imul    rax, 7
0x14000e680  add     rax, 8
0x14000e684  cmp     rax, rdx
0x14000e687  cmova   rax, rdx
0x14000e68b  cmp     rcx, rax
0x14000e68e  jnb     loc_14000E73B
0x14000e694  mov     rcx, 3FFFFFFFFFFFFFFFh
0x14000e69e  cmp     rax, rcx
0x14000e6a1  ja      loc_14000E73B
0x14000e6a7  lea     r15, ds:0[rax*4]
0x14000e6af  mov     rcx, r15; unsigned __int64
0x14000e6b2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000e6b9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000e6be  mov     rdi, rax
0x14000e6c1  lea     rcx, [rax-1]
0x14000e6c5  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x14000e6c9  ja      short loc_14000E73B
0x14000e6cb  mov     r8, [rbx+8]
0x14000e6cf  mov     r14, rsi
0x14000e6d2  sub     r8, [rbx]
0x14000e6d5  sub     r14, rbp
0x14000e6d8  mov     rdx, [rbx]; Src
0x14000e6db  lea     rbp, [r15+rax]
0x14000e6df  and     r8, 0FFFFFFFFFFFFFFFCh; Size
0x14000e6e3  mov     rcx, rax; void *
0x14000e6e6  call    memcpy_0
0x14000e6eb  mov     rcx, [rbx]; void *
0x14000e6ee  mov     rax, [rbx+8]
0x14000e6f2  sub     rax, rcx
0x14000e6f5  sar     rax, 2
0x14000e6f9  lea     r15, [rdi+rax*4]
0x14000e6fd  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14000e701  jz      short loc_14000E713
0x14000e703  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000e70a  mov     [rbx+8], rcx
0x14000e70e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000e713  mov     rax, r15
0x14000e716  mov     [rbx], rdi
0x14000e719  sub     rax, rdi
0x14000e71c  mov     [rbx+8], r15
0x14000e720  mov     [rbx+10h], rbp
0x14000e724  cmp     r14, rax
0x14000e727  jnb     short loc_14000E72D
0x14000e729  lea     rsi, [r14+rdi]
0x14000e72d  mov     eax, [rsi]
0x14000e72f  mov     [r15], eax
0x14000e732  mov     al, 1
0x14000e734  add     qword ptr [rbx+8], 4
0x14000e739  jmp     short loc_14000E73D
0x14000e73b  xor     al, al
0x14000e73d  add     rsp, 28h
0x14000e741  pop     r15
0x14000e743  pop     r14
0x14000e745  pop     rdi
0x14000e746  pop     rsi
0x14000e747  pop     rbp
0x14000e748  pop     rbx
0x14000e749  retn
```
