# BipPackageImportanceUpdateScoreForPackage

- ea: `0x180023bf0`
- end: `0x180024239`
- name: `BipPackageImportanceUpdateScoreForPackage`
- size: `1609`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180024610`
- `0x180024ecc`
- `0x1800617d0`

## callees

- `0x180006ef0`
- `0x180023bf0`
- `0x1800250d0`
- `0x1800251f8`
- `0x18002b320`
- `0x18002d9a0`
- `0x18002e210`
- `0x180051dfc`
- `0x180051fa0`
- `0x18009467a`
- `0x1800946a0`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180023c95`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180023c95`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180024207`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180024207`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800241a6`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800241a6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180023ceb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180023ee5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180023ceb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180023ee5`
- `api-ms-win-appmodel-runtime-l1-1-1!GetStagedPackageOrigin` at `0x180023e53`
- `api-ms-win-appmodel-runtime-l1-1-1!GetStagedPackageOrigin` at `0x180023e53`

## pseudocode

```c
__int64 __fastcall BipPackageImportanceUpdateScoreForPackage(__int64 a1, __int64 a2)
{
  unsigned int v2; // r15d
  __int64 *v3; // rbx
  unsigned int v4; // r12d
  __int64 v5; // r14
  __int64 v8; // rdi
  HRESULT v9; // edi
  void **v10; // r12
  __int64 v11; // rcx
  __int64 v12; // rdi
  __int64 v13; // xmm1_8
  unsigned __int8 v14; // al
  __int64 BudgetForPackage; // rax
  int v16; // edx
  __int64 v17; // rdx
  char IsPackageInImportantAppsTable; // al
  char v19; // al
  bool v20; // zf
  char v21; // di
  int v22; // eax
  unsigned __int8 v23; // r12
  __int64 v24; // rax
  unsigned __int64 v25; // rcx
  int v26; // r14d
  __int64 v27; // rbx
  char v29; // [rsp+30h] [rbp-D0h]
  PackageOrigin origin; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v31; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v32; // [rsp+40h] [rbp-C0h] BYREF
  int v33; // [rsp+48h] [rbp-B8h] BYREF
  int v34; // [rsp+4Ch] [rbp-B4h] BYREF
  int v35; // [rsp+50h] [rbp-B0h] BYREF
  int v36; // [rsp+54h] [rbp-ACh] BYREF
  int v37; // [rsp+58h] [rbp-A8h] BYREF
  int v38; // [rsp+5Ch] [rbp-A4h] BYREF
  PackageOrigin v39; // [rsp+60h] [rbp-A0h] BYREF
  int v40; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v41; // [rsp+68h] [rbp-98h]
  struct _FILETIME v42; // [rsp+70h] [rbp-90h] BYREF
  __int128 v43; // [rsp+78h] [rbp-88h] BYREF
  __int64 v44; // [rsp+88h] [rbp-78h]
  unsigned __int64 v45; // [rsp+90h] [rbp-70h] BYREF
  __int64 v46; // [rsp+98h] [rbp-68h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v48[424]; // [rsp+B0h] [rbp-50h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+258h] [rbp+158h] BYREF
  unsigned __int8 v50; // [rsp+284h] [rbp+184h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+290h] [rbp+190h] BYREF
  char *v52; // [rsp+2A0h] [rbp+1A0h]
  int v53; // [rsp+2A8h] [rbp+1A8h]
  int v54; // [rsp+2ACh] [rbp+1ACh]
  __int64 *v55; // [rsp+2B0h] [rbp+1B0h]
  int v56; // [rsp+2B8h] [rbp+1B8h]
  int v57; // [rsp+2BCh] [rbp+1BCh]
  unsigned int *v58; // [rsp+2C0h] [rbp+1C0h]
  __int64 v59; // [rsp+2C8h] [rbp+1C8h]
  int *v60; // [rsp+2D0h] [rbp+1D0h]
  __int64 v61; // [rsp+2D8h] [rbp+1D8h]
  int *v62; // [rsp+2E0h] [rbp+1E0h]
  __int64 v63; // [rsp+2E8h] [rbp+1E8h]
  int *v64; // [rsp+2F0h] [rbp+1F0h]
  __int64 v65; // [rsp+2F8h] [rbp+1F8h]
  int *v66; // [rsp+300h] [rbp+200h]
  __int64 v67; // [rsp+308h] [rbp+208h]
  int *v68; // [rsp+310h] [rbp+210h]
  __int64 v69; // [rsp+318h] [rbp+218h]
  unsigned __int64 *v70; // [rsp+320h] [rbp+220h]
  __int64 v71; // [rsp+328h] [rbp+228h]
  int *v72; // [rsp+330h] [rbp+230h]
  __int64 v73; // [rsp+338h] [rbp+238h]
  PackageOrigin *v74; // [rsp+340h] [rbp+240h]
  __int64 v75; // [rsp+348h] [rbp+248h]
  int *v76; // [rsp+350h] [rbp+250h]
  __int64 v77; // [rsp+358h] [rbp+258h]
  __int64 *v78; // [rsp+360h] [rbp+260h]
  __int64 v79; // [rsp+368h] [rbp+268h]

  v2 = *(_DWORD *)(a2 + 464);
  v3 = (__int64 *)(a2 + 16);
  v31 = v2;
  v4 = 0;
  v42 = 0;
  v41 = 0;
  v5 = -1;
  v44 = 0;
  origin = PackageOrigin_Unknown;
  v29 = 0;
  v43 = 0;
  v8 = -1;
  do
    ++v8;
  while ( *((_WORD *)v3 + v8) );
  v32 = 0;
  memset_0(v48, 0, 0x1D8u);
  if ( !v8 )
  {
    v9 = -2147024809;
    goto LABEL_49;
  }
  v9 = CoInitializeEx(0, 0);
  if ( v9 < 0 )
    goto LABEL_49;
  v10 = (void **)(a2 + 408);
  v29 = 1;
  if ( *(_QWORD *)(a2 + 424) )
  {
    SystemTimeAsFileTime = *(struct _FILETIME *)(a2 + 424);
  }
  else if ( (int)BipGetPackageImportanceInfoFromStore(v3, *v10, &SystemTimeAsFileTime, a2 + 432) < 0 )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    *(_BYTE *)(a2 + 468) |= 0x20u;
  }
  if ( (int)BipEnergyBudgetGetOrCreatePerSessionInfo(a1, *(unsigned int *)(a2 + 416), &v32) >= 0 )
  {
    v12 = v32;
    if ( v32 )
    {
      if ( !*(_QWORD *)(v32 + 32) )
      {
        if ( (int)BipSystemBackgroundAccessContextAllocateState(&v43, *(unsigned int *)(a2 + 416)) < 0 )
        {
          v41 = v44;
          goto LABEL_19;
        }
        v13 = v44;
        *(_OWORD *)(v12 + 32) = v43;
        v41 = 0;
        *(_QWORD *)(v12 + 48) = v13;
        v43 = 0;
      }
      if ( (int)BipSystemBackgroundAccessQueryPackageState(*(__int64 **)(v12 + 32), *v10, v3, &v31) < 0 )
      {
        v2 = -2;
        goto LABEL_31;
      }
      v2 = v31;
LABEL_19:
      if ( v2 > 0xFFFFFFFD )
      {
LABEL_31:
        v17 = *(_QWORD *)(v12 + 56);
        if ( v17 )
        {
          IsPackageInImportantAppsTable = BipEnergyBudgetIsPackageInImportantAppsTable(v11, v17, v3);
          v11 = v50;
          LOBYTE(v11) = v50 & 0xFB;
          v50 = v50 & 0xFB | (4 * (IsPackageInImportantAppsTable & 1));
        }
        goto LABEL_33;
      }
      v14 = v50;
      if ( (v2 & 2) != 0 )
      {
        v14 = v50 & 0xFC | 1;
      }
      else
      {
        if ( (v2 & 0x20) == 0 )
        {
LABEL_25:
          if ( (v14 & 1) == 0 && (*(_BYTE *)(a2 + 468) & 1) != 0 )
          {
            BudgetForPackage = BipEnergyBudgetGetBudgetForPackage(a1, v3, 0);
            if ( BudgetForPackage )
            {
              v16 = *(_DWORD *)(BudgetForPackage + 304);
              v11 = 0;
              if ( v16 <= 0 )
                v16 = 0;
              *(_DWORD *)(BudgetForPackage + 304) = v16;
            }
          }
          goto LABEL_31;
        }
        v14 = v50 & 0xFC | 2;
      }
      v50 = v14;
      goto LABEL_25;
    }
  }
LABEL_33:
  v19 = BipEnergyBudgetIsPackageInImportantAppsTable(v11, *(_QWORD *)(a1 + 152), v3);
  origin = PackageOrigin_Unknown;
  v20 = (*(_BYTE *)(a1 + 178) & 0x20) == 0;
  v50 = v50 & 0xEF | (16 * (v19 & 1));
  if ( !v20 && !GetStagedPackageOrigin((PCWSTR)v3, &origin) && (unsigned int)(origin - 4) <= 2 )
    v50 |= 0x10u;
  v21 = (unsigned int)BipPackageImportanceScoreFromInputs(a1, a2) != 0;
  v22 = BipPackageImportanceScoreFromInputs(a1, v48);
  *(_DWORD *)(a2 + 464) = v2;
  *(struct _FILETIME *)(a2 + 424) = SystemTimeAsFileTime;
  v23 = v22 != 0;
  *(_BYTE *)(a2 + 468) = v50 | 0x80;
  v24 = BipEnergyBudgetGetBudgetForPackage(a1, v3, 0);
  if ( v24 )
    BipEnergyBudgetCacheImportanceScoreForBudget(a1, v24);
  if ( v23 != v21 )
  {
    GetSystemTimeAsFileTime(&v42);
    v25 = *(_QWORD *)&v42 - *(_QWORD *)(a2 + 424);
    if ( (unsigned int)dword_1800C3098 > 4
      && (qword_1800C30A8 & 0x200000000003LL) != 0
      && (qword_1800C30B0 & 0x200000000003LL) == qword_1800C30B0 )
    {
      if ( v3 )
      {
        do
          v20 = *((_WORD *)v3 + ++v5) == 0;
        while ( !v20 );
        v26 = 2 * v5 + 2;
      }
      else
      {
        v3 = &qword_1800A1670;
        v26 = 2;
      }
      v31 = v23;
      v58 = &v31;
      v55 = v3;
      v33 = v50 & 1;
      v60 = &v33;
      v56 = v26;
      v34 = (v50 >> 1) & 1;
      v62 = &v34;
      v57 = 0;
      v35 = (v50 >> 2) & 1;
      v64 = &v35;
      v36 = (v50 >> 3) & 1;
      v37 = (v50 >> 4) & 1;
      v66 = &v36;
      v59 = 4;
      v68 = &v37;
      v70 = &v45;
      v38 = *(unsigned __int16 *)(a1 + 38);
      v72 = &v38;
      v39 = origin;
      v74 = &v39;
      v40 = *(_DWORD *)(a2 + 464);
      v76 = &v40;
      v78 = &v46;
      *(_DWORD *)&EventDescriptor.Level = 4;
      UserData.Ptr = (ULONGLONG)off_1800C30A0;
      v61 = 4;
      v63 = 4;
      v65 = 4;
      v67 = 4;
      v69 = 4;
      v45 = v25 / 0x2710 / 0x5265C00;
      v71 = 8;
      v73 = 4;
      v75 = 4;
      v77 = 4;
      v46 = 0x1000000;
      v79 = 8;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0x200000000003LL;
      UserData.Size = *(unsigned __int16 *)off_1800C30A0;
      v52 = byte_1800B1473;
      UserData.Reserved = 2;
      v53 = 261;
      v54 = 1;
      LODWORD(v32) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 0xEu, &UserData);
    }
  }
  v4 = v41;
  v9 = 0;
LABEL_49:
  v27 = v43;
  if ( v4 && (_QWORD)v43 )
    (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v43 + 160LL))(v43, v4);
  if ( *((_QWORD *)&v43 + 1) )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v43 + 1) + 16LL))(*((_QWORD *)&v43 + 1));
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  if ( v29 )
    CoUninitialize();
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180023bf0  mov     [rsp-8+arg_10], rbx
0x180023bf5  push    rbp
0x180023bf6  push    rsi
0x180023bf7  push    rdi
0x180023bf8  push    r12
0x180023bfa  push    r13
0x180023bfc  push    r14
0x180023bfe  push    r15
0x180023c00  lea     rbp, [rsp-280h]
0x180023c08  sub     rsp, 380h
0x180023c0f  mov     rax, cs:__security_cookie
0x180023c16  xor     rax, rsp
0x180023c19  mov     [rbp+2B0h+var_40], rax
0x180023c20  mov     r15d, [rdx+1D0h]
0x180023c27  lea     rbx, [rdx+10h]
0x180023c2b  xor     eax, eax
0x180023c2d  mov     [rsp+3B0h+var_378], r15d
0x180023c32  xor     r12d, r12d
0x180023c35  mov     qword ptr [rsp+3B0h+var_340.dwLowDateTime], rax
0x180023c3a  xorps   xmm0, xmm0
0x180023c3d  mov     [rsp+3B0h+var_348], r12
0x180023c42  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180023c49  mov     [rbp+2B0h+var_328], r12
0x180023c4d  mov     rsi, rdx
0x180023c50  mov     [rsp+3B0h+origin], eax
0x180023c54  mov     r13, rcx
0x180023c57  mov     [rsp+3B0h+var_380], al
0x180023c5b  movups  [rsp+3B0h+var_338], xmm0
0x180023c60  mov     rdi, r14
0x180023c63  inc     rdi
0x180023c66  cmp     [rbx+rdi*2], ax
0x180023c6a  jnz     short loc_180023C63
0x180023c6c  xor     edx, edx; Val
0x180023c6e  mov     [rsp+3B0h+var_370], rax
0x180023c73  mov     r8d, 1D8h; Size
0x180023c79  lea     rcx, [rbp+2B0h+var_300]; void *
0x180023c7d  call    memset_0
0x180023c82  test    rdi, rdi
0x180023c85  jnz     short loc_180023C91
0x180023c87  mov     edi, 80070057h
0x180023c8c  jmp     loc_1800241B3
0x180023c91  xor     edx, edx; dwCoInit
0x180023c93  xor     ecx, ecx; pvReserved
0x180023c95  call    cs:__imp_CoInitializeEx
0x180023c9b  mov     edi, eax
0x180023c9d  test    eax, eax
0x180023c9f  js      loc_1800241B3
0x180023ca5  mov     rax, [rsi+1A8h]
0x180023cac  lea     r12, [rsi+198h]
0x180023cb3  mov     [rsp+3B0h+var_380], 1
0x180023cb8  test    rax, rax
0x180023cbb  jz      short loc_180023CC6
0x180023cbd  mov     qword ptr [rbp+2B0h+SystemTimeAsFileTime.dwLowDateTime], rax
0x180023cc4  jmp     short loc_180023CF8
0x180023cc6  mov     rdx, [r12]
0x180023cca  lea     r9, [rsi+1B0h]
0x180023cd1  lea     r8, [rbp+2B0h+SystemTimeAsFileTime]
0x180023cd8  mov     rcx, rbx
0x180023cdb  call    BipGetPackageImportanceInfoFromStore
0x180023ce0  test    eax, eax
0x180023ce2  jns     short loc_180023CF8
0x180023ce4  lea     rcx, [rbp+2B0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180023ceb  call    cs:__imp_GetSystemTimeAsFileTime
0x180023cf1  or      byte ptr [rsi+1D4h], 20h
0x180023cf8  mov     edx, [rsi+1A0h]
0x180023cfe  lea     r8, [rsp+3B0h+var_370]
0x180023d03  mov     rcx, r13
0x180023d06  call    BipEnergyBudgetGetOrCreatePerSessionInfo
0x180023d0b  test    eax, eax
0x180023d0d  js      loc_180023E13
0x180023d13  mov     rdi, [rsp+3B0h+var_370]
0x180023d18  test    rdi, rdi
0x180023d1b  jz      loc_180023E13
0x180023d21  cmp     qword ptr [rdi+20h], 0
0x180023d26  jnz     short loc_180023D5E
0x180023d28  mov     edx, [rsi+1A0h]
0x180023d2e  lea     rcx, [rsp+3B0h+var_338]
0x180023d33  call    BipSystemBackgroundAccessContextAllocateState
0x180023d38  test    eax, eax
0x180023d3a  js      short loc_180023D7F
0x180023d3c  movups  xmm0, [rsp+3B0h+var_338]
0x180023d41  xor     eax, eax
0x180023d43  movsd   xmm1, [rbp+2B0h+var_328]
0x180023d48  movups  xmmword ptr [rdi+20h], xmm0
0x180023d4c  mov     [rsp+3B0h+var_348], rax
0x180023d51  xorps   xmm0, xmm0
0x180023d54  movsd   qword ptr [rdi+30h], xmm1
0x180023d59  movups  [rsp+3B0h+var_338], xmm0
0x180023d5e  mov     rdx, [r12]
0x180023d62  lea     r9, [rsp+3B0h+var_378]
0x180023d67  mov     rcx, [rdi+20h]
0x180023d6b  mov     r8, rbx
0x180023d6e  call    BipSystemBackgroundAccessQueryPackageState
0x180023d73  test    eax, eax
0x180023d75  jns     short loc_180023D8A
0x180023d77  mov     r15d, 0FFFFFFFEh
0x180023d7d  jmp     short loc_180023DEB
0x180023d7f  mov     rax, [rbp+2B0h+var_328]
0x180023d83  mov     [rsp+3B0h+var_348], rax
0x180023d88  jmp     short loc_180023D8F
0x180023d8a  mov     r15d, [rsp+3B0h+var_378]
0x180023d8f  cmp     r15d, 0FFFFFFFDh
0x180023d93  ja      short loc_180023DEB
0x180023d95  movzx   eax, [rbp+2B0h+var_12C]
0x180023d9c  test    r15b, 2
0x180023da0  jz      short loc_180023DA8
0x180023da2  and     al, 0FDh
0x180023da4  or      al, 1
0x180023da6  jmp     short loc_180023DB2
0x180023da8  test    r15b, 20h
0x180023dac  jz      short loc_180023DB8
0x180023dae  and     al, 0FEh
0x180023db0  or      al, 2
0x180023db2  mov     [rbp+2B0h+var_12C], al
0x180023db8  test    al, 1
0x180023dba  jnz     short loc_180023DEB
0x180023dbc  test    byte ptr [rsi+1D4h], 1
0x180023dc3  jz      short loc_180023DEB
0x180023dc5  xor     r8d, r8d
0x180023dc8  mov     rdx, rbx
0x180023dcb  mov     rcx, r13
0x180023dce  call    BipEnergyBudgetGetBudgetForPackage
0x180023dd3  test    rax, rax
0x180023dd6  jz      short loc_180023DEB
0x180023dd8  mov     edx, [rax+130h]
0x180023dde  xor     ecx, ecx
0x180023de0  test    edx, edx
0x180023de2  cmovle  edx, ecx
0x180023de5  mov     [rax+130h], edx
0x180023deb  mov     rdx, [rdi+38h]
0x180023def  test    rdx, rdx
0x180023df2  jz      short loc_180023E13
0x180023df4  mov     r8, rbx
0x180023df7  call    BipEnergyBudgetIsPackageInImportantAppsTable
0x180023dfc  movzx   ecx, [rbp+2B0h+var_12C]
0x180023e03  and     al, 1
0x180023e05  shl     al, 2
0x180023e08  and     cl, 0FBh
0x180023e0b  or      al, cl
0x180023e0d  mov     [rbp+2B0h+var_12C], al
0x180023e13  mov     rdx, [r13+98h]
0x180023e1a  mov     r8, rbx
0x180023e1d  call    BipEnergyBudgetIsPackageInImportantAppsTable
0x180023e22  movzx   ecx, [rbp+2B0h+var_12C]
0x180023e29  and     al, 1
0x180023e2b  shl     al, 4
0x180023e2e  and     cl, 0EFh
0x180023e31  or      al, cl
0x180023e33  mov     [rsp+3B0h+origin], 0
0x180023e3b  test    byte ptr [r13+0B2h], 20h
0x180023e43  mov     [rbp+2B0h+var_12C], al
0x180023e49  jz      short loc_180023E70
0x180023e4b  lea     rdx, [rsp+3B0h+origin]; origin
0x180023e50  mov     rcx, rbx; packageFullName
0x180023e53  call    cs:__imp_GetStagedPackageOrigin
0x180023e59  test    eax, eax
0x180023e5b  jnz     short loc_180023E70
0x180023e5d  mov     eax, [rsp+3B0h+origin]
0x180023e61  add     eax, 0FFFFFFFCh
0x180023e64  cmp     eax, 2
0x180023e67  ja      short loc_180023E70
0x180023e69  or      [rbp+2B0h+var_12C], 10h
0x180023e70  mov     rdx, rsi
0x180023e73  mov     rcx, r13
0x180023e76  call    BipPackageImportanceScoreFromInputs
0x180023e7b  cmp     eax, 1
0x180023e7e  lea     rdx, [rbp+2B0h+var_300]
0x180023e82  mov     rcx, r13
0x180023e85  setnb   dil
0x180023e89  call    BipPackageImportanceScoreFromInputs
0x180023e8e  cmp     eax, 1
0x180023e91  mov     [rsi+1D0h], r15d
0x180023e98  mov     rax, qword ptr [rbp+2B0h+SystemTimeAsFileTime.dwLowDateTime]
0x180023e9f  mov     rdx, rbx
0x180023ea2  mov     [rsi+1A8h], rax
0x180023ea9  setnb   r12b
0x180023ead  movzx   eax, [rbp+2B0h+var_12C]
0x180023eb4  xor     r8d, r8d
0x180023eb7  or      al, 80h
0x180023eb9  mov     rcx, r13
0x180023ebc  mov     [rsi+1D4h], al
0x180023ec2  call    BipEnergyBudgetGetBudgetForPackage
0x180023ec7  test    rax, rax
0x180023eca  jz      short loc_180023ED7
0x180023ecc  mov     rdx, rax
0x180023ecf  mov     rcx, r13
0x180023ed2  call    BipEnergyBudgetCacheImportanceScoreForBudget
0x180023ed7  cmp     r12b, dil
0x180023eda  jz      loc_1800241AC
0x180023ee0  lea     rcx, [rsp+3B0h+var_340]; lpSystemTimeAsFileTime
0x180023ee5  call    cs:__imp_GetSystemTimeAsFileTime
0x180023eeb  mov     rcx, qword ptr [rsp+3B0h+var_340.dwLowDateTime]
0x180023ef0  sub     rcx, [rsi+1A8h]
0x180023ef7  mov     eax, cs:dword_1800C3098
0x180023efd  cmp     eax, 4
0x180023f00  jbe     loc_1800241AC
0x180023f06  mov     rdx, cs:qword_1800C30B0
0x180023f0d  mov     r9, 200000000003h
0x180023f17  mov     rax, cs:qword_1800C30A8
0x180023f1e  test    r9, rax
0x180023f21  jz      loc_1800241AC
0x180023f27  mov     rax, rdx
0x180023f2a  and     rax, r9
0x180023f2d  cmp     rax, rdx
0x180023f30  jnz     loc_1800241AC
0x180023f36  mov     rax, 346DC5D63886594Bh
0x180023f40  mul     rcx
0x180023f43  mov     rax, 8DAEA1D7F4CF721Bh
0x180023f4d  mov     r8, rdx
0x180023f50  shr     r8, 0Bh
0x180023f54  mul     r8
0x180023f57  sub     r8, rdx
0x180023f5a  shr     r8, 1
0x180023f5d  add     r8, rdx
0x180023f60  shr     r8, 1Ah
0x180023f64  test    rbx, rbx
0x180023f67  jz      short loc_180023F87
0x180023f69  nop     dword ptr [rax+00000000h]
0x180023f70  cmp     word ptr [rbx+r14*2+2], 0
0x180023f77  lea     r14, [r14+1]
0x180023f7b  jnz     short loc_180023F70
0x180023f7d  lea     r14d, ds:2[r14*2]
0x180023f85  jmp     short loc_180023F94
0x180023f87  lea     rbx, qword_1800A1670
0x180023f8e  mov     r14d, 2
0x180023f94  movzx   ecx, [rbp+2B0h+var_12C]
0x180023f9b  xor     edx, edx
0x180023f9d  movzx   eax, r12b
0x180023fa1  mov     [rsp+3B0h+var_378], eax
0x180023fa5  lea     rax, [rsp+3B0h+var_378]
0x180023faa  mov     [rbp+2B0h+var_F0], rax
0x180023fb1  mov     eax, ecx
0x180023fb3  and     eax, 1
0x180023fb6  mov     [rbp+2B0h+var_100], rbx
0x180023fbd  mov     [rsp+3B0h+var_368], eax
0x180023fc1  lea     rax, [rsp+3B0h+var_368]
0x180023fc6  mov     [rbp+2B0h+var_E0], rax
0x180023fcd  mov     eax, ecx
0x180023fcf  shr     eax, 1
0x180023fd1  and     eax, 1
0x180023fd4  mov     [rbp+2B0h+var_F8], r14d
0x180023fdb  mov     [rsp+3B0h+var_364], eax
0x180023fdf  lea     rax, [rsp+3B0h+var_364]
0x180023fe4  mov     [rbp+2B0h+var_D0], rax
0x180023feb  mov     eax, ecx
0x180023fed  shr     eax, 2
0x180023ff0  and     eax, 1
0x180023ff3  mov     [rbp+2B0h+var_F4], edx
0x180023ff9  mov     [rsp+3B0h+var_360], eax
0x180023ffd  lea     rax, [rsp+3B0h+var_360]
0x180024002  mov     [rbp+2B0h+var_C0], rax
0x180024009  mov     eax, ecx
0x18002400b  shr     eax, 3
0x18002400e  and     eax, 1
0x180024011  shr     ecx, 4
0x180024014  mov     [rsp+3B0h+var_35C], eax
0x180024018  and     ecx, 1
0x18002401b  lea     rax, [rsp+3B0h+var_35C]
0x180024020  mov     [rsp+3B0h+var_358], ecx
0x180024024  mov     [rbp+2B0h+var_B0], rax
0x18002402b  lea     rcx, _TraceLoggingMetadata
0x180024032  lea     rax, [rsp+3B0h+var_358]
0x180024037  mov     [rbp+2B0h+var_E8], 4
0x180024042  mov     [rbp+2B0h+var_A0], rax
0x180024049  lea     rax, [rbp+2B0h+var_320]
0x18002404d  mov     [rbp+2B0h+var_90], rax
0x180024054  movzx   eax, word ptr [r13+26h]
0x180024059  mov     [rsp+3B0h+var_354], eax
0x18002405d  lea     rax, [rsp+3B0h+var_354]
0x180024062  mov     [rbp+2B0h+var_80], rax
0x180024069  mov     eax, [rsp+3B0h+origin]
0x18002406d  mov     [rsp+3B0h+var_350], eax
0x180024071  lea     rax, [rsp+3B0h+var_350]
0x180024076  mov     [rbp+2B0h+var_70], rax
0x18002407d  mov     eax, [rsi+1D0h]
0x180024083  mov     [rsp+3B0h+var_34C], eax
0x180024087  lea     rax, [rsp+3B0h+var_34C]
0x18002408c  mov     [rbp+2B0h+var_60], rax
0x180024093  lea     rax, [rbp+2B0h+var_318]
0x180024097  mov     [rbp+2B0h+var_50], rax
0x18002409e  movzx   eax, cs:word_1800B1469
0x1800240a5  mov     dword ptr [rbp+2B0h+EventDescriptor.Level], eax
0x1800240a8  mov     rax, cs:off_1800C30A0
0x1800240af  mov     [rbp+2B0h+var_120.Ptr], rax
0x1800240b6  mov     [rbp+2B0h+var_D8], 4
0x1800240c1  mov     [rbp+2B0h+var_C8], 4
0x1800240cc  mov     [rbp+2B0h+var_B8], 4
0x1800240d7  mov     [rbp+2B0h+var_A8], 4
0x1800240e2  mov     [rbp+2B0h+var_98], 4
0x1800240ed  mov     [rbp+2B0h+var_320], r8
0x1800240f1  mov     [rbp+2B0h+var_88], 8
0x1800240fc  mov     [rbp+2B0h+var_78], 4
0x180024107  mov     [rbp+2B0h+var_68], 4
0x180024112  mov     [rbp+2B0h+var_58], 4
0x18002411d  mov     [rbp+2B0h+var_318], 1000000h
0x180024125  mov     [rbp+2B0h+var_48], 8
0x180024130  mov     dword ptr [rbp+2B0h+EventDescriptor.Id], 0B000000h
0x180024137  mov     [rbp+2B0h+EventDescriptor.Keyword], r9
0x18002413b  movzx   eax, word ptr [rax]
0x18002413e  mov     [rbp+2B0h+var_120.Size], eax
  ... truncated ...
```
