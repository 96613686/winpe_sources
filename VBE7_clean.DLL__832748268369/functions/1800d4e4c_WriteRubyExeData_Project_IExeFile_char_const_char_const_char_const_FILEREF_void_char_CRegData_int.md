# _WriteRubyExeData(Project *,IExeFile *,char const *,char const *,char const *,FILEREF *,void *,char *,CRegData *,int)

- ea: `0x1800d4e4c`
- end: `0x1800d5e2e`
- name: `?_WriteRubyExeData@@YAHPEAVProject@@PEAUIExeFile@@PEBD22PEAUFILEREF@@PEAXPEADPEAVCRegData@@H@Z`
- size: `4066`
- prototype: `__int64 __fastcall(struct Project *, struct IExeFile *, const char *, const char *, const char *, struct FILEREF *, void *, char *, struct CRegData *, int)`
- caller_count: `1`
- callee_count: `32`
- tags: `loader_planting, installer_update`

## callers

- `0x1800d3d5c`

## callees

- `0x180002e4c`
- `0x18000434c`
- `0x180004518`
- `0x180015ae8`
- `0x180015b08`
- `0x1800164ec`
- `0x180019c44`
- `0x18001a358`
- `0x18001a378`
- `0x18001a424`
- `0x18001a69c`
- `0x18001aa78`
- `0x18001ec18`
- `0x18001ec34`
- `0x180026838`
- `0x18003f828`
- `0x18003f85c`
- `0x180042964`
- `0x180046978`
- `0x18004dc94`
- `0x180058a2c`
- `0x180058b4c`
- `0x1800ca084`
- `0x1800d4d68`
- `0x1800d4e4c`
- `0x1800d61e8`
- `0x1800d6824`
- `0x1800e29a8`
- `0x1801487bc`
- `0x180379380`
- `0x180379520`
- `0x180379546`

## import_xrefs

- `MSVCR100!free` at `0x1800d5708`
- `MSVCR100!free` at `0x1800d5708`
- `MSVCR100!malloc` at `0x1800d585a`
- `MSVCR100!malloc` at `0x1800d585a`
- `MSVCR100!strtoul` at `0x1800d5b65`
- `MSVCR100!strtoul` at `0x1800d5b97`
- `MSVCR100!strtoul` at `0x1800d5b65`
- `MSVCR100!strtoul` at `0x1800d5b97`
- `MSVCR100!_msize` at `0x1800d5314`
- `MSVCR100!_msize` at `0x1800d536d`
- `MSVCR100!_msize` at `0x1800d53c6`
- `MSVCR100!_msize` at `0x1800d541f`
- `MSVCR100!_msize` at `0x1800d5314`
- `MSVCR100!_msize` at `0x1800d536d`
- `MSVCR100!_msize` at `0x1800d53c6`
- `MSVCR100!_msize` at `0x1800d541f`
- `KERNEL32!lstrlenA` at `0x1800d54b7`
- `KERNEL32!lstrlenA` at `0x1800d558a`
- `KERNEL32!lstrlenA` at `0x1800d55c6`
- `KERNEL32!lstrlenA` at `0x1800d5602`
- `KERNEL32!lstrlenA` at `0x1800d563b`
- `KERNEL32!lstrlenA` at `0x1800d5bb8`
- `KERNEL32!lstrlenA` at `0x1800d5bf2`
- `KERNEL32!lstrlenA` at `0x1800d5c2c`
- `KERNEL32!lstrlenA` at `0x1800d5c66`
- `KERNEL32!lstrlenA` at `0x1800d54b7`
- `KERNEL32!lstrlenA` at `0x1800d558a`
- `KERNEL32!lstrlenA` at `0x1800d55c6`
- `KERNEL32!lstrlenA` at `0x1800d5602`
- `KERNEL32!lstrlenA` at `0x1800d563b`
- `KERNEL32!lstrlenA` at `0x1800d5bb8`
- `KERNEL32!lstrlenA` at `0x1800d5bf2`
- `KERNEL32!lstrlenA` at `0x1800d5c2c`
- `KERNEL32!lstrlenA` at `0x1800d5c66`
- `KERNEL32!lstrcpyA` at `0x1800d5b2a`
- `KERNEL32!lstrcpyA` at `0x1800d5b47`
- `KERNEL32!lstrcpyA` at `0x1800d5b7f`
- `KERNEL32!lstrcpyA` at `0x1800d5b2a`
- `KERNEL32!lstrcpyA` at `0x1800d5b47`
- `KERNEL32!lstrcpyA` at `0x1800d5b7f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d5555`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d5716`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d5555`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d5716`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1800d551d`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1800d5531`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1800d551d`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1800d5531`

## pseudocode

```c
__int64 __fastcall _WriteRubyExeData(
        struct Project *a1,
        struct IExeFile *a2,
        const char *a3,
        const char *a4,
        const char *a5,
        struct FILEREF *a6,
        void *a7,
        char *a8,
        struct CRegData *a9,
        char a10)
{
  float v10; // xmm7_4
  struct Project *v12; // r14
  OLECHAR *v13; // r12
  __int64 v14; // rbx
  void *v15; // rsi
  int v16; // eax
  unsigned int OleCtlInfo; // eax
  CHxmodList *v18; // r15
  unsigned int v19; // esi
  struct XMOD *i; // rax
  struct XMOD *v21; // r13
  struct XMOD *v22; // rbx
  int v23; // r12d
  __int64 v24; // rdx
  int v25; // r14d
  int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  unsigned int v30; // eax
  __int64 v31; // r15
  int v32; // eax
  int v33; // eax
  UINT v34; // eax
  UINT v35; // eax
  int v36; // eax
  int v37; // eax
  int v38; // eax
  int v39; // eax
  int v40; // ebx
  void **v41; // r13
  struct GEN_PROJECT *v43; // rbx
  int v44; // eax
  int v45; // r14d
  Project *v46; // r15
  Projitem *j; // rax
  struct Projitem *v48; // rbx
  int v49; // eax
  float v50; // xmm6_4
  unsigned __int64 HProj; // rax
  int v52; // r15d
  int v53; // eax
  void **v54; // rax
  Projitem *k; // rax
  struct Projitem *v56; // rbx
  struct GEN_PROJECT *v57; // rbx
  int v58; // eax
  int v59; // ebx
  void **v60; // r15
  int v61; // eax
  int v62; // ebx
  struct Project *v63; // r15
  const CHAR *v64; // rax
  const char *v65; // rax
  const CHAR *v66; // rax
  const char *v67; // rax
  int v68; // eax
  CHAR *v69; // r14
  int v70; // eax
  int v71; // eax
  CHAR *v72; // r14
  int v73; // eax
  int v74; // eax
  CHAR *v75; // r14
  int v76; // eax
  int v77; // eax
  int v78; // r14d
  struct GEN_PROJECT *v79; // rbx
  int v80; // eax
  struct GEN_PROJECT *v81; // r8
  void *v82; // rbx
  __int64 v83; // r14
  unsigned int *v84; // [rsp+20h] [rbp-E0h]
  NAMMGR *v85; // [rsp+40h] [rbp-C0h] BYREF
  NAMMGR *v86; // [rsp+48h] [rbp-B8h] BYREF
  int v87; // [rsp+50h] [rbp-B0h] BYREF
  int v88; // [rsp+54h] [rbp-ACh] BYREF
  NAMMGR *v89; // [rsp+58h] [rbp-A8h] BYREF
  BSTR bstr; // [rsp+60h] [rbp-A0h] BYREF
  struct Project *v91; // [rsp+68h] [rbp-98h]
  __int64 v92; // [rsp+70h] [rbp-90h]
  int v93; // [rsp+78h] [rbp-88h] BYREF
  __int64 v94; // [rsp+80h] [rbp-80h]
  void *Block; // [rsp+88h] [rbp-78h]
  CHxmodList *v96; // [rsp+90h] [rbp-70h]
  char *v97; // [rsp+98h] [rbp-68h]
  LPCSTR lpString; // [rsp+A0h] [rbp-60h]
  __int64 v99; // [rsp+A8h] [rbp-58h]
  LPCSTR v100; // [rsp+B0h] [rbp-50h]
  struct CRegData *v101; // [rsp+B8h] [rbp-48h]
  void *v102; // [rsp+C0h] [rbp-40h]
  void *v103; // [rsp+C8h] [rbp-38h]
  LPCSTR v104; // [rsp+D0h] [rbp-30h]
  int v105; // [rsp+E0h] [rbp-20h] BYREF
  CHAR v106[4]; // [rsp+E4h] [rbp-1Ch] BYREF
  int v107; // [rsp+E8h] [rbp-18h]
  int v108; // [rsp+ECh] [rbp-14h]
  int v109; // [rsp+F0h] [rbp-10h]
  CHAR String1[4]; // [rsp+F4h] [rbp-Ch] BYREF
  int v111; // [rsp+F8h] [rbp-8h]
  int v112; // [rsp+FCh] [rbp-4h]
  UINT v113; // [rsp+100h] [rbp+0h]
  unsigned int ProfileInt; // [rsp+104h] [rbp+4h]
  unsigned int v115; // [rsp+108h] [rbp+8h]
  int v116; // [rsp+10Ch] [rbp+Ch]
  int v117; // [rsp+110h] [rbp+10h]
  unsigned int v118; // [rsp+120h] [rbp+20h] BYREF
  unsigned int v119; // [rsp+128h] [rbp+28h]
  int v120; // [rsp+12Ch] [rbp+2Ch]
  __int16 v121; // [rsp+130h] [rbp+30h]
  __int16 v122; // [rsp+132h] [rbp+32h]
  __int16 v123; // [rsp+134h] [rbp+34h]
  int v124; // [rsp+150h] [rbp+50h]
  int v125; // [rsp+154h] [rbp+54h]
  int v126; // [rsp+158h] [rbp+58h]
  int v127; // [rsp+15Ch] [rbp+5Ch]
  GUID v128; // [rsp+160h] [rbp+60h]
  struct _GUID v129; // [rsp+170h] [rbp+70h] BYREF
  __int128 v130; // [rsp+180h] [rbp+80h]
  __int128 v131; // [rsp+190h] [rbp+90h]
  __int128 v132; // [rsp+1A0h] [rbp+A0h]
  __int128 v133; // [rsp+1B0h] [rbp+B0h]
  int v134; // [rsp+1C0h] [rbp+C0h]
  _DWORD v135[3]; // [rsp+1C4h] [rbp+C4h] BYREF
  __int128 v136; // [rsp+1D0h] [rbp+D0h]
  __int128 v137; // [rsp+1E0h] [rbp+E0h]
  __int64 v138; // [rsp+1F4h] [rbp+F4h]
  __int16 v139; // [rsp+1FCh] [rbp+FCh]
  __int16 v140; // [rsp+1FEh] [rbp+FEh]
  __int16 v141; // [rsp+202h] [rbp+102h]
  char v142; // [rsp+204h] [rbp+104h]
  CHAR String[2048]; // [rsp+210h] [rbp+110h] BYREF

  v10 = FLOAT_5_0;
  v100 = a5;
  v102 = a7;
  v97 = a8;
  v12 = a1;
  v91 = a1;
  lpString = a4;
  v101 = a9;
  v104 = a3;
  Block = 0;
  v13 = 0;
  bstr = 0;
  v85 = 0;
  v86 = 0;
  v89 = 0;
  UpdateProgressBar(5, 0);
  v14 = (*(__int64 (__fastcall **)(struct IExeFile *, __int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)a2 + 88LL))(
          a2,
          49,
          0,
          0,
          0);
  if ( !v14 )
    goto LABEL_69;
  v92 = (*(__int64 (__fastcall **)(struct IExeFile *, __int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)a2 + 88LL))(
          a2,
          33,
          0,
          0,
          0);
  if ( !v92 )
    goto LABEL_69;
  v94 = (*(__int64 (__fastcall **)(struct IExeFile *, __int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)a2 + 88LL))(
          a2,
          33,
          0,
          0,
          0);
  if ( !v94 )
    goto LABEL_69;
  v15 = (void *)(*(__int64 (__fastcall **)(struct IExeFile *, __int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)a2 + 88LL))(
                  a2,
                  33,
                  0,
                  0,
                  0);
  v103 = v15;
  if ( !v15 )
    goto LABEL_69;
  v99 = (*(__int64 (__fastcall **)(struct IExeFile *, __int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)a2 + 88LL))(
          a2,
          49,
          0,
          0,
          0);
  if ( !v99
    || !(unsigned int)_WriteDllStubs(a2, v15, &v88, &v87)
    || !(*(unsigned int (__fastcall **)(struct IExeFile *, __int64, void *, __int64))(*(_QWORD *)a2 + 16LL))(
          a2,
          v14,
          &abStartUpCodeDll,
          17)
    || !(*(unsigned int (__fastcall **)(struct IExeFile *, __int64, __int64, _QWORD, __int64, int))(*(_QWORD *)a2 + 40LL))(
          a2,
          v14,
          13,
          0,
          105,
          17)
    || !(*(unsigned int (__fastcall **)(struct IExeFile *, __int64, __int64, _QWORD, int))(*(_QWORD *)a2 + 80LL))(
          a2,
          v14,
          7,
          v88,
          18)
    || !(*(unsigned int (__fastcall **)(struct IExeFile *, __int64, __int64, _QWORD, int))(*(_QWORD *)a2 + 80LL))(
          a2,
          v14,
          2,
          v87,
          18) )
  {
    goto LABEL_69;
  }
  (*(void (__fastcall **)(struct IExeFile *, __int64, _QWORD))(*(_QWORD *)a2 + 64LL))(a2, v14, 0);
  v16 = HrFrefOpenMem(0, 0, &v85);
  if ( v16 < 0 )
  {
    OleCtlInfo = _ErrFromHr(v16, 0xFFFFFFFF);
    if ( OleCtlInfo )
      goto LABEL_67;
  }
  v87 = 0;
  v18 = (struct Project *)((char *)v12 + 496);
  v19 = 1;
  ++Cio_cUnloadCtlsSweep;
  v96 = (struct Project *)((char *)v12 + 496);
  for ( i = CHxmodList::hxmodFirst((struct Project *)((char *)v12 + 496)); ; i = CHxmodList::hxmodNext(v18, v21) )
  {
    v21 = i;
    if ( !i )
      break;
    v22 = i;
    if ( MdlImdlOfLpmdl(*(struct MDL **)i) == 0xFF
      && !(unsigned int)CioCanUnloadCustomControl(v12, v22)
      && (*((_BYTE *)v22 + 114) & 0x40) != 0 )
    {
      v23 = 0;
      if ( *(_BYTE *)(*(_QWORD *)v22 + 95LL) == 32 && *((_QWORD *)v22 + 1) )
        v22 = (struct XMOD *)*((_QWORD *)v22 + 1);
      memset_0(&v105, 0, 0x34u);
      memset_0(&v129, 0, 0x98u);
      OleCtlInfo = _GetOleCtlInfo(v22, String, &v129, &v88, &v93, &bstr);
      if ( OleCtlInfo )
      {
        v13 = bstr;
        goto LABEL_67;
      }
      v24 = 0;
      v142 ^= (v88 ^ v142) & 1;
      v138 = *((_QWORD *)v22 + 14);
      v141 = *((_WORD *)v22 + 99);
      v139 = *((_WORD *)v22 + 104);
      v130 = *(_OWORD *)((char *)v22 + 212);
      v131 = *(_OWORD *)((char *)v22 + 228);
      v140 = *((_WORD *)v22 + 105);
      v132 = *(_OWORD *)((char *)v22 + 308);
      v133 = *(_OWORD *)((char *)v22 + 324);
      v136 = *(_OWORD *)((char *)v22 + 340);
      v137 = *(_OWORD *)((char *)v22 + 356);
      WORD1(v138) ^= (*((_WORD *)v22 + 57) ^ WORD1(v138)) & 0x80;
      do
      {
        v135[v24] = *(_DWORD *)&String[4 * v24 + 400 + v22 - (struct XMOD *)v135];
        ++v24;
      }
      while ( v24 < 3 );
      v134 = *((_DWORD *)v22 + 122);
      v25 = RelSeekFileRef(v85, 0);
      v26 = HrFrefWrite((__int64)v85, (CHAR *)&v105, 52);
      if ( v26 < 0 )
        goto LABEL_64;
      v26 = HrFrefAlign(v85);
      if ( v26 < 0 )
        goto LABEL_64;
      *(_DWORD *)v106 = RelSeekFileRef(v85, 0) - v25;
      v26 = HrFrefWrite((__int64)v85, (CHAR *)&v129, 152);
      if ( v26 < 0 )
        goto LABEL_64;
      v26 = HrFrefAlign(v85);
      if ( v26 < 0 )
        goto LABEL_64;
      if ( *((_QWORD *)v22 + 32) )
      {
        v107 = RelSeekFileRef(v85, 0) - v25;
        v27 = _msize(*((void **)v22 + 32));
        v26 = HrFrefWrite((__int64)v85, *((CHAR **)v22 + 32), v27);
        if ( v26 < 0 )
          goto LABEL_64;
        v26 = HrFrefAlign(v85);
        if ( v26 < 0 )
          goto LABEL_64;
      }
      if ( *((_QWORD *)v22 + 33) )
      {
        v108 = RelSeekFileRef(v85, 0) - v25;
        v28 = _msize(*((void **)v22 + 33));
        v26 = HrFrefWrite((__int64)v85, *((CHAR **)v22 + 33), v28);
        if ( v26 < 0 )
          goto LABEL_64;
        v26 = HrFrefAlign(v85);
        if ( v26 < 0 )
          goto LABEL_64;
      }
      if ( *((_QWORD *)v22 + 34) )
      {
        v109 = RelSeekFileRef(v85, 0) - v25;
        v29 = _msize(*((void **)v22 + 34));
        v26 = HrFrefWrite((__int64)v85, *((CHAR **)v22 + 34), v29);
        if ( v26 < 0 )
          goto LABEL_64;
        v26 = HrFrefAlign(v85);
        if ( v26 < 0 )
          goto LABEL_64;
      }
      if ( *((_QWORD *)v22 + 17) )
      {
        *(_DWORD *)String1 = RelSeekFileRef(v85, 0) - v25;
        v30 = _msize(*((void **)v22 + 17));
        v26 = HrFrefWrite((__int64)v85, *((CHAR **)v22 + 17), v30);
        if ( v26 < 0 )
          goto LABEL_64;
        v26 = HrFrefAlign(v85);
        if ( v26 < 0 )
          goto LABEL_64;
      }
      if ( *((_QWORD *)v22 + 25) )
      {
        v111 = RelSeekFileRef(v85, 0) - v25;
        v26 = HrFrefWrite((__int64)v85, *((CHAR **)v22 + 25), 32 * (unsigned int)*((unsigned __int16 *)v22 + 99));
        if ( v26 < 0 )
          goto LABEL_64;
        if ( *((_WORD *)v22 + 99) )
        {
          v31 = 0;
          while ( 1 )
          {
            v32 = lstrlenA(*(LPCSTR *)(v31 + *((_QWORD *)v22 + 25) + 16));
            v26 = HrFrefWrite((__int64)v85, *(CHAR **)(v31 + *((_QWORD *)v22 + 25) + 16), (unsigned int)(v32 + 1));
            if ( v26 < 0 )
              break;
            ++v23;
            v31 += 32;
            if ( v23 >= *((unsigned __int16 *)v22 + 99) )
            {
              v18 = v96;
              goto LABEL_47;
            }
          }
LABEL_64:
          v13 = bstr;
LABEL_65:
          OleCtlInfo = _ErrFromHrDefault(v26);
          goto LABEL_67;
        }
      }
LABEL_47:
      if ( v93 )
      {
        v33 = RelSeekFileRef(v85, 0);
        v13 = bstr;
        v112 = v33 - v25;
        v34 = SysStringByteLen(bstr);
        if ( !v34 )
          v34 = -1;
        v113 = v34;
        v35 = SysStringByteLen(v13);
        v26 = HrFrefWrite((__int64)v85, (CHAR *)v13, v35);
        if ( v26 < 0 )
          goto LABEL_65;
        SysFreeString(v13);
        v13 = 0;
        bstr = 0;
      }
      else
      {
        v13 = bstr;
      }
      if ( v88 )
      {
        ProfileInt = RelSeekFileRef(v85, 0) - v25;
        v36 = lstrlenA(*((LPCSTR *)v22 + 10));
        v26 = HrFrefWrite((__int64)v85, *((CHAR **)v22 + 10), (unsigned int)(v36 + 1));
        if ( v26 < 0 )
          goto LABEL_65;
      }
      v115 = RelSeekFileRef(v85, 0) - v25;
      v37 = lstrlenA(String);
      v26 = HrFrefWrite((__int64)v85, String, (unsigned int)(v37 + 1));
      if ( v26 < 0 )
        goto LABEL_65;
      v116 = RelSeekFileRef(v85, 0) - v25;
      v38 = lstrlenA(*((LPCSTR *)v22 + 13));
      v26 = HrFrefWrite((__int64)v85, *((CHAR **)v22 + 13), (unsigned int)(v38 + 1));
      if ( v26 < 0 )
        goto LABEL_65;
      v117 = RelSeekFileRef(v85, 0) - v25;
      v39 = lstrlenA(*((LPCSTR *)v22 + 12));
      v26 = HrFrefWrite((__int64)v85, *((CHAR **)v22 + 12), (unsigned int)(v39 + 1));
      if ( v26 < 0 )
        goto LABEL_65;
      v26 = HrFrefAlign(v85);
      if ( v26 < 0 )
        goto LABEL_65;
      v40 = RelSeekFileRef(v85, 0);
      v105 = v40 - v25;
      v26 = HrFrefSeek(v85, v25);
      if ( v26 < 0 )
        goto LABEL_65;
      v26 = HrFrefWrite((__int64)v85, (CHAR *)&v105, 52);
      if ( v26 < 0 )
        goto LABEL_65;
      v26 = HrFrefSeek(v85, v40);
      if ( v26 < 0 )
        goto LABEL_65;
      ++v87;
      v12 = v91;
    }
  }
  v43 = NAMMGR::Pgenproj(v85);
  v44 = RelSeekFileRef(v85, 0);
  if ( !(*(unsigned int (__fastcall **)(struct IExeFile *, __int64, struct GEN_PROJECT *, _QWORD))(*(_QWORD *)a2 + 16LL))(
          a2,
          v94,
          v43,
          v44) )
    goto LABEL_69;
  FrefDelete(v85);
  v85 = 0;
  v45 = 0;
  v46 = v91;
  for ( j = ProjLppiFirstProjitem(v91); ; j = ProjLppiNextProjitem(v48) )
  {
    v48 = j;
    if ( !j )
      break;
    if ( (*(_BYTE *)Projitem::GetInfo(j) & 2) != 0 )
      ++v45;
  }
  v49 = 1;
  if ( v45 )
    v49 = v45;
  v50 = 85.0 / (float)v49;
  HProj = Project::GetHProj(v46);
  OleCtlInfo = TipExeAllowCodeExec(HProj);
  v52 = 0;
  if ( OleCtlInfo )
    goto LABEL_67;
  v53 = HrFrefOpenMem(0, 0, &v89);
  if ( v53 < 0 )
  {
    OleCtlInfo = _ErrFromHr(v53, 0xFFFFFFFF);
    if ( OleCtlInfo )
      goto LABEL_67;
  }
  v54 = (void **)malloc(8LL * v45);
  v41 = v54;
  Block = v54;
  if ( !v54 )
  {
    OleCtlInfo = 7;
    goto LABEL_68;
  }
  memset_0(v54, 0, 8LL * v45);
  for ( k = ProjLppiFirstProjitem(v91); ; k = ProjLppiNextProjitem(v56) )
  {
    v56 = k;
    if ( !k )
      break;
    if ( (*(_BYTE *)Projitem::GetInfo(k) & 2) != 0 )
    {
      memset_0(&v105, 0, 0x58u);
      OleCtlInfo = _WriteFormExeData(
                     a2,
                     v56,
                     *((_QWORD *)v91 + 10) == *((_QWORD *)v56 + 7),
                     (struct EXEFORMINFO *)&v105,
                     0,
                     0,
                     &v41[v52]);
      if ( OleCtlInfo )
        goto LABEL_67;
      v105 = 88;
      v26 = HrFrefWrite((__int64)v89, (CHAR *)&v105, 88);
      if ( v26 < 0 )
        goto LABEL_65;
      v26 = HrFrefAlign(v89);
      if ( v26 < 0 )
        goto LABEL_65;
      v10 = v10 + v50;
      ++v52;
      UpdateProgressBar((int)v10, 0);
    }
  }
  v57 = NAMMGR::Pgenproj(v89);
  v58 = RelSeekFileRef(v89, 0);
  if ( !(*(unsigned int (__fastcall **)(struct IExeFile *, __int64, struct GEN_PROJECT *, _QWORD))(*(_QWORD *)a2 + 16LL))(
          a2,
          v92,
          v57,
          v58) )
    goto LABEL_69;
  FrefDelete(v89);
  v89 = 0;
  v59 = 0;
  if ( v45 > 0 )
  {
    v60 = v41;
    do
    {
      if ( *v60 )
      {
        HIDWORD(v84) = 0;
        if ( !(*(unsigned int (__fastcall **)(struct IExeFile *, __int64, __int64))(*(_QWORD *)a2 + 48LL))(
                a2,
                v92,
                88LL * v59 + 80) )
          goto LABEL_69;
      }
      ++v59;
      ++v60;
    }
    while ( v59 < v45 );
  }
  v61 = HrFrefOpenMem(0, 0, &v86);
  if ( v61 < 0 )
  {
    OleCtlInfo = _ErrFromHr(v61, 0xFFFFFFFF);
    if ( OleCtlInfo )
    {
LABEL_67:
      if ( OleCtlInfo == -1 )
      {
LABEL_69:
        v41 = (void **)Block;
        v19 = 0;
        goto LABEL_70;
      }
LABEL_68:
      Error(OleCtlInfo);
      goto LABEL_69;
    }
  }
  memset_0(&v105, 0, 0x90u);
  v62 = RelSeekFileRef(v86, 0);
  v26 = HrFrefWrite((__int64)v86, (CHAR *)&v105, 144);
  if ( v26 < 0 )
    goto LABEL_65;
  v63 = v91;
  Project::GetProjectName(v91, String, 0x7FCu);
  v120 = -1;
  v128 = GUID_NULL;
  HIWORD(v113) = 10;
  v105 = 557138518;
  *(_WORD *)v106 = 1153;
  v121 = v45;
  v119 = ((a10 & 1 | v119 & 0xC2) ^ (unsigned __int8)(2 * *((_WORD *)v63 + 104))) & 2 ^ (a10 & 1 | v119 & 0xFFFFFFC2);
  v122 = v87;
  v123 = 256;
  GetInternalCtlUsage(v63, &v118);
  if ( (unsigned int)RbyGetProfileString(0x832u, &v106[2], Rby_szNull, 14) )
  {
    ProfileInt = RbyGetProfileInt(0x841u, 1033);
    lstrcpyA(String1, "*");
    v115 = 1033;
  }
  else
  {
    v64 = IntlLpstrStringOfID(252);
    lstrcpyA(&v106[2], v64);
    v65 = IntlLpstrStringOfID(253);
    ProfileInt = strtoul(v65, 0, 16);
    v66 = IntlLpstrStringOfID(254);
    lstrcpyA(String1, v66);
    v67 = IntlLpstrStringOfID(255);
    v115 = strtoul(v67, 0, 16);
  }
  v68 = RelSeekFileRef(v86, 0);
  v69 = (CHAR *)lpString;
  v124 = v68 - v62;
  v70 = lstrlenA(lpString);
  v26 = HrFrefWrite((__int64)v86, v69, (unsigned int)(v70 + 1));
  if ( v26 < 0 )
    goto LABEL_65;
  v71 = RelSeekFileRef(v86, 0);
  v72 = (CHAR *)v104;
  v125 = v71 - v62;
  v73 = lstrlenA(v104);
  v26 = HrFrefWrite((__int64)v86, v72, (unsigned int)(v73 + 1));
  if ( v26 < 0 )
    goto LABEL_65;
  v74 = RelSeekFileRef(v86, 0);
  v75 = (CHAR *)v100;
  v126 = v74 - v62;
  v76 = lstrlenA(v100);
  v26 = HrFrefWrite((__int64)v86, v75, (unsigned int)(v76 + 1));
  if ( v26 < 0 )
    goto LABEL_65;
  v127 = RelSeekFileRef(v86, 0) - v62;
  v77 = lstrlenA(String);
  v26 = HrFrefWrite((__int64)v86, String, (unsigned int)(v77 + 1));
  if ( v26 < 0 )
    goto LABEL_65;
  v78 = RelSeekFileRef(v86, 0);
  v26 = HrFrefSeek(v86, v62);
  if ( v26 < 0 )
    goto LABEL_65;
  v26 = HrFrefWrite((__int64)v86, (CHAR *)&v105, 144);
  if ( v26 < 0 )
    goto LABEL_65;
  v26 = HrFrefSeek(v86, v78);
  if ( v26 < 0 )
    goto LABEL_65;
  v79 = NAMMGR::Pgenproj(v86);
  v80 = RelSeekFileRef(v86, 0);
  v81 = v79;
  v82 = v103;
  if ( !(*(unsigned int (__fastcall **)(struct IExeFile *, void *, struct GEN_PROJECT *, _QWORD))(*(_QWORD *)a2 + 16LL))(
          a2,
          v103,
          v81,
          v80) )
    goto LABEL_69;
  FrefDelete(v86);
  v86 = 0;
  if ( v102 )
  {
    HIDWORD(v84) = 0;
    if ( !(*(unsigned int (__fastcall **)(struct IExeFile *, void *, __int64))(*(_QWORD *)a2 + 48LL))(a2, v82, 56) )
      goto LABEL_69;
  }
  if ( v97 )
  {
    if ( *v97 )
    {
      LODWORD(v84) = 18;
      if ( !(*(unsigned int (__fastcall **)(struct IExeFile *, char *, void *, __int64, unsigned int *))(*(_QWORD *)a2 + 128LL))(
              a2,
              v97,
              v82,
              48,
              v84) )
        goto LABEL_69;
    }
  }
  if ( !(*(unsigned int (__fastcall **)(struct IExeFile *, void *, __int64, __int64, _QWORD, int))(*(_QWORD *)a2 + 48LL))(
          a2,
          v82,
          96,
          v94,
          0,
          18) )
    goto LABEL_69;
  if ( !(*(unsigned int (__fastcall **)(struct IExeFile *, void *, __int64, __int64, _QWORD, int))(*(_QWORD *)a2 + 48LL))(
          a2,
          v82,
          88,
          v92,
          0,
          18) )
    goto LABEL_69;
  v83 = v99;
  if ( !(*(unsigned int (__fastcall **)(struct IExeFile *, void *, __int64, __int64, _QWORD, int))(*(_QWORD *)a2 + 48LL))(
          a2,
          v82,
          104,
          v99,
          0,
          18)
    || !(*(unsigned int (__fastcall **)(struct IExeFile *, __int64, _QWORD, _QWORD))(*(_QWORD *)a2 + 16LL))(
          a2,
          v83,
          *(_QWORD *)v101,
          *((unsigned int *)v101 + 3)) )
  {
    goto LABEL_69;
  }
LABEL_70:
  if ( v41 )
    free(v41);
  if ( v13 )
    SysFreeString(v13);
  if ( v85 )
    FrefDelete(v85);
  if ( v86 )
    FrefDelete(v86);
  if ( v89 )
    FrefDelete(v89);
  return v19;
}

```

## disassembly

```asm
0x1800d4e4c  push    rbp
0x1800d4e4e  push    rbx
0x1800d4e4f  push    rsi
0x1800d4e50  push    rdi
0x1800d4e51  push    r12
0x1800d4e53  push    r13
0x1800d4e55  push    r14
0x1800d4e57  push    r15
0x1800d4e59  lea     rbp, [rsp-948h]
0x1800d4e61  mov     eax, 0A48h
0x1800d4e66  call    _alloca_probe
0x1800d4e6b  sub     rsp, rax
0x1800d4e6e  movaps  [rsp+0A80h+var_50], xmm6
0x1800d4e76  movaps  [rsp+0A80h+var_60], xmm7
0x1800d4e7e  mov     rax, cs:__security_cookie
0x1800d4e85  xor     rax, rsp
0x1800d4e88  mov     [rbp+980h+var_70], rax
0x1800d4e8f  mov     rax, [rbp+980h+arg_20]
0x1800d4e96  movss   xmm7, cs:__real@40a00000
0x1800d4e9e  xor     r15d, r15d
0x1800d4ea1  mov     [rbp+980h+var_9D0], rax
0x1800d4ea5  mov     rax, [rbp+980h+arg_30]
0x1800d4eac  mov     rdi, rdx
0x1800d4eaf  mov     [rbp+980h+var_9C0], rax
0x1800d4eb3  mov     rax, [rbp+980h+arg_38]
0x1800d4eba  xor     edx, edx; char *
0x1800d4ebc  mov     [rbp+980h+var_9E8], rax
0x1800d4ec0  mov     rax, [rbp+980h+arg_40]
0x1800d4ec7  mov     r14, rcx
0x1800d4eca  mov     [rsp+0A80h+var_A18], rcx
0x1800d4ecf  lea     ecx, [rdx+5]; int
0x1800d4ed2  mov     [rbp+980h+lpString], r9
0x1800d4ed6  mov     [rbp+980h+var_9C8], rax
0x1800d4eda  mov     [rbp+980h+var_9B0], r8
0x1800d4ede  mov     [rbp+980h+Block], r15
0x1800d4ee2  mov     r12d, r15d
0x1800d4ee5  mov     [rsp+0A80h+bstr], r15
0x1800d4eea  mov     [rsp+0A80h+var_A40], r15
0x1800d4eef  mov     [rsp+0A80h+var_A38], r15
0x1800d4ef4  mov     [rsp+0A80h+var_A28], r15
0x1800d4ef9  call    ?UpdateProgressBar@@YAXJPEBD@Z; UpdateProgressBar(long,char const *)
0x1800d4efe  mov     r11, [rdi]
0x1800d4f01  lea     r13d, [r15+31h]
0x1800d4f05  xor     r9d, r9d
0x1800d4f08  xor     r8d, r8d
0x1800d4f0b  mov     rcx, rdi
0x1800d4f0e  mov     edx, r13d
0x1800d4f11  mov     [rsp+0A80h+var_A60], r15
0x1800d4f16  call    qword ptr [r11+58h]
0x1800d4f1a  mov     rbx, rax
0x1800d4f1d  test    rax, rax
0x1800d4f20  jz      loc_1800D56F9
0x1800d4f26  mov     r10, [rdi]
0x1800d4f29  lea     esi, [r15+21h]
0x1800d4f2d  xor     r9d, r9d
0x1800d4f30  xor     r8d, r8d
0x1800d4f33  mov     rcx, rdi
0x1800d4f36  mov     edx, esi
0x1800d4f38  mov     [rsp+0A80h+var_A60], r15
0x1800d4f3d  call    qword ptr [r10+58h]
0x1800d4f41  mov     [rsp+0A80h+var_A10], rax
0x1800d4f46  test    rax, rax
0x1800d4f49  jz      loc_1800D56F9
0x1800d4f4f  mov     r10, [rdi]
0x1800d4f52  xor     r9d, r9d
0x1800d4f55  xor     r8d, r8d
0x1800d4f58  mov     edx, esi
0x1800d4f5a  mov     rcx, rdi
0x1800d4f5d  mov     [rsp+0A80h+var_A60], r15
0x1800d4f62  call    qword ptr [r10+58h]
0x1800d4f66  mov     [rbp+980h+var_A00], rax
0x1800d4f6a  test    rax, rax
0x1800d4f6d  jz      loc_1800D56F9
0x1800d4f73  mov     r10, [rdi]
0x1800d4f76  xor     r9d, r9d
0x1800d4f79  xor     r8d, r8d
0x1800d4f7c  mov     edx, esi
0x1800d4f7e  mov     rcx, rdi
0x1800d4f81  mov     [rsp+0A80h+var_A60], r15
0x1800d4f86  call    qword ptr [r10+58h]
0x1800d4f8a  mov     rsi, rax
0x1800d4f8d  mov     [rbp+980h+var_9B8], rax
0x1800d4f91  test    rax, rax
0x1800d4f94  jz      loc_1800D56F9
0x1800d4f9a  mov     r10, [rdi]
0x1800d4f9d  xor     r9d, r9d
0x1800d4fa0  xor     r8d, r8d
0x1800d4fa3  mov     edx, r13d
0x1800d4fa6  mov     rcx, rdi
0x1800d4fa9  mov     [rsp+0A80h+var_A60], r15
0x1800d4fae  call    qword ptr [r10+58h]
0x1800d4fb2  mov     [rbp+980h+var_9D8], rax
0x1800d4fb6  test    rax, rax
0x1800d4fb9  jz      loc_1800D56F9
0x1800d4fbf  lea     r9, [rsp+0A80h+var_A30]; int *
0x1800d4fc4  lea     r8, [rsp+0A80h+var_A2C]; int *
0x1800d4fc9  mov     rdx, rsi; void *
0x1800d4fcc  mov     rcx, rdi; struct IExeFile *
0x1800d4fcf  call    ?_WriteDllStubs@@YAHPEAUIExeFile@@PEAXPEAJ2@Z; _WriteDllStubs(IExeFile *,void *,long *,long *)
0x1800d4fd4  test    eax, eax
0x1800d4fd6  jz      loc_1800D56F9
0x1800d4fdc  mov     r10, [rdi]
0x1800d4fdf  lea     esi, [r15+11h]
0x1800d4fe3  lea     r8, ?abStartUpCodeDll@@3PAEA; uchar near * abStartUpCodeDll
0x1800d4fea  mov     r9d, esi
0x1800d4fed  mov     rdx, rbx
0x1800d4ff0  mov     rcx, rdi
0x1800d4ff3  call    qword ptr [r10+10h]
0x1800d4ff7  test    eax, eax
0x1800d4ff9  jz      loc_1800D56F9
0x1800d4fff  mov     rax, [rdi]
0x1800d5002  lea     r8d, [r15+0Dh]
0x1800d5006  xor     r9d, r9d
0x1800d5009  mov     rdx, rbx
0x1800d500c  mov     rcx, rdi
0x1800d500f  mov     dword ptr [rsp+0A80h+var_A58], esi
0x1800d5013  mov     [rsp+0A80h+var_A60], 69h ; 'i'
0x1800d501c  call    qword ptr [rax+28h]
0x1800d501f  test    eax, eax
0x1800d5021  jz      loc_1800D56F9
0x1800d5027  mov     rax, [rdi]
0x1800d502a  movsxd  r9, [rsp+0A80h+var_A2C]
0x1800d502f  lea     esi, [r15+12h]
0x1800d5033  lea     r8d, [r15+7]
0x1800d5037  mov     rdx, rbx
0x1800d503a  mov     rcx, rdi
0x1800d503d  mov     dword ptr [rsp+0A80h+var_A60], esi
0x1800d5041  call    qword ptr [rax+50h]
0x1800d5044  test    eax, eax
0x1800d5046  jz      loc_1800D56F9
0x1800d504c  mov     rax, [rdi]
0x1800d504f  movsxd  r9, [rsp+0A80h+var_A30]
0x1800d5054  lea     r8d, [r15+2]
0x1800d5058  mov     rdx, rbx
0x1800d505b  mov     rcx, rdi
0x1800d505e  mov     dword ptr [rsp+0A80h+var_A60], esi
0x1800d5062  call    qword ptr [rax+50h]
0x1800d5065  test    eax, eax
0x1800d5067  jz      loc_1800D56F9
0x1800d506d  mov     rax, [rdi]
0x1800d5070  xor     r8d, r8d
0x1800d5073  mov     rdx, rbx
0x1800d5076  mov     rcx, rdi
0x1800d5079  call    qword ptr [rax+40h]
0x1800d507c  lea     r8, [rsp+0A80h+var_A40]; struct FILEREF **
0x1800d5081  xor     edx, edx; unsigned int
0x1800d5083  xor     ecx, ecx; void *
0x1800d5085  call    ?HrFrefOpenMem@@YAJPEAXKPEAPEAUFILEREF@@@Z; HrFrefOpenMem(void *,ulong,FILEREF * *)
0x1800d508a  test    eax, eax
0x1800d508c  jns     short loc_1800D50A0
0x1800d508e  or      edx, 0FFFFFFFFh; unsigned int
0x1800d5091  mov     ecx, eax; int
0x1800d5093  call    ?_ErrFromHr@@YAIJI@Z; _ErrFromHr(long,uint)
0x1800d5098  test    eax, eax
0x1800d509a  jnz     loc_1800D56EA
0x1800d50a0  mov     [rsp+0A80h+var_A30], r15d
0x1800d50a5  lea     r15, [r14+1F0h]
0x1800d50ac  mov     esi, 1
0x1800d50b1  add     cs:?Cio_cUnloadCtlsSweep@@3KA, esi; ulong Cio_cUnloadCtlsSweep
0x1800d50b7  mov     rcx, r15; this
0x1800d50ba  mov     [rbp+980h+var_9F0], r15
0x1800d50be  call    ?hxmodFirst@CHxmodList@@QEAAPEAUXMOD@@XZ; CHxmodList::hxmodFirst(void)
0x1800d50c3  mov     r13, rax
0x1800d50c6  test    rax, rax
0x1800d50c9  jz      loc_1800D577C
0x1800d50cf  mov     rcx, [rax]; struct MDL *
0x1800d50d2  mov     rbx, rax
0x1800d50d5  call    ?MdlImdlOfLpmdl@@YAEPEAUMDL@@@Z; MdlImdlOfLpmdl(MDL *)
0x1800d50da  cmp     al, 0FFh
0x1800d50dc  jnz     loc_1800D56C1
0x1800d50e2  mov     rdx, rbx; struct XMOD *
0x1800d50e5  mov     rcx, r14; struct Project *
0x1800d50e8  call    ?CioCanUnloadCustomControl@@YAHPEAVProject@@PEAUXMOD@@@Z; CioCanUnloadCustomControl(Project *,XMOD *)
0x1800d50ed  xor     edx, edx; Val
0x1800d50ef  test    eax, eax
0x1800d50f1  jnz     loc_1800D56C1
0x1800d50f7  test    byte ptr [rbx+72h], 40h
0x1800d50fb  jz      loc_1800D56C1
0x1800d5101  mov     rax, [rbx]
0x1800d5104  xor     r12d, r12d
0x1800d5107  cmp     byte ptr [rax+5Fh], 20h ; ' '
0x1800d510b  jnz     short loc_1800D5116
0x1800d510d  cmp     [rbx+8], r12
0x1800d5111  cmovnz  rbx, [rbx+8]
0x1800d5116  lea     rcx, [rbp+980h+var_9A0]; void *
0x1800d511a  mov     r8d, 34h ; '4'; Size
0x1800d5120  call    memset_0
0x1800d5125  lea     rcx, [rbp+980h+var_910]; void *
0x1800d5129  xor     edx, edx; Val
0x1800d512b  mov     r8d, 98h; Size
0x1800d5131  call    memset_0
0x1800d5136  lea     r11, [rsp+0A80h+bstr]
0x1800d513b  lea     rax, [rsp+0A80h+var_A08]
0x1800d5140  mov     [rsp+0A80h+var_A58], r11; wchar_t **
0x1800d5145  lea     r9, [rsp+0A80h+var_A2C]; int *
0x1800d514a  lea     r8, [rbp+980h+var_910]; struct _GUID *
0x1800d514e  lea     rdx, [rbp+980h+String]; char *
0x1800d5155  mov     rcx, rbx; struct XMOD *
0x1800d5158  mov     [rsp+0A80h+var_A60], rax; int *
0x1800d515d  call    ?_GetOleCtlInfo@@YAIPEAUXMOD@@PEADPEAU_GUID@@PEAH3PEAPEA_W@Z; _GetOleCtlInfo(XMOD *,char *,_GUID *,int *,int *,wchar_t * *)
0x1800d5162  test    eax, eax
0x1800d5164  jnz     loc_1800D56E2
0x1800d516a  mov     cl, [rbp+980h+var_87C]
0x1800d5170  mov     r8, rbx
0x1800d5173  mov     rdx, r12
0x1800d5176  mov     al, cl
0x1800d5178  xor     al, byte ptr [rsp+0A80h+var_A2C]
0x1800d517c  and     al, sil
0x1800d517f  xor     cl, al
0x1800d5181  mov     [rbp+980h+var_87C], cl
0x1800d5187  mov     rax, [rbx+70h]
0x1800d518b  mov     [rbp+980h+var_88C], rax
0x1800d5192  movzx   eax, word ptr [rbx+0C6h]
0x1800d5199  mov     ecx, dword ptr [rbp+980h+var_88C]
0x1800d519f  mov     [rbp+980h+var_87E], ax
0x1800d51a6  movzx   eax, word ptr [rbx+0D0h]
0x1800d51ad  shr     rcx, 10h
0x1800d51b1  mov     [rbp+980h+var_884], ax
0x1800d51b8  movups  xmm0, xmmword ptr [rbx+0D4h]
0x1800d51bf  movdqu  [rbp+980h+var_900], xmm0
0x1800d51c7  movups  xmm1, xmmword ptr [rbx+0E4h]
0x1800d51ce  movdqu  [rbp+980h+var_8F0], xmm1
0x1800d51d6  movzx   eax, word ptr [rbx+0D2h]
0x1800d51dd  mov     [rbp+980h+var_882], ax
0x1800d51e4  mov     eax, 80h
0x1800d51e9  movups  xmm0, xmmword ptr [rbx+134h]
0x1800d51f0  movdqu  [rbp+980h+var_8E0], xmm0
0x1800d51f8  movups  xmm1, xmmword ptr [rbx+144h]
0x1800d51ff  movdqu  [rbp+980h+var_8D0], xmm1
0x1800d5207  movups  xmm0, xmmword ptr [rbx+154h]
0x1800d520e  movdqu  [rbp+980h+var_8B0], xmm0
0x1800d5216  movups  xmm1, xmmword ptr [rbx+164h]
0x1800d521d  movdqu  [rbp+980h+var_8A0], xmm1
0x1800d5225  xor     cx, [rbx+72h]
0x1800d5229  and     cx, ax
0x1800d522c  mov     eax, dword ptr [rbp+980h+var_88C]
0x1800d5232  shr     rax, 10h
0x1800d5236  xor     cx, ax
0x1800d5239  lea     rax, [rbp+980h+var_8BC]
0x1800d5240  sub     r8, rax
0x1800d5243  mov     word ptr [rbp+980h+var_88C+2], cx
0x1800d524a  lea     rax, [r8+rdx*4]
0x1800d524e  mov     ecx, [rbp+rax+980h+var_6E0]
0x1800d5255  mov     [rbp+rdx*4+980h+var_8BC], ecx
0x1800d525c  add     rdx, rsi
0x1800d525f  cmp     rdx, 3
0x1800d5263  jl      short loc_1800D524A
0x1800d5265  mov     eax, [rbx+1E8h]
0x1800d526b  mov     rcx, [rsp+0A80h+var_A40]; struct FILEREF *
0x1800d5270  xor     edx, edx; int
0x1800d5272  mov     [rbp+980h+var_8C0], eax
0x1800d5278  call    ?RelSeekFileRef@@YAJPEAUFILEREF@@J@Z; RelSeekFileRef(FILEREF *,long)
0x1800d527d  mov     rcx, [rsp+0A80h+var_A40]
0x1800d5282  xor     r9d, r9d
0x1800d5285  lea     rdx, [rbp+980h+var_9A0]
0x1800d5289  mov     r14d, eax
0x1800d528c  lea     r8d, [r9+34h]
0x1800d5290  call    ?HrFrefWrite@@YAJPEAUFILEREF@@PEAEKW4DataType@@@Z; HrFrefWrite(FILEREF *,uchar *,ulong,DataType)
0x1800d5295  test    eax, eax
0x1800d5297  js      loc_1800D56D1
0x1800d529d  mov     rcx, [rsp+0A80h+var_A40]; struct FILEREF *
0x1800d52a2  call    ?HrFrefAlign@@YAJPEAUFILEREF@@@Z; HrFrefAlign(FILEREF *)
0x1800d52a7  test    eax, eax
0x1800d52a9  js      loc_1800D56D1
0x1800d52af  mov     rcx, [rsp+0A80h+var_A40]; struct FILEREF *
0x1800d52b4  xor     edx, edx; int
0x1800d52b6  call    ?RelSeekFileRef@@YAJPEAUFILEREF@@J@Z; RelSeekFileRef(FILEREF *,long)
0x1800d52bb  mov     rcx, [rsp+0A80h+var_A40]
0x1800d52c0  lea     rdx, [rbp+980h+var_910]
0x1800d52c4  sub     eax, r14d
0x1800d52c7  xor     r9d, r9d
0x1800d52ca  mov     r8d, 98h
0x1800d52d0  mov     dword ptr [rbp+980h+var_99C], eax
0x1800d52d3  call    ?HrFrefWrite@@YAJPEAUFILEREF@@PEAEKW4DataType@@@Z; HrFrefWrite(FILEREF *,uchar *,ulong,DataType)
0x1800d52d8  test    eax, eax
0x1800d52da  js      loc_1800D56D1
0x1800d52e0  mov     rcx, [rsp+0A80h+var_A40]; struct FILEREF *
0x1800d52e5  call    ?HrFrefAlign@@YAJPEAUFILEREF@@@Z; HrFrefAlign(FILEREF *)
0x1800d52ea  test    eax, eax
0x1800d52ec  js      loc_1800D56D1
0x1800d52f2  cmp     [rbx+100h], r12
0x1800d52f9  jz      short loc_1800D534B
0x1800d52fb  mov     rcx, [rsp+0A80h+var_A40]; struct FILEREF *
0x1800d5300  xor     edx, edx; int
0x1800d5302  call    ?RelSeekFileRef@@YAJPEAUFILEREF@@J@Z; RelSeekFileRef(FILEREF *,long)
0x1800d5307  sub     eax, r14d
0x1800d530a  mov     [rbp+980h+var_998], eax
0x1800d530d  mov     rcx, [rbx+100h]; Block
0x1800d5314  call    cs:__imp__msize
0x1800d531a  mov     rdx, [rbx+100h]
0x1800d5321  mov     rcx, [rsp+0A80h+var_A40]
0x1800d5326  mov     r8d, eax
0x1800d5329  xor     r9d, r9d
0x1800d532c  call    ?HrFrefWrite@@YAJPEAUFILEREF@@PEAEKW4DataType@@@Z; HrFrefWrite(FILEREF *,uchar *,ulong,DataType)
0x1800d5331  test    eax, eax
0x1800d5333  js      loc_1800D56D1
0x1800d5339  mov     rcx, [rsp+0A80h+var_A40]; struct FILEREF *
0x1800d533e  call    ?HrFrefAlign@@YAJPEAUFILEREF@@@Z; HrFrefAlign(FILEREF *)
0x1800d5343  test    eax, eax
0x1800d5345  js      loc_1800D56D1
  ... truncated ...
```
