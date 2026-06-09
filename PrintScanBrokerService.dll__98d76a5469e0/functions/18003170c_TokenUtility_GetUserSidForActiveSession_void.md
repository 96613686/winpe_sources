# TokenUtility::GetUserSidForActiveSession(void)

- ea: `0x18003170c`
- end: `0x1800317b6`
- name: `?GetUserSidForActiveSession@TokenUtility@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `170`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001290c`
- `0x1800296a0`

## callees

- `0x18001d058`
- `0x18003161c`
- `0x180031d24`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800317a6`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800317a6`

## string_xrefs

- `0x18003173f`: `onecoreuap\printscan\print\printscanbroker\class\tokenutility.cpp`
- `0x180031794`: `onecoreuap\printscan\print\printscanbroker\class\tokenutility.cpp`
- `0x180031785`: `GetUserSid failed!`
- `0x180031730`: `ImpersonateActiveUser failed!`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall TokenUtility::GetUserSidForActiveSession(__int64 a1, _QWORD *a2)
{
  unsigned int active; // eax
  unsigned int UserSid; // eax
  const char *v6; // [rsp+28h] [rbp-20h]
  const char *v7; // [rsp+28h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  active = PrintCore::UserImpersonationHelpers::ImpersonateActiveUser();
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0xBC,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\tokenutility.cpp",
    (const char *)active,
    (int)"ImpersonateActiveUser failed!",
    v6);
  *(_OWORD *)a2 = 0;
  a2[2] = 0;
  a2[3] = 7;
  *(_WORD *)a2 = 0;
  UserSid = PrintCore::TokenHelpers::GetUserSid(a2);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0xC3,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\tokenutility.cpp",
    (const char *)UserSid,
    (int)"GetUserSid failed!",
    v7);
  RevertToSelf();
  return a2;
}

```

## disassembly

```asm
0x18003170c  mov     [rsp+arg_8], rdx
0x180031711  mov     [rsp+arg_0], rcx
0x180031716  push    rbx
0x180031717  sub     rsp, 40h
0x18003171b  mov     rbx, rdx
0x18003171e  mov     [rsp+48h+var_18], 0
0x180031726  call    ?ImpersonateActiveUser@UserImpersonationHelpers@PrintCore@@SAJXZ; PrintCore::UserImpersonationHelpers::ImpersonateActiveUser(void)
0x18003172b  mov     rcx, [rsp+48h]; this
0x180031730  lea     rdx, aImpersonateact; "ImpersonateActiveUser failed!"
0x180031737  mov     qword ptr [rsp+48h+var_28], rdx; int
0x18003173c  mov     r9d, eax; char *
0x18003173f  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\printscan"...
0x180031746  mov     edx, 0BCh; void *
0x18003174b  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180031750  mov     byte ptr [rsp+48h+arg_0+1], 1
0x180031755  xorps   xmm0, xmm0
0x180031758  movups  xmmword ptr [rbx], xmm0
0x18003175b  mov     qword ptr [rbx+10h], 0
0x180031763  mov     qword ptr [rbx+18h], 7
0x18003176b  xor     eax, eax
0x18003176d  mov     [rbx], ax
0x180031770  mov     [rsp+48h+var_18], 1
0x180031778  mov     rcx, rbx
0x18003177b  call    ?GetUserSid@TokenHelpers@PrintCore@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PrintCore::TokenHelpers::GetUserSid(std::wstring &)
0x180031780  mov     rcx, [rsp+48h]; this
0x180031785  lea     rdx, aGetusersidFail; "GetUserSid failed!"
0x18003178c  mov     qword ptr [rsp+48h+var_28], rdx; int
0x180031791  mov     r9d, eax; char *
0x180031794  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\printscan"...
0x18003179b  mov     edx, 0C3h; void *
0x1800317a0  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800317a5  nop
0x1800317a6  call    cs:__imp_RevertToSelf
0x1800317ac  mov     rax, rbx
0x1800317af  add     rsp, 40h
0x1800317b3  pop     rbx
0x1800317b4  retn
```
