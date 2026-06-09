# DmGetActiveUserSid(ushort * *)

- ea: `0x180069ef0`
- end: `0x18006a13d`
- name: `?DmGetActiveUserSid@@YAJPEAPEAG@Z`
- size: `589`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `7`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180061610`
- `0x180071b24`
- `0x180074fa0`
- `0x180087b90`
- `0x1800887d0`
- `0x18008a440`
- `0x18008a650`

## callees

- `0x1800527b4`
- `0x180052ac4`
- `0x180069ae8`
- `0x180069ef0`
- `0x18006c63c`
- `0x18006c7c8`
- `0x18006cea8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069f7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069f7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006a026`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006a026`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006a036`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006a045`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006a036`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006a045`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180069ff6`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18006a10c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180069ff6`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18006a10c`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x18006a05a`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x18006a05a`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180069fc0`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180069fc0`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x180069f6f`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x180069f6f`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18006a0c5`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18006a0c5`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x18006a095`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x18006a095`

## pseudocode

```c
__int64 __fastcall DmGetActiveUserSid(unsigned __int16 **a1)
{
  PSID v1; // rsi
  signed int CurrentUserSid; // ebx
  signed int LastError; // eax
  __int64 i; // rdi
  bool v6; // zf
  ULONG SessionId; // ecx
  _QWORD *v9; // [rsp+30h] [rbp-30h] BYREF
  PSID Sid; // [rsp+38h] [rbp-28h]
  void *phToken; // [rsp+40h] [rbp-20h] BYREF
  LPWSTR StringSid; // [rsp+48h] [rbp-18h] BYREF
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+50h] [rbp-10h] BYREF
  DWORD pCount; // [rsp+98h] [rbp+38h] BYREF
  WINBOOL IsMember; // [rsp+A0h] [rbp+40h] BYREF
  int v16; // [rsp+A8h] [rbp+48h] BYREF

  v1 = 0;
  Sid = 0;
  StringSid = 0;
  ppSessionInfo = 0;
  pCount = 0;
  phToken = 0;
  IsMember = 0;
  CurrentUserSid = IsRunningInSystemContext(&IsMember);
  if ( CurrentUserSid < 0 )
    goto LABEL_20;
  if ( !IsMember )
  {
    CurrentUserSid = GetCurrentUserSid(a1);
    goto LABEL_20;
  }
  if ( !(unsigned __int8)IsWTSEnumerateSessionsWPresent() || !(unsigned __int8)IsWTSEnumerateSessionsWPresent() )
  {
    if ( (unsigned __int8)IsUMgrEnumerateSessionUsersPresent() && (unsigned __int8)IsUMgrEnumerateSessionUsersPresent() )
    {
      v16 = 0;
      v9 = 0;
      CurrentUserSid = UMgrEnumerateSessionUsers(&v16, &v9);
      if ( CurrentUserSid < 0 || v16 && (CurrentUserSid = UMgrQueryUserToken(*v9, &phToken), CurrentUserSid < 0) )
      {
        wil::details::unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>(&v9);
        goto LABEL_20;
      }
      wil::details::unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>(&v9);
    }
    if ( (char *)phToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      CurrentUserSid = GetUserSidFromToken(phToken);
      if ( CurrentUserSid < 0 )
      {
LABEL_36:
        v1 = Sid;
        goto LABEL_20;
      }
      v1 = Sid;
      if ( ConvertSidToStringSidW(Sid, &StringSid) )
      {
LABEL_35:
        *a1 = StringSid;
        StringSid = 0;
        goto LABEL_20;
      }
      goto LABEL_7;
    }
LABEL_19:
    CurrentUserSid = -2102788088;
    goto LABEL_20;
  }
  if ( WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &pCount) )
  {
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      v6 = (_DWORD)i == pCount;
      if ( (unsigned int)i >= pCount )
        break;
      SessionId = ppSessionInfo[i].SessionId;
      if ( SessionId && ppSessionInfo[i].State == WTSActive && WTSQueryUserToken(SessionId, &phToken) )
      {
        CurrentUserSid = GetUserSidFromToken(phToken);
        if ( CurrentUserSid < 0 )
          goto LABEL_36;
        v1 = Sid;
        if ( !ConvertSidToStringSidW(Sid, &StringSid) )
          goto LABEL_7;
        v6 = (_DWORD)i == pCount;
        break;
      }
    }
    if ( !v6 )
      goto LABEL_35;
    goto LABEL_19;
  }
LABEL_7:
  LastError = GetLastError();
  CurrentUserSid = LastError;
  if ( LastError > 0 )
    CurrentUserSid = (unsigned __int16)LastError | 0x80070000;
LABEL_20:
  if ( (char *)phToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(phToken);
  LocalFree(StringSid);
  LocalFree(v1);
  if ( ppSessionInfo )
    WTSFreeMemory(ppSessionInfo);
  return (unsigned int)CurrentUserSid;
}

```

## disassembly

```asm
0x180069ef0  push    rbp
0x180069ef2  push    rbx
0x180069ef3  push    rsi
0x180069ef4  push    rdi
0x180069ef5  push    r14
0x180069ef7  mov     rbp, rsp
0x180069efa  sub     rsp, 60h
0x180069efe  xor     esi, esi
0x180069f00  mov     r14, rcx
0x180069f03  lea     rcx, [rbp+IsMember]; IsMember
0x180069f07  mov     [rbp+Sid], rsi
0x180069f0b  mov     [rbp+StringSid], rsi
0x180069f0f  mov     [rbp+ppSessionInfo], rsi
0x180069f13  mov     [rbp+arg_8], esi
0x180069f16  mov     [rbp+phToken], rsi
0x180069f1a  mov     [rbp+IsMember], esi
0x180069f1d  call    IsRunningInSystemContext
0x180069f22  mov     ebx, eax
0x180069f24  test    eax, eax
0x180069f26  js      loc_18006A018
0x180069f2c  cmp     [rbp+IsMember], esi
0x180069f2f  jnz     short loc_180069F40
0x180069f31  mov     rcx, r14
0x180069f34  call    GetCurrentUserSid
0x180069f39  mov     ebx, eax
0x180069f3b  jmp     loc_18006A018
0x180069f40  call    IsWTSEnumerateSessionsWPresent
0x180069f45  test    al, al
0x180069f47  jz      loc_18006A074
0x180069f4d  call    IsWTSEnumerateSessionsWPresent
0x180069f52  test    al, al
0x180069f54  jz      loc_18006A074
0x180069f5a  xor     edx, edx; Reserved
0x180069f5c  lea     rax, [rbp+arg_8]
0x180069f60  lea     r9, [rbp+ppSessionInfo]; ppSessionInfo
0x180069f64  mov     [rsp+60h+pCount], rax; pCount
0x180069f69  xor     ecx, ecx; hServer
0x180069f6b  lea     r8d, [rdx+1]; Version
0x180069f6f  call    cs:__imp_WTSEnumerateSessionsW
0x180069f76  nop     dword ptr [rax+rax+00h]
0x180069f7b  test    eax, eax
0x180069f7d  jnz     short loc_180069FA0
0x180069f7f  call    cs:__imp_GetLastError
0x180069f86  nop     dword ptr [rax+rax+00h]
0x180069f8b  mov     ebx, eax
0x180069f8d  test    eax, eax
0x180069f8f  jle     loc_18006A018
0x180069f95  movzx   ebx, ax
0x180069f98  or      ebx, 80070000h
0x180069f9e  jmp     short loc_18006A018
0x180069fa0  xor     edi, edi
0x180069fa2  cmp     edi, [rbp+arg_8]
0x180069fa5  jnb     short loc_18006A00D
0x180069fa7  mov     rax, [rbp+ppSessionInfo]
0x180069fab  lea     rdx, [rdi+rdi*2]
0x180069faf  mov     ecx, [rax+rdx*8]; SessionId
0x180069fb2  test    ecx, ecx
0x180069fb4  jz      short loc_180069FD0
0x180069fb6  cmp     [rax+rdx*8+10h], esi
0x180069fba  jnz     short loc_180069FD0
0x180069fbc  lea     rdx, [rbp+phToken]; phToken
0x180069fc0  call    cs:__imp_WTSQueryUserToken
0x180069fc7  nop     dword ptr [rax+rax+00h]
0x180069fcc  test    eax, eax
0x180069fce  jnz     short loc_180069FD4
0x180069fd0  inc     edi
0x180069fd2  jmp     short loc_180069FA2
0x180069fd4  mov     rcx, [rbp+phToken]; TokenHandle
0x180069fd8  lea     rdx, [rbp+Sid]
0x180069fdc  call    GetUserSidFromToken
0x180069fe1  mov     ebx, eax
0x180069fe3  test    eax, eax
0x180069fe5  js      loc_18006A134
0x180069feb  mov     rsi, [rbp+Sid]
0x180069fef  lea     rdx, [rbp+StringSid]; StringSid
0x180069ff3  mov     rcx, rsi; Sid
0x180069ff6  call    cs:__imp_ConvertSidToStringSidW
0x180069ffd  nop     dword ptr [rax+rax+00h]
0x18006a002  test    eax, eax
0x18006a004  jz      loc_180069F7F
0x18006a00a  cmp     edi, [rbp+arg_8]
0x18006a00d  jnz     loc_18006A120
0x18006a013  mov     ebx, 82AA0008h
0x18006a018  mov     rcx, [rbp+phToken]; hObject
0x18006a01c  lea     rax, [rcx-1]
0x18006a020  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006a024  ja      short loc_18006A032
0x18006a026  call    cs:__imp_CloseHandle
0x18006a02d  nop     dword ptr [rax+rax+00h]
0x18006a032  mov     rcx, [rbp+StringSid]; hMem
0x18006a036  call    cs:__imp_LocalFree
0x18006a03d  nop     dword ptr [rax+rax+00h]
0x18006a042  mov     rcx, rsi; hMem
0x18006a045  call    cs:__imp_LocalFree
0x18006a04c  nop     dword ptr [rax+rax+00h]
0x18006a051  mov     rcx, [rbp+ppSessionInfo]; pMemory
0x18006a055  test    rcx, rcx
0x18006a058  jz      short loc_18006A066
0x18006a05a  call    cs:__imp_WTSFreeMemory
0x18006a061  nop     dword ptr [rax+rax+00h]
0x18006a066  mov     eax, ebx
0x18006a068  add     rsp, 60h
0x18006a06c  pop     r14
0x18006a06e  pop     rdi
0x18006a06f  pop     rsi
0x18006a070  pop     rbx
0x18006a071  pop     rbp
0x18006a072  retn
0x18006a074  call    IsUMgrEnumerateSessionUsersPresent
0x18006a079  test    al, al
0x18006a07b  jz      short loc_18006A0E0
0x18006a07d  call    IsUMgrEnumerateSessionUsersPresent
0x18006a082  test    al, al
0x18006a084  jz      short loc_18006A0E0
0x18006a086  lea     rdx, [rbp+var_30]
0x18006a08a  mov     [rbp+arg_18], esi
0x18006a08d  lea     rcx, [rbp+arg_18]
0x18006a091  mov     [rbp+var_30], rsi
0x18006a095  call    cs:__imp_UMgrEnumerateSessionUsers
0x18006a09c  nop     dword ptr [rax+rax+00h]
0x18006a0a1  mov     ebx, eax
0x18006a0a3  test    eax, eax
0x18006a0a5  jns     short loc_18006A0B5
0x18006a0a7  lea     rcx, [rbp+var_30]
0x18006a0ab  call    ??1?$unique_storage@U?$resource_policy@PEAU_SESSION_USER_CONTEXT@@P6AXPEAU1@@Z$1?UMgrFreeSessionUsers@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>(void)
0x18006a0b0  jmp     loc_18006A018
0x18006a0b5  cmp     [rbp+arg_18], esi
0x18006a0b8  jbe     short loc_18006A0D7
0x18006a0ba  mov     rcx, [rbp+var_30]
0x18006a0be  lea     rdx, [rbp+phToken]
0x18006a0c2  mov     rcx, [rcx]
0x18006a0c5  call    cs:__imp_UMgrQueryUserToken
0x18006a0cc  nop     dword ptr [rax+rax+00h]
0x18006a0d1  mov     ebx, eax
0x18006a0d3  test    eax, eax
0x18006a0d5  js      short loc_18006A0A7
0x18006a0d7  lea     rcx, [rbp+var_30]
0x18006a0db  call    ??1?$unique_storage@U?$resource_policy@PEAU_SESSION_USER_CONTEXT@@P6AXPEAU1@@Z$1?UMgrFreeSessionUsers@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>(void)
0x18006a0e0  mov     rcx, [rbp+phToken]; TokenHandle
0x18006a0e4  lea     rax, [rcx-1]
0x18006a0e8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006a0ec  ja      loc_18006A013
0x18006a0f2  lea     rdx, [rbp+Sid]
0x18006a0f6  call    GetUserSidFromToken
0x18006a0fb  mov     ebx, eax
0x18006a0fd  test    eax, eax
0x18006a0ff  js      short loc_18006A134
0x18006a101  mov     rsi, [rbp+Sid]
0x18006a105  lea     rdx, [rbp+StringSid]; StringSid
0x18006a109  mov     rcx, rsi; Sid
0x18006a10c  call    cs:__imp_ConvertSidToStringSidW
0x18006a113  nop     dword ptr [rax+rax+00h]
0x18006a118  test    eax, eax
0x18006a11a  jz      loc_180069F7F
0x18006a120  mov     rax, [rbp+StringSid]
0x18006a124  mov     [r14], rax
0x18006a127  mov     [rbp+StringSid], 0
0x18006a12f  jmp     loc_18006A018
0x18006a134  mov     rsi, [rbp+Sid]
0x18006a138  jmp     loc_18006A018
```
