# AccessCheckIncomingToken(void *,void *)

- ea: `0x18000bb10`
- end: `0x18000be90`
- name: `?AccessCheckIncomingToken@@YAJPEAX0@Z`
- size: `896`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, HANDLE)`
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180028aa4`
- `0x180029474`
- `0x180029ce4`
- `0x1800327a0`

## callees

- `0x180007c78`
- `0x18000bb10`
- `0x180018150`
- `0x18001ac0c`
- `0x18001b0c4`
- `0x18001b8a4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000bb7b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000bbfa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000bc52`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000bd14`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000bb7b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000bbfa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000bc52`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000bd14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc66`
- `ntdll!RtlEqualSid` at `0x18000bd53`
- `ntdll!RtlEqualSid` at `0x18000bd53`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000bd7b`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000bd7b`

## string_xrefs

- `0x18000bcde`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18000bd9f`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18000bdf1`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18000be23`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18000bbc1`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18000bc0f`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18000bc98`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18000bcbc`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18000bd29`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18000bdcf`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

## pseudocode

```c
__int64 __fastcall AccessCheckIncomingToken(HANDLE TokenHandle, HANDLE a2)
{
  __int64 v5; // rsi
  PSID *v6; // rdi
  const char *v7; // r9
  PSID *v8; // rbx
  int LastError; // r15d
  const char *v10; // r9
  PSID *v11; // rbx
  const char *v12; // r9
  PSID *v13; // rsi
  int v14; // r15d
  const char *v15; // r9
  NTSTATUS v16; // eax
  signed int v17; // eax
  unsigned int v18; // esi
  int ReturnLength; // [rsp+20h] [rbp-38h]
  int ReturnLengtha; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  DWORD TokenInformationLength; // [rsp+68h] [rbp+10h] BYREF

  if ( !a2 )
    return 0;
  v5 = (__int64)TokenHandle;
  v6 = 0;
  TokenInformationLength = 0;
  if ( !TokenHandle )
    v5 = -6;
  if ( GetTokenInformation((HANDLE)v5, TokenUser, 0, 0, &TokenInformationLength) || GetLastError() != 122 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x117,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                  v7);
  }
  else
  {
    v8 = (PSID *)operator new(TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v8 )
    {
      LastError = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x119,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
        (const char *)0x8007000ELL,
        ReturnLength);
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x15DA,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
        (const char *)(unsigned int)LastError,
        ReturnLength);
      return (unsigned int)LastError;
    }
    if ( GetTokenInformation((HANDLE)v5, TokenUser, v8, TokenInformationLength, &TokenInformationLength) )
    {
      v6 = v8;
      goto LABEL_12;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x11A,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                  v10);
    operator delete(v8);
  }
  if ( LastError < 0 )
    goto LABEL_18;
LABEL_12:
  TokenInformationLength = 0;
  v11 = 0;
  if ( GetTokenInformation(a2, TokenUser, 0, 0, &TokenInformationLength) || GetLastError() != 122 )
  {
    v14 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x117,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
            v12);
  }
  else
  {
    v13 = (PSID *)operator new(TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v13 )
    {
      v14 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x119,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
        (const char *)0x8007000ELL,
        ReturnLengtha);
LABEL_29:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x15DB,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
        (const char *)(unsigned int)v14,
        ReturnLengtha);
      if ( v6 )
        operator delete(v6);
      return (unsigned int)v14;
    }
    if ( GetTokenInformation(a2, TokenUser, v13, TokenInformationLength, &TokenInformationLength) )
    {
      v11 = v13;
      goto LABEL_22;
    }
    v14 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x11A,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
            v15);
    operator delete(v13);
  }
  if ( v14 < 0 )
    goto LABEL_29;
LABEL_22:
  if ( RtlEqualSid(*v6, *v11) )
    goto LABEL_34;
  TokenInformationLength = 0;
  v16 = AiCheckForTcbPrivilege(TokenHandle, (int *)&TokenInformationLength);
  v17 = RtlNtStatusToDosErrorNoTeb(v16);
  v18 = v17;
  if ( v17 > 0 )
    v18 = (unsigned __int16)v17 | 0x80070000;
  if ( (v18 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x15E3,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)v18,
      ReturnLengtha);
    operator delete(v11);
    operator delete(v6);
    return v18;
  }
  if ( TokenInformationLength )
  {
LABEL_34:
    operator delete(v11);
    operator delete(v6);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x15E4,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)0x80070005LL,
      ReturnLengtha);
    operator delete(v11);
    operator delete(v6);
    return 2147942405LL;
  }
}

```

## disassembly

```asm
0x18000bb10  push    rbp
0x18000bb12  push    r14
0x18000bb14  sub     rsp, 48h
0x18000bb18  mov     rbp, rdx
0x18000bb1b  mov     r14, rcx
0x18000bb1e  test    rdx, rdx
0x18000bb21  jnz     short loc_18000BB2E
0x18000bb23  xor     eax, eax
0x18000bb25  add     rsp, 48h
0x18000bb29  pop     r14
0x18000bb2b  pop     rbp
0x18000bb2c  retn
0x18000bb2e  mov     [rsp+58h+arg_0], rbx
0x18000bb33  mov     rax, 0FFFFFFFFFFFFFFFAh
0x18000bb3a  mov     [rsp+58h+arg_10], rsi
0x18000bb3f  mov     rsi, r14
0x18000bb42  mov     [rsp+58h+var_18], rdi
0x18000bb47  mov     [rsp+58h+var_20], r12
0x18000bb4c  xor     r12d, r12d
0x18000bb4f  test    r14, r14
0x18000bb52  mov     [rsp+58h+var_28], r15
0x18000bb57  mov     edi, r12d
0x18000bb5a  mov     [rsp+58h+TokenInformationLength], r12d
0x18000bb5f  cmovz   rsi, rax
0x18000bb63  lea     rax, [rsp+58h+TokenInformationLength]
0x18000bb68  mov     rcx, rsi; TokenHandle
0x18000bb6b  mov     qword ptr [rsp+58h+ReturnLength], rax; int
0x18000bb70  xor     r9d, r9d; TokenInformationLength
0x18000bb73  lea     edx, [r12+1]; TokenInformationClass
0x18000bb78  xor     r8d, r8d; TokenInformation
0x18000bb7b  call    cs:__imp_GetTokenInformation
0x18000bb82  nop     dword ptr [rax+rax+00h]
0x18000bb87  test    eax, eax
0x18000bb89  jnz     loc_18000BCB7
0x18000bb8f  call    cs:__imp_GetLastError
0x18000bb96  nop     dword ptr [rax+rax+00h]
0x18000bb9b  cmp     eax, 7Ah ; 'z'
0x18000bb9e  jnz     loc_18000BCB7
0x18000bba4  mov     ecx, [rsp+58h+TokenInformationLength]; unsigned __int64
0x18000bba8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000bbaf  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000bbb4  mov     rbx, rax
0x18000bbb7  test    rax, rax
0x18000bbba  jnz     short loc_18000BBE0
0x18000bbbc  mov     rcx, [rsp+58h]; this
0x18000bbc1  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000bbc8  mov     r15d, 8007000Eh
0x18000bbce  mov     edx, 119h; void *
0x18000bbd3  mov     r9d, r15d; char *
0x18000bbd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bbdb  jmp     loc_18000BCD9
0x18000bbe0  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x18000bbe5  lea     rax, [rsp+58h+TokenInformationLength]
0x18000bbea  mov     r8, rbx; TokenInformation
0x18000bbed  mov     qword ptr [rsp+58h+ReturnLength], rax; ReturnLength
0x18000bbf2  mov     edx, 1; TokenInformationClass
0x18000bbf7  mov     rcx, rsi; TokenHandle
0x18000bbfa  call    cs:__imp_GetTokenInformation
0x18000bc01  nop     dword ptr [rax+rax+00h]
0x18000bc06  test    eax, eax
0x18000bc08  jnz     short loc_18000BC30
0x18000bc0a  mov     rcx, [rsp+58h]; this
0x18000bc0f  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000bc16  mov     edx, 11Ah; void *
0x18000bc1b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000bc20  mov     rcx, rbx; Block
0x18000bc23  mov     r15d, eax
0x18000bc26  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000bc2b  jmp     loc_18000BCD0
0x18000bc30  mov     rdi, rbx
0x18000bc33  xor     r9d, r9d; TokenInformationLength
0x18000bc36  mov     [rsp+58h+TokenInformationLength], r12d
0x18000bc3b  lea     rax, [rsp+58h+TokenInformationLength]
0x18000bc40  xor     r8d, r8d; TokenInformation
0x18000bc43  mov     rcx, rbp; TokenHandle
0x18000bc46  mov     qword ptr [rsp+58h+ReturnLength], rax; int
0x18000bc4b  mov     rbx, r12
0x18000bc4e  lea     edx, [r9+1]; TokenInformationClass
0x18000bc52  call    cs:__imp_GetTokenInformation
0x18000bc59  nop     dword ptr [rax+rax+00h]
0x18000bc5e  test    eax, eax
0x18000bc60  jnz     loc_18000BDCA
0x18000bc66  call    cs:__imp_GetLastError
0x18000bc6d  nop     dword ptr [rax+rax+00h]
0x18000bc72  cmp     eax, 7Ah ; 'z'
0x18000bc75  jnz     loc_18000BDCA
0x18000bc7b  mov     ecx, [rsp+58h+TokenInformationLength]; unsigned __int64
0x18000bc7f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000bc86  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000bc8b  mov     rsi, rax
0x18000bc8e  test    rax, rax
0x18000bc91  jnz     short loc_18000BCFA
0x18000bc93  mov     rcx, [rsp+58h]; this
0x18000bc98  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000bc9f  mov     r15d, 8007000Eh
0x18000bca5  mov     edx, 119h; void *
0x18000bcaa  mov     r9d, r15d; char *
0x18000bcad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bcb2  jmp     loc_18000BDEC
0x18000bcb7  mov     rcx, [rsp+58h]; this
0x18000bcbc  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000bcc3  mov     edx, 117h; void *
0x18000bcc8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000bccd  mov     r15d, eax
0x18000bcd0  test    r15d, r15d
0x18000bcd3  jns     loc_18000BC33
0x18000bcd9  mov     rcx, [rsp+58h]; this
0x18000bcde  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18000bce5  mov     r9d, r15d; char *
0x18000bce8  mov     edx, 15DAh; void *
0x18000bced  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bcf2  mov     eax, r15d
0x18000bcf5  jmp     loc_18000BE63
0x18000bcfa  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x18000bcff  lea     rax, [rsp+58h+TokenInformationLength]
0x18000bd04  mov     r8, rsi; TokenInformation
0x18000bd07  mov     qword ptr [rsp+58h+ReturnLength], rax; int
0x18000bd0c  mov     edx, 1; TokenInformationClass
0x18000bd11  mov     rcx, rbp; TokenHandle
0x18000bd14  call    cs:__imp_GetTokenInformation
0x18000bd1b  nop     dword ptr [rax+rax+00h]
0x18000bd20  test    eax, eax
0x18000bd22  jnz     short loc_18000BD4A
0x18000bd24  mov     rcx, [rsp+58h]; this
0x18000bd29  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000bd30  mov     edx, 11Ah; void *
0x18000bd35  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000bd3a  mov     rcx, rsi; Block
0x18000bd3d  mov     r15d, eax
0x18000bd40  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000bd45  jmp     loc_18000BDE3
0x18000bd4a  mov     rbx, rsi
0x18000bd4d  mov     rdx, [rbx]; Sid2
0x18000bd50  mov     rcx, [rdi]; Sid1
0x18000bd53  call    cs:__imp_RtlEqualSid
0x18000bd5a  nop     dword ptr [rax+rax+00h]
0x18000bd5f  test    al, al
0x18000bd61  jnz     loc_18000BE51
0x18000bd67  lea     rdx, [rsp+58h+TokenInformationLength]; int *
0x18000bd6c  mov     [rsp+58h+TokenInformationLength], r12d
0x18000bd71  mov     rcx, r14; TokenHandle
0x18000bd74  call    ?AiCheckForTcbPrivilege@@YAJPEAXPEAH@Z; AiCheckForTcbPrivilege(void *,int *)
0x18000bd79  mov     ecx, eax; Status
0x18000bd7b  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18000bd82  nop     dword ptr [rax+rax+00h]
0x18000bd87  mov     esi, eax
0x18000bd89  test    eax, eax
0x18000bd8b  jle     short loc_18000BD96
0x18000bd8d  movzx   esi, ax
0x18000bd90  or      esi, 80070000h
0x18000bd96  test    esi, esi
0x18000bd98  jns     short loc_18000BE17
0x18000bd9a  mov     rcx, [rsp+58h]; this
0x18000bd9f  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18000bda6  mov     r9d, esi; char *
0x18000bda9  mov     edx, 15E3h; void *
0x18000bdae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bdb3  mov     rcx, rbx; Block
0x18000bdb6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000bdbb  mov     rcx, rdi; Block
0x18000bdbe  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000bdc3  mov     eax, esi
0x18000bdc5  jmp     loc_18000BE63
0x18000bdca  mov     rcx, [rsp+58h]; this
0x18000bdcf  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000bdd6  mov     edx, 117h; void *
0x18000bddb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000bde0  mov     r15d, eax
0x18000bde3  test    r15d, r15d
0x18000bde6  jns     loc_18000BD4D
0x18000bdec  mov     rcx, [rsp+58h]; this
0x18000bdf1  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18000bdf8  mov     r9d, r15d; char *
0x18000bdfb  mov     edx, 15DBh; void *
0x18000be00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000be05  test    rdi, rdi
0x18000be08  jz      short loc_18000BE12
0x18000be0a  mov     rcx, rdi; Block
0x18000be0d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000be12  mov     eax, r15d
0x18000be15  jmp     short loc_18000BE63
0x18000be17  cmp     [rsp+58h+TokenInformationLength], r12d
0x18000be1c  jnz     short loc_18000BE51
0x18000be1e  mov     rcx, [rsp+58h]; this
0x18000be23  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18000be2a  mov     r9d, 80070005h; char *
0x18000be30  mov     edx, 15E4h; void *
0x18000be35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000be3a  mov     rcx, rbx; Block
0x18000be3d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000be42  mov     rcx, rdi; Block
0x18000be45  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000be4a  mov     eax, 80070005h
0x18000be4f  jmp     short loc_18000BE63
0x18000be51  mov     rcx, rbx; Block
0x18000be54  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000be59  mov     rcx, rdi; Block
0x18000be5c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000be61  xor     eax, eax
0x18000be63  mov     r12, [rsp+58h+var_20]
0x18000be68  mov     rdi, [rsp+58h+var_18]
0x18000be6d  mov     rsi, [rsp+58h+arg_10]
0x18000be72  mov     rbx, [rsp+58h+arg_0]
0x18000be77  mov     r15, [rsp+58h+var_28]
0x18000be7c  add     rsp, 48h
0x18000be80  pop     r14
0x18000be82  pop     rbp
0x18000be83  retn
```
