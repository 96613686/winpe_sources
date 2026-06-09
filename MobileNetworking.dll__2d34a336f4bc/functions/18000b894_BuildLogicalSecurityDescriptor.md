# BuildLogicalSecurityDescriptor

- ea: `0x18000b894`
- end: `0x18000be5e`
- name: `BuildLogicalSecurityDescriptor`
- size: `1482`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, PSID pOwner, PSID pGroup, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002200`

## callees

- `0x180004390`
- `0x180004b80`
- `0x180008ff0`
- `0x180009130`
- `0x18000b894`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b933`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b992`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b9db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bbfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b933`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b992`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b9db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bbfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd83`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18000b929`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18000b929`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18000b988`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18000b988`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18000b9d1`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18000b9d1`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000ba42`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000ba42`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18000bb86`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18000bb86`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18000bbf1`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18000bbf1`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAce` at `0x18000bc32`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAce` at `0x18000bc32`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18000bc89`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18000bc89`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18000bcce`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18000bcce`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18000bd79`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18000bd79`

## string_xrefs

- `0x18000bb24`: `BuildLogicalSecurityDescriptor`
- `0x18000bd15`: `BuildLogicalSecurityDescriptor`
- `0x18000bde5`: `BuildLogicalSecurityDescriptor`
- `0x18000be09`: `BuildLogicalSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall BuildLogicalSecurityDescriptor(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        PSID pOwner,
        PSID pGroup,
        _QWORD *a7)
{
  __int64 v7; // r12
  _QWORD *v10; // r13
  DWORD LastError; // eax
  unsigned int v12; // ebx
  PVOID *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  DWORD v16; // edi
  __int64 i; // rbx
  void *v18; // rcx
  DWORD v19; // eax
  unsigned int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // r9
  __int64 j; // rdi
  DWORD v24; // r8d
  void *v25; // r9
  DWORD SecurityDescriptorLength; // eax
  unsigned int v27; // eax
  PSECURITY_DESCRIPTOR v28; // rdi
  DWORD v29; // eax
  PSECURITY_DESCRIPTOR pSelfRelativeSecurityDescriptor; // [rsp+20h] [rbp-30h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+28h] [rbp-28h] BYREF
  __int64 v33; // [rsp+48h] [rbp-8h]
  DWORD dwBufferLength; // [rsp+80h] [rbp+30h] BYREF
  PACL pAcl; // [rsp+88h] [rbp+38h] BYREF

  v7 = *(_QWORD *)&g_pSecurity;
  pAcl = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v33 = 0;
  pSelfRelativeSecurityDescriptor = 0;
  dwBufferLength = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_fd6184a389643c6486807174a58ed414_Traceguids);
  v10 = a7;
  *a7 = 0;
  if ( InitializeSecurityDescriptor(pSecurityDescriptor, 1u) || (LastError = GetLastError(), (v12 = LastError) == 0) )
  {
    if ( !SetSecurityDescriptorOwner(pSecurityDescriptor, pOwner, 0) )
    {
      LastError = GetLastError();
      v12 = LastError;
      if ( LastError )
      {
        v13 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          return v12;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          goto LABEL_92;
        v14 = 51;
        goto LABEL_9;
      }
    }
    if ( !SetSecurityDescriptorGroup(pSecurityDescriptor, pGroup, 0) )
    {
      LastError = GetLastError();
      v12 = LastError;
      if ( LastError )
      {
        v13 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          return v12;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          goto LABEL_92;
        v14 = 52;
        goto LABEL_9;
      }
    }
    v16 = 8;
    for ( i = 0; (unsigned int)i < a3; i = (unsigned int)(i + 1) )
    {
      v15 = *(unsigned int *)(a4 + 12 * i + 4);
      if ( (unsigned int)v15 >= 0xA )
      {
        v12 = 87;
        v13 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          return v12;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v14 = 53;
          goto LABEL_10;
        }
        goto LABEL_92;
      }
      v18 = *(void **)(v7 + 8 * v15);
      if ( !v18 )
      {
        v12 = 87;
        v13 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          return v12;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v14 = 54;
          goto LABEL_10;
        }
        goto LABEL_92;
      }
      v19 = GetLengthSid(v18) + 8;
      if ( v19 < 8 )
      {
        v15 = 534;
        v12 = 534;
        v13 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          return v12;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v14 = 55;
          goto LABEL_10;
        }
        goto LABEL_92;
      }
      v16 += v19;
      if ( v16 < v19 )
      {
        v15 = 534;
        v12 = 534;
        v13 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          return v12;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v14 = 56;
          goto LABEL_10;
        }
        goto LABEL_92;
      }
    }
    v20 = AllocateMemory(v16, &pAcl, (int)"BuildLogicalSecurityDescriptor", 17);
    v12 = v20;
    if ( v20 )
    {
      v13 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_89;
      v21 = 57;
      goto LABEL_44;
    }
    if ( !InitializeAcl(pAcl, v16, 2u) )
    {
      v20 = GetLastError();
      v12 = v20;
      if ( v20 )
      {
        v13 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          goto LABEL_89;
        v21 = 58;
LABEL_44:
        v22 = v20;
LABEL_45:
        WPP_SF_L(v13[2], v21, WPP_fd6184a389643c6486807174a58ed414_Traceguids, v22);
LABEL_88:
        v13 = (PVOID *)WPP_GLOBAL_Control;
LABEL_89:
        if ( !pAcl )
          goto LABEL_92;
        FreeMemory(&pAcl, "BuildLogicalSecurityDescriptor", 617);
        goto LABEL_91;
      }
    }
    for ( j = 0; (unsigned int)j < a3; j = (unsigned int)(j + 1) )
    {
      v24 = *(_DWORD *)(a4 + 12 * j + 8);
      v25 = *(void **)(v7 + 8LL * *(unsigned int *)(a4 + 12 * j + 4));
      if ( *(_BYTE *)(a4 + 12 * j) )
      {
        if ( !AddAccessDeniedAce(pAcl, 2u, v24, v25) )
        {
          v20 = GetLastError();
          v12 = v20;
          if ( v20 )
          {
            v13 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              v21 = 60;
              goto LABEL_44;
            }
            goto LABEL_89;
          }
        }
      }
      else if ( !AddAccessAllowedAce(pAcl, 2u, v24, v25) )
      {
        v20 = GetLastError();
        v12 = v20;
        if ( v20 )
        {
          v13 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v21 = 59;
            goto LABEL_44;
          }
          goto LABEL_89;
        }
      }
    }
    if ( !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, pAcl, 0) )
    {
      v20 = GetLastError();
      v12 = v20;
      if ( v20 )
      {
        v13 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v21 = 61;
          goto LABEL_44;
        }
        goto LABEL_89;
      }
    }
    SecurityDescriptorLength = GetSecurityDescriptorLength(pSecurityDescriptor);
    dwBufferLength = SecurityDescriptorLength;
    if ( SecurityDescriptorLength < 0x28 )
    {
      v12 = 5023;
      v13 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v21 = 62;
        v22 = 5023;
        goto LABEL_45;
      }
      goto LABEL_89;
    }
    v27 = AllocateMemory(
            SecurityDescriptorLength,
            &pSelfRelativeSecurityDescriptor,
            (int)"BuildLogicalSecurityDescriptor",
            82);
    v12 = v27;
    if ( v27 )
    {
      v13 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        v28 = pSelfRelativeSecurityDescriptor;
LABEL_86:
        if ( !v28 )
          goto LABEL_89;
        FreeMemory(&pSelfRelativeSecurityDescriptor, "BuildLogicalSecurityDescriptor", 612);
        goto LABEL_88;
      }
      WPP_SF_L(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, WPP_fd6184a389643c6486807174a58ed414_Traceguids, v27);
      v28 = pSelfRelativeSecurityDescriptor;
    }
    else
    {
      v28 = pSelfRelativeSecurityDescriptor;
      if ( MakeSelfRelativeSD(pSecurityDescriptor, pSelfRelativeSecurityDescriptor, &dwBufferLength)
        || (v29 = GetLastError(), (v12 = v29) == 0) )
      {
        *v10 = v28;
        v28 = 0;
        pSelfRelativeSecurityDescriptor = 0;
      }
      else
      {
        v13 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          goto LABEL_86;
        WPP_SF_L(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, WPP_fd6184a389643c6486807174a58ed414_Traceguids, v29);
      }
    }
    v13 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_86;
  }
  v13 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v12;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v14 = 50;
LABEL_9:
    v15 = LastError;
LABEL_10:
    WPP_SF_L(v13[2], v14, WPP_fd6184a389643c6486807174a58ed414_Traceguids, v15);
LABEL_91:
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_92:
  if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 8) != 0 )
    WPP_SF_L(v13[2], 65, WPP_fd6184a389643c6486807174a58ed414_Traceguids, v12);
  return v12;
}

```

## disassembly

```asm
0x18000b894  mov     rax, rsp
0x18000b897  mov     [rax+18h], rbx
0x18000b89b  mov     [rax+20h], rsi
0x18000b89f  mov     [rax+10h], rdx
0x18000b8a3  mov     [rax+8], ecx
0x18000b8a6  push    rbp
0x18000b8a7  push    rdi
0x18000b8a8  push    r12
0x18000b8aa  push    r13
0x18000b8ac  push    r14
0x18000b8ae  mov     rbp, rsp
0x18000b8b1  sub     rsp, 50h
0x18000b8b5  mov     r12, cs:g_pSecurity
0x18000b8bc  xorps   xmm0, xmm0
0x18000b8bf  xor     eax, eax
0x18000b8c1  mov     [rbp+pAcl], 0
0x18000b8c9  movups  [rbp+pSecurityDescriptor], xmm0
0x18000b8cd  mov     [rbp+var_8], rax
0x18000b8d1  mov     rsi, r9
0x18000b8d4  movups  [rbp+var_18], xmm0
0x18000b8d8  mov     [rbp+pSelfRelativeSecurityDescriptor], rax
0x18000b8dc  mov     r14d, r8d
0x18000b8df  mov     [rbp+dwBufferLength], 0
0x18000b8e6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b8ed  lea     rax, WPP_GLOBAL_Control
0x18000b8f4  cmp     rcx, rax
0x18000b8f7  jz      short loc_18000B914
0x18000b8f9  test    byte ptr [rcx+1Ch], 8
0x18000b8fd  jz      short loc_18000B914
0x18000b8ff  mov     rcx, [rcx+10h]
0x18000b903  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x18000b90a  mov     edx, 31h ; '1'
0x18000b90f  call    WPP_SF_
0x18000b914  mov     r13, [rbp+arg_30]
0x18000b918  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x18000b91c  mov     edx, 1; dwRevision
0x18000b921  mov     qword ptr [r13+0], 0
0x18000b929  call    cs:__imp_InitializeSecurityDescriptor
0x18000b92f  test    eax, eax
0x18000b931  jnz     short loc_18000B97D
0x18000b933  call    cs:__imp_GetLastError
0x18000b939  mov     ebx, eax
0x18000b93b  test    eax, eax
0x18000b93d  jz      short loc_18000B97D
0x18000b93f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b946  lea     rsi, WPP_GLOBAL_Control
0x18000b94d  cmp     rcx, rsi
0x18000b950  jz      loc_18000BE43
0x18000b956  test    byte ptr [rcx+1Ch], 4
0x18000b95a  jz      loc_18000BE20
0x18000b960  mov     edx, 32h ; '2'
0x18000b965  mov     r9d, eax
0x18000b968  mov     rcx, [rcx+10h]
0x18000b96c  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x18000b973  call    WPP_SF_L
0x18000b978  jmp     loc_18000BE19
0x18000b97d  mov     rdx, [rbp+pOwner]; pOwner
0x18000b981  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x18000b985  xor     r8d, r8d; bOwnerDefaulted
0x18000b988  call    cs:__imp_SetSecurityDescriptorOwner
0x18000b98e  test    eax, eax
0x18000b990  jnz     short loc_18000B9C6
0x18000b992  call    cs:__imp_GetLastError
0x18000b998  mov     ebx, eax
0x18000b99a  test    eax, eax
0x18000b99c  jz      short loc_18000B9C6
0x18000b99e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b9a5  lea     rsi, WPP_GLOBAL_Control
0x18000b9ac  cmp     rcx, rsi
0x18000b9af  jz      loc_18000BE43
0x18000b9b5  test    byte ptr [rcx+1Ch], 4
0x18000b9b9  jz      loc_18000BE20
0x18000b9bf  mov     edx, 33h ; '3'
0x18000b9c4  jmp     short loc_18000B965
0x18000b9c6  mov     rdx, [rbp+pGroup]; pGroup
0x18000b9ca  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x18000b9ce  xor     r8d, r8d; bGroupDefaulted
0x18000b9d1  call    cs:__imp_SetSecurityDescriptorGroup
0x18000b9d7  test    eax, eax
0x18000b9d9  jnz     short loc_18000BA12
0x18000b9db  call    cs:__imp_GetLastError
0x18000b9e1  mov     ebx, eax
0x18000b9e3  test    eax, eax
0x18000b9e5  jz      short loc_18000BA12
0x18000b9e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b9ee  lea     rsi, WPP_GLOBAL_Control
0x18000b9f5  cmp     rcx, rsi
0x18000b9f8  jz      loc_18000BE43
0x18000b9fe  test    byte ptr [rcx+1Ch], 4
0x18000ba02  jz      loc_18000BE20
0x18000ba08  mov     edx, 34h ; '4'
0x18000ba0d  jmp     loc_18000B965
0x18000ba12  mov     edi, 8
0x18000ba17  xor     ebx, ebx
0x18000ba19  cmp     ebx, r14d
0x18000ba1c  jnb     loc_18000BB1E
0x18000ba22  lea     rcx, [rbx+rbx*2]
0x18000ba26  mov     r9d, [rsi+rcx*4+4]
0x18000ba2b  cmp     r9d, 0Ah
0x18000ba2f  jnb     loc_18000BAF0
0x18000ba35  mov     rcx, [r12+r9*8]; pSid
0x18000ba39  test    rcx, rcx
0x18000ba3c  jz      loc_18000BAC2
0x18000ba42  call    cs:__imp_GetLengthSid
0x18000ba48  add     eax, 8
0x18000ba4b  cmp     eax, 8
0x18000ba4e  jb      short loc_18000BA8E
0x18000ba50  add     edi, eax
0x18000ba52  cmp     edi, eax
0x18000ba54  jb      short loc_18000BA5A
0x18000ba56  inc     ebx
0x18000ba58  jmp     short loc_18000BA19
0x18000ba5a  mov     r9d, 216h
0x18000ba60  mov     ebx, r9d
0x18000ba63  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ba6a  lea     rsi, WPP_GLOBAL_Control
0x18000ba71  cmp     rcx, rsi
0x18000ba74  jz      loc_18000BE43
0x18000ba7a  test    byte ptr [rcx+1Ch], 4
0x18000ba7e  jz      loc_18000BE20
0x18000ba84  mov     edx, 38h ; '8'
0x18000ba89  jmp     loc_18000B968
0x18000ba8e  mov     r9d, 216h
0x18000ba94  mov     ebx, r9d
0x18000ba97  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ba9e  lea     rsi, WPP_GLOBAL_Control
0x18000baa5  cmp     rcx, rsi
0x18000baa8  jz      loc_18000BE43
0x18000baae  test    byte ptr [rcx+1Ch], 4
0x18000bab2  jz      loc_18000BE20
0x18000bab8  mov     edx, 37h ; '7'
0x18000babd  jmp     loc_18000B968
0x18000bac2  mov     ebx, 57h ; 'W'
0x18000bac7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bace  lea     rsi, WPP_GLOBAL_Control
0x18000bad5  cmp     rcx, rsi
0x18000bad8  jz      loc_18000BE43
0x18000bade  test    byte ptr [rcx+1Ch], 4
0x18000bae2  jz      loc_18000BE20
0x18000bae8  lea     edx, [rbx-21h]
0x18000baeb  jmp     loc_18000B968
0x18000baf0  mov     ebx, 57h ; 'W'
0x18000baf5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bafc  lea     rsi, WPP_GLOBAL_Control
0x18000bb03  cmp     rcx, rsi
0x18000bb06  jz      loc_18000BE43
0x18000bb0c  test    byte ptr [rcx+1Ch], 4
0x18000bb10  jz      loc_18000BE20
0x18000bb16  lea     edx, [rbx-22h]
0x18000bb19  jmp     loc_18000B968
0x18000bb1e  mov     r9d, 211h
0x18000bb24  lea     r8, aBuildlogicalse; "BuildLogicalSecurityDescriptor"
0x18000bb2b  lea     rdx, [rbp+pAcl]
0x18000bb2f  mov     ecx, edi; dwBytes
0x18000bb31  call    AllocateMemory
0x18000bb36  mov     ebx, eax
0x18000bb38  test    eax, eax
0x18000bb3a  jz      short loc_18000BB7A
0x18000bb3c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bb43  lea     rsi, WPP_GLOBAL_Control
0x18000bb4a  cmp     rcx, rsi
0x18000bb4d  jz      loc_18000BDFC
0x18000bb53  test    byte ptr [rcx+1Ch], 4
0x18000bb57  jz      loc_18000BDFC
0x18000bb5d  mov     edx, 39h ; '9'
0x18000bb62  mov     r9d, eax
0x18000bb65  mov     rcx, [rcx+10h]
0x18000bb69  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x18000bb70  call    WPP_SF_L
0x18000bb75  jmp     loc_18000BDF5
0x18000bb7a  mov     rcx, [rbp+pAcl]; pAcl
0x18000bb7e  mov     r8d, 2; dwAclRevision
0x18000bb84  mov     edx, edi; nAclLength
0x18000bb86  call    cs:__imp_InitializeAcl
0x18000bb8c  test    eax, eax
0x18000bb8e  jnz     short loc_18000BBC4
0x18000bb90  call    cs:__imp_GetLastError
0x18000bb96  mov     ebx, eax
0x18000bb98  test    eax, eax
0x18000bb9a  jz      short loc_18000BBC4
0x18000bb9c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bba3  lea     rsi, WPP_GLOBAL_Control
0x18000bbaa  cmp     rcx, rsi
0x18000bbad  jz      loc_18000BDFC
0x18000bbb3  test    byte ptr [rcx+1Ch], 4
0x18000bbb7  jz      loc_18000BDFC
0x18000bbbd  mov     edx, 3Ah ; ':'
0x18000bbc2  jmp     short loc_18000BB62
0x18000bbc4  xor     edi, edi
0x18000bbc6  cmp     edi, r14d
0x18000bbc9  jnb     loc_18000BC7A
0x18000bbcf  mov     rcx, [rbp+pAcl]; pAcl
0x18000bbd3  lea     r8, [rdi+rdi*2]
0x18000bbd7  mov     r9d, [rsi+r8*4+4]
0x18000bbdc  mov     edx, 2; dwAceRevision
0x18000bbe1  cmp     byte ptr [rsi+r8*4], 0
0x18000bbe6  mov     r8d, [rsi+r8*4+8]; AccessMask
0x18000bbeb  mov     r9, [r12+r9*8]; pSid
0x18000bbef  jnz     short loc_18000BC32
0x18000bbf1  call    cs:__imp_AddAccessAllowedAce
0x18000bbf7  test    eax, eax
0x18000bbf9  jnz     short loc_18000BC48
0x18000bbfb  call    cs:__imp_GetLastError
0x18000bc01  mov     ebx, eax
0x18000bc03  test    eax, eax
0x18000bc05  jz      short loc_18000BC48
0x18000bc07  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bc0e  lea     rsi, WPP_GLOBAL_Control
0x18000bc15  cmp     rcx, rsi
0x18000bc18  jz      loc_18000BDFC
0x18000bc1e  test    byte ptr [rcx+1Ch], 4
0x18000bc22  jz      loc_18000BDFC
0x18000bc28  mov     edx, 3Bh ; ';'
0x18000bc2d  jmp     loc_18000BB62
0x18000bc32  call    cs:__imp_AddAccessDeniedAce
0x18000bc38  test    eax, eax
0x18000bc3a  jnz     short loc_18000BC48
0x18000bc3c  call    cs:__imp_GetLastError
0x18000bc42  mov     ebx, eax
0x18000bc44  test    eax, eax
0x18000bc46  jnz     short loc_18000BC4F
0x18000bc48  inc     edi
0x18000bc4a  jmp     loc_18000BBC6
0x18000bc4f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bc56  lea     rsi, WPP_GLOBAL_Control
0x18000bc5d  cmp     rcx, rsi
0x18000bc60  jz      loc_18000BDFC
0x18000bc66  test    byte ptr [rcx+1Ch], 4
0x18000bc6a  jz      loc_18000BDFC
0x18000bc70  mov     edx, 3Ch ; '<'
0x18000bc75  jmp     loc_18000BB62
0x18000bc7a  mov     r8, [rbp+pAcl]; pDacl
0x18000bc7e  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x18000bc82  xor     r9d, r9d; bDaclDefaulted
0x18000bc85  lea     edx, [r9+1]; bDaclPresent
0x18000bc89  call    cs:__imp_SetSecurityDescriptorDacl
0x18000bc8f  test    eax, eax
0x18000bc91  jnz     short loc_18000BCCA
0x18000bc93  call    cs:__imp_GetLastError
0x18000bc99  mov     ebx, eax
0x18000bc9b  test    eax, eax
0x18000bc9d  jz      short loc_18000BCCA
0x18000bc9f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bca6  lea     rsi, WPP_GLOBAL_Control
0x18000bcad  cmp     rcx, rsi
0x18000bcb0  jz      loc_18000BDFC
0x18000bcb6  test    byte ptr [rcx+1Ch], 4
0x18000bcba  jz      loc_18000BDFC
0x18000bcc0  mov     edx, 3Dh ; '='
0x18000bcc5  jmp     loc_18000BB62
0x18000bcca  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x18000bcce  call    cs:__imp_GetSecurityDescriptorLength
0x18000bcd4  mov     [rbp+dwBufferLength], eax
0x18000bcd7  cmp     eax, 28h ; '('
0x18000bcda  jnb     short loc_18000BD0F
0x18000bcdc  mov     ebx, 139Fh
0x18000bce1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bce8  lea     rsi, WPP_GLOBAL_Control
0x18000bcef  cmp     rcx, rsi
0x18000bcf2  jz      loc_18000BDFC
0x18000bcf8  test    byte ptr [rcx+1Ch], 4
0x18000bcfc  jz      loc_18000BDFC
0x18000bd02  mov     edx, 3Eh ; '>'
0x18000bd07  mov     r9d, ebx
0x18000bd0a  jmp     loc_18000BB65
0x18000bd0f  mov     r9d, 252h
0x18000bd15  lea     r8, aBuildlogicalse; "BuildLogicalSecurityDescriptor"
0x18000bd1c  lea     rdx, [rbp+pSelfRelativeSecurityDescriptor]
0x18000bd20  mov     ecx, eax; dwBytes
0x18000bd22  call    AllocateMemory
0x18000bd27  mov     ebx, eax
0x18000bd29  test    eax, eax
0x18000bd2b  jz      short loc_18000BD6A
0x18000bd2d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bd34  lea     rsi, WPP_GLOBAL_Control
0x18000bd3b  cmp     rcx, rsi
0x18000bd3e  jz      short loc_18000BD64
0x18000bd40  test    byte ptr [rcx+1Ch], 4
0x18000bd44  jz      short loc_18000BD64
0x18000bd46  mov     rcx, [rcx+10h]
0x18000bd4a  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x18000bd51  mov     edx, 3Fh ; '?'
0x18000bd56  mov     r9d, eax
0x18000bd59  call    WPP_SF_L
0x18000bd5e  mov     rdi, [rbp+pSelfRelativeSecurityDescriptor]
0x18000bd62  jmp     short loc_18000BDD3
0x18000bd64  mov     rdi, [rbp+pSelfRelativeSecurityDescriptor]
0x18000bd68  jmp     short loc_18000BDDA
0x18000bd6a  mov     rdi, [rbp+pSelfRelativeSecurityDescriptor]
0x18000bd6e  lea     r8, [rbp+dwBufferLength]; lpdwBufferLength
0x18000bd72  mov     rdx, rdi; pSelfRelativeSecurityDescriptor
0x18000bd75  lea     rcx, [rbp+pSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x18000bd79  call    cs:__imp_MakeSelfRelativeSD
0x18000bd7f  test    eax, eax
0x18000bd81  jnz     short loc_18000BDC2
0x18000bd83  call    cs:__imp_GetLastError
0x18000bd89  mov     ebx, eax
0x18000bd8b  test    eax, eax
0x18000bd8d  jz      short loc_18000BDC2
0x18000bd8f  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
