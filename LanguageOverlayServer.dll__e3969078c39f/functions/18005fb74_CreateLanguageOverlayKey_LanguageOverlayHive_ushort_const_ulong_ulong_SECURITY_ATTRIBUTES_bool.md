# CreateLanguageOverlayKey(LanguageOverlayHive,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,bool *)

- ea: `0x18005fb74`
- end: `0x18005fcb8`
- name: `?CreateLanguageOverlayKey@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@W4LanguageOverlayHive@@PEBGKKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `324`
- prototype: `__int64(void)`
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800380a0`
- `0x180038258`
- `0x180059ce8`
- `0x180059d7c`
- `0x18005e9b0`

## callees

- `0x180003a00`
- `0x180011334`
- `0x180014ed0`
- `0x18005fb74`
- `0x18005feb0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005fc3a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005fc3a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005fc6b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005fc6b`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18005fbc6`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18005fbc6`

## string_xrefs

- `0x18005fc91`: `onecore\base\languageoverlay\common\platformutils.cpp`
- `0x18005fca6`: `onecore\base\languageoverlay\common\platformutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HKEY __fastcall CreateLanguageOverlayKey(HKEY a1, unsigned int a2, __int64 a3)
{
  HKEY v6; // rdi
  unsigned int v7; // eax
  __int64 LanguageOverlayAbsoluteKeyPath; // rax
  unsigned int v9; // edi
  DWORD dwOptions; // [rsp+20h] [rbp-51h]
  DWORD dwOptionsa; // [rsp+20h] [rbp-51h]
  HKEY phkResult; // [rsp+50h] [rbp-21h] BYREF
  HKEY v14; // [rsp+58h] [rbp-19h] BYREF
  DWORD dwDisposition; // [rsp+60h] [rbp-11h] BYREF
  char *v16[4]; // [rsp+68h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+47h]

  v14 = a1;
  v6 = HKEY_LOCAL_MACHINE;
  phkResult = 0;
  if ( a2 == 1 )
  {
    phkResult = 0;
    v7 = RegOpenCurrentUser(0xF003Fu, &phkResult);
    if ( v7 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x59,
        (unsigned int)"onecore\\base\\languageoverlay\\common\\platformutils.cpp",
        (const char *)v7,
        dwOptions);
    v6 = phkResult;
  }
  dwDisposition = 0;
  v14 = 0;
  LanguageOverlayAbsoluteKeyPath = GetLanguageOverlayAbsoluteKeyPath(v16, a2, a3);
  if ( *(_QWORD *)(LanguageOverlayAbsoluteKeyPath + 24) > 7u )
    LanguageOverlayAbsoluteKeyPath = *(_QWORD *)LanguageOverlayAbsoluteKeyPath;
  v9 = RegCreateKeyExW(v6, (LPCWSTR)LanguageOverlayAbsoluteKeyPath, 0, 0, 0, 0xF003Fu, 0, &v14, &dwDisposition);
  std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v16);
  if ( v9 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x69,
      (unsigned int)"onecore\\base\\languageoverlay\\common\\platformutils.cpp",
      (const char *)v9,
      dwOptionsa);
  *(_QWORD *)a1 = v14;
  v14 = 0;
  if ( phkResult )
    RegCloseKey(phkResult);
  return a1;
}

```

## disassembly

```asm
0x18005fb74  push    rbp
0x18005fb76  push    rbx
0x18005fb77  push    rsi
0x18005fb78  push    rdi
0x18005fb79  push    r14
0x18005fb7b  lea     rbp, [rsp-1Fh]
0x18005fb80  sub     rsp, 90h
0x18005fb87  mov     rax, cs:__security_cookie
0x18005fb8e  xor     rax, rsp
0x18005fb91  mov     [rbp+3Fh+var_28], rax
0x18005fb95  mov     r14, r8
0x18005fb98  mov     esi, edx
0x18005fb9a  mov     rbx, rcx
0x18005fb9d  mov     [rbp+3Fh+var_58], rcx
0x18005fba1  mov     rdi, 0FFFFFFFF80000002h
0x18005fba8  mov     [rbp+3Fh+phkResult], 0
0x18005fbb0  cmp     edx, 1
0x18005fbb3  jnz     short loc_18005FBDC
0x18005fbb5  mov     [rbp+3Fh+phkResult], 0
0x18005fbbd  lea     rdx, [rbp+3Fh+phkResult]; phkResult
0x18005fbc1  mov     ecx, 0F003Fh; samDesired
0x18005fbc6  call    cs:__imp_RegOpenCurrentUser
0x18005fbcc  mov     rcx, [rbp+47h]; this
0x18005fbd0  test    eax, eax
0x18005fbd2  jnz     loc_18005FCA3
0x18005fbd8  mov     rdi, [rbp+3Fh+phkResult]
0x18005fbdc  mov     [rbp+3Fh+dwDisposition], 0
0x18005fbe3  mov     [rbp+3Fh+var_58], 0
0x18005fbeb  mov     r8, r14
0x18005fbee  mov     edx, esi
0x18005fbf0  lea     rcx, [rbp+3Fh+var_48]
0x18005fbf4  call    ?GetLanguageOverlayAbsoluteKeyPath@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4LanguageOverlayHive@@PEBG@Z; GetLanguageOverlayAbsoluteKeyPath(LanguageOverlayHive,ushort const *)
0x18005fbf9  cmp     qword ptr [rax+18h], 7
0x18005fbfe  jbe     short loc_18005FC03
0x18005fc00  mov     rax, [rax]
0x18005fc03  lea     rcx, [rbp+3Fh+dwDisposition]
0x18005fc07  mov     [rsp+0B0h+lpdwDisposition], rcx; lpdwDisposition
0x18005fc0c  lea     rcx, [rbp+3Fh+var_58]
0x18005fc10  mov     [rsp+0B0h+var_78], rcx; phkResult
0x18005fc15  mov     [rsp+0B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18005fc1e  mov     [rsp+0B0h+samDesired], 0F003Fh; samDesired
0x18005fc26  mov     [rsp+0B0h+dwOptions], 0; unsigned int
0x18005fc2e  xor     r9d, r9d; lpClass
0x18005fc31  xor     r8d, r8d; Reserved
0x18005fc34  mov     rdx, rax; lpSubKey
0x18005fc37  mov     rcx, rdi; hKey
0x18005fc3a  call    cs:__imp_RegCreateKeyExW
0x18005fc40  mov     edi, eax
0x18005fc42  lea     rcx, [rbp+3Fh+var_48]; void *
0x18005fc46  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x18005fc4b  mov     rcx, [rbp+47h]; this
0x18005fc4f  test    edi, edi
0x18005fc51  jnz     short loc_18005FC8E
0x18005fc53  mov     rcx, [rbp+3Fh+var_58]
0x18005fc57  mov     [rbx], rcx
0x18005fc5a  mov     [rbp+3Fh+var_58], 0
0x18005fc62  mov     rcx, [rbp+3Fh+phkResult]; hKey
0x18005fc66  test    rcx, rcx
0x18005fc69  jz      short loc_18005FC71
0x18005fc6b  call    cs:__imp_RegCloseKey
0x18005fc71  mov     rax, rbx
0x18005fc74  mov     rcx, [rbp+3Fh+var_28]
0x18005fc78  xor     rcx, rsp; StackCookie
0x18005fc7b  call    __security_check_cookie
0x18005fc80  add     rsp, 90h
0x18005fc87  pop     r14
0x18005fc89  pop     rdi
0x18005fc8a  pop     rsi
0x18005fc8b  pop     rbx
0x18005fc8c  pop     rbp
0x18005fc8d  retn
0x18005fc8e  mov     r9d, edi; char *
0x18005fc91  lea     r8, aOnecoreBaseLan_2; "onecore\\base\\languageoverlay\\common"...
0x18005fc98  mov     edx, 69h ; 'i'; void *
0x18005fc9d  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18005fca3  mov     r9d, eax; char *
0x18005fca6  lea     r8, aOnecoreBaseLan_2; "onecore\\base\\languageoverlay\\common"...
0x18005fcad  mov     edx, 59h ; 'Y'; void *
0x18005fcb2  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
