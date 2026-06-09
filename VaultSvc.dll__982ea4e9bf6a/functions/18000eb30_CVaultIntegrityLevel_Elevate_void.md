# CVaultIntegrityLevel::Elevate(void)

- ea: `0x18000eb30`
- end: `0x18000f0d0`
- name: `?Elevate@CVaultIntegrityLevel@@QEAAKXZ`
- size: `1440`
- prototype: `ULONG __fastcall(CVaultIntegrityLevel *this)`
- caller_count: `11`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000f7d0`
- `0x18000ff18`
- `0x180013390`
- `0x18001ab50`
- `0x18001eda0`
- `0x180023c90`
- `0x18002d724`
- `0x1800398d0`
- `0x180039ea8`
- `0x180040944`
- `0x180040f30`

## callees

- `0x18000eb30`
- `0x180012210`
- `0x18003a580`
- `0x18003af10`
- `0x18003b7b0`
- `0x18003b7d8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ed80`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ee33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f0a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ed80`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ee33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f0a8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ef25`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ef25`
- `ntdll!NtSetInformationThread` at `0x18000ec8a`
- `ntdll!NtSetInformationThread` at `0x18000ed48`
- `ntdll!NtSetInformationThread` at `0x18000f06f`
- `ntdll!NtSetInformationThread` at `0x18000ec8a`
- `ntdll!NtSetInformationThread` at `0x18000ed48`
- `ntdll!NtSetInformationThread` at `0x18000f06f`
- `ntdll!RtlInitializeSid` at `0x18000ebcc`
- `ntdll!RtlInitializeSid` at `0x18000ebcc`
- `ntdll!RtlSubAuthoritySid` at `0x18000ebd8`
- `ntdll!RtlSubAuthoritySid` at `0x18000ebd8`
- `ntdll!RtlSidDominates` at `0x18000ec58`
- `ntdll!RtlSidDominates` at `0x18000ec58`
- `ntdll!NtDuplicateToken` at `0x18000ece1`
- `ntdll!NtDuplicateToken` at `0x18000ece1`
- `ntdll!NtSetInformationToken` at `0x18000ed21`
- `ntdll!NtSetInformationToken` at `0x18000ed21`
- `ntdll!NtQueryInformationToken` at `0x18000ec3c`
- `ntdll!NtQueryInformationToken` at `0x18000ef88`
- `ntdll!NtQueryInformationToken` at `0x18000ec3c`
- `ntdll!NtQueryInformationToken` at `0x18000ef88`
- `ntdll!NtOpenThreadToken` at `0x18000ec0f`
- `ntdll!NtOpenThreadToken` at `0x18000ec0f`
- `ntdll!RtlNtStatusToDosError` at `0x18000ed99`
- `ntdll!RtlNtStatusToDosError` at `0x18000edcf`
- `ntdll!RtlNtStatusToDosError` at `0x18000ed99`
- `ntdll!RtlNtStatusToDosError` at `0x18000edcf`

## pseudocode

```c
ULONG __fastcall CVaultIntegrityLevel::Elevate(CVaultIntegrityLevel *this)
{
  _DWORD *v2; // rdi
  char v3; // r14
  NTSTATUS v4; // eax
  unsigned int v5; // ebx
  PVOID *v6; // rax
  ULONG v8; // eax
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  _BYTE v11[4]; // [rsp+30h] [rbp-D0h] BYREF
  ULONG TokenInformationLength; // [rsp+34h] [rbp-CCh] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE hObject; // [rsp+40h] [rbp-C0h] BYREF
  __int64 ThreadInformation; // [rsp+48h] [rbp-B8h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-B0h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+80h] [rbp-80h] BYREF
  _OWORD TokenInformation[8]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE Sid[80]; // [rsp+110h] [rbp+10h] BYREF

  TokenInformationLength = 128;
  *(_WORD *)&IdentifierAuthority.Value[4] = 4096;
  TokenHandle = 0;
  hObject = 0;
  ThreadInformation = 0;
  v11[0] = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  *(_DWORD *)IdentifierAuthority.Value = 0;
  v2 = TokenInformation;
  v3 = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  RtlInitializeSid(Sid, &IdentifierAuthority, 1u);
  *RtlSubAuthoritySid(Sid, 0) = 0x2000;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_fc1af33029303d26f917cfed6bc21a33_Traceguids);
  v4 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xEu, 1u, &TokenHandle);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v4 = NtQueryInformationToken(
           TokenHandle,
           TokenIntegrityLevel,
           TokenInformation,
           TokenInformationLength,
           &TokenInformationLength);
    v5 = v4;
    if ( v4 >= 0 )
      goto LABEL_4;
    if ( v4 != -1073741789 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_66;
      v10 = 15;
      goto LABEL_65;
    }
    v2 = LocalAlloc(0x40u, TokenInformationLength);
    if ( !v2 )
    {
      v5 = -1073741670;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_fc1af33029303d26f917cfed6bc21a33_Traceguids);
      goto LABEL_66;
    }
    v4 = NtQueryInformationToken(TokenHandle, TokenIntegrityLevel, v2, TokenInformationLength, &TokenInformationLength);
    v5 = v4;
    if ( v4 >= 0 )
    {
LABEL_4:
      v4 = RtlSidDominates(Sid, *(_QWORD *)v2, v11);
      v5 = v4;
      if ( v4 < 0 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_66;
        v10 = 18;
      }
      else
      {
        if ( !v11[0] )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_fc1af33029303d26f917cfed6bc21a33_Traceguids);
          v5 = 0;
          if ( TokenHandle )
            CloseHandle(TokenHandle);
LABEL_26:
          *(_QWORD *)this = 0;
          goto LABEL_27;
        }
        v4 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
        v5 = v4;
        if ( v4 < 0 )
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_66;
          v10 = 20;
        }
        else
        {
          ObjectAttributes.Length = 48;
          memset(&ObjectAttributes.RootDirectory, 0, 20);
          v3 = 1;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          v4 = NtDuplicateToken(TokenHandle, 0x8Eu, &ObjectAttributes, 0, TokenImpersonation, &hObject);
          v5 = v4;
          if ( v4 >= 0 )
          {
            memset_0(v2, 0, TokenInformationLength);
            v2[2] = 96;
            *(_QWORD *)v2 = Sid;
            v4 = NtSetInformationToken(hObject, TokenIntegrityLevel, v2, 0x80u);
            v5 = v4;
            if ( v4 >= 0 )
            {
              v4 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &hObject, 8u);
              v5 = v4;
              if ( v4 >= 0 )
              {
                *(_QWORD *)this = TokenHandle;
                v6 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
                  goto LABEL_12;
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_fc1af33029303d26f917cfed6bc21a33_Traceguids);
LABEL_27:
                v6 = (PVOID *)WPP_GLOBAL_Control;
                goto LABEL_12;
              }
              v9 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                goto LABEL_66;
              v10 = 23;
              goto LABEL_65;
            }
            v9 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v10 = 22;
              goto LABEL_65;
            }
LABEL_66:
            if ( TokenHandle )
            {
              if ( v3
                && NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &TokenHandle, 8u) < 0
                && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_fc1af33029303d26f917cfed6bc21a33_Traceguids, v5);
              }
              CloseHandle(TokenHandle);
              *(_QWORD *)this = 0;
              goto LABEL_27;
            }
            goto LABEL_26;
          }
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_66;
          v10 = 21;
        }
      }
    }
    else
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_66;
      v10 = 17;
    }
LABEL_65:
    WPP_SF_d(v9[2], v10, WPP_fc1af33029303d26f917cfed6bc21a33_Traceguids, (unsigned int)v4);
    goto LABEL_66;
  }
  if ( v4 != -1073741700 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_66;
    v10 = 14;
    goto LABEL_65;
  }
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_fc1af33029303d26f917cfed6bc21a33_Traceguids);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  v5 = 0;
LABEL_12:
  if ( hObject )
  {
    CloseHandle(hObject);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v2 && v2 != (_DWORD *)TokenInformation )
  {
    VaultFreeInternal(v2);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
  {
    v8 = RtlNtStatusToDosError(v5);
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_fc1af33029303d26f917cfed6bc21a33_Traceguids, v8);
  }
  return RtlNtStatusToDosError(v5);
}

```

## disassembly

```asm
0x18000eb30  mov     [rsp-8+arg_8], rbx
0x18000eb35  mov     [rsp-8+arg_10], rsi
0x18000eb3a  push    rbp
0x18000eb3b  push    rdi
0x18000eb3c  push    r12
0x18000eb3e  push    r14
0x18000eb40  push    r15
0x18000eb42  lea     rbp, [rsp-70h]
0x18000eb47  sub     rsp, 170h
0x18000eb4e  mov     rax, cs:__security_cookie
0x18000eb55  xor     rax, rsp
0x18000eb58  mov     [rbp+90h+var_30], rax
0x18000eb5c  xorps   xmm0, xmm0
0x18000eb5f  mov     [rsp+190h+TokenInformationLength], 80h
0x18000eb67  xor     r12d, r12d
0x18000eb6a  mov     word ptr [rbp+90h+IdentifierAuthority.Value+4], 1000h
0x18000eb70  mov     rsi, rcx
0x18000eb73  mov     [rsp+190h+TokenHandle], r12
0x18000eb78  lea     rcx, [rbp+90h+Sid]; Sid
0x18000eb7c  mov     [rsp+190h+hObject], r12
0x18000eb81  mov     r8b, 1; SubAuthorityCount
0x18000eb84  mov     [rsp+190h+ThreadInformation], r12
0x18000eb89  lea     rdx, [rbp+90h+IdentifierAuthority]; IdentifierAuthority
0x18000eb8d  mov     [rsp+190h+var_160], r12b
0x18000eb92  movups  xmmword ptr [rsp+190h+ObjectAttributes.Length], xmm0
0x18000eb97  mov     dword ptr [rbp+90h+IdentifierAuthority.Value], r12d
0x18000eb9b  lea     rdi, [rbp+90h+TokenInformation]
0x18000eb9f  movups  xmmword ptr [rsp+190h+ObjectAttributes.ObjectName], xmm0
0x18000eba4  xor     r14b, r14b
0x18000eba7  movups  xmmword ptr [rsp+190h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000ebac  movups  [rbp+90h+TokenInformation], xmm0
0x18000ebb0  movups  [rbp+90h+var_F0], xmm0
0x18000ebb4  movups  [rbp+90h+var_E0], xmm0
0x18000ebb8  movups  [rbp+90h+var_D0], xmm0
0x18000ebbc  movups  [rbp+90h+var_C0], xmm0
0x18000ebc0  movups  [rbp+90h+var_B0], xmm0
0x18000ebc4  movups  [rbp+90h+var_A0], xmm0
0x18000ebc8  movups  [rbp+90h+var_90], xmm0
0x18000ebcc  call    cs:__imp_RtlInitializeSid
0x18000ebd2  xor     edx, edx; SubAuthority
0x18000ebd4  lea     rcx, [rbp+90h+Sid]; Sid
0x18000ebd8  call    cs:__imp_RtlSubAuthoritySid
0x18000ebde  mov     dword ptr [rax], 2000h
0x18000ebe4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ebeb  lea     r15, WPP_GLOBAL_Control
0x18000ebf2  cmp     rcx, r15
0x18000ebf5  jnz     loc_18000EE48
0x18000ebfb  lea     r9, [rsp+190h+TokenHandle]; TokenHandle
0x18000ec00  mov     r8b, 1; OpenAsSelf
0x18000ec03  mov     edx, 0Eh; DesiredAccess
0x18000ec08  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18000ec0f  call    cs:__imp_NtOpenThreadToken
0x18000ec15  mov     ebx, eax
0x18000ec17  test    eax, eax
0x18000ec19  js      loc_18000EE90
0x18000ec1f  mov     r9d, [rsp+190h+TokenInformationLength]; TokenInformationLength
0x18000ec24  lea     rax, [rsp+190h+TokenInformationLength]
0x18000ec29  mov     rcx, [rsp+190h+TokenHandle]; TokenHandle
0x18000ec2e  lea     r8, [rbp+90h+TokenInformation]; TokenInformation
0x18000ec32  mov     edx, 19h; TokenInformationClass
0x18000ec37  mov     [rsp+190h+ReturnLength], rax; ReturnLength
0x18000ec3c  call    cs:__imp_NtQueryInformationToken
0x18000ec42  mov     ebx, eax
0x18000ec44  test    eax, eax
0x18000ec46  js      loc_18000EEF1
0x18000ec4c  mov     rdx, [rdi]
0x18000ec4f  lea     r8, [rsp+190h+var_160]
0x18000ec54  lea     rcx, [rbp+90h+Sid]
0x18000ec58  call    cs:__imp_RtlSidDominates
0x18000ec5e  mov     ebx, eax
0x18000ec60  test    eax, eax
0x18000ec62  js      loc_18000EE6C
0x18000ec68  cmp     [rsp+190h+var_160], r12b
0x18000ec6d  jz      loc_18000EE10
0x18000ec73  mov     r9d, 8; ThreadInformationLength
0x18000ec79  lea     r8, [rsp+190h+ThreadInformation]; ThreadInformation
0x18000ec7e  mov     edx, 5; ThreadInformationClass
0x18000ec83  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18000ec8a  call    cs:__imp_NtSetInformationThread
0x18000ec90  mov     ebx, eax
0x18000ec92  test    eax, eax
0x18000ec94  js      loc_18000EFD3
0x18000ec9a  mov     rcx, [rsp+190h+TokenHandle]; ExistingTokenHandle
0x18000ec9f  lea     rax, [rsp+190h+hObject]
0x18000eca4  xorps   xmm0, xmm0
0x18000eca7  mov     [rsp+190h+NewTokenHandle], rax; NewTokenHandle
0x18000ecac  xor     r9d, r9d; EffectiveOnly
0x18000ecaf  mov     dword ptr [rsp+190h+ReturnLength], 2; TokenType
0x18000ecb7  lea     r8, [rsp+190h+ObjectAttributes]; ObjectAttributes
0x18000ecbc  mov     [rsp+190h+ObjectAttributes.Length], 30h ; '0'
0x18000ecc4  mov     edx, 8Eh; DesiredAccess
0x18000ecc9  mov     [rsp+190h+ObjectAttributes.RootDirectory], r12
0x18000ecce  mov     r14b, 1
0x18000ecd1  mov     [rsp+190h+ObjectAttributes.Attributes], r12d
0x18000ecd6  mov     [rsp+190h+ObjectAttributes.ObjectName], r12
0x18000ecdb  movdqu  xmmword ptr [rsp+190h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000ece1  call    cs:__imp_NtDuplicateToken
0x18000ece7  mov     ebx, eax
0x18000ece9  test    eax, eax
0x18000eceb  js      loc_18000EFEC
0x18000ecf1  mov     r8d, [rsp+190h+TokenInformationLength]; Size
0x18000ecf6  xor     edx, edx; Val
0x18000ecf8  mov     rcx, rdi; void *
0x18000ecfb  call    memset_0
0x18000ed00  lea     rax, [rbp+90h+Sid]
0x18000ed04  mov     dword ptr [rdi+8], 60h ; '`'
0x18000ed0b  mov     [rdi], rax
0x18000ed0e  mov     r9d, 80h; TokenInformationLength
0x18000ed14  mov     rcx, [rsp+190h+hObject]; TokenHandle
0x18000ed19  mov     r8, rdi; TokenInformation
0x18000ed1c  mov     edx, 19h; TokenInformationClass
0x18000ed21  call    cs:__imp_NtSetInformationToken
0x18000ed27  mov     ebx, eax
0x18000ed29  test    eax, eax
0x18000ed2b  js      loc_18000F005
0x18000ed31  mov     r9d, 8; ThreadInformationLength
0x18000ed37  lea     r8, [rsp+190h+hObject]; ThreadInformation
0x18000ed3c  mov     edx, 5; ThreadInformationClass
0x18000ed41  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18000ed48  call    cs:__imp_NtSetInformationThread
0x18000ed4e  mov     ebx, eax
0x18000ed50  test    eax, eax
0x18000ed52  js      loc_18000F01E
0x18000ed58  mov     rax, [rsp+190h+TokenHandle]
0x18000ed5d  mov     [rsi], rax
0x18000ed60  mov     rax, cs:WPP_GLOBAL_Control
0x18000ed67  cmp     rax, r15
0x18000ed6a  jz      short loc_18000ED76
0x18000ed6c  test    byte ptr [rax+1Ch], 8
0x18000ed70  jnz     loc_18000F0B6
0x18000ed76  mov     rcx, [rsp+190h+hObject]; hObject
0x18000ed7b  test    rcx, rcx
0x18000ed7e  jz      short loc_18000ED8D
0x18000ed80  call    cs:__imp_CloseHandle
0x18000ed86  mov     rax, cs:WPP_GLOBAL_Control
0x18000ed8d  test    rdi, rdi
0x18000ed90  jnz     short loc_18000EDF6
0x18000ed92  cmp     rax, r15
0x18000ed95  jnz     short loc_18000EDC7
0x18000ed97  mov     ecx, ebx; Status
0x18000ed99  call    cs:__imp_RtlNtStatusToDosError
0x18000ed9f  mov     rcx, [rbp+90h+var_30]
0x18000eda3  xor     rcx, rsp; StackCookie
0x18000eda6  call    __security_check_cookie
0x18000edab  lea     r11, [rsp+190h+var_20]
0x18000edb3  mov     rbx, [r11+38h]
0x18000edb7  mov     rsi, [r11+40h]
0x18000edbb  mov     rsp, r11
0x18000edbe  pop     r15
0x18000edc0  pop     r14
0x18000edc2  pop     r12
0x18000edc4  pop     rdi
0x18000edc5  pop     rbp
0x18000edc6  retn
0x18000edc7  test    byte ptr [rax+1Ch], 8
0x18000edcb  jz      short loc_18000ED97
0x18000edcd  mov     ecx, ebx; Status
0x18000edcf  call    cs:__imp_RtlNtStatusToDosError
0x18000edd5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eddc  lea     r8, WPP_fc1af33029303d26f917cfed6bc21a33_Traceguids
0x18000ede3  mov     edx, 1Ah
0x18000ede8  mov     r9d, eax
0x18000edeb  mov     rcx, [rcx+10h]
0x18000edef  call    WPP_SF_d
0x18000edf4  jmp     short loc_18000ED97
0x18000edf6  lea     rcx, [rbp+90h+TokenInformation]
0x18000edfa  cmp     rdi, rcx
0x18000edfd  jz      short loc_18000ED92
0x18000edff  mov     rcx, rdi; hMem
0x18000ee02  call    ?VaultFreeInternal@@YAXPEAE@Z; VaultFreeInternal(uchar *)
0x18000ee07  mov     rax, cs:WPP_GLOBAL_Control
0x18000ee0e  jmp     short loc_18000ED92
0x18000ee10  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ee17  cmp     rcx, r15
0x18000ee1a  jz      short loc_18000EE26
0x18000ee1c  test    byte ptr [rcx+1Ch], 8
0x18000ee20  jnz     loc_18000EFB9
0x18000ee26  mov     rcx, [rsp+190h+TokenHandle]; hObject
0x18000ee2b  mov     ebx, r12d
0x18000ee2e  test    rcx, rcx
0x18000ee31  jz      short loc_18000EE39
0x18000ee33  call    cs:__imp_CloseHandle
0x18000ee39  mov     [rsi], r12
0x18000ee3c  mov     rax, cs:WPP_GLOBAL_Control
0x18000ee43  jmp     loc_18000ED76
0x18000ee48  test    byte ptr [rcx+1Ch], 8
0x18000ee4c  jz      loc_18000EBFB
0x18000ee52  mov     rcx, [rcx+10h]
0x18000ee56  lea     r8, WPP_fc1af33029303d26f917cfed6bc21a33_Traceguids
0x18000ee5d  mov     edx, 0Ch
0x18000ee62  call    WPP_SF_
0x18000ee67  jmp     loc_18000EBFB
0x18000ee6c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ee73  cmp     rcx, r15
0x18000ee76  jz      loc_18000F048
0x18000ee7c  test    byte ptr [rcx+1Ch], 2
0x18000ee80  jz      loc_18000F048
0x18000ee86  mov     edx, 12h
0x18000ee8b  jmp     loc_18000F035
0x18000ee90  cmp     eax, 0C000007Ch
0x18000ee95  jnz     short loc_18000EECD
0x18000ee97  mov     rax, cs:WPP_GLOBAL_Control
0x18000ee9e  cmp     rax, r15
0x18000eea1  jz      short loc_18000EEC5
0x18000eea3  test    byte ptr [rax+1Ch], 8
0x18000eea7  jz      short loc_18000EEC5
0x18000eea9  mov     rcx, [rax+10h]
0x18000eead  lea     r8, WPP_fc1af33029303d26f917cfed6bc21a33_Traceguids
0x18000eeb4  mov     edx, 0Dh
0x18000eeb9  call    WPP_SF_
0x18000eebe  mov     rax, cs:WPP_GLOBAL_Control
0x18000eec5  mov     ebx, r12d
0x18000eec8  jmp     loc_18000ED76
0x18000eecd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eed4  cmp     rcx, r15
0x18000eed7  jz      loc_18000F048
0x18000eedd  test    byte ptr [rcx+1Ch], 2
0x18000eee1  jz      loc_18000F048
0x18000eee7  mov     edx, 0Eh
0x18000eeec  jmp     loc_18000F035
0x18000eef1  cmp     eax, 0C0000023h
0x18000eef6  jz      short loc_18000EF1C
0x18000eef8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eeff  cmp     rcx, r15
0x18000ef02  jz      loc_18000F048
0x18000ef08  test    byte ptr [rcx+1Ch], 2
0x18000ef0c  jz      loc_18000F048
0x18000ef12  mov     edx, 0Fh
0x18000ef17  jmp     loc_18000F035
0x18000ef1c  mov     edx, [rsp+190h+TokenInformationLength]; uBytes
0x18000ef20  mov     ecx, 40h ; '@'; uFlags
0x18000ef25  call    cs:__imp_LocalAlloc
0x18000ef2b  mov     rdi, rax
0x18000ef2e  test    rax, rax
0x18000ef31  jnz     short loc_18000EF6C
0x18000ef33  mov     ebx, 0C000009Ah
0x18000ef38  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ef3f  cmp     rcx, r15
0x18000ef42  jz      loc_18000F048
0x18000ef48  test    byte ptr [rcx+1Ch], 2
0x18000ef4c  jz      loc_18000F048
0x18000ef52  mov     rcx, [rcx+10h]
0x18000ef56  lea     r8, WPP_fc1af33029303d26f917cfed6bc21a33_Traceguids
0x18000ef5d  mov     edx, 10h
0x18000ef62  call    WPP_SF_
0x18000ef67  jmp     loc_18000F048
0x18000ef6c  mov     r9d, [rsp+190h+TokenInformationLength]; TokenInformationLength
0x18000ef71  lea     rax, [rsp+190h+TokenInformationLength]
0x18000ef76  mov     rcx, [rsp+190h+TokenHandle]; TokenHandle
0x18000ef7b  mov     r8, rdi; TokenInformation
0x18000ef7e  mov     edx, 19h; TokenInformationClass
0x18000ef83  mov     [rsp+190h+ReturnLength], rax; ReturnLength
0x18000ef88  call    cs:__imp_NtQueryInformationToken
0x18000ef8e  mov     ebx, eax
0x18000ef90  test    eax, eax
0x18000ef92  jns     loc_18000EC4C
0x18000ef98  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ef9f  cmp     rcx, r15
0x18000efa2  jz      loc_18000F048
0x18000efa8  test    byte ptr [rcx+1Ch], 2
0x18000efac  jz      loc_18000F048
0x18000efb2  mov     edx, 11h
0x18000efb7  jmp     short loc_18000F035
0x18000efb9  mov     rcx, [rcx+10h]
0x18000efbd  lea     r8, WPP_fc1af33029303d26f917cfed6bc21a33_Traceguids
0x18000efc4  mov     edx, 13h
0x18000efc9  call    WPP_SF_
0x18000efce  jmp     loc_18000EE26
0x18000efd3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000efda  cmp     rcx, r15
0x18000efdd  jz      short loc_18000F048
0x18000efdf  test    byte ptr [rcx+1Ch], 2
0x18000efe3  jz      short loc_18000F048
0x18000efe5  mov     edx, 14h
0x18000efea  jmp     short loc_18000F035
0x18000efec  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eff3  cmp     rcx, r15
0x18000eff6  jz      short loc_18000F048
0x18000eff8  test    byte ptr [rcx+1Ch], 2
0x18000effc  jz      short loc_18000F048
0x18000effe  mov     edx, 15h
0x18000f003  jmp     short loc_18000F035
0x18000f005  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f00c  cmp     rcx, r15
0x18000f00f  jz      short loc_18000F048
0x18000f011  test    byte ptr [rcx+1Ch], 2
0x18000f015  jz      short loc_18000F048
0x18000f017  mov     edx, 16h
0x18000f01c  jmp     short loc_18000F035
0x18000f01e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f025  cmp     rcx, r15
0x18000f028  jz      short loc_18000F048
0x18000f02a  test    byte ptr [rcx+1Ch], 2
0x18000f02e  jz      short loc_18000F048
0x18000f030  mov     edx, 17h
0x18000f035  mov     rcx, [rcx+10h]
0x18000f039  lea     r8, WPP_fc1af33029303d26f917cfed6bc21a33_Traceguids
0x18000f040  mov     r9d, eax
0x18000f043  call    WPP_SF_d
0x18000f048  cmp     [rsp+190h+TokenHandle], r12
  ... truncated ...
```
