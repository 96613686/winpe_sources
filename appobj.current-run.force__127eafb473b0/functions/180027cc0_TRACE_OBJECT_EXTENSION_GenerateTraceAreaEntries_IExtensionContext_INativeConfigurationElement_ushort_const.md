# TRACE_OBJECT_EXTENSION::GenerateTraceAreaEntries(IExtensionContext *,INativeConfigurationElement *,ushort const *)

- ea: `0x180027cc0`
- end: `0x18002893c`
- name: `?GenerateTraceAreaEntries@TRACE_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEAVINativeConfigurationElement@@PEBG@Z`
- size: `3196`
- prototype: `int(TRACE_OBJECT_EXTENSION *__hidden this, struct IExtensionContext *, struct INativeConfigurationElement *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180025748`

## callees

- `0x180001fb0`
- `0x180002640`
- `0x180002e90`
- `0x180002ed0`
- `0x180027cc0`
- `0x18002b564`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!wcsstr` at `0x180027eb3`
- `msvcrt!wcsstr` at `0x180027f40`
- `msvcrt!wcsstr` at `0x180027f53`
- `msvcrt!wcsstr` at `0x180027f83`
- `msvcrt!wcsstr` at `0x1800284ac`
- `msvcrt!wcsstr` at `0x180027eb3`
- `msvcrt!wcsstr` at `0x180027f40`
- `msvcrt!wcsstr` at `0x180027f53`
- `msvcrt!wcsstr` at `0x180027f83`
- `msvcrt!wcsstr` at `0x1800284ac`

## pseudocode

```c
__int64 __fastcall TRACE_OBJECT_EXTENSION::GenerateTraceAreaEntries(
        TRACE_OBJECT_EXTENSION *this,
        struct IExtensionContext *a2,
        struct INativeConfigurationElement *a3,
        const unsigned __int16 *a4)
{
  __int16 *v7; // r12
  wchar_t *v8; // r13
  int v9; // ebx
  int v10; // r15d
  int v11; // r14d
  wchar_t *v12; // rax
  wchar_t *v13; // r15
  int v14; // eax
  wchar_t *v15; // r14
  wchar_t *v16; // rax
  wchar_t *v17; // rax
  const unsigned __int16 *v18; // rdx
  int v19; // eax
  const unsigned __int16 *v20; // rdx
  int v21; // eax
  unsigned int v22; // edi
  unsigned int v23; // r13d
  APP_OBJECT_UTILS *v24; // rcx
  int v25; // eax
  APP_OBJECT_UTILS *v26; // rcx
  wchar_t *v27; // rax
  wchar_t *v28; // rax
  wchar_t *v29; // rdi
  wchar_t *v30; // rdi
  int v31; // r14d
  APP_OBJECT_UTILS *v32; // rcx
  int v33; // eax
  __int16 *v34; // rdi
  int v35; // eax
  unsigned __int16 *v36; // rcx
  __int64 v37; // r8
  __int64 v38; // rax
  int v39; // eax
  struct STRU *v41; // [rsp+20h] [rbp-E0h]
  wchar_t *Str; // [rsp+40h] [rbp-C0h] BYREF
  int v43; // [rsp+48h] [rbp-B8h]
  unsigned int v44; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v45; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v46; // [rsp+58h] [rbp-A8h] BYREF
  struct ICommandParameterList *v47; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v48; // [rsp+68h] [rbp-98h] BYREF
  __int64 v49; // [rsp+70h] [rbp-90h] BYREF
  struct ICommandParameterList *v50; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v51; // [rsp+80h] [rbp-80h] BYREF
  __int64 v52; // [rsp+88h] [rbp-78h] BYREF
  __int64 v53; // [rsp+90h] [rbp-70h] BYREF
  __int64 v54; // [rsp+98h] [rbp-68h] BYREF
  __int64 v55; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v56; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v57; // [rsp+B8h] [rbp-48h] BYREF
  struct ICommandParameterList *v58; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v59; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v60; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v61; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v62; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v63; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v64; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v65; // [rsp+F8h] [rbp-8h] BYREF
  struct INativeConfigurationElement *v66; // [rsp+108h] [rbp+8h]
  _BYTE v67[32]; // [rsp+110h] [rbp+10h] BYREF
  __int16 *v68; // [rsp+130h] [rbp+30h]
  int v69; // [rsp+138h] [rbp+38h]
  __int16 v70; // [rsp+13Ch] [rbp+3Ch]
  int v71; // [rsp+140h] [rbp+40h]
  _BYTE v72[32]; // [rsp+148h] [rbp+48h] BYREF
  __int16 *v73; // [rsp+168h] [rbp+68h]
  int v74; // [rsp+170h] [rbp+70h]
  __int16 v75; // [rsp+174h] [rbp+74h]
  int v76; // [rsp+178h] [rbp+78h]
  _BYTE v77[32]; // [rsp+180h] [rbp+80h] BYREF
  wchar_t *v78; // [rsp+1A0h] [rbp+A0h]
  int v79; // [rsp+1A8h] [rbp+A8h]
  __int16 v80; // [rsp+1ACh] [rbp+ACh]
  int v81; // [rsp+1B0h] [rbp+B0h]
  __int16 v82; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v83[126]; // [rsp+1C2h] [rbp+C2h] BYREF
  __int16 v84; // [rsp+240h] [rbp+140h] BYREF
  _BYTE v85[510]; // [rsp+242h] [rbp+142h] BYREF
  __int16 v86; // [rsp+440h] [rbp+340h] BYREF
  _BYTE v87[510]; // [rsp+442h] [rbp+342h] BYREF

  v66 = a3;
  v62 = 0;
  v60 = 0;
  v61 = 0;
  v63 = 0;
  v59 = 0;
  v64 = 0;
  v55 = 0;
  v49 = 0;
  v65 = 0;
  v54 = 0;
  v53 = 0;
  v57 = 0;
  v52 = 0;
  v56 = 0;
  v48 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v51 = 0;
  memset_0(v85, 0, sizeof(v85));
  v7 = &v84;
  v75 = 256;
  v73 = &v84;
  v74 = 512;
  v76 = 0;
  v84 = 0;
  memset_0(v83, 0, sizeof(v83));
  v69 = 128;
  v68 = &v82;
  v70 = 256;
  v71 = 0;
  v82 = 0;
  v50 = 0;
  v47 = 0;
  v58 = 0;
  memset_0(v87, 0, sizeof(v87));
  v79 = 512;
  v80 = 256;
  v8 = (wchar_t *)&v86;
  v78 = (wchar_t *)&v86;
  v81 = 0;
  v86 = 0;
  Str = 0;
  if ( a4 && a2 && a3 )
  {
    v9 = (*(__int64 (__fastcall **)(struct IExtensionContext *, struct ICommandParameterList **))(*(_QWORD *)a2 + 192LL))(
           a2,
           &v50);
    if ( v9 >= 0 )
    {
      v10 = 1;
      v43 = 1;
      v11 = 1;
      v9 = (*(__int64 (__fastcall **)(struct IExtensionContext *, struct ICommandParameterList **))(*(_QWORD *)a2 + 192LL))(
             a2,
             &v58);
      if ( v9 >= 0 )
      {
        while ( a4 )
        {
          v43 = v11;
          if ( !*a4 )
            break;
          while ( *a4 == 32 )
            ++a4;
          v12 = wcsstr(a4, L"/");
          v13 = v12;
          if ( !v12 || v12 == a4 )
          {
            v9 = -2147024883;
            goto LABEL_23;
          }
          *v8 = 0;
          v81 = 0;
          v9 = STRU::Copy((STRU *)v77, a4, v12 - a4);
          if ( v9 < 0 )
            goto LABEL_23;
          v8 = v78;
          v43 = 0;
          v14 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, wchar_t *, wchar_t **))(*(_QWORD *)v50 + 40LL))(
                  v50,
                  v78,
                  &Str);
          v9 = v14;
          if ( v14 >= 0 )
          {
            v10 = 0;
            break;
          }
          if ( v14 != -2147023483 )
            goto LABEL_23;
          v15 = wcsstr(a4, L":");
          v16 = wcsstr(a4, L";");
          a4 = v16;
          if ( !v15 || v16 && v16 < v15 )
          {
            v15 = v16;
            v71 = 0;
            *v68 = 0;
          }
          else
          {
            v17 = wcsstr(v15 + 1, L";");
            v18 = v15 + 1;
            a4 = v17;
            if ( v17 )
              v19 = STRU::Copy((STRU *)v67, v18, v17 - (v15 + 1));
            else
              v19 = STRU::Copy((STRU *)v67, v18);
            v9 = v19;
            if ( v19 < 0 )
              goto LABEL_23;
          }
          v20 = v13 + 1;
          v10 = 0;
          *v7 = 0;
          v76 = 0;
          if ( v15 )
            v21 = STRU::Copy((STRU *)v72, v20, v15 - v20);
          else
            v21 = STRU::Copy((STRU *)v72, v20);
          v9 = v21;
          if ( v21 < 0 )
            goto LABEL_23;
          if ( a4 )
            ++a4;
          v7 = v73;
          v9 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, wchar_t *, __int16 *))(*(_QWORD *)v50 + 56LL))(
                 v50,
                 v8,
                 v73);
          if ( v9 < 0 )
            goto LABEL_23;
          v9 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, wchar_t *, __int16 *))(*(_QWORD *)v58 + 56LL))(
                 v58,
                 v8,
                 v68);
          if ( v9 < 0 )
            goto LABEL_23;
          v11 = 0;
        }
        v22 = 0;
        v9 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, __int64 *))(*(_QWORD *)v66 + 32LL))(
               v66,
               L"traceAreas",
               &v60);
        if ( v9 < 0 )
          goto LABEL_23;
        v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v60 + 40LL))(v60, &v56);
        if ( v9 < 0 )
          goto LABEL_23;
        v9 = (*(__int64 (__fastcall **)(struct IExtensionContext *, const wchar_t *, __int64 *))(*(_QWORD *)a2 + 80LL))(
               a2,
               &::Str,
               &v62);
        if ( v9 < 0 )
          goto LABEL_23;
        v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, __int64 *, __int64 *, _QWORD))(*(_QWORD *)v62 + 24LL))(
               v62,
               L"system.webServer/tracing/traceProviderDefinitions",
               L"MACHINE/WEBROOT/APPHOST",
               &v61,
               &v63,
               0);
        if ( v9 < 0 )
          goto LABEL_23;
        v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v61 + 40LL))(v61, &v57);
        if ( v9 < 0 )
          goto LABEL_23;
        v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v57 + 24LL))(v57, &v45);
        if ( v9 < 0 )
          goto LABEL_23;
        v23 = 0;
LABEL_74:
        if ( v23 < v45 )
        {
          v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v57 + 32LL))(v57, v23, &v49);
          if ( v9 < 0 )
            goto LABEL_23;
          v9 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, unsigned __int16 **, __int64 *, _QWORD))(*(_QWORD *)v49 + 64LL))(
                 v49,
                 L"name",
                 &v46,
                 &v55,
                 0);
          if ( v9 < 0 )
            goto LABEL_23;
          if ( v43 )
          {
            if ( !v71 )
            {
              v9 = STRU::Copy((STRU *)v67, L"Verbose");
              if ( v9 < 0 )
                goto LABEL_23;
            }
          }
          else
          {
            v25 = APP_OBJECT_UTILS::PopParameter(v24, a2, v50, v46, (struct STRU *)v77, 0, 1);
            v9 = v25;
            if ( v25 == -2147023483 )
            {
              v46 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
              v49 = 0;
              goto LABEL_123;
            }
            if ( v25 < 0 )
              goto LABEL_23;
            v9 = APP_OBJECT_UTILS::PopParameter(v26, a2, v58, v46, (struct STRU *)v67, 0, 1);
            if ( v9 < 0 )
              goto LABEL_23;
            Str = v78;
            v9 = (*(__int64 (__fastcall **)(struct IExtensionContext *, struct ICommandParameterList **))(*(_QWORD *)a2 + 192LL))(
                   a2,
                   &v47);
            if ( v9 < 0 )
              goto LABEL_23;
            v10 = 1;
            while ( 1 )
            {
              v27 = Str;
              if ( !Str || !*Str )
                break;
              v10 = 0;
              if ( *Str == 32 )
              {
                do
                  Str = ++v27;
                while ( *v27 == 32 );
                if ( !*v27 )
                  break;
              }
              *v7 = 0;
              v76 = 0;
              v28 = wcsstr(Str, L",");
              v29 = v28;
              if ( v28 )
              {
                v9 = STRU::Copy((STRU *)v72, Str, v28 - Str);
                if ( v9 < 0 )
                  goto LABEL_23;
                v30 = v29 + 1;
              }
              else
              {
                v30 = 0;
                v9 = STRU::Copy((STRU *)v72, Str);
                if ( v9 < 0 )
                  goto LABEL_23;
              }
              v7 = v73;
              Str = v30;
              v22 = 0;
              v9 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, __int16 *, const wchar_t *))(*(_QWORD *)v47 + 56LL))(
                     v47,
                     v73,
                     &::Str);
              if ( v9 < 0 )
                goto LABEL_23;
            }
          }
          v9 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64 *))(*(_QWORD *)v49 + 32LL))(
                 v49,
                 L"areas",
                 &v54);
          if ( v9 < 0 )
            goto LABEL_23;
          v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v54 + 40LL))(v54, &v52);
          if ( v9 < 0 )
            goto LABEL_23;
          v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v52 + 24LL))(v52, &v44);
          if ( v9 < 0 )
            goto LABEL_23;
          *v7 = 0;
          v31 = 0;
          v76 = 0;
          while ( 1 )
          {
            if ( v22 >= v44 )
            {
              if ( !v10 )
              {
                (*(void (__fastcall **)(struct ICommandParameterList *, unsigned int *))(*(_QWORD *)v47 + 24LL))(
                  v47,
                  &v44);
                if ( v44 )
                {
                  v35 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, _QWORD, unsigned __int16 **, wchar_t **))(*(_QWORD *)v47 + 32LL))(
                          v47,
                          0,
                          &v51,
                          &Str);
                  v36 = (unsigned __int16 *)&::Str;
                  v37 = 3221226530LL;
                  if ( v35 >= 0 )
                    v36 = v51;
                  *((_QWORD *)&v65 + 1) = v46;
LABEL_127:
                  v38 = *(_QWORD *)a2;
                  *(_QWORD *)&v65 = v36;
                  v9 = -2147023483;
                  LODWORD(v41) = 0;
                  (*(void (__fastcall **)(struct IExtensionContext *, __int64, __int64, __int128 *, struct STRU *))(v38 + 144))(
                    a2,
                    2147943813LL,
                    v37,
                    &v65,
                    v41);
                  goto LABEL_23;
                }
              }
              v9 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64 *))(*(_QWORD *)v56 + 48LL))(
                     v56,
                     L"add",
                     &v48);
              if ( v9 < 0 )
                goto LABEL_23;
              v9 = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64, const wchar_t *, unsigned __int16 *))(*(_QWORD *)a2 + 96LL))(
                     a2,
                     v48,
                     L"provider",
                     v46);
              if ( v9 < 0 )
                goto LABEL_23;
              v7 = v73;
              v9 = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64, const unsigned __int16 *, __int16 *))(*(_QWORD *)a2 + 96LL))(
                     a2,
                     v48,
                     L"areas",
                     v73);
              if ( v9 < 0 )
                goto LABEL_23;
              v34 = v68;
              if ( v71 )
              {
                v9 = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64, const unsigned __int16 *, __int16 *))(*(_QWORD *)a2 + 96LL))(
                       a2,
                       v48,
                       L"verbosity",
                       v68);
                if ( v9 < 0 )
                  goto LABEL_23;
              }
              v9 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)v56 + 56LL))(
                     v56,
                     v48,
                     0xFFFFFFFFLL,
                     &v59);
              if ( v9 < 0 )
                goto LABEL_23;
              if ( v47 )
              {
                (*(void (__fastcall **)(struct ICommandParameterList *))(*(_QWORD *)v47 + 16LL))(v47);
                v47 = 0;
              }
              v46 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
              v52 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
              v54 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
              v49 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
              v48 = 0;
              *v34 = 0;
              v22 = 0;
              v71 = 0;
LABEL_123:
              ++v23;
              goto LABEL_74;
            }
            v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v52 + 32LL))(v52, v22, &v53);
            if ( v9 < 0 )
              goto LABEL_23;
            v9 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, unsigned __int16 **, __int64 *, _QWORD))(*(_QWORD *)v53 + 64LL))(
                   v53,
                   L"name",
                   &v51,
                   &v55,
                   0);
            if ( v9 < 0 )
              goto LABEL_23;
            if ( !v10 )
            {
              v33 = APP_OBJECT_UTILS::PopParameter(v32, a2, v47, v51, (struct STRU *)v77, 0, 1);
              v9 = v33;
              if ( v33 == -2147023483 )
                goto LABEL_111;
              if ( v33 < 0 )
                goto LABEL_23;
            }
            if ( v31 )
            {
              v9 = STRU::Append((STRU *)v72, L",");
              if ( v9 < 0 )
                goto LABEL_23;
            }
            v9 = STRU::Append((STRU *)v72, v51);
            if ( v9 < 0 )
              goto LABEL_23;
            ++v31;
LABEL_111:
            v51 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
            ++v22;
            v53 = 0;
          }
        }
        v9 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, unsigned int *))(*(_QWORD *)v50 + 24LL))(
               v50,
               &v45);
        if ( v45 )
        {
          v39 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, _QWORD, unsigned __int16 **, wchar_t **))(*(_QWORD *)v50 + 32LL))(
                  v50,
                  0,
                  &v46,
                  &Str);
          v36 = (unsigned __int16 *)&::Str;
          v37 = 3221226529LL;
          if ( v39 >= 0 )
            v36 = v46;
          goto LABEL_127;
        }
      }
    }
LABEL_23:
    if ( v55 )
    {
      (*(void (__fastcall **)(struct IExtensionContext *, _QWORD, const wchar_t *))(*(_QWORD *)a2 + 120LL))(
        a2,
        (unsigned int)v9,
        &::Str);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
      v55 = 0;
    }
    if ( v59 )
    {
      (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v59 + 24LL))(v59, &v64);
      (*(void (__fastcall **)(struct IExtensionContext *, _QWORD, __int64, _QWORD))(*(_QWORD *)a2 + 128LL))(
        a2,
        (unsigned int)v9,
        v64,
        0);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
      v59 = 0;
    }
    if ( v47 )
    {
      (*(void (__fastcall **)(struct ICommandParameterList *))(*(_QWORD *)v47 + 16LL))(v47);
      v47 = 0;
    }
    if ( v56 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
      v56 = 0;
    }
    if ( v48 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
      v48 = 0;
    }
    if ( v60 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
      v60 = 0;
    }
    if ( v61 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
      v61 = 0;
    }
    if ( v57 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
      v57 = 0;
    }
    if ( v52 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
      v52 = 0;
    }
    if ( v54 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
      v54 = 0;
    }
    if ( v49 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
      v49 = 0;
    }
    if ( v53 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
      v53 = 0;
    }
    if ( v63 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
      v63 = 0;
    }
    if ( v50 )
    {
      (*(void (__fastcall **)(struct ICommandParameterList *))(*(_QWORD *)v50 + 16LL))(v50);
      v50 = 0;
    }
    if ( v58 )
    {
      (*(void (__fastcall **)(struct ICommandParameterList *))(*(_QWORD *)v58 + 16LL))(v58);
      v58 = 0;
    }
    if ( v62 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
      v62 = 0;
    }
  }
  else
  {
    v9 = -2147024809;
  }
  BUFFER::~BUFFER((BUFFER *)v77);
  BUFFER::~BUFFER((BUFFER *)v67);
  BUFFER::~BUFFER((BUFFER *)v72);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180027cc0  mov     [rsp-8+arg_0], rbx
0x180027cc5  push    rbp
0x180027cc6  push    rsi
0x180027cc7  push    rdi
0x180027cc8  push    r12
0x180027cca  push    r13
0x180027ccc  push    r14
0x180027cce  push    r15
0x180027cd0  lea     rbp, [rsp-550h]
0x180027cd8  sub     rsp, 650h
0x180027cdf  mov     rax, cs:__security_cookie
0x180027ce6  xor     rax, rsp
0x180027ce9  mov     [rbp+580h+var_40], rax
0x180027cf0  xor     r13d, r13d
0x180027cf3  mov     [rbp+580h+var_578], r8
0x180027cf7  mov     r14, r8
0x180027cfa  mov     [rbp+580h+var_5A0], r13
0x180027cfe  mov     rsi, rdx
0x180027d01  mov     [rbp+580h+var_5B0], r13
0x180027d05  xorps   xmm0, xmm0
0x180027d08  mov     [rbp+580h+var_5A8], r13
0x180027d0c  mov     r15d, 1FEh
0x180027d12  mov     [rbp+580h+var_598], r13
0x180027d16  mov     r8d, r15d; Size
0x180027d19  mov     [rbp+580h+var_5B8], r13
0x180027d1d  xor     edx, edx; Val
0x180027d1f  mov     [rbp+580h+var_590], r13
0x180027d23  lea     rcx, [rbp+580h+var_43E]; void *
0x180027d2a  mov     [rbp+580h+var_5D8], r13
0x180027d2e  mov     rdi, r9
0x180027d31  mov     [rsp+680h+var_610], r13
0x180027d36  movups  [rbp+580h+var_588], xmm0
0x180027d3a  mov     [rbp+580h+var_5E8], r13
0x180027d3e  mov     [rbp+580h+var_5F0], r13
0x180027d42  mov     [rbp+580h+var_5C8], r13
0x180027d46  mov     [rbp+580h+var_5F8], r13
0x180027d4a  mov     [rbp+580h+var_5D0], r13
0x180027d4e  mov     [rsp+680h+var_618], r13
0x180027d53  mov     [rsp+680h+var_634], r13d
0x180027d58  mov     [rsp+680h+var_630], r13d
0x180027d5d  mov     [rsp+680h+var_628], r13
0x180027d62  mov     [rbp+580h+var_600], r13
0x180027d66  call    memset_0
0x180027d6b  lea     r12, [rbp+580h+var_440]
0x180027d72  mov     [rbp+580h+var_50C], 100h
0x180027d78  lea     ebx, [r15+2]
0x180027d7c  mov     [rbp+580h+var_518], r12
0x180027d80  xor     edx, edx; Val
0x180027d82  mov     [rbp+580h+var_510], ebx
0x180027d85  lea     r8d, [r13+7Eh]; Size
0x180027d89  mov     [rbp+580h+var_508], r13d
0x180027d8d  lea     rcx, [rbp+580h+var_4BE]; void *
0x180027d94  mov     [rbp+580h+var_440], r13w
0x180027d9c  call    memset_0
0x180027da1  lea     rax, [rbp+580h+var_4C0]
0x180027da8  mov     [rbp+580h+var_548], 80h
0x180027daf  mov     r8d, r15d; Size
0x180027db2  mov     [rbp+580h+var_550], rax
0x180027db6  xor     edx, edx; Val
0x180027db8  mov     [rbp+580h+var_544], 100h
0x180027dbe  lea     rcx, [rbp+580h+var_23E]; void *
0x180027dc5  mov     [rbp+580h+var_540], r13d
0x180027dc9  mov     [rbp+580h+var_4C0], r13w
0x180027dd1  mov     [rsp+680h+var_608], r13
0x180027dd6  mov     [rsp+680h+var_620], r13
0x180027ddb  mov     [rbp+580h+var_5C0], r13
0x180027ddf  call    memset_0
0x180027de4  xor     r15d, r15d
0x180027de7  mov     [rbp+580h+var_4D8], ebx
0x180027ded  mov     [rbp+580h+var_4D4], 100h
0x180027df6  lea     r13, [rbp+580h+var_240]
0x180027dfd  mov     [rbp+580h+var_4E0], r13
0x180027e04  mov     [rbp+580h+var_4D0], r15d
0x180027e0b  mov     [rbp+580h+var_240], r15w
0x180027e13  mov     [rsp+680h+Str], r15
0x180027e18  test    rdi, rdi
0x180027e1b  jz      loc_1800288ED
0x180027e21  test    rsi, rsi
0x180027e24  jz      loc_1800288ED
0x180027e2a  test    r14, r14
0x180027e2d  jz      loc_1800288ED
0x180027e33  mov     rax, [rsi]
0x180027e36  lea     rdx, [rsp+680h+var_608]
0x180027e3b  mov     rcx, rsi
0x180027e3e  mov     rax, [rax+0C0h]
0x180027e45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e4a  mov     ebx, eax
0x180027e4c  test    eax, eax
0x180027e4e  js      loc_180027FB7
0x180027e54  lea     eax, [r15+1]
0x180027e58  mov     rcx, rsi
0x180027e5b  mov     r15d, eax
0x180027e5e  mov     [rsp+680h+var_638], eax
0x180027e62  mov     r14d, eax
0x180027e65  lea     rdx, [rbp+580h+var_5C0]
0x180027e69  mov     rax, [rsi]
0x180027e6c  mov     rax, [rax+0C0h]
0x180027e73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e78  mov     ebx, eax
0x180027e7a  test    eax, eax
0x180027e7c  js      loc_180027FB7
0x180027e82  test    rdi, rdi
0x180027e85  jz      loc_180028252
0x180027e8b  mov     [rsp+680h+var_638], r14d
0x180027e90  xor     r14d, r14d
0x180027e93  cmp     [rdi], r14w
0x180027e97  jz      loc_180028252
0x180027e9d  jmp     short loc_180027EA3
0x180027e9f  add     rdi, 2
0x180027ea3  cmp     word ptr [rdi], 20h ; ' '
0x180027ea7  jz      short loc_180027E9F
0x180027ea9  lea     rdx, SubStr; "/"
0x180027eb0  mov     rcx, rdi; Str
0x180027eb3  call    cs:__imp_wcsstr
0x180027eb9  mov     r15, rax
0x180027ebc  test    rax, rax
0x180027ebf  jz      loc_180028245
0x180027ec5  cmp     rax, rdi
0x180027ec8  jz      loc_180028245
0x180027ece  mov     r8, rax
0x180027ed1  mov     [r13+0], r14w
0x180027ed6  sub     r8, rdi
0x180027ed9  mov     [rbp+580h+var_4D0], r14d
0x180027ee0  sar     r8, 1; unsigned int
0x180027ee3  lea     rcx, [rbp+580h+var_500]; this
0x180027eea  mov     rdx, rdi; unsigned __int16 *
0x180027eed  call    ?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180027ef2  mov     ebx, eax
0x180027ef4  test    eax, eax
0x180027ef6  js      loc_180027FB7
0x180027efc  mov     rcx, [rsp+680h+var_608]
0x180027f01  lea     r8, [rsp+680h+Str]
0x180027f06  mov     r13, [rbp+580h+var_4E0]
0x180027f0d  mov     rdx, r13
0x180027f10  mov     [rsp+680h+var_638], r14d
0x180027f15  mov     rax, [rcx]
0x180027f18  mov     rax, [rax+28h]
0x180027f1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027f21  mov     ebx, eax
0x180027f23  test    eax, eax
0x180027f25  jns     loc_18002824F
0x180027f2b  cmp     eax, 80070585h
0x180027f30  jnz     loc_180027FB7
0x180027f36  lea     rdx, asc_18003A620; ":"
0x180027f3d  mov     rcx, rdi; Str
0x180027f40  call    cs:__imp_wcsstr
0x180027f46  lea     rdx, asc_18004E348; ";"
0x180027f4d  mov     rcx, rdi; Str
0x180027f50  mov     r14, rax
0x180027f53  call    cs:__imp_wcsstr
0x180027f59  xor     edx, edx
0x180027f5b  mov     rdi, rax
0x180027f5e  test    r14, r14
0x180027f61  jz      loc_1800281A9
0x180027f67  test    rax, rax
0x180027f6a  jz      short loc_180027F75
0x180027f6c  cmp     rax, r14
0x180027f6f  jb      loc_1800281A9
0x180027f75  lea     rbx, [r14+2]
0x180027f79  mov     rcx, rbx; Str
0x180027f7c  lea     rdx, asc_18004E348; ";"
0x180027f83  call    cs:__imp_wcsstr
0x180027f89  mov     rdx, rbx; unsigned __int16 *
0x180027f8c  lea     rcx, [rbp+580h+var_570]; this
0x180027f90  mov     rdi, rax
0x180027f93  test    rax, rax
0x180027f96  jz      short loc_180027FA8
0x180027f98  mov     r8, rax
0x180027f9b  sub     r8, rbx
0x180027f9e  sar     r8, 1; unsigned int
0x180027fa1  call    ?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180027fa6  jmp     short loc_180027FAD
0x180027fa8  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180027fad  mov     ebx, eax
0x180027faf  test    eax, eax
0x180027fb1  jns     loc_1800281B6
0x180027fb7  xor     edi, edi
0x180027fb9  mov     r9, [rbp+580h+var_5D8]
0x180027fbd  test    r9, r9
0x180027fc0  jz      short loc_180027FF2
0x180027fc2  mov     rax, [rsi]
0x180027fc5  lea     r8, Str
0x180027fcc  mov     edx, ebx
0x180027fce  mov     dword ptr [rsp+680h+var_660], edi
0x180027fd2  mov     rcx, rsi
0x180027fd5  mov     rax, [rax+78h]
0x180027fd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027fde  mov     rcx, [rbp+580h+var_5D8]
0x180027fe2  mov     rax, [rcx]
0x180027fe5  mov     rax, [rax+10h]
0x180027fe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027fee  mov     [rbp+580h+var_5D8], rdi
0x180027ff2  mov     rcx, [rbp+580h+var_5B8]
0x180027ff6  test    rcx, rcx
0x180027ff9  jz      short loc_18002803A
0x180027ffb  mov     rax, [rcx]
0x180027ffe  lea     rdx, [rbp+580h+var_590]
0x180028002  mov     rax, [rax+18h]
0x180028006  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002800b  mov     rax, [rsi]
0x18002800e  xor     r9d, r9d
0x180028011  mov     r8, [rbp+580h+var_590]
0x180028015  mov     edx, ebx
0x180028017  mov     rcx, rsi
0x18002801a  mov     rax, [rax+80h]
0x180028021  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028026  mov     rcx, [rbp+580h+var_5B8]
0x18002802a  mov     rax, [rcx]
0x18002802d  mov     rax, [rax+10h]
0x180028031  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028036  mov     [rbp+580h+var_5B8], rdi
0x18002803a  mov     rcx, [rsp+680h+var_620]
0x18002803f  test    rcx, rcx
0x180028042  jz      short loc_180028055
0x180028044  mov     rax, [rcx]
0x180028047  mov     rax, [rax+10h]
0x18002804b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028050  mov     [rsp+680h+var_620], rdi
0x180028055  mov     rcx, [rbp+580h+var_5D0]
0x180028059  test    rcx, rcx
0x18002805c  jz      short loc_18002806E
0x18002805e  mov     rax, [rcx]
0x180028061  mov     rax, [rax+10h]
0x180028065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002806a  mov     [rbp+580h+var_5D0], rdi
0x18002806e  mov     rcx, [rsp+680h+var_618]
0x180028073  test    rcx, rcx
0x180028076  jz      short loc_180028089
0x180028078  mov     rax, [rcx]
0x18002807b  mov     rax, [rax+10h]
0x18002807f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028084  mov     [rsp+680h+var_618], rdi
0x180028089  mov     rcx, [rbp+580h+var_5B0]
0x18002808d  test    rcx, rcx
0x180028090  jz      short loc_1800280A2
0x180028092  mov     rax, [rcx]
0x180028095  mov     rax, [rax+10h]
0x180028099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002809e  mov     [rbp+580h+var_5B0], rdi
0x1800280a2  mov     rcx, [rbp+580h+var_5A8]
0x1800280a6  test    rcx, rcx
0x1800280a9  jz      short loc_1800280BB
0x1800280ab  mov     rax, [rcx]
0x1800280ae  mov     rax, [rax+10h]
0x1800280b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800280b7  mov     [rbp+580h+var_5A8], rdi
0x1800280bb  mov     rcx, [rbp+580h+var_5C8]
0x1800280bf  test    rcx, rcx
0x1800280c2  jz      short loc_1800280D4
0x1800280c4  mov     rax, [rcx]
0x1800280c7  mov     rax, [rax+10h]
0x1800280cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800280d0  mov     [rbp+580h+var_5C8], rdi
0x1800280d4  mov     rcx, [rbp+580h+var_5F8]
0x1800280d8  test    rcx, rcx
0x1800280db  jz      short loc_1800280ED
0x1800280dd  mov     rax, [rcx]
0x1800280e0  mov     rax, [rax+10h]
0x1800280e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800280e9  mov     [rbp+580h+var_5F8], rdi
0x1800280ed  mov     rcx, [rbp+580h+var_5E8]
0x1800280f1  test    rcx, rcx
0x1800280f4  jz      short loc_180028106
0x1800280f6  mov     rax, [rcx]
0x1800280f9  mov     rax, [rax+10h]
0x1800280fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028102  mov     [rbp+580h+var_5E8], rdi
0x180028106  mov     rcx, [rsp+680h+var_610]
0x18002810b  test    rcx, rcx
0x18002810e  jz      short loc_180028121
0x180028110  mov     rax, [rcx]
0x180028113  mov     rax, [rax+10h]
0x180028117  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002811c  mov     [rsp+680h+var_610], rdi
0x180028121  mov     rcx, [rbp+580h+var_5F0]
0x180028125  test    rcx, rcx
0x180028128  jz      short loc_18002813A
0x18002812a  mov     rax, [rcx]
0x18002812d  mov     rax, [rax+10h]
0x180028131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028136  mov     [rbp+580h+var_5F0], rdi
0x18002813a  mov     rcx, [rbp+580h+var_598]
0x18002813e  test    rcx, rcx
0x180028141  jz      short loc_180028153
0x180028143  mov     rax, [rcx]
0x180028146  mov     rax, [rax+10h]
0x18002814a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002814f  mov     [rbp+580h+var_598], rdi
0x180028153  mov     rcx, [rsp+680h+var_608]
0x180028158  test    rcx, rcx
0x18002815b  jz      short loc_18002816E
0x18002815d  mov     rax, [rcx]
0x180028160  mov     rax, [rax+10h]
0x180028164  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028169  mov     [rsp+680h+var_608], rdi
0x18002816e  mov     rcx, [rbp+580h+var_5C0]
0x180028172  test    rcx, rcx
0x180028175  jz      short loc_180028187
0x180028177  mov     rax, [rcx]
0x18002817a  mov     rax, [rax+10h]
  ... truncated ...
```
