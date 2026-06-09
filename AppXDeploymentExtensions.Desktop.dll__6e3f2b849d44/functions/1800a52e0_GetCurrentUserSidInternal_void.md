# GetCurrentUserSidInternal(void * *)

- ea: `0x1800a52e0`
- end: `0x1800a55d8`
- name: `?GetCurrentUserSidInternal@@YAJPEAPEAX@Z`
- size: `760`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800a508c`

## callees

- `0x180012fc8`
- `0x1800a52e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a5460`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a54fb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a5460`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a54fb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a544c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a54e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a557f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a55a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a544c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a54e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a557f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a55a4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a5593`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a55b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a5593`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a55b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5334`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5347`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a53ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a540b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a541c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a54a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5535`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5334`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5347`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a53ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a540b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a541c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a54a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5535`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800a5320`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800a5320`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800a5387`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800a5387`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a5301`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a5301`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800a539c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800a539c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a556e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a556e`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800a5525`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800a5525`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800a53ec`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800a5498`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800a53ec`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800a5498`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800a54d8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800a54d8`

## string_xrefs

- `0x1800a5373`: `onecore\admin\appmodel\common\removeregistrytree.cpp`

## pseudocode

```c
__int64 __fastcall GetCurrentUserSidInternal(void **a1)
{
  PSID *v1; // rsi
  void *v3; // rdi
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  signed int v6; // ebx
  __int64 v7; // rdx
  HANDLE CurrentProcess; // rax
  signed int v9; // eax
  signed int v10; // eax
  DWORD v11; // ebx
  HANDLE ProcessHeap; // rax
  signed int v13; // eax
  DWORD LengthSid; // r14d
  HANDLE v15; // rax
  void *v16; // rax
  signed int v17; // eax
  HANDLE v18; // rax
  HANDLE v19; // rax
  int ReturnLength; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  DWORD TokenInformationLength; // [rsp+68h] [rbp+38h] BYREF
  void *TokenHandle; // [rsp+70h] [rbp+40h] BYREF

  v1 = 0;
  TokenHandle = 0;
  v3 = 0;
  TokenInformationLength = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    goto LABEL_44;
  if ( GetLastError() != 1008 )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 < 0 )
    {
      v7 = 32;
LABEL_7:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v7,
        (unsigned int)"onecore\\admin\\appmodel\\common\\removeregistrytree.cpp",
        (const char *)(unsigned int)v6,
        ReturnLength);
      goto LABEL_35;
    }
    goto LABEL_35;
  }
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
LABEL_44:
    if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
    {
      v6 = -2147418113;
      v7 = 37;
      goto LABEL_7;
    }
    if ( GetLastError() == 122 )
    {
      v11 = TokenInformationLength;
      ProcessHeap = GetProcessHeap();
      v1 = (PSID *)HeapAlloc(ProcessHeap, 0, v11);
      if ( !v1 )
      {
        v6 = -2147024882;
        v7 = 40;
        goto LABEL_7;
      }
      if ( GetTokenInformation(TokenHandle, TokenUser, v1, TokenInformationLength, &TokenInformationLength) )
      {
        LengthSid = GetLengthSid(*v1);
        v15 = GetProcessHeap();
        v16 = HeapAlloc(v15, 0, LengthSid);
        v3 = v16;
        if ( !v16 )
        {
          v6 = -2147024882;
          v7 = 47;
          goto LABEL_7;
        }
        if ( CopySid(LengthSid, v16, *v1) )
        {
          v6 = 0;
          *a1 = v3;
          v3 = 0;
        }
        else
        {
          v17 = GetLastError();
          v6 = v17;
          if ( v17 > 0 )
            v6 = (unsigned __int16)v17 | 0x80070000;
          if ( v6 < 0 )
          {
            v7 = 48;
            goto LABEL_7;
          }
        }
      }
      else
      {
        v13 = GetLastError();
        v6 = v13;
        if ( v13 > 0 )
          v6 = (unsigned __int16)v13 | 0x80070000;
        if ( v6 < 0 )
        {
          v7 = 43;
          goto LABEL_7;
        }
      }
    }
    else
    {
      v10 = GetLastError();
      v6 = v10;
      if ( v10 > 0 )
        v6 = (unsigned __int16)v10 | 0x80070000;
      if ( v6 < 0 )
      {
        v7 = 38;
        goto LABEL_7;
      }
    }
    goto LABEL_35;
  }
  v9 = GetLastError();
  v6 = v9;
  if ( v9 > 0 )
    v6 = (unsigned __int16)v9 | 0x80070000;
  if ( v6 < 0 )
  {
    v7 = 35;
    goto LABEL_7;
  }
LABEL_35:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v1 )
  {
    v18 = GetProcessHeap();
    HeapFree(v18, 0, v1);
  }
  if ( v3 )
  {
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v3);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800a52e0  mov     [rsp-28h+arg_0], rbx
0x1800a52e5  push    rbp
0x1800a52e6  push    rsi
0x1800a52e7  push    rdi
0x1800a52e8  push    r14
0x1800a52ea  push    r15
0x1800a52ec  mov     rbp, rsp
0x1800a52ef  sub     rsp, 30h
0x1800a52f3  xor     esi, esi
0x1800a52f5  mov     r15, rcx
0x1800a52f8  mov     [rbp+TokenHandle], rsi
0x1800a52fc  xor     edi, edi
0x1800a52fe  mov     [rbp+TokenInformationLength], esi
0x1800a5301  call    cs:__imp_GetCurrentThread
0x1800a5308  nop     dword ptr [rax+rax+00h]
0x1800a530d  lea     r14d, [rsi+1]
0x1800a5311  mov     rcx, rax; ThreadHandle
0x1800a5314  lea     ebx, [rsi+8]
0x1800a5317  mov     r8d, r14d; OpenAsSelf
0x1800a531a  mov     edx, ebx; DesiredAccess
0x1800a531c  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800a5320  call    cs:__imp_OpenThreadToken
0x1800a5327  nop     dword ptr [rax+rax+00h]
0x1800a532c  test    eax, eax
0x1800a532e  jnz     loc_1800A53D6
0x1800a5334  call    cs:__imp_GetLastError
0x1800a533b  nop     dword ptr [rax+rax+00h]
0x1800a5340  cmp     eax, 3F0h
0x1800a5345  jz      short loc_1800A5387
0x1800a5347  call    cs:__imp_GetLastError
0x1800a534e  nop     dword ptr [rax+rax+00h]
0x1800a5353  mov     ebx, eax
0x1800a5355  test    eax, eax
0x1800a5357  jle     short loc_1800A5362
0x1800a5359  movzx   ebx, ax
0x1800a535c  or      ebx, 80070000h
0x1800a5362  test    ebx, ebx
0x1800a5364  jns     loc_1800A5565
0x1800a536a  mov     edx, 20h ; ' '; void *
0x1800a536f  mov     rcx, [rbp+28h]; this
0x1800a5373  lea     r8, aOnecoreAdminAp_112; "onecore\\admin\\appmodel\\common\\remov"...
0x1800a537a  mov     r9d, ebx; char *
0x1800a537d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a5382  jmp     loc_1800A5565
0x1800a5387  call    cs:__imp_GetCurrentProcess
0x1800a538e  nop     dword ptr [rax+rax+00h]
0x1800a5393  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800a5397  mov     edx, ebx; DesiredAccess
0x1800a5399  mov     rcx, rax; ProcessHandle
0x1800a539c  call    cs:__imp_OpenProcessToken
0x1800a53a3  nop     dword ptr [rax+rax+00h]
0x1800a53a8  test    eax, eax
0x1800a53aa  jnz     short loc_1800A53D6
0x1800a53ac  call    cs:__imp_GetLastError
0x1800a53b3  nop     dword ptr [rax+rax+00h]
0x1800a53b8  mov     ebx, eax
0x1800a53ba  test    eax, eax
0x1800a53bc  jle     short loc_1800A53C7
0x1800a53be  movzx   ebx, ax
0x1800a53c1  or      ebx, 80070000h
0x1800a53c7  test    ebx, ebx
0x1800a53c9  jns     loc_1800A5565
0x1800a53cf  mov     edx, 23h ; '#'
0x1800a53d4  jmp     short loc_1800A536F
0x1800a53d6  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800a53da  lea     rax, [rbp+TokenInformationLength]
0x1800a53de  xor     r9d, r9d; TokenInformationLength
0x1800a53e1  mov     qword ptr [rsp+30h+ReturnLength], rax; ReturnLength
0x1800a53e6  xor     r8d, r8d; TokenInformation
0x1800a53e9  mov     edx, r14d; TokenInformationClass
0x1800a53ec  call    cs:__imp_GetTokenInformation
0x1800a53f3  nop     dword ptr [rax+rax+00h]
0x1800a53f8  test    eax, eax
0x1800a53fa  jz      short loc_1800A540B
0x1800a53fc  mov     ebx, 8000FFFFh
0x1800a5401  mov     edx, 25h ; '%'
0x1800a5406  jmp     loc_1800A536F
0x1800a540b  call    cs:__imp_GetLastError
0x1800a5412  nop     dword ptr [rax+rax+00h]
0x1800a5417  cmp     eax, 7Ah ; 'z'
0x1800a541a  jz      short loc_1800A5449
0x1800a541c  call    cs:__imp_GetLastError
0x1800a5423  nop     dword ptr [rax+rax+00h]
0x1800a5428  mov     ebx, eax
0x1800a542a  test    eax, eax
0x1800a542c  jle     short loc_1800A5437
0x1800a542e  movzx   ebx, ax
0x1800a5431  or      ebx, 80070000h
0x1800a5437  test    ebx, ebx
0x1800a5439  jns     loc_1800A5565
0x1800a543f  mov     edx, 26h ; '&'
0x1800a5444  jmp     loc_1800A536F
0x1800a5449  mov     ebx, [rbp+TokenInformationLength]
0x1800a544c  call    cs:__imp_GetProcessHeap
0x1800a5453  nop     dword ptr [rax+rax+00h]
0x1800a5458  mov     r8d, ebx; dwBytes
0x1800a545b  xor     edx, edx; dwFlags
0x1800a545d  mov     rcx, rax; hHeap
0x1800a5460  call    cs:__imp_HeapAlloc
0x1800a5467  nop     dword ptr [rax+rax+00h]
0x1800a546c  mov     rsi, rax
0x1800a546f  test    rax, rax
0x1800a5472  jnz     short loc_1800A5481
0x1800a5474  mov     ebx, 8007000Eh
0x1800a5479  lea     edx, [rax+28h]
0x1800a547c  jmp     loc_1800A536F
0x1800a5481  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800a5485  lea     rax, [rbp+TokenInformationLength]
0x1800a5489  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800a548d  mov     r8, rsi; TokenInformation
0x1800a5490  mov     edx, r14d; TokenInformationClass
0x1800a5493  mov     qword ptr [rsp+30h+ReturnLength], rax; ReturnLength
0x1800a5498  call    cs:__imp_GetTokenInformation
0x1800a549f  nop     dword ptr [rax+rax+00h]
0x1800a54a4  test    eax, eax
0x1800a54a6  jnz     short loc_1800A54D5
0x1800a54a8  call    cs:__imp_GetLastError
0x1800a54af  nop     dword ptr [rax+rax+00h]
0x1800a54b4  mov     ebx, eax
0x1800a54b6  test    eax, eax
0x1800a54b8  jle     short loc_1800A54C3
0x1800a54ba  movzx   ebx, ax
0x1800a54bd  or      ebx, 80070000h
0x1800a54c3  test    ebx, ebx
0x1800a54c5  jns     loc_1800A5565
0x1800a54cb  mov     edx, 2Bh ; '+'
0x1800a54d0  jmp     loc_1800A536F
0x1800a54d5  mov     rcx, [rsi]; pSid
0x1800a54d8  call    cs:__imp_GetLengthSid
0x1800a54df  nop     dword ptr [rax+rax+00h]
0x1800a54e4  mov     r14d, eax
0x1800a54e7  call    cs:__imp_GetProcessHeap
0x1800a54ee  nop     dword ptr [rax+rax+00h]
0x1800a54f3  mov     r8d, r14d; dwBytes
0x1800a54f6  xor     edx, edx; dwFlags
0x1800a54f8  mov     rcx, rax; hHeap
0x1800a54fb  call    cs:__imp_HeapAlloc
0x1800a5502  nop     dword ptr [rax+rax+00h]
0x1800a5507  mov     rdi, rax
0x1800a550a  test    rax, rax
0x1800a550d  jnz     short loc_1800A551C
0x1800a550f  mov     ebx, 8007000Eh
0x1800a5514  lea     edx, [rax+2Fh]
0x1800a5517  jmp     loc_1800A536F
0x1800a551c  mov     r8, [rsi]; pSourceSid
0x1800a551f  mov     rdx, rdi; pDestinationSid
0x1800a5522  mov     ecx, r14d; nDestinationSidLength
0x1800a5525  call    cs:__imp_CopySid
0x1800a552c  nop     dword ptr [rax+rax+00h]
0x1800a5531  test    eax, eax
0x1800a5533  jnz     short loc_1800A555E
0x1800a5535  call    cs:__imp_GetLastError
0x1800a553c  nop     dword ptr [rax+rax+00h]
0x1800a5541  mov     ebx, eax
0x1800a5543  test    eax, eax
0x1800a5545  jle     short loc_1800A5550
0x1800a5547  movzx   ebx, ax
0x1800a554a  or      ebx, 80070000h
0x1800a5550  test    ebx, ebx
0x1800a5552  jns     short loc_1800A5565
0x1800a5554  mov     edx, 30h ; '0'
0x1800a5559  jmp     loc_1800A536F
0x1800a555e  xor     ebx, ebx
0x1800a5560  mov     [r15], rdi
0x1800a5563  xor     edi, edi
0x1800a5565  mov     rcx, [rbp+TokenHandle]; hObject
0x1800a5569  test    rcx, rcx
0x1800a556c  jz      short loc_1800A557A
0x1800a556e  call    cs:__imp_CloseHandle
0x1800a5575  nop     dword ptr [rax+rax+00h]
0x1800a557a  test    rsi, rsi
0x1800a557d  jz      short loc_1800A559F
0x1800a557f  call    cs:__imp_GetProcessHeap
0x1800a5586  nop     dword ptr [rax+rax+00h]
0x1800a558b  mov     r8, rsi; lpMem
0x1800a558e  xor     edx, edx; dwFlags
0x1800a5590  mov     rcx, rax; hHeap
0x1800a5593  call    cs:__imp_HeapFree
0x1800a559a  nop     dword ptr [rax+rax+00h]
0x1800a559f  test    rdi, rdi
0x1800a55a2  jz      short loc_1800A55C4
0x1800a55a4  call    cs:__imp_GetProcessHeap
0x1800a55ab  nop     dword ptr [rax+rax+00h]
0x1800a55b0  mov     r8, rdi; lpMem
0x1800a55b3  xor     edx, edx; dwFlags
0x1800a55b5  mov     rcx, rax; hHeap
0x1800a55b8  call    cs:__imp_HeapFree
0x1800a55bf  nop     dword ptr [rax+rax+00h]
0x1800a55c4  mov     eax, ebx
0x1800a55c6  mov     rbx, [rsp+30h+arg_0]
0x1800a55cb  add     rsp, 30h
0x1800a55cf  pop     r15
0x1800a55d1  pop     r14
0x1800a55d3  pop     rdi
0x1800a55d4  pop     rsi
0x1800a55d5  pop     rbp
0x1800a55d6  retn
```
