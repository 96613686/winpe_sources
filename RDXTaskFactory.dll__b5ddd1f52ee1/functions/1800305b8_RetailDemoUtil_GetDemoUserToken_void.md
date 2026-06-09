# RetailDemoUtil::GetDemoUserToken(void)

- ea: `0x1800305b8`
- end: `0x18003070c`
- name: `?GetDemoUserToken@RetailDemoUtil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ`
- size: `340`
- prototype: ``
- caller_count: `5`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023720`
- `0x18002fc68`
- `0x180030538`
- `0x180030f50`
- `0x180032050`

## callees

- `0x180004794`
- `0x180004874`
- `0x180006490`
- `0x18001094c`
- `0x180014d04`
- `0x180024acc`
- `0x180025ee4`
- `0x18002ffe0`
- `0x1800304e8`
- `0x1800305b8`
- `0x180032018`

## import_xrefs

- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x180030676`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x180030676`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180030643`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180030643`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18003060d`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18003060d`

## string_xrefs

- `0x1800306a0`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x1800306b9`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x1800306e8`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x1800306fa`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`
- `0x1800306dc`: `Neither WTSQueryUserToken or QueryUserToken are present on the system.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall RetailDemoUtil::GetDemoUserToken(_QWORD *a1, unsigned __int64 *a2)
{
  RetailDemoUtil *v3; // rcx
  int UserToken; // eax
  ULONG DemoUserSession; // edi
  const char *v6; // r9
  const char *v7; // r9
  unsigned int v9; // eax
  int v10; // [rsp+20h] [rbp-30h]
  const char *v11; // [rsp+28h] [rbp-28h]
  _QWORD *v12; // [rsp+38h] [rbp-18h] BYREF
  void *phToken; // [rsp+40h] [rbp-10h] BYREF
  char v14; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  __int64 v16; // [rsp+68h] [rbp+18h] BYREF

  *a1 = 0;
  v16 = 0;
  if ( (int)RetailDemoUtil::GetDemoUserContext((RetailDemoUtil *)&v16, a2) < 0 )
  {
    DemoUserSession = RetailDemoUtil::GetDemoUserSession(v3);
    if ( (unsigned __int8)IsWTSEnumerateSessionsWPresent() )
    {
      v12 = a1;
      phToken = 0;
      v14 = 1;
      if ( !WTSQueryUserToken(DemoUserSession, &phToken) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x199,
          (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
          v6);
    }
    else
    {
      if ( !(unsigned __int8)IsQueryUserTokenPresent() )
      {
        v9 = wil::verify_hresult<long>(2147942527LL);
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x1A1,
          (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
          (const char *)v9,
          (int)"Neither WTSQueryUserToken or QueryUserToken are present on the system.",
          v11);
      }
      v12 = a1;
      phToken = 0;
      v14 = 1;
      if ( !(unsigned int)QueryUserToken(DemoUserSession, &phToken) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x19D,
          (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
          v7);
    }
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v12);
  }
  else
  {
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      a1,
      0);
    UserToken = UMgrQueryUserToken(v16, a1);
    if ( UserToken < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x18E,
        (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
        (const char *)(unsigned int)UserToken,
        v10);
  }
  return a1;
}

```

## disassembly

```asm
0x1800305b8  mov     [rsp-8+arg_10], rbx
0x1800305bd  mov     [rsp-8+arg_18], rdi
0x1800305c2  mov     [rsp-8+arg_0], rcx
0x1800305c7  push    rbp
0x1800305c8  mov     rbp, rsp
0x1800305cb  sub     rsp, 50h
0x1800305cf  mov     rbx, rcx
0x1800305d2  mov     [rbp+var_20], 0
0x1800305d9  mov     qword ptr [rcx], 0
0x1800305e0  mov     [rbp+var_20], 1
0x1800305e7  mov     [rbp+arg_8], 0
0x1800305ef  lea     rcx, [rbp+arg_8]; this
0x1800305f3  call    ?GetDemoUserContext@RetailDemoUtil@@YAJPEA_K@Z; RetailDemoUtil::GetDemoUserContext(unsigned __int64 *)
0x1800305f8  test    eax, eax
0x1800305fa  js      short loc_18003061D
0x1800305fc  xor     edx, edx
0x1800305fe  mov     rcx, rbx
0x180030601  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180030606  mov     rdx, rbx
0x180030609  mov     rcx, [rbp+arg_8]
0x18003060d  call    cs:__imp_UMgrQueryUserToken
0x180030613  test    eax, eax
0x180030615  js      loc_1800306B2
0x18003061b  jmp     short loc_18003068D
0x18003061d  call    ?GetDemoUserSession@RetailDemoUtil@@YAKXZ; RetailDemoUtil::GetDemoUserSession(void)
0x180030622  mov     edi, eax
0x180030624  call    IsWTSEnumerateSessionsWPresent
0x180030629  test    al, al
0x18003062b  jz      short loc_180030657
0x18003062d  mov     [rbp+var_18], rbx
0x180030631  mov     [rbp+phToken], 0
0x180030639  mov     [rbp+var_8], 1
0x18003063d  lea     rdx, [rbp+phToken]; phToken
0x180030641  mov     ecx, edi; SessionId
0x180030643  call    cs:__imp_WTSQueryUserToken
0x180030649  mov     rcx, [rbp+8]; this
0x18003064d  test    eax, eax
0x18003064f  jz      loc_1800306FA
0x180030655  jmp     short loc_180030684
0x180030657  call    IsQueryUserTokenPresent
0x18003065c  test    al, al
0x18003065e  jz      short loc_1800306CB
0x180030660  mov     [rbp+var_18], rbx
0x180030664  mov     [rbp+phToken], 0
0x18003066c  mov     [rbp+var_8], 1
0x180030670  lea     rdx, [rbp+phToken]
0x180030674  mov     ecx, edi
0x180030676  call    cs:__imp_QueryUserToken
0x18003067c  mov     rcx, [rbp+8]; this
0x180030680  test    eax, eax
0x180030682  jz      short loc_1800306A0
0x180030684  lea     rcx, [rbp+var_18]
0x180030688  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x18003068d  mov     rax, rbx
0x180030690  mov     rbx, [rsp+50h+arg_10]
0x180030695  mov     rdi, [rsp+50h+arg_18]
0x18003069a  add     rsp, 50h
0x18003069e  pop     rbp
0x18003069f  retn
0x1800306a0  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x1800306a7  mov     edx, 19Dh; void *
0x1800306ac  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800306b2  mov     rcx, [rbp+8]; this
0x1800306b6  mov     r9d, eax; char *
0x1800306b9  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x1800306c0  mov     edx, 18Eh; void *
0x1800306c5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800306cb  mov     ecx, 8007007Fh
0x1800306d0  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800306d5  mov     r9d, eax; char *
0x1800306d8  mov     rcx, [rbp+8]; this
0x1800306dc  lea     rax, aNeitherWtsquer; "Neither WTSQueryUserToken or QueryUserT"...
0x1800306e3  mov     qword ptr [rsp+50h+var_30], rax; int
0x1800306e8  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x1800306ef  mov     edx, 1A1h; void *
0x1800306f4  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800306fa  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x180030701  mov     edx, 199h; void *
0x180030706  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
