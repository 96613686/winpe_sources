# GetCurrentUserSID

- ea: `0x180068398`
- end: `0x1800684f8`
- name: `GetCurrentUserSID`
- size: `352`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180065100`

## callees

- `0x18006830c`
- `0x180068398`

## import_xrefs

- `ADVAPI32!GetTokenInformation` at `0x18006842a`
- `ADVAPI32!GetTokenInformation` at `0x180068482`
- `ADVAPI32!GetTokenInformation` at `0x18006842a`
- `ADVAPI32!GetTokenInformation` at `0x180068482`
- `ADVAPI32!OpenThreadToken` at `0x1800683cb`
- `ADVAPI32!OpenThreadToken` at `0x1800683cb`
- `ADVAPI32!OpenProcessToken` at `0x1800683f2`
- `ADVAPI32!OpenProcessToken` at `0x1800683f2`
- `KERNEL32!GetCurrentProcess` at `0x1800683e2`
- `KERNEL32!GetCurrentProcess` at `0x1800683e2`
- `KERNEL32!CloseHandle` at `0x1800684d3`
- `KERNEL32!CloseHandle` at `0x1800684d3`
- `KERNEL32!SetLastError` at `0x1800684db`
- `KERNEL32!SetLastError` at `0x1800684db`
- `KERNEL32!GetLastError` at `0x1800683d5`
- `KERNEL32!GetLastError` at `0x1800683fc`
- `KERNEL32!GetLastError` at `0x180068438`
- `KERNEL32!GetLastError` at `0x180068497`
- `KERNEL32!GetLastError` at `0x1800684bc`
- `KERNEL32!GetLastError` at `0x1800683d5`
- `KERNEL32!GetLastError` at `0x1800683fc`
- `KERNEL32!GetLastError` at `0x180068438`
- `KERNEL32!GetLastError` at `0x180068497`
- `KERNEL32!GetLastError` at `0x1800684bc`
- `KERNEL32!HeapFree` at `0x1800684ad`
- `KERNEL32!HeapFree` at `0x1800684ad`
- `KERNEL32!HeapAlloc` at `0x180068458`
- `KERNEL32!HeapAlloc` at `0x180068458`
- `KERNEL32!GetProcessHeap` at `0x180068447`
- `KERNEL32!GetProcessHeap` at `0x18006849f`
- `KERNEL32!GetProcessHeap` at `0x180068447`
- `KERNEL32!GetProcessHeap` at `0x18006849f`
- `KERNEL32!GetCurrentThread` at `0x1800683b3`
- `KERNEL32!GetCurrentThread` at `0x1800683b3`

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
0x180068398  mov     [rsp+arg_0], rbx
0x18006839d  mov     [rsp+arg_18], rsi
0x1800683a2  push    rdi
0x1800683a3  sub     rsp, 30h
0x1800683a7  mov     rsi, rcx
0x1800683aa  mov     [rsp+38h+TokenHandle], 0
0x1800683b3  call    cs:__imp_GetCurrentThread
0x1800683b9  mov     ebx, 20008h
0x1800683be  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x1800683c3  mov     rcx, rax; ThreadHandle
0x1800683c6  mov     edx, ebx; DesiredAccess
0x1800683c8  xor     r8d, r8d; OpenAsSelf
0x1800683cb  call    cs:__imp_OpenThreadToken
0x1800683d1  test    eax, eax
0x1800683d3  jnz     short loc_180068409
0x1800683d5  call    cs:__imp_GetLastError
0x1800683db  cmp     eax, 3F0h
0x1800683e0  jnz     short loc_1800683FC
0x1800683e2  call    cs:__imp_GetCurrentProcess
0x1800683e8  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x1800683ed  mov     edx, ebx; DesiredAccess
0x1800683ef  mov     rcx, rax; ProcessHandle
0x1800683f2  call    cs:__imp_OpenProcessToken
0x1800683f8  test    eax, eax
0x1800683fa  jnz     short loc_180068409
0x1800683fc  call    cs:__imp_GetLastError
0x180068402  mov     ebx, eax
0x180068404  jmp     loc_1800684D9
0x180068409  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x18006840e  lea     rax, [rsp+38h+TokenInformationLength]
0x180068413  xor     r9d, r9d; TokenInformationLength
0x180068416  mov     [rsp+38h+TokenInformationLength], 0
0x18006841e  xor     r8d, r8d; TokenInformation
0x180068421  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180068426  lea     edx, [r9+1]; TokenInformationClass
0x18006842a  call    cs:__imp_GetTokenInformation
0x180068430  test    eax, eax
0x180068432  jnz     loc_1800684BC
0x180068438  call    cs:__imp_GetLastError
0x18006843e  cmp     eax, 7Ah ; 'z'
0x180068441  jnz     short loc_1800684BC
0x180068443  mov     ebx, [rsp+38h+TokenInformationLength]
0x180068447  call    cs:__imp_GetProcessHeap
0x18006844d  mov     r8d, ebx; dwBytes
0x180068450  mov     edx, 8; dwFlags
0x180068455  mov     rcx, rax; hHeap
0x180068458  call    cs:__imp_HeapAlloc
0x18006845e  mov     rdi, rax
0x180068461  test    rax, rax
0x180068464  jz      short loc_1800684B5
0x180068466  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18006846b  lea     rax, [rsp+38h+TokenInformationLength]
0x180068470  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x180068475  mov     r8, rdi; TokenInformation
0x180068478  mov     edx, 1; TokenInformationClass
0x18006847d  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180068482  call    cs:__imp_GetTokenInformation
0x180068488  test    eax, eax
0x18006848a  jz      short loc_180068497
0x18006848c  mov     rcx, [rdi]; pSourceSid
0x18006848f  call    DuplicateSID
0x180068494  mov     [rsi], rax
0x180068497  call    cs:__imp_GetLastError
0x18006849d  mov     ebx, eax
0x18006849f  call    cs:__imp_GetProcessHeap
0x1800684a5  mov     r8, rdi; lpMem
0x1800684a8  xor     edx, edx; dwFlags
0x1800684aa  mov     rcx, rax; hHeap
0x1800684ad  call    cs:__imp_HeapFree
0x1800684b3  jmp     short loc_1800684CE
0x1800684b5  mov     ebx, 0Eh
0x1800684ba  jmp     short loc_1800684CE
0x1800684bc  call    cs:__imp_GetLastError
0x1800684c2  mov     ebx, eax
0x1800684c4  mov     eax, 1Fh
0x1800684c9  test    ebx, ebx
0x1800684cb  cmovz   ebx, eax
0x1800684ce  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x1800684d3  call    cs:__imp_CloseHandle
0x1800684d9  mov     ecx, ebx; dwErrCode
0x1800684db  call    cs:__imp_SetLastError
0x1800684e1  mov     rsi, [rsp+38h+arg_18]
0x1800684e6  xor     eax, eax
0x1800684e8  test    ebx, ebx
0x1800684ea  mov     rbx, [rsp+38h+arg_0]
0x1800684ef  setz    al
0x1800684f2  add     rsp, 30h
0x1800684f6  pop     rdi
0x1800684f7  retn
```
