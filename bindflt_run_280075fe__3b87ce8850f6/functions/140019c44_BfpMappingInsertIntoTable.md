# BfpMappingInsertIntoTable

- ea: `0x140019c44`
- end: `0x14001ad6e`
- name: `BfpMappingInsertIntoTable`
- size: `4394`
- prototype: `__int64 __fastcall(int, int, int, int, PFLT_CONTEXT Context, int, __int64, __int64)`
- caller_count: `2`
- callee_count: `19`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001d974`
- `0x14001efcc`

## callees

- `0x140001348`
- `0x1400030fc`
- `0x140003304`
- `0x140003e14`
- `0x140004060`
- `0x140017bb8`
- `0x140019b40`
- `0x140019c44`
- `0x14001b280`
- `0x14001baf4`
- `0x14001caf8`
- `0x14001cd84`
- `0x14001d130`
- `0x14001d194`
- `0x14001e854`
- `0x14001ea10`
- `0x140020180`
- `0x140022d58`
- `0x140023b7c`

## import_xrefs

- `ntoskrnl!RtlRbRemoveNode` at `0x14001ad4b`
- `ntoskrnl!RtlRbRemoveNode` at `0x14001ad4b`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001ab0a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001ab0a`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x14001a061`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x14001a4ce`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x14001a061`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x14001a4ce`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001a2b8`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001a2d7`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001a2b8`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001a2d7`

## pseudocode

```c
__int64 __fastcall BfpMappingInsertIntoTable(
        __int64 *a1,
        unsigned int a2,
        PFLT_INSTANCE *a3,
        __int64 a4,
        PFLT_CONTEXT Context,
        int a6,
        __int64 a7,
        __int64 a8)
{
  __int64 *v8; // r14
  __int16 v10; // r12
  char v11; // r15
  __int64 v12; // rsi
  unsigned __int64 v13; // rdi
  int v14; // r14d
  int v15; // eax
  unsigned __int64 v16; // rax
  WCHAR *v17; // rcx
  __int64 v18; // r9
  unsigned __int16 v19; // r8
  __int64 v20; // rdx
  unsigned __int16 v21; // cx
  unsigned __int16 v22; // dx
  unsigned __int16 v23; // dx
  __int64 v24; // r10
  __int64 *v25; // r14
  unsigned __int64 v26; // rdi
  int v27; // ebx
  int v28; // eax
  unsigned __int64 v29; // rax
  char v30; // r12
  unsigned __int64 v31; // rbx
  BOOL v32; // r14d
  int v33; // edi
  int v34; // eax
  __int64 v35; // rdx
  unsigned __int64 v36; // rax
  int v37; // edx
  int PathTree; // ebx
  __int64 v39; // r8
  __int64 *v40; // r15
  unsigned __int64 v41; // rbx
  int v42; // edi
  unsigned __int64 v43; // rax
  int v44; // esi
  char v45; // r13
  char v47; // r8
  PFLT_INSTANCE *v48; // r14
  int v49; // r9d
  PVOID v50; // rdi
  __int64 v51; // r14
  unsigned __int64 v52; // rbx
  int v53; // edi
  int v54; // eax
  unsigned __int64 v55; // rax
  __int64 v56; // r8
  __int64 v57; // r14
  unsigned __int64 v58; // rbx
  int v59; // edi
  unsigned __int64 v60; // rax
  int v61; // edx
  int v62; // r9d
  int v63; // r9d
  int v64; // r9d
  int v65; // r9d
  __int64 **v66; // rdi
  int v67; // edx
  int v68; // r9d
  __int64 v69; // rcx
  __int64 v70; // rax
  __int64 v71; // rcx
  int v72; // [rsp+28h] [rbp-B1h]
  int v73; // [rsp+30h] [rbp-A9h]
  char v74; // [rsp+38h] [rbp-A1h]
  char v75; // [rsp+38h] [rbp-A1h]
  char v76; // [rsp+38h] [rbp-A1h]
  char v77; // [rsp+38h] [rbp-A1h]
  char v78; // [rsp+38h] [rbp-A1h]
  char v79; // [rsp+40h] [rbp-99h]
  char v80; // [rsp+40h] [rbp-99h]
  __int64 v81; // [rsp+40h] [rbp-99h]
  char v82; // [rsp+40h] [rbp-99h]
  char v83; // [rsp+59h] [rbp-80h]
  UNICODE_STRING String2; // [rsp+68h] [rbp-71h] BYREF
  PVOID P; // [rsp+78h] [rbp-61h]
  __int64 v86; // [rsp+80h] [rbp-59h] BYREF
  UNICODE_STRING SourceString; // [rsp+88h] [rbp-51h] BYREF
  __int128 v88; // [rsp+98h] [rbp-41h] BYREF
  BOOL v89; // [rsp+A8h] [rbp-31h]
  __int64 v90; // [rsp+B0h] [rbp-29h] BYREF
  PVOID v91; // [rsp+B8h] [rbp-21h]
  UNICODE_STRING String1; // [rsp+C0h] [rbp-19h] BYREF
  __int64 v93; // [rsp+D0h] [rbp-9h]
  unsigned int v95; // [rsp+130h] [rbp+57h]

  v95 = a2;
  v8 = a1;
  v86 = 0;
  v90 = 0;
  P = 0;
  v10 = a2;
  String2 = 0;
  String1 = 0;
  if ( (a2 & 0x11) == 0x10 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)-1073741811;
    v62 = 93;
    v75 = -91;
LABEL_177:
    LOBYTE(a2) = 2;
    WPP_RECORDER_SF_sD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      8,
      v62,
      (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
      v75);
    return (unsigned int)-1073741811;
  }
  v91 = 0;
  v93 = 0;
  v83 = BfWalkContainerRootId(*a1, &String2);
  v11 = v83;
  if ( a8 )
    BfWalkContainerRootId(a8, &String1);
  v12 = *(_QWORD *)(a4 + 24);
  if ( String2.Length )
  {
    while ( 1 )
    {
      v13 = *(_QWORD *)v12;
      *(_QWORD *)&SourceString.Length = &String2;
      SourceString.Buffer = 0;
      if ( (*(_BYTE *)(v12 + 8) & 1) != 0 )
      {
        if ( v13 )
          v13 ^= v12;
        else
          v13 = 0;
      }
      v14 = *(_BYTE *)(v12 + 8) & 1;
      if ( !v13 )
        goto LABEL_265;
      do
      {
        v15 = BfpRBComparePathNodes(&SourceString, v13);
        if ( v15 < 0 )
        {
          v16 = *(_QWORD *)v13;
        }
        else
        {
          if ( v15 <= 0 )
            break;
          v16 = *(_QWORD *)(v13 + 8);
        }
        if ( v14 && v16 )
          v13 ^= v16;
        else
          v13 = v16;
      }
      while ( v13 );
      v17 = 0;
      v10 = v95;
      if ( !v13 )
      {
LABEL_265:
        if ( (v10 & 0x100) == 0 )
          goto LABEL_47;
        v26 = *(_QWORD *)v12;
        LOBYTE(SourceString.Buffer) = 1;
        if ( (*(_BYTE *)(v12 + 8) & 1) != 0 )
        {
          if ( v26 )
            v26 ^= v12;
          else
            v26 = 0;
        }
        v27 = *(_BYTE *)(v12 + 8) & 1;
        if ( !v26 )
          goto LABEL_47;
        do
        {
          v28 = BfpRBComparePathNodes(&SourceString, v26);
          if ( v28 < 0 )
          {
            v29 = *(_QWORD *)v26;
          }
          else
          {
            if ( v28 <= 0 )
              break;
            v29 = *(_QWORD *)(v26 + 8);
          }
          if ( v27 && v29 )
            v26 ^= v29;
          else
            v26 = v29;
        }
        while ( v26 );
        if ( !v26 )
          goto LABEL_47;
        PathTree = -1073741635;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return (unsigned int)PathTree;
        v65 = 102;
LABEL_232:
        WPP_RECORDER_SF_sDZ(WPP_GLOBAL_Control->DeviceExtension, a2, 8, v65);
        return (unsigned int)PathTree;
      }
      if ( (*(_DWORD *)(v13 - 8) & 2) != 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v62 = 100;
          v75 = 77;
          goto LABEL_177;
        }
        return (unsigned int)-1073741811;
      }
      if ( !v11 )
        goto LABEL_46;
      v18 = *a1 + 6;
      v19 = *(_WORD *)(*a1 + 4) >> 1;
      if ( String2.Length )
      {
        v23 = ((__int64)String2.Buffer - v18) >> 1;
        if ( v23 >= v19 )
        {
LABEL_24:
          if ( v23 == v19 )
          {
            v11 = 0;
            v83 = 0;
            *(_DWORD *)&String2.Length = 0;
            goto LABEL_32;
          }
        }
        else
        {
          while ( *(_WORD *)(v18 + 2LL * v23) != 92 )
          {
            if ( ++v23 >= v19 )
              goto LABEL_24;
          }
        }
        v22 = v23 + 1;
      }
      else
      {
        v20 = *(_WORD *)(*a1 + 2) >> 1;
        v21 = v20 + 1;
        if ( *(_WORD *)(v18 + 2 * v20) != 92 )
          v21 = *(_WORD *)(*a1 + 2) >> 1;
        v22 = v21;
        String2.Buffer = (PWSTR)(v18 + 2LL * v21);
      }
      v11 = 0;
      v83 = 0;
      v24 = v22;
      while ( 1 )
      {
        if ( v22 >= v19 )
          goto LABEL_31;
        if ( *(_WORD *)(v18 + 2LL * v22) == 92 )
          break;
        ++v22;
      }
      v11 = 1;
      v83 = 1;
LABEL_31:
      v17 = (WCHAR *)(v18 + 2 * v24);
      String2.MaximumLength = 2 * (v22 - v24);
      String2.Length = String2.MaximumLength;
LABEL_32:
      String2.Buffer = v17;
      if ( a8 )
        BfWalkContainerRootId(a8, &String1);
      v25 = (__int64 *)(v13 + 72);
      v12 = *(_QWORD *)(v13 + 72);
      if ( (unsigned __int8)BfpPathTreeEmpty(v12) )
      {
        if ( !v12 )
        {
          PathTree = BfpCreatePathTree(v13 + 72);
          if ( PathTree < 0 )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              return (unsigned int)PathTree;
            v80 = PathTree;
            v63 = 101;
            v76 = -124;
LABEL_184:
            LOBYTE(a2) = 2;
            WPP_RECORDER_SF_sDd(
              WPP_GLOBAL_Control->DeviceExtension,
              a2,
              8,
              v63,
              (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
              (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
              v76,
              v80);
            return (unsigned int)PathTree;
          }
          v69 = *(_QWORD *)(v13 + 80);
          if ( v69 )
            *(_QWORD *)(v69 + 80) = *v25;
        }
        v12 = *v25;
LABEL_46:
        v86 = 0;
LABEL_47:
        if ( (v10 & 0x200) == 0 || !v11 )
        {
          while ( 1 )
          {
            v88 = 0;
            if ( v11 || (v30 = 0, a6) )
              v30 = 1;
            v31 = *(_QWORD *)v12;
            *(_QWORD *)&v88 = &String2;
            BYTE8(v88) = 0;
            v32 = v11 == 0;
            v89 = v32;
            if ( (*(_BYTE *)(v12 + 8) & 1) != 0 )
            {
              if ( v31 )
                v31 ^= v12;
              else
                v31 = 0;
            }
            v33 = *(_BYTE *)(v12 + 8) & 1;
            if ( !v31 )
              goto LABEL_59;
            do
            {
              v34 = BfpRBComparePathNodes(&v88, v31);
              if ( v34 < 0 )
              {
                v36 = *(_QWORD *)v31;
              }
              else
              {
                if ( v34 <= 0 )
                  break;
                v36 = *(_QWORD *)(v31 + 8);
              }
              if ( v33 && v36 )
                v31 ^= v36;
              else
                v31 = v36;
            }
            while ( v31 );
            if ( v31 )
            {
              v40 = (__int64 *)(v31 - 8);
              v86 = v31 - 8;
              if ( !v83 )
              {
                if ( (*(_DWORD *)v40 & 1) != 0 )
                {
                  v47 = v95;
                  if ( (v95 & 0x40) != 0 )
                  {
                    PathTree = -1073741811;
                    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                      goto LABEL_112;
                    v64 = 109;
                    v77 = 78;
                    goto LABEL_194;
                  }
                  v35 = v40[9];
                  if ( v35 && !(unsigned __int8)BfpDoMappingFlagsMatch(v95, *(unsigned int *)(v35 + 8)) )
                  {
                    PathTree = -1073741811;
                    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                      WPP_RECORDER_SF_sDDD(WPP_GLOBAL_Control->DeviceExtension, v35, 8, 110, v72, v73, 90, v35, v47);
LABEL_112:
                    v45 = 0;
LABEL_113:
                    v50 = v91;
                    if ( v91 )
                    {
                      RtlRbRemoveNode(v93, (char *)v91 + 8);
                      BfpDeletePathTierNode(v50);
                    }
                    if ( !v45 )
                    {
LABEL_116:
                      if ( P )
                        BfpDeleteTargetEntry(P);
                      return (unsigned int)PathTree;
                    }
LABEL_216:
                    BfpDeletePathTierNode(*(PVOID *)(a4 + 32));
                    *(_QWORD *)(a4 + 32) = 0;
                    goto LABEL_116;
                  }
                  if ( (v47 & 1) == 0 )
                  {
                    PathTree = -1073741811;
                    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                      goto LABEL_112;
                    v64 = 111;
                    v77 = 102;
LABEL_194:
                    LOBYTE(v35) = 2;
                    WPP_RECORDER_SF_sD(
                      WPP_GLOBAL_Control->DeviceExtension,
                      v35,
                      8,
                      v64,
                      (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
                      (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
                      v77);
                    goto LABEL_112;
                  }
                }
                PathTree = BfpCreateTargetEntry(Context);
                if ( PathTree < 0 )
                {
                  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                    goto LABEL_112;
                  v79 = PathTree;
                  v49 = 112;
                  v74 = 115;
                  goto LABEL_262;
                }
                if ( v40[9] )
                {
                  if ( (unsigned __int8)BfTargetEntryExistsInMappingInformation(0) )
                  {
                    PathTree = -1073741811;
                    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                      goto LABEL_112;
                    v79 = 13;
                    v49 = 113;
                    v74 = 127;
                    goto LABEL_262;
                  }
                  v48 = a3;
                  *(_BYTE *)(v40[9] + 48) = 1;
                }
                else
                {
                  *(_DWORD *)v40 = v32;
                  PathTree = BfpCreateMappingInformation(*a1, v95, v40 + 9);
                  if ( PathTree < 0 )
                  {
                    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                      goto LABEL_112;
                    v79 = PathTree;
                    v49 = 114;
                    v74 = -109;
                    goto LABEL_262;
                  }
                  v70 = *a1;
                  SourceString = 0;
                  v71 = *(unsigned __int16 *)(v70 + 4);
                  SourceString.Buffer = (PWSTR)(v70 + 6);
                  SourceString.Length = v71;
                  SourceString.MaximumLength = v71;
                  PathTree = BfAllocateUnicodeString(v71, v40 + 7);
                  if ( PathTree < 0 )
                  {
                    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                      goto LABEL_112;
                    v79 = PathTree;
                    v49 = 115;
                    v74 = -97;
                    goto LABEL_262;
                  }
                  RtlCopyUnicodeString((PUNICODE_STRING)(v40 + 7), &SourceString);
                  v48 = a3;
                  v40[6] = (__int64)*a3;
                }
                if ( (v95 & 2) != 0 )
                {
                  PathTree = BfpCreateTargetEntry(v48);
                  if ( PathTree < 0 )
                  {
                    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                      goto LABEL_112;
                    v79 = PathTree;
                    v49 = 116;
                    v74 = -77;
LABEL_262:
                    LOBYTE(v37) = 2;
                    WPP_RECORDER_SF_sDd(
                      WPP_GLOBAL_Control->DeviceExtension,
                      v37,
                      8,
                      v49,
                      (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
                      (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
                      v74,
                      v79);
                    goto LABEL_112;
                  }
                  PathTree = BfpInsertTargetEntryIntoMappingInformation(*v48);
                  if ( PathTree < 0 )
                  {
                    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                      goto LABEL_112;
                    v79 = PathTree;
                    v49 = 117;
                    v74 = -67;
                    goto LABEL_262;
                  }
                  P = 0;
                }
                PathTree = BfpInsertTargetEntryIntoMappingInformation(*v48);
                if ( PathTree < 0 )
                {
                  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                    goto LABEL_112;
                  v79 = PathTree;
                  v49 = 118;
                  v74 = -54;
                  goto LABEL_262;
                }
              }
            }
            else
            {
LABEL_59:
              PathTree = BfpCreatePathTierNode(&String2, (__int64)a3, *a1, 0, 0, (__int64)&v86);
              if ( PathTree < 0 )
              {
                if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  goto LABEL_112;
                v79 = PathTree;
                v49 = 104;
                v74 = -9;
                goto LABEL_262;
              }
              v40 = (__int64 *)v86;
              if ( !v83 )
              {
                if ( (v95 & 2) != 0 )
                {
                  PathTree = BfpCreateTargetEntry(a3);
                  if ( PathTree < 0 )
                  {
                    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                      goto LABEL_112;
                    v79 = PathTree;
                    v49 = 105;
                    v74 = 8;
                    goto LABEL_262;
                  }
                  PathTree = BfpInsertTargetEntryIntoMappingInformation(*a3);
                  if ( PathTree < 0 )
                  {
                    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                      goto LABEL_112;
                    v79 = PathTree;
                    v49 = 106;
                    v74 = 18;
                    goto LABEL_262;
                  }
                  P = 0;
                }
                PathTree = BfpCreateTargetEntry(Context);
                if ( PathTree < 0 )
                {
                  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                    goto LABEL_112;
                  v79 = PathTree;
                  v49 = 107;
                  v74 = 33;
                  goto LABEL_262;
                }
                PathTree = BfpInsertTargetEntryIntoMappingInformation(*a3);
                if ( PathTree < 0 )
                {
                  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                    goto LABEL_112;
                  v79 = PathTree;
                  v49 = 108;
                  v74 = 43;
                  goto LABEL_262;
                }
              }
              v41 = *(_QWORD *)v12;
              if ( (*(_BYTE *)(v12 + 8) & 1) != 0 )
              {
                if ( v41 )
                  v41 ^= v12;
                else
                  v41 = 0;
              }
              LOBYTE(v39) = 0;
              v42 = *(_BYTE *)(v12 + 8) & 1;
              if ( v41 )
              {
                while ( 1 )
                {
                  if ( (int)BfpRBComparePathNodes(&v88, v41) < 0 )
                  {
                    v43 = *(_QWORD *)v41;
                    if ( v42 )
                    {
                      if ( !v43 )
                      {
LABEL_93:
                        LOBYTE(v39) = 0;
                        break;
                      }
                      v43 ^= v41;
                    }
                    if ( !v43 )
                      goto LABEL_93;
                  }
                  else
                  {
                    v43 = *(_QWORD *)(v41 + 8);
                    if ( v42 )
                    {
                      if ( !v43 )
                      {
LABEL_71:
                        LOBYTE(v39) = 1;
                        break;
                      }
                      v43 ^= v41;
                    }
                    if ( !v43 )
                      goto LABEL_71;
                  }
                  v41 = v43;
                }
              }
              RtlRbInsertNodeEx(v12, v41, v39, v40 + 1);
            }
            if ( !v91 )
            {
              v91 = v40;
              v93 = v12;
            }
            if ( a8
              && RtlCompareUnicodeString(&String1, &g_NoShortComponent, 0)
              && RtlCompareUnicodeString(&String1, &String2, 0) )
            {
              v88 = 0;
              if ( v30 )
                v51 = v40[10];
              else
                v51 = 0;
              v52 = *(_QWORD *)v12;
              *(_QWORD *)&v88 = &String1;
              BYTE8(v88) = 0;
              if ( (*(_BYTE *)(v12 + 8) & 1) != 0 && v52 )
                v52 ^= v12;
              v53 = *(_BYTE *)(v12 + 8) & 1;
              if ( !v52 )
                goto LABEL_145;
              do
              {
                v54 = BfpRBComparePathNodes(&v88, v52);
                if ( v54 < 0 )
                {
                  v55 = *(_QWORD *)v52;
                }
                else
                {
                  if ( v54 <= 0 )
                    break;
                  v55 = *(_QWORD *)(v52 + 8);
                }
                if ( v53 && v55 )
                  v52 ^= v55;
                else
                  v52 = v55;
              }
              while ( v52 );
              if ( v52 )
              {
                v90 = v52 - 8;
              }
              else
              {
LABEL_145:
                PathTree = BfpCreatePathTierNode(&String1, 0, 0, v40[9], v51, (__int64)&v90);
                if ( PathTree < 0 )
                {
                  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                    goto LABEL_112;
                  v79 = PathTree;
                  v49 = 119;
                  v74 = 31;
                  goto LABEL_262;
                }
                v57 = v90;
                v58 = *(_QWORD *)v12;
                if ( (*(_BYTE *)(v12 + 8) & 1) != 0 )
                {
                  if ( v58 )
                    v58 ^= v12;
                  else
                    v58 = 0;
                }
                LOBYTE(v56) = 0;
                v59 = *(_BYTE *)(v12 + 8) & 1;
                if ( v58 )
                {
                  while ( 1 )
                  {
                    if ( (int)BfpRBComparePathNodes(&v88, v58) < 0 )
                    {
                      v60 = *(_QWORD *)v58;
                      if ( v59 )
                      {
                        if ( !v60 )
                        {
LABEL_174:
                          LOBYTE(v56) = 0;
                          break;
                        }
                        v60 ^= v58;
                      }
                      if ( !v60 )
                        goto LABEL_174;
                    }
                    else
                    {
                      v60 = *(_QWORD *)(v58 + 8);
                      if ( v59 )
                      {
                        if ( !v60 )
                        {
LABEL_152:
                          LOBYTE(v56) = 1;
                          break;
                        }
                        v60 ^= v58;
                      }
                      if ( !v60 )
                        goto LABEL_152;
                    }
                    v58 = v60;
                  }
                }
                RtlRbInsertNodeEx(v12, v58, v56, v57 + 8);
                v40[11] = v57;
              }
            }
            if ( v83 )
              v12 = v40[10];
            LODWORD(v8) = (_DWORD)a1;
            v83 = BfWalkContainerRootId(*a1, &String2);
            if ( a8 )
              BfWalkContainerRootId(a8, &String1);
            if ( !String2.Length )
            {
              v44 = (int)a3;
              v45 = 0;
              goto LABEL_83;
            }
            v11 = v83;
          }
        }
        PathTree = -1073741766;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return (unsigned int)PathTree;
        v65 = 103;
        goto LABEL_232;
      }
      v86 = 0;
      v83 = v11;
    }
  }
  v66 = (__int64 **)(a4 + 32);
  if ( *v66 || !(unsigned __int8)BfpPathTreeEmpty(v12) )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)-1073741811;
    v62 = 94;
    v75 = -54;
    goto LABEL_177;
  }
  v45 = 1;
  v81 = v12;
  v44 = (int)a3;
  PathTree = BfpCreatePathTierNode(&g_rootName, (__int64)a3, *v8, 0, v81, (__int64)v66);
  if ( PathTree < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)PathTree;
    v80 = PathTree;
    v63 = 95;
    v76 = -21;
    goto LABEL_184;
  }
  if ( (v10 & 2) != 0 )
  {
    PathTree = BfpCreateTargetEntry(a3);
    if ( PathTree < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_216;
      v82 = PathTree;
      v68 = 96;
      v78 = -3;
LABEL_215:
      LOBYTE(v67) = 2;
      WPP_RECORDER_SF_sDd(
        WPP_GLOBAL_Control->DeviceExtension,
        v67,
        8,
        v68,
        (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
        v78,
        v82);
      goto LABEL_216;
    }
    PathTree = BfpInsertTargetEntryIntoMappingInformation(*a3);
    if ( PathTree < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_216;
      v82 = PathTree;
      v68 = 97;
      v78 = 7;
      goto LABEL_215;
    }
  }
  PathTree = BfpCreateTargetEntry(Context);
  if ( PathTree < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_216;
    v82 = PathTree;
    v68 = 98;
    v78 = 22;
    goto LABEL_215;
  }
  PathTree = BfpInsertTargetEntryIntoMappingInformation(*a3);
  if ( PathTree < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_216;
    v82 = PathTree;
    v68 = 99;
    v78 = 32;
    goto LABEL_215;
  }
  v40 = *v66;
LABEL_83:
  if ( a6 )
  {
    PathTree = BfpMappingInsertExceptions((_DWORD)v8, (_DWORD)v40, v44, a6, a7);
    if ( PathTree < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v61) = 2;
        WPP_RECORDER_SF_sDd(
          WPP_GLOBAL_Control->DeviceExtension,
          v61,
          8,
          120,
          (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
          113,
          PathTree);
      }
      goto LABEL_113;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140019c44  mov     rax, rsp
0x140019c47  mov     [rax+20h], r9
0x140019c4b  mov     [rax+18h], r8
0x140019c4f  mov     [rax+10h], edx
0x140019c52  mov     [rax+8], rcx
0x140019c56  push    rbp
0x140019c57  push    rbx
0x140019c58  push    rsi
0x140019c59  push    rdi
0x140019c5a  push    r12
0x140019c5c  push    r13
0x140019c5e  push    r14
0x140019c60  push    r15
0x140019c62  lea     rbp, [rax-47h]
0x140019c66  sub     rsp, 0D8h
0x140019c6d  mov     eax, edx
0x140019c6f  mov     r14, rcx
0x140019c72  xor     ecx, ecx
0x140019c74  and     al, 11h
0x140019c76  mov     [rbp+3Fh+var_98], rcx
0x140019c7a  xorps   xmm0, xmm0
0x140019c7d  mov     [rbp+3Fh+var_68], rcx
0x140019c81  xorps   xmm1, xmm1
0x140019c84  mov     [rbp+3Fh+var_B8], rcx
0x140019c88  mov     rdi, r9
0x140019c8b  mov     [rbp+3Fh+P], rcx
0x140019c8f  mov     r12d, edx
0x140019c92  movups  xmmword ptr [rbp+3Fh+String2.Length], xmm0
0x140019c96  movups  xmmword ptr [rbp+3Fh+String1.Length], xmm1
0x140019c9a  cmp     al, 10h
0x140019c9c  jz      loc_14001A36F
0x140019ca2  mov     [rbp+3Fh+var_60], rcx
0x140019ca6  lea     rdx, [rbp+3Fh+String2]
0x140019caa  mov     [rbp+3Fh+var_48], rcx
0x140019cae  mov     rcx, [r14]
0x140019cb1  call    BfWalkContainerRootId
0x140019cb6  mov     r8, [rbp+3Fh+arg_38]
0x140019cbd  xor     ecx, ecx
0x140019cbf  mov     [rbp+3Fh+var_BF], al
0x140019cc2  mov     r15b, al
0x140019cc5  test    r8, r8
0x140019cc8  jz      short loc_140019CD8
0x140019cca  lea     rdx, [rbp+3Fh+String1]
0x140019cce  mov     rcx, r8
0x140019cd1  call    BfWalkContainerRootId
0x140019cd6  xor     ecx, ecx
0x140019cd8  movzx   ebx, [rbp+3Fh+String2.Length]
0x140019cdc  mov     rsi, [rdi+18h]
0x140019ce0  test    bx, bx
0x140019ce3  jz      loc_14001A82C
0x140019ce9  mov     r13d, 1
0x140019cef  lea     rax, [rbp+3Fh+String2]
0x140019cf3  mov     rdi, [rsi]
0x140019cf6  xorps   xmm0, xmm0
0x140019cf9  movups  xmmword ptr [rbp+3Fh+SourceString.Length], xmm0
0x140019cfd  mov     qword ptr [rbp+3Fh+SourceString.Length], rax
0x140019d01  mov     byte ptr [rbp+3Fh+SourceString.Buffer], cl
0x140019d04  test    [rsi+8], r13b
0x140019d08  jnz     loc_14001A38D
0x140019d0e  movzx   r14d, byte ptr [rsi+8]
0x140019d13  and     r14d, r13d
0x140019d16  test    rdi, rdi
0x140019d19  jz      loc_140019E7B
0x140019d1f  mov     rdx, rdi
0x140019d22  lea     rcx, [rbp+3Fh+SourceString]
0x140019d26  call    BfpRBComparePathNodes
0x140019d2b  test    eax, eax
0x140019d2d  js      short loc_140019DAD
0x140019d2f  jle     short loc_140019D46
0x140019d31  mov     rax, [rdi+8]
0x140019d35  test    r14d, r14d
0x140019d38  jnz     loc_140019E5C
0x140019d3e  mov     rdi, rax
0x140019d41  test    rdi, rdi
0x140019d44  jnz     short loc_140019D1F
0x140019d46  movzx   ebx, [rbp+3Fh+String2.Length]
0x140019d4a  xor     ecx, ecx
0x140019d4c  mov     r12d, [rbp+3Fh+arg_8]
0x140019d50  test    rdi, rdi
0x140019d53  jz      loc_140019E7B
0x140019d59  mov     eax, [rdi-8]
0x140019d5c  test    al, 2
0x140019d5e  jnz     loc_14001A647
0x140019d64  test    r15b, r15b
0x140019d67  jz      loc_140019ECC
0x140019d6d  mov     rax, [rbp+3Fh+arg_0]
0x140019d71  mov     rax, [rax]
0x140019d74  movzx   r8d, word ptr [rax+4]
0x140019d79  lea     r9, [rax+6]
0x140019d7d  shr     r8w, 1
0x140019d81  test    bx, bx
0x140019d84  jnz     short loc_140019DB2
0x140019d86  movzx   eax, word ptr [rax+2]
0x140019d8a  shr     ax, 1
0x140019d8d  movzx   edx, ax
0x140019d90  cmp     word ptr [r9+rdx*2], 5Ch ; '\'
0x140019d96  lea     ecx, [rdx+r13]
0x140019d9a  cmovnz  cx, dx
0x140019d9e  movzx   edx, cx
0x140019da1  xor     ecx, ecx
0x140019da3  lea     rax, [r9+rdx*2]
0x140019da7  mov     [rbp+3Fh+String2.Buffer], rax
0x140019dab  jmp     short loc_140019DE8
0x140019dad  mov     rax, [rdi]
0x140019db0  jmp     short loc_140019D35
0x140019db2  mov     rax, [rbp+3Fh+String2.Buffer]
0x140019db6  sub     rax, r9
0x140019db9  sar     rax, 1
0x140019dbc  movzx   edx, ax
0x140019dbf  cmp     ax, r8w
0x140019dc3  jnb     short loc_140019DDA
0x140019dc5  movzx   eax, dx
0x140019dc8  cmp     word ptr [r9+rax*2], 5Ch ; '\'
0x140019dce  jz      short loc_140019DE4
0x140019dd0  add     dx, r13w
0x140019dd4  cmp     dx, r8w
0x140019dd8  jb      short loc_140019DC5
0x140019dda  cmp     dx, r8w
0x140019dde  jz      loc_14001A22F
0x140019de4  add     dx, r13w
0x140019de8  mov     r15b, cl
0x140019deb  mov     [rbp+3Fh+var_BF], cl
0x140019dee  movzx   r10d, dx
0x140019df2  cmp     dx, r8w
0x140019df6  jnb     short loc_140019E10
0x140019df8  movzx   eax, dx
0x140019dfb  cmp     word ptr [r9+rax*2], 5Ch ; '\'
0x140019e01  jz      short loc_140019E09
0x140019e03  add     dx, r13w
0x140019e07  jmp     short loc_140019DF2
0x140019e09  mov     r15b, r13b
0x140019e0c  mov     [rbp+3Fh+var_BF], r13b
0x140019e10  sub     dx, r10w
0x140019e14  lea     rcx, [r9+r10*2]
0x140019e18  add     dx, dx
0x140019e1b  mov     [rbp+3Fh+String2.MaximumLength], dx
0x140019e1f  movzx   ebx, dx
0x140019e22  mov     [rbp+3Fh+String2.Length], dx
0x140019e26  mov     [rbp+3Fh+String2.Buffer], rcx
0x140019e2a  mov     r8, [rbp+3Fh+arg_38]
0x140019e31  test    r8, r8
0x140019e34  jnz     short loc_140019E6D
0x140019e36  lea     r14, [rdi+48h]
0x140019e3a  mov     rsi, [r14]
0x140019e3d  mov     rcx, rsi
0x140019e40  call    BfpPathTreeEmpty
0x140019e45  xor     ecx, ecx
0x140019e47  test    al, al
0x140019e49  jnz     loc_14001A6AF
0x140019e4f  mov     [rbp+3Fh+var_98], rcx
0x140019e53  mov     [rbp+3Fh+var_BF], r15b
0x140019e57  jmp     loc_140019CEF
0x140019e5c  test    rax, rax
0x140019e5f  jz      loc_140019D3E
0x140019e65  xor     rdi, rax
0x140019e68  jmp     loc_140019D41
0x140019e6d  lea     rdx, [rbp+3Fh+String1]
0x140019e71  mov     rcx, r8
0x140019e74  call    BfWalkContainerRootId
0x140019e79  jmp     short loc_140019E36
0x140019e7b  bt      r12d, 8
0x140019e80  jnb     short loc_140019ED0
0x140019e82  mov     rdi, [rsi]
0x140019e85  mov     byte ptr [rbp+3Fh+SourceString.Buffer], r13b
0x140019e89  test    [rsi+8], r13b
0x140019e8d  jz      short loc_140019E9B
0x140019e8f  test    rdi, rdi
0x140019e92  jz      loc_14001A811
0x140019e98  xor     rdi, rsi
0x140019e9b  movzx   ebx, byte ptr [rsi+8]
0x140019e9f  and     ebx, r13d
0x140019ea2  test    rdi, rdi
0x140019ea5  jz      short loc_140019ED0
0x140019ea7  mov     rdx, rdi
0x140019eaa  lea     rcx, [rbp+3Fh+SourceString]
0x140019eae  call    BfpRBComparePathNodes
0x140019eb3  xor     ecx, ecx
0x140019eb5  test    eax, eax
0x140019eb7  js      loc_14001A7B6
0x140019ebd  jle     loc_14001A7CE
0x140019ec3  mov     rax, [rdi+8]
0x140019ec7  jmp     loc_14001A7B9
0x140019ecc  mov     [rbp+3Fh+var_98], rcx
0x140019ed0  bt      r12d, 9
0x140019ed5  jb      loc_14001AA8E
0x140019edb  mov     [rsp+50h], cl
0x140019edf  xorps   xmm0, xmm0
0x140019ee2  movups  [rbp+3Fh+var_80], xmm0
0x140019ee6  test    r15b, r15b
0x140019ee9  jz      loc_14001A118
0x140019eef  mov     r12b, r13b
0x140019ef2  mov     rbx, [rsi]
0x140019ef5  lea     rax, [rbp+3Fh+String2]
0x140019ef9  test    r15b, r15b
0x140019efc  mov     qword ptr [rbp+3Fh+var_80], rax
0x140019f00  mov     r14d, ecx
0x140019f03  mov     byte ptr [rbp+3Fh+var_80+8], cl
0x140019f06  setz    r14b
0x140019f0a  mov     [rbp+3Fh+var_70], r14d
0x140019f0e  test    [rsi+8], r13b
0x140019f12  jnz     loc_14001A4E3
0x140019f18  movzx   edi, byte ptr [rsi+8]
0x140019f1c  and     edi, r13d
0x140019f1f  test    rbx, rbx
0x140019f22  jz      short loc_140019F5F
0x140019f24  mov     rdx, rbx
0x140019f27  lea     rcx, [rbp+3Fh+var_80]
0x140019f2b  call    BfpRBComparePathNodes
0x140019f30  test    eax, eax
0x140019f32  js      loc_14001A04A
0x140019f38  jle     short loc_140019F4E
0x140019f3a  mov     rax, [rbx+8]
0x140019f3e  test    edi, edi
0x140019f40  jnz     loc_14001A107
0x140019f46  mov     rbx, rax
0x140019f49  test    rbx, rbx
0x140019f4c  jnz     short loc_140019F24
0x140019f4e  mov     r13d, 1
0x140019f54  test    rbx, rbx
0x140019f57  jnz     loc_14001A147
0x140019f5d  xor     ecx, ecx
0x140019f5f  mov     edi, [rbp+3Fh+arg_8]
0x140019f62  lea     rax, [rbp+3Fh+var_98]
0x140019f66  mov     [rsp+40h], rax; __int64
0x140019f6b  mov     r9d, edi
0x140019f6e  mov     rax, [rbp+3Fh+arg_0]
0x140019f72  mov     r8b, r12b
0x140019f75  mov     [rsp+110h+var_D8], rcx; __int64
0x140019f7a  mov     edx, r14d
0x140019f7d  mov     [rsp+110h+var_E0], rcx; __int64
0x140019f82  lea     rcx, [rbp+3Fh+String2]; SourceString
0x140019f86  mov     rax, [rax]
0x140019f89  mov     [rsp+110h+var_E8], rax; __int64
0x140019f8e  mov     rax, [rbp+3Fh+arg_10]
0x140019f92  mov     [rsp+110h+var_F0], rax; __int64
0x140019f97  call    BfpCreatePathTierNode
0x140019f9c  xor     r14d, r14d
0x140019f9f  mov     ebx, eax
0x140019fa1  test    eax, eax
0x140019fa3  js      loc_14001ACE8
0x140019fa9  mov     r15, [rbp+3Fh+var_98]
0x140019fad  cmp     [rbp+3Fh+var_BF], r14b
0x140019fb1  jnz     loc_14001A100
0x140019fb7  test    dil, 2
0x140019fbb  mov     rdi, [rbp+3Fh+arg_10]
0x140019fbf  jnz     loc_14001A39E
0x140019fc5  mov     rax, [rbp+3Fh+arg_0]
0x140019fc9  lea     r8, [rbp+3Fh+var_B8]
0x140019fcd  mov     rcx, [rbp+3Fh+Context]; Context
0x140019fd1  mov     rdx, [rax+8]
0x140019fd5  call    BfpCreateTargetEntry
0x140019fda  mov     ebx, eax
0x140019fdc  test    eax, eax
0x140019fde  js      loc_14001A254
0x140019fe4  mov     r8, [r15+48h]
0x140019fe8  mov     rdx, [rbp+3Fh+var_B8]
0x140019fec  mov     rcx, [rdi]; SourceInstance
0x140019fef  call    BfpInsertTargetEntryIntoMappingInformation
0x140019ff4  xor     edi, edi
0x140019ff6  mov     ebx, eax
0x140019ff8  test    eax, eax
0x140019ffa  js      loc_14001AC84
0x14001a000  mov     [rbp+3Fh+var_B8], rdi
0x14001a004  mov     rbx, [rsi]
0x14001a007  test    [rsi+8], r13b
0x14001a00b  jnz     loc_14001A501
0x14001a011  movzx   edi, byte ptr [rsi+8]
0x14001a015  xor     r8b, r8b
0x14001a018  and     edi, r13d
0x14001a01b  test    rbx, rbx
0x14001a01e  jz      short loc_14001A055
0x14001a020  mov     rdx, rbx
0x14001a023  lea     rcx, [rbp+3Fh+var_80]
0x14001a027  call    BfpRBComparePathNodes
0x14001a02c  test    eax, eax
0x14001a02e  js      loc_14001A129
0x14001a034  mov     rax, [rbx+8]
0x14001a038  test    edi, edi
0x14001a03a  jnz     loc_14001A243
0x14001a040  test    rax, rax
0x14001a043  jz      short loc_14001A052
0x14001a045  mov     rbx, rax
0x14001a048  jmp     short loc_14001A020
0x14001a04a  mov     rax, [rbx]
0x14001a04d  jmp     loc_140019F3E
0x14001a052  mov     r8b, r13b
0x14001a055  xor     edi, edi
0x14001a057  lea     r9, [r15+8]
0x14001a05b  mov     rdx, rbx
0x14001a05e  mov     rcx, rsi
0x14001a061  call    cs:__imp_RtlRbInsertNodeEx
0x14001a068  nop     dword ptr [rax+rax+00h]
0x14001a06d  cmp     [rbp+3Fh+var_60], rdi
0x14001a071  jnz     short loc_14001A07B
0x14001a073  mov     [rbp+3Fh+var_60], r15
0x14001a077  mov     [rbp+3Fh+var_48], rsi
0x14001a07b  cmp     [rbp+3Fh+arg_38], rdi
0x14001a082  jnz     loc_14001A2AA
0x14001a088  cmp     [rbp+3Fh+var_BF], dil
0x14001a08c  jz      short loc_14001A092
  ... truncated ...
```
