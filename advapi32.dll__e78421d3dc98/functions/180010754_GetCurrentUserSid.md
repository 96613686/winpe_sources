# GetCurrentUserSid

- ea: `0x180010754`
- end: `0x18001085c`
- name: `GetCurrentUserSid`
- size: `264`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000cb10`
- `0x180010564`

## callees

- `0x180010754`
- `0x18006505a`
- `0x180065090`

## import_xrefs

- `ntdll!NtOpenThreadToken` at `0x1800107c5`
- `ntdll!NtOpenThreadToken` at `0x1800107c5`
- `ntdll!NtOpenProcessToken` at `0x1800107e0`
- `ntdll!NtOpenProcessToken` at `0x1800107e0`
- `ntdll!RtlCopySid` at `0x180010823`
- `ntdll!RtlCopySid` at `0x180010823`
- `ntdll!NtQueryInformationToken` at `0x18001080a`
- `ntdll!NtQueryInformationToken` at `0x18001080a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800107cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800107cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800107b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800107b1`
- `KERNEL32!CloseHandle` at `0x180010833`
- `KERNEL32!CloseHandle` at `0x180010833`

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
0x180010754  mov     [rsp+arg_8], rbx
0x180010759  push    rdi
0x18001075a  sub     rsp, 0B0h
0x180010761  mov     rax, cs:__security_cookie
0x180010768  xor     rax, rsp
0x18001076b  mov     [rsp+0B8h+var_18], rax
0x180010773  mov     rdi, rcx
0x180010776  mov     [rsp+0B8h+TokenHandle], 0
0x18001077f  mov     ebx, 54h ; 'T'
0x180010784  lea     rcx, [rsp+0B8h+TokenInformation]; void *
0x180010789  mov     r8d, ebx; Size
0x18001078c  xor     edx, edx; Val
0x18001078e  call    memset_0
0x180010793  xor     edx, edx; Val
0x180010795  mov     [rsp+0B8h+TokenInformationLength], ebx
0x180010799  lea     r8d, [rbx-10h]; Size
0x18001079d  mov     rcx, rdi; void *
0x1800107a0  call    memset_0
0x1800107a5  mov     eax, gs:179Ch
0x1800107ad  test    eax, eax
0x1800107af  jz      short loc_1800107CD
0x1800107b1  call    cs:__imp_GetCurrentThread
0x1800107b7  lea     r9, [rsp+0B8h+TokenHandle]; TokenHandle
0x1800107bc  mov     r8b, 1; OpenAsSelf
0x1800107bf  mov     rcx, rax; ThreadHandle
0x1800107c2  lea     edx, [rbx-4Ch]; DesiredAccess
0x1800107c5  call    cs:__imp_NtOpenThreadToken
0x1800107cb  jmp     short loc_1800107E6
0x1800107cd  call    cs:__imp_GetCurrentProcess
0x1800107d3  lea     r8, [rsp+0B8h+TokenHandle]; TokenHandle
0x1800107d8  mov     edx, 8; DesiredAccess
0x1800107dd  mov     rcx, rax; ProcessHandle
0x1800107e0  call    cs:__imp_NtOpenProcessToken
0x1800107e6  mov     ebx, eax
0x1800107e8  test    eax, eax
0x1800107ea  js      short loc_180010829
0x1800107ec  mov     r9d, [rsp+0B8h+TokenInformationLength]; TokenInformationLength
0x1800107f1  lea     rax, [rsp+0B8h+TokenInformationLength]
0x1800107f6  mov     rcx, [rsp+0B8h+TokenHandle]; TokenHandle
0x1800107fb  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x180010800  mov     edx, 1; TokenInformationClass
0x180010805  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x18001080a  call    cs:__imp_NtQueryInformationToken
0x180010810  mov     ebx, eax
0x180010812  test    eax, eax
0x180010814  js      short loc_180010829
0x180010816  mov     r8, [rsp+0B8h+TokenInformation]; SourceSid
0x18001081b  mov     rdx, rdi; DestinationSid
0x18001081e  mov     ecx, 44h ; 'D'; DestinationSidLength
0x180010823  call    cs:__imp_RtlCopySid
0x180010829  mov     rcx, [rsp+0B8h+TokenHandle]; hObject
0x18001082e  test    rcx, rcx
0x180010831  jz      short loc_180010839
0x180010833  call    cs:__imp_CloseHandle
0x180010839  mov     eax, ebx
0x18001083b  mov     rcx, [rsp+0B8h+var_18]
0x180010843  xor     rcx, rsp; StackCookie
0x180010846  call    __security_check_cookie
0x18001084b  mov     rbx, [rsp+0B8h+arg_8]
0x180010853  add     rsp, 0B0h
0x18001085a  pop     rdi
0x18001085b  retn
```
