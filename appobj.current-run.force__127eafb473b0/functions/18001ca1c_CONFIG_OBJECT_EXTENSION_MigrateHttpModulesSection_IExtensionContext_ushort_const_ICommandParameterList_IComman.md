# CONFIG_OBJECT_EXTENSION::MigrateHttpModulesSection(IExtensionContext *,ushort const *,ICommandParameterList *,ICommandObjectList *)

- ea: `0x18001ca1c`
- end: `0x18001d70d`
- name: `?MigrateHttpModulesSection@CONFIG_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEBGPEAVICommandParameterList@@PEAVICommandObjectList@@@Z`
- size: `3313`
- prototype: `int(CONFIG_OBJECT_EXTENSION *__hidden this, struct IExtensionContext *, const unsigned __int16 *, struct ICommandParameterList *, struct ICommandObjectList *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001b350`

## callees

- `0x180001044`
- `0x180001084`
- `0x180001fb0`
- `0x180002e90`
- `0x18000557c`
- `0x180006b6c`
- `0x180019948`
- `0x18001ca1c`
- `0x18002b0cc`
- `0x18002bd3c`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## pseudocode

```c
__int64 __fastcall CONFIG_OBJECT_EXTENSION::MigrateHttpModulesSection(
        CONFIG_OBJECT_EXTENSION *this,
        struct IExtensionContext *a2,
        const unsigned __int16 *a3,
        struct ICommandParameterList *a4,
        struct ICommandObjectList *a5)
{
  unsigned int v5; // r12d
  STATUS_OBJECT *v9; // rsi
  APP_OBJECT_UTILS *v10; // rcx
  int v11; // ebx
  APP_OBJECT_UTILS *v12; // rcx
  APP_OBJECT_UTILS *v13; // rcx
  unsigned __int64 v14; // rbx
  _QWORD *v15; // r14
  _DWORD *v16; // r13
  unsigned int v17; // edi
  __int64 v18; // rcx
  __int64 i; // rdi
  unsigned __int16 *v20; // rax
  int v21; // ecx
  int v22; // edx
  unsigned __int16 *v23; // rax
  int v24; // ecx
  int v25; // edx
  int v26; // r13d
  unsigned int j; // eax
  __int64 v28; // rdi
  unsigned int k; // edi
  unsigned __int16 *v30; // rax
  int v31; // ecx
  int v32; // edx
  unsigned __int16 *v33; // rax
  int v34; // ecx
  int v35; // edx
  STATUS_OBJECT *v36; // rax
  STATUS_OBJECT *v37; // rax
  int v38; // ecx
  CONFIG_OBJECT_EXTENSION *v39; // rcx
  struct ICommandObjectList *v40; // rdi
  STATUS_OBJECT *v41; // rax
  unsigned int v42; // eax
  __int64 v43; // rcx
  int v45; // [rsp+28h] [rbp-D8h]
  int v46; // [rsp+28h] [rbp-D8h]
  unsigned int v47; // [rsp+40h] [rbp-C0h]
  __int64 v48; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v49; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v50; // [rsp+58h] [rbp-A8h] BYREF
  int v51; // [rsp+5Ch] [rbp-A4h] BYREF
  __int64 v52; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v53; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v54; // [rsp+70h] [rbp-90h] BYREF
  va_list v55; // [rsp+78h] [rbp-88h] BYREF
  _DWORD *v56; // [rsp+80h] [rbp-80h]
  struct ICommandParameterList *v57; // [rsp+88h] [rbp-78h] BYREF
  va_list v58; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v59; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v60; // [rsp+9Ch] [rbp-64h]
  int v61; // [rsp+A0h] [rbp-60h] BYREF
  char *v62; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v63; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v64; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v65; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v66; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v67; // [rsp+D0h] [rbp-30h] BYREF
  char *v68; // [rsp+D8h] [rbp-28h] BYREF
  struct ICommandParameterList *v69; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v70; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v71; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v72; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v73; // [rsp+100h] [rbp+0h] BYREF
  struct ICommandObjectList *v74; // [rsp+108h] [rbp+8h]
  __int64 v75; // [rsp+110h] [rbp+10h]
  __int64 v76; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v77[32]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 *v78; // [rsp+140h] [rbp+40h]
  int v79; // [rsp+148h] [rbp+48h]
  __int16 v80; // [rsp+14Ch] [rbp+4Ch]
  int v81; // [rsp+150h] [rbp+50h]
  va_list Arguments[2]; // [rsp+158h] [rbp+58h] BYREF
  char *v83; // [rsp+168h] [rbp+68h]
  __int16 v84; // [rsp+170h] [rbp+70h] BYREF
  char v85[510]; // [rsp+172h] [rbp+72h] BYREF

  v5 = 0;
  v74 = a5;
  v69 = 0;
  v57 = 0;
  v70 = 0;
  v64 = 0;
  v83 = 0;
  v52 = 0;
  *(_OWORD *)Arguments = 0;
  v63 = 0;
  v76 = 0;
  v71 = 0;
  v72 = 0;
  v65 = 0;
  v66 = 0;
  v53 = 0;
  v73 = 0;
  memset_0(v85, 0, sizeof(v85));
  v79 = 512;
  v78 = (unsigned __int16 *)&v84;
  v9 = 0;
  v80 = 256;
  v81 = 0;
  v84 = 0;
  v50 = 0;
  v54 = 0;
  v67 = 0;
  v49 = 0;
  v48 = 0;
  v58 = 0;
  v55 = 0;
  v68 = 0;
  v62 = 0;
  v59 = 0;
  v61 = 0;
  v51 = 0;
  if ( !a2 || !a3 || !a4 || !a5 )
  {
    v11 = -2147024809;
    goto LABEL_122;
  }
  v11 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, struct ICommandParameterList **))(*(_QWORD *)a4 + 80LL))(
          a4,
          &v57);
  if ( v11 >= 0 )
  {
    v11 = APP_OBJECT_UTILS::PopBooleanParameter(v10, a2, v57, L"clear", &v61, v45, 1);
    if ( (int)(v11 + 0x80000000) < 0 || v11 == -2147023483 )
    {
      v11 = APP_OBJECT_UTILS::PopBooleanParameter(v12, a2, v57, L"recurse", &v51, v46, 1);
      if ( ((v11 + 0x80000000) & 0x80000000) != 0 || v11 == -2147023483 )
      {
        v11 = APP_OBJECT_UTILS::ValidateEmptyParameters(v13, a2, v57);
        if ( v11 >= 0 )
        {
          v11 = STRU::Copy((STRU *)v77, a3);
          if ( v11 >= 0 )
          {
            v11 = (*(__int64 (__fastcall **)(struct IExtensionContext *, const wchar_t *, __int64 *))(*(_QWORD *)a2 + 80LL))(
                    a2,
                    L"MACHINE/WEBROOT/APPHOST",
                    &v70);
            if ( v11 >= 0 )
            {
              v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, __int64 *, __int64 *, _QWORD))(*(_QWORD *)v70 + 24LL))(
                      v70,
                      L"system.web/httpModules",
                      L"MACHINE/WEBROOT/APPHOST",
                      &v71,
                      &v52,
                      0);
              if ( v11 < 0 )
                goto LABEL_14;
              v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v71 + 40LL))(v71, &v65);
              if ( v11 < 0 )
                goto LABEL_122;
              v11 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v65 + 24LL))(v65, &v50);
              if ( v11 < 0 )
                goto LABEL_122;
              v11 = (*(__int64 (__fastcall **)(struct IExtensionContext *, unsigned __int16 *, __int64 *))(*(_QWORD *)a2 + 80LL))(
                      a2,
                      v78,
                      &v64);
              if ( v11 < 0 )
                goto LABEL_122;
              v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 *, __int64 *, __int64 *, _QWORD))(*(_QWORD *)v64 + 24LL))(
                      v64,
                      L"system.web/httpModules",
                      v78,
                      &v72,
                      &v52,
                      0);
              if ( v11 < 0 )
              {
LABEL_14:
                if ( v52 )
                  (*(void (__fastcall **)(struct IExtensionContext *, _QWORD, const wchar_t *, __int64, _DWORD))(*(_QWORD *)a2 + 112LL))(
                    a2,
                    (unsigned int)v11,
                    &Str,
                    v52,
                    0);
                goto LABEL_122;
              }
              v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v72 + 40LL))(v72, &v66);
              if ( v11 < 0 )
                goto LABEL_122;
              v11 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v66 + 24LL))(v66, &v54);
              if ( v11 < 0 )
                goto LABEL_122;
              v14 = v54 + v50;
              v15 = operator new(saturated_mul(v14, 8u));
              if ( !v15 )
              {
                v11 = -2147024888;
                goto LABEL_122;
              }
              v56 = operator new(saturated_mul(v14, 4u));
              v16 = v56;
              if ( !v56 )
              {
                v11 = -2147024888;
                goto LABEL_120;
              }
              v17 = 0;
              while ( 1 )
              {
                v47 = v17;
                if ( v17 >= v50 )
                  break;
                v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v65 + 32LL))(v65, v17, &v67);
                if ( v11 < 0 )
                  goto LABEL_115;
                v18 = v17++;
                v15[v18] = v67;
                v16[v18] = 0;
                v67 = 0;
              }
              while ( v5 < v54 )
              {
                v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v66 + 32LL))(v66, v5, &v49);
                if ( v11 < 0
                  || (v11 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, va_list *, _QWORD, _QWORD))(*(_QWORD *)v49 + 64LL))(
                              v49,
                              L"name",
                              &v58,
                              0,
                              0),
                      v11 < 0)
                  || (v11 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, va_list *, _QWORD, _QWORD))(*(_QWORD *)v49 + 64LL))(
                              v49,
                              L"type",
                              &v55,
                              0,
                              0),
                      v11 < 0) )
                {
LABEL_50:
                  v5 = 0;
                  goto LABEL_115;
                }
                for ( i = 0; (unsigned int)i < v50; i = (unsigned int)(i + 1) )
                {
                  v11 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, char **, _QWORD, _QWORD))(*(_QWORD *)v15[i] + 64LL))(
                          v15[i],
                          L"name",
                          &v68,
                          0,
                          0);
                  if ( v11 < 0 )
                    goto LABEL_50;
                  v11 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, char **, _QWORD, _QWORD))(*(_QWORD *)v15[i] + 64LL))(
                          v15[i],
                          L"type",
                          &v62,
                          0,
                          0);
                  if ( v11 < 0 )
                    goto LABEL_50;
                  v20 = (unsigned __int16 *)v68;
                  do
                  {
                    v21 = *(unsigned __int16 *)((char *)v20 + v58 - v68);
                    v22 = *v20 - v21;
                    if ( v22 )
                      break;
                    ++v20;
                  }
                  while ( v21 );
                  if ( !v22 )
                  {
                    v23 = (unsigned __int16 *)v62;
                    do
                    {
                      v24 = *(unsigned __int16 *)((char *)v23 + v55 - v62);
                      v25 = *v23 - v24;
                      if ( v25 )
                        break;
                      ++v23;
                    }
                    while ( v24 );
                    if ( !v25 )
                    {
                      v16[i] = 1;
                      v17 = v47;
                      goto LABEL_49;
                    }
                  }
                }
                v15[v47] = v49;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 8LL))(v49);
                v16[v47] = 2;
                v17 = ++v47;
LABEL_49:
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
                ++v5;
                v49 = 0;
              }
              v5 = 0;
              v11 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, unsigned __int16 *, __int64 *, __int64 *, _QWORD))(*(_QWORD *)v64 + 24LL))(
                      v64,
                      L"system.webServer/modules",
                      v78,
                      &v73,
                      &v52,
                      0);
              if ( v11 < 0 )
              {
                if ( v52 )
                  (*(void (__fastcall **)(struct IExtensionContext *, _QWORD, const wchar_t *))(*(_QWORD *)a2 + 112LL))(
                    a2,
                    (unsigned int)v11,
                    &Str);
                goto LABEL_115;
              }
              v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v73 + 40LL))(v73, &v53);
              if ( v11 < 0 )
                goto LABEL_115;
              v60 = 0;
              v26 = 0;
              for ( j = 0; ; j = v51 + 1 )
              {
                v51 = j;
                if ( j >= v17 )
                {
                  if ( v61 )
                  {
                    v11 = (*(__int64 (__fastcall **)(struct IExtensionContext *, struct ICommandParameterList **))(*(_QWORD *)a2 + 192LL))(
                            a2,
                            &v69);
                    if ( v11 >= 0 )
                    {
                      v40 = v74;
                      v11 = CONFIG_OBJECT_EXTENSION::DoClear(v39, a2, v78, L"system.web/httpModules", v69, v74);
                      if ( v11 >= 0 )
                      {
                        v26 = 1;
                        goto LABEL_105;
                      }
                    }
                    goto LABEL_114;
                  }
                  v40 = v74;
LABEL_105:
                  v11 = (*(__int64 (__fastcall **)(struct IExtensionContext *, unsigned __int16 *, __int64))(*(_QWORD *)a2 + 208LL))(
                          a2,
                          v78,
                          1);
                  if ( v11 < 0 )
                  {
LABEL_114:
                    v9 = 0;
                    goto LABEL_115;
                  }
                  if ( !v26 )
                  {
                    v11 = 1;
                    goto LABEL_114;
                  }
                  v41 = (STATUS_OBJECT *)operator new(0x110u);
                  if ( v41 )
                  {
                    v9 = STATUS_OBJECT::STATUS_OBJECT(v41);
                    if ( v9 )
                    {
                      Arguments[1] = 0;
                      Arguments[0] = (va_list)L"system.web/httpModules";
                      v11 = STATUS_OBJECT::Create(v9, 0x413u, Arguments);
                      if ( v11 >= 0 )
                        v11 = (*(__int64 (__fastcall **)(struct ICommandObjectList *, STATUS_OBJECT *))(*(_QWORD *)v40 + 24LL))(
                                v40,
                                v9);
LABEL_115:
                      v42 = v47;
                      if ( v47 )
                      {
                        do
                        {
                          v43 = v15[v5];
                          if ( v43 )
                          {
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
                            v42 = v47;
                            v15[v5] = 0;
                          }
                          ++v5;
                        }
                        while ( v5 < v42 );
                      }
                      v16 = v56;
LABEL_120:
                      operator delete(v15);
                      operator delete(v16);
                      break;
                    }
                  }
                  else
                  {
                    v9 = 0;
                  }
LABEL_112:
                  v11 = -2147024888;
                  goto LABEL_115;
                }
                v28 = j;
                v75 = j;
                v49 = v15[j];
                v11 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, va_list *, _QWORD, _QWORD))(*(_QWORD *)v49 + 64LL))(
                        v49,
                        L"name",
                        &v58,
                        0,
                        0);
                if ( v11 < 0 )
                  goto LABEL_114;
                v11 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, va_list *, _QWORD, _QWORD))(*(_QWORD *)v49 + 64LL))(
                        v49,
                        L"type",
                        &v55,
                        0,
                        0);
                if ( v11 < 0 )
                  goto LABEL_114;
                v49 = 0;
                if ( (v56[v28] & 0xFFFFFFFD) != 0 )
                {
                  v9 = 0;
                }
                else
                {
                  v11 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v53 + 24LL))(v53, &v59);
                  if ( v11 < 0 )
                  {
                    v5 = 0;
                    goto LABEL_114;
                  }
                  for ( k = 0; ; ++k )
                  {
                    v9 = 0;
                    if ( k >= v59 )
                      break;
                    v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v53 + 32LL))(v53, k, &v48);
                    if ( v11 < 0 )
                      goto LABEL_50;
                    v11 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, char **, _QWORD, _QWORD))(*(_QWORD *)v48 + 64LL))(
                            v48,
                            L"name",
                            &v68,
                            0,
                            0);
                    if ( v11 < 0 )
                      goto LABEL_50;
                    v11 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, char **, _QWORD, _QWORD))(*(_QWORD *)v48 + 64LL))(
                            v48,
                            L"type",
                            &v62,
                            0,
                            0);
                    if ( v11 < 0 )
                      goto LABEL_50;
                    v30 = (unsigned __int16 *)v58;
                    do
                    {
                      v31 = *(unsigned __int16 *)((char *)v30 + v68 - v58);
                      v32 = *v30 - v31;
                      if ( v32 )
                        break;
                      ++v30;
                    }
                    while ( v31 );
                    if ( !v32 )
                    {
                      v33 = (unsigned __int16 *)v55;
                      do
                      {
                        v34 = *(unsigned __int16 *)((char *)v33 + v62 - v55);
                        v35 = *v33 - v34;
                        if ( v35 )
                          break;
                        ++v33;
                      }
                      while ( v34 );
                      v5 = 0;
                      if ( v35 )
                      {
                        v36 = (STATUS_OBJECT *)operator new(0x110u);
                        if ( !v36 )
                          goto LABEL_112;
                        v37 = STATUS_OBJECT::STATUS_OBJECT(v36);
                        v9 = v37;
                        if ( !v37 )
                          goto LABEL_112;
                        Arguments[0] = v58;
                        Arguments[1] = v55;
                        v83 = v62;
                        v11 = STATUS_OBJECT::Create(v37, 0xC000042C, Arguments);
                        if ( v11 < 0 )
                          goto LABEL_115;
                        v11 = (*(__int64 (__fastcall **)(struct ICommandObjectList *, STATUS_OBJECT *))(*(_QWORD *)v74 + 24LL))(
                                v74,
                                v9);
                        if ( v11 < 0 )
                          goto LABEL_115;
                        (*(void (__fastcall **)(STATUS_OBJECT *))(*(_QWORD *)v9 + 16LL))(v9);
                      }
                      v5 = 1;
                      v60 = k;
                    }
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
                    v9 = 0;
                    v48 = 0;
                    if ( v5 )
                      break;
                  }
                  v28 = v75;
                }
                v38 = v56[v28];
                if ( v38 )
                {
                  if ( v38 == 2 && !v5 )
                  {
                    v5 = 0;
                    v11 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64 *))(*(_QWORD *)v53 + 48LL))(
                            v53,
                            L"add",
                            &v48);
                    if ( v11 < 0 )
                      goto LABEL_115;
                    v11 = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64, const unsigned __int16 *, va_list))(*(_QWORD *)a2 + 96LL))(
                            a2,
                            v48,
                            L"name",
                            v58);
                    if ( v11 < 0 )
                      goto LABEL_115;
                    v11 = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64, const unsigned __int16 *, va_list))(*(_QWORD *)a2 + 96LL))(
                            a2,
                            v48,
                            L"type",
                            v55);
                    if ( v11 < 0 )
                      goto LABEL_115;
                    v11 = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64, const wchar_t *, const wchar_t *))(*(_QWORD *)a2 + 96LL))(
                            a2,
                            v48,
                            L"preCondition",
                            L"managedHandler");
                    if ( v11 < 0 )
                      goto LABEL_115;
                    v11 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)v53 + 56LL))(
                            v53,
                            v48,
                            0xFFFFFFFFLL,
                            &v63);
                    if ( v11 < 0 )
                      goto LABEL_115;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
                    v48 = 0;
                    goto LABEL_93;
                  }
                }
                else if ( v5 )
                {
                  v5 = 0;
                  v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v53 + 64LL))(v53, v60, &v63);
                  if ( v11 < 0 )
                    goto LABEL_115;
LABEL_93:
                  v26 = 1;
                  goto LABEL_98;
                }
                v5 = 0;
LABEL_98:
                v17 = v47;
              }
            }
          }
        }
      }
    }
  }
LABEL_122:
  if ( v63 )
  {
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v63 + 24LL))(v63, &v76);
    (*(void (__fastcall **)(struct IExtensionContext *, _QWORD, __int64, _QWORD))(*(_QWORD *)a2 + 128LL))(
      a2,
      (unsigned int)v11,
      v76,
      0);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
    v63 = 0;
  }
  if ( v69 )
  {
    (*(void (__fastcall **)(struct ICommandParameterList *))(*(_QWORD *)v69 + 16LL))(v69);
    v69 = 0;
  }
  if ( v57 )
  {
    (*(void (__fastcall **)(struct ICommandParameterList *))(*(_QWORD *)v57 + 16LL))(v57);
    v57 = 0;
  }
  if ( v70 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 16LL))(v70);
    v70 = 0;
  }
  if ( v52 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    v52 = 0;
  }
  if ( v71 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
    v71 = 0;
  }
  if ( v64 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
    v64 = 0;
  }
  if ( v72 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
    v72 = 0;
  }
  if ( v65 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
    v65 = 0;
  }
  if ( v66 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
    v66 = 0;
  }
  if ( v53 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
    v53 = 0;
  }
  if ( v73 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
    v73 = 0;
  }
  if ( v67 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
    v67 = 0;
  }
  if ( v49 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
    v49 = 0;
  }
  if ( v48 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
    v48 = 0;
  }
  if ( v9 )
    (*(void (__fastcall **)(STATUS_OBJECT *))(*(_QWORD *)v9 + 16LL))(v9);
  BUFFER::~BUFFER((BUFFER *)v77);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18001ca1c  mov     [rsp-8+arg_0], rbx
0x18001ca21  push    rbp
0x18001ca22  push    rsi
0x18001ca23  push    rdi
0x18001ca24  push    r12
0x18001ca26  push    r13
0x18001ca28  push    r14
0x18001ca2a  push    r15
0x18001ca2c  lea     rbp, [rsp-280h]
0x18001ca34  sub     rsp, 380h
0x18001ca3b  mov     rax, cs:__security_cookie
0x18001ca42  xor     rax, rsp
0x18001ca45  mov     [rbp+2B0h+var_40], rax
0x18001ca4c  mov     r14, [rbp+2B0h+arg_20]
0x18001ca53  lea     rcx, [rbp+2B0h+var_23E]; void *
0x18001ca57  xor     r12d, r12d
0x18001ca5a  mov     [rbp+2B0h+var_2A8], r14
0x18001ca5e  mov     rdi, r8
0x18001ca61  mov     [rbp+2B0h+var_2D0], r12
0x18001ca65  mov     r15, rdx
0x18001ca68  mov     [rbp+2B0h+var_328], r12
0x18001ca6c  xorps   xmm0, xmm0
0x18001ca6f  mov     [rbp+2B0h+var_2C8], r12
0x18001ca73  xor     eax, eax
0x18001ca75  mov     [rbp+2B0h+var_2F8], r12
0x18001ca79  xor     edx, edx; Val
0x18001ca7b  mov     [rbp+2B0h+var_248], rax
0x18001ca7f  mov     r8d, 1FEh; Size
0x18001ca85  mov     [rsp+3B0h+var_350], r12
0x18001ca8a  movups  xmmword ptr [rbp+2B0h+Arguments], xmm0
0x18001ca8e  mov     [rbp+2B0h+var_300], r12
0x18001ca92  mov     rbx, r9
0x18001ca95  mov     [rbp+2B0h+var_298], r12
0x18001ca99  mov     [rbp+2B0h+var_2C0], r12
0x18001ca9d  mov     [rbp+2B0h+var_2B8], r12
0x18001caa1  mov     [rbp+2B0h+var_2F0], r12
0x18001caa5  mov     [rbp+2B0h+var_2E8], r12
0x18001caa9  mov     [rsp+3B0h+var_348], r12
0x18001caae  mov     [rbp+2B0h+var_2B0], r12
0x18001cab2  call    memset_0
0x18001cab7  mov     [rbp+2B0h+var_268], 200h
0x18001cabe  lea     rax, [rbp+2B0h+var_240]
0x18001cac2  mov     [rbp+2B0h+var_270], rax
0x18001cac6  mov     esi, r12d
0x18001cac9  mov     [rbp+2B0h+var_264], 100h
0x18001cacf  mov     [rbp+2B0h+var_260], r12d
0x18001cad3  mov     [rbp+2B0h+var_240], r12w
0x18001cad8  mov     [rsp+3B0h+var_358], r12d
0x18001cadd  mov     [rsp+3B0h+var_340], r12d
0x18001cae2  mov     [rbp+2B0h+var_2E0], r12
0x18001cae6  mov     [rsp+3B0h+var_360], r12
0x18001caeb  mov     [rsp+3B0h+var_368], r12
0x18001caf0  mov     [rbp+2B0h+var_320], r12
0x18001caf4  mov     [rsp+3B0h+var_338], r12
0x18001caf9  mov     [rbp+2B0h+var_2D8], r12
0x18001cafd  mov     [rbp+2B0h+var_308], r12
0x18001cb01  mov     [rbp+2B0h+var_318], r12d
0x18001cb05  mov     [rbp+2B0h+var_310], r12d
0x18001cb09  mov     [rsp+3B0h+var_354], r12d
0x18001cb0e  test    r15, r15
0x18001cb11  jz      loc_18001D511
0x18001cb17  test    rdi, rdi
0x18001cb1a  jz      loc_18001D511
0x18001cb20  test    rbx, rbx
0x18001cb23  jz      loc_18001D511
0x18001cb29  test    r14, r14
0x18001cb2c  jz      loc_18001D511
0x18001cb32  mov     rax, [rbx]
0x18001cb35  lea     rdx, [rbp+2B0h+var_328]
0x18001cb39  mov     rcx, rbx
0x18001cb3c  mov     rax, [rax+50h]
0x18001cb40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb45  mov     ebx, eax
0x18001cb47  test    eax, eax
0x18001cb49  js      loc_18001D516
0x18001cb4f  mov     r8, [rbp+2B0h+var_328]; struct ICommandParameterList *
0x18001cb53  lea     rax, [rbp+2B0h+var_310]
0x18001cb57  mov     [rsp+3B0h+var_380], 1; int
0x18001cb5f  lea     r9, aClear; "clear"
0x18001cb66  mov     rdx, r15; struct IExtensionContext *
0x18001cb69  mov     [rsp+3B0h+var_390], rax; int *
0x18001cb6e  call    ?PopBooleanParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAHHH@Z; APP_OBJECT_UTILS::PopBooleanParameter(IExtensionContext *,ICommandParameterList *,ushort const *,int *,int,int)
0x18001cb73  mov     r14d, 80000000h
0x18001cb79  mov     ebx, eax
0x18001cb7b  add     eax, r14d
0x18001cb7e  mov     r13d, 80070585h
0x18001cb84  test    r14d, eax
0x18001cb87  jnz     short loc_18001CB92
0x18001cb89  cmp     ebx, r13d
0x18001cb8c  jnz     loc_18001D516
0x18001cb92  mov     r8, [rbp+2B0h+var_328]; struct ICommandParameterList *
0x18001cb96  lea     rax, [rsp+3B0h+var_354]
0x18001cb9b  mov     [rsp+3B0h+var_380], 1; int
0x18001cba3  lea     r9, aRecurse; "recurse"
0x18001cbaa  mov     rdx, r15; struct IExtensionContext *
0x18001cbad  mov     [rsp+3B0h+var_390], rax; int *
0x18001cbb2  call    ?PopBooleanParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAHHH@Z; APP_OBJECT_UTILS::PopBooleanParameter(IExtensionContext *,ICommandParameterList *,ushort const *,int *,int,int)
0x18001cbb7  mov     ebx, eax
0x18001cbb9  add     eax, r14d
0x18001cbbc  test    r14d, eax
0x18001cbbf  jnz     short loc_18001CBCA
0x18001cbc1  cmp     ebx, r13d
0x18001cbc4  jnz     loc_18001D516
0x18001cbca  mov     r8, [rbp+2B0h+var_328]; struct ICommandParameterList *
0x18001cbce  mov     rdx, r15; struct IExtensionContext *
0x18001cbd1  call    ?ValidateEmptyParameters@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@@Z; APP_OBJECT_UTILS::ValidateEmptyParameters(IExtensionContext *,ICommandParameterList *)
0x18001cbd6  mov     ebx, eax
0x18001cbd8  test    eax, eax
0x18001cbda  js      loc_18001D516
0x18001cbe0  mov     rdx, rdi; unsigned __int16 *
0x18001cbe3  lea     rcx, [rbp+2B0h+var_290]; this
0x18001cbe7  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001cbec  mov     ebx, eax
0x18001cbee  test    eax, eax
0x18001cbf0  js      loc_18001D516
0x18001cbf6  mov     rax, [r15]
0x18001cbf9  lea     r8, [rbp+2B0h+var_2C8]
0x18001cbfd  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x18001cc04  mov     rcx, r15
0x18001cc07  mov     rax, [rax+50h]
0x18001cc0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc10  mov     ebx, eax
0x18001cc12  test    eax, eax
0x18001cc14  js      loc_18001D516
0x18001cc1a  mov     rcx, [rbp+2B0h+var_2C8]
0x18001cc1e  lea     rdx, [rsp+3B0h+var_350]
0x18001cc23  mov     [rsp+3B0h+var_388], r12
0x18001cc28  lea     rdi, aSystemWebHttpm; "system.web/httpModules"
0x18001cc2f  mov     [rsp+3B0h+var_390], rdx
0x18001cc34  lea     r9, [rbp+2B0h+var_2C0]
0x18001cc38  lea     r8, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x18001cc3f  mov     rdx, rdi
0x18001cc42  mov     rax, [rcx]
0x18001cc45  mov     rax, [rax+18h]
0x18001cc49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc4e  mov     ebx, eax
0x18001cc50  test    eax, eax
0x18001cc52  jns     short loc_18001CC87
0x18001cc54  mov     rcx, [rsp+3B0h+var_350]
0x18001cc59  test    rcx, rcx
0x18001cc5c  jz      loc_18001D516
0x18001cc62  mov     rax, [r15]
0x18001cc65  lea     r8, Str
0x18001cc6c  mov     r9, rcx
0x18001cc6f  mov     dword ptr [rsp+3B0h+var_390], r12d
0x18001cc74  mov     edx, ebx
0x18001cc76  mov     rcx, r15
0x18001cc79  mov     rax, [rax+70h]
0x18001cc7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc82  jmp     loc_18001D516
0x18001cc87  mov     rcx, [rbp+2B0h+var_2C0]
0x18001cc8b  lea     rdx, [rbp+2B0h+var_2F0]
0x18001cc8f  mov     rax, [rcx]
0x18001cc92  mov     rax, [rax+28h]
0x18001cc96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc9b  mov     ebx, eax
0x18001cc9d  test    eax, eax
0x18001cc9f  js      loc_18001D516
0x18001cca5  mov     rcx, [rbp+2B0h+var_2F0]
0x18001cca9  lea     rdx, [rsp+3B0h+var_358]
0x18001ccae  mov     rax, [rcx]
0x18001ccb1  mov     rax, [rax+18h]
0x18001ccb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ccba  mov     ebx, eax
0x18001ccbc  test    eax, eax
0x18001ccbe  js      loc_18001D516
0x18001ccc4  mov     rax, [r15]
0x18001ccc7  lea     r8, [rbp+2B0h+var_2F8]
0x18001cccb  mov     rdx, [rbp+2B0h+var_270]
0x18001cccf  mov     rcx, r15
0x18001ccd2  mov     rax, [rax+50h]
0x18001ccd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ccdb  mov     ebx, eax
0x18001ccdd  test    eax, eax
0x18001ccdf  js      loc_18001D516
0x18001cce5  mov     rcx, [rbp+2B0h+var_2F8]
0x18001cce9  lea     rdx, [rsp+3B0h+var_350]
0x18001ccee  mov     r8, [rbp+2B0h+var_270]
0x18001ccf2  lea     r9, [rbp+2B0h+var_2B8]
0x18001ccf6  mov     [rsp+3B0h+var_388], r12
0x18001ccfb  mov     [rsp+3B0h+var_390], rdx
0x18001cd00  mov     rdx, rdi
0x18001cd03  mov     rax, [rcx]
0x18001cd06  mov     rax, [rax+18h]
0x18001cd0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd0f  mov     ebx, eax
0x18001cd11  test    eax, eax
0x18001cd13  js      loc_18001CC54
0x18001cd19  mov     rcx, [rbp+2B0h+var_2B8]
0x18001cd1d  lea     rdx, [rbp+2B0h+var_2E8]
0x18001cd21  mov     rax, [rcx]
0x18001cd24  mov     rax, [rax+28h]
0x18001cd28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd2d  mov     ebx, eax
0x18001cd2f  test    eax, eax
0x18001cd31  js      loc_18001D516
0x18001cd37  mov     rcx, [rbp+2B0h+var_2E8]
0x18001cd3b  lea     rdx, [rsp+3B0h+var_340]
0x18001cd40  mov     rax, [rcx]
0x18001cd43  mov     rax, [rax+18h]
0x18001cd47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd4c  mov     ebx, eax
0x18001cd4e  test    eax, eax
0x18001cd50  js      loc_18001D516
0x18001cd56  mov     ebx, [rsp+3B0h+var_358]
0x18001cd5a  mov     eax, 8
0x18001cd5f  add     ebx, [rsp+3B0h+var_340]
0x18001cd63  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18001cd6a  mul     rbx
0x18001cd6d  cmovb   rax, rdi
0x18001cd71  mov     rcx, rax; Size
0x18001cd74  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001cd79  mov     r14, rax
0x18001cd7c  test    rax, rax
0x18001cd7f  jnz     short loc_18001CD8B
0x18001cd81  mov     ebx, 80070008h
0x18001cd86  jmp     loc_18001D516
0x18001cd8b  mov     eax, 4
0x18001cd90  mul     rbx
0x18001cd93  cmovb   rax, rdi
0x18001cd97  mov     rcx, rax; Size
0x18001cd9a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001cd9f  mov     [rbp+2B0h+var_330], rax
0x18001cda3  mov     r13, rax
0x18001cda6  test    rax, rax
0x18001cda9  jnz     short loc_18001CDB5
0x18001cdab  mov     ebx, 80070008h
0x18001cdb0  jmp     loc_18001D4FF
0x18001cdb5  mov     edi, r12d
0x18001cdb8  mov     [rsp+3B0h+var_370], edi
0x18001cdbc  cmp     edi, [rsp+3B0h+var_358]
0x18001cdc0  jnb     short loc_18001CDF9
0x18001cdc2  mov     rcx, [rbp+2B0h+var_2F0]
0x18001cdc6  lea     r8, [rbp+2B0h+var_2E0]
0x18001cdca  mov     edx, edi
0x18001cdcc  mov     rax, [rcx]
0x18001cdcf  mov     rax, [rax+20h]
0x18001cdd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cdd8  mov     ebx, eax
0x18001cdda  test    eax, eax
0x18001cddc  js      loc_18001D4C1
0x18001cde2  mov     rax, [rbp+2B0h+var_2E0]
0x18001cde6  mov     ecx, edi
0x18001cde8  inc     edi
0x18001cdea  mov     [r14+rcx*8], rax
0x18001cdee  mov     [r13+rcx*4+0], r12d
0x18001cdf3  mov     [rbp+2B0h+var_2E0], r12
0x18001cdf7  jmp     short loc_18001CDB8
0x18001cdf9  cmp     r12d, [rsp+3B0h+var_340]
0x18001cdfe  jnb     loc_18001CF99
0x18001ce04  mov     rcx, [rbp+2B0h+var_2E8]
0x18001ce08  lea     r8, [rsp+3B0h+var_360]
0x18001ce0d  mov     edx, r12d
0x18001ce10  mov     rax, [rcx]
0x18001ce13  mov     rax, [rax+20h]
0x18001ce17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce1c  mov     ebx, eax
0x18001ce1e  test    eax, eax
0x18001ce20  js      loc_18001CF91
0x18001ce26  mov     rcx, [rsp+3B0h+var_360]
0x18001ce2b  lea     r8, [rbp+2B0h+var_320]
0x18001ce2f  xor     r9d, r9d
0x18001ce32  mov     [rsp+3B0h+var_390], rsi
0x18001ce37  lea     rdx, aName_0; "name"
0x18001ce3e  mov     rax, [rcx]
0x18001ce41  mov     rax, [rax+40h]
0x18001ce45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce4a  mov     ebx, eax
0x18001ce4c  test    eax, eax
0x18001ce4e  js      loc_18001CF91
0x18001ce54  mov     rcx, [rsp+3B0h+var_360]
0x18001ce59  lea     r8, [rsp+3B0h+var_338]
0x18001ce5e  xor     r9d, r9d
0x18001ce61  mov     [rsp+3B0h+var_390], rsi
0x18001ce66  lea     rdx, aType; "type"
0x18001ce6d  mov     rax, [rcx]
0x18001ce70  mov     rax, [rax+40h]
0x18001ce74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce79  mov     ebx, eax
0x18001ce7b  test    eax, eax
0x18001ce7d  js      loc_18001CF91
0x18001ce83  xor     edi, edi
0x18001ce85  cmp     edi, [rsp+3B0h+var_358]
0x18001ce89  jnb     loc_18001CF46
0x18001ce8f  mov     rcx, [r14+rdi*8]
0x18001ce93  lea     r8, [rbp+2B0h+var_2D8]
0x18001ce97  xor     r9d, r9d
0x18001ce9a  mov     [rsp+3B0h+var_390], rsi
0x18001ce9f  lea     rdx, aName_0; "name"
0x18001cea6  mov     rax, [rcx]
0x18001cea9  mov     rax, [rax+40h]
0x18001cead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ceb2  mov     ebx, eax
0x18001ceb4  test    eax, eax
0x18001ceb6  js      loc_18001CF91
0x18001cebc  mov     rcx, [r14+rdi*8]
0x18001cec0  lea     r8, [rbp+2B0h+var_308]
0x18001cec4  xor     r9d, r9d
0x18001cec7  mov     [rsp+3B0h+var_390], rsi
0x18001cecc  lea     rdx, aType; "type"
  ... truncated ...
```
