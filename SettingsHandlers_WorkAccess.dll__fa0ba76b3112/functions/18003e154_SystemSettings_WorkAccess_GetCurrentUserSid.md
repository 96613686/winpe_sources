# SystemSettings::WorkAccess::GetCurrentUserSid

- ea: `0x18003e154`
- end: `0x18003e235`
- name: `SystemSettings::WorkAccess::GetCurrentUserSid`
- size: `225`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003c430`

## callees

- `0x1800096cc`
- `0x1800096ec`
- `0x1800236d8`
- `0x180029708`
- `0x18002eccc`
- `0x18003e154`
- `0x18003e23c`
- `0x18003ea30`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18003e1d7`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18003e1d7`

## string_xrefs

- `0x18003e1b3`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmentprofilesettings.cpp`
- `0x18003e1eb`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmentprofilesettings.cpp`

## pseudocode

```c
__int64 __fastcall SystemSettings::WorkAccess::GetCurrentUserSid(LPWSTR *a1)
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
  CurrentUserToken = SystemSettings::WorkAccess::GetCurrentUserToken(&TokenHandle);
  LastError = CurrentUserToken;
  if ( CurrentUserToken < 0 )
  {
    v4 = 122;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmentprofilesettings.cpp",
      (const char *)(unsigned int)CurrentUserToken,
      savedregs);
    goto LABEL_9;
  }
  CurrentUserToken = SystemSettings::WorkAccess::GetUserSidFromToken(TokenHandle, &Sid);
  LastError = CurrentUserToken;
  if ( CurrentUserToken < 0 )
  {
    v4 = 123;
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
                  (void *)0x7D,
                  (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmentprofilesettings.cpp",
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
0x18003e154  push    rbp
0x18003e156  push    rbx
0x18003e157  push    rdi; int
0x18003e158  mov     rbp, rsp
0x18003e15b  sub     rsp, 20h
0x18003e15f  mov     rdi, rcx
0x18003e162  mov     qword ptr [rcx], 0
0x18003e169  lea     rcx, [rbp+TokenHandle]; TokenHandle
0x18003e16d  mov     [rbp+Sid], 0
0x18003e175  mov     [rbp+StringSid], 0
0x18003e17d  mov     [rbp+TokenHandle], 0
0x18003e185  call    SystemSettings__WorkAccess__GetCurrentUserToken
0x18003e18a  mov     ebx, eax
0x18003e18c  test    eax, eax
0x18003e18e  jns     short loc_18003E197
0x18003e190  mov     edx, 7Ah ; 'z'
0x18003e195  jmp     short loc_18003E1AF
0x18003e197  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18003e19b  lea     rdx, [rbp+Sid]
0x18003e19f  call    SystemSettings__WorkAccess__GetUserSidFromToken
0x18003e1a4  mov     ebx, eax
0x18003e1a6  test    eax, eax
0x18003e1a8  jns     short loc_18003E1C4
0x18003e1aa  mov     edx, 7Bh ; '{'; void *
0x18003e1af  mov     rcx, [rbp+18h]; this
0x18003e1b3  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\settingshandlers\\w"...
0x18003e1ba  mov     r9d, eax; char *
0x18003e1bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e1c2  jmp     short loc_18003E20F
0x18003e1c4  xor     edx, edx
0x18003e1c6  lea     rcx, [rbp+StringSid]
0x18003e1ca  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003e1cf  mov     rcx, [rbp+Sid]; Sid
0x18003e1d3  lea     rdx, [rbp+StringSid]; StringSid
0x18003e1d7  call    cs:__imp_ConvertSidToStringSidW
0x18003e1de  nop     dword ptr [rax+rax+00h]
0x18003e1e3  test    eax, eax
0x18003e1e5  jnz     short loc_18003E1FE
0x18003e1e7  mov     rcx, [rbp+18h]; this
0x18003e1eb  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\settingshandlers\\w"...
0x18003e1f2  lea     edx, [rax+7Dh]; void *
0x18003e1f5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003e1fa  mov     ebx, eax
0x18003e1fc  jmp     short loc_18003E20F
0x18003e1fe  mov     rax, [rbp+StringSid]
0x18003e202  xor     ebx, ebx
0x18003e204  mov     [rdi], rax
0x18003e207  mov     [rbp+StringSid], 0
0x18003e20f  lea     rcx, [rbp+TokenHandle]
0x18003e213  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003e218  lea     rcx, [rbp+StringSid]
0x18003e21c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003e221  lea     rcx, [rbp+Sid]
0x18003e225  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003e22a  mov     eax, ebx
0x18003e22c  add     rsp, 20h
0x18003e230  pop     rdi
0x18003e231  pop     rbx
0x18003e232  pop     rbp
0x18003e233  retn
```
