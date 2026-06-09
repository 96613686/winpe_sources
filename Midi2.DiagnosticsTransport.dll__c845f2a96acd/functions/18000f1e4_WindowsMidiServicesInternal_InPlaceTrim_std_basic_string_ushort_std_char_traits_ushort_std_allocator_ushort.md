# WindowsMidiServicesInternal::InPlaceTrim(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18000f1e4`
- end: `0x18000f4e7`
- name: `?InPlaceTrim@WindowsMidiServicesInternal@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `771`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x18000cb4c`

## callees

- `0x180002e90`
- `0x180002fb0`
- `0x1800033d0`
- `0x180004164`
- `0x180004170`
- `0x18000b7fc`
- `0x18000c4c0`
- `0x18000c5cc`
- `0x18000f1e4`
- `0x18001096c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WindowsMidiServicesInternal::InPlaceTrim(wchar_t *Src)
{
  char v2; // r13
  const wchar_t *v3; // r12
  __int64 v4; // rcx
  wchar_t *v5; // r14
  __int64 last_not_of_trivial_pos_2; // rsi
  size_t v7; // r13
  unsigned __int64 first_not_of_trivial_pos_2; // rdi
  wchar_t *v9; // r15
  const wchar_t *v10; // rcx
  const wchar_t *v11; // rdx
  wchar_t *v12; // rdi
  unsigned __int64 v13; // r14
  unsigned __int64 v14; // rax
  wchar_t *v15; // rcx
  unsigned __int64 v16; // r14
  const wchar_t *v17; // r15
  __int64 v18; // rax
  wchar_t *v19; // r14
  size_t v20; // r12
  __int64 v21; // rdi
  const wchar_t *v22; // rcx
  const wchar_t *v23; // rdx
  wchar_t *v24; // rdi
  unsigned __int64 v25; // rsi
  unsigned __int64 v26; // rcx
  wchar_t *v27; // rdi
  __int64 i; // rcx
  _BYTE v30[256]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t *S[2]; // [rsp+130h] [rbp+30h] BYREF
  size_t N; // [rsp+140h] [rbp+40h]
  unsigned __int64 v33; // [rsp+148h] [rbp+48h]

  *(_OWORD *)S = 0;
  N = 0;
  v33 = 0;
  v2 = 1;
  std::wstring::_Construct<1,unsigned short const *>(S, L" ", 1);
  v3 = (const wchar_t *)S;
  if ( v33 > 7 )
    v3 = S[0];
  v4 = *((_QWORD *)Src + 2);
  if ( *((_QWORD *)Src + 3) <= 7u )
    v5 = Src;
  else
    v5 = *(wchar_t **)Src;
  last_not_of_trivial_pos_2 = -1;
  if ( v4 )
  {
    v7 = N;
    if ( v4 + N < 0x10 )
    {
      v9 = &v5[v4];
      memset_0(v30, 0, sizeof(v30));
      v10 = v3;
      v11 = &v3[v7];
      if ( v3 == v11 )
      {
LABEL_12:
        v12 = v5;
        if ( v5 >= v9 )
        {
LABEL_29:
          v2 = 1;
          goto LABEL_30;
        }
        while ( *v12 < 0x100u && v30[*v12] )
        {
          if ( ++v12 >= v9 )
            goto LABEL_29;
        }
      }
      else
      {
        while ( *v10 < 0x100u )
        {
          v30[*(unsigned __int8 *)v10++] = 1;
          if ( v10 == v11 )
            goto LABEL_12;
        }
        v12 = v5;
        if ( v5 >= v9 )
          goto LABEL_29;
        while ( wmemchr(v3, *v12, v7) )
        {
          if ( ++v12 >= v9 )
            goto LABEL_29;
        }
      }
      first_not_of_trivial_pos_2 = v12 - v5;
    }
    else
    {
      first_not_of_trivial_pos_2 = _std_find_first_not_of_trivial_pos_2(v5, *((_QWORD *)Src + 2), v3, N);
    }
    if ( first_not_of_trivial_pos_2 != -1 )
    {
      v13 = *((_QWORD *)Src + 2);
      v14 = v13;
      if ( v13 >= first_not_of_trivial_pos_2 )
        v14 = first_not_of_trivial_pos_2;
      if ( *((_QWORD *)Src + 3) <= 7u )
        v15 = Src;
      else
        v15 = *(wchar_t **)Src;
      v16 = v13 - v14;
      memmove_0(v15, &v15[v14], 2 * v16 + 2);
      *((_QWORD *)Src + 2) = v16;
    }
    goto LABEL_29;
  }
LABEL_30:
  v17 = (const wchar_t *)S;
  if ( v33 > 7 )
    v17 = S[0];
  v18 = *((_QWORD *)Src + 2);
  if ( *((_QWORD *)Src + 3) <= 7u )
    v19 = Src;
  else
    v19 = *(wchar_t **)Src;
  if ( v18 )
  {
    v20 = N;
    v21 = v18 - 1;
    if ( N + v18 < 0x10 )
    {
      memset_0(v30, 0, sizeof(v30));
      v22 = v17;
      v23 = &v17[v20];
      if ( v17 != v23 )
      {
        while ( *v22 < 0x100u )
        {
          v30[*(unsigned __int8 *)v22++] = 1;
          if ( v22 == v23 )
            goto LABEL_43;
        }
        v2 = 0;
      }
LABEL_43:
      v24 = &v19[v21];
      if ( v2 )
      {
        while ( *v24 < 0x100u && v30[*v24] )
        {
          if ( v24 == v19 )
            goto LABEL_52;
          --v24;
        }
      }
      else
      {
        while ( wmemchr(v17, *v24, v20) )
        {
          if ( v24 == v19 )
            goto LABEL_52;
          --v24;
        }
      }
      last_not_of_trivial_pos_2 = v24 - v19;
    }
    else
    {
      last_not_of_trivial_pos_2 = _std_find_last_not_of_trivial_pos_2(v19, v18, v17, N);
    }
  }
LABEL_52:
  v25 = last_not_of_trivial_pos_2 + 1;
  v26 = *((_QWORD *)Src + 2);
  if ( v25 > v26 )
  {
    if ( v25 - v26 > *((_QWORD *)Src + 3) - v26 )
    {
      ____Reallocate_grow_by_V_lambda_1___1__append___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAAEAV34__KG_Z__KG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__append_01_QEAAAEAV01_0G_Z__KG_Z(Src);
      return std::wstring::~wstring(S);
    }
    *((_QWORD *)Src + 2) = v25;
    if ( *((_QWORD *)Src + 3) > 7u )
      Src = *(wchar_t **)Src;
    v27 = &Src[v26];
    if ( v25 != v26 )
    {
      for ( i = v25 - v26; i; --i )
        *v27++ = 0;
    }
  }
  else
  {
    *((_QWORD *)Src + 2) = v25;
    if ( *((_QWORD *)Src + 3) > 7u )
      Src = *(wchar_t **)Src;
  }
  Src[v25] = 0;
  return std::wstring::~wstring(S);
}

```

## disassembly

```asm
0x18000f1e4  push    rbp
0x18000f1e6  push    rbx
0x18000f1e7  push    rsi
0x18000f1e8  push    rdi
0x18000f1e9  push    r12
0x18000f1eb  push    r13
0x18000f1ed  push    r14
0x18000f1ef  push    r15
0x18000f1f1  lea     rbp, [rsp-68h]
0x18000f1f6  sub     rsp, 168h
0x18000f1fd  mov     rax, cs:__security_cookie
0x18000f204  xor     rax, rsp
0x18000f207  mov     [rbp+0A0h+var_50], rax
0x18000f20b  mov     rbx, rcx
0x18000f20e  xorps   xmm0, xmm0
0x18000f211  movups  xmmword ptr [rbp+0A0h+S], xmm0
0x18000f215  mov     [rbp+0A0h+N], 0
0x18000f21d  mov     [rbp+0A0h+var_58], 0
0x18000f225  mov     r13d, 1
0x18000f22b  mov     r8d, r13d
0x18000f22e  lea     rdx, asc_180015B78; " "
0x18000f235  lea     rcx, [rbp+0A0h+S]
0x18000f239  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000f23e  nop
0x18000f23f  lea     r12, [rbp+0A0h+S]
0x18000f243  cmp     [rbp+0A0h+var_58], 7
0x18000f248  cmova   r12, [rbp+0A0h+S]
0x18000f24d  mov     rcx, [rbx+10h]
0x18000f251  cmp     qword ptr [rbx+18h], 7
0x18000f256  jbe     short loc_18000F25D
0x18000f258  mov     r14, [rbx]
0x18000f25b  jmp     short loc_18000F260
0x18000f25d  mov     r14, rbx
0x18000f260  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000f264  mov     r8d, 100h; Size
0x18000f26a  test    rcx, rcx
0x18000f26d  jz      loc_18000F378
0x18000f273  mov     r13, [rbp+0A0h+N]
0x18000f277  lea     rax, [rcx+r13]
0x18000f27b  cmp     rax, 10h
0x18000f27f  jb      short loc_18000F2A0
0x18000f281  mov     r9, r13
0x18000f284  mov     r8, r12
0x18000f287  mov     rdx, rcx
0x18000f28a  mov     rcx, r14
0x18000f28d  call    __std_find_first_not_of_trivial_pos_2
0x18000f292  mov     rdi, rax
0x18000f295  mov     r8d, 100h
0x18000f29b  jmp     loc_18000F332
0x18000f2a0  lea     r15, [r14+rcx*2]
0x18000f2a4  xor     edx, edx; Val
0x18000f2a6  lea     rcx, [rsp+1A0h+var_170]; void *
0x18000f2ab  call    memset_0
0x18000f2b0  mov     rcx, r12
0x18000f2b3  lea     rdx, [r12+r13*2]
0x18000f2b7  mov     r8d, 100h
0x18000f2bd  cmp     r12, rdx
0x18000f2c0  jz      short loc_18000F2D9
0x18000f2c2  cmp     [rcx], r8w
0x18000f2c6  jnb     short loc_18000F300
0x18000f2c8  movzx   eax, byte ptr [rcx]
0x18000f2cb  mov     [rsp+rax+1A0h+var_170], 1
0x18000f2d0  add     rcx, 2
0x18000f2d4  cmp     rcx, rdx
0x18000f2d7  jnz     short loc_18000F2C2
0x18000f2d9  mov     rdi, r14
0x18000f2dc  cmp     r14, r15
0x18000f2df  jnb     loc_18000F372
0x18000f2e5  cmp     [rdi], r8w
0x18000f2e9  jnb     short loc_18000F32C
0x18000f2eb  movzx   eax, word ptr [rdi]
0x18000f2ee  cmp     [rsp+rax+1A0h+var_170], 0
0x18000f2f3  jz      short loc_18000F32C
0x18000f2f5  add     rdi, 2
0x18000f2f9  cmp     rdi, r15
0x18000f2fc  jb      short loc_18000F2E5
0x18000f2fe  jmp     short loc_18000F372
0x18000f300  mov     rdi, r14
0x18000f303  cmp     r14, r15
0x18000f306  jnb     short loc_18000F372
0x18000f308  mov     r8, r13; N
0x18000f30b  movzx   edx, word ptr [rdi]; C
0x18000f30e  mov     rcx, r12; S
0x18000f311  call    wmemchr
0x18000f316  test    rax, rax
0x18000f319  jz      short loc_18000F326
0x18000f31b  add     rdi, 2
0x18000f31f  cmp     rdi, r15
0x18000f322  jb      short loc_18000F308
0x18000f324  jmp     short loc_18000F36C
0x18000f326  mov     r8d, 100h
0x18000f32c  sub     rdi, r14
0x18000f32f  sar     rdi, 1
0x18000f332  cmp     rdi, rsi
0x18000f335  jz      short loc_18000F372
0x18000f337  mov     r14, [rbx+10h]
0x18000f33b  mov     rax, r14
0x18000f33e  cmp     r14, rdi
0x18000f341  cmovnb  rax, rdi
0x18000f345  cmp     qword ptr [rbx+18h], 7
0x18000f34a  jbe     short loc_18000F351
0x18000f34c  mov     rcx, [rbx]
0x18000f34f  jmp     short loc_18000F354
0x18000f351  mov     rcx, rbx; void *
0x18000f354  sub     r14, rax
0x18000f357  lea     r8, ds:2[r14*2]; Size
0x18000f35f  lea     rdx, [rcx+rax*2]; Src
0x18000f363  call    memmove_0
0x18000f368  mov     [rbx+10h], r14
0x18000f36c  mov     r8d, 100h; Size
0x18000f372  mov     r13d, 1
0x18000f378  lea     r15, [rbp+0A0h+S]
0x18000f37c  cmp     [rbp+0A0h+var_58], 7
0x18000f381  cmova   r15, [rbp+0A0h+S]
0x18000f386  mov     rax, [rbx+10h]
0x18000f38a  cmp     qword ptr [rbx+18h], 7
0x18000f38f  jbe     short loc_18000F396
0x18000f391  mov     r14, [rbx]
0x18000f394  jmp     short loc_18000F399
0x18000f396  mov     r14, rbx
0x18000f399  test    rax, rax
0x18000f39c  jz      loc_18000F45A
0x18000f3a2  mov     r12, [rbp+0A0h+N]
0x18000f3a6  lea     rdi, [rax-1]
0x18000f3aa  cmp     rdi, rsi
0x18000f3ad  cmovnb  rdi, rsi
0x18000f3b1  lea     rdx, [rdi+1]
0x18000f3b5  lea     rax, [r12+rdx]
0x18000f3b9  cmp     rax, 10h
0x18000f3bd  jb      short loc_18000F3D5
0x18000f3bf  mov     r9, r12
0x18000f3c2  mov     r8, r15
0x18000f3c5  mov     rcx, r14
0x18000f3c8  call    __std_find_last_not_of_trivial_pos_2
0x18000f3cd  mov     rsi, rax
0x18000f3d0  jmp     loc_18000F45A
0x18000f3d5  xor     edx, edx; Val
0x18000f3d7  lea     rcx, [rsp+1A0h+var_170]; void *
0x18000f3dc  call    memset_0
0x18000f3e1  mov     rcx, r15
0x18000f3e4  lea     rdx, [r15+r12*2]
0x18000f3e8  mov     r8d, 100h
0x18000f3ee  cmp     r15, rdx
0x18000f3f1  jz      short loc_18000F40F
0x18000f3f3  cmp     [rcx], r8w
0x18000f3f7  jnb     short loc_18000F40C
0x18000f3f9  movzx   eax, byte ptr [rcx]
0x18000f3fc  mov     [rsp+rax+1A0h+var_170], r13b
0x18000f401  add     rcx, 2
0x18000f405  cmp     rcx, rdx
0x18000f408  jnz     short loc_18000F3F3
0x18000f40a  jmp     short loc_18000F40F
0x18000f40c  xor     r13b, r13b
0x18000f40f  lea     rdi, [r14+rdi*2]
0x18000f413  test    r13b, r13b
0x18000f416  jz      short loc_18000F433
0x18000f418  cmp     [rdi], r8w
0x18000f41c  jnb     short loc_18000F451
0x18000f41e  movzx   eax, word ptr [rdi]
0x18000f421  cmp     [rsp+rax+1A0h+var_170], 0
0x18000f426  jz      short loc_18000F451
0x18000f428  cmp     rdi, r14
0x18000f42b  jz      short loc_18000F45A
0x18000f42d  sub     rdi, 2
0x18000f431  jmp     short loc_18000F418
0x18000f433  mov     r8, r12; N
0x18000f436  movzx   edx, word ptr [rdi]; C
0x18000f439  mov     rcx, r15; S
0x18000f43c  call    wmemchr
0x18000f441  test    rax, rax
0x18000f444  jz      short loc_18000F451
0x18000f446  cmp     rdi, r14
0x18000f449  jz      short loc_18000F45A
0x18000f44b  sub     rdi, 2
0x18000f44f  jmp     short loc_18000F433
0x18000f451  mov     rsi, rdi
0x18000f454  sub     rsi, r14
0x18000f457  sar     rsi, 1
0x18000f45a  inc     rsi
0x18000f45d  mov     rcx, [rbx+10h]
0x18000f461  cmp     rsi, rcx
0x18000f464  ja      short loc_18000F476
0x18000f466  mov     [rbx+10h], rsi
0x18000f46a  cmp     qword ptr [rbx+18h], 7
0x18000f46f  jbe     short loc_18000F4AA
0x18000f471  mov     rbx, [rbx]
0x18000f474  jmp     short loc_18000F4AA
0x18000f476  mov     rdx, rsi
0x18000f479  sub     rdx, rcx
0x18000f47c  mov     rax, [rbx+18h]
0x18000f480  sub     rax, rcx
0x18000f483  cmp     rdx, rax
0x18000f486  ja      short loc_18000F4B2
0x18000f488  mov     [rbx+10h], rsi
0x18000f48c  cmp     qword ptr [rbx+18h], 7
0x18000f491  jbe     short loc_18000F496
0x18000f493  mov     rbx, [rbx]
0x18000f496  lea     rdi, [rbx+rcx*2]
0x18000f49a  test    rdx, rdx
0x18000f49d  jz      short loc_18000F4AA
0x18000f49f  xor     eax, eax
0x18000f4a1  movzx   eax, ax
0x18000f4a4  mov     rcx, rdx
0x18000f4a7  rep stosw
0x18000f4aa  xor     eax, eax
0x18000f4ac  mov     [rbx+rsi*2], ax
0x18000f4b0  jmp     short loc_18000F4BE
0x18000f4b2  mov     r9, rdx
0x18000f4b5  mov     rcx, rbx; Src
0x18000f4b8  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV34@_KG@Z@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??append@01@QEAAAEAV01@0G@Z@_KG@Z; std::wstring::_Reallocate_grow_by<`std::wstring::append(unsigned __int64,ushort)'::`2'::_lambda_1_,unsigned __int64,ushort>(unsigned __int64,`std::wstring::append(unsigned __int64,ushort)'::`2'::_lambda_1_,unsigned __int64,ushort)
0x18000f4bd  nop
0x18000f4be  lea     rcx, [rbp+0A0h+S]
0x18000f4c2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000f4c7  mov     rcx, [rbp+0A0h+var_50]
0x18000f4cb  xor     rcx, rsp; StackCookie
0x18000f4ce  call    __security_check_cookie
0x18000f4d3  add     rsp, 168h
0x18000f4da  pop     r15
0x18000f4dc  pop     r14
0x18000f4de  pop     r13
0x18000f4e0  pop     r12
0x18000f4e2  pop     rdi
0x18000f4e3  pop     rsi
0x18000f4e4  pop     rbx
0x18000f4e5  pop     rbp
0x18000f4e6  retn
```
