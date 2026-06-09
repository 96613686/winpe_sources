# Int_FwIsProcessElevated

- ea: `0x18005593c`
- end: `0x180055a16`
- name: `Int_FwIsProcessElevated`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18004c03c`

## callees

- `0x180005e0c`
- `0x1800294b0`
- `0x18005593c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800559a6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800559a6`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18005597b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18005597b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180055964`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180055964`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800559c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800559c3`

## pseudocode

```c
__int64 Int_FwIsProcessElevated()
{
  unsigned int v0; // ebx
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+30h] [rbp-28h] BYREF
  unsigned int TokenInformation; // [rsp+38h] [rbp-20h] BYREF
  DWORD ReturnLength; // [rsp+3Ch] [rbp-1Ch] BYREF

  v0 = 0;
  ReturnLength = 4;
  TokenHandle = 0;
  TokenInformation = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle)
    && GetTokenInformation(TokenHandle, TokenElevation, &TokenInformation, 4u, &ReturnLength) )
  {
    v0 = TokenInformation;
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 628, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v0);
  return v0;
}

```

## disassembly

```asm
0x18005593c  push    rbx
0x18005593e  sub     rsp, 50h
0x180055942  mov     rax, cs:__security_cookie
0x180055949  xor     rax, rsp
0x18005594c  mov     [rsp+58h+var_18], rax
0x180055951  xor     ebx, ebx
0x180055953  mov     [rsp+58h+var_1C], 4
0x18005595b  mov     [rsp+58h+TokenHandle], rbx
0x180055960  mov     [rsp+58h+TokenInformation], ebx
0x180055964  call    cs:__imp_GetCurrentProcess
0x18005596b  nop     dword ptr [rax+rax+00h]
0x180055970  mov     rcx, rax; ProcessHandle
0x180055973  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x180055978  lea     edx, [rbx+8]; DesiredAccess
0x18005597b  call    cs:__imp_OpenProcessToken
0x180055982  nop     dword ptr [rax+rax+00h]
0x180055987  test    eax, eax
0x180055989  jz      short loc_1800559B9
0x18005598b  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x180055990  lea     rax, [rsp+58h+var_1C]
0x180055995  lea     r9d, [rbx+4]; TokenInformationLength
0x180055999  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18005599e  lea     r8, [rsp+58h+TokenInformation]; TokenInformation
0x1800559a3  lea     edx, [rbx+14h]; TokenInformationClass
0x1800559a6  call    cs:__imp_GetTokenInformation
0x1800559ad  nop     dword ptr [rax+rax+00h]
0x1800559b2  test    eax, eax
0x1800559b4  cmovnz  ebx, [rsp+58h+TokenInformation]
0x1800559b9  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x1800559be  test    rcx, rcx
0x1800559c1  jz      short loc_1800559CF
0x1800559c3  call    cs:__imp_CloseHandle
0x1800559ca  nop     dword ptr [rax+rax+00h]
0x1800559cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800559d6  lea     rax, WPP_GLOBAL_Control
0x1800559dd  cmp     rcx, rax
0x1800559e0  jz      short loc_180055A00
0x1800559e2  test    byte ptr [rcx+1Ch], 8
0x1800559e6  jz      short loc_180055A00
0x1800559e8  mov     rcx, [rcx+10h]
0x1800559ec  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x1800559f3  mov     edx, 274h
0x1800559f8  mov     r9d, ebx
0x1800559fb  call    WPP_SF_d
0x180055a00  mov     eax, ebx
0x180055a02  mov     rcx, [rsp+58h+var_18]
0x180055a07  xor     rcx, rsp; StackCookie
0x180055a0a  call    __security_check_cookie
0x180055a0f  add     rsp, 50h
0x180055a13  pop     rbx
0x180055a14  retn
```
