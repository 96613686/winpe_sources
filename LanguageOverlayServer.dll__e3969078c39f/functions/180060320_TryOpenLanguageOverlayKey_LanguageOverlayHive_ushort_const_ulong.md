# TryOpenLanguageOverlayKey(LanguageOverlayHive,ushort const *,ulong)

- ea: `0x180060320`
- end: `0x180060410`
- name: `?TryOpenLanguageOverlayKey@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@W4LanguageOverlayHive@@PEBGK@Z`
- size: `240`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180035dbc`
- `0x180035f30`
- `0x1800371e4`
- `0x1800379d4`
- `0x18003867c`
- `0x180038cfc`

## callees

- `0x180003a00`
- `0x180011334`
- `0x180014ed0`
- `0x18005feb0`
- `0x180060320`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800603d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800603d2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180060385`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180060385`

## string_xrefs

- `0x1800603fe`: `onecore\base\languageoverlay\common\platformutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HKEY *__fastcall TryOpenLanguageOverlayKey(HKEY *a1, __int64 a2, const unsigned __int16 *a3, REGSAM a4)
{
  __int64 LanguageOverlayAbsoluteKeyPath; // rax
  unsigned int v7; // ebx
  unsigned int phkResult; // [rsp+20h] [rbp-58h]
  HKEY v10; // [rsp+30h] [rbp-48h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-40h]
  char *v12[4]; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  hKey = 0;
  v10 = 0;
  LanguageOverlayAbsoluteKeyPath = GetLanguageOverlayAbsoluteKeyPath((__int64)v12, 0, a3);
  if ( *(_QWORD *)(LanguageOverlayAbsoluteKeyPath + 24) > 7u )
    LanguageOverlayAbsoluteKeyPath = *(_QWORD *)LanguageOverlayAbsoluteKeyPath;
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)LanguageOverlayAbsoluteKeyPath, 0, a4, &v10);
  std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v12);
  if ( v7 && v7 != 2 && v7 != 3 && v7 != 1018 && v7 != 1168 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x47,
      (unsigned int)"onecore\\base\\languageoverlay\\common\\platformutils.cpp",
      (const char *)v7,
      phkResult);
  *a1 = v10;
  v10 = 0;
  if ( hKey )
    RegCloseKey(hKey);
  return a1;
}

```

## disassembly

```asm
0x180060320  mov     r11, rsp
0x180060323  mov     [r11+10h], rbx
0x180060327  push    rdi
0x180060328  sub     rsp, 70h
0x18006032c  mov     rax, cs:__security_cookie
0x180060333  xor     rax, rsp
0x180060336  mov     [rsp+78h+var_10], rax
0x18006033b  mov     ebx, r9d
0x18006033e  mov     rdi, rcx
0x180060341  mov     [rsp+78h+hKey], rcx
0x180060346  mov     qword ptr [r11-40h], 0
0x18006034e  mov     qword ptr [r11-48h], 0
0x180060356  xor     edx, edx
0x180060358  lea     rcx, [r11-30h]
0x18006035c  call    ?GetLanguageOverlayAbsoluteKeyPath@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4LanguageOverlayHive@@PEBG@Z; GetLanguageOverlayAbsoluteKeyPath(LanguageOverlayHive,ushort const *)
0x180060361  cmp     qword ptr [rax+18h], 7
0x180060366  jbe     short loc_18006036B
0x180060368  mov     rax, [rax]
0x18006036b  lea     rcx, [rsp+78h+var_48]
0x180060370  mov     qword ptr [rsp+78h+phkResult], rcx; unsigned int
0x180060375  mov     r9d, ebx; samDesired
0x180060378  xor     r8d, r8d; ulOptions
0x18006037b  mov     rdx, rax; lpSubKey
0x18006037e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180060385  call    cs:__imp_RegOpenKeyExW
0x18006038b  mov     ebx, eax
0x18006038d  lea     rcx, [rsp+78h+var_30]; void *
0x180060392  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180060397  test    ebx, ebx
0x180060399  jz      short loc_1800603B7
0x18006039b  mov     ecx, ebx
0x18006039d  sub     ecx, 2
0x1800603a0  jz      short loc_1800603B7
0x1800603a2  sub     ecx, 1
0x1800603a5  jz      short loc_1800603B7
0x1800603a7  sub     ecx, 3F7h
0x1800603ad  jz      short loc_1800603B7
0x1800603af  cmp     ecx, 96h
0x1800603b5  jnz     short loc_1800603F6
0x1800603b7  mov     rcx, [rsp+78h+var_48]
0x1800603bc  mov     [rdi], rcx
0x1800603bf  mov     [rsp+78h+var_48], 0
0x1800603c8  mov     rcx, [rsp+78h+hKey]; hKey
0x1800603cd  test    rcx, rcx
0x1800603d0  jz      short loc_1800603D8
0x1800603d2  call    cs:__imp_RegCloseKey
0x1800603d8  mov     rax, rdi
0x1800603db  mov     rcx, [rsp+78h+var_10]
0x1800603e0  xor     rcx, rsp; StackCookie
0x1800603e3  call    __security_check_cookie
0x1800603e8  mov     rbx, [rsp+78h+arg_8]
0x1800603f0  add     rsp, 70h
0x1800603f4  pop     rdi
0x1800603f5  retn
0x1800603f6  mov     rcx, [rsp+78h]; this
0x1800603fb  mov     r9d, ebx; char *
0x1800603fe  lea     r8, aOnecoreBaseLan_2; "onecore\\base\\languageoverlay\\common"...
0x180060405  mov     edx, 47h ; 'G'; void *
0x18006040a  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
