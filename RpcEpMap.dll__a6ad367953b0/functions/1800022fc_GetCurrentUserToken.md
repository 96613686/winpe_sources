# GetCurrentUserToken

- ea: `0x1800022fc`
- end: `0x18000234a`
- name: `GetCurrentUserToken`
- size: `78`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1800018a0`

## callees

- `0x1800022fc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000230e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000230e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180002329`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180002329`

## pseudocode

```c
__int64 __fastcall GetCurrentUserToken(void **a1)
{
  HANDLE CurrentThread; // rax
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !CurrentThread || !OpenThreadToken(CurrentThread, 0x20008u, 0, &TokenHandle) )
    return 1721;
  *a1 = TokenHandle;
  return 0;
}

```

## disassembly

```asm
0x1800022fc  push    rbx
0x1800022fe  sub     rsp, 20h
0x180002302  mov     rbx, rcx
0x180002305  mov     [rsp+28h+TokenHandle], 0
0x18000230e  call    cs:__imp_GetCurrentThread
0x180002314  test    rax, rax
0x180002317  jz      short loc_180002343
0x180002319  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18000231e  xor     r8d, r8d; OpenAsSelf
0x180002321  mov     edx, 20008h; DesiredAccess
0x180002326  mov     rcx, rax; ThreadHandle
0x180002329  call    cs:__imp_OpenThreadToken
0x18000232f  test    eax, eax
0x180002331  jz      short loc_180002343
0x180002333  mov     rax, [rsp+28h+TokenHandle]
0x180002338  mov     [rbx], rax
0x18000233b  xor     eax, eax
0x18000233d  add     rsp, 20h
0x180002341  pop     rbx
0x180002342  retn
0x180002343  mov     eax, 6B9h
0x180002348  jmp     short loc_18000233D
```
