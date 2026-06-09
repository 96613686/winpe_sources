# IISCERTMAP_SITE_META_STORED_CONTEXT::Initialize(IHttpContext *,INativeSectionException * *)

- ea: `0x1800041f0`
- end: `0x180004e29`
- name: `?Initialize@IISCERTMAP_SITE_META_STORED_CONTEXT@@QEAAJPEAVIHttpContext@@PEAPEAVINativeSectionException@@@Z`
- size: `3129`
- prototype: `__int64 __fastcall(IISCERTMAP_SITE_META_STORED_CONTEXT *__hidden this, struct IHttpContext *, struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180003260`

## callees

- `0x180001008`
- `0x180001048`
- `0x180001af8`
- `0x18000357c`
- `0x1800036b0`
- `0x180003d94`
- `0x1800041f0`
- `0x180006d92`
- `0x180006dd0`
- `0x180008010`

## import_xrefs

- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800042b1`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180004849`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180004860`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180004a75`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180004a8c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180004c9f`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800042b1`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180004849`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180004860`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180004a75`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180004a8c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180004c9f`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180004c88`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180004c88`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800045c7`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800045c7`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800042c6`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004408`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004ac5`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004ae2`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800042c6`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004408`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004ac5`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004ae2`
- `iisutil!EncryptMemoryPassword` at `0x180004af5`
- `iisutil!EncryptMemoryPassword` at `0x180004af5`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180004895`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180004895`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800042fd`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800042fd`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800045bd`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000460f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004de9`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800045bd`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000460f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004de9`

## string_xrefs

- `0x180004353`: `system.webServer/security/authentication/iisClientCertificateMappingAuthentication`
- `0x180004c47`: `compareCaseSensitive`

## pseudocode

```c
__int64 __fastcall IISCERTMAP_SITE_META_STORED_CONTEXT::Initialize(
        IISCERTMAP_SITE_META_STORED_CONTEXT *this,
        struct IHttpContext *a2,
        struct INativeSectionException **a3)
{
  unsigned __int16 *v6; // r14
  unsigned __int16 *v7; // rsi
  unsigned __int16 *v8; // rdi
  signed int v9; // ebx
  __int64 v10; // rax
  const unsigned __int16 *v11; // rax
  __int64 (__fastcall ***v12)(_QWORD, GUID *, __int64 *); // rax
  int v14; // eax
  __int64 v15; // rcx
  unsigned int i; // r15d
  unsigned __int16 *v17; // rax
  int inserted; // eax
  unsigned int v19; // r12d
  unsigned __int16 *v20; // rax
  unsigned __int16 *v21; // r14
  BOOL v22; // r15d
  unsigned int v23; // edi
  char *v24; // rax
  unsigned __int16 **v25; // rcx
  IISCERTMAP_SITE_META_STORED_CONTEXT **v26; // rcx
  __int64 v27; // rcx
  int v28; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v29; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v30; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v31; // [rsp+50h] [rbp-B0h] BYREF
  int v32; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v33; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v34; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v35; // [rsp+70h] [rbp-90h] BYREF
  __int64 v36; // [rsp+78h] [rbp-88h] BYREF
  __int64 v37; // [rsp+80h] [rbp-80h] BYREF
  __int64 v38; // [rsp+88h] [rbp-78h] BYREF
  __int64 v39; // [rsp+90h] [rbp-70h] BYREF
  __int64 v40; // [rsp+98h] [rbp-68h] BYREF
  __int64 v41; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v42; // [rsp+A8h] [rbp-58h] BYREF
  int v43; // [rsp+B0h] [rbp-50h] BYREF
  int v44; // [rsp+B4h] [rbp-4Ch] BYREF
  unsigned int v45; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v46; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v47; // [rsp+C8h] [rbp-38h] BYREF
  const unsigned __int16 *v48; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 *v49; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v50; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v51; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v52[32]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v53; // [rsp+110h] [rbp+10h]
  unsigned __int16 v54[64]; // [rsp+130h] [rbp+30h] BYREF

  v44 = 1;
  v42 = 0;
  v30 = 0;
  v38 = 0;
  v36 = 0;
  v37 = 0;
  v34 = 0;
  v31 = 0;
  v6 = 0;
  v33 = 0;
  v7 = 0;
  v39 = 0;
  v8 = 0;
  v41 = 0;
  v40 = 0;
  v29 = 0;
  v35 = 0;
  v45 = 0;
  v51 = 0;
  v50 = 0;
  v32 = 0;
  v47 = 0;
  v46 = 0;
  v43 = 0;
  v49 = 0;
  v48 = 0;
  memset_0(v54, 0, sizeof(v54));
  STRU::STRU((STRU *)v52, v54, 0x40u);
  v28 = 0;
  v9 = STRU::Copy((STRU *)v52, L"MACHINE/WEBROOT/APPHOST/");
  if ( v9 < 0 )
    goto LABEL_15;
  v10 = (**(__int64 (__fastcall ***)(struct IHttpContext *))a2)(a2);
  v11 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
  v9 = STRU::Append((STRU *)v52, v11);
  if ( v9 < 0 )
    goto LABEL_15;
  v12 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)s_pGlobalInfo + 56LL))(s_pGlobalInfo);
  v9 = (**v12)(v12, &IID_INativeConfigurationSystem, &v42);
  if ( v9 < 0 )
    goto LABEL_15;
  v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, __int64 *, struct INativeSectionException **, _QWORD))(*(_QWORD *)v42 + 24LL))(
         v42,
         L"system.webServer/security/authentication/iisClientCertificateMappingAuthentication",
         v53,
         &v30,
         a3,
         0);
  if ( v9 < 0 )
    goto LABEL_15;
  v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v30 + 72LL))(
         v30,
         L"oneToOneCertificateMappingsEnabled",
         (char *)this + 8,
         0,
         0);
  if ( v9 < 0 )
    goto LABEL_15;
  v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v30 + 72LL))(
         v30,
         L"manyToOneCertificateMappingsEnabled",
         (char *)this + 12,
         0,
         0);
  if ( v9 < 0 )
    goto LABEL_15;
  v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v30 + 64LL))(
         v30,
         L"defaultLogonDomain",
         &v48,
         0,
         0);
  if ( v9 < 0 )
    goto LABEL_15;
  v9 = STRU::Copy((IISCERTMAP_SITE_META_STORED_CONTEXT *)((char *)this + 16), v48);
  if ( v9 < 0 )
    goto LABEL_15;
  v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v30 + 48LL))(
         v30,
         L"logonMethod",
         &v28,
         0,
         0);
  if ( v9 < 0 )
    goto LABEL_15;
  switch ( v28 )
  {
    case 0:
      v14 = 2;
LABEL_49:
      v15 = v30;
      v28 = v14;
      *((_DWORD *)this + 18) = v14;
      v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v15 + 32LL))(
             v15,
             L"oneToOneMappings",
             &v41);
      if ( v9 < 0 )
        goto LABEL_15;
      v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v41 + 40LL))(v41, &v38);
      if ( v9 < 0 )
        goto LABEL_15;
      v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v30 + 32LL))(
             v30,
             L"manyToOneMappings",
             &v39);
      if ( v9 < 0 )
        goto LABEL_15;
      v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v39 + 40LL))(v39, &v36);
      if ( v9 < 0 )
        goto LABEL_15;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
      v30 = 0;
      if ( *((_DWORD *)this + 2) )
      {
        v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v38 + 24LL))(v38, &v29);
        if ( v9 < 0 )
          goto LABEL_15;
        for ( i = 0; i < v29; v34 = 0 )
        {
          v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v38 + 32LL))(v38, i, &v34);
          if ( v9 < 0 )
            goto LABEL_102;
          v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v34 + 72LL))(
                 v34,
                 L"enabled",
                 &v32,
                 0,
                 0);
          if ( v9 < 0 )
            goto LABEL_102;
          if ( v32 )
          {
            v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v34 + 64LL))(
                   v34,
                   L"userName",
                   &v47,
                   0,
                   0);
            if ( v9 < 0 )
              goto LABEL_102;
            v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v34 + 64LL))(
                   v34,
                   L"password",
                   &v46,
                   0,
                   0);
            if ( v9 < 0 )
              goto LABEL_102;
            v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v34 + 64LL))(
                   v34,
                   L"certificate",
                   &v49,
                   0,
                   0);
            if ( v9 < 0 )
              goto LABEL_102;
            v17 = (unsigned __int16 *)operator new(0x118u);
            v8 = v17;
            if ( !v17 )
            {
              v9 = -2147024882;
              goto LABEL_102;
            }
            *(_DWORD *)v17 = 1;
            STRU::STRU((STRU *)(v17 + 4), v17 + 32, 0x20u);
            STRU::STRU((STRU *)(v8 + 64), v8 + 92, 0x20u);
            *((_QWORD *)v8 + 34) = 0;
            v9 = CERT_1TO1_MAP_RULE::InitializeInstance((CERT_1TO1_MAP_RULE *)v8, v49, v47, v46);
            if ( v9 < 0 )
              goto LABEL_15;
            inserted = CLKRHashTable::InsertRecord((char *)this + 80, v8, 0);
            v9 = inserted;
            if ( (unsigned int)inserted > 1 )
            {
              if ( inserted > 0 )
                v9 = (unsigned __int16)inserted | 0x80070000;
              if ( v9 < 0 )
                goto LABEL_15;
            }
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8, 0xFFFFFFFF) == 1 )
            {
              CERT_1TO1_MAP_RULE::~CERT_1TO1_MAP_RULE((CERT_1TO1_MAP_RULE *)v8);
              operator delete(v8);
            }
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
          ++i;
        }
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
      v38 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
      v41 = 0;
      if ( *((_DWORD *)this + 3) )
      {
        v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v36 + 24LL))(v36, &v29);
        if ( v9 < 0 )
        {
LABEL_102:
          v8 = 0;
          goto LABEL_15;
        }
        v19 = 0;
        if ( v29 )
        {
          while ( 1 )
          {
            v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v36 + 32LL))(v36, v19, &v31);
            if ( v9 < 0 )
              break;
            v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v31 + 72LL))(
                   v31,
                   L"enabled",
                   &v32,
                   0,
                   0);
            if ( v9 < 0 )
              break;
            if ( v32 )
            {
              v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v31 + 64LL))(
                     v31,
                     L"userName",
                     &v47,
                     0,
                     0);
              if ( v9 < 0 )
                break;
              v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v31 + 64LL))(
                     v31,
                     L"password",
                     &v46,
                     0,
                     0);
              if ( v9 < 0 )
                break;
              v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v31 + 48LL))(
                     v31,
                     L"permissionMode",
                     &v43,
                     0,
                     0);
              if ( v9 < 0 )
                break;
              v20 = (unsigned __int16 *)operator new(0x118u);
              v7 = v20;
              if ( !v20 )
              {
                v9 = -2147024882;
                break;
              }
              STRU::STRU((STRU *)(v20 + 8), v20 + 36, 0x20u);
              STRU::STRU((STRU *)(v7 + 68), v7 + 96, 0x20u);
              *((_QWORD *)v7 + 32) = 0;
              *((_QWORD *)v7 + 34) = v7 + 132;
              *((_QWORD *)v7 + 33) = v7 + 132;
              v21 = v46;
              v22 = v43 == 2;
              v9 = STRU::Copy((STRU *)(v7 + 8), v47);
              if ( v9 < 0 )
                goto LABEL_104;
              v9 = STRU::Copy((STRU *)(v7 + 68), v21);
              if ( v9 < 0 )
                goto LABEL_104;
              v9 = EncryptMemoryPassword((struct STRU *)(v7 + 68));
              if ( v9 < 0 )
                goto LABEL_104;
              *((_DWORD *)v7 + 64) = v22;
              v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v31 + 32LL))(
                     v31,
                     L"rules",
                     &v40);
              if ( v9 < 0 )
                goto LABEL_104;
              v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v40 + 40LL))(v40, &v37);
              if ( v9 < 0 )
                goto LABEL_104;
              v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v37 + 24LL))(v37, &v35);
              if ( v9 < 0 )
                goto LABEL_104;
              v23 = 0;
              if ( v35 )
              {
                while ( 1 )
                {
                  v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v37 + 32LL))(v37, v23, &v33);
                  if ( v9 < 0 )
                    break;
                  v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned int *, _QWORD, _QWORD))(*(_QWORD *)v33 + 48LL))(
                         v33,
                         L"certificateField",
                         &v45,
                         0,
                         0);
                  if ( v9 < 0 )
                    break;
                  v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *, _QWORD, _QWORD))(*(_QWORD *)v33 + 64LL))(
                         v33,
                         L"certificateSubField",
                         &v51,
                         0,
                         0);
                  if ( v9 < 0 )
                    break;
                  v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *, _QWORD, _QWORD))(*(_QWORD *)v33 + 64LL))(
                         v33,
                         L"matchCriteria",
                         &v50,
                         0,
                         0);
                  if ( v9 < 0 )
                    break;
                  v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v33 + 72LL))(
                         v33,
                         L"compareCaseSensitive",
                         &v44,
                         0,
                         0);
                  if ( v9 < 0 )
                    break;
                  v24 = (char *)operator new(0xE0u);
                  v6 = (unsigned __int16 *)v24;
                  if ( !v24 )
                  {
                    v9 = -2147024882;
                    break;
                  }
                  STRA::STRA((STRA *)(v24 + 24), v24 + 80, 0x10u);
                  STRU::STRU((STRU *)(v6 + 48), v6 + 76, 0x20u);
                  v9 = CERT_MAP_RULE_ELEMENT::InitializeInstance(v6, v45, v51, v50, v44);
                  if ( v9 < 0 )
                    goto LABEL_102;
                  ++*((_DWORD *)v7 + 65);
                  v25 = (unsigned __int16 **)*((_QWORD *)v7 + 34);
                  if ( *v25 != v7 + 132 )
                    goto LABEL_105;
                  *(_QWORD *)v6 = v7 + 132;
                  *((_QWORD *)v6 + 1) = v25;
                  *v25 = v6;
                  *((_QWORD *)v7 + 34) = v6;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
                  ++v23;
                  v33 = 0;
                  if ( v23 >= v35 )
                    goto LABEL_97;
                }
LABEL_104:
                v8 = 0;
                v6 = 0;
                goto LABEL_15;
              }
LABEL_97:
              ++*((_DWORD *)this + 38);
              v26 = (IISCERTMAP_SITE_META_STORED_CONTEXT **)*((_QWORD *)this + 21);
              if ( *v26 != (IISCERTMAP_SITE_META_STORED_CONTEXT *)((char *)this + 160) )
LABEL_105:
                __fastfail(3u);
              *(_QWORD *)v7 = (char *)this + 160;
              *((_QWORD *)v7 + 1) = v26;
              *v26 = (IISCERTMAP_SITE_META_STORED_CONTEXT *)v7;
              v27 = v37;
              *((_QWORD *)this + 21) = v7;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
              v37 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
              v40 = 0;
            }
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
            ++v19;
            v31 = 0;
            if ( v19 >= v29 )
              goto LABEL_100;
          }
          v8 = 0;
          v6 = 0;
          v7 = 0;
          goto LABEL_15;
        }
      }
LABEL_100:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
      v36 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
      v39 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
      v42 = 0;
      STRU::~STRU((STRU *)v52);
      return 0;
    case 1:
      v14 = 4;
      goto LABEL_49;
    case 2:
      v14 = 3;
      goto LABEL_49;
    case 3:
      v14 = 8;
      goto LABEL_49;
  }
  v9 = -2147024809;
LABEL_15:
  if ( v36 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    v36 = 0;
  }
  if ( v39 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    v39 = 0;
  }
  if ( v33 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    v33 = 0;
  }
  if ( v31 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    v31 = 0;
  }
  if ( v37 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    v37 = 0;
  }
  if ( v40 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    v40 = 0;
  }
  if ( v34 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    v34 = 0;
  }
  if ( v41 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    v41 = 0;
  }
  if ( v38 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    v38 = 0;
  }
  if ( v30 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    v30 = 0;
  }
  if ( v42 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    v42 = 0;
  }
  if ( v6 )
  {
    STRU::~STRU((STRU *)(v6 + 48));
    STRA::~STRA((STRA *)(v6 + 12));
    operator delete(v6);
  }
  if ( v7 )
  {
    CERT_MAP_RULE::~CERT_MAP_RULE((CERT_MAP_RULE *)v7);
    operator delete(v7);
  }
  if ( v8 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8, 0xFFFFFFFF) == 1 )
    {
      CERT_1TO1_MAP_RULE::~CERT_1TO1_MAP_RULE((CERT_1TO1_MAP_RULE *)v8);
      operator delete(v8);
    }
  }
  STRU::~STRU((STRU *)v52);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800041f0  mov     [rsp-8+arg_18], rbx
0x1800041f5  push    rbp
0x1800041f6  push    rsi
0x1800041f7  push    rdi
0x1800041f8  push    r12
0x1800041fa  push    r13
0x1800041fc  push    r14
0x1800041fe  push    r15
0x180004200  lea     rbp, [rsp-0C0h]
0x180004208  sub     rsp, 1C0h
0x18000420f  mov     rax, cs:__security_cookie
0x180004216  xor     rax, rsp
0x180004219  mov     [rbp+0F0h+var_40], rax
0x180004220  xor     ebx, ebx
0x180004222  mov     [rbp+0F0h+var_13C], 1
0x180004229  mov     r12, r8
0x18000422c  mov     [rbp+0F0h+var_148], rbx
0x180004230  mov     r15, rdx
0x180004233  mov     [rsp+1F0h+var_1A8], rbx
0x180004238  mov     r13, rcx
0x18000423b  mov     [rbp+0F0h+var_168], rbx
0x18000423f  xor     edx, edx; Val
0x180004241  mov     [rsp+1F0h+var_178], rbx
0x180004246  mov     r8d, 80h; Size
0x18000424c  mov     [rbp+0F0h+var_170], rbx
0x180004250  lea     rcx, [rbp+0F0h+var_C0]; void *
0x180004254  mov     [rsp+1F0h+var_188], rbx
0x180004259  mov     [rsp+1F0h+var_1A0], rbx
0x18000425e  mov     r14d, ebx
0x180004261  mov     [rsp+1F0h+var_190], rbx
0x180004266  mov     esi, ebx
0x180004268  mov     [rbp+0F0h+var_160], rbx
0x18000426c  mov     edi, ebx
0x18000426e  mov     [rbp+0F0h+var_150], rbx
0x180004272  mov     [rbp+0F0h+var_158], rbx
0x180004276  mov     [rsp+1F0h+var_1AC], ebx
0x18000427a  mov     [rsp+1F0h+var_180], ebx
0x18000427e  mov     [rbp+0F0h+var_138], ebx
0x180004281  mov     [rbp+0F0h+var_108], rbx
0x180004285  mov     [rbp+0F0h+var_110], rbx
0x180004289  mov     [rsp+1F0h+var_198], ebx
0x18000428d  mov     [rbp+0F0h+var_128], rbx
0x180004291  mov     [rbp+0F0h+var_130], rbx
0x180004295  mov     [rbp+0F0h+var_140], ebx
0x180004298  mov     [rbp+0F0h+var_118], rbx
0x18000429c  mov     [rbp+0F0h+var_120], rbx
0x1800042a0  call    memset_0
0x1800042a5  lea     r8d, [rbx+40h]
0x1800042a9  lea     rdx, [rbp+0F0h+var_C0]
0x1800042ad  lea     rcx, [rbp+0F0h+var_100]
0x1800042b1  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800042b7  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST/"
0x1800042be  mov     [rsp+1F0h+var_1B0], ebx
0x1800042c2  lea     rcx, [rbp+0F0h+var_100]
0x1800042c6  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800042cc  mov     ebx, eax
0x1800042ce  test    eax, eax
0x1800042d0  js      loc_18000446B
0x1800042d6  mov     rax, [r15]
0x1800042d9  mov     rcx, r15
0x1800042dc  mov     rax, [rax]
0x1800042df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042e4  mov     rdx, rax
0x1800042e7  mov     rcx, [rax]
0x1800042ea  mov     rax, [rcx+8]
0x1800042ee  mov     rcx, rdx
0x1800042f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042f6  mov     rdx, rax
0x1800042f9  lea     rcx, [rbp+0F0h+var_100]
0x1800042fd  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180004303  mov     ebx, eax
0x180004305  test    eax, eax
0x180004307  js      loc_18000446B
0x18000430d  mov     rcx, cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * s_pGlobalInfo
0x180004314  mov     rax, [rcx]
0x180004317  mov     rax, [rax+38h]
0x18000431b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004320  mov     r9, rax
0x180004323  lea     r8, [rbp+0F0h+var_148]
0x180004327  lea     rdx, IID_INativeConfigurationSystem
0x18000432e  mov     rcx, [rax]
0x180004331  mov     rax, [rcx]
0x180004334  mov     rcx, r9
0x180004337  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000433c  mov     ebx, eax
0x18000433e  test    eax, eax
0x180004340  js      loc_18000446B
0x180004346  mov     rcx, [rbp+0F0h+var_148]
0x18000434a  lea     r9, [rsp+1F0h+var_1A8]
0x18000434f  mov     r8, [rbp+0F0h+var_E0]
0x180004353  lea     rdx, aSystemWebserve; "system.webServer/security/authenticatio"...
0x18000435a  mov     [rsp+1F0h+var_1C8], rdi
0x18000435f  mov     [rsp+1F0h+var_1D0], r12
0x180004364  mov     rax, [rcx]
0x180004367  mov     rax, [rax+18h]
0x18000436b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004370  mov     ebx, eax
0x180004372  test    eax, eax
0x180004374  js      loc_18000446B
0x18000437a  mov     rcx, [rsp+1F0h+var_1A8]
0x18000437f  lea     r8, [r13+8]
0x180004383  xor     r9d, r9d
0x180004386  mov     [rsp+1F0h+var_1D0], rdi
0x18000438b  lea     rdx, aOnetoonecertif; "oneToOneCertificateMappingsEnabled"
0x180004392  mov     rax, [rcx]
0x180004395  mov     rax, [rax+48h]
0x180004399  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000439e  mov     ebx, eax
0x1800043a0  test    eax, eax
0x1800043a2  js      loc_18000446B
0x1800043a8  mov     rcx, [rsp+1F0h+var_1A8]
0x1800043ad  lea     r8, [r13+0Ch]
0x1800043b1  xor     r9d, r9d
0x1800043b4  mov     [rsp+1F0h+var_1D0], rdi
0x1800043b9  lea     rdx, aManytoonecerti; "manyToOneCertificateMappingsEnabled"
0x1800043c0  mov     rax, [rcx]
0x1800043c3  mov     rax, [rax+48h]
0x1800043c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043cc  mov     ebx, eax
0x1800043ce  test    eax, eax
0x1800043d0  js      loc_18000446B
0x1800043d6  mov     rcx, [rsp+1F0h+var_1A8]
0x1800043db  lea     r8, [rbp+0F0h+var_120]
0x1800043df  xor     r9d, r9d
0x1800043e2  mov     [rsp+1F0h+var_1D0], rdi
0x1800043e7  lea     rdx, aDefaultlogondo; "defaultLogonDomain"
0x1800043ee  mov     rax, [rcx]
0x1800043f1  mov     rax, [rax+40h]
0x1800043f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043fa  mov     ebx, eax
0x1800043fc  test    eax, eax
0x1800043fe  js      short loc_18000446B
0x180004400  mov     rdx, [rbp+0F0h+var_120]
0x180004404  lea     rcx, [r13+10h]
0x180004408  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000440e  mov     ebx, eax
0x180004410  test    eax, eax
0x180004412  js      short loc_18000446B
0x180004414  mov     rcx, [rsp+1F0h+var_1A8]
0x180004419  lea     r8, [rsp+1F0h+var_1B0]
0x18000441e  xor     r9d, r9d
0x180004421  mov     [rsp+1F0h+var_1D0], rdi
0x180004426  lea     rdx, aLogonmethod; "logonMethod"
0x18000442d  mov     rax, [rcx]
0x180004430  mov     rax, [rax+30h]
0x180004434  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004439  mov     ebx, eax
0x18000443b  test    eax, eax
0x18000443d  js      short loc_18000446B
0x18000443f  mov     eax, [rsp+1F0h+var_1B0]
0x180004443  test    eax, eax
0x180004445  jz      loc_180004656
0x18000444b  sub     eax, 1
0x18000444e  jz      loc_18000464F
0x180004454  sub     eax, 1
0x180004457  jz      loc_180004648
0x18000445d  cmp     eax, 1
0x180004460  jz      loc_180004641
0x180004466  mov     ebx, 80070057h
0x18000446b  mov     rcx, [rsp+1F0h+var_178]
0x180004470  test    rcx, rcx
0x180004473  jz      short loc_18000448A
0x180004475  mov     rax, [rcx]
0x180004478  mov     rax, [rax+10h]
0x18000447c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004481  mov     [rsp+1F0h+var_178], 0
0x18000448a  mov     rcx, [rbp+0F0h+var_160]
0x18000448e  test    rcx, rcx
0x180004491  jz      short loc_1800044A7
0x180004493  mov     rax, [rcx]
0x180004496  mov     rax, [rax+10h]
0x18000449a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000449f  mov     [rbp+0F0h+var_160], 0
0x1800044a7  mov     rcx, [rsp+1F0h+var_190]
0x1800044ac  test    rcx, rcx
0x1800044af  jz      short loc_1800044C6
0x1800044b1  mov     rax, [rcx]
0x1800044b4  mov     rax, [rax+10h]
0x1800044b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044bd  mov     [rsp+1F0h+var_190], 0
0x1800044c6  mov     rcx, [rsp+1F0h+var_1A0]
0x1800044cb  test    rcx, rcx
0x1800044ce  jz      short loc_1800044E5
0x1800044d0  mov     rax, [rcx]
0x1800044d3  mov     rax, [rax+10h]
0x1800044d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044dc  mov     [rsp+1F0h+var_1A0], 0
0x1800044e5  mov     rcx, [rbp+0F0h+var_170]
0x1800044e9  test    rcx, rcx
0x1800044ec  jz      short loc_180004502
0x1800044ee  mov     rax, [rcx]
0x1800044f1  mov     rax, [rax+10h]
0x1800044f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044fa  mov     [rbp+0F0h+var_170], 0
0x180004502  mov     rcx, [rbp+0F0h+var_158]
0x180004506  test    rcx, rcx
0x180004509  jz      short loc_18000451F
0x18000450b  mov     rax, [rcx]
0x18000450e  mov     rax, [rax+10h]
0x180004512  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004517  mov     [rbp+0F0h+var_158], 0
0x18000451f  mov     rcx, [rsp+1F0h+var_188]
0x180004524  test    rcx, rcx
0x180004527  jz      short loc_18000453E
0x180004529  mov     rax, [rcx]
0x18000452c  mov     rax, [rax+10h]
0x180004530  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004535  mov     [rsp+1F0h+var_188], 0
0x18000453e  mov     rcx, [rbp+0F0h+var_150]
0x180004542  test    rcx, rcx
0x180004545  jz      short loc_18000455B
0x180004547  mov     rax, [rcx]
0x18000454a  mov     rax, [rax+10h]
0x18000454e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004553  mov     [rbp+0F0h+var_150], 0
0x18000455b  mov     rcx, [rbp+0F0h+var_168]
0x18000455f  test    rcx, rcx
0x180004562  jz      short loc_180004578
0x180004564  mov     rax, [rcx]
0x180004567  mov     rax, [rax+10h]
0x18000456b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004570  mov     [rbp+0F0h+var_168], 0
0x180004578  mov     rcx, [rsp+1F0h+var_1A8]
0x18000457d  test    rcx, rcx
0x180004580  jz      short loc_180004597
0x180004582  mov     rax, [rcx]
0x180004585  mov     rax, [rax+10h]
0x180004589  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000458e  mov     [rsp+1F0h+var_1A8], 0
0x180004597  mov     rcx, [rbp+0F0h+var_148]
0x18000459b  test    rcx, rcx
0x18000459e  jz      short loc_1800045B4
0x1800045a0  mov     rax, [rcx]
0x1800045a3  mov     rax, [rax+10h]
0x1800045a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045ac  mov     [rbp+0F0h+var_148], 0
0x1800045b4  test    r14, r14
0x1800045b7  jz      short loc_1800045D5
0x1800045b9  lea     rcx, [r14+60h]
0x1800045bd  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800045c3  lea     rcx, [r14+18h]
0x1800045c7  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800045cd  mov     rcx, r14; Block
0x1800045d0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800045d5  test    rsi, rsi
0x1800045d8  jz      short loc_1800045EA
0x1800045da  mov     rcx, rsi; this
0x1800045dd  call    ??1CERT_MAP_RULE@@QEAA@XZ; CERT_MAP_RULE::~CERT_MAP_RULE(void)
0x1800045e2  mov     rcx, rsi; Block
0x1800045e5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800045ea  test    rdi, rdi
0x1800045ed  jz      short loc_18000460B
0x1800045ef  or      eax, 0FFFFFFFFh
0x1800045f2  lock xadd [rdi], eax
0x1800045f6  cmp     eax, 1
0x1800045f9  jnz     short loc_18000460B
0x1800045fb  mov     rcx, rdi; this
0x1800045fe  call    ??1CERT_1TO1_MAP_RULE@@QEAA@XZ; CERT_1TO1_MAP_RULE::~CERT_1TO1_MAP_RULE(void)
0x180004603  mov     rcx, rdi; Block
0x180004606  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000460b  lea     rcx, [rbp+0F0h+var_100]
0x18000460f  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180004615  mov     eax, ebx
0x180004617  mov     rcx, [rbp+0F0h+var_40]
0x18000461e  xor     rcx, rsp; StackCookie
0x180004621  call    __security_check_cookie
0x180004626  mov     rbx, [rsp+1F0h+arg_18]
0x18000462e  add     rsp, 1C0h
0x180004635  pop     r15
0x180004637  pop     r14
0x180004639  pop     r13
0x18000463b  pop     r12
0x18000463d  pop     rdi
0x18000463e  pop     rsi
0x18000463f  pop     rbp
0x180004640  retn
0x180004641  mov     eax, 8
0x180004646  jmp     short loc_18000465B
0x180004648  mov     eax, 3
0x18000464d  jmp     short loc_18000465B
0x18000464f  mov     eax, 4
0x180004654  jmp     short loc_18000465B
0x180004656  mov     eax, 2
0x18000465b  mov     rcx, [rsp+1F0h+var_1A8]
0x180004660  lea     r8, [rbp+0F0h+var_150]
0x180004664  mov     [rsp+1F0h+var_1B0], eax
0x180004668  lea     rdx, aOnetoonemappin; "oneToOneMappings"
0x18000466f  mov     [r13+48h], eax
0x180004673  mov     rax, [rcx]
0x180004676  mov     rax, [rax+20h]
0x18000467a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000467f  mov     ebx, eax
0x180004681  test    eax, eax
0x180004683  js      loc_18000446B
0x180004689  mov     rcx, [rbp+0F0h+var_150]
0x18000468d  lea     rdx, [rbp+0F0h+var_168]
0x180004691  mov     rax, [rcx]
0x180004694  mov     rax, [rax+28h]
0x180004698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000469d  mov     ebx, eax
  ... truncated ...
```
