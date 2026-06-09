# StateRepository::Cache::Entity::User_NoThrow::GetByToken(StateRepository::Cache::Manager_NoThrow &,void *,__int64 &)

- ea: `0x180009470`
- end: `0x1800096ac`
- name: `?GetByToken@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEAXAEA_J@Z`
- size: `572`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, void *, __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180012cdc`

## callees

- `0x180007c78`
- `0x180009470`
- `0x180009790`
- `0x180018400`
- `0x18001b494`
- `0x18001bc74`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800094c1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000953f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800094c1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000953f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800094d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800094d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800095b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009641`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000967c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800095b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009641`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000967c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180009581`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180009581`

## string_xrefs

- `0x180009596`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x1800095ed`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x180009623`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x180009652`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x180009507`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x180009554`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x1800095d1`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::User_NoThrow::GetByToken(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 v3; // rsi
  void **v6; // rbx
  const char *v7; // r9
  void **v8; // rdi
  int LastError; // esi
  const char *v10; // r9
  void *v11; // rcx
  const char *v12; // r9
  int v13; // edi
  int v15; // eax
  int ReturnLength; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  LPWSTR TokenInformationLength; // [rsp+58h] [rbp+10h] BYREF

  v3 = a2;
  LODWORD(TokenInformationLength) = 0;
  if ( !a2 )
    v3 = -6;
  v6 = 0;
  if ( GetTokenInformation((HANDLE)v3, TokenUser, 0, 0, (PDWORD)&TokenInformationLength) || GetLastError() != 122 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x117,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                  v7);
  }
  else
  {
    v8 = (void **)operator new((unsigned int)TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v8 )
    {
      LastError = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x119,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
        (const char *)0x8007000ELL,
        ReturnLength);
LABEL_17:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x146,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
        (const char *)(unsigned int)LastError,
        ReturnLength);
      return (unsigned int)LastError;
    }
    if ( GetTokenInformation((HANDLE)v3, TokenUser, v8, (DWORD)TokenInformationLength, (PDWORD)&TokenInformationLength) )
    {
      v6 = v8;
      goto LABEL_10;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x11A,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                  v10);
    operator delete(v8);
  }
  if ( LastError < 0 )
    goto LABEL_17;
LABEL_10:
  v11 = *v6;
  TokenInformationLength = 0;
  if ( ConvertSidToStringSidW(v11, &TokenInformationLength) )
  {
    v15 = StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(a1, TokenInformationLength, a3);
    v13 = v15;
    if ( v15 >= 0 )
    {
      if ( TokenInformationLength )
        LocalFree(TokenInformationLength);
      goto LABEL_24;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAC,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)(unsigned int)v15,
      ReturnLength);
    if ( TokenInformationLength )
      LocalFree(TokenInformationLength);
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x147,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)(unsigned int)v13,
      ReturnLength);
    operator delete(v6);
    return (unsigned int)v13;
  }
  v13 = wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)0xAA,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
          v12);
  if ( TokenInformationLength )
    LocalFree(TokenInformationLength);
  if ( v13 < 0 )
    goto LABEL_21;
LABEL_24:
  operator delete(v6);
  return 0;
}

```

## disassembly

```asm
0x180009470  mov     [rsp+arg_0], rbx
0x180009475  mov     [rsp+arg_10], rbp
0x18000947a  mov     [rsp+arg_18], rsi
0x18000947f  push    rdi
0x180009480  push    r14
0x180009482  push    r15
0x180009484  sub     rsp, 30h
0x180009488  xor     r15d, r15d
0x18000948b  mov     rsi, rdx
0x18000948e  test    rdx, rdx
0x180009491  mov     dword ptr [rsp+48h+TokenInformationLength], r15d
0x180009496  mov     rax, 0FFFFFFFFFFFFFFFAh
0x18000949d  mov     rbp, r8
0x1800094a0  cmovz   rsi, rax
0x1800094a4  mov     r14, rcx
0x1800094a7  lea     rax, [rsp+48h+TokenInformationLength]
0x1800094ac  mov     rcx, rsi; TokenHandle
0x1800094af  xor     r9d, r9d; TokenInformationLength
0x1800094b2  mov     qword ptr [rsp+48h+ReturnLength], rax; int
0x1800094b7  xor     r8d, r8d; TokenInformation
0x1800094ba  lea     edx, [r15+1]; TokenInformationClass
0x1800094be  mov     ebx, r15d
0x1800094c1  call    cs:__imp_GetTokenInformation
0x1800094c8  nop     dword ptr [rax+rax+00h]
0x1800094cd  test    eax, eax
0x1800094cf  jnz     loc_1800095CC
0x1800094d5  call    cs:__imp_GetLastError
0x1800094dc  nop     dword ptr [rax+rax+00h]
0x1800094e1  cmp     eax, 7Ah ; 'z'
0x1800094e4  jnz     loc_1800095CC
0x1800094ea  mov     ecx, dword ptr [rsp+48h+TokenInformationLength]; unsigned __int64
0x1800094ee  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800094f5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800094fa  mov     rdi, rax
0x1800094fd  test    rax, rax
0x180009500  jnz     short loc_180009525
0x180009502  mov     rcx, [rsp+48h]; this
0x180009507  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000950e  mov     esi, 8007000Eh
0x180009513  mov     edx, 119h; void *
0x180009518  mov     r9d, esi; char *
0x18000951b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009520  jmp     loc_1800095E8
0x180009525  mov     r9d, dword ptr [rsp+48h+TokenInformationLength]; TokenInformationLength
0x18000952a  lea     rax, [rsp+48h+TokenInformationLength]
0x18000952f  mov     r8, rdi; TokenInformation
0x180009532  mov     qword ptr [rsp+48h+ReturnLength], rax; int
0x180009537  mov     edx, 1; TokenInformationClass
0x18000953c  mov     rcx, rsi; TokenHandle
0x18000953f  call    cs:__imp_GetTokenInformation
0x180009546  nop     dword ptr [rax+rax+00h]
0x18000954b  test    eax, eax
0x18000954d  jnz     short loc_180009571
0x18000954f  mov     rcx, [rsp+48h]; this
0x180009554  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000955b  mov     edx, 11Ah; void *
0x180009560  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009565  mov     rcx, rdi; Block
0x180009568  mov     esi, eax
0x18000956a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000956f  jmp     short loc_1800095E4
0x180009571  mov     rbx, rdi
0x180009574  mov     rcx, [rbx]; Sid
0x180009577  lea     rdx, [rsp+48h+TokenInformationLength]; StringSid
0x18000957c  mov     [rsp+48h+TokenInformationLength], r15
0x180009581  call    cs:__imp_ConvertSidToStringSidW
0x180009588  nop     dword ptr [rax+rax+00h]
0x18000958d  test    eax, eax
0x18000958f  jnz     short loc_180009608
0x180009591  mov     rcx, [rsp+48h]; this
0x180009596  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000959d  mov     edx, 0AAh; void *
0x1800095a2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800095a7  mov     rcx, [rsp+48h+TokenInformationLength]; hMem
0x1800095ac  mov     edi, eax
0x1800095ae  test    rcx, rcx
0x1800095b1  jz      short loc_1800095BF
0x1800095b3  call    cs:__imp_LocalFree
0x1800095ba  nop     dword ptr [rax+rax+00h]
0x1800095bf  test    edi, edi
0x1800095c1  js      loc_18000964D
0x1800095c7  jmp     loc_180009688
0x1800095cc  mov     rcx, [rsp+48h]; this
0x1800095d1  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800095d8  mov     edx, 117h; void *
0x1800095dd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800095e2  mov     esi, eax
0x1800095e4  test    esi, esi
0x1800095e6  jns     short loc_180009574
0x1800095e8  mov     rcx, [rsp+48h]; this
0x1800095ed  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800095f4  mov     r9d, esi; char *
0x1800095f7  mov     edx, 146h; void *
0x1800095fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009601  mov     eax, esi
0x180009603  jmp     loc_180009692
0x180009608  mov     rdx, [rsp+48h+TokenInformationLength]; unsigned __int16 *
0x18000960d  mov     r8, rbp; __int64 *
0x180009610  mov     rcx, r14; struct StateRepository::Cache::Manager_NoThrow *
0x180009613  call    ?GetByUserSidAsString@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x180009618  mov     edi, eax
0x18000961a  test    eax, eax
0x18000961c  jns     short loc_180009672
0x18000961e  mov     rcx, [rsp+48h]; this
0x180009623  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000962a  mov     r9d, eax; char *
0x18000962d  mov     edx, 0ACh; void *
0x180009632  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009637  mov     rcx, [rsp+48h+TokenInformationLength]; hMem
0x18000963c  test    rcx, rcx
0x18000963f  jz      short loc_18000964D
0x180009641  call    cs:__imp_LocalFree
0x180009648  nop     dword ptr [rax+rax+00h]
0x18000964d  mov     rcx, [rsp+48h]; this
0x180009652  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x180009659  mov     r9d, edi; char *
0x18000965c  mov     edx, 147h; void *
0x180009661  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009666  mov     rcx, rbx; Block
0x180009669  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000966e  mov     eax, edi
0x180009670  jmp     short loc_180009692
0x180009672  mov     rcx, [rsp+48h+TokenInformationLength]; hMem
0x180009677  test    rcx, rcx
0x18000967a  jz      short loc_180009688
0x18000967c  call    cs:__imp_LocalFree
0x180009683  nop     dword ptr [rax+rax+00h]
0x180009688  mov     rcx, rbx; Block
0x18000968b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009690  xor     eax, eax
0x180009692  mov     rbx, [rsp+48h+arg_0]
0x180009697  mov     rbp, [rsp+48h+arg_10]
0x18000969c  mov     rsi, [rsp+48h+arg_18]
0x1800096a1  add     rsp, 30h
0x1800096a5  pop     r15
0x1800096a7  pop     r14
0x1800096a9  pop     rdi
0x1800096aa  retn
```
