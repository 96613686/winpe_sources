# CfRegisterSyncRoot

- ea: `0x180006060`
- end: `0x1800073a9`
- name: `CfRegisterSyncRoot`
- size: `4937`
- prototype: `__int64 __fastcall(__int64, __int64, _DWORD *, int)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, reparse_path, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001a80`
- `0x1800022ee`
- `0x18000446c`
- `0x180006060`
- `0x18000add8`
- `0x18000b284`
- `0x18000f6fc`
- `0x1800106c0`
- `0x180011338`
- `0x1800118a4`
- `0x180011d18`
- `0x180011e18`
- `0x18001be44`
- `0x18001be50`
- `0x18001be5c`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180006435`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180006459`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180006435`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180006459`
- `ntdll!RtlSetThreadPlaceholderCompatibilityMode` at `0x1800060cc`
- `ntdll!RtlSetThreadPlaceholderCompatibilityMode` at `0x180007381`
- `ntdll!RtlSetThreadPlaceholderCompatibilityMode` at `0x1800060cc`
- `ntdll!RtlSetThreadPlaceholderCompatibilityMode` at `0x180007381`
- `ntdll!RtlComputeCrc32` at `0x180006eef`
- `ntdll!RtlComputeCrc32` at `0x180006eef`
- `ntdll!RtlNtStatusToDosError` at `0x1800065e5`
- `ntdll!RtlNtStatusToDosError` at `0x1800067a6`
- `ntdll!RtlNtStatusToDosError` at `0x180006882`
- `ntdll!RtlNtStatusToDosError` at `0x18000695a`
- `ntdll!RtlNtStatusToDosError` at `0x180006a15`
- `ntdll!RtlNtStatusToDosError` at `0x180006abe`
- `ntdll!RtlNtStatusToDosError` at `0x180006b6c`
- `ntdll!RtlNtStatusToDosError` at `0x180006c1b`
- `ntdll!RtlNtStatusToDosError` at `0x180006cda`
- `ntdll!RtlNtStatusToDosError` at `0x180006de1`
- `ntdll!RtlNtStatusToDosError` at `0x180006e95`
- `ntdll!RtlNtStatusToDosError` at `0x1800065e5`
- `ntdll!RtlNtStatusToDosError` at `0x1800067a6`
- `ntdll!RtlNtStatusToDosError` at `0x180006882`
- `ntdll!RtlNtStatusToDosError` at `0x18000695a`
- `ntdll!RtlNtStatusToDosError` at `0x180006a15`
- `ntdll!RtlNtStatusToDosError` at `0x180006abe`
- `ntdll!RtlNtStatusToDosError` at `0x180006b6c`
- `ntdll!RtlNtStatusToDosError` at `0x180006c1b`
- `ntdll!RtlNtStatusToDosError` at `0x180006cda`
- `ntdll!RtlNtStatusToDosError` at `0x180006de1`
- `ntdll!RtlNtStatusToDosError` at `0x180006e95`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800060dd`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800060dd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000669a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006f32`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007341`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000736a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000669a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006f32`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007341`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000736a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800066af`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006f40`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800066af`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006f40`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000734f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007378`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000734f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007378`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000735f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000735f`

## string_xrefs

- `0x18000611e`: `SyncRootPath is NULL`
- `0x180006618`: `CfpCreateFile on SyncRootPath failed`
- `0x180006c4c`: `SetSyncRootHardLinkPolicy Failed`
- `0x1800072e4`: `CfpRegisterSyncRoot (Update) Failed`

## pseudocode

```c
__int64 __fastcall CfRegisterSyncRoot(__int64 a1, __int64 a2, _DWORD *a3, int a4)
{
  __int64 v7; // r12
  _DWORD *v8; // r15
  __int64 v9; // rcx
  char v10; // di
  signed int v11; // esi
  __int64 v12; // rcx
  const wchar_t *v13; // rax
  wchar_t *v14; // rbx
  bool v15; // cf
  const wchar_t *v16; // r8
  void *v17; // rdx
  unsigned int v18; // r13d
  int v19; // edi
  int v20; // eax
  int v21; // ebx
  int v22; // ecx
  int v23; // r14d
  int v24; // eax
  unsigned int v25; // r12d
  __int64 v26; // rcx
  unsigned int v27; // r14d
  __int64 v28; // rcx
  __int64 v29; // rdx
  NTSTATUS File; // eax
  __int64 v31; // rcx
  bool v32; // zf
  unsigned int v33; // r12d
  HANDLE ProcessHeap; // rax
  __int64 v35; // rcx
  unsigned int *v36; // r13
  char *v37; // rdx
  NTSTATUS v38; // r12d
  NTSTATUS v39; // ecx
  __int64 v40; // rcx
  size_t v41; // r8
  __int64 v42; // rcx
  char *v43; // rcx
  signed int v44; // eax
  __int64 v45; // rcx
  NTSTATUS v46; // ecx
  __int64 v47; // rcx
  unsigned int v48; // eax
  wchar_t *v49; // rcx
  signed int v50; // eax
  __int64 v51; // rcx
  NTSTATUS v52; // ecx
  __int64 v53; // rcx
  unsigned int v54; // eax
  wchar_t *v55; // rcx
  signed int v56; // eax
  __int64 v57; // rcx
  NTSTATUS v58; // ecx
  __int64 v59; // rcx
  __int64 v60; // rax
  signed int v61; // eax
  __int64 v62; // rcx
  NTSTATUS v63; // ecx
  __int64 v64; // rcx
  __int64 v65; // rax
  signed int v66; // eax
  __int64 v67; // rcx
  NTSTATUS v68; // ecx
  __int64 v69; // rcx
  __int64 v70; // rax
  int v71; // ecx
  signed int v72; // eax
  __int64 v73; // rcx
  NTSTATUS v74; // ecx
  __int64 v75; // rcx
  __int64 v76; // rax
  signed int v77; // eax
  __int64 v78; // rcx
  __int64 v79; // rbx
  NTSTATUS v80; // ecx
  __int64 v81; // rdx
  __int128 v82; // xmm0
  __int64 v83; // rax
  signed int v84; // eax
  __int64 v85; // rcx
  unsigned int Guid; // eax
  __int64 v87; // rcx
  NTSTATUS v88; // ecx
  __int64 v89; // rdx
  __int128 v90; // xmm0
  __int64 v91; // rax
  signed int v92; // eax
  __int64 v93; // rcx
  __int64 v94; // rcx
  __int64 v95; // rax
  signed int v96; // eax
  __int64 v97; // rcx
  unsigned int v98; // r8d
  int v99; // eax
  int v100; // r14d
  unsigned int v101; // edi
  HANDLE v102; // rax
  const wchar_t *v103; // rcx
  unsigned int SyncRootInfoByHandle; // eax
  __int64 v105; // rcx
  unsigned int v106; // eax
  __int64 v107; // rcx
  int v108; // eax
  __int64 v109; // rcx
  __int64 v110; // rcx
  const wchar_t *v111; // rcx
  int v112; // eax
  __int64 v113; // rcx
  int v114; // eax
  __int64 v115; // rcx
  __int64 v116; // rcx
  size_t v117; // rdi
  __int64 v118; // rcx
  unsigned int v119; // eax
  __int64 v120; // rcx
  HANDLE v121; // rax
  HANDLE v122; // rcx
  HANDLE v123; // rax
  size_t v125; // [rsp+20h] [rbp-E0h]
  char v126; // [rsp+50h] [rbp-B0h]
  const wchar_t *v127; // [rsp+58h] [rbp-A8h]
  wchar_t *Source; // [rsp+60h] [rbp-A0h]
  unsigned int v129; // [rsp+68h] [rbp-98h]
  int v130; // [rsp+6Ch] [rbp-94h]
  wchar_t *String2; // [rsp+78h] [rbp-88h]
  ULONG cbInput; // [rsp+80h] [rbp-80h]
  int v134; // [rsp+84h] [rbp-7Ch]
  int v135; // [rsp+88h] [rbp-78h] BYREF
  int v136; // [rsp+8Ch] [rbp-74h]
  unsigned int Size; // [rsp+90h] [rbp-70h]
  int Size_4; // [rsp+94h] [rbp-6Ch]
  HANDLE hObject; // [rsp+98h] [rbp-68h]
  __int64 v140; // [rsp+A0h] [rbp-60h]
  int Buf2; // [rsp+A8h] [rbp-58h] BYREF
  int v142; // [rsp+ACh] [rbp-54h] BYREF
  unsigned __int64 v143; // [rsp+B0h] [rbp-50h]
  unsigned __int64 UnbiasedTime; // [rsp+B8h] [rbp-48h] BYREF
  void *Src; // [rsp+C0h] [rbp-40h]
  __int64 v146; // [rsp+C8h] [rbp-38h]
  char v147[8]; // [rsp+D0h] [rbp-30h] BYREF
  const wchar_t *v148; // [rsp+D8h] [rbp-28h]
  int v149; // [rsp+E0h] [rbp-20h]
  char v150; // [rsp+E4h] [rbp-1Ch]
  UCHAR pbOutput[16]; // [rsp+130h] [rbp+30h] BYREF

  *(_QWORD *)pbOutput = a2;
  v140 = a1;
  hObject = (HANDLE)-1LL;
  LODWORD(String2) = 0;
  v135 = 0;
  UnbiasedTime = 0;
  v7 = 0;
  v8 = 0;
  memset_0(v147, 0, 0x58u);
  LOBYTE(v9) = 2;
  v126 = RtlSetThreadPlaceholderCompatibilityMode(v9);
  v10 = v126;
  QueryUnbiasedInterruptTime(&UnbiasedTime);
  v11 = a1 == 0 ? 0x57 : 0;
  v12 = v11 | 0x80070000;
  if ( !v140 )
    v11 |= 0x80070000;
  if ( v11 )
  {
    TlmChk(v12, 1498, "CfRegisterSyncRoot", (unsigned int)v11);
    if ( v11 < 0 )
    {
      v13 = L"SyncRootPath is NULL";
LABEL_6:
      v14 = 0;
      goto LABEL_330;
    }
  }
  v11 = a2 == 0 ? 0x57 : 0;
  if ( !a2 )
    v11 |= 0x80070000;
  if ( v11 )
  {
    TlmChk(v12, 1499, "CfRegisterSyncRoot", (unsigned int)v11);
    if ( v11 < 0 )
    {
      v13 = L"Registration is NULL";
      goto LABEL_6;
    }
  }
  v11 = *(_QWORD *)(a2 + 8) == 0 ? 0x57 : 0;
  if ( !*(_QWORD *)(a2 + 8) )
    v11 = (*(_QWORD *)(a2 + 8) == 0 ? 0x57 : 0) | 0x80070000;
  if ( v11 )
  {
    TlmChk(v12, 1500, "CfRegisterSyncRoot", (unsigned int)v11);
    if ( v11 < 0 )
    {
      v13 = L"ProviderName is NULL";
      goto LABEL_6;
    }
  }
  v11 = *(_QWORD *)(a2 + 16) == 0 ? 0x57 : 0;
  if ( !*(_QWORD *)(a2 + 16) )
    v11 = (*(_QWORD *)(a2 + 16) == 0 ? 0x57 : 0) | 0x80070000;
  if ( v11 )
  {
    TlmChk(v12, 1501, "CfRegisterSyncRoot", (unsigned int)v11);
    if ( v11 < 0 )
    {
      v13 = L"ProviderVersion is NULL";
      goto LABEL_6;
    }
  }
  if ( !*(_QWORD *)(a2 + 24) || (v11 = 87, *(_DWORD *)(a2 + 32)) )
    v11 = 0;
  if ( v11 )
    v11 |= 0x80070000;
  if ( v11 )
  {
    TlmChk(v12, 1505, "CfRegisterSyncRoot", (unsigned int)v11);
    v13 = L"Invalid SyncRootIdentity";
    goto LABEL_6;
  }
  if ( !*(_QWORD *)(a2 + 40) || (v11 = 87, *(_DWORD *)(a2 + 48)) )
    v11 = 0;
  if ( v11 )
    v11 |= 0x80070000;
  if ( v11 )
  {
    TlmChk(v12, 1509, "CfRegisterSyncRoot", (unsigned int)v11);
    v13 = L"Invalid FileIdentity";
    goto LABEL_6;
  }
  v11 = a3 == 0 ? 0x57 : 0;
  if ( !a3 )
    v11 |= 0x80070000;
  if ( v11 )
  {
    TlmChk(v12, 1511, "CfRegisterSyncRoot", (unsigned int)v11);
    if ( v11 < 0 )
    {
      v13 = L"Policies can't be NULL";
      goto LABEL_6;
    }
  }
  v11 = *a3 < 0x14u ? 0x57 : 0;
  if ( *a3 < 0x14u )
    v11 = (*a3 < 0x14u ? 0x57 : 0) | 0x80070000;
  if ( v11 )
  {
    TlmChk(v12, 1515, "CfRegisterSyncRoot", (unsigned int)v11);
    if ( v11 < 0 )
    {
      v13 = L"StructSize lesser than PlaceholderManagement";
      goto LABEL_6;
    }
  }
  v11 = *(_DWORD *)(a2 + 32) > 0x1000u ? 0x57 : 0;
  if ( *(_DWORD *)(a2 + 32) > 0x1000u )
    v11 = (*(_DWORD *)(a2 + 32) > 0x1000u ? 0x57 : 0) | 0x80070000;
  if ( v11 )
  {
    TlmChk(4096, 1519, "CfRegisterSyncRoot", (unsigned int)v11);
    if ( v11 < 0 )
    {
      v13 = L"SyncRootIdentityLength invalid";
      goto LABEL_6;
    }
  }
  v15 = *a3 < 0x14u;
  v16 = *(const wchar_t **)(a2 + 8);
  v7 = *(_QWORD *)(a2 + 16);
  v17 = *(void **)(a2 + 24);
  v18 = *(_DWORD *)(a2 + 32);
  v19 = a3[2];
  v146 = *(_QWORD *)(a2 + 40);
  v20 = *(_DWORD *)(a2 + 48);
  v21 = a3[1];
  Size_4 = v20;
  v136 = a3[3];
  String2 = (wchar_t *)v16;
  Source = (wchar_t *)v7;
  Src = v17;
  Size = v18;
  Buf2 = v21;
  v142 = v19;
  if ( v15 )
  {
    v23 = 0;
    v130 = 0;
    goto LABEL_56;
  }
  v130 = a3[4];
  if ( *a3 < 0x18u )
  {
    v130 = a3[4];
    v23 = 0;
LABEL_56:
    v134 = 0;
    goto LABEL_57;
  }
  v22 = a3[5];
  v23 = 0;
  v134 = v22;
LABEL_57:
  if ( (v21 & 0x20000) == 0 || (v11 = 87, (v21 & 0x10000) == 0) )
    v11 = 0;
  if ( v11 )
    v11 |= 0x80070000;
  if ( !v11 )
  {
    if ( v16 )
      v24 = wcsnlen(v16, 0xFFu);
    else
      v24 = 0;
    v25 = 2 * v24 + 2;
    cbInput = v25;
    if ( Source )
      v23 = wcsnlen(Source, 0xFFu);
    v11 = 0;
    if ( v25 <= 2 )
      v11 = 87;
    v26 = v11 | 0x80070000;
    if ( v25 <= 2 )
      v11 |= 0x80070000;
    if ( v11 )
    {
      TlmChk(v26, 1556, "CfRegisterSyncRoot", (unsigned int)v11);
      if ( v11 < 0 )
      {
        v13 = L"providerNameLength smaller than expected";
LABEL_76:
        v14 = 0;
LABEL_328:
        v7 = (__int64)Source;
        goto LABEL_329;
      }
    }
    v11 = v25 >= 0x1FE ? 0x57 : 0;
    if ( v25 >= 0x1FE )
      v11 = (v25 >= 0x1FE ? 0x57 : 0) | 0x80070000;
    if ( v11 )
    {
      TlmChk(510, 1559, "CfRegisterSyncRoot", (unsigned int)v11);
      if ( v11 < 0 )
      {
        v13 = L"providerNameLength larger than allowed";
        goto LABEL_76;
      }
    }
    v27 = 2 * v23 + 2;
    v11 = 0;
    if ( v27 <= 2 )
      v11 = -2147024809;
    if ( v11 )
    {
      TlmChk(2, 1563, "CfRegisterSyncRoot", (unsigned int)v11);
      v13 = L"providerVersionLength smaller than expected";
      goto LABEL_76;
    }
    v28 = 510;
    v11 = v27 >= 0x1FE ? 0x57 : 0;
    if ( v27 >= 0x1FE )
      v11 = (v27 >= 0x1FE ? 0x57 : 0) | 0x80070000;
    if ( v11 )
    {
      TlmChk(510, 1566, "CfRegisterSyncRoot", (unsigned int)v11);
      if ( v11 < 0 )
      {
        v13 = L"providerVersionLength larger than expected";
        goto LABEL_76;
      }
    }
    LOBYTE(v28) = 1;
    v11 = GlobalPortInit(v28);
    if ( v11 <= -1 )
    {
      v13 = L"GlobalPortInit Failed";
LABEL_93:
      v14 = 0;
      goto LABEL_328;
    }
    v11 = AttachFilterToVolume(v140);
    if ( v11 <= -1 )
    {
      v13 = L"AttachFilterToVolume Failed";
      goto LABEL_93;
    }
    File = CfpCreateFile(v140, v29, 0, 7);
    v11 = RtlNtStatusToDosError(File);
    v32 = v11 == 0;
    if ( v11 > 0 )
    {
      v11 = (unsigned __int16)v11 | 0x80070000;
      v32 = v11 == 0;
    }
    if ( !v32 )
    {
      TlmChk(v31, 1585, "CfRegisterSyncRoot", (unsigned int)v11);
      if ( v11 < 0 )
      {
        v13 = L"CfpCreateFile on SyncRootPath failed";
        goto LABEL_76;
      }
    }
    v33 = ((v27 + ((((v18 + 91) & 0xFFFFFFFC) + 3 + v25) & 0xFFFFFFFC) + 23) & 0xFFFFFFFC) + 16;
    v129 = v33;
    v11 = v33 > 0x10000 ? 0x57 : 0;
    if ( v33 > 0x10000 )
      v11 = (v33 > 0x10000 ? 0x57 : 0) | 0x80070000;
    if ( v11 )
    {
      TlmChk(0x10000, 1600, "CfRegisterSyncRoot", (unsigned int)v11);
      if ( v11 < 0 )
      {
        v13 = L"Invalid syncRootInfoLength";
LABEL_106:
        v14 = 0;
        goto LABEL_328;
      }
    }
    v143 = v33;
    ProcessHeap = GetProcessHeap();
    v8 = HeapAlloc(ProcessHeap, 8u, v33);
    v11 = v8 == 0 ? 8 : 0;
    if ( !v8 )
      v11 |= 0x80070000;
    if ( v11 )
    {
      TlmChk(v35, 1606, "CfRegisterSyncRoot", (unsigned int)v11);
      if ( v11 < 0 )
      {
        v13 = L"syncRootInfo allocation failed";
        goto LABEL_106;
      }
    }
    *(_QWORD *)v8 = 1850307155;
    v36 = v8 + 2;
    v8[3] = 589824;
    v8[2] = 88;
    memset_0(v8 + 4, 0, 0x48u);
    v37 = (char *)Src;
    v38 = -1073741789;
    if ( !Src )
      goto LABEL_127;
    if ( v129 < 0x18 )
      goto LABEL_114;
    if ( *((_WORD *)v8 + 7) )
    {
      v40 = *v36;
      v41 = (unsigned __int16)Size;
      if ( (unsigned __int16)Size + ((v40 + 3) & 0xFFFFFFFFFFFFFFFCuLL) > v143 )
      {
LABEL_114:
        v39 = -1073741789;
        goto LABEL_121;
      }
      v42 = ((_DWORD)v40 + 3) & 0xFFFFFFFC;
      *v36 = v42;
      v8[5] = v42;
      v43 = (char *)v8 + v42;
      *((_WORD *)v8 + 8) = 17;
      *((_WORD *)v8 + 9) = v41;
      if ( v43 != v37 )
        memcpy_0(v43, v37, v41);
      v39 = 0;
      *v36 += *((unsigned __int16 *)v8 + 9);
    }
    else
    {
      v39 = -1073741811;
    }
LABEL_121:
    v44 = RtlNtStatusToDosError(v39);
    v11 = v44;
    if ( v44 > 0 )
      v11 = (unsigned __int16)v44 | 0x80070000;
    if ( v11 )
    {
      TlmChk(v45, 1617, "CfRegisterSyncRoot", (unsigned int)v11);
      if ( v11 < 0 )
      {
        v13 = L"SetSyncRootIdentity Failed";
LABEL_126:
        v14 = 0;
        goto LABEL_328;
      }
    }
LABEL_127:
    if ( v129 < 0x18 )
    {
LABEL_128:
      v46 = -1073741789;
      goto LABEL_139;
    }
    if ( *((_WORD *)v8 + 7) > 1u )
    {
      if ( v129 < 0x20 )
        goto LABEL_128;
      v47 = *v36;
      if ( (unsigned __int16)cbInput + ((v47 + 3) & 0xFFFFFFFFFFFFFFFCuLL) > v143 )
        goto LABEL_128;
      if ( *((_WORD *)v8 + 12) )
        *((_WORD *)v8 + 6) |= 1u;
      v48 = (v47 + 3) & 0xFFFFFFFC;
      *v36 = v48;
      *((_WORD *)v8 + 12) = 17;
      *((_WORD *)v8 + 13) = cbInput;
      v8[7] = v48;
      if ( String2 )
      {
        v49 = (wchar_t *)((char *)v8 + v48);
        if ( v49 != String2 )
          memcpy_0(v49, String2, (unsigned __int16)cbInput);
      }
      v46 = 0;
      *v36 += *((unsigned __int16 *)v8 + 13);
    }
    else
    {
      v46 = -1073741811;
    }
LABEL_139:
    v50 = RtlNtStatusToDosError(v46);
    v11 = v50;
    if ( v50 > 0 )
      v11 = (unsigned __int16)v50 | 0x80070000;
    if ( v11 )
    {
      TlmChk(v51, 1625, "CfRegisterSyncRoot", (unsigned int)v11);
      if ( v11 < 0 )
      {
        v13 = L"SetSyncRootProviderName Failed";
        goto LABEL_126;
      }
    }
    if ( v129 < 0x18 )
      goto LABEL_145;
    if ( *((_WORD *)v8 + 7) > 2u )
    {
      if ( v129 < 0x28 || (v53 = *v36, (unsigned __int16)v27 + ((v53 + 3) & 0xFFFFFFFFFFFFFFFCuLL) > v143) )
      {
LABEL_145:
        v52 = -1073741789;
        goto LABEL_156;
      }
      if ( *((_WORD *)v8 + 16) )
        *((_WORD *)v8 + 6) |= 1u;
      v54 = (v53 + 3) & 0xFFFFFFFC;
      *v36 = v54;
      *((_WORD *)v8 + 16) = 17;
      *((_WORD *)v8 + 17) = v27;
      v8[9] = v54;
      if ( Source )
      {
        v55 = (wchar_t *)((char *)v8 + v54);
        if ( v55 != Source )
          memcpy_0(v55, Source, (unsigned __int16)v27);
      }
      v52 = 0;
      *v36 += *((unsigned __int16 *)v8 + 17);
    }
    else
    {
      v52 = -1073741811;
    }
LABEL_156:
    v56 = RtlNtStatusToDosError(v52);
    v11 = v56;
    if ( v56 > 0 )
      v11 = (unsigned __int16)v56 | 0x80070000;
    if ( v11 )
    {
      TlmChk(v57, 1632, "CfRegisterSyncRoot", (unsigned int)v11);
      if ( v11 < 0 )
      {
        v13 = L"SetSyncRootProviderVersion Failed";
LABEL_161:
        v14 = 0;
        goto LABEL_328;
      }
    }
    if ( v129 < 0x18 )
      goto LABEL_163;
    if ( *((_WORD *)v8 + 7) > 3u )
    {
      if ( v129 < 0x30 || (v59 = *v36, ((v59 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 4 > v129) )
      {
LABEL_163:
        v58 = -1073741789;
        goto LABEL_171;
      }
      v60 = ((_DWORD)v59 + 3) & 0xFFFFFFFC;
      *v36 = v60;
      if ( *((_WORD *)v8 + 20) )
        *((_WORD *)v8 + 6) |= 1u;
      v8[10] = 262154;
      v58 = 0;
      v8[11] = v60;
      *(_DWORD *)((char *)v8 + v60) = v21;
      *v36 += 4;
    }
    else
    {
      v58 = -1073741811;
    }
LABEL_171:
    v61 = RtlNtStatusToDosError(v58);
    v14 = 0;
    v11 = v61;
    if ( v61 > 0 )
      v11 = (unsigned __int16)v61 | 0x80070000;
    if ( v11 )
    {
      TlmChk(v62, 1638, "CfRegisterSyncRoot", (unsigned int)v11);
      if ( v11 < 0 )
      {
        v13 = L"SetSyncRootHydrationPolicy Failed";
        goto LABEL_328;
      }
    }
    if ( v129 < 0x18 )
      goto LABEL_177;
    if ( *((_WORD *)v8 + 7) > 4u )
    {
      if ( v129 < 0x38 || (v64 = *v36, ((v64 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 4 > v129) )
      {
LABEL_177:
        v63 = -1073741789;
        goto LABEL_185;
      }
      v65 = ((_DWORD)v64 + 3) & 0xFFFFFFFC;
      *v36 = v65;
      if ( *((_WORD *)v8 + 24) )
        *((_WORD *)v8 + 6) |= 1u;
      v8[12] = 262154;
      v63 = 0;
      v8[13] = v65;
      *(_DWORD *)((char *)v8 + v65) = v19;
      *v36 += 4;
    }
    else
    {
      v63 = -1073741811;
    }
LABEL_185:
    v66 = RtlNtStatusToDosError(v63);
    v11 = v66;
    if ( v66 > 0 )
      v11 = (unsigned __int16)v66 | 0x80070000;
    if ( v11 )
    {
      TlmChk(v67, 1644, "CfRegisterSyncRoot", (unsigned int)v11);
      if ( v11 < 0 )
      {
        v13 = L"SetSyncRootPopulationPolicy Failed";
        goto LABEL_328;
      }
    }
    if ( v129 < 0x18 )
      goto LABEL_191;
    if ( *((_WORD *)v8 + 7) > 5u )
    {
      if ( v129 < 0x40 || (v69 = *v36, ((v69 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 4 > v129) )
      {
LABEL_191:
        v68 = -1073741789;
        goto LABEL_199;
      }
      v70 = ((_DWORD)v69 + 3) & 0xFFFFFFFC;
      *v36 = v70;
      if ( *((_WORD *)v8 + 28) )
        *((_WORD *)v8 + 6) |= 1u;
      v71 = v136;
      v8[14] = 262154;
      v8[15] = v70;
      *(_DWORD *)((char *)v8 + v70) = v71;
      v68 = 0;
      *v36 += 4;
    }
    else
    {
      v68 = -1073741811;
    }
LABEL_199:
    v72 = RtlNtStatusToDosError(v68);
    v11 = v72;
    if ( v72 > 0 )
      v11 = (unsigned __int16)v72 | 0x80070000;
    if ( v11 )
    {
      TlmChk(v73, 1648, "CfRegisterSyncRoot", (unsigned int)v11);
      if ( v11 < 0 )
      {
        v13 = L"SetSyncRootInSyncPolicy Failed";
        goto LABEL_328;
      }
    }
    if ( v129 < 0x18 )
      goto LABEL_205;
    if ( *((_WORD *)v8 + 7) > 6u )
    {
      if ( v129 < 0x48 || (v75 = *v36, ((v75 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 4 > v129) )
      {
LABEL_205:
        v74 = -1073741789;
        goto LABEL_213;
      }
      v76 = ((_DWORD)v75 + 3) & 0xFFFFFFFC;
      *v36 = v76;
      if ( *((_WORD *)v8 + 32) )
        *((_WORD *)v8 + 6) |= 1u;
      v8[16] = 262154;
      v8[17] = v76;
      *(_DWORD *)((char *)v8 + v76) = v130;
      v74 = 0;
      *v36 += 4;
    }
    else
    {
      v74 = -1073741811;
    }
LABEL_213:
    v77 = RtlNtStatusToDosError(v74);
    v11 = v77;
    if ( v77 > 0 )
      v11 = (unsigned __int16)v77 | 0x80070000;
    if ( v11 )
    {
      TlmChk(v78, 1652, "CfRegisterSyncRoot", (unsigned int)v11);
      if ( v11 < 0 )
      {
        v13 = L"SetSyncRootHardLinkPolicy Failed";
        goto LABEL_328;
      }
    }
    v79 = *(_QWORD *)pbOutput;
    if ( **(_DWORD **)pbOutput >= 0x44u )
    {
      if ( v129 < 0x18 )
      {
LABEL_220:
        v80 = -1073741789;
        goto LABEL_228;
      }
      if ( *((_WORD *)v8 + 7) > 7u )
      {
        if ( v129 < 0x50 )
          goto LABEL_220;
        v81 = *v36;
        if ( ((v81 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 16 > v129 )
          goto LABEL_220;
        v82 = *(_OWORD *)(*(_QWORD *)pbOutput + 52LL);
        v83 = ((_DWORD)v81 + 3) & 0xFFFFFFFC;
        *v36 = v83;
        if ( *((_WORD *)v8 + 36) )
          *((_WORD *)v8 + 6) |= 1u;
        v8[18] = 1048592;
        v8[19] = v83;
        *(_OWORD *)((char *)v8 + v83) = v82;
        *v36 += 16;
        v80 = 0;
      }
      else
      {
        v80 = -1073741811;
      }
LABEL_228:
      v84 = RtlNtStatusToDosError(v80);
      v11 = v84;
      if ( v84 > 0 )
        v11 = (unsigned __int16)v84 | 0x80070000;
      if ( v11 )
      {
        TlmChk(v85, 1666, "CfRegisterSyncRoot", (unsigned int)v11);
        if ( v11 < 0 )
        {
          v13 = L"SetSyncRootProviderGuid Failed";
          goto LABEL_161;
        }
      }
LABEL_250:
      if ( v129 >= 0x18 )
      {
        if ( *((_WORD *)v8 + 7) > 8u )
        {
          if ( v129 >= 0x58 )
          {
            v94 = *v36;
            if ( ((v94 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 4 <= v129 )
            {
              v95 = ((_DWORD)v94 + 3) & 0xFFFFFFFC;
              *v36 = v95;
              if ( *((_WORD *)v8 + 40) )
                *((_WORD *)v8 + 6) |= 1u;
              v38 = 0;
              v8[20] = 262154;
              v8[21] = v95;
              *(_DWORD *)((char *)v8 + v95) = v134;
              *v36 += 4;
            }
          }
        }
        else
        {
          v38 = -1073741811;
        }
      }
      v96 = RtlNtStatusToDosError(v38);
      v11 = v96;
      if ( v96 > 0 )
        v11 = (unsigned __int16)v96 | 0x80070000;
      if ( v11 )
      {
        TlmChk(v97, 1689, "CfRegisterSyncRoot", (unsigned int)v11);
        if ( v11 < 0 )
        {
          v13 = L"SetSyncRootPlaceholderManagementPolicy failed.";
          v14 = 0;
          goto LABEL_328;
        }
      }
      v98 = *v36;
      *((_WORD *)v8 + 6) |= 2u;
      v8[1] = RtlComputeCrc32(0, (PUCHAR)v8 + 8, v98 - 8);
      if ( (unsigned __int16)v19 >= 3u || (a4 & 2) != 0 )
      {
        v99 = 65;
        v100 = 320;
      }
      else
      {
        v99 = 33;
        v100 = 288;
      }
      if ( (a4 & 4) != 0 )
        v100 = v99;
      v101 = *(_DWORD *)(v79 + 32) + 1056;
      v102 = GetProcessHeap();
      v103 = (const wchar_t *)HeapAlloc(v102, 0, v101);
      v127 = v103;
      v11 = v103 == 0 ? 8 : 0;
      if ( !v103 )
        v11 |= 0x80070000;
      if ( !v11 || (TlmChk(v103, 1725, "CfRegisterSyncRoot", (unsigned int)v11), v11 >= 0) )
      {
        SyncRootInfoByHandle = CfpGetSyncRootInfoByHandle(hObject, (__int64)&v135);
        v11 = SyncRootInfoByHandle;
        if ( SyncRootInfoByHandle == -2147024506 )
        {
          v7 = (__int64)Source;
          TlmInitializeFirstRunExpStatus(UnbiasedTime, String2, Source);
          LODWORD(v125) = Size_4;
          v106 = CfpRegisterSyncRoot(hObject, v8, v125, v100, 0);
          v11 = v106;
          if ( v106 && (TlmChk(v107, 1749, "CfRegisterSyncRoot", v106), v11 < 0) )
          {
            v13 = L"CfpRegisterSyncRoot Failed when folder not under syncroot";
          }
          else
          {
            v13 = 0;
            v150 = 1;
          }
          v14 = (wchar_t *)v127;
          goto LABEL_329;
        }
        if ( SyncRootInfoByHandle == -2147024662 )
        {
          v108 = 0;
        }
        else
        {
          if ( SyncRootInfoByHandle )
          {
            TlmChk(v105, 1767, "CfRegisterSyncRoot", SyncRootInfoByHandle);
            if ( v11 < 0 )
            {
              v13 = L"CfpGetSyncRootInfoByHandle Failed";
LABEL_327:
              v14 = (wchar_t *)v127;
              goto LABEL_328;
            }
          }
          v108 = v135;
        }
        if ( (a4 & 1) == 0 )
        {
          v11 = v108 != v101 ? 0x57 : 0;
          if ( v11 )
            v11 |= 0x80070000;
          if ( v11 )
          {
            TlmChk(v105, 1783, "CfRegisterSyncRoot", (unsigned int)v11);
            v13 = L"SyncRootStdInfoLength Mismatch";
            goto LABEL_327;
          }
          v14 = (wchar_t *)v127;
          v11 = memcmp_0(v127 + 4, &Buf2, 4u) != 0 ? 0x57 : 0;
          if ( v11 )
            v11 |= 0x80070000;
          if ( v11 )
          {
            TlmChk(v109, 1788, "CfRegisterSyncRoot", (unsigned int)v11);
            v13 = L"HydrationPolicy Mismatch";
            goto LABEL_328;
          }
          v11 = memcmp_0(v127 + 6, &v142, 4u) != 0 ? 0x57 : 0;
          if ( v11 )
            v11 |= 0x80070000;
          if ( v11 )
          {
            TlmChk(v110, 1793, "CfRegisterSyncRoot", (unsigned int)v11);
LABEL_298:
            v13 = L"PopulationPolicy Mismatch";
            goto LABEL_328;
          }
          v111 = v127;
          v11 = v136 != *((_DWORD *)v127 + 4) ? 0x57 : 0;
          if ( *((_DWORD *)v127 + 4) != v136 )
            v11 = (v136 != *((_DWORD *)v127 + 4) ? 0x57 : 0) | 0x80070000;
          if ( v11 )
          {
            TlmChk(v127, 1796, "CfRegisterSyncRoot", (unsigned int)v11);
            if ( v11 < 0 )
              goto LABEL_298;
            v111 = v127;
          }
          v112 = wcsncmp_0(v111 + 14, String2, 0xFFu);
          v11 = v112 != 0 ? 0x57 : 0;
          v113 = v11 | 0x80070000;
          if ( v112 )
            v11 |= 0x80070000;
          if ( !v11 || (TlmChk(v113, 1801, "CfRegisterSyncRoot", (unsigned int)v11), v11 >= 0) )
          {
            v7 = (__int64)Source;
            v114 = wcsncmp_0(v127 + 270, Source, 0xFFu);
            v11 = v114 != 0 ? 0x57 : 0;
            v115 = v11 | 0x80070000;
            if ( v114 )
              v11 |= 0x80070000;
            if ( v11 && (TlmChk(v115, 1806, "CfRegisterSyncRoot", (unsigned int)v11), v11 < 0) )
            {
              v13 = L"ProviderVersion Mismatch";
            }
            else
            {
              v116 = *((unsigned int *)v127 + 263);
              v117 = Size;
              v11 = Size != *((_DWORD *)v127 + 263) ? 0x57 : 0;
              if ( (_DWORD)v116 != Size )
                v11 = (Size != *((_DWORD *)v127 + 263) ? 0x57 : 0) | 0x80070000;
              if ( v11 && (TlmChk(v116, 1810, "CfRegisterSyncRoot", (unsigned int)v11), v11 < 0) )
              {
                v13 = L"SyncRootIdentityLength Mismatch";
              }
              else
              {
                v11 = memcmp_0(v127 + 528, Src, v117) != 0 ? 0x57 : 0;
                if ( v11 )
                  v11 |= 0x80070000;
                if ( v11 )
                {
                  TlmChk(v118, 1815, "CfRegisterSyncRoot", (unsigned int)v11);
                  v13 = L"SyncRootIdentity Mismatch";
                }
                else
                {
                  v13 = 0;
                }
              }
            }
            goto LABEL_329;
          }
          v13 = L"ProviderName Mismatch";
          goto LABEL_328;
        }
        LODWORD(v125) = Size_4;
        v119 = CfpRegisterSyncRoot(hObject, v8, v125, v100, 1);
        v11 = v119;
        if ( v119 )
        {
          TlmChk(v120, 1829, "CfRegisterSyncRoot", v119);
          v13 = L"CfpRegisterSyncRoot (Update) Failed";
          if ( v11 < 0 )
            goto LABEL_327;
        }
      }
      v13 = 0;
      goto LABEL_327;
    }
    *(_OWORD *)pbOutput = 0;
    Guid = CfpMakeGuid((PUCHAR)String2, cbInput, pbOutput);
    v11 = Guid;
    if ( Guid )
    {
      TlmChk(v87, 1678, "CfRegisterSyncRoot", Guid);
      if ( v11 < 0 )
      {
        v13 = L"CfpMakeGuid Failed";
        goto LABEL_126;
      }
    }
    if ( v129 < 0x18 )
      goto LABEL_237;
    if ( *((_WORD *)v8 + 7) > 7u )
    {
      if ( v129 < 0x50 || (v89 = *v36, ((v89 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 16 > v129) )
      {
LABEL_237:
        v88 = -1073741789;
        goto LABEL_245;
      }
      v90 = *(_OWORD *)pbOutput;
      v91 = ((_DWORD)v89 + 3) & 0xFFFFFFFC;
      *v36 = v91;
      if ( *((_WORD *)v8 + 36) )
        *((_WORD *)v8 + 6) |= 1u;
      v8[18] = 1048592;
      v8[19] = v91;
      *(_OWORD *)((char *)v8 + v91) = v90;
      *v36 += 16;
      v88 = 0;
    }
    else
    {
      v88 = -1073741811;
    }
LABEL_245:
    v92 = RtlNtStatusToDosError(v88);
    v11 = v92;
    if ( v92 > 0 )
      v11 = (unsigned __int16)v92 | 0x80070000;
    if ( v11 )
    {
      TlmChk(v93, 1682, "CfRegisterSyncRoot", (unsigned int)v11);
      if ( v11 < 0 )
      {
        v13 = L"SetSyncRootProviderGuid after CfpMakeGuid failed";
        goto LABEL_161;
      }
    }
    goto LABEL_250;
  }
  TlmChk(2, 1545, "CfRegisterSyncRoot", (unsigned int)v11);
  v13 = L"hydrationPolicy varification failed";
  v14 = 0;
LABEL_329:
  v10 = v126;
LABEL_330:
  v148 = v13;
  v149 = a4;
  TlmLogApiReliability(9, 0, v140, (_DWORD)String2, v7, UnbiasedTime, (__int64)v147, v11);
  if ( v14 )
  {
    v121 = GetProcessHeap();
    HeapFree(v121, 0, v14);
  }
  v122 = hObject;
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  if ( v8 )
  {
    v123 = GetProcessHeap();
    HeapFree(v123, 0, v8);
  }
  LOBYTE(v122) = v10;
  RtlSetThreadPlaceholderCompatibilityMode(v122);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180006060  push    rbp
0x180006062  push    rbx
0x180006063  push    rsi
0x180006064  push    rdi
0x180006065  push    r12
0x180006067  push    r13
0x180006069  push    r14
0x18000606b  push    r15
0x18000606d  lea     rbp, [rsp-58h]
0x180006072  sub     rsp, 158h
0x180006079  mov     rax, cs:__security_cookie
0x180006080  xor     rax, rsp
0x180006083  mov     [rbp+90h+var_50], rax
0x180006087  xor     r13d, r13d
0x18000608a  mov     qword ptr [rbp+90h+pbOutput], rdx
0x18000608e  mov     r14, r8
0x180006091  mov     [rbp+90h+var_F0], rcx
0x180006095  mov     rbx, rdx
0x180006098  mov     [rsp+190h+var_120], r9d
0x18000609d  mov     rsi, rcx
0x1800060a0  mov     [rbp+90h+hObject], 0FFFFFFFFFFFFFFFFh
0x1800060a8  lea     r8d, [r13+58h]; Size
0x1800060ac  mov     [rsp+190h+String2], r13
0x1800060b1  xor     edx, edx; Val
0x1800060b3  mov     dword ptr [rbp+90h+var_108], r13d
0x1800060b7  lea     rcx, [rbp+90h+var_C0]; void *
0x1800060bb  mov     [rbp+90h+UnbiasedTime], r13
0x1800060bf  mov     r12d, r13d
0x1800060c2  mov     r15d, r13d
0x1800060c5  call    memset_0
0x1800060ca  mov     cl, 2
0x1800060cc  call    cs:__imp_RtlSetThreadPlaceholderCompatibilityMode
0x1800060d2  lea     rcx, [rbp+90h+UnbiasedTime]; UnbiasedTime
0x1800060d6  mov     [rsp+190h+var_140], al
0x1800060da  mov     dil, al
0x1800060dd  call    cs:__imp_QueryUnbiasedInterruptTime
0x1800060e3  mov     rcx, rsi
0x1800060e6  lea     edx, [r13+57h]
0x1800060ea  neg     rcx
0x1800060ed  sbb     esi, esi
0x1800060ef  not     esi
0x1800060f1  and     esi, edx
0x1800060f3  mov     ecx, esi
0x1800060f5  or      ecx, 80070000h
0x1800060fb  cmp     [rbp+90h+var_F0], r13
0x1800060ff  cmovz   esi, ecx
0x180006102  test    esi, esi
0x180006104  jz      short loc_180006132
0x180006106  mov     r9d, esi
0x180006109  lea     r8, aCfregistersync_0; "CfRegisterSyncRoot"
0x180006110  mov     edx, 5DAh
0x180006115  call    TlmChk
0x18000611a  test    esi, esi
0x18000611c  jns     short loc_18000612D
0x18000611e  lea     rax, aSyncrootpathIs; "SyncRootPath is NULL"
0x180006125  mov     rbx, r13
0x180006128  jmp     loc_180007301
0x18000612d  mov     edx, 57h ; 'W'
0x180006132  mov     rax, rbx
0x180006135  neg     rax
0x180006138  sbb     esi, esi
0x18000613a  not     esi
0x18000613c  and     esi, edx
0x18000613e  mov     eax, esi
0x180006140  or      eax, 80070000h
0x180006145  test    rbx, rbx
0x180006148  cmovz   esi, eax
0x18000614b  test    esi, esi
0x18000614d  jz      short loc_180006175
0x18000614f  mov     r9d, esi
0x180006152  lea     r8, aCfregistersync_0; "CfRegisterSyncRoot"
0x180006159  mov     edx, 5DBh
0x18000615e  call    TlmChk
0x180006163  test    esi, esi
0x180006165  jns     short loc_180006170
0x180006167  lea     rax, aRegistrationIs; "Registration is NULL"
0x18000616e  jmp     short loc_180006125
0x180006170  mov     edx, 57h ; 'W'
0x180006175  mov     rax, [rbx+8]
0x180006179  neg     rax
0x18000617c  sbb     esi, esi
0x18000617e  not     esi
0x180006180  and     esi, edx
0x180006182  mov     eax, esi
0x180006184  or      eax, 80070000h
0x180006189  cmp     [rbx+8], r13
0x18000618d  cmovz   esi, eax
0x180006190  test    esi, esi
0x180006192  jz      short loc_1800061BD
0x180006194  mov     r9d, esi
0x180006197  lea     r8, aCfregistersync_0; "CfRegisterSyncRoot"
0x18000619e  mov     edx, 5DCh
0x1800061a3  call    TlmChk
0x1800061a8  test    esi, esi
0x1800061aa  jns     short loc_1800061B8
0x1800061ac  lea     rax, aProvidernameIs; "ProviderName is NULL"
0x1800061b3  jmp     loc_180006125
0x1800061b8  mov     edx, 57h ; 'W'
0x1800061bd  mov     rax, [rbx+10h]
0x1800061c1  neg     rax
0x1800061c4  sbb     esi, esi
0x1800061c6  not     esi
0x1800061c8  and     esi, edx
0x1800061ca  mov     eax, esi
0x1800061cc  or      eax, 80070000h
0x1800061d1  cmp     [rbx+10h], r13
0x1800061d5  cmovz   esi, eax
0x1800061d8  test    esi, esi
0x1800061da  jz      short loc_180006205
0x1800061dc  mov     r9d, esi
0x1800061df  lea     r8, aCfregistersync_0; "CfRegisterSyncRoot"
0x1800061e6  mov     edx, 5DDh
0x1800061eb  call    TlmChk
0x1800061f0  test    esi, esi
0x1800061f2  jns     short loc_180006200
0x1800061f4  lea     rax, aProviderversio; "ProviderVersion is NULL"
0x1800061fb  jmp     loc_180006125
0x180006200  mov     edx, 57h ; 'W'
0x180006205  cmp     [rbx+18h], r13
0x180006209  jz      short loc_180006213
0x18000620b  mov     esi, edx
0x18000620d  cmp     [rbx+20h], r13d
0x180006211  jz      short loc_180006216
0x180006213  mov     esi, r13d
0x180006216  mov     eax, esi
0x180006218  or      eax, 80070000h
0x18000621d  test    esi, esi
0x18000621f  cmovnz  esi, eax
0x180006222  test    esi, esi
0x180006224  jz      short loc_18000624A
0x180006226  mov     r9d, esi
0x180006229  lea     r8, aCfregistersync_0; "CfRegisterSyncRoot"
0x180006230  mov     edx, 5E1h
0x180006235  call    TlmChk
0x18000623a  test    esi, esi
0x18000623c  jns     short loc_18000624A
0x18000623e  lea     rax, aInvalidSyncroo; "Invalid SyncRootIdentity"
0x180006245  jmp     loc_180006125
0x18000624a  cmp     [rbx+28h], r13
0x18000624e  jz      short loc_18000625B
0x180006250  mov     esi, 57h ; 'W'
0x180006255  cmp     [rbx+30h], r13d
0x180006259  jz      short loc_18000625E
0x18000625b  mov     esi, r13d
0x18000625e  mov     eax, esi
0x180006260  or      eax, 80070000h
0x180006265  test    esi, esi
0x180006267  cmovnz  esi, eax
0x18000626a  test    esi, esi
0x18000626c  jz      short loc_180006292
0x18000626e  mov     r9d, esi
0x180006271  lea     r8, aCfregistersync_0; "CfRegisterSyncRoot"
0x180006278  mov     edx, 5E5h
0x18000627d  call    TlmChk
0x180006282  test    esi, esi
0x180006284  jns     short loc_180006292
0x180006286  lea     rax, aInvalidFileide; "Invalid FileIdentity"
0x18000628d  jmp     loc_180006125
0x180006292  mov     rax, r14
0x180006295  neg     rax
0x180006298  sbb     esi, esi
0x18000629a  not     esi
0x18000629c  and     esi, 57h
0x18000629f  mov     eax, esi
0x1800062a1  or      eax, 80070000h
0x1800062a6  test    r14, r14
0x1800062a9  cmovz   esi, eax
0x1800062ac  test    esi, esi
0x1800062ae  jz      short loc_1800062D4
0x1800062b0  mov     r9d, esi
0x1800062b3  lea     r8, aCfregistersync_0; "CfRegisterSyncRoot"
0x1800062ba  mov     edx, 5E7h
0x1800062bf  call    TlmChk
0x1800062c4  test    esi, esi
0x1800062c6  jns     short loc_1800062D4
0x1800062c8  lea     rax, aPoliciesCanTBe; "Policies can't be NULL"
0x1800062cf  jmp     loc_180006125
0x1800062d4  cmp     dword ptr [r14], 14h
0x1800062d8  sbb     esi, esi
0x1800062da  and     esi, 57h
0x1800062dd  mov     eax, esi
0x1800062df  or      eax, 80070000h
0x1800062e4  cmp     dword ptr [r14], 14h
0x1800062e8  cmovb   esi, eax
0x1800062eb  test    esi, esi
0x1800062ed  jz      short loc_180006313
0x1800062ef  mov     r9d, esi
0x1800062f2  lea     r8, aCfregistersync_0; "CfRegisterSyncRoot"
0x1800062f9  mov     edx, 5EBh
0x1800062fe  call    TlmChk
0x180006303  test    esi, esi
0x180006305  jns     short loc_180006313
0x180006307  lea     rax, aStructsizeLess; "StructSize lesser than PlaceholderManag"...
0x18000630e  jmp     loc_180006125
0x180006313  mov     ecx, 1000h
0x180006318  cmp     ecx, [rbx+20h]
0x18000631b  sbb     esi, esi
0x18000631d  and     esi, 57h
0x180006320  mov     eax, esi
0x180006322  or      eax, 80070000h
0x180006327  cmp     [rbx+20h], ecx
0x18000632a  cmova   esi, eax
0x18000632d  test    esi, esi
0x18000632f  jz      short loc_180006355
0x180006331  mov     r9d, esi
0x180006334  lea     r8, aCfregistersync_0; "CfRegisterSyncRoot"
0x18000633b  mov     edx, 5EFh
0x180006340  call    TlmChk
0x180006345  test    esi, esi
0x180006347  jns     short loc_180006355
0x180006349  lea     rax, aSyncrootidenti_1; "SyncRootIdentityLength invalid"
0x180006350  jmp     loc_180006125
0x180006355  cmp     dword ptr [r14], 14h
0x180006359  mov     rax, [rbx+28h]
0x18000635d  mov     r8, [rbx+8]
0x180006361  mov     r12, [rbx+10h]
0x180006365  mov     rdx, [rbx+18h]
0x180006369  mov     r13d, [rbx+20h]
0x18000636d  mov     edi, [r14+8]
0x180006371  mov     [rbp+90h+var_C8], rax
0x180006375  mov     eax, [rbx+30h]
0x180006378  mov     ebx, [r14+4]
0x18000637c  mov     dword ptr [rbp+90h+Size+4], eax
0x18000637f  mov     eax, [r14+0Ch]
0x180006383  mov     dword ptr [rbp+90h+var_108+4], eax
0x180006386  mov     [rsp+190h+String2], r8
0x18000638b  mov     [rsp+190h+Source], r12
0x180006390  mov     [rbp+90h+Src], rdx
0x180006394  mov     dword ptr [rbp+90h+Size], r13d
0x180006398  mov     [rbp+90h+Buf2], ebx
0x18000639b  mov     [rbp+90h+var_E4], edi
0x18000639e  jb      short loc_1800063C3
0x1800063a0  cmp     dword ptr [r14], 18h
0x1800063a4  mov     eax, [r14+10h]
0x1800063a8  mov     [rsp+190h+var_124], eax
0x1800063ac  jb      short loc_1800063BA
0x1800063ae  mov     ecx, [r14+14h]
0x1800063b2  xor     r14d, r14d
0x1800063b5  mov     [rbp+90h+var_10C], ecx
0x1800063b8  jmp     short loc_1800063CF
0x1800063ba  mov     [rsp+190h+var_124], eax
0x1800063be  xor     r14d, r14d
0x1800063c1  jmp     short loc_1800063CB
0x1800063c3  xor     r14d, r14d
0x1800063c6  mov     [rsp+190h+var_124], r14d
0x1800063cb  mov     [rbp+90h+var_10C], r14d
0x1800063cf  mov     eax, ebx
0x1800063d1  mov     ecx, 2
0x1800063d6  shr     eax, 10h
0x1800063d9  test    cl, al
0x1800063db  jz      short loc_1800063E4
0x1800063dd  lea     esi, [rcx+55h]
0x1800063e0  test    al, 1
0x1800063e2  jnz     short loc_1800063E7
0x1800063e4  mov     esi, r14d
0x1800063e7  mov     eax, esi
0x1800063e9  or      eax, 80070000h
0x1800063ee  test    esi, esi
0x1800063f0  cmovnz  esi, eax
0x1800063f3  test    esi, esi
0x1800063f5  jz      short loc_180006423
0x1800063f7  mov     r9d, esi
0x1800063fa  lea     r8, aCfregistersync_0; "CfRegisterSyncRoot"
0x180006401  mov     edx, 609h
0x180006406  call    TlmChk
0x18000640b  test    esi, esi
0x18000640d  jns     short loc_18000641E
0x18000640f  lea     rax, aHydrationpolic; "hydrationPolicy varification failed"
0x180006416  mov     rbx, r15
0x180006419  jmp     loc_1800072FC
0x18000641e  mov     r8, [rsp+190h+String2]
0x180006423  test    r8, r8
0x180006426  jnz     short loc_18000642D
0x180006428  mov     rax, r14
0x18000642b  jmp     short loc_18000643B
0x18000642d  mov     edx, 0FFh; MaxCount
0x180006432  mov     rcx, r8; Source
0x180006435  call    cs:__imp_wcsnlen
0x18000643b  lea     r12d, ds:2[rax*2]
0x180006443  mov     rax, [rsp+190h+Source]
0x180006448  mov     [rbp+90h+cbInput], r12d
0x18000644c  test    rax, rax
0x18000644f  jz      short loc_180006462
0x180006451  mov     edx, 0FFh; MaxCount
0x180006456  mov     rcx, rax; Source
0x180006459  call    cs:__imp_wcsnlen
0x18000645f  mov     r14, rax
0x180006462  xor     edx, edx
0x180006464  mov     esi, edx
0x180006466  lea     r8d, [rdx+2]
0x18000646a  cmp     r12d, r8d
0x18000646d  lea     eax, [rdx+57h]
0x180006470  cmovbe  esi, eax
0x180006473  mov     ecx, esi
0x180006475  or      ecx, 80070000h
0x18000647b  cmp     r12d, r8d
0x18000647e  cmovbe  esi, ecx
0x180006481  test    esi, esi
0x180006483  jz      short loc_1800064B3
0x180006485  mov     r9d, esi
  ... truncated ...
```
