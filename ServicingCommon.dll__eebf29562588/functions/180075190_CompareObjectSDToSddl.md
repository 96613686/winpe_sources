# CompareObjectSDToSddl

- ea: `0x180075190`
- end: `0x180075896`
- name: `CompareObjectSDToSddl`
- size: `1798`
- prototype: `__int64 __fastcall(LPCWSTR pObjectName, SE_OBJECT_TYPE ObjectType, LPCWSTR StringSecurityDescriptor)`
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180075190`
- `0x18007589c`
- `0x1800758d4`
- `0x180075b78`
- `0x180077058`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800752ce`
- `KERNEL32!GetLastError` at `0x18007531e`
- `KERNEL32!GetLastError` at `0x180075472`
- `KERNEL32!GetLastError` at `0x1800754dd`
- `KERNEL32!GetLastError` at `0x180075532`
- `KERNEL32!GetLastError` at `0x18007558f`
- `KERNEL32!GetLastError` at `0x18007574a`
- `KERNEL32!GetLastError` at `0x1800752ce`
- `KERNEL32!GetLastError` at `0x18007531e`
- `KERNEL32!GetLastError` at `0x180075472`
- `KERNEL32!GetLastError` at `0x1800754dd`
- `KERNEL32!GetLastError` at `0x180075532`
- `KERNEL32!GetLastError` at `0x18007558f`
- `KERNEL32!GetLastError` at `0x18007574a`
- `KERNEL32!LocalFree` at `0x18007537c`
- `KERNEL32!LocalFree` at `0x180075392`
- `KERNEL32!LocalFree` at `0x1800753a8`
- `KERNEL32!LocalFree` at `0x1800753be`
- `KERNEL32!LocalFree` at `0x18007537c`
- `KERNEL32!LocalFree` at `0x180075392`
- `KERNEL32!LocalFree` at `0x1800753a8`
- `KERNEL32!LocalFree` at `0x1800753be`
- `ntdll!RtlMapGenericMask` at `0x18007567e`
- `ntdll!RtlMapGenericMask` at `0x180075695`
- `ntdll!RtlMapGenericMask` at `0x18007567e`
- `ntdll!RtlMapGenericMask` at `0x180075695`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x180075416`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x180075416`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x18007530e`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x180075462`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x18007530e`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x180075462`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x18007573a`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x18007573a`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x18007557f`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x18007557f`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800752be`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800752be`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x1800754cd`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x1800754cd`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x180075522`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x180075522`
- `ADVAPI32!GetExplicitEntriesFromAclW` at `0x1800755f4`
- `ADVAPI32!GetExplicitEntriesFromAclW` at `0x18007562c`
- `ADVAPI32!GetExplicitEntriesFromAclW` at `0x18007579a`
- `ADVAPI32!GetExplicitEntriesFromAclW` at `0x1800757d2`
- `ADVAPI32!GetExplicitEntriesFromAclW` at `0x1800755f4`
- `ADVAPI32!GetExplicitEntriesFromAclW` at `0x18007562c`
- `ADVAPI32!GetExplicitEntriesFromAclW` at `0x18007579a`
- `ADVAPI32!GetExplicitEntriesFromAclW` at `0x1800757d2`

## string_xrefs

- `0x180075222`: `onecore\base\subsys\sm\sfc\wrpdisable\aclcomp.c`
- `0x180075257`: `onecore\base\subsys\sm\sfc\wrpdisable\aclcomp.c`
- `0x1800752ed`: `onecore\base\subsys\sm\sfc\wrpdisable\aclcomp.c`
- `0x18007535a`: `onecore\base\subsys\sm\sfc\wrpdisable\aclcomp.c`
- `0x18007543e`: `onecore\base\subsys\sm\sfc\wrpdisable\aclcomp.c`
- `0x1800754a9`: `onecore\base\subsys\sm\sfc\wrpdisable\aclcomp.c`
- `0x1800755c4`: `onecore\base\subsys\sm\sfc\wrpdisable\aclcomp.c`
- `0x180075215`: ` CompareObjectSdToSddl: SeObjectType not supported \n`
- `0x180075348`: ` Target SDDL %ws doesnt have a protected dacl-- dont care, return matched\n`
- `0x18007532a`: ` GetSecurityDescriptorControl failed for Target SDDL %08d \n`
- `0x18007547e`: ` GetSecurityDescriptorControl failed for Object SDDL %08d \n`
- `0x18007542d`: `GetNamedSecurityInfo failed with error %08d for object %ws \n`
- `0x18007549c`: ` Object SD doesnt have a protected DACL\n`
- `0x1800755b7`: `Target SDDL has a DACL but the object doesnt\n`
- `0x18007563e`: `GetExplicitEntriesFromAcl for object dacl failed with error %08d \n`
- `0x1800757e4`: `GetExplicitEntriesFromAcl for object dacl failed with error %08d \n`
- `0x180075606`: `GeExplicitEntriesFromAcl for targetdacl failed with error %08d \n`
- `0x180075772`: ` Target SD has a sacl but the object sd doesnt\n`
- `0x1800757ac`: `GeExplicitEntriesFromAcl for targetsacl failed with error %08d \n`

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
0x180075190  push    rbp
0x180075192  push    rbx
0x180075193  push    rsi
0x180075194  push    rdi
0x180075195  push    r12
0x180075197  push    r13
0x180075199  push    r14
0x18007519b  push    r15
0x18007519d  lea     rbp, [rsp-8]
0x1800751a2  sub     rsp, 108h
0x1800751a9  xor     r13d, r13d
0x1800751ac  mov     r12, r9
0x1800751af  mov     [rbp+40h+ppsidOwner], r13
0x1800751b3  mov     rsi, r8
0x1800751b6  mov     [rbp+40h+pOwner], r13
0x1800751ba  mov     edi, edx
0x1800751bc  mov     [rbp+40h+var_A8], r13
0x1800751c0  mov     r15, rcx
0x1800751c3  mov     [rbp+40h+pGroup], r13
0x1800751c7  mov     [rsp+140h+pacl], r13
0x1800751cc  mov     [rbp+40h+pDacl], r13
0x1800751d0  mov     [rsp+140h+var_C8], r13
0x1800751d5  mov     [rbp+40h+pSacl], r13
0x1800751d9  mov     [rsp+140h+bDaclPresent], r13d
0x1800751de  mov     [rsp+140h+var_E0], r13
0x1800751e3  mov     [rsp+140h+var_D8], r13
0x1800751e8  mov     [rsp+140h+var_100], r13d
0x1800751ed  mov     [rsp+140h+pcCountOfExplicitEntries], r13d
0x1800751f2  mov     [rsp+140h+SecurityDescriptor], r13
0x1800751f7  mov     [rbp+40h+hMem], r13
0x1800751fb  mov     [rsp+140h+dwRevision], r13d
0x180075200  mov     [rsp+140h+var_F8], r13w
0x180075206  mov     [rbp+40h+pControl], r13w
0x18007520b  cmp     edx, 1
0x18007520e  jz      short loc_18007523B
0x180075210  cmp     edx, 4
0x180075213  jz      short loc_18007523B
0x180075215  lea     r9, aCompareobjects_0; " CompareObjectSdToSddl: SeObjectType no"...
0x18007521c  mov     r8d, 166h
0x180075222  lea     rdx, aOnecoreBaseSub_0; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x180075229  lea     ecx, [r13+5]
0x18007522d  call    dprintf
0x180075232  lea     ebx, [r13+57h]
0x180075236  jmp     loc_180075373
0x18007523b  call    InitializeObjectMapping
0x180075240  mov     ebx, eax
0x180075242  test    eax, eax
0x180075244  jz      short loc_18007526D
0x180075246  lea     r9, aInitializeFail; " Initialize() Failed, dwStatus = %08d "...
0x18007524d  mov     dword ptr [rsp+140h+ppsidGroup], eax
0x180075251  mov     r8d, 172h
0x180075257  lea     rdx, aOnecoreBaseSub_0; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x18007525e  mov     ecx, 5
0x180075263  call    dprintf
0x180075268  jmp     loc_1800753CA
0x18007526d  cmp     edi, 1
0x180075270  jnz     short loc_18007527B
0x180075272  mov     r14, cs:g_pFileMapping
0x180075279  jmp     short loc_180075289
0x18007527b  cmp     edi, 4
0x18007527e  mov     r14, r13
0x180075281  cmovz   r14, cs:g_pKeyMapping
0x180075289  xor     r9d, r9d; SecurityDescriptorSize
0x18007528c  mov     [r12], r13d
0x180075290  lea     r8, [rsp+140h+SecurityDescriptor]; SecurityDescriptor
0x180075295  mov     [rbp+40h+pOwner], r13
0x180075299  mov     rcx, rsi; StringSecurityDescriptor
0x18007529c  mov     [rbp+40h+ppsidOwner], r13
0x1800752a0  mov     [rbp+40h+pGroup], r13
0x1800752a4  lea     edx, [r9+1]; StringSDRevision
0x1800752a8  mov     [rbp+40h+var_A8], r13
0x1800752ac  mov     [rbp+40h+pDacl], r13
0x1800752b0  mov     [rsp+140h+pacl], r13
0x1800752b5  mov     [rbp+40h+pSacl], r13
0x1800752b9  mov     [rsp+140h+var_C8], r13
0x1800752be  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800752c5  nop     dword ptr [rax+rax+00h]
0x1800752ca  test    eax, eax
0x1800752cc  jnz     short loc_180075300
0x1800752ce  call    cs:__imp_GetLastError
0x1800752d5  nop     dword ptr [rax+rax+00h]
0x1800752da  mov     r8d, 18Ch
0x1800752e0  lea     r9, aConvertstrings_1; "ConvertStringSDtoSD failed with error %"...
0x1800752e7  mov     ebx, eax
0x1800752e9  mov     dword ptr [rsp+140h+ppsidGroup], eax
0x1800752ed  lea     rdx, aOnecoreBaseSub_0; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x1800752f4  mov     ecx, 5
0x1800752f9  call    dprintf
0x1800752fe  jmp     short loc_180075373
0x180075300  mov     rcx, [rsp+140h+SecurityDescriptor]; pSecurityDescriptor
0x180075305  lea     r8, [rsp+140h+dwRevision]; lpdwRevision
0x18007530a  lea     rdx, [rbp+40h+pControl]; pControl
0x18007530e  call    cs:__imp_GetSecurityDescriptorControl
0x180075315  nop     dword ptr [rax+rax+00h]
0x18007531a  test    eax, eax
0x18007531c  jnz     short loc_180075339
0x18007531e  call    cs:__imp_GetLastError
0x180075325  nop     dword ptr [rax+rax+00h]
0x18007532a  lea     r9, aGetsecuritydes_5; " GetSecurityDescriptorControl failed fo"...
0x180075331  mov     r8d, 196h
0x180075337  jmp     short loc_1800752E7
0x180075339  mov     eax, 1000h
0x18007533e  test    [rbp+40h+pControl], ax
0x180075342  jnz     loc_1800753E1
0x180075348  lea     r9, aTargetSddlWsDo; " Target SDDL %ws doesnt have a protecte"...
0x18007534f  mov     [rsp+140h+ppsidGroup], rsi
0x180075354  mov     r8d, 1A2h
0x18007535a  lea     rdx, aOnecoreBaseSub_0; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x180075361  mov     ecx, 5
0x180075366  call    dprintf
0x18007536b  mov     dword ptr [r12], 1
0x180075373  mov     rcx, [rbp+40h+hMem]; hMem
0x180075377  test    rcx, rcx
0x18007537a  jz      short loc_180075388
0x18007537c  call    cs:__imp_LocalFree
0x180075383  nop     dword ptr [rax+rax+00h]
0x180075388  mov     rcx, [rsp+140h+SecurityDescriptor]; hMem
0x18007538d  test    rcx, rcx
0x180075390  jz      short loc_18007539E
0x180075392  call    cs:__imp_LocalFree
0x180075399  nop     dword ptr [rax+rax+00h]
0x18007539e  mov     rcx, [rsp+140h+var_E0]; hMem
0x1800753a3  test    rcx, rcx
0x1800753a6  jz      short loc_1800753B4
0x1800753a8  call    cs:__imp_LocalFree
0x1800753af  nop     dword ptr [rax+rax+00h]
0x1800753b4  mov     rcx, [rsp+140h+var_D8]; hMem
0x1800753b9  test    rcx, rcx
0x1800753bc  jz      short loc_1800753CA
0x1800753be  call    cs:__imp_LocalFree
0x1800753c5  nop     dword ptr [rax+rax+00h]
0x1800753ca  mov     eax, ebx
0x1800753cc  add     rsp, 108h
0x1800753d3  pop     r15
0x1800753d5  pop     r14
0x1800753d7  pop     r13
0x1800753d9  pop     r12
0x1800753db  pop     rdi
0x1800753dc  pop     rsi
0x1800753dd  pop     rbx
0x1800753de  pop     rbp
0x1800753df  retn
0x1800753e1  lea     rax, [rbp+40h+hMem]
0x1800753e5  mov     r8d, 0Fh; SecurityInfo
0x1800753eb  mov     [rsp+140h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x1800753f0  lea     r9, [rbp+40h+ppsidOwner]; ppsidOwner
0x1800753f4  lea     rax, [rsp+140h+var_C8]
0x1800753f9  mov     edx, edi; ObjectType
0x1800753fb  mov     [rsp+140h+ppSacl], rax; ppSacl
0x180075400  mov     rcx, r15; pObjectName
0x180075403  lea     rax, [rsp+140h+pacl]
0x180075408  mov     [rsp+140h+ppDacl], rax; ppDacl
0x18007540d  lea     rax, [rbp+40h+var_A8]
0x180075411  mov     [rsp+140h+ppsidGroup], rax; ppsidGroup
0x180075416  call    cs:__imp_GetNamedSecurityInfoW
0x18007541d  nop     dword ptr [rax+rax+00h]
0x180075422  mov     ebx, eax
0x180075424  test    eax, eax
0x180075426  jz      short loc_180075454
0x180075428  mov     [rsp+140h+ppDacl], r15
0x18007542d  lea     r9, aGetnamedsecuri_0; "GetNamedSecurityInfo failed with error "...
0x180075434  mov     r8d, 1B3h
0x18007543a  mov     dword ptr [rsp+140h+ppsidGroup], eax
0x18007543e  lea     rdx, aOnecoreBaseSub_0; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x180075445  mov     ecx, 5
0x18007544a  call    dprintf
0x18007544f  jmp     loc_180075373
0x180075454  mov     rcx, [rbp+40h+hMem]; pSecurityDescriptor
0x180075458  lea     r8, [rsp+140h+dwRevision]; lpdwRevision
0x18007545d  lea     rdx, [rsp+140h+var_F8]; pControl
0x180075462  call    cs:__imp_GetSecurityDescriptorControl
0x180075469  nop     dword ptr [rax+rax+00h]
0x18007546e  test    eax, eax
0x180075470  jnz     short loc_180075490
0x180075472  call    cs:__imp_GetLastError
0x180075479  nop     dword ptr [rax+rax+00h]
0x18007547e  lea     r9, aGetsecuritydes_4; " GetSecurityDescriptorControl failed fo"...
0x180075485  mov     r8d, 1BCh
0x18007548b  jmp     loc_1800752E7
0x180075490  mov     eax, 1000h
0x180075495  test    [rsp+140h+var_F8], ax
0x18007549a  jnz     short loc_1800754BF
0x18007549c  lea     r9, aObjectSdDoesnt; " Object SD doesnt have a protected DACL"...
0x1800754a3  mov     r8d, 1C4h
0x1800754a9  lea     rdx, aOnecoreBaseSub_0; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x1800754b0  mov     ecx, 5
0x1800754b5  call    dprintf
0x1800754ba  jmp     loc_180075373
0x1800754bf  mov     rcx, [rsp+140h+SecurityDescriptor]; pSecurityDescriptor
0x1800754c4  lea     r8, [rsp+140h+dwRevision]; lpbOwnerDefaulted
0x1800754c9  lea     rdx, [rbp+40h+pOwner]; pOwner
0x1800754cd  call    cs:__imp_GetSecurityDescriptorOwner
0x1800754d4  nop     dword ptr [rax+rax+00h]
0x1800754d9  test    eax, eax
0x1800754db  jnz     short loc_1800754F4
0x1800754dd  call    cs:__imp_GetLastError
0x1800754e4  nop     dword ptr [rax+rax+00h]
0x1800754e9  mov     r8d, 1D0h
0x1800754ef  jmp     loc_1800752E0
0x1800754f4  mov     rdx, [rbp+40h+pOwner]
0x1800754f8  mov     rcx, [rbp+40h+ppsidOwner]
0x1800754fc  call    CompareSid
0x180075501  test    eax, eax
0x180075503  jnz     short loc_180075514
0x180075505  lea     r9, aOwnerDidntMatc; "Owner didnt match \n"
0x18007550c  mov     r8d, 1D8h
0x180075512  jmp     short loc_1800754A9
0x180075514  mov     rcx, [rsp+140h+SecurityDescriptor]; pSecurityDescriptor
0x180075519  lea     r8, [rsp+140h+dwRevision]; lpbGroupDefaulted
0x18007551e  lea     rdx, [rbp+40h+pGroup]; pGroup
0x180075522  call    cs:__imp_GetSecurityDescriptorGroup
0x180075529  nop     dword ptr [rax+rax+00h]
0x18007552e  test    eax, eax
0x180075530  jnz     short loc_180075549
0x180075532  call    cs:__imp_GetLastError
0x180075539  nop     dword ptr [rax+rax+00h]
0x18007553e  mov     r8d, 1E3h
0x180075544  jmp     loc_1800752E0
0x180075549  mov     rdx, [rbp+40h+pGroup]
0x18007554d  mov     rcx, [rbp+40h+var_A8]
0x180075551  call    CompareSid
0x180075556  test    eax, eax
0x180075558  jnz     short loc_18007556C
0x18007555a  lea     r9, aGroupDidntMatc; "Group didnt match \n"
0x180075561  mov     r8d, 1EBh
0x180075567  jmp     loc_1800754A9
0x18007556c  mov     rcx, [rsp+140h+SecurityDescriptor]; pSecurityDescriptor
0x180075571  lea     r9, [rsp+140h+dwRevision]; lpbDaclDefaulted
0x180075576  lea     r8, [rbp+40h+pDacl]; pDacl
0x18007557a  lea     rdx, [rsp+140h+bDaclPresent]; lpbDaclPresent
0x18007557f  call    cs:__imp_GetSecurityDescriptorDacl
0x180075586  nop     dword ptr [rax+rax+00h]
0x18007558b  test    eax, eax
0x18007558d  jnz     short loc_1800755A6
0x18007558f  call    cs:__imp_GetLastError
0x180075596  nop     dword ptr [rax+rax+00h]
0x18007559b  mov     r8d, 1F5h
0x1800755a1  jmp     loc_1800752E0
0x1800755a6  cmp     [rsp+140h+bDaclPresent], r13d
0x1800755ab  jz      short loc_180075618
0x1800755ad  mov     rcx, [rsp+140h+pacl]
0x1800755b2  test    rcx, rcx
0x1800755b5  jnz     short loc_1800755DE
0x1800755b7  lea     r9, aTargetSddlHasA; "Target SDDL has a DACL but the object d"...
0x1800755be  mov     r8d, 1FDh
0x1800755c4  lea     rdx, aOnecoreBaseSub_0; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x1800755cb  mov     ecx, 5
0x1800755d0  call    dprintf
0x1800755d5  mov     [r12], r13d
0x1800755d9  jmp     loc_180075373
0x1800755de  mov     rax, [rbp+40h+pDacl]
0x1800755e2  test    rax, rax
0x1800755e5  jz      short loc_18007561D
0x1800755e7  lea     r8, [rsp+140h+var_D8]; pListOfExplicitEntries
0x1800755ec  mov     rcx, rax; pacl
0x1800755ef  lea     rdx, [rsp+140h+pcCountOfExplicitEntries]; pcCountOfExplicitEntries
0x1800755f4  call    cs:__imp_GetExplicitEntriesFromAclW
0x1800755fb  nop     dword ptr [rax+rax+00h]
0x180075600  mov     ebx, eax
0x180075602  test    eax, eax
0x180075604  jz      short loc_180075618
0x180075606  lea     r9, aGeexplicitentr_0; "GeExplicitEntriesFromAcl for targetdacl"...
0x18007560d  mov     r8d, 20Ah
0x180075613  jmp     loc_1800752E9
0x180075618  mov     rcx, [rsp+140h+pacl]; pacl
0x18007561d  test    rcx, rcx
0x180075620  jz      short loc_180075650
0x180075622  lea     r8, [rsp+140h+var_E0]; pListOfExplicitEntries
0x180075627  lea     rdx, [rsp+140h+var_100]; pcCountOfExplicitEntries
0x18007562c  call    cs:__imp_GetExplicitEntriesFromAclW
0x180075633  nop     dword ptr [rax+rax+00h]
0x180075638  mov     ebx, eax
0x18007563a  test    eax, eax
0x18007563c  jz      short loc_180075650
0x18007563e  lea     r9, aGetexplicitent_0; "GetExplicitEntriesFromAcl for object da"...
0x180075645  mov     r8d, 218h
0x18007564b  jmp     loc_1800752E9
0x180075650  mov     eax, [rsp+140h+var_100]
0x180075654  cmp     eax, [rsp+140h+pcCountOfExplicitEntries]
0x180075658  jnz     loc_180075373
0x18007565e  mov     esi, r13d
0x180075661  cmp     esi, eax
0x180075663  jnb     loc_18007571D
0x180075669  mov     rcx, [rsp+140h+var_E0]
0x18007566e  mov     rdx, r14; GenericMapping
0x180075671  mov     eax, esi
0x180075673  lea     rdi, [rax+rax*2]
0x180075677  shl     rdi, 4
0x18007567b  add     rcx, rdi; AccessMask
0x18007567e  call    cs:__imp_RtlMapGenericMask
0x180075685  nop     dword ptr [rax+rax+00h]
0x18007568a  mov     rcx, [rsp+140h+var_D8]
0x18007568f  mov     rdx, r14; GenericMapping
0x180075692  add     rcx, rdi; AccessMask
0x180075695  call    cs:__imp_RtlMapGenericMask
0x18007569c  nop     dword ptr [rax+rax+00h]
0x1800756a1  mov     rcx, [rsp+140h+var_D8]
0x1800756a6  mov     rdx, [rsp+140h+var_E0]
0x1800756ab  mov     eax, [rdi+rcx]
0x1800756ae  cmp     [rdi+rdx], eax
  ... truncated ...
```
