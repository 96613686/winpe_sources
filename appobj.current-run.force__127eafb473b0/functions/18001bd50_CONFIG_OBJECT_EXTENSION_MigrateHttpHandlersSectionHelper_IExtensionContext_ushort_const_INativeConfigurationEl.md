# CONFIG_OBJECT_EXTENSION::MigrateHttpHandlersSectionHelper(IExtensionContext *,ushort const *,INativeConfigurationElementCollection *,ushort const *,int,ICommandObjectList *)

- ea: `0x18001bd50`
- end: `0x18001ca15`
- name: `?MigrateHttpHandlersSectionHelper@CONFIG_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEBGPEAVINativeConfigurationElementCollection@@1HPEAVICommandObjectList@@@Z`
- size: `3269`
- prototype: `int(CONFIG_OBJECT_EXTENSION *__hidden this, struct IExtensionContext *, const unsigned __int16 *, struct INativeConfigurationElementCollection *, const unsigned __int16 *, int, struct ICommandObjectList *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001b7e4`

## callees

- `0x180001044`
- `0x180001084`
- `0x180001fb0`
- `0x180002640`
- `0x180002e90`
- `0x18000557c`
- `0x180006b6c`
- `0x180019948`
- `0x18001bd50`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!wcsstr` at `0x18001c4d1`
- `msvcrt!wcsstr` at `0x18001c4e7`
- `msvcrt!wcsstr` at `0x18001c4ff`
- `msvcrt!wcsstr` at `0x18001c4d1`
- `msvcrt!wcsstr` at `0x18001c4e7`
- `msvcrt!wcsstr` at `0x18001c4ff`

## pseudocode

```c
__int64 __fastcall CONFIG_OBJECT_EXTENSION::MigrateHttpHandlersSectionHelper(
        CONFIG_OBJECT_EXTENSION *this,
        struct IExtensionContext *a2,
        unsigned __int16 *a3,
        struct INativeConfigurationElementCollection *a4,
        const unsigned __int16 *a5,
        int a6,
        struct ICommandObjectList *a7)
{
  unsigned int v7; // r14d
  STATUS_OBJECT *v10; // r13
  int v12; // ebx
  unsigned __int64 v13; // rbx
  _QWORD *v14; // rsi
  _DWORD *v15; // r15
  __int64 v16; // rcx
  unsigned int v17; // edi
  unsigned int i; // r15d
  unsigned __int16 *v19; // rax
  int v20; // ecx
  int v21; // edx
  unsigned __int16 *v22; // rax
  int v23; // ecx
  int v24; // edx
  unsigned __int16 *v25; // rax
  int v26; // ecx
  int v27; // edx
  __int64 v28; // r14
  int v29; // r15d
  __int64 v30; // rax
  __int64 v31; // rdi
  int v32; // r14d
  unsigned int k; // edi
  unsigned __int16 *v34; // rax
  int v35; // ecx
  int v36; // edx
  unsigned __int16 *v37; // rax
  int v38; // ecx
  int v39; // edx
  unsigned __int16 *v40; // rax
  int v41; // ecx
  int v42; // edx
  wchar_t *v43; // rax
  int v44; // ecx
  unsigned int v45; // edi
  CONFIG_OBJECT_EXTENSION *v46; // rcx
  struct ICommandObjectList *v47; // r14
  unsigned __int16 *v48; // rdi
  STATUS_OBJECT *v49; // rax
  unsigned int v50; // eax
  __int64 j; // r14
  __int64 v52; // rcx
  __int64 v54; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v55; // [rsp+48h] [rbp-B8h]
  __int64 v56; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v57; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v58; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v59; // [rsp+68h] [rbp-98h] BYREF
  void *Block; // [rsp+70h] [rbp-90h]
  unsigned __int16 *v61; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v62; // [rsp+80h] [rbp-80h] BYREF
  __int64 v63; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v64; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v65; // [rsp+94h] [rbp-6Ch]
  unsigned int v66; // [rsp+98h] [rbp-68h]
  int v67; // [rsp+9Ch] [rbp-64h]
  char *v68; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v69; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v70; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v71; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v72; // [rsp+C0h] [rbp-40h] BYREF
  char *v73; // [rsp+C8h] [rbp-38h] BYREF
  char *v74; // [rsp+D0h] [rbp-30h] BYREF
  char *v75; // [rsp+D8h] [rbp-28h] BYREF
  struct ICommandParameterList *v76; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v77; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v78; // [rsp+F0h] [rbp-10h] BYREF
  wchar_t *Str; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int16 *v80; // [rsp+100h] [rbp+0h]
  __int64 v81; // [rsp+108h] [rbp+8h]
  struct ICommandObjectList *v82; // [rsp+110h] [rbp+10h]
  __int64 v83; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v84[32]; // [rsp+120h] [rbp+20h] BYREF
  __int16 *v85; // [rsp+140h] [rbp+40h]
  int v86; // [rsp+148h] [rbp+48h]
  __int16 v87; // [rsp+14Ch] [rbp+4Ch]
  int v88; // [rsp+150h] [rbp+50h]
  va_list Arguments[2]; // [rsp+158h] [rbp+58h] BYREF
  __int64 v90; // [rsp+168h] [rbp+68h]
  __int16 v91; // [rsp+170h] [rbp+70h] BYREF
  char v92[510]; // [rsp+172h] [rbp+72h] BYREF

  v7 = 0;
  v80 = a3;
  v82 = a7;
  v76 = 0;
  v70 = 0;
  v63 = 0;
  v90 = 0;
  v69 = 0;
  *(_OWORD *)Arguments = 0;
  v83 = 0;
  v10 = 0;
  v77 = 0;
  v71 = 0;
  v58 = 0;
  v78 = 0;
  v57 = 0;
  v59 = 0;
  v72 = 0;
  v56 = 0;
  v54 = 0;
  v68 = 0;
  v61 = 0;
  v62 = 0;
  v73 = 0;
  v74 = 0;
  v75 = 0;
  Str = 0;
  v64 = 0;
  memset_0(v92, 0, sizeof(v92));
  v86 = 512;
  v85 = &v91;
  v87 = 256;
  v88 = 0;
  v91 = 0;
  if ( !a2 || !a3 || !a4 || !a7 )
  {
    v12 = -2147024809;
    goto LABEL_119;
  }
  v12 = (*(__int64 (__fastcall **)(struct INativeConfigurationElementCollection *, unsigned int *))(*(_QWORD *)a4 + 24LL))(
          a4,
          &v57);
  if ( v12 >= 0 )
  {
    v12 = (*(__int64 (__fastcall **)(struct IExtensionContext *, unsigned __int16 *, __int64 *))(*(_QWORD *)a2 + 80LL))(
            a2,
            a3,
            &v70);
    if ( v12 >= 0 )
    {
      v12 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 *, __int64 *, __int64 *, _QWORD))(*(_QWORD *)v70 + 24LL))(
              v70,
              L"system.web/httpHandlers",
              a3,
              &v77,
              &v63,
              0);
      if ( v12 < 0 )
      {
        if ( v63 )
          (*(void (__fastcall **)(struct IExtensionContext *, _QWORD, const wchar_t *, __int64, _DWORD))(*(_QWORD *)a2 + 112LL))(
            a2,
            (unsigned int)v12,
            &::Str,
            v63,
            0);
        goto LABEL_119;
      }
      v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v77 + 40LL))(v77, &v71);
      if ( v12 < 0 )
        goto LABEL_119;
      v12 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v71 + 24LL))(v71, &v59);
      if ( v12 < 0 )
        goto LABEL_119;
      v13 = v59 + v57;
      v14 = operator new(saturated_mul(v13, 8u));
      if ( !v14 )
      {
        v12 = -2147024888;
        goto LABEL_119;
      }
      Block = operator new(saturated_mul(v13, 4u));
      v15 = Block;
      if ( !Block )
      {
        v12 = -2147024888;
        goto LABEL_117;
      }
      while ( 1 )
      {
        v55 = v7;
        if ( v7 >= v57 )
          break;
        v12 = (*(__int64 (__fastcall **)(struct INativeConfigurationElementCollection *, _QWORD, __int64 *))(*(_QWORD *)a4 + 32LL))(
                a4,
                v7,
                &v72);
        if ( v12 < 0 )
          goto LABEL_113;
        v16 = v7++;
        v14[v16] = v72;
        v15[v16] = 0;
        v72 = 0;
      }
      v17 = 0;
      for ( i = 0; i < v59; ++i )
      {
        v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v71 + 32LL))(v71, i, &v56);
        if ( v12 < 0 )
          goto LABEL_113;
        v12 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v56 + 64LL))(
                v56,
                L"path",
                &v61,
                0,
                0);
        if ( v12 < 0 )
          goto LABEL_113;
        v12 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v56 + 64LL))(
                v56,
                L"verb",
                &v62,
                0,
                0);
        if ( v12 < 0 )
          goto LABEL_113;
        v12 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, char **, _QWORD, _QWORD))(*(_QWORD *)v56 + 64LL))(
                v56,
                L"type",
                &v68,
                0,
                0);
        if ( v12 < 0 )
          goto LABEL_113;
        while ( v17 < v57 )
        {
          v12 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, char **, _QWORD, _QWORD))(*(_QWORD *)v14[v17] + 64LL))(
                  v14[v17],
                  L"path",
                  &v73,
                  0,
                  0);
          if ( v12 < 0 )
            goto LABEL_113;
          v12 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, char **, _QWORD, _QWORD))(*(_QWORD *)v14[v17] + 64LL))(
                  v14[v17],
                  L"verb",
                  &v74,
                  0,
                  0);
          if ( v12 < 0 )
            goto LABEL_113;
          v12 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, char **, _QWORD, _QWORD))(*(_QWORD *)v14[v17] + 64LL))(
                  v14[v17],
                  L"type",
                  &v75,
                  0,
                  0);
          if ( v12 < 0 )
            goto LABEL_113;
          v19 = (unsigned __int16 *)v73;
          do
          {
            v20 = *(unsigned __int16 *)((char *)v19 + (char *)v61 - v73);
            v21 = *v19 - v20;
            if ( v21 )
              break;
            ++v19;
          }
          while ( v20 );
          if ( !v21 )
          {
            v22 = (unsigned __int16 *)v74;
            do
            {
              v23 = *(unsigned __int16 *)((char *)v22 + (char *)v62 - v74);
              v24 = *v22 - v23;
              if ( v24 )
                break;
              ++v22;
            }
            while ( v23 );
            if ( !v24 )
            {
              v25 = (unsigned __int16 *)v75;
              do
              {
                v26 = *(unsigned __int16 *)((char *)v25 + v68 - v75);
                v27 = *v25 - v26;
                if ( v27 )
                  break;
                ++v25;
              }
              while ( v26 );
              if ( !v27 )
              {
                *((_DWORD *)Block + v17) = 1;
                v7 = v55;
                goto LABEL_44;
              }
            }
          }
          ++v17;
        }
        v28 = v55;
        v14[v55] = v56;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 8LL))(v56);
        *((_DWORD *)Block + v28) = 2;
        v7 = v28 + 1;
        v55 = v7;
LABEL_44:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
        v17 = 0;
        v56 = 0;
      }
      v12 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 *, __int64 *, __int64 *, _QWORD))(*(_QWORD *)v70 + 24LL))(
              v70,
              L"system.webServer/handlers",
              v80,
              &v78,
              &v63,
              0);
      if ( v12 < 0 )
      {
        if ( v63 )
          (*(void (__fastcall **)(struct IExtensionContext *, _QWORD, const wchar_t *))(*(_QWORD *)a2 + 112LL))(
            a2,
            (unsigned int)v12,
            &::Str);
        goto LABEL_113;
      }
      v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v78 + 40LL))(v78, &v58);
      if ( v12 < 0 )
        goto LABEL_113;
      v29 = 0;
      v66 = 0;
      v30 = 0;
      v65 = 0;
      while ( 1 )
      {
        v67 = v30;
        if ( (unsigned int)v30 >= v7 )
        {
          if ( !a6 )
          {
            v48 = v80;
            v47 = v82;
            goto LABEL_105;
          }
          v12 = (*(__int64 (__fastcall **)(struct IExtensionContext *, struct ICommandParameterList **))(*(_QWORD *)a2 + 192LL))(
                  a2,
                  &v76);
          if ( v12 >= 0 )
          {
            v47 = v82;
            v48 = v80;
            v12 = CONFIG_OBJECT_EXTENSION::DoClear(v46, a2, v80, L"system.web/httpHandlers", v76, v82);
            if ( v12 >= 0 )
            {
              v29 = 1;
LABEL_105:
              v12 = (*(__int64 (__fastcall **)(struct IExtensionContext *, unsigned __int16 *, __int64))(*(_QWORD *)a2 + 208LL))(
                      a2,
                      v48,
                      1);
              if ( v12 >= 0 )
              {
                if ( v29 )
                {
                  v49 = (STATUS_OBJECT *)operator new(0x110u);
                  if ( v49 && (v10 = STATUS_OBJECT::STATUS_OBJECT(v49)) != 0 )
                  {
                    Arguments[1] = 0;
                    Arguments[0] = (va_list)L"system.web/httpHandlers";
                    v12 = STATUS_OBJECT::Create(v10, 0x413u, Arguments);
                    if ( v12 >= 0 )
                      v12 = (*(__int64 (__fastcall **)(struct ICommandObjectList *, STATUS_OBJECT *))(*(_QWORD *)v47 + 24LL))(
                              v47,
                              v10);
                  }
                  else
                  {
                    v12 = -2147024888;
                  }
                }
                else
                {
                  v12 = 1;
                }
              }
            }
          }
LABEL_113:
          v50 = v55;
          for ( j = 0; (unsigned int)j < v50; j = (unsigned int)(j + 1) )
          {
            v52 = v14[j];
            if ( v52 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
              v50 = v55;
              v14[j] = 0;
            }
          }
LABEL_117:
          operator delete(v14);
          operator delete(Block);
          goto LABEL_119;
        }
        v31 = (unsigned int)v30;
        v56 = v14[v30];
        v81 = (unsigned int)v30;
        v12 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v56 + 64LL))(
                v56,
                L"path",
                &v61,
                0,
                0);
        if ( v12 < 0 )
          goto LABEL_113;
        v12 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v56 + 64LL))(
                v56,
                L"verb",
                &v62,
                0,
                0);
        if ( v12 < 0 )
          goto LABEL_113;
        v12 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, char **, _QWORD, _QWORD))(*(_QWORD *)v56 + 64LL))(
                v56,
                L"type",
                &v68,
                0,
                0);
        if ( v12 < 0 )
          goto LABEL_113;
        v32 = 0;
        v56 = 0;
        if ( (*((_DWORD *)Block + v31) & 0xFFFFFFFD) == 0 )
        {
          v12 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v58 + 24LL))(v58, &v64);
          if ( v12 < 0 )
            goto LABEL_113;
          for ( k = 0; k < v64; ++k )
          {
            v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v58 + 32LL))(v58, k, &v54);
            if ( v12 < 0 )
              goto LABEL_113;
            v12 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, char **, _QWORD, _QWORD))(*(_QWORD *)v54 + 64LL))(
                    v54,
                    L"path",
                    &v73,
                    0,
                    0);
            if ( v12 < 0 )
              goto LABEL_113;
            v12 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char **, _QWORD, _QWORD))(*(_QWORD *)v54 + 64LL))(
                    v54,
                    L"verb",
                    &v74,
                    0,
                    0);
            if ( v12 < 0 )
              goto LABEL_113;
            v12 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, char **, _QWORD, _QWORD))(*(_QWORD *)v54 + 64LL))(
                    v54,
                    L"type",
                    &v75,
                    0,
                    0);
            if ( v12 < 0 )
              goto LABEL_113;
            v12 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v54 + 64LL))(
                    v54,
                    L"preCondition",
                    &Str,
                    0,
                    0);
            if ( v12 < 0 )
              goto LABEL_113;
            v34 = v61;
            do
            {
              v35 = *(unsigned __int16 *)((char *)v34 + v73 - (char *)v61);
              v36 = *v34 - v35;
              if ( v36 )
                break;
              ++v34;
            }
            while ( v35 );
            if ( !v36 )
            {
              v37 = v62;
              do
              {
                v38 = *(unsigned __int16 *)((char *)v37 + v74 - (char *)v62);
                v39 = *v37 - v38;
                if ( v39 )
                  break;
                ++v37;
              }
              while ( v38 );
              if ( !v39 )
              {
                v40 = (unsigned __int16 *)v68;
                do
                {
                  v41 = *(unsigned __int16 *)((char *)v40 + v75 - v68);
                  v42 = *v40 - v41;
                  if ( v42 )
                    break;
                  ++v40;
                }
                while ( v41 );
                if ( !v42 && !wcsstr(Str, L"classicMode") )
                {
                  v43 = wcsstr(Str, L"runtimeVersion");
                  if ( !v43 || wcsstr(v43, L"v2.0") == v43 + 14 )
                  {
                    v32 = 1;
                    v66 = k;
                  }
                }
              }
            }
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
            v54 = 0;
            if ( v32 )
              break;
          }
          v31 = v81;
        }
        v44 = *((_DWORD *)Block + v31);
        if ( !v44 )
          break;
        if ( v44 == 2 && !v32 )
        {
          v12 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64 *))(*(_QWORD *)v58 + 48LL))(
                  v58,
                  L"add",
                  &v54);
          if ( v12 < 0 )
            goto LABEL_113;
          v12 = STRU::Copy((STRU *)v84, v61);
          if ( v12 < 0 )
            goto LABEL_113;
          v12 = STRU::Append((STRU *)v84, L"_");
          if ( v12 < 0 )
            goto LABEL_113;
          v12 = STRU::Append((STRU *)v84, v62);
          if ( v12 < 0 )
            goto LABEL_113;
          v12 = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64, const unsigned __int16 *, __int16 *))(*(_QWORD *)a2 + 96LL))(
                  a2,
                  v54,
                  L"name",
                  v85);
          if ( v12 < 0 )
            goto LABEL_113;
          v12 = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64, const unsigned __int16 *, unsigned __int16 *))(*(_QWORD *)a2 + 96LL))(
                  a2,
                  v54,
                  L"path",
                  v61);
          if ( v12 < 0 )
            goto LABEL_113;
          v12 = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64, const wchar_t *, unsigned __int16 *))(*(_QWORD *)a2 + 96LL))(
                  a2,
                  v54,
                  L"verb",
                  v62);
          if ( v12 < 0 )
            goto LABEL_113;
          v12 = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64, const unsigned __int16 *, char *))(*(_QWORD *)a2 + 96LL))(
                  a2,
                  v54,
                  L"type",
                  v68);
          if ( v12 < 0 )
            goto LABEL_113;
          v12 = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64, const wchar_t *, const wchar_t *))(*(_QWORD *)a2 + 96LL))(
                  a2,
                  v54,
                  L"preCondition",
                  L"integratedMode,runtimeVersionv2.0");
          if ( v12 < 0 )
            goto LABEL_113;
          v45 = v65;
          v12 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64 *))(*(_QWORD *)v58 + 56LL))(
                  v58,
                  v54,
                  v65,
                  &v69);
          if ( v12 < 0 )
            goto LABEL_113;
          v65 = v45 + 1;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
          v54 = 0;
LABEL_98:
          v29 = 1;
        }
LABEL_99:
        v7 = v55;
        v30 = (unsigned int)(v67 + 1);
      }
      if ( !v32 )
        goto LABEL_99;
      v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v58 + 64LL))(v58, v66, &v69);
      if ( v12 < 0 )
        goto LABEL_113;
      goto LABEL_98;
    }
  }
LABEL_119:
  if ( v69 )
  {
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v69 + 24LL))(v69, &v83);
    (*(void (__fastcall **)(struct IExtensionContext *, _QWORD, __int64, _QWORD))(*(_QWORD *)a2 + 128LL))(
      a2,
      (unsigned int)v12,
      v83,
      0);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
    v69 = 0;
  }
  if ( v76 )
  {
    (*(void (__fastcall **)(struct ICommandParameterList *))(*(_QWORD *)v76 + 16LL))(v76);
    v76 = 0;
  }
  if ( v63 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
    v63 = 0;
  }
  if ( v70 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 16LL))(v70);
    v70 = 0;
  }
  if ( v77 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
    v77 = 0;
  }
  if ( v71 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
    v71 = 0;
  }
  if ( v58 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
    v58 = 0;
  }
  if ( v78 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
    v78 = 0;
  }
  if ( v72 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
    v72 = 0;
  }
  if ( v56 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
    v56 = 0;
  }
  if ( v54 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
    v54 = 0;
  }
  if ( v10 )
    (*(void (__fastcall **)(STATUS_OBJECT *))(*(_QWORD *)v10 + 16LL))(v10);
  BUFFER::~BUFFER((BUFFER *)v84);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18001bd50  mov     [rsp-8+arg_0], rbx
0x18001bd55  push    rbp
0x18001bd56  push    rsi
0x18001bd57  push    rdi
0x18001bd58  push    r12
0x18001bd5a  push    r13
0x18001bd5c  push    r14
0x18001bd5e  push    r15
0x18001bd60  lea     rbp, [rsp-280h]
0x18001bd68  sub     rsp, 380h
0x18001bd6f  mov     rax, cs:__security_cookie
0x18001bd76  xor     rax, rsp
0x18001bd79  mov     [rbp+2B0h+var_40], rax
0x18001bd80  mov     rbx, [rbp+2B0h+arg_30]
0x18001bd87  lea     rcx, [rbp+2B0h+var_23E]; void *
0x18001bd8b  xor     r14d, r14d
0x18001bd8e  mov     [rbp+2B0h+var_2B0], r8
0x18001bd92  mov     rsi, r8
0x18001bd95  mov     [rbp+2B0h+var_2A0], rbx
0x18001bd99  mov     r12, rdx
0x18001bd9c  mov     [rbp+2B0h+var_2D0], r14
0x18001bda0  xorps   xmm0, xmm0
0x18001bda3  mov     [rbp+2B0h+var_300], r14
0x18001bda7  xor     eax, eax
0x18001bda9  mov     [rbp+2B0h+var_328], r14
0x18001bdad  xor     edx, edx; Val
0x18001bdaf  mov     [rbp+2B0h+var_248], rax
0x18001bdb3  mov     r8d, 1FEh; Size
0x18001bdb9  mov     [rbp+2B0h+var_308], r14
0x18001bdbd  movups  xmmword ptr [rbp+2B0h+Arguments], xmm0
0x18001bdc1  mov     [rbp+2B0h+var_298], r14
0x18001bdc5  mov     r13d, r14d
0x18001bdc8  mov     [rbp+2B0h+var_2C8], r14
0x18001bdcc  mov     rdi, r9
0x18001bdcf  mov     [rbp+2B0h+var_2F8], r14
0x18001bdd3  mov     [rsp+3B0h+var_350], r14
0x18001bdd8  mov     [rbp+2B0h+var_2C0], r14
0x18001bddc  mov     [rsp+3B0h+var_358], r14d
0x18001bde1  mov     [rsp+3B0h+var_348], r14d
0x18001bde6  mov     [rbp+2B0h+var_2F0], r14
0x18001bdea  mov     [rsp+3B0h+var_360], r14
0x18001bdef  mov     [rsp+3B0h+var_370], r14
0x18001bdf4  mov     [rbp+2B0h+var_310], r14
0x18001bdf8  mov     [rsp+3B0h+var_338], r14
0x18001bdfd  mov     [rbp+2B0h+var_330], r14
0x18001be01  mov     [rbp+2B0h+var_2E8], r14
0x18001be05  mov     [rbp+2B0h+var_2E0], r14
0x18001be09  mov     [rbp+2B0h+var_2D8], r14
0x18001be0d  mov     [rbp+2B0h+Str], r14
0x18001be11  mov     [rbp+2B0h+var_320], r14d
0x18001be15  call    memset_0
0x18001be1a  mov     [rbp+2B0h+var_268], 200h
0x18001be21  lea     rax, [rbp+2B0h+var_240]
0x18001be25  mov     [rbp+2B0h+var_270], rax
0x18001be29  mov     [rbp+2B0h+var_264], 100h
0x18001be2f  mov     [rbp+2B0h+var_260], r14d
0x18001be33  mov     [rbp+2B0h+var_240], r14w
0x18001be38  test    r12, r12
0x18001be3b  jz      loc_18001C87D
0x18001be41  test    rsi, rsi
0x18001be44  jz      loc_18001C87D
0x18001be4a  test    rdi, rdi
0x18001be4d  jz      loc_18001C87D
0x18001be53  test    rbx, rbx
0x18001be56  jz      loc_18001C87D
0x18001be5c  mov     rax, [rdi]
0x18001be5f  lea     rdx, [rsp+3B0h+var_358]
0x18001be64  mov     rcx, rdi
0x18001be67  mov     rax, [rax+18h]
0x18001be6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be70  mov     ebx, eax
0x18001be72  test    eax, eax
0x18001be74  js      loc_18001C882
0x18001be7a  mov     rax, [r12]
0x18001be7e  lea     r8, [rbp+2B0h+var_300]
0x18001be82  mov     rdx, rsi
0x18001be85  mov     rcx, r12
0x18001be88  mov     rax, [rax+50h]
0x18001be8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be91  mov     ebx, eax
0x18001be93  test    eax, eax
0x18001be95  js      loc_18001C882
0x18001be9b  mov     rcx, [rbp+2B0h+var_300]
0x18001be9f  lea     rdx, [rbp+2B0h+var_328]
0x18001bea3  mov     [rsp+3B0h+var_388], r14
0x18001bea8  lea     r9, [rbp+2B0h+var_2C8]
0x18001beac  mov     [rsp+3B0h+var_390], rdx
0x18001beb1  mov     r8, rsi
0x18001beb4  lea     rdx, aSystemWebHttph; "system.web/httpHandlers"
0x18001bebb  mov     rax, [rcx]
0x18001bebe  mov     rax, [rax+18h]
0x18001bec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bec7  mov     ebx, eax
0x18001bec9  test    eax, eax
0x18001becb  jns     short loc_18001BF00
0x18001becd  mov     rcx, [rbp+2B0h+var_328]
0x18001bed1  test    rcx, rcx
0x18001bed4  jz      loc_18001C882
0x18001beda  mov     rax, [r12]
0x18001bede  lea     r8, Str
0x18001bee5  mov     r9, rcx
0x18001bee8  mov     dword ptr [rsp+3B0h+var_390], r14d
0x18001beed  mov     edx, ebx
0x18001beef  mov     rcx, r12
0x18001bef2  mov     rax, [rax+70h]
0x18001bef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001befb  jmp     loc_18001C882
0x18001bf00  mov     rcx, [rbp+2B0h+var_2C8]
0x18001bf04  lea     rdx, [rbp+2B0h+var_2F8]
0x18001bf08  mov     rax, [rcx]
0x18001bf0b  mov     rax, [rax+28h]
0x18001bf0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf14  mov     ebx, eax
0x18001bf16  test    eax, eax
0x18001bf18  js      loc_18001C882
0x18001bf1e  mov     rcx, [rbp+2B0h+var_2F8]
0x18001bf22  lea     rdx, [rsp+3B0h+var_348]
0x18001bf27  mov     rax, [rcx]
0x18001bf2a  mov     rax, [rax+18h]
0x18001bf2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf33  mov     ebx, eax
0x18001bf35  test    eax, eax
0x18001bf37  js      loc_18001C882
0x18001bf3d  mov     ebx, [rsp+3B0h+var_358]
0x18001bf41  mov     eax, 8
0x18001bf46  add     ebx, [rsp+3B0h+var_348]
0x18001bf4a  mov     r15, 0FFFFFFFFFFFFFFFFh
0x18001bf51  mul     rbx
0x18001bf54  cmovb   rax, r15
0x18001bf58  mov     rcx, rax; Size
0x18001bf5b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001bf60  mov     rsi, rax
0x18001bf63  test    rax, rax
0x18001bf66  jnz     short loc_18001BF72
0x18001bf68  mov     ebx, 80070008h
0x18001bf6d  jmp     loc_18001C882
0x18001bf72  mov     eax, 4
0x18001bf77  mul     rbx
0x18001bf7a  cmovb   rax, r15
0x18001bf7e  mov     rcx, rax; Size
0x18001bf81  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001bf86  mov     [rsp+3B0h+Block], rax
0x18001bf8b  mov     r15, rax
0x18001bf8e  test    rax, rax
0x18001bf91  jnz     short loc_18001BF9D
0x18001bf93  mov     ebx, 80070008h
0x18001bf98  jmp     loc_18001C869
0x18001bf9d  mov     [rsp+3B0h+var_368], r14d
0x18001bfa2  cmp     r14d, [rsp+3B0h+var_358]
0x18001bfa7  jnb     short loc_18001BFE1
0x18001bfa9  mov     rax, [rdi]
0x18001bfac  lea     r8, [rbp+2B0h+var_2F0]
0x18001bfb0  mov     edx, r14d
0x18001bfb3  mov     rcx, rdi
0x18001bfb6  mov     rax, [rax+20h]
0x18001bfba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bfbf  mov     ebx, eax
0x18001bfc1  test    eax, eax
0x18001bfc3  js      loc_18001C82F
0x18001bfc9  mov     rax, [rbp+2B0h+var_2F0]
0x18001bfcd  mov     ecx, r14d
0x18001bfd0  inc     r14d
0x18001bfd3  mov     [rsi+rcx*8], rax
0x18001bfd7  mov     [r15+rcx*4], r13d
0x18001bfdb  mov     [rbp+2B0h+var_2F0], r13
0x18001bfdf  jmp     short loc_18001BF9D
0x18001bfe1  xor     edi, edi
0x18001bfe3  mov     r15d, edi
0x18001bfe6  cmp     r15d, [rsp+3B0h+var_348]
0x18001bfeb  jnb     loc_18001C20B
0x18001bff1  mov     rcx, [rbp+2B0h+var_2F8]
0x18001bff5  lea     r8, [rsp+3B0h+var_360]
0x18001bffa  mov     edx, r15d
0x18001bffd  mov     rax, [rcx]
0x18001c000  mov     rax, [rax+20h]
0x18001c004  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c009  mov     ebx, eax
0x18001c00b  test    eax, eax
0x18001c00d  js      loc_18001C82F
0x18001c013  mov     rcx, [rsp+3B0h+var_360]
0x18001c018  lea     r8, [rsp+3B0h+var_338]
0x18001c01d  xor     r9d, r9d
0x18001c020  mov     [rsp+3B0h+var_390], rdi
0x18001c025  lea     rdx, aPath_1; "path"
0x18001c02c  mov     rax, [rcx]
0x18001c02f  mov     rax, [rax+40h]
0x18001c033  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c038  mov     ebx, eax
0x18001c03a  test    eax, eax
0x18001c03c  js      loc_18001C82F
0x18001c042  mov     rcx, [rsp+3B0h+var_360]
0x18001c047  lea     r8, [rbp+2B0h+var_330]
0x18001c04b  xor     r9d, r9d
0x18001c04e  mov     [rsp+3B0h+var_390], rdi
0x18001c053  lea     rdx, aVerb; "verb"
0x18001c05a  mov     rax, [rcx]
0x18001c05d  mov     rax, [rax+40h]
0x18001c061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c066  mov     ebx, eax
0x18001c068  test    eax, eax
0x18001c06a  js      loc_18001C82F
0x18001c070  mov     rcx, [rsp+3B0h+var_360]
0x18001c075  lea     r8, [rbp+2B0h+var_310]
0x18001c079  xor     r9d, r9d
0x18001c07c  mov     [rsp+3B0h+var_390], rdi
0x18001c081  lea     rdx, aType; "type"
0x18001c088  mov     rax, [rcx]
0x18001c08b  mov     rax, [rax+40h]
0x18001c08f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c094  mov     ebx, eax
0x18001c096  test    eax, eax
0x18001c098  js      loc_18001C82F
0x18001c09e  cmp     edi, [rsp+3B0h+var_358]
0x18001c0a2  jnb     loc_18001C1B7
0x18001c0a8  mov     r14d, edi
0x18001c0ab  lea     r8, [rbp+2B0h+var_2E8]
0x18001c0af  xor     r9d, r9d
0x18001c0b2  mov     [rsp+3B0h+var_390], r13
0x18001c0b7  lea     rdx, aPath_1; "path"
0x18001c0be  mov     rcx, [rsi+r14*8]
0x18001c0c2  mov     rax, [rcx]
0x18001c0c5  mov     rax, [rax+40h]
0x18001c0c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c0ce  mov     ebx, eax
0x18001c0d0  test    eax, eax
0x18001c0d2  js      loc_18001C82F
0x18001c0d8  mov     rcx, [rsi+r14*8]
0x18001c0dc  lea     r8, [rbp+2B0h+var_2E0]
0x18001c0e0  xor     r9d, r9d
0x18001c0e3  mov     [rsp+3B0h+var_390], r13
0x18001c0e8  lea     rdx, aVerb; "verb"
0x18001c0ef  mov     rax, [rcx]
0x18001c0f2  mov     rax, [rax+40h]
0x18001c0f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c0fb  mov     ebx, eax
0x18001c0fd  test    eax, eax
0x18001c0ff  js      loc_18001C82F
0x18001c105  mov     rcx, [rsi+r14*8]
0x18001c109  lea     r8, [rbp+2B0h+var_2D8]
0x18001c10d  xor     r9d, r9d
0x18001c110  mov     [rsp+3B0h+var_390], r13
0x18001c115  lea     rdx, aType; "type"
0x18001c11c  mov     rax, [rcx]
0x18001c11f  mov     rax, [rax+40h]
0x18001c123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c128  mov     ebx, eax
0x18001c12a  test    eax, eax
0x18001c12c  js      loc_18001C82F
0x18001c132  mov     rax, [rbp+2B0h+var_2E8]
0x18001c136  mov     r8, [rsp+3B0h+var_338]
0x18001c13b  sub     r8, rax
0x18001c13e  movzx   edx, word ptr [rax]
0x18001c141  movzx   ecx, word ptr [rax+r8]
0x18001c146  sub     edx, ecx
0x18001c148  jnz     short loc_18001C152
0x18001c14a  add     rax, 2
0x18001c14e  test    ecx, ecx
0x18001c150  jnz     short loc_18001C13E
0x18001c152  test    edx, edx
0x18001c154  jnz     short loc_18001C19C
0x18001c156  mov     rax, [rbp+2B0h+var_2E0]
0x18001c15a  mov     r8, [rbp+2B0h+var_330]
0x18001c15e  sub     r8, rax
0x18001c161  movzx   edx, word ptr [rax]
0x18001c164  movzx   ecx, word ptr [rax+r8]
0x18001c169  sub     edx, ecx
0x18001c16b  jnz     short loc_18001C175
0x18001c16d  add     rax, 2
0x18001c171  test    ecx, ecx
0x18001c173  jnz     short loc_18001C161
0x18001c175  test    edx, edx
0x18001c177  jnz     short loc_18001C19C
0x18001c179  mov     rax, [rbp+2B0h+var_2D8]
0x18001c17d  mov     r8, [rbp+2B0h+var_310]
0x18001c181  sub     r8, rax
0x18001c184  movzx   edx, word ptr [rax]
0x18001c187  movzx   ecx, word ptr [rax+r8]
0x18001c18c  sub     edx, ecx
0x18001c18e  jnz     short loc_18001C198
0x18001c190  add     rax, 2
0x18001c194  test    ecx, ecx
0x18001c196  jnz     short loc_18001C184
0x18001c198  test    edx, edx
0x18001c19a  jz      short loc_18001C1A3
0x18001c19c  inc     edi
0x18001c19e  jmp     loc_18001C09E
0x18001c1a3  mov     rax, [rsp+3B0h+Block]
0x18001c1a8  mov     dword ptr [rax+r14*4], 1
0x18001c1b0  mov     r14d, [rsp+3B0h+var_368]
0x18001c1b5  jmp     short loc_18001C1EB
0x18001c1b7  mov     rax, [rsp+3B0h+var_360]
0x18001c1bc  mov     r14d, [rsp+3B0h+var_368]
0x18001c1c1  mov     [rsi+r14*8], rax
0x18001c1c5  mov     rcx, [rsp+3B0h+var_360]
0x18001c1ca  mov     rax, [rcx]
0x18001c1cd  mov     rax, [rax+8]
0x18001c1d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c1d6  mov     rax, [rsp+3B0h+Block]
0x18001c1db  mov     dword ptr [rax+r14*4], 2
0x18001c1e3  inc     r14d
  ... truncated ...
```
