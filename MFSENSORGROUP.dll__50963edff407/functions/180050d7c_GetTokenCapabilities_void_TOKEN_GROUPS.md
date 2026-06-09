# GetTokenCapabilities(void *,_TOKEN_GROUPS * *)

- ea: `0x180050d7c`
- end: `0x180051010`
- name: `?GetTokenCapabilities@@YAJPEAXPEAPEAU_TOKEN_GROUPS@@@Z`
- size: `660`
- prototype: `__int64 __fastcall(void *, struct _TOKEN_GROUPS **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180056220`

## callees

- `0x180005fa0`
- `0x180044b1c`
- `0x180044b28`
- `0x180050d7c`
- `0x180051a1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050e10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050e90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050e9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050f31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050e10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050e90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050e9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050f31`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180050e06`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180050e06`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180050df6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180050df6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180050ff7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180050ff7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050fdf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050fdf`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180050fa1`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180050fa1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180050e54`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180050e86`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180050f27`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180050e54`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180050e86`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180050f27`

## pseudocode

```c
__int64 __fastcall GetTokenCapabilities(void *a1, struct _TOKEN_GROUPS **a2)
{
  signed int v3; // ebx
  __int64 v4; // rdx
  char v5; // r15
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  signed int v8; // eax
  __int64 v9; // rdx
  struct _TOKEN_GROUPS *v10; // rdi
  signed int v11; // eax
  DWORD i; // esi
  void *TokenHandle; // [rsp+60h] [rbp+30h] BYREF
  DWORD TokenInformationLength; // [rsp+68h] [rbp+38h] BYREF
  LPWSTR TokenInformation; // [rsp+70h] [rbp+40h] BYREF

  TokenHandle = a1;
  TokenInformationLength = 0;
  if ( a2 )
  {
    v3 = 0;
    v5 = 0;
    *a2 = 0;
    if ( !a1 )
    {
      LODWORD(TokenInformation) = 0;
      CurrentProcess = GetCurrentProcess();
      if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
        if ( v3 < 0 )
        {
          if ( !g_wppLevels )
            return (unsigned int)v3;
          v4 = 219;
          goto LABEL_4;
        }
      }
      if ( !GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &TokenInformationLength)
        || (v5 = 1, !(_DWORD)TokenInformation) )
      {
LABEL_40:
        CloseHandle(TokenHandle);
        return (unsigned int)v3;
      }
      a1 = TokenHandle;
    }
    if ( !GetTokenInformation(a1, TokenCapabilities, 0, 0, &TokenInformationLength) && GetLastError() != 122 )
    {
      v8 = GetLastError();
      v3 = v8;
      if ( v8 > 0 )
        v3 = (unsigned __int16)v8 | 0x80070000;
      if ( v3 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_39;
        v9 = 220;
        goto LABEL_22;
      }
    }
    v10 = (struct _TOKEN_GROUPS *)operator new[](TokenInformationLength);
    if ( v10 )
    {
      if ( GetTokenInformation(TokenHandle, TokenCapabilities, v10, TokenInformationLength, &TokenInformationLength) )
        goto LABEL_44;
      v11 = GetLastError();
      v3 = v11;
      if ( v11 > 0 )
        v3 = (unsigned __int16)v11 | 0x80070000;
      if ( v3 >= 0 )
      {
LABEL_44:
        if ( (unsigned __int8)byte_18008D62D >= 0x10u )
        {
          for ( i = 0; i < v10->GroupCount; ++i )
          {
            TokenInformation = 0;
            ConvertSidToStringSidW(v10->Groups[i].Sid, &TokenInformation);
            if ( (unsigned __int8)byte_18008D62D >= 8u )
              WPP_SF_dS(
                *((_QWORD *)WPP_GLOBAL_Control + 27),
                223,
                (unsigned int)&WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids,
                i,
                (__int64)TokenInformation);
            LocalFree(TokenInformation);
          }
        }
        *a2 = v10;
      }
      else
      {
        if ( g_wppLevels )
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 222, &WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids, 0, v3);
        operator delete(v10);
      }
    }
    else
    {
      v3 = -2147024882;
      if ( g_wppLevels )
      {
        v9 = 221;
LABEL_22:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids, 0, v3);
      }
    }
LABEL_39:
    if ( !v5 )
      return (unsigned int)v3;
    goto LABEL_40;
  }
  v3 = -2147467261;
  if ( g_wppLevels )
  {
    v4 = 218;
LABEL_4:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v4, &WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids, 0, v3);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180050d7c  mov     [rsp-28h+arg_18], rbx
0x180050d81  mov     [rsp-28h+TokenHandle], rcx
0x180050d86  push    rbp
0x180050d87  push    rsi
0x180050d88  push    rdi
0x180050d89  push    r14
0x180050d8b  push    r15
0x180050d8d  mov     rbp, rsp
0x180050d90  sub     rsp, 30h
0x180050d94  mov     [rbp+TokenInformationLength], 0
0x180050d9b  mov     r14, rdx
0x180050d9e  test    rdx, rdx
0x180050da1  jnz     short loc_180050DDD
0x180050da3  mov     ebx, 80004003h
0x180050da8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180050daf  jb      loc_180050FFD
0x180050db5  mov     edx, 0DAh
0x180050dba  mov     rcx, cs:WPP_GLOBAL_Control
0x180050dc1  lea     r8, WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids
0x180050dc8  xor     r9d, r9d
0x180050dcb  mov     dword ptr [rsp+30h+ReturnLength], ebx
0x180050dcf  mov     rcx, [rcx+10h]
0x180050dd3  call    WPP_SF_qD
0x180050dd8  jmp     loc_180050FFD
0x180050ddd  xor     ebx, ebx
0x180050ddf  xor     r15b, r15b
0x180050de2  mov     [rdx], rbx
0x180050de5  mov     esi, 80070000h
0x180050dea  test    rcx, rcx
0x180050ded  jnz     loc_180050E73
0x180050df3  mov     dword ptr [rbp+TokenInformation], ebx
0x180050df6  call    cs:__imp_GetCurrentProcess
0x180050dfc  mov     rcx, rax; ProcessHandle
0x180050dff  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180050e03  lea     edx, [rbx+8]; DesiredAccess
0x180050e06  call    cs:__imp_OpenProcessToken
0x180050e0c  test    eax, eax
0x180050e0e  jnz     short loc_180050E39
0x180050e10  call    cs:__imp_GetLastError
0x180050e16  mov     ebx, eax
0x180050e18  test    eax, eax
0x180050e1a  jle     short loc_180050E21
0x180050e1c  movzx   ebx, ax
0x180050e1f  or      ebx, esi
0x180050e21  test    ebx, ebx
0x180050e23  jns     short loc_180050E39
0x180050e25  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180050e2c  jb      loc_180050FFD
0x180050e32  mov     edx, 0DBh
0x180050e37  jmp     short loc_180050DBA
0x180050e39  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180050e3d  lea     rax, [rbp+TokenInformationLength]
0x180050e41  mov     r9d, 4; TokenInformationLength
0x180050e47  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180050e4c  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180050e50  lea     edx, [r9+19h]; TokenInformationClass
0x180050e54  call    cs:__imp_GetTokenInformation
0x180050e5a  test    eax, eax
0x180050e5c  jz      loc_180050FF3
0x180050e62  cmp     dword ptr [rbp+TokenInformation], 0
0x180050e66  mov     r15b, 1
0x180050e69  jz      loc_180050FF3
0x180050e6f  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180050e73  xor     r9d, r9d; TokenInformationLength
0x180050e76  lea     rax, [rbp+TokenInformationLength]
0x180050e7a  xor     r8d, r8d; TokenInformation
0x180050e7d  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180050e82  lea     edx, [r9+1Eh]; TokenInformationClass
0x180050e86  call    cs:__imp_GetTokenInformation
0x180050e8c  test    eax, eax
0x180050e8e  jnz     short loc_180050EE5
0x180050e90  call    cs:__imp_GetLastError
0x180050e96  cmp     eax, 7Ah ; 'z'
0x180050e99  jz      short loc_180050EE5
0x180050e9b  call    cs:__imp_GetLastError
0x180050ea1  mov     ebx, eax
0x180050ea3  test    eax, eax
0x180050ea5  jle     short loc_180050EAC
0x180050ea7  movzx   ebx, ax
0x180050eaa  or      ebx, esi
0x180050eac  test    ebx, ebx
0x180050eae  jns     short loc_180050EE5
0x180050eb0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180050eb7  jb      loc_180050FEE
0x180050ebd  mov     edx, 0DCh
0x180050ec2  mov     rcx, cs:WPP_GLOBAL_Control
0x180050ec9  lea     r8, WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids
0x180050ed0  xor     r9d, r9d
0x180050ed3  mov     dword ptr [rsp+30h+ReturnLength], ebx
0x180050ed7  mov     rcx, [rcx+10h]
0x180050edb  call    WPP_SF_qD
0x180050ee0  jmp     loc_180050FEE
0x180050ee5  mov     ecx, [rbp+TokenInformationLength]; unsigned __int64
0x180050ee8  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180050eed  mov     rdi, rax
0x180050ef0  test    rax, rax
0x180050ef3  jnz     short loc_180050F0E
0x180050ef5  mov     ebx, 8007000Eh
0x180050efa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180050f01  jb      loc_180050FEE
0x180050f07  mov     edx, 0DDh
0x180050f0c  jmp     short loc_180050EC2
0x180050f0e  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180050f12  lea     rax, [rbp+TokenInformationLength]
0x180050f16  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180050f1a  mov     r8, rdi; TokenInformation
0x180050f1d  mov     edx, 1Eh; TokenInformationClass
0x180050f22  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180050f27  call    cs:__imp_GetTokenInformation
0x180050f2d  test    eax, eax
0x180050f2f  jnz     short loc_180050F7C
0x180050f31  call    cs:__imp_GetLastError
0x180050f37  mov     ebx, eax
0x180050f39  test    eax, eax
0x180050f3b  jle     short loc_180050F42
0x180050f3d  movzx   ebx, ax
0x180050f40  or      ebx, esi
0x180050f42  test    ebx, ebx
0x180050f44  jns     short loc_180050F7C
0x180050f46  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180050f4d  jb      short loc_180050F72
0x180050f4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180050f56  lea     r8, WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids
0x180050f5d  mov     edx, 0DEh
0x180050f62  mov     dword ptr [rsp+30h+ReturnLength], ebx
0x180050f66  xor     r9d, r9d
0x180050f69  mov     rcx, [rcx+10h]
0x180050f6d  call    WPP_SF_qD
0x180050f72  mov     rcx, rdi; Block
0x180050f75  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180050f7a  jmp     short loc_180050FEE
0x180050f7c  cmp     cs:byte_18008D62D, 10h
0x180050f83  jb      short loc_180050FEB
0x180050f85  xor     esi, esi
0x180050f87  cmp     [rdi], esi
0x180050f89  jbe     short loc_180050FEB
0x180050f8b  mov     ecx, esi
0x180050f8d  lea     rdx, [rbp+TokenInformation]; StringSid
0x180050f91  add     rcx, rcx
0x180050f94  mov     [rbp+TokenInformation], 0
0x180050f9c  mov     rcx, [rdi+rcx*8+8]; Sid
0x180050fa1  call    cs:__imp_ConvertSidToStringSidW
0x180050fa7  cmp     cs:byte_18008D62D, 8
0x180050fae  jb      short loc_180050FDB
0x180050fb0  mov     rcx, cs:WPP_GLOBAL_Control
0x180050fb7  lea     r8, WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids
0x180050fbe  mov     rax, [rbp+TokenInformation]
0x180050fc2  mov     edx, 0DFh
0x180050fc7  mov     r9d, esi
0x180050fca  mov     [rsp+30h+ReturnLength], rax
0x180050fcf  mov     rcx, [rcx+0D8h]
0x180050fd6  call    WPP_SF_dS
0x180050fdb  mov     rcx, [rbp+TokenInformation]; hMem
0x180050fdf  call    cs:__imp_LocalFree
0x180050fe5  inc     esi
0x180050fe7  cmp     esi, [rdi]
0x180050fe9  jb      short loc_180050F8B
0x180050feb  mov     [r14], rdi
0x180050fee  test    r15b, r15b
0x180050ff1  jz      short loc_180050FFD
0x180050ff3  mov     rcx, [rbp+TokenHandle]; hObject
0x180050ff7  call    cs:__imp_CloseHandle
0x180050ffd  mov     eax, ebx
0x180050fff  mov     rbx, [rsp+30h+arg_18]
0x180051004  add     rsp, 30h
0x180051008  pop     r15
0x18005100a  pop     r14
0x18005100c  pop     rdi
0x18005100d  pop     rsi
0x18005100e  pop     rbp
0x18005100f  retn
```
