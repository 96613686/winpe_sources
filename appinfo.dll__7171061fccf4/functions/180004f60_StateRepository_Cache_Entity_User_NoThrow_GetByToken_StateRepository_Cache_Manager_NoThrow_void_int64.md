# StateRepository::Cache::Entity::User_NoThrow::GetByToken(StateRepository::Cache::Manager_NoThrow &,void *,__int64 &)

- ea: `0x180004f60`
- end: `0x180005155`
- name: `?GetByToken@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEAXAEA_J@Z`
- size: `501`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, void *, __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000a938`

## callees

- `0x180004f60`
- `0x180006670`
- `0x18000720c`
- `0x18001a0d4`
- `0x18001e7bc`
- `0x18001ef98`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004fb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004fb7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800050b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800050fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005132`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800050b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800050fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005132`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004fa9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180005014`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004fa9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180005014`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000508c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000508c`

## string_xrefs

- `0x180005064`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18000509b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x1800050df`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x180005108`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x180004fdf`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x180005023`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x180005045`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::User_NoThrow::GetByToken(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 v3; // rdi
  const char *v6; // r9
  void **v7; // rbx
  int LastError; // edi
  const char *v9; // r9
  void *v11; // rcx
  const char *v12; // r9
  int v13; // edi
  int v14; // eax
  int ReturnLength; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  LPWSTR TokenInformationLength; // [rsp+58h] [rbp+10h] BYREF

  v3 = a2;
  if ( !a2 )
    v3 = -6;
  LODWORD(TokenInformationLength) = 0;
  if ( GetTokenInformation((HANDLE)v3, TokenUser, 0, 0, (PDWORD)&TokenInformationLength) || GetLastError() != 122 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x117,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                  v6);
LABEL_10:
    v7 = 0;
    if ( LastError < 0 )
      goto LABEL_11;
    goto LABEL_12;
  }
  v7 = (void **)operator new((unsigned int)TokenInformationLength, (const struct std::nothrow_t *)std::nothrow);
  if ( !v7 )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x119,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
      (const char *)0x8007000ELL,
      ReturnLength);
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x146,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)(unsigned int)LastError,
      ReturnLength);
    return (unsigned int)LastError;
  }
  if ( !GetTokenInformation((HANDLE)v3, TokenUser, v7, (DWORD)TokenInformationLength, (PDWORD)&TokenInformationLength) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x11A,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                  v9);
    operator delete(v7);
    goto LABEL_10;
  }
LABEL_12:
  v11 = *v7;
  TokenInformationLength = 0;
  if ( ConvertSidToStringSidW(v11, &TokenInformationLength) )
  {
    v14 = StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(a1, TokenInformationLength, a3);
    v13 = v14;
    if ( v14 >= 0 )
    {
      if ( TokenInformationLength )
        LocalFree(TokenInformationLength);
      goto LABEL_23;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAC,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)(unsigned int)v14,
      ReturnLength);
    if ( TokenInformationLength )
      LocalFree(TokenInformationLength);
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x147,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)(unsigned int)v13,
      ReturnLength);
    operator delete(v7);
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
    goto LABEL_20;
LABEL_23:
  operator delete(v7);
  return 0;
}

```

## disassembly

```asm
0x180004f60  mov     [rsp+arg_0], rbx
0x180004f65  mov     [rsp+arg_10], rbp
0x180004f6a  push    rsi
0x180004f6b  push    rdi
0x180004f6c  push    r14
0x180004f6e  sub     rsp, 30h
0x180004f72  test    rdx, rdx
0x180004f75  mov     rdi, rdx
0x180004f78  mov     rax, 0FFFFFFFFFFFFFFFAh
0x180004f7f  mov     rsi, r8
0x180004f82  cmovz   rdi, rax
0x180004f86  mov     rbp, rcx
0x180004f89  lea     rax, [rsp+48h+TokenInformationLength]
0x180004f8e  xor     r14d, r14d
0x180004f91  mov     rcx, rdi; TokenHandle
0x180004f94  mov     dword ptr [rsp+48h+TokenInformationLength], r14d
0x180004f99  xor     r9d, r9d; TokenInformationLength
0x180004f9c  mov     qword ptr [rsp+48h+ReturnLength], rax; int
0x180004fa1  xor     r8d, r8d; TokenInformation
0x180004fa4  mov     edx, 1; TokenInformationClass
0x180004fa9  call    cs:__imp_GetTokenInformation
0x180004faf  test    eax, eax
0x180004fb1  jnz     loc_180005040
0x180004fb7  call    cs:__imp_GetLastError
0x180004fbd  cmp     eax, 7Ah ; 'z'
0x180004fc0  jnz     short loc_180005040
0x180004fc2  mov     ecx, dword ptr [rsp+48h+TokenInformationLength]; unsigned __int64
0x180004fc6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180004fcd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180004fd2  mov     rbx, rax
0x180004fd5  test    rax, rax
0x180004fd8  jnz     short loc_180004FFA
0x180004fda  mov     rcx, [rsp+48h]; this
0x180004fdf  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180004fe6  mov     edi, 8007000Eh
0x180004feb  mov     edx, 119h; void *
0x180004ff0  mov     r9d, edi; char *
0x180004ff3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004ff8  jmp     short loc_18000505F
0x180004ffa  mov     r9d, dword ptr [rsp+48h+TokenInformationLength]; TokenInformationLength
0x180004fff  lea     rax, [rsp+48h+TokenInformationLength]
0x180005004  mov     r8, rbx; TokenInformation
0x180005007  mov     qword ptr [rsp+48h+ReturnLength], rax; int
0x18000500c  mov     edx, 1; TokenInformationClass
0x180005011  mov     rcx, rdi; TokenHandle
0x180005014  call    cs:__imp_GetTokenInformation
0x18000501a  test    eax, eax
0x18000501c  jnz     short loc_18000507F
0x18000501e  mov     rcx, [rsp+48h]; this
0x180005023  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000502a  mov     edx, 11Ah; void *
0x18000502f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180005034  mov     rcx, rbx; Block
0x180005037  mov     edi, eax
0x180005039  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000503e  jmp     short loc_180005058
0x180005040  mov     rcx, [rsp+48h]; this
0x180005045  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000504c  mov     edx, 117h; void *
0x180005051  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180005056  mov     edi, eax
0x180005058  mov     rbx, r14
0x18000505b  test    edi, edi
0x18000505d  jns     short loc_18000507F
0x18000505f  mov     rcx, [rsp+48h]; this
0x180005064  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000506b  mov     r9d, edi; char *
0x18000506e  mov     edx, 146h; void *
0x180005073  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005078  mov     eax, edi
0x18000507a  jmp     loc_180005142
0x18000507f  mov     rcx, [rbx]; Sid
0x180005082  lea     rdx, [rsp+48h+TokenInformationLength]; StringSid
0x180005087  mov     [rsp+48h+TokenInformationLength], r14
0x18000508c  call    cs:__imp_ConvertSidToStringSidW
0x180005092  test    eax, eax
0x180005094  jnz     short loc_1800050C4
0x180005096  mov     rcx, [rsp+48h]; this
0x18000509b  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800050a2  mov     edx, 0AAh; void *
0x1800050a7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800050ac  mov     rcx, [rsp+48h+TokenInformationLength]; hMem
0x1800050b1  mov     edi, eax
0x1800050b3  test    rcx, rcx
0x1800050b6  jz      short loc_1800050BE
0x1800050b8  call    cs:__imp_LocalFree
0x1800050be  test    edi, edi
0x1800050c0  js      short loc_180005103
0x1800050c2  jmp     short loc_180005138
0x1800050c4  mov     rdx, [rsp+48h+TokenInformationLength]; unsigned __int16 *
0x1800050c9  mov     r8, rsi; __int64 *
0x1800050cc  mov     rcx, rbp; struct StateRepository::Cache::Manager_NoThrow *
0x1800050cf  call    ?GetByUserSidAsString@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x1800050d4  mov     edi, eax
0x1800050d6  test    eax, eax
0x1800050d8  jns     short loc_180005128
0x1800050da  mov     rcx, [rsp+48h]; this
0x1800050df  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800050e6  mov     r9d, eax; char *
0x1800050e9  mov     edx, 0ACh; void *
0x1800050ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800050f3  mov     rcx, [rsp+48h+TokenInformationLength]; hMem
0x1800050f8  test    rcx, rcx
0x1800050fb  jz      short loc_180005103
0x1800050fd  call    cs:__imp_LocalFree
0x180005103  mov     rcx, [rsp+48h]; this
0x180005108  lea     r8, aOnecorePrivate_3; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000510f  mov     r9d, edi; char *
0x180005112  mov     edx, 147h; void *
0x180005117  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000511c  mov     rcx, rbx; Block
0x18000511f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005124  mov     eax, edi
0x180005126  jmp     short loc_180005142
0x180005128  mov     rcx, [rsp+48h+TokenInformationLength]; hMem
0x18000512d  test    rcx, rcx
0x180005130  jz      short loc_180005138
0x180005132  call    cs:__imp_LocalFree
0x180005138  mov     rcx, rbx; Block
0x18000513b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005140  xor     eax, eax
0x180005142  mov     rbx, [rsp+48h+arg_0]
0x180005147  mov     rbp, [rsp+48h+arg_10]
0x18000514c  add     rsp, 30h
0x180005150  pop     r14
0x180005152  pop     rdi
0x180005153  pop     rsi
0x180005154  retn
```
