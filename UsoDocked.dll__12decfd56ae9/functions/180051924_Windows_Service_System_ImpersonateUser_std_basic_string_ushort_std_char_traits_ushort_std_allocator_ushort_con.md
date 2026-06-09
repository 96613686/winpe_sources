# Windows::Service::System::ImpersonateUser(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180051924`
- end: `0x180051aac`
- name: `?ImpersonateUser@System@Service@Windows@@UEAA?AV?$unique_ptr@VRevertToSelf@SystemInterface@@U?$default_delete@VRevertToSelf@SystemInterface@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@@Z`
- size: `392`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800460e0`

## callees

- `0x180007660`
- `0x180007dfc`
- `0x1800085a8`
- `0x18001ee04`
- `0x180023a18`
- `0x180024190`
- `0x180050304`
- `0x180050410`
- `0x180050e80`
- `0x180051808`
- `0x180051924`
- `0x180053dc8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051a1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051a1f`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800519fb`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800519fb`

## string_xrefs

- `0x180051a76`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\servicesystem.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall Windows::Service::System::ImpersonateUser(__int64 a1, _QWORD *a2, __int64 a3)
{
  char **v5; // rdi
  char **v6; // r12
  size_t v7; // r14
  const wchar_t *v8; // rdx
  size_t v9; // r15
  const wchar_t *v10; // rcx
  size_t v11; // r8
  char *v12; // rbx
  char *v13; // rax
  const char *v14; // r9
  _QWORD *v15; // rax
  _QWORD pExceptionObject[4]; // [rsp+28h] [rbp-48h] BYREF
  wchar_t *S1[2]; // [rsp+48h] [rbp-28h] BYREF
  size_t v19; // [rsp+58h] [rbp-18h]
  unsigned __int64 v20; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  Windows::UserMgrHelpers::GetAllSessionUserTokens(pExceptionObject);
  v5 = (char **)pExceptionObject[0];
  v6 = (char **)pExceptionObject[1];
  while ( 1 )
  {
    if ( v5 == v6 )
    {
      v12 = 0;
      std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~vector<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(pExceptionObject);
      v13 = 0;
      goto LABEL_15;
    }
    Windows::UserMgrHelpers::GetUserSidStringFromToken(S1, *v5);
    v7 = *(_QWORD *)(a3 + 16);
    if ( *(_QWORD *)(a3 + 24) <= 7u )
      v8 = (const wchar_t *)a3;
    else
      v8 = *(const wchar_t **)a3;
    v9 = v19;
    v10 = (const wchar_t *)S1;
    if ( v20 > 7 )
      v10 = S1[0];
    v11 = v19;
    if ( v7 < v19 )
      v11 = *(_QWORD *)(a3 + 16);
    if ( !wmemcmp(v10, v8, v11) && v9 >= v7 && v9 <= v7 )
      break;
    std::wstring::_Tidy_deallocate(S1);
    ++v5;
  }
  v12 = *v5;
  *v5 = 0;
  std::wstring::_Tidy_deallocate(S1);
  std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~vector<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(pExceptionObject);
  v13 = v12;
LABEL_15:
  if ( (unsigned __int64)(v13 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    std::out_of_range::out_of_range((std::out_of_range *)pExceptionObject, "User identifier not found");
    throw (std::out_of_range *)pExceptionObject;
  }
  Windows::AdjustProcessPrivilege(29, 1u);
  if ( !ImpersonateLoggedOnUser(v12) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xDF,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\servicesystem.cpp",
      v14);
  v15 = operator new(8u);
  *v15 = &Windows::RevertToSelf::`vftable';
  *a2 = v15;
  CloseHandle(v12);
  return a2;
}

```

## disassembly

```asm
0x180051924  mov     [rsp-28h+arg_0], rbx
0x180051929  mov     [rsp-28h+arg_18], rsi
0x18005192e  push    rbp
0x18005192f  push    rdi
0x180051930  push    r12
0x180051932  push    r14
0x180051934  push    r15
0x180051936  mov     rbp, rsp
0x180051939  sub     rsp, 70h
0x18005193d  mov     rax, cs:__security_cookie
0x180051944  xor     rax, rsp
0x180051947  mov     [rbp+var_8], rax
0x18005194b  mov     rbx, r8
0x18005194e  mov     rsi, rdx
0x180051951  mov     [rbp+var_50], rdx
0x180051955  lea     rcx, [rbp+pExceptionObject]
0x180051959  call    ?GetAllSessionUserTokens@UserMgrHelpers@Windows@@YA?AV?$vector@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@@std@@XZ; Windows::UserMgrHelpers::GetAllSessionUserTokens(void)
0x18005195e  nop
0x18005195f  mov     rdi, [rbp+pExceptionObject]
0x180051963  mov     r12, [rbp+var_40]
0x180051967  jmp     short loc_1800519C5
0x180051969  mov     rdx, [rdi]
0x18005196c  lea     rcx, [rbp+S1]
0x180051970  call    ?GetUserSidStringFromToken@UserMgrHelpers@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; Windows::UserMgrHelpers::GetUserSidStringFromToken(void *)
0x180051975  mov     r14, [rbx+10h]
0x180051979  cmp     qword ptr [rbx+18h], 7
0x18005197e  jbe     short loc_180051985
0x180051980  mov     rdx, [rbx]
0x180051983  jmp     short loc_180051988
0x180051985  mov     rdx, rbx; S2
0x180051988  mov     r15, [rbp+var_18]
0x18005198c  lea     rcx, [rbp+S1]
0x180051990  cmp     [rbp+var_10], 7
0x180051995  cmova   rcx, [rbp+S1]; S1
0x18005199a  mov     r8, r15
0x18005199d  cmp     r14, r15
0x1800519a0  cmovb   r8, r14; N
0x1800519a4  call    wmemcmp
0x1800519a9  test    eax, eax
0x1800519ab  jnz     short loc_1800519B8
0x1800519ad  cmp     r15, r14
0x1800519b0  jb      short loc_1800519B8
0x1800519b2  jbe     loc_180051A4D
0x1800519b8  lea     rcx, [rbp+S1]
0x1800519bc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800519c1  add     rdi, 8
0x1800519c5  cmp     rdi, r12
0x1800519c8  jnz     short loc_180051969
0x1800519ca  xor     ebx, ebx
0x1800519cc  mov     [rbp+var_50], rbx
0x1800519d0  lea     rcx, [rbp+pExceptionObject]
0x1800519d4  call    ??1?$vector@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~vector<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x1800519d9  xor     eax, eax
0x1800519db  dec     rax
0x1800519de  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800519e2  ja      loc_180051A8B
0x1800519e8  mov     dl, 1; bool
0x1800519ea  mov     ecx, 1Dh; unsigned int
0x1800519ef  call    ?AdjustProcessPrivilege@Windows@@YAXK_N@Z; Windows::AdjustProcessPrivilege(ulong,bool)
0x1800519f4  mov     rdi, [rbp+28h]
0x1800519f8  mov     rcx, rbx; hToken
0x1800519fb  call    cs:__imp_ImpersonateLoggedOnUser
0x180051a01  test    eax, eax
0x180051a03  jz      short loc_180051A76
0x180051a05  mov     ecx, 8; Size
0x180051a0a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180051a0f  lea     rcx, ??_7RevertToSelf@Windows@@6B@; const Windows::RevertToSelf::`vftable'
0x180051a16  mov     [rax], rcx
0x180051a19  mov     [rsi], rax
0x180051a1c  mov     rcx, rbx; hObject
0x180051a1f  call    cs:__imp_CloseHandle
0x180051a25  mov     rax, rsi
0x180051a28  mov     rcx, [rbp+var_8]
0x180051a2c  xor     rcx, rsp; StackCookie
0x180051a2f  call    __security_check_cookie
0x180051a34  lea     r11, [rsp+70h+var_s0]
0x180051a39  mov     rbx, [r11+30h]
0x180051a3d  mov     rsi, [r11+48h]
0x180051a41  mov     rsp, r11
0x180051a44  pop     r15
0x180051a46  pop     r14
0x180051a48  pop     r12
0x180051a4a  pop     rdi
0x180051a4b  pop     rbp
0x180051a4c  retn
0x180051a4d  mov     rbx, [rdi]
0x180051a50  mov     [rbp+var_50], rbx
0x180051a54  mov     qword ptr [rdi], 0
0x180051a5b  lea     rcx, [rbp+S1]
0x180051a5f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180051a64  nop
0x180051a65  lea     rcx, [rbp+pExceptionObject]
0x180051a69  call    ??1?$vector@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~vector<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x180051a6e  mov     rax, rbx
0x180051a71  jmp     loc_1800519DB
0x180051a76  lea     r8, aOnecoreEnduser_17; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180051a7d  mov     edx, 0DFh; void *
0x180051a82  mov     rcx, rdi; this
0x180051a85  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180051a8b  lea     rdx, aUserIdentifier; "User identifier not found"
0x180051a92  lea     rcx, [rbp+pExceptionObject]; this
0x180051a96  call    ??0out_of_range@std@@QEAA@PEBD@Z; std::out_of_range::out_of_range(char const *)
0x180051a9b  lea     rdx, _TI3?AVout_of_range@std@@; pThrowInfo
0x180051aa2  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180051aa6  call    _CxxThrowException_0
```
