# CheckIndexHeaderRecurse

- ea: `0x1401386b0`
- end: `0x1401392aa`
- name: `CheckIndexHeaderRecurse`
- size: `3066`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1401392b0`
- `0x1401393d0`

## callees

- `0x14007eb38`
- `0x1400830f4`
- `0x1400834f0`
- `0x1400a76d0`
- `0x1400b9ae4`
- `0x1400e7d58`
- `0x1400e7ea0`
- `0x1400e8234`
- `0x1400e95fc`
- `0x1401386b0`
- `0x1401392b0`
- `0x14013957c`
- `0x1401395b4`
- `0x1401395e8`
- `0x1401b9010`

## string_xrefs

- `0x140138a68`: `!(offset + sizeof(SmsIndexEntry) <= maxIndexEntryLocation)`
- `0x140138ec5`: `!(offset + sizeof(SmsIndexEntry) <= maxIndexEntryLocation)`
- `0x140138d95`: `!(dataLength >= sizeof(SmsIndexRoot))`
- `0x140138954`: `!(length >= run.GetChecksumSizeInBytes(&checker.Volume))`
- `0x140138ea3`: `!(length >= sizeof(SmsIndexEntry))`
- `0x140138de8`: `!(checksumBlob.ChecksumSizeInBytes == checker.Volume.GetChecksumSizeInBytesForOnePage())`
- `0x140138e1b`: `!(checksumBlob.ChecksumOffset + limits_add(checksumBlob.ChecksumSizeInBytes, ((ULONG)__builtin_offsetof(SmsDirectorData, ChecksumBlob))) <= ie->DataLength)`
- `0x1401386e6`: `!(indexHeader.FirstIndexEntry >= sizeof(SmsIndexHeader))`
- `0x140138aad`: `!(indexHeader.NumberIndexEntryOffsets == nonDeletedEntryCount)`
- `0x140138f27`: `!(indexHeader.NumberIndexEntryOffsets == nonDeletedEntryCount)`
- `0x140138ffa`: `!(lastDeleted || offsetEntry.Offset < maxIndexEntryLocation)`
- `0x1401390aa`: `!(indexHeader.NextInsertOffset + sizeof(SmsIndexEntryOffset) <= indexHeader.FirstIndexEntryOffset)`
- `0x140139103`: `!NT_SUCCESS(checkOneOffsetEntry(lastDeletedOffset, true))`

## pseudocode

```c
__int64 __fastcall CheckIndexHeaderRecurse(unsigned int *a1, unsigned int a2, __int64 a3, __int64 *a4)
{
  __int64 *v4; // r12
  const char *v7; // rax
  __int64 v8; // rdx
  unsigned int v9; // ebx
  unsigned int v10; // edx
  unsigned __int8 v11; // al
  __int64 v12; // r9
  char v13; // al
  unsigned int v14; // edx
  __int64 v15; // r8
  const char *v16; // rax
  __int64 v17; // rdx
  int v18; // eax
  __int64 v19; // rcx
  int v20; // r9d
  SmsRunHeader *v21; // rbx
  unsigned __int64 v22; // r10
  __int16 v23; // ax
  unsigned int v24; // r12d
  __int64 v25; // rdx
  const char *v26; // rax
  __int64 v27; // rdx
  __int64 v28; // r11
  int v29; // eax
  int v30; // ecx
  char *v31; // rbx
  unsigned __int64 v32; // r9
  unsigned __int16 v33; // r10
  unsigned int v34; // edx
  unsigned __int64 v35; // r13
  int v36; // ecx
  unsigned int v37; // r8d
  __int64 v38; // rdx
  unsigned __int64 v39; // r9
  unsigned int v40; // r13d
  __int64 v41; // rcx
  const struct SmsInternalPropertyDef *PropertyDef; // rax
  __int64 v43; // r8
  __int64 v44; // r9
  __int64 v45; // rdx
  __int64 v46; // rcx
  const char *v47; // rax
  __int64 v48; // rdx
  unsigned __int16 *v49; // rbx
  unsigned __int16 *v50; // rax
  unsigned __int16 *v51; // rdx
  unsigned int v52; // ecx
  unsigned __int64 v53; // r11
  __int64 v54; // r10
  __int64 v55; // r9
  __int64 v56; // rdx
  const char *v57; // rax
  __int64 v58; // r13
  unsigned __int64 v59; // rcx
  __int64 v60; // rcx
  __int64 v61; // rdx
  const char *v62; // rax
  unsigned __int8 (__fastcall *v63)(__int64, __int64, _QWORD *); // r9
  __int64 v64; // r10
  __int64 v65; // r11
  __int64 v66; // r9
  unsigned __int16 *v67; // rdx
  int v68; // eax
  const char *v70; // [rsp+30h] [rbp-41h]
  unsigned int v71; // [rsp+38h] [rbp-39h]
  int v72; // [rsp+3Ch] [rbp-35h]
  int v73; // [rsp+3Ch] [rbp-35h]
  unsigned int v74; // [rsp+40h] [rbp-31h]
  int v75; // [rsp+44h] [rbp-2Dh]
  unsigned int v76; // [rsp+48h] [rbp-29h]
  unsigned __int64 v77; // [rsp+50h] [rbp-21h]
  unsigned int v78; // [rsp+50h] [rbp-21h]
  unsigned __int64 v79; // [rsp+58h] [rbp-19h]
  unsigned __int64 v80; // [rsp+58h] [rbp-19h]
  unsigned int v81; // [rsp+60h] [rbp-11h]
  _DWORD v82[2]; // [rsp+68h] [rbp-9h] BYREF
  __int16 v83; // [rsp+70h] [rbp-1h]
  char v84; // [rsp+72h] [rbp+1h]
  char v85; // [rsp+73h] [rbp+2h]
  char v86; // [rsp+74h] [rbp+3h]
  char *v87; // [rsp+78h] [rbp+7h]
  _QWORD v88[2]; // [rsp+80h] [rbp+Fh] BYREF
  CmsVolume *v89; // [rsp+90h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+5Fh]
  char v91; // [rsp+D8h] [rbp+67h]
  int v92; // [rsp+D8h] [rbp+67h]

  v4 = a4;
  if ( *a1 < 0x28 )
  {
    v7 = "!(indexHeader.FirstIndexEntry >= sizeof(SmsIndexHeader))";
    v8 = 486;
    goto LABEL_212;
  }
  v9 = a1[1];
  v81 = v9;
  if ( v9 < *a1 )
  {
    v7 = "!(indexHeader.NextInsertOffset >= indexHeader.FirstIndexEntry)";
    v8 = 489;
    goto LABEL_212;
  }
  if ( a1[4] < v9 )
  {
    v7 = "!(indexHeader.FirstIndexEntryOffset >= indexHeader.NextInsertOffset)";
    v8 = 493;
    goto LABEL_212;
  }
  v10 = a1[8];
  if ( v10 < a1[4] )
  {
    v7 = "!(indexHeader.EndOfBucketOffset >= indexHeader.FirstIndexEntryOffset)";
    v8 = 496;
    goto LABEL_212;
  }
  if ( v10 - a1[4] < 4 * (unsigned __int64)a1[5] )
  {
    v7 = "!(indexHeader.EndOfBucketOffset - indexHeader.FirstIndexEntryOffset >= indexEntryOffsetArraySize)";
    v8 = 500;
    goto LABEL_212;
  }
  if ( v10 > a2 )
  {
    v7 = "!(indexHeader.EndOfBucketOffset <= length)";
    v8 = 503;
    goto LABEL_212;
  }
  v11 = *((_BYTE *)a1 + 12);
  if ( (*((_BYTE *)a1 + 13) & 1) != 0 )
  {
    if ( !v11 )
    {
      v7 = "!(indexHeader.Level != 0)";
      v8 = 516;
      goto LABEL_212;
    }
    if ( v11 >= 0xF8u )
    {
      v7 = "!(indexHeader.Level < ROOT_LEVEL)";
      v8 = 520;
      goto LABEL_212;
    }
  }
  else if ( v11 )
  {
    v7 = "!(indexHeader.Level == 0)";
    v8 = 522;
    goto LABEL_212;
  }
  v89 = (CmsVolume *)a4[5];
  if ( v9 > *((_DWORD *)v89 + 809) )
  {
    v7 = "!(maxIndexEntryLocation <= volume.VolumePageSize)";
    v8 = 528;
    goto LABEL_212;
  }
  if ( (*(_BYTE *)a1 & 7) != 0 )
  {
    v7 = "!(bAligned)";
    v8 = 533;
    goto LABEL_212;
  }
  anonymous_namespace_::IndexEntryChecker::PushIndexHeader(a4, v82, a1, a3);
  if ( !*((_BYTE *)v4 + 35) && (v9 & 7) != 0 )
  {
    v7 = "!(checker.CheckAlignment(maxIndexEntryLocation))";
    v8 = 537;
    goto LABEL_212;
  }
  if ( (*(_BYTE *)(v12 + 44) & 4) != 0 )
  {
    v91 = *((_BYTE *)a1 + 12);
    if ( !v91 )
    {
      v13 = 1;
      goto LABEL_32;
    }
    v91 = *((_BYTE *)a1 + 12);
  }
  else
  {
    v91 = *((_BYTE *)a1 + 12);
  }
  v13 = 0;
LABEL_32:
  v14 = a1[1];
  v15 = a1[4] - v14;
  v76 = v14;
  v71 = a1[4] - v14;
  if ( v13 )
  {
    if ( a1[2] >= (unsigned int)v15 )
    {
      v19 = *a1;
      v20 = 0;
      v92 = 0;
      v21 = (SmsRunHeader *)((char *)a1 + v19);
      if ( (unsigned int)v19 >= v14 )
      {
LABEL_69:
        if ( *((_BYTE *)a1 + 12) )
        {
          v16 = "!(endEntryCount == 1)";
          v17 = 459;
        }
        else if ( a1[2] == (_DWORD)v15 )
        {
          if ( a1[5] == v20 )
          {
            v18 = 0;
            goto LABEL_76;
          }
          v16 = "!(indexHeader.NumberIndexEntryOffsets == nonDeletedEntryCount)";
          v17 = 465;
        }
        else
        {
          v16 = "!(indexHeader.BytesAvailable == freeSpace)";
          v17 = 464;
        }
      }
      else
      {
        v22 = a1[1];
        v77 = v22;
        while ( (unsigned __int64)(unsigned int)v19 + 16 <= v22 )
        {
          v23 = *((_WORD *)v21 + 4) & 0x40;
          if ( v23 )
            v24 = (*((unsigned __int16 *)v21 + 5) + 7) & 0xFFFFFFF8;
          else
            v24 = *(_DWORD *)v21;
          if ( (*((_BYTE *)v21 + 8) & 4) != 0 )
          {
            v25 = v24;
            if ( v24 + (unsigned __int64)(unsigned int)v19 > v22 )
            {
              v16 = "!(limits_add(offset, length) <= maxIndexEntryLocation)";
              v17 = 311;
              goto LABEL_35;
            }
            LODWORD(v19) = v24 + v19;
          }
          else
          {
            if ( !v23 )
            {
              v16 = "IsYes(isStream)";
              v17 = 364;
              goto LABEL_35;
            }
            v72 = v24 + v19;
            if ( v24 + (unsigned int)v19 > v14 )
            {
              v16 = "!(offset + length <= maxIndexEntryLocation)";
              v17 = 327;
              goto LABEL_35;
            }
            anonymous_namespace_::IndexEntryChecker::MarkIndexEntryOffset(a4, (unsigned int)v19);
            if ( (*((_WORD *)v21 + 4) & 0xF007) != 0 )
            {
              v16 = "!(!IsFlagOn(ie->Flags, ~INDEX_IE_ALL_STREAM_FLAGS))";
              v17 = 332;
              goto LABEL_35;
            }
            if ( SmsRunHeader::HasChecksums(v21) )
            {
              if ( v24 < SmsRunHeader::GetChecksumSizeInBytes(v21, (const struct CmsVolume *)a4[5]) )
              {
                v16 = "!(length >= run.GetChecksumSizeInBytes(&checker.Volume))";
                v17 = 340;
                goto LABEL_35;
              }
            }
            else if ( v24 < 0x18 )
            {
              v16 = "!(length >= sizeof(SmsRunHeader))";
              v17 = 343;
              goto LABEL_35;
            }
            if ( SmsRunHeader::IsGhosted(v21) )
            {
              v79 = (unsigned __int16)(SmsRunHeader::GetChecksumSizeInBytes(v21, (const struct CmsVolume *)a4[5]) + 56);
              if ( v79 > v24 )
              {
                v16 = "!(recallBufferOffset <= length)";
                v17 = 350;
                goto LABEL_35;
              }
              if ( v79 + *((unsigned int *)SmsRun::GetRecallMetadataHeader(v21, (const struct CmsVolume *)a4[5]) + 6) > v24 )
              {
                v16 = "!(recallBufferEndOffset <= length)";
                v17 = 355;
                goto LABEL_35;
              }
            }
            LODWORD(v19) = v72;
            v20 = v92;
            v22 = v77;
            v25 = v24;
          }
          v15 = v71;
          if ( (*((_BYTE *)v21 + 8) & 4) != 0 )
          {
            v15 = v24 + v71;
            v71 += v24;
          }
          else
          {
            v92 = ++v20;
          }
          if ( (unsigned int)v19 >= v76 )
            goto LABEL_69;
          v21 = (SmsRunHeader *)((char *)v21 + v25);
          v14 = v76;
        }
        v16 = "!(offset + sizeof(SmsIndexEntry) <= maxIndexEntryLocation)";
        v17 = 301;
      }
    }
    else
    {
      v16 = "!(indexHeader.BytesAvailable >= freeSpace)";
      v17 = 287;
    }
LABEL_35:
    wil::details::in1diag3::Return_NtStatusMsg(
      retaddr,
      (void *)v17,
      (unsigned int)"minkernel\\fs\\minstore\\checksup.cpp",
      (const char *)0xC0000518LL,
      (int)v16,
      v70);
    v18 = -1073740520;
LABEL_76:
    v4 = a4;
    goto LABEL_162;
  }
  if ( a1[2] < (unsigned int)v15 )
  {
    v26 = "!(indexHeader.BytesAvailable >= freeSpace)";
    v27 = 287;
    goto LABEL_79;
  }
  v28 = *a1;
  v29 = 0;
  v78 = *a1;
  v30 = 0;
  v73 = 0;
  v75 = 0;
  v31 = (char *)a1 + v28;
  if ( (unsigned int)v28 < v14 )
  {
    v32 = a1[1];
    v80 = v32;
    while ( 1 )
    {
      if ( v28 + 16 > v32 )
      {
        v26 = "!(offset + sizeof(SmsIndexEntry) <= maxIndexEntryLocation)";
        v27 = 301;
        goto LABEL_79;
      }
      v33 = *((_WORD *)v31 + 4);
      v34 = (v33 & 0x40) != 0 ? (*((unsigned __int16 *)v31 + 5) + 7) & 0xFFFFFFF8 : *(_DWORD *)v31;
      v74 = v34;
      if ( (v33 & 4) != 0 )
      {
        v35 = v34;
        if ( v28 + (unsigned __int64)v34 > v32 )
        {
          v26 = "!(limits_add(offset, length) <= maxIndexEntryLocation)";
          v27 = 311;
          goto LABEL_79;
        }
      }
      else
      {
        if ( (v33 & 0x40) != 0 )
        {
          v26 = "!(IsYes(isStream))";
          v27 = 321;
          goto LABEL_79;
        }
        if ( !*((_BYTE *)v4 + 35) && (v34 & 7) != 0 )
        {
          v26 = "!(checker.CheckAlignment(length))";
          v27 = 375;
          goto LABEL_79;
        }
        if ( v34 < 0x10 )
        {
          v26 = "!(length >= sizeof(SmsIndexEntry))";
          v27 = 377;
          goto LABEL_79;
        }
        v35 = v34;
        v88[0] = v34;
        if ( v28 + (unsigned __int64)v34 > v32 )
        {
          v26 = "!(limits_add(offset, length) <= maxIndexEntryLocation)";
          v27 = 380;
          goto LABEL_79;
        }
        v36 = *((unsigned __int16 *)v31 + 2);
        v37 = v36 + *((unsigned __int16 *)v31 + 3);
        if ( v37 > v34 )
        {
          v26 = "!(endOfKey <= length)";
          v27 = 384;
          goto LABEL_79;
        }
        v38 = *((unsigned __int16 *)v31 + 5);
        v39 = v38 + *((unsigned int *)v31 + 3);
        if ( v39 > v35 )
        {
          v26 = "!(endOfData <= length)";
          v27 = 387;
          goto LABEL_79;
        }
        if ( *((_BYTE *)v4 + 36) )
          LOWORD(v36) = v36 + 8;
        if ( (unsigned __int16)v36 < (unsigned __int16)v38 )
        {
          if ( v37 > (unsigned int)v38 )
          {
            v26 = "!(endOfKey <= ie->DataOffset)";
            v27 = 399;
            goto LABEL_79;
          }
        }
        else if ( v37 > v39 )
        {
          v26 = "!(endOfKey <= endOfData)";
          v27 = 397;
          goto LABEL_79;
        }
        if ( (v33 & (_WORD)v4[4]) != 0 )
        {
          v26 = "!(checker.OnlyAllowedFlags(ie->Flags))";
          v27 = 402;
          goto LABEL_79;
        }
        if ( (v33 & 2) != 0 )
          ++v73;
        anonymous_namespace_::IndexEntryChecker::MarkIndexEntryOffset(v4, (unsigned int)v28);
        if ( (v31[8] & 1) == 0
          || *((_BYTE *)a1 + 12)
          || (unsigned __int8)anonymous_namespace_::IndexEntryChecker::IsSpuriousEmbeddedRoot(v4, v31) )
        {
          if ( v91 )
          {
            if ( *((_DWORD *)v31 + 3) < 0x28u )
            {
              v26 = "!(ie->DataLength >= sizeof(SmsDirectorData))";
              v27 = 429;
              goto LABEL_79;
            }
            if ( *((_DWORD *)v31 + 3) > 0x48u )
            {
              v26 = "!(ie->DataLength <= MAX_DIRECTOR_DATA_SIZE)";
              v27 = 430;
              goto LABEL_79;
            }
            v43 = *((unsigned __int16 *)v31 + 5);
            v44 = *(unsigned int *)&v31[v43 + 36];
            v45 = (unsigned __int8)v31[v43 + 35];
            if ( v45 + v44 + 32 > (unsigned __int64)*((unsigned int *)v31 + 3) )
            {
              v26 = "!(checksumBlob.ChecksumOffset + limits_add(checksumBlob.ChecksumSizeInBytes, ((ULONG)__builtin_offse"
                    "tof(SmsDirectorData, ChecksumBlob))) <= ie->DataLength)";
              v27 = 436;
              goto LABEL_79;
            }
            if ( (_BYTE)v45 != 8 )
            {
              v26 = "!(checksumBlob.ChecksumOffset == sizeof(SmsChecksumBlob))";
              v27 = 439;
              goto LABEL_79;
            }
            v46 = v4[5];
            if ( v31[v43 + 34] != *(_BYTE *)(v46 + 88) )
            {
              v26 = "!(checksumBlob.ChecksumType == checker.Volume.ChecksumType)";
              v27 = 442;
              goto LABEL_79;
            }
            if ( (_DWORD)v44 != *(_DWORD *)(v46 + 3480) )
            {
              v26 = "!(checksumBlob.ChecksumSizeInBytes == checker.Volume.GetChecksumSizeInBytesForOnePage())";
              v27 = 443;
              goto LABEL_79;
            }
          }
        }
        else
        {
          if ( (v31[10] & 7) != 0 )
          {
            v26 = "!(bAligned)";
            v27 = 418;
            goto LABEL_79;
          }
          v40 = *((_DWORD *)v31 + 3);
          if ( (v40 & 7) != 0 )
          {
            v26 = "!(bAligned)";
            v27 = 421;
            goto LABEL_79;
          }
          if ( v40 < 0x28 )
          {
            v47 = "!(dataLength >= sizeof(SmsIndexRoot))";
            v48 = 257;
            goto LABEL_133;
          }
          v41 = v4[5];
          v87 = &v31[*((unsigned __int16 *)v31 + 5)];
          PropertyDef = CmsSchemaTable::GetPropertyDef(*(CmsSchemaTable **)(v41 + 3272), *((_DWORD *)v87 + 3));
          if ( !PropertyDef )
          {
            v47 = "!(embeddedPropertyDef != nullptr)";
            v48 = 259;
            goto LABEL_133;
          }
          if ( *((_DWORD *)PropertyDef + 6) > v40 && (*((_DWORD *)PropertyDef + 11) & 0x1000) == 0 )
          {
            v47 = "!(embeddedPropertyDef->InitialSizeOfRoot <= dataLength || ( (((embeddedPropertyDef->Flags) & (PD_VARIA"
                  "BLE_ROOT_SIZE))) ))";
            v48 = 261;
LABEL_133:
            wil::details::in1diag3::Return_NtStatusMsg(
              retaddr,
              (void *)v48,
              (unsigned int)"minkernel\\fs\\minstore\\checksup.cpp",
              (const char *)0xC0000518LL,
              (int)v47,
              v70);
LABEL_134:
            v26 = "!NT_SUCCESS(CheckEmbeddedRoot(*ie->ToIndexRoot(), ie->DataLength, checker))";
            v27 = 426;
            goto LABEL_79;
          }
          if ( (int)CheckIndexRootRecurse(v87, v40, PropertyDef, v4) < 0 )
            goto LABEL_134;
          v35 = v88[0];
        }
        v34 = v74;
        LODWORD(v28) = v78;
        v15 = v71;
        v32 = v80;
      }
      v30 = v75;
      if ( (v31[8] & 4) != 0 )
      {
        v15 = v34 + (unsigned int)v15;
        v71 = v15;
      }
      else
      {
        v30 = ++v75;
      }
      v28 = v34 + (unsigned int)v28;
      v78 = v28;
      if ( (unsigned int)v28 >= v76 )
        break;
      v31 += v35;
    }
    v29 = v73;
  }
  if ( *((_BYTE *)a1 + 12) )
  {
    if ( v29 != 1 )
    {
      v26 = "!(endEntryCount == 1)";
      v27 = 459;
LABEL_79:
      wil::details::in1diag3::Return_NtStatusMsg(
        retaddr,
        (void *)v27,
        (unsigned int)"minkernel\\fs\\minstore\\checksup.cpp",
        (const char *)0xC0000518LL,
        (int)v26,
        v70);
      v18 = -1073740520;
      goto LABEL_162;
    }
  }
  else if ( v29 )
  {
    v26 = "!(endEntryCount == 0)";
    v27 = 461;
    goto LABEL_79;
  }
  if ( a1[2] != (_DWORD)v15 )
  {
    v26 = "!(indexHeader.BytesAvailable == freeSpace)";
    v27 = 464;
    goto LABEL_79;
  }
  if ( a1[5] != v30 )
  {
    v26 = "!(indexHeader.NumberIndexEntryOffsets == nonDeletedEntryCount)";
    v27 = 465;
    goto LABEL_79;
  }
  v18 = 0;
LABEL_162:
  if ( v18 < 0 )
  {
    v7 = "!NT_SUCCESS(status)";
    v8 = 553;
    goto LABEL_212;
  }
  v49 = (unsigned __int16 *)((char *)a1 + a1[4]);
  v50 = v49;
  v51 = &v49[2 * a1[5]];
  while ( v50 != v51 )
  {
    v15 = *v50;
    if ( (unsigned int)v15 < *a1 )
    {
      v56 = 560;
      v57 = "!(offsetEntry.Offset >= indexHeader.FirstIndexEntry)";
      goto LABEL_177;
    }
    if ( (unsigned int)v15 >= v81 )
    {
      v56 = 561;
      v57 = "!(lastDeleted || offsetEntry.Offset < maxIndexEntryLocation)";
      goto LABEL_177;
    }
    if ( !*((_BYTE *)v4 + 35) )
    {
      if ( (v15 & 7) != 0 )
      {
        v56 = 562;
        v57 = "!(checker.CheckAlignment(offsetEntry.Offset))";
LABEL_177:
        wil::details::in1diag3::Return_NtStatusMsg(
          retaddr,
          (void *)v56,
          (unsigned int)"minkernel\\fs\\minstore\\checksup.cpp",
          (const char *)0xC0000518LL,
          (int)v57,
          v70);
        v7 = "!NT_SUCCESS(checkOneOffsetEntry(offsetEntry, false))";
        v8 = 568;
        goto LABEL_212;
      }
      if ( !*((_BYTE *)v4 + 35) )
      {
        v52 = v15 + *((_DWORD *)v4 + 6);
        v15 = *v4;
        v53 = v52 >> 3;
        v54 = 1LL << v53;
        v53 >>= 6;
        v55 = *(_QWORD *)(*v4 + 8 * v53);
        *(_QWORD *)(*v4 + 8 * v53) = v55 & ~v54;
        if ( (v54 & v55) == 0 )
        {
          v7 = "!(checker.CheckAndClearIndexEntryOffset(offsetEntry.Offset))";
          v8 = 570;
          goto LABEL_212;
        }
      }
    }
    v50 += 2;
  }
  LODWORD(v58) = a1[5];
  if ( *((_BYTE *)a1 + 12) )
  {
    if ( !(_DWORD)v58 )
    {
      v7 = "!(indexHeader.NumberIndexEntryOffsets > 0)";
      v8 = 579;
      goto LABEL_212;
    }
    v58 = (unsigned int)(v58 - 1);
    if ( (*((_BYTE *)a1 + *(unsigned __int16 *)((char *)&a1[v58] + a1[4]) + 8) & 2) == 0 )
    {
      v7 = "!(endEntry.IsEndEntry())";
      v8 = 585;
      goto LABEL_212;
    }
  }
  if ( (*((_BYTE *)a1 + 13) & 2) == 0 && !(_DWORD)v58 )
  {
    v59 = a1[4];
    if ( (unsigned __int64)a1[1] + 4 > v59 )
    {
      v7 = "!(indexHeader.NextInsertOffset + sizeof(SmsIndexEntryOffset) <= indexHeader.FirstIndexEntryOffset)";
      v8 = 592;
      goto LABEL_212;
    }
    v60 = *(unsigned __int16 *)((char *)a1 + v59 - 4);
    if ( (unsigned int)v60 < *a1 )
    {
      v61 = 560;
      v62 = "!(offsetEntry.Offset >= indexHeader.FirstIndexEntry)";
LABEL_192:
      wil::details::in1diag3::Return_NtStatusMsg(
        retaddr,
        (void *)v61,
        (unsigned int)"minkernel\\fs\\minstore\\checksup.cpp",
        (const char *)0xC0000518LL,
        (int)v62,
        v70);
      v7 = "!NT_SUCCESS(checkOneOffsetEntry(lastDeletedOffset, true))";
      v8 = 595;
      goto LABEL_212;
    }
    if ( !*((_BYTE *)v4 + 35) && (v60 & 7) != 0 )
    {
      v61 = 562;
      v62 = "!(checker.CheckAlignment(offsetEntry.Offset))";
      goto LABEL_192;
    }
    _SmsIndexEntry::ToKey((char *)a1 + v60, v88, v15, ***(_QWORD ***)(a3 + 56));
    if ( !v63(v64, v65, v88) )
    {
      v7 = "!(propertyDef.KeyRules->IsValidKey(propertyDef, ie.ToKey()))";
      v8 = 601;
      goto LABEL_212;
    }
  }
  v66 = a3;
  if ( (*(_BYTE *)(a3 + 44) & 2) != 0 )
  {
    if ( (*((_BYTE *)a1 + 13) & 8) != 0 )
    {
      v67 = &v49[2 * (unsigned int)v58];
      while ( v49 != v67 )
      {
        if ( *((_QWORD *)a1 + 3) + v49[1] != _SmsIndexEntry::StartValueFromRangeIndexEntry((_SmsIndexEntry *)((char *)a1 + *v49)) )
        {
          v7 = "!(offsetEntry.Key + indexHeader.BucketRangeStart == ie.StartValueFromRangeIndexEntry())";
          v8 = 609;
          goto LABEL_212;
        }
        v49 += 2;
      }
      if ( *((_BYTE *)a1 + 12) && v67[1] != 0xFFFF )
      {
        v7 = "!(offsetEntries[keyedEntryCount].Key == 0xffff)";
        v8 = 613;
        goto LABEL_212;
      }
    }
    else if ( CmsVolume::FormattedSinceVersion(v89, 0x30Fu) && *((_QWORD *)a1 + 3) )
    {
      v7 = "!(indexHeader.BucketRangeStart == 0)";
      v8 = 621;
      goto LABEL_212;
    }
  }
  if ( (*(int (__fastcall **)(_QWORD, unsigned int *, __int64))(**(_QWORD **)(v66 + 56) + 24LL))(
         *(_QWORD *)(v66 + 56),
         a1,
         v66) >= 0 )
  {
    v68 = v82[0];
    --*((_BYTE *)v4 + 34);
    *((_DWORD *)v4 + 6) = v68;
    *((_DWORD *)v4 + 7) = v82[1];
    *((_WORD *)v4 + 16) = v83;
    *((_BYTE *)v4 + 35) = v84;
    *((_BYTE *)v4 + 36) = v85;
    *((_BYTE *)v4 + 37) = v86;
    return 0;
  }
  v7 = "!NT_SUCCESS(propertyDef.KeyRules->VerifyKeys(indexHeader, propertyDef))";
  v8 = 628;
LABEL_212:
  wil::details::in1diag3::Return_NtStatusMsg(
    retaddr,
    (void *)v8,
    (unsigned int)"minkernel\\fs\\minstore\\checksup.cpp",
    (const char *)0xC0000518LL,
    (int)v7,
    v70);
  return 3221226776LL;
}

```

## disassembly

```asm
0x1401386b0  mov     rax, rsp
0x1401386b3  mov     [rax+10h], rbx
0x1401386b7  mov     [rax+20h], r9
0x1401386bb  mov     [rax+18h], r8
0x1401386bf  push    rbp
0x1401386c0  push    rsi
0x1401386c1  push    rdi
0x1401386c2  push    r12
0x1401386c4  push    r13
0x1401386c6  push    r14
0x1401386c8  push    r15
0x1401386ca  lea     rbp, [rax-5Fh]
0x1401386ce  sub     rsp, 90h
0x1401386d5  cmp     dword ptr [rcx], 28h ; '('
0x1401386d8  mov     r12, r9
0x1401386db  mov     r9, r8
0x1401386de  mov     r10d, edx
0x1401386e1  mov     r14, rcx
0x1401386e4  jnb     short loc_1401386F7
0x1401386e6  lea     rax, aIndexheaderFir; "!(indexHeader.FirstIndexEntry >= sizeof"...
0x1401386ed  mov     edx, 1E6h
0x1401386f2  jmp     loc_14013926F
0x1401386f7  mov     ebx, [rcx+4]
0x1401386fa  mov     [rbp+57h+var_68], ebx
0x1401386fd  cmp     ebx, [rcx]
0x1401386ff  jnb     short loc_140138712
0x140138701  lea     rax, aIndexheaderNex; "!(indexHeader.NextInsertOffset >= index"...
0x140138708  mov     edx, 1E9h
0x14013870d  jmp     loc_14013926F
0x140138712  cmp     [rcx+10h], ebx
0x140138715  jnb     short loc_140138728
0x140138717  lea     rax, aIndexheaderFir_0; "!(indexHeader.FirstIndexEntryOffset >= "...
0x14013871e  mov     edx, 1EDh
0x140138723  jmp     loc_14013926F
0x140138728  mov     edx, [rcx+20h]
0x14013872b  cmp     edx, [rcx+10h]
0x14013872e  jnb     short loc_140138741
0x140138730  lea     rax, aIndexheaderEnd_1; "!(indexHeader.EndOfBucketOffset >= inde"...
0x140138737  mov     edx, 1F0h
0x14013873c  jmp     loc_14013926F
0x140138741  mov     eax, [r14+14h]
0x140138745  mov     ecx, edx
0x140138747  sub     ecx, [r14+10h]
0x14013874b  shl     rax, 2
0x14013874f  cmp     rcx, rax
0x140138752  jnb     short loc_140138765
0x140138754  lea     rax, aIndexheaderEnd_0; "!(indexHeader.EndOfBucketOffset - index"...
0x14013875b  mov     edx, 1F4h
0x140138760  jmp     loc_14013926F
0x140138765  cmp     edx, r10d
0x140138768  jbe     short loc_14013877B
0x14013876a  lea     rax, aIndexheaderEnd; "!(indexHeader.EndOfBucketOffset <= leng"...
0x140138771  mov     edx, 1F7h
0x140138776  jmp     loc_14013926F
0x14013877b  mov     al, [r14+0Ch]
0x14013877f  xor     r15d, r15d
0x140138782  test    byte ptr [r14+0Dh], 1
0x140138787  jz      short loc_1401387B3
0x140138789  test    al, al
0x14013878b  jnz     short loc_14013879E
0x14013878d  lea     rax, aIndexheaderLev_0; "!(indexHeader.Level != 0)"
0x140138794  mov     edx, 204h
0x140138799  jmp     loc_14013926F
0x14013879e  cmp     al, 0F8h
0x1401387a0  jb      short loc_1401387C8
0x1401387a2  lea     rax, aIndexheaderLev_1; "!(indexHeader.Level < ROOT_LEVEL)"
0x1401387a9  mov     edx, 208h
0x1401387ae  jmp     loc_14013926F
0x1401387b3  test    al, al
0x1401387b5  jz      short loc_1401387C8
0x1401387b7  lea     rax, aIndexheaderLev; "!(indexHeader.Level == 0)"
0x1401387be  mov     edx, 20Ah
0x1401387c3  jmp     loc_14013926F
0x1401387c8  mov     rax, [r12+28h]
0x1401387cd  mov     [rbp+57h+var_38], rax
0x1401387d1  cmp     ebx, [rax+0CA4h]
0x1401387d7  jbe     short loc_1401387EA
0x1401387d9  lea     rax, aMaxindexentryl; "!(maxIndexEntryLocation <= volume.Volum"...
0x1401387e0  mov     edx, 210h
0x1401387e5  jmp     loc_14013926F
0x1401387ea  test    byte ptr [r14], 7
0x1401387ee  jnz     loc_140139263
0x1401387f4  mov     r8, r14
0x1401387f7  lea     rdx, [rbp+57h+var_60]
0x1401387fb  mov     rcx, r12
0x1401387fe  call    _anonymous_namespace___IndexEntryChecker__PushIndexHeader
0x140138803  cmp     [r12+23h], r15b
0x140138808  jnz     short loc_140138820
0x14013880a  test    bl, 7
0x14013880d  jz      short loc_140138820
0x14013880f  lea     rax, aCheckerCheckal_0; "!(checker.CheckAlignment(maxIndexEntryL"...
0x140138816  mov     edx, 219h
0x14013881b  jmp     loc_14013926F
0x140138820  test    byte ptr [r9+2Ch], 4
0x140138825  jz      short loc_14013883B
0x140138827  mov     cl, [r14+0Ch]
0x14013882b  mov     byte ptr [rbp+57h+arg_0], cl
0x14013882e  test    cl, cl
0x140138830  jnz     short loc_140138836
0x140138832  mov     al, 1
0x140138834  jmp     short loc_140138845
0x140138836  mov     byte ptr [rbp+57h+arg_0], cl
0x140138839  jmp     short loc_140138842
0x14013883b  mov     al, [r14+0Ch]
0x14013883f  mov     byte ptr [rbp+57h+arg_0], al
0x140138842  mov     al, r15b
0x140138845  mov     edx, [r14+4]
0x140138849  lea     rsi, aMinkernelFsMin_4; "minkernel\\fs\\minstore\\checksup.cpp"
0x140138850  mov     r8d, [r14+10h]
0x140138854  mov     edi, 0C0000518h
0x140138859  sub     r8d, edx
0x14013885c  mov     [rbp+57h+var_80], edx
0x14013885f  mov     [rbp+57h+var_90], r8d
0x140138863  test    al, al
0x140138865  jz      loc_140138ACA
0x14013886b  cmp     [r14+8], r8d
0x14013886f  jnb     short loc_140138898
0x140138871  lea     rax, aIndexheaderByt_0; "!(indexHeader.BytesAvailable >= freeSpa"...
0x140138878  mov     edx, 11Fh; void *
0x14013887d  mov     rcx, [rbp+5Fh]; this
0x140138881  mov     r9d, edi; char *
0x140138884  mov     r8, rsi; unsigned int
0x140138887  mov     [rsp+20h], rax; int
0x14013888c  call    ?Return_NtStatusMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x140138891  mov     eax, edi
0x140138893  jmp     loc_140138AC1
0x140138898  mov     ecx, [r14]
0x14013889b  mov     r9d, r15d
0x14013889e  mov     [rbp+57h+arg_0], r15d
0x1401388a2  lea     rbx, [r14+rcx]
0x1401388a6  cmp     ecx, edx
0x1401388a8  jnb     loc_140138A79
0x1401388ae  mov     r13, [rbp+57h+arg_18]
0x1401388b2  mov     r10, rdx
0x1401388b5  mov     [rbp+57h+var_78], rdx
0x1401388b9  mov     r8d, ecx
0x1401388bc  lea     rax, [r8+10h]
0x1401388c0  cmp     rax, r10
0x1401388c3  ja      loc_140138A68
0x1401388c9  movzx   eax, word ptr [rbx+8]
0x1401388cd  and     ax, 40h
0x1401388d1  jz      short loc_1401388E2
0x1401388d3  movzx   r12d, word ptr [rbx+0Ah]
0x1401388d8  add     r12d, 7
0x1401388dc  and     r12d, 0FFFFFFF8h
0x1401388e0  jmp     short loc_1401388E5
0x1401388e2  mov     r12d, [rbx]
0x1401388e5  test    byte ptr [rbx+8], 4
0x1401388e9  jz      short loc_140138903
0x1401388eb  mov     edx, r12d
0x1401388ee  lea     rax, [rdx+r8]
0x1401388f2  cmp     rax, r10
0x1401388f5  ja      loc_1401389F1
0x1401388fb  add     ecx, r12d
0x1401388fe  jmp     loc_1401389C3
0x140138903  test    ax, ax
0x140138906  jz      loc_140138A57
0x14013890c  lea     eax, [r12+rcx]
0x140138910  mov     [rbp+57h+var_8C], eax
0x140138913  cmp     eax, edx
0x140138915  ja      loc_140138A46
0x14013891b  mov     edx, ecx
0x14013891d  mov     rcx, r13
0x140138920  call    _anonymous_namespace___IndexEntryChecker__MarkIndexEntryOffset
0x140138925  mov     eax, 0F007h
0x14013892a  test    [rbx+8], ax
0x14013892e  jnz     loc_140138A35
0x140138934  mov     rcx, rbx; this
0x140138937  call    ?HasChecksums@SmsRunHeader@@QEBA_NXZ; SmsRunHeader::HasChecksums(void)
0x14013893c  test    al, al
0x14013893e  jz      short loc_140138965
0x140138940  mov     rdx, [r13+28h]; struct CmsVolume *
0x140138944  mov     rcx, rbx; this
0x140138947  call    ?GetChecksumSizeInBytes@SmsRunHeader@@QEBAGPEBVCmsVolume@@@Z; SmsRunHeader::GetChecksumSizeInBytes(CmsVolume const *)
0x14013894c  movzx   eax, ax
0x14013894f  cmp     r12d, eax
0x140138952  jnb     short loc_14013896F
0x140138954  lea     rax, aLengthRunGetch; "!(length >= run.GetChecksumSizeInBytes("...
0x14013895b  mov     edx, 154h
0x140138960  jmp     loc_14013887D
0x140138965  cmp     r12d, 18h
0x140138969  jb      loc_140138A24
0x14013896f  mov     rcx, rbx; this
0x140138972  call    ?IsGhosted@SmsRunHeader@@QEBA_NXZ; SmsRunHeader::IsGhosted(void)
0x140138977  test    al, al
0x140138979  jz      short loc_1401389B5
0x14013897b  mov     rdx, [r13+28h]; struct CmsVolume *
0x14013897f  mov     rcx, rbx; this
0x140138982  call    ?GetChecksumSizeInBytes@SmsRunHeader@@QEBAGPEBVCmsVolume@@@Z; SmsRunHeader::GetChecksumSizeInBytes(CmsVolume const *)
0x140138987  add     ax, 38h ; '8'
0x14013898b  mov     ecx, r12d
0x14013898e  movzx   eax, ax
0x140138991  mov     [rbp+57h+var_70], rax
0x140138995  cmp     rax, rcx
0x140138998  ja      short loc_140138A13
0x14013899a  mov     rdx, [r13+28h]; struct CmsVolume *
0x14013899e  mov     rcx, rbx; this
0x1401389a1  call    ?GetRecallMetadataHeader@SmsRun@@QEBAPEAU_SmsRecallMetadataHeader@@PEBVCmsVolume@@@Z; SmsRun::GetRecallMetadataHeader(CmsVolume const *)
0x1401389a6  mov     ecx, [rax+18h]
0x1401389a9  add     rcx, [rbp+57h+var_70]
0x1401389ad  mov     eax, r12d
0x1401389b0  cmp     rcx, rax
0x1401389b3  ja      short loc_140138A02
0x1401389b5  mov     ecx, [rbp+57h+var_8C]
0x1401389b8  mov     r9d, [rbp+57h+arg_0]
0x1401389bc  mov     r10, [rbp+57h+var_78]
0x1401389c0  mov     edx, r12d
0x1401389c3  test    byte ptr [rbx+8], 4
0x1401389c7  mov     r8d, [rbp+57h+var_90]
0x1401389cb  jz      short loc_1401389D6
0x1401389cd  add     r8d, r12d
0x1401389d0  mov     [rbp+57h+var_90], r8d
0x1401389d4  jmp     short loc_1401389DD
0x1401389d6  inc     r9d
0x1401389d9  mov     [rbp+57h+arg_0], r9d
0x1401389dd  cmp     ecx, [rbp+57h+var_80]
0x1401389e0  jnb     loc_140138A79
0x1401389e6  add     rbx, rdx
0x1401389e9  mov     edx, [rbp+57h+var_80]
0x1401389ec  jmp     loc_1401388B9
0x1401389f1  lea     rax, aLimitsAddOffse; "!(limits_add(offset, length) <= maxInde"...
0x1401389f8  mov     edx, 137h
0x1401389fd  jmp     loc_14013887D
0x140138a02  lea     rax, aRecallbufferen; "!(recallBufferEndOffset <= length)"
0x140138a09  mov     edx, 163h
0x140138a0e  jmp     loc_14013887D
0x140138a13  lea     rax, aRecallbufferof; "!(recallBufferOffset <= length)"
0x140138a1a  mov     edx, 15Eh
0x140138a1f  jmp     loc_14013887D
0x140138a24  lea     rax, aLengthSizeofSm_0; "!(length >= sizeof(SmsRunHeader))"
0x140138a2b  mov     edx, 157h
0x140138a30  jmp     loc_14013887D
0x140138a35  lea     rax, aIsflagonIeFlag; "!(!IsFlagOn(ie->Flags, ~INDEX_IE_ALL_ST"...
0x140138a3c  mov     edx, 14Ch
0x140138a41  jmp     loc_14013887D
0x140138a46  lea     rax, aOffsetLengthMa; "!(offset + length <= maxIndexEntryLocat"...
0x140138a4d  mov     edx, 147h
0x140138a52  jmp     loc_14013887D
0x140138a57  lea     rax, aIsyesIsstream; "IsYes(isStream)"
0x140138a5e  mov     edx, 16Ch
0x140138a63  jmp     loc_14013887D
0x140138a68  lea     rax, aOffsetSizeofSm; "!(offset + sizeof(SmsIndexEntry) <= max"...
0x140138a6f  mov     edx, 12Dh
0x140138a74  jmp     loc_14013887D
0x140138a79  cmp     [r14+0Ch], r15b
0x140138a7d  jz      short loc_140138A90
0x140138a7f  lea     rax, aEndentrycount1; "!(endEntryCount == 1)"
0x140138a86  mov     edx, 1CBh
0x140138a8b  jmp     loc_14013887D
0x140138a90  cmp     [r14+8], r8d
0x140138a94  jz      short loc_140138AA7
0x140138a96  lea     rax, aIndexheaderByt; "!(indexHeader.BytesAvailable == freeSpa"...
0x140138a9d  mov     edx, 1D0h
0x140138aa2  jmp     loc_14013887D
0x140138aa7  cmp     [r14+14h], r9d
0x140138aab  jz      short loc_140138ABE
0x140138aad  lea     rax, aIndexheaderNum; "!(indexHeader.NumberIndexEntryOffsets ="...
0x140138ab4  mov     edx, 1D1h
0x140138ab9  jmp     loc_14013887D
0x140138abe  mov     eax, r15d
0x140138ac1  mov     r12, [rbp+57h+arg_18]
0x140138ac5  jmp     loc_140138F3B
0x140138aca  cmp     [r14+8], r8d
0x140138ace  jnb     short loc_140138AF7
0x140138ad0  lea     rax, aIndexheaderByt_0; "!(indexHeader.BytesAvailable >= freeSpa"...
0x140138ad7  mov     edx, 11Fh; void *
0x140138adc  mov     rcx, [rbp+5Fh]; this
0x140138ae0  mov     r9d, edi; char *
0x140138ae3  mov     r8, rsi; unsigned int
0x140138ae6  mov     [rsp+20h], rax; int
0x140138aeb  call    ?Return_NtStatusMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x140138af0  mov     eax, edi
0x140138af2  jmp     loc_140138F3B
0x140138af7  mov     r11d, [r14]
0x140138afa  mov     eax, r15d
0x140138afd  mov     [rbp+57h+var_78], r11
0x140138b01  mov     ecx, r15d
0x140138b04  mov     [rbp+57h+var_8C], eax
0x140138b07  mov     [rbp+57h+var_84], ecx
0x140138b0a  lea     rbx, [r14+r11]
0x140138b0e  cmp     r11d, edx
0x140138b11  jnb     loc_140138ED9
0x140138b17  mov     r9, rdx
0x140138b1a  mov     [rbp+57h+var_70], rdx
0x140138b1e  lea     rax, [r11+10h]
0x140138b22  cmp     rax, r9
0x140138b25  ja      loc_140138EC5
0x140138b2b  movzx   r10d, word ptr [rbx+8]
0x140138b30  movzx   eax, r10w
0x140138b34  and     ax, 40h
0x140138b38  jz      short loc_140138B46
0x140138b3a  movzx   edx, word ptr [rbx+0Ah]
0x140138b3e  add     edx, 7
0x140138b41  and     edx, 0FFFFFFF8h
0x140138b44  jmp     short loc_140138B48
0x140138b46  mov     edx, [rbx]
0x140138b48  mov     [rbp+57h+var_88], edx
0x140138b4b  test    r10b, 4
0x140138b4f  jz      short loc_140138B72
0x140138b51  mov     r13d, edx
  ... truncated ...
```
