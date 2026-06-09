# Common::SidHelper::GetUserSidFromToken(void *,void * *)

- ea: `0x18002d3e0`
- end: `0x18002d51c`
- name: `?GetUserSidFromToken@SidHelper@Common@@SAJPEAXPEAPEAX@Z`
- size: `316`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180026888`

## callees

- `0x180003d50`
- `0x1800043a8`
- `0x180007f70`
- `0x18000a3a0`
- `0x18000a3c0`
- `0x18002d3e0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002d4bf`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002d4bf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002d43e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002d49a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002d43e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002d49a`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18002d4d9`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18002d4d9`

## string_xrefs

- `0x18002d402`: `onecore\base\appmodel\common\sidhelper.cpp`
- `0x18002d461`: `onecore\base\appmodel\common\sidhelper.cpp`
- `0x18002d4a9`: `onecore\base\appmodel\common\sidhelper.cpp`
- `0x18002d4e8`: `onecore\base\appmodel\common\sidhelper.cpp`

## pseudocode

```c
__int64 __fastcall Common::SidHelper::GetUserSidFromToken(HANDLE TokenHandle, void **a2)
{
  __int64 v4; // rdx
  unsigned int LastError; // ebx
  const char *v6; // r9
  PSID *v8; // r14
  const char *v9; // r9
  unsigned __int64 v10; // rdx
  DWORD LengthSid; // ebx
  void *v12; // rsi
  const char *v13; // r9
  unsigned __int64 v14; // rdx
  int ReturnLength; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  DWORD TokenInformationLength; // [rsp+60h] [rbp+8h] BYREF

  if ( !TokenHandle )
  {
    v4 = 71;
LABEL_3:
    LastError = -2147024809;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\base\\appmodel\\common\\sidhelper.cpp",
      (const char *)LastError,
      ReturnLength);
    return LastError;
  }
  if ( !a2 )
  {
    v4 = 72;
    goto LABEL_3;
  }
  TokenInformationLength = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
  {
    LastError = -2147418113;
    v4 = 75;
    goto LABEL_4;
  }
  if ( GetLastError_0() != 122 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x4C,
             (unsigned int)"onecore\\base\\appmodel\\common\\sidhelper.cpp",
             v6);
  v8 = (PSID *)operator new[](TokenInformationLength);
  if ( GetTokenInformation(TokenHandle, TokenUser, v8, TokenInformationLength, &TokenInformationLength) )
  {
    LengthSid = GetLengthSid(*v8);
    v12 = operator new[](LengthSid);
    if ( CopySid(LengthSid, v12, *v8) )
    {
      *a2 = v12;
      LastError = 0;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x56,
                    (unsigned int)"onecore\\base\\appmodel\\common\\sidhelper.cpp",
                    v13);
      operator delete(v12, v14);
    }
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x50,
                  (unsigned int)"onecore\\base\\appmodel\\common\\sidhelper.cpp",
                  v9);
  }
  operator delete(v8, v10);
  return LastError;
}

```

## disassembly

```asm
0x18002d3e0  push    rbx
0x18002d3e2  push    rsi
0x18002d3e3  push    rdi
0x18002d3e4  push    r14
0x18002d3e6  sub     rsp, 38h
0x18002d3ea  mov     rdi, rdx
0x18002d3ed  mov     rbx, rcx
0x18002d3f0  test    rcx, rcx
0x18002d3f3  jnz     short loc_18002D416
0x18002d3f5  lea     edx, [rcx+47h]; void *
0x18002d3f8  mov     ebx, 80070057h
0x18002d3fd  mov     rcx, [rsp+58h]; this
0x18002d402  lea     r8, aOnecoreBaseApp_35; "onecore\\base\\appmodel\\common\\sidhel"...
0x18002d409  mov     r9d, ebx; char *
0x18002d40c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d411  jmp     loc_18002D510
0x18002d416  test    rdi, rdi
0x18002d419  jnz     short loc_18002D420
0x18002d41b  lea     edx, [rdi+48h]
0x18002d41e  jmp     short loc_18002D3F8
0x18002d420  xor     r9d, r9d; TokenInformationLength
0x18002d423  mov     [rsp+58h+TokenInformationLength], 0
0x18002d42b  lea     rax, [rsp+58h+TokenInformationLength]
0x18002d430  xor     r8d, r8d; TokenInformation
0x18002d433  mov     qword ptr [rsp+58h+ReturnLength], rax; ReturnLength
0x18002d438  lea     esi, [r9+1]
0x18002d43c  mov     edx, esi; TokenInformationClass
0x18002d43e  call    cs:__imp_GetTokenInformation
0x18002d444  test    eax, eax
0x18002d446  jz      short loc_18002D452
0x18002d448  mov     ebx, 8000FFFFh
0x18002d44d  lea     edx, [rsi+4Ah]
0x18002d450  jmp     short loc_18002D3FD
0x18002d452  call    GetLastError_0
0x18002d457  cmp     eax, 7Ah ; 'z'
0x18002d45a  jz      short loc_18002D477
0x18002d45c  mov     rcx, [rsp+58h]; this
0x18002d461  lea     r8, aOnecoreBaseApp_35; "onecore\\base\\appmodel\\common\\sidhel"...
0x18002d468  mov     edx, 4Ch ; 'L'; void *
0x18002d46d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002d472  jmp     loc_18002D512
0x18002d477  mov     ecx, [rsp+58h+TokenInformationLength]; unsigned __int64
0x18002d47b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002d480  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x18002d485  mov     r14, rax
0x18002d488  lea     rax, [rsp+58h+TokenInformationLength]
0x18002d48d  mov     r8, r14; TokenInformation
0x18002d490  mov     edx, esi; TokenInformationClass
0x18002d492  mov     qword ptr [rsp+58h+ReturnLength], rax; ReturnLength
0x18002d497  mov     rcx, rbx; TokenHandle
0x18002d49a  call    cs:__imp_GetTokenInformation
0x18002d4a0  test    eax, eax
0x18002d4a2  jnz     short loc_18002D4BC
0x18002d4a4  mov     rcx, [rsp+58h]; this
0x18002d4a9  lea     r8, aOnecoreBaseApp_35; "onecore\\base\\appmodel\\common\\sidhel"...
0x18002d4b0  lea     edx, [rax+50h]; void *
0x18002d4b3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002d4b8  mov     ebx, eax
0x18002d4ba  jmp     short loc_18002D508
0x18002d4bc  mov     rcx, [r14]; pSid
0x18002d4bf  call    cs:__imp_GetLengthSid
0x18002d4c5  mov     ecx, eax; unsigned __int64
0x18002d4c7  mov     ebx, eax
0x18002d4c9  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002d4ce  mov     r8, [r14]; pSourceSid
0x18002d4d1  mov     rdx, rax; pDestinationSid
0x18002d4d4  mov     ecx, ebx; nDestinationSidLength
0x18002d4d6  mov     rsi, rax
0x18002d4d9  call    cs:__imp_CopySid
0x18002d4df  test    eax, eax
0x18002d4e1  jnz     short loc_18002D503
0x18002d4e3  mov     rcx, [rsp+58h]; this
0x18002d4e8  lea     r8, aOnecoreBaseApp_35; "onecore\\base\\appmodel\\common\\sidhel"...
0x18002d4ef  lea     edx, [rax+56h]; void *
0x18002d4f2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002d4f7  mov     rcx, rsi; void *
0x18002d4fa  mov     ebx, eax
0x18002d4fc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002d501  jmp     short loc_18002D508
0x18002d503  mov     [rdi], rsi
0x18002d506  xor     ebx, ebx
0x18002d508  mov     rcx, r14; void *
0x18002d50b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002d510  mov     eax, ebx
0x18002d512  add     rsp, 38h
0x18002d516  pop     r14
0x18002d518  pop     rdi
0x18002d519  pop     rsi
0x18002d51a  pop     rbx
0x18002d51b  retn
```
