# std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>::_Emplace_reallocate<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping const &>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping const &)

- ea: `0x18001ceb8`
- end: `0x18001d0d6`
- name: `??$_Emplace_reallocate@AEBUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@?$vector@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@AEAAPEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU2345@AEBU2345@@Z`
- size: `542`
- prototype: `char *__fastcall(_QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180021e08`

## callees

- `0x180001b84`
- `0x180001bc8`
- `0x18000a600`
- `0x18000bb3c`
- `0x18000fde8`
- `0x18001ceb8`
- `0x18001d9bc`
- `0x18001f544`
- `0x180026964`

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
  unsigned __int64 v24; // rdx
  void *v25; // rcx
  _QWORD *v27; // [rsp+20h] [rbp-68h] BYREF
  _QWORD *v28; // [rsp+28h] [rbp-60h]
  __int64 v29; // [rsp+30h] [rbp-58h]
  _QWORD *v30; // [rsp+38h] [rbp-50h]
  char *v31; // [rsp+40h] [rbp-48h]

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
      goto LABEL_29;
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
LABEL_29:
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
  v27 = a1;
  v28 = v14;
  v29 = v7;
  v31 = v17 + 64;
  std::wstring::wstring(v17, a3);
  std::wstring::wstring(v17 + 32, a3 + 32);
  v30 = v17;
  v18 = a1[1];
  v19 = v14;
  v20 = *a1;
  if ( a2 != v18 )
  {
    std::_Uninitialized_move<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *>(v20, a2, v14);
    v30 = v14;
    v19 = v17 + 64;
    v18 = a1[1];
    v20 = a2;
  }
  std::_Uninitialized_move<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *>(v20, v18, v19);
  v28 = 0;
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
    v24 = (a1[2] - *a1) & 0xFFFFFFFFFFFFFFC0uLL;
    if ( v24 < 0x1000 )
    {
      v25 = (void *)*a1;
    }
    else
    {
      v25 = *(void **)(v23 - 8);
      if ( (unsigned __int64)(v23 - (_QWORD)v25 - 8) > 0x1F )
        __fastfail(5u);
      v24 += 39LL;
    }
    operator delete(v25, v24);
  }
  *a1 = v14;
  a1[1] = &v14[8 * v8];
  a1[2] = (char *)v14 + v11;
  std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::_Reallocation_guard::~_Reallocation_guard(&v27);
  return (char *)&v14[8 * v16];
}

```

## disassembly

```asm
0x18001ceb8  mov     [rsp+arg_8], rbx
0x18001cebd  mov     [rsp+arg_10], r8
0x18001cec2  push    rbp
0x18001cec3  push    rsi
0x18001cec4  push    rdi
0x18001cec5  push    r12
0x18001cec7  push    r13
0x18001cec9  push    r14
0x18001cecb  push    r15
0x18001cecd  sub     rsp, 50h
0x18001ced1  mov     r13, rdx
0x18001ced4  mov     rsi, rcx
0x18001ced7  mov     rbx, [rcx]
0x18001ceda  mov     rax, [rcx+8]
0x18001cede  sub     rax, rbx
0x18001cee1  sar     rax, 6
0x18001cee5  mov     rbp, 3FFFFFFFFFFFFFFh
0x18001ceef  cmp     rax, rbp
0x18001cef2  jz      loc_18001D0CA
0x18001cef8  lea     r15, [rax+1]
0x18001cefc  mov     rcx, [rcx+10h]
0x18001cf00  sub     rcx, rbx
0x18001cf03  sar     rcx, 6
0x18001cf07  mov     rdx, rcx
0x18001cf0a  shr     rdx, 1
0x18001cf0d  mov     rax, rbp
0x18001cf10  sub     rax, rdx
0x18001cf13  cmp     rcx, rax
0x18001cf16  jbe     short loc_18001CF25
0x18001cf18  mov     rcx, 0FFFFFFFFFFFFFFE7h
0x18001cf1f  lea     r14, [rcx-27h]
0x18001cf23  jmp     short loc_18001CF65
0x18001cf25  lea     rax, [rcx+rdx]
0x18001cf29  mov     rcx, r15
0x18001cf2c  cmp     rax, r15
0x18001cf2f  cmovnb  rcx, rax
0x18001cf33  cmp     rcx, rbp
0x18001cf36  ja      loc_18001D0D0
0x18001cf3c  mov     r14, rcx
0x18001cf3f  shl     r14, 6
0x18001cf43  mov     rbp, rcx
0x18001cf46  test    r14, r14
0x18001cf49  jnz     short loc_18001CF4F
0x18001cf4b  xor     edi, edi
0x18001cf4d  jmp     short loc_18001CF8D
0x18001cf4f  cmp     r14, 1000h
0x18001cf56  jb      short loc_18001CF82
0x18001cf58  lea     rcx, [r14+27h]; Size
0x18001cf5c  cmp     rcx, r14
0x18001cf5f  jbe     loc_18001D0D0
0x18001cf65  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001cf6a  test    rax, rax
0x18001cf6d  jnz     short loc_18001CF74
0x18001cf6f  lea     ecx, [rax+5]
0x18001cf72  int     29h; Win8: RtlFailFast(ecx)
0x18001cf74  lea     rdi, [rax+27h]
0x18001cf78  and     rdi, 0FFFFFFFFFFFFFFE0h
0x18001cf7c  mov     [rdi-8], rax
0x18001cf80  jmp     short loc_18001CF8D
0x18001cf82  mov     rcx, r14; Size
0x18001cf85  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001cf8a  mov     rdi, rax
0x18001cf8d  mov     r12, r13
0x18001cf90  sub     r12, rbx
0x18001cf93  sar     r12, 6
0x18001cf97  mov     rbx, r12
0x18001cf9a  shl     rbx, 6
0x18001cf9e  add     rbx, rdi
0x18001cfa1  lea     rax, [rbx+40h]
0x18001cfa5  mov     [rsp+88h+var_68], rsi
0x18001cfaa  mov     [rsp+88h+var_60], rdi
0x18001cfaf  mov     [rsp+88h+var_58], rbp
0x18001cfb4  mov     [rsp+88h+var_50], rax
0x18001cfb9  mov     [rsp+88h+var_48], rax
0x18001cfbe  mov     [rsp+88h+arg_0], rbx
0x18001cfc6  mov     rbp, [rsp+88h+arg_10]
0x18001cfce  mov     rdx, rbp
0x18001cfd1  mov     rcx, rbx
0x18001cfd4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001cfd9  nop
0x18001cfda  lea     rdx, [rbp+20h]
0x18001cfde  lea     rcx, [rbx+20h]
0x18001cfe2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001cfe7  nop
0x18001cfe8  mov     [rsp+88h+var_50], rbx
0x18001cfed  mov     rdx, [rsi+8]
0x18001cff1  mov     r8, rdi
0x18001cff4  mov     rcx, [rsi]
0x18001cff7  cmp     r13, rdx
0x18001cffa  jz      short loc_18001D014
0x18001cffc  mov     rdx, r13
0x18001cfff  call    ??$_Uninitialized_move@PEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAPEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU1234@0PEAU1234@AEAV?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@@Z; std::_Uninitialized_move<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping> &)
0x18001d004  mov     [rsp+88h+var_50], rdi
0x18001d009  lea     r8, [rbx+40h]
0x18001d00d  mov     rdx, [rsi+8]
0x18001d011  mov     rcx, r13
0x18001d014  call    ??$_Uninitialized_move@PEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAPEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU1234@0PEAU1234@AEAV?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@@Z; std::_Uninitialized_move<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping> &)
0x18001d019  mov     [rsp+88h+var_60], 0
0x18001d022  mov     rbx, [rsi]
0x18001d025  test    rbx, rbx
0x18001d028  jz      short loc_18001D087
0x18001d02a  mov     rbp, [rsi+8]
0x18001d02e  jmp     short loc_18001D045
0x18001d030  lea     rcx, [rbx+20h]
0x18001d034  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d039  mov     rcx, rbx
0x18001d03c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d041  add     rbx, 40h ; '@'
0x18001d045  cmp     rbx, rbp
0x18001d048  jnz     short loc_18001D030
0x18001d04a  mov     rax, [rsi]
0x18001d04d  mov     rdx, [rsi+10h]
0x18001d051  sub     rdx, rax
0x18001d054  and     rdx, 0FFFFFFFFFFFFFFC0h; unsigned __int64
0x18001d058  cmp     rdx, 1000h
0x18001d05f  jb      short loc_18001D07F
0x18001d061  mov     rcx, [rax-8]
0x18001d065  sub     rax, rcx
0x18001d068  sub     rax, 8
0x18001d06c  cmp     rax, 1Fh
0x18001d070  ja      short loc_18001D078
0x18001d072  add     rdx, 27h ; '''
0x18001d076  jmp     short loc_18001D082
0x18001d078  mov     ecx, 5
0x18001d07d  int     29h; Win8: RtlFailFast(ecx)
0x18001d07f  mov     rcx, rax; void *
0x18001d082  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001d087  mov     [rsi], rdi
0x18001d08a  shl     r15, 6
0x18001d08e  add     r15, rdi
0x18001d091  mov     [rsi+8], r15
0x18001d095  lea     rax, [r14+rdi]
0x18001d099  mov     [rsi+10h], rax
0x18001d09d  shl     r12, 6
0x18001d0a1  lea     rbx, [r12+rdi]
0x18001d0a5  lea     rcx, [rsp+88h+var_68]
0x18001d0aa  call    ??1_Reallocation_guard@?$vector@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@QEAA@XZ; std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::_Reallocation_guard::~_Reallocation_guard(void)
0x18001d0af  mov     rax, rbx
0x18001d0b2  mov     rbx, [rsp+88h+arg_8]
0x18001d0ba  add     rsp, 50h
0x18001d0be  pop     r15
0x18001d0c0  pop     r14
0x18001d0c2  pop     r13
0x18001d0c4  pop     r12
0x18001d0c6  pop     rdi
0x18001d0c7  pop     rsi
0x18001d0c8  pop     rbp
0x18001d0c9  retn
0x18001d0ca  call    ?_Xlength@?$vector@IV?$allocator@I@std@@@std@@CAXXZ; std::vector<uint>::_Xlength(void)
0x18001d0d0  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
