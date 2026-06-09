# GetCurrentUserSid

- ea: `0x180032cb4`
- end: `0x180032d97`
- name: `GetCurrentUserSid`
- size: `227`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800318c0`
- `0x180031d60`
- `0x180032040`

## callees

- `0x1800096cc`
- `0x1800096ec`
- `0x1800236d8`
- `0x180029708`
- `0x18002eccc`
- `0x180032cb4`
- `0x180032da0`
- `0x180033f04`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180032d37`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180032d37`

## string_xrefs

- `0x180032d13`: `shellcommon\shell\settingshandlers\workaccess\lib\accountenthusiast.cpp`
- `0x180032d4b`: `shellcommon\shell\settingshandlers\workaccess\lib\accountenthusiast.cpp`

## pseudocode

```c
__int64 __fastcall GetCurrentUserSid(LPWSTR *a1)
{
  int CurrentUserToken; // eax
  unsigned int LastError; // ebx
  __int64 v4; // rdx
  const char *v5; // r9
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  LPWSTR StringSid; // [rsp+40h] [rbp+20h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp+28h] BYREF
  PSID Sid; // [rsp+50h] [rbp+30h] BYREF

  *a1 = 0;
  Sid = 0;
  StringSid = 0;
  TokenHandle = 0;
  CurrentUserToken = GetCurrentUserToken(&TokenHandle);
  LastError = CurrentUserToken;
  if ( CurrentUserToken < 0 )
  {
    v4 = 150;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\accountenthusiast.cpp",
      (const char *)(unsigned int)CurrentUserToken,
      savedregs);
    goto LABEL_9;
  }
  CurrentUserToken = GetUserSidFromToken(TokenHandle, &Sid);
  LastError = CurrentUserToken;
  if ( CurrentUserToken < 0 )
  {
    v4 = 151;
    goto LABEL_5;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &StringSid,
    0);
  if ( ConvertSidToStringSidW(Sid, &StringSid) )
  {
    LastError = 0;
    *a1 = StringSid;
    StringSid = 0;
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x99,
                  (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\accountenthusiast.cpp",
                  v5);
  }
LABEL_9:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
  return LastError;
}

```

## disassembly

```asm
0x180032cb4  push    rbp
0x180032cb6  push    rbx
0x180032cb7  push    rdi; int
0x180032cb8  mov     rbp, rsp
0x180032cbb  sub     rsp, 20h
0x180032cbf  mov     rdi, rcx
0x180032cc2  mov     qword ptr [rcx], 0
0x180032cc9  lea     rcx, [rbp+TokenHandle]; TokenHandle
0x180032ccd  mov     [rbp+Sid], 0
0x180032cd5  mov     [rbp+StringSid], 0
0x180032cdd  mov     [rbp+TokenHandle], 0
0x180032ce5  call    GetCurrentUserToken
0x180032cea  mov     ebx, eax
0x180032cec  test    eax, eax
0x180032cee  jns     short loc_180032CF7
0x180032cf0  mov     edx, 96h
0x180032cf5  jmp     short loc_180032D0F
0x180032cf7  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180032cfb  lea     rdx, [rbp+Sid]
0x180032cff  call    GetUserSidFromToken
0x180032d04  mov     ebx, eax
0x180032d06  test    eax, eax
0x180032d08  jns     short loc_180032D24
0x180032d0a  mov     edx, 97h; void *
0x180032d0f  mov     rcx, [rbp+18h]; this
0x180032d13  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\settingshandlers\\w"...
0x180032d1a  mov     r9d, eax; char *
0x180032d1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032d22  jmp     short loc_180032D71
0x180032d24  xor     edx, edx
0x180032d26  lea     rcx, [rbp+StringSid]
0x180032d2a  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180032d2f  mov     rcx, [rbp+Sid]; Sid
0x180032d33  lea     rdx, [rbp+StringSid]; StringSid
0x180032d37  call    cs:__imp_ConvertSidToStringSidW
0x180032d3e  nop     dword ptr [rax+rax+00h]
0x180032d43  test    eax, eax
0x180032d45  jnz     short loc_180032D60
0x180032d47  mov     rcx, [rbp+18h]; this
0x180032d4b  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\settingshandlers\\w"...
0x180032d52  mov     edx, 99h; void *
0x180032d57  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180032d5c  mov     ebx, eax
0x180032d5e  jmp     short loc_180032D71
0x180032d60  mov     rax, [rbp+StringSid]
0x180032d64  xor     ebx, ebx
0x180032d66  mov     [rdi], rax
0x180032d69  mov     [rbp+StringSid], 0
0x180032d71  lea     rcx, [rbp+TokenHandle]
0x180032d75  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180032d7a  lea     rcx, [rbp+StringSid]
0x180032d7e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180032d83  lea     rcx, [rbp+Sid]
0x180032d87  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180032d8c  mov     eax, ebx
0x180032d8e  add     rsp, 20h
0x180032d92  pop     rdi
0x180032d93  pop     rbx
0x180032d94  pop     rbp
0x180032d95  retn
```
