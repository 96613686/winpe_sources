# Utility::RemovePiiFromPath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18003dd7c`
- end: `0x18003e1ce`
- name: `?RemovePiiFromPath@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z`
- size: `1106`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x18003c8f0`

## callees

- `0x180004ea0`
- `0x180006c30`
- `0x180006c40`
- `0x18000fb60`
- `0x180011fcc`
- `0x1800134b8`
- `0x1800149a8`
- `0x180014a48`
- `0x1800276fc`
- `0x180027cb0`
- `0x180039288`
- `0x180039db0`
- `0x18003dd7c`
- `0x180042bb0`
- `0x180044868`
- `0x180044a1c`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathUnExpandEnvStringsW` at `0x18003de86`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathUnExpandEnvStringsW` at `0x18003de86`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_OWORD *__fastcall Utility::RemovePiiFromPath(_OWORD *a1, __int64 a2)
{
  __int64 *HklmUserProfilePaths; // rax
  _QWORD *v4; // rsi
  _QWORD *v5; // r12
  unsigned __int64 v6; // rdi
  unsigned __int64 v7; // r9
  _QWORD *v8; // r8
  LPCWSTR *v9; // r15
  char *v10; // rbx
  __int64 v11; // rax
  WCHAR *v12; // rdx
  const WCHAR *v13; // rcx
  LPWSTR *v14; // rax
  __int64 v15; // rdx
  __int64 UserNames; // rax
  __int64 v17; // rdx
  _QWORD *v18; // rsi
  _QWORD *v19; // r12
  __int64 v20; // rdx
  __int64 v21; // r8
  unsigned __int64 v22; // rcx
  unsigned __int64 v23; // r8
  LPCWSTR *v24; // rax
  unsigned __int64 v25; // r9
  _QWORD *v26; // r8
  LPCWSTR *v27; // r15
  char *v28; // rbx
  __int64 v29; // rax
  __int64 v30; // rcx
  __int64 *v31; // r8
  LPCWSTR *v32; // rsi
  __int64 v33; // rax
  char *v34; // rbx
  __int64 v35; // rax
  unsigned __int64 v36; // rsi
  LPCWSTR *v37; // rax
  __int64 v38; // rdx
  __int64 v39; // rcx
  __int128 *v40; // r15
  char *v41; // rbx
  __int64 trivial_2; // rax
  unsigned __int64 v43; // r8
  LPCWSTR *v44; // rax
  LPCWSTR pszPath[2]; // [rsp+30h] [rbp-89h] BYREF
  __int128 v47; // [rsp+40h] [rbp-79h]
  LPWSTR pszBuf[2]; // [rsp+50h] [rbp-69h] BYREF
  __m128i si128; // [rsp+60h] [rbp-59h]
  __int128 v50; // [rsp+70h] [rbp-49h] BYREF
  __m128i v51; // [rsp+80h] [rbp-39h]
  __int128 v52; // [rsp+90h] [rbp-29h] BYREF
  __int64 v53; // [rsp+A0h] [rbp-19h]
  unsigned __int64 v54; // [rsp+A8h] [rbp-11h]
  _OWORD v55[2]; // [rsp+B0h] [rbp-9h] BYREF

  if ( *(_DWORD *)(a2 + 16) > 3u )
  {
    *(_OWORD *)pszBuf = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(pszBuf[0]) = 0;
    Utility::ToLower(pszPath, a2);
    HklmUserProfilePaths = Utility::GetHklmUserProfilePaths();
    v4 = (_QWORD *)*HklmUserProfilePaths;
    v5 = (_QWORD *)HklmUserProfilePaths[1];
    v6 = -1;
    while ( v4 != v5 )
    {
      v7 = v4[2];
      if ( v4[3] <= 7u )
        v8 = v4;
      else
        v8 = (_QWORD *)*v4;
      v9 = pszPath;
      if ( *((_QWORD *)&v47 + 1) > 7u )
        v9 = (LPCWSTR *)pszPath[0];
      if ( v7 <= (unsigned __int64)v47 )
      {
        if ( !v7
          || (v10 = (char *)v9 + 2 * v47, v11 = _std_search_2(v9, v10, v8, v7), (char *)v11 != v10)
          && !((v11 - (__int64)v9) >> 1) )
        {
          std::wstring::operator=(pszBuf, Utility::UserProfileEnvironmentVar);
          v22 = v4[2];
          v50 = 0;
          v51 = 0;
          if ( (unsigned __int64)v47 < v22 )
            std::_String_val<std::_Simple_types<unsigned short>>::_Xran(v22, v20, v21);
          v23 = -1;
          if ( (_QWORD)v47 - v22 != -1 )
            v23 = v47 - v22;
          v24 = pszPath;
          if ( *((_QWORD *)&v47 + 1) > 7u )
            v24 = (LPCWSTR *)pszPath[0];
          std::wstring::_Construct<1,unsigned short const *>((char **)&v50, (char *)v24 + 2 * v22, v23);
          std::wstring::append(pszBuf);
          std::wstring::~wstring((char **)&v50);
          goto LABEL_25;
        }
      }
      v4 += 4;
    }
    std::wstring::resize(pszBuf);
    v12 = (WCHAR *)pszBuf;
    if ( si128.m128i_i64[1] > 7uLL )
      v12 = pszBuf[0];
    v13 = (const WCHAR *)pszPath;
    if ( *((_QWORD *)&v47 + 1) > 7u )
      v13 = pszPath[0];
    if ( PathUnExpandEnvStringsW(v13, v12, 0x104u) )
    {
      v14 = pszBuf;
      if ( si128.m128i_i64[1] > 7uLL )
        v14 = (LPWSTR *)pszBuf[0];
      v15 = -1;
      do
        ++v15;
      while ( *((_WORD *)v14 + v15) );
      std::wstring::resize(pszBuf);
LABEL_25:
      std::wstring::operator=(pszPath, pszBuf);
    }
    UserNames = Utility::GetUserNames();
    v18 = *(_QWORD **)UserNames;
    v19 = *(_QWORD **)(UserNames + 8);
    while ( v18 != v19 )
    {
      v25 = v18[2];
      if ( v18[3] <= 7u )
        v26 = v18;
      else
        v26 = (_QWORD *)*v18;
      v27 = pszPath;
      if ( *((_QWORD *)&v47 + 1) > 7u )
        v27 = (LPCWSTR *)pszPath[0];
      if ( v25 <= (unsigned __int64)v47 )
      {
        if ( !v25
          || (v28 = (char *)v27 + 2 * v47, v29 = _std_search_2(v27, v28, v26, v25), (char *)v29 != v28)
          && (v29 - (__int64)v27) >> 1 != -1 )
        {
          std::wstring::replace(pszPath);
          break;
        }
      }
      v18 += 4;
    }
    v30 = qword_18011BAE0;
    v31 = &Utility::UserNameSearchString;
    if ( (unsigned __int64)qword_18011BAE8 > 7 )
      v31 = (__int64 *)Utility::UserNameSearchString;
    v32 = pszPath;
    if ( *((_QWORD *)&v47 + 1) > 7u )
      v32 = (LPCWSTR *)pszPath[0];
    if ( qword_18011BAE0 > (unsigned __int64)v47 )
    {
      v33 = -1;
    }
    else
    {
      if ( !qword_18011BAE0 )
      {
        v33 = 0;
LABEL_57:
        v36 = v33 + v30;
        v52 = 0;
        v53 = 0;
        v54 = 0;
        if ( (unsigned __int64)v47 < v33 + v30 )
          std::_String_val<std::_Simple_types<unsigned short>>::_Xran(v30, v17, v31);
        v37 = pszPath;
        if ( *((_QWORD *)&v47 + 1) > 7u )
          v37 = (LPCWSTR *)pszPath[0];
        std::wstring::_Construct<1,unsigned short const *>((char **)&v52, (char *)v37 + 2 * v36, v47 - v36);
        v50 = 0;
        v51 = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v50) = 0;
        v40 = &v52;
        if ( v54 > 7 )
          v40 = (__int128 *)v52;
        if ( v53 )
        {
          v41 = (char *)v40 + 2 * v53;
          trivial_2 = _std_find_trivial_2(v40, v41, 92);
          if ( (char *)trivial_2 != v41 )
            v6 = (trivial_2 - (__int64)v40) >> 1;
        }
        memset(v55, 0, sizeof(v55));
        if ( (unsigned __int64)v47 < v36 )
          std::_String_val<std::_Simple_types<unsigned short>>::_Xran(v39, v38, v47);
        v43 = v47 - v36;
        if ( (unsigned __int64)v47 - v36 >= v6 )
          v43 = v6;
        v44 = pszPath;
        if ( *((_QWORD *)&v47 + 1) > 7u )
          v44 = (LPCWSTR *)pszPath[0];
        std::wstring::_Construct<1,unsigned short const *>((char **)v55, (char *)v44 + 2 * v36, v43);
        std::wstring::operator=(&v50, v55);
        std::wstring::~wstring((char **)v55);
        std::wstring::replace(pszPath);
        std::wstring::~wstring((char **)&v50);
        std::wstring::~wstring((char **)&v52);
        goto LABEL_71;
      }
      v34 = (char *)v32 + 2 * v47;
      v35 = _std_search_2(v32, v34, v31, qword_18011BAE0);
      if ( (char *)v35 == v34 )
      {
LABEL_71:
        *a1 = *(_OWORD *)pszPath;
        a1[1] = v47;
        *(_QWORD *)&v47 = 0;
        *((_QWORD *)&v47 + 1) = 7;
        LOWORD(pszPath[0]) = 0;
        std::wstring::~wstring((char **)pszPath);
        std::wstring::~wstring((char **)pszBuf);
        return a1;
      }
      v33 = (v35 - (__int64)v32) >> 1;
      v30 = qword_18011BAE0;
    }
    if ( v33 != -1 )
      goto LABEL_57;
    goto LABEL_71;
  }
  std::wstring::wstring((__int64)a1, a2);
  return a1;
}

```

## disassembly

```asm
0x18003dd7c  mov     [rsp-8+arg_10], rbx
0x18003dd81  push    rbp
0x18003dd82  push    rsi
0x18003dd83  push    rdi
0x18003dd84  push    r12
0x18003dd86  push    r13
0x18003dd88  push    r14
0x18003dd8a  push    r15
0x18003dd8c  lea     rbp, [rsp-27h]
0x18003dd91  sub     rsp, 0E0h
0x18003dd98  mov     rax, cs:__security_cookie
0x18003dd9f  xor     rax, rsp
0x18003dda2  mov     [rbp+57h+var_40], rax
0x18003dda6  mov     r14, rcx
0x18003dda9  mov     [rsp+110h+var_E8], rcx
0x18003ddae  xor     r13d, r13d
0x18003ddb1  cmp     dword ptr [rdx+10h], 3
0x18003ddb5  ja      short loc_18003DDC1
0x18003ddb7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003ddbc  jmp     loc_18003E192
0x18003ddc1  xorps   xmm0, xmm0
0x18003ddc4  movups  xmmword ptr [rbp+57h+pszBuf], xmm0
0x18003ddc8  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18003ddd0  movdqu  [rbp+57h+var_B0], xmm1
0x18003ddd5  mov     word ptr [rbp+57h+pszBuf], r13w
0x18003ddda  lea     rcx, [rsp+110h+pszPath]
0x18003dddf  call    ?ToLower@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::ToLower(std::wstring const &)
0x18003dde4  nop
0x18003dde5  call    ?GetHklmUserProfilePaths@Utility@@SAAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ; Utility::GetHklmUserProfilePaths(void)
0x18003ddea  mov     rsi, [rax]
0x18003dded  mov     r12, [rax+8]
0x18003ddf1  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003ddf5  jmp     short loc_18003DE50
0x18003ddf7  mov     r9, [rsi+10h]
0x18003ddfb  cmp     qword ptr [rsi+18h], 7
0x18003de00  jbe     short loc_18003DE07
0x18003de02  mov     r8, [rsi]
0x18003de05  jmp     short loc_18003DE0A
0x18003de07  mov     r8, rsi
0x18003de0a  mov     rax, qword ptr [rbp+57h+var_D0]
0x18003de0e  lea     r15, [rsp+110h+pszPath]
0x18003de13  cmp     qword ptr [rbp+57h+var_D0+8], 7
0x18003de18  cmova   r15, [rsp+110h+pszPath]
0x18003de1e  cmp     r9, rax
0x18003de21  ja      short loc_18003DE4C
0x18003de23  test    r9, r9
0x18003de26  jz      loc_18003DED3
0x18003de2c  lea     rbx, [r15+rax*2]
0x18003de30  mov     rdx, rbx
0x18003de33  mov     rcx, r15
0x18003de36  call    __std_search_2
0x18003de3b  cmp     rax, rbx
0x18003de3e  jz      short loc_18003DE4C
0x18003de40  sub     rax, r15
0x18003de43  sar     rax, 1
0x18003de46  jz      loc_18003DED3
0x18003de4c  add     rsi, 20h ; ' '
0x18003de50  cmp     rsi, r12
0x18003de53  jnz     short loc_18003DDF7
0x18003de55  mov     ebx, 104h
0x18003de5a  mov     edx, ebx
0x18003de5c  lea     rcx, [rbp+57h+pszBuf]; Src
0x18003de60  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18003de65  lea     rdx, [rbp+57h+pszBuf]
0x18003de69  cmp     qword ptr [rbp+57h+var_B0+8], 7
0x18003de6e  cmova   rdx, [rbp+57h+pszBuf]; pszBuf
0x18003de73  lea     rcx, [rsp+110h+pszPath]
0x18003de78  cmp     qword ptr [rbp+57h+var_D0+8], 7
0x18003de7d  cmova   rcx, [rsp+110h+pszPath]; pszPath
0x18003de83  mov     r8d, ebx; cchBuf
0x18003de86  call    cs:__imp_PathUnExpandEnvStringsW
0x18003de8c  test    eax, eax
0x18003de8e  jz      short loc_18003DEC2
0x18003de90  lea     rax, [rbp+57h+pszBuf]
0x18003de94  cmp     qword ptr [rbp+57h+var_B0+8], 7
0x18003de99  cmova   rax, [rbp+57h+pszBuf]
0x18003de9e  mov     rdx, rdi
0x18003dea1  inc     rdx
0x18003dea4  cmp     [rax+rdx*2], r13w
0x18003dea9  jnz     short loc_18003DEA1
0x18003deab  lea     rcx, [rbp+57h+pszBuf]; Src
0x18003deaf  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18003deb4  lea     rdx, [rbp+57h+pszBuf]
0x18003deb8  lea     rcx, [rsp+110h+pszPath]
0x18003debd  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18003dec2  call    ?GetUserNames@Utility@@SAAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ; Utility::GetUserNames(void)
0x18003dec7  mov     rsi, [rax]
0x18003deca  mov     r12, [rax+8]
0x18003dece  jmp     loc_18003DF9E
0x18003ded3  lea     rdx, ?UserProfileEnvironmentVar@Utility@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Utility::UserProfileEnvironmentVar
0x18003deda  lea     rcx, [rbp+57h+pszBuf]
0x18003dede  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18003dee3  mov     rcx, [rsi+10h]
0x18003dee7  xorps   xmm0, xmm0
0x18003deea  movups  [rbp+57h+var_A0], xmm0
0x18003deee  xorps   xmm1, xmm1
0x18003def1  movdqu  [rbp+57h+var_90], xmm1
0x18003def6  mov     rax, qword ptr [rbp+57h+var_D0]
0x18003defa  cmp     rax, rcx
0x18003defd  jb      loc_18003E1C2
0x18003df03  sub     rax, rcx
0x18003df06  mov     r8, rdi
0x18003df09  cmp     rax, rdi
0x18003df0c  cmovb   r8, rax
0x18003df10  lea     rax, [rsp+110h+pszPath]
0x18003df15  cmp     qword ptr [rbp+57h+var_D0+8], 7
0x18003df1a  cmova   rax, [rsp+110h+pszPath]
0x18003df20  lea     rdx, [rax+rcx*2]
0x18003df24  lea     rcx, [rbp+57h+var_A0]
0x18003df28  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003df2d  nop
0x18003df2e  lea     rdx, [rbp+57h+var_A0]
0x18003df32  lea     rcx, [rbp+57h+pszBuf]; Src
0x18003df36  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18003df3b  nop
0x18003df3c  lea     rcx, [rbp+57h+var_A0]
0x18003df40  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003df45  jmp     loc_18003DEB4
0x18003df4a  mov     r9, [rsi+10h]
0x18003df4e  cmp     qword ptr [rsi+18h], 7
0x18003df53  jbe     short loc_18003DF5A
0x18003df55  mov     r8, [rsi]
0x18003df58  jmp     short loc_18003DF5D
0x18003df5a  mov     r8, rsi
0x18003df5d  mov     rax, qword ptr [rbp+57h+var_D0]
0x18003df61  lea     r15, [rsp+110h+pszPath]
0x18003df66  cmp     qword ptr [rbp+57h+var_D0+8], 7
0x18003df6b  cmova   r15, [rsp+110h+pszPath]
0x18003df71  cmp     r9, rax
0x18003df74  ja      short loc_18003DF9A
0x18003df76  test    r9, r9
0x18003df79  jz      short loc_18003DFA5
0x18003df7b  lea     rbx, [r15+rax*2]
0x18003df7f  mov     rdx, rbx
0x18003df82  mov     rcx, r15
0x18003df85  call    __std_search_2
0x18003df8a  cmp     rax, rbx
0x18003df8d  jz      short loc_18003DF9A
0x18003df8f  sub     rax, r15
0x18003df92  sar     rax, 1
0x18003df95  cmp     rax, rdi
0x18003df98  jnz     short loc_18003DFA8
0x18003df9a  add     rsi, 20h ; ' '
0x18003df9e  cmp     rsi, r12
0x18003dfa1  jnz     short loc_18003DF4A
0x18003dfa3  jmp     short loc_18003DFC0
0x18003dfa5  mov     rax, r13
0x18003dfa8  lea     r9, aXxxx; "xxxx"
0x18003dfaf  mov     r8, [rsi+10h]
0x18003dfb3  mov     rdx, rax
0x18003dfb6  lea     rcx, [rsp+110h+pszPath]; Src
0x18003dfbb  call    ?replace@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0QEBG@Z; std::wstring::replace(unsigned __int64,unsigned __int64,ushort const * const)
0x18003dfc0  mov     rcx, cs:qword_18011BAE0
0x18003dfc7  lea     r8, ?UserNameSearchString@Utility@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Utility::UserNameSearchString
0x18003dfce  cmp     cs:qword_18011BAE8, 7
0x18003dfd6  cmova   r8, cs:?UserNameSearchString@Utility@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Utility::UserNameSearchString
0x18003dfde  mov     rax, qword ptr [rbp+57h+var_D0]
0x18003dfe2  lea     rsi, [rsp+110h+pszPath]
0x18003dfe7  cmp     qword ptr [rbp+57h+var_D0+8], 7
0x18003dfec  cmova   rsi, [rsp+110h+pszPath]
0x18003dff2  cmp     rcx, rax
0x18003dff5  ja      short loc_18003E02B
0x18003dff7  test    rcx, rcx
0x18003dffa  jnz     short loc_18003E001
0x18003dffc  mov     rax, r13
0x18003dfff  jmp     short loc_18003E037
0x18003e001  lea     rbx, [rsi+rax*2]
0x18003e005  mov     r9, rcx
0x18003e008  mov     rdx, rbx
0x18003e00b  mov     rcx, rsi
0x18003e00e  call    __std_search_2
0x18003e013  cmp     rax, rbx
0x18003e016  jz      loc_18003E15A
0x18003e01c  sub     rax, rsi
0x18003e01f  sar     rax, 1
0x18003e022  mov     rcx, cs:qword_18011BAE0
0x18003e029  jmp     short loc_18003E02E
0x18003e02b  mov     rax, rdi
0x18003e02e  cmp     rax, rdi
0x18003e031  jz      loc_18003E15A
0x18003e037  lea     rsi, [rax+rcx]
0x18003e03b  mov     rax, qword ptr [rbp+57h+var_D0]
0x18003e03f  xorps   xmm0, xmm0
0x18003e042  movups  [rbp+57h+var_80], xmm0
0x18003e046  mov     [rbp+57h+var_70], r13
0x18003e04a  mov     [rbp+57h+var_68], r13
0x18003e04e  cmp     rax, rsi
0x18003e051  jb      loc_18003E1C8
0x18003e057  mov     r8, rax
0x18003e05a  sub     r8, rsi
0x18003e05d  cmp     r8, rax
0x18003e060  cmovnb  r8, rax
0x18003e064  lea     rax, [rsp+110h+pszPath]
0x18003e069  cmp     qword ptr [rbp+57h+var_D0+8], 7
0x18003e06e  cmova   rax, [rsp+110h+pszPath]
0x18003e074  lea     rdx, [rax+rsi*2]
0x18003e078  lea     rcx, [rbp+57h+var_80]
0x18003e07c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003e081  nop
0x18003e082  xorps   xmm0, xmm0
0x18003e085  movups  [rbp+57h+var_A0], xmm0
0x18003e089  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18003e091  movdqu  [rbp+57h+var_90], xmm1
0x18003e096  mov     word ptr [rbp+57h+var_A0], r13w
0x18003e09b  mov     rax, [rbp+57h+var_70]
0x18003e09f  lea     r15, [rbp+57h+var_80]
0x18003e0a3  cmp     [rbp+57h+var_68], 7
0x18003e0a8  cmova   r15, qword ptr [rbp+57h+var_80]
0x18003e0ad  test    rax, rax
0x18003e0b0  jz      short loc_18003E0D5
0x18003e0b2  lea     rbx, [r15+rax*2]
0x18003e0b6  mov     r8d, 5Ch ; '\'
0x18003e0bc  mov     rdx, rbx
0x18003e0bf  mov     rcx, r15
0x18003e0c2  call    __std_find_trivial_2
0x18003e0c7  cmp     rax, rbx
0x18003e0ca  jz      short loc_18003E0D5
0x18003e0cc  mov     rdi, rax
0x18003e0cf  sub     rdi, r15
0x18003e0d2  sar     rdi, 1
0x18003e0d5  xorps   xmm0, xmm0
0x18003e0d8  movups  [rbp+57h+var_60], xmm0
0x18003e0dc  xorps   xmm1, xmm1
0x18003e0df  movdqu  [rbp+57h+var_50], xmm1
0x18003e0e4  mov     r8, qword ptr [rbp+57h+var_D0]
0x18003e0e8  cmp     r8, rsi
0x18003e0eb  jb      loc_18003E1BC
0x18003e0f1  sub     r8, rsi
0x18003e0f4  cmp     r8, rdi
0x18003e0f7  cmovnb  r8, rdi
0x18003e0fb  lea     rax, [rsp+110h+pszPath]
0x18003e100  cmp     qword ptr [rbp+57h+var_D0+8], 7
0x18003e105  cmova   rax, [rsp+110h+pszPath]
0x18003e10b  lea     rdx, [rax+rsi*2]
0x18003e10f  lea     rcx, [rbp+57h+var_60]
0x18003e113  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003e118  lea     rdx, [rbp+57h+var_60]
0x18003e11c  lea     rcx, [rbp+57h+var_A0]
0x18003e120  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003e125  lea     rcx, [rbp+57h+var_60]
0x18003e129  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003e12e  lea     r9, aXxxx; "xxxx"
0x18003e135  mov     r8, qword ptr [rbp+57h+var_90]
0x18003e139  mov     rdx, rsi
0x18003e13c  lea     rcx, [rsp+110h+pszPath]; Src
0x18003e141  call    ?replace@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0QEBG@Z; std::wstring::replace(unsigned __int64,unsigned __int64,ushort const * const)
0x18003e146  nop
0x18003e147  lea     rcx, [rbp+57h+var_A0]
0x18003e14b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003e150  nop
0x18003e151  lea     rcx, [rbp+57h+var_80]
0x18003e155  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003e15a  movups  xmm0, xmmword ptr [rsp+110h+pszPath]
0x18003e15f  movups  xmmword ptr [r14], xmm0
0x18003e163  movups  xmm1, [rbp+57h+var_D0]
0x18003e167  movups  xmmword ptr [r14+10h], xmm1
0x18003e16c  mov     qword ptr [rbp+57h+var_D0], r13
0x18003e170  mov     qword ptr [rbp+57h+var_D0+8], 7
0x18003e178  mov     word ptr [rsp+110h+pszPath], r13w
0x18003e17e  lea     rcx, [rsp+110h+pszPath]
0x18003e183  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003e188  nop
0x18003e189  lea     rcx, [rbp+57h+pszBuf]
0x18003e18d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003e192  mov     rax, r14
0x18003e195  mov     rcx, [rbp+57h+var_40]
0x18003e199  xor     rcx, rsp; StackCookie
0x18003e19c  call    __security_check_cookie
0x18003e1a1  mov     rbx, [rsp+110h+arg_10]
0x18003e1a9  add     rsp, 0E0h
0x18003e1b0  pop     r15
0x18003e1b2  pop     r14
0x18003e1b4  pop     r13
0x18003e1b6  pop     r12
0x18003e1b8  pop     rdi
0x18003e1b9  pop     rsi
0x18003e1ba  pop     rbp
0x18003e1bb  retn
0x18003e1bc  call    ?_Xran@?$_String_val@U?$_Simple_types@G@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<ushort>>::_Xran(void)
0x18003e1c2  call    ?_Xran@?$_String_val@U?$_Simple_types@G@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<ushort>>::_Xran(void)
0x18003e1c8  call    ?_Xran@?$_String_val@U?$_Simple_types@G@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<ushort>>::_Xran(void)
```
