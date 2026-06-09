# Planar::CompressV2<24,ulong,3,16777215>(uchar *,uchar *,uint,uint,uint,uchar *,uint,Planar::_MATCH *)

- ea: `0x1800542e0`
- end: `0x180056308`
- name: `??$CompressV2@$0BI@K$02$0PPPPPP@@Planar@@YAIPEAE0III0IPEAU_MATCH@0@@Z`
- size: `8232`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, int, void *, int, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18003cfc8`

## callees

- `0x180002c8c`
- `0x180003158`
- `0x180004a94`
- `0x180006210`
- `0x180006340`
- `0x1800065b0`
- `0x1800542e0`
- `0x180078c20`
- `0x1801614c4`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180054b41`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180054cf8`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800552d9`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800553cd`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180055bd5`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180056031`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800560f8`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800562de`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180054b41`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180054cf8`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800552d9`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800553cd`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180055bd5`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180056031`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800560f8`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800562de`

## pseudocode

```c
__int64 __fastcall Planar::CompressV2<24,unsigned long,3,16777215>(
        char *Src,
        char *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        char *a6,
        unsigned int a7,
        __int64 a8)
{
  char *v8; // rsi
  __int64 v10; // r13
  unsigned int v11; // edi
  char v12; // r14
  char v13; // r15
  unsigned __int8 *v14; // r9
  char *v15; // rcx
  unsigned int v16; // r8d
  int *i; // rdx
  int v18; // eax
  unsigned __int8 *v19; // r8
  unsigned int v20; // r12d
  int v21; // edx
  unsigned int v22; // eax
  unsigned int v23; // r11d
  __int64 v24; // r10
  unsigned __int8 *v25; // rbx
  int v26; // r13d
  unsigned __int8 *v27; // rdx
  unsigned int v28; // edi
  unsigned int v29; // esi
  int v30; // r13d
  unsigned __int8 *v31; // rdx
  unsigned __int8 *v32; // rdx
  int v33; // r15d
  int v34; // r14d
  int v35; // r12d
  unsigned __int8 *v36; // r11
  int v37; // r10d
  unsigned __int64 v38; // r10
  unsigned int v39; // edx
  unsigned int v40; // r13d
  unsigned __int8 *v41; // rdx
  unsigned __int64 v42; // r10
  int v43; // r9d
  char v44; // r10
  unsigned __int64 v45; // r11
  unsigned int v46; // r14d
  int v47; // ecx
  int v48; // eax
  int v49; // eax
  int v50; // ecx
  unsigned int v51; // r15d
  __int64 v52; // rdi
  unsigned int v53; // r14d
  unsigned __int8 *v54; // rbx
  int v55; // ecx
  unsigned int v56; // eax
  char *v57; // r13
  __int64 v58; // rdi
  int v59; // r14d
  int v60; // r12d
  unsigned int v61; // r15d
  char *v62; // r9
  unsigned int v63; // ecx
  unsigned __int8 *v64; // rsi
  int v65; // eax
  int v66; // ecx
  unsigned __int8 *v67; // rcx
  unsigned __int8 *v68; // rbx
  unsigned int v69; // eax
  char *v70; // rdx
  unsigned int v71; // eax
  _BYTE *v72; // r13
  unsigned int v73; // eax
  unsigned int v74; // ebx
  unsigned int v75; // ecx
  _BYTE *v76; // r13
  char *j; // rsi
  char v78; // dl
  int v79; // ecx
  char v80; // dl
  unsigned __int8 *v81; // r8
  unsigned __int8 *v83; // rdx
  unsigned __int8 *v84; // r9
  bool v85; // r8
  bool v86; // zf
  char v87; // cl
  int v88; // edx
  char v89; // r8
  char v90; // cl
  char v91; // r8
  char v92; // cl
  char v93; // r8
  char v94; // cl
  char v95; // r8
  char v96; // cl
  char v97; // r8
  char v98; // cl
  char v99; // r8
  EVENT_DESCRIPTOR *v100; // rdx
  __int16 *v101; // rax
  char v102; // dl
  unsigned int v103; // eax
  char *v104; // r13
  char v105; // r8
  char v106; // dl
  unsigned int v107; // eax
  char *v108; // r13
  char *v109; // r8
  char v110; // dl
  char v111; // cl
  char v112; // dl
  char v113; // cl
  unsigned int v114; // edx
  char *v115; // rbx
  char *v116; // r13
  unsigned int v117; // ecx
  char v118; // [rsp+40h] [rbp-C0h]
  char v119; // [rsp+41h] [rbp-BFh]
  _BYTE v120[2]; // [rsp+42h] [rbp-BEh] BYREF
  int v121; // [rsp+44h] [rbp-BCh]
  unsigned int v122; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v123; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v124; // [rsp+50h] [rbp-B0h]
  unsigned int v125; // [rsp+54h] [rbp-ACh]
  __int64 v126; // [rsp+58h] [rbp-A8h]
  int v127; // [rsp+60h] [rbp-A0h] BYREF
  const char *v128; // [rsp+68h] [rbp-98h] BYREF
  char v129; // [rsp+70h] [rbp-90h]
  unsigned int v130; // [rsp+74h] [rbp-8Ch] BYREF
  int v131; // [rsp+78h] [rbp-88h]
  const char *v132; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v133; // [rsp+88h] [rbp-78h]
  char *v134; // [rsp+90h] [rbp-70h]
  unsigned int v135; // [rsp+98h] [rbp-68h]
  char *v136; // [rsp+A0h] [rbp-60h]
  EVENT_DESCRIPTOR v137; // [rsp+A8h] [rbp-58h] BYREF
  char *v138; // [rsp+B8h] [rbp-48h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+C0h] [rbp-40h] BYREF
  EVENT_DESCRIPTOR v140; // [rsp+D0h] [rbp-30h] BYREF
  EVENT_DESCRIPTOR v141; // [rsp+E0h] [rbp-20h] BYREF
  char *v142; // [rsp+F0h] [rbp-10h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+100h] [rbp+0h] BYREF
  __int16 *v144; // [rsp+110h] [rbp+10h]
  int v145; // [rsp+118h] [rbp+18h]
  int v146; // [rsp+11Ch] [rbp+1Ch]
  const char *v147; // [rsp+120h] [rbp+20h]
  __int64 v148; // [rsp+128h] [rbp+28h]
  const char **v149; // [rsp+130h] [rbp+30h]
  __int64 v150; // [rsp+138h] [rbp+38h]
  unsigned int *v151; // [rsp+140h] [rbp+40h]
  __int64 v152; // [rsp+148h] [rbp+48h]
  unsigned int *v153; // [rsp+150h] [rbp+50h]
  __int64 v154; // [rsp+158h] [rbp+58h]

  v8 = a6;
  v10 = a4;
  v11 = a3;
  v136 = Src;
  v133 = a4;
  v122 = a3;
  v138 = a2;
  v134 = a6;
  v126 = a8;
  v142 = a2;
  if ( a3 < a4 || (((unsigned __int8)a3 | (unsigned __int8)a4) & 3) != 0 || a3 > a7 || a3 != 3 * (a3 / 3) )
  {
    if ( (unsigned int)CallbackContext > 5 )
    {
      v137.Keyword = 0;
      v151 = &v122;
      v122 = a4;
      v149 = (const char **)&v123;
      v123 = a3;
      v147 = "Lines must be a multiple of 4 pels and there must be a whole number of pixels in the buffer (cbSrcBitmap = "
             "%d, rowDelta = %d)";
      *(_DWORD *)&v137.Level = 5;
      UserData.Ptr = (ULONGLONG)off_1801E7010;
      v152 = 4;
      v150 = 4;
      v148 = 126;
      *(_DWORD *)&v137.Id = 184549376;
      UserData.Size = *(unsigned __int16 *)off_1801E7010;
      v144 = word_1801B4B6A;
      UserData.Reserved = 2;
      v145 = 44;
      v146 = 1;
      LODWORD(v132) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &v137, 0, 0, 5u, &UserData);
    }
    return 0;
  }
  v12 = 0;
  v13 = 0;
  v131 = 0xFFFFFF;
  v118 = 0;
  v127 = 0xFFFFFF;
  v119 = 0;
  memcpy_0(a6, Src, a4);
  v15 = &Src[v10];
  v16 = v11 - v10;
  for ( i = (int *)&a6[v10]; v16 >= 8; i += 2 )
  {
    v16 -= 8;
    *i = *(_DWORD *)v15 ^ *(_DWORD *)&v15[-(unsigned int)v10];
    v18 = *((_DWORD *)v15 + 1) ^ *(_DWORD *)&v15[-(unsigned int)v10 + 4];
    v15 += 8;
    i[1] = v18;
  }
  if ( v16 )
    *i = *(_DWORD *)v15 ^ *(_DWORD *)&v15[-(unsigned int)v10];
  v19 = (unsigned __int8 *)v126;
  v20 = 0;
  v21 = 2;
  v125 = 0;
  v22 = 0;
  v129 = 1;
  v121 = 2;
  v23 = v10;
  *(_BYTE *)(v126 + 8) = 0;
  v19[20] = 0;
  v124 = v10;
  v135 = 0;
  do
  {
    if ( v20 >= v23 )
      goto LABEL_157;
    do
    {
      if ( (unsigned int)v21 >= 0x2000 )
        return 0;
      if ( v20 + 18 >= v23 )
      {
LABEL_121:
        v13 = 7;
        v29 = 1;
        v118 = 7;
LABEL_126:
        v12 = 1;
        v119 = 1;
        if ( v19[12 * (v21 - 1) + 8] != 7 )
          goto LABEL_135;
        *(_DWORD *)&v19[12 * (v21 - 1) + 4] += v29;
        v20 += v29 + 2 * v29;
        v125 = v20;
        goto LABEL_155;
      }
      while ( 1 )
      {
        v24 = v20;
        v25 = (unsigned __int8 *)&v8[v20];
        v26 = v25[2] | ((v25[1] | (*v25 << 8)) << 8);
        if ( v26 )
        {
          if ( v26 != (v25[5] | (((v25[3] << 8) | v25[4]) << 8)) || v26 != (v25[8] | (((v25[6] << 8) | v25[7]) << 8)) )
          {
            v29 = 0;
            goto LABEL_46;
          }
          v29 = 0;
          if ( v26 != (v25[11] | ((v25[10] | (v25[9] << 8)) << 8)) )
            goto LABEL_46;
          v31 = v25 + 12;
          v14 = &v25[v23 - v20 - 12];
          v28 = 4;
          LODWORD(v19) = v25[11] | (((v25[9] << 8) | v25[10]) << 8);
          if ( v25 + 14 < v14 )
          {
            do
            {
              if ( (v31[2] | ((v31[1] | (*v31 << 8)) << 8)) != (_DWORD)v19 )
                break;
              v31 += 3;
              ++v28;
            }
            while ( v31 + 2 < v14 );
            if ( v28 > 5 )
            {
              v13 = 3;
              v29 = v28;
              v118 = 3;
              if ( v28 >= 0x14 )
                goto LABEL_41;
            }
          }
        }
        else
        {
          if ( v20 + 3 < v23 && !(v25[5] | (((v25[3] << 8) | v25[4]) << 8)) )
          {
            if ( v20 + 6 >= v23 || v25[8] | (((v25[6] << 8) | v25[7]) << 8) )
            {
              v13 = 1;
              v29 = 2;
              v118 = 1;
              if ( !v12 )
                goto LABEL_28;
            }
            else
            {
              if ( v20 + 9 < v23 && !(v25[11] | ((v25[10] | (v25[9] << 8)) << 8)) )
              {
                v27 = v25 + 12;
                v14 = &v25[v23 - v20 - 12];
                v28 = 4;
                LODWORD(v19) = v25[11] | (((v25[9] << 8) | v25[10]) << 8);
                if ( v25 + 14 >= v14 )
                  goto LABEL_355;
                do
                {
                  if ( (v27[2] | (((*v27 << 8) | v27[1]) << 8)) != (_DWORD)v19 )
                    break;
                  v27 += 3;
                  ++v28;
                }
                while ( v27 + 2 < v14 );
                v29 = 0;
                if ( v28 )
                {
LABEL_355:
                  v13 = 1;
                  v29 = v28;
                  v118 = 1;
                  if ( v28 >= 0x14 )
                    goto LABEL_41;
                }
                if ( !v12 )
                  goto LABEL_131;
                goto LABEL_47;
              }
              v13 = 1;
              v29 = 3;
              v118 = 1;
              if ( !v12 )
                goto LABEL_28;
            }
LABEL_46:
            v28 = 0;
            goto LABEL_47;
          }
          v28 = 0;
          v13 = 1;
          v118 = 1;
          v29 = 1;
          if ( !v12 )
          {
LABEL_28:
            v30 = v127;
            goto LABEL_43;
          }
        }
LABEL_47:
        v32 = (unsigned __int8 *)&v136[v20];
        v33 = *v32;
        v34 = v32[1];
        v35 = v32[2];
        LODWORD(v14) = v35 | ((v34 | ((unsigned __int8)v136[v24] << 8)) << 8);
        if ( (_DWORD)v14 != ((unsigned __int8)v136[v24 + 8]
                           | ((((unsigned __int8)v136[v24 + 6] << 8) | (unsigned __int8)v136[v24 + 7]) << 8)) )
        {
          v20 = v125;
          v13 = v118;
          goto LABEL_72;
        }
        v19 = v32 + 12;
        v36 = v32 + 14;
        if ( (_DWORD)v14 != (v32[14] | (((v32[12] << 8) | v32[13]) << 8)) )
          goto LABEL_69;
        v37 = v32[5] | (((v32[3] << 8) | v32[4]) << 8);
        if ( v37 != (v32[11] | (((v32[9] << 8) | v32[10]) << 8)) || v37 != (v32[17] | (((v32[15] << 8) | v32[16]) << 8)) )
          goto LABEL_69;
        if ( (_DWORD)v14 != v37 )
        {
          LODWORD(v14) = 0;
          LODWORD(v19) = (__int16)(v124 - v125);
          if ( (int)v19 > 3 )
          {
            do
            {
              if ( (v32[2] | ((v32[1] | (*v32 << 8)) << 8)) != (v35 | ((v34 | (v33 << 8)) << 8)) )
                break;
              if ( (v32[5] | (((v32[3] << 8) | v32[4]) << 8)) != v37 )
                break;
              v32 += 6;
              LODWORD(v14) = (_DWORD)v14 + 2;
              LODWORD(v19) = (_DWORD)v19 - 6;
            }
            while ( (int)v19 > 3 );
            if ( (unsigned int)v14 > 9 && (unsigned int)v14 > v29 )
            {
              v13 = 5;
              v29 = (unsigned int)v14;
              v118 = 5;
              if ( (unsigned int)v14 >= 0x14 )
                goto LABEL_41;
              v20 = v125;
              goto LABEL_71;
            }
          }
LABEL_69:
          v20 = v125;
          goto LABEL_70;
        }
        v20 = v125;
        if ( !v129 )
        {
          v38 = (unsigned __int64)&v32[v124 - v125 - 12];
          v39 = 4;
          LODWORD(v14) = *(v19 - 1) | (((*(v19 - 3) << 8) | *(v19 - 2)) << 8);
          if ( (unsigned __int64)v36 < v38 )
          {
            do
            {
              if ( (v19[2] | ((v19[1] | (*v19 << 8)) << 8)) != (_DWORD)v14 )
                break;
              v19 += 3;
              ++v39;
            }
            while ( (unsigned __int64)(v19 + 2) < v38 );
            if ( v39 > 5 && v39 > v29 )
            {
              v13 = 4;
              v29 = v39;
              v118 = 4;
              if ( v39 >= 0x14 )
                goto LABEL_41;
              goto LABEL_71;
            }
          }
        }
LABEL_70:
        v13 = v118;
LABEL_71:
        v23 = v124;
LABEL_72:
        if ( v29 >= 6 )
          goto LABEL_113;
        if ( v25[5] | (((v25[3] << 8) | v25[4]) << 8)
          || v25[8] | (((v25[6] << 8) | v25[7]) << 8)
          || v25[11] | ((v25[10] | (v25[9] << 8)) << 8)
          || v25[14] | (((v25[12] << 8) | v25[13]) << 8)
          || v26 != v131
          || *(_BYTE *)(v126 + 12LL * (unsigned int)(v121 - 1) + 8) != 1
          || (v40 = v133, v20 == (unsigned __int16)v133) )
        {
          if ( (unsigned int)CallbackContext > 5 )
          {
            v150 = 4;
            v148 = 24;
            v127 = v23 - v20;
            *(_DWORD *)&EventDescriptor.Id = 184549376;
            v149 = (const char **)&v127;
            EventDescriptor.Keyword = 0;
            v147 = "FGBG: Checking %d bytes";
            *(_DWORD *)&EventDescriptor.Level = 5;
            UserData.Ptr = (ULONGLONG)off_1801E7010;
            UserData.Size = *(unsigned __int16 *)off_1801E7010;
            v144 = (__int16 *)qword_1801B4B30;
            UserData.Reserved = 2;
            v145 = 46;
            v146 = 1;
            v130 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
            EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
          }
          v44 = 0;
          v45 = (unsigned __int64)&v25[v124 - v20];
          v46 = 0;
          v14 = v25;
          v30 = v25[2] | (((*v25 << 8) | v25[1]) << 8);
          v127 = v30;
          do
          {
            v14 += 3;
            ++v46;
            if ( (unsigned __int64)(v14 + 3) > v45 )
              break;
            v47 = v14[2] | ((v14[1] | (*v14 << 8)) << 8);
            if ( v47 != v30 )
            {
              if ( v47 )
                break;
            }
            if ( (v46 & 7) == 0 && (unsigned __int64)(v14 + 72) <= v45 )
            {
              v48 = 3;
              while ( 1 )
              {
                LODWORD(v19) = v14[v48 + 2] | (((v14[v48] << 8) | v14[v48 + 1]) << 8);
                if ( (_DWORD)v19 != v30 )
                  break;
                v48 += 3;
                if ( v48 >= 72 )
                  goto LABEL_99;
                v44 = 1;
              }
            }
          }
          while ( !v44 );
LABEL_99:
          v49 = 32;
          v50 = 48;
          if ( v30 != v131 )
            v49 = 48;
          v51 = v49 - 8;
          if ( (v46 & 7) != 0 )
            v51 = v49;
          if ( (unsigned int)CallbackContext > 5 )
          {
            v130 = v51;
            v140.Keyword = 0;
            v151 = &v130;
            LODWORD(v132) = v46;
            v149 = &v132;
            v152 = 4;
            v147 = "FGBG: resulting run %d, checklen %d ";
            *(_DWORD *)&v140.Level = 5;
            UserData.Ptr = (ULONGLONG)off_1801E7010;
            v150 = 4;
            v148 = 37;
            *(_DWORD *)&v140.Id = 184549376;
            UserData.Size = *(unsigned __int16 *)off_1801E7010;
            v144 = (__int16 *)&byte_1801B4AEF;
            UserData.Reserved = 2;
            v145 = 53;
            v146 = 1;
            v123 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
            EventWriteTransfer(RegHandle, &v140, 0, 0, 5u, &UserData);
          }
          if ( v46 < v51 )
          {
            v13 = v118;
          }
          else
          {
            if ( v46 <= v29 )
            {
              v13 = v118;
            }
            else
            {
              v13 = 6;
              v29 = v46;
              v118 = 6;
              if ( v46 >= 0x14 )
                goto LABEL_42;
            }
            if ( (unsigned int)CallbackContext > 5 )
            {
              v120[0] = v13;
              v132 = "FGBG: resulting best run %d, type %d";
              v123 = v29;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
                v50,
                (unsigned int)&byte_1801B4AA7,
                (_DWORD)v19,
                (_DWORD)v14,
                (__int64)&v132,
                (__int64)&v123,
                (__int64)v120);
            }
          }
LABEL_113:
          v40 = v133;
          goto LABEL_114;
        }
        v41 = v25 + 15;
        v42 = (unsigned __int64)&v25[v23 - v20 - 12];
        v43 = 4;
        if ( (unsigned __int64)(v25 + 17) < v42 )
        {
          do
          {
            if ( (v41[2] | (((*v41 << 8) | v41[1]) << 8)) != (v25[14] | ((v25[13] | (v25[12] << 8)) << 8)) )
              break;
            v41 += 3;
            ++v43;
          }
          while ( (unsigned __int64)(v41 + 2) < v42 );
        }
        LODWORD(v14) = v43 + 1;
        if ( (unsigned int)v14 > v29 )
        {
          v13 = 2;
          v29 = (unsigned int)v14;
          v118 = 2;
          if ( (unsigned int)v14 >= 0x14 )
            goto LABEL_41;
        }
LABEL_114:
        v12 = v119;
        if ( v119 )
        {
          if ( v29 >= 6 && (v13 == 1 || v29 >= 8) )
            goto LABEL_131;
LABEL_124:
          v13 = 7;
          v29 = 1;
          v118 = 7;
LABEL_125:
          v21 = v121;
          v19 = (unsigned __int8 *)v126;
          goto LABEL_126;
        }
        if ( v29 >= 6 )
          goto LABEL_131;
        if ( v28 <= 4 || (v25[2] | ((v25[1] | (*v25 << 8)) << 8)) != v131 )
          break;
        v21 = v121;
        v19 = (unsigned __int8 *)v126;
        if ( *(_BYTE *)(v126 + 12LL * (unsigned int)(v121 - 1) + 8) != 3 || v20 == v40 )
        {
          v13 = 3;
          v118 = 3;
          v29 = v28;
          v119 = 0;
          goto LABEL_44;
        }
        *(_DWORD *)(v126 + 12LL * (unsigned int)(v121 - 1) + 4) += v28;
        v23 = v124;
        v20 += v28 + 2 * v28;
        v8 = v134;
        v125 = v20;
        if ( v20 + 18 >= v124 )
          goto LABEL_121;
      }
      if ( !v29 )
        goto LABEL_124;
LABEL_131:
      if ( v13 == 7 )
        goto LABEL_125;
LABEL_41:
      v30 = v127;
LABEL_42:
      v21 = v121;
      v19 = (unsigned __int8 *)v126;
LABEL_43:
      v119 = 0;
      if ( v13 == 3 )
      {
LABEL_44:
        v30 = v25[2] | ((v25[1] | (*v25 << 8)) << 8);
        v131 = v30;
        goto LABEL_136;
      }
      if ( v13 == 6 )
      {
        v131 = v30;
        goto LABEL_136;
      }
LABEL_135:
      v30 = v131;
LABEL_136:
      v52 = (unsigned int)(v21 - 1);
      v53 = v29 + v125 + 2 * v29;
      if ( v125 == (unsigned __int16)v133 )
        goto LABEL_178;
      v125 += v29 + 2 * v29;
      v54 = &v19[12 * v52];
      v20 = v53;
      v55 = v54[8];
      if ( v13 != (_BYTE)v55 )
      {
        if ( v13 == 1 )
        {
          if ( (unsigned __int8)(v55 - 1) <= 1u )
          {
            *((_DWORD *)v54 + 1) += v29;
            goto LABEL_154;
          }
LABEL_163:
          if ( (_BYTE)v55 == 6 )
          {
            v65 = *((_DWORD *)v54 + 1) & 7;
            if ( v65 )
            {
              v66 = 8 - v65;
              if ( 8 - v65 > v29 )
                v66 = v29;
              v29 -= v66;
              *((_DWORD *)v54 + 1) += v66;
              if ( (unsigned int)CallbackContext > 5 )
              {
                LODWORD(v132) = *((_DWORD *)v54 + 1);
                v128 = "Added %u pels to FGBG giving %u leaving %u";
                v123 = v29;
                v130 = v66;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                  v66,
                  (unsigned int)byte_1801B49BD,
                  (_DWORD)v19,
                  (_DWORD)v14,
                  (__int64)&v128,
                  (__int64)&v130,
                  (__int64)&v132,
                  (__int64)&v123);
                v19 = (unsigned __int8 *)v126;
              }
              if ( v29 < 9 )
              {
                *((_DWORD *)v54 + 1) += v29;
                if ( (unsigned int)CallbackContext > 5 )
                {
                  v123 = *((_DWORD *)v54 + 1);
                  v128 = "Merged BG with preceding FGBG gives %u";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                    v66,
                    (unsigned int)qword_1801B4980,
                    (_DWORD)v19,
                    (_DWORD)v14,
                    (__int64)&v128,
                    (__int64)&v123);
                }
LABEL_153:
                v21 = v121;
                goto LABEL_154;
              }
            }
            v21 = v121;
          }
LABEL_173:
          if ( v13 == 7 )
          {
            v67 = &v19[12 * (v21 - 2)];
            if ( v67[8] == 7 && *((_DWORD *)v54 + 1) == 1 )
            {
              v21 = v52;
              *((_DWORD *)v67 + 1) += v29 + 1;
              v121 = v52;
              if ( (unsigned int)CallbackContext > 5 )
              {
                v123 = *(_DWORD *)&v19[12 * (unsigned int)(v52 - 1) + 4];
                v128 = "Merged color with preceding color gives %u";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                  v123,
                  (unsigned int)byte_1801B4943,
                  (_DWORD)v19,
                  (_DWORD)v14,
                  (__int64)&v128,
                  (__int64)&v123);
                v21 = v52;
              }
              goto LABEL_154;
            }
          }
        }
        else
        {
LABEL_148:
          if ( v13 != 6 )
          {
LABEL_162:
            if ( v13 == 2 )
              goto LABEL_163;
            goto LABEL_173;
          }
          if ( (_BYTE)v55 == 1 )
          {
            v56 = *((_DWORD *)v54 + 1);
            if ( v56 < 8 )
            {
              v54[8] = 6;
              *((_DWORD *)v54 + 1) = v29 + v56;
              *(_DWORD *)v54 = v30;
              if ( (unsigned int)CallbackContext <= 5 )
                goto LABEL_154;
              v123 = *((_DWORD *)v54 + 1);
              v132 = "Merged FGBG with preceding BG run -> %u";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                v55,
                (unsigned int)byte_1801B4A13,
                (_DWORD)v19,
                (_DWORD)v14,
                (__int64)&v132,
                (__int64)&v123);
              goto LABEL_153;
            }
          }
        }
LABEL_178:
        v68 = &v19[12 * v21];
        v68[8] = v13;
        *((_DWORD *)v68 + 1) = v29;
        *(_DWORD *)v68 = v30;
        if ( (unsigned int)CallbackContext > 5 )
        {
          LODWORD(v132) = v52;
          v123 = *(_DWORD *)&v19[12 * v52 + 4];
          v120[0] = v19[12 * v52 + 8];
          v154 = 4;
          v153 = &v123;
          v152 = 4;
          v151 = (unsigned int *)&v132;
          v149 = (const char **)v120;
          v147 = "Best run of type %u (index %u) has length %u";
          *(_DWORD *)&v141.Level = 5;
          UserData.Ptr = (ULONGLONG)off_1801E7010;
          v150 = 1;
          v148 = 45;
          *(_DWORD *)&v141.Id = 184549376;
          v141.Keyword = 0;
          UserData.Size = *(unsigned __int16 *)off_1801E7010;
          v144 = (__int16 *)byte_1801B48E9;
          UserData.Reserved = 2;
          v145 = 89;
          v146 = 1;
          v130 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EventWriteTransfer(RegHandle, &v141, 0, 0, 6u, &UserData);
          v21 = v121;
        }
        if ( (unsigned int)CallbackContext > 5 )
        {
          v123 = *((_DWORD *)v68 + 1);
          v120[0] = v68[8];
          v153 = &v123;
          v151 = (unsigned int *)&v132;
          v149 = (const char **)v120;
          v147 = "Trying run of type %u (index %u) length %u";
          *(_DWORD *)&v137.Level = 5;
          UserData.Ptr = (ULONGLONG)off_1801E7010;
          LODWORD(v132) = v21;
          v154 = 4;
          v152 = 4;
          v150 = 1;
          v148 = 43;
          *(_DWORD *)&v137.Id = 184549376;
          v137.Keyword = 0;
          UserData.Size = *(unsigned __int16 *)off_1801E7010;
          v144 = word_1801B488A;
          UserData.Reserved = 2;
          v145 = 83;
          v146 = 1;
          v130 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EventWriteTransfer(RegHandle, &v137, 0, 0, 6u, &UserData);
          v21 = v121;
        }
        ++v21;
        v125 = v53;
        v121 = v21;
        v20 = v53;
        goto LABEL_154;
      }
      if ( v13 == 1 )
      {
        *((_DWORD *)v54 + 1) += v29;
        goto LABEL_154;
      }
      if ( v13 != 3 && v13 != 6 )
        goto LABEL_162;
      if ( v30 != *(_DWORD *)v54 )
        goto LABEL_148;
      *((_DWORD *)v54 + 1) += v29;
      if ( (unsigned int)CallbackContext > 5 )
      {
        v123 = *((_DWORD *)v54 + 1);
        v120[0] = v54[8];
        v132 = "Merged %u with preceding, giving %u";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
          v55,
          (unsigned int)qword_1801B4A50,
          (_DWORD)v19,
          (_DWORD)v14,
          (__int64)&v132,
          (__int64)v120,
          (__int64)&v123);
        goto LABEL_153;
      }
LABEL_154:
      v12 = v119;
LABEL_155:
      v23 = v124;
      v19 = (unsigned __int8 *)v126;
      v8 = v134;
    }
    while ( v20 < v124 );
    v11 = v122;
    v22 = v135;
LABEL_157:
    ++v22;
    v124 = v11;
    v129 = 0;
    v23 = v11;
    v135 = v22;
  }
  while ( v22 < 2 );
  v57 = v142;
  v58 = 0;
  v59 = 2;
  v60 = 0xFFFFFF;
  if ( v21 > 2 )
  {
    v61 = a5;
    while ( 1 )
    {
      v62 = v138;
      if ( (int)v57 - (int)v138 + 6 > v61 )
        return 0;
      v63 = 3 * v59;
      v64 = &v19[12 * v59];
      switch ( v64[8] )
      {
        case 1u:
        case 2u:
          v69 = *((_DWORD *)v64 + 1);
          if ( v69 > 0x1F )
          {
            if ( v69 > 0x11F )
            {
              *v57 = -16;
              *(_WORD *)(v57 + 1) = v69;
              v57 += 3;
            }
            else
            {
              *v57 = 0;
              v57[1] = v69 - 32;
              v57 += 2;
            }
          }
          else
          {
            *v57++ = v69;
          }
          if ( (unsigned int)CallbackContext <= 5 )
            goto LABEL_191;
          v70 = byte_1801B484D;
          v122 = *((_DWORD *)v64 + 1);
          v128 = "BG_RUN %u";
          goto LABEL_190;
        case 3u:
          v63 = *(_DWORD *)v64;
          v71 = *((_DWORD *)v64 + 1);
          if ( v60 == *(_DWORD *)v64 )
          {
            if ( v71 > 0x1F )
            {
              if ( v71 > 0x11F )
              {
                *v57 = -15;
                *(_WORD *)(v57 + 1) = v71;
                v57 += 3;
              }
              else
              {
                *v57 = 32;
                v57[1] = v71 - 32;
                v57 += 2;
              }
            }
            else
            {
              *v57++ = v71 | 0x20;
            }
            if ( (unsigned int)CallbackContext > 5 )
            {
              v70 = byte_1801B47E9;
              v122 = *((_DWORD *)v64 + 1);
              v128 = "FG_RUN %u";
              goto LABEL_190;
            }
          }
          else
          {
            v60 = *(_DWORD *)v64;
            if ( v71 > 0xF )
            {
              if ( v71 > 0x10F )
              {
                *v57 = -10;
                *(_WORD *)(v57 + 1) = v71;
                v72 = v57 + 3;
              }
              else
              {
                *v57 = -64;
                v57[1] = v71 - 16;
                v72 = v57 + 2;
              }
            }
            else
            {
              *v57 = v71 | 0xC0;
              v72 = v57 + 1;
            }
            v72[2] = v63;
            v73 = v63 >> 8;
            v63 >>= 16;
            v72[1] = v73;
            *v72 = v63;
            v57 = v72 + 3;
            if ( (unsigned int)CallbackContext > 5 )
            {
              v70 = byte_1801B481B;
              v122 = *((_DWORD *)v64 + 1);
              v128 = "SET_FG_FG_RUN %u";
LABEL_190:
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                v63,
                (_DWORD)v70,
                (_DWORD)v19,
                (_DWORD)v62,
                (__int64)&v128,
                (__int64)&v122);
              v21 = v121;
              v19 = (unsigned __int8 *)v126;
            }
          }
LABEL_191:
          v58 = (unsigned int)(v58 + *((_DWORD *)v64 + 1) + 2 * *((_DWORD *)v64 + 1));
          goto LABEL_260;
        case 4u:
          v103 = *((_DWORD *)v64 + 1);
          if ( v103 > 0x1F )
          {
            if ( v103 > 0x11F )
            {
              *v57 = -13;
              *(_WORD *)(v57 + 1) = v103;
              v104 = v57 + 3;
            }
            else
            {
              *v57 = 96;
              v57[1] = v103 - 32;
              v104 = v57 + 2;
            }
          }
          else
          {
            *v57 = v103 | 0x60;
            v104 = v57 + 1;
          }
          if ( (unsigned int)CallbackContext > 5 )
          {
            v122 = *((_DWORD *)v64 + 1);
            v128 = "COLOR_RUN %u";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              v63,
              (unsigned int)&byte_1801B46DF,
              (_DWORD)v19,
              (_DWORD)v62,
              (__int64)&v128,
              (__int64)&v122);
          }
          v105 = v136[v58];
          v106 = v136[v58 + 1];
          v104[2] = v136[v58 + 2];
          v104[1] = v106;
          *v104 = v105;
          v57 = v104 + 3;
          v58 = (unsigned int)(v58 + *((_DWORD *)v64 + 1) + 2 * *((_DWORD *)v64 + 1));
          goto LABEL_258;
        case 5u:
          v107 = *((_DWORD *)v64 + 1) >> 1;
          if ( v107 > 0xF )
          {
            if ( v107 > 0x10F )
            {
              *v57 = -8;
              *(_WORD *)(v57 + 1) = v107;
              v108 = v57 + 3;
            }
            else
            {
              *v57 = -32;
              v57[1] = v107 - 16;
              v108 = v57 + 2;
            }
          }
          else
          {
            *v57 = v107 | 0xE0;
            v108 = v57 + 1;
          }
          if ( (unsigned int)CallbackContext > 5 )
          {
            v122 = *((_DWORD *)v64 + 1);
            v128 = "DITHERED_RUN %u";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              v63,
              (unsigned int)byte_1801B46AD,
              (_DWORD)v19,
              (_DWORD)v62,
              (__int64)&v128,
              (__int64)&v122);
            LODWORD(v62) = (_DWORD)v138;
          }
          if ( (int)v108 - (int)v62 + 6 > v61 )
            return 0;
          v109 = &v136[(unsigned int)v58];
          v110 = *v109;
          v111 = v109[1];
          v108[2] = v109[2];
          v108[1] = v111;
          *v108 = v110;
          v112 = v109[3];
          v113 = v109[4];
          v108[5] = v109[5];
          v108[4] = v113;
          v108[3] = v112;
          v57 = v108 + 6;
          v58 = (unsigned int)(v58 + *((_DWORD *)v64 + 1) + 2 * *((_DWORD *)v64 + 1));
          goto LABEL_258;
        case 6u:
          v74 = *((_DWORD *)v64 + 1);
          if ( (__int64)&v57[((unsigned __int64)(v74 + 7) >> 3) - (_QWORD)v138 + 6] > v61 )
            return 0;
          v75 = *(_DWORD *)v64;
          if ( v60 != *(_DWORD *)v64 )
          {
            v60 = *(_DWORD *)v64;
            if ( (v74 & 7) == 0 && v74 <= 0x78 )
            {
              *v57 = (v74 >> 3) | 0xD0;
              v76 = v57 + 1;
              goto LABEL_216;
            }
            if ( v74 > 0xFF )
            {
              *v57 = -9;
              *(_WORD *)(v57 + 1) = v74;
              v76 = v57 + 3;
LABEL_216:
              v76[2] = v75;
              v76[1] = BYTE1(v75);
              *v76 = BYTE2(v75);
              v57 = v76 + 3;
            }
            else if ( v74 >= 2 )
            {
              *v57 = -48;
              v57[1] = v74 - 1;
              v76 = v57 + 2;
              goto LABEL_216;
            }
            if ( (unsigned int)CallbackContext > 5 )
            {
              v123 = *((_DWORD *)v64 + 1);
              v128 = "SET_FG_FG_BG %u, fgPel %06lx";
              v122 = v75;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                v75,
                (unsigned int)qword_1801B47B0,
                (_DWORD)v19,
                (_DWORD)v62,
                (__int64)&v128,
                (__int64)&v123,
                (__int64)&v122);
            }
            j = v134;
            if ( v74 >= 8 )
            {
              do
              {
                *v57 = 0;
                v78 = 0;
                if ( (unsigned __int8)j[v58 + 2] | (((unsigned __int8)j[v58 + 1] | ((unsigned __int8)j[v58] << 8)) << 8) )
                {
                  *v57 = 1;
                  v78 = 1;
                }
                if ( (unsigned __int8)j[v58 + 5]
                   | (((unsigned __int8)j[v58 + 4] | ((unsigned __int8)j[v58 + 3] << 8)) << 8) )
                {
                  v78 |= 2u;
                  *v57 = v78;
                }
                if ( (unsigned __int8)j[v58 + 8]
                   | (((unsigned __int8)j[v58 + 7] | ((unsigned __int8)j[v58 + 6] << 8)) << 8) )
                {
                  v78 |= 4u;
                  *v57 = v78;
                }
                if ( (unsigned __int8)j[v58 + 11]
                   | (((unsigned __int8)j[v58 + 10] | ((unsigned __int8)j[v58 + 9] << 8)) << 8) )
                {
                  v78 |= 8u;
                  *v57 = v78;
                }
                if ( (unsigned __int8)j[v58 + 14]
                   | ((((unsigned __int8)j[v58 + 12] << 8) | (unsigned __int8)j[v58 + 13]) << 8) )
                {
                  v78 |= 0x10u;
                  *v57 = v78;
                }
                if ( (unsigned __int8)j[v58 + 17]
                   | ((((unsigned __int8)j[v58 + 15] << 8) | (unsigned __int8)j[v58 + 16]) << 8) )
                {
                  v78 |= 0x20u;
                  *v57 = v78;
                }
                if ( (unsigned __int8)j[v58 + 20]
                   | (((unsigned __int8)j[v58 + 19] | ((unsigned __int8)j[v58 + 18] << 8)) << 8) )
                {
                  v78 |= 0x40u;
                  *v57 = v78;
                }
                v79 = (unsigned __int8)j[v58 + 23]
                    | (((unsigned __int8)j[v58 + 22] | ((unsigned __int8)j[v58 + 21] << 8)) << 8);
                if ( v79 )
                  *v57 = v78 | 0x80;
                if ( (unsigned int)CallbackContext > 5 )
                {
                  v120[0] = *v57;
                  v128 = "Encoded as %08lx";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<1>>(
                    v79,
                    (unsigned int)byte_1801B4785,
                    (_DWORD)v19,
                    (_DWORD)v62,
                    (__int64)&v128,
                    (__int64)v120);
                }
                ++v57;
                v58 = (unsigned int)(v58 + 24);
                v74 -= 8;
              }
              while ( v74 >= 8 );
              v61 = a5;
            }
            goto LABEL_240;
          }
          if ( v74 == 8 )
          {
            v83 = (unsigned __int8 *)&v134[(unsigned int)v58];
            v84 = v83 + 3;
            v85 = (v83[2] | (((*v83 << 8) | v83[1]) << 8)) != 0;
            v86 = (v83[5] | ((v83[4] | (v83[3] << 8)) << 8)) == 0;
            v87 = v85 | 2;
            v88 = v83[6];
            if ( v86 )
              v87 = v85;
            v89 = v87;
            v90 = v87 | 4;
            if ( !(v84[5] | ((v84[4] | (v88 << 8)) << 8)) )
              v90 = v89;
            v91 = v90;
            v92 = v90 | 8;
            if ( !(v84[8] | ((v84[7] | (v84[6] << 8)) << 8)) )
              v92 = v91;
            v93 = v92;
            v94 = v92 | 0x10;
            if ( !(v84[11] | ((v84[10] | (v84[9] << 8)) << 8)) )
              v94 = v93;
            v95 = v94;
            v96 = v94 | 0x20;
            if ( !(v84[14] | ((v84[13] | (v84[12] << 8)) << 8)) )
              v96 = v95;
            v97 = v96;
            v98 = v96 | 0x40;
            if ( !(v84[17] | ((v84[16] | (v84[15] << 8)) << 8)) )
              v98 = v97;
            v99 = v98 | 0x80;
            if ( !(v84[20] | ((v84[19] | (v84[18] << 8)) << 8)) )
              v99 = v98;
            if ( v99 == 3 )
            {
              *v57++ = -7;
              if ( (unsigned int)CallbackContext > 5 )
              {
                v148 = 15;
                v147 = "SPECIAL FGBG_1";
                v100 = &v141;
                *(_DWORD *)&v141.Level = 5;
                UserData.Ptr = (ULONGLONG)off_1801E7010;
                *(_DWORD *)&v141.Id = 184549376;
                v141.Keyword = 0;
                UserData.Size = *(unsigned __int16 *)off_1801E7010;
                v101 = (__int16 *)&byte_1801B476F;
LABEL_285:
                v144 = v101;
                UserData.Reserved = 2;
                v145 = 21;
                v146 = 1;
                v122 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
                EventWriteTransfer(RegHandle, v100, 0, 0, 3u, &UserData);
              }
            }
            else
            {
              if ( v99 != 5 )
              {
                *v57 = 65;
                v57[1] = v99;
                v57 += 2;
                v58 = (unsigned int)(v58 + 24);
                goto LABEL_258;
              }
              *v57++ = -6;
              if ( (unsigned int)CallbackContext > 5 )
              {
                v148 = 15;
                v147 = "SPECIAL FGBG_2";
                v100 = &v137;
                *(_DWORD *)&v137.Level = 5;
                UserData.Ptr = (ULONGLONG)off_1801E7010;
                *(_DWORD *)&v137.Id = 184549376;
                v137.Keyword = 0;
                UserData.Size = *(unsigned __int16 *)off_1801E7010;
                v101 = &word_1801B474E;
                goto LABEL_285;
              }
            }
            v58 = (unsigned int)(v58 + 24);
            goto LABEL_258;
          }
          if ( (v74 & 7) != 0 || v74 > 0xF8 )
          {
            if ( v74 > 0xFF )
            {
              *v57 = -14;
              *(_WORD *)(v57 + 1) = v74;
              v57 += 3;
            }
            else
            {
              *v57 = 64;
              v57[1] = v74 - 1;
              v57 += 2;
            }
          }
          else
          {
            *v57++ = (v74 >> 3) | 0x40;
          }
          if ( (unsigned int)CallbackContext > 5 )
          {
            v122 = *((_DWORD *)v64 + 1);
            v128 = "FG_BG %u";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              v75,
              (unsigned int)byte_1801B4711,
              (_DWORD)v19,
              (_DWORD)v62,
              (__int64)&v128,
              (__int64)&v122);
          }
          for ( j = v134; v74 >= 8; v74 -= 8 )
          {
            *v57 = 0;
            v102 = 0;
            if ( (unsigned __int8)j[v58 + 2] | ((((unsigned __int8)j[v58] << 8) | (unsigned __int8)j[v58 + 1]) << 8) )
            {
              *v57 = 1;
              v102 = 1;
            }
            if ( (unsigned __int8)j[v58 + 5] | (((unsigned __int8)j[v58 + 4] | ((unsigned __int8)j[v58 + 3] << 8)) << 8) )
            {
              v102 |= 2u;
              *v57 = v102;
            }
            if ( (unsigned __int8)j[v58 + 8] | (((unsigned __int8)j[v58 + 7] | ((unsigned __int8)j[v58 + 6] << 8)) << 8) )
            {
              v102 |= 4u;
              *v57 = v102;
            }
            if ( (unsigned __int8)j[v58 + 11]
               | ((((unsigned __int8)j[v58 + 9] << 8) | (unsigned __int8)j[v58 + 10]) << 8) )
            {
              v102 |= 8u;
              *v57 = v102;
            }
            if ( (unsigned __int8)j[v58 + 14]
               | ((((unsigned __int8)j[v58 + 12] << 8) | (unsigned __int8)j[v58 + 13]) << 8) )
            {
              v102 |= 0x10u;
              *v57 = v102;
            }
            if ( (unsigned __int8)j[v58 + 17]
               | (((unsigned __int8)j[v58 + 16] | ((unsigned __int8)j[v58 + 15] << 8)) << 8) )
            {
              v102 |= 0x20u;
              *v57 = v102;
            }
            if ( (unsigned __int8)j[v58 + 20]
               | (((unsigned __int8)j[v58 + 19] | ((unsigned __int8)j[v58 + 18] << 8)) << 8) )
            {
              v102 |= 0x40u;
              *v57 = v102;
            }
            if ( (unsigned __int8)j[v58 + 23]
               | ((((unsigned __int8)j[v58 + 21] << 8) | (unsigned __int8)j[v58 + 22]) << 8) )
            {
              *v57 = v102 | 0x80;
            }
            ++v57;
            v58 = (unsigned int)(v58 + 24);
          }
LABEL_240:
          if ( v74 )
          {
            *v57 = 0;
            v80 = 0;
            v81 = (unsigned __int8 *)&j[(unsigned int)v58];
            if ( v81[2] | (((*v81 << 8) | v81[1]) << 8) )
            {
              *v57 = 1;
              v80 = 1;
            }
            if ( v81[5] | (((v81[3] << 8) | v81[4]) << 8) )
            {
              v80 |= 2u;
              *v57 = v80;
            }
            if ( v81[8] | (((v81[6] << 8) | v81[7]) << 8) )
            {
              v80 |= 4u;
              *v57 = v80;
            }
            if ( v81[11] | (((v81[9] << 8) | v81[10]) << 8) )
            {
              v80 |= 8u;
              *v57 = v80;
            }
            if ( v81[14] | (((v81[12] << 8) | v81[13]) << 8) )
            {
              v80 |= 0x10u;
              *v57 = v80;
            }
            if ( v81[17] | (((v81[15] << 8) | v81[16]) << 8) )
            {
              v80 |= 0x20u;
              *v57 = v80;
            }
            if ( v81[20] | (((v81[18] << 8) | v81[19]) << 8) )
            {
              v80 |= 0x40u;
              *v57 = v80;
            }
            if ( v81[23] | (((v81[21] << 8) | v81[22]) << 8) )
            {
              v80 |= 0x80u;
              *v57 = v80;
            }
            *v57 = v80 & ((1 << v74) - 1);
            v58 = (_DWORD)v58 + v74 + 2 * v74;
            ++v57;
          }
LABEL_258:
          v19 = (unsigned __int8 *)v126;
LABEL_259:
          v21 = v121;
LABEL_260:
          if ( ++v59 >= v21 )
            return (unsigned int)((_DWORD)v57 - (_DWORD)v138);
          break;
        case 7u:
          v114 = *((_DWORD *)v64 + 1);
          v115 = v136;
          if ( v114 != 1 )
            goto LABEL_338;
          LODWORD(v19) = (unsigned __int8)v136[v58 + 2]
                       | ((((unsigned __int8)v136[v58] << 8) | (unsigned __int8)v136[v58 + 1]) << 8);
          if ( !(_DWORD)v19 )
          {
            *v57 = -2;
            v58 = (unsigned int)(v58 + 3);
            ++v57;
            if ( (unsigned int)CallbackContext > 5 )
            {
              v148 = 11;
              v147 = "CODE_BLACK";
              *(_DWORD *)&v140.Level = 5;
              UserData.Ptr = (ULONGLONG)off_1801E7010;
              *(_DWORD *)&v140.Id = 184549376;
              v140.Keyword = 0;
              UserData.Size = *(unsigned __int16 *)off_1801E7010;
              v144 = (__int16 *)&byte_1801B4697;
              v146 = 1;
              UserData.Reserved = 2;
              v145 = 21;
              v122 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
              EventWriteTransfer(RegHandle, &v140, 0, 0, 3u, &UserData);
            }
            goto LABEL_258;
          }
          if ( (_DWORD)v19 == 0xFFFFFF )
          {
            *v57 = -3;
            v58 = (unsigned int)(v58 + 3);
            ++v57;
            if ( (unsigned int)CallbackContext > 5 )
            {
              v148 = 11;
              EventDescriptor.Keyword = 0;
              v147 = "CODE_WHITE";
              *(_DWORD *)&EventDescriptor.Level = 5;
              UserData.Ptr = (ULONGLONG)off_1801E7010;
              *(_DWORD *)&EventDescriptor.Id = 184549376;
              UserData.Size = *(unsigned __int16 *)off_1801E7010;
              v144 = &word_1801B4676;
              UserData.Reserved = 2;
              v145 = 21;
              v146 = 1;
              v122 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
              EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
            }
            goto LABEL_258;
          }
LABEL_338:
          if ( v114 > 0x1F )
          {
            if ( v114 > 0x11F )
            {
              *v57 = -12;
              *(_WORD *)(v57 + 1) = v114;
              v116 = v57 + 3;
            }
            else
            {
              *v57 = 0x80;
              v57[1] = v114 - 32;
              v116 = v57 + 2;
            }
          }
          else
          {
            *v57 = v114 | 0x80;
            v116 = v57 + 1;
          }
          if ( (unsigned int)CallbackContext > 5 )
          {
            v122 = *((_DWORD *)v64 + 1);
            v128 = "COLOR_IMAGE %u";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              v63,
              (unsigned int)byte_1801B4639,
              (_DWORD)v19,
              (_DWORD)v62,
              (__int64)&v128,
              (__int64)&v122);
            v62 = v138;
          }
          if ( (__int64)&v116[(unsigned int)(3 * *((_DWORD *)v64 + 1)) - (_QWORD)v62] > v61 )
            return 0;
          memcpy_0(v116, &v115[(unsigned int)v58], (unsigned int)(3 * *((_DWORD *)v64 + 1)));
          v19 = (unsigned __int8 *)v126;
          v117 = 3 * *(_DWORD *)(v126 + 12LL * v59 + 4);
          v57 = &v116[v117];
          v58 = v117 + (unsigned int)v58;
          goto LABEL_259;
        default:
          if ( (unsigned int)CallbackContext <= 5 )
            goto LABEL_260;
          v120[0] = v64[8];
          v128 = "Invalid run type %u";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<1>>(
            v63,
            (unsigned int)byte_1801B4609,
            (_DWORD)v19,
            (_DWORD)v138,
            (__int64)&v128,
            (__int64)v120);
          goto LABEL_258;
      }
    }
  }
  return (unsigned int)((_DWORD)v57 - (_DWORD)v138);
}

```

## disassembly

```asm
0x1800542e0  mov     r11, rsp
0x1800542e3  push    rbp
0x1800542e4  push    rsi
0x1800542e5  push    rdi
0x1800542e6  push    r12
0x1800542e8  push    r13
0x1800542ea  lea     rbp, [rsp-80h]
0x1800542ef  sub     rsp, 180h
0x1800542f6  mov     rax, cs:__security_cookie
0x1800542fd  xor     rax, rsp
0x180054300  mov     [rbp+0A0h+var_40], rax
0x180054304  mov     rsi, [rbp+0A0h+arg_28]
0x18005430b  mov     r12, rcx
0x18005430e  mov     r13d, r9d
0x180054311  mov     edi, r8d
0x180054314  mov     r9, [rbp+0A0h+arg_38]
0x18005431b  mov     [rbp+0A0h+var_100], rcx
0x18005431f  xor     ecx, ecx
0x180054321  mov     [rbp+0A0h+var_118], r13d
0x180054325  mov     [rsp+1A0h+var_158], r8d
0x18005432a  mov     [rbp+0A0h+var_E8], rdx
0x18005432e  mov     [rbp+0A0h+var_110], rsi
0x180054332  mov     [rsp+1A0h+var_148], r9
0x180054337  mov     [rbp+0A0h+var_B0], rdx
0x18005433b  cmp     r8d, r13d
0x18005433e  jb      loc_180056213
0x180054344  mov     eax, r13d
0x180054347  or      eax, r8d
0x18005434a  test    al, 3
0x18005434c  jnz     loc_180056213
0x180054352  cmp     r8d, [rbp+0A0h+arg_30]
0x180054359  ja      loc_180056213
0x18005435f  mov     eax, 0AAAAAAABh
0x180054364  mul     edi
0x180054366  shr     edx, 1
0x180054368  lea     ecx, [rdx+rdx*2]
0x18005436b  cmp     r8d, ecx
0x18005436e  jnz     loc_180056211
0x180054374  mov     [r11+18h], rbx
0x180054378  mov     r8d, r13d; Size
0x18005437b  mov     [r11-30h], r14
0x18005437f  mov     rdx, r12; Src
0x180054382  mov     [r11-38h], r15
0x180054386  xor     r14b, r14b
0x180054389  xor     r15b, r15b
0x18005438c  mov     [rsp+1A0h+var_128], 0FFFFFFh
0x180054394  mov     rcx, rsi; void *
0x180054397  mov     [rsp+1A0h+var_160], r15b
0x18005439c  mov     [rsp+1A0h+var_140], 0FFFFFFh
0x1800543a4  mov     ebx, r13d
0x1800543a7  mov     [rsp+1A0h+var_15F], r14b
0x1800543ac  call    memcpy_0
0x1800543b1  mov     r8d, edi
0x1800543b4  lea     rcx, [r12+r13]
0x1800543b8  sub     r8d, r13d
0x1800543bb  lea     rdx, [rsi+r13]
0x1800543bf  cmp     r8d, 8
0x1800543c3  jb      short loc_1800543FD
0x1800543c5  nop     word ptr [rax+rax+00000000h]
0x1800543d0  mov     rax, rcx
0x1800543d3  add     r8d, 0FFFFFFF8h
0x1800543d7  sub     rax, rbx
0x1800543da  mov     eax, [rax]
0x1800543dc  xor     eax, [rcx]
0x1800543de  mov     [rdx], eax
0x1800543e0  lea     rax, [rcx+4]
0x1800543e4  sub     rax, rbx
0x1800543e7  mov     eax, [rax]
0x1800543e9  xor     eax, [rcx+4]
0x1800543ec  add     rcx, 8
0x1800543f0  mov     [rdx+4], eax
0x1800543f3  add     rdx, 8
0x1800543f7  cmp     r8d, 8
0x1800543fb  jnb     short loc_1800543D0
0x1800543fd  test    r8d, r8d
0x180054400  jz      short loc_18005440E
0x180054402  mov     rax, rcx
0x180054405  sub     rax, rbx
0x180054408  mov     eax, [rax]
0x18005440a  xor     eax, [rcx]
0x18005440c  mov     [rdx], eax
0x18005440e  mov     r8, [rsp+1A0h+var_148]
0x180054413  xor     r12d, r12d
0x180054416  mov     edx, 2
0x18005441b  mov     [rsp+1A0h+var_14C], r12d
0x180054420  xor     eax, eax
0x180054422  mov     [rsp+1A0h+var_130], 1
0x180054427  mov     [rsp+1A0h+var_15C], edx
0x18005442b  mov     r11d, r13d
0x18005442e  mov     [r8+8], r12b
0x180054432  mov     [r8+14h], r12b
0x180054436  mov     [rsp+1A0h+var_150], r13d
0x18005443b  mov     [rbp+0A0h+var_108], eax
0x18005443e  xchg    ax, ax
0x180054440  cmp     r12d, r11d
0x180054443  jnb     loc_180054FE7
0x180054449  nop     dword ptr [rax+00000000h]
0x180054450  cmp     edx, 2000h
0x180054456  jnb     loc_18005620A
0x18005445c  lea     eax, [r12+12h]
0x180054461  cmp     eax, r11d
0x180054464  jnb     loc_180054DFB
0x18005446a  nop     word ptr [rax+rax+00h]
0x180054470  mov     r10d, r12d
0x180054473  movzx   eax, byte ptr [rsi+r10+1]
0x180054479  lea     rbx, [rsi+r10]
0x18005447d  movzx   r13d, byte ptr [rbx]
0x180054481  shl     r13d, 8
0x180054485  or      r13d, eax
0x180054488  movzx   eax, byte ptr [rbx+2]
0x18005448c  shl     r13d, 8
0x180054490  or      r13d, eax
0x180054493  jnz     loc_1800545F0
0x180054499  lea     eax, [r12+3]
0x18005449e  cmp     eax, r11d
0x1800544a1  jnb     loc_1800545D7
0x1800544a7  movzx   eax, byte ptr [rbx+3]
0x1800544ab  movzx   ecx, byte ptr [rbx+4]
0x1800544af  shl     eax, 8
0x1800544b2  or      ecx, eax
0x1800544b4  movzx   eax, byte ptr [rbx+5]
0x1800544b8  shl     ecx, 8
0x1800544bb  or      ecx, eax
0x1800544bd  jnz     loc_1800545D7
0x1800544c3  lea     eax, [r12+6]
0x1800544c8  cmp     eax, r11d
0x1800544cb  jnb     loc_1800545C0
0x1800544d1  movzx   eax, byte ptr [rbx+6]
0x1800544d5  movzx   ecx, byte ptr [rbx+7]
0x1800544d9  shl     eax, 8
0x1800544dc  or      ecx, eax
0x1800544de  movzx   eax, byte ptr [rbx+8]
0x1800544e2  shl     ecx, 8
0x1800544e5  or      ecx, eax
0x1800544e7  jnz     loc_1800545C0
0x1800544ed  lea     eax, [r12+9]
0x1800544f2  cmp     eax, r11d
0x1800544f5  jnb     loc_1800545A0
0x1800544fb  movzx   eax, byte ptr [rbx+0Ah]
0x1800544ff  movzx   ecx, byte ptr [rbx+9]
0x180054503  shl     ecx, 8
0x180054506  or      ecx, eax
0x180054508  movzx   eax, byte ptr [rbx+0Bh]
0x18005450c  shl     ecx, 8
0x18005450f  or      ecx, eax
0x180054511  jnz     loc_1800545A0
0x180054517  movzx   eax, byte ptr [rbx+9]
0x18005451b  lea     rdx, [rbx+0Ch]
0x18005451f  movzx   r8d, byte ptr [rdx-2]
0x180054524  mov     r9d, r11d
0x180054527  shl     eax, 8
0x18005452a  sub     r9d, r12d
0x18005452d  or      r8d, eax
0x180054530  add     r9, 0FFFFFFFFFFFFFFF4h
0x180054534  movzx   eax, byte ptr [rdx-1]
0x180054538  add     r9, rbx
0x18005453b  shl     r8d, 8
0x18005453f  mov     edi, 4
0x180054544  or      r8d, eax
0x180054547  lea     rax, [rdx+2]
0x18005454b  cmp     rax, r9
0x18005454e  jnb     short loc_18005457F
0x180054550  movzx   eax, byte ptr [rdx]
0x180054553  movzx   ecx, byte ptr [rdx+1]
0x180054557  shl     eax, 8
0x18005455a  or      ecx, eax
0x18005455c  movzx   eax, byte ptr [rdx+2]
0x180054560  shl     ecx, 8
0x180054563  or      ecx, eax
0x180054565  cmp     ecx, r8d
0x180054568  jnz     short loc_180054579
0x18005456a  add     rdx, 3
0x18005456e  inc     edi
0x180054570  lea     rax, [rdx+2]
0x180054574  cmp     rax, r9
0x180054577  jb      short loc_180054550
0x180054579  xor     esi, esi
0x18005457b  test    edi, edi
0x18005457d  jz      short loc_180054592
0x18005457f  mov     r15b, 1
0x180054582  mov     esi, edi
0x180054584  mov     [rsp+1A0h+var_160], r15b
0x180054589  cmp     edi, 14h
0x18005458c  jnb     loc_1800546CD
0x180054592  test    r14b, r14b
0x180054595  jz      loc_180054E77
0x18005459b  jmp     loc_180054713
0x1800545a0  mov     r15b, 1
0x1800545a3  mov     esi, 3
0x1800545a8  mov     [rsp+1A0h+var_160], r15b
0x1800545ad  test    r14b, r14b
0x1800545b0  jnz     loc_180054711
0x1800545b6  mov     r13d, [rsp+1A0h+var_140]
0x1800545bb  jmp     loc_1800546DB
0x1800545c0  mov     r15b, 1
0x1800545c3  mov     esi, 2
0x1800545c8  mov     [rsp+1A0h+var_160], r15b
0x1800545cd  test    r14b, r14b
0x1800545d0  jz      short loc_1800545B6
0x1800545d2  jmp     loc_180054711
0x1800545d7  xor     edi, edi
0x1800545d9  mov     r15b, 1
0x1800545dc  mov     [rsp+1A0h+var_160], r15b
0x1800545e1  mov     esi, 1
0x1800545e6  test    r14b, r14b
0x1800545e9  jz      short loc_1800545B6
0x1800545eb  jmp     loc_180054713
0x1800545f0  movzx   eax, byte ptr [rbx+3]
0x1800545f4  movzx   ecx, byte ptr [rbx+4]
0x1800545f8  shl     eax, 8
0x1800545fb  or      ecx, eax
0x1800545fd  movzx   eax, byte ptr [rbx+5]
0x180054601  shl     ecx, 8
0x180054604  or      ecx, eax
0x180054606  cmp     r13d, ecx
0x180054609  jnz     loc_18005470F
0x18005460f  movzx   eax, byte ptr [rbx+6]
0x180054613  movzx   ecx, byte ptr [rbx+7]
0x180054617  shl     eax, 8
0x18005461a  or      ecx, eax
0x18005461c  movzx   eax, byte ptr [rbx+8]
0x180054620  shl     ecx, 8
0x180054623  or      ecx, eax
0x180054625  cmp     r13d, ecx
0x180054628  jnz     loc_18005470F
0x18005462e  movzx   eax, byte ptr [rbx+0Ah]
0x180054632  xor     esi, esi
0x180054634  movzx   ecx, byte ptr [rbx+9]
0x180054638  shl     ecx, 8
0x18005463b  or      ecx, eax
0x18005463d  movzx   eax, byte ptr [rbx+0Bh]
0x180054641  shl     ecx, 8
0x180054644  or      ecx, eax
0x180054646  cmp     r13d, ecx
0x180054649  jnz     loc_180054711
0x18005464f  movzx   eax, byte ptr [rbx+9]
0x180054653  lea     rdx, [rbx+0Ch]
0x180054657  movzx   r8d, byte ptr [rdx-2]
0x18005465c  mov     r9d, r11d
0x18005465f  shl     eax, 8
0x180054662  sub     r9d, r12d
0x180054665  or      r8d, eax
0x180054668  add     r9, 0FFFFFFFFFFFFFFF4h
0x18005466c  movzx   eax, byte ptr [rdx-1]
0x180054670  add     r9, rbx
0x180054673  shl     r8d, 8
0x180054677  mov     edi, 4
0x18005467c  or      r8d, eax
0x18005467f  lea     rax, [rdx+2]
0x180054683  cmp     rax, r9
0x180054686  jnb     loc_180054713
0x18005468c  nop     dword ptr [rax+00h]
0x180054690  movzx   eax, byte ptr [rdx+1]
0x180054694  movzx   ecx, byte ptr [rdx]
0x180054697  shl     ecx, 8
0x18005469a  or      ecx, eax
0x18005469c  movzx   eax, byte ptr [rdx+2]
0x1800546a0  shl     ecx, 8
0x1800546a3  or      ecx, eax
0x1800546a5  cmp     ecx, r8d
0x1800546a8  jnz     short loc_1800546B9
0x1800546aa  add     rdx, 3
0x1800546ae  inc     edi
0x1800546b0  lea     rax, [rdx+2]
0x1800546b4  cmp     rax, r9
0x1800546b7  jb      short loc_180054690
0x1800546b9  cmp     edi, 5
0x1800546bc  jbe     short loc_180054713
0x1800546be  mov     r15b, 3
0x1800546c1  mov     esi, edi
0x1800546c3  mov     [rsp+1A0h+var_160], r15b
0x1800546c8  cmp     edi, 14h
0x1800546cb  jb      short loc_180054713
0x1800546cd  mov     r13d, [rsp+1A0h+var_140]
0x1800546d2  mov     edx, [rsp+1A0h+var_15C]
0x1800546d6  mov     r8, [rsp+1A0h+var_148]
0x1800546db  xor     al, al
0x1800546dd  mov     [rsp+1A0h+var_15F], al
0x1800546e1  cmp     r15b, 3
0x1800546e5  jnz     loc_180054E82
0x1800546eb  movzx   eax, byte ptr [rbx+1]
0x1800546ef  movzx   r13d, byte ptr [rbx]
0x1800546f3  shl     r13d, 8
0x1800546f7  or      r13d, eax
0x1800546fa  movzx   eax, byte ptr [rbx+2]
0x1800546fe  shl     r13d, 8
0x180054702  or      r13d, eax
0x180054705  mov     [rsp+1A0h+var_128], r13d
0x18005470a  jmp     loc_180054E94
0x18005470f  xor     esi, esi
0x180054711  xor     edi, edi
0x180054713  mov     rdx, [rbp+0A0h+var_100]
0x180054717  add     rdx, r10
0x18005471a  movzx   r15d, byte ptr [rdx]
0x18005471e  movzx   eax, byte ptr [rdx+6]
0x180054722  mov     r9d, r15d
0x180054725  movzx   r14d, byte ptr [rdx+1]
0x18005472a  movzx   ecx, byte ptr [rdx+7]
0x18005472e  movzx   r12d, byte ptr [rdx+2]
0x180054733  shl     r9d, 8
  ... truncated ...
```
