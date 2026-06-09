# AccessCheckIncomingToken(void *,void *)

- ea: `0x18000b510`
- end: `0x18000b82d`
- name: `?AccessCheckIncomingToken@@YAJPEAX0@Z`
- size: `797`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, HANDLE)`
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002b27c`
- `0x18002bc04`
- `0x18002c480`
- `0x180035dbc`

## callees

- `0x18000720c`
- `0x18000b510`
- `0x18001a0d4`
- `0x18001d034`
- `0x18001e7bc`
- `0x18001ef98`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b57e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b67a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b57e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b67a`
- `ntdll!RtlEqualSid` at `0x18000b75e`
- `ntdll!RtlEqualSid` at `0x18000b75e`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000b780`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000b780`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000b570`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000b5e0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000b66c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000b6dc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000b570`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000b5e0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000b66c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000b6dc`

## string_xrefs

- `0x18000b5aa`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18000b5ef`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18000b612`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18000b6a6`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18000b6eb`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18000b70e`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18000b633`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18000b72f`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18000b79e`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18000b7d2`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

## pseudocode

```c
__int64 __fastcall AccessCheckIncomingToken(HANDLE TokenHandle, HANDLE a2)
{
  __int64 v5; // rbx
  const char *v6; // r9
  PSID *v7; // rdi
  int LastError; // r14d
  const char *v9; // r9
  const char *v10; // r9
  PSID *v11; // rbx
  int v12; // r14d
  const char *v13; // r9
  NTSTATUS v14; // eax
  signed int v15; // eax
  unsigned int v16; // esi
  int ReturnLength; // [rsp+20h] [rbp-28h]
  int ReturnLengtha; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  DWORD TokenInformationLength; // [rsp+58h] [rbp+10h] BYREF

  if ( !a2 )
    return 0;
  v5 = (__int64)TokenHandle;
  if ( !TokenHandle )
    v5 = -6;
  TokenInformationLength = 0;
  if ( GetTokenInformation((HANDLE)v5, TokenUser, 0, 0, &TokenInformationLength) || GetLastError() != 122 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x117,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                  v6);
LABEL_12:
    v7 = 0;
    if ( LastError < 0 )
      goto LABEL_13;
    goto LABEL_14;
  }
  v7 = (PSID *)operator new(TokenInformationLength, (const struct std::nothrow_t *)std::nothrow);
  if ( !v7 )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x119,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
      (const char *)0x8007000ELL,
      ReturnLength);
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1926,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)LastError,
      ReturnLength);
    return (unsigned int)LastError;
  }
  if ( !GetTokenInformation((HANDLE)v5, TokenUser, v7, TokenInformationLength, &TokenInformationLength) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x11A,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                  v9);
    operator delete(v7);
    goto LABEL_12;
  }
LABEL_14:
  TokenInformationLength = 0;
  if ( GetTokenInformation(a2, TokenUser, 0, 0, &TokenInformationLength) || GetLastError() != 122 )
  {
    v12 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x117,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
            v10);
LABEL_21:
    v11 = 0;
    if ( v12 < 0 )
      goto LABEL_22;
    goto LABEL_25;
  }
  v11 = (PSID *)operator new(TokenInformationLength, (const struct std::nothrow_t *)std::nothrow);
  if ( !v11 )
  {
    v12 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x119,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
      (const char *)0x8007000ELL,
      ReturnLengtha);
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1927,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)v12,
      ReturnLengtha);
    if ( v7 )
      operator delete(v7);
    return (unsigned int)v12;
  }
  if ( !GetTokenInformation(a2, TokenUser, v11, TokenInformationLength, &TokenInformationLength) )
  {
    v12 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x11A,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
            v13);
    operator delete(v11);
    goto LABEL_21;
  }
LABEL_25:
  if ( RtlEqualSid(*v7, *v11) )
    goto LABEL_32;
  TokenInformationLength = 0;
  v14 = AiCheckForTcbPrivilege(TokenHandle, (int *)&TokenInformationLength);
  v15 = RtlNtStatusToDosErrorNoTeb(v14);
  v16 = v15;
  if ( v15 > 0 )
    v16 = (unsigned __int16)v15 | 0x80070000;
  if ( (v16 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x192F,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)v16,
      ReturnLengtha);
    operator delete(v11);
    operator delete(v7);
    return v16;
  }
  if ( TokenInformationLength )
  {
LABEL_32:
    operator delete(v11);
    operator delete(v7);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1930,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)0x80070005LL,
      ReturnLengtha);
    operator delete(v11);
    operator delete(v7);
    return 2147942405LL;
  }
}

```

## disassembly

```asm
0x18000b510  push    rbp
0x18000b512  push    rsi
0x18000b513  sub     rsp, 38h
0x18000b517  mov     rsi, rdx
0x18000b51a  mov     rbp, rcx
0x18000b51d  test    rdx, rdx
0x18000b520  jnz     short loc_18000B52B
0x18000b522  xor     eax, eax
0x18000b524  add     rsp, 38h
0x18000b528  pop     rsi
0x18000b529  pop     rbp
0x18000b52a  retn
0x18000b52b  mov     [rsp+48h+arg_0], rbx
0x18000b530  mov     rax, 0FFFFFFFFFFFFFFFAh
0x18000b537  mov     [rsp+48h+arg_10], rdi
0x18000b53c  test    rbp, rbp
0x18000b53f  mov     rbx, rbp
0x18000b542  mov     [rsp+48h+arg_18], r14
0x18000b547  cmovz   rbx, rax
0x18000b54b  mov     [rsp+48h+var_18], r15
0x18000b550  lea     rax, [rsp+48h+TokenInformationLength]
0x18000b555  xor     r15d, r15d
0x18000b558  mov     rcx, rbx; TokenHandle
0x18000b55b  mov     [rsp+48h+TokenInformationLength], r15d
0x18000b560  xor     r9d, r9d; TokenInformationLength
0x18000b563  mov     qword ptr [rsp+48h+ReturnLength], rax; int
0x18000b568  xor     r8d, r8d; TokenInformation
0x18000b56b  mov     edx, 1; TokenInformationClass
0x18000b570  call    cs:__imp_GetTokenInformation
0x18000b576  test    eax, eax
0x18000b578  jnz     loc_18000B60D
0x18000b57e  call    cs:__imp_GetLastError
0x18000b584  cmp     eax, 7Ah ; 'z'
0x18000b587  jnz     loc_18000B60D
0x18000b58d  mov     ecx, [rsp+48h+TokenInformationLength]; unsigned __int64
0x18000b591  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b598  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000b59d  mov     rdi, rax
0x18000b5a0  test    rax, rax
0x18000b5a3  jnz     short loc_18000B5C6
0x18000b5a5  mov     rcx, [rsp+48h]; this
0x18000b5aa  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000b5b1  mov     r14d, 8007000Eh
0x18000b5b7  mov     edx, 119h; void *
0x18000b5bc  mov     r9d, r14d; char *
0x18000b5bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b5c4  jmp     short loc_18000B62E
0x18000b5c6  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x18000b5cb  lea     rax, [rsp+48h+TokenInformationLength]
0x18000b5d0  mov     r8, rdi; TokenInformation
0x18000b5d3  mov     qword ptr [rsp+48h+ReturnLength], rax; ReturnLength
0x18000b5d8  mov     edx, 1; TokenInformationClass
0x18000b5dd  mov     rcx, rbx; TokenHandle
0x18000b5e0  call    cs:__imp_GetTokenInformation
0x18000b5e6  test    eax, eax
0x18000b5e8  jnz     short loc_18000B64F
0x18000b5ea  mov     rcx, [rsp+48h]; this
0x18000b5ef  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000b5f6  mov     edx, 11Ah; void *
0x18000b5fb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b600  mov     rcx, rdi; Block
0x18000b603  mov     r14d, eax
0x18000b606  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b60b  jmp     short loc_18000B626
0x18000b60d  mov     rcx, [rsp+48h]; this
0x18000b612  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000b619  mov     edx, 117h; void *
0x18000b61e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b623  mov     r14d, eax
0x18000b626  mov     rdi, r15
0x18000b629  test    r14d, r14d
0x18000b62c  jns     short loc_18000B64F
0x18000b62e  mov     rcx, [rsp+48h]; this
0x18000b633  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18000b63a  mov     r9d, r14d; char *
0x18000b63d  mov     edx, 1926h; void *
0x18000b642  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b647  mov     eax, r14d
0x18000b64a  jmp     loc_18000B812
0x18000b64f  lea     rax, [rsp+48h+TokenInformationLength]
0x18000b654  mov     [rsp+48h+TokenInformationLength], r15d
0x18000b659  xor     r9d, r9d; TokenInformationLength
0x18000b65c  mov     qword ptr [rsp+48h+ReturnLength], rax; int
0x18000b661  xor     r8d, r8d; TokenInformation
0x18000b664  mov     edx, 1; TokenInformationClass
0x18000b669  mov     rcx, rsi; TokenHandle
0x18000b66c  call    cs:__imp_GetTokenInformation
0x18000b672  test    eax, eax
0x18000b674  jnz     loc_18000B709
0x18000b67a  call    cs:__imp_GetLastError
0x18000b680  cmp     eax, 7Ah ; 'z'
0x18000b683  jnz     loc_18000B709
0x18000b689  mov     ecx, [rsp+48h+TokenInformationLength]; unsigned __int64
0x18000b68d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b694  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000b699  mov     rbx, rax
0x18000b69c  test    rax, rax
0x18000b69f  jnz     short loc_18000B6C2
0x18000b6a1  mov     rcx, [rsp+48h]; this
0x18000b6a6  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000b6ad  mov     r14d, 8007000Eh
0x18000b6b3  mov     edx, 119h; void *
0x18000b6b8  mov     r9d, r14d; char *
0x18000b6bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b6c0  jmp     short loc_18000B72A
0x18000b6c2  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x18000b6c7  lea     rax, [rsp+48h+TokenInformationLength]
0x18000b6cc  mov     r8, rbx; TokenInformation
0x18000b6cf  mov     qword ptr [rsp+48h+ReturnLength], rax; int
0x18000b6d4  mov     edx, 1; TokenInformationClass
0x18000b6d9  mov     rcx, rsi; TokenHandle
0x18000b6dc  call    cs:__imp_GetTokenInformation
0x18000b6e2  test    eax, eax
0x18000b6e4  jnz     short loc_18000B758
0x18000b6e6  mov     rcx, [rsp+48h]; this
0x18000b6eb  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000b6f2  mov     edx, 11Ah; void *
0x18000b6f7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b6fc  mov     rcx, rbx; Block
0x18000b6ff  mov     r14d, eax
0x18000b702  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b707  jmp     short loc_18000B722
0x18000b709  mov     rcx, [rsp+48h]; this
0x18000b70e  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000b715  mov     edx, 117h; void *
0x18000b71a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b71f  mov     r14d, eax
0x18000b722  mov     rbx, r15
0x18000b725  test    r14d, r14d
0x18000b728  jns     short loc_18000B758
0x18000b72a  mov     rcx, [rsp+48h]; this
0x18000b72f  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18000b736  mov     r9d, r14d; char *
0x18000b739  mov     edx, 1927h; void *
0x18000b73e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b743  test    rdi, rdi
0x18000b746  jz      short loc_18000B750
0x18000b748  mov     rcx, rdi; Block
0x18000b74b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b750  mov     eax, r14d
0x18000b753  jmp     loc_18000B812
0x18000b758  mov     rdx, [rbx]; Sid2
0x18000b75b  mov     rcx, [rdi]; Sid1
0x18000b75e  call    cs:__imp_RtlEqualSid
0x18000b764  test    al, al
0x18000b766  jnz     loc_18000B800
0x18000b76c  lea     rdx, [rsp+48h+TokenInformationLength]; int *
0x18000b771  mov     [rsp+48h+TokenInformationLength], r15d
0x18000b776  mov     rcx, rbp; TokenHandle
0x18000b779  call    ?AiCheckForTcbPrivilege@@YAJPEAXPEAH@Z; AiCheckForTcbPrivilege(void *,int *)
0x18000b77e  mov     ecx, eax; Status
0x18000b780  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18000b786  mov     esi, eax
0x18000b788  test    eax, eax
0x18000b78a  jle     short loc_18000B795
0x18000b78c  movzx   esi, ax
0x18000b78f  or      esi, 80070000h
0x18000b795  test    esi, esi
0x18000b797  jns     short loc_18000B7C6
0x18000b799  mov     rcx, [rsp+48h]; this
0x18000b79e  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18000b7a5  mov     r9d, esi; char *
0x18000b7a8  mov     edx, 192Fh; void *
0x18000b7ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b7b2  mov     rcx, rbx; Block
0x18000b7b5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b7ba  mov     rcx, rdi; Block
0x18000b7bd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b7c2  mov     eax, esi
0x18000b7c4  jmp     short loc_18000B812
0x18000b7c6  cmp     [rsp+48h+TokenInformationLength], r15d
0x18000b7cb  jnz     short loc_18000B800
0x18000b7cd  mov     rcx, [rsp+48h]; this
0x18000b7d2  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18000b7d9  mov     r9d, 80070005h; char *
0x18000b7df  mov     edx, 1930h; void *
0x18000b7e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b7e9  mov     rcx, rbx; Block
0x18000b7ec  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b7f1  mov     rcx, rdi; Block
0x18000b7f4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b7f9  mov     eax, 80070005h
0x18000b7fe  jmp     short loc_18000B812
0x18000b800  mov     rcx, rbx; Block
0x18000b803  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b808  mov     rcx, rdi; Block
0x18000b80b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b810  xor     eax, eax
0x18000b812  mov     r14, [rsp+48h+arg_18]
0x18000b817  mov     rdi, [rsp+48h+arg_10]
0x18000b81c  mov     rbx, [rsp+48h+arg_0]
0x18000b821  mov     r15, [rsp+48h+var_18]
0x18000b826  add     rsp, 38h
0x18000b82a  pop     rsi
0x18000b82b  pop     rbp
0x18000b82c  retn
```
