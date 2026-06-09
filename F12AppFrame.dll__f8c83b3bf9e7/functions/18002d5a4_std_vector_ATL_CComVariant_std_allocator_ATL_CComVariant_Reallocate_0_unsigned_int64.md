# std::vector<ATL::CComVariant,std::allocator<ATL::CComVariant>>::_Reallocate<0>(unsigned __int64 &)

- ea: `0x18002d5a4`
- end: `0x18002d6c6`
- name: `??$_Reallocate@$0A@@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@AEAAXAEA_K@Z`
- size: `290`
- prototype: `__int64 __fastcall(const VARIANTARG **, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002e670`

## callees

- `0x18000193c`
- `0x180003858`
- `0x1800056c4`
- `0x180029aa0`
- `0x18002d5a4`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x18002d664`
- `OLEAUT32!__imp_VariantCopy` at `0x18002d664`

## pseudocode

```c
__int64 __fastcall std::vector<ATL::CComVariant>::_Reallocate<0>(const VARIANTARG **a1, _QWORD *a2)
{
  const VARIANTARG *v4; // rsi
  const VARIANTARG *v5; // rbx
  __int64 v6; // rax
  size_t v7; // rcx
  VARIANTARG *v8; // rdi
  IRecordInfo *v9; // rax
  __int64 v10; // rsi
  const VARIANTARG *v11; // r12
  const VARIANTARG *v12; // rbp
  VARIANTARG *v13; // rbx
  HRESULT v14; // eax
  VARIANTARG *v16; // [rsp+28h] [rbp-60h]
  __int64 v17; // [rsp+48h] [rbp-40h]

  v4 = a1[1];
  v5 = *a1;
  v6 = *a2;
  if ( *a2 > 0xAAAAAAAAAAAAAAAuLL )
    goto LABEL_16;
  v7 = 24 * v6;
  if ( !(24 * v6) )
  {
    v8 = 0;
    goto LABEL_10;
  }
  if ( v7 < 0x1000 )
  {
    v8 = (VARIANTARG *)operator new(v7);
    goto LABEL_10;
  }
  if ( v7 + 39 < v7 )
LABEL_16:
    __scrt_throw_std_bad_array_new_length();
  v9 = (IRecordInfo *)operator new(v7 + 39);
  if ( !v9 )
    __fastfail(5u);
  v8 = (VARIANTARG *)(((unsigned __int64)&v9[4].lpVtbl + 7) & 0xFFFFFFFFFFFFFFE0uLL);
  v8[-1].pRecInfo = v9;
LABEL_10:
  v10 = (char *)v4 - (char *)v5;
  v17 = *a2;
  v11 = a1[1];
  v12 = *a1;
  v13 = v8;
  v16 = v8;
  while ( v12 != v11 )
  {
    v13->vt = 0;
    v14 = VariantCopy(v13, v12);
    if ( v14 < 0 )
    {
      v13->vt = 10;
      v13->lVal = v14;
      ATL::AtlThrowImpl(v14);
    }
    v16 = ++v13;
    ++v12;
  }
  return std::vector<ATL::CComVariant>::_Change_array(
           a1,
           v8,
           0xAAAAAAAAAAAAAAABuLL * (v10 >> 3),
           *a2,
           v8,
           v16,
           a1,
           a1,
           v8,
           v17);
}

```

## disassembly

```asm
0x18002d5a4  push    rbx
0x18002d5a6  push    rbp
0x18002d5a7  push    rsi
0x18002d5a8  push    rdi
0x18002d5a9  push    r12
0x18002d5ab  push    r14
0x18002d5ad  push    r15
0x18002d5af  sub     rsp, 50h
0x18002d5b3  mov     r15, rdx
0x18002d5b6  mov     r14, rcx
0x18002d5b9  mov     rsi, [rcx+8]
0x18002d5bd  mov     rbx, [rcx]
0x18002d5c0  mov     rax, [rdx]
0x18002d5c3  mov     rcx, 0AAAAAAAAAAAAAAAh
0x18002d5cd  cmp     rax, rcx
0x18002d5d0  ja      loc_18002D6C0
0x18002d5d6  lea     rax, [rax+rax*2]
0x18002d5da  lea     rcx, ds:0[rax*8]; Size
0x18002d5e2  test    rcx, rcx
0x18002d5e5  jnz     short loc_18002D5EB
0x18002d5e7  xor     edi, edi
0x18002d5e9  jmp     short loc_18002D629
0x18002d5eb  cmp     rcx, 1000h
0x18002d5f2  jb      short loc_18002D621
0x18002d5f4  lea     rax, [rcx+27h]
0x18002d5f8  cmp     rax, rcx
0x18002d5fb  jbe     loc_18002D6C0
0x18002d601  mov     rcx, rax; Size
0x18002d604  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002d609  test    rax, rax
0x18002d60c  jnz     short loc_18002D613
0x18002d60e  lea     ecx, [rax+5]
0x18002d611  int     29h; Win8: RtlFailFast(ecx)
0x18002d613  lea     rdi, [rax+27h]
0x18002d617  and     rdi, 0FFFFFFFFFFFFFFE0h
0x18002d61b  mov     [rdi-8], rax
0x18002d61f  jmp     short loc_18002D629
0x18002d621  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002d626  mov     rdi, rax
0x18002d629  sub     rsi, rbx
0x18002d62c  mov     [rsp+88h+var_50], r14
0x18002d631  mov     [rsp+88h+var_48], rdi
0x18002d636  mov     rcx, [r15]
0x18002d639  mov     [rsp+88h+var_40], rcx
0x18002d63e  mov     r12, [r14+8]
0x18002d642  mov     rbp, [r14]
0x18002d645  mov     [rsp+88h+var_68], rdi
0x18002d64a  mov     rbx, rdi
0x18002d64d  mov     [rsp+88h+var_60], rbx
0x18002d652  mov     [rsp+88h+var_58], r14
0x18002d657  jmp     short loc_18002D67B
0x18002d659  xor     eax, eax
0x18002d65b  mov     [rbx], ax
0x18002d65e  mov     rdx, rbp; pvargSrc
0x18002d661  mov     rcx, rbx; pvargDest
0x18002d664  call    cs:__imp_VariantCopy
0x18002d66a  test    eax, eax
0x18002d66c  js      short loc_18002D6B0
0x18002d66e  add     rbx, 18h
0x18002d672  mov     [rsp+88h+var_60], rbx
0x18002d677  add     rbp, 18h
0x18002d67b  cmp     rbp, r12
0x18002d67e  jnz     short loc_18002D659
0x18002d680  sar     rsi, 3
0x18002d684  mov     r8, 0AAAAAAAAAAAAAAABh
0x18002d68e  imul    r8, rsi
0x18002d692  mov     r9, [r15]
0x18002d695  mov     rdx, rdi
0x18002d698  mov     rcx, r14
0x18002d69b  call    ?_Change_array@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@AEAAXQEAVCComVariant@ATL@@_K1@Z; std::vector<ATL::CComVariant>::_Change_array(ATL::CComVariant * const,unsigned __int64,unsigned __int64)
0x18002d6a0  nop
0x18002d6a1  add     rsp, 50h
0x18002d6a5  pop     r15
0x18002d6a7  pop     r14
0x18002d6a9  pop     r12
0x18002d6ab  pop     rdi
0x18002d6ac  pop     rsi
0x18002d6ad  pop     rbp
0x18002d6ae  pop     rbx
0x18002d6af  retn
0x18002d6b0  mov     word ptr [rbx], 0Ah
0x18002d6b5  mov     [rbx+8], eax
0x18002d6b8  mov     ecx, eax; int
0x18002d6ba  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002d6c0  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
