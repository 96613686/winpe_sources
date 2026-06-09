# GetCurrentClientToken(int)

- ea: `0x180005314`
- end: `0x1800053b6`
- name: `?GetCurrentClientToken@@YAPEAXH@Z`
- size: `162`
- prototype: `void *__fastcall(int)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000b68c`
- `0x18000f820`

## callees

- `0x180001f90`
- `0x180005314`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005363`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005363`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000538b`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000538b`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180005325`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180005325`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000533f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000533f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180005359`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180005359`

## string_xrefs

- `0x18000532f`: `Failed to set Impersonation token due to error %X`
- `0x18000537c`: `Failed to OpenThreadToken due to error %X`

## pseudocode

```c
void *__fastcall GetCurrentClientToken(int a1)
{
  HRESULT v2; // eax
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  HRESULT v5; // eax
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  TokenHandle = 0;
  v2 = CoImpersonateClient();
  if ( v2 >= 0 )
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, a1 != 0 ? 131148 : 131144, 1, &TokenHandle) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      ABO_MAPPER_LOG::WriteLogEntry(g_pAboLog, L"Failed to OpenThreadToken due to error %X", (unsigned int)LastError);
    }
    v5 = CoRevertToSelf();
    if ( v5 < 0 )
      ABO_MAPPER_LOG::WriteLogEntry(g_pAboLog, L"Failed to revert to self due to error %X", (unsigned int)v5);
  }
  else
  {
    ABO_MAPPER_LOG::WriteLogEntry(g_pAboLog, L"Failed to set Impersonation token due to error %X", (unsigned int)v2);
  }
  return TokenHandle;
}

```

## disassembly

```asm
0x180005314  push    rbx
0x180005316  sub     rsp, 20h
0x18000531a  mov     ebx, ecx
0x18000531c  mov     [rsp+28h+TokenHandle], 0
0x180005325  call    cs:__imp_CoImpersonateClient
0x18000532b  test    eax, eax
0x18000532d  jns     short loc_180005338
0x18000532f  lea     rdx, aFailedToSetImp; "Failed to set Impersonation token due t"...
0x180005336  jmp     short loc_18000539C
0x180005338  neg     ebx
0x18000533a  sbb     ebx, ebx
0x18000533c  and     ebx, 4
0x18000533f  call    cs:__imp_GetCurrentThread
0x180005345  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18000534a  mov     r8d, 1; OpenAsSelf
0x180005350  mov     rcx, rax; ThreadHandle
0x180005353  lea     edx, [rbx+20048h]; DesiredAccess
0x180005359  call    cs:__imp_OpenThreadToken
0x18000535f  test    eax, eax
0x180005361  jnz     short loc_18000538B
0x180005363  call    cs:__imp_GetLastError
0x180005369  test    eax, eax
0x18000536b  jle     short loc_180005375
0x18000536d  movzx   eax, ax
0x180005370  or      eax, 80070000h
0x180005375  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x18000537c  lea     rdx, aFailedToOpenth; "Failed to OpenThreadToken due to error "...
0x180005383  mov     r8d, eax
0x180005386  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x18000538b  call    cs:__imp_CoRevertToSelf
0x180005391  test    eax, eax
0x180005393  jns     short loc_1800053AB
0x180005395  lea     rdx, aFailedToRevert; "Failed to revert to self due to error %"...
0x18000539c  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x1800053a3  mov     r8d, eax
0x1800053a6  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x1800053ab  mov     rax, [rsp+28h+TokenHandle]
0x1800053b0  add     rsp, 20h
0x1800053b4  pop     rbx
0x1800053b5  retn
```
