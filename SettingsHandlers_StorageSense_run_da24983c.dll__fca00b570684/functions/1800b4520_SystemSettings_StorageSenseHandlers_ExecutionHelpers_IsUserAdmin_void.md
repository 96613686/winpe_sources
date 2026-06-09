# SystemSettings::StorageSenseHandlers::ExecutionHelpers::IsUserAdmin(void)

- ea: `0x1800b4520`
- end: `0x1800b4632`
- name: `?IsUserAdmin@ExecutionHelpers@StorageSenseHandlers@SystemSettings@@YA_NXZ`
- size: `274`
- prototype: `bool __fastcall(SystemSettings::StorageSenseHandlers::ExecutionHelpers *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005d030`
- `0x1800b5d9c`

## callees

- `0x180006e50`
- `0x180043f48`
- `0x1800b4520`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800b4550`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800b4550`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800b4583`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800b4583`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b45ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b45f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b4608`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b45ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b45f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b4608`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800b45a1`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800b45a1`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800b45dc`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800b45dc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b45c6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b45c6`

## pseudocode

```c
bool __fastcall SystemSettings::StorageSenseHandlers::ExecutionHelpers::IsUserAdmin(
        SystemSettings::StorageSenseHandlers::ExecutionHelpers *this)
{
  HANDLE CurrentProcess; // rbx
  DWORD cbSid; // [rsp+30h] [rbp-29h] BYREF
  WINBOOL IsMember; // [rsp+34h] [rbp-25h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-21h] BYREF
  HANDLE TokenInformation[2]; // [rsp+40h] [rbp-19h] BYREF
  _BYTE pSid[80]; // [rsp+50h] [rbp-9h] BYREF

  if ( !IsDesktopSKU() )
    return 1;
  TokenHandle = 0;
  TokenInformation[0] = 0;
  cbSid = 0;
  CurrentProcess = GetCurrentProcess();
  IsMember = 0;
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    cbSid = 68;
    if ( CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, pSid, &cbSid) )
    {
      if ( GetTokenInformation(TokenHandle, TokenLinkedToken, TokenInformation, 8u, &cbSid) )
        CheckTokenMembership(TokenInformation[0], pSid, &IsMember);
    }
  }
  if ( CurrentProcess )
    CloseHandle(CurrentProcess);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( TokenInformation[0] )
    CloseHandle(TokenInformation[0]);
  return IsMember != 0;
}

```

## disassembly

```asm
0x1800b4520  mov     [rsp-8+arg_0], rbx
0x1800b4525  push    rbp
0x1800b4526  lea     rbp, [rsp-57h]
0x1800b452b  sub     rsp, 0B0h
0x1800b4532  mov     rax, cs:__security_cookie
0x1800b4539  xor     rax, rsp
0x1800b453c  mov     [rbp+57h+var_10], rax
0x1800b4540  call    ?IsDesktopSKU@@YA_NXZ; IsDesktopSKU(void)
0x1800b4545  test    al, al
0x1800b4547  jnz     short loc_1800B4550
0x1800b4549  mov     al, 1
0x1800b454b  jmp     loc_1800B4615
0x1800b4550  call    cs:__imp_GetCurrentProcess
0x1800b4556  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x1800b455a  mov     [rbp+57h+TokenHandle], 0
0x1800b4562  mov     rcx, rax; ProcessHandle
0x1800b4565  mov     [rbp+57h+TokenInformation], 0
0x1800b456d  mov     edx, 8; DesiredAccess
0x1800b4572  mov     [rbp+57h+cbSid], 0
0x1800b4579  mov     rbx, rax
0x1800b457c  mov     [rbp+57h+IsMember], 0
0x1800b4583  call    cs:__imp_OpenProcessToken
0x1800b4589  test    eax, eax
0x1800b458b  jz      short loc_1800B45E2
0x1800b458d  xor     edx, edx; DomainSid
0x1800b458f  mov     [rbp+57h+cbSid], 44h ; 'D'
0x1800b4596  lea     r9, [rbp+57h+cbSid]; cbSid
0x1800b459a  lea     r8, [rbp+57h+pSid]; pSid
0x1800b459e  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x1800b45a1  call    cs:__imp_CreateWellKnownSid
0x1800b45a7  test    eax, eax
0x1800b45a9  jz      short loc_1800B45E2
0x1800b45ab  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800b45af  lea     rax, [rbp+57h+cbSid]
0x1800b45b3  mov     r9d, 8; TokenInformationLength
0x1800b45b9  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x1800b45be  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1800b45c2  lea     edx, [r9+0Bh]; TokenInformationClass
0x1800b45c6  call    cs:__imp_GetTokenInformation
0x1800b45cc  test    eax, eax
0x1800b45ce  jz      short loc_1800B45E2
0x1800b45d0  mov     rcx, [rbp+57h+TokenInformation]; TokenHandle
0x1800b45d4  lea     r8, [rbp+57h+IsMember]; IsMember
0x1800b45d8  lea     rdx, [rbp+57h+pSid]; SidToCheck
0x1800b45dc  call    cs:__imp_CheckTokenMembership
0x1800b45e2  test    rbx, rbx
0x1800b45e5  jz      short loc_1800B45F0
0x1800b45e7  mov     rcx, rbx; hObject
0x1800b45ea  call    cs:__imp_CloseHandle
0x1800b45f0  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x1800b45f4  test    rcx, rcx
0x1800b45f7  jz      short loc_1800B45FF
0x1800b45f9  call    cs:__imp_CloseHandle
0x1800b45ff  mov     rcx, [rbp+57h+TokenInformation]; hObject
0x1800b4603  test    rcx, rcx
0x1800b4606  jz      short loc_1800B460E
0x1800b4608  call    cs:__imp_CloseHandle
0x1800b460e  cmp     [rbp+57h+IsMember], 0
0x1800b4612  setnz   al
0x1800b4615  mov     rcx, [rbp+57h+var_10]
0x1800b4619  xor     rcx, rsp; StackCookie
0x1800b461c  call    __security_check_cookie
0x1800b4621  mov     rbx, [rsp+0B0h+arg_0]
0x1800b4629  add     rsp, 0B0h
0x1800b4630  pop     rbp
0x1800b4631  retn
```
