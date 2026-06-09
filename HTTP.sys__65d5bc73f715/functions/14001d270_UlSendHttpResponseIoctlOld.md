# UlSendHttpResponseIoctlOld

- ea: `0x14001d270`
- end: `0x14001f2b5`
- name: `UlSendHttpResponseIoctlOld`
- size: `8261`
- prototype: `__int64 __fastcall(PIRP Irp, __int64)`
- caller_count: `1`
- callee_count: `49`
- tags: `broker_com_uri`

## callers

- `0x14009ee50`

## callees

- `0x14000a350`
- `0x14000bfb0`
- `0x140019f88`
- `0x14001a360`
- `0x14001a794`
- `0x14001c8b4`
- `0x14001cb08`
- `0x14001ceac`
- `0x14001d270`
- `0x14001f2c0`
- `0x14001f4ec`
- `0x14001f9f4`
- `0x140020290`
- `0x140022610`
- `0x140033830`
- `0x1400354a0`
- `0x140035a50`
- `0x140039340`
- `0x1400474d0`
- `0x140049bc0`
- `0x140062bd0`
- `0x1400829a0`
- `0x1400a69ec`
- `0x1400a7b50`
- `0x1400aa0f8`
- `0x1400b0a28`
- `0x1400b1acc`
- `0x1400b379c`
- `0x1400c91f0`
- `0x1400caf44`
- `0x1400d3cd0`
- `0x1400e35c0`
- `0x1400e36dc`
- `0x1400fce98`
- `0x140167810`
- `0x140167840`
- `0x1401678f0`
- `0x140167c40`
- `0x1401c10e0`
- `0x1401c111c`
- `0x1401c3008`
- `0x1401c37f8`
- `0x1401c49c4`
- `0x1401c4a18`
- `0x1401cdb74`
- `0x1401cdbcc`
- `0x1401ce090`
- `0x1401d9f54`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14001e0e1`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001f0ff`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001e0e1`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001f0ff`
- `ntoskrnl!IofCompleteRequest` at `0x14001f286`
- `ntoskrnl!IofCompleteRequest` at `0x14001f286`
- `ntoskrnl!IoIs32bitProcess` at `0x14001d40a`
- `ntoskrnl!IoIs32bitProcess` at `0x14001d559`
- `ntoskrnl!IoIs32bitProcess` at `0x14001d40a`
- `ntoskrnl!IoIs32bitProcess` at `0x14001d559`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14001d4a6`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14001d4a6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001eaaf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001eaaf`
- `ntoskrnl!ExAllocatePool3` at `0x14001dca2`
- `ntoskrnl!ExAllocatePool3` at `0x14001dca2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f22e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f249`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f25f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f22e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f249`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f25f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001eaa3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001eaa3`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001ea49`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001ea49`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001ea29`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001ea29`

## pseudocode

```c
__int64 __fastcall UlSendHttpResponseIoctlOld(PIRP Irp, __int64 a2)
{
  PIRP v3; // r12
  void *v4; // rax
  __int64 RequestFromId; // rsi
  _QWORD *v6; // rbx
  unsigned __int64 v7; // rcx
  __int64 v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rdi
  signed int SendInfoOld; // edi
  __int64 v12; // rbx
  KPROCESSOR_MODE RequestorMode; // r15
  unsigned __int8 v14; // r13
  bool v15; // zf
  unsigned __int16 v16; // ax
  _OWORD *v17; // rdx
  int ChunkInfoOld; // eax
  __int16 v19; // r8d^2
  int v20; // eax
  char v21; // r15
  int v22; // ebx
  int v23; // ecx
  _WORD *v24; // rdi
  char v25; // r13
  __int64 v26; // r9
  int v27; // eax
  __int64 v28; // r8
  char v29; // bl
  __int64 v30; // rdx
  __int64 v31; // rcx
  int v32; // eax
  unsigned __int8 v33; // r15
  __int64 v34; // r12
  __int64 v35; // rbx
  __int64 v36; // rbx
  unsigned __int8 v37; // bl
  PVOID v38; // r15
  PIRP v39; // r13
  int v40; // eax
  __int64 v41; // r12
  unsigned __int16 UShortFromUser; // r13
  _WORD *v43; // r10
  unsigned __int16 v44; // bx
  _DWORD *Pool3; // rax
  _DWORD *v46; // r8
  char *v47; // rbx
  int ULongFromUser; // eax
  const void *v49; // rdx
  _DWORD *v50; // rbx
  char *v51; // rdx
  __int16 v52; // ax
  __int64 v53; // rbx
  __int16 v54; // ax
  unsigned int v55; // eax
  __int16 v56; // ax
  unsigned int v57; // eax
  __int16 v58; // ax
  int v59; // eax
  unsigned int v60; // eax
  unsigned __int64 v61; // rbx
  _DWORD *v62; // r13
  __int64 v63; // rax
  __int16 v64; // ax
  unsigned int v65; // eax
  __int16 v66; // ax
  unsigned int v67; // eax
  unsigned __int16 v68; // cx
  __int16 v69; // ax
  __int64 v70; // rax
  unsigned int v71; // eax
  __int64 v72; // r8
  unsigned __int64 v73; // rbx
  int v74; // eax
  unsigned int v75; // eax
  unsigned __int16 v76; // ax
  _DWORD *v77; // r13
  __int64 v78; // r15
  int v79; // eax
  _QWORD *v80; // rbx
  __int64 v81; // r9
  SIZE_T v82; // rdx
  char *v83; // rdx
  __int64 v84; // rdx
  char *v85; // rbx
  _DWORD *v86; // r13
  __int64 v87; // rax
  size_t v88; // r8
  __int16 v89; // ax
  int appended; // eax
  char v91; // al
  __int64 v92; // rax
  __int64 v93; // rdx
  __int64 v94; // r9
  int v95; // eax
  PIRP v96; // r15
  char v97; // di
  __int64 v98; // rbx
  int v99; // edx
  int v100; // ecx
  char v101; // r14
  unsigned __int16 v102; // dx
  int v103; // eax
  _QWORD *v104; // rax
  __int64 v106; // r8
  __int64 v107; // rdi
  unsigned int v108; // eax
  ULONG_PTR v109; // rdx
  int v110; // r12d
  _QWORD *v111; // rsi
  __int64 v112; // r15
  __int64 v113; // r9
  __int64 v114; // rbx
  __int64 v115; // [rsp+88h] [rbp-5D8h]
  int *v116; // [rsp+90h] [rbp-5D0h]
  int v117; // [rsp+A8h] [rbp-5B8h]
  __int64 v118; // [rsp+B8h] [rbp-5A8h]
  char v119; // [rsp+C0h] [rbp-5A0h]
  unsigned __int8 v120; // [rsp+E8h] [rbp-578h]
  char v121; // [rsp+E9h] [rbp-577h]
  unsigned __int16 v122; // [rsp+ECh] [rbp-574h]
  unsigned __int16 v123; // [rsp+ECh] [rbp-574h]
  unsigned __int16 v124; // [rsp+ECh] [rbp-574h]
  char v125; // [rsp+F0h] [rbp-570h] BYREF
  char v126; // [rsp+F1h] [rbp-56Fh]
  char v127; // [rsp+F2h] [rbp-56Eh] BYREF
  bool v128; // [rsp+F3h] [rbp-56Dh]
  PVOID v129; // [rsp+F8h] [rbp-568h]
  unsigned __int16 v130[2]; // [rsp+100h] [rbp-560h] BYREF
  int v131; // [rsp+104h] [rbp-55Ch]
  PIRP Irpa; // [rsp+108h] [rbp-558h]
  char v133; // [rsp+110h] [rbp-550h] BYREF
  BOOLEAN v134; // [rsp+111h] [rbp-54Fh]
  char v135; // [rsp+112h] [rbp-54Eh]
  char v136; // [rsp+113h] [rbp-54Dh]
  char v137; // [rsp+114h] [rbp-54Ch]
  char v138; // [rsp+115h] [rbp-54Bh]
  char v139; // [rsp+116h] [rbp-54Ah]
  __int16 v140; // [rsp+118h] [rbp-548h]
  char *v141; // [rsp+120h] [rbp-540h]
  int v142; // [rsp+128h] [rbp-538h]
  char v143; // [rsp+12Ch] [rbp-534h]
  __int64 v144; // [rsp+130h] [rbp-530h] BYREF
  unsigned __int16 v145; // [rsp+138h] [rbp-528h]
  int v146; // [rsp+13Ch] [rbp-524h]
  __int64 v147; // [rsp+140h] [rbp-520h] BYREF
  int v148; // [rsp+148h] [rbp-518h]
  char v149; // [rsp+14Ch] [rbp-514h]
  int v150; // [rsp+150h] [rbp-510h]
  __int64 v151; // [rsp+158h] [rbp-508h]
  __int128 v152; // [rsp+160h] [rbp-500h] BYREF
  int v153; // [rsp+170h] [rbp-4F0h]
  __int64 v154; // [rsp+178h] [rbp-4E8h]
  PVOID P; // [rsp+180h] [rbp-4E0h]
  void *Src[2]; // [rsp+188h] [rbp-4D8h] BYREF
  __int128 v157; // [rsp+198h] [rbp-4C8h]
  __int128 v158; // [rsp+1A8h] [rbp-4B8h]
  __int64 v159; // [rsp+1B8h] [rbp-4A8h]
  unsigned __int64 v160; // [rsp+1C0h] [rbp-4A0h]
  _DWORD *v161; // [rsp+1C8h] [rbp-498h]
  unsigned __int64 v162; // [rsp+1D0h] [rbp-490h]
  __int64 v163; // [rsp+1D8h] [rbp-488h]
  char *v164; // [rsp+1E0h] [rbp-480h]
  _DWORD *v165; // [rsp+1E8h] [rbp-478h]
  _DWORD *v166; // [rsp+1F0h] [rbp-470h]
  __int128 v167; // [rsp+1F8h] [rbp-468h] BYREF
  _BYTE v168[144]; // [rsp+208h] [rbp-458h] BYREF
  _BYTE v169[576]; // [rsp+298h] [rbp-3C8h] BYREF
  __int128 v170; // [rsp+4D8h] [rbp-188h] BYREF
  int v171; // [rsp+4E8h] [rbp-178h] BYREF
  __int128 v172; // [rsp+4F0h] [rbp-170h]
  __int64 v173; // [rsp+500h] [rbp-160h]
  _QWORD v174[36]; // [rsp+508h] [rbp-158h] BYREF

  v3 = Irp;
  Irpa = Irp;
  *(_QWORD *)&v167 = Irp;
  *(_OWORD *)Src = 0;
  v157 = 0;
  v158 = 0;
  v159 = 0;
  v147 = 0;
  v4 = memset(v169, 0, 0x238u);
  v129 = 0;
  RequestFromId = 0;
  v163 = 0;
  v127 = 0;
  LOBYTE(v4) = 0;
  v146 = (int)v4;
  v135 = 0;
  LOBYTE(v153) = 0;
  v126 = 0;
  v133 = 0;
  v144 = 0;
  v121 = 0;
  v136 = 0;
  v128 = 0;
  v151 = 0;
  v120 = 0;
  v171 = 0;
  v172 = 0;
  v173 = 0;
  memset(v174, 0, sizeof(v174));
  P = 0;
  v139 = 0;
  memset(v168, 0, sizeof(v168));
  v130[0] = 0;
  v170 = 0;
  v125 = 0;
  v137 = 0;
  v154 = 0;
  v140 = 0;
  v138 = 0;
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_qq(1033, 10, WPP_54b57318e3d43d9a582754a6a1e5a7fd_Traceguids, v3, a2);
  v134 = IoIs32bitProcess(v3);
  v6 = *(_QWORD **)(a2 + 48);
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_qdP(1033, 12, WPP_cabed21e4b613d44a46a0a969b426de7_Traceguids, v6, 1, &v144);
  v144 = 0;
  v7 = v6[1];
  if ( *(PVOID *)(v7 + 8) == UxDriverObject && v6[4] == 1347440705 )
  {
    v8 = v6[3];
    if ( v8
      && *(_DWORD *)(v8 + 24) == 1346464853
      && (v9 = *(_QWORD *)(v8 + 8)) != 0
      && *(_DWORD *)(v9 + 128) == 1329687637 )
    {
      if ( (*(_DWORD *)(v8 + 40) & 1) != 0 )
      {
        v10 = *(_QWORD *)(*(_QWORD *)(v8 + 8) + 320LL);
        if ( v10 == PsGetCurrentServerSilo() )
        {
          SendInfoOld = 0;
          v144 = v8;
        }
        else
        {
          SendInfoOld = -1073740700;
        }
      }
      else
      {
        SendInfoOld = -1073741637;
      }
    }
    else
    {
      SendInfoOld = -1073741811;
    }
  }
  else
  {
    SendInfoOld = -1073741808;
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_qD(1033, 13, WPP_cabed21e4b613d44a46a0a969b426de7_Traceguids, v144, SendInfoOld);
  if ( SendInfoOld < 0 )
    goto LABEL_305;
  SendInfoOld = UlpGetSendInfoOld(
                  v3,
                  (unsigned __int8)v3->RequestorMode,
                  *(_QWORD *)(a2 + 32),
                  *(unsigned int *)(a2 + 16),
                  Src);
  v131 = SendInfoOld;
  if ( SendInfoOld < 0 )
  {
    v39 = Irpa;
    v37 = 0;
    v38 = v129;
    goto LABEL_307;
  }
  v12 = *(_QWORD *)(v144 + 8);
  RequestorMode = v3->RequestorMode;
  v142 = 0;
  v129 = 0;
  v14 = 0;
  v120 = 0;
  if ( !Src[0] )
  {
    SendInfoOld = -1073741811;
    v142 = -1073741811;
    goto LABEL_23;
  }
  SendInfoOld = 0;
  v142 = 0;
  v15 = IoIs32bitProcess(v3) == 0;
  v16 = *(_WORD *)(v12 + 276);
  if ( !v15 )
  {
    UShortFromUser = 0;
    v145 = 0;
    v43 = Src[0];
    v141 = (char *)Src[0];
    if ( UxKirNewUma )
    {
      v7 = (__int64)Src[0] & 3;
      if ( v16 < 2u )
      {
        SendInfoOld = v7 != 0 ? 0xC000000D : 0;
        v142 = SendInfoOld;
        if ( ((__int64)Src[0] & 3) != 0 )
          goto LABEL_97;
      }
      else
      {
        SendInfoOld = v7 != 0 ? 0xC000000D : 0;
        v142 = SendInfoOld;
        if ( ((__int64)Src[0] & 3) != 0 )
          goto LABEL_97;
      }
    }
    else
    {
      v82 = 288;
      if ( v16 < 2u )
        v82 = 280;
      UlProbeForRead(Src[0], v82, 4u);
      v43 = v141;
    }
    if ( *(_WORD *)(v12 + 276) > 1u || *(_WORD *)(v12 + 276) == 1 && *(_WORD *)(v12 + 278) )
    {
      if ( UxKirNewUma && RequestorMode )
      {
        UShortFromUser = RtlReadUShortFromUser(v43 + 140);
        v43 = v141;
      }
      else
      {
        UShortFromUser = v43[140];
      }
      v145 = UShortFromUser;
    }
    if ( UxKirNewUma && RequestorMode )
      v44 = RtlReadUShortFromUser(v43 + 8);
    else
      v44 = v43[8];
    Pool3 = (_DWORD *)ExAllocatePool3(
                        256,
                        ((24LL * v44 + 7) & 0xFFFFFFFFFFFFFFF8uLL) + 568 + 16LL * UShortFromUser,
                        1397255253,
                        UxLowPriorityPool,
                        1);
    v46 = Pool3;
    *(_QWORD *)&v152 = Pool3;
    if ( !Pool3 )
    {
      SendInfoOld = -1073741801;
      v142 = -1073741801;
      if ( (BYTE8(xmmword_1401A2C90) & 0x40) != 0 )
        WPP_SF_d(774, 21, WPP_1b5368ba27d432da7ccf48cd814def19_Traceguids, 3221225495LL);
      goto LABEL_96;
    }
    v129 = Pool3;
    v120 = 1;
    *((_WORD *)Pool3 + 12) = v44;
    *((_WORD *)Pool3 + 276) = UShortFromUser;
    SendInfoOld = 0;
    v148 = 0;
    v160 = 0;
    v161 = 0;
    v164 = 0;
    v165 = 0;
    v162 = 0;
    v166 = 0;
    if ( UxKirNewUma )
    {
      v47 = v141;
      if ( RequestorMode )
      {
        ULongFromUser = RtlReadULongFromUser(v141);
        v46 = (_DWORD *)v152;
      }
      else
      {
        ULongFromUser = *(_DWORD *)v141;
      }
      *v46 = ULongFromUser;
      v49 = v47 + 4;
      v50 = v46 + 1;
      if ( RequestorMode )
        *v50 = RtlReadULongFromUser(v49);
      else
        RtlCopyVolatileMemory(v50, v49, 4u);
      v51 = v141;
      if ( RequestorMode )
      {
        v52 = RtlReadUShortFromUser(v141 + 8);
        v51 = v141;
      }
      else
      {
        v52 = *((_WORD *)v141 + 4);
      }
      v53 = v152;
      *(_WORD *)(v152 + 8) = v52;
      if ( RequestorMode )
      {
        v54 = RtlReadUShortFromUser(v51 + 10);
        v51 = v141;
      }
      else
      {
        v54 = *((_WORD *)v51 + 5);
      }
      *(_WORD *)(v53 + 10) = v54;
      if ( RequestorMode )
      {
        v55 = RtlReadULongFromUser(v51 + 12);
        v51 = v141;
      }
      else
      {
        v55 = *((_DWORD *)v51 + 3);
      }
      *(_QWORD *)(v53 + 16) = v55;
      if ( RequestorMode )
      {
        v56 = RtlReadUShortFromUser(v51 + 272);
        v51 = v141;
      }
      else
      {
        v56 = *((_WORD *)v51 + 136);
      }
      *(_WORD *)(v53 + 536) = v56;
      if ( RequestorMode )
      {
        v57 = RtlReadULongFromUser(v51 + 276);
        v51 = v141;
      }
      else
      {
        v57 = *((_DWORD *)v51 + 69);
      }
      *(_QWORD *)(v53 + 544) = v57;
      if ( RequestorMode )
      {
        v58 = RtlReadUShortFromUser(v51 + 24);
        v51 = v141;
      }
      else
      {
        v58 = *((_WORD *)v51 + 12);
      }
      if ( !v58 )
      {
        if ( RequestorMode )
        {
          v59 = RtlReadULongFromUser(v51 + 28);
          v51 = v141;
        }
        else
        {
          v59 = *((_DWORD *)v51 + 7);
        }
        if ( !v59 )
        {
          if ( RequestorMode )
            v60 = RtlReadULongFromUser(v51 + 20);
          else
            v60 = *((_DWORD *)v51 + 5);
          v61 = v60;
          v46 = (_DWORD *)v152;
LABEL_123:
          v160 = v61;
          v62 = v46 + 142;
          v161 = v46 + 142;
          *((_QWORD *)v46 + 4) = v46 + 142;
          v63 = *((unsigned __int16 *)v46 + 12);
          if ( UxKirNewUma )
          {
            if ( !(_WORD)v63 || (SendInfoOld = -1073741811, (v61 & 3) == 0) )
              SendInfoOld = 0;
            v148 = SendInfoOld;
            if ( SendInfoOld < 0 )
              goto LABEL_233;
          }
          else
          {
            UlProbeForRead((volatile void *)v61, 12 * v63, 4u);
            v46 = (_DWORD *)v152;
          }
          v68 = 0;
          while ( 1 )
          {
            v122 = v68;
            if ( v68 >= *((_WORD *)v46 + 12) )
              break;
            if ( UxKirNewUma )
            {
              if ( RequestorMode )
                v64 = RtlReadUShortFromUser(v61);
              else
                v64 = *(_WORD *)v61;
              *(_WORD *)v62 = v64;
              if ( RequestorMode )
                v65 = RtlReadULongFromUser(v61 + 4);
              else
                v65 = *(_DWORD *)(v61 + 4);
              *((_QWORD *)v62 + 1) = v65;
              if ( RequestorMode )
                v66 = RtlReadUShortFromUser(v61 + 2);
              else
                v66 = *(_WORD *)(v61 + 2);
              *((_WORD *)v62 + 1) = v66;
              if ( RequestorMode )
                v67 = RtlReadULongFromUser(v61 + 8);
              else
                v67 = *(_DWORD *)(v61 + 8);
              *((_QWORD *)v62 + 2) = v67;
              v68 = v122;
              v46 = (_DWORD *)v152;
            }
            else
            {
              *(_WORD *)v62 = *(_WORD *)v61;
              *((_QWORD *)v62 + 1) = *(unsigned int *)(v61 + 4);
              *((_WORD *)v62 + 1) = *(_WORD *)(v61 + 2);
              *((_QWORD *)v62 + 2) = *(unsigned int *)(v61 + 8);
            }
            ++v68;
            v61 += 12LL;
            v160 = v61;
            v62 += 6;
            v161 = v62;
          }
          v85 = v141 + 32;
          v86 = v46 + 14;
          v7 = 0;
          while ( 1 )
          {
            v123 = v7;
            v165 = v86;
            v164 = v85;
            if ( (unsigned __int16)v7 >= 0x1Eu )
              break;
            if ( UxKirNewUma )
            {
              if ( RequestorMode )
                v69 = RtlReadUShortFromUser(v85);
              else
                v69 = *(_WORD *)v85;
              *(_WORD *)v86 = v69;
              if ( RequestorMode )
                LODWORD(v70) = RtlReadULongFromUser(v85 + 4);
              else
                LODWORD(v70) = *((_DWORD *)v85 + 1);
              v70 = (unsigned int)v70;
              v7 = v123;
            }
            else
            {
              *(_WORD *)v86 = *(_WORD *)v85;
              v70 = *((unsigned int *)v85 + 1);
            }
            *((_QWORD *)v86 + 1) = v70;
            LOWORD(v7) = v7 + 1;
            v85 += 8;
            v86 += 4;
          }
          v77 = (_DWORD *)(((unsigned __int64)v161 + 7) & 0xFFFFFFFFFFFFFFF8uLL);
          v166 = v77;
          v72 = v152;
          if ( *(_WORD *)(v152 + 552) )
          {
            if ( UxKirNewUma )
            {
              if ( RequestorMode )
              {
                v71 = RtlReadULongFromUser(v141 + 284);
                v72 = v152;
              }
              else
              {
                v71 = *((_DWORD *)v141 + 71);
              }
              v73 = v71;
            }
            else
            {
              v73 = *((unsigned int *)v141 + 71);
            }
            v162 = v73;
            *(_QWORD *)(v72 + 560) = v77;
            v87 = *(unsigned __int16 *)(v72 + 552);
            if ( UxKirNewUma )
            {
              if ( !(_WORD)v87 || (SendInfoOld = -1073741811, (v73 & 3) == 0) )
                SendInfoOld = 0;
              v148 = SendInfoOld;
              if ( SendInfoOld < 0 )
                goto LABEL_233;
            }
            else
            {
              UlProbeForRead((volatile void *)v73, 12 * v87, 4u);
              v72 = v152;
            }
            v76 = 0;
            while ( 1 )
            {
              v124 = v76;
              if ( v76 >= *(_WORD *)(v72 + 552) )
                break;
              if ( UxKirNewUma )
              {
                if ( RequestorMode )
                  *v77 = RtlReadULongFromUser(v73);
                else
                  RtlCopyVolatileMemory(v77, (const void *)v73, 4u);
                if ( RequestorMode )
                  v74 = RtlReadULongFromUser(v73 + 4);
                else
                  v74 = *(_DWORD *)(v73 + 4);
                v77[1] = v74;
                if ( RequestorMode )
                  v75 = RtlReadULongFromUser(v73 + 8);
                else
                  v75 = *(_DWORD *)(v73 + 8);
                *((_QWORD *)v77 + 1) = v75;
                v72 = v152;
              }
              else
              {
                *v77 = *(_DWORD *)v73;
                v77[1] = *(_DWORD *)(v73 + 4);
                *((_QWORD *)v77 + 1) = *(unsigned int *)(v73 + 8);
              }
              v76 = v124 + 1;
              v77 += 4;
              v166 = v77;
              v73 += 12LL;
              v162 = v73;
            }
          }
LABEL_233:
          v142 = SendInfoOld;
LABEL_96:
          v3 = Irpa;
LABEL_97:
          v14 = v120;
          goto LABEL_23;
        }
      }
      SendInfoOld = -1073741811;
      v148 = -1073741811;
      if ( (BYTE8(xmmword_1401A2C90) & 0x40) == 0 )
        goto LABEL_233;
      v84 = 20;
    }
    else
    {
      v83 = v141;
      *Pool3 = *(_DWORD *)v141;
      Pool3[1] = *((_DWORD *)v83 + 1);
      *((_WORD *)Pool3 + 4) = *((_WORD *)v83 + 4);
      *((_WORD *)Pool3 + 5) = *((_WORD *)v83 + 5);
      *((_QWORD *)Pool3 + 2) = *((unsigned int *)v83 + 3);
      *((_WORD *)Pool3 + 268) = *((_WORD *)v83 + 136);
      *((_QWORD *)Pool3 + 68) = *((unsigned int *)v83 + 69);
      if ( !*((_WORD *)v83 + 12) && !*((_DWORD *)v83 + 7) )
      {
        v61 = *((unsigned int *)v83 + 5);
        goto LABEL_123;
      }
      SendInfoOld = -1073741811;
      v148 = -1073741811;
      if ( (BYTE8(xmmword_1401A2C90) & 0x40) == 0 )
        goto LABEL_233;
      v84 = 19;
    }
    WPP_SF_d(774, v84, WPP_1b5368ba27d432da7ccf48cd814def19_Traceguids, 3221225485LL);
    goto LABEL_233;
  }
  if ( UxKirNewUma )
  {
    v17 = Src[0];
    v7 = (__int64)Src[0] & 7;
    if ( v16 >= 2u )
    {
      SendInfoOld = v7 != 0 ? 0xC000000D : 0;
      v142 = SendInfoOld;
      if ( ((__int64)Src[0] & 7) != 0 )
        goto LABEL_23;
    }
    else
    {
      SendInfoOld = v7 != 0 ? 0xC000000D : 0;
      v142 = SendInfoOld;
      if ( ((__int64)Src[0] & 7) != 0 )
        goto LABEL_23;
    }
  }
  else
  {
    if ( v16 >= 2u )
      UlProbeForRead(Src[0], 0x238u, 8u);
    else
      UlProbeForRead(Src[0], 0x228u, 8u);
    v17 = Src[0];
  }
  if ( !UxKirNewUma )
  {
    v7 = (unsigned __int64)v169;
    v41 = 4;
    do
    {
      *(_OWORD *)v7 = *v17;
      *(_OWORD *)(v7 + 16) = v17[1];
      *(_OWORD *)(v7 + 32) = v17[2];
      *(_OWORD *)(v7 + 48) = v17[3];
      *(_OWORD *)(v7 + 64) = v17[4];
      *(_OWORD *)(v7 + 80) = v17[5];
      *(_OWORD *)(v7 + 96) = v17[6];
      *(_OWORD *)(v7 + 112) = v17[7];
      v7 += 128LL;
      v17 += 8;
      --v41;
    }
    while ( v41 );
    *(_OWORD *)v7 = *v17;
    *(_OWORD *)(v7 + 16) = v17[1];
    *(_OWORD *)(v7 + 32) = v17[2];
    *(_QWORD *)(v7 + 48) = *((_QWORD *)v17 + 6);
    v3 = Irpa;
    goto LABEL_84;
  }
  v88 = 568;
  if ( *(_WORD *)(v12 + 276) < 2u )
    v88 = 552;
  if ( !RequestorMode )
  {
    RtlCopyVolatileMemory(v169, v17, v88);
LABEL_84:
    v129 = v169;
    goto LABEL_23;
  }
  RtlCopyFromUser(v169, v17, v88);
  v129 = v169;
LABEL_23:
  v131 = SendInfoOld;
  if ( SendInfoOld < 0 )
  {
    v39 = Irpa;
    v37 = v120;
    v38 = v129;
    goto LABEL_307;
  }
  v116 = &v171;
  ChunkInfoOld = UlpGetChunkInfoOld(v3, (unsigned __int8)v3->RequestorMode, LOWORD(Src[1]), v157);
  SendInfoOld = ChunkInfoOld;
  v131 = ChunkInfoOld;
  if ( ChunkInfoOld < 0 )
  {
    if ( (BYTE8(xmmword_1401A2C90) & 0x40) != 0 )
      WPP_SF_d(774, 11, WPP_54b57318e3d43d9a582754a6a1e5a7fd_Traceguids, (unsigned int)ChunkInfoOld);
    v39 = Irpa;
    v37 = v120;
    v38 = v129;
    goto LABEL_307;
  }
  SendInfoOld = UlpGetLogInfoOld(v3, (unsigned __int8)v3->RequestorMode, Src, v168);
  v131 = SendInfoOld;
  if ( SendInfoOld < 0 )
  {
    v39 = Irpa;
    v37 = v120;
    v38 = v129;
    goto LABEL_307;
  }
  v19 = WORD5(v158);
  v20 = BYTE8(v158) & 2;
  LODWORD(v141) = v20;
  v128 = v20 == 0;
  if ( (BYTE8(v158) & 2) == 0 )
  {
    v151 = v158;
    *((_QWORD *)&v170 + 1) = *((_QWORD *)&UlEtwBaseOpaqueIdActivityGuid + 1);
    *(_QWORD *)&v170 = v158;
    v7 = *(_QWORD *)(*(_QWORD *)(v144 + 8) + 328LL);
    if ( (*(_BYTE *)(v7 + 1760) & 4) != 0 )
    {
      McTemplateK0x_EtwWriteTransfer(v7 + 1688, HTTP_EVENT_RECEIVE_RESPONSE_FROM_USERMODE_LEGACY, &v170, v158);
      v19 = WORD5(v158);
      v20 = (int)v141;
    }
    else
    {
      v20 = (int)v141;
    }
  }
  if ( v154 && v20 )
  {
    SendInfoOld = -1073741811;
    v131 = -1073741811;
    v39 = Irpa;
    v37 = v120;
    v38 = v129;
    goto LABEL_307;
  }
  v131 = 0;
  if ( (BYTE2(xmmword_1401A2CA0) & 1) != 0 )
  {
    WORD1(v115) = v19;
    WPP_SF_iD(v7, 12);
  }
  RequestFromId = UlGetRequestFromId(v158, v144);
  v163 = RequestFromId;
  if ( !RequestFromId )
  {
    SendInfoOld = -1073741254;
    v131 = -1073741254;
    if ( (BYTE8(xmmword_1401A2C90) & 0x40) != 0 )
      WPP_SF_d(774, 13, WPP_54b57318e3d43d9a582754a6a1e5a7fd_Traceguids, 3221226042LL);
    v39 = Irpa;
    v37 = v120;
    v38 = v129;
    goto LABEL_307;
  }
  if ( SDWORD2(v157) >= 3 )
  {
    SendInfoOld = -1073741811;
    v131 = -1073741811;
    if ( (BYTE8(xmmword_1401A2C90) & 0x40) != 0 )
      WPP_SF_d(774, 14, WPP_54b57318e3d43d9a582754a6a1e5a7fd_Traceguids, 3221225485LL);
    v39 = Irpa;
    v37 = v120;
    v38 = v129;
    goto LABEL_307;
  }
  if ( DWORD2(v157) )
  {
    v40 = *(_DWORD *)(RequestFromId + 2200) >> 1;
    LOBYTE(v40) = (*(_DWORD *)(RequestFromId + 2200) & 2) != 0;
    v146 = v40;
    v135 = v40;
    v21 = v40;
    v143 = v40;
  }
  else
  {
    v21 = v153;
  }
  v22 = *(_DWORD *)(*(_QWORD *)(v144 + 8) + 276LL);
  v153 = v22;
  if ( (unsigned __int16)v22 >= 2u )
  {
    SendInfoOld = UlFlCaptureFlowRateInfoOld(*(_QWORD *)(v144 + 136), (_DWORD)v129, 0, 0, v14, v134, (__int64)&v125);
    v131 = SendInfoOld;
    if ( SendInfoOld < 0 )
    {
      v39 = Irpa;
      v37 = v120;
      v38 = v129;
      goto LABEL_307;
    }
  }
  v23 = DWORD2(v158);
  v24 = v129;
  if ( *(_QWORD *)(RequestFromId + 2488) )
  {
    if ( (BYTE8(v158) & 0x10) != 0 )
    {
      v25 = 0;
    }
    else if ( (BYTE8(v158) & 0x40) != 0 )
    {
      v25 = 0;
    }
    else if ( (unsigned __int16)v22 >= 2u && *((_WORD *)v129 + 276) )
    {
      v25 = 0;
    }
    else
    {
      v89 = *((_WORD *)v129 + 4);
      v25 = (v89 == 200 || v89 == 206) && *(_DWORD *)(RequestFromId + 2676) <= 1u;
    }
  }
  else
  {
    v25 = 0;
  }
  v137 = v25;
  if ( !v21 )
  {
    if ( !v25 )
      goto LABEL_42;
    v21 = (*(_DWORD *)(RequestFromId + 2200) & 4) != 0;
    v143 = v21;
  }
  if ( v25 )
    goto LABEL_53;
LABEL_42:
  if ( (_BYTE)v146
    || v125
    || (BYTE8(v158) & 4) != 0
    || (BYTE8(v158) & 0x20) != 0
    || *(int *)(RequestFromId + 2116) <= 1 && (WORD4(v158) & 0x200) != 0 )
  {
    goto LABEL_53;
  }
  if ( !(unsigned __int8)UxTpIsFastSendPossible(*(_QWORD *)(RequestFromId + 24) + 976LL)
    || v140 != 1
    || *(_DWORD *)P
    || (unsigned int)(*((_DWORD *)P + 4) - 1) > 0xFFFF )
  {
    goto LABEL_51;
  }
  if ( (unsigned __int16)v22 >= 2u && v24[276] )
  {
    appended = UlExtractAndAppendAuthenticationResponseInfo(
                 RequestFromId,
                 (_DWORD)v24,
                 0,
                 (unsigned __int8)v3->RequestorMode,
                 0,
                 (__int64)&v133);
    SendInfoOld = appended;
    v131 = appended;
    if ( appended < 0 )
    {
      if ( (BYTE8(xmmword_1401A2C90) & 0x40) != 0 )
        WPP_SF_d(774, 15, WPP_54b57318e3d43d9a582754a6a1e5a7fd_Traceguids, (unsigned int)appended);
      v39 = Irpa;
      v37 = v120;
      v38 = v129;
      goto LABEL_307;
    }
    if ( v133 )
    {
      LODWORD(v24) = (_DWORD)v129;
LABEL_51:
      v23 = DWORD2(v158);
LABEL_53:
      v27 = UlCaptureHttpResponseOld(
              v144,
              (_DWORD)v24,
              RequestFromId,
              (_DWORD)v3,
              v140,
              (__int64)P,
              v3->RequestorMode,
              v23,
              v21,
              0,
              v159,
              v25,
              0,
              v154,
              (__int64)v130,
              (__int64)&v147);
      SendInfoOld = v27;
      v131 = v27;
      if ( v27 < 0 )
      {
        if ( (BYTE8(xmmword_1401A2C90) & 0x40) != 0 )
          WPP_SF_d(774, 16, WPP_54b57318e3d43d9a582754a6a1e5a7fd_Traceguids, (unsigned int)v27);
        v39 = Irpa;
        v37 = v120;
        v38 = v129;
        goto LABEL_307;
      }
      v26 = v147;
      v29 = *(_BYTE *)(v147 + 64);
      v149 = v29;
      v30 = *(_QWORD *)(RequestFromId + 24);
      if ( v30 )
      {
        v31 = *(_QWORD *)(v30 + 1096);
        if ( (*(_BYTE *)(v31 + 1760) & 4) != 0 )
        {
          if ( !*(_QWORD *)(v31 + 1776)
            || (v91 = UlEtwEvaluateFilterForRequestConnection(RequestFromId, v30, 0), v26 = v147, v91) )
          {
            v92 = UlVerbToString(*(unsigned int *)(v26 + 156), *(_QWORD *)(RequestFromId + 24), v28, v26);
            McTemplateK0xxhsqhq_EtwWriteTransfer(
              *(_QWORD *)(v93 + 1096) + 1688,
              (unsigned int)HTTP_EVENT_RECEIVE_RESPONSE_FROM_USERMODE,
              RequestFromId + 72,
              *(_QWORD *)(RequestFromId + 56),
              *(_QWORD *)(v93 + 48),
              *(_WORD *)(v94 + 152),
              v92,
              *(_DWORD *)(v94 + 168),
              (char)Src[1],
              SBYTE8(v157));
            v26 = v147;
          }
        }
      }
      if ( (BYTE2(xmmword_1401A2CA0) & 1) != 0 )
      {
        LOWORD(v117) = Src[1];
        LOWORD(v116) = *(_WORD *)(v26 + 152);
        WPP_SF_iiHLLHL(
          *(_QWORD *)(RequestFromId + 24),
          17,
          WPP_54b57318e3d43d9a582754a6a1e5a7fd_Traceguids,
          *(_QWORD *)(RequestFromId + 56),
          *(_QWORD *)(*(_QWORD *)(RequestFromId + 24) + 48LL),
          (_DWORD)v116,
          *(_DWORD *)(v26 + 156),
          *(_DWORD *)(v26 + 168),
          v117,
          DWORD2(v157));
      }
      goto LABEL_58;
    }
  }
  v126 = 1;
  v29 = 0;
LABEL_58:
  LOBYTE(v26) = 1;
  v32 = UlCheckSendResponseFlags(RequestFromId, DWORD2(v158), v130[0], v26, v29, v140 != 0);
  SendInfoOld = v32;
  v131 = v32;
  if ( v32 < 0 )
  {
    if ( (BYTE8(xmmword_1401A2C90) & 0x40) != 0 )
      WPP_SF_d(774, 18, WPP_54b57318e3d43d9a582754a6a1e5a7fd_Traceguids, (unsigned int)v32);
    v39 = Irpa;
    v37 = v120;
    v38 = v129;
  }
  else
  {
    v33 = v3->RequestorMode;
    v34 = v159;
    v35 = *(_QWORD *)(RequestFromId + 24);
    SendInfoOld = 0;
    v150 = 0;
    if ( (BYTE8(v158) & 2) != 0 )
    {
      if ( *(_DWORD *)(v35 + 528) )
      {
        SendInfoOld = -1073741254;
        v150 = -1073741254;
      }
    }
    else if ( _InterlockedCompareExchange((volatile signed __int32 *)(RequestFromId + 2228), 1, 0) == 1 )
    {
      KeEnterCriticalRegion();
      *(_QWORD *)&v152 = v35 + 576;
      ExAcquirePushLockExclusiveEx(v35 + 576, 0);
      if ( *(_DWORD *)(v35 + 528) )
      {
        if ( _InterlockedCompareExchange((volatile signed __int32 *)(v35 + 560), 1, 0) == 1 )
        {
          SendInfoOld = -1073741254;
          v150 = -1073741254;
        }
        else
        {
          SendInfoOld = UlLogZombieConnection(RequestFromId, v35, v34, v33);
          v150 = SendInfoOld;
        }
      }
      ExReleasePushLockExclusiveEx(v152, 0);
      KeLeaveCriticalRegion();
    }
    v131 = SendInfoOld;
    if ( SendInfoOld >= 0 )
    {
      if ( v147 )
      {
        if ( v159 )
        {
          if ( !(_DWORD)v141 )
          {
            v95 = UlCaptureUserLogData(v159, RequestFromId, v147 + 512);
            SendInfoOld = v95;
            v131 = v95;
            if ( v95 < 0 )
            {
              if ( (BYTE8(xmmword_1401A2C90) & 0x40) != 0 )
                WPP_SF_d(774, 20, WPP_54b57318e3d43d9a582754a6a1e5a7fd_Traceguids, (unsigned int)v95);
              v39 = Irpa;
              v37 = v120;
              v38 = v129;
              goto LABEL_307;
            }
          }
        }
      }
      if ( !v125 )
      {
LABEL_296:
        v96 = Irpa;
        v97 = v146;
        if ( (WORD4(v158) & 0x100) != 0 )
        {
          v107 = *(_QWORD *)(RequestFromId + 24);
          if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
            WPP_SF_qLqqqq(1049, 10, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids, v107 + 496, 51, 0, 0, 0, 0);
          v116 = 0;
          v115 = 0;
          v108 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(*(_QWORD *)(v107 + 504) + 136LL))(
                   *(_QWORD *)(v107 + 496),
                   51,
                   0,
                   0);
          SendInfoOld = v108;
          if ( (BYTE3(xmmword_1401A2CA0) & 2) != 0 )
            WPP_SF_d(1049, 11, WPP_300186a3c0a63884e6514bae8b68e166_Traceguids, v108);
          if ( SendInfoOld < 0 )
          {
            v121 = 1;
            goto LABEL_305;
          }
          v97 = v146;
        }
        if ( v126 )
        {
          v119 = v96->RequestorMode;
          v118 = (__int64)v96;
          v38 = v129;
          SendInfoOld = UlFastSendHttpResponseOld(
                          (_DWORD)v129,
                          v159,
                          (_DWORD)P,
                          1,
                          *((_DWORD *)P + 4),
                          0,
                          0,
                          DWORD2(v158),
                          RequestFromId,
                          *(_DWORD *)(*(_QWORD *)(v144 + 8) + 276LL),
                          v118,
                          v119,
                          v154,
                          0);
          goto LABEL_306;
        }
        if ( (unsigned __int8)UlSetSendIrpCancelRoutine(*(_QWORD *)(RequestFromId + 24), v96) )
        {
          *(_QWORD *)(v147 + 592) = v96;
          v98 = v147;
          v147 = 0;
          if ( v25 )
            *(_BYTE *)(v98 + 50) = UlpSetResponseCacheClassification(RequestFromId, v98, *((_QWORD *)&v157 + 1));
          v99 = v98;
          v100 = RequestFromId;
          if ( v97 )
          {
            SendInfoOld = UlCacheAndSendResponse(RequestFromId, v98, v144, DWORD2(v157), v115, v98, (__int64)&v127);
            if ( SendInfoOld < 0 || v127 )
            {
LABEL_303:
              if ( SendInfoOld != 259 )
              {
                UlRestartSendHttpResponseIoctl(v98, (unsigned int)SendInfoOld, 0);
                v121 = 1;
                SendInfoOld = 259;
              }
              goto LABEL_305;
            }
            v99 = v98;
            v100 = RequestFromId;
          }
          SendInfoOld = UlSendHttpResponse(v100, v99, (unsigned int)UlRestartSendHttpResponseIoctl, v98, 0);
          goto LABEL_303;
        }
        SendInfoOld = -1073741536;
LABEL_305:
        v38 = v129;
LABEL_306:
        v37 = v120;
        v39 = Irpa;
        goto LABEL_307;
      }
      v36 = *(_QWORD *)(RequestFromId + 2480);
      if ( !v36 )
      {
LABEL_66:
        v37 = v120;
        v38 = v129;
        SendInfoOld = UlFlCaptureFlowRateInfoOld(
                        *(_QWORD *)(*(_QWORD *)(RequestFromId + 24) + 1096LL),
                        (_DWORD)v129,
                        (int)RequestFromId + 2480,
                        (int)RequestFromId + 72,
                        v120,
                        v134,
                        0);
        v131 = SendInfoOld;
        if ( SendInfoOld < 0 )
        {
          v39 = Irpa;
          goto LABEL_307;
        }
        goto LABEL_296;
      }
      v78 = *(_QWORD *)(*(_QWORD *)(RequestFromId + 24) + 1088LL);
      v79 = _InterlockedDecrement((volatile signed __int32 *)(v36 + 24));
      if ( UxDebugCheckRefcount && v79 <= -1 )
        UlBugCheckEx(3u, v36 + 24, 1u, v79);
      if ( !v79 )
      {
        v80 = (_QWORD *)(v36 + 32);
        v152 = 0;
        if ( *v80 || v80[2] || v80[4] )
          UlBugCheckEx(1u, (ULONG_PTR)v80, (ULONG_PTR)"minio\\http\\sys\\flowrate.h", 0x76u);
        if ( KeGetCurrentIrql() )
        {
          LOBYTE(v81) = 1;
          UlThreadPoolEnqueueWorkItem(0, v80, UlpFlCleanupFlowRateInfoWorker, v81, v78, -1);
          *(_QWORD *)(RequestFromId + 2480) = 0;
          goto LABEL_66;
        }
        UxPodAttachThread(v78, &v152);
        UlpFlCleanupFlowRateInfoWorker(v80);
        UxPodDetachThread(&v152);
      }
      *(_QWORD *)(RequestFromId + 2480) = 0;
      goto LABEL_66;
    }
    if ( (BYTE8(xmmword_1401A2C90) & 0x40) != 0 )
      WPP_SF_d(774, 19, WPP_54b57318e3d43d9a582754a6a1e5a7fd_Traceguids, (unsigned int)SendInfoOld);
    v39 = Irpa;
    v37 = v120;
    v38 = v129;
  }
LABEL_307:
  v101 = 0;
  if ( v138 )
    ExFreePoolWithTag(*(PVOID *)(v154 + 16), 0);
  if ( v139 )
    ExFreePoolWithTag(P, 0);
  if ( v37 )
    ExFreePoolWithTag(v38, 0);
  if ( RequestFromId )
  {
    if ( !v127 && SendInfoOld != -1073741766 )
      UlpFlushHttpPushList(RequestFromId, 0);
    v102 = v130[0];
    if ( !v130[0] )
    {
      v102 = *(_WORD *)(RequestFromId + 1690);
      v130[0] = v102;
    }
    if ( !v128 || ((SendInfoOld + 0x80000000) & 0x80000000) != 0 || SendInfoOld == -1073741766 )
      goto LABEL_321;
    v7 = *(_QWORD *)(RequestFromId + 24);
    if ( v7 )
    {
      v106 = *(_QWORD *)(v7 + 1096);
      if ( (*(_BYTE *)(v106 + 1760) & 0x20) != 0 )
      {
        if ( !*(_QWORD *)(v106 + 1776) )
        {
LABEL_375:
          LOWORD(v115) = v102;
          McTemplateK0xh_EtwWriteTransfer(
            *(_QWORD *)(*(_QWORD *)(RequestFromId + 24) + 1096LL) + 1688LL,
            HTTP_EVENT_COMPLETE_SEND_ERROR_LEGACY,
            &v170,
            v151,
            v115);
          goto LABEL_376;
        }
        if ( (unsigned __int8)UlEtwEvaluateFilterForRequestConnection(RequestFromId, *(_QWORD *)(RequestFromId + 24), 0) )
        {
          v102 = v130[0];
          goto LABEL_375;
        }
      }
    }
LABEL_376:
    v101 = 1;
LABEL_321:
    if ( ((SendInfoOld + 0x80000000) & 0x80000000) == 0 && SendInfoOld != -1073741766 || v121 )
      UlCloseConnection(*(_QWORD *)(RequestFromId + 24));
    v103 = _InterlockedDecrement((volatile signed __int32 *)(RequestFromId + 48));
    if ( UxDebugCheckRefcount && v103 <= -1 )
      UlBugCheckEx(3u, RequestFromId + 48, 0xBu, v103);
    if ( !v103 )
      UlpQueueFreeHttpRequest(RequestFromId);
  }
  v104 = (_QWORD *)v147;
  if ( v147 )
  {
    v109 = v147 + 20;
    v110 = _InterlockedDecrement((volatile signed __int32 *)(v147 + 20));
    if ( UxDebugCheckRefcount && v110 <= -1 )
      UlBugCheckEx(3u, v109, 1u, v110);
    if ( !v110 )
    {
      v111 = v104 + 76;
      v167 = 0;
      if ( v104[76] || v104[78] || v104[80] )
        UlBugCheckEx(1u, (ULONG_PTR)(v104 + 76), (ULONG_PTR)"minio\\http\\sys\\sendresponse.h", 0x453u);
      v112 = *(_QWORD *)(*(_QWORD *)(v104[3] + 24LL) + 1088LL);
      if ( KeGetCurrentIrql() )
      {
        LOBYTE(v113) = 1;
        UlThreadPoolEnqueueWorkItem(0, v111, UlDestroyCapturedResponse, v113, v112, -1);
      }
      else
      {
        UxPodAttachThread(v112, &v167);
        UlDestroyCapturedResponse(v111);
        UxPodDetachThread(&v167);
      }
    }
  }
  if ( v128 && ((SendInfoOld + 0x80000000) & 0x80000000) == 0 && SendInfoOld != -1073741766 )
  {
    v114 = v151;
    if ( !v101 )
    {
      v7 = *(_QWORD *)(*(_QWORD *)(v144 + 8) + 328LL);
      if ( (*(_BYTE *)(v7 + 1760) & 0x20) != 0 )
      {
        LOWORD(v115) = v130[0];
        McTemplateK0xh_EtwWriteTransfer(v7 + 1688, HTTP_EVENT_COMPLETE_SEND_ERROR_LEGACY, &v170, v151, v115);
      }
    }
    if ( (BYTE2(xmmword_1401A2CA0) & 1) != 0 )
    {
      LOWORD(v116) = v130[0];
      WPP_SF_diH(v7, 22, WPP_54b57318e3d43d9a582754a6a1e5a7fd_Traceguids, (unsigned int)SendInfoOld, v114, v116);
    }
  }
  if ( SendInfoOld != 259 )
  {
    v39->IoStatus.Status = SendInfoOld;
    IofCompleteRequest(v39, 0);
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 2) != 0 )
    WPP_SF_d(1033, 23, WPP_54b57318e3d43d9a582754a6a1e5a7fd_Traceguids, (unsigned int)SendInfoOld);
  return (unsigned int)SendInfoOld;
}

```

## disassembly

```asm
0x14001d270  mov     [rsp+arg_10], rbx
0x14001d275  mov     [rsp+arg_18], rsi
0x14001d27a  push    rdi
0x14001d27b  push    r12
0x14001d27d  push    r13
0x14001d27f  push    r14
0x14001d281  push    r15
0x14001d283  sub     rsp, 5D0h
0x14001d28a  mov     rax, cs:__security_cookie
0x14001d291  xor     rax, rsp
0x14001d294  mov     [rsp+5F8h+var_38], rax
0x14001d29c  mov     r15, rdx
0x14001d29f  mov     r12, rcx
0x14001d2a2  mov     [rsp+5F8h+Irp], rcx
0x14001d2aa  mov     qword ptr [rsp+5F8h+var_468], rcx
0x14001d2b2  xorps   xmm0, xmm0
0x14001d2b5  xor     eax, eax
0x14001d2b7  movups  xmmword ptr [rsp+5F8h+Src], xmm0
0x14001d2bf  movups  [rsp+5F8h+var_4C8], xmm0
0x14001d2c7  movups  [rsp+5F8h+var_4B8], xmm0
0x14001d2cf  mov     [rsp+5F8h+var_4A8], rax
0x14001d2d7  xor     r14d, r14d
0x14001d2da  mov     [rsp+5F8h+var_520], r14
0x14001d2e2  xor     edx, edx; Val
0x14001d2e4  mov     r8d, 238h; Size
0x14001d2ea  lea     rcx, [rsp+5F8h+var_3C8]; void *
0x14001d2f2  call    memset
0x14001d2f7  mov     [rsp+5F8h+var_568], r14
0x14001d2ff  mov     esi, r14d
0x14001d302  mov     [rsp+5F8h+var_488], r14
0x14001d30a  mov     [rsp+5F8h+var_56E], sil
0x14001d312  xor     al, al
0x14001d314  mov     [rsp+5F8h+var_524], eax
0x14001d31b  mov     [rsp+5F8h+var_54E], al
0x14001d322  mov     byte ptr [rsp+5F8h+var_4F0], sil
0x14001d32a  mov     [rsp+5F8h+var_56F], sil
0x14001d332  mov     [rsp+5F8h+var_550], sil
0x14001d33a  mov     [rsp+5F8h+var_530], r14
0x14001d342  mov     [rsp+5F8h+var_577], al
0x14001d349  mov     [rsp+5F8h+var_54D], al
0x14001d350  mov     [rsp+5F8h+var_56D], al
0x14001d357  mov     [rsp+5F8h+var_508], r14
0x14001d35f  mov     [rsp+5F8h+var_578], al
0x14001d366  mov     [rsp+5F8h+var_178], r14d
0x14001d36e  xorps   xmm0, xmm0
0x14001d371  xor     eax, eax
0x14001d373  movups  [rsp+5F8h+var_170], xmm0
0x14001d37b  mov     [rsp+5F8h+var_160], rax
0x14001d383  xor     edx, edx; Val
0x14001d385  mov     r8d, 120h; Size
0x14001d38b  lea     rcx, [rsp+5F8h+var_158]; void *
0x14001d393  call    memset
0x14001d398  mov     [rsp+5F8h+P], r14
0x14001d3a0  mov     [rsp+5F8h+var_54A], sil
0x14001d3a8  xor     edx, edx; Val
0x14001d3aa  mov     r8d, 90h; Size
0x14001d3b0  lea     rcx, [rsp+5F8h+var_458]; void *
0x14001d3b8  call    memset
0x14001d3bd  mov     [rsp+5F8h+var_560], r14w
0x14001d3c6  xorps   xmm0, xmm0
0x14001d3c9  movups  [rsp+5F8h+var_188], xmm0
0x14001d3d1  mov     [rsp+5F8h+var_570], sil
0x14001d3d9  mov     [rsp+5F8h+var_54C], sil
0x14001d3e1  mov     [rsp+5F8h+var_4E8], r14
0x14001d3e9  mov     [rsp+5F8h+var_548], r14w
0x14001d3f2  mov     [rsp+5F8h+var_54B], sil
0x14001d3fa  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x14001d401  jnz     loc_14001F17D
0x14001d407  mov     rcx, r12; Irp
0x14001d40a  call    cs:__imp_IoIs32bitProcess
0x14001d411  nop     dword ptr [rax+rax+00h]
0x14001d416  mov     [rsp+5F8h+var_54F], al
0x14001d41d  mov     rbx, [r15+30h]
0x14001d421  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x14001d428  jnz     loc_14001EF98
0x14001d42e  mov     [rsp+5F8h+var_530], r14
0x14001d436  mov     rcx, [rbx+8]
0x14001d43a  mov     rax, cs:UxDriverObject
0x14001d441  cmp     [rcx+8], rax
0x14001d445  jnz     loc_14001EFD5
0x14001d44b  cmp     qword ptr [rbx+20h], 50505041h
0x14001d453  jnz     loc_14001EFD5
0x14001d459  mov     rbx, [rbx+18h]
0x14001d45d  test    rbx, rbx
0x14001d460  jz      loc_14001EF8E
0x14001d466  cmp     dword ptr [rbx+18h], 50416C55h
0x14001d46d  jnz     loc_14001EF8E
0x14001d473  mov     rax, [rbx+8]
0x14001d477  test    rax, rax
0x14001d47a  jz      loc_14001EF8E
0x14001d480  cmp     dword ptr [rax+80h], 4F416C55h
0x14001d48a  jnz     loc_14001EF8E
0x14001d490  mov     eax, [rbx+28h]
0x14001d493  test    al, 1
0x14001d495  jz      loc_14001EFCB
0x14001d49b  mov     rax, [rbx+8]
0x14001d49f  mov     rdi, [rax+140h]
0x14001d4a6  call    cs:__imp_PsGetCurrentServerSilo
0x14001d4ad  nop     dword ptr [rax+rax+00h]
0x14001d4b2  cmp     rdi, rax
0x14001d4b5  jnz     loc_14001F1A0
0x14001d4bb  mov     edi, r14d
0x14001d4be  mov     [rsp+5F8h+var_530], rbx
0x14001d4c6  test    byte ptr cs:xmmword_1401A2CA0+1, 2
0x14001d4cd  jnz     loc_14001F1AA
0x14001d4d3  test    edi, edi
0x14001d4d5  js      loc_14001F215
0x14001d4db  lea     rax, [rsp+5F8h+Src]
0x14001d4e3  mov     [rsp+5F8h+var_5D8], rax
0x14001d4e8  mov     r9d, [r15+10h]
0x14001d4ec  mov     r8, [r15+20h]
0x14001d4f0  movzx   edx, byte ptr [r12+40h]
0x14001d4f6  mov     rcx, r12
0x14001d4f9  call    UlpGetSendInfoOld
0x14001d4fe  mov     edi, eax
0x14001d500  mov     [rsp+5F8h+var_55C], eax
0x14001d507  test    eax, eax
0x14001d509  js      loc_14001E15E
0x14001d50f  mov     rax, [rsp+5F8h+var_530]
0x14001d517  mov     rbx, [rax+8]
0x14001d51b  movzx   r15d, byte ptr [r12+40h]
0x14001d521  mov     [rsp+5F8h+var_538], r14d
0x14001d529  mov     [rsp+5F8h+var_568], r14
0x14001d531  xor     r13b, r13b
0x14001d534  mov     [rsp+5F8h+var_578], r13b
0x14001d53c  cmp     [rsp+5F8h+Src], 0
0x14001d545  jz      loc_14001E181
0x14001d54b  mov     edi, r14d
0x14001d54e  mov     [rsp+5F8h+var_538], r14d
0x14001d556  mov     rcx, r12; Irp
0x14001d559  call    cs:__imp_IoIs32bitProcess
0x14001d560  nop     dword ptr [rax+rax+00h]
0x14001d565  test    al, al
0x14001d567  movzx   eax, word ptr [rbx+114h]
0x14001d56e  jnz     loc_14001E192
0x14001d574  cmp     cs:UxKirNewUma, dil
0x14001d57b  jz      loc_14001DB0F
0x14001d581  mov     rdx, [rsp+5F8h+Src]
0x14001d589  mov     rcx, rdx
0x14001d58c  and     ecx, 7
0x14001d58f  cmp     ax, 2
0x14001d593  mov     eax, ecx
0x14001d595  jnb     loc_14001E592
0x14001d59b  neg     rax
0x14001d59e  sbb     edi, edi
0x14001d5a0  and     edi, 0C000000Dh
0x14001d5a6  mov     [rsp+5F8h+var_538], edi
0x14001d5ad  test    rcx, rcx
0x14001d5b0  jz      loc_14001DB3D
0x14001d5b6  mov     [rsp+5F8h+var_55C], edi
0x14001d5bd  test    edi, edi
0x14001d5bf  js      loc_14001E5DB
0x14001d5c5  lea     rax, [rsp+5F8h+var_548]
0x14001d5cd  mov     [rsp+5F8h+var_5A8], rax
0x14001d5d2  lea     rax, [rsp+5F8h+var_54B]
0x14001d5da  mov     [rsp+5F8h+var_5B0], rax
0x14001d5df  lea     rax, [rsp+5F8h+var_4E8]
0x14001d5e7  mov     [rsp+5F8h+var_5B8], rax
0x14001d5ec  lea     rax, [rsp+5F8h+var_54A]
0x14001d5f4  mov     [rsp+5F8h+var_5C0], rax
0x14001d5f9  lea     rax, [rsp+5F8h+P]
0x14001d601  mov     [rsp+5F8h+var_5C8], rax
0x14001d606  lea     rax, [rsp+5F8h+var_178]
0x14001d60e  mov     [rsp+5F8h+var_5D0], rax
0x14001d613  mov     r9, qword ptr [rsp+5F8h+var_4C8]
0x14001d61b  movzx   r8d, word ptr [rsp+5F8h+Src+8]
0x14001d624  movzx   edx, byte ptr [r12+40h]
0x14001d62a  mov     rcx, r12
0x14001d62d  call    UlpGetChunkInfoOld
0x14001d632  mov     edi, eax
0x14001d634  mov     [rsp+5F8h+var_55C], eax
0x14001d63b  test    eax, eax
0x14001d63d  js      loc_14001E5FE
0x14001d643  lea     r9, [rsp+5F8h+var_458]
0x14001d64b  lea     r8, [rsp+5F8h+Src]
0x14001d653  movzx   edx, byte ptr [r12+40h]
0x14001d659  mov     rcx, r12
0x14001d65c  call    UlpGetLogInfoOld
0x14001d661  mov     edi, eax
0x14001d663  mov     [rsp+5F8h+var_55C], eax
0x14001d66a  test    eax, eax
0x14001d66c  js      loc_14001DA90
0x14001d672  mov     r8d, dword ptr [rsp+5F8h+var_4B8+8]
0x14001d67a  mov     eax, r8d
0x14001d67d  and     eax, 2
0x14001d680  mov     dword ptr [rsp+5F8h+var_540], eax
0x14001d687  setz    [rsp+5F8h+var_56D]
0x14001d68f  test    eax, eax
0x14001d691  jnz     loc_14001E66D
0x14001d697  mov     r9, qword ptr [rsp+5F8h+var_4B8]
0x14001d69f  mov     [rsp+5F8h+var_508], r9
0x14001d6a7  movups  xmm0, cs:UlEtwBaseOpaqueIdActivityGuid
0x14001d6ae  movups  [rsp+5F8h+var_188], xmm0
0x14001d6b6  mov     qword ptr [rsp+5F8h+var_188], r9
0x14001d6be  mov     rax, [rsp+5F8h+var_530]
0x14001d6c6  mov     rcx, [rax+8]
0x14001d6ca  mov     rcx, [rcx+148h]
0x14001d6d1  test    byte ptr [rcx+6E0h], 4
0x14001d6d8  jnz     loc_14001E643
0x14001d6de  mov     eax, dword ptr [rsp+5F8h+var_540]
0x14001d6e5  cmp     [rsp+5F8h+var_4E8], 0
0x14001d6ee  jnz     loc_14001E67A
0x14001d6f4  mov     [rsp+5F8h+var_55C], r14d
0x14001d6fc  test    byte ptr cs:xmmword_1401A2CA0+2, 1
0x14001d703  jnz     loc_14001E6B1
0x14001d709  mov     rdx, [rsp+5F8h+var_530]
0x14001d711  mov     rcx, qword ptr [rsp+5F8h+var_4B8]
0x14001d719  call    UlGetRequestFromId
0x14001d71e  mov     rsi, rax
0x14001d721  mov     [rsp+5F8h+var_488], rax
0x14001d729  test    rax, rax
0x14001d72c  jz      loc_14001E6C5
0x14001d732  mov     rax, qword ptr [rsp+5F8h+var_4C8+8]
0x14001d73a  cmp     eax, 3
0x14001d73d  jge     loc_14001E716
0x14001d743  test    eax, eax
0x14001d745  jnz     loc_14001DAB3
0x14001d74b  mov     r15d, [rsp+5F8h+var_4F0]
0x14001d753  mov     r10, [rsp+5F8h+var_530]
0x14001d75b  mov     rbx, [r10+8]
0x14001d75f  mov     ebx, [rbx+114h]
0x14001d765  mov     [rsp+5F8h+var_4F0], ebx
0x14001d76c  cmp     bx, 2
0x14001d770  jb      short loc_14001D7BE
0x14001d772  movzx   eax, [rsp+5F8h+var_54F]
0x14001d77a  movzx   ecx, r13b
0x14001d77e  lea     rdx, [rsp+5F8h+var_570]
0x14001d786  mov     [rsp+5F8h+var_5C8], rdx
0x14001d78b  mov     dword ptr [rsp+5F8h+var_5D0], eax
0x14001d78f  mov     dword ptr [rsp+5F8h+var_5D8], ecx
0x14001d793  xor     r9d, r9d
0x14001d796  xor     r8d, r8d
0x14001d799  mov     rdx, [rsp+5F8h+var_568]
0x14001d7a1  mov     rcx, [r10+88h]
0x14001d7a8  call    UlFlCaptureFlowRateInfoOld
0x14001d7ad  mov     edi, eax
0x14001d7af  mov     [rsp+5F8h+var_55C], eax
0x14001d7b6  test    eax, eax
0x14001d7b8  js      loc_14001E767
0x14001d7be  mov     ecx, dword ptr [rsp+5F8h+var_4B8+8]
0x14001d7c5  mov     rdi, [rsp+5F8h+var_568]
0x14001d7cd  cmp     qword ptr [rsi+9B8h], 0
0x14001d7d5  jnz     loc_14001E78A
0x14001d7db  xor     r13b, r13b
0x14001d7de  mov     [rsp+5F8h+var_54C], r13b
0x14001d7e6  test    r15b, r15b
0x14001d7e9  jnz     short loc_14001D85B
0x14001d7eb  test    r13b, r13b
0x14001d7ee  jnz     loc_14001E7EC
0x14001d7f4  cmp     byte ptr [rsp+5F8h+var_524], 0
0x14001d7fc  jnz     short loc_14001D860
0x14001d7fe  cmp     [rsp+5F8h+var_570], 0
0x14001d806  jnz     short loc_14001D860
0x14001d808  test    cl, 4
0x14001d80b  jnz     short loc_14001D860
0x14001d80d  test    cl, 20h
0x14001d810  jnz     short loc_14001D860
0x14001d812  cmp     dword ptr [rsi+844h], 1
0x14001d819  jg      short loc_14001D821
0x14001d81b  bt      ecx, 9
0x14001d81f  jb      short loc_14001D860
0x14001d821  mov     rcx, [rsi+18h]
0x14001d825  add     rcx, 3D0h
0x14001d82c  call    UxTpIsFastSendPossible
0x14001d831  test    al, al
0x14001d833  jz      short loc_14001D852
0x14001d835  cmp     [rsp+5F8h+var_548], 1
0x14001d83e  jnz     short loc_14001D852
0x14001d840  mov     r8, [rsp+5F8h+P]
0x14001d848  cmp     dword ptr [r8], 0
0x14001d84c  jz      loc_14001DADB
0x14001d852  mov     ecx, dword ptr [rsp+5F8h+var_4B8+8]
0x14001d859  jmp     short loc_14001D860
0x14001d85b  test    r13b, r13b
0x14001d85e  jz      short loc_14001D7F4
0x14001d860  lea     rax, [rsp+5F8h+var_520]
0x14001d868  mov     [rsp+5F8h+var_580], rax
0x14001d86d  lea     rax, [rsp+5F8h+var_560]
0x14001d875  mov     [rsp+5F8h+var_588], rax
0x14001d87a  mov     rax, [rsp+5F8h+var_4E8]
0x14001d882  mov     [rsp+5F8h+var_590], rax
0x14001d887  mov     byte ptr [rsp+5F8h+var_598], 0
0x14001d88c  mov     [rsp+5F8h+var_5A0], r13b
0x14001d891  mov     rax, [rsp+5F8h+var_4A8]
0x14001d899  mov     [rsp+5F8h+var_5A8], rax
0x14001d89e  mov     byte ptr [rsp+5F8h+var_5B0], 0
0x14001d8a3  mov     byte ptr [rsp+5F8h+var_5B8], r15b
0x14001d8a8  mov     dword ptr [rsp+5F8h+var_5C0], ecx
0x14001d8ac  movzx   eax, byte ptr [r12+40h]
0x14001d8b2  mov     byte ptr [rsp+5F8h+var_5C8], al
0x14001d8b6  mov     rax, [rsp+5F8h+P]
0x14001d8be  mov     [rsp+5F8h+var_5D0], rax
0x14001d8c3  movzx   eax, [rsp+5F8h+var_548]
0x14001d8cb  mov     word ptr [rsp+5F8h+var_5D8], ax
0x14001d8d0  mov     r9, r12
0x14001d8d3  mov     r8, rsi
0x14001d8d6  mov     rdx, rdi
0x14001d8d9  mov     rcx, [rsp+5F8h+var_530]
0x14001d8e1  call    UlCaptureHttpResponseOld
0x14001d8e6  mov     edi, eax
  ... truncated ...
```
