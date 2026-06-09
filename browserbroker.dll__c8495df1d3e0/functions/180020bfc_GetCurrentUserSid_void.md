# GetCurrentUserSid(void * *)

- ea: `0x180020bfc`
- end: `0x180020c57`
- name: `?GetCurrentUserSid@@YAKPEAPEAX@Z`
- size: `91`
- prototype: `unsigned int __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18002b100`

## callees

- `0x180020bfc`
- `0x180021100`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020c3f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020c3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180020c0e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180020c0e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180020c21`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180020c21`

## pseudocode

```c
__int64 __fastcall GetCurrentUserSid(void **a1)
{
  HANDLE CurrentProcess; // rax
  unsigned int UserSid; // ebx
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    UserSid = GetUserSid(TokenHandle, a1);
    CloseHandle(TokenHandle);
  }
  else
  {
    return GetLastError();
  }
  return UserSid;
}

```

## disassembly

```asm
0x180020bfc  push    rbx
0x180020bfe  sub     rsp, 20h
0x180020c02  mov     rbx, rcx
0x180020c05  mov     [rsp+28h+TokenHandle], 0
0x180020c0e  call    cs:__imp_GetCurrentProcess
0x180020c14  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x180020c19  mov     edx, 8; DesiredAccess
0x180020c1e  mov     rcx, rax; ProcessHandle
0x180020c21  call    cs:__imp_OpenProcessToken
0x180020c27  test    eax, eax
0x180020c29  jz      short loc_180020C47
0x180020c2b  mov     rcx, [rsp+28h+TokenHandle]; TokenHandle
0x180020c30  mov     rdx, rbx; void **
0x180020c33  call    ?GetUserSid@@YAKPEAXPEAPEAX@Z; GetUserSid(void *,void * *)
0x180020c38  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x180020c3d  mov     ebx, eax
0x180020c3f  call    cs:__imp_CloseHandle
0x180020c45  jmp     short loc_180020C4F
0x180020c47  call    cs:__imp_GetLastError
0x180020c4d  mov     ebx, eax
0x180020c4f  mov     eax, ebx
0x180020c51  add     rsp, 20h
0x180020c55  pop     rbx
0x180020c56  retn
```
