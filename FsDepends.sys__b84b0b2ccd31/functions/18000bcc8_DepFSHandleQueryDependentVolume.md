# DepFSHandleQueryDependentVolume

- ea: `0x18000bcc8`
- end: `0x18000c777`
- name: `DepFSHandleQueryDependentVolume`
- size: `2735`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000c940`

## callees

- `0x180001020`
- `0x180001150`
- `0x180001430`
- `0x180001460`
- `0x180002180`
- `0x180002480`
- `0x18000bcc8`
- `0x18000f91c`
- `0x18000f970`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x18000bf5e`
- `ntoskrnl!RtlCompareUnicodeString` at `0x18000c119`
- `ntoskrnl!RtlCompareUnicodeString` at `0x18000bf5e`
- `ntoskrnl!RtlCompareUnicodeString` at `0x18000c119`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000c6cc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000c6cc`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000c6c0`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000c6c0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18000be9c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18000be9c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000be86`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000be86`
- `FLTMGR!FltReleaseContext` at `0x18000be42`
- `FLTMGR!FltReleaseContext` at `0x18000be42`
- `FLTMGR!FltGetInstanceContext` at `0x18000bddb`
- `FLTMGR!FltGetInstanceContext` at `0x18000bddb`

## pseudocode

```c
__int64 __fastcall DepFSHandleQueryDependentVolume(__int64 a1, __int64 a2)
{
  unsigned int v2; // r15d
  __int64 v3; // r8
  __int64 v4; // rdi
  __int64 v5; // rax
  unsigned int *v6; // rax
  unsigned int v7; // r12d
  unsigned int v8; // r14d
  NTSTATUS InstanceContext; // ebx
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rdx
  unsigned int v12; // ebx
  unsigned int v13; // r13d
  _QWORD *v14; // r12
  _QWORD *v15; // r14
  __int64 v16; // rax
  WCHAR *v17; // r8
  __int64 v18; // rdx
  WCHAR *v19; // rcx
  USHORT v20; // r8
  int v21; // r8d
  _QWORD *v22; // rcx
  __int64 v23; // r9
  unsigned int v24; // ebx
  unsigned int v25; // r13d
  __int64 v26; // r14
  unsigned int v27; // eax
  unsigned int *v28; // r14
  int v29; // r9d
  _QWORD *v30; // rdx
  __int64 v31; // rax
  unsigned int *v32; // rax
  char *v33; // r12
  _QWORD *v34; // rbx
  __int64 v35; // rax
  WCHAR *v36; // r8
  __int64 v37; // rdx
  WCHAR *v38; // rcx
  USHORT v39; // r8
  __int64 v40; // rcx
  _QWORD *v41; // rdx
  __int64 v42; // r15
  const void *v43; // rdx
  unsigned int *v44; // rdx
  __int64 v45; // rcx
  char *v46; // rcx
  __int64 v47; // r15
  const void *v48; // rdx
  unsigned int *v49; // rdx
  __int64 v50; // rcx
  char *v51; // rcx
  unsigned int v52; // eax
  __int64 v53; // rax
  _QWORD *v54; // rcx
  _QWORD *v55; // r8
  __int64 v56; // r8
  int v57; // r9d
  int v58; // ebx
  __int64 v59; // r14
  unsigned int v60; // eax
  unsigned int v61; // ebx
  __int64 v62; // rcx
  unsigned int *v63; // rcx
  int v64; // r12d
  char *v65; // r13
  _QWORD *v66; // rdi
  __int64 v67; // rbx
  __int64 v68; // rcx
  __int64 v69; // r15
  const void *v70; // rdx
  int v71; // edx
  __int64 v72; // rcx
  unsigned int v73; // eax
  unsigned int v75; // [rsp+30h] [rbp-39h]
  _QWORD *v76; // [rsp+30h] [rbp-39h]
  PFLT_CONTEXT Context; // [rsp+38h] [rbp-31h] BYREF
  char *v78; // [rsp+40h] [rbp-29h]
  UNICODE_STRING String2; // [rsp+48h] [rbp-21h] BYREF
  UNICODE_STRING String1; // [rsp+58h] [rbp-11h] BYREF
  UNICODE_STRING v81; // [rsp+68h] [rbp-1h] BYREF
  int v84; // [rsp+E0h] [rbp+77h]

  v2 = 0;
  v3 = a2;
  Context = 0;
  v4 = a1;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qq(
      WPP_GLOBAL_Control->AttachedDevice,
      51,
      WPP_bc64936b77293105c4440102cf4189d6_Traceguids,
      a1,
      *(_QWORD *)(a2 + 32));
    v3 = a2;
  }
  v5 = *(_QWORD *)(v4 + 16);
  if ( *(_DWORD *)(v5 + 32) < 8u )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 52, WPP_bc64936b77293105c4440102cf4189d6_Traceguids);
    }
    *(_DWORD *)(v4 + 24) = -1073741811;
    return 4;
  }
  v6 = *(unsigned int **)(v5 + 48);
  v7 = *v6;
  v8 = v6[1];
  v84 = *v6;
  if ( *v6 - 1 > 1 || (v8 & 0xFFFFFFFC) != 0 || !v8 || (v8 & 3) == 3 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_DD(WPP_GLOBAL_Control->AttachedDevice, 53, WPP_bc64936b77293105c4440102cf4189d6_Traceguids, v7, v8);
    }
    *(_DWORD *)(v4 + 24) = -1073741496;
    return 4;
  }
  InstanceContext = FltGetInstanceContext(*(PFLT_INSTANCE *)(v3 + 24), &Context);
  if ( InstanceContext < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_21;
    }
    v11 = 54;
LABEL_20:
    WPP_SF_D(v10->AttachedDevice, v11, WPP_bc64936b77293105c4440102cf4189d6_Traceguids, (unsigned int)InstanceContext);
LABEL_21:
    *(_DWORD *)(v4 + 24) = InstanceContext;
    return 4;
  }
  InstanceContext = ReferenceVolumeContext(Context);
  if ( InstanceContext < 0 )
  {
    FltReleaseContext(Context);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_21;
    }
    v11 = 55;
    goto LABEL_20;
  }
  v12 = 76;
  v13 = 0;
  v75 = 0;
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(&Resource, 1u);
  if ( (v8 & 2) != 0 )
  {
    v14 = (_QWORD *)*((_QWORD *)Context + 1);
    if ( v14 != (_QWORD *)((char *)Context + 8) )
    {
      do
      {
        v15 = v14;
        v14 = (_QWORD *)*v14;
        if ( *((_DWORD *)Context + 20) == 13 )
        {
          v16 = *(_QWORD *)(*(_QWORD *)(v4 + 16) + 8LL);
          if ( v16 )
          {
            v17 = *(WCHAR **)(v16 + 96);
            if ( v17 )
            {
              v18 = v15[12];
              if ( v18 )
              {
                v19 = *(WCHAR **)(v18 + 96);
                if ( v19 )
                {
                  *(_QWORD *)&String2.Length = 0;
                  String1 = 0;
                  String2.Buffer = v17;
                  v20 = *(_WORD *)(v16 + 88);
                  String2.Length = v20;
                  String2.MaximumLength = *(_WORD *)(v16 + 90);
                  String1.Buffer = v19;
                  String1.Length = *(_WORD *)(v18 + 88);
                  String1.MaximumLength = *(_WORD *)(v18 + 90);
                  if ( String1.Length < v20 )
                    continue;
                  String1.Length = v20;
                  if ( RtlCompareUnicodeString(&String1, &String2, 1u) )
                    continue;
                }
              }
            }
          }
        }
        if ( v84 == 1 )
        {
          v12 += 32;
          ++v2;
        }
        else
        {
          v21 = *((unsigned __int16 *)v15 + 72);
          v22 = (_QWORD *)v15[2];
          v12 += v21 + 2;
          if ( v22 == v15 + 2 )
          {
            ++v2;
            v12 += 68;
            if ( v15[17] )
              v12 += v21 + *((unsigned __int16 *)v15 + 65) + 2;
          }
          else
          {
            do
            {
              v23 = *(v22 - 3);
              v24 = v12 + 68;
              v22 = (_QWORD *)*v22;
              if ( v15[17] )
                v24 += *((unsigned __int16 *)v15 + 65) + 2;
              ++v2;
              v12 = v21 + *(unsigned __int16 *)(v23 + 128) + v24;
            }
            while ( v22 != v15 + 2 );
          }
        }
      }
      while ( v14 != (_QWORD *)((char *)Context + 8) );
      v25 = 0;
      if ( v2 )
      {
        v26 = *(_QWORD *)(v4 + 16);
        v27 = *(_DWORD *)(v26 + 24);
        if ( v27 < 8 )
        {
          *(_DWORD *)(v4 + 24) = -1073741789;
          *(_QWORD *)(v4 + 32) = 0;
LABEL_97:
          v61 = 4;
          goto LABEL_114;
        }
        v28 = *(unsigned int **)(v26 + 48);
        if ( v27 >= v12 )
        {
          *(_QWORD *)&String1.Length = v12;
          memset(v28, 0, v12);
          v29 = v84;
          *v28 = v84;
          v30 = (_QWORD *)*((_QWORD *)Context + 1);
          if ( v84 == 1 )
            v31 = 8LL * v2;
          else
            v31 = 17LL * v2;
          v32 = &v28[v31];
          if ( v30 != (_QWORD *)((char *)Context + 8) )
          {
            v33 = (char *)(v32 + 2);
            do
            {
              v34 = v30;
              v30 = (_QWORD *)*v30;
              v76 = v30;
              if ( *((_DWORD *)Context + 20) == 13 )
              {
                v35 = *(_QWORD *)(*(_QWORD *)(v4 + 16) + 8LL);
                if ( v35 )
                {
                  v36 = *(WCHAR **)(v35 + 96);
                  if ( v36 )
                  {
                    v37 = v34[12];
                    if ( v37 )
                    {
                      v38 = *(WCHAR **)(v37 + 96);
                      if ( v38 )
                      {
                        *(_QWORD *)&v81.Length = 0;
                        String2 = 0;
                        v81.Buffer = v36;
                        v39 = *(_WORD *)(v35 + 88);
                        v81.Length = v39;
                        v81.MaximumLength = *(_WORD *)(v35 + 90);
                        String2.Buffer = v38;
                        String2.Length = *(_WORD *)(v37 + 88);
                        String2.MaximumLength = *(_WORD *)(v37 + 90);
                        if ( String2.Length < v39 )
                          goto LABEL_82;
                        String2.Length = v39;
                        if ( RtlCompareUnicodeString(&String2, &v81, 1u) )
                          goto LABEL_81;
                        v29 = v84;
                      }
                    }
                    v30 = v76;
                  }
                }
              }
              if ( v29 != 1 )
              {
                v41 = (_QWORD *)v34[2];
                if ( v41 == v34 + 2 )
                {
                  v42 = 17LL * v25;
                  v28[v42 + 2] = 68;
                  v28[v42 + 3] = *((_DWORD *)v34 + 13);
                  *(_OWORD *)&v28[v42 + 5] = *(_OWORD *)((char *)v34 + 60);
                  v28[v42 + 9] = *((_DWORD *)v34 + 19);
                  v28[v42 + 4] = *((_DWORD *)v34 + 14);
                  v28[v42 + 10] = *((_DWORD *)v34 + 20);
                  v43 = (const void *)v34[17];
                  if ( v43 )
                  {
                    memmove(v33, v43, *((unsigned __int16 *)v34 + 65));
                    v44 = &v28[v42];
                    if ( *((unsigned __int16 *)v34 + 65) > (unsigned __int64)*((unsigned __int16 *)v34 + 64) + 2 )
                    {
                      v44[11] = (_DWORD)v33 - (_DWORD)v28;
                      v28[v42 + 12] = *((unsigned __int16 *)v34 + 65) - *((unsigned __int16 *)v34 + 64) - 2;
                    }
                    v45 = *((unsigned __int16 *)v34 + 65);
                    v33 += v45;
                    v28[v42 + 15] = v44[11] + v45 - *((unsigned __int16 *)v34 + 64);
                    v28[v42 + 16] = *((unsigned __int16 *)v34 + 64);
                  }
                  if ( *((_WORD *)v34 + 72) )
                  {
                    memmove(v33, (const void *)v34[19], *((unsigned __int16 *)v34 + 72));
                    v28[v42 + 17] = (_DWORD)v33 - (_DWORD)v28;
                    v28[v42 + 18] = *((unsigned __int16 *)v34 + 72);
                    v33 += *((unsigned __int16 *)v34 + 72);
                  }
                  ++v25;
                }
                else
                {
                  do
                  {
                    v46 = (char *)*(v41 - 3);
                    v47 = 17LL * v25;
                    *(_QWORD *)&String2.Length = *v41;
                    v78 = v46;
                    v28[v47 + 2] = 68;
                    v28[v47 + 3] = *((_DWORD *)v34 + 13);
                    *(_OWORD *)&v28[v47 + 5] = *(_OWORD *)((char *)v34 + 60);
                    v28[v47 + 9] = *((_DWORD *)v34 + 19);
                    v28[v47 + 4] = *((_DWORD *)v34 + 14);
                    v28[v47 + 10] = *((_DWORD *)v34 + 20);
                    v48 = (const void *)v34[17];
                    if ( v48 )
                    {
                      memmove(v33, v48, *((unsigned __int16 *)v34 + 65));
                      v49 = &v28[v47];
                      if ( *((unsigned __int16 *)v34 + 65) > (unsigned __int64)*((unsigned __int16 *)v34 + 64) + 2 )
                      {
                        v49[11] = (_DWORD)v33 - (_DWORD)v28;
                        v28[v47 + 12] = *((unsigned __int16 *)v34 + 65) - *((unsigned __int16 *)v34 + 64) - 2;
                      }
                      v50 = *((unsigned __int16 *)v34 + 65);
                      v33 += v50;
                      v28[v47 + 15] = v49[11] + v50 - *((unsigned __int16 *)v34 + 64);
                      v46 = v78;
                      v28[v47 + 16] = *((unsigned __int16 *)v34 + 64);
                    }
                    memmove(v33, *((const void **)v46 + 17), *((unsigned __int16 *)v46 + 64));
                    v51 = v78;
                    v28[v47 + 13] = (_DWORD)v33 - (_DWORD)v28;
                    v28[v47 + 14] = *((unsigned __int16 *)v51 + 64);
                    v33 += *((unsigned __int16 *)v51 + 64);
                    v52 = *((unsigned __int16 *)v34 + 72);
                    v78 = v33;
                    if ( (_WORD)v52 )
                    {
                      memmove(v33, (const void *)v34[19], v52);
                      v28[v47 + 17] = (_DWORD)v33 - (_DWORD)v28;
                      v28[v47 + 18] = *((unsigned __int16 *)v34 + 72);
                      v33 = &v78[*((unsigned __int16 *)v34 + 72)];
                    }
                    v41 = *(_QWORD **)&String2.Length;
                    ++v25;
                  }
                  while ( *(_QWORD **)&String2.Length != v34 + 2 );
                  v4 = a1;
                }
LABEL_81:
                v29 = v84;
LABEL_82:
                v30 = v76;
                continue;
              }
              v40 = 8LL * v25++;
              v28[v40 + 2] = 32;
              *(_OWORD *)&v28[v40 + 5] = *(_OWORD *)((char *)v34 + 60);
              v28[v40 + 9] = *((_DWORD *)v34 + 19);
              v28[v40 + 4] = *((_DWORD *)v34 + 14);
              v28[v40 + 3] = *((_DWORD *)v34 + 13);
            }
            while ( v30 != (_QWORD *)((char *)Context + 8) );
          }
          v53 = *(_QWORD *)&String1.Length;
          v28[1] = v25;
          *(_DWORD *)(v4 + 24) = 0;
          goto LABEL_112;
        }
        goto LABEL_96;
      }
    }
  }
  else
  {
    v54 = (_QWORD *)*((_QWORD *)Context + 3);
    if ( v54 != (_QWORD *)((char *)Context + 24) )
    {
      do
      {
        v55 = v54;
        v54 = (_QWORD *)*v54;
        if ( v7 == 1 )
        {
          v12 += 32;
        }
        else
        {
          v56 = *(v55 - 2);
          v57 = *(unsigned __int16 *)(v56 + 138);
          v58 = v57 + *((unsigned __int16 *)Context + 64) + v12 + 68;
          if ( *(_QWORD *)(v56 + 144) )
            v58 += v57 + 2;
          v12 = *(unsigned __int16 *)(v56 + 152) + v58;
        }
        ++v2;
      }
      while ( v54 != (_QWORD *)((char *)Context + 24) );
      v4 = a1;
      if ( v2 )
      {
        v59 = *(_QWORD *)(a1 + 16);
        v60 = *(_DWORD *)(v59 + 24);
        if ( v60 < 8 )
        {
          *(_DWORD *)(a1 + 24) = -1073741789;
          *(_QWORD *)(a1 + 32) = 0;
          goto LABEL_97;
        }
        v28 = *(unsigned int **)(v59 + 48);
        if ( v60 >= v12 )
        {
          *(_QWORD *)&String2.Length = v12;
          memset(v28, 0, v12);
          *v28 = v7;
          if ( v7 == 1 )
            v62 = 8LL * v2;
          else
            v62 = 17LL * v2;
          v63 = &v28[v62];
          if ( *((PFLT_CONTEXT *)Context + 3) != (char *)Context + 24 )
          {
            v64 = (int)v28;
            v65 = (char *)(v63 + 2);
            v66 = (_QWORD *)*((_QWORD *)Context + 3);
            do
            {
              v67 = *(v66 - 2);
              v66 = (_QWORD *)*v66;
              if ( v84 == 1 )
              {
                v68 = 8LL * v75;
                v64 = (int)v28;
                v28[v68 + 2] = 32;
                v28[v68 + 3] = *(_DWORD *)(v67 + 60);
                *(_OWORD *)&v28[v68 + 5] = *(_OWORD *)(v67 + 68);
                v28[v68 + 9] = *(_DWORD *)(v67 + 84);
                v28[v68 + 4] = *(_DWORD *)(v67 + 64);
              }
              else
              {
                v69 = 17LL * v75;
                v28[v69 + 2] = 68;
                v28[v69 + 3] = *(_DWORD *)(v67 + 60);
                *(_OWORD *)&v28[v69 + 5] = *(_OWORD *)(v67 + 68);
                v28[v69 + 9] = *(_DWORD *)(v67 + 84);
                v28[v69 + 4] = *(_DWORD *)(v67 + 64);
                v28[v69 + 10] = *(_DWORD *)(v67 + 88);
                v70 = *(const void **)(v67 + 144);
                if ( v70 )
                {
                  memmove(v65, v70, *(unsigned __int16 *)(v67 + 138));
                  v64 = (int)v28;
                  v71 = (_DWORD)v65 - (_DWORD)v28;
                  v28[v69 + 11] = (_DWORD)v65 - (_DWORD)v28;
                  v28[v69 + 12] = *(unsigned __int16 *)(v67 + 138) - *(unsigned __int16 *)(v67 + 136) - 2;
                  v72 = *(unsigned __int16 *)(v67 + 138);
                  v65 += v72;
                  v28[v69 + 15] = v71 + v72 - *(unsigned __int16 *)(v67 + 136);
                  v28[v69 + 16] = *(unsigned __int16 *)(v67 + 136);
                }
                memmove(v65, *((const void **)Context + 17), *((unsigned __int16 *)Context + 64));
                v28[v69 + 13] = (_DWORD)v65 - v64;
                v28[v69 + 14] = *((unsigned __int16 *)Context + 64);
                v73 = *(unsigned __int16 *)(v67 + 152);
                v65 += *((unsigned __int16 *)Context + 64);
                *(_QWORD *)&String1.Length = v65;
                if ( (_WORD)v73 )
                {
                  memmove(v65, *(const void **)(v67 + 160), v73);
                  v28[v69 + 17] = (_DWORD)v65 - v64;
                  v28[v69 + 18] = *(unsigned __int16 *)(v67 + 152);
                  v65 = (char *)(*(_QWORD *)&String1.Length + *(unsigned __int16 *)(v67 + 152));
                }
              }
              ++v75;
            }
            while ( v66 != (_QWORD *)((char *)Context + 24) );
            v4 = a1;
            v13 = v75;
          }
          v53 = *(_QWORD *)&String2.Length;
          v28[1] = v13;
          *(_DWORD *)(v4 + 24) = 0;
LABEL_112:
          v61 = 4;
          *(_QWORD *)(v4 + 32) = v53;
          goto LABEL_114;
        }
LABEL_96:
        v28[1] = v2;
        *(_DWORD *)(v4 + 24) = -2147483643;
        *(_QWORD *)(v4 + 32) = 8;
        goto LABEL_97;
      }
    }
  }
  v61 = 1;
LABEL_114:
  DereferenceVolumeContext(Context);
  ExReleaseResourceLite(&Resource);
  KeLeaveCriticalRegion();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qq(
      WPP_GLOBAL_Control->AttachedDevice,
      56,
      WPP_bc64936b77293105c4440102cf4189d6_Traceguids,
      v4,
      *(_QWORD *)(a2 + 32));
  }
  return v61;
}

```

## disassembly

```asm
0x18000bcc8  mov     [rsp-8+arg_8], rdx
0x18000bccd  mov     [rsp-8+arg_0], rcx
0x18000bcd2  push    rbp
0x18000bcd3  push    rbx
0x18000bcd4  push    rsi
0x18000bcd5  push    rdi
0x18000bcd6  push    r12
0x18000bcd8  push    r13
0x18000bcda  push    r14
0x18000bcdc  push    r15
0x18000bcde  lea     rbp, [rsp-1Fh]
0x18000bce3  sub     rsp, 88h
0x18000bcea  xor     r15d, r15d
0x18000bced  mov     r8, rdx
0x18000bcf0  mov     [rbp+57h+Context], r15
0x18000bcf4  mov     rdi, rcx
0x18000bcf7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bcfe  lea     rdx, WPP_GLOBAL_Control
0x18000bd05  lea     r13d, [r15+4]
0x18000bd09  cmp     rcx, rdx
0x18000bd0c  jz      short loc_18000BD46
0x18000bd0e  mov     eax, [rcx+2Ch]
0x18000bd11  test    al, 10h
0x18000bd13  jz      short loc_18000BD46
0x18000bd15  cmp     [rcx+29h], r13b
0x18000bd19  jb      short loc_18000BD46
0x18000bd1b  mov     rax, [r8+20h]
0x18000bd1f  lea     edx, [r15+33h]
0x18000bd23  mov     rcx, [rcx+18h]
0x18000bd27  lea     r8, WPP_bc64936b77293105c4440102cf4189d6_Traceguids
0x18000bd2e  mov     r9, rdi
0x18000bd31  mov     [rsp+0C0h+var_A0], rax
0x18000bd36  call    WPP_SF_qq
0x18000bd3b  mov     r8, [rbp+57h+arg_8]
0x18000bd3f  lea     rdx, WPP_GLOBAL_Control
0x18000bd46  mov     rax, [rdi+10h]
0x18000bd4a  cmp     dword ptr [rax+20h], 8
0x18000bd4e  jnb     short loc_18000BD8E
0x18000bd50  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bd57  cmp     rcx, rdx
0x18000bd5a  jz      short loc_18000BD82
0x18000bd5c  mov     edx, [rcx+2Ch]
0x18000bd5f  mov     esi, 1
0x18000bd64  test    sil, dl
0x18000bd67  jz      short loc_18000BD82
0x18000bd69  cmp     byte ptr [rcx+29h], 2
0x18000bd6d  jb      short loc_18000BD82
0x18000bd6f  mov     rcx, [rcx+18h]
0x18000bd73  lea     edx, [rsi+33h]
0x18000bd76  lea     r8, WPP_bc64936b77293105c4440102cf4189d6_Traceguids
0x18000bd7d  call    WPP_SF_
0x18000bd82  mov     dword ptr [rdi+18h], 0C000000Dh
0x18000bd89  jmp     loc_18000C75F
0x18000bd8e  mov     rax, [rax+30h]
0x18000bd92  mov     esi, 1
0x18000bd97  mov     r12d, [rax]
0x18000bd9a  mov     r14d, [rax+4]
0x18000bd9e  mov     [rbp+57h+arg_10], r12d
0x18000bda2  lea     eax, [r12-1]
0x18000bda7  cmp     eax, esi
0x18000bda9  ja      loc_18000C721
0x18000bdaf  test    r14d, 0FFFFFFFCh
0x18000bdb6  jnz     loc_18000C721
0x18000bdbc  test    r14d, r14d
0x18000bdbf  jz      loc_18000C721
0x18000bdc5  mov     eax, r14d
0x18000bdc8  and     eax, 3
0x18000bdcb  cmp     al, 3
0x18000bdcd  jz      loc_18000C721
0x18000bdd3  mov     rcx, [r8+18h]; Instance
0x18000bdd7  lea     rdx, [rbp+57h+Context]; Context
0x18000bddb  call    cs:__imp_FltGetInstanceContext
0x18000bde2  nop     dword ptr [rax+rax+00h]
0x18000bde7  mov     ebx, eax
0x18000bde9  test    eax, eax
0x18000bdeb  jns     short loc_18000BE2C
0x18000bded  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bdf4  lea     rax, WPP_GLOBAL_Control
0x18000bdfb  cmp     rcx, rax
0x18000bdfe  jz      short loc_18000BE24
0x18000be00  mov     edx, [rcx+2Ch]
0x18000be03  test    sil, dl
0x18000be06  jz      short loc_18000BE24
0x18000be08  cmp     byte ptr [rcx+29h], 2
0x18000be0c  jb      short loc_18000BE24
0x18000be0e  lea     edx, [rsi+35h]
0x18000be11  mov     rcx, [rcx+18h]
0x18000be15  lea     r8, WPP_bc64936b77293105c4440102cf4189d6_Traceguids
0x18000be1c  mov     r9d, ebx
0x18000be1f  call    WPP_SF_D
0x18000be24  mov     [rdi+18h], ebx
0x18000be27  jmp     loc_18000C75F
0x18000be2c  mov     rcx, [rbp+57h+Context]; Context
0x18000be30  mov     dl, sil
0x18000be33  call    ReferenceVolumeContext
0x18000be38  mov     ebx, eax
0x18000be3a  test    eax, eax
0x18000be3c  jns     short loc_18000BE76
0x18000be3e  mov     rcx, [rbp+57h+Context]; Context
0x18000be42  call    cs:__imp_FltReleaseContext
0x18000be49  nop     dword ptr [rax+rax+00h]
0x18000be4e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000be55  lea     rax, WPP_GLOBAL_Control
0x18000be5c  cmp     rcx, rax
0x18000be5f  jz      short loc_18000BE24
0x18000be61  mov     edx, [rcx+2Ch]
0x18000be64  test    sil, dl
0x18000be67  jz      short loc_18000BE24
0x18000be69  cmp     byte ptr [rcx+29h], 2
0x18000be6d  jb      short loc_18000BE24
0x18000be6f  mov     edx, 37h ; '7'
0x18000be74  jmp     short loc_18000BE11
0x18000be76  mov     [rbp+57h+arg_18], r13d
0x18000be7a  mov     ebx, 4Ch ; 'L'
0x18000be7f  mov     r13d, r15d
0x18000be82  mov     dword ptr [rbp+57h+var_90], r15d
0x18000be86  call    cs:__imp_KeEnterCriticalRegion
0x18000be8d  nop     dword ptr [rax+rax+00h]
0x18000be92  mov     dl, sil; Wait
0x18000be95  lea     rcx, Resource; Resource
0x18000be9c  call    cs:__imp_ExAcquireResourceExclusiveLite
0x18000bea3  nop     dword ptr [rax+rax+00h]
0x18000bea8  test    r14b, 2
0x18000beac  jz      loc_18000C414
0x18000beb2  mov     rax, [rbp+57h+Context]
0x18000beb6  add     rax, 8
0x18000beba  mov     r12, [rax]
0x18000bebd  cmp     r12, rax
0x18000bec0  jz      loc_18000C6AE
0x18000bec6  mov     r13d, [rbp+57h+arg_10]
0x18000beca  mov     rax, [rbp+57h+Context]
0x18000bece  lea     r14, [r12]
0x18000bed2  mov     r12, [r12]
0x18000bed6  xor     r11d, r11d
0x18000bed9  cmp     dword ptr [rax+50h], 0Dh
0x18000bedd  jnz     loc_18000BF75
0x18000bee3  mov     rax, [rdi+10h]
0x18000bee7  mov     rax, [rax+8]
0x18000beeb  test    rax, rax
0x18000beee  jz      loc_18000BF75
0x18000bef4  mov     r8, [rax+60h]
0x18000bef8  test    r8, r8
0x18000befb  jz      short loc_18000BF75
0x18000befd  mov     rdx, [r14+60h]
0x18000bf01  test    rdx, rdx
0x18000bf04  jz      short loc_18000BF75
0x18000bf06  mov     rcx, [rdx+60h]
0x18000bf0a  test    rcx, rcx
0x18000bf0d  jz      short loc_18000BF75
0x18000bf0f  mov     qword ptr [rbp+57h+String2.Length], r11
0x18000bf13  xorps   xmm0, xmm0
0x18000bf16  movups  xmmword ptr [rbp+57h+String1.Length], xmm0
0x18000bf1a  mov     [rbp+57h+String2.Buffer], r8
0x18000bf1e  movzx   r8d, word ptr [rax+58h]
0x18000bf23  mov     [rbp+57h+String2.Length], r8w
0x18000bf28  movzx   eax, word ptr [rax+5Ah]
0x18000bf2c  mov     [rbp+57h+String2.MaximumLength], ax
0x18000bf30  mov     [rbp+57h+String1.Buffer], rcx
0x18000bf34  movzx   ecx, word ptr [rdx+58h]
0x18000bf38  mov     [rbp+57h+String1.Length], cx
0x18000bf3c  movzx   eax, word ptr [rdx+5Ah]
0x18000bf40  mov     [rbp+57h+String1.MaximumLength], ax
0x18000bf44  cmp     cx, r8w
0x18000bf48  jb      loc_18000BFF5
0x18000bf4e  mov     [rbp+57h+String1.Length], r8w
0x18000bf53  lea     rdx, [rbp+57h+String2]; String2
0x18000bf57  mov     r8b, sil; CaseInSensitive
0x18000bf5a  lea     rcx, [rbp+57h+String1]; String1
0x18000bf5e  call    cs:__imp_RtlCompareUnicodeString
0x18000bf65  nop     dword ptr [rax+rax+00h]
0x18000bf6a  xor     r11d, r11d
0x18000bf6d  test    eax, eax
0x18000bf6f  jnz     loc_18000BFF5
0x18000bf75  cmp     r13d, esi
0x18000bf78  jnz     short loc_18000BF82
0x18000bf7a  add     ebx, 20h ; ' '
0x18000bf7d  add     r15d, esi
0x18000bf80  jmp     short loc_18000BFF5
0x18000bf82  movzx   r8d, word ptr [r14+90h]
0x18000bf8a  lea     rdx, [r14+10h]
0x18000bf8e  mov     rcx, [rdx]
0x18000bf91  add     ebx, 2
0x18000bf94  add     ebx, r8d
0x18000bf97  cmp     rcx, rdx
0x18000bf9a  jnz     short loc_18000BFBD
0x18000bf9c  add     r15d, esi
0x18000bf9f  add     ebx, 44h ; 'D'
0x18000bfa2  cmp     [r14+88h], r11
0x18000bfa9  jz      short loc_18000BFF5
0x18000bfab  movzx   eax, word ptr [r14+82h]
0x18000bfb3  add     ebx, 2
0x18000bfb6  add     ebx, eax
0x18000bfb8  add     ebx, r8d
0x18000bfbb  jmp     short loc_18000BFF5
0x18000bfbd  mov     r10, [r14+88h]
0x18000bfc4  mov     r9, [rcx-18h]
0x18000bfc8  add     ebx, 44h ; 'D'
0x18000bfcb  mov     rcx, [rcx]
0x18000bfce  test    r10, r10
0x18000bfd1  jz      short loc_18000BFE0
0x18000bfd3  movzx   eax, word ptr [r14+82h]
0x18000bfdb  add     ebx, 2
0x18000bfde  add     ebx, eax
0x18000bfe0  movzx   eax, word ptr [r9+80h]
0x18000bfe8  add     r15d, esi
0x18000bfeb  add     eax, r8d
0x18000bfee  add     ebx, eax
0x18000bff0  cmp     rcx, rdx
0x18000bff3  jnz     short loc_18000BFC4
0x18000bff5  mov     rax, [rbp+57h+Context]
0x18000bff9  add     rax, 8
0x18000bffd  cmp     r12, rax
0x18000c000  jnz     loc_18000BECA
0x18000c006  mov     r13d, dword ptr [rbp+57h+var_90]
0x18000c00a  test    r15d, r15d
0x18000c00d  jz      loc_18000C6AE
0x18000c013  mov     r14, [rdi+10h]
0x18000c017  mov     eax, [r14+18h]
0x18000c01b  cmp     eax, 8
0x18000c01e  jnb     short loc_18000C030
0x18000c020  mov     dword ptr [rdi+18h], 0C0000023h
0x18000c027  mov     [rdi+20h], r11
0x18000c02b  jmp     loc_18000C4BB
0x18000c030  mov     r14, [r14+30h]
0x18000c034  cmp     eax, ebx
0x18000c036  jb      loc_18000C4A8
0x18000c03c  mov     eax, ebx
0x18000c03e  xor     edx, edx; Val
0x18000c040  mov     r8d, ebx; Size
0x18000c043  mov     rcx, r14; void *
0x18000c046  mov     qword ptr [rbp+57h+String1.Length], rax
0x18000c04a  call    memset
0x18000c04f  mov     r9d, [rbp+57h+arg_10]
0x18000c053  mov     [r14], r9d
0x18000c056  mov     rcx, [rbp+57h+Context]
0x18000c05a  add     rcx, 8
0x18000c05e  mov     eax, r15d
0x18000c061  mov     rdx, [rcx]
0x18000c064  cmp     r9d, esi
0x18000c067  jnz     short loc_18000C06F
0x18000c069  shl     rax, 5
0x18000c06d  jmp     short loc_18000C073
0x18000c06f  imul    rax, 44h ; 'D'
0x18000c073  add     rax, r14
0x18000c076  cmp     rdx, rcx
0x18000c079  jz      loc_18000C402
0x18000c07f  lea     r12, [rax+8]
0x18000c083  mov     rax, [rbp+57h+Context]
0x18000c087  lea     rbx, [rdx]
0x18000c08a  mov     rdx, [rdx]
0x18000c08d  mov     [rbp+57h+var_90], rdx
0x18000c091  cmp     dword ptr [rax+50h], 0Dh
0x18000c095  jnz     loc_18000C135
0x18000c09b  mov     rax, [rdi+10h]
0x18000c09f  xor     r10d, r10d
0x18000c0a2  mov     rax, [rax+8]
0x18000c0a6  test    rax, rax
0x18000c0a9  jz      loc_18000C135
0x18000c0af  mov     r8, [rax+60h]
0x18000c0b3  test    r8, r8
0x18000c0b6  jz      short loc_18000C135
0x18000c0b8  mov     rdx, [rbx+60h]
0x18000c0bc  test    rdx, rdx
0x18000c0bf  jz      short loc_18000C131
0x18000c0c1  mov     rcx, [rdx+60h]
0x18000c0c5  test    rcx, rcx
0x18000c0c8  jz      short loc_18000C131
0x18000c0ca  mov     qword ptr [rbp+57h+var_58.Length], r10
0x18000c0ce  xorps   xmm0, xmm0
0x18000c0d1  movups  xmmword ptr [rbp+57h+String2.Length], xmm0
0x18000c0d5  mov     [rbp+57h+var_58.Buffer], r8
0x18000c0d9  movzx   r8d, word ptr [rax+58h]
0x18000c0de  mov     [rbp+57h+var_58.Length], r8w
0x18000c0e3  movzx   eax, word ptr [rax+5Ah]
0x18000c0e7  mov     [rbp+57h+var_58.MaximumLength], ax
0x18000c0eb  mov     [rbp+57h+String2.Buffer], rcx
0x18000c0ef  movzx   ecx, word ptr [rdx+58h]
0x18000c0f3  mov     [rbp+57h+String2.Length], cx
0x18000c0f7  movzx   eax, word ptr [rdx+5Ah]
0x18000c0fb  mov     [rbp+57h+String2.MaximumLength], ax
0x18000c0ff  cmp     cx, r8w
0x18000c103  jb      loc_18000C3ED
0x18000c109  mov     [rbp+57h+String2.Length], r8w
0x18000c10e  lea     rdx, [rbp+57h+var_58]; String2
0x18000c112  mov     r8b, sil; CaseInSensitive
0x18000c115  lea     rcx, [rbp+57h+String2]; String1
0x18000c119  call    cs:__imp_RtlCompareUnicodeString
0x18000c120  nop     dword ptr [rax+rax+00h]
0x18000c125  test    eax, eax
0x18000c127  jnz     loc_18000C3E9
0x18000c12d  mov     r9d, [rbp+57h+arg_10]
0x18000c131  mov     rdx, [rbp+57h+var_90]
0x18000c135  cmp     r9d, esi
0x18000c138  jnz     short loc_18000C174
0x18000c13a  mov     ecx, r13d
0x18000c13d  shl     rcx, 5
0x18000c141  add     r13d, esi
0x18000c144  mov     dword ptr [rcx+r14+8], 20h ; ' '
0x18000c14d  movups  xmm0, xmmword ptr [rbx+3Ch]
0x18000c151  movups  xmmword ptr [rcx+r14+14h], xmm0
  ... truncated ...
```
