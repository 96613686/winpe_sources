# CallerIdentity::IsProcessAppContainer(void *,bool *)

- ea: `0x180032a50`
- end: `0x180032b41`
- name: `?IsProcessAppContainer@CallerIdentity@@YAJPEAXPEA_N@Z`
- size: `241`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, void *, bool *)`
- caller_count: `9`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000e008`
- `0x1800107b0`
- `0x1800322f8`
- `0x180032964`
- `0x180055240`
- `0x18005facc`
- `0x1800f1e54`
- `0x180109c10`
- `0x18010f8f0`

## callees

- `0x180032a50`
- `0x1801afa28`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032b1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032b1b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032b39`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032b39`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180032b0d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180032b0d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180032a6c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180032a6c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180032ab8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180032ab8`

## pseudocode

```c
__int64 __fastcall CallerIdentity::IsProcessAppContainer(HANDLE ProcessHandle, bool *a2, bool *a3)
{
  signed int Error; // ebx
  char *v6; // rcx
  signed int LastError; // eax
  int TokenInformation; // [rsp+40h] [rbp+8h] BYREF
  DWORD ReturnLength; // [rsp+48h] [rbp+10h] BYREF
  HANDLE TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  *a2 = 0;
  TokenHandle = 0;
  if ( ProcessHandle == GetCurrentProcess() )
  {
    TokenHandle = (HANDLE)-4LL;
LABEL_3:
    Error = 0;
    goto LABEL_4;
  }
  if ( OpenProcessToken(ProcessHandle, 8u, &TokenHandle) )
    goto LABEL_3;
  LastError = GetLastError();
  Error = LastError;
  if ( LastError > 0 )
    Error = (unsigned __int16)LastError | 0x80070000;
LABEL_4:
  if ( Error < 0 )
    goto LABEL_8;
  ReturnLength = 0;
  TokenInformation = 0;
  if ( GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) )
  {
    Error = 0;
LABEL_7:
    *a2 = TokenInformation != 0;
    goto LABEL_8;
  }
  Error = ResultFromKnownLastError();
  if ( Error >= 0 )
    goto LABEL_7;
LABEL_8:
  v6 = (char *)TokenHandle;
  TokenHandle = 0;
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v6);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180032a50  mov     [rsp+arg_18], rbx
0x180032a55  push    rdi
0x180032a56  sub     rsp, 30h
0x180032a5a  mov     rdi, rdx
0x180032a5d  mov     byte ptr [rdx], 0
0x180032a60  mov     rbx, rcx
0x180032a63  mov     [rsp+38h+TokenHandle], 0
0x180032a6c  call    cs:__imp_GetCurrentProcess
0x180032a72  cmp     rbx, rax
0x180032a75  jnz     loc_180032B00
0x180032a7b  mov     [rsp+38h+TokenHandle], 0FFFFFFFFFFFFFFFCh
0x180032a84  xor     ebx, ebx
0x180032a86  test    ebx, ebx
0x180032a88  js      short loc_180032ACE
0x180032a8a  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x180032a8f  lea     rax, [rsp+38h+arg_8]
0x180032a94  mov     r9d, 4; TokenInformationLength
0x180032a9a  mov     [rsp+38h+arg_8], 0
0x180032aa2  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x180032aa7  mov     [rsp+38h+TokenInformation], 0
0x180032aaf  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180032ab4  lea     edx, [r9+19h]; TokenInformationClass
0x180032ab8  call    cs:__imp_GetTokenInformation
0x180032abe  test    eax, eax
0x180032ac0  jz      short loc_180032AF3
0x180032ac2  xor     ebx, ebx
0x180032ac4  cmp     [rsp+38h+TokenInformation], 0
0x180032ac9  setnz   al
0x180032acc  mov     [rdi], al
0x180032ace  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180032ad3  mov     [rsp+38h+TokenHandle], 0
0x180032adc  lea     rdx, [rcx-1]
0x180032ae0  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180032ae4  jbe     short loc_180032B39
0x180032ae6  mov     eax, ebx
0x180032ae8  mov     rbx, [rsp+38h+arg_18]
0x180032aed  add     rsp, 30h
0x180032af1  pop     rdi
0x180032af2  retn
0x180032af3  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180032af8  mov     ebx, eax
0x180032afa  test    eax, eax
0x180032afc  js      short loc_180032ACE
0x180032afe  jmp     short loc_180032AC4
0x180032b00  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x180032b05  mov     edx, 8; DesiredAccess
0x180032b0a  mov     rcx, rbx; ProcessHandle
0x180032b0d  call    cs:__imp_OpenProcessToken
0x180032b13  test    eax, eax
0x180032b15  jnz     loc_180032A84
0x180032b1b  call    cs:__imp_GetLastError
0x180032b21  mov     ebx, eax
0x180032b23  test    eax, eax
0x180032b25  jle     loc_180032A86
0x180032b2b  movzx   ebx, ax
0x180032b2e  or      ebx, 80070000h
0x180032b34  jmp     loc_180032A86
0x180032b39  call    cs:__imp_CloseHandle
0x180032b3f  jmp     short loc_180032AE6
```
