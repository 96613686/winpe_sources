# IsRedistributable(VSDependenciesHelper &,HKEY__ * const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x180027b94`
- end: `0x180028326`
- name: `?IsRedistributable@@YAHAEAVVSDependenciesHelper@@QEAUHKEY__@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@2@Z`
- size: `1938`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180028330`

## callees

- `0x180001cf0`
- `0x18000b5fc`
- `0x18000b720`
- `0x18000e0e4`
- `0x180010718`
- `0x180010730`
- `0x1800180dc`
- `0x18002515c`
- `0x18002589c`
- `0x180026290`
- `0x18002649c`
- `0x180026530`
- `0x180026e50`
- `0x180026ee0`
- `0x1800271f4`
- `0x180027624`
- `0x180027b94`
- `0x18002f08c`
- `0x180046b68`
- `0x180047d00`
- `0x180063c30`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180027c4c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180027c4c`

## string_xrefs

- `0x180027c88`: `UninstallString`
- `0x180027cc3`: `-m ([\w:\\]+\\Autodesk\\ODIS\\metadata\\\{[0-9A-F\-]+\}\\bundleManifest.xml)`
- `0x180028014`: `InstallSource`
- `0x180028177`: `InstallSource`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
__int64 __fastcall IsRedistributable(__int64 a1, wchar_t *a2, void *a3, _QWORD *a4)
{
  wchar_t *v6; // rsi
  __int64 v7; // rdi
  __int128 *v8; // rdx
  _QWORD *v9; // rcx
  int v10; // ebx
  __int128 *v11; // rcx
  __int128 *v12; // rdx
  unsigned int v13; // ebx
  _QWORD *v14; // rax
  __int64 v15; // r14
  __int128 *v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // rdi
  __int64 v19; // rax
  __int64 v20; // rcx
  unsigned __int64 v21; // rax
  unsigned __int64 v22; // r8
  __int128 *v23; // rax
  const wchar_t *v24; // rcx
  __int128 *v25; // rcx
  __int128 *v26; // rcx
  _QWORD *v27; // rdi
  _QWORD *i; // rbx
  unsigned __int64 v29; // r9
  _QWORD *v30; // r8
  _QWORD *v31; // r15
  char *v32; // rsi
  __int64 seq_traits_avx_2_void_unsigned_short; // rax
  __int64 v35; // [rsp+30h] [rbp-D0h] BYREF
  bool v36; // [rsp+38h] [rbp-C8h]
  char v37; // [rsp+39h] [rbp-C7h]
  int v38; // [rsp+3Ah] [rbp-C6h]
  __int16 v39; // [rsp+3Eh] [rbp-C2h]
  char v40[16]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v41; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v42; // [rsp+60h] [rbp-A0h]
  int v43; // [rsp+68h] [rbp-98h]
  __int64 v44; // [rsp+70h] [rbp-90h]
  char v45; // [rsp+78h] [rbp-88h]
  _OWORD v46[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v47; // [rsp+A0h] [rbp-60h]
  char v48; // [rsp+A8h] [rbp-58h]
  __int128 v49; // [rsp+B0h] [rbp-50h]
  char v50; // [rsp+C0h] [rbp-40h]
  __int64 v51; // [rsp+C8h] [rbp-38h]
  __int64 v52; // [rsp+D0h] [rbp-30h]
  char v53; // [rsp+D8h] [rbp-28h]
  __int64 v54; // [rsp+E0h] [rbp-20h]
  _BYTE v55[40]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v56[32]; // [rsp+110h] [rbp+10h] BYREF
  char v57[16]; // [rsp+130h] [rbp+30h] BYREF
  _QWORD v58[12]; // [rsp+140h] [rbp+40h] BYREF
  _QWORD v59[22]; // [rsp+1A0h] [rbp+A0h] BYREF
  _QWORD v60[12]; // [rsp+250h] [rbp+150h] BYREF
  _QWORD *v61; // [rsp+2B0h] [rbp+1B0h] BYREF
  int v62; // [rsp+2BAh] [rbp+1BAh]
  __int16 v63; // [rsp+2BEh] [rbp+1BEh]
  void *v64; // [rsp+2C0h] [rbp+1C0h]
  __int128 v65; // [rsp+2C8h] [rbp+1C8h] BYREF
  __int128 v66; // [rsp+2D8h] [rbp+1D8h]
  __int128 v67; // [rsp+2E8h] [rbp+1E8h] BYREF
  __int128 v68; // [rsp+2F8h] [rbp+1F8h]
  __int128 v69; // [rsp+310h] [rbp+210h] BYREF
  __m128i si128; // [rsp+320h] [rbp+220h]
  wchar_t *S1[2]; // [rsp+330h] [rbp+230h] BYREF
  __int64 v72; // [rsp+340h] [rbp+240h]
  unsigned __int64 v73; // [rsp+348h] [rbp+248h]
  _QWORD v74[2]; // [rsp+360h] [rbp+260h] BYREF
  unsigned __int64 v75; // [rsp+370h] [rbp+270h]
  unsigned __int64 v76; // [rsp+378h] [rbp+278h]

  v54 = -2;
  v6 = a2;
  S1[0] = a2;
  v7 = a1;
  v35 = a1;
  v64 = a3;
  v61 = a4;
  v65 = 0;
  v66 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v65, L"Autodesk", 8);
  v8 = &v65;
  if ( *((_QWORD *)&v66 + 1) > 7u )
    v8 = (__int128 *)v65;
  if ( a4[3] <= 7u )
    v9 = a4;
  else
    v9 = (_QWORD *)*a4;
  v10 = _o__wcsnicmp(v9, v8);
  std::wstring::~wstring(&v65);
  v67 = 0;
  v68 = 0;
  if ( v10 )
  {
    std::wstring::_Construct<1,unsigned short const *>(&v67, L"DisplayName", 11);
    AppCompatUtility::RegOperations::GetStringOrDefault(&v69, v6, a3, &v67);
    std::wstring::~wstring(&v67);
    if ( *(_QWORD *)std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::find(
                      v7 + 16,
                      v40,
                      &v69) == *(_QWORD *)(v7 + 24) )
    {
      v65 = 0;
      v66 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v65, L"InstallSource", 13);
      AppCompatUtility::RegOperations::GetStringOrDefault(v74, v6, a3, &v65);
      std::wstring::~wstring(&v65);
      v27 = *(_QWORD **)v7;
      for ( i = (_QWORD *)*v27; i != v27; i = (_QWORD *)*i )
      {
        v29 = i[4];
        v30 = i + 2;
        if ( i[5] > 7u )
          v30 = (_QWORD *)*v30;
        v31 = v74;
        if ( v76 > 7 )
          v31 = (_QWORD *)v74[0];
        if ( v29 <= v75 )
        {
          if ( !v29
            || (v32 = (char *)v31 + 2 * v75,
                seq_traits_avx_2_void_unsigned_short = anonymous_namespace_::_Find_seq::_Search_impl__anonymous_namespace_::_Finding::_Find_traits_2_A0x8fcf2c39::_Find_seq::_Find_seq_traits_avx_2_void_unsigned_short_(
                                                         v31,
                                                         v32,
                                                         v30),
                (char *)seq_traits_avx_2_void_unsigned_short != v32)
            && (seq_traits_avx_2_void_unsigned_short - (__int64)v31) >> 1 != -1 )
          {
            v13 = 1;
            goto LABEL_49;
          }
        }
      }
      v13 = 0;
LABEL_49:
      std::wstring::~wstring(v74);
      v7 = v35;
      v6 = S1[0];
    }
    else
    {
      v13 = 1;
    }
    if ( !v13 )
    {
      v65 = 0;
      v66 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v65, L"BundleProviderKey", 17);
      AppCompatUtility::RegOperations::GetStringOrDefault(&v67, v6, a3, &v65);
      std::wstring::~wstring(&v65);
      v13 = *(_QWORD *)std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::find(
                         v7 + 80,
                         &v61,
                         &v67) != *(_QWORD *)(v7 + 88);
      std::wstring::~wstring(&v67);
    }
    v26 = &v69;
  }
  else
  {
    std::wstring::_Construct<1,unsigned short const *>(&v67, L"UninstallString", 15);
    AppCompatUtility::RegOperations::GetStringOrDefault(&v65, v6, a3, &v67);
    std::wstring::~wstring(&v67);
    std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::basic_regex<unsigned short,std::regex_traits<unsigned short>>(
      v55,
      L"-m ([\\w:\\\\]+\\\\Autodesk\\\\ODIS\\\\metadata\\\\\\{[0-9A-F\\-]+\\}\\\\bundleManifest.xml)",
      256);
    v11 = &v65;
    if ( *((_QWORD *)&v66 + 1) > 7u )
      v11 = (__int128 *)v65;
    v12 = &v65;
    if ( *((_QWORD *)&v66 + 1) > 7u )
      v12 = (__int128 *)v65;
    std::regex_iterator<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short,std::regex_traits<unsigned short>>::regex_iterator<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short,std::regex_traits<unsigned short>>(
      v56,
      v12,
      (char *)v11 + 2 * v66,
      v55);
    v41 = 0u;
    v42 = 0;
    v43 = 0;
    v44 = 0;
    v45 = 0;
    memset(v46, 0, sizeof(v46));
    v47 = 0;
    v48 = 0;
    v49 = 0u;
    v50 = 0;
    v51 = 0;
    v52 = 0;
    v53 = 0;
    if ( (unsigned __int8)std::regex_iterator<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short,std::regex_traits<unsigned short>>::operator!=(
                            v56,
                            &v41)
      && v58[1] - v58[0] == 48 )
    {
      v13 = 1;
      v14 = (_QWORD *)std::match_results<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::str(
                        v57,
                        S1,
                        1);
      if ( v14[3] > 7u )
        v14 = (_QWORD *)*v14;
      v67 = 0;
      v68 = 0;
      v15 = -1;
      do
        ++v15;
      while ( *((_WORD *)v14 + v15) );
      std::wstring::_Construct<1,unsigned short const *>(&v67, v14, v15);
      std::wstring::~wstring(S1);
      v16 = &v67;
      if ( *((_QWORD *)&v68 + 1) > 7u )
        v16 = (__int128 *)v67;
      std::ifstream::ifstream(v59, v16);
      *(_QWORD *)((char *)v59 + *(int *)(v59[0] + 4LL)) = &std::ifstream::`vftable';
      *(_DWORD *)((char *)&v58[11] + *(int *)(v59[0] + 4LL) + 4) = *(_DWORD *)(v59[0] + 4LL) - 176;
      v69 = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v69) = 0;
      v17 = *(_QWORD *)((char *)&v59[9] + *(int *)(v59[0] + 4LL));
      S1[0] = 0;
      LOWORD(S1[1]) = 1;
      *(_DWORD *)((char *)&S1[1] + 2) = v62;
      HIWORD(S1[1]) = v63;
      v35 = v17;
      v36 = v17 == 0;
      v37 = 0;
      v38 = v62;
      v39 = v63;
      std::wstring::assign<std::istreambuf_iterator<char>,0>(&v69, &v35, S1);
      v18 = std::wstring::find(&v69, L"<Type>");
      v19 = std::wstring::find(&v69, L"</Type>");
      v20 = v18 + 6;
      *(_OWORD *)S1 = 0;
      v72 = 0;
      v73 = 0;
      if ( si128.m128i_i64[0] < (unsigned __int64)(v18 + 6) )
        std::_String_val<std::_Simple_types<unsigned short>>::_Xran();
      v21 = v19 - v18 - 6;
      v22 = si128.m128i_i64[0] - v20;
      if ( si128.m128i_i64[0] - v20 >= v21 )
        v22 = v21;
      v23 = &v69;
      if ( si128.m128i_i64[1] > 7uLL )
        v23 = (__int128 *)v69;
      std::wstring::_Construct<1,unsigned short const *>(S1, (char *)v23 + 2 * v20, v22);
      v24 = (const wchar_t *)S1;
      if ( v73 > 7 )
        v24 = S1[0];
      if ( v72 == 3 && !wmemcmp(v24, L"PRD", 3u) )
        v13 = 0;
      std::wstring::~wstring(S1);
      std::wstring::~wstring(&v69);
      std::ifstream::~ifstream<char,std::char_traits<char>>(v60);
      v60[0] = &std::ios::`vftable';
      std::ios_base::~ios_base((std::ios_base *)v60);
      v25 = &v67;
    }
    else
    {
      v67 = 0;
      v68 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v67, L"InstallSource", 13);
      AppCompatUtility::RegOperations::GetStringOrDefault(&v69, v6, a3, &v67);
      std::wstring::~wstring(&v67);
      std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::basic_regex<unsigned short,std::regex_traits<unsigned short>>(
        S1,
        L"[\\w:\\\\]+\\\\Autodesk\\\\\\{[0-9A-F\\-]+\\}\\\\image\\\\",
        256);
      if ( (unsigned __int8)std::regex_search<std::char_traits<unsigned short>,std::allocator<unsigned short>,unsigned short,std::regex_traits<unsigned short>>(
                              &v69,
                              S1) )
      {
        v13 = 1;
      }
      else
      {
        std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::basic_regex<unsigned short,std::regex_traits<unsigned short>>(
          &v67,
          L"[\\w:\\\\]+\\\\Autodesk\\\\ODIS\\\\extract\\\\\\{[0-9A-F\\-]+\\}",
          256);
        v13 = (unsigned __int8)std::regex_search<std::char_traits<unsigned short>,std::allocator<unsigned short>,unsigned short,std::regex_traits<unsigned short>>(
                                 &v69,
                                 &v67);
        std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::regex_traits<unsigned short>>(&v67);
      }
      std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::regex_traits<unsigned short>>(S1);
      v25 = &v69;
    }
    std::wstring::~wstring(v25);
    std::vector<std::sub_match<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>::~vector<std::sub_match<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>(v46);
    std::vector<std::sub_match<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>::~vector<std::sub_match<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>(v58);
    std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::regex_traits<unsigned short>>(v55);
    v26 = &v65;
  }
  std::wstring::~wstring(v26);
  std::wstring::~wstring(a3);
  std::wstring::~wstring(a4);
  return v13;
}

```

## disassembly

```asm
0x180027b94  push    rbp
0x180027b96  push    rbx
0x180027b97  push    rsi
0x180027b98  push    rdi
0x180027b99  push    r12
0x180027b9b  push    r13
0x180027b9d  push    r14
0x180027b9f  push    r15
0x180027ba1  lea     rbp, [rsp-298h]
0x180027ba9  sub     rsp, 398h
0x180027bb0  mov     [rbp+2D0h+var_2F0], 0FFFFFFFFFFFFFFFEh
0x180027bb8  mov     rax, cs:__security_cookie
0x180027bbf  xor     rax, rsp
0x180027bc2  mov     [rbp+2D0h+var_50], rax
0x180027bc9  mov     r13, r9
0x180027bcc  mov     r12, r8
0x180027bcf  mov     rsi, rdx
0x180027bd2  mov     [rbp+2D0h+S1], rdx
0x180027bd9  mov     rdi, rcx
0x180027bdc  mov     [rsp+3D0h+var_3A0], rcx
0x180027be1  mov     [rbp+2D0h+var_110], r8
0x180027be8  mov     [rbp+2D0h+var_120], r9
0x180027bef  xor     r15d, r15d
0x180027bf2  xorps   xmm0, xmm0
0x180027bf5  movups  [rbp+2D0h+var_108], xmm0
0x180027bfc  xorps   xmm1, xmm1
0x180027bff  movdqu  [rbp+2D0h+var_F8], xmm1
0x180027c07  lea     r8d, [r15+8]
0x180027c0b  lea     rdx, aAutodesk; "Autodesk"
0x180027c12  lea     rcx, [rbp+2D0h+var_108]
0x180027c19  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180027c1e  lea     rdx, [rbp+2D0h+var_108]
0x180027c25  cmp     qword ptr [rbp+2D0h+var_F8+8], 7
0x180027c2d  cmova   rdx, qword ptr [rbp+2D0h+var_108]
0x180027c35  cmp     qword ptr [r13+18h], 7
0x180027c3a  jbe     short loc_180027C42
0x180027c3c  mov     rcx, [r13+0]
0x180027c40  jmp     short loc_180027C45
0x180027c42  mov     rcx, r13
0x180027c45  mov     r8, qword ptr [rbp+2D0h+var_F8]
0x180027c4c  call    cs:__imp__o__wcsnicmp
0x180027c52  mov     ebx, eax
0x180027c54  lea     rcx, [rbp+2D0h+var_108]; void *
0x180027c5b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180027c60  xorps   xmm0, xmm0
0x180027c63  xorps   xmm1, xmm1
0x180027c66  lea     rcx, [rbp+2D0h+var_E8]
0x180027c6d  movups  [rbp+2D0h+var_E8], xmm0
0x180027c74  movdqu  [rbp+2D0h+var_D8], xmm1
0x180027c7c  test    ebx, ebx
0x180027c7e  jnz     loc_180028101
0x180027c84  lea     r8d, [rbx+0Fh]
0x180027c88  lea     rdx, aUninstallstrin; "UninstallString"
0x180027c8f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180027c94  nop
0x180027c95  lea     r9, [rbp+2D0h+var_E8]
0x180027c9c  mov     r8, r12
0x180027c9f  mov     rdx, rsi
0x180027ca2  lea     rcx, [rbp+2D0h+var_108]
0x180027ca9  call    ?GetStringOrDefault@RegOperations@AppCompatUtility@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@AEBV34@1@Z; AppCompatUtility::RegOperations::GetStringOrDefault(HKEY__ *,std::wstring const &,std::wstring const &)
0x180027cae  nop
0x180027caf  lea     rcx, [rbp+2D0h+var_E8]; void *
0x180027cb6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180027cbb  mov     ebx, 100h
0x180027cc0  mov     r8d, ebx
0x180027cc3  lea     rdx, aMWAutodeskOdis; "-m ([\\w:\\\\]+\\\\Autodesk\\\\ODIS\\\\"...
0x180027cca  lea     rcx, [rbp+2D0h+var_2E8]
0x180027cce  call    ??0?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@PEBGW4syntax_option_type@regex_constants@1@@Z; std::basic_regex<ushort,std::regex_traits<ushort>>::basic_regex<ushort,std::regex_traits<ushort>>(ushort const *,std::regex_constants::syntax_option_type)
0x180027cd3  nop
0x180027cd4  lea     rcx, [rbp+2D0h+var_108]
0x180027cdb  cmp     qword ptr [rbp+2D0h+var_F8+8], 7
0x180027ce3  cmova   rcx, qword ptr [rbp+2D0h+var_108]
0x180027ceb  mov     rax, qword ptr [rbp+2D0h+var_F8]
0x180027cf2  lea     r8, [rcx+rax*2]
0x180027cf6  lea     rdx, [rbp+2D0h+var_108]
0x180027cfd  cmova   rdx, qword ptr [rbp+2D0h+var_108]
0x180027d05  lea     r9, [rbp+2D0h+var_2E8]
0x180027d09  lea     rcx, [rbp+2D0h+var_2C0]
0x180027d0d  call    ??0?$regex_iterator@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@GV?$regex_traits@G@2@@std@@QEAA@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@1@0AEBV?$basic_regex@GV?$regex_traits@G@std@@@1@W4match_flag_type@regex_constants@1@@Z; std::regex_iterator<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort,std::regex_traits<ushort>>::regex_iterator<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort,std::regex_traits<ushort>>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::basic_regex<ushort,std::regex_traits<ushort>> const &,std::regex_constants::match_flag_type)
0x180027d12  nop
0x180027d13  xorps   xmm0, xmm0
0x180027d16  movdqa  [rsp+3D0h+var_380], xmm0
0x180027d1c  mov     qword ptr [rsp+3D0h+var_380+8], r15
0x180027d21  mov     [rsp+3D0h+var_370], r15
0x180027d26  mov     [rsp+3D0h+var_368], r15d
0x180027d2b  mov     [rsp+3D0h+var_360], r15
0x180027d30  mov     [rsp+3D0h+var_358], r15b
0x180027d35  movdqa  [rbp+2D0h+var_350], xmm0
0x180027d3a  xorps   xmm1, xmm1
0x180027d3d  movdqa  [rbp+2D0h+var_340], xmm1
0x180027d42  mov     qword ptr [rbp+2D0h+var_340+8], r15
0x180027d46  mov     [rbp+2D0h+var_330], r15
0x180027d4a  mov     [rbp+2D0h+var_328], r15b
0x180027d4e  movdqa  [rbp+2D0h+var_320], xmm0
0x180027d53  mov     qword ptr [rbp+2D0h+var_320+8], r15
0x180027d57  mov     [rbp+2D0h+var_310], r15b
0x180027d5b  mov     [rbp+2D0h+var_308], r15
0x180027d5f  mov     [rbp+2D0h+var_300], r15
0x180027d63  mov     [rbp+2D0h+var_2F8], r15b
0x180027d67  lea     rdx, [rsp+3D0h+var_380]
0x180027d6c  lea     rcx, [rbp+2D0h+var_2C0]
0x180027d70  call    ??9?$regex_iterator@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@GV?$regex_traits@G@2@@std@@QEBA_NAEBV01@@Z; std::regex_iterator<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort,std::regex_traits<ushort>>::operator!=(std::regex_iterator<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort,std::regex_traits<ushort>> const &)
0x180027d75  test    al, al
0x180027d77  jz      loc_180027FF9
0x180027d7d  mov     rax, [rbp+2D0h+var_288]
0x180027d81  sub     rax, [rbp+2D0h+var_290]
0x180027d85  cmp     rax, 30h ; '0'
0x180027d89  jnz     loc_180027FF9
0x180027d8f  lea     ebx, [rax-2Fh]
0x180027d92  mov     r8d, ebx
0x180027d95  lea     rdx, [rbp+2D0h+S1]
0x180027d9c  lea     rcx, [rbp+2D0h+var_2A0]
0x180027da0  call    ?str@?$match_results@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$allocator@V?$sub_match@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_K@Z; std::match_results<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>>::str(unsigned __int64)
0x180027da5  nop
0x180027da6  cmp     qword ptr [rax+18h], 7
0x180027dab  jbe     short loc_180027DB0
0x180027dad  mov     rax, [rax]
0x180027db0  xorps   xmm0, xmm0
0x180027db3  movups  [rbp+2D0h+var_E8], xmm0
0x180027dba  xorps   xmm1, xmm1
0x180027dbd  movdqu  [rbp+2D0h+var_D8], xmm1
0x180027dc5  or      r14, 0FFFFFFFFFFFFFFFFh
0x180027dc9  inc     r14
0x180027dcc  cmp     [rax+r14*2], r15w
0x180027dd1  jnz     short loc_180027DC9
0x180027dd3  mov     r8, r14
0x180027dd6  mov     rdx, rax
0x180027dd9  lea     rcx, [rbp+2D0h+var_E8]
0x180027de0  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180027de5  nop
0x180027de6  lea     rcx, [rbp+2D0h+S1]; void *
0x180027ded  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180027df2  lea     rdx, [rbp+2D0h+var_E8]
0x180027df9  cmp     qword ptr [rbp+2D0h+var_D8+8], 7
0x180027e01  cmova   rdx, qword ptr [rbp+2D0h+var_E8]
0x180027e09  lea     rcx, [rbp+2D0h+var_230]
0x180027e10  call    ??0?$basic_ifstream@DU?$char_traits@D@std@@@std@@QEAA@PEBGHH@Z; std::ifstream::ifstream(ushort const *,int,int)
0x180027e15  mov     rax, [rbp+2D0h+var_230]
0x180027e1c  movsxd  rcx, dword ptr [rax+4]
0x180027e20  lea     rax, ??_7?$basic_ifstream@DU?$char_traits@D@std@@@std@@6B@; const std::ifstream::`vftable'
0x180027e27  mov     [rbp+rcx+2D0h+var_230], rax
0x180027e2f  mov     rax, [rbp+2D0h+var_230]
0x180027e36  movsxd  rcx, dword ptr [rax+4]
0x180027e3a  lea     edx, [rcx-0B0h]
0x180027e40  mov     [rbp+rcx+2D0h+var_234], edx
0x180027e47  xorps   xmm0, xmm0
0x180027e4a  movups  [rbp+2D0h+var_C0], xmm0
0x180027e51  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180027e59  movdqu  [rbp+2D0h+var_B0], xmm1
0x180027e61  mov     word ptr [rbp+2D0h+var_C0], r15w
0x180027e69  mov     rax, [rbp+2D0h+var_230]
0x180027e70  movsxd  rcx, dword ptr [rax+4]
0x180027e74  mov     rdx, [rbp+rcx+2D0h+var_1E8]
0x180027e7c  mov     [rbp+2D0h+S1], r15
0x180027e83  mov     word ptr [rbp+2D0h+S1+8], 1
0x180027e8c  mov     eax, [rbp+2D0h+var_116]
0x180027e92  mov     dword ptr [rbp+2D0h+S1+0Ah], eax
0x180027e98  movzx   eax, [rbp+2D0h+var_112]
0x180027e9f  mov     word ptr [rbp+2D0h+S1+0Eh], ax
0x180027ea6  mov     [rsp+3D0h+var_3A0], rdx
0x180027eab  test    rdx, rdx
0x180027eae  setz    [rsp+3D0h+var_398]
0x180027eb3  mov     [rsp+3D0h+var_397], r15b
0x180027eb8  mov     eax, [rbp+2D0h+var_116]
0x180027ebe  mov     [rsp+3D0h+var_396], eax
0x180027ec2  movzx   eax, [rbp+2D0h+var_112]
0x180027ec9  mov     [rsp+3D0h+var_392], ax
0x180027ece  lea     r8, [rbp+2D0h+S1]
0x180027ed5  lea     rdx, [rsp+3D0h+var_3A0]
0x180027eda  lea     rcx, [rbp+2D0h+var_C0]
0x180027ee1  call    ??$assign@V?$istreambuf_iterator@DU?$char_traits@D@std@@@std@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@V?$istreambuf_iterator@DU?$char_traits@D@std@@@1@0@Z; std::wstring::assign<std::istreambuf_iterator<char>,0>(std::istreambuf_iterator<char>,std::istreambuf_iterator<char>)
0x180027ee6  lea     rdx, aType_0; "<Type>"
0x180027eed  lea     rcx, [rbp+2D0h+var_C0]
0x180027ef4  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x180027ef9  mov     rdi, rax
0x180027efc  lea     rdx, aType; "</Type>"
0x180027f03  lea     rcx, [rbp+2D0h+var_C0]
0x180027f0a  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x180027f0f  lea     rcx, [rdi+6]
0x180027f13  xorps   xmm0, xmm0
0x180027f16  movups  xmmword ptr [rbp+2D0h+S1], xmm0
0x180027f1d  mov     [rbp+2D0h+var_90], r15
0x180027f24  mov     [rbp+2D0h+var_88], r15
0x180027f2b  mov     r8, qword ptr [rbp+2D0h+var_B0]
0x180027f32  cmp     r8, rcx
0x180027f35  jb      loc_180028320
0x180027f3b  sub     rax, rdi
0x180027f3e  add     rax, 0FFFFFFFFFFFFFFFAh
0x180027f42  sub     r8, rcx
0x180027f45  cmp     r8, rax
0x180027f48  cmovnb  r8, rax
0x180027f4c  lea     rax, [rbp+2D0h+var_C0]
0x180027f53  cmp     qword ptr [rbp+2D0h+var_B0+8], 7
0x180027f5b  cmova   rax, qword ptr [rbp+2D0h+var_C0]
0x180027f63  lea     rdx, [rax+rcx*2]
0x180027f67  lea     rcx, [rbp+2D0h+S1]
0x180027f6e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180027f73  lea     rcx, [rbp+2D0h+S1]
0x180027f7a  cmp     [rbp+2D0h+var_88], 7
0x180027f82  cmova   rcx, [rbp+2D0h+S1]; S1
0x180027f8a  mov     r8d, 3; N
0x180027f90  cmp     [rbp+2D0h+var_90], r8
0x180027f97  jnz     short loc_180027FAC
0x180027f99  lea     rdx, aPrd; "PRD"
0x180027fa0  call    wmemcmp
0x180027fa5  test    eax, eax
0x180027fa7  jnz     short loc_180027FAC
0x180027fa9  mov     ebx, r15d
0x180027fac  lea     rcx, [rbp+2D0h+S1]; void *
0x180027fb3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180027fb8  nop
0x180027fb9  lea     rcx, [rbp+2D0h+var_C0]; void *
0x180027fc0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180027fc5  nop
0x180027fc6  lea     rcx, [rbp+2D0h+var_180]
0x180027fcd  call    ??1?$basic_ifstream@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::ifstream::~ifstream<char,std::char_traits<char>>(void)
0x180027fd2  lea     rax, ??_7?$basic_ios@DU?$char_traits@D@std@@@std@@6B@; const std::ios::`vftable'
0x180027fd9  mov     [rbp+2D0h+var_180], rax
0x180027fe0  lea     rcx, [rbp+2D0h+var_180]; this
0x180027fe7  call    ??1ios_base@std@@UEAA@XZ; std::ios_base::~ios_base(void)
0x180027fec  nop
0x180027fed  lea     rcx, [rbp+2D0h+var_E8]
0x180027ff4  jmp     loc_1800280D1
0x180027ff9  xorps   xmm0, xmm0
0x180027ffc  movups  [rbp+2D0h+var_E8], xmm0
0x180028003  xorps   xmm1, xmm1
0x180028006  movdqu  [rbp+2D0h+var_D8], xmm1
0x18002800e  mov     r8d, 0Dh
0x180028014  lea     rdx, aInstallsource; "InstallSource"
0x18002801b  lea     rcx, [rbp+2D0h+var_E8]
0x180028022  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180028027  nop
0x180028028  lea     r9, [rbp+2D0h+var_E8]
0x18002802f  mov     r8, r12
0x180028032  mov     rdx, rsi
0x180028035  lea     rcx, [rbp+2D0h+var_C0]
0x18002803c  call    ?GetStringOrDefault@RegOperations@AppCompatUtility@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@AEBV34@1@Z; AppCompatUtility::RegOperations::GetStringOrDefault(HKEY__ *,std::wstring const &,std::wstring const &)
0x180028041  nop
0x180028042  lea     rcx, [rbp+2D0h+var_E8]; void *
0x180028049  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002804e  mov     r8d, ebx
0x180028051  lea     rdx, aWAutodesk09aFI; "[\\w:\\\\]+\\\\Autodesk\\\\\\{[0-9A-F\\"...
0x180028058  lea     rcx, [rbp+2D0h+S1]
0x18002805f  call    ??0?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@PEBGW4syntax_option_type@regex_constants@1@@Z; std::basic_regex<ushort,std::regex_traits<ushort>>::basic_regex<ushort,std::regex_traits<ushort>>(ushort const *,std::regex_constants::syntax_option_type)
0x180028064  nop
0x180028065  lea     rdx, [rbp+2D0h+S1]
0x18002806c  lea     rcx, [rbp+2D0h+var_C0]
0x180028073  call    ??$regex_search@U?$char_traits@G@std@@V?$allocator@G@2@GV?$regex_traits@G@2@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV?$basic_regex@GV?$regex_traits@G@std@@@0@W4match_flag_type@regex_constants@0@@Z; std::regex_search<std::char_traits<ushort>,std::allocator<ushort>,ushort,std::regex_traits<ushort>>(std::wstring const &,std::basic_regex<ushort,std::regex_traits<ushort>> const &,std::regex_constants::match_flag_type)
0x180028078  test    al, al
0x18002807a  jz      short loc_180028083
0x18002807c  mov     ebx, 1
0x180028081  jmp     short loc_1800280BD
0x180028083  mov     r8d, ebx
0x180028086  lea     rdx, aWAutodeskOdisE; "[\\w:\\\\]+\\\\Autodesk\\\\ODIS\\\\extr"...
0x18002808d  lea     rcx, [rbp+2D0h+var_E8]
0x180028094  call    ??0?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@PEBGW4syntax_option_type@regex_constants@1@@Z; std::basic_regex<ushort,std::regex_traits<ushort>>::basic_regex<ushort,std::regex_traits<ushort>>(ushort const *,std::regex_constants::syntax_option_type)
0x180028099  nop
0x18002809a  lea     rdx, [rbp+2D0h+var_E8]
0x1800280a1  lea     rcx, [rbp+2D0h+var_C0]
0x1800280a8  call    ??$regex_search@U?$char_traits@G@std@@V?$allocator@G@2@GV?$regex_traits@G@2@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV?$basic_regex@GV?$regex_traits@G@std@@@0@W4match_flag_type@regex_constants@0@@Z; std::regex_search<std::char_traits<ushort>,std::allocator<ushort>,ushort,std::regex_traits<ushort>>(std::wstring const &,std::basic_regex<ushort,std::regex_traits<ushort>> const &,std::regex_constants::match_flag_type)
0x1800280ad  movzx   ebx, al
0x1800280b0  lea     rcx, [rbp+2D0h+var_E8]; void *
0x1800280b7  call    ??1?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@XZ; std::basic_regex<ushort,std::regex_traits<ushort>>::~basic_regex<ushort,std::regex_traits<ushort>>(void)
0x1800280bc  nop
0x1800280bd  lea     rcx, [rbp+2D0h+S1]; void *
0x1800280c4  call    ??1?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@XZ; std::basic_regex<ushort,std::regex_traits<ushort>>::~basic_regex<ushort,std::regex_traits<ushort>>(void)
0x1800280c9  nop
0x1800280ca  lea     rcx, [rbp+2D0h+var_C0]; void *
0x1800280d1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800280d6  nop
0x1800280d7  lea     rcx, [rbp+2D0h+var_350]
0x1800280db  call    ??1?$vector@V?$sub_match@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@V?$allocator@V?$sub_match@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::sub_match<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>>>::~vector<std::sub_match<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>>>(void)
0x1800280e0  nop
0x1800280e1  lea     rcx, [rbp+2D0h+var_290]
0x1800280e5  call    ??1?$vector@V?$sub_match@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@V?$allocator@V?$sub_match@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::sub_match<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>>>::~vector<std::sub_match<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>>>(void)
0x1800280ea  nop
0x1800280eb  lea     rcx, [rbp+2D0h+var_2E8]; void *
0x1800280ef  call    ??1?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@XZ; std::basic_regex<ushort,std::regex_traits<ushort>>::~basic_regex<ushort,std::regex_traits<ushort>>(void)
0x1800280f4  nop
0x1800280f5  lea     rcx, [rbp+2D0h+var_108]
0x1800280fc  jmp     loc_1800282E4
0x180028101  mov     r8d, 0Bh
0x180028107  lea     rdx, aDisplayname; "DisplayName"
0x18002810e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180028113  nop
0x180028114  lea     r9, [rbp+2D0h+var_E8]
0x18002811b  mov     r8, r12
0x18002811e  mov     rdx, rsi
0x180028121  lea     rcx, [rbp+2D0h+var_C0]
0x180028128  call    ?GetStringOrDefault@RegOperations@AppCompatUtility@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@AEBV34@1@Z; AppCompatUtility::RegOperations::GetStringOrDefault(HKEY__ *,std::wstring const &,std::wstring const &)
0x18002812d  nop
0x18002812e  lea     rcx, [rbp+2D0h+var_E8]; void *
0x180028135  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002813a  lea     rcx, [rdi+10h]
0x18002813e  lea     r8, [rbp+2D0h+var_C0]
0x180028145  lea     rdx, [rsp+3D0h+var_390]
0x18002814a  call    ?find@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::find(std::wstring const &)
0x18002814f  mov     rcx, [rdi+18h]
0x180028153  cmp     [rax], rcx
0x180028156  jnz     loc_180028248
  ... truncated ...
```
