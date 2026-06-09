# CompareObjectSDToSddl

- ea: `0x180074e20`
- end: `0x180075526`
- name: `CompareObjectSDToSddl`
- size: `1798`
- prototype: `__int64 __fastcall(LPCWSTR pObjectName, SE_OBJECT_TYPE ObjectType, LPCWSTR StringSecurityDescriptor)`
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180074e20`
- `0x18007552c`
- `0x180075564`
- `0x180075808`
- `0x180076ce8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180074f5e`
- `KERNEL32!GetLastError` at `0x180074fae`
- `KERNEL32!GetLastError` at `0x180075102`
- `KERNEL32!GetLastError` at `0x18007516d`
- `KERNEL32!GetLastError` at `0x1800751c2`
- `KERNEL32!GetLastError` at `0x18007521f`
- `KERNEL32!GetLastError` at `0x1800753da`
- `KERNEL32!GetLastError` at `0x180074f5e`
- `KERNEL32!GetLastError` at `0x180074fae`
- `KERNEL32!GetLastError` at `0x180075102`
- `KERNEL32!GetLastError` at `0x18007516d`
- `KERNEL32!GetLastError` at `0x1800751c2`
- `KERNEL32!GetLastError` at `0x18007521f`
- `KERNEL32!GetLastError` at `0x1800753da`
- `KERNEL32!LocalFree` at `0x18007500c`
- `KERNEL32!LocalFree` at `0x180075022`
- `KERNEL32!LocalFree` at `0x180075038`
- `KERNEL32!LocalFree` at `0x18007504e`
- `KERNEL32!LocalFree` at `0x18007500c`
- `KERNEL32!LocalFree` at `0x180075022`
- `KERNEL32!LocalFree` at `0x180075038`
- `KERNEL32!LocalFree` at `0x18007504e`
- `ntdll!RtlMapGenericMask` at `0x18007530e`
- `ntdll!RtlMapGenericMask` at `0x180075325`
- `ntdll!RtlMapGenericMask` at `0x18007530e`
- `ntdll!RtlMapGenericMask` at `0x180075325`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x1800750a6`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x1800750a6`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x180074f9e`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x1800750f2`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x180074f9e`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x1800750f2`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x1800753ca`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x1800753ca`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x18007520f`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x18007520f`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180074f4e`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180074f4e`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x18007515d`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x18007515d`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x1800751b2`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x1800751b2`
- `ADVAPI32!GetExplicitEntriesFromAclW` at `0x180075284`
- `ADVAPI32!GetExplicitEntriesFromAclW` at `0x1800752bc`
- `ADVAPI32!GetExplicitEntriesFromAclW` at `0x18007542a`
- `ADVAPI32!GetExplicitEntriesFromAclW` at `0x180075462`
- `ADVAPI32!GetExplicitEntriesFromAclW` at `0x180075284`
- `ADVAPI32!GetExplicitEntriesFromAclW` at `0x1800752bc`
- `ADVAPI32!GetExplicitEntriesFromAclW` at `0x18007542a`
- `ADVAPI32!GetExplicitEntriesFromAclW` at `0x180075462`

## string_xrefs

- `0x180074eb2`: `onecore\base\subsys\sm\sfc\wrpdisable\aclcomp.c`
- `0x180074ee7`: `onecore\base\subsys\sm\sfc\wrpdisable\aclcomp.c`
- `0x180074f7d`: `onecore\base\subsys\sm\sfc\wrpdisable\aclcomp.c`
- `0x180074fea`: `onecore\base\subsys\sm\sfc\wrpdisable\aclcomp.c`
- `0x1800750ce`: `onecore\base\subsys\sm\sfc\wrpdisable\aclcomp.c`
- `0x180075139`: `onecore\base\subsys\sm\sfc\wrpdisable\aclcomp.c`
- `0x180075254`: `onecore\base\subsys\sm\sfc\wrpdisable\aclcomp.c`
- `0x180074ea5`: ` CompareObjectSdToSddl: SeObjectType not supported \n`
- `0x180074fd8`: ` Target SDDL %ws doesnt have a protected dacl-- dont care, return matched\n`
- `0x180074fba`: ` GetSecurityDescriptorControl failed for Target SDDL %08d \n`
- `0x18007510e`: ` GetSecurityDescriptorControl failed for Object SDDL %08d \n`
- `0x1800750bd`: `GetNamedSecurityInfo failed with error %08d for object %ws \n`
- `0x18007512c`: ` Object SD doesnt have a protected DACL\n`
- `0x180075247`: `Target SDDL has a DACL but the object doesnt\n`
- `0x1800752ce`: `GetExplicitEntriesFromAcl for object dacl failed with error %08d \n`
- `0x180075474`: `GetExplicitEntriesFromAcl for object dacl failed with error %08d \n`
- `0x180075296`: `GeExplicitEntriesFromAcl for targetdacl failed with error %08d \n`
- `0x180075402`: ` Target SD has a sacl but the object sd doesnt\n`
- `0x18007543c`: `GeExplicitEntriesFromAcl for targetsacl failed with error %08d \n`

## pseudocode

```c
__int64 __fastcall CompareObjectSDToSddl(
        LPCWSTR pObjectName,
        SE_OBJECT_TYPE ObjectType,
        LPCWSTR StringSecurityDescriptor,
        _DWORD *a4)
{
  DWORD NamedSecurityInfoW; // ebx
  struct _GENERIC_MAPPING *v9; // r14
  DWORD LastError; // eax
  int v11; // r8d
  const wchar_t *v12; // r9
  struct _ACL *v14; // rcx
  ULONG v15; // eax
  ULONG i; // esi
  __int64 v17; // rdi
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  struct _ACL *v21; // rcx
  ULONG v22; // eax
  ULONG j; // edi
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  __int128 v26; // xmm1
  ULONG v27; // [rsp+40h] [rbp-C0h] BYREF
  DWORD dwRevision; // [rsp+44h] [rbp-BCh] BYREF
  WORD v29[2]; // [rsp+48h] [rbp-B8h] BYREF
  ULONG pcCountOfExplicitEntries; // [rsp+4Ch] [rbp-B4h] BYREF
  WINBOOL bDaclPresent; // [rsp+50h] [rbp-B0h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+58h] [rbp-A8h] BYREF
  HLOCAL v33; // [rsp+60h] [rbp-A0h] BYREF
  HLOCAL v34; // [rsp+68h] [rbp-98h] BYREF
  PACL pacl; // [rsp+70h] [rbp-90h] BYREF
  PACL ppSacl; // [rsp+78h] [rbp-88h] BYREF
  PSID pOwner; // [rsp+80h] [rbp-80h] BYREF
  PSID ppsidOwner; // [rsp+88h] [rbp-78h] BYREF
  PSID pGroup; // [rsp+90h] [rbp-70h] BYREF
  PSID ppsidGroup; // [rsp+98h] [rbp-68h] BYREF
  PACL pDacl; // [rsp+A0h] [rbp-60h] BYREF
  PACL pSacl; // [rsp+A8h] [rbp-58h] BYREF
  HLOCAL hMem; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v44; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v45; // [rsp+D0h] [rbp-30h]
  __int128 v46; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v47; // [rsp+F0h] [rbp-10h]
  WORD pControl; // [rsp+158h] [rbp+58h] BYREF

  ppsidOwner = 0;
  pOwner = 0;
  ppsidGroup = 0;
  pGroup = 0;
  pacl = 0;
  pDacl = 0;
  ppSacl = 0;
  pSacl = 0;
  bDaclPresent = 0;
  v33 = 0;
  v34 = 0;
  v27 = 0;
  pcCountOfExplicitEntries = 0;
  SecurityDescriptor = 0;
  hMem = 0;
  dwRevision = 0;
  v29[0] = 0;
  pControl = 0;
  if ( ObjectType == SE_FILE_OBJECT || ObjectType == SE_REGISTRY_KEY )
  {
    NamedSecurityInfoW = InitializeObjectMapping();
    if ( NamedSecurityInfoW )
    {
      dprintf(
        5,
        (unsigned int)L"onecore\\base\\subsys\\sm\\sfc\\wrpdisable\\aclcomp.c",
        370,
        (unsigned int)L" Initialize() Failed, dwStatus = %08d \n");
      return NamedSecurityInfoW;
    }
    if ( ObjectType == SE_FILE_OBJECT )
    {
      v9 = g_pFileMapping;
    }
    else
    {
      v9 = 0;
      if ( ObjectType == SE_REGISTRY_KEY )
        v9 = (struct _GENERIC_MAPPING *)g_pKeyMapping;
    }
    *a4 = 0;
    pOwner = 0;
    ppsidOwner = 0;
    pGroup = 0;
    ppsidGroup = 0;
    pDacl = 0;
    pacl = 0;
    pSacl = 0;
    ppSacl = 0;
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
    {
      LastError = GetLastError();
      v11 = 396;
LABEL_12:
      v12 = L"ConvertStringSDtoSD failed with error %08d \n";
LABEL_13:
      NamedSecurityInfoW = LastError;
LABEL_14:
      dprintf(5, (unsigned int)L"onecore\\base\\subsys\\sm\\sfc\\wrpdisable\\aclcomp.c", v11, (_DWORD)v12);
      goto LABEL_20;
    }
    if ( !GetSecurityDescriptorControl(SecurityDescriptor, &pControl, &dwRevision) )
    {
      LastError = GetLastError();
      v12 = L" GetSecurityDescriptorControl failed for Target SDDL %08d \n";
      v11 = 406;
      goto LABEL_13;
    }
    if ( (pControl & 0x1000) == 0 )
    {
      dprintf(
        5,
        (unsigned int)L"onecore\\base\\subsys\\sm\\sfc\\wrpdisable\\aclcomp.c",
        418,
        (unsigned int)L" Target SDDL %ws doesnt have a protected dacl-- dont care, return matched\n");
      goto LABEL_19;
    }
    NamedSecurityInfoW = GetNamedSecurityInfoW(
                           pObjectName,
                           ObjectType,
                           0xFu,
                           &ppsidOwner,
                           &ppsidGroup,
                           &pacl,
                           &ppSacl,
                           &hMem);
    if ( NamedSecurityInfoW )
    {
      dprintf(
        5,
        (unsigned int)L"onecore\\base\\subsys\\sm\\sfc\\wrpdisable\\aclcomp.c",
        435,
        (unsigned int)L"GetNamedSecurityInfo failed with error %08d for object %ws \n");
      goto LABEL_20;
    }
    if ( !GetSecurityDescriptorControl(hMem, v29, &dwRevision) )
    {
      LastError = GetLastError();
      v12 = L" GetSecurityDescriptorControl failed for Object SDDL %08d \n";
      v11 = 444;
      goto LABEL_13;
    }
    if ( (v29[0] & 0x1000) == 0 )
    {
      v12 = L" Object SD doesnt have a protected DACL\n";
      v11 = 452;
      goto LABEL_14;
    }
    if ( !GetSecurityDescriptorOwner(SecurityDescriptor, &pOwner, (LPBOOL)&dwRevision) )
    {
      LastError = GetLastError();
      v11 = 464;
      goto LABEL_12;
    }
    if ( !(unsigned int)CompareSid(ppsidOwner, pOwner) )
    {
      v12 = L"Owner didnt match \n";
      v11 = 472;
      goto LABEL_14;
    }
    if ( !GetSecurityDescriptorGroup(SecurityDescriptor, &pGroup, (LPBOOL)&dwRevision) )
    {
      LastError = GetLastError();
      v11 = 483;
      goto LABEL_12;
    }
    if ( !(unsigned int)CompareSid(ppsidGroup, pGroup) )
    {
      v12 = L"Group didnt match \n";
      v11 = 491;
      goto LABEL_14;
    }
    if ( !GetSecurityDescriptorDacl(SecurityDescriptor, &bDaclPresent, &pDacl, (LPBOOL)&dwRevision) )
    {
      LastError = GetLastError();
      v11 = 501;
      goto LABEL_12;
    }
    if ( bDaclPresent )
    {
      v14 = pacl;
      if ( !pacl )
      {
        dprintf(
          5,
          (unsigned int)L"onecore\\base\\subsys\\sm\\sfc\\wrpdisable\\aclcomp.c",
          509,
          (unsigned int)L"Target SDDL has a DACL but the object doesnt\n");
        *a4 = 0;
        goto LABEL_20;
      }
      if ( !pDacl )
      {
LABEL_52:
        if ( v14 )
        {
          NamedSecurityInfoW = GetExplicitEntriesFromAclW(v14, &v27, (PEXPLICIT_ACCESS_W *)&v33);
          if ( NamedSecurityInfoW )
          {
            v12 = L"GetExplicitEntriesFromAcl for object dacl failed with error %08d \n";
            v11 = 536;
            goto LABEL_14;
          }
        }
        v15 = v27;
        if ( v27 != pcCountOfExplicitEntries )
          goto LABEL_20;
        for ( i = 0; i < v15; ++i )
        {
          v17 = 48LL * i;
          RtlMapGenericMask((PACCESS_MASK)((char *)v33 + v17), v9);
          RtlMapGenericMask((PACCESS_MASK)((char *)v34 + v17), v9);
          if ( *(_DWORD *)((char *)v33 + v17) != *(_DWORD *)((char *)v34 + v17)
            || *(_DWORD *)((char *)v33 + v17 + 4) != *(_DWORD *)((char *)v34 + v17 + 4)
            || *(_DWORD *)((char *)v33 + v17 + 8) != *(_DWORD *)((char *)v34 + v17 + 8)
            || (v18 = *(_OWORD *)((char *)v34 + v17 + 32),
                v44 = *(_OWORD *)((char *)v34 + v17 + 16),
                v19 = *(_OWORD *)((char *)v33 + v17 + 16),
                v45 = v18,
                v20 = *(_OWORD *)((char *)v33 + v17 + 32),
                v46 = v19,
                v47 = v20,
                !(unsigned int)CompareTrustee(&v46, &v44)) )
          {
            v12 = L"Ace %d didnt match\n";
            v11 = 563;
            goto LABEL_14;
          }
          v15 = v27;
        }
        pcCountOfExplicitEntries = 0;
        v27 = 0;
        if ( !GetSecurityDescriptorSacl(SecurityDescriptor, &bDaclPresent, &pSacl, (LPBOOL)&dwRevision) )
        {
          LastError = GetLastError();
          v11 = 577;
          goto LABEL_12;
        }
        if ( bDaclPresent )
        {
          v21 = ppSacl;
          if ( !ppSacl )
          {
            v12 = L" Target SD has a sacl but the object sd doesnt\n";
            v11 = 584;
            goto LABEL_14;
          }
          if ( !pSacl )
            goto LABEL_73;
          NamedSecurityInfoW = GetExplicitEntriesFromAclW(pSacl, &pcCountOfExplicitEntries, (PEXPLICIT_ACCESS_W *)&v34);
          if ( NamedSecurityInfoW )
          {
            v12 = L"GeExplicitEntriesFromAcl for targetsacl failed with error %08d \n";
            v11 = 594;
            goto LABEL_14;
          }
        }
        v21 = ppSacl;
LABEL_73:
        if ( v21 )
        {
          NamedSecurityInfoW = GetExplicitEntriesFromAclW(v21, &v27, (PEXPLICIT_ACCESS_W *)&v33);
          if ( NamedSecurityInfoW )
          {
            v12 = L"GetExplicitEntriesFromAcl for object dacl failed with error %08d \n";
            v11 = 607;
            goto LABEL_14;
          }
        }
        v22 = v27;
        if ( v27 != pcCountOfExplicitEntries )
          goto LABEL_20;
        for ( j = 0; j < v22; ++j )
        {
          if ( *((_DWORD *)v33 + 12 * j) != *((_DWORD *)v34 + 12 * j)
            || *((_DWORD *)v33 + 12 * j + 1) != *((_DWORD *)v34 + 12 * j + 1)
            || *((_DWORD *)v33 + 12 * j + 2) != *((_DWORD *)v34 + 12 * j + 2)
            || (v24 = *((_OWORD *)v34 + 3 * j + 2),
                v46 = *((_OWORD *)v34 + 3 * j + 1),
                v25 = *((_OWORD *)v33 + 3 * j + 1),
                v47 = v24,
                v26 = *((_OWORD *)v33 + 3 * j + 2),
                v44 = v25,
                v45 = v26,
                !(unsigned int)CompareTrustee(&v44, &v46)) )
          {
            v12 = L"Ace %d didnt match\n";
            v11 = 634;
            goto LABEL_14;
          }
          v22 = v27;
        }
LABEL_19:
        *a4 = 1;
        goto LABEL_20;
      }
      NamedSecurityInfoW = GetExplicitEntriesFromAclW(pDacl, &pcCountOfExplicitEntries, (PEXPLICIT_ACCESS_W *)&v34);
      if ( NamedSecurityInfoW )
      {
        v12 = L"GeExplicitEntriesFromAcl for targetdacl failed with error %08d \n";
        v11 = 522;
        goto LABEL_14;
      }
    }
    v14 = pacl;
    goto LABEL_52;
  }
  dprintf(
    5,
    (unsigned int)L"onecore\\base\\subsys\\sm\\sfc\\wrpdisable\\aclcomp.c",
    358,
    (unsigned int)L" CompareObjectSdToSddl: SeObjectType not supported \n");
  NamedSecurityInfoW = 87;
LABEL_20:
  if ( hMem )
    LocalFree(hMem);
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  if ( v33 )
    LocalFree(v33);
  if ( v34 )
    LocalFree(v34);
  return NamedSecurityInfoW;
}

```

## disassembly

```asm
0x180074e20  push    rbp
0x180074e22  push    rbx
0x180074e23  push    rsi
0x180074e24  push    rdi
0x180074e25  push    r12
0x180074e27  push    r13
0x180074e29  push    r14
0x180074e2b  push    r15
0x180074e2d  lea     rbp, [rsp-8]
0x180074e32  sub     rsp, 108h
0x180074e39  xor     r13d, r13d
0x180074e3c  mov     r12, r9
0x180074e3f  mov     [rbp+40h+ppsidOwner], r13
0x180074e43  mov     rsi, r8
0x180074e46  mov     [rbp+40h+pOwner], r13
0x180074e4a  mov     edi, edx
0x180074e4c  mov     [rbp+40h+var_A8], r13
0x180074e50  mov     r15, rcx
0x180074e53  mov     [rbp+40h+pGroup], r13
0x180074e57  mov     [rsp+140h+pacl], r13
0x180074e5c  mov     [rbp+40h+pDacl], r13
0x180074e60  mov     [rsp+140h+var_C8], r13
0x180074e65  mov     [rbp+40h+pSacl], r13
0x180074e69  mov     [rsp+140h+bDaclPresent], r13d
0x180074e6e  mov     [rsp+140h+var_E0], r13
0x180074e73  mov     [rsp+140h+var_D8], r13
0x180074e78  mov     [rsp+140h+var_100], r13d
0x180074e7d  mov     [rsp+140h+pcCountOfExplicitEntries], r13d
0x180074e82  mov     [rsp+140h+SecurityDescriptor], r13
0x180074e87  mov     [rbp+40h+hMem], r13
0x180074e8b  mov     [rsp+140h+dwRevision], r13d
0x180074e90  mov     [rsp+140h+var_F8], r13w
0x180074e96  mov     [rbp+40h+pControl], r13w
0x180074e9b  cmp     edx, 1
0x180074e9e  jz      short loc_180074ECB
0x180074ea0  cmp     edx, 4
0x180074ea3  jz      short loc_180074ECB
0x180074ea5  lea     r9, aCompareobjects_0; " CompareObjectSdToSddl: SeObjectType no"...
0x180074eac  mov     r8d, 166h
0x180074eb2  lea     rdx, aOnecoreBaseSub_0; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x180074eb9  lea     ecx, [r13+5]
0x180074ebd  call    dprintf
0x180074ec2  lea     ebx, [r13+57h]
0x180074ec6  jmp     loc_180075003
0x180074ecb  call    InitializeObjectMapping
0x180074ed0  mov     ebx, eax
0x180074ed2  test    eax, eax
0x180074ed4  jz      short loc_180074EFD
0x180074ed6  lea     r9, aInitializeFail; " Initialize() Failed, dwStatus = %08d "...
0x180074edd  mov     dword ptr [rsp+140h+ppsidGroup], eax
0x180074ee1  mov     r8d, 172h
0x180074ee7  lea     rdx, aOnecoreBaseSub_0; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x180074eee  mov     ecx, 5
0x180074ef3  call    dprintf
0x180074ef8  jmp     loc_18007505A
0x180074efd  cmp     edi, 1
0x180074f00  jnz     short loc_180074F0B
0x180074f02  mov     r14, cs:g_pFileMapping
0x180074f09  jmp     short loc_180074F19
0x180074f0b  cmp     edi, 4
0x180074f0e  mov     r14, r13
0x180074f11  cmovz   r14, cs:g_pKeyMapping
0x180074f19  xor     r9d, r9d; SecurityDescriptorSize
0x180074f1c  mov     [r12], r13d
0x180074f20  lea     r8, [rsp+140h+SecurityDescriptor]; SecurityDescriptor
0x180074f25  mov     [rbp+40h+pOwner], r13
0x180074f29  mov     rcx, rsi; StringSecurityDescriptor
0x180074f2c  mov     [rbp+40h+ppsidOwner], r13
0x180074f30  mov     [rbp+40h+pGroup], r13
0x180074f34  lea     edx, [r9+1]; StringSDRevision
0x180074f38  mov     [rbp+40h+var_A8], r13
0x180074f3c  mov     [rbp+40h+pDacl], r13
0x180074f40  mov     [rsp+140h+pacl], r13
0x180074f45  mov     [rbp+40h+pSacl], r13
0x180074f49  mov     [rsp+140h+var_C8], r13
0x180074f4e  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180074f55  nop     dword ptr [rax+rax+00h]
0x180074f5a  test    eax, eax
0x180074f5c  jnz     short loc_180074F90
0x180074f5e  call    cs:__imp_GetLastError
0x180074f65  nop     dword ptr [rax+rax+00h]
0x180074f6a  mov     r8d, 18Ch
0x180074f70  lea     r9, aConvertstrings_1; "ConvertStringSDtoSD failed with error %"...
0x180074f77  mov     ebx, eax
0x180074f79  mov     dword ptr [rsp+140h+ppsidGroup], eax
0x180074f7d  lea     rdx, aOnecoreBaseSub_0; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x180074f84  mov     ecx, 5
0x180074f89  call    dprintf
0x180074f8e  jmp     short loc_180075003
0x180074f90  mov     rcx, [rsp+140h+SecurityDescriptor]; pSecurityDescriptor
0x180074f95  lea     r8, [rsp+140h+dwRevision]; lpdwRevision
0x180074f9a  lea     rdx, [rbp+40h+pControl]; pControl
0x180074f9e  call    cs:__imp_GetSecurityDescriptorControl
0x180074fa5  nop     dword ptr [rax+rax+00h]
0x180074faa  test    eax, eax
0x180074fac  jnz     short loc_180074FC9
0x180074fae  call    cs:__imp_GetLastError
0x180074fb5  nop     dword ptr [rax+rax+00h]
0x180074fba  lea     r9, aGetsecuritydes_5; " GetSecurityDescriptorControl failed fo"...
0x180074fc1  mov     r8d, 196h
0x180074fc7  jmp     short loc_180074F77
0x180074fc9  mov     eax, 1000h
0x180074fce  test    [rbp+40h+pControl], ax
0x180074fd2  jnz     loc_180075071
0x180074fd8  lea     r9, aTargetSddlWsDo; " Target SDDL %ws doesnt have a protecte"...
0x180074fdf  mov     [rsp+140h+ppsidGroup], rsi
0x180074fe4  mov     r8d, 1A2h
0x180074fea  lea     rdx, aOnecoreBaseSub_0; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x180074ff1  mov     ecx, 5
0x180074ff6  call    dprintf
0x180074ffb  mov     dword ptr [r12], 1
0x180075003  mov     rcx, [rbp+40h+hMem]; hMem
0x180075007  test    rcx, rcx
0x18007500a  jz      short loc_180075018
0x18007500c  call    cs:__imp_LocalFree
0x180075013  nop     dword ptr [rax+rax+00h]
0x180075018  mov     rcx, [rsp+140h+SecurityDescriptor]; hMem
0x18007501d  test    rcx, rcx
0x180075020  jz      short loc_18007502E
0x180075022  call    cs:__imp_LocalFree
0x180075029  nop     dword ptr [rax+rax+00h]
0x18007502e  mov     rcx, [rsp+140h+var_E0]; hMem
0x180075033  test    rcx, rcx
0x180075036  jz      short loc_180075044
0x180075038  call    cs:__imp_LocalFree
0x18007503f  nop     dword ptr [rax+rax+00h]
0x180075044  mov     rcx, [rsp+140h+var_D8]; hMem
0x180075049  test    rcx, rcx
0x18007504c  jz      short loc_18007505A
0x18007504e  call    cs:__imp_LocalFree
0x180075055  nop     dword ptr [rax+rax+00h]
0x18007505a  mov     eax, ebx
0x18007505c  add     rsp, 108h
0x180075063  pop     r15
0x180075065  pop     r14
0x180075067  pop     r13
0x180075069  pop     r12
0x18007506b  pop     rdi
0x18007506c  pop     rsi
0x18007506d  pop     rbx
0x18007506e  pop     rbp
0x18007506f  retn
0x180075071  lea     rax, [rbp+40h+hMem]
0x180075075  mov     r8d, 0Fh; SecurityInfo
0x18007507b  mov     [rsp+140h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x180075080  lea     r9, [rbp+40h+ppsidOwner]; ppsidOwner
0x180075084  lea     rax, [rsp+140h+var_C8]
0x180075089  mov     edx, edi; ObjectType
0x18007508b  mov     [rsp+140h+ppSacl], rax; ppSacl
0x180075090  mov     rcx, r15; pObjectName
0x180075093  lea     rax, [rsp+140h+pacl]
0x180075098  mov     [rsp+140h+ppDacl], rax; ppDacl
0x18007509d  lea     rax, [rbp+40h+var_A8]
0x1800750a1  mov     [rsp+140h+ppsidGroup], rax; ppsidGroup
0x1800750a6  call    cs:__imp_GetNamedSecurityInfoW
0x1800750ad  nop     dword ptr [rax+rax+00h]
0x1800750b2  mov     ebx, eax
0x1800750b4  test    eax, eax
0x1800750b6  jz      short loc_1800750E4
0x1800750b8  mov     [rsp+140h+ppDacl], r15
0x1800750bd  lea     r9, aGetnamedsecuri_0; "GetNamedSecurityInfo failed with error "...
0x1800750c4  mov     r8d, 1B3h
0x1800750ca  mov     dword ptr [rsp+140h+ppsidGroup], eax
0x1800750ce  lea     rdx, aOnecoreBaseSub_0; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x1800750d5  mov     ecx, 5
0x1800750da  call    dprintf
0x1800750df  jmp     loc_180075003
0x1800750e4  mov     rcx, [rbp+40h+hMem]; pSecurityDescriptor
0x1800750e8  lea     r8, [rsp+140h+dwRevision]; lpdwRevision
0x1800750ed  lea     rdx, [rsp+140h+var_F8]; pControl
0x1800750f2  call    cs:__imp_GetSecurityDescriptorControl
0x1800750f9  nop     dword ptr [rax+rax+00h]
0x1800750fe  test    eax, eax
0x180075100  jnz     short loc_180075120
0x180075102  call    cs:__imp_GetLastError
0x180075109  nop     dword ptr [rax+rax+00h]
0x18007510e  lea     r9, aGetsecuritydes_4; " GetSecurityDescriptorControl failed fo"...
0x180075115  mov     r8d, 1BCh
0x18007511b  jmp     loc_180074F77
0x180075120  mov     eax, 1000h
0x180075125  test    [rsp+140h+var_F8], ax
0x18007512a  jnz     short loc_18007514F
0x18007512c  lea     r9, aObjectSdDoesnt; " Object SD doesnt have a protected DACL"...
0x180075133  mov     r8d, 1C4h
0x180075139  lea     rdx, aOnecoreBaseSub_0; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x180075140  mov     ecx, 5
0x180075145  call    dprintf
0x18007514a  jmp     loc_180075003
0x18007514f  mov     rcx, [rsp+140h+SecurityDescriptor]; pSecurityDescriptor
0x180075154  lea     r8, [rsp+140h+dwRevision]; lpbOwnerDefaulted
0x180075159  lea     rdx, [rbp+40h+pOwner]; pOwner
0x18007515d  call    cs:__imp_GetSecurityDescriptorOwner
0x180075164  nop     dword ptr [rax+rax+00h]
0x180075169  test    eax, eax
0x18007516b  jnz     short loc_180075184
0x18007516d  call    cs:__imp_GetLastError
0x180075174  nop     dword ptr [rax+rax+00h]
0x180075179  mov     r8d, 1D0h
0x18007517f  jmp     loc_180074F70
0x180075184  mov     rdx, [rbp+40h+pOwner]
0x180075188  mov     rcx, [rbp+40h+ppsidOwner]
0x18007518c  call    CompareSid
0x180075191  test    eax, eax
0x180075193  jnz     short loc_1800751A4
0x180075195  lea     r9, aOwnerDidntMatc; "Owner didnt match \n"
0x18007519c  mov     r8d, 1D8h
0x1800751a2  jmp     short loc_180075139
0x1800751a4  mov     rcx, [rsp+140h+SecurityDescriptor]; pSecurityDescriptor
0x1800751a9  lea     r8, [rsp+140h+dwRevision]; lpbGroupDefaulted
0x1800751ae  lea     rdx, [rbp+40h+pGroup]; pGroup
0x1800751b2  call    cs:__imp_GetSecurityDescriptorGroup
0x1800751b9  nop     dword ptr [rax+rax+00h]
0x1800751be  test    eax, eax
0x1800751c0  jnz     short loc_1800751D9
0x1800751c2  call    cs:__imp_GetLastError
0x1800751c9  nop     dword ptr [rax+rax+00h]
0x1800751ce  mov     r8d, 1E3h
0x1800751d4  jmp     loc_180074F70
0x1800751d9  mov     rdx, [rbp+40h+pGroup]
0x1800751dd  mov     rcx, [rbp+40h+var_A8]
0x1800751e1  call    CompareSid
0x1800751e6  test    eax, eax
0x1800751e8  jnz     short loc_1800751FC
0x1800751ea  lea     r9, aGroupDidntMatc; "Group didnt match \n"
0x1800751f1  mov     r8d, 1EBh
0x1800751f7  jmp     loc_180075139
0x1800751fc  mov     rcx, [rsp+140h+SecurityDescriptor]; pSecurityDescriptor
0x180075201  lea     r9, [rsp+140h+dwRevision]; lpbDaclDefaulted
0x180075206  lea     r8, [rbp+40h+pDacl]; pDacl
0x18007520a  lea     rdx, [rsp+140h+bDaclPresent]; lpbDaclPresent
0x18007520f  call    cs:__imp_GetSecurityDescriptorDacl
0x180075216  nop     dword ptr [rax+rax+00h]
0x18007521b  test    eax, eax
0x18007521d  jnz     short loc_180075236
0x18007521f  call    cs:__imp_GetLastError
0x180075226  nop     dword ptr [rax+rax+00h]
0x18007522b  mov     r8d, 1F5h
0x180075231  jmp     loc_180074F70
0x180075236  cmp     [rsp+140h+bDaclPresent], r13d
0x18007523b  jz      short loc_1800752A8
0x18007523d  mov     rcx, [rsp+140h+pacl]
0x180075242  test    rcx, rcx
0x180075245  jnz     short loc_18007526E
0x180075247  lea     r9, aTargetSddlHasA; "Target SDDL has a DACL but the object d"...
0x18007524e  mov     r8d, 1FDh
0x180075254  lea     rdx, aOnecoreBaseSub_0; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x18007525b  mov     ecx, 5
0x180075260  call    dprintf
0x180075265  mov     [r12], r13d
0x180075269  jmp     loc_180075003
0x18007526e  mov     rax, [rbp+40h+pDacl]
0x180075272  test    rax, rax
0x180075275  jz      short loc_1800752AD
0x180075277  lea     r8, [rsp+140h+var_D8]; pListOfExplicitEntries
0x18007527c  mov     rcx, rax; pacl
0x18007527f  lea     rdx, [rsp+140h+pcCountOfExplicitEntries]; pcCountOfExplicitEntries
0x180075284  call    cs:__imp_GetExplicitEntriesFromAclW
0x18007528b  nop     dword ptr [rax+rax+00h]
0x180075290  mov     ebx, eax
0x180075292  test    eax, eax
0x180075294  jz      short loc_1800752A8
0x180075296  lea     r9, aGeexplicitentr_0; "GeExplicitEntriesFromAcl for targetdacl"...
0x18007529d  mov     r8d, 20Ah
0x1800752a3  jmp     loc_180074F79
0x1800752a8  mov     rcx, [rsp+140h+pacl]; pacl
0x1800752ad  test    rcx, rcx
0x1800752b0  jz      short loc_1800752E0
0x1800752b2  lea     r8, [rsp+140h+var_E0]; pListOfExplicitEntries
0x1800752b7  lea     rdx, [rsp+140h+var_100]; pcCountOfExplicitEntries
0x1800752bc  call    cs:__imp_GetExplicitEntriesFromAclW
0x1800752c3  nop     dword ptr [rax+rax+00h]
0x1800752c8  mov     ebx, eax
0x1800752ca  test    eax, eax
0x1800752cc  jz      short loc_1800752E0
0x1800752ce  lea     r9, aGetexplicitent_0; "GetExplicitEntriesFromAcl for object da"...
0x1800752d5  mov     r8d, 218h
0x1800752db  jmp     loc_180074F79
0x1800752e0  mov     eax, [rsp+140h+var_100]
0x1800752e4  cmp     eax, [rsp+140h+pcCountOfExplicitEntries]
0x1800752e8  jnz     loc_180075003
0x1800752ee  mov     esi, r13d
0x1800752f1  cmp     esi, eax
0x1800752f3  jnb     loc_1800753AD
0x1800752f9  mov     rcx, [rsp+140h+var_E0]
0x1800752fe  mov     rdx, r14; GenericMapping
0x180075301  mov     eax, esi
0x180075303  lea     rdi, [rax+rax*2]
0x180075307  shl     rdi, 4
0x18007530b  add     rcx, rdi; AccessMask
0x18007530e  call    cs:__imp_RtlMapGenericMask
0x180075315  nop     dword ptr [rax+rax+00h]
0x18007531a  mov     rcx, [rsp+140h+var_D8]
0x18007531f  mov     rdx, r14; GenericMapping
0x180075322  add     rcx, rdi; AccessMask
0x180075325  call    cs:__imp_RtlMapGenericMask
0x18007532c  nop     dword ptr [rax+rax+00h]
0x180075331  mov     rcx, [rsp+140h+var_D8]
0x180075336  mov     rdx, [rsp+140h+var_E0]
0x18007533b  mov     eax, [rdi+rcx]
0x18007533e  cmp     [rdi+rdx], eax
  ... truncated ...
```
