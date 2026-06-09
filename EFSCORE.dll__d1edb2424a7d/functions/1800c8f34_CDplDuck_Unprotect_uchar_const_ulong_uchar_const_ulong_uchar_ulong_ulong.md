# CDplDuck::Unprotect(uchar const *,ulong,uchar const *,ulong,uchar * *,ulong *,ulong *)

- ea: `0x1800c8f34`
- end: `0x1800c9ddb`
- name: `?Unprotect@CDplDuck@@AEAAJPEBEK0KPEAPEAEPEAK2@Z`
- size: `3751`
- prototype: `int(CDplDuck *__hidden this, const unsigned __int8 *, unsigned int, const unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *, unsigned int *)`
- caller_count: `4`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800a4ce0`
- `0x1800b74e8`
- `0x1800caa2c`
- `0x1800cb188`

## callees

- `0x180004f86`
- `0x18000505d`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x1800bd7a8`
- `0x1800bd810`
- `0x1800be8a8`
- `0x1800c8f34`
- `0x1800d5af8`
- `0x1800d6064`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9d0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9d0a`
- `CRYPT32!CryptProtectMemory` at `0x1800c9d00`
- `CRYPT32!CryptProtectMemory` at `0x1800c9d00`
- `bcrypt!BCryptGetProperty` at `0x1800c961e`
- `bcrypt!BCryptGetProperty` at `0x1800c961e`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800c9bde`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800c9bde`
- `bcrypt!BCryptDestroyHash` at `0x1800c9328`
- `bcrypt!BCryptDestroyHash` at `0x1800c9328`
- `bcrypt!BCryptFinishHash` at `0x1800c98eb`
- `bcrypt!BCryptFinishHash` at `0x1800c98eb`
- `bcrypt!BCryptHashData` at `0x1800c9877`
- `bcrypt!BCryptHashData` at `0x1800c9877`
- `bcrypt!BCryptDestroyKey` at `0x1800c9300`
- `bcrypt!BCryptDestroyKey` at `0x1800c9cea`
- `bcrypt!BCryptDestroyKey` at `0x1800c9300`
- `bcrypt!BCryptDestroyKey` at `0x1800c9cea`
- `bcrypt!BCryptCreateHash` at `0x1800c981a`
- `bcrypt!BCryptCreateHash` at `0x1800c981a`
- `bcrypt!BCryptDecrypt` at `0x1800c9c9b`
- `bcrypt!BCryptDecrypt` at `0x1800c9c9b`
- `ntdll!RtlNtStatusToDosError` at `0x1800c9632`
- `ntdll!RtlNtStatusToDosError` at `0x1800c982e`
- `ntdll!RtlNtStatusToDosError` at `0x1800c988b`
- `ntdll!RtlNtStatusToDosError` at `0x1800c9912`
- `ntdll!RtlNtStatusToDosError` at `0x1800c9c03`
- `ntdll!RtlNtStatusToDosError` at `0x1800c9cb0`
- `ntdll!RtlNtStatusToDosError` at `0x1800c9d66`
- `ntdll!RtlNtStatusToDosError` at `0x1800c9632`
- `ntdll!RtlNtStatusToDosError` at `0x1800c982e`
- `ntdll!RtlNtStatusToDosError` at `0x1800c988b`
- `ntdll!RtlNtStatusToDosError` at `0x1800c9912`
- `ntdll!RtlNtStatusToDosError` at `0x1800c9c03`
- `ntdll!RtlNtStatusToDosError` at `0x1800c9cb0`
- `ntdll!RtlNtStatusToDosError` at `0x1800c9d66`

## pseudocode

```c
__int64 __fastcall CDplDuck::Unprotect(
        CDplDuck *this,
        const unsigned __int8 *a2,
        unsigned int a3,
        unsigned __int8 *a4,
        size_t Size,
        unsigned __int8 **a6,
        unsigned int *a7,
        unsigned int *a8)
{
  size_t v8; // r12
  UCHAR *v11; // rdi
  PUCHAR v12; // r13
  unsigned __int8 *v13; // r15
  unsigned __int8 **v14; // rdx
  unsigned int *v15; // rcx
  unsigned int *v16; // rax
  unsigned int v17; // ebx
  int v18; // r8d
  PUCHAR v19; // r14
  int v20; // r14d
  int v21; // ecx
  int v22; // ecx
  int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // r9d
  unsigned int v26; // ecx
  unsigned int v27; // eax
  unsigned int v28; // ecx
  unsigned int v29; // r8d
  int v30; // r8d
  CDplDuck *v31; // r12
  unsigned int v33; // ecx
  unsigned int v34; // eax
  unsigned int v35; // r14d
  unsigned int v36; // esi
  int v37; // ecx
  unsigned int v38; // ecx
  unsigned int v39; // r12d
  int v40; // ecx
  unsigned int v41; // ecx
  int v42; // ecx
  PUCHAR v43; // rsi
  size_t v44; // r8
  void *v45; // rdx
  __int64 v46; // rbx
  PUCHAR v47; // rcx
  int Property; // eax
  int v49; // ecx
  int v50; // esi
  signed int v51; // eax
  int v52; // ecx
  UCHAR *v53; // rsi
  int v54; // ecx
  int v55; // eax
  int v56; // esi
  signed int v57; // eax
  ULONG v58; // r8d
  int v59; // eax
  int v60; // esi
  signed int v61; // eax
  int v62; // esi
  __int64 v63; // rcx
  PUCHAR v64; // rax
  signed int v65; // eax
  int v66; // ecx
  int v67; // ecx
  unsigned int v68; // ecx
  unsigned int v69; // r13d
  ULONG v70; // eax
  DWORD v71; // esi
  unsigned int v72; // eax
  ULONG v73; // eax
  int v74; // ecx
  PUCHAR v75; // r15
  __int64 v76; // r12
  int v77; // eax
  int v78; // r14d
  signed int v79; // eax
  int v80; // eax
  int v81; // r14d
  signed int v82; // eax
  signed int LastError; // eax
  signed int v84; // eax
  char pcbResult; // [rsp+28h] [rbp-A1h]
  char pcbResulta; // [rsp+28h] [rbp-A1h]
  unsigned int pcbResultc; // [rsp+28h] [rbp-A1h]
  char pcbResultb; // [rsp+28h] [rbp-A1h]
  unsigned int pcbResultd; // [rsp+28h] [rbp-A1h]
  PUCHAR pbIV; // [rsp+58h] [rbp-71h] BYREF
  PUCHAR pbInput; // [rsp+60h] [rbp-69h] BYREF
  UCHAR pbOutput[4]; // [rsp+68h] [rbp-61h] BYREF
  ULONG cbInput; // [rsp+6Ch] [rbp-5Dh] BYREF
  BCRYPT_KEY_HANDLE hKey; // [rsp+70h] [rbp-59h] BYREF
  int v95; // [rsp+78h] [rbp-51h]
  PUCHAR v96; // [rsp+80h] [rbp-49h] BYREF
  BCRYPT_HASH_HANDLE hHash; // [rsp+88h] [rbp-41h] BYREF
  PUCHAR v98; // [rsp+90h] [rbp-39h] BYREF
  PUCHAR pbSecret; // [rsp+98h] [rbp-31h] BYREF
  PUCHAR v100; // [rsp+A0h] [rbp-29h] BYREF
  ULONG v101; // [rsp+A8h] [rbp-21h] BYREF
  PUCHAR pbKeyObject; // [rsp+B0h] [rbp-19h] BYREF
  PUCHAR pbHashObject[10]; // [rsp+B8h] [rbp-11h] BYREF
  void *v105; // [rsp+120h] [rbp+57h] BYREF
  unsigned int v106; // [rsp+128h] [rbp+5Fh]
  void *Src; // [rsp+130h] [rbp+67h]

  Src = a4;
  v106 = a3;
  v8 = a3;
  v95 = 0;
  v105 = 0;
  pbIV = 0;
  v98 = 0;
  pbSecret = 0;
  v11 = 0;
  hKey = 0;
  v12 = 0;
  pbKeyObject = 0;
  hHash = 0;
  v13 = 0;
  pbHashObject[0] = 0;
  cbInput = 0;
  v96 = 0;
  pbInput = 0;
  v100 = 0;
  *(_DWORD *)pbOutput = 0;
  v101 = 0;
  fnEfsLogTrace1Strings((_DWORD)this, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 39, 81);
  v14 = a6;
  if ( a6 )
    *a6 = 0;
  v15 = a7;
  if ( a7 )
    *a7 = 0;
  v16 = a8;
  if ( a8 )
    *a8 = 0;
  if ( !a2 )
  {
    pcbResult = 95;
LABEL_9:
    v17 = -2147024809;
    v18 = -2147024809;
LABEL_10:
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v18, 39, pcbResult);
    v19 = pbInput;
LABEL_38:
    v31 = this;
    goto LABEL_39;
  }
  if ( !a4 )
  {
    pcbResult = 96;
    goto LABEL_9;
  }
  if ( !v14 )
  {
    pcbResult = 97;
LABEL_15:
    v17 = -2147467261;
    v18 = -2147467261;
    goto LABEL_10;
  }
  if ( !v15 )
  {
    pcbResult = 98;
    goto LABEL_15;
  }
  if ( !v16 )
  {
    pcbResult = 99;
    goto LABEL_15;
  }
  if ( (unsigned int)v8 < 0x10 || (v20 = Size) == 0 )
  {
    pcbResult = 104;
    goto LABEL_9;
  }
  fnEfsLogTrace1Strings((_DWORD)v15, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 114);
  v17 = DplibpMemAllocEx(32, 1, 1, &v98);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v17,
              39,
              114) < 0 )
    goto LABEL_36;
  fnEfsLogTrace1Strings(v21, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 119);
  v17 = DplibpMemAllocEx(32, 1, 1, &pbSecret);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v17,
              39,
              119) < 0 )
    goto LABEL_36;
  fnEfsLogTrace1Strings(v22, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 131);
  v17 = DplibpMemAllocEx(v8, 1, 1, &v105);
  v23 = fnEfsLogTrace1String1Dword(
          g_hPublisher,
          (unsigned int)EFS_TRACE_COMPLETE_EVENT,
          (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
          (unsigned int)&sourceString,
          v17,
          39,
          131);
  v11 = (UCHAR *)v105;
  if ( v23 < 0 )
    goto LABEL_36;
  memcpy_0(v105, a2, v8);
  if ( *(_WORD *)v11 < 0x10u || *(_WORD *)v11 > *((_WORD *)v11 + 1) )
  {
    pcbResulta = -101;
    goto LABEL_34;
  }
  if ( *((_WORD *)v11 + 1) < 0x10u
    || (v24 = *((unsigned __int16 *)v11 + 1), v25 = *((unsigned __int16 *)v11 + 2), v26 = v25 + v24, v25 + v24 <= v24)
    || (v27 = *((unsigned __int16 *)v11 + 3), v26 > v27) )
  {
    pcbResulta = -94;
    goto LABEL_34;
  }
  v28 = *((unsigned __int16 *)v11 + 5);
  if ( v28 + v27 <= v27 || (v29 = *((unsigned __int16 *)v11 + 6), v28 + v27 > v29) )
  {
    pcbResulta = -88;
    goto LABEL_34;
  }
  if ( v28 % v25 )
  {
    pcbResulta = -83;
LABEL_34:
    v17 = -2147024809;
    v30 = -2147024809;
LABEL_35:
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v30, 39, pcbResulta);
LABEL_36:
    v19 = pbInput;
LABEL_37:
    v12 = pbIV;
    goto LABEL_38;
  }
  if ( *((_WORD *)v11 + 4) > (unsigned __int16)v28 )
  {
    pcbResulta = -78;
    goto LABEL_34;
  }
  v33 = v29 + *((unsigned __int16 *)v11 + 7);
  if ( v33 <= v29 || v33 > (unsigned int)v8 )
  {
    pcbResulta = -72;
    goto LABEL_34;
  }
  fnEfsLogTrace1Strings(v33, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 191);
  v34 = v20 + 4;
  v35 = -1;
  v36 = -1;
  if ( v34 >= 4 )
    v36 = v34;
  v17 = v34 < 4 ? 0x80070216 : 0;
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v17,
              39,
              191) < 0 )
    goto LABEL_36;
  fnEfsLogTrace1Strings(v37, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 193);
  v38 = v36 + *((unsigned __int16 *)v11 + 2);
  v39 = -1;
  if ( v38 >= v36 )
    v39 = v36 + *((unsigned __int16 *)v11 + 2);
  v17 = v38 < v36 ? 0x80070216 : 0;
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v17,
              39,
              193) < 0 )
    goto LABEL_36;
  fnEfsLogTrace1Strings(v40, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 195);
  v41 = v39 + *((unsigned __int16 *)v11 + 5);
  if ( v41 >= v39 )
    v35 = v39 + *((unsigned __int16 *)v11 + 5);
  v17 = v41 < v39 ? 0x80070216 : 0;
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v17,
              39,
              195) < 0 )
    goto LABEL_36;
  fnEfsLogTrace1Strings(v42, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 204);
  v17 = DplibpMemAllocEx(v35, 0, 0, &pbInput);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v17,
              39,
              204) < 0 )
    goto LABEL_36;
  v43 = pbInput;
  v44 = (unsigned int)Size;
  v45 = Src;
  v46 = (unsigned int)Size;
  v47 = pbInput + 4;
  *(_DWORD *)pbInput = Size;
  memcpy_0(v47, v45, v44);
  memcpy_0(&v43[v46 + 4], &v11[*((unsigned __int16 *)v11 + 1)], *((unsigned __int16 *)v11 + 2));
  memcpy_0(
    &v43[v46 + 4 + *((unsigned __int16 *)v11 + 2)],
    &v11[*((unsigned __int16 *)v11 + 3)],
    *((unsigned __int16 *)v11 + 5));
  v31 = this;
  Property = BCryptGetProperty(*((BCRYPT_HANDLE *)this + 8), L"HashDigestLength", pbOutput, 4u, &v101, 0);
  v50 = Property;
  if ( Property )
  {
    v17 = 0;
    if ( Property < 0 )
    {
      v51 = RtlNtStatusToDosError(Property);
      v17 = v51;
      if ( !v51 || v51 == 317 )
      {
        v17 = v50 | 0x10000000;
      }
      else if ( v51 > 0 )
      {
        v17 = (unsigned __int16)v51 | 0x80070000;
      }
    }
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v17, 39, 242);
    goto LABEL_84;
  }
  fnEfsLogTrace1Strings(v49, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 252);
  v17 = DplibpMemAllocEx(*(unsigned int *)pbOutput, 0, 0, &v100);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v17,
              39,
              252) < 0
    || (v95 = CDplUser::UserSvcLock(*((CDplUser **)this + 16)),
        fnEfsLogTrace1Strings(v52, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 7),
        v53 = pbSecret,
        v17 = CDplDuck::DeriveKey(this, "Auth-HMAC-SHA256", 0x11u, pbSecret, pcbResultc),
        (int)fnEfsLogTrace1String1Dword(
               g_hPublisher,
               (unsigned int)EFS_TRACE_COMPLETE_EVENT,
               (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
               (unsigned int)&sourceString,
               v17,
               39,
               7) < 0)
    || (fnEfsLogTrace1Strings(v54, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 16),
        v17 = DplibpMemAllocEx(*((unsigned int *)this + 18), 1, 1, pbHashObject),
        (int)fnEfsLogTrace1String1Dword(
               g_hPublisher,
               (unsigned int)EFS_TRACE_COMPLETE_EVENT,
               (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
               (unsigned int)&sourceString,
               v17,
               39,
               16) < 0) )
  {
LABEL_84:
    v12 = pbIV;
    v19 = pbInput;
    goto LABEL_39;
  }
  v55 = BCryptCreateHash(
          *((BCRYPT_ALG_HANDLE *)this + 8),
          &hHash,
          pbHashObject[0],
          *((_DWORD *)this + 18),
          v53,
          0x20u,
          0);
  v56 = v55;
  if ( v55 )
  {
    v17 = 0;
    if ( v55 < 0 )
    {
      v57 = RtlNtStatusToDosError(v55);
      v17 = v57;
      if ( !v57 || v57 == 317 )
      {
        v17 = v56 | 0x10000000;
      }
      else if ( v57 > 0 )
      {
        v17 = (unsigned __int16)v57 | 0x80070000;
      }
    }
    pcbResulta = 28;
LABEL_96:
    v30 = v17;
    goto LABEL_35;
  }
  v58 = v35;
  v19 = pbInput;
  v59 = BCryptHashData(hHash, pbInput, v58, 0);
  v60 = v59;
  if ( v59 )
  {
    v17 = 0;
    if ( v59 < 0 )
    {
      v61 = RtlNtStatusToDosError(v59);
      v17 = v61;
      if ( !v61 || v61 == 317 )
      {
        v17 = v60 | 0x10000000;
      }
      else if ( v61 > 0 )
      {
        v17 = (unsigned __int16)v61 | 0x80070000;
      }
    }
    pcbResultb = 42;
LABEL_105:
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v17, 39, pcbResultb);
    goto LABEL_37;
  }
  v62 = BCryptFinishHash(hHash, v100, *(ULONG *)pbOutput, 0);
  v63 = 32;
  v64 = pbSecret;
  do
  {
    *v64++ = 0;
    --v63;
  }
  while ( v63 );
  if ( v62 )
  {
    v17 = 0;
    if ( v62 < 0 )
    {
      v65 = RtlNtStatusToDosError(v62);
      v17 = v65;
      if ( !v65 || v65 == 317 )
      {
        v17 = v62 | 0x10000000;
      }
      else if ( v65 > 0 )
      {
        v17 = (unsigned __int16)v65 | 0x80070000;
      }
    }
    pcbResultb = 51;
    goto LABEL_105;
  }
  if ( *(_DWORD *)pbOutput != *((unsigned __int16 *)v11 + 7)
    || memcmp_0(v100, &v11[*((unsigned __int16 *)v11 + 6)], *(unsigned int *)pbOutput) )
  {
    v84 = RtlNtStatusToDosError(-1073700862);
    v17 = v84;
    if ( !v84 || v84 == 317 )
    {
      v17 = -805265406;
    }
    else if ( v84 > 0 )
    {
      v17 = (unsigned __int16)v84 | 0x80070000;
    }
    pcbResultb = 62;
    goto LABEL_105;
  }
  fnEfsLogTrace1Strings(v66, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 76);
  v17 = CDplDuck::DeriveKey(this, "Enc-AES-CBC", 0xCu, v98, pcbResultd);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v17,
              39,
              76) < 0 )
    goto LABEL_37;
  fnEfsLogTrace1Strings(v67, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 85);
  v17 = DplibpMemAllocEx(*((unsigned __int16 *)v11 + 2), 0, 0, &pbIV);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v17,
              39,
              85) < 0 )
    goto LABEL_37;
  memcpy_0(pbIV, &v11[*((unsigned __int16 *)v11 + 1)], *((unsigned __int16 *)v11 + 2));
  v69 = *((unsigned __int16 *)v11 + 4);
  LOWORD(v105) = *((_WORD *)v11 + 3);
  v70 = *((unsigned __int16 *)v11 + 5);
  cbInput = v70;
  v71 = (v69 + 15) & 0xFFFFFFF0;
  if ( v71 < v69 )
  {
    v17 = -2147418113;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147418113, 39, 101);
    goto LABEL_37;
  }
  if ( v71 > v70 )
  {
    v72 = *((unsigned __int16 *)v11 + 3);
    v68 = v72 + v71;
    if ( v72 + v71 <= v72 || v68 > v106 )
    {
      v17 = -2147024809;
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024809, 39, 108);
      goto LABEL_37;
    }
  }
  fnEfsLogTrace1Strings(v68, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 114);
  v73 = cbInput;
  if ( v71 > cbInput )
    v73 = (v69 + 15) & 0xFFFFFFF0;
  v17 = DplibpMemAllocEx(v73, 1, 1, &v96);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v17,
              39,
              114) < 0 )
  {
    v13 = v96;
    goto LABEL_37;
  }
  fnEfsLogTrace1Strings(v74, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 123);
  v31 = this;
  v17 = DplibpMemAllocEx(*((unsigned int *)this + 10), 1, 1, &pbKeyObject);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v17,
              39,
              123) >= 0 )
  {
    v75 = v98;
    v76 = 32;
    v77 = BCryptGenerateSymmetricKey(
            *((BCRYPT_ALG_HANDLE *)this + 4),
            &hKey,
            pbKeyObject,
            *((_DWORD *)this + 10),
            v98,
            0x20u,
            0);
    v78 = v77;
    do
    {
      *v75++ = 0;
      --v76;
    }
    while ( v76 );
    if ( v77 )
    {
      v17 = 0;
      if ( v77 < 0 )
      {
        v79 = RtlNtStatusToDosError(v77);
        v17 = v79;
        if ( !v79 || v79 == 317 )
        {
          v17 = v78 | 0x10000000;
        }
        else if ( v79 > 0 )
        {
          v17 = (unsigned __int16)v79 | 0x80070000;
        }
      }
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v17, 39, 137);
      v13 = v96;
      goto LABEL_36;
    }
    v13 = v96;
    v80 = BCryptDecrypt(
            hKey,
            &v11[(unsigned __int16)v105],
            cbInput,
            0,
            pbIV,
            *((unsigned __int16 *)v11 + 2),
            v96,
            cbInput,
            &cbInput,
            0);
    v81 = v80;
    if ( v80 )
    {
      v17 = 0;
      if ( v80 < 0 )
      {
        v82 = RtlNtStatusToDosError(v80);
        v17 = v82;
        if ( !v82 || v82 == 317 )
        {
          v17 = v81 | 0x10000000;
        }
        else if ( v82 > 0 )
        {
          v17 = (unsigned __int16)v82 | 0x80070000;
        }
      }
      pcbResulta = -99;
    }
    else
    {
      BCryptDestroyKey(hKey);
      hKey = 0;
      if ( CryptProtectMemory(v13, v71, 0) )
      {
        *a8 = v69;
        *a7 = v71;
        *a6 = v13;
        v13 = 0;
        goto LABEL_36;
      }
      LastError = GetLastError();
      v17 = LastError;
      if ( LastError > 0 )
        v17 = (unsigned __int16)LastError | 0x80070000;
      pcbResulta = -85;
    }
    goto LABEL_96;
  }
  v13 = v96;
  v12 = pbIV;
LABEL_39:
  CDplUser::UserSvcUnlock(*((CDplUser **)v31 + 16), v95);
  if ( v98 )
    DplibMemFree(v98);
  if ( pbSecret )
    DplibMemFree(pbSecret);
  if ( v13 )
    DplibMemFree(v13);
  if ( v11 )
    DplibMemFree(v11);
  if ( v12 )
    DplibMemFree(v12);
  if ( hKey )
  {
    BCryptDestroyKey(hKey);
    hKey = 0;
  }
  if ( pbKeyObject )
    DplibMemFree(pbKeyObject);
  if ( hHash )
  {
    BCryptDestroyHash(hHash);
    hHash = 0;
  }
  if ( pbHashObject[0] )
    DplibMemFree(pbHashObject[0]);
  if ( v19 )
    DplibMemFree(v19);
  if ( v100 )
    DplibMemFree(v100);
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&sourceString,
    v17,
    39,
    217);
  return v17;
}

```

## disassembly

```asm
0x1800c8f34  mov     rax, rsp
0x1800c8f37  mov     [rax+20h], r9
0x1800c8f3b  mov     [rax+18h], r8d
0x1800c8f3f  mov     [rax+8], rcx
0x1800c8f43  push    rbp
0x1800c8f44  push    rbx
0x1800c8f45  push    rsi
0x1800c8f46  push    rdi
0x1800c8f47  push    r12
0x1800c8f49  push    r13
0x1800c8f4b  push    r14
0x1800c8f4d  push    r15
0x1800c8f4f  lea     rbp, [rax-47h]
0x1800c8f53  sub     rsp, 0C8h
0x1800c8f5a  xor     r14d, r14d
0x1800c8f5d  mov     r12d, r8d
0x1800c8f60  mov     rbx, r9
0x1800c8f63  mov     [rbp+3Fh+var_90], r14d
0x1800c8f67  mov     rsi, rdx
0x1800c8f6a  mov     [rbp+3Fh+arg_8], r14
0x1800c8f6e  lea     r8, sourceString
0x1800c8f75  mov     [rbp+3Fh+pbIV], r14
0x1800c8f79  lea     r9d, [r14+27h]
0x1800c8f7d  mov     [rbp+3Fh+var_78], r14
0x1800c8f81  lea     rdx, EFS_TRACE_ENTER_EVENT
0x1800c8f88  mov     [rbp+3Fh+pbSecret], r14
0x1800c8f8c  mov     edi, r14d
0x1800c8f8f  mov     [rbp+3Fh+hKey], r14
0x1800c8f93  mov     r13d, r14d
0x1800c8f96  mov     [rbp+3Fh+pbKeyObject], r14
0x1800c8f9a  mov     [rbp+3Fh+hHash], r14
0x1800c8f9e  mov     r15d, r14d
0x1800c8fa1  mov     [rbp+3Fh+pbHashObject], r14
0x1800c8fa5  mov     [rbp+3Fh+cbInput], r14d
0x1800c8fa9  mov     [rbp+3Fh+var_88], r14
0x1800c8fad  mov     [rbp+3Fh+pbInput], r14
0x1800c8fb1  mov     [rbp+3Fh+var_68], r14
0x1800c8fb5  mov     dword ptr [rbp+3Fh+pbOutput], r14d
0x1800c8fb9  mov     [rbp+3Fh+var_60], r14d
0x1800c8fbd  mov     dword ptr [rsp+100h+pcbResult], 2151h
0x1800c8fc5  call    fnEfsLogTrace1Strings
0x1800c8fca  mov     rdx, [rbp+3Fh+arg_28]
0x1800c8fce  test    rdx, rdx
0x1800c8fd1  jz      short loc_1800C8FD8
0x1800c8fd3  xor     eax, eax
0x1800c8fd5  mov     [rdx], rax
0x1800c8fd8  mov     rcx, [rbp+3Fh+arg_30]
0x1800c8fdc  test    rcx, rcx
0x1800c8fdf  jz      short loc_1800C8FE5
0x1800c8fe1  xor     eax, eax
0x1800c8fe3  mov     [rcx], eax
0x1800c8fe5  mov     rax, [rbp+3Fh+arg_38]
0x1800c8fec  test    rax, rax
0x1800c8fef  jz      short loc_1800C8FF7
0x1800c8ff1  xor     r8d, r8d
0x1800c8ff4  mov     [rax], r8d
0x1800c8ff7  test    rsi, rsi
0x1800c8ffa  jnz     short loc_1800C9031
0x1800c8ffc  mov     dword ptr [rsp+100h+pcbResult], 215Fh
0x1800c9004  mov     ebx, 80070057h
0x1800c9009  mov     r8d, 80070057h
0x1800c900f  mov     rcx, cs:g_hPublisher
0x1800c9016  lea     rdx, EFS_TRACE_ERROR
0x1800c901d  mov     r9d, 27h ; '''
0x1800c9023  call    fnEfsLogTrace1
0x1800c9028  mov     r14, [rbp+3Fh+pbInput]
0x1800c902c  jmp     loc_1800C92A0
0x1800c9031  test    rbx, rbx
0x1800c9034  jnz     short loc_1800C9040
0x1800c9036  mov     dword ptr [rsp+100h+pcbResult], 2160h
0x1800c903e  jmp     short loc_1800C9004
0x1800c9040  test    rdx, rdx
0x1800c9043  jnz     short loc_1800C905A
0x1800c9045  mov     dword ptr [rsp+100h+pcbResult], 2161h
0x1800c904d  mov     ebx, 80004003h
0x1800c9052  mov     r8d, 80004003h
0x1800c9058  jmp     short loc_1800C900F
0x1800c905a  test    rcx, rcx
0x1800c905d  jnz     short loc_1800C9069
0x1800c905f  mov     dword ptr [rsp+100h+pcbResult], 2162h
0x1800c9067  jmp     short loc_1800C904D
0x1800c9069  test    rax, rax
0x1800c906c  jnz     short loc_1800C9078
0x1800c906e  mov     dword ptr [rsp+100h+pcbResult], 2163h
0x1800c9076  jmp     short loc_1800C904D
0x1800c9078  cmp     r12d, 10h
0x1800c907c  jb      loc_1800C9DCE
0x1800c9082  mov     r14d, dword ptr [rbp+3Fh+Size]
0x1800c9086  test    r14d, r14d
0x1800c9089  jz      loc_1800C9DCE
0x1800c908f  mov     r9d, 27h ; '''
0x1800c9095  mov     dword ptr [rsp+100h+pcbResult], 2172h
0x1800c909d  lea     r8, sourceString
0x1800c90a4  lea     rdx, EFS_TRACE_START_EVENT
0x1800c90ab  call    fnEfsLogTrace1Strings
0x1800c90b0  mov     edx, 1
0x1800c90b5  lea     r9, [rbp+3Fh+var_78]
0x1800c90b9  mov     r8d, edx
0x1800c90bc  lea     r13d, [rdx+1Fh]
0x1800c90c0  mov     ecx, r13d
0x1800c90c3  call    ?DplibpMemAllocEx@@YAJ_KW4_DPLIB_ALLOC_QOS_LEVEL@@HPEAPEAX@Z; DplibpMemAllocEx(unsigned __int64,_DPLIB_ALLOC_QOS_LEVEL,int,void * *)
0x1800c90c8  mov     rcx, cs:g_hPublisher
0x1800c90cf  lea     r9, sourceString
0x1800c90d6  mov     [rsp+100h+var_D0], 2172h
0x1800c90de  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800c90e5  mov     [rsp+100h+dwFlags], 27h ; '''
0x1800c90ed  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800c90f4  mov     dword ptr [rsp+100h+pcbResult], eax
0x1800c90f8  mov     ebx, eax
0x1800c90fa  call    fnEfsLogTrace1String1Dword
0x1800c90ff  test    eax, eax
0x1800c9101  js      loc_1800C9298
0x1800c9107  lea     r9d, [r13+7]
0x1800c910b  mov     dword ptr [rsp+100h+pcbResult], 2177h
0x1800c9113  lea     r8, sourceString
0x1800c911a  lea     rdx, EFS_TRACE_START_EVENT
0x1800c9121  call    fnEfsLogTrace1Strings
0x1800c9126  lea     edx, [r13-1Fh]
0x1800c912a  mov     ecx, r13d
0x1800c912d  mov     r8d, edx
0x1800c9130  lea     r9, [rbp+3Fh+pbSecret]
0x1800c9134  call    ?DplibpMemAllocEx@@YAJ_KW4_DPLIB_ALLOC_QOS_LEVEL@@HPEAPEAX@Z; DplibpMemAllocEx(unsigned __int64,_DPLIB_ALLOC_QOS_LEVEL,int,void * *)
0x1800c9139  mov     rcx, cs:g_hPublisher
0x1800c9140  lea     r9, sourceString
0x1800c9147  mov     [rsp+100h+var_D0], 2177h
0x1800c914f  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800c9156  mov     [rsp+100h+dwFlags], 27h ; '''
0x1800c915e  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800c9165  mov     dword ptr [rsp+100h+pcbResult], eax
0x1800c9169  mov     ebx, eax
0x1800c916b  call    fnEfsLogTrace1String1Dword
0x1800c9170  test    eax, eax
0x1800c9172  js      loc_1800C9298
0x1800c9178  lea     r9d, [r13+7]
0x1800c917c  mov     dword ptr [rsp+100h+pcbResult], 2183h
0x1800c9184  lea     r8, sourceString
0x1800c918b  lea     rdx, EFS_TRACE_START_EVENT
0x1800c9192  call    fnEfsLogTrace1Strings
0x1800c9197  lea     edx, [r13-1Fh]
0x1800c919b  mov     rcx, r12
0x1800c919e  mov     r8d, edx
0x1800c91a1  lea     r9, [rbp+3Fh+arg_8]
0x1800c91a5  call    ?DplibpMemAllocEx@@YAJ_KW4_DPLIB_ALLOC_QOS_LEVEL@@HPEAPEAX@Z; DplibpMemAllocEx(unsigned __int64,_DPLIB_ALLOC_QOS_LEVEL,int,void * *)
0x1800c91aa  mov     rcx, cs:g_hPublisher
0x1800c91b1  lea     r9, sourceString
0x1800c91b8  mov     [rsp+100h+var_D0], 2183h
0x1800c91c0  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800c91c7  mov     [rsp+100h+dwFlags], 27h ; '''
0x1800c91cf  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800c91d6  mov     dword ptr [rsp+100h+pcbResult], eax
0x1800c91da  mov     ebx, eax
0x1800c91dc  call    fnEfsLogTrace1String1Dword
0x1800c91e1  mov     rdi, [rbp+3Fh+arg_8]
0x1800c91e5  test    eax, eax
0x1800c91e7  js      loc_1800C9298
0x1800c91ed  mov     r8, r12; Size
0x1800c91f0  mov     rdx, rsi; Src
0x1800c91f3  mov     rcx, rdi; void *
0x1800c91f6  call    memcpy_0
0x1800c91fb  movzx   eax, word ptr [rdi]
0x1800c91fe  lea     ecx, [r13-10h]
0x1800c9202  cmp     ax, cx
0x1800c9205  jb      loc_1800C9DC1
0x1800c920b  cmp     ax, [rdi+2]
0x1800c920f  ja      loc_1800C9DC1
0x1800c9215  cmp     [rdi+2], cx
0x1800c9219  jb      loc_1800C9DB4
0x1800c921f  movzx   eax, word ptr [rdi+2]
0x1800c9223  movzx   r9d, word ptr [rdi+4]
0x1800c9228  lea     ecx, [r9+rax]
0x1800c922c  cmp     ecx, eax
0x1800c922e  jbe     loc_1800C9DB4
0x1800c9234  movzx   eax, word ptr [rdi+6]
0x1800c9238  cmp     ecx, eax
0x1800c923a  ja      loc_1800C9DB4
0x1800c9240  movzx   ecx, word ptr [rdi+0Ah]
0x1800c9244  lea     edx, [rcx+rax]
0x1800c9247  cmp     edx, eax
0x1800c9249  jbe     loc_1800C9DA7
0x1800c924f  movzx   r8d, word ptr [rdi+0Ch]
0x1800c9254  cmp     edx, r8d
0x1800c9257  ja      loc_1800C9DA7
0x1800c925d  xor     edx, edx
0x1800c925f  mov     eax, ecx
0x1800c9261  div     r9d
0x1800c9264  test    edx, edx
0x1800c9266  jz      loc_1800C93AD
0x1800c926c  mov     dword ptr [rsp+100h+pcbResult], 21ADh
0x1800c9274  mov     ebx, 80070057h
0x1800c9279  mov     r8d, 80070057h
0x1800c927f  mov     rcx, cs:g_hPublisher
0x1800c9286  lea     rdx, EFS_TRACE_ERROR
0x1800c928d  mov     r9d, 27h ; '''
0x1800c9293  call    fnEfsLogTrace1
0x1800c9298  mov     r14, [rbp+3Fh+pbInput]
0x1800c929c  mov     r13, [rbp+3Fh+pbIV]
0x1800c92a0  mov     r12, [rbp+3Fh+arg_0]
0x1800c92a4  mov     edx, [rbp+3Fh+var_90]; int
0x1800c92a7  mov     rcx, [r12+80h]; this
0x1800c92af  call    ?UserSvcUnlock@CDplUser@@AEAAHH@Z; CDplUser::UserSvcUnlock(int)
0x1800c92b4  mov     rcx, [rbp+3Fh+var_78]; void *
0x1800c92b8  test    rcx, rcx
0x1800c92bb  jz      short loc_1800C92C2
0x1800c92bd  call    ?DplibMemFree@@YAJPEAX@Z; DplibMemFree(void *)
0x1800c92c2  mov     rcx, [rbp+3Fh+pbSecret]; void *
0x1800c92c6  test    rcx, rcx
0x1800c92c9  jz      short loc_1800C92D0
0x1800c92cb  call    ?DplibMemFree@@YAJPEAX@Z; DplibMemFree(void *)
0x1800c92d0  test    r15, r15
0x1800c92d3  jz      short loc_1800C92DD
0x1800c92d5  mov     rcx, r15; void *
0x1800c92d8  call    ?DplibMemFree@@YAJPEAX@Z; DplibMemFree(void *)
0x1800c92dd  test    rdi, rdi
0x1800c92e0  jz      short loc_1800C92EA
0x1800c92e2  mov     rcx, rdi; void *
0x1800c92e5  call    ?DplibMemFree@@YAJPEAX@Z; DplibMemFree(void *)
0x1800c92ea  test    r13, r13
0x1800c92ed  jz      short loc_1800C92F7
0x1800c92ef  mov     rcx, r13; void *
0x1800c92f2  call    ?DplibMemFree@@YAJPEAX@Z; DplibMemFree(void *)
0x1800c92f7  mov     rcx, [rbp+3Fh+hKey]; hKey
0x1800c92fb  test    rcx, rcx
0x1800c92fe  jz      short loc_1800C930E
0x1800c9300  call    cs:__imp_BCryptDestroyKey
0x1800c9306  mov     [rbp+3Fh+hKey], 0
0x1800c930e  mov     rax, [rbp+3Fh+pbKeyObject]
0x1800c9312  test    rax, rax
0x1800c9315  jz      short loc_1800C931F
0x1800c9317  mov     rcx, rax; void *
0x1800c931a  call    ?DplibMemFree@@YAJPEAX@Z; DplibMemFree(void *)
0x1800c931f  mov     rcx, [rbp+3Fh+hHash]; hHash
0x1800c9323  test    rcx, rcx
0x1800c9326  jz      short loc_1800C9336
0x1800c9328  call    cs:__imp_BCryptDestroyHash
0x1800c932e  mov     [rbp+3Fh+hHash], 0
0x1800c9336  mov     rax, [rbp+3Fh+pbHashObject]
0x1800c933a  test    rax, rax
0x1800c933d  jz      short loc_1800C9347
0x1800c933f  mov     rcx, rax; void *
0x1800c9342  call    ?DplibMemFree@@YAJPEAX@Z; DplibMemFree(void *)
0x1800c9347  test    r14, r14
0x1800c934a  jz      short loc_1800C9354
0x1800c934c  mov     rcx, r14; void *
0x1800c934f  call    ?DplibMemFree@@YAJPEAX@Z; DplibMemFree(void *)
0x1800c9354  mov     rcx, [rbp+3Fh+var_68]; void *
0x1800c9358  test    rcx, rcx
0x1800c935b  jz      short loc_1800C9362
0x1800c935d  call    ?DplibMemFree@@YAJPEAX@Z; DplibMemFree(void *)
0x1800c9362  mov     rcx, cs:g_hPublisher
0x1800c9369  lea     r9, sourceString
0x1800c9370  mov     [rsp+100h+var_D0], 22D9h
0x1800c9378  lea     r8, EFS_TRACE_LEAVE_HR_EVENT_ERROR
0x1800c937f  mov     [rsp+100h+dwFlags], 27h ; '''
0x1800c9387  lea     rdx, EFS_TRACE_LEAVE_HR_EVENT
0x1800c938e  mov     dword ptr [rsp+100h+pcbResult], ebx
0x1800c9392  call    fnEfsLogTrace1String1Dword
0x1800c9397  mov     eax, ebx
0x1800c9399  add     rsp, 0C8h
0x1800c93a0  pop     r15
0x1800c93a2  pop     r14
0x1800c93a4  pop     r13
0x1800c93a6  pop     r12
0x1800c93a8  pop     rdi
0x1800c93a9  pop     rsi
0x1800c93aa  pop     rbx
0x1800c93ab  pop     rbp
0x1800c93ac  retn
0x1800c93ad  cmp     [rdi+8], cx
0x1800c93b1  jbe     short loc_1800C93C0
0x1800c93b3  mov     dword ptr [rsp+100h+pcbResult], 21B2h
0x1800c93bb  jmp     loc_1800C9274
0x1800c93c0  movzx   ecx, word ptr [rdi+0Eh]
0x1800c93c4  add     ecx, r8d
0x1800c93c7  cmp     ecx, r8d
0x1800c93ca  jbe     loc_1800C9D9A
0x1800c93d0  cmp     ecx, r12d
0x1800c93d3  ja      loc_1800C9D9A
0x1800c93d9  mov     r12d, 21BFh
0x1800c93df  lea     r8, sourceString
0x1800c93e6  mov     r9d, 27h ; '''
0x1800c93ec  mov     dword ptr [rsp+100h+pcbResult], r12d
0x1800c93f1  lea     rdx, EFS_TRACE_START_EVENT
0x1800c93f8  call    fnEfsLogTrace1Strings
0x1800c93fd  mov     rcx, cs:g_hPublisher
0x1800c9404  lea     eax, [r14+4]
0x1800c9408  mov     [rsp+100h+var_D0], r12d
0x1800c940d  lea     r9, sourceString
0x1800c9414  or      r14d, 0FFFFFFFFh
0x1800c9418  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800c941f  cmp     eax, 4
0x1800c9422  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800c9429  mov     esi, r14d
0x1800c942c  mov     r12d, 27h ; '''
0x1800c9432  cmovnb  esi, eax
0x1800c9435  mov     [rsp+100h+dwFlags], r12d
0x1800c943a  sbb     ebx, ebx
0x1800c943c  and     ebx, 80070216h
0x1800c9442  mov     dword ptr [rsp+100h+pcbResult], ebx
0x1800c9446  call    fnEfsLogTrace1String1Dword
0x1800c944b  test    eax, eax
  ... truncated ...
```
