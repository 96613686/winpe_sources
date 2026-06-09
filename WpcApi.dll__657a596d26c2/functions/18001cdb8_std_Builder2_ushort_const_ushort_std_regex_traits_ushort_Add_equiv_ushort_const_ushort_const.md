# std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_Add_equiv(ushort const *,ushort const *)

- ea: `0x18001cdb8`
- end: `0x18001d118`
- name: `?_Add_equiv@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@QEAAXPEBG0@Z`
- size: `864`
- prototype: `__int64 __fastcall(char *, _BYTE *, _BYTE *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18001e824`

## callees

- `0x1800032a0`
- `0x1800032c4`
- `0x180003ea8`
- `0x180005950`
- `0x180005f9c`
- `0x18000b498`
- `0x18001cdb8`
- `0x18001decc`
- `0x18001fa1c`

## import_xrefs

- `msvcp_win!?_Xregex_error@std@@YAXW4error_type@regex_constants@1@@Z` at `0x18001d111`
- `msvcp_win!?_Xregex_error@std@@YAXW4error_type@regex_constants@1@@Z` at `0x18001d111`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18001ce45`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18001ce59`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18001cf63`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18001cf77`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18001ce45`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18001ce59`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18001cf63`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18001cf77`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x18001ce31`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x18001cf4f`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x18001ce31`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x18001cf4f`

## pseudocode

```c
__int64 __fastcall std::_Builder2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Add_equiv(
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
  if ( !(unsigned int)__std_type_info_compare(v8, &qword_180044920)
    || !(unsigned int)__std_type_info_compare(v8, &qword_1800448F8) )
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
    std::wstring::~wstring((char **)S1);
  }
  if ( !v38 )
  {
LABEL_39:
    std::_Xregex_error(0);
    JUMPOUT(0x18001D117LL);
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
    if ( !(unsigned int)__std_type_info_compare(v17, &qword_180044920)
      || !(unsigned int)__std_type_info_compare(v17, &qword_1800448F8) )
    {
      v40 = 0;
      v41 = 0;
      v42 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v40, v29, 1u);
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
      std::wstring::~wstring((char **)&v40);
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
    std::wstring::~wstring((char **)S1);
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
  return std::wstring::~wstring((char **)S2);
}

```

## disassembly

```asm
0x18001cdb8  mov     [rsp-8+arg_18], rbx
0x18001cdbd  push    rbp
0x18001cdbe  push    rsi
0x18001cdbf  push    rdi
0x18001cdc0  push    r12
0x18001cdc2  push    r13
0x18001cdc4  push    r14
0x18001cdc6  push    r15
0x18001cdc8  lea     rbp, [rsp-27h]
0x18001cdcd  sub     rsp, 0C0h
0x18001cdd4  mov     rax, cs:__security_cookie
0x18001cddb  xor     rax, rsp
0x18001cdde  mov     [rbp+57h+var_40], rax
0x18001cde2  mov     rdi, r8
0x18001cde5  mov     [rbp+57h+var_B0], r8
0x18001cde9  mov     r12, rdx
0x18001cdec  mov     [rbp+57h+var_A8], rdx
0x18001cdf0  mov     [rbp+57h+var_B8], rcx
0x18001cdf4  xor     r15d, r15d
0x18001cdf7  mov     [rbp+57h+var_BC], r15d
0x18001cdfb  xorps   xmm0, xmm0
0x18001cdfe  movups  xmmword ptr [rbp+57h+S2], xmm0
0x18001ce02  mov     [rbp+57h+var_70], r15
0x18001ce06  mov     [rbp+57h+var_68], 7
0x18001ce0e  mov     word ptr [rbp+57h+S2], r15w
0x18001ce13  lea     esi, [r15+1]
0x18001ce17  mov     [rbp+57h+var_BC], esi
0x18001ce1a  cmp     rdx, r8
0x18001ce1d  jz      loc_18001D10F
0x18001ce23  mov     r13, [rcx+8]
0x18001ce27  mov     rax, [rcx+18h]
0x18001ce2b  mov     r14, [rax]
0x18001ce2e  mov     rcx, r14
0x18001ce31  call    cs:__imp___RTtypeid
0x18001ce37  lea     rbx, [rax+8]
0x18001ce3b  lea     rdx, qword_180044920
0x18001ce42  mov     rcx, rbx
0x18001ce45  call    cs:__imp___std_type_info_compare
0x18001ce4b  test    eax, eax
0x18001ce4d  jz      short loc_18001CE67
0x18001ce4f  lea     rdx, qword_1800448F8
0x18001ce56  mov     rcx, rbx
0x18001ce59  call    cs:__imp___std_type_info_compare
0x18001ce5f  test    eax, eax
0x18001ce61  jnz     loc_18001CF0C
0x18001ce67  xorps   xmm0, xmm0
0x18001ce6a  movups  xmmword ptr [rbp+57h+S1], xmm0
0x18001ce6e  mov     [rbp+57h+N], r15
0x18001ce72  mov     [rbp+57h+var_88], r15
0x18001ce76  mov     r8, rdi
0x18001ce79  sub     r8, r12
0x18001ce7c  sar     r8, 1
0x18001ce7f  mov     rdx, r12
0x18001ce82  lea     rcx, [rbp+57h+S1]
0x18001ce86  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001ce8b  nop
0x18001ce8c  lea     rdi, [rbp+57h+S1]
0x18001ce90  cmp     [rbp+57h+var_88], 7
0x18001ce95  cmova   rdi, [rbp+57h+S1]
0x18001ce9a  mov     rbx, [rbp+57h+N]
0x18001ce9e  lea     r15, [rdi+rbx*2]
0x18001cea2  cmp     [rbp+57h+var_70], rbx
0x18001cea6  jnb     short loc_18001CEF6
0x18001cea8  add     r14, 10h
0x18001ceac  mov     rdx, rbx
0x18001ceaf  lea     rcx, [rbp+57h+S2]; Src
0x18001ceb3  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18001ceb8  lea     rax, [rbp+57h+S2]
0x18001cebc  cmp     [rbp+57h+var_68], 7
0x18001cec1  cmova   rax, [rbp+57h+S2]
0x18001cec6  lea     rdx, [rax+rbx*2]
0x18001ceca  lea     rcx, [rbp+57h+S2]
0x18001cece  cmova   rcx, [rbp+57h+S2]; void *
0x18001ced3  mov     [rsp+0F0h+var_D0], r14; __int64
0x18001ced8  mov     r9, r15
0x18001cedb  mov     r8, rdi
0x18001cede  call    __std_regex_transform_primary_wchar_t
0x18001cee3  mov     rbx, rax
0x18001cee6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001ceea  jz      short loc_18001CEF4
0x18001ceec  cmp     [rbp+57h+var_70], rax
0x18001cef0  jb      short loc_18001CEAC
0x18001cef2  jmp     short loc_18001CEF6
0x18001cef4  xor     ebx, ebx
0x18001cef6  mov     rdx, rbx
0x18001cef9  lea     rcx, [rbp+57h+S2]; Src
0x18001cefd  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18001cf02  nop
0x18001cf03  lea     rcx, [rbp+57h+S1]
0x18001cf07  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001cf0c  cmp     [rbp+57h+var_70], 0
0x18001cf11  jz      loc_18001D10F
0x18001cf17  xor     edi, edi
0x18001cf19  mov     r12, [rbp+57h+var_B8]
0x18001cf1d  mov     [rbp+57h+var_C0], di
0x18001cf21  mov     rcx, [r12+18h]
0x18001cf26  xorps   xmm0, xmm0
0x18001cf29  movups  xmmword ptr [rbp+57h+S1], xmm0
0x18001cf2d  mov     [rbp+57h+N], 0
0x18001cf35  mov     [rbp+57h+var_88], 7
0x18001cf3d  xor     eax, eax
0x18001cf3f  mov     word ptr [rbp+57h+S1], ax
0x18001cf43  or      esi, 2
0x18001cf46  mov     [rbp+57h+var_BC], esi
0x18001cf49  mov     r15, [rcx]
0x18001cf4c  mov     rcx, r15
0x18001cf4f  call    cs:__imp___RTtypeid
0x18001cf55  lea     rbx, [rax+8]
0x18001cf59  lea     rdx, qword_180044920
0x18001cf60  mov     rcx, rbx
0x18001cf63  call    cs:__imp___std_type_info_compare
0x18001cf69  test    eax, eax
0x18001cf6b  jz      short loc_18001CF85
0x18001cf6d  lea     rdx, qword_1800448F8
0x18001cf74  mov     rcx, rbx
0x18001cf77  call    cs:__imp___std_type_info_compare
0x18001cf7d  test    eax, eax
0x18001cf7f  jnz     loc_18001D035
0x18001cf85  xorps   xmm0, xmm0
0x18001cf88  movups  [rbp+57h+var_60], xmm0
0x18001cf8c  mov     [rbp+57h+var_50], 0
0x18001cf94  mov     [rbp+57h+var_48], 0
0x18001cf9c  mov     r8d, 1
0x18001cfa2  lea     rdx, [rbp+57h+var_C0]
0x18001cfa6  lea     rcx, [rbp+57h+var_60]
0x18001cfaa  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001cfaf  nop
0x18001cfb0  lea     r14, [rbp+57h+var_60]
0x18001cfb4  cmp     [rbp+57h+var_48], 7
0x18001cfb9  cmova   r14, qword ptr [rbp+57h+var_60]
0x18001cfbe  mov     rbx, [rbp+57h+var_50]
0x18001cfc2  lea     rax, [r14+rbx*2]
0x18001cfc6  mov     [rbp+57h+var_B8], rax
0x18001cfca  cmp     [rbp+57h+N], rbx
0x18001cfce  jnb     short loc_18001D01F
0x18001cfd0  add     r15, 10h
0x18001cfd4  mov     rdx, rbx
0x18001cfd7  lea     rcx, [rbp+57h+S1]; Src
0x18001cfdb  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18001cfe0  lea     rax, [rbp+57h+S1]
0x18001cfe4  cmp     [rbp+57h+var_88], 7
0x18001cfe9  cmova   rax, [rbp+57h+S1]
0x18001cfee  lea     rdx, [rax+rbx*2]
0x18001cff2  lea     rcx, [rbp+57h+S1]
0x18001cff6  cmova   rcx, [rbp+57h+S1]; void *
0x18001cffb  mov     [rsp+0F0h+var_D0], r15; __int64
0x18001d000  mov     r9, [rbp+57h+var_B8]
0x18001d004  mov     r8, r14
0x18001d007  call    __std_regex_transform_primary_wchar_t
0x18001d00c  mov     rbx, rax
0x18001d00f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001d013  jz      short loc_18001D01D
0x18001d015  cmp     [rbp+57h+N], rax
0x18001d019  jb      short loc_18001CFD4
0x18001d01b  jmp     short loc_18001D01F
0x18001d01d  xor     ebx, ebx
0x18001d01f  mov     rdx, rbx
0x18001d022  lea     rcx, [rbp+57h+S1]; Src
0x18001d026  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18001d02b  nop
0x18001d02c  lea     rcx, [rbp+57h+var_60]
0x18001d030  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d035  lea     rdx, [rbp+57h+S2]
0x18001d039  cmp     [rbp+57h+var_68], 7
0x18001d03e  cmova   rdx, [rbp+57h+S2]; S2
0x18001d043  mov     r8, [rbp+57h+N]; N
0x18001d047  lea     rcx, [rbp+57h+S1]
0x18001d04b  cmp     [rbp+57h+var_88], 7
0x18001d050  cmova   rcx, [rbp+57h+S1]; S1
0x18001d055  cmp     r8, [rbp+57h+var_70]
0x18001d059  jz      short loc_18001D05F
0x18001d05b  xor     bl, bl
0x18001d05d  jmp     short loc_18001D072
0x18001d05f  test    r8, r8
0x18001d062  jnz     short loc_18001D068
0x18001d064  mov     bl, 1
0x18001d066  jmp     short loc_18001D072
0x18001d068  call    wmemcmp
0x18001d06d  test    eax, eax
0x18001d06f  setz    bl
0x18001d072  and     esi, 0FFFFFFFDh
0x18001d075  mov     [rbp+57h+var_BC], esi
0x18001d078  lea     rcx, [rbp+57h+S1]
0x18001d07c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d081  test    bl, bl
0x18001d083  jz      short loc_18001D0BF
0x18001d085  mov     rdx, [r13+28h]
0x18001d089  test    rdx, rdx
0x18001d08c  jnz     short loc_18001D0A7
0x18001d08e  lea     ecx, [rdx+20h]; Size
0x18001d091  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d096  mov     rdx, rax
0x18001d099  xorps   xmm0, xmm0
0x18001d09c  movups  xmmword ptr [rax], xmm0
0x18001d09f  movups  xmmword ptr [rax+10h], xmm0
0x18001d0a3  mov     [r13+28h], rax
0x18001d0a7  mov     r9d, edi
0x18001d0aa  shr     r9, 3
0x18001d0ae  movzx   ecx, byte ptr [r9+rdx]
0x18001d0b3  mov     eax, edi
0x18001d0b5  and     eax, 7
0x18001d0b8  bts     ecx, eax
0x18001d0bb  mov     [r9+rdx], cl
0x18001d0bf  inc     edi
0x18001d0c1  cmp     edi, 100h
0x18001d0c7  jb      loc_18001CF1D
0x18001d0cd  lea     r9, [r13+48h]
0x18001d0d1  mov     r8, [rbp+57h+var_B0]
0x18001d0d5  mov     rdx, [rbp+57h+var_A8]
0x18001d0d9  call    ?_Char_to_elts@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@AEAAXPEBG0PEAPEAU?$_Sequence@G@2@@Z; std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_Char_to_elts(ushort const *,ushort const *,std::_Sequence<ushort> * *)
0x18001d0de  nop
0x18001d0df  lea     rcx, [rbp+57h+S2]
0x18001d0e3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d0e8  mov     rcx, [rbp+57h+var_40]
0x18001d0ec  xor     rcx, rsp; StackCookie
0x18001d0ef  call    __security_check_cookie
0x18001d0f4  mov     rbx, [rsp+0F0h+arg_18]
0x18001d0fc  add     rsp, 0C0h
0x18001d103  pop     r15
0x18001d105  pop     r14
0x18001d107  pop     r13
0x18001d109  pop     r12
0x18001d10b  pop     rdi
0x18001d10c  pop     rsi
0x18001d10d  pop     rbp
0x18001d10e  retn
0x18001d10f  xor     ecx, ecx
0x18001d111  call    cs:__imp_?_Xregex_error@std@@YAXW4error_type@regex_constants@1@@Z; std::_Xregex_error(std::regex_constants::error_type)
```
