# RestoreAllPrivileges(_TOKEN_PRIVILEGES *)

- ea: `0x1800eb400`
- end: `0x1800eb4bf`
- name: `?RestoreAllPrivileges@@YAHPEAU_TOKEN_PRIVILEGES@@@Z`
- size: `191`
- prototype: `__int64 __fastcall(struct _TOKEN_PRIVILEGES *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180005d10`
- `0x1800eb400`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eb49b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800eb49b`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800eb484`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800eb484`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800eb493`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800eb4ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800eb493`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800eb4ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800eb442`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800eb442`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800eb45b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800eb45b`

## pseudocode

```c
_BOOL8 __fastcall RestoreAllPrivileges(struct _TOKEN_PRIVILEGES *a1)
{
  HANDLE CurrentThread; // rax
  BOOL v4; // ebx
  void *TokenHandle; // [rsp+40h] [rbp+8h] BYREF

  if ( !a1 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmanutils.cpp", 2191, L"2191", 0x54Fu, 0);
    return 0;
  }
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x28u, 1, &TokenHandle) )
    return 0;
  if ( !AdjustTokenPrivileges(TokenHandle, 0, a1, 0, 0, 0) )
  {
    CloseHandle(TokenHandle);
    return 0;
  }
  v4 = GetLastError() == 0;
  CloseHandle(TokenHandle);
  return v4;
}

```

## disassembly

```asm
0x1800eb400  mov     [rsp+arg_8], rbx
0x1800eb405  push    rdi
0x1800eb406  sub     rsp, 30h
0x1800eb40a  mov     rdi, rcx
0x1800eb40d  test    rcx, rcx
0x1800eb410  jnz     short loc_1800EB439
0x1800eb412  mov     [rsp+38h+PreviousState], rcx; struct IRequestContext *
0x1800eb417  lea     r8, a2191; "2191"
0x1800eb41e  lea     rcx, aOnecoreAdminWm_90; "onecore\\admin\\wmi\\wmx\\stdlib\\wsman"...
0x1800eb425  mov     r9d, 54Fh; unsigned int
0x1800eb42b  mov     edx, 88Fh; unsigned int
0x1800eb430  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1800eb435  xor     eax, eax
0x1800eb437  jmp     short loc_1800EB4B4
0x1800eb439  mov     [rsp+38h+TokenHandle], 0
0x1800eb442  call    cs:__imp_GetCurrentThread
0x1800eb448  mov     ebx, 1
0x1800eb44d  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x1800eb452  mov     rcx, rax; ThreadHandle
0x1800eb455  mov     r8d, ebx; OpenAsSelf
0x1800eb458  lea     edx, [rbx+27h]; DesiredAccess
0x1800eb45b  call    cs:__imp_OpenThreadToken
0x1800eb461  test    eax, eax
0x1800eb463  jz      short loc_1800EB435
0x1800eb465  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x1800eb46a  xor     r9d, r9d; BufferLength
0x1800eb46d  mov     [rsp+38h+ReturnLength], 0; ReturnLength
0x1800eb476  mov     r8, rdi; NewState
0x1800eb479  xor     edx, edx; DisableAllPrivileges
0x1800eb47b  mov     [rsp+38h+PreviousState], 0; PreviousState
0x1800eb484  call    cs:__imp_AdjustTokenPrivileges
0x1800eb48a  test    eax, eax
0x1800eb48c  jnz     short loc_1800EB49B
0x1800eb48e  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x1800eb493  call    cs:__imp_CloseHandle
0x1800eb499  jmp     short loc_1800EB435
0x1800eb49b  call    cs:__imp_GetLastError
0x1800eb4a1  test    eax, eax
0x1800eb4a3  jz      short loc_1800EB4A7
0x1800eb4a5  xor     ebx, ebx
0x1800eb4a7  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x1800eb4ac  call    cs:__imp_CloseHandle
0x1800eb4b2  mov     eax, ebx
0x1800eb4b4  mov     rbx, [rsp+38h+arg_8]
0x1800eb4b9  add     rsp, 30h
0x1800eb4bd  pop     rdi
0x1800eb4be  retn
```
