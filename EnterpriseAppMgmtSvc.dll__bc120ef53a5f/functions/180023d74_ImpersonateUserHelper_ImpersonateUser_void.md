# ImpersonateUserHelper::ImpersonateUser(void)

- ea: `0x180023d74`
- end: `0x180023f8f`
- name: `?ImpersonateUser@ImpersonateUserHelper@@QEAAJXZ`
- size: `539`
- prototype: `int(ImpersonateUserHelper *__hidden this)`
- caller_count: `7`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001f908`
- `0x180021650`
- `0x1800246b8`
- `0x1800249d8`
- `0x1800255ec`
- `0x1800277c0`
- `0x180028d10`

## callees

- `0x180009d14`
- `0x18000d3bc`
- `0x18000d3dc`
- `0x180023d74`
- `0x180029444`
- `0x18006b158`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180023e8d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180023edf`
- `msvcrt!??3@YAXPEAX@Z` at `0x180023f26`
- `msvcrt!??3@YAXPEAX@Z` at `0x180023e8d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180023edf`
- `msvcrt!??3@YAXPEAX@Z` at `0x180023f26`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180023e0f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180023e0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180023df3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180023df3`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180023f0a`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180023f0a`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180023daa`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180023daa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023e42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023efa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023f41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023e42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023efa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023f41`
- `DMCmnUtils!DmImpersonate` at `0x180023f51`
- `DMCmnUtils!DmImpersonate` at `0x180023f51`

## string_xrefs

- `0x180023dd1`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\ImpersonateUserHelper.h`
- `0x180023e23`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\ImpersonateUserHelper.h`
- `0x180023e72`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\ImpersonateUserHelper.h`
- `0x180023ec5`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\ImpersonateUserHelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
ImpersonateUser *__fastcall ImpersonateUserHelper::ImpersonateUser(ImpersonateUser *this)
{
  unsigned int LastError; // ebx
  __int64 v4; // rdx
  HANDLE CurrentThread; // rax
  const char *v6; // r9
  void *v7; // rcx
  bool v8; // cc
  int token_information; // eax
  PSID *v10; // rbx
  int v11; // eax
  unsigned int v12; // esi
  HRESULT v13; // eax
  unsigned int v14; // r8d
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  void *TokenHandle; // [rsp+48h] [rbp+28h] BYREF
  PSID *v18; // [rsp+50h] [rbp+30h] BYREF

  if ( NtCurrentTeb()->IsImpersonating )
  {
    *((_BYTE *)this + 8) = 0;
    return (ImpersonateUser *)1;
  }
  if ( !*((_DWORD *)this + 4) )
  {
    LastError = CoImpersonateClient();
    if ( (int)(LastError + 0x80000000) >= 0 && LastError != -2147417833 )
    {
      v4 = 42;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v4,
        (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\ImpersonateUserHelper.h",
        (const char *)LastError,
        savedregs);
      return (ImpersonateUser *)LastError;
    }
    TokenHandle = 0;
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x31,
                    (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt"
                                  "\\ImpersonateUserHelper.h",
                    v6);
      v7 = TokenHandle;
      v8 = (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
LABEL_11:
      if ( v8 )
        CloseHandle(v7);
      return (ImpersonateUser *)LastError;
    }
    v18 = 0;
    token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&v18, TokenHandle);
    LastError = token_information;
    if ( token_information < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x34,
        (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\ImpersonateUserHelper.h",
        (const char *)(unsigned int)token_information,
        savedregs);
      if ( v18 )
        operator delete(v18);
      v7 = TokenHandle;
      v8 = (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
      goto LABEL_11;
    }
    v10 = v18;
    v11 = Common::SidHelper::ConvertSidToString(*v18, (ImpersonateUser *)((char *)this + 16));
    v12 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x36,
        (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\ImpersonateUserHelper.h",
        (const char *)(unsigned int)v11,
        savedregs);
      if ( v10 )
        operator delete(v10);
      if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(TokenHandle);
      return (ImpersonateUser *)v12;
    }
    v13 = CoRevertToSelf();
    if ( v13 < 0 )
      wil::details::in1diag3::_FailFast_Hr(retaddr, (void *)0x38, v14, (const char *)(unsigned int)v13, savedregs);
    if ( v10 )
      operator delete(v10);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
  }
  LastError = DmImpersonate(*((const unsigned __int16 **)this + 3));
  if ( (LastError & 0x80000000) != 0 )
  {
    v4 = 59;
    goto LABEL_7;
  }
  *((_BYTE *)this + 8) = 1;
  return 0;
}

```

## disassembly

```asm
0x180023d74  mov     [rsp-18h+arg_0], rbx
0x180023d79  push    rbp
0x180023d7a  push    rsi
0x180023d7b  push    rdi; int
0x180023d7c  mov     rbp, rsp
0x180023d7f  sub     rsp, 20h
0x180023d83  mov     rdi, rcx
0x180023d86  mov     eax, gs:179Ch
0x180023d8e  test    eax, eax
0x180023d90  jz      short loc_180023DA0
0x180023d92  mov     byte ptr [rcx+8], 0
0x180023d96  mov     eax, 1
0x180023d9b  jmp     loc_180023F73
0x180023da0  cmp     dword ptr [rcx+10h], 0
0x180023da4  jnz     loc_180023F4D
0x180023daa  call    cs:__imp_CoImpersonateClient
0x180023db1  nop     dword ptr [rax+rax+00h]
0x180023db6  mov     ebx, eax
0x180023db8  mov     eax, 80000000h
0x180023dbd  lea     ecx, [rbx+rax]
0x180023dc0  test    eax, ecx
0x180023dc2  jnz     short loc_180023DEB
0x180023dc4  cmp     ebx, 80010117h
0x180023dca  jz      short loc_180023DEB
0x180023dcc  mov     edx, 2Ah ; '*'; void *
0x180023dd1  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180023dd8  mov     r9d, ebx; char *
0x180023ddb  mov     rcx, [rbp+18h]; this
0x180023ddf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023de4  mov     eax, ebx
0x180023de6  jmp     loc_180023F73
0x180023deb  mov     [rbp+TokenHandle], 0
0x180023df3  call    cs:__imp_GetCurrentThread
0x180023dfa  nop     dword ptr [rax+rax+00h]
0x180023dff  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180023e03  mov     edx, 8; DesiredAccess
0x180023e08  lea     r8d, [rdx-7]; OpenAsSelf
0x180023e0c  mov     rcx, rax; ThreadHandle
0x180023e0f  call    cs:__imp_OpenThreadToken
0x180023e16  nop     dword ptr [rax+rax+00h]
0x180023e1b  test    eax, eax
0x180023e1d  jnz     short loc_180023E50
0x180023e1f  mov     rcx, [rbp+18h]; this
0x180023e23  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180023e2a  lea     edx, [rax+31h]; void *
0x180023e2d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180023e32  mov     ebx, eax
0x180023e34  mov     rcx, [rbp+TokenHandle]; hObject
0x180023e38  lea     rdx, [rcx-1]
0x180023e3c  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180023e40  ja      short loc_180023DE4
0x180023e42  call    cs:__imp_CloseHandle
0x180023e49  nop     dword ptr [rax+rax+00h]
0x180023e4e  jmp     short loc_180023DE4
0x180023e50  mov     [rbp+arg_10], 0
0x180023e58  mov     rdx, [rbp+TokenHandle]
0x180023e5c  lea     rcx, [rbp+arg_10]
0x180023e60  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x180023e65  mov     ebx, eax
0x180023e67  test    eax, eax
0x180023e69  jns     short loc_180023EA8
0x180023e6b  mov     rcx, [rbp+18h]; this
0x180023e6f  mov     r9d, eax; char *
0x180023e72  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180023e79  mov     edx, 34h ; '4'; void *
0x180023e7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023e83  nop
0x180023e84  mov     rcx, [rbp+arg_10]
0x180023e88  test    rcx, rcx
0x180023e8b  jz      short loc_180023E9A
0x180023e8d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180023e94  nop     dword ptr [rax+rax+00h]
0x180023e99  nop
0x180023e9a  mov     rcx, [rbp+TokenHandle]
0x180023e9e  lea     rax, [rcx-1]
0x180023ea2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180023ea6  jmp     short loc_180023E40
0x180023ea8  lea     rdx, [rdi+10h]; struct Common::StringBuffer *
0x180023eac  mov     rbx, [rbp+arg_10]
0x180023eb0  mov     rcx, [rbx]; Sid
0x180023eb3  call    ?ConvertSidToString@SidHelper@Common@@SAJQEAXPEAVStringBuffer@2@@Z; Common::SidHelper::ConvertSidToString(void * const,Common::StringBuffer *)
0x180023eb8  mov     esi, eax
0x180023eba  test    eax, eax
0x180023ebc  jns     short loc_180023F0A
0x180023ebe  mov     rcx, [rbp+18h]; this
0x180023ec2  mov     r9d, eax; char *
0x180023ec5  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180023ecc  mov     edx, 36h ; '6'; void *
0x180023ed1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023ed6  nop
0x180023ed7  test    rbx, rbx
0x180023eda  jz      short loc_180023EEC
0x180023edc  mov     rcx, rbx
0x180023edf  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180023ee6  nop     dword ptr [rax+rax+00h]
0x180023eeb  nop
0x180023eec  mov     rcx, [rbp+TokenHandle]; hObject
0x180023ef0  lea     rax, [rcx-1]
0x180023ef4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180023ef8  ja      short loc_180023F06
0x180023efa  call    cs:__imp_CloseHandle
0x180023f01  nop     dword ptr [rax+rax+00h]
0x180023f06  mov     eax, esi
0x180023f08  jmp     short loc_180023F73
0x180023f0a  call    cs:__imp_CoRevertToSelf
0x180023f11  nop     dword ptr [rax+rax+00h]
0x180023f16  mov     rcx, [rbp+18h]; this
0x180023f1a  test    eax, eax
0x180023f1c  js      short loc_180023F81
0x180023f1e  test    rbx, rbx
0x180023f21  jz      short loc_180023F33
0x180023f23  mov     rcx, rbx
0x180023f26  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180023f2d  nop     dword ptr [rax+rax+00h]
0x180023f32  nop
0x180023f33  mov     rcx, [rbp+TokenHandle]; hObject
0x180023f37  lea     rax, [rcx-1]
0x180023f3b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180023f3f  ja      short loc_180023F4D
0x180023f41  call    cs:__imp_CloseHandle
0x180023f48  nop     dword ptr [rax+rax+00h]
0x180023f4d  mov     rcx, [rdi+18h]
0x180023f51  call    cs:__imp_?DmImpersonate@@YAJPEBG@Z; DmImpersonate(ushort const *)
0x180023f58  nop     dword ptr [rax+rax+00h]
0x180023f5d  mov     ebx, eax
0x180023f5f  test    eax, eax
0x180023f61  jns     short loc_180023F6D
0x180023f63  mov     edx, 3Bh ; ';'
0x180023f68  jmp     loc_180023DD1
0x180023f6d  mov     byte ptr [rdi+8], 1
0x180023f71  xor     eax, eax
0x180023f73  mov     rbx, [rsp+20h+arg_0]
0x180023f78  add     rsp, 20h
0x180023f7c  pop     rdi
0x180023f7d  pop     rsi
0x180023f7e  pop     rbp
0x180023f7f  retn
0x180023f81  mov     r9d, eax; char *
0x180023f84  mov     edx, 38h ; '8'; void *
0x180023f89  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
