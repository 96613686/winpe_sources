# GetSystemPreferredMuiLanguages(void)

- ea: `0x1800158f0`
- end: `0x1800159b2`
- name: `?GetSystemPreferredMuiLanguages@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ`
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
- `0x1800158f0`
- `0x18001dcc0`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x180015926`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x18001596d`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x180015926`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x18001596d`

## string_xrefs

- `0x180015930`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`
- `0x180015977`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
WCHAR *__fastcall GetSystemPreferredMuiLanguages(WCHAR *a1)
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
  if ( !GetSystemPreferredUILanguages(8u, &pulNumLanguages, 0, &pcchLanguagesBuffer) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x2C8,
      (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
      v2);
  std::make_unique<unsigned short [0],0>(pwszLanguagesBuffer, pcchLanguagesBuffer);
  if ( !GetSystemPreferredUILanguages(8u, &pulNumLanguages, pwszLanguagesBuffer[0], &pcchLanguagesBuffer) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x2CD,
      (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
      v3);
  WstringContainerFromMultiString<std::vector<std::wstring>>(a1, pwszLanguagesBuffer[0]);
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>((void **)pwszLanguagesBuffer, v4);
  return a1;
}

```

## disassembly

```asm
0x1800158f0  mov     rax, rsp
0x1800158f3  mov     [rax+10h], rbx
0x1800158f7  push    rdi
0x1800158f8  sub     rsp, 40h
0x1800158fc  mov     rbx, rcx
0x1800158ff  mov     [rsp+48h+pwszLanguagesBuffer], rcx
0x180015904  mov     dword ptr [rax-24h], 0
0x18001590b  mov     dword ptr [rax-28h], 0
0x180015912  mov     rdi, [rsp+48h]
0x180015917  lea     r9, [rax-28h]; pcchLanguagesBuffer
0x18001591b  xor     r8d, r8d; pwszLanguagesBuffer
0x18001591e  lea     rdx, [rax-24h]; pulNumLanguages
0x180015922  lea     ecx, [r8+8]; dwFlags
0x180015926  call    cs:__imp_GetSystemPreferredUILanguages
0x18001592c  test    eax, eax
0x18001592e  jnz     short loc_180015945
0x180015930  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x180015937  mov     edx, 2C8h; void *
0x18001593c  mov     rcx, rdi; this
0x18001593f  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180015945  mov     edx, [rsp+48h+pcchLanguagesBuffer]
0x180015949  lea     rcx, [rsp+48h+pwszLanguagesBuffer]
0x18001594e  call    ??$make_unique@$$BY0A@G$0A@@std@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@0@_K@Z; std::make_unique<ushort [0],0>(unsigned __int64)
0x180015953  nop
0x180015954  mov     rdi, [rsp+48h]
0x180015959  lea     r9, [rsp+48h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x18001595e  mov     r8, [rsp+48h+pwszLanguagesBuffer]; pwszLanguagesBuffer
0x180015963  lea     rdx, [rsp+48h+pulNumLanguages]; pulNumLanguages
0x180015968  mov     ecx, 8; dwFlags
0x18001596d  call    cs:__imp_GetSystemPreferredUILanguages
0x180015973  test    eax, eax
0x180015975  jnz     short loc_18001598C
0x180015977  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x18001597e  mov     edx, 2CDh; void *
0x180015983  mov     rcx, rdi; this
0x180015986  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18001598c  mov     rdx, [rsp+48h+pwszLanguagesBuffer]
0x180015991  mov     rcx, rbx
0x180015994  call    ??$WstringContainerFromMultiString@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEBG@Z; WstringContainerFromMultiString<std::vector<std::wstring>>(ushort const *)
0x180015999  nop
0x18001599a  lea     rcx, [rsp+48h+pwszLanguagesBuffer]
0x18001599f  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1800159a4  mov     rax, rbx
0x1800159a7  mov     rbx, [rsp+48h+arg_8]
0x1800159ac  add     rsp, 40h
0x1800159b0  pop     rdi
0x1800159b1  retn
```
