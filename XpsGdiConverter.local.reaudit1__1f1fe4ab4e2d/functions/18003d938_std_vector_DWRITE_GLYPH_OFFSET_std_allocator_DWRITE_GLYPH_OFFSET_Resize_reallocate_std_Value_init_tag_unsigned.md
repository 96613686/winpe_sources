# std::vector<DWRITE_GLYPH_OFFSET,std::allocator<DWRITE_GLYPH_OFFSET>>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)

- ea: `0x18003d938`
- end: `0x18003d9ec`
- name: `??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UDWRITE_GLYPH_OFFSET@@V?$allocator@UDWRITE_GLYPH_OFFSET@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z`
- size: `180`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
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
- `0x18003d938`
- `0x18003daf4`

## pseudocode

```c
__int64 __fastcall std::vector<DWRITE_GLYPH_OFFSET>::_Resize_reallocate<std::_Value_init_tag>(
        const void **a1,
        unsigned __int64 a2)
{
  __int64 v4; // rbx
  __int64 v5; // rsi
  __int64 size_of; // rax
  char *v7; // rdi
  __int64 v8; // rax
  size_t v9; // r8
  const void *v10; // rdx
  _QWORD v12[3]; // [rsp+20h] [rbp-58h] BYREF
  char *v13; // [rsp+38h] [rbp-40h]
  __int64 v14; // [rsp+40h] [rbp-38h]

  if ( a2 > 0x1FFFFFFFFFFFFFFFLL )
    std::vector<Gdiplus::Color>::_Xlength();
  v4 = ((_BYTE *)a1[1] - (_BYTE *)*a1) >> 3;
  v5 = std::vector<DWRITE_GLYPH_OFFSET>::_Calculate_growth(a1, a2);
  size_of = std::_Get_size_of_n<8>(v5);
  v12[0] = a1;
  v12[2] = v5;
  v7 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  v13 = &v7[8 * v4];
  v8 = std::_Uninitialized_value_construct_n<std::allocator<DWRITE_GLYPH_OFFSET>>(v13, a2 - v4);
  v9 = (_BYTE *)a1[1] - (_BYTE *)*a1;
  v10 = *a1;
  v14 = v8;
  memmove_0(v7, v10, v9);
  std::vector<tagPOINT>::_Change_array(a1, v7, a2, v5, a1, 0, v5, v13, v14);
  return std::vector<CCoordinate>::_Simple_reallocation_guard::~_Simple_reallocation_guard(v12);
}

```

## disassembly

```asm
0x18003d938  push    rbx
0x18003d93a  push    rbp
0x18003d93b  push    rsi
0x18003d93c  push    rdi
0x18003d93d  push    r14
0x18003d93f  sub     rsp, 50h
0x18003d943  mov     rax, 1FFFFFFFFFFFFFFFh
0x18003d94d  mov     rbp, rdx
0x18003d950  mov     r14, rcx
0x18003d953  cmp     rdx, rax
0x18003d956  ja      loc_18003D9E6
0x18003d95c  mov     rbx, [rcx+8]
0x18003d960  sub     rbx, [rcx]
0x18003d963  sar     rbx, 3
0x18003d967  call    ?_Calculate_growth@?$vector@UDWRITE_GLYPH_OFFSET@@V?$allocator@UDWRITE_GLYPH_OFFSET@@@std@@@std@@AEBA_K_K@Z; std::vector<DWRITE_GLYPH_OFFSET>::_Calculate_growth(unsigned __int64)
0x18003d96c  mov     rcx, rax
0x18003d96f  mov     rsi, rax
0x18003d972  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x18003d977  mov     rcx, rax
0x18003d97a  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18003d97f  mov     rdx, rbp
0x18003d982  mov     [rsp+78h+var_58], r14
0x18003d987  sub     rdx, rbx
0x18003d98a  mov     [rsp+78h+var_48], rsi
0x18003d98f  mov     rdi, rax
0x18003d992  lea     rcx, [rax+rbx*8]
0x18003d996  mov     [rsp+78h+var_40], rcx
0x18003d99b  call    ??$_Uninitialized_value_construct_n@V?$allocator@UDWRITE_GLYPH_OFFSET@@@std@@@std@@YAPEAUDWRITE_GLYPH_OFFSET@@PEAU1@_KAEAV?$allocator@UDWRITE_GLYPH_OFFSET@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<DWRITE_GLYPH_OFFSET>>(DWRITE_GLYPH_OFFSET *,unsigned __int64,std::allocator<DWRITE_GLYPH_OFFSET> &)
0x18003d9a0  mov     r8, [r14+8]
0x18003d9a4  mov     rcx, rdi; void *
0x18003d9a7  sub     r8, [r14]; Size
0x18003d9aa  mov     rdx, [r14]; Src
0x18003d9ad  mov     [rsp+78h+var_38], rax
0x18003d9b2  call    memmove_0
0x18003d9b7  mov     r9, rsi
0x18003d9ba  mov     [rsp+78h+var_50], 0
0x18003d9c3  mov     r8, rbp
0x18003d9c6  mov     rdx, rdi
0x18003d9c9  mov     rcx, r14
0x18003d9cc  call    ?_Change_array@?$vector@UtagPOINT@@V?$allocator@UtagPOINT@@@std@@@std@@AEAAXQEAUtagPOINT@@_K1@Z; std::vector<tagPOINT>::_Change_array(tagPOINT * const,unsigned __int64,unsigned __int64)
0x18003d9d1  lea     rcx, [rsp+78h+var_58]
0x18003d9d6  call    ??1_Simple_reallocation_guard@?$vector@UCCoordinate@@V?$allocator@UCCoordinate@@@std@@@std@@QEAA@XZ; std::vector<CCoordinate>::_Simple_reallocation_guard::~_Simple_reallocation_guard(void)
0x18003d9db  add     rsp, 50h
0x18003d9df  pop     r14
0x18003d9e1  pop     rdi
0x18003d9e2  pop     rsi
0x18003d9e3  pop     rbp
0x18003d9e4  pop     rbx
0x18003d9e5  retn
0x18003d9e6  call    ?_Xlength@?$vector@VColor@Gdiplus@@V?$allocator@VColor@Gdiplus@@@std@@@std@@CAXXZ; std::vector<Gdiplus::Color>::_Xlength(void)
```
