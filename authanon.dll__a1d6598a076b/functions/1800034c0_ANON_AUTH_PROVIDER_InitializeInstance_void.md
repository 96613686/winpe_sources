# ANON_AUTH_PROVIDER::InitializeInstance(void)

- ea: `0x1800034c0`
- end: `0x180003609`
- name: `?InitializeInstance@ANON_AUTH_PROVIDER@@QEAAJXZ`
- size: `329`
- prototype: `__int64 __fastcall(ANON_AUTH_PROVIDER *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003f30`

## callees

- `0x1800034c0`
- `0x18000570c`
- `0x180005b70`
- `0x180006010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180003503`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180003503`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180003514`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180003514`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000351e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000351e`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000355b`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000357e`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000355b`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000357e`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800035cb`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800035cb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800035ae`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800035ae`

## pseudocode

```c
signed int __fastcall ANON_AUTH_PROVIDER::InitializeInstance(ANON_AUTH_PROVIDER *this)
{
  void **v1; // rbx
  signed int result; // eax
  HANDLE *v3; // rdi
  HANDLE CurrentProcess; // rax
  void *v5; // rcx
  DWORD ReturnLength[4]; // [rsp+30h] [rbp-88h] BYREF
  PSID TokenInformation[12]; // [rsp+40h] [rbp-78h] BYREF

  v1 = (void **)s_pAnonAuthProvider;
  result = IIS_LOGON_PROVIDER::InitializeInstance((wchar_t *)s_pAnonAuthProvider + 8);
  if ( result >= 0 )
  {
    v3 = v1 + 324;
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 0xF01FFu, v1 + 324)
      && (DuplicateTokenEx(*v3, 0, 0, SecurityDelegation, TokenImpersonation, v1 + 325)
       || DuplicateTokenEx(*v3, 0, 0, SecurityImpersonation, TokenImpersonation, v1 + 325))
      && (v5 = v1[325], ReturnLength[0] = 0, GetTokenInformation(v5, TokenUser, TokenInformation, 0x54u, ReturnLength)) )
    {
      CopySid(0x44u, v1 + 326, TokenInformation[0]);
      (*((void (__fastcall **)(void **, __int64))*v1 + 8))(v1, 1);
      return 0;
    }
    else
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800034c0  mov     [rsp+arg_0], rbx
0x1800034c5  mov     [rsp+arg_8], rsi
0x1800034ca  push    rdi
0x1800034cb  sub     rsp, 0B0h
0x1800034d2  mov     rax, cs:__security_cookie
0x1800034d9  xor     rax, rsp
0x1800034dc  mov     [rsp+0B8h+var_18], rax
0x1800034e4  mov     rbx, cs:?s_pAnonAuthProvider@@3PEAVANON_AUTH_PROVIDER@@EA; ANON_AUTH_PROVIDER * s_pAnonAuthProvider
0x1800034eb  lea     rcx, [rbx+10h]; Destination
0x1800034ef  call    ?InitializeInstance@IIS_LOGON_PROVIDER@@QEAAJXZ; IIS_LOGON_PROVIDER::InitializeInstance(void)
0x1800034f4  test    eax, eax
0x1800034f6  js      loc_1800035E4
0x1800034fc  lea     rdi, [rbx+0A20h]
0x180003503  call    cs:__imp_GetCurrentProcess
0x180003509  mov     r8, rdi; TokenHandle
0x18000350c  mov     edx, 0F01FFh; DesiredAccess
0x180003511  mov     rcx, rax; ProcessHandle
0x180003514  call    cs:__imp_OpenProcessToken
0x18000351a  test    eax, eax
0x18000351c  jnz     short loc_180003539
0x18000351e  call    cs:__imp_GetLastError
0x180003524  test    eax, eax
0x180003526  jle     loc_1800035E4
0x18000352c  movzx   eax, ax
0x18000352f  or      eax, 80070000h
0x180003534  jmp     loc_1800035E4
0x180003539  mov     rcx, [rdi]; hExistingToken
0x18000353c  lea     rsi, [rbx+0A28h]
0x180003543  mov     [rsp+0B8h+phNewToken], rsi; phNewToken
0x180003548  mov     r9d, 3; ImpersonationLevel
0x18000354e  xor     r8d, r8d; lpTokenAttributes
0x180003551  mov     [rsp+0B8h+TokenType], 2; TokenType
0x180003559  xor     edx, edx; dwDesiredAccess
0x18000355b  call    cs:__imp_DuplicateTokenEx
0x180003561  test    eax, eax
0x180003563  jnz     short loc_180003588
0x180003565  mov     rcx, [rdi]; hExistingToken
0x180003568  lea     r9d, [rax+2]; ImpersonationLevel
0x18000356c  mov     [rsp+0B8h+phNewToken], rsi; phNewToken
0x180003571  xor     r8d, r8d; lpTokenAttributes
0x180003574  xor     edx, edx; dwDesiredAccess
0x180003576  mov     [rsp+0B8h+TokenType], 2; TokenType
0x18000357e  call    cs:__imp_DuplicateTokenEx
0x180003584  test    eax, eax
0x180003586  jz      short loc_18000351E
0x180003588  mov     rcx, [rsi]; TokenHandle
0x18000358b  lea     rax, [rsp+0B8h+ReturnLength]
0x180003590  mov     r9d, 54h ; 'T'; TokenInformationLength
0x180003596  mov     [rsp+0B8h+ReturnLength], 0
0x18000359e  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x1800035a3  mov     qword ptr [rsp+0B8h+TokenType], rax; ReturnLength
0x1800035a8  lea     edi, [r9-53h]
0x1800035ac  mov     edx, edi; TokenInformationClass
0x1800035ae  call    cs:__imp_GetTokenInformation
0x1800035b4  test    eax, eax
0x1800035b6  jz      loc_18000351E
0x1800035bc  mov     r8, [rsp+0B8h+TokenInformation]; pSourceSid
0x1800035c1  lea     rdx, [rbx+0A30h]; pDestinationSid
0x1800035c8  lea     ecx, [rdi+43h]; nDestinationSidLength
0x1800035cb  call    cs:__imp_CopySid
0x1800035d1  mov     rax, [rbx]
0x1800035d4  mov     edx, edi
0x1800035d6  mov     rcx, rbx
0x1800035d9  mov     rax, [rax+40h]
0x1800035dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035e2  xor     eax, eax
0x1800035e4  mov     rcx, [rsp+0B8h+var_18]
0x1800035ec  xor     rcx, rsp; StackCookie
0x1800035ef  call    __security_check_cookie
0x1800035f4  lea     r11, [rsp+0B8h+var_8]
0x1800035fc  mov     rbx, [r11+10h]
0x180003600  mov     rsi, [r11+18h]
0x180003604  mov     rsp, r11
0x180003607  pop     rdi
0x180003608  retn
```
