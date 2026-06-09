# CWwanUicc::OnNdisNotification(WWAN_EVENT const *)

- ea: `0x180068eac`
- end: `0x18006a6fa`
- name: `?OnNdisNotification@CWwanUicc@@IEAAXPEBUWWAN_EVENT@@@Z`
- size: `6222`
- prototype: `void __fastcall(CWwanUicc *__hidden this, const struct WWAN_EVENT *)`
- caller_count: `2`
- callee_count: `62`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180061830`
- `0x180065290`

## callees

- `0x18000153c`
- `0x1800052d8`
- `0x1800085d0`
- `0x180008a7c`
- `0x1800094d0`
- `0x1800094f4`
- `0x18001077c`
- `0x1800111ac`
- `0x18001150c`
- `0x180011a1c`
- `0x180012300`
- `0x180013288`
- `0x180013588`
- `0x180014b5c`
- `0x180014c68`
- `0x180014f1c`
- `0x180018abc`
- `0x180019f48`
- `0x18001e9b4`
- `0x18001e9f0`
- `0x180020540`
- `0x180020bd4`
- `0x180020e2c`
- `0x180064698`
- `0x180066f30`
- `0x180067078`
- `0x180067124`
- `0x1800671d0`
- `0x180067348`
- `0x1800673d0`
- `0x1800674d8`
- `0x18006768c`
- `0x18006778c`
- `0x180068178`
- `0x180068eac`
- `0x18006b6e0`
- `0x18006cd68`
- `0x18006cf10`
- `0x18006d3d0`
- `0x18006d468`
- `0x18006d4c0`
- `0x18006dfa8`
- `0x18006e198`
- `0x18006e224`
- `0x18006ec84`
- `0x18006edbc`
- `0x18006f198`
- `0x18006f36c`
- `0x18006f808`
- `0x18006f918`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180069dfa`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180069fc4`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180069dfa`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180069fc4`

## string_xrefs

- `0x1800692d1`: `Error in Ready info received`
- `0x18006a078`: `SupportedDataClassBitMap`
- `0x18006a096`: `SupportedDataClassBitMap`
- `0x18006927e`: ` HomeProvider ID [%s] state %d Name [%s] dataCleass 0x%x`
- `0x180068fb5`: `Error in open channel response`
- `0x180069b81`: `Failed to send query WwanEventCodeReadyInfo for Inactive slot %d, Error = 0x%x`
- `0x18006943c`: `WwanEventCodeUiccSlotInfo (isRsp %d) with bad slot index %d outside [0, %d]`
- `0x18006955d`: `Send card removed toast notification, slotIndex:%d, physical slot previous state:%d, new state:%d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CWwanUicc::OnNdisNotification(CWwanUicc *this, const struct WWAN_EVENT *a2)
{
  int v4; // ecx
  __int64 v5; // rax
  const unsigned __int16 *v6; // r8
  __int64 v7; // rax
  char *v8; // rcx
  __int64 v9; // rcx
  bool v10; // r14
  __int64 v11; // r9
  void *v12; // r8
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  unsigned __int8 v18; // r13
  unsigned int v19; // eax
  int v20; // r12d
  unsigned int *v21; // r15
  unsigned int v22; // edx
  unsigned int v23; // ecx
  CWwanUicc *v24; // rcx
  unsigned int v25; // r12d
  unsigned int v26; // ebx
  unsigned int v27; // eax
  int v28; // r8d
  int v29; // r8d
  CWwanManager *v30; // rcx
  int v31; // r9d
  char v32; // dl
  char v33; // al
  CWwanManager *v34; // rcx
  CWwanUicc *v35; // rcx
  unsigned int v36; // eax
  __int64 v37; // rcx
  CWwanManager *v38; // rcx
  unsigned int v39; // eax
  unsigned __int8 v40; // dl
  unsigned int v41; // ebx
  __int64 v42; // rcx
  int v43; // r14d
  unsigned int v44; // r11d
  __int64 v45; // rdx
  unsigned int v46; // edi
  _DWORD *v47; // r8
  int v48; // r10d
  _DWORD *v49; // r13
  int *v50; // r15
  unsigned int v51; // ecx
  _DWORD *v52; // r12
  int v53; // r8d
  const wchar_t *v54; // r9
  __int64 v55; // rbx
  __int64 v56; // rdx
  __int64 v57; // rax
  void *v58; // rcx
  int v59; // ebx
  int v60; // ebx
  __int64 v61; // rbx
  _QWORD *v62; // rax
  unsigned int v63; // ebx
  __int64 v64; // rax
  struct CWwanManager *Instance; // rax
  __int64 v66; // rbx
  struct CWwanManager *v67; // rax
  _QWORD *ExecutorFromInterfaceGuid; // rax
  __int64 v69; // rax
  __int64 *v70; // rbx
  unsigned int v71; // edx
  __int64 v72; // rdx
  __int64 v73; // rdx
  int v74; // r12d
  unsigned int DWORD; // eax
  unsigned int v76; // eax
  __int64 v77; // r9
  unsigned int v78; // ecx
  signed __int64 v79; // r13
  struct _GUID *v80; // rbx
  unsigned int v81; // eax
  unsigned int v82; // eax
  unsigned int v83; // eax
  unsigned int v84; // eax
  int String; // eax
  int v86; // eax
  int v87; // eax
  int v88; // eax
  const unsigned __int16 *v89; // r15
  int v90; // eax
  const unsigned __int16 *v91; // r15
  int v92; // eax
  const unsigned __int16 *v93; // r15
  int v94; // eax
  __int64 v95; // r8
  int v96; // ecx
  int v97; // r8d
  int v98; // r9d
  unsigned int *v99; // [rsp+20h] [rbp-100h]
  int v100; // [rsp+20h] [rbp-100h]
  unsigned int *v101; // [rsp+20h] [rbp-100h]
  __int64 v102; // [rsp+28h] [rbp-F8h]
  __int64 v103; // [rsp+28h] [rbp-F8h]
  unsigned int v104; // [rsp+28h] [rbp-F8h]
  unsigned int v105; // [rsp+A0h] [rbp-80h] BYREF
  unsigned int v106; // [rsp+A4h] [rbp-7Ch] BYREF
  char v107; // [rsp+A8h] [rbp-78h]
  unsigned int v108; // [rsp+ACh] [rbp-74h] BYREF
  unsigned int EmbeddedSlotIndex; // [rsp+B0h] [rbp-70h] BYREF
  bool v110; // [rsp+B4h] [rbp-6Ch]
  unsigned int v111; // [rsp+B8h] [rbp-68h] BYREF
  signed __int64 v112; // [rsp+C0h] [rbp-60h] BYREF
  std::_Ref_count_base *v113; // [rsp+C8h] [rbp-58h]
  int v114; // [rsp+D0h] [rbp-50h] BYREF
  unsigned int v115; // [rsp+D8h] [rbp-48h] BYREF
  struct _GUID *v116; // [rsp+E0h] [rbp-40h] BYREF
  _QWORD v117[2]; // [rsp+E8h] [rbp-38h] BYREF
  StateSeparation *v118; // [rsp+F8h] [rbp-28h] BYREF
  __int64 v119; // [rsp+100h] [rbp-20h] BYREF
  __int64 v120; // [rsp+108h] [rbp-18h] BYREF
  __int64 v121; // [rsp+110h] [rbp-10h] BYREF
  __int64 v122; // [rsp+118h] [rbp-8h] BYREF
  __int64 v123; // [rsp+120h] [rbp+0h] BYREF
  __int64 v124; // [rsp+128h] [rbp+8h] BYREF
  __int64 v125; // [rsp+130h] [rbp+10h] BYREF
  __int64 v126; // [rsp+138h] [rbp+18h] BYREF
  __int64 v127; // [rsp+140h] [rbp+20h] BYREF
  __int64 v128; // [rsp+148h] [rbp+28h] BYREF
  __int64 v129; // [rsp+150h] [rbp+30h] BYREF
  __int64 v130; // [rsp+158h] [rbp+38h] BYREF
  __int128 v131; // [rsp+160h] [rbp+40h] BYREF
  __int64 v132; // [rsp+170h] [rbp+50h]
  __int64 v133; // [rsp+178h] [rbp+58h]
  __int128 v134; // [rsp+180h] [rbp+60h] BYREF
  __int64 v135; // [rsp+190h] [rbp+70h]
  __int64 v136; // [rsp+198h] [rbp+78h]
  __int128 v137; // [rsp+1A0h] [rbp+80h] BYREF
  __int64 v138; // [rsp+1B0h] [rbp+90h]
  __int64 v139; // [rsp+1B8h] [rbp+98h]
  __int128 v140; // [rsp+1C0h] [rbp+A0h] BYREF
  __int64 v141; // [rsp+1D0h] [rbp+B0h]
  __int64 v142; // [rsp+1D8h] [rbp+B8h]
  __int128 v143; // [rsp+1E0h] [rbp+C0h] BYREF
  __int64 v144; // [rsp+1F0h] [rbp+D0h]
  __int64 v145; // [rsp+1F8h] [rbp+D8h]
  __int128 v146; // [rsp+200h] [rbp+E0h] BYREF
  __int64 v147; // [rsp+210h] [rbp+F0h]
  __int64 v148; // [rsp+218h] [rbp+F8h]
  __int128 v149; // [rsp+220h] [rbp+100h] BYREF
  __int64 v150; // [rsp+230h] [rbp+110h]
  __int64 v151; // [rsp+238h] [rbp+118h]
  unsigned __int16 Destination; // [rsp+240h] [rbp+120h] BYREF
  char v153[12]; // [rsp+242h] [rbp+122h] BYREF
  __int16 v154; // [rsp+24Eh] [rbp+12Eh]
  int v155; // [rsp+284h] [rbp+164h]
  OLECHAR sz[48]; // [rsp+2A0h] [rbp+180h] BYREF

  v4 = *((_DWORD *)a2 + 1);
  if ( v4 > 48 )
  {
    v13 = v4 - 49;
    if ( !v13 )
    {
      if ( *((_DWORD *)a2 + 4) == 1 )
        CWwanUicc::onTerminalCapability(this, a2);
      else
        WwanLog::Info("CWwanUicc::OnNdisNotification", 0, L"Response to set terminal capability is ignored");
      return;
    }
    v14 = v13 - 10;
    if ( v14 )
    {
      v15 = v14 - 1;
      if ( v15 )
      {
        v16 = v15 - 3;
        if ( v16 )
        {
          v17 = v16 - 7;
          if ( v17 )
          {
            if ( (unsigned int)(v17 - 2) <= 1 )
              CWwanUicc::onUiccAccessResponse(this, a2);
          }
          else
          {
            CWwanUicc::onUiccAppList(this, a2);
          }
        }
        else
        {
          CWwanUicc::onResetUicc(this, a2);
        }
        return;
      }
      if ( *(_DWORD *)a2 == 1 )
      {
        v18 = 1;
        if ( !*((_DWORD *)a2 + 4) )
        {
          WwanLog::Error("CWwanUicc::OnNdisNotification", 0, L"WwanEventCodeUiccSlotInfo set response is received");
          return;
        }
      }
      else
      {
        v18 = 0;
      }
      v19 = 0;
      v108 = 0;
      if ( v18 )
      {
        if ( !CWwanUicc::fMatchSlotInfoResponse(this, *((void **)a2 + 3), &v108) )
        {
          WwanLog::Error(
            "CWwanUicc::OnNdisNotification",
            0,
            L"WwanEventCodeUiccSlotInfo unknown query response (received reqHandle 0x%p)",
            *((_QWORD *)a2 + 3));
          return;
        }
        v19 = v108;
      }
      v20 = *((_DWORD *)a2 + 8);
      if ( v20 )
      {
        WwanLog::Error(
          "CWwanUicc::OnNdisNotification",
          0,
          L"WwanEventCodeUiccSlotInfo (isRsp %d) failure 0x%x",
          v18,
          *((_DWORD *)a2 + 8));
        goto LABEL_141;
      }
      v21 = (unsigned int *)((char *)a2 + 92);
      v20 = -1073739509;
      if ( a2 == (const struct WWAN_EVENT *)-92LL || *((_DWORD *)a2 + 22) < 8u )
      {
        WwanLog::Error(
          "CWwanUicc::OnNdisNotification",
          0,
          L"WwanEventCodeUiccSlotInfo (isRsp %d) with bad data (size %d pData 0x%p)",
          v18,
          *((_DWORD *)a2 + 22),
          (char *)a2 + 92);
LABEL_141:
        if ( v18 )
          goto LABEL_142;
LABEL_144:
        CWwanUicc::fsmEventHandler(this, 2 * (v18 ^ 1u));
        return;
      }
      v22 = *((_DWORD *)this + 197);
      v23 = *v21;
      if ( *v21 >= v22 )
      {
        WwanLog::Error(
          "CWwanUicc::OnNdisNotification",
          0,
          L"WwanEventCodeUiccSlotInfo (isRsp %d) with bad slot index %d outside [0, %d]",
          v18,
          *v21,
          v22 - 1);
        goto LABEL_141;
      }
      if ( v18 && v23 != v19 )
      {
        WwanLog::Error(
          "CWwanUicc::OnNdisNotification",
          0,
          L"WwanEventCodeUiccSlotInfo query response with bad slot index %d matchedSlotIdx %d",
          v23,
          v19);
LABEL_142:
        v41 = v108;
        goto LABEL_143;
      }
      if ( CWwanUicc::isDSSASupported(this) )
      {
        EmbeddedSlotIndex = CWwanUicc::getEmbeddedSlotIndex(v24);
        v25 = (EmbeddedSlotIndex - 1) & 1;
        v106 = v25;
        v111 = v25;
        if ( *v21 == v25 )
        {
          v26 = *((_DWORD *)this + 6 * v25 + 234);
          if ( v26 )
          {
            v27 = v21[1];
            v105 = v27;
            if ( v27 != v26 )
            {
              v110 = ((v27 - 1) & 0xFFFFFFFD) == 0;
              if ( ((v26 - 1) & 0xFFFFFFFC) != 0 || (v107 = 1, v26 == 2) )
                v107 = 0;
              memset_0(&Destination, 0, 0x4Au);
              v116 = (struct _GUID *)((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 8);
              if ( memcmp_0(&GUID_NULL, v116, 0x10u) )
                GuidToString(v116, &Destination, v28);
              v29 = *((_DWORD *)this + 203);
              if ( v29 == v25 && v110 && !v107 )
              {
                WwanLog::Info(
                  "CWwanUicc::OnNdisNotification",
                  0,
                  L"Send card removed toast notification, slotIndex:%d, physical slot previous state:%d, new state:%d",
                  *v21,
                  v26,
                  v105);
                CWwanManager::GetInstance();
                CWwanManager::RemoveToastNotification(v30, &Destination);
                CWwanManager::GetInstance();
                v31 = 1;
LABEL_126:
                v37 = *(int *)(*((_QWORD *)this + 1) + 4LL);
                CWwanManager::SendToastNotification(
                  v37,
                  (const struct _GUID *)((char *)this + v37 + 8),
                  (const unsigned __int16 *)((char *)this + v37 + 80),
                  v31);
                goto LABEL_131;
              }
              if ( ((v105 - 5) & 0xFFFFFFFC) != 0 || (v32 = 1, v105 == 6) )
                v32 = 0;
              if ( v26 == 6 || v26 <= 3 || (v33 = 1, v26 >= 9) )
                v33 = 0;
              if ( v29 == EmbeddedSlotIndex && v32 && !v33 )
              {
                LODWORD(v99) = v26;
                WwanLog::Info(
                  "CWwanUicc::OnNdisNotification",
                  0,
                  L"Send card inserted toast notification, slotIndex:%d, physical slot previous state:%d, new state:%d",
                  *v21);
                CWwanManager::GetInstance();
                CWwanManager::RemoveToastNotification(v34, &Destination);
                if ( CWwanUicc::isAutoSlotSwitchEnabled(v35) )
                {
                  v36 = CWwanUicc::UiccSlotRemap(this, 4u, (const unsigned __int8 *)&v111, 0, v99);
                  if ( v36 )
                    WwanLog::Error("CWwanUicc::OnNdisNotification", 0, L"UiccSlotRemap failed (err 0x%x)", v36);
                  CWwanManager::GetInstance();
                  v31 = 3;
                }
                else
                {
                  CWwanManager::GetInstance();
                  v31 = 2;
                }
                goto LABEL_126;
              }
              if ( v29 == v106 && v32 && !v33 )
              {
                CWwanManager::GetInstance();
                CWwanManager::RemoveToastNotification(v38, &Destination);
              }
            }
          }
        }
      }
LABEL_131:
      v39 = v21[1];
      if ( *((_DWORD *)this + 6 * *v21 + 234) == 7 )
      {
        if ( v39 != 8 )
        {
LABEL_133:
          v40 = 0;
LABEL_134:
          *((_DWORD *)this + 6 * *v21 + 234) = v39;
          CWwanUicc::runOobeDssaSlotSwitch(this, v40);
          if ( v18 )
          {
            v20 = 0;
            v41 = v108;
            LODWORD(v102) = *v21;
            WwanLog::Info(
              "CWwanUicc::OnNdisNotification",
              0,
              L" WwanEventCodeUiccSlotInfo query response (reqID %d reqHandle 0x%p): slotIdx %d State %d",
              *((unsigned int *)this + 6 * v108 + 235),
              *((_QWORD *)this + 3 * v108 + 118),
              v102,
              v21[1]);
LABEL_143:
            v42 = 3LL * v41;
            *((_BYTE *)this + 8 * v42 + 928) = 1;
            *((_DWORD *)this + 2 * v42 + 233) = v20;
            *((_DWORD *)this + 2 * v42 + 235) = 0;
            *((_QWORD *)this + v42 + 118) = 0;
            goto LABEL_144;
          }
          LODWORD(v99) = v21[1];
          WwanLog::Info(
            "CWwanUicc::OnNdisNotification",
            0,
            L" WwanEventCodeUiccSlotInfo indication: slotIdx %d State %d",
            *v21,
            v99);
          goto LABEL_144;
        }
      }
      else if ( *((_DWORD *)this + 6 * *v21 + 234) != 8 || v39 != 7 )
      {
        goto LABEL_133;
      }
      v40 = 1;
      goto LABEL_134;
    }
    v43 = 1;
    if ( *(_DWORD *)a2 != 1 )
    {
      WwanLog::Error("CWwanUicc::OnNdisNotification", 0, L"WwanEventCodeUiccSlotMapping isRsp %d");
      return;
    }
    v44 = *((_DWORD *)a2 + 4);
    v106 = v44;
    v45 = *((_QWORD *)this + 103);
    v46 = 0;
    if ( !v45 || v45 != *((_QWORD *)a2 + 3) )
    {
      LOBYTE(v46) = v44 == 1;
      WwanLog::Error(
        "CWwanUicc::OnNdisNotification",
        0,
        L"WwanEventCodeUiccSlotMapping unknown (isQuery %d) response, expecting reqID %d reqHandle 0x%p; received reqHandle 0x%p",
        v46,
        *((_DWORD *)this + 204),
        v45,
        *((_QWORD *)a2 + 3));
      return;
    }
    v47 = (_DWORD *)((char *)a2 + 92);
    if ( a2 == (const struct WWAN_EVENT *)-92LL || *((_DWORD *)a2 + 22) < 8u )
    {
      v49 = (_DWORD *)((char *)this + 808);
      *((_DWORD *)this + 202) = -1073739509;
      v50 = (int *)((char *)this + 812);
      *((_DWORD *)this + 203) = 0;
      v52 = (_DWORD *)((char *)this + 816);
      WwanLog::Error(
        "CWwanUicc::OnNdisNotification",
        0,
        L"WwanEventCodeUiccSlotMapping response (reqID %d reqHandle 0x%p) with bad data (size %d pData 0x%p)",
        *((unsigned int *)this + 204),
        v45,
        *((_DWORD *)a2 + 22),
        (char *)a2 + 92);
    }
    else if ( *((_DWORD *)a2 + 24) == 1
           && *v47 == 14
           && 4 * (unsigned __int64)*((unsigned int *)a2 + 24) + 8 <= *((unsigned int *)a2 + 22) )
    {
      v48 = *((_DWORD *)a2 + 8);
      v49 = (_DWORD *)((char *)this + 808);
      *((_DWORD *)this + 202) = v48;
      v50 = (int *)((char *)this + 812);
      v116 = (struct _GUID *)*((unsigned int *)this + 203);
      v51 = *((_DWORD *)a2 + 25);
      *((_DWORD *)this + 203) = v51;
      v52 = (_DWORD *)((char *)this + 816);
      v53 = *((_DWORD *)this + 204);
      v54 = L"query";
      if ( *((_DWORD *)a2 + 8) )
      {
        *v50 = 0;
        if ( v44 != 1 )
          v54 = L"set";
        WwanLog::Error(
          "CWwanUicc::OnNdisNotification",
          0,
          L"WwanEventCodeUiccSlotMapping %s response (reqID %d reqHandle 0x%p): status 0x%x",
          v54,
          v53,
          v45,
          v48);
      }
      else
      {
        v100 = *((_DWORD *)this + 204);
        if ( v51 < 2 )
        {
          if ( v44 != 1 )
            v54 = L"set";
          WwanLog::Info(
            "CWwanUicc::OnNdisNotification",
            0,
            L" WwanEventCodeUiccSlotMapping %s response (reqID %d reqHandle 0x%p): m_slotInUse %d",
            v54,
            v100,
            v45,
            v51);
          if ( !*((_BYTE *)this + 856) )
          {
            v105 = -1;
            if ( *(_QWORD *)std::_Hash<std::_Uset_traits<enum _WWAN_INTERFACE_TYPE,std::_Uhash_compare<enum _WWAN_INTERFACE_TYPE,std::hash<enum _WWAN_INTERFACE_TYPE>,std::equal_to<enum _WWAN_INTERFACE_TYPE>>,std::allocator<enum _WWAN_INTERFACE_TYPE>,0>>::find(
                              (char *)this + 624,
                              &v112,
                              &v105) != *((_QWORD *)this + 79) )
            {
              v105 = -1;
              if ( *(_QWORD *)(*(_QWORD *)std::_Hash<std::_Umap_traits<unsigned long,std::unique_ptr<WWAN_SUBSCRIBER_INFORMATION>,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,std::unique_ptr<WWAN_SUBSCRIBER_INFORMATION>>>,0>>::_Try_emplace<unsigned long const &,>(
                                            (char *)this + 624,
                                            &v112,
                                            &v105)
                             + 24LL) )
              {
                v105 = -1;
                v55 = *(_QWORD *)std::_Hash<std::_Umap_traits<unsigned long,std::unique_ptr<WWAN_SUBSCRIBER_INFORMATION>,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,std::unique_ptr<WWAN_SUBSCRIBER_INFORMATION>>>,0>>::_Try_emplace<unsigned long const &,>(
                                   (char *)this + 624,
                                   &v112,
                                   &v105);
                v56 = *(_QWORD *)std::_Hash<std::_Umap_traits<unsigned long,std::unique_ptr<WWAN_SUBSCRIBER_INFORMATION>,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,std::unique_ptr<WWAN_SUBSCRIBER_INFORMATION>>>,0>>::_Try_emplace<unsigned long const &,>(
                                   (char *)this + 624,
                                   v117,
                                   (char *)this + 812);
                v57 = *(_QWORD *)(v55 + 24);
                *(_QWORD *)(v55 + 24) = 0;
                v58 = *(void **)(v56 + 24);
                *(_QWORD *)(v56 + 24) = v57;
                if ( v58 )
                  operator delete(v58);
                v105 = -1;
                std::_Hash<std::_Umap_traits<unsigned long,std::unique_ptr<WWAN_SUBSCRIBER_INFORMATION>,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,std::unique_ptr<WWAN_SUBSCRIBER_INFORMATION>>>,0>>::_Erase<unsigned long>(
                  (char *)this + 624,
                  &v105);
                v59 = *v50;
                *(_DWORD *)(*(_QWORD *)(*(_QWORD *)std::_Hash<std::_Umap_traits<unsigned long,std::unique_ptr<WWAN_SUBSCRIBER_INFORMATION>,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,std::unique_ptr<WWAN_SUBSCRIBER_INFORMATION>>>,0>>::_Try_emplace<unsigned long const &,>(
                                                     (char *)this + 624,
                                                     &v112,
                                                     (char *)this + 812)
                                      + 24LL)
                          + 84LL) = v59;
              }
            }
            v105 = -1;
            if ( *(_QWORD *)std::_Hash<std::_Uset_traits<enum _WWAN_INTERFACE_TYPE,std::_Uhash_compare<enum _WWAN_INTERFACE_TYPE,std::hash<enum _WWAN_INTERFACE_TYPE>,std::equal_to<enum _WWAN_INTERFACE_TYPE>>,std::allocator<enum _WWAN_INTERFACE_TYPE>,0>>::find(
                              (char *)this + 688,
                              &v112,
                              &v105) != *((_QWORD *)this + 87) )
            {
              v105 = -1;
              v60 = *(_DWORD *)(*(_QWORD *)std::_Hash<std::_Umap_traits<unsigned long,unsigned long,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,unsigned long>>,0>>::_Try_emplace<unsigned long,>(
                                             (char *)this + 688,
                                             &v112,
                                             &v105)
                              + 20LL);
              *(_DWORD *)(*(_QWORD *)std::_Hash<std::_Umap_traits<unsigned long,unsigned long,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,unsigned long>>,0>>::_Try_emplace<unsigned long,>(
                                       (char *)this + 688,
                                       &v112,
                                       (char *)this + 812)
                        + 20LL) = v60;
              v105 = -1;
              std::_Hash<std::_Umap_traits<unsigned long,unsigned long,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,unsigned long>>,0>>::_Erase<unsigned long>(
                (char *)this + 688,
                &v105);
            }
            v105 = -1;
            if ( *(_QWORD *)std::_Hash<std::_Uset_traits<enum _WWAN_INTERFACE_TYPE,std::_Uhash_compare<enum _WWAN_INTERFACE_TYPE,std::hash<enum _WWAN_INTERFACE_TYPE>,std::equal_to<enum _WWAN_INTERFACE_TYPE>>,std::allocator<enum _WWAN_INTERFACE_TYPE>,0>>::find(
                              (char *)this + 560,
                              &v112,
                              &v105) != *((_QWORD *)this + 71) )
            {
              v105 = -1;
              if ( *(_QWORD *)(*(_QWORD *)std::_Hash<std::_Umap_traits<unsigned long,std::unique_ptr<_WWAN_ATR_INFO>,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,std::unique_ptr<_WWAN_ATR_INFO>>>,0>>::_Try_emplace<unsigned long const &,>(
                                            (char *)this + 560,
                                            &v112,
                                            &v105)
                             + 24LL) )
              {
                v105 = -1;
                v61 = *(_QWORD *)std::_Hash<std::_Umap_traits<unsigned long,std::unique_ptr<_WWAN_ATR_INFO>,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,std::unique_ptr<_WWAN_ATR_INFO>>>,0>>::_Try_emplace<unsigned long const &,>(
                                   (char *)this + 560,
                                   &v112,
                                   &v105);
                v62 = (_QWORD *)std::_Hash<std::_Umap_traits<unsigned long,std::unique_ptr<_WWAN_ATR_INFO>,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,std::unique_ptr<_WWAN_ATR_INFO>>>,0>>::_Try_emplace<unsigned long const &,>(
                                  (char *)this + 560,
                                  v117,
                                  (char *)this + 812);
                std::unique_ptr<_WWAN_ATR_INFO>::operator=<std::default_delete<_WWAN_ATR_INFO>,0>(*v62 + 24LL, v61 + 24);
                v105 = -1;
                std::_Hash<std::_Umap_traits<unsigned long,std::unique_ptr<_WWAN_ATR_INFO>,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,std::unique_ptr<_WWAN_ATR_INFO>>>,0>>::_Erase<unsigned long>(
                  (char *)this + 560,
                  &v105);
              }
            }
            *((_BYTE *)this + 856) = 1;
            if ( (*((_DWORD *)this + 191) & 0x800) != 0 )
            {
              v63 = (*v50 - 1) & 1;
              EmbeddedSlotIndex = v63;
              v105 = 0;
              v111 = CWwanInterface::SendRequest(
                       (char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 8,
                       2,
                       1,
                       &EmbeddedSlotIndex,
                       4,
                       0,
                       &v105,
                       0,
                       0,
                       0,
                       -1);
              v64 = std::_Hash<std::_Umap_traits<unsigned long,unsigned long,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,unsigned long>>,0>>::_Try_emplace<unsigned long,>(
                      (char *)this + 496,
                      &v112,
                      &v105);
              *(_DWORD *)(*(_QWORD *)v64 + 20LL) = EmbeddedSlotIndex;
              if ( v111 )
              {
                LODWORD(v101) = v111;
                WwanLog::Error(
                  "CWwanUicc::OnNdisNotification",
                  0,
                  L"Failed to send query WwanEventCodeReadyInfo for Inactive slot %d, Error = 0x%x",
                  v63,
                  v101);
              }
            }
          }
          if ( (_DWORD)v116 != *v50 )
          {
            Instance = CWwanManager::GetInstance();
            v66 = *(_QWORD *)CWwanManager::GetExecutorFromInterfaceGuid(
                               Instance,
                               &v112,
                               (char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 8);
            if ( v113 )
              std::_Ref_count_base::_Decref(v113);
            if ( v66 )
            {
              v67 = CWwanManager::GetInstance();
              ExecutorFromInterfaceGuid = (_QWORD *)CWwanManager::GetExecutorFromInterfaceGuid(
                                                      v67,
                                                      &v112,
                                                      (char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 8);
              v69 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*ExecutorFromInterfaceGuid + 608LL))(*ExecutorFromInterfaceGuid);
              CWwanFirstTimeModemReadyTelemetryEventContext::Start(v69, 3);
              if ( v113 )
                std::_Ref_count_base::_Decref(v113);
            }
          }
        }
        else
        {
          *v49 = -1073739509;
          if ( v44 != 1 )
            v54 = L"set";
          WwanLog::Error(
            "CWwanUicc::OnNdisNotification",
            0,
            L"WwanEventCodeUiccSlotMapping %s response (reqID %d reqHandle 0x%p): invalid slot mapping 0x%x",
            v54,
            v100,
            v45,
            v51);
          *v50 = 0;
          v52 = (_DWORD *)((char *)this + 816);
        }
      }
      if ( (*((_DWORD *)this + 191) & 0x800) == 0 )
      {
        v70 = (__int64 *)*((_QWORD *)this + 109);
        while ( 1 )
        {
          v70 = (__int64 *)*v70;
          if ( v70 == *((__int64 **)this + 109) )
            break;
          v71 = *((_DWORD *)v70 + 4);
          if ( v71 != *v50 )
            CWwanUicc::removeUiccIsoSwDevice(this, v71);
        }
      }
      if ( *((_QWORD *)this + 109) == *(_QWORD *)std::_Hash<std::_Uset_traits<enum _WWAN_INTERFACE_TYPE,std::_Uhash_compare<enum _WWAN_INTERFACE_TYPE,std::hash<enum _WWAN_INTERFACE_TYPE>,std::equal_to<enum _WWAN_INTERFACE_TYPE>>,std::allocator<enum _WWAN_INTERFACE_TYPE>,0>>::find(
                                                   (char *)this + 864,
                                                   &v112,
                                                   (char *)this + 812)
        || !*(_QWORD *)(*(_QWORD *)std::_Hash<std::_Umap_traits<unsigned long,void *,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,void *>>,0>>::_Try_emplace<unsigned long const &,>(
                                     (char *)this + 864,
                                     &v112,
                                     (char *)this + 812)
                      + 24LL) )
      {
        if ( *(_QWORD *)(*(_QWORD *)std::_Hash<std::_Umap_traits<unsigned long,std::unique_ptr<_WWAN_ATR_INFO>,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,std::unique_ptr<_WWAN_ATR_INFO>>>,0>>::_Try_emplace<unsigned long const &,>(
                                      (char *)this + 560,
                                      &v112,
                                      (char *)this + 812)
                       + 24LL) )
        {
          v72 = (unsigned int)*v50;
          if ( *((_DWORD *)this + 6 * v72 + 234) != 1 && *((_DWORD *)this + 6 * v72 + 234) != 3 )
            CWwanUicc::createUiccIsoSwDevice(this, v72);
        }
      }
      else
      {
        v52 = (_DWORD *)((char *)this + 816);
      }
    }
    else
    {
      v49 = (_DWORD *)((char *)this + 808);
      *((_DWORD *)this + 202) = -1073739509;
      v50 = (int *)((char *)this + 812);
      *((_DWORD *)this + 203) = 0;
      v52 = (_DWORD *)((char *)this + 816);
      v104 = *((_DWORD *)a2 + 24);
      WwanLog::Error(
        "CWwanUicc::OnNdisNotification",
        0,
        L"WwanEventCodeUiccSlotMapping response (reqID %d reqHandle 0x%p) with bad data: ElementCount %d ElementType %d to"
         "tal size %d (expected %d)",
        *((unsigned int *)this + 204),
        v45,
        v104,
        *v47,
        *((_DWORD *)a2 + 22),
        4LL * v104 + 8);
    }
    *v52 = 0;
    *((_QWORD *)this + 103) = 0;
    v73 = 3;
    if ( v106 == 1 )
      v73 = 5;
    CWwanUicc::fsmEventHandler(this, v73);
    if ( v106 == 1 || *v49 )
      return;
    memset_0(sz, 0, 0x5Eu);
    StringFromGUID2((const GUID *const)((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 8), sz, 47);
    v105 = 37;
    std::make_unique<StateSeparation,enum _REG_ROOT_PATH,0>(&v118, &v105);
    v108 = 0;
    v111 = 0;
    v74 = 0;
    DWORD = StateSeparation::GetDWORD(v118, sz, L"eSIMinSlot0", &v108);
    if ( DWORD )
    {
      LODWORD(v103) = DWORD;
      WwanLog::Error(
        "CWwanUicc::OnNdisNotification",
        0,
        L": Failed to get interface %s DWORD property [%s] with error (%u)",
        sz,
        L"eSIMinSlot0",
        v103);
      v108 = 0;
    }
    v76 = StateSeparation::GetDWORD(v118, sz, L"eSIMinSlot1", &v111);
    if ( v76 )
    {
      LODWORD(v103) = v76;
      WwanLog::Error(
        "CWwanUicc::OnNdisNotification",
        0,
        L": Failed to get interface %s DWORD property [%s] with error (%u)",
        sz,
        L"eSIMinSlot1",
        v103);
      v77 = 0;
      v111 = 0;
    }
    else
    {
      v77 = v111;
    }
    if ( *v50 )
    {
      v78 = v77;
      v77 = v108;
    }
    else
    {
      v78 = v108;
    }
    if ( v78 )
    {
      if ( v78 == 1 )
      {
        switch ( (_DWORD)v77 )
        {
          case 0:
            v74 = 6;
            goto LABEL_232;
          case 1:
            v74 = 4;
            goto LABEL_232;
          case 2:
            v74 = 1;
            goto LABEL_232;
        }
      }
      else
      {
        if ( v78 != 2 )
        {
          WwanLog::Error("CWwanUicc::OnNdisNotification", 0, L"Unexpected value for slotInUseIsEsim = %d", v78);
LABEL_232:
          v79 = _InterlockedIncrement64((volatile signed __int64 *)&g_TelemetrySequenceNumber);
          v114 = 37;
          std::make_unique<StateSeparation,enum _REG_ROOT_PATH,0>(&v116, &v114);
          memset_0(&Destination, 0, 0x5Eu);
          StringFromGUID2(
            (const GUID *const)((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 8),
            &Destination,
            47);
          v106 = 0;
          v115 = 0;
          EmbeddedSlotIndex = 0;
          v105 = 0;
          v80 = v116;
          v81 = StateSeparation::GetDWORD((StateSeparation *)v116, &Destination, L"DSDxType", &v106);
          if ( v81 )
          {
            LODWORD(v103) = v81;
            WwanLog::Error(
              "CWwanUicc::OnNdisNotification",
              0,
              L": Failed to get interface %s DWORD property [%s] with error (%u)",
              &Destination,
              L"DSDxType",
              v103);
            v106 = 0;
          }
          v82 = StateSeparation::GetDWORD((StateSeparation *)v80, &Destination, L"ActiveSIMSlotForDSSA", &v115);
          if ( v82 )
          {
            LODWORD(v103) = v82;
            WwanLog::Error(
              "CWwanUicc::OnNdisNotification",
              0,
              L": Failed to get interface %s DWORD property [%s] with error (%u)",
              &Destination,
              L"ActiveSIMSlotForDSSA",
              v103);
            v115 = 0;
          }
          v83 = StateSeparation::GetDWORD(
                  (StateSeparation *)v80,
                  &Destination,
                  L"SupportedDataClassBitMap",
                  &EmbeddedSlotIndex);
          if ( v83 )
          {
            LODWORD(v103) = v83;
            WwanLog::Error(
              "CWwanUicc::OnNdisNotification",
              0,
              L": Failed to get interface %s DWORD property [%s] with error (%u)",
              &Destination,
              L"SupportedDataClassBitMap",
              v103);
            EmbeddedSlotIndex = 0;
          }
          v84 = StateSeparation::GetDWORD((StateSeparation *)v80, &Destination, L"ModemOptionalCapabilityBitMap", &v105);
          if ( v84 )
          {
            LODWORD(v103) = v84;
            WwanLog::Error(
              "CWwanUicc::OnNdisNotification",
              0,
              L": Failed to get interface %s DWORD property [%s] with error (%u)",
              &Destination,
              L"ModemOptionalCapabilityBitMap",
              v103);
            v105 = 0;
          }
          if ( v106 != 2 || v115 != 1 )
            v43 = 0;
          v149 = 0;
          v150 = 0;
          v151 = 7;
          LOWORD(v149) = 0;
          v146 = 0;
          v147 = 0;
          v148 = 7;
          LOWORD(v146) = 0;
          v143 = 0;
          v144 = 0;
          v145 = 7;
          LOWORD(v143) = 0;
          v140 = 0;
          v141 = 0;
          v142 = 7;
          LOWORD(v140) = 0;
          v137 = 0;
          v138 = 0;
          v139 = 7;
          LOWORD(v137) = 0;
          v134 = 0;
          v135 = 0;
          v136 = 7;
          LOWORD(v134) = 0;
          v131 = 0;
          v132 = 0;
          v133 = 7;
          LOWORD(v131) = 0;
          String = StateSeparation::GetString(v80, &Destination, L"HWID", &v149);
          if ( String )
          {
            LODWORD(v103) = String;
            WwanLog::Error(
              "CWwanUicc::OnNdisNotification",
              0,
              L": Failed to get interface %s string property [%s] with error (%u)",
              &Destination,
              L"HWID",
              v103);
            v150 = 0;
            *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v149) = 0;
          }
          v86 = StateSeparation::GetString(v80, &Destination, L"DriverName", &v146);
          if ( v86 )
          {
            LODWORD(v103) = v86;
            WwanLog::Error(
              "CWwanUicc::OnNdisNotification",
              0,
              L": Failed to get interface %s string property [%s] with error (%u)",
              &Destination,
              L"DriverName",
              v103);
            v147 = 0;
            *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v146) = 0;
          }
          v87 = StateSeparation::GetString(v80, &Destination, L"Manufacturer", &v143);
          if ( v87 )
          {
            LODWORD(v103) = v87;
            WwanLog::Error(
              "CWwanUicc::OnNdisNotification",
              0,
              L": Failed to get interface %s string property [%s] with error (%u)",
              &Destination,
              L"Manufacturer",
              v103);
            v144 = 0;
            *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v143) = 0;
          }
          v88 = StateSeparation::GetString(v80, &Destination, L"FirmwareVersion", &v140);
          if ( v88 )
          {
            LODWORD(v103) = v88;
            WwanLog::Error(
              "CWwanUicc::OnNdisNotification",
              0,
              L": Failed to get interface %s string property [%s] with error (%u)",
              &Destination,
              L"FirmwareVersion",
              v103);
            v141 = 0;
            *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v140) = 0;
          }
          v89 = L"MCC1";
          if ( !v43 )
            v89 = L"MCC0";
          v90 = StateSeparation::GetString(v80, &Destination, v89, &v137);
          if ( v90 )
          {
            LODWORD(v103) = v90;
            WwanLog::Error(
              "CWwanUicc::OnNdisNotification",
              0,
              L": Failed to get interface %s string property [%s] with error (%u)",
              &Destination,
              v89,
              v103);
            v138 = 0;
            *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v137) = 0;
          }
          v91 = L"MNC1";
          if ( !v43 )
            v91 = L"MNC0";
          v92 = StateSeparation::GetString(v80, &Destination, v91, &v134);
          if ( v92 )
          {
            LODWORD(v103) = v92;
            WwanLog::Error(
              "CWwanUicc::OnNdisNotification",
              0,
              L": Failed to get interface %s string property [%s] with error (%u)",
              &Destination,
              v91,
              v103);
            v135 = 0;
            *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v134) = 0;
          }
          v93 = L"MobileOperatorInUse1";
          if ( !v43 )
            v93 = L"MobileOperatorInUse0";
          v94 = StateSeparation::GetString(v80, &Destination, v93, &v131);
          if ( v94 )
          {
            LODWORD(v103) = v94;
            WwanLog::Error(
              "CWwanUicc::OnNdisNotification",
              0,
              L": Failed to get interface %s string property [%s] with error (%u)",
              &Destination,
              v93,
              v103);
            v132 = 0;
            *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v131) = 0;
          }
          if ( (unsigned int)dword_180151040 > 5
            && (unsigned __int8)tlgKeywordOn(&dword_180151040, 0x800000000000LL, v95) )
          {
            v114 = v74;
            v129 = 16779264;
            v130 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v134);
            v119 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v137);
            v120 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v131);
            v121 = EmbeddedSlotIndex;
            v122 = v105;
            v123 = v115;
            v124 = v106;
            v125 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v140);
            v126 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v143);
            v127 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v146);
            v128 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v149);
            v117[0] = (char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 8;
            v112 = v79;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
              v96,
              (unsigned int)&unk_180140138,
              v97,
              v98,
              (__int64)&v112,
              (__int64)v117,
              (__int64)&v128,
              (__int64)&v127,
              (__int64)&v126,
              (__int64)&v125,
              (__int64)&v124,
              (__int64)&v123,
              (__int64)&v122,
              (__int64)&v121,
              (__int64)&v120,
              (__int64)&v119,
              (__int64)&v130,
              (__int64)&v129,
              (__int64)&v114);
          }
          std::wstring::_Tidy_deallocate(&v131);
          std::wstring::_Tidy_deallocate(&v134);
          std::wstring::_Tidy_deallocate(&v137);
          std::wstring::_Tidy_deallocate(&v140);
          std::wstring::_Tidy_deallocate(&v143);
          std::wstring::_Tidy_deallocate(&v146);
          std::wstring::_Tidy_deallocate(&v149);
          std::unique_ptr<StateSeparation>::~unique_ptr<StateSeparation>(&v116);
          std::unique_ptr<StateSeparation>::~unique_ptr<StateSeparation>(&v118);
          return;
        }
        switch ( (_DWORD)v77 )
        {
          case 0:
            v74 = 5;
            goto LABEL_232;
          case 1:
            v74 = 2;
            goto LABEL_232;
          case 2:
            v74 = 3;
            goto LABEL_232;
        }
      }
    }
    else
    {
      switch ( (_DWORD)v77 )
      {
        case 0:
          v74 = 0;
          goto LABEL_232;
        case 1:
          v74 = 8;
          goto LABEL_232;
        case 2:
          v74 = 7;
          goto LABEL_232;
      }
    }
    WwanLog::Error("CWwanUicc::OnNdisNotification", 0, L"Unexpected value for inactiveSlotIsEsim = %d", v77);
    goto LABEL_232;
  }
  if ( v4 == 48 )
  {
    if ( *((_DWORD *)a2 + 4) )
      WwanLog::Error("CWwanUicc::OnNdisNotification", 0, L"Error in APDU response");
    else
      CWwanUicc::onSendApdu(this, a2);
    return;
  }
  if ( v4 != 2 )
  {
    if ( v4 != 6 )
    {
      switch ( v4 )
      {
        case 7:
          if ( *(_DWORD *)a2 != 2 && (*((_DWORD *)a2 + 8) || *((_DWORD *)a2 + 4) != 1) )
          {
            WwanLog::Error("CWwanUicc::OnNdisNotification", 0, L"Error in preferred providers received");
            return;
          }
          v7 = CWwanUicc::convertToProviderList(this, &v112, (char *)a2 + 92, *((unsigned int *)a2 + 22));
          v8 = (char *)this + 416;
          break;
        case 36:
          if ( *(_DWORD *)a2 != 2 && (*((_DWORD *)a2 + 8) || *((_DWORD *)a2 + 4) != 1) )
          {
            WwanLog::Error("CWwanUicc::OnNdisNotification", 0, L"Error in Multi-carrier preferred providers response");
            return;
          }
          v7 = CWwanUicc::convertToProviderList(this, &v112, (char *)a2 + 92, *((unsigned int *)a2 + 22));
          v8 = (char *)this + 432;
          break;
        case 45:
          if ( !*((_DWORD *)a2 + 8) && *((_DWORD *)a2 + 4) == 1 )
          {
            wwan::unique_autoref_tx::unique_autoref_tx((wwan::unique_autoref_tx *)v117, *((void **)a2 + 3));
            if ( v117[0] )
            {
              v106 = *(_DWORD *)(v117[0] + 52LL);
              if ( *(_QWORD *)std::_Hash<std::_Uset_traits<enum _WWAN_INTERFACE_TYPE,std::_Uhash_compare<enum _WWAN_INTERFACE_TYPE,std::hash<enum _WWAN_INTERFACE_TYPE>,std::equal_to<enum _WWAN_INTERFACE_TYPE>>,std::allocator<enum _WWAN_INTERFACE_TYPE>,0>>::find(
                                (char *)this + 496,
                                &v112,
                                &v106) == *((_QWORD *)this + 63) )
              {
                WwanLog::Error("CWwanUicc::OnNdisNotification", 0, L"RequestId is not present in internal map!");
              }
              else
              {
                v5 = std::_Hash<std::_Umap_traits<unsigned long,unsigned long,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,unsigned long>>,0>>::_Try_emplace<unsigned long,>(
                       (char *)this + 496,
                       &v112,
                       &v106);
                CWwanUicc::onAtr(this, *(_DWORD *)(*(_QWORD *)v5 + 20LL), (char *)a2 + 92, *((_DWORD *)a2 + 22));
                std::_Hash<std::_Umap_traits<unsigned long,unsigned long,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,unsigned long>>,0>>::_Erase<unsigned long>(
                  (char *)this + 496,
                  &v106);
              }
            }
            else
            {
              WwanLog::Error("CWwanUicc::OnNdisNotification", 0, L"Unexpected response");
            }
            wwan::unique_autoref_tx::~unique_autoref_tx((wwan::unique_autoref_tx *)v117);
            return;
          }
          v6 = L"Error in ATR response [result:0x%x, setQueryType:%d]";
LABEL_33:
          WwanLog::Error("CWwanUicc::OnNdisNotification", 0, v6);
          return;
        default:
          switch ( v4 )
          {
            case 46:
              if ( *((_DWORD *)a2 + 4) )
                WwanLog::Error("CWwanUicc::OnNdisNotification", 0, L"Error in open channel response");
              else
                CWwanUicc::onOpenChannel(this, a2);
              break;
            case 47:
              if ( *((_DWORD *)a2 + 4) )
                WwanLog::Error("CWwanUicc::OnNdisNotification", 0, L"Error in close channel response");
              else
                CWwanUicc::onCloseChannel(this, a2);
              break;
            case 3:
            case 34:
              CWwanPinSM::processPinInfoResponse(this, a2);
              break;
            case 5:
              CWwanPinSM::processPinListResponse(this, a2);
              break;
            case 4:
            case 33:
              CWwanPinSM::processPinActionResponse(this, a2);
              break;
          }
          return;
      }
      std::list<_WWAN_PROVIDER2>::operator=(v8, v7);
      std::_List_node<_WWAN_PROVIDER2,void *>::_Free_non_head<std::allocator<std::_List_node<_WWAN_PROVIDER2,void *>>>(
        v9,
        v112);
      std::_Deallocate<16>(v112, 96);
      return;
    }
    v10 = 1;
    if ( *(_DWORD *)a2 == 1 )
    {
      if ( *((_DWORD *)a2 + 4) == 1 )
      {
        v11 = *((_QWORD *)this + 57);
        if ( v11 == -1 )
        {
          WwanLog::Error(
            "CWwanUicc::OnNdisNotification",
            0,
            L"receiving a HomeProvider queryRsp (0x%p) with no pending req",
            *((_QWORD *)a2 + 3));
        }
        else if ( v11 == *((_QWORD *)a2 + 3) )
        {
          WwanLog::Info("CWwanUicc::OnNdisNotification", 0, L" a pending HomeProvider query (0x%p) is cleared");
          *((_QWORD *)this + 57) = -1;
        }
        else
        {
          WwanLog::Error(
            "CWwanUicc::OnNdisNotification",
            0,
            L"receiving a HomeProvider queryRsp (0x%p) not matching pending req (0x%p)",
            *((_QWORD *)a2 + 3),
            *((_QWORD *)this + 57));
        }
      }
      else
      {
        v10 = 0;
        WwanLog::Error(
          "CWwanUicc::OnNdisNotification",
          0,
          L"unexpected HomeProvider setRsp (0x%p) (pendingQuery 0x%p)",
          *((_QWORD *)a2 + 3),
          *((_QWORD *)this + 57));
      }
      if ( *((_DWORD *)a2 + 8) )
      {
        WwanLog::Error("CWwanUicc::OnNdisNotification", 0, L"failure HomeProvider HomeProvider response (result 0x%x)");
        return;
      }
    }
    else
    {
      v10 = 0;
      if ( *(_DWORD *)a2 != 2 )
      {
        v6 = L"invalid WwanEventCodeHomeProvider event (type %d, size %d)";
        goto LABEL_33;
      }
    }
    if ( a2 == (const struct WWAN_EVENT *)-92LL )
    {
      WwanLog::Error("CWwanUicc::OnNdisNotification", 0, L"received a null response");
    }
    else if ( *((_DWORD *)a2 + 22) >= 0x44u )
    {
      Destination = 0;
      v154 = 0;
      memset_0(v153, 0, 0x46u);
      LODWORD(v99) = *((_DWORD *)a2 + 27);
      WwanLog::Info(
        "CWwanUicc::OnNdisNotification",
        0,
        L" HomeProvider ID [%s] state %d Name [%s] dataCleass 0x%x",
        (char *)a2 + 92,
        v99,
        (char *)a2 + 112,
        *((_DWORD *)a2 + 39));
      memcpy_s(&Destination, 0x44u, (char *)a2 + 92, 0x44u);
      v155 = 0;
      CWwanUicc::onHomeProvider(this, (const struct WWAN_PROVIDER_OBJECT *)&Destination, v10);
    }
    else
    {
      WwanLog::Error("CWwanUicc::OnNdisNotification", 0, L"received a response with insufficient buffer size(%d)");
    }
    return;
  }
  if ( *(_DWORD *)a2 == 2 || !*((_DWORD *)a2 + 8) )
  {
    if ( *(_DWORD *)a2 == 1 )
      v12 = (void *)*((_QWORD *)a2 + 3);
    else
      v12 = 0;
    CWwanUicc::onReadyStateInfo(this, (const struct WWAN_EVENT *)((char *)a2 + 92), v12);
  }
  else
  {
    WwanLog::Error("CWwanUicc::OnNdisNotification", 0, L"Error in Ready info received");
  }
}

```

## disassembly

```asm
0x180068eac  mov     [rsp-8+arg_10], rbx
0x180068eb1  push    rbp
0x180068eb2  push    rsi
0x180068eb3  push    rdi
0x180068eb4  push    r12
0x180068eb6  push    r13
0x180068eb8  push    r14
0x180068eba  push    r15
0x180068ebc  lea     rbp, [rsp-1F0h]
0x180068ec4  sub     rsp, 310h
0x180068ecb  mov     rax, cs:__security_cookie
0x180068ed2  xor     rax, rsp
0x180068ed5  mov     [rbp+220h+var_40], rax
0x180068edc  mov     rbx, rdx
0x180068edf  mov     rsi, rcx
0x180068ee2  mov     ecx, [rdx+4]
0x180068ee5  cmp     ecx, 30h ; '0'
0x180068ee8  jg      loc_180069322
0x180068eee  jz      loc_180069302
0x180068ef4  mov     edx, ecx
0x180068ef6  sub     edx, 2
0x180068ef9  jz      loc_1800692C5
0x180068eff  sub     edx, 4
0x180068f02  jz      loc_18006914C
0x180068f08  sub     edx, 1
0x180068f0b  jz      loc_1800690EB
0x180068f11  sub     edx, 1Dh
0x180068f14  jz      loc_1800690AC
0x180068f1a  sub     edx, 9
0x180068f1d  jz      loc_180068FCF
0x180068f23  sub     edx, 1
0x180068f26  jz      short loc_180068F9E
0x180068f28  cmp     edx, 1
0x180068f2b  jz      short loc_180068F7E
0x180068f2d  cmp     ecx, 3
0x180068f30  jz      short loc_180068F6E
0x180068f32  cmp     ecx, 22h ; '"'
0x180068f35  jz      short loc_180068F6E
0x180068f37  mov     edx, 5
0x180068f3c  cmp     ecx, edx
0x180068f3e  jnz     short loc_180068F50
0x180068f40  mov     rdx, rbx; struct WWAN_EVENT *
0x180068f43  mov     rcx, rsi; this
0x180068f46  call    ?processPinListResponse@CWwanPinSM@@AEAAXPEBUWWAN_EVENT@@@Z; CWwanPinSM::processPinListResponse(WWAN_EVENT const *)
0x180068f4b  jmp     loc_18006A6D0
0x180068f50  cmp     ecx, 4
0x180068f53  jz      short loc_180068F5E
0x180068f55  cmp     ecx, 21h ; '!'
0x180068f58  jnz     loc_18006A6D0
0x180068f5e  mov     rdx, rbx; struct WWAN_EVENT *
0x180068f61  mov     rcx, rsi; this
0x180068f64  call    ?processPinActionResponse@CWwanPinSM@@AEAAXPEBUWWAN_EVENT@@@Z; CWwanPinSM::processPinActionResponse(WWAN_EVENT const *)
0x180068f69  jmp     loc_18006A6D0
0x180068f6e  mov     rdx, rbx; struct WWAN_EVENT *
0x180068f71  mov     rcx, rsi; this
0x180068f74  call    ?processPinInfoResponse@CWwanPinSM@@AEAAXPEBUWWAN_EVENT@@@Z; CWwanPinSM::processPinInfoResponse(WWAN_EVENT const *)
0x180068f79  jmp     loc_18006A6D0
0x180068f7e  xor     edi, edi
0x180068f80  cmp     [rbx+10h], edi
0x180068f83  jnz     short loc_180068F95
0x180068f85  mov     rdx, rbx; struct WWAN_EVENT *
0x180068f88  mov     rcx, rsi; this
0x180068f8b  call    ?onCloseChannel@CWwanUicc@@AEAAXPEBUWWAN_EVENT@@@Z; CWwanUicc::onCloseChannel(WWAN_EVENT const *)
0x180068f90  jmp     loc_18006A6D0
0x180068f95  lea     r8, aErrorInCloseCh; "Error in close channel response"
0x180068f9c  jmp     short loc_180068FBC
0x180068f9e  xor     edi, edi
0x180068fa0  cmp     [rbx+10h], edi
0x180068fa3  jnz     short loc_180068FB5
0x180068fa5  mov     rdx, rbx; struct WWAN_EVENT *
0x180068fa8  mov     rcx, rsi; this
0x180068fab  call    ?onOpenChannel@CWwanUicc@@AEAAXPEBUWWAN_EVENT@@@Z; CWwanUicc::onOpenChannel(WWAN_EVENT const *)
0x180068fb0  jmp     loc_18006A6D0
0x180068fb5  lea     r8, aErrorInOpenCha; "Error in open channel response"
0x180068fbc  xor     edx, edx; struct _GUID *
0x180068fbe  lea     rcx, aCwwanuiccOnndi; "CWwanUicc::OnNdisNotification"
0x180068fc5  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180068fca  jmp     loc_18006A6D0
0x180068fcf  mov     r9d, [rbx+20h]
0x180068fd3  test    r9d, r9d
0x180068fd6  jnz     loc_18006908B
0x180068fdc  lea     r14d, [r9+1]
0x180068fe0  cmp     [rbx+10h], r14d
0x180068fe4  jnz     loc_18006908B
0x180068fea  mov     rdx, [rbx+18h]; void *
0x180068fee  lea     rcx, [rbp+220h+var_258]; this
0x180068ff2  call    ??0unique_autoref_tx@wwan@@QEAA@PEAX@Z; wwan::unique_autoref_tx::unique_autoref_tx(void *)
0x180068ff7  nop
0x180068ff8  mov     rax, [rbp+220h+var_258]
0x180068ffc  test    rax, rax
0x180068fff  jnz     short loc_180069025
0x180069001  lea     r8, aUnexpectedResp_0; "Unexpected response"
0x180069008  xor     edx, edx; struct _GUID *
0x18006900a  lea     rcx, aCwwanuiccOnndi; "CWwanUicc::OnNdisNotification"
0x180069011  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180069016  nop
0x180069017  lea     rcx, [rbp+220h+var_258]; this
0x18006901b  call    ??1unique_autoref_tx@wwan@@QEAA@XZ; wwan::unique_autoref_tx::~unique_autoref_tx(void)
0x180069020  jmp     loc_18006A6D0
0x180069025  mov     eax, [rax+34h]
0x180069028  mov     [rbp+220h+var_29C], eax
0x18006902b  lea     rdi, [rsi+1F0h]
0x180069032  lea     r8, [rbp+220h+var_29C]
0x180069036  lea     rdx, [rbp+220h+var_280]
0x18006903a  mov     rcx, rdi
0x18006903d  call    ?find@?$_Hash@V?$_Uset_traits@W4_WWAN_INTERFACE_TYPE@@V?$_Uhash_compare@W4_WWAN_INTERFACE_TYPE@@U?$hash@W4_WWAN_INTERFACE_TYPE@@@std@@U?$equal_to@W4_WWAN_INTERFACE_TYPE@@@3@@std@@V?$allocator@W4_WWAN_INTERFACE_TYPE@@@3@$0A@@std@@@std@@QEAA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@W4_WWAN_INTERFACE_TYPE@@@std@@@std@@@2@AEBW4_WWAN_INTERFACE_TYPE@@@Z; std::_Hash<std::_Uset_traits<_WWAN_INTERFACE_TYPE,std::_Uhash_compare<_WWAN_INTERFACE_TYPE,std::hash<_WWAN_INTERFACE_TYPE>,std::equal_to<_WWAN_INTERFACE_TYPE>>,std::allocator<_WWAN_INTERFACE_TYPE>,0>>::find(_WWAN_INTERFACE_TYPE const &)
0x180069042  mov     rcx, [rsi+1F8h]
0x180069049  cmp     [rax], rcx
0x18006904c  jnz     short loc_180069057
0x18006904e  lea     r8, aRequestidIsNot; "RequestId is not present in internal ma"...
0x180069055  jmp     short loc_180069008
0x180069057  lea     r8, [rbp+220h+var_29C]
0x18006905b  lea     rdx, [rbp+220h+var_280]
0x18006905f  mov     rcx, rdi
0x180069062  call    ??$_Try_emplace@K$$V@?$_Hash@V?$_Umap_traits@KKV?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@U?$pair@$$CBKK@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBKK@std@@PEAX@std@@_N@1@$$QEAK@Z; std::_Hash<std::_Umap_traits<ulong,ulong,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,ulong>>,0>>::_Try_emplace<ulong,>(ulong &&)
0x180069067  lea     r8, [rbx+5Ch]; void *
0x18006906b  mov     rdx, [rax]
0x18006906e  mov     r9d, [rbx+58h]; unsigned int
0x180069072  mov     edx, [rdx+14h]; unsigned int
0x180069075  mov     rcx, rsi; this
0x180069078  call    ?onAtr@CWwanUicc@@AEAAXKPEBXK@Z; CWwanUicc::onAtr(ulong,void const *,ulong)
0x18006907d  lea     rdx, [rbp+220h+var_29C]
0x180069081  mov     rcx, rdi
0x180069084  call    ??$_Erase@K@?$_Hash@V?$_Umap_traits@KKV?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@U?$pair@$$CBKK@std@@@2@$0A@@std@@@std@@AEAA_KAEBK@Z; std::_Hash<std::_Umap_traits<ulong,ulong,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,ulong>>,0>>::_Erase<ulong>(ulong const &)
0x180069089  jmp     short loc_180069017
0x18006908b  mov     eax, [rbx+10h]
0x18006908e  lea     r8, aErrorInAtrResp; "Error in ATR response [result:0x%x, set"...
0x180069095  mov     dword ptr [rsp+340h+var_320], eax
0x180069099  xor     edx, edx; struct _GUID *
0x18006909b  lea     rcx, aCwwanuiccOnndi; "CWwanUicc::OnNdisNotification"
0x1800690a2  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800690a7  jmp     loc_18006A6D0
0x1800690ac  cmp     dword ptr [rbx], 2
0x1800690af  jz      short loc_1800690CE
0x1800690b1  xor     edi, edi
0x1800690b3  cmp     [rbx+20h], edi
0x1800690b6  jnz     short loc_1800690C2
0x1800690b8  lea     r14d, [rdi+1]
0x1800690bc  cmp     [rbx+10h], r14d
0x1800690c0  jz      short loc_1800690CE
0x1800690c2  lea     r8, aErrorInMultiCa; "Error in Multi-carrier preferred provid"...
0x1800690c9  jmp     loc_180068FBC
0x1800690ce  lea     r8, [rbx+5Ch]
0x1800690d2  mov     r9d, [rbx+58h]
0x1800690d6  lea     rdx, [rbp+220h+var_280]
0x1800690da  mov     rcx, rsi
0x1800690dd  call    ?convertToProviderList@CWwanUicc@@AEBA?AV?$list@U_WWAN_PROVIDER2@@V?$allocator@U_WWAN_PROVIDER2@@@std@@@std@@PEBU_WWAN_LIST_HEADER@@K@Z; CWwanUicc::convertToProviderList(_WWAN_LIST_HEADER const *,ulong)
0x1800690e2  lea     rcx, [rsi+1B0h]
0x1800690e9  jmp     short loc_180069128
0x1800690eb  cmp     dword ptr [rbx], 2
0x1800690ee  jz      short loc_18006910D
0x1800690f0  xor     edi, edi
0x1800690f2  cmp     [rbx+20h], edi
0x1800690f5  jnz     short loc_180069101
0x1800690f7  lea     r14d, [rdi+1]
0x1800690fb  cmp     [rbx+10h], r14d
0x1800690ff  jz      short loc_18006910D
0x180069101  lea     r8, aErrorInPreferr; "Error in preferred providers received"
0x180069108  jmp     loc_180068FBC
0x18006910d  lea     r8, [rbx+5Ch]
0x180069111  mov     r9d, [rbx+58h]
0x180069115  lea     rdx, [rbp+220h+var_280]
0x180069119  mov     rcx, rsi
0x18006911c  call    ?convertToProviderList@CWwanUicc@@AEBA?AV?$list@U_WWAN_PROVIDER2@@V?$allocator@U_WWAN_PROVIDER2@@@std@@@std@@PEBU_WWAN_LIST_HEADER@@K@Z; CWwanUicc::convertToProviderList(_WWAN_LIST_HEADER const *,ulong)
0x180069121  lea     rcx, [rsi+1A0h]
0x180069128  mov     rdx, rax
0x18006912b  call    ??4?$list@U_WWAN_PROVIDER2@@V?$allocator@U_WWAN_PROVIDER2@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::list<_WWAN_PROVIDER2>::operator=(std::list<_WWAN_PROVIDER2> &&)
0x180069130  mov     rdx, [rbp+220h+var_280]
0x180069134  call    ??$_Free_non_head@V?$allocator@U?$_List_node@U_WWAN_PROVIDER2@@PEAX@std@@@std@@@?$_List_node@U_WWAN_PROVIDER2@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@U_WWAN_PROVIDER2@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<_WWAN_PROVIDER2,void *>::_Free_non_head<std::allocator<std::_List_node<_WWAN_PROVIDER2,void *>>>(std::allocator<std::_List_node<_WWAN_PROVIDER2,void *>> &,std::_List_node<_WWAN_PROVIDER2,void *> *)
0x180069139  mov     edx, 60h ; '`'
0x18006913e  mov     rcx, [rbp+220h+var_280]
0x180069142  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180069147  jmp     loc_18006A6D0
0x18006914c  mov     r14d, 1
0x180069152  xor     edi, edi
0x180069154  cmp     [rbx], r14d
0x180069157  jnz     loc_1800691E9
0x18006915d  xor     edx, edx; struct _GUID *
0x18006915f  lea     rcx, aCwwanuiccOnndi; "CWwanUicc::OnNdisNotification"
0x180069166  cmp     [rbx+10h], r14d
0x18006916a  jnz     short loc_1800691B8
0x18006916c  mov     r9, [rsi+1C8h]
0x180069173  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x180069177  jnz     short loc_18006918B
0x180069179  mov     r9, [rbx+18h]
0x18006917d  lea     r8, aReceivingAHome_0; "receiving a HomeProvider queryRsp (0x%p"...
0x180069184  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180069189  jmp     short loc_1800691D7
0x18006918b  cmp     r9, [rbx+18h]
0x18006918f  jz      short loc_18006919F
0x180069191  mov     [rsp+340h+var_320], r9
0x180069196  lea     r8, aReceivingAHome; "receiving a HomeProvider queryRsp (0x%p"...
0x18006919d  jmp     short loc_1800691CE
0x18006919f  lea     r8, aAPendingHomepr; " a pending HomeProvider query (0x%p) is"...
0x1800691a6  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x1800691ab  mov     qword ptr [rsi+1C8h], 0FFFFFFFFFFFFFFFFh
0x1800691b6  jmp     short loc_1800691D7
0x1800691b8  mov     r14b, dil
0x1800691bb  mov     rax, [rsi+1C8h]
0x1800691c2  mov     [rsp+340h+var_320], rax
0x1800691c7  lea     r8, aUnexpectedHome; "unexpected HomeProvider setRsp (0x%p) ("...
0x1800691ce  mov     r9, [rbx+18h]
0x1800691d2  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800691d7  mov     r9d, [rbx+20h]
0x1800691db  test    r9d, r9d
0x1800691de  jz      short loc_180069203
0x1800691e0  lea     r8, aFailureHomepro; "failure HomeProvider HomeProvider respo"...
0x1800691e7  jmp     short loc_18006922D
0x1800691e9  mov     r14b, dil
0x1800691ec  cmp     dword ptr [rbx], 2
0x1800691ef  jz      short loc_180069203
0x1800691f1  mov     eax, [rbx+58h]
0x1800691f4  mov     r9d, [rbx]
0x1800691f7  lea     r8, aInvalidWwaneve; "invalid WwanEventCodeHomeProvider event"...
0x1800691fe  jmp     loc_180069095
0x180069203  lea     r15, [rbx+5Ch]
0x180069207  test    r15, r15
0x18006920a  jnz     short loc_180069218
0x18006920c  lea     r8, aReceivedANullR; "received a null response"
0x180069213  jmp     loc_180068FBC
0x180069218  mov     r9d, [rbx+58h]
0x18006921c  mov     ebx, 44h ; 'D'
0x180069221  cmp     r9d, ebx
0x180069224  jnb     short loc_180069240
0x180069226  lea     r8, aReceivedARespo; "received a response with insufficient b"...
0x18006922d  xor     edx, edx; struct _GUID *
0x18006922f  lea     rcx, aCwwanuiccOnndi; "CWwanUicc::OnNdisNotification"
0x180069236  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18006923b  jmp     loc_18006A6D0
0x180069240  mov     [rbp+220h+Destination], di
0x180069247  xor     eax, eax
0x180069249  mov     [rbp+220h+var_F2], ax
0x180069250  xor     edx, edx; Val
0x180069252  lea     r8d, [rax+46h]; Size
0x180069256  lea     rcx, [rbp+220h+var_FE]; void *
0x18006925d  call    memset_0
0x180069262  lea     rcx, [r15+14h]
0x180069266  mov     eax, [r15+40h]
0x18006926a  mov     dword ptr [rsp+340h+var_310], eax
0x18006926e  mov     [rsp+340h+var_318], rcx
0x180069273  mov     eax, [r15+10h]
0x180069277  mov     dword ptr [rsp+340h+var_320], eax
0x18006927b  mov     r9, r15
0x18006927e  lea     r8, aHomeproviderId_0; " HomeProvider ID [%s] state %d Name [%s"...
0x180069285  xor     edx, edx; struct _GUID *
0x180069287  lea     rcx, aCwwanuiccOnndi; "CWwanUicc::OnNdisNotification"
0x18006928e  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180069293  mov     r9, rbx; SourceSize
0x180069296  mov     r8, r15; Source
0x180069299  mov     rdx, rbx; DestinationSize
0x18006929c  lea     rcx, [rbp+220h+Destination]; Destination
0x1800692a3  call    memcpy_s
0x1800692a8  mov     [rbp+220h+var_BC], edi
0x1800692ae  mov     r8b, r14b; bool
0x1800692b1  lea     rdx, [rbp+220h+Destination]; struct WWAN_PROVIDER_OBJECT *
0x1800692b8  mov     rcx, rsi; this
0x1800692bb  call    ?onHomeProvider@CWwanUicc@@AEAAXAEBUWWAN_PROVIDER_OBJECT@@_N@Z; CWwanUicc::onHomeProvider(WWAN_PROVIDER_OBJECT const &,bool)
0x1800692c0  jmp     loc_18006A6D0
0x1800692c5  cmp     dword ptr [rbx], 2
0x1800692c8  jz      short loc_1800692DD
0x1800692ca  xor     edi, edi
0x1800692cc  cmp     [rbx+20h], edi
0x1800692cf  jz      short loc_1800692DD
0x1800692d1  lea     r8, aErrorInReadyIn; "Error in Ready info received"
0x1800692d8  jmp     loc_180068FBC
0x1800692dd  lea     rdx, [rbx+5Ch]; struct _WWAN_READY_INFO *
0x1800692e1  mov     r14d, 1
0x1800692e7  mov     rcx, rsi; this
0x1800692ea  cmp     [rbx], r14d
0x1800692ed  jnz     short loc_1800692F5
0x1800692ef  mov     r8, [rbx+18h]
0x1800692f3  jmp     short loc_1800692F8
0x1800692f5  xor     r8d, r8d; void *
0x1800692f8  call    ?onReadyStateInfo@CWwanUicc@@AEAAXPEAU_WWAN_READY_INFO@@PEAX@Z; CWwanUicc::onReadyStateInfo(_WWAN_READY_INFO *,void *)
0x1800692fd  jmp     loc_18006A6D0
0x180069302  xor     edi, edi
0x180069304  cmp     [rdx+10h], edi
0x180069307  jnz     short loc_180069316
0x180069309  mov     rcx, rsi; this
0x18006930c  call    ?onSendApdu@CWwanUicc@@AEAAXPEBUWWAN_EVENT@@@Z; CWwanUicc::onSendApdu(WWAN_EVENT const *)
0x180069311  jmp     loc_18006A6D0
0x180069316  lea     r8, aErrorInApduRes; "Error in APDU response"
0x18006931d  jmp     loc_180068FBC
0x180069322  sub     ecx, 31h ; '1'
0x180069325  jz      loc_18006A6A5
0x18006932b  sub     ecx, 0Ah
0x18006932e  jz      loc_1800697A2
0x180069334  sub     ecx, 1
0x180069337  jz      short loc_180069378
0x180069339  sub     ecx, 3
0x18006933c  jz      short loc_18006936B
0x18006933e  sub     ecx, 7
0x180069341  jz      short loc_18006935E
0x180069343  sub     ecx, 2
0x180069346  jz      short loc_180069351
0x180069348  cmp     ecx, 1
0x18006934b  jnz     loc_18006A6D0
0x180069351  mov     rcx, rsi; this
0x180069354  call    ?onUiccAccessResponse@CWwanUicc@@AEAAXPEBUWWAN_EVENT@@@Z; CWwanUicc::onUiccAccessResponse(WWAN_EVENT const *)
0x180069359  jmp     loc_18006A6D0
  ... truncated ...
```
