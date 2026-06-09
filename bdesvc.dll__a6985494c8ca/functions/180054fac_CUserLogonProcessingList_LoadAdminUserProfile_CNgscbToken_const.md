# CUserLogonProcessingList::LoadAdminUserProfile(CNgscbToken const &)

- ea: `0x180054fac`
- end: `0x18005520a`
- name: `?LoadAdminUserProfile@CUserLogonProcessingList@@KAJAEBVCNgscbToken@@@Z`
- size: `606`
- prototype: `__int64 __fastcall(const struct CNgscbToken *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180020a90`

## callees

- `0x180009f60`
- `0x180021d18`
- `0x180026190`
- `0x18002b6ac`
- `0x180034070`
- `0x180034d28`
- `0x180054fac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180055113`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180055113`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005509a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005515c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005509a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005515c`
- `SspiCli!GetUserNameExW` at `0x18005508a`
- `SspiCli!GetUserNameExW` at `0x18005508a`
- `USERENV!LoadUserProfileW` at `0x18005514c`
- `USERENV!LoadUserProfileW` at `0x18005514c`
- `USERENV!UnloadUserProfile` at `0x1800551d5`
- `USERENV!UnloadUserProfile` at `0x1800551d5`

## string_xrefs

- `0x180055057`: `ImpersonateUser`

## pseudocode

```c
__int64 __fastcall CUserLogonProcessingList::LoadAdminUserProfile(HANDLE *a1)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  signed int v4; // eax
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  wchar_t *v7; // rax
  WCHAR *v8; // rax
  HANDLE v9; // rcx
  signed int LastError; // eax
  const char *v12; // [rsp+28h] [rbp-D8h]
  _BYTE v13[8]; // [rsp+30h] [rbp-D0h] BYREF
  _PROFILEINFOW ProfileInfo; // [rsp+38h] [rbp-C8h] BYREF
  ULONG nSize[4]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR NameBuffer[520]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4C8h] [rbp+3C8h]

  v13[0] = 0;
  memset_0(NameBuffer, 0, 0x404u);
  nSize[0] = 514;
  memset(&ProfileInfo, 0, sizeof(ProfileInfo));
  v2 = CScopedImpersonation::ImpersonateUser((CScopedImpersonation *)v13, a1);
  v3 = v2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 237, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, v2);
  if ( (v3 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0xCF5,
      (unsigned int)"base\\ngscb\\cornerstone\\bdesvc\\svc\\deviceencryption.cpp",
      (const char *)v3,
      (int)"ImpersonateUser",
      v12);
    goto LABEL_22;
  }
  if ( GetUserNameExW(NameSamCompatible, NameBuffer, nSize) )
  {
    CScopedImpersonation::Revert((CScopedImpersonation *)v13);
    v7 = wcschr(NameBuffer, 0x5Cu);
    if ( v7 )
      v8 = v7 + 1;
    else
      v8 = NameBuffer;
    v9 = *a1;
    ProfileInfo.dwSize = 56;
    ProfileInfo.lpUserName = v8;
    ProfileInfo.lpProfilePath = 0;
    if ( !LoadUserProfileW(v9, &ProfileInfo) )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0xD12,
        (unsigned int)"base\\ngscb\\cornerstone\\bdesvc\\svc\\deviceencryption.cpp",
        (const char *)v3,
        (int)"LoadUserProfileW",
        v12);
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        v6 = 239;
        goto LABEL_21;
      }
    }
  }
  else
  {
    v4 = GetLastError();
    v3 = v4;
    if ( v4 > 0 )
      v3 = (unsigned __int16)v4 | 0x80070000;
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0xCFA,
      (unsigned int)"base\\ngscb\\cornerstone\\bdesvc\\svc\\deviceencryption.cpp",
      (const char *)v3,
      (int)"GetUserNameExW",
      v12);
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      v6 = 238;
LABEL_21:
      WPP_SF_d(v5[2], v6, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, v3);
    }
  }
LABEL_22:
  if ( ProfileInfo.hProfile )
    UnloadUserProfile(*a1, ProfileInfo.hProfile);
  CScopedImpersonation::Revert((CScopedImpersonation *)v13);
  return v3;
}

```

## disassembly

```asm
0x180054fac  push    rbp
0x180054fae  push    rbx
0x180054faf  push    rdi
0x180054fb0  push    r15
0x180054fb2  lea     rbp, [rsp-3A8h]
0x180054fba  sub     rsp, 4A8h
0x180054fc1  mov     rax, cs:__security_cookie
0x180054fc8  xor     rax, rsp
0x180054fcb  mov     [rbp+3C0h+var_30], rax
0x180054fd2  mov     rdi, rcx
0x180054fd5  mov     [rsp+4C0h+var_490], 0
0x180054fda  lea     rcx, [rbp+3C0h+NameBuffer]; void *
0x180054fde  xor     edx, edx; Val
0x180054fe0  mov     r8d, 404h; Size
0x180054fe6  call    memset_0
0x180054feb  xorps   xmm0, xmm0
0x180054fee  mov     [rsp+4C0h+nSize], 202h
0x180054ff6  xor     eax, eax
0x180054ff8  lea     rcx, [rsp+4C0h+var_490]; this
0x180054ffd  mov     rdx, rdi; struct CNgscbToken *
0x180055000  mov     [rsp+4C0h+ProfileInfo.hProfile], rax
0x180055005  movups  xmmword ptr [rsp+4C0h+ProfileInfo.dwSize], xmm0
0x18005500a  movups  xmmword ptr [rsp+4C0h+ProfileInfo.lpProfilePath], xmm0
0x18005500f  movups  xmmword ptr [rsp+4C0h+ProfileInfo.lpServerName], xmm0
0x180055014  call    ?ImpersonateUser@CScopedImpersonation@@QEAAJAEBVCNgscbToken@@@Z; CScopedImpersonation::ImpersonateUser(CNgscbToken const &)
0x180055019  mov     ebx, eax
0x18005501b  mov     rcx, cs:WPP_GLOBAL_Control
0x180055022  lea     r15, WPP_GLOBAL_Control
0x180055029  cmp     rcx, r15
0x18005502c  jz      short loc_18005504C
0x18005502e  test    byte ptr [rcx+1Ch], 40h
0x180055032  jz      short loc_18005504C
0x180055034  mov     rcx, [rcx+10h]
0x180055038  lea     r8, WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids
0x18005503f  mov     edx, 0EDh
0x180055044  mov     r9d, eax
0x180055047  call    WPP_SF_d
0x18005504c  test    ebx, ebx
0x18005504e  jns     short loc_18005507C
0x180055050  mov     rcx, [rbp+3C8h]; this
0x180055057  lea     rax, aImpersonateuse; "ImpersonateUser"
0x18005505e  mov     r9d, ebx; char *
0x180055061  mov     qword ptr [rsp+4C0h+var_4A0], rax; int
0x180055066  lea     r8, aBaseNgscbCorne; "base\\ngscb\\cornerstone\\bdesvc\\svc\\"...
0x18005506d  mov     edx, 0CF5h; void *
0x180055072  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180055077  jmp     loc_1800551C8
0x18005507c  lea     r8, [rsp+4C0h+nSize]; nSize
0x180055081  mov     ecx, 2; NameFormat
0x180055086  lea     rdx, [rbp+3C0h+NameBuffer]; lpNameBuffer
0x18005508a  call    cs:__imp_GetUserNameExW
0x180055091  nop     dword ptr [rax+rax+00h]
0x180055096  test    al, al
0x180055098  jnz     short loc_180055100
0x18005509a  call    cs:__imp_GetLastError
0x1800550a1  nop     dword ptr [rax+rax+00h]
0x1800550a6  mov     ebx, eax
0x1800550a8  test    eax, eax
0x1800550aa  jle     short loc_1800550B5
0x1800550ac  movzx   ebx, ax
0x1800550af  or      ebx, 80070000h
0x1800550b5  mov     rcx, [rbp+3C8h]; this
0x1800550bc  lea     rax, aGetusernameexw_0; "GetUserNameExW"
0x1800550c3  mov     r9d, ebx; char *
0x1800550c6  mov     qword ptr [rsp+4C0h+var_4A0], rax; int
0x1800550cb  lea     r8, aBaseNgscbCorne; "base\\ngscb\\cornerstone\\bdesvc\\svc\\"...
0x1800550d2  mov     edx, 0CFAh; void *
0x1800550d7  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800550dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800550e3  cmp     rcx, r15
0x1800550e6  jz      loc_1800551C8
0x1800550ec  test    byte ptr [rcx+1Ch], 40h
0x1800550f0  jz      loc_1800551C8
0x1800550f6  mov     edx, 0EEh
0x1800550fb  jmp     loc_1800551B5
0x180055100  lea     rcx, [rsp+4C0h+var_490]; this
0x180055105  call    ?Revert@CScopedImpersonation@@QEAAJXZ; CScopedImpersonation::Revert(void)
0x18005510a  mov     edx, 5Ch ; '\'; Ch
0x18005510f  lea     rcx, [rbp+3C0h+NameBuffer]; Str
0x180055113  call    cs:__imp_wcschr
0x18005511a  nop     dword ptr [rax+rax+00h]
0x18005511f  test    rax, rax
0x180055122  jnz     short loc_18005512A
0x180055124  lea     rax, [rbp+3C0h+NameBuffer]
0x180055128  jmp     short loc_18005512E
0x18005512a  add     rax, 2
0x18005512e  mov     rcx, [rdi]; hToken
0x180055131  lea     rdx, [rsp+4C0h+ProfileInfo]; lpProfileInfo
0x180055136  mov     [rsp+4C0h+ProfileInfo.dwSize], 38h ; '8'
0x18005513e  mov     [rsp+4C0h+ProfileInfo.lpUserName], rax
0x180055143  mov     [rsp+4C0h+ProfileInfo.lpProfilePath], 0
0x18005514c  call    cs:__imp_LoadUserProfileW
0x180055153  nop     dword ptr [rax+rax+00h]
0x180055158  test    eax, eax
0x18005515a  jnz     short loc_1800551C8
0x18005515c  call    cs:__imp_GetLastError
0x180055163  nop     dword ptr [rax+rax+00h]
0x180055168  mov     ebx, eax
0x18005516a  test    eax, eax
0x18005516c  jle     short loc_180055177
0x18005516e  movzx   ebx, ax
0x180055171  or      ebx, 80070000h
0x180055177  mov     rcx, [rbp+3C8h]; this
0x18005517e  lea     rax, aLoaduserprofil_0; "LoadUserProfileW"
0x180055185  mov     r9d, ebx; char *
0x180055188  mov     qword ptr [rsp+4C0h+var_4A0], rax; int
0x18005518d  lea     r8, aBaseNgscbCorne; "base\\ngscb\\cornerstone\\bdesvc\\svc\\"...
0x180055194  mov     edx, 0D12h; void *
0x180055199  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18005519e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800551a5  cmp     rcx, r15
0x1800551a8  jz      short loc_1800551C8
0x1800551aa  test    byte ptr [rcx+1Ch], 40h
0x1800551ae  jz      short loc_1800551C8
0x1800551b0  mov     edx, 0EFh
0x1800551b5  mov     rcx, [rcx+10h]
0x1800551b9  lea     r8, WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids
0x1800551c0  mov     r9d, ebx
0x1800551c3  call    WPP_SF_d
0x1800551c8  mov     rdx, [rsp+4C0h+ProfileInfo.hProfile]; hProfile
0x1800551cd  test    rdx, rdx
0x1800551d0  jz      short loc_1800551E1
0x1800551d2  mov     rcx, [rdi]; hToken
0x1800551d5  call    cs:__imp_UnloadUserProfile
0x1800551dc  nop     dword ptr [rax+rax+00h]
0x1800551e1  lea     rcx, [rsp+4C0h+var_490]; this
0x1800551e6  call    ?Revert@CScopedImpersonation@@QEAAJXZ; CScopedImpersonation::Revert(void)
0x1800551eb  mov     eax, ebx
0x1800551ed  mov     rcx, [rbp+3C0h+var_30]
0x1800551f4  xor     rcx, rsp; StackCookie
0x1800551f7  call    __security_check_cookie
0x1800551fc  add     rsp, 4A8h
0x180055203  pop     r15
0x180055205  pop     rdi
0x180055206  pop     rbx
0x180055207  pop     rbp
0x180055208  retn
```
