# SITE_OBJECT_EXTENSION::AddSite(IExtensionContext *,ICommandParameterList *,ICommandObjectList *,IXMLDOMDocument *)

- ea: `0x18000f234`
- end: `0x18000fc7c`
- name: `?AddSite@SITE_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEAVICommandObjectList@@PEAUIXMLDOMDocument@@@Z`
- size: `2632`
- prototype: `__int64 __usercall@<rax>(SITE_OBJECT_EXTENSION *__hidden this@<rcx>, struct IExtensionContext *@<rdx>, struct ICommandParameterList *@<r8>, struct ICommandObjectList *@<r9>, struct IXMLDOMDocument *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180011690`

## callees

- `0x180001044`
- `0x180001fb0`
- `0x180002640`
- `0x180002e90`
- `0x18000efb0`
- `0x18000f234`
- `0x180010850`
- `0x180011afc`
- `0x1800122a8`
- `0x180012450`
- `0x18002a6cc`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!_wtol` at `0x18000f4d9`
- `msvcrt!_wtol` at `0x18000f4d9`
- `msvcrt!_ltow_s` at `0x18000f496`
- `msvcrt!_ltow_s` at `0x18000f496`
- `msvcrt!wcsstr` at `0x18000f3f4`
- `msvcrt!wcsstr` at `0x18000f3f4`

## string_xrefs

- `0x18000f55d`: `physicalPath`
- `0x18000f592`: `physicalPath`
- `0x18000f9e4`: `physicalPath`
- `0x18000f99c`: `virtualDirectory`

## pseudocode

```c
__int64 __fastcall SITE_OBJECT_EXTENSION::AddSite(
        SITE_OBJECT_EXTENSION *this,
        struct IExtensionContext *a2,
        struct ICommandParameterList *a3,
        struct ICommandObjectList *a4,
        struct IXMLDOMDocument *a5)
{
  int v9; // r15d
  int v10; // eax
  signed int NextAvailableSiteId; // ebx
  __int64 v12; // r8
  int v13; // eax
  errno_t v14; // eax
  int v15; // r15d
  int v16; // eax
  int v17; // eax
  SITE_OBJECT *v18; // rax
  SITE_OBJECT *v19; // rdi
  int v20; // eax
  SITE_OBJECT_EXTENSION *v21; // rcx
  int v22; // eax
  __int64 v23; // rax
  APP_OBJECT_UTILS *v24; // rcx
  unsigned int v25; // r8d
  unsigned __int16 *v26; // rax
  APP_OBJECT_UTILS *v27; // rcx
  unsigned int v28; // r8d
  APP_OBJECT_UTILS *v29; // rcx
  unsigned int v30; // r8d
  __int64 v32; // [rsp+40h] [rbp-C0h] BYREF
  struct INativeConfigurationElement *v33; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *Str; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v35; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v36; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v37; // [rsp+68h] [rbp-98h] BYREF
  int Value; // [rsp+70h] [rbp-90h] BYREF
  wchar_t *String; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v40; // [rsp+80h] [rbp-80h] BYREF
  __int64 v41; // [rsp+88h] [rbp-78h] BYREF
  struct INativeConfigurationElement *v42; // [rsp+90h] [rbp-70h] BYREF
  __int64 v43; // [rsp+98h] [rbp-68h] BYREF
  __int64 v44; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v45; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v46; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v47; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v48; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v49[32]; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int16 *v50; // [rsp+E8h] [rbp-18h]
  int v51; // [rsp+F0h] [rbp-10h]
  __int16 v52; // [rsp+F4h] [rbp-Ch]
  int v53; // [rsp+F8h] [rbp-8h]
  _BYTE v54[32]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 *v55; // [rsp+120h] [rbp+20h]
  int v56; // [rsp+128h] [rbp+28h]
  __int16 v57; // [rsp+12Ch] [rbp+2Ch]
  int v58; // [rsp+130h] [rbp+30h]
  unsigned __int16 *v59[2]; // [rsp+138h] [rbp+38h] BYREF
  __int64 v60; // [rsp+148h] [rbp+48h]
  wchar_t Buffer[32]; // [rsp+150h] [rbp+50h] BYREF
  __int16 v62; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v63[510]; // [rsp+192h] [rbp+92h] BYREF
  __int16 v64; // [rsp+390h] [rbp+290h] BYREF
  _BYTE v65[510]; // [rsp+392h] [rbp+292h] BYREF

  v42 = 0;
  v33 = 0;
  v36 = 0;
  v37 = 0;
  v41 = 0;
  v44 = 0;
  v43 = 0;
  v46 = 0;
  v47 = 0;
  v32 = 0;
  v45 = 0;
  Str = 0;
  v48 = 0;
  String = 0;
  v40 = 0;
  *(_OWORD *)v59 = 0;
  v60 = 0;
  memset_0(v63, 0, sizeof(v63));
  v57 = 256;
  v55 = (unsigned __int16 *)&v62;
  v56 = 512;
  v62 = 0;
  v58 = 0;
  memset_0(v65, 0, sizeof(v65));
  v51 = 512;
  v9 = -1;
  v52 = 256;
  v53 = 0;
  v50 = (unsigned __int16 *)&v64;
  v64 = 0;
  v35 = 0;
  Value = -1;
  if ( !a2 || !a3 || !a4 )
  {
    NextAvailableSiteId = -2147024809;
    goto LABEL_105;
  }
  v10 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, const unsigned __int16 *, wchar_t **))(*(_QWORD *)a3 + 40LL))(
          a3,
          L"name",
          &Str);
  NextAvailableSiteId = v10;
  if ( v10 == -2147023483 )
  {
    if ( (*(int (__fastcall **)(struct ICommandParameterList *, const unsigned __int16 *, wchar_t **))(*(_QWORD *)a3 + 40LL))(
           a3,
           L"SITE.NAME",
           &Str) < 0 )
    {
      v59[0] = L"name";
      v12 = 3221226486LL;
      v59[1] = 0;
LABEL_7:
      NextAvailableSiteId = -2147024809;
      (*(void (__fastcall **)(struct IExtensionContext *, __int64, __int64, unsigned __int16 **, _DWORD))(*(_QWORD *)a2 + 144LL))(
        a2,
        2147942487LL,
        v12,
        v59,
        0);
      goto LABEL_82;
    }
  }
  else if ( v10 < 0 )
  {
    goto LABEL_82;
  }
  if ( wcsstr(Str, L"/") )
  {
    v59[0] = L"name";
    v12 = 3221226476LL;
    v59[1] = Str;
    goto LABEL_7;
  }
  v13 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, const wchar_t *, wchar_t **))(*(_QWORD *)a3 + 40LL))(
          a3,
          L"id",
          &String);
  NextAvailableSiteId = v13;
  if ( v13 != -2147023483 )
  {
    if ( v13 < 0 )
      goto LABEL_82;
    goto LABEL_19;
  }
  if ( (*(int (__fastcall **)(struct ICommandParameterList *, const unsigned __int16 *, wchar_t **))(*(_QWORD *)a3 + 40LL))(
         a3,
         L"SITE.ID",
         &String) < 0 )
  {
    NextAvailableSiteId = SITE_OBJECT_EXTENSION::GetNextAvailableSiteId(this, a2, &Value);
    if ( NextAvailableSiteId < 0 )
      goto LABEL_82;
    v9 = Value;
    v14 = _ltow_s(Value, Buffer, 0x20u, 10);
    NextAvailableSiteId = v14;
    if ( v14 )
    {
      if ( v14 > 0 )
        NextAvailableSiteId = (unsigned __int16)v14 | 0x80070000;
      goto LABEL_82;
    }
    String = Buffer;
LABEL_19:
    if ( v9 != -1 )
      goto LABEL_25;
  }
  v15 = _wtol(String);
  if ( !*((_DWORD *)this + 12) )
  {
    NextAvailableSiteId = SITE_OBJECT_EXTENSION::GetNextAvailableSiteId(this, a2, 0);
    if ( NextAvailableSiteId < 0 )
      goto LABEL_82;
  }
  v16 = *((_DWORD *)this + 12);
  if ( v16 <= v15 )
    v16 = v15 + 1;
  *((_DWORD *)this + 12) = v16;
LABEL_25:
  NextAvailableSiteId = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64 *))(*(_QWORD *)a2 + 192LL))(
                          a2,
                          &v35);
  if ( NextAvailableSiteId < 0 )
    goto LABEL_82;
  NextAvailableSiteId = (*(__int64 (__fastcall **)(struct ICommandParameterList *, __int64))(*(_QWORD *)a3 + 72LL))(
                          a3,
                          v35);
  if ( NextAvailableSiteId < 0 )
    goto LABEL_82;
  v17 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, unsigned __int16 **))(*(_QWORD *)v35 + 40LL))(
          v35,
          L"physicalPath",
          &v40);
  NextAvailableSiteId = v17;
  if ( v17 < 0 )
  {
    if ( v17 != -2147023483 )
      goto LABEL_82;
  }
  else
  {
    NextAvailableSiteId = STRU::Copy((STRU *)v54, v40);
    if ( NextAvailableSiteId < 0 )
      goto LABEL_82;
    NextAvailableSiteId = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v35 + 48LL))(
                            v35,
                            L"physicalPath");
    if ( NextAvailableSiteId < 0 )
      goto LABEL_82;
    v40 = v55;
  }
  NextAvailableSiteId = (*(__int64 (__fastcall **)(struct IExtensionContext *, const wchar_t *, __int64 *))(*(_QWORD *)a2 + 80LL))(
                          a2,
                          L"MACHINE/WEBROOT/APPHOST",
                          &v46);
  if ( NextAvailableSiteId >= 0 )
  {
    NextAvailableSiteId = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, struct INativeConfigurationElement **, __int64 *, _QWORD))(*(_QWORD *)v46 + 24LL))(
                            v46,
                            L"system.applicationHost/sites",
                            L"MACHINE/WEBROOT/APPHOST",
                            &v42,
                            &v47,
                            0);
    if ( NextAvailableSiteId < 0 )
    {
      if ( v47 )
        (*(void (__fastcall **)(struct IExtensionContext *, _QWORD, const wchar_t *, __int64, _DWORD))(*(_QWORD *)a2 + 112LL))(
          a2,
          (unsigned int)NextAvailableSiteId,
          &::Str,
          v47,
          0);
      goto LABEL_82;
    }
    NextAvailableSiteId = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 *))(*(_QWORD *)v42 + 40LL))(
                            v42,
                            &v41);
    if ( NextAvailableSiteId >= 0 )
    {
      NextAvailableSiteId = (*(__int64 (__fastcall **)(__int64, const wchar_t *, struct INativeConfigurationElement **))(*(_QWORD *)v41 + 48LL))(
                              v41,
                              L"site",
                              &v33);
      if ( NextAvailableSiteId >= 0 )
      {
        v18 = (SITE_OBJECT *)operator new(0xD8u);
        if ( !v18 || (v19 = SITE_OBJECT::SITE_OBJECT(v18, v33, v42)) == 0 )
        {
          NextAvailableSiteId = -2147024888;
          goto LABEL_82;
        }
        NextAvailableSiteId = (*(__int64 (__fastcall **)(struct IExtensionContext *, struct INativeConfigurationElement *, const unsigned __int16 *, wchar_t *))(*(_QWORD *)a2 + 96LL))(
                                a2,
                                v33,
                                L"name",
                                Str);
        if ( NextAvailableSiteId < 0 )
          goto LABEL_76;
        NextAvailableSiteId = (*(__int64 (__fastcall **)(struct IExtensionContext *, struct INativeConfigurationElement *, const wchar_t *, wchar_t *))(*(_QWORD *)a2 + 96LL))(
                                a2,
                                v33,
                                L"id",
                                String);
        if ( NextAvailableSiteId < 0 )
          goto LABEL_76;
        NextAvailableSiteId = SITE_OBJECT::Reset(v19);
        if ( NextAvailableSiteId < 0 )
          goto LABEL_76;
        NextAvailableSiteId = (*(__int64 (__fastcall **)(struct IExtensionContext *, SITE_OBJECT *, __int64, _QWORD, struct IXMLDOMDocument *, int))(*(_QWORD *)a2 + 168LL))(
                                a2,
                                v19,
                                v35,
                                0,
                                a5,
                                1);
        if ( NextAvailableSiteId < 0 )
          goto LABEL_76;
        v20 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, unsigned __int16 **))(*(_QWORD *)v35 + 40LL))(
                v35,
                L"bindings",
                &v48);
        NextAvailableSiteId = v20;
        if ( v20 < 0 )
        {
          if ( v20 != -2147023483 )
          {
LABEL_76:
            (*(void (__fastcall **)(SITE_OBJECT *))(*(_QWORD *)v19 + 16LL))(v19);
            goto LABEL_82;
          }
        }
        else if ( *v48 )
        {
          NextAvailableSiteId = SITE_OBJECT_EXTENSION::SetBindingInformation(v21, a2, v33, v48, 1);
          if ( NextAvailableSiteId < 0 )
            goto LABEL_76;
        }
        v22 = (*(__int64 (__fastcall **)(__int64, struct INativeConfigurationElement *, __int64, __int64 *))(*(_QWORD *)v41 + 56LL))(
                v41,
                v33,
                0xFFFFFFFFLL,
                &v32);
        NextAvailableSiteId = v22;
        if ( v22 < 0 )
        {
          if ( v22 == -2147024713 )
          {
            v59[0] = Str;
            v23 = *(_QWORD *)a2;
            v59[1] = 0;
            (*(void (__fastcall **)(struct IExtensionContext *, __int64, __int64, unsigned __int16 **, _DWORD))(v23 + 144))(
              a2,
              2147942583LL,
              3221226483LL,
              v59,
              0);
            goto LABEL_76;
          }
          if ( !v32 )
            goto LABEL_76;
          (*(void (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v32 + 24LL))(v32, &v45);
          if ( !v45 )
          {
LABEL_56:
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
            v32 = 0;
            goto LABEL_76;
          }
          v59[1] = v45;
          v59[0] = L"SITE";
LABEL_55:
          (*(void (__fastcall **)(struct IExtensionContext *, _QWORD, __int64, unsigned __int16 **, _DWORD))(*(_QWORD *)a2 + 144LL))(
            a2,
            (unsigned int)NextAvailableSiteId,
            3221226480LL,
            v59,
            0);
          goto LABEL_56;
        }
        NextAvailableSiteId = SITE_OBJECT::Create(v19, L"MACHINE/WEBROOT/APPHOST", 4);
        if ( NextAvailableSiteId < 0 )
          goto LABEL_76;
        NextAvailableSiteId = (*(__int64 (__fastcall **)(struct IExtensionContext *, const wchar_t *, _QWORD))(*(_QWORD *)a2 + 208LL))(
                                a2,
                                L"MACHINE/WEBROOT/APPHOST",
                                0);
        if ( NextAvailableSiteId < 0 )
          goto LABEL_76;
        v59[0] = L"SITE";
        v59[1] = Str;
        NextAvailableSiteId = APP_OBJECT_UTILS::AddStatusObject(v24, a4, v25, (const unsigned __int16 **const)v59);
        if ( NextAvailableSiteId < 0 )
          goto LABEL_76;
        if ( v40 )
        {
          NextAvailableSiteId = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 *))(*(_QWORD *)v33 + 40LL))(
                                  v33,
                                  &v44);
          if ( NextAvailableSiteId < 0 )
            goto LABEL_76;
          NextAvailableSiteId = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v44 + 48LL))(
                                  v44,
                                  L"application",
                                  &v36);
          if ( NextAvailableSiteId < 0 )
            goto LABEL_76;
          NextAvailableSiteId = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64, const unsigned __int16 *, const wchar_t *))(*(_QWORD *)a2 + 96LL))(
                                  a2,
                                  v36,
                                  L"path",
                                  L"/");
          if ( NextAvailableSiteId < 0 )
            goto LABEL_76;
          NextAvailableSiteId = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v36 + 40LL))(v36, &v43);
          if ( NextAvailableSiteId < 0 )
            goto LABEL_76;
          NextAvailableSiteId = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v43 + 48LL))(
                                  v43,
                                  L"virtualDirectory",
                                  &v37);
          if ( NextAvailableSiteId < 0 )
            goto LABEL_76;
          NextAvailableSiteId = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64, const unsigned __int16 *, const wchar_t *))(*(_QWORD *)a2 + 96LL))(
                                  a2,
                                  v37,
                                  L"path",
                                  L"/");
          if ( NextAvailableSiteId < 0 )
            goto LABEL_76;
          NextAvailableSiteId = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64, const unsigned __int16 *, unsigned __int16 *))(*(_QWORD *)a2 + 96LL))(
                                  a2,
                                  v37,
                                  L"physicalPath",
                                  v40);
          if ( NextAvailableSiteId < 0 )
            goto LABEL_76;
          NextAvailableSiteId = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)v43 + 56LL))(
                                  v43,
                                  v37,
                                  0xFFFFFFFFLL,
                                  &v32);
          if ( NextAvailableSiteId < 0 )
          {
            v26 = L"VDIR";
            goto LABEL_78;
          }
          NextAvailableSiteId = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)v44 + 56LL))(
                                  v44,
                                  v36,
                                  0xFFFFFFFFLL,
                                  &v32);
          if ( NextAvailableSiteId < 0 )
          {
            v26 = L"APP";
LABEL_78:
            v59[0] = v26;
            if ( !v32 )
              goto LABEL_76;
            (*(void (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v32 + 24LL))(v32, &v45);
            if ( !v45 )
              goto LABEL_56;
            v59[1] = v45;
            goto LABEL_55;
          }
          NextAvailableSiteId = STRU::Copy((STRU *)v49, Str);
          if ( NextAvailableSiteId < 0 )
            goto LABEL_76;
          NextAvailableSiteId = STRU::Append((STRU *)v49, L"/");
          if ( NextAvailableSiteId < 0 )
            goto LABEL_76;
          v59[0] = L"APP";
          v59[1] = v50;
          NextAvailableSiteId = APP_OBJECT_UTILS::AddStatusObject(v27, a4, v28, (const unsigned __int16 **const)v59);
          if ( NextAvailableSiteId < 0 )
            goto LABEL_76;
          v59[0] = L"VDIR";
          NextAvailableSiteId = APP_OBJECT_UTILS::AddStatusObject(v29, a4, v30, (const unsigned __int16 **const)v59);
          if ( NextAvailableSiteId < 0 )
            goto LABEL_76;
        }
        NextAvailableSiteId = 0;
        goto LABEL_76;
      }
    }
  }
LABEL_82:
  if ( v33 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v33 + 16LL))(v33);
    v33 = 0;
  }
  if ( v41 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    v41 = 0;
  }
  if ( v42 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v42 + 16LL))(v42);
    v42 = 0;
  }
  if ( v43 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    v43 = 0;
  }
  if ( v44 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    v44 = 0;
  }
  if ( v36 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    v36 = 0;
  }
  if ( v37 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    v37 = 0;
  }
  if ( v46 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    v46 = 0;
  }
  if ( v47 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    v47 = 0;
  }
  if ( v32 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    v32 = 0;
  }
  if ( v35 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    v35 = 0;
  }
LABEL_105:
  BUFFER::~BUFFER((BUFFER *)v49);
  BUFFER::~BUFFER((BUFFER *)v54);
  return (unsigned int)NextAvailableSiteId;
}

```

## disassembly

```asm
0x18000f234  push    rbp
0x18000f236  push    rbx
0x18000f237  push    rsi
0x18000f238  push    rdi
0x18000f239  push    r12
0x18000f23b  push    r13
0x18000f23d  push    r14
0x18000f23f  push    r15
0x18000f241  lea     rbp, [rsp-4A8h]
0x18000f249  sub     rsp, 5A8h
0x18000f250  mov     rax, cs:__security_cookie
0x18000f257  xor     rax, rsp
0x18000f25a  mov     [rbp+4E0h+var_50], rax
0x18000f261  mov     r13, [rbp+4E0h+arg_20]
0x18000f268  mov     r14, rcx
0x18000f26b  xor     ecx, ecx
0x18000f26d  mov     rdi, r8
0x18000f270  mov     [rbp+4E0h+var_550], rcx
0x18000f274  mov     rsi, rdx
0x18000f277  mov     [rsp+5E0h+var_598], rcx
0x18000f27c  xorps   xmm0, xmm0
0x18000f27f  mov     [rsp+5E0h+var_580], rcx
0x18000f284  xor     eax, eax
0x18000f286  mov     [rsp+5E0h+var_578], rcx
0x18000f28b  mov     r15d, 1FEh
0x18000f291  mov     [rbp+4E0h+var_558], rcx
0x18000f295  mov     r8d, r15d; Size
0x18000f298  mov     [rbp+4E0h+var_540], rcx
0x18000f29c  xor     edx, edx; Val
0x18000f29e  mov     [rbp+4E0h+var_548], rcx
0x18000f2a2  mov     r12, r9
0x18000f2a5  mov     [rbp+4E0h+var_530], rcx
0x18000f2a9  mov     [rbp+4E0h+var_528], rcx
0x18000f2ad  mov     [rsp+5E0h+var_5A0], rcx
0x18000f2b2  mov     [rbp+4E0h+var_538], rcx
0x18000f2b6  mov     [rsp+5E0h+Str], rcx
0x18000f2bb  mov     [rbp+4E0h+var_520], rcx
0x18000f2bf  mov     [rsp+5E0h+String], rcx
0x18000f2c4  mov     [rbp+4E0h+var_560], rcx
0x18000f2c8  lea     rcx, [rbp+4E0h+var_44E]; void *
0x18000f2cf  movups  xmmword ptr [rbp+4E0h+var_4A8], xmm0
0x18000f2d3  mov     [rbp+4E0h+var_498], rax
0x18000f2d7  call    memset_0
0x18000f2dc  lea     rax, [rbp+4E0h+var_450]
0x18000f2e3  mov     [rbp+4E0h+var_4B4], 100h
0x18000f2e9  mov     [rbp+4E0h+var_4C0], rax
0x18000f2ed  lea     ebx, [r15+2]
0x18000f2f1  xor     eax, eax
0x18000f2f3  mov     [rbp+4E0h+var_4B8], ebx
0x18000f2f6  mov     r8d, r15d; Size
0x18000f2f9  mov     [rbp+4E0h+var_450], ax
0x18000f300  xor     edx, edx; Val
0x18000f302  mov     [rbp+4E0h+var_4B0], 0
0x18000f309  lea     rcx, [rbp+4E0h+var_24E]; void *
0x18000f310  call    memset_0
0x18000f315  xor     ecx, ecx
0x18000f317  mov     [rbp+4E0h+var_4F0], ebx
0x18000f31a  or      r15d, 0FFFFFFFFh
0x18000f31e  mov     [rbp+4E0h+var_4EC], 100h
0x18000f324  mov     [rbp+4E0h+var_4E8], ecx
0x18000f327  lea     rax, [rbp+4E0h+var_250]
0x18000f32e  mov     [rbp+4E0h+var_4F8], rax
0x18000f332  mov     [rbp+4E0h+var_250], cx
0x18000f339  mov     [rsp+5E0h+var_588], rcx
0x18000f33e  mov     [rsp+5E0h+Value], r15d
0x18000f343  test    rsi, rsi
0x18000f346  jz      loc_18000FC40
0x18000f34c  test    rdi, rdi
0x18000f34f  jz      loc_18000FC40
0x18000f355  test    r12, r12
0x18000f358  jz      loc_18000FC40
0x18000f35e  mov     rax, [rdi]
0x18000f361  lea     r8, [rsp+5E0h+Str]
0x18000f366  lea     rdx, aName_0; "name"
0x18000f36d  mov     rcx, rdi
0x18000f370  mov     rax, [rax+28h]
0x18000f374  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f379  mov     ebx, eax
0x18000f37b  cmp     eax, 80070585h
0x18000f380  jnz     short loc_18000F3E0
0x18000f382  mov     rax, [rdi]
0x18000f385  lea     r8, [rsp+5E0h+Str]
0x18000f38a  lea     rdx, aSiteName; "SITE.NAME"
0x18000f391  mov     rcx, rdi
0x18000f394  mov     rax, [rax+28h]
0x18000f398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f39d  test    eax, eax
0x18000f39f  jns     short loc_18000F3E8
0x18000f3a1  lea     r8, aName_0; "name"
0x18000f3a8  xor     r15d, r15d
0x18000f3ab  mov     [rbp+4E0h+var_4A8], r8
0x18000f3af  mov     r8d, 0C00003F6h
0x18000f3b5  mov     [rbp+4E0h+var_4A8+8], r15
0x18000f3b9  mov     rax, [rsi]
0x18000f3bc  lea     r9, [rbp+4E0h+var_4A8]
0x18000f3c0  mov     ebx, 80070057h
0x18000f3c5  mov     [rsp+5E0h+var_5C0], r15d
0x18000f3ca  mov     edx, ebx
0x18000f3cc  mov     rcx, rsi
0x18000f3cf  mov     rax, [rax+90h]
0x18000f3d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3db  jmp     loc_18000FB21
0x18000f3e0  test    eax, eax
0x18000f3e2  js      loc_18000FB1E
0x18000f3e8  mov     rcx, [rsp+5E0h+Str]; Str
0x18000f3ed  lea     rdx, SubStr; "/"
0x18000f3f4  call    cs:__imp_wcsstr
0x18000f3fa  test    rax, rax
0x18000f3fd  jz      short loc_18000F41E
0x18000f3ff  mov     rax, [rsp+5E0h+Str]
0x18000f404  lea     r8, aName_0; "name"
0x18000f40b  mov     [rbp+4E0h+var_4A8], r8
0x18000f40f  xor     r15d, r15d
0x18000f412  mov     r8d, 0C00003ECh
0x18000f418  mov     [rbp+4E0h+var_4A8+8], rax
0x18000f41c  jmp     short loc_18000F3B9
0x18000f41e  mov     rax, [rdi]
0x18000f421  lea     r8, [rsp+5E0h+String]
0x18000f426  lea     rdx, aId; "id"
0x18000f42d  mov     rcx, rdi
0x18000f430  mov     rax, [rax+28h]
0x18000f434  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f439  mov     ebx, eax
0x18000f43b  cmp     eax, 80070585h
0x18000f440  jnz     loc_18000F4C6
0x18000f446  mov     rax, [rdi]
0x18000f449  lea     r8, [rsp+5E0h+String]
0x18000f44e  lea     rdx, aSiteId; "SITE.ID"
0x18000f455  mov     rcx, rdi
0x18000f458  mov     rax, [rax+28h]
0x18000f45c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f461  xor     r15d, r15d
0x18000f464  test    eax, eax
0x18000f466  jns     short loc_18000F4D4
0x18000f468  lea     r8, [rsp+5E0h+Value]; int *
0x18000f46d  mov     rdx, rsi; struct IExtensionContext *
0x18000f470  mov     rcx, r14; this
0x18000f473  call    ?GetNextAvailableSiteId@SITE_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEAJ@Z; SITE_OBJECT_EXTENSION::GetNextAvailableSiteId(IExtensionContext *,long *)
0x18000f478  mov     ebx, eax
0x18000f47a  test    eax, eax
0x18000f47c  js      loc_18000FB21
0x18000f482  lea     r9d, [r15+0Ah]; Radix
0x18000f486  lea     r8d, [r15+20h]; BufferCount
0x18000f48a  mov     r15d, [rsp+5E0h+Value]
0x18000f48f  mov     ecx, r15d; Value
0x18000f492  lea     rdx, [rbp+4E0h+Buffer]; Buffer
0x18000f496  call    cs:__imp__ltow_s
0x18000f49c  mov     ebx, eax
0x18000f49e  test    eax, eax
0x18000f4a0  jz      short loc_18000F4BB
0x18000f4a2  xor     r15d, r15d
0x18000f4a5  test    eax, eax
0x18000f4a7  jle     loc_18000FB21
0x18000f4ad  movzx   ebx, ax
0x18000f4b0  or      ebx, 80070000h
0x18000f4b6  jmp     loc_18000FB21
0x18000f4bb  lea     rax, [rbp+4E0h+Buffer]
0x18000f4bf  mov     [rsp+5E0h+String], rax
0x18000f4c4  jmp     short loc_18000F4CE
0x18000f4c6  test    eax, eax
0x18000f4c8  js      loc_18000FB1E
0x18000f4ce  cmp     r15d, 0FFFFFFFFh
0x18000f4d2  jnz     short loc_18000F512
0x18000f4d4  mov     rcx, [rsp+5E0h+String]; String
0x18000f4d9  call    cs:__imp__wtol
0x18000f4df  cmp     dword ptr [r14+30h], 0
0x18000f4e4  mov     r15d, eax
0x18000f4e7  jnz     short loc_18000F501
0x18000f4e9  xor     r8d, r8d; int *
0x18000f4ec  mov     rdx, rsi; struct IExtensionContext *
0x18000f4ef  mov     rcx, r14; this
0x18000f4f2  call    ?GetNextAvailableSiteId@SITE_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEAJ@Z; SITE_OBJECT_EXTENSION::GetNextAvailableSiteId(IExtensionContext *,long *)
0x18000f4f7  mov     ebx, eax
0x18000f4f9  test    eax, eax
0x18000f4fb  js      loc_18000FB1E
0x18000f501  mov     eax, [r14+30h]
0x18000f505  cmp     eax, r15d
0x18000f508  jg      short loc_18000F50E
0x18000f50a  lea     eax, [r15+1]
0x18000f50e  mov     [r14+30h], eax
0x18000f512  mov     rax, [rsi]
0x18000f515  lea     rdx, [rsp+5E0h+var_588]
0x18000f51a  mov     rcx, rsi
0x18000f51d  mov     rax, [rax+0C0h]
0x18000f524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f529  xor     r15d, r15d
0x18000f52c  mov     ebx, eax
0x18000f52e  test    eax, eax
0x18000f530  js      loc_18000FB21
0x18000f536  mov     rax, [rdi]
0x18000f539  mov     rcx, rdi
0x18000f53c  mov     rdx, [rsp+5E0h+var_588]
0x18000f541  mov     rax, [rax+48h]
0x18000f545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f54a  mov     ebx, eax
0x18000f54c  test    eax, eax
0x18000f54e  js      loc_18000FB21
0x18000f554  mov     rcx, [rsp+5E0h+var_588]
0x18000f559  lea     r8, [rbp+4E0h+var_560]
0x18000f55d  lea     rdx, aPhysicalpath; "physicalPath"
0x18000f564  mov     rax, [rcx]
0x18000f567  mov     rax, [rax+28h]
0x18000f56b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f570  mov     ebx, eax
0x18000f572  test    eax, eax
0x18000f574  js      short loc_18000F5B9
0x18000f576  mov     rdx, [rbp+4E0h+var_560]; unsigned __int16 *
0x18000f57a  lea     rcx, [rbp+4E0h+var_4E0]; this
0x18000f57e  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000f583  mov     ebx, eax
0x18000f585  test    eax, eax
0x18000f587  js      loc_18000FB21
0x18000f58d  mov     rcx, [rsp+5E0h+var_588]
0x18000f592  lea     rdx, aPhysicalpath; "physicalPath"
0x18000f599  mov     rax, [rcx]
0x18000f59c  mov     rax, [rax+30h]
0x18000f5a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5a5  mov     ebx, eax
0x18000f5a7  test    eax, eax
0x18000f5a9  js      loc_18000FB21
0x18000f5af  mov     rax, [rbp+4E0h+var_4C0]
0x18000f5b3  mov     [rbp+4E0h+var_560], rax
0x18000f5b7  jmp     short loc_18000F5C4
0x18000f5b9  cmp     eax, 80070585h
0x18000f5be  jnz     loc_18000FB21
0x18000f5c4  mov     rax, [rsi]
0x18000f5c7  lea     r14, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x18000f5ce  lea     r8, [rbp+4E0h+var_530]
0x18000f5d2  mov     rdx, r14
0x18000f5d5  mov     rcx, rsi
0x18000f5d8  mov     rax, [rax+50h]
0x18000f5dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5e1  mov     ebx, eax
0x18000f5e3  test    eax, eax
0x18000f5e5  js      loc_18000FB21
0x18000f5eb  mov     rcx, [rbp+4E0h+var_530]
0x18000f5ef  lea     rdx, [rbp+4E0h+var_528]
0x18000f5f3  mov     [rsp+5E0h+var_5B8], r15
0x18000f5f8  lea     r9, [rbp+4E0h+var_550]
0x18000f5fc  mov     qword ptr [rsp+5E0h+var_5C0], rdx
0x18000f601  mov     r8, r14
0x18000f604  lea     rdx, aSystemApplicat_2; "system.applicationHost/sites"
0x18000f60b  mov     rax, [rcx]
0x18000f60e  mov     rax, [rax+18h]
0x18000f612  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f617  mov     ebx, eax
0x18000f619  test    eax, eax
0x18000f61b  jns     short loc_18000F64F
0x18000f61d  mov     rcx, [rbp+4E0h+var_528]
0x18000f621  test    rcx, rcx
0x18000f624  jz      loc_18000FB21
0x18000f62a  mov     rax, [rsi]
0x18000f62d  lea     r8, Str
0x18000f634  mov     r9, rcx
0x18000f637  mov     [rsp+5E0h+var_5C0], r15d
0x18000f63c  mov     edx, ebx
0x18000f63e  mov     rcx, rsi
0x18000f641  mov     rax, [rax+70h]
0x18000f645  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f64a  jmp     loc_18000FB21
0x18000f64f  mov     rcx, [rbp+4E0h+var_550]
0x18000f653  lea     rdx, [rbp+4E0h+var_558]
0x18000f657  mov     rax, [rcx]
0x18000f65a  mov     rax, [rax+28h]
0x18000f65e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f663  mov     ebx, eax
0x18000f665  test    eax, eax
0x18000f667  js      loc_18000FB21
0x18000f66d  mov     rcx, [rbp+4E0h+var_558]
0x18000f671  lea     r8, [rsp+5E0h+var_598]
0x18000f676  lea     rdx, aSite; "site"
0x18000f67d  mov     rax, [rcx]
0x18000f680  mov     rax, [rax+30h]
0x18000f684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f689  mov     ebx, eax
0x18000f68b  test    eax, eax
0x18000f68d  js      loc_18000FB21
0x18000f693  mov     ecx, 0D8h; Size
0x18000f698  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f69d  test    rax, rax
0x18000f6a0  jz      loc_18000FB17
0x18000f6a6  mov     r8, [rbp+4E0h+var_550]; struct INativeConfigurationElement *
0x18000f6aa  mov     rcx, rax; this
0x18000f6ad  mov     rdx, [rsp+5E0h+var_598]; struct INativeConfigurationElement *
0x18000f6b2  call    ??0SITE_OBJECT@@QEAA@PEAVINativeConfigurationElement@@0@Z; SITE_OBJECT::SITE_OBJECT(INativeConfigurationElement *,INativeConfigurationElement *)
0x18000f6b7  mov     rdi, rax
0x18000f6ba  test    rax, rax
0x18000f6bd  jz      loc_18000FB17
0x18000f6c3  mov     rax, [rsi]
0x18000f6c6  lea     r8, aName_0; "name"
0x18000f6cd  mov     r9, [rsp+5E0h+Str]
0x18000f6d2  mov     rcx, rsi
0x18000f6d5  mov     rdx, [rsp+5E0h+var_598]
0x18000f6da  mov     rax, [rax+60h]
0x18000f6de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6e3  mov     ebx, eax
0x18000f6e5  test    eax, eax
0x18000f6e7  js      loc_18000FACB
0x18000f6ed  mov     rax, [rsi]
0x18000f6f0  lea     r8, aId; "id"
  ... truncated ...
```
