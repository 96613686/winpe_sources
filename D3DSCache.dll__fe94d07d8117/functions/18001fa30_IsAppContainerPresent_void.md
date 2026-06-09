# IsAppContainerPresent(void)

- ea: `0x18001fa30`
- end: `0x18001faf9`
- name: `?IsAppContainerPresent@@YAHXZ`
- size: `201`
- prototype: `_BOOL8(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001d70`
- `0x18001f410`

## callees

- `0x18001fa30`
- `0x1800449f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001fa65`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001fa65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001fa52`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001fa52`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001fa9e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001fa9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001faab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001faab`

## pseudocode

```c
_BOOL8 IsAppContainerPresent(void)
{
  HANDLE CurrentProcess; // rax
  BOOL v1; // ebx
  DWORD ReturnLength; // [rsp+30h] [rbp-78h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-70h] BYREF
  _QWORD TokenInformation[10]; // [rsp+40h] [rbp-68h] BYREF

  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle)
    && (ReturnLength = 76,
        v1 = GetTokenInformation(TokenHandle, TokenAppContainerSid, TokenInformation, 0x4Cu, &ReturnLength),
        CloseHandle(TokenHandle),
        v1) )
  {
    return TokenInformation[0] != 0;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x18001fa30  sub     rsp, 0A8h
0x18001fa37  mov     rax, cs:__security_cookie
0x18001fa3e  xor     rax, rsp
0x18001fa41  mov     [rsp+0A8h+var_18], rax
0x18001fa49  mov     [rsp+0A8h+TokenHandle], 0
0x18001fa52  call    cs:__imp_GetCurrentProcess
0x18001fa58  lea     r8, [rsp+0A8h+TokenHandle]; TokenHandle
0x18001fa5d  mov     edx, 8; DesiredAccess
0x18001fa62  mov     rcx, rax; ProcessHandle
0x18001fa65  call    cs:__imp_OpenProcessToken
0x18001fa6b  test    eax, eax
0x18001fa6d  jz      short loc_18001FABD
0x18001fa6f  mov     rcx, [rsp+0A8h+TokenHandle]; TokenHandle
0x18001fa74  lea     rax, [rsp+0A8h+var_78]
0x18001fa79  mov     r9d, 4Ch ; 'L'; TokenInformationLength
0x18001fa7f  mov     [rsp+0A8h+ReturnLength], rax; ReturnLength
0x18001fa84  lea     r8, [rsp+0A8h+TokenInformation]; TokenInformation
0x18001fa89  mov     [rsp+0A8h+var_8], rbx
0x18001fa91  mov     edx, 1Fh; TokenInformationClass
0x18001fa96  mov     [rsp+0A8h+var_78], 4Ch ; 'L'
0x18001fa9e  call    cs:__imp_GetTokenInformation
0x18001faa4  mov     rcx, [rsp+0A8h+TokenHandle]; hObject
0x18001faa9  mov     ebx, eax
0x18001faab  call    cs:__imp_CloseHandle
0x18001fab1  test    ebx, ebx
0x18001fab3  mov     rbx, [rsp+0A8h+var_8]
0x18001fabb  jnz     short loc_18001FAD7
0x18001fabd  xor     eax, eax
0x18001fabf  mov     rcx, [rsp+0A8h+var_18]
0x18001fac7  xor     rcx, rsp; StackCookie
0x18001faca  call    __security_check_cookie
0x18001facf  add     rsp, 0A8h
0x18001fad6  retn
0x18001fad7  xor     eax, eax
0x18001fad9  cmp     [rsp+0A8h+TokenInformation], rax
0x18001fade  setnz   al
0x18001fae1  mov     rcx, [rsp+0A8h+var_18]
0x18001fae9  xor     rcx, rsp; StackCookie
0x18001faec  call    __security_check_cookie
0x18001faf1  add     rsp, 0A8h
0x18001faf8  retn
```
