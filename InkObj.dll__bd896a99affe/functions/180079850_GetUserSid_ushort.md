# GetUserSid(ushort * *)

- ea: `0x180079850`
- end: `0x180079945`
- name: `?GetUserSid@@YAJPEAPEAG@Z`
- size: `245`
- prototype: `__int64 __fastcall(LPWSTR *StringSid)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180078bf8`
- `0x180078ed0`

## callees

- `0x180002740`
- `0x180010350`
- `0x180079850`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800798cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800798cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007987f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007987f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180079892`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180079892`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007992d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007992d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800798c1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180079903`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800798c1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180079903`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180079913`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180079913`

## pseudocode

```c
__int64 __fastcall GetUserSid(LPWSTR *StringSid)
{
  unsigned int v3; // edi
  HANDLE CurrentProcess; // rax
  PSID *v5; // rbx
  DWORD TokenInformationLength; // [rsp+40h] [rbp+8h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp+10h] BYREF

  if ( !StringSid )
    return 2147500035LL;
  v3 = -2147467259;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    TokenInformationLength = 0;
    if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) && GetLastError() == 122 )
    {
      v5 = (PSID *)WinMalloc(TokenInformationLength);
      if ( v5 )
      {
        if ( GetTokenInformation(TokenHandle, TokenUser, v5, TokenInformationLength, &TokenInformationLength) )
        {
          if ( ConvertSidToStringSidW(*v5, StringSid) )
            v3 = 0;
        }
        WinFree(v5);
      }
    }
    CloseHandle(TokenHandle);
  }
  return v3;
}

```

## disassembly

```asm
0x180079850  mov     [rsp+arg_10], rbx
0x180079855  mov     [rsp+arg_18], rsi
0x18007985a  push    rdi
0x18007985b  sub     rsp, 30h
0x18007985f  mov     rsi, rcx
0x180079862  test    rcx, rcx
0x180079865  jnz     short loc_180079871
0x180079867  mov     eax, 80004003h
0x18007986c  jmp     loc_180079935
0x180079871  mov     edi, 80004005h
0x180079876  mov     [rsp+38h+TokenHandle], 0
0x18007987f  call    cs:__imp_GetCurrentProcess
0x180079885  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x18007988a  mov     edx, 8; DesiredAccess
0x18007988f  mov     rcx, rax; ProcessHandle
0x180079892  call    cs:__imp_OpenProcessToken
0x180079898  test    eax, eax
0x18007989a  jz      loc_180079933
0x1800798a0  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x1800798a5  lea     rax, [rsp+38h+TokenInformationLength]
0x1800798aa  xor     r9d, r9d; TokenInformationLength
0x1800798ad  mov     [rsp+38h+TokenInformationLength], 0
0x1800798b5  xor     r8d, r8d; TokenInformation
0x1800798b8  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800798bd  lea     edx, [r9+1]; TokenInformationClass
0x1800798c1  call    cs:__imp_GetTokenInformation
0x1800798c7  test    eax, eax
0x1800798c9  jnz     short loc_180079928
0x1800798cb  call    cs:__imp_GetLastError
0x1800798d1  cmp     eax, 7Ah ; 'z'
0x1800798d4  jnz     short loc_180079928
0x1800798d6  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x1800798da  call    ?WinMalloc@@YAPEAX_K@Z; WinMalloc(unsigned __int64)
0x1800798df  mov     rbx, rax
0x1800798e2  test    rax, rax
0x1800798e5  jz      short loc_180079928
0x1800798e7  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x1800798ec  lea     rax, [rsp+38h+TokenInformationLength]
0x1800798f1  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x1800798f6  mov     r8, rbx; TokenInformation
0x1800798f9  mov     edx, 1; TokenInformationClass
0x1800798fe  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180079903  call    cs:__imp_GetTokenInformation
0x180079909  test    eax, eax
0x18007990b  jz      short loc_180079920
0x18007990d  mov     rcx, [rbx]; Sid
0x180079910  mov     rdx, rsi; StringSid
0x180079913  call    cs:__imp_ConvertSidToStringSidW
0x180079919  xor     ecx, ecx
0x18007991b  test    eax, eax
0x18007991d  cmovnz  edi, ecx
0x180079920  mov     rcx, rbx; void *
0x180079923  call    ?WinFree@@YAXPEAX@Z; WinFree(void *)
0x180079928  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x18007992d  call    cs:__imp_CloseHandle
0x180079933  mov     eax, edi
0x180079935  mov     rbx, [rsp+38h+arg_10]
0x18007993a  mov     rsi, [rsp+38h+arg_18]
0x18007993f  add     rsp, 30h
0x180079943  pop     rdi
0x180079944  retn
```
