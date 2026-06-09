# IkeSubstituteIPsecIDInTunnelAcquireWithIKEToken

- ea: `0x18007b608`
- end: `0x18007b6be`
- name: `IkeSubstituteIPsecIDInTunnelAcquireWithIKEToken`
- size: `182`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18002f080`
- `0x180040d70`

## callees

- `0x1800061ec`
- `0x180008388`
- `0x180050850`
- `0x18007b608`
- `0x18007b6c4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007b62d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007b62d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18007b640`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18007b640`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b64a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b64a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007b691`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007b691`

## string_xrefs

- `0x18007b656`: `OpenProcessToken`
- `0x18007b697`: `IkeSubstituteIPsecIDInTunnelAcquireWithIKEToken`

## pseudocode

```c
__int64 __fastcall IkeSubstituteIPsecIDInTunnelAcquireWithIKEToken(__int64 a1)
{
  HANDLE CurrentProcess; // rax
  DWORD LastError; // eax
  __int64 v4; // rcx
  __int64 v5; // rdi
  void *TokenHandle; // [rsp+20h] [rbp-18h] BYREF

  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0xAu, &TokenHandle) )
  {
    v5 = IkeSubstituteIPsecIDInTunnelAcquireWithLocalToken(a1, TokenHandle);
    if ( !v5 )
      *(_DWORD *)(a1 + 376) |= 0x800u;
  }
  else
  {
    LastError = GetLastError();
    v5 = WfpReportSysErrorAsWinError(v4, "OpenProcessToken", LastError, 1);
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return IkeReturnError(v5, "IkeSubstituteIPsecIDInTunnelAcquireWithIKEToken");
}

```

## disassembly

```asm
0x18007b608  mov     [rsp+arg_8], rbx
0x18007b60d  push    rdi
0x18007b60e  sub     rsp, 30h
0x18007b612  mov     rax, cs:__security_cookie
0x18007b619  xor     rax, rsp
0x18007b61c  mov     [rsp+38h+var_10], rax
0x18007b621  mov     rbx, rcx
0x18007b624  mov     [rsp+38h+TokenHandle], 0
0x18007b62d  call    cs:__imp_GetCurrentProcess
0x18007b633  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x18007b638  mov     edx, 0Ah; DesiredAccess
0x18007b63d  mov     rcx, rax; ProcessHandle
0x18007b640  call    cs:__imp_OpenProcessToken
0x18007b646  test    eax, eax
0x18007b648  jnz     short loc_18007B66A
0x18007b64a  call    cs:__imp_GetLastError
0x18007b650  mov     r9d, 1
0x18007b656  lea     rdx, aOpenprocesstok; "OpenProcessToken"
0x18007b65d  mov     r8d, eax
0x18007b660  call    WfpReportSysErrorAsWinError
0x18007b665  mov     rdi, rax
0x18007b668  jmp     short loc_18007B687
0x18007b66a  mov     rdx, [rsp+38h+TokenHandle]
0x18007b66f  mov     rcx, rbx
0x18007b672  call    IkeSubstituteIPsecIDInTunnelAcquireWithLocalToken
0x18007b677  mov     rdi, rax
0x18007b67a  test    rax, rax
0x18007b67d  jnz     short loc_18007B687
0x18007b67f  bts     dword ptr [rbx+178h], 0Bh
0x18007b687  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x18007b68c  test    rcx, rcx
0x18007b68f  jz      short loc_18007B697
0x18007b691  call    cs:__imp_CloseHandle
0x18007b697  lea     rdx, aIkesubstitutei; "IkeSubstituteIPsecIDInTunnelAcquireWith"...
0x18007b69e  mov     rcx, rdi
0x18007b6a1  call    IkeReturnError
0x18007b6a6  mov     rcx, [rsp+38h+var_10]
0x18007b6ab  xor     rcx, rsp; StackCookie
0x18007b6ae  call    __security_check_cookie
0x18007b6b3  mov     rbx, [rsp+38h+arg_8]
0x18007b6b8  add     rsp, 30h
0x18007b6bc  pop     rdi
0x18007b6bd  retn
```
