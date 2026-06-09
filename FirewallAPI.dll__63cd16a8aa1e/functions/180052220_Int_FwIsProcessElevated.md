# Int_FwIsProcessElevated

- ea: `0x180052220`
- end: `0x1800522e1`
- name: `Int_FwIsProcessElevated`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18004861c`

## callees

- `0x180005954`
- `0x1800277b0`
- `0x180052220`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005227e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005227e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180052259`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180052259`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180052248`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180052248`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180052295`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180052295`

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
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 629, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v0);
  return v0;
}

```

## disassembly

```asm
0x180052220  push    rbx
0x180052222  sub     rsp, 50h
0x180052226  mov     rax, cs:__security_cookie
0x18005222d  xor     rax, rsp
0x180052230  mov     [rsp+58h+var_18], rax
0x180052235  xor     ebx, ebx
0x180052237  mov     [rsp+58h+var_1C], 4
0x18005223f  mov     [rsp+58h+TokenHandle], rbx
0x180052244  mov     [rsp+58h+TokenInformation], ebx
0x180052248  call    cs:__imp_GetCurrentProcess
0x18005224e  mov     rcx, rax; ProcessHandle
0x180052251  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x180052256  lea     edx, [rbx+8]; DesiredAccess
0x180052259  call    cs:__imp_OpenProcessToken
0x18005225f  test    eax, eax
0x180052261  jz      short loc_18005228B
0x180052263  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x180052268  lea     rax, [rsp+58h+var_1C]
0x18005226d  lea     r9d, [rbx+4]; TokenInformationLength
0x180052271  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180052276  lea     r8, [rsp+58h+TokenInformation]; TokenInformation
0x18005227b  lea     edx, [rbx+14h]; TokenInformationClass
0x18005227e  call    cs:__imp_GetTokenInformation
0x180052284  test    eax, eax
0x180052286  cmovnz  ebx, [rsp+58h+TokenInformation]
0x18005228b  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x180052290  test    rcx, rcx
0x180052293  jz      short loc_18005229B
0x180052295  call    cs:__imp_CloseHandle
0x18005229b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800522a2  lea     rax, WPP_GLOBAL_Control
0x1800522a9  cmp     rcx, rax
0x1800522ac  jz      short loc_1800522CC
0x1800522ae  test    byte ptr [rcx+1Ch], 8
0x1800522b2  jz      short loc_1800522CC
0x1800522b4  mov     rcx, [rcx+10h]
0x1800522b8  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x1800522bf  mov     edx, 275h
0x1800522c4  mov     r9d, ebx
0x1800522c7  call    WPP_SF_d
0x1800522cc  mov     eax, ebx
0x1800522ce  mov     rcx, [rsp+58h+var_18]
0x1800522d3  xor     rcx, rsp; StackCookie
0x1800522d6  call    __security_check_cookie
0x1800522db  add     rsp, 50h
0x1800522df  pop     rbx
0x1800522e0  retn
```
