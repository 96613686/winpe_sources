# GetProcessIntegrityLevel(void *,ulong *)

- ea: `0x180020fe8`
- end: `0x18002105a`
- name: `?GetProcessIntegrityLevel@@YAJPEAXPEAK@Z`
- size: `114`
- prototype: `__int64 __fastcall(void *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180020b50`

## callees

- `0x18000a2dc`
- `0x180020fe8`
- `0x180025704`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021043`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021043`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180021004`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180021004`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180021017`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180021017`

## pseudocode

```c
__int64 __fastcall GetProcessIntegrityLevel(void *a1, unsigned int *a2)
{
  HANDLE CurrentProcess; // rax
  unsigned int v4; // ebx
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  TokenHandle = 0;
  *a2 = 0x2000;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    v4 = TokenIntegrityRIDFromToken(TokenHandle, a2);
    if ( v4 == -1073741821 )
      v4 = 1;
    CloseHandle(TokenHandle);
  }
  else
  {
    return (unsigned int)HRESULTFromLastErrorError();
  }
  return v4;
}

```

## disassembly

```asm
0x180020fe8  mov     [rsp+TokenHandle], rcx
0x180020fed  push    rbx
0x180020fee  sub     rsp, 20h
0x180020ff2  mov     rbx, rdx
0x180020ff5  mov     [rsp+28h+TokenHandle], 0
0x180020ffe  mov     dword ptr [rdx], 2000h
0x180021004  call    cs:__imp_GetCurrentProcess
0x18002100a  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x18002100f  mov     edx, 8; DesiredAccess
0x180021014  mov     rcx, rax; ProcessHandle
0x180021017  call    cs:__imp_OpenProcessToken
0x18002101d  test    eax, eax
0x18002101f  jz      short loc_18002104B
0x180021021  mov     rcx, [rsp+28h+TokenHandle]; TokenHandle
0x180021026  mov     rdx, rbx
0x180021029  call    _TokenIntegrityRIDFromToken
0x18002102e  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x180021033  mov     ebx, eax
0x180021035  cmp     ebx, 0C0000003h
0x18002103b  mov     eax, 1
0x180021040  cmovz   ebx, eax
0x180021043  call    cs:__imp_CloseHandle
0x180021049  jmp     short loc_180021052
0x18002104b  call    ?HRESULTFromLastErrorError@@YAJXZ; HRESULTFromLastErrorError(void)
0x180021050  mov     ebx, eax
0x180021052  mov     eax, ebx
0x180021054  add     rsp, 20h
0x180021058  pop     rbx
0x180021059  retn
```
