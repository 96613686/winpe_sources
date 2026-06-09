# GetCurrentUserSid

- ea: `0x180015a8c`
- end: `0x180015bbf`
- name: `GetCurrentUserSid`
- size: `307`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180012300`
- `0x180015864`

## callees

- `0x180015a8c`
- `0x18007205a`
- `0x1800720b0`

## import_xrefs

- `ntdll!NtOpenThreadToken` at `0x180015b03`
- `ntdll!NtOpenThreadToken` at `0x180015b03`
- `ntdll!NtOpenProcessToken` at `0x180015b2a`
- `ntdll!NtOpenProcessToken` at `0x180015b2a`
- `ntdll!RtlCopySid` at `0x180015b79`
- `ntdll!RtlCopySid` at `0x180015b79`
- `ntdll!NtQueryInformationToken` at `0x180015b5a`
- `ntdll!NtQueryInformationToken` at `0x180015b5a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180015b11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180015b11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180015ae9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180015ae9`
- `KERNEL32!CloseHandle` at `0x180015b8f`
- `KERNEL32!CloseHandle` at `0x180015b8f`

## pseudocode

```c
__int64 __fastcall GetCurrentUserSid(void *a1)
{
  HANDLE CurrentThread; // rax
  NTSTATUS v3; // eax
  HANDLE CurrentProcess; // rax
  NTSTATUS v5; // ebx
  ULONG TokenInformationLength; // [rsp+30h] [rbp-88h] BYREF
  HANDLE TokenHandle; // [rsp+38h] [rbp-80h] BYREF
  PSID TokenInformation[12]; // [rsp+40h] [rbp-78h] BYREF

  TokenHandle = 0;
  memset_0(TokenInformation, 0, 0x54u);
  TokenInformationLength = 84;
  memset_0(a1, 0, 0x44u);
  if ( NtCurrentTeb()->IsImpersonating )
  {
    CurrentThread = GetCurrentThread();
    v3 = NtOpenThreadToken(CurrentThread, 8u, 1u, &TokenHandle);
  }
  else
  {
    CurrentProcess = GetCurrentProcess();
    v3 = NtOpenProcessToken(CurrentProcess, 8u, &TokenHandle);
  }
  v5 = v3;
  if ( v3 >= 0 )
  {
    v5 = NtQueryInformationToken(
           TokenHandle,
           TokenUser,
           TokenInformation,
           TokenInformationLength,
           &TokenInformationLength);
    if ( v5 >= 0 )
      RtlCopySid(0x44u, a1, TokenInformation[0]);
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180015a8c  mov     [rsp+arg_8], rbx
0x180015a91  push    rdi
0x180015a92  sub     rsp, 0B0h
0x180015a99  mov     rax, cs:__security_cookie
0x180015aa0  xor     rax, rsp
0x180015aa3  mov     [rsp+0B8h+var_18], rax
0x180015aab  mov     rdi, rcx
0x180015aae  mov     [rsp+0B8h+TokenHandle], 0
0x180015ab7  mov     ebx, 54h ; 'T'
0x180015abc  lea     rcx, [rsp+0B8h+TokenInformation]; void *
0x180015ac1  mov     r8d, ebx; Size
0x180015ac4  xor     edx, edx; Val
0x180015ac6  call    memset_0
0x180015acb  xor     edx, edx; Val
0x180015acd  mov     [rsp+0B8h+TokenInformationLength], ebx
0x180015ad1  lea     r8d, [rbx-10h]; Size
0x180015ad5  mov     rcx, rdi; void *
0x180015ad8  call    memset_0
0x180015add  mov     eax, gs:179Ch
0x180015ae5  test    eax, eax
0x180015ae7  jz      short loc_180015B11
0x180015ae9  call    cs:__imp_GetCurrentThread
0x180015af0  nop     dword ptr [rax+rax+00h]
0x180015af5  lea     r9, [rsp+0B8h+TokenHandle]; TokenHandle
0x180015afa  mov     r8b, 1; OpenAsSelf
0x180015afd  mov     rcx, rax; ThreadHandle
0x180015b00  lea     edx, [rbx-4Ch]; DesiredAccess
0x180015b03  call    cs:__imp_NtOpenThreadToken
0x180015b0a  nop     dword ptr [rax+rax+00h]
0x180015b0f  jmp     short loc_180015B36
0x180015b11  call    cs:__imp_GetCurrentProcess
0x180015b18  nop     dword ptr [rax+rax+00h]
0x180015b1d  lea     r8, [rsp+0B8h+TokenHandle]; TokenHandle
0x180015b22  mov     edx, 8; DesiredAccess
0x180015b27  mov     rcx, rax; ProcessHandle
0x180015b2a  call    cs:__imp_NtOpenProcessToken
0x180015b31  nop     dword ptr [rax+rax+00h]
0x180015b36  mov     ebx, eax
0x180015b38  test    eax, eax
0x180015b3a  js      short loc_180015B85
0x180015b3c  mov     r9d, [rsp+0B8h+TokenInformationLength]; TokenInformationLength
0x180015b41  lea     rax, [rsp+0B8h+TokenInformationLength]
0x180015b46  mov     rcx, [rsp+0B8h+TokenHandle]; TokenHandle
0x180015b4b  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x180015b50  mov     edx, 1; TokenInformationClass
0x180015b55  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x180015b5a  call    cs:__imp_NtQueryInformationToken
0x180015b61  nop     dword ptr [rax+rax+00h]
0x180015b66  mov     ebx, eax
0x180015b68  test    eax, eax
0x180015b6a  js      short loc_180015B85
0x180015b6c  mov     r8, [rsp+0B8h+TokenInformation]; SourceSid
0x180015b71  mov     rdx, rdi; DestinationSid
0x180015b74  mov     ecx, 44h ; 'D'; DestinationSidLength
0x180015b79  call    cs:__imp_RtlCopySid
0x180015b80  nop     dword ptr [rax+rax+00h]
0x180015b85  mov     rcx, [rsp+0B8h+TokenHandle]; hObject
0x180015b8a  test    rcx, rcx
0x180015b8d  jz      short loc_180015B9B
0x180015b8f  call    cs:__imp_CloseHandle
0x180015b96  nop     dword ptr [rax+rax+00h]
0x180015b9b  mov     eax, ebx
0x180015b9d  mov     rcx, [rsp+0B8h+var_18]
0x180015ba5  xor     rcx, rsp; StackCookie
0x180015ba8  call    __security_check_cookie
0x180015bad  mov     rbx, [rsp+0B8h+arg_8]
0x180015bb5  add     rsp, 0B0h
0x180015bbc  pop     rdi
0x180015bbd  retn
```
