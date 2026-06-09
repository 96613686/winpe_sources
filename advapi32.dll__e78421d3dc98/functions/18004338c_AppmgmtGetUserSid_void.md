# AppmgmtGetUserSid(void *)

- ea: `0x18004338c`
- end: `0x1800434b5`
- name: `?AppmgmtGetUserSid@@YAPEAXPEAX@Z`
- size: `297`
- prototype: `void *__fastcall(void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180044c20`

## callees

- `0x18004338c`
- `0x180065090`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x180043464`
- `KERNELBASE!LocalAlloc` at `0x180043464`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800433e0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800433e0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180043407`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180043407`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800433f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800433f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800433cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800433cd`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18004347c`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18004347c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180043457`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180043457`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180043434`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180043434`
- `KERNEL32!LocalFree` at `0x180043489`
- `KERNEL32!LocalFree` at `0x180043489`
- `KERNEL32!GetLastError` at `0x1800433ea`
- `KERNEL32!GetLastError` at `0x1800433ea`
- `KERNEL32!CloseHandle` at `0x180043445`
- `KERNEL32!CloseHandle` at `0x180043445`

## pseudocode

```c
void *__fastcall AppmgmtGetUserSid(void *a1)
{
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  BOOL v4; // edi
  HLOCAL v6; // rax
  void *v7; // rbx
  DWORD nDestinationSidLength; // [rsp+30h] [rbp-29h] BYREF
  HANDLE TokenHandle; // [rsp+38h] [rbp-21h] BYREF
  PSID TokenInformation[12]; // [rsp+40h] [rbp-19h] BYREF

  TokenHandle = 0;
  nDestinationSidLength = 0;
  if ( a1 )
  {
    TokenHandle = a1;
  }
  else
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      if ( GetLastError() != 1008 )
        return 0;
      CurrentProcess = GetCurrentProcess();
      if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
        return 0;
    }
  }
  nDestinationSidLength = 84;
  v4 = GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x54u, &nDestinationSidLength);
  if ( !a1 )
    CloseHandle(TokenHandle);
  if ( !v4 )
    return 0;
  nDestinationSidLength = GetLengthSid(TokenInformation[0]);
  v6 = LocalAlloc(0, nDestinationSidLength);
  v7 = v6;
  if ( v6 )
  {
    if ( !CopySid(nDestinationSidLength, v6, TokenInformation[0]) )
    {
      LocalFree(v7);
      return 0;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18004338c  mov     [rsp-8+arg_8], rbx
0x180043391  mov     [rsp-8+arg_10], rdi
0x180043396  push    rbp
0x180043397  lea     rbp, [rsp-57h]
0x18004339c  sub     rsp, 0B0h
0x1800433a3  mov     rax, cs:__security_cookie
0x1800433aa  xor     rax, rsp
0x1800433ad  mov     [rbp+57h+var_10], rax
0x1800433b1  mov     [rbp+57h+TokenHandle], 0
0x1800433b9  mov     rbx, rcx
0x1800433bc  mov     [rbp+57h+nDestinationSidLength], 0
0x1800433c3  mov     edi, 1
0x1800433c8  test    rcx, rcx
0x1800433cb  jnz     short loc_180043413
0x1800433cd  call    cs:__imp_GetCurrentThread
0x1800433d3  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1800433d7  mov     r8d, edi; OpenAsSelf
0x1800433da  mov     rcx, rax; ThreadHandle
0x1800433dd  lea     edx, [rbx+8]; DesiredAccess
0x1800433e0  call    cs:__imp_OpenThreadToken
0x1800433e6  test    eax, eax
0x1800433e8  jnz     short loc_180043417
0x1800433ea  call    cs:__imp_GetLastError
0x1800433f0  cmp     eax, 3F0h
0x1800433f5  jnz     short loc_18004344F
0x1800433f7  call    cs:__imp_GetCurrentProcess
0x1800433fd  mov     rcx, rax; ProcessHandle
0x180043400  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x180043404  lea     edx, [rbx+8]; DesiredAccess
0x180043407  call    cs:__imp_OpenProcessToken
0x18004340d  test    eax, eax
0x18004340f  jz      short loc_18004344F
0x180043411  jmp     short loc_180043417
0x180043413  mov     [rbp+57h+TokenHandle], rbx
0x180043417  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18004341b  lea     rax, [rbp+57h+nDestinationSidLength]
0x18004341f  mov     r9d, 54h ; 'T'; TokenInformationLength
0x180043425  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x18004342a  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18004342e  mov     [rbp+57h+nDestinationSidLength], r9d
0x180043432  mov     edx, edi; TokenInformationClass
0x180043434  call    cs:__imp_GetTokenInformation
0x18004343a  mov     edi, eax
0x18004343c  test    rbx, rbx
0x18004343f  jnz     short loc_18004344B
0x180043441  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180043445  call    cs:__imp_CloseHandle
0x18004344b  test    edi, edi
0x18004344d  jnz     short loc_180043453
0x18004344f  xor     eax, eax
0x180043451  jmp     short loc_180043494
0x180043453  mov     rcx, [rbp+57h+TokenInformation]; pSid
0x180043457  call    cs:__imp_GetLengthSid
0x18004345d  mov     edx, eax; uBytes
0x18004345f  xor     ecx, ecx; uFlags
0x180043461  mov     [rbp+57h+nDestinationSidLength], edx
0x180043464  call    cs:__imp_LocalAlloc
0x18004346a  mov     rbx, rax
0x18004346d  test    rax, rax
0x180043470  jz      short loc_180043491
0x180043472  mov     r8, [rbp+57h+TokenInformation]; pSourceSid
0x180043476  mov     rdx, rax; pDestinationSid
0x180043479  mov     ecx, [rbp+57h+nDestinationSidLength]; nDestinationSidLength
0x18004347c  call    cs:__imp_CopySid
0x180043482  test    eax, eax
0x180043484  jnz     short loc_180043491
0x180043486  mov     rcx, rbx; hMem
0x180043489  call    cs:__imp_LocalFree
0x18004348f  xor     ebx, ebx
0x180043491  mov     rax, rbx
0x180043494  mov     rcx, [rbp+57h+var_10]
0x180043498  xor     rcx, rsp; StackCookie
0x18004349b  call    __security_check_cookie
0x1800434a0  lea     r11, [rsp+0B0h+var_s0]
0x1800434a8  mov     rbx, [r11+18h]
0x1800434ac  mov     rdi, [r11+20h]
0x1800434b0  mov     rsp, r11
0x1800434b3  pop     rbp
0x1800434b4  retn
```
