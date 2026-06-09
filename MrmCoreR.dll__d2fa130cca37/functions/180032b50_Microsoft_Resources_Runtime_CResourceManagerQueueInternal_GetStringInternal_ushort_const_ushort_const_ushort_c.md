# Microsoft::Resources::Runtime::CResourceManagerQueueInternal::GetStringInternal(ushort const *,ushort const *,ushort const *,bool,ushort *,unsigned __int64,unsigned __int64 *)

- ea: `0x180032b50`
- end: `0x180033ee8`
- name: `?GetStringInternal@CResourceManagerQueueInternal@Runtime@Resources@Microsoft@@AEAAJPEBG00_NPEAG_KPEA_K@Z`
- size: `5016`
- prototype: `int(Microsoft::Resources::Runtime::CResourceManagerQueueInternal *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, bool, unsigned __int16 *, unsigned __int64, unsigned __int64 *)`
- caller_count: `3`
- callee_count: `39`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180032a00`
- `0x180032ab0`
- `0x18008da50`

## callees

- `0x180017960`
- `0x180018210`
- `0x18001f1b4`
- `0x180024004`
- `0x180027270`
- `0x1800279a8`
- `0x180028ad0`
- `0x18002c8d0`
- `0x18002cfd0`
- `0x18002d0c0`
- `0x18002eb8c`
- `0x180032458`
- `0x180032b50`
- `0x180033ef0`
- `0x180034528`
- `0x18003490c`
- `0x180034934`
- `0x180034c3c`
- `0x180034d84`
- `0x180034db4`
- `0x180035110`
- `0x180035680`
- `0x1800364a8`
- `0x1800371a8`
- `0x1800373f8`
- `0x18003bbf8`
- `0x18004619c`
- `0x180047cdc`
- `0x180072238`
- `0x1800774fc`
- `0x180078864`
- `0x18007be80`
- `0x1800862f0`
- `0x18008679c`
- `0x1800867dc`
- `0x180086800`
- `0x180086e06`
- `0x180086f28`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180032c46`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180032c46`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800330fd`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800330fd`
- `api-ms-win-core-localization-private-l1-1-0!_GetMUIStringFromCache` at `0x180033225`
- `api-ms-win-core-localization-private-l1-1-0!_GetMUIStringFromCache` at `0x18003325e`
- `api-ms-win-core-localization-private-l1-1-0!_GetMUIStringFromCache` at `0x180033225`
- `api-ms-win-core-localization-private-l1-1-0!_GetMUIStringFromCache` at `0x18003325e`
- `api-ms-win-core-localization-private-l1-1-0!_AddMUIStringToCache` at `0x180033eae`
- `api-ms-win-core-localization-private-l1-1-0!_AddMUIStringToCache` at `0x180033eae`
- `api-ms-win-core-localization-private-l1-1-0!_OpenMuiStringCache` at `0x1800331fa`
- `api-ms-win-core-localization-private-l1-1-0!_OpenMuiStringCache` at `0x1800331fa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180033543`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180033543`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180033606`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180033606`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800338b3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800338b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800338c1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800338c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033e17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033e17`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180033e2a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180033e2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033dde`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033de9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033e22`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033e50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033e79`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033e84`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033e8f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033e9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033ebd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033ec8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033ed3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033dde`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033de9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033e22`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033e50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033e79`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033e84`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033e8f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033e9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033ebd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033ec8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033ed3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800335cf`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800335cf`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180033094`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180033094`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180033168`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180033168`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033179`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033292`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033988`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033cc6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033d38`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033179`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033292`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033988`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033cc6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033d38`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180033126`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180033126`

## string_xrefs

- `0x1800330d0`: `Software\Classes\Local Settings\MrtCache`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Resources::Runtime::CResourceManagerQueueInternal::GetStringInternal(
        Microsoft::Resources::Runtime::CResourceManagerQueueInternal *this,
        const unsigned __int16 *a2,
        struct Microsoft::Resources::Runtime::CResourceIndexInternal *a3,
        unsigned __int16 *a4,
        bool a5,
        unsigned __int16 *a6,
        unsigned __int64 a7,
        unsigned __int64 *a8)
{
  unsigned __int16 *v9; // rcx
  Microsoft::Resources::Runtime::CResourceManagerInternal *v10; // r14
  unsigned int v11; // r15d
  __int64 v12; // rdx
  unsigned __int64 v13; // rax
  __int64 v14; // rsi
  wchar_t *v15; // rax
  wchar_t *v16; // r10
  unsigned __int64 v17; // rcx
  __int64 v18; // rbx
  const unsigned __int16 *v19; // rdx
  __int64 v20; // r8
  WCHAR *v21; // r9
  unsigned __int16 v22; // ax
  int FullyQualifiedReferenceType; // edi
  WCHAR *v24; // rcx
  unsigned __int16 *v25; // rdx
  unsigned __int64 v26; // rcx
  __int64 v27; // r8
  unsigned __int16 *v28; // r9
  unsigned __int16 v29; // ax
  unsigned __int16 *v30; // rcx
  unsigned __int64 v31; // rbx
  unsigned int v32; // esi
  __int64 v33; // rdx
  struct std::nothrow_t *v34; // rdx
  unsigned int EscapedPriPathFromPackageFullName; // edi
  void *v36; // rcx
  void *v37; // rcx
  WCHAR *v38; // rcx
  __int64 v39; // rdx
  WCHAR *v40; // r8
  WCHAR v41; // ax
  unsigned int v42; // ebx
  WCHAR *v43; // rcx
  const struct std::nothrow_t *v44; // rdx
  void *v45; // rcx
  void *v46; // rcx
  _QWORD *v47; // rdi
  void (__fastcall ***v49)(_QWORD, __int64); // rdi
  int v50; // ebx
  struct Microsoft::Resources::Runtime::CResourceIndexInternal *v51; // rsi
  char v52; // bl
  LSTATUS Key; // ebx
  __int64 v54; // r11
  HANDLE v55; // rsi
  unsigned int v56; // ecx
  int MUIStringFromCache; // eax
  unsigned int v58; // ebx
  const struct std::nothrow_t *v59; // rdx
  void *v60; // rcx
  void *v61; // rcx
  __int64 v62; // rcx
  WCHAR *v63; // rdx
  __int64 v64; // r8
  WCHAR *v65; // r9
  WCHAR v66; // ax
  unsigned int v67; // edi
  WCHAR *v68; // rcx
  void *v69; // rcx
  void *v70; // rcx
  const struct std::nothrow_t *v71; // rdx
  void *v72; // rcx
  void *v73; // rcx
  Microsoft::Resources::Runtime::CContext *v74; // r12
  int i; // ebx
  __int64 v76; // r14
  __int64 v77; // rcx
  const WCHAR *v78; // rcx
  int v79; // eax
  volatile signed __int32 *v80; // rdx
  void *v81; // rax
  void *v82; // rax
  Microsoft::Resources::Runtime::CResourceManagerInternal *v83; // rax
  Microsoft::Resources::Runtime::CResourceManagerInternal *v84; // r14
  const struct std::nothrow_t *v85; // rdx
  void *v86; // rcx
  void *v87; // rcx
  _BYTE *v88; // r9
  WCHAR *v89; // r8
  int v90; // eax
  unsigned int v91; // ebx
  __int64 v92; // rcx
  int v93; // eax
  unsigned int v94; // ebx
  Microsoft::Resources::Runtime::CResourceManagerInternal *v95; // r15
  int v96; // eax
  unsigned int v97; // ebx
  Microsoft::Resources::Runtime::CContext *v98; // rbx
  struct Microsoft::Resources::Runtime::CResourceIndexInternal *v99; // r14
  int ApplicationResources; // eax
  unsigned int v101; // r14d
  unsigned int v102; // edx
  int v103; // r14d
  int v104; // ecx
  wchar_t *v105; // rbx
  __int64 v106; // rax
  unsigned __int64 v107; // r15
  HANDLE ProcessHeap; // rax
  const struct std::nothrow_t *v109; // rdx
  void *v110; // rcx
  void *v111; // rcx
  const struct std::nothrow_t *v112; // rdx
  void *v113; // rcx
  void *v114; // rcx
  Microsoft::Resources::Runtime::CResourceManagerInternal *v115; // rcx
  void *v116; // rcx
  void *v117; // rcx
  unsigned int v118; // edx
  void *v119; // rcx
  void *v120; // rcx
  DWORD LastError; // ebx
  int v122; // eax
  unsigned int v123; // ebx
  int v124; // eax
  unsigned int v125; // r14d
  int dwOptions; // [rsp+20h] [rbp-E0h]
  struct std::nothrow_t **dwOptionsa; // [rsp+20h] [rbp-E0h]
  bool v128; // [rsp+60h] [rbp-A0h] BYREF
  void *v129; // [rsp+68h] [rbp-98h] BYREF
  void *v130; // [rsp+70h] [rbp-90h] BYREF
  void *Block; // [rsp+78h] [rbp-88h] BYREF
  HANDLE hObject; // [rsp+80h] [rbp-80h] BYREF
  char v133; // [rsp+88h] [rbp-78h]
  void **v134; // [rsp+90h] [rbp-70h] BYREF
  Microsoft::Resources::Runtime::CResourceManagerInternal *v135; // [rsp+98h] [rbp-68h]
  HKEY phkResult; // [rsp+A0h] [rbp-60h] BYREF
  void **v137; // [rsp+A8h] [rbp-58h] BYREF
  void (__fastcall ***v138)(_QWORD, __int64); // [rsp+B0h] [rbp-50h]
  int Value[2]; // [rsp+B8h] [rbp-48h] BYREF
  struct std::nothrow_t *v140; // [rsp+C0h] [rbp-40h] BYREF
  char v141; // [rsp+C8h] [rbp-38h]
  unsigned int v142; // [rsp+D0h] [rbp-30h]
  wchar_t *Destination; // [rsp+D8h] [rbp-28h]
  struct Microsoft::Resources::Runtime::CResourceIndexInternal *v144; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE *v145; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v146[24]; // [rsp+F0h] [rbp-10h] BYREF
  wchar_t *Source; // [rsp+108h] [rbp+8h]
  unsigned __int16 *v148; // [rsp+110h] [rbp+10h]
  unsigned __int64 *v149; // [rsp+118h] [rbp+18h]
  __int128 v150; // [rsp+120h] [rbp+20h] BYREF
  int v151; // [rsp+130h] [rbp+30h]
  char v152; // [rsp+134h] [rbp+34h]
  void (__fastcall ***v153)(_QWORD, __int64); // [rsp+138h] [rbp+38h]
  __int128 v154; // [rsp+140h] [rbp+40h]
  __int64 v155; // [rsp+150h] [rbp+50h]
  char v156[40]; // [rsp+158h] [rbp+58h] BYREF
  __int128 FileInformation; // [rsp+180h] [rbp+80h] BYREF
  __int128 v158; // [rsp+190h] [rbp+90h]
  int v159; // [rsp+1A0h] [rbp+A0h]
  wchar_t Buffer[8]; // [rsp+1A8h] [rbp+A8h] BYREF
  __int16 v161; // [rsp+1B8h] [rbp+B8h]
  unsigned __int16 v162[24]; // [rsp+1C0h] [rbp+C0h] BYREF
  WCHAR FileName[280]; // [rsp+1F0h] [rbp+F0h] BYREF
  unsigned __int16 v164[280]; // [rsp+420h] [rbp+320h] BYREF
  _BYTE v165[560]; // [rsp+650h] [rbp+550h] BYREF
  WCHAR SubKey[544]; // [rsp+880h] [rbp+780h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D08h] [rbp+C08h]

  v148 = a4;
  v144 = a3;
  v9 = a6;
  Destination = a6;
  v149 = a8;
  if ( !a2 || !a6 )
    return 2147942487LL;
  Block = 0;
  v134 = &Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>::`vftable';
  v10 = 0;
  v135 = 0;
  hObject = 0;
  *(_OWORD *)Buffer = 0;
  v161 = 0;
  if ( a8 )
    *a8 = 0;
  v11 = 0;
  Value[0] = 0;
  v12 = -1;
  v13 = -1;
  do
    ++v13;
  while ( a2[v13] );
  if ( v13 < 0x19 )
    goto LABEL_34;
  if ( *a2 != 64 )
    goto LABEL_34;
  if ( a2[1] != 123 )
    goto LABEL_34;
  v14 = 2 * v13;
  if ( a2[v13 - 1] != 125 )
    goto LABEL_34;
  v15 = wcschr(a2, 0x3Fu);
  v16 = v15;
  if ( !v15 )
  {
LABEL_33:
    v12 = -1;
    v9 = Destination;
    do
LABEL_34:
      ++v12;
    while ( a2[v12] );
    v31 = v12 + 1;
    if ( v12 + 1 > a7 )
    {
      v32 = -2147024774;
    }
    else
    {
      wcscpy_s(v9, v12 + 1, a2);
      v32 = 1;
    }
    if ( a8 )
      *a8 = v31;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<void (*)(void *),&void _DefCloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<void (*)(void *),&void _DefCloseHandle(void *)>>(&hObject);
    Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>::Release(&v134);
    Microsoft::WRL::ComPtr<wil::details::RefCountedContainer<Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>>>::InternalRelease(&Block);
    return v32;
  }
  v17 = v15 - a2 - 2;
  v18 = 2147483646;
  if ( v17 > 0x7FFFFFFE )
  {
    FullyQualifiedReferenceType = -2147024809;
    FileName[0] = 0;
LABEL_37:
    v33 = 157;
    goto LABEL_38;
  }
  v19 = a2 + 2;
  v20 = 276;
  v21 = FileName;
  do
  {
    if ( !v17 )
      break;
    v22 = *v19;
    if ( !*v19 )
      break;
    ++v19;
    *v21++ = v22;
    --v17;
    --v20;
  }
  while ( v20 );
  FullyQualifiedReferenceType = -2147024774;
  if ( v20 )
    FullyQualifiedReferenceType = 0;
  v24 = v21 - 1;
  if ( v20 )
    v24 = v21;
  *v24 = 0;
  if ( !v20 )
    goto LABEL_37;
  v25 = v16 + 1;
  v26 = ((__int64)a2 + v14 - (__int64)(v16 + 1) - 2) >> 1;
  if ( v26 > 0x7FFFFFFE )
  {
    FullyQualifiedReferenceType = -2147024809;
    v164[0] = 0;
LABEL_266:
    v33 = 162;
    goto LABEL_38;
  }
  v27 = 276;
  v28 = v164;
  do
  {
    if ( !v26 )
      break;
    v29 = *v25;
    if ( !*v25 )
      break;
    ++v25;
    *v28++ = v29;
    --v26;
    --v27;
  }
  while ( v27 );
  FullyQualifiedReferenceType = -2147024774;
  if ( v27 )
    FullyQualifiedReferenceType = 0;
  v30 = v28 - 1;
  if ( v27 )
    v30 = v28;
  *v30 = 0;
  if ( !v27 )
    goto LABEL_266;
  v128 = 0;
  if ( (int)Microsoft::Resources::Runtime::CMrtUriParser::IsMrtUriReference(v164, &v128, 0) < 0 || !v128 )
    goto LABEL_33;
  FullyQualifiedReferenceType = Microsoft::Resources::Runtime::CResourceReferenceHandlerInternal::s_GetFullyQualifiedReferenceType(
                                  FileName,
                                  (enum Microsoft::Resources::Runtime::FULLY_QUALIFIED_REFERENCE_TYPE *)Value);
  v11 = Value[0];
  if ( FullyQualifiedReferenceType >= 0 )
    goto LABEL_39;
  v33 = 171;
LABEL_38:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v33,
    (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourcereferencehandlerinternal.cpp",
    (const char *)(unsigned int)FullyQualifiedReferenceType,
    dwOptions);
  if ( FullyQualifiedReferenceType < 0 )
    goto LABEL_33;
LABEL_39:
  v130 = 0;
  v129 = 0;
  v137 = &Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::MrmProfile>::`vftable';
  v138 = 0;
  v142 = 0;
  FileInformation = (unsigned __int64)&v129;
  LOBYTE(v158) = 1;
  *(_QWORD *)Value = &v130;
  v140 = 0;
  v141 = 1;
  dwOptionsa = &v140;
  EscapedPriPathFromPackageFullName = Microsoft::Resources::Runtime::CResourceManagerQueueInternal::GetEscapedPriPathFromPackageFullName(
                                        0,
                                        FileName,
                                        v164,
                                        v11);
  if ( v141 )
  {
    v36 = **(void ***)Value;
    v34 = v140;
    **(_QWORD **)Value = v140;
    if ( v36 )
      operator delete(v36, v34);
  }
  if ( (_BYTE)v158 )
  {
    v34 = (struct std::nothrow_t *)FileInformation;
    v37 = *(void **)FileInformation;
    *(_QWORD *)FileInformation = *((_QWORD *)&FileInformation + 1);
    if ( v37 )
      operator delete(v37, v34);
  }
  if ( (EscapedPriPathFromPackageFullName & 0x80000000) != 0 )
  {
    if ( EscapedPriPathFromPackageFullName == -2147023728
      || EscapedPriPathFromPackageFullName == -2147009737
      || EscapedPriPathFromPackageFullName == -2147024809 )
    {
      if ( v138 )
        (**v138)(v138, 1);
      v69 = v129;
      v129 = 0;
      if ( v69 )
        operator delete(v69, v34);
      v70 = v130;
      v130 = 0;
      if ( v70 )
        operator delete(v70, v34);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      Microsoft::WRL::ComPtr<wil::details::RefCountedContainer<Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>>>::InternalRelease(&Block);
      return EscapedPriPathFromPackageFullName;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x155,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourcemanagerqueueinternal.cpp",
        (const char *)EscapedPriPathFromPackageFullName,
        (int)&v140);
      v137 = &Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::MrmProfile>::`vftable';
      Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Build::AutoMergeBehavior>::Release(&v137);
      wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v129);
      wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v130);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<void (*)(void *),&void _DefCloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<void (*)(void *),&void _DefCloseHandle(void *)>>(&hObject);
      Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>::Release(&v134);
      Microsoft::WRL::ComPtr<wil::details::RefCountedContainer<Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>>>::InternalRelease(&Block);
      return EscapedPriPathFromPackageFullName;
    }
  }
  if ( v11 == 1 || v11 == 4 )
  {
    v62 = 2147483646;
    v63 = FileName;
    v64 = 276;
    v65 = (WCHAR *)v165;
    do
    {
      if ( !v62 )
        break;
      v66 = *v63;
      if ( !*v63 )
        break;
      ++v63;
      *v65++ = v66;
      --v62;
      --v64;
    }
    while ( v64 );
    v67 = -2147024774;
    if ( v64 )
      v67 = 0;
    v68 = v65 - 1;
    if ( v64 )
      v68 = v65;
    *v68 = 0;
    if ( !v64 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x15A,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourcemanagerqueueinternal.cpp",
        (const char *)v67,
        (int)&v140);
      v137 = &Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::MrmProfile>::`vftable';
      Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Build::AutoMergeBehavior>::Release(&v137);
      wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v129);
      wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v130);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<void (*)(void *),&void _DefCloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<void (*)(void *),&void _DefCloseHandle(void *)>>(&hObject);
      Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>::Release(&v134);
      Microsoft::WRL::ComPtr<wil::details::RefCountedContainer<Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>>>::InternalRelease(&Block);
      return v67;
    }
  }
  if ( ((v11 - 1) & 0xFFFFFFFC) == 0 && v11 != 2 )
  {
    v38 = (WCHAR *)v130;
    if ( v130 )
    {
      v39 = 276;
      v40 = FileName;
      do
      {
        if ( !v18 )
          break;
        v41 = *v38;
        if ( !*v38 )
          break;
        ++v38;
        *v40++ = v41;
        --v18;
        --v39;
      }
      while ( v39 );
      v42 = -2147024774;
      if ( v39 )
        v42 = 0;
      v43 = v40 - 1;
      if ( v39 )
        v43 = v40;
      *v43 = 0;
      if ( !v39 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x164,
          (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourcemanagerqueueinternal.cpp",
          (const char *)v42,
          (int)&v140);
        if ( v138 )
          (**v138)(v138, 1);
        v45 = v129;
        v129 = 0;
        if ( v45 )
          operator delete(v45, v44);
        v46 = v130;
        v130 = 0;
        if ( v46 )
          operator delete(v46, v44);
        if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(hObject);
        v47 = Block;
        if ( Block )
        {
          Block = 0;
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v47, 0xFFFFFFFF) == 1 )
          {
            v47[1] = &Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>::`vftable';
            Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>::Release(v47 + 1);
            operator delete(v47);
          }
        }
        return v42;
      }
    }
  }
  DefStringResult_InitBuf(v146);
  v145 = v146;
  v49 = v138;
  if ( a5 )
    goto LABEL_128;
  v50 = (int)v129;
  Value[0] = 0;
  v150 = 0;
  v151 = 0;
  v152 = 0;
  v153 = v138;
  v154 = 0;
  v155 = 0;
  Microsoft::Resources::StringResult::StringResult((Microsoft::Resources::StringResult *)v156);
  v51 = v144;
  if ( !v144 )
  {
    if ( (int)Microsoft::Resources::Runtime::CContextualHash::_GetHash(
                (Microsoft::Resources::Runtime::CContextualHash *)&v150,
                -1,
                0,
                (unsigned int *)Value) >= 0 )
      goto LABEL_73;
LABEL_127:
    Microsoft::Resources::Runtime::CContextualHash::~CContextualHash((Microsoft::Resources::Runtime::CContextualHash *)&v150);
    goto LABEL_128;
  }
  if ( !v152
    && (int)Microsoft::Resources::Runtime::CContextualHash::_Initialize((Microsoft::Resources::Runtime::CContextualHash *)&v150) < 0 )
  {
    goto LABEL_127;
  }
  LODWORD(phkResult) = 0;
  if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, struct Microsoft::Resources::Runtime::CResourceIndexInternal *, HKEY *))(**((_QWORD **)&v154 + 1) + 80LL))(
          *((_QWORD *)&v154 + 1),
          v51,
          &phkResult) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\ccontext.cpp",
      (const char *)0x80070490LL,
      (int)&v140);
    goto LABEL_127;
  }
  if ( (int)Microsoft::Resources::Runtime::CContextualHash::_GetHash(
              (Microsoft::Resources::Runtime::CContextualHash *)&v150,
              (int)phkResult,
              v148,
              (unsigned int *)Value) < 0 )
    goto LABEL_127;
LABEL_73:
  if ( Microsoft::Resources::Runtime::CContextualHash::GetQualifierList(
         (Microsoft::Resources::Runtime::CContextualHash *)&v150,
         (struct Microsoft::Resources::StringResult *)&v145) < 0 )
    goto LABEL_127;
  Microsoft::Resources::Runtime::CContextualHash::~CContextualHash((Microsoft::Resources::Runtime::CContextualHash *)&v150);
  if ( !itow_s(Value[0], Buffer, 9u, 16) )
  {
    FileInformation = 0;
    v158 = 0;
    v159 = 0;
    if ( GetFileAttributesExW(FileName, GetFileExInfoStandard, &FileInformation) )
    {
      LODWORD(dwOptionsa) = DWORD1(v158);
      StringCchPrintfW(v162, 0x14u, L"%x%x", DWORD2(v158), dwOptionsa);
      LODWORD(dwOptionsa) = v50;
      StringCchPrintfW(SubKey, 0x219u, L"%s\\%s", L"Software\\Classes\\Local Settings\\MrtCache");
      v52 = 1;
      goto LABEL_77;
    }
  }
LABEL_128:
  v52 = 0;
LABEL_77:
  if ( wcsnlen(FileName, 0x114u) >= 0x114 )
  {
LABEL_141:
    Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v145);
    if ( v49 )
      (**v49)(v49, 1);
    v72 = v129;
    v129 = 0;
    if ( v72 )
      operator delete(v72, v71);
    v73 = v130;
    v130 = 0;
    if ( v73 )
      operator delete(v73, v71);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    if ( v10 )
      Microsoft::Resources::Runtime::CResourceManagerInternal::`scalar deleting destructor'(v10, (unsigned int)v71);
    goto LABEL_110;
  }
  if ( !v52 )
  {
LABEL_154:
    v74 = 0;
    phkResult = 0;
    AcquireSRWLockShared(&SRWLock);
    Microsoft::WRL::ComPtr<wil::details::RefCountedContainer<Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>>>::InternalRelease(&Block);
    for ( i = 0; i < dword_1800FC488; ++i )
    {
      v76 = 40LL * i;
      v77 = *(_QWORD *)(v76 + g_ResManQueue);
      if ( v77 && (*(_QWORD *)v77 || !*(_DWORD *)(v77 + 8)) && (*(_DWORD *)(v77 + 8) || !*(_QWORD *)v77) )
      {
        v78 = *(const WCHAR **)(v77 + 16);
        if ( v78 )
        {
          v79 = CompareStringOrdinal(v78, -1, FileName, -1, 1);
          if ( !(unsigned int)IntToComparison((unsigned int)(v79 - 2)) )
          {
            v80 = *(volatile signed __int32 **)(v76 + g_ResManQueue + 32);
            v81 = Block;
            if ( Block != v80 )
            {
              if ( v80 )
              {
                _InterlockedIncrement(v80);
                v81 = Block;
              }
              *(_QWORD *)Value = v81;
              Block = (void *)v80;
              Microsoft::WRL::ComPtr<wil::details::RefCountedContainer<Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>>>::InternalRelease(Value);
            }
            break;
          }
        }
      }
    }
    ReleaseSRWLockShared(&SRWLock);
    v128 = 0;
    v82 = Block;
    if ( !Block )
    {
      v83 = (Microsoft::Resources::Runtime::CResourceManagerInternal *)operator new(
                                                                         0xC8u,
                                                                         (const struct std::nothrow_t *)byte_1800DE361);
      if ( !v83
        || (v84 = (Microsoft::Resources::Runtime::CResourceManagerInternal *)Microsoft::Resources::Runtime::CResourceManagerInternal::CResourceManagerInternal(v83),
            (v135 = v84) == 0) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1CA,
          (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourcemanagerqueueinternal.cpp",
          (const char *)0x8007000ELL,
          (int)dwOptionsa);
        Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v145);
        if ( v49 )
          (**v49)(v49, 1);
        v86 = v129;
        v129 = 0;
        if ( v86 )
          operator delete(v86, v85);
        v87 = v130;
        v130 = 0;
        if ( v87 )
          operator delete(v87, v85);
        if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(hObject);
        Microsoft::WRL::ComPtr<wil::details::RefCountedContainer<Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>>>::InternalRelease(&Block);
        return 2147942414LL;
      }
      if ( v11 == 1 || v11 == 4 )
        v88 = v165;
      else
        v88 = 0;
      if ( v11 - 2 > 1 )
        v89 = 0;
      else
        v89 = FileName;
      LODWORD(dwOptionsa) = 0;
      v90 = Microsoft::Resources::Runtime::CResourceManagerInternal::InitializeWithProfile(v84, v142, v89, v88);
      v91 = v90;
      if ( v90 < 0 )
      {
        if ( v90 == -2147009760 || v90 == -2147024882 )
        {
          Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v145);
          if ( v49 )
            (**v49)(v49, 1);
          v110 = v129;
          v129 = 0;
          if ( v110 )
            operator delete(v110, v109);
          v111 = v130;
          v130 = 0;
          if ( v111 )
            operator delete(v111, v109);
          if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            CloseHandle(hObject);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1D4,
            (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourcemanagerqueueinternal.cpp",
            (const char *)(unsigned int)v90,
            0);
          Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v145);
          if ( v49 )
            (**v49)(v49, 1);
          v116 = v129;
          v129 = 0;
          if ( v116 )
            operator delete(v116, v109);
          v117 = v130;
          v130 = 0;
          if ( v117 )
            operator delete(v117, v109);
          if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            CloseHandle(hObject);
        }
        Microsoft::Resources::Runtime::CResourceManagerInternal::`scalar deleting destructor'(v84, (unsigned int)v109);
        Microsoft::WRL::ComPtr<wil::details::RefCountedContainer<Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>>>::InternalRelease(&Block);
        return v91;
      }
      Microsoft::WRL::ComPtr<wil::details::RefCountedContainer<Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>>>::InternalRelease(&Block);
      v93 = Microsoft::Resources::Runtime::CResourceManagerQueueInternal::CreateRefCountedManager(v92, &v134, &Block);
      v94 = v93;
      if ( v93 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1D6,
          (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourcemanagerqueueinternal.cpp",
          (const char *)(unsigned int)v93,
          0);
        Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v145);
        v137 = &Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::MrmProfile>::`vftable';
        Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Build::AutoMergeBehavior>::Release(&v137);
        wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v129);
        wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v130);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<void (*)(void *),&void _DefCloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<void (*)(void *),&void _DefCloseHandle(void *)>>(&hObject);
        v134 = &Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>::`vftable';
        Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>::Release(&v134);
        Microsoft::WRL::ComPtr<wil::details::RefCountedContainer<Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>>>::InternalRelease(&Block);
        return v94;
      }
      v128 = 1;
      v82 = Block;
    }
    *(_QWORD *)&FileInformation = &g_ResManQueue;
    *((_QWORD *)&FileInformation + 1) = FileName;
    *(_QWORD *)&v158 = &v128;
    *((_QWORD *)&v158 + 1) = &Block;
    LOBYTE(v159) = 1;
    *(_QWORD *)Value = &Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CContext>::`vftable';
    v140 = 0;
    v95 = (Microsoft::Resources::Runtime::CResourceManagerInternal *)*((_QWORD *)v82 + 2);
    v96 = Microsoft::Resources::Runtime::CResourceManagerInternal::ResetDefaultContext(
            v95,
            (const struct Microsoft::Resources::Runtime::CContext **)&phkResult);
    v97 = v96;
    if ( v96 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1F2,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourcemanagerqueueinternal.cpp",
        (const char *)(unsigned int)v96,
        (int)dwOptionsa);
      Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CContext>::~AutoDeletePtr<Microsoft::Resources::Runtime::CContext>(Value);
      wil::details::lambda_call__lambda_5fdaf3d3394d7722bc4889b5da3c4151___::reset(&FileInformation);
      Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v145);
      v137 = &Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::MrmProfile>::`vftable';
      Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Build::AutoMergeBehavior>::Release(&v137);
      wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v129);
      wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v130);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<void (*)(void *),&void _DefCloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<void (*)(void *),&void _DefCloseHandle(void *)>>(&hObject);
      v134 = &Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>::`vftable';
      Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>::Release(&v134);
      Microsoft::WRL::ComPtr<wil::details::RefCountedContainer<Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>>>::InternalRelease(&Block);
      return v97;
    }
    v98 = 0;
    v99 = v144;
    if ( v144 && v148 )
    {
      v122 = Microsoft::Resources::Runtime::CContext::Clone((Microsoft::Resources::Runtime::CContext *)phkResult, &v140);
      v123 = v122;
      if ( v122 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1F5,
          (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourcemanagerqueueinternal.cpp",
          (const char *)(unsigned int)v122,
          (int)dwOptionsa);
        Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CContext>::~AutoDeletePtr<Microsoft::Resources::Runtime::CContext>(Value);
        wil::details::lambda_call__lambda_5fdaf3d3394d7722bc4889b5da3c4151___::reset(&FileInformation);
        Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v145);
        v137 = &Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::MrmProfile>::`vftable';
        Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Build::AutoMergeBehavior>::Release(&v137);
        wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v129);
        wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v130);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<void (*)(void *),&void _DefCloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<void (*)(void *),&void _DefCloseHandle(void *)>>(&hObject);
        v134 = &Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>::`vftable';
        Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>::Release(&v134);
        Microsoft::WRL::ComPtr<wil::details::RefCountedContainer<Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>>>::InternalRelease(&Block);
        return v123;
      }
      v74 = v140;
      v98 = v140;
      v124 = Microsoft::Resources::Runtime::CContext::SetAttributeValue(v140, v99, v148, 32);
      v125 = v124;
      if ( v124 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1F6,
          (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourcemanagerqueueinternal.cpp",
          (const char *)(unsigned int)v124,
          (int)dwOptionsa);
        Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CContext>::~AutoDeletePtr<Microsoft::Resources::Runtime::CContext>(Value);
        wil::details::lambda_call__lambda_5fdaf3d3394d7722bc4889b5da3c4151___::reset(&FileInformation);
        Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v145);
        v137 = &Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::MrmProfile>::`vftable';
        Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Build::AutoMergeBehavior>::Release(&v137);
        wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v129);
        wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v130);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<void (*)(void *),&void _DefCloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<void (*)(void *),&void _DefCloseHandle(void *)>>(&hObject);
        v134 = &Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>::`vftable';
        Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>::Release(&v134);
        Microsoft::WRL::ComPtr<wil::details::RefCountedContainer<Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>>>::InternalRelease(&Block);
        return v125;
      }
    }
    v144 = 0;
    ApplicationResources = Microsoft::Resources::Runtime::CResourceManagerInternal::GetApplicationResources(v95, &v144);
    v101 = ApplicationResources;
    if ( ApplicationResources < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1FB,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourcemanagerqueueinternal.cpp",
        (const char *)(unsigned int)ApplicationResources,
        (int)dwOptionsa);
      Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CContext>::~AutoDeletePtr<Microsoft::Resources::Runtime::CContext>(Value);
      wil::details::lambda_call__lambda_5fdaf3d3394d7722bc4889b5da3c4151___::reset(&FileInformation);
      Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v145);
      v137 = &Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::MrmProfile>::`vftable';
      Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Build::AutoMergeBehavior>::Release(&v137);
      wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v129);
      wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v130);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<void (*)(void *),&void _DefCloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<void (*)(void *),&void _DefCloseHandle(void *)>>(&hObject);
      v134 = &Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>::`vftable';
      Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>::Release(&v134);
      Microsoft::WRL::ComPtr<wil::details::RefCountedContainer<Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>>>::InternalRelease(&Block);
      return v101;
    }
    v133 = 0;
    Source = 0;
    v103 = Microsoft::Resources::Runtime::CResourceIndexInternal::_GetValue(v144, v164, 0, 0);
    if ( (unsigned int)(v103 + 2147009780) <= 0x13 && (v104 = 526337, _bittest(&v104, v103 + 2147009780))
      || v103 == -2147024875 )
    {
      if ( v98 )
        Microsoft::Resources::Runtime::CContext::`scalar deleting destructor'(v98, v102);
      wil::details::lambda_call__lambda_5fdaf3d3394d7722bc4889b5da3c4151___::reset(&FileInformation);
      Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v145);
      if ( v49 )
        (**v49)(v49, 1);
      v113 = v129;
      v129 = 0;
      if ( v113 )
        operator delete(v113, v112);
      v114 = v130;
      v130 = 0;
      if ( v114 )
        operator delete(v114, v112);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      v115 = v135;
      if ( !v135 )
        goto LABEL_202;
    }
    else
    {
      if ( v103 >= 0 )
      {
        v105 = Source;
        v106 = -1;
        do
          ++v106;
        while ( Source[v106] );
        v107 = v106 + 1;
        if ( v106 + 1 > a7 )
        {
          v103 = -2147024774;
        }
        else
        {
          wcscpy_s(Destination, v106 + 1, Source);
          v105 = Source;
        }
        if ( v149 )
          *v149 = v107;
        if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        {
          _AddMUIStringToCache(hObject, a2, v105, (unsigned int)v107);
          v105 = Source;
        }
        if ( v133 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v105);
        }
        if ( v103 < 0 )
        {
          Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CContext>::~AutoDeletePtr<Microsoft::Resources::Runtime::CContext>(Value);
          wil::details::lambda_call__lambda_5fdaf3d3394d7722bc4889b5da3c4151___::reset(&FileInformation);
          Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v145);
          v137 = &Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::MrmProfile>::`vftable';
          Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Build::AutoMergeBehavior>::Release(&v137);
          wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v129);
          wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v130);
          wil::details::unique_storage<wil::details::handle_null_resource_policy<void (*)(void *),&void _DefCloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<void (*)(void *),&void _DefCloseHandle(void *)>>(&hObject);
          v134 = &Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>::`vftable';
          Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>::Release(&v134);
          Microsoft::WRL::ComPtr<wil::details::RefCountedContainer<Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>>>::InternalRelease(&Block);
          return 2147942522LL;
        }
        if ( v74 )
          Microsoft::Resources::Runtime::CContext::`scalar deleting destructor'(v74, v102);
        wil::details::lambda_call__lambda_5fdaf3d3394d7722bc4889b5da3c4151___::reset(&FileInformation);
        v10 = v135;
        goto LABEL_141;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x207,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourcemanagerqueueinternal.cpp",
        (const char *)(unsigned int)v103,
        (int)v98);
      if ( v98 )
        Microsoft::Resources::Runtime::CContext::`scalar deleting destructor'(v98, v118);
      wil::details::lambda_call__lambda_5fdaf3d3394d7722bc4889b5da3c4151___::reset(&FileInformation);
      Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v145);
      if ( v49 )
        (**v49)(v49, 1);
      v119 = v129;
      v129 = 0;
      if ( v119 )
        operator delete(v119, v112);
      v120 = v130;
      v130 = 0;
      if ( v120 )
        operator delete(v120, v112);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      v115 = v135;
      if ( !v135 )
      {
LABEL_202:
        Microsoft::WRL::ComPtr<wil::details::RefCountedContainer<Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>>>::InternalRelease(&Block);
        return (unsigned int)v103;
      }
    }
    Microsoft::Resources::Runtime::CResourceManagerInternal::`scalar deleting destructor'(v115, (unsigned int)v112);
    goto LABEL_202;
  }
  phkResult = 0;
  if ( RegOpenCurrentUser(0x20019u, &phkResult) )
    goto LABEL_152;
  *(_QWORD *)Value = 0;
  Key = RegCreateKeyExW(phkResult, SubKey, 0, 0, 0, 0x2001Fu, 0, (PHKEY)Value, 0);
  if ( *(_QWORD *)Value )
    RegCloseKey(*(HKEY *)Value);
  if ( Key )
    goto LABEL_152;
  *(_QWORD *)Value = 0;
  DefStringResult_GetLength(v145);
  if ( v54 && (*(_QWORD *)v54 || !*(_DWORD *)(v54 + 8)) && (*(_DWORD *)(v54 + 8) || !*(_QWORD *)v54) )
    v10 = *(Microsoft::Resources::Runtime::CResourceManagerInternal **)(v54 + 16);
  v55 = hObject;
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    LastError = GetLastError();
    CloseHandle(v55);
    SetLastError(LastError);
  }
  hObject = 0;
  LODWORD(dwOptionsa) = (_DWORD)v10;
  if ( (unsigned int)_OpenMuiStringCache(&hObject, SubKey, v162, Buffer)
    || (Value[0] = 0, LODWORD(dwOptionsa) = 0, (unsigned int)_GetMUIStringFromCache(hObject, a2, 0, 0)) )
  {
LABEL_152:
    if ( phkResult )
      RegCloseKey(phkResult);
    goto LABEL_154;
  }
  v56 = Value[0];
  if ( (unsigned int)Value[0] > a7 )
  {
    v58 = -2147024774;
  }
  else
  {
    LODWORD(dwOptionsa) = Value[0];
    MUIStringFromCache = _GetMUIStringFromCache(hObject, a2, 0, Destination);
    v58 = MUIStringFromCache;
    if ( MUIStringFromCache > 0 )
      v58 = (unsigned __int16)MUIStringFromCache | 0x80070000;
    v56 = Value[0];
  }
  if ( a8 )
    *a8 = v56;
  if ( (v58 & 0x80000000) == 0 )
  {
    if ( phkResult )
      RegCloseKey(phkResult);
    Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v145);
    if ( v49 )
      (**v49)(v49, 1);
    v60 = v129;
    v129 = 0;
    if ( v60 )
      operator delete(v60, v59);
    v61 = v130;
    v130 = 0;
    if ( v61 )
      operator delete(v61, v59);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
LABEL_110:
    Microsoft::WRL::ComPtr<wil::details::RefCountedContainer<Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>>>::InternalRelease(&Block);
    return 0;
  }
  if ( v58 == -2147024774 )
  {
    if ( phkResult )
      RegCloseKey(phkResult);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B7,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourcemanagerqueueinternal.cpp",
      (const char *)v58,
      (int)dwOptionsa);
    if ( phkResult )
      RegCloseKey(phkResult);
  }
  Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v145);
  v137 = &Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::MrmProfile>::`vftable';
  Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Build::AutoMergeBehavior>::Release(&v137);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v129);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v130);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<void (*)(void *),&void _DefCloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<void (*)(void *),&void _DefCloseHandle(void *)>>(&hObject);
  v134 = &Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>::`vftable';
  Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>::Release(&v134);
  Microsoft::WRL::ComPtr<wil::details::RefCountedContainer<Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>>>::InternalRelease(&Block);
  return v58;
}

```

## disassembly

```asm
0x180032b50  mov     [rsp-8+arg_0], rbx
0x180032b55  push    rbp
0x180032b56  push    rsi
0x180032b57  push    rdi
0x180032b58  push    r12
0x180032b5a  push    r13
0x180032b5c  push    r14
0x180032b5e  push    r15
0x180032b60  lea     rbp, [rsp-0BD0h]
0x180032b68  sub     rsp, 0CD0h
0x180032b6f  mov     rax, cs:__security_cookie
0x180032b76  xor     rax, rsp
0x180032b79  mov     [rbp+0C00h+var_40], rax
0x180032b80  mov     [rbp+0C00h+var_BF0], r9
0x180032b84  mov     [rbp+0C00h+var_C20], r8
0x180032b88  mov     r13, rdx
0x180032b8b  mov     rcx, [rbp+0C00h+arg_28]
0x180032b92  mov     [rbp+0C00h+Destination], rcx
0x180032b96  mov     r12, [rbp+0C00h+arg_38]
0x180032b9d  mov     [rbp+0C00h+var_BE8], r12
0x180032ba1  test    rdx, rdx
0x180032ba4  jz      loc_180033EDE
0x180032baa  test    rcx, rcx
0x180032bad  jz      loc_180033EDE
0x180032bb3  xor     edx, edx
0x180032bb5  mov     [rsp+0D00h+Block], rdx
0x180032bba  lea     rax, ??_7?$AutoDeletePtr@VCResourceManagerInternal@Runtime@Resources@Microsoft@@@Resources@Microsoft@@6B@; const Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>::`vftable'
0x180032bc1  mov     [rbp+0C00h+var_C70], rax
0x180032bc5  mov     r14d, edx
0x180032bc8  mov     [rbp+0C00h+var_C68], rdx
0x180032bcc  mov     [rbp+0C00h+hObject], rdx
0x180032bd0  xorps   xmm0, xmm0
0x180032bd3  xor     eax, eax
0x180032bd5  movups  xmmword ptr [rbp+0C00h+Buffer], xmm0
0x180032bdc  mov     [rbp+0C00h+var_B48], ax
0x180032be3  test    r12, r12
0x180032be6  jz      short loc_180032BEC
0x180032be8  mov     [r12], rdx
0x180032bec  mov     r15d, edx
0x180032bef  mov     [rbp+0C00h+Value], edx
0x180032bf2  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180032bf9  mov     rax, rdx
0x180032bfc  nop     dword ptr [rax+00h]
0x180032c00  inc     rax
0x180032c03  cmp     [r13+rax*2+0], r14w
0x180032c09  jnz     short loc_180032C00
0x180032c0b  cmp     rax, 19h
0x180032c0f  jb      loc_180032D5B
0x180032c15  cmp     word ptr [r13+0], 40h ; '@'
0x180032c1b  jnz     loc_180032D5B
0x180032c21  cmp     word ptr [r13+2], 7Bh ; '{'
0x180032c27  jnz     loc_180032D5B
0x180032c2d  lea     rsi, [rax+rax]
0x180032c31  cmp     word ptr [rsi+r13-2], 7Dh ; '}'
0x180032c38  jnz     loc_180032D5B
0x180032c3e  mov     edx, 3Fh ; '?'; Ch
0x180032c43  mov     rcx, r13; Str
0x180032c46  call    cs:__imp_wcschr
0x180032c4c  mov     r10, rax
0x180032c4f  test    rax, rax
0x180032c52  jz      loc_180032D50
0x180032c58  mov     rcx, rax
0x180032c5b  sub     rcx, r13
0x180032c5e  sar     rcx, 1
0x180032c61  add     rcx, 0FFFFFFFFFFFFFFFEh
0x180032c65  mov     ebx, 7FFFFFFEh
0x180032c6a  cmp     rcx, rbx
0x180032c6d  ja      loc_180033DA1
0x180032c73  lea     rdx, [r13+4]
0x180032c77  mov     r8d, 114h
0x180032c7d  lea     r9, [rbp+0C00h+FileName]
0x180032c84  test    rcx, rcx
0x180032c87  jz      short loc_180032CA6
0x180032c89  movzx   eax, word ptr [rdx]
0x180032c8c  test    ax, ax
0x180032c8f  jz      short loc_180032CA6
0x180032c91  add     rdx, 2
0x180032c95  mov     [r9], ax
0x180032c99  add     r9, 2
0x180032c9d  dec     rcx
0x180032ca0  sub     r8, 1
0x180032ca4  jnz     short loc_180032C84
0x180032ca6  mov     edi, 8007007Ah
0x180032cab  xor     eax, eax
0x180032cad  test    r8, r8
0x180032cb0  cmovnz  edi, eax
0x180032cb3  lea     rcx, [r9-2]
0x180032cb7  cmovnz  rcx, r9
0x180032cbb  mov     [rcx], ax
0x180032cbe  jz      loc_180032D8D
0x180032cc4  lea     rdx, [r10+2]
0x180032cc8  sub     rsi, rdx
0x180032ccb  lea     rcx, [r13-2]
0x180032ccf  add     rcx, rsi
0x180032cd2  sar     rcx, 1
0x180032cd5  cmp     rcx, rbx
0x180032cd8  ja      loc_180033DB4
0x180032cde  mov     r8d, 114h
0x180032ce4  lea     r9, [rbp+0C00h+var_8E0]
0x180032ceb  nop     dword ptr [rax+rax+00h]
0x180032cf0  test    rcx, rcx
0x180032cf3  jz      short loc_180032D12
0x180032cf5  movzx   eax, word ptr [rdx]
0x180032cf8  test    ax, ax
0x180032cfb  jz      short loc_180032D12
0x180032cfd  add     rdx, 2
0x180032d01  mov     [r9], ax
0x180032d05  add     r9, 2
0x180032d09  dec     rcx
0x180032d0c  sub     r8, 1
0x180032d10  jnz     short loc_180032CF0
0x180032d12  mov     edi, 8007007Ah
0x180032d17  xor     eax, eax
0x180032d19  test    r8, r8
0x180032d1c  cmovnz  edi, eax
0x180032d1f  lea     rcx, [r9-2]
0x180032d23  cmovnz  rcx, r9
0x180032d27  mov     [rcx], ax
0x180032d2a  jz      loc_180033DC0
0x180032d30  mov     [rsp+0D00h+var_CA0], al
0x180032d34  xor     r8d, r8d; struct Microsoft::Resources::StringResult *
0x180032d37  lea     rdx, [rsp+0D00h+var_CA0]; bool *
0x180032d3c  lea     rcx, [rbp+0C00h+var_8E0]; unsigned __int16 *
0x180032d43  call    ?IsMrtUriReference@CMrtUriParser@Runtime@Resources@Microsoft@@SAJPEBGPEA_NPEAVStringResult@34@@Z; Microsoft::Resources::Runtime::CMrtUriParser::IsMrtUriReference(ushort const *,bool *,Microsoft::Resources::StringResult *)
0x180032d48  test    eax, eax
0x180032d4a  jns     loc_180033355
0x180032d50  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180032d57  mov     rcx, [rbp+0C00h+Destination]; Destination
0x180032d5b  lea     rdx, [rdx+1]
0x180032d5f  cmp     [r13+rdx*2+0], r14w
0x180032d65  jnz     short loc_180032D5B
0x180032d67  lea     rbx, [rdx+1]
0x180032d6b  cmp     rbx, [rbp+0C00h+arg_30]
0x180032d72  ja      loc_1800C1F97
0x180032d78  mov     r8, r13; Source
0x180032d7b  mov     rdx, rbx; SizeInWords
0x180032d7e  call    wcscpy_s
0x180032d83  mov     esi, 1
0x180032d88  jmp     loc_1800C1F9C
0x180032d8d  mov     edx, 9Dh; void *
0x180032d92  mov     rcx, [rbp+0C08h]; this
0x180032d99  lea     r8, aOnecoreuapBase_32; "onecoreuap\\base\\mrt\\runtime\\src\\cr"...
0x180032da0  mov     r9d, edi; char *
0x180032da3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032da8  test    edi, edi
0x180032daa  js      short loc_180032D50
0x180032dac  xor     ecx, ecx
0x180032dae  mov     [rsp+0D00h+var_C90], rcx
0x180032db3  mov     [rsp+0D00h+var_C98], rcx
0x180032db8  lea     rsi, ??_7?$AutoDeletePtr@VMrmProfile@Resources@Microsoft@@@Resources@Microsoft@@6B@; const Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::MrmProfile>::`vftable'
0x180032dbf  mov     [rbp+0C00h+var_C58], rsi
0x180032dc3  mov     [rbp+0C00h+var_C50], rcx
0x180032dc7  mov     [rbp+0C00h+var_C30], ecx
0x180032dca  lea     rax, [rsp+0D00h+var_C98]
0x180032dcf  mov     qword ptr [rbp+0C00h+FileInformation], rax
0x180032dd6  mov     qword ptr [rbp+0C00h+FileInformation+8], rcx
0x180032ddd  mov     byte ptr [rbp+0C00h+var_B70], 1
0x180032de4  lea     rax, [rsp+0D00h+var_C90]
0x180032de9  mov     qword ptr [rbp+0C00h+Value], rax
0x180032ded  mov     [rbp+0C00h+var_C40], rcx
0x180032df1  mov     [rbp+0C00h+var_C38], 1
0x180032df5  lea     rax, [rbp+0C00h+var_C30]
0x180032df9  mov     [rsp+0D00h+var_CC8], rax
0x180032dfe  lea     rax, [rbp+0C00h+var_C50]
0x180032e02  mov     [rsp+0D00h+lpSecurityAttributes], rax
0x180032e07  lea     rax, [rbp+0C00h+FileInformation+8]
0x180032e0e  mov     qword ptr [rsp+0D00h+samDesired], rax
0x180032e13  lea     rax, [rbp+0C00h+var_C40]
0x180032e17  mov     qword ptr [rsp+0D00h+dwOptions], rax; int
0x180032e1c  mov     r9d, r15d
0x180032e1f  lea     r8, [rbp+0C00h+var_8E0]
0x180032e26  lea     rdx, [rbp+0C00h+FileName]
0x180032e2d  call    ?GetEscapedPriPathFromPackageFullName@CResourceManagerQueueInternal@Runtime@Resources@Microsoft@@AEAAJPEBG0W4FULLY_QUALIFIED_REFERENCE_TYPE@234@PEAPEAG2PEAPEAVMrmProfile@34@PEAW4ProfileType@634@@Z; Microsoft::Resources::Runtime::CResourceManagerQueueInternal::GetEscapedPriPathFromPackageFullName(ushort const *,ushort const *,Microsoft::Resources::Runtime::FULLY_QUALIFIED_REFERENCE_TYPE,ushort * *,ushort * *,Microsoft::Resources::MrmProfile * *,Microsoft::Resources::MrmProfile::ProfileType *)
0x180032e32  mov     edi, eax
0x180032e34  cmp     [rbp+0C00h+var_C38], r14b
0x180032e38  jz      short loc_180032E51
0x180032e3a  mov     r8, qword ptr [rbp+0C00h+Value]
0x180032e3e  mov     rcx, [r8]; void *
0x180032e41  mov     rdx, [rbp+0C00h+var_C40]; struct std::nothrow_t *
0x180032e45  mov     [r8], rdx
0x180032e48  test    rcx, rcx
0x180032e4b  jnz     loc_180033DCA
0x180032e51  cmp     byte ptr [rbp+0C00h+var_B70], r14b
0x180032e58  jz      short loc_180032E77
0x180032e5a  mov     rdx, qword ptr [rbp+0C00h+FileInformation]; struct std::nothrow_t *
0x180032e61  mov     rcx, [rdx]; void *
0x180032e64  mov     rax, qword ptr [rbp+0C00h+FileInformation+8]
0x180032e6b  mov     [rdx], rax
0x180032e6e  test    rcx, rcx
0x180032e71  jnz     loc_180033DD4
0x180032e77  test    edi, edi
0x180032e79  js      loc_18003341F
0x180032e7f  cmp     r15d, 1
0x180032e83  jz      loc_1800332F6
0x180032e89  cmp     r15d, 4
0x180032e8d  jz      loc_1800332F6
0x180032e93  lea     eax, [r15-1]
0x180032e97  test    eax, 0FFFFFFFCh
0x180032e9c  jnz     loc_180032FB0
0x180032ea2  cmp     r15d, 2
0x180032ea6  jz      loc_180032FB0
0x180032eac  mov     rcx, [rsp+0D00h+var_C90]
0x180032eb1  test    rcx, rcx
0x180032eb4  jz      loc_180032FB0
0x180032eba  mov     edx, 114h
0x180032ebf  lea     r8, [rbp+0C00h+FileName]
0x180032ec6  test    rbx, rbx
0x180032ec9  jz      short loc_180032EE8
0x180032ecb  movzx   eax, word ptr [rcx]
0x180032ece  test    ax, ax
0x180032ed1  jz      short loc_180032EE8
0x180032ed3  add     rcx, 2
0x180032ed7  mov     [r8], ax
0x180032edb  add     r8, 2
0x180032edf  dec     rbx
0x180032ee2  sub     rdx, 1
0x180032ee6  jnz     short loc_180032EC6
0x180032ee8  mov     ebx, 8007007Ah
0x180032eed  xor     edi, edi
0x180032eef  test    rdx, rdx
0x180032ef2  cmovnz  ebx, edi
0x180032ef5  lea     rcx, [r8-2]
0x180032ef9  cmovnz  rcx, r8
0x180032efd  mov     [rcx], di
0x180032f00  jnz     loc_180032FB0
0x180032f06  mov     rcx, [rbp+0C08h]; this
0x180032f0d  mov     r9d, ebx; char *
0x180032f10  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\mrt\\runtime\\src\\cr"...
0x180032f17  mov     edx, 164h; void *
0x180032f1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032f21  nop
0x180032f22  mov     rcx, [rbp+0C00h+var_C50]
0x180032f26  test    rcx, rcx
0x180032f29  jz      short loc_180032F3C
0x180032f2b  mov     rax, [rcx]
0x180032f2e  mov     edx, 1
0x180032f33  mov     rax, [rax]
0x180032f36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032f3b  nop
0x180032f3c  mov     rcx, [rsp+0D00h+var_C98]; void *
0x180032f41  mov     [rsp+0D00h+var_C98], rdi
0x180032f46  test    rcx, rcx
0x180032f49  jz      short loc_180032F50
0x180032f4b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180032f50  mov     rcx, [rsp+0D00h+var_C90]; void *
0x180032f55  mov     [rsp+0D00h+var_C90], rdi
0x180032f5a  test    rcx, rcx
0x180032f5d  jz      short loc_180032F64
0x180032f5f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180032f64  mov     rcx, [rbp+0C00h+hObject]; hObject
0x180032f68  lea     rax, [rcx-1]
0x180032f6c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180032f70  jbe     loc_180033DE9
0x180032f76  mov     rdi, [rsp+0D00h+Block]
0x180032f7b  test    rdi, rdi
0x180032f7e  jnz     loc_1800333E1
0x180032f84  mov     eax, ebx
0x180032f86  mov     rcx, [rbp+0C00h+var_40]
0x180032f8d  xor     rcx, rsp; StackCookie
0x180032f90  call    __security_check_cookie
0x180032f95  mov     rbx, [rsp+0D00h+arg_0]
0x180032f9d  add     rsp, 0CD0h
0x180032fa4  pop     r15
0x180032fa6  pop     r14
0x180032fa8  pop     r13
0x180032faa  pop     r12
0x180032fac  pop     rdi
0x180032fad  pop     rsi
0x180032fae  pop     rbp
0x180032faf  retn
0x180032fb0  lea     rcx, [rbp+0C00h+var_C10]
0x180032fb4  call    DefStringResult_InitBuf
0x180032fb9  lea     rcx, [rbp+0C00h+var_C10]
0x180032fbd  mov     [rbp+0C00h+var_C18], rcx
0x180032fc1  mov     rdi, [rbp+0C00h+var_C50]
0x180032fc5  cmp     [rbp+0C00h+arg_20], r14b
0x180032fcc  jnz     loc_1800333DA
0x180032fd2  mov     rbx, [rsp+0D00h+var_C98]
0x180032fd7  xor     eax, eax
0x180032fd9  mov     [rbp+0C00h+Value], eax
0x180032fdc  xorps   xmm0, xmm0
0x180032fdf  movdqa  [rbp+0C00h+var_BE0], xmm0
0x180032fe4  mov     [rbp+0C00h+var_BD0], eax
0x180032fe7  mov     [rbp+0C00h+var_BCC], al
0x180032fea  mov     [rbp+0C00h+var_BC8], rdi
0x180032fee  movdqa  [rbp+0C00h+var_BC0], xmm0
0x180032ff3  mov     [rbp+0C00h+var_BB0], rax
0x180032ff7  lea     rcx, [rbp+0C00h+var_BA8]; this
0x180032ffb  call    ??0StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::StringResult(void)
0x180033000  mov     rsi, [rbp+0C00h+var_C20]
0x180033004  test    rsi, rsi
0x180033007  jnz     loc_180033388
0x18003300d  lea     r9, [rbp+0C00h+Value]; unsigned int *
0x180033011  xor     r8d, r8d; unsigned __int16 *
0x180033014  mov     edx, 0FFFFFFFFh; int
0x180033019  lea     rcx, [rbp+0C00h+var_BE0]; this
0x18003301d  call    ?_GetHash@CContextualHash@Runtime@Resources@Microsoft@@QEAAJHPEBGPEAI@Z; Microsoft::Resources::Runtime::CContextualHash::_GetHash(int,ushort const *,uint *)
0x180033022  test    eax, eax
0x180033024  js      loc_1800333D1
0x18003302a  lea     rdx, [rbp+0C00h+var_C18]; struct Microsoft::Resources::StringResult *
  ... truncated ...
```
