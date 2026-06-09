# GetUserPreferredMuiLanguages(void)

- ea: `0x180015a54`
- end: `0x180015b16`
- name: `?GetUserPreferredMuiLanguages@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ`
- size: `194`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800190bc`

## callees

- `0x18000c230`
- `0x18000e8cc`
- `0x180011300`
- `0x180015a54`
- `0x18001dcc0`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetUserPreferredUILanguages` at `0x180015a8a`
- `api-ms-win-core-localization-l1-2-0!GetUserPreferredUILanguages` at `0x180015ad1`
- `api-ms-win-core-localization-l1-2-0!GetUserPreferredUILanguages` at `0x180015a8a`
- `api-ms-win-core-localization-l1-2-0!GetUserPreferredUILanguages` at `0x180015ad1`

## string_xrefs

- `0x180015a94`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`
- `0x180015adb`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`

## pseudocode

```c
WCHAR *__fastcall GetUserPreferredMuiLanguages(WCHAR *a1)
{
  const char *v2; // r9
  const char *v3; // r9
  unsigned __int64 v4; // rdx
  ULONG pcchLanguagesBuffer; // [rsp+20h] [rbp-28h] BYREF
  ULONG pulNumLanguages; // [rsp+24h] [rbp-24h] BYREF
  PZZWSTR pwszLanguagesBuffer[4]; // [rsp+28h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  pwszLanguagesBuffer[0] = a1;
  pulNumLanguages = 0;
  pcchLanguagesBuffer = 0;
  if ( !GetUserPreferredUILanguages(8u, &pulNumLanguages, 0, &pcchLanguagesBuffer) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x2D8,
      (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
      v2);
  std::make_unique<unsigned short [0],0>(pwszLanguagesBuffer, pcchLanguagesBuffer);
  if ( !GetUserPreferredUILanguages(8u, &pulNumLanguages, pwszLanguagesBuffer[0], &pcchLanguagesBuffer) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x2DD,
      (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
      v3);
  WstringContainerFromMultiString<std::vector<std::wstring>>(a1, pwszLanguagesBuffer[0]);
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>((void **)pwszLanguagesBuffer, v4);
  return a1;
}

```

## disassembly

```asm
0x180015a54  mov     rax, rsp
0x180015a57  mov     [rax+10h], rbx
0x180015a5b  push    rdi
0x180015a5c  sub     rsp, 40h
0x180015a60  mov     rbx, rcx
0x180015a63  mov     [rsp+48h+pwszLanguagesBuffer], rcx
0x180015a68  mov     dword ptr [rax-24h], 0
0x180015a6f  mov     dword ptr [rax-28h], 0
0x180015a76  mov     rdi, [rsp+48h]
0x180015a7b  lea     r9, [rax-28h]; pcchLanguagesBuffer
0x180015a7f  xor     r8d, r8d; pwszLanguagesBuffer
0x180015a82  lea     rdx, [rax-24h]; pulNumLanguages
0x180015a86  lea     ecx, [r8+8]; dwFlags
0x180015a8a  call    cs:__imp_GetUserPreferredUILanguages
0x180015a90  test    eax, eax
0x180015a92  jnz     short loc_180015AA9
0x180015a94  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x180015a9b  mov     edx, 2D8h; void *
0x180015aa0  mov     rcx, rdi; this
0x180015aa3  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180015aa9  mov     edx, [rsp+48h+pcchLanguagesBuffer]
0x180015aad  lea     rcx, [rsp+48h+pwszLanguagesBuffer]
0x180015ab2  call    ??$make_unique@$$BY0A@G$0A@@std@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@0@_K@Z; std::make_unique<ushort [0],0>(unsigned __int64)
0x180015ab7  nop
0x180015ab8  mov     rdi, [rsp+48h]
0x180015abd  lea     r9, [rsp+48h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x180015ac2  mov     r8, [rsp+48h+pwszLanguagesBuffer]; pwszLanguagesBuffer
0x180015ac7  lea     rdx, [rsp+48h+pulNumLanguages]; pulNumLanguages
0x180015acc  mov     ecx, 8; dwFlags
0x180015ad1  call    cs:__imp_GetUserPreferredUILanguages
0x180015ad7  test    eax, eax
0x180015ad9  jnz     short loc_180015AF0
0x180015adb  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x180015ae2  mov     edx, 2DDh; void *
0x180015ae7  mov     rcx, rdi; this
0x180015aea  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180015af0  mov     rdx, [rsp+48h+pwszLanguagesBuffer]
0x180015af5  mov     rcx, rbx
0x180015af8  call    ??$WstringContainerFromMultiString@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEBG@Z; WstringContainerFromMultiString<std::vector<std::wstring>>(ushort const *)
0x180015afd  nop
0x180015afe  lea     rcx, [rsp+48h+pwszLanguagesBuffer]
0x180015b03  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x180015b08  mov     rax, rbx
0x180015b0b  mov     rbx, [rsp+48h+arg_8]
0x180015b10  add     rsp, 40h
0x180015b14  pop     rdi
0x180015b15  retn
```
