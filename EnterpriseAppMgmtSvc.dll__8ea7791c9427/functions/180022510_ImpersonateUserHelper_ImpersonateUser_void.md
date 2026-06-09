# ImpersonateUserHelper::ImpersonateUser(void)

- ea: `0x180022510`
- end: `0x1800226e8`
- name: `?ImpersonateUser@ImpersonateUserHelper@@QEAAJXZ`
- size: `472`
- prototype: `int(ImpersonateUserHelper *__hidden this)`
- caller_count: `7`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001e394`
- `0x18001ffb0`
- `0x180022df8`
- `0x1800230e0`
- `0x180023c18`
- `0x180025c00`
- `0x180026d04`

## callees

- `0x180009a40`
- `0x18000cfc8`
- `0x18000cfe8`
- `0x180022510`
- `0x1800273c8`
- `0x180065790`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180022611`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002265d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180022692`
- `msvcrt!??3@YAXPEAX@Z` at `0x180022611`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002265d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180022692`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002259f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002259f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180022589`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180022589`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18002267c`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18002267c`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180022546`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180022546`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800225cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022672`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800226a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800225cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022672`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800226a7`
- `DMCmnUtils!DmImpersonate` at `0x1800226b1`
- `DMCmnUtils!DmImpersonate` at `0x1800226b1`

## string_xrefs

- `0x180022567`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\ImpersonateUserHelper.h`
- `0x1800225ad`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\ImpersonateUserHelper.h`
- `0x1800225f6`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\ImpersonateUserHelper.h`
- `0x180022643`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\ImpersonateUserHelper.h`

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
  __int64 v14; // r8
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
    token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>((void **)&v18, (__int64)TokenHandle);
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
0x180022510  mov     [rsp-18h+arg_0], rbx
0x180022515  push    rbp
0x180022516  push    rsi
0x180022517  push    rdi; int
0x180022518  mov     rbp, rsp
0x18002251b  sub     rsp, 20h
0x18002251f  mov     rdi, rcx
0x180022522  mov     eax, gs:179Ch
0x18002252a  test    eax, eax
0x18002252c  jz      short loc_18002253C
0x18002252e  mov     byte ptr [rcx+8], 0
0x180022532  mov     eax, 1
0x180022537  jmp     loc_1800226CD
0x18002253c  cmp     dword ptr [rcx+10h], 0
0x180022540  jnz     loc_1800226AD
0x180022546  call    cs:__imp_CoImpersonateClient
0x18002254c  mov     ebx, eax
0x18002254e  mov     eax, 80000000h
0x180022553  lea     ecx, [rbx+rax]
0x180022556  test    eax, ecx
0x180022558  jnz     short loc_180022581
0x18002255a  cmp     ebx, 80010117h
0x180022560  jz      short loc_180022581
0x180022562  mov     edx, 2Ah ; '*'; void *
0x180022567  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18002256e  mov     r9d, ebx; char *
0x180022571  mov     rcx, [rbp+18h]; this
0x180022575  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002257a  mov     eax, ebx
0x18002257c  jmp     loc_1800226CD
0x180022581  mov     [rbp+TokenHandle], 0
0x180022589  call    cs:__imp_GetCurrentThread
0x18002258f  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180022593  mov     edx, 8; DesiredAccess
0x180022598  lea     r8d, [rdx-7]; OpenAsSelf
0x18002259c  mov     rcx, rax; ThreadHandle
0x18002259f  call    cs:__imp_OpenThreadToken
0x1800225a5  test    eax, eax
0x1800225a7  jnz     short loc_1800225D4
0x1800225a9  mov     rcx, [rbp+18h]; this
0x1800225ad  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\appmodel\\enterprise"...
0x1800225b4  lea     edx, [rax+31h]; void *
0x1800225b7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800225bc  mov     ebx, eax
0x1800225be  mov     rcx, [rbp+TokenHandle]; hObject
0x1800225c2  lea     rdx, [rcx-1]
0x1800225c6  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800225ca  ja      short loc_18002257A
0x1800225cc  call    cs:__imp_CloseHandle
0x1800225d2  jmp     short loc_18002257A
0x1800225d4  mov     [rbp+arg_10], 0
0x1800225dc  mov     rdx, [rbp+TokenHandle]
0x1800225e0  lea     rcx, [rbp+arg_10]
0x1800225e4  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x1800225e9  mov     ebx, eax
0x1800225eb  test    eax, eax
0x1800225ed  jns     short loc_180022626
0x1800225ef  mov     rcx, [rbp+18h]; this
0x1800225f3  mov     r9d, eax; char *
0x1800225f6  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\appmodel\\enterprise"...
0x1800225fd  mov     edx, 34h ; '4'; void *
0x180022602  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022607  nop
0x180022608  mov     rcx, [rbp+arg_10]
0x18002260c  test    rcx, rcx
0x18002260f  jz      short loc_180022618
0x180022611  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180022617  nop
0x180022618  mov     rcx, [rbp+TokenHandle]
0x18002261c  lea     rax, [rcx-1]
0x180022620  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180022624  jmp     short loc_1800225CA
0x180022626  lea     rdx, [rdi+10h]; struct Common::StringBuffer *
0x18002262a  mov     rbx, [rbp+arg_10]
0x18002262e  mov     rcx, [rbx]; Sid
0x180022631  call    ?ConvertSidToString@SidHelper@Common@@SAJQEAXPEAVStringBuffer@2@@Z; Common::SidHelper::ConvertSidToString(void * const,Common::StringBuffer *)
0x180022636  mov     esi, eax
0x180022638  test    eax, eax
0x18002263a  jns     short loc_18002267C
0x18002263c  mov     rcx, [rbp+18h]; this
0x180022640  mov     r9d, eax; char *
0x180022643  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18002264a  mov     edx, 36h ; '6'; void *
0x18002264f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022654  nop
0x180022655  test    rbx, rbx
0x180022658  jz      short loc_180022664
0x18002265a  mov     rcx, rbx
0x18002265d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180022663  nop
0x180022664  mov     rcx, [rbp+TokenHandle]; hObject
0x180022668  lea     rax, [rcx-1]
0x18002266c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180022670  ja      short loc_180022678
0x180022672  call    cs:__imp_CloseHandle
0x180022678  mov     eax, esi
0x18002267a  jmp     short loc_1800226CD
0x18002267c  call    cs:__imp_CoRevertToSelf
0x180022682  mov     rcx, [rbp+18h]; this
0x180022686  test    eax, eax
0x180022688  js      short loc_1800226DA
0x18002268a  test    rbx, rbx
0x18002268d  jz      short loc_180022699
0x18002268f  mov     rcx, rbx
0x180022692  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180022698  nop
0x180022699  mov     rcx, [rbp+TokenHandle]; hObject
0x18002269d  lea     rax, [rcx-1]
0x1800226a1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800226a5  ja      short loc_1800226AD
0x1800226a7  call    cs:__imp_CloseHandle
0x1800226ad  mov     rcx, [rdi+18h]
0x1800226b1  call    cs:__imp_?DmImpersonate@@YAJPEBG@Z; DmImpersonate(ushort const *)
0x1800226b7  mov     ebx, eax
0x1800226b9  test    eax, eax
0x1800226bb  jns     short loc_1800226C7
0x1800226bd  mov     edx, 3Bh ; ';'
0x1800226c2  jmp     loc_180022567
0x1800226c7  mov     byte ptr [rdi+8], 1
0x1800226cb  xor     eax, eax
0x1800226cd  mov     rbx, [rsp+20h+arg_0]
0x1800226d2  add     rsp, 20h
0x1800226d6  pop     rdi
0x1800226d7  pop     rsi
0x1800226d8  pop     rbp
0x1800226d9  retn
0x1800226da  mov     r9d, eax; char *
0x1800226dd  mov     edx, 38h ; '8'; void *
0x1800226e2  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
