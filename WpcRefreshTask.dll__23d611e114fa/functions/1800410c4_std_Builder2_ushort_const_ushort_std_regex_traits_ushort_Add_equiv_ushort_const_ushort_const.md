# std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_Add_equiv(ushort const *,ushort const *)

- ea: `0x1800410c4`
- end: `0x180041434`
- name: `?_Add_equiv@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@QEAAXPEBG0@Z`
- size: `880`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800432b8`

## callees

- `0x1800060a0`
- `0x180006108`
- `0x180007c98`
- `0x180008d50`
- `0x180009a80`
- `0x18000edec`
- `0x180035a70`
- `0x1800410c4`
- `0x180042464`

## import_xrefs

- `msvcp_win!?_Xregex_error@std@@YAXW4error_type@regex_constants@1@@Z` at `0x18004142d`
- `msvcp_win!?_Xregex_error@std@@YAXW4error_type@regex_constants@1@@Z` at `0x18004142d`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180041151`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180041165`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180041275`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180041289`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180041151`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180041165`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180041275`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180041289`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x18004113d`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x180041261`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x18004113d`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x180041261`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall std::_Builder2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Add_equiv(
        char *a1,
        __int64 a2,
        __int64 a3)
{
  unsigned int v5; // esi
  __int64 v6; // r13
  __int64 v7; // r14
  __int64 v8; // rbx
  __int64 v9; // r14
  wchar_t **v10; // rcx
  unsigned __int64 v11; // rax
  unsigned int v12; // ebx
  char *v13; // r12
  _QWORD *v14; // rcx
  int v15; // esi
  __int64 v16; // r15
  __int64 v17; // rdi
  __int128 *v18; // r14
  __int64 v19; // r15
  wchar_t **v20; // rcx
  size_t v21; // rax
  const wchar_t *v22; // rdx
  const wchar_t *v23; // rcx
  bool v24; // di
  __int64 v25; // rcx
  _OWORD *v26; // rdx
  unsigned __int64 v27; // r9
  __int16 v29[2]; // [rsp+30h] [rbp-69h] BYREF
  int v30; // [rsp+34h] [rbp-65h]
  char *v31; // [rsp+38h] [rbp-61h]
  __int64 v32; // [rsp+40h] [rbp-59h]
  __int64 v33; // [rsp+48h] [rbp-51h]
  wchar_t *S1[2]; // [rsp+50h] [rbp-49h] BYREF
  size_t N; // [rsp+60h] [rbp-39h]
  unsigned __int64 v36; // [rsp+68h] [rbp-31h]
  wchar_t *S2[2]; // [rsp+70h] [rbp-29h] BYREF
  size_t v38; // [rsp+80h] [rbp-19h]
  unsigned __int64 v39; // [rsp+88h] [rbp-11h]
  __int128 v40; // [rsp+90h] [rbp-9h] BYREF
  size_t v41; // [rsp+A0h] [rbp+7h]
  unsigned __int64 v42; // [rsp+A8h] [rbp+Fh]

  v32 = a3;
  v33 = a2;
  v31 = a1;
  *(_OWORD *)S2 = 0;
  v38 = 0;
  v39 = 7;
  LOWORD(S2[0]) = 0;
  v5 = 1;
  v30 = 1;
  if ( a2 == a3 )
    goto LABEL_39;
  v6 = *((_QWORD *)a1 + 1);
  v7 = **((_QWORD **)a1 + 3);
  v8 = __RTtypeid(v7) + 8;
  if ( !(unsigned int)__std_type_info_compare(v8, &qword_1800F13F0)
    || !(unsigned int)__std_type_info_compare(v8, &qword_1800F13C8) )
  {
    *(_OWORD *)S1 = 0;
    N = 0;
    v36 = 0;
    std::wstring::_Construct<1,unsigned short const *>(S1, a2, (a3 - a2) >> 1);
    if ( v38 < N )
    {
      v9 = v7 + 16;
      do
      {
        std::wstring::resize(S2);
        v10 = S2;
        if ( v39 > 7 )
          v10 = (wchar_t **)S2[0];
        v11 = _std_regex_transform_primary_wchar_t(v10, v9);
      }
      while ( v11 != -1 && v38 < v11 );
    }
    std::wstring::resize(S2);
    std::wstring::~wstring(S1);
  }
  if ( !v38 )
  {
LABEL_39:
    std::_Xregex_error(0);
    JUMPOUT(0x180041433LL);
  }
  v12 = 0;
  v13 = v31;
  do
  {
    v29[0] = v12;
    v14 = (_QWORD *)*((_QWORD *)v13 + 3);
    *(_OWORD *)S1 = 0;
    N = 0;
    v36 = 7;
    LOWORD(S1[0]) = 0;
    v15 = v5 | 2;
    v30 = v15;
    v16 = *v14;
    v17 = __RTtypeid(*v14) + 8;
    if ( !(unsigned int)__std_type_info_compare(v17, &qword_1800F13F0)
      || !(unsigned int)__std_type_info_compare(v17, &qword_1800F13C8) )
    {
      v40 = 0;
      v41 = 0;
      v42 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v40, v29, 1);
      v18 = &v40;
      if ( v42 > 7 )
        v18 = (__int128 *)v40;
      v31 = (char *)v18 + 2 * v41;
      if ( N < v41 )
      {
        v19 = v16 + 16;
        do
        {
          std::wstring::resize(S1);
          v20 = S1;
          if ( v36 > 7 )
            v20 = (wchar_t **)S1[0];
          v21 = _std_regex_transform_primary_wchar_t(v20, v19);
        }
        while ( v21 != -1 && N < v21 );
      }
      std::wstring::resize(S1);
      std::wstring::~wstring(&v40);
    }
    v22 = (const wchar_t *)S2;
    if ( v39 > 7 )
      v22 = S2[0];
    v23 = (const wchar_t *)S1;
    if ( v36 > 7 )
      v23 = S1[0];
    if ( N == v38 )
    {
      if ( N )
        v24 = wmemcmp(v23, v22, N) == 0;
      else
        v24 = 1;
    }
    else
    {
      v24 = 0;
    }
    v5 = v15 & 0xFFFFFFFD;
    v30 = v5;
    std::wstring::~wstring(S1);
    if ( v24 )
    {
      v26 = *(_OWORD **)(v6 + 40);
      if ( !v26 )
      {
        v26 = operator new(0x20u);
        *v26 = 0;
        v26[1] = 0;
        *(_QWORD *)(v6 + 40) = v26;
      }
      v27 = (unsigned __int64)v12 >> 3;
      v25 = *((unsigned __int8 *)v26 + v27);
      LODWORD(v25) = v25 | (1 << (v12 & 7));
      *((_BYTE *)v26 + v27) = v25;
    }
    ++v12;
  }
  while ( v12 < 0x100 );
  std::_Builder2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Char_to_elts(
    v25,
    v33,
    v32,
    v6 + 72);
  return std::wstring::~wstring(S2);
}

```

## disassembly

```asm
0x1800410c4  mov     [rsp-8+arg_18], rbx
0x1800410c9  push    rbp
0x1800410ca  push    rsi
0x1800410cb  push    rdi
0x1800410cc  push    r12
0x1800410ce  push    r13
0x1800410d0  push    r14
0x1800410d2  push    r15
0x1800410d4  lea     rbp, [rsp-27h]
0x1800410d9  sub     rsp, 0C0h
0x1800410e0  mov     rax, cs:__security_cookie
0x1800410e7  xor     rax, rsp
0x1800410ea  mov     [rbp+57h+var_40], rax
0x1800410ee  mov     rdi, r8
0x1800410f1  mov     [rbp+57h+var_B0], r8
0x1800410f5  mov     r12, rdx
0x1800410f8  mov     [rbp+57h+var_A8], rdx
0x1800410fc  mov     [rbp+57h+var_B8], rcx
0x180041100  xor     r15d, r15d
0x180041103  mov     [rbp+57h+var_BC], r15d
0x180041107  xorps   xmm0, xmm0
0x18004110a  movups  xmmword ptr [rbp+57h+S2], xmm0
0x18004110e  mov     [rbp+57h+var_70], r15
0x180041112  mov     [rbp+57h+var_68], 7
0x18004111a  mov     word ptr [rbp+57h+S2], r15w
0x18004111f  lea     esi, [r15+1]
0x180041123  mov     [rbp+57h+var_BC], esi
0x180041126  cmp     rdx, r8
0x180041129  jz      loc_18004142B
0x18004112f  mov     r13, [rcx+8]
0x180041133  mov     rax, [rcx+18h]
0x180041137  mov     r14, [rax]
0x18004113a  mov     rcx, r14
0x18004113d  call    cs:__imp___RTtypeid
0x180041143  lea     rbx, [rax+8]
0x180041147  lea     rdx, qword_1800F13F0
0x18004114e  mov     rcx, rbx
0x180041151  call    cs:__imp___std_type_info_compare
0x180041157  test    eax, eax
0x180041159  jz      short loc_180041173
0x18004115b  lea     rdx, qword_1800F13C8
0x180041162  mov     rcx, rbx
0x180041165  call    cs:__imp___std_type_info_compare
0x18004116b  test    eax, eax
0x18004116d  jnz     loc_18004121E
0x180041173  xorps   xmm0, xmm0
0x180041176  movups  xmmword ptr [rbp+57h+S1], xmm0
0x18004117a  mov     [rbp+57h+N], r15
0x18004117e  mov     [rbp+57h+var_88], r15
0x180041182  mov     r8, rdi
0x180041185  sub     r8, r12
0x180041188  sar     r8, 1
0x18004118b  mov     rdx, r12
0x18004118e  lea     rcx, [rbp+57h+S1]
0x180041192  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180041197  nop
0x180041198  lea     rdi, [rbp+57h+S1]
0x18004119c  cmp     [rbp+57h+var_88], 7
0x1800411a1  cmova   rdi, [rbp+57h+S1]
0x1800411a6  mov     rbx, [rbp+57h+N]
0x1800411aa  lea     r15, [rdi+rbx*2]
0x1800411ae  cmp     [rbp+57h+var_70], rbx
0x1800411b2  jnb     short loc_180041205
0x1800411b4  add     r14, 10h
0x1800411b8  xor     r8d, r8d
0x1800411bb  mov     rdx, rbx
0x1800411be  lea     rcx, [rbp+57h+S2]; Src
0x1800411c2  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1800411c7  lea     rax, [rbp+57h+S2]
0x1800411cb  cmp     [rbp+57h+var_68], 7
0x1800411d0  cmova   rax, [rbp+57h+S2]
0x1800411d5  lea     rdx, [rax+rbx*2]
0x1800411d9  lea     rcx, [rbp+57h+S2]
0x1800411dd  cmova   rcx, [rbp+57h+S2]; void *
0x1800411e2  mov     [rsp+0F0h+var_D0], r14; __int64
0x1800411e7  mov     r9, r15
0x1800411ea  mov     r8, rdi
0x1800411ed  call    __std_regex_transform_primary_wchar_t
0x1800411f2  mov     rbx, rax
0x1800411f5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800411f9  jz      short loc_180041203
0x1800411fb  cmp     [rbp+57h+var_70], rax
0x1800411ff  jb      short loc_1800411B8
0x180041201  jmp     short loc_180041205
0x180041203  xor     ebx, ebx
0x180041205  xor     r8d, r8d
0x180041208  mov     rdx, rbx
0x18004120b  lea     rcx, [rbp+57h+S2]; Src
0x18004120f  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180041214  nop
0x180041215  lea     rcx, [rbp+57h+S1]
0x180041219  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004121e  cmp     [rbp+57h+var_70], 0
0x180041223  jz      loc_18004142B
0x180041229  xor     ebx, ebx
0x18004122b  mov     r12, [rbp+57h+var_B8]
0x18004122f  mov     [rbp+57h+var_C0], bx
0x180041233  mov     rcx, [r12+18h]
0x180041238  xorps   xmm0, xmm0
0x18004123b  movups  xmmword ptr [rbp+57h+S1], xmm0
0x18004123f  mov     [rbp+57h+N], 0
0x180041247  mov     [rbp+57h+var_88], 7
0x18004124f  xor     eax, eax
0x180041251  mov     word ptr [rbp+57h+S1], ax
0x180041255  or      esi, 2
0x180041258  mov     [rbp+57h+var_BC], esi
0x18004125b  mov     r15, [rcx]
0x18004125e  mov     rcx, r15
0x180041261  call    cs:__imp___RTtypeid
0x180041267  lea     rdi, [rax+8]
0x18004126b  lea     rdx, qword_1800F13F0
0x180041272  mov     rcx, rdi
0x180041275  call    cs:__imp___std_type_info_compare
0x18004127b  test    eax, eax
0x18004127d  jz      short loc_180041297
0x18004127f  lea     rdx, qword_1800F13C8
0x180041286  mov     rcx, rdi
0x180041289  call    cs:__imp___std_type_info_compare
0x18004128f  test    eax, eax
0x180041291  jnz     loc_18004134D
0x180041297  xorps   xmm0, xmm0
0x18004129a  movups  [rbp+57h+var_60], xmm0
0x18004129e  mov     [rbp+57h+var_50], 0
0x1800412a6  mov     [rbp+57h+var_48], 0
0x1800412ae  mov     r8d, 1
0x1800412b4  lea     rdx, [rbp+57h+var_C0]
0x1800412b8  lea     rcx, [rbp+57h+var_60]
0x1800412bc  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800412c1  nop
0x1800412c2  lea     r14, [rbp+57h+var_60]
0x1800412c6  cmp     [rbp+57h+var_48], 7
0x1800412cb  cmova   r14, qword ptr [rbp+57h+var_60]
0x1800412d0  mov     rdi, [rbp+57h+var_50]
0x1800412d4  lea     rax, [r14+rdi*2]
0x1800412d8  mov     [rbp+57h+var_B8], rax
0x1800412dc  cmp     [rbp+57h+N], rdi
0x1800412e0  jnb     short loc_180041334
0x1800412e2  add     r15, 10h
0x1800412e6  xor     r8d, r8d
0x1800412e9  mov     rdx, rdi
0x1800412ec  lea     rcx, [rbp+57h+S1]; Src
0x1800412f0  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1800412f5  lea     rax, [rbp+57h+S1]
0x1800412f9  cmp     [rbp+57h+var_88], 7
0x1800412fe  cmova   rax, [rbp+57h+S1]
0x180041303  lea     rdx, [rax+rdi*2]
0x180041307  lea     rcx, [rbp+57h+S1]
0x18004130b  cmova   rcx, [rbp+57h+S1]; void *
0x180041310  mov     [rsp+0F0h+var_D0], r15; __int64
0x180041315  mov     r9, [rbp+57h+var_B8]
0x180041319  mov     r8, r14
0x18004131c  call    __std_regex_transform_primary_wchar_t
0x180041321  mov     rdi, rax
0x180041324  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180041328  jz      short loc_180041332
0x18004132a  cmp     [rbp+57h+N], rax
0x18004132e  jb      short loc_1800412E6
0x180041330  jmp     short loc_180041334
0x180041332  xor     edi, edi
0x180041334  xor     r8d, r8d
0x180041337  mov     rdx, rdi
0x18004133a  lea     rcx, [rbp+57h+S1]; Src
0x18004133e  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180041343  nop
0x180041344  lea     rcx, [rbp+57h+var_60]
0x180041348  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004134d  lea     rdx, [rbp+57h+S2]
0x180041351  cmp     [rbp+57h+var_68], 7
0x180041356  cmova   rdx, [rbp+57h+S2]; S2
0x18004135b  mov     r8, [rbp+57h+N]; N
0x18004135f  lea     rcx, [rbp+57h+S1]
0x180041363  cmp     [rbp+57h+var_88], 7
0x180041368  cmova   rcx, [rbp+57h+S1]; S1
0x18004136d  cmp     r8, [rbp+57h+var_70]
0x180041371  jz      short loc_180041378
0x180041373  xor     dil, dil
0x180041376  jmp     short loc_18004138D
0x180041378  test    r8, r8
0x18004137b  jnz     short loc_180041382
0x18004137d  mov     dil, 1
0x180041380  jmp     short loc_18004138D
0x180041382  call    wmemcmp
0x180041387  test    eax, eax
0x180041389  setz    dil
0x18004138d  and     esi, 0FFFFFFFDh
0x180041390  mov     [rbp+57h+var_BC], esi
0x180041393  lea     rcx, [rbp+57h+S1]
0x180041397  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004139c  test    dil, dil
0x18004139f  jz      short loc_1800413DB
0x1800413a1  mov     rdx, [r13+28h]
0x1800413a5  test    rdx, rdx
0x1800413a8  jnz     short loc_1800413C3
0x1800413aa  lea     ecx, [rdx+20h]; Size
0x1800413ad  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800413b2  mov     rdx, rax
0x1800413b5  xorps   xmm0, xmm0
0x1800413b8  movups  xmmword ptr [rax], xmm0
0x1800413bb  movups  xmmword ptr [rax+10h], xmm0
0x1800413bf  mov     [r13+28h], rax
0x1800413c3  mov     r9d, ebx
0x1800413c6  shr     r9, 3
0x1800413ca  movzx   ecx, byte ptr [r9+rdx]
0x1800413cf  mov     eax, ebx
0x1800413d1  and     eax, 7
0x1800413d4  bts     ecx, eax
0x1800413d7  mov     [r9+rdx], cl
0x1800413db  inc     ebx
0x1800413dd  cmp     ebx, 100h
0x1800413e3  jb      loc_18004122F
0x1800413e9  lea     r9, [r13+48h]
0x1800413ed  mov     r8, [rbp+57h+var_B0]
0x1800413f1  mov     rdx, [rbp+57h+var_A8]
0x1800413f5  call    ?_Char_to_elts@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@AEAAXPEBG0PEAPEAU?$_Sequence@G@2@@Z; std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_Char_to_elts(ushort const *,ushort const *,std::_Sequence<ushort> * *)
0x1800413fa  nop
0x1800413fb  lea     rcx, [rbp+57h+S2]
0x1800413ff  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180041404  mov     rcx, [rbp+57h+var_40]
0x180041408  xor     rcx, rsp; StackCookie
0x18004140b  call    __security_check_cookie
0x180041410  mov     rbx, [rsp+0F0h+arg_18]
0x180041418  add     rsp, 0C0h
0x18004141f  pop     r15
0x180041421  pop     r14
0x180041423  pop     r13
0x180041425  pop     r12
0x180041427  pop     rdi
0x180041428  pop     rsi
0x180041429  pop     rbp
0x18004142a  retn
0x18004142b  xor     ecx, ecx
0x18004142d  call    cs:__imp_?_Xregex_error@std@@YAXW4error_type@regex_constants@1@@Z; std::_Xregex_error(std::regex_constants::error_type)
```
