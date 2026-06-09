# SaferIdentifyLevel

- ea: `0x180010c00`
- end: `0x18001153f`
- name: `SaferIdentifyLevel`
- size: `2367`
- prototype: `BOOL __stdcall(DWORD dwNumProperties, PSAFER_CODE_PROPERTIES pCodeProperties, SAFER_LEVEL_HANDLE *pLevelHandle, LPVOID lpReserved)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180010870`

## callees

- `0x18000cb10`
- `0x18000e4fc`
- `0x1800101bc`
- `0x1800102a8`
- `0x1800103f4`
- `0x180010564`
- `0x1800109ec`
- `0x180010c00`
- `0x180011548`
- `0x1800118c0`
- `0x180012fcc`
- `0x1800488f4`
- `0x180065036`
- `0x18006505a`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180010dda`
- `msvcrt!_wcsicmp` at `0x180010df5`
- `msvcrt!_wcsicmp` at `0x180010e0d`
- `msvcrt!_wcsicmp` at `0x180010e42`
- `msvcrt!_wcsicmp` at `0x180010dda`
- `msvcrt!_wcsicmp` at `0x180010df5`
- `msvcrt!_wcsicmp` at `0x180010e0d`
- `msvcrt!_wcsicmp` at `0x180010e42`
- `ntdll!RtlAllocateHandle` at `0x18001116e`
- `ntdll!RtlAllocateHandle` at `0x18001123a`
- `ntdll!RtlAllocateHandle` at `0x18001116e`
- `ntdll!RtlAllocateHandle` at `0x18001123a`
- `ntdll!RtlIsGenericTableEmpty` at `0x180010c8e`
- `ntdll!RtlIsGenericTableEmpty` at `0x180010c8e`
- `ntdll!NtQuerySystemInformation` at `0x1800113a8`
- `ntdll!NtQuerySystemInformation` at `0x1800113a8`
- `ntdll!RtlLeaveCriticalSection` at `0x180010f8f`
- `ntdll!RtlLeaveCriticalSection` at `0x180010f8f`
- `ntdll!RtlEnterCriticalSection` at `0x180010c74`
- `ntdll!RtlEnterCriticalSection` at `0x180010c74`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180010d10`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180010d10`
- `KERNEL32!BaseSetLastNTError` at `0x180011369`
- `KERNEL32!BaseSetLastNTError` at `0x180011369`
- `KERNEL32!CloseHandle` at `0x180011451`
- `KERNEL32!CloseHandle` at `0x180011451`
- `KERNEL32!CreateFileW` at `0x18001140d`
- `KERNEL32!CreateFileW` at `0x18001140d`

## string_xrefs

- `0x180010de8`: `WLDPMSI`
- `0x180010dd0`: `WLDPCONFIGCI`

## pseudocode

```c
BOOL __stdcall SaferIdentifyLevel(
        DWORD dwNumProperties,
        PSAFER_CODE_PROPERTIES pCodeProperties,
        SAFER_LEVEL_HANDLE *pLevelHandle,
        LPVOID lpReserved)
{
  BOOL v4; // r12d
  __int128 v5; // xmm6
  DWORD v8; // r15d
  int v9; // r14d
  DWORD i; // ecx
  __int64 v11; // rdx
  DWORD j; // ecx
  int IsV2PolicyPresent; // ebx
  ULONG *v14; // rdi
  unsigned int v15; // r15d
  DWORD k; // r14d
  int v17; // eax
  char v18; // si
  __int64 v19; // rcx
  __int64 v20; // rdx
  int v21; // r12d
  const wchar_t *v22; // rsi
  LPCWSTR v23; // r14
  int v24; // edx
  DWORD v25; // r15d
  wchar_t *ImagePath; // rax
  int LevelHandleFromRecord; // eax
  const wchar_t *v28; // rdx
  __int64 v30; // rcx
  __int64 v31; // rcx
  _DWORD *v32; // rax
  int v33; // r8d
  __int64 v34; // rdx
  PRTL_HANDLE_TABLE_ENTRY Handle; // rbx
  int v36; // r9d
  int v37; // ebx
  bool v38; // zf
  PRTL_HANDLE_TABLE_ENTRY v39; // rsi
  unsigned int v40; // r9d
  int v41; // eax
  int v42; // eax
  DWORD m; // r14d
  unsigned int v44; // edi
  __int64 v45; // rcx
  HANDLE hImageFileHandle; // rbx
  int v47; // r14d
  int v48; // esi
  unsigned int v49; // [rsp+48h] [rbp-39h] BYREF
  DWORD v50; // [rsp+4Ch] [rbp-35h]
  ULONG Index[2]; // [rsp+50h] [rbp-31h] BYREF
  int v52[4]; // [rsp+58h] [rbp-29h] BYREF
  __int128 SystemInformation; // [rsp+68h] [rbp-19h] BYREF
  __int128 Buf2; // [rsp+78h] [rbp-9h] BYREF
  WINBOOL IsMember[8]; // [rsp+88h] [rbp+7h] BYREF

  v4 = 0;
  IsMember[0] = 0;
  v5 = 0;
  Buf2 = 0;
  v52[0] = 0;
  v49 = 0;
  v8 = dwNumProperties;
  Index[0] = 0;
  LODWORD(SystemInformation) = 0;
  if ( !pLevelHandle )
  {
    IsV2PolicyPresent = -1073741819;
    goto LABEL_112;
  }
  if ( !g_bInitializedFirstTime )
  {
    IsV2PolicyPresent = -1073741823;
    goto LABEL_112;
  }
  v9 = 1;
  RtlEnterCriticalSection(&g_TableCritSec);
  if ( g_bNeedCacheReload )
  {
    IsV2PolicyPresent = CodeAuthzpImmediateReloadCacheTables();
    if ( IsV2PolicyPresent < 0 )
      goto LABEL_57;
    v9 = 0;
  }
  if ( RtlIsGenericTableEmpty(&g_CodeLevelObjTable) )
    goto LABEL_73;
  v50 = 0;
  if ( !lpReserved )
    goto LABEL_6;
  if ( !_wcsicmp((const wchar_t *)lpReserved, L"WLDPCONFIGCI") )
  {
    v18 = 1;
LABEL_115:
    v44 = 0x40000;
    *(_QWORD *)&SystemInformation = 8;
    if ( v18 || NtQuerySystemInformation(MaxSystemInfoClass|SystemProcessInformation, &SystemInformation, 8u, 0) < 0 )
    {
      DWORD1(SystemInformation) = -2147483644;
      v45 = 2147483652LL;
    }
    else
    {
      v45 = DWORD1(SystemInformation) | 0x80000000;
      DWORD1(SystemInformation) |= 0x80000000;
    }
    if ( (v45 & 0x80000004) == 0x80000000 )
    {
      v21 = 3;
    }
    else
    {
      hImageFileHandle = pCodeProperties->hImageFileHandle;
      v47 = 0;
      if ( !hImageFileHandle || hImageFileHandle == (HANDLE)-1LL )
      {
        v21 = 3;
        hImageFileHandle = CreateFileW(pCodeProperties->ImagePath, 1u, 5u, 0, 3u, 0, 0);
        if ( hImageFileHandle == (HANDLE)-1LL )
          hImageFileHandle = 0;
        else
          v47 = 1;
      }
      else
      {
        v21 = 3;
      }
      v48 = AiVerifyTrustedPublisherPolicy(hImageFileHandle);
      if ( v47 )
        CloseHandle(hImageFileHandle);
      if ( v48 < 0 )
        v44 = 0;
    }
    v5 = xmmword_18007ABE8;
    v14 = (ULONG *)CodeAuthzLevelObjpLookupByLevelId(v45, v44);
    goto LABEL_71;
  }
  v18 = 0;
  if ( !_wcsicmp((const wchar_t *)lpReserved, L"WLDPMSI") || !_wcsicmp((const wchar_t *)lpReserved, L"WLDPSCRIPT") )
    goto LABEL_115;
  IsV2PolicyPresent = SaferpIsV2PolicyPresent(&SystemInformation);
  if ( IsV2PolicyPresent < 0 )
    goto LABEL_57;
  if ( (_DWORD)SystemInformation )
  {
    IsV2PolicyPresent = SaferIdentifyLevel2(v8, pCodeProperties, lpReserved, Index);
    if ( IsV2PolicyPresent < 0 )
      goto LABEL_57;
    v20 = Index[0];
    goto LABEL_69;
  }
  if ( !_wcsicmp((const wchar_t *)lpReserved, L"APPX") )
  {
    v20 = 0x40000;
LABEL_69:
    v5 = xmmword_18007ABE8;
    v14 = (ULONG *)CodeAuthzLevelObjpLookupByLevelId(v19, v20);
    goto LABEL_70;
  }
LABEL_6:
  if ( v8 && pCodeProperties )
  {
    if ( pCodeProperties->cbSize == 176 )
    {
      for ( i = 0; i < v8; ++i )
      {
        v11 = i;
        if ( (unsigned __int64)pCodeProperties[v11].hImageFileHandle - 1 <= 0xFFFFFFFFFFFFFFFDuLL
          && !pCodeProperties[v11].ImagePath )
        {
          goto LABEL_100;
        }
      }
    }
    else
    {
      if ( pCodeProperties->cbSize != 136 )
      {
LABEL_100:
        IsV2PolicyPresent = -1073741811;
        goto LABEL_57;
      }
      for ( j = 0; j < v8; ++j )
      {
        v34 = 136LL * j;
        if ( *(unsigned __int64 *)((char *)&pCodeProperties->hImageFileHandle + v34) - 1 <= 0xFFFFFFFFFFFFFFFDuLL
          && !*(LPCWSTR *)((char *)&pCodeProperties->ImagePath + v34) )
        {
          goto LABEL_100;
        }
      }
    }
  }
  if ( !CheckTokenMembership(0, g_pAdminSid, IsMember) || !IsMember[0] || !(unsigned int)SaferpSkipPolicyForAdmins() )
  {
    if ( pCodeProperties && v8 )
    {
      if ( v9 )
      {
        if ( !g_dwNumHandlesAllocated )
        {
          IsV2PolicyPresent = SaferpReloadPolicyIfNeeded();
          if ( IsV2PolicyPresent < 0 )
            goto LABEL_57;
        }
      }
      v14 = 0;
      v15 = 0;
      if ( pCodeProperties->cbSize == 176 )
      {
        for ( k = 0; k < dwNumProperties; ++k )
        {
          SystemInformation = 0;
          *(_QWORD *)Index = 0;
          v17 = _CodeAuthzpIdentifyOneCodeAuthzLevel(
                  (__int64)&pCodeProperties[k],
                  (__int64)v52,
                  Index,
                  &SystemInformation,
                  &v49);
          IsV2PolicyPresent = v17;
          if ( v17 < 0 )
          {
            if ( v17 != -1073741275 )
              goto LABEL_57;
          }
          else if ( !v14 || v49 < v15 )
          {
            v5 = SystemInformation;
            v14 = *(ULONG **)Index;
            v15 = v49;
            Buf2 = SystemInformation;
            v50 = k;
          }
        }
      }
      else
      {
        if ( pCodeProperties->cbSize != 136 )
          goto LABEL_64;
        for ( m = 0; m < dwNumProperties; ++m )
        {
          SystemInformation = 0;
          *(_QWORD *)Index = 0;
          v42 = _CodeAuthzpIdentifyOneCodeAuthzLevel(
                  (__int64)pCodeProperties + 136 * m,
                  (__int64)v52,
                  Index,
                  &SystemInformation,
                  &v49);
          IsV2PolicyPresent = v42;
          if ( v42 < 0 )
          {
            if ( v42 != -1073741275 )
              goto LABEL_57;
          }
          else if ( !v14 || v49 < v15 )
          {
            v5 = SystemInformation;
            v14 = *(ULONG **)Index;
            v15 = v49;
            Buf2 = SystemInformation;
            v50 = m;
          }
        }
      }
      if ( v14 )
      {
        v8 = dwNumProperties;
        v21 = 3;
        goto LABEL_39;
      }
LABEL_64:
      IsV2PolicyPresent = -1073741275;
      goto LABEL_57;
    }
    v14 = (ULONG *)g_DefaultCodeLevel;
    if ( g_DefaultCodeLevel )
      goto LABEL_62;
LABEL_73:
    IsV2PolicyPresent = -1073741275;
    goto LABEL_57;
  }
  v14 = (ULONG *)CodeAuthzLevelObjpLookupByLevelId(v30, 0x40000);
LABEL_62:
  v5 = xmmword_18007AA70;
LABEL_70:
  v21 = 3;
LABEL_71:
  Buf2 = v5;
LABEL_39:
  v22 = L"default";
  v23 = L"Default";
  if ( !memcmp_0(&xmmword_18007AA70, &Buf2, 0x10u) )
  {
    if ( g_hKeyCustomRoot )
    {
      v24 = 3;
    }
    else if ( !g_DefaultCodeLevelUser || (v24 = 2, (ULONG *)g_DefaultCodeLevelUser != v14) )
    {
      v24 = 1;
    }
    if ( pCodeProperties && v8 )
    {
      v25 = v50;
      ImagePath = (wchar_t *)pCodeProperties[v50].ImagePath;
    }
    else
    {
      v25 = v50;
      ImagePath = 0;
    }
    LevelHandleFromRecord = CodeAuthzpCreateLevelHandleFromRecord(
                              (int)v14,
                              v24,
                              g_DefaultCodeLevelFlags,
                              v52[0],
                              0,
                              (__int64)&Buf2,
                              ImagePath,
                              (__int64)pLevelHandle);
    goto LABEL_47;
  }
  if ( !memcmp_0(&xmmword_18007ABD8, &Buf2, 0x10u) )
  {
    Index[0] = 0;
    if ( g_hKeyCustomRoot )
    {
      IsV2PolicyPresent = -1073741776;
    }
    else
    {
      Handle = RtlAllocateHandle(&g_LevelHandleTable, Index);
      if ( Handle )
      {
        ++g_dwNumHandlesAllocated;
        *pLevelHandle = (SAFER_LEVEL_HANDLE)(Index[0] | 0x74000000LL);
        memset_0((char *)&Handle->NextFree + 4, 0, 0x23Cu);
        v36 = v52[0];
        Handle->Flags = 1;
        Handle[1].Flags = *v14;
        HIDWORD(Handle[69].NextFree) = g_dwLevelHandleSequence;
        HIDWORD(Handle[1].NextFree) = 1;
        Handle[69].Flags = 0;
        Handle[70].Flags = v36;
        HIDWORD(Handle[70].NextFree) = 4;
        *(_OWORD *)&Handle[2].Flags = v5;
        LOWORD(Handle[4].Flags) = 0;
        IsV2PolicyPresent = 0;
      }
      else
      {
        IsV2PolicyPresent = -1073741670;
      }
    }
    v22 = L"certificate";
    goto LABEL_90;
  }
  if ( !memcmp_0(&xmmword_18007ABE8, &Buf2, 0x10u) )
  {
    Index[0] = 0;
    v37 = g_hKeyCustomRoot != 0 ? 3 : 1;
    if ( g_hKeyCustomRoot )
      v38 = v37 == 3;
    else
      v38 = v37 == 1;
    if ( v38 )
    {
      v39 = RtlAllocateHandle(&g_LevelHandleTable, Index);
      if ( v39 )
      {
        ++g_dwNumHandlesAllocated;
        *pLevelHandle = (SAFER_LEVEL_HANDLE)(Index[0] | 0x74000000LL);
        memset_0((char *)&v39->NextFree + 4, 0, 0x23Cu);
        v40 = v52[0];
        v39->Flags = 1;
        v39[1].Flags = *v14;
        v41 = g_dwLevelHandleSequence;
        HIDWORD(v39[1].NextFree) = v37;
        IsV2PolicyPresent = 0;
        HIDWORD(v39[69].NextFree) = v41;
        v39[69].Flags = 0;
        v39[70].NextFree = (struct _RTL_HANDLE_TABLE_ENTRY *)v40;
        *(_OWORD *)&v39[2].Flags = v5;
        LOWORD(v39[4].Flags) = 0;
      }
      else
      {
        IsV2PolicyPresent = -1073741670;
      }
    }
    else
    {
      IsV2PolicyPresent = -1073741776;
    }
    v22 = L"SRPv2";
    goto LABEL_90;
  }
  v32 = (_DWORD *)CodeAuthzIdentsLookupByGuid(v31, &Buf2);
  if ( !v32 )
  {
    IsV2PolicyPresent = -1073741790;
LABEL_90:
    v25 = v50;
    goto LABEL_48;
  }
  switch ( v32[4] )
  {
    case 1:
      v33 = v32[14];
      v22 = L"path";
      v49 = 1;
      v21 = 1;
      break;
    case 2:
      v33 = v32[44];
      v22 = L"hash";
      v21 = 2;
      break;
    case 3:
      v33 = v32[9];
      v22 = L"zone";
      break;
    default:
      v33 = 0;
      v21 = 0;
      break;
  }
  v25 = v50;
  LevelHandleFromRecord = CodeAuthzpCreateLevelHandleFromRecord(
                            (int)v14,
                            v32[6],
                            v33,
                            v52[0],
                            v21,
                            (__int64)&Buf2,
                            (wchar_t *)pCodeProperties[v50].ImagePath,
                            (__int64)pLevelHandle);
LABEL_47:
  IsV2PolicyPresent = LevelHandleFromRecord;
LABEL_48:
  v4 = IsV2PolicyPresent >= 0;
  if ( *v14 )
  {
    switch ( *v14 )
    {
      case 0x1000u:
        v28 = L"Untrusted";
        break;
      case 0x10000u:
        v28 = L"Restricted";
        break;
      case 0x20000u:
        v28 = L"Basic User";
        break;
      default:
        v28 = L"Unrestricted";
        if ( *v14 != 0x40000 )
          v28 = L"\"default\"";
        break;
    }
  }
  else
  {
    v28 = L"Disallowed";
  }
  if ( pCodeProperties[v25].ImagePath )
    v23 = pCodeProperties[v25].ImagePath;
  SaferpLogResultsToFile((__int64)v23, (__int64)v28, (__int64)v22, (__int64)&Buf2);
LABEL_57:
  RtlLeaveCriticalSection(&g_TableCritSec);
  if ( !v4 )
LABEL_112:
    BaseSetLastNTError((unsigned int)IsV2PolicyPresent);
  return v4;
}

```

## disassembly

```asm
0x180010c00  mov     rax, rsp; IdentifyCodeAuthzLevelW
0x180010c03  mov     [rax+10h], rbx
0x180010c07  mov     [rax+18h], r8
0x180010c0b  mov     [rax+8], ecx
0x180010c0e  push    rbp
0x180010c0f  push    rsi
0x180010c10  push    rdi
0x180010c11  push    r12
0x180010c13  push    r13
0x180010c15  push    r14
0x180010c17  push    r15
0x180010c19  lea     rbp, [rax-5Fh]
0x180010c1d  sub     rsp, 0A0h
0x180010c24  xor     r12d, r12d
0x180010c27  movaps  xmmword ptr [rax-48h], xmm6
0x180010c2b  mov     [rbp+57h+IsMember], 0
0x180010c32  xorps   xmm6, xmm6
0x180010c35  movaps  [rbp+57h+Buf2], xmm6
0x180010c39  mov     rdi, r9
0x180010c3c  mov     [rbp+57h+var_80], r12d
0x180010c40  mov     r13, rdx
0x180010c43  mov     [rbp+57h+var_90], r12d
0x180010c47  mov     r15d, ecx
0x180010c4a  mov     [rbp+57h+Index], r12d
0x180010c4e  mov     dword ptr [rbp+57h+SystemInformation], r12d
0x180010c52  test    r8, r8
0x180010c55  jz      loc_180011362
0x180010c5b  cmp     cs:g_bInitializedFirstTime, r12b
0x180010c62  jz      loc_180011374
0x180010c68  lea     rcx, g_TableCritSec; CriticalSection
0x180010c6f  lea     r14d, [r12+1]
0x180010c74  call    cs:__imp_RtlEnterCriticalSection
0x180010c7a  cmp     cs:g_bNeedCacheReload, r12b
0x180010c81  jnz     loc_180011000
0x180010c87  lea     rcx, g_CodeLevelObjTable; Table
0x180010c8e  call    cs:__imp_RtlIsGenericTableEmpty
0x180010c94  test    al, al
0x180010c96  jnz     loc_180011060
0x180010c9c  mov     [rbp+57h+var_8C], r12d
0x180010ca0  test    rdi, rdi
0x180010ca3  jnz     loc_180010DD0
0x180010ca9  test    r15d, r15d
0x180010cac  jz      short loc_180010D03
0x180010cae  test    r13, r13
0x180010cb1  jz      short loc_180010D03
0x180010cb3  cmp     dword ptr [r13+0], 0B0h
0x180010cbb  jnz     short loc_180010CEA
0x180010cbd  xor     ecx, ecx
0x180010cbf  cmp     ecx, r15d
0x180010cc2  jnb     short loc_180010D03
0x180010cc4  mov     eax, ecx
0x180010cc6  imul    rdx, rax, 0B0h
0x180010ccd  mov     rax, [rdx+r13+10h]
0x180010cd2  dec     rax
0x180010cd5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180010cd9  ja      short loc_180010CE6
0x180010cdb  cmp     [rdx+r13+8], r12
0x180010ce0  jz      loc_1800112CE
0x180010ce6  inc     ecx
0x180010ce8  jmp     short loc_180010CBF
0x180010cea  cmp     dword ptr [r13+0], 88h
0x180010cf2  jnz     loc_1800112CE
0x180010cf8  xor     ecx, ecx
0x180010cfa  cmp     ecx, r15d
0x180010cfd  jb      loc_180011123
0x180010d03  mov     rdx, cs:g_pAdminSid; SidToCheck
0x180010d0a  lea     r8, [rbp+57h+IsMember]; IsMember
0x180010d0e  xor     ecx, ecx; TokenHandle
0x180010d10  call    cs:__imp_CheckTokenMembership
0x180010d16  test    eax, eax
0x180010d18  jnz     loc_180010FC1
0x180010d1e  test    r13, r13
0x180010d21  jz      loc_180011054
0x180010d27  test    r15d, r15d
0x180010d2a  jz      loc_180011054
0x180010d30  test    r14d, r14d
0x180010d33  jz      short loc_180010D4D
0x180010d35  cmp     cs:g_dwNumHandlesAllocated, r12d
0x180010d3c  jnz     short loc_180010D4D
0x180010d3e  call    SaferpReloadPolicyIfNeeded
0x180010d43  mov     ebx, eax
0x180010d45  test    eax, eax
0x180010d47  js      loc_180010F88
0x180010d4d  xor     edi, edi
0x180010d4f  xor     r15d, r15d
0x180010d52  cmp     dword ptr [r13+0], 0B0h
0x180010d5a  mov     esi, 0C0000225h
0x180010d5f  jnz     loc_180010FEE
0x180010d65  xor     r14d, r14d
0x180010d68  cmp     r14d, [rbp+57h+arg_0]
0x180010d6c  jnb     loc_180010E5A
0x180010d72  mov     eax, r14d
0x180010d75  lea     r9, [rbp+57h+SystemInformation]
0x180010d79  imul    rcx, rax, 0B0h
0x180010d80  xorps   xmm0, xmm0
0x180010d83  movups  [rbp+57h+SystemInformation], xmm0
0x180010d87  lea     rax, [rbp+57h+var_90]
0x180010d8b  mov     qword ptr [rbp+57h+Index], r12
0x180010d8f  add     rcx, r13
0x180010d92  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rax
0x180010d97  lea     r8, [rbp+57h+Index]
0x180010d9b  lea     rdx, [rbp+57h+var_80]
0x180010d9f  call    __CodeAuthzpIdentifyOneCodeAuthzLevel
0x180010da4  mov     ebx, eax
0x180010da6  test    eax, eax
0x180010da8  js      loc_180011145
0x180010dae  test    rdi, rdi
0x180010db1  jnz     loc_1800112BF
0x180010db7  movaps  xmm6, [rbp+57h+SystemInformation]
0x180010dbb  mov     rdi, qword ptr [rbp+57h+Index]
0x180010dbf  mov     r15d, [rbp+57h+var_90]
0x180010dc3  movaps  [rbp+57h+Buf2], xmm6
0x180010dc7  mov     [rbp+57h+var_8C], r14d
0x180010dcb  inc     r14d
0x180010dce  jmp     short loc_180010D68
0x180010dd0  lea     rdx, aWldpconfigci; "WLDPCONFIGCI"
0x180010dd7  mov     rcx, rdi; String1
0x180010dda  call    cs:__imp__wcsicmp
0x180010de0  test    eax, eax
0x180010de2  jz      loc_18001137B
0x180010de8  lea     rdx, aWldpmsi; "WLDPMSI"
0x180010def  mov     rcx, rdi; String1
0x180010df2  xor     sil, sil
0x180010df5  call    cs:__imp__wcsicmp
0x180010dfb  test    eax, eax
0x180010dfd  jz      loc_18001137E
0x180010e03  lea     rdx, aWldpscript; "WLDPSCRIPT"
0x180010e0a  mov     rcx, rdi; String1
0x180010e0d  call    cs:__imp__wcsicmp
0x180010e13  test    eax, eax
0x180010e15  jz      loc_18001137E
0x180010e1b  lea     rcx, [rbp+57h+SystemInformation]
0x180010e1f  call    SaferpIsV2PolicyPresent
0x180010e24  mov     ebx, eax
0x180010e26  test    eax, eax
0x180010e28  js      loc_180010F88
0x180010e2e  cmp     dword ptr [rbp+57h+SystemInformation], r12d
0x180010e32  jnz     loc_180011017
0x180010e38  lea     rdx, aAppx; "APPX"
0x180010e3f  mov     rcx, rdi; String1
0x180010e42  call    cs:__imp__wcsicmp
0x180010e48  test    eax, eax
0x180010e4a  jnz     loc_180010CA9
0x180010e50  mov     edx, 40000h
0x180010e55  jmp     loc_180011036
0x180010e5a  test    rdi, rdi
0x180010e5d  jz      loc_180010FFC
0x180010e63  mov     r15d, [rbp+57h+arg_0]
0x180010e67  mov     r12d, 3
0x180010e6d  mov     ebx, 10h
0x180010e72  lea     rdx, [rbp+57h+Buf2]; Buf2
0x180010e76  mov     r8d, ebx; Size
0x180010e79  lea     rcx, xmmword_18007AA70; Buf1
0x180010e80  lea     rsi, aDefault; "default"
0x180010e87  lea     r14, aDefault_0; "Default"
0x180010e8e  call    memcmp_0
0x180010e93  test    eax, eax
0x180010e95  jnz     loc_18001106A
0x180010e9b  cmp     cs:g_hKeyCustomRoot, 0
0x180010ea3  jnz     loc_18001110E
0x180010ea9  mov     rax, cs:g_DefaultCodeLevelUser
0x180010eb0  test    rax, rax
0x180010eb3  jnz     loc_1800114A3
0x180010eb9  mov     edx, 1; int
0x180010ebe  test    r13, r13
0x180010ec1  jz      loc_180011118
0x180010ec7  test    r15d, r15d
0x180010eca  jz      loc_180011118
0x180010ed0  mov     r15d, [rbp+57h+var_8C]
0x180010ed4  imul    rcx, r15, 0B0h
0x180010edb  mov     rax, [rcx+r13+8]
0x180010ee0  mov     rcx, [rbp+57h+arg_10]
0x180010ee4  mov     r8d, cs:g_DefaultCodeLevelFlags; int
0x180010eeb  mov     [rsp+0D0h+var_98], rcx; __int64
0x180010ef0  mov     [rsp+0D0h+hTemplateFile], rax; Source
0x180010ef5  lea     rax, [rbp+57h+Buf2]
0x180010ef9  mov     qword ptr [rsp+0D0h+dwFlagsAndAttributes], rax; __int64
0x180010efe  mov     [rsp+0D0h+dwCreationDisposition], 0; int
0x180010f06  mov     r9d, [rbp+57h+var_80]; int
0x180010f0a  mov     rcx, rdi; int
0x180010f0d  call    CodeAuthzpCreateLevelHandleFromRecord
0x180010f12  mov     ebx, eax
0x180010f14  mov     r12d, ebx
0x180010f17  not     r12d
0x180010f1a  shr     r12d, 1Fh
0x180010f1e  cmp     dword ptr [rdi], 0
0x180010f21  jz      loc_180011533
0x180010f27  cmp     dword ptr [rdi], 1000h
0x180010f2d  jz      loc_180011527
0x180010f33  cmp     dword ptr [rdi], 10000h
0x180010f39  jz      loc_18001151B
0x180010f3f  cmp     dword ptr [rdi], 20000h
0x180010f45  jz      loc_18001150F
0x180010f4b  cmp     dword ptr [rdi], 40000h
0x180010f51  lea     rdx, aUnrestricted; "Unrestricted"
0x180010f58  lea     rax, aDefault_1; "\"default\""
0x180010f5f  cmovnz  rdx, rax
0x180010f63  mov     eax, r15d
0x180010f66  mov     r8, rsi
0x180010f69  imul    r9, rax, 0B0h
0x180010f70  mov     rax, [r9+r13+8]
0x180010f75  lea     r9, [rbp+57h+Buf2]
0x180010f79  test    rax, rax
0x180010f7c  cmovnz  r14, rax
0x180010f80  mov     rcx, r14
0x180010f83  call    SaferpLogResultsToFile
0x180010f88  lea     rcx, g_TableCritSec; CriticalSection
0x180010f8f  call    cs:__imp_RtlLeaveCriticalSection
0x180010f95  test    r12d, r12d
0x180010f98  jz      loc_180011367
0x180010f9e  lea     r11, [rsp+0D0h+var_30]
0x180010fa6  mov     eax, r12d
0x180010fa9  mov     rbx, [r11+48h]
0x180010fad  movaps  xmm6, xmmword ptr [r11-10h]
0x180010fb2  mov     rsp, r11
0x180010fb5  pop     r15
0x180010fb7  pop     r14
0x180010fb9  pop     r13
0x180010fbb  pop     r12
0x180010fbd  pop     rdi
0x180010fbe  pop     rsi
0x180010fbf  pop     rbp
0x180010fc0  retn
0x180010fc1  cmp     [rbp+57h+IsMember], r12d
0x180010fc5  jz      loc_180010D1E
0x180010fcb  call    SaferpSkipPolicyForAdmins
0x180010fd0  test    eax, eax
0x180010fd2  jz      loc_180010D1E
0x180010fd8  mov     edx, 40000h
0x180010fdd  call    CodeAuthzLevelObjpLookupByLevelId
0x180010fe2  mov     rdi, rax
0x180010fe5  movups  xmm6, cs:xmmword_18007AA70
0x180010fec  jmp     short loc_180011045
0x180010fee  cmp     dword ptr [r13+0], 88h
0x180010ff6  jz      loc_18001148C
0x180010ffc  mov     ebx, esi
0x180010ffe  jmp     short loc_180010F88
0x180011000  call    CodeAuthzpImmediateReloadCacheTables
0x180011005  mov     ebx, eax
0x180011007  test    eax, eax
0x180011009  js      loc_180010F88
0x18001100f  xor     r14d, r14d
0x180011012  jmp     loc_180010C87
0x180011017  lea     r9, [rbp+57h+Index]
0x18001101b  mov     r8, rdi
0x18001101e  mov     rdx, r13
0x180011021  mov     ecx, r15d
0x180011024  call    SaferIdentifyLevel2
0x180011029  mov     ebx, eax
0x18001102b  test    eax, eax
0x18001102d  js      loc_180010F88
0x180011033  mov     edx, [rbp+57h+Index]
0x180011036  call    CodeAuthzLevelObjpLookupByLevelId
0x18001103b  movups  xmm6, cs:xmmword_18007ABE8
0x180011042  mov     rdi, rax
0x180011045  mov     r12d, 3
0x18001104b  movaps  [rbp+57h+Buf2], xmm6
0x18001104f  jmp     loc_180010E6D
0x180011054  mov     rdi, cs:g_DefaultCodeLevel
0x18001105b  test    rdi, rdi
0x18001105e  jnz     short loc_180010FE5
0x180011060  mov     ebx, 0C0000225h
0x180011065  jmp     loc_180010F88
0x18001106a  mov     r8, rbx; Size
0x18001106d  lea     rdx, [rbp+57h+Buf2]; Buf2
0x180011071  lea     rcx, xmmword_18007ABD8; Buf1
0x180011078  call    memcmp_0
0x18001107d  xor     r15d, r15d
0x180011080  test    eax, eax
0x180011082  jz      loc_180011152
0x180011088  mov     r8, rbx; Size
0x18001108b  lea     rdx, [rbp+57h+Buf2]; Buf2
0x18001108f  lea     rcx, xmmword_18007ABE8; Buf1
0x180011096  call    memcmp_0
0x18001109b  test    eax, eax
0x18001109d  jz      loc_180011205
0x1800110a3  lea     rdx, [rbp+57h+Buf2]
0x1800110a7  call    CodeAuthzIdentsLookupByGuid
0x1800110ac  mov     rdx, rax
0x1800110af  test    rax, rax
0x1800110b2  jz      loc_1800111FE
0x1800110b8  mov     ecx, [rax+10h]
0x1800110bb  sub     ecx, 1
0x1800110be  jnz     loc_1800112D8
0x1800110c4  mov     r8d, [rax+38h]
0x1800110c8  lea     rsi, aPath; "path"
0x1800110cf  mov     [rbp+57h+var_90], 1
0x1800110d6  mov     r12d, [rbp+57h+var_90]
0x1800110da  mov     r15d, [rbp+57h+var_8C]
0x1800110de  mov     rcx, [rbp+57h+arg_10]
0x1800110e2  mov     edx, [rdx+18h]
0x1800110e5  mov     [rsp+0D0h+var_98], rcx
0x1800110ea  imul    rax, r15, 0B0h
0x1800110f1  mov     rax, [rax+r13+8]
0x1800110f6  mov     [rsp+0D0h+hTemplateFile], rax
0x1800110fb  lea     rax, [rbp+57h+Buf2]
0x1800110ff  mov     qword ptr [rsp+0D0h+dwFlagsAndAttributes], rax
0x180011104  mov     [rsp+0D0h+dwCreationDisposition], r12d
0x180011109  jmp     loc_180010F06
0x18001110e  mov     edx, 3
  ... truncated ...
```
