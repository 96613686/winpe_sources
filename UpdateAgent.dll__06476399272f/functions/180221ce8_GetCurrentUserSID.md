# GetCurrentUserSID

- ea: `0x180221ce8`
- end: `0x180221eb3`
- name: `GetCurrentUserSID`
- size: `459`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180040b48`
- `0x18022e2b4`

## callees

- `0x180221c2c`
- `0x180221ce8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180221dcb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180221e3b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180221dcb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180221e3b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180221e4f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180221e4f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180221de2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180221de2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180221e8f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180221e8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180221d31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180221d6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180221db2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180221e2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180221e64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180221d31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180221d6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180221db2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180221e2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180221e64`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180221d9e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180221e12`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180221d9e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180221e12`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180221d44`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180221d44`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180221d21`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180221d21`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180221d5a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180221d5a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180221d03`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180221d03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180221e81`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180221e81`

## pseudocode

```c
_BOOL8 __fastcall GetCurrentUserSID(_QWORD *a1)
{
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  DWORD LastError; // ebx
  DWORD v5; // ebx
  HANDLE ProcessHeap; // rax
  PSID *v7; // rdi
  HANDLE v8; // rax
  DWORD TokenInformationLength; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x20008u, 0, &TokenHandle)
    || GetLastError() == 1008
    && (CurrentProcess = GetCurrentProcess(), OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle)) )
  {
    TokenInformationLength = 0;
    if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) || GetLastError() != 122 )
    {
      LastError = GetLastError();
      if ( !LastError )
        LastError = 31;
    }
    else
    {
      v5 = TokenInformationLength;
      ProcessHeap = GetProcessHeap();
      v7 = (PSID *)HeapAlloc(ProcessHeap, 8u, v5);
      if ( v7 )
      {
        if ( GetTokenInformation(TokenHandle, TokenUser, v7, TokenInformationLength, &TokenInformationLength) )
          *a1 = DuplicateSID(*v7);
        LastError = GetLastError();
        v8 = GetProcessHeap();
        HeapFree(v8, 0, v7);
      }
      else
      {
        LastError = 14;
      }
    }
    CloseHandle(TokenHandle);
  }
  else
  {
    LastError = GetLastError();
  }
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x180221ce8  mov     [rsp+arg_0], rbx
0x180221ced  mov     [rsp+arg_18], rsi
0x180221cf2  push    rdi
0x180221cf3  sub     rsp, 30h
0x180221cf7  mov     rsi, rcx
0x180221cfa  mov     [rsp+38h+TokenHandle], 0
0x180221d03  call    cs:__imp_GetCurrentThread
0x180221d0a  nop     dword ptr [rax+rax+00h]
0x180221d0f  mov     ebx, 20008h
0x180221d14  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x180221d19  mov     rcx, rax; ThreadHandle
0x180221d1c  mov     edx, ebx; DesiredAccess
0x180221d1e  xor     r8d, r8d; OpenAsSelf
0x180221d21  call    cs:__imp_OpenThreadToken
0x180221d28  nop     dword ptr [rax+rax+00h]
0x180221d2d  test    eax, eax
0x180221d2f  jnz     short loc_180221D7D
0x180221d31  call    cs:__imp_GetLastError
0x180221d38  nop     dword ptr [rax+rax+00h]
0x180221d3d  cmp     eax, 3F0h
0x180221d42  jnz     short loc_180221D6A
0x180221d44  call    cs:__imp_GetCurrentProcess
0x180221d4b  nop     dword ptr [rax+rax+00h]
0x180221d50  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x180221d55  mov     edx, ebx; DesiredAccess
0x180221d57  mov     rcx, rax; ProcessHandle
0x180221d5a  call    cs:__imp_OpenProcessToken
0x180221d61  nop     dword ptr [rax+rax+00h]
0x180221d66  test    eax, eax
0x180221d68  jnz     short loc_180221D7D
0x180221d6a  call    cs:__imp_GetLastError
0x180221d71  nop     dword ptr [rax+rax+00h]
0x180221d76  mov     ebx, eax
0x180221d78  jmp     loc_180221E8D
0x180221d7d  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x180221d82  lea     rax, [rsp+38h+TokenInformationLength]
0x180221d87  xor     r9d, r9d; TokenInformationLength
0x180221d8a  mov     [rsp+38h+TokenInformationLength], 0
0x180221d92  xor     r8d, r8d; TokenInformation
0x180221d95  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180221d9a  lea     edx, [r9+1]; TokenInformationClass
0x180221d9e  call    cs:__imp_GetTokenInformation
0x180221da5  nop     dword ptr [rax+rax+00h]
0x180221daa  test    eax, eax
0x180221dac  jnz     loc_180221E64
0x180221db2  call    cs:__imp_GetLastError
0x180221db9  nop     dword ptr [rax+rax+00h]
0x180221dbe  cmp     eax, 7Ah ; 'z'
0x180221dc1  jnz     loc_180221E64
0x180221dc7  mov     ebx, [rsp+38h+TokenInformationLength]
0x180221dcb  call    cs:__imp_GetProcessHeap
0x180221dd2  nop     dword ptr [rax+rax+00h]
0x180221dd7  mov     r8d, ebx; dwBytes
0x180221dda  mov     edx, 8; dwFlags
0x180221ddf  mov     rcx, rax; hHeap
0x180221de2  call    cs:__imp_HeapAlloc
0x180221de9  nop     dword ptr [rax+rax+00h]
0x180221dee  mov     rdi, rax
0x180221df1  test    rax, rax
0x180221df4  jz      short loc_180221E5D
0x180221df6  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x180221dfb  lea     rax, [rsp+38h+TokenInformationLength]
0x180221e00  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x180221e05  mov     r8, rdi; TokenInformation
0x180221e08  mov     edx, 1; TokenInformationClass
0x180221e0d  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180221e12  call    cs:__imp_GetTokenInformation
0x180221e19  nop     dword ptr [rax+rax+00h]
0x180221e1e  test    eax, eax
0x180221e20  jz      short loc_180221E2D
0x180221e22  mov     rcx, [rdi]; pSourceSid
0x180221e25  call    DuplicateSID
0x180221e2a  mov     [rsi], rax
0x180221e2d  call    cs:__imp_GetLastError
0x180221e34  nop     dword ptr [rax+rax+00h]
0x180221e39  mov     ebx, eax
0x180221e3b  call    cs:__imp_GetProcessHeap
0x180221e42  nop     dword ptr [rax+rax+00h]
0x180221e47  mov     r8, rdi; lpMem
0x180221e4a  xor     edx, edx; dwFlags
0x180221e4c  mov     rcx, rax; hHeap
0x180221e4f  call    cs:__imp_HeapFree
0x180221e56  nop     dword ptr [rax+rax+00h]
0x180221e5b  jmp     short loc_180221E7C
0x180221e5d  mov     ebx, 0Eh
0x180221e62  jmp     short loc_180221E7C
0x180221e64  call    cs:__imp_GetLastError
0x180221e6b  nop     dword ptr [rax+rax+00h]
0x180221e70  mov     ebx, eax
0x180221e72  mov     eax, 1Fh
0x180221e77  test    ebx, ebx
0x180221e79  cmovz   ebx, eax
0x180221e7c  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180221e81  call    cs:__imp_CloseHandle
0x180221e88  nop     dword ptr [rax+rax+00h]
0x180221e8d  mov     ecx, ebx; dwErrCode
0x180221e8f  call    cs:__imp_SetLastError
0x180221e96  nop     dword ptr [rax+rax+00h]
0x180221e9b  mov     rsi, [rsp+38h+arg_18]
0x180221ea0  xor     eax, eax
0x180221ea2  test    ebx, ebx
0x180221ea4  mov     rbx, [rsp+38h+arg_0]
0x180221ea9  setz    al
0x180221eac  add     rsp, 30h
0x180221eb0  pop     rdi
0x180221eb1  retn
```
