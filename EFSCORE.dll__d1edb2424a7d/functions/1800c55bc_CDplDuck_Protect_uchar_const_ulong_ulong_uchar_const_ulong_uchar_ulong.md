# CDplDuck::Protect(uchar const *,ulong,ulong,uchar const *,ulong,uchar * *,ulong *)

- ea: `0x1800c55bc`
- end: `0x1800c65a7`
- name: `?Protect@CDplDuck@@AEAAJPEBEKK0KPEAPEAEPEAK@Z`
- size: `4075`
- prototype: `int(CDplDuck *__hidden this, const unsigned __int8 *, unsigned int, unsigned int, const unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `3`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800a6cf0`
- `0x1800b7198`
- `0x1800c1780`

## callees

- `0x180004f86`
- `0x180005045`
- `0x180013260`
- `0x180056a08`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x180099734`
- `0x1800bd7a8`
- `0x1800bd810`
- `0x1800be8a8`
- `0x1800c55bc`
- `0x1800d5af8`
- `0x1800d6064`
- `0x1800dddf0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c611e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c611e`
- `CRYPT32!CryptUnprotectMemory` at `0x1800c6114`
- `CRYPT32!CryptUnprotectMemory` at `0x1800c6114`
- `bcrypt!BCryptGetProperty` at `0x1800c5810`
- `bcrypt!BCryptGetProperty` at `0x1800c5810`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800c60b1`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800c60b1`
- `bcrypt!BCryptDestroyHash` at `0x1800c6527`
- `bcrypt!BCryptDestroyHash` at `0x1800c6527`
- `bcrypt!BCryptFinishHash` at `0x1800c6410`
- `bcrypt!BCryptFinishHash` at `0x1800c6410`
- `bcrypt!BCryptHashData` at `0x1800c63b6`
- `bcrypt!BCryptHashData` at `0x1800c63b6`
- `bcrypt!BCryptDestroyKey` at `0x1800c64ff`
- `bcrypt!BCryptDestroyKey` at `0x1800c64ff`
- `bcrypt!BCryptCreateHash` at `0x1800c6342`
- `bcrypt!BCryptCreateHash` at `0x1800c6342`
- `bcrypt!BCryptGenRandom` at `0x1800c5f38`
- `bcrypt!BCryptGenRandom` at `0x1800c5f38`
- `bcrypt!BCryptEncrypt` at `0x1800c61a2`
- `bcrypt!BCryptEncrypt` at `0x1800c61a2`
- `ntdll!RtlNtStatusToDosError` at `0x1800c5824`
- `ntdll!RtlNtStatusToDosError` at `0x1800c5f4c`
- `ntdll!RtlNtStatusToDosError` at `0x1800c60d5`
- `ntdll!RtlNtStatusToDosError` at `0x1800c61b6`
- `ntdll!RtlNtStatusToDosError` at `0x1800c6356`
- `ntdll!RtlNtStatusToDosError` at `0x1800c63ca`
- `ntdll!RtlNtStatusToDosError` at `0x1800c6434`
- `ntdll!RtlNtStatusToDosError` at `0x1800c5824`
- `ntdll!RtlNtStatusToDosError` at `0x1800c5f4c`
- `ntdll!RtlNtStatusToDosError` at `0x1800c60d5`
- `ntdll!RtlNtStatusToDosError` at `0x1800c61b6`
- `ntdll!RtlNtStatusToDosError` at `0x1800c6356`
- `ntdll!RtlNtStatusToDosError` at `0x1800c63ca`
- `ntdll!RtlNtStatusToDosError` at `0x1800c6434`

## pseudocode

```c
__int64 __fastcall CDplDuck::Protect(
        CDplDuck *this,
        unsigned __int8 *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int8 *a5,
        unsigned int a6,
        unsigned __int8 **a7,
        unsigned int *a8)
{
  __int64 v10; // r14
  unsigned int v11; // r15d
  unsigned __int16 *v12; // rsi
  int v13; // ecx
  unsigned int v14; // ebx
  int v15; // r8d
  __int64 v16; // r13
  int v17; // ecx
  int Property; // eax
  int v19; // ecx
  int v20; // edi
  signed int v21; // eax
  ULONG v22; // r12d
  ULONG v23; // ecx
  int v24; // ecx
  int v25; // ecx
  ULONG v26; // eax
  unsigned int v27; // edi
  unsigned int v28; // eax
  int v29; // ecx
  int v30; // eax
  int v31; // ecx
  unsigned int v32; // edi
  int v33; // ecx
  unsigned int v34; // r15d
  int v35; // ecx
  int v36; // ecx
  int v37; // ecx
  int v38; // eax
  int v39; // ecx
  unsigned __int16 *v40; // r12
  int v41; // ecx
  int v42; // ecx
  int v43; // ecx
  int v44; // ecx
  char *v45; // r12
  unsigned __int16 v46; // ax
  UCHAR *v47; // rbx
  int v48; // eax
  int v49; // edi
  signed int v50; // eax
  CDplDuck *v51; // rbx
  int v52; // ecx
  UCHAR *v53; // r15
  int v54; // ecx
  int v55; // edi
  __int64 v56; // rax
  signed int v57; // eax
  signed int LastError; // eax
  ULONG cbOutput; // r8d
  _OWORD *v60; // r14
  int v61; // eax
  int v62; // edi
  signed int v63; // eax
  PUCHAR v64; // rdi
  size_t v65; // r8
  void *v66; // rdx
  __int64 v67; // rbx
  PUCHAR v68; // rcx
  int v69; // ecx
  UCHAR *v70; // rdi
  CDplDuck *v71; // r14
  int v72; // ecx
  void *v73; // rcx
  ULONG v74; // r9d
  PUCHAR v75; // r14
  int v76; // eax
  int v77; // edi
  signed int v78; // eax
  int v79; // eax
  int v80; // edi
  signed int v81; // eax
  int v82; // edi
  PUCHAR v83; // rax
  signed int v84; // eax
  char pcbResult; // [rsp+20h] [rbp-E0h]
  unsigned int pcbResulta; // [rsp+20h] [rbp-E0h]
  unsigned int pcbResultb; // [rsp+20h] [rbp-E0h]
  PUCHAR pbHashObject; // [rsp+50h] [rbp-B0h] BYREF
  ULONG cbInput; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v91; // [rsp+5Ch] [rbp-A4h] BYREF
  UCHAR pbOutput[4]; // [rsp+60h] [rbp-A0h] BYREF
  DWORD Size; // [rsp+64h] [rbp-9Ch]
  unsigned int Size_4; // [rsp+68h] [rbp-98h]
  CDplDuck *v95; // [rsp+70h] [rbp-90h]
  void *v96; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v97; // [rsp+80h] [rbp-80h]
  int v98; // [rsp+84h] [rbp-7Ch]
  BCRYPT_HASH_HANDLE phHash; // [rsp+88h] [rbp-78h] BYREF
  PUCHAR v100; // [rsp+90h] [rbp-70h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+98h] [rbp-68h] BYREF
  PUCHAR pbInput; // [rsp+A0h] [rbp-60h] BYREF
  ULONG v103; // [rsp+A8h] [rbp-58h] BYREF
  ULONG v104; // [rsp+ACh] [rbp-54h]
  PUCHAR pbSecret; // [rsp+B0h] [rbp-50h] BYREF
  PUCHAR pbKeyObject; // [rsp+B8h] [rbp-48h] BYREF
  void *v107; // [rsp+C0h] [rbp-40h]
  void *Src; // [rsp+C8h] [rbp-38h]
  unsigned int *v109; // [rsp+D0h] [rbp-30h]
  unsigned __int8 **v110; // [rsp+D8h] [rbp-28h]
  UCHAR pbIV[16]; // [rsp+E0h] [rbp-20h] BYREF

  v107 = a5;
  Size_4 = a6;
  v10 = a4;
  v11 = 0;
  Src = a2;
  v12 = 0;
  Size = a3;
  v95 = this;
  v110 = a7;
  v109 = a8;
  v98 = 0;
  *(_OWORD *)pbIV = 0;
  pbSecret = 0;
  v100 = 0;
  phKey = 0;
  pbKeyObject = 0;
  v91 = 0;
  cbInput = 0;
  phHash = 0;
  pbHashObject = 0;
  pbInput = 0;
  *(_DWORD *)pbOutput = 0;
  v103 = 0;
  v96 = 0;
  fnEfsLogTrace1Strings((_DWORD)this, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 39, 166);
  if ( a7 )
    *a7 = 0;
  if ( a8 )
    *a8 = 0;
  if ( !a2 )
  {
    pcbResult = -77;
LABEL_126:
    v14 = -2147024809;
    v15 = -2147024809;
    goto LABEL_127;
  }
  if ( !v107 )
  {
    pcbResult = -76;
    goto LABEL_126;
  }
  if ( !a7 )
  {
    pcbResult = -75;
LABEL_11:
    v14 = -2147467261;
    v15 = -2147467261;
LABEL_127:
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v15, 39, pcbResult);
    goto LABEL_128;
  }
  if ( !a8 )
  {
    pcbResult = -74;
    goto LABEL_11;
  }
  if ( !a3 || !(_DWORD)v10 || a3 < (unsigned int)v10 || !Size_4 )
  {
    pcbResult = -67;
    goto LABEL_126;
  }
  fnEfsLogTrace1Strings(v13, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 199);
  v16 = 32;
  v14 = DplibpMemAllocEx(32, 1, 1, &pbSecret);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v14,
              39,
              199) < 0 )
    goto LABEL_128;
  fnEfsLogTrace1Strings(v17, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 204);
  v14 = DplibpMemAllocEx(32, 1, 1, &v100);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v14,
              39,
              204) < 0 )
    goto LABEL_128;
  Property = BCryptGetProperty(*((BCRYPT_HANDLE *)v95 + 8), L"HashDigestLength", pbOutput, 4u, &v103, 0);
  v20 = Property;
  if ( Property )
  {
    v14 = 0;
    if ( Property < 0 )
    {
      v21 = RtlNtStatusToDosError(Property);
      v14 = v21;
      if ( !v21 || v21 == 317 )
      {
        v14 = v20 | 0x10000000;
      }
      else if ( v21 > 0 )
      {
        v14 = (unsigned __int16)v21 | 0x80070000;
      }
    }
    pcbResult = -37;
LABEL_28:
    v15 = v14;
    goto LABEL_127;
  }
  if ( (v10 & 0xF) != 0 )
  {
    fnEfsLogTrace1Strings(v19, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 234);
    v14 = ULongSub(0x10u, v10 & 0xF, &v91);
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                v14,
                39,
                234) < 0 )
    {
LABEL_128:
      v75 = pbHashObject;
      goto LABEL_129;
    }
    v11 = v91;
  }
  fnEfsLogTrace1Strings(v19, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 241);
  v22 = -1;
  v23 = -1;
  if ( (unsigned int)v10 + v11 >= (unsigned int)v10 )
    v23 = v10 + v11;
  cbInput = v23;
  v14 = (unsigned int)v10 + v11 < (unsigned int)v10 ? 0x80070216 : 0;
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v14,
              39,
              241) < 0 )
    goto LABEL_128;
  fnEfsLogTrace1Strings(v24, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 249);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              0,
              39,
              249) < 0 )
  {
    v14 = 0;
    goto LABEL_128;
  }
  fnEfsLogTrace1Strings(v25, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 251);
  v26 = cbInput;
  if ( Size > cbInput )
    v26 = Size;
  v27 = -1;
  v28 = v26 + 32;
  if ( v28 >= 0x20 )
    v27 = v28;
  v14 = v28 < 0x20 ? 0x80070216 : 0;
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v14,
              39,
              251) < 0 )
    goto LABEL_128;
  fnEfsLogTrace1Strings(v29, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 253);
  v30 = -1;
  if ( v27 + *(_DWORD *)pbOutput >= v27 )
    v30 = v27 + *(_DWORD *)pbOutput;
  v14 = v27 + *(_DWORD *)pbOutput < v27 ? 0x80070216 : 0;
  v97 = v30;
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v14,
              39,
              253) < 0 )
    goto LABEL_128;
  fnEfsLogTrace1Strings(v31, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 3);
  v32 = -1;
  if ( Size_4 < 0xFFFFFFFC )
    v32 = Size_4 + 4;
  v14 = Size_4 >= 0xFFFFFFFC ? 0x80070216 : 0;
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v14,
              39,
              3) < 0 )
    goto LABEL_128;
  fnEfsLogTrace1Strings(v33, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 5);
  v34 = -1;
  if ( v32 + 16 >= v32 )
    v34 = v32 + 16;
  v14 = v32 + 16 < v32 ? 0x80070216 : 0;
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v14,
              39,
              5) < 0 )
    goto LABEL_128;
  fnEfsLogTrace1Strings(v35, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 7);
  if ( v34 + cbInput >= v34 )
    v22 = v34 + cbInput;
  v14 = v34 + cbInput < v34 ? 0x80070216 : 0;
  v104 = v22;
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v14,
              39,
              7) < 0 )
    goto LABEL_128;
  fnEfsLogTrace1Strings(v36, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 16);
  v14 = DplibpMemAllocEx(v97, 1, 0, &v96);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v14,
              39,
              16) < 0 )
  {
    v12 = (unsigned __int16 *)v96;
    goto LABEL_128;
  }
  fnEfsLogTrace1Strings(v37, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 25);
  v14 = DplibpMemAllocEx(v22, 0, 0, &pbInput);
  v38 = fnEfsLogTrace1String1Dword(
          g_hPublisher,
          (unsigned int)EFS_TRACE_COMPLETE_EVENT,
          (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
          (unsigned int)&sourceString,
          v14,
          39,
          25);
  v12 = (unsigned __int16 *)v96;
  if ( v38 < 0 )
    goto LABEL_128;
  *(_DWORD *)v96 = 1048592;
  v12[2] = 16;
  fnEfsLogTrace1Strings(v39, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 49);
  v40 = v12 + 3;
  v14 = UShortAdd(v12[1], v12[2], v12 + 3);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v14,
              39,
              49) < 0 )
    goto LABEL_128;
  fnEfsLogTrace1Strings(v41, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 51);
  v14 = ULongToUShort(v10, v12 + 4);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v14,
              39,
              51) < 0 )
    goto LABEL_128;
  fnEfsLogTrace1Strings(v42, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 53);
  v14 = ULongToUShort(cbInput, v12 + 5);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v14,
              39,
              53) < 0 )
    goto LABEL_128;
  fnEfsLogTrace1Strings(v43, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 57);
  v14 = UShortAdd(*v40, v12[5], v12 + 6);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v14,
              39,
              57) < 0 )
    goto LABEL_128;
  fnEfsLogTrace1Strings(v44, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 59);
  v14 = ULongToUShort(*(unsigned int *)pbOutput, v12 + 7);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v14,
              39,
              59) < 0 )
    goto LABEL_128;
  v45 = (char *)v12 + *v40;
  v46 = v12[6];
  v96 = (char *)v12 + v12[1];
  v47 = (UCHAR *)v96;
  LOWORD(v91) = v46;
  memcpy_0(v45, Src, Size);
  v48 = BCryptGenRandom(0, v47, 0x10u, 2u);
  v49 = v48;
  if ( v48 )
  {
    v14 = 0;
    if ( v48 < 0 )
    {
      v50 = RtlNtStatusToDosError(v48);
      v14 = v50;
      if ( !v50 || v50 == 317 )
      {
        v14 = v49 | 0x10000000;
      }
      else if ( v50 > 0 )
      {
        v14 = (unsigned __int16)v50 | 0x80070000;
      }
    }
    pcbResult = 78;
    goto LABEL_28;
  }
  v51 = v95;
  v98 = CDplUser::UserSvcLock(*((CDplUser **)v95 + 16));
  fnEfsLogTrace1Strings(v52, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 90);
  v53 = pbSecret;
  v14 = CDplDuck::DeriveKey(v51, "Enc-AES-CBC", 0xCu, pbSecret, pcbResulta);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v14,
              39,
              90) < 0 )
    goto LABEL_128;
  fnEfsLogTrace1Strings(v54, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 99);
  v14 = DplibpMemAllocEx(*((unsigned int *)v95 + 10), 1, 1, &pbKeyObject);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v14,
              39,
              99) < 0 )
    goto LABEL_128;
  v55 = BCryptGenerateSymmetricKey(
          *((BCRYPT_ALG_HANDLE *)v95 + 4),
          &phKey,
          pbKeyObject,
          *((_DWORD *)v95 + 10),
          v53,
          0x20u,
          0);
  v56 = 32;
  do
  {
    *v53++ = 0;
    --v56;
  }
  while ( v56 );
  if ( v55 )
  {
    v14 = 0;
    if ( v55 < 0 )
    {
      v57 = RtlNtStatusToDosError(v55);
      v14 = v57;
      if ( !v57 || v57 == 317 )
      {
        v14 = v55 | 0x10000000;
      }
      else if ( v57 > 0 )
      {
        v14 = (unsigned __int16)v57 | 0x80070000;
      }
    }
    pcbResult = 113;
    goto LABEL_28;
  }
  if ( !CryptUnprotectMemory(v45, Size, 0) )
  {
    LastError = GetLastError();
    v14 = LastError;
    if ( LastError > 0 )
      v14 = (unsigned __int16)LastError | 0x80070000;
    pcbResult = 124;
    goto LABEL_28;
  }
  cbOutput = cbInput;
  if ( cbInput > (unsigned int)v10 )
  {
    memset_0(&v45[v10], 0, cbInput - (unsigned int)v10);
    cbOutput = cbInput;
  }
  v60 = v96;
  *(_OWORD *)pbIV = *(_OWORD *)v96;
  v61 = BCryptEncrypt(phKey, (PUCHAR)v45, cbOutput, 0, pbIV, 0x10u, (PUCHAR)v45, cbOutput, &cbInput, 0);
  v62 = v61;
  if ( v61 )
  {
    v14 = 0;
    if ( v61 < 0 )
    {
      v63 = RtlNtStatusToDosError(v61);
      v14 = v63;
      if ( !v63 || v63 == 317 )
      {
        v14 = v62 | 0x10000000;
      }
      else if ( v63 > 0 )
      {
        v14 = (unsigned __int16)v63 | 0x80070000;
      }
    }
    pcbResult = -105;
    goto LABEL_28;
  }
  v64 = pbInput;
  v65 = Size_4;
  v66 = v107;
  v67 = Size_4;
  v68 = pbInput + 4;
  *(_DWORD *)pbInput = Size_4;
  memcpy_0(v68, v66, v65);
  *(_OWORD *)&v64[v67 + 4] = *v60;
  memcpy_0(&v64[v67 + 20], v45, cbInput);
  fnEfsLogTrace1Strings(v69, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 184);
  v70 = v100;
  v71 = v95;
  v14 = CDplDuck::DeriveKey(v95, "Auth-HMAC-SHA256", 0x11u, v100, pcbResultb);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v14,
              39,
              184) < 0 )
    goto LABEL_128;
  fnEfsLogTrace1Strings(v72, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 39, 193);
  v14 = DplibpMemAllocEx(*((unsigned int *)v71 + 18), 1, 1, &pbHashObject);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v14,
              39,
              193) < 0 )
    goto LABEL_128;
  v73 = (void *)*((_QWORD *)v71 + 8);
  v74 = *((_DWORD *)v71 + 18);
  v75 = pbHashObject;
  v76 = BCryptCreateHash(v73, &phHash, pbHashObject, v74, v70, 0x20u, 0);
  v77 = v76;
  if ( v76 )
  {
    v14 = 0;
    if ( v76 < 0 )
    {
      v78 = RtlNtStatusToDosError(v76);
      v14 = v78;
      if ( !v78 || v78 == 317 )
      {
        v14 = v77 | 0x10000000;
      }
      else if ( v78 > 0 )
      {
        v14 = (unsigned __int16)v78 | 0x80070000;
      }
    }
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v14, 39, 205);
  }
  else
  {
    v79 = BCryptHashData(phHash, pbInput, v104, 0);
    v80 = v79;
    if ( v79 )
    {
      v14 = 0;
      if ( v79 < 0 )
      {
        v81 = RtlNtStatusToDosError(v79);
        v14 = v81;
        if ( !v81 || v81 == 317 )
        {
          v14 = v80 | 0x10000000;
        }
        else if ( v81 > 0 )
        {
          v14 = (unsigned __int16)v81 | 0x80070000;
        }
      }
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v14, 39, 219);
    }
    else
    {
      v82 = BCryptFinishHash(phHash, (PUCHAR)v12 + (unsigned __int16)v91, *(ULONG *)pbOutput, 0);
      v83 = v100;
      do
      {
        *v83++ = 0;
        --v16;
      }
      while ( v16 );
      if ( v82 )
      {
        v14 = 0;
        if ( v82 < 0 )
        {
          v84 = RtlNtStatusToDosError(v82);
          v14 = v84;
          if ( !v84 || v84 == 317 )
          {
            v14 = v82 | 0x10000000;
          }
          else if ( v84 > 0 )
          {
            v14 = (unsigned __int16)v84 | 0x80070000;
          }
        }
        fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v14, 39, 228);
      }
      else
      {
        *v109 = v97;
        *v110 = (unsigned __int8 *)v12;
        v12 = 0;
      }
    }
  }
LABEL_129:
  CDplUser::UserSvcUnlock(*((CDplUser **)v95 + 16), v98);
  if ( pbSecret )
    DplibMemFree(pbSecret);
  if ( v100 )
    DplibMemFree(v100);
  if ( v12 )
    DplibMemFree(v12);
  if ( phKey )
  {
    BCryptDestroyKey(phKey);
    phKey = 0;
  }
  if ( pbKeyObject )
    DplibMemFree(pbKeyObject);
  if ( phHash )
  {
    BCryptDestroyHash(phHash);
    phHash = 0;
  }
  if ( v75 )
    DplibMemFree(v75);
  if ( pbInput )
    DplibMemFree(pbInput);
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&sourceString,
    v14,
    39,
    11);
  return v14;
}

```

## disassembly

```asm
0x1800c55bc  push    rbp
0x1800c55be  push    rbx
0x1800c55bf  push    rsi
0x1800c55c0  push    rdi
0x1800c55c1  push    r12
0x1800c55c3  push    r13
0x1800c55c5  push    r14
0x1800c55c7  push    r15
0x1800c55c9  lea     rbp, [rsp-8]
0x1800c55ce  sub     rsp, 108h
0x1800c55d5  mov     rax, cs:__security_cookie
0x1800c55dc  xor     rax, rsp
0x1800c55df  mov     [rbp+40h+var_50], rax
0x1800c55e3  mov     rax, [rbp+40h+arg_20]
0x1800c55e7  mov     ebx, r8d
0x1800c55ea  mov     r12, [rbp+40h+arg_30]
0x1800c55f1  lea     r8, sourceString
0x1800c55f8  mov     rdi, [rbp+40h+arg_38]
0x1800c55ff  mov     r13, rdx
0x1800c5602  mov     [rbp+40h+var_80], rax
0x1800c5606  xorps   xmm0, xmm0
0x1800c5609  mov     eax, [rbp+40h+arg_28]
0x1800c560c  mov     dword ptr [rsp+140h+Size+4], eax
0x1800c5610  xor     eax, eax
0x1800c5612  mov     r14d, r9d
0x1800c5615  mov     r15d, eax
0x1800c5618  mov     [rbp+40h+Src], rdx
0x1800c561c  mov     esi, eax
0x1800c561e  lea     rdx, EFS_TRACE_ENTER_EVENT
0x1800c5625  mov     dword ptr [rsp+140h+Size], ebx
0x1800c5629  lea     r9d, [rax+27h]
0x1800c562d  mov     [rsp+140h+var_D0], rcx
0x1800c5632  mov     [rbp+40h+var_68], r12
0x1800c5636  mov     [rbp+40h+var_70], rdi
0x1800c563a  mov     [rbp+40h+var_BC], eax
0x1800c563d  movups  xmmword ptr [rbp+40h+pbIV], xmm0
0x1800c5641  mov     [rbp+40h+pbSecret], rax
0x1800c5645  mov     [rbp+40h+var_B0], rax
0x1800c5649  mov     [rbp+40h+phKey], rax
0x1800c564d  mov     [rbp+40h+pbKeyObject], rax
0x1800c5651  mov     [rsp+140h+var_E4], eax
0x1800c5655  mov     [rsp+140h+cbInput], eax
0x1800c5659  mov     [rbp+40h+phHash], rax
0x1800c565d  mov     [rsp+140h+pbHashObject], rax
0x1800c5662  mov     [rbp+40h+pbInput], rax
0x1800c5666  mov     dword ptr [rsp+140h+pbOutput], eax
0x1800c566a  mov     [rbp+40h+var_98], eax
0x1800c566d  mov     [rsp+140h+var_C8], rax
0x1800c5672  mov     dword ptr [rsp+140h+pcbResult], 1FA6h
0x1800c567a  call    fnEfsLogTrace1Strings
0x1800c567f  test    r12, r12
0x1800c5682  jz      short loc_1800C568A
0x1800c5684  xor     eax, eax
0x1800c5686  mov     [r12], rax
0x1800c568a  test    rdi, rdi
0x1800c568d  jz      short loc_1800C5693
0x1800c568f  xor     eax, eax
0x1800c5691  mov     [rdi], eax
0x1800c5693  test    r13, r13
0x1800c5696  jnz     short loc_1800C56A5
0x1800c5698  mov     dword ptr [rsp+140h+pcbResult], 1FB3h
0x1800c56a0  jmp     loc_1800C6490
0x1800c56a5  cmp     [rbp+40h+var_80], rsi
0x1800c56a9  jnz     short loc_1800C56B8
0x1800c56ab  mov     dword ptr [rsp+140h+pcbResult], 1FB4h
0x1800c56b3  jmp     loc_1800C6490
0x1800c56b8  test    r12, r12
0x1800c56bb  jnz     short loc_1800C56D5
0x1800c56bd  mov     dword ptr [rsp+140h+pcbResult], 1FB5h
0x1800c56c5  mov     ebx, 80004003h
0x1800c56ca  mov     r8d, 80004003h
0x1800c56d0  jmp     loc_1800C649B
0x1800c56d5  test    rdi, rdi
0x1800c56d8  jnz     short loc_1800C56E4
0x1800c56da  mov     dword ptr [rsp+140h+pcbResult], 1FB6h
0x1800c56e2  jmp     short loc_1800C56C5
0x1800c56e4  test    ebx, ebx
0x1800c56e6  jz      loc_1800C6488
0x1800c56ec  test    r14d, r14d
0x1800c56ef  jz      loc_1800C6488
0x1800c56f5  cmp     ebx, r14d
0x1800c56f8  jb      loc_1800C6488
0x1800c56fe  cmp     dword ptr [rsp+140h+Size+4], esi
0x1800c5702  jz      loc_1800C6488
0x1800c5708  mov     r12d, 27h ; '''
0x1800c570e  lea     r8, sourceString
0x1800c5715  mov     edi, 1FC7h
0x1800c571a  lea     rdx, EFS_TRACE_START_EVENT
0x1800c5721  mov     r9d, r12d
0x1800c5724  mov     dword ptr [rsp+140h+pcbResult], edi
0x1800c5728  call    fnEfsLogTrace1Strings
0x1800c572d  lea     edx, [r12-26h]
0x1800c5732  lea     r13d, [r12-7]
0x1800c5737  mov     r8d, edx
0x1800c573a  lea     r9, [rbp+40h+pbSecret]
0x1800c573e  mov     ecx, r13d
0x1800c5741  call    ?DplibpMemAllocEx@@YAJ_KW4_DPLIB_ALLOC_QOS_LEVEL@@HPEAPEAX@Z; DplibpMemAllocEx(unsigned __int64,_DPLIB_ALLOC_QOS_LEVEL,int,void * *)
0x1800c5746  mov     rcx, cs:g_hPublisher
0x1800c574d  lea     r9, sourceString
0x1800c5754  mov     [rsp+140h+var_110], edi
0x1800c5758  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800c575f  mov     [rsp+140h+dwFlags], r12d
0x1800c5764  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800c576b  mov     dword ptr [rsp+140h+pcbResult], eax
0x1800c576f  mov     ebx, eax
0x1800c5771  call    fnEfsLogTrace1String1Dword
0x1800c5776  test    eax, eax
0x1800c5778  js      loc_1800C64B4
0x1800c577e  mov     edi, 1FCCh
0x1800c5783  lea     r8, sourceString
0x1800c578a  mov     r9d, r12d
0x1800c578d  mov     dword ptr [rsp+140h+pcbResult], edi
0x1800c5791  lea     rdx, EFS_TRACE_START_EVENT
0x1800c5798  call    fnEfsLogTrace1Strings
0x1800c579d  lea     edx, [r12-26h]
0x1800c57a2  mov     ecx, r13d
0x1800c57a5  mov     r8d, edx
0x1800c57a8  lea     r9, [rbp+40h+var_B0]
0x1800c57ac  call    ?DplibpMemAllocEx@@YAJ_KW4_DPLIB_ALLOC_QOS_LEVEL@@HPEAPEAX@Z; DplibpMemAllocEx(unsigned __int64,_DPLIB_ALLOC_QOS_LEVEL,int,void * *)
0x1800c57b1  mov     rcx, cs:g_hPublisher
0x1800c57b8  lea     r9, sourceString
0x1800c57bf  mov     [rsp+140h+var_110], edi
0x1800c57c3  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800c57ca  mov     [rsp+140h+dwFlags], r12d
0x1800c57cf  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800c57d6  mov     dword ptr [rsp+140h+pcbResult], eax
0x1800c57da  mov     ebx, eax
0x1800c57dc  call    fnEfsLogTrace1String1Dword
0x1800c57e1  test    eax, eax
0x1800c57e3  js      loc_1800C64B4
0x1800c57e9  lea     rax, [rbp+40h+var_98]
0x1800c57ed  mov     [rsp+140h+dwFlags], esi; dwFlags
0x1800c57f1  mov     [rsp+140h+pcbResult], rax; pcbResult
0x1800c57f6  lea     r9d, [r12-23h]; cbOutput
0x1800c57fb  mov     rax, [rsp+140h+var_D0]
0x1800c5800  lea     r8, [rsp+140h+pbOutput]; pbOutput
0x1800c5805  lea     rdx, aHashdigestleng; "HashDigestLength"
0x1800c580c  mov     rcx, [rax+40h]; hObject
0x1800c5810  call    cs:__imp_BCryptGetProperty
0x1800c5816  mov     edi, eax
0x1800c5818  test    eax, eax
0x1800c581a  jz      short loc_1800C585F
0x1800c581c  xor     ebx, ebx
0x1800c581e  test    eax, eax
0x1800c5820  jns     short loc_1800C584C
0x1800c5822  mov     ecx, eax; Status
0x1800c5824  call    cs:__imp_RtlNtStatusToDosError
0x1800c582a  mov     ebx, eax
0x1800c582c  test    eax, eax
0x1800c582e  jz      short loc_1800C5846
0x1800c5830  cmp     eax, 13Dh
0x1800c5835  jz      short loc_1800C5846
0x1800c5837  test    eax, eax
0x1800c5839  jle     short loc_1800C584C
0x1800c583b  movzx   ebx, ax
0x1800c583e  or      ebx, 80070000h
0x1800c5844  jmp     short loc_1800C584C
0x1800c5846  mov     ebx, edi
0x1800c5848  bts     ebx, 1Ch
0x1800c584c  mov     dword ptr [rsp+140h+pcbResult], 1FDBh
0x1800c5854  mov     r9d, r12d
0x1800c5857  mov     r8d, ebx
0x1800c585a  jmp     loc_1800C64A1
0x1800c585f  mov     ebx, r14d
0x1800c5862  and     ebx, 0Fh
0x1800c5865  jz      short loc_1800C58D4
0x1800c5867  mov     edi, 1FEAh
0x1800c586c  lea     r8, sourceString
0x1800c5873  mov     r9d, r12d
0x1800c5876  mov     dword ptr [rsp+140h+pcbResult], edi
0x1800c587a  lea     rdx, EFS_TRACE_START_EVENT
0x1800c5881  call    fnEfsLogTrace1Strings
0x1800c5886  lea     r8, [rsp+140h+var_E4]; unsigned int *
0x1800c588b  mov     edx, ebx; unsigned int
0x1800c588d  mov     ecx, 10h; unsigned int
0x1800c5892  call    ?ULongSub@@YAJKKPEAK@Z; ULongSub(ulong,ulong,ulong *)
0x1800c5897  mov     rcx, cs:g_hPublisher
0x1800c589e  lea     r9, sourceString
0x1800c58a5  mov     [rsp+140h+var_110], edi
0x1800c58a9  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800c58b0  mov     [rsp+140h+dwFlags], r12d
0x1800c58b5  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800c58bc  mov     dword ptr [rsp+140h+pcbResult], eax
0x1800c58c0  mov     ebx, eax
0x1800c58c2  call    fnEfsLogTrace1String1Dword
0x1800c58c7  test    eax, eax
0x1800c58c9  js      loc_1800C64B4
0x1800c58cf  mov     r15d, [rsp+140h+var_E4]
0x1800c58d4  mov     edi, 1FF1h
0x1800c58d9  lea     r8, sourceString
0x1800c58e0  mov     r9d, r12d
0x1800c58e3  mov     dword ptr [rsp+140h+pcbResult], edi
0x1800c58e7  lea     rdx, EFS_TRACE_START_EVENT
0x1800c58ee  call    fnEfsLogTrace1Strings
0x1800c58f3  lea     eax, [r14+r15]
0x1800c58f7  mov     [rsp+140h+var_110], edi
0x1800c58fb  or      r12d, 0FFFFFFFFh
0x1800c58ff  mov     [rsp+140h+dwFlags], 27h ; '''
0x1800c5907  cmp     eax, r14d
0x1800c590a  lea     r9, sourceString
0x1800c5911  mov     ecx, r12d
0x1800c5914  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800c591b  cmovnb  ecx, eax
0x1800c591e  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800c5925  sbb     ebx, ebx
0x1800c5927  mov     [rsp+140h+cbInput], ecx
0x1800c592b  mov     rcx, cs:g_hPublisher
0x1800c5932  and     ebx, 80070216h
0x1800c5938  mov     dword ptr [rsp+140h+pcbResult], ebx
0x1800c593c  call    fnEfsLogTrace1String1Dword
0x1800c5941  test    eax, eax
0x1800c5943  js      loc_1800C64B4
0x1800c5949  lea     ebx, [rdi+8]
0x1800c594c  mov     r9d, 27h ; '''
0x1800c5952  lea     r8, sourceString
0x1800c5959  mov     dword ptr [rsp+140h+pcbResult], ebx
0x1800c595d  lea     rdx, EFS_TRACE_START_EVENT
0x1800c5964  call    fnEfsLogTrace1Strings
0x1800c5969  mov     rcx, cs:g_hPublisher
0x1800c5970  lea     r9, sourceString
0x1800c5977  mov     [rsp+140h+var_110], ebx
0x1800c597b  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800c5982  mov     [rsp+140h+dwFlags], 27h ; '''
0x1800c598a  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800c5991  mov     dword ptr [rsp+140h+pcbResult], esi
0x1800c5995  call    fnEfsLogTrace1String1Dword
0x1800c599a  test    eax, eax
0x1800c599c  js      loc_1800C6484
0x1800c59a2  lea     r15d, [rdi+0Ah]
0x1800c59a6  mov     r9d, 27h ; '''
0x1800c59ac  lea     r8, sourceString
0x1800c59b3  mov     dword ptr [rsp+140h+pcbResult], r15d
0x1800c59b8  lea     rdx, EFS_TRACE_START_EVENT
0x1800c59bf  call    fnEfsLogTrace1Strings
0x1800c59c4  mov     eax, [rsp+140h+cbInput]
0x1800c59c8  lea     r9, sourceString
0x1800c59cf  cmp     dword ptr [rsp+140h+Size], eax
0x1800c59d3  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800c59da  mov     rcx, cs:g_hPublisher
0x1800c59e1  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800c59e8  cmova   eax, dword ptr [rsp+140h+Size]
0x1800c59ed  mov     edi, r12d
0x1800c59f0  add     eax, r13d
0x1800c59f3  mov     [rsp+140h+var_110], r15d
0x1800c59f8  cmp     eax, r13d
0x1800c59fb  mov     [rsp+140h+dwFlags], 27h ; '''
0x1800c5a03  cmovnb  edi, eax
0x1800c5a06  sbb     ebx, ebx
0x1800c5a08  and     ebx, 80070216h
0x1800c5a0e  mov     dword ptr [rsp+140h+pcbResult], ebx
0x1800c5a12  call    fnEfsLogTrace1String1Dword
0x1800c5a17  test    eax, eax
0x1800c5a19  js      loc_1800C64B4
0x1800c5a1f  mov     r15d, 1FFDh
0x1800c5a25  lea     r8, sourceString
0x1800c5a2c  mov     r9d, 27h ; '''
0x1800c5a32  mov     dword ptr [rsp+140h+pcbResult], r15d
0x1800c5a37  lea     rdx, EFS_TRACE_START_EVENT
0x1800c5a3e  call    fnEfsLogTrace1Strings
0x1800c5a43  mov     ecx, dword ptr [rsp+140h+pbOutput]
0x1800c5a47  lea     r9, sourceString
0x1800c5a4e  add     ecx, edi
0x1800c5a50  mov     [rsp+140h+var_110], r15d
0x1800c5a55  cmp     ecx, edi
0x1800c5a57  mov     [rsp+140h+dwFlags], 27h ; '''
0x1800c5a5f  mov     eax, r12d
0x1800c5a62  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800c5a69  cmovnb  eax, ecx
0x1800c5a6c  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800c5a73  mov     rcx, cs:g_hPublisher
0x1800c5a7a  sbb     ebx, ebx
0x1800c5a7c  and     ebx, 80070216h
0x1800c5a82  mov     [rbp+40h+var_C0], eax
0x1800c5a85  mov     dword ptr [rsp+140h+pcbResult], ebx
0x1800c5a89  call    fnEfsLogTrace1String1Dword
0x1800c5a8e  test    eax, eax
0x1800c5a90  js      loc_1800C64B4
0x1800c5a96  mov     r15d, 2003h
0x1800c5a9c  lea     r8, sourceString
0x1800c5aa3  mov     r9d, 27h ; '''
0x1800c5aa9  mov     dword ptr [rsp+140h+pcbResult], r15d
0x1800c5aae  lea     rdx, EFS_TRACE_START_EVENT
0x1800c5ab5  call    fnEfsLogTrace1Strings
0x1800c5aba  mov     eax, dword ptr [rsp+140h+Size+4]
0x1800c5abe  lea     r9, sourceString
0x1800c5ac5  mov     rcx, cs:g_hPublisher
0x1800c5acc  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800c5ad3  add     eax, 4
0x1800c5ad6  mov     [rsp+140h+var_110], r15d
0x1800c5adb  cmp     eax, 4
0x1800c5ade  mov     [rsp+140h+dwFlags], 27h ; '''
0x1800c5ae6  mov     edi, r12d
0x1800c5ae9  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800c5af0  cmovnb  edi, eax
0x1800c5af3  sbb     ebx, ebx
0x1800c5af5  and     ebx, 80070216h
0x1800c5afb  mov     dword ptr [rsp+140h+pcbResult], ebx
0x1800c5aff  call    fnEfsLogTrace1String1Dword
0x1800c5b04  test    eax, eax
0x1800c5b06  js      loc_1800C64B4
  ... truncated ...
```
