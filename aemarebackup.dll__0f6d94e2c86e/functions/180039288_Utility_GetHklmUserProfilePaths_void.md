# Utility::GetHklmUserProfilePaths(void)

- ea: `0x180039288`
- end: `0x180039723`
- name: `?GetHklmUserProfilePaths@Utility@@SAAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ`
- size: `1179`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180039db0`
- `0x18003dd7c`

## callees

- `0x180004ea0`
- `0x18000527c`
- `0x180006eac`
- `0x180006f14`
- `0x18000fb60`
- `0x1800134b8`
- `0x1800149a8`
- `0x18002cd04`
- `0x1800334b8`
- `0x180039288`
- `0x180039b70`
- `0x180042bb0`
- `0x180044344`
- `0x180044a1c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x180039512`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x180039512`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800392fc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800392fc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003965f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003965f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180039418`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180039418`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003934a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003934a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003939f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003939f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180039655`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180039655`

## string_xrefs

- `0x180039690`: `onecore\internal\base\inc\appcompat\inventory\utility.cpp`
- `0x1800396a5`: `onecore\internal\base\inc\appcompat\inventory\utility.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 *Utility::GetHklmUserProfilePaths()
{
  __int64 v0; // rbx
  const WCHAR *v1; // rdx
  int v2; // eax
  DWORD v3; // ebx
  __m128i si128; // xmm6
  WCHAR *v5; // r8
  LSTATUS v6; // eax
  __int64 *v7; // rdx
  unsigned __int64 v8; // r8
  LPWSTR *v9; // rdx
  unsigned __int64 v10; // r8
  __int64 v11; // rax
  unsigned __int16 *v12; // rcx
  __int128 *v13; // rax
  __int128 *v14; // rax
  __int128 *v15; // rax
  __int128 *v16; // rax
  __int128 *v17; // rax
  __int128 *v18; // rax
  __int128 *v19; // rax
  __int128 *v20; // rax
  __int64 v21; // rdx
  int phkResult; // [rsp+28h] [rbp-E0h]
  int phkResulta; // [rsp+28h] [rbp-E0h]
  DWORD cSubKeys; // [rsp+68h] [rbp-A0h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+6Ch] [rbp-9Ch] BYREF
  DWORD cchName[2]; // [rsp+70h] [rbp-98h] BYREF
  HKEY hKey[2]; // [rsp+78h] [rbp-90h] BYREF
  __int128 v29; // [rsp+88h] [rbp-80h] BYREF
  __m128i v30; // [rsp+98h] [rbp-70h]
  LPWSTR lpName[3]; // [rsp+A8h] [rbp-60h] BYREF
  unsigned __int64 v32; // [rsp+C0h] [rbp-48h]
  _OWORD v33[2]; // [rsp+C8h] [rbp-40h] BYREF
  _OWORD v34[2]; // [rsp+E8h] [rbp-20h] BYREF
  char *v35[4]; // [rsp+108h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+170h] [rbp+68h]

  v0 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( dword_18011C138 > *(_DWORD *)(v0 + 4) )
  {
    Init_thread_header(&dword_18011C138);
    if ( dword_18011C138 == -1 )
    {
      atexit(Utility::GetHklmUserProfilePaths_::_2_::_dynamic_atexit_destructor_for__userProfilePaths__);
      Init_thread_footer(&dword_18011C138);
    }
  }
  if ( dword_18011C158 > *(_DWORD *)(v0 + 4) )
  {
    Init_thread_header(&dword_18011C158);
    if ( dword_18011C158 == -1 )
    {
      atexit(Utility::GetHklmUserProfilePaths_::_2_::_dynamic_atexit_destructor_for__programDataPath__);
      Init_thread_footer(&dword_18011C158);
    }
  }
  if ( byte_180119F3D )
  {
    AcquireSRWLockExclusive(&stru_18011BF00);
    hKey[1] = (HKEY)&stru_18011BF00;
    if ( byte_180119F3D )
    {
      hKey[0] = 0;
      v1 = (const WCHAR *)&Utility::ProfileListSubKeyPath;
      if ( (unsigned __int64)qword_18011BB08 > 7 )
        v1 = Utility::ProfileListSubKeyPath;
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v1, 0, 0x20019u, hKey) )
      {
        cSubKeys = 0;
        cbMaxSubKeyLen = 0;
        v2 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
        if ( v2 > 0 )
          v2 = (unsigned __int16)v2 | 0x80070000;
        if ( v2 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x58E,
            (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\utility.cpp",
            (const char *)(unsigned int)v2,
            phkResult);
        v3 = 0;
        if ( cSubKeys )
        {
          si128 = _mm_load_si128((const __m128i *)&_xmm);
          do
          {
            cchName[0] = cbMaxSubKeyLen + 1;
            std::wstring::wstring(lpName, cbMaxSubKeyLen + 1, 0);
            v5 = (WCHAR *)lpName;
            if ( v32 > 7 )
              v5 = lpName[0];
            v6 = RegEnumKeyExW(hKey[0], v3, v5, cchName, 0, 0, 0, 0);
            if ( v6 < 0 )
              wil::details::in1diag3::_Throw_Hr(
                retaddr,
                (void *)0x59C,
                (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\utility.cpp",
                (const char *)(unsigned int)v6,
                phkResulta);
            std::wstring::resize(lpName);
            v7 = &Utility::ProfileImagePath;
            if ( (unsigned __int64)qword_18011BB28 > 7 )
              v7 = (__int64 *)Utility::ProfileImagePath;
            memset(v34, 0, sizeof(v34));
            v8 = -1;
            do
              ++v8;
            while ( *((_WORD *)v7 + v8) );
            std::wstring::_Construct<1,unsigned short const *>((char **)v34, v7, v8);
            v9 = lpName;
            if ( v32 > 7 )
              v9 = (LPWSTR *)lpName[0];
            memset(v33, 0, sizeof(v33));
            v10 = -1;
            do
              ++v10;
            while ( *((_WORD *)v9 + v10) );
            std::wstring::_Construct<1,unsigned short const *>((char **)v33, v9, v10);
            Utility::GetRegValueString(&v29, hKey[0], v33, v34);
            std::wstring::~wstring((char **)v33);
            std::wstring::~wstring((char **)v34);
            v11 = Utility::ToLower(v35, &v29);
            std::wstring::operator=(&v29, v11);
            std::wstring::~wstring(v35);
            if ( v30.m128i_i64[0] >= 9uLL )
            {
              v12 = (unsigned __int16 *)&v29;
              if ( v30.m128i_i64[1] > 7uLL )
                v12 = (unsigned __int16 *)v29;
              if ( (unsigned int)_o_iswalpha(*v12) )
              {
                v13 = &v29;
                if ( v30.m128i_i64[1] > 7uLL )
                  v13 = (__int128 *)v29;
                if ( *((_WORD *)v13 + 1) == 58 )
                {
                  v14 = &v29;
                  if ( v30.m128i_i64[1] > 7uLL )
                    v14 = (__int128 *)v29;
                  if ( *((_WORD *)v14 + 2) == 92 )
                  {
                    v15 = &v29;
                    if ( v30.m128i_i64[1] > 7uLL )
                      v15 = (__int128 *)v29;
                    if ( *((_WORD *)v15 + 3) == 117 )
                    {
                      v16 = &v29;
                      if ( v30.m128i_i64[1] > 7uLL )
                        v16 = (__int128 *)v29;
                      if ( *((_WORD *)v16 + 4) == 115 )
                      {
                        v17 = &v29;
                        if ( v30.m128i_i64[1] > 7uLL )
                          v17 = (__int128 *)v29;
                        if ( *((_WORD *)v17 + 5) == 101 )
                        {
                          v18 = &v29;
                          if ( v30.m128i_i64[1] > 7uLL )
                            v18 = (__int128 *)v29;
                          if ( *((_WORD *)v18 + 6) == 114 )
                          {
                            v19 = &v29;
                            if ( v30.m128i_i64[1] > 7uLL )
                              v19 = (__int128 *)v29;
                            if ( *((_WORD *)v19 + 7) == 115 )
                            {
                              v20 = &v29;
                              if ( v30.m128i_i64[1] > 7uLL )
                                v20 = (__int128 *)v29;
                              if ( *((_WORD *)v20 + 8) == 92 )
                              {
                                v21 = qword_18011C148;
                                if ( qword_18011C148 == qword_18011C150 )
                                {
                                  std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(
                                    &qword_18011C140,
                                    qword_18011C148,
                                    &v29);
                                }
                                else
                                {
                                  *(_OWORD *)qword_18011C148 = 0;
                                  *(_QWORD *)(v21 + 16) = 0;
                                  *(_QWORD *)(v21 + 24) = 0;
                                  *(_OWORD *)v21 = v29;
                                  *(__m128i *)(v21 + 16) = v30;
                                  v30 = si128;
                                  LOWORD(v29) = 0;
                                  qword_18011C148 += 32;
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
            std::wstring::~wstring((char **)&v29);
            std::wstring::~wstring((char **)lpName);
            ++v3;
          }
          while ( v3 < cSubKeys );
        }
      }
      byte_180119F3D = 0;
      if ( hKey[0] )
        RegCloseKey(hKey[0]);
    }
    ReleaseSRWLockExclusive(&stru_18011BF00);
  }
  return &qword_18011C140;
}

```

## disassembly

```asm
0x180039288  mov     rax, rsp
0x18003928b  push    rbp
0x18003928c  push    rbx
0x18003928d  push    rdi
0x18003928e  push    r14
0x180039290  lea     rbp, [rax-68h]
0x180039294  sub     rsp, 148h
0x18003929b  movaps  xmmword ptr [rax-38h], xmm6
0x18003929f  mov     rax, cs:__security_cookie
0x1800392a6  xor     rax, rsp
0x1800392a9  mov     [rbp+60h+var_40], rax
0x1800392ad  mov     ecx, cs:_tls_index
0x1800392b3  mov     rax, gs:58h
0x1800392bc  mov     edi, 4
0x1800392c1  mov     rbx, [rax+rcx*8]
0x1800392c5  mov     eax, [rbx+rdi]
0x1800392c8  cmp     cs:dword_18011C138, eax
0x1800392ce  jg      loc_1800396B7
0x1800392d4  mov     eax, [rbx+rdi]
0x1800392d7  cmp     cs:dword_18011C158, eax
0x1800392dd  jg      loc_1800396ED
0x1800392e3  xor     edi, edi
0x1800392e5  cmp     cs:byte_180119F3D, dil
0x1800392ec  jz      loc_180039665
0x1800392f2  lea     r14, stru_18011BF00
0x1800392f9  mov     rcx, r14; SRWLock
0x1800392fc  call    cs:__imp_AcquireSRWLockExclusive
0x180039302  mov     [rsp+160h+hKey+8], r14
0x180039307  cmp     cs:byte_180119F3D, dil
0x18003930e  jz      loc_18003965C
0x180039314  mov     [rsp+160h+hKey], rdi
0x180039319  lea     rdx, ?ProfileListSubKeyPath@Utility@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Utility::ProfileListSubKeyPath
0x180039320  cmp     cs:qword_18011BB08, 7
0x180039328  cmova   rdx, cs:?ProfileListSubKeyPath@Utility@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; lpSubKey
0x180039330  lea     rax, [rsp+160h+hKey]
0x180039335  mov     [rsp+160h+phkResult], rax; phkResult
0x18003933a  mov     r9d, 20019h; samDesired
0x180039340  xor     r8d, r8d; ulOptions
0x180039343  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003934a  call    cs:__imp_RegOpenKeyExW
0x180039350  test    eax, eax
0x180039352  jnz     loc_180039644
0x180039358  mov     [rsp+160h+cSubKeys], edi
0x18003935c  mov     [rsp+160h+cbMaxSubKeyLen], edi
0x180039360  mov     [rsp+160h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x180039365  mov     [rsp+160h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x18003936a  mov     [rsp+160h+lpcbMaxValueLen], rdi; lpcbMaxValueLen
0x18003936f  mov     [rsp+160h+lpcbMaxValueNameLen], rdi; lpcbMaxValueNameLen
0x180039374  mov     [rsp+160h+lpcValues], rdi; lpcValues
0x180039379  mov     [rsp+160h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x18003937e  lea     rax, [rsp+160h+cbMaxSubKeyLen]
0x180039383  mov     [rsp+160h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180039388  lea     rax, [rsp+160h+cSubKeys]
0x18003938d  mov     [rsp+160h+phkResult], rax; int
0x180039392  xor     r9d, r9d; lpReserved
0x180039395  xor     r8d, r8d; lpcchClass
0x180039398  xor     edx, edx; lpClass
0x18003939a  mov     rcx, [rsp+160h+hKey]; hKey
0x18003939f  call    cs:__imp_RegQueryInfoKeyW
0x1800393a5  test    eax, eax
0x1800393a7  jle     short loc_1800393B1
0x1800393a9  movzx   eax, ax
0x1800393ac  or      eax, 80070000h
0x1800393b1  mov     rcx, [rbp+68h]; this
0x1800393b5  test    eax, eax
0x1800393b7  js      loc_18003968D
0x1800393bd  mov     ebx, edi
0x1800393bf  cmp     [rsp+160h+cSubKeys], edi
0x1800393c3  jbe     loc_180039644
0x1800393c9  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1800393d1  mov     eax, [rsp+160h+cbMaxSubKeyLen]
0x1800393d5  inc     eax
0x1800393d7  mov     [rsp+160h+cchName], eax
0x1800393db  xor     r8d, r8d
0x1800393de  mov     edx, eax
0x1800393e0  lea     rcx, [rbp+60h+lpName]
0x1800393e4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x1800393e9  nop
0x1800393ea  lea     r8, [rbp+60h+lpName]
0x1800393ee  cmp     [rbp+60h+var_A8], 7
0x1800393f3  cmova   r8, [rbp+60h+lpName]; lpName
0x1800393f8  mov     [rsp+160h+lpcValues], rdi; lpftLastWriteTime
0x1800393fd  mov     [rsp+160h+lpcbMaxClassLen], rdi; lpcchClass
0x180039402  mov     [rsp+160h+lpcbMaxSubKeyLen], rdi; lpClass
0x180039407  mov     [rsp+160h+phkResult], rdi; int
0x18003940c  lea     r9, [rsp+160h+cchName]; lpcchName
0x180039411  mov     edx, ebx; dwIndex
0x180039413  mov     rcx, [rsp+160h+hKey]; hKey
0x180039418  call    cs:__imp_RegEnumKeyExW
0x18003941e  mov     rcx, [rbp+68h]; this
0x180039422  test    eax, eax
0x180039424  js      loc_1800396A2
0x18003942a  mov     edx, [rsp+160h+cchName]
0x18003942e  lea     rcx, [rbp+60h+lpName]; Src
0x180039432  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180039437  lea     rdx, ?ProfileImagePath@Utility@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Utility::ProfileImagePath
0x18003943e  cmp     cs:qword_18011BB28, 7
0x180039446  cmova   rdx, cs:?ProfileImagePath@Utility@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Utility::ProfileImagePath
0x18003944e  xorps   xmm0, xmm0
0x180039451  movups  [rbp+60h+var_80], xmm0
0x180039455  xorps   xmm1, xmm1
0x180039458  movdqu  [rbp+60h+var_70], xmm1
0x18003945d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180039461  inc     r8
0x180039464  cmp     [rdx+r8*2], di
0x180039469  jnz     short loc_180039461
0x18003946b  lea     rcx, [rbp+60h+var_80]
0x18003946f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180039474  nop
0x180039475  lea     rdx, [rbp+60h+lpName]
0x180039479  cmp     [rbp+60h+var_A8], 7
0x18003947e  cmova   rdx, [rbp+60h+lpName]
0x180039483  xorps   xmm0, xmm0
0x180039486  movups  [rbp+60h+var_A0], xmm0
0x18003948a  xorps   xmm1, xmm1
0x18003948d  movdqu  [rbp+60h+var_90], xmm1
0x180039492  or      r8, 0FFFFFFFFFFFFFFFFh
0x180039496  inc     r8
0x180039499  cmp     [rdx+r8*2], di
0x18003949e  jnz     short loc_180039496
0x1800394a0  lea     rcx, [rbp+60h+var_A0]
0x1800394a4  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800394a9  nop
0x1800394aa  lea     r9, [rbp+60h+var_80]
0x1800394ae  lea     r8, [rbp+60h+var_A0]
0x1800394b2  mov     rdx, [rsp+160h+hKey]
0x1800394b7  lea     rcx, [rbp+60h+var_E0]
0x1800394bb  call    ?GetRegValueString@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAUHKEY__@@AEBV23@1_N@Z; Utility::GetRegValueString(HKEY__ * const,std::wstring const &,std::wstring const &,bool)
0x1800394c0  nop
0x1800394c1  lea     rcx, [rbp+60h+var_A0]
0x1800394c5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800394ca  nop
0x1800394cb  lea     rcx, [rbp+60h+var_80]
0x1800394cf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800394d4  lea     rdx, [rbp+60h+var_E0]
0x1800394d8  lea     rcx, [rbp+60h+var_60]
0x1800394dc  call    ?ToLower@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::ToLower(std::wstring const &)
0x1800394e1  mov     rdx, rax
0x1800394e4  lea     rcx, [rbp+60h+var_E0]
0x1800394e8  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800394ed  lea     rcx, [rbp+60h+var_60]
0x1800394f1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800394f6  cmp     qword ptr [rbp+60h+var_D0], 9
0x1800394fb  jb      loc_180039625
0x180039501  lea     rcx, [rbp+60h+var_E0]
0x180039505  cmp     qword ptr [rbp+60h+var_D0+8], 7
0x18003950a  cmova   rcx, qword ptr [rbp+60h+var_E0]
0x18003950f  movzx   ecx, word ptr [rcx]
0x180039512  call    cs:__imp__o_iswalpha
0x180039518  test    eax, eax
0x18003951a  jz      loc_180039625
0x180039520  mov     rcx, qword ptr [rbp+60h+var_D0+8]
0x180039524  lea     rax, [rbp+60h+var_E0]
0x180039528  mov     rdx, qword ptr [rbp+60h+var_E0]
0x18003952c  cmp     rcx, 7
0x180039530  cmova   rax, rdx
0x180039534  cmp     word ptr [rax+2], 3Ah ; ':'
0x180039539  jnz     loc_180039625
0x18003953f  lea     rax, [rbp+60h+var_E0]
0x180039543  cmp     rcx, 7
0x180039547  cmova   rax, rdx
0x18003954b  cmp     word ptr [rax+4], 5Ch ; '\'
0x180039550  jnz     loc_180039625
0x180039556  lea     rax, [rbp+60h+var_E0]
0x18003955a  cmp     rcx, 7
0x18003955e  cmova   rax, rdx
0x180039562  cmp     word ptr [rax+6], 75h ; 'u'
0x180039567  jnz     loc_180039625
0x18003956d  lea     rax, [rbp+60h+var_E0]
0x180039571  cmp     rcx, 7
0x180039575  cmova   rax, rdx
0x180039579  cmp     word ptr [rax+8], 73h ; 's'
0x18003957e  jnz     loc_180039625
0x180039584  lea     rax, [rbp+60h+var_E0]
0x180039588  cmp     rcx, 7
0x18003958c  cmova   rax, rdx
0x180039590  cmp     word ptr [rax+0Ah], 65h ; 'e'
0x180039595  jnz     loc_180039625
0x18003959b  lea     rax, [rbp+60h+var_E0]
0x18003959f  cmp     rcx, 7
0x1800395a3  cmova   rax, rdx
0x1800395a7  cmp     word ptr [rax+0Ch], 72h ; 'r'
0x1800395ac  jnz     short loc_180039625
0x1800395ae  lea     rax, [rbp+60h+var_E0]
0x1800395b2  cmp     rcx, 7
0x1800395b6  cmova   rax, rdx
0x1800395ba  cmp     word ptr [rax+0Eh], 73h ; 's'
0x1800395bf  jnz     short loc_180039625
0x1800395c1  lea     rax, [rbp+60h+var_E0]
0x1800395c5  cmp     rcx, 7
0x1800395c9  cmova   rax, rdx
0x1800395cd  cmp     word ptr [rax+10h], 5Ch ; '\'
0x1800395d2  jnz     short loc_180039625
0x1800395d4  mov     rdx, cs:qword_18011C148
0x1800395db  cmp     rdx, cs:qword_18011C150
0x1800395e2  jz      short loc_180039614
0x1800395e4  xorps   xmm0, xmm0
0x1800395e7  movups  xmmword ptr [rdx], xmm0
0x1800395ea  mov     [rdx+10h], rdi
0x1800395ee  mov     [rdx+18h], rdi
0x1800395f2  movups  xmm0, [rbp+60h+var_E0]
0x1800395f6  movups  xmmword ptr [rdx], xmm0
0x1800395f9  movups  xmm1, [rbp+60h+var_D0]
0x1800395fd  movups  xmmword ptr [rdx+10h], xmm1
0x180039601  movdqu  [rbp+60h+var_D0], xmm6
0x180039606  mov     word ptr [rbp+60h+var_E0], di
0x18003960a  add     cs:qword_18011C148, 20h ; ' '
0x180039612  jmp     short loc_180039625
0x180039614  lea     r8, [rbp+60h+var_E0]
0x180039618  lea     rcx, qword_18011C140
0x18003961f  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x180039624  nop
0x180039625  lea     rcx, [rbp+60h+var_E0]
0x180039629  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003962e  nop
0x18003962f  lea     rcx, [rbp+60h+lpName]
0x180039633  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180039638  inc     ebx
0x18003963a  cmp     ebx, [rsp+160h+cSubKeys]
0x18003963e  jb      loc_1800393D1
0x180039644  mov     cs:byte_180119F3D, dil
0x18003964b  mov     rcx, [rsp+160h+hKey]; hKey
0x180039650  test    rcx, rcx
0x180039653  jz      short loc_18003965C
0x180039655  call    cs:__imp_RegCloseKey
0x18003965b  nop
0x18003965c  mov     rcx, r14; SRWLock
0x18003965f  call    cs:__imp_ReleaseSRWLockExclusive
0x180039665  lea     rax, qword_18011C140
0x18003966c  mov     rcx, [rbp+60h+var_40]
0x180039670  xor     rcx, rsp; StackCookie
0x180039673  call    __security_check_cookie
0x180039678  movaps  xmm6, [rsp+160h+var_38+8]
0x180039680  add     rsp, 148h
0x180039687  pop     r14
0x180039689  pop     rdi
0x18003968a  pop     rbx
0x18003968b  pop     rbp
0x18003968c  retn
0x18003968d  mov     r9d, eax; char *
0x180039690  lea     r8, aOnecoreInterna_1; "onecore\\internal\\base\\inc\\appcompat"...
0x180039697  mov     edx, 58Eh; void *
0x18003969c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800396a2  mov     r9d, eax; char *
0x1800396a5  lea     r8, aOnecoreInterna_1; "onecore\\internal\\base\\inc\\appcompat"...
0x1800396ac  mov     edx, 59Ch; void *
0x1800396b1  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800396b7  lea     rcx, dword_18011C138
0x1800396be  call    _Init_thread_header
0x1800396c3  cmp     cs:dword_18011C138, 0FFFFFFFFh
0x1800396ca  jnz     loc_1800392D4
0x1800396d0  lea     rcx, _Utility__GetHklmUserProfilePaths____2____dynamic_atexit_destructor_for__userProfilePaths__; void (__cdecl *)()
0x1800396d7  call    atexit
0x1800396dc  lea     rcx, dword_18011C138
0x1800396e3  call    _Init_thread_footer
0x1800396e8  jmp     loc_1800392D4
0x1800396ed  lea     rcx, dword_18011C158
0x1800396f4  call    _Init_thread_header
0x1800396f9  cmp     cs:dword_18011C158, 0FFFFFFFFh
0x180039700  jnz     loc_1800392E3
0x180039706  lea     rcx, _Utility__GetHklmUserProfilePaths____2____dynamic_atexit_destructor_for__programDataPath__; void (__cdecl *)()
0x18003970d  call    atexit
0x180039712  lea     rcx, dword_18011C158
0x180039719  call    _Init_thread_footer
0x18003971e  jmp     loc_1800392E3
```
