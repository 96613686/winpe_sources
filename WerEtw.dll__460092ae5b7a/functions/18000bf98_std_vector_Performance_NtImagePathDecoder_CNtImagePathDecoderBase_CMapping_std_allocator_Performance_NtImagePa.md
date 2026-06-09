# std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>::_Emplace_reallocate<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping const &>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping const &)

- ea: `0x18000bf98`
- end: `0x18000c1b6`
- name: `??$_Emplace_reallocate@AEBUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@?$vector@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@AEAAPEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU2345@AEBU2345@@Z`
- size: `542`
- prototype: `char *__fastcall(_QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x1800111f8`

## callees

- `0x180001894`
- `0x1800018a0`
- `0x18000b534`
- `0x18000be50`
- `0x18000bf98`
- `0x18000ccd4`
- `0x18000d074`
- `0x18000e920`
- `0x180015b68`

## pseudocode

```c
char *__fastcall std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::_Emplace_reallocate<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping const &>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  void *v5; // rbx
  __int64 v6; // rax
  __int64 v7; // rbp
  unsigned __int64 v8; // r15
  unsigned __int64 v9; // rcx
  size_t v10; // rcx
  unsigned __int64 v11; // r14
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // rcx
  _QWORD *v14; // rdi
  void *v15; // rax
  __int64 v16; // r12
  char *v17; // rbx
  __int64 v18; // rdx
  _QWORD *v19; // r8
  __int64 v20; // rcx
  __int64 v21; // rbx
  __int64 v22; // rbp
  __int64 v23; // rax
  void *v24; // rcx
  _QWORD *v26; // [rsp+20h] [rbp-68h] BYREF
  _QWORD *v27; // [rsp+28h] [rbp-60h]
  __int64 v28; // [rsp+30h] [rbp-58h]
  _QWORD *v29; // [rsp+38h] [rbp-50h]
  char *v30; // [rsp+40h] [rbp-48h]

  v5 = (void *)*a1;
  v6 = (__int64)(a1[1] - *a1) >> 6;
  v7 = 0x3FFFFFFFFFFFFFFLL;
  if ( v6 == 0x3FFFFFFFFFFFFFFLL )
    std::vector<unsigned int>::_Xlength();
  v8 = v6 + 1;
  v9 = (__int64)(a1[2] - (_QWORD)v5) >> 6;
  if ( v9 <= 0x3FFFFFFFFFFFFFFLL - (v9 >> 1) )
  {
    v12 = v9 + (v9 >> 1);
    v13 = v8;
    if ( v12 >= v8 )
      v13 = v12;
    if ( v13 > 0x3FFFFFFFFFFFFFFLL )
      goto LABEL_28;
    v11 = v13 << 6;
    v7 = v13;
    if ( !(v13 << 6) )
    {
      v14 = 0;
      goto LABEL_15;
    }
    if ( v11 < 0x1000 )
    {
      v14 = operator new(v13 << 6);
      goto LABEL_15;
    }
    v10 = v11 + 39;
    if ( v11 + 39 < v11 )
LABEL_28:
      __scrt_throw_std_bad_array_new_length();
  }
  else
  {
    v10 = -25;
    v11 = -64;
  }
  v15 = operator new(v10);
  if ( !v15 )
    __fastfail(5u);
  v14 = (_QWORD *)(((unsigned __int64)v15 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v14 - 1) = v15;
LABEL_15:
  v16 = (a2 - (__int64)v5) >> 6;
  v17 = (char *)&v14[8 * v16];
  v26 = a1;
  v27 = v14;
  v28 = v7;
  v30 = v17 + 64;
  std::wstring::wstring(v17, a3);
  std::wstring::wstring(v17 + 32, a3 + 32);
  v29 = v17;
  v18 = a1[1];
  v19 = v14;
  v20 = *a1;
  if ( a2 != v18 )
  {
    std::_Uninitialized_move<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *>(v20, a2, v14);
    v29 = v14;
    v19 = v17 + 64;
    v18 = a1[1];
    v20 = a2;
  }
  std::_Uninitialized_move<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *>(v20, v18, v19);
  v27 = 0;
  v21 = *a1;
  if ( *a1 )
  {
    v22 = a1[1];
    while ( v21 != v22 )
    {
      std::wstring::~wstring(v21 + 32);
      std::wstring::~wstring(v21);
      v21 += 64;
    }
    v23 = *a1;
    if ( ((a1[2] - *a1) & 0xFFFFFFFFFFFFFFC0uLL) < 0x1000 )
    {
      v24 = (void *)*a1;
    }
    else
    {
      v24 = *(void **)(v23 - 8);
      if ( (unsigned __int64)(v23 - (_QWORD)v24 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v24);
  }
  *a1 = v14;
  a1[1] = &v14[8 * v8];
  a1[2] = (char *)v14 + v11;
  std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::_Reallocation_guard::~_Reallocation_guard(&v26);
  return (char *)&v14[8 * v16];
}

```

## disassembly

```asm
0x18000bf98  mov     [rsp+arg_8], rbx
0x18000bf9d  mov     [rsp+arg_10], r8
0x18000bfa2  push    rbp
0x18000bfa3  push    rsi
0x18000bfa4  push    rdi
0x18000bfa5  push    r12
0x18000bfa7  push    r13
0x18000bfa9  push    r14
0x18000bfab  push    r15
0x18000bfad  sub     rsp, 50h
0x18000bfb1  mov     r13, rdx
0x18000bfb4  mov     rsi, rcx
0x18000bfb7  mov     rbx, [rcx]
0x18000bfba  mov     rax, [rcx+8]
0x18000bfbe  sub     rax, rbx
0x18000bfc1  sar     rax, 6
0x18000bfc5  mov     rbp, 3FFFFFFFFFFFFFFh
0x18000bfcf  cmp     rax, rbp
0x18000bfd2  jz      loc_18000C1AA
0x18000bfd8  lea     r15, [rax+1]
0x18000bfdc  mov     rcx, [rcx+10h]
0x18000bfe0  sub     rcx, rbx
0x18000bfe3  sar     rcx, 6
0x18000bfe7  mov     rdx, rcx
0x18000bfea  shr     rdx, 1
0x18000bfed  mov     rax, rbp
0x18000bff0  sub     rax, rdx
0x18000bff3  cmp     rcx, rax
0x18000bff6  jbe     short loc_18000C005
0x18000bff8  mov     rcx, 0FFFFFFFFFFFFFFE7h
0x18000bfff  lea     r14, [rcx-27h]
0x18000c003  jmp     short loc_18000C045
0x18000c005  lea     rax, [rcx+rdx]
0x18000c009  mov     rcx, r15
0x18000c00c  cmp     rax, r15
0x18000c00f  cmovnb  rcx, rax
0x18000c013  cmp     rcx, rbp
0x18000c016  ja      loc_18000C1B0
0x18000c01c  mov     r14, rcx
0x18000c01f  shl     r14, 6
0x18000c023  mov     rbp, rcx
0x18000c026  test    r14, r14
0x18000c029  jnz     short loc_18000C02F
0x18000c02b  xor     edi, edi
0x18000c02d  jmp     short loc_18000C06D
0x18000c02f  cmp     r14, 1000h
0x18000c036  jb      short loc_18000C062
0x18000c038  lea     rcx, [r14+27h]; Size
0x18000c03c  cmp     rcx, r14
0x18000c03f  jbe     loc_18000C1B0
0x18000c045  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c04a  test    rax, rax
0x18000c04d  jnz     short loc_18000C054
0x18000c04f  lea     ecx, [rax+5]
0x18000c052  int     29h; Win8: RtlFailFast(ecx)
0x18000c054  lea     rdi, [rax+27h]
0x18000c058  and     rdi, 0FFFFFFFFFFFFFFE0h
0x18000c05c  mov     [rdi-8], rax
0x18000c060  jmp     short loc_18000C06D
0x18000c062  mov     rcx, r14; Size
0x18000c065  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c06a  mov     rdi, rax
0x18000c06d  mov     r12, r13
0x18000c070  sub     r12, rbx
0x18000c073  sar     r12, 6
0x18000c077  mov     rbx, r12
0x18000c07a  shl     rbx, 6
0x18000c07e  add     rbx, rdi
0x18000c081  lea     rax, [rbx+40h]
0x18000c085  mov     [rsp+88h+var_68], rsi
0x18000c08a  mov     [rsp+88h+var_60], rdi
0x18000c08f  mov     [rsp+88h+var_58], rbp
0x18000c094  mov     [rsp+88h+var_50], rax
0x18000c099  mov     [rsp+88h+var_48], rax
0x18000c09e  mov     [rsp+88h+arg_0], rbx
0x18000c0a6  mov     rbp, [rsp+88h+arg_10]
0x18000c0ae  mov     rdx, rbp
0x18000c0b1  mov     rcx, rbx
0x18000c0b4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000c0b9  nop
0x18000c0ba  lea     rdx, [rbp+20h]
0x18000c0be  lea     rcx, [rbx+20h]
0x18000c0c2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000c0c7  nop
0x18000c0c8  mov     [rsp+88h+var_50], rbx
0x18000c0cd  mov     rdx, [rsi+8]
0x18000c0d1  mov     r8, rdi
0x18000c0d4  mov     rcx, [rsi]
0x18000c0d7  cmp     r13, rdx
0x18000c0da  jz      short loc_18000C0F4
0x18000c0dc  mov     rdx, r13
0x18000c0df  call    ??$_Uninitialized_move@PEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAPEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU1234@0PEAU1234@AEAV?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@@Z; std::_Uninitialized_move<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping> &)
0x18000c0e4  mov     [rsp+88h+var_50], rdi
0x18000c0e9  lea     r8, [rbx+40h]
0x18000c0ed  mov     rdx, [rsi+8]
0x18000c0f1  mov     rcx, r13
0x18000c0f4  call    ??$_Uninitialized_move@PEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAPEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU1234@0PEAU1234@AEAV?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@@Z; std::_Uninitialized_move<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping> &)
0x18000c0f9  mov     [rsp+88h+var_60], 0
0x18000c102  mov     rbx, [rsi]
0x18000c105  test    rbx, rbx
0x18000c108  jz      short loc_18000C167
0x18000c10a  mov     rbp, [rsi+8]
0x18000c10e  jmp     short loc_18000C125
0x18000c110  lea     rcx, [rbx+20h]
0x18000c114  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000c119  mov     rcx, rbx
0x18000c11c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000c121  add     rbx, 40h ; '@'
0x18000c125  cmp     rbx, rbp
0x18000c128  jnz     short loc_18000C110
0x18000c12a  mov     rax, [rsi]
0x18000c12d  mov     rdx, [rsi+10h]
0x18000c131  sub     rdx, rax
0x18000c134  and     rdx, 0FFFFFFFFFFFFFFC0h
0x18000c138  cmp     rdx, 1000h
0x18000c13f  jb      short loc_18000C15F
0x18000c141  mov     rcx, [rax-8]
0x18000c145  sub     rax, rcx
0x18000c148  sub     rax, 8
0x18000c14c  cmp     rax, 1Fh
0x18000c150  ja      short loc_18000C158
0x18000c152  add     rdx, 27h ; '''
0x18000c156  jmp     short loc_18000C162
0x18000c158  mov     ecx, 5
0x18000c15d  int     29h; Win8: RtlFailFast(ecx)
0x18000c15f  mov     rcx, rax; Block
0x18000c162  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c167  mov     [rsi], rdi
0x18000c16a  shl     r15, 6
0x18000c16e  add     r15, rdi
0x18000c171  mov     [rsi+8], r15
0x18000c175  lea     rax, [r14+rdi]
0x18000c179  mov     [rsi+10h], rax
0x18000c17d  shl     r12, 6
0x18000c181  lea     rbx, [r12+rdi]
0x18000c185  lea     rcx, [rsp+88h+var_68]
0x18000c18a  call    ??1_Reallocation_guard@?$vector@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@QEAA@XZ; std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::_Reallocation_guard::~_Reallocation_guard(void)
0x18000c18f  mov     rax, rbx
0x18000c192  mov     rbx, [rsp+88h+arg_8]
0x18000c19a  add     rsp, 50h
0x18000c19e  pop     r15
0x18000c1a0  pop     r14
0x18000c1a2  pop     r13
0x18000c1a4  pop     r12
0x18000c1a6  pop     rdi
0x18000c1a7  pop     rsi
0x18000c1a8  pop     rbp
0x18000c1a9  retn
0x18000c1aa  call    ?_Xlength@?$vector@IV?$allocator@I@std@@@std@@CAXXZ; std::vector<uint>::_Xlength(void)
0x18000c1b0  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
