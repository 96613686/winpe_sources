# GetCurrentUserSid(void * *)

- ea: `0x1800cfd18`
- end: `0x1800cff10`
- name: `?GetCurrentUserSid@@YAJPEAPEAX@Z`
- size: `504`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800705dc`
- `0x1800d9834`

## callees

- `0x1800cfd18`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cfdde`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cfe48`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cfeb4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cfecd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cfdde`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cfe48`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cfeb4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cfecd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800cfec2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800cfedb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800cfec2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800cfedb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800cfdec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800cfe56`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800cfdec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800cfe56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cfd68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cfdb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cfe21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cfe7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cfd68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cfdb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cfe21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cfe7c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800cfd43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800cfd43`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800cfd58`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800cfd58`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cfef7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cfef7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800cfda5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800cfe17`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800cfda5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800cfe17`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800cfe67`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800cfe67`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800cfe40`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800cfe40`

## pseudocode

```c
__int64 __fastcall GetCurrentUserSid(void **a1)
{
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  signed int v4; // ebx
  signed int v5; // eax
  DWORD v6; // ebx
  HANDLE ProcessHeap; // rax
  PSID *v8; // rsi
  signed int v9; // eax
  DWORD LengthSid; // edi
  HANDLE v11; // rax
  void *v12; // rbp
  signed int v13; // eax
  HANDLE v14; // rax
  HANDLE v15; // rax
  DWORD TokenInformationLength; // [rsp+60h] [rbp+8h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp+10h] BYREF

  TokenHandle = 0;
  TokenInformationLength = 0;
  *a1 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( !LastError )
    {
LABEL_34:
      v4 = -2147467259;
      goto LABEL_35;
    }
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 < 0 )
      goto LABEL_35;
  }
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, TokenInformationLength, &TokenInformationLength) )
  {
    v4 = 0;
    goto LABEL_35;
  }
  v5 = GetLastError();
  v4 = v5;
  if ( !v5 )
    goto LABEL_34;
  if ( v5 > 0 )
    v4 = (unsigned __int16)v5 | 0x80070000;
  if ( v4 == -2147024774 )
  {
    v6 = TokenInformationLength;
    ProcessHeap = GetProcessHeap();
    v8 = (PSID *)HeapAlloc(ProcessHeap, 8u, v6);
    if ( !v8 )
    {
      v4 = -2147024882;
      goto LABEL_35;
    }
    if ( !GetTokenInformation(TokenHandle, TokenUser, v8, TokenInformationLength, &TokenInformationLength) )
    {
      v9 = GetLastError();
      v4 = v9;
      if ( !v9 )
      {
        v4 = -2147467259;
LABEL_33:
        v15 = GetProcessHeap();
        HeapFree(v15, 0, v8);
        goto LABEL_35;
      }
      if ( v9 > 0 )
        v4 = (unsigned __int16)v9 | 0x80070000;
      if ( v4 < 0 )
        goto LABEL_33;
    }
    LengthSid = GetLengthSid(*v8);
    v11 = GetProcessHeap();
    v12 = HeapAlloc(v11, 8u, LengthSid);
    if ( CopySid(LengthSid, v12, *v8) )
    {
      v4 = 0;
LABEL_25:
      *a1 = v12;
      goto LABEL_33;
    }
    v13 = GetLastError();
    v4 = v13;
    if ( v13 )
    {
      if ( v13 > 0 )
        v4 = (unsigned __int16)v13 | 0x80070000;
      if ( v4 >= 0 )
        goto LABEL_25;
    }
    else
    {
      v4 = -2147467259;
    }
  }
  else
  {
    if ( v4 >= 0 )
      goto LABEL_35;
    v8 = 0;
    v12 = 0;
  }
  if ( v12 )
  {
    v14 = GetProcessHeap();
    HeapFree(v14, 0, v12);
  }
  if ( v8 )
    goto LABEL_33;
LABEL_35:
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800cfd18  mov     [rsp+arg_10], rbx
0x1800cfd1d  push    rbp
0x1800cfd1e  push    rsi
0x1800cfd1f  push    rdi
0x1800cfd20  push    r12
0x1800cfd22  push    r14
0x1800cfd24  sub     rsp, 30h
0x1800cfd28  mov     r14, rcx
0x1800cfd2b  mov     [rsp+58h+TokenHandle], 0
0x1800cfd34  mov     [rsp+58h+TokenInformationLength], 0
0x1800cfd3c  mov     qword ptr [rcx], 0
0x1800cfd43  call    cs:__imp_GetCurrentProcess
0x1800cfd49  mov     ebp, 8
0x1800cfd4e  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x1800cfd53  mov     rcx, rax; ProcessHandle
0x1800cfd56  mov     edx, ebp; DesiredAccess
0x1800cfd58  call    cs:__imp_OpenProcessToken
0x1800cfd5e  mov     r12d, 80070000h
0x1800cfd64  test    eax, eax
0x1800cfd66  jnz     short loc_1800CFD88
0x1800cfd68  call    cs:__imp_GetLastError
0x1800cfd6e  mov     ebx, eax
0x1800cfd70  test    eax, eax
0x1800cfd72  jz      loc_1800CFEE3
0x1800cfd78  jle     short loc_1800CFD80
0x1800cfd7a  movzx   ebx, ax
0x1800cfd7d  or      ebx, r12d
0x1800cfd80  test    ebx, ebx
0x1800cfd82  js      loc_1800CFEE8
0x1800cfd88  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x1800cfd8d  lea     rax, [rsp+58h+TokenInformationLength]
0x1800cfd92  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x1800cfd97  xor     r8d, r8d; TokenInformation
0x1800cfd9a  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1800cfd9f  lea     edi, [r8+1]
0x1800cfda3  mov     edx, edi; TokenInformationClass
0x1800cfda5  call    cs:__imp_GetTokenInformation
0x1800cfdab  test    eax, eax
0x1800cfdad  jz      short loc_1800CFDB6
0x1800cfdaf  xor     ebx, ebx
0x1800cfdb1  jmp     loc_1800CFEE8
0x1800cfdb6  call    cs:__imp_GetLastError
0x1800cfdbc  mov     ebx, eax
0x1800cfdbe  test    eax, eax
0x1800cfdc0  jz      loc_1800CFEE3
0x1800cfdc6  jle     short loc_1800CFDCE
0x1800cfdc8  movzx   ebx, ax
0x1800cfdcb  or      ebx, r12d
0x1800cfdce  cmp     ebx, 8007007Ah
0x1800cfdd4  jnz     loc_1800CFEA7
0x1800cfdda  mov     ebx, [rsp+58h+TokenInformationLength]
0x1800cfdde  call    cs:__imp_GetProcessHeap
0x1800cfde4  mov     r8d, ebx; dwBytes
0x1800cfde7  mov     edx, ebp; dwFlags
0x1800cfde9  mov     rcx, rax; hHeap
0x1800cfdec  call    cs:__imp_HeapAlloc
0x1800cfdf2  mov     rsi, rax
0x1800cfdf5  test    rax, rax
0x1800cfdf8  jz      loc_1800CFEA0
0x1800cfdfe  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x1800cfe03  lea     rax, [rsp+58h+TokenInformationLength]
0x1800cfe08  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x1800cfe0d  mov     r8, rsi; TokenInformation
0x1800cfe10  mov     edx, edi; TokenInformationClass
0x1800cfe12  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1800cfe17  call    cs:__imp_GetTokenInformation
0x1800cfe1d  test    eax, eax
0x1800cfe1f  jnz     short loc_1800CFE3D
0x1800cfe21  call    cs:__imp_GetLastError
0x1800cfe27  mov     ebx, eax
0x1800cfe29  test    eax, eax
0x1800cfe2b  jz      short loc_1800CFE75
0x1800cfe2d  jle     short loc_1800CFE35
0x1800cfe2f  movzx   ebx, ax
0x1800cfe32  or      ebx, r12d
0x1800cfe35  test    ebx, ebx
0x1800cfe37  js      loc_1800CFECD
0x1800cfe3d  mov     rcx, [rsi]; pSid
0x1800cfe40  call    cs:__imp_GetLengthSid
0x1800cfe46  mov     edi, eax
0x1800cfe48  call    cs:__imp_GetProcessHeap
0x1800cfe4e  mov     r8d, edi; dwBytes
0x1800cfe51  mov     edx, ebp; dwFlags
0x1800cfe53  mov     rcx, rax; hHeap
0x1800cfe56  call    cs:__imp_HeapAlloc
0x1800cfe5c  mov     r8, [rsi]; pSourceSid
0x1800cfe5f  mov     ecx, edi; nDestinationSidLength
0x1800cfe61  mov     rdx, rax; pDestinationSid
0x1800cfe64  mov     rbp, rax
0x1800cfe67  call    cs:__imp_CopySid
0x1800cfe6d  test    eax, eax
0x1800cfe6f  jz      short loc_1800CFE7C
0x1800cfe71  xor     ebx, ebx
0x1800cfe73  jmp     short loc_1800CFE94
0x1800cfe75  mov     ebx, 80004005h
0x1800cfe7a  jmp     short loc_1800CFECD
0x1800cfe7c  call    cs:__imp_GetLastError
0x1800cfe82  mov     ebx, eax
0x1800cfe84  test    eax, eax
0x1800cfe86  jz      short loc_1800CFE99
0x1800cfe88  jle     short loc_1800CFE90
0x1800cfe8a  movzx   ebx, ax
0x1800cfe8d  or      ebx, r12d
0x1800cfe90  test    ebx, ebx
0x1800cfe92  js      short loc_1800CFEAF
0x1800cfe94  mov     [r14], rbp
0x1800cfe97  jmp     short loc_1800CFECD
0x1800cfe99  mov     ebx, 80004005h
0x1800cfe9e  jmp     short loc_1800CFEAF
0x1800cfea0  mov     ebx, 8007000Eh
0x1800cfea5  jmp     short loc_1800CFEE8
0x1800cfea7  test    ebx, ebx
0x1800cfea9  jns     short loc_1800CFEE8
0x1800cfeab  xor     esi, esi
0x1800cfead  xor     ebp, ebp
0x1800cfeaf  test    rbp, rbp
0x1800cfeb2  jz      short loc_1800CFEC8
0x1800cfeb4  call    cs:__imp_GetProcessHeap
0x1800cfeba  mov     r8, rbp; lpMem
0x1800cfebd  xor     edx, edx; dwFlags
0x1800cfebf  mov     rcx, rax; hHeap
0x1800cfec2  call    cs:__imp_HeapFree
0x1800cfec8  test    rsi, rsi
0x1800cfecb  jz      short loc_1800CFEE8
0x1800cfecd  call    cs:__imp_GetProcessHeap
0x1800cfed3  mov     r8, rsi; lpMem
0x1800cfed6  xor     edx, edx; dwFlags
0x1800cfed8  mov     rcx, rax; hHeap
0x1800cfedb  call    cs:__imp_HeapFree
0x1800cfee1  jmp     short loc_1800CFEE8
0x1800cfee3  mov     ebx, 80004005h
0x1800cfee8  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x1800cfeed  lea     rdx, [rcx-1]
0x1800cfef1  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800cfef5  ja      short loc_1800CFEFD
0x1800cfef7  call    cs:__imp_CloseHandle
0x1800cfefd  mov     eax, ebx
0x1800cfeff  mov     rbx, [rsp+58h+arg_10]
0x1800cff04  add     rsp, 30h
0x1800cff08  pop     r14
0x1800cff0a  pop     r12
0x1800cff0c  pop     rdi
0x1800cff0d  pop     rsi
0x1800cff0e  pop     rbp
0x1800cff0f  retn
```
