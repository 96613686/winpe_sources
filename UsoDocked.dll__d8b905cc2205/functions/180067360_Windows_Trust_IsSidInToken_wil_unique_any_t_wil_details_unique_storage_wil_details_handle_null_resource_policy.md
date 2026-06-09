# Windows::Trust::IsSidInToken(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> const &)

- ea: `0x180067360`
- end: `0x1800674c5`
- name: `?IsSidInToken@Trust@Windows@@YA_NAEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@4@@Z`
- size: `357`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180053454`
- `0x180055614`

## callees

- `0x180023a18`
- `0x180067360`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067437`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067437`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800673af`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800673af`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800673f0`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800673f0`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180067414`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180067452`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180067414`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180067452`

## string_xrefs

- `0x180067474`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\common\trust.cpp`
- `0x180067486`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\common\trust.cpp`
- `0x18006749b`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\common\trust.cpp`
- `0x1800674b0`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\common\trust.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall Windows::Trust::IsSidInToken(HANDLE *a1, PSID *a2)
{
  char *v4; // rcx
  const char *v5; // r9
  const char *v6; // r9
  const char *v7; // r9
  bool v8; // bl
  const char *v10; // r9
  DWORD ReturnLength; // [rsp+30h] [rbp-10h] BYREF
  HANDLE TokenHandle; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  int TokenInformation; // [rsp+60h] [rbp+20h] BYREF
  WINBOOL IsMember; // [rsp+70h] [rbp+30h] BYREF
  WINBOOL v16; // [rsp+78h] [rbp+38h] BYREF

  v4 = (char *)*a1;
  if ( (unsigned __int64)(v4 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    goto LABEL_9;
  ReturnLength = 0;
  TokenInformation = 1;
  if ( !GetTokenInformation(v4, TokenType, &TokenInformation, 4u, &ReturnLength) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xED,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\common\\trust.cpp",
      v5);
  if ( TokenInformation == 2 )
  {
LABEL_9:
    v16 = 0;
    if ( !CheckTokenMembership(*a1, *a2, &v16) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x102,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\common\\trust.cpp",
        v10);
    return v16 != 0;
  }
  else
  {
    TokenHandle = 0;
    if ( !DuplicateTokenEx(*a1, 8u, 0, SecurityIdentification, TokenImpersonation, &TokenHandle) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xF8,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\common\\trust.cpp",
        v6);
    IsMember = 0;
    if ( !CheckTokenMembership(TokenHandle, *a2, &IsMember) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xFB,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\common\\trust.cpp",
        v7);
    v8 = IsMember != 0;
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    return v8;
  }
}

```

## disassembly

```asm
0x180067360  mov     [rsp-18h+arg_8], rbx
0x180067365  push    rbp
0x180067366  push    rsi
0x180067367  push    rdi
0x180067368  mov     rbp, rsp
0x18006736b  sub     rsp, 40h
0x18006736f  mov     rdi, rdx
0x180067372  mov     rbx, rcx
0x180067375  mov     rcx, [rcx]; TokenHandle
0x180067378  lea     rax, [rcx-1]
0x18006737c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180067380  ja      loc_180067441
0x180067386  mov     [rbp+var_10], 0
0x18006738d  mov     [rbp+TokenInformation], 1
0x180067394  mov     rsi, [rbp+18h]
0x180067398  lea     rax, [rbp+var_10]
0x18006739c  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x1800673a1  mov     r9d, 4; TokenInformationLength
0x1800673a7  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800673ab  lea     edx, [r9+4]; TokenInformationClass
0x1800673af  call    cs:__imp_GetTokenInformation
0x1800673b5  test    eax, eax
0x1800673b7  jz      loc_180067486
0x1800673bd  cmp     [rbp+TokenInformation], 2
0x1800673c1  jz      short loc_180067441
0x1800673c3  mov     [rbp+TokenHandle], 0
0x1800673cb  mov     rsi, [rbp+18h]
0x1800673cf  lea     rax, [rbp+TokenHandle]
0x1800673d3  mov     [rsp+40h+phNewToken], rax; phNewToken
0x1800673d8  mov     dword ptr [rsp+40h+ReturnLength], 2; TokenType
0x1800673e0  mov     r9d, 1; ImpersonationLevel
0x1800673e6  xor     r8d, r8d; lpTokenAttributes
0x1800673e9  lea     edx, [r9+7]; dwDesiredAccess
0x1800673ed  mov     rcx, [rbx]; hExistingToken
0x1800673f0  call    cs:__imp_DuplicateTokenEx
0x1800673f6  test    eax, eax
0x1800673f8  jz      loc_18006749B
0x1800673fe  mov     [rbp+IsMember], 0
0x180067405  mov     rbx, [rbp+18h]
0x180067409  lea     r8, [rbp+IsMember]; IsMember
0x18006740d  mov     rdx, [rdi]; SidToCheck
0x180067410  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180067414  call    cs:__imp_CheckTokenMembership
0x18006741a  test    eax, eax
0x18006741c  jz      loc_1800674B0
0x180067422  cmp     [rbp+IsMember], 0
0x180067426  setnz   bl
0x180067429  mov     rcx, [rbp+TokenHandle]; hObject
0x18006742d  lea     rdx, [rcx-1]
0x180067431  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180067435  ja      short loc_18006743D
0x180067437  call    cs:__imp_CloseHandle
0x18006743d  mov     al, bl
0x18006743f  jmp     short loc_180067463
0x180067441  mov     [rbp+arg_18], 0
0x180067448  lea     r8, [rbp+arg_18]; IsMember
0x18006744c  mov     rdx, [rdi]; SidToCheck
0x18006744f  mov     rcx, [rbx]; TokenHandle
0x180067452  call    cs:__imp_CheckTokenMembership
0x180067458  test    eax, eax
0x18006745a  jz      short loc_180067470
0x18006745c  cmp     [rbp+arg_18], 0
0x180067460  setnz   al
0x180067463  mov     rbx, [rsp+40h+arg_8]
0x180067468  add     rsp, 40h
0x18006746c  pop     rdi
0x18006746d  pop     rsi
0x18006746e  pop     rbp
0x18006746f  retn
0x180067470  mov     rcx, [rbp+18h]; this
0x180067474  lea     r8, aOnecoreEnduser_7; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18006747b  mov     edx, 102h; void *
0x180067480  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180067486  lea     r8, aOnecoreEnduser_7; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18006748d  mov     edx, 0EDh; void *
0x180067492  mov     rcx, rsi; this
0x180067495  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18006749b  lea     r8, aOnecoreEnduser_7; "onecore\\enduser\\windowsupdate\\muse\\"...
0x1800674a2  mov     edx, 0F8h; void *
0x1800674a7  mov     rcx, rsi; this
0x1800674aa  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800674b0  lea     r8, aOnecoreEnduser_7; "onecore\\enduser\\windowsupdate\\muse\\"...
0x1800674b7  mov     edx, 0FBh; void *
0x1800674bc  mov     rcx, rbx; this
0x1800674bf  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
