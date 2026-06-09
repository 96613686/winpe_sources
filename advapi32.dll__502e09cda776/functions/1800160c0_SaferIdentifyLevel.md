# SaferIdentifyLevel

- ea: `0x1800160c0`
- end: `0x180016a54`
- name: `SaferIdentifyLevel`
- size: `2452`
- prototype: `BOOL __stdcall(DWORD dwNumProperties, PSAFER_CODE_PROPERTIES pCodeProperties, SAFER_LEVEL_HANDLE *pLevelHandle, LPVOID lpReserved)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180015bd0`

## callees

- `0x180012300`
- `0x180013f20`
- `0x18001546c`
- `0x180015570`
- `0x1800156e8`
- `0x180015864`
- `0x180015d60`
- `0x180015f94`
- `0x1800160c0`
- `0x180016a5c`
- `0x180016e28`
- `0x18004e478`
- `0x180072036`
- `0x18007205a`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800162ac`
- `msvcrt!_wcsicmp` at `0x1800162cd`
- `msvcrt!_wcsicmp` at `0x1800162eb`
- `msvcrt!_wcsicmp` at `0x180016326`
- `msvcrt!_wcsicmp` at `0x1800162ac`
- `msvcrt!_wcsicmp` at `0x1800162cd`
- `msvcrt!_wcsicmp` at `0x1800162eb`
- `msvcrt!_wcsicmp` at `0x180016326`
- `ntdll!RtlAllocateHandle` at `0x18001665f`
- `ntdll!RtlAllocateHandle` at `0x180016731`
- `ntdll!RtlAllocateHandle` at `0x18001665f`
- `ntdll!RtlAllocateHandle` at `0x180016731`
- `ntdll!RtlIsGenericTableEmpty` at `0x180016154`
- `ntdll!RtlIsGenericTableEmpty` at `0x180016154`
- `ntdll!NtQuerySystemInformation` at `0x1800168ab`
- `ntdll!NtQuerySystemInformation` at `0x1800168ab`
- `ntdll!RtlLeaveCriticalSection` at `0x180016479`
- `ntdll!RtlLeaveCriticalSection` at `0x180016479`
- `ntdll!RtlEnterCriticalSection` at `0x180016134`
- `ntdll!RtlEnterCriticalSection` at `0x180016134`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800161dc`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800161dc`
- `KERNEL32!BaseSetLastNTError` at `0x180016866`
- `KERNEL32!BaseSetLastNTError` at `0x180016866`
- `KERNEL32!CloseHandle` at `0x180016960`
- `KERNEL32!CloseHandle` at `0x180016960`
- `KERNEL32!CreateFileW` at `0x180016916`
- `KERNEL32!CreateFileW` at `0x180016916`

## string_xrefs

- `0x1800162c0`: `WLDPMSI`
- `0x1800162a2`: `WLDPCONFIGCI`

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
    v5 = xmmword_180088D58;
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
    v5 = xmmword_180088D58;
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
                  (unsigned int)pCodeProperties + 176 * k,
                  (unsigned int)v52,
                  (unsigned int)Index,
                  (unsigned int)&SystemInformation,
                  (__int64)&v49);
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
                  (unsigned int)pCodeProperties + 136 * m,
                  (unsigned int)v52,
                  (unsigned int)Index,
                  (unsigned int)&SystemInformation,
                  (__int64)&v49);
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
  v5 = xmmword_180088BD8;
LABEL_70:
  v21 = 3;
LABEL_71:
  Buf2 = v5;
LABEL_39:
  v22 = L"default";
  v23 = L"Default";
  if ( !memcmp_0(&xmmword_180088BD8, &Buf2, 0x10u) )
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
  if ( !memcmp_0(&xmmword_180088D48, &Buf2, 0x10u) )
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
  if ( !memcmp_0(&xmmword_180088D58, &Buf2, 0x10u) )
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
  SaferpLogResultsToFile(v23, v28, v22, &Buf2);
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
0x1800160c0  mov     rax, rsp; IdentifyCodeAuthzLevelW
0x1800160c3  mov     [rax+10h], rbx
0x1800160c7  mov     [rax+18h], r8
0x1800160cb  mov     [rax+8], ecx
0x1800160ce  push    rbp
0x1800160cf  push    rsi
0x1800160d0  push    rdi
0x1800160d1  push    r12
0x1800160d3  push    r13
0x1800160d5  push    r14
0x1800160d7  push    r15
0x1800160d9  lea     rbp, [rax-5Fh]
0x1800160dd  sub     rsp, 0A0h
0x1800160e4  xor     r12d, r12d
0x1800160e7  movaps  xmmword ptr [rax-48h], xmm6
0x1800160eb  mov     [rbp+57h+IsMember], 0
0x1800160f2  xorps   xmm6, xmm6
0x1800160f5  movaps  [rbp+57h+Buf2], xmm6
0x1800160f9  mov     rdi, r9
0x1800160fc  mov     [rbp+57h+var_80], r12d
0x180016100  mov     r13, rdx
0x180016103  mov     [rbp+57h+var_90], r12d
0x180016107  mov     r15d, ecx
0x18001610a  mov     [rbp+57h+Index], r12d
0x18001610e  mov     dword ptr [rbp+57h+SystemInformation], r12d
0x180016112  test    r8, r8
0x180016115  jz      loc_18001685F
0x18001611b  cmp     cs:g_bInitializedFirstTime, r12b
0x180016122  jz      loc_180016877
0x180016128  lea     rcx, g_TableCritSec; CriticalSection
0x18001612f  lea     r14d, [r12+1]
0x180016134  call    cs:__imp_RtlEnterCriticalSection
0x18001613b  nop     dword ptr [rax+rax+00h]
0x180016140  cmp     cs:g_bNeedCacheReload, r12b
0x180016147  jnz     loc_1800164F1
0x18001614d  lea     rcx, g_CodeLevelObjTable; Table
0x180016154  call    cs:__imp_RtlIsGenericTableEmpty
0x18001615b  nop     dword ptr [rax+rax+00h]
0x180016160  test    al, al
0x180016162  jnz     loc_180016551
0x180016168  mov     [rbp+57h+var_8C], r12d
0x18001616c  test    rdi, rdi
0x18001616f  jnz     loc_1800162A2
0x180016175  test    r15d, r15d
0x180016178  jz      short loc_1800161CF
0x18001617a  test    r13, r13
0x18001617d  jz      short loc_1800161CF
0x18001617f  cmp     dword ptr [r13+0], 0B0h
0x180016187  jnz     short loc_1800161B6
0x180016189  xor     ecx, ecx
0x18001618b  cmp     ecx, r15d
0x18001618e  jnb     short loc_1800161CF
0x180016190  mov     eax, ecx
0x180016192  imul    rdx, rax, 0B0h
0x180016199  mov     rax, [rdx+r13+10h]
0x18001619e  dec     rax
0x1800161a1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800161a5  ja      short loc_1800161B2
0x1800161a7  cmp     [rdx+r13+8], r12
0x1800161ac  jz      loc_1800167CB
0x1800161b2  inc     ecx
0x1800161b4  jmp     short loc_18001618B
0x1800161b6  cmp     dword ptr [r13+0], 88h
0x1800161be  jnz     loc_1800167CB
0x1800161c4  xor     ecx, ecx
0x1800161c6  cmp     ecx, r15d
0x1800161c9  jb      loc_180016614
0x1800161cf  mov     rdx, cs:g_pAdminSid; SidToCheck
0x1800161d6  lea     r8, [rbp+57h+IsMember]; IsMember
0x1800161da  xor     ecx, ecx; TokenHandle
0x1800161dc  call    cs:__imp_CheckTokenMembership
0x1800161e3  nop     dword ptr [rax+rax+00h]
0x1800161e8  test    eax, eax
0x1800161ea  jnz     loc_1800164B2
0x1800161f0  test    r13, r13
0x1800161f3  jz      loc_180016545
0x1800161f9  test    r15d, r15d
0x1800161fc  jz      loc_180016545
0x180016202  test    r14d, r14d
0x180016205  jz      short loc_18001621F
0x180016207  cmp     cs:g_dwNumHandlesAllocated, r12d
0x18001620e  jnz     short loc_18001621F
0x180016210  call    SaferpReloadPolicyIfNeeded
0x180016215  mov     ebx, eax
0x180016217  test    eax, eax
0x180016219  js      loc_180016472
0x18001621f  xor     edi, edi
0x180016221  xor     r15d, r15d
0x180016224  cmp     dword ptr [r13+0], 0B0h
0x18001622c  mov     esi, 0C0000225h
0x180016231  jnz     loc_1800164DF
0x180016237  xor     r14d, r14d
0x18001623a  cmp     r14d, [rbp+57h+arg_0]
0x18001623e  jnb     loc_180016344
0x180016244  mov     eax, r14d
0x180016247  lea     r9, [rbp+57h+SystemInformation]
0x18001624b  imul    rcx, rax, 0B0h
0x180016252  xorps   xmm0, xmm0
0x180016255  movups  [rbp+57h+SystemInformation], xmm0
0x180016259  lea     rax, [rbp+57h+var_90]
0x18001625d  mov     qword ptr [rbp+57h+Index], r12
0x180016261  add     rcx, r13
0x180016264  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rax
0x180016269  lea     r8, [rbp+57h+Index]
0x18001626d  lea     rdx, [rbp+57h+var_80]
0x180016271  call    __CodeAuthzpIdentifyOneCodeAuthzLevel
0x180016276  mov     ebx, eax
0x180016278  test    eax, eax
0x18001627a  js      loc_180016636
0x180016280  test    rdi, rdi
0x180016283  jnz     loc_1800167BC
0x180016289  movaps  xmm6, [rbp+57h+SystemInformation]
0x18001628d  mov     rdi, qword ptr [rbp+57h+Index]
0x180016291  mov     r15d, [rbp+57h+var_90]
0x180016295  movaps  [rbp+57h+Buf2], xmm6
0x180016299  mov     [rbp+57h+var_8C], r14d
0x18001629d  inc     r14d
0x1800162a0  jmp     short loc_18001623A
0x1800162a2  lea     rdx, aWldpconfigci; "WLDPCONFIGCI"
0x1800162a9  mov     rcx, rdi; String1
0x1800162ac  call    cs:__imp__wcsicmp
0x1800162b3  nop     dword ptr [rax+rax+00h]
0x1800162b8  test    eax, eax
0x1800162ba  jz      loc_18001687E
0x1800162c0  lea     rdx, aWldpmsi; "WLDPMSI"
0x1800162c7  mov     rcx, rdi; String1
0x1800162ca  xor     sil, sil
0x1800162cd  call    cs:__imp__wcsicmp
0x1800162d4  nop     dword ptr [rax+rax+00h]
0x1800162d9  test    eax, eax
0x1800162db  jz      loc_180016881
0x1800162e1  lea     rdx, aWldpscript; "WLDPSCRIPT"
0x1800162e8  mov     rcx, rdi; String1
0x1800162eb  call    cs:__imp__wcsicmp
0x1800162f2  nop     dword ptr [rax+rax+00h]
0x1800162f7  test    eax, eax
0x1800162f9  jz      loc_180016881
0x1800162ff  lea     rcx, [rbp+57h+SystemInformation]
0x180016303  call    SaferpIsV2PolicyPresent
0x180016308  mov     ebx, eax
0x18001630a  test    eax, eax
0x18001630c  js      loc_180016472
0x180016312  cmp     dword ptr [rbp+57h+SystemInformation], r12d
0x180016316  jnz     loc_180016508
0x18001631c  lea     rdx, aAppx; "APPX"
0x180016323  mov     rcx, rdi; String1
0x180016326  call    cs:__imp__wcsicmp
0x18001632d  nop     dword ptr [rax+rax+00h]
0x180016332  test    eax, eax
0x180016334  jnz     loc_180016175
0x18001633a  mov     edx, 40000h
0x18001633f  jmp     loc_180016527
0x180016344  test    rdi, rdi
0x180016347  jz      loc_1800164ED
0x18001634d  mov     r15d, [rbp+57h+arg_0]
0x180016351  mov     r12d, 3
0x180016357  mov     ebx, 10h
0x18001635c  lea     rdx, [rbp+57h+Buf2]; Buf2
0x180016360  mov     r8d, ebx; Size
0x180016363  lea     rcx, xmmword_180088BD8; Buf1
0x18001636a  lea     rsi, aDefault; "default"
0x180016371  lea     r14, aDefault_0; "Default"
0x180016378  call    memcmp_0
0x18001637d  test    eax, eax
0x18001637f  jnz     loc_18001655B
0x180016385  cmp     cs:g_hKeyCustomRoot, 0
0x18001638d  jnz     loc_1800165FF
0x180016393  mov     rax, cs:g_DefaultCodeLevelUser
0x18001639a  test    rax, rax
0x18001639d  jnz     loc_1800169B8
0x1800163a3  mov     edx, 1; int
0x1800163a8  test    r13, r13
0x1800163ab  jz      loc_180016609
0x1800163b1  test    r15d, r15d
0x1800163b4  jz      loc_180016609
0x1800163ba  mov     r15d, [rbp+57h+var_8C]
0x1800163be  imul    rcx, r15, 0B0h
0x1800163c5  mov     rax, [rcx+r13+8]
0x1800163ca  mov     rcx, [rbp+57h+arg_10]
0x1800163ce  mov     r8d, cs:g_DefaultCodeLevelFlags; int
0x1800163d5  mov     [rsp+0D0h+var_98], rcx; __int64
0x1800163da  mov     [rsp+0D0h+hTemplateFile], rax; Source
0x1800163df  lea     rax, [rbp+57h+Buf2]
0x1800163e3  mov     qword ptr [rsp+0D0h+dwFlagsAndAttributes], rax; __int64
0x1800163e8  mov     [rsp+0D0h+dwCreationDisposition], 0; int
0x1800163f0  mov     r9d, [rbp+57h+var_80]; int
0x1800163f4  mov     rcx, rdi; int
0x1800163f7  call    CodeAuthzpCreateLevelHandleFromRecord
0x1800163fc  mov     ebx, eax
0x1800163fe  mov     r12d, ebx
0x180016401  not     r12d
0x180016404  shr     r12d, 1Fh
0x180016408  cmp     dword ptr [rdi], 0
0x18001640b  jz      loc_180016A48
0x180016411  cmp     dword ptr [rdi], 1000h
0x180016417  jz      loc_180016A3C
0x18001641d  cmp     dword ptr [rdi], 10000h
0x180016423  jz      loc_180016A30
0x180016429  cmp     dword ptr [rdi], 20000h
0x18001642f  jz      loc_180016A24
0x180016435  cmp     dword ptr [rdi], 40000h
0x18001643b  lea     rdx, aUnrestricted; "Unrestricted"
0x180016442  lea     rax, aDefault_1; "\"default\""
0x180016449  cmovnz  rdx, rax
0x18001644d  mov     eax, r15d
0x180016450  mov     r8, rsi
0x180016453  imul    r9, rax, 0B0h
0x18001645a  mov     rax, [r9+r13+8]
0x18001645f  lea     r9, [rbp+57h+Buf2]
0x180016463  test    rax, rax
0x180016466  cmovnz  r14, rax
0x18001646a  mov     rcx, r14
0x18001646d  call    SaferpLogResultsToFile
0x180016472  lea     rcx, g_TableCritSec; CriticalSection
0x180016479  call    cs:__imp_RtlLeaveCriticalSection
0x180016480  nop     dword ptr [rax+rax+00h]
0x180016485  test    r12d, r12d
0x180016488  jz      loc_180016864
0x18001648e  lea     r11, [rsp+0D0h+var_30]
0x180016496  mov     eax, r12d
0x180016499  mov     rbx, [r11+48h]
0x18001649d  movaps  xmm6, xmmword ptr [r11-10h]
0x1800164a2  mov     rsp, r11
0x1800164a5  pop     r15
0x1800164a7  pop     r14
0x1800164a9  pop     r13
0x1800164ab  pop     r12
0x1800164ad  pop     rdi
0x1800164ae  pop     rsi
0x1800164af  pop     rbp
0x1800164b0  retn
0x1800164b2  cmp     [rbp+57h+IsMember], r12d
0x1800164b6  jz      loc_1800161F0
0x1800164bc  call    SaferpSkipPolicyForAdmins
0x1800164c1  test    eax, eax
0x1800164c3  jz      loc_1800161F0
0x1800164c9  mov     edx, 40000h
0x1800164ce  call    CodeAuthzLevelObjpLookupByLevelId
0x1800164d3  mov     rdi, rax
0x1800164d6  movups  xmm6, cs:xmmword_180088BD8
0x1800164dd  jmp     short loc_180016536
0x1800164df  cmp     dword ptr [r13+0], 88h
0x1800164e7  jz      loc_1800169A1
0x1800164ed  mov     ebx, esi
0x1800164ef  jmp     short loc_180016472
0x1800164f1  call    CodeAuthzpImmediateReloadCacheTables
0x1800164f6  mov     ebx, eax
0x1800164f8  test    eax, eax
0x1800164fa  js      loc_180016472
0x180016500  xor     r14d, r14d
0x180016503  jmp     loc_18001614D
0x180016508  lea     r9, [rbp+57h+Index]
0x18001650c  mov     r8, rdi
0x18001650f  mov     rdx, r13
0x180016512  mov     ecx, r15d
0x180016515  call    SaferIdentifyLevel2
0x18001651a  mov     ebx, eax
0x18001651c  test    eax, eax
0x18001651e  js      loc_180016472
0x180016524  mov     edx, [rbp+57h+Index]
0x180016527  call    CodeAuthzLevelObjpLookupByLevelId
0x18001652c  movups  xmm6, cs:xmmword_180088D58
0x180016533  mov     rdi, rax
0x180016536  mov     r12d, 3
0x18001653c  movaps  [rbp+57h+Buf2], xmm6
0x180016540  jmp     loc_180016357
0x180016545  mov     rdi, cs:g_DefaultCodeLevel
0x18001654c  test    rdi, rdi
0x18001654f  jnz     short loc_1800164D6
0x180016551  mov     ebx, 0C0000225h
0x180016556  jmp     loc_180016472
0x18001655b  mov     r8, rbx; Size
0x18001655e  lea     rdx, [rbp+57h+Buf2]; Buf2
0x180016562  lea     rcx, xmmword_180088D48; Buf1
0x180016569  call    memcmp_0
0x18001656e  xor     r15d, r15d
0x180016571  test    eax, eax
0x180016573  jz      loc_180016643
0x180016579  mov     r8, rbx; Size
0x18001657c  lea     rdx, [rbp+57h+Buf2]; Buf2
0x180016580  lea     rcx, xmmword_180088D58; Buf1
0x180016587  call    memcmp_0
0x18001658c  test    eax, eax
0x18001658e  jz      loc_1800166FC
0x180016594  lea     rdx, [rbp+57h+Buf2]
0x180016598  call    CodeAuthzIdentsLookupByGuid
0x18001659d  mov     rdx, rax
0x1800165a0  test    rax, rax
0x1800165a3  jz      loc_1800166F5
0x1800165a9  mov     ecx, [rax+10h]
0x1800165ac  sub     ecx, 1
0x1800165af  jnz     loc_1800167D5
0x1800165b5  mov     r8d, [rax+38h]
0x1800165b9  lea     rsi, aPath; "path"
0x1800165c0  mov     [rbp+57h+var_90], 1
0x1800165c7  mov     r12d, [rbp+57h+var_90]
0x1800165cb  mov     r15d, [rbp+57h+var_8C]
0x1800165cf  mov     rcx, [rbp+57h+arg_10]
0x1800165d3  mov     edx, [rdx+18h]
0x1800165d6  mov     [rsp+0D0h+var_98], rcx
  ... truncated ...
```
