# COSInstaller::MergeUpdates(ulong,tagSusDeployData * const,IUpdateDeploymentCallback *,bool *,wchar_t * *)

- ea: `0x18003fd7c`
- end: `0x18004080e`
- name: `?MergeUpdates@COSInstaller@@AEAAJKQEAUtagSusDeployData@@PEAUIUpdateDeploymentCallback@@PEA_NPEAPEA_W@Z`
- size: `2706`
- prototype: `__int64 __fastcall(COSInstaller *__hidden this, unsigned int, struct tagSusDeployData *const, struct IUpdateDeploymentCallback *, bool *, wchar_t **)`
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003cc10`

## callees

- `0x180003180`
- `0x180008ab8`
- `0x180008f98`
- `0x180009060`
- `0x180009438`
- `0x18000dce4`
- `0x1800110fc`
- `0x180011b44`
- `0x180011bf0`
- `0x18003bbdc`
- `0x18003fd7c`
- `0x180040814`
- `0x180040a3c`
- `0x180042e50`
- `0x180043a60`
- `0x180044b90`
- `0x180048ba0`
- `0x1800498a0`
- `0x180049ff8`
- `0x18004b558`
- `0x180051f78`
- `0x1800526f4`
- `0x180052830`
- `0x180061960`
- `0x180061d54`
- `0x180068ea0`
- `0x180068f20`

## import_xrefs

- `RPCRT4!UuidFromStringW` at `0x18003ff4f`
- `RPCRT4!UuidFromStringW` at `0x18003ff4f`
- `OLEAUT32!__imp_SysAllocString` at `0x18004027d`
- `OLEAUT32!__imp_SysAllocString` at `0x18004027d`
- `OLEAUT32!__imp_SysFreeString` at `0x18004074c`
- `OLEAUT32!__imp_SysFreeString` at `0x18004074c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180040560`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180040560`

## string_xrefs

- `0x18003fe99`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x1800403f7`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x18004043e`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x18004059e`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x180040642`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x180040682`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x1800406c7`: `C:\__w\1\s\src\Client\Engine\handler\OSDeployment\Installer\OSInstaller.cpp`
- `0x180040656`: `ParseHandlerXml`
- `0x18003ff9a`: `Skipping merging UUP on Prem language specific update ID: %ws`
- `0x18003fe62`: `CreateMergedSandboxDir`
- `0x1800401b7`: `Merge failed for update ID: %ws.%d`
- `0x180040785`: `No updates were merged`

## pseudocode

```c
__int64 __fastcall COSInstaller::MergeUpdates(
        COSInstaller *this,
        unsigned int a2,
        struct tagSusDeployData *const a3,
        struct IUpdateDeploymentCallback *a4,
        bool *a5,
        wchar_t **a6)
{
  struct tagSusDeployData *v6; // rbx
  wchar_t *v8; // rsi
  OLECHAR *v9; // r12
  WCHAR *v10; // r13
  __int64 v11; // rdx
  int FilesPerPatchType; // r15d
  COSInstaller *v13; // rcx
  unsigned __int64 v14; // r9
  __int64 v15; // rax
  __int64 v16; // r15
  struct tagDSUpdateMetadata *v17; // rdi
  wchar_t *v18; // r14
  OSDeploymentHelper::CDeploymentSessionWrapper *v19; // rbx
  struct tagSusDeployData *v20; // rax
  unsigned __int16 *v21; // rcx
  unsigned int v22; // eax
  struct tagDSUpdateMetadata *v23; // r15
  wchar_t **v24; // r8
  __int64 v25; // r15
  char *v26; // rax
  char IsEnabled; // al
  struct tagDSFile **v28; // rax
  __int64 v29; // r15
  __int64 v30; // rdx
  const struct std::nothrow_t *v31; // rdx
  BSTR v32; // rax
  int v33; // eax
  int CombinedPath; // eax
  int v35; // eax
  GUID *v36; // r15
  wchar_t **v37; // rax
  const struct std::nothrow_t *v38; // rdx
  __int64 v39; // rdx
  __int64 v40; // rdx
  unsigned int v41; // edi
  unsigned int v42; // ebx
  unsigned int v43; // esi
  __int64 v44; // r14
  __int64 v45; // r13
  __int64 v46; // r15
  const WCHAR *v47; // rbx
  LPWSTR v48; // rcx
  WCHAR i; // ax
  const wchar_t *v50; // rdi
  int v51; // eax
  int v52; // eax
  __int64 v53; // rdi
  BSTR *v54; // rbx
  int v55; // eax
  unsigned int *v57; // [rsp+20h] [rbp-E0h]
  int v58; // [rsp+20h] [rbp-E0h]
  int v59; // [rsp+20h] [rbp-E0h]
  int v60; // [rsp+38h] [rbp-C8h]
  int v61; // [rsp+50h] [rbp-B0h]
  int v62; // [rsp+50h] [rbp-B0h]
  GUID *rguid; // [rsp+60h] [rbp-A0h] BYREF
  const struct tagDSFile *v65; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v66; // [rsp+70h] [rbp-90h]
  void *v67; // [rsp+78h] [rbp-88h] BYREF
  wchar_t **v68; // [rsp+80h] [rbp-80h] BYREF
  __int64 v69; // [rsp+88h] [rbp-78h]
  LPCWSTR lpNewFileName; // [rsp+90h] [rbp-70h] BYREF
  void *lpMem; // [rsp+98h] [rbp-68h] BYREF
  void *v72; // [rsp+A0h] [rbp-60h] BYREF
  struct tagDSUpdateMetadata *v73; // [rsp+A8h] [rbp-58h] BYREF
  struct tagDSFile **v74; // [rsp+B0h] [rbp-50h] BYREF
  OLECHAR *psz; // [rsp+B8h] [rbp-48h] BYREF
  wchar_t *v76; // [rsp+C0h] [rbp-40h] BYREF
  OSDeploymentHelper::CDeploymentSessionWrapper *v77; // [rsp+C8h] [rbp-38h] BYREF
  wchar_t *v78; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v79; // [rsp+D8h] [rbp-28h] BYREF
  GUID v80; // [rsp+E0h] [rbp-20h]
  __int64 v81; // [rsp+F0h] [rbp-10h]
  const struct tagDSGlobalUpdateId *v82; // [rsp+F8h] [rbp-8h]
  bool *v83; // [rsp+100h] [rbp+0h]
  wchar_t **v84; // [rsp+108h] [rbp+8h]
  __int64 v85; // [rsp+110h] [rbp+10h]
  GUID v86; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v87[112]; // [rsp+130h] [rbp+30h] BYREF
  _QWORD v88[14]; // [rsp+1A0h] [rbp+A0h] BYREF
  struct tagDSFile ***v89; // [rsp+210h] [rbp+110h] BYREF
  COSInstaller *v90; // [rsp+218h] [rbp+118h] BYREF
  void **v91; // [rsp+220h] [rbp+120h] BYREF
  __int64 v92; // [rsp+228h] [rbp+128h]
  __int64 v93; // [rsp+230h] [rbp+130h]
  void **v94; // [rsp+238h] [rbp+138h] BYREF
  __int64 v95; // [rsp+240h] [rbp+140h]
  __int64 v96; // [rsp+248h] [rbp+148h]
  UUID Uuid; // [rsp+250h] [rbp+150h] BYREF
  _BYTE v98[112]; // [rsp+260h] [rbp+160h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+218h]

  v6 = a3;
  v66 = a2;
  v90 = this;
  v83 = a5;
  v84 = a6;
  v8 = 0;
  v9 = 0;
  psz = 0;
  v85 = 0;
  v10 = 0;
  lpNewFileName = 0;
  v94 = &CSusArrayList<wchar_t *,CSusArrayListItemOpSusFree<wchar_t *>>::`vftable';
  v95 = 0;
  v96 = 0;
  v91 = &CSusArrayList<wchar_t *,CSusArrayListItemOpSusFree<wchar_t *>>::`vftable';
  v92 = 0;
  v93 = 0;
  if ( !a5 )
  {
    v11 = 1664;
LABEL_5:
    FilesPerPatchType = -2147467261;
    goto LABEL_8;
  }
  if ( !a6 )
  {
    v11 = 1665;
    goto LABEL_5;
  }
  *a5 = 0;
  FilesPerPatchType = COSInstaller::CreateMergedSandboxDir((COSInstaller *)a6, &psz);
  v61 = FilesPerPatchType;
  if ( FilesPerPatchType < 0 )
  {
    LODWORD(v57) = FilesPerPatchType;
    WUTrace(0, 0, 4096, 2, v57, L"CreateMergedSandboxDir");
    v11 = 1674;
    v9 = psz;
    goto LABEL_8;
  }
  v15 = 0;
  HIDWORD(v65) = 0;
  v9 = psz;
  if ( a2 )
  {
    while ( 1 )
    {
      v16 = 296 * v15;
      v69 = 296 * v15;
      v73 = (struct tagDSUpdateMetadata *)*((_QWORD *)v6 + 37 * v15 + 7);
      v89 = 0;
      memset(v88, 0, 0x68u);
      rguid = (GUID *)&CONTAINING_RECORD(v73, GUID, Data4)->Data4[4];
      Trace::UpdateIdToString::UpdateIdToString(
        (Trace::UpdateIdToString *)v98,
        (struct tagDSUpdateMetadata *)((char *)v73 + 4));
      LODWORD(v65) = 0;
      v67 = 0;
      LODWORD(v74) = 0;
      v72 = 0;
      v17 = 0;
      v78 = 0;
      v18 = 0;
      v76 = 0;
      lpMem = 0;
      v19 = 0;
      v77 = 0;
      Uuid = 0;
      v20 = a3;
      v21 = *(unsigned __int16 **)((char *)a3 + v16);
      if ( v21 && *v21 )
      {
        v22 = UuidFromStringW(v21, &Uuid);
        if ( v22 )
        {
          FilesPerPatchType = wil::details::in1diag3::Return_Win32(
                                retaddr,
                                (void *)0x6A0,
                                (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
                                (const char *)v22,
                                (unsigned int)v57);
          goto LABEL_101;
        }
        v20 = a3;
      }
      v82 = (struct tagSusDeployData *)((char *)v20 + v16 + 32);
      v23 = v73;
      if ( IsUUPOnPremLangSpecificChildUpdate(v73, v82, &Uuid) )
      {
        Trace::UpdateIdToString::UpdateIdToString(
          (Trace::UpdateIdToString *)v87,
          (const struct tagDSGlobalUpdateId *)rguid);
        v8 = 0;
        WUTrace(0, 0, 4096, 4, 0, L"Skipping merging UUP on Prem language specific update ID: %ws");
      }
      else
      {
        FilesPerPatchType = OSDeploymentHelper::GetFilesPerPatchType(
                              (OSDeploymentHelper *)*((unsigned int *)v23 + 116),
                              *((_QWORD *)v23 + 59),
                              (struct tagDSFile *const)&v89,
                              &v65,
                              (unsigned int *)&v67,
                              &v74,
                              (unsigned int *)&v72);
        if ( FilesPerPatchType < 0 )
        {
          LODWORD(v57) = FilesPerPatchType;
          WUTrace(0, 0, 4096, 2, v57, L"Determine the servicing stack cab file and/or metadata files");
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x6BA,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
            (const char *)(unsigned int)FilesPerPatchType,
            v59);
          goto LABEL_101;
        }
        FilesPerPatchType = OSDeploymentHelper::ParseHandlerXml(
                              (struct tagDSUpdateMetadata *)((char *)v73 + 544),
                              (const struct tagDSDataBlob *)&v78,
                              v24);
        if ( FilesPerPatchType < 0 )
        {
          LODWORD(v57) = FilesPerPatchType;
          WUTrace(0, 0, 4096, 2, v57, L"ParseHandlerXml");
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x6C2,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
            (const char *)(unsigned int)FilesPerPatchType,
            v58);
          v17 = (struct tagDSUpdateMetadata *)v78;
          goto LABEL_101;
        }
        v88[1] = v98;
        v25 = v69;
        v88[2] = *(_QWORD *)((char *)a3 + v69 + 104);
        v88[3] = *(_QWORD *)((char *)a3 + v69 + 248);
        v88[0] = *(_QWORD *)((char *)a3 + v69 + 256);
        v26 = (char *)v88[4];
        if ( *((_BYTE *)a3 + v69 + 112) )
          v26 = (char *)a3 + v69 + 112;
        v88[4] = v26;
        v79 = 0;
        v80 = GUID_NULL;
        v81 = 0;
        IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex>::GetImpl'::`2'::impl);
        v17 = (struct tagDSUpdateMetadata *)v78;
        if ( IsEnabled )
        {
          FilesPerPatchType = OSDeploymentHelper::SandboxAccessMutexGuard::Acquire(
                                (struct _GUID *)&v79,
                                rguid,
                                (void **)0x493E0);
          if ( FilesPerPatchType < 0 )
          {
            v39 = 1748;
            goto LABEL_98;
          }
          v25 = v69;
        }
        rguid = (GUID *)v88;
        v86 = Buf1;
        v73 = v17;
        if ( v89 )
          v28 = v89[9];
        else
          v28 = 0;
        v74 = v28;
        v68 = (wchar_t **)((char *)a3 + v25 + 16);
        FilesPerPatchType = Microsoft::WRL::Details::MakeAndInitialize<OSDeploymentHelper::CDeploymentSessionWrapper,OSDeploymentHelper::CDeploymentSessionWrapper,wchar_t * const &,wchar_t * const &,wchar_t * const &,int,std::nullptr_t,_GUID,unsigned long const &,tagOptionalSessionInfo5 *>(
                              &v77,
                              v68,
                              (const wchar_t **)&v74,
                              (wchar_t **)&v73,
                              (unsigned int *)&v65,
                              (struct tagDSFile ***)&v67,
                              (__int64)&v86,
                              v60,
                              (char **)&rguid);
        v19 = v77;
        if ( FilesPerPatchType < 0 )
        {
          v39 = 1760;
LABEL_98:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v39,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
            (const char *)(unsigned int)FilesPerPatchType,
            (int)v57);
LABEL_63:
          OSDeploymentHelper::SandboxAccessMutexGuard::~SandboxAccessMutexGuard((OSDeploymentHelper::SandboxAccessMutexGuard *)&v79);
LABEL_101:
          if ( v19 )
            (*(void (__fastcall **)(OSDeploymentHelper::CDeploymentSessionWrapper *))(*(_QWORD *)v19 + 16LL))(v19);
          if ( v8 )
            SusFree(v8);
          if ( v18 )
            SusFree(v18);
          if ( v17 )
            SusFree(v17);
          if ( v72 )
            operator delete(v72, v38);
          if ( v67 )
            operator delete(v67, v38);
          goto LABEL_121;
        }
        v61 = (*(__int64 (__fastcall **)(char *, OLECHAR *))(*((_QWORD *)v77 + 1) + 72LL))((char *)v77 + 8, v9);
        v29 = v69;
        v30 = *(_QWORD *)((char *)a3 + v69 + 56);
        if ( v61 >= 0 )
        {
          (*(void (__fastcall **)(__int64, __int64, _QWORD))(*((_QWORD *)v90 + 15) + 8LL))(
            (__int64)v90 + 120,
            v30 + 4,
            0);
          (*(void (__fastcall **)(__int64, const struct tagDSGlobalUpdateId *, _QWORD))(*((_QWORD *)v90 + 18) + 8LL))(
            (__int64)v90 + 144,
            v82,
            0);
          v32 = SysAllocString(v9);
          *(_QWORD *)((char *)a3 + v29 + 24) = v32;
          if ( !v32 )
          {
            FilesPerPatchType = -2147024882;
            v39 = 1793;
            goto LABEL_98;
          }
          v33 = CreateCombinedPath(*v68, L"Metadata", &v76);
          v18 = v76;
          if ( v33 < 0 )
          {
            FilesPerPatchType = v33;
            v39 = 1798;
            goto LABEL_98;
          }
          CombinedPath = CreateCombinedPath(v76, (const wchar_t *)v17, (wchar_t **)&lpMem);
          v8 = (wchar_t *)lpMem;
          if ( CombinedPath < 0 )
          {
            FilesPerPatchType = CombinedPath;
            v39 = 1802;
            goto LABEL_98;
          }
          if ( (int)CheckIfFileExists((const wchar_t *)lpMem) >= 0 && v89 )
          {
            rguid = 0;
            v35 = CreateCombinedPath(
                    *(const wchar_t **)((char *)a3 + v29 + 16),
                    (const wchar_t *)v89[9],
                    (wchar_t **)&rguid);
            v36 = rguid;
            if ( v35 < 0 )
            {
              v40 = 1811;
              goto LABEL_60;
            }
            v35 = CheckIfFileExists((const wchar_t *)rguid);
            if ( v35 < 0 )
            {
              v40 = 1813;
LABEL_60:
              v62 = v35;
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v40,
                (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
                (const char *)(unsigned int)v35,
                (int)v57);
              if ( v36 )
                SusFree(v36);
              FilesPerPatchType = v62;
              goto LABEL_63;
            }
            v37 = (wchar_t **)v8;
            v8 = 0;
            lpMem = 0;
            v68 = v37;
            CSusArrayList<HandlerMap *,CSusArrayListItemOpDelete<HandlerMap *>>::Add(&v94, &v68, 0);
            v68 = (wchar_t **)v36;
            CSusArrayList<HandlerMap *,CSusArrayListItemOpDelete<HandlerMap *>>::Add(&v91, &v68, 0);
          }
          OSDeploymentHelper::SandboxAccessMutexGuard::~SandboxAccessMutexGuard((OSDeploymentHelper::SandboxAccessMutexGuard *)&v79);
          if ( v19 )
            (*(void (__fastcall **)(OSDeploymentHelper::CDeploymentSessionWrapper *))(*(_QWORD *)v19 + 16LL))(v19);
          if ( v8 )
            SusFree(v8);
          v8 = 0;
          if ( v18 )
            SusFree(v18);
        }
        else
        {
          v60 = *(_DWORD *)(v30 + 20);
          Trace::GuidToString::GuidToString((Trace::GuidToString *)v87, (const struct _GUID *)(v30 + 4));
          FilesPerPatchType = v61;
          LODWORD(v57) = v61;
          WUTrace(0, 0, 4096, 3, v57, L"Merge failed for update ID: %ws.%d");
          if ( v61 != -2145079036 )
          {
            v39 = 1783;
            goto LABEL_98;
          }
          v8 = 0;
          WUTrace(0, 0, 4096, 4, 0, L"Continuing the merge operation");
          v61 = 0;
          OSDeploymentHelper::SandboxAccessMutexGuard::~SandboxAccessMutexGuard((OSDeploymentHelper::SandboxAccessMutexGuard *)&v79);
          if ( v19 )
            (*(void (__fastcall **)(OSDeploymentHelper::CDeploymentSessionWrapper *))(*(_QWORD *)v19 + 16LL))(v19);
        }
        if ( v17 )
          SusFree(v17);
        if ( v72 )
          operator delete(v72, v31);
        v13 = (COSInstaller *)v67;
        if ( v67 )
          operator delete(v67, v31);
      }
      v15 = (unsigned int)(HIDWORD(v65) + 1);
      HIDWORD(v65) = v15;
      if ( (unsigned int)v15 >= v66 )
      {
        v41 = HIDWORD(v96);
        if ( HIDWORD(v96) < 2 )
        {
          v53 = v66;
          if ( v66 )
          {
            v54 = (BSTR *)((char *)a3 + 24);
            do
            {
              SysFreeString(*v54);
              *v54 = 0;
              v54 += 37;
              --v53;
            }
            while ( v53 );
          }
          break;
        }
        *v83 = 1;
        v42 = 0;
        if ( v41 )
        {
          v43 = 1;
          v44 = v41;
          v45 = v95;
          do
          {
            v89 = 0;
            v90 = 0;
            if ( v42 < v41 )
            {
              v46 = *(_QWORD *)(v45 + 8LL * v42);
              if ( (int)GetFileVersion(v46, &v89) >= 0
                && v43 < v41
                && (int)GetFileVersion(v46, &v90) >= 0
                && v89 != (struct tagDSFile ***)v90
                && v89 < (struct tagDSFile ***)v90 )
              {
                v42 = v43;
              }
            }
            ++v43;
            --v44;
          }
          while ( v44 );
          v10 = (WCHAR *)lpNewFileName;
          v8 = 0;
        }
        if ( v42 >= HIDWORD(v93) )
        {
          FilesPerPatchType = -2145124345;
          v11 = 1868;
          goto LABEL_8;
        }
        _mm_lfence();
        v47 = *(const WCHAR **)(v92 + 8LL * v42);
        if ( !v47 )
        {
          FilesPerPatchType = -2147467261;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3E7,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\fileutil.cpp",
            (const char *)0x80004003LL,
            (int)v57);
          v11 = 1871;
          goto LABEL_8;
        }
        v48 = (LPWSTR)v47;
        for ( i = *v47; i; i = *v48 )
        {
          if ( i == 92 || i == 47 )
            v8 = v48;
          v48 = CharNextW(v48);
        }
        v50 = v8 + 1;
        if ( !v8 )
          v50 = v47;
        v51 = CreateCombinedPath(v9, v50, (wchar_t **)&lpNewFileName);
        FilesPerPatchType = v51;
        if ( v51 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x753,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
            (const char *)(unsigned int)v51,
            (int)v57);
          v10 = (WCHAR *)lpNewFileName;
          goto LABEL_121;
        }
        v10 = (WCHAR *)lpNewFileName;
        SusCopyFileRetryIfSharingViolation(v47, lpNewFileName, 0, 0);
        v52 = DuplicateString<wchar_t const *,wchar_t *>(v50, v84);
        FilesPerPatchType = v52;
        if ( v52 < 0 )
        {
          v14 = (unsigned int)v52;
          v11 = 1883;
          goto LABEL_9;
        }
        FilesPerPatchType = v61;
        if ( v61 < 0 )
        {
          v11 = 1885;
          goto LABEL_8;
        }
LABEL_120:
        FilesPerPatchType = 0;
        goto LABEL_121;
      }
      v6 = a3;
    }
  }
  v55 = COSInstaller::DeleteMergedSandboxDir(v13, v9);
  FilesPerPatchType = v55;
  if ( v55 >= 0 )
  {
    WUTrace(0, 0, 4096, 4, 0, L"No updates were merged");
    goto LABEL_120;
  }
  if ( (unsigned int)(v55 + 2147024894) > 1 )
  {
    v11 = 1833;
LABEL_8:
    v14 = (unsigned int)FilesPerPatchType;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Installer\\OSInstaller.cpp",
      (const char *)v14,
      (int)v57);
  }
LABEL_121:
  CSusArrayList<wchar_t *,CSusArrayListItemOpSusFree<wchar_t *>>::~CSusArrayList<wchar_t *,CSusArrayListItemOpSusFree<wchar_t *>>(&v91);
  CSusArrayList<wchar_t *,CSusArrayListItemOpSusFree<wchar_t *>>::~CSusArrayList<wchar_t *,CSusArrayListItemOpSusFree<wchar_t *>>(&v94);
  if ( v10 )
    SusFree(v10);
  if ( v9 )
    SusFree(v9);
  return (unsigned int)FilesPerPatchType;
}

```

## disassembly

```asm
0x18003fd7c  mov     [rsp-8+arg_8], rbx
0x18003fd81  push    rbp
0x18003fd82  push    rsi
0x18003fd83  push    rdi
0x18003fd84  push    r12
0x18003fd86  push    r13
0x18003fd88  push    r14
0x18003fd8a  push    r15
0x18003fd8c  lea     rbp, [rsp-1E0h]
0x18003fd94  sub     rsp, 2E0h
0x18003fd9b  mov     rax, cs:__security_cookie
0x18003fda2  xor     rax, rsp
0x18003fda5  mov     [rbp+210h+var_40], rax
0x18003fdac  mov     rbx, r8
0x18003fdaf  mov     [rsp+310h+var_2B8], rbx
0x18003fdb4  mov     edi, edx
0x18003fdb6  mov     [rsp+310h+var_2A0], edi
0x18003fdba  mov     [rbp+210h+var_F8], rcx
0x18003fdc1  mov     rax, [rbp+210h+arg_20]
0x18003fdc8  mov     [rbp+210h+var_210], rax
0x18003fdcc  mov     rcx, [rbp+210h+arg_28]; this
0x18003fdd3  mov     [rbp+210h+var_208], rcx
0x18003fdd7  xor     esi, esi
0x18003fdd9  mov     r12d, esi
0x18003fddc  mov     [rbp+210h+psz], rsi
0x18003fde0  mov     [rbp+210h+var_200], rsi
0x18003fde4  mov     r13d, esi
0x18003fde7  mov     [rbp+210h+lpNewFileName], rsi
0x18003fdeb  xorps   xmm0, xmm0
0x18003fdee  movups  [rbp+210h+var_D8], xmm0
0x18003fdf5  lea     r8, ??_7?$CSusArrayList@PEA_WV?$CSusArrayListItemOpSusFree@PEA_W@@@@6B@; const CSusArrayList<wchar_t *,CSusArrayListItemOpSusFree<wchar_t *>>::`vftable'
0x18003fdfc  mov     qword ptr [rbp+210h+var_D8], r8
0x18003fe03  mov     qword ptr [rbp+210h+var_D8+8], rsi
0x18003fe0a  mov     [rbp+210h+var_C8], rsi
0x18003fe11  movups  [rbp+210h+var_F0], xmm0
0x18003fe18  mov     qword ptr [rbp+210h+var_F0], r8
0x18003fe1f  mov     qword ptr [rbp+210h+var_F0+8], rsi
0x18003fe26  mov     [rbp+210h+var_E0], rsi
0x18003fe2d  test    rax, rax
0x18003fe30  jnz     short loc_18003FE39
0x18003fe32  mov     edx, 680h
0x18003fe37  jmp     short loc_18003FE43
0x18003fe39  test    rcx, rcx
0x18003fe3c  jnz     short loc_18003FE4B
0x18003fe3e  mov     edx, 681h
0x18003fe43  mov     r15d, 80004003h
0x18003fe49  jmp     short loc_18003FE8F
0x18003fe4b  mov     [rax], sil
0x18003fe4e  lea     rdx, [rbp+210h+psz]; wchar_t **
0x18003fe52  call    ?CreateMergedSandboxDir@COSInstaller@@AEAAJPEAPEA_W@Z; COSInstaller::CreateMergedSandboxDir(wchar_t * *)
0x18003fe57  mov     r15d, eax
0x18003fe5a  mov     [rsp+310h+var_2C0], eax
0x18003fe5e  test    eax, eax
0x18003fe60  jns     short loc_18003FEAA
0x18003fe62  lea     rax, aCreatemergedsa; "CreateMergedSandboxDir"
0x18003fe69  mov     [rsp+310h+var_2E8], rax
0x18003fe6e  mov     dword ptr [rsp+310h+var_2F0], r15d; int
0x18003fe73  xor     edx, edx
0x18003fe75  xor     ecx, ecx
0x18003fe77  lea     r9d, [rdx+2]
0x18003fe7b  mov     r8d, 1000h
0x18003fe81  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003fe86  mov     edx, 68Ah; void *
0x18003fe8b  mov     r12, [rbp+210h+psz]
0x18003fe8f  mov     r9d, r15d; char *
0x18003fe92  mov     rcx, [rbp+218h]; this
0x18003fe99  lea     r8, aCW1SSrcClientE_7; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18003fea0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fea5  jmp     loc_1800407AC
0x18003feaa  mov     eax, esi
0x18003feac  mov     dword ptr [rsp+310h+var_2A8+4], eax
0x18003feb0  mov     r12, [rbp+210h+psz]
0x18003feb4  test    edi, edi
0x18003feb6  jz      loc_180040762
0x18003febc  imul    r15, rax, 128h
0x18003fec3  mov     [rbp+210h+var_288], r15
0x18003fec7  mov     rbx, [r15+rbx+38h]
0x18003fecc  mov     [rbp+210h+var_268], rbx
0x18003fed0  mov     [rbp+210h+var_100], rsi
0x18003fed7  xor     edx, edx; Val
0x18003fed9  lea     r8d, [rdx+68h]; Size
0x18003fedd  lea     rcx, [rbp+210h+var_170]; void *
0x18003fee4  call    memset
0x18003fee9  lea     rax, [rbx+4]
0x18003feed  mov     [rsp+310h+rguid], rax
0x18003fef2  mov     rdx, rax; struct tagDSGlobalUpdateId *
0x18003fef5  lea     rcx, [rbp+210h+var_B0]; this
0x18003fefc  call    ??0UpdateIdToString@Trace@@QEAA@AEBUtagDSGlobalUpdateId@@@Z; Trace::UpdateIdToString::UpdateIdToString(tagDSGlobalUpdateId const &)
0x18003ff01  mov     dword ptr [rsp+310h+var_2A8], esi
0x18003ff05  mov     [rsp+310h+var_298], rsi
0x18003ff0a  mov     dword ptr [rbp+210h+var_260], esi
0x18003ff0d  mov     [rbp+210h+var_270], rsi
0x18003ff11  mov     rdi, rsi
0x18003ff14  mov     [rbp+210h+var_240], rsi
0x18003ff18  mov     r14, rsi
0x18003ff1b  mov     [rbp+210h+var_250], rsi
0x18003ff1f  mov     [rbp+210h+lpMem], rsi
0x18003ff23  xor     edx, edx
0x18003ff25  mov     ebx, edx
0x18003ff27  mov     [rbp+210h+var_248], rdx
0x18003ff2b  xorps   xmm0, xmm0
0x18003ff2e  movups  xmmword ptr [rbp+210h+Uuid.Data1], xmm0
0x18003ff35  mov     rax, [rsp+310h+var_2B8]
0x18003ff3a  mov     rcx, [r15+rax]; StringUuid
0x18003ff3e  test    rcx, rcx
0x18003ff41  jz      short loc_18003FF62
0x18003ff43  cmp     [rcx], dx
0x18003ff46  jz      short loc_18003FF62
0x18003ff48  lea     rdx, [rbp+210h+Uuid]; Uuid
0x18003ff4f  call    cs:__imp_UuidFromStringW
0x18003ff55  test    eax, eax
0x18003ff57  jnz     loc_1800403ED
0x18003ff5d  mov     rax, [rsp+310h+var_2B8]
0x18003ff62  add     r15, 20h ; ' '
0x18003ff66  add     rax, r15
0x18003ff69  mov     [rbp+210h+var_218], rax
0x18003ff6d  lea     r8, [rbp+210h+Uuid]; struct _GUID *
0x18003ff74  mov     rdx, rax; struct tagDSGlobalUpdateId *
0x18003ff77  mov     r15, [rbp+210h+var_268]
0x18003ff7b  mov     rcx, r15; struct tagDSUpdateMetadata *
0x18003ff7e  call    ?IsUUPOnPremLangSpecificChildUpdate@@YA_NAEBUtagDSUpdateMetadata@@AEBUtagDSGlobalUpdateId@@AEBU_GUID@@@Z; IsUUPOnPremLangSpecificChildUpdate(tagDSUpdateMetadata const &,tagDSGlobalUpdateId const &,_GUID const &)
0x18003ff83  test    al, al
0x18003ff85  jz      short loc_18003FFC6
0x18003ff87  mov     rdx, [rsp+310h+rguid]; struct tagDSGlobalUpdateId *
0x18003ff8c  lea     rcx, [rbp+210h+var_1E0]; this
0x18003ff90  call    ??0UpdateIdToString@Trace@@QEAA@AEBUtagDSGlobalUpdateId@@@Z; Trace::UpdateIdToString::UpdateIdToString(tagDSGlobalUpdateId const &)
0x18003ff95  mov     [rsp+310h+var_2E0], rax
0x18003ff9a  lea     rax, aSkippingMergin; "Skipping merging UUP on Prem language s"...
0x18003ffa1  mov     [rsp+310h+var_2E8], rax
0x18003ffa6  xor     esi, esi
0x18003ffa8  mov     [rsp+310h+var_2F0], rsi
0x18003ffad  xor     edx, edx
0x18003ffaf  xor     ecx, ecx
0x18003ffb1  lea     r9d, [rsi+4]
0x18003ffb5  mov     r8d, 1000h
0x18003ffbb  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003ffc0  nop
0x18003ffc1  jmp     loc_1800403CF
0x18003ffc6  lea     rax, [rbp+210h+var_270]
0x18003ffca  mov     [rsp+310h+var_2E0], rax; unsigned int *
0x18003ffcf  lea     rax, [rbp+210h+var_260]
0x18003ffd3  mov     [rsp+310h+var_2E8], rax; struct tagDSFile ***
0x18003ffd8  lea     rax, [rsp+310h+var_298]
0x18003ffdd  mov     [rsp+310h+var_2F0], rax; unsigned int *
0x18003ffe2  lea     r9, [rsp+310h+var_2A8]; struct tagDSFile **
0x18003ffe7  lea     r8, [rbp+210h+var_100]; struct tagDSFile *
0x18003ffee  mov     rdx, [r15+1D8h]; unsigned int
0x18003fff5  mov     ecx, [r15+1D0h]; this
0x18003fffc  call    ?GetFilesPerPatchType@OSDeploymentHelper@@YAJKQEAUtagDSFile@@PEAPEBU2@PEAKPEAPEAPEAU2@23@Z; OSDeploymentHelper::GetFilesPerPatchType(ulong,tagDSFile * const,tagDSFile const * *,ulong *,tagDSFile * * *,ulong *,tagDSFile * * *)
0x180040001  mov     r15d, eax
0x180040004  test    eax, eax
0x180040006  js      loc_180040699
0x18004000c  mov     rcx, [rbp+210h+var_268]
0x180040010  add     rcx, 220h; this
0x180040017  lea     rdx, [rbp+210h+var_240]; struct tagDSDataBlob *
0x18004001b  call    ?ParseHandlerXml@OSDeploymentHelper@@YAJAEBUtagDSDataBlob@@PEAPEA_W@Z; OSDeploymentHelper::ParseHandlerXml(tagDSDataBlob const &,wchar_t * *)
0x180040020  mov     r15d, eax
0x180040023  xor     edx, edx
0x180040025  test    eax, eax
0x180040027  js      loc_180040656
0x18004002d  lea     rax, [rbp+210h+var_B0]
0x180040034  mov     [rbp+210h+var_168], rax
0x18004003b  mov     r15, [rbp+210h+var_288]
0x18004003f  mov     rcx, [rsp+310h+var_2B8]
0x180040044  mov     rax, [r15+rcx+68h]
0x180040049  mov     [rbp+210h+var_160], rax
0x180040050  mov     rax, [r15+rcx+0F8h]
0x180040058  mov     [rbp+210h+var_158], rax
0x18004005f  mov     rax, [r15+rcx+100h]
0x180040067  mov     [rbp+210h+var_170], rax
0x18004006e  add     rcx, 70h ; 'p'
0x180040072  add     rcx, r15
0x180040075  mov     rax, [rbp+210h+var_150]
0x18004007c  cmp     [rcx], dl
0x18004007e  cmovnz  rax, rcx
0x180040082  mov     [rbp+210h+var_150], rax
0x180040089  xorps   xmm0, xmm0
0x18004008c  movups  xmmword ptr [rbp+210h+var_238.Data1], xmm0
0x180040090  movups  [rbp+210h+var_228], xmm0
0x180040094  mov     qword ptr [rbp+210h+var_238.Data1], rdx
0x180040098  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x18004009f  movdqu  xmmword ptr [rbp+210h+var_238.Data4], xmm1
0x1800400a4  mov     qword ptr [rbp+210h+var_228+8], rdx
0x1800400a8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex>::GetImpl(void)'::`2'::impl
0x1800400af  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_AcquireUAMutex>::__private_IsEnabled(void)
0x1800400b4  mov     rdi, [rbp+210h+var_240]
0x1800400b8  test    al, al
0x1800400ba  jz      short loc_1800400DF
0x1800400bc  mov     r8d, 493E0h; void **
0x1800400c2  mov     rdx, [rsp+310h+rguid]; rguid
0x1800400c7  lea     rcx, [rbp+210h+var_238]; this
0x1800400cb  call    ?Acquire@SandboxAccessMutexGuard@OSDeploymentHelper@@QEAAJAEBU_GUID@@K@Z; OSDeploymentHelper::SandboxAccessMutexGuard::Acquire(_GUID const &,ulong)
0x1800400d0  mov     r15d, eax
0x1800400d3  test    eax, eax
0x1800400d5  js      loc_180040410
0x1800400db  mov     r15, [rbp+210h+var_288]
0x1800400df  lea     rax, [rbp+210h+var_170]
0x1800400e6  mov     [rsp+310h+rguid], rax
0x1800400eb  movups  xmm0, xmmword ptr cs:Buf1.Data1
0x1800400f2  movdqu  xmmword ptr [rbp+210h+var_1F8.Data1], xmm0
0x1800400f7  mov     [rbp+210h+var_268], rdi
0x1800400fb  mov     rax, [rbp+210h+var_100]
0x180040102  xor     ebx, ebx
0x180040104  test    rax, rax
0x180040107  jnz     short loc_18004010D
0x180040109  mov     eax, ebx
0x18004010b  jmp     short loc_180040111
0x18004010d  mov     rax, [rax+48h]
0x180040111  mov     [rbp+210h+var_260], rax
0x180040115  mov     rax, [rsp+310h+var_2B8]
0x18004011a  add     rax, 10h
0x18004011e  add     rax, r15
0x180040121  mov     [rbp+210h+var_290], rax
0x180040125  lea     rcx, [rsp+310h+rguid]
0x18004012a  mov     [rsp+310h+var_2D0], rcx
0x18004012f  lea     rcx, [rbp+210h+var_1F8]
0x180040133  mov     [rsp+310h+var_2E0], rcx
0x180040138  lea     rcx, [rsp+310h+var_298]
0x18004013d  mov     [rsp+310h+var_2E8], rcx
0x180040142  lea     rcx, [rsp+310h+var_2A8]
0x180040147  mov     [rsp+310h+var_2F0], rcx; int
0x18004014c  lea     r9, [rbp+210h+var_268]
0x180040150  lea     r8, [rbp+210h+var_260]
0x180040154  mov     rdx, rax
0x180040157  lea     rcx, [rbp+210h+var_248]
0x18004015b  call    ??$MakeAndInitialize@VCDeploymentSessionWrapper@OSDeploymentHelper@@V12@AEBQEA_WAEBQEA_WAEBQEA_WH$$TU_GUID@@AEBKPEAUtagOptionalSessionInfo5@@@Details@WRL@Microsoft@@YAJPEAPEAVCDeploymentSessionWrapper@OSDeploymentHelper@@AEBQEA_W11$$QEAH$$QEA$$T$$QEAU_GUID@@AEBK$$QEAPEAUtagOptionalSessionInfo5@@@Z; Microsoft::WRL::Details::MakeAndInitialize<OSDeploymentHelper::CDeploymentSessionWrapper,OSDeploymentHelper::CDeploymentSessionWrapper,wchar_t * const &,wchar_t * const &,wchar_t * const &,int,std::nullptr_t,_GUID,ulong const &,tagOptionalSessionInfo5 *>(OSDeploymentHelper::CDeploymentSessionWrapper * *,wchar_t * const &,wchar_t * const &,wchar_t * const &,int &&,$$T$$QEAU_GUID &&,ulong const &,tagOptionalSessionInfo5 * &&)
0x180040160  mov     r15d, eax
0x180040163  mov     rbx, [rbp+210h+var_248]
0x180040167  test    eax, eax
0x180040169  js      loc_180040636
0x18004016f  lea     rcx, [rbx+8]
0x180040173  mov     rax, [rcx]
0x180040176  mov     rdx, r12
0x180040179  mov     rax, [rax+48h]
0x18004017d  call    _guard_dispatch_icall
0x180040182  mov     [rsp+310h+var_2C0], eax
0x180040186  mov     r15, [rbp+210h+var_288]
0x18004018a  test    eax, eax
0x18004018c  mov     rax, [rsp+310h+var_2B8]
0x180040191  mov     rdx, [r15+rax+38h]
0x180040196  jns     loc_18004023B
0x18004019c  mov     r15d, [rdx+14h]
0x1800401a0  add     rdx, 4; struct _GUID *
0x1800401a4  lea     rcx, [rbp+210h+var_1E0]; this
0x1800401a8  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x1800401ad  mov     [rsp+310h+var_2D8], r15d
0x1800401b2  mov     [rsp+310h+var_2E0], rax
0x1800401b7  lea     rax, aMergeFailedFor; "Merge failed for update ID: %ws.%d"
0x1800401be  mov     [rsp+310h+var_2E8], rax
0x1800401c3  mov     r15d, [rsp+310h+var_2C0]
0x1800401c8  mov     dword ptr [rsp+310h+var_2F0], r15d
0x1800401cd  xor     edx, edx
0x1800401cf  xor     ecx, ecx
0x1800401d1  lea     r9d, [rdx+3]
0x1800401d5  mov     r8d, 1000h
0x1800401db  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800401e0  cmp     r15d, 8024B104h
0x1800401e7  jnz     loc_18004041A
0x1800401ed  lea     rax, aContinuingTheM; "Continuing the merge operation"
0x1800401f4  mov     [rsp+310h+var_2E8], rax
0x1800401f9  xor     esi, esi
0x1800401fb  mov     [rsp+310h+var_2F0], rsi
0x180040200  xor     edx, edx
0x180040202  xor     ecx, ecx
0x180040204  lea     r9d, [rsi+4]
0x180040208  mov     r8d, 1000h
0x18004020e  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180040213  mov     [rsp+310h+var_2C0], esi
0x180040217  lea     rcx, [rbp+210h+var_238]; this
0x18004021b  call    ??1SandboxAccessMutexGuard@OSDeploymentHelper@@QEAA@XZ; OSDeploymentHelper::SandboxAccessMutexGuard::~SandboxAccessMutexGuard(void)
0x180040220  nop
0x180040221  test    rbx, rbx
0x180040224  jz      short loc_180040236
0x180040226  mov     rax, [rbx]
0x180040229  mov     rcx, rbx
0x18004022c  mov     rax, [rax+10h]
0x180040230  call    _guard_dispatch_icall
0x180040235  nop
0x180040236  jmp     loc_1800403A3
0x18004023b  mov     rcx, [rbp+210h+var_F8]
0x180040242  add     rcx, 78h ; 'x'
0x180040246  add     rdx, 4
0x18004024a  mov     rax, [rcx]
0x18004024d  xor     r8d, r8d
0x180040250  mov     rax, [rax+8]
0x180040254  call    _guard_dispatch_icall
0x180040259  mov     rcx, [rbp+210h+var_F8]
0x180040260  add     rcx, 90h
0x180040267  mov     rax, [rcx]
0x18004026a  xor     r8d, r8d
0x18004026d  mov     rdx, [rbp+210h+var_218]
0x180040271  mov     rax, [rax+8]
0x180040275  call    _guard_dispatch_icall
0x18004027a  mov     rcx, r12; psz
0x18004027d  call    cs:__imp_SysAllocString
0x180040283  mov     rdx, [rsp+310h+var_2B8]
0x180040288  mov     [r15+rdx+18h], rax
0x18004028d  test    rax, rax
0x180040290  jz      loc_180040629
0x180040296  lea     r8, [rbp+210h+var_250]; wchar_t **
  ... truncated ...
```
