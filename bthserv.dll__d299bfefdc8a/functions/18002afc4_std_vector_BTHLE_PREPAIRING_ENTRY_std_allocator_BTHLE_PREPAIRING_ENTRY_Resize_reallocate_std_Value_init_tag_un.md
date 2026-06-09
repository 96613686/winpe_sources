# std::vector<BTHLE_PREPAIRING_ENTRY,std::allocator<BTHLE_PREPAIRING_ENTRY>>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)

- ea: `0x18002afc4`
- end: `0x18002b131`
- name: `??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UBTHLE_PREPAIRING_ENTRY@@V?$allocator@UBTHLE_PREPAIRING_ENTRY@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z`
- size: `365`
- prototype: `char *__fastcall(__int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x18002b154`

## callees

- `0x180001b60`
- `0x180001b9c`
- `0x1800024ac`
- `0x180010d08`
- `0x180016748`
- `0x18002afc4`
- `0x180032c5c`

## pseudocode

```c
char *__fastcall std::vector<BTHLE_PREPAIRING_ENTRY>::_Resize_reallocate<std::_Value_init_tag>(
        __int64 a1,
        unsigned __int64 a2)
{
  const void *v4; // r14
  unsigned __int64 v5; // rcx
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // rax
  __int64 v8; // r15
  unsigned __int64 v9; // rsi
  _QWORD *v10; // rdi
  void *v11; // rax
  unsigned __int64 v12; // r15
  unsigned __int64 v13; // r14
  char *v14; // rcx
  const struct std::nothrow_t *v15; // rdx
  void *v16; // rax
  char *result; // rax

  if ( a2 > 0xA3D70A3D70A3D70LL )
    std::vector<BTHLE_PREPAIRING_ENTRY>::_Xlength();
  v4 = *(const void **)a1;
  v5 = 0x8F5C28F5C28F5C29uLL * (*(_QWORD *)(a1 + 16) - *(_QWORD *)a1);
  v6 = v5 >> 1;
  if ( v5 > 0xA3D70A3D70A3D70LL - (v5 >> 1) )
    goto LABEL_25;
  v7 = v5 + v6;
  if ( v5 + v6 >= a2 )
  {
    if ( v7 > 0xA3D70A3D70A3D70LL )
      goto LABEL_25;
  }
  else
  {
    v7 = a2;
  }
  v8 = *(_QWORD *)(a1 + 8);
  v9 = 25 * v7;
  if ( !(25 * v7) )
  {
    v10 = 0;
    goto LABEL_13;
  }
  if ( v9 < 0x1000 )
  {
    v10 = operator new(25 * v7);
    goto LABEL_13;
  }
  if ( v9 + 39 < v9 )
LABEL_25:
    __scrt_throw_std_bad_array_new_length();
  v11 = operator new(v9 + 39);
  if ( !v11 )
    goto LABEL_20;
  v10 = (_QWORD *)(((unsigned __int64)v11 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v10 - 1) = v11;
LABEL_13:
  v12 = 0x8F5C28F5C28F5C29uLL * (v8 - (_QWORD)v4);
  v13 = a2 - v12;
  if ( a2 != v12 )
  {
    LOBYTE(v6) = 0;
    memset_0((char *)v10 + 25 * v12, v6, 25 * v13);
    do
      --v13;
    while ( v13 );
  }
  memmove_0(v10, *(const void **)a1, *(_QWORD *)(a1 + 8) - *(_QWORD *)a1);
  v14 = *(char **)a1;
  if ( *(_QWORD *)a1 )
  {
    v15 = (const struct std::nothrow_t *)(*(_QWORD *)(a1 + 16) - (_QWORD)v14);
    if ( (unsigned __int64)v15 < 0x1000 )
    {
      v16 = *(void **)a1;
      goto LABEL_22;
    }
    v16 = (void *)*((_QWORD *)v14 - 1);
    if ( (unsigned __int64)(v14 - (_BYTE *)v16 - 8) <= 0x1F )
    {
      v15 = (const struct std::nothrow_t *)((char *)v15 + 39);
LABEL_22:
      operator delete(v16, v15);
      goto LABEL_23;
    }
LABEL_20:
    __fastfail(5u);
  }
LABEL_23:
  *(_QWORD *)a1 = v10;
  *(_QWORD *)(a1 + 8) = (char *)v10 + 25 * a2;
  result = (char *)v10 + v9;
  *(_QWORD *)(a1 + 16) = (char *)v10 + v9;
  return result;
}

```

## disassembly

```asm
0x18002afc4  push    rbx
0x18002afc6  push    rbp
0x18002afc7  push    rsi
0x18002afc8  push    rdi
0x18002afc9  push    r13
0x18002afcb  push    r14
0x18002afcd  push    r15
0x18002afcf  sub     rsp, 20h
0x18002afd3  mov     r8, 0A3D70A3D70A3D70h
0x18002afdd  mov     rbp, rdx
0x18002afe0  mov     rbx, rcx
0x18002afe3  cmp     rdx, r8
0x18002afe6  ja      loc_18002B125
0x18002afec  mov     r14, [rcx]
0x18002afef  mov     r13, 8F5C28F5C28F5C29h
0x18002aff9  mov     rcx, [rcx+10h]
0x18002affd  mov     rax, r8
0x18002b000  sub     rcx, r14
0x18002b003  imul    rcx, r13
0x18002b007  mov     rdx, rcx
0x18002b00a  shr     rdx, 1
0x18002b00d  sub     rax, rdx
0x18002b010  cmp     rcx, rax
0x18002b013  ja      loc_18002B12B
0x18002b019  lea     rax, [rcx+rdx]
0x18002b01d  cmp     rax, rbp
0x18002b020  jnb     short loc_18002B027
0x18002b022  mov     rax, rbp
0x18002b025  jmp     short loc_18002B030
0x18002b027  cmp     rax, r8
0x18002b02a  ja      loc_18002B12B
0x18002b030  mov     r15, [rbx+8]
0x18002b034  imul    rsi, rax, 19h
0x18002b038  test    rsi, rsi
0x18002b03b  jnz     short loc_18002B041
0x18002b03d  xor     edi, edi
0x18002b03f  jmp     short loc_18002B07E
0x18002b041  cmp     rsi, 1000h
0x18002b048  jb      short loc_18002B073
0x18002b04a  lea     rcx, [rsi+27h]; Size
0x18002b04e  cmp     rcx, rsi
0x18002b051  jbe     loc_18002B12B
0x18002b057  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002b05c  test    rax, rax
0x18002b05f  jz      loc_18002B0EE
0x18002b065  lea     rdi, [rax+27h]
0x18002b069  and     rdi, 0FFFFFFFFFFFFFFE0h
0x18002b06d  mov     [rdi-8], rax
0x18002b071  jmp     short loc_18002B07E
0x18002b073  mov     rcx, rsi; Size
0x18002b076  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002b07b  mov     rdi, rax
0x18002b07e  sub     r15, r14
0x18002b081  mov     r14, rbp
0x18002b084  imul    r15, r13
0x18002b088  imul    rcx, r15, 19h
0x18002b08c  add     rcx, rdi; void *
0x18002b08f  sub     r14, r15
0x18002b092  jz      short loc_18002B0A5
0x18002b094  imul    r8, r14, 19h; Size
0x18002b098  xor     dl, dl; Val
0x18002b09a  call    memset_0
0x18002b09f  sub     r14, 1
0x18002b0a3  jnz     short loc_18002B09F
0x18002b0a5  mov     r8, [rbx+8]
0x18002b0a9  mov     rcx, rdi; void *
0x18002b0ac  sub     r8, [rbx]; Size
0x18002b0af  mov     rdx, [rbx]; Src
0x18002b0b2  call    memmove_0
0x18002b0b7  mov     rcx, [rbx]
0x18002b0ba  test    rcx, rcx
0x18002b0bd  jz      short loc_18002B100
0x18002b0bf  mov     rax, [rbx+10h]
0x18002b0c3  sub     rax, rcx
0x18002b0c6  imul    rax, r13
0x18002b0ca  imul    rdx, rax, 19h; struct std::nothrow_t *
0x18002b0ce  cmp     rdx, 1000h
0x18002b0d5  jb      short loc_18002B0F5
0x18002b0d7  mov     rax, [rcx-8]
0x18002b0db  sub     rcx, rax
0x18002b0de  sub     rcx, 8
0x18002b0e2  cmp     rcx, 1Fh
0x18002b0e6  ja      short loc_18002B0EE
0x18002b0e8  add     rdx, 27h ; '''
0x18002b0ec  jmp     short loc_18002B0F8
0x18002b0ee  mov     ecx, 5
0x18002b0f3  int     29h; Win8: RtlFailFast(ecx)
0x18002b0f5  mov     rax, rcx
0x18002b0f8  mov     rcx, rax; void *
0x18002b0fb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002b100  mov     [rbx], rdi
0x18002b103  imul    rax, rbp, 19h
0x18002b107  add     rax, rdi
0x18002b10a  mov     [rbx+8], rax
0x18002b10e  lea     rax, [rsi+rdi]
0x18002b112  mov     [rbx+10h], rax
0x18002b116  add     rsp, 20h
0x18002b11a  pop     r15
0x18002b11c  pop     r14
0x18002b11e  pop     r13
0x18002b120  pop     rdi
0x18002b121  pop     rsi
0x18002b122  pop     rbp
0x18002b123  pop     rbx
0x18002b124  retn
0x18002b125  call    ?_Xlength@?$vector@UBTHLE_PREPAIRING_ENTRY@@V?$allocator@UBTHLE_PREPAIRING_ENTRY@@@std@@@std@@CAXXZ; std::vector<BTHLE_PREPAIRING_ENTRY>::_Xlength(void)
0x18002b12b  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
