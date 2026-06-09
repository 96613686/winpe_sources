# CMsiEngine::SecureRepair(void)

- ea: `0x180030568`
- end: `0x180031c90`
- name: `?SecureRepair@CMsiEngine@@QEAAPEAVIMsiRecord@@XZ`
- size: `5928`
- prototype: `struct IMsiRecord *__fastcall(CMsiEngine *__hidden this)`
- caller_count: `3`
- callee_count: `27`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180030300`
- `0x180136c78`
- `0x1801795e0`

## callees

- `0x180025904`
- `0x180025a18`
- `0x180027b54`
- `0x180030568`
- `0x180035a8c`
- `0x18003bccc`
- `0x18004295c`
- `0x180061334`
- `0x180064a78`
- `0x180066074`
- `0x180068680`
- `0x18008f3e8`
- `0x1800a6ef0`
- `0x1800c2854`
- `0x1800cb888`
- `0x1800d6ff0`
- `0x1800e80a4`
- `0x180137b34`
- `0x18013a830`
- `0x18014148c`
- `0x18014983c`
- `0x180156c9c`
- `0x180209674`
- `0x18020aa58`
- `0x18020ab20`
- `0x18020b404`
- `0x18025c010`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x18003192a`
- `KERNEL32!DeleteFileW` at `0x18003192a`

## string_xrefs

- `0x180030835`: `SECREPAIR: Error in CreatePath`
- `0x180030955`: `SECREPAIR: Error in CreatePath`
- `0x180030a5b`: `SECREPAIR: Source location is URL. Initial Installation or Advertising.`
- `0x180030a45`: `SECREPAIR: Source location is URL. User is elevated.`
- `0x180030a64`: `SECREPAIR: Secure repair not needed`
- `0x18003076a`: `SECREPAIR: Error determining package source type`
- `0x180030b5e`: `SECREPAIR: Source Subpath Temporary column index unavailable`
- `0x180031bed`: `SECREPAIR: Error Installer folder does not exist`
- `0x180030ce4`: `SECREPAIR: Error determining whether source hash file already exists`
- `0x180030d47`: `SECREPAIR: Re-Create hashes`
- `0x180030dbc`: `SECREPAIR: Hash Database: %s`
- `0x1800318e0`: `SECREPAIR: SourceHash database file already exists. Deleting it.`
- `0x180031bcf`: `SECREPAIR: Error in CreateDatabase for write`
- `0x1800310a8`: `SECREPAIR: Failed to commit the hash database`
- `0x180031af7`: `SECREPAIR: New Hash Database creation complete.`
- `0x180031b4d`: `SECREPAIR: Failed to create hash for the install source files`
- `0x180031b8a`: `SECREPAIR: Failed to create hash for the CustomAction source files`
- `0x180030f63`: `SECREPAIR: SourceHash file is not found`
- `0x180030841`: `SECREPAIR: Admin consent through REGISTRY to not show HashMissing UAC`
- `0x1800311c5`: `SECREPAIR: UAC not supported and could not take approval from user`
- `0x180031862`: `SECREPAIR: UAC not supported and could not take approval from user`
- `0x1800314ec`: `SECREPAIR: Error in Creating File Hash Storage Path`
- `0x180031682`: `SECREPAIR: File Hash Storage Path contains Junction`
- `0x180031006`: `SECREPAIR: Error in CreateDatabase for read`
- `0x180031537`: `SECREPAIR: Failed to verify hash for the install source files`
- `0x18003178c`: `SECREPAIR: Failed to verify hash for the CustomAction source files`
- `0x1800317c6`: `SECREPAIR: Hash mismatch`
- `0x180030f9c`: `SECREPAIR: Source files have been tampered`
- `0x180030e40`: `SECREPAIR: Neither a installation/repair nor an advertisement scenario`

## pseudocode

```c
struct IMsiRecord *__fastcall CMsiEngine::SecureRepair(CMsiEngine *this)
{
  __int64 v2; // rdi
  CMsiSecureRepairManager *v3; // rax
  __int64 v4; // rbx
  unsigned int v5; // r15d
  __int64 v6; // rsi
  __int64 v7; // rcx
  __int64 v8; // rsi
  void (*v9)(void); // rax
  int v11; // eax
  CMsiSecureRepairManager *v12; // rax
  __int64 (__fastcall *v13)(CMsiEngine *, struct IMsiRecord **, __int64 *, int *); // rsi
  const unsigned __int16 *v14; // r9
  __int64 (__fastcall *v15)(__int64, __int64, __int64); // r14
  __int64 v16; // rsi
  __int64 v17; // rax
  const unsigned __int16 *v18; // r9
  int v19; // esi
  const unsigned __int16 *v20; // r9
  const unsigned __int16 *v21; // rax
  _QWORD *v22; // rax
  _QWORD *v23; // rcx
  struct IMsiRecord *Record; // rdi
  __int64 (__fastcall *v25)(__int64, __int64, __int64); // r14
  __int64 v26; // rsi
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // r14
  __int64 (__fastcall *v30)(__int64, __int64, int *, _QWORD); // rsi
  __int64 v31; // rax
  const unsigned __int16 *v32; // rax
  int v33; // esi
  __int64 v34; // rsi
  __int64 v35; // r14
  __int64 v36; // r15
  __int64 v37; // r12
  __int64 v38; // r13
  CMsiSecureRepairManager **v39; // rdi
  unsigned int v40; // ecx
  const unsigned __int16 *v41; // r9
  void (*v42)(void); // rax
  __int64 v43; // r8
  __int64 v44; // r8
  __int64 v45; // rdi
  __int64 v46; // rax
  __int64 v47; // rcx
  __int64 v48; // rax
  __int64 v49; // rcx
  __int64 v50; // rax
  __int64 v51; // rcx
  __int64 v52; // rax
  __int64 v53; // rcx
  __int64 v54; // rax
  __int64 v55; // rcx
  __int64 v56; // rax
  int v57; // eax
  __int64 v58; // rax
  __int64 v59; // rcx
  __int64 v60; // rax
  __int64 v61; // rcx
  __int64 v62; // rax
  __int64 v63; // rcx
  __int64 v64; // rax
  __int64 v65; // rcx
  __int64 v66; // rax
  __int64 v67; // rcx
  __int64 v68; // rax
  struct IMsiRecord *v69; // rax
  __int64 v70; // rcx
  __int64 v71; // rax
  __int64 v72; // rax
  CMsiSecureRepairManager **v73; // rdi
  int v74; // ecx
  __int64 v75; // r8
  const WCHAR *v76; // rax
  __int64 (__fastcall *v77)(__int64, __int64, __int64, __int64); // r14
  __int64 v78; // rsi
  __int64 v79; // rax
  struct IMsiDatabase *v80; // r14
  __int64 (__fastcall *v81)(struct IMsiDatabase *, _QWORD, _QWORD, __int64); // rsi
  __int64 v82; // rdi
  MsiString *v83; // rax
  __int64 v84; // rsi
  __int64 (__fastcall *v85)(__int64, __int64, _QWORD); // rdi
  MsiString *v86; // rax
  int v87; // r14d
  __int64 v88; // rsi
  __int64 (__fastcall *v89)(__int64, __int64, _QWORD); // rdi
  MsiString *v90; // rax
  __int64 v91; // rsi
  __int64 (__fastcall *v92)(__int64, __int64, _QWORD); // rdi
  MsiString *v93; // rax
  int v94; // edi
  const unsigned __int16 *v95; // r9
  __int64 v96; // [rsp+60h] [rbp-59h] BYREF
  __int64 v97; // [rsp+68h] [rbp-51h] BYREF
  struct IMsiString *MsiDirectory; // [rsp+70h] [rbp-49h] BYREF
  __int64 v99; // [rsp+78h] [rbp-41h] BYREF
  struct IMsiDatabase *v100; // [rsp+80h] [rbp-39h] BYREF
  __int64 v101; // [rsp+88h] [rbp-31h] BYREF
  __int64 v102; // [rsp+90h] [rbp-29h] BYREF
  __int64 v103; // [rsp+98h] [rbp-21h] BYREF
  __int64 v104; // [rsp+A0h] [rbp-19h] BYREF
  __int64 v105; // [rsp+A8h] [rbp-11h]
  __int64 v106; // [rsp+B0h] [rbp-9h] BYREF
  __int64 (__fastcall *v107)(__int64, __int64, struct IMsiRecord *); // [rsp+B8h] [rbp-1h]
  _DWORD v108[20]; // [rsp+C0h] [rbp+7h] BYREF
  CMsiSecureRepairManager **v109; // [rsp+120h] [rbp+67h] BYREF
  int v110; // [rsp+128h] [rbp+6Fh] BYREF
  struct IMsiRecord *v111; // [rsp+130h] [rbp+77h] BYREF
  int v112; // [rsp+138h] [rbp+7Fh] BYREF

  v109 = (CMsiSecureRepairManager **)this;
  v96 = (*(__int64 (__fastcall **)(CMsiEngine *))(*(_QWORD *)this + 296LL))(this);
  v2 = (*(__int64 (__fastcall **)(CMsiEngine *))(*(_QWORD *)this + 56LL))(this);
  v99 = v2;
  v3 = *(CMsiSecureRepairManager **)this;
  LODWORD(v111) = 0;
  v4 = (*((__int64 (__fastcall **)(CMsiEngine *, const unsigned __int16 *))v3 + 23))(this, L"SourceDir");
  v97 = 0;
  v5 = (*(__int64 (__fastcall **)(CMsiEngine *))(*(_QWORD *)this + 504LL))(this);
  LODWORD(v105) = v5;
  if ( g_scServerContext != 2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    if ( v2 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    goto LABEL_11;
  }
  v6 = *((_QWORD *)this + 276);
  if ( v6 )
  {
    v7 = *(_QWORD *)(v6 + 48);
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
    v8 = *(_QWORD *)(v6 + 48);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    if ( v2 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    v9 = *(void (**)(void))(*(_QWORD *)v96 + 16LL);
    goto LABEL_8;
  }
  if ( *(_WORD *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 66) + 80LL))(*((_QWORD *)this + 66)) == 58
    && *((_QWORD *)this + 22) )
  {
    goto LABEL_27;
  }
  v15 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v2 + 120LL);
  v16 = CComPointer<IEnumMsiRecord>::operator=(&v97);
  v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 80LL))(v4);
  v8 = v15(v2, v17, v16);
  if ( v8 )
  {
    if ( !g_dmDiagnosticMode )
      goto LABEL_29;
    v14 = L"SECREPAIR: Error in CreatePath";
    goto LABEL_17;
  }
  v106 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v97 + 72LL))(v97);
  v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v106 + 144LL))(v106);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v106);
  if ( v19 )
  {
    if ( v5 <= 1 )
    {
      if ( g_dmDiagnosticMode )
      {
        v20 = L"SECREPAIR: Source location is URL. Initial Installation or Advertising.";
        goto LABEL_38;
      }
LABEL_27:
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v97);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v99);
LABEL_11:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
      return 0;
    }
    if ( IsAdmin() || *((_BYTE *)this + 601) )
    {
      if ( g_dmDiagnosticMode )
      {
        v20 = L"SECREPAIR: Source location is URL. User is elevated.";
LABEL_38:
        DebugString(9, 0, 0, v20, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
        goto LABEL_27;
      }
      goto LABEL_27;
    }
  }
  v21 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v96 + 80LL))(v96);
  if ( !CMsiSecureRepairManager::NeedsSecureRepair(v21, (enum eSecRepairModeEnum *)&v111) )
  {
    if ( !g_dmDiagnosticMode )
      goto LABEL_27;
    v20 = L"SECREPAIR: Secure repair not needed";
    goto LABEL_38;
  }
  v22 = operator new(0x40u);
  v23 = v22;
  if ( !v22 )
  {
    *((_QWORD *)this + 276) = 0;
    Record = (struct IMsiRecord *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v2 + 48LL))(v2, 1);
    (*(void (__fastcall **)(struct IMsiRecord *, __int64, __int64))(*(_QWORD *)Record + 104LL))(Record, 1, 8);
LABEL_170:
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v97);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    goto LABEL_171;
  }
  *v22 = this;
  v22[1] = 0;
  *((_WORD *)v22 + 8) = 0;
  *((_BYTE *)v22 + 18) = 0;
  *((_DWORD *)v22 + 5) = 0;
  *(_QWORD *)((char *)v22 + 28) = 0;
  *(_QWORD *)((char *)v22 + 36) = 0;
  v22[6] = 0;
  v22[7] = -1;
  v11 = (int)v111;
  *((_QWORD *)this + 276) = v23;
  *((_DWORD *)v23 + 6) = v11;
  *(_DWORD *)(*((_QWORD *)this + 276) + 40LL) = CMsiEngine::GetDeploymentFlags(this);
  v12 = *(CMsiSecureRepairManager **)this;
  v112 = 0;
  v13 = (__int64 (__fastcall *)(CMsiEngine *, struct IMsiRecord **, __int64 *, int *))*((_QWORD *)v12 + 68);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
  v111 = (struct IMsiRecord *)v2;
  v8 = v13(this, &v111, &v96, &v112);
  if ( v8 )
  {
    if ( !g_dmDiagnosticMode )
    {
LABEL_29:
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v97);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v99);
      v9 = *(void (**)(void))(*(_QWORD *)v96 + 16LL);
LABEL_8:
      v9();
      return (struct IMsiRecord *)v8;
    }
    v14 = L"SECREPAIR: Error determining package source type";
LABEL_17:
    DebugString(9, 0, 0, v14, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
    goto LABEL_29;
  }
  if ( (v112 & 2) != 0 )
    *(_BYTE *)(*((_QWORD *)this + 276) + 17LL) = 1;
  if ( !*((_DWORD *)this + 463) && g_dmDiagnosticMode )
    DebugString(
      9,
      0,
      0,
      L"SECREPAIR: Source Subpath Temporary column index unavailable",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      0,
      0);
  *(_DWORD *)(*((_QWORD *)this + 276) + 20LL) = *((_DWORD *)this + 463);
  v102 = (*(__int64 (__fastcall **)(CMsiEngine *))(*(_QWORD *)this + 72LL))(this);
  v101 = 0;
  MsiDirectory = GetMsiDirectory();
  if ( !(*(unsigned int (__fastcall **)(struct IMsiString *, __int64, const unsigned __int16 *))(*(_QWORD *)MsiDirectory
                                                                                               + 200LL))(
          MsiDirectory,
          4,
          L"\\") )
    MsiString::operator+=(&MsiDirectory, L"\\");
  v25 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v2 + 120LL);
  v26 = CComPointer<IEnumMsiRecord>::operator=(&v101);
  v27 = (*(__int64 (__fastcall **)(struct IMsiString *))(*(_QWORD *)MsiDirectory + 80LL))(MsiDirectory);
  v8 = v25(v2, v27, v26);
  if ( v8 )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        L"SECREPAIR: Error in CreatePath",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
LABEL_28:
    (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)MsiDirectory + 16LL))(MsiDirectory);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v101);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v102);
    goto LABEL_29;
  }
  v108[0] = 0;
  v28 = (*(__int64 (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v101 + 160LL))(v101, v108);
  if ( !v108[0] || v28 )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        L"SECREPAIR: Error Installer folder does not exist",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    Record = PostError(2362, MsiDirectory);
    (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)MsiDirectory + 16LL))(MsiDirectory);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v101);
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v102);
    goto LABEL_170;
  }
  MsiString::MsiString((MsiString *)&v104, L"SourceHash");
  MsiString::operator+=(&v104, &v96);
  v110 = 0;
  v29 = v101;
  v30 = *(__int64 (__fastcall **)(__int64, __int64, int *, _QWORD))(*(_QWORD *)v101 + 120LL);
  v31 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v104 + 80LL))(v104);
  v8 = v30(v29, v31, &v110, 0);
  if ( v8 )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        L"SECREPAIR: Error determining whether source hash file already exists",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v104 + 16LL))(v104);
    goto LABEL_28;
  }
  if ( *((_BYTE *)this + 601) )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        L"SECREPAIR: Re-Create hashes",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    *(_BYTE *)(*((_QWORD *)this + 276) + 18LL) = 1;
  }
  v100 = 0;
  v103 = 0;
  MsiString::operator+=(&MsiDirectory, &v104);
  if ( g_dmDiagnosticMode )
  {
    v32 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IMsiString *))(*(_QWORD *)MsiDirectory + 80LL))(MsiDirectory);
    DebugString(
      9,
      0,
      0,
      L"SECREPAIR: Hash Database: %s",
      v32,
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      0,
      0);
  }
  v33 = v105;
  if ( (unsigned int)v105 > 1
    && !CMsiSecureRepairManager::IsGPDeployFirstInstall(*((CMsiSecureRepairManager **)this + 276))
    && !*(_BYTE *)(*((_QWORD *)this + 276) + 18LL) )
  {
    if ( ((v33 - 2) & 0xFFFFFFFD) != 0 )
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          L"SECREPAIR: Neither a installation/repair nor an advertisement scenario",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      goto LABEL_26;
    }
    v34 = (*(__int64 (__fastcall **)(CMsiEngine *, const WCHAR *))(*(_QWORD *)this + 184LL))(this, L"ProductName");
    v35 = (*(__int64 (__fastcall **)(CMsiEngine *, const unsigned __int16 *))(*(_QWORD *)this + 184LL))(
            this,
            L"ProductVersion");
    v36 = (*(__int64 (__fastcall **)(CMsiEngine *, const unsigned __int16 *))(*(_QWORD *)this + 184LL))(
            this,
            L"ProductLanguage");
    v37 = (*(__int64 (__fastcall **)(CMsiEngine *, const unsigned __int16 *))(*(_QWORD *)this + 184LL))(
            this,
            L"Manufacturer");
    v38 = (*(__int64 (__fastcall **)(CMsiEngine *, const unsigned __int16 *))(*(_QWORD *)this + 184LL))(
            this,
            L"DATABASE");
    v105 = (*((__int64 (__fastcall **)(CMsiSecureRepairManager **, const unsigned __int16 *))*v109 + 23))(
             v109,
             L"OriginalDatabase");
    if ( !v110 )
    {
      v39 = v109;
      if ( *((_DWORD *)v109[276] + 6) == 1 )
      {
        if ( g_dmDiagnosticMode )
          DebugString(
            9,
            0,
            0,
            L"SECREPAIR: SourceHash file is not found",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        v40 = 1;
        goto LABEL_79;
      }
      if ( CMsiSecureRepairManager::DonotShowHashMissingUAC(0) )
      {
        if ( !g_dmDiagnosticMode )
          goto LABEL_24;
        v18 = L"SECREPAIR: Admin consent through REGISTRY to not show HashMissing UAC";
LABEL_23:
        DebugString(9, 0, 0, v18, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
LABEL_24:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v105 + 16LL))(v105);
LABEL_25:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
LABEL_26:
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v103);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v100);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v104 + 16LL))(v104);
        (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)MsiDirectory + 16LL))(MsiDirectory);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v101);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v102);
        goto LABEL_27;
      }
      if ( g_iMajorVersion <= 6
        && (g_iMajorVersion != 6 || g_iMinorVersion <= 1 && (g_iMinorVersion != 1 || g_iServicePackLevel < 0)) )
      {
        if ( !g_dmDiagnosticMode )
          goto LABEL_24;
        v18 = L"SECREPAIR: UAC not supported and could not take approval from user";
        goto LABEL_23;
      }
      LODWORD(v109) = GetIntegerPolicyValue(5, 1, v43);
      if ( (unsigned int)GetIntegerPolicyValue(5, 0, v44) == 1 && (_DWORD)v109 == 1
        || IsAdmin()
        || ((*((__int64 (__fastcall **)(CMsiSecureRepairManager **))*v39 + 12))(v39) & 1) != 0 )
      {
        goto LABEL_24;
      }
      v45 = v105;
      v46 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v105 + 80LL))(v105);
      v47 = *(_QWORD *)v38;
      v109 = (CMsiSecureRepairManager **)v46;
      v48 = (*(__int64 (__fastcall **)(__int64))(v47 + 80))(v38);
      v49 = *(_QWORD *)v37;
      v111 = (struct IMsiRecord *)v48;
      v50 = (*(__int64 (__fastcall **)(__int64))(v49 + 80))(v37);
      v51 = *(_QWORD *)v36;
      v106 = v50;
      v52 = (*(__int64 (__fastcall **)(__int64))(v51 + 80))(v36);
      v53 = *(_QWORD *)v35;
      v105 = v52;
      v54 = (*(__int64 (__fastcall **)(__int64))(v53 + 80))(v35);
      v55 = *(_QWORD *)v34;
      v107 = (__int64 (__fastcall *)(__int64, __int64, struct IMsiRecord *))v54;
      v56 = (*(__int64 (__fastcall **)(__int64))(v55 + 80))(v34);
      v57 = InstallPromptForElevatedCredentials(v102, 7, v56, v107, v105, v106, v111, v109, 0, 0, 0);
LABEL_100:
      if ( v57 < 0 )
      {
        v69 = PostError(3);
        v70 = *(_QWORD *)v45;
        v109 = (CMsiSecureRepairManager **)v69;
        (*(void (__fastcall **)(__int64))(v70 + 16))(v45);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v103);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v100);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v104 + 16LL))(v104);
        (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)MsiDirectory + 16LL))(MsiDirectory);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v101);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v102);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v97);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v99);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
        return (struct IMsiRecord *)v109;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
      goto LABEL_25;
    }
    v106 = 0;
    v107 = *(__int64 (__fastcall **)(__int64, __int64, struct IMsiRecord *))(*(_QWORD *)v2 + 120LL);
    v111 = (struct IMsiRecord *)CComPointer<IEnumMsiRecord>::operator=(&v106);
    v71 = (*(__int64 (__fastcall **)(struct IMsiString *))(*(_QWORD *)MsiDirectory + 80LL))(MsiDirectory);
    v111 = (struct IMsiRecord *)v107(v2, v71, v111);
    if ( v111 )
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          L"SECREPAIR: Error in Creating File Hash Storage Path",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v106);
LABEL_107:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v105 + 16LL))(v105);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v103);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v100);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v104 + 16LL))(v104);
      (*(void (__fastcall **)(struct IMsiString *))(*(_QWORD *)MsiDirectory + 16LL))(MsiDirectory);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v101);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v102);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v97);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v99);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
      return v111;
    }
    LODWORD(v111) = 0;
    if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v106 + 584LL))(v106) )
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          L"SECREPAIR: File Hash Storage Path contains Junction",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      LODWORD(v111) = 1;
    }
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v106);
    if ( !(_DWORD)v111 )
    {
      v107 = *(__int64 (__fastcall **)(__int64, __int64, struct IMsiRecord *))(*(_QWORD *)v2 + 104LL);
      v111 = (struct IMsiRecord *)CComPointer<IEnumMsiRecord>::operator=(&v100);
      v72 = (*(__int64 (__fastcall **)(struct IMsiString *))(*(_QWORD *)MsiDirectory + 80LL))(MsiDirectory);
      Record = (struct IMsiRecord *)((__int64 (__fastcall *)(__int64, __int64, _QWORD, struct IMsiRecord *))v107)(
                                      v2,
                                      v72,
                                      0,
                                      v111);
      if ( Record || !v100 )
      {
        if ( g_dmDiagnosticMode )
          DebugString(
            9,
            0,
            0,
            L"SECREPAIR: Error in CreateDatabase for read",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        goto LABEL_80;
      }
      v73 = v109;
      CMsiSecureRepairManager::SetHashDatabase(v109[276], v100);
      v111 = CMsiSecureRepairManager::AllFilesHash(v73[276]);
      if ( v111 )
      {
        if ( g_dmDiagnosticMode )
          DebugString(
            9,
            0,
            0,
            L"SECREPAIR: Failed to verify hash for the install source files",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        goto LABEL_107;
      }
      v111 = CMsiSecureRepairManager::SecureCustomActions(v73[276]);
      if ( v111 )
      {
        if ( g_dmDiagnosticMode )
          DebugString(
            9,
            0,
            0,
            L"SECREPAIR: Failed to verify hash for the CustomAction source files",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        goto LABEL_107;
      }
      if ( *((_BYTE *)v73[276] + 16) != 1 )
        goto LABEL_24;
      v74 = g_dmDiagnosticMode;
      if ( !g_dmDiagnosticMode )
      {
LABEL_127:
        if ( *((_DWORD *)v109[276] + 6) == 1 )
        {
          if ( !v74 )
            goto LABEL_78;
          v41 = L"SECREPAIR: Source files have been tampered";
        }
        else
        {
          if ( g_iMajorVersion > 6
            || g_iMajorVersion == 6 && (g_iMinorVersion > 1 || g_iMinorVersion == 1 && g_iServicePackLevel >= 0) )
          {
            LODWORD(v111) = GetIntegerPolicyValue(5, 1, 0);
            if ( (unsigned int)GetIntegerPolicyValue(5, 0, v75) == 1 && (_DWORD)v111 == 1
              || IsAdmin()
              || ((*((__int64 (__fastcall **)(CMsiSecureRepairManager **))*v109 + 12))(v109) & 1) != 0 )
            {
              goto LABEL_24;
            }
            v45 = v105;
            v58 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v105 + 80LL))(v105);
            v59 = *(_QWORD *)v38;
            v109 = (CMsiSecureRepairManager **)v58;
            v60 = (*(__int64 (__fastcall **)(__int64))(v59 + 80))(v38);
            v61 = *(_QWORD *)v37;
            v111 = (struct IMsiRecord *)v60;
            v62 = (*(__int64 (__fastcall **)(__int64))(v61 + 80))(v37);
            v63 = *(_QWORD *)v36;
            v107 = (__int64 (__fastcall *)(__int64, __int64, struct IMsiRecord *))v62;
            v64 = (*(__int64 (__fastcall **)(__int64))(v63 + 80))(v36);
            v65 = *(_QWORD *)v35;
            v106 = v64;
            v66 = (*(__int64 (__fastcall **)(__int64))(v65 + 80))(v35);
            v67 = *(_QWORD *)v34;
            v105 = v66;
            v68 = (*(__int64 (__fastcall **)(__int64))(v67 + 80))(v34);
            v57 = InstallPromptForElevatedCredentials(v102, 6, v68, v105, v106, v107, v111, v109, 0, 0, 0);
            goto LABEL_100;
          }
          if ( !v74 )
          {
LABEL_78:
            v40 = 2;
LABEL_79:
            Record = CreateRecord(v40);
            (*(void (__fastcall **)(struct IMsiRecord *, __int64, __int64))(*(_QWORD *)Record + 104LL))(Record, 1, 1260);
LABEL_80:
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v105 + 16LL))(v105);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
            goto LABEL_82;
          }
          v41 = L"SECREPAIR: UAC not supported and could not take approval from user";
        }
        DebugString(9, 0, 0, v41, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
        goto LABEL_78;
      }
      DebugString(
        9,
        0,
        0,
        L"SECREPAIR: Hash mismatch",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    }
    v74 = g_dmDiagnosticMode;
    goto LABEL_127;
  }
  CElevate::CElevate((CElevate *)&v109, 1);
  if ( v110 )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        L"SECREPAIR: SourceHash database file already exists. Deleting it.",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    v76 = (const WCHAR *)(*(__int64 (__fastcall **)(struct IMsiString *))(*(_QWORD *)MsiDirectory + 80LL))(MsiDirectory);
    DeleteFileW(v76);
  }
  v77 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v2 + 104LL);
  v78 = CComPointer<IEnumMsiRecord>::operator=(&v100);
  v79 = (*(__int64 (__fastcall **)(struct IMsiString *))(*(_QWORD *)MsiDirectory + 80LL))(MsiDirectory);
  Record = (struct IMsiRecord *)v77(v2, v79, 3, v78);
  CElevate::~CElevate((CElevate *)&v109);
  if ( Record || !v100 )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        L"SECREPAIR: Error in CreateDatabase for write",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    goto LABEL_82;
  }
  CMsiSecureRepairManager::SetHashDatabase(*((CMsiSecureRepairManager **)this + 276), v100);
  v80 = v100;
  v81 = *(__int64 (__fastcall **)(struct IMsiDatabase *, _QWORD, _QWORD, __int64))(*(_QWORD *)v100 + 88LL);
  v82 = CComPointer<IEnumMsiRecord>::operator=(&v103);
  v83 = MsiString::MsiString((MsiString *)&v109, L"SourceHash");
  Record = (struct IMsiRecord *)v81(v80, *(_QWORD *)v83, 0, v82);
  (*((void (__fastcall **)(CMsiSecureRepairManager **))*v109 + 2))(v109);
  if ( !Record )
  {
    v84 = v103;
    v85 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v103 + 120LL);
    v86 = MsiString::MsiString((MsiString *)&v109, L"FileName");
    v87 = v85(v84, 11520, *(_QWORD *)v86);
    (*((void (__fastcall **)(CMsiSecureRepairManager **))*v109 + 2))(v109);
    v88 = v103;
    v89 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v103 + 120LL);
    v90 = MsiString::MsiString((MsiString *)&v111, L"HashAlgo");
    LODWORD(v109) = v89(v88, 256, *(_QWORD *)v90);
    (*(void (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)v111 + 16LL))(v111);
    v91 = v103;
    v92 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v103 + 120LL);
    v93 = MsiString::MsiString((MsiString *)&v111, L"FileHashValue");
    v94 = v92(v91, 3328, *(_QWORD *)v93);
    (*(void (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)v111 + 16LL))(v111);
    if ( !v87 || !(_DWORD)v109 || !v94 )
    {
      Record = PostError(2728, L"SourceHash");
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v103);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v100);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v104 + 16LL))(v104);
      v42 = *(void (**)(void))(*(_QWORD *)MsiDirectory + 16LL);
      goto LABEL_84;
    }
    Record = (struct IMsiRecord *)(*(__int64 (__fastcall **)(struct IMsiDatabase *))(*(_QWORD *)v100 + 152LL))(v100);
    if ( !Record )
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          L"SECREPAIR: New Hash Database creation complete.",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      Record = CMsiSecureRepairManager::AllFilesHash(*((CMsiSecureRepairManager **)this + 276));
      if ( Record )
      {
        if ( !g_dmDiagnosticMode )
          goto LABEL_82;
        v95 = L"SECREPAIR: Failed to create hash for the install source files";
        goto LABEL_81;
      }
      Record = CMsiSecureRepairManager::SecureCustomActions(*((CMsiSecureRepairManager **)this + 276));
      if ( Record )
      {
        if ( !g_dmDiagnosticMode )
          goto LABEL_82;
        v95 = L"SECREPAIR: Failed to create hash for the CustomAction source files";
LABEL_81:
        DebugString(9, 0, 0, v95, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
        goto LABEL_82;
      }
      Record = (struct IMsiRecord *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 276) + 8LL)
                                                                      + 152LL))(*(_QWORD *)(*((_QWORD *)this + 276) + 8LL));
      if ( !Record )
        goto LABEL_26;
    }
    if ( !g_dmDiagnosticMode )
      goto LABEL_82;
    v95 = L"SECREPAIR: Failed to commit the hash database";
    goto LABEL_81;
  }
LABEL_82:
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v103);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v100);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v104 + 16LL))(v104);
  v42 = *(void (**)(void))(*(_QWORD *)MsiDirectory + 16LL);
LABEL_84:
  v42();
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v101);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v102);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v97);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
LABEL_171:
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v99);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
  return Record;
}

```

## disassembly

```asm
0x180030568  mov     [rsp-8+arg_0], rcx
0x18003056d  push    rbp
0x18003056e  push    rbx
0x18003056f  push    rsi
0x180030570  push    rdi
0x180030571  push    r12
0x180030573  push    r13
0x180030575  push    r14
0x180030577  push    r15
0x180030579  lea     rbp, [rsp-1Fh]
0x18003057e  sub     rsp, 0D8h
0x180030585  mov     rax, [rcx]
0x180030588  mov     r13, rcx
0x18003058b  mov     rax, [rax+128h]
0x180030592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030597  mov     [rbp+57h+var_B0], rax
0x18003059b  mov     rcx, r13
0x18003059e  mov     rax, [r13+0]
0x1800305a2  mov     rax, [rax+38h]
0x1800305a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800305ab  mov     rdi, rax
0x1800305ae  mov     [rbp+57h+var_98], rax
0x1800305b2  mov     rax, [r13+0]
0x1800305b6  lea     rdx, aSourcedir; "SourceDir"
0x1800305bd  xor     r12d, r12d
0x1800305c0  mov     rcx, r13
0x1800305c3  mov     dword ptr [rbp+57h+arg_10], r12d
0x1800305c7  mov     rax, [rax+0B8h]
0x1800305ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800305d3  mov     rbx, rax
0x1800305d6  mov     [rbp+57h+var_A8], r12
0x1800305da  mov     rax, [r13+0]
0x1800305de  mov     rcx, r13
0x1800305e1  mov     rax, [rax+1F8h]
0x1800305e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800305ed  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x1800305f4  mov     r15d, eax
0x1800305f7  mov     dword ptr [rbp+57h+var_68], eax
0x1800305fa  jnz     loc_180030680
0x180030600  mov     rsi, [r13+8A0h]
0x180030607  test    rsi, rsi
0x18003060a  jz      loc_1800307C3
0x180030610  mov     rcx, [rsi+30h]
0x180030614  test    rcx, rcx
0x180030617  jnz     loc_1800307B2
0x18003061d  mov     rcx, [rbp+57h+var_A8]
0x180030621  mov     rsi, [rsi+30h]
0x180030625  test    rcx, rcx
0x180030628  jz      short loc_180030636
0x18003062a  mov     rax, [rcx]
0x18003062d  mov     rax, [rax+10h]
0x180030631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030636  mov     rax, [rbx]
0x180030639  mov     rcx, rbx
0x18003063c  mov     rax, [rax+10h]
0x180030640  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030645  test    rdi, rdi
0x180030648  jz      short loc_180030659
0x18003064a  mov     rcx, [rdi]
0x18003064d  mov     rax, [rcx+10h]
0x180030651  mov     rcx, rdi
0x180030654  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030659  mov     rcx, [rbp+57h+var_B0]
0x18003065d  mov     rdx, [rcx]
0x180030660  mov     rax, [rdx+10h]
0x180030664  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030669  mov     rax, rsi
0x18003066c  add     rsp, 0D8h
0x180030673  pop     r15
0x180030675  pop     r14
0x180030677  pop     r13
0x180030679  pop     r12
0x18003067b  pop     rdi
0x18003067c  pop     rsi
0x18003067d  pop     rbx
0x18003067e  pop     rbp
0x18003067f  retn
0x180030680  mov     rcx, [rbp+57h+var_A8]
0x180030684  test    rcx, rcx
0x180030687  jz      short loc_180030695
0x180030689  mov     rax, [rcx]
0x18003068c  mov     rax, [rax+10h]
0x180030690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030695  mov     rax, [rbx]
0x180030698  mov     rcx, rbx
0x18003069b  mov     rax, [rax+10h]
0x18003069f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800306a4  test    rdi, rdi
0x1800306a7  jz      short loc_1800306B8
0x1800306a9  mov     rax, [rdi]
0x1800306ac  mov     rcx, rdi
0x1800306af  mov     rax, [rax+10h]
0x1800306b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800306b8  mov     rcx, [rbp+57h+var_B0]
0x1800306bc  mov     rax, [rcx]
0x1800306bf  mov     rax, [rax+10h]
0x1800306c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800306c8  xor     eax, eax
0x1800306ca  jmp     short loc_18003066C
0x1800306cc  mov     [rax], r13
0x1800306cf  mov     [rax+8], r12
0x1800306d3  mov     [rax+10h], r12w
0x1800306d8  mov     [rax+12h], r12b
0x1800306dc  mov     [rax+14h], r12d
0x1800306e0  mov     [rax+1Ch], r12
0x1800306e4  mov     [rax+24h], r12
0x1800306e8  mov     [rax+30h], r12
0x1800306ec  mov     qword ptr [rax+38h], 0FFFFFFFFFFFFFFFFh
0x1800306f4  mov     eax, dword ptr [rbp+57h+arg_10]
0x1800306f7  mov     [r13+8A0h], rcx
0x1800306fe  mov     [rcx+18h], eax
0x180030701  mov     rcx, r13; this
0x180030704  call    ?GetDeploymentFlags@CMsiEngine@@IEAAHXZ; CMsiEngine::GetDeploymentFlags(void)
0x180030709  mov     rcx, [r13+8A0h]
0x180030710  mov     [rcx+28h], eax
0x180030713  mov     rax, [r13+0]
0x180030717  mov     [rbp+57h+arg_18], r12d
0x18003071b  mov     rsi, [rax+220h]
0x180030722  test    rdi, rdi
0x180030725  jz      short loc_180030736
0x180030727  mov     rcx, [rdi]
0x18003072a  mov     rax, [rcx+8]
0x18003072e  mov     rcx, rdi
0x180030731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030736  lea     r9, [rbp+57h+arg_18]
0x18003073a  mov     [rbp+57h+arg_10], rdi
0x18003073e  lea     r8, [rbp+57h+var_B0]
0x180030742  mov     rcx, r13
0x180030745  lea     rdx, [rbp+57h+arg_10]
0x180030749  mov     rax, rsi
0x18003074c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030751  mov     rsi, rax
0x180030754  test    rax, rax
0x180030757  jz      loc_180030B2A
0x18003075d  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x180030764  jz      loc_1800309AE
0x18003076a  lea     r9, aSecrepairError_9; "SECREPAIR: Error determining package so"...
0x180030771  mov     [rsp+110h+var_B8], r12; void *
0x180030776  lea     rax, aNull; "(NULL)"
0x18003077d  mov     [rsp+110h+var_C0], r12d; unsigned int
0x180030782  xor     edx, edx; unsigned __int16
0x180030784  mov     [rsp+110h+var_C8], rax; unsigned __int16 *
0x180030789  xor     r8d, r8d; int
0x18003078c  mov     [rsp+110h+var_D0], rax; unsigned __int16 *
0x180030791  mov     [rsp+110h+var_D8], rax; unsigned __int16 *
0x180030796  mov     [rsp+110h+var_E0], rax; unsigned __int16 *
0x18003079b  lea     ecx, [rdx+9]; int
0x18003079e  mov     [rsp+110h+var_E8], rax; unsigned __int16 *
0x1800307a3  mov     [rsp+110h+var_F0], rax; unsigned __int16 *
0x1800307a8  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1800307ad  jmp     loc_1800309AE
0x1800307b2  mov     rax, [rcx]
0x1800307b5  mov     rax, [rax+8]
0x1800307b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800307be  jmp     loc_18003061D
0x1800307c3  mov     rcx, [r13+210h]
0x1800307ca  mov     rax, [rcx]
0x1800307cd  mov     rax, [rax+50h]
0x1800307d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800307d6  cmp     word ptr [rax], 3Ah ; ':'
0x1800307da  jnz     short loc_1800307E9
0x1800307dc  cmp     [r13+0B0h], r12
0x1800307e3  jnz     loc_18003092A
0x1800307e9  mov     rax, [rdi]
0x1800307ec  lea     rcx, [rbp+57h+var_A8]
0x1800307f0  mov     r14, [rax+78h]
0x1800307f4  call    ??4?$CComPointer@VIEnumMsiRecord@@@@QEAAAEAV0@PEAVIEnumMsiRecord@@@Z; CComPointer<IEnumMsiRecord>::operator=(IEnumMsiRecord *)
0x1800307f9  mov     rcx, [rbx]
0x1800307fc  mov     rsi, rax
0x1800307ff  mov     rax, [rcx+50h]
0x180030803  mov     rcx, rbx
0x180030806  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003080b  mov     rdx, rax
0x18003080e  mov     r8, rsi
0x180030811  mov     rax, r14
0x180030814  mov     rcx, rdi
0x180030817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003081c  mov     rsi, rax
0x18003081f  test    rax, rax
0x180030822  jz      loc_1800309DF
0x180030828  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x18003082f  jz      loc_1800309AE
0x180030835  lea     r9, aSecrepairError_10; "SECREPAIR: Error in CreatePath"
0x18003083c  jmp     loc_180030771
0x180030841  lea     r9, aSecrepairAdmin; "SECREPAIR: Admin consent through REGIST"...
0x180030848  mov     [rsp+110h+var_B8], rcx; void *
0x18003084d  lea     rax, aNull; "(NULL)"
0x180030854  mov     [rsp+110h+var_C0], ecx; unsigned int
0x180030858  xor     edx, edx; unsigned __int16
0x18003085a  mov     [rsp+110h+var_C8], rax; unsigned __int16 *
0x18003085f  xor     r8d, r8d; int
0x180030862  mov     [rsp+110h+var_D0], rax; unsigned __int16 *
0x180030867  mov     [rsp+110h+var_D8], rax; unsigned __int16 *
0x18003086c  mov     [rsp+110h+var_E0], rax; unsigned __int16 *
0x180030871  lea     ecx, [rdx+9]; int
0x180030874  mov     [rsp+110h+var_E8], rax; unsigned __int16 *
0x180030879  mov     [rsp+110h+var_F0], rax; unsigned __int16 *
0x18003087e  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180030883  mov     rax, [rbp+57h+var_68]
0x180030887  mov     rcx, [rax]
0x18003088a  mov     rdx, [rcx+10h]
0x18003088e  mov     rcx, rax
0x180030891  mov     rax, rdx
0x180030894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030899  mov     rax, [r13+0]
0x18003089d  mov     rcx, r13
0x1800308a0  mov     rax, [rax+10h]
0x1800308a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800308a9  mov     rax, [r12]
0x1800308ad  mov     rcx, r12
0x1800308b0  mov     rax, [rax+10h]
0x1800308b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800308b9  mov     rax, [r15]
0x1800308bc  mov     rcx, r15
0x1800308bf  mov     rax, [rax+10h]
0x1800308c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800308c8  mov     rax, [r14]
0x1800308cb  mov     rcx, r14
0x1800308ce  mov     rax, [rax+10h]
0x1800308d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800308d7  mov     rax, [rsi]
0x1800308da  mov     rcx, rsi
0x1800308dd  mov     rax, [rax+10h]
0x1800308e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800308e6  lea     rcx, [rbp+57h+var_78]
0x1800308ea  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1800308ef  lea     rcx, [rbp+57h+var_90]
0x1800308f3  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1800308f8  mov     rcx, [rbp+57h+var_70]
0x1800308fc  mov     rax, [rcx]
0x1800308ff  mov     rax, [rax+10h]
0x180030903  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030908  mov     rcx, [rbp+57h+var_A0]
0x18003090c  mov     rax, [rcx]
0x18003090f  mov     rax, [rax+10h]
0x180030913  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030918  lea     rcx, [rbp+57h+var_88]
0x18003091c  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x180030921  lea     rcx, [rbp+57h+var_80]
0x180030925  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x18003092a  lea     rcx, [rbp+57h+var_A8]
0x18003092e  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x180030933  mov     rax, [rbx]
0x180030936  mov     rcx, rbx
0x180030939  mov     rax, [rax+10h]
0x18003093d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030942  lea     rcx, [rbp+57h+var_98]
0x180030946  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x18003094b  jmp     loc_1800306B8
0x180030950  mov     [rsp+110h+var_B8], r14; void *
0x180030955  lea     r9, aSecrepairError_10; "SECREPAIR: Error in CreatePath"
0x18003095c  mov     [rsp+110h+var_C0], r14d; unsigned int
0x180030961  xor     edx, edx; unsigned __int16
0x180030963  mov     [rsp+110h+var_C8], r15; unsigned __int16 *
0x180030968  xor     r8d, r8d; int
0x18003096b  mov     [rsp+110h+var_D0], r15; unsigned __int16 *
0x180030970  mov     ecx, r12d; int
0x180030973  mov     [rsp+110h+var_D8], r15; unsigned __int16 *
0x180030978  mov     [rsp+110h+var_E0], r15; unsigned __int16 *
0x18003097d  mov     [rsp+110h+var_E8], r15; unsigned __int16 *
0x180030982  mov     [rsp+110h+var_F0], r15; unsigned __int16 *
0x180030987  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18003098c  mov     rcx, [rbp+57h+var_A0]
0x180030990  mov     rax, [rcx]
0x180030993  mov     rax, [rax+10h]
0x180030997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003099c  lea     rcx, [rbp+57h+var_88]
0x1800309a0  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1800309a5  lea     rcx, [rbp+57h+var_80]
0x1800309a9  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1800309ae  lea     rcx, [rbp+57h+var_A8]
0x1800309b2  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1800309b7  mov     rax, [rbx]
0x1800309ba  mov     rcx, rbx
0x1800309bd  mov     rax, [rax+10h]
0x1800309c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800309c6  lea     rcx, [rbp+57h+var_98]
0x1800309ca  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1800309cf  mov     rcx, [rbp+57h+var_B0]
0x1800309d3  mov     rax, [rcx]
0x1800309d6  mov     rax, [rax+10h]
0x1800309da  jmp     loc_180030664
0x1800309df  mov     rcx, [rbp+57h+var_A8]
0x1800309e3  mov     rax, [rcx]
0x1800309e6  mov     rax, [rax+48h]
0x1800309ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800309ef  mov     rdx, rax
0x1800309f2  mov     [rbp+57h+var_60], rax
0x1800309f6  mov     rcx, [rax]
0x1800309f9  mov     rax, [rcx+90h]
0x180030a00  mov     rcx, rdx
0x180030a03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a08  lea     rcx, [rbp+57h+var_60]
0x180030a0c  mov     esi, eax
0x180030a0e  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x180030a13  mov     r14d, 1
0x180030a19  test    esi, esi
0x180030a1b  jz      loc_180030AAC
0x180030a21  cmp     r15d, r14d
0x180030a24  jbe     short loc_180030A4E
  ... truncated ...
```
