# CASFDataUnitParserv1::ParseDataUnit(ulong,uchar *,ushort,_ASF_DATA_DESCRIPTOR *,ushort *)

- ea: `0x18002bce0`
- end: `0x18002c5ab`
- name: `?ParseDataUnit@CASFDataUnitParserv1@@UEAAJKPEAEGPEAU_ASF_DATA_DESCRIPTOR@@PEAG@Z`
- size: `2251`
- prototype: `__int64 __fastcall(CASFDataUnitParserv1 *this, unsigned int, unsigned __int8 *, unsigned __int16, struct _ASF_DATA_DESCRIPTOR *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `13`
- tags: ``

## callees

- `0x1800015d0`
- `0x180001ee8`
- `0x1800021dc`
- `0x18000220c`
- `0x180003a68`
- `0x18002b760`
- `0x18002b7ac`
- `0x18002bce0`
- `0x18002e900`
- `0x18002ee78`
- `0x18002f044`
- `0x18003ee8c`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFDataUnitParserv1::ParseDataUnit(
        CASFDataUnitParserv1 *this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned __int16 a4,
        struct _ASF_DATA_DESCRIPTOR *a5,
        unsigned __int16 *a6)
{
  __int64 v8; // r12
  struct IWMSCriticalSection *v10; // rdx
  int v11; // edi
  __int64 v12; // rcx
  __int64 v13; // r14
  bool v14; // zf
  unsigned int v15; // r15d
  int v16; // eax
  unsigned __int8 *v17; // r14
  __int64 v18; // rcx
  __int64 v19; // rcx
  int ASFVarFieldSize; // eax
  unsigned int v21; // r10d
  __int64 v22; // rcx
  int v23; // r9d
  unsigned int v24; // r9d
  int v25; // edx
  unsigned int v26; // eax
  unsigned __int8 *v27; // r11
  unsigned __int8 *v28; // rbx
  unsigned __int8 *v29; // rcx
  unsigned int ASFVarField; // eax
  unsigned __int8 *v31; // rcx
  char v32; // r9
  __int64 v33; // r11
  unsigned int v34; // edx
  unsigned __int8 *v35; // r8
  __int64 v36; // rax
  unsigned int v37; // r15d
  __int64 v38; // rcx
  unsigned int v39; // ecx
  __int64 v40; // xmm6_8
  int v41; // ebx
  char *v42; // r12
  int v43; // eax
  __int64 v44; // rcx
  int v45; // eax
  __int16 v46; // ax
  __int64 v47; // rcx
  unsigned __int8 *v48; // rdx
  char v49; // al
  __int64 v50; // rcx
  __int64 v51; // rdx
  int v52; // eax
  __int64 v53; // rcx
  __int64 v54; // r14
  __int64 v55; // rdx
  unsigned __int8 *v56; // r14
  unsigned int v57; // eax
  __int64 v58; // r11
  unsigned int v59; // r8d
  unsigned __int8 *v60; // rcx
  unsigned __int8 *v61; // r14
  unsigned __int16 v62; // dx
  unsigned __int16 v63; // dx
  CASFDataUnitParserBase *v64; // rcx
  __int64 v65; // rcx
  __int64 v66; // r11
  unsigned int v67; // r12d
  unsigned __int8 *v68; // rcx
  unsigned int v69; // r9d
  int v70; // edx
  unsigned __int8 *v71; // r8
  __int64 v72; // r11
  __int64 v73; // rbx
  unsigned __int8 *v74; // rax
  __int128 v75; // xmm1
  __int128 v76; // xmm0
  __int128 v77; // xmm1
  __int128 v78; // xmm0
  __int64 v79; // r11
  __int64 v80; // rcx
  int v81; // r8d
  char *v82; // r8
  __int64 v83; // r11
  int v84; // r10d
  int v85; // edx
  __int64 v86; // rcx
  char v88; // [rsp+40h] [rbp-C0h]
  char v89; // [rsp+41h] [rbp-BFh]
  unsigned __int8 v90; // [rsp+42h] [rbp-BEh]
  unsigned int v91; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v92; // [rsp+48h] [rbp-B8h] BYREF
  char v93; // [rsp+4Ch] [rbp-B4h]
  char v94; // [rsp+4Dh] [rbp-B3h]
  unsigned __int16 v95; // [rsp+4Eh] [rbp-B2h]
  int v96; // [rsp+50h] [rbp-B0h]
  unsigned int v97; // [rsp+54h] [rbp-ACh]
  unsigned int v98; // [rsp+58h] [rbp-A8h]
  struct CASFDataUnitParserBase::STREAM_INFO *v99; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v100; // [rsp+68h] [rbp-98h]
  int v101; // [rsp+6Ch] [rbp-94h]
  int v102; // [rsp+70h] [rbp-90h]
  int v103; // [rsp+74h] [rbp-8Ch]
  unsigned int v104; // [rsp+78h] [rbp-88h]
  int v105; // [rsp+7Ch] [rbp-84h]
  unsigned int v106; // [rsp+80h] [rbp-80h]
  int v107; // [rsp+84h] [rbp-7Ch]
  __int64 v108; // [rsp+88h] [rbp-78h] BYREF
  int v109; // [rsp+90h] [rbp-70h]
  CASFDataUnitParserBase *v110; // [rsp+98h] [rbp-68h]
  int v111; // [rsp+A0h] [rbp-60h]
  int v112; // [rsp+A4h] [rbp-5Ch]
  unsigned int v113; // [rsp+A8h] [rbp-58h]
  char *v114; // [rsp+B0h] [rbp-50h]
  unsigned __int8 *v115; // [rsp+B8h] [rbp-48h]
  char v116[8]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v117; // [rsp+C8h] [rbp-38h]
  int v118; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int v119; // [rsp+D4h] [rbp-2Ch]
  int v120; // [rsp+D8h] [rbp-28h]
  int v121; // [rsp+E8h] [rbp-18h]
  char v122; // [rsp+EDh] [rbp-13h]
  char v123; // [rsp+EEh] [rbp-12h]
  unsigned __int8 v124; // [rsp+EFh] [rbp-11h]
  char v125; // [rsp+F0h] [rbp-10h]
  unsigned int v126; // [rsp+F8h] [rbp-8h]
  int v127; // [rsp+108h] [rbp+8h]
  unsigned int v128; // [rsp+10Ch] [rbp+Ch]
  unsigned __int16 v129; // [rsp+114h] [rbp+14h]
  char v130; // [rsp+118h] [rbp+18h]
  unsigned int v131; // [rsp+128h] [rbp+28h]
  unsigned int v132; // [rsp+130h] [rbp+30h] BYREF
  __int64 v133; // [rsp+138h] [rbp+38h] BYREF
  int v134; // [rsp+140h] [rbp+40h]

  v8 = a2;
  v10 = (struct IWMSCriticalSection *)*((_QWORD *)this + 4);
  v110 = this;
  v95 = a4;
  v113 = v8;
  v117 = a6;
  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v116, v10);
  if ( !*((_QWORD *)this + 2) )
  {
    v11 = -1072887818;
    goto LABEL_102;
  }
  if ( !a5 && a4 || !a6 || !a3 )
  {
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v116);
    return 2147942487LL;
  }
  *a6 = 0;
  memset_0(&v118, 0, 0x60u);
  v11 = CBasePacketFilter::ParsePacket(a3, v8, (struct PACKET_PARSE_INFO *)&v118);
  if ( v11 < 0 )
  {
LABEL_102:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v116);
    return (unsigned int)v11;
  }
  v11 = 1;
  v105 = v121;
  if ( v120 && v118 )
  {
    v100 = v131;
    v88 = v130;
  }
  else
  {
    v88 = 0;
    v100 = 1;
    if ( v121 )
    {
      v12 = v119;
      if ( v119 >= (unsigned int)v8 )
      {
        v11 = -1072887856;
        goto LABEL_102;
      }
      v14 = (a3[v119] & 0x3F) == 0;
      v88 = a3[v119] >> 6;
      v100 = a3[v119] & 0x3F;
      if ( v14 )
      {
        v11 = -1072887795;
        goto LABEL_102;
      }
      v13 = v119 + 1;
      goto LABEL_12;
    }
  }
  v13 = v119;
LABEL_12:
  v96 = v13;
  if ( v120 && v118 )
  {
    *a6 = 0;
    goto LABEL_102;
  }
  v132 = 0;
  v106 = v126;
  if ( v126 )
  {
    v15 = v126;
    v132 = v126;
  }
  else
  {
    v16 = (*(__int64 (__fastcall **)(CASFDataUnitParserv1 *, unsigned int *))(*(_QWORD *)this + 136LL))(this, &v132);
    if ( v16 < 0 )
    {
LABEL_24:
      v11 = v16;
      goto LABEL_102;
    }
    v15 = v132;
  }
  if ( !v105 && (unsigned int)v8 < v15 || (v17 = &a3[v13], (int)v17 - (int)a3 > (unsigned int)v8) )
  {
LABEL_101:
    v11 = -1072886849;
    goto LABEL_102;
  }
  LOBYTE(v12) = v122;
  v98 = 0;
  v94 = v122;
  GetASFVarFieldSize(v12);
  LOBYTE(v18) = v125;
  v93 = v125;
  GetASFVarFieldSize(v18);
  LOBYTE(v19) = v124;
  v90 = v124;
  ASFVarFieldSize = GetASFVarFieldSize(v19);
  LOBYTE(v22) = v123;
  v24 = ASFVarFieldSize + v23;
  v25 = v127;
  v26 = 0;
  v104 = v24;
  v27 = v17;
  v101 = v127;
  v89 = v123;
  while ( 1 )
  {
    v97 = v26;
    if ( v26 >= v100 )
      break;
    v28 = &v27[v24];
    v92 = 0;
    LODWORD(v99) = 0;
    if ( (_BYTE)v22 )
    {
      v29 = &v28[(unsigned int)GetASFVarFieldSize(v22)];
      if ( v29 > &a3[v8] )
        goto LABEL_101;
      LOBYTE(v29) = v89;
      ASFVarField = GetASFVarField(v29, v28, &v92);
      v22 = v92;
      LODWORD(v99) = ASFVarField;
      v25 = v101;
      v28 += v92 + (unsigned __int64)ASFVarField;
    }
    if ( v105 )
    {
      LOBYTE(v22) = v88;
      v31 = &v28[(unsigned int)GetASFVarFieldSize(v22)];
      if ( v31 > &a3[v8] )
        goto LABEL_101;
      LOBYTE(v31) = v32;
      v33 = (unsigned int)GetASFVarField(v31, v28, &v92);
      v28 += v92;
    }
    else if ( v106 )
    {
      v33 = (unsigned __int16)(v106 + (_WORD)v27 - (_WORD)v28 - v96 - v25);
    }
    else
    {
      v33 = v15 + (_DWORD)v27 - (_DWORD)v28 - v25 - v96;
    }
    v21 = v98;
    if ( (_DWORD)v99 == 1 )
    {
      v34 = v33;
      v35 = v28;
      while ( v34 )
      {
        if ( v35 + 1 > &a3[v8] )
          goto LABEL_101;
        v22 = *v35;
        v36 = (unsigned int)(v22 + 1);
        if ( (unsigned int)v36 > v34 )
          goto LABEL_101;
        v35 += v36;
        v34 += -1 - v22;
        v98 = ++v21;
      }
    }
    else
    {
      v21 = ++v98;
    }
    v27 = &v28[v33];
    if ( (int)v27 - (int)a3 > (unsigned int)v8 )
      goto LABEL_101;
    v24 = v104;
    v26 = v97 + 1;
    LOBYTE(v22) = v89;
    v25 = v101;
  }
  if ( v21 > 0xFFFF || (*v117 = v21, v95 < (unsigned __int16)v21) )
  {
    v11 = -1072887799;
    goto LABEL_102;
  }
  v37 = 0;
  v133 = 0;
  v134 = 0;
  v38 = *((_QWORD *)v110 + 2);
  v108 = 0;
  v109 = 0;
  ASFGetTimeBase(v38, 0, &v133);
  ASFTimeToSendTime32(&v133, v128, &v108);
  v39 = 0;
  v40 = v108;
  LODWORD(v99) = v132;
  v112 = 8 * v90 - 1;
  v95 = v129;
  v111 = v109;
  while ( 1 )
  {
    v104 = v39;
    if ( v39 >= v100 || v37 >= v98 )
      break;
    v41 = (int)v17;
    v91 = 0;
    v107 = 0;
    v108 = 88LL * v37;
    v42 = (char *)a5 + v108;
    v114 = (char *)a5 + v108;
    memset_0((char *)a5 + v108, 0, 0x58u);
    v43 = v111;
    LOBYTE(v44) = v90;
    *(_QWORD *)(v42 + 12) = v40;
    *((_DWORD *)v42 + 5) = v43;
    *((_WORD *)v42 + 40) = v95;
    v45 = (int)v99;
    *(_DWORD *)v42 = (_DWORD)v99;
    *((_DWORD *)v42 + 1) = v45;
    v46 = GetASFVarField(v44, v17, &v91);
    LOBYTE(v47) = v93;
    v48 = &v17[v91];
    *((_WORD *)v42 + 4) = v46;
    v49 = GetASFVarField(v47, v48, &v91);
    LOBYTE(v50) = v94;
    v42[10] = v49;
    v52 = GetASFVarField(v50, v91 + v51, &v91);
    v54 = v91;
    LODWORD(v99) = v52;
    *((_DWORD *)v42 + 11) = v52;
    v56 = (unsigned __int8 *)(v55 + v54);
    v103 = 0;
    v102 = 0;
    v97 = 0;
    if ( v89 )
    {
      LOBYTE(v53) = v89;
      v57 = GetASFVarField(v53, v56, &v91);
      v59 = v57;
      v60 = &v56[v91];
      v92 = v57;
      v61 = v60;
      if ( v57 < 8 )
      {
        if ( v57 == 1 )
        {
          v107 = 1;
          ASFTimeToPresTime32(&v133, (unsigned int)v99, v58);
          v59 = v92;
          v97 = *((_DWORD *)v42 + 11);
          *((_DWORD *)v42 + 11) = 0;
        }
        else
        {
          *(_QWORD *)v58 = 0;
          *(_DWORD *)(v58 + 8) = 0;
        }
      }
      else
      {
        v61 = v60 + 8;
        v103 = *(_DWORD *)v60;
        v97 = *((_DWORD *)v60 + 1);
        ASFTimeToPresTime32(&v133, v97, v58);
        v59 = v92 - 8;
        v102 = 1;
        v92 -= 8;
      }
      v115 = v61;
      v56 = &v61[v59];
    }
    else
    {
      v115 = 0;
      *(_QWORD *)(v42 + 28) = 0;
      *((_DWORD *)v42 + 9) = 0;
      v92 = 0;
    }
    v62 = 1 << v112;
    *((_DWORD *)v42 + 6) = 0;
    if ( (v62 & *((_WORD *)v42 + 4)) != 0 )
      *((_DWORD *)v42 + 6) = 2;
    v63 = *((_WORD *)v42 + 4) & ~v62;
    v64 = v110;
    v99 = 0;
    *(_WORD *)((char *)a5 + v108 + 8) = v63;
    if ( (int)CASFDataUnitParserBase::GetStreamInfo(v64, v63, &v99) >= 0 && v99 && *((_DWORD *)v99 + 13) )
      *((_DWORD *)v42 + 6) |= 2u;
    v65 = v37;
    v66 = 88LL * v37;
    LODWORD(v99) = v132;
    if ( v105 )
    {
      LOBYTE(v65) = v88;
      v67 = GetASFVarField(v65, v56, &v91);
      v65 = v37;
      v56 += v91;
    }
    else if ( v106 )
    {
      v67 = (unsigned __int16)(v106 + v41 - (_WORD)v56 - v96 - v101);
    }
    else
    {
      v67 = v41 - (_DWORD)v56 - v101 - v96 + v132;
    }
    v14 = v107 == 0;
    *(_DWORD *)((char *)a5 + v66 + 64) = v67;
    if ( !v14 )
    {
      v68 = v56;
      v102 = v37;
      v17 = &v56[v67];
      v69 = v37;
      while ( v67 )
      {
        v70 = *v68;
        v103 = v70;
        if ( v70 + 1 > v67 )
          goto LABEL_101;
        v71 = v68 + 1;
        v108 = (__int64)(v68 + 1);
        if ( v37 > v69 )
        {
          v72 = 88LL * v37;
          v73 = 88LL * (v37 - 1);
          v74 = v115;
          v75 = *(_OWORD *)((char *)a5 + v73 + 16);
          *(_OWORD *)((char *)a5 + v72) = *(_OWORD *)((char *)a5 + v73);
          v76 = *(_OWORD *)((char *)a5 + v73 + 32);
          *(_OWORD *)((char *)a5 + v72 + 16) = v75;
          v77 = *(_OWORD *)((char *)a5 + v73 + 48);
          *(_OWORD *)((char *)a5 + v72 + 32) = v76;
          v78 = *(_OWORD *)((char *)a5 + v73 + 64);
          *(_OWORD *)((char *)a5 + v72 + 48) = v77;
          *(_QWORD *)&v77 = *(_QWORD *)((char *)a5 + v73 + 80);
          *(_OWORD *)((char *)a5 + v72 + 64) = v78;
          *(_QWORD *)((char *)a5 + v72 + 80) = v77;
          ASFTimeToPresTime32(&v133, v97 + *v74 * (v37 - v69), (char *)a5 + v72 + 28);
          *(_DWORD *)((char *)a5 + v79 + 24) |= 8u;
          *(_DWORD *)((char *)a5 + v73 + 24) |= 8u;
          ++*((_BYTE *)a5 + v79 + 10);
          v70 = v103;
          v71 = (unsigned __int8 *)v108;
          v69 = v102;
        }
        v80 = 88LL * v37;
        v67 += -1 - v70;
        *(_DWORD *)((char *)a5 + v80 + 64) = v70;
        *(_QWORD *)((char *)a5 + v80 + 72) = v71;
        v68 = &v71[(unsigned __int8)v70];
        ++v37;
      }
      goto LABEL_95;
    }
    *((_QWORD *)a5 + 11 * v65 + 9) = v56;
    v17 = &v56[v67];
    if ( v102 )
    {
      v81 = v103;
LABEL_84:
      if ( v81 != v67 )
      {
        *((_DWORD *)a5 + 22 * v37 + 6) |= 4u;
        *((_DWORD *)a5 + 22 * v37 + 12) = v81;
      }
      goto LABEL_86;
    }
    if ( *((_DWORD *)a5 + 22 * v37 + 11) )
    {
      v81 = 0;
      goto LABEL_84;
    }
LABEL_86:
    v82 = v114;
    if ( v37 )
    {
      v83 = 88LL * (v37 - 1);
      v84 = *(_DWORD *)((char *)a5 + v83 + 24);
      v85 = *((_DWORD *)a5 + 22 * v37 + 6);
      if ( (((unsigned __int8)v85 | *((_BYTE *)a5 + v83 + 24)) & 4) == 0
        && *(_WORD *)((char *)a5 + v83 + 8) == *((_WORD *)v114 + 4)
        && (v85 & 2) == 0 )
      {
        *((_DWORD *)v114 + 6) = v85 | 8;
        *(_DWORD *)((char *)a5 + v83 + 24) = v84 | 8;
      }
    }
    if ( v92 )
    {
      v16 = (*(__int64 (__fastcall **)(CASFDataUnitParserBase *, _QWORD, _QWORD, unsigned __int8 *, unsigned int, char *))(*(_QWORD *)v110 + 144LL))(
              v110,
              *((_QWORD *)v110 + 2),
              *((unsigned __int16 *)v82 + 4),
              v115,
              v92,
              v82);
      if ( v16 < 0 )
        goto LABEL_24;
      LODWORD(v99) = v132;
    }
    ++v37;
LABEL_95:
    LODWORD(v8) = v113;
    if ( (int)v17 - (int)a3 > v113 )
      goto LABEL_101;
    v39 = v104 + 1;
  }
  v86 = *((_QWORD *)v110 + 3);
  if ( v86 )
    (*(void (__fastcall **)(__int64, unsigned __int8 *, _QWORD, _QWORD, struct _ASF_DATA_DESCRIPTOR *))(*(_QWORD *)v86 + 88LL))(
      v86,
      a3,
      (unsigned int)v8,
      *v117,
      a5);
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v116);
  return 0;
}

```

## disassembly

```asm
0x18002bce0  mov     rax, rsp
0x18002bce3  mov     [rax+20h], rbx
0x18002bce7  push    rbp
0x18002bce8  push    rsi
0x18002bce9  push    rdi
0x18002bcea  push    r12
0x18002bcec  push    r13
0x18002bcee  push    r14
0x18002bcf0  push    r15
0x18002bcf2  lea     rbp, [rsp-60h]
0x18002bcf7  sub     rsp, 160h
0x18002bcfe  movaps  xmmword ptr [rax-48h], xmm6
0x18002bd02  mov     rax, cs:__security_cookie
0x18002bd09  xor     rax, rsp
0x18002bd0c  mov     [rbp+90h+var_48], rax
0x18002bd10  mov     r15, [rbp+90h+arg_28]
0x18002bd17  mov     rbx, rcx
0x18002bd1a  mov     rsi, [rbp+90h+arg_20]
0x18002bd21  movzx   edi, r9w
0x18002bd25  mov     r12d, edx
0x18002bd28  mov     r13, r8
0x18002bd2b  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x18002bd2f  mov     [rbp+90h+var_F8], rcx
0x18002bd33  lea     rcx, [rbp+90h+var_D0]; this
0x18002bd37  mov     [rsp+190h+var_142], r9w
0x18002bd3d  mov     [rbp+90h+var_E8], r12d
0x18002bd41  mov     [rbp+90h+var_C8], r15
0x18002bd45  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18002bd4a  xor     r14d, r14d
0x18002bd4d  cmp     [rbx+10h], r14
0x18002bd51  jnz     short loc_18002BD5D
0x18002bd53  mov     edi, 0C00D07F6h
0x18002bd58  jmp     loc_18002C564
0x18002bd5d  test    rsi, rsi
0x18002bd60  jnz     short loc_18002BD6B
0x18002bd62  test    di, di
0x18002bd65  jnz     loc_18002C571
0x18002bd6b  test    r15, r15
0x18002bd6e  jz      loc_18002C571
0x18002bd74  test    r13, r13
0x18002bd77  jz      loc_18002C571
0x18002bd7d  xor     edx, edx; Val
0x18002bd7f  mov     [r15], r14w
0x18002bd83  lea     rcx, [rbp+90h+var_C0]; void *
0x18002bd87  lea     r8d, [rdx+60h]; Size
0x18002bd8b  call    memset_0
0x18002bd90  lea     r8, [rbp+90h+var_C0]; struct PACKET_PARSE_INFO *
0x18002bd94  mov     edx, r12d; unsigned int
0x18002bd97  mov     rcx, r13; unsigned __int8 *
0x18002bd9a  call    ?ParsePacket@CBasePacketFilter@@SAJPEAEKPEAUPACKET_PARSE_INFO@@@Z; CBasePacketFilter::ParsePacket(uchar *,ulong,PACKET_PARSE_INFO *)
0x18002bd9f  mov     edi, eax
0x18002bda1  test    eax, eax
0x18002bda3  js      loc_18002C564
0x18002bda9  mov     r8d, [rbp+90h+var_B8]
0x18002bdad  mov     edi, 1
0x18002bdb2  mov     eax, [rbp+90h+var_A8]
0x18002bdb5  mov     edx, [rbp+90h+var_C0]
0x18002bdb8  mov     [rsp+190h+var_114], eax
0x18002bdbc  test    r8d, r8d
0x18002bdbf  jz      short loc_18002BDF0
0x18002bdc1  test    edx, edx
0x18002bdc3  jz      short loc_18002BDF0
0x18002bdc5  mov     eax, [rbp+90h+var_68]
0x18002bdc8  mov     [rsp+190h+var_128], eax
0x18002bdcc  mov     al, [rbp+90h+var_78]
0x18002bdcf  mov     [rsp+190h+var_150], al
0x18002bdd3  mov     r14d, [rbp+90h+var_BC]
0x18002bdd7  mov     [rsp+190h+var_140], r14d
0x18002bddc  test    r8d, r8d
0x18002bddf  jz      short loc_18002BE39
0x18002bde1  test    edx, edx
0x18002bde3  jz      short loc_18002BE39
0x18002bde5  xor     eax, eax
0x18002bde7  mov     [r15], ax
0x18002bdeb  jmp     loc_18002C564
0x18002bdf0  mov     [rsp+190h+var_150], r14b
0x18002bdf5  mov     [rsp+190h+var_128], edi
0x18002bdf9  test    eax, eax
0x18002bdfb  jz      short loc_18002BDD3
0x18002bdfd  mov     ecx, [rbp+90h+var_BC]
0x18002be00  cmp     ecx, r12d
0x18002be03  jb      short loc_18002BE0F
0x18002be05  mov     edi, 0C00D07D0h
0x18002be0a  jmp     loc_18002C564
0x18002be0f  movzx   eax, byte ptr [rcx+r13]
0x18002be14  mov     r9b, al
0x18002be17  shr     r9b, 6
0x18002be1b  and     eax, 3Fh
0x18002be1e  mov     [rsp+190h+var_150], r9b
0x18002be23  mov     [rsp+190h+var_128], eax
0x18002be27  jnz     short loc_18002BE33
0x18002be29  mov     edi, 0C00D080Dh
0x18002be2e  jmp     loc_18002C564
0x18002be33  lea     r14d, [rcx+1]
0x18002be37  jmp     short loc_18002BDD7
0x18002be39  mov     eax, [rbp+90h+var_98]
0x18002be3c  mov     [rbp+90h+var_60], 0
0x18002be43  mov     [rbp+90h+var_110], eax
0x18002be46  test    eax, eax
0x18002be48  jz      short loc_18002BE52
0x18002be4a  mov     r15d, eax
0x18002be4d  mov     [rbp+90h+var_60], eax
0x18002be50  jmp     short loc_18002BE77
0x18002be52  mov     rax, [rbx]
0x18002be55  lea     rdx, [rbp+90h+var_60]
0x18002be59  mov     rcx, rbx
0x18002be5c  mov     rax, [rax+88h]
0x18002be63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be68  test    eax, eax
0x18002be6a  jns     short loc_18002BE73
0x18002be6c  mov     edi, eax
0x18002be6e  jmp     loc_18002C564
0x18002be73  mov     r15d, [rbp+90h+var_60]
0x18002be77  cmp     [rsp+190h+var_114], 0
0x18002be7c  jnz     short loc_18002BE87
0x18002be7e  cmp     r12d, r15d
0x18002be81  jb      loc_18002C55F
0x18002be87  add     r14, r13
0x18002be8a  mov     eax, r14d
0x18002be8d  sub     eax, r13d
0x18002be90  cmp     eax, r12d
0x18002be93  ja      loc_18002C55F
0x18002be99  mov     al, [rbp+90h+var_A3]
0x18002be9c  xor     r10d, r10d
0x18002be9f  mov     cl, al
0x18002bea1  mov     [rsp+190h+var_138], r10d
0x18002bea6  mov     [rsp+190h+var_143], al
0x18002beaa  call    GetASFVarFieldSize
0x18002beaf  mov     r9d, eax
0x18002beb2  mov     al, [rbp+90h+var_A0]
0x18002beb5  mov     cl, al
0x18002beb7  mov     [rsp+190h+var_144], al
0x18002bebb  call    GetASFVarFieldSize
0x18002bec0  add     r9d, eax
0x18002bec3  mov     al, [rbp+90h+var_A1]
0x18002bec6  mov     cl, al
0x18002bec8  mov     [rsp+190h+var_14E], al
0x18002becc  call    GetASFVarFieldSize
0x18002bed1  mov     cl, [rbp+90h+var_A2]
0x18002bed4  add     r9d, eax
0x18002bed7  mov     edx, [rbp+90h+var_88]
0x18002beda  xor     eax, eax
0x18002bedc  mov     [rsp+190h+var_118], r9d
0x18002bee1  mov     r11, r14
0x18002bee4  mov     [rsp+190h+var_124], edx
0x18002bee8  mov     [rsp+190h+var_14F], cl
0x18002beec  mov     [rsp+190h+var_13C], eax
0x18002bef0  cmp     eax, [rsp+190h+var_128]
0x18002bef4  jnb     loc_18002C03A
0x18002befa  mov     ebx, r9d
0x18002befd  add     rbx, r11
0x18002bf00  mov     [rsp+190h+var_148], 0
0x18002bf08  mov     dword ptr [rsp+190h+var_130], 0
0x18002bf10  test    cl, cl
0x18002bf12  jz      short loc_18002BF50
0x18002bf14  call    GetASFVarFieldSize
0x18002bf19  mov     ecx, eax
0x18002bf1b  lea     rax, [r12+r13]
0x18002bf1f  add     rcx, rbx
0x18002bf22  cmp     rcx, rax
0x18002bf25  ja      loc_18002C55F
0x18002bf2b  mov     cl, [rsp+190h+var_14F]
0x18002bf2f  lea     r8, [rsp+190h+var_148]
0x18002bf34  mov     rdx, rbx
0x18002bf37  call    GetASFVarField
0x18002bf3c  mov     ecx, [rsp+190h+var_148]
0x18002bf40  mov     edx, eax
0x18002bf42  add     rbx, rdx
0x18002bf45  mov     dword ptr [rsp+190h+var_130], edx
0x18002bf49  mov     edx, [rsp+190h+var_124]
0x18002bf4d  add     rbx, rcx
0x18002bf50  cmp     [rsp+190h+var_114], 0
0x18002bf55  jz      short loc_18002BF92
0x18002bf57  mov     r9b, [rsp+190h+var_150]
0x18002bf5c  mov     cl, r9b
0x18002bf5f  call    GetASFVarFieldSize
0x18002bf64  mov     ecx, eax
0x18002bf66  lea     rax, [r12+r13]
0x18002bf6a  add     rcx, rbx
0x18002bf6d  cmp     rcx, rax
0x18002bf70  ja      loc_18002C55F
0x18002bf76  lea     r8, [rsp+190h+var_148]
0x18002bf7b  mov     rdx, rbx
0x18002bf7e  mov     cl, r9b
0x18002bf81  call    GetASFVarField
0x18002bf86  mov     r11d, eax
0x18002bf89  mov     eax, [rsp+190h+var_148]
0x18002bf8d  add     rbx, rax
0x18002bf90  jmp     short loc_18002BFBF
0x18002bf92  mov     eax, [rbp+90h+var_110]
0x18002bf95  test    eax, eax
0x18002bf97  jz      short loc_18002BFB1
0x18002bf99  sub     r11w, bx
0x18002bf9d  sub     r11w, word ptr [rsp+190h+var_140]
0x18002bfa3  sub     r11w, dx
0x18002bfa7  add     r11w, ax
0x18002bfab  movzx   r11d, r11w
0x18002bfaf  jmp     short loc_18002BFBF
0x18002bfb1  sub     r11d, ebx
0x18002bfb4  sub     r11d, edx
0x18002bfb7  sub     r11d, [rsp+190h+var_140]
0x18002bfbc  add     r11d, r15d
0x18002bfbf  mov     r10d, [rsp+190h+var_138]
0x18002bfc4  cmp     dword ptr [rsp+190h+var_130], edi
0x18002bfc8  jnz     short loc_18002C008
0x18002bfca  mov     edx, r11d
0x18002bfcd  mov     r8, rbx
0x18002bfd0  test    edx, edx
0x18002bfd2  jz      short loc_18002C010
0x18002bfd4  lea     rcx, [r12+r13]
0x18002bfd8  lea     rax, [r8+1]
0x18002bfdc  cmp     rax, rcx
0x18002bfdf  ja      loc_18002C55F
0x18002bfe5  movzx   ecx, byte ptr [r8]
0x18002bfe9  lea     eax, [rcx+1]
0x18002bfec  cmp     eax, edx
0x18002bfee  ja      loc_18002C55F
0x18002bff4  add     r8, rax
0x18002bff7  or      eax, 0FFFFFFFFh
0x18002bffa  sub     eax, ecx
0x18002bffc  add     edx, eax
0x18002bffe  add     r10d, edi
0x18002c001  mov     [rsp+190h+var_138], r10d
0x18002c006  jmp     short loc_18002BFD0
0x18002c008  add     r10d, edi
0x18002c00b  mov     [rsp+190h+var_138], r10d
0x18002c010  add     r11, rbx
0x18002c013  mov     eax, r11d
0x18002c016  sub     eax, r13d
0x18002c019  cmp     eax, r12d
0x18002c01c  ja      loc_18002C55F
0x18002c022  mov     eax, [rsp+190h+var_13C]
0x18002c026  mov     r9d, [rsp+190h+var_118]
0x18002c02b  add     eax, edi
0x18002c02d  mov     cl, [rsp+190h+var_14F]
0x18002c031  mov     edx, [rsp+190h+var_124]
0x18002c035  jmp     loc_18002BEEC
0x18002c03a  cmp     r10d, 0FFFFh
0x18002c041  ja      loc_18002C558
0x18002c047  mov     rax, [rbp+90h+var_C8]
0x18002c04b  mov     [rax], r10w
0x18002c04f  cmp     [rsp+190h+var_142], r10w
0x18002c055  jb      loc_18002C558
0x18002c05b  mov     rbx, [rbp+90h+var_F8]
0x18002c05f  lea     r8, [rbp+90h+var_58]
0x18002c063  xor     eax, eax
0x18002c065  xor     edx, edx
0x18002c067  xor     r15d, r15d
0x18002c06a  mov     [rbp+90h+var_58], rax
0x18002c06e  mov     [rbp+90h+var_50], eax
0x18002c071  mov     rcx, [rbx+10h]
0x18002c075  mov     [rbp+90h+var_108], rax
0x18002c079  mov     [rbp+90h+var_100], eax
0x18002c07c  call    ASFGetTimeBase
0x18002c081  mov     edx, [rbp+90h+var_84]
0x18002c084  lea     r8, [rbp+90h+var_108]
0x18002c088  lea     rcx, [rbp+90h+var_58]
0x18002c08c  call    ASFTimeToSendTime32
0x18002c091  movzx   eax, [rsp+190h+var_14E]
0x18002c096  xor     ecx, ecx
0x18002c098  mov     r9d, [rbp+90h+var_60]
0x18002c09c  movsd   xmm6, [rbp+90h+var_108]
0x18002c0a1  mov     dword ptr [rsp+190h+var_130], r9d
0x18002c0a6  lea     eax, ds:0FFFFFFFFFFFFFFFFh[rax*8]
0x18002c0ad  mov     [rbp+90h+var_EC], eax
0x18002c0b0  movzx   eax, [rbp+90h+var_7C]
0x18002c0b4  mov     [rsp+190h+var_142], ax
0x18002c0b9  mov     eax, [rbp+90h+var_100]
0x18002c0bc  mov     [rbp+90h+var_F0], eax
0x18002c0bf  mov     [rsp+190h+var_118], ecx
0x18002c0c3  cmp     ecx, [rsp+190h+var_128]
0x18002c0c7  jnb     loc_18002C51F
0x18002c0cd  cmp     r15d, [rsp+190h+var_138]
0x18002c0d2  jnb     loc_18002C51F
0x18002c0d8  xor     edx, edx; Val
0x18002c0da  mov     eax, r15d
0x18002c0dd  imul    rax, 58h ; 'X'
0x18002c0e1  mov     rbx, r14
0x18002c0e4  mov     [rsp+190h+var_14C], 0
0x18002c0ec  lea     r8d, [rdx+58h]; Size
0x18002c0f0  mov     [rbp+90h+var_10C], 0
0x18002c0f7  mov     [rbp+90h+var_108], rax
0x18002c0fb  lea     r12, [rax+rsi]
0x18002c0ff  mov     rcx, r12; void *
0x18002c102  mov     [rbp+90h+var_E0], r12
0x18002c106  call    memset_0
0x18002c10b  mov     eax, [rbp+90h+var_F0]
0x18002c10e  lea     r8, [rsp+190h+var_14C]
0x18002c113  mov     cl, [rsp+190h+var_14E]
0x18002c117  mov     rdx, r14
0x18002c11a  movsd   qword ptr [r12+0Ch], xmm6
0x18002c121  mov     [r12+14h], eax
0x18002c126  movzx   eax, [rsp+190h+var_142]
0x18002c12b  mov     [r12+50h], ax
0x18002c131  mov     eax, dword ptr [rsp+190h+var_130]
0x18002c135  mov     [r12], eax
0x18002c139  mov     [r12+4], eax
0x18002c13e  call    GetASFVarField
0x18002c143  mov     edx, [rsp+190h+var_14C]
0x18002c147  lea     r8, [rsp+190h+var_14C]
  ... truncated ...
```
