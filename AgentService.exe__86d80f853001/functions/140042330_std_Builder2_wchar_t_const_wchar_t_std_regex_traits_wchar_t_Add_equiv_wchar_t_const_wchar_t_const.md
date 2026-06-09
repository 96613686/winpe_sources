# std::_Builder2<wchar_t const *,wchar_t,std::regex_traits<wchar_t>>::_Add_equiv(wchar_t const *,wchar_t const *)

- ea: `0x140042330`
- end: `0x140042690`
- name: `?_Add_equiv@?$_Builder2@PEB_W_WV?$regex_traits@_W@std@@@std@@QEAAXPEB_W0@Z`
- size: `864`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140043d74`

## callees

- `0x140003e50`
- `0x140003e74`
- `0x14000a7bc`
- `0x14000ba60`
- `0x14000c2b8`
- `0x14000e30c`
- `0x1400180e8`
- `0x140042330`
- `0x1400434ec`

## import_xrefs

- `msvcp_win!?_Xregex_error@std@@YAXW4error_type@regex_constants@1@@Z` at `0x140042689`
- `msvcp_win!?_Xregex_error@std@@YAXW4error_type@regex_constants@1@@Z` at `0x140042689`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1400423bd`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1400423d1`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1400424db`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1400424ef`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1400423bd`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1400423d1`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1400424db`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1400424ef`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1400423a9`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1400424c7`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1400423a9`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x1400424c7`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall std::_Builder2<wchar_t const *,wchar_t,std::regex_traits<wchar_t>>::_Add_equiv(
        char *a1,
        _BYTE *a2,
        _BYTE *a3)
{
  unsigned int v5; // esi
  __int64 v6; // r13
  __int64 v7; // r14
  __int64 v8; // rbx
  __int64 v9; // r14
  wchar_t **v10; // rcx
  unsigned __int64 v11; // rax
  unsigned int v12; // edi
  char *v13; // r12
  _QWORD *v14; // rcx
  int v15; // esi
  __int64 v16; // r15
  __int64 v17; // rbx
  __int128 *v18; // r14
  __int64 v19; // r15
  wchar_t **v20; // rcx
  size_t v21; // rax
  const wchar_t *v22; // rdx
  const wchar_t *v23; // rcx
  bool v24; // bl
  __int64 v25; // rcx
  _OWORD *v26; // rdx
  unsigned __int64 v27; // r9
  __int16 v29[2]; // [rsp+30h] [rbp-69h] BYREF
  int v30; // [rsp+34h] [rbp-65h]
  char *v31; // [rsp+38h] [rbp-61h]
  _BYTE *v32; // [rsp+40h] [rbp-59h]
  const void *v33; // [rsp+48h] [rbp-51h]
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
  if ( !(unsigned int)__std_type_info_compare(v8, &qword_1400CBB60)
    || !(unsigned int)__std_type_info_compare(v8, &qword_1400CBB38) )
  {
    *(_OWORD *)S1 = 0;
    N = 0;
    v36 = 0;
    std::wstring::_Construct<1,wchar_t *>(S1, a2, (a3 - a2) >> 1);
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
    std::wstring::_Tidy_deallocate(S1);
  }
  if ( !v38 )
  {
LABEL_39:
    std::_Xregex_error(0);
    JUMPOUT(0x14004268FLL);
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
    if ( !(unsigned int)__std_type_info_compare(v17, &qword_1400CBB60)
      || !(unsigned int)__std_type_info_compare(v17, &qword_1400CBB38) )
    {
      v40 = 0;
      v41 = 0;
      v42 = 0;
      std::wstring::_Construct<1,wchar_t *>(&v40, v29, 1u);
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
      std::wstring::_Tidy_deallocate(&v40);
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
    std::wstring::_Tidy_deallocate(S1);
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
  std::_Builder2<wchar_t const *,wchar_t,std::regex_traits<wchar_t>>::_Char_to_elts(v25, v33, v32, v6 + 72);
  return std::wstring::_Tidy_deallocate(S2);
}

```

## disassembly

```asm
0x140042330  mov     [rsp-8+arg_18], rbx
0x140042335  push    rbp
0x140042336  push    rsi
0x140042337  push    rdi
0x140042338  push    r12
0x14004233a  push    r13
0x14004233c  push    r14
0x14004233e  push    r15
0x140042340  lea     rbp, [rsp-27h]
0x140042345  sub     rsp, 0C0h
0x14004234c  mov     rax, cs:__security_cookie
0x140042353  xor     rax, rsp
0x140042356  mov     [rbp+57h+var_40], rax
0x14004235a  mov     rdi, r8
0x14004235d  mov     [rbp+57h+var_B0], r8
0x140042361  mov     r12, rdx
0x140042364  mov     [rbp+57h+var_A8], rdx
0x140042368  mov     [rbp+57h+var_B8], rcx
0x14004236c  xor     r15d, r15d
0x14004236f  mov     [rbp+57h+var_BC], r15d
0x140042373  xorps   xmm0, xmm0
0x140042376  movups  xmmword ptr [rbp+57h+S2], xmm0
0x14004237a  mov     [rbp+57h+var_70], r15
0x14004237e  mov     [rbp+57h+var_68], 7
0x140042386  mov     word ptr [rbp+57h+S2], r15w
0x14004238b  lea     esi, [r15+1]
0x14004238f  mov     [rbp+57h+var_BC], esi
0x140042392  cmp     rdx, r8
0x140042395  jz      loc_140042687
0x14004239b  mov     r13, [rcx+8]
0x14004239f  mov     rax, [rcx+18h]
0x1400423a3  mov     r14, [rax]
0x1400423a6  mov     rcx, r14
0x1400423a9  call    cs:__imp___RTtypeid
0x1400423af  lea     rbx, [rax+8]
0x1400423b3  lea     rdx, qword_1400CBB60
0x1400423ba  mov     rcx, rbx
0x1400423bd  call    cs:__imp___std_type_info_compare
0x1400423c3  test    eax, eax
0x1400423c5  jz      short loc_1400423DF
0x1400423c7  lea     rdx, qword_1400CBB38
0x1400423ce  mov     rcx, rbx
0x1400423d1  call    cs:__imp___std_type_info_compare
0x1400423d7  test    eax, eax
0x1400423d9  jnz     loc_140042484
0x1400423df  xorps   xmm0, xmm0
0x1400423e2  movups  xmmword ptr [rbp+57h+S1], xmm0
0x1400423e6  mov     [rbp+57h+N], r15
0x1400423ea  mov     [rbp+57h+var_88], r15
0x1400423ee  mov     r8, rdi
0x1400423f1  sub     r8, r12
0x1400423f4  sar     r8, 1
0x1400423f7  mov     rdx, r12
0x1400423fa  lea     rcx, [rbp+57h+S1]
0x1400423fe  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x140042403  nop
0x140042404  lea     rdi, [rbp+57h+S1]
0x140042408  cmp     [rbp+57h+var_88], 7
0x14004240d  cmova   rdi, [rbp+57h+S1]
0x140042412  mov     rbx, [rbp+57h+N]
0x140042416  lea     r15, [rdi+rbx*2]
0x14004241a  cmp     [rbp+57h+var_70], rbx
0x14004241e  jnb     short loc_14004246E
0x140042420  add     r14, 10h
0x140042424  mov     rdx, rbx
0x140042427  lea     rcx, [rbp+57h+S2]; Src
0x14004242b  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x140042430  lea     rax, [rbp+57h+S2]
0x140042434  cmp     [rbp+57h+var_68], 7
0x140042439  cmova   rax, [rbp+57h+S2]
0x14004243e  lea     rdx, [rax+rbx*2]
0x140042442  lea     rcx, [rbp+57h+S2]
0x140042446  cmova   rcx, [rbp+57h+S2]; void *
0x14004244b  mov     [rsp+0F0h+var_D0], r14; __int64
0x140042450  mov     r9, r15
0x140042453  mov     r8, rdi
0x140042456  call    __std_regex_transform_primary_wchar_t
0x14004245b  mov     rbx, rax
0x14004245e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140042462  jz      short loc_14004246C
0x140042464  cmp     [rbp+57h+var_70], rax
0x140042468  jb      short loc_140042424
0x14004246a  jmp     short loc_14004246E
0x14004246c  xor     ebx, ebx
0x14004246e  mov     rdx, rbx
0x140042471  lea     rcx, [rbp+57h+S2]; Src
0x140042475  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x14004247a  nop
0x14004247b  lea     rcx, [rbp+57h+S1]
0x14004247f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140042484  cmp     [rbp+57h+var_70], 0
0x140042489  jz      loc_140042687
0x14004248f  xor     edi, edi
0x140042491  mov     r12, [rbp+57h+var_B8]
0x140042495  mov     [rbp+57h+var_C0], di
0x140042499  mov     rcx, [r12+18h]
0x14004249e  xorps   xmm0, xmm0
0x1400424a1  movups  xmmword ptr [rbp+57h+S1], xmm0
0x1400424a5  mov     [rbp+57h+N], 0
0x1400424ad  mov     [rbp+57h+var_88], 7
0x1400424b5  xor     eax, eax
0x1400424b7  mov     word ptr [rbp+57h+S1], ax
0x1400424bb  or      esi, 2
0x1400424be  mov     [rbp+57h+var_BC], esi
0x1400424c1  mov     r15, [rcx]
0x1400424c4  mov     rcx, r15
0x1400424c7  call    cs:__imp___RTtypeid
0x1400424cd  lea     rbx, [rax+8]
0x1400424d1  lea     rdx, qword_1400CBB60
0x1400424d8  mov     rcx, rbx
0x1400424db  call    cs:__imp___std_type_info_compare
0x1400424e1  test    eax, eax
0x1400424e3  jz      short loc_1400424FD
0x1400424e5  lea     rdx, qword_1400CBB38
0x1400424ec  mov     rcx, rbx
0x1400424ef  call    cs:__imp___std_type_info_compare
0x1400424f5  test    eax, eax
0x1400424f7  jnz     loc_1400425AD
0x1400424fd  xorps   xmm0, xmm0
0x140042500  movups  [rbp+57h+var_60], xmm0
0x140042504  mov     [rbp+57h+var_50], 0
0x14004250c  mov     [rbp+57h+var_48], 0
0x140042514  mov     r8d, 1
0x14004251a  lea     rdx, [rbp+57h+var_C0]
0x14004251e  lea     rcx, [rbp+57h+var_60]
0x140042522  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x140042527  nop
0x140042528  lea     r14, [rbp+57h+var_60]
0x14004252c  cmp     [rbp+57h+var_48], 7
0x140042531  cmova   r14, qword ptr [rbp+57h+var_60]
0x140042536  mov     rbx, [rbp+57h+var_50]
0x14004253a  lea     rax, [r14+rbx*2]
0x14004253e  mov     [rbp+57h+var_B8], rax
0x140042542  cmp     [rbp+57h+N], rbx
0x140042546  jnb     short loc_140042597
0x140042548  add     r15, 10h
0x14004254c  mov     rdx, rbx
0x14004254f  lea     rcx, [rbp+57h+S1]; Src
0x140042553  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x140042558  lea     rax, [rbp+57h+S1]
0x14004255c  cmp     [rbp+57h+var_88], 7
0x140042561  cmova   rax, [rbp+57h+S1]
0x140042566  lea     rdx, [rax+rbx*2]
0x14004256a  lea     rcx, [rbp+57h+S1]
0x14004256e  cmova   rcx, [rbp+57h+S1]; void *
0x140042573  mov     [rsp+0F0h+var_D0], r15; __int64
0x140042578  mov     r9, [rbp+57h+var_B8]
0x14004257c  mov     r8, r14
0x14004257f  call    __std_regex_transform_primary_wchar_t
0x140042584  mov     rbx, rax
0x140042587  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14004258b  jz      short loc_140042595
0x14004258d  cmp     [rbp+57h+N], rax
0x140042591  jb      short loc_14004254C
0x140042593  jmp     short loc_140042597
0x140042595  xor     ebx, ebx
0x140042597  mov     rdx, rbx
0x14004259a  lea     rcx, [rbp+57h+S1]; Src
0x14004259e  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x1400425a3  nop
0x1400425a4  lea     rcx, [rbp+57h+var_60]
0x1400425a8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400425ad  lea     rdx, [rbp+57h+S2]
0x1400425b1  cmp     [rbp+57h+var_68], 7
0x1400425b6  cmova   rdx, [rbp+57h+S2]; S2
0x1400425bb  mov     r8, [rbp+57h+N]; N
0x1400425bf  lea     rcx, [rbp+57h+S1]
0x1400425c3  cmp     [rbp+57h+var_88], 7
0x1400425c8  cmova   rcx, [rbp+57h+S1]; S1
0x1400425cd  cmp     r8, [rbp+57h+var_70]
0x1400425d1  jz      short loc_1400425D7
0x1400425d3  xor     bl, bl
0x1400425d5  jmp     short loc_1400425EA
0x1400425d7  test    r8, r8
0x1400425da  jnz     short loc_1400425E0
0x1400425dc  mov     bl, 1
0x1400425de  jmp     short loc_1400425EA
0x1400425e0  call    wmemcmp
0x1400425e5  test    eax, eax
0x1400425e7  setz    bl
0x1400425ea  and     esi, 0FFFFFFFDh
0x1400425ed  mov     [rbp+57h+var_BC], esi
0x1400425f0  lea     rcx, [rbp+57h+S1]
0x1400425f4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400425f9  test    bl, bl
0x1400425fb  jz      short loc_140042637
0x1400425fd  mov     rdx, [r13+28h]
0x140042601  test    rdx, rdx
0x140042604  jnz     short loc_14004261F
0x140042606  lea     ecx, [rdx+20h]; Size
0x140042609  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14004260e  mov     rdx, rax
0x140042611  xorps   xmm0, xmm0
0x140042614  movups  xmmword ptr [rax], xmm0
0x140042617  movups  xmmword ptr [rax+10h], xmm0
0x14004261b  mov     [r13+28h], rax
0x14004261f  mov     r9d, edi
0x140042622  shr     r9, 3
0x140042626  movzx   ecx, byte ptr [r9+rdx]
0x14004262b  mov     eax, edi
0x14004262d  and     eax, 7
0x140042630  bts     ecx, eax
0x140042633  mov     [r9+rdx], cl
0x140042637  inc     edi
0x140042639  cmp     edi, 100h
0x14004263f  jb      loc_140042495
0x140042645  lea     r9, [r13+48h]
0x140042649  mov     r8, [rbp+57h+var_B0]
0x14004264d  mov     rdx, [rbp+57h+var_A8]
0x140042651  call    ?_Char_to_elts@?$_Builder2@PEB_W_WV?$regex_traits@_W@std@@@std@@AEAAXPEB_W0PEAPEAU?$_Sequence@_W@2@@Z; std::_Builder2<wchar_t const *,wchar_t,std::regex_traits<wchar_t>>::_Char_to_elts(wchar_t const *,wchar_t const *,std::_Sequence<wchar_t> * *)
0x140042656  nop
0x140042657  lea     rcx, [rbp+57h+S2]
0x14004265b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140042660  mov     rcx, [rbp+57h+var_40]
0x140042664  xor     rcx, rsp; StackCookie
0x140042667  call    __security_check_cookie
0x14004266c  mov     rbx, [rsp+0F0h+arg_18]
0x140042674  add     rsp, 0C0h
0x14004267b  pop     r15
0x14004267d  pop     r14
0x14004267f  pop     r13
0x140042681  pop     r12
0x140042683  pop     rdi
0x140042684  pop     rsi
0x140042685  pop     rbp
0x140042686  retn
0x140042687  xor     ecx, ecx
0x140042689  call    cs:__imp_?_Xregex_error@std@@YAXW4error_type@regex_constants@1@@Z; std::_Xregex_error(std::regex_constants::error_type)
```
