# SetEfsData

- ea: `0x1400b9bc4`
- end: `0x1400ba629`
- name: `SetEfsData`
- size: `2661`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation`

## callers

- `0x140115900`

## callees

- `0x14001ebf0`
- `0x1400592a4`
- `0x140059440`
- `0x140059740`
- `0x1400b3838`
- `0x1400b9bc4`
- `0x1400ba630`
- `0x140115410`
- `0x1401197c8`
- `0x140142c60`
- `0x1401451bc`
- `0x140145ddc`
- `0x14014631c`
- `0x140146540`
- `0x140147034`
- `0x1401476a8`
- `0x140148820`
- `0x1402325a4`
- `0x140243fd0`
- `0x140254f9c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400b9e86`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ba019`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ba02f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ba0ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ba138`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b9e86`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ba019`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ba02f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ba0ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ba138`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400b9c78`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400b9cfd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400b9e46`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400b9f27`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400b9fff`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400ba07c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400ba0cc`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400ba120`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400ba3cc`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400ba45b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400ba607`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402bec06`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402bec80`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400b9c78`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400b9cfd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400b9e46`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400b9f27`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400b9fff`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400ba07c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400ba0cc`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400ba120`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400ba3cc`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400ba45b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400ba607`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402bec06`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1402bec80`
- `ksecdd!BCryptDestroyKey` at `0x1400b9e18`
- `ksecdd!BCryptDestroyKey` at `0x1400ba3a1`
- `ksecdd!BCryptDestroyKey` at `0x1400b9e18`
- `ksecdd!BCryptDestroyKey` at `0x1400ba3a1`

## pseudocode

```c
__int64 __fastcall SetEfsData(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        PVOID *a6,
        char a7,
        __int64 a8,
        int *a9,
        _BYTE *a10,
        PVOID *a11)
{
  char v11; // r12
  char v12; // r14
  __int64 v14; // r9
  unsigned int *v15; // rdi
  int EfsData; // ebx
  __int64 KeyBlobBuffer; // rax
  char v18; // al
  __int64 v19; // rcx
  __int64 v20; // r8
  _QWORD *v21; // r12
  __int64 v22; // rax
  _BYTE *v23; // rcx
  PVOID *v24; // r15
  char *v25; // rax
  unsigned int *v26; // r8
  unsigned int *v27; // r14
  unsigned int v28; // eax
  char *v29; // rcx
  __int64 v30; // rax
  _BYTE *v31; // rcx
  PVOID *v32; // r14
  __int64 v33; // rcx
  __int64 v34; // rax
  _BYTE *v35; // rcx
  __int64 v37; // r12
  int v38; // r14d
  PVOID v39; // r14
  __int64 v40; // rax
  _BYTE *v41; // rdx
  __int64 v42; // rax
  _BYTE *v43; // rcx
  __int64 v44; // rax
  _BYTE *v45; // rcx
  __int64 v46; // rax
  _BYTE *v47; // rcx
  __int64 v48; // rcx
  _BYTE *v49; // rdx
  __int64 v50; // rcx
  _WORD *v51; // r14
  __int64 v52; // r8
  int v53; // eax
  PVOID *v54; // r14
  char *v55; // rax
  unsigned int *v56; // r13
  _QWORD *v57; // r12
  unsigned int *v58; // r14
  unsigned int v59; // eax
  char *v60; // rcx
  __int64 v61; // rax
  _BYTE *v62; // rcx
  __int64 v63; // rax
  _BYTE *v64; // rcx
  __int64 v65; // rax
  _DWORD **v66; // r12
  __int64 v67; // rcx
  unsigned int *v68; // r14
  unsigned int v69; // r15d
  __int64 v70; // rcx
  unsigned int v71; // eax
  __int64 v72; // rbx
  unsigned int *v73; // rcx
  __int64 v74; // rax
  _BYTE *v75; // rcx
  __int64 v76; // [rsp+0h] [rbp-D8h] BYREF
  int v77; // [rsp+40h] [rbp-98h] BYREF
  int v78; // [rsp+44h] [rbp-94h] BYREF
  int v79; // [rsp+48h] [rbp-90h] BYREF
  unsigned int *v80; // [rsp+50h] [rbp-88h]
  unsigned int Size; // [rsp+58h] [rbp-80h] BYREF
  unsigned int Size_4; // [rsp+5Ch] [rbp-7Ch]
  __int64 v83; // [rsp+60h] [rbp-78h]
  PVOID P; // [rsp+68h] [rbp-70h] BYREF
  int v85[2]; // [rsp+70h] [rbp-68h] BYREF
  void *Src; // [rsp+78h] [rbp-60h] BYREF
  unsigned int *v87; // [rsp+80h] [rbp-58h]
  _DWORD *v88; // [rsp+88h] [rbp-50h]
  __int64 v89; // [rsp+90h] [rbp-48h]
  __int64 *v90; // [rsp+98h] [rbp-40h]
  unsigned int **v91; // [rsp+E0h] [rbp+8h] BYREF
  int v92; // [rsp+E8h] [rbp+10h]
  int v93; // [rsp+F0h] [rbp+18h]
  __int64 v94; // [rsp+F8h] [rbp+20h]

  v94 = a4;
  v93 = a3;
  v92 = a2;
  v90 = &v76;
  v11 = a3;
  v12 = a2;
  v14 = 0;
  LOBYTE(v91) = 0;
  v15 = 0;
  v80 = 0;
  EfsData = 0;
  *(_QWORD *)v85 = 0;
  Src = 0;
  v79 = 0;
  P = 0;
  Size = 0;
  v77 = 0;
  v83 = 0;
  v78 = *a9;
  if ( (*(_DWORD *)(a1 + 8) & 2) == 0 )
    goto LABEL_33;
  KeyBlobBuffer = GetKeyBlobBufferEx(
                    *(unsigned int *)(*(_QWORD *)(a1 + 24) + 4LL),
                    *(unsigned int *)(*(_QWORD *)(a1 + 24) + 8LL));
  v15 = (unsigned int *)KeyBlobBuffer;
  if ( !KeyBlobBuffer )
    return 3221225626LL;
  v18 = SetKeyTable(KeyBlobBuffer, &v78, *(_QWORD *)(a1 + 24));
  v14 = 0;
  if ( !v18 )
  {
    ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v15 + 9), v15);
    v20 = 3449;
LABEL_5:
    EfsData = -1073741790;
LABEL_6:
    EfspTraceLogAssert(v19, 6, v20, (unsigned int)EfsData);
    return (unsigned int)EfsData;
  }
  v80 = v15;
  if ( *(_DWORD *)(a1 + 4) != 1 )
    goto LABEL_33;
  v21 = *a11;
  if ( !*a11 )
  {
    v11 = v93;
LABEL_33:
    v24 = a6;
    goto LABEL_34;
  }
  EfsData = EfsSameContext(v15, *v21, &v91, 0);
  v22 = *v15 - 87LL;
  v23 = v15 + 20;
  if ( *v15 != 87 )
  {
    do
    {
      *v23++ = 0;
      --v22;
    }
    while ( v22 );
  }
  ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v15 + 9), v15);
  v14 = 0;
  if ( EfsData < 0 )
  {
    v20 = 3463;
    goto LABEL_6;
  }
  if ( !(_BYTE)v91 )
  {
    if ( (*(_DWORD *)(a1 + 8) & 1) != 0 )
    {
      EfsData = -1073741811;
      v20 = 3482;
      goto LABEL_6;
    }
    return 0;
  }
  v15 = 0;
  v80 = 0;
  v24 = a6;
  if ( a6 )
  {
    v25 = (char *)*a6;
    if ( *a6 )
    {
      if ( !v21[1] )
      {
        v26 = (unsigned int *)(v25 + 16);
        v87 = (unsigned int *)(v25 + 16);
        *((_QWORD *)v25 + 5) = *v21 + 80LL;
        *((_DWORD *)v25 + 12) = *(_DWORD *)*v21;
        *((_QWORD *)v25 + 7) = *(_QWORD *)(*v21 + 56LL);
        *((_QWORD *)v25 + 8) = *(_QWORD *)(*v21 + 64LL);
        *((_DWORD *)v25 + 18) = 512;
        *((_DWORD *)v25 + 19) = *(_DWORD *)(*v21 + 4LL);
        *((_DWORD *)v25 + 20) = *(_DWORD *)(*v21 + 24LL);
        *((_QWORD *)v25 + 4) = v25 + 40;
        v91 = (unsigned int **)*v24;
        v27 = *v91;
        if ( *v91 )
        {
          v28 = v27[1];
          if ( (v28 == 26126 || v28 == 26128 || v28 == 536897040 || v28 == 1073767952) && v27[20] == 1 )
          {
            v29 = (char *)*((_QWORD *)v27 + 11);
            if ( (unsigned __int64)(v29 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
              BCryptDestroyKey(v29);
          }
          v30 = *v27 - 87LL;
          v31 = v27 + 20;
          if ( *v27 != 87 )
          {
            do
            {
              *v31++ = 0;
              --v30;
            }
            while ( v30 );
          }
          ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v27 + 9), v27);
          *v91 = 0;
          v26 = v87;
        }
        *(_QWORD *)*v24 = *v21;
        *((_QWORD *)*v24 + 1) = v26;
        v32 = a11;
        ExFreePoolWithTag(*a11, 0x6D736645u);
        *v32 = *v24;
        v14 = 0;
        *v24 = 0;
        v12 = v92;
      }
    }
  }
  v11 = v93;
LABEL_34:
  v33 = *(unsigned int *)(a1 + 8);
  if ( (*(_DWORD *)(a1 + 8) & 1) == 0 && (v33 & 8) == 0 )
    goto LABEL_103;
  if ( (*(_DWORD *)(a1 + 8) & 1) != 0 )
  {
    if ( (*(_DWORD *)(a1 + 12) & 2) == 0 )
    {
      EfspTraceLogAssert(v33, 6, 3548, 3221225473LL);
      v14 = 0;
    }
    if ( (v12 & 1) != 0 )
    {
      if ( v15 )
      {
        v34 = *v15 - 87LL;
        v35 = v15 + 20;
        if ( *v15 != 87 )
        {
          do
          {
            *v35++ = 0;
            --v34;
          }
          while ( v34 );
        }
        ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v15 + 9), v15);
      }
      return 3221225634LL;
    }
  }
  if ( (v11 & 2) == 0 )
  {
    v37 = a5;
LABEL_85:
    v38 = v94;
    goto LABEL_86;
  }
  v37 = a5;
  v38 = v94;
  EfsData = EfsReadEfsData(v94, a5, 0, (unsigned int)&P, (__int64)&Size, (__int64)&v77);
  Size_4 = EfsData;
  if ( EfsData < 0 || v77 != 512 && v77 != 0x10000 )
  {
    if ( v15 )
    {
      v46 = *v15 - 87LL;
      v47 = v15 + 20;
      if ( *v15 != 87 )
      {
        do
        {
          *v47++ = 0;
          --v46;
        }
        while ( v46 );
      }
      ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v15 + 9), v15);
    }
    if ( P )
      ExFreePoolWithTag(P, 0);
    if ( v77 == 2048 )
    {
      return (unsigned int)-1073741670;
    }
    else if ( EfsData >= 0 )
    {
      return (unsigned int)-1073741808;
    }
    return (unsigned int)EfsData;
  }
  if ( v77 == 0x10000 )
  {
    v39 = P;
    EfsData = EfsGetEfsStreamInfo(P, Size, 8);
    if ( EfsData < 0 )
    {
      if ( v15 )
      {
        v40 = *v15 - 87LL;
        v41 = v15 + 20;
        if ( *v15 != 87 )
        {
          do
          {
            *v41++ = 0;
            --v40;
          }
          while ( v40 );
        }
        ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v15 + 9), v15);
      }
      if ( v39 )
        ExFreePoolWithTag(v39, 0);
      return (unsigned int)EfsData;
    }
    ExFreePoolWithTag(v39, 0);
    if ( (_DWORD)v83 == 1 && (v83 & 0x300000000LL) != 0 )
    {
      if ( (*(_DWORD *)(a1 + 8) & 1) != 0 )
      {
        if ( v15 )
        {
          v42 = *v15 - 87LL;
          v43 = v15 + 20;
          if ( *v15 != 87 )
          {
            do
            {
              *v43++ = 0;
              --v42;
            }
            while ( v42 );
          }
          ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v15 + 9), v15);
        }
        v20 = 3667;
        goto LABEL_5;
      }
      if ( (v83 & 0x200000000LL) != 0 )
      {
        *a10 = 1;
        if ( v15 )
        {
          v44 = *v15 - 87LL;
          v45 = v15 + 20;
          if ( *v15 != 87 )
          {
            do
            {
              *v45++ = 0;
              --v44;
            }
            while ( v44 );
          }
          ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v15 + 9), v15);
        }
        return 0;
      }
    }
    goto LABEL_85;
  }
  if ( P )
    ExFreePoolWithTag(P, 0);
LABEL_86:
  if ( (*(_DWORD *)(a1 + 8) & 1) == 0 )
    goto LABEL_103;
  EfsData = EfspGetEfsStreamForWrite(*(_QWORD *)(a1 + 16), **(unsigned int **)(a1 + 16), &Src, &v79);
  if ( EfsData < 0 )
  {
    if ( !v15 )
      return (unsigned int)EfsData;
    v48 = *v15 - 87LL;
    v49 = v15 + 20;
    if ( *v15 != 87 )
    {
      do
      {
        *v49++ = 0;
        --v48;
      }
      while ( v48 );
    }
LABEL_149:
    ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v15 + 9), v15);
    return (unsigned int)EfsData;
  }
  EfsData = NtOfsCreateAttributeEx(v37, v38, (unsigned int)&DestinationString, 256, 1, 1, (__int64)v85);
  Size_4 = EfsData;
  if ( EfsData == -1073741808 )
    EfspTraceLogAssert(v50, 6, 3722, 3221225488LL);
  if ( EfsData >= 0 )
  {
    v51 = *(_WORD **)v85;
    NtOfsSetLength(v37);
    NtOfsPutData(v37, (int)v51, 0, v79, Src);
    if ( !v51 || (unsigned __int16)(*v51 - 1795) > 2u )
      NtOfsFlushAttribute(v37, v51, 0);
    NtOfsMarkFileModified(v37, v94, v52, 0x40000);
    if ( *a11 && (*(_DWORD *)(a1 + 8) & 2) == 0 )
    {
      LOBYTE(a2) = a7;
      EfsCleanup(a11, a2, a8);
    }
    if ( v51 )
      NtfsDecrementCloseCounts(v37, (_DWORD)v51, 0, 1, 0);
LABEL_103:
    if ( !v15 || (*(_DWORD *)(a1 + 8) & 2) == 0 )
      return (unsigned int)EfsData;
    v53 = *(_DWORD *)(a1 + 4);
    v54 = a11;
    if ( v53 != 1 || *a11 )
    {
      if ( v53 != 4 )
        return (unsigned int)EfsData;
      v66 = (_DWORD **)*a11;
      if ( *a11 )
      {
        v68 = *v66;
        v69 = **v66;
        v70 = *v15;
        if ( (unsigned int)v70 > v69 )
        {
          EfsData = -1073740974;
          EfspTraceLogAssert(v70, 6, 3954, 3221226322LL);
        }
        else
        {
          v71 = v15[1];
          if ( (v71 == 26126 || v71 == 26128 || v71 == 536897040 || v71 == 1073767952) && v15[20] == 1 )
          {
            EfsData = EfspCopyAesKeyBlob(*v66);
          }
          else
          {
            v72 = *((_QWORD *)v68 + 9);
            memmove(*v66, v15, *v15);
            *((_QWORD *)v68 + 9) = v72;
            if ( *v15 < v69 )
            {
              *v68 = v69;
              memset((char *)v68 + *v15, 0, v69 - *v15);
            }
            EfsData = 0;
          }
          if ( EfsData >= 0 )
          {
            *((_DWORD *)v66 + 4) = 87119;
            v66[3] = 0;
            v73 = *v66;
            v66[5] = *v66 + 20;
            *((_DWORD *)v66 + 12) = *v73;
            v66[7] = (_DWORD *)*((_QWORD *)v73 + 7);
            v66[8] = (_DWORD *)*((_QWORD *)v73 + 8);
            *((_DWORD *)v66 + 18) = 512;
            *((_DWORD *)v66 + 19) = v73[1];
            *((_DWORD *)v66 + 20) = v73[6];
            v66[4] = v66 + 5;
            v66[1] = v66 + 2;
            *a9 = v78;
          }
        }
        v74 = *v15 - 87LL;
        v75 = v15 + 20;
        if ( *v15 != 87 )
        {
          do
          {
            *v75++ = 0;
            --v74;
          }
          while ( v74 );
        }
        goto LABEL_149;
      }
      v67 = AllocateAndSetContextDataBlock(v15, a2, a3, v14);
      if ( v67 )
      {
        *a9 = v78;
        *v54 = (PVOID)v67;
        return (unsigned int)EfsData;
      }
    }
    else
    {
      if ( v24 )
      {
        v55 = (char *)*v24;
        if ( *v24 )
        {
          v56 = (unsigned int *)(v55 + 16);
          *((_QWORD *)v55 + 5) = v15 + 20;
          *((_DWORD *)v55 + 12) = *v15;
          *((_QWORD *)v55 + 7) = *((_QWORD *)v15 + 7);
          *((_QWORD *)v55 + 8) = *((_QWORD *)v15 + 8);
          *((_DWORD *)v55 + 18) = 512;
          *((_DWORD *)v55 + 19) = v15[1];
          *((_DWORD *)v55 + 20) = v15[6];
          *((_QWORD *)v55 + 4) = v55 + 40;
          v57 = *v24;
          v58 = *(unsigned int **)*v24;
          if ( v58 )
          {
            v59 = v58[1];
            if ( (v59 == 26126 || v59 == 26128 || v59 == 536897040 || v59 == 1073767952) && v58[20] == 1 )
            {
              v60 = (char *)*((_QWORD *)v58 + 11);
              if ( (unsigned __int64)(v60 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
                BCryptDestroyKey(v60);
            }
            v61 = *v58 - 87LL;
            v62 = v58 + 20;
            if ( *v58 != 87 )
            {
              do
              {
                *v62++ = 0;
                --v61;
              }
              while ( v61 );
            }
            ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v58 + 9), v58);
            *v57 = 0;
          }
          *(_QWORD *)*v24 = v15;
          *((_QWORD *)*v24 + 1) = v56;
          *a9 = v78;
          *a11 = *v24;
          *v24 = 0;
          return (unsigned int)EfsData;
        }
      }
      v65 = AllocateAndSetContextDataBlock(v15, a2, a3, v14);
      if ( v65 )
      {
        *a9 = v78;
        *v54 = (PVOID)v65;
        return (unsigned int)EfsData;
      }
    }
    return 3221225626LL;
  }
  if ( v15 )
  {
    v63 = *v15 - 87LL;
    v89 = v63;
    v64 = v15 + 20;
    v88 = v15 + 20;
    while ( v63 )
    {
      *v64++ = 0;
      v88 = v64;
      v89 = --v63;
    }
    ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v15 + 9), v15);
    v80 = 0;
  }
  local_unwind_0(v90, &loc_1400BA485);
  return Size_4;
}

```

## disassembly

```asm
0x1400b9bc4  mov     rax, rsp
0x1400b9bc7  mov     [rax+20h], r9
0x1400b9bcb  mov     [rax+18h], r8d
0x1400b9bcf  mov     [rax+10h], edx
0x1400b9bd2  push    rbx
0x1400b9bd3  push    rsi
0x1400b9bd4  push    rdi
0x1400b9bd5  push    r12
0x1400b9bd7  push    r13
0x1400b9bd9  push    r14
0x1400b9bdb  push    r15
0x1400b9bdd  sub     rsp, 0A0h
0x1400b9be4  mov     [rsp+0D8h+var_40], rsp
0x1400b9bec  mov     r12d, r8d
0x1400b9bef  mov     r14d, edx
0x1400b9bf2  mov     r13, rcx
0x1400b9bf5  xor     r9d, r9d
0x1400b9bf8  mov     [rax+8], r9b
0x1400b9bfc  mov     edi, r9d
0x1400b9bff  mov     [rsp+0D8h+var_88], r9
0x1400b9c04  mov     ebx, r9d
0x1400b9c07  mov     [rax-68h], r9
0x1400b9c0b  mov     [rax-60h], r9
0x1400b9c0f  mov     [rsp+0D8h+var_90], r9d
0x1400b9c14  mov     [rax-70h], r9
0x1400b9c18  mov     [rax-80h], r9d
0x1400b9c1c  mov     [rsp+0D8h+var_98], r9d
0x1400b9c21  mov     [rax-78h], r9
0x1400b9c25  mov     rax, [rsp+0D8h+arg_40]
0x1400b9c2d  mov     eax, [rax]
0x1400b9c2f  mov     [rsp+0D8h+var_94], eax
0x1400b9c33  mov     eax, [rcx+8]
0x1400b9c36  test    al, 2
0x1400b9c38  jz      loc_1400B9EBA
0x1400b9c3e  mov     rcx, [rcx+18h]
0x1400b9c42  mov     edx, [rcx+8]
0x1400b9c45  mov     ecx, [rcx+4]
0x1400b9c48  call    GetKeyBlobBufferEx
0x1400b9c4d  mov     rdi, rax
0x1400b9c50  test    rax, rax
0x1400b9c53  jz      loc_1400BA4D2
0x1400b9c59  mov     r8, [r13+18h]
0x1400b9c5d  lea     rdx, [rsp+0D8h+var_94]
0x1400b9c62  mov     rcx, rax
0x1400b9c65  call    SetKeyTable
0x1400b9c6a  xor     r9d, r9d
0x1400b9c6d  test    al, al
0x1400b9c6f  jnz     short loc_1400B9CA1
0x1400b9c71  mov     rdx, rdi; Entry
0x1400b9c74  mov     rcx, [rdi+48h]; Lookaside
0x1400b9c78  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400b9c7f  nop     dword ptr [rax+rax+00h]
0x1400b9c84  mov     r8d, 0D79h
0x1400b9c8a  mov     ebx, 0C0000022h
0x1400b9c8f  mov     edx, 6
0x1400b9c94  mov     r9d, ebx
0x1400b9c97  call    EfspTraceLogAssert
0x1400b9c9c  jmp     loc_1400BA613
0x1400b9ca1  mov     [rsp+0D8h+var_88], rdi
0x1400b9ca6  mov     esi, 1
0x1400b9cab  cmp     [r13+4], esi
0x1400b9caf  jnz     loc_1400B9EBF
0x1400b9cb5  mov     rcx, [rsp+0D8h+arg_50]
0x1400b9cbd  mov     r12, [rcx]
0x1400b9cc0  test    r12, r12
0x1400b9cc3  jz      loc_1400B9EB0
0x1400b9cc9  lea     r8, [rsp+0D8h+arg_0]
0x1400b9cd1  mov     rdx, [r12]
0x1400b9cd5  mov     rcx, rdi
0x1400b9cd8  call    EfsSameContext
0x1400b9cdd  mov     ebx, eax
0x1400b9cdf  mov     eax, [rdi]
0x1400b9ce1  sub     rax, 57h ; 'W'
0x1400b9ce5  lea     rcx, [rdi+50h]
0x1400b9ce9  jz      short loc_1400B9CF6
0x1400b9ceb  mov     byte ptr [rcx], 0
0x1400b9cee  add     rcx, rsi
0x1400b9cf1  sub     rax, rsi
0x1400b9cf4  jnz     short loc_1400B9CEB
0x1400b9cf6  mov     rdx, rdi; Entry
0x1400b9cf9  mov     rcx, [rdi+48h]; Lookaside
0x1400b9cfd  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400b9d04  nop     dword ptr [rax+rax+00h]
0x1400b9d09  xor     r9d, r9d
0x1400b9d0c  test    ebx, ebx
0x1400b9d0e  jns     short loc_1400B9D1B
0x1400b9d10  mov     r8d, 0D87h
0x1400b9d16  jmp     loc_1400B9C8F
0x1400b9d1b  cmp     byte ptr [rsp+0D8h+arg_0], r9b
0x1400b9d23  jnz     short loc_1400B9D42
0x1400b9d25  mov     eax, [r13+8]
0x1400b9d29  test    sil, al
0x1400b9d2c  jz      loc_1400BA0D8
0x1400b9d32  mov     ebx, 0C000000Dh
0x1400b9d37  mov     r8d, 0D9Ah
0x1400b9d3d  jmp     loc_1400B9C8F
0x1400b9d42  mov     rdi, r9
0x1400b9d45  mov     [rsp+0D8h+var_88], r9
0x1400b9d4a  mov     r15, [rsp+0D8h+arg_28]
0x1400b9d52  test    r15, r15
0x1400b9d55  jz      loc_1400B9EA6
0x1400b9d5b  mov     rax, [r15]
0x1400b9d5e  test    rax, rax
0x1400b9d61  jz      loc_1400B9EA6
0x1400b9d67  cmp     [r12+8], r9
0x1400b9d6c  jnz     loc_1400B9EA6
0x1400b9d72  lea     r8, [rax+10h]
0x1400b9d76  mov     [rsp+0D8h+var_58], r8
0x1400b9d7e  lea     rdx, [r8+18h]
0x1400b9d82  mov     rax, [r12]
0x1400b9d86  add     rax, 50h ; 'P'
0x1400b9d8a  mov     [rdx], rax
0x1400b9d8d  mov     rax, [r12]
0x1400b9d91  mov     ecx, [rax]
0x1400b9d93  mov     [rdx+8], ecx
0x1400b9d96  mov     rax, [r12]
0x1400b9d9a  mov     rcx, [rax+38h]
0x1400b9d9e  mov     [rdx+10h], rcx
0x1400b9da2  mov     rax, [r12]
0x1400b9da6  mov     rcx, [rax+40h]
0x1400b9daa  mov     [rdx+18h], rcx
0x1400b9dae  mov     dword ptr [rdx+20h], 200h
0x1400b9db5  mov     rax, [r12]
0x1400b9db9  mov     ecx, [rax+4]
0x1400b9dbc  mov     [rdx+24h], ecx
0x1400b9dbf  mov     rax, [r12]
0x1400b9dc3  mov     ecx, [rax+18h]
0x1400b9dc6  mov     [rdx+28h], ecx
0x1400b9dc9  mov     [r8+10h], rdx
0x1400b9dcd  mov     rax, [r15]
0x1400b9dd0  mov     [rsp+0D8h+arg_0], rax
0x1400b9dd8  mov     r14, [rax]
0x1400b9ddb  test    r14, r14
0x1400b9dde  jz      loc_1400B9E65
0x1400b9de4  mov     eax, [r14+4]
0x1400b9de8  cmp     eax, 660Eh
0x1400b9ded  jz      short loc_1400B9E04
0x1400b9def  cmp     eax, 6610h
0x1400b9df4  jz      short loc_1400B9E04
0x1400b9df6  cmp     eax, 20006610h
0x1400b9dfb  jz      short loc_1400B9E04
0x1400b9dfd  cmp     eax, 40006610h
0x1400b9e02  jnz     short loc_1400B9E27
0x1400b9e04  cmp     [r14+50h], esi
0x1400b9e08  jnz     short loc_1400B9E27
0x1400b9e0a  mov     rcx, [r14+58h]; hKey
0x1400b9e0e  lea     rax, [rcx-1]
0x1400b9e12  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400b9e16  ja      short loc_1400B9E27
0x1400b9e18  call    cs:__imp_BCryptDestroyKey
0x1400b9e1f  nop     dword ptr [rax+rax+00h]
0x1400b9e24  xor     r9d, r9d
0x1400b9e27  mov     eax, [r14]
0x1400b9e2a  sub     rax, 57h ; 'W'
0x1400b9e2e  lea     rcx, [r14+50h]
0x1400b9e32  jz      short loc_1400B9E3F
0x1400b9e34  mov     [rcx], r9b
0x1400b9e37  add     rcx, rsi
0x1400b9e3a  sub     rax, rsi
0x1400b9e3d  jnz     short loc_1400B9E34
0x1400b9e3f  mov     rdx, r14; Entry
0x1400b9e42  mov     rcx, [r14+48h]; Lookaside
0x1400b9e46  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400b9e4d  nop     dword ptr [rax+rax+00h]
0x1400b9e52  mov     rax, [rsp+0D8h+arg_0]
0x1400b9e5a  mov     [rax], rdi
0x1400b9e5d  mov     r8, [rsp+0D8h+var_58]
0x1400b9e65  mov     rcx, [r15]
0x1400b9e68  mov     rax, [r12]
0x1400b9e6c  mov     [rcx], rax
0x1400b9e6f  mov     rax, [r15]
0x1400b9e72  mov     [rax+8], r8
0x1400b9e76  mov     edx, 6D736645h; Tag
0x1400b9e7b  mov     r14, [rsp+0D8h+arg_50]
0x1400b9e83  mov     rcx, [r14]; P
0x1400b9e86  call    cs:__imp_ExFreePoolWithTag
0x1400b9e8d  nop     dword ptr [rax+rax+00h]
0x1400b9e92  mov     rax, [r15]
0x1400b9e95  mov     [r14], rax
0x1400b9e98  xor     r9d, r9d
0x1400b9e9b  mov     [r15], r9
0x1400b9e9e  mov     r14d, [rsp+0D8h+arg_8]
0x1400b9ea6  mov     r12d, [rsp+0D8h+arg_10]
0x1400b9eae  jmp     short loc_1400B9EC7
0x1400b9eb0  mov     r12d, [rsp+0D8h+arg_10]
0x1400b9eb8  jmp     short loc_1400B9EBF
0x1400b9eba  mov     esi, 1
0x1400b9ebf  mov     r15, [rsp+0D8h+arg_28]
0x1400b9ec7  mov     ecx, [r13+8]
0x1400b9ecb  mov     eax, ecx
0x1400b9ecd  and     eax, esi
0x1400b9ecf  jnz     short loc_1400B9EDA
0x1400b9ed1  test    cl, 8
0x1400b9ed4  jz      loc_1400BA2DE
0x1400b9eda  test    eax, eax
0x1400b9edc  jz      short loc_1400B9F3D
0x1400b9ede  mov     eax, [r13+0Ch]
0x1400b9ee2  test    al, 2
0x1400b9ee4  jnz     short loc_1400B9EFF
0x1400b9ee6  mov     edx, 6
0x1400b9eeb  mov     r9d, 0C0000001h
0x1400b9ef1  mov     r8d, 0DDCh
0x1400b9ef7  call    EfspTraceLogAssert
0x1400b9efc  xor     r9d, r9d
0x1400b9eff  test    sil, r14b
0x1400b9f02  jz      short loc_1400B9F3D
0x1400b9f04  test    rdi, rdi
0x1400b9f07  jz      short loc_1400B9F33
0x1400b9f09  mov     eax, [rdi]
0x1400b9f0b  sub     rax, 57h ; 'W'
0x1400b9f0f  lea     rcx, [rdi+50h]
0x1400b9f13  jz      short loc_1400B9F20
0x1400b9f15  mov     [rcx], r9b
0x1400b9f18  add     rcx, rsi
0x1400b9f1b  sub     rax, rsi
0x1400b9f1e  jnz     short loc_1400B9F15
0x1400b9f20  mov     rdx, rdi; Entry
0x1400b9f23  mov     rcx, [rdi+48h]; Lookaside
0x1400b9f27  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400b9f2e  nop     dword ptr [rax+rax+00h]
0x1400b9f33  mov     eax, 0C00000A2h
0x1400b9f38  jmp     loc_1400BA615
0x1400b9f3d  test    r12b, 2
0x1400b9f41  jz      loc_1400BA169
0x1400b9f47  lea     rax, [rsp+0D8h+var_98]
0x1400b9f4c  mov     [rsp+0D8h+var_B0], rax
0x1400b9f51  lea     rax, [rsp+0D8h+Size]
0x1400b9f56  mov     [rsp+0D8h+Src], rax
0x1400b9f5b  lea     r9, [rsp+0D8h+P]
0x1400b9f60  xor     r8d, r8d
0x1400b9f63  mov     r12, [rsp+0D8h+arg_20]
0x1400b9f6b  mov     rdx, r12
0x1400b9f6e  mov     r14, [rsp+0D8h+arg_18]
0x1400b9f76  mov     rcx, r14
0x1400b9f79  call    EfsReadEfsData
0x1400b9f7e  mov     ebx, eax
0x1400b9f80  mov     dword ptr [rsp+0D8h+Size+4], eax
0x1400b9f84  test    ebx, ebx
0x1400b9f86  js      loc_1400BA0FD
0x1400b9f8c  cmp     [rsp+0D8h+var_98], 200h
0x1400b9f94  jz      short loc_1400B9FA4
0x1400b9f96  cmp     [rsp+0D8h+var_98], 10000h
0x1400b9f9e  jnz     loc_1400BA0FD
0x1400b9fa4  cmp     [rsp+0D8h+var_98], 10000h
0x1400b9fac  jnz     loc_1400BA0DF
0x1400b9fb2  mov     dword ptr [rsp+0D8h+Src], 8; int
0x1400b9fba  lea     r9, [rsp+0D8h+var_78]
0x1400b9fbf  mov     r8d, 0Bh
0x1400b9fc5  mov     edx, dword ptr [rsp+0D8h+Size]; Size
0x1400b9fc9  mov     r14, [rsp+0D8h+P]
0x1400b9fce  mov     rcx, r14; Src
0x1400b9fd1  call    EfsGetEfsStreamInfo
0x1400b9fd6  mov     ebx, eax
0x1400b9fd8  test    eax, eax
0x1400b9fda  jns     short loc_1400BA02A
0x1400b9fdc  test    rdi, rdi
0x1400b9fdf  jz      short loc_1400BA00B
0x1400b9fe1  mov     eax, [rdi]
0x1400b9fe3  sub     rax, 57h ; 'W'
0x1400b9fe7  lea     rdx, [rdi+50h]
0x1400b9feb  jz      short loc_1400B9FF8
0x1400b9fed  mov     byte ptr [rdx], 0
0x1400b9ff0  add     rdx, rsi
0x1400b9ff3  sub     rax, rsi
0x1400b9ff6  jnz     short loc_1400B9FED
0x1400b9ff8  mov     rdx, rdi; Entry
0x1400b9ffb  mov     rcx, [rdi+48h]; Lookaside
0x1400b9fff  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400ba006  nop     dword ptr [rax+rax+00h]
0x1400ba00b  test    r14, r14
0x1400ba00e  jz      loc_1400BA613
0x1400ba014  xor     edx, edx; Tag
0x1400ba016  mov     rcx, r14; P
0x1400ba019  call    cs:__imp_ExFreePoolWithTag
0x1400ba020  nop     dword ptr [rax+rax+00h]
0x1400ba025  jmp     loc_1400BA613
0x1400ba02a  xor     edx, edx; Tag
0x1400ba02c  mov     rcx, r14; P
0x1400ba02f  call    cs:__imp_ExFreePoolWithTag
0x1400ba036  nop     dword ptr [rax+rax+00h]
0x1400ba03b  cmp     [rsp+0D8h+var_78], esi
0x1400ba03f  jnz     loc_1400BA171
0x1400ba045  test    [rsp+0D8h+var_74], 3
0x1400ba04a  jz      loc_1400BA171
0x1400ba050  mov     eax, [r13+8]
0x1400ba054  test    sil, al
0x1400ba057  jz      short loc_1400BA093
0x1400ba059  test    rdi, rdi
0x1400ba05c  jz      short loc_1400BA088
0x1400ba05e  mov     eax, [rdi]
0x1400ba060  sub     rax, 57h ; 'W'
0x1400ba064  lea     rcx, [rdi+50h]
0x1400ba068  jz      short loc_1400BA075
0x1400ba06a  mov     byte ptr [rcx], 0
0x1400ba06d  add     rcx, rsi
0x1400ba070  sub     rax, rsi
0x1400ba073  jnz     short loc_1400BA06A
0x1400ba075  mov     rdx, rdi; Entry
0x1400ba078  mov     rcx, [rdi+48h]; Lookaside
0x1400ba07c  call    cs:__imp_ExFreeToNPagedLookasideList
  ... truncated ...
```
