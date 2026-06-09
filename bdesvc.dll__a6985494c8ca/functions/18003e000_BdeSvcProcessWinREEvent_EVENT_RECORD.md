# BdeSvcProcessWinREEvent(_EVENT_RECORD *)

- ea: `0x18003e000`
- end: `0x180040d1e`
- name: `?BdeSvcProcessWinREEvent@@YAXPEAU_EVENT_RECORD@@@Z`
- size: `11550`
- prototype: `void __fastcall(struct _EVENT_RECORD *)`
- caller_count: `0`
- callee_count: `39`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180001008`
- `0x1800010d8`
- `0x18000115c`
- `0x180001208`
- `0x180001540`
- `0x1800015e0`
- `0x18000188c`
- `0x180001908`
- `0x180001a30`
- `0x180001f4c`
- `0x180001fe8`
- `0x180009f30`
- `0x180009f60`
- `0x180027508`
- `0x180034070`
- `0x180034d28`
- `0x18003ad48`
- `0x18003ade8`
- `0x18003aee4`
- `0x18003c3f4`
- `0x18003cf1c`
- `0x18003d0dc`
- `0x18003d244`
- `0x18003d3ac`
- `0x18003d540`
- `0x18003d62c`
- `0x18003d718`
- `0x18003d8bc`
- `0x18003e000`
- `0x180040d44`
- `0x180044378`
- `0x18005f4c0`
- `0x18005fec0`
- `0x180061f40`
- `0x180062290`
- `0x18006a26c`
- `0x18006a4bc`
- `0x18006a594`
- `0x180079fd4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180040bdb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180040c04`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180040c29`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180040c53`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180040c7d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180040ca2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180040cc7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180040bdb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180040c04`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180040c29`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180040c53`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180040c7d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180040ca2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180040cc7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180040bc7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180040bf0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180040c15`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180040c3f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180040c69`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180040c8e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180040cb3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180040bc7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180040bf0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180040c15`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180040c3f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180040c69`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180040c8e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180040cb3`
- `FVEAPI!FveGetVolumeNameW` at `0x18003e6e4`
- `FVEAPI!FveGetVolumeNameW` at `0x18003e6e4`
- `FVEAPI!FveCloseVolume` at `0x18003e666`
- `FVEAPI!FveCloseVolume` at `0x18003e666`

## string_xrefs

- `0x18003e9da`: `base\ngscb\cornerstone\bdesvc\svc\thread.cpp`

## pseudocode

```c
void __fastcall BdeSvcProcessWinREEvent(struct _EVENT_RECORD *a1)
{
  int v2; // ebx
  struct _TRACE_EVENT_INFO *v3; // r14
  unsigned __int16 *v4; // r15
  unsigned __int16 *v5; // r13
  struct RecoveryTelemetery *Instance; // rdi
  __int64 v7; // r12
  unsigned int EventInformation; // eax
  unsigned int Id; // ebx
  int v10; // r8d
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  __int16 v14; // bx
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  int v18; // ebx
  int v19; // eax
  int v20; // eax
  int VolumeNameW; // eax
  __int64 v22; // rdx
  int v23; // ebx
  unsigned int v24; // eax
  int v25; // ecx
  const unsigned __int16 *v26; // rdx
  __int64 v27; // rcx
  int v28; // ecx
  int v29; // r8d
  int v30; // r9d
  const unsigned __int16 *v31; // rdx
  int v32; // ecx
  int v33; // r8d
  int v34; // r9d
  int v35; // ecx
  int v36; // r8d
  int v37; // r9d
  unsigned int v38; // eax
  int v39; // ecx
  unsigned int v40; // eax
  int v41; // ecx
  unsigned int v42; // r9d
  int v43; // ecx
  int v44; // r8d
  int v45; // r9d
  int v46; // ecx
  int v47; // r8d
  int v48; // r9d
  int v49; // ecx
  int v50; // r8d
  int v51; // r9d
  unsigned int v52; // esi
  unsigned int v53; // r12d
  int v54; // ecx
  int v55; // r8d
  unsigned int v56; // r9d
  unsigned __int64 v57; // r9
  __int16 v58; // ax
  unsigned int v59; // eax
  const unsigned __int16 *v60; // rdx
  int v61; // ecx
  int v62; // r8d
  int v63; // r9d
  char *v64; // rdx
  int v65; // ecx
  int v66; // r8d
  int v67; // r9d
  int v68; // ecx
  int v69; // r8d
  int v70; // r9d
  int v71; // ecx
  int v72; // r8d
  int v73; // r9d
  void *v74; // rbx
  HANDLE ProcessHeap; // rax
  void *v76; // rbx
  HANDLE v77; // rax
  HANDLE v78; // rax
  unsigned __int16 *v79; // rbx
  HANDLE v80; // rax
  unsigned __int16 *v81; // rbx
  HANDLE v82; // rax
  HANDLE v83; // rax
  HANDLE v84; // rax
  unsigned int v85; // [rsp+20h] [rbp-E0h]
  unsigned int v86; // [rsp+20h] [rbp-E0h]
  unsigned int v87; // [rsp+20h] [rbp-E0h]
  unsigned int v88; // [rsp+20h] [rbp-E0h]
  char v89; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v90[7]; // [rsp+51h] [rbp-AFh] BYREF
  unsigned __int16 *v91; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v92; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v93; // [rsp+68h] [rbp-98h] BYREF
  LPVOID lpMem[2]; // [rsp+78h] [rbp-88h]
  LPVOID v95[2]; // [rsp+88h] [rbp-78h]
  __int64 v96; // [rsp+98h] [rbp-68h] BYREF
  __int64 *v97; // [rsp+A0h] [rbp-60h]
  __int128 *v98; // [rsp+A8h] [rbp-58h] BYREF
  struct _TRACE_EVENT_INFO **v99; // [rsp+B0h] [rbp-50h]
  __int64 v100; // [rsp+B8h] [rbp-48h] BYREF
  __int64 *v101; // [rsp+C0h] [rbp-40h]
  __int64 v102; // [rsp+C8h] [rbp-38h] BYREF
  __int64 *v103; // [rsp+D0h] [rbp-30h]
  __int64 v104; // [rsp+D8h] [rbp-28h] BYREF
  __int64 *v105; // [rsp+E0h] [rbp-20h]
  __int64 **v106; // [rsp+E8h] [rbp-18h] BYREF
  __int64 ****v107; // [rsp+F0h] [rbp-10h]
  __int64 v108; // [rsp+F8h] [rbp-8h] BYREF
  __int64 *v109; // [rsp+100h] [rbp+0h]
  __int64 v110; // [rsp+108h] [rbp+8h] BYREF
  __int64 *v111; // [rsp+110h] [rbp+10h]
  __int64 v112; // [rsp+118h] [rbp+18h] BYREF
  __int64 *v113; // [rsp+120h] [rbp+20h]
  __int64 v114; // [rsp+128h] [rbp+28h] BYREF
  __int64 *v115; // [rsp+130h] [rbp+30h]
  __int64 v116; // [rsp+138h] [rbp+38h] BYREF
  __int64 *v117; // [rsp+140h] [rbp+40h]
  __int64 v118; // [rsp+148h] [rbp+48h] BYREF
  __int64 *v119; // [rsp+150h] [rbp+50h]
  int v120; // [rsp+158h] [rbp+58h] BYREF
  void *v121; // [rsp+160h] [rbp+60h] BYREF
  __int64 v122; // [rsp+168h] [rbp+68h]
  __int64 v123; // [rsp+170h] [rbp+70h]
  unsigned __int16 *v124; // [rsp+178h] [rbp+78h] BYREF
  __int128 v125; // [rsp+180h] [rbp+80h] BYREF
  __int128 v126; // [rsp+190h] [rbp+90h]
  __int128 v127; // [rsp+1A0h] [rbp+A0h]
  __int128 v128; // [rsp+1B0h] [rbp+B0h] BYREF
  __int128 v129; // [rsp+1C0h] [rbp+C0h] BYREF
  __int128 v130; // [rsp+1D0h] [rbp+D0h]
  struct _GUID v131; // [rsp+1E0h] [rbp+E0h] BYREF
  unsigned int v132; // [rsp+1F0h] [rbp+F0h] BYREF
  unsigned int v133; // [rsp+1F4h] [rbp+F4h] BYREF
  __int64 *v134; // [rsp+1F8h] [rbp+F8h] BYREF
  __int128 *v135; // [rsp+200h] [rbp+100h]
  const wchar_t *v136; // [rsp+208h] [rbp+108h]
  const wchar_t *v137; // [rsp+210h] [rbp+110h]
  void *v138; // [rsp+218h] [rbp+118h]
  __int64 v139; // [rsp+220h] [rbp+120h]
  unsigned __int16 *v140; // [rsp+228h] [rbp+128h] BYREF
  __int128 *v141; // [rsp+230h] [rbp+130h] BYREF
  __int128 *v142; // [rsp+238h] [rbp+138h]
  const wchar_t *v143; // [rsp+240h] [rbp+140h]
  const wchar_t *v144; // [rsp+248h] [rbp+148h]
  int *v145; // [rsp+250h] [rbp+150h]
  __int64 v146; // [rsp+258h] [rbp+158h]
  int v147; // [rsp+260h] [rbp+160h] BYREF
  struct _TRACE_EVENT_INFO *v148; // [rsp+268h] [rbp+168h] BYREF
  __int128 *v149; // [rsp+270h] [rbp+170h]
  const wchar_t *v150; // [rsp+278h] [rbp+178h]
  const wchar_t *v151; // [rsp+280h] [rbp+180h]
  struct _SYSTEMTIME *v152; // [rsp+288h] [rbp+188h]
  __int64 v153; // [rsp+290h] [rbp+190h]
  __int128 *v154; // [rsp+298h] [rbp+198h] BYREF
  __int128 *v155; // [rsp+2A0h] [rbp+1A0h]
  const wchar_t *v156; // [rsp+2A8h] [rbp+1A8h]
  const wchar_t *v157; // [rsp+2B0h] [rbp+1B0h]
  int *v158; // [rsp+2B8h] [rbp+1B8h]
  __int64 v159; // [rsp+2C0h] [rbp+1C0h]
  int v160; // [rsp+2C8h] [rbp+1C8h] BYREF
  __int128 ***v161; // [rsp+2D0h] [rbp+1D0h] BYREF
  __int128 ***v162; // [rsp+2D8h] [rbp+1D8h]
  const wchar_t *v163; // [rsp+2E0h] [rbp+1E0h]
  const wchar_t *v164; // [rsp+2E8h] [rbp+1E8h]
  LPVOID v165; // [rsp+2F0h] [rbp+1F0h]
  int v166; // [rsp+2F8h] [rbp+1F8h]
  int v167; // [rsp+2FCh] [rbp+1FCh]
  __int128 **v168; // [rsp+300h] [rbp+200h] BYREF
  __int128 **v169; // [rsp+308h] [rbp+208h]
  const wchar_t *v170; // [rsp+310h] [rbp+210h]
  const unsigned __int16 *v171; // [rsp+318h] [rbp+218h]
  unsigned __int16 **v172; // [rsp+320h] [rbp+220h]
  __int64 v173; // [rsp+328h] [rbp+228h]
  __int128 *v174; // [rsp+330h] [rbp+230h] BYREF
  __int128 *v175; // [rsp+338h] [rbp+238h]
  const wchar_t *v176; // [rsp+340h] [rbp+240h]
  const wchar_t *v177; // [rsp+348h] [rbp+248h]
  void **v178; // [rsp+350h] [rbp+250h]
  __int64 v179; // [rsp+358h] [rbp+258h]
  BYTE pBuffer[16]; // [rsp+360h] [rbp+260h] BYREF
  struct _SYSTEMTIME v181; // [rsp+370h] [rbp+270h] BYREF
  _OWORD v182[3]; // [rsp+380h] [rbp+280h] BYREF
  unsigned __int16 v183[264]; // [rsp+3B0h] [rbp+2B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+618h] [rbp+518h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
  v2 = 0;
  v3 = 0;
  v148 = 0;
  v131 = 0;
  v91 = 0;
  v92 = 0;
  *(_OWORD *)pBuffer = 0;
  v147 = 0;
  v181 = 0;
  v4 = 0;
  v124 = 0;
  v133 = 0;
  v93 = 0;
  *(_OWORD *)lpMem = 0;
  *(_OWORD *)v95 = 0;
  v5 = 0;
  v140 = 0;
  v132 = 0;
  Instance = RecoveryTelemetery::getInstance();
  memset(v182, 0, 36);
  v7 = -1;
  v121 = (void *)-1LL;
  v160 = 260;
  memset_0(v183, 0, 0x208u);
  if ( *(_QWORD *)&a1->EventHeader.ProviderId.Data1 == *(_QWORD *)&FVEAPI_Provider.Data1
    && *(_QWORD *)a1->EventHeader.ProviderId.Data4 == *(_QWORD *)FVEAPI_Provider.Data4 )
  {
    v89 = 0;
    EventInformation = BdeSvcGetEventInformation(a1, &v148);
    v3 = v148;
    if ( !EventInformation && !BdeSvcpGetEventLocalSystemTime(&a1->EventHeader, &v181) )
    {
      Id = v3->EventDescriptor.Id;
      if ( (_WORD)Id == 793 )
      {
        if ( BdeSvcParseFveApiOperationalEvent(a1, v3, &v131, &v91, &v92) )
        {
          if ( !Instance )
          {
LABEL_13:
            v2 = 0;
            goto LABEL_228;
          }
          LOWORD(v10) = 793;
LABEL_12:
          RecoveryTelemetery::AddRecoveryEvent(Instance, &v131, v10, 0, 0, 0);
          goto LABEL_13;
        }
        v96 = 0;
        v121 = 0;
        v122 = 0;
        v123 = 0;
        *(_QWORD *)&v129 = L"IdentityGuid";
        *((_QWORD *)&v129 + 1) = L"GUID";
        *(_QWORD *)&v130 = &v131;
        *((_QWORD *)&v130 + 1) = 16;
        *((_QWORD *)&v128 + 1) = &v98;
        v98 = &v128;
        v150 = L"ResealTime";
        v151 = L"SYSTEMTIME";
        v152 = &v181;
        v153 = 16;
        v148 = (struct _TRACE_EVENT_INFO *)&v98;
        v149 = &v128;
        *(_QWORD *)&v128 = &v148;
        v99 = &v148;
        v97 = FVEAPI_OP_BOOT_SETTINGS_RESEAL_TPM_WINRE;
        FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)&v121, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v96);
        FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v121);
        if ( (unsigned int)dword_18009A348 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18009A348, 0x400000000000LL) )
        {
          v14 = 793;
          LOWORD(v120) = 793;
          v124 = (unsigned __int16 *)&v131;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<2>>(
            v11,
            (unsigned int)word_18008D4E2,
            v12,
            v13,
            (__int64)&v124,
            (__int64)&v120);
        }
        else
        {
          v14 = 793;
        }
LABEL_18:
        if ( !Instance )
          goto LABEL_13;
        LOWORD(v10) = v14;
        goto LABEL_12;
      }
      if ( (_WORD)Id == 782 )
      {
        if ( !BdeSvcParseFveApiOperationalEventWithProtectorAndType(a1, v3, &v131, &v91, &v92, pBuffer, &v147) )
        {
          v96 = 0;
          v148 = 0;
          v149 = 0;
          v150 = 0;
          *(_QWORD *)&v129 = L"IdentityGuid";
          *((_QWORD *)&v129 + 1) = L"GUID";
          *(_QWORD *)&v130 = &v131;
          *((_QWORD *)&v130 + 1) = 16;
          *((_QWORD *)&v128 + 1) = &v98;
          v98 = &v128;
          v156 = L"ProtectorGuid";
          v157 = L"GUID";
          v158 = (int *)pBuffer;
          v159 = 16;
          v155 = &v128;
          *(_QWORD *)&v128 = &v154;
          v120 = v147;
          v143 = L"ProtectorType";
          v144 = L"INT32";
          v145 = &v120;
          v146 = 4;
          v142 = (__int128 *)&v154;
          v154 = (__int128 *)&v141;
          v136 = L"UnlockTime";
          v137 = L"SYSTEMTIME";
          v138 = &v181;
          v139 = 16;
          v134 = (__int64 *)&v98;
          v135 = (__int128 *)&v141;
          v141 = (__int128 *)&v134;
          v99 = (struct _TRACE_EVENT_INFO **)&v134;
          v97 = FVEAPI_OP_VOLUME_UNLOCK_WINRE;
          FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)&v148, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v96);
          FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v148);
          if ( (unsigned int)dword_18009A348 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18009A348, 0x400000000000LL) )
          {
            LOWORD(v120) = 782;
            v124 = (unsigned __int16 *)&v131;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<2>>(
              v15,
              (unsigned int)&byte_18008D4A7,
              v16,
              v17,
              (__int64)&v124,
              (__int64)&v120);
          }
          if ( Instance )
            RecoveryTelemetery::AddRecoveryEvent(Instance, &v131, 0x30Eu, 0, 0, 0);
          if ( v147 == 3 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
            v18 = CheckDeviceForClientKeyRotation();
            if ( v18 < 0 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  110,
                  &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids,
                  (unsigned int)v18);
              if ( v18 != -2144272363 && v18 != -2144272161 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0xBA3,
                  (unsigned int)"base\\ngscb\\cornerstone\\bdesvc\\svc\\thread.cpp",
                  (const char *)(unsigned int)v18,
                  v86);
            }
            else
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
              if ( Instance )
                *((_BYTE *)Instance + 18) = 1;
              v19 = FvepOpenVolumeByGuid(&v131, &v121);
              if ( v19 >= 0 )
              {
                v7 = (__int64)v121;
                VolumeNameW = FveGetVolumeNameW(v121, &v160, v183);
                if ( VolumeNameW >= 0 )
                {
                  LODWORD(v182[0]) = 1;
                  *(_OWORD *)((char *)v182 + 4) = *(_OWORD *)pBuffer;
                  *(struct _GUID *)((char *)&v182[1] + 4) = v131;
                  v23 = FveSavePersistentRequest(v183, 1u, (__int64)v182, 0x24u);
                  if ( v23 >= 0 )
                  {
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                      WPP_SF_(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        109,
                        &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
                    v89 = 1;
                  }
                  else
                  {
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
                    {
                      v22 = 2;
                      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                        WPP_SF_d(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          108,
                          &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids,
                          (unsigned int)v23);
                    }
                    v96 = 0;
                    v121 = 0;
                    v122 = 0;
                    v123 = 0;
                    v136 = L"ProtectorGUID";
                    v137 = L"GUID";
                    v138 = pBuffer;
                    v139 = 16;
                    v135 = (__int128 *)&v98;
                    v98 = (__int128 *)&v134;
                    v120 = 1;
                    v143 = L"RequestType";
                    v144 = L"ULONG";
                    v145 = &v120;
                    v146 = 4;
                    v142 = (__int128 *)&v134;
                    v134 = (__int64 *)&v141;
                    v126 = 0;
                    v127 = 0;
                    FveApiEventLogDeclareWSTRING(
                      (struct _FVEAPI_EVENT_DATA *)&v125,
                      (const unsigned __int16 *)v22,
                      L"VolumeName",
                      v183,
                      v86);
                    *((_QWORD *)&v125 + 1) = &v141;
                    v141 = &v125;
                    LODWORD(v148) = v23;
                    v156 = L"hr";
                    v157 = L"HRESULT";
                    v158 = (int *)&v148;
                    v159 = 4;
                    v154 = (__int128 *)&v98;
                    v155 = &v125;
                    *(_QWORD *)&v125 = &v154;
                    v99 = (struct _TRACE_EVENT_INFO **)&v154;
                    v97 = FVEAPI_SAVE_PERSISTENT_REQ_FAILED;
                    FveEventLogHandle::LogFveApiEvent(
                      (FveEventLogHandle *)&v121,
                      (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v96);
                    FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v121);
                  }
                }
                else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    107,
                    &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids,
                    (unsigned int)VolumeNameW);
                }
              }
              else
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    106,
                    &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids,
                    (unsigned int)v19);
                v7 = (__int64)v121;
              }
            }
          }
        }
        goto LABEL_42;
      }
      v24 = (unsigned __int16)Id;
      if ( (unsigned __int16)(Id - 521) <= 0xAu && (v25 = 1977, LOWORD(v24) = Id - 521, _bittest(&v25, v24))
        || (unsigned __int16)(Id - 823) <= 1u )
      {
        if ( !BdeSvcParseFveApiRecoveryEventSimple(a1, v3, &v131) )
        {
          AddWinRERecoveryEventToSqm(Id);
          switch ( (_WORD)Id )
          {
            case 0x209:
              *(_QWORD *)&v128 = 0;
              v96 = 0;
              v97 = 0;
              v98 = 0;
              *(_QWORD *)&v126 = L"IdentityGuid";
              *((_QWORD *)&v126 + 1) = L"GUID";
              *(_QWORD *)&v127 = &v131;
              *((_QWORD *)&v127 + 1) = 16;
              *(_QWORD *)&v125 = &v129;
              *((_QWORD *)&v125 + 1) = &v129;
              *(_QWORD *)&v129 = &v125;
              *((_QWORD *)&v129 + 1) = &v125;
              *((_QWORD *)&v128 + 1) = FVEAPI_GENERAL_PCR_MISMATCH;
              FveEventLogHandle::LogFveApiEvent(
                (FveEventLogHandle *)&v96,
                (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v128);
              FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v96);
              break;
            case 0x20C:
              *(_QWORD *)&v128 = 0;
              v96 = 0;
              v97 = 0;
              v98 = 0;
              *(_QWORD *)&v126 = L"IdentityGuid";
              *((_QWORD *)&v126 + 1) = L"GUID";
              *(_QWORD *)&v127 = &v131;
              *((_QWORD *)&v127 + 1) = 16;
              *(_QWORD *)&v125 = &v129;
              *((_QWORD *)&v125 + 1) = &v129;
              *(_QWORD *)&v129 = &v125;
              *((_QWORD *)&v129 + 1) = &v125;
              *((_QWORD *)&v128 + 1) = FVEAPI_BAD_SRK;
              FveEventLogHandle::LogFveApiEvent(
                (FveEventLogHandle *)&v96,
                (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v128);
              FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v96);
              break;
            case 0x20D:
              *(_QWORD *)&v128 = 0;
              v96 = 0;
              v97 = 0;
              v98 = 0;
              *(_QWORD *)&v126 = L"IdentityGuid";
              *((_QWORD *)&v126 + 1) = L"GUID";
              *(_QWORD *)&v127 = &v131;
              *((_QWORD *)&v127 + 1) = 16;
              *(_QWORD *)&v125 = &v129;
              *((_QWORD *)&v125 + 1) = &v129;
              *(_QWORD *)&v129 = &v125;
              *((_QWORD *)&v129 + 1) = &v125;
              *((_QWORD *)&v128 + 1) = FVEAPI_TPM_DISABLED;
              FveEventLogHandle::LogFveApiEvent(
                (FveEventLogHandle *)&v96,
                (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v128);
              FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v96);
              break;
            case 0x20E:
              *(_QWORD *)&v128 = 0;
              v96 = 0;
              v97 = 0;
              v98 = 0;
              *(_QWORD *)&v126 = L"IdentityGuid";
              *((_QWORD *)&v126 + 1) = L"GUID";
              *(_QWORD *)&v127 = &v131;
              *((_QWORD *)&v127 + 1) = 16;
              *(_QWORD *)&v125 = &v129;
              *((_QWORD *)&v125 + 1) = &v129;
              *(_QWORD *)&v129 = &v125;
              *((_QWORD *)&v129 + 1) = &v125;
              *((_QWORD *)&v128 + 1) = FVEAPI_TPM_INVALIDATED;
              FveEventLogHandle::LogFveApiEvent(
                (FveEventLogHandle *)&v96,
                (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v128);
              FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v96);
              break;
            case 0x210:
              *(_QWORD *)&v128 = 0;
              v96 = 0;
              v97 = 0;
              v98 = 0;
              *(_QWORD *)&v126 = L"IdentityGuid";
              *((_QWORD *)&v126 + 1) = L"GUID";
              *(_QWORD *)&v127 = &v131;
              *((_QWORD *)&v127 + 1) = 16;
              *(_QWORD *)&v125 = &v129;
              *((_QWORD *)&v125 + 1) = &v129;
              *(_QWORD *)&v129 = &v125;
              *((_QWORD *)&v129 + 1) = &v125;
              *((_QWORD *)&v128 + 1) = FVEAPI_DEBUG_ENABLED;
              FveEventLogHandle::LogFveApiEvent(
                (FveEventLogHandle *)&v96,
                (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v128);
              FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v96);
              break;
            case 0x211:
              *(_QWORD *)&v128 = 0;
              v96 = 0;
              v97 = 0;
              v98 = 0;
              *(_QWORD *)&v126 = L"IdentityGuid";
              *((_QWORD *)&v126 + 1) = L"GUID";
              *(_QWORD *)&v127 = &v131;
              *((_QWORD *)&v127 + 1) = 16;
              *(_QWORD *)&v125 = &v129;
              *((_QWORD *)&v125 + 1) = &v129;
              *(_QWORD *)&v129 = &v125;
              *((_QWORD *)&v129 + 1) = &v125;
              *((_QWORD *)&v128 + 1) = FVEAPI_CI_DISABLED;
              FveEventLogHandle::LogFveApiEvent(
                (FveEventLogHandle *)&v96,
                (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v128);
              FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v96);
              break;
            case 0x337:
              *(_QWORD *)&v128 = 0;
              v96 = 0;
              v97 = 0;
              v98 = 0;
              *(_QWORD *)&v126 = L"IdentityGuid";
              *((_QWORD *)&v126 + 1) = L"GUID";
              *(_QWORD *)&v127 = &v131;
              *((_QWORD *)&v127 + 1) = 16;
              *(_QWORD *)&v125 = &v129;
              *((_QWORD *)&v125 + 1) = &v129;
              *(_QWORD *)&v129 = &v125;
              *((_QWORD *)&v129 + 1) = &v125;
              *((_QWORD *)&v128 + 1) = FVEAPI_SECUREBOOT_DISABLED;
              FveEventLogHandle::LogFveApiEvent(
                (FveEventLogHandle *)&v96,
                (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v128);
              FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v96);
              break;
            case 0x338:
              *(_QWORD *)&v128 = 0;
              v96 = 0;
              v97 = 0;
              v98 = 0;
              *(_QWORD *)&v126 = L"IdentityGuid";
              *((_QWORD *)&v126 + 1) = L"GUID";
              *(_QWORD *)&v127 = &v131;
              *((_QWORD *)&v127 + 1) = 16;
              *(_QWORD *)&v125 = &v129;
              *((_QWORD *)&v125 + 1) = &v129;
              *(_QWORD *)&v129 = &v125;
              *((_QWORD *)&v129 + 1) = &v125;
              *((_QWORD *)&v128 + 1) = FVEAPI_SECUREBOOT_CONFIG_CHANGE;
              FveEventLogHandle::LogFveApiEvent(
                (FveEventLogHandle *)&v96,
                (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v128);
              FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v96);
              break;
            case 0x212:
              *(_QWORD *)&v128 = 0;
              v96 = 0;
              v97 = 0;
              v98 = 0;
              *(_QWORD *)&v126 = L"IdentityGuid";
              *((_QWORD *)&v126 + 1) = L"GUID";
              *(_QWORD *)&v127 = &v131;
              *((_QWORD *)&v127 + 1) = 16;
              *(_QWORD *)&v125 = &v129;
              *((_QWORD *)&v125 + 1) = &v129;
              *(_QWORD *)&v129 = &v125;
              *((_QWORD *)&v129 + 1) = &v125;
              *((_QWORD *)&v128 + 1) = FVEAPI_DEVICE_LOCKOUT;
              FveEventLogHandle::LogFveApiEvent(
                (FveEventLogHandle *)&v96,
                (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v128);
              FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v96);
              break;
            case 0x213:
              *(_QWORD *)&v128 = 0;
              v96 = 0;
              v97 = 0;
              v98 = 0;
              *(_QWORD *)&v126 = L"IdentityGuid";
              *((_QWORD *)&v126 + 1) = L"GUID";
              *(_QWORD *)&v127 = &v131;
              *((_QWORD *)&v127 + 1) = 16;
              *(_QWORD *)&v125 = &v129;
              *((_QWORD *)&v125 + 1) = &v129;
              *(_QWORD *)&v129 = &v125;
              *((_QWORD *)&v129 + 1) = &v125;
              *((_QWORD *)&v128 + 1) = FVEAPI_DEVICE_LOCKOUT_MISMATCH;
              FveEventLogHandle::LogFveApiEvent(
                (FveEventLogHandle *)&v96,
                (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v128);
              FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v96);
              break;
            default:
              MicrosoftTelemetryAssertTriggeredNoArgs();
              break;
          }
          if ( (unsigned int)dword_18009A348 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18009A348, 0x400000000000LL) )
          {
            LOWORD(v120) = Id;
            v124 = (unsigned __int16 *)&v131;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<2>>(
              v65,
              (unsigned int)word_18008D462,
              v66,
              v67,
              (__int64)&v124,
              (__int64)&v120);
          }
          if ( (unsigned int)dword_18009A310 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18009A310, 0x800000000000LL) )
          {
            LODWORD(v124) = 0;
            v121 = &v131;
            LOWORD(v120) = Id;
            v140 = (unsigned __int16 *)0x1000000;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<2>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
              v68,
              (unsigned int)byte_18008D411,
              v69,
              v70,
              (__int64)&v140,
              (__int64)&v120,
              (__int64)&v121,
              (__int64)&v124);
          }
          if ( Instance )
            RecoveryTelemetery::AddRecoveryEvent(Instance, &v131, Id, 0, 0, 0);
          goto LABEL_42;
        }
        if ( !Instance )
          goto LABEL_13;
        v42 = 0;
LABEL_132:
        RecoveryTelemetery::AddRecoveryEvent(Instance, &v131, Id, v42, 0, 0);
        goto LABEL_13;
      }
      switch ( (_WORD)Id )
      {
        case 0x20A:
          if ( !BdeSvcParseFveApiRecoveryEventBadCodeId(a1, v3, &v124, &v131) )
          {
            v14 = 522;
            AddWinRERecoveryEventToSqm(0x20Au);
            v100 = 0;
            v101 = 0;
            v121 = 0;
            v122 = 0;
            v123 = 0;
            v103 = &v102;
            v102 = (__int64)&v102;
            v128 = 0;
            v129 = 0;
            v130 = 0;
            v4 = v124;
            FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)&v128, v26, L"BootApplication", v124, v85);
            if ( (__int64 *)*v103 != &v102
              || (*(_QWORD *)&v128 = &v102,
                  *((_QWORD *)&v128 + 1) = v103,
                  *v103 = (__int64)&v128,
                  v136 = L"IdentityGuid",
                  v137 = L"GUID",
                  v138 = &v131,
                  v139 = 16,
                  (__int64 *)v128 != &v102) )
            {
              __fastfail(3u);
            }
            v134 = &v102;
            v135 = &v128;
            *(_QWORD *)&v128 = &v134;
            v103 = (__int64 *)&v134;
            v101 = FVEAPI_BAD_CODE_ID;
            FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)&v121, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v100);
            FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v121);
            if ( (unsigned int)dword_18009A348 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18009A348, 0x400000000000LL) )
            {
              LOWORD(v120) = 522;
              v124 = v4;
              v121 = &v131;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>>(
                v27,
                byte_18008D3BB);
            }
            if ( (unsigned int)dword_18009A310 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18009A310, 0x800000000000LL) )
            {
              LODWORD(v148) = 0;
              v124 = (unsigned __int16 *)&v131;
              LOWORD(v120) = 522;
              v121 = (void *)0x1000000;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<2>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
                v28,
                (unsigned int)word_18008D36A,
                v29,
                v30,
                (__int64)&v121,
                (__int64)&v120,
                (__int64)&v124,
                (__int64)&v148);
            }
            goto LABEL_18;
          }
          if ( Instance )
            RecoveryTelemetery::AddRecoveryEvent(Instance, &v131, 0x20Au, 0, 0, 0);
          goto LABEL_75;
        case 0x20B:
          if ( !BdeSvcParseFveApiRecoveryEventBadCodeOption(a1, v3, (int *)&v133, &v124, &v131) )
          {
            AddWinREBCDRecoveryEventToSqm(0x20Bu, v133);
            v104 = 0;
            v105 = 0;
            v121 = 0;
            v122 = 0;
            v123 = 0;
            LODWORD(v148) = v133;
            v136 = L"BCDSetting";
            v137 = L"INT32";
            v138 = &v148;
            v139 = 4;
            v134 = (__int64 *)&v106;
            v135 = (__int128 *)&v106;
            v106 = &v134;
            v107 = (__int64 ****)&v134;
            v128 = 0;
            v129 = 0;
            v130 = 0;
            v4 = v124;
            FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)&v128, v31, L"BootApplication", v124, v87);
            if ( *v107 != &v106
              || (*(_QWORD *)&v128 = &v106,
                  *((_QWORD *)&v128 + 1) = v107,
                  *v107 = (__int64 ***)&v128,
                  v143 = L"IdentityGuid",
                  v144 = L"GUID",
                  v145 = (int *)&v131,
                  v146 = 16,
                  (__int64 ***)v128 != &v106) )
            {
              __fastfail(3u);
            }
            v141 = (__int128 *)&v106;
            v142 = &v128;
            *(_QWORD *)&v128 = &v141;
            v107 = (__int64 ****)&v141;
            v105 = FVEAPI_BAD_CODE_OPTION;
            FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)&v121, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v104);
            FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v121);
            if ( (unsigned int)dword_18009A348 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18009A348, 0x400000000000LL) )
            {
              v124 = v4;
              v121 = &v131;
              LOWORD(v120) = 523;
              LODWORD(v148) = v133;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>>(
                v32,
                (unsigned int)&word_18008D306,
                v33,
                v34,
                (__int64)&v148,
                (__int64)&v120,
                (__int64)&v121,
                (__int64)&v124);
            }
            if ( (unsigned int)dword_18009A310 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18009A310, 0x800000000000LL) )
            {
              LODWORD(v148) = v133;
              v124 = (unsigned __int16 *)&v131;
              LOWORD(v120) = 523;
              v121 = (void *)0x1000000;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<2>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
                v35,
                (unsigned int)byte_18008D2B5,
                v36,
                v37,
                (__int64)&v121,
                (__int64)&v120,
                (__int64)&v124,
                (__int64)&v148);
            }
            if ( Instance )
              RecoveryTelemetery::AddRecoveryEvent(Instance, &v131, 0x20Bu, 0, v133, 0);
            goto LABEL_13;
          }
          if ( Instance )
            RecoveryTelemetery::AddRecoveryEvent(Instance, &v131, 0x20Bu, 0, v133, 0);
LABEL_75:
          v2 = 0;
          v4 = v124;
          goto LABEL_228;
        case 0x32A:
          *(_QWORD *)&v128 = 0;
          v96 = 0;
          v97 = 0;
          v98 = 0;
          *((_QWORD *)&v129 + 1) = &v129;
          *(_QWORD *)&v129 = &v129;
          *((_QWORD *)&v128 + 1) = FVEAPI_OP_SECUREBOOT_DISABLED;
          FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)&v96, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v128);
          FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v96);
LABEL_193:
          if ( (unsigned int)dword_18009A348 <= 4 || !(unsigned __int8)tlgKeywordOn(&dword_18009A348, 0x400000000000LL) )
            goto LABEL_13;
          v64 = byte_18008D275;
          goto LABEL_191;
      }
      v38 = (unsigned __int16)Id;
      if ( (unsigned __int16)(Id - 809) <= 0x1Eu )
      {
        v39 = 2097152225;
        LOWORD(v38) = Id - 809;
        if ( _bittest(&v39, v38) )
        {
          switch ( (_WORD)Id )
          {
            case 0x329:
              v96 = 0;
              v121 = 0;
              v122 = 0;
              v123 = 0;
              v99 = (struct _TRACE_EVENT_INFO **)&v98;
              v98 = (__int128 *)&v98;
              v97 = FVEAPI_OP_SECUREBOOT_DISABLED_IN_POLICY;
              FveEventLogHandle::LogFveApiEvent(
                (FveEventLogHandle *)&v121,
                (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v96);
              FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v121);
              break;
            case 0x32E:
              v96 = 0;
              v121 = 0;
              v122 = 0;
              v123 = 0;
              v99 = (struct _TRACE_EVENT_INFO **)&v98;
              v98 = (__int128 *)&v98;
              v97 = FVEAPI_OP_SECUREBOOT_TCG_LOG_AUTHORITY_INVALID;
              FveEventLogHandle::LogFveApiEvent(
                (FveEventLogHandle *)&v121,
                (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v96);
              FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v121);
              break;
            case 0x32F:
              v96 = 0;
              v121 = 0;
              v122 = 0;
              v123 = 0;
              v99 = (struct _TRACE_EVENT_INFO **)&v98;
              v98 = (__int128 *)&v98;
              v97 = FVEAPI_OP_SECUREBOOT_TCG_LOG_SEPARATOR_INVALID;
              FveEventLogHandle::LogFveApiEvent(
                (FveEventLogHandle *)&v121,
                (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v96);
              FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v121);
              break;
            case 0x330:
              v96 = 0;
              v121 = 0;
              v122 = 0;
              v123 = 0;
              v99 = (struct _TRACE_EVENT_INFO **)&v98;
              v98 = (__int128 *)&v98;
              v97 = FVEAPI_OP_SECUREBOOT_TCG_LOG_INVALID;
              FveEventLogHandle::LogFveApiEvent(
                (FveEventLogHandle *)&v121,
                (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v96);
              FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v121);
              break;
            case 0x341:
              v96 = 0;
              v121 = 0;
              v122 = 0;
              v123 = 0;
              v99 = (struct _TRACE_EVENT_INFO **)&v98;
              v98 = (__int128 *)&v98;
              v97 = FVEAPI_OP_SECUREBOOT_CUSTOM_POLICY_INSTALLED;
              FveEventLogHandle::LogFveApiEvent(
                (FveEventLogHandle *)&v121,
                (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v96);
              FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v121);
              break;
            case 0x343:
              v96 = 0;
              v121 = 0;
              v122 = 0;
              v123 = 0;
              v99 = (struct _TRACE_EVENT_INFO **)&v98;
              v98 = (__int128 *)&v98;
              v97 = FVEAPI_OP_SECUREBOOT_TCG_LOG_AUTHORITY_INVALID_STRUCTURE;
              FveEventLogHandle::LogFveApiEvent(
                (FveEventLogHandle *)&v121,
                (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v96);
              FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v121);
              break;
            case 0x344:
              v96 = 0;
              v121 = 0;
              v122 = 0;
              v123 = 0;
              v99 = (struct _TRACE_EVENT_INFO **)&v98;
              v98 = (__int128 *)&v98;
              v97 = FVEAPI_OP_SECUREBOOT_TCG_LOG_AUTHORITY_INVALID_SIGNATURE_OWNER;
              FveEventLogHandle::LogFveApiEvent(
                (FveEventLogHandle *)&v121,
                (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v96);
              FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v121);
              break;
            case 0x345:
              v96 = 0;
              v121 = 0;
              v122 = 0;
              v123 = 0;
              v99 = (struct _TRACE_EVENT_INFO **)&v98;
              v98 = (__int128 *)&v98;
              v97 = FVEAPI_OP_SECUREBOOT_TCG_LOG_AUTHORITY_SIGNATURE_NOT_IN_DB;
              FveEventLogHandle::LogFveApiEvent(
                (FveEventLogHandle *)&v121,
                (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v96);
              FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v121);
              break;
            case 0x346:
              v96 = 0;
              v121 = 0;
              v122 = 0;
              v123 = 0;
              v99 = (struct _TRACE_EVENT_INFO **)&v98;
              v98 = (__int128 *)&v98;
              v97 = FVEAPI_OP_SECUREBOOT_FAILED_BOOTLOADER_SIGNATURE_CHECK;
              FveEventLogHandle::LogFveApiEvent(
                (FveEventLogHandle *)&v121,
                (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v96);
              FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v121);
              break;
            case 0x347:
              v96 = 0;
              v121 = 0;
              v122 = 0;
              v123 = 0;
              v99 = (struct _TRACE_EVENT_INFO **)&v98;
              v98 = (__int128 *)&v98;
              v97 = FVEAPI_OP_SECUREBOOT_AUTHORITY_SIGNATURE_NOT_IN_BOOTLOADER_CERT_CHAIN;
              FveEventLogHandle::LogFveApiEvent(
                (FveEventLogHandle *)&v121,
                (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v96);
              FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v121);
              break;
            default:
              MicrosoftTelemetryAssertTriggeredNoArgs();
              break;
          }
          goto LABEL_193;
        }
      }
      if ( (unsigned __int16)(Id - 811) > 2u )
      {
        if ( (_WORD)Id == 817 || (_WORD)Id == 834 )
        {
          if ( !BdeSvcParseFveApiTpmSealEvent(a1, v3, (struct PARSED_TPM_SEAL_EVENT *)&v93) )
          {
            *(_QWORD *)&v128 = 0;
            v96 = 0;
            v97 = 0;
            v98 = 0;
            if ( (_WORD)Id == 817 )
            {
              LODWORD(v148) = v93;
              v136 = L"PCRBitmap";
              v137 = L"ULONG";
              v138 = &v148;
              v139 = 4;
              v135 = &v129;
              *(_QWORD *)&v129 = &v134;
              LODWORD(v140) = DWORD1(v93);
              v143 = L"PCRBitmapSource";
              v144 = L"ULONG";
              v145 = (int *)&v140;
              v146 = 4;
              v142 = (__int128 *)&v134;
              v134 = (__int64 *)&v141;
              v52 = DWORD2(v93);
              LODWORD(v121) = DWORD2(v93);
              v156 = L"PCRValuesSize";
              v157 = L"ULONG";
              v158 = (int *)&v121;
              v159 = 4;
              v155 = (__int128 *)&v141;
              v141 = (__int128 *)&v154;
              v163 = L"PCRValues";
              v164 = L"BYTE";
              v165 = lpMem[0];
              v166 = DWORD2(v93);
              v167 = 0;
              v162 = (__int128 ***)&v154;
              v154 = (__int128 *)&v161;
              v53 = (unsigned int)lpMem[1];
              LODWORD(v124) = lpMem[1];
              v170 = L"FilteredTcgLogSize";
              v171 = L"ULONG";
              v172 = &v124;
              v173 = 4;
              v169 = (__int128 **)&v161;
              v161 = &v168;
              v176 = L"FilteredTcgLog";
              v177 = L"BYTE";
              v178 = (void **)v95[0];
              v179 = LODWORD(lpMem[1]);
              v175 = (__int128 *)&v168;
              v168 = &v174;
              LOWORD(v120) = 0;
              *(_QWORD *)&v126 = L"TpmSrkAesStrengthInBits";
              *((_QWORD *)&v126 + 1) = L"UINT16";
              *(_QWORD *)&v127 = &v120;
              *((_QWORD *)&v127 + 1) = 2;
              *(_QWORD *)&v125 = &v129;
              *((_QWORD *)&v125 + 1) = &v174;
              v174 = &v125;
              *((_QWORD *)&v129 + 1) = &v125;
              *((_QWORD *)&v128 + 1) = FVEAPI_OP_TPM_SEAL;
            }
            else
            {
              LODWORD(v124) = v93;
              *(_QWORD *)&v126 = L"PCRBitmap";
              *((_QWORD *)&v126 + 1) = L"ULONG";
              *(_QWORD *)&v127 = &v124;
              *((_QWORD *)&v127 + 1) = 4;
              *((_QWORD *)&v125 + 1) = &v129;
              *(_QWORD *)&v129 = &v125;
              LODWORD(v121) = DWORD1(v93);
              v176 = L"PCRBitmapSource";
              v177 = L"ULONG";
              v178 = &v121;
              v179 = 4;
              v175 = &v125;
              *(_QWORD *)&v125 = &v174;
              v52 = DWORD2(v93);
              LODWORD(v140) = DWORD2(v93);
              v170 = L"PCRValuesSize";
              v171 = L"ULONG";
              v172 = &v140;
              v173 = 4;
              v169 = &v174;
              v174 = (__int128 *)&v168;
              v163 = L"PCRValues";
              v164 = L"BYTE";
              v165 = lpMem[0];
              v166 = DWORD2(v93);
              v167 = 0;
              v162 = &v168;
              v168 = (__int128 **)&v161;
              v53 = (unsigned int)lpMem[1];
              LODWORD(v148) = lpMem[1];
              v136 = L"FilteredTcgLogSize";
              v137 = L"ULONG";
              v138 = &v148;
              v139 = 4;
              v135 = (__int128 *)&v161;
              v161 = (__int128 ***)&v134;
              v143 = L"FilteredTcgLog";
              v144 = L"BYTE";
              v145 = (int *)v95[0];
              v146 = LODWORD(lpMem[1]);
              v142 = (__int128 *)&v134;
              v134 = (__int64 *)&v141;
              LOWORD(v120) = 0;
              v156 = L"TpmSrkAesStrengthInBits";
              v157 = L"UINT16";
              v158 = &v120;
              v159 = 2;
              v154 = &v129;
              v155 = (__int128 *)&v141;
              v141 = (__int128 *)&v154;
              *((_QWORD *)&v129 + 1) = &v154;
              *((_QWORD *)&v128 + 1) = FVEAPI_OP_FAILED_SECUREBOOT_TCG_LOG_VALIDATION;
            }
            FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)&v96, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v128);
            FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v96);
            if ( (unsigned int)dword_18009A348 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18009A348, 0x400000000000LL) )
            {
              LODWORD(v121) = DWORD1(v93);
              LODWORD(v124) = v93;
              if ( v52 > v56 )
                LOWORD(v52) = v56;
              v148 = (struct _TRACE_EVENT_INFO *)lpMem[0];
              LOWORD(v149) = v52;
              LODWORD(v140) = DWORD2(v93);
              LOWORD(v120) = Id;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                v54,
                (unsigned int)&word_18008D1C6,
                v55,
                v56,
                (__int64)&v120,
                (__int64)&v140,
                (__int64)&v148,
                (__int64)&v121,
                (__int64)&v124);
            }
            LOWORD(v10) = 817;
            if ( (_WORD)Id != 817 )
              goto LABEL_13;
            if ( (unsigned int)dword_18009A348 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18009A348, 0x400000000000LL) )
            {
              v58 = v53;
              if ( v53 > v57 )
                v58 = v57;
              v121 = v95[0];
              LOWORD(v122) = v58;
              LODWORD(v124) = v53;
              LOWORD(v120) = v10;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperArray<1>>(
                v95[0],
                (unsigned int)&dword_18008D17C,
                v10,
                v57,
                (__int64)&v120,
                (__int64)&v124,
                (__int64)&v121);
              LOWORD(v10) = 817;
            }
            if ( !Instance )
              goto LABEL_13;
            goto LABEL_12;
          }
          goto LABEL_42;
        }
        v40 = (unsigned __int16)Id;
        if ( (unsigned __int16)(Id - 832) > 0xCu || (v41 = 5121, LOWORD(v40) = Id - 832, !_bittest(&v41, v40)) )
        {
          if ( (_WORD)Id == 773 )
          {
            if ( BdeSvcParseFveApiOperationalEvent(a1, v3, &v131, &v91, &v92) )
            {
              if ( !Instance )
                goto LABEL_13;
              LOWORD(v10) = 773;
              goto LABEL_12;
            }
            v96 = 0;
            v121 = 0;
            v122 = 0;
            v123 = 0;
            v136 = L"IdentityGuid";
            v137 = L"GUID";
            v138 = &v131;
            v139 = 16;
            v135 = (__int128 *)&v98;
            v98 = (__int128 *)&v134;
            v143 = L"ResealTime";
            v144 = L"SYSTEMTIME";
            v145 = (int *)&v181;
            v146 = 16;
            v141 = (__int128 *)&v98;
            v142 = (__int128 *)&v134;
            v134 = (__int64 *)&v141;
            v99 = (struct _TRACE_EVENT_INFO **)&v141;
            v97 = FVEAPI_OP_WINRE_PROTECTION_DISABLE;
            FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)&v121, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v96);
            FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v121);
            if ( (unsigned int)dword_18009A348 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18009A348, 0x400000000000LL) )
            {
              LOWORD(v120) = 773;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<2>>(
                v49,
                (unsigned int)byte_18008D0A1,
                v50,
                v51,
                (__int64)&v120);
            }
            if ( Instance )
              RecoveryTelemetery::AddRecoveryEvent(Instance, &v131, 0x305u, 0, 0, 0);
          }
          goto LABEL_42;
        }
        if ( !BdeSvcParseFveApiRecoveryEventSimpleError(a1, v3, (int *)&v132) )
        {
          switch ( (_WORD)Id )
          {
            case 0x340:
              v96 = 0;
              v121 = 0;
              v122 = 0;
              v123 = 0;
              LODWORD(v148) = v132;
              v136 = L"hr";
              v137 = L"HRESULT";
              v138 = &v148;
              v139 = 4;
              v134 = (__int64 *)&v98;
              v135 = (__int128 *)&v98;
              v98 = (__int128 *)&v134;
              v99 = (struct _TRACE_EVENT_INFO **)&v134;
              v97 = FVEAPI_OP_TCG_LOG_FILTER_FAILURE;
              FveEventLogHandle::LogFveApiEvent(
                (FveEventLogHandle *)&v121,
                (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v96);
              FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v121);
              break;
            case 0x34A:
              v96 = 0;
              v121 = 0;
              v122 = 0;
              v123 = 0;
              LODWORD(v148) = v132;
              v136 = L"hr";
              v137 = L"HRESULT";
              v138 = &v148;
              v139 = 4;
              v134 = (__int64 *)&v98;
              v135 = (__int128 *)&v98;
              v98 = (__int128 *)&v134;
              v99 = (struct _TRACE_EVENT_INFO **)&v134;
              v97 = FVEAPI_OP_WINRE_TPM_RESEAL_FAILED;
              FveEventLogHandle::LogFveApiEvent(
                (FveEventLogHandle *)&v121,
                (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v96);
              FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v121);
              break;
            case 0x34C:
              v96 = 0;
              v121 = 0;
              v122 = 0;
              v123 = 0;
              LODWORD(v148) = v132;
              v136 = L"hr";
              v137 = L"HRESULT";
              v138 = &v148;
              v139 = 4;
              v134 = (__int64 *)&v98;
              v135 = (__int128 *)&v98;
              v98 = (__int128 *)&v134;
              v99 = (struct _TRACE_EVENT_INFO **)&v134;
              v97 = FVEAPI_OP_WINRE_DEVICE_LOCK_RECOVERY_FAILED;
              FveEventLogHandle::LogFveApiEvent(
                (FveEventLogHandle *)&v121,
                (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v96);
              FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v121);
              break;
            default:
              MicrosoftTelemetryAssertTriggeredNoArgs();
              break;
          }
          if ( (unsigned int)dword_18009A348 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18009A348, 0x400000000000LL) )
          {
            LOWORD(v120) = Id;
            LODWORD(v148) = v132;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<2>>(
              v43,
              (unsigned int)&word_18008D12E,
              v44,
              v45,
              (__int64)&v148,
              (__int64)&v120);
          }
          if ( (unsigned int)dword_18009A310 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18009A310, 0x800000000000LL) )
          {
            LOWORD(v120) = Id;
            LODWORD(v148) = v132;
            v124 = (unsigned __int16 *)0x1000000;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>>(
              v46,
              (unsigned int)word_18008D0E2,
              v47,
              v48,
              (__int64)&v124,
              (__int64)&v148,
              (__int64)&v120);
          }
        }
        if ( !Instance )
          goto LABEL_13;
        v42 = v132;
        goto LABEL_132;
      }
      v59 = BdeSvcParseFveApiSecureBootEvent(a1, v3, (_WORD)Id == 812, &v140, (int *)&v132);
      v5 = v140;
      if ( !v59 )
      {
        switch ( (_WORD)Id )
        {
          case 0x32B:
            v112 = 0;
            v113 = 0;
            v96 = 0;
            v97 = 0;
            v98 = 0;
            v115 = &v114;
            v114 = (__int64)&v114;
            v125 = 0;
            v126 = 0;
            v127 = 0;
            FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)&v125, v60, L"VariableName", v140, v88);
            if ( (__int64 *)*v115 != &v114 )
              __fastfail(3u);
            *(_QWORD *)&v125 = &v114;
            *((_QWORD *)&v125 + 1) = v115;
            *v115 = (__int64)&v125;
            v115 = (__int64 *)&v125;
            v113 = FVEAPI_OP_SECUREBOOT_REQUIRED_EFI_VARIABLE_MISSING;
            FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)&v96, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v112);
            FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v96);
            break;
          case 0x32D:
            v116 = 0;
            v117 = 0;
            v96 = 0;
            v97 = 0;
            v98 = 0;
            v119 = &v118;
            v118 = (__int64)&v118;
            v125 = 0;
            v126 = 0;
            v127 = 0;
            FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)&v125, v60, L"VariableName", v140, v88);
            if ( (__int64 *)*v119 != &v118 )
              __fastfail(3u);
            *(_QWORD *)&v125 = &v118;
            *((_QWORD *)&v125 + 1) = v119;
            *v119 = (__int64)&v125;
            v119 = (__int64 *)&v125;
            v117 = FVEAPI_OP_SECUREBOOT_TCG_LOG_VARIABLE_INVALID;
            FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)&v96, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v116);
            FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v96);
            break;
          case 0x32C:
            v108 = 0;
            v109 = 0;
            v96 = 0;
            v97 = 0;
            v98 = 0;
            v111 = &v110;
            v110 = (__int64)&v110;
            v128 = 0;
            v129 = 0;
            v130 = 0;
            FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)&v128, v60, L"VariableName", v140, v88);
            if ( (__int64 *)*v111 != &v110 )
              goto LABEL_186;
            *(_QWORD *)&v128 = &v110;
            *((_QWORD *)&v128 + 1) = v111;
            *v111 = (__int64)&v128;
            LODWORD(v124) = v132;
            *(_QWORD *)&v126 = L"hr";
            *((_QWORD *)&v126 + 1) = L"HRESULT";
            *(_QWORD *)&v127 = &v124;
            *((_QWORD *)&v127 + 1) = 4;
            if ( (__int64 *)v128 != &v110 )
LABEL_186:
              __fastfail(3u);
            *(_QWORD *)&v125 = &v110;
            *((_QWORD *)&v125 + 1) = &v128;
            *(_QWORD *)&v128 = &v125;
            v111 = (__int64 *)&v125;
            v109 = FVEAPI_OP_SECUREBOOT_EFI_VARIABLE_ERROR;
            FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)&v96, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v108);
            FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v96);
            break;
          default:
            MicrosoftTelemetryAssertTriggeredNoArgs();
            break;
        }
        if ( (unsigned int)dword_18009A348 <= 4 || !(unsigned __int8)tlgKeywordOn(&dword_18009A348, 0x400000000000LL) )
          goto LABEL_13;
        v64 = byte_18008D235;
LABEL_191:
        LOWORD(v120) = Id;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<2>>(
          v61,
          (_DWORD)v64,
          v62,
          v63,
          (__int64)&v120);
        goto LABEL_13;
      }
    }
LABEL_42:
    v2 = 0;
    if ( v7 != -1 )
      FveCloseVolume(v7);
    if ( v89 )
    {
      v20 = FveTriggerPersistentRequestWNFEvent(1);
      v2 = v20;
      if ( v20 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          111,
          &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids,
          (unsigned int)v20);
    }
  }
LABEL_228:
  if ( Instance
    && (*((_BYTE *)Instance + 16) || *((_BYTE *)Instance + 17))
    && (unsigned int)dword_18009A348 > 4
    && (unsigned __int8)tlgKeywordOn(&dword_18009A348, 0x400000000000LL) )
  {
    v121 = (void *)0x1000000;
    LODWORD(v124) = v2;
    v89 = *((_BYTE *)Instance + 17);
    v90[0] = *((_BYTE *)Instance + 16);
    LOBYTE(v120) = *((_BYTE *)Instance + 18);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      v71,
      (unsigned int)byte_18008D021,
      v72,
      v73,
      (__int64)&v120,
      (__int64)v90,
      (__int64)&v89,
      (__int64)&v124,
      (__int64)&v121);
  }
  v74 = lpMem[0];
  if ( lpMem[0] )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v74);
  }
  v76 = v95[0];
  if ( v95[0] )
  {
    v77 = GetProcessHeap();
    HeapFree(v77, 0, v76);
  }
  if ( v5 )
  {
    v78 = GetProcessHeap();
    HeapFree(v78, 0, v5);
  }
  v79 = v91;
  if ( v91 )
  {
    v80 = GetProcessHeap();
    HeapFree(v80, 0, v79);
  }
  v81 = v92;
  if ( v92 )
  {
    v82 = GetProcessHeap();
    HeapFree(v82, 0, v81);
  }
  if ( v3 )
  {
    v83 = GetProcessHeap();
    HeapFree(v83, 0, v3);
  }
  if ( v4 )
  {
    v84 = GetProcessHeap();
    HeapFree(v84, 0, v4);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
}

```

## disassembly

```asm
0x18003e000  push    rbp
0x18003e002  push    rbx
0x18003e003  push    rsi
0x18003e004  push    rdi
0x18003e005  push    r12
0x18003e007  push    r13
0x18003e009  push    r14
0x18003e00b  push    r15
0x18003e00d  lea     rbp, [rsp-4D8h]
0x18003e015  sub     rsp, 5D8h
0x18003e01c  mov     rax, cs:__security_cookie
0x18003e023  xor     rax, rsp
0x18003e026  mov     [rbp+510h+var_50], rax
0x18003e02d  mov     rsi, rcx
0x18003e030  lea     rax, WPP_GLOBAL_Control
0x18003e037  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e03e  cmp     rcx, rax
0x18003e041  jz      short loc_18003E05E
0x18003e043  test    byte ptr [rcx+1Ch], 20h
0x18003e047  jz      short loc_18003E05E
0x18003e049  mov     edx, 67h ; 'g'
0x18003e04e  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18003e055  mov     rcx, [rcx+10h]
0x18003e059  call    WPP_SF_
0x18003e05e  xor     ebx, ebx
0x18003e060  mov     r14d, ebx
0x18003e063  mov     [rbp+510h+var_3A8], rbx
0x18003e06a  xorps   xmm0, xmm0
0x18003e06d  movups  xmmword ptr [rbp+510h+var_430.Data1], xmm0
0x18003e074  mov     [rsp+610h+var_5B8], rbx
0x18003e079  mov     [rsp+610h+var_5B0], rbx
0x18003e07e  movups  xmmword ptr [rbp+510h+var_2B0], xmm0
0x18003e085  mov     [rbp+510h+var_3B0], ebx
0x18003e08b  xorps   xmm1, xmm1
0x18003e08e  movups  xmmword ptr [rbp+510h+var_2A0.wYear], xmm1
0x18003e095  mov     r15d, ebx
0x18003e098  mov     [rbp+510h+var_498], rbx
0x18003e09c  mov     [rbp+510h+var_41C], ebx
0x18003e0a2  movups  [rsp+610h+var_5A8], xmm0
0x18003e0a7  movups  xmmword ptr [rsp+610h+lpMem], xmm0
0x18003e0ac  movups  xmmword ptr [rbp+510h+var_588], xmm0
0x18003e0b0  mov     r13d, ebx
0x18003e0b3  mov     [rbp+510h+var_3E8], rbx
0x18003e0ba  mov     [rbp+510h+var_420], ebx
0x18003e0c0  call    ?getInstance@RecoveryTelemetery@@SAPEAV1@XZ; RecoveryTelemetery::getInstance(void)
0x18003e0c5  mov     rdi, rax
0x18003e0c8  xorps   xmm0, xmm0
0x18003e0cb  xor     eax, eax
0x18003e0cd  movups  [rbp+510h+var_290], xmm0
0x18003e0d4  movups  [rbp+510h+var_280], xmm0
0x18003e0db  mov     [rbp+510h+var_270], eax
0x18003e0e1  or      r12, 0FFFFFFFFFFFFFFFFh
0x18003e0e5  mov     [rbp+510h+var_4B0], r12
0x18003e0e9  mov     [rbp+510h+var_348], 104h
0x18003e0f3  xor     edx, edx; Val
0x18003e0f5  mov     r8d, 208h; Size
0x18003e0fb  lea     rcx, [rbp+510h+var_260]; void *
0x18003e102  call    memset_0
0x18003e107  mov     rax, [rsi+18h]
0x18003e10b  cmp     rax, qword ptr cs:FVEAPI_Provider.Data1
0x18003e112  jnz     loc_180040B20
0x18003e118  mov     rax, [rsi+20h]
0x18003e11c  cmp     rax, qword ptr cs:FVEAPI_Provider.Data4
0x18003e123  jnz     loc_180040B20
0x18003e129  mov     [rsp+610h+var_5C0], bl
0x18003e12d  lea     rdx, [rbp+510h+var_3A8]; struct _TRACE_EVENT_INFO **
0x18003e134  mov     rcx, rsi; Event
0x18003e137  call    ?BdeSvcGetEventInformation@@YAKPEAU_EVENT_RECORD@@PEAPEAU_TRACE_EVENT_INFO@@@Z; BdeSvcGetEventInformation(_EVENT_RECORD *,_TRACE_EVENT_INFO * *)
0x18003e13c  mov     r14, [rbp+510h+var_3A8]
0x18003e143  test    eax, eax
0x18003e145  jnz     loc_18003E659
0x18003e14b  lea     rdx, [rbp+510h+var_2A0]; struct _SYSTEMTIME *
0x18003e152  mov     rcx, rsi; struct _EVENT_HEADER *
0x18003e155  call    ?BdeSvcpGetEventLocalSystemTime@@YAKPEAU_EVENT_HEADER@@PEAU_SYSTEMTIME@@@Z; BdeSvcpGetEventLocalSystemTime(_EVENT_HEADER *,_SYSTEMTIME *)
0x18003e15a  test    eax, eax
0x18003e15c  jnz     loc_18003E659
0x18003e162  movzx   ebx, word ptr [r14+20h]
0x18003e167  mov     eax, 319h
0x18003e16c  cmp     bx, ax
0x18003e16f  jnz     loc_18003E320
0x18003e175  lea     rax, [rsp+610h+var_5B0]
0x18003e17a  mov     [rsp+610h+var_5F0], rax; unsigned __int16 **
0x18003e17f  lea     r9, [rsp+610h+var_5B8]; unsigned __int16 **
0x18003e184  lea     r8, [rbp+510h+var_430]; struct _GUID *
0x18003e18b  mov     rdx, r14; struct _TRACE_EVENT_INFO *
0x18003e18e  mov     rcx, rsi; pEvent
0x18003e191  call    ?BdeSvcParseFveApiOperationalEvent@@YAKPEAU_EVENT_RECORD@@PEAU_TRACE_EVENT_INFO@@PEAU_GUID@@PEAPEAG3@Z; BdeSvcParseFveApiOperationalEvent(_EVENT_RECORD *,_TRACE_EVENT_INFO *,_GUID *,ushort * *,ushort * *)
0x18003e196  xor     esi, esi
0x18003e198  test    eax, eax
0x18003e19a  jz      short loc_18003E1C8
0x18003e19c  test    rdi, rdi
0x18003e19f  jz      short loc_18003E1C1
0x18003e1a1  mov     r8d, 319h; unsigned __int16
0x18003e1a7  mov     dword ptr [rsp+610h+pBuffer], esi; unsigned int
0x18003e1ab  mov     dword ptr [rsp+610h+var_5F0], esi; unsigned int
0x18003e1af  xor     r9d, r9d; unsigned int
0x18003e1b2  lea     rdx, [rbp+510h+var_430]; struct _GUID *
0x18003e1b9  mov     rcx, rdi; this
0x18003e1bc  call    ?AddRecoveryEvent@RecoveryTelemetery@@QEAAXAEBU_GUID@@GKKK@Z; RecoveryTelemetery::AddRecoveryEvent(_GUID const &,ushort,ulong,ulong,ulong)
0x18003e1c1  mov     ebx, esi
0x18003e1c3  jmp     loc_180040B22
0x18003e1c8  mov     [rbp+510h+var_578], rsi
0x18003e1cc  mov     [rbp+510h+var_4B0], rsi
0x18003e1d0  mov     [rbp+510h+var_4A8], rsi
0x18003e1d4  mov     [rbp+510h+var_4A0], rsi
0x18003e1d8  lea     rax, aIdentityguid; "IdentityGuid"
0x18003e1df  lea     rsi, aGuid; "GUID"
0x18003e1e6  lea     rdx, [rbp+510h+var_430]
0x18003e1ed  mov     qword ptr [rbp+510h+var_450], rax
0x18003e1f4  mov     qword ptr [rbp+510h+var_450+8], rsi
0x18003e1fb  mov     qword ptr [rbp+510h+var_440], rdx
0x18003e202  mov     qword ptr [rbp+510h+var_440+8], 10h
0x18003e20d  lea     rax, [rbp+510h+var_568]
0x18003e211  mov     qword ptr [rbp+510h+var_460+8], rax
0x18003e218  lea     rax, [rbp+510h+var_460]
0x18003e21f  mov     [rbp+510h+var_568], rax
0x18003e223  lea     rcx, aResealtime; "ResealTime"
0x18003e22a  lea     rax, aSystemtime; "SYSTEMTIME"
0x18003e231  lea     rdx, [rbp+510h+var_2A0]
0x18003e238  mov     [rbp+510h+var_398], rcx
0x18003e23f  mov     [rbp+510h+var_390], rax
0x18003e246  mov     [rbp+510h+var_388], rdx
0x18003e24d  mov     [rbp+510h+var_380], 10h
0x18003e258  lea     rax, [rbp+510h+var_568]
0x18003e25c  mov     [rbp+510h+var_3A8], rax
0x18003e263  lea     rax, [rbp+510h+var_460]
0x18003e26a  mov     [rbp+510h+var_3A0], rax
0x18003e271  lea     rax, [rbp+510h+var_3A8]
0x18003e278  mov     qword ptr [rbp+510h+var_460], rax
0x18003e27f  lea     rax, [rbp+510h+var_3A8]
0x18003e286  mov     [rbp+510h+var_560], rax
0x18003e28a  lea     rax, FVEAPI_OP_BOOT_SETTINGS_RESEAL_TPM_WINRE
0x18003e291  mov     [rbp+510h+var_570], rax
0x18003e295  lea     rdx, [rbp+510h+var_578]; struct _FVEAPI_EVENT_DATA_COLLECTION *
0x18003e299  lea     rcx, [rbp+510h+var_4B0]; this
0x18003e29d  call    ?LogFveApiEvent@FveEventLogHandle@@QEAAJPEAU_FVEAPI_EVENT_DATA_COLLECTION@@@Z; FveEventLogHandle::LogFveApiEvent(_FVEAPI_EVENT_DATA_COLLECTION *)
0x18003e2a2  nop
0x18003e2a3  lea     rcx, [rbp+510h+var_4B0]; this
0x18003e2a7  call    ?EventLogCleanup@FveEventLogHandle@@AEAAXXZ; FveEventLogHandle::EventLogCleanup(void)
0x18003e2ac  nop
0x18003e2ad  mov     eax, cs:dword_18009A348
0x18003e2b3  cmp     eax, 4
0x18003e2b6  jbe     short loc_18003E308
0x18003e2b8  mov     rdx, 400000000000h
0x18003e2c2  lea     rcx, dword_18009A348
0x18003e2c9  call    _tlgKeywordOn
0x18003e2ce  xor     esi, esi
0x18003e2d0  test    al, al
0x18003e2d2  jz      short loc_18003E30A
0x18003e2d4  mov     ebx, 319h
0x18003e2d9  mov     word ptr [rbp+510h+var_4B8], bx
0x18003e2dd  lea     rax, [rbp+510h+var_430]
0x18003e2e4  mov     [rbp+510h+var_498], rax
0x18003e2e8  lea     rax, [rbp+510h+var_4B8]
0x18003e2ec  mov     [rsp+610h+pBuffer], rax
0x18003e2f1  lea     rax, [rbp+510h+var_498]
0x18003e2f5  mov     [rsp+610h+var_5F0], rax
0x18003e2fa  lea     rdx, word_18008D4E2
0x18003e301  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$01@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$01@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<2>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<2> const &)
0x18003e306  jmp     short loc_18003E30F
0x18003e308  xor     esi, esi
0x18003e30a  mov     ebx, 319h
0x18003e30f  test    rdi, rdi
0x18003e312  jz      loc_18003E1C1
0x18003e318  mov     r8d, ebx
0x18003e31b  jmp     loc_18003E1A7
0x18003e320  mov     eax, 30Eh
0x18003e325  cmp     bx, ax
0x18003e328  jnz     loc_18003E9F0
0x18003e32e  lea     rax, [rbp+510h+var_3B0]
0x18003e335  mov     [rsp+610h+var_5E0], rax; int *
0x18003e33a  lea     rax, [rbp+510h+var_2B0]
0x18003e341  mov     [rsp+610h+pBuffer], rax; pBuffer
0x18003e346  lea     rax, [rsp+610h+var_5B0]
0x18003e34b  mov     [rsp+610h+var_5F0], rax; unsigned __int16 **
0x18003e350  lea     r9, [rsp+610h+var_5B8]; unsigned __int16 **
0x18003e355  lea     r8, [rbp+510h+var_430]; struct _GUID *
0x18003e35c  mov     rdx, r14; struct _TRACE_EVENT_INFO *
0x18003e35f  mov     rcx, rsi; pEvent
0x18003e362  call    ?BdeSvcParseFveApiOperationalEventWithProtectorAndType@@YAKPEAU_EVENT_RECORD@@PEAU_TRACE_EVENT_INFO@@PEAU_GUID@@PEAPEAG32PEAH@Z; BdeSvcParseFveApiOperationalEventWithProtectorAndType(_EVENT_RECORD *,_TRACE_EVENT_INFO *,_GUID *,ushort * *,ushort * *,_GUID *,int *)
0x18003e367  xor     esi, esi
0x18003e369  test    eax, eax
0x18003e36b  jnz     loc_18003E65B
0x18003e371  mov     [rbp+510h+var_578], rsi
0x18003e375  mov     [rbp+510h+var_3A8], rsi
0x18003e37c  mov     [rbp+510h+var_3A0], rsi
0x18003e383  mov     [rbp+510h+var_398], rsi
0x18003e38a  lea     rax, aIdentityguid; "IdentityGuid"
0x18003e391  lea     rsi, aGuid; "GUID"
0x18003e398  lea     rdx, [rbp+510h+var_430]
0x18003e39f  mov     qword ptr [rbp+510h+var_450], rax
0x18003e3a6  mov     qword ptr [rbp+510h+var_450+8], rsi
0x18003e3ad  mov     qword ptr [rbp+510h+var_440], rdx
0x18003e3b4  mov     qword ptr [rbp+510h+var_440+8], 10h
0x18003e3bf  lea     rax, [rbp+510h+var_568]
0x18003e3c3  mov     qword ptr [rbp+510h+var_460+8], rax
0x18003e3ca  lea     rax, [rbp+510h+var_460]
0x18003e3d1  mov     [rbp+510h+var_568], rax
0x18003e3d5  lea     rax, aProtectorguid_0; "ProtectorGuid"
0x18003e3dc  lea     rcx, [rbp+510h+var_2B0]
0x18003e3e3  mov     [rbp+510h+var_368], rax
0x18003e3ea  mov     [rbp+510h+var_360], rsi
0x18003e3f1  mov     [rbp+510h+var_358], rcx
0x18003e3f8  mov     [rbp+510h+var_350], 10h
0x18003e403  lea     rax, [rbp+510h+var_460]
0x18003e40a  mov     [rbp+510h+var_370], rax
0x18003e411  lea     rax, [rbp+510h+var_378]
0x18003e418  mov     qword ptr [rbp+510h+var_460], rax
0x18003e41f  mov     eax, [rbp+510h+var_3B0]
0x18003e425  mov     [rbp+510h+var_4B8], eax
0x18003e428  lea     r8, aProtectortype; "ProtectorType"
0x18003e42f  lea     rax, aInt32; "INT32"
0x18003e436  lea     rcx, [rbp+510h+var_4B8]
0x18003e43a  mov     [rbp+510h+var_3D0], r8
0x18003e441  mov     [rbp+510h+var_3C8], rax
0x18003e448  mov     [rbp+510h+var_3C0], rcx
0x18003e44f  mov     [rbp+510h+var_3B8], 4
0x18003e45a  lea     rax, [rbp+510h+var_378]
0x18003e461  mov     [rbp+510h+var_3D8], rax
0x18003e468  lea     rax, [rbp+510h+var_3E0]
0x18003e46f  mov     [rbp+510h+var_378], rax
0x18003e476  lea     r8, aUnlocktime; "UnlockTime"
0x18003e47d  lea     rax, aSystemtime; "SYSTEMTIME"
0x18003e484  lea     rcx, [rbp+510h+var_2A0]
0x18003e48b  mov     [rbp+510h+var_408], r8
0x18003e492  mov     [rbp+510h+var_400], rax
0x18003e499  mov     [rbp+510h+var_3F8], rcx
0x18003e4a0  mov     [rbp+510h+var_3F0], 10h
0x18003e4ab  lea     rax, [rbp+510h+var_568]
0x18003e4af  mov     [rbp+510h+var_418], rax
0x18003e4b6  lea     rax, [rbp+510h+var_3E0]
0x18003e4bd  mov     [rbp+510h+var_410], rax
0x18003e4c4  lea     rax, [rbp+510h+var_418]
0x18003e4cb  mov     [rbp+510h+var_3E0], rax
0x18003e4d2  lea     rax, [rbp+510h+var_418]
0x18003e4d9  mov     [rbp+510h+var_560], rax
0x18003e4dd  lea     rax, FVEAPI_OP_VOLUME_UNLOCK_WINRE
0x18003e4e4  mov     [rbp+510h+var_570], rax
0x18003e4e8  lea     rdx, [rbp+510h+var_578]; struct _FVEAPI_EVENT_DATA_COLLECTION *
0x18003e4ec  lea     rcx, [rbp+510h+var_3A8]; this
0x18003e4f3  call    ?LogFveApiEvent@FveEventLogHandle@@QEAAJPEAU_FVEAPI_EVENT_DATA_COLLECTION@@@Z; FveEventLogHandle::LogFveApiEvent(_FVEAPI_EVENT_DATA_COLLECTION *)
0x18003e4f8  nop
0x18003e4f9  lea     rcx, [rbp+510h+var_3A8]; this
0x18003e500  call    ?EventLogCleanup@FveEventLogHandle@@AEAAXXZ; FveEventLogHandle::EventLogCleanup(void)
0x18003e505  nop
0x18003e506  mov     eax, cs:dword_18009A348
0x18003e50c  cmp     eax, 4
0x18003e50f  jbe     short loc_18003E55F
0x18003e511  mov     rdx, 400000000000h
0x18003e51b  lea     rcx, dword_18009A348
0x18003e522  call    _tlgKeywordOn
0x18003e527  test    al, al
0x18003e529  jz      short loc_18003E55F
0x18003e52b  mov     ebx, 30Eh
0x18003e530  mov     word ptr [rbp+510h+var_4B8], bx
0x18003e534  lea     rax, [rbp+510h+var_430]
0x18003e53b  mov     [rbp+510h+var_498], rax
0x18003e53f  lea     rax, [rbp+510h+var_4B8]
0x18003e543  mov     [rsp+610h+pBuffer], rax
0x18003e548  lea     rax, [rbp+510h+var_498]
0x18003e54c  mov     [rsp+610h+var_5F0], rax
0x18003e551  lea     rdx, byte_18008D4A7
0x18003e558  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$01@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$01@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<2>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<2> const &)
0x18003e55d  jmp     short loc_18003E564
0x18003e55f  mov     ebx, 30Eh
0x18003e564  test    rdi, rdi
0x18003e567  jz      short loc_18003E58E
0x18003e569  mov     r8d, ebx; unsigned __int16
0x18003e56c  mov     dword ptr [rsp+610h+pBuffer], 0; unsigned int
0x18003e574  mov     dword ptr [rsp+610h+var_5F0], 0; int
0x18003e57c  xor     r9d, r9d; unsigned int
0x18003e57f  lea     rdx, [rbp+510h+var_430]; struct _GUID *
0x18003e586  mov     rcx, rdi; this
0x18003e589  call    ?AddRecoveryEvent@RecoveryTelemetery@@QEAAXAEBU_GUID@@GKKK@Z; RecoveryTelemetery::AddRecoveryEvent(_GUID const &,ushort,ulong,ulong,ulong)
0x18003e58e  cmp     [rbp+510h+var_3B0], 3
0x18003e595  jnz     loc_18003E659
0x18003e59b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e5a2  lea     rax, WPP_GLOBAL_Control
0x18003e5a9  cmp     rcx, rax
0x18003e5ac  jz      short loc_18003E5C9
0x18003e5ae  test    byte ptr [rcx+1Ch], 8
0x18003e5b2  jz      short loc_18003E5C9
0x18003e5b4  mov     edx, 68h ; 'h'
0x18003e5b9  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18003e5c0  mov     rcx, [rcx+10h]
0x18003e5c4  call    WPP_SF_
0x18003e5c9  call    ?CheckDeviceForClientKeyRotation@@YAJXZ; CheckDeviceForClientKeyRotation(void)
0x18003e5ce  mov     ebx, eax
0x18003e5d0  test    eax, eax
0x18003e5d2  js      loc_18003E983
0x18003e5d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e5df  lea     rbx, WPP_GLOBAL_Control
0x18003e5e6  cmp     rcx, rbx
0x18003e5e9  jz      short loc_18003E606
0x18003e5eb  test    byte ptr [rcx+1Ch], 8
0x18003e5ef  jz      short loc_18003E606
0x18003e5f1  mov     edx, 69h ; 'i'
0x18003e5f6  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18003e5fd  mov     rcx, [rcx+10h]
0x18003e601  call    WPP_SF_
  ... truncated ...
```
