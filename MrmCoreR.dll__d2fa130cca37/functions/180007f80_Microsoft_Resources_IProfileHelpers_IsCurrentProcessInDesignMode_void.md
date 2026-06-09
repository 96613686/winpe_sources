# Microsoft::Resources::IProfileHelpers::IsCurrentProcessInDesignMode(void)

- ea: `0x180007f80`
- end: `0x18000800b`
- name: `?IsCurrentProcessInDesignMode@IProfileHelpers@Resources@Microsoft@@SA_NXZ`
- size: `139`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007cb0`
- `0x1800172a0`

## callees

- `0x180007f80`
- `0x180008014`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007ffa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007ffa`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180007fc1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180007fc1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180007faa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180007faa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007ff2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007ff2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180007fcb`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180007fcb`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180007fe2`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180007fe2`

## pseudocode

```c
bool Microsoft::Resources::IProfileHelpers::IsCurrentProcessInDesignMode(void)
{
  bool IsDesignModeClaimPresentOnCurrentProcess; // bl
  HANDLE CurrentThread; // rax
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  if ( !NtCurrentTeb()->IsImpersonating )
    return Microsoft::Resources::IProfileHelpers::IsDesignModeClaimPresentOnCurrentProcess();
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) || GetLastError() == 1008 )
  {
    RevertToSelf();
    IsDesignModeClaimPresentOnCurrentProcess = Microsoft::Resources::IProfileHelpers::IsDesignModeClaimPresentOnCurrentProcess();
    if ( !TokenHandle )
      return IsDesignModeClaimPresentOnCurrentProcess;
    ImpersonateLoggedOnUser(TokenHandle);
  }
  else
  {
    IsDesignModeClaimPresentOnCurrentProcess = 0;
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return IsDesignModeClaimPresentOnCurrentProcess;
}

```

## disassembly

```asm
0x180007f80  push    rbx
0x180007f82  sub     rsp, 20h
0x180007f86  mov     eax, gs:179Ch
0x180007f8e  test    eax, eax
0x180007f90  jnz     short loc_180007FA1
0x180007f92  call    ?IsDesignModeClaimPresentOnCurrentProcess@IProfileHelpers@Resources@Microsoft@@CA_NXZ; Microsoft::Resources::IProfileHelpers::IsDesignModeClaimPresentOnCurrentProcess(void)
0x180007f97  mov     bl, al
0x180007f99  mov     al, bl
0x180007f9b  add     rsp, 20h
0x180007f9f  pop     rbx
0x180007fa0  retn
0x180007fa1  mov     [rsp+28h+TokenHandle], 0
0x180007faa  call    cs:__imp_GetCurrentThread
0x180007fb0  mov     edx, 0Ch; DesiredAccess
0x180007fb5  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180007fba  mov     rcx, rax; ThreadHandle
0x180007fbd  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x180007fc1  call    cs:__imp_OpenThreadToken
0x180007fc7  test    eax, eax
0x180007fc9  jz      short loc_180007FFA
0x180007fcb  call    cs:__imp_RevertToSelf
0x180007fd1  call    ?IsDesignModeClaimPresentOnCurrentProcess@IProfileHelpers@Resources@Microsoft@@CA_NXZ; Microsoft::Resources::IProfileHelpers::IsDesignModeClaimPresentOnCurrentProcess(void)
0x180007fd6  mov     rcx, [rsp+28h+TokenHandle]; hToken
0x180007fdb  mov     bl, al
0x180007fdd  test    rcx, rcx
0x180007fe0  jz      short loc_180007F99
0x180007fe2  call    cs:__imp_ImpersonateLoggedOnUser
0x180007fe8  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x180007fed  test    rcx, rcx
0x180007ff0  jz      short loc_180007F99
0x180007ff2  call    cs:__imp_CloseHandle
0x180007ff8  jmp     short loc_180007F99
0x180007ffa  call    cs:__imp_GetLastError
0x180008000  cmp     eax, 3F0h
0x180008005  jz      short loc_180007FCB
0x180008007  xor     bl, bl
0x180008009  jmp     short loc_180007FE8
```
