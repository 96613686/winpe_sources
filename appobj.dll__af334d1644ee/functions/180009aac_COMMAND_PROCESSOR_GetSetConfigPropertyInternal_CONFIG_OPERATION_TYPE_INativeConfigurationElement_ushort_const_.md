# COMMAND_PROCESSOR::GetSetConfigPropertyInternal(CONFIG_OPERATION_TYPE,INativeConfigurationElement *,ushort const *,ushort const *,STRU *,int *)

- ea: `0x180009aac`
- end: `0x18000a77d`
- name: `?GetSetConfigPropertyInternal@COMMAND_PROCESSOR@@AEAAJW4CONFIG_OPERATION_TYPE@@PEAVINativeConfigurationElement@@PEBG2PEAVSTRU@@PEAH@Z`
- size: `3281`
- prototype: ``
- caller_count: `6`
- callee_count: `20`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180008160`
- `0x180009aac`
- `0x18000b0c0`
- `0x18000bff0`
- `0x18000cd60`
- `0x18000d6e0`

## callees

- `0x180001ed0`
- `0x180001fb0`
- `0x180002640`
- `0x180002680`
- `0x180002e90`
- `0x180004560`
- `0x180004a70`
- `0x1800055c0`
- `0x180005e40`
- `0x1800063c8`
- `0x180008990`
- `0x180008f00`
- `0x180009aac`
- `0x18000aed4`
- `0x18000c38c`
- `0x1800131d8`
- `0x180034cbe`
- `0x180034d00`
- `0x180034d90`
- `0x180036010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180009f6b`
- `msvcrt!_wcsnicmp` at `0x18000a02a`
- `msvcrt!_wcsnicmp` at `0x180009f6b`
- `msvcrt!_wcsnicmp` at `0x18000a02a`
- `msvcrt!_wcsicmp` at `0x180009e28`
- `msvcrt!_wcsicmp` at `0x180009fa6`
- `msvcrt!_wcsicmp` at `0x18000a113`
- `msvcrt!_wcsicmp` at `0x18000a229`
- `msvcrt!_wcsicmp` at `0x180009e28`
- `msvcrt!_wcsicmp` at `0x180009fa6`
- `msvcrt!_wcsicmp` at `0x18000a113`
- `msvcrt!_wcsicmp` at `0x18000a229`

## pseudocode

```c
__int64 __fastcall COMMAND_PROCESSOR::GetSetConfigPropertyInternal(
        COMMAND_PROCESSOR *a1,
        unsigned int a2,
        struct INativeConfigurationElement *a3,
        unsigned __int16 *a4,
        wchar_t *String1,
        STRU *a6,
        _DWORD *a7)
{
  const wchar_t *v8; // rsi
  COMMAND_PROCESSOR *v12; // rcx
  struct INativeConfigurationElement *v13; // rdx
  int SetConfigPropertyInternal; // eax
  int MatchingSchema; // ebx
  __int64 v16; // rax
  const unsigned __int8 *v17; // rdx
  _WORD *v18; // rcx
  va_list *v19; // r12
  unsigned int j; // eax
  unsigned int v21; // edx
  __int64 v22; // r8
  va_list v23; // rdx
  int v24; // eax
  _DWORD *v25; // rdi
  int v26; // eax
  wchar_t *v27; // rbx
  __int64 v28; // rcx
  unsigned __int64 v29; // rax
  unsigned __int16 *v30; // rbx
  bool v31; // zf
  const wchar_t *v32; // rdx
  size_t v33; // rax
  unsigned __int16 *v34; // rbx
  int v35; // eax
  __int64 v36; // r8
  __int64 v37; // rdx
  __int64 v38; // rcx
  wchar_t *v39; // r9
  int v40; // eax
  unsigned int v41; // r8d
  unsigned int v42; // edi
  unsigned int k; // ebx
  int v44; // eax
  int v45; // eax
  unsigned int v46; // ebx
  __int64 v47; // rdx
  COMMAND_PROCESSOR *v48; // rcx
  unsigned int v49; // r8d
  int v50; // eax
  DWORD v51; // ecx
  _QWORD *v52; // rcx
  __int16 *v53; // r8
  __int64 v54; // rax
  __int64 v55; // rdx
  const unsigned __int16 *v56; // r9
  __int64 i; // rcx
  const unsigned __int8 *v58; // rdi
  __int64 v59; // rax
  unsigned int v61; // [rsp+40h] [rbp-C0h]
  unsigned int v62; // [rsp+40h] [rbp-C0h]
  __int64 v63; // [rsp+48h] [rbp-B8h] BYREF
  struct INativeConfigurationElement *v64; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v65; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v66; // [rsp+60h] [rbp-A0h] BYREF
  int v67; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned __int16 *v68; // [rsp+68h] [rbp-98h]
  int v69; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v70; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v71; // [rsp+78h] [rbp-88h] BYREF
  int v72; // [rsp+7Ch] [rbp-84h] BYREF
  __int64 v73; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v74; // [rsp+88h] [rbp-78h] BYREF
  int v75; // [rsp+8Ch] [rbp-74h] BYREF
  _DWORD *v76; // [rsp+90h] [rbp-70h]
  unsigned __int16 *v77; // [rsp+98h] [rbp-68h] BYREF
  void **v78; // [rsp+A0h] [rbp-60h] BYREF
  int v79; // [rsp+A8h] [rbp-58h]
  __int64 v80; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v81; // [rsp+B8h] [rbp-48h]
  int v82; // [rsp+C0h] [rbp-40h]
  unsigned __int16 *v83; // [rsp+C8h] [rbp-38h]
  char v84[32]; // [rsp+D0h] [rbp-30h] BYREF
  __int16 *v85; // [rsp+F0h] [rbp-10h]
  int v86; // [rsp+F8h] [rbp-8h]
  __int16 v87; // [rsp+FCh] [rbp-4h]
  int v88; // [rsp+100h] [rbp+0h]
  _BYTE v89[32]; // [rsp+108h] [rbp+8h] BYREF
  wchar_t *String2; // [rsp+128h] [rbp+28h]
  int v91; // [rsp+130h] [rbp+30h]
  __int16 v92; // [rsp+134h] [rbp+34h]
  size_t MaxCount; // [rsp+138h] [rbp+38h]
  _BYTE v94[32]; // [rsp+140h] [rbp+40h] BYREF
  __int16 *v95; // [rsp+160h] [rbp+60h]
  int v96; // [rsp+168h] [rbp+68h]
  __int16 v97; // [rsp+16Ch] [rbp+6Ch]
  int v98; // [rsp+170h] [rbp+70h]
  _BYTE v99[32]; // [rsp+178h] [rbp+78h] BYREF
  unsigned __int16 *v100; // [rsp+198h] [rbp+98h]
  int v101; // [rsp+1A0h] [rbp+A0h]
  __int16 v102; // [rsp+1A4h] [rbp+A4h]
  int v103; // [rsp+1A8h] [rbp+A8h]
  _BYTE v104[32]; // [rsp+1B0h] [rbp+B0h] BYREF
  __int16 *v105; // [rsp+1D0h] [rbp+D0h]
  int v106; // [rsp+1D8h] [rbp+D8h]
  __int16 v107; // [rsp+1DCh] [rbp+DCh]
  int v108; // [rsp+1E0h] [rbp+E0h]
  _BYTE v109[32]; // [rsp+1E8h] [rbp+E8h] BYREF
  __int64 v110; // [rsp+208h] [rbp+108h]
  _BYTE v111[56]; // [rsp+220h] [rbp+120h] BYREF
  va_list Arguments[2]; // [rsp+258h] [rbp+158h] BYREF
  __int64 v113; // [rsp+268h] [rbp+168h]
  _QWORD v114[192]; // [rsp+270h] [rbp+170h] BYREF
  __int16 v115; // [rsp+870h] [rbp+770h] BYREF
  char v116[510]; // [rsp+872h] [rbp+772h] BYREF
  __int16 v117; // [rsp+A70h] [rbp+970h] BYREF
  char v118[510]; // [rsp+A72h] [rbp+972h] BYREF
  __int16 v119; // [rsp+C70h] [rbp+B70h] BYREF
  char v120[510]; // [rsp+C72h] [rbp+B72h] BYREF
  __int16 v121; // [rsp+E70h] [rbp+D70h] BYREF
  char v122[510]; // [rsp+E72h] [rbp+D72h] BYREF
  __int16 v123; // [rsp+1070h] [rbp+F70h] BYREF
  char v124[542]; // [rsp+1072h] [rbp+F72h] BYREF

  v8 = String1;
  v83 = a4;
  v76 = a7;
  v74 = 64;
  memset_0(v116, 0, sizeof(v116));
  v92 = 256;
  LODWORD(MaxCount) = 0;
  v115 = 0;
  v64 = 0;
  v65 = 0;
  String2 = (wchar_t *)&v115;
  v91 = 512;
  memset_0(v118, 0, sizeof(v118));
  v86 = 512;
  v88 = 0;
  v117 = 0;
  v69 = 0;
  v70 = 0;
  v85 = &v117;
  v87 = 256;
  MULTISZ::MULTISZ((MULTISZ *)v111);
  v77 = 0;
  v66 = 0;
  v63 = 0;
  *(_OWORD *)Arguments = 0;
  v113 = 0;
  memset_0(v120, 0, sizeof(v120));
  v96 = 512;
  v95 = &v119;
  v97 = 256;
  v98 = 0;
  v119 = 0;
  MULTISZ::MULTISZ((MULTISZ *)v109);
  memset_0(v124, 0, 0x210u);
  v106 = 530;
  v107 = 256;
  v105 = &v123;
  v108 = 0;
  v78 = &PARAMETER_LIST::`vftable';
  v123 = 0;
  v79 = 1;
  v80 = 0;
  v81 = 0;
  v82 = 0;
  v73 = 0;
  v67 = 0;
  v75 = 0;
  memset_0(v122, 0, sizeof(v122));
  v101 = 512;
  v102 = 256;
  v100 = (unsigned __int16 *)&v121;
  v103 = 0;
  v121 = 0;
  v72 = 0;
  v71 = -1;
  if ( !a3 || !a4 || !String1 || !a6 )
  {
    MatchingSchema = -2147024809;
    goto LABEL_162;
  }
  if ( !*String1 && a2 == 3 )
  {
    v13 = a3;
    goto LABEL_8;
  }
  v16 = -1;
  do
    ++v16;
  while ( a4[v16] );
  v17 = (const unsigned __int8 *)&String1[v16];
  v18 = v17 + 2;
  if ( *(_WORD *)v17 == 63 || *(_WORD *)v17 == 46 && *v18 == 63 )
  {
    v56 = L"*";
    if ( *v18 )
      v56 = (const unsigned __int16 *)(v17 + 2);
    MatchingSchema = COMMAND_PROCESSOR::GetMatchingSchema(a1, a3, a4, v56, (struct MULTISZ *)v109);
    if ( MatchingSchema < 0 )
      goto LABEL_162;
    for ( i = v110; ; i = (__int64)&v58[2 * v59 + 2] )
    {
      v58 = (const unsigned __int8 *)(i & -(__int64)(*(_WORD *)i != 0));
      if ( !v58 )
        break;
      MatchingSchema = STRU::Append((STRU *)v104, (const unsigned __int8 *)L"-");
      if ( MatchingSchema < 0 )
        goto LABEL_162;
      MatchingSchema = STRU::Append((STRU *)v104, v58);
      if ( MatchingSchema < 0 )
        goto LABEL_162;
      MatchingSchema = STRU::Append((STRU *)v104, (const unsigned __int8 *)L"\n");
      if ( MatchingSchema < 0 )
        goto LABEL_162;
      v59 = -1;
      do
        ++v59;
      while ( *(_WORD *)&v58[2 * v59] );
    }
    v53 = v105;
    v52 = (_QWORD *)((char *)a1 + 8);
    v54 = *((_QWORD *)a1 + 1);
    v55 = 2147942487LL;
    MatchingSchema = -2147024809;
    goto LABEL_160;
  }
  if ( v16 )
    v17 += 2;
  MatchingSchema = STRU::Copy((STRU *)v99, v17);
  if ( MatchingSchema < 0 )
    goto LABEL_162;
  MatchingSchema = COMMAND_PROCESSOR::SetElementMetadataInternal(a1, a3, v100, *((const unsigned __int16 **)a6 + 4));
  if ( MatchingSchema != -2147023483 )
    goto LABEL_162;
  MatchingSchema = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, _QWORD *, unsigned int *))(*(_QWORD *)a3 + 96LL))(
                     a3,
                     v114,
                     &v74);
  if ( MatchingSchema < 0 )
    goto LABEL_162;
  v19 = 0;
  for ( j = 0; ; j = v61 + 1 )
  {
    v61 = j;
    if ( j >= v74 )
      goto LABEL_132;
    MatchingSchema = STRU::Copy((STRU *)v89, (const unsigned __int8 *)v83);
    if ( MatchingSchema < 0 )
      goto LABEL_162;
    v21 = MaxCount;
    if ( (_DWORD)MaxCount )
    {
      MatchingSchema = STRU::Append((STRU *)v89, (const unsigned __int8 *)L".");
      if ( MatchingSchema < 0 )
        goto LABEL_162;
      v21 = MaxCount;
    }
    v19 = (va_list *)&v114[3 * v61];
    if ( *(_DWORD *)v19 )
      break;
    MatchingSchema = STRU::Append((STRU *)v89, (const unsigned __int8 *)v19[1]);
    if ( MatchingSchema < 0 )
      goto LABEL_162;
    if ( *v8 == 46 )
      ++v8;
    if ( !_wcsicmp(v8, String2) )
    {
      if ( !a2 )
      {
        v22 = *((_QWORD *)a6 + 4);
        v23 = v19[1];
        v66 = *((_DWORD *)a6 + 10);
        v24 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, va_list, __int64, unsigned int *, __int64 *, __int64 *))(*(_QWORD *)a3 + 88LL))(
                a3,
                v23,
                v22,
                &v66,
                &v63,
                &v73);
        MatchingSchema = v24;
        if ( v24 >= 0
          || v24 == -2147024774
          && (MatchingSchema = STRA::Resize(a6, v66), MatchingSchema >= 0)
          && (MatchingSchema = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, va_list, _QWORD, unsigned int *, __int64 *, __int64 *))(*(_QWORD *)a3 + 88LL))(
                                 a3,
                                 v19[1],
                                 *((_QWORD *)a6 + 4),
                                 &v66,
                                 &v63,
                                 &v73),
              MatchingSchema >= 0) )
        {
          v25 = v76;
          if ( v76 )
          {
            MatchingSchema = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v73 + 24LL))(v73, &v67);
            if ( MatchingSchema < 0 )
              goto LABEL_162;
            v26 = v67;
            if ( !v67 )
            {
              MatchingSchema = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v73 + 32LL))(v73, &v67);
              if ( MatchingSchema < 0 )
                goto LABEL_162;
              v26 = v67;
            }
            *v25 = v26;
          }
          STRU::SyncWithBuffer(a6);
        }
        goto LABEL_162;
      }
      if ( a2 != 4 )
      {
        if ( a2 != 1 )
          goto LABEL_72;
        v35 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, va_list, _QWORD, __int64 *))(*(_QWORD *)a3 + 160LL))(
                a3,
                v19[1],
                *((_QWORD *)a6 + 4),
                &v63);
        goto LABEL_69;
      }
      if ( !*((_DWORD *)a6 + 12) )
      {
        v35 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, va_list))(*(_QWORD *)a3 + 184LL))(
                a3,
                v19[1]);
LABEL_69:
        MatchingSchema = v35;
        if ( v35 >= 0 )
          goto LABEL_162;
LABEL_140:
        Arguments[0] = v19[1];
        if ( MatchingSchema == -2147023483 )
        {
          v51 = -1073740824;
        }
        else if ( a2 == 4 )
        {
          v51 = -1073740815;
        }
        else
        {
          v51 = -1073740820;
          Arguments[1] = *((va_list *)a6 + 4);
        }
        FormatCommandMessage(v51, Arguments, (struct STRU *)v94);
        v52 = (_QWORD *)((char *)a1 + 8);
        v53 = v95;
        v54 = *((_QWORD *)a1 + 1);
        if ( v63 )
        {
          (*(void (__fastcall **)(_QWORD *, _QWORD, __int16 *))(v54 + 120))(v52, (unsigned int)MatchingSchema, v95);
          v38 = v63;
          goto LABEL_163;
        }
        v55 = (unsigned int)MatchingSchema;
LABEL_160:
        (*(void (__fastcall **)(_QWORD *, __int64, __int16 *, _QWORD))(v54 + 128))(v52, v55, v53, 0);
        goto LABEL_162;
      }
LABEL_63:
      v36 = 3221226526LL;
      goto LABEL_64;
    }
LABEL_59:
    ;
  }
  if ( *(_DWORD *)v19 == 1 )
  {
    MatchingSchema = STRU::Append((STRU *)v89, (const unsigned __int8 *)v19[1]);
    if ( MatchingSchema < 0 )
      goto LABEL_162;
    if ( !_wcsnicmp(v8, String2, (unsigned int)MaxCount) )
    {
      MatchingSchema = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, va_list, struct INativeConfigurationElement **))(*(_QWORD *)a3 + 32LL))(
                         a3,
                         v19[1],
                         &v64);
      if ( MatchingSchema < 0 )
        goto LABEL_162;
      v27 = String2;
      if ( !_wcsicmp(v8, String2) && a2 == 4 )
      {
        SetConfigPropertyInternal = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v64 + 168LL))(v64);
        goto LABEL_9;
      }
      if ( _wcsicmp(v8, v27) || a2 != 3 )
      {
        v39 = v27;
LABEL_77:
        SetConfigPropertyInternal = COMMAND_PROCESSOR::GetSetConfigPropertyInternal(a1, a2, v64, v39, v8, a6, v76);
        goto LABEL_9;
      }
      v13 = v64;
LABEL_8:
      SetConfigPropertyInternal = COMMAND_PROCESSOR::ClearCollection(v12, v13);
LABEL_9:
      MatchingSchema = SetConfigPropertyInternal;
      goto LABEL_162;
    }
    goto LABEL_59;
  }
  if ( *(_DWORD *)v19 != 2 )
    goto LABEL_59;
  v28 = v21;
  v29 = -1;
  do
    ++v29;
  while ( v8[v29] );
  if ( v29 < v21 )
    goto LABEL_131;
  v30 = (unsigned __int16 *)&v8[v21];
  v31 = *v30 == 91;
  v68 = v30;
  if ( v31 )
    goto LABEL_80;
  v32 = (const wchar_t *)v19[1];
  v33 = -1;
  do
    ++v33;
  while ( v32[v33] );
  v68 = (unsigned __int16 *)v33;
  if ( _wcsnicmp(&v8[v28], v32, v33) )
    goto LABEL_59;
  v34 = &v30[(_QWORD)v68];
  v31 = *v34 == 91;
  v68 = v34;
  if ( !v31 )
    goto LABEL_59;
  MatchingSchema = STRU::Append((STRU *)v89, (const unsigned __int8 *)v19[1]);
  if ( MatchingSchema < 0 )
    goto LABEL_162;
  v30 = v68;
  if ( *v68 != 91 )
  {
LABEL_132:
    MatchingSchema = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, int *))(*(_QWORD *)a3 + 240LL))(
                       a3,
                       &v75);
    if ( MatchingSchema < 0 )
      goto LABEL_162;
    if ( !v75 )
    {
LABEL_131:
      MatchingSchema = -2147023483;
      goto LABEL_162;
    }
    if ( a2 == 4 )
    {
      if ( *((_DWORD *)a6 + 12) )
        goto LABEL_63;
      v50 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, unsigned __int16 *))(*(_QWORD *)a3 + 184LL))(
              a3,
              v100);
    }
    else
    {
      if ( a2 != 1 )
        goto LABEL_72;
      v50 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, unsigned __int16 *, _QWORD, __int64 *))(*(_QWORD *)a3 + 160LL))(
              a3,
              v100,
              *((_QWORD *)a6 + 4),
              &v63);
    }
    MatchingSchema = v50;
    if ( v50 >= 0 )
    {
      MatchingSchema = 0;
      goto LABEL_162;
    }
    goto LABEL_140;
  }
LABEL_80:
  MatchingSchema = COMMAND_PROCESSOR::GetIndexer(
                     a1,
                     v30,
                     (struct PARAMETER_LIST *)&v78,
                     (const unsigned __int16 **)&v77,
                     (enum COLLECTION_INDEX_TYPE *)&v72,
                     &v71);
  if ( MatchingSchema < 0 )
  {
    v36 = 3221226482LL;
    goto LABEL_82;
  }
  MatchingSchema = STRU::Append((STRU *)v89, v68, (unsigned int)(v77 - v68) + 1);
  if ( MatchingSchema >= 0 )
  {
    MatchingSchema = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 *))(*(_QWORD *)a3 + 40LL))(
                       a3,
                       &v65);
    if ( MatchingSchema >= 0 )
    {
      MatchingSchema = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v65 + 24LL))(v65, &v70);
      if ( MatchingSchema >= 0 )
      {
        v40 = _wcsicmp(String2, v8);
        v41 = v70;
        v42 = -1;
        LODWORD(v68) = v40;
        if ( v72 )
        {
          switch ( v72 )
          {
            case 1:
              v42 = v71;
              break;
            case 2:
              goto LABEL_93;
            case 3:
              if ( !v70 )
LABEL_93:
                v42 = 0;
              else
                v42 = v70 - 1;
              break;
            default:
              MatchingSchema = -2147024846;
              goto LABEL_162;
          }
          if ( v40 && a2 != 2 && (_DWORD)v81 )
          {
            MatchingSchema = -2147024846;
            v36 = 3221226537LL;
LABEL_82:
            v37 = (unsigned int)MatchingSchema;
LABEL_65:
            (*(void (__fastcall **)(_QWORD *, __int64, __int64, va_list *, _DWORD))(*((_QWORD *)a1 + 1) + 144LL))(
              (_QWORD *)a1 + 1,
              v37,
              v36,
              Arguments,
              0);
            goto LABEL_162;
          }
        }
        for ( k = 0; ; k = v46 + 1 )
        {
          v62 = k;
          if ( k >= v41 )
          {
LABEL_125:
            if ( a2 != 2 || v40 )
            {
              MatchingSchema = -2147020584;
              (*(void (__fastcall **)(_QWORD *, __int64, __int64, va_list *, _DWORD))(*((_QWORD *)a1 + 1) + 144LL))(
                (_QWORD *)a1 + 1,
                2147946712LL,
                3221226507LL,
                Arguments,
                0);
            }
            else
            {
              if ( *((_DWORD *)a6 + 12) )
                goto LABEL_63;
              MatchingSchema = COMMAND_PROCESSOR::AddNewCollectionElement(
                                 (__int64)a1,
                                 (__int64)&v78,
                                 v65,
                                 v19[1],
                                 v72,
                                 v71);
            }
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
            v65 = 0;
            goto LABEL_162;
          }
          if ( v42 == -1 || a2 == 2 && !v40 )
          {
            MatchingSchema = (*(__int64 (__fastcall **)(__int64, _QWORD, struct INativeConfigurationElement **))(*(_QWORD *)v65 + 32LL))(
                               v65,
                               k,
                               &v64);
            if ( MatchingSchema < 0 )
              goto LABEL_162;
            MatchingSchema = COMMAND_PROCESSOR::MatchCollectionElement(
                               v48,
                               v64,
                               v49,
                               (struct PARAMETER_LIST *)&v78,
                               &v69);
            if ( MatchingSchema < 0 )
              goto LABEL_162;
            v46 = v62;
            v47 = v62;
            v45 = v69;
          }
          else
          {
            v44 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct INativeConfigurationElement **))(*(_QWORD *)v65 + 32LL))(
                    v65,
                    v42,
                    &v64);
            MatchingSchema = v44;
            if ( v44 < 0 )
            {
              if ( v44 != -2147023483 )
                goto LABEL_162;
              v45 = 0;
            }
            else
            {
              v45 = 1;
            }
            v46 = v62;
            v47 = v42;
            v69 = v45;
          }
          if ( v45 )
            break;
          if ( v64 )
          {
            (*(void (__fastcall **)(struct INativeConfigurationElement *, __int64))(*(_QWORD *)v64 + 16LL))(v64, v47);
            v64 = 0;
          }
          v40 = (int)v68;
          if ( v42 != -1 )
            goto LABEL_125;
          v41 = v70;
        }
        if ( (_DWORD)v68 )
        {
          v39 = String2;
          goto LABEL_77;
        }
        if ( *((_DWORD *)a6 + 12) )
          goto LABEL_63;
        if ( a2 == 2 )
        {
          SetConfigPropertyInternal = COMMAND_PROCESSOR::AddNewCollectionElement(
                                        (__int64)a1,
                                        (__int64)&v78,
                                        v65,
                                        v19[1],
                                        0,
                                        0xFFFFFFFF);
          goto LABEL_9;
        }
        if ( a2 == 4 )
        {
          MatchingSchema = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v65 + 64LL))(v65, v47, 0);
          if ( MatchingSchema == -2147024863 )
          {
            Arguments[0] = v19[1];
            (*(void (__fastcall **)(_QWORD *, __int64, __int64, va_list *, _DWORD))(*((_QWORD *)a1 + 1) + 144LL))(
              (_QWORD *)a1 + 1,
              2147942433LL,
              3221226542LL,
              Arguments,
              0);
          }
          goto LABEL_162;
        }
LABEL_72:
        v36 = 3221226528LL;
LABEL_64:
        v37 = 2147942487LL;
        MatchingSchema = -2147024809;
        Arguments[0] = (va_list)v8;
        goto LABEL_65;
      }
    }
  }
LABEL_162:
  v38 = v63;
  if ( v63 )
  {
LABEL_163:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    v63 = 0;
  }
  if ( v73 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
    v73 = 0;
  }
  if ( v65 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
    v65 = 0;
  }
  if ( v64 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v64 + 16LL))(v64);
    v64 = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v99);
  v78 = &PARAMETER_LIST::`vftable';
  ARRAY_LIST::~ARRAY_LIST((ARRAY_LIST *)&v80);
  BUFFER::~BUFFER((BUFFER *)v104);
  BUFFER::~BUFFER((BUFFER *)v109);
  BUFFER::~BUFFER((BUFFER *)v94);
  BUFFER::~BUFFER((BUFFER *)v111);
  BUFFER::~BUFFER((BUFFER *)v84);
  BUFFER::~BUFFER((BUFFER *)v89);
  return (unsigned int)MatchingSchema;
}

```

## disassembly

```asm
0x180009aac  push    rbp
0x180009aae  push    rbx
0x180009aaf  push    rsi
0x180009ab0  push    rdi
0x180009ab1  push    r12
0x180009ab3  push    r13
0x180009ab5  push    r14
0x180009ab7  push    r15
0x180009ab9  lea     rbp, [rsp-11A8h]
0x180009ac1  mov     eax, 12A8h
0x180009ac6  call    _alloca_probe
0x180009acb  sub     rsp, rax
0x180009ace  mov     rax, cs:__security_cookie
0x180009ad5  xor     rax, rsp
0x180009ad8  mov     [rbp+11E0h+var_50], rax
0x180009adf  mov     rax, [rbp+11E0h+arg_30]
0x180009ae6  mov     rbx, r9
0x180009ae9  mov     rsi, [rbp+11E0h+String1]
0x180009af0  mov     rdi, r8
0x180009af3  mov     r13, [rbp+11E0h+arg_28]
0x180009afa  mov     r15d, edx
0x180009afd  mov     r14, rcx
0x180009b00  mov     [rbp+11E0h+var_1218], rbx
0x180009b04  xor     edx, edx; Val
0x180009b06  mov     [rbp+11E0h+var_1250], rax
0x180009b0a  mov     r8d, 1FEh; Size
0x180009b10  mov     [rbp+11E0h+var_1258], 40h ; '@'
0x180009b17  lea     rcx, [rbp+11E0h+var_A6E]; void *
0x180009b1e  call    memset_0
0x180009b23  xor     ecx, ecx
0x180009b25  mov     [rbp+11E0h+var_11AC], 100h
0x180009b2b  mov     r12d, 200h
0x180009b31  mov     dword ptr [rbp+11E0h+MaxCount], ecx
0x180009b34  lea     rax, [rbp+11E0h+var_A70]
0x180009b3b  mov     [rbp+11E0h+var_A70], cx
0x180009b42  mov     [rsp+12E0h+var_1290], rcx
0x180009b47  xor     edx, edx; Val
0x180009b49  mov     [rsp+12E0h+var_1288], rcx
0x180009b4e  lea     rcx, [rbp+11E0h+var_86E]; void *
0x180009b55  lea     r8d, [r12-2]; Size
0x180009b5a  mov     [rbp+11E0h+String2], rax
0x180009b5e  mov     [rbp+11E0h+var_11B0], r12d
0x180009b62  call    memset_0
0x180009b67  xor     ecx, ecx
0x180009b69  mov     [rbp+11E0h+var_11E8], r12d
0x180009b6d  mov     [rbp+11E0h+var_11E0], ecx
0x180009b70  lea     rax, [rbp+11E0h+var_870]
0x180009b77  mov     [rbp+11E0h+var_870], cx
0x180009b7e  mov     [rsp+12E0h+var_1270], ecx
0x180009b82  mov     [rsp+12E0h+var_126C], ecx
0x180009b86  lea     rcx, [rbp+11E0h+var_10C0]; this
0x180009b8d  mov     [rbp+11E0h+var_11F0], rax
0x180009b91  mov     [rbp+11E0h+var_11E4], 100h
0x180009b97  call    ??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x180009b9c  xor     eax, eax
0x180009b9e  lea     r8d, [r12-2]; Size
0x180009ba3  xorps   xmm0, xmm0
0x180009ba6  mov     [rbp+11E0h+var_1248], rax
0x180009baa  xor     edx, edx; Val
0x180009bac  mov     [rsp+12E0h+var_1280], eax
0x180009bb0  lea     rcx, [rbp+11E0h+var_66E]; void *
0x180009bb7  mov     [rsp+12E0h+var_1298], rax
0x180009bbc  movups  xmmword ptr [rbp+11E0h+Arguments], xmm0
0x180009bc3  mov     [rbp+11E0h+var_1078], rax
0x180009bca  call    memset_0
0x180009bcf  lea     rax, [rbp+11E0h+var_670]
0x180009bd6  mov     [rbp+11E0h+var_1178], r12d
0x180009bda  mov     [rbp+11E0h+var_1180], rax
0x180009bde  lea     rcx, [rbp+11E0h+var_10F8]; this
0x180009be5  xor     eax, eax
0x180009be7  mov     [rbp+11E0h+var_1174], 100h
0x180009bed  mov     [rbp+11E0h+var_1170], eax
0x180009bf0  mov     [rbp+11E0h+var_670], ax
0x180009bf7  call    ??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x180009bfc  xor     edx, edx; Val
0x180009bfe  lea     r8d, [r12+10h]; Size
0x180009c03  lea     rcx, [rbp+11E0h+var_26E]; void *
0x180009c0a  call    memset_0
0x180009c0f  xor     ecx, ecx
0x180009c11  mov     [rbp+11E0h+var_1108], 212h
0x180009c1b  lea     rax, [rbp+11E0h+var_270]
0x180009c22  mov     [rbp+11E0h+var_1104], 100h
0x180009c2b  mov     [rbp+11E0h+var_1110], rax
0x180009c32  lea     r8d, [r12-2]; Size
0x180009c37  lea     rax, ??_7PARAMETER_LIST@@6B@; const PARAMETER_LIST::`vftable'
0x180009c3e  mov     [rbp+11E0h+var_1100], ecx
0x180009c44  mov     [rbp+11E0h+var_1240], rax
0x180009c48  xor     edx, edx; Val
0x180009c4a  mov     [rbp+11E0h+var_270], cx
0x180009c51  mov     [rbp+11E0h+var_1238], 1
0x180009c58  mov     [rbp+11E0h+var_1230], rcx
0x180009c5c  mov     [rbp+11E0h+var_1228], rcx
0x180009c60  mov     [rbp+11E0h+var_1220], ecx
0x180009c63  mov     [rbp+11E0h+var_1260], rcx
0x180009c67  mov     [rsp+12E0h+var_127C], ecx
0x180009c6b  mov     [rbp+11E0h+var_1254], ecx
0x180009c6e  lea     rcx, [rbp+11E0h+var_46E]; void *
0x180009c75  call    memset_0
0x180009c7a  xor     r10d, r10d
0x180009c7d  mov     [rbp+11E0h+var_1140], r12d
0x180009c84  mov     [rbp+11E0h+var_113C], 100h
0x180009c8d  lea     rax, [rbp+11E0h+var_470]
0x180009c94  mov     [rbp+11E0h+var_1148], rax
0x180009c9b  mov     [rbp+11E0h+var_1138], r10d
0x180009ca2  mov     [rbp+11E0h+var_470], r10w
0x180009caa  mov     [rsp+12E0h+var_1264], r10d
0x180009caf  mov     [rsp+12E0h+var_1268], 0FFFFFFFFh
0x180009cb7  test    rdi, rdi
0x180009cba  jz      loc_18000A680
0x180009cc0  test    rbx, rbx
0x180009cc3  jz      loc_18000A680
0x180009cc9  test    rsi, rsi
0x180009ccc  jz      loc_18000A680
0x180009cd2  test    r13, r13
0x180009cd5  jz      loc_18000A680
0x180009cdb  cmp     [rsi], r10w
0x180009cdf  jnz     short loc_180009CF6
0x180009ce1  cmp     r15d, 3
0x180009ce5  jnz     short loc_180009CF6
0x180009ce7  mov     rdx, rdi; struct INativeConfigurationElement *
0x180009cea  call    ?ClearCollection@COMMAND_PROCESSOR@@AEAAJPEAVINativeConfigurationElement@@@Z; COMMAND_PROCESSOR::ClearCollection(INativeConfigurationElement *)
0x180009cef  mov     ebx, eax
0x180009cf1  jmp     loc_18000A685
0x180009cf6  or      r12, 0FFFFFFFFFFFFFFFFh
0x180009cfa  mov     rax, r12
0x180009cfd  inc     rax
0x180009d00  cmp     [rbx+rax*2], r10w
0x180009d05  jnz     short loc_180009CFD
0x180009d07  lea     rdx, [rsi+rax*2]
0x180009d0b  cmp     word ptr [rdx], 3Fh ; '?'
0x180009d0f  lea     rcx, [rdx+2]
0x180009d13  jz      loc_18000A5AE
0x180009d19  cmp     word ptr [rdx], 2Eh ; '.'
0x180009d1d  jnz     short loc_180009D29
0x180009d1f  cmp     word ptr [rcx], 3Fh ; '?'
0x180009d23  jz      loc_18000A5AE
0x180009d29  test    rax, rax
0x180009d2c  jz      short loc_180009D31
0x180009d2e  mov     rdx, rcx; unsigned __int16 *
0x180009d31  lea     rcx, [rbp+11E0h+var_1168]; this
0x180009d35  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180009d3a  mov     ebx, eax
0x180009d3c  test    eax, eax
0x180009d3e  js      loc_18000A685
0x180009d44  mov     r9, [r13+20h]; unsigned __int16 *
0x180009d48  mov     rdx, rdi; struct INativeConfigurationElement *
0x180009d4b  mov     r8, [rbp+11E0h+var_1148]; unsigned __int16 *
0x180009d52  mov     rcx, r14; this
0x180009d55  call    ?SetElementMetadataInternal@COMMAND_PROCESSOR@@AEAAJPEAVINativeConfigurationElement@@PEBG1@Z; COMMAND_PROCESSOR::SetElementMetadataInternal(INativeConfigurationElement *,ushort const *,ushort const *)
0x180009d5a  mov     ebx, eax
0x180009d5c  cmp     eax, 80070585h
0x180009d61  jnz     loc_18000A685
0x180009d67  mov     rax, [rdi]
0x180009d6a  lea     r8, [rbp+11E0h+var_1258]
0x180009d6e  lea     rdx, [rbp+11E0h+var_1070]
0x180009d75  mov     rcx, rdi
0x180009d78  mov     rax, [rax+60h]
0x180009d7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d81  xor     r10d, r10d
0x180009d84  mov     ebx, eax
0x180009d86  test    eax, eax
0x180009d88  js      loc_18000A685
0x180009d8e  mov     r12d, r10d
0x180009d91  mov     eax, r10d
0x180009d94  mov     [rsp+12E0h+var_12A0], eax
0x180009d98  cmp     eax, [rbp+11E0h+var_1258]
0x180009d9b  jnb     loc_18000A4B3
0x180009da1  mov     rdx, [rbp+11E0h+var_1218]; unsigned __int16 *
0x180009da5  lea     rcx, [rbp+11E0h+var_11D8]; this
0x180009da9  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180009dae  xor     r10d, r10d
0x180009db1  mov     ebx, eax
0x180009db3  test    eax, eax
0x180009db5  js      loc_18000A685
0x180009dbb  mov     edx, dword ptr [rbp+11E0h+MaxCount]
0x180009dbe  test    edx, edx
0x180009dc0  jz      short loc_180009DE2
0x180009dc2  lea     rdx, asc_180039808; "."
0x180009dc9  lea     rcx, [rbp+11E0h+var_11D8]; this
0x180009dcd  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180009dd2  xor     r10d, r10d
0x180009dd5  mov     ebx, eax
0x180009dd7  test    eax, eax
0x180009dd9  js      loc_18000A685
0x180009ddf  mov     edx, dword ptr [rbp+11E0h+MaxCount]
0x180009de2  mov     eax, [rsp+12E0h+var_12A0]
0x180009de6  lea     r12, [rbp+11E0h+var_1070]
0x180009ded  lea     rcx, [rax+rax*2]
0x180009df1  lea     r12, [r12+rcx*8]
0x180009df5  cmp     [r12], r10d
0x180009df9  jnz     loc_180009F3D
0x180009dff  mov     rdx, [r12+8]; unsigned __int16 *
0x180009e04  lea     rcx, [rbp+11E0h+var_11D8]; this
0x180009e08  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180009e0d  mov     ebx, eax
0x180009e0f  test    eax, eax
0x180009e11  js      loc_18000A685
0x180009e17  cmp     word ptr [rsi], 2Eh ; '.'
0x180009e1b  jnz     short loc_180009E21
0x180009e1d  add     rsi, 2
0x180009e21  mov     rdx, [rbp+11E0h+String2]; String2
0x180009e25  mov     rcx, rsi; String1
0x180009e28  call    cs:__imp__wcsicmp
0x180009e2e  xor     r10d, r10d
0x180009e31  test    eax, eax
0x180009e33  jnz     loc_18000A04C
0x180009e39  test    r15d, r15d
0x180009e3c  jnz     loc_18000A057
0x180009e42  mov     eax, [r13+28h]
0x180009e46  lea     rcx, [rbp+11E0h+var_1260]
0x180009e4a  mov     r8, [r13+20h]
0x180009e4e  lea     r9, [rsp+12E0h+var_1280]
0x180009e53  mov     rdx, [r12+8]
0x180009e58  mov     [rsp+12E0h+var_12B8], rcx
0x180009e5d  lea     rcx, [rsp+12E0h+var_1298]
0x180009e62  mov     [rsp+12E0h+var_1280], eax
0x180009e66  mov     rax, [rdi]
0x180009e69  mov     [rsp+12E0h+var_12C0], rcx
0x180009e6e  mov     rcx, rdi
0x180009e71  mov     rax, [rax+58h]
0x180009e75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e7a  mov     ebx, eax
0x180009e7c  test    eax, eax
0x180009e7e  jns     short loc_180009EDB
0x180009e80  cmp     eax, 8007007Ah
0x180009e85  jnz     loc_18000A685
0x180009e8b  mov     edx, [rsp+12E0h+var_1280]; unsigned int
0x180009e8f  mov     rcx, r13; this
0x180009e92  call    ?Resize@STRA@@QEAAJK@Z; STRA::Resize(ulong)
0x180009e97  mov     ebx, eax
0x180009e99  test    eax, eax
0x180009e9b  js      loc_18000A685
0x180009ea1  mov     rax, [rdi]
0x180009ea4  lea     rcx, [rbp+11E0h+var_1260]
0x180009ea8  mov     r8, [r13+20h]
0x180009eac  lea     r9, [rsp+12E0h+var_1280]
0x180009eb1  mov     rdx, [r12+8]
0x180009eb6  mov     [rsp+12E0h+var_12B8], rcx
0x180009ebb  lea     rcx, [rsp+12E0h+var_1298]
0x180009ec0  mov     rax, [rax+58h]
0x180009ec4  mov     [rsp+12E0h+var_12C0], rcx
0x180009ec9  mov     rcx, rdi
0x180009ecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ed1  mov     ebx, eax
0x180009ed3  test    eax, eax
0x180009ed5  js      loc_18000A685
0x180009edb  mov     rdi, [rbp+11E0h+var_1250]
0x180009edf  test    rdi, rdi
0x180009ee2  jz      short loc_180009F30
0x180009ee4  mov     rcx, [rbp+11E0h+var_1260]
0x180009ee8  lea     rdx, [rsp+12E0h+var_127C]
0x180009eed  mov     rax, [rcx]
0x180009ef0  mov     rax, [rax+18h]
0x180009ef4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ef9  mov     ebx, eax
0x180009efb  test    eax, eax
0x180009efd  js      loc_18000A685
0x180009f03  mov     eax, [rsp+12E0h+var_127C]
0x180009f07  test    eax, eax
0x180009f09  jnz     short loc_180009F2E
0x180009f0b  mov     rcx, [rbp+11E0h+var_1260]
0x180009f0f  lea     rdx, [rsp+12E0h+var_127C]
0x180009f14  mov     rax, [rcx]
0x180009f17  mov     rax, [rax+20h]
0x180009f1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f20  mov     ebx, eax
0x180009f22  test    eax, eax
0x180009f24  js      loc_18000A685
0x180009f2a  mov     eax, [rsp+12E0h+var_127C]
0x180009f2e  mov     [rdi], eax
0x180009f30  mov     rcx, r13; this
0x180009f33  call    ?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x180009f38  jmp     loc_18000A685
0x180009f3d  cmp     dword ptr [r12], 1
0x180009f42  jnz     loc_180009FD7
0x180009f48  mov     rdx, [r12+8]; unsigned __int16 *
0x180009f4d  lea     rcx, [rbp+11E0h+var_11D8]; this
0x180009f51  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180009f56  mov     ebx, eax
0x180009f58  test    eax, eax
0x180009f5a  js      loc_18000A685
0x180009f60  mov     r8d, dword ptr [rbp+11E0h+MaxCount]; MaxCount
0x180009f64  mov     rcx, rsi; String1
0x180009f67  mov     rdx, [rbp+11E0h+String2]; String2
0x180009f6b  call    cs:__imp__wcsnicmp
0x180009f71  test    eax, eax
0x180009f73  jnz     loc_18000A04C
0x180009f79  mov     rax, [rdi]
0x180009f7c  lea     r8, [rsp+12E0h+var_1290]
0x180009f81  mov     rdx, [r12+8]
0x180009f86  mov     rcx, rdi
0x180009f89  mov     rax, [rax+20h]
0x180009f8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f92  mov     ebx, eax
0x180009f94  test    eax, eax
0x180009f96  js      loc_18000A685
0x180009f9c  mov     rbx, [rbp+11E0h+String2]
0x180009fa0  mov     rcx, rsi; String1
0x180009fa3  mov     rdx, rbx; String2
0x180009fa6  call    cs:__imp__wcsicmp
  ... truncated ...
```
