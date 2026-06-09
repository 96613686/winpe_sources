# GenerateSSLProperties(ABO_NODE *,ushort const *)

- ea: `0x1800278cc`
- end: `0x180028441`
- name: `?GenerateSSLProperties@@YAJPEAVABO_NODE@@PEBG@Z`
- size: `2933`
- prototype: `int(struct ABO_NODE *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config, service_task`

## callers

- `0x180016200`
- `0x1800165d0`
- `0x180028f20`

## callees

- `0x180001f90`
- `0x180002990`
- `0x180003402`
- `0x1800065a8`
- `0x1800077dc`
- `0x18000fa00`
- `0x18000fd48`
- `0x18000fec4`
- `0x180027404`
- `0x1800278cc`
- `0x180028c64`

## import_xrefs

- `HTTPAPI!HttpTerminate` at `0x1800283d4`
- `HTTPAPI!HttpTerminate` at `0x1800283d4`
- `HTTPAPI!HttpInitialize` at `0x18002793a`
- `HTTPAPI!HttpInitialize` at `0x18002793a`
- `HTTPAPI!HttpQueryServiceConfiguration` at `0x1800279ca`
- `HTTPAPI!HttpQueryServiceConfiguration` at `0x180027a4f`
- `HTTPAPI!HttpQueryServiceConfiguration` at `0x1800279ca`
- `HTTPAPI!HttpQueryServiceConfiguration` at `0x180027a4f`
- `WS2_32!FreeAddrInfoW` at `0x1800283c2`
- `WS2_32!FreeAddrInfoW` at `0x1800283c2`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180027a09`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180027a09`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180027a23`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180027a91`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180027b5a`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180027b6c`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180027c8f`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180027ca1`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180027db4`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180027dc6`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180027eb8`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180027eca`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180027fbd`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800280a3`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180028187`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002825f`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002833a`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180027a23`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180027a91`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180027b5a`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180027b6c`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180027c8f`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180027ca1`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180027db4`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180027dc6`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180027eb8`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180027eca`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180027fbd`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800280a3`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180028187`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002825f`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002833a`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x1800279ef`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x1800279ef`

## string_xrefs

- `0x180027a6e`: `HttpQueryServiceConfiguration failed err=%X\n`

## pseudocode

```c
__int64 __fastcall GenerateSSLProperties(struct ABO_NODE *a1, wchar_t *a2)
{
  unsigned int v3; // edx
  struct PROPERTY_ENTRY *v5; // r14
  PROPERTY_ENTRY *v6; // rsi
  BUFFER *v7; // r15
  signed int SockAddress; // edi
  bool v9; // sf
  int v10; // r12d
  signed int v11; // eax
  BUFFER *v12; // rax
  BUFFER *v13; // rax
  ULONG OutputLength; // ebx
  void *pOutput; // rax
  unsigned int *Ptr; // rax
  PROPERTY_BAG *v17; // rbx
  unsigned int *v18; // r15
  PROPERTY_ENTRY *v19; // rax
  PROPERTY_ENTRY *v20; // rax
  __int64 v21; // r13
  __int64 v22; // rcx
  __int64 v23; // rax
  int v24; // eax
  int v25; // eax
  PROPERTY_ENTRY *v26; // rax
  PROPERTY_ENTRY *v27; // rax
  unsigned __int8 *v28; // rax
  _DWORD *v29; // rax
  int v30; // eax
  int v31; // eax
  PROPERTY_ENTRY *v32; // rax
  PROPERTY_ENTRY *v33; // rax
  __int64 v34; // rcx
  __int64 v35; // rax
  _DWORD *v36; // rax
  int v37; // eax
  int v38; // eax
  PROPERTY_ENTRY *v39; // rax
  PROPERTY_ENTRY *v40; // rax
  __int64 v41; // rax
  _DWORD *v42; // rax
  int v43; // eax
  int v44; // eax
  PROPERTY_ENTRY *v45; // rax
  PROPERTY_ENTRY *v46; // rax
  int v47; // eax
  int v48; // eax
  int v49; // eax
  PROPERTY_ENTRY *v50; // rax
  PROPERTY_ENTRY *v51; // rax
  int v52; // eax
  int v53; // eax
  int v54; // eax
  PROPERTY_ENTRY *v55; // rax
  PROPERTY_ENTRY *v56; // rax
  int v57; // eax
  int v58; // eax
  int v59; // eax
  PROPERTY_ENTRY *v60; // rax
  PROPERTY_ENTRY *v61; // rax
  int v62; // eax
  int v63; // eax
  int v64; // eax
  PROPERTY_ENTRY *v65; // rax
  PROPERTY_ENTRY *v66; // rax
  int v67; // eax
  int v68; // eax
  int v69; // eax
  __int64 result; // rax
  struct PROPERTY_ENTRY *v71; // [rsp+40h] [rbp-39h] BYREF
  BUFFER *v72; // [rsp+48h] [rbp-31h]
  struct _METADATA_RECORD v73; // [rsp+50h] [rbp-29h] BYREF
  PROPERTY_BAG *v74; // [rsp+78h] [rbp-1h]
  PADDRINFOW pAddrInfo; // [rsp+80h] [rbp+7h] BYREF
  __int128 pInput; // [rsp+88h] [rbp+Fh] BYREF
  __int64 v77; // [rsp+98h] [rbp+1Fh]
  int v79; // [rsp+F0h] [rbp+77h] BYREF
  ULONG pReturnLength; // [rsp+F8h] [rbp+7Fh] BYREF

  v3 = 0;
  v77 = 0;
  v71 = 0;
  v72 = 0;
  pReturnLength = 0;
  v5 = 0;
  pAddrInfo = 0;
  v6 = 0;
  v79 = 0;
  v7 = 0;
  pInput = 0;
  if ( a1 && a2 )
  {
    SockAddress = HttpInitialize(g_Version, 2u, 0);
    v9 = SockAddress < 0;
    if ( SockAddress > 0 )
    {
      SockAddress = (unsigned __int16)SockAddress | 0x80070000;
      v9 = SockAddress < 0;
    }
    if ( v9 )
    {
      ABO_MAPPER_LOG::WriteLogEntry(g_pAboLog, L"HttpInitialize failed err=%X\n", (unsigned int)SockAddress);
      goto LABEL_151;
    }
    v10 = 1;
    SockAddress = GetSockAddress(a2, &pAddrInfo);
    if ( SockAddress < 0 )
      goto LABEL_147;
    v77 = 0;
    pInput = 0;
    *((_QWORD *)&pInput + 1) = pAddrInfo->ai_addr;
    v11 = HttpQueryServiceConfiguration(0, HttpServiceConfigSSLCertInfo, &pInput, 0x18u, 0, 0, &pReturnLength, 0);
    if ( v11 == 122 )
    {
      v12 = (BUFFER *)operator new(0x30u);
      if ( !v12 || (v13 = BUFFER::BUFFER(v12), (v7 = v13) == 0) )
      {
        SockAddress = -2147024888;
        goto LABEL_147;
      }
      if ( !BUFFER::Resize(v13, pReturnLength) )
      {
        SockAddress = -2147024888;
LABEL_146:
        BUFFER::`scalar deleting destructor'(v7, v3);
        goto LABEL_147;
      }
      OutputLength = pReturnLength;
      pOutput = BUFFER::QueryPtr(v7);
      v11 = HttpQueryServiceConfiguration(
              0,
              HttpServiceConfigSSLCertInfo,
              &pInput,
              0x18u,
              pOutput,
              OutputLength,
              &pReturnLength,
              0);
      v72 = v7;
    }
    if ( v11 )
    {
      if ( v11 > 0 )
        v11 = (unsigned __int16)v11 | 0x80070000;
      ABO_MAPPER_LOG::WriteLogEntry(g_pAboLog, L"HttpQueryServiceConfiguration failed err=%X\n", (unsigned int)v11);
      goto LABEL_18;
    }
    Ptr = (unsigned int *)BUFFER::QueryPtr(v7);
    v17 = (struct ABO_NODE *)((char *)a1 + 184);
    v74 = (struct ABO_NODE *)((char *)a1 + 184);
    v18 = Ptr;
    SockAddress = PROPERTY_BAG::FindEntry((struct ABO_NODE *)((char *)a1 + 184), 0x1587u, &v71);
    if ( (int)(SockAddress + 0x80000000) >= 0 && SockAddress != -2147024894 )
    {
      v5 = v71;
      v3 = 0;
      v7 = v72;
      goto LABEL_159;
    }
    v19 = (PROPERTY_ENTRY *)operator new(0x50u);
    v3 = 0;
    if ( !v19 )
      goto LABEL_155;
    v20 = PROPERTY_ENTRY::PROPERTY_ENTRY(v19, 1);
    v3 = 0;
    v6 = v20;
    if ( !v20 )
      goto LABEL_155;
    v21 = -1;
    v73.dwMDIdentifier = 5511;
    v5 = v71;
    *(&v73.dwMDDataLen + 1) = 0;
    *(_QWORD *)&v73.dwMDDataTag = 0;
    v73.dwMDAttributes = 1;
    v73.dwMDDataType = 2;
    v73.dwMDUserType = 1;
    if ( v18 )
    {
      v22 = *((_QWORD *)v18 + 5);
      if ( v22 )
      {
        v23 = -1;
        do
          ++v23;
        while ( *(_WORD *)(v22 + 2 * v23) );
        if ( v23 )
        {
          if ( SockAddress < 0 )
          {
            v73.pbMDData = (unsigned __int8 *)*((_QWORD *)v18 + 5);
            v73.dwMDDataLen = 2 * v23 + 2;
          }
          else
          {
            v73.pbMDData = (unsigned __int8 *)*((_QWORD *)BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)v71 + 16))
                                              + 3);
            v73.dwMDDataLen = *((_DWORD *)BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)v5 + 16)) + 4);
          }
          v24 = PROPERTY_ENTRY::Create(v6, &v73);
          v3 = 0;
          SockAddress = v24;
          if ( v24 < 0 )
            goto LABEL_157;
          v25 = PROPERTY_BAG::AddEntry(v17, v6, 1);
          v3 = 0;
          SockAddress = v25;
          if ( v25 < 0 )
            goto LABEL_157;
        }
      }
    }
    PROPERTY_MAPPING::DereferencePropertyMapping(v6);
    if ( v5 )
    {
      PROPERTY_MAPPING::DereferencePropertyMapping(v5);
      v71 = 0;
    }
    SockAddress = PROPERTY_BAG::FindEntry(v17, 0x1582u, &v71);
    if ( (int)(SockAddress + 0x80000000) >= 0 && SockAddress != -2147024894 )
    {
LABEL_39:
      v3 = 0;
      v6 = 0;
LABEL_156:
      v5 = v71;
      goto LABEL_157;
    }
    v26 = (PROPERTY_ENTRY *)operator new(0x50u);
    v3 = 0;
    if ( !v26 )
      goto LABEL_154;
    v27 = PROPERTY_ENTRY::PROPERTY_ENTRY(v26, 1);
    v3 = 0;
    v6 = v27;
    if ( v27 )
    {
      v73.dwMDIdentifier = 5506;
      v5 = v71;
      *(&v73.dwMDDataLen + 1) = 0;
      *(_QWORD *)&v73.dwMDDataTag = 0;
      v73.dwMDDataType = 3;
      if ( v18 && *((_QWORD *)v18 + 2) && v18[2] )
      {
        v28 = (unsigned __int8 *)operator new(v18[2]);
        v3 = 0;
        v73.pbMDData = v28;
        if ( !v28 )
        {
          SockAddress = -2147024888;
LABEL_157:
          v7 = v72;
          goto LABEL_159;
        }
        if ( SockAddress < 0 )
        {
          memcpy_0(v28, *((const void **)v18 + 2), v18[2]);
          v73.dwMDDataLen = v18[2];
        }
        else
        {
          v73.pbMDData = (unsigned __int8 *)*((_QWORD *)BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)v5 + 16)) + 3);
          v29 = BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)v5 + 16));
          v17 = v74;
          v73.dwMDDataLen = v29[4];
        }
        v30 = PROPERTY_ENTRY::Create(v6, &v73);
        v3 = 0;
        SockAddress = v30;
        if ( v30 < 0 )
          goto LABEL_157;
        v31 = PROPERTY_BAG::AddEntry(v17, v6, 1);
        v3 = 0;
        SockAddress = v31;
        if ( v31 < 0 )
          goto LABEL_157;
      }
      PROPERTY_MAPPING::DereferencePropertyMapping(v6);
      if ( v5 )
      {
        PROPERTY_MAPPING::DereferencePropertyMapping(v5);
        v71 = 0;
      }
      SockAddress = PROPERTY_BAG::FindEntry(v17, 0x1588u, &v71);
      if ( (int)(SockAddress + 0x80000000) >= 0 && SockAddress != -2147024894 )
        goto LABEL_39;
      v32 = (PROPERTY_ENTRY *)operator new(0x50u);
      v3 = 0;
      if ( !v32 )
        goto LABEL_154;
      v33 = PROPERTY_ENTRY::PROPERTY_ENTRY(v32, 1);
      v3 = 0;
      v6 = v33;
      if ( !v33 )
        goto LABEL_155;
      *(_QWORD *)&v73.dwMDIdentifier = 5512;
      v5 = v71;
      *(&v73.dwMDDataLen + 1) = 0;
      *(_QWORD *)&v73.dwMDDataTag = 0;
      v73.dwMDDataType = 2;
      if ( v18 )
      {
        v34 = *((_QWORD *)v18 + 8);
        if ( v34 )
        {
          v35 = -1;
          do
            ++v35;
          while ( *(_WORD *)(v34 + 2 * v35) );
          if ( v35 )
          {
            if ( SockAddress < 0 )
            {
              v73.pbMDData = (unsigned __int8 *)*((_QWORD *)v18 + 8);
              v73.dwMDDataLen = 2 * v35 + 2;
            }
            else
            {
              v73.pbMDData = (unsigned __int8 *)*((_QWORD *)BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)v71 + 16))
                                                + 3);
              v36 = BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)v5 + 16));
              v17 = v74;
              v73.dwMDDataLen = v36[4];
            }
            v37 = PROPERTY_ENTRY::Create(v6, &v73);
            v3 = 0;
            SockAddress = v37;
            if ( v37 < 0 )
              goto LABEL_157;
            v38 = PROPERTY_BAG::AddEntry(v17, v6, 1);
            v3 = 0;
            SockAddress = v38;
            if ( v38 < 0 )
              goto LABEL_157;
          }
        }
      }
      PROPERTY_MAPPING::DereferencePropertyMapping(v6);
      if ( v5 )
      {
        PROPERTY_MAPPING::DereferencePropertyMapping(v5);
        v71 = 0;
      }
      SockAddress = PROPERTY_BAG::FindEntry(v17, 0x158Du, &v71);
      if ( (int)(SockAddress + 0x80000000) >= 0 && SockAddress != -2147024894 )
        goto LABEL_39;
      v39 = (PROPERTY_ENTRY *)operator new(0x50u);
      v3 = 0;
      if ( !v39 )
        goto LABEL_154;
      v40 = PROPERTY_ENTRY::PROPERTY_ENTRY(v39, 1);
      v3 = 0;
      v6 = v40;
      if ( !v40 )
        goto LABEL_155;
      v73.dwMDIdentifier = 5517;
      v5 = v71;
      *(&v73.dwMDDataLen + 1) = 0;
      *(_QWORD *)&v73.dwMDDataTag = 0;
      if ( v18 )
      {
        v41 = *((_QWORD *)v18 + 9);
        if ( v41 )
        {
          if ( SockAddress < 0 )
          {
            v73.pbMDData = (unsigned __int8 *)*((_QWORD *)v18 + 9);
            do
              ++v21;
            while ( *(_WORD *)(v41 + 2 * v21) );
            v73.dwMDDataLen = 2 * v21 + 2;
          }
          else
          {
            v73.pbMDData = (unsigned __int8 *)*((_QWORD *)BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)v71 + 16))
                                              + 3);
            v42 = BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)v5 + 16));
            v17 = v74;
            v73.dwMDDataLen = v42[4];
          }
          v43 = PROPERTY_ENTRY::Create(v6, &v73);
          v3 = 0;
          SockAddress = v43;
          if ( v43 < 0 )
            goto LABEL_157;
          v44 = PROPERTY_BAG::AddEntry(v17, v6, 1);
          v3 = 0;
          SockAddress = v44;
          if ( v44 < 0 )
            goto LABEL_157;
        }
      }
      PROPERTY_MAPPING::DereferencePropertyMapping(v6);
      if ( v5 )
      {
        PROPERTY_MAPPING::DereferencePropertyMapping(v5);
        v71 = 0;
      }
      SockAddress = PROPERTY_BAG::FindEntry(v17, 0x870u, &v71);
      if ( (int)(SockAddress + 0x80000000) >= 0 && SockAddress != -2147024894 )
        goto LABEL_39;
      v45 = (PROPERTY_ENTRY *)operator new(0x50u);
      v3 = 0;
      if ( !v45 )
        goto LABEL_154;
      v46 = PROPERTY_ENTRY::PROPERTY_ENTRY(v45, 1);
      v3 = 0;
      v6 = v46;
      if ( !v46 )
        goto LABEL_155;
      v73.dwMDIdentifier = 2160;
      v5 = v71;
      *(&v73.dwMDDataLen + 1) = 0;
      *(_QWORD *)&v73.dwMDDataTag = 0;
      v73.dwMDAttributes = 1;
      v73.dwMDDataType = 1;
      if ( SockAddress < 0 )
      {
        if ( v18 )
          v47 = v18[12];
        else
          v47 = 0;
      }
      else
      {
        v47 = **((_DWORD **)BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)v71 + 16)) + 3);
      }
      v79 = v47;
      v73.dwMDDataLen = 4;
      v73.pbMDData = (unsigned __int8 *)&v79;
      v48 = PROPERTY_ENTRY::Create(v6, &v73);
      v3 = 0;
      SockAddress = v48;
      if ( v48 < 0 )
        goto LABEL_157;
      v49 = PROPERTY_BAG::AddEntry(v17, v6, 1);
      v3 = 0;
      SockAddress = v49;
      if ( v49 < 0 )
        goto LABEL_157;
      PROPERTY_MAPPING::DereferencePropertyMapping(v6);
      SockAddress = PROPERTY_BAG::FindEntry((PROPERTY_BAG *)(*((_QWORD *)a1 + 2) + 184LL), 0x158Fu, &v71);
      if ( (int)(SockAddress + 0x80000000) >= 0 && SockAddress != -2147024894 )
        goto LABEL_39;
      v50 = (PROPERTY_ENTRY *)operator new(0x50u);
      v3 = 0;
      if ( !v50 )
        goto LABEL_154;
      v51 = PROPERTY_ENTRY::PROPERTY_ENTRY(v50, 1);
      v3 = 0;
      v6 = v51;
      if ( !v51 )
        goto LABEL_155;
      v73.dwMDIdentifier = 5519;
      v5 = v71;
      *(&v73.dwMDDataLen + 1) = 0;
      *(_QWORD *)&v73.dwMDDataTag = 0;
      if ( SockAddress < 0 )
        v52 = v18[20] & 1;
      else
        v52 = **((_DWORD **)BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)v71 + 16)) + 3);
      v79 = v52;
      v53 = PROPERTY_ENTRY::Create(v6, &v73);
      v3 = 0;
      SockAddress = v53;
      if ( v53 < 0 )
        goto LABEL_157;
      v54 = PROPERTY_BAG::AddEntry((PROPERTY_BAG *)(*((_QWORD *)a1 + 2) + 184LL), v6, 1);
      v3 = 0;
      SockAddress = v54;
      if ( v54 < 0 )
        goto LABEL_157;
      PROPERTY_MAPPING::DereferencePropertyMapping(v6);
      if ( v5 )
      {
        PROPERTY_MAPPING::DereferencePropertyMapping(v5);
        v71 = 0;
      }
      SockAddress = PROPERTY_BAG::FindEntry(v17, 0x1591u, &v71);
      if ( (int)(SockAddress + 0x80000000) >= 0 && SockAddress != -2147024894 )
        goto LABEL_39;
      v55 = (PROPERTY_ENTRY *)operator new(0x50u);
      v3 = 0;
      if ( !v55 )
        goto LABEL_154;
      v56 = PROPERTY_ENTRY::PROPERTY_ENTRY(v55, 1);
      v3 = 0;
      v6 = v56;
      if ( !v56 )
        goto LABEL_155;
      v73.dwMDIdentifier = 5521;
      v5 = v71;
      *(&v73.dwMDDataLen + 1) = 0;
      *(_QWORD *)&v73.dwMDDataTag = 0;
      if ( SockAddress < 0 )
        v57 = (*((unsigned __int8 *)v18 + 80) >> 1) & 1;
      else
        v57 = **((_DWORD **)BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)v71 + 16)) + 3);
      v79 = v57;
      v58 = PROPERTY_ENTRY::Create(v6, &v73);
      v3 = 0;
      SockAddress = v58;
      if ( v58 < 0 )
        goto LABEL_157;
      v59 = PROPERTY_BAG::AddEntry(v17, v6, 1);
      v3 = 0;
      SockAddress = v59;
      if ( v59 < 0 )
        goto LABEL_157;
      PROPERTY_MAPPING::DereferencePropertyMapping(v6);
      if ( v5 )
      {
        PROPERTY_MAPPING::DereferencePropertyMapping(v5);
        v71 = 0;
      }
      SockAddress = PROPERTY_BAG::FindEntry(v17, 0x871u, &v71);
      if ( ((SockAddress + 0x80000000) & 0x80000000) == 0 && SockAddress != -2147024894 )
        goto LABEL_39;
      v60 = (PROPERTY_ENTRY *)operator new(0x50u);
      v3 = 0;
      if ( !v60 )
      {
LABEL_154:
        v6 = 0;
        goto LABEL_155;
      }
      v61 = PROPERTY_ENTRY::PROPERTY_ENTRY(v60, 1);
      v3 = 0;
      v6 = v61;
      if ( v61 )
      {
        v73.dwMDIdentifier = 2161;
        v5 = v71;
        *(&v73.dwMDDataLen + 1) = 0;
        *(_QWORD *)&v73.dwMDDataTag = 0;
        if ( SockAddress < 0 )
        {
          if ( v18 )
            v62 = v18[13];
          else
            v62 = 0;
        }
        else
        {
          v62 = **((_DWORD **)BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)v71 + 16)) + 3);
        }
        v79 = v62;
        v63 = PROPERTY_ENTRY::Create(v6, &v73);
        v3 = 0;
        SockAddress = v63;
        if ( v63 < 0 )
          goto LABEL_157;
        v64 = PROPERTY_BAG::AddEntry(v17, v6, 1);
        v3 = 0;
        SockAddress = v64;
        if ( v64 < 0 )
          goto LABEL_157;
        PROPERTY_MAPPING::DereferencePropertyMapping(v6);
        if ( v5 )
        {
          PROPERTY_MAPPING::DereferencePropertyMapping(v5);
          v71 = 0;
        }
        SockAddress = PROPERTY_BAG::FindEntry(v17, 0x872u, &v71);
        if ( ((SockAddress + 0x80000000) & 0x80000000) == 0 && SockAddress != -2147024894 )
          goto LABEL_39;
        v65 = (PROPERTY_ENTRY *)operator new(0x50u);
        v3 = 0;
        if ( v65 )
        {
          v66 = PROPERTY_ENTRY::PROPERTY_ENTRY(v65, 1);
          v3 = 0;
          v6 = v66;
          if ( v66 )
          {
            v73.dwMDIdentifier = 2162;
            v5 = v71;
            *(&v73.dwMDDataLen + 1) = 0;
            *(_QWORD *)&v73.dwMDDataTag = 0;
            if ( SockAddress < 0 )
            {
              if ( v18 )
                v67 = v18[14];
              else
                v67 = 0;
            }
            else
            {
              v67 = **((_DWORD **)BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)v71 + 16)) + 3);
            }
            v79 = v67;
            v68 = PROPERTY_ENTRY::Create(v6, &v73);
            v3 = 0;
            SockAddress = v68;
            if ( v68 >= 0 )
            {
              v69 = PROPERTY_BAG::AddEntry(v17, v6, 1);
              v3 = 0;
              SockAddress = v69;
              if ( v69 >= 0 )
              {
                PROPERTY_MAPPING::DereferencePropertyMapping(v6);
                v3 = 0;
                if ( v5 )
                {
                  PROPERTY_MAPPING::DereferencePropertyMapping(v5);
                  v3 = 0;
                }
                v7 = v72;
                goto LABEL_145;
              }
            }
            goto LABEL_157;
          }
          goto LABEL_155;
        }
        goto LABEL_154;
      }
    }
LABEL_155:
    SockAddress = -2147024888;
    goto LABEL_156;
  }
  v10 = 0;
  SockAddress = -2147024809;
LABEL_159:
  if ( v5 )
  {
    PROPERTY_MAPPING::DereferencePropertyMapping(v5);
    v3 = 0;
  }
  if ( v6 )
  {
    PROPERTY_MAPPING::DereferencePropertyMapping(v6);
LABEL_18:
    v3 = 0;
  }
LABEL_145:
  if ( v7 )
    goto LABEL_146;
LABEL_147:
  if ( pAddrInfo )
    FreeAddrInfoW(pAddrInfo);
  if ( v10 )
    HttpTerminate(2u, 0);
LABEL_151:
  result = 0;
  if ( SockAddress != -2147024894 )
    return (unsigned int)SockAddress;
  return result;
}

```

## disassembly

```asm
0x1800278cc  mov     [rsp-8+arg_8], rbx
0x1800278d1  mov     [rsp-8+arg_0], rcx
0x1800278d6  push    rbp
0x1800278d7  push    rsi
0x1800278d8  push    rdi
0x1800278d9  push    r12
0x1800278db  push    r13
0x1800278dd  push    r14
0x1800278df  push    r15
0x1800278e1  lea     rbp, [rsp-27h]
0x1800278e6  sub     rsp, 0A0h
0x1800278ed  xor     eax, eax
0x1800278ef  mov     rbx, rdx
0x1800278f2  xor     edx, edx
0x1800278f4  mov     [rbp+57h+var_38], rax
0x1800278f8  mov     [rbp+57h+var_90], rdx
0x1800278fc  xorps   xmm0, xmm0
0x1800278ff  mov     [rbp+57h+var_88], rdx
0x180027903  mov     r13, rcx
0x180027906  mov     [rbp+57h+arg_18], edx
0x180027909  mov     r14d, edx
0x18002790c  mov     [rbp+57h+pAddrInfo], rdx
0x180027910  mov     esi, edx
0x180027912  mov     [rbp+57h+arg_10], edx
0x180027915  mov     r15d, edx
0x180027918  movups  [rbp+57h+pInput], xmm0
0x18002791c  test    rcx, rcx
0x18002791f  jz      loc_180028414
0x180027925  test    rbx, rbx
0x180027928  jz      loc_180028414
0x18002792e  mov     ecx, dword ptr cs:?g_Version@@3U_HTTPAPI_VERSION@@A.HttpApiMajorVersion; Version
0x180027934  lea     edx, [rax+2]; Flags
0x180027937  xor     r8d, r8d; pReserved
0x18002793a  call    cs:__imp_HttpInitialize
0x180027940  mov     edi, eax
0x180027942  test    eax, eax
0x180027944  jle     short loc_180027951
0x180027946  movzx   edi, di
0x180027949  or      edi, 80070000h
0x18002794f  test    edi, edi
0x180027951  jns     short loc_18002796E
0x180027953  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x18002795a  lea     rdx, aHttpinitialize; "HttpInitialize failed err=%X\n"
0x180027961  mov     r8d, edi
0x180027964  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x180027969  jmp     loc_1800283DA
0x18002796e  lea     rdx, [rbp+57h+pAddrInfo]; struct addrinfoW **
0x180027972  mov     rcx, rbx; Str
0x180027975  mov     r12d, 1
0x18002797b  call    ?GetSockAddress@@YAJPEBGPEAPEAUaddrinfoW@@@Z; GetSockAddress(ushort const *,addrinfoW * *)
0x180027980  xor     edx, edx
0x180027982  mov     edi, eax
0x180027984  test    eax, eax
0x180027986  js      loc_1800283B6
0x18002798c  mov     rcx, [rbp+57h+pAddrInfo]
0x180027990  lea     r9d, [r12+17h]; InputLength
0x180027995  mov     [rsp+0D0h+pOverlapped], rdx; pOverlapped
0x18002799a  lea     r8, [rbp+57h+pInput]; pInput
0x18002799e  xor     eax, eax
0x1800279a0  xorps   xmm0, xmm0
0x1800279a3  mov     [rbp+57h+var_38], rax
0x1800279a7  lea     rax, [rbp+57h+arg_18]
0x1800279ab  movups  [rbp+57h+pInput], xmm0
0x1800279af  mov     rcx, [rcx+20h]
0x1800279b3  mov     [rsp+0D0h+pReturnLength], rax; pReturnLength
0x1800279b8  mov     [rsp+0D0h+OutputLength], edx; OutputLength
0x1800279bc  mov     qword ptr [rbp+57h+pInput+8], rcx
0x1800279c0  xor     ecx, ecx; ServiceHandle
0x1800279c2  mov     [rsp+0D0h+pOutput], rdx; pOutput
0x1800279c7  mov     edx, r12d; ConfigId
0x1800279ca  call    cs:__imp_HttpQueryServiceConfiguration
0x1800279d0  cmp     eax, 7Ah ; 'z'
0x1800279d3  jnz     loc_180027A59
0x1800279d9  lea     ecx, [rax-4Ah]; Size
0x1800279dc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800279e1  xor     edx, edx
0x1800279e3  test    rax, rax
0x1800279e6  jz      loc_180027A84
0x1800279ec  mov     rcx, rax
0x1800279ef  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x1800279f5  xor     edx, edx
0x1800279f7  mov     r15, rax
0x1800279fa  test    rax, rax
0x1800279fd  jz      loc_180027A84
0x180027a03  mov     edx, [rbp+57h+arg_18]
0x180027a06  mov     rcx, rax
0x180027a09  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180027a0f  test    al, al
0x180027a11  jnz     short loc_180027A1D
0x180027a13  mov     edi, 80070008h
0x180027a18  jmp     loc_1800283AC
0x180027a1d  mov     ebx, [rbp+57h+arg_18]
0x180027a20  mov     rcx, r15
0x180027a23  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180027a29  mov     [rsp+0D0h+pOverlapped], r14; pOverlapped
0x180027a2e  lea     rcx, [rbp+57h+arg_18]
0x180027a32  mov     [rsp+0D0h+pReturnLength], rcx; pReturnLength
0x180027a37  lea     r8, [rbp+57h+pInput]; pInput
0x180027a3b  mov     [rsp+0D0h+OutputLength], ebx; OutputLength
0x180027a3f  xor     ecx, ecx; ServiceHandle
0x180027a41  mov     r9d, 18h; InputLength
0x180027a47  mov     [rsp+0D0h+pOutput], rax; pOutput
0x180027a4c  mov     edx, r12d; ConfigId
0x180027a4f  call    cs:__imp_HttpQueryServiceConfiguration
0x180027a55  mov     [rbp+57h+var_88], r15
0x180027a59  test    eax, eax
0x180027a5b  jz      short loc_180027A8E
0x180027a5d  jle     short loc_180027A67
0x180027a5f  movzx   eax, ax
0x180027a62  or      eax, 80070000h
0x180027a67  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x180027a6e  lea     rdx, aHttpqueryservi; "HttpQueryServiceConfiguration failed er"...
0x180027a75  mov     r8d, eax
0x180027a78  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x180027a7d  xor     edx, edx
0x180027a7f  jmp     loc_1800283A7
0x180027a84  mov     edi, 80070008h
0x180027a89  jmp     loc_1800283B6
0x180027a8e  mov     rcx, r15
0x180027a91  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180027a97  lea     rbx, [r13+0B8h]
0x180027a9e  mov     r14d, 1587h
0x180027aa4  mov     edx, r14d; unsigned int
0x180027aa7  mov     [rbp+57h+var_58], rbx
0x180027aab  mov     rcx, rbx; this
0x180027aae  lea     r8, [rbp+57h+var_90]; struct PROPERTY_ENTRY **
0x180027ab2  mov     r15, rax
0x180027ab5  call    ?FindEntry@PROPERTY_BAG@@QEAAJKPEAPEAVPROPERTY_ENTRY@@@Z; PROPERTY_BAG::FindEntry(ulong,PROPERTY_ENTRY * *)
0x180027aba  mov     edi, eax
0x180027abc  mov     eax, 80000000h
0x180027ac1  lea     ecx, [rdi+rax]
0x180027ac4  test    eax, ecx
0x180027ac6  jnz     short loc_180027ADF
0x180027ac8  cmp     edi, 80070002h
0x180027ace  jz      short loc_180027ADF
0x180027ad0  mov     r14, [rbp+57h+var_90]
0x180027ad4  xor     edx, edx
0x180027ad6  mov     r15, [rbp+57h+var_88]
0x180027ada  jmp     loc_18002841C
0x180027adf  mov     ecx, 50h ; 'P'; Size
0x180027ae4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180027ae9  xor     edx, edx
0x180027aeb  test    rax, rax
0x180027aee  jz      loc_180028405
0x180027af4  mov     edx, r12d; int
0x180027af7  mov     rcx, rax; this
0x180027afa  call    ??0PROPERTY_ENTRY@@QEAA@H@Z; PROPERTY_ENTRY::PROPERTY_ENTRY(int)
0x180027aff  xor     edx, edx
0x180027b01  mov     rsi, rax
0x180027b04  test    rax, rax
0x180027b07  jz      loc_180028405
0x180027b0d  or      r13, 0FFFFFFFFFFFFFFFFh
0x180027b11  mov     [rbp+57h+var_80.dwMDIdentifier], r14d
0x180027b15  mov     r14, [rbp+57h+var_90]
0x180027b19  mov     dword ptr [rbp+57h+var_80+14h], edx
0x180027b1c  mov     qword ptr [rbp+57h+var_80.dwMDDataTag], rdx
0x180027b20  mov     [rbp+57h+var_80.dwMDAttributes], r12d
0x180027b24  mov     [rbp+57h+var_80.dwMDDataType], 2
0x180027b2b  mov     [rbp+57h+var_80.dwMDUserType], r12d
0x180027b2f  test    r15, r15
0x180027b32  jz      loc_180027BBA
0x180027b38  mov     rcx, [r15+28h]
0x180027b3c  test    rcx, rcx
0x180027b3f  jz      short loc_180027BBA
0x180027b41  mov     rax, r13
0x180027b44  inc     rax
0x180027b47  cmp     [rcx+rax*2], dx
0x180027b4b  jnz     short loc_180027B44
0x180027b4d  test    rax, rax
0x180027b50  jz      short loc_180027BBA
0x180027b52  test    edi, edi
0x180027b54  js      short loc_180027B7A
0x180027b56  lea     rcx, [r14+10h]
0x180027b5a  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180027b60  lea     rcx, [r14+10h]
0x180027b64  mov     rdx, [rax+18h]
0x180027b68  mov     [rbp+57h+var_80.pbMDData], rdx
0x180027b6c  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180027b72  mov     ecx, [rax+10h]
0x180027b75  mov     [rbp+57h+var_80.dwMDDataLen], ecx
0x180027b78  jmp     short loc_180027B88
0x180027b7a  lea     eax, ds:2[rax*2]
0x180027b81  mov     [rbp+57h+var_80.pbMDData], rcx
0x180027b85  mov     [rbp+57h+var_80.dwMDDataLen], eax
0x180027b88  lea     rdx, [rbp+57h+var_80]; struct _METADATA_RECORD *
0x180027b8c  mov     rcx, rsi; this
0x180027b8f  call    ?Create@PROPERTY_ENTRY@@QEAAJPEAU_METADATA_RECORD@@@Z; PROPERTY_ENTRY::Create(_METADATA_RECORD *)
0x180027b94  xor     edx, edx
0x180027b96  mov     edi, eax
0x180027b98  test    eax, eax
0x180027b9a  js      loc_18002840E
0x180027ba0  mov     r8d, r12d; int
0x180027ba3  mov     rdx, rsi; struct PROPERTY_ENTRY *
0x180027ba6  mov     rcx, rbx; this
0x180027ba9  call    ?AddEntry@PROPERTY_BAG@@QEAAJPEAVPROPERTY_ENTRY@@H@Z; PROPERTY_BAG::AddEntry(PROPERTY_ENTRY *,int)
0x180027bae  xor     edx, edx
0x180027bb0  mov     edi, eax
0x180027bb2  test    eax, eax
0x180027bb4  js      loc_18002840E
0x180027bba  mov     rcx, rsi; this
0x180027bbd  call    ?DereferencePropertyMapping@PROPERTY_MAPPING@@QEAAXXZ; PROPERTY_MAPPING::DereferencePropertyMapping(void)
0x180027bc2  xor     edi, edi
0x180027bc4  test    r14, r14
0x180027bc7  jz      short loc_180027BD5
0x180027bc9  mov     rcx, r14; this
0x180027bcc  call    ?DereferencePropertyMapping@PROPERTY_MAPPING@@QEAAXXZ; PROPERTY_MAPPING::DereferencePropertyMapping(void)
0x180027bd1  mov     [rbp+57h+var_90], rdi
0x180027bd5  mov     r14d, 1582h
0x180027bdb  lea     r8, [rbp+57h+var_90]; struct PROPERTY_ENTRY **
0x180027bdf  mov     edx, r14d; unsigned int
0x180027be2  mov     rcx, rbx; this
0x180027be5  call    ?FindEntry@PROPERTY_BAG@@QEAAJKPEAPEAVPROPERTY_ENTRY@@@Z; PROPERTY_BAG::FindEntry(ulong,PROPERTY_ENTRY * *)
0x180027bea  mov     ecx, 80000000h
0x180027bef  mov     edi, eax
0x180027bf1  add     eax, ecx
0x180027bf3  test    ecx, eax
0x180027bf5  jnz     short loc_180027C08
0x180027bf7  cmp     edi, 80070002h
0x180027bfd  jz      short loc_180027C08
0x180027bff  xor     edx, edx
0x180027c01  mov     esi, edx
0x180027c03  jmp     loc_18002840A
0x180027c08  mov     ecx, 50h ; 'P'; Size
0x180027c0d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180027c12  xor     edx, edx
0x180027c14  test    rax, rax
0x180027c17  jz      loc_180028402
0x180027c1d  mov     edx, r12d; int
0x180027c20  mov     rcx, rax; this
0x180027c23  call    ??0PROPERTY_ENTRY@@QEAA@H@Z; PROPERTY_ENTRY::PROPERTY_ENTRY(int)
0x180027c28  xor     edx, edx
0x180027c2a  mov     rsi, rax
0x180027c2d  test    rax, rax
0x180027c30  jz      loc_180028405
0x180027c36  mov     [rbp+57h+var_80.dwMDIdentifier], r14d
0x180027c3a  mov     r14, [rbp+57h+var_90]
0x180027c3e  mov     dword ptr [rbp+57h+var_80+14h], edx
0x180027c41  mov     qword ptr [rbp+57h+var_80.dwMDDataTag], rdx
0x180027c45  mov     [rbp+57h+var_80.dwMDDataType], 3
0x180027c4c  test    r15, r15
0x180027c4f  jz      loc_180027CFC
0x180027c55  cmp     [r15+10h], rdx
0x180027c59  jz      loc_180027CFC
0x180027c5f  cmp     [r15+8], edx
0x180027c63  jbe     loc_180027CFC
0x180027c69  mov     ecx, [r15+8]; Size
0x180027c6d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180027c72  xor     edx, edx
0x180027c74  mov     [rbp+57h+var_80.pbMDData], rax
0x180027c78  test    rax, rax
0x180027c7b  jnz     short loc_180027C87
0x180027c7d  mov     edi, 80070008h
0x180027c82  jmp     loc_18002840E
0x180027c87  test    edi, edi
0x180027c89  js      short loc_180027CB3
0x180027c8b  lea     rcx, [r14+10h]
0x180027c8f  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180027c95  lea     rcx, [r14+10h]
0x180027c99  mov     rdx, [rax+18h]
0x180027c9d  mov     [rbp+57h+var_80.pbMDData], rdx
0x180027ca1  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180027ca7  mov     rbx, [rbp+57h+var_58]
0x180027cab  mov     ecx, [rax+10h]
0x180027cae  mov     [rbp+57h+var_80.dwMDDataLen], ecx
0x180027cb1  jmp     short loc_180027CCA
0x180027cb3  mov     r8d, [r15+8]; Size
0x180027cb7  mov     rcx, rax; void *
0x180027cba  mov     rdx, [r15+10h]; Src
0x180027cbe  call    memcpy_0
0x180027cc3  mov     eax, [r15+8]
0x180027cc7  mov     [rbp+57h+var_80.dwMDDataLen], eax
0x180027cca  lea     rdx, [rbp+57h+var_80]; struct _METADATA_RECORD *
0x180027cce  mov     rcx, rsi; this
0x180027cd1  call    ?Create@PROPERTY_ENTRY@@QEAAJPEAU_METADATA_RECORD@@@Z; PROPERTY_ENTRY::Create(_METADATA_RECORD *)
0x180027cd6  xor     edx, edx
0x180027cd8  mov     edi, eax
0x180027cda  test    eax, eax
0x180027cdc  js      loc_18002840E
0x180027ce2  mov     r8d, r12d; int
0x180027ce5  mov     rdx, rsi; struct PROPERTY_ENTRY *
0x180027ce8  mov     rcx, rbx; this
0x180027ceb  call    ?AddEntry@PROPERTY_BAG@@QEAAJPEAVPROPERTY_ENTRY@@H@Z; PROPERTY_BAG::AddEntry(PROPERTY_ENTRY *,int)
0x180027cf0  xor     edx, edx
0x180027cf2  mov     edi, eax
0x180027cf4  test    eax, eax
0x180027cf6  js      loc_18002840E
0x180027cfc  mov     rcx, rsi; this
0x180027cff  call    ?DereferencePropertyMapping@PROPERTY_MAPPING@@QEAAXXZ; PROPERTY_MAPPING::DereferencePropertyMapping(void)
0x180027d04  xor     edi, edi
0x180027d06  test    r14, r14
0x180027d09  jz      short loc_180027D17
0x180027d0b  mov     rcx, r14; this
0x180027d0e  call    ?DereferencePropertyMapping@PROPERTY_MAPPING@@QEAAXXZ; PROPERTY_MAPPING::DereferencePropertyMapping(void)
0x180027d13  mov     [rbp+57h+var_90], rdi
0x180027d17  mov     r14d, 1588h
0x180027d1d  lea     r8, [rbp+57h+var_90]; struct PROPERTY_ENTRY **
0x180027d21  mov     edx, r14d; unsigned int
0x180027d24  mov     rcx, rbx; this
0x180027d27  call    ?FindEntry@PROPERTY_BAG@@QEAAJKPEAPEAVPROPERTY_ENTRY@@@Z; PROPERTY_BAG::FindEntry(ulong,PROPERTY_ENTRY * *)
0x180027d2c  mov     ecx, 80000000h
  ... truncated ...
```
