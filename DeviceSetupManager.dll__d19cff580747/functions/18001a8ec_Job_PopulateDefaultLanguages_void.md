# Job::_PopulateDefaultLanguages(void)

- ea: `0x18001a8ec`
- end: `0x18001a9db`
- name: `?_PopulateDefaultLanguages@Job@@IEAAXXZ`
- size: `239`
- prototype: `void(Job *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180014198`
- `0x1800333e8`
- `0x1800345c8`

## callees

- `0x18000a9c0`
- `0x180013c1c`
- `0x18001a8ec`
- `0x18001a9e4`
- `0x18001aa34`
- `0x18002a900`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x18001a91b`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x18001a975`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x18001a91b`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x18001a975`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a9cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a9cd`

## string_xrefs

- `0x18001a925`: `onecoreuap\base\devices\setup\dsm\service\jobbase.cpp`
- `0x18001a952`: `onecoreuap\base\devices\setup\dsm\service\jobbase.cpp`
- `0x18001a97f`: `onecoreuap\base\devices\setup\dsm\service\jobbase.cpp`
- `0x18001a9aa`: `onecoreuap\base\devices\setup\dsm\service\jobbase.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Job::_PopulateDefaultLanguages(Job *this)
{
  const char *v2; // r9
  const char *v3; // r9
  const char *v4; // r9
  int v5; // eax
  PZZWSTR v6; // rcx
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  ULONG pcchLanguagesBuffer; // [rsp+48h] [rbp+28h] BYREF
  ULONG pulNumLanguages; // [rsp+50h] [rbp+30h] BYREF
  PZZWSTR pwszLanguagesBuffer; // [rsp+58h] [rbp+38h] BYREF

  pulNumLanguages = 0;
  pcchLanguagesBuffer = 0;
  if ( !GetThreadPreferredUILanguages(0x18u, &pulNumLanguages, 0, &pcchLanguagesBuffer) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x2B,
      (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\jobbase.cpp",
      v2);
  wil::make_unique_cotaskmem<unsigned short [0]>(&pwszLanguagesBuffer, pcchLanguagesBuffer);
  if ( !pwszLanguagesBuffer )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x2F,
      (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\jobbase.cpp",
      v3);
  if ( !GetThreadPreferredUILanguages(0x18u, &pulNumLanguages, pwszLanguagesBuffer, &pcchLanguagesBuffer) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x35,
      (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\jobbase.cpp",
      v4);
  v5 = MultiSzToPropVariant(pwszLanguagesBuffer, (struct tagPROPVARIANT *)((char *)this + 80));
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x39,
      (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\jobbase.cpp",
      (const char *)(unsigned int)v5,
      savedregs);
  v6 = pwszLanguagesBuffer;
  pwszLanguagesBuffer = 0;
  if ( v6 )
    CoTaskMemFree(v6);
}

```

## disassembly

```asm
0x18001a8ec  push    rbp
0x18001a8ee  push    rbx
0x18001a8ef  push    rdi; int
0x18001a8f0  mov     rbp, rsp
0x18001a8f3  sub     rsp, 20h
0x18001a8f7  mov     rdi, rcx
0x18001a8fa  mov     [rbp+pulNumLanguages], 0
0x18001a901  mov     [rbp+pcchLanguagesBuffer], 0
0x18001a908  mov     rbx, [rbp+18h]
0x18001a90c  lea     r9, [rbp+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x18001a910  xor     r8d, r8d; pwszLanguagesBuffer
0x18001a913  lea     rdx, [rbp+pulNumLanguages]; pulNumLanguages
0x18001a917  lea     ecx, [r8+18h]; dwFlags
0x18001a91b  call    cs:__imp_GetThreadPreferredUILanguages
0x18001a921  test    eax, eax
0x18001a923  jnz     short loc_18001A938
0x18001a925  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x18001a92c  lea     edx, [rax+2Bh]; void *
0x18001a92f  mov     rcx, rbx; this
0x18001a932  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18001a938  mov     edx, [rbp+pcchLanguagesBuffer]
0x18001a93b  lea     rcx, [rbp+pwszLanguagesBuffer]
0x18001a93f  call    ??$make_unique_cotaskmem@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem<ushort [0]>(unsigned __int64)
0x18001a944  nop
0x18001a945  mov     rcx, [rbp+18h]; this
0x18001a949  mov     r8, [rbp+pwszLanguagesBuffer]; pwszLanguagesBuffer
0x18001a94d  test    r8, r8
0x18001a950  jnz     short loc_18001A964
0x18001a952  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x18001a959  mov     edx, 2Fh ; '/'; void *
0x18001a95e  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18001a964  mov     rbx, [rbp+18h]
0x18001a968  lea     r9, [rbp+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x18001a96c  lea     rdx, [rbp+pulNumLanguages]; pulNumLanguages
0x18001a970  mov     ecx, 18h; dwFlags
0x18001a975  call    cs:__imp_GetThreadPreferredUILanguages
0x18001a97b  test    eax, eax
0x18001a97d  jnz     short loc_18001A992
0x18001a97f  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x18001a986  lea     edx, [rax+35h]; void *
0x18001a989  mov     rcx, rbx; this
0x18001a98c  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18001a992  lea     rdx, [rdi+50h]; struct tagPROPVARIANT *
0x18001a996  mov     rcx, [rbp+pwszLanguagesBuffer]; Src
0x18001a99a  call    ?MultiSzToPropVariant@@YAJPEBGPEAUtagPROPVARIANT@@@Z; MultiSzToPropVariant(ushort const *,tagPROPVARIANT *)
0x18001a99f  mov     rcx, [rbp+18h]; this
0x18001a9a3  test    eax, eax
0x18001a9a5  jns     short loc_18001A9BC
0x18001a9a7  mov     r9d, eax; char *
0x18001a9aa  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x18001a9b1  mov     edx, 39h ; '9'; void *
0x18001a9b6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001a9bc  mov     rcx, [rbp+pwszLanguagesBuffer]; pv
0x18001a9c0  mov     [rbp+pwszLanguagesBuffer], 0
0x18001a9c8  test    rcx, rcx
0x18001a9cb  jz      short loc_18001A9D3
0x18001a9cd  call    cs:__imp_CoTaskMemFree
0x18001a9d3  add     rsp, 20h
0x18001a9d7  pop     rdi
0x18001a9d8  pop     rbx
0x18001a9d9  pop     rbp
0x18001a9da  retn
```
