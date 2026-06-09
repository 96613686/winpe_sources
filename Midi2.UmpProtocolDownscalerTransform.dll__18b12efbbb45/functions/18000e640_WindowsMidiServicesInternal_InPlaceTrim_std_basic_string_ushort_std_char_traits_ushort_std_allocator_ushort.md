# WindowsMidiServicesInternal::InPlaceTrim(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18000e640`
- end: `0x18000e943`
- name: `?InPlaceTrim@WindowsMidiServicesInternal@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `771`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x18000e950`

## callees

- `0x180002930`
- `0x180002a50`
- `0x180002e70`
- `0x180003a14`
- `0x180003a20`
- `0x18000b238`
- `0x18000b770`
- `0x18000d0ac`
- `0x18000e640`
- `0x180011e2c`

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
  std::wstring::_Construct<1,unsigned short const *>(S, L" ");
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
0x18000e640  push    rbp
0x18000e642  push    rbx
0x18000e643  push    rsi
0x18000e644  push    rdi
0x18000e645  push    r12
0x18000e647  push    r13
0x18000e649  push    r14
0x18000e64b  push    r15
0x18000e64d  lea     rbp, [rsp-68h]
0x18000e652  sub     rsp, 168h
0x18000e659  mov     rax, cs:__security_cookie
0x18000e660  xor     rax, rsp
0x18000e663  mov     [rbp+0A0h+var_50], rax
0x18000e667  mov     rbx, rcx
0x18000e66a  xorps   xmm0, xmm0
0x18000e66d  movups  xmmword ptr [rbp+0A0h+S], xmm0
0x18000e671  mov     [rbp+0A0h+N], 0
0x18000e679  mov     [rbp+0A0h+var_58], 0
0x18000e681  mov     r13d, 1
0x18000e687  mov     r8d, r13d
0x18000e68a  lea     rdx, asc_1800167D0; " "
0x18000e691  lea     rcx, [rbp+0A0h+S]
0x18000e695  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000e69a  nop
0x18000e69b  lea     r12, [rbp+0A0h+S]
0x18000e69f  cmp     [rbp+0A0h+var_58], 7
0x18000e6a4  cmova   r12, [rbp+0A0h+S]
0x18000e6a9  mov     rcx, [rbx+10h]
0x18000e6ad  cmp     qword ptr [rbx+18h], 7
0x18000e6b2  jbe     short loc_18000E6B9
0x18000e6b4  mov     r14, [rbx]
0x18000e6b7  jmp     short loc_18000E6BC
0x18000e6b9  mov     r14, rbx
0x18000e6bc  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000e6c0  mov     r8d, 100h; Size
0x18000e6c6  test    rcx, rcx
0x18000e6c9  jz      loc_18000E7D4
0x18000e6cf  mov     r13, [rbp+0A0h+N]
0x18000e6d3  lea     rax, [rcx+r13]
0x18000e6d7  cmp     rax, 10h
0x18000e6db  jb      short loc_18000E6FC
0x18000e6dd  mov     r9, r13
0x18000e6e0  mov     r8, r12
0x18000e6e3  mov     rdx, rcx
0x18000e6e6  mov     rcx, r14
0x18000e6e9  call    __std_find_first_not_of_trivial_pos_2
0x18000e6ee  mov     rdi, rax
0x18000e6f1  mov     r8d, 100h
0x18000e6f7  jmp     loc_18000E78E
0x18000e6fc  lea     r15, [r14+rcx*2]
0x18000e700  xor     edx, edx; Val
0x18000e702  lea     rcx, [rsp+1A0h+var_170]; void *
0x18000e707  call    memset_0
0x18000e70c  mov     rcx, r12
0x18000e70f  lea     rdx, [r12+r13*2]
0x18000e713  mov     r8d, 100h
0x18000e719  cmp     r12, rdx
0x18000e71c  jz      short loc_18000E735
0x18000e71e  cmp     [rcx], r8w
0x18000e722  jnb     short loc_18000E75C
0x18000e724  movzx   eax, byte ptr [rcx]
0x18000e727  mov     [rsp+rax+1A0h+var_170], 1
0x18000e72c  add     rcx, 2
0x18000e730  cmp     rcx, rdx
0x18000e733  jnz     short loc_18000E71E
0x18000e735  mov     rdi, r14
0x18000e738  cmp     r14, r15
0x18000e73b  jnb     loc_18000E7CE
0x18000e741  cmp     [rdi], r8w
0x18000e745  jnb     short loc_18000E788
0x18000e747  movzx   eax, word ptr [rdi]
0x18000e74a  cmp     [rsp+rax+1A0h+var_170], 0
0x18000e74f  jz      short loc_18000E788
0x18000e751  add     rdi, 2
0x18000e755  cmp     rdi, r15
0x18000e758  jb      short loc_18000E741
0x18000e75a  jmp     short loc_18000E7CE
0x18000e75c  mov     rdi, r14
0x18000e75f  cmp     r14, r15
0x18000e762  jnb     short loc_18000E7CE
0x18000e764  mov     r8, r13; N
0x18000e767  movzx   edx, word ptr [rdi]; C
0x18000e76a  mov     rcx, r12; S
0x18000e76d  call    wmemchr
0x18000e772  test    rax, rax
0x18000e775  jz      short loc_18000E782
0x18000e777  add     rdi, 2
0x18000e77b  cmp     rdi, r15
0x18000e77e  jb      short loc_18000E764
0x18000e780  jmp     short loc_18000E7C8
0x18000e782  mov     r8d, 100h
0x18000e788  sub     rdi, r14
0x18000e78b  sar     rdi, 1
0x18000e78e  cmp     rdi, rsi
0x18000e791  jz      short loc_18000E7CE
0x18000e793  mov     r14, [rbx+10h]
0x18000e797  mov     rax, r14
0x18000e79a  cmp     r14, rdi
0x18000e79d  cmovnb  rax, rdi
0x18000e7a1  cmp     qword ptr [rbx+18h], 7
0x18000e7a6  jbe     short loc_18000E7AD
0x18000e7a8  mov     rcx, [rbx]
0x18000e7ab  jmp     short loc_18000E7B0
0x18000e7ad  mov     rcx, rbx; void *
0x18000e7b0  sub     r14, rax
0x18000e7b3  lea     r8, ds:2[r14*2]; Size
0x18000e7bb  lea     rdx, [rcx+rax*2]; Src
0x18000e7bf  call    memmove_0
0x18000e7c4  mov     [rbx+10h], r14
0x18000e7c8  mov     r8d, 100h; Size
0x18000e7ce  mov     r13d, 1
0x18000e7d4  lea     r15, [rbp+0A0h+S]
0x18000e7d8  cmp     [rbp+0A0h+var_58], 7
0x18000e7dd  cmova   r15, [rbp+0A0h+S]
0x18000e7e2  mov     rax, [rbx+10h]
0x18000e7e6  cmp     qword ptr [rbx+18h], 7
0x18000e7eb  jbe     short loc_18000E7F2
0x18000e7ed  mov     r14, [rbx]
0x18000e7f0  jmp     short loc_18000E7F5
0x18000e7f2  mov     r14, rbx
0x18000e7f5  test    rax, rax
0x18000e7f8  jz      loc_18000E8B6
0x18000e7fe  mov     r12, [rbp+0A0h+N]
0x18000e802  lea     rdi, [rax-1]
0x18000e806  cmp     rdi, rsi
0x18000e809  cmovnb  rdi, rsi
0x18000e80d  lea     rdx, [rdi+1]
0x18000e811  lea     rax, [r12+rdx]
0x18000e815  cmp     rax, 10h
0x18000e819  jb      short loc_18000E831
0x18000e81b  mov     r9, r12
0x18000e81e  mov     r8, r15
0x18000e821  mov     rcx, r14
0x18000e824  call    __std_find_last_not_of_trivial_pos_2
0x18000e829  mov     rsi, rax
0x18000e82c  jmp     loc_18000E8B6
0x18000e831  xor     edx, edx; Val
0x18000e833  lea     rcx, [rsp+1A0h+var_170]; void *
0x18000e838  call    memset_0
0x18000e83d  mov     rcx, r15
0x18000e840  lea     rdx, [r15+r12*2]
0x18000e844  mov     r8d, 100h
0x18000e84a  cmp     r15, rdx
0x18000e84d  jz      short loc_18000E86B
0x18000e84f  cmp     [rcx], r8w
0x18000e853  jnb     short loc_18000E868
0x18000e855  movzx   eax, byte ptr [rcx]
0x18000e858  mov     [rsp+rax+1A0h+var_170], r13b
0x18000e85d  add     rcx, 2
0x18000e861  cmp     rcx, rdx
0x18000e864  jnz     short loc_18000E84F
0x18000e866  jmp     short loc_18000E86B
0x18000e868  xor     r13b, r13b
0x18000e86b  lea     rdi, [r14+rdi*2]
0x18000e86f  test    r13b, r13b
0x18000e872  jz      short loc_18000E88F
0x18000e874  cmp     [rdi], r8w
0x18000e878  jnb     short loc_18000E8AD
0x18000e87a  movzx   eax, word ptr [rdi]
0x18000e87d  cmp     [rsp+rax+1A0h+var_170], 0
0x18000e882  jz      short loc_18000E8AD
0x18000e884  cmp     rdi, r14
0x18000e887  jz      short loc_18000E8B6
0x18000e889  sub     rdi, 2
0x18000e88d  jmp     short loc_18000E874
0x18000e88f  mov     r8, r12; N
0x18000e892  movzx   edx, word ptr [rdi]; C
0x18000e895  mov     rcx, r15; S
0x18000e898  call    wmemchr
0x18000e89d  test    rax, rax
0x18000e8a0  jz      short loc_18000E8AD
0x18000e8a2  cmp     rdi, r14
0x18000e8a5  jz      short loc_18000E8B6
0x18000e8a7  sub     rdi, 2
0x18000e8ab  jmp     short loc_18000E88F
0x18000e8ad  mov     rsi, rdi
0x18000e8b0  sub     rsi, r14
0x18000e8b3  sar     rsi, 1
0x18000e8b6  inc     rsi
0x18000e8b9  mov     rcx, [rbx+10h]
0x18000e8bd  cmp     rsi, rcx
0x18000e8c0  ja      short loc_18000E8D2
0x18000e8c2  mov     [rbx+10h], rsi
0x18000e8c6  cmp     qword ptr [rbx+18h], 7
0x18000e8cb  jbe     short loc_18000E906
0x18000e8cd  mov     rbx, [rbx]
0x18000e8d0  jmp     short loc_18000E906
0x18000e8d2  mov     rdx, rsi
0x18000e8d5  sub     rdx, rcx
0x18000e8d8  mov     rax, [rbx+18h]
0x18000e8dc  sub     rax, rcx
0x18000e8df  cmp     rdx, rax
0x18000e8e2  ja      short loc_18000E90E
0x18000e8e4  mov     [rbx+10h], rsi
0x18000e8e8  cmp     qword ptr [rbx+18h], 7
0x18000e8ed  jbe     short loc_18000E8F2
0x18000e8ef  mov     rbx, [rbx]
0x18000e8f2  lea     rdi, [rbx+rcx*2]
0x18000e8f6  test    rdx, rdx
0x18000e8f9  jz      short loc_18000E906
0x18000e8fb  xor     eax, eax
0x18000e8fd  movzx   eax, ax
0x18000e900  mov     rcx, rdx
0x18000e903  rep stosw
0x18000e906  xor     eax, eax
0x18000e908  mov     [rbx+rsi*2], ax
0x18000e90c  jmp     short loc_18000E91A
0x18000e90e  mov     r9, rdx
0x18000e911  mov     rcx, rbx; Src
0x18000e914  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV34@_KG@Z@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??append@01@QEAAAEAV01@0G@Z@_KG@Z; std::wstring::_Reallocate_grow_by<`std::wstring::append(unsigned __int64,ushort)'::`2'::_lambda_1_,unsigned __int64,ushort>(unsigned __int64,`std::wstring::append(unsigned __int64,ushort)'::`2'::_lambda_1_,unsigned __int64,ushort)
0x18000e919  nop
0x18000e91a  lea     rcx, [rbp+0A0h+S]
0x18000e91e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e923  mov     rcx, [rbp+0A0h+var_50]
0x18000e927  xor     rcx, rsp; StackCookie
0x18000e92a  call    __security_check_cookie
0x18000e92f  add     rsp, 168h
0x18000e936  pop     r15
0x18000e938  pop     r14
0x18000e93a  pop     r13
0x18000e93c  pop     r12
0x18000e93e  pop     rdi
0x18000e93f  pop     rsi
0x18000e940  pop     rbx
0x18000e941  pop     rbp
0x18000e942  retn
```
