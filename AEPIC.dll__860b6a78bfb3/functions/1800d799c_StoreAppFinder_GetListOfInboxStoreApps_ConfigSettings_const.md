# StoreAppFinder::GetListOfInboxStoreApps(ConfigSettings const &)

- ea: `0x1800d799c`
- end: `0x1800d7c6e`
- name: `?GetListOfInboxStoreApps@StoreAppFinder@@SA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBVConfigSettings@@@Z`
- size: `722`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800d7e1c`
- `0x1800de63c`

## callees

- `0x180005890`
- `0x180006938`
- `0x18000faf0`
- `0x18001c5f0`
- `0x1800c31cc`
- `0x1800c97f0`
- `0x1800c993c`
- `0x1800cfc40`
- `0x1800d799c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x1800d7ab4`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x1800d7bf3`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x1800d7ab4`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x1800d7bf3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800d7be1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800d7be1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d7a0f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d7b2a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d7a0f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d7b2a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800d7a7f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800d7b9b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800d7a7f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800d7b9b`

## string_xrefs

- `0x1800d7a23`: `onecore\base\appcompat\inventory\software\inv\lib\storeappfinder.cpp`
- `0x1800d7ae5`: `onecore\base\appcompat\inventory\software\inv\lib\storeappfinder.cpp`
- `0x1800d7b3e`: `onecore\base\appcompat\inventory\software\inv\lib\storeappfinder.cpp`
- `0x1800d7c24`: `onecore\base\appcompat\inventory\software\inv\lib\storeappfinder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
HKEY __fastcall StoreAppFinder::GetListOfInboxStoreApps(HKEY a1, __int64 a2)
{
  unsigned int v4; // eax
  DWORD v5; // esi
  LSTATUS v6; // ebx
  LSTATUS v7; // eax
  char v8; // dl
  __int16 v9; // r8
  unsigned __int64 v10; // r9
  __int64 v11; // rax
  unsigned int v12; // eax
  DWORD v13; // esi
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
  HKEY hKey[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v31[32]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Name[264]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  hKey[1] = a1;
  *(_QWORD *)a1 = 0;
  *((_QWORD *)a1 + 1) = 0;
  *((_QWORD *)a1 + 2) = 0;
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
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeappfinder.cpp",
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
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeappfinder.cpp",
        (const char *)v10,
        phkResulta);
    ++v5;
    v11 = o((wchar_t)Name, v8, v9, v10, phkResulta, *(long double *)&lpClass);
    std::wstring::wstring(v31, v11);
    std::vector<std::wstring>::push_back(a1, v31);
    std::wstring::_Tidy_deallocate(v31);
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
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeappfinder.cpp",
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
          (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeappfinder.cpp",
          (const char *)v16,
          phkResultc);
      ++v13;
      if ( !(unsigned int)_o__wcsnicmp(Name, L"Microsoft.", 10) )
      {
        v20 = o((wchar_t)Name, v17, v18, v19, phkResultc, *(long double *)&lpClassa);
        std::wstring::wstring(v31, v20);
        std::vector<std::wstring>::push_back(a1, v31);
        std::wstring::_Tidy_deallocate(v31);
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
0x1800d799c  push    rbp
0x1800d799e  push    rbx
0x1800d799f  push    rsi
0x1800d79a0  push    rdi
0x1800d79a1  push    r14
0x1800d79a3  push    r15
0x1800d79a5  lea     rbp, [rsp-1A8h]
0x1800d79ad  sub     rsp, 2A8h
0x1800d79b4  mov     rax, cs:__security_cookie
0x1800d79bb  xor     rax, rsp
0x1800d79be  mov     [rbp+1D0h+var_40], rax
0x1800d79c5  mov     r14, rdx
0x1800d79c8  mov     rdi, rcx
0x1800d79cb  mov     [rsp+2D0h+var_278], rcx
0x1800d79d0  xor     r15d, r15d
0x1800d79d3  mov     [rsp+2D0h+var_28C], r15d
0x1800d79d8  mov     [rcx], r15
0x1800d79db  mov     [rcx+8], r15
0x1800d79df  mov     [rcx+10h], r15
0x1800d79e3  mov     [rsp+2D0h+var_28C], 1
0x1800d79eb  mov     [rsp+2D0h+hKey], r15
0x1800d79f0  lea     rax, [rsp+2D0h+hKey]
0x1800d79f5  mov     [rsp+2D0h+phkResult], rax; unsigned int
0x1800d79fa  lea     r9d, [r15+8]; samDesired
0x1800d79fe  xor     r8d, r8d; ulOptions
0x1800d7a01  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800d7a08  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800d7a0f  call    cs:__imp_RegOpenKeyExW
0x1800d7a15  mov     rcx, [rbp+1D8h]; this
0x1800d7a1c  test    eax, eax
0x1800d7a1e  jz      short loc_1800D7A34
0x1800d7a20  mov     r9d, eax; char *
0x1800d7a23  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\inventory\\so"...
0x1800d7a2a  lea     edx, [r15+47h]; void *
0x1800d7a2e  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800d7a34  mov     esi, r15d
0x1800d7a37  mov     ebx, r15d
0x1800d7a3a  test    ebx, ebx
0x1800d7a3c  jnz     loc_1800D7AF7
0x1800d7a42  xor     edx, edx; Val
0x1800d7a44  mov     r8d, 208h; Size
0x1800d7a4a  lea     rcx, [rbp+1D0h+Name]; void *
0x1800d7a4e  call    memset_0
0x1800d7a53  mov     [rsp+2D0h+cchName], 104h
0x1800d7a5b  mov     [rsp+2D0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800d7a60  mov     [rsp+2D0h+lpcchClass], r15; lpcchClass
0x1800d7a65  mov     [rsp+2D0h+lpClass], r15; lpClass
0x1800d7a6a  mov     [rsp+2D0h+phkResult], r15; int
0x1800d7a6f  lea     r9, [rsp+2D0h+cchName]; lpcchName
0x1800d7a74  lea     r8, [rbp+1D0h+Name]; lpName
0x1800d7a78  mov     edx, esi; dwIndex
0x1800d7a7a  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800d7a7f  call    cs:__imp_RegEnumKeyExW
0x1800d7a85  mov     ebx, eax
0x1800d7a87  cmp     eax, 103h
0x1800d7a8c  jz      short loc_1800D7AF7
0x1800d7a8e  test    eax, eax
0x1800d7a90  jg      short loc_1800D7A97
0x1800d7a92  mov     r9d, eax
0x1800d7a95  jmp     short loc_1800D7AA2
0x1800d7a97  movzx   r9d, ax
0x1800d7a9b  or      r9d, 80070000h; char *
0x1800d7aa2  mov     rcx, [rbp+1D8h]; this
0x1800d7aa9  test    r9d, r9d
0x1800d7aac  js      short loc_1800D7AE5
0x1800d7aae  inc     esi
0x1800d7ab0  lea     rcx, [rbp+1D0h+Name]
0x1800d7ab4  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x1800d7aba  mov     rdx, rax
0x1800d7abd  lea     rcx, [rsp+2D0h+var_270]
0x1800d7ac2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800d7ac7  nop
0x1800d7ac8  lea     rdx, [rsp+2D0h+var_270]
0x1800d7acd  mov     rcx, rdi
0x1800d7ad0  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x1800d7ad5  nop
0x1800d7ad6  lea     rcx, [rsp+2D0h+var_270]
0x1800d7adb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800d7ae0  jmp     loc_1800D7A3A
0x1800d7ae5  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\inventory\\so"...
0x1800d7aec  mov     edx, 5Ch ; '\'; void *
0x1800d7af1  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800d7af7  cmp     [r14+0DAh], r15b
0x1800d7afe  jz      loc_1800D7C41
0x1800d7b04  mov     [rsp+2D0h+var_288], r15
0x1800d7b09  lea     rax, [rsp+2D0h+var_288]
0x1800d7b0e  mov     [rsp+2D0h+phkResult], rax; unsigned int
0x1800d7b13  mov     r9d, 8; samDesired
0x1800d7b19  xor     r8d, r8d; ulOptions
0x1800d7b1c  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800d7b23  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800d7b2a  call    cs:__imp_RegOpenKeyExW
0x1800d7b30  mov     rcx, [rbp+1D8h]; this
0x1800d7b37  test    eax, eax
0x1800d7b39  jz      short loc_1800D7B50
0x1800d7b3b  mov     r9d, eax; char *
0x1800d7b3e  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\inventory\\so"...
0x1800d7b45  mov     edx, 6Bh ; 'k'; void *
0x1800d7b4a  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800d7b50  mov     esi, r15d
0x1800d7b53  mov     ebx, r15d
0x1800d7b56  test    ebx, ebx
0x1800d7b58  jnz     loc_1800D7C36
0x1800d7b5e  xor     edx, edx; Val
0x1800d7b60  mov     r8d, 208h; Size
0x1800d7b66  lea     rcx, [rbp+1D0h+Name]; void *
0x1800d7b6a  call    memset_0
0x1800d7b6f  mov     [rsp+2D0h+cchName], 104h
0x1800d7b77  mov     [rsp+2D0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800d7b7c  mov     [rsp+2D0h+lpcchClass], r15; lpcchClass
0x1800d7b81  mov     [rsp+2D0h+lpClass], r15; lpClass
0x1800d7b86  mov     [rsp+2D0h+phkResult], r15; int
0x1800d7b8b  lea     r9, [rsp+2D0h+cchName]; lpcchName
0x1800d7b90  lea     r8, [rbp+1D0h+Name]; lpName
0x1800d7b94  mov     edx, esi; dwIndex
0x1800d7b96  mov     rcx, [rsp+2D0h+var_288]; hKey
0x1800d7b9b  call    cs:__imp_RegEnumKeyExW
0x1800d7ba1  mov     ebx, eax
0x1800d7ba3  cmp     eax, 103h
0x1800d7ba8  jz      loc_1800D7C36
0x1800d7bae  test    eax, eax
0x1800d7bb0  jg      short loc_1800D7BB7
0x1800d7bb2  mov     r9d, eax
0x1800d7bb5  jmp     short loc_1800D7BC2
0x1800d7bb7  movzx   r9d, ax
0x1800d7bbb  or      r9d, 80070000h; char *
0x1800d7bc2  mov     rcx, [rbp+1D8h]; this
0x1800d7bc9  test    r9d, r9d
0x1800d7bcc  js      short loc_1800D7C24
0x1800d7bce  inc     esi
0x1800d7bd0  mov     r8d, 0Ah
0x1800d7bd6  lea     rdx, aMicrosoft_0; "Microsoft."
0x1800d7bdd  lea     rcx, [rbp+1D0h+Name]
0x1800d7be1  call    cs:__imp__o__wcsnicmp
0x1800d7be7  test    eax, eax
0x1800d7be9  jnz     loc_1800D7B56
0x1800d7bef  lea     rcx, [rbp+1D0h+Name]
0x1800d7bf3  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x1800d7bf9  mov     rdx, rax
0x1800d7bfc  lea     rcx, [rsp+2D0h+var_270]
0x1800d7c01  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800d7c06  nop
0x1800d7c07  lea     rdx, [rsp+2D0h+var_270]
0x1800d7c0c  mov     rcx, rdi
0x1800d7c0f  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x1800d7c14  nop
0x1800d7c15  lea     rcx, [rsp+2D0h+var_270]
0x1800d7c1a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800d7c1f  jmp     loc_1800D7B56
0x1800d7c24  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\inventory\\so"...
0x1800d7c2b  mov     edx, 83h; void *
0x1800d7c30  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800d7c36  lea     rcx, [rsp+2D0h+var_288]
0x1800d7c3b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d7c40  nop
0x1800d7c41  lea     rcx, [rsp+2D0h+hKey]
0x1800d7c46  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d7c4b  mov     rax, rdi
0x1800d7c4e  mov     rcx, [rbp+1D0h+var_40]
0x1800d7c55  xor     rcx, rsp; StackCookie
0x1800d7c58  call    __security_check_cookie
0x1800d7c5d  add     rsp, 2A8h
0x1800d7c64  pop     r15
0x1800d7c66  pop     r14
0x1800d7c68  pop     rdi
0x1800d7c69  pop     rsi
0x1800d7c6a  pop     rbx
0x1800d7c6b  pop     rbp
0x1800d7c6c  retn
```
