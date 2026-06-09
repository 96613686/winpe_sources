# GetMandatoryLabel(ushort * *)

- ea: `0x180079754`
- end: `0x180079849`
- name: `?GetMandatoryLabel@@YAJPEAPEAG@Z`
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
- `0x180079754`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800797cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800797cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180079783`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180079783`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180079796`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180079796`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180079831`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180079831`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800797c5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180079807`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800797c5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180079807`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180079817`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180079817`

## pseudocode

```c
__int64 __fastcall GetMandatoryLabel(LPWSTR *StringSid)
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
    if ( !GetTokenInformation(TokenHandle, TokenIntegrityLevel, 0, 0, &TokenInformationLength) && GetLastError() == 122 )
    {
      v5 = (PSID *)WinMalloc(TokenInformationLength);
      if ( v5 )
      {
        if ( GetTokenInformation(TokenHandle, TokenIntegrityLevel, v5, TokenInformationLength, &TokenInformationLength) )
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
0x180079754  mov     [rsp+arg_10], rbx
0x180079759  mov     [rsp+arg_18], rsi
0x18007975e  push    rdi
0x18007975f  sub     rsp, 30h
0x180079763  mov     rsi, rcx
0x180079766  test    rcx, rcx
0x180079769  jnz     short loc_180079775
0x18007976b  mov     eax, 80004003h
0x180079770  jmp     loc_180079839
0x180079775  mov     edi, 80004005h
0x18007977a  mov     [rsp+38h+TokenHandle], 0
0x180079783  call    cs:__imp_GetCurrentProcess
0x180079789  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x18007978e  mov     edx, 8; DesiredAccess
0x180079793  mov     rcx, rax; ProcessHandle
0x180079796  call    cs:__imp_OpenProcessToken
0x18007979c  test    eax, eax
0x18007979e  jz      loc_180079837
0x1800797a4  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x1800797a9  lea     rax, [rsp+38h+TokenInformationLength]
0x1800797ae  xor     r9d, r9d; TokenInformationLength
0x1800797b1  mov     [rsp+38h+TokenInformationLength], 0
0x1800797b9  xor     r8d, r8d; TokenInformation
0x1800797bc  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800797c1  lea     edx, [r9+19h]; TokenInformationClass
0x1800797c5  call    cs:__imp_GetTokenInformation
0x1800797cb  test    eax, eax
0x1800797cd  jnz     short loc_18007982C
0x1800797cf  call    cs:__imp_GetLastError
0x1800797d5  cmp     eax, 7Ah ; 'z'
0x1800797d8  jnz     short loc_18007982C
0x1800797da  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x1800797de  call    ?WinMalloc@@YAPEAX_K@Z; WinMalloc(unsigned __int64)
0x1800797e3  mov     rbx, rax
0x1800797e6  test    rax, rax
0x1800797e9  jz      short loc_18007982C
0x1800797eb  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x1800797f0  lea     rax, [rsp+38h+TokenInformationLength]
0x1800797f5  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x1800797fa  mov     r8, rbx; TokenInformation
0x1800797fd  mov     edx, 19h; TokenInformationClass
0x180079802  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180079807  call    cs:__imp_GetTokenInformation
0x18007980d  test    eax, eax
0x18007980f  jz      short loc_180079824
0x180079811  mov     rcx, [rbx]; Sid
0x180079814  mov     rdx, rsi; StringSid
0x180079817  call    cs:__imp_ConvertSidToStringSidW
0x18007981d  xor     ecx, ecx
0x18007981f  test    eax, eax
0x180079821  cmovnz  edi, ecx
0x180079824  mov     rcx, rbx; void *
0x180079827  call    ?WinFree@@YAXPEAX@Z; WinFree(void *)
0x18007982c  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180079831  call    cs:__imp_CloseHandle
0x180079837  mov     eax, edi
0x180079839  mov     rbx, [rsp+38h+arg_10]
0x18007983e  mov     rsi, [rsp+38h+arg_18]
0x180079843  add     rsp, 30h
0x180079847  pop     rdi
0x180079848  retn
```
