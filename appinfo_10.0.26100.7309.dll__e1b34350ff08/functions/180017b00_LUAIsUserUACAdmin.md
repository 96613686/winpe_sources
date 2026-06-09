# LUAIsUserUACAdmin

- ea: `0x180017b00`
- end: `0x180017f14`
- name: `LUAIsUserUACAdmin`
- size: `1044`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800437ec`

## callees

- `0x180017b00`
- `0x18001c04c`
- `0x18001c19e`
- `0x18001c265`
- `0x1800435ac`
- `0x180043690`
- `0x180043a2c`
- `0x1800444e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ec9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ed9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ee7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ec9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ed9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ee7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180017b2a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180017b2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017c5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017e75`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017ea9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017c5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017e75`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017ea9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017deb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017e89`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017deb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017e89`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017d9e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017d9e`
- `ntdll!NtQueryInformationToken` at `0x180017b95`
- `ntdll!NtQueryInformationToken` at `0x180017bdc`
- `ntdll!NtQueryInformationToken` at `0x180017cc7`
- `ntdll!NtQueryInformationToken` at `0x180017cfe`
- `ntdll!NtQueryInformationToken` at `0x180017d48`
- `ntdll!NtQueryInformationToken` at `0x180017d79`
- `ntdll!NtQueryInformationToken` at `0x180017dd1`
- `ntdll!NtQueryInformationToken` at `0x180017b95`
- `ntdll!NtQueryInformationToken` at `0x180017bdc`
- `ntdll!NtQueryInformationToken` at `0x180017cc7`
- `ntdll!NtQueryInformationToken` at `0x180017cfe`
- `ntdll!NtQueryInformationToken` at `0x180017d48`
- `ntdll!NtQueryInformationToken` at `0x180017d79`
- `ntdll!NtQueryInformationToken` at `0x180017dd1`
- `ntdll!RtlEqualSid` at `0x180017e4c`
- `ntdll!RtlEqualSid` at `0x180017e4c`

## pseudocode

```c
DWORD __fastcall LUAIsUserUACAdmin(_DWORD *a1)
{
  unsigned int v1; // ebx
  HANDLE CurrentProcess; // rax
  int v4; // r15d
  void *v5; // rdi
  NTSTATUS v6; // eax
  NTSTATUS v7; // edi
  int v8; // eax
  HANDLE v9; // rcx
  _QWORD *v10; // rsi
  HANDLE v11; // r14
  HLOCAL v12; // r12
  __int64 v13; // rcx
  ULONG TokenInformation; // [rsp+30h] [rbp-59h] BYREF
  DWORD cbSid; // [rsp+34h] [rbp-55h] BYREF
  ULONG ReturnLength; // [rsp+38h] [rbp-51h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-49h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-41h] BYREF
  HANDLE v20[2]; // [rsp+50h] [rbp-39h] BYREF
  _BYTE pSid[80]; // [rsp+60h] [rbp-29h] BYREF

  v1 = 0;
  *a1 = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken_0(CurrentProcess, 0xAu, &TokenHandle) )
  {
    v4 = 4;
    if ( !(unsigned int)Feature_ShadowAdmin__private_IsEnabledDeviceUsageNoInline() )
    {
      v5 = TokenHandle;
      ReturnLength = 0;
      cbSid = 0;
      TokenInformation = 1;
      v6 = NtQueryInformationToken(TokenHandle, TokenElevationType, &TokenInformation, 4u, &ReturnLength);
      if ( v6 >= 0 )
      {
        if ( TokenInformation == 2 )
        {
          v7 = v6;
          *a1 = _LUAIsTokenAdmin(TokenHandle);
LABEL_44:
          CloseHandle(TokenHandle);
          return v7;
        }
        if ( TokenInformation == 1 )
        {
          v6 = NtQueryInformationToken(v5, TokenElevation, &cbSid, 4u, &ReturnLength);
          v7 = v6;
          if ( v6 >= 0 )
          {
            if ( cbSid )
            {
              *a1 = _LUAIsTokenAdmin(TokenHandle);
              goto LABEL_44;
            }
          }
        }
      }
      v7 = v6;
      if ( v6 >= 0 )
      {
        hObject = 0;
        cbSid = 8;
        if ( GetTokenInformation_0(TokenHandle, TokenLinkedToken, &hObject, 8u, &cbSid) )
        {
          if ( hObject )
          {
            v8 = _LUAIsTokenAdmin(hObject);
            v9 = hObject;
            *a1 = v8;
            CloseHandle(v9);
          }
        }
      }
      goto LABEL_44;
    }
    v10 = 0;
    v11 = TokenHandle;
    *a1 = 0;
    v20[0] = 0;
    LODWORD(hObject) = 0;
    if ( !(unsigned int)Feature_ShadowAdmin__private_IsEnabledDeviceUsageNoInline() )
    {
      v7 = -1073741822;
      goto LABEL_44;
    }
    ReturnLength = 0;
    TokenInformation = 0;
    cbSid = 1;
    v7 = NtQueryInformationToken(v11, TokenElevationType, &cbSid, 4u, &ReturnLength);
    if ( v7 >= 0 )
    {
      if ( cbSid == 2 )
        goto LABEL_26;
      if ( cbSid == 1 )
      {
        v7 = NtQueryInformationToken(v11, TokenElevation, &TokenInformation, 4u, &ReturnLength);
        if ( v7 >= 0 )
        {
          if ( TokenInformation )
            goto LABEL_26;
        }
      }
    }
    if ( v7 >= 0 )
    {
      if ( (unsigned int)LUAIsShadowAdminEnabled() )
      {
        v4 = 16;
        goto LABEL_26;
      }
      if ( NtQueryInformationToken(v11, TokenLinkedToken, v20, 8u, (PULONG)&hObject) >= 0 )
      {
        v11 = v20[0];
LABEL_26:
        TokenInformation = 0;
        v7 = NtQueryInformationToken(v11, TokenGroupsAndPrivileges, 0, 0, &TokenInformation);
        if ( v7 == -1073741789 )
        {
          v12 = LocalAlloc(0x40u, TokenInformation);
          if ( v12 )
          {
            v7 = NtQueryInformationToken(v11, TokenGroupsAndPrivileges, v12, TokenInformation, &TokenInformation);
            if ( v7 < 0 )
              LocalFree(v12);
            else
              v10 = v12;
          }
          else
          {
            v7 = -1073741801;
          }
        }
        if ( v7 >= 0 )
        {
          cbSid = 68;
          if ( CreateWellKnownSid_0(WinBuiltinAdministratorsSid, 0, pSid, &cbSid) )
          {
            if ( *(_DWORD *)v10 )
            {
              while ( 1 )
              {
                v13 = v10[1] + 16LL * v1;
                if ( (v4 & *(_DWORD *)(v13 + 8)) == v4 )
                {
                  if ( RtlEqualSid(*(PSID *)v13, pSid) )
                    break;
                }
                if ( ++v1 >= *(_DWORD *)v10 )
                  goto LABEL_40;
              }
              *a1 = 1;
            }
          }
        }
      }
    }
LABEL_40:
    if ( v20[0] )
      CloseHandle(v20[0]);
    if ( v10 )
      LocalFree(v10);
    goto LABEL_44;
  }
  if ( (int)GetLastError() > 0 )
    return (unsigned __int16)GetLastError() | 0xC0070000;
  else
    return GetLastError();
}

```

## disassembly

```asm
0x180017b00  push    rbp
0x180017b02  push    rbx
0x180017b03  push    r13
0x180017b05  lea     rbp, [rsp-47h]
0x180017b0a  sub     rsp, 0D0h
0x180017b11  mov     rax, cs:__security_cookie
0x180017b18  xor     rax, rsp
0x180017b1b  mov     [rbp+57h+var_30], rax
0x180017b1f  xor     ebx, ebx
0x180017b21  mov     r13, rcx
0x180017b24  mov     [rcx], ebx
0x180017b26  mov     [rbp+57h+TokenHandle], rbx
0x180017b2a  call    cs:__imp_GetCurrentProcess
0x180017b31  nop     dword ptr [rax+rax+00h]
0x180017b36  mov     rcx, rax; ProcessHandle
0x180017b39  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x180017b3d  lea     edx, [rbx+0Ah]; DesiredAccess
0x180017b40  call    OpenProcessToken_0
0x180017b45  test    eax, eax
0x180017b47  jz      loc_180017EC9
0x180017b4d  mov     [rsp+0E0h+arg_10], rdi
0x180017b55  mov     [rsp+0E0h+var_20], r15
0x180017b5d  call    Feature_ShadowAdmin__private_IsEnabledDeviceUsageNoInline
0x180017b62  lea     r15d, [rbx+4]
0x180017b66  test    eax, eax
0x180017b68  jnz     loc_180017C6D
0x180017b6e  mov     rdi, [rbp+57h+TokenHandle]
0x180017b72  lea     rax, [rbp+57h+var_A8]
0x180017b76  mov     rcx, rdi; TokenHandle
0x180017b79  mov     [rbp+57h+var_A8], ebx
0x180017b7c  mov     r9d, r15d; TokenInformationLength
0x180017b7f  mov     [rbp+57h+cbSid], ebx
0x180017b82  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180017b86  mov     [rbp+57h+TokenInformation], 1
0x180017b8d  lea     edx, [rbx+12h]; TokenInformationClass
0x180017b90  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x180017b95  call    cs:__imp_NtQueryInformationToken
0x180017b9c  nop     dword ptr [rax+rax+00h]
0x180017ba1  test    eax, eax
0x180017ba3  js      short loc_180017C05
0x180017ba5  mov     ecx, [rbp+57h+TokenInformation]
0x180017ba8  cmp     ecx, 2
0x180017bab  jnz     short loc_180017BC1
0x180017bad  mov     rcx, [rbp+57h+TokenHandle]; void *
0x180017bb1  mov     edi, eax
0x180017bb3  call    ?_LUAIsTokenAdmin@@YAHPEAX@Z; _LUAIsTokenAdmin(void *)
0x180017bb8  mov     [r13+0], eax
0x180017bbc  jmp     loc_180017EA5
0x180017bc1  cmp     ecx, 1
0x180017bc4  jnz     short loc_180017C05
0x180017bc6  lea     rax, [rbp+57h+var_A8]
0x180017bca  mov     r9d, r15d; TokenInformationLength
0x180017bcd  lea     edx, [rcx+13h]; TokenInformationClass
0x180017bd0  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x180017bd5  mov     rcx, rdi; TokenHandle
0x180017bd8  lea     r8, [rbp+57h+cbSid]; TokenInformation
0x180017bdc  call    cs:__imp_NtQueryInformationToken
0x180017be3  nop     dword ptr [rax+rax+00h]
0x180017be8  mov     edi, eax
0x180017bea  test    eax, eax
0x180017bec  js      short loc_180017C05
0x180017bee  cmp     [rbp+57h+cbSid], ebx
0x180017bf1  jz      short loc_180017C05
0x180017bf3  mov     rcx, [rbp+57h+TokenHandle]; void *
0x180017bf7  call    ?_LUAIsTokenAdmin@@YAHPEAX@Z; _LUAIsTokenAdmin(void *)
0x180017bfc  mov     [r13+0], eax
0x180017c00  jmp     loc_180017EA5
0x180017c05  mov     edi, eax
0x180017c07  test    eax, eax
0x180017c09  js      loc_180017EA5
0x180017c0f  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180017c13  lea     rax, [rbp+57h+cbSid]
0x180017c17  mov     r9d, 8; TokenInformationLength
0x180017c1d  mov     [rbp+57h+hObject], rbx
0x180017c21  lea     r8, [rbp+57h+hObject]; TokenInformation
0x180017c25  mov     [rbp+57h+cbSid], 8
0x180017c2c  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x180017c31  lea     edx, [r9+0Bh]; TokenInformationClass
0x180017c35  call    GetTokenInformation_0
0x180017c3a  test    eax, eax
0x180017c3c  jz      loc_180017EA5
0x180017c42  mov     rcx, [rbp+57h+hObject]; void *
0x180017c46  test    rcx, rcx
0x180017c49  jz      loc_180017EA5
0x180017c4f  call    ?_LUAIsTokenAdmin@@YAHPEAX@Z; _LUAIsTokenAdmin(void *)
0x180017c54  mov     rcx, [rbp+57h+hObject]; hObject
0x180017c58  mov     [r13+0], eax
0x180017c5c  call    cs:__imp_CloseHandle
0x180017c63  nop     dword ptr [rax+rax+00h]
0x180017c68  jmp     loc_180017EA5
0x180017c6d  mov     [rsp+0E0h+arg_8], rsi
0x180017c75  mov     rsi, rbx
0x180017c78  mov     [rsp+0E0h+var_18], r14
0x180017c80  mov     r14, [rbp+57h+TokenHandle]
0x180017c84  mov     [r13+0], ebx
0x180017c88  mov     [rbp+57h+var_90], rbx
0x180017c8c  mov     dword ptr [rbp+57h+hObject], ebx
0x180017c8f  call    Feature_ShadowAdmin__private_IsEnabledDeviceUsageNoInline
0x180017c94  test    eax, eax
0x180017c96  jnz     short loc_180017CA2
0x180017c98  mov     edi, 0C0000002h
0x180017c9d  jmp     loc_180017E95
0x180017ca2  lea     rax, [rbp+57h+var_A8]
0x180017ca6  mov     [rbp+57h+var_A8], ebx
0x180017ca9  mov     r9d, r15d; TokenInformationLength
0x180017cac  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x180017cb1  lea     r8, [rbp+57h+cbSid]; TokenInformation
0x180017cb5  mov     [rbp+57h+TokenInformation], ebx
0x180017cb8  mov     edx, 12h; TokenInformationClass
0x180017cbd  mov     [rbp+57h+cbSid], 1
0x180017cc4  mov     rcx, r14; TokenHandle
0x180017cc7  call    cs:__imp_NtQueryInformationToken
0x180017cce  nop     dword ptr [rax+rax+00h]
0x180017cd3  mov     edi, eax
0x180017cd5  test    eax, eax
0x180017cd7  js      short loc_180017D15
0x180017cd9  mov     eax, [rbp+57h+cbSid]
0x180017cdc  cmp     eax, 2
0x180017cdf  jz      short loc_180017D60
0x180017ce1  cmp     eax, 1
0x180017ce4  jnz     short loc_180017D15
0x180017ce6  lea     rax, [rbp+57h+var_A8]
0x180017cea  mov     r9d, r15d; TokenInformationLength
0x180017ced  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180017cf1  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x180017cf6  mov     edx, 14h; TokenInformationClass
0x180017cfb  mov     rcx, r14; TokenHandle
0x180017cfe  call    cs:__imp_NtQueryInformationToken
0x180017d05  nop     dword ptr [rax+rax+00h]
0x180017d0a  mov     edi, eax
0x180017d0c  test    eax, eax
0x180017d0e  js      short loc_180017D15
0x180017d10  cmp     [rbp+57h+TokenInformation], ebx
0x180017d13  jnz     short loc_180017D60
0x180017d15  test    edi, edi
0x180017d17  js      loc_180017E6C
0x180017d1d  call    LUAIsShadowAdminEnabled
0x180017d22  test    eax, eax
0x180017d24  jz      short loc_180017D2E
0x180017d26  mov     r15d, 10h
0x180017d2c  jmp     short loc_180017D60
0x180017d2e  mov     r9d, 8; TokenInformationLength
0x180017d34  lea     rax, [rbp+57h+hObject]
0x180017d38  lea     r8, [rbp+57h+var_90]; TokenInformation
0x180017d3c  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x180017d41  mov     rcx, r14; TokenHandle
0x180017d44  lea     edx, [r9+0Bh]; TokenInformationClass
0x180017d48  call    cs:__imp_NtQueryInformationToken
0x180017d4f  nop     dword ptr [rax+rax+00h]
0x180017d54  test    eax, eax
0x180017d56  js      loc_180017E6C
0x180017d5c  mov     r14, [rbp+57h+var_90]
0x180017d60  xor     r9d, r9d; TokenInformationLength
0x180017d63  mov     [rbp+57h+TokenInformation], ebx
0x180017d66  lea     rax, [rbp+57h+TokenInformation]
0x180017d6a  xor     r8d, r8d; TokenInformation
0x180017d6d  mov     rcx, r14; TokenHandle
0x180017d70  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x180017d75  lea     edx, [r9+0Dh]; TokenInformationClass
0x180017d79  call    cs:__imp_NtQueryInformationToken
0x180017d80  nop     dword ptr [rax+rax+00h]
0x180017d85  mov     edi, eax
0x180017d87  cmp     eax, 0C0000023h
0x180017d8c  jnz     short loc_180017DFF
0x180017d8e  mov     edx, [rbp+57h+TokenInformation]; uBytes
0x180017d91  mov     ecx, 40h ; '@'; uFlags
0x180017d96  mov     [rsp+0E0h+arg_18], r12
0x180017d9e  call    cs:__imp_LocalAlloc
0x180017da5  nop     dword ptr [rax+rax+00h]
0x180017daa  mov     r12, rax
0x180017dad  test    rax, rax
0x180017db0  jnz     short loc_180017DB9
0x180017db2  mov     edi, 0C0000017h
0x180017db7  jmp     short loc_180017DF7
0x180017db9  mov     r9d, [rbp+57h+TokenInformation]; TokenInformationLength
0x180017dbd  lea     rax, [rbp+57h+TokenInformation]
0x180017dc1  mov     r8, r12; TokenInformation
0x180017dc4  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x180017dc9  mov     edx, 0Dh; TokenInformationClass
0x180017dce  mov     rcx, r14; TokenHandle
0x180017dd1  call    cs:__imp_NtQueryInformationToken
0x180017dd8  nop     dword ptr [rax+rax+00h]
0x180017ddd  mov     edi, eax
0x180017ddf  test    eax, eax
0x180017de1  js      short loc_180017DE8
0x180017de3  mov     rsi, r12
0x180017de6  jmp     short loc_180017DF7
0x180017de8  mov     rcx, r12; hMem
0x180017deb  call    cs:__imp_LocalFree
0x180017df2  nop     dword ptr [rax+rax+00h]
0x180017df7  mov     r12, [rsp+0E0h+arg_18]
0x180017dff  test    edi, edi
0x180017e01  js      short loc_180017E6C
0x180017e03  xor     edx, edx; DomainSid
0x180017e05  mov     [rbp+57h+cbSid], 44h ; 'D'
0x180017e0c  lea     r9, [rbp+57h+cbSid]; cbSid
0x180017e10  lea     r8, [rbp+57h+pSid]; pSid
0x180017e14  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x180017e17  call    CreateWellKnownSid_0
0x180017e1c  test    eax, eax
0x180017e1e  jz      short loc_180017E6C
0x180017e20  cmp     [rsi], ebx
0x180017e22  jbe     short loc_180017E6C
0x180017e24  nop     dword ptr [rax+00h]
0x180017e28  nop     dword ptr [rax+rax+00000000h]
0x180017e30  mov     ecx, ebx
0x180017e32  shl     rcx, 4
0x180017e36  add     rcx, [rsi+8]
0x180017e3a  mov     eax, [rcx+8]
0x180017e3d  and     eax, r15d
0x180017e40  cmp     eax, r15d
0x180017e43  jnz     short loc_180017E5C
0x180017e45  mov     rcx, [rcx]; Sid1
0x180017e48  lea     rdx, [rbp+57h+pSid]; Sid2
0x180017e4c  call    cs:__imp_RtlEqualSid
0x180017e53  nop     dword ptr [rax+rax+00h]
0x180017e58  test    al, al
0x180017e5a  jnz     short loc_180017E64
0x180017e5c  inc     ebx
0x180017e5e  cmp     ebx, [rsi]
0x180017e60  jb      short loc_180017E30
0x180017e62  jmp     short loc_180017E6C
0x180017e64  mov     dword ptr [r13+0], 1
0x180017e6c  mov     rcx, [rbp+57h+var_90]; hObject
0x180017e70  test    rcx, rcx
0x180017e73  jz      short loc_180017E81
0x180017e75  call    cs:__imp_CloseHandle
0x180017e7c  nop     dword ptr [rax+rax+00h]
0x180017e81  test    rsi, rsi
0x180017e84  jz      short loc_180017E95
0x180017e86  mov     rcx, rsi; hMem
0x180017e89  call    cs:__imp_LocalFree
0x180017e90  nop     dword ptr [rax+rax+00h]
0x180017e95  mov     rsi, [rsp+0E0h+arg_8]
0x180017e9d  mov     r14, [rsp+0E0h+var_18]
0x180017ea5  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180017ea9  call    cs:__imp_CloseHandle
0x180017eb0  nop     dword ptr [rax+rax+00h]
0x180017eb5  mov     r15, [rsp+0E0h+var_20]
0x180017ebd  mov     eax, edi
0x180017ebf  mov     rdi, [rsp+0E0h+arg_10]
0x180017ec7  jmp     short loc_180017EFB
0x180017ec9  call    cs:__imp_GetLastError
0x180017ed0  nop     dword ptr [rax+rax+00h]
0x180017ed5  test    eax, eax
0x180017ed7  jg      short loc_180017EE7
0x180017ed9  call    cs:__imp_GetLastError
0x180017ee0  nop     dword ptr [rax+rax+00h]
0x180017ee5  jmp     short loc_180017EFB
0x180017ee7  call    cs:__imp_GetLastError
0x180017eee  nop     dword ptr [rax+rax+00h]
0x180017ef3  movzx   eax, ax
0x180017ef6  or      eax, 0C0070000h
0x180017efb  mov     rcx, [rbp+57h+var_30]
0x180017eff  xor     rcx, rsp; StackCookie
0x180017f02  call    __security_check_cookie
0x180017f07  add     rsp, 0D0h
0x180017f0e  pop     r13
0x180017f10  pop     rbx
0x180017f11  pop     rbp
0x180017f12  retn
```
