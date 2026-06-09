# IsDefaultAccount(bool *)

- ea: `0x1800601e8`
- end: `0x180060319`
- name: `?IsDefaultAccount@@YAJPEA_N@Z`
- size: `305`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18004d4cc`

## callees

- `0x180004350`
- `0x180005d6c`
- `0x180009064`
- `0x180009084`
- `0x1800601e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060222`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060222`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180060214`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180060287`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180060214`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180060287`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1800602be`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1800602be`

## string_xrefs

- `0x18006024e`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x180060296`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x1800602e5`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x180060301`: `onecore\base\languageoverlay\common\platformutils.cpp`

## pseudocode

```c
__int64 __fastcall IsDefaultAccount(bool *a1)
{
  PSID *v1; // rbx
  const char *v3; // r9
  PSID *v4; // rsi
  int LastError; // edi
  const char *v6; // r9
  int ReturnLength; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  DWORD TokenInformationLength; // [rsp+68h] [rbp+10h] BYREF

  v1 = 0;
  TokenInformationLength = 0;
  if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenUser, 0, 0, &TokenInformationLength)
    || GetLastError() != 122 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x117,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
                  v3);
    goto LABEL_10;
  }
  v4 = (PSID *)operator new(TokenInformationLength, (const struct std::nothrow_t *)std::nothrow);
  if ( v4 )
  {
    if ( GetTokenInformation(
           (HANDLE)0xFFFFFFFFFFFFFFFALL,
           TokenUser,
           v4,
           TokenInformationLength,
           &TokenInformationLength) )
    {
      v1 = v4;
      goto LABEL_8;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x11A,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
                  v6);
    operator delete(v4);
LABEL_10:
    if ( LastError < 0 )
      goto LABEL_11;
LABEL_8:
    *a1 = IsWellKnownSid(*v1, WinLocalAccountAndAdministratorSid|WinCreatorGroupSid);
    operator delete(v1);
    return 0;
  }
  LastError = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x119,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
    (const char *)0x8007000ELL,
    ReturnLength);
LABEL_11:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x88,
    (unsigned int)"onecore\\base\\languageoverlay\\common\\platformutils.cpp",
    (const char *)(unsigned int)LastError,
    ReturnLength);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800601e8  push    rbx
0x1800601ea  push    rsi
0x1800601eb  push    rdi
0x1800601ec  push    r14
0x1800601ee  sub     rsp, 38h
0x1800601f2  xor     ebx, ebx
0x1800601f4  lea     rax, [rsp+58h+TokenInformationLength]
0x1800601f9  mov     r14, rcx
0x1800601fc  mov     [rsp+58h+TokenInformationLength], ebx
0x180060200  xor     r9d, r9d; TokenInformationLength
0x180060203  mov     qword ptr [rsp+58h+ReturnLength], rax; int
0x180060208  xor     r8d, r8d; TokenInformation
0x18006020b  lea     edi, [rbx+1]
0x18006020e  mov     edx, edi; TokenInformationClass
0x180060210  lea     rcx, [rbx-6]; TokenHandle
0x180060214  call    cs:__imp_GetTokenInformation
0x18006021a  test    eax, eax
0x18006021c  jnz     loc_1800602E0
0x180060222  call    cs:__imp_GetLastError
0x180060228  cmp     eax, 7Ah ; 'z'
0x18006022b  jnz     loc_1800602E0
0x180060231  mov     ecx, [rsp+58h+TokenInformationLength]; unsigned __int64
0x180060235  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18006023c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180060241  mov     rsi, rax
0x180060244  test    rax, rax
0x180060247  jnz     short loc_18006026C
0x180060249  mov     rcx, [rsp+58h]; this
0x18006024e  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180060255  mov     edi, 8007000Eh
0x18006025a  mov     edx, 119h; void *
0x18006025f  mov     r9d, edi; char *
0x180060262  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180060267  jmp     loc_1800602FC
0x18006026c  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x180060271  lea     rax, [rsp+58h+TokenInformationLength]
0x180060276  mov     r8, rsi; TokenInformation
0x180060279  mov     qword ptr [rsp+58h+ReturnLength], rax; ReturnLength
0x18006027e  mov     edx, edi; TokenInformationClass
0x180060280  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x180060287  call    cs:__imp_GetTokenInformation
0x18006028d  test    eax, eax
0x18006028f  jnz     short loc_1800602B3
0x180060291  mov     rcx, [rsp+58h]; this
0x180060296  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18006029d  mov     edx, 11Ah; void *
0x1800602a2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800602a7  mov     rcx, rsi; Block
0x1800602aa  mov     edi, eax
0x1800602ac  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800602b1  jmp     short loc_1800602F8
0x1800602b3  mov     rbx, rsi
0x1800602b6  mov     rcx, [rbx]; pSid
0x1800602b9  mov     edx, 6Eh ; 'n'; WellKnownSidType
0x1800602be  call    cs:__imp_IsWellKnownSid
0x1800602c4  test    eax, eax
0x1800602c6  mov     rcx, rbx; Block
0x1800602c9  setnz   al
0x1800602cc  mov     [r14], al
0x1800602cf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800602d4  xor     eax, eax
0x1800602d6  add     rsp, 38h
0x1800602da  pop     r14
0x1800602dc  pop     rdi
0x1800602dd  pop     rsi
0x1800602de  pop     rbx
0x1800602df  retn
0x1800602e0  mov     rcx, [rsp+58h]; this
0x1800602e5  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800602ec  mov     edx, 117h; void *
0x1800602f1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800602f6  mov     edi, eax
0x1800602f8  test    edi, edi
0x1800602fa  jns     short loc_1800602B6
0x1800602fc  mov     rcx, [rsp+58h]; this
0x180060301  lea     r8, aOnecoreBaseLan_2; "onecore\\base\\languageoverlay\\common"...
0x180060308  mov     r9d, edi; char *
0x18006030b  mov     edx, 88h; void *
0x180060310  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180060315  mov     eax, edi
0x180060317  jmp     short loc_1800602D6
```
