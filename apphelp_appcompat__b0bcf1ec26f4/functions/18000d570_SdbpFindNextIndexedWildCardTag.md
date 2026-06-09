# SdbpFindNextIndexedWildCardTag

- ea: `0x18000d570`
- end: `0x18000e523`
- name: `SdbpFindNextIndexedWildCardTag`
- size: `4019`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x18000c43c`

## callees

- `0x18000bd50`
- `0x18000beb0`
- `0x18000d570`
- `0x18000ef24`
- `0x18000ef54`
- `0x18000efe0`
- `0x18000f080`
- `0x18000f114`
- `0x18000fad0`
- `0x180010db0`
- `0x18005921d`
- `0x180059235`
- `0x180059270`

## import_xrefs

- `ntdll!RtlRunOnceExecuteOnce` at `0x18000dd89`
- `ntdll!RtlRunOnceExecuteOnce` at `0x18000dd89`
- `ntdll!RtlInitUnicodeString` at `0x18000d5d9`
- `ntdll!RtlInitUnicodeString` at `0x18000d5d9`
- `ntdll!RtlUpcaseUnicodeString` at `0x18000d629`
- `ntdll!RtlUpcaseUnicodeString` at `0x18000d629`
- `ntdll!RtlFreeHeap` at `0x18000d6cd`
- `ntdll!RtlFreeHeap` at `0x18000d6cd`
- `ntdll!RtlAllocateHeap` at `0x18000d5f7`
- `ntdll!RtlAllocateHeap` at `0x18000d5f7`

## string_xrefs

- `0x18000d712`: `SdbpReadMappedData`
- `0x18000da66`: `SdbpReadMappedData`
- `0x18000db68`: `SdbpReadMappedData`
- `0x18000dbb6`: `SdbpReadMappedData`
- `0x18000ddce`: `SdbpReadMappedData`
- `0x18000de32`: `SdbpReadMappedData`
- `0x18000def6`: `SdbpReadMappedData`
- `0x18000e21f`: `SdbpReadMappedData`
- `0x18000e259`: `SdbpReadMappedData`
- `0x18000e2d5`: `SdbpReadMappedData`
- `0x18000e321`: `SdbpReadMappedData`
- `0x18000e378`: `SdbpReadMappedData`
- `0x18000e400`: `SdbpReadMappedData`
- `0x18000e4d0`: `SdbpReadMappedData`
- `0x18000e512`: `SdbpReadMappedData`
- `0x18000d723`: `Error reading data`
- `0x18000da7b`: `Error reading data`
- `0x18000dbc7`: `Error reading data`
- `0x18000dddf`: `Error reading data`
- `0x18000de61`: `Error reading data`
- `0x18000df07`: `Error reading data`
- `0x18000e33c`: `Error reading data`
- `0x18000db79`: `Error reading size data [%x]`
- `0x18000de84`: `Error reading size data [%x]`
- `0x18000dbfe`: `SdbpReadStringRef`
- `0x18000de6e`: `SdbpReadStringRef`
- `0x18000e420`: `Error reading tag`
- `0x18000de50`: `SdbpReadTagData`
- `0x18000e0b1`: `SdbpReadTagData`
- `0x18000de43`: `Error reading tag data`
- `0x18000dc6d`: `Error reading size data`
- `0x18000e398`: `Error reading size data`
- `0x18000e210`: `Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)`
- `0x18000e24a`: `Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)`
- `0x18000e2c6`: `Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)`
- `0x18000e312`: `Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)`
- `0x18000e369`: `Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)`
- `0x18000e3f1`: `Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)`
- `0x18000e4c5`: `Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)`
- `0x18000e4f4`: `Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)`

## pseudocode

```c
__int64 __fastcall SdbpFindNextIndexedWildCardTag(__int64 a1, unsigned int *a2)
{
  unsigned int *v2; // rsi
  const WCHAR *v4; // rdx
  NTSTATUS v5; // eax
  int v6; // ebx
  unsigned __int64 Length; // r10
  unsigned __int64 v8; // rax
  unsigned __int64 i; // r8
  WCHAR v10; // dx
  __int16 v11; // dx
  __int64 v12; // rbx
  unsigned int v14; // ecx
  __int64 v15; // r15
  __int64 MappedTagData; // rax
  unsigned int v17; // r12d
  unsigned int v18; // ecx
  unsigned int TagDataSize; // eax
  unsigned __int64 v20; // rcx
  unsigned __int64 v21; // r14
  __int64 v22; // r13
  __int64 v23; // rax
  __int16 v24; // r14
  __int64 v25; // rdi
  unsigned int NextTagId; // ebx
  unsigned int v27; // eax
  unsigned int v28; // esi
  __int64 v29; // rbx
  unsigned int *v30; // r15
  __int16 v31; // dx
  unsigned int v32; // edi
  unsigned int v33; // ebx
  __int16 v34; // r8
  unsigned int v35; // eax
  _QWORD *v36; // r12
  __int64 v37; // rdx
  unsigned __int16 TagFromTagID; // ax
  int v39; // r14d
  unsigned int v40; // edi
  unsigned int v41; // ebx
  unsigned __int16 v42; // cx
  unsigned int v43; // eax
  __int64 v44; // rdi
  unsigned int v45; // eax
  int v46; // ecx
  unsigned int v47; // ecx
  int v48; // ebx
  bool v49; // zf
  int v50; // eax
  __int64 v51; // rdx
  __int64 v52; // r8
  unsigned int v53; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING v55; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v56; // [rsp+68h] [rbp-98h]
  unsigned int *v57; // [rsp+70h] [rbp-90h]
  _DWORD *v58; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v59; // [rsp+80h] [rbp-80h]
  __int64 v60; // [rsp+88h] [rbp-78h] BYREF
  __int16 v61; // [rsp+90h] [rbp-70h]
  _BYTE v62[272]; // [rsp+A0h] [rbp-60h] BYREF

  v2 = a2;
  v57 = a2;
  v56 = a1;
  memset_0(v62, 0, 0x104u);
  v4 = (const WCHAR *)*((_QWORD *)v2 + 4);
  v60 = 0;
  v61 = 0;
  DestinationString = 0;
  v55 = 0;
  RtlInitUnicodeString(&DestinationString, v4);
  v55.Buffer = (PWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, DestinationString.MaximumLength);
  if ( v55.Buffer )
  {
    v55.MaximumLength = DestinationString.MaximumLength;
    v55.Length = 0;
    v5 = RtlUpcaseUnicodeString(&v55, &DestinationString, 0);
    v6 = v5;
    if ( v5 < 0 )
    {
      AslLogCallPrintf(1, "AslStringUpcaseToMultiByteN", 1152, "RtlUpcaseUnicodeString failed [%x]", v5);
    }
    else
    {
      Length = v55.Length;
      v8 = 0;
      for ( i = 0; i < Length >> 1; ++i )
      {
        v10 = v55.Buffer[i];
        v62[v8++] = v10;
        if ( v8 < 0x104 )
        {
          v11 = HIBYTE(v10);
          if ( !(_BYTE)v11 )
            continue;
          v62[v8++] = v11;
          if ( v8 < 0x104 )
            continue;
        }
        v6 = -1073741789;
        AslLogCallPrintf(1, "AslStringUpcaseToMultiByteN", 1190, "Failed to convert to ANSI [%x]", -1073741789);
        goto LABEL_9;
      }
      v62[v8] = 0;
      v6 = 0;
    }
  }
  else
  {
    v6 = -1073741801;
    AslLogCallPrintf(1, "AslStringUpcaseToMultiByteN", 1143, "Out of memory");
  }
LABEL_9:
  if ( v55.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v55.Buffer);
  if ( v6 < 0 )
    return 0;
  v12 = *v2;
  if ( (unsigned int)v12 >= 0xFFFFFFFE )
  {
    AslLogCallPrintf(
      1,
      "SdbpReadMappedData",
      855,
      "Offset and region size add up to cause an integer overflow or underflow");
LABEL_14:
    AslLogCallPrintf(1, "SdbGetTagFromTagID", 3039, "Error reading data");
LABEL_15:
    AslLogCallPrintf(1, "SdbpGetIndex", 1517, "Index tagid 0x%lx is not referring to the index bits", v12);
    return 0;
  }
  v18 = *(_DWORD *)(a1 + 20);
  if ( v18 < (int)v12 + 2 )
  {
    AslLogCallPrintf(
      1,
      "SdbpReadMappedData",
      860,
      "Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)",
      v12,
      2,
      v18);
    goto LABEL_14;
  }
  if ( *(_WORD *)(v12 + *(_QWORD *)(a1 + 8)) != 0x9801 )
    goto LABEL_15;
  TagDataSize = SdbGetTagDataSize(a1, (unsigned int)v12);
  v20 = 0;
  if ( TagDataSize != 0x20000000 )
    v20 = TagDataSize;
  v21 = v20 / 0xC;
  *(_QWORD *)&v55.Length = v20 / 0xC;
  *(_QWORD *)&DestinationString.Length = SdbpGetMappedTagData(a1, (unsigned int)v12);
  v15 = *(_QWORD *)&DestinationString.Length;
  if ( !*(_QWORD *)&DestinationString.Length )
    return 0;
  LODWORD(v22) = v2[4];
  do
  {
LABEL_33:
    v22 = (unsigned int)(v22 + 1);
    if ( (unsigned int)v22 >= (unsigned int)v21 )
      return 0;
    v23 = *(_QWORD *)(v15 + 12 * v22);
    if ( (v2[5] & 2) != 0 )
    {
      BYTE1(v60) = HIBYTE(v23);
      BYTE2(v60) = BYTE6(v23);
      BYTE3(v60) = BYTE5(v23);
      BYTE4(v60) = BYTE4(v23);
      BYTE5(v60) = BYTE3(v23);
      BYTE6(v60) = BYTE2(v23);
      HIBYTE(v60) = BYTE1(v23);
      v61 = (unsigned __int8)v23;
      LOBYTE(v60) = 42;
    }
    else
    {
      LOBYTE(v60) = HIBYTE(v23);
      BYTE1(v60) = BYTE6(v23);
      BYTE2(v60) = BYTE5(v23);
      BYTE3(v60) = BYTE4(v23);
      BYTE4(v60) = BYTE3(v23);
      BYTE5(v60) = BYTE2(v23);
      BYTE6(v60) = BYTE1(v23);
      HIBYTE(v60) = v23;
      LOBYTE(v61) = 42;
    }
  }
  while ( !(unsigned int)AslStringPatternMatchExA(&v60, v62) );
  v17 = *(_DWORD *)(v15 + 12 * v22 + 8);
  v24 = *((_WORD *)v2 + 6);
  v25 = v56;
  v59 = v17;
  if ( v17 )
  {
    if ( (SdbGetTagFromTagID(v56, v17) & 0xF000) != 0x7000 )
    {
      v28 = 0;
      goto LABEL_45;
    }
    NextTagId = SdbpGetNextTagId(v25, v17);
    if ( (unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline()
      && NextTagId > *(_DWORD *)(v25 + 20) )
    {
      AslLogCallPrintf(
        2,
        "SdbGetFirstChild",
        3141,
        "SdbpGetNextTagId returned value larger than the SDB (for tiParent=0x%X; pdb->dwSize=0x%X)",
        v17,
        *(_DWORD *)(v25 + 20));
      v28 = 0;
      goto LABEL_45;
    }
    v27 = v17 + 6;
  }
  else
  {
    NextTagId = *(_DWORD *)(v56 + 20);
    v27 = 12;
  }
  v28 = 0;
  if ( v27 < NextTagId )
    v28 = v27;
  while ( 1 )
  {
LABEL_45:
    if ( !v28 )
      goto LABEL_78;
    v29 = v28 + 2;
    if ( v28 >= 0xFFFFFFFE )
    {
      AslLogCallPrintf(
        1,
        "SdbpReadMappedData",
        855,
        "Offset and region size add up to cause an integer overflow or underflow");
      v30 = (unsigned int *)(v25 + 20);
    }
    else
    {
      v30 = (unsigned int *)(v25 + 20);
      if ( *(_DWORD *)(v25 + 20) >= (unsigned int)v29 )
      {
        v31 = *(_WORD *)(v28 + *(_QWORD *)(v25 + 8));
        goto LABEL_49;
      }
      AslLogCallPrintf(
        1,
        "SdbpReadMappedData",
        860,
        "Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)",
        v28,
        2,
        *(_DWORD *)(v25 + 20));
    }
    AslLogCallPrintf(1, "SdbGetTagFromTagID", 3039, "Error reading data");
    v31 = 0;
LABEL_49:
    if ( v31 == v24 )
      break;
    if ( !v17 )
    {
      v32 = *v30;
      goto LABEL_54;
    }
    if ( (SdbGetTagFromTagID(v25, v17) & 0xF000) == 0x7000 )
    {
      v32 = SdbpGetNextTagId(v25, v17);
      if ( (unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline() && v32 > *v30 )
      {
        AslLogCallPrintf(
          2,
          "SdbGetNextChild",
          3196,
          "SdbpGetNextTagId returned value larger than the SDB (for tiParent=0x%X; tiPrev=0x%X; pdb->dwSize=0x%X)",
          v17,
          v28,
          *v30);
        v25 = v56;
        v28 = 0;
      }
      else
      {
LABEL_54:
        v33 = SdbpGetNextTagId(v56, v28);
        if ( !(unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline() )
        {
          if ( v33 < v32 )
            goto LABEL_57;
LABEL_139:
          v33 = 0;
          goto LABEL_57;
        }
        if ( v33 >= v32 || v33 <= v28 )
          goto LABEL_139;
LABEL_57:
        v25 = v56;
        v28 = v33;
      }
    }
    else
    {
      AslLogCallPrintf(1, "SdbGetNextChild", 3182, "Trying to operate on non-list, non-root tag");
      v28 = 0;
    }
  }
  if ( !v25 )
  {
    AslLogCallPrintf(1, "SdbGetStringTagPtr", 722, "Invalid pdb");
    goto LABEL_78;
  }
  if ( (unsigned int)v29 < 2 )
  {
    AslLogCallPrintf(
      1,
      "SdbpReadMappedData",
      855,
      "Offset and region size add up to cause an integer overflow or underflow");
LABEL_73:
    AslLogCallPrintf(1, "SdbGetTagFromTagID", 3039, "Error reading data");
    goto LABEL_78;
  }
  if ( *v30 < (unsigned int)v29 )
  {
    AslLogCallPrintf(
      1,
      "SdbpReadMappedData",
      860,
      "Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)",
      v28,
      2,
      *v30);
    goto LABEL_73;
  }
  v34 = *(_WORD *)(*(_QWORD *)(v25 + 8) + v28) & 0xF000;
  if ( v34 == (__int16)0x8000 )
  {
    MappedTagData = SdbpGetMappedTagData(v25, v28);
    LODWORD(v21) = *(_DWORD *)&v55.Length;
    v15 = *(_QWORD *)&DestinationString.Length;
    goto LABEL_24;
  }
  if ( v34 != 24576 )
    goto LABEL_78;
  v35 = *v30;
  LODWORD(v58) = 0;
  if ( v35 < (unsigned int)v29 )
  {
    AslLogCallPrintf(
      1,
      "SdbpReadMappedData",
      860,
      "Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)",
      v28,
      2,
      v35);
    AslLogCallPrintf(1, "SdbGetTagFromTagID", 3039, "Error reading data");
    v37 = v28;
    v36 = (_QWORD *)(v25 + 8);
LABEL_74:
    if ( *v30 < (unsigned int)v29 )
    {
      AslLogCallPrintf(
        1,
        "SdbpReadMappedData",
        860,
        "Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)",
        v28,
        2,
        *v30);
      AslLogCallPrintf(1, "SdbGetTagFromTagID", 3039, "Error reading data");
      v42 = 0;
    }
    else
    {
      v42 = *(_WORD *)(v37 + *v36);
    }
    AslLogCallPrintf(1, "SdbpReadStringRef", 634, "TagID 0x%08X, Tag %04X not STRINGREF type", v28, v42);
    goto LABEL_77;
  }
  v36 = (_QWORD *)(v25 + 8);
  v37 = v28;
  if ( (*(_WORD *)(v28 + *(_QWORD *)(v25 + 8)) & 0xF000) != 0x6000 )
    goto LABEL_74;
  TagFromTagID = SdbGetTagFromTagID(v25, v28);
  v39 = TagFromTagID;
  v40 = TagFromTagID & 0xF000;
  if ( !(unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline() )
  {
    switch ( v40 )
    {
      case 0x1000u:
        v41 = 0;
LABEL_83:
        if ( v41 + v28 < v41 || v41 + v28 > *v30 )
        {
          AslLogCallPrintf(1, "SdbGetTagDataSize", 375, "Error reading size data");
          v41 = 0x20000000;
        }
        goto LABEL_91;
      case 0x2000u:
        v41 = 1;
        goto LABEL_83;
      case 0x3000u:
        v41 = 2;
        goto LABEL_83;
    }
    if ( v40 != 0x4000 )
    {
      if ( v40 == 20480 )
      {
        v41 = 8;
        goto LABEL_83;
      }
      if ( v40 != 24576 )
      {
        v53 = 0;
        if ( !(unsigned int)SdbpReadMappedData(v56, (unsigned int)v29, &v53, 4) )
          AslLogCallPrintf(1, "SdbGetTagDataSize", 364, "Error reading size data");
        v41 = v53;
        goto LABEL_83;
      }
    }
    v41 = 4;
    goto LABEL_83;
  }
  if ( v40 == 36864 )
    goto LABEL_69;
  if ( v40 == 20480 )
  {
    v41 = 8;
    goto LABEL_88;
  }
  if ( v40 > 0x5000 )
  {
    if ( v40 != 24576 )
    {
      if ( v40 != 28672 && v40 != 0x8000 )
        goto LABEL_133;
LABEL_69:
      if ( (unsigned int)v29 < 0xFFFFFFFC )
      {
        if ( *v30 >= v28 + 6 )
        {
          v41 = *(_DWORD *)(v29 + *v36);
          goto LABEL_88;
        }
        AslLogCallPrintf(
          1,
          "SdbpReadMappedData",
          860,
          "Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)",
          v28 + 2,
          4,
          *v30);
      }
      else
      {
        AslLogCallPrintf(
          1,
          "SdbpReadMappedData",
          855,
          "Offset and region size add up to cause an integer overflow or underflow");
      }
      v41 = 0x20000000;
      AslLogCallPrintf(1, "SdbGetTagDataSize", 311, "Error reading size data [%x]", -1073741789);
      goto LABEL_88;
    }
LABEL_124:
    v41 = 4;
LABEL_88:
    v43 = v41;
  }
  else
  {
    switch ( v40 )
    {
      case 0x1000u:
        v41 = 0;
        v43 = 0;
        break;
      case 0x3000u:
        v43 = 2;
        v41 = 2;
        break;
      case 0x2000u:
        v41 = 1;
        goto LABEL_88;
      case 0x4000u:
        goto LABEL_124;
      default:
LABEL_133:
        AslLogCallPrintf(1, "SdbGetTagDataSize", 318, "Invalid TAG_TYPE encountered TAG: [0x%x]", v39);
        v41 = 0x20000000;
LABEL_134:
        AslLogCallPrintf(1, "SdbpReadTagData", 439, "Buffer too small. Avail: %d, Need: %d", 4, v41);
LABEL_111:
        AslLogCallPrintf(1, "SdbpReadStringRef", 639, "Error reading data");
LABEL_77:
        AslLogCallPrintf(1, "SdbGetStringTagPtr", 742, "Error getting StringRef");
LABEL_78:
        v15 = *(_QWORD *)&DestinationString.Length;
        LODWORD(v21) = *(_DWORD *)&v55.Length;
LABEL_79:
        v2 = v57;
        goto LABEL_33;
    }
  }
  if ( v43 + v28 < v43 || v43 + v28 > *v30 )
  {
    AslLogCallPrintf(1, "SdbGetTagDataSize", 329, "Error reading size data [%x]", -1073741675);
    v41 = 0x20000000;
  }
LABEL_91:
  v21 = *(_QWORD *)&v55.Length;
  if ( v41 > 4 )
    goto LABEL_134;
  v44 = v56;
  LOWORD(v53) = 0;
  if ( (unsigned int)SdbpReadMappedData(v56, v28, &v53, 2) )
  {
    if ( (unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline() )
    {
      v45 = v53 & 0xF000;
      if ( v45 == 36864 )
        goto LABEL_95;
      if ( v45 == 24576 )
      {
LABEL_116:
        v46 = 2;
      }
      else
      {
        if ( v45 > 0x4000 )
        {
          if ( v45 == 20480 )
            goto LABEL_116;
          if ( v45 == 28672 || v45 == 0x8000 )
          {
LABEL_95:
            v46 = 6;
            goto LABEL_96;
          }
        }
        else if ( v45 == 0x4000 || v45 == 4096 || v45 == 0x2000 || v45 == 12288 )
        {
          goto LABEL_116;
        }
        AslLogCallPrintf(1, "SdbpGetTagHeadSize", 121, "Invalid TAG_TYPE encountered. TAG: [%x]", (unsigned __int16)v53);
        v46 = 0;
      }
    }
    else
    {
      v46 = 6;
      if ( (v53 & 0xF000) < 0x7000 )
        v46 = 2;
    }
  }
  else
  {
    AslLogCallPrintf(1, "SdbpGetTagHeadSize", 100, "Error reading tag");
    v46 = 0;
  }
LABEL_96:
  v47 = v28 + v46;
  if ( v41 + v47 < v41 )
  {
    AslLogCallPrintf(
      1,
      "SdbpReadMappedData",
      855,
      "Offset and region size add up to cause an integer overflow or underflow");
LABEL_110:
    AslLogCallPrintf(1, "SdbpReadTagData", 446, "Error reading tag data");
    goto LABEL_111;
  }
  if ( *v30 < v41 + v47 )
  {
    AslLogCallPrintf(
      1,
      "SdbpReadMappedData",
      860,
      "Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)",
      v47,
      v41,
      *v30);
    goto LABEL_110;
  }
  memcpy_0(&v58, (const void *)(*v36 + v47), v41);
  v48 = (int)v58;
  if ( !(_DWORD)v58 )
    goto LABEL_77;
  v49 = *(_DWORD *)(v44 + 16) == 0;
  v58 = 0;
  if ( v49 )
  {
    v50 = RtlRunOnceExecuteOnce(v44 + 2624, InitOnceGetStringTableOffset, v44, &v58);
    if ( v50 < 0 )
    {
      AslLogCallPrintf(
        1,
        "SdbpGetStringTableItemFromStringRef",
        858,
        "RtlRunOnceExecuteOnce failed for InitOnceGetStringTableOffset [%x]",
        v50);
      v15 = *(_QWORD *)&DestinationString.Length;
    }
    else
    {
      if ( v58 && *v58 )
      {
        v51 = (unsigned int)(*v58 + v48);
        v52 = v44;
        goto LABEL_104;
      }
      AslLogCallPrintf(
        1,
        "SdbpGetStringTableItemFromStringRef",
        874,
        "InitOnceGetStringTableOffset succeeded but failed to find string table");
LABEL_108:
      v15 = *(_QWORD *)&DestinationString.Length;
    }
LABEL_22:
    AslLogCallPrintf(
      1,
      "SdbpGetMappedStringFromTable",
      977,
      "SdbpGetStringTableItemFromStringRef failed to get tagid for string ref");
    MappedTagData = 0;
    goto LABEL_23;
  }
  v52 = *(_QWORD *)(v44 + 2640);
  if ( !v52 )
  {
    AslLogCallPrintf(1, "SdbpGetStringTableItemFromStringRef", 838, "No stringtable in DB");
    goto LABEL_108;
  }
  v51 = (unsigned int)(v48 + 6);
LABEL_104:
  if ( (unsigned int)v51 >= 0xFFFFFFFE )
  {
    AslLogCallPrintf(
      1,
      "SdbpReadMappedData",
      855,
      "Offset and region size add up to cause an integer overflow or underflow");
    goto LABEL_106;
  }
  v14 = *(_DWORD *)(v52 + 20);
  if ( v14 < (int)v51 + 2 )
  {
    AslLogCallPrintf(
      1,
      "SdbpReadMappedData",
      860,
      "Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)",
      v51,
      2,
      v14);
LABEL_106:
    AslLogCallPrintf(1, "SdbGetTagFromTagID", 3039, "Error reading data");
LABEL_107:
    AslLogCallPrintf(1, "SdbpGetStringTableItemFromStringRef", 888, "Pulled out a non-stringtable item");
    goto LABEL_108;
  }
  if ( *(_WORD *)(v51 + *(_QWORD *)(v52 + 8)) != 0x8801 )
    goto LABEL_107;
  if ( !(_DWORD)v51 || !v52 )
  {
    v15 = *(_QWORD *)&DestinationString.Length;
    *(_QWORD *)&v55.Length = v21;
    goto LABEL_22;
  }
  MappedTagData = SdbpGetMappedTagData(v52, v51);
  v15 = *(_QWORD *)&DestinationString.Length;
  *(_QWORD *)&v55.Length = v21;
LABEL_23:
  v17 = v59;
LABEL_24:
  if ( !MappedTagData )
    goto LABEL_79;
  v2 = v57;
  if ( !(unsigned int)AslStringPatternMatchExW(MappedTagData, *((_QWORD *)v57 + 4), 0, 0) )
    goto LABEL_33;
  v2[4] = v22;
  return v17;
}

```

## disassembly

```asm
0x18000d570  push    rbp
0x18000d572  push    rbx
0x18000d573  push    rsi
0x18000d574  push    rdi
0x18000d575  lea     rbp, [rsp-0D8h]
0x18000d57d  sub     rsp, 1D8h
0x18000d584  mov     rax, cs:__security_cookie
0x18000d58b  xor     rax, rsp
0x18000d58e  mov     [rbp+0F0h+var_40], rax
0x18000d595  mov     rsi, rdx
0x18000d598  mov     [rsp+1F0h+var_180], rdx
0x18000d59d  mov     rdi, rcx
0x18000d5a0  mov     [rsp+1F0h+var_188], rcx
0x18000d5a5  xor     edx, edx; Val
0x18000d5a7  lea     rcx, [rbp+0F0h+var_150]; void *
0x18000d5ab  mov     r8d, 104h; Size
0x18000d5b1  call    memset_0
0x18000d5b6  mov     rdx, [rsi+20h]; SourceString
0x18000d5ba  lea     rcx, [rsp+1F0h+DestinationString]; DestinationString
0x18000d5bf  xor     eax, eax
0x18000d5c1  xorps   xmm0, xmm0
0x18000d5c4  xorps   xmm1, xmm1
0x18000d5c7  mov     [rbp+0F0h+var_168], rax
0x18000d5cb  mov     [rbp+0F0h+var_160], ax
0x18000d5cf  movups  xmmword ptr [rsp+1F0h+DestinationString.Length], xmm0
0x18000d5d4  movups  xmmword ptr [rsp+1F0h+var_198.Length], xmm1
0x18000d5d9  call    cs:__imp_RtlInitUnicodeString
0x18000d5df  mov     rcx, gs:60h
0x18000d5e8  mov     edx, 8; Flags
0x18000d5ed  movzx   r8d, [rsp+1F0h+DestinationString.MaximumLength]; Size
0x18000d5f3  mov     rcx, [rcx+30h]; HeapHandle
0x18000d5f7  call    cs:__imp_RtlAllocateHeap
0x18000d5fd  mov     [rsp+1F0h+var_198.Buffer], rax
0x18000d602  test    rax, rax
0x18000d605  jz      loc_18000DFFD
0x18000d60b  movzx   eax, [rsp+1F0h+DestinationString.MaximumLength]
0x18000d610  lea     rdx, [rsp+1F0h+DestinationString]; SourceString
0x18000d615  mov     [rsp+1F0h+var_198.MaximumLength], ax
0x18000d61a  lea     rcx, [rsp+1F0h+var_198]; DestinationString
0x18000d61f  xor     eax, eax
0x18000d621  xor     r8d, r8d; AllocateDestinationString
0x18000d624  mov     [rsp+1F0h+var_198.Length], ax
0x18000d629  call    cs:__imp_RtlUpcaseUnicodeString
0x18000d62f  mov     ebx, eax
0x18000d631  test    eax, eax
0x18000d633  js      loc_18000E1D2
0x18000d639  movzx   r10d, [rsp+1F0h+var_198.Length]
0x18000d63f  xor     eax, eax
0x18000d641  xor     r8d, r8d
0x18000d644  nop     dword ptr [rax+00h]
0x18000d648  nop     dword ptr [rax+rax+00000000h]
0x18000d650  mov     rcx, r10
0x18000d653  lea     r9, [rbp+0F0h+var_150]
0x18000d657  shr     rcx, 1
0x18000d65a  cmp     r8, rcx
0x18000d65d  jnb     loc_18000E200
0x18000d663  mov     rcx, [rsp+1F0h+var_198.Buffer]
0x18000d668  movzx   edx, word ptr [rcx+r8*2]
0x18000d66d  mov     [r9+rax], dl
0x18000d671  inc     rax
0x18000d674  cmp     rax, 104h
0x18000d67a  jnb     short loc_18000D68D
0x18000d67c  shr     dx, 8
0x18000d680  test    dl, dl
0x18000d682  jnz     loc_18000E1E8
0x18000d688  inc     r8
0x18000d68b  jmp     short loc_18000D650
0x18000d68d  mov     ebx, 0C0000023h
0x18000d692  lea     r9, aFailedToConver_25; "Failed to convert to ANSI [%x]"
0x18000d699  mov     [rsp+1F0h+var_1D0], ebx
0x18000d69d  mov     r8d, 4A6h
0x18000d6a3  lea     rdx, aAslstringupcas; "AslStringUpcaseToMultiByteN"
0x18000d6aa  mov     ecx, 1
0x18000d6af  call    AslLogCallPrintf
0x18000d6b4  mov     r8, [rsp+1F0h+var_198.Buffer]; P
0x18000d6b9  test    r8, r8
0x18000d6bc  jz      short loc_18000D6D3
0x18000d6be  mov     rcx, gs:60h
0x18000d6c7  xor     edx, edx; Flags
0x18000d6c9  mov     rcx, [rcx+30h]; HeapHandle
0x18000d6cd  call    cs:__imp_RtlFreeHeap
0x18000d6d3  mov     [rsp+1F0h+arg_10], r12
0x18000d6db  mov     [rsp+1F0h+var_20], r13
0x18000d6e3  mov     [rsp+1F0h+var_28], r14
0x18000d6eb  mov     [rsp+1F0h+var_30], r15
0x18000d6f3  test    ebx, ebx
0x18000d6f5  js      short loc_18000D763
0x18000d6f7  mov     ebx, [rsi]
0x18000d6f9  lea     eax, [rbx+2]
0x18000d6fc  cmp     eax, 2
0x18000d6ff  jnb     loc_18000D838
0x18000d705  lea     r9, aOffsetAndRegio; "Offset and region size add up to cause "...
0x18000d70c  mov     r8d, 357h
0x18000d712  lea     rdx, aSdbpreadmapped; "SdbpReadMappedData"
0x18000d719  mov     ecx, 1
0x18000d71e  call    AslLogCallPrintf
0x18000d723  lea     r9, aErrorReadingDa; "Error reading data"
0x18000d72a  mov     r8d, 0BDFh
0x18000d730  lea     rdx, aSdbgettagfromt_1; "SdbGetTagFromTagID"
0x18000d737  mov     ecx, 1
0x18000d73c  call    AslLogCallPrintf
0x18000d741  lea     r9, aIndexTagid0xLx; "Index tagid 0x%lx is not referring to t"...
0x18000d748  mov     [rsp+1F0h+var_1D0], ebx
0x18000d74c  mov     r8d, 5EDh
0x18000d752  lea     rdx, aSdbpgetindex; "SdbpGetIndex"
0x18000d759  mov     ecx, 1
0x18000d75e  call    AslLogCallPrintf
0x18000d763  xor     eax, eax
0x18000d765  jmp     loc_18000D7FD
0x18000d76a  mov     ecx, [r8+14h]
0x18000d76e  cmp     ecx, eax
0x18000d770  jb      loc_18000E4F0
0x18000d776  mov     rax, [r8+8]
0x18000d77a  mov     r9d, 8801h
0x18000d780  cmp     [rdx+rax], r9w
0x18000d785  jnz     loc_18000DDFD
0x18000d78b  mov     rcx, r8
0x18000d78e  test    edx, edx
0x18000d790  jz      short loc_18000D79B
0x18000d792  test    rcx, rcx
0x18000d795  jnz     loc_18000DF41
0x18000d79b  mov     r15, qword ptr [rsp+1F0h+DestinationString.Length]
0x18000d7a0  mov     qword ptr [rsp+1F0h+DestinationString.Length], r15
0x18000d7a5  mov     qword ptr [rsp+1F0h+var_198.Length], r14
0x18000d7aa  lea     r9, aSdbpgetstringt; "SdbpGetStringTableItemFromStringRef fai"...
0x18000d7b1  mov     r8d, 3D1h
0x18000d7b7  lea     rdx, aSdbpgetmappeds; "SdbpGetMappedStringFromTable"
0x18000d7be  mov     ecx, 1
0x18000d7c3  call    AslLogCallPrintf
0x18000d7c8  xor     eax, eax
0x18000d7ca  mov     r12d, [rbp+0F0h+var_170]
0x18000d7ce  test    rax, rax
0x18000d7d1  jz      loc_18000DC41
0x18000d7d7  mov     rsi, [rsp+1F0h+var_180]
0x18000d7dc  xor     r9d, r9d
0x18000d7df  xor     r8d, r8d
0x18000d7e2  mov     rcx, rax
0x18000d7e5  mov     rdx, [rsi+20h]
0x18000d7e9  call    AslStringPatternMatchExW
0x18000d7ee  test    eax, eax
0x18000d7f0  jz      loc_18000D8A2
0x18000d7f6  mov     [rsi+10h], r13d
0x18000d7fa  mov     eax, r12d
0x18000d7fd  mov     r15, [rsp+1F0h+var_30]
0x18000d805  mov     r14, [rsp+1F0h+var_28]
0x18000d80d  mov     r13, [rsp+1F0h+var_20]
0x18000d815  mov     r12, [rsp+1F0h+arg_10]
0x18000d81d  mov     rcx, [rbp+0F0h+var_40]
0x18000d824  xor     rcx, rsp; StackCookie
0x18000d827  call    __security_check_cookie
0x18000d82c  add     rsp, 1D8h
0x18000d833  pop     rdi
0x18000d834  pop     rsi
0x18000d835  pop     rbx
0x18000d836  pop     rbp
0x18000d837  retn
0x18000d838  mov     ecx, [rdi+14h]
0x18000d83b  cmp     ecx, eax
0x18000d83d  jb      loc_18000E20C
0x18000d843  mov     rax, [rdi+8]
0x18000d847  mov     edx, 9801h
0x18000d84c  cmp     [rbx+rax], dx
0x18000d850  jnz     loc_18000D741
0x18000d856  mov     edx, ebx
0x18000d858  mov     rcx, rdi
0x18000d85b  call    SdbGetTagDataSize
0x18000d860  xor     ecx, ecx
0x18000d862  cmp     eax, 20000000h
0x18000d867  cmovnz  ecx, eax
0x18000d86a  mov     rax, 0AAAAAAAAAAAAAAABh
0x18000d874  mul     rcx
0x18000d877  mov     rcx, rdi
0x18000d87a  mov     r14, rdx
0x18000d87d  mov     edx, ebx
0x18000d87f  shr     r14, 3
0x18000d883  mov     qword ptr [rsp+1F0h+var_198.Length], r14
0x18000d888  call    SdbpGetMappedTagData
0x18000d88d  mov     qword ptr [rsp+1F0h+DestinationString.Length], rax
0x18000d892  mov     r15, rax
0x18000d895  test    rax, rax
0x18000d898  jz      loc_18000D763
0x18000d89e  mov     r13d, [rsi+10h]
0x18000d8a2  inc     r13d
0x18000d8a5  cmp     r13d, r14d
0x18000d8a8  jnb     loc_18000D763
0x18000d8ae  lea     rcx, ds:0[r13*2]
0x18000d8b6  add     rcx, r13
0x18000d8b9  mov     rax, [r15+rcx*4]
0x18000d8bd  lea     rdi, [r15+rcx*4]
0x18000d8c1  mov     rcx, rax
0x18000d8c4  mov     rdx, rax
0x18000d8c7  mov     r8, rax
0x18000d8ca  shr     rcx, 8
0x18000d8ce  mov     r9, rax
0x18000d8d1  shr     rdx, 10h
0x18000d8d5  mov     r10, rax
0x18000d8d8  shr     r8, 18h
0x18000d8dc  mov     r11, rax
0x18000d8df  shr     r9, 20h
0x18000d8e3  mov     rbx, rax
0x18000d8e6  shr     r10, 28h
0x18000d8ea  shr     r11, 30h
0x18000d8ee  shr     rbx, 38h
0x18000d8f2  test    byte ptr [rsi+14h], 2
0x18000d8f6  jnz     loc_18000DFD4
0x18000d8fc  mov     byte ptr [rbp+0F0h+var_168], bl
0x18000d8ff  mov     byte ptr [rbp+0F0h+var_168+1], r11b
0x18000d903  mov     byte ptr [rbp+0F0h+var_168+2], r10b
0x18000d907  mov     byte ptr [rbp+0F0h+var_168+3], r9b
0x18000d90b  mov     byte ptr [rbp+0F0h+var_168+4], r8b
0x18000d90f  mov     byte ptr [rbp+0F0h+var_168+5], dl
0x18000d912  mov     byte ptr [rbp+0F0h+var_168+6], cl
0x18000d915  mov     byte ptr [rbp+0F0h+var_168+7], al
0x18000d918  mov     byte ptr [rbp+0F0h+var_160], 2Ah ; '*'
0x18000d91c  lea     rdx, [rbp+0F0h+var_150]
0x18000d920  lea     rcx, [rbp+0F0h+var_168]
0x18000d924  call    AslStringPatternMatchExA
0x18000d929  test    eax, eax
0x18000d92b  jz      loc_18000D8A2
0x18000d931  mov     r12d, [rdi+8]
0x18000d935  movzx   r14d, word ptr [rsi+0Ch]
0x18000d93a  mov     rdi, [rsp+1F0h+var_188]
0x18000d93f  mov     [rbp+0F0h+var_170], r12d
0x18000d943  test    r12d, r12d
0x18000d946  jnz     short loc_18000D952
0x18000d948  mov     ebx, [rdi+14h]
0x18000d94b  mov     eax, 0Ch
0x18000d950  jmp     short loc_18000D999
0x18000d952  mov     edx, r12d
0x18000d955  mov     rcx, rdi
0x18000d958  call    SdbGetTagFromTagID
0x18000d95d  mov     ecx, 0F000h
0x18000d962  and     ax, cx
0x18000d965  mov     ecx, 7000h
0x18000d96a  cmp     ax, cx
0x18000d96d  jnz     loc_18000E23F
0x18000d973  mov     edx, r12d
0x18000d976  mov     rcx, rdi
0x18000d979  call    SdbpGetNextTagId
0x18000d97e  mov     ebx, eax
0x18000d980  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x18000d985  test    eax, eax
0x18000d987  jz      short loc_18000D994
0x18000d989  mov     eax, [rdi+14h]
0x18000d98c  cmp     ebx, eax
0x18000d98e  ja      loc_18000DFA6
0x18000d994  lea     eax, [r12+6]
0x18000d999  xor     esi, esi
0x18000d99b  cmp     eax, ebx
0x18000d99d  cmovb   esi, eax
0x18000d9a0  test    esi, esi
0x18000d9a2  jz      loc_18000DC37
0x18000d9a8  lea     ebx, [rsi+2]
0x18000d9ab  cmp     ebx, 2
0x18000d9ae  jb      loc_18000DA59
0x18000d9b4  mov     eax, [rdi+14h]
0x18000d9b7  lea     r15, [rdi+14h]
0x18000d9bb  cmp     eax, ebx
0x18000d9bd  jb      loc_18000E246
0x18000d9c3  mov     rax, [rdi+8]
0x18000d9c7  mov     ecx, esi
0x18000d9c9  movzx   edx, word ptr [rcx+rax]
0x18000d9cd  cmp     dx, r14w
0x18000d9d1  jz      loc_18000DAA0
0x18000d9d7  test    r12d, r12d
0x18000d9da  jz      loc_18000DC4B
0x18000d9e0  mov     edx, r12d
0x18000d9e3  mov     rcx, rdi
0x18000d9e6  call    SdbGetTagFromTagID
0x18000d9eb  mov     ecx, 0F000h
0x18000d9f0  and     ax, cx
0x18000d9f3  mov     ecx, 7000h
0x18000d9f8  cmp     ax, cx
0x18000d9fb  jnz     loc_18000E0FD
0x18000da01  mov     edx, r12d
0x18000da04  mov     rcx, rdi
0x18000da07  call    SdbpGetNextTagId
0x18000da0c  mov     edi, eax
0x18000da0e  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x18000da13  test    eax, eax
0x18000da15  jz      short loc_18000DA22
0x18000da17  mov     eax, [r15]
0x18000da1a  cmp     edi, eax
0x18000da1c  ja      loc_18000E279
0x18000da22  mov     rcx, [rsp+1F0h+var_188]
0x18000da27  mov     edx, esi
0x18000da29  call    SdbpGetNextTagId
0x18000da2e  mov     ebx, eax
0x18000da30  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x18000da35  test    eax, eax
0x18000da37  jz      loc_18000E0EE
0x18000da3d  cmp     ebx, edi
0x18000da3f  jnb     loc_18000E0F6
0x18000da45  cmp     ebx, esi
0x18000da47  jbe     loc_18000E0F6
0x18000da4d  mov     rdi, [rsp+1F0h+var_188]
0x18000da52  mov     esi, ebx
0x18000da54  jmp     loc_18000D9A0
0x18000da59  lea     r9, aOffsetAndRegio; "Offset and region size add up to cause "...
0x18000da60  mov     r8d, 357h
  ... truncated ...
```
