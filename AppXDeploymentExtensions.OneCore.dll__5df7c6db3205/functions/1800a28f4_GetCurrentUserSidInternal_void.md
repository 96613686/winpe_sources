# GetCurrentUserSidInternal(void * *)

- ea: `0x1800a28f4`
- end: `0x1800a2b57`
- name: `?GetCurrentUserSidInternal@@YAJPEAPEAX@Z`
- size: `611`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800dca54`

## callees

- `0x1800a219c`
- `0x1800a28f4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a2a32`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a2aab`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a2a32`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a2aab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a2a24`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a2a9d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a2b17`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a2b30`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a2a24`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a2a9d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a2b17`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a2b30`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a2b25`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a2b3e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a2b25`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a2b3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a293c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2949`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a299c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a29ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a29fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2a6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2ad9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a293c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2949`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a299c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a29ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a29fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2a6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2ad9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800a2983`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800a2983`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800a2992`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800a2992`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800a292e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800a292e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a2915`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a2915`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a2b0c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a2b0c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800a29d6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800a2a64`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800a29d6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800a2a64`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800a2acf`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800a2acf`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800a2a94`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800a2a94`

## string_xrefs

- `0x1800a296f`: `onecore\admin\appmodel\common\removeregistrytree.cpp`

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
0x1800a28f4  mov     [rsp-28h+arg_0], rbx
0x1800a28f9  push    rbp
0x1800a28fa  push    rsi
0x1800a28fb  push    rdi
0x1800a28fc  push    r14
0x1800a28fe  push    r15
0x1800a2900  mov     rbp, rsp
0x1800a2903  sub     rsp, 30h
0x1800a2907  xor     esi, esi
0x1800a2909  mov     r15, rcx
0x1800a290c  mov     [rbp+TokenHandle], rsi
0x1800a2910  xor     edi, edi
0x1800a2912  mov     [rbp+TokenInformationLength], esi
0x1800a2915  call    cs:__imp_GetCurrentThread
0x1800a291b  lea     r14d, [rsi+1]
0x1800a291f  mov     rcx, rax; ThreadHandle
0x1800a2922  lea     ebx, [rsi+8]
0x1800a2925  mov     r8d, r14d; OpenAsSelf
0x1800a2928  mov     edx, ebx; DesiredAccess
0x1800a292a  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800a292e  call    cs:__imp_OpenThreadToken
0x1800a2934  test    eax, eax
0x1800a2936  jnz     loc_1800A29C0
0x1800a293c  call    cs:__imp_GetLastError
0x1800a2942  cmp     eax, 3F0h
0x1800a2947  jz      short loc_1800A2983
0x1800a2949  call    cs:__imp_GetLastError
0x1800a294f  mov     ebx, eax
0x1800a2951  test    eax, eax
0x1800a2953  jle     short loc_1800A295E
0x1800a2955  movzx   ebx, ax
0x1800a2958  or      ebx, 80070000h
0x1800a295e  test    ebx, ebx
0x1800a2960  jns     loc_1800A2B03
0x1800a2966  mov     edx, 20h ; ' '; void *
0x1800a296b  mov     rcx, [rbp+28h]; this
0x1800a296f  lea     r8, aOnecoreAdminAp_126; "onecore\\admin\\appmodel\\common\\remov"...
0x1800a2976  mov     r9d, ebx; char *
0x1800a2979  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a297e  jmp     loc_1800A2B03
0x1800a2983  call    cs:__imp_GetCurrentProcess
0x1800a2989  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800a298d  mov     edx, ebx; DesiredAccess
0x1800a298f  mov     rcx, rax; ProcessHandle
0x1800a2992  call    cs:__imp_OpenProcessToken
0x1800a2998  test    eax, eax
0x1800a299a  jnz     short loc_1800A29C0
0x1800a299c  call    cs:__imp_GetLastError
0x1800a29a2  mov     ebx, eax
0x1800a29a4  test    eax, eax
0x1800a29a6  jle     short loc_1800A29B1
0x1800a29a8  movzx   ebx, ax
0x1800a29ab  or      ebx, 80070000h
0x1800a29b1  test    ebx, ebx
0x1800a29b3  jns     loc_1800A2B03
0x1800a29b9  mov     edx, 23h ; '#'
0x1800a29be  jmp     short loc_1800A296B
0x1800a29c0  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800a29c4  lea     rax, [rbp+TokenInformationLength]
0x1800a29c8  xor     r9d, r9d; TokenInformationLength
0x1800a29cb  mov     qword ptr [rsp+30h+ReturnLength], rax; ReturnLength
0x1800a29d0  xor     r8d, r8d; TokenInformation
0x1800a29d3  mov     edx, r14d; TokenInformationClass
0x1800a29d6  call    cs:__imp_GetTokenInformation
0x1800a29dc  test    eax, eax
0x1800a29de  jz      short loc_1800A29EF
0x1800a29e0  mov     ebx, 8000FFFFh
0x1800a29e5  mov     edx, 25h ; '%'
0x1800a29ea  jmp     loc_1800A296B
0x1800a29ef  call    cs:__imp_GetLastError
0x1800a29f5  cmp     eax, 7Ah ; 'z'
0x1800a29f8  jz      short loc_1800A2A21
0x1800a29fa  call    cs:__imp_GetLastError
0x1800a2a00  mov     ebx, eax
0x1800a2a02  test    eax, eax
0x1800a2a04  jle     short loc_1800A2A0F
0x1800a2a06  movzx   ebx, ax
0x1800a2a09  or      ebx, 80070000h
0x1800a2a0f  test    ebx, ebx
0x1800a2a11  jns     loc_1800A2B03
0x1800a2a17  mov     edx, 26h ; '&'
0x1800a2a1c  jmp     loc_1800A296B
0x1800a2a21  mov     ebx, [rbp+TokenInformationLength]
0x1800a2a24  call    cs:__imp_GetProcessHeap
0x1800a2a2a  mov     r8d, ebx; dwBytes
0x1800a2a2d  xor     edx, edx; dwFlags
0x1800a2a2f  mov     rcx, rax; hHeap
0x1800a2a32  call    cs:__imp_HeapAlloc
0x1800a2a38  mov     rsi, rax
0x1800a2a3b  test    rax, rax
0x1800a2a3e  jnz     short loc_1800A2A4D
0x1800a2a40  mov     ebx, 8007000Eh
0x1800a2a45  lea     edx, [rax+28h]
0x1800a2a48  jmp     loc_1800A296B
0x1800a2a4d  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800a2a51  lea     rax, [rbp+TokenInformationLength]
0x1800a2a55  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800a2a59  mov     r8, rsi; TokenInformation
0x1800a2a5c  mov     edx, r14d; TokenInformationClass
0x1800a2a5f  mov     qword ptr [rsp+30h+ReturnLength], rax; ReturnLength
0x1800a2a64  call    cs:__imp_GetTokenInformation
0x1800a2a6a  test    eax, eax
0x1800a2a6c  jnz     short loc_1800A2A91
0x1800a2a6e  call    cs:__imp_GetLastError
0x1800a2a74  mov     ebx, eax
0x1800a2a76  test    eax, eax
0x1800a2a78  jle     short loc_1800A2A83
0x1800a2a7a  movzx   ebx, ax
0x1800a2a7d  or      ebx, 80070000h
0x1800a2a83  test    ebx, ebx
0x1800a2a85  jns     short loc_1800A2B03
0x1800a2a87  mov     edx, 2Bh ; '+'
0x1800a2a8c  jmp     loc_1800A296B
0x1800a2a91  mov     rcx, [rsi]; pSid
0x1800a2a94  call    cs:__imp_GetLengthSid
0x1800a2a9a  mov     r14d, eax
0x1800a2a9d  call    cs:__imp_GetProcessHeap
0x1800a2aa3  mov     r8d, r14d; dwBytes
0x1800a2aa6  xor     edx, edx; dwFlags
0x1800a2aa8  mov     rcx, rax; hHeap
0x1800a2aab  call    cs:__imp_HeapAlloc
0x1800a2ab1  mov     rdi, rax
0x1800a2ab4  test    rax, rax
0x1800a2ab7  jnz     short loc_1800A2AC6
0x1800a2ab9  mov     ebx, 8007000Eh
0x1800a2abe  lea     edx, [rax+2Fh]
0x1800a2ac1  jmp     loc_1800A296B
0x1800a2ac6  mov     r8, [rsi]; pSourceSid
0x1800a2ac9  mov     rdx, rdi; pDestinationSid
0x1800a2acc  mov     ecx, r14d; nDestinationSidLength
0x1800a2acf  call    cs:__imp_CopySid
0x1800a2ad5  test    eax, eax
0x1800a2ad7  jnz     short loc_1800A2AFC
0x1800a2ad9  call    cs:__imp_GetLastError
0x1800a2adf  mov     ebx, eax
0x1800a2ae1  test    eax, eax
0x1800a2ae3  jle     short loc_1800A2AEE
0x1800a2ae5  movzx   ebx, ax
0x1800a2ae8  or      ebx, 80070000h
0x1800a2aee  test    ebx, ebx
0x1800a2af0  jns     short loc_1800A2B03
0x1800a2af2  mov     edx, 30h ; '0'
0x1800a2af7  jmp     loc_1800A296B
0x1800a2afc  xor     ebx, ebx
0x1800a2afe  mov     [r15], rdi
0x1800a2b01  xor     edi, edi
0x1800a2b03  mov     rcx, [rbp+TokenHandle]; hObject
0x1800a2b07  test    rcx, rcx
0x1800a2b0a  jz      short loc_1800A2B12
0x1800a2b0c  call    cs:__imp_CloseHandle
0x1800a2b12  test    rsi, rsi
0x1800a2b15  jz      short loc_1800A2B2B
0x1800a2b17  call    cs:__imp_GetProcessHeap
0x1800a2b1d  mov     r8, rsi; lpMem
0x1800a2b20  xor     edx, edx; dwFlags
0x1800a2b22  mov     rcx, rax; hHeap
0x1800a2b25  call    cs:__imp_HeapFree
0x1800a2b2b  test    rdi, rdi
0x1800a2b2e  jz      short loc_1800A2B44
0x1800a2b30  call    cs:__imp_GetProcessHeap
0x1800a2b36  mov     r8, rdi; lpMem
0x1800a2b39  xor     edx, edx; dwFlags
0x1800a2b3b  mov     rcx, rax; hHeap
0x1800a2b3e  call    cs:__imp_HeapFree
0x1800a2b44  mov     eax, ebx
0x1800a2b46  mov     rbx, [rsp+30h+arg_0]
0x1800a2b4b  add     rsp, 30h
0x1800a2b4f  pop     r15
0x1800a2b51  pop     r14
0x1800a2b53  pop     rdi
0x1800a2b54  pop     rsi
0x1800a2b55  pop     rbp
0x1800a2b56  retn
```
