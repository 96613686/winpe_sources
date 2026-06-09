# LUAIsUserUACAdmin

- ea: `0x180017850`
- end: `0x180017c64`
- name: `LUAIsUserUACAdmin`
- size: `1044`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180041c24`

## callees

- `0x180017850`
- `0x18001bc7c`
- `0x18001bd37`
- `0x1800419dc`
- `0x180041ac8`
- `0x180041e64`
- `0x180042950`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180017b67`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180017b67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017c19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017c29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017c37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017c19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017c29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017c37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001787a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001787a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800179ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017bc5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017bf9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800179ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017bc5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017bf9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017b3b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017bd9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017b3b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017bd9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017aee`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017aee`
- `ntdll!NtQueryInformationToken` at `0x1800178e5`
- `ntdll!NtQueryInformationToken` at `0x18001792c`
- `ntdll!NtQueryInformationToken` at `0x180017a17`
- `ntdll!NtQueryInformationToken` at `0x180017a4e`
- `ntdll!NtQueryInformationToken` at `0x180017a98`
- `ntdll!NtQueryInformationToken` at `0x180017ac9`
- `ntdll!NtQueryInformationToken` at `0x180017b21`
- `ntdll!NtQueryInformationToken` at `0x1800178e5`
- `ntdll!NtQueryInformationToken` at `0x18001792c`
- `ntdll!NtQueryInformationToken` at `0x180017a17`
- `ntdll!NtQueryInformationToken` at `0x180017a4e`
- `ntdll!NtQueryInformationToken` at `0x180017a98`
- `ntdll!NtQueryInformationToken` at `0x180017ac9`
- `ntdll!NtQueryInformationToken` at `0x180017b21`
- `ntdll!RtlEqualSid` at `0x180017b9c`
- `ntdll!RtlEqualSid` at `0x180017b9c`

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
          if ( CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, pSid, &cbSid) )
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
0x180017850  push    rbp
0x180017852  push    rbx
0x180017853  push    r13
0x180017855  lea     rbp, [rsp-47h]
0x18001785a  sub     rsp, 0D0h
0x180017861  mov     rax, cs:__security_cookie
0x180017868  xor     rax, rsp
0x18001786b  mov     [rbp+57h+var_30], rax
0x18001786f  xor     ebx, ebx
0x180017871  mov     r13, rcx
0x180017874  mov     [rcx], ebx
0x180017876  mov     [rbp+57h+TokenHandle], rbx
0x18001787a  call    cs:__imp_GetCurrentProcess
0x180017881  nop     dword ptr [rax+rax+00h]
0x180017886  mov     rcx, rax; ProcessHandle
0x180017889  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x18001788d  lea     edx, [rbx+0Ah]; DesiredAccess
0x180017890  call    OpenProcessToken_0
0x180017895  test    eax, eax
0x180017897  jz      loc_180017C19
0x18001789d  mov     [rsp+0E0h+arg_10], rdi
0x1800178a5  mov     [rsp+0E0h+var_20], r15
0x1800178ad  call    Feature_ShadowAdmin__private_IsEnabledDeviceUsageNoInline
0x1800178b2  lea     r15d, [rbx+4]
0x1800178b6  test    eax, eax
0x1800178b8  jnz     loc_1800179BD
0x1800178be  mov     rdi, [rbp+57h+TokenHandle]
0x1800178c2  lea     rax, [rbp+57h+var_A8]
0x1800178c6  mov     rcx, rdi; TokenHandle
0x1800178c9  mov     [rbp+57h+var_A8], ebx
0x1800178cc  mov     r9d, r15d; TokenInformationLength
0x1800178cf  mov     [rbp+57h+cbSid], ebx
0x1800178d2  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1800178d6  mov     [rbp+57h+TokenInformation], 1
0x1800178dd  lea     edx, [rbx+12h]; TokenInformationClass
0x1800178e0  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x1800178e5  call    cs:__imp_NtQueryInformationToken
0x1800178ec  nop     dword ptr [rax+rax+00h]
0x1800178f1  test    eax, eax
0x1800178f3  js      short loc_180017955
0x1800178f5  mov     ecx, [rbp+57h+TokenInformation]
0x1800178f8  cmp     ecx, 2
0x1800178fb  jnz     short loc_180017911
0x1800178fd  mov     rcx, [rbp+57h+TokenHandle]; void *
0x180017901  mov     edi, eax
0x180017903  call    ?_LUAIsTokenAdmin@@YAHPEAX@Z; _LUAIsTokenAdmin(void *)
0x180017908  mov     [r13+0], eax
0x18001790c  jmp     loc_180017BF5
0x180017911  cmp     ecx, 1
0x180017914  jnz     short loc_180017955
0x180017916  lea     rax, [rbp+57h+var_A8]
0x18001791a  mov     r9d, r15d; TokenInformationLength
0x18001791d  lea     edx, [rcx+13h]; TokenInformationClass
0x180017920  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x180017925  mov     rcx, rdi; TokenHandle
0x180017928  lea     r8, [rbp+57h+cbSid]; TokenInformation
0x18001792c  call    cs:__imp_NtQueryInformationToken
0x180017933  nop     dword ptr [rax+rax+00h]
0x180017938  mov     edi, eax
0x18001793a  test    eax, eax
0x18001793c  js      short loc_180017955
0x18001793e  cmp     [rbp+57h+cbSid], ebx
0x180017941  jz      short loc_180017955
0x180017943  mov     rcx, [rbp+57h+TokenHandle]; void *
0x180017947  call    ?_LUAIsTokenAdmin@@YAHPEAX@Z; _LUAIsTokenAdmin(void *)
0x18001794c  mov     [r13+0], eax
0x180017950  jmp     loc_180017BF5
0x180017955  mov     edi, eax
0x180017957  test    eax, eax
0x180017959  js      loc_180017BF5
0x18001795f  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180017963  lea     rax, [rbp+57h+cbSid]
0x180017967  mov     r9d, 8; TokenInformationLength
0x18001796d  mov     [rbp+57h+hObject], rbx
0x180017971  lea     r8, [rbp+57h+hObject]; TokenInformation
0x180017975  mov     [rbp+57h+cbSid], 8
0x18001797c  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x180017981  lea     edx, [r9+0Bh]; TokenInformationClass
0x180017985  call    GetTokenInformation_0
0x18001798a  test    eax, eax
0x18001798c  jz      loc_180017BF5
0x180017992  mov     rcx, [rbp+57h+hObject]; void *
0x180017996  test    rcx, rcx
0x180017999  jz      loc_180017BF5
0x18001799f  call    ?_LUAIsTokenAdmin@@YAHPEAX@Z; _LUAIsTokenAdmin(void *)
0x1800179a4  mov     rcx, [rbp+57h+hObject]; hObject
0x1800179a8  mov     [r13+0], eax
0x1800179ac  call    cs:__imp_CloseHandle
0x1800179b3  nop     dword ptr [rax+rax+00h]
0x1800179b8  jmp     loc_180017BF5
0x1800179bd  mov     [rsp+0E0h+arg_8], rsi
0x1800179c5  mov     rsi, rbx
0x1800179c8  mov     [rsp+0E0h+var_18], r14
0x1800179d0  mov     r14, [rbp+57h+TokenHandle]
0x1800179d4  mov     [r13+0], ebx
0x1800179d8  mov     [rbp+57h+var_90], rbx
0x1800179dc  mov     dword ptr [rbp+57h+hObject], ebx
0x1800179df  call    Feature_ShadowAdmin__private_IsEnabledDeviceUsageNoInline
0x1800179e4  test    eax, eax
0x1800179e6  jnz     short loc_1800179F2
0x1800179e8  mov     edi, 0C0000002h
0x1800179ed  jmp     loc_180017BE5
0x1800179f2  lea     rax, [rbp+57h+var_A8]
0x1800179f6  mov     [rbp+57h+var_A8], ebx
0x1800179f9  mov     r9d, r15d; TokenInformationLength
0x1800179fc  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x180017a01  lea     r8, [rbp+57h+cbSid]; TokenInformation
0x180017a05  mov     [rbp+57h+TokenInformation], ebx
0x180017a08  mov     edx, 12h; TokenInformationClass
0x180017a0d  mov     [rbp+57h+cbSid], 1
0x180017a14  mov     rcx, r14; TokenHandle
0x180017a17  call    cs:__imp_NtQueryInformationToken
0x180017a1e  nop     dword ptr [rax+rax+00h]
0x180017a23  mov     edi, eax
0x180017a25  test    eax, eax
0x180017a27  js      short loc_180017A65
0x180017a29  mov     eax, [rbp+57h+cbSid]
0x180017a2c  cmp     eax, 2
0x180017a2f  jz      short loc_180017AB0
0x180017a31  cmp     eax, 1
0x180017a34  jnz     short loc_180017A65
0x180017a36  lea     rax, [rbp+57h+var_A8]
0x180017a3a  mov     r9d, r15d; TokenInformationLength
0x180017a3d  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180017a41  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x180017a46  mov     edx, 14h; TokenInformationClass
0x180017a4b  mov     rcx, r14; TokenHandle
0x180017a4e  call    cs:__imp_NtQueryInformationToken
0x180017a55  nop     dword ptr [rax+rax+00h]
0x180017a5a  mov     edi, eax
0x180017a5c  test    eax, eax
0x180017a5e  js      short loc_180017A65
0x180017a60  cmp     [rbp+57h+TokenInformation], ebx
0x180017a63  jnz     short loc_180017AB0
0x180017a65  test    edi, edi
0x180017a67  js      loc_180017BBC
0x180017a6d  call    LUAIsShadowAdminEnabled
0x180017a72  test    eax, eax
0x180017a74  jz      short loc_180017A7E
0x180017a76  mov     r15d, 10h
0x180017a7c  jmp     short loc_180017AB0
0x180017a7e  mov     r9d, 8; TokenInformationLength
0x180017a84  lea     rax, [rbp+57h+hObject]
0x180017a88  lea     r8, [rbp+57h+var_90]; TokenInformation
0x180017a8c  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x180017a91  mov     rcx, r14; TokenHandle
0x180017a94  lea     edx, [r9+0Bh]; TokenInformationClass
0x180017a98  call    cs:__imp_NtQueryInformationToken
0x180017a9f  nop     dword ptr [rax+rax+00h]
0x180017aa4  test    eax, eax
0x180017aa6  js      loc_180017BBC
0x180017aac  mov     r14, [rbp+57h+var_90]
0x180017ab0  xor     r9d, r9d; TokenInformationLength
0x180017ab3  mov     [rbp+57h+TokenInformation], ebx
0x180017ab6  lea     rax, [rbp+57h+TokenInformation]
0x180017aba  xor     r8d, r8d; TokenInformation
0x180017abd  mov     rcx, r14; TokenHandle
0x180017ac0  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x180017ac5  lea     edx, [r9+0Dh]; TokenInformationClass
0x180017ac9  call    cs:__imp_NtQueryInformationToken
0x180017ad0  nop     dword ptr [rax+rax+00h]
0x180017ad5  mov     edi, eax
0x180017ad7  cmp     eax, 0C0000023h
0x180017adc  jnz     short loc_180017B4F
0x180017ade  mov     edx, [rbp+57h+TokenInformation]; uBytes
0x180017ae1  mov     ecx, 40h ; '@'; uFlags
0x180017ae6  mov     [rsp+0E0h+arg_18], r12
0x180017aee  call    cs:__imp_LocalAlloc
0x180017af5  nop     dword ptr [rax+rax+00h]
0x180017afa  mov     r12, rax
0x180017afd  test    rax, rax
0x180017b00  jnz     short loc_180017B09
0x180017b02  mov     edi, 0C0000017h
0x180017b07  jmp     short loc_180017B47
0x180017b09  mov     r9d, [rbp+57h+TokenInformation]; TokenInformationLength
0x180017b0d  lea     rax, [rbp+57h+TokenInformation]
0x180017b11  mov     r8, r12; TokenInformation
0x180017b14  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x180017b19  mov     edx, 0Dh; TokenInformationClass
0x180017b1e  mov     rcx, r14; TokenHandle
0x180017b21  call    cs:__imp_NtQueryInformationToken
0x180017b28  nop     dword ptr [rax+rax+00h]
0x180017b2d  mov     edi, eax
0x180017b2f  test    eax, eax
0x180017b31  js      short loc_180017B38
0x180017b33  mov     rsi, r12
0x180017b36  jmp     short loc_180017B47
0x180017b38  mov     rcx, r12; hMem
0x180017b3b  call    cs:__imp_LocalFree
0x180017b42  nop     dword ptr [rax+rax+00h]
0x180017b47  mov     r12, [rsp+0E0h+arg_18]
0x180017b4f  test    edi, edi
0x180017b51  js      short loc_180017BBC
0x180017b53  xor     edx, edx; DomainSid
0x180017b55  mov     [rbp+57h+cbSid], 44h ; 'D'
0x180017b5c  lea     r9, [rbp+57h+cbSid]; cbSid
0x180017b60  lea     r8, [rbp+57h+pSid]; pSid
0x180017b64  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x180017b67  call    cs:__imp_CreateWellKnownSid
0x180017b6e  nop     dword ptr [rax+rax+00h]
0x180017b73  test    eax, eax
0x180017b75  jz      short loc_180017BBC
0x180017b77  cmp     [rsi], ebx
0x180017b79  jbe     short loc_180017BBC
0x180017b7b  nop     dword ptr [rax+rax+00h]
0x180017b80  mov     ecx, ebx
0x180017b82  shl     rcx, 4
0x180017b86  add     rcx, [rsi+8]
0x180017b8a  mov     eax, [rcx+8]
0x180017b8d  and     eax, r15d
0x180017b90  cmp     eax, r15d
0x180017b93  jnz     short loc_180017BAC
0x180017b95  mov     rcx, [rcx]; Sid1
0x180017b98  lea     rdx, [rbp+57h+pSid]; Sid2
0x180017b9c  call    cs:__imp_RtlEqualSid
0x180017ba3  nop     dword ptr [rax+rax+00h]
0x180017ba8  test    al, al
0x180017baa  jnz     short loc_180017BB4
0x180017bac  inc     ebx
0x180017bae  cmp     ebx, [rsi]
0x180017bb0  jb      short loc_180017B80
0x180017bb2  jmp     short loc_180017BBC
0x180017bb4  mov     dword ptr [r13+0], 1
0x180017bbc  mov     rcx, [rbp+57h+var_90]; hObject
0x180017bc0  test    rcx, rcx
0x180017bc3  jz      short loc_180017BD1
0x180017bc5  call    cs:__imp_CloseHandle
0x180017bcc  nop     dword ptr [rax+rax+00h]
0x180017bd1  test    rsi, rsi
0x180017bd4  jz      short loc_180017BE5
0x180017bd6  mov     rcx, rsi; hMem
0x180017bd9  call    cs:__imp_LocalFree
0x180017be0  nop     dword ptr [rax+rax+00h]
0x180017be5  mov     rsi, [rsp+0E0h+arg_8]
0x180017bed  mov     r14, [rsp+0E0h+var_18]
0x180017bf5  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180017bf9  call    cs:__imp_CloseHandle
0x180017c00  nop     dword ptr [rax+rax+00h]
0x180017c05  mov     r15, [rsp+0E0h+var_20]
0x180017c0d  mov     eax, edi
0x180017c0f  mov     rdi, [rsp+0E0h+arg_10]
0x180017c17  jmp     short loc_180017C4B
0x180017c19  call    cs:__imp_GetLastError
0x180017c20  nop     dword ptr [rax+rax+00h]
0x180017c25  test    eax, eax
0x180017c27  jg      short loc_180017C37
0x180017c29  call    cs:__imp_GetLastError
0x180017c30  nop     dword ptr [rax+rax+00h]
0x180017c35  jmp     short loc_180017C4B
0x180017c37  call    cs:__imp_GetLastError
0x180017c3e  nop     dword ptr [rax+rax+00h]
0x180017c43  movzx   eax, ax
0x180017c46  or      eax, 0C0070000h
0x180017c4b  mov     rcx, [rbp+57h+var_30]
0x180017c4f  xor     rcx, rsp; StackCookie
0x180017c52  call    __security_check_cookie
0x180017c57  add     rsp, 0D0h
0x180017c5e  pop     r13
0x180017c60  pop     rbx
0x180017c61  pop     rbp
0x180017c62  retn
```
