# DeviceLanguageManager::_EnsureTrustedCaller(void)

- ea: `0x180024788`
- end: `0x18002489f`
- name: `?_EnsureTrustedCaller@DeviceLanguageManager@@AEAAJXZ`
- size: `279`
- prototype: `__int64 __fastcall(DeviceLanguageManager *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800218f0`
- `0x180021a30`

## callees

- `0x180003a00`
- `0x180009084`
- `0x180011318`
- `0x180024788`
- `0x180036fd4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800247ee`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800247ee`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180024806`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180024806`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002481c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002481c`

## string_xrefs

- `0x18002483b`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\devicelanguagemanager.cpp`
- `0x180024877`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageproviderutils.cpp`
- `0x18002488d`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageproviderutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DeviceLanguageManager::_EnsureTrustedCaller(DeviceLanguageManager *this)
{
  const char *v1; // r9
  const char *v2; // r9
  WINBOOL v3; // ebx
  DWORD nSubAuthority2; // [rsp+20h] [rbp-60h]
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+60h] [rbp-20h] BYREF
  WINBOOL IsMember; // [rsp+68h] [rbp-18h] BYREF
  PSID SidToCheck; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  IsMember = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  SidToCheck = 0;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1B9,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageproviderutils.cpp",
      v1);
  if ( !CheckTokenMembership(0, SidToCheck, &IsMember) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1BB,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageproviderutils.cpp",
      v2);
  v3 = IsMember;
  if ( SidToCheck )
    LocalFree(SidToCheck);
  if ( v3 || IsCallerLocalSystem() )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x70,
    (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\devicelanguagemanager.cpp",
    (const char *)0x80070005LL,
    nSubAuthority2);
  return 2147942405LL;
}

```

## disassembly

```asm
0x180024788  mov     [rsp-8+arg_0], rbx
0x18002478d  mov     [rsp-8+arg_8], rdi
0x180024792  push    rbp
0x180024793  mov     rbp, rsp
0x180024796  sub     rsp, 80h
0x18002479d  mov     rax, cs:__security_cookie
0x1800247a4  xor     rax, rsp
0x1800247a7  mov     [rbp+var_8], rax
0x1800247ab  xor     edi, edi
0x1800247ad  mov     [rbp+IsMember], edi
0x1800247b0  mov     dword ptr [rbp+pIdentifierAuthority.Value], edi
0x1800247b3  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x1800247b9  mov     [rbp+SidToCheck], rdi
0x1800247bd  lea     rax, [rbp+SidToCheck]
0x1800247c1  mov     [rsp+80h+pSid], rax; pSid
0x1800247c6  mov     [rsp+80h+nSubAuthority7], edi; nSubAuthority7
0x1800247ca  mov     [rsp+80h+nSubAuthority6], edi; nSubAuthority6
0x1800247ce  mov     [rsp+80h+nSubAuthority5], edi; nSubAuthority5
0x1800247d2  mov     [rsp+80h+nSubAuthority4], edi; nSubAuthority4
0x1800247d6  mov     [rsp+80h+nSubAuthority3], edi; nSubAuthority3
0x1800247da  mov     [rsp+80h+nSubAuthority2], edi; int
0x1800247de  mov     r9d, 220h; nSubAuthority1
0x1800247e4  lea     r8d, [rdi+20h]; nSubAuthority0
0x1800247e8  mov     dl, 2; nSubAuthorityCount
0x1800247ea  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x1800247ee  call    cs:__imp_AllocateAndInitializeSid
0x1800247f4  test    eax, eax
0x1800247f6  jz      loc_180024889
0x1800247fc  lea     r8, [rbp+IsMember]; IsMember
0x180024800  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x180024804  xor     ecx, ecx; TokenHandle
0x180024806  call    cs:__imp_CheckTokenMembership
0x18002480c  test    eax, eax
0x18002480e  jz      short loc_180024873
0x180024810  mov     ebx, [rbp+IsMember]
0x180024813  mov     rcx, [rbp+SidToCheck]; hMem
0x180024817  test    rcx, rcx
0x18002481a  jz      short loc_180024822
0x18002481c  call    cs:__imp_LocalFree
0x180024822  test    ebx, ebx
0x180024824  jnz     short loc_180024850
0x180024826  call    ?IsCallerLocalSystem@@YA_NXZ; IsCallerLocalSystem(void)
0x18002482b  test    al, al
0x18002482d  jnz     short loc_180024850
0x18002482f  mov     rcx, [rbp+8]; this
0x180024833  mov     ebx, 80070005h
0x180024838  mov     r9d, ebx; char *
0x18002483b  lea     r8, aOnecoreBaseLan_20; "onecore\\base\\languageoverlay\\service"...
0x180024842  mov     edx, 70h ; 'p'; void *
0x180024847  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002484c  mov     eax, ebx
0x18002484e  jmp     short loc_180024852
0x180024850  xor     eax, eax
0x180024852  mov     rcx, [rbp+var_8]
0x180024856  xor     rcx, rsp; StackCookie
0x180024859  call    __security_check_cookie
0x18002485e  lea     r11, [rsp+80h+var_s0]
0x180024866  mov     rbx, [r11+10h]
0x18002486a  mov     rdi, [r11+18h]
0x18002486e  mov     rsp, r11
0x180024871  pop     rbp
0x180024872  retn
0x180024873  mov     rcx, [rbp+8]; this
0x180024877  lea     r8, aOnecoreBaseLan_17; "onecore\\base\\languageoverlay\\service"...
0x18002487e  mov     edx, 1BBh; void *
0x180024883  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180024889  mov     rcx, [rbp+8]; this
0x18002488d  lea     r8, aOnecoreBaseLan_17; "onecore\\base\\languageoverlay\\service"...
0x180024894  mov     edx, 1B9h; void *
0x180024899  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
