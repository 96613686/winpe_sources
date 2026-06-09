# CDplServiceImpl::SvcControl(void *,_EDP_CRED_SVC_INFO_TYPE,ushort const *,ushort const *,ushort const *,_EDP_CRED_SVC_INFO_CXT *,_EDP_CRED_SVC_INFO *,_EDP_CRED_SVC_INFO * *)

- ea: `0x1800977b0`
- end: `0x1800991b6`
- name: `?SvcControl@CDplServiceImpl@@AEAAJPEAXW4_EDP_CRED_SVC_INFO_TYPE@@PEBG22PEAU_EDP_CRED_SVC_INFO_CXT@@PEAU_EDP_CRED_SVC_INFO@@PEAPEAU4@@Z`
- size: `6662`
- prototype: ``
- caller_count: `1`
- callee_count: `37`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180080f58`

## callees

- `0x180004f86`
- `0x180005045`
- `0x1800124d8`
- `0x180022760`
- `0x180046fa4`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x180087d4c`
- `0x180087d84`
- `0x18008a018`
- `0x18008a6b0`
- `0x18008c200`
- `0x18008dd38`
- `0x18008deb4`
- `0x18008e020`
- `0x18008ed84`
- `0x18008f910`
- `0x18008fb78`
- `0x180090228`
- `0x18009153c`
- `0x180092e48`
- `0x1800963f0`
- `0x1800964ac`
- `0x18009652c`
- `0x1800966dc`
- `0x1800968bc`
- `0x180097468`
- `0x1800977b0`
- `0x1800991bc`
- `0x180099274`
- `0x1800aa1c4`
- `0x1800bd7a8`
- `0x1800bd810`
- `0x1800d5af8`
- `0x1800d6064`
- `0x1800dddf0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097aba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097bd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097d44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097aba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097bd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097d44`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180097ab0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180097d3a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180097ab0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180097d3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180097a9a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180097d24`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180097a9a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180097d24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800979ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800979bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800979ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800979bd`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180097bc5`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180097bc5`
- `RPCRT4!UuidIsNil` at `0x180098034`
- `RPCRT4!UuidIsNil` at `0x180098034`

## pseudocode

```c
__int64 __fastcall CDplServiceImpl::SvcControl(
        CDplServiceImpl *a1,
        void *a2,
        int a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        __int64 a7,
        unsigned __int64 a8,
        _QWORD *a9)
{
  char *v10; // r12
  unsigned int v11; // ecx
  unsigned int User; // esi
  int v13; // r8d
  void *v14; // rbx
  CDplUser *v15; // rdi
  unsigned __int16 *v16; // r13
  __int64 v17; // rcx
  unsigned __int8 *v18; // rax
  HANDLE v20; // rax
  int v21; // ecx
  signed int v22; // eax
  int v23; // ecx
  unsigned __int64 v24; // rbx
  int v25; // ecx
  signed int v26; // eax
  int v27; // ecx
  unsigned int v28; // edx
  HANDLE CurrentThread; // rax
  int v30; // ecx
  signed int LastError; // eax
  int v32; // ecx
  int v33; // ecx
  char v34; // bl
  CDplServiceImpl *v35; // rcx
  int v36; // eax
  struct _GUID *v37; // rbx
  int v38; // ecx
  int DplKeysState; // eax
  int v40; // ecx
  int v41; // ebx
  int v42; // ebx
  int v43; // ebx
  int v44; // ebx
  int v45; // ebx
  int v46; // ebx
  unsigned int v47; // eax
  unsigned int v48; // esi
  unsigned int v49; // edx
  const unsigned __int8 *v50; // rcx
  int v51; // ecx
  unsigned __int64 v52; // r13
  int v53; // ecx
  int v54; // ecx
  int v55; // ebx
  char *v56; // rdi
  void *v57; // rcx
  unsigned int v58; // ebx
  unsigned int v59; // eax
  int v60; // ecx
  unsigned __int64 v61; // r13
  int v62; // ecx
  int v63; // ecx
  int v64; // ebx
  int v65; // ecx
  unsigned __int64 v66; // r13
  unsigned __int64 v67; // rcx
  int v68; // ecx
  unsigned __int64 v69; // rcx
  int v70; // ecx
  int v71; // ecx
  int v72; // ebx
  int v73; // ecx
  int v74; // ecx
  CDplServiceImpl *v75; // rcx
  int v76; // ecx
  int v77; // eax
  CDplServiceImpl *v78; // rcx
  int v79; // ecx
  int v80; // ecx
  unsigned __int8 v81; // r8
  int v82; // ecx
  CDplAccount *v83; // r12
  CDplUser *v84; // rcx
  int v85; // eax
  int v86; // ecx
  char v87; // [rsp+20h] [rbp-110h]
  char v88; // [rsp+30h] [rbp-100h]
  char v89; // [rsp+30h] [rbp-100h]
  char v90; // [rsp+30h] [rbp-100h]
  unsigned __int16 *v91; // [rsp+B0h] [rbp-80h] BYREF
  struct CDplUser *v92; // [rsp+B8h] [rbp-78h] BYREF
  void *v93; // [rsp+C0h] [rbp-70h]
  size_t Size; // [rsp+C8h] [rbp-68h] BYREF
  char *v95; // [rsp+D0h] [rbp-60h] BYREF
  CDplServiceImpl *v96; // [rsp+D8h] [rbp-58h]
  int v97; // [rsp+E0h] [rbp-50h]
  void *Src; // [rsp+E8h] [rbp-48h] BYREF
  _QWORD *v99; // [rsp+F0h] [rbp-40h]
  HANDLE hObject; // [rsp+F8h] [rbp-38h] BYREF
  RPC_STATUS Status; // [rsp+100h] [rbp-30h] BYREF
  unsigned int v102; // [rsp+104h] [rbp-2Ch] BYREF
  unsigned int v103; // [rsp+108h] [rbp-28h] BYREF
  unsigned __int64 v104; // [rsp+110h] [rbp-20h] BYREF
  unsigned __int16 *v105; // [rsp+118h] [rbp-18h]
  unsigned __int16 *v106; // [rsp+120h] [rbp-10h] BYREF
  void *v107; // [rsp+128h] [rbp-8h] BYREF
  unsigned __int64 v108; // [rsp+130h] [rbp+0h] BYREF
  unsigned __int16 *v109; // [rsp+138h] [rbp+8h]
  unsigned __int16 *v110; // [rsp+140h] [rbp+10h] BYREF
  unsigned __int64 v111; // [rsp+148h] [rbp+18h]
  int v112; // [rsp+150h] [rbp+20h] BYREF
  CDplAccount *v113; // [rsp+158h] [rbp+28h] BYREF
  unsigned __int64 v114; // [rsp+160h] [rbp+30h] BYREF
  unsigned __int16 *v115; // [rsp+168h] [rbp+38h]
  void *v116; // [rsp+170h] [rbp+40h]
  struct _GUID v117; // [rsp+178h] [rbp+48h] BYREF
  unsigned __int8 v118[16]; // [rsp+188h] [rbp+58h] BYREF
  __int128 v119; // [rsp+198h] [rbp+68h]
  unsigned __int8 v120[16]; // [rsp+1A8h] [rbp+78h] BYREF
  __int128 v121; // [rsp+1B8h] [rbp+88h]
  unsigned __int8 v122[16]; // [rsp+1C8h] [rbp+98h] BYREF
  __int128 v123; // [rsp+1D8h] [rbp+A8h]

  v105 = a4;
  v10 = 0;
  v116 = a2;
  v96 = a1;
  v109 = a5;
  v115 = a6;
  v111 = a8;
  v99 = a9;
  Status = 0;
  v95 = 0;
  hObject = 0;
  v107 = 0;
  v108 = 0;
  v114 = 0;
  v93 = 0;
  v97 = 0;
  v91 = 0;
  v110 = 0;
  v92 = 0;
  v113 = 0;
  v106 = 0;
  v104 = 0;
  v112 = 0;
  Src = 0;
  Size = 0;
  v117 = 0;
  v102 = -1;
  v103 = 0;
  *(_OWORD *)v120 = 0;
  v121 = 0;
  *(_OWORD *)v122 = 0;
  v123 = 0;
  *(_OWORD *)v118 = 0;
  v119 = 0;
  fnEfsLogTrace1Strings((_DWORD)a1, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 37, 137);
  if ( a9 )
    *a9 = 0;
  if ( !v105 )
  {
    v87 = -111;
LABEL_5:
    User = -2147024809;
    v13 = -2147024809;
LABEL_6:
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v13, 37, v87);
LABEL_7:
    v14 = 0;
LABEL_8:
    v15 = v92;
LABEL_9:
    v16 = v91;
    goto LABEL_10;
  }
  if ( (unsigned int)(a3 - 1) > 0xE )
  {
    v87 = -106;
    goto LABEL_5;
  }
  if ( a3 > 8 )
  {
    v41 = a3 - 9;
    if ( !v41 )
    {
      if ( !a7 )
      {
        v87 = 123;
        goto LABEL_5;
      }
      if ( !a9 )
      {
        v87 = 124;
        goto LABEL_74;
      }
      if ( a6 )
      {
        v87 = 125;
        goto LABEL_5;
      }
      fnEfsLogTrace1Strings(v11, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 134);
      User = DplibpMemAllocEx(136, 0, 0, &v95);
      v85 = fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              User,
              37,
              134);
      v10 = v95;
      if ( v85 < 0 )
        goto LABEL_50;
      memset_0(v95, 0, 0x88u);
      *(_DWORD *)v10 = 136;
      *((_DWORD *)v10 + 1) = 9;
      fnEfsLogTrace1Strings(v86, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 150);
      DplKeysState = CDplServiceImpl::GetDplKeysState(
                       v96,
                       v109,
                       0,
                       *(_DWORD *)(a7 + 4),
                       1,
                       (int *)v10 + 2,
                       (struct _FILETIME *)(v10 + 12),
                       (int *)v10 + 5);
      v89 = -106;
      goto LABEL_187;
    }
    v42 = v41 - 1;
    if ( v42 )
    {
      v43 = v42 - 1;
      if ( !v43 )
      {
        if ( a8 )
        {
          fnEfsLogTrace1Strings(v11, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 11);
          User = CDplServiceImpl::SetTestDeviceLockState(v75, a5, 1, *(_DWORD *)(a8 + 8));
          if ( (int)fnEfsLogTrace1String1Dword(
                      g_hPublisher,
                      (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                      (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                      (unsigned int)&sourceString,
                      User,
                      37,
                      11) >= 0 )
          {
            fnEfsLogTrace1Strings(v76, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 19);
            User = CDplServiceImpl::FindUser(v96, v109, 0, &v92);
            v77 = fnEfsLogTrace1String1Dword(
                    g_hPublisher,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                    (unsigned int)&sourceString,
                    User,
                    37,
                    19);
            v15 = v92;
            if ( v77 >= 0 )
            {
              if ( v92 )
              {
                *((_DWORD *)v92 + 92) = *(_DWORD *)(v111 + 8);
              }
              else
              {
                User = -2147418113;
                fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147418113, 37, 21);
              }
            }
            v14 = 0;
            goto LABEL_9;
          }
          goto LABEL_7;
        }
        v87 = 6;
        goto LABEL_5;
      }
      v44 = v43 - 1;
      if ( !v44 )
      {
        if ( !a7 )
        {
          v87 = -97;
          goto LABEL_5;
        }
        if ( !a9 )
        {
          v87 = -96;
          goto LABEL_74;
        }
        if ( a6 )
        {
          v87 = -95;
          goto LABEL_5;
        }
        fnEfsLogTrace1Strings(v11, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 172);
        User = CDplServiceImpl::EdpConsumerCredentialCreate(
                 v96,
                 a5,
                 *(_DWORD *)(a7 + 4),
                 &v104,
                 &v106,
                 (unsigned __int8 **)&Src,
                 (unsigned int *)&Size);
        if ( (int)fnEfsLogTrace1String1Dword(
                    g_hPublisher,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                    (unsigned int)&sourceString,
                    User,
                    37,
                    172) < 0 )
          goto LABEL_7;
        fnEfsLogTrace1Strings(v65, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 180);
        v66 = -1;
        v67 = -1;
        if ( v104 < 0xFFFFFFFFFFFFFF78uLL )
          v67 = v104 + 136;
        v111 = v67;
        User = v104 >= 0xFFFFFFFFFFFFFF78uLL ? 0x80070216 : 0;
        if ( (int)fnEfsLogTrace1String1Dword(
                    g_hPublisher,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                    (unsigned int)&sourceString,
                    User,
                    37,
                    180) < 0 )
          goto LABEL_7;
        fnEfsLogTrace1Strings(v68, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 184);
        v69 = v111 + (unsigned int)Size;
        if ( v69 >= v111 )
          v66 = v111 + (unsigned int)Size;
        User = v69 < v111 ? 0x80070216 : 0;
        if ( (int)fnEfsLogTrace1String1Dword(
                    g_hPublisher,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                    (unsigned int)&sourceString,
                    User,
                    37,
                    184) < 0 )
          goto LABEL_7;
        fnEfsLogTrace1Strings(v70, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 189);
        User = DplibpMemAllocEx(v66, 0, 0, &v95);
        if ( (int)fnEfsLogTrace1String1Dword(
                    g_hPublisher,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                    (unsigned int)&sourceString,
                    User,
                    37,
                    189) < 0 )
          goto LABEL_155;
        fnEfsLogTrace1Strings(v71, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 192);
        User = ULongLongToULong(v66, (unsigned int *)&Size + 1);
        if ( (int)fnEfsLogTrace1String1Dword(
                    g_hPublisher,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                    (unsigned int)&sourceString,
                    User,
                    37,
                    192) < 0 )
          goto LABEL_155;
        v72 = HIDWORD(Size);
        v10 = v95;
        memset_0(v95, 0, HIDWORD(Size));
        *(_DWORD *)v10 = v72;
        *((_DWORD *)v10 + 1) = 12;
        fnEfsLogTrace1Strings(v73, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 199);
        User = ULongLongToULong(v104 + 136, (unsigned int *)v10 + 2);
        if ( (int)fnEfsLogTrace1String1Dword(
                    g_hPublisher,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                    (unsigned int)&sourceString,
                    User,
                    37,
                    199) < 0 )
          goto LABEL_50;
        *((_DWORD *)v10 + 3) = Size;
        memcpy_0(&v10[*((unsigned int *)v10 + 2)], Src, (unsigned int)Size);
        fnEfsLogTrace1Strings(v74, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 207);
        DplKeysState = StringCbCopyW((unsigned __int16 *)v10 + 8, v104, v106);
        v89 = -49;
        goto LABEL_187;
      }
      v45 = v44 - 1;
      if ( !v45 )
      {
        if ( a6 )
        {
          v87 = -40;
          goto LABEL_5;
        }
        v34 = -33;
        fnEfsLogTrace1Strings(v11, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 223);
        v36 = CDplServiceImpl::EdpConsumerCredentialDelete(v96, a5, *(_DWORD *)(a8 + 8));
LABEL_67:
        v88 = v34;
LABEL_68:
        User = v36;
        fnEfsLogTrace1String1Dword(
          g_hPublisher,
          (unsigned int)EFS_TRACE_COMPLETE_EVENT,
          (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
          (unsigned int)&sourceString,
          v36,
          37,
          v88);
        goto LABEL_7;
      }
      v46 = v45 - 1;
      if ( v46 )
      {
        if ( v46 != 1 )
          goto LABEL_94;
        if ( !v116 )
        {
          v87 = 91;
          goto LABEL_5;
        }
        if ( !a7 )
        {
          v87 = 92;
          goto LABEL_5;
        }
        if ( !a9 )
        {
          v87 = 93;
          goto LABEL_74;
        }
        if ( *(_DWORD *)(a7 + 72) )
        {
          if ( *(_DWORD *)(a7 + 72) != 24 )
          {
            v87 = 106;
            goto LABEL_5;
          }
          v47 = *(_DWORD *)(a7 + 68);
          if ( v47 >= *(_DWORD *)a7 )
          {
            v87 = 112;
            goto LABEL_5;
          }
          v11 = v47 + 24;
          if ( v47 + 24 < v47 || v11 > *(_DWORD *)a7 )
          {
            v87 = 119;
            goto LABEL_5;
          }
        }
        v48 = *(_DWORD *)(a7 + 100);
        fnEfsLogTrace1Strings(v11, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 147);
        v49 = *(_DWORD *)(a7 + 72);
        if ( v49 )
          v50 = (const unsigned __int8 *)(a7 + *(unsigned int *)(a7 + 68));
        else
          v50 = 0;
        User = CDplServiceImpl::GetAppKeyForAppCache(
                 v96,
                 v116,
                 v105,
                 a5,
                 a6,
                 v48,
                 (const unsigned __int16 *)(a7 + 104),
                 v50,
                 v49,
                 (const struct _GUID *)(a7 + 76),
                 *(_DWORD *)(a7 + 92),
                 *(_DWORD *)(a7 + 96),
                 (const unsigned __int8 *)(a7 + 4),
                 (const unsigned __int8 *)(a7 + 36),
                 (unsigned __int8 **)&Src,
                 (unsigned int *)&Size,
                 &v117,
                 &v102,
                 &v103,
                 v120,
                 v122,
                 v118);
        if ( (int)fnEfsLogTrace1String1Dword(
                    g_hPublisher,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                    (unsigned int)&sourceString,
                    User,
                    37,
                    147) < 0 )
          goto LABEL_7;
        fnEfsLogTrace1Strings(v51, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 153);
        v52 = (unsigned int)Size + 136LL;
        User = 0;
        if ( (int)fnEfsLogTrace1String1Dword(
                    g_hPublisher,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                    (unsigned int)&sourceString,
                    0,
                    37,
                    153) < 0 )
          goto LABEL_7;
        fnEfsLogTrace1Strings(v53, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 158);
        User = DplibpMemAllocEx(v52, 1, 1, &v95);
        if ( (int)fnEfsLogTrace1String1Dword(
                    g_hPublisher,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                    (unsigned int)&sourceString,
                    User,
                    37,
                    158) < 0 )
          goto LABEL_155;
        fnEfsLogTrace1Strings(v54, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 160);
        User = ULongLongToULong(v52, (unsigned int *)&Size + 1);
        if ( (int)fnEfsLogTrace1String1Dword(
                    g_hPublisher,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                    (unsigned int)&sourceString,
                    User,
                    37,
                    160) < 0 )
          goto LABEL_155;
        v55 = HIDWORD(Size);
        v56 = v95;
        memset_0(v95, 0, HIDWORD(Size));
        *(_DWORD *)v56 = v55;
        v57 = v56 + 132;
        *((_DWORD *)v56 + 1) = 15;
        *(_OWORD *)(v56 + 8) = *(_OWORD *)v120;
        *(_OWORD *)(v56 + 24) = v121;
        *(_OWORD *)(v56 + 40) = *(_OWORD *)v122;
        *(_OWORD *)(v56 + 56) = v123;
        *(_OWORD *)(v56 + 72) = *(_OWORD *)v118;
        *(_OWORD *)(v56 + 88) = v119;
        *(struct _GUID *)(v56 + 104) = v117;
        *((_DWORD *)v56 + 30) = v102;
        *((_DWORD *)v56 + 31) = v103;
        *((_DWORD *)v56 + 32) = Size;
      }
      else
      {
        if ( !a7 )
        {
          v87 = 36;
          goto LABEL_5;
        }
        if ( !a9 )
        {
          v87 = 37;
          goto LABEL_74;
        }
        v58 = *(_DWORD *)(a7 + 4);
        if ( v58 == -1 )
        {
          if ( !a6 )
          {
            v87 = 43;
            goto LABEL_5;
          }
          fnEfsLogTrace1Strings(v11, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 51);
          v59 = CDplServiceImpl::EdpCredentialExists(
                  v96,
                  v105,
                  a5,
                  a6,
                  (const unsigned __int16 *)(a7 + 8),
                  &v112,
                  (unsigned __int8 **)&Src,
                  (unsigned int *)&Size);
          v90 = 51;
        }
        else
        {
          if ( a6 )
          {
            v87 = 54;
            goto LABEL_5;
          }
          fnEfsLogTrace1Strings(v11, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 61);
          v59 = CDplServiceImpl::EdpConsumerCredentialCreate(
                  v96,
                  a5,
                  v58,
                  &v104,
                  &v106,
                  (unsigned __int8 **)&Src,
                  (unsigned int *)&Size);
          v90 = 61;
        }
        User = v59;
        if ( (int)fnEfsLogTrace1String1Dword(
                    g_hPublisher,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                    (unsigned int)&sourceString,
                    v59,
                    37,
                    v90) < 0 )
          goto LABEL_7;
        fnEfsLogTrace1Strings(v60, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 68);
        v61 = (unsigned int)Size + 136LL;
        User = 0;
        if ( (int)fnEfsLogTrace1String1Dword(
                    g_hPublisher,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                    (unsigned int)&sourceString,
                    0,
                    37,
                    68) < 0 )
          goto LABEL_7;
        fnEfsLogTrace1Strings(v62, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 73);
        User = DplibpMemAllocEx(v61, 0, 0, &v95);
        if ( (int)fnEfsLogTrace1String1Dword(
                    g_hPublisher,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                    (unsigned int)&sourceString,
                    User,
                    37,
                    73) < 0 )
          goto LABEL_155;
        fnEfsLogTrace1Strings(v63, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 75);
        User = ULongLongToULong(v61, (unsigned int *)&Size + 1);
        if ( (int)fnEfsLogTrace1String1Dword(
                    g_hPublisher,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                    (unsigned int)&sourceString,
                    User,
                    37,
                    75) < 0 )
          goto LABEL_155;
        v64 = HIDWORD(Size);
        v56 = v95;
        memset_0(v95, 0, HIDWORD(Size));
        *(_DWORD *)v56 = v64;
        v57 = v56 + 12;
        *((_DWORD *)v56 + 1) = 14;
        *((_DWORD *)v56 + 2) = Size;
      }
      memcpy_0(v57, Src, (unsigned int)Size);
    }
    else
    {
      if ( !a9 )
      {
        v87 = -27;
        goto LABEL_74;
      }
      if ( !a6 )
      {
        v87 = -26;
        goto LABEL_5;
      }
      fnEfsLogTrace1Strings(v11, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 236);
      User = CDplServiceImpl::EdpProtectorPreParse(v78, a6, &v91);
      if ( (int)fnEfsLogTrace1String1Dword(
                  g_hPublisher,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                  (unsigned int)&sourceString,
                  User,
                  37,
                  236) < 0 )
        goto LABEL_7;
      fnEfsLogTrace1Strings(v79, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 237);
      v16 = v91;
      User = CDplService::StringConcatAlloc(&v110, v105, L"-", v91, 0);
      if ( (int)fnEfsLogTrace1String1Dword(
                  g_hPublisher,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                  (unsigned int)&sourceString,
                  User,
                  37,
                  237) < 0 )
        goto LABEL_192;
      fnEfsLogTrace1Strings(v80, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 238);
      User = DpmCache::FindStr2Ptr((CDplServiceImpl *)((char *)v96 + 176), v110, v81, (void **)&v113);
      if ( (int)fnEfsLogTrace1String1Dword(
                  g_hPublisher,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                  (unsigned int)&sourceString,
                  User,
                  37,
                  238) < 0 )
        goto LABEL_7;
      fnEfsLogTrace1Strings(v82, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 247);
      User = DplibpMemAllocEx(136, 0, 0, &v95);
      if ( (int)fnEfsLogTrace1String1Dword(
                  g_hPublisher,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                  (unsigned int)&sourceString,
                  User,
                  37,
                  247) < 0 )
        goto LABEL_155;
      v56 = v95;
      memset_0(v95, 0, 0x88u);
      v83 = v113;
      *(_DWORD *)v56 = 136;
      *((_DWORD *)v56 + 1) = 10;
      if ( v83 )
      {
        v56[25] = *((_DWORD *)v83 + 51) != 0;
        v84 = (CDplUser *)*((_QWORD *)v83 + 7);
        if ( v84 )
        {
          CDplUser::UserSvcLock(v84);
          *((_QWORD *)v56 + 1) = *(_QWORD *)(*((_QWORD *)v83 + 7) + 360LL);
          *((_QWORD *)v56 + 2) = *((_QWORD *)v83 + 28);
          if ( *((_DWORD *)v83 + 34)
            || *((_DWORD *)v83 + 51) && (unsigned int)CDplAccount::ShouldDropKeysForConsumerAccount(v83, 0) )
          {
            v56[24] = *(_DWORD *)(*((_QWORD *)v83 + 7) + 248LL) != 0;
          }
          CDplUser::UserSvcUnlock(*((CDplUser **)v83 + 7), 1);
        }
      }
    }
    v10 = 0;
    *v99 = v56;
    goto LABEL_7;
  }
  if ( a3 == 8 )
  {
    fnEfsLogTrace1Strings(v11, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 118);
    v36 = CDplServiceImpl::SetSecondaryIdentities(v96, a5, a6, (const unsigned __int16 *)(a8 + 8));
    v88 = 118;
    goto LABEL_68;
  }
  if ( a3 != 1 )
  {
    if ( a3 != 2 )
    {
      if ( a3 == 3 )
      {
        User = 0;
        CDplServiceImpl::ReloadSvcConfig(v96);
        v14 = 0;
        goto LABEL_8;
      }
      if ( a3 != 4 )
      {
        if ( a3 == 5 || a3 == 6 )
        {
          CurrentThread = GetCurrentThread();
          if ( OpenThreadToken(CurrentThread, 8u, 1, &hObject) )
          {
            fnEfsLogTrace1Strings(v30, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 42);
            User = EdpInlGetProcessUniqueIdByProcessToken(hObject, &v108);
            if ( (int)fnEfsLogTrace1String1Dword(
                        g_hPublisher,
                        (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                        (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                        (unsigned int)&sourceString,
                        User,
                        37,
                        42) >= 0 )
            {
              fnEfsLogTrace1Strings(v32, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 44);
              User = CDplServiceImpl::RevertToSelf(v96, &v107);
              if ( (int)fnEfsLogTrace1String1Dword(
                          g_hPublisher,
                          (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                          (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                          (unsigned int)&sourceString,
                          User,
                          37,
                          44) >= 0 )
              {
                v97 = CDplServiceImpl::SvcLock(v96);
                fnEfsLogTrace1Strings(v33, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 51);
                User = EdpInlSetProcessUiEnforcement(v108, a3 == 5);
                if ( (int)fnEfsLogTrace1String1Dword(
                            g_hPublisher,
                            (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                            (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                            (unsigned int)&sourceString,
                            User,
                            37,
                            51) >= 0 )
                {
                  v97 = CDplServiceImpl::SvcUnlockIf(v96, v97);
                  CDplServiceImpl::RestoreImpersonation(v96, &v107);
                }
              }
            }
            goto LABEL_7;
          }
          LastError = GetLastError();
          User = LastError;
          if ( LastError > 0 )
            User = (unsigned __int16)LastError | 0x80070000;
          v87 = 39;
          goto LABEL_43;
        }
        if ( a3 == 7 )
        {
          if ( !a8 )
          {
            v87 = 64;
            goto LABEL_5;
          }
          v20 = GetCurrentThread();
          if ( !OpenThreadToken(v20, 8u, 1, &hObject) )
          {
            v22 = GetLastError();
            User = v22;
            if ( v22 > 0 )
              User = (unsigned __int16)v22 | 0x80070000;
            v87 = 71;
LABEL_43:
            v13 = User;
            goto LABEL_6;
          }
          fnEfsLogTrace1Strings(v21, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 74);
          User = EdpInlGetProcessUniqueIdByProcessToken(hObject, &v108);
          if ( (int)fnEfsLogTrace1String1Dword(
                      g_hPublisher,
                      (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                      (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                      (unsigned int)&sourceString,
                      User,
                      37,
                      74) < 0 )
            goto LABEL_7;
          fnEfsLogTrace1Strings(v23, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 76);
          User = CDplServiceImpl::RevertToSelf(v96, &v107);
          if ( (int)fnEfsLogTrace1String1Dword(
                      g_hPublisher,
                      (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                      (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                      (unsigned int)&sourceString,
                      User,
                      37,
                      76) >= 0 )
          {
            v24 = v111;
            v93 = OpenProcess(0x1000u, 0, *(_DWORD *)(v111 + 8));
            if ( v93 )
            {
              fnEfsLogTrace1Strings(v25, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 84);
              User = EdpInlGetProcessUniqueIdByProcessHandle(v93, &v114);
              if ( (int)fnEfsLogTrace1String1Dword(
                          g_hPublisher,
                          (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                          (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                          (unsigned int)&sourceString,
                          User,
                          37,
                          84) >= 0 )
              {
                if ( v108 == v114 )
                {
                  v97 = CDplServiceImpl::SvcLock(v96);
                  fnEfsLogTrace1Strings(v27, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 102);
                  v28 = *(_DWORD *)(v24 + 12);
                  v14 = v93;
                  User = EdpInlBrokerSetProcessTlsIndex(v93, v28);
                  if ( (int)fnEfsLogTrace1String1Dword(
                              g_hPublisher,
                              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                              (unsigned int)&sourceString,
                              User,
                              37,
                              102) >= 0 )
                  {
                    v97 = CDplServiceImpl::SvcUnlockIf(v96, v97);
                    CDplServiceImpl::RestoreImpersonation(v96, &v107);
                  }
                  goto LABEL_8;
                }
                User = -2147024891;
                fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024891, 37, 96);
              }
            }
            else
            {
              v26 = GetLastError();
              User = v26;
              if ( v26 > 0 )
                User = (unsigned __int16)v26 | 0x80070000;
              fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, User, 37, 82);
            }
            goto LABEL_50;
          }
          v16 = v91;
LABEL_192:
          v15 = v92;
          v14 = 0;
          goto LABEL_10;
        }
LABEL_94:
        v87 = -74;
        goto LABEL_5;
      }
      if ( !a8 )
      {
        v87 = -5;
        goto LABEL_5;
      }
      v34 = 0;
      fnEfsLogTrace1Strings(0, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 0);
      v36 = CDplServiceImpl::SetTestDeviceLockState(v35, a5, 0, *(_DWORD *)(a8 + 8));
      goto LABEL_67;
    }
    if ( !a7 )
    {
      v87 = -61;
      goto LABEL_5;
    }
    if ( !a9 )
    {
      v87 = -60;
LABEL_74:
      User = -2147467261;
      v13 = -2147467261;
      goto LABEL_6;
    }
    fnEfsLogTrace1Strings(0, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 205);
    User = DplibpMemAllocEx(136, 0, 0, &v95);
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                User,
                37,
                205) >= 0 )
    {
      v10 = v95;
      memset_0(v95, 0, 0x88u);
      *(_DWORD *)v10 = 136;
      v37 = (struct _GUID *)(a7 + 12);
      *((_DWORD *)v10 + 1) = 2;
      if ( UuidIsNil((UUID *)(a7 + 12), &Status) )
        v37 = 0;
      fnEfsLogTrace1Strings(0, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 217);
      User = Status;
      if ( Status )
        User = Status | 0x80010000;
      if ( (int)fnEfsLogTrace1String1Dword(
                  g_hPublisher,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                  (unsigned int)&sourceString,
                  User,
                  37,
                  217) >= 0 )
      {
        fnEfsLogTrace1Strings(v38, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 232);
        DplKeysState = CDplServiceImpl::GetRevocationInfo(
                         v96,
                         v105,
                         v109,
                         v115,
                         v37,
                         *(struct _FILETIME *)(a7 + 4),
                         0,
                         (int *)v10 + 3,
                         (int *)v10 + 2,
                         (int *)v10 + 4,
                         (struct _FILETIME *)(v10 + 20));
        v89 = -24;
        goto LABEL_187;
      }
LABEL_50:
      v14 = v93;
      goto LABEL_8;
    }
LABEL_155:
    v10 = v95;
    goto LABEL_50;
  }
  if ( !a9 )
  {
    v87 = -95;
    goto LABEL_74;
  }
  fnEfsLogTrace1Strings(a3 - 1, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 170);
  User = DplibpMemAllocEx(136, 0, 0, &v95);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              User,
              37,
              170) < 0 )
    goto LABEL_155;
  v10 = v95;
  memset_0(v95, 0, 0x88u);
  *(_DWORD *)v10 = 136;
  *((_DWORD *)v10 + 1) = 1;
  fnEfsLogTrace1Strings(v40, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 186);
  DplKeysState = CDplServiceImpl::GetDplKeysState(
                   v96,
                   v109,
                   v115,
                   0xFFFFFFFF,
                   v115 == 0,
                   (int *)v10 + 2,
                   (struct _FILETIME *)(v10 + 12),
                   (int *)v10 + 5);
  v89 = -70;
LABEL_187:
  User = DplKeysState;
  v16 = v91;
  v15 = v92;
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              DplKeysState,
              37,
              v89) < 0 )
  {
    v14 = v93;
  }
  else
  {
    *v99 = v10;
    v10 = 0;
    v14 = 0;
  }
LABEL_10:
  CDplServiceImpl::SvcUnlockIf(v96, v97);
  ReleaseIf<CDplAccount>(v113);
  ReleaseIf<CDplUser>(v15);
  v17 = 32;
  v18 = v118;
  do
  {
    *v18++ = 0;
    --v17;
  }
  while ( v17 );
  if ( Src )
    DplibMemFree(Src);
  Src = 0;
  if ( v16 )
    DplibMemFree(v16);
  if ( v110 )
    DplibMemFree(v110);
  v110 = 0;
  if ( v106 )
    DplibMemFree(v106);
  v106 = 0;
  if ( v10 )
    DplibMemFree(v10);
  CDplServiceImpl::RestoreImpersonation(v96, &v107);
  if ( v14 )
    CloseHandle(v14);
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&sourceString,
    User,
    37,
    211);
  return User;
}

```

## disassembly

```asm
0x1800977b0  mov     [rsp-8+arg_10], rbx
0x1800977b5  push    rbp
0x1800977b6  push    rsi
0x1800977b7  push    rdi
0x1800977b8  push    r12
0x1800977ba  push    r13
0x1800977bc  push    r14
0x1800977be  push    r15
0x1800977c0  lea     rbp, [rsp-0C0h]
0x1800977c8  sub     rsp, 1F0h
0x1800977cf  mov     rax, cs:__security_cookie
0x1800977d6  xor     rax, rsp
0x1800977d9  mov     [rbp+0F0h+var_38], rax
0x1800977e0  mov     r15, [rbp+0F0h+arg_20]
0x1800977e7  xor     eax, eax
0x1800977e9  mov     r14, [rbp+0F0h+arg_28]
0x1800977f0  xorps   xmm0, xmm0
0x1800977f3  mov     rsi, [rbp+0F0h+arg_38]
0x1800977fa  xorps   xmm1, xmm1
0x1800977fd  mov     rdi, [rbp+0F0h+arg_40]
0x180097804  mov     ebx, r8d
0x180097807  mov     r13, [rbp+0F0h+arg_30]
0x18009780e  lea     r8, sourceString
0x180097815  mov     [rbp+0F0h+var_108], r9
0x180097819  mov     r12d, eax
0x18009781c  mov     [rbp+0F0h+var_B0], rdx
0x180097820  lea     r9d, [rax+25h]
0x180097824  lea     rdx, EFS_TRACE_ENTER_EVENT
0x18009782b  mov     [rbp+0F0h+var_148], rcx
0x18009782f  mov     [rbp+0F0h+var_E8], r15
0x180097833  mov     [rbp+0F0h+var_B8], r14
0x180097837  mov     [rbp+0F0h+var_D8], rsi
0x18009783b  mov     [rbp+0F0h+var_130], rdi
0x18009783f  mov     [rbp+0F0h+Status], eax
0x180097842  mov     [rbp+0F0h+var_150], rax
0x180097846  mov     [rbp+0F0h+hObject], rax
0x18009784a  mov     [rbp+0F0h+var_F8], rax
0x18009784e  mov     [rbp+0F0h+var_F0], rax
0x180097852  mov     [rbp+0F0h+var_C0], rax
0x180097856  mov     [rbp+0F0h+var_160], rax
0x18009785a  mov     [rbp+0F0h+var_140], eax
0x18009785d  mov     [rbp+0F0h+var_170], rax
0x180097861  mov     [rbp+0F0h+var_E0], rax
0x180097865  mov     [rbp+0F0h+var_168], rax
0x180097869  mov     [rbp+0F0h+var_C8], rax
0x18009786d  mov     [rbp+0F0h+var_100], rax
0x180097871  mov     [rbp+0F0h+var_110], rax
0x180097875  mov     dword ptr [rbp+0F0h+Size+4], eax
0x180097878  mov     [rbp+0F0h+var_D0], eax
0x18009787b  mov     [rbp+0F0h+Src], rax
0x18009787f  mov     dword ptr [rbp+0F0h+Size], eax
0x180097882  movups  xmmword ptr [rbp+0F0h+var_A8.Data1], xmm0
0x180097886  mov     [rbp+0F0h+var_11C], 0FFFFFFFFh
0x18009788d  mov     [rbp+0F0h+var_118], eax
0x180097890  movups  xmmword ptr [rbp+0F0h+var_78], xmm0
0x180097894  mov     dword ptr [rsp+220h+var_200], 1689h
0x18009789c  movups  [rbp+0F0h+var_68], xmm0
0x1800978a3  movups  xmmword ptr [rbp+0F0h+var_58], xmm1
0x1800978aa  movups  [rbp+0F0h+var_48], xmm1
0x1800978b1  movups  xmmword ptr [rbp+0F0h+var_98], xmm0
0x1800978b5  movups  [rbp+0F0h+var_88], xmm0
0x1800978b9  call    fnEfsLogTrace1Strings
0x1800978be  xor     edx, edx
0x1800978c0  test    rdi, rdi
0x1800978c3  jz      short loc_1800978CA
0x1800978c5  xor     eax, eax
0x1800978c7  mov     [rdi], rax
0x1800978ca  cmp     [rbp+0F0h+var_108], rdx
0x1800978ce  jnz     loc_180097A2C
0x1800978d4  mov     dword ptr [rsp+220h+var_200], 1691h
0x1800978dc  mov     r9d, 25h ; '%'
0x1800978e2  mov     esi, 80070057h
0x1800978e7  mov     r8d, 80070057h
0x1800978ed  mov     rcx, cs:g_hPublisher
0x1800978f4  lea     rdx, EFS_TRACE_ERROR
0x1800978fb  call    fnEfsLogTrace1
0x180097900  mov     rbx, r12
0x180097903  mov     rdi, [rbp+0F0h+var_168]
0x180097907  mov     r13, [rbp+0F0h+var_170]
0x18009790b  mov     edx, [rbp+0F0h+var_140]; int
0x18009790e  mov     rcx, [rbp+0F0h+var_148]; this
0x180097912  call    ?SvcUnlockIf@CDplServiceImpl@@AEAAHH@Z; CDplServiceImpl::SvcUnlockIf(int)
0x180097917  mov     rcx, [rbp+0F0h+var_C8]
0x18009791b  call    ??$ReleaseIf@VCDplAccount@@@@YAPEAVCDplAccount@@PEAV0@@Z; ReleaseIf<CDplAccount>(CDplAccount *)
0x180097920  mov     rcx, rdi
0x180097923  call    ??$ReleaseIf@VCDplUser@@@@YAPEAVCDplUser@@PEAV0@@Z; ReleaseIf<CDplUser>(CDplUser *)
0x180097928  mov     ecx, 20h ; ' '
0x18009792d  lea     rax, [rbp+0F0h+var_98]
0x180097931  mov     byte ptr [rax], 0
0x180097934  inc     rax
0x180097937  sub     rcx, 1
0x18009793b  jnz     short loc_180097931
0x18009793d  mov     rcx, [rbp+0F0h+Src]; void *
0x180097941  test    rcx, rcx
0x180097944  jz      short loc_18009794B
0x180097946  call    ?DplibMemFree@@YAJPEAX@Z; DplibMemFree(void *)
0x18009794b  mov     [rbp+0F0h+Src], 0
0x180097953  test    r13, r13
0x180097956  jz      short loc_180097960
0x180097958  mov     rcx, r13; void *
0x18009795b  call    ?DplibMemFree@@YAJPEAX@Z; DplibMemFree(void *)
0x180097960  mov     rcx, [rbp+0F0h+var_E0]; void *
0x180097964  test    rcx, rcx
0x180097967  jz      short loc_18009796E
0x180097969  call    ?DplibMemFree@@YAJPEAX@Z; DplibMemFree(void *)
0x18009796e  mov     rcx, [rbp+0F0h+var_100]; void *
0x180097972  mov     [rbp+0F0h+var_E0], 0
0x18009797a  test    rcx, rcx
0x18009797d  jz      short loc_180097984
0x18009797f  call    ?DplibMemFree@@YAJPEAX@Z; DplibMemFree(void *)
0x180097984  mov     [rbp+0F0h+var_100], 0
0x18009798c  test    r12, r12
0x18009798f  jz      short loc_180097999
0x180097991  mov     rcx, r12; void *
0x180097994  call    ?DplibMemFree@@YAJPEAX@Z; DplibMemFree(void *)
0x180097999  mov     rcx, [rbp+0F0h+var_148]; this
0x18009799d  lea     rdx, [rbp+0F0h+var_F8]; void **
0x1800979a1  call    ?RestoreImpersonation@CDplServiceImpl@@AEAAXPEAPEAX@Z; CDplServiceImpl::RestoreImpersonation(void * *)
0x1800979a6  test    rbx, rbx
0x1800979a9  jz      short loc_1800979B4
0x1800979ab  mov     rcx, rbx; hObject
0x1800979ae  call    cs:__imp_CloseHandle
0x1800979b4  mov     rcx, [rbp+0F0h+hObject]; hObject
0x1800979b8  test    rcx, rcx
0x1800979bb  jz      short loc_1800979CB
0x1800979bd  call    cs:__imp_CloseHandle
0x1800979c3  mov     [rbp+0F0h+hObject], 0
0x1800979cb  mov     rcx, cs:g_hPublisher
0x1800979d2  lea     r9, sourceString
0x1800979d9  mov     dword ptr [rsp+220h+var_1F0], 18D3h
0x1800979e1  lea     r8, EFS_TRACE_LEAVE_HR_EVENT_ERROR
0x1800979e8  mov     [rsp+220h+var_1F8.dwLowDateTime], 25h ; '%'
0x1800979f0  lea     rdx, EFS_TRACE_LEAVE_HR_EVENT
0x1800979f7  mov     dword ptr [rsp+220h+var_200], esi
0x1800979fb  call    fnEfsLogTrace1String1Dword
0x180097a00  mov     eax, esi
0x180097a02  mov     rcx, [rbp+0F0h+var_38]
0x180097a09  xor     rcx, rsp; StackCookie
0x180097a0c  call    __security_check_cookie
0x180097a11  mov     rbx, [rsp+220h+arg_10]
0x180097a19  add     rsp, 1F0h
0x180097a20  pop     r15
0x180097a22  pop     r14
0x180097a24  pop     r13
0x180097a26  pop     r12
0x180097a28  pop     rdi
0x180097a29  pop     rsi
0x180097a2a  pop     rbp
0x180097a2b  retn
0x180097a2c  lea     eax, [rbx-1]
0x180097a2f  cmp     eax, 0Eh
0x180097a32  ja      loc_180099190
0x180097a38  cmp     ebx, 8
0x180097a3b  jg      loc_180098277
0x180097a41  jz      loc_180098231
0x180097a47  mov     ecx, ebx
0x180097a49  sub     ecx, 1
0x180097a4c  jz      loc_18009811A
0x180097a52  sub     ecx, 1
0x180097a55  jz      loc_180097F59
0x180097a5b  sub     ecx, 1
0x180097a5e  jz      loc_180097F47
0x180097a64  sub     ecx, 1
0x180097a67  jz      loc_180097ECC
0x180097a6d  sub     ecx, 1
0x180097a70  jz      loc_180097D24
0x180097a76  sub     ecx, 1
0x180097a79  jz      loc_180097D24
0x180097a7f  cmp     ecx, 1
0x180097a82  jnz     loc_1800982B2
0x180097a88  test    rsi, rsi
0x180097a8b  jnz     short loc_180097A9A
0x180097a8d  mov     dword ptr [rsp+220h+var_200], 1740h
0x180097a95  jmp     loc_1800978DC
0x180097a9a  call    cs:__imp_GetCurrentThread
0x180097aa0  mov     edx, 8; DesiredAccess
0x180097aa5  lea     r9, [rbp+0F0h+hObject]; TokenHandle
0x180097aa9  mov     rcx, rax; ThreadHandle
0x180097aac  lea     r8d, [rdx-7]; OpenAsSelf
0x180097ab0  call    cs:__imp_OpenThreadToken
0x180097ab6  test    eax, eax
0x180097ab8  jnz     short loc_180097AE5
0x180097aba  call    cs:__imp_GetLastError
0x180097ac0  mov     esi, eax
0x180097ac2  test    eax, eax
0x180097ac4  jle     short loc_180097ACF
0x180097ac6  movzx   esi, ax
0x180097ac9  or      esi, 80070000h
0x180097acf  mov     dword ptr [rsp+220h+var_200], 1747h
0x180097ad7  mov     r9d, 25h ; '%'
0x180097add  mov     r8d, esi
0x180097ae0  jmp     loc_1800978ED
0x180097ae5  mov     r13d, 25h ; '%'
0x180097aeb  lea     rdi, EFS_TRACE_START_EVENT
0x180097af2  mov     ebx, 174Ah
0x180097af7  lea     r8, sourceString
0x180097afe  mov     r9d, r13d
0x180097b01  mov     dword ptr [rsp+220h+var_200], ebx
0x180097b05  mov     rdx, rdi
0x180097b08  call    fnEfsLogTrace1Strings
0x180097b0d  mov     rcx, [rbp+0F0h+hObject]; void *
0x180097b11  lea     rdx, [rbp+0F0h+var_F0]; unsigned __int64 *
0x180097b15  call    ?EdpInlGetProcessUniqueIdByProcessToken@@YAJPEAXPEA_K@Z; EdpInlGetProcessUniqueIdByProcessToken(void *,unsigned __int64 *)
0x180097b1a  mov     rcx, cs:g_hPublisher
0x180097b21  lea     r14, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180097b28  mov     dword ptr [rsp+220h+var_1F0], ebx
0x180097b2c  lea     r15, EFS_TRACE_COMPLETE_EVENT
0x180097b33  mov     r8, r14
0x180097b36  mov     [rsp+220h+var_1F8.dwLowDateTime], r13d
0x180097b3b  mov     rdx, r15
0x180097b3e  mov     dword ptr [rsp+220h+var_200], eax
0x180097b42  lea     r9, sourceString
0x180097b49  mov     esi, eax
0x180097b4b  call    fnEfsLogTrace1String1Dword
0x180097b50  test    eax, eax
0x180097b52  js      loc_180097900
0x180097b58  mov     ebx, 174Ch
0x180097b5d  lea     r8, sourceString
0x180097b64  mov     r9d, r13d
0x180097b67  mov     dword ptr [rsp+220h+var_200], ebx
0x180097b6b  mov     rdx, rdi
0x180097b6e  call    fnEfsLogTrace1Strings
0x180097b73  mov     r13, [rbp+0F0h+var_148]
0x180097b77  lea     rdx, [rbp+0F0h+var_F8]; void **
0x180097b7b  mov     rcx, r13; this
0x180097b7e  call    ?RevertToSelf@CDplServiceImpl@@AEAAJPEAPEAX@Z; CDplServiceImpl::RevertToSelf(void * *)
0x180097b83  mov     rcx, cs:g_hPublisher
0x180097b8a  lea     r9, sourceString
0x180097b91  mov     dword ptr [rsp+220h+var_1F0], ebx
0x180097b95  mov     r8, r14
0x180097b98  mov     [rsp+220h+var_1F8.dwLowDateTime], 25h ; '%'
0x180097ba0  mov     rdx, r15
0x180097ba3  mov     dword ptr [rsp+220h+var_200], eax
0x180097ba7  mov     esi, eax
0x180097ba9  call    fnEfsLogTrace1String1Dword
0x180097bae  test    eax, eax
0x180097bb0  js      loc_1800991A6
0x180097bb6  mov     rbx, [rbp+0F0h+var_D8]
0x180097bba  xor     edx, edx; bInheritHandle
0x180097bbc  mov     ecx, 1000h; dwDesiredAccess
0x180097bc1  mov     r8d, [rbx+8]; dwProcessId
0x180097bc5  call    cs:__imp_OpenProcess
0x180097bcb  mov     [rbp+0F0h+var_160], rax
0x180097bcf  mov     rsi, rax
0x180097bd2  test    rax, rax
0x180097bd5  jnz     short loc_180097C19
0x180097bd7  call    cs:__imp_GetLastError
0x180097bdd  mov     esi, eax
0x180097bdf  test    eax, eax
0x180097be1  jle     short loc_180097BEC
0x180097be3  movzx   esi, ax
0x180097be6  or      esi, 80070000h
0x180097bec  mov     dword ptr [rsp+220h+var_200], 1752h
0x180097bf4  mov     r8d, esi
0x180097bf7  mov     rcx, cs:g_hPublisher
0x180097bfe  lea     rdx, EFS_TRACE_ERROR
0x180097c05  mov     r9d, 25h ; '%'
0x180097c0b  call    fnEfsLogTrace1
0x180097c10  mov     rbx, [rbp+0F0h+var_160]
0x180097c14  jmp     loc_180097903
0x180097c19  mov     r9d, 25h ; '%'
0x180097c1f  mov     dword ptr [rsp+220h+var_200], 1754h
0x180097c27  lea     r8, sourceString
0x180097c2e  mov     rdx, rdi
0x180097c31  call    fnEfsLogTrace1Strings
0x180097c36  lea     rdx, [rbp+0F0h+var_C0]; unsigned __int64 *
0x180097c3a  mov     rcx, rsi; void *
0x180097c3d  call    ?EdpInlGetProcessUniqueIdByProcessHandle@@YAJPEAXPEA_K@Z; EdpInlGetProcessUniqueIdByProcessHandle(void *,unsigned __int64 *)
0x180097c42  mov     rcx, cs:g_hPublisher
0x180097c49  lea     r9, sourceString
0x180097c50  mov     dword ptr [rsp+220h+var_1F0], 1754h
0x180097c58  mov     r8, r14
0x180097c5b  mov     [rsp+220h+var_1F8.dwLowDateTime], 25h ; '%'
0x180097c63  mov     rdx, r15
0x180097c66  mov     dword ptr [rsp+220h+var_200], eax
0x180097c6a  mov     esi, eax
0x180097c6c  call    fnEfsLogTrace1String1Dword
0x180097c71  test    eax, eax
0x180097c73  js      short loc_180097C10
0x180097c75  mov     rax, [rbp+0F0h+var_C0]
0x180097c79  cmp     [rbp+0F0h+var_F0], rax
0x180097c7d  jz      short loc_180097C97
0x180097c7f  mov     esi, 80070005h
0x180097c84  mov     dword ptr [rsp+220h+var_200], 1760h
0x180097c8c  mov     r8d, 80070005h
0x180097c92  jmp     loc_180097BF7
0x180097c97  mov     rcx, r13; this
0x180097c9a  call    ?SvcLock@CDplServiceImpl@@AEAAHXZ; CDplServiceImpl::SvcLock(void)
0x180097c9f  mov     r9d, 25h ; '%'
0x180097ca5  mov     [rbp+0F0h+var_140], eax
0x180097ca8  lea     r8, sourceString
0x180097caf  mov     dword ptr [rsp+220h+var_200], 1766h
0x180097cb7  mov     rdx, rdi
0x180097cba  call    fnEfsLogTrace1Strings
0x180097cbf  mov     edx, [rbx+0Ch]; unsigned int
0x180097cc2  mov     rbx, [rbp+0F0h+var_160]
0x180097cc6  mov     rcx, rbx; void *
0x180097cc9  call    ?EdpInlBrokerSetProcessTlsIndex@@YAJPEAXK@Z; EdpInlBrokerSetProcessTlsIndex(void *,ulong)
0x180097cce  mov     rcx, cs:g_hPublisher
0x180097cd5  lea     r9, sourceString
  ... truncated ...
```
