# GetCurrentUserSID

- ea: `0x140023ac4`
- end: `0x140023c86`
- name: `GetCurrentUserSID`
- size: `450`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1400093b8`
- `0x14000a21c`
- `0x140027a70`

## callees

- `0x1400239f4`
- `0x140023ac4`

## import_xrefs

- `ADVAPI32!GetTokenInformation` at `0x140023b72`
- `ADVAPI32!GetTokenInformation` at `0x140023be6`
- `ADVAPI32!GetTokenInformation` at `0x140023b72`
- `ADVAPI32!GetTokenInformation` at `0x140023be6`
- `ADVAPI32!OpenProcessToken` at `0x140023b32`
- `ADVAPI32!OpenProcessToken` at `0x140023b32`
- `ADVAPI32!OpenThreadToken` at `0x140023af9`
- `ADVAPI32!OpenThreadToken` at `0x140023af9`
- `KERNEL32!CloseHandle` at `0x140023c55`
- `KERNEL32!CloseHandle` at `0x140023c55`
- `KERNEL32!HeapFree` at `0x140023c23`
- `KERNEL32!HeapFree` at `0x140023c23`
- `KERNEL32!HeapAlloc` at `0x140023bb6`
- `KERNEL32!HeapAlloc` at `0x140023bb6`
- `KERNEL32!GetProcessHeap` at `0x140023b9f`
- `KERNEL32!GetProcessHeap` at `0x140023c0f`
- `KERNEL32!GetProcessHeap` at `0x140023b9f`
- `KERNEL32!GetProcessHeap` at `0x140023c0f`
- `KERNEL32!GetCurrentThread` at `0x140023adb`
- `KERNEL32!GetCurrentThread` at `0x140023adb`
- `KERNEL32!GetLastError` at `0x140023b09`
- `KERNEL32!GetLastError` at `0x140023b42`
- `KERNEL32!GetLastError` at `0x140023b86`
- `KERNEL32!GetLastError` at `0x140023c01`
- `KERNEL32!GetLastError` at `0x140023c38`
- `KERNEL32!GetLastError` at `0x140023b09`
- `KERNEL32!GetLastError` at `0x140023b42`
- `KERNEL32!GetLastError` at `0x140023b86`
- `KERNEL32!GetLastError` at `0x140023c01`
- `KERNEL32!GetLastError` at `0x140023c38`
- `KERNEL32!GetCurrentProcess` at `0x140023b1c`
- `KERNEL32!GetCurrentProcess` at `0x140023b1c`
- `KERNEL32!SetLastError` at `0x140023c63`
- `KERNEL32!SetLastError` at `0x140023c63`

## pseudocode

```c
__int64 __fastcall GetCurrentUserSID(_QWORD *a1)
{
  unsigned int v1; // edi
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  DWORD LastError; // ebx
  DWORD v6; // ebx
  HANDLE ProcessHeap; // rax
  PSID *v8; // rsi
  HANDLE v9; // rax
  DWORD TokenInformationLength; // [rsp+58h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp+18h] BYREF

  v1 = 0;
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
      v6 = TokenInformationLength;
      ProcessHeap = GetProcessHeap();
      v8 = (PSID *)HeapAlloc(ProcessHeap, 8u, v6);
      if ( v8 )
      {
        if ( GetTokenInformation(TokenHandle, TokenUser, v8, TokenInformationLength, &TokenInformationLength) )
          *a1 = DuplicateSID(*v8);
        LastError = GetLastError();
        v9 = GetProcessHeap();
        HeapFree(v9, 0, v8);
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
  LOBYTE(v1) = LastError == 0;
  return v1;
}

```

## disassembly

```asm
0x140023ac4  mov     [rsp+arg_0], rbx
0x140023ac9  push    rsi
0x140023aca  push    rdi
0x140023acb  push    r14
0x140023acd  sub     rsp, 30h
0x140023ad1  xor     edi, edi
0x140023ad3  mov     r14, rcx
0x140023ad6  mov     [rsp+48h+TokenHandle], rdi
0x140023adb  call    cs:__imp_GetCurrentThread
0x140023ae2  nop     dword ptr [rax+rax+00h]
0x140023ae7  mov     ebx, 20008h
0x140023aec  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x140023af1  mov     rcx, rax; ThreadHandle
0x140023af4  mov     edx, ebx; DesiredAccess
0x140023af6  xor     r8d, r8d; OpenAsSelf
0x140023af9  call    cs:__imp_OpenThreadToken
0x140023b00  nop     dword ptr [rax+rax+00h]
0x140023b05  test    eax, eax
0x140023b07  jnz     short loc_140023B55
0x140023b09  call    cs:__imp_GetLastError
0x140023b10  nop     dword ptr [rax+rax+00h]
0x140023b15  cmp     eax, 3F0h
0x140023b1a  jnz     short loc_140023B42
0x140023b1c  call    cs:__imp_GetCurrentProcess
0x140023b23  nop     dword ptr [rax+rax+00h]
0x140023b28  lea     r8, [rsp+48h+TokenHandle]; TokenHandle
0x140023b2d  mov     edx, ebx; DesiredAccess
0x140023b2f  mov     rcx, rax; ProcessHandle
0x140023b32  call    cs:__imp_OpenProcessToken
0x140023b39  nop     dword ptr [rax+rax+00h]
0x140023b3e  test    eax, eax
0x140023b40  jnz     short loc_140023B55
0x140023b42  call    cs:__imp_GetLastError
0x140023b49  nop     dword ptr [rax+rax+00h]
0x140023b4e  mov     ebx, eax
0x140023b50  jmp     loc_140023C61
0x140023b55  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x140023b5a  lea     rax, [rsp+48h+TokenInformationLength]
0x140023b5f  xor     r9d, r9d; TokenInformationLength
0x140023b62  mov     [rsp+48h+TokenInformationLength], edi
0x140023b66  xor     r8d, r8d; TokenInformation
0x140023b69  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x140023b6e  lea     edx, [r9+1]; TokenInformationClass
0x140023b72  call    cs:__imp_GetTokenInformation
0x140023b79  nop     dword ptr [rax+rax+00h]
0x140023b7e  test    eax, eax
0x140023b80  jnz     loc_140023C38
0x140023b86  call    cs:__imp_GetLastError
0x140023b8d  nop     dword ptr [rax+rax+00h]
0x140023b92  cmp     eax, 7Ah ; 'z'
0x140023b95  jnz     loc_140023C38
0x140023b9b  mov     ebx, [rsp+48h+TokenInformationLength]
0x140023b9f  call    cs:__imp_GetProcessHeap
0x140023ba6  nop     dword ptr [rax+rax+00h]
0x140023bab  mov     r8d, ebx; dwBytes
0x140023bae  mov     edx, 8; dwFlags
0x140023bb3  mov     rcx, rax; hHeap
0x140023bb6  call    cs:__imp_HeapAlloc
0x140023bbd  nop     dword ptr [rax+rax+00h]
0x140023bc2  mov     rsi, rax
0x140023bc5  test    rax, rax
0x140023bc8  jz      short loc_140023C31
0x140023bca  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x140023bcf  lea     rax, [rsp+48h+TokenInformationLength]
0x140023bd4  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x140023bd9  mov     r8, rsi; TokenInformation
0x140023bdc  mov     edx, 1; TokenInformationClass
0x140023be1  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x140023be6  call    cs:__imp_GetTokenInformation
0x140023bed  nop     dword ptr [rax+rax+00h]
0x140023bf2  test    eax, eax
0x140023bf4  jz      short loc_140023C01
0x140023bf6  mov     rcx, [rsi]; pSourceSid
0x140023bf9  call    DuplicateSID
0x140023bfe  mov     [r14], rax
0x140023c01  call    cs:__imp_GetLastError
0x140023c08  nop     dword ptr [rax+rax+00h]
0x140023c0d  mov     ebx, eax
0x140023c0f  call    cs:__imp_GetProcessHeap
0x140023c16  nop     dword ptr [rax+rax+00h]
0x140023c1b  mov     r8, rsi; lpMem
0x140023c1e  xor     edx, edx; dwFlags
0x140023c20  mov     rcx, rax; hHeap
0x140023c23  call    cs:__imp_HeapFree
0x140023c2a  nop     dword ptr [rax+rax+00h]
0x140023c2f  jmp     short loc_140023C50
0x140023c31  mov     ebx, 0Eh
0x140023c36  jmp     short loc_140023C50
0x140023c38  call    cs:__imp_GetLastError
0x140023c3f  nop     dword ptr [rax+rax+00h]
0x140023c44  mov     ebx, eax
0x140023c46  mov     eax, 1Fh
0x140023c4b  test    ebx, ebx
0x140023c4d  cmovz   ebx, eax
0x140023c50  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x140023c55  call    cs:__imp_CloseHandle
0x140023c5c  nop     dword ptr [rax+rax+00h]
0x140023c61  mov     ecx, ebx; dwErrCode
0x140023c63  call    cs:__imp_SetLastError
0x140023c6a  nop     dword ptr [rax+rax+00h]
0x140023c6f  test    ebx, ebx
0x140023c71  mov     rbx, [rsp+48h+arg_0]
0x140023c76  setz    dil
0x140023c7a  mov     eax, edi
0x140023c7c  add     rsp, 30h
0x140023c80  pop     r14
0x140023c82  pop     rdi
0x140023c83  pop     rsi
0x140023c84  retn
```
