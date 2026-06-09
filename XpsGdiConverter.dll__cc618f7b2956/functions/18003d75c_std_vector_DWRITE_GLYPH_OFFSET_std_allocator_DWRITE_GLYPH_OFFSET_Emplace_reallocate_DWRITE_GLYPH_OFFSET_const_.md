# std::vector<DWRITE_GLYPH_OFFSET,std::allocator<DWRITE_GLYPH_OFFSET>>::_Emplace_reallocate<DWRITE_GLYPH_OFFSET const &>(DWRITE_GLYPH_OFFSET * const,DWRITE_GLYPH_OFFSET const &)

- ea: `0x18003d75c`
- end: `0x18003d861`
- name: `??$_Emplace_reallocate@AEBUDWRITE_GLYPH_OFFSET@@@?$vector@UDWRITE_GLYPH_OFFSET@@V?$allocator@UDWRITE_GLYPH_OFFSET@@@std@@@std@@AEAAPEAUDWRITE_GLYPH_OFFSET@@QEAU2@AEBU2@@Z`
- size: `261`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18003dcd4`

## callees

- `0x1800093b8`
- `0x18000d900`
- `0x180011ee0`
- `0x180013404`
- `0x18001aea4`
- `0x18001b694`
- `0x180030898`
- `0x18003d75c`

## pseudocode

```c
char *__fastcall std::vector<DWRITE_GLYPH_OFFSET>::_Emplace_reallocate<DWRITE_GLYPH_OFFSET const &>(
        _QWORD *a1,
        _BYTE *a2,
        __int64 *a3)
{
  _BYTE *v3; // rbp
  __int64 v6; // rax
  __int64 v8; // r15
  __int64 v9; // r14
  __int64 size_of; // rax
  char *v11; // rax
  __int64 v12; // xmm0_8
  char *v13; // rdi
  char *v14; // rbp
  void *v15; // rcx
  _BYTE *v16; // r8
  _BYTE *v17; // rdx
  size_t v18; // r8
  _QWORD *v20; // [rsp+20h] [rbp-78h] BYREF
  __int64 v21; // [rsp+30h] [rbp-68h]
  char *v22; // [rsp+38h] [rbp-60h]
  _QWORD *v23; // [rsp+40h] [rbp-58h]

  v3 = (_BYTE *)*a1;
  v6 = (__int64)(a1[1] - *a1) >> 3;
  if ( v6 == 0x1FFFFFFFFFFFFFFFLL )
    std::vector<Gdiplus::Color>::_Xlength();
  v8 = v6 + 1;
  v9 = std::vector<DWRITE_GLYPH_OFFSET>::_Calculate_growth(a1, v6 + 1);
  size_of = std::_Get_size_of_n<8>(v9);
  v11 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  v12 = *a3;
  v20 = a1;
  v13 = v11;
  v21 = v9;
  v14 = &v11[8 * ((a2 - v3) >> 3)];
  v15 = v11;
  *(_QWORD *)v14 = v12;
  v16 = (_BYTE *)a1[1];
  v17 = (_BYTE *)*a1;
  v23 = v14 + 8;
  v22 = v14;
  if ( a2 == v16 )
  {
    v18 = v16 - v17;
  }
  else
  {
    memmove_0(v11, v17, (size_t)&a2[-*a1]);
    v17 = a2;
    v18 = a1[1] - (_QWORD)a2;
    v22 = v13;
    v15 = v14 + 8;
  }
  memmove_0(v15, v17, v18);
  std::vector<tagPOINT>::_Change_array(a1, v13, v8, v9, v20, 0, v21, v22, v23);
  std::vector<CCoordinate>::_Simple_reallocation_guard::~_Simple_reallocation_guard(&v20);
  return v14;
}

```

## disassembly

```asm
0x18003d75c  push    rbx
0x18003d75e  push    rbp
0x18003d75f  push    rsi
0x18003d760  push    rdi
0x18003d761  push    r12
0x18003d763  push    r13
0x18003d765  push    r14
0x18003d767  push    r15
0x18003d769  sub     rsp, 58h
0x18003d76d  mov     rbp, [rcx]
0x18003d770  mov     rbx, rcx
0x18003d773  mov     rax, [rcx+8]
0x18003d777  mov     r12, r8
0x18003d77a  sub     rax, rbp
0x18003d77d  mov     rcx, 1FFFFFFFFFFFFFFFh
0x18003d787  sar     rax, 3
0x18003d78b  mov     rsi, rdx
0x18003d78e  cmp     rax, rcx
0x18003d791  jz      loc_18003D85B
0x18003d797  lea     r15, [rax+1]
0x18003d79b  mov     rcx, rbx
0x18003d79e  mov     rdx, r15
0x18003d7a1  call    ?_Calculate_growth@?$vector@UDWRITE_GLYPH_OFFSET@@V?$allocator@UDWRITE_GLYPH_OFFSET@@@std@@@std@@AEBA_K_K@Z; std::vector<DWRITE_GLYPH_OFFSET>::_Calculate_growth(unsigned __int64)
0x18003d7a6  mov     rcx, rax
0x18003d7a9  mov     r14, rax
0x18003d7ac  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x18003d7b1  mov     rcx, rax
0x18003d7b4  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18003d7b9  movsd   xmm0, qword ptr [r12]
0x18003d7bf  mov     rcx, rsi
0x18003d7c2  sub     rcx, rbp
0x18003d7c5  mov     [rsp+98h+var_78], rbx
0x18003d7ca  sar     rcx, 3
0x18003d7ce  mov     rdi, rax
0x18003d7d1  mov     [rsp+98h+var_68], r14
0x18003d7d6  lea     rbp, [rax+rcx*8]
0x18003d7da  mov     rcx, rax; void *
0x18003d7dd  movsd   qword ptr [rbp+0], xmm0
0x18003d7e2  lea     r13, [rbp+8]
0x18003d7e6  mov     r8, [rbx+8]
0x18003d7ea  mov     rdx, [rbx]; Src
0x18003d7ed  mov     [rsp+98h+var_58], r13
0x18003d7f2  mov     [rsp+98h+var_60], rbp
0x18003d7f7  cmp     rsi, r8
0x18003d7fa  jnz     short loc_18003D801
0x18003d7fc  sub     r8, rdx
0x18003d7ff  jmp     short loc_18003D81E
0x18003d801  mov     r8, rsi
0x18003d804  sub     r8, [rbx]; Size
0x18003d807  call    memmove_0
0x18003d80c  mov     r8, [rbx+8]
0x18003d810  mov     rdx, rsi; Src
0x18003d813  sub     r8, rsi; Size
0x18003d816  mov     [rsp+98h+var_60], rdi
0x18003d81b  mov     rcx, r13; void *
0x18003d81e  call    memmove_0
0x18003d823  mov     r9, r14
0x18003d826  mov     [rsp+98h+var_70], 0
0x18003d82f  mov     r8, r15
0x18003d832  mov     rdx, rdi
0x18003d835  mov     rcx, rbx
0x18003d838  call    ?_Change_array@?$vector@UtagPOINT@@V?$allocator@UtagPOINT@@@std@@@std@@AEAAXQEAUtagPOINT@@_K1@Z; std::vector<tagPOINT>::_Change_array(tagPOINT * const,unsigned __int64,unsigned __int64)
0x18003d83d  lea     rcx, [rsp+98h+var_78]
0x18003d842  call    ??1_Simple_reallocation_guard@?$vector@UCCoordinate@@V?$allocator@UCCoordinate@@@std@@@std@@QEAA@XZ; std::vector<CCoordinate>::_Simple_reallocation_guard::~_Simple_reallocation_guard(void)
0x18003d847  mov     rax, rbp
0x18003d84a  add     rsp, 58h
0x18003d84e  pop     r15
0x18003d850  pop     r14
0x18003d852  pop     r13
0x18003d854  pop     r12
0x18003d856  pop     rdi
0x18003d857  pop     rsi
0x18003d858  pop     rbp
0x18003d859  pop     rbx
0x18003d85a  retn
0x18003d85b  call    ?_Xlength@?$vector@VColor@Gdiplus@@V?$allocator@VColor@Gdiplus@@@std@@@std@@CAXXZ; std::vector<Gdiplus::Color>::_Xlength(void)
```
