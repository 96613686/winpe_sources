# CRestoreManager::PruneLastRestoreTimes(void)

- ea: `0x14002896c`
- end: `0x140028c55`
- name: `?PruneLastRestoreTimes@CRestoreManager@@SAXXZ`
- size: `745`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1400262e0`

## callees

- `0x140002470`
- `0x140002728`
- `0x140005468`
- `0x14000c8a0`
- `0x140014474`
- `0x140027f2c`
- `0x14002896c`
- `0x14002979c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x140028ad5`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x140028c16`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x140028ad5`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x140028c16`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140028c49`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140028c49`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140028a6d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140028a6d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140028a14`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140028a14`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140028a9d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140028a9d`

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
  unsigned __int64 v8; // r8
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
  phkResult = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
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
          v6 = utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_SetCapacity(&si128);
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
        if ( !utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(v7, ValueName, v8) )
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
0x14002896c  push    rbp
0x14002896e  push    rbx
0x14002896f  push    rsi
0x140028970  push    rdi
0x140028971  push    r12
0x140028973  push    r13
0x140028975  push    r14
0x140028977  push    r15
0x140028979  lea     rbp, [rsp-1B8h]
0x140028981  sub     rsp, 2B8h
0x140028988  mov     rax, cs:__security_cookie
0x14002898f  xor     rax, rsp
0x140028992  mov     [rbp+1F0h+var_50], rax
0x140028999  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1400289a1  lea     rcx, [rsp+2F0h+hKey]
0x1400289a6  xor     r13d, r13d
0x1400289a9  mov     [rsp+2F0h+cbData], 8
0x1400289b1  or      r15, 0FFFFFFFFFFFFFFFFh
0x1400289b5  mov     [rsp+2F0h+dwDisposition], r13d
0x1400289ba  mov     [rsp+2F0h+hKey], r13
0x1400289bf  movdqu  [rsp+2F0h+var_280], xmm0
0x1400289c5  mov     [rbp+1F0h+var_270], r15
0x1400289c9  mov     qword ptr [rsp+2F0h+Data], r13
0x1400289ce  mov     qword ptr [rbp+1F0h+SystemTimeAsFileTime.dwLowDateTime], r13
0x1400289d2  mov     [rsp+2F0h+cchValueName], 104h
0x1400289da  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1400289df  lea     rcx, [rsp+2F0h+dwDisposition]
0x1400289e4  xor     r9d, r9d; lpClass
0x1400289e7  mov     [rsp+2F0h+lpdwDisposition], rcx; lpdwDisposition
0x1400289ec  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\Windows\\Windows E"...
0x1400289f3  mov     [rsp+2F0h+phkResult], rax; phkResult
0x1400289f8  xor     r8d, r8d; Reserved
0x1400289fb  mov     [rsp+2F0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x140028a00  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140028a07  mov     [rsp+2F0h+samDesired], 103h; samDesired
0x140028a0f  mov     [rsp+2F0h+dwOptions], r13d; dwOptions
0x140028a14  call    cs:__imp_RegCreateKeyExW
0x140028a1a  test    eax, eax
0x140028a1c  jz      short loc_140028A96
0x140028a1e  jle     short loc_140028A28
0x140028a20  movzx   eax, ax
0x140028a23  or      eax, 80070000h
0x140028a28  mov     rcx, cs:WPP_GLOBAL_Control
0x140028a2f  lea     r14, WPP_GLOBAL_Control
0x140028a36  cmp     rcx, r14
0x140028a39  jz      short loc_140028A59
0x140028a3b  test    byte ptr [rcx+1Ch], 1
0x140028a3f  jz      short loc_140028A59
0x140028a41  mov     rcx, [rcx+10h]
0x140028a45  lea     r8, WPP_ebdcbfb5f87130f40ccbe77ddf731309_Traceguids
0x140028a4c  mov     edx, 2Eh ; '.'
0x140028a51  mov     r9d, eax
0x140028a54  call    WPP_SF_d
0x140028a59  lea     rcx, [rsp+2F0h+var_280]
0x140028a5e  call    ??1?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@QEAA@XZ; utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::~vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(void)
0x140028a63  mov     rcx, [rsp+2F0h+hKey]; hKey
0x140028a68  test    rcx, rcx
0x140028a6b  jz      short loc_140028A73
0x140028a6d  call    cs:__imp_RegCloseKey
0x140028a73  mov     rcx, [rbp+1F0h+var_50]
0x140028a7a  xor     rcx, rsp; StackCookie
0x140028a7d  call    __security_check_cookie
0x140028a82  add     rsp, 2B8h
0x140028a89  pop     r15
0x140028a8b  pop     r14
0x140028a8d  pop     r13
0x140028a8f  pop     r12
0x140028a91  pop     rdi
0x140028a92  pop     rsi
0x140028a93  pop     rbx
0x140028a94  pop     rbp
0x140028a95  retn
0x140028a96  lea     rcx, [rbp+1F0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140028a9a  mov     r12d, r13d
0x140028a9d  call    cs:__imp_GetSystemTimeAsFileTime
0x140028aa3  mov     rcx, [rsp+2F0h+hKey]; hKey
0x140028aa8  lea     rax, [rsp+2F0h+cbData]
0x140028aad  mov     rbx, qword ptr [rbp+1F0h+SystemTimeAsFileTime.dwLowDateTime]
0x140028ab1  lea     r9, [rsp+2F0h+cchValueName]; lpcchValueName
0x140028ab6  mov     [rsp+2F0h+phkResult], rax; lpcbData
0x140028abb  lea     r8, [rbp+1F0h+ValueName]; lpValueName
0x140028abf  lea     rax, [rsp+2F0h+Data]
0x140028ac4  xor     edx, edx; dwIndex
0x140028ac6  mov     [rsp+2F0h+lpSecurityAttributes], rax; lpData
0x140028acb  mov     qword ptr [rsp+2F0h+samDesired], r13; lpType
0x140028ad0  mov     qword ptr [rsp+2F0h+dwOptions], r13; lpReserved
0x140028ad5  call    cs:__imp_RegEnumValueW
0x140028adb  cmp     eax, 103h
0x140028ae0  jz      loc_140028C31
0x140028ae6  lea     r14, WPP_GLOBAL_Control
0x140028aed  mov     r8, 3FFFFFFFFFFFFFFh
0x140028af7  cmp     [rsp+2F0h+cbData], 8
0x140028afc  jnz     short loc_140028B12
0x140028afe  mov     rax, rbx
0x140028b01  sub     rax, qword ptr [rsp+2F0h+Data]
0x140028b06  cmp     rax, 23C34600h
0x140028b0c  jbe     loc_140028BD4
0x140028b12  cmp     qword ptr [rsp+2F0h+var_280+8], r15
0x140028b17  jnz     short loc_140028B52
0x140028b19  mov     rcx, r15
0x140028b1c  sub     rcx, qword ptr [rsp+2F0h+var_280]
0x140028b21  sar     rcx, 5
0x140028b25  mov     rax, rcx
0x140028b28  shr     rax, 2
0x140028b2c  imul    rdx, rax, 7
0x140028b30  add     rdx, 8
0x140028b34  cmp     rdx, r8
0x140028b37  cmova   rdx, r8
0x140028b3b  cmp     rcx, rdx
0x140028b3e  jnb     short loc_140028BA7
0x140028b40  lea     rcx, [rsp+2F0h+var_280]
0x140028b45  call    ?_SetCapacity@?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@AEAA_N_K@Z; utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_SetCapacity(unsigned __int64)
0x140028b4a  mov     r15, [rbp+1F0h+var_270]
0x140028b4e  test    al, al
0x140028b50  jz      short loc_140028BA7
0x140028b52  mov     rdi, qword ptr [rsp+2F0h+var_280+8]
0x140028b57  lea     rax, [rbp+1F0h+ValueName]
0x140028b5b  or      r8, 0FFFFFFFFFFFFFFFFh
0x140028b5f  lea     rsi, [rdi+10h]
0x140028b63  mov     [rdi], rsi
0x140028b66  mov     [rdi+8], rsi
0x140028b6a  mov     [rsi], r13w
0x140028b6e  inc     r8
0x140028b71  cmp     [rax+r8*2], r13w
0x140028b76  jnz     short loc_140028B6E
0x140028b78  lea     rdx, [rbp+1F0h+ValueName]
0x140028b7c  mov     rcx, rdi
0x140028b7f  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x140028b84  test    al, al
0x140028b86  jz      short loc_140028B93
0x140028b88  lea     rax, [rdi+20h]
0x140028b8c  mov     qword ptr [rsp+2F0h+var_280+8], rax
0x140028b91  jmp     short loc_140028BD4
0x140028b93  cmp     [rdi], rsi
0x140028b96  jz      short loc_140028BA7
0x140028b98  mov     rcx, [rdi]; void *
0x140028b9b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140028ba2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140028ba7  mov     rcx, cs:WPP_GLOBAL_Control
0x140028bae  cmp     rcx, r14
0x140028bb1  jz      short loc_140028BD4
0x140028bb3  test    byte ptr [rcx+1Ch], 1
0x140028bb7  jz      short loc_140028BD4
0x140028bb9  mov     rcx, [rcx+10h]
0x140028bbd  lea     r8, WPP_ebdcbfb5f87130f40ccbe77ddf731309_Traceguids
0x140028bc4  mov     edx, 2Fh ; '/'
0x140028bc9  mov     r9d, 8007000Eh
0x140028bcf  call    WPP_SF_d
0x140028bd4  mov     rcx, [rsp+2F0h+hKey]; hKey
0x140028bd9  lea     rax, [rsp+2F0h+cbData]
0x140028bde  mov     [rsp+2F0h+phkResult], rax; lpcbData
0x140028be3  lea     r9, [rsp+2F0h+cchValueName]; lpcchValueName
0x140028be8  lea     rax, [rsp+2F0h+Data]
0x140028bed  mov     [rsp+2F0h+cchValueName], 104h
0x140028bf5  mov     [rsp+2F0h+lpSecurityAttributes], rax; lpData
0x140028bfa  lea     r8, [rbp+1F0h+ValueName]; lpValueName
0x140028bfe  inc     r12d
0x140028c01  mov     qword ptr [rsp+2F0h+samDesired], r13; lpType
0x140028c06  mov     edx, r12d; dwIndex
0x140028c09  mov     qword ptr [rsp+2F0h+dwOptions], r13; lpReserved
0x140028c0e  mov     [rsp+2F0h+cbData], 8
0x140028c16  call    cs:__imp_RegEnumValueW
0x140028c1c  mov     r8, 3FFFFFFFFFFFFFFh
0x140028c26  cmp     eax, 103h
0x140028c2b  jnz     loc_140028AF7
0x140028c31  mov     rbx, qword ptr [rsp+2F0h+var_280]
0x140028c36  cmp     rbx, qword ptr [rsp+2F0h+var_280+8]
0x140028c3b  jz      loc_140028A59
0x140028c41  mov     rdx, [rbx]; lpValueName
0x140028c44  mov     rcx, [rsp+2F0h+hKey]; hKey
0x140028c49  call    cs:__imp_RegDeleteValueW
0x140028c4f  add     rbx, 20h ; ' '
0x140028c53  jmp     short loc_140028C36
```
