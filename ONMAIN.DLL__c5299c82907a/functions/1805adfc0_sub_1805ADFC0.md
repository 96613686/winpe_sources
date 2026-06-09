# sub_1805ADFC0

- ea: `0x1805adfc0`
- end: `0x1805aebcb`
- name: `sub_1805ADFC0`
- size: `3083`
- prototype: ``
- caller_count: `0`
- callee_count: `25`
- tags: `broker_com_uri`

## callees

- `0x180031ec0`
- `0x180078530`
- `0x18008d184`
- `0x1801f1cc8`
- `0x180269f54`
- `0x1802b1130`
- `0x1802d3794`
- `0x1802dc464`
- `0x1802dcef0`
- `0x1802dd020`
- `0x1802dd458`
- `0x1802de0c0`
- `0x1802de200`
- `0x1802de3a0`
- `0x18036e3c4`
- `0x180372a44`
- `0x1805adfc0`
- `0x1805aebcc`
- `0x1805aeee0`
- `0x1805af3b4`
- `0x1805af974`
- `0x1805af99c`
- `0x18074bdcc`
- `0x1808abd70`
- `0x1808d9644`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x1805aea79`
- `KERNEL32!GetTickCount64` at `0x1805aea79`
- `KERNEL32!QueryUnbiasedInterruptTime` at `0x1805ae026`
- `KERNEL32!QueryUnbiasedInterruptTime` at `0x1805ae26e`
- `KERNEL32!QueryUnbiasedInterruptTime` at `0x1805aea5c`
- `KERNEL32!QueryUnbiasedInterruptTime` at `0x1805ae026`
- `KERNEL32!QueryUnbiasedInterruptTime` at `0x1805ae26e`
- `KERNEL32!QueryUnbiasedInterruptTime` at `0x1805aea5c`
- `MSVCP140!_Mtx_unlock` at `0x1805ae84b`
- `MSVCP140!_Mtx_unlock` at `0x1805ae84b`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1805ae877`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1805ae966`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1805ae877`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1805ae966`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1805ae1c2`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1805ae236`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1805ae1c2`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1805ae236`
- `Csi!?CreateKnowledge@Csi@@YAXPEAPEAUIKnowledge@1@@Z` at `0x1805ae3ae`
- `Csi!?CreateKnowledge@Csi@@YAXPEAPEAUIKnowledge@1@@Z` at `0x1805ae3cd`
- `Csi!?CreateKnowledge@Csi@@YAXPEAPEAUIKnowledge@1@@Z` at `0x1805ae3ae`
- `Csi!?CreateKnowledge@Csi@@YAXPEAPEAUIKnowledge@1@@Z` at `0x1805ae3cd`
- `Csi!?FGetCellKnowledge@Csi@@YA_NPEAUIKnowledge@1@PEAPEAUICellKnowledge@CsiCell@@@Z` at `0x1805ae467`
- `Csi!?FGetCellKnowledge@Csi@@YA_NPEAUIKnowledge@1@PEAPEAUICellKnowledge@CsiCell@@@Z` at `0x1805ae467`

## pseudocode

```c
_UNKNOWN **__fastcall sub_1805ADFC0(__int64 a1, _DWORD *a2)
{
  _UNKNOWN **result; // rax
  _QWORD *v4; // rcx
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rbx
  const void *v8; // rax
  char v9; // al
  __int64 v10; // rbx
  __int64 v11; // rax
  __int128 *v12; // rdx
  const void *v13; // rax
  struct Csi::IKnowledge **v14; // rdx
  _QWORD *v15; // rcx
  __int64 v16; // rax
  Csi **v17; // rsi
  __int64 v18; // rax
  __int64 v19; // rax
  Csi *v20; // rdi
  void (__fastcall *v21)(Csi *, __int64); // rbx
  __int64 v22; // rax
  struct CsiCell::ICellKnowledge **v23; // r8
  __int64 v24; // rax
  __int64 v25; // rdi
  __int64 v26; // rbx
  void (__fastcall ***v27)(_QWORD, __int64 *, __int64 *); // r9
  __int64 v28; // rcx
  __int64 v29; // rax
  __int64 v30; // rax
  void (__fastcall ***v31)(_QWORD, __int64 *, void (__fastcall ****)(_QWORD)); // rcx
  __int64 v32; // rax
  struct _Mtx_internal_imp_t *v33; // r14
  __int64 v34; // r14
  __int64 v35; // r15
  __int64 v36; // rsi
  void (__fastcall ***v37)(_QWORD); // rsi
  void (__fastcall ***v38)(_QWORD); // rsi
  int v39; // eax
  __int64 v40; // rax
  __int64 *v41; // r14
  __int64 v42; // r15
  _QWORD *v43; // rsi
  __int64 v44; // rcx
  void (__fastcall *v45)(__int64, __int128 *); // rsi
  void (__fastcall *v46)(__int64, __int128 *); // rbx
  __int64 v47; // rax
  void (__fastcall ***v48)(_QWORD); // rbx
  __int64 v49; // rax
  __int64 *v50; // rbx
  __int64 v51; // rcx
  __int64 v52; // rdx
  ULONGLONG *v53; // rdi
  char v54; // di
  char v55; // si
  char v56; // r14
  __int64 v57; // r15
  __int64 v58; // r12
  int v59; // eax
  __int64 v60; // rax
  _DWORD *v61; // rdi
  _QWORD *v62; // rsi
  __int128 v63; // [rsp+78h] [rbp-90h] BYREF
  char v64; // [rsp+88h] [rbp-80h] BYREF
  char v65; // [rsp+89h] [rbp-7Fh]
  char v66; // [rsp+8Ah] [rbp-7Eh]
  __int64 v67; // [rsp+90h] [rbp-78h] BYREF
  __int64 v68; // [rsp+98h] [rbp-70h] BYREF
  __int64 v69; // [rsp+A0h] [rbp-68h] BYREF
  void (__fastcall ***v70)(_QWORD); // [rsp+A8h] [rbp-60h] BYREF
  _Mtx_t v71; // [rsp+B0h] [rbp-58h] BYREF
  __int64 *v72; // [rsp+B8h] [rbp-50h] BYREF
  void (__fastcall ***v73)(_QWORD); // [rsp+C0h] [rbp-48h] BYREF
  __int64 v74; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v75; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v76; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v77; // [rsp+E0h] [rbp-28h] BYREF
  char ***v78; // [rsp+E8h] [rbp-20h] BYREF
  const char *v79; // [rsp+F0h] [rbp-18h]
  void **v80; // [rsp+F8h] [rbp-10h] BYREF
  __int64 (__fastcall **v81)(); // [rsp+100h] [rbp-8h]
  char *v82; // [rsp+108h] [rbp+0h]
  __int64 v83; // [rsp+110h] [rbp+8h]
  _QWORD *v84; // [rsp+118h] [rbp+10h]
  __int16 v85; // [rsp+120h] [rbp+18h]
  __int64 (__fastcall **v86)(); // [rsp+128h] [rbp+20h] BYREF
  __int64 (__fastcall **v87)(); // [rsp+130h] [rbp+28h]
  const wchar_t *v88; // [rsp+138h] [rbp+30h]
  __int64 v89; // [rsp+140h] [rbp+38h]
  _Mtx_t *v90; // [rsp+148h] [rbp+40h]
  __int16 v91; // [rsp+150h] [rbp+48h]
  __int64 v92; // [rsp+158h] [rbp+50h]
  __int64 v93; // [rsp+160h] [rbp+58h]
  char v94[8]; // [rsp+168h] [rbp+60h] BYREF
  __int64 *v95; // [rsp+170h] [rbp+68h]
  __int64 *v96; // [rsp+178h] [rbp+70h]
  char *v97; // [rsp+180h] [rbp+78h]
  __int64 *v98; // [rsp+188h] [rbp+80h]
  __int64 *v99; // [rsp+190h] [rbp+88h]
  _QWORD v100[5]; // [rsp+198h] [rbp+90h] BYREF
  __int16 v101; // [rsp+1C0h] [rbp+B8h]
  __int128 v102; // [rsp+1E0h] [rbp+D8h] BYREF
  char *v103; // [rsp+1F0h] [rbp+E8h]
  _UNKNOWN *retaddr; // [rsp+230h] [rbp+128h] BYREF

  result = &retaddr;
  v69 = a1;
  switch ( *a2 )
  {
    case 0xA:
      *(_QWORD *)&v63 = &off_1810F3250;
      *((_QWORD *)&v63 + 1) = "COSRS/CS::GetRevisionsInBatch_Started";
      sub_1802DD458(19169755, &v63, 100);
      (*(void (__fastcall **)(_QWORD, void (__fastcall ****)(_QWORD)))(**(_QWORD **)(a1 + 392) + 200LL))(
        *(_QWORD *)(a1 + 392),
        &v73);
      if ( v73 )
      {
        v46 = *(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a1 + 96LL);
        v63 = 0;
        __ExceptionPtrCreate(&v63);
        v46(a1, &v63);
      }
      else
      {
        sub_180269F54(&v80, *(_QWORD *)(a1 + 392) + 352LL);
        v70 = 0;
        v47 = *(_QWORD *)(a1 + 392);
        v48 = *(void (__fastcall ****)(_QWORD))(v47 + 16);
        if ( v48 )
          (**v48)(*(_QWORD *)(v47 + 16));
        v70 = v48;
        sub_1805AF99C(&v72, *(_QWORD *)(*(_QWORD *)(a1 + 392) + 144LL), &v70, &v80);
        v49 = 0;
        v68 = 0;
        v50 = v72;
        if ( v72 )
        {
          (*(void (__fastcall **)(__int64 *, __int64 *, __int64 *))*v72)(v72, &qword_1811E9AA8, &v68);
          v49 = v68;
        }
        v51 = 0;
        v68 = 0;
        v52 = *(_QWORD *)(a1 + 464);
        *(_QWORD *)(a1 + 464) = v49;
        if ( v52 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
          v51 = v68;
        }
        if ( v51 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
        QueryUnbiasedInterruptTime((PULONGLONG)(a1 + 488));
        v53 = (ULONGLONG *)sub_1802DCEF0(8);
        *(_QWORD *)&v63 = v53;
        if ( v53 )
          *v53 = GetTickCount64();
        else
          v53 = 0;
        sub_1805AF974(a1 + 456, v53);
        v54 = *(_BYTE *)(a1 + 483);
        v55 = *(_BYTE *)(a1 + 481);
        v56 = *(_BYTE *)(a1 + 480);
        v57 = *(_QWORD *)(a1 + 472);
        v58 = *(_QWORD *)(a1 + 464);
        v59 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v69 + 392) + 144LL))(*(_QWORD *)(v69 + 392));
        v60 = sub_180372A44(
                (unsigned int)&v77,
                v59,
                v58,
                (int)v69 + 400,
                1,
                1,
                (__int64)&xmmword_1811EBB90,
                v57,
                v56,
                v55,
                0,
                v54);
        v61 = (_DWORD *)v69;
        v62 = (_QWORD *)(v69 + 448);
        sub_1802D3794(v69 + 448, v60);
        if ( v77 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
        sub_180031EC0(v61 + 94, *v62);
        v61[96] = 11;
        v61[97] = 12;
        v61[93] = 3;
        if ( v50 )
          (*(void (__fastcall **)(__int64 *))(*v50 + 16))(v50);
      }
      return (_UNKNOWN **)sub_1801F1CC8(v73);
    case 0xB:
      if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 448) + 112LL))(*(_QWORD *)(a1 + 448)) )
      {
        QueryUnbiasedInterruptTime((PULONGLONG)(a1 + 496));
        v71 = (_Mtx_t)(100LL * (*(_QWORD *)(a1 + 496) - *(_QWORD *)(a1 + 488)) / 1000000);
        v100[0] = off_18106CA00;
        v100[1] = off_181072FB8;
        v100[2] = L"CSITimeInMSec";
        v100[3] = -1;
        v100[4] = &v71;
        v101 = 4;
        v15 = *(_QWORD **)(a1 + 456);
        if ( v15 )
          v16 = sub_1802DC464(*v15);
        else
          v16 = 0;
        v69 = v16;
        v86 = off_1810960B8;
        v87 = off_1810D3080;
        v88 = L"TimeInMSec";
        v89 = -1;
        v90 = (_Mtx_t *)&v69;
        v91 = 4;
        v78 = &off_1810F3250;
        v79 = "ExecuteQueryChangesSuccess";
        *(_QWORD *)&v63 = &v86;
        *((_QWORD *)&v63 + 1) = v100;
        v80 = &Mso::Logging::CompositeStructuredTrace::`vftable';
        v81 = (__int64 (__fastcall **)())&v63;
        v82 = &v64;
        Jot::Logging::details::SendStructuredTraceTag(19169757, 50, &v78, &v80);
      }
      v68 = 0;
      v17 = (Csi **)(a1 + 472);
      if ( *(_QWORD *)(a1 + 472) )
      {
        Csi::CreateKnowledge((Csi *)&v68, v14);
        (*(void (__fastcall **)(__int64, Csi *))(*(_QWORD *)v68 + 80LL))(v68, *v17);
      }
      else
      {
        Csi::CreateKnowledge((Csi *)(a1 + 472), v14);
      }
      v18 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 448) + 96LL))(*(_QWORD *)(a1 + 448));
      v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 120LL))(v18);
      v102 = *(_OWORD *)v19;
      LODWORD(v103) = *(_DWORD *)(v19 + 16);
      if ( (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 448) + 144LL))(*(_QWORD *)(a1 + 448)) )
      {
        v20 = *v17;
        v21 = *(void (__fastcall **)(Csi *, __int64))(*(_QWORD *)*v17 + 80LL);
        v22 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 448) + 144LL))(*(_QWORD *)(a1 + 448));
        v21(v20, v22);
        v67 = 0;
        if ( Csi::FGetCellKnowledge(*v17, (struct Csi::IKnowledge *)&v67, v23) )
          (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v67 + 72LL))(v67, &xmmword_1811D4F20);
        if ( v67 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
      }
      (*(void (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)(a1 + 448) + 152LL))(*(_QWORD *)(a1 + 448), &v63);
      if ( BYTE8(v63) )
      {
        v24 = sub_180078530(&v63);
        sub_18074BDCC(*(_QWORD *)(a1 + 392), a1 + 400, 0, v24);
      }
      v25 = 0;
      v92 = 0;
      v26 = 0;
      v93 = 0;
      if ( *(_BYTE *)(a1 + 483) )
      {
        v27 = *(void (__fastcall ****)(_QWORD, __int64 *, __int64 *))(a1 + 448);
        v28 = 0;
        v67 = 0;
        if ( v27 )
        {
          (**v27)(v27, &qword_1811EC3C0, &v67);
          v28 = v67;
        }
        v29 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 96LL))(v28);
        v25 = v29;
        if ( v29 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 8LL))(v29);
        v92 = v25;
        v30 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v67 + 104LL))(v67);
        v26 = v30;
        if ( v30 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 8LL))(v30);
        v93 = v26;
        if ( v67 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
      }
      v31 = *(void (__fastcall ****)(_QWORD, __int64 *, void (__fastcall ****)(_QWORD)))(a1 + 464);
      v70 = 0;
      if ( v31 )
        (**v31)(v31, &qword_1811E9A98, &v70);
      v72 = &v67;
      v67 = 0;
      if ( v26 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 8LL))(v26);
      v67 = v26;
      v95 = &v74;
      v74 = 0;
      if ( v25 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 8LL))(v25);
      v74 = v25;
      v64 = *(_BYTE *)(a1 + 483);
      v96 = &v75;
      v75 = 0;
      sub_180031EC0(&v75, *(_QWORD *)(a1 + 464));
      v65 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 448) + 160LL))(*(_QWORD *)(a1 + 448));
      v66 = *(_BYTE *)(a1 + 482);
      v97 = v94;
      v32 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 448) + 136LL))(*(_QWORD *)(a1 + 448));
      v33 = (struct _Mtx_internal_imp_t *)v32;
      if ( v32 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 8LL))(v32);
      v71 = v33;
      v34 = sub_1802B1130(v94, &v71);
      v98 = &v77;
      v35 = sub_18008D184(&v77, a1 + 472);
      v99 = &v76;
      v76 = 0;
      v36 = v68;
      if ( v68 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 8LL))(v68);
      v76 = v36;
      v78 = (char ***)&v73;
      v73 = 0;
      v37 = *(void (__fastcall ****)(_QWORD))(*(_QWORD *)(a1 + 392) + 16LL);
      if ( v37 )
        (**v37)(*(_QWORD *)(*(_QWORD *)(a1 + 392) + 16LL));
      v73 = v37;
      *(_QWORD *)&v63 = &v69;
      v69 = 0;
      v38 = v70;
      if ( v70 )
        (*v70)[1](v70);
      v69 = (__int64)v38;
      v39 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 392) + 136LL))(*(_QWORD *)(a1 + 392));
      sub_1805AEBCC(
        (unsigned int)&v72,
        v39,
        (unsigned int)&v69,
        (unsigned int)&v73,
        (__int64)&v76,
        v35,
        v34,
        (__int64)&v102,
        v66,
        v65,
        (__int64)&v75,
        v64,
        (__int64)&v74,
        (__int64)&v67);
      if ( v71 )
        (*(void (__fastcall **)(_Mtx_t))(*(_QWORD *)v71 + 16LL))(v71);
      v40 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 448) + 104LL))(*(_QWORD *)(a1 + 448));
      v41 = v72;
      if ( v40 )
      {
        v42 = *(_QWORD *)(a1 + 392) + 152LL;
        *(_QWORD *)&v63 = v42;
        v71 = (_Mtx_t)(v42 + 88);
        sub_1802DE0C0(v42 + 88);
        *((_QWORD *)&v63 + 1) = v42;
        v43 = **(_QWORD ***)(v42 + 16);
        while ( v43 != *(_QWORD **)(v42 + 16) )
        {
          v44 = v43[5];
          v43 = (_QWORD *)*v43;
          sub_1805AF3B4(v44, v41);
        }
        Mtx_unlock(v71);
      }
      sub_1805AEEE0(*(_QWORD *)(a1 + 392), v41);
      v45 = *(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a1 + 96LL);
      v63 = 0;
      __ExceptionPtrCreate(&v63);
      v45(a1, &v63);
      result = (_UNKNOWN **)sub_1801F1CC8(v41);
      if ( v70 )
        result = (_UNKNOWN **)((__int64 (__fastcall *)(_QWORD))(*v70)[2])(v70);
      if ( v26 )
        result = (_UNKNOWN **)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      if ( v25 )
        result = (_UNKNOWN **)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      if ( v68 )
        return (_UNKNOWN **)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
      break;
    case 0xC:
      QueryUnbiasedInterruptTime((PULONGLONG)(a1 + 496));
      v71 = (_Mtx_t)(100LL * (*(_QWORD *)(a1 + 496) - *(_QWORD *)(a1 + 488)) / 1000000);
      v86 = off_18106CA00;
      v87 = off_181072FB8;
      v88 = L"CSITimeInMSec";
      v89 = -1;
      v90 = &v71;
      v91 = 4;
      v4 = *(_QWORD **)(a1 + 456);
      if ( v4 )
        v5 = sub_1802DC464(*v4);
      else
        v5 = 0;
      v70 = (void (__fastcall ***)(_QWORD))v5;
      v80 = (void **)off_1810960B8;
      v81 = off_1810D3080;
      v82 = (char *)L"TimeInMSec";
      v83 = -1;
      v84 = &v70;
      v85 = 4;
      v78 = &off_1810F3250;
      v79 = "ExecuteQueryChangesFailure";
      *(_QWORD *)&v63 = &v80;
      *((_QWORD *)&v63 + 1) = &v86;
      *(_QWORD *)&v102 = &Mso::Logging::CompositeStructuredTrace::`vftable';
      *((_QWORD *)&v102 + 1) = &v63;
      v103 = &v64;
      Jot::Logging::details::SendStructuredTraceTag(19169760, 50, &v78, &v102);
      (*(void (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)(a1 + 448) + 152LL))(*(_QWORD *)(a1 + 448), &v63);
      if ( BYTE8(v63) )
      {
        v6 = sub_180078530(&v63);
        sub_18074BDCC(*(_QWORD *)(a1 + 392), a1 + 400, 0, v6);
      }
      v7 = *(_QWORD *)(a1 + 392);
      v8 = (const void *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 448) + 80LL))(*(_QWORD *)(a1 + 448));
      v63 = 0;
      __ExceptionPtrCopy(&v63, v8);
      v9 = sub_18036E3C4(&v63, v7);
      v10 = *(_QWORD *)a1;
      if ( v9 )
      {
        v11 = sub_1808ABD70(v100, 19169762);
        v12 = (__int128 *)sub_1808D9644(&v63, v11);
      }
      else
      {
        v13 = (const void *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 448) + 80LL))(*(_QWORD *)(a1 + 448));
        v63 = 0;
        __ExceptionPtrCopy(&v63, v13);
        v12 = &v63;
      }
      return (_UNKNOWN **)(*(__int64 (__fastcall **)(__int64, __int128 *))(v10 + 96))(a1, v12);
  }
  return result;
}

```

## disassembly

```asm
0x1805adfc0  mov     rax, rsp
0x1805adfc3  mov     [rax+10h], rbx
0x1805adfc7  mov     [rax+18h], rsi
0x1805adfcb  mov     [rax+20h], rdi
0x1805adfcf  push    rbp
0x1805adfd0  push    r12
0x1805adfd2  push    r13
0x1805adfd4  push    r14
0x1805adfd6  push    r15
0x1805adfd8  lea     rbp, [rax-128h]
0x1805adfdf  sub     rsp, 200h
0x1805adfe6  mov     rax, cs:__security_cookie
0x1805adfed  xor     rax, rsp
0x1805adff0  mov     [rbp+120h+var_30], rax
0x1805adff7  mov     r12, rcx
0x1805adffa  mov     [rbp+120h+var_188], rcx
0x1805adffe  mov     ecx, [rdx]
0x1805ae000  sub     ecx, 0Ah
0x1805ae003  jz      loc_1805AE8F8
0x1805ae009  sub     ecx, 1
0x1805ae00c  jz      loc_1805AE243
0x1805ae012  cmp     ecx, 1
0x1805ae015  jnz     loc_1805AEB9B
0x1805ae01b  lea     rbx, [r12+1F0h]
0x1805ae023  mov     rcx, rbx; UnbiasedTime
0x1805ae026  call    cs:QueryUnbiasedInterruptTime
0x1805ae02c  mov     rax, [rbx]
0x1805ae02f  sub     rax, [r12+1E8h]
0x1805ae037  imul    rcx, rax, 64h ; 'd'
0x1805ae03b  mov     rax, 431BDE82D7B634DBh
0x1805ae045  imul    rcx
0x1805ae048  sar     rdx, 12h
0x1805ae04c  mov     rax, rdx
0x1805ae04f  shr     rax, 3Fh
0x1805ae053  add     rdx, rax
0x1805ae056  mov     [rbp+120h+var_178], rdx
0x1805ae05a  lea     rax, off_18106CA00
0x1805ae061  mov     [rbp+120h+var_100], rax
0x1805ae065  lea     rax, off_181072FB8
0x1805ae06c  mov     [rbp+120h+var_F8], rax
0x1805ae070  lea     rax, aCsitimeinmsec; "CSITimeInMSec"
0x1805ae077  mov     [rbp+120h+var_F0], rax
0x1805ae07b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1805ae07f  mov     [rbp+120h+var_E8], rbx
0x1805ae083  lea     rax, [rbp+120h+var_178]
0x1805ae087  mov     [rbp+120h+var_E0], rax
0x1805ae08b  lea     edi, [rbx+5]
0x1805ae08e  mov     [rbp+120h+var_D8], di
0x1805ae092  mov     rcx, [r12+1C8h]
0x1805ae09a  xor     r13d, r13d
0x1805ae09d  test    rcx, rcx
0x1805ae0a0  jz      short loc_1805AE0AC
0x1805ae0a2  mov     rcx, [rcx]
0x1805ae0a5  call    sub_1802DC464
0x1805ae0aa  jmp     short loc_1805AE0AF
0x1805ae0ac  mov     rax, r13
0x1805ae0af  mov     [rbp+120h+var_180], rax
0x1805ae0b3  lea     rax, off_1810960B8
0x1805ae0ba  mov     [rbp+120h+var_130], rax
0x1805ae0be  lea     rax, off_1810D3080
0x1805ae0c5  mov     [rbp+120h+var_128], rax
0x1805ae0c9  lea     rax, aTimeinmsec; "TimeInMSec"
0x1805ae0d0  mov     [rbp+120h+var_120], rax
0x1805ae0d4  mov     [rbp+120h+var_118], rbx
0x1805ae0d8  lea     rax, [rbp+120h+var_180]
0x1805ae0dc  mov     [rbp+120h+var_110], rax
0x1805ae0e0  mov     [rbp+120h+var_108], di
0x1805ae0e4  lea     rax, off_1810F3250
0x1805ae0eb  mov     [rbp+120h+var_140], rax
0x1805ae0ef  lea     rax, aExecutequerych; "ExecuteQueryChangesFailure"
0x1805ae0f6  mov     [rbp+120h+var_138], rax
0x1805ae0fa  lea     rax, [rbp+120h+var_130]
0x1805ae0fe  mov     qword ptr [rsp+220h+var_1B8+8], rax
0x1805ae103  lea     rax, [rbp+120h+var_100]
0x1805ae107  mov     [rsp+220h+var_1A8], rax
0x1805ae10c  lea     rax, ??_7CompositeStructuredTrace@Logging@Mso@@6B@; const Mso::Logging::CompositeStructuredTrace::`vftable'
0x1805ae113  mov     qword ptr [rbp+120h+var_48], rax
0x1805ae11a  lea     rax, [rsp+220h+var_1B8+8]
0x1805ae11f  mov     qword ptr [rbp+120h+var_48+8], rax
0x1805ae126  lea     rax, [rbp+120h+var_1A0]
0x1805ae12a  mov     [rbp+120h+var_38], rax
0x1805ae131  lea     r9, [rbp+120h+var_48]
0x1805ae138  lea     r8, [rbp+120h+var_140]
0x1805ae13c  mov     edx, 32h ; '2'
0x1805ae141  mov     ecx, 12481E0h
0x1805ae146  call    ?SendStructuredTraceTag@details@Logging@Jot@@YAXKW4Severity@2Mso@@AEBUEventName@Telemetry@5@AEBUIStructuredTrace@25@@Z; Jot::Logging::details::SendStructuredTraceTag(ulong,Mso::Logging::Severity,Mso::Telemetry::EventName const &,Mso::Logging::IStructuredTrace const &)
0x1805ae14b  mov     rcx, [r12+1C0h]
0x1805ae153  mov     rax, [rcx]
0x1805ae156  lea     rdx, [rsp+220h+var_1B8+8]
0x1805ae15b  mov     rax, [rax+98h]
0x1805ae162  call    cs:__guard_dispatch_icall_fptr
0x1805ae168  cmp     byte ptr [rsp+220h+var_1A8], r13b
0x1805ae16d  jz      short loc_1805AE194
0x1805ae16f  lea     rcx, [rsp+220h+var_1B8+8]
0x1805ae174  call    sub_180078530
0x1805ae179  lea     rdx, [r12+190h]
0x1805ae181  mov     r9, rax
0x1805ae184  xor     r8d, r8d
0x1805ae187  mov     rcx, [r12+188h]
0x1805ae18f  call    sub_18074BDCC
0x1805ae194  mov     rbx, [r12+188h]
0x1805ae19c  mov     rcx, [r12+1C0h]
0x1805ae1a4  mov     rax, [rcx]
0x1805ae1a7  mov     rax, [rax+50h]
0x1805ae1ab  call    cs:__guard_dispatch_icall_fptr
0x1805ae1b1  xorps   xmm0, xmm0
0x1805ae1b4  movdqu  [rsp+220h+var_1B8+8], xmm0
0x1805ae1ba  mov     rdx, rax
0x1805ae1bd  lea     rcx, [rsp+220h+var_1B8+8]
0x1805ae1c2  call    cs:?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1805ae1c8  mov     rdx, rbx
0x1805ae1cb  lea     rcx, [rsp+220h+var_1B8+8]
0x1805ae1d0  call    sub_18036E3C4
0x1805ae1d5  mov     rbx, [r12]
0x1805ae1d9  test    al, al
0x1805ae1db  jz      short loc_1805AE210
0x1805ae1dd  mov     edx, 12481E2h
0x1805ae1e2  lea     rcx, [rbp+120h+var_90]
0x1805ae1e9  call    sub_1808ABD70
0x1805ae1ee  mov     rdx, rax
0x1805ae1f1  lea     rcx, [rsp+220h+var_1B8+8]
0x1805ae1f6  call    sub_1808D9644
0x1805ae1fb  mov     rdx, rax
0x1805ae1fe  mov     rcx, r12
0x1805ae201  mov     rax, [rbx+60h]
0x1805ae205  call    cs:__guard_dispatch_icall_fptr
0x1805ae20b  jmp     loc_1805AEB9B
0x1805ae210  mov     rcx, [r12+1C0h]
0x1805ae218  mov     rax, [rcx]
0x1805ae21b  mov     rax, [rax+50h]
0x1805ae21f  call    cs:__guard_dispatch_icall_fptr
0x1805ae225  xorps   xmm0, xmm0
0x1805ae228  movdqu  [rsp+220h+var_1B8+8], xmm0
0x1805ae22e  mov     rdx, rax
0x1805ae231  lea     rcx, [rsp+220h+var_1B8+8]
0x1805ae236  call    cs:?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1805ae23c  lea     rdx, [rsp+220h+var_1B8+8]
0x1805ae241  jmp     short loc_1805AE1FE
0x1805ae243  mov     rcx, [r12+1C0h]
0x1805ae24b  mov     rax, [rcx]
0x1805ae24e  mov     rax, [rax+70h]
0x1805ae252  call    cs:__guard_dispatch_icall_fptr
0x1805ae258  xor     r13d, r13d
0x1805ae25b  test    al, al
0x1805ae25d  jz      loc_1805AE399
0x1805ae263  lea     rbx, [r12+1F0h]
0x1805ae26b  mov     rcx, rbx; UnbiasedTime
0x1805ae26e  call    cs:QueryUnbiasedInterruptTime
0x1805ae274  mov     rax, [rbx]
0x1805ae277  sub     rax, [r12+1E8h]
0x1805ae27f  imul    rcx, rax, 64h ; 'd'
0x1805ae283  mov     rax, 431BDE82D7B634DBh
0x1805ae28d  imul    rcx
0x1805ae290  sar     rdx, 12h
0x1805ae294  mov     rax, rdx
0x1805ae297  shr     rax, 3Fh
0x1805ae29b  add     rdx, rax
0x1805ae29e  mov     [rbp+120h+var_178], rdx
0x1805ae2a2  lea     rax, off_18106CA00
0x1805ae2a9  mov     [rbp+120h+var_90], rax
0x1805ae2b0  lea     rax, off_181072FB8
0x1805ae2b7  mov     [rbp+120h+var_88], rax
0x1805ae2be  lea     rax, aCsitimeinmsec; "CSITimeInMSec"
0x1805ae2c5  mov     [rbp+120h+var_80], rax
0x1805ae2cc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1805ae2d0  mov     [rbp+120h+var_78], rbx
0x1805ae2d7  lea     rax, [rbp+120h+var_178]
0x1805ae2db  mov     [rbp+120h+var_70], rax
0x1805ae2e2  lea     edi, [rbx+5]
0x1805ae2e5  mov     [rbp+120h+var_68], di
0x1805ae2ec  mov     rcx, [r12+1C8h]
0x1805ae2f4  test    rcx, rcx
0x1805ae2f7  jz      short loc_1805AE303
0x1805ae2f9  mov     rcx, [rcx]
0x1805ae2fc  call    sub_1802DC464
0x1805ae301  jmp     short loc_1805AE306
0x1805ae303  mov     rax, r13
0x1805ae306  mov     [rbp+120h+var_188], rax
0x1805ae30a  lea     rax, off_1810960B8
0x1805ae311  mov     [rbp+120h+var_100], rax
0x1805ae315  lea     rax, off_1810D3080
0x1805ae31c  mov     [rbp+120h+var_F8], rax
0x1805ae320  lea     rax, aTimeinmsec; "TimeInMSec"
0x1805ae327  mov     [rbp+120h+var_F0], rax
0x1805ae32b  mov     [rbp+120h+var_E8], rbx
0x1805ae32f  lea     rax, [rbp+120h+var_188]
0x1805ae333  mov     [rbp+120h+var_E0], rax
0x1805ae337  mov     [rbp+120h+var_D8], di
0x1805ae33b  lea     rax, off_1810F3250
0x1805ae342  mov     [rbp+120h+var_140], rax
0x1805ae346  lea     rax, aExecutequerych_0; "ExecuteQueryChangesSuccess"
0x1805ae34d  mov     [rbp+120h+var_138], rax
0x1805ae351  lea     rax, [rbp+120h+var_100]
0x1805ae355  mov     qword ptr [rsp+220h+var_1B8+8], rax
0x1805ae35a  lea     rax, [rbp+120h+var_90]
0x1805ae361  mov     [rsp+220h+var_1A8], rax
0x1805ae366  lea     rax, ??_7CompositeStructuredTrace@Logging@Mso@@6B@; const Mso::Logging::CompositeStructuredTrace::`vftable'
0x1805ae36d  mov     [rbp+120h+var_130], rax
0x1805ae371  lea     rax, [rsp+220h+var_1B8+8]
0x1805ae376  mov     [rbp+120h+var_128], rax
0x1805ae37a  lea     rax, [rbp+120h+var_1A0]
0x1805ae37e  mov     [rbp+120h+var_120], rax
0x1805ae382  lea     r9, [rbp+120h+var_130]
0x1805ae386  lea     r8, [rbp+120h+var_140]
0x1805ae38a  mov     edx, 32h ; '2'
0x1805ae38f  mov     ecx, 12481DDh
0x1805ae394  call    ?SendStructuredTraceTag@details@Logging@Jot@@YAXKW4Severity@2Mso@@AEBUEventName@Telemetry@5@AEBUIStructuredTrace@25@@Z; Jot::Logging::details::SendStructuredTraceTag(ulong,Mso::Logging::Severity,Mso::Telemetry::EventName const &,Mso::Logging::IStructuredTrace const &)
0x1805ae399  mov     [rbp+120h+var_190], r13
0x1805ae39d  lea     rsi, [r12+1D8h]
0x1805ae3a5  cmp     [rsi], r13
0x1805ae3a8  jz      short loc_1805AE3CA
0x1805ae3aa  lea     rcx, [rbp+120h+var_190]
0x1805ae3ae  call    cs:?CreateKnowledge@Csi@@YAXPEAPEAUIKnowledge@1@@Z; Csi::CreateKnowledge(Csi::IKnowledge * *)
0x1805ae3b4  mov     rcx, [rbp+120h+var_190]
0x1805ae3b8  mov     rax, [rcx]
0x1805ae3bb  mov     rdx, [rsi]
0x1805ae3be  mov     rax, [rax+50h]
0x1805ae3c2  call    cs:__guard_dispatch_icall_fptr
0x1805ae3c8  jmp     short loc_1805AE3D3
0x1805ae3ca  mov     rcx, rsi
0x1805ae3cd  call    cs:?CreateKnowledge@Csi@@YAXPEAPEAUIKnowledge@1@@Z; Csi::CreateKnowledge(Csi::IKnowledge * *)
0x1805ae3d3  mov     rcx, [r12+1C0h]
0x1805ae3db  mov     rax, [rcx]
0x1805ae3de  mov     rax, [rax+60h]
0x1805ae3e2  call    cs:__guard_dispatch_icall_fptr
0x1805ae3e8  mov     rdx, rax
0x1805ae3eb  mov     rcx, [rax]
0x1805ae3ee  mov     rax, [rcx+78h]
0x1805ae3f2  mov     rcx, rdx
0x1805ae3f5  call    cs:__guard_dispatch_icall_fptr
0x1805ae3fb  movups  xmm0, xmmword ptr [rax]
0x1805ae3fe  movups  [rbp+120h+var_48], xmm0
0x1805ae405  mov     eax, [rax+10h]
0x1805ae408  mov     dword ptr [rbp+120h+var_38], eax
0x1805ae40e  mov     rcx, [r12+1C0h]
0x1805ae416  mov     rax, [rcx]
0x1805ae419  mov     rax, [rax+90h]
0x1805ae420  call    cs:__guard_dispatch_icall_fptr
0x1805ae426  test    rax, rax
0x1805ae429  jz      short loc_1805AE4A0
0x1805ae42b  mov     rdi, [rsi]
0x1805ae42e  mov     rax, [rdi]
0x1805ae431  mov     rbx, [rax+50h]
0x1805ae435  mov     rcx, [r12+1C0h]
0x1805ae43d  mov     rdx, [rcx]
0x1805ae440  mov     rax, [rdx+90h]
0x1805ae447  call    cs:__guard_dispatch_icall_fptr
0x1805ae44d  mov     rdx, rax
0x1805ae450  mov     rcx, rdi
0x1805ae453  mov     rax, rbx
0x1805ae456  call    cs:__guard_dispatch_icall_fptr
0x1805ae45c  mov     [rbp+120h+var_198], r13
0x1805ae460  lea     rdx, [rbp+120h+var_198]
0x1805ae464  mov     rcx, [rsi]
0x1805ae467  call    cs:?FGetCellKnowledge@Csi@@YA_NPEAUIKnowledge@1@PEAPEAUICellKnowledge@CsiCell@@@Z; Csi::FGetCellKnowledge(Csi::IKnowledge *,CsiCell::ICellKnowledge * *)
0x1805ae46d  test    al, al
0x1805ae46f  jz      short loc_1805AE48A
0x1805ae471  mov     rcx, [rbp+120h+var_198]
0x1805ae475  mov     rax, [rcx]
0x1805ae478  lea     rdx, xmmword_1811D4F20
0x1805ae47f  mov     rax, [rax+48h]
0x1805ae483  call    cs:__guard_dispatch_icall_fptr
0x1805ae489  nop
0x1805ae48a  mov     rcx, [rbp+120h+var_198]
0x1805ae48e  test    rcx, rcx
0x1805ae491  jz      short loc_1805AE4A0
0x1805ae493  mov     rax, [rcx]
0x1805ae496  mov     rax, [rax+10h]
0x1805ae49a  call    cs:__guard_dispatch_icall_fptr
0x1805ae4a0  mov     rcx, [r12+1C0h]
0x1805ae4a8  mov     rax, [rcx]
0x1805ae4ab  lea     rdx, [rsp+220h+var_1B8+8]
0x1805ae4b0  mov     rax, [rax+98h]
0x1805ae4b7  call    cs:__guard_dispatch_icall_fptr
0x1805ae4bd  cmp     byte ptr [rsp+220h+var_1A8], r13b
0x1805ae4c2  jz      short loc_1805AE4E9
0x1805ae4c4  lea     rcx, [rsp+220h+var_1B8+8]
0x1805ae4c9  call    sub_180078530
0x1805ae4ce  lea     rdx, [r12+190h]
0x1805ae4d6  mov     r9, rax
0x1805ae4d9  xor     r8d, r8d
0x1805ae4dc  mov     rcx, [r12+188h]
0x1805ae4e4  call    sub_18074BDCC
0x1805ae4e9  mov     rdi, r13
0x1805ae4ec  mov     [rbp+120h+var_D0], r13
0x1805ae4f0  mov     rbx, r13
0x1805ae4f3  mov     [rbp+120h+var_C8], rbx
0x1805ae4f7  cmp     [r12+1E3h], r13b
0x1805ae4ff  jz      loc_1805AE5A3
0x1805ae505  mov     r9, [r12+1C0h]
0x1805ae50d  mov     rcx, r13
0x1805ae510  mov     [rbp+120h+var_198], rcx
0x1805ae514  test    r9, r9
0x1805ae517  jz      short loc_1805AE537
0x1805ae519  mov     rax, [r9]
0x1805ae51c  lea     r8, [rbp+120h+var_198]
0x1805ae520  lea     rdx, qword_1811EC3C0
0x1805ae527  mov     rcx, r9
0x1805ae52a  mov     rax, [rax]
0x1805ae52d  call    cs:__guard_dispatch_icall_fptr
  ... truncated ...
```
