# Microsoft::Resources::IProfileHelpers::IsDesignModeClaimPresentOnCurrentProcess(void)

- ea: `0x180008014`
- end: `0x180008063`
- name: `?IsDesignModeClaimPresentOnCurrentProcess@IProfileHelpers@Resources@Microsoft@@CA_NXZ`
- size: `79`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007f80`

## callees

- `0x180008014`
- `0x18000806c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180008023`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180008023`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180008036`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180008036`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008051`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008051`

## pseudocode

```c
char Microsoft::Resources::IProfileHelpers::IsDesignModeClaimPresentOnCurrentProcess(void)
{
  HANDLE CurrentProcess; // rax
  const unsigned __int16 *v1; // rdx
  char IsClaimPresentInToken; // bl
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    return 0;
  IsClaimPresentInToken = Microsoft::Resources::IProfileHelpers::IsClaimPresentInToken(TokenHandle, v1);
  CloseHandle(TokenHandle);
  return IsClaimPresentInToken;
}

```

## disassembly

```asm
0x180008014  push    rbx
0x180008016  sub     rsp, 20h
0x18000801a  mov     [rsp+28h+TokenHandle], 0
0x180008023  call    cs:__imp_GetCurrentProcess
0x180008029  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x18000802e  mov     edx, 8; DesiredAccess
0x180008033  mov     rcx, rax; ProcessHandle
0x180008036  call    cs:__imp_OpenProcessToken
0x18000803c  test    eax, eax
0x18000803e  jz      short loc_18000805F
0x180008040  mov     rcx, [rsp+28h+TokenHandle]; TokenHandle
0x180008045  call    ?IsClaimPresentInToken@IProfileHelpers@Resources@Microsoft@@CA_NPEAXPEBG@Z; Microsoft::Resources::IProfileHelpers::IsClaimPresentInToken(void *,ushort const *)
0x18000804a  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x18000804f  mov     bl, al
0x180008051  call    cs:__imp_CloseHandle
0x180008057  mov     al, bl
0x180008059  add     rsp, 20h
0x18000805d  pop     rbx
0x18000805e  retn
0x18000805f  xor     al, al
0x180008061  jmp     short loc_180008059
```
