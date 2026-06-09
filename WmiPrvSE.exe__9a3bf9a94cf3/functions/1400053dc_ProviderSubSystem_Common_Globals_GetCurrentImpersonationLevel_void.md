# ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel(void)

- ea: `0x1400053dc`
- end: `0x14000549a`
- name: `?GetCurrentImpersonationLevel@ProviderSubSystem_Common_Globals@@SAKXZ`
- size: `190`
- prototype: `unsigned int(void)`
- caller_count: `34`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140005080`
- `0x140005200`
- `0x140005544`
- `0x140005984`
- `0x140005a14`
- `0x14000a640`
- `0x14000b7d0`
- `0x14000c3a0`
- `0x14000de90`
- `0x14000ed60`
- `0x14000fa50`
- `0x14001bdb4`
- `0x14001c6d8`
- `0x14001cbf4`
- `0x140021dc0`
- `0x140022720`
- `0x1400260d0`
- `0x140027570`
- `0x140027850`
- `0x140027afc`
- `0x140027ca0`
- `0x1400294c0`
- `0x140030f90`
- `0x1400310f0`
- `0x140036450`
- `0x14003d680`
- `0x14003d860`
- `0x14003dc20`
- `0x14003df40`
- `0x14003e2c0`
- `0x14003e4b0`
- `0x14003e650`
- `0x14003e8d0`
- `0x14003ebd0`

## callees

- `0x1400053dc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14000543d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14000543d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005474`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005474`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000544a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000544a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400053ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400053ef`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140005408`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140005408`

## pseudocode

```c
__int64 ProviderSubSystem_Common_Globals::GetCurrentImpersonationLevel(void)
{
  HANDLE CurrentThread; // rax
  unsigned int v1; // edi
  BOOL v2; // ebx
  DWORD LastError; // eax
  bool v5; // zf
  int TokenInformation; // [rsp+40h] [rbp+8h] BYREF
  DWORD ReturnLength; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  v1 = 1;
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    if ( LastError == 1309 )
      return 4;
    v5 = LastError == 1008;
LABEL_10:
    if ( !v5 )
      return v1;
    return 4;
  }
  TokenInformation = 0;
  ReturnLength = 0;
  v2 = GetTokenInformation(TokenHandle, TokenImpersonationLevel, &TokenInformation, 4u, &ReturnLength);
  CloseHandle(TokenHandle);
  if ( v2 && TokenInformation )
  {
    if ( TokenInformation == 1 )
      return 2;
    if ( TokenInformation == 2 )
      return 3;
    v5 = TokenInformation == 3;
    goto LABEL_10;
  }
  return v1;
}

```

## disassembly

```asm
0x1400053dc  mov     [rsp+arg_18], rbx
0x1400053e1  push    rdi
0x1400053e2  sub     rsp, 30h
0x1400053e6  mov     [rsp+38h+TokenHandle], 0
0x1400053ef  call    cs:__imp_GetCurrentThread
0x1400053f5  mov     edi, 1
0x1400053fa  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x1400053ff  mov     rcx, rax; ThreadHandle
0x140005402  mov     r8d, edi; OpenAsSelf
0x140005405  lea     edx, [rdi+7]; DesiredAccess
0x140005408  call    cs:__imp_OpenThreadToken
0x14000540e  test    eax, eax
0x140005410  jz      short loc_140005474
0x140005412  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x140005417  lea     rax, [rsp+38h+arg_8]
0x14000541c  lea     r9d, [rdi+3]; TokenInformationLength
0x140005420  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x140005425  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x14000542a  mov     [rsp+38h+TokenInformation], 0
0x140005432  lea     edx, [rdi+8]; TokenInformationClass
0x140005435  mov     [rsp+38h+arg_8], 0
0x14000543d  call    cs:__imp_GetTokenInformation
0x140005443  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x140005448  mov     ebx, eax
0x14000544a  call    cs:__imp_CloseHandle
0x140005450  test    ebx, ebx
0x140005452  jz      short loc_140005467
0x140005454  mov     ecx, [rsp+38h+TokenInformation]
0x140005458  test    ecx, ecx
0x14000545a  jz      short loc_140005467
0x14000545c  sub     ecx, edi
0x14000545e  jz      short loc_140005493
0x140005460  sub     ecx, edi
0x140005462  jnz     short loc_14000548F
0x140005464  lea     edi, [rcx+3]
0x140005467  mov     rbx, [rsp+38h+arg_18]
0x14000546c  mov     eax, edi
0x14000546e  add     rsp, 30h
0x140005472  pop     rdi
0x140005473  retn
0x140005474  call    cs:__imp_GetLastError
0x14000547a  cmp     eax, 51Dh
0x14000547f  jz      short loc_140005488
0x140005481  cmp     eax, 3F0h
0x140005486  jnz     short loc_140005467
0x140005488  mov     edi, 4
0x14000548d  jmp     short loc_140005467
0x14000548f  cmp     ecx, edi
0x140005491  jmp     short loc_140005486
0x140005493  mov     edi, 2
0x140005498  jmp     short loc_140005467
```
