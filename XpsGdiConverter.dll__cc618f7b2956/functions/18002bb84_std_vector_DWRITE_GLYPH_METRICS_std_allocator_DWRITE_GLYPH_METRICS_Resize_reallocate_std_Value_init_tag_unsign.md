# std::vector<DWRITE_GLYPH_METRICS,std::allocator<DWRITE_GLYPH_METRICS>>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)

- ea: `0x18002bb84`
- end: `0x18002bc7a`
- name: `??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UDWRITE_GLYPH_METRICS@@V?$allocator@UDWRITE_GLYPH_METRICS@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z`
- size: `246`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18002c850`

## callees

- `0x1800093b8`
- `0x18000d900`
- `0x180011cf4`
- `0x180011ee0`
- `0x18002bb84`
- `0x18002bc80`
- `0x18002bccc`
- `0x18002c750`

## pseudocode

```c
__int64 __fastcall std::vector<DWRITE_GLYPH_METRICS>::_Resize_reallocate<std::_Value_init_tag>(
        const void **a1,
        unsigned __int64 a2)
{
  __int64 v2; // rsi
  unsigned __int64 v5; // rcx
  unsigned __int64 v6; // rdx
  __int64 v7; // rbx
  __int64 v8; // rax
  void *v9; // rdi
  __int64 v10; // rax
  size_t v11; // r8
  const void *v12; // rdx
  _QWORD v14[3]; // [rsp+20h] [rbp-58h] BYREF
  __int64 v15; // [rsp+38h] [rbp-40h]
  __int64 v16; // [rsp+40h] [rbp-38h]

  v2 = 0x924924924924924LL;
  if ( a2 > 0x924924924924924LL )
    std::vector<Gdiplus::Color>::_Xlength();
  v5 = 0x6DB6DB6DB6DB6DB7LL * (((_BYTE *)a1[2] - (_BYTE *)*a1) >> 2);
  v6 = v5 >> 1;
  if ( v5 <= 0x924924924924924LL - (v5 >> 1) )
  {
    if ( v5 + v6 >= a2 )
    {
      if ( v5 + v6 > 0x924924924924924LL )
        __scrt_throw_std_bad_array_new_length();
      v2 = v5 + v6;
    }
    else
    {
      v2 = a2;
    }
  }
  v7 = 0x6DB6DB6DB6DB6DB7LL * (((_BYTE *)a1[1] - (_BYTE *)*a1) >> 2);
  v8 = std::_Allocate<16,std::_Default_allocate_traits>(28 * v2);
  v14[0] = a1;
  v14[2] = v2;
  v15 = v8 + 28 * v7;
  v9 = (void *)v8;
  v10 = std::_Uninitialized_value_construct_n<std::allocator<DWRITE_GLYPH_METRICS>>(v15, a2 - v7);
  v11 = (_BYTE *)a1[1] - (_BYTE *)*a1;
  v12 = *a1;
  v16 = v10;
  memmove_0(v9, v12, v11);
  v14[1] = 0;
  std::vector<DWRITE_GLYPH_METRICS>::_Change_array(a1, v9, a2, v2);
  return std::vector<DWRITE_GLYPH_METRICS>::_Reallocation_guard::~_Reallocation_guard(v14);
}

```

## disassembly

```asm
0x18002bb84  push    rbx
0x18002bb86  push    rbp
0x18002bb87  push    rsi
0x18002bb88  push    rdi
0x18002bb89  push    r14
0x18002bb8b  sub     rsp, 50h
0x18002bb8f  mov     rsi, 924924924924924h
0x18002bb99  mov     rbp, rdx
0x18002bb9c  mov     r14, rcx
0x18002bb9f  cmp     rdx, rsi
0x18002bba2  ja      loc_18002BC74
0x18002bba8  mov     rcx, [rcx+10h]
0x18002bbac  mov     r8, 6DB6DB6DB6DB6DB7h
0x18002bbb6  sub     rcx, [r14]
0x18002bbb9  mov     rax, rsi
0x18002bbbc  sar     rcx, 2
0x18002bbc0  imul    rcx, r8
0x18002bbc4  mov     rdx, rcx
0x18002bbc7  shr     rdx, 1
0x18002bbca  sub     rax, rdx
0x18002bbcd  cmp     rcx, rax
0x18002bbd0  ja      short loc_18002BBEC
0x18002bbd2  lea     rax, [rcx+rdx]
0x18002bbd6  cmp     rax, rbp
0x18002bbd9  jnb     short loc_18002BBE0
0x18002bbdb  mov     rsi, rbp
0x18002bbde  jmp     short loc_18002BBEC
0x18002bbe0  cmp     rax, rsi
0x18002bbe3  ja      loc_18002BC6E
0x18002bbe9  mov     rsi, rax
0x18002bbec  mov     rbx, [r14+8]
0x18002bbf0  sub     rbx, [r14]
0x18002bbf3  imul    rcx, rsi, 1Ch
0x18002bbf7  sar     rbx, 2
0x18002bbfb  imul    rbx, r8
0x18002bbff  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18002bc04  imul    rcx, rbx, 1Ch
0x18002bc08  mov     rdx, rbp
0x18002bc0b  mov     [rsp+78h+var_58], r14
0x18002bc10  add     rcx, rax
0x18002bc13  mov     [rsp+78h+var_48], rsi
0x18002bc18  sub     rdx, rbx
0x18002bc1b  mov     [rsp+78h+var_40], rcx
0x18002bc20  mov     rdi, rax
0x18002bc23  call    ??$_Uninitialized_value_construct_n@V?$allocator@UDWRITE_GLYPH_METRICS@@@std@@@std@@YAPEAUDWRITE_GLYPH_METRICS@@PEAU1@_KAEAV?$allocator@UDWRITE_GLYPH_METRICS@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<DWRITE_GLYPH_METRICS>>(DWRITE_GLYPH_METRICS *,unsigned __int64,std::allocator<DWRITE_GLYPH_METRICS> &)
0x18002bc28  mov     r8, [r14+8]
0x18002bc2c  mov     rcx, rdi; void *
0x18002bc2f  sub     r8, [r14]; Size
0x18002bc32  mov     rdx, [r14]; Src
0x18002bc35  mov     [rsp+78h+var_38], rax
0x18002bc3a  call    memmove_0
0x18002bc3f  mov     r9, rsi
0x18002bc42  mov     [rsp+78h+var_50], 0
0x18002bc4b  mov     r8, rbp
0x18002bc4e  mov     rdx, rdi
0x18002bc51  mov     rcx, r14
0x18002bc54  call    ?_Change_array@?$vector@UDWRITE_GLYPH_METRICS@@V?$allocator@UDWRITE_GLYPH_METRICS@@@std@@@std@@AEAAXQEAUDWRITE_GLYPH_METRICS@@_K1@Z; std::vector<DWRITE_GLYPH_METRICS>::_Change_array(DWRITE_GLYPH_METRICS * const,unsigned __int64,unsigned __int64)
0x18002bc59  lea     rcx, [rsp+78h+var_58]
0x18002bc5e  call    ??1_Reallocation_guard@?$vector@UDWRITE_GLYPH_METRICS@@V?$allocator@UDWRITE_GLYPH_METRICS@@@std@@@std@@QEAA@XZ; std::vector<DWRITE_GLYPH_METRICS>::_Reallocation_guard::~_Reallocation_guard(void)
0x18002bc63  add     rsp, 50h
0x18002bc67  pop     r14
0x18002bc69  pop     rdi
0x18002bc6a  pop     rsi
0x18002bc6b  pop     rbp
0x18002bc6c  pop     rbx
0x18002bc6d  retn
0x18002bc6e  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
0x18002bc74  call    ?_Xlength@?$vector@VColor@Gdiplus@@V?$allocator@VColor@Gdiplus@@@std@@@std@@CAXXZ; std::vector<Gdiplus::Color>::_Xlength(void)
```
