# __CodeAuthzpComputeAccessTokenFromCodeAuthzObject

- ea: `0x18000a78c`
- end: `0x18000b1c4`
- name: `__CodeAuthzpComputeAccessTokenFromCodeAuthzObject`
- size: `2616`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000a3b0`

## callees

- `0x180009f70`
- `0x18000a150`
- `0x18000a680`
- `0x18000a78c`
- `0x18000bf20`
- `0x18000c0d0`
- `0x18000c650`
- `0x180065090`

## import_xrefs

- `ntdll!NtClose` at `0x18000aad3`
- `ntdll!NtClose` at `0x18000ad90`
- `ntdll!NtClose` at `0x18000ae2d`
- `ntdll!NtClose` at `0x18000b143`
- `ntdll!NtClose` at `0x18000aad3`
- `ntdll!NtClose` at `0x18000ad90`
- `ntdll!NtClose` at `0x18000ae2d`
- `ntdll!NtClose` at `0x18000b143`
- `ntdll!NtOpenThreadToken` at `0x18000ab29`
- `ntdll!NtOpenThreadToken` at `0x18000ab29`
- `ntdll!NtOpenProcessToken` at `0x18000ab45`
- `ntdll!NtOpenProcessToken` at `0x18000ab45`
- `ntdll!RtlEqualSid` at `0x18000b12c`
- `ntdll!RtlEqualSid` at `0x18000b12c`
- `ntdll!NtSetInformationToken` at `0x18000ae1d`
- `ntdll!NtSetInformationToken` at `0x18000ae1d`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18000ace5`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18000aeb4`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18000afc4`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18000ace5`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18000aeb4`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18000afc4`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18000ad05`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18000aed4`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18000afe4`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18000ad05`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18000aed4`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x18000afe4`
- `ntdll!NtDuplicateToken` at `0x18000ad71`
- `ntdll!NtDuplicateToken` at `0x18000af2a`
- `ntdll!NtDuplicateToken` at `0x18000af5a`
- `ntdll!NtDuplicateToken` at `0x18000b11b`
- `ntdll!NtDuplicateToken` at `0x18000ad71`
- `ntdll!NtDuplicateToken` at `0x18000af2a`
- `ntdll!NtDuplicateToken` at `0x18000af5a`
- `ntdll!NtDuplicateToken` at `0x18000b11b`
- `ntdll!NtCompareTokens` at `0x18000b0cc`
- `ntdll!NtCompareTokens` at `0x18000b0cc`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000ac72`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000acba`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000ac72`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000acba`
- `ntdll!RtlFreeSid` at `0x18000b14e`
- `ntdll!RtlFreeSid` at `0x18000b159`
- `ntdll!RtlFreeSid` at `0x18000b14e`
- `ntdll!RtlFreeSid` at `0x18000b159`
- `ntdll!RtlFreeHeap` at `0x18000aa37`
- `ntdll!RtlFreeHeap` at `0x18000ae4b`
- `ntdll!RtlFreeHeap` at `0x18000b177`
- `ntdll!RtlFreeHeap` at `0x18000b194`
- `ntdll!RtlFreeHeap` at `0x18000aa37`
- `ntdll!RtlFreeHeap` at `0x18000ae4b`
- `ntdll!RtlFreeHeap` at `0x18000b177`
- `ntdll!RtlFreeHeap` at `0x18000b194`
- `ntdll!NtQueryInformationToken` at `0x18000a91e`
- `ntdll!NtQueryInformationToken` at `0x18000a91e`
- `api-ms-win-security-base-l1-1-0!CreateRestrictedToken` at `0x18000ac20`
- `api-ms-win-security-base-l1-1-0!CreateRestrictedToken` at `0x18000ac20`

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
0x18000a78c  mov     [rsp-8+arg_18], rbx
0x18000a791  push    rbp
0x18000a792  push    rsi
0x18000a793  push    rdi
0x18000a794  push    r12
0x18000a796  push    r13
0x18000a798  push    r14
0x18000a79a  push    r15
0x18000a79c  lea     rbp, [rsp-0A0h]
0x18000a7a4  sub     rsp, 1A0h
0x18000a7ab  mov     rax, cs:__security_cookie
0x18000a7b2  xor     rax, rsp
0x18000a7b5  mov     [rbp+0D0h+var_38], rax
0x18000a7bc  mov     rax, [rbp+0D0h+arg_20]
0x18000a7c3  xor     r12d, r12d
0x18000a7c6  mov     [rbp+0D0h+var_58], rax
0x18000a7ca  mov     eax, r12d
0x18000a7cd  mov     [rbp+0D0h+var_108], rax
0x18000a7d1  xorps   xmm0, xmm0
0x18000a7d4  mov     [rbp+0D0h+var_138], rax
0x18000a7d8  mov     rbx, r8
0x18000a7db  mov     [rbp+0D0h+var_50], rax
0x18000a7e2  mov     r14, rcx
0x18000a7e5  mov     [rbp+0D0h+var_48], eax
0x18000a7eb  mov     r13d, r12d
0x18000a7ee  mov     [rbp+0D0h+var_90], rax
0x18000a7f2  mov     [rsp+1D0h+var_170], r9d
0x18000a7f7  mov     [rbp+0D0h+var_130], rbx
0x18000a7fb  mov     [rbp+0D0h+TokenHandle], rdx
0x18000a7ff  mov     dword ptr [rbp+0D0h+IdentifierAuthority.Value], r12d
0x18000a806  mov     word ptr [rbp+0D0h+IdentifierAuthority.Value+4], 500h
0x18000a80f  mov     [rbp+0D0h+ExistingTokenHandle], r12
0x18000a813  mov     [rbp+0D0h+var_F0], r12
0x18000a817  mov     [rbp+0D0h+Sid2], r12
0x18000a81b  mov     [rbp+0D0h+DisableSidCount], r12d
0x18000a81f  mov     [rbp+0D0h+SidsToDisable], r12
0x18000a823  mov     dword ptr [rbp+0D0h+var_124], r12d
0x18000a827  mov     [rbp+0D0h+var_128], r12d
0x18000a82b  mov     [rsp+1D0h+var_158], r12
0x18000a830  mov     [rbp+0D0h+var_F8], r12
0x18000a834  movups  xmmword ptr [rbp+0D0h+var_E0.Length], xmm0
0x18000a838  movups  xmmword ptr [rbp+0D0h+var_E0.ObjectName], xmm0
0x18000a83c  movups  xmmword ptr [rbp+0D0h+var_E0.SecurityDescriptor], xmm0
0x18000a840  movups  [rbp+0D0h+SecurityDescriptor], xmm0
0x18000a844  movups  [rbp+0D0h+var_A0], xmm0
0x18000a848  test    rcx, rcx
0x18000a84b  jz      loc_18000AF96
0x18000a851  test    rbx, rbx
0x18000a854  jz      loc_18000AFA0
0x18000a85a  mov     r15, [rbp+0D0h+arg_28]
0x18000a861  test    r15, r15
0x18000a864  jz      loc_18000AFA0
0x18000a86a  mov     [rbp+0D0h+var_13C], r12d
0x18000a86e  lea     esi, [r12+1]
0x18000a873  mov     [rbp+0D0h+var_11C], r12d
0x18000a877  mov     [rbp+0D0h+var_118], r12d
0x18000a87b  test    rdx, rdx
0x18000a87e  jz      loc_18000AB0F
0x18000a884  mov     [rbp+0D0h+var_114], esi
0x18000a887  cmp     dword ptr [r14+10h], 0
0x18000a88c  mov     r13d, [r15+228h]
0x18000a893  mov     ecx, [r14+20h]
0x18000a897  setnz   r12b
0x18000a89b  test    r13d, 0FF000000h
0x18000a8a2  jnz     loc_18000AABC
0x18000a8a8  or      ecx, r13d
0x18000a8ab  bt      ecx, 11h
0x18000a8af  setnb   r8b
0x18000a8b3  test    r9b, 4
0x18000a8b7  setz    al
0x18000a8ba  and     r8b, al
0x18000a8bd  jnz     short loc_18000A8C3
0x18000a8bf  or      r12d, 2
0x18000a8c3  mov     edi, ecx
0x18000a8c5  bts     edi, 11h
0x18000a8c9  test    r8b, r8b
0x18000a8cc  cmovnz  edi, ecx
0x18000a8cf  mov     rcx, rdx
0x18000a8d2  call    IsSystemProcessOrService
0x18000a8d7  mov     rcx, [rbp+0D0h+TokenHandle]; TokenHandle
0x18000a8db  mov     edx, esi; TokenInformationClass
0x18000a8dd  mov     dword ptr [rbp+0D0h+var_124+4], eax
0x18000a8e0  call    CodeAuthzpGetTokenInformation
0x18000a8e5  mov     [rsp+1D0h+P], rax
0x18000a8ea  test    rax, rax
0x18000a8ed  jz      loc_18000AA01
0x18000a8f3  mov     rcx, [rbp+0D0h+TokenHandle]; TokenHandle
0x18000a8f7  lea     rax, [rbp+0D0h+var_100]
0x18000a8fb  mov     r9d, 4; TokenInformationLength
0x18000a901  mov     [rsp+1D0h+TokenInformation], 0
0x18000a909  lea     r8, [rsp+1D0h+TokenInformation]; TokenInformation
0x18000a90e  mov     [rbp+0D0h+var_100], 0
0x18000a915  mov     [rsp+1D0h+ReturnLength], rax; ReturnLength
0x18000a91a  lea     edx, [r9+0Bh]; TokenInformationClass
0x18000a91e  call    cs:__imp_NtQueryInformationToken
0x18000a924  xor     ecx, ecx
0x18000a926  test    eax, eax
0x18000a928  jns     loc_18000AADB
0x18000a92e  xor     ebx, ebx
0x18000a930  cmp     dword ptr [rbp+0D0h+var_124+4], ebx
0x18000a933  jz      loc_18000AAFD
0x18000a939  cmp     [r14+38h], ebx
0x18000a93d  jnz     loc_18000AB77
0x18000a943  mov     eax, [r14+40h]
0x18000a947  mov     rcx, [r14+48h]
0x18000a94b  mov     r8d, [r14+2Ch]
0x18000a94f  mov     [rsp+1D0h+var_158], rcx
0x18000a954  mov     [rsp+1D0h+TokenInformation], eax
0x18000a958  cmp     [r14+24h], ebx
0x18000a95c  jnz     loc_18000AE56
0x18000a962  test    r8d, r8d
0x18000a965  jnz     loc_18000ABB0
0x18000a96b  mov     [rbp+0D0h+var_13C], ebx
0x18000a96e  mov     rbx, [rsp+1D0h+P]
0x18000a973  mov     r8d, [r14+54h]
0x18000a977  test    r8d, r8d
0x18000a97a  jnz     loc_18000B02E
0x18000a980  mov     r9, [r14+68h]
0x18000a984  mov     ecx, [r14+64h]
0x18000a988  mov     [rbp+0D0h+var_108], r9
0x18000a98c  mov     edx, dword ptr [rbp+0D0h+var_124+4]
0x18000a98f  mov     ebx, r12d
0x18000a992  and     ebx, 2
0x18000a995  test    edx, edx
0x18000a997  jnz     loc_18000AB67
0x18000a99d  bt      r13d, 0Ch
0x18000a9a2  jb      loc_18000B07C
0x18000a9a8  xor     r13d, r13d
0x18000a9ab  mov     r8d, [rbp+0D0h+DisableSidCount]; DisableSidCount
0x18000a9af  mov     eax, [rsp+1D0h+TokenInformation]
0x18000a9b3  test    ebx, ebx
0x18000a9b5  jnz     loc_18000ABF0
0x18000a9bb  test    r8d, r8d
0x18000a9be  jnz     loc_18000ABF0
0x18000a9c4  test    eax, eax
0x18000a9c6  jnz     loc_18000ABF0
0x18000a9cc  test    ecx, ecx
0x18000a9ce  jnz     loc_18000ABF0
0x18000a9d4  test    sil, r12b
0x18000a9d7  jnz     loc_18000ABF0
0x18000a9dd  mov     r15d, [rsp+1D0h+var_170]
0x18000a9e2  test    sil, r15b
0x18000a9e5  jz      loc_18000AE92
0x18000a9eb  mov     r14, [rbp+0D0h+var_130]
0x18000a9ef  mov     ebx, r13d
0x18000a9f2  mov     [r14], r13
0x18000a9f5  mov     r12, [rsp+1D0h+P]
0x18000a9fa  mov     r13, [rsp+1D0h+var_158]
0x18000a9ff  jmp     short loc_18000AA13
0x18000aa01  mov     ebx, 0C0000001h
0x18000aa06  mov     r12, rax
0x18000aa09  mov     r13, [rsp+1D0h+var_158]
0x18000aa0e  mov     r15d, [rsp+1D0h+var_170]
0x18000aa13  mov     rcx, [rbp+0D0h+ExistingTokenHandle]; Handle
0x18000aa17  test    rcx, rcx
0x18000aa1a  jnz     loc_18000B143
0x18000aa20  test    r12, r12
0x18000aa23  jz      short loc_18000AA3D
0x18000aa25  mov     rcx, gs:60h
0x18000aa2e  mov     r8, r12; P
0x18000aa31  xor     edx, edx; Flags
0x18000aa33  mov     rcx, [rcx+30h]; HeapHandle
0x18000aa37  call    cs:__imp_RtlFreeHeap
0x18000aa3d  mov     rcx, [rbp+0D0h+var_F0]; Sid
0x18000aa41  xor     r12d, r12d
0x18000aa44  test    rcx, rcx
0x18000aa47  jnz     loc_18000B14E
0x18000aa4d  mov     rcx, [rbp+0D0h+Sid2]; Sid
0x18000aa51  test    rcx, rcx
0x18000aa54  jnz     loc_18000B159
0x18000aa5a  cmp     [rbp+0D0h+var_13C], r12d
0x18000aa5e  jnz     loc_18000AE38
0x18000aa64  cmp     [rbp+0D0h+var_11C], r12d
0x18000aa68  jnz     loc_18000B164
0x18000aa6e  cmp     [rbp+0D0h+var_118], r12d
0x18000aa72  jnz     loc_18000B182
0x18000aa78  test    ebx, ebx
0x18000aa7a  jnz     loc_18000B19F
0x18000aa80  test    r15b, 8
0x18000aa84  jnz     loc_18000B1B0
0x18000aa8a  cmp     [rbp+0D0h+var_114], r12d
0x18000aa8e  jz      short loc_18000AAC7
0x18000aa90  mov     eax, ebx
0x18000aa92  mov     rcx, [rbp+0D0h+var_38]
0x18000aa99  xor     rcx, rsp; StackCookie
0x18000aa9c  call    __security_check_cookie
0x18000aaa1  mov     rbx, [rsp+1D0h+arg_18]
0x18000aaa9  add     rsp, 1A0h
0x18000aab0  pop     r15
0x18000aab2  pop     r14
0x18000aab4  pop     r13
0x18000aab6  pop     r12
0x18000aab8  pop     rdi
0x18000aab9  pop     rsi
0x18000aaba  pop     rbp
0x18000aabb  retn
0x18000aabc  and     ecx, 0FFFFFFh
0x18000aac2  jmp     loc_18000A8A8
0x18000aac7  mov     rdx, [rbp+0D0h+TokenHandle]
0x18000aacb  test    rdx, rdx
0x18000aace  jz      short loc_18000AA90
0x18000aad0  mov     rcx, rdx; Handle
0x18000aad3  call    cs:__imp_NtClose
0x18000aad9  jmp     short loc_18000AA90
0x18000aadb  cmp     [rsp+1D0h+TokenInformation], ecx
0x18000aadf  jz      loc_18000A92E
0x18000aae5  mov     r15d, [rsp+1D0h+var_170]
0x18000aaea  test    sil, r15b
0x18000aaed  jz      loc_18000AFAA
0x18000aaf3  mov     [rbx], rcx
0x18000aaf6  mov     ebx, ecx
0x18000aaf8  jmp     loc_18000A9F5
0x18000aafd  cmp     [r14+0Ch], ebx
0x18000ab01  jz      loc_18000A939
0x18000ab07  or      ebx, 0FFFFFFFFh
0x18000ab0a  jmp     loc_18000AF7B
0x18000ab0f  lea     r9, [rbp+0D0h+TokenHandle]; TokenHandle
0x18000ab13  mov     [rbp+0D0h+var_114], r12d
0x18000ab17  mov     r8b, sil; OpenAsSelf
0x18000ab1a  mov     edx, 2000Ah; DesiredAccess
0x18000ab1f  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18000ab26  mov     edi, r12d
0x18000ab29  call    cs:__imp_NtOpenThreadToken
0x18000ab2f  mov     ebx, eax
0x18000ab31  cmp     eax, 0C000007Ch
0x18000ab36  jnz     short loc_18000AB4D
0x18000ab38  lea     r8, [rbp+0D0h+TokenHandle]; TokenHandle
0x18000ab3c  mov     edx, 2000Ah; DesiredAccess
0x18000ab41  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18000ab45  call    cs:__imp_NtOpenProcessToken
0x18000ab4b  mov     ebx, eax
0x18000ab4d  test    eax, eax
0x18000ab4f  js      loc_18000AA0E
0x18000ab55  mov     r9d, [rsp+1D0h+var_170]
0x18000ab5a  mov     rbx, [rbp+0D0h+var_130]
0x18000ab5e  mov     rdx, [rbp+0D0h+TokenHandle]
0x18000ab62  jmp     loc_18000A887
0x18000ab67  mov     eax, [rsp+1D0h+TokenInformation]
0x18000ab6b  xor     r13d, r13d
0x18000ab6e  mov     r8d, [rbp+0D0h+DisableSidCount]
0x18000ab72  jmp     loc_18000A9DD
0x18000ab77  mov     r8, [r14+48h]
0x18000ab7b  lea     rax, [rbp+0D0h+var_F8]
0x18000ab7f  mov     edx, [r14+40h]
0x18000ab83  lea     r9, [rbp+0D0h+var_128]
0x18000ab87  mov     rcx, [rbp+0D0h+TokenHandle]
0x18000ab8b  mov     [rsp+1D0h+ReturnLength], rax
0x18000ab90  call    CodeAuthzpInvertPrivs
0x18000ab95  test    al, al
0x18000ab97  jnz     loc_18000ADEF
0x18000ab9d  mov     r13, [rbp+0D0h+var_F8]
0x18000aba1  mov     ebx, 0C0000001h
0x18000aba6  mov     r12, [rsp+1D0h+P]
0x18000abab  jmp     loc_18000AA0E
0x18000abb0  mov     r9, [r14+30h]
0x18000abb4  test    r9, r9
0x18000abb7  jz      loc_18000A96B
0x18000abbd  mov     rbx, [rsp+1D0h+P]
0x18000abc2  lea     rax, [rbp+0D0h+SidsToDisable]
0x18000abc6  mov     rcx, [rbp+0D0h+TokenHandle]; TokenHandle
0x18000abca  mov     [rsp+1D0h+PrivilegesToDelete], rax; __int64
0x18000abcf  lea     rax, [rbp+0D0h+DisableSidCount]
0x18000abd3  mov     [rsp+1D0h+ReturnLength], rax; __int64
0x18000abd8  mov     rdx, [rbx]; Sid1
0x18000abdb  call    CodeAuthzpExpandWildcardList
0x18000abe0  test    al, al
0x18000abe2  jz      loc_18000AF76
0x18000abe8  mov     [rbp+0D0h+var_13C], esi
0x18000abeb  jmp     loc_18000A973
0x18000abf0  mov     r15d, [rsp+1D0h+var_170]
0x18000abf5  mov     r13, [rsp+1D0h+var_158]
0x18000abfa  lea     rdx, [rbp+0D0h+ExistingTokenHandle]
0x18000abfe  mov     [rsp+1D0h+NewTokenHandle], rdx; NewTokenHandle
0x18000ac03  mov     edx, r12d; Flags
0x18000ac06  mov     [rsp+1D0h+SidsToRestrict], r9; SidsToRestrict
0x18000ac0b  mov     r9, [rbp+0D0h+SidsToDisable]; SidsToDisable
0x18000ac0f  mov     [rsp+1D0h+RestrictedSidCount], ecx; RestrictedSidCount
0x18000ac13  mov     rcx, [rbp+0D0h+TokenHandle]; ExistingTokenHandle
0x18000ac17  mov     [rsp+1D0h+PrivilegesToDelete], r13; PrivilegesToDelete
0x18000ac1c  mov     dword ptr [rsp+1D0h+ReturnLength], eax; DeletePrivilegeCount
0x18000ac20  call    cs:__imp_CreateRestrictedToken
0x18000ac26  xor     r12d, r12d
0x18000ac29  test    eax, eax
0x18000ac2b  jz      loc_18000AF67
0x18000ac31  test    sil, r15b
0x18000ac34  jnz     loc_18000B0B2
0x18000ac3a  lea     rax, [rbp+0D0h+var_F0]
0x18000ac3e  xor     r9d, r9d; SubAuthority1
0x18000ac41  mov     [rsp+1D0h+Sid], rax; Sid
0x18000ac46  lea     rcx, [rbp+0D0h+IdentifierAuthority]; IdentifierAuthority
0x18000ac4d  mov     [rsp+1D0h+SubAuthority7], r12d; SubAuthority7
0x18000ac52  mov     dl, sil; SubAuthorityCount
0x18000ac55  mov     dword ptr [rsp+1D0h+NewTokenHandle], r12d; SubAuthority6
0x18000ac5a  mov     dword ptr [rsp+1D0h+SidsToRestrict], r12d; SubAuthority5
0x18000ac5f  lea     r8d, [r9+0Ch]; SubAuthority0
0x18000ac63  mov     [rsp+1D0h+RestrictedSidCount], r12d; SubAuthority4
0x18000ac68  mov     dword ptr [rsp+1D0h+PrivilegesToDelete], r12d; SubAuthority3
0x18000ac6d  mov     dword ptr [rsp+1D0h+ReturnLength], r12d; SubAuthority2
0x18000ac72  call    cs:__imp_RtlAllocateAndInitializeSid
0x18000ac78  mov     ebx, eax
  ... truncated ...
```
