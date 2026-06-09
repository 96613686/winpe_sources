# BfGetMappingList

- ea: `0x140017f00`
- end: `0x140018b52`
- name: `BfGetMappingList`
- size: `3154`
- prototype: `__int64 __usercall@<rax>(PFLT_CALLBACK_DATA CallbackData@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140024e50`

## callees

- `0x140001010`
- `0x140001348`
- `0x140017bb8`
- `0x140017bf0`
- `0x140017f00`
- `0x140018b60`
- `0x140019b40`
- `0x140020d60`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x140018384`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140018384`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400183e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400183e7`
- `FLTMGR!FltGetFileNameInformation` at `0x140017fd5`
- `FLTMGR!FltGetFileNameInformation` at `0x140017fd5`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001841e`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001841e`
- `FLTMGR!FltAcquireResourceShared` at `0x14001806d`
- `FLTMGR!FltAcquireResourceShared` at `0x14001814c`
- `FLTMGR!FltAcquireResourceShared` at `0x140018250`
- `FLTMGR!FltAcquireResourceShared` at `0x14001806d`
- `FLTMGR!FltAcquireResourceShared` at `0x14001814c`
- `FLTMGR!FltAcquireResourceShared` at `0x140018250`
- `FLTMGR!FltReleaseContext` at `0x140018409`
- `FLTMGR!FltReleaseContext` at `0x140018409`
- `FLTMGR!FltReleaseResource` at `0x1400180f1`
- `FLTMGR!FltReleaseResource` at `0x140018201`
- `FLTMGR!FltReleaseResource` at `0x140018302`
- `FLTMGR!FltReleaseResource` at `0x1400180f1`
- `FLTMGR!FltReleaseResource` at `0x140018201`
- `FLTMGR!FltReleaseResource` at `0x140018302`
- `FLTMGR!FltGetInstanceContext` at `0x140017f76`
- `FLTMGR!FltGetInstanceContext` at `0x140017f76`

## pseudocode

```c
__int64 __fastcall BfGetMappingList(
        PFLT_CALLBACK_DATA CallbackData,
        __int64 a2,
        __int64 a3,
        const UNICODE_STRING **a4,
        _BYTE *a5)
{
  __int64 v5; // r14
  struct _FLT_INSTANCE *v7; // rcx
  __int64 v9; // r15
  NTSTATUS InstanceContext; // eax
  int v11; // edx
  int MappingContexts; // eax
  NTSTATUS v13; // ebx
  int v14; // eax
  _QWORD *v15; // rbx
  struct _ERESOURCE *v16; // r13
  __int64 v17; // rdi
  struct _ERESOURCE *v18; // rcx
  _QWORD *v19; // rcx
  __int64 v20; // rbx
  __int64 v21; // rax
  int v22; // edi
  int v23; // eax
  __int64 v24; // rax
  _QWORD *v25; // rbx
  struct _ERESOURCE *v26; // r13
  __int64 v27; // rdi
  struct _ERESOURCE *v28; // rcx
  _QWORD *v29; // rcx
  __int64 v30; // rbx
  __int64 v31; // rax
  int v32; // edi
  int v33; // eax
  __int64 v34; // rax
  __int64 **v35; // r13
  __int64 v36; // rbx
  __int64 **v37; // rcx
  __int64 v38; // rdi
  __int64 v39; // rbx
  int v40; // edi
  int v41; // eax
  __int64 v42; // rax
  UNICODE_STRING *v43; // rdi
  PVOID *v44; // rax
  const UNICODE_STRING *i; // rbx
  LONG v46; // eax
  int v48; // r9d
  __int64 *v49; // rcx
  unsigned __int64 v50; // r15
  __int64 *v51; // rcx
  unsigned __int64 v52; // r15
  __int64 *v53; // rcx
  unsigned __int64 v54; // r15
  char v55; // r12
  __int64 v56; // rdx
  unsigned __int16 v57; // r9
  unsigned __int16 v58; // dx
  char v59; // r14
  __int64 v60; // r9
  __int64 v61; // rbx
  _BYTE *v62; // r15
  _BYTE *v63; // rdi
  __int64 v64; // rcx
  unsigned __int64 v65; // rcx
  char v66; // dl
  unsigned __int64 v67; // rax
  __int64 v68; // rax
  char v69; // r12
  __int64 v70; // rdx
  unsigned __int16 v71; // r8
  unsigned __int16 v72; // dx
  char v73; // r14
  __int64 v74; // r8
  __int64 v75; // rbx
  _BYTE *v76; // rdi
  _BYTE *v77; // r14
  __int64 v78; // rcx
  unsigned __int64 v79; // rax
  char v80; // dl
  __int64 v81; // rcx
  char v82; // r12
  __int64 v83; // rdx
  unsigned __int16 v84; // r8
  unsigned __int16 v85; // dx
  char v86; // r14
  __int64 v87; // r8
  __int64 v88; // rbx
  _BYTE *v89; // rdi
  _BYTE *v90; // r14
  __int64 v91; // rcx
  unsigned __int64 v92; // rax
  char v93; // dl
  __int64 v94; // rcx
  WCHAR *v95; // rax
  char v96; // [rsp+30h] [rbp-91h]
  NTSTATUS v97; // [rsp+38h] [rbp-89h]
  _BYTE v98[4]; // [rsp+40h] [rbp-81h] BYREF
  NTSTATUS v99; // [rsp+44h] [rbp-7Dh]
  PVOID P[2]; // [rsp+48h] [rbp-79h] BYREF
  __int128 v101; // [rsp+58h] [rbp-69h] BYREF
  __int128 v102; // [rsp+68h] [rbp-59h] BYREF
  __int128 v103; // [rsp+78h] [rbp-49h] BYREF
  _QWORD *v104; // [rsp+88h] [rbp-39h] BYREF
  PVOID Entry; // [rsp+90h] [rbp-31h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+98h] [rbp-29h] BYREF
  __int128 v107; // [rsp+A0h] [rbp-21h] BYREF
  PFLT_CONTEXT Context; // [rsp+B0h] [rbp-11h] BYREF
  __int64 v109; // [rsp+B8h] [rbp-9h] BYREF
  __int64 v110; // [rsp+C0h] [rbp-1h]
  _QWORD **v111; // [rsp+C8h] [rbp+7h]
  __int64 v112; // [rsp+D0h] [rbp+Fh]
  _BYTE *v113; // [rsp+D8h] [rbp+17h]

  v5 = a2;
  Context = 0;
  *(_QWORD *)&v103 = 0;
  Entry = &v104;
  *(_QWORD *)&v102 = 0;
  v7 = *(struct _FLT_INSTANCE **)(a2 + 24);
  *(_QWORD *)&v101 = 0;
  FileNameInformation = 0;
  v9 = a3;
  v98[0] = 0;
  *(_OWORD *)P = 0;
  v104 = &v104;
  InstanceContext = FltGetInstanceContext(v7, &Context);
  if ( InstanceContext < 0 )
  {
    v13 = InstanceContext;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_65;
    v97 = InstanceContext;
    v48 = 15;
    v96 = -96;
    goto LABEL_75;
  }
  MappingContexts = BfGetMappingContexts(
                      *(_QWORD *)(v5 + 32),
                      (__int64)Context,
                      (__int64)CallbackData,
                      &v101,
                      &v102,
                      &v103);
  if ( MappingContexts < 0 )
  {
    v13 = MappingContexts;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = 4;
      WPP_RECORDER_SF_sDd(
        WPP_GLOBAL_Control->DeviceExtension,
        v11,
        12,
        16,
        (__int64)WPP_e12ce5656ffd33908c95ca7de20f6d85_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\dirctrl.c",
        168,
        MappingContexts);
    }
  }
  else
  {
    FileNameInformation = 0;
    if ( !CallbackData )
      goto LABEL_72;
    v13 = FltGetFileNameInformation(CallbackData, 0x1000102u, &FileNameInformation);
    if ( v13 < 0 )
    {
LABEL_73:
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_65;
      v97 = v13;
      v48 = 17;
      v96 = -74;
LABEL_75:
      LOBYTE(v11) = 2;
      WPP_RECORDER_SF_sDd(
        WPP_GLOBAL_Control->DeviceExtension,
        v11,
        12,
        v48,
        (__int64)WPP_e12ce5656ffd33908c95ca7de20f6d85_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\dirctrl.c",
        v96,
        v97);
      goto LABEL_65;
    }
    if ( !FileNameInformation->Name.Length && FileNameInformation->Volume.Length )
    {
LABEL_72:
      v13 = -1073741811;
      goto LABEL_73;
    }
    v14 = BfFormatPathFromFileNameInfo(FileNameInformation, 0, P);
    v99 = v14;
    v13 = v14;
    if ( v14 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_65;
      v97 = v14;
      v48 = 18;
      v96 = -66;
      goto LABEL_75;
    }
    v15 = (_QWORD *)v101;
    if ( (_QWORD)v101 )
    {
      v16 = (struct _ERESOURCE *)(v101 + 16);
      v17 = *(_QWORD *)(v5 + 24);
      v109 = *(_QWORD *)(v5 + 32);
      v110 = v17;
      v111 = &v104;
      v18 = (struct _ERESOURCE *)(v101 + 16);
      v112 = v9;
      v113 = v98;
      v101 = 0;
      v107 = 0;
      FltAcquireResourceShared(v18);
      v19 = (_QWORD *)*v15;
      if ( (_QWORD *)*v15 != v15 )
      {
        while ( *(_QWORD *)v19[2] != v17 )
        {
          v19 = (_QWORD *)*v19;
          if ( v19 == v15 )
            goto LABEL_19;
        }
        v52 = v19[3];
        v69 = 1;
        while ( 2 )
        {
          if ( (_WORD)v101 )
          {
            v71 = LOWORD(P[0]) >> 1;
            v72 = (__int64)(*((_QWORD *)&v101 + 1) - (unsigned __int64)P[1]) >> 1;
            if ( v72 >= (unsigned __int16)(LOWORD(P[0]) >> 1) )
            {
LABEL_136:
              if ( v72 == v71 )
              {
                LODWORD(v101) = 0;
                *((_QWORD *)&v101 + 1) = 0;
                goto LABEL_146;
              }
            }
            else
            {
              while ( *((_WORD *)P[1] + v72) != 92 )
              {
                if ( ++v72 >= v71 )
                  goto LABEL_136;
              }
            }
            LOWORD(v70) = v72 + 1;
          }
          else
          {
            v70 = *(_WORD *)P[1] == 92;
            *((_QWORD *)&v101 + 1) = (char *)P[1] + 2 * v70;
          }
          v73 = 0;
          v74 = (unsigned __int16)v70;
          while ( (unsigned __int16)v70 < (unsigned __int16)(LOWORD(P[0]) >> 1) )
          {
            if ( *((_WORD *)P[1] + (unsigned __int16)v70) == 92 )
            {
              v73 = 1;
              break;
            }
            LOWORD(v70) = v70 + 1;
          }
          *((_QWORD *)&v101 + 1) = (char *)P[1] + 2 * v74;
          WORD1(v101) = 2 * (v70 - v74);
          LOWORD(v101) = WORD1(v101);
          if ( !WORD1(v101) )
            goto LABEL_144;
          v20 = *(_QWORD *)v52;
          *(_QWORD *)&v107 = &v101;
          v21 = *(_QWORD *)(v52 + 8);
          BYTE8(v107) = 1;
          if ( (v21 & 1) != 0 )
          {
            if ( !v20 )
              goto LABEL_19;
            v20 ^= v52;
          }
          v22 = v21 & 1;
          if ( !v20 )
            goto LABEL_19;
          while ( 1 )
          {
            v23 = BfpRBComparePathNodes((__int64)&v107, v20);
            if ( v23 >= 0 )
              break;
            v24 = *(_QWORD *)v20;
            if ( !v22 )
              goto LABEL_17;
LABEL_26:
            if ( v24 )
            {
              v20 ^= v24;
              goto LABEL_18;
            }
LABEL_17:
            v20 = v24;
LABEL_18:
            if ( !v20 )
              goto LABEL_19;
          }
          if ( v23 > 0 )
          {
            v24 = *(_QWORD *)(v20 + 8);
            if ( !v22 )
              goto LABEL_17;
            goto LABEL_26;
          }
          if ( (*(_DWORD *)(v20 - 8) & 1) != 0 && (*(_DWORD *)(*(_QWORD *)(v20 + 64) + 8LL) & 2) != 0 )
            *a5 = 1;
          if ( (*(_DWORD *)(v20 - 8) & 4) == 0 && !(unsigned __int8)BfpPathTreeEmpty(*(_QWORD *)(v20 + 72)) )
          {
            v52 = (unsigned __int64)v51;
            if ( !v73 )
              goto LABEL_146;
            continue;
          }
          break;
        }
        v69 = 0;
LABEL_144:
        if ( !v73 && v69 )
        {
LABEL_146:
          v75 = *(_QWORD *)v52;
          if ( *(_QWORD *)v52 )
          {
            v76 = (_BYTE *)(v52 + 8);
            v77 = (_BYTE *)(v52 + 8);
            while ( (int)BfWalkMappingTree(v75, (__int64)&v109) >= 0 )
            {
              v78 = *(_QWORD *)v75;
              if ( *(_QWORD *)v75 )
              {
                if ( (*v77 & 1) == 0 )
                  goto LABEL_160;
                v75 ^= v78;
                v76 = (_BYTE *)(v52 + 8);
              }
              else
              {
                v78 = *(_QWORD *)(v75 + 8);
                if ( v78 )
                {
                  if ( (*v77 & 1) != 0 )
                  {
                    v75 ^= v78;
                    v76 = (_BYTE *)(v52 + 8);
                  }
                  else
                  {
LABEL_160:
                    v75 = v78;
                    v76 = (_BYTE *)(v52 + 8);
                  }
                }
                else
                {
                  v79 = v75;
                  v80 = *v76 & 1;
                  while ( 1 )
                  {
                    v79 = *(_QWORD *)(v79 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
                    if ( v80 )
                    {
                      if ( !v79 )
                        goto LABEL_19;
                      v79 ^= v75;
                    }
                    if ( !v79 )
                      goto LABEL_19;
                    v81 = *(_QWORD *)(v79 + 8);
                    if ( v80 )
                    {
                      if ( !v81 )
                        goto LABEL_158;
                      v81 ^= v79;
                    }
                    if ( v81 && v81 != v75 )
                      break;
LABEL_158:
                    v75 = v79;
                  }
                  v75 = v81;
                }
              }
            }
          }
        }
      }
LABEL_19:
      FltReleaseResource(v16);
      v5 = a2;
      v9 = a3;
    }
    v25 = (_QWORD *)v102;
    if ( (_QWORD)v102 )
    {
      v26 = (struct _ERESOURCE *)(v102 + 16);
      v27 = *(_QWORD *)(v5 + 24);
      v109 = *(_QWORD *)(v5 + 32);
      v110 = v27;
      v111 = &v104;
      v28 = (struct _ERESOURCE *)(v102 + 16);
      v112 = v9;
      v113 = v98;
      v102 = 0;
      v107 = 0;
      FltAcquireResourceShared(v28);
      v29 = (_QWORD *)*v25;
      if ( (_QWORD *)*v25 != v25 )
      {
        while ( *(_QWORD *)v29[2] != v27 )
        {
          v29 = (_QWORD *)*v29;
          if ( v29 == v25 )
            goto LABEL_35;
        }
        v54 = v29[3];
        v82 = 1;
        while ( 2 )
        {
          if ( (_WORD)v102 )
          {
            v84 = LOWORD(P[0]) >> 1;
            v85 = (__int64)(*((_QWORD *)&v102 + 1) - (unsigned __int64)P[1]) >> 1;
            if ( v85 >= (unsigned __int16)(LOWORD(P[0]) >> 1) )
            {
LABEL_173:
              if ( v85 == v84 )
              {
                LODWORD(v102) = 0;
                *((_QWORD *)&v102 + 1) = 0;
                goto LABEL_183;
              }
            }
            else
            {
              while ( *((_WORD *)P[1] + v85) != 92 )
              {
                if ( ++v85 >= v84 )
                  goto LABEL_173;
              }
            }
            LOWORD(v83) = v85 + 1;
          }
          else
          {
            v83 = *(_WORD *)P[1] == 92;
            *((_QWORD *)&v102 + 1) = (char *)P[1] + 2 * v83;
          }
          v86 = 0;
          v87 = (unsigned __int16)v83;
          while ( (unsigned __int16)v83 < (unsigned __int16)(LOWORD(P[0]) >> 1) )
          {
            if ( *((_WORD *)P[1] + (unsigned __int16)v83) == 92 )
            {
              v86 = 1;
              break;
            }
            LOWORD(v83) = v83 + 1;
          }
          *((_QWORD *)&v102 + 1) = (char *)P[1] + 2 * v87;
          WORD1(v102) = 2 * (v83 - v87);
          LOWORD(v102) = WORD1(v102);
          if ( !WORD1(v102) )
            goto LABEL_181;
          v30 = *(_QWORD *)v54;
          *(_QWORD *)&v107 = &v102;
          v31 = *(_QWORD *)(v54 + 8);
          BYTE8(v107) = 1;
          if ( (v31 & 1) != 0 )
          {
            if ( !v30 )
              goto LABEL_35;
            v30 ^= v54;
          }
          v32 = v31 & 1;
          if ( !v30 )
            goto LABEL_35;
          while ( 1 )
          {
            v33 = BfpRBComparePathNodes((__int64)&v107, v30);
            if ( v33 >= 0 )
              break;
            v34 = *(_QWORD *)v30;
            if ( !v32 )
              goto LABEL_33;
LABEL_41:
            if ( v34 )
            {
              v30 ^= v34;
              goto LABEL_34;
            }
LABEL_33:
            v30 = v34;
LABEL_34:
            if ( !v30 )
              goto LABEL_35;
          }
          if ( v33 > 0 )
          {
            v34 = *(_QWORD *)(v30 + 8);
            if ( !v32 )
              goto LABEL_33;
            goto LABEL_41;
          }
          if ( (*(_DWORD *)(v30 - 8) & 1) != 0 && (*(_DWORD *)(*(_QWORD *)(v30 + 64) + 8LL) & 2) != 0 )
            *a5 = 1;
          if ( (*(_DWORD *)(v30 - 8) & 4) == 0 && !(unsigned __int8)BfpPathTreeEmpty(*(_QWORD *)(v30 + 72)) )
          {
            v54 = (unsigned __int64)v53;
            if ( !v86 )
              goto LABEL_183;
            continue;
          }
          break;
        }
        v82 = 0;
LABEL_181:
        if ( !v86 && v82 )
        {
LABEL_183:
          v88 = *(_QWORD *)v54;
          if ( *(_QWORD *)v54 )
          {
            v89 = (_BYTE *)(v54 + 8);
            v90 = (_BYTE *)(v54 + 8);
            while ( (int)BfWalkMappingTree(v88, (__int64)&v109) >= 0 )
            {
              v91 = *(_QWORD *)v88;
              if ( *(_QWORD *)v88 )
              {
                if ( (*v90 & 1) == 0 )
                  goto LABEL_197;
                v88 ^= v91;
                v89 = (_BYTE *)(v54 + 8);
              }
              else
              {
                v91 = *(_QWORD *)(v88 + 8);
                if ( v91 )
                {
                  if ( (*v90 & 1) != 0 )
                  {
                    v88 ^= v91;
                    v89 = (_BYTE *)(v54 + 8);
                  }
                  else
                  {
LABEL_197:
                    v88 = v91;
                    v89 = (_BYTE *)(v54 + 8);
                  }
                }
                else
                {
                  v92 = v88;
                  v93 = *v89 & 1;
                  while ( 1 )
                  {
                    v92 = *(_QWORD *)(v92 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
                    if ( v93 )
                    {
                      if ( !v92 )
                        goto LABEL_35;
                      v92 ^= v88;
                    }
                    if ( !v92 )
                      goto LABEL_35;
                    v94 = *(_QWORD *)(v92 + 8);
                    if ( v93 )
                    {
                      if ( !v94 )
                        goto LABEL_195;
                      v94 ^= v92;
                    }
                    if ( v94 && v94 != v88 )
                      break;
LABEL_195:
                    v88 = v92;
                  }
                  v88 = v94;
                }
              }
            }
          }
        }
      }
LABEL_35:
      FltReleaseResource(v26);
    }
    v35 = (__int64 **)v103;
    v103 = 0;
    v36 = *(_QWORD *)(a2 + 24);
    v109 = *(_QWORD *)(a2 + 32);
    v111 = &v104;
    v112 = a3;
    v113 = v98;
    v107 = 0;
    v110 = v36;
    FltAcquireResourceShared((PERESOURCE)(v35 + 2));
    v37 = (__int64 **)*v35;
    if ( *v35 != (__int64 *)v35 )
    {
      while ( *v37[2] != v36 )
      {
        v37 = (__int64 **)*v37;
        if ( v37 == v35 )
          goto LABEL_50;
      }
      v50 = (unsigned __int64)v37[3];
      v55 = 1;
      while ( 2 )
      {
        if ( (_WORD)v103 )
        {
          v57 = LOWORD(P[0]) >> 1;
          v58 = (__int64)(*((_QWORD *)&v103 + 1) - (unsigned __int64)P[1]) >> 1;
          if ( v58 >= (unsigned __int16)(LOWORD(P[0]) >> 1) )
          {
LABEL_98:
            if ( v58 == v57 )
            {
              LODWORD(v103) = 0;
              *((_QWORD *)&v103 + 1) = 0;
              goto LABEL_108;
            }
          }
          else
          {
            while ( *((_WORD *)P[1] + v58) != 92 )
            {
              if ( ++v58 >= v57 )
                goto LABEL_98;
            }
          }
          LOWORD(v56) = v58 + 1;
        }
        else
        {
          v56 = *(_WORD *)P[1] == 92;
          *((_QWORD *)&v103 + 1) = (char *)P[1] + 2 * v56;
        }
        v59 = 0;
        v60 = (unsigned __int16)v56;
        while ( (unsigned __int16)v56 < (unsigned __int16)(LOWORD(P[0]) >> 1) )
        {
          if ( *((_WORD *)P[1] + (unsigned __int16)v56) == 92 )
          {
            v59 = 1;
            break;
          }
          LOWORD(v56) = v56 + 1;
        }
        *((_QWORD *)&v103 + 1) = (char *)P[1] + 2 * v60;
        WORD1(v103) = 2 * (v56 - v60);
        LOWORD(v103) = WORD1(v103);
        if ( !WORD1(v103) )
          goto LABEL_106;
        v38 = *(_QWORD *)(v50 + 8);
        v39 = *(_QWORD *)v50;
        *(_QWORD *)&v107 = &v103;
        BYTE8(v107) = 1;
        if ( (v38 & 1) != 0 )
        {
          if ( !v39 )
            goto LABEL_50;
          v39 ^= v50;
        }
        v40 = v38 & 1;
        if ( !v39 )
          goto LABEL_50;
        while ( 1 )
        {
          v41 = BfpRBComparePathNodes((__int64)&v107, v39);
          if ( v41 >= 0 )
            break;
          v42 = *(_QWORD *)v39;
          if ( !v40 )
            goto LABEL_48;
LABEL_62:
          if ( v42 )
          {
            v39 ^= v42;
            goto LABEL_49;
          }
LABEL_48:
          v39 = v42;
LABEL_49:
          if ( !v39 )
            goto LABEL_50;
        }
        if ( v41 > 0 )
        {
          v42 = *(_QWORD *)(v39 + 8);
          if ( !v40 )
            goto LABEL_48;
          goto LABEL_62;
        }
        if ( (*(_DWORD *)(v39 - 8) & 1) != 0 && (*(_DWORD *)(*(_QWORD *)(v39 + 64) + 8LL) & 2) != 0 )
          *a5 = 1;
        if ( (*(_DWORD *)(v39 - 8) & 4) == 0 && !(unsigned __int8)BfpPathTreeEmpty(*(_QWORD *)(v39 + 72)) )
        {
          v50 = (unsigned __int64)v49;
          if ( !v59 )
            goto LABEL_108;
          continue;
        }
        break;
      }
      v55 = 0;
LABEL_106:
      if ( !v59 && v55 )
      {
LABEL_108:
        v61 = *(_QWORD *)v50;
        if ( *(_QWORD *)v50 )
        {
          v62 = (_BYTE *)(v50 + 8);
          v63 = v62;
          while ( (int)BfWalkMappingTree(v61, (__int64)&v109) >= 0 )
          {
            v64 = *(_QWORD *)v61;
            if ( *(_QWORD *)v61 )
            {
              if ( (*v63 & 1) == 0 )
                goto LABEL_123;
              v61 ^= v64;
              v62 = v63;
            }
            else
            {
              v64 = *(_QWORD *)(v61 + 8);
              if ( !v64 )
              {
                v65 = v61;
                v66 = *v62 & 1;
LABEL_114:
                v67 = *(_QWORD *)(v65 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
                if ( v66 && v67 )
                  v65 = v67 ^ v61;
                else
                  v65 = *(_QWORD *)(v65 + 16) & 0xFFFFFFFFFFFFFFFCuLL;
                if ( !v65 )
                  break;
                v68 = *(_QWORD *)(v65 + 8);
                if ( v66 )
                {
                  if ( v68 )
                  {
                    v68 ^= v65;
                    goto LABEL_118;
                  }
                }
                else
                {
LABEL_118:
                  if ( v68 && v68 != v61 )
                  {
                    v61 = v68;
                    continue;
                  }
                }
                v61 = v65;
                goto LABEL_114;
              }
              if ( (*v63 & 1) != 0 )
              {
                v61 ^= v64;
                v62 = v63;
              }
              else
              {
LABEL_123:
                v61 = v64;
                v62 = v63;
              }
            }
          }
        }
      }
    }
LABEL_50:
    FltReleaseResource((PERESOURCE)(v35 + 2));
    if ( v98[0] )
    {
LABEL_51:
      while ( v104 != &v104 )
      {
        v43 = (UNICODE_STRING *)Entry;
        if ( *(_QWORD ***)Entry != &v104 || (v44 = (PVOID *)*((_QWORD *)Entry + 1), *v44 != Entry) )
LABEL_54:
          __fastfail(3u);
        Entry = (PVOID)*((_QWORD *)Entry + 1);
        *v44 = &v104;
        for ( i = *a4; i != (const UNICODE_STRING *)a4; i = *(const UNICODE_STRING **)&i->Length )
        {
          v46 = RtlCompareUnicodeString(v43 + 5, i + 5, 1u);
          if ( v46 < 0 )
          {
            *(_QWORD *)i->Buffer = v43;
            v43->Buffer = i->Buffer;
            i->Buffer = &v43->Length;
            *(_QWORD *)&v43->Length = i;
            goto LABEL_51;
          }
          if ( !v46 )
          {
            BfDereferenceMappingListEntry(v43);
            goto LABEL_51;
          }
        }
        v95 = (WCHAR *)a4[1];
        if ( *(const UNICODE_STRING ***)v95 != a4 )
          goto LABEL_54;
        *(_QWORD *)&v43->Length = a4;
        v43->Buffer = v95;
        *(_QWORD *)v95 = v43;
        a4[1] = v43;
      }
    }
    v13 = v99;
  }
LABEL_65:
  if ( P[1] )
  {
    ExFreePoolWithTag(P[1], 0x74734642u);
    P[1] = 0;
  }
  LODWORD(P[0]) = 0;
  if ( Context )
    FltReleaseContext(Context);
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140017f00  mov     [rsp-8+arg_10], r8
0x140017f05  mov     [rsp-8+arg_8], rdx
0x140017f0a  push    rbp
0x140017f0b  push    rbx
0x140017f0c  push    rsi
0x140017f0d  push    rdi
0x140017f0e  push    r14
0x140017f10  push    r15
0x140017f12  lea     rbp, [rsp-27h]
0x140017f17  sub     rsp, 0E8h
0x140017f1e  mov     r14, rdx
0x140017f21  mov     [rbp+4Fh+Context], 0
0x140017f29  lea     rax, [rbp+4Fh+var_88]
0x140017f2d  mov     qword ptr [rbp+4Fh+var_98], 0
0x140017f35  mov     [rbp+4Fh+Entry], rax
0x140017f39  lea     rdx, [rbp+4Fh+Context]; Context
0x140017f3d  mov     rbx, rcx
0x140017f40  mov     qword ptr [rbp+4Fh+var_A8], 0
0x140017f48  mov     rcx, [r14+18h]; Instance
0x140017f4c  lea     rax, [rbp+4Fh+var_88]
0x140017f50  xorps   xmm0, xmm0
0x140017f53  mov     qword ptr [rbp+4Fh+var_B8], 0
0x140017f5b  mov     rsi, r9
0x140017f5e  mov     [rbp+4Fh+FileNameInformation], 0
0x140017f66  mov     r15, r8
0x140017f69  mov     [rsp+110h+var_D0], 0
0x140017f6e  movups  xmmword ptr [rbp+4Fh+P], xmm0
0x140017f72  mov     [rbp+4Fh+var_88], rax
0x140017f76  call    cs:__imp_FltGetInstanceContext
0x140017f7d  nop     dword ptr [rax+rax+00h]
0x140017f82  test    eax, eax
0x140017f84  js      loc_140018AD2
0x140017f8a  mov     rdx, [rbp+4Fh+Context]
0x140017f8e  lea     rax, [rbp+4Fh+var_98]
0x140017f92  mov     rcx, [r14+20h]
0x140017f96  lea     r9, [rbp+4Fh+var_B8]
0x140017f9a  mov     [rsp+110h+var_E8], rax
0x140017f9f  mov     r8, rbx
0x140017fa2  lea     rax, [rbp+4Fh+var_A8]
0x140017fa6  mov     [rsp+110h+var_F0], rax
0x140017fab  call    BfGetMappingContexts
0x140017fb0  test    eax, eax
0x140017fb2  js      loc_1400189EE
0x140017fb8  mov     [rbp+4Fh+FileNameInformation], 0
0x140017fc0  test    rbx, rbx
0x140017fc3  jz      loc_14001843D
0x140017fc9  lea     r8, [rbp+4Fh+FileNameInformation]; FileNameInformation
0x140017fcd  mov     edx, 1000102h; NameOptions
0x140017fd2  mov     rcx, rbx; CallbackData
0x140017fd5  call    cs:__imp_FltGetFileNameInformation
0x140017fdc  nop     dword ptr [rax+rax+00h]
0x140017fe1  mov     ebx, eax
0x140017fe3  test    eax, eax
0x140017fe5  js      loc_140018442
0x140017feb  mov     rcx, [rbp+4Fh+FileNameInformation]
0x140017fef  cmp     word ptr [rcx+8], 0
0x140017ff4  jz      loc_140018A98
0x140017ffa  mov     rcx, [rbp+4Fh+FileNameInformation]
0x140017ffe  lea     r8, [rbp+4Fh+P]
0x140018002  xor     edx, edx
0x140018004  call    BfFormatPathFromFileNameInfo
0x140018009  mov     [rbp+4Fh+var_CC], eax
0x14001800c  mov     ebx, eax
0x14001800e  test    eax, eax
0x140018010  js      loc_140018A6D
0x140018016  mov     rbx, qword ptr [rbp+4Fh+var_B8]
0x14001801a  mov     [rsp+110h+arg_0], r12
0x140018022  mov     [rsp+110h+var_30], r13
0x14001802a  test    rbx, rbx
0x14001802d  jz      loc_140018105
0x140018033  mov     rax, [r14+20h]
0x140018037  lea     r13, [rbx+10h]
0x14001803b  mov     rdi, [r14+18h]
0x14001803f  xorps   xmm0, xmm0
0x140018042  mov     [rbp+4Fh+var_58], rax
0x140018046  xorps   xmm1, xmm1
0x140018049  lea     rax, [rbp+4Fh+var_88]
0x14001804d  mov     [rbp+4Fh+var_50], rdi
0x140018051  mov     [rbp+4Fh+var_48], rax
0x140018055  mov     rcx, r13; Resource
0x140018058  lea     rax, [rsp+110h+var_D0]
0x14001805d  mov     [rbp+4Fh+var_40], r15
0x140018061  mov     [rbp+4Fh+var_38], rax
0x140018065  movups  [rbp+4Fh+var_B8], xmm0
0x140018069  movups  [rbp+4Fh+var_70], xmm1
0x14001806d  call    cs:__imp_FltAcquireResourceShared
0x140018074  nop     dword ptr [rax+rax+00h]
0x140018079  mov     rcx, [rbx]
0x14001807c  cmp     rcx, rbx
0x14001807f  jz      short loc_1400180EE
0x140018081  mov     rax, [rcx+10h]
0x140018085  cmp     [rax], rdi
0x140018088  jz      loc_1400186BC
0x14001808e  mov     rcx, [rcx]
0x140018091  cmp     rcx, rbx
0x140018094  jnz     short loc_140018081
0x140018096  jmp     short loc_1400180EE
0x140018098  mov     rbx, [r15]
0x14001809b  lea     rax, [rbp+4Fh+var_B8]
0x14001809f  mov     qword ptr [rbp+4Fh+var_70], rax
0x1400180a3  mov     rax, [r15+8]
0x1400180a7  mov     byte ptr [rbp+4Fh+var_70+8], r12b
0x1400180ab  test    r12b, al
0x1400180ae  jnz     loc_140018B10
0x1400180b4  movzx   edi, al
0x1400180b7  and     edi, 1
0x1400180ba  test    rbx, rbx
0x1400180bd  jz      short loc_1400180EE
0x1400180bf  nop
0x1400180c0  mov     rdx, rbx
0x1400180c3  lea     rcx, [rbp+4Fh+var_70]
0x1400180c7  call    BfpRBComparePathNodes
0x1400180cc  test    eax, eax
0x1400180ce  js      loc_140018187
0x1400180d4  jle     loc_1400184D2
0x1400180da  mov     rax, [rbx+8]
0x1400180de  test    edi, edi
0x1400180e0  jnz     loc_140018192
0x1400180e6  mov     rbx, rax
0x1400180e9  test    rbx, rbx
0x1400180ec  jnz     short loc_1400180C0
0x1400180ee  mov     rcx, r13; Resource
0x1400180f1  call    cs:__imp_FltReleaseResource
0x1400180f8  nop     dword ptr [rax+rax+00h]
0x1400180fd  mov     r14, [rbp+4Fh+arg_8]
0x140018101  mov     r15, [rbp+4Fh+arg_10]
0x140018105  mov     rbx, qword ptr [rbp+4Fh+var_A8]
0x140018109  test    rbx, rbx
0x14001810c  jz      loc_14001820D
0x140018112  mov     rax, [r14+20h]
0x140018116  lea     r13, [rbx+10h]
0x14001811a  mov     rdi, [r14+18h]
0x14001811e  xorps   xmm0, xmm0
0x140018121  mov     [rbp+4Fh+var_58], rax
0x140018125  xorps   xmm1, xmm1
0x140018128  lea     rax, [rbp+4Fh+var_88]
0x14001812c  mov     [rbp+4Fh+var_50], rdi
0x140018130  mov     [rbp+4Fh+var_48], rax
0x140018134  mov     rcx, r13; Resource
0x140018137  lea     rax, [rsp+110h+var_D0]
0x14001813c  mov     [rbp+4Fh+var_40], r15
0x140018140  mov     [rbp+4Fh+var_38], rax
0x140018144  movups  [rbp+4Fh+var_A8], xmm0
0x140018148  movups  [rbp+4Fh+var_70], xmm1
0x14001814c  call    cs:__imp_FltAcquireResourceShared
0x140018153  nop     dword ptr [rax+rax+00h]
0x140018158  mov     rcx, [rbx]
0x14001815b  cmp     rcx, rbx
0x14001815e  jz      loc_1400181FE
0x140018164  nop     dword ptr [rax+00h]
0x140018168  nop     dword ptr [rax+rax+00000000h]
0x140018170  mov     rax, [rcx+10h]
0x140018174  cmp     [rax], rdi
0x140018177  jz      loc_140018838
0x14001817d  mov     rcx, [rcx]
0x140018180  cmp     rcx, rbx
0x140018183  jnz     short loc_140018170
0x140018185  jmp     short loc_1400181FE
0x140018187  mov     rax, [rbx]
0x14001818a  test    edi, edi
0x14001818c  jz      loc_1400180E6
0x140018192  test    rax, rax
0x140018195  jz      loc_1400180E6
0x14001819b  xor     rbx, rax
0x14001819e  jmp     loc_1400180E9
0x1400181a3  mov     rbx, [r15]
0x1400181a6  lea     rax, [rbp+4Fh+var_A8]
0x1400181aa  mov     qword ptr [rbp+4Fh+var_70], rax
0x1400181ae  mov     rax, [r15+8]
0x1400181b2  mov     byte ptr [rbp+4Fh+var_70+8], r12b
0x1400181b6  test    r12b, al
0x1400181b9  jnz     loc_140018B21
0x1400181bf  movzx   edi, al
0x1400181c2  and     edi, 1
0x1400181c5  test    rbx, rbx
0x1400181c8  jz      short loc_1400181FE
0x1400181ca  nop     word ptr [rax+rax+00h]
0x1400181d0  mov     rdx, rbx
0x1400181d3  lea     rcx, [rbp+4Fh+var_70]
0x1400181d7  call    BfpRBComparePathNodes
0x1400181dc  test    eax, eax
0x1400181de  js      loc_140018287
0x1400181e4  jle     loc_14001850B
0x1400181ea  mov     rax, [rbx+8]
0x1400181ee  test    edi, edi
0x1400181f0  jnz     loc_140018292
0x1400181f6  mov     rbx, rax
0x1400181f9  test    rbx, rbx
0x1400181fc  jnz     short loc_1400181D0
0x1400181fe  mov     rcx, r13; Resource
0x140018201  call    cs:__imp_FltReleaseResource
0x140018208  nop     dword ptr [rax+rax+00h]
0x14001820d  mov     r13, qword ptr [rbp+4Fh+var_98]
0x140018211  xorps   xmm0, xmm0
0x140018214  mov     rax, [rbp+4Fh+arg_8]
0x140018218  xorps   xmm1, xmm1
0x14001821b  movups  [rbp+4Fh+var_98], xmm0
0x14001821f  lea     rcx, [r13+10h]; Resource
0x140018223  mov     rbx, [rax+18h]
0x140018227  mov     rax, [rax+20h]
0x14001822b  mov     [rbp+4Fh+var_58], rax
0x14001822f  lea     rax, [rbp+4Fh+var_88]
0x140018233  mov     [rbp+4Fh+var_48], rax
0x140018237  mov     rax, [rbp+4Fh+arg_10]
0x14001823b  mov     [rbp+4Fh+var_40], rax
0x14001823f  lea     rax, [rsp+110h+var_D0]
0x140018244  mov     [rbp+4Fh+var_38], rax
0x140018248  movups  [rbp+4Fh+var_70], xmm1
0x14001824c  mov     [rbp+4Fh+var_50], rbx
0x140018250  call    cs:__imp_FltAcquireResourceShared
0x140018257  nop     dword ptr [rax+rax+00h]
0x14001825c  mov     rcx, [r13+0]
0x140018260  cmp     rcx, r13
0x140018263  jz      loc_1400182FE
0x140018269  nop     dword ptr [rax+00000000h]
0x140018270  mov     rax, [rcx+10h]
0x140018274  cmp     [rax], rbx
0x140018277  jz      loc_140018544
0x14001827d  mov     rcx, [rcx]
0x140018280  cmp     rcx, r13
0x140018283  jnz     short loc_140018270
0x140018285  jmp     short loc_1400182FE
0x140018287  mov     rax, [rbx]
0x14001828a  test    edi, edi
0x14001828c  jz      loc_1400181F6
0x140018292  test    rax, rax
0x140018295  jz      loc_1400181F6
0x14001829b  xor     rbx, rax
0x14001829e  jmp     loc_1400181F9
0x1400182a3  mov     rdi, [r15+8]
0x1400182a7  lea     rax, [rbp+4Fh+var_98]
0x1400182ab  mov     rbx, [r15]
0x1400182ae  mov     qword ptr [rbp+4Fh+var_70], rax
0x1400182b2  mov     byte ptr [rbp+4Fh+var_70+8], r12b
0x1400182b6  test    r12b, dil
0x1400182b9  jnz     loc_140018AFF
0x1400182bf  and     edi, 1
0x1400182c2  test    rbx, rbx
0x1400182c5  jz      short loc_1400182FE
0x1400182c7  nop     word ptr [rax+rax+00000000h]
0x1400182d0  mov     rdx, rbx
0x1400182d3  lea     rcx, [rbp+4Fh+var_70]
0x1400182d7  call    BfpRBComparePathNodes
0x1400182dc  test    eax, eax
0x1400182de  js      loc_1400183BA
0x1400182e4  jle     loc_140018499
0x1400182ea  mov     rax, [rbx+8]
0x1400182ee  test    edi, edi
0x1400182f0  jnz     loc_1400183C5
0x1400182f6  mov     rbx, rax
0x1400182f9  test    rbx, rbx
0x1400182fc  jnz     short loc_1400182D0
0x1400182fe  lea     rcx, [r13+10h]; Resource
0x140018302  call    cs:__imp_FltReleaseResource
0x140018309  nop     dword ptr [rax+rax+00h]
0x14001830e  cmp     [rsp+110h+var_D0], 0
0x140018313  mov     r13, [rsp+110h+var_30]
0x14001831b  mov     r12, [rsp+110h+arg_0]
0x140018323  jz      loc_1400183D6
0x140018329  nop     dword ptr [rax+00000000h]
0x140018330  lea     rax, [rbp+4Fh+var_88]
0x140018334  cmp     [rbp+4Fh+var_88], rax
0x140018338  jz      loc_1400183D6
0x14001833e  mov     rdi, [rbp+4Fh+Entry]
0x140018342  lea     rax, [rbp+4Fh+var_88]
0x140018346  cmp     [rdi], rax
0x140018349  jnz     short loc_140018354
0x14001834b  mov     rax, [rdi+8]
0x14001834f  cmp     [rax], rdi
0x140018352  jz      short loc_14001835B
0x140018354  mov     ecx, 3
0x140018359  int     29h; Win8: RtlFailFast(ecx)
0x14001835b  lea     rcx, [rbp+4Fh+var_88]
0x14001835f  mov     [rbp+4Fh+Entry], rax
0x140018363  mov     [rax], rcx
0x140018366  mov     rbx, [rsi]
0x140018369  nop     dword ptr [rax+00000000h]
0x140018370  cmp     rbx, rsi
0x140018373  jz      loc_140018B32
0x140018379  lea     rdx, [rbx+50h]; String2
0x14001837d  mov     r8b, 1; CaseInSensitive
0x140018380  lea     rcx, [rdi+50h]; String1
0x140018384  call    cs:__imp_RtlCompareUnicodeString
0x14001838b  nop     dword ptr [rax+rax+00h]
0x140018390  test    eax, eax
0x140018392  js      short loc_14001839F
0x140018394  jz      loc_1400189AF
0x14001839a  mov     rbx, [rbx]
0x14001839d  jmp     short loc_140018370
0x14001839f  mov     rax, [rbx+8]
0x1400183a3  mov     [rax], rdi
0x1400183a6  mov     rax, [rbx+8]
0x1400183aa  mov     [rdi+8], rax
0x1400183ae  mov     [rbx+8], rdi
0x1400183b2  mov     [rdi], rbx
0x1400183b5  jmp     loc_140018330
0x1400183ba  mov     rax, [rbx]
0x1400183bd  test    edi, edi
0x1400183bf  jz      loc_1400182F6
0x1400183c5  test    rax, rax
  ... truncated ...
```
