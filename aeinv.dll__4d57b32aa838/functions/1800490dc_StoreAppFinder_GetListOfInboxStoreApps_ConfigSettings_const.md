# StoreAppFinder::GetListOfInboxStoreApps(ConfigSettings const &)

- ea: `0x1800490dc`
- end: `0x1800493b1`
- name: `?GetListOfInboxStoreApps@StoreAppFinder@@SA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBVConfigSettings@@@Z`
- size: `725`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180041f68`
- `0x1800422a8`

## callees

- `0x18000e458`
- `0x180018a60`
- `0x1800404c4`
- `0x1800490dc`
- `0x1800493b8`
- `0x180050030`
- `0x180059920`
- `0x18005a8bc`
- `0x1800679f8`
- `0x180100418`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x1800491f7`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x180049336`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x1800491f7`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x180049336`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180049324`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180049324`
- `ADVAPI32!RegOpenKeyExW` at `0x180049152`
- `ADVAPI32!RegOpenKeyExW` at `0x18004926d`
- `ADVAPI32!RegOpenKeyExW` at `0x180049152`
- `ADVAPI32!RegOpenKeyExW` at `0x18004926d`
- `ADVAPI32!RegEnumKeyExW` at `0x1800491c2`
- `ADVAPI32!RegEnumKeyExW` at `0x1800492de`
- `ADVAPI32!RegEnumKeyExW` at `0x1800491c2`
- `ADVAPI32!RegEnumKeyExW` at `0x1800492de`

## string_xrefs

- `0x180049166`: `onecore\internal\base\inc\appcompat\inventory\storeappfinder.cpp`
- `0x180049228`: `onecore\internal\base\inc\appcompat\inventory\storeappfinder.cpp`
- `0x180049281`: `onecore\internal\base\inc\appcompat\inventory\storeappfinder.cpp`
- `0x180049367`: `onecore\internal\base\inc\appcompat\inventory\storeappfinder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
HKEY __fastcall StoreAppFinder::GetListOfInboxStoreApps(HKEY a1, __int64 a2)
{
  unsigned int v4; // eax
  DWORD v5; // edi
  LSTATUS v6; // ebx
  LSTATUS v7; // eax
  char v8; // dl
  __int16 v9; // r8
  unsigned __int64 v10; // r9
  __int64 v11; // rax
  unsigned int v12; // eax
  DWORD v13; // edi
  LSTATUS v14; // ebx
  LSTATUS v15; // eax
  unsigned __int64 v16; // r9
  char v17; // dl
  __int16 v18; // r8
  int v19; // r9d
  __int64 v20; // rax
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultb; // [rsp+20h] [rbp-E0h]
  int phkResultc; // [rsp+20h] [rbp-E0h]
  LPWSTR lpClass; // [rsp+28h] [rbp-D8h]
  LPWSTR lpClassa; // [rsp+28h] [rbp-D8h]
  DWORD cchName[2]; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v29; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey[3]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v31[40]; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Name[264]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  hKey[1] = HKEY_DYN_DATA|0x7FFFFFF8LL;
  hKey[2] = a1;
  std::vector<enum tagMSIINSTALLCONTEXT>::vector<enum tagMSIINSTALLCONTEXT>(a1);
  cchName[1] = 1;
  hKey[0] = 0;
  v4 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Appx\\AppxAllUserStore\\InboxApplications",
         0,
         8u,
         hKey);
  if ( v4 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x47,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeappfinder.cpp",
      (const char *)v4,
      phkResult);
  v5 = 0;
  v6 = 0;
  while ( !v6 )
  {
    memset_0(Name, 0, 0x208u);
    cchName[0] = 260;
    v7 = RegEnumKeyExW(hKey[0], v5, Name, cchName, 0, 0, 0, 0);
    v6 = v7;
    if ( v7 == 259 )
      break;
    if ( v7 > 0 )
      v10 = (unsigned __int16)v7 | 0x80070000;
    else
      v10 = (unsigned int)v7;
    if ( (v10 & 0x80000000) != 0LL )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x5C,
        (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeappfinder.cpp",
        (const char *)v10,
        phkResulta);
    ++v5;
    v11 = o((wchar_t)Name, v8, v9, v10, phkResulta, *(long double *)&lpClass);
    std::wstring::wstring(v31, v11);
    std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(a1, v31);
    std::wstring::~wstring(v31);
  }
  if ( *(_BYTE *)(a2 + 218) )
  {
    v29 = 0;
    v12 = RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Appx\\AppxAllUserStore\\Applications",
            0,
            8u,
            &v29);
    if ( v12 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x6B,
        (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeappfinder.cpp",
        (const char *)v12,
        phkResultb);
    v13 = 0;
    v14 = 0;
    while ( !v14 )
    {
      memset_0(Name, 0, 0x208u);
      cchName[0] = 260;
      v15 = RegEnumKeyExW(v29, v13, Name, cchName, 0, 0, 0, 0);
      v14 = v15;
      if ( v15 == 259 )
        break;
      if ( v15 > 0 )
        v16 = (unsigned __int16)v15 | 0x80070000;
      else
        v16 = (unsigned int)v15;
      if ( (v16 & 0x80000000) != 0LL )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x83,
          (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeappfinder.cpp",
          (const char *)v16,
          phkResultc);
      ++v13;
      if ( !(unsigned int)_o__wcsnicmp(Name, L"Microsoft.", 10) )
      {
        v20 = o((wchar_t)Name, v17, v18, v19, phkResultc, *(long double *)&lpClassa);
        std::wstring::wstring(v31, v20);
        std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(a1, v31);
        std::wstring::~wstring(v31);
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v29);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
  return a1;
}

```

## disassembly

```asm
0x1800490dc  push    rbp
0x1800490de  push    rbx
0x1800490df  push    rsi
0x1800490e0  push    rdi
0x1800490e1  push    r14
0x1800490e3  push    r15
0x1800490e5  lea     rbp, [rsp-1B8h]
0x1800490ed  sub     rsp, 2B8h
0x1800490f4  mov     [rsp+2E0h+var_288], 0FFFFFFFFFFFFFFFEh
0x1800490fd  mov     rax, cs:__security_cookie
0x180049104  xor     rax, rsp
0x180049107  mov     [rbp+1E0h+var_40], rax
0x18004910e  mov     r14, rdx
0x180049111  mov     rsi, rcx
0x180049114  mov     [rsp+2E0h+var_280], rcx
0x180049119  xor     r15d, r15d
0x18004911c  mov     [rsp+2E0h+var_29C], r15d
0x180049121  call    ??0?$vector@W4tagMSIINSTALLCONTEXT@@V?$allocator@W4tagMSIINSTALLCONTEXT@@@std@@@std@@QEAA@XZ; std::vector<tagMSIINSTALLCONTEXT>::vector<tagMSIINSTALLCONTEXT>(void)
0x180049126  mov     [rsp+2E0h+var_29C], 1
0x18004912e  mov     [rsp+2E0h+hKey], r15
0x180049133  lea     rax, [rsp+2E0h+hKey]
0x180049138  mov     [rsp+2E0h+phkResult], rax; unsigned int
0x18004913d  lea     r9d, [r15+8]; samDesired
0x180049141  xor     r8d, r8d; ulOptions
0x180049144  lea     rdx, aSoftwareMicros_9; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18004914b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180049152  call    cs:__imp_RegOpenKeyExW
0x180049158  mov     rcx, [rbp+1E8h]; this
0x18004915f  test    eax, eax
0x180049161  jz      short loc_180049177
0x180049163  mov     r9d, eax; char *
0x180049166  lea     r8, aOnecoreInterna_3; "onecore\\internal\\base\\inc\\appcompat"...
0x18004916d  lea     edx, [r15+47h]; void *
0x180049171  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180049177  mov     edi, r15d
0x18004917a  mov     ebx, r15d
0x18004917d  test    ebx, ebx
0x18004917f  jnz     loc_18004923A
0x180049185  xor     edx, edx; Val
0x180049187  mov     r8d, 208h; Size
0x18004918d  lea     rcx, [rbp+1E0h+Name]; void *
0x180049191  call    memset_0
0x180049196  mov     [rsp+2E0h+cchName], 104h
0x18004919e  mov     [rsp+2E0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800491a3  mov     [rsp+2E0h+lpcchClass], r15; lpcchClass
0x1800491a8  mov     [rsp+2E0h+lpClass], r15; lpClass
0x1800491ad  mov     [rsp+2E0h+phkResult], r15; int
0x1800491b2  lea     r9, [rsp+2E0h+cchName]; lpcchName
0x1800491b7  lea     r8, [rbp+1E0h+Name]; lpName
0x1800491bb  mov     edx, edi; dwIndex
0x1800491bd  mov     rcx, [rsp+2E0h+hKey]; hKey
0x1800491c2  call    cs:__imp_RegEnumKeyExW
0x1800491c8  mov     ebx, eax
0x1800491ca  cmp     eax, 103h
0x1800491cf  jz      short loc_18004923A
0x1800491d1  test    eax, eax
0x1800491d3  jg      short loc_1800491DA
0x1800491d5  mov     r9d, eax
0x1800491d8  jmp     short loc_1800491E5
0x1800491da  movzx   r9d, ax
0x1800491de  or      r9d, 80070000h; char *
0x1800491e5  mov     rcx, [rbp+1E8h]; this
0x1800491ec  test    r9d, r9d
0x1800491ef  js      short loc_180049228
0x1800491f1  inc     edi
0x1800491f3  lea     rcx, [rbp+1E0h+Name]
0x1800491f7  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x1800491fd  mov     rdx, rax
0x180049200  lea     rcx, [rsp+2E0h+var_278]
0x180049205  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004920a  nop
0x18004920b  lea     rdx, [rsp+2E0h+var_278]
0x180049210  mov     rcx, rsi
0x180049213  call    ??$_Emplace_one_at_back@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(std::wstring &&)
0x180049218  nop
0x180049219  lea     rcx, [rsp+2E0h+var_278]
0x18004921e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180049223  jmp     loc_18004917D
0x180049228  lea     r8, aOnecoreInterna_3; "onecore\\internal\\base\\inc\\appcompat"...
0x18004922f  mov     edx, 5Ch ; '\'; void *
0x180049234  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004923a  cmp     [r14+0DAh], r15b
0x180049241  jz      loc_180049384
0x180049247  mov     [rsp+2E0h+var_298], r15
0x18004924c  lea     rax, [rsp+2E0h+var_298]
0x180049251  mov     [rsp+2E0h+phkResult], rax; unsigned int
0x180049256  mov     r9d, 8; samDesired
0x18004925c  xor     r8d, r8d; ulOptions
0x18004925f  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180049266  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004926d  call    cs:__imp_RegOpenKeyExW
0x180049273  mov     rcx, [rbp+1E8h]; this
0x18004927a  test    eax, eax
0x18004927c  jz      short loc_180049293
0x18004927e  mov     r9d, eax; char *
0x180049281  lea     r8, aOnecoreInterna_3; "onecore\\internal\\base\\inc\\appcompat"...
0x180049288  mov     edx, 6Bh ; 'k'; void *
0x18004928d  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180049293  mov     edi, r15d
0x180049296  mov     ebx, r15d
0x180049299  test    ebx, ebx
0x18004929b  jnz     loc_180049379
0x1800492a1  xor     edx, edx; Val
0x1800492a3  mov     r8d, 208h; Size
0x1800492a9  lea     rcx, [rbp+1E0h+Name]; void *
0x1800492ad  call    memset_0
0x1800492b2  mov     [rsp+2E0h+cchName], 104h
0x1800492ba  mov     [rsp+2E0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800492bf  mov     [rsp+2E0h+lpcchClass], r15; lpcchClass
0x1800492c4  mov     [rsp+2E0h+lpClass], r15; lpClass
0x1800492c9  mov     [rsp+2E0h+phkResult], r15; int
0x1800492ce  lea     r9, [rsp+2E0h+cchName]; lpcchName
0x1800492d3  lea     r8, [rbp+1E0h+Name]; lpName
0x1800492d7  mov     edx, edi; dwIndex
0x1800492d9  mov     rcx, [rsp+2E0h+var_298]; hKey
0x1800492de  call    cs:__imp_RegEnumKeyExW
0x1800492e4  mov     ebx, eax
0x1800492e6  cmp     eax, 103h
0x1800492eb  jz      loc_180049379
0x1800492f1  test    eax, eax
0x1800492f3  jg      short loc_1800492FA
0x1800492f5  mov     r9d, eax
0x1800492f8  jmp     short loc_180049305
0x1800492fa  movzx   r9d, ax
0x1800492fe  or      r9d, 80070000h; char *
0x180049305  mov     rcx, [rbp+1E8h]; this
0x18004930c  test    r9d, r9d
0x18004930f  js      short loc_180049367
0x180049311  inc     edi
0x180049313  mov     r8d, 0Ah
0x180049319  lea     rdx, aMicrosoft_1; "Microsoft."
0x180049320  lea     rcx, [rbp+1E0h+Name]
0x180049324  call    cs:__imp__o__wcsnicmp
0x18004932a  test    eax, eax
0x18004932c  jnz     loc_180049299
0x180049332  lea     rcx, [rbp+1E0h+Name]
0x180049336  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x18004933c  mov     rdx, rax
0x18004933f  lea     rcx, [rsp+2E0h+var_278]
0x180049344  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180049349  nop
0x18004934a  lea     rdx, [rsp+2E0h+var_278]
0x18004934f  mov     rcx, rsi
0x180049352  call    ??$_Emplace_one_at_back@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(std::wstring &&)
0x180049357  nop
0x180049358  lea     rcx, [rsp+2E0h+var_278]
0x18004935d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180049362  jmp     loc_180049299
0x180049367  lea     r8, aOnecoreInterna_3; "onecore\\internal\\base\\inc\\appcompat"...
0x18004936e  mov     edx, 83h; void *
0x180049373  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180049379  lea     rcx, [rsp+2E0h+var_298]
0x18004937e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180049383  nop
0x180049384  lea     rcx, [rsp+2E0h+hKey]
0x180049389  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004938e  mov     rax, rsi
0x180049391  mov     rcx, [rbp+1E0h+var_40]
0x180049398  xor     rcx, rsp; StackCookie
0x18004939b  call    __security_check_cookie
0x1800493a0  add     rsp, 2B8h
0x1800493a7  pop     r15
0x1800493a9  pop     r14
0x1800493ab  pop     rdi
0x1800493ac  pop     rsi
0x1800493ad  pop     rbx
0x1800493ae  pop     rbp
0x1800493af  retn
```
