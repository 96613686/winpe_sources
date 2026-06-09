# PrintCore::UserImpersonationHelpers::GetUserSidFromSessionId(ulong)

- ea: `0x180028624`
- end: `0x180028752`
- name: `?GetUserSidFromSessionId@UserImpersonationHelpers@PrintCore@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z`
- size: `302`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002b44c`

## callees

- `0x18000f760`
- `0x18001255c`
- `0x18001cf40`
- `0x18001cfd4`
- `0x18001d058`
- `0x180023264`
- `0x180028624`
- `0x180028758`

## import_xrefs

- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x1800286b0`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x1800286b0`

## string_xrefs

- `0x180028683`: `OneCoreUap\Internal\Printscan\inc\UserImpersonationHelpers.h`
- `0x1800286d0`: `OneCoreUap\Internal\Printscan\inc\UserImpersonationHelpers.h`
- `0x180028702`: `OneCoreUap\Internal\Printscan\inc\UserImpersonationHelpers.h`
- `0x1800286c0`: `WTSQueryUserToken failed!`
- `0x1800286f3`: `Failed to retrieve the user SID from the token!`
- `0x18002872c`: `PrintCore::UserImpersonationHelpers::GetUserSidFromSessionId`
- `0x180028725`: `Got SID: %ws for sessionId 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall PrintCore::UserImpersonationHelpers::GetUserSidFromSessionId(_QWORD *a1, ULONG a2)
{
  BOOL v4; // eax
  unsigned int UserSidFromToken; // eax
  _QWORD *v6; // r8
  char *v8; // [rsp+28h] [rbp-20h]
  char *v9; // [rsp+28h] [rbp-20h]
  char *v10; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  void *phToken; // [rsp+60h] [rbp+18h] BYREF

  *(_OWORD *)a1 = 0;
  a1[2] = 0;
  a1[3] = 7;
  *(_WORD *)a1 = 0;
  LODWORD(v10) = 1;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0xDD,
    (unsigned int)"OneCoreUap\\Internal\\Printscan\\inc\\UserImpersonationHelpers.h",
    (const char *)0x80070057LL,
    a2 == 0,
    (bool)"Session Id cannot be 0!",
    v10);
  phToken = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &phToken,
    0);
  v4 = WTSQueryUserToken(a2, &phToken);
  wil::details::in1diag3::Throw_GetLastErrorIfFalseMsg(
    retaddr,
    (void *)0xE1,
    (unsigned int)"OneCoreUap\\Internal\\Printscan\\inc\\UserImpersonationHelpers.h",
    (const char *)v4,
    (bool)"WTSQueryUserToken failed!",
    v8);
  UserSidFromToken = PrintCore::TokenHelpers::GetUserSidFromToken(phToken, a1);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0xE4,
    (unsigned int)"OneCoreUap\\Internal\\Printscan\\inc\\UserImpersonationHelpers.h",
    (const char *)UserSidFromToken,
    (int)"Failed to retrieve the user SID from the token!",
    v9);
  if ( a1[3] <= 7u )
    v6 = a1;
  else
    v6 = (_QWORD *)*a1;
  PrintScanBrokerTelemetry::WriteDbgTraceInfo(
    "PrintCore::UserImpersonationHelpers::GetUserSidFromSessionId",
    L"Got SID: %ws for sessionId 0x%x",
    v6,
    a2);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phToken);
  return a1;
}

```

## disassembly

```asm
0x180028624  mov     [rsp+arg_8], rbx
0x180028629  mov     [rsp+arg_0], rcx
0x18002862e  push    rdi
0x18002862f  sub     rsp, 40h
0x180028633  mov     edi, edx
0x180028635  mov     rbx, rcx
0x180028638  mov     dword ptr [rsp+48h+var_18], 0
0x180028640  xorps   xmm0, xmm0
0x180028643  movups  xmmword ptr [rcx], xmm0
0x180028646  mov     qword ptr [rcx+10h], 0
0x18002864e  mov     qword ptr [rcx+18h], 7
0x180028656  xor     eax, eax
0x180028658  mov     [rcx], ax
0x18002865b  mov     dword ptr [rsp+48h+var_18], 1; char *
0x180028663  test    edx, edx
0x180028665  setz    al
0x180028668  mov     rcx, [rsp+48h]; this
0x18002866d  lea     rdx, aSessionIdCanno; "Session Id cannot be 0!"
0x180028674  mov     [rsp+48h+var_20], rdx; char *
0x180028679  mov     [rsp+48h+var_28], al; char
0x18002867d  mov     r9d, 80070057h; char *
0x180028683  lea     r8, aOnecoreuapInte_7; "OneCoreUap\\Internal\\Printscan\\inc\\U"...
0x18002868a  mov     edx, 0DDh; void *
0x18002868f  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180028694  mov     [rsp+48h+phToken], 0
0x18002869d  xor     edx, edx
0x18002869f  lea     rcx, [rsp+48h+phToken]
0x1800286a4  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800286a9  lea     rdx, [rsp+48h+phToken]; phToken
0x1800286ae  mov     ecx, edi; SessionId
0x1800286b0  call    cs:__imp_WTSQueryUserToken
0x1800286b6  test    eax, eax
0x1800286b8  setnz   al
0x1800286bb  mov     rcx, [rsp+48h]; this
0x1800286c0  lea     rdx, aWtsqueryuserto_0; "WTSQueryUserToken failed!"
0x1800286c7  mov     qword ptr [rsp+48h+var_28], rdx; bool
0x1800286cc  movzx   r9d, al; char *
0x1800286d0  lea     r8, aOnecoreuapInte_7; "OneCoreUap\\Internal\\Printscan\\inc\\U"...
0x1800286d7  mov     edx, 0E1h; void *
0x1800286dc  call    ?Throw_GetLastErrorIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfFalseMsg(void *,uint,char const *,bool,char const *,...)
0x1800286e1  mov     rdx, rbx
0x1800286e4  mov     rcx, [rsp+48h+phToken]; TokenHandle
0x1800286e9  call    ?GetUserSidFromToken@TokenHelpers@PrintCore@@SAJPEAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PrintCore::TokenHelpers::GetUserSidFromToken(void *,std::wstring &)
0x1800286ee  mov     rcx, [rsp+48h]; this
0x1800286f3  lea     rdx, aFailedToRetrie; "Failed to retrieve the user SID from th"...
0x1800286fa  mov     qword ptr [rsp+48h+var_28], rdx; int
0x1800286ff  mov     r9d, eax; char *
0x180028702  lea     r8, aOnecoreuapInte_7; "OneCoreUap\\Internal\\Printscan\\inc\\U"...
0x180028709  mov     edx, 0E4h; void *
0x18002870e  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180028713  cmp     qword ptr [rbx+18h], 7
0x180028718  jbe     short loc_18002871F
0x18002871a  mov     r8, [rbx]
0x18002871d  jmp     short loc_180028722
0x18002871f  mov     r8, rbx
0x180028722  mov     r9d, edi
0x180028725  lea     rdx, aGotSidWsForSes; "Got SID: %ws for sessionId 0x%x"
0x18002872c  lea     rcx, aPrintcoreUseri; "PrintCore::UserImpersonationHelpers::Ge"...
0x180028733  call    ?WriteDbgTraceInfo@PrintScanBrokerTelemetry@@SAXPEADPEAGZZ; PrintScanBrokerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180028738  nop
0x180028739  lea     rcx, [rsp+48h+phToken]
0x18002873e  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180028743  mov     rax, rbx
0x180028746  mov     rbx, [rsp+48h+arg_8]
0x18002874b  add     rsp, 40h
0x18002874f  pop     rdi
0x180028750  retn
```
