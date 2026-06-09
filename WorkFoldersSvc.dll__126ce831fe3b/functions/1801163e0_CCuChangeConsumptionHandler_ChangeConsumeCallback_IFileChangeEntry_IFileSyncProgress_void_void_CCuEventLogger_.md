# CCuChangeConsumptionHandler::ChangeConsumeCallback(IFileChangeEntry *,IFileSyncProgress *,void *,void *,CCuEventLogger *,bool *,IFileSyncItemMetadata *,bool,ISyncFileSystemInterface *)

- ea: `0x1801163e0`
- end: `0x180118a2a`
- name: `?ChangeConsumeCallback@CCuChangeConsumptionHandler@@CAJPEAUIFileChangeEntry@@PEAUIFileSyncProgress@@PEAX2PEAVCCuEventLogger@@PEA_NPEAUIFileSyncItemMetadata@@_NPEAUISyncFileSystemInterface@@@Z`
- size: `9802`
- prototype: `static int(struct IFileChangeEntry *, struct IFileSyncProgress *, void *, void *, struct CCuEventLogger *, bool *, struct IFileSyncItemMetadata *, bool, struct ISyncFileSystemInterface *)`
- caller_count: `1`
- callee_count: `54`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180120a9c`

## callees

- `0x180002ab0`
- `0x18000430d`
- `0x180006f5c`
- `0x180007de8`
- `0x180007e10`
- `0x180008080`
- `0x180009158`
- `0x1800091ac`
- `0x180011314`
- `0x18001133c`
- `0x18001137c`
- `0x180035564`
- `0x18004af44`
- `0x18004b814`
- `0x180058d2c`
- `0x180058d44`
- `0x180058d88`
- `0x18006a410`
- `0x180080b60`
- `0x180083ed0`
- `0x180083ee4`
- `0x180083ef4`
- `0x18009c93c`
- `0x1800a0c30`
- `0x1800bb748`
- `0x180111420`
- `0x180115154`
- `0x180115170`
- `0x18011624c`
- `0x1801162ac`
- `0x18011637c`
- `0x1801163e0`
- `0x180119198`
- `0x1801194f0`
- `0x180119a80`
- `0x180119ac0`
- `0x18011acd0`
- `0x18011ad44`
- `0x18011adcc`
- `0x18011ae94`
- `0x18011af94`
- `0x18011b0d8`
- `0x18011e428`
- `0x18011e708`
- `0x18011ede8`
- `0x18012100c`
- `0x18012122c`
- `0x1801214ec`
- `0x180121654`
- `0x1801217bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18011809e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18011809e`
- `KERNEL32!CompareFileTime` at `0x18011771d`
- `KERNEL32!CompareFileTime` at `0x18011771d`
- `ntdll!NtClose` at `0x180116d74`
- `ntdll!NtClose` at `0x180116d74`

## pseudocode

```c
__int64 __fastcall CCuChangeConsumptionHandler::ChangeConsumeCallback(
        struct IFileChangeEntry *a1,
        struct IFileSyncProgress *a2,
        struct CCuCallbackHandlerContext::CallbackContext *a3,
        struct CCuChangeEntryContext *a4,
        struct CCuEventLogger *a5,
        bool *a6,
        struct IFileSyncItemMetadata *a7,
        bool a8,
        struct ISyncFileSystemInterface *a9)
{
  char *v12; // rax
  bool v13; // r9
  __int16 v14; // ax
  __int64 v15; // rcx
  __int64 (__fastcall *v16)(struct IFileChangeEntry *, __int64); // rbx
  __int64 v17; // rax
  int v18; // eax
  char v19; // bl
  __int64 v20; // rax
  unsigned __int16 *v21; // r13
  __int16 v22; // ax
  __int64 *v23; // rcx
  struct CCuCallbackHandlerContext::CallbackContext *v24; // rbx
  __int64 v25; // rax
  int v26; // edi
  unsigned __int16 *v27; // rcx
  bool v28; // zf
  struct ISyncFileSystemInterface *v29; // rdi
  __int64 v30; // rax
  __int64 v31; // rcx
  unsigned __int64 v32; // rbx
  const unsigned __int16 *v33; // rax
  unsigned int v34; // ebx
  unsigned int v35; // eax
  int v36; // eax
  bool v37; // sf
  __int64 v38; // rax
  __int16 v39; // ax
  const unsigned __int16 *v40; // rax
  const WCHAR *v41; // r10
  PCWSTR v42; // rax
  int v43; // edx
  int v44; // ecx
  unsigned int v45; // eax
  int v46; // eax
  NTSTATUS v47; // eax
  struct IFileSyncReplicaMetadata *v48; // r12
  int FileMetadataByNativeFileID; // eax
  __int16 v50; // ax
  __int16 v51; // ax
  struct CNtfsBaseFileConcurrencyBlob *v52; // rdx
  _OWORD *v53; // rax
  char v54; // di
  unsigned __int16 *v55; // rbx
  int v56; // eax
  unsigned int v57; // edx
  __int64 v58; // r8
  const unsigned __int16 *v59; // rbx
  int v60; // eax
  __int16 v61; // ax
  int v62; // eax
  __int16 v63; // ax
  __int16 v64; // ax
  __int16 v65; // ax
  int v66; // ecx
  struct CCuCallbackHandlerContext::CallbackContext *v67; // r12
  struct CCuEventLogger *v68; // r15
  unsigned __int16 *v69; // rcx
  int v70; // r8d
  CCuEventLogger *v71; // rcx
  __int64 v72; // rax
  char v73; // al
  char v74; // al
  struct ISyncFileSystemInterface *v75; // r15
  unsigned int v76; // ebx
  int v77; // eax
  bool *v78; // r13
  BOOL v79; // esi
  struct _FILE_ID_128 *v80; // rax
  struct IFileSyncReplicaMetadata *v81; // rdi
  const unsigned __int16 *v82; // rbx
  __int64 (__fastcall *v83)(struct IFileSyncReplicaMetadata *, BOOL, bool, __int128 *); // rbx
  char v84; // al
  int v85; // eax
  __int16 v86; // ax
  __int64 v87; // rax
  _QWORD *v88; // rcx
  __int64 v89; // rdx
  int v90; // edi
  struct _FILE_ID_128 *v91; // rax
  struct IFileSyncReplicaMetadata *v92; // rdi
  __int64 v93; // rax
  int Item; // eax
  struct _FILE_ID_128 v95; // xmm6
  __int64 v96; // rax
  const unsigned __int16 *v97; // rbx
  char v98; // bl
  PVOID *v99; // rcx
  int v100; // eax
  struct ISyncFileSystemInterface *v101; // r14
  __int16 v102; // ax
  struct CNtfsBaseFileConcurrencyBlob *v103; // rdx
  int v104; // esi
  unsigned int v105; // ecx
  int v106; // eax
  unsigned int v107; // ebx
  int v108; // eax
  unsigned int v109; // ebx
  int FileInfoFromParentEnumeration; // [rsp+78h] [rbp-90h] BYREF
  __int16 v112; // [rsp+7Ch] [rbp-8Ch]
  __int16 v113; // [rsp+7Eh] [rbp-8Ah]
  struct IFileInfoFromDisk *v114; // [rsp+98h] [rbp-70h] BYREF
  unsigned int v115; // [rsp+A0h] [rbp-68h] BYREF
  struct IFileSyncItemMetadata *v116; // [rsp+A8h] [rbp-60h] BYREF
  bool v117; // [rsp+B0h] [rbp-58h]
  unsigned __int16 *v118; // [rsp+B8h] [rbp-50h] BYREF
  struct IFileSyncItemMetadata *v119; // [rsp+C0h] [rbp-48h] BYREF
  bool v120; // [rsp+C8h] [rbp-40h] BYREF
  bool v121; // [rsp+C9h] [rbp-3Fh] BYREF
  bool v122; // [rsp+CAh] [rbp-3Eh] BYREF
  bool v123; // [rsp+CBh] [rbp-3Dh] BYREF
  bool v124; // [rsp+CCh] [rbp-3Ch] BYREF
  bool v125; // [rsp+CDh] [rbp-3Bh] BYREF
  bool v126; // [rsp+CEh] [rbp-3Ah] BYREF
  char v127; // [rsp+CFh] [rbp-39h] BYREF
  bool v128; // [rsp+D0h] [rbp-38h] BYREF
  _BYTE v129[7]; // [rsp+D1h] [rbp-37h] BYREF
  __int64 v130; // [rsp+D8h] [rbp-30h] BYREF
  unsigned int v131; // [rsp+E0h] [rbp-28h] BYREF
  struct CCuEventLogger *v132; // [rsp+E8h] [rbp-20h]
  __int64 v133; // [rsp+F0h] [rbp-18h] BYREF
  int v134; // [rsp+F8h] [rbp-10h] BYREF
  struct ISyncFileSystemInterface *v135; // [rsp+100h] [rbp-8h]
  __int64 v136; // [rsp+108h] [rbp+0h] BYREF
  struct CCuCallbackHandlerContext::CallbackContext *v137; // [rsp+110h] [rbp+8h]
  struct _FILE_ID_128 v138; // [rsp+118h] [rbp+10h] BYREF
  struct IFileSyncReplicaMetadata *v139; // [rsp+128h] [rbp+20h]
  __int64 v140; // [rsp+130h] [rbp+28h] BYREF
  __int64 v141; // [rsp+138h] [rbp+30h] BYREF
  __int64 v142; // [rsp+140h] [rbp+38h] BYREF
  __int64 v143; // [rsp+148h] [rbp+40h] BYREF
  int v144; // [rsp+150h] [rbp+48h] BYREF
  unsigned int v145; // [rsp+154h] [rbp+4Ch] BYREF
  PCWSTR SourceString; // [rsp+158h] [rbp+50h] BYREF
  __int64 v147; // [rsp+160h] [rbp+58h] BYREF
  int v148; // [rsp+168h] [rbp+60h] BYREF
  unsigned int v149; // [rsp+16Ch] [rbp+64h] BYREF
  int v150; // [rsp+170h] [rbp+68h] BYREF
  unsigned int v151; // [rsp+174h] [rbp+6Ch] BYREF
  unsigned int v152; // [rsp+178h] [rbp+70h] BYREF
  unsigned int v153; // [rsp+17Ch] [rbp+74h] BYREF
  unsigned __int16 *v154; // [rsp+180h] [rbp+78h] BYREF
  __int64 v155; // [rsp+188h] [rbp+80h] BYREF
  __int64 v156; // [rsp+190h] [rbp+88h] BYREF
  __int64 v157; // [rsp+198h] [rbp+90h] BYREF
  int v158; // [rsp+1A0h] [rbp+98h] BYREF
  unsigned int v159; // [rsp+1A4h] [rbp+9Ch] BYREF
  __int64 v160; // [rsp+1A8h] [rbp+A0h] BYREF
  __int64 v161; // [rsp+1B0h] [rbp+A8h] BYREF
  __int64 v162; // [rsp+1B8h] [rbp+B0h] BYREF
  __int64 *v163; // [rsp+1C0h] [rbp+B8h] BYREF
  __int64 v164; // [rsp+1C8h] [rbp+C0h] BYREF
  HANDLE Handle; // [rsp+1D0h] [rbp+C8h] BYREF
  FILETIME FileTime1; // [rsp+1D8h] [rbp+D0h] BYREF
  bool *v167; // [rsp+1E0h] [rbp+D8h]
  struct _FILE_ID_128 v168; // [rsp+1E8h] [rbp+E0h] BYREF
  __int64 v169; // [rsp+1F8h] [rbp+F0h] BYREF
  struct IFileInfoFromDisk *v170; // [rsp+200h] [rbp+F8h] BYREF
  __int64 v171; // [rsp+208h] [rbp+100h] BYREF
  struct CNtfsBaseFileConcurrencyBlob *v172; // [rsp+210h] [rbp+108h] BYREF
  struct CNtfsBaseFileConcurrencyBlob *v173; // [rsp+218h] [rbp+110h] BYREF
  FILETIME FileTime2; // [rsp+220h] [rbp+118h] BYREF
  __int64 v175; // [rsp+228h] [rbp+120h] BYREF
  struct CNtfsBaseFileConcurrencyBlob *v176; // [rsp+230h] [rbp+128h] BYREF
  struct CNtfsBaseFileConcurrencyBlob *v177; // [rsp+238h] [rbp+130h] BYREF
  __int128 Buf2; // [rsp+240h] [rbp+138h] BYREF
  struct _FILE_ID_128 Buf1; // [rsp+258h] [rbp+150h] BYREF
  struct _FILE_ID_128 v180; // [rsp+268h] [rbp+160h] BYREF
  char v181[16]; // [rsp+278h] [rbp+170h] BYREF
  __int64 v182; // [rsp+288h] [rbp+180h]
  struct _FILE_ID_128 v183; // [rsp+298h] [rbp+190h] BYREF
  struct _FILE_ID_128 v184; // [rsp+2A8h] [rbp+1A0h] BYREF
  __int128 v185; // [rsp+2B8h] [rbp+1B0h] BYREF
  __int64 v186; // [rsp+2C8h] [rbp+1C0h]
  struct _FILE_ID_128 v187; // [rsp+2D0h] [rbp+1C8h] BYREF
  __int128 v188; // [rsp+2E0h] [rbp+1D8h] BYREF
  __int64 v189; // [rsp+2F0h] [rbp+1E8h]
  struct _FILE_ID_128 v190; // [rsp+2F8h] [rbp+1F0h] BYREF
  struct _FILE_ID_128 v191; // [rsp+308h] [rbp+200h] BYREF
  struct _FILE_ID_128 v192; // [rsp+318h] [rbp+210h] BYREF
  GUID v193; // [rsp+328h] [rbp+220h] BYREF
  _BYTE v194[16]; // [rsp+338h] [rbp+230h] BYREF
  _BYTE v195[16]; // [rsp+348h] [rbp+240h] BYREF
  _BYTE v196[16]; // [rsp+358h] [rbp+250h] BYREF
  _BYTE v197[16]; // [rsp+368h] [rbp+260h] BYREF
  _BYTE v198[16]; // [rsp+378h] [rbp+270h] BYREF
  _BYTE v199[16]; // [rsp+388h] [rbp+280h] BYREF
  _BYTE v200[16]; // [rsp+398h] [rbp+290h] BYREF
  _BYTE v201[16]; // [rsp+3A8h] [rbp+2A0h] BYREF
  _BYTE v202[16]; // [rsp+3B8h] [rbp+2B0h] BYREF

  v132 = a5;
  v167 = a6;
  v135 = a9;
  v137 = a3;
  v12 = (char *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( *((char *)WPP_GLOBAL_Control + 68) >= 0 )
      goto LABEL_8;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 18, &WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids);
      v12 = (char *)WPP_GLOBAL_Control;
    }
  }
  if ( v12[68] < 0 && (unsigned __int8)v12[65] >= 6u )
  {
    v13 = 1;
    goto LABEL_9;
  }
LABEL_8:
  v13 = 0;
LABEL_9:
  CEcsFunctionTracer::CEcsFunctionTracer(
    (CEcsFunctionTracer *)&FileInfoFromParentEnumeration,
    "CCuChangeConsumptionHandler::ChangeConsumeCallback",
    0x1D1u,
    v13);
  v115 = 0;
  v193 = GUID_NULL;
  v118 = 0;
  Buf2 = 0;
  v180 = 0;
  Buf1 = 0;
  v183 = 0;
  ATL::CComPtrBase<IFileInfoFromDisk>::CComPtrBase<IFileInfoFromDisk>(&v114);
  v142 = 0;
  v134 = 0;
  ATL::CComPtr<IFileConcurrencyBlob>::CComPtr<IFileConcurrencyBlob>(&v119);
  v189 = 0;
  v188 = 0;
  EcsZeroOut<bool>(a6);
  v14 = 492;
  if ( !a1 )
    goto LABEL_397;
  v112 = 492;
  v14 = 493;
  if ( !a3 || (v112 = 493, v14 = 494, !a4) || (v112 = 494, v14 = 495, !a5) || (v112 = 495, v14 = 496, !a6) )
  {
LABEL_397:
    FileInfoFromParentEnumeration = -2147024809;
    goto LABEL_398;
  }
  FileInfoFromParentEnumeration = 0;
  v112 = 496;
  v139 = *(struct IFileSyncReplicaMetadata **)a3;
  FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(struct IFileSyncReplicaMetadata *, GUID *))(*(_QWORD *)v139 + 32LL))(
                                    v139,
                                    &v193);
  v14 = 506;
  if ( FileInfoFromParentEnumeration < 0 )
    goto LABEL_398;
  v112 = 506;
  v15 = *((_QWORD *)a3 + 1);
  if ( v15 )
  {
    FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 48LL))(v15);
    v14 = 510;
    if ( FileInfoFromParentEnumeration < 0 )
      goto LABEL_398;
    v112 = 510;
  }
  FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(struct IFileChangeEntry *, unsigned int *))(*(_QWORD *)a1 + 56LL))(
                                    a1,
                                    &v115);
  v14 = 513;
  if ( FileInfoFromParentEnumeration < 0 )
    goto LABEL_398;
  v112 = 513;
  v16 = *(__int64 (__fastcall **)(struct IFileChangeEntry *, __int64))(*(_QWORD *)a1 + 24LL);
  v17 = ATL::CHeapPtrBase<unsigned short,ATL::CComAllocator>::operator&(&v118);
  v18 = v16(a1, v17);
  v19 = 0;
  FileInfoFromParentEnumeration = v18;
  if ( v18 < 0 )
  {
    v113 = 514;
    goto LABEL_399;
  }
  v112 = 514;
  FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(struct IFileChangeEntry *, struct _FILE_ID_128 *))(*(_QWORD *)a1 + 32LL))(
                                    a1,
                                    &Buf1);
  v14 = 516;
  if ( FileInfoFromParentEnumeration < 0 )
    goto LABEL_398;
  v112 = 516;
  FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(struct IFileChangeEntry *, struct _FILE_ID_128 *))(*(_QWORD *)a1 + 80LL))(
                                    a1,
                                    &v180);
  v14 = 517;
  if ( FileInfoFromParentEnumeration < 0 )
    goto LABEL_398;
  v112 = 517;
  FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(struct IFileChangeEntry *, struct _FILE_ID_128 *))(*(_QWORD *)a1 + 40LL))(
                                    a1,
                                    &v183);
  v14 = 518;
  if ( FileInfoFromParentEnumeration < 0 )
    goto LABEL_398;
  v112 = 518;
  FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(struct IFileChangeEntry *, __int64 *))(*(_QWORD *)a1 + 64LL))(
                                    a1,
                                    &v142);
  v14 = 520;
  if ( FileInfoFromParentEnumeration < 0 )
    goto LABEL_398;
  v112 = 520;
  FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(struct IFileChangeEntry *, int *))(*(_QWORD *)a1 + 48LL))(
                                    a1,
                                    &v134);
  v14 = 521;
  if ( FileInfoFromParentEnumeration < 0 )
    goto LABEL_398;
  v112 = 521;
  v20 = *(_QWORD *)Buf1.Identifier - *((_QWORD *)a3 + 5);
  if ( *(_QWORD *)Buf1.Identifier == *((_QWORD *)a3 + 5) )
    v20 = *(_QWORD *)&Buf1.Identifier[8] - *((_QWORD *)a3 + 6);
  v117 = v20 == 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 68) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    WPP_SF_iiiiiiiDDS(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      19,
      (unsigned int)&WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids,
      *(_DWORD *)&v183.Identifier[8],
      v183.Identifier[0],
      Buf1.Identifier[8],
      Buf1.Identifier[0],
      v180.Identifier[8],
      v180.Identifier[0],
      v142,
      v115,
      v134,
      (__int64)v118);
  }
  v21 = (unsigned __int16 *)&Format;
  if ( memcmp_0(&Buf1, &Buf2, 0x10u) )
  {
    v171 = 0;
    if ( a9 )
    {
      v169 = 0;
      v163 = 0;
      FileInfoFromParentEnumeration = IUnknown::QueryInterface<IFileSystemExtInterface>(a9, &v163);
      v22 = 555;
      if ( FileInfoFromParentEnumeration < 0 )
      {
        v23 = (__int64 *)&v163;
LABEL_36:
        v113 = v22;
LABEL_37:
        ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(v23);
        goto LABEL_399;
      }
      v24 = v137;
      v112 = 555;
      v25 = *v163;
      v168 = Buf1;
      v26 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, struct _FILE_ID_128 *, __int64 *))(v25 + 32))(
              v163,
              *((_QWORD *)v137 + 8),
              &v168,
              &v169);
      ATL::CComPtrBase<IFileInfoFromDisk>::Attach(&v114, v169);
      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v163);
    }
    else
    {
      v170 = 0;
      v24 = v137;
      v168 = Buf1;
      v26 = CNtfsFileInfoFromDisk::CreateInstance(*((void **)v137 + 8), &v168, &v170);
      ATL::CComPtrBase<IFileInfoFromDisk>::Attach(&v114, v170);
    }
    if ( v26 == -1073741790 )
    {
      if ( (v134 & 0x10) == 0 )
      {
        v27 = (unsigned __int16 *)&Format;
        if ( v118 )
          v27 = v118;
        CCuEventLogger::LogEvent(v132, -2147024891, 0, 0, (__int64)v27, 0);
        v28 = memcmp_0(&v183, &Buf2, 0x10u) == 0;
        v14 = 574;
        if ( v28 )
          goto LABEL_54;
        v112 = 574;
        FileInfoFromParentEnumeration = 0;
        v29 = v135;
        v168 = Buf1;
        v138 = v183;
        FileInfoFromParentEnumeration = CCuChangeConsumptionHandler::GetFileInfoFromParentEnumeration(
                                          &v138,
                                          &v168,
                                          v24,
                                          v132,
                                          v135,
                                          &v114);
        v14 = 581;
        if ( FileInfoFromParentEnumeration < 0 )
          goto LABEL_398;
        v112 = 581;
        (*(void (__fastcall **)(struct IFileInfoFromDisk *, __int64))(*(_QWORD *)v114 + 80LL))(v114, v142);
        v28 = ((*(__int64 (__fastcall **)(struct IFileInfoFromDisk *))(*(_QWORD *)v114 + 32LL))(v114) & 0x10) == 0;
        v14 = 584;
        if ( !v28 )
          goto LABEL_54;
        FileInfoFromParentEnumeration = 0;
        v112 = 584;
        if ( !v118 )
        {
          v30 = (*(__int64 (__fastcall **)(struct IFileInfoFromDisk *))(*(_QWORD *)v114 + 104LL))(v114);
          v31 = -1;
          do
            ++v31;
          while ( *(_WORD *)(v30 + 2 * v31) );
          v32 = v31 + 1;
          v28 = (unsigned __int8)ATL::CHeapPtr<unsigned short,ATL::CComAllocator>::Allocate(&v118, v31 + 1) == 0;
          v14 = 590;
          if ( v28 )
          {
            FileInfoFromParentEnumeration = -2147024882;
            goto LABEL_398;
          }
          FileInfoFromParentEnumeration = 0;
          v112 = 590;
          v33 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IFileInfoFromDisk *))(*(_QWORD *)v114 + 104LL))(v114);
          FileInfoFromParentEnumeration = StringCchCopyW(v118, v32, v33);
          v14 = 593;
          if ( FileInfoFromParentEnumeration < 0 )
            goto LABEL_398;
          v112 = 593;
          (*(void (__fastcall **)(struct IFileInfoFromDisk *, unsigned __int16 *))(*(_QWORD *)v114 + 136LL))(v114, v118);
        }
LABEL_57:
        v120 = 0;
        v159 = 0;
        FileInfoFromParentEnumeration = CSimpleHashTable<_FILE_ID_128,unsigned int,CCuCallbackHandlerContext::CFileIDHash,CCuCallbackHandlerContext::CFileIDHash,CDefaultResizePolicy,CDefaultRehashPolicy>::GetItem(
                                          (char *)a4 + 256,
                                          &Buf1,
                                          &v159);
        v14 = 608;
        if ( FileInfoFromParentEnumeration < 0 )
          goto LABEL_398;
        v112 = 608;
        v34 = (*(__int64 (__fastcall **)(struct IFileInfoFromDisk *))(*(_QWORD *)v114 + 88LL))(v114);
        v35 = (*(__int64 (__fastcall **)(struct IFileInfoFromDisk *))(*(_QWORD *)v114 + 32LL))(v114);
        v36 = CCuFileSystemOperations::CheckFileAgainstReparsePoint(v35, v34, v29, &v120);
        v19 = 0;
        FileInfoFromParentEnumeration = v36;
        v37 = v36 < 0;
        v14 = 613;
        if ( v37 )
          goto LABEL_398;
        v112 = 613;
        if ( v120 )
        {
          CCuEventLogger::LogEvent(v132, -2134375935, 0, 0, (__int64)v118, 0);
          v14 = 617;
          FileInfoFromParentEnumeration = -2134375935;
          goto LABEL_398;
        }
        if ( (*(unsigned int (__fastcall **)(struct IFileInfoFromDisk *))(*(_QWORD *)v114 + 96LL))(v114) != 1 )
        {
          CCuEventLogger::LogEvent(v132, -2134375934, 0, 0, (__int64)v118, 0);
          v14 = 626;
          FileInfoFromParentEnumeration = -2134375934;
          goto LABEL_398;
        }
        if ( !v142 )
          v142 = (*(__int64 (__fastcall **)(struct IFileInfoFromDisk *))(*(_QWORD *)v114 + 72LL))(v114);
        v38 = (*(__int64 (__fastcall **)(struct IFileInfoFromDisk *))(*(_QWORD *)v114 + 72LL))(v114);
        if ( v142 != v38 )
        {
          if ( (v134 & 0x10) != 0
            && v118
            && (*(__int64 (__fastcall **)(struct IFileInfoFromDisk *))(*(_QWORD *)v114 + 128LL))(v114) )
          {
            CEcsMemPtr<unsigned short,0>::CEcsMemPtr<unsigned short,0>(&SourceString);
            CEcsMemPtr<unsigned short,0>::CEcsMemPtr<unsigned short,0>(&v154);
            FileInfoFromParentEnumeration = CPathUtilities::GetNormalizedNtPath(
                                              v118,
                                              (unsigned __int16 **)&SourceString);
            v39 = 649;
            if ( FileInfoFromParentEnumeration < 0
              || (v112 = 649,
                  v40 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IFileInfoFromDisk *))(*(_QWORD *)v114 + 128LL))(v114),
                  FileInfoFromParentEnumeration = CPathUtilities::GetNormalizedNtPath(v40, &v154),
                  v39 = 650,
                  FileInfoFromParentEnumeration < 0) )
            {
              v113 = v39;
              CEcsMemPtr<unsigned short,0>::~CEcsMemPtr<unsigned short,0>(&v154);
              CEcsMemPtr<unsigned short,0>::~CEcsMemPtr<unsigned short,0>(&SourceString);
              goto LABEL_399;
            }
            v41 = SourceString;
            v112 = 650;
            v42 = SourceString;
            do
            {
              v43 = *(PCWSTR)((char *)v42 + (char *)v154 - (char *)SourceString);
              v44 = *v42 - v43;
              if ( v44 )
                break;
              ++v42;
            }
            while ( v43 );
            if ( !v44 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && *((char *)WPP_GLOBAL_Control + 68) < 0
                && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
              {
                WPP_SF_S(
                  *((_QWORD *)WPP_GLOBAL_Control + 7),
                  20,
                  &WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids,
                  v118);
                v41 = SourceString;
              }
              Handle = 0;
              v45 = CCuFileSystemOperations::OpenFile(&Handle, 0x100021u, v41, 0, 0x21u);
              v46 = HRESULTFromNTSTATUS(v45);
              if ( v46 >= 0 )
              {
                v47 = NtClose(Handle);
                if ( v47 < 0
                  && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && *((char *)WPP_GLOBAL_Control + 68) < 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 3u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 7),
                    22,
                    &WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids,
                    (unsigned int)v47);
                }
                Handle = 0;
              }
              else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                     && *((char *)WPP_GLOBAL_Control + 68) < 0
                     && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 3u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 7),
                  21,
                  &WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids,
                  (unsigned int)v46);
              }
            }
            CEcsMemPtr<unsigned short,0>::~CEcsMemPtr<unsigned short,0>(&v154);
            CEcsMemPtr<unsigned short,0>::~CEcsMemPtr<unsigned short,0>(&SourceString);
          }
          FileInfoFromParentEnumeration = -2134375931;
          v14 = 682;
          goto LABEL_398;
        }
        if ( !a7 )
        {
          v48 = v139;
          FileMetadataByNativeFileID = CCuDBOperations::FindFileMetadataByNativeFileID(v139, &Buf1, &v119);
          if ( FileMetadataByNativeFileID >= 0 )
          {
            v133 = 0;
            FileInfoFromParentEnumeration = IUnknown::QueryInterface<INtfsBaseItemMetadata>(v119, &v133);
            v50 = 693;
            if ( FileInfoFromParentEnumeration < 0
              || (v112 = 693,
                  FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v133 + 32LL))(
                                                    v133,
                                                    &v171),
                  v50 = 694,
                  FileInfoFromParentEnumeration < 0) )
            {
              v113 = v50;
LABEL_97:
              v23 = &v133;
              goto LABEL_37;
            }
            v112 = 694;
            if ( v142 == v171 )
            {
              ATL::CComPtr<IFileConcurrencyBlob>::CComPtr<IFileConcurrencyBlob>(&v136);
              ATL::CComPtr<IFileConcurrencyBlob>::CComPtr<IFileConcurrencyBlob>(&v141);
              v158 = 0;
              if ( v29 )
              {
                v172 = 0;
                FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(struct ISyncFileSystemInterface *, struct IFileInfoFromDisk *, struct CNtfsBaseFileConcurrencyBlob **))(*(_QWORD *)v29 + 72LL))(
                                                  v29,
                                                  v114,
                                                  &v172);
                v51 = 707;
                if ( FileInfoFromParentEnumeration < 0 )
                {
LABEL_102:
                  v113 = v51;
LABEL_103:
                  ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(&v141);
                  ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(&v136);
                  goto LABEL_97;
                }
                v52 = v172;
              }
              else
              {
                v173 = 0;
                FileInfoFromParentEnumeration = CNtfsBaseFileConcurrencyBlob::CreateInstance(v114, &v173);
                v51 = 713;
                if ( FileInfoFromParentEnumeration < 0 )
                  goto LABEL_102;
                v52 = v173;
              }
              v112 = v51;
              ATL::CComPtrBase<IFileConcurrencyBlob>::Attach(&v136, v52);
              FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(struct IFileSyncItemMetadata *, __int64 *))(*(_QWORD *)v119 + 184LL))(
                                                v119,
                                                &v141);
              v51 = 717;
              if ( FileInfoFromParentEnumeration < 0 )
                goto LABEL_102;
              v112 = 717;
              FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v136 + 24LL))(
                                                v136,
                                                v141,
                                                &v158);
              v51 = 720;
              if ( FileInfoFromParentEnumeration < 0 )
                goto LABEL_102;
              v112 = 720;
              if ( !v158 )
              {
                FileInfoFromParentEnumeration = 0;
                v112 = 726;
                goto LABEL_103;
              }
              ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(&v141);
              ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(&v136);
            }
            ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v133);
            goto LABEL_120;
          }
          if ( FileMetadataByNativeFileID != -2147216764 )
          {
            FileInfoFromParentEnumeration = FileMetadataByNativeFileID;
            v14 = 732;
            goto LABEL_398;
          }
          v14 = 732;
LABEL_119:
          v112 = v14;
          FileInfoFromParentEnumeration = 0;
LABEL_120:
          if ( (unsigned __int8)ATL::CComPtrBase<IFileSyncItemMetadata>::operator!=(&v119, 0) )
          {
            FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(struct IFileSyncItemMetadata *, __int128 *))(*(_QWORD *)v119 + 48LL))(
                                              v119,
                                              &v188);
            v14 = 750;
            if ( FileInfoFromParentEnumeration < 0 )
              goto LABEL_398;
            v112 = 750;
          }
          if ( v117 )
            (*(void (__fastcall **)(struct IFileInfoFromDisk *))(*(_QWORD *)v114 + 120LL))(v114);
          v53 = (_OWORD *)(*(__int64 (__fastcall **)(struct IFileInfoFromDisk *, _BYTE *))(*(_QWORD *)v114 + 112LL))(
                            v114,
                            v194);
          *(_OWORD *)(*((_QWORD *)a4 + 20) + 16LL * v159) = *v53;
          goto LABEL_135;
        }
        v191 = 0;
        ATL::CComPtr<IFileSyncItemMetadata>::operator=(&v119, a7);
        FileInfoFromParentEnumeration = CCuDBOperations::GetNativeFileID(v119, &v191);
        v14 = 744;
        if ( FileInfoFromParentEnumeration < 0 )
          goto LABEL_398;
        v112 = 744;
        v28 = memcmp_0(&v191, &Buf1, 0x10u) == 0;
        v14 = 745;
        if ( v28 )
        {
          v48 = v139;
          goto LABEL_119;
        }
LABEL_54:
        FileInfoFromParentEnumeration = -2147418113;
        goto LABEL_398;
      }
    }
    else
    {
      v19 = 0;
      if ( v26 >= 0 )
      {
        v29 = v135;
        goto LABEL_57;
      }
      if ( v26 == -1073741738 )
      {
        FileInfoFromParentEnumeration = -2134375931;
        v14 = 763;
        goto LABEL_398;
      }
      if ( v26 == -1073741811 )
      {
        v48 = v139;
        v54 = 1;
        goto LABEL_151;
      }
    }
    v55 = (unsigned __int16 *)&Format;
    if ( v118 )
      v55 = v118;
    v56 = HRESULTFromNTSTATUS((unsigned int)v26);
    CCuEventLogger::LogEvent(v132, v56, 0, 0, (__int64)v55, 0);
    v19 = 0;
    FileInfoFromParentEnumeration = HRESULTFromNTSTATUS((unsigned int)v26);
    v14 = 777;
    if ( FileInfoFromParentEnumeration < 0 )
      goto LABEL_398;
    v112 = 777;
  }
  v48 = v139;
LABEL_135:
  v54 = 0;
  if ( memcmp_0(&Buf1, &Buf2, 0x10u) && (v115 & 0x409) != 0 )
  {
    v145 = 0;
    v121 = 0;
    v187 = 0;
    FileInfoFromParentEnumeration = CSimpleHashTable<_FILE_ID_128,unsigned int,CCuCallbackHandlerContext::CFileIDHash,CCuCallbackHandlerContext::CFileIDHash,CDefaultResizePolicy,CDefaultRehashPolicy>::GetItem(
                                      (char *)a4 + 256,
                                      &Buf1,
                                      &v145);
    v14 = 796;
    if ( FileInfoFromParentEnumeration < 0 )
      goto LABEL_398;
    v112 = 796;
    v57 = 0;
    v58 = *((_QWORD *)a4 + 28);
    while ( (unsigned __int64)v57 < *(_QWORD *)(32LL * v145 + v58 + 8) )
    {
      if ( !*(_BYTE *)(*(unsigned int *)(*(_QWORD *)(v58 + 32LL * v145) + 4LL * v57) + *((_QWORD *)a4 + 4)) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 68) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 23, &WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids, v118);
        }
        FileInfoFromParentEnumeration = -2134375930;
        v14 = 803;
        goto LABEL_398;
      }
      ++v57;
    }
    v59 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IFileInfoFromDisk *))(*(_QWORD *)v114 + 104LL))(v114);
    v138 = *(struct _FILE_ID_128 *)(*(__int64 (__fastcall **)(struct IFileInfoFromDisk *, _BYTE *))(*(_QWORD *)v114
                                                                                                  + 112LL))(
                                     v114,
                                     v195);
    v60 = CCuDBOperations::ItemExist(&v138, v59, v48, &v121, &v187);
    v19 = 0;
    FileInfoFromParentEnumeration = v60;
    v37 = v60 < 0;
    v14 = 807;
    if ( v37 )
      goto LABEL_398;
    v112 = 807;
    if ( v121 && memcmp_0(&v187, &Buf1, 0x10u) )
      *(struct _FILE_ID_128 *)(*((_QWORD *)a4 + 12) + 16LL * v145) = v187;
  }
LABEL_151:
  if ( (v115 & 0x202) != 0 )
  {
    ATL::CComPtr<IFileConcurrencyBlob>::CComPtr<IFileConcurrencyBlob>(&v116);
    v182 = 0;
    v61 = 851;
    *(_OWORD *)v181 = 0;
    if ( v117 )
    {
      FileInfoFromParentEnumeration = -2134375932;
    }
    else
    {
      FileInfoFromParentEnumeration = 0;
      v112 = 851;
      v62 = CCuDBOperations::FindFileMetadataByNativeFileID(v48, &v180, &v116);
      if ( v62 >= 0 )
      {
        v130 = 0;
        v144 = 0;
        FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(struct IFileSyncItemMetadata *, char *))(*(_QWORD *)v116 + 48LL))(
                                          v116,
                                          v181);
        v63 = 860;
        if ( FileInfoFromParentEnumeration < 0 )
          goto LABEL_155;
        v112 = 860;
        FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(struct IFileSyncItemMetadata *, int *))(*(_QWORD *)v116 + 64LL))(
                                          v116,
                                          &v144);
        v63 = 862;
        if ( FileInfoFromParentEnumeration < 0 )
          goto LABEL_155;
        v112 = 862;
        FileInfoFromParentEnumeration = IUnknown::QueryInterface<INtfsBaseItemMetadata>(v116, &v130);
        v63 = 864;
        if ( FileInfoFromParentEnumeration < 0 )
          goto LABEL_155;
        v112 = 864;
        if ( (v144 & 0x10) == 0 )
        {
          if ( (v115 & 9) == 0 || !memcmp_0(&Buf1, &v180, 0x10u) || v54 )
            goto LABEL_221;
          FileTime1 = 0;
          (*(void (__fastcall **)(struct IFileInfoFromDisk *, FILETIME *))(*(_QWORD *)v114 + 40LL))(v114, &FileTime2);
          FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(struct IFileSyncItemMetadata *, FILETIME *))(*(_QWORD *)v116 + 80LL))(
                                            v116,
                                            &FileTime1);
          v63 = 960;
          if ( FileInfoFromParentEnumeration < 0 )
            goto LABEL_155;
          v112 = 960;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((char *)WPP_GLOBAL_Control + 68) < 0
            && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
          {
            ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_ii)(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              26,
              &WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids,
              FileTime1,
              FileTime2);
          }
          if ( CompareFileTime(&FileTime1, &FileTime2)
            || ((*(__int64 (__fastcall **)(struct IFileInfoFromDisk *))(*(_QWORD *)v114 + 32LL))(v114) & 0x10) != 0 )
          {
LABEL_221:
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *((char *)WPP_GLOBAL_Control + 68) < 0
              && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
            {
              WPP_SF_i_guid_iiS(
                *((_QWORD *)WPP_GLOBAL_Control + 7),
                29,
                (unsigned int)&WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids,
                *(_DWORD *)v181,
                (__int64)&v181[8],
                v180.Identifier[8],
                v180.Identifier[0],
                (__int64)v118);
            }
            v67 = v137;
            FileInfoFromParentEnumeration = CCuDBOperations::DeleteItem(v116, v137, 0);
            v63 = 1046;
            if ( FileInfoFromParentEnumeration >= 0 )
            {
              v71 = v132;
              v70 = 5;
              goto LABEL_225;
            }
            goto LABEL_155;
          }
          v123 = 0;
          v138 = *(struct _FILE_ID_128 *)(*(__int64 (__fastcall **)(struct IFileInfoFromDisk *, _BYTE *))(*(_QWORD *)v114 + 112LL))(
                                           v114,
                                           v202);
          FileInfoFromParentEnumeration = CCuDBOperations::ItemExist(&v138, v48, &v123);
          v63 = 975;
          if ( FileInfoFromParentEnumeration < 0 )
            goto LABEL_155;
          v112 = 975;
          v63 = 976;
          if ( v123 )
          {
            FileInfoFromParentEnumeration = 0;
            v112 = 976;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *((char *)WPP_GLOBAL_Control + 68) < 0
              && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
            {
              v72 = (*(__int64 (__fastcall **)(struct IFileInfoFromDisk *))(*(_QWORD *)v114 + 104LL))(v114);
              WPP_SF_iiSiii_guid_(
                *((_QWORD *)WPP_GLOBAL_Control + 7),
                v180.Identifier[0],
                v72,
                Buf1.Identifier[8],
                Buf1.Identifier[0],
                v181[0],
                (__int64)&v181[8]);
            }
            v73 = ATL::CComPtrBase<IFileSyncItemMetadata>::operator!=(&v119, 0);
            v67 = v137;
            if ( v73 )
            {
              FileInfoFromParentEnumeration = CCuDBOperations::DeleteItem(v119, v137, 0);
              v63 = 991;
              if ( FileInfoFromParentEnumeration < 0 )
                goto LABEL_155;
              v112 = 991;
            }
            FileInfoFromParentEnumeration = CCuCallbackHandlerContext::PrepareChangeVersion(v67);
            v63 = 994;
            if ( FileInfoFromParentEnumeration >= 0 )
            {
              v112 = 994;
              v74 = (*(__int64 (__fastcall **)(struct IFileInfoFromDisk *))(*(_QWORD *)v114 + 32LL))(v114);
              v75 = v135;
              v76 = 22;
              if ( (v74 & 0x17) == (v144 & 0x17) )
                v76 = 6;
              if ( v135 )
              {
                v164 = 0;
                FileInfoFromParentEnumeration = IUnknown::QueryInterface<IFileSystemExtInterface>(v135, &v164);
                if ( FileInfoFromParentEnumeration < 0 )
                {
                  v113 = 1012;
                  ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v164);
                  goto LABEL_156;
                }
                v112 = 1012;
                v77 = (*(__int64 (__fastcall **)(__int64, struct IFileInfoFromDisk *))(*(_QWORD *)v164 + 72LL))(
                        v164,
                        v114);
                if ( v77 < 0
                  && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && *((char *)WPP_GLOBAL_Control + 68) < 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 7),
                    28,
                    &WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids,
                    (unsigned int)v77);
                }
                ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v164);
              }
              FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(__int64, struct IFileInfoFromDisk *, _QWORD, __int64))(*(_QWORD *)v130 + 40LL))(
                                                v130,
                                                v114,
                                                v76,
                                                (__int64)v67 + 24);
              v63 = 1026;
              if ( FileInfoFromParentEnumeration >= 0 )
              {
                v112 = 1026;
                FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(struct IFileSyncItemMetadata *))(*(_QWORD *)v116 + 160LL))(v116);
                v63 = 1028;
                if ( FileInfoFromParentEnumeration >= 0 )
                {
                  v112 = 1028;
                  CCuEventLogger::LogEvent(v132, 0, 4, 0, (__int64)v118, (__int64)v181);
                  v19 = 1;
LABEL_229:
                  if ( !memcmp_0(&Buf1, &v180, 0x10u) )
                    ATL::CComPtrBase<IFileConcurrencyBlob>::Release(&v119);
                  v78 = v167;
                  *v167 = 1;
                  ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v130);
                  goto LABEL_234;
                }
              }
            }
            goto LABEL_155;
          }
LABEL_184:
          FileInfoFromParentEnumeration = -2134375930;
LABEL_155:
          v113 = v63;
LABEL_156:
          ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v130);
LABEL_238:
          ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(&v116);
          goto LABEL_399;
        }
        v64 = v115;
        if ( (v115 & 2) != 0 )
        {
          v147 = 0;
          ATL::CComPtr<IFileConcurrencyBlob>::CComPtr<IFileConcurrencyBlob>(&v155);
          FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(struct IFileSyncItemMetadata *, __int64 *))(*(_QWORD *)v116 + 280LL))(
                                            v116,
                                            &v147);
          v65 = 905;
          if ( FileInfoFromParentEnumeration >= 0 )
          {
            v112 = 905;
            v66 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v147 + 24LL))(v147, &v155);
            FileInfoFromParentEnumeration = v66;
            v65 = 906;
            if ( v66 >= 0 )
            {
              v112 = 906;
              v65 = 907;
              if ( v66 == 1 )
              {
                FileInfoFromParentEnumeration = 0;
                v112 = 907;
                ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(&v155);
                ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v147);
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && *((char *)WPP_GLOBAL_Control + 68) < 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
                {
                  WPP_SF_i_guid_iiS(
                    *((_QWORD *)WPP_GLOBAL_Control + 7),
                    24,
                    (unsigned int)&WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids,
                    *(_DWORD *)v181,
                    (__int64)&v181[8],
                    v180.Identifier[8],
                    v180.Identifier[0],
                    (__int64)v118);
                }
                v67 = v137;
                FileInfoFromParentEnumeration = CCuDBOperations::DeleteItem(v116, v137, 0);
                v63 = 914;
                if ( FileInfoFromParentEnumeration < 0 )
                  goto LABEL_155;
                v68 = v132;
                v69 = (unsigned __int16 *)&Format;
                v112 = 914;
                if ( v118 )
                  v69 = v118;
                CCuEventLogger::LogEvent(v132, 0, 2, 0, (__int64)v69, (__int64)v181);
                v64 = v115;
                goto LABEL_175;
              }
              FileInfoFromParentEnumeration = -2134375930;
            }
          }
          v113 = v65;
          ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(&v155);
          ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v147);
          goto LABEL_156;
        }
        v67 = v137;
        v68 = v132;
LABEL_175:
        if ( (v64 & 0x200) == 0 )
        {
LABEL_228:
          v75 = v135;
          goto LABEL_229;
        }
        v122 = 0;
        FileInfoFromParentEnumeration = CCuChangeConsumptionHandler::DescendantAppearInNotAppliedChangeEntries(
                                          v116,
                                          a4,
                                          &v122);
        v63 = 925;
        if ( FileInfoFromParentEnumeration < 0 )
          goto LABEL_155;
        v112 = 925;
        v63 = 926;
        if ( !v122 )
        {
          FileInfoFromParentEnumeration = 0;
          v112 = 926;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((char *)WPP_GLOBAL_Control + 68) < 0
            && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
          {
            WPP_SF_i_guid_iiS(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              25,
              (unsigned int)&WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids,
              *(_DWORD *)v181,
              (__int64)&v181[8],
              v180.Identifier[8],
              v180.Identifier[0],
              (__int64)v118);
          }
          FileInfoFromParentEnumeration = CCuDBOperations::DeleteItem(v116, v67, 1);
          v63 = 935;
          if ( FileInfoFromParentEnumeration >= 0 )
          {
            v70 = 3;
            v71 = v68;
LABEL_225:
            v112 = v63;
            if ( v118 )
              v21 = v118;
            CCuEventLogger::LogEvent(v71, 0, v70, 0, (__int64)v21, (__int64)v181);
            goto LABEL_228;
          }
          goto LABEL_155;
        }
        goto LABEL_184;
      }
      if ( v62 == -2147216764 )
      {
        v67 = v137;
        v78 = v167;
        FileInfoFromParentEnumeration = 0;
        v75 = v135;
        v112 = 1069;
LABEL_234:
        ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(&v116);
        goto LABEL_240;
      }
      FileInfoFromParentEnumeration = v62;
      v61 = 1069;
    }
    v113 = v61;
    goto LABEL_238;
  }
  v75 = v135;
  v67 = v137;
  v78 = v167;
LABEL_240:
  if ( v54 )
  {
    v148 = 0;
    FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(struct IFileChangeEntry *, int *))(*(_QWORD *)a1 + 48LL))(
                                      a1,
                                      &v148);
    v14 = 1088;
    if ( FileInfoFromParentEnumeration >= 0 )
    {
      v112 = 1088;
      if ( (v148 & 0x10) == 0 && (v115 & 1) != 0 )
      {
        FileInfoFromParentEnumeration = 0;
        v112 = 1096;
        goto LABEL_399;
      }
      FileInfoFromParentEnumeration = -2134375931;
      v14 = 1101;
    }
    goto LABEL_398;
  }
  if ( (v115 & 0x408) == 8 && (unsigned __int8)ATL::CComPtrBase<IFileSyncItemMetadata>::operator==(&v119, 0) )
    v115 |= 0x400u;
  if ( !v19 )
  {
    if ( (v115 & 0x401) != 0 )
    {
      v149 = 0;
      FileInfoFromParentEnumeration = CSimpleHashTable<_FILE_ID_128,unsigned int,CCuCallbackHandlerContext::CFileIDHash,CCuCallbackHandlerContext::CFileIDHash,CDefaultResizePolicy,CDefaultRehashPolicy>::GetItem(
                                        (char *)a4 + 256,
                                        &Buf1,
                                        &v149);
      v14 = 1138;
      if ( FileInfoFromParentEnumeration < 0 )
        goto LABEL_398;
      v112 = 1138;
      if ( (unsigned __int8)ATL::CComPtrBase<IFileSyncItemMetadata>::operator==(&v119, 0) )
      {
        v79 = v117;
        if ( v117 )
        {
          v81 = v139;
        }
        else
        {
          v124 = 0;
          v192 = 0;
          v80 = (struct _FILE_ID_128 *)(*(__int64 (__fastcall **)(struct IFileInfoFromDisk *, _BYTE *))(*(_QWORD *)v114 + 112LL))(
                                         v114,
                                         v196);
          v81 = v139;
          v138 = *v80;
          FileInfoFromParentEnumeration = CCuDBOperations::ItemExist(&v138, v139, &v124);
          v14 = 1156;
          if ( FileInfoFromParentEnumeration < 0 )
            goto LABEL_398;
          v112 = 1156;
          v14 = 1157;
          if ( !v124 )
          {
            FileInfoFromParentEnumeration = -2134375930;
            goto LABEL_398;
          }
          FileInfoFromParentEnumeration = 0;
          v112 = 1157;
          v125 = 0;
          v82 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IFileInfoFromDisk *))(*(_QWORD *)v114 + 104LL))(v114);
          v138 = *(struct _FILE_ID_128 *)(*(__int64 (__fastcall **)(struct IFileInfoFromDisk *, _BYTE *))(*(_QWORD *)v114 + 112LL))(
                                           v114,
                                           v197);
          FileInfoFromParentEnumeration = CCuDBOperations::ItemExist(&v138, v82, v81, &v125, &v192);
          v14 = 1160;
          if ( FileInfoFromParentEnumeration < 0 )
            goto LABEL_398;
          v112 = 1160;
          if ( v125 )
          {
            *(struct _FILE_ID_128 *)(*((_QWORD *)a4 + 12) + 16LL * v149) = v192;
            FileInfoFromParentEnumeration = -2134375930;
            v14 = 1165;
            goto LABEL_398;
          }
        }
        v186 = 0;
        v185 = 0;
        FileInfoFromParentEnumeration = CCuCallbackHandlerContext::PrepareChangeVersion(v67);
        v14 = 1173;
        if ( FileInfoFromParentEnumeration < 0 )
          goto LABEL_398;
        v112 = 1173;
        v83 = *(__int64 (__fastcall **)(struct IFileSyncReplicaMetadata *, BOOL, bool, __int128 *))(*(_QWORD *)v81
                                                                                                  + 176LL);
        v84 = (*(__int64 (__fastcall **)(struct IFileInfoFromDisk *))(*(_QWORD *)v114 + 32LL))(v114);
        FileInfoFromParentEnumeration = v83(v81, v79, (v84 & 0x10) != 0, &v185);
        v14 = 1177;
        if ( FileInfoFromParentEnumeration < 0 )
          goto LABEL_398;
        v112 = 1177;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 68) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
        {
          WPP_SF_i_guid_ii(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            30,
            (unsigned int)&WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids,
            v185,
            (__int64)&v185 + 8);
        }
        FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(struct IFileSyncReplicaMetadata *, __int128 *, struct IFileSyncItemMetadata **))(*(_QWORD *)v81 + 192LL))(
                                          v81,
                                          &v185,
                                          &v119);
        v14 = 1183;
        if ( FileInfoFromParentEnumeration < 0 )
          goto LABEL_398;
        v112 = 1183;
        if ( v75 )
        {
          v160 = 0;
          FileInfoFromParentEnumeration = IUnknown::QueryInterface<IFileSystemExtInterface>(v75, &v160);
          v22 = 1190;
          if ( FileInfoFromParentEnumeration < 0 )
          {
            v23 = &v160;
            goto LABEL_36;
          }
          v112 = 1190;
          v85 = (*(__int64 (__fastcall **)(__int64, struct IFileInfoFromDisk *))(*(_QWORD *)v160 + 72LL))(v160, v114);
          if ( v85 < 0
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((char *)WPP_GLOBAL_Control + 68) < 0
            && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              31,
              &WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids,
              (unsigned int)v85);
          }
          ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v160);
        }
        v156 = 0;
        FileInfoFromParentEnumeration = IUnknown::QueryInterface<INtfsBaseItemMetadata>(v119, &v156);
        if ( FileInfoFromParentEnumeration < 0 )
        {
          v113 = 1204;
          v23 = &v156;
          goto LABEL_37;
        }
        v112 = 1204;
        FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(__int64, struct IFileInfoFromDisk *, __int64, __int64))(*(_QWORD *)v156 + 40LL))(
                                          v156,
                                          v114,
                                          1,
                                          (__int64)v67 + 24);
        v23 = &v156;
        v86 = 1207;
        if ( FileInfoFromParentEnumeration >= 0 )
        {
          v112 = 1207;
          ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v156);
          FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(struct IFileSyncItemMetadata *))(*(_QWORD *)v119 + 160LL))(v119);
          v14 = 1211;
          if ( FileInfoFromParentEnumeration >= 0 )
          {
            v112 = 1211;
            CCuEventLogger::LogEvent(v132, 0, 7, 0, (__int64)v118, (__int64)&v185);
            *v78 = 1;
            goto LABEL_399;
          }
          goto LABEL_398;
        }
LABEL_279:
        v113 = v86;
        goto LABEL_37;
      }
      v190 = 0;
      v175 = 0;
      FileInfoFromParentEnumeration = CCuDBOperations::GetNativeParentFileID(v119, &v190);
      v14 = 1224;
      if ( FileInfoFromParentEnumeration < 0 )
        goto LABEL_398;
      v112 = 1224;
      FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(struct IFileSyncItemMetadata *, __int64 *))(*(_QWORD *)v119 + 56LL))(
                                        v119,
                                        &v175);
      v14 = 1225;
      if ( FileInfoFromParentEnumeration < 0 )
        goto LABEL_398;
      v112 = 1225;
      v138 = *(struct _FILE_ID_128 *)(*(__int64 (__fastcall **)(struct IFileInfoFromDisk *, _BYTE *))(*(_QWORD *)v114 + 112LL))(
                                       v114,
                                       v198);
      if ( memcmp_0(&v138, &v190, 0x10u)
        || (v87 = (*(__int64 (__fastcall **)(struct IFileInfoFromDisk *))(*(_QWORD *)v114 + 104LL))(v114),
            (unsigned int)_o__wcsicmp(v87)) )
      {
        v115 = v115 & 0xFFFFFBF6 | 8;
        goto LABEL_297;
      }
      if ( (v115 & 0x400) != 0 )
      {
        v88 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 68) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
        {
          v89 = 32;
LABEL_291:
          WPP_SF_(v88[7], v89, &WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids);
        }
      }
      else
      {
        v88 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 68) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
        {
          v89 = 33;
          goto LABEL_291;
        }
      }
    }
LABEL_297:
    v90 = 0;
    if ( (v115 & 8) == 0 || (v115 & 0x400) != 0 )
    {
LABEL_344:
      if ( !memcmp_0(&Buf1, &Buf2, 0x10u) )
        goto LABEL_399;
      if ( (unsigned __int8)ATL::CComPtrBase<IFileSyncItemMetadata>::operator==(&v119, 0) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 68) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 37, &WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids, v118);
        }
        FileInfoFromParentEnumeration = -2134375931;
        v14 = 1428;
        goto LABEL_398;
      }
      v131 = 0;
      ATL::CComPtr<IFileConcurrencyBlob>::CComPtr<IFileConcurrencyBlob>(&v143);
      ATL::CComPtr<IFileConcurrencyBlob>::CComPtr<IFileConcurrencyBlob>(&v140);
      v101 = v135;
      if ( v135 )
      {
        v176 = 0;
        FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(struct ISyncFileSystemInterface *, struct IFileInfoFromDisk *, struct CNtfsBaseFileConcurrencyBlob **))(*(_QWORD *)v135 + 72LL))(
                                          v135,
                                          v114,
                                          &v176);
        v102 = 1441;
        if ( FileInfoFromParentEnumeration < 0 )
        {
LABEL_353:
          v113 = v102;
          ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(&v140);
          ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(&v143);
          goto LABEL_399;
        }
        v103 = v176;
      }
      else
      {
        v177 = 0;
        FileInfoFromParentEnumeration = CNtfsBaseFileConcurrencyBlob::CreateInstance(v114, &v177);
        v102 = 1447;
        if ( FileInfoFromParentEnumeration < 0 )
          goto LABEL_353;
        v103 = v177;
      }
      v112 = v102;
      ATL::CComPtrBase<IFileConcurrencyBlob>::Attach(&v140, v103);
      FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(struct IFileSyncItemMetadata *, __int64 *))(*(_QWORD *)v119 + 184LL))(
                                        v119,
                                        &v143);
      v102 = 1451;
      if ( FileInfoFromParentEnumeration < 0 )
        goto LABEL_353;
      v112 = 1451;
      FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v143
                                                                                                  + 24LL))(
                                        v143,
                                        v140,
                                        &v131);
      v102 = 1454;
      if ( FileInfoFromParentEnumeration < 0 )
        goto LABEL_353;
      v104 = 0;
      v112 = 1454;
      ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(&v140);
      ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(&v143);
      v105 = v131;
      if ( (v131 & 0x20000) != 0 || (v115 & 0x10) != 0 )
      {
        v129[0] = 0;
        if ( !v101 )
          goto LABEL_370;
        v161 = 0;
        FileInfoFromParentEnumeration = IUnknown::QueryInterface<IFileSystemExtInterface>(v101, &v161);
        v22 = 1471;
        if ( FileInfoFromParentEnumeration < 0 )
        {
          v23 = &v161;
          goto LABEL_36;
        }
        v112 = 1471;
        v106 = (*(__int64 (__fastcall **)(__int64, struct IFileInfoFromDisk *, _BYTE *))(*(_QWORD *)v161 + 64LL))(
                 v161,
                 v114,
                 v129);
        if ( v106 < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 68) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            38,
            &WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids,
            (unsigned int)v106);
        }
        ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v161);
        v105 = v131;
        if ( !v129[0] )
LABEL_370:
          v104 = 4;
      }
      v107 = v104 | 0x10;
      if ( (v105 & 0x10000) == 0 )
        v107 = v104;
      if ( (v105 & 0x300000) != 0 )
      {
        v14 = 1503;
        if ( !v90 )
          goto LABEL_314;
        FileInfoFromParentEnumeration = 0;
        v107 |= 8u;
        v112 = 1503;
      }
      if ( (v105 & 0xFFFF0004) != 0 || v107 )
      {
        FileInfoFromParentEnumeration = CCuCallbackHandlerContext::PrepareChangeVersion(v67);
        v14 = 1512;
        if ( FileInfoFromParentEnumeration < 0 )
          goto LABEL_398;
        v112 = 1512;
        v107 |= 2u;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 68) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
      {
        WPP_SF_i_guid_iiD(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          39,
          (unsigned int)&WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids,
          v188,
          (__int64)&v188 + 8);
      }
      v157 = 0;
      FileInfoFromParentEnumeration = IUnknown::QueryInterface<INtfsBaseItemMetadata>(v119, &v157);
      if ( FileInfoFromParentEnumeration < 0 )
      {
        v113 = 1539;
        v23 = &v157;
        goto LABEL_37;
      }
      v112 = 1539;
      FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(__int64, struct IFileInfoFromDisk *, _QWORD, __int64))(*(_QWORD *)v157 + 40LL))(
                                        v157,
                                        v114,
                                        v107,
                                        (__int64)v67 + 24);
      v23 = &v157;
      v86 = 1542;
      if ( FileInfoFromParentEnumeration < 0 )
        goto LABEL_279;
      v112 = 1542;
      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v157);
      FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(struct IFileSyncItemMetadata *))(*(_QWORD *)v119 + 160LL))(v119);
      v14 = 1545;
      if ( FileInfoFromParentEnumeration >= 0 )
      {
        v112 = 1545;
        CCuEventLogger::LogEvent(v132, 0, 8, v107, (__int64)v118, (__int64)&v188);
        *v78 = 1;
        if ( !v101 )
          goto LABEL_399;
        v162 = 0;
        FileInfoFromParentEnumeration = IUnknown::QueryInterface<IFileSystemExtInterface>(v101, &v162);
        if ( FileInfoFromParentEnumeration >= 0 )
        {
          v112 = 1558;
          v108 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IFileInfoFromDisk *, _QWORD))(*(_QWORD *)v162 + 56LL))(
                   v162,
                   v131,
                   v114,
                   0);
          if ( v108 < 0
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((char *)WPP_GLOBAL_Control + 68) < 0
            && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              40,
              &WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids,
              (unsigned int)v108);
          }
        }
        else
        {
          v113 = 1558;
        }
        v23 = &v162;
        goto LABEL_37;
      }
LABEL_398:
      v113 = v14;
      goto LABEL_399;
    }
    if ( (unsigned __int8)ATL::CComPtrBase<IFileSyncItemMetadata>::operator==(&v119, 0) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 68) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 34, &WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids, v118);
      }
      FileInfoFromParentEnumeration = -2134375931;
      v14 = 1288;
      goto LABEL_398;
    }
    v150 = 0;
    FileInfoFromParentEnumeration = (*(__int64 (__fastcall **)(struct IFileSyncItemMetadata *, int *))(*(_QWORD *)v119 + 40LL))(
                                      v119,
                                      &v150);
    v14 = 1295;
    if ( FileInfoFromParentEnumeration < 0 )
      goto LABEL_398;
    v112 = 1295;
    v14 = 1296;
    if ( v150 )
      goto LABEL_314;
    FileInfoFromParentEnumeration = 0;
    v112 = 1296;
    v184 = 0;
    v126 = 0;
    v91 = (struct _FILE_ID_128 *)(*(__int64 (__fastcall **)(struct IFileInfoFromDisk *, _BYTE *))(*(_QWORD *)v114 + 112LL))(
                                   v114,
                                   v199);
    v92 = v139;
    v138 = *v91;
    FileInfoFromParentEnumeration = CCuDBOperations::ItemExist(&v138, v139, &v126);
    v14 = 1312;
    if ( FileInfoFromParentEnumeration < 0 )
      goto LABEL_398;
    v112 = 1312;
    if ( !v126 )
    {
      v151 = 0;
      v93 = (*(__int64 (__fastcall **)(struct IFileInfoFromDisk *, _BYTE *))(*(_QWORD *)v114 + 112LL))(v114, v200);
      Item = CSimpleHashTable<_FILE_ID_128,unsigned int,CCuCallbackHandlerContext::CFileIDHash,CCuCallbackHandlerContext::CFileIDHash,CDefaultResizePolicy,CDefaultRehashPolicy>::GetItem(
               (char *)a4 + 256,
               v93,
               &v151);
      if ( Item < 0 )
      {
        if ( Item != -2147319765 )
        {
          FileInfoFromParentEnumeration = Item;
          v14 = 1347;
          goto LABEL_398;
        }
        v14 = 1347;
      }
      else
      {
        v95 = *(struct _FILE_ID_128 *)(*((_QWORD *)a4 + 12) + 16LL * v151);
        v96 = *((_QWORD *)a4 + 4);
        v138 = v95;
        if ( *(_BYTE *)(v151 + v96) || !memcmp_0(&v138, &Buf2, 0x10u) )
          goto LABEL_318;
        v168 = Buf1;
        v127 = 0;
        v138 = v95;
        FileInfoFromParentEnumeration = CCuDBOperations::IsDescendant(&v168, &v138, v92, &v127, 0);
        v14 = 1341;
        if ( FileInfoFromParentEnumeration < 0 )
          goto LABEL_398;
        v112 = 1341;
        v14 = 1342;
        if ( v127 )
        {
LABEL_314:
          FileInfoFromParentEnumeration = -2134375932;
          goto LABEL_398;
        }
      }
      v112 = v14;
LABEL_318:
      FileInfoFromParentEnumeration = -2134375930;
      v14 = 1350;
      goto LABEL_398;
    }
    v128 = 0;
    v97 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IFileInfoFromDisk *))(*(_QWORD *)v114 + 104LL))(v114);
    v138 = *(struct _FILE_ID_128 *)(*(__int64 (__fastcall **)(struct IFileInfoFromDisk *, _BYTE *))(*(_QWORD *)v114
                                                                                                  + 112LL))(
                                     v114,
                                     v201);
    FileInfoFromParentEnumeration = CCuDBOperations::ItemExist(&v138, v97, v92, &v128, &v184);
    v14 = 1354;
    if ( FileInfoFromParentEnumeration < 0 )
      goto LABEL_398;
    v98 = 0;
    v112 = 1354;
    if ( v128 )
    {
      if ( memcmp_0(&v184, &Buf1, 0x10u) )
      {
        v152 = 0;
        v153 = 0;
        FileInfoFromParentEnumeration = CSimpleHashTable<_FILE_ID_128,unsigned int,CCuCallbackHandlerContext::CFileIDHash,CCuCallbackHandlerContext::CFileIDHash,CDefaultResizePolicy,CDefaultRehashPolicy>::GetItem(
                                          (char *)a4 + 256,
                                          &Buf1,
                                          &v152);
        v14 = 1372;
        if ( FileInfoFromParentEnumeration >= 0 )
        {
          v112 = 1372;
          *(struct _FILE_ID_128 *)(*((_QWORD *)a4 + 12) + 16LL * v152) = v184;
          v100 = CSimpleHashTable<_FILE_ID_128,unsigned int,CCuCallbackHandlerContext::CFileIDHash,CCuCallbackHandlerContext::CFileIDHash,CDefaultResizePolicy,CDefaultRehashPolicy>::GetItem(
                   (char *)a4 + 256,
                   &v184,
                   &v153);
          if ( v100 < 0 )
          {
            if ( v100 != -2147319765 )
            {
              FileInfoFromParentEnumeration = v100;
              v14 = 1388;
              goto LABEL_398;
            }
            v112 = 1388;
          }
          else
          {
            *(struct _FILE_ID_128 *)(*((_QWORD *)a4 + 16) + 16LL * v153) = Buf1;
          }
          FileInfoFromParentEnumeration = -2134375930;
          v14 = 1391;
        }
        goto LABEL_398;
      }
      v98 = 1;
      v99 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((char *)WPP_GLOBAL_Control + 68) >= 0
        || *((_BYTE *)WPP_GLOBAL_Control + 65) < 4u )
      {
        goto LABEL_328;
      }
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 35, &WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids);
    }
    v99 = (PVOID *)WPP_GLOBAL_Control;
LABEL_328:
    if ( a8 )
    {
      FileInfoFromParentEnumeration = CCuChangeConsumptionHandler::MoveUnderDescendantCheck(v114, v92, a4);
      v14 = 1401;
      if ( FileInfoFromParentEnumeration < 0 )
        goto LABEL_398;
      v99 = (PVOID *)WPP_GLOBAL_Control;
      v112 = 1401;
    }
    v90 = 0;
    if ( !v98 )
    {
      if ( v99 != &WPP_GLOBAL_Control && *((char *)v99 + 68) < 0 && *((_BYTE *)v99 + 65) >= 4u )
        WPP_SF_qii(
          v99[7],
          36,
          &WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids,
          v119,
          *(_QWORD *)&Buf1.Identifier[8],
          *(_QWORD *)Buf1.Identifier);
      v90 = 1;
    }
    goto LABEL_344;
  }
LABEL_399:
  v109 = FileInfoFromParentEnumeration;
  ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(&v119);
  ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(&v114);
  ATL::CHeapPtr<unsigned short,ATL::CComAllocator>::~CHeapPtr<unsigned short,ATL::CComAllocator>(&v118);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&FileInfoFromParentEnumeration);
  return v109;
}

```

## disassembly

```asm
0x1801163e0  mov     rax, rsp
0x1801163e3  mov     [rax+10h], rbx
0x1801163e7  push    rbp
0x1801163e8  push    rsi
0x1801163e9  push    rdi
0x1801163ea  push    r12
0x1801163ec  push    r13
0x1801163ee  push    r14
0x1801163f0  push    r15
0x1801163f2  lea     rbp, [rax-318h]
0x1801163f9  sub     rsp, 3E0h
0x180116400  movaps  xmmword ptr [rax-48h], xmm6
0x180116404  mov     rax, cs:__security_cookie
0x18011640b  xor     rax, rsp
0x18011640e  mov     [rbp+310h+var_50], rax
0x180116415  mov     rbx, [rbp+310h+arg_20]
0x18011641c  mov     r14, r9
0x18011641f  mov     r15, [rbp+310h+arg_28]
0x180116426  mov     r13, r8
0x180116429  mov     rdi, [rbp+310h+arg_40]
0x180116430  mov     rsi, rcx
0x180116433  mov     r12, [rbp+310h+arg_30]
0x18011643a  mov     [rbp+310h+var_330], rbx
0x18011643e  mov     [rbp+310h+var_238], r15
0x180116445  mov     [rbp+310h+var_318], rdi
0x180116449  mov     [rbp+310h+var_308], r8
0x18011644d  mov     rax, cs:WPP_GLOBAL_Control
0x180116454  lea     rcx, WPP_GLOBAL_Control
0x18011645b  mov     edx, 6
0x180116460  cmp     rax, rcx
0x180116463  jz      short loc_180116491
0x180116465  test    byte ptr [rax+44h], 80h
0x180116469  jz      short loc_1801164A1
0x18011646b  cmp     [rax+41h], dl
0x18011646e  jb      short loc_180116491
0x180116470  mov     rcx, [rax+38h]
0x180116474  lea     r8, WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids
0x18011647b  mov     edx, 12h
0x180116480  call    WPP_SF_
0x180116485  mov     rax, cs:WPP_GLOBAL_Control
0x18011648c  mov     edx, 6
0x180116491  test    byte ptr [rax+44h], 80h
0x180116495  jz      short loc_1801164A1
0x180116497  cmp     [rax+41h], dl
0x18011649a  jb      short loc_1801164A1
0x18011649c  mov     r9b, 1
0x18011649f  jmp     short loc_1801164A4
0x1801164a1  xor     r9d, r9d; bool
0x1801164a4  mov     r8d, 1D1h; unsigned __int16
0x1801164aa  lea     rdx, aCcuchangeconsu_5; "CCuChangeConsumptionHandler::ChangeCons"...
0x1801164b1  lea     rcx, [rsp+410h+var_3A0]; this
0x1801164b6  call    ??0CEcsFunctionTracer@@QEAA@PEBDG_N@Z; CEcsFunctionTracer::CEcsFunctionTracer(char const *,ushort,bool)
0x1801164bb  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1801164c2  xor     eax, eax
0x1801164c4  lea     rcx, [rbp+310h+var_380]
0x1801164c8  xorps   xmm1, xmm1
0x1801164cb  mov     [rbp+310h+var_378], eax
0x1801164ce  movdqu  [rbp+310h+var_F0], xmm0
0x1801164d6  mov     [rbp+310h+var_360], rax
0x1801164da  xor     edx, edx
0x1801164dc  xorps   xmm0, xmm0
0x1801164df  movups  [rbp+310h+Buf2], xmm0
0x1801164e6  movups  xmmword ptr [rbp+310h+var_1B0.Identifier], xmm0
0x1801164ed  movups  [rbp+310h+Buf1], xmm1
0x1801164f4  movups  [rbp+310h+var_180], xmm1
0x1801164fb  call    ??0?$CComPtrBase@UIFileInfoFromDisk@@@ATL@@IEAA@PEAUIFileInfoFromDisk@@@Z; ATL::CComPtrBase<IFileInfoFromDisk>::CComPtrBase<IFileInfoFromDisk>(IFileInfoFromDisk *)
0x180116500  xor     eax, eax
0x180116502  lea     rcx, [rbp+310h+var_358]
0x180116506  mov     [rbp+310h+var_2D8], rax
0x18011650a  mov     [rbp+310h+var_320], eax
0x18011650d  call    ??0?$CComPtr@UIFileConcurrencyBlob@@@ATL@@QEAA@XZ; ATL::CComPtr<IFileConcurrencyBlob>::CComPtr<IFileConcurrencyBlob>(void)
0x180116512  xorps   xmm0, xmm0
0x180116515  xor     eax, eax
0x180116517  mov     rcx, r15
0x18011651a  mov     [rbp+310h+var_128], rax
0x180116521  movups  [rbp+310h+var_138], xmm0
0x180116528  call    ??$EcsZeroOut@_N@@YAXPEA_N@Z; EcsZeroOut<bool>(bool *)
0x18011652d  xor     ecx, ecx
0x18011652f  mov     eax, 1ECh
0x180116534  test    rsi, rsi
0x180116537  jz      loc_1801189C3
0x18011653d  mov     [rsp+410h+var_39C], ax
0x180116542  mov     eax, 1EDh
0x180116547  test    r13, r13
0x18011654a  jz      loc_1801189C3
0x180116550  mov     [rsp+410h+var_39C], ax
0x180116555  mov     eax, 1EEh
0x18011655a  test    r14, r14
0x18011655d  jz      loc_1801189C3
0x180116563  mov     [rsp+410h+var_39C], ax
0x180116568  mov     eax, 1EFh
0x18011656d  test    rbx, rbx
0x180116570  jz      loc_1801189C3
0x180116576  mov     [rsp+410h+var_39C], ax
0x18011657b  mov     eax, 1F0h
0x180116580  test    r15, r15
0x180116583  jz      loc_1801189C3
0x180116589  mov     [rsp+410h+var_3A0], ecx
0x18011658d  lea     rdx, [rbp+310h+var_F0]
0x180116594  mov     [rsp+410h+var_39C], ax
0x180116599  mov     rcx, [r13+0]
0x18011659d  mov     [rbp+310h+var_2F0], rcx
0x1801165a1  mov     rax, [rcx]
0x1801165a4  mov     rax, [rax+20h]
0x1801165a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801165ad  mov     [rsp+410h+var_3A0], eax
0x1801165b1  test    eax, eax
0x1801165b3  mov     eax, 1FAh
0x1801165b8  js      loc_1801189CB
0x1801165be  mov     [rsp+410h+var_39C], ax
0x1801165c3  mov     rcx, [r13+8]
0x1801165c7  test    rcx, rcx
0x1801165ca  jz      short loc_1801165EE
0x1801165cc  mov     rax, [rcx]
0x1801165cf  mov     rax, [rax+30h]
0x1801165d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801165d8  mov     [rsp+410h+var_3A0], eax
0x1801165dc  test    eax, eax
0x1801165de  mov     eax, 1FEh
0x1801165e3  js      loc_1801189CB
0x1801165e9  mov     [rsp+410h+var_39C], ax
0x1801165ee  mov     rax, [rsi]
0x1801165f1  lea     rdx, [rbp+310h+var_378]
0x1801165f5  mov     rcx, rsi
0x1801165f8  mov     rax, [rax+38h]
0x1801165fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116601  mov     [rsp+410h+var_3A0], eax
0x180116605  test    eax, eax
0x180116607  mov     eax, 201h
0x18011660c  js      loc_1801189CB
0x180116612  mov     [rsp+410h+var_39C], ax
0x180116617  lea     rcx, [rbp+310h+var_360]
0x18011661b  mov     rax, [rsi]
0x18011661e  mov     rbx, [rax+18h]
0x180116622  call    ??I?$CHeapPtrBase@GVCComAllocator@ATL@@@ATL@@QEAAPEAPEAGXZ; ATL::CHeapPtrBase<ushort,ATL::CComAllocator>::operator&(void)
0x180116627  mov     rdx, rax
0x18011662a  mov     rcx, rsi
0x18011662d  mov     rax, rbx
0x180116630  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116635  xor     ebx, ebx
0x180116637  mov     [rsp+410h+var_3A0], eax
0x18011663b  mov     r15d, 202h
0x180116641  test    eax, eax
0x180116643  jns     short loc_180116650
0x180116645  mov     [rsp+410h+var_39A], r15w
0x18011664b  jmp     loc_1801189D0
0x180116650  mov     [rsp+410h+var_39C], r15w
0x180116656  lea     rdx, [rbp+310h+Buf1]
0x18011665d  mov     rax, [rsi]
0x180116660  mov     rcx, rsi
0x180116663  mov     rax, [rax+20h]
0x180116667  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011666c  mov     [rsp+410h+var_3A0], eax
0x180116670  test    eax, eax
0x180116672  mov     eax, 204h
0x180116677  js      loc_1801189CB
0x18011667d  mov     [rsp+410h+var_39C], ax
0x180116682  lea     rdx, [rbp+310h+var_1B0]
0x180116689  mov     rax, [rsi]
0x18011668c  mov     rcx, rsi
0x18011668f  mov     rax, [rax+50h]
0x180116693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116698  mov     [rsp+410h+var_3A0], eax
0x18011669c  test    eax, eax
0x18011669e  mov     eax, 205h
0x1801166a3  js      loc_1801189CB
0x1801166a9  mov     [rsp+410h+var_39C], ax
0x1801166ae  lea     rdx, [rbp+310h+var_180]
0x1801166b5  mov     rax, [rsi]
0x1801166b8  mov     rcx, rsi
0x1801166bb  mov     rax, [rax+28h]
0x1801166bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801166c4  mov     [rsp+410h+var_3A0], eax
0x1801166c8  test    eax, eax
0x1801166ca  mov     eax, 206h
0x1801166cf  js      loc_1801189CB
0x1801166d5  mov     [rsp+410h+var_39C], ax
0x1801166da  lea     rdx, [rbp+310h+var_2D8]
0x1801166de  mov     rax, [rsi]
0x1801166e1  mov     rcx, rsi
0x1801166e4  mov     rax, [rax+40h]
0x1801166e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801166ed  mov     [rsp+410h+var_3A0], eax
0x1801166f1  test    eax, eax
0x1801166f3  mov     eax, 208h
0x1801166f8  js      loc_1801189CB
0x1801166fe  mov     [rsp+410h+var_39C], ax
0x180116703  lea     rdx, [rbp+310h+var_320]
0x180116707  mov     rax, [rsi]
0x18011670a  mov     rcx, rsi
0x18011670d  mov     rax, [rax+30h]
0x180116711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116716  mov     [rsp+410h+var_3A0], eax
0x18011671a  test    eax, eax
0x18011671c  mov     eax, 209h
0x180116721  js      loc_1801189CB
0x180116727  mov     r9, qword ptr [rbp+310h+Buf1]
0x18011672e  mov     r8, qword ptr [rbp+310h+Buf1+8]
0x180116735  mov     [rsp+410h+var_39C], ax
0x18011673a  mov     rax, r9
0x18011673d  sub     rax, [r13+28h]
0x180116741  jnz     short loc_18011674A
0x180116743  mov     rax, r8
0x180116746  sub     rax, [r13+30h]
0x18011674a  test    rax, rax
0x18011674d  setz    [rbp+310h+var_368]
0x180116751  mov     rcx, cs:WPP_GLOBAL_Control
0x180116758  lea     rax, WPP_GLOBAL_Control
0x18011675f  cmp     rcx, rax
0x180116762  jz      short loc_1801167DA
0x180116764  test    byte ptr [rcx+44h], 80h
0x180116768  jz      short loc_1801167DA
0x18011676a  cmp     byte ptr [rcx+41h], 4
0x18011676e  jb      short loc_1801167DA
0x180116770  mov     rax, [rbp+310h+var_360]
0x180116774  mov     edx, 13h
0x180116779  mov     rcx, [rcx+38h]
0x18011677d  mov     [rsp+410h+var_3B0], rax
0x180116782  mov     eax, [rbp+310h+var_320]
0x180116785  mov     dword ptr [rsp+410h+var_3B8], eax
0x180116789  mov     eax, [rbp+310h+var_378]
0x18011678c  mov     [rsp+410h+var_3C0], eax
0x180116790  mov     rax, [rbp+310h+var_2D8]
0x180116794  mov     [rsp+410h+var_3C8], rax
0x180116799  mov     rax, qword ptr [rbp+310h+var_1B0.Identifier]
0x1801167a0  mov     qword ptr [rsp+410h+var_3D0], rax
0x1801167a5  mov     rax, qword ptr [rbp+310h+var_1B0.Identifier+8]
0x1801167ac  mov     qword ptr [rsp+410h+var_3D8], rax
0x1801167b1  mov     rax, qword ptr [rbp+310h+var_180]
0x1801167b8  mov     qword ptr [rsp+410h+var_3E0], r9
0x1801167bd  mov     r9, qword ptr [rbp+310h+var_180+8]
0x1801167c4  mov     [rsp+410h+var_3E8], r8
0x1801167c9  lea     r8, WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids
0x1801167d0  mov     [rsp+410h+var_3F0], rax
0x1801167d5  call    WPP_SF_iiiiiiiDDS
0x1801167da  mov     r8d, 10h; Size
0x1801167e0  lea     rdx, [rbp+310h+Buf2]; Buf2
0x1801167e7  lea     rcx, [rbp+310h+Buf1]; Buf1
0x1801167ee  call    memcmp_0
0x1801167f3  lea     r13, Format
0x1801167fa  test    eax, eax
0x1801167fc  jz      loc_180117144
0x180116802  mov     [rbp+310h+var_210], rbx
0x180116809  test    rdi, rdi
0x18011680c  jz      loc_1801168AF
0x180116812  lea     rdx, [rbp+310h+var_258]
0x180116819  mov     [rbp+310h+var_220], rbx
0x180116820  mov     rcx, rdi
0x180116823  mov     [rbp+310h+var_258], rbx
0x18011682a  call    ??$QueryInterface@UIFileSystemExtInterface@@@IUnknown@@QEAAJPEAPEAUIFileSystemExtInterface@@@Z; IUnknown::QueryInterface<IFileSystemExtInterface>(IFileSystemExtInterface * *)
0x18011682f  mov     [rsp+410h+var_3A0], eax
0x180116833  test    eax, eax
0x180116835  mov     eax, 22Bh
0x18011683a  jns     short loc_180116852
0x18011683c  lea     rcx, [rbp+310h+var_258]
0x180116843  mov     [rsp+410h+var_39A], ax
0x180116848  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18011684d  jmp     loc_1801189D0
0x180116852  mov     rcx, [rbp+310h+var_258]
0x180116859  lea     r9, [rbp+310h+var_220]
0x180116860  movaps  xmm0, [rbp+310h+Buf1]
0x180116867  lea     r8, [rbp+310h+var_230]
0x18011686e  mov     rbx, [rbp+310h+var_308]
0x180116872  mov     [rsp+410h+var_39C], ax
0x180116877  mov     rax, [rcx]
0x18011687a  movdqa  xmmword ptr [rbp+310h+var_230.Identifier], xmm0
0x180116882  mov     rdx, [rbx+40h]
0x180116886  mov     rax, [rax+20h]
0x18011688a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011688f  mov     rdx, [rbp+310h+var_220]
0x180116896  lea     rcx, [rbp+310h+var_380]
0x18011689a  mov     edi, eax
0x18011689c  call    ?Attach@?$CComPtrBase@UIFileInfoFromDisk@@@ATL@@QEAAXPEAUIFileInfoFromDisk@@@Z; ATL::CComPtrBase<IFileInfoFromDisk>::Attach(IFileInfoFromDisk *)
0x1801168a1  lea     rcx, [rbp+310h+var_258]
0x1801168a8  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x1801168ad  jmp     short loc_1801168F2
0x1801168af  movaps  xmm0, [rbp+310h+Buf1]
0x1801168b6  lea     r8, [rbp+310h+var_218]; struct IFileInfoFromDisk **
0x1801168bd  mov     [rbp+310h+var_218], rbx
0x1801168c4  lea     rdx, [rbp+310h+var_230]; struct _FILE_ID_128
0x1801168cb  mov     rbx, [rbp+310h+var_308]
0x1801168cf  movdqa  xmmword ptr [rbp+310h+var_230.Identifier], xmm0
0x1801168d7  mov     rcx, [rbx+40h]; void *
0x1801168db  call    ?CreateInstance@CNtfsFileInfoFromDisk@@SAJPEAXU_FILE_ID_128@@PEAPEAUIFileInfoFromDisk@@@Z; CNtfsFileInfoFromDisk::CreateInstance(void *,_FILE_ID_128,IFileInfoFromDisk * *)
0x1801168e0  mov     rdx, [rbp+310h+var_218]
0x1801168e7  lea     rcx, [rbp+310h+var_380]
0x1801168eb  mov     edi, eax
0x1801168ed  call    ?Attach@?$CComPtrBase@UIFileInfoFromDisk@@@ATL@@QEAAXPEAUIFileInfoFromDisk@@@Z; ATL::CComPtrBase<IFileInfoFromDisk>::Attach(IFileInfoFromDisk *)
0x1801168f2  cmp     edi, 0C0000022h
0x1801168f8  jnz     loc_180116AB0
0x1801168fe  test    byte ptr [rbp+310h+var_320], 10h
0x180116902  jnz     loc_1801170F1
0x180116908  mov     rax, [rbp+310h+var_360]
0x18011690c  xor     edi, edi
0x18011690e  test    rax, rax
0x180116911  mov     [rsp+410h+var_3E8], rdi
0x180116916  mov     rcx, r13
0x180116919  mov     edx, 80070005h
0x18011691e  cmovnz  rcx, rax
0x180116922  xor     r9d, r9d
  ... truncated ...
```
