# CLanguageComponentsInstallerHandler::GetRegistryKeyPath(void)

- ea: `0x180018234`
- end: `0x180018348`
- name: `?GetRegistryKeyPath@CLanguageComponentsInstallerHandler@@AEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `276`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180014788`
- `0x18001844c`
- `0x18001b5b4`
- `0x18001baa0`

## callees

- `0x180003520`
- `0x1800041b4`
- `0x180005954`
- `0x18000a7fc`
- `0x180018234`
- `0x180021494`

## import_xrefs

- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800182ad`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800182ad`

## string_xrefs

- `0x180018313`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\languagecomponentsinstaller.cpp`
- `0x180018330`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\languagecomponentsinstaller.cpp`
- `0x18001826f`: `Microsoft\Windows\CurrentVersion\LanguageComponentsInstaller`
- `0x18001829f`: `Software\Microsoft\Windows\CurrentVersion\LanguageComponentsInstaller`
- `0x1800182a6`: `LanguageComponentsInstallerKeyName`

## pseudocode

```c
__int64 __fastcall CLanguageComponentsInstallerHandler::GetRegistryKeyPath(__int64 a1, __int64 a2)
{
  __int64 v2; // rdi
  unsigned int PersistedRegistryLocationW; // eax
  int v6; // [rsp+20h] [rbp-248h]
  wchar_t Buffer[264]; // [rsp+40h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  v2 = -1;
  if ( *(_QWORD *)(a1 + 280) )
  {
    if ( swprintf_s(Buffer, 0x104u, L"Microsoft\\Windows\\CurrentVersion\\LanguageComponentsInstaller") == -1 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1D6,
        (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\languagecomponentsinstaller.cpp",
        (const char *)0x8000FFFFLL,
        v6);
  }
  else
  {
    PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                   L"LanguageComponentsInstallerKeyName",
                                   L"Software\\Microsoft\\Windows\\CurrentVersion\\LanguageComponentsInstaller",
                                   Buffer,
                                   520);
    if ( PersistedRegistryLocationW )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x1DF,
        (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\languagecomponentsinstaller.cpp",
        (const char *)PersistedRegistryLocationW,
        0);
  }
  *(_OWORD *)a2 = 0;
  *(_QWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 24) = 0;
  do
    ++v2;
  while ( Buffer[v2] );
  std::wstring::_Construct<1,unsigned short const *>(a2);
  return a2;
}

```

## disassembly

```asm
0x180018234  mov     [rsp+arg_0], rbx
0x180018239  mov     [rsp+arg_10], rsi
0x18001823e  push    rdi
0x18001823f  sub     rsp, 260h
0x180018246  mov     rax, cs:__security_cookie
0x18001824d  xor     rax, rsp
0x180018250  mov     [rsp+268h+var_18], rax
0x180018258  xor     esi, esi
0x18001825a  mov     [rsp+268h+var_230], rdx
0x18001825f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180018263  mov     rbx, rdx
0x180018266  cmp     [rcx+118h], rsi
0x18001826d  jz      short loc_18001828F
0x18001826f  lea     r8, aMicrosoftWindo; "Microsoft\\Windows\\CurrentVersion\\Lan"...
0x180018276  mov     edx, 104h; BufferCount
0x18001827b  lea     rcx, [rsp+268h+Buffer]; Buffer
0x180018280  call    swprintf_s
0x180018285  cmp     eax, edi
0x180018287  jz      loc_180018328
0x18001828d  jmp     short loc_1800182B7
0x18001828f  mov     r9d, 208h
0x180018295  mov     qword ptr [rsp+268h+var_248], rsi; unsigned int
0x18001829a  lea     r8, [rsp+268h+Buffer]
0x18001829f  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800182a6  lea     rcx, aLanguagecompon_0; "LanguageComponentsInstallerKeyName"
0x1800182ad  call    cs:__imp_GetPersistedRegistryLocationW
0x1800182b3  test    eax, eax
0x1800182b5  jnz     short loc_18001830B
0x1800182b7  xorps   xmm0, xmm0
0x1800182ba  lea     rax, [rsp+268h+Buffer]
0x1800182bf  movups  xmmword ptr [rbx], xmm0
0x1800182c2  mov     [rbx+10h], rsi
0x1800182c6  mov     [rbx+18h], rsi
0x1800182ca  inc     rdi
0x1800182cd  cmp     [rax+rdi*2], si
0x1800182d1  jnz     short loc_1800182CA
0x1800182d3  mov     r8, rdi
0x1800182d6  lea     rdx, [rsp+268h+Buffer]
0x1800182db  mov     rcx, rbx
0x1800182de  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800182e3  mov     rax, rbx
0x1800182e6  mov     rcx, [rsp+268h+var_18]
0x1800182ee  xor     rcx, rsp; StackCookie
0x1800182f1  call    __security_check_cookie
0x1800182f6  lea     r11, [rsp+268h+var_8]
0x1800182fe  mov     rbx, [r11+10h]
0x180018302  mov     rsi, [r11+20h]
0x180018306  mov     rsp, r11
0x180018309  pop     rdi
0x18001830a  retn
0x18001830b  mov     rcx, [rsp+268h]; this
0x180018313  lea     r8, aOnecoreShellCp_1; "onecore\\shell\\cpls\\internationalsett"...
0x18001831a  mov     r9d, eax; char *
0x18001831d  mov     edx, 1DFh; void *
0x180018322  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180018328  mov     rcx, [rsp+268h]; this
0x180018330  lea     r8, aOnecoreShellCp_1; "onecore\\shell\\cpls\\internationalsett"...
0x180018337  mov     r9d, 8000FFFFh; char *
0x18001833d  mov     edx, 1D6h; void *
0x180018342  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
