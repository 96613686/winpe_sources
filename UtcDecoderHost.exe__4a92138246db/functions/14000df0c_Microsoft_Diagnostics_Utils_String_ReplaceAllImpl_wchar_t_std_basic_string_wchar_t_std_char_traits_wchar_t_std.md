# Microsoft::Diagnostics::Utils::String::ReplaceAllImpl<wchar_t>(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,bool)

- ea: `0x14000df0c`
- end: `0x14000e1a7`
- name: `??$ReplaceAllImpl@_W@String@Utils@Diagnostics@Microsoft@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@5@1_N@Z`
- size: `667`
- prototype: `__int64 __fastcall(_QWORD *Src, __int64, char **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14001071c`

## callees

- `0x140009527`
- `0x140009533`
- `0x14000c434`
- `0x14000df0c`
- `0x14000f014`
- `0x140010ef4`
- `0x140011724`

## pseudocode

```c
__int64 __fastcall Microsoft::Diagnostics::Utils::String::ReplaceAllImpl<wchar_t>(_QWORD *Src, __int64 a2, char **a3)
{
  char **v3; // rdi
  __int64 v4; // rbx
  __int64 result; // rax
  unsigned __int64 v7; // rax
  __int64 v8; // r8
  const char *v9; // r9
  unsigned __int64 v10; // r14
  unsigned __int64 v11; // rcx
  char *v12; // r13
  unsigned __int64 v13; // r12
  unsigned __int64 v14; // r15
  _QWORD *v15; // rax
  _QWORD *v16; // rax
  char *v17; // rdi
  unsigned __int64 v18; // rdx
  char *v19; // r8
  unsigned __int64 v20; // r10
  unsigned __int64 v21; // r9
  __int64 v22; // rdi
  int v23; // [rsp+20h] [rbp-88h]
  unsigned __int64 v24; // [rsp+40h] [rbp-68h]
  unsigned __int64 v25; // [rsp+50h] [rbp-58h]
  char *v26; // [rsp+50h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v3 = a3;
  v4 = a2;
  if ( !*(_QWORD *)(a2 + 8) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x447,
      (unsigned int)"onecore\\base\\telemetry\\utc\\include\\StringUtils.h",
      (const char *)0x80004005LL,
      v23);
    return 2147500037LL;
  }
  try
  {
    while ( 1 )
    {
      while ( 1 )
      {
        v7 = Microsoft::Diagnostics::Utils::String::IFindSequence();
        v10 = v7;
        if ( v7 == -1 )
          return 0;
        v11 = Src[2];
        if ( v11 < v7 )
          std::_String_val<std::_Simple_types<wchar_t>>::_Xran();
        v12 = *v3;
        v13 = (unsigned __int64)v3[1];
        v14 = v11 - v7;
        if ( v11 - v7 >= *(_QWORD *)(v4 + 8) )
          v14 = *(_QWORD *)(v4 + 8);
        if ( v14 != v13 )
          break;
        if ( Src[3] <= 7u )
          v15 = Src;
        else
          v15 = (_QWORD *)*Src;
        memmove_0((char *)v15 + 2 * v10, *v3, 2 * v13);
      }
      v25 = v11 - v14;
      v24 = v11 - v14 - v7;
      if ( v13 < v14 )
        break;
      v18 = v13 - v14;
      if ( v13 - v14 > Src[3] - v11 )
      {
        ____Reallocate_grow_by_V_lambda_1___1_____Replace__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV23__K_KQEB_W0_Z__K_KPEB_W_K___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1_____Replace__W_01_AEAAAEAV01_0_KQEB_W0_Z_11PEB_W1_Z(
          (void **)Src,
          v18,
          v8,
          v7,
          v14,
          v12,
          v13);
      }
      else
      {
        Src[2] = v11 + v18;
        if ( Src[3] <= 7u )
          v19 = (char *)Src;
        else
          v19 = (char *)*Src;
        v20 = (unsigned __int64)&v19[2 * v7];
        v26 = (char *)v20;
        v21 = v20 + 2 * v14;
        if ( (unsigned __int64)&v12[2 * v13] <= v20 || v12 > &v19[2 * v11] )
        {
          v22 = v13;
        }
        else if ( v21 > (unsigned __int64)v12 )
        {
          v22 = (__int64)(v21 - (_QWORD)v12) >> 1;
        }
        else
        {
          v22 = 0;
        }
        memmove_0((void *)(v21 + 2 * v18), (const void *)(v20 + 2 * v14), 2 * (v11 - v14 - v7) + 2);
        memmove_0(v26, v12, 2 * v22);
        memcpy_0(&v26[2 * v22], &v12[2 * v22 + 2 * (v13 - v14)], 2 * (v13 - v22));
LABEL_17:
        v4 = a2;
        v3 = a3;
      }
    }
    if ( Src[3] <= 7u )
      v16 = Src;
    else
      v16 = (_QWORD *)*Src;
    v17 = (char *)v16 + 2 * v10;
    memmove_0(v17, v12, 2 * v13);
    memmove_0(&v17[2 * v13], &v17[2 * v14], 2 * v24 + 2);
    Src[2] = v13 + v25;
    goto LABEL_17;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x45C,
                           (unsigned int)"onecore\\base\\telemetry\\utc\\include\\StringUtils.h",
                           v9);
  }
  return result;
}

```

## disassembly

```asm
0x14000df0c  mov     byte ptr [rsp+arg_18], r9b
0x14000df11  mov     [rsp+arg_10], r8
0x14000df16  mov     [rsp+arg_8], rdx
0x14000df1b  push    rbx
0x14000df1c  push    rsi
0x14000df1d  push    rdi
0x14000df1e  push    r12
0x14000df20  push    r13
0x14000df22  push    r14
0x14000df24  push    r15
0x14000df26  sub     rsp, 70h
0x14000df2a  mov     rdi, r8
0x14000df2d  mov     rbx, rdx
0x14000df30  mov     rsi, rcx
0x14000df33  cmp     qword ptr [rdx+8], 0
0x14000df38  jnz     short loc_14000DF62
0x14000df3a  mov     rcx, [rsp+0A8h]; this
0x14000df42  mov     ebx, 80004005h
0x14000df47  mov     r9d, ebx; char *
0x14000df4a  lea     r8, aOnecoreBaseTel_0; "onecore\\base\\telemetry\\utc\\include"...
0x14000df51  mov     edx, 447h; void *
0x14000df56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000df5b  mov     eax, ebx
0x14000df5d  jmp     loc_14000E190
0x14000df62  cmp     qword ptr [rcx+18h], 7
0x14000df67  jbe     short loc_14000DF6E
0x14000df69  mov     rax, [rcx]
0x14000df6c  jmp     short loc_14000DF71
0x14000df6e  mov     rax, rsi
0x14000df71  movaps  xmm0, xmmword ptr [rdx]
0x14000df74  movdqa  [rsp+0A8h+var_48], xmm0
0x14000df7a  mov     [rsp+0A8h+var_58], rax
0x14000df7f  mov     rax, [rcx+10h]
0x14000df83  mov     [rsp+0A8h+var_58+8], rax
0x14000df88  xor     r8d, r8d
0x14000df8b  lea     rdx, [rsp+0A8h+var_48]
0x14000df90  lea     rcx, [rsp+0A8h+var_58]
0x14000df95  call    ?IFindSequence@String@Utils@Diagnostics@Microsoft@@SA_KV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0_K@Z; Microsoft::Diagnostics::Utils::String::IFindSequence(std::wstring_view,std::wstring_view,unsigned __int64)
0x14000df9a  mov     r14, rax
0x14000df9d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000dfa1  jz      loc_14000E185
0x14000dfa7  mov     rcx, [rsi+10h]
0x14000dfab  cmp     rcx, rax
0x14000dfae  jb      loc_14000E1A0
0x14000dfb4  mov     r13, [rdi]
0x14000dfb7  mov     r12, [rdi+8]
0x14000dfbb  mov     r15, rcx
0x14000dfbe  sub     r15, r14
0x14000dfc1  cmp     r15, [rbx+8]
0x14000dfc5  cmovnb  r15, [rbx+8]
0x14000dfca  cmp     r15, r12
0x14000dfcd  jnz     short loc_14000DFF3
0x14000dfcf  cmp     qword ptr [rsi+18h], 7
0x14000dfd4  jbe     short loc_14000DFDB
0x14000dfd6  mov     rax, [rsi]
0x14000dfd9  jmp     short loc_14000DFDE
0x14000dfdb  mov     rax, rsi
0x14000dfde  lea     r8, [r12+r12]; Size
0x14000dfe2  lea     rcx, [rax+r14*2]; void *
0x14000dfe6  mov     rdx, r13; Src
0x14000dfe9  call    memmove_0
0x14000dfee  jmp     loc_14000E14C
0x14000dff3  mov     rax, rcx
0x14000dff6  sub     rax, r15
0x14000dff9  mov     [rsp+0A8h+var_58], rax
0x14000dffe  mov     r11, rax
0x14000e001  sub     r11, r14
0x14000e004  mov     [rsp+0A8h+var_68], r11
0x14000e009  cmp     r12, r15
0x14000e00c  jnb     short loc_14000E06E
0x14000e00e  cmp     qword ptr [rsi+18h], 7
0x14000e013  jbe     short loc_14000E01A
0x14000e015  mov     rax, [rsi]
0x14000e018  jmp     short loc_14000E01D
0x14000e01a  mov     rax, rsi
0x14000e01d  lea     rdi, [rax+r14*2]
0x14000e021  lea     rbx, [r12+r12]
0x14000e025  mov     r8, rbx; Size
0x14000e028  mov     rdx, r13; Src
0x14000e02b  mov     rcx, rdi; void *
0x14000e02e  call    memmove_0
0x14000e033  mov     r8, [rsp+0A8h+var_68]
0x14000e038  lea     r8, ds:2[r8*2]; Size
0x14000e040  lea     rdx, [rdi+r15*2]; Src
0x14000e044  lea     rcx, [rdi+rbx]; void *
0x14000e048  call    memmove_0
0x14000e04d  mov     rax, [rsp+0A8h+var_58]
0x14000e052  add     rax, r12
0x14000e055  mov     [rsi+10h], rax
0x14000e059  mov     rbx, [rsp+0A8h+arg_8]
0x14000e061  mov     rdi, [rsp+0A8h+arg_10]
0x14000e069  jmp     loc_14000E14C
0x14000e06e  mov     rdx, r12
0x14000e071  sub     rdx, r15
0x14000e074  mov     [rsp+0A8h+var_68], rdx
0x14000e079  mov     rax, [rsi+18h]
0x14000e07d  sub     rax, rcx
0x14000e080  cmp     rdx, rax
0x14000e083  ja      loc_14000E132
0x14000e089  lea     rax, [rcx+rdx]
0x14000e08d  mov     [rsi+10h], rax
0x14000e091  cmp     qword ptr [rsi+18h], 7
0x14000e096  jbe     short loc_14000E09D
0x14000e098  mov     r8, [rsi]
0x14000e09b  jmp     short loc_14000E0A0
0x14000e09d  mov     r8, rsi
0x14000e0a0  lea     r10, [r8+r14*2]
0x14000e0a4  mov     [rsp+0A8h+var_58], r10
0x14000e0a9  lea     r9, [r10+r15*2]
0x14000e0ad  lea     rax, ds:0[r12*2]
0x14000e0b5  add     rax, r13
0x14000e0b8  cmp     rax, r10
0x14000e0bb  jbe     short loc_14000E0DA
0x14000e0bd  lea     rax, [r8+rcx*2]
0x14000e0c1  cmp     r13, rax
0x14000e0c4  ja      short loc_14000E0DA
0x14000e0c6  cmp     r9, r13
0x14000e0c9  ja      short loc_14000E0CF
0x14000e0cb  xor     edi, edi
0x14000e0cd  jmp     short loc_14000E0DD
0x14000e0cf  mov     rdi, r9
0x14000e0d2  sub     rdi, r13
0x14000e0d5  sar     rdi, 1
0x14000e0d8  jmp     short loc_14000E0DD
0x14000e0da  mov     rdi, r12
0x14000e0dd  lea     r8, ds:2[r11*2]; Size
0x14000e0e5  lea     rcx, [r9+rdx*2]; void *
0x14000e0e9  mov     rdx, r9; Src
0x14000e0ec  call    memmove_0
0x14000e0f1  lea     rbx, [rdi+rdi]
0x14000e0f5  mov     r8, rbx; Size
0x14000e0f8  mov     rdx, r13; Src
0x14000e0fb  mov     r15, [rsp+0A8h+var_58]
0x14000e100  mov     rcx, r15; void *
0x14000e103  call    memmove_0
0x14000e108  mov     r8, r12
0x14000e10b  sub     r8, rdi
0x14000e10e  add     r8, r8; Size
0x14000e111  mov     rax, [rsp+0A8h+var_68]
0x14000e116  add     rax, rdi
0x14000e119  lea     rdx, ds:0[rax*2]
0x14000e121  add     rdx, r13; Src
0x14000e124  lea     rcx, [rbx+r15]; void *
0x14000e128  call    memcpy_0
0x14000e12d  jmp     loc_14000E059
0x14000e132  mov     [rsp+0A8h+var_78], r12; __int64
0x14000e137  mov     [rsp+0A8h+var_80], r13; void *
0x14000e13c  mov     [rsp+0A8h+var_88], r15; __int64
0x14000e141  mov     r9, r14
0x14000e144  mov     rcx, rsi; Src
0x14000e147  call    ??$_Reallocate_grow_by@V_lambda_1_@?1???$_Replace@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV23@_K_KQEB_W0@Z@_K_KPEB_W_K@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Replace@_W@01@AEAAAEAV01@0_KQEB_W0@Z@11PEB_W1@Z; std::wstring::_Reallocate_grow_by<`std::wstring::_Replace<wchar_t>(unsigned __int64,unsigned __int64,wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,unsigned __int64,unsigned __int64,wchar_t const *,unsigned __int64>(unsigned __int64,`std::wstring::_Replace<wchar_t>(unsigned __int64,unsigned __int64,wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,unsigned __int64,unsigned __int64,wchar_t const *,unsigned __int64)
0x14000e14c  lea     r8, [r12+r14]
0x14000e150  cmp     qword ptr [rsi+18h], 7
0x14000e155  jbe     short loc_14000E15C
0x14000e157  mov     rax, [rsi]
0x14000e15a  jmp     short loc_14000E15F
0x14000e15c  mov     rax, rsi
0x14000e15f  movaps  xmm0, xmmword ptr [rbx]
0x14000e162  movdqa  xmmword ptr [rsp+0A8h+var_58], xmm0
0x14000e168  mov     qword ptr [rsp+0A8h+var_48], rax
0x14000e16d  mov     rax, [rsi+10h]
0x14000e171  mov     qword ptr [rsp+0A8h+var_48+8], rax
0x14000e176  lea     rdx, [rsp+0A8h+var_58]
0x14000e17b  lea     rcx, [rsp+0A8h+var_48]
0x14000e180  jmp     loc_14000DF95
0x14000e185  xor     eax, eax
0x14000e187  jmp     short loc_14000E190
0x14000e189  mov     eax, [rsp+0A8h+arg_18]
0x14000e190  add     rsp, 70h
0x14000e194  pop     r15
0x14000e196  pop     r14
0x14000e198  pop     r13
0x14000e19a  pop     r12
0x14000e19c  pop     rdi
0x14000e19d  pop     rsi
0x14000e19e  pop     rbx
0x14000e19f  retn
0x14000e1a0  call    ?_Xran@?$_String_val@U?$_Simple_types@_W@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Xran(void)
```
