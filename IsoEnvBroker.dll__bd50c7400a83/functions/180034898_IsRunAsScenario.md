# IsRunAsScenario

- ea: `0x180034898`
- end: `0x180034b1d`
- name: `IsRunAsScenario`
- size: `645`
- prototype: `char()`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180032e60`

## callees

- `0x180002a54`
- `0x180010240`
- `0x180011e18`
- `0x180013270`
- `0x180034898`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034903`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800349a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034a9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034903`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800349a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034a9c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034a26`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034a7c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034a26`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034a7c`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003491c`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180034984`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180034ab7`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180034ae8`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003491c`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180034984`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180034ab7`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180034ae8`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800348bb`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800348bb`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180034976`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180034976`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800349ef`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800349ef`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800348f9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800348f9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18003494c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18003494c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180034958`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180034958`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034a3e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034a94`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034a3e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034a94`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x18003499a`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x18003499a`

## string_xrefs

- `0x180034b0b`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x180034ad6`: `IsRunAsScenario: get_token_information(TOKEN_USER) failed: %#x`
- `0x18003490c`: `IsRunAsScenario: GetTokenInformation(SessionId) failed: %#x`
- `0x1800349b1`: `IsRunAsScenario: WTSQueryUserToken(%u) failed: %#x`
- `0x180034aa5`: `IsRunAsScenario: Failed to copy caller SID: %#x`
- `0x180034a4e`: `IsRunAsScenario: get_token_information for session token failed: %#x`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
char IsRunAsScenario()
{
  HRESULT v0; // eax
  DWORD LastError; // eax
  int token_information; // eax
  PSID *v3; // rbx
  SIZE_T LengthSid; // rdi
  HLOCAL v5; // rax
  void *v6; // rsi
  DWORD v7; // eax
  int v8; // eax
  void *v9; // rdi
  DWORD v11; // eax
  int ReturnLength; // [rsp+20h] [rbp-28h]
  void *v13; // [rsp+30h] [rbp-18h] BYREF
  HLOCAL v14; // [rsp+38h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+20h]
  void *Block; // [rsp+70h] [rbp+28h] BYREF
  ULONG TokenInformation; // [rsp+78h] [rbp+30h] BYREF
  DWORD v18; // [rsp+80h] [rbp+38h] BYREF
  void *phToken; // [rsp+88h] [rbp+40h] BYREF

  TokenInformation = 0;
  v14 = 0;
  v13 = 0;
  v0 = CoImpersonateClient();
  if ( v0 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x14AA,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      (const char *)(unsigned int)v0,
      ReturnLength);
  LOBYTE(Block) = 1;
  v18 = 0;
  if ( !GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFBLL, TokenSessionId, &TokenInformation, 4u, &v18) )
  {
    LastError = GetLastError();
    Log(2u, L"IsRunAsScenario: GetTokenInformation(SessionId) failed: %#x", LastError);
    CoRevertToSelf();
    return 1;
  }
  token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&v13, -5);
  v3 = (PSID *)v13;
  if ( token_information < 0 || !v13 )
  {
    Log(2u, L"IsRunAsScenario: get_token_information(TOKEN_USER) failed: %#x", (unsigned int)token_information);
    CoRevertToSelf();
    if ( v3 )
      operator delete(v3);
    return 1;
  }
  LengthSid = GetLengthSid(*(PSID *)v13);
  v5 = LocalAlloc(0, LengthSid);
  v6 = v5;
  v14 = v5;
  if ( !v5 || !CopySid(LengthSid, v5, *v3) )
  {
    v11 = GetLastError();
    Log(2u, L"IsRunAsScenario: Failed to copy caller SID: %#x", v11);
    CoRevertToSelf();
    if ( v3 )
      operator delete(v3);
    if ( !v6 )
      return 1;
    goto LABEL_28;
  }
  CoRevertToSelf();
  phToken = 0;
  if ( !WTSQueryUserToken(TokenInformation, &phToken) )
  {
    v7 = GetLastError();
    Log(2u, L"IsRunAsScenario: WTSQueryUserToken(%u) failed: %#x", TokenInformation, v7);
LABEL_24:
    if ( (char *)phToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(phToken);
    if ( v3 )
      operator delete(v3);
LABEL_28:
    LocalFree(v6);
    return 1;
  }
  Block = 0;
  v8 = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, phToken);
  v9 = Block;
  if ( v8 < 0 || !Block )
  {
    Log(2u, L"IsRunAsScenario: get_token_information for session token failed: %#x", (unsigned int)v8);
LABEL_22:
    if ( v9 )
      operator delete(v9);
    goto LABEL_24;
  }
  if ( !EqualSid(v6, *(PSID *)Block) )
  {
    Log(3u, aIsrunasscenari_1);
    goto LABEL_22;
  }
  if ( v9 )
    operator delete(v9);
  if ( (char *)phToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(phToken);
  if ( v3 )
    operator delete(v3);
  LocalFree(v6);
  return 0;
}

```

## disassembly

```asm
0x180034898  push    rbp
0x18003489a  push    rbx
0x18003489b  push    rsi
0x18003489c  push    rdi
0x18003489d  mov     rbp, rsp
0x1800348a0  sub     rsp, 48h
0x1800348a4  mov     [rbp+TokenInformation], 0
0x1800348ab  mov     [rbp+var_10], 0
0x1800348b3  mov     [rbp+var_18], 0
0x1800348bb  call    cs:__imp_CoImpersonateClient
0x1800348c1  mov     rcx, [rbp+20h]; this
0x1800348c5  test    eax, eax
0x1800348c7  js      loc_180034B08
0x1800348cd  mov     byte ptr [rbp+Block], 1
0x1800348d1  mov     [rbp+arg_10], 0
0x1800348d8  lea     rax, [rbp+arg_10]
0x1800348dc  mov     qword ptr [rsp+48h+ReturnLength], rax; ReturnLength
0x1800348e1  mov     r9d, 4; TokenInformationLength
0x1800348e7  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800348eb  lea     edx, [r9+8]; TokenInformationClass
0x1800348ef  mov     rbx, 0FFFFFFFFFFFFFFFBh
0x1800348f6  mov     rcx, rbx; TokenHandle
0x1800348f9  call    cs:__imp_GetTokenInformation
0x1800348ff  test    eax, eax
0x180034901  jnz     short loc_180034928
0x180034903  call    cs:__imp_GetLastError
0x180034909  mov     r8d, eax
0x18003490c  lea     rdx, aIsrunasscenari_3; "IsRunAsScenario: GetTokenInformation(Se"...
0x180034913  lea     ecx, [rbx+7]; unsigned __int8
0x180034916  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x18003491b  nop
0x18003491c  call    cs:__imp_CoRevertToSelf
0x180034922  nop
0x180034923  jmp     loc_180034AFD
0x180034928  mov     rdx, rbx
0x18003492b  lea     rcx, [rbp+var_18]
0x18003492f  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x180034934  mov     rbx, [rbp+var_18]
0x180034938  test    eax, eax
0x18003493a  js      loc_180034AD3
0x180034940  test    rbx, rbx
0x180034943  jz      loc_180034AD3
0x180034949  mov     rcx, [rbx]; pSid
0x18003494c  call    cs:__imp_GetLengthSid
0x180034952  mov     edi, eax
0x180034954  mov     edx, eax; uBytes
0x180034956  xor     ecx, ecx; uFlags
0x180034958  call    cs:__imp_LocalAlloc
0x18003495e  mov     rsi, rax
0x180034961  mov     [rbp+var_10], rax
0x180034965  test    rax, rax
0x180034968  jz      loc_180034A9C
0x18003496e  mov     r8, [rbx]; pSourceSid
0x180034971  mov     rdx, rax; pDestinationSid
0x180034974  mov     ecx, edi; nDestinationSidLength
0x180034976  call    cs:__imp_CopySid
0x18003497c  test    eax, eax
0x18003497e  jz      loc_180034A9C
0x180034984  call    cs:__imp_CoRevertToSelf
0x18003498a  nop
0x18003498b  mov     [rbp+phToken], 0
0x180034993  lea     rdx, [rbp+phToken]; phToken
0x180034997  mov     ecx, [rbp+TokenInformation]; SessionId
0x18003499a  call    cs:__imp_WTSQueryUserToken
0x1800349a0  test    eax, eax
0x1800349a2  jnz     short loc_1800349C7
0x1800349a4  call    cs:__imp_GetLastError
0x1800349aa  mov     r9d, eax
0x1800349ad  mov     r8d, [rbp+TokenInformation]
0x1800349b1  lea     rdx, aIsrunasscenari_0; "IsRunAsScenario: WTSQueryUserToken(%u) "...
0x1800349b8  mov     ecx, 2; unsigned __int8
0x1800349bd  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x1800349c2  jmp     loc_180034A6E
0x1800349c7  mov     [rbp+Block], 0
0x1800349cf  mov     rdx, [rbp+phToken]
0x1800349d3  lea     rcx, [rbp+Block]
0x1800349d7  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x1800349dc  mov     rdi, [rbp+Block]
0x1800349e0  test    eax, eax
0x1800349e2  js      short loc_180034A4B
0x1800349e4  test    rdi, rdi
0x1800349e7  jz      short loc_180034A4B
0x1800349e9  mov     rdx, [rdi]; pSid2
0x1800349ec  mov     rcx, rsi; pSid1
0x1800349ef  call    cs:__imp_EqualSid
0x1800349f5  test    eax, eax
0x1800349f7  jnz     short loc_180034A0A
0x1800349f9  lea     rdx, aIsrunasscenari_1; "IsRunAsScenario: RunAs detected "
0x180034a00  lea     ecx, [rax+3]; unsigned __int8
0x180034a03  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180034a08  jmp     short loc_180034A60
0x180034a0a  test    rdi, rdi
0x180034a0d  jz      short loc_180034A18
0x180034a0f  mov     rcx, rdi; Block
0x180034a12  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180034a17  nop
0x180034a18  mov     rcx, [rbp+phToken]; hObject
0x180034a1c  lea     rax, [rcx-1]
0x180034a20  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180034a24  ja      short loc_180034A2D
0x180034a26  call    cs:__imp_CloseHandle
0x180034a2c  nop
0x180034a2d  test    rbx, rbx
0x180034a30  jz      short loc_180034A3B
0x180034a32  mov     rcx, rbx; Block
0x180034a35  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180034a3a  nop
0x180034a3b  mov     rcx, rsi; hMem
0x180034a3e  call    cs:__imp_LocalFree
0x180034a44  xor     al, al
0x180034a46  jmp     loc_180034AFF
0x180034a4b  mov     r8d, eax
0x180034a4e  lea     rdx, aIsrunasscenari_2; "IsRunAsScenario: get_token_information "...
0x180034a55  mov     ecx, 2; unsigned __int8
0x180034a5a  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180034a5f  nop
0x180034a60  test    rdi, rdi
0x180034a63  jz      short loc_180034A6E
0x180034a65  mov     rcx, rdi; Block
0x180034a68  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180034a6d  nop
0x180034a6e  mov     rcx, [rbp+phToken]; hObject
0x180034a72  lea     rax, [rcx-1]
0x180034a76  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180034a7a  ja      short loc_180034A83
0x180034a7c  call    cs:__imp_CloseHandle
0x180034a82  nop
0x180034a83  test    rbx, rbx
0x180034a86  jz      short loc_180034A91
0x180034a88  mov     rcx, rbx; Block
0x180034a8b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180034a90  nop
0x180034a91  mov     rcx, rsi; hMem
0x180034a94  call    cs:__imp_LocalFree
0x180034a9a  jmp     short loc_180034AFD
0x180034a9c  call    cs:__imp_GetLastError
0x180034aa2  mov     r8d, eax
0x180034aa5  lea     rdx, aIsrunasscenari; "IsRunAsScenario: Failed to copy caller "...
0x180034aac  mov     ecx, 2; unsigned __int8
0x180034ab1  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180034ab6  nop
0x180034ab7  call    cs:__imp_CoRevertToSelf
0x180034abd  nop
0x180034abe  test    rbx, rbx
0x180034ac1  jz      short loc_180034ACC
0x180034ac3  mov     rcx, rbx; Block
0x180034ac6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180034acb  nop
0x180034acc  test    rsi, rsi
0x180034acf  jz      short loc_180034AFD
0x180034ad1  jmp     short loc_180034A91
0x180034ad3  mov     r8d, eax
0x180034ad6  lea     rdx, aIsrunasscenari_4; "IsRunAsScenario: get_token_information("...
0x180034add  mov     ecx, 2; unsigned __int8
0x180034ae2  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180034ae7  nop
0x180034ae8  call    cs:__imp_CoRevertToSelf
0x180034aee  nop
0x180034aef  test    rbx, rbx
0x180034af2  jz      short loc_180034AFD
0x180034af4  mov     rcx, rbx; Block
0x180034af7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180034afc  nop
0x180034afd  mov     al, 1
0x180034aff  add     rsp, 48h
0x180034b03  pop     rdi
0x180034b04  pop     rsi
0x180034b05  pop     rbx
0x180034b06  pop     rbp
0x180034b07  retn
0x180034b08  mov     r9d, eax; char *
0x180034b0b  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180034b12  mov     edx, 14AAh; void *
0x180034b17  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
