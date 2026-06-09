# CSession::_InitToken(void)

- ea: `0x18000f010`
- end: `0x18000f12f`
- name: `?_InitToken@CSession@@AEAAJXZ`
- size: `287`
- prototype: `__int64 __fastcall(void **this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000d754`

## callees

- `0x18000c7cc`
- `0x18000cadc`
- `0x18000ccd4`
- `0x18000f010`
- `0x18001e020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f09f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f0e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f09f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f0e2`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000f0d8`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000f0d8`
- `WTSAPI32!WTSQueryUserToken` at `0x18000f095`
- `WTSAPI32!WTSQueryUserToken` at `0x18000f095`

## string_xrefs

- `0x18000f02e`: `CSession::_InitToken`

## pseudocode

```c
__int64 __fastcall CSession::_InitToken(void **this)
{
  ULONG v2; // ecx
  signed int v3; // eax
  unsigned int v4; // ebx
  signed int LastError; // eax
  unsigned int v7; // [rsp+30h] [rbp-50h] BYREF
  int v8; // [rsp+34h] [rbp-4Ch] BYREF
  void *phToken; // [rsp+38h] [rbp-48h] BYREF
  _QWORD *v10; // [rsp+40h] [rbp-40h] BYREF
  _QWORD v11[3]; // [rsp+48h] [rbp-38h] BYREF
  char v12[24]; // [rsp+60h] [rbp-20h] BYREF

  v11[0] = v12;
  v11[1] = &v8;
  strcpy(v12, "CSession::_InitToken");
  v11[2] = &v7;
  v7 = 0;
  v8 = 0;
  lambda_3b30f6966661b124bbdd0ab0ef31d9ec_::operator()(v11);
  v2 = *(_DWORD *)this;
  v10 = v11;
  v8 = 1;
  phToken = 0;
  if ( WTSQueryUserToken(v2, &phToken) )
  {
    if ( DuplicateTokenEx(phToken, 0xEu, 0, SecurityImpersonation, TokenImpersonation, this + 3) )
    {
      v4 = v7;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v7 = LastError;
      v4 = LastError;
    }
  }
  else
  {
    v3 = GetLastError();
    v4 = v3;
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
    v7 = v4;
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phToken);
  WppTraceUnwinder__lambda_3b30f6966661b124bbdd0ab0ef31d9ec____::_WppTraceUnwinder__lambda_3b30f6966661b124bbdd0ab0ef31d9ec____(&v10);
  return v4;
}

```

## disassembly

```asm
0x18000f010  mov     [rsp-8+arg_8], rbx
0x18000f015  push    rbp
0x18000f016  mov     rbp, rsp
0x18000f019  sub     rsp, 80h
0x18000f020  mov     rax, cs:__security_cookie
0x18000f027  xor     rax, rsp
0x18000f02a  mov     [rbp+var_8], rax
0x18000f02e  movups  xmm0, xmmword ptr cs:aCsessionInitto; "CSession::_InitToken"
0x18000f035  lea     rax, [rbp+var_20]
0x18000f039  mov     rbx, rcx
0x18000f03c  movsd   xmm1, qword ptr cs:aCsessionInitto+0Dh; "itToken"
0x18000f044  lea     rcx, [rbp+var_38]
0x18000f048  mov     [rbp+var_38], rax
0x18000f04c  lea     rax, [rbp+var_4C]
0x18000f050  mov     [rbp+var_30], rax
0x18000f054  lea     rax, [rbp+var_50]
0x18000f058  movups  xmmword ptr [rbp+var_20], xmm0
0x18000f05c  mov     [rbp+var_28], rax
0x18000f060  mov     [rbp+var_50], 0
0x18000f067  mov     [rbp+var_4C], 0
0x18000f06e  movsd   qword ptr [rbp+var_20+0Dh], xmm1
0x18000f073  call    _lambda_3b30f6966661b124bbdd0ab0ef31d9ec___operator__
0x18000f078  mov     ecx, [rbx]; SessionId
0x18000f07a  lea     rax, [rbp+var_38]
0x18000f07e  lea     rdx, [rbp+phToken]; phToken
0x18000f082  mov     [rbp+var_40], rax
0x18000f086  mov     [rbp+var_4C], 1
0x18000f08d  mov     [rbp+phToken], 0
0x18000f095  call    cs:__imp_WTSQueryUserToken
0x18000f09b  test    eax, eax
0x18000f09d  jnz     short loc_18000F0B9
0x18000f09f  call    cs:__imp_GetLastError
0x18000f0a5  mov     ebx, eax
0x18000f0a7  test    eax, eax
0x18000f0a9  jle     short loc_18000F0B4
0x18000f0ab  movzx   ebx, ax
0x18000f0ae  or      ebx, 80070000h
0x18000f0b4  mov     [rbp+var_50], ebx
0x18000f0b7  jmp     short loc_18000F0FE
0x18000f0b9  mov     rcx, [rbp+phToken]; hExistingToken
0x18000f0bd  lea     rax, [rbx+18h]
0x18000f0c1  mov     r9d, 2; ImpersonationLevel
0x18000f0c7  mov     [rsp+80h+phNewToken], rax; phNewToken
0x18000f0cc  xor     r8d, r8d; lpTokenAttributes
0x18000f0cf  mov     [rsp+80h+TokenType], r9d; TokenType
0x18000f0d4  lea     edx, [r9+0Ch]; dwDesiredAccess
0x18000f0d8  call    cs:__imp_DuplicateTokenEx
0x18000f0de  test    eax, eax
0x18000f0e0  jnz     short loc_18000F0FB
0x18000f0e2  call    cs:__imp_GetLastError
0x18000f0e8  test    eax, eax
0x18000f0ea  jle     short loc_18000F0F4
0x18000f0ec  movzx   eax, ax
0x18000f0ef  or      eax, 80070000h
0x18000f0f4  mov     [rbp+var_50], eax
0x18000f0f7  mov     ebx, eax
0x18000f0f9  jmp     short loc_18000F0FE
0x18000f0fb  mov     ebx, [rbp+var_50]
0x18000f0fe  lea     rcx, [rbp+phToken]
0x18000f102  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000f107  lea     rcx, [rbp+var_40]
0x18000f10b  call    WppTraceUnwinder__lambda_3b30f6966661b124bbdd0ab0ef31d9ec_______WppTraceUnwinder__lambda_3b30f6966661b124bbdd0ab0ef31d9ec____
0x18000f110  mov     eax, ebx
0x18000f112  mov     rcx, [rbp+var_8]
0x18000f116  xor     rcx, rsp; StackCookie
0x18000f119  call    __security_check_cookie
0x18000f11e  mov     rbx, [rsp+80h+arg_8]
0x18000f126  add     rsp, 80h
0x18000f12d  pop     rbp
0x18000f12e  retn
```
