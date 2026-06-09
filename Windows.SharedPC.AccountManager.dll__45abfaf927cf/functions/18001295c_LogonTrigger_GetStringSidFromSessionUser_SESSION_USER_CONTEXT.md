# LogonTrigger::GetStringSidFromSessionUser(_SESSION_USER_CONTEXT)

- ea: `0x18001295c`
- end: `0x180012b24`
- name: `?GetStringSidFromSessionUser@LogonTrigger@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_SESSION_USER_CONTEXT@@@Z`
- size: `456`
- prototype: ``
- caller_count: `4`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180012dc8`
- `0x180012f64`
- `0x180013040`
- `0x1800133fc`

## callees

- `0x180003b20`
- `0x18000402c`
- `0x1800041bc`
- `0x180006e2c`
- `0x180007328`
- `0x18000a1bc`
- `0x18000a548`
- `0x18000ccd4`
- `0x18001134c`
- `0x18001138c`
- `0x180011a14`
- `0x180012510`
- `0x18001295c`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180012abd`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180012abd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800129d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012a5b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800129d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012a5b`
- `ntdll!RtlIsMultiSessionSku` at `0x180012979`
- `ntdll!RtlIsMultiSessionSku` at `0x180012979`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x180012987`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x180012987`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x1800129f5`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x1800129f5`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180012a79`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180012a79`

## string_xrefs

- `0x1800129a8`: `shellcommon\shell\sharedpc\accountmanager\lib\service\logontrigger.cpp`
- `0x180012a07`: `shellcommon\shell\sharedpc\accountmanager\lib\service\logontrigger.cpp`
- `0x180012a2c`: `shellcommon\shell\sharedpc\accountmanager\lib\service\logontrigger.cpp`
- `0x180012a8a`: `shellcommon\shell\sharedpc\accountmanager\lib\service\logontrigger.cpp`
- `0x180012acb`: `shellcommon\shell\sharedpc\accountmanager\lib\service\logontrigger.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall LogonTrigger::GetStringSidFromSessionUser(__int64 a1, __int64 a2)
{
  HANDLE v4; // rdi
  const char *v5; // r9
  HANDLE v6; // rdi
  int v7; // eax
  const char *v8; // r9
  void *v9; // rcx
  int v11; // [rsp+20h] [rbp-20h]
  void *Block; // [rsp+28h] [rbp-18h] BYREF
  _BYTE v13[16]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  HANDLE hObject; // [rsp+70h] [rbp+30h] BYREF
  LPWSTR StringSid; // [rsp+78h] [rbp+38h] BYREF

  hObject = 0;
  if ( (unsigned __int8)RtlIsMultiSessionSku() || (unsigned __int8)RtlIsMultiUsersInSessionSku() )
  {
    if ( !(unsigned __int8)IsUMgrEnumerateSessionUsersPresent() )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0xF3,
        (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\logontrigger.cpp",
        (const char *)0x8000FFFFLL,
        v11);
    v6 = hObject;
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v13);
      CloseHandle(v6);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v13);
    }
    hObject = 0;
    v7 = UMgrQueryUserToken(*(_QWORD *)a2, &hObject);
    if ( v7 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xF4,
        (int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\logontrigger.cpp",
        (const char *)(unsigned int)v7,
        v11);
  }
  else
  {
    if ( !(unsigned __int8)IsQueryActiveSessionPresent() )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0xF8,
        (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\logontrigger.cpp",
        (const char *)0x8000FFFFLL,
        v11);
    v4 = hObject;
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v13);
      CloseHandle(v4);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v13);
    }
    hObject = 0;
    if ( !(unsigned int)QueryUserToken(*(unsigned int *)(a2 + 8), &hObject) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xF9,
        (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\logontrigger.cpp",
        v5);
  }
  wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(&Block, (__int64)hObject);
  StringSid = 0;
  if ( !ConvertSidToStringSidW(*(PSID *)Block, &StringSid) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xFF,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\logontrigger.cpp",
      v8);
  std::wstring::wstring(a1, (__int64)StringSid);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
  v9 = Block;
  Block = 0;
  if ( v9 )
    operator delete(v9);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
  return a1;
}

```

## disassembly

```asm
0x18001295c  mov     [rsp-18h+arg_0], rbx
0x180012961  push    rbp
0x180012962  push    rsi
0x180012963  push    rdi
0x180012964  mov     rbp, rsp
0x180012967  sub     rsp, 40h
0x18001296b  mov     rsi, rdx
0x18001296e  mov     rbx, rcx
0x180012971  mov     [rbp+hObject], 0
0x180012979  call    cs:__imp_RtlIsMultiSessionSku
0x18001297f  test    al, al
0x180012981  jnz     loc_180012A19
0x180012987  call    cs:__imp_RtlIsMultiUsersInSessionSku
0x18001298d  test    al, al
0x18001298f  jnz     loc_180012A19
0x180012995  mov     rdi, [rbp+18h]
0x180012999  call    IsQueryActiveSessionPresent
0x18001299e  test    al, al
0x1800129a0  jnz     short loc_1800129BD
0x1800129a2  mov     r9d, 8000FFFFh; char *
0x1800129a8  lea     r8, aShellcommonShe_11; "shellcommon\\shell\\sharedpc\\accountma"...
0x1800129af  mov     edx, 0F8h; void *
0x1800129b4  mov     rcx, rdi; this
0x1800129b7  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800129bd  mov     rdi, [rbp+hObject]
0x1800129c1  lea     rax, [rdi-1]
0x1800129c5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800129c9  ja      short loc_1800129E6
0x1800129cb  lea     rcx, [rbp+var_10]; this
0x1800129cf  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800129d4  mov     rcx, rdi; hObject
0x1800129d7  call    cs:__imp_CloseHandle
0x1800129dd  lea     rcx, [rbp+var_10]; this
0x1800129e1  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800129e6  mov     [rbp+hObject], 0
0x1800129ee  lea     rdx, [rbp+hObject]
0x1800129f2  mov     ecx, [rsi+8]
0x1800129f5  call    cs:__imp_QueryUserToken
0x1800129fb  mov     rcx, [rbp+18h]; this
0x1800129ff  test    eax, eax
0x180012a01  jnz     loc_180012A9C
0x180012a07  lea     r8, aShellcommonShe_11; "shellcommon\\shell\\sharedpc\\accountma"...
0x180012a0e  mov     edx, 0F9h; void *
0x180012a13  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180012a19  mov     rdi, [rbp+18h]
0x180012a1d  call    IsUMgrEnumerateSessionUsersPresent
0x180012a22  test    al, al
0x180012a24  jnz     short loc_180012A41
0x180012a26  mov     r9d, 8000FFFFh; char *
0x180012a2c  lea     r8, aShellcommonShe_11; "shellcommon\\shell\\sharedpc\\accountma"...
0x180012a33  mov     edx, 0F3h; void *
0x180012a38  mov     rcx, rdi; this
0x180012a3b  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180012a41  mov     rdi, [rbp+hObject]
0x180012a45  lea     rax, [rdi-1]
0x180012a49  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180012a4d  ja      short loc_180012A6A
0x180012a4f  lea     rcx, [rbp+var_10]; this
0x180012a53  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180012a58  mov     rcx, rdi; hObject
0x180012a5b  call    cs:__imp_CloseHandle
0x180012a61  lea     rcx, [rbp+var_10]; this
0x180012a65  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180012a6a  mov     [rbp+hObject], 0
0x180012a72  lea     rdx, [rbp+hObject]
0x180012a76  mov     rcx, [rsi]
0x180012a79  call    cs:__imp_UMgrQueryUserToken
0x180012a7f  mov     rcx, [rbp+18h]; this
0x180012a83  test    eax, eax
0x180012a85  jns     short loc_180012A9C
0x180012a87  mov     r9d, eax; char *
0x180012a8a  lea     r8, aShellcommonShe_11; "shellcommon\\shell\\sharedpc\\accountma"...
0x180012a91  mov     edx, 0F4h; void *
0x180012a96  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180012a9c  mov     rdx, [rbp+hObject]
0x180012aa0  lea     rcx, [rbp+Block]
0x180012aa4  call    ??$GetTokenInfoWrap@U_TOKEN_USER@@Uerr_exception_policy@wil@@$0A@@details@wil@@YA?AV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(void *)
0x180012aa9  nop
0x180012aaa  mov     [rbp+StringSid], 0
0x180012ab2  lea     rdx, [rbp+StringSid]; StringSid
0x180012ab6  mov     rcx, [rbp+Block]
0x180012aba  mov     rcx, [rcx]; Sid
0x180012abd  call    cs:__imp_ConvertSidToStringSidW
0x180012ac3  mov     rcx, [rbp+18h]; this
0x180012ac7  test    eax, eax
0x180012ac9  jnz     short loc_180012ADD
0x180012acb  lea     r8, aShellcommonShe_11; "shellcommon\\shell\\sharedpc\\accountma"...
0x180012ad2  mov     edx, 0FFh; void *
0x180012ad7  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180012add  mov     rdx, [rbp+StringSid]
0x180012ae1  mov     rcx, rbx
0x180012ae4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180012ae9  nop
0x180012aea  lea     rcx, [rbp+StringSid]
0x180012aee  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180012af3  nop
0x180012af4  mov     rcx, [rbp+Block]; Block
0x180012af8  mov     [rbp+Block], 0
0x180012b00  test    rcx, rcx
0x180012b03  jz      short loc_180012B0B
0x180012b05  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012b0a  nop
0x180012b0b  lea     rcx, [rbp+hObject]
0x180012b0f  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180012b14  mov     rax, rbx
0x180012b17  mov     rbx, [rsp+40h+arg_0]
0x180012b1c  add     rsp, 40h
0x180012b20  pop     rdi
0x180012b21  pop     rsi
0x180012b22  pop     rbp
0x180012b23  retn
```
