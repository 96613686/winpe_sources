# std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_Add_equiv(ushort const *,ushort const *)

- ea: `0x18004e1c4`
- end: `0x18004e551`
- name: `?_Add_equiv@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@QEAAXPEBG0@Z`
- size: `909`
- prototype: `__int64 __fastcall(__int64, _BYTE *, _BYTE *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180050700`

## callees

- `0x180003400`
- `0x180003c20`
- `0x18000de1c`
- `0x18000fa4c`
- `0x180019bf8`
- `0x180038b40`
- `0x18004e1c4`
- `0x18004f41c`
- `0x180052308`
- `0x1800ea1b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x18004e246`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x18004e376`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x18004e246`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x18004e376`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18004e260`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18004e27a`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18004e390`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18004e3aa`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18004e260`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18004e27a`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18004e390`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18004e3aa`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall std::_Builder2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Add_equiv(
        __int64 a1,
        __int16 *a2,
        __int16 *a3)
{
  unsigned int v5; // esi
  __int64 v6; // r13
  const struct _Collvec *v7; // r14
  __int64 v8; // rbx
  const unsigned __int16 *v9; // rdi
  size_t v10; // rbx
  const unsigned __int16 *v11; // r15
  const struct _Collvec *v12; // r14
  wchar_t **v13; // rax
  unsigned __int16 *v14; // rcx
  size_t v15; // rax
  unsigned int v16; // edi
  unsigned __int16 *v17; // r12
  const struct _Collvec **v18; // rcx
  int v19; // esi
  const struct _Collvec *v20; // r15
  __int64 v21; // rbx
  const unsigned __int16 *v22; // r14
  void *v23; // rbx
  const struct _Collvec *v24; // r15
  wchar_t **v25; // rax
  unsigned __int16 *v26; // rcx
  size_t v27; // rax
  const wchar_t *v28; // rdx
  const wchar_t *v29; // rcx
  bool v30; // bl
  __int64 v31; // rcx
  _OWORD *v32; // rdx
  unsigned __int64 v33; // r9
  __int16 v35[2]; // [rsp+38h] [rbp-69h] BYREF
  int v36; // [rsp+3Ch] [rbp-65h]
  unsigned __int16 *v37; // [rsp+40h] [rbp-61h]
  __int16 *v38; // [rsp+48h] [rbp-59h]
  __int16 *v39; // [rsp+50h] [rbp-51h]
  __int64 v40; // [rsp+58h] [rbp-49h]
  wchar_t *S1[2]; // [rsp+60h] [rbp-41h] BYREF
  size_t N; // [rsp+70h] [rbp-31h]
  unsigned __int64 v43; // [rsp+78h] [rbp-29h]
  wchar_t *S2[2]; // [rsp+80h] [rbp-21h] BYREF
  size_t v45; // [rsp+90h] [rbp-11h]
  unsigned __int64 v46; // [rsp+98h] [rbp-9h]
  unsigned __int16 *v47[2]; // [rsp+A0h] [rbp-1h] BYREF
  size_t v48; // [rsp+B0h] [rbp+Fh]
  unsigned __int64 v49; // [rsp+B8h] [rbp+17h]

  v40 = -2;
  v38 = a3;
  v39 = a2;
  v37 = (unsigned __int16 *)a1;
  *(_OWORD *)S2 = 0;
  v45 = 0;
  v46 = 7;
  LOWORD(S2[0]) = 0;
  v5 = 1;
  v36 = 1;
  if ( a2 == a3 )
    goto LABEL_49;
  v6 = *(_QWORD *)(a1 + 8);
  v7 = **(const struct _Collvec ***)(a1 + 24);
  v8 = __RTtypeid(v7) + 8;
  if ( !(unsigned int)__std_type_info_compare(v8, &qword_1802963A8)
    || !(unsigned int)__std_type_info_compare(v8, &qword_1802963D8) )
  {
    *(_OWORD *)S1 = 0;
    N = 0;
    v43 = 0;
    std::wstring::_Construct<1,unsigned short const *>(S1, a2, a3 - a2);
    v9 = (const unsigned __int16 *)S1;
    if ( v43 > 7 )
      v9 = S1[0];
    v10 = N;
    v11 = &v9[N];
    if ( v45 < N )
    {
      v12 = v7 + 1;
      while ( 1 )
      {
        std::wstring::resize((void **)S2, (void *)v10);
        v13 = S2;
        if ( v46 > 7 )
          v13 = (wchar_t **)S2[0];
        v14 = (unsigned __int16 *)S2;
        if ( v46 > 7 )
          v14 = S2[0];
        v15 = std::_Regex_transform_primary(v14, (unsigned __int16 *)v13 + v10, v9, v11, v12);
        v10 = v15;
        if ( v15 == -1 )
          break;
        if ( v45 >= v15 )
          goto LABEL_16;
      }
      v10 = 0;
    }
LABEL_16:
    std::wstring::resize((void **)S2, (void *)v10);
    std::wstring::~wstring((char **)S1);
  }
  if ( !v45 )
LABEL_49:
    std::_Xregex_error(0);
  v16 = 0;
  v17 = v37;
  do
  {
    v35[0] = v16;
    v18 = (const struct _Collvec **)*((_QWORD *)v17 + 3);
    *(_OWORD *)S1 = 0;
    N = 0;
    v43 = 7;
    LOWORD(S1[0]) = 0;
    v19 = v5 | 2;
    v36 = v19;
    v20 = *v18;
    v21 = __RTtypeid(*v18) + 8;
    if ( !(unsigned int)__std_type_info_compare(v21, &qword_1802963A8)
      || !(unsigned int)__std_type_info_compare(v21, &qword_1802963D8) )
    {
      *(_OWORD *)v47 = 0;
      v48 = 0;
      v49 = 0;
      std::wstring::_Construct<1,unsigned short const *>(v47, v35, 1u);
      v22 = (const unsigned __int16 *)v47;
      if ( v49 > 7 )
        v22 = v47[0];
      v23 = (void *)v48;
      v37 = (unsigned __int16 *)&v22[v48];
      if ( N < v48 )
      {
        v24 = v20 + 1;
        while ( 1 )
        {
          std::wstring::resize((void **)S1, v23);
          v25 = S1;
          if ( v43 > 7 )
            v25 = (wchar_t **)S1[0];
          v26 = (unsigned __int16 *)S1;
          if ( v43 > 7 )
            v26 = S1[0];
          v27 = std::_Regex_transform_primary(v26, (unsigned __int16 *)v25 + (_QWORD)v23, v22, v37, v24);
          v23 = (void *)v27;
          if ( v27 == -1 )
            break;
          if ( N >= v27 )
            goto LABEL_33;
        }
        v23 = 0;
      }
LABEL_33:
      std::wstring::resize((void **)S1, v23);
      std::wstring::~wstring((char **)v47);
    }
    v28 = (const wchar_t *)S2;
    if ( v46 > 7 )
      v28 = S2[0];
    v29 = (const wchar_t *)S1;
    if ( v43 > 7 )
      v29 = S1[0];
    if ( N == v45 )
    {
      if ( N )
        v30 = wmemcmp(v29, v28, N) == 0;
      else
        v30 = 1;
    }
    else
    {
      v30 = 0;
    }
    v5 = v19 & 0xFFFFFFFD;
    v36 = v5;
    std::wstring::~wstring((char **)S1);
    if ( v30 )
    {
      v32 = *(_OWORD **)(v6 + 40);
      if ( !v32 )
      {
        v32 = operator new(0x20u);
        *v32 = 0;
        v32[1] = 0;
        *(_QWORD *)(v6 + 40) = v32;
      }
      v33 = (unsigned __int64)v16 >> 3;
      v31 = *((unsigned __int8 *)v32 + v33);
      LODWORD(v31) = v31 | (1 << (v16 & 7));
      *((_BYTE *)v32 + v33) = v31;
    }
    ++v16;
  }
  while ( v16 < 0x100 );
  std::_Builder2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Char_to_elts(
    v31,
    v39,
    v38,
    (_DWORD **)(v6 + 72));
  return std::wstring::~wstring((char **)S2);
}

```

## disassembly

```asm
0x18004e1c4  mov     rax, rsp
0x18004e1c7  push    rbp
0x18004e1c8  push    rsi
0x18004e1c9  push    rdi
0x18004e1ca  push    r12
0x18004e1cc  push    r13
0x18004e1ce  push    r14
0x18004e1d0  push    r15
0x18004e1d2  lea     rbp, [rax-5Fh]
0x18004e1d6  sub     rsp, 0C0h
0x18004e1dd  mov     [rbp+57h+var_A0], 0FFFFFFFFFFFFFFFEh
0x18004e1e5  mov     [rax+20h], rbx
0x18004e1e9  mov     rax, cs:__security_cookie
0x18004e1f0  xor     rax, rsp
0x18004e1f3  mov     [rbp+57h+var_38], rax
0x18004e1f7  mov     rdi, r8
0x18004e1fa  mov     [rbp+57h+var_B0], r8
0x18004e1fe  mov     r12, rdx
0x18004e201  mov     [rbp+57h+var_A8], rdx
0x18004e205  mov     [rbp+57h+var_B8], rcx
0x18004e209  xor     r15d, r15d
0x18004e20c  mov     [rbp+57h+var_BC], r15d
0x18004e210  xorps   xmm0, xmm0
0x18004e213  movups  xmmword ptr [rbp+57h+S2], xmm0
0x18004e217  mov     [rbp+57h+var_68], r15
0x18004e21b  mov     [rbp+57h+var_60], 7
0x18004e223  mov     word ptr [rbp+57h+S2], r15w
0x18004e228  lea     esi, [r15+1]
0x18004e22c  mov     [rbp+57h+var_BC], esi
0x18004e22f  cmp     rdx, r8
0x18004e232  jz      loc_18004E549
0x18004e238  mov     r13, [rcx+8]
0x18004e23c  mov     rax, [rcx+18h]
0x18004e240  mov     r14, [rax]
0x18004e243  mov     rcx, r14
0x18004e246  call    cs:__imp___RTtypeid
0x18004e24d  nop     dword ptr [rax+rax+00h]
0x18004e252  lea     rbx, [rax+8]
0x18004e256  lea     rdx, qword_1802963A8
0x18004e25d  mov     rcx, rbx
0x18004e260  call    cs:__imp___std_type_info_compare
0x18004e267  nop     dword ptr [rax+rax+00h]
0x18004e26c  test    eax, eax
0x18004e26e  jz      short loc_18004E28E
0x18004e270  lea     rdx, qword_1802963D8
0x18004e277  mov     rcx, rbx
0x18004e27a  call    cs:__imp___std_type_info_compare
0x18004e281  nop     dword ptr [rax+rax+00h]
0x18004e286  test    eax, eax
0x18004e288  jnz     loc_18004E333
0x18004e28e  xorps   xmm0, xmm0
0x18004e291  movups  xmmword ptr [rbp+57h+S1], xmm0
0x18004e295  mov     [rbp+57h+N], r15
0x18004e299  mov     [rbp+57h+var_80], r15
0x18004e29d  mov     r8, rdi
0x18004e2a0  sub     r8, r12
0x18004e2a3  sar     r8, 1
0x18004e2a6  mov     rdx, r12
0x18004e2a9  lea     rcx, [rbp+57h+S1]
0x18004e2ad  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18004e2b2  nop
0x18004e2b3  lea     rdi, [rbp+57h+S1]
0x18004e2b7  cmp     [rbp+57h+var_80], 7
0x18004e2bc  cmova   rdi, [rbp+57h+S1]
0x18004e2c1  mov     rbx, [rbp+57h+N]
0x18004e2c5  lea     r15, [rdi+rbx*2]
0x18004e2c9  cmp     [rbp+57h+var_68], rbx
0x18004e2cd  jnb     short loc_18004E31D
0x18004e2cf  add     r14, 10h
0x18004e2d3  mov     rdx, rbx
0x18004e2d6  lea     rcx, [rbp+57h+S2]; Src
0x18004e2da  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18004e2df  lea     rax, [rbp+57h+S2]
0x18004e2e3  cmp     [rbp+57h+var_60], 7
0x18004e2e8  cmova   rax, [rbp+57h+S2]
0x18004e2ed  lea     rdx, [rax+rbx*2]; unsigned __int16 *
0x18004e2f1  lea     rcx, [rbp+57h+S2]
0x18004e2f5  cmova   rcx, [rbp+57h+S2]; unsigned __int16 *
0x18004e2fa  mov     [rsp+20h], r14; struct _Collvec *
0x18004e2ff  mov     r9, r15; unsigned __int16 *
0x18004e302  mov     r8, rdi; unsigned __int16 *
0x18004e305  call    ?_Regex_transform_primary@std@@YA_KPEAG0PEBG1PEBU_Collvec@@@Z; std::_Regex_transform_primary(ushort *,ushort *,ushort const *,ushort const *,_Collvec const *)
0x18004e30a  mov     rbx, rax
0x18004e30d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004e311  jz      short loc_18004E31B
0x18004e313  cmp     [rbp+57h+var_68], rax
0x18004e317  jb      short loc_18004E2D3
0x18004e319  jmp     short loc_18004E31D
0x18004e31b  xor     ebx, ebx
0x18004e31d  mov     rdx, rbx
0x18004e320  lea     rcx, [rbp+57h+S2]; Src
0x18004e324  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18004e329  nop
0x18004e32a  lea     rcx, [rbp+57h+S1]
0x18004e32e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004e333  cmp     [rbp+57h+var_68], 0
0x18004e338  jz      loc_18004E549
0x18004e33e  xor     edi, edi
0x18004e340  mov     r12, [rbp+57h+var_B8]
0x18004e344  mov     [rbp+57h+var_C0], di
0x18004e348  mov     rcx, [r12+18h]
0x18004e34d  xorps   xmm0, xmm0
0x18004e350  movups  xmmword ptr [rbp+57h+S1], xmm0
0x18004e354  mov     [rbp+57h+N], 0
0x18004e35c  mov     [rbp+57h+var_80], 7
0x18004e364  xor     eax, eax
0x18004e366  mov     word ptr [rbp+57h+S1], ax
0x18004e36a  or      esi, 2
0x18004e36d  mov     [rbp+57h+var_BC], esi
0x18004e370  mov     r15, [rcx]
0x18004e373  mov     rcx, r15
0x18004e376  call    cs:__imp___RTtypeid
0x18004e37d  nop     dword ptr [rax+rax+00h]
0x18004e382  lea     rbx, [rax+8]
0x18004e386  lea     rdx, qword_1802963A8
0x18004e38d  mov     rcx, rbx
0x18004e390  call    cs:__imp___std_type_info_compare
0x18004e397  nop     dword ptr [rax+rax+00h]
0x18004e39c  test    eax, eax
0x18004e39e  jz      short loc_18004E3BE
0x18004e3a0  lea     rdx, qword_1802963D8
0x18004e3a7  mov     rcx, rbx
0x18004e3aa  call    cs:__imp___std_type_info_compare
0x18004e3b1  nop     dword ptr [rax+rax+00h]
0x18004e3b6  test    eax, eax
0x18004e3b8  jnz     loc_18004E46E
0x18004e3be  xorps   xmm0, xmm0
0x18004e3c1  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x18004e3c5  mov     [rbp+57h+var_48], 0
0x18004e3cd  mov     [rbp+57h+var_40], 0
0x18004e3d5  mov     r8d, 1
0x18004e3db  lea     rdx, [rbp+57h+var_C0]
0x18004e3df  lea     rcx, [rbp+57h+var_58]
0x18004e3e3  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18004e3e8  nop
0x18004e3e9  lea     r14, [rbp+57h+var_58]
0x18004e3ed  cmp     [rbp+57h+var_40], 7
0x18004e3f2  cmova   r14, [rbp+57h+var_58]
0x18004e3f7  mov     rbx, [rbp+57h+var_48]
0x18004e3fb  lea     rax, [r14+rbx*2]
0x18004e3ff  mov     [rbp+57h+var_B8], rax
0x18004e403  cmp     [rbp+57h+N], rbx
0x18004e407  jnb     short loc_18004E458
0x18004e409  add     r15, 10h
0x18004e40d  mov     rdx, rbx
0x18004e410  lea     rcx, [rbp+57h+S1]; Src
0x18004e414  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18004e419  lea     rax, [rbp+57h+S1]
0x18004e41d  cmp     [rbp+57h+var_80], 7
0x18004e422  cmova   rax, [rbp+57h+S1]
0x18004e427  lea     rdx, [rax+rbx*2]; unsigned __int16 *
0x18004e42b  lea     rcx, [rbp+57h+S1]
0x18004e42f  cmova   rcx, [rbp+57h+S1]; unsigned __int16 *
0x18004e434  mov     [rsp+20h], r15; struct _Collvec *
0x18004e439  mov     r9, [rbp+57h+var_B8]; unsigned __int16 *
0x18004e43d  mov     r8, r14; unsigned __int16 *
0x18004e440  call    ?_Regex_transform_primary@std@@YA_KPEAG0PEBG1PEBU_Collvec@@@Z; std::_Regex_transform_primary(ushort *,ushort *,ushort const *,ushort const *,_Collvec const *)
0x18004e445  mov     rbx, rax
0x18004e448  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004e44c  jz      short loc_18004E456
0x18004e44e  cmp     [rbp+57h+N], rax
0x18004e452  jb      short loc_18004E40D
0x18004e454  jmp     short loc_18004E458
0x18004e456  xor     ebx, ebx
0x18004e458  mov     rdx, rbx
0x18004e45b  lea     rcx, [rbp+57h+S1]; Src
0x18004e45f  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18004e464  nop
0x18004e465  lea     rcx, [rbp+57h+var_58]
0x18004e469  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004e46e  lea     rdx, [rbp+57h+S2]
0x18004e472  cmp     [rbp+57h+var_60], 7
0x18004e477  cmova   rdx, [rbp+57h+S2]; S2
0x18004e47c  mov     r8, [rbp+57h+N]; N
0x18004e480  lea     rcx, [rbp+57h+S1]
0x18004e484  cmp     [rbp+57h+var_80], 7
0x18004e489  cmova   rcx, [rbp+57h+S1]; S1
0x18004e48e  cmp     r8, [rbp+57h+var_68]
0x18004e492  jz      short loc_18004E498
0x18004e494  xor     bl, bl
0x18004e496  jmp     short loc_18004E4AB
0x18004e498  test    r8, r8
0x18004e49b  jnz     short loc_18004E4A1
0x18004e49d  mov     bl, 1
0x18004e49f  jmp     short loc_18004E4AB
0x18004e4a1  call    wmemcmp
0x18004e4a6  test    eax, eax
0x18004e4a8  setz    bl
0x18004e4ab  and     esi, 0FFFFFFFDh
0x18004e4ae  mov     [rbp+57h+var_BC], esi
0x18004e4b1  lea     rcx, [rbp+57h+S1]
0x18004e4b5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004e4ba  test    bl, bl
0x18004e4bc  jz      short loc_18004E4F8
0x18004e4be  mov     rdx, [r13+28h]
0x18004e4c2  test    rdx, rdx
0x18004e4c5  jnz     short loc_18004E4E0
0x18004e4c7  lea     ecx, [rdx+20h]; Size
0x18004e4ca  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004e4cf  mov     rdx, rax
0x18004e4d2  xorps   xmm0, xmm0
0x18004e4d5  movups  xmmword ptr [rax], xmm0
0x18004e4d8  movups  xmmword ptr [rax+10h], xmm0
0x18004e4dc  mov     [r13+28h], rax
0x18004e4e0  mov     r9d, edi
0x18004e4e3  shr     r9, 3
0x18004e4e7  movzx   ecx, byte ptr [r9+rdx]
0x18004e4ec  mov     eax, edi
0x18004e4ee  and     eax, 7
0x18004e4f1  bts     ecx, eax
0x18004e4f4  mov     [r9+rdx], cl
0x18004e4f8  inc     edi
0x18004e4fa  cmp     edi, 100h
0x18004e500  jb      loc_18004E344
0x18004e506  lea     r9, [r13+48h]
0x18004e50a  mov     r8, [rbp+57h+var_B0]
0x18004e50e  mov     rdx, [rbp+57h+var_A8]
0x18004e512  call    ?_Char_to_elts@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@AEAAXPEBG0PEAPEAU?$_Sequence@G@2@@Z; std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_Char_to_elts(ushort const *,ushort const *,std::_Sequence<ushort> * *)
0x18004e517  nop
0x18004e518  lea     rcx, [rbp+57h+S2]
0x18004e51c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004e521  mov     rcx, [rbp+57h+var_38]
0x18004e525  xor     rcx, rsp; StackCookie
0x18004e528  call    __security_check_cookie
0x18004e52d  mov     rbx, [rsp+0F0h+arg_18]
0x18004e535  add     rsp, 0C0h
0x18004e53c  pop     r15
0x18004e53e  pop     r14
0x18004e540  pop     r13
0x18004e542  pop     r12
0x18004e544  pop     rdi
0x18004e545  pop     rsi
0x18004e546  pop     rbp
0x18004e547  retn
0x18004e549  xor     ecx, ecx
0x18004e54b  call    ?_Xregex_error@std@@YAXW4error_type@regex_constants@1@@Z; std::_Xregex_error(std::regex_constants::error_type)
```
