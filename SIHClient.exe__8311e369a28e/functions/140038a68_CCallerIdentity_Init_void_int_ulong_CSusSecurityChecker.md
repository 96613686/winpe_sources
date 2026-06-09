# CCallerIdentity::Init(void *,int,ulong,CSusSecurityChecker *)

- ea: `0x140038a68`
- end: `0x140038c53`
- name: `?Init@CCallerIdentity@@QEAAJPEAXHKPEAVCSusSecurityChecker@@@Z`
- size: `491`
- prototype: `__int64 __fastcall(CCallerIdentity *__hidden this, void *, int, unsigned int, struct CSusSecurityChecker *)`
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001a10c`
- `0x14001fb74`
- `0x140022b60`

## callees

- `0x140008de4`
- `0x14000ce30`
- `0x14000d7e4`
- `0x140010698`
- `0x140038a68`
- `0x140038c5c`
- `0x140038fa4`
- `0x140039010`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140038b7c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140038b91`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140038b7c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140038b91`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x140038bbd`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x140038bbd`

## string_xrefs

- `0x140038aec`: `C:\__w\1\s\src\Client\Engine\lib\susenginelib\tokencache.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CCallerIdentity::Init(CCallerIdentity *this, void *a2)
{
  void **v3; // rsi
  unsigned int UserSidFromToken; // edi
  wil::details::in1diag3 *v5; // rcx
  __int64 v6; // rdx
  CCallerIdentity *v8; // rcx
  int DefAppsToken; // eax
  __int64 v10; // rdx
  __int64 v11; // rax
  HANDLE hObject; // [rsp+20h] [rbp-28h] BYREF
  int v13; // [rsp+28h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v13 = 0;
  CCallerIdentity::Uninit(this);
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_DWORD *)this + 32) = 0;
  v3 = (void **)((char *)this + 16);
  UserSidFromToken = GetUserSidFromToken(0, (_QWORD *)this + 2);
  v5 = retaddr;
  if ( (UserSidFromToken & 0x80000000) != 0 )
  {
    v6 = 230;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      v5,
      (void *)v6,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\susenginelib\\calleridentity.cpp",
      (const char *)UserSidFromToken,
      (int)hObject);
    return UserSidFromToken;
  }
  *((_DWORD *)this + 26) = 0;
  *((_DWORD *)this + 20) = -1;
  UserSidFromToken = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x14,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\susenginelib\\tokencache.cpp",
    (const char *)0x80070057LL,
    (int)hObject);
  if ( *((_DWORD *)this + 25) )
  {
    v5 = retaddr;
    v6 = 293;
    goto LABEL_3;
  }
  if ( CCallerIdentity::IsDefAppsTestHookEnabled(this) )
  {
    hObject = 0;
    DefAppsToken = CCallerIdentity::GetDefAppsToken(v8, &hObject);
    UserSidFromToken = DefAppsToken;
    if ( DefAppsToken < 0 )
    {
      v10 = 298;
      goto LABEL_12;
    }
    SusFree(*v3);
    *v3 = 0;
    DefAppsToken = GetUserSidFromToken(hObject, (_QWORD *)this + 2);
    UserSidFromToken = DefAppsToken;
    if ( DefAppsToken < 0 )
    {
      v10 = 300;
LABEL_12:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\susenginelib\\calleridentity.cpp",
        (const char *)(unsigned int)DefAppsToken,
        (int)hObject);
      if ( hObject )
        CloseHandle(hObject);
      return UserSidFromToken;
    }
    if ( hObject )
      CloseHandle(hObject);
  }
  if ( !*v3 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x134,
      (int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\susenginelib\\calleridentity.cpp",
      (const char *)0x80240FFFLL);
  if ( !IsValidSid(*v3) )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x135,
      (int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\susenginelib\\calleridentity.cpp",
      (const char *)0x80240FFFLL);
  if ( *((_DWORD *)this + 20) != -1 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x138,
      (int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\susenginelib\\calleridentity.cpp",
      (const char *)0x80240FFFLL);
  if ( *((_QWORD *)this + 14) )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x139,
      (int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\susenginelib\\calleridentity.cpp",
      (const char *)0x80240FFFLL);
  v11 = *((_QWORD *)this + 14);
  if ( !v11 )
    v11 = *((_QWORD *)this + 2);
  *((_QWORD *)this + 11) = v11;
  return 0;
}

```

## disassembly

```asm
0x140038a68  mov     [rsp+arg_8], rbx
0x140038a6d  mov     [rsp+arg_10], rbp
0x140038a72  mov     [rsp+arg_18], rsi
0x140038a77  push    rdi
0x140038a78  sub     rsp, 40h
0x140038a7c  mov     rax, cs:__security_cookie
0x140038a83  xor     rax, rsp
0x140038a86  mov     [rsp+48h+var_18], rax
0x140038a8b  mov     rbx, rcx
0x140038a8e  xor     ebp, ebp
0x140038a90  mov     [rsp+48h+var_20], ebp
0x140038a94  call    ?Uninit@CCallerIdentity@@QEAAXXZ; CCallerIdentity::Uninit(void)
0x140038a99  mov     [rbx], rbp
0x140038a9c  mov     [rbx+8], rbp
0x140038aa0  mov     [rbx+80h], ebp
0x140038aa6  lea     rsi, [rbx+10h]
0x140038aaa  mov     rdx, rsi
0x140038aad  xor     ecx, ecx; TokenHandle
0x140038aaf  call    GetUserSidFromToken
0x140038ab4  mov     edi, eax
0x140038ab6  mov     rcx, [rsp+48h]; this
0x140038abb  test    eax, eax
0x140038abd  jns     short loc_140038ADA
0x140038abf  mov     edx, 0E6h; void *
0x140038ac4  lea     r8, aCW1SSrcClientE_3; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x140038acb  mov     r9d, edi; char *
0x140038ace  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140038ad3  mov     eax, edi
0x140038ad5  jmp     loc_140038C31
0x140038ada  mov     [rbx+68h], ebp
0x140038add  mov     dword ptr [rbx+50h], 0FFFFFFFFh
0x140038ae4  mov     edi, 80070057h
0x140038ae9  mov     r9d, edi; char *
0x140038aec  lea     r8, aCW1SSrcClientE_2; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x140038af3  mov     edx, 14h; void *
0x140038af8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140038afd  cmp     [rbx+64h], ebp
0x140038b00  jz      short loc_140038B0E
0x140038b02  mov     rcx, [rsp+48h]
0x140038b07  mov     edx, 125h
0x140038b0c  jmp     short loc_140038AC4
0x140038b0e  mov     rcx, rbx; this
0x140038b11  call    ?IsDefAppsTestHookEnabled@CCallerIdentity@@AEBA_NXZ; CCallerIdentity::IsDefAppsTestHookEnabled(void)
0x140038b16  test    al, al
0x140038b18  jz      short loc_140038B97
0x140038b1a  mov     [rsp+48h+hObject], rbp; int
0x140038b1f  lea     rdx, [rsp+48h+hObject]; void **
0x140038b24  call    ?GetDefAppsToken@CCallerIdentity@@AEBAJPEAPEAX@Z; CCallerIdentity::GetDefAppsToken(void * *)
0x140038b29  mov     edi, eax
0x140038b2b  test    eax, eax
0x140038b2d  jns     short loc_140038B36
0x140038b2f  mov     edx, 12Ah
0x140038b34  jmp     short loc_140038B59
0x140038b36  mov     rcx, [rsi]; lpMem
0x140038b39  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140038b3e  mov     [rsi], rbp
0x140038b41  mov     rdx, rsi
0x140038b44  mov     rcx, [rsp+48h+hObject]; TokenHandle
0x140038b49  call    GetUserSidFromToken
0x140038b4e  mov     edi, eax
0x140038b50  test    eax, eax
0x140038b52  jns     short loc_140038B87
0x140038b54  mov     edx, 12Ch; void *
0x140038b59  mov     r9d, eax; char *
0x140038b5c  lea     r8, aCW1SSrcClientE_3; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x140038b63  mov     rcx, [rsp+48h]; this
0x140038b68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140038b6d  nop
0x140038b6e  mov     rcx, [rsp+48h+hObject]; hObject
0x140038b73  test    rcx, rcx
0x140038b76  jz      loc_140038AD3
0x140038b7c  call    cs:__imp_CloseHandle
0x140038b82  jmp     loc_140038AD3
0x140038b87  mov     rcx, [rsp+48h+hObject]; hObject
0x140038b8c  test    rcx, rcx
0x140038b8f  jz      short loc_140038B97
0x140038b91  call    cs:__imp_CloseHandle
0x140038b97  mov     edi, 80240FFFh
0x140038b9c  cmp     [rsi], rbp
0x140038b9f  jnz     short loc_140038BBA
0x140038ba1  mov     rcx, [rsp+48h]; this
0x140038ba6  mov     r9d, edi; char *
0x140038ba9  lea     r8, aCW1SSrcClientE_3; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x140038bb0  mov     edx, 134h; void *
0x140038bb5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140038bba  mov     rcx, [rsi]; pSid
0x140038bbd  call    cs:__imp_IsValidSid
0x140038bc3  test    eax, eax
0x140038bc5  jnz     short loc_140038BE0
0x140038bc7  mov     rcx, [rsp+48h]; this
0x140038bcc  mov     r9d, edi; char *
0x140038bcf  lea     r8, aCW1SSrcClientE_3; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x140038bd6  mov     edx, 135h; void *
0x140038bdb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140038be0  cmp     dword ptr [rbx+50h], 0FFFFFFFFh
0x140038be4  jz      short loc_140038BFF
0x140038be6  mov     rcx, [rsp+48h]; this
0x140038beb  mov     r9d, edi; char *
0x140038bee  lea     r8, aCW1SSrcClientE_3; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x140038bf5  mov     edx, 138h; void *
0x140038bfa  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140038bff  cmp     [rbx+70h], rbp
0x140038c03  jz      short loc_140038C1E
0x140038c05  mov     rcx, [rsp+48h]; this
0x140038c0a  mov     r9d, edi; char *
0x140038c0d  lea     r8, aCW1SSrcClientE_3; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x140038c14  mov     edx, 139h; void *
0x140038c19  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140038c1e  mov     rax, [rbx+70h]
0x140038c22  test    rax, rax
0x140038c25  jnz     short loc_140038C2B
0x140038c27  mov     rax, [rbx+10h]
0x140038c2b  mov     [rbx+58h], rax
0x140038c2f  xor     eax, eax
0x140038c31  mov     rcx, [rsp+48h+var_18]
0x140038c36  xor     rcx, rsp; StackCookie
0x140038c39  call    __security_check_cookie
0x140038c3e  mov     rbx, [rsp+48h+arg_8]
0x140038c43  mov     rbp, [rsp+48h+arg_10]
0x140038c48  mov     rsi, [rsp+48h+arg_18]
0x140038c4d  add     rsp, 40h
0x140038c51  pop     rdi
0x140038c52  retn
```
