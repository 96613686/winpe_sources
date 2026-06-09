# CBSSListManager::ReceiveBeaconOrProbe(_WDI_BSS_ENTRY_CONTAINER *,unsigned __int64,uchar,CBSSEntry * *)

- ea: `0x140017b50`
- end: `0x1400191e6`
- name: `?ReceiveBeaconOrProbe@CBSSListManager@@QEAAHPEAU_WDI_BSS_ENTRY_CONTAINER@@_KEPEAPEAVCBSSEntry@@@Z`
- size: `5782`
- prototype: `__int64 __fastcall(CBSSListManager *this, CBSSEntryFactory *p_m_ResolveListOpenEntries, struct _LIST_ENTRY *, unsigned __int8, struct CBSSEntry **)`
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x14000e838`

## callees

- `0x14000b43c`
- `0x140017a90`
- `0x140017b50`
- `0x1400191ec`
- `0x1400192c4`
- `0x140019574`
- `0x140019700`
- `0x140019b70`
- `0x140019c80`
- `0x140019e48`
- `0x140019ed8`
- `0x14001a60c`
- `0x140034e04`
- `0x140034ec4`
- `0x140040d20`
- `0x14004c5b4`
- `0x1400500c0`
- `0x140072bfc`
- `0x14007cf50`
- `0x140082d74`
- `0x140085f94`
- `0x140086bcc`
- `0x1400bae88`
- `0x1400bdfcc`
- `0x1400da4f0`
- `0x1400da680`
- `0x1400dac80`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140018c6a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018d10`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018fa0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018c6a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018d10`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018fa0`
- `ntoskrnl!ExAllocatePool2` at `0x140017df3`
- `ntoskrnl!ExAllocatePool2` at `0x140018196`
- `ntoskrnl!ExAllocatePool2` at `0x140018a73`
- `ntoskrnl!ExAllocatePool2` at `0x140018c1a`
- `ntoskrnl!ExAllocatePool2` at `0x140018cc2`
- `ntoskrnl!ExAllocatePool2` at `0x140017df3`
- `ntoskrnl!ExAllocatePool2` at `0x140018196`
- `ntoskrnl!ExAllocatePool2` at `0x140018a73`
- `ntoskrnl!ExAllocatePool2` at `0x140018c1a`
- `ntoskrnl!ExAllocatePool2` at `0x140018cc2`

## pseudocode

```c
__int64 __fastcall CBSSListManager::ReceiveBeaconOrProbe(
        CBSSListManager *this,
        CBSSEntryFactory *p_m_ResolveListOpenEntries,
        struct _LIST_ENTRY *a3,
        unsigned __int8 a4,
        struct CBSSEntry **a5)
{
  _WFC_PORT_TYPE m_PortType; // r15d
  char v6; // r13
  CBSSEntryFactory *v7; // rsi
  _WDI_BSS_ENTRY_CONTAINER::_WDI_BSS_ENTRY_CONTAINER_Optional Flink; // eax
  unsigned int v9; // r8d
  unsigned int v10; // eax
  unsigned __int8 *v11; // rdi
  unsigned int v12; // ebx
  __int64 v13; // rcx
  unsigned int v14; // edx
  size_t v15; // rcx
  __int64 v16; // rax
  enum CBSSEntryFactory::BSS_TYPE updated; // r12d
  int v18; // eax
  const unsigned __int8 *v19; // r14
  CBSSListManager *v20; // rdi
  char v21; // r12
  _LIST_ENTRY *p_m_BSSEntryList; // rsi
  _LIST_ENTRY *v23; // rbx
  CBSSEntryFactory *p_m_BSSEntryFactory; // rsi
  bool m_OWEAuthenticationSupported; // al
  struct CBSSEntry *v26; // rdi
  CBSSEntryFactory *v27; // rcx
  enum CBSSEntryFactory::BSS_TYPE BSSType; // eax
  CBSSEntryFactory *v29; // rcx
  CBSSEntry *v30; // rax
  CBSSEntry *v31; // rbx
  struct CBSSEntry *v32; // rbx
  unsigned int v34; // ecx
  __int64 v35; // rdi
  unsigned int v36; // ebx
  __int64 v37; // rax
  int v38; // eax
  unsigned int i; // ecx
  struct _WDI_BSS_ENTRY_CONTAINER *v40; // rbx
  CBSSListManager *v41; // rsi
  CBSSEntry *v42; // r10
  int v43; // eax
  int v44; // edx
  int v45; // r8d
  struct _LIST_ENTRY *v46; // rcx
  struct _LIST_ENTRY *v47; // rax
  const char *v48; // rcx
  CAdapter *m_pAdapter; // r15
  CBSSEntryFactory *v50; // rsi
  struct _LIST_ENTRY *v51; // r14
  _WDI_BAND_ID v52; // ecx
  unsigned int Blink_high; // ecx
  enum _WDI_BAND_ID v54; // ebx
  unsigned int v55; // edi
  struct CAdapterPropertyCache *v56; // rax
  _BOOL8 v57; // r9
  CBSSEntry *v58; // rax
  CBSSListManager *v59; // r10
  char v60; // di
  CBSSEntry *v61; // r9
  struct _LIST_ENTRY *v62; // rcx
  _CPP_LIST_ENTRY *p_m_BssListEntry; // rax
  struct _LIST_ENTRY *v64; // rdx
  struct _LIST_ENTRY *v65; // rcx
  struct _LIST_ENTRY *v66; // rdx
  __int64 v67; // rax
  int v68; // r8d
  __int64 v69; // rdi
  __int64 *v70; // rdx
  __int64 v71; // rax
  int v72; // ebx
  __int64 *v73; // rbx
  int v74; // r15d
  __int64 v75; // rdi
  __int64 v76; // rax
  int v77; // esi
  CBSSEntry *v78; // r10
  struct _LIST_ENTRY *v79; // rax
  char v80; // r11
  unsigned __int8 *v81; // r14
  _BYTE *v82; // rsi
  unsigned int v83; // r15d
  unsigned int v84; // ebx
  enum CBSSEntryFactory::BSS_TYPE v85; // edi
  int v86; // ecx
  unsigned int v87; // ecx
  _BYTE *k; // rdx
  int v89; // r8d
  __int64 v90; // rax
  int v91; // eax
  _WORD *v92; // r9
  unsigned int v93; // ecx
  unsigned int v94; // edx
  int v95; // edx
  int v96; // r10d
  unsigned int v97; // r8d
  CBSSEntryFactory::BSS_TYPE v98; // eax
  size_t Flink_low; // rbx
  struct _LIST_ENTRY *v100; // r12
  unsigned __int8 *pBuffer; // rsi
  size_t v102; // r14
  CBSSEntry *v103; // rdi
  struct _LIST_ENTRY *v104; // rax
  unsigned __int8 *v105; // r14
  unsigned int v106; // r15d
  _BYTE *v107; // rsi
  unsigned int v108; // edi
  enum CBSSEntryFactory::BSS_TYPE v109; // ebx
  int v110; // eax
  unsigned int v111; // ecx
  _BYTE *m; // rdx
  int v113; // r8d
  __int64 v114; // rax
  _WORD *v115; // r9
  unsigned int v116; // ecx
  unsigned int v117; // edx
  int v118; // edx
  int v119; // r10d
  unsigned int v120; // r8d
  struct COWETransitionModeBSSEntry *v121; // rax
  int v122; // eax
  int v123; // edx
  int v124; // r8d
  size_t v125; // rcx
  __int64 v126; // rax
  int v127; // r8d
  unsigned __int8 j; // cl
  unsigned __int8 *v129; // rcx
  bool v130; // zf
  __int64 v131; // rax
  struct DOT11_RNR_NEIGHBOR *Pool2; // rax
  struct DOT11_RNR_NEIGHBOR *v133; // rbx
  struct CBSSEntry *v134; // rsi
  int v135; // ecx
  __int64 v136; // rax
  struct DOT11_RNR_NEIGHBOR *v137; // rax
  struct DOT11_RNR_NEIGHBOR *v138; // rbx
  const char *v139; // rdx
  int v140; // [rsp+20h] [rbp-E0h]
  int v141; // [rsp+20h] [rbp-E0h]
  char v142; // [rsp+30h] [rbp-D0h]
  char v143; // [rsp+30h] [rbp-D0h]
  char v144; // [rsp+60h] [rbp-A0h]
  CBSSEntry *v145; // [rsp+68h] [rbp-98h]
  enum CBSSEntryFactory::BSS_TYPE v146; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int8 v147; // [rsp+74h] [rbp-8Ch]
  char v148; // [rsp+75h] [rbp-8Bh]
  bool v149; // [rsp+76h] [rbp-8Ah]
  unsigned __int8 v150; // [rsp+77h] [rbp-89h] BYREF
  int v151; // [rsp+78h] [rbp-88h]
  unsigned int v152; // [rsp+80h] [rbp-80h] BYREF
  enum CBSSEntryFactory::BSS_TYPE v153[2]; // [rsp+88h] [rbp-78h] BYREF
  CBSSListManager *v154; // [rsp+90h] [rbp-70h]
  CBSSEntryFactory *v155; // [rsp+98h] [rbp-68h]
  unsigned __int8 *v156; // [rsp+A0h] [rbp-60h] BYREF
  _WFC_PORT_TYPE v157; // [rsp+A8h] [rbp-58h]
  struct _LIST_ENTRY *Blink; // [rsp+B0h] [rbp-50h]
  struct CBSSEntry **v159; // [rsp+B8h] [rbp-48h]
  _OWORD v160[2]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v161; // [rsp+E0h] [rbp-20h] BYREF
  _OWORD v162[2]; // [rsp+E4h] [rbp-1Ch] BYREF
  unsigned __int8 v163[4]; // [rsp+108h] [rbp+8h] BYREF
  __int16 v164; // [rsp+10Ch] [rbp+Ch]

  m_PortType = this->m_PortType;
  v147 = a4;
  v149 = m_PortType == WfcPortTypeExtSTA;
  Blink = a3;
  v155 = p_m_ResolveListOpenEntries;
  v6 = 0;
  *(_DWORD *)v163 = 0;
  v164 = 0;
  v7 = p_m_ResolveListOpenEntries;
  Flink = (_WDI_BSS_ENTRY_CONTAINER::_WDI_BSS_ENTRY_CONTAINER_Optional)p_m_ResolveListOpenEntries->m_ResolveListOWEEntries.Flink;
  v154 = this;
  v159 = a5;
  v145 = 0;
  v157 = m_PortType;
  v148 = 0;
  v161 = 0;
  memset(v162, 0, sizeof(v162));
  if ( (*(_BYTE *)&Flink & 2) != 0 )
  {
    v9 = (unsigned int)p_m_ResolveListOpenEntries[1].m_ResolveListOWEEntries.Flink;
    if ( v9 < 0xC )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(p_m_ResolveListOpenEntries) = 2;
        WPP_RECORDER_SF_Dd(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)p_m_ResolveListOpenEntries,
          v9,
          10,
          (__int64)WPP_c61af74bc3a930f8b940b9c9c657a55c_Traceguids,
          v9,
          12);
      }
      goto LABEL_273;
    }
    v10 = v9 - 12;
    v11 = (unsigned __int8 *)&p_m_ResolveListOpenEntries[1].m_ResolveListOWEEntries.Blink->Blink + 4;
    v12 = 0;
    while ( v10 >= 2 )
    {
      v13 = v12;
      v10 -= 2;
      v12 += 2;
      v14 = v11[v13 + 1];
      if ( (_BYTE)v14 )
      {
        if ( v10 < v14 )
        {
          v130 = *(_QWORD *)&WPP_RECORDER_INITIALIZED == (_QWORD)&WPP_RECORDER_INITIALIZED;
LABEL_239:
          if ( !v130 )
          {
            LOBYTE(v14) = 2;
            WPP_RECORDER_SF_d(
              WPP_GLOBAL_Control->DeviceExtension,
              v14,
              v9,
              11,
              (__int64)WPP_c61af74bc3a930f8b940b9c9c657a55c_Traceguids,
              v9);
          }
          updated = BSS_TYPE_OWE_TRANSITION_MODE_OWE|BSS_TYPE_OWE_TRANSITION_MODE_OPEN|0x10000;
          v32 = 0;
          goto LABEL_48;
        }
        v10 -= v14;
        v12 += v14;
      }
    }
    v152 = v12;
    *(_QWORD *)v153 = v11;
    memset(v160, 0, 24);
    if ( (int)FindFirstP2PIE((unsigned __int8 **)v153, &v152) >= 0
      && FindAttributeInFragmentedP2PIEs(*(unsigned __int8 **)v153, v152, 3u, (struct _WFD_ATTRIBUTE_INFO *)v160) >= 0 )
    {
      a4 = 6;
      if ( WORD1(v160[0]) == 6 )
      {
        if ( GetAttributeBytes((struct _WFD_ATTRIBUTE_INFO *)v160, v163, 0, 6u, 0) >= 0 )
          v6 = 1;
        v148 = v6;
      }
    }
    v152 = v12 + 12;
    while ( v12 >= 2 )
    {
      v15 = v11[1];
      v16 = (unsigned int)(v15 + 2);
      if ( v12 < (unsigned int)v16 )
        break;
      if ( !*v11 )
      {
        p_m_ResolveListOpenEntries = (CBSSEntryFactory *)(v11 + 2);
        if ( v11 != (unsigned __int8 *)-2LL && (unsigned __int8)v15 <= 0x20u )
        {
          v161 = v11[1];
          memmove(v162, p_m_ResolveListOpenEntries, v15);
        }
        break;
      }
      v12 -= v16;
      v11 += v16;
    }
  }
  else
  {
    v152 = 0;
  }
  updated = BSS_TYPE_DEFAULT;
  v18 = (int)v7->m_ResolveListOWEEntries.Flink;
  v151 = 0;
  if ( (v18 & 1) != 0 )
  {
    v9 = (unsigned int)v7->m_ResolveListOpenEntries.Flink;
    v153[0] = 25;
    memset(v160, 0, 25);
    if ( v9 >= 0xC )
    {
      v34 = v9 - 12;
      v35 = (__int64)&v7->m_ResolveListOpenEntries.Blink->Blink + 4;
      v36 = 0;
      while ( v34 >= 2 )
      {
        v37 = v36;
        v34 -= 2;
        v36 += 2;
        v14 = *(unsigned __int8 *)(v37 + v35 + 1);
        if ( (_BYTE)v14 )
        {
          if ( v34 < v14 )
          {
            v130 = *(_QWORD *)&WPP_RECORDER_INITIALIZED == (_QWORD)&WPP_RECORDER_INITIALIZED;
            goto LABEL_239;
          }
          v34 -= v14;
          v36 += v14;
        }
      }
      v38 = WFDGetDeviceInfo((unsigned __int8 *)v35);
      if ( (int)(v38 + 0x80000000) < 0 || v38 == -1071448042 )
      {
        v6 = 1;
        *(_DWORD *)v163 = v160[0];
        v164 = WORD2(v160[0]);
        v148 = 1;
      }
      LODWORD(p_m_ResolveListOpenEntries) = v161;
      LOWORD(v151) = v36 + 12;
      if ( v161 )
      {
        for ( i = 0; ; ++i )
        {
          if ( i >= v161 )
            goto LABEL_211;
          if ( *((_BYTE *)v162 + i) )
            break;
        }
      }
      else
      {
LABEL_211:
        while ( v36 >= 2 )
        {
          v125 = *(unsigned __int8 *)(v35 + 1);
          v126 = (unsigned int)(v125 + 2);
          if ( v36 < (unsigned int)v126 )
            break;
          if ( !*(_BYTE *)v35 )
          {
            p_m_ResolveListOpenEntries = (CBSSEntryFactory *)(v35 + 2);
            if ( v35 != -2 && (unsigned __int8)v125 <= 0x20u )
            {
              v161 = *(unsigned __int8 *)(v35 + 1);
              memmove(v162, p_m_ResolveListOpenEntries, v125);
            }
            break;
          }
          v36 -= v126;
          v35 += v126;
        }
      }
      updated = BSS_TYPE_DEFAULT;
      goto LABEL_18;
    }
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(p_m_ResolveListOpenEntries) = 2;
      WPP_RECORDER_SF_Dd(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)p_m_ResolveListOpenEntries,
        v9,
        10,
        (__int64)WPP_c61af74bc3a930f8b940b9c9c657a55c_Traceguids,
        v9,
        12);
      updated = -1073676267;
      v32 = 0;
      goto LABEL_48;
    }
LABEL_273:
    updated = -1073676267;
    v32 = 0;
    goto LABEL_48;
  }
LABEL_18:
  v19 = (const unsigned __int8 *)&v7->m_ResolveListOWEEntries.Flink + 4;
  if ( m_PortType == WfcPortTypeExtSTA )
  {
    v20 = v154;
    if ( v154->m_IHVMaintainedExtSTABSSListCache )
    {
      if ( ((__int64)v7->m_ResolveListOWEEntries.Flink & 8) == 0 )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(p_m_ResolveListOpenEntries) = 2;
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            (_DWORD)p_m_ResolveListOpenEntries,
            1,
            151,
            (__int64)&WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids);
        }
        updated = -1073676267;
        goto LABEL_47;
      }
      Blink = v7[2].m_ResolveListOpenEntries.Blink;
    }
  }
  else
  {
    if ( !v6 )
    {
      v127 = 0xFFFF;
      for ( j = 0; ; ++j )
      {
        if ( j >= 5u )
          goto LABEL_223;
        p_m_ResolveListOpenEntries = (CBSSEntryFactory *)v154->m_pAdapter->m_pPortList[j];
        if ( p_m_ResolveListOpenEntries )
        {
          if ( LODWORD(p_m_ResolveListOpenEntries[2].m_ResolveListOpenEntries.Blink) == v154->m_PortType )
            break;
        }
      }
      v127 = WORD2(p_m_ResolveListOpenEntries[2].m_ResolveListOpenEntries.Flink);
LABEL_223:
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        LOBYTE(p_m_ResolveListOpenEntries) = 5;
        WPP_RECORDER_SF__MAC_dd(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)p_m_ResolveListOpenEntries,
          v127,
          152,
          v140,
          (__int64)&v7->m_ResolveListOWEEntries.Flink + 4,
          v127,
          v154->m_PortType);
      }
      goto LABEL_47;
    }
    v20 = v154;
  }
  v21 = 0;
  v144 = 0;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(p_m_ResolveListOpenEntries) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)p_m_ResolveListOpenEntries,
      1,
      97,
      (__int64)&WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids);
  }
  p_m_BSSEntryList = &v20->m_BSSEntryList;
  v23 = v20->m_BSSEntryList.Flink;
  if ( v23 == &v20->m_BSSEntryList )
  {
    p_m_BSSEntryFactory = &v20->m_BSSEntryFactory;
    goto LABEL_26;
  }
  do
  {
    if ( v23 )
      v26 = (struct CBSSEntry *)v23[1].Flink;
    else
      v26 = 0;
    if ( v26->IsMatch(v26, (const unsigned __int8 (*)[6])v19, (_DOT11_SSID *const)&v161, v149) )
    {
      p_m_BSSEntryFactory = &v154->m_BSSEntryFactory;
      m_OWEAuthenticationSupported = v154->m_BSSEntryFactory.m_OWEAuthenticationSupported;
      if ( !v26 )
        goto LABEL_33;
      if ( !m_OWEAuthenticationSupported )
        goto LABEL_69;
      v40 = (struct _WDI_BSS_ENTRY_CONTAINER *)v155;
      v156 = 0;
      v150 = 0;
      v146 = BSS_TYPE_DEFAULT;
      if ( ((__int64)v155->m_ResolveListOWEEntries.Flink & 1) != 0 )
      {
        p_m_ResolveListOpenEntries = (CBSSEntryFactory *)&v155->m_ResolveListOpenEntries;
      }
      else
      {
        if ( ((__int64)v155->m_ResolveListOWEEntries.Flink & 2) == 0 )
          goto LABEL_284;
        p_m_ResolveListOpenEntries = v155 + 1;
      }
      if ( p_m_ResolveListOpenEntries )
      {
        if ( !CBSSEntryFactory::GetBSSType(
                v27,
                (unsigned __int8 *)p_m_ResolveListOpenEntries->m_ResolveListOWEEntries.Blink,
                (unsigned int)p_m_ResolveListOpenEntries->m_ResolveListOWEEntries.Flink,
                &v156,
                &v150,
                &v146) )
        {
          v98 = v26->GetBSSType(v26);
          if ( v98 != v146 )
          {
            *(_QWORD *)v153 = 0;
            v43 = CBSSEntryFactory::Rebuild(p_m_BSSEntryFactory, v26, v40, v147, (struct CBSSEntry **)v153);
            updated = v43;
            if ( v43 || (v31 = *(CBSSEntry **)v153) == 0 )
            {
              if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v44) = 2;
                WPP_RECORDER_SF__MAC_d(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v44,
                  v45,
                  154,
                  (__int64)&WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids,
                  (__int64)v19,
                  v43);
              }
              goto LABEL_46;
            }
            v46 = v26->m_BssListEntry.ListEntry.Flink;
            if ( (_CPP_LIST_ENTRY *)v46->Blink != &v26->m_BssListEntry )
              goto LABEL_198;
            v47 = v26->m_BssListEntry.ListEntry.Blink;
            if ( (_CPP_LIST_ENTRY *)v47->Flink != &v26->m_BssListEntry )
              goto LABEL_198;
            v41 = v154;
            v47->Flink = v46;
            v46->Blink = v47;
            --v41->m_CurrentBSSEntryCount;
            ++v41->m_LastBSSListChangedCounter;
            v41->m_LastInternalBSSListUpdateTime = MEMORY[0xFFFFF78000000014];
            ((void (__fastcall *)(struct CBSSEntry *, __int64))v26->~CBSSEntry)(v26, 1);
            v42 = v31;
            if ( !v31 )
              NT_ASSERT("pBssEntry");
LABEL_75:
            v145 = v31;
            v21 = 1;
            v144 = 1;
LABEL_76:
            if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              v48 = "NEW";
              if ( !v21 )
                v48 = "EXISTING";
              WPP_RECORDER_SF_s_MAC__SSID_D(
                WPP_GLOBAL_Control->DeviceExtension,
                (unsigned int)"EXISTING",
                (_DWORD)a3,
                a4,
                v140,
                (__int64)v48,
                (__int64)v19,
                (__int64)&v161,
                v149);
              v42 = v145;
            }
            m_pAdapter = v41->m_pAdapter;
            v50 = v155;
            v51 = Blink;
            v146 = BSS_TYPE_DEFAULT;
            v52 = *((_DWORD *)&v155[1].m_OWEAuthenticationSupported + 1);
            v42->m_BssChannelInfo.Channel = *(_DWORD *)&v155[1].m_OWEAuthenticationSupported;
            v42->m_BssChannelInfo.BandId = v52;
            Blink_high = HIDWORD(v50[1].m_ResolveListOpenEntries.Blink);
            v42->m_SignalInfo.Rssi = (int)v50[1].m_ResolveListOpenEntries.Blink;
            v42->m_SignalInfo.LinkQuality = Blink_high;
            if ( ((__int64)v50->m_ResolveListOWEEntries.Flink & 1) != 0 )
            {
              updated = ((unsigned int (__fastcall *)(CBSSEntry *, __int64, struct _LIST_ENTRY *, CAdapter *))v42->SetBeaconOrProbeResponse)(
                          v42,
                          1,
                          v51,
                          m_pAdapter);
              if ( updated )
                goto LABEL_91;
              v42 = v145;
            }
            else
            {
              updated = v146;
            }
            if ( ((__int64)v50->m_ResolveListOWEEntries.Flink & 2) == 0
              || (updated = ((unsigned int (__fastcall *)(CBSSEntry *, _QWORD, struct _LIST_ENTRY *, CAdapter *))v42->SetBeaconOrProbeResponse)(
                              v42,
                              0,
                              v51,
                              m_pAdapter)) == BSS_TYPE_DEFAULT )
            {
              if ( ((__int64)v50->m_ResolveListOWEEntries.Flink & 4) == 0 )
              {
LABEL_85:
                v54 = *((_DWORD *)&v50[1].m_OWEAuthenticationSupported + 1);
                v55 = *(_DWORD *)&v50[1].m_OWEAuthenticationSupported;
                v56 = m_pAdapter->GetAdapterPropertyCache(&m_pAdapter->IPropertyCacheDirectory);
                CBSSEntry::SetChannelAndPhyID(v145, v149, v56, v55, v54);
                CBSSEntry::UpdateShortSsid(v145);
                v59 = v154;
                if ( v154->m_BackgroundDiscoveryEnabled )
                {
                  updated = (unsigned int)CBSSEntry::UpdateBackgroundDeviceIndicatedByDriver(v145, v154->m_pAdapter);
                  if ( updated )
                    goto LABEL_313;
                  v59 = v154;
                }
                v60 = v144;
                if ( v144 )
                {
                  LOBYTE(v57) = 1;
                  v32 = v145;
                  v122 = v59->AddBSSEntry(v59, v145, 0, v57);
                  updated = v122;
                  if ( v122 )
                  {
                    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                    {
                      LOBYTE(v123) = 2;
                      WPP_RECORDER_SF__MAC_d(
                        WPP_GLOBAL_Control->DeviceExtension,
                        v123,
                        v124,
                        156,
                        (__int64)&WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids,
                        (__int64)v145->m_BssID,
                        v122);
                    }
                    goto LABEL_229;
                  }
                  v59 = v154;
                  v61 = v145;
                  ++v154->m_DebugScanNewBSSEntryCount;
LABEL_98:
                  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
                    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
                  {
                    v139 = "Added NEW";
                    if ( !v144 )
                      v139 = "Refreshed EXISTING";
                    WPP_RECORDER_SF_sq_MAC_dddD(
                      WPP_GLOBAL_Control->DeviceExtension,
                      (_DWORD)v139,
                      (_DWORD)v61 + 444,
                      (_DWORD)v61,
                      v141,
                      (__int64)v139,
                      (char)v61,
                      (__int64)v61->m_BssID,
                      v61->m_BssChannelInfo.BandId,
                      v61->m_BssChannelInfo.Channel,
                      v61->m_SignalInfo.LinkQuality,
                      v61->m_ConnectionCapabilityFlags);
                    v59 = v154;
                  }
                  if ( v157 != WfcPortTypeExtSTA )
                    goto LABEL_143;
                  v67 = (__int64)v59->m_pAdapter->GetAdapterPropertyCache(&v59->m_pAdapter->IPropertyCacheDirectory);
                  v69 = 0;
                  v70 = WPP_cc661508417c3cac5f0bc601c5c9eca5_Traceguids;
                  if ( *(_DWORD *)(v67 + 8) <= 2u )
                  {
                    v72 = -1073741811;
                    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
                    {
LABEL_142:
                      v60 = v144;
LABEL_143:
                      if ( !v154->m_IHVMaintainedExtSTABSSListCache || v60 )
                        v154->m_LastInternalBSSListUpdateTime = MEMORY[0xFFFFF78000000014];
                      goto LABEL_46;
                    }
                    LOBYTE(v70) = 2;
                    WPP_RECORDER_SF_d(
                      WPP_GLOBAL_Control->DeviceExtension,
                      (_DWORD)v70,
                      v68,
                      19,
                      (__int64)WPP_cc661508417c3cac5f0bc601c5c9eca5_Traceguids,
                      2);
                    v70 = WPP_cc661508417c3cac5f0bc601c5c9eca5_Traceguids;
                  }
                  else
                  {
                    v71 = *(_QWORD *)(v67 + 16);
                    if ( *(_BYTE *)(v71 + 120) )
                    {
                      v69 = v71 + 112;
LABEL_105:
                      v72 = 0;
                      goto LABEL_106;
                    }
                    if ( *(_QWORD *)(v71 + 160) )
                    {
                      v69 = *(_QWORD *)(v71 + 160);
                      goto LABEL_105;
                    }
                    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                    {
                      LOBYTE(v70) = 4;
                      WPP_RECORDER_SF_d(
                        WPP_GLOBAL_Control->DeviceExtension,
                        (_DWORD)v70,
                        v68,
                        20,
                        (__int64)WPP_cc661508417c3cac5f0bc601c5c9eca5_Traceguids,
                        2);
                      v70 = WPP_cc661508417c3cac5f0bc601c5c9eca5_Traceguids;
                    }
                    v72 = -1073741436;
                  }
LABEL_106:
                  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
                    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
                  {
                    LOBYTE(v70) = 5;
                    WPP_RECORDER_SF_D(
                      WPP_GLOBAL_Control->DeviceExtension,
                      (_DWORD)v70,
                      1,
                      22,
                      (__int64)WPP_cc661508417c3cac5f0bc601c5c9eca5_Traceguids,
                      v72);
                    v70 = WPP_cc661508417c3cac5f0bc601c5c9eca5_Traceguids;
                  }
                  if ( v72 )
                  {
                    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                    {
                      LOBYTE(v70) = 2;
                      WPP_RECORDER_SF_D(
                        WPP_GLOBAL_Control->DeviceExtension,
                        (_DWORD)v70,
                        1,
                        120,
                        (__int64)WPP_cc661508417c3cac5f0bc601c5c9eca5_Traceguids,
                        v72);
                    }
                  }
                  else
                  {
                    v73 = *(__int64 **)(v69 + 16);
                    v74 = v151;
                    while ( v73 )
                    {
                      v75 = 0;
                      if ( *((_DWORD *)v73 + 2) )
                      {
                        v76 = v73[2];
                        if ( *(_BYTE *)(v76 + 8) || (v76 = *(_QWORD *)(v76 + 48)) != 0 )
                        {
                          v77 = 0;
                          v75 = v76;
                        }
                        else
                        {
                          if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                          {
                            LOBYTE(v70) = 4;
                            WPP_RECORDER_SF_d(
                              WPP_GLOBAL_Control->DeviceExtension,
                              (_DWORD)v70,
                              v68,
                              20,
                              (__int64)WPP_cc661508417c3cac5f0bc601c5c9eca5_Traceguids,
                              0);
                          }
                          v77 = -1073741436;
                        }
                      }
                      else
                      {
                        v77 = -1073741811;
                        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
                          goto LABEL_142;
                        LOBYTE(v70) = 2;
                        WPP_RECORDER_SF_d(
                          WPP_GLOBAL_Control->DeviceExtension,
                          (_DWORD)v70,
                          v68,
                          19,
                          (__int64)WPP_cc661508417c3cac5f0bc601c5c9eca5_Traceguids,
                          0);
                      }
                      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
                        && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
                      {
                        LOBYTE(v70) = 5;
                        WPP_RECORDER_SF_D(
                          WPP_GLOBAL_Control->DeviceExtension,
                          (_DWORD)v70,
                          1,
                          22,
                          (__int64)WPP_cc661508417c3cac5f0bc601c5c9eca5_Traceguids,
                          v77);
                      }
                      if ( v77 )
                      {
                        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                        {
                          LOBYTE(v70) = 2;
                          WPP_RECORDER_SF_D(
                            WPP_GLOBAL_Control->DeviceExtension,
                            (_DWORD)v70,
                            1,
                            121,
                            (__int64)WPP_cc661508417c3cac5f0bc601c5c9eca5_Traceguids,
                            v77);
                        }
                        goto LABEL_142;
                      }
                      v78 = v145;
                      if ( *(_DWORD *)(v75 + 16) == 5 )
                      {
                        v151 = v74;
                        if ( ((__int64)v155->m_ResolveListOWEEntries.Flink & 2) != 0 )
                        {
                          v79 = v155[1].m_ResolveListOWEEntries.Blink;
                          if ( v79 )
                          {
                            if ( (unsigned __int16)v152 > 0xCu )
                            {
                              v80 = v144;
                              v81 = (unsigned __int8 *)&v79->Blink + 4;
                              v82 = (char *)&v79->Blink + 4;
                              v83 = (unsigned __int16)v152 - 12;
                              v84 = v83;
                              v85 = BSS_TYPE_DEFAULT;
LABEL_130:
                              while ( 1 )
                              {
                                v86 = 0;
                                if ( !v84 )
                                  break;
                                v87 = v84;
                                for ( k = v82; ; k += v90 )
                                {
                                  if ( v87 < 2
                                    || (v89 = (unsigned __int8)k[1],
                                        v90 = (unsigned int)(v89 + 2),
                                        v87 < (unsigned int)v90) )
                                  {
                                    v86 = -1073741823;
                                    goto LABEL_138;
                                  }
                                  if ( *k == 0xC9 )
                                    break;
                                  v87 -= v90;
                                }
                                v92 = k + 2;
                                v145 = v78;
                                v144 = v80;
                                v93 = (unsigned __int8)k[1];
                                v94 = v89 + (_DWORD)k + 2 - (_DWORD)v82;
                                if ( v84 < v94 )
                                {
                                  v86 = -1073676267;
                                  break;
                                }
                                v82 += v94;
                                v84 -= v94;
                                while ( 1 )
                                {
                                  v78 = v145;
                                  if ( v93 <= 4 )
                                    break;
                                  v95 = (unsigned __int8)*v92 >> 4;
                                  v96 = HIBYTE(*v92);
                                  v97 = v96 * (v95 + 1) + 4;
                                  if ( v93 < v97 )
                                  {
                                    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                                    {
                                      v142 = v96 * (v95 + 1) + 4;
                                      LOBYTE(v95) = 2;
                                      WPP_RECORDER_SF_dddd(
                                        WPP_GLOBAL_Control->DeviceExtension,
                                        v95,
                                        v97,
                                        141,
                                        (__int64)&WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids,
                                        v93,
                                        v142,
                                        (unsigned __int8)*v92 >> 4,
                                        v96);
                                      v80 = v144;
                                    }
                                    v78 = v145;
                                    goto LABEL_130;
                                  }
                                  v85 += v95 + 1;
                                  v92 = (_WORD *)((char *)v92 + v97);
                                  v93 -= v97;
                                }
                              }
LABEL_138:
                              v91 = 0;
                              v153[0] = v85;
                              if ( v85 == BSS_TYPE_DEFAULT )
                                v91 = v86;
                              if ( !v91 && v85 )
                              {
                                v131 = 20LL * (unsigned int)v85;
                                if ( !is_mul_ok((unsigned int)v85, 0x14u) )
                                  v131 = -1;
                                Pool2 = (struct DOT11_RNR_NEIGHBOR *)ExAllocatePool2(64, v131, 1198089303);
                                v133 = Pool2;
                                if ( Pool2 )
                                {
                                  if ( !(unsigned int)Dot11GetRnrInfo(v81, v83, (unsigned int *)v153, Pool2) && v153[0] )
                                    CBSSListManager::AddNeighborAPsFromRnrInfo(v154, v145, v153[0], v133);
                                  ExFreePoolWithTag(v133, 0x47696457u);
                                }
                              }
                            }
                          }
                        }
                        if ( ((__int64)v155->m_ResolveListOWEEntries.Flink & 1) != 0 )
                        {
                          v104 = v155->m_ResolveListOpenEntries.Blink;
                          if ( v104 )
                          {
                            if ( (unsigned __int16)v151 > 0xCu )
                            {
                              v105 = (unsigned __int8 *)&v104->Blink + 4;
                              v106 = (unsigned __int16)v151 - 12;
                              v107 = (char *)&v104->Blink + 4;
                              v108 = v106;
                              v109 = BSS_TYPE_DEFAULT;
LABEL_180:
                              while ( 1 )
                              {
                                v110 = 0;
                                if ( !v108 )
                                  break;
                                v111 = v108;
                                for ( m = v107; ; m += v114 )
                                {
                                  if ( v111 < 2
                                    || (v113 = (unsigned __int8)m[1],
                                        v114 = (unsigned int)(v113 + 2),
                                        v111 < (unsigned int)v114) )
                                  {
                                    v110 = -1073741823;
                                    goto LABEL_256;
                                  }
                                  if ( *m == 0xC9 )
                                    break;
                                  v111 -= v114;
                                }
                                v115 = m + 2;
                                v116 = (unsigned __int8)m[1];
                                v117 = v113 + (_DWORD)m + 2 - (_DWORD)v107;
                                if ( v108 < v117 )
                                {
                                  v134 = v145;
                                  v110 = -1073676267;
                                  v60 = v144;
                                  goto LABEL_257;
                                }
                                v107 += v117;
                                v108 -= v117;
                                while ( v116 > 4 )
                                {
                                  v118 = (unsigned __int8)*v115 >> 4;
                                  v119 = HIBYTE(*v115);
                                  v120 = v119 * (v118 + 1) + 4;
                                  if ( v116 < v120 )
                                  {
                                    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                                    {
                                      v143 = v119 * (v118 + 1) + 4;
                                      LOBYTE(v118) = 2;
                                      WPP_RECORDER_SF_dddd(
                                        WPP_GLOBAL_Control->DeviceExtension,
                                        v118,
                                        v120,
                                        141,
                                        (__int64)&WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids,
                                        v116,
                                        v143,
                                        (unsigned __int8)*v115 >> 4,
                                        v119);
                                    }
                                    goto LABEL_180;
                                  }
                                  v109 += v118 + 1;
                                  v115 = (_WORD *)((char *)v115 + v120);
                                  v116 -= v120;
                                }
                              }
LABEL_256:
                              v134 = v145;
                              v60 = v144;
LABEL_257:
                              v135 = 0;
                              v153[0] = v109;
                              if ( v109 == BSS_TYPE_DEFAULT )
                                v135 = v110;
                              if ( !v135 && v109 )
                              {
                                v136 = 20LL * (unsigned int)v109;
                                if ( !is_mul_ok((unsigned int)v109, 0x14u) )
                                  v136 = -1;
                                v137 = (struct DOT11_RNR_NEIGHBOR *)ExAllocatePool2(64, v136, 1198089303);
                                v138 = v137;
                                if ( v137 )
                                {
                                  if ( !(unsigned int)Dot11GetRnrInfo(v105, v106, (unsigned int *)v153, v137) && v153[0] )
                                    CBSSListManager::AddNeighborAPsFromRnrInfo(v154, v134, v153[0], v138);
                                  ExFreePoolWithTag(v138, 0x47696457u);
                                }
                              }
                              goto LABEL_143;
                            }
                          }
                        }
                        goto LABEL_142;
                      }
                      v70 = WPP_cc661508417c3cac5f0bc601c5c9eca5_Traceguids;
                      v73 = (__int64 *)*v73;
                    }
                  }
                  goto LABEL_142;
                }
                v61 = v145;
                v62 = v145->m_BssListEntry.ListEntry.Flink;
                p_m_BssListEntry = &v145->m_BssListEntry;
                if ( (_CPP_LIST_ENTRY *)v62->Blink == &v145->m_BssListEntry )
                {
                  v64 = v145->m_BssListEntry.ListEntry.Blink;
                  if ( (_CPP_LIST_ENTRY *)v64->Flink == p_m_BssListEntry )
                  {
                    v64->Flink = v62;
                    v62->Blink = v64;
                    v65 = &v59->m_BSSEntryList;
                    v66 = v59->m_BSSEntryList.Flink;
                    if ( v66->Blink == &v59->m_BSSEntryList )
                    {
                      p_m_BssListEntry->ListEntry.Flink = v66;
                      v145->m_BssListEntry.ListEntry.Blink = v65;
                      v66->Blink = &p_m_BssListEntry->ListEntry;
                      v65->Flink = &p_m_BssListEntry->ListEntry;
                      goto LABEL_98;
                    }
                  }
                }
LABEL_198:
                __fastfail(3u);
              }
              Flink_low = LOWORD(v50[2].m_ResolveListOWEEntries.Flink);
              v100 = v50[2].m_ResolveListOWEEntries.Blink;
              v146 = BSS_TYPE_DEFAULT;
              if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
                && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
              {
                LOBYTE(p_m_ResolveListOpenEntries) = 5;
                WPP_RECORDER_SF_(
                  WPP_GLOBAL_Control->DeviceExtension,
                  (_DWORD)p_m_ResolveListOpenEntries,
                  1,
                  36,
                  (__int64)&WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids);
              }
              if ( !(_WORD)Flink_low )
              {
                v32 = v145;
                updated = BSS_TYPE_DEFAULT;
                v145->m_DeviceSpecificContext.dataLength = 0;
                goto LABEL_163;
              }
              pBuffer = v145->m_DeviceSpecificContext.pBuffer;
              if ( pBuffer && v145->m_DeviceSpecificContext.bufferCapacity >= (unsigned __int16)Flink_low )
              {
                v102 = Flink_low;
                v103 = v145;
              }
              else
              {
                v102 = Flink_low;
                pBuffer = (unsigned __int8 *)ExAllocatePool2(64, Flink_low, 1198089303);
                if ( !pBuffer )
                {
                  updated = -1073741670;
                  goto LABEL_162;
                }
                v103 = v145;
                v129 = v145->m_DeviceSpecificContext.pBuffer;
                if ( v129 )
                  ExFreePoolWithTag(v129, 0x47696457u);
                v145->m_DeviceSpecificContext.pBuffer = pBuffer;
                v145->m_DeviceSpecificContext.bufferCapacity = Flink_low;
              }
              memmove(pBuffer, v100, v102);
              updated = v146;
              v103->m_DeviceSpecificContext.dataLength = Flink_low;
LABEL_162:
              v32 = v145;
              v50 = v155;
LABEL_163:
              if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
                && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
              {
                LOBYTE(p_m_ResolveListOpenEntries) = 5;
                WPP_RECORDER_SF_D(
                  WPP_GLOBAL_Control->DeviceExtension,
                  (_DWORD)p_m_ResolveListOpenEntries,
                  1,
                  37,
                  (__int64)&WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids,
                  updated);
              }
              if ( updated )
                goto LABEL_314;
              goto LABEL_85;
            }
LABEL_91:
            v32 = v145;
            goto LABEL_314;
          }
        }
LABEL_69:
        v41 = v154;
        v42 = v26;
        v145 = v26;
        goto LABEL_76;
      }
LABEL_284:
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(p_m_ResolveListOpenEntries) = 2;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)p_m_ResolveListOpenEntries,
          1,
          253,
          (__int64)&WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids);
      }
      goto LABEL_69;
    }
    v23 = v23->Flink;
  }
  while ( v23 != p_m_BSSEntryList );
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(p_m_ResolveListOpenEntries) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)p_m_ResolveListOpenEntries,
      1,
      99,
      (__int64)&WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids,
      0);
  }
  p_m_BSSEntryFactory = &v154->m_BSSEntryFactory;
LABEL_26:
  m_OWEAuthenticationSupported = p_m_BSSEntryFactory->m_OWEAuthenticationSupported;
LABEL_33:
  updated = BSS_TYPE_DEFAULT;
  v156 = 0;
  v150 = 0;
  v153[0] = BSS_TYPE_DEFAULT;
  if ( !m_OWEAuthenticationSupported )
  {
    v58 = (CBSSEntry *)ExAllocatePool2(64, 800, 1198089303);
    if ( v58 )
      v31 = CBSSEntry::CBSSEntry(v58, (const unsigned __int8 (*)[6])v19, v147);
    else
      v31 = 0;
    if ( !v31 )
      updated = -1073741670;
    goto LABEL_43;
  }
  if ( ((__int64)v155->m_ResolveListOWEEntries.Flink & 1) == 0 )
  {
    if ( ((__int64)v155->m_ResolveListOWEEntries.Flink & 2) != 0 )
    {
      p_m_ResolveListOpenEntries = v155 + 1;
      goto LABEL_37;
    }
    goto LABEL_288;
  }
  p_m_ResolveListOpenEntries = (CBSSEntryFactory *)&v155->m_ResolveListOpenEntries;
LABEL_37:
  if ( !p_m_ResolveListOpenEntries )
  {
LABEL_288:
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(p_m_ResolveListOpenEntries) = 2;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)p_m_ResolveListOpenEntries,
        1,
        253,
        (__int64)&WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids);
    }
    updated = -1073676267;
    goto LABEL_292;
  }
  BSSType = CBSSEntryFactory::GetBSSType(
              v155,
              (unsigned __int8 *)p_m_ResolveListOpenEntries->m_ResolveListOWEEntries.Blink,
              (unsigned int)p_m_ResolveListOpenEntries->m_ResolveListOWEEntries.Flink,
              &v156,
              &v150,
              v153);
  v146 = BSSType;
  if ( BSSType )
  {
    updated = BSSType;
LABEL_292:
    v31 = 0;
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(p_m_ResolveListOpenEntries) = 2;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)p_m_ResolveListOpenEntries,
        1,
        260,
        (__int64)&WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids);
    }
    goto LABEL_43;
  }
  if ( v153[0] )
  {
    v121 = CBSSEntryFactory::BuildTransitionModeBSSEntry(
             v29,
             (const unsigned __int8 (*)[6])v19,
             v147 != 0,
             v153[0],
             v156);
    v31 = v121;
    if ( v121 )
    {
      CBSSEntryFactory::ResolveOrAddToResolveList(p_m_BSSEntryFactory, v121);
LABEL_42:
      updated = v146;
    }
    else
    {
      updated = -1073741670;
    }
  }
  else
  {
    v30 = (CBSSEntry *)ExAllocatePool2(64, 800, 1198089303);
    if ( v30 )
    {
      v31 = CBSSEntry::CBSSEntry(v30, (const unsigned __int8 (*)[6])v19, v147);
      if ( v31 )
        goto LABEL_42;
    }
    else
    {
      v31 = 0;
    }
    updated = -1073741670;
  }
LABEL_43:
  if ( updated == BSS_TYPE_DEFAULT && v31 )
  {
    v41 = v154;
    v42 = v31;
    goto LABEL_75;
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(p_m_ResolveListOpenEntries) = 2;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)p_m_ResolveListOpenEntries,
      1,
      153,
      (__int64)&WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids,
      updated);
  }
LABEL_46:
  if ( updated == BSS_TYPE_DEFAULT )
  {
LABEL_47:
    v32 = v145;
    goto LABEL_48;
  }
LABEL_313:
  v32 = v145;
LABEL_314:
  v60 = v144;
LABEL_229:
  if ( v32 && v60 )
  {
    ((void (__fastcall *)(CBSSEntry *, __int64))v145->~CBSSEntry)(v145, 1);
    v32 = 0;
  }
LABEL_48:
  *v159 = v32;
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x140017b50  push    rbp
0x140017b52  push    rbx
0x140017b53  push    rsi
0x140017b54  push    rdi
0x140017b55  push    r12
0x140017b57  push    r13
0x140017b59  push    r14
0x140017b5b  push    r15
0x140017b5d  lea     rbp, [rsp-28h]
0x140017b62  sub     rsp, 128h
0x140017b69  mov     rax, cs:__security_cookie
0x140017b70  xor     rax, rsp
0x140017b73  mov     [rbp+60h+var_50], rax
0x140017b77  mov     r15d, [rcx+20h]
0x140017b7b  xor     r14d, r14d
0x140017b7e  mov     rbx, [rbp+60h+arg_20]
0x140017b85  cmp     r15d, 1
0x140017b89  xorps   xmm0, xmm0
0x140017b8c  mov     [rsp+160h+var_EC], r9b
0x140017b91  setz    [rsp+160h+var_EA]
0x140017b96  mov     [rbp+60h+var_B0], r8
0x140017b9a  xor     eax, eax
0x140017b9c  mov     [rbp+60h+var_C8], rdx
0x140017ba0  xor     r13b, r13b
0x140017ba3  mov     dword ptr [rbp+60h+var_58], eax
0x140017ba6  mov     [rbp+60h+var_54], ax
0x140017baa  mov     rsi, rdx
0x140017bad  mov     eax, [rdx]
0x140017baf  mov     [rbp+60h+var_D0], rcx
0x140017bb3  mov     [rbp+60h+var_A8], rbx
0x140017bb7  mov     [rsp+160h+var_F8], r14
0x140017bbc  mov     [rbp+60h+var_B8], r15d
0x140017bc0  mov     [rsp+160h+var_EB], r13b
0x140017bc5  mov     [rbp+60h+var_80], r14d
0x140017bc9  movups  [rbp+60h+var_7C], xmm0
0x140017bcd  movups  [rbp+60h+var_6C], xmm0
0x140017bd1  test    al, 2
0x140017bd3  jz      loc_140018E01
0x140017bd9  mov     r8d, [rdx+28h]
0x140017bdd  cmp     r8d, 0Ch
0x140017be1  jb      loc_140018D81
0x140017be7  mov     rdi, [rdx+30h]
0x140017beb  lea     eax, [r8-0Ch]
0x140017bef  add     rdi, 0Ch
0x140017bf3  mov     ebx, r14d
0x140017bf6  cmp     eax, 2
0x140017bf9  jb      short loc_140017C1A
0x140017bfb  mov     ecx, ebx
0x140017bfd  add     eax, 0FFFFFFFEh
0x140017c00  add     ebx, 2
0x140017c03  movzx   edx, byte ptr [rcx+rdi+1]
0x140017c08  test    dl, dl
0x140017c0a  jz      short loc_140017BF6
0x140017c0c  cmp     eax, edx
0x140017c0e  jb      loc_140018ABE
0x140017c14  sub     eax, edx
0x140017c16  add     ebx, edx
0x140017c18  jmp     short loc_140017BF6
0x140017c1a  xor     eax, eax
0x140017c1c  mov     [rbp+60h+var_E0], ebx
0x140017c1f  xorps   xmm0, xmm0
0x140017c22  mov     [rbp+60h+var_90], rax
0x140017c26  lea     rdx, [rbp+60h+var_E0]; unsigned int *
0x140017c2a  mov     qword ptr [rbp+60h+var_D8], rdi
0x140017c2e  lea     rcx, [rbp+60h+var_D8]; unsigned __int8 **
0x140017c32  movups  [rbp+60h+var_A0], xmm0
0x140017c36  call    ?FindFirstP2PIE@@YAJPEAPEAEPEAK@Z; FindFirstP2PIE(uchar * *,ulong *)
0x140017c3b  test    eax, eax
0x140017c3d  jns     loc_140018DD0
0x140017c43  lea     ecx, [rbx+0Ch]
0x140017c46  mov     [rbp+60h+var_E0], ecx
0x140017c49  nop     dword ptr [rax+00000000h]
0x140017c50  cmp     ebx, 2
0x140017c53  jb      short loc_140017C89
0x140017c55  movzx   ecx, byte ptr [rdi+1]
0x140017c59  lea     eax, [rcx+2]
0x140017c5c  cmp     ebx, eax
0x140017c5e  jb      short loc_140017C89
0x140017c60  cmp     [rdi], r14b
0x140017c63  jz      short loc_140017C6C
0x140017c65  sub     ebx, eax
0x140017c67  add     rdi, rax
0x140017c6a  jmp     short loc_140017C50
0x140017c6c  lea     rdx, [rdi+2]; Src
0x140017c70  test    rdx, rdx
0x140017c73  jz      short loc_140017C89
0x140017c75  cmp     cl, 20h ; ' '
0x140017c78  ja      short loc_140017C89
0x140017c7a  mov     [rbp+60h+var_80], ecx
0x140017c7d  mov     r8, rcx; Size
0x140017c80  lea     rcx, [rbp+60h+var_7C]; void *
0x140017c84  call    memmove
0x140017c89  mov     r12d, r14d
0x140017c8c  mov     eax, [rsi]
0x140017c8e  mov     [rsp+160h+var_E8], r14d
0x140017c93  test    al, 1
0x140017c95  jnz     loc_140017E5E
0x140017c9b  test    r14d, r14d
0x140017c9e  jnz     loc_140018DC8
0x140017ca4  lea     r14, [rsi+4]
0x140017ca8  cmp     r15d, 1
0x140017cac  jz      loc_140018376
0x140017cb2  test    r13b, r13b
0x140017cb5  jz      loc_140018994
0x140017cbb  mov     rdi, [rbp+60h+var_D0]
0x140017cbf  xor     r12b, r12b
0x140017cc2  mov     [rsp+160h+var_100], r12b
0x140017cc7  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140017cce  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140017cd5  lea     r13, WPP_80a5feb0ecb23662e1af05670292ea94_Traceguids
0x140017cdc  jz      short loc_140017CFA
0x140017cde  mov     rcx, cs:WPP_GLOBAL_Control
0x140017ce5  cmp     byte ptr [rcx+29h], 5
0x140017ce9  jnb     loc_140018E9E
0x140017cef  cmp     word ptr [rcx+48h], 0
0x140017cf4  jnz     loc_140018E9E
0x140017cfa  lea     rsi, [rdi+158h]
0x140017d01  mov     rbx, [rsi]
0x140017d04  cmp     rbx, rsi
0x140017d07  jnz     short loc_140017D44
0x140017d09  lea     rsi, [rdi+168h]
0x140017d10  movzx   eax, byte ptr [rsi+20h]
0x140017d14  jmp     short loc_140017D67
0x140017d16  xor     edi, edi
0x140017d18  mov     rax, [rdi]
0x140017d1b  lea     r8, [rbp+60h+var_80]
0x140017d1f  movzx   r9d, [rsp+160h+var_EA]
0x140017d25  mov     rdx, r14
0x140017d28  mov     rcx, rdi
0x140017d2b  mov     rax, [rax+8]
0x140017d2f  call    _guard_dispatch_icall
0x140017d34  test    al, al
0x140017d36  jnz     short loc_140017D4F
0x140017d38  mov     rbx, [rbx]
0x140017d3b  cmp     rbx, rsi
0x140017d3e  jz      loc_14001878A
0x140017d44  test    rbx, rbx
0x140017d47  jz      short loc_140017D16
0x140017d49  mov     rdi, [rbx+10h]
0x140017d4d  jmp     short loc_140017D18
0x140017d4f  mov     rsi, [rbp+60h+var_D0]
0x140017d53  add     rsi, 168h
0x140017d5a  movzx   eax, byte ptr [rsi+20h]
0x140017d5e  test    rdi, rdi
0x140017d61  jnz     loc_140017F19
0x140017d67  xor     r12d, r12d
0x140017d6a  mov     [rbp+60h+var_C0], r12
0x140017d6e  mov     [rsp+160h+var_E9], r12b
0x140017d73  mov     [rbp+60h+var_D8], r12d
0x140017d77  test    al, al
0x140017d79  jz      loc_140018186
0x140017d7f  mov     rcx, [rbp+60h+var_C8]; this
0x140017d83  mov     edi, 0C000009Ah
0x140017d88  mov     eax, [rcx]
0x140017d8a  test    al, 1
0x140017d8c  jnz     loc_140017F10
0x140017d92  test    al, 2
0x140017d94  jz      loc_140018F2D
0x140017d9a  lea     rdx, [rcx+28h]
0x140017d9e  test    rdx, rdx
0x140017da1  jz      loc_140018F2D
0x140017da7  mov     r8d, [rdx]; unsigned int
0x140017daa  lea     rax, [rbp+60h+var_D8]
0x140017dae  mov     rdx, [rdx+8]; unsigned __int8 *
0x140017db2  lea     r9, [rbp+60h+var_C0]; unsigned __int8 **
0x140017db6  mov     [rsp+160h+var_138], rax; enum CBSSEntryFactory::BSS_TYPE *
0x140017dbb  lea     rax, [rsp+160h+var_E9]
0x140017dc0  mov     qword ptr [rsp+160h+var_140], rax; unsigned __int8 *
0x140017dc5  call    ?GetBSSType@CBSSEntryFactory@@AEBAHPEAEKPEAPEAE0PEAW4BSS_TYPE@1@@Z; CBSSEntryFactory::GetBSSType(uchar *,ulong,uchar * *,uchar *,CBSSEntryFactory::BSS_TYPE *)
0x140017dca  mov     [rsp+160h+var_F0], eax
0x140017dce  test    eax, eax
0x140017dd0  jnz     loc_140018F61
0x140017dd6  mov     r9d, [rbp+60h+var_D8]; enum CBSSEntryFactory::BSS_TYPE
0x140017dda  test    r9d, r9d
0x140017ddd  jnz     loc_140018867
0x140017de3  mov     edx, 320h
0x140017de8  mov     ecx, 40h ; '@'
0x140017ded  mov     r8d, 47696457h
0x140017df3  call    cs:__imp_ExAllocatePool2
0x140017dfa  nop     dword ptr [rax+rax+00h]
0x140017dff  test    rax, rax
0x140017e02  jz      loc_14001839B
0x140017e08  movzx   r8d, [rsp+160h+var_EC]; unsigned __int8
0x140017e0e  mov     rdx, r14; unsigned __int8 (*)[6]
0x140017e11  mov     rcx, rax; this
0x140017e14  call    ??0CBSSEntry@@QEAA@AEAY05$$CBEE@Z; CBSSEntry::CBSSEntry(uchar const (&)[6],uchar)
0x140017e19  mov     rbx, rax
0x140017e1c  test    rax, rax
0x140017e1f  jz      loc_14001839E
0x140017e25  mov     r12d, [rsp+160h+var_F0]
0x140017e2a  test    r12d, r12d
0x140017e2d  jz      loc_140018948
0x140017e33  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140017e3a  jnz     loc_140018BC2
0x140017e40  test    r12d, r12d
0x140017e43  jnz     loc_1400191B7
0x140017e49  mov     rbx, [rsp+160h+var_F8]
0x140017e4e  mov     rax, [rbp+60h+var_A8]
0x140017e52  mov     [rax], rbx
0x140017e55  mov     eax, r12d
0x140017e58  jmp     loc_1400191C6
0x140017e5e  mov     r8d, [rsi+10h]
0x140017e62  xorps   xmm0, xmm0
0x140017e65  mov     [rbp+60h+var_D8], 19h
0x140017e6c  movups  [rbp+60h+var_A0], xmm0
0x140017e70  movups  [rbp+60h+var_A0+9], xmm0
0x140017e74  cmp     r8d, 0Ch
0x140017e78  jb      loc_140018E0A
0x140017e7e  mov     rdi, [rsi+18h]
0x140017e82  lea     ecx, [r8-0Ch]
0x140017e86  add     rdi, 0Ch
0x140017e8a  mov     ebx, r14d
0x140017e8d  nop     dword ptr [rax]
0x140017e90  cmp     ecx, 2
0x140017e93  jb      short loc_140017EB4
0x140017e95  mov     eax, ebx
0x140017e97  add     ecx, 0FFFFFFFEh
0x140017e9a  add     ebx, 2
0x140017e9d  movzx   edx, byte ptr [rax+rdi+1]
0x140017ea2  test    dl, dl
0x140017ea4  jz      short loc_140017E90
0x140017ea6  cmp     ecx, edx
0x140017ea8  jb      loc_140018B05
0x140017eae  sub     ecx, edx
0x140017eb0  add     ebx, edx
0x140017eb2  jmp     short loc_140017E90
0x140017eb4  lea     r9, [rbp+60h+var_D8]
0x140017eb8  mov     edx, ebx
0x140017eba  lea     r8, [rbp+60h+var_A0]
0x140017ebe  mov     rcx, rdi; unsigned __int8 *
0x140017ec1  call    WFDGetDeviceInfo
0x140017ec6  mov     edx, 80000000h
0x140017ecb  lea     ecx, [rax+rdx]
0x140017ece  test    edx, ecx
0x140017ed0  jnz     loc_140018B15
0x140017ed6  cmp     eax, 0C0230016h
0x140017edb  jz      loc_140018B15
0x140017ee1  mov     edx, [rbp+60h+var_80]
0x140017ee4  lea     eax, [rbx+0Ch]
0x140017ee7  mov     word ptr [rsp+160h+var_E8], ax
0x140017eec  test    edx, edx
0x140017eee  jz      loc_140018920
0x140017ef4  mov     ecx, r14d
0x140017ef7  cmp     ecx, edx
0x140017ef9  jnb     loc_140018920
0x140017eff  mov     eax, ecx
0x140017f01  cmp     byte ptr [rbp+rax+60h+var_7C], r14b
0x140017f06  jnz     loc_1400186A4
0x140017f0c  inc     ecx
0x140017f0e  jmp     short loc_140017EF7
0x140017f10  lea     rdx, [rcx+10h]
0x140017f14  jmp     loc_140017D9E
0x140017f19  test    al, al
0x140017f1b  jz      short loc_140017F7A
0x140017f1d  mov     rbx, [rbp+60h+var_C8]
0x140017f21  xor     eax, eax
0x140017f23  mov     [rbp+60h+var_C0], rax
0x140017f27  mov     [rsp+160h+var_E9], al
0x140017f2b  mov     [rsp+160h+var_F0], eax
0x140017f2f  mov     eax, [rbx]
0x140017f31  test    al, 1
0x140017f33  jnz     loc_1400184F5
0x140017f39  test    al, 2
0x140017f3b  jz      loc_140018EBF
0x140017f41  lea     rdx, [rbx+28h]
0x140017f45  test    rdx, rdx
0x140017f48  jz      loc_140018EBF
0x140017f4e  mov     r8d, [rdx]; unsigned int
0x140017f51  lea     rax, [rsp+160h+var_F0]
0x140017f56  mov     rdx, [rdx+8]; unsigned __int8 *
0x140017f5a  lea     r9, [rbp+60h+var_C0]; unsigned __int8 **
0x140017f5e  mov     [rsp+160h+var_138], rax; enum CBSSEntryFactory::BSS_TYPE *
0x140017f63  lea     rax, [rsp+160h+var_E9]
0x140017f68  mov     qword ptr [rsp+160h+var_140], rax; unsigned __int8 *
0x140017f6d  call    ?GetBSSType@CBSSEntryFactory@@AEBAHPEAEKPEAPEAE0PEAW4BSS_TYPE@1@@Z; CBSSEntryFactory::GetBSSType(uchar *,ulong,uchar * *,uchar *,CBSSEntryFactory::BSS_TYPE *)
0x140017f72  test    eax, eax
0x140017f74  jz      loc_140018576
0x140017f7a  mov     rsi, [rbp+60h+var_D0]
0x140017f7e  mov     r10, rdi
0x140017f81  mov     [rsp+160h+var_F8], rdi
0x140017f86  mov     r13, 0FFFFF78000000014h
0x140017f90  mov     edi, 0C000009Ah
0x140017f95  jmp     loc_14001804F
0x140017f9a  movzx   r9d, [rsp+160h+var_EC]; unsigned __int8
0x140017fa0  lea     rax, [rbp+60h+var_D8]
0x140017fa4  mov     r8, rbx; struct _WDI_BSS_ENTRY_CONTAINER *
0x140017fa7  mov     qword ptr [rsp+160h+var_140], rax; struct CBSSEntry **
0x140017fac  mov     rdx, rdi; struct CBSSEntry *
0x140017faf  mov     qword ptr [rbp+60h+var_D8], 0
0x140017fb7  mov     rcx, rsi; this
0x140017fba  call    ?Rebuild@CBSSEntryFactory@@QEAAHPEAVCBSSEntry@@PEAU_WDI_BSS_ENTRY_CONTAINER@@EPEAPEAV2@@Z; CBSSEntryFactory::Rebuild(CBSSEntry *,_WDI_BSS_ENTRY_CONTAINER *,uchar,CBSSEntry * *)
0x140017fbf  mov     r12d, eax
0x140017fc2  test    eax, eax
0x140017fc4  jnz     loc_140018B30
0x140017fca  mov     rbx, qword ptr [rbp+60h+var_D8]
0x140017fce  test    rbx, rbx
0x140017fd1  jz      loc_140018B30
0x140017fd7  mov     rcx, [rdi+8]
0x140017fdb  lea     rdx, [rdi+8]
0x140017fdf  cmp     [rcx+8], rdx
  ... truncated ...
```
