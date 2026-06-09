# ServiceManager::LogOperationEndTelemetry(long)

- ea: `0x180017220`
- end: `0x180017df7`
- name: `?LogOperationEndTelemetry@ServiceManager@@AEAAXJ@Z`
- size: `3031`
- prototype: `void __fastcall(ServiceManager *this, int)`
- caller_count: `1`
- callee_count: `29`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800142c4`

## callees

- `0x180003410`
- `0x180003f7c`
- `0x180009d0c`
- `0x180009db4`
- `0x18000f67c`
- `0x18000f6a8`
- `0x18000f6d4`
- `0x180017220`
- `0x180018a20`
- `0x180018b38`
- `0x180018c50`
- `0x180018d68`
- `0x180018e80`
- `0x180018fa8`
- `0x1800190d0`
- `0x180019310`
- `0x180019428`
- `0x180019540`
- `0x180019678`
- `0x1800197c8`
- `0x18001992c`
- `0x180019a90`
- `0x18001a140`
- `0x18001a214`
- `0x18001a2e8`
- `0x18001a748`
- `0x18001a850`
- `0x18001a968`
- `0x18001aa80`

## import_xrefs

- `MosStorage!MosStorageGetCurrentLocation` at `0x180017269`
- `MosStorage!MosStorageGetCurrentLocation` at `0x180017269`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180017288`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180017288`

## string_xrefs

- `0x180017279`: `ServiceManager::LogOperationEndTelemetry`

## pseudocode

```c
void __fastcall ServiceManager::LogOperationEndTelemetry(ServiceManager *this, int a2)
{
  int CurrentLocation; // eax
  int v5; // ecx
  int v6; // edx
  int v7; // edx
  int v8; // edx
  int v9; // edi
  bool v10; // si
  OfflineMapsTelemetry *v11; // rax
  bool v12; // di
  int v13; // esi
  PackageManager *v14; // rcx
  int v15; // r14d
  PackageManager *v16; // rcx
  unsigned int v17; // eax
  unsigned int v18; // r12d
  unsigned int v19; // r15d
  OfflineMapsTelemetry *v20; // rax
  int v21; // edi
  bool v22; // si
  int v23; // r14d
  PackageManager *v24; // rcx
  int v25; // r15d
  PackageManager *v26; // rcx
  unsigned int v27; // eax
  unsigned int v28; // r13d
  unsigned int v29; // r12d
  OfflineMapsTelemetry *v30; // rax
  int v31; // edx
  int v32; // edx
  int v33; // esi
  int v34; // ecx
  bool v35; // r14
  OfflineMapsTelemetry *v36; // rax
  bool v37; // r14
  OfflineMapsTelemetry *v38; // rax
  bool v39; // r14
  OfflineMapsTelemetry *v40; // rax
  int v41; // ecx
  bool v42; // zf
  char *v43; // rcx
  bool v44; // si
  int v45; // r14d
  PackageManager *v46; // rcx
  int v47; // r15d
  PackageManager *v48; // rcx
  unsigned int v49; // eax
  unsigned int v50; // r13d
  unsigned int v51; // r12d
  OfflineMapsTelemetry *v52; // rax
  bool v53; // si
  int CurrentOperationTrigger; // r14d
  PackageManager *v55; // rcx
  int CurrentOperationInfo; // r15d
  PackageManager *v57; // rcx
  unsigned int CurrentPackageSizeInKB; // eax
  unsigned int v59; // r13d
  unsigned int v60; // r12d
  OfflineMapsTelemetry *v61; // rax
  bool v62; // si
  int v63; // r14d
  PackageManager *v64; // rcx
  int v65; // r15d
  PackageManager *v66; // rcx
  unsigned int v67; // eax
  unsigned int v68; // r13d
  unsigned int v69; // r12d
  OfflineMapsTelemetry *v70; // rax
  int v71; // esi
  int v72; // ecx
  char *v73; // rcx
  bool v74; // r14
  int v75; // r15d
  PackageManager *v76; // rcx
  int v77; // r12d
  PackageManager *v78; // rcx
  unsigned int v79; // r13d
  OfflineMapsTelemetry *v80; // rax
  bool v81; // r14
  int v82; // r15d
  PackageManager *v83; // rcx
  int v84; // r12d
  PackageManager *v85; // rcx
  unsigned int v86; // r13d
  OfflineMapsTelemetry *v87; // rax
  bool v88; // r14
  int v89; // r15d
  PackageManager *v90; // rcx
  int v91; // r12d
  PackageManager *v92; // rcx
  unsigned int v93; // r13d
  OfflineMapsTelemetry *v94; // rax
  int v95; // ecx
  int v96; // ecx
  bool v97; // di
  OfflineMapsTelemetry *v98; // rax
  bool v99; // di
  int v100; // esi
  PackageManager *v101; // rcx
  int v102; // r14d
  PackageManager *v103; // rcx
  unsigned int v104; // eax
  unsigned int v105; // r12d
  unsigned int v106; // r15d
  OfflineMapsTelemetry *v107; // rax
  bool v108; // di
  int v109; // esi
  PackageManager *v110; // rcx
  int v111; // r14d
  PackageManager *v112; // rcx
  unsigned int v113; // eax
  unsigned int v114; // r12d
  unsigned int v115; // r15d
  OfflineMapsTelemetry *v116; // rax
  bool v117; // di
  OfflineMapsTelemetry *v118; // rax
  bool v119; // di
  int v120; // esi
  PackageManager *v121; // rcx
  int v122; // r14d
  PackageManager *v123; // rcx
  unsigned int v124; // eax
  unsigned int v125; // r12d
  unsigned int v126; // r15d
  OfflineMapsTelemetry *v127; // rax
  bool v128; // di
  int v129; // esi
  PackageManager *v130; // rcx
  int v131; // r14d
  PackageManager *v132; // rcx
  unsigned int v133; // eax
  unsigned int v134; // r12d
  unsigned int v135; // r15d
  OfflineMapsTelemetry *v136; // rax
  bool v137; // di
  OfflineMapsTelemetry *v138; // rax
  bool v139; // di
  int v140; // esi
  PackageManager *v141; // rcx
  int v142; // r14d
  PackageManager *v143; // rcx
  unsigned int v144; // eax
  unsigned int v145; // r12d
  unsigned int v146; // r15d
  OfflineMapsTelemetry *v147; // rax
  bool v148; // di
  int v149; // esi
  PackageManager *v150; // rcx
  int v151; // r14d
  PackageManager *v152; // rcx
  unsigned int v153; // eax
  unsigned int v154; // r12d
  unsigned int v155; // r15d
  OfflineMapsTelemetry *v156; // rax
  unsigned int v157; // [rsp+60h] [rbp-A0h]
  unsigned int v158; // [rsp+60h] [rbp-A0h]
  unsigned int v159; // [rsp+60h] [rbp-A0h]
  _BYTE v160[4]; // [rsp+70h] [rbp-90h] BYREF
  int v161; // [rsp+74h] [rbp-8Ch]
  unsigned int v162; // [rsp+284h] [rbp+184h]
  unsigned int v163; // [rsp+6D0h] [rbp+5D0h]

  memset_0(v160, 0, 0x670u);
  CurrentLocation = MosStorageGetCurrentLocation((struct _STORAGE_DEVICE_DATA *)v160);
  if ( CurrentLocation < 0 )
    ZTraceReportIgnore(CurrentLocation, "ServiceManager::LogOperationEndTelemetry", 487, this);
  v5 = *((_DWORD *)this + 881);
  if ( (unsigned int)(v5 - 5) > 1 )
  {
    v6 = *((_DWORD *)this + 880);
    if ( a2 < 0 )
    {
      v31 = v6 - 1;
      if ( v31 )
      {
        v32 = v31 - 1;
        if ( v32 )
        {
          if ( v32 == 1 )
          {
            v33 = *((_DWORD *)this + 1090);
            v34 = v5 - 3;
            if ( v34 )
            {
              if ( v34 == 1 )
              {
                v37 = v161 != 0;
                if ( OfflineMapsTelemetry::IsEnabled() )
                {
                  v38 = OfflineMapsTelemetry::Instance();
                  OfflineMapsTelemetry::OfflineUpdateFailedBing_(
                    v38,
                    *(struct _FILETIME *)((char *)this + 4332),
                    *((_QWORD *)this + 543),
                    v37,
                    v162,
                    v163,
                    v33,
                    a2);
                }
              }
              else
              {
                v35 = v161 != 0;
                if ( OfflineMapsTelemetry::IsEnabled() )
                {
                  v36 = OfflineMapsTelemetry::Instance();
                  OfflineMapsTelemetry::OfflineUpdateFailed_(
                    v36,
                    *(struct _FILETIME *)((char *)this + 4332),
                    *((_QWORD *)this + 543),
                    v35,
                    v162,
                    v163,
                    v33,
                    a2);
                }
              }
            }
            else
            {
              v39 = v161 != 0;
              if ( OfflineMapsTelemetry::IsEnabled() )
              {
                v40 = OfflineMapsTelemetry::Instance();
                OfflineMapsTelemetry::OfflineUpdateFailedMos_(
                  v40,
                  *(struct _FILETIME *)((char *)this + 4332),
                  *((_QWORD *)this + 543),
                  v39,
                  v162,
                  v163,
                  v33,
                  a2);
              }
            }
          }
        }
        else
        {
          v41 = v5 - 3;
          if ( v41 )
          {
            v42 = v41 == 1;
            v43 = (char *)this + 3568;
            if ( v42 )
            {
              v53 = v161 != 0;
              CurrentOperationTrigger = PackageManager::GetCurrentOperationTrigger(v43);
              CurrentOperationInfo = PackageManager::GetCurrentOperationInfo(v55);
              CurrentPackageSizeInKB = PackageManager::GetCurrentPackageSizeInKB(v57);
              v59 = *((_DWORD *)this + 952);
              v60 = CurrentPackageSizeInKB;
              if ( OfflineMapsTelemetry::IsEnabled() )
              {
                v61 = OfflineMapsTelemetry::Instance();
                OfflineMapsTelemetry::OfflineDeleteFailedBing_(
                  v61,
                  v59,
                  v60,
                  CurrentOperationInfo,
                  CurrentOperationTrigger,
                  *(struct _FILETIME *)((char *)this + 4332),
                  *((_QWORD *)this + 543),
                  v53,
                  v162,
                  v163,
                  a2);
              }
            }
            else
            {
              v44 = v161 != 0;
              v45 = PackageManager::GetCurrentOperationTrigger(v43);
              v47 = PackageManager::GetCurrentOperationInfo(v46);
              v49 = PackageManager::GetCurrentPackageSizeInKB(v48);
              v50 = *((_DWORD *)this + 952);
              v51 = v49;
              if ( OfflineMapsTelemetry::IsEnabled() )
              {
                v52 = OfflineMapsTelemetry::Instance();
                OfflineMapsTelemetry::OfflineDeleteFailed_(
                  v52,
                  v50,
                  v51,
                  v47,
                  v45,
                  *(struct _FILETIME *)((char *)this + 4332),
                  *((_QWORD *)this + 543),
                  v44,
                  v162,
                  v163,
                  a2);
              }
            }
          }
          else
          {
            v62 = v161 != 0;
            v63 = PackageManager::GetCurrentOperationTrigger((char *)this + 3568);
            v65 = PackageManager::GetCurrentOperationInfo(v64);
            v67 = PackageManager::GetCurrentPackageSizeInKB(v66);
            v68 = *((_DWORD *)this + 952);
            v69 = v67;
            if ( OfflineMapsTelemetry::IsEnabled() )
            {
              v70 = OfflineMapsTelemetry::Instance();
              OfflineMapsTelemetry::OfflineDeleteFailedMos_(
                v70,
                v68,
                v69,
                v65,
                v63,
                *(struct _FILETIME *)((char *)this + 4332),
                *((_QWORD *)this + 543),
                v62,
                v162,
                v163,
                a2);
            }
          }
        }
      }
      else
      {
        v71 = *((_DWORD *)this + 1090);
        v72 = v5 - 3;
        if ( v72 )
        {
          v42 = v72 == 1;
          v73 = (char *)this + 3568;
          if ( v42 )
          {
            v81 = v161 != 0;
            v82 = PackageManager::GetCurrentOperationTrigger(v73);
            v84 = PackageManager::GetCurrentOperationInfo(v83);
            v86 = PackageManager::GetCurrentPackageSizeInKB(v85);
            v158 = *((_DWORD *)this + 952);
            if ( OfflineMapsTelemetry::IsEnabled() )
            {
              v87 = OfflineMapsTelemetry::Instance();
              OfflineMapsTelemetry::OfflineDownloadFailedBing_(
                v87,
                v158,
                v86,
                v84,
                v82,
                *(struct _FILETIME *)((char *)this + 4332),
                *((_QWORD *)this + 543),
                v81,
                v162,
                v163,
                v71,
                a2);
            }
          }
          else
          {
            v74 = v161 != 0;
            v75 = PackageManager::GetCurrentOperationTrigger(v73);
            v77 = PackageManager::GetCurrentOperationInfo(v76);
            v79 = PackageManager::GetCurrentPackageSizeInKB(v78);
            v157 = *((_DWORD *)this + 952);
            if ( OfflineMapsTelemetry::IsEnabled() )
            {
              v80 = OfflineMapsTelemetry::Instance();
              OfflineMapsTelemetry::OfflineDownloadFailed_(
                v80,
                v157,
                v79,
                v77,
                v75,
                *(struct _FILETIME *)((char *)this + 4332),
                *((_QWORD *)this + 543),
                v74,
                v162,
                v163,
                v71,
                a2);
            }
          }
        }
        else
        {
          v88 = v161 != 0;
          v89 = PackageManager::GetCurrentOperationTrigger((char *)this + 3568);
          v91 = PackageManager::GetCurrentOperationInfo(v90);
          v93 = PackageManager::GetCurrentPackageSizeInKB(v92);
          v159 = *((_DWORD *)this + 952);
          if ( OfflineMapsTelemetry::IsEnabled() )
          {
            v94 = OfflineMapsTelemetry::Instance();
            OfflineMapsTelemetry::OfflineDownloadFailedMos_(
              v94,
              v159,
              v93,
              v91,
              v89,
              *(struct _FILETIME *)((char *)this + 4332),
              *((_QWORD *)this + 543),
              v88,
              v162,
              v163,
              v71,
              a2);
          }
        }
      }
    }
    else
    {
      v7 = v6 - 1;
      if ( v7 )
      {
        v8 = v7 - 1;
        if ( v8 )
        {
          if ( v8 == 1 )
          {
            v9 = *((_DWORD *)this + 1090);
            v10 = v161 != 0;
            if ( OfflineMapsTelemetry::IsEnabled() )
            {
              v11 = OfflineMapsTelemetry::Instance();
              OfflineMapsTelemetry::OfflineUpdateComplete_(
                v11,
                *(struct _FILETIME *)((char *)this + 4332),
                *((_QWORD *)this + 543),
                v10,
                v162,
                v163,
                v9);
            }
          }
        }
        else
        {
          v12 = v161 != 0;
          v13 = PackageManager::GetCurrentOperationTrigger((char *)this + 3568);
          v15 = PackageManager::GetCurrentOperationInfo(v14);
          v17 = PackageManager::GetCurrentPackageSizeInKB(v16);
          v18 = *((_DWORD *)this + 952);
          v19 = v17;
          if ( OfflineMapsTelemetry::IsEnabled() )
          {
            v20 = OfflineMapsTelemetry::Instance();
            OfflineMapsTelemetry::OfflineDeleteComplete_(
              v20,
              v18,
              v19,
              v15,
              v13,
              *(struct _FILETIME *)((char *)this + 4332),
              *((_QWORD *)this + 543),
              v12,
              v162,
              v163);
          }
        }
      }
      else
      {
        v21 = *((_DWORD *)this + 1090);
        v22 = v161 != 0;
        v23 = PackageManager::GetCurrentOperationTrigger((char *)this + 3568);
        v25 = PackageManager::GetCurrentOperationInfo(v24);
        v27 = PackageManager::GetCurrentPackageSizeInKB(v26);
        v28 = *((_DWORD *)this + 952);
        v29 = v27;
        if ( OfflineMapsTelemetry::IsEnabled() )
        {
          v30 = OfflineMapsTelemetry::Instance();
          OfflineMapsTelemetry::OfflineDownloadComplete_(
            v30,
            v28,
            v29,
            v25,
            v23,
            *(struct _FILETIME *)((char *)this + 4332),
            *((_QWORD *)this + 543),
            v22,
            v162,
            v163,
            v21);
        }
      }
    }
    return;
  }
  v95 = *((_DWORD *)this + 883);
  if ( !v95 )
  {
LABEL_62:
    switch ( *((_DWORD *)this + 880) )
    {
      case 1:
        v148 = v161 != 0;
        v149 = PackageManager::GetCurrentOperationTrigger((char *)this + 3568);
        v151 = PackageManager::GetCurrentOperationInfo(v150);
        v153 = PackageManager::GetCurrentPackageSizeInKB(v152);
        v154 = *((_DWORD *)this + 952);
        v155 = v153;
        if ( OfflineMapsTelemetry::IsEnabled() )
        {
          v156 = OfflineMapsTelemetry::Instance();
          OfflineMapsTelemetry::OfflineDownloadCanceledUser_(
            v156,
            v154,
            v155,
            v151,
            v149,
            *(struct _FILETIME *)((char *)this + 4332),
            *((_QWORD *)this + 543),
            v148,
            v162,
            v163);
        }
        break;
      case 2:
        v139 = v161 != 0;
        v140 = PackageManager::GetCurrentOperationTrigger((char *)this + 3568);
        v142 = PackageManager::GetCurrentOperationInfo(v141);
        v144 = PackageManager::GetCurrentPackageSizeInKB(v143);
        v145 = *((_DWORD *)this + 952);
        v146 = v144;
        if ( OfflineMapsTelemetry::IsEnabled() )
        {
          v147 = OfflineMapsTelemetry::Instance();
          OfflineMapsTelemetry::OfflineDeleteCanceledUser_(
            v147,
            v145,
            v146,
            v142,
            v140,
            *(struct _FILETIME *)((char *)this + 4332),
            *((_QWORD *)this + 543),
            v139,
            v162,
            v163);
        }
        break;
      case 3:
        v137 = v161 != 0;
        if ( OfflineMapsTelemetry::IsEnabled() )
        {
          v138 = OfflineMapsTelemetry::Instance();
          OfflineMapsTelemetry::OfflineMapUpdateCanceledUser_(
            v138,
            *(struct _FILETIME *)((char *)this + 4332),
            *((_QWORD *)this + 543),
            v137,
            v162,
            v163);
        }
        break;
    }
    return;
  }
  v96 = v95 - 1;
  if ( v96 )
  {
    if ( v96 == 1 )
    {
      switch ( *((_DWORD *)this + 880) )
      {
        case 1:
          v108 = v161 != 0;
          v109 = PackageManager::GetCurrentOperationTrigger((char *)this + 3568);
          v111 = PackageManager::GetCurrentOperationInfo(v110);
          v113 = PackageManager::GetCurrentPackageSizeInKB(v112);
          v114 = *((_DWORD *)this + 952);
          v115 = v113;
          if ( OfflineMapsTelemetry::IsEnabled() )
          {
            v116 = OfflineMapsTelemetry::Instance();
            OfflineMapsTelemetry::OfflineDownloadCanceledSuspended_(
              v116,
              v114,
              v115,
              v111,
              v109,
              *(struct _FILETIME *)((char *)this + 4332),
              *((_QWORD *)this + 543),
              v108,
              v162,
              v163);
          }
          break;
        case 2:
          v99 = v161 != 0;
          v100 = PackageManager::GetCurrentOperationTrigger((char *)this + 3568);
          v102 = PackageManager::GetCurrentOperationInfo(v101);
          v104 = PackageManager::GetCurrentPackageSizeInKB(v103);
          v105 = *((_DWORD *)this + 952);
          v106 = v104;
          if ( OfflineMapsTelemetry::IsEnabled() )
          {
            v107 = OfflineMapsTelemetry::Instance();
            OfflineMapsTelemetry::OfflineDeleteCanceledSuspended_(
              v107,
              v105,
              v106,
              v102,
              v100,
              *(struct _FILETIME *)((char *)this + 4332),
              *((_QWORD *)this + 543),
              v99,
              v162,
              v163);
          }
          break;
        case 3:
          v97 = v161 != 0;
          if ( OfflineMapsTelemetry::IsEnabled() )
          {
            v98 = OfflineMapsTelemetry::Instance();
            OfflineMapsTelemetry::OfflineMapUpdateCanceledSuspended_(
              v98,
              *(struct _FILETIME *)((char *)this + 4332),
              *((_QWORD *)this + 543),
              v97,
              v162,
              v163);
          }
          break;
      }
      return;
    }
    goto LABEL_62;
  }
  switch ( *((_DWORD *)this + 880) )
  {
    case 1:
      v128 = v161 != 0;
      v129 = PackageManager::GetCurrentOperationTrigger((char *)this + 3568);
      v131 = PackageManager::GetCurrentOperationInfo(v130);
      v133 = PackageManager::GetCurrentPackageSizeInKB(v132);
      v134 = *((_DWORD *)this + 952);
      v135 = v133;
      if ( OfflineMapsTelemetry::IsEnabled() )
      {
        v136 = OfflineMapsTelemetry::Instance();
        OfflineMapsTelemetry::OfflineDownloadCanceledPaused_(
          v136,
          v134,
          v135,
          v131,
          v129,
          *(struct _FILETIME *)((char *)this + 4332),
          *((_QWORD *)this + 543),
          v128,
          v162,
          v163);
      }
      break;
    case 2:
      v119 = v161 != 0;
      v120 = PackageManager::GetCurrentOperationTrigger((char *)this + 3568);
      v122 = PackageManager::GetCurrentOperationInfo(v121);
      v124 = PackageManager::GetCurrentPackageSizeInKB(v123);
      v125 = *((_DWORD *)this + 952);
      v126 = v124;
      if ( OfflineMapsTelemetry::IsEnabled() )
      {
        v127 = OfflineMapsTelemetry::Instance();
        OfflineMapsTelemetry::OfflineDeleteCanceledPaused_(
          v127,
          v125,
          v126,
          v122,
          v120,
          *(struct _FILETIME *)((char *)this + 4332),
          *((_QWORD *)this + 543),
          v119,
          v162,
          v163);
      }
      break;
    case 3:
      v117 = v161 != 0;
      if ( OfflineMapsTelemetry::IsEnabled() )
      {
        v118 = OfflineMapsTelemetry::Instance();
        OfflineMapsTelemetry::OfflineMapUpdateCanceledPaused_(
          v118,
          *(struct _FILETIME *)((char *)this + 4332),
          *((_QWORD *)this + 543),
          v117,
          v162,
          v163);
      }
      break;
  }
}

```

## disassembly

```asm
0x180017220  push    rbp
0x180017222  push    rbx
0x180017223  push    rsi
0x180017224  push    rdi
0x180017225  push    r12
0x180017227  push    r13
0x180017229  push    r14
0x18001722b  push    r15
0x18001722d  lea     rbp, [rsp-5F8h]
0x180017235  sub     rsp, 6F8h
0x18001723c  mov     rax, cs:__security_cookie
0x180017243  xor     rax, rsp
0x180017246  mov     [rbp+630h+var_50], rax
0x18001724d  mov     edi, edx
0x18001724f  mov     rbx, rcx
0x180017252  xor     edx, edx; Val
0x180017254  lea     rcx, [rsp+730h+var_6C0]; void *
0x180017259  mov     r8d, 670h; Size
0x18001725f  call    memset_0
0x180017264  lea     rcx, [rsp+730h+var_6C0]
0x180017269  call    cs:__imp_?MosStorageGetCurrentLocation@@YAJPEAU_STORAGE_DEVICE_DATA@@@Z; MosStorageGetCurrentLocation(_STORAGE_DEVICE_DATA *)
0x18001726f  xor     r13d, r13d
0x180017272  test    eax, eax
0x180017274  jns     short loc_18001728E
0x180017276  mov     r9, rbx
0x180017279  lea     rdx, aServicemanager_19; "ServiceManager::LogOperationEndTelemetr"...
0x180017280  mov     r8d, 1E7h
0x180017286  mov     ecx, eax
0x180017288  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x18001728e  mov     ecx, [rbx+0DC4h]; unsigned __int8
0x180017294  lea     eax, [rcx-5]
0x180017297  cmp     eax, 1
0x18001729a  jbe     loc_180017925
0x1800172a0  mov     edx, [rbx+0DC0h]
0x1800172a6  test    edi, edi
0x1800172a8  js      loc_180017446
0x1800172ae  sub     edx, 1
0x1800172b1  jz      loc_1800173AB
0x1800172b7  sub     edx, 1; unsigned __int64
0x1800172ba  jz      short loc_18001731C
0x1800172bc  cmp     edx, 1
0x1800172bf  jnz     loc_180017DD4
0x1800172c5  cmp     [rsp+730h+var_6BC], r13d
0x1800172ca  mov     edi, [rbx+1108h]
0x1800172d0  setnz   sil
0x1800172d4  call    ?IsEnabled@OfflineMapsTelemetry@@SA_NE_K@Z; OfflineMapsTelemetry::IsEnabled(uchar,unsigned __int64)
0x1800172d9  test    al, al
0x1800172db  jz      loc_180017DD4
0x1800172e1  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x1800172e6  mov     ecx, [rbp+630h+var_60]
0x1800172ec  mov     r9b, sil; bool
0x1800172ef  mov     r8, [rbx+10F8h]; unsigned __int64
0x1800172f6  mov     rdx, [rbx+10ECh]; struct _FILETIME
0x1800172fd  mov     dword ptr [rsp+730h+var_700], edi; int
0x180017301  mov     [rsp+730h+var_708.dwLowDateTime], ecx; unsigned int
0x180017305  mov     ecx, [rbp+630h+var_4AC]
0x18001730b  mov     [rsp+730h+var_710], ecx; unsigned int
0x18001730f  mov     rcx, rax; this
0x180017312  call    ?OfflineUpdateComplete_@OfflineMapsTelemetry@@QEAAXU_FILETIME@@_K_NIIH@Z; OfflineMapsTelemetry::OfflineUpdateComplete_(_FILETIME,unsigned __int64,bool,uint,uint,int)
0x180017317  jmp     loc_180017DD4
0x18001731c  cmp     [rsp+730h+var_6BC], r13d
0x180017321  lea     rcx, [rbx+0DF0h]
0x180017328  setnz   dil
0x18001732c  call    ?GetCurrentOperationTrigger@PackageManager@@QEAA?AW4MapsOperationTrigger@@XZ; PackageManager::GetCurrentOperationTrigger(void)
0x180017331  mov     esi, eax
0x180017333  call    ?GetCurrentOperationInfo@PackageManager@@QEAAKXZ; PackageManager::GetCurrentOperationInfo(void)
0x180017338  mov     r14d, eax
0x18001733b  call    ?GetCurrentPackageSizeInKB@PackageManager@@QEAAIXZ; PackageManager::GetCurrentPackageSizeInKB(void)
0x180017340  mov     r12d, [rbx+0EE0h]
0x180017347  mov     r15d, eax
0x18001734a  call    ?IsEnabled@OfflineMapsTelemetry@@SA_NE_K@Z; OfflineMapsTelemetry::IsEnabled(uchar,unsigned __int64)
0x18001734f  test    al, al
0x180017351  jz      loc_180017DD4
0x180017357  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x18001735c  mov     r8d, [rbp+630h+var_60]
0x180017363  mov     r9d, r14d; int
0x180017366  mov     rcx, [rbx+10ECh]
0x18001736d  mov     edx, r12d; unsigned int
0x180017370  mov     [rsp+730h+var_6E8], r8d; unsigned int
0x180017375  mov     r8d, [rbp+630h+var_4AC]
0x18001737c  mov     [rsp+730h+var_6F0], r8d; unsigned int
0x180017381  mov     r8, [rbx+10F8h]
0x180017388  mov     [rsp+730h+var_6F8], dil; bool
0x18001738d  mov     [rsp+730h+var_700], r8; unsigned __int64
0x180017392  mov     r8d, r15d; unsigned int
0x180017395  mov     qword ptr [rsp+730h+var_708.dwLowDateTime], rcx; struct _FILETIME
0x18001739a  mov     rcx, rax; this
0x18001739d  mov     [rsp+730h+var_710], esi; int
0x1800173a1  call    ?OfflineDeleteComplete_@OfflineMapsTelemetry@@QEAAXIIHHU_FILETIME@@_K_NII@Z; OfflineMapsTelemetry::OfflineDeleteComplete_(uint,uint,int,int,_FILETIME,unsigned __int64,bool,uint,uint)
0x1800173a6  jmp     loc_180017DD4
0x1800173ab  cmp     [rsp+730h+var_6BC], r13d
0x1800173b0  lea     rcx, [rbx+0DF0h]
0x1800173b7  mov     edi, [rbx+1108h]
0x1800173bd  setnz   sil
0x1800173c1  call    ?GetCurrentOperationTrigger@PackageManager@@QEAA?AW4MapsOperationTrigger@@XZ; PackageManager::GetCurrentOperationTrigger(void)
0x1800173c6  mov     r14d, eax
0x1800173c9  call    ?GetCurrentOperationInfo@PackageManager@@QEAAKXZ; PackageManager::GetCurrentOperationInfo(void)
0x1800173ce  mov     r15d, eax
0x1800173d1  call    ?GetCurrentPackageSizeInKB@PackageManager@@QEAAIXZ; PackageManager::GetCurrentPackageSizeInKB(void)
0x1800173d6  mov     r13d, [rbx+0EE0h]
0x1800173dd  mov     r12d, eax
0x1800173e0  call    ?IsEnabled@OfflineMapsTelemetry@@SA_NE_K@Z; OfflineMapsTelemetry::IsEnabled(uchar,unsigned __int64)
0x1800173e5  test    al, al
0x1800173e7  jz      loc_180017DD4
0x1800173ed  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x1800173f2  mov     r8d, [rbp+630h+var_60]
0x1800173f9  mov     r9d, r15d; int
0x1800173fc  mov     rcx, [rbx+10ECh]
0x180017403  mov     edx, r13d; unsigned int
0x180017406  mov     [rsp+730h+var_6E0], edi; int
0x18001740a  mov     [rsp+730h+var_6E8], r8d; unsigned int
0x18001740f  mov     r8d, [rbp+630h+var_4AC]
0x180017416  mov     [rsp+730h+var_6F0], r8d; unsigned int
0x18001741b  mov     r8, [rbx+10F8h]
0x180017422  mov     [rsp+730h+var_6F8], sil; bool
0x180017427  mov     [rsp+730h+var_700], r8; unsigned __int64
0x18001742c  mov     r8d, r12d; unsigned int
0x18001742f  mov     qword ptr [rsp+730h+var_708.dwLowDateTime], rcx; struct _FILETIME
0x180017434  mov     rcx, rax; this
0x180017437  mov     [rsp+730h+var_710], r14d; int
0x18001743c  call    ?OfflineDownloadComplete_@OfflineMapsTelemetry@@QEAAXIIHHU_FILETIME@@_K_NIIH@Z; OfflineMapsTelemetry::OfflineDownloadComplete_(uint,uint,int,int,_FILETIME,unsigned __int64,bool,uint,uint,int)
0x180017441  jmp     loc_180017DD4
0x180017446  sub     edx, 1
0x180017449  jz      loc_18001773D
0x18001744f  sub     edx, 1; unsigned __int64
0x180017452  jz      loc_180017573
0x180017458  cmp     edx, 1
0x18001745b  jnz     loc_180017DD4
0x180017461  mov     esi, [rbx+1108h]
0x180017467  sub     ecx, 3; unsigned __int8
0x18001746a  jz      loc_18001751E
0x180017470  cmp     ecx, edx
0x180017472  jz      short loc_1800174C9
0x180017474  cmp     [rsp+730h+var_6BC], r13d
0x180017479  setnz   r14b
0x18001747d  call    ?IsEnabled@OfflineMapsTelemetry@@SA_NE_K@Z; OfflineMapsTelemetry::IsEnabled(uchar,unsigned __int64)
0x180017482  test    al, al
0x180017484  jz      loc_180017DD4
0x18001748a  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x18001748f  mov     ecx, [rbp+630h+var_60]
0x180017495  mov     r9b, r14b; bool
0x180017498  mov     r8, [rbx+10F8h]; unsigned __int64
0x18001749f  mov     rdx, [rbx+10ECh]; struct _FILETIME
0x1800174a6  mov     dword ptr [rsp+730h+var_6F8], edi; int
0x1800174aa  mov     dword ptr [rsp+730h+var_700], esi; int
0x1800174ae  mov     [rsp+730h+var_708.dwLowDateTime], ecx; unsigned int
0x1800174b2  mov     ecx, [rbp+630h+var_4AC]
0x1800174b8  mov     [rsp+730h+var_710], ecx; unsigned int
0x1800174bc  mov     rcx, rax; this
0x1800174bf  call    ?OfflineUpdateFailed_@OfflineMapsTelemetry@@QEAAXU_FILETIME@@_K_NIIHJ@Z; OfflineMapsTelemetry::OfflineUpdateFailed_(_FILETIME,unsigned __int64,bool,uint,uint,int,long)
0x1800174c4  jmp     loc_180017DD4
0x1800174c9  cmp     [rsp+730h+var_6BC], r13d
0x1800174ce  setnz   r14b
0x1800174d2  call    ?IsEnabled@OfflineMapsTelemetry@@SA_NE_K@Z; OfflineMapsTelemetry::IsEnabled(uchar,unsigned __int64)
0x1800174d7  test    al, al
0x1800174d9  jz      loc_180017DD4
0x1800174df  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x1800174e4  mov     ecx, [rbp+630h+var_60]
0x1800174ea  mov     r9b, r14b; bool
0x1800174ed  mov     r8, [rbx+10F8h]; unsigned __int64
0x1800174f4  mov     rdx, [rbx+10ECh]; struct _FILETIME
0x1800174fb  mov     dword ptr [rsp+730h+var_6F8], edi; int
0x1800174ff  mov     dword ptr [rsp+730h+var_700], esi; int
0x180017503  mov     [rsp+730h+var_708.dwLowDateTime], ecx; unsigned int
0x180017507  mov     ecx, [rbp+630h+var_4AC]
0x18001750d  mov     [rsp+730h+var_710], ecx; unsigned int
0x180017511  mov     rcx, rax; this
0x180017514  call    ?OfflineUpdateFailedBing_@OfflineMapsTelemetry@@QEAAXU_FILETIME@@_K_NIIHJ@Z; OfflineMapsTelemetry::OfflineUpdateFailedBing_(_FILETIME,unsigned __int64,bool,uint,uint,int,long)
0x180017519  jmp     loc_180017DD4
0x18001751e  cmp     [rsp+730h+var_6BC], r13d
0x180017523  setnz   r14b
0x180017527  call    ?IsEnabled@OfflineMapsTelemetry@@SA_NE_K@Z; OfflineMapsTelemetry::IsEnabled(uchar,unsigned __int64)
0x18001752c  test    al, al
0x18001752e  jz      loc_180017DD4
0x180017534  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x180017539  mov     ecx, [rbp+630h+var_60]
0x18001753f  mov     r9b, r14b; bool
0x180017542  mov     r8, [rbx+10F8h]; unsigned __int64
0x180017549  mov     rdx, [rbx+10ECh]; struct _FILETIME
0x180017550  mov     dword ptr [rsp+730h+var_6F8], edi; int
0x180017554  mov     dword ptr [rsp+730h+var_700], esi; int
0x180017558  mov     [rsp+730h+var_708.dwLowDateTime], ecx; unsigned int
0x18001755c  mov     ecx, [rbp+630h+var_4AC]
0x180017562  mov     [rsp+730h+var_710], ecx; unsigned int
0x180017566  mov     rcx, rax; this
0x180017569  call    ?OfflineUpdateFailedMos_@OfflineMapsTelemetry@@QEAAXU_FILETIME@@_K_NIIHJ@Z; OfflineMapsTelemetry::OfflineUpdateFailedMos_(_FILETIME,unsigned __int64,bool,uint,uint,int,long)
0x18001756e  jmp     loc_180017DD4
0x180017573  sub     ecx, 3
0x180017576  jz      loc_1800176A8
0x18001757c  cmp     ecx, 1
0x18001757f  lea     rcx, [rbx+0DF0h]
0x180017586  jz      loc_18001761A
0x18001758c  cmp     [rsp+730h+var_6BC], r13d
0x180017591  setnz   sil
0x180017595  call    ?GetCurrentOperationTrigger@PackageManager@@QEAA?AW4MapsOperationTrigger@@XZ; PackageManager::GetCurrentOperationTrigger(void)
0x18001759a  mov     r14d, eax
0x18001759d  call    ?GetCurrentOperationInfo@PackageManager@@QEAAKXZ; PackageManager::GetCurrentOperationInfo(void)
0x1800175a2  mov     r15d, eax
0x1800175a5  call    ?GetCurrentPackageSizeInKB@PackageManager@@QEAAIXZ; PackageManager::GetCurrentPackageSizeInKB(void)
0x1800175aa  mov     r13d, [rbx+0EE0h]
0x1800175b1  mov     r12d, eax
0x1800175b4  call    ?IsEnabled@OfflineMapsTelemetry@@SA_NE_K@Z; OfflineMapsTelemetry::IsEnabled(uchar,unsigned __int64)
0x1800175b9  test    al, al
0x1800175bb  jz      loc_180017DD4
0x1800175c1  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x1800175c6  mov     r8d, [rbp+630h+var_60]
0x1800175cd  mov     r9d, r15d; int
0x1800175d0  mov     rcx, [rbx+10ECh]
0x1800175d7  mov     edx, r13d; unsigned int
0x1800175da  mov     [rsp+730h+var_6E0], edi; int
0x1800175de  mov     [rsp+730h+var_6E8], r8d; unsigned int
0x1800175e3  mov     r8d, [rbp+630h+var_4AC]
0x1800175ea  mov     [rsp+730h+var_6F0], r8d; unsigned int
0x1800175ef  mov     r8, [rbx+10F8h]
0x1800175f6  mov     [rsp+730h+var_6F8], sil; bool
0x1800175fb  mov     [rsp+730h+var_700], r8; unsigned __int64
0x180017600  mov     r8d, r12d; unsigned int
0x180017603  mov     qword ptr [rsp+730h+var_708.dwLowDateTime], rcx; struct _FILETIME
0x180017608  mov     rcx, rax; this
0x18001760b  mov     [rsp+730h+var_710], r14d; int
0x180017610  call    ?OfflineDeleteFailed_@OfflineMapsTelemetry@@QEAAXIIHHU_FILETIME@@_K_NIIJ@Z; OfflineMapsTelemetry::OfflineDeleteFailed_(uint,uint,int,int,_FILETIME,unsigned __int64,bool,uint,uint,long)
0x180017615  jmp     loc_180017DD4
0x18001761a  cmp     [rsp+730h+var_6BC], r13d
0x18001761f  setnz   sil
0x180017623  call    ?GetCurrentOperationTrigger@PackageManager@@QEAA?AW4MapsOperationTrigger@@XZ; PackageManager::GetCurrentOperationTrigger(void)
0x180017628  mov     r14d, eax
0x18001762b  call    ?GetCurrentOperationInfo@PackageManager@@QEAAKXZ; PackageManager::GetCurrentOperationInfo(void)
0x180017630  mov     r15d, eax
0x180017633  call    ?GetCurrentPackageSizeInKB@PackageManager@@QEAAIXZ; PackageManager::GetCurrentPackageSizeInKB(void)
0x180017638  mov     r13d, [rbx+0EE0h]
0x18001763f  mov     r12d, eax
0x180017642  call    ?IsEnabled@OfflineMapsTelemetry@@SA_NE_K@Z; OfflineMapsTelemetry::IsEnabled(uchar,unsigned __int64)
0x180017647  test    al, al
0x180017649  jz      loc_180017DD4
0x18001764f  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x180017654  mov     r8d, [rbp+630h+var_60]
0x18001765b  mov     r9d, r15d; int
0x18001765e  mov     rcx, [rbx+10ECh]
0x180017665  mov     edx, r13d; unsigned int
0x180017668  mov     [rsp+730h+var_6E0], edi; int
0x18001766c  mov     [rsp+730h+var_6E8], r8d; unsigned int
0x180017671  mov     r8d, [rbp+630h+var_4AC]
0x180017678  mov     [rsp+730h+var_6F0], r8d; unsigned int
0x18001767d  mov     r8, [rbx+10F8h]
0x180017684  mov     [rsp+730h+var_6F8], sil; bool
0x180017689  mov     [rsp+730h+var_700], r8; unsigned __int64
0x18001768e  mov     r8d, r12d; unsigned int
0x180017691  mov     qword ptr [rsp+730h+var_708.dwLowDateTime], rcx; struct _FILETIME
0x180017696  mov     rcx, rax; this
0x180017699  mov     [rsp+730h+var_710], r14d; int
0x18001769e  call    ?OfflineDeleteFailedBing_@OfflineMapsTelemetry@@QEAAXIIHHU_FILETIME@@_K_NIIJ@Z; OfflineMapsTelemetry::OfflineDeleteFailedBing_(uint,uint,int,int,_FILETIME,unsigned __int64,bool,uint,uint,long)
0x1800176a3  jmp     loc_180017DD4
0x1800176a8  cmp     [rsp+730h+var_6BC], r13d
0x1800176ad  lea     rcx, [rbx+0DF0h]
0x1800176b4  setnz   sil
0x1800176b8  call    ?GetCurrentOperationTrigger@PackageManager@@QEAA?AW4MapsOperationTrigger@@XZ; PackageManager::GetCurrentOperationTrigger(void)
0x1800176bd  mov     r14d, eax
0x1800176c0  call    ?GetCurrentOperationInfo@PackageManager@@QEAAKXZ; PackageManager::GetCurrentOperationInfo(void)
0x1800176c5  mov     r15d, eax
0x1800176c8  call    ?GetCurrentPackageSizeInKB@PackageManager@@QEAAIXZ; PackageManager::GetCurrentPackageSizeInKB(void)
0x1800176cd  mov     r13d, [rbx+0EE0h]
0x1800176d4  mov     r12d, eax
0x1800176d7  call    ?IsEnabled@OfflineMapsTelemetry@@SA_NE_K@Z; OfflineMapsTelemetry::IsEnabled(uchar,unsigned __int64)
0x1800176dc  test    al, al
0x1800176de  jz      loc_180017DD4
0x1800176e4  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x1800176e9  mov     r8d, [rbp+630h+var_60]
0x1800176f0  mov     r9d, r15d; int
0x1800176f3  mov     rcx, [rbx+10ECh]
0x1800176fa  mov     edx, r13d; unsigned int
0x1800176fd  mov     [rsp+730h+var_6E0], edi; int
0x180017701  mov     [rsp+730h+var_6E8], r8d; unsigned int
0x180017706  mov     r8d, [rbp+630h+var_4AC]
0x18001770d  mov     [rsp+730h+var_6F0], r8d; unsigned int
0x180017712  mov     r8, [rbx+10F8h]
0x180017719  mov     [rsp+730h+var_6F8], sil; bool
0x18001771e  mov     [rsp+730h+var_700], r8; unsigned __int64
0x180017723  mov     r8d, r12d; unsigned int
0x180017726  mov     qword ptr [rsp+730h+var_708.dwLowDateTime], rcx; struct _FILETIME
0x18001772b  mov     rcx, rax; this
0x18001772e  mov     [rsp+730h+var_710], r14d; int
0x180017733  call    ?OfflineDeleteFailedMos_@OfflineMapsTelemetry@@QEAAXIIHHU_FILETIME@@_K_NIIJ@Z; OfflineMapsTelemetry::OfflineDeleteFailedMos_(uint,uint,int,int,_FILETIME,unsigned __int64,bool,uint,uint,long)
0x180017738  jmp     loc_180017DD4
0x18001773d  mov     esi, [rbx+1108h]
0x180017743  sub     ecx, 3
0x180017746  jz      loc_180017888
0x18001774c  cmp     ecx, 1
0x18001774f  lea     rcx, [rbx+0DF0h]
0x180017756  jz      loc_1800177F2
0x18001775c  cmp     [rsp+730h+var_6BC], r13d
0x180017761  setnz   r14b
0x180017765  call    ?GetCurrentOperationTrigger@PackageManager@@QEAA?AW4MapsOperationTrigger@@XZ; PackageManager::GetCurrentOperationTrigger(void)
0x18001776a  mov     r15d, eax
0x18001776d  call    ?GetCurrentOperationInfo@PackageManager@@QEAAKXZ; PackageManager::GetCurrentOperationInfo(void)
0x180017772  mov     r12d, eax
0x180017775  call    ?GetCurrentPackageSizeInKB@PackageManager@@QEAAIXZ; PackageManager::GetCurrentPackageSizeInKB(void)
0x18001777a  mov     r13d, eax
0x18001777d  mov     eax, [rbx+0EE0h]
0x180017783  mov     [rsp+730h+var_6D0], eax
0x180017787  call    ?IsEnabled@OfflineMapsTelemetry@@SA_NE_K@Z; OfflineMapsTelemetry::IsEnabled(uchar,unsigned __int64)
  ... truncated ...
```
