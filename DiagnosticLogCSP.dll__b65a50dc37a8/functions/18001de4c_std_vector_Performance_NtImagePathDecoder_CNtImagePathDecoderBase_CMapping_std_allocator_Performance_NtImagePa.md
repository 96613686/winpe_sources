# std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>::_Emplace_reallocate<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping const &>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping const &)

- ea: `0x18001de4c`
- end: `0x18001e06b`
- name: `??$_Emplace_reallocate@AEBUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@?$vector@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@AEAAPEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU2345@AEBU2345@@Z`
- size: `543`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180022d48`

## callees

- `0x180001bb4`
- `0x180001bf8`
- `0x18000a924`
- `0x18000c07c`
- `0x1800105f8`
- `0x18001de4c`
- `0x18001e954`
- `0x180020560`
- `0x180027b50`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x18001de4c  mov     [rsp+arg_8], rbx
0x18001de51  mov     [rsp+arg_10], r8
0x18001de56  push    rbp
0x18001de57  push    rsi
0x18001de58  push    rdi
0x18001de59  push    r12
0x18001de5b  push    r13
0x18001de5d  push    r14
0x18001de5f  push    r15
0x18001de61  sub     rsp, 50h
0x18001de65  mov     r13, rdx
0x18001de68  mov     rsi, rcx
0x18001de6b  mov     rbx, [rcx]
0x18001de6e  mov     rax, [rcx+8]
0x18001de72  sub     rax, rbx
0x18001de75  sar     rax, 6
0x18001de79  mov     rbp, 3FFFFFFFFFFFFFFh
0x18001de83  cmp     rax, rbp
0x18001de86  jz      loc_18001E05F
0x18001de8c  lea     r15, [rax+1]
0x18001de90  mov     rcx, [rcx+10h]
0x18001de94  sub     rcx, rbx
0x18001de97  sar     rcx, 6
0x18001de9b  mov     rdx, rcx
0x18001de9e  shr     rdx, 1
0x18001dea1  mov     rax, rbp
0x18001dea4  sub     rax, rdx
0x18001dea7  cmp     rcx, rax
0x18001deaa  jbe     short loc_18001DEB9
0x18001deac  mov     rcx, 0FFFFFFFFFFFFFFE7h
0x18001deb3  lea     r14, [rcx-27h]
0x18001deb7  jmp     short loc_18001DEF9
0x18001deb9  lea     rax, [rcx+rdx]
0x18001debd  mov     rcx, r15
0x18001dec0  cmp     rax, r15
0x18001dec3  cmovnb  rcx, rax
0x18001dec7  cmp     rcx, rbp
0x18001deca  ja      loc_18001E065
0x18001ded0  mov     r14, rcx
0x18001ded3  shl     r14, 6
0x18001ded7  mov     rbp, rcx
0x18001deda  test    r14, r14
0x18001dedd  jnz     short loc_18001DEE3
0x18001dedf  xor     edi, edi
0x18001dee1  jmp     short loc_18001DF21
0x18001dee3  cmp     r14, 1000h
0x18001deea  jb      short loc_18001DF16
0x18001deec  lea     rcx, [r14+27h]; Size
0x18001def0  cmp     rcx, r14
0x18001def3  jbe     loc_18001E065
0x18001def9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001defe  test    rax, rax
0x18001df01  jnz     short loc_18001DF08
0x18001df03  lea     ecx, [rax+5]
0x18001df06  int     29h; Win8: RtlFailFast(ecx)
0x18001df08  lea     rdi, [rax+27h]
0x18001df0c  and     rdi, 0FFFFFFFFFFFFFFE0h
0x18001df10  mov     [rdi-8], rax
0x18001df14  jmp     short loc_18001DF21
0x18001df16  mov     rcx, r14; Size
0x18001df19  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001df1e  mov     rdi, rax
0x18001df21  mov     r12, r13
0x18001df24  sub     r12, rbx
0x18001df27  sar     r12, 6
0x18001df2b  mov     rbx, r12
0x18001df2e  shl     rbx, 6
0x18001df32  add     rbx, rdi
0x18001df35  lea     rax, [rbx+40h]
0x18001df39  mov     [rsp+88h+var_68], rsi
0x18001df3e  mov     [rsp+88h+var_60], rdi
0x18001df43  mov     [rsp+88h+var_58], rbp
0x18001df48  mov     [rsp+88h+var_50], rax
0x18001df4d  mov     [rsp+88h+var_48], rax
0x18001df52  mov     [rsp+88h+arg_0], rbx
0x18001df5a  mov     rbp, [rsp+88h+arg_10]
0x18001df62  mov     rdx, rbp
0x18001df65  mov     rcx, rbx
0x18001df68  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001df6d  nop
0x18001df6e  lea     rdx, [rbp+20h]
0x18001df72  lea     rcx, [rbx+20h]
0x18001df76  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001df7b  nop
0x18001df7c  mov     [rsp+88h+var_50], rbx
0x18001df81  mov     rdx, [rsi+8]
0x18001df85  mov     r8, rdi
0x18001df88  mov     rcx, [rsi]
0x18001df8b  cmp     r13, rdx
0x18001df8e  jz      short loc_18001DFA8
0x18001df90  mov     rdx, r13
0x18001df93  call    ??$_Uninitialized_move@PEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAPEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU1234@0PEAU1234@AEAV?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@@Z; std::_Uninitialized_move<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping> &)
0x18001df98  mov     [rsp+88h+var_50], rdi
0x18001df9d  lea     r8, [rbx+40h]
0x18001dfa1  mov     rdx, [rsi+8]
0x18001dfa5  mov     rcx, r13
0x18001dfa8  call    ??$_Uninitialized_move@PEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAPEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU1234@0PEAU1234@AEAV?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@@Z; std::_Uninitialized_move<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping> &)
0x18001dfad  mov     [rsp+88h+var_60], 0
0x18001dfb6  mov     rbx, [rsi]
0x18001dfb9  test    rbx, rbx
0x18001dfbc  jz      short loc_18001E01B
0x18001dfbe  mov     rbp, [rsi+8]
0x18001dfc2  jmp     short loc_18001DFD9
0x18001dfc4  lea     rcx, [rbx+20h]
0x18001dfc8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001dfcd  mov     rcx, rbx
0x18001dfd0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001dfd5  add     rbx, 40h ; '@'
0x18001dfd9  cmp     rbx, rbp
0x18001dfdc  jnz     short loc_18001DFC4
0x18001dfde  mov     rax, [rsi]
0x18001dfe1  mov     rdx, [rsi+10h]
0x18001dfe5  sub     rdx, rax
0x18001dfe8  and     rdx, 0FFFFFFFFFFFFFFC0h; unsigned __int64
0x18001dfec  cmp     rdx, 1000h
0x18001dff3  jb      short loc_18001E013
0x18001dff5  mov     rcx, [rax-8]
0x18001dff9  sub     rax, rcx
0x18001dffc  sub     rax, 8
0x18001e000  cmp     rax, 1Fh
0x18001e004  ja      short loc_18001E00C
0x18001e006  add     rdx, 27h ; '''
0x18001e00a  jmp     short loc_18001E016
0x18001e00c  mov     ecx, 5
0x18001e011  int     29h; Win8: RtlFailFast(ecx)
0x18001e013  mov     rcx, rax; void *
0x18001e016  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001e01b  mov     [rsi], rdi
0x18001e01e  shl     r15, 6
0x18001e022  add     r15, rdi
0x18001e025  mov     [rsi+8], r15
0x18001e029  lea     rax, [r14+rdi]
0x18001e02d  mov     [rsi+10h], rax
0x18001e031  shl     r12, 6
0x18001e035  lea     rbx, [r12+rdi]
0x18001e039  lea     rcx, [rsp+88h+var_68]
0x18001e03e  call    ??1_Reallocation_guard@?$vector@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@QEAA@XZ; std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::_Reallocation_guard::~_Reallocation_guard(void)
0x18001e043  mov     rax, rbx
0x18001e046  mov     rbx, [rsp+88h+arg_8]
0x18001e04e  add     rsp, 50h
0x18001e052  pop     r15
0x18001e054  pop     r14
0x18001e056  pop     r13
0x18001e058  pop     r12
0x18001e05a  pop     rdi
0x18001e05b  pop     rsi
0x18001e05c  pop     rbp
0x18001e05d  retn
0x18001e05f  call    ?_Xlength@?$vector@IV?$allocator@I@std@@@std@@CAXXZ; std::vector<uint>::_Xlength(void)
0x18001e065  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
