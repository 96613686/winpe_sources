# std::vector<FeatureDescriptor *,std::allocator<FeatureDescriptor *>>::_Emplace_reallocate<FeatureDescriptor *>(FeatureDescriptor * * const,FeatureDescriptor * &&)

- ea: `0x18002621c`
- end: `0x1800263ae`
- name: `??$_Emplace_reallocate@PEAUFeatureDescriptor@@@?$vector@PEAUFeatureDescriptor@@V?$allocator@PEAUFeatureDescriptor@@@std@@@std@@AEAAPEAPEAUFeatureDescriptor@@QEAPEAU2@$$QEAPEAU2@@Z`
- size: `402`
- prototype: `_QWORD *__fastcall(_QWORD *, _BYTE *, _QWORD *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800269c0`
- `0x180026f3c`

## callees

- `0x180003544`
- `0x180003a34`
- `0x18000410c`
- `0x18000a81c`
- `0x18000a85c`
- `0x18002621c`

## pseudocode

```c
_QWORD *__fastcall std::vector<FeatureDescriptor *>::_Emplace_reallocate<FeatureDescriptor *>(
        _QWORD *a1,
        _BYTE *a2,
        _QWORD *a3)
{
  _BYTE *v3; // r14
  __int64 v6; // rdx
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // r8
  __int64 v10; // r15
  unsigned __int64 v11; // rsi
  size_t v12; // rsi
  _QWORD *v13; // rbx
  void *v14; // rax
  _QWORD *v15; // r14
  void *v16; // rcx
  _BYTE *v17; // r8
  _BYTE *v18; // rdx
  size_t v19; // r8
  _BYTE *v20; // rcx
  _BYTE *v21; // rax
  _QWORD *result; // rax

  v3 = (_BYTE *)*a1;
  v6 = (__int64)(a1[1] - *a1) >> 3;
  if ( v6 == 0x1FFFFFFFFFFFFFFFLL )
    std::vector<Windows::AutoNewPtr<FeatureDescriptor>>::_Xlength();
  v8 = (__int64)(a1[2] - (_QWORD)v3) >> 3;
  v9 = v8 >> 1;
  if ( v8 > 0x1FFFFFFFFFFFFFFFLL - (v8 >> 1) )
    goto LABEL_24;
  v10 = v6 + 1;
  v11 = v6 + 1;
  if ( v8 + v9 >= v6 + 1 )
    v11 = v8 + v9;
  if ( v11 > 0x1FFFFFFFFFFFFFFFLL )
    goto LABEL_24;
  v12 = 8 * v11;
  if ( !v12 )
  {
    v13 = 0;
    goto LABEL_13;
  }
  if ( v12 < 0x1000 )
  {
    v13 = operator new(v12);
    goto LABEL_13;
  }
  if ( v12 + 39 < v12 )
LABEL_24:
    __scrt_throw_std_bad_array_new_length();
  v14 = operator new(v12 + 39);
  if ( !v14 )
    goto LABEL_19;
  v13 = (_QWORD *)(((unsigned __int64)v14 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v13 - 1) = v14;
LABEL_13:
  v15 = &v13[(a2 - v3) >> 3];
  *v15 = *a3;
  v16 = v13;
  v17 = (_BYTE *)a1[1];
  v18 = (_BYTE *)*a1;
  if ( a2 == v17 )
  {
    v19 = v17 - v18;
  }
  else
  {
    memmove_0(v13, v18, (size_t)&a2[-*a1]);
    v16 = v15 + 1;
    v19 = a1[1] - (_QWORD)a2;
    v18 = a2;
  }
  memmove_0(v16, v18, v19);
  v20 = (_BYTE *)*a1;
  if ( *a1 )
  {
    if ( (unsigned __int64)(8 * ((__int64)(a1[2] - (_QWORD)v20) >> 3)) < 0x1000 )
    {
      v21 = (_BYTE *)*a1;
    }
    else
    {
      v21 = (_BYTE *)*((_QWORD *)v20 - 1);
      if ( (unsigned __int64)(v20 - v21 - 8) > 0x1F )
LABEL_19:
        __fastfail(5u);
    }
    operator delete(v21);
  }
  *a1 = v13;
  result = v15;
  a1[1] = &v13[v10];
  a1[2] = &v13[v12 / 8];
  return result;
}

```

## disassembly

```asm
0x18002621c  mov     [rsp+arg_10], rbx
0x180026221  mov     [rsp+arg_18], rbp
0x180026226  push    rsi
0x180026227  push    rdi
0x180026228  push    r12
0x18002622a  push    r14
0x18002622c  push    r15
0x18002622e  sub     rsp, 20h
0x180026232  mov     r14, [rcx]
0x180026235  mov     rbp, rdx
0x180026238  mov     rdx, [rcx+8]
0x18002623c  mov     r9, 1FFFFFFFFFFFFFFFh
0x180026246  sub     rdx, r14
0x180026249  mov     r12, r8
0x18002624c  sar     rdx, 3
0x180026250  mov     rdi, rcx
0x180026253  cmp     rdx, r9
0x180026256  jz      loc_1800263A2
0x18002625c  mov     rcx, [rcx+10h]
0x180026260  mov     rax, r9
0x180026263  sub     rcx, r14
0x180026266  sar     rcx, 3
0x18002626a  mov     r8, rcx
0x18002626d  shr     r8, 1
0x180026270  sub     rax, r8
0x180026273  cmp     rcx, rax
0x180026276  ja      loc_1800263A8
0x18002627c  lea     r15, [rdx+1]
0x180026280  lea     rax, [rcx+r8]
0x180026284  mov     rsi, r15
0x180026287  cmp     rax, r15
0x18002628a  cmovnb  rsi, rax
0x18002628e  cmp     rsi, r9
0x180026291  ja      loc_1800263A8
0x180026297  shl     rsi, 3
0x18002629b  test    rsi, rsi
0x18002629e  jnz     short loc_1800262A4
0x1800262a0  xor     ebx, ebx
0x1800262a2  jmp     short loc_1800262E1
0x1800262a4  cmp     rsi, 1000h
0x1800262ab  jb      short loc_1800262D6
0x1800262ad  lea     rcx, [rsi+27h]; Size
0x1800262b1  cmp     rcx, rsi
0x1800262b4  jbe     loc_1800263A8
0x1800262ba  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800262bf  test    rax, rax
0x1800262c2  jz      loc_180026363
0x1800262c8  lea     rbx, [rax+27h]
0x1800262cc  and     rbx, 0FFFFFFFFFFFFFFE0h
0x1800262d0  mov     [rbx-8], rax
0x1800262d4  jmp     short loc_1800262E1
0x1800262d6  mov     rcx, rsi; Size
0x1800262d9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800262de  mov     rbx, rax
0x1800262e1  mov     rcx, rbp
0x1800262e4  sub     rcx, r14
0x1800262e7  sar     rcx, 3
0x1800262eb  lea     r14, [rbx+rcx*8]
0x1800262ef  mov     rcx, [r12]
0x1800262f3  mov     [r14], rcx
0x1800262f6  mov     rcx, rbx; void *
0x1800262f9  mov     r8, [rdi+8]
0x1800262fd  mov     rdx, [rdi]; Src
0x180026300  cmp     rbp, r8
0x180026303  jnz     short loc_18002630A
0x180026305  sub     r8, rdx
0x180026308  jmp     short loc_180026323
0x18002630a  mov     r8, rbp
0x18002630d  sub     r8, [rdi]; Size
0x180026310  call    memmove_0
0x180026315  mov     r8, [rdi+8]
0x180026319  lea     rcx, [r14+8]; void *
0x18002631d  sub     r8, rbp; Size
0x180026320  mov     rdx, rbp; Src
0x180026323  call    memmove_0
0x180026328  mov     rcx, [rdi]
0x18002632b  test    rcx, rcx
0x18002632e  jz      short loc_180026375
0x180026330  mov     rax, [rdi+10h]
0x180026334  sub     rax, rcx
0x180026337  sar     rax, 3
0x18002633b  lea     rdx, ds:0[rax*8]
0x180026343  cmp     rdx, 1000h
0x18002634a  jb      short loc_18002636A
0x18002634c  mov     rax, [rcx-8]
0x180026350  sub     rcx, rax
0x180026353  sub     rcx, 8
0x180026357  cmp     rcx, 1Fh
0x18002635b  ja      short loc_180026363
0x18002635d  add     rdx, 27h ; '''
0x180026361  jmp     short loc_18002636D
0x180026363  mov     ecx, 5
0x180026368  int     29h; Win8: RtlFailFast(ecx)
0x18002636a  mov     rax, rcx
0x18002636d  mov     rcx, rax; Block
0x180026370  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180026375  mov     rbp, [rsp+48h+arg_18]
0x18002637a  lea     rcx, [rbx+r15*8]
0x18002637e  mov     [rdi], rbx
0x180026381  mov     rax, r14
0x180026384  mov     [rdi+8], rcx
0x180026388  lea     rcx, [rsi+rbx]
0x18002638c  mov     rbx, [rsp+48h+arg_10]
0x180026391  mov     [rdi+10h], rcx
0x180026395  add     rsp, 20h
0x180026399  pop     r15
0x18002639b  pop     r14
0x18002639d  pop     r12
0x18002639f  pop     rdi
0x1800263a0  pop     rsi
0x1800263a1  retn
0x1800263a2  call    ?_Xlength@?$vector@V?$AutoNewPtr@UFeatureDescriptor@@@Windows@@V?$allocator@V?$AutoNewPtr@UFeatureDescriptor@@@Windows@@@std@@@std@@CAXXZ; std::vector<Windows::AutoNewPtr<FeatureDescriptor>>::_Xlength(void)
0x1800263a8  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
