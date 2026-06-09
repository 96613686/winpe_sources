# CRestoreManager::PruneLastRestoreTimes(void)

- ea: `0x14002a45c`
- end: `0x14002a76a`
- name: `?PruneLastRestoreTimes@CRestoreManager@@SAXXZ`
- size: `782`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140027c40`

## callees

- `0x140002490`
- `0x140002748`
- `0x14000551c`
- `0x14000ca20`
- `0x140014f14`
- `0x14002996c`
- `0x14002a45c`
- `0x14002b35c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x14002a5d8`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x14002a71f`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x14002a5d8`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x14002a71f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x14002a758`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x14002a758`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002a563`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002a563`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14002a504`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14002a504`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14002a59a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14002a59a`

## pseudocode

```c
void CRestoreManager::PruneLastRestoreTimes(void)
{
  __int64 v0; // r15
  HKEY *phkResult; // rax
  int v2; // eax
  DWORD v3; // r12d
  struct _FILETIME v4; // rbx
  unsigned __int64 v5; // rdx
  char v6; // al
  __int64 v7; // rdi
  __int64 v8; // r8
  _WORD *v9; // rsi
  LPCWSTR *i; // rbx
  DWORD cbData; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cchValueName; // [rsp+54h] [rbp-ACh] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  BYTE Data[8]; // [rsp+60h] [rbp-A0h] BYREF
  DWORD dwDisposition; // [rsp+68h] [rbp-98h] BYREF
  __m128i si128; // [rsp+70h] [rbp-90h] BYREF
  __int64 v17; // [rsp+80h] [rbp-80h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+88h] [rbp-78h] BYREF
  WCHAR ValueName[264]; // [rsp+90h] [rbp-70h] BYREF

  cbData = 8;
  v0 = -1;
  dwDisposition = 0;
  hKey = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v17 = -1;
  *(_QWORD *)Data = 0;
  SystemTimeAsFileTime = 0;
  cchValueName = 260;
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  v2 = RegCreateKeyExW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Hangs\\NHRTimes",
         0,
         0,
         0,
         0x103u,
         0,
         phkResult,
         &dwDisposition);
  if ( !v2 )
  {
    v3 = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v4 = SystemTimeAsFileTime;
    if ( RegEnumValueW(hKey, 0, ValueName, &cchValueName, 0, 0, Data, &cbData) == 259 )
    {
LABEL_28:
      for ( i = (LPCWSTR *)si128.m128i_i64[0]; i != (LPCWSTR *)si128.m128i_i64[1]; i += 4 )
        RegDeleteValueW(hKey, *i);
      goto LABEL_7;
    }
    while ( 1 )
    {
      if ( cbData != 8 || *(_QWORD *)&v4 - *(_QWORD *)Data > 0x23C34600u )
      {
        if ( si128.m128i_i64[1] == v0 )
        {
          v5 = 7 * ((unsigned __int64)((v0 - si128.m128i_i64[0]) >> 5) >> 2) + 8;
          if ( v5 > 0x3FFFFFFFFFFFFFFLL )
            v5 = 0x3FFFFFFFFFFFFFFLL;
          if ( (v0 - si128.m128i_i64[0]) >> 5 >= v5 )
            goto LABEL_24;
          v6 = utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_SetCapacity(
                 &si128,
                 v5,
                 0x3FFFFFFFFFFFFFFLL);
          v0 = v17;
          if ( !v6 )
            goto LABEL_24;
        }
        v7 = si128.m128i_i64[1];
        v8 = -1;
        v9 = (_WORD *)(si128.m128i_i64[1] + 16);
        *(_QWORD *)si128.m128i_i64[1] = si128.m128i_i64[1] + 16;
        *(_QWORD *)(v7 + 8) = v9;
        *v9 = 0;
        do
          ++v8;
        while ( ValueName[v8] );
        if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                 v7,
                                 ValueName) )
        {
          if ( *(_WORD **)v7 != v9 )
            operator delete(*(void **)v7, (const struct std::nothrow_t *)&std::nothrow);
LABEL_24:
          if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              47,
              WPP_ebdcbfb5f87130f40ccbe77ddf731309_Traceguids,
              2147942414LL);
          }
          goto LABEL_27;
        }
        si128.m128i_i64[1] = v7 + 32;
      }
LABEL_27:
      cchValueName = 260;
      ++v3;
      cbData = 8;
      if ( RegEnumValueW(hKey, v3, ValueName, &cchValueName, 0, 0, Data, &cbData) == 259 )
        goto LABEL_28;
    }
  }
  if ( v2 > 0 )
    v2 = (unsigned __int16)v2 | 0x80070000;
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_ebdcbfb5f87130f40ccbe77ddf731309_Traceguids, (unsigned int)v2);
  }
LABEL_7:
  utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::~vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(&si128);
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x14002a45c  push    rbp
0x14002a45e  push    rbx
0x14002a45f  push    rsi
0x14002a460  push    rdi
0x14002a461  push    r12
0x14002a463  push    r13
0x14002a465  push    r14
0x14002a467  push    r15
0x14002a469  lea     rbp, [rsp-1B8h]
0x14002a471  sub     rsp, 2B8h
0x14002a478  mov     rax, cs:__security_cookie
0x14002a47f  xor     rax, rsp
0x14002a482  mov     [rbp+1F0h+var_50], rax
0x14002a489  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x14002a491  lea     rcx, [rsp+2F0h+hKey]
0x14002a496  xor     r13d, r13d
0x14002a499  mov     [rsp+2F0h+cbData], 8
0x14002a4a1  or      r15, 0FFFFFFFFFFFFFFFFh
0x14002a4a5  mov     [rsp+2F0h+dwDisposition], r13d
0x14002a4aa  mov     [rsp+2F0h+hKey], r13
0x14002a4af  movdqu  [rsp+2F0h+var_280], xmm0
0x14002a4b5  mov     [rbp+1F0h+var_270], r15
0x14002a4b9  mov     qword ptr [rsp+2F0h+Data], r13
0x14002a4be  mov     qword ptr [rbp+1F0h+SystemTimeAsFileTime.dwLowDateTime], r13
0x14002a4c2  mov     [rsp+2F0h+cchValueName], 104h
0x14002a4ca  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14002a4cf  lea     rcx, [rsp+2F0h+dwDisposition]
0x14002a4d4  xor     r9d, r9d; lpClass
0x14002a4d7  mov     [rsp+2F0h+lpdwDisposition], rcx; lpdwDisposition
0x14002a4dc  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\Windows\\Windows E"...
0x14002a4e3  mov     [rsp+2F0h+phkResult], rax; phkResult
0x14002a4e8  xor     r8d, r8d; Reserved
0x14002a4eb  mov     [rsp+2F0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x14002a4f0  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14002a4f7  mov     [rsp+2F0h+samDesired], 103h; samDesired
0x14002a4ff  mov     [rsp+2F0h+dwOptions], r13d; dwOptions
0x14002a504  call    cs:__imp_RegCreateKeyExW
0x14002a50b  nop     dword ptr [rax+rax+00h]
0x14002a510  test    eax, eax
0x14002a512  jz      short loc_14002A593
0x14002a514  jle     short loc_14002A51E
0x14002a516  movzx   eax, ax
0x14002a519  or      eax, 80070000h
0x14002a51e  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a525  lea     r14, WPP_GLOBAL_Control
0x14002a52c  cmp     rcx, r14
0x14002a52f  jz      short loc_14002A54F
0x14002a531  test    byte ptr [rcx+1Ch], 1
0x14002a535  jz      short loc_14002A54F
0x14002a537  mov     rcx, [rcx+10h]
0x14002a53b  lea     r8, WPP_ebdcbfb5f87130f40ccbe77ddf731309_Traceguids
0x14002a542  mov     edx, 2Eh ; '.'
0x14002a547  mov     r9d, eax
0x14002a54a  call    WPP_SF_d
0x14002a54f  lea     rcx, [rsp+2F0h+var_280]
0x14002a554  call    ??1?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@QEAA@XZ; utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::~vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(void)
0x14002a559  mov     rcx, [rsp+2F0h+hKey]; hKey
0x14002a55e  test    rcx, rcx
0x14002a561  jz      short loc_14002A56F
0x14002a563  call    cs:__imp_RegCloseKey
0x14002a56a  nop     dword ptr [rax+rax+00h]
0x14002a56f  mov     rcx, [rbp+1F0h+var_50]
0x14002a576  xor     rcx, rsp; StackCookie
0x14002a579  call    __security_check_cookie
0x14002a57e  add     rsp, 2B8h
0x14002a585  pop     r15
0x14002a587  pop     r14
0x14002a589  pop     r13
0x14002a58b  pop     r12
0x14002a58d  pop     rdi
0x14002a58e  pop     rsi
0x14002a58f  pop     rbx
0x14002a590  pop     rbp
0x14002a591  retn
0x14002a593  lea     rcx, [rbp+1F0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14002a597  mov     r12d, r13d
0x14002a59a  call    cs:__imp_GetSystemTimeAsFileTime
0x14002a5a1  nop     dword ptr [rax+rax+00h]
0x14002a5a6  mov     rcx, [rsp+2F0h+hKey]; hKey
0x14002a5ab  lea     rax, [rsp+2F0h+cbData]
0x14002a5b0  mov     rbx, qword ptr [rbp+1F0h+SystemTimeAsFileTime.dwLowDateTime]
0x14002a5b4  lea     r9, [rsp+2F0h+cchValueName]; lpcchValueName
0x14002a5b9  mov     [rsp+2F0h+phkResult], rax; lpcbData
0x14002a5be  lea     r8, [rbp+1F0h+ValueName]; lpValueName
0x14002a5c2  lea     rax, [rsp+2F0h+Data]
0x14002a5c7  xor     edx, edx; dwIndex
0x14002a5c9  mov     [rsp+2F0h+lpSecurityAttributes], rax; lpData
0x14002a5ce  mov     qword ptr [rsp+2F0h+samDesired], r13; lpType
0x14002a5d3  mov     qword ptr [rsp+2F0h+dwOptions], r13; lpReserved
0x14002a5d8  call    cs:__imp_RegEnumValueW
0x14002a5df  nop     dword ptr [rax+rax+00h]
0x14002a5e4  cmp     eax, 103h
0x14002a5e9  jz      loc_14002A740
0x14002a5ef  lea     r14, WPP_GLOBAL_Control
0x14002a5f6  mov     r8, 3FFFFFFFFFFFFFFh
0x14002a600  cmp     [rsp+2F0h+cbData], 8
0x14002a605  jnz     short loc_14002A61B
0x14002a607  mov     rax, rbx
0x14002a60a  sub     rax, qword ptr [rsp+2F0h+Data]
0x14002a60f  cmp     rax, 23C34600h
0x14002a615  jbe     loc_14002A6DD
0x14002a61b  cmp     qword ptr [rsp+2F0h+var_280+8], r15
0x14002a620  jnz     short loc_14002A65B
0x14002a622  mov     rcx, r15
0x14002a625  sub     rcx, qword ptr [rsp+2F0h+var_280]
0x14002a62a  sar     rcx, 5
0x14002a62e  mov     rax, rcx
0x14002a631  shr     rax, 2
0x14002a635  imul    rdx, rax, 7
0x14002a639  add     rdx, 8
0x14002a63d  cmp     rdx, r8
0x14002a640  cmova   rdx, r8
0x14002a644  cmp     rcx, rdx
0x14002a647  jnb     short loc_14002A6B0
0x14002a649  lea     rcx, [rsp+2F0h+var_280]
0x14002a64e  call    ?_SetCapacity@?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@AEAA_N_K@Z; utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_SetCapacity(unsigned __int64)
0x14002a653  mov     r15, [rbp+1F0h+var_270]
0x14002a657  test    al, al
0x14002a659  jz      short loc_14002A6B0
0x14002a65b  mov     rdi, qword ptr [rsp+2F0h+var_280+8]
0x14002a660  lea     rax, [rbp+1F0h+ValueName]
0x14002a664  or      r8, 0FFFFFFFFFFFFFFFFh
0x14002a668  lea     rsi, [rdi+10h]
0x14002a66c  mov     [rdi], rsi
0x14002a66f  mov     [rdi+8], rsi
0x14002a673  mov     [rsi], r13w
0x14002a677  inc     r8
0x14002a67a  cmp     [rax+r8*2], r13w
0x14002a67f  jnz     short loc_14002A677
0x14002a681  lea     rdx, [rbp+1F0h+ValueName]
0x14002a685  mov     rcx, rdi
0x14002a688  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x14002a68d  test    al, al
0x14002a68f  jz      short loc_14002A69C
0x14002a691  lea     rax, [rdi+20h]
0x14002a695  mov     qword ptr [rsp+2F0h+var_280+8], rax
0x14002a69a  jmp     short loc_14002A6DD
0x14002a69c  cmp     [rdi], rsi
0x14002a69f  jz      short loc_14002A6B0
0x14002a6a1  mov     rcx, [rdi]; void *
0x14002a6a4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002a6ab  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002a6b0  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a6b7  cmp     rcx, r14
0x14002a6ba  jz      short loc_14002A6DD
0x14002a6bc  test    byte ptr [rcx+1Ch], 1
0x14002a6c0  jz      short loc_14002A6DD
0x14002a6c2  mov     rcx, [rcx+10h]
0x14002a6c6  lea     r8, WPP_ebdcbfb5f87130f40ccbe77ddf731309_Traceguids
0x14002a6cd  mov     edx, 2Fh ; '/'
0x14002a6d2  mov     r9d, 8007000Eh
0x14002a6d8  call    WPP_SF_d
0x14002a6dd  mov     rcx, [rsp+2F0h+hKey]; hKey
0x14002a6e2  lea     rax, [rsp+2F0h+cbData]
0x14002a6e7  mov     [rsp+2F0h+phkResult], rax; lpcbData
0x14002a6ec  lea     r9, [rsp+2F0h+cchValueName]; lpcchValueName
0x14002a6f1  lea     rax, [rsp+2F0h+Data]
0x14002a6f6  mov     [rsp+2F0h+cchValueName], 104h
0x14002a6fe  mov     [rsp+2F0h+lpSecurityAttributes], rax; lpData
0x14002a703  lea     r8, [rbp+1F0h+ValueName]; lpValueName
0x14002a707  inc     r12d
0x14002a70a  mov     qword ptr [rsp+2F0h+samDesired], r13; lpType
0x14002a70f  mov     edx, r12d; dwIndex
0x14002a712  mov     qword ptr [rsp+2F0h+dwOptions], r13; lpReserved
0x14002a717  mov     [rsp+2F0h+cbData], 8
0x14002a71f  call    cs:__imp_RegEnumValueW
0x14002a726  nop     dword ptr [rax+rax+00h]
0x14002a72b  mov     r8, 3FFFFFFFFFFFFFFh
0x14002a735  cmp     eax, 103h
0x14002a73a  jnz     loc_14002A600
0x14002a740  mov     rbx, qword ptr [rsp+2F0h+var_280]
0x14002a745  cmp     rbx, qword ptr [rsp+2F0h+var_280+8]
0x14002a74a  jz      loc_14002A54F
0x14002a750  mov     rdx, [rbx]; lpValueName
0x14002a753  mov     rcx, [rsp+2F0h+hKey]; hKey
0x14002a758  call    cs:__imp_RegDeleteValueW
0x14002a75f  nop     dword ptr [rax+rax+00h]
0x14002a764  add     rbx, 20h ; ' '
0x14002a768  jmp     short loc_14002A745
```
