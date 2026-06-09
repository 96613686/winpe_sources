# IsUIAccessProcess(void)

- ea: `0x180008778`
- end: `0x1800087ec`
- name: `?IsUIAccessProcess@@YAHXZ`
- size: `116`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008318`

## callees

- `0x180008778`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800087a2`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800087a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180008791`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180008791`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800087de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800087de`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800087c8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800087c8`

## pseudocode

```c
__int64 IsUIAccessProcess(void)
{
  unsigned int v0; // ebx
  HANDLE CurrentProcess; // rax
  DWORD TokenInformationLength; // [rsp+40h] [rbp+8h] BYREF
  int TokenInformation; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  v0 = 0;
  TokenInformationLength = 4;
  TokenInformation = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    if ( GetTokenInformation(
           TokenHandle,
           TokenUIAccess,
           &TokenInformation,
           TokenInformationLength,
           &TokenInformationLength) )
    {
      LOBYTE(v0) = TokenInformation != 0;
    }
    CloseHandle(TokenHandle);
  }
  return v0;
}

```

## disassembly

```asm
0x180008778  push    rbx
0x18000877a  sub     rsp, 30h
0x18000877e  xor     ebx, ebx
0x180008780  mov     [rsp+38h+TokenInformationLength], 4
0x180008788  mov     [rsp+38h+TokenInformation], ebx
0x18000878c  mov     [rsp+38h+TokenHandle], rbx
0x180008791  call    cs:__imp_GetCurrentProcess
0x180008797  mov     rcx, rax; ProcessHandle
0x18000879a  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x18000879f  lea     edx, [rbx+8]; DesiredAccess
0x1800087a2  call    cs:__imp_OpenProcessToken
0x1800087a8  test    eax, eax
0x1800087aa  jz      short loc_1800087E4
0x1800087ac  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x1800087b1  lea     rax, [rsp+38h+TokenInformationLength]
0x1800087b6  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x1800087bb  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x1800087c0  lea     edx, [rbx+1Ah]; TokenInformationClass
0x1800087c3  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800087c8  call    cs:__imp_GetTokenInformation
0x1800087ce  test    eax, eax
0x1800087d0  jz      short loc_1800087D9
0x1800087d2  cmp     [rsp+38h+TokenInformation], ebx
0x1800087d6  setnz   bl
0x1800087d9  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x1800087de  call    cs:__imp_CloseHandle
0x1800087e4  mov     eax, ebx
0x1800087e6  add     rsp, 30h
0x1800087ea  pop     rbx
0x1800087eb  retn
```
