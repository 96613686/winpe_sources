# CallerIdentity::IsProcessAppContainer(void *,bool *)

- ea: `0x18004ef68`
- end: `0x18004f048`
- name: `?IsProcessAppContainer@CallerIdentity@@YAJPEAXPEA_N@Z`
- size: `224`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, void *, bool *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180022c60`

## callees

- `0x18004b914`
- `0x18004ef68`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004efa6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004efa6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004ef84`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004ef84`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004ef9c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004ef9c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004f035`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004f035`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004effa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004effa`

## pseudocode

```c
__int64 __fastcall CallerIdentity::IsProcessAppContainer(HANDLE ProcessHandle, bool *a2, bool *a3)
{
  signed int LastError; // eax
  signed int Error; // ebx
  char *v7; // rcx
  int TokenInformation; // [rsp+40h] [rbp+8h] BYREF
  DWORD ReturnLength; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  *a2 = 0;
  TokenHandle = 0;
  if ( ProcessHandle == GetCurrentProcess() )
  {
    TokenHandle = (void *)-4LL;
    goto LABEL_6;
  }
  if ( OpenProcessToken(ProcessHandle, 8u, &TokenHandle) )
  {
LABEL_6:
    Error = 0;
    goto LABEL_7;
  }
  LastError = GetLastError();
  Error = LastError;
  if ( LastError > 0 )
    Error = (unsigned __int16)LastError | 0x80070000;
LABEL_7:
  if ( Error < 0 )
    goto LABEL_12;
  ReturnLength = 0;
  TokenInformation = 0;
  if ( GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) )
  {
    Error = 0;
  }
  else
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
      goto LABEL_12;
  }
  *a2 = TokenInformation != 0;
LABEL_12:
  v7 = (char *)TokenHandle;
  TokenHandle = 0;
  if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v7);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18004ef68  mov     [rsp+arg_18], rbx
0x18004ef6d  push    rdi
0x18004ef6e  sub     rsp, 30h
0x18004ef72  mov     rdi, rdx
0x18004ef75  mov     byte ptr [rdx], 0
0x18004ef78  mov     rbx, rcx
0x18004ef7b  mov     [rsp+38h+TokenHandle], 0
0x18004ef84  call    cs:__imp_GetCurrentProcess
0x18004ef8a  cmp     rbx, rax
0x18004ef8d  jz      short loc_18004EFBD
0x18004ef8f  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x18004ef94  mov     edx, 8; DesiredAccess
0x18004ef99  mov     rcx, rbx; ProcessHandle
0x18004ef9c  call    cs:__imp_OpenProcessToken
0x18004efa2  test    eax, eax
0x18004efa4  jnz     short loc_18004EFC6
0x18004efa6  call    cs:__imp_GetLastError
0x18004efac  mov     ebx, eax
0x18004efae  test    eax, eax
0x18004efb0  jle     short loc_18004EFC8
0x18004efb2  movzx   ebx, ax
0x18004efb5  or      ebx, 80070000h
0x18004efbb  jmp     short loc_18004EFC8
0x18004efbd  mov     [rsp+38h+TokenHandle], 0FFFFFFFFFFFFFFFCh
0x18004efc6  xor     ebx, ebx
0x18004efc8  test    ebx, ebx
0x18004efca  js      short loc_18004F01D
0x18004efcc  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x18004efd1  lea     rax, [rsp+38h+arg_8]
0x18004efd6  mov     r9d, 4; TokenInformationLength
0x18004efdc  mov     [rsp+38h+arg_8], 0
0x18004efe4  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x18004efe9  mov     [rsp+38h+TokenInformation], 0
0x18004eff1  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18004eff6  lea     edx, [r9+19h]; TokenInformationClass
0x18004effa  call    cs:__imp_GetTokenInformation
0x18004f000  test    eax, eax
0x18004f002  jz      short loc_18004F008
0x18004f004  xor     ebx, ebx
0x18004f006  jmp     short loc_18004F013
0x18004f008  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18004f00d  mov     ebx, eax
0x18004f00f  test    eax, eax
0x18004f011  js      short loc_18004F01D
0x18004f013  cmp     [rsp+38h+TokenInformation], 0
0x18004f018  setnz   al
0x18004f01b  mov     [rdi], al
0x18004f01d  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x18004f022  mov     [rsp+38h+TokenHandle], 0
0x18004f02b  lea     rdx, [rcx-1]
0x18004f02f  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18004f033  ja      short loc_18004F03B
0x18004f035  call    cs:__imp_CloseHandle
0x18004f03b  mov     eax, ebx
0x18004f03d  mov     rbx, [rsp+38h+arg_18]
0x18004f042  add     rsp, 30h
0x18004f046  pop     rdi
0x18004f047  retn
```
