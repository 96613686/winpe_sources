# ADPApisCommon::CallerIdentityHelpers::GetCallerUserId(void)

- ea: `0x180018764`
- end: `0x180018949`
- name: `?GetCallerUserId@CallerIdentityHelpers@ADPApisCommon@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@XZ`
- size: `485`
- prototype: `LPWSTR *__fastcall(LPWSTR *StringSid)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180013180`
- `0x180017c78`

## callees

- `0x180002ba0`
- `0x180003400`
- `0x180005290`
- `0x180006824`
- `0x180006844`
- `0x18000771c`
- `0x18000f1b8`
- `0x180018764`
- `0x180018950`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800187ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800187ce`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18001877b`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18001877b`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800188c7`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800188c7`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001889a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001889a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800187c0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180018830`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800187c0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180018830`

## string_xrefs

- `0x180018913`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x1800188e9`: `onecoreuap\base\appmodel\aggregateddataplatform\service\dataaggregators\aggregatorscommon\calleridentityhelpers.cpp`
- `0x1800188fe`: `onecoreuap\base\appmodel\aggregateddataplatform\service\dataaggregators\aggregatorscommon\calleridentityhelpers.cpp`
- `0x180018925`: `onecoreuap\base\appmodel\aggregateddataplatform\service\dataaggregators\aggregatorscommon\calleridentityhelpers.cpp`
- `0x180018937`: `onecoreuap\base\appmodel\aggregateddataplatform\service\dataaggregators\aggregatorscommon\calleridentityhelpers.cpp`
- `0x180018802`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x18001883f`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x18001886d`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
LPWSTR *__fastcall ADPApisCommon::CallerIdentityHelpers::GetCallerUserId(LPWSTR *StringSid)
{
  HRESULT v2; // eax
  PSID *v3; // rdi
  const char *v4; // r9
  PSID *v5; // rbp
  int LastError; // ebx
  const char *v7; // r9
  const char *v8; // r9
  HRESULT v9; // eax
  int ReturnLength; // [rsp+20h] [rbp-38h]
  int ReturnLengtha; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  DWORD TokenInformationLength; // [rsp+70h] [rbp+18h] BYREF
  PSID *v15; // [rsp+78h] [rbp+20h]

  v2 = CoImpersonateClient();
  if ( v2 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0xA,
      (unsigned int)"onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\dataaggregators\\aggregatorscommon\\cal"
                    "leridentityhelpers.cpp",
      (const char *)(unsigned int)v2,
      ReturnLength);
  v3 = 0;
  v15 = 0;
  TokenInformationLength = 0;
  if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenUser, 0, 0, &TokenInformationLength)
    || GetLastError() != 122 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x117,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
                  v4);
  }
  else
  {
    v5 = (PSID *)operator new(TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
    if ( v5 )
    {
      if ( GetTokenInformation(
             (HANDLE)0xFFFFFFFFFFFFFFFALL,
             TokenUser,
             v5,
             TokenInformationLength,
             &TokenInformationLength) )
      {
        v3 = v5;
        v15 = v5;
        LastError = 0;
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x11A,
                      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
                      v7);
        operator delete(v5);
      }
    }
    else
    {
      LastError = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x119,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
        (const char *)0x8007000ELL,
        ReturnLengtha);
    }
  }
  if ( LastError < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)LastError,
      ReturnLengtha);
  *StringSid = 0;
  if ( !ConvertSidToStringSidW(*v3, StringSid) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x12,
      (unsigned int)"onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\dataaggregators\\aggregatorscommon\\cal"
                    "leridentityhelpers.cpp",
      v8);
  if ( !*StringSid )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x13,
      (unsigned int)"onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\dataaggregators\\aggregatorscommon\\cal"
                    "leridentityhelpers.cpp",
      v8);
  if ( v3 )
    operator delete(v3);
  v9 = CoRevertToSelf();
  if ( v9 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0xC,
      (unsigned int)"onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\dataaggregators\\aggregatorscommon\\cal"
                    "leridentityhelpers.cpp",
      (const char *)(unsigned int)v9,
      ReturnLengtha);
  return StringSid;
}

```

## disassembly

```asm
0x180018764  mov     [rsp+arg_0], rbx
0x180018769  push    rbp
0x18001876a  push    rsi
0x18001876b  push    rdi
0x18001876c  sub     rsp, 40h
0x180018770  mov     rsi, rcx
0x180018773  mov     [rsp+58h+var_28], 0
0x18001877b  call    cs:__imp_CoImpersonateClient
0x180018781  mov     rcx, [rsp+58h]; this
0x180018786  test    eax, eax
0x180018788  js      loc_1800188FB
0x18001878e  mov     ebx, 1
0x180018793  mov     [rsp+58h+arg_9], bl
0x180018797  mov     [rsp+58h+var_28], 8
0x18001879f  xor     edi, edi
0x1800187a1  mov     [rsp+58h+arg_18], rdi
0x1800187a6  mov     [rsp+58h+TokenInformationLength], edi
0x1800187aa  lea     rax, [rsp+58h+TokenInformationLength]
0x1800187af  mov     qword ptr [rsp+58h+ReturnLength], rax; int
0x1800187b4  xor     r9d, r9d; TokenInformationLength
0x1800187b7  xor     r8d, r8d; TokenInformation
0x1800187ba  mov     edx, ebx; TokenInformationClass
0x1800187bc  lea     rcx, [rdi-6]; TokenHandle
0x1800187c0  call    cs:__imp_GetTokenInformation
0x1800187c6  test    eax, eax
0x1800187c8  jnz     loc_180018868
0x1800187ce  call    cs:__imp_GetLastError
0x1800187d4  cmp     eax, 7Ah ; 'z'
0x1800187d7  jnz     loc_180018868
0x1800187dd  mov     ecx, [rsp+58h+TokenInformationLength]; unsigned __int64
0x1800187e1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800187e8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800187ed  mov     rbp, rax
0x1800187f0  test    rax, rax
0x1800187f3  jnz     short loc_180018815
0x1800187f5  mov     rcx, [rsp+58h]; this
0x1800187fa  mov     ebx, 8007000Eh
0x1800187ff  mov     r9d, ebx; char *
0x180018802  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180018809  mov     edx, 119h; void *
0x18001880e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018813  jmp     short loc_180018880
0x180018815  lea     rax, [rsp+58h+TokenInformationLength]
0x18001881a  mov     qword ptr [rsp+58h+ReturnLength], rax; ReturnLength
0x18001881f  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x180018824  mov     r8, rbp; TokenInformation
0x180018827  mov     edx, ebx; TokenInformationClass
0x180018829  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x180018830  call    cs:__imp_GetTokenInformation
0x180018836  test    eax, eax
0x180018838  jnz     short loc_18001885C
0x18001883a  mov     rcx, [rsp+58h]; this
0x18001883f  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180018846  mov     edx, 11Ah; void *
0x18001884b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180018850  mov     ebx, eax
0x180018852  mov     rcx, rbp; Block
0x180018855  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001885a  jmp     short loc_180018880
0x18001885c  mov     rdi, rbp
0x18001885f  mov     [rsp+58h+arg_18], rbp
0x180018864  xor     ebx, ebx
0x180018866  jmp     short loc_180018880
0x180018868  mov     rcx, [rsp+58h]; this
0x18001886d  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180018874  mov     edx, 117h; void *
0x180018879  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001887e  mov     ebx, eax
0x180018880  mov     rcx, [rsp+58h]; this
0x180018885  test    ebx, ebx
0x180018887  js      loc_180018910
0x18001888d  mov     qword ptr [rsi], 0
0x180018894  mov     rdx, rsi; StringSid
0x180018897  mov     rcx, [rdi]; Sid
0x18001889a  call    cs:__imp_ConvertSidToStringSidW
0x1800188a0  mov     rcx, [rsp+58h]; this
0x1800188a5  test    eax, eax
0x1800188a7  jz      short loc_180018925
0x1800188a9  cmp     qword ptr [rsi], 0
0x1800188ad  setz    al
0x1800188b0  mov     rcx, [rsp+58h]; this
0x1800188b5  test    al, al
0x1800188b7  jnz     short loc_180018937
0x1800188b9  test    rdi, rdi
0x1800188bc  jz      short loc_1800188C7
0x1800188be  mov     rcx, rdi; Block
0x1800188c1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800188c6  nop
0x1800188c7  call    cs:__imp_CoRevertToSelf
0x1800188cd  test    eax, eax
0x1800188cf  js      short loc_1800188E1
0x1800188d1  mov     rax, rsi
0x1800188d4  mov     rbx, [rsp+58h+arg_0]
0x1800188d9  add     rsp, 40h
0x1800188dd  pop     rdi
0x1800188de  pop     rsi
0x1800188df  pop     rbp
0x1800188e0  retn
0x1800188e1  mov     rcx, [rsp+58h]; this
0x1800188e6  mov     r9d, eax; char *
0x1800188e9  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x1800188f0  mov     edx, 0Ch; void *
0x1800188f5  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800188fb  mov     r9d, eax; char *
0x1800188fe  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x180018905  mov     edx, 0Ah; void *
0x18001890a  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180018910  mov     r9d, ebx; char *
0x180018913  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001891a  mov     edx, 1CBEh; void *
0x18001891f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180018925  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x18001892c  mov     edx, 12h; void *
0x180018931  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180018937  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x18001893e  mov     edx, 13h; void *
0x180018943  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
