# GetPackageInfoForUserContext

- ea: `0x180084bb0`
- end: `0x180084cdd`
- name: `GetPackageInfoForUserContext`
- size: `301`
- prototype: `__int64 __fastcall(PCWSTR packageFullName)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180084b2c`

## callees

- `0x18000b5c0`
- `0x1800445ac`
- `0x18005ae90`
- `0x18005e96c`
- `0x180084bb0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180084c67`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180084c67`
- `ntdll!NtQueryInformationToken` at `0x180084c5b`
- `ntdll!NtQueryInformationToken` at `0x180084c5b`
- `api-ms-win-appmodel-runtime-l1-1-1!OpenPackageInfoByFullNameForUser` at `0x180084c91`
- `api-ms-win-appmodel-runtime-l1-1-1!OpenPackageInfoByFullNameForUser` at `0x180084c91`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180084c2d`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180084c2d`

## pseudocode

```c
int __fastcall GetPackageInfoForUserContext(PCWSTR packageFullName, __int64 a2, PACKAGE_INFO_REFERENCE *a3)
{
  int v6; // ebx
  __int64 v7; // rdx
  NTSTATUS v9; // ebx
  unsigned int v10; // eax
  unsigned int ReturnLength; // [rsp+20h] [rbp-59h]
  ULONG v12; // [rsp+30h] [rbp-49h] BYREF
  HANDLE TokenHandle; // [rsp+38h] [rbp-41h] BYREF
  PACKAGE_INFO_REFERENCE packageInfoReference; // [rsp+40h] [rbp-39h] BYREF
  PSID TokenInformation[12]; // [rsp+50h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  *a3 = 0;
  if ( !(unsigned __int8)IsUMgrOpenProcessHandleForAccessPresent() )
  {
    v6 = -2147467263;
    v7 = 106;
    goto LABEL_3;
  }
  TokenHandle = 0;
  v12 = 0;
  packageInfoReference = 0;
  v6 = UMgrQueryUserToken(a2, &TokenHandle);
  if ( v6 < 0 )
  {
    v7 = 113;
    goto LABEL_3;
  }
  v9 = NtQueryInformationToken(TokenHandle, TokenUser, TokenInformation, 0x54u, &v12);
  CloseHandle(TokenHandle);
  if ( v9 < 0 )
  {
    v6 = v9 | 0x10000000;
    if ( v6 >= 0 )
      return v6;
    v7 = 119;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\hostedappgrouppolicy.cpp",
      (const char *)(unsigned int)v6,
      ReturnLength);
    return v6;
  }
  v10 = OpenPackageInfoByFullNameForUser(TokenInformation[0], packageFullName, 0, &packageInfoReference);
  if ( v10 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x7B,
             (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\hostedappgrouppolicy.cpp",
             (const char *)v10,
             ReturnLength);
  *a3 = packageInfoReference;
  return 0;
}

```

## disassembly

```asm
0x180084bb0  mov     [rsp-8+arg_18], rbx
0x180084bb5  push    rbp
0x180084bb6  push    rsi
0x180084bb7  push    rdi
0x180084bb8  lea     rbp, [rsp-47h]
0x180084bbd  sub     rsp, 0C0h
0x180084bc4  mov     rax, cs:__security_cookie
0x180084bcb  xor     rax, rsp
0x180084bce  mov     [rbp+57h+var_20], rax
0x180084bd2  mov     rdi, r8
0x180084bd5  mov     qword ptr [r8], 0
0x180084bdc  mov     rbx, rdx
0x180084bdf  mov     rsi, rcx
0x180084be2  call    IsUMgrOpenProcessHandleForAccessPresent
0x180084be7  test    al, al
0x180084be9  jnz     short loc_180084C0F
0x180084beb  mov     ebx, 80004001h
0x180084bf0  mov     edx, 6Ah ; 'j'; void *
0x180084bf5  mov     rcx, [rbp+5Fh]; this
0x180084bf9  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180084c00  mov     r9d, ebx; char *
0x180084c03  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084c08  mov     eax, ebx
0x180084c0a  jmp     loc_180084CBE
0x180084c0f  lea     rdx, [rbp+57h+TokenHandle]
0x180084c13  mov     [rbp+57h+TokenHandle], 0
0x180084c1b  mov     rcx, rbx
0x180084c1e  mov     [rbp+57h+var_A0], 0
0x180084c25  mov     [rbp+57h+packageInfoReference], 0
0x180084c2d  call    cs:__imp_UMgrQueryUserToken
0x180084c33  mov     ebx, eax
0x180084c35  test    eax, eax
0x180084c37  jns     short loc_180084C40
0x180084c39  mov     edx, 71h ; 'q'
0x180084c3e  jmp     short loc_180084BF5
0x180084c40  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180084c44  lea     rax, [rbp+57h+var_A0]
0x180084c48  mov     r9d, 54h ; 'T'; TokenInformationLength
0x180084c4e  mov     qword ptr [rsp+0D0h+ReturnLength], rax; unsigned int
0x180084c53  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180084c57  lea     edx, [r9-53h]; TokenInformationClass
0x180084c5b  call    cs:__imp_NtQueryInformationToken
0x180084c61  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180084c65  mov     ebx, eax
0x180084c67  call    cs:__imp_CloseHandle
0x180084c6d  test    ebx, ebx
0x180084c6f  jns     short loc_180084C83
0x180084c71  or      ebx, 10000000h
0x180084c77  jge     short loc_180084C08
0x180084c79  mov     edx, 77h ; 'w'
0x180084c7e  jmp     loc_180084BF5
0x180084c83  mov     rcx, [rbp+57h+TokenInformation]; userSid
0x180084c87  lea     r9, [rbp+57h+packageInfoReference]; packageInfoReference
0x180084c8b  xor     r8d, r8d; reserved
0x180084c8e  mov     rdx, rsi; packageFullName
0x180084c91  call    cs:__imp_OpenPackageInfoByFullNameForUser
0x180084c97  test    eax, eax
0x180084c99  jz      short loc_180084CB5
0x180084c9b  mov     rcx, [rbp+5Fh]; this
0x180084c9f  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180084ca6  mov     r9d, eax; char *
0x180084ca9  mov     edx, 7Bh ; '{'; void *
0x180084cae  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180084cb3  jmp     short loc_180084CBE
0x180084cb5  mov     rax, [rbp+57h+packageInfoReference]
0x180084cb9  mov     [rdi], rax
0x180084cbc  xor     eax, eax
0x180084cbe  mov     rcx, [rbp+57h+var_20]
0x180084cc2  xor     rcx, rsp; StackCookie
0x180084cc5  call    __security_check_cookie
0x180084cca  mov     rbx, [rsp+0D0h+arg_18]
0x180084cd2  add     rsp, 0C0h
0x180084cd9  pop     rdi
0x180084cda  pop     rsi
0x180084cdb  pop     rbp
0x180084cdc  retn
```
