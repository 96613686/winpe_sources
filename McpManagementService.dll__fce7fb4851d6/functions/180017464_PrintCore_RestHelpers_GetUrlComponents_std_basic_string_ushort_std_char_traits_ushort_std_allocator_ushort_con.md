# PrintCore::RestHelpers::GetUrlComponents(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180017464`
- end: `0x18001760b`
- name: `?GetUrlComponents@RestHelpers@PrintCore@@SA?AUUrlComponents@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `423`
- prototype: `PrintCore::UrlComponents *__fastcall(PrintCore::UrlComponents *this, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18001d7dc`

## callees

- `0x180003a60`
- `0x1800045d8`
- `0x18000e164`
- `0x18000e208`
- `0x180011d98`
- `0x180011e24`
- `0x1800123ec`
- `0x180012bc0`
- `0x18001309c`
- `0x18001b9ec`

## import_xrefs

- `WINHTTP!WinHttpCrackUrl` at `0x1800174f1`
- `WINHTTP!WinHttpCrackUrl` at `0x1800174f1`

## string_xrefs

- `0x180017505`: `Unable to crack the url into its component parts: %ws`

## pseudocode

```c
PrintCore::UrlComponents *__fastcall PrintCore::RestHelpers::GetUrlComponents(
        PrintCore::UrlComponents *this,
        __int64 a2)
{
  __int64 v3; // rax
  const WCHAR *v4; // rbx
  BOOL v5; // eax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  int v11; // [rsp+30h] [rbp-D0h]
  $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+40h] [rbp-C0h] BYREF
  PrintCore::UrlComponents *v13; // [rsp+B0h] [rbp-50h]
  _BYTE v14[32]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v15[32]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v16[16]; // [rsp+108h] [rbp+8h] BYREF
  DWORD dwUrlLength; // [rsp+118h] [rbp+18h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  v13 = this;
  v11 = 0;
  v3 = std::wstring::wstring(v14, a2);
  PrintCore::RestHelpers::CanonicalizeUrl(v16, v3);
  memset_0(&UrlComponents, 0, sizeof(UrlComponents));
  UrlComponents.dwStructSize = 104;
  UrlComponents.dwSchemeLength = -1;
  UrlComponents.dwHostNameLength = -1;
  UrlComponents.dwUrlPathLength = -1;
  UrlComponents.dwExtraInfoLength = -1;
  v4 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v16);
  v5 = WinHttpCrackUrl(v4, dwUrlLength, 0, &UrlComponents);
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x64,
    (unsigned int)"onecoreuap\\internal\\printscan\\inc\\RestHelpers.h",
    (const char *)!v5,
    (bool)"Unable to crack the url into its component parts: %ws",
    (const char *)v4,
    v11);
  PrintCore::UrlComponents::UrlComponents(this);
  v6 = std::wstring::wstring(v15, UrlComponents.lpszScheme, UrlComponents.dwSchemeLength);
  std::wstring::operator=(this, v6);
  std::wstring::_Tidy_deallocate(v15);
  v7 = std::wstring::wstring(v15, UrlComponents.lpszHostName, UrlComponents.dwHostNameLength);
  std::wstring::operator=((char *)this + 32, v7);
  std::wstring::_Tidy_deallocate(v15);
  v8 = std::wstring::wstring(v15, UrlComponents.lpszUrlPath, UrlComponents.dwUrlPathLength);
  std::wstring::operator=((char *)this + 64, v8);
  std::wstring::_Tidy_deallocate(v15);
  v9 = std::wstring::wstring(v15, UrlComponents.lpszExtraInfo, UrlComponents.dwExtraInfoLength);
  std::wstring::operator=((char *)this + 96, v9);
  std::wstring::_Tidy_deallocate(v15);
  *((_WORD *)this + 64) = UrlComponents.nPort;
  std::wstring::_Tidy_deallocate(v16);
  return this;
}

```

## disassembly

```asm
0x180017464  mov     [rsp-8+arg_10], rbx
0x180017469  mov     [rsp-8+arg_18], rdi
0x18001746e  push    rbp
0x18001746f  lea     rbp, [rsp-30h]
0x180017474  sub     rsp, 130h
0x18001747b  mov     rax, cs:__security_cookie
0x180017482  xor     rax, rsp
0x180017485  mov     [rbp+30h+var_8], rax
0x180017489  mov     rdi, rcx
0x18001748c  mov     [rbp+30h+var_80], rcx
0x180017490  mov     [rsp+130h+var_100], 0
0x180017498  lea     rcx, [rbp+30h+var_68]
0x18001749c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800174a1  mov     rdx, rax
0x1800174a4  lea     rcx, [rbp+30h+var_28]
0x1800174a8  call    ?CanonicalizeUrl@RestHelpers@PrintCore@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V34@@Z; PrintCore::RestHelpers::CanonicalizeUrl(std::wstring)
0x1800174ad  nop
0x1800174ae  mov     ebx, 68h ; 'h'
0x1800174b3  mov     r8d, ebx; Size
0x1800174b6  xor     edx, edx; Val
0x1800174b8  lea     rcx, [rsp+130h+UrlComponents]; void *
0x1800174bd  call    memset_0
0x1800174c2  mov     [rsp+130h+UrlComponents.dwStructSize], ebx
0x1800174c6  or      eax, 0FFFFFFFFh
0x1800174c9  mov     [rsp+130h+UrlComponents.dwSchemeLength], eax
0x1800174cd  mov     [rsp+130h+UrlComponents.dwHostNameLength], eax
0x1800174d1  mov     [rbp+30h+UrlComponents.dwUrlPathLength], eax
0x1800174d4  mov     [rbp+30h+UrlComponents.dwExtraInfoLength], eax
0x1800174d7  lea     rcx, [rbp+30h+var_28]
0x1800174db  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800174e0  mov     rbx, rax
0x1800174e3  lea     r9, [rsp+130h+UrlComponents]; lpUrlComponents
0x1800174e8  xor     r8d, r8d; dwFlags
0x1800174eb  mov     edx, [rbp+30h+dwUrlLength]; dwUrlLength
0x1800174ee  mov     rcx, rax; pwszUrl
0x1800174f1  call    cs:__imp_WinHttpCrackUrl
0x1800174f7  test    eax, eax
0x1800174f9  setz    dl
0x1800174fc  mov     rcx, [rbp+38h]; this
0x180017500  mov     [rsp+130h+var_108], rbx; char *
0x180017505  lea     rax, aUnableToCrackT; "Unable to crack the url into its compon"...
0x18001750c  mov     qword ptr [rsp+130h+var_110], rax; bool
0x180017511  movzx   r9d, dl; char *
0x180017515  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\printscan\\inc\\R"...
0x18001751c  mov     edx, 64h ; 'd'; void *
0x180017521  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180017526  mov     rcx, rdi; this
0x180017529  call    ??0UrlComponents@PrintCore@@QEAA@XZ; PrintCore::UrlComponents::UrlComponents(void)
0x18001752e  mov     [rsp+130h+var_100], 1
0x180017536  mov     r8d, [rsp+130h+UrlComponents.dwSchemeLength]
0x18001753b  mov     rdx, [rsp+130h+UrlComponents.lpszScheme]
0x180017540  lea     rcx, [rbp+30h+var_48]
0x180017544  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG_K@Z; std::wstring::wstring(ushort const * const,unsigned __int64)
0x180017549  mov     rdx, rax
0x18001754c  mov     rcx, rdi
0x18001754f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180017554  lea     rcx, [rbp+30h+var_48]
0x180017558  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001755d  mov     r8d, [rsp+130h+UrlComponents.dwHostNameLength]
0x180017562  mov     rdx, [rsp+130h+UrlComponents.lpszHostName]
0x180017567  lea     rcx, [rbp+30h+var_48]
0x18001756b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG_K@Z; std::wstring::wstring(ushort const * const,unsigned __int64)
0x180017570  lea     rcx, [rdi+20h]
0x180017574  mov     rdx, rax
0x180017577  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001757c  lea     rcx, [rbp+30h+var_48]
0x180017580  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180017585  mov     r8d, [rbp+30h+UrlComponents.dwUrlPathLength]
0x180017589  mov     rdx, [rbp+30h+UrlComponents.lpszUrlPath]
0x18001758d  lea     rcx, [rbp+30h+var_48]
0x180017591  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG_K@Z; std::wstring::wstring(ushort const * const,unsigned __int64)
0x180017596  lea     rcx, [rdi+40h]
0x18001759a  mov     rdx, rax
0x18001759d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800175a2  lea     rcx, [rbp+30h+var_48]
0x1800175a6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800175ab  mov     r8d, [rbp+30h+UrlComponents.dwExtraInfoLength]
0x1800175af  mov     rdx, [rbp+30h+UrlComponents.lpszExtraInfo]
0x1800175b3  lea     rcx, [rbp+30h+var_48]
0x1800175b7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG_K@Z; std::wstring::wstring(ushort const * const,unsigned __int64)
0x1800175bc  lea     rcx, [rdi+60h]
0x1800175c0  mov     rdx, rax
0x1800175c3  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800175c8  lea     rcx, [rbp+30h+var_48]
0x1800175cc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800175d1  movzx   ecx, [rsp+130h+UrlComponents.nPort]
0x1800175d6  mov     [rdi+80h], cx
0x1800175dd  lea     rcx, [rbp+30h+var_28]
0x1800175e1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800175e6  mov     rax, rdi
0x1800175e9  mov     rcx, [rbp+30h+var_8]
0x1800175ed  xor     rcx, rsp; StackCookie
0x1800175f0  call    __security_check_cookie
0x1800175f5  lea     r11, [rsp+130h+var_s0]
0x1800175fd  mov     rbx, [r11+20h]
0x180017601  mov     rdi, [r11+28h]
0x180017605  mov     rsp, r11
0x180017608  pop     rbp
0x180017609  retn
```
