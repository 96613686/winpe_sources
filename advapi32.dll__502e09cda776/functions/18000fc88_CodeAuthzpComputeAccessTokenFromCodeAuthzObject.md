# __CodeAuthzpComputeAccessTokenFromCodeAuthzObject

- ea: `0x18000fc88`
- end: `0x18001076f`
- name: `__CodeAuthzpComputeAccessTokenFromCodeAuthzObject`
- size: `2791`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000f840`

## callees

- `0x18000f388`
- `0x18000f5ac`
- `0x18000fb50`
- `0x18000fc88`
- `0x1800115f0`
- `0x1800117d0`
- `0x180011dd0`
- `0x1800720b0`

## import_xrefs

- `ntdll!NtClose` at `0x18000ffdc`
- `ntdll!NtClose` at `0x1800102cf`
- `ntdll!NtClose` at `0x180010378`
- `ntdll!NtClose` at `0x1800106d0`
- `ntdll!NtClose` at `0x18000ffdc`
- `ntdll!NtClose` at `0x1800102cf`
- `ntdll!NtClose` at `0x180010378`
- `ntdll!NtClose` at `0x1800106d0`
- `ntdll!NtOpenThreadToken` at `0x180010038`
- `ntdll!NtOpenThreadToken` at `0x180010038`
- `ntdll!NtOpenProcessToken` at `0x18001005a`
- `ntdll!NtOpenProcessToken` at `0x18001005a`
- `ntdll!RtlEqualSid` at `0x1800106b3`
- `ntdll!RtlEqualSid` at `0x1800106b3`
- `ntdll!NtSetInformationToken` at `0x180010362`
- `ntdll!NtSetInformationToken` at `0x180010362`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180010212`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18001040b`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180010533`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180010212`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18001040b`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180010533`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180010238`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180010431`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180010559`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180010238`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180010431`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180010559`
- `ntdll!NtDuplicateToken` at `0x1800102aa`
- `ntdll!NtDuplicateToken` at `0x18001048d`
- `ntdll!NtDuplicateToken` at `0x1800104c3`
- `ntdll!NtDuplicateToken` at `0x18001069c`
- `ntdll!NtDuplicateToken` at `0x1800102aa`
- `ntdll!NtDuplicateToken` at `0x18001048d`
- `ntdll!NtDuplicateToken` at `0x1800104c3`
- `ntdll!NtDuplicateToken` at `0x18001069c`
- `ntdll!NtCompareTokens` at `0x180010647`
- `ntdll!NtCompareTokens` at `0x180010647`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180010193`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800101e1`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180010193`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800101e1`
- `ntdll!RtlFreeSid` at `0x1800106e1`
- `ntdll!RtlFreeSid` at `0x1800106f2`
- `ntdll!RtlFreeSid` at `0x1800106e1`
- `ntdll!RtlFreeSid` at `0x1800106f2`
- `ntdll!RtlFreeHeap` at `0x18000ff39`
- `ntdll!RtlFreeHeap` at `0x18001039c`
- `ntdll!RtlFreeHeap` at `0x180010716`
- `ntdll!RtlFreeHeap` at `0x180010739`
- `ntdll!RtlFreeHeap` at `0x18000ff39`
- `ntdll!RtlFreeHeap` at `0x18001039c`
- `ntdll!RtlFreeHeap` at `0x180010716`
- `ntdll!RtlFreeHeap` at `0x180010739`
- `ntdll!NtQueryInformationToken` at `0x18000fe1a`
- `ntdll!NtQueryInformationToken` at `0x18000fe1a`
- `api-ms-win-security-base-l1-1-0!CreateRestrictedToken` at `0x18001013b`
- `api-ms-win-security-base-l1-1-0!CreateRestrictedToken` at `0x18001013b`

## pseudocode

```c
__int64 __fastcall _CodeAuthzpComputeAccessTokenFromCodeAuthzObject(
        __int64 a1,
        HANDLE a2,
        HANDLE *a3,
        char a4,
        int *a5,
        __int64 a6)
{
  PSID *v6; // r12
  PHANDLE v7; // rbx
  PLUID_AND_ATTRIBUTES v9; // r13
  int v10; // r13d
  int v11; // ecx
  int v12; // ecx
  bool v13; // r8
  int v14; // edi
  DWORD v15; // eax
  struct _LUID_AND_ATTRIBUTES *v16; // rcx
  int v17; // r8d
  PSID *v18; // rbx
  struct _SID_AND_ATTRIBUTES *SidsToRestrict; // r9
  DWORD RestrictedSidCount; // ecx
  DWORD v21; // r8d
  DWORD v22; // eax
  char v23; // r15
  NTSTATUS v24; // ebx
  NTSTATUS v26; // eax
  char v27; // al
  NTSTATUS v28; // eax
  void *v29; // rcx
  PSID v30; // rsi
  HANDLE v31; // rax
  HANDLE *v32; // r14
  char v33; // al
  char v34; // [rsp+60h] [rbp-A0h]
  unsigned __int8 Equal[4]; // [rsp+64h] [rbp-9Ch] BYREF
  PVOID P; // [rsp+68h] [rbp-98h]
  DWORD TokenInformation; // [rsp+70h] [rbp-90h] BYREF
  PLUID_AND_ATTRIBUTES PrivilegesToDelete; // [rsp+78h] [rbp-88h]
  HANDLE TokenHandle; // [rsp+80h] [rbp-80h] BYREF
  HANDLE ExistingTokenHandle; // [rsp+88h] [rbp-78h] BYREF
  DWORD DisableSidCount; // [rsp+90h] [rbp-70h] BYREF
  int v42; // [rsp+94h] [rbp-6Ch]
  HANDLE v43; // [rsp+98h] [rbp-68h] BYREF
  PHANDLE v44; // [rsp+A0h] [rbp-60h]
  DWORD v45; // [rsp+A8h] [rbp-58h] BYREF
  DWORD v46; // [rsp+ACh] [rbp-54h] BYREF
  int v47; // [rsp+B0h] [rbp-50h]
  int v48; // [rsp+B4h] [rbp-4Ch]
  int v49; // [rsp+B8h] [rbp-48h]
  int v50; // [rsp+BCh] [rbp-44h]
  PSID_AND_ATTRIBUTES SidsToDisable; // [rsp+C0h] [rbp-40h] BYREF
  PVOID v52; // [rsp+C8h] [rbp-38h]
  ULONG ReturnLength; // [rsp+D0h] [rbp-30h] BYREF
  struct _LUID_AND_ATTRIBUTES *v54; // [rsp+D8h] [rbp-28h] BYREF
  PSID Sid; // [rsp+E0h] [rbp-20h] BYREF
  PSID Sid2; // [rsp+E8h] [rbp-18h] BYREF
  struct _OBJECT_ATTRIBUTES v57; // [rsp+F0h] [rbp-10h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v59; // [rsp+140h] [rbp+40h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+148h] [rbp+48h] BYREF
  int *v61; // [rsp+178h] [rbp+78h]
  __int64 v62; // [rsp+180h] [rbp+80h] BYREF
  int v63; // [rsp+188h] [rbp+88h]
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+190h] [rbp+90h] BYREF

  v6 = 0;
  v61 = a5;
  v52 = 0;
  v43 = 0;
  v7 = a3;
  v62 = 0;
  v63 = 0;
  v9 = 0;
  v59 = 0;
  v34 = a4;
  v44 = a3;
  TokenHandle = a2;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  ExistingTokenHandle = 0;
  Sid = 0;
  Sid2 = 0;
  DisableSidCount = 0;
  SidsToDisable = 0;
  v46 = 0;
  v45 = 0;
  PrivilegesToDelete = 0;
  v54 = 0;
  memset(&v57, 0, sizeof(v57));
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  if ( !a1 )
  {
    v24 = -1073741585;
    goto LABEL_55;
  }
  if ( !a3 || !a6 )
  {
    v24 = -1073741819;
LABEL_55:
    if ( a2 )
      NtClose(a2);
    return (unsigned int)v24;
  }
  v42 = 0;
  v48 = 0;
  v49 = 0;
  if ( a2 )
  {
    v50 = 1;
  }
  else
  {
    v50 = 0;
    v14 = 0;
    v26 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x2000Au, 1u, &TokenHandle);
    v24 = v26;
    if ( v26 == -1073741700 )
    {
      v26 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0x2000Au, &TokenHandle);
      v24 = v26;
    }
    if ( v26 < 0 )
      goto LABEL_35;
    a4 = v34;
    v7 = v44;
    a2 = TokenHandle;
  }
  v10 = *(_DWORD *)(a6 + 552);
  v11 = *(_DWORD *)(a1 + 32);
  LOBYTE(v6) = *(_DWORD *)(a1 + 16) != 0;
  if ( (v10 & 0xFF000000) != 0 )
    v11 &= 0xFFFFFFu;
  v12 = v10 | v11;
  v13 = (a4 & 4) == 0 && (v12 & 0x20000) == 0;
  if ( !v13 )
    LODWORD(v6) = (unsigned int)v6 | 2;
  v14 = v12 | 0x20000;
  if ( v13 )
    v14 = v12;
  v47 = IsSystemProcessOrService(a2);
  P = (PVOID)CodeAuthzpGetTokenInformation(TokenHandle, TokenUser);
  if ( !P )
  {
    v24 = -1073741823;
    v6 = 0;
LABEL_34:
    v9 = PrivilegesToDelete;
LABEL_35:
    v23 = v34;
    goto LABEL_36;
  }
  TokenInformation = 0;
  ReturnLength = 0;
  if ( NtQueryInformationToken(TokenHandle, TokenSandBoxInert, &TokenInformation, 4u, &ReturnLength) >= 0
    && TokenInformation )
  {
    v23 = v34;
    if ( (v34 & 1) != 0 )
    {
      *v7 = 0;
      v24 = 0;
      goto LABEL_31;
    }
    v62 = 12;
    LOWORD(v63) = 1;
    v6 = (PSID *)P;
    v24 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
    if ( v24 < 0 )
      goto LABEL_32;
    v24 = RtlSetOwnerSecurityDescriptor(SecurityDescriptor, *(PSID *)P, 0);
    if ( v24 < 0 )
      goto LABEL_32;
    v32 = v44;
    v57.SecurityDescriptor = SecurityDescriptor;
    v57.SecurityQualityOfService = &v62;
    v57.Length = 48;
    v57.RootDirectory = 0;
    v57.Attributes = 2;
    v57.ObjectName = 0;
LABEL_100:
    v24 = NtDuplicateToken(TokenHandle, 0xF01FFu, &v57, 0, TokenPrimary, v32);
    goto LABEL_32;
  }
  if ( !v47 && *(_DWORD *)(a1 + 12) )
  {
    v24 = -1;
LABEL_104:
    v6 = (PSID *)P;
    goto LABEL_34;
  }
  if ( *(_DWORD *)(a1 + 56) )
  {
    if ( !(unsigned __int8)CodeAuthzpInvertPrivs(
                             (_DWORD)TokenHandle,
                             *(_DWORD *)(a1 + 64),
                             *(_QWORD *)(a1 + 72),
                             (unsigned int)&v45,
                             (__int64)&v54) )
    {
      v9 = v54;
      v24 = -1073741823;
      v6 = (PSID *)P;
      goto LABEL_35;
    }
    v15 = v45;
    v16 = v54;
    v49 = 1;
  }
  else
  {
    v15 = *(_DWORD *)(a1 + 64);
    v16 = *(struct _LUID_AND_ATTRIBUTES **)(a1 + 72);
  }
  v17 = *(_DWORD *)(a1 + 44);
  PrivilegesToDelete = v16;
  TokenInformation = v15;
  if ( *(_DWORD *)(a1 + 36) )
  {
    v18 = (PSID *)P;
    v27 = CodeAuthzpInvertAndAddSids(TokenHandle, *(PSID *)P, 0, 0, (__int64)&DisableSidCount, (__int64)&SidsToDisable);
  }
  else
  {
    if ( !v17 || !*(_QWORD *)(a1 + 48) )
    {
      v42 = 0;
      v18 = (PSID *)P;
      goto LABEL_20;
    }
    v18 = (PSID *)P;
    v27 = CodeAuthzpExpandWildcardList(TokenHandle, *(PSID *)P, (__int64)&DisableSidCount, (__int64)&SidsToDisable);
  }
  if ( !v27 )
    goto LABEL_103;
  v42 = 1;
LABEL_20:
  if ( !*(_DWORD *)(a1 + 84) )
  {
    SidsToRestrict = *(struct _SID_AND_ATTRIBUTES **)(a1 + 104);
    RestrictedSidCount = *(_DWORD *)(a1 + 100);
    v52 = SidsToRestrict;
    goto LABEL_22;
  }
  v33 = CodeAuthzpInvertAndAddSids(
          TokenHandle,
          *v18,
          *(_DWORD *)(a1 + 100),
          *(_QWORD *)(a1 + 104),
          (__int64)&v46,
          (__int64)&v43);
  SidsToRestrict = (struct _SID_AND_ATTRIBUTES *)v43;
  v52 = v43;
  if ( !v33 )
  {
LABEL_103:
    v24 = -1073741823;
    goto LABEL_104;
  }
  RestrictedSidCount = v46;
  v48 = 1;
LABEL_22:
  if ( v47 )
  {
    v22 = TokenInformation;
    v21 = DisableSidCount;
  }
  else
  {
    if ( (v10 & 0x1000) != 0
      && *(_WORD *)(a6 + 32)
      && (*(_DWORD *)(a6 + 16) || *(_DWORD *)(a6 + 20) || *(_DWORD *)(a6 + 24) || *(_DWORD *)(a6 + 28)) )
    {
      v24 = 1073741874;
      goto LABEL_104;
    }
    v21 = DisableSidCount;
    v22 = TokenInformation;
    if ( ((unsigned __int8)v6 & 2) != 0
      || DisableSidCount
      || TokenInformation
      || RestrictedSidCount
      || ((unsigned __int8)v6 & 1) != 0 )
    {
      v23 = v34;
      goto LABEL_74;
    }
  }
  v23 = v34;
  if ( (v34 & 1) != 0 )
  {
    v24 = 0;
    *v44 = 0;
LABEL_31:
    v6 = (PSID *)P;
LABEL_32:
    v9 = PrivilegesToDelete;
    goto LABEL_36;
  }
  if ( v47 )
  {
    v62 = 12;
    LOWORD(v63) = 1;
    v6 = (PSID *)P;
    v24 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
    if ( v24 < 0 )
      goto LABEL_32;
    v24 = RtlSetOwnerSecurityDescriptor(SecurityDescriptor, *(PSID *)P, 0);
    if ( v24 < 0 )
      goto LABEL_32;
    v32 = v44;
    v57.SecurityDescriptor = SecurityDescriptor;
    v57.SecurityQualityOfService = &v62;
    v57.Length = 48;
    v57.RootDirectory = 0;
    v57.Attributes = 2;
    v57.ObjectName = 0;
    v24 = NtDuplicateToken(TokenHandle, 0xF01FFu, &v57, 0, TokenPrimary, v44);
    if ( v24 != -1073741734 )
      goto LABEL_32;
    v57.SecurityDescriptor = 0;
    goto LABEL_100;
  }
LABEL_74:
  v9 = PrivilegesToDelete;
  if ( !CreateRestrictedToken(
          TokenHandle,
          (DWORD)v6,
          v21,
          SidsToDisable,
          v22,
          PrivilegesToDelete,
          RestrictedSidCount,
          SidsToRestrict,
          &ExistingTokenHandle) )
  {
    v24 = -1073741823;
    goto LABEL_102;
  }
  if ( (v23 & 1) == 0 || ((unsigned __int8)v6 & 2) != 0 )
    goto LABEL_76;
  Equal[0] = 0;
  v24 = NtCompareTokens(TokenHandle, ExistingTokenHandle, Equal);
  if ( v24 < 0 )
  {
LABEL_102:
    v6 = (PSID *)P;
    goto LABEL_36;
  }
  if ( Equal[0] )
  {
    v24 = 0;
    *v44 = 0;
    goto LABEL_102;
  }
LABEL_76:
  v24 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0xCu, 0, 0, 0, 0, 0, 0, 0, &Sid);
  if ( v24 < 0 )
    goto LABEL_102;
  v24 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0xAu, 0, 0, 0, 0, 0, 0, 0, &Sid2);
  if ( v24 < 0 )
    goto LABEL_102;
  v43 = 0;
  memset(&ObjectAttributes, 0, 44);
  v28 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  v6 = (PSID *)P;
  v24 = v28;
  if ( v28 >= 0 )
  {
    v24 = RtlSetOwnerSecurityDescriptor(SecurityDescriptor, *(PSID *)P, 0);
    if ( v24 >= 0 )
    {
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.SecurityDescriptor = SecurityDescriptor;
      ObjectAttributes.ObjectName = 0;
      ObjectAttributes.SecurityQualityOfService = &v62;
      v62 = 12;
      LOWORD(v63) = 1;
      ObjectAttributes.Length = 48;
      ObjectAttributes.Attributes = 2;
      v24 = NtDuplicateToken(ExistingTokenHandle, 0xF01FFu, &ObjectAttributes, 0, TokenPrimary, &v43);
      if ( v24 == -1073741734 )
      {
        ObjectAttributes.SecurityDescriptor = 0;
        v24 = NtDuplicateToken(ExistingTokenHandle, 0xF01FFu, &ObjectAttributes, 0, TokenPrimary, &v43);
      }
      if ( v24 >= 0 )
      {
        NtClose(ExistingTokenHandle);
        v29 = *(void **)(a1 + 24);
        ExistingTokenHandle = v43;
        if ( v29 && RtlEqualSid(v29, Sid2) )
          v30 = *v6;
        else
          v30 = *(PSID *)(a1 + 24);
        v24 = CodeAuthzpModifyTokenPermissions(ExistingTokenHandle, *v6);
        if ( v24 >= 0 )
        {
          if ( !v30
            || (!ExistingTokenHandle
              ? (v24 = -1073741811)
              : (v43 = v30, v24 = NtSetInformationToken(ExistingTokenHandle, TokenOwner, &v43, 8u)),
                v24 >= 0) )
          {
            v31 = ExistingTokenHandle;
            v24 = 0;
            ExistingTokenHandle = 0;
            *v44 = v31;
LABEL_39:
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
            goto LABEL_40;
          }
        }
        NtClose(ExistingTokenHandle);
      }
    }
  }
LABEL_36:
  if ( ExistingTokenHandle )
    NtClose(ExistingTokenHandle);
  if ( v6 )
    goto LABEL_39;
LABEL_40:
  if ( Sid )
    RtlFreeSid(Sid);
  if ( Sid2 )
    RtlFreeSid(Sid2);
  if ( v42 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, SidsToDisable);
  if ( v48 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v52);
  if ( v49 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
  if ( (!v24 || v24 == 1073741874) && (v23 & 8) != 0 && v61 )
    *v61 = v14;
  if ( !v50 )
  {
    a2 = TokenHandle;
    goto LABEL_55;
  }
  return (unsigned int)v24;
}

```

## disassembly

```asm
0x18000fc88  mov     [rsp-8+arg_18], rbx
0x18000fc8d  push    rbp
0x18000fc8e  push    rsi
0x18000fc8f  push    rdi
0x18000fc90  push    r12
0x18000fc92  push    r13
0x18000fc94  push    r14
0x18000fc96  push    r15
0x18000fc98  lea     rbp, [rsp-0A0h]
0x18000fca0  sub     rsp, 1A0h
0x18000fca7  mov     rax, cs:__security_cookie
0x18000fcae  xor     rax, rsp
0x18000fcb1  mov     [rbp+0D0h+var_38], rax
0x18000fcb8  mov     rax, [rbp+0D0h+arg_20]
0x18000fcbf  xor     r12d, r12d
0x18000fcc2  mov     [rbp+0D0h+var_58], rax
0x18000fcc6  mov     eax, r12d
0x18000fcc9  mov     [rbp+0D0h+var_108], rax
0x18000fccd  xorps   xmm0, xmm0
0x18000fcd0  mov     [rbp+0D0h+var_138], rax
0x18000fcd4  mov     rbx, r8
0x18000fcd7  mov     [rbp+0D0h+var_50], rax
0x18000fcde  mov     r14, rcx
0x18000fce1  mov     [rbp+0D0h+var_48], eax
0x18000fce7  mov     r13d, r12d
0x18000fcea  mov     [rbp+0D0h+var_90], rax
0x18000fcee  mov     [rsp+1D0h+var_170], r9d
0x18000fcf3  mov     [rbp+0D0h+var_130], rbx
0x18000fcf7  mov     [rbp+0D0h+TokenHandle], rdx
0x18000fcfb  mov     dword ptr [rbp+0D0h+IdentifierAuthority.Value], r12d
0x18000fd02  mov     word ptr [rbp+0D0h+IdentifierAuthority.Value+4], 500h
0x18000fd0b  mov     [rbp+0D0h+ExistingTokenHandle], r12
0x18000fd0f  mov     [rbp+0D0h+var_F0], r12
0x18000fd13  mov     [rbp+0D0h+Sid2], r12
0x18000fd17  mov     [rbp+0D0h+DisableSidCount], r12d
0x18000fd1b  mov     [rbp+0D0h+SidsToDisable], r12
0x18000fd1f  mov     dword ptr [rbp+0D0h+var_124], r12d
0x18000fd23  mov     [rbp+0D0h+var_128], r12d
0x18000fd27  mov     [rsp+1D0h+var_158], r12
0x18000fd2c  mov     [rbp+0D0h+var_F8], r12
0x18000fd30  movups  xmmword ptr [rbp+0D0h+var_E0.Length], xmm0
0x18000fd34  movups  xmmword ptr [rbp+0D0h+var_E0.ObjectName], xmm0
0x18000fd38  movups  xmmword ptr [rbp+0D0h+var_E0.SecurityDescriptor], xmm0
0x18000fd3c  movups  [rbp+0D0h+SecurityDescriptor], xmm0
0x18000fd40  movups  [rbp+0D0h+var_A0], xmm0
0x18000fd44  test    rcx, rcx
0x18000fd47  jz      loc_180010505
0x18000fd4d  test    rbx, rbx
0x18000fd50  jz      loc_18001050F
0x18000fd56  mov     r15, [rbp+0D0h+arg_28]
0x18000fd5d  test    r15, r15
0x18000fd60  jz      loc_18001050F
0x18000fd66  mov     [rbp+0D0h+var_13C], r12d
0x18000fd6a  lea     esi, [r12+1]
0x18000fd6f  mov     [rbp+0D0h+var_11C], r12d
0x18000fd73  mov     [rbp+0D0h+var_118], r12d
0x18000fd77  test    rdx, rdx
0x18000fd7a  jz      loc_18001001E
0x18000fd80  mov     [rbp+0D0h+var_114], esi
0x18000fd83  cmp     dword ptr [r14+10h], 0
0x18000fd88  mov     r13d, [r15+228h]
0x18000fd8f  mov     ecx, [r14+20h]
0x18000fd93  setnz   r12b
0x18000fd97  test    r13d, 0FF000000h
0x18000fd9e  jnz     loc_18000FFC5
0x18000fda4  or      ecx, r13d
0x18000fda7  bt      ecx, 11h
0x18000fdab  setnb   r8b
0x18000fdaf  test    r9b, 4
0x18000fdb3  setz    al
0x18000fdb6  and     r8b, al
0x18000fdb9  jnz     short loc_18000FDBF
0x18000fdbb  or      r12d, 2
0x18000fdbf  mov     edi, ecx
0x18000fdc1  bts     edi, 11h
0x18000fdc5  test    r8b, r8b
0x18000fdc8  cmovnz  edi, ecx
0x18000fdcb  mov     rcx, rdx
0x18000fdce  call    IsSystemProcessOrService
0x18000fdd3  mov     rcx, [rbp+0D0h+TokenHandle]; TokenHandle
0x18000fdd7  mov     edx, esi; TokenInformationClass
0x18000fdd9  mov     dword ptr [rbp+0D0h+var_124+4], eax
0x18000fddc  call    CodeAuthzpGetTokenInformation
0x18000fde1  mov     [rsp+1D0h+P], rax
0x18000fde6  test    rax, rax
0x18000fde9  jz      loc_18000FF03
0x18000fdef  mov     rcx, [rbp+0D0h+TokenHandle]; TokenHandle
0x18000fdf3  lea     rax, [rbp+0D0h+var_100]
0x18000fdf7  mov     r9d, 4; TokenInformationLength
0x18000fdfd  mov     [rsp+1D0h+TokenInformation], 0
0x18000fe05  lea     r8, [rsp+1D0h+TokenInformation]; TokenInformation
0x18000fe0a  mov     [rbp+0D0h+var_100], 0
0x18000fe11  mov     [rsp+1D0h+ReturnLength], rax; ReturnLength
0x18000fe16  lea     edx, [r9+0Bh]; TokenInformationClass
0x18000fe1a  call    cs:__imp_NtQueryInformationToken
0x18000fe21  nop     dword ptr [rax+rax+00h]
0x18000fe26  xor     ecx, ecx
0x18000fe28  test    eax, eax
0x18000fe2a  jns     loc_18000FFEA
0x18000fe30  xor     ebx, ebx
0x18000fe32  cmp     dword ptr [rbp+0D0h+var_124+4], ebx
0x18000fe35  jz      loc_18001000C
0x18000fe3b  cmp     [r14+38h], ebx
0x18000fe3f  jnz     loc_180010092
0x18000fe45  mov     eax, [r14+40h]
0x18000fe49  mov     rcx, [r14+48h]
0x18000fe4d  mov     r8d, [r14+2Ch]
0x18000fe51  mov     [rsp+1D0h+var_158], rcx
0x18000fe56  mov     [rsp+1D0h+TokenInformation], eax
0x18000fe5a  cmp     [r14+24h], ebx
0x18000fe5e  jnz     loc_1800103AD
0x18000fe64  test    r8d, r8d
0x18000fe67  jnz     loc_1800100CB
0x18000fe6d  mov     [rbp+0D0h+var_13C], ebx
0x18000fe70  mov     rbx, [rsp+1D0h+P]
0x18000fe75  mov     r8d, [r14+54h]
0x18000fe79  test    r8d, r8d
0x18000fe7c  jnz     loc_1800105A9
0x18000fe82  mov     r9, [r14+68h]
0x18000fe86  mov     ecx, [r14+64h]
0x18000fe8a  mov     [rbp+0D0h+var_108], r9
0x18000fe8e  mov     edx, dword ptr [rbp+0D0h+var_124+4]
0x18000fe91  mov     ebx, r12d
0x18000fe94  and     ebx, 2
0x18000fe97  test    edx, edx
0x18000fe99  jnz     loc_180010082
0x18000fe9f  bt      r13d, 0Ch
0x18000fea4  jb      loc_1800105F7
0x18000feaa  xor     r13d, r13d
0x18000fead  mov     r8d, [rbp+0D0h+DisableSidCount]; DisableSidCount
0x18000feb1  mov     eax, [rsp+1D0h+TokenInformation]
0x18000feb5  test    ebx, ebx
0x18000feb7  jnz     loc_18001010B
0x18000febd  test    r8d, r8d
0x18000fec0  jnz     loc_18001010B
0x18000fec6  test    eax, eax
0x18000fec8  jnz     loc_18001010B
0x18000fece  test    ecx, ecx
0x18000fed0  jnz     loc_18001010B
0x18000fed6  test    sil, r12b
0x18000fed9  jnz     loc_18001010B
0x18000fedf  mov     r15d, [rsp+1D0h+var_170]
0x18000fee4  test    sil, r15b
0x18000fee7  jz      loc_1800103E9
0x18000feed  mov     r14, [rbp+0D0h+var_130]
0x18000fef1  mov     ebx, r13d
0x18000fef4  mov     [r14], r13
0x18000fef7  mov     r12, [rsp+1D0h+P]
0x18000fefc  mov     r13, [rsp+1D0h+var_158]
0x18000ff01  jmp     short loc_18000FF15
0x18000ff03  mov     ebx, 0C0000001h
0x18000ff08  mov     r12, rax
0x18000ff0b  mov     r13, [rsp+1D0h+var_158]
0x18000ff10  mov     r15d, [rsp+1D0h+var_170]
0x18000ff15  mov     rcx, [rbp+0D0h+ExistingTokenHandle]; Handle
0x18000ff19  test    rcx, rcx
0x18000ff1c  jnz     loc_1800106D0
0x18000ff22  test    r12, r12
0x18000ff25  jz      short loc_18000FF45
0x18000ff27  mov     rcx, gs:60h
0x18000ff30  mov     r8, r12; P
0x18000ff33  xor     edx, edx; Flags
0x18000ff35  mov     rcx, [rcx+30h]; HeapHandle
0x18000ff39  call    cs:__imp_RtlFreeHeap
0x18000ff40  nop     dword ptr [rax+rax+00h]
0x18000ff45  mov     rcx, [rbp+0D0h+var_F0]; Sid
0x18000ff49  xor     r12d, r12d
0x18000ff4c  test    rcx, rcx
0x18000ff4f  jnz     loc_1800106E1
0x18000ff55  mov     rcx, [rbp+0D0h+Sid2]; Sid
0x18000ff59  test    rcx, rcx
0x18000ff5c  jnz     loc_1800106F2
0x18000ff62  cmp     [rbp+0D0h+var_13C], r12d
0x18000ff66  jnz     loc_180010389
0x18000ff6c  cmp     [rbp+0D0h+var_11C], r12d
0x18000ff70  jnz     loc_180010703
0x18000ff76  cmp     [rbp+0D0h+var_118], r12d
0x18000ff7a  jnz     loc_180010727
0x18000ff80  test    ebx, ebx
0x18000ff82  jnz     loc_18001074A
0x18000ff88  test    r15b, 8
0x18000ff8c  jnz     loc_18001075B
0x18000ff92  cmp     [rbp+0D0h+var_114], r12d
0x18000ff96  jz      short loc_18000FFD0
0x18000ff98  mov     eax, ebx
0x18000ff9a  mov     rcx, [rbp+0D0h+var_38]
0x18000ffa1  xor     rcx, rsp; StackCookie
0x18000ffa4  call    __security_check_cookie
0x18000ffa9  mov     rbx, [rsp+1D0h+arg_18]
0x18000ffb1  add     rsp, 1A0h
0x18000ffb8  pop     r15
0x18000ffba  pop     r14
0x18000ffbc  pop     r13
0x18000ffbe  pop     r12
0x18000ffc0  pop     rdi
0x18000ffc1  pop     rsi
0x18000ffc2  pop     rbp
0x18000ffc3  retn
0x18000ffc5  and     ecx, 0FFFFFFh
0x18000ffcb  jmp     loc_18000FDA4
0x18000ffd0  mov     rdx, [rbp+0D0h+TokenHandle]
0x18000ffd4  test    rdx, rdx
0x18000ffd7  jz      short loc_18000FF98
0x18000ffd9  mov     rcx, rdx; Handle
0x18000ffdc  call    cs:__imp_NtClose
0x18000ffe3  nop     dword ptr [rax+rax+00h]
0x18000ffe8  jmp     short loc_18000FF98
0x18000ffea  cmp     [rsp+1D0h+TokenInformation], ecx
0x18000ffee  jz      loc_18000FE30
0x18000fff4  mov     r15d, [rsp+1D0h+var_170]
0x18000fff9  test    sil, r15b
0x18000fffc  jz      loc_180010519
0x180010002  mov     [rbx], rcx
0x180010005  mov     ebx, ecx
0x180010007  jmp     loc_18000FEF7
0x18001000c  cmp     [r14+0Ch], ebx
0x180010010  jz      loc_18000FE3B
0x180010016  or      ebx, 0FFFFFFFFh
0x180010019  jmp     loc_1800104EA
0x18001001e  lea     r9, [rbp+0D0h+TokenHandle]; TokenHandle
0x180010022  mov     [rbp+0D0h+var_114], r12d
0x180010026  mov     r8b, sil; OpenAsSelf
0x180010029  mov     edx, 2000Ah; DesiredAccess
0x18001002e  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180010035  mov     edi, r12d
0x180010038  call    cs:__imp_NtOpenThreadToken
0x18001003f  nop     dword ptr [rax+rax+00h]
0x180010044  mov     ebx, eax
0x180010046  cmp     eax, 0C000007Ch
0x18001004b  jnz     short loc_180010068
0x18001004d  lea     r8, [rbp+0D0h+TokenHandle]; TokenHandle
0x180010051  mov     edx, 2000Ah; DesiredAccess
0x180010056  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18001005a  call    cs:__imp_NtOpenProcessToken
0x180010061  nop     dword ptr [rax+rax+00h]
0x180010066  mov     ebx, eax
0x180010068  test    eax, eax
0x18001006a  js      loc_18000FF10
0x180010070  mov     r9d, [rsp+1D0h+var_170]
0x180010075  mov     rbx, [rbp+0D0h+var_130]
0x180010079  mov     rdx, [rbp+0D0h+TokenHandle]
0x18001007d  jmp     loc_18000FD83
0x180010082  mov     eax, [rsp+1D0h+TokenInformation]
0x180010086  xor     r13d, r13d
0x180010089  mov     r8d, [rbp+0D0h+DisableSidCount]
0x18001008d  jmp     loc_18000FEDF
0x180010092  mov     r8, [r14+48h]
0x180010096  lea     rax, [rbp+0D0h+var_F8]
0x18001009a  mov     edx, [r14+40h]
0x18001009e  lea     r9, [rbp+0D0h+var_128]
0x1800100a2  mov     rcx, [rbp+0D0h+TokenHandle]
0x1800100a6  mov     [rsp+1D0h+ReturnLength], rax
0x1800100ab  call    CodeAuthzpInvertPrivs
0x1800100b0  test    al, al
0x1800100b2  jnz     loc_180010334
0x1800100b8  mov     r13, [rbp+0D0h+var_F8]
0x1800100bc  mov     ebx, 0C0000001h
0x1800100c1  mov     r12, [rsp+1D0h+P]
0x1800100c6  jmp     loc_18000FF10
0x1800100cb  mov     r9, [r14+30h]
0x1800100cf  test    r9, r9
0x1800100d2  jz      loc_18000FE6D
0x1800100d8  mov     rbx, [rsp+1D0h+P]
0x1800100dd  lea     rax, [rbp+0D0h+SidsToDisable]
0x1800100e1  mov     rcx, [rbp+0D0h+TokenHandle]; TokenHandle
0x1800100e5  mov     [rsp+1D0h+PrivilegesToDelete], rax; __int64
0x1800100ea  lea     rax, [rbp+0D0h+DisableSidCount]
0x1800100ee  mov     [rsp+1D0h+ReturnLength], rax; __int64
0x1800100f3  mov     rdx, [rbx]; Sid1
0x1800100f6  call    CodeAuthzpExpandWildcardList
0x1800100fb  test    al, al
0x1800100fd  jz      loc_1800104E5
0x180010103  mov     [rbp+0D0h+var_13C], esi
0x180010106  jmp     loc_18000FE75
0x18001010b  mov     r15d, [rsp+1D0h+var_170]
0x180010110  mov     r13, [rsp+1D0h+var_158]
0x180010115  lea     rdx, [rbp+0D0h+ExistingTokenHandle]
0x180010119  mov     [rsp+1D0h+NewTokenHandle], rdx; NewTokenHandle
0x18001011e  mov     edx, r12d; Flags
0x180010121  mov     [rsp+1D0h+SidsToRestrict], r9; SidsToRestrict
0x180010126  mov     r9, [rbp+0D0h+SidsToDisable]; SidsToDisable
0x18001012a  mov     [rsp+1D0h+RestrictedSidCount], ecx; RestrictedSidCount
0x18001012e  mov     rcx, [rbp+0D0h+TokenHandle]; ExistingTokenHandle
0x180010132  mov     [rsp+1D0h+PrivilegesToDelete], r13; PrivilegesToDelete
0x180010137  mov     dword ptr [rsp+1D0h+ReturnLength], eax; DeletePrivilegeCount
0x18001013b  call    cs:__imp_CreateRestrictedToken
0x180010142  nop     dword ptr [rax+rax+00h]
0x180010147  xor     r12d, r12d
0x18001014a  test    eax, eax
0x18001014c  jz      loc_1800104D6
0x180010152  test    sil, r15b
0x180010155  jnz     loc_18001062D
0x18001015b  lea     rax, [rbp+0D0h+var_F0]
0x18001015f  xor     r9d, r9d; SubAuthority1
0x180010162  mov     [rsp+1D0h+Sid], rax; Sid
0x180010167  lea     rcx, [rbp+0D0h+IdentifierAuthority]; IdentifierAuthority
0x18001016e  mov     [rsp+1D0h+SubAuthority7], r12d; SubAuthority7
0x180010173  mov     dl, sil; SubAuthorityCount
0x180010176  mov     dword ptr [rsp+1D0h+NewTokenHandle], r12d; SubAuthority6
0x18001017b  mov     dword ptr [rsp+1D0h+SidsToRestrict], r12d; SubAuthority5
  ... truncated ...
```
