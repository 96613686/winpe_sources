# BdeSvcpGetClientIntegrityLevel(ulong *)

- ea: `0x180049a54`
- end: `0x180049e69`
- name: `?BdeSvcpGetClientIntegrityLevel@@YAJPEAK@Z`
- size: `1045`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004c830`
- `0x18004d6a0`

## callees

- `0x180009f30`
- `0x180009f60`
- `0x180034070`
- `0x180049a54`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049deb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049deb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180049ca1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180049ca1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049c8d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049dd7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049c8d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049dd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049ac8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049b45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049c1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049d2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049e31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049ac8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049b45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049c1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049d2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049e31`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180049b35`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180049b35`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180049b1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180049b1b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049dbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049dbd`
- `RPCRT4!RpcImpersonateClient` at `0x180049a84`
- `RPCRT4!RpcImpersonateClient` at `0x180049a84`
- `RPCRT4!RpcRevertToSelf` at `0x180049dfb`
- `RPCRT4!RpcRevertToSelf` at `0x180049dfb`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180049d8f`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180049d8f`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180049da3`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180049da3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180049bc3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180049d1d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180049bc3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180049d1d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall BdeSvcpGetClientIntegrityLevel(unsigned int *a1)
{
  PSID *v2; // rsi
  unsigned int v3; // eax
  int v4; // ebp
  signed int LastError; // eax
  signed int v6; // ebx
  PVOID *v7; // rcx
  __int64 v8; // rdx
  HANDLE CurrentThread; // rax
  DWORD v10; // eax
  DWORD v11; // eax
  DWORD v12; // ebx
  HANDLE ProcessHeap; // rax
  DWORD v14; // eax
  PUCHAR SidSubAuthorityCount; // rax
  HANDLE v16; // rax
  unsigned int v17; // eax
  signed int v18; // eax
  void *TokenHandle; // [rsp+30h] [rbp-58h] BYREF
  DWORD TokenInformationLength; // [rsp+38h] [rbp-50h] BYREF

  TokenInformationLength = 0;
  v2 = 0;
  TokenHandle = 0;
  v3 = RpcImpersonateClient(0);
  if ( v3 )
  {
    v4 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 127, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v3);
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      v8 = 128;
LABEL_10:
      WPP_SF_d(v7[2], v8, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, (unsigned int)v6);
    }
  }
  else
  {
    v4 = 1;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
    {
      if ( GetTokenInformation(TokenHandle, TokenIntegrityLevel, 0, 0, &TokenInformationLength) )
      {
        v7 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 131, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids);
          v7 = (PVOID *)WPP_GLOBAL_Control;
        }
        v6 = -2147467259;
        if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x40) != 0 )
        {
          v8 = 132;
          goto LABEL_10;
        }
      }
      else
      {
        v11 = GetLastError();
        v6 = v11;
        if ( v11 == 122 )
        {
          v12 = TokenInformationLength;
          ProcessHeap = GetProcessHeap();
          v2 = (PSID *)HeapAlloc(ProcessHeap, 0, v12);
          if ( v2 )
          {
            if ( GetTokenInformation(
                   TokenHandle,
                   TokenIntegrityLevel,
                   v2,
                   TokenInformationLength,
                   &TokenInformationLength) )
            {
              v6 = 0;
              SidSubAuthorityCount = GetSidSubAuthorityCount(*v2);
              *a1 = *GetSidSubAuthority(*v2, (unsigned int)*SidSubAuthorityCount - 1);
            }
            else
            {
              v14 = GetLastError();
              v6 = v14;
              v7 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  137,
                  &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids,
                  v14);
                v7 = (PVOID *)WPP_GLOBAL_Control;
              }
              if ( v6 > 0 )
                v6 = (unsigned __int16)v6 | 0x80070000;
              if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x40) != 0 )
              {
                v8 = 138;
                goto LABEL_10;
              }
            }
          }
          else
          {
            v7 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 135, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids);
              v7 = (PVOID *)WPP_GLOBAL_Control;
            }
            v6 = -2147024882;
            if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x40) != 0 )
            {
              v8 = 136;
              goto LABEL_10;
            }
          }
        }
        else
        {
          v7 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 133, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v11);
            v7 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v6 > 0 )
            v6 = (unsigned __int16)v6 | 0x80070000;
          if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x40) != 0 )
          {
            v8 = 134;
            goto LABEL_10;
          }
        }
      }
    }
    else
    {
      v10 = GetLastError();
      v6 = v10;
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 129, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v10);
        v7 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v6 > 0 )
        v6 = (unsigned __int16)v6 | 0x80070000;
      if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x40) != 0 )
      {
        v8 = 130;
        goto LABEL_10;
      }
    }
  }
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  if ( v2 )
  {
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v2);
  }
  if ( v4 )
  {
    v17 = RpcRevertToSelf();
    if ( v17 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 139, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v17);
      v18 = GetLastError();
      v6 = v18;
      if ( v18 > 0 )
        return (unsigned __int16)v18 | 0x80070000;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180049a54  push    rbx
0x180049a56  push    rbp
0x180049a57  push    rsi
0x180049a58  push    rdi
0x180049a59  push    r12
0x180049a5b  push    r15
0x180049a5d  sub     rsp, 58h
0x180049a61  mov     rax, cs:__security_cookie
0x180049a68  xor     rax, rsp
0x180049a6b  mov     [rsp+88h+var_48], rax
0x180049a70  mov     rdi, rcx
0x180049a73  mov     [rsp+88h+TokenInformationLength], 0
0x180049a7b  xor     esi, esi
0x180049a7d  xor     ecx, ecx; BindingHandle
0x180049a7f  mov     [rsp+88h+TokenHandle], rsi
0x180049a84  call    cs:__imp_RpcImpersonateClient
0x180049a8b  nop     dword ptr [rax+rax+00h]
0x180049a90  lea     r15, WPP_GLOBAL_Control
0x180049a97  lea     r12, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x180049a9e  test    eax, eax
0x180049aa0  jz      short loc_180049B16
0x180049aa2  xor     ebp, ebp
0x180049aa4  mov     rcx, cs:WPP_GLOBAL_Control
0x180049aab  cmp     rcx, r15
0x180049aae  jz      short loc_180049AC8
0x180049ab0  test    byte ptr [rcx+1Ch], 2
0x180049ab4  jz      short loc_180049AC8
0x180049ab6  mov     rcx, [rcx+10h]
0x180049aba  lea     edx, [rsi+7Fh]
0x180049abd  mov     r9d, eax
0x180049ac0  mov     r8, r12
0x180049ac3  call    WPP_SF_d
0x180049ac8  call    cs:__imp_GetLastError
0x180049acf  nop     dword ptr [rax+rax+00h]
0x180049ad4  mov     ebx, eax
0x180049ad6  test    eax, eax
0x180049ad8  jle     short loc_180049AE3
0x180049ada  movzx   ebx, ax
0x180049add  or      ebx, 80070000h
0x180049ae3  mov     rcx, cs:WPP_GLOBAL_Control
0x180049aea  cmp     rcx, r15
0x180049aed  jz      loc_180049DB3
0x180049af3  test    byte ptr [rcx+1Ch], 40h
0x180049af7  jz      loc_180049DB3
0x180049afd  mov     edx, 80h
0x180049b02  mov     rcx, [rcx+10h]
0x180049b06  mov     r9d, ebx
0x180049b09  mov     r8, r12
0x180049b0c  call    WPP_SF_d
0x180049b11  jmp     loc_180049DB3
0x180049b16  mov     ebp, 1
0x180049b1b  call    cs:__imp_GetCurrentThread
0x180049b22  nop     dword ptr [rax+rax+00h]
0x180049b27  lea     r9, [rsp+88h+TokenHandle]; TokenHandle
0x180049b2c  xor     r8d, r8d; OpenAsSelf
0x180049b2f  mov     rcx, rax; ThreadHandle
0x180049b32  lea     edx, [rbp+7]; DesiredAccess
0x180049b35  call    cs:__imp_OpenThreadToken
0x180049b3c  nop     dword ptr [rax+rax+00h]
0x180049b41  test    eax, eax
0x180049b43  jnz     short loc_180049BAA
0x180049b45  call    cs:__imp_GetLastError
0x180049b4c  nop     dword ptr [rax+rax+00h]
0x180049b51  mov     ebx, eax
0x180049b53  mov     rcx, cs:WPP_GLOBAL_Control
0x180049b5a  cmp     rcx, r15
0x180049b5d  jz      short loc_180049B80
0x180049b5f  test    byte ptr [rcx+1Ch], 2
0x180049b63  jz      short loc_180049B80
0x180049b65  mov     rcx, [rcx+10h]
0x180049b69  mov     edx, 81h
0x180049b6e  mov     r9d, eax
0x180049b71  mov     r8, r12
0x180049b74  call    WPP_SF_d
0x180049b79  mov     rcx, cs:WPP_GLOBAL_Control
0x180049b80  test    ebx, ebx
0x180049b82  jle     short loc_180049B8D
0x180049b84  movzx   ebx, bx
0x180049b87  or      ebx, 80070000h
0x180049b8d  cmp     rcx, r15
0x180049b90  jz      loc_180049DB3
0x180049b96  test    byte ptr [rcx+1Ch], 40h
0x180049b9a  jz      loc_180049DB3
0x180049ba0  mov     edx, 82h
0x180049ba5  jmp     loc_180049B02
0x180049baa  mov     rcx, [rsp+88h+TokenHandle]; TokenHandle
0x180049baf  lea     rax, [rsp+88h+TokenInformationLength]
0x180049bb4  xor     r9d, r9d; TokenInformationLength
0x180049bb7  mov     [rsp+88h+ReturnLength], rax; ReturnLength
0x180049bbc  xor     r8d, r8d; TokenInformation
0x180049bbf  lea     edx, [r9+19h]; TokenInformationClass
0x180049bc3  call    cs:__imp_GetTokenInformation
0x180049bca  nop     dword ptr [rax+rax+00h]
0x180049bcf  cmp     eax, ebp
0x180049bd1  jnz     short loc_180049C1F
0x180049bd3  mov     rcx, cs:WPP_GLOBAL_Control
0x180049bda  cmp     rcx, r15
0x180049bdd  jz      short loc_180049BFD
0x180049bdf  test    byte ptr [rcx+1Ch], 2
0x180049be3  jz      short loc_180049BFD
0x180049be5  mov     rcx, [rcx+10h]
0x180049be9  mov     edx, 83h
0x180049bee  mov     r8, r12
0x180049bf1  call    WPP_SF_
0x180049bf6  mov     rcx, cs:WPP_GLOBAL_Control
0x180049bfd  mov     ebx, 80004005h
0x180049c02  cmp     rcx, r15
0x180049c05  jz      loc_180049DB3
0x180049c0b  test    byte ptr [rcx+1Ch], 40h
0x180049c0f  jz      loc_180049DB3
0x180049c15  mov     edx, 84h
0x180049c1a  jmp     loc_180049B02
0x180049c1f  call    cs:__imp_GetLastError
0x180049c26  nop     dword ptr [rax+rax+00h]
0x180049c2b  mov     ebx, eax
0x180049c2d  cmp     eax, 7Ah ; 'z'
0x180049c30  jz      short loc_180049C89
0x180049c32  mov     rcx, cs:WPP_GLOBAL_Control
0x180049c39  cmp     rcx, r15
0x180049c3c  jz      short loc_180049C5F
0x180049c3e  test    byte ptr [rcx+1Ch], 2
0x180049c42  jz      short loc_180049C5F
0x180049c44  mov     rcx, [rcx+10h]
0x180049c48  mov     edx, 85h
0x180049c4d  mov     r9d, eax
0x180049c50  mov     r8, r12
0x180049c53  call    WPP_SF_d
0x180049c58  mov     rcx, cs:WPP_GLOBAL_Control
0x180049c5f  test    ebx, ebx
0x180049c61  jle     short loc_180049C6C
0x180049c63  movzx   ebx, bx
0x180049c66  or      ebx, 80070000h
0x180049c6c  cmp     rcx, r15
0x180049c6f  jz      loc_180049DB3
0x180049c75  test    byte ptr [rcx+1Ch], 40h
0x180049c79  jz      loc_180049DB3
0x180049c7f  mov     edx, 86h
0x180049c84  jmp     loc_180049B02
0x180049c89  mov     ebx, [rsp+88h+TokenInformationLength]
0x180049c8d  call    cs:__imp_GetProcessHeap
0x180049c94  nop     dword ptr [rax+rax+00h]
0x180049c99  mov     r8d, ebx; dwBytes
0x180049c9c  xor     edx, edx; dwFlags
0x180049c9e  mov     rcx, rax; hHeap
0x180049ca1  call    cs:__imp_HeapAlloc
0x180049ca8  nop     dword ptr [rax+rax+00h]
0x180049cad  mov     rsi, rax
0x180049cb0  test    rax, rax
0x180049cb3  jnz     short loc_180049D01
0x180049cb5  mov     rcx, cs:WPP_GLOBAL_Control
0x180049cbc  cmp     rcx, r15
0x180049cbf  jz      short loc_180049CDF
0x180049cc1  test    byte ptr [rcx+1Ch], 2
0x180049cc5  jz      short loc_180049CDF
0x180049cc7  mov     rcx, [rcx+10h]
0x180049ccb  mov     edx, 87h
0x180049cd0  mov     r8, r12
0x180049cd3  call    WPP_SF_
0x180049cd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180049cdf  mov     ebx, 8007000Eh
0x180049ce4  cmp     rcx, r15
0x180049ce7  jz      loc_180049DB3
0x180049ced  test    byte ptr [rcx+1Ch], 40h
0x180049cf1  jz      loc_180049DB3
0x180049cf7  mov     edx, 88h
0x180049cfc  jmp     loc_180049B02
0x180049d01  mov     r9d, [rsp+88h+TokenInformationLength]; TokenInformationLength
0x180049d06  lea     rax, [rsp+88h+TokenInformationLength]
0x180049d0b  mov     rcx, [rsp+88h+TokenHandle]; TokenHandle
0x180049d10  mov     r8, rsi; TokenInformation
0x180049d13  mov     edx, 19h; TokenInformationClass
0x180049d18  mov     [rsp+88h+ReturnLength], rax; ReturnLength
0x180049d1d  call    cs:__imp_GetTokenInformation
0x180049d24  nop     dword ptr [rax+rax+00h]
0x180049d29  test    eax, eax
0x180049d2b  jnz     short loc_180049D8A
0x180049d2d  call    cs:__imp_GetLastError
0x180049d34  nop     dword ptr [rax+rax+00h]
0x180049d39  mov     ebx, eax
0x180049d3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180049d42  cmp     rcx, r15
0x180049d45  jz      short loc_180049D68
0x180049d47  test    byte ptr [rcx+1Ch], 2
0x180049d4b  jz      short loc_180049D68
0x180049d4d  mov     rcx, [rcx+10h]
0x180049d51  mov     edx, 89h
0x180049d56  mov     r9d, eax
0x180049d59  mov     r8, r12
0x180049d5c  call    WPP_SF_d
0x180049d61  mov     rcx, cs:WPP_GLOBAL_Control
0x180049d68  test    ebx, ebx
0x180049d6a  jle     short loc_180049D75
0x180049d6c  movzx   ebx, bx
0x180049d6f  or      ebx, 80070000h
0x180049d75  cmp     rcx, r15
0x180049d78  jz      short loc_180049DB3
0x180049d7a  test    byte ptr [rcx+1Ch], 40h
0x180049d7e  jz      short loc_180049DB3
0x180049d80  mov     edx, 8Ah
0x180049d85  jmp     loc_180049B02
0x180049d8a  mov     rcx, [rsi]; pSid
0x180049d8d  xor     ebx, ebx
0x180049d8f  call    cs:__imp_GetSidSubAuthorityCount
0x180049d96  nop     dword ptr [rax+rax+00h]
0x180049d9b  mov     rcx, [rsi]; pSid
0x180049d9e  movzx   edx, byte ptr [rax]
0x180049da1  sub     edx, ebp; nSubAuthority
0x180049da3  call    cs:__imp_GetSidSubAuthority
0x180049daa  nop     dword ptr [rax+rax+00h]
0x180049daf  mov     ecx, [rax]
0x180049db1  mov     [rdi], ecx
0x180049db3  mov     rcx, [rsp+88h+TokenHandle]; hObject
0x180049db8  test    rcx, rcx
0x180049dbb  jz      short loc_180049DD2
0x180049dbd  call    cs:__imp_CloseHandle
0x180049dc4  nop     dword ptr [rax+rax+00h]
0x180049dc9  mov     [rsp+88h+TokenHandle], 0
0x180049dd2  test    rsi, rsi
0x180049dd5  jz      short loc_180049DF7
0x180049dd7  call    cs:__imp_GetProcessHeap
0x180049dde  nop     dword ptr [rax+rax+00h]
0x180049de3  mov     r8, rsi; lpMem
0x180049de6  xor     edx, edx; dwFlags
0x180049de8  mov     rcx, rax; hHeap
0x180049deb  call    cs:__imp_HeapFree
0x180049df2  nop     dword ptr [rax+rax+00h]
0x180049df7  test    ebp, ebp
0x180049df9  jz      short loc_180049E4C
0x180049dfb  call    cs:__imp_RpcRevertToSelf
0x180049e02  nop     dword ptr [rax+rax+00h]
0x180049e07  test    eax, eax
0x180049e09  jz      short loc_180049E4C
0x180049e0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180049e12  cmp     rcx, r15
0x180049e15  jz      short loc_180049E31
0x180049e17  test    byte ptr [rcx+1Ch], 2
0x180049e1b  jz      short loc_180049E31
0x180049e1d  mov     rcx, [rcx+10h]
0x180049e21  mov     edx, 8Bh
0x180049e26  mov     r9d, eax
0x180049e29  mov     r8, r12
0x180049e2c  call    WPP_SF_d
0x180049e31  call    cs:__imp_GetLastError
0x180049e38  nop     dword ptr [rax+rax+00h]
0x180049e3d  mov     ebx, eax
0x180049e3f  test    eax, eax
0x180049e41  jle     short loc_180049E4C
0x180049e43  movzx   ebx, ax
0x180049e46  or      ebx, 80070000h
0x180049e4c  mov     eax, ebx
0x180049e4e  mov     rcx, [rsp+88h+var_48]
0x180049e53  xor     rcx, rsp; StackCookie
0x180049e56  call    __security_check_cookie
0x180049e5b  add     rsp, 58h
0x180049e5f  pop     r15
0x180049e61  pop     r12
0x180049e63  pop     rdi
0x180049e64  pop     rsi
0x180049e65  pop     rbp
0x180049e66  pop     rbx
0x180049e67  retn
```
