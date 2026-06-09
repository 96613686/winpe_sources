# WxGetThreadIntegrityLevel(ulong *)

- ea: `0x1800211ac`
- end: `0x180021358`
- name: `?WxGetThreadIntegrityLevel@@YAJPEAK@Z`
- size: `428`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180020468`
- `0x1800a83b4`

## callees

- `0x1800211ac`
- `0x1800701d0`
- `0x18014a7a0`
- `0x18014b3b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800212a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800212a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800211e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800211e3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800211fd`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800211fd`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800212be`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800212be`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800212af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800212af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021282`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021282`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180021256`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180021256`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180021267`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180021267`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180021242`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180021242`

## pseudocode

```c
__int64 __fastcall WxGetThreadIntegrityLevel(unsigned int *a1)
{
  HANDLE CurrentThread; // rax
  void *v3; // rbx
  signed int v4; // ebx
  PUCHAR SidSubAuthorityCount; // rax
  DWORD v6; // edi
  HANDLE CurrentProcess; // rax
  int v9; // eax
  int v10; // eax
  int LastError; // eax
  DWORD ReturnLength; // [rsp+30h] [rbp-59h] BYREF
  int v13; // [rsp+34h] [rbp-55h]
  void *TokenHandle; // [rsp+38h] [rbp-51h] BYREF
  PSID TokenInformation[14]; // [rsp+40h] [rbp-49h] BYREF

  v13 = 0;
  TokenHandle = 0;
  *a1 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x20008u, 1, &TokenHandle) )
    goto LABEL_2;
  if ( GetLastError() == 1008 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle) )
    {
LABEL_2:
      v3 = TokenHandle;
      v13 = 0;
      memset_0(TokenInformation, 0, 0x6Cu);
      ReturnLength = 108;
      if ( GetTokenInformation(v3, TokenIntegrityLevel, TokenInformation, 0x6Cu, &ReturnLength) )
      {
        v4 = 0;
        SidSubAuthorityCount = GetSidSubAuthorityCount(TokenInformation[0]);
        v6 = *GetSidSubAuthority(TokenInformation[0], (unsigned __int8)(*SidSubAuthorityCount - 1));
      }
      else
      {
        v6 = 4096;
        LastError = WxGetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
        v13 = 307;
        if ( v4 >= 0 )
          v4 = -2147418113;
      }
      if ( v4 < 0 )
        v13 = 222;
      else
        *a1 = v6;
      goto LABEL_6;
    }
    v9 = WxGetLastError();
    v4 = v9;
    if ( v9 > 0 )
      v4 = (unsigned __int16)v9 | 0x80070000;
    v13 = 219;
    if ( v4 >= 0 )
      v4 = -2147418113;
  }
  else
  {
    v10 = WxGetLastError();
    v4 = v10;
    if ( v10 > 0 )
      v4 = (unsigned __int16)v10 | 0x80070000;
    v13 = 217;
    if ( v4 >= 0 )
      v4 = -2147418113;
  }
LABEL_6:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800211ac  push    rbp
0x1800211ae  push    rbx
0x1800211af  push    rsi
0x1800211b0  push    rdi
0x1800211b1  lea     rbp, [rsp-3Fh]
0x1800211b6  sub     rsp, 0C8h
0x1800211bd  mov     rax, cs:__security_cookie
0x1800211c4  xor     rax, rsp
0x1800211c7  mov     [rbp+57h+var_30], rax
0x1800211cb  mov     rsi, rcx
0x1800211ce  mov     [rbp+57h+var_AC], 0
0x1800211d5  mov     [rbp+57h+TokenHandle], 0
0x1800211dd  mov     dword ptr [rcx], 0
0x1800211e3  call    cs:__imp_GetCurrentThread
0x1800211e9  mov     ebx, 20008h
0x1800211ee  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1800211f2  mov     edx, ebx; DesiredAccess
0x1800211f4  mov     rcx, rax; ThreadHandle
0x1800211f7  mov     r8d, 1; OpenAsSelf
0x1800211fd  call    cs:__imp_OpenThreadToken
0x180021203  test    eax, eax
0x180021205  jz      loc_1800212A2
0x18002120b  mov     rbx, [rbp+57h+TokenHandle]
0x18002120f  lea     rcx, [rbp+57h+TokenInformation]; void *
0x180021213  mov     edi, 6Ch ; 'l'
0x180021218  mov     [rbp+57h+var_AC], 0
0x18002121f  mov     r8d, edi; Size
0x180021222  xor     edx, edx; Val
0x180021224  call    memset_0
0x180021229  lea     rax, [rbp+57h+var_B0]
0x18002122d  mov     [rbp+57h+var_B0], edi
0x180021230  mov     r9d, edi; TokenInformationLength
0x180021233  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x180021238  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18002123c  mov     rcx, rbx; TokenHandle
0x18002123f  lea     edx, [rdi-53h]; TokenInformationClass
0x180021242  call    cs:__imp_GetTokenInformation
0x180021248  test    eax, eax
0x18002124a  jz      loc_18002131D
0x180021250  mov     rcx, [rbp+57h+TokenInformation]; pSid
0x180021254  xor     ebx, ebx
0x180021256  call    cs:__imp_GetSidSubAuthorityCount
0x18002125c  mov     cl, [rax]
0x18002125e  dec     cl
0x180021260  movzx   edx, cl; nSubAuthority
0x180021263  mov     rcx, [rbp+57h+TokenInformation]; pSid
0x180021267  call    cs:__imp_GetSidSubAuthority
0x18002126d  mov     edi, [rax]
0x18002126f  test    ebx, ebx
0x180021271  js      loc_18002134C
0x180021277  mov     [rsi], edi
0x180021279  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18002127d  test    rcx, rcx
0x180021280  jz      short loc_180021288
0x180021282  call    cs:__imp_CloseHandle
0x180021288  mov     eax, ebx
0x18002128a  mov     rcx, [rbp+57h+var_30]
0x18002128e  xor     rcx, rsp; StackCookie
0x180021291  call    __security_check_cookie
0x180021296  add     rsp, 0C8h
0x18002129d  pop     rdi
0x18002129e  pop     rsi
0x18002129f  pop     rbx
0x1800212a0  pop     rbp
0x1800212a1  retn
0x1800212a2  call    cs:__imp_GetLastError
0x1800212a8  cmp     eax, 3F0h
0x1800212ad  jnz     short loc_1800212F3
0x1800212af  call    cs:__imp_GetCurrentProcess
0x1800212b5  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x1800212b9  mov     edx, ebx; DesiredAccess
0x1800212bb  mov     rcx, rax; ProcessHandle
0x1800212be  call    cs:__imp_OpenProcessToken
0x1800212c4  test    eax, eax
0x1800212c6  jnz     loc_18002120B
0x1800212cc  call    WxGetLastError
0x1800212d1  mov     ebx, eax
0x1800212d3  test    eax, eax
0x1800212d5  jle     short loc_1800212E0
0x1800212d7  movzx   ebx, ax
0x1800212da  or      ebx, 80070000h
0x1800212e0  test    ebx, ebx
0x1800212e2  mov     [rbp+57h+var_AC], 0DBh
0x1800212e9  mov     eax, 8000FFFFh
0x1800212ee  cmovns  ebx, eax
0x1800212f1  jmp     short loc_180021279
0x1800212f3  call    WxGetLastError
0x1800212f8  mov     ebx, eax
0x1800212fa  test    eax, eax
0x1800212fc  jle     short loc_180021307
0x1800212fe  movzx   ebx, ax
0x180021301  or      ebx, 80070000h
0x180021307  test    ebx, ebx
0x180021309  mov     [rbp+57h+var_AC], 0D9h
0x180021310  mov     eax, 8000FFFFh
0x180021315  cmovns  ebx, eax
0x180021318  jmp     loc_180021279
0x18002131d  mov     edi, 1000h
0x180021322  call    WxGetLastError
0x180021327  mov     ebx, eax
0x180021329  test    eax, eax
0x18002132b  jle     short loc_180021336
0x18002132d  movzx   ebx, ax
0x180021330  or      ebx, 80070000h
0x180021336  test    ebx, ebx
0x180021338  mov     [rbp+57h+var_AC], 133h
0x18002133f  mov     eax, 8000FFFFh
0x180021344  cmovns  ebx, eax
0x180021347  jmp     loc_18002126F
0x18002134c  mov     [rbp+57h+var_AC], 0DEh
0x180021353  jmp     loc_180021279
```
