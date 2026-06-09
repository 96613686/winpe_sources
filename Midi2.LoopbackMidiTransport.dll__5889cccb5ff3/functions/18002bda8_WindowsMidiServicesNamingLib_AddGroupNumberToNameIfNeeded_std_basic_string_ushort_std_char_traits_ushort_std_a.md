# WindowsMidiServicesNamingLib::AddGroupNumberToNameIfNeeded(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,uchar)

- ea: `0x18002bda8`
- end: `0x18002c0d7`
- name: `?AddGroupNumberToNameIfNeeded@WindowsMidiServicesNamingLib@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@00E@Z`
- size: `815`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, wchar_t *S2@<rdx>, wchar_t *@<r8>, char)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task`

## callers

- `0x18002c41c`

## callees

- `0x180004180`
- `0x180005000`
- `0x18000b740`
- `0x18000e178`
- `0x18000e5a0`
- `0x18000e820`
- `0x18000f0a4`
- `0x18000feb0`
- `0x1800134cc`
- `0x180014ab8`
- `0x18002bda8`
- `0x18002febc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18002bef9`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18002bef9`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void *__fastcall WindowsMidiServicesNamingLib::AddGroupNumberToNameIfNeeded(
        void *Src,
        wchar_t *S2,
        wchar_t *a3,
        const wchar_t *a4,
        unsigned __int8 a5)
{
  const wchar_t *v5; // rbx
  __int64 v9; // rdx
  size_t v10; // r8
  const wchar_t *v11; // rcx
  unsigned __int64 v12; // rax
  __int64 v13; // rdx
  const wchar_t *v14; // rcx
  _QWORD *v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rdx
  _QWORD *v18; // rax
  __int128 *v19; // rcx
  int v20; // eax
  void **v21; // rcx
  unsigned __int64 v22; // rsi
  __int64 v23; // r8
  __int128 *v24; // rcx
  __int128 *appended; // rcx
  void **v26; // r9
  __int64 v27; // rcx
  __int64 v28; // rdi
  __int128 *v29; // rbx
  __int128 *v30; // rax
  void *v31; // rax
  __int128 v33; // [rsp+40h] [rbp-91h] BYREF
  __int128 v34; // [rsp+50h] [rbp-81h]
  __int128 v35; // [rsp+60h] [rbp-71h] BYREF
  __int128 v36; // [rsp+70h] [rbp-61h]
  _QWORD v37[2]; // [rsp+80h] [rbp-51h] BYREF
  unsigned __int64 v38; // [rsp+90h] [rbp-41h]
  unsigned __int64 v39; // [rsp+98h] [rbp-39h]
  void *Srca[4]; // [rsp+A0h] [rbp-31h] BYREF
  _OWORD v41[2]; // [rsp+C0h] [rbp-11h] BYREF

  v5 = a4;
  std::wstring::wstring(v37, a4);
  v9 = *((_QWORD *)S2 + 2);
  if ( *((_QWORD *)S2 + 3) > 7u )
    S2 = *(wchar_t **)S2;
  v10 = *((_QWORD *)v5 + 2);
  v11 = v5;
  v12 = *((_QWORD *)v5 + 3);
  if ( v12 > 7 )
    v11 = *(const wchar_t **)v5;
  if ( v10 != v9 )
  {
LABEL_9:
    v13 = *((_QWORD *)a3 + 2);
    if ( *((_QWORD *)a3 + 3) > 7u )
      a3 = *(wchar_t **)a3;
    v10 = *((_QWORD *)v5 + 2);
    v14 = v5;
    if ( v12 > 7 )
      v14 = *(const wchar_t **)v5;
    if ( v10 != v13 || v10 && wmemcmp(v14, a3, v10) )
      goto LABEL_43;
    goto LABEL_16;
  }
  if ( v10 && wmemcmp(v11, S2, v10) )
  {
    v12 = *((_QWORD *)v5 + 3);
    goto LABEL_9;
  }
LABEL_16:
  if ( a5 )
  {
    v15 = v37;
    if ( v39 > 7 )
      v15 = (_QWORD *)v37[0];
    v16 = std::_Traits_find_last_not_of<std::char_traits<unsigned short>>(v15, v38, v10, L"0123456789", 10);
    if ( v16 != -1 )
    {
      v17 = v16 + 1;
      if ( v16 + 1 <= v38 )
      {
        v33 = 0;
        v34 = 0;
        v18 = v37;
        if ( v39 > 7 )
          v18 = (_QWORD *)v37[0];
        std::wstring::_Construct<1,unsigned short const *>(&v33, (char *)v18 + 2 * v17);
        v19 = &v33;
        if ( *((_QWORD *)&v34 + 1) > 7u )
          v19 = (__int128 *)v33;
        v20 = _o__wtoi(v19);
        v21 = (void **)&v33;
        if ( v20 == (unsigned __int16)(a5 + 1) )
          goto LABEL_42;
        std::wstring::~wstring(&v33);
      }
    }
    std::to_wstring(Srca);
    v33 = 0;
    v34 = 0;
    v22 = (unsigned __int64)Srca[2];
    if ( *((_QWORD *)v5 + 3) > 7u )
      v5 = *(const wchar_t **)v5;
    std::wstring::_Construct<1,unsigned short const *>(&v33, v5);
    v23 = v34;
    v24 = &v33;
    if ( *((_QWORD *)&v34 + 1) == (_QWORD)v34 )
    {
      appended = (__int128 *)____Reallocate_grow_by_V_lambda_1___1_____Append_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG_K___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Append_G_01_AEAAAEAV01_QEBG0_Z_PEBG_K_Z(
                               &v33,
                               1);
    }
    else
    {
      *(_QWORD *)&v34 = v34 + 1;
      if ( *((_QWORD *)&v34 + 1) > 7u )
        v24 = (__int128 *)v33;
      *((_WORD *)v24 + v23) = 32;
      *((_WORD *)v24 + v23 + 1) = 0;
      appended = &v33;
    }
    v35 = 0;
    v36 = 0;
    v35 = *appended;
    v36 = appended[1];
    *(_WORD *)appended = 0;
    *((_QWORD *)appended + 2) = 0;
    *((_QWORD *)appended + 3) = 7;
    v26 = Srca;
    if ( Srca[3] > (void *)7 )
      v26 = (void **)Srca[0];
    v27 = v36;
    if ( v22 > *((_QWORD *)&v36 + 1) - (_QWORD)v36 )
    {
      v30 = (__int128 *)____Reallocate_grow_by_V_lambda_1___1_____Append_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG_K___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Append_G_01_AEAAAEAV01_QEBG0_Z_PEBG_K_Z(
                          &v35,
                          v22);
    }
    else
    {
      v28 = v36 + v22;
      *(_QWORD *)&v36 = v36 + v22;
      v29 = &v35;
      if ( *((_QWORD *)&v36 + 1) > 7u )
        v29 = (__int128 *)v35;
      memmove_0((char *)v29 + 2 * v27, v26, 2 * v22);
      *((_WORD *)v29 + v28) = 0;
      v30 = &v35;
    }
    v41[0] = *v30;
    v41[1] = v30[1];
    *(_WORD *)v30 = 0;
    *((_QWORD *)v30 + 2) = 0;
    *((_QWORD *)v30 + 3) = 7;
    std::wstring::operator=(v37, v41);
    std::wstring::~wstring(v41);
    std::wstring::~wstring(&v35);
    std::wstring::~wstring(&v33);
    v21 = Srca;
LABEL_42:
    std::wstring::~wstring(v21);
  }
LABEL_43:
  v31 = (void *)std::wstring::wstring(v41, v37);
  WindowsMidiServicesInternal::TrimmedWStringCopy(Src, v31);
  std::wstring::~wstring(v37);
  return Src;
}

```

## disassembly

```asm
0x18002bda8  push    rbp
0x18002bdaa  push    rbx
0x18002bdab  push    rsi
0x18002bdac  push    rdi
0x18002bdad  push    r12
0x18002bdaf  push    r13
0x18002bdb1  push    r14
0x18002bdb3  lea     rbp, [rsp-1Fh]
0x18002bdb8  sub     rsp, 0F0h
0x18002bdbf  mov     rax, cs:__security_cookie
0x18002bdc6  xor     rax, rsp
0x18002bdc9  mov     [rbp+4Fh+var_40], rax
0x18002bdcd  mov     rbx, r9
0x18002bdd0  mov     rdi, r8
0x18002bdd3  mov     rsi, rdx
0x18002bdd6  mov     r14, rcx
0x18002bdd9  mov     [rsp+120h+var_E8], rcx
0x18002bdde  mov     rdx, r9
0x18002bde1  lea     rcx, [rbp+4Fh+var_A0]
0x18002bde5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002bdea  nop
0x18002bdeb  mov     rdx, [rsi+10h]
0x18002bdef  mov     r12d, 7
0x18002bdf5  cmp     [rsi+18h], r12
0x18002bdf9  jbe     short loc_18002BDFE
0x18002bdfb  mov     rsi, [rsi]
0x18002bdfe  mov     r8, [rbx+10h]; N
0x18002be02  mov     rcx, rbx
0x18002be05  mov     rax, [rbx+18h]
0x18002be09  cmp     rax, r12
0x18002be0c  jbe     short loc_18002BE11
0x18002be0e  mov     rcx, [rbx]; S1
0x18002be11  cmp     r8, rdx
0x18002be14  jnz     short loc_18002BE2B
0x18002be16  test    r8, r8
0x18002be19  jz      short loc_18002BE65
0x18002be1b  mov     rdx, rsi; S2
0x18002be1e  call    wmemcmp
0x18002be23  test    eax, eax
0x18002be25  jz      short loc_18002BE65
0x18002be27  mov     rax, [rbx+18h]
0x18002be2b  mov     rdx, [rdi+10h]
0x18002be2f  cmp     [rdi+18h], r12
0x18002be33  jbe     short loc_18002BE38
0x18002be35  mov     rdi, [rdi]
0x18002be38  mov     r8, [rbx+10h]; N
0x18002be3c  mov     rcx, rbx
0x18002be3f  cmp     rax, r12
0x18002be42  jbe     short loc_18002BE47
0x18002be44  mov     rcx, [rbx]; S1
0x18002be47  cmp     r8, rdx
0x18002be4a  jnz     loc_18002C094
0x18002be50  test    r8, r8
0x18002be53  jz      short loc_18002BE65
0x18002be55  mov     rdx, rdi; S2
0x18002be58  call    wmemcmp
0x18002be5d  test    eax, eax
0x18002be5f  jnz     loc_18002C094
0x18002be65  movzx   edi, [rbp+4Fh+arg_20]
0x18002be69  test    dil, dil
0x18002be6c  jz      loc_18002C094
0x18002be72  lea     rcx, [rbp+4Fh+var_A0]
0x18002be76  cmp     [rbp+4Fh+var_88], r12
0x18002be7a  cmova   rcx, [rbp+4Fh+var_A0]
0x18002be7f  mov     [rsp+120h+var_100], 0Ah
0x18002be88  lea     r9, a0123456789; "0123456789"
0x18002be8f  mov     rdx, [rbp+4Fh+var_90]
0x18002be93  call    ??$_Traits_find_last_not_of@U?$char_traits@G@std@@@std@@YA_KQEBG_K101@Z; std::_Traits_find_last_not_of<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort const * const,unsigned __int64)
0x18002be98  mov     r13d, 1
0x18002be9e  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002bea2  cmp     rax, r8
0x18002bea5  jz      short loc_18002BF18
0x18002bea7  mov     rcx, [rbp+4Fh+var_90]
0x18002beab  lea     rdx, [rax+1]
0x18002beaf  cmp     rdx, rcx
0x18002beb2  ja      short loc_18002BF18
0x18002beb4  xorps   xmm0, xmm0
0x18002beb7  movups  [rsp+120h+var_E0], xmm0
0x18002bebc  xorps   xmm1, xmm1
0x18002bebf  movdqu  [rsp+120h+var_D0], xmm1
0x18002bec5  sub     rcx, rdx
0x18002bec8  cmp     rcx, r8
0x18002becb  cmovb   r8, rcx
0x18002becf  lea     rax, [rbp+4Fh+var_A0]
0x18002bed3  cmp     [rbp+4Fh+var_88], r12
0x18002bed7  cmova   rax, [rbp+4Fh+var_A0]
0x18002bedc  lea     rdx, [rax+rdx*2]
0x18002bee0  lea     rcx, [rsp+120h+var_E0]
0x18002bee5  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002beea  lea     rcx, [rsp+120h+var_E0]
0x18002beef  cmp     qword ptr [rbp+4Fh+var_D0+8], r12
0x18002bef3  cmova   rcx, qword ptr [rsp+120h+var_E0]
0x18002bef9  call    cs:__imp__o__wtoi
0x18002beff  lea     ecx, [rdi+r13]
0x18002bf03  movzx   ecx, cx
0x18002bf06  cmp     eax, ecx
0x18002bf08  lea     rcx, [rsp+120h+var_E0]; void *
0x18002bf0d  jz      loc_18002C08F
0x18002bf13  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002bf18  lea     edx, [rdi+r13]
0x18002bf1c  lea     rcx, [rbp+4Fh+Src]; void *
0x18002bf20  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@H@Z; std::to_wstring(int)
0x18002bf25  nop
0x18002bf26  xorps   xmm0, xmm0
0x18002bf29  movups  [rsp+120h+var_E0], xmm0
0x18002bf2e  xorps   xmm1, xmm1
0x18002bf31  movdqu  [rsp+120h+var_D0], xmm1
0x18002bf37  mov     r8, [rbx+10h]
0x18002bf3b  mov     eax, 1Eh
0x18002bf40  mov     rsi, [rbp+4Fh+var_70]
0x18002bf44  sub     rax, rsi
0x18002bf47  cmp     r8, rax
0x18002bf4a  cmovnb  r8, rax
0x18002bf4e  cmp     [rbx+18h], r12
0x18002bf52  jbe     short loc_18002BF57
0x18002bf54  mov     rbx, [rbx]
0x18002bf57  mov     rdx, rbx
0x18002bf5a  lea     rcx, [rsp+120h+var_E0]
0x18002bf5f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002bf64  nop
0x18002bf65  mov     r8, qword ptr [rsp+120h+var_D0]
0x18002bf6a  mov     rax, qword ptr [rbp+4Fh+var_D0+8]
0x18002bf6e  sub     rax, r8
0x18002bf71  lea     rcx, [rsp+120h+var_E0]; Src
0x18002bf76  cmp     rax, r13
0x18002bf79  jb      short loc_18002BFA2
0x18002bf7b  lea     rdx, [r8+1]
0x18002bf7f  mov     qword ptr [rsp+120h+var_D0], rdx
0x18002bf84  cmp     qword ptr [rbp+4Fh+var_D0+8], r12
0x18002bf88  cmova   rcx, qword ptr [rsp+120h+var_E0]
0x18002bf8e  mov     word ptr [rcx+r8*2], 20h ; ' '
0x18002bf95  xor     eax, eax
0x18002bf97  mov     [rcx+rdx*2], ax
0x18002bf9b  lea     rcx, [rsp+120h+var_E0]
0x18002bfa0  jmp     short loc_18002BFB9
0x18002bfa2  mov     [rsp+120h+var_100], r13; __int64
0x18002bfa7  lea     r9, asc_180053C68; " "
0x18002bfae  mov     rdx, r13
0x18002bfb1  call    ??$_Reallocate_grow_by@V_lambda_1_@?1???$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Append@G@01@AEAAAEAV01@QEBG0@Z@PEBG_K@Z; std::wstring::_Reallocate_grow_by<`std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *,unsigned __int64>(unsigned __int64,`std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *,unsigned __int64)
0x18002bfb6  mov     rcx, rax
0x18002bfb9  xorps   xmm0, xmm0
0x18002bfbc  movups  [rbp+4Fh+var_C0], xmm0
0x18002bfc0  xorps   xmm1, xmm1
0x18002bfc3  movdqu  [rbp+4Fh+var_B0], xmm1
0x18002bfc8  movups  xmm0, xmmword ptr [rcx]
0x18002bfcb  movups  [rbp+4Fh+var_C0], xmm0
0x18002bfcf  movups  xmm1, xmmword ptr [rcx+10h]
0x18002bfd3  movups  [rbp+4Fh+var_B0], xmm1
0x18002bfd7  xor     eax, eax
0x18002bfd9  mov     [rcx], ax
0x18002bfdc  mov     [rcx+10h], rax
0x18002bfe0  mov     [rcx+18h], r12
0x18002bfe4  lea     r9, [rbp+4Fh+Src]
0x18002bfe8  cmp     [rbp+4Fh+var_68], r12
0x18002bfec  cmova   r9, [rbp+4Fh+Src]
0x18002bff1  mov     rcx, qword ptr [rbp+4Fh+var_B0]
0x18002bff5  mov     rax, qword ptr [rbp+4Fh+var_B0+8]
0x18002bff9  sub     rax, rcx
0x18002bffc  cmp     rsi, rax
0x18002bfff  ja      short loc_18002C032
0x18002c001  lea     rdi, [rcx+rsi]
0x18002c005  mov     qword ptr [rbp+4Fh+var_B0], rdi
0x18002c009  lea     rbx, [rbp+4Fh+var_C0]
0x18002c00d  cmp     qword ptr [rbp+4Fh+var_B0+8], r12
0x18002c011  cmova   rbx, qword ptr [rbp+4Fh+var_C0]
0x18002c016  lea     r8, [rsi+rsi]; Size
0x18002c01a  lea     rcx, [rbx+rcx*2]; void *
0x18002c01e  mov     rdx, r9; Src
0x18002c021  call    memmove_0
0x18002c026  xor     eax, eax
0x18002c028  mov     [rbx+rdi*2], ax
0x18002c02c  lea     rax, [rbp+4Fh+var_C0]
0x18002c030  jmp     short loc_18002C043
0x18002c032  mov     [rsp+120h+var_100], rsi; __int64
0x18002c037  mov     rdx, rsi
0x18002c03a  lea     rcx, [rbp+4Fh+var_C0]; Src
0x18002c03e  call    ??$_Reallocate_grow_by@V_lambda_1_@?1???$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Append@G@01@AEAAAEAV01@QEBG0@Z@PEBG_K@Z; std::wstring::_Reallocate_grow_by<`std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *,unsigned __int64>(unsigned __int64,`std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *,unsigned __int64)
0x18002c043  movups  xmm0, xmmword ptr [rax]
0x18002c046  movups  [rbp+4Fh+var_60], xmm0
0x18002c04a  movups  xmm1, xmmword ptr [rax+10h]
0x18002c04e  movups  [rbp+4Fh+var_50], xmm1
0x18002c052  xor     ecx, ecx
0x18002c054  mov     [rax], cx
0x18002c057  mov     [rax+10h], rcx
0x18002c05b  mov     [rax+18h], r12
0x18002c05f  lea     rdx, [rbp+4Fh+var_60]
0x18002c063  lea     rcx, [rbp+4Fh+var_A0]
0x18002c067  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002c06c  lea     rcx, [rbp+4Fh+var_60]; void *
0x18002c070  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c075  nop
0x18002c076  lea     rcx, [rbp+4Fh+var_C0]; void *
0x18002c07a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c07f  nop
0x18002c080  lea     rcx, [rsp+120h+var_E0]; void *
0x18002c085  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c08a  nop
0x18002c08b  lea     rcx, [rbp+4Fh+Src]; void *
0x18002c08f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c094  lea     rdx, [rbp+4Fh+var_A0]
0x18002c098  lea     rcx, [rbp+4Fh+var_60]
0x18002c09c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002c0a1  mov     rdx, rax; void *
0x18002c0a4  mov     rcx, r14; Src
0x18002c0a7  call    ?TrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::TrimmedWStringCopy(std::wstring)
0x18002c0ac  nop
0x18002c0ad  lea     rcx, [rbp+4Fh+var_A0]; void *
0x18002c0b1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c0b6  mov     rax, r14
0x18002c0b9  mov     rcx, [rbp+4Fh+var_40]
0x18002c0bd  xor     rcx, rsp; StackCookie
0x18002c0c0  call    __security_check_cookie
0x18002c0c5  add     rsp, 0F0h
0x18002c0cc  pop     r14
0x18002c0ce  pop     r13
0x18002c0d0  pop     r12
0x18002c0d2  pop     rdi
0x18002c0d3  pop     rsi
0x18002c0d4  pop     rbx
0x18002c0d5  pop     rbp
0x18002c0d6  retn
```
