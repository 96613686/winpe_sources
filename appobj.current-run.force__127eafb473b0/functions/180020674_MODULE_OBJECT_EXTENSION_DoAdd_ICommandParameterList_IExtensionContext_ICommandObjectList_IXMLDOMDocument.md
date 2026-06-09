# MODULE_OBJECT_EXTENSION::DoAdd(ICommandParameterList *,IExtensionContext *,ICommandObjectList *,IXMLDOMDocument *)

- ea: `0x180020674`
- end: `0x180020fd1`
- name: `?DoAdd@MODULE_OBJECT_EXTENSION@@AEAAJPEAVICommandParameterList@@PEAVIExtensionContext@@PEAVICommandObjectList@@PEAUIXMLDOMDocument@@@Z`
- size: `2397`
- prototype: `int(MODULE_OBJECT_EXTENSION *__hidden this, struct ICommandParameterList *, struct IExtensionContext *, struct ICommandObjectList *, struct IXMLDOMDocument *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180021b60`

## callees

- `0x180001044`
- `0x180001fb0`
- `0x18001fe08`
- `0x180020674`
- `0x180021f7c`
- `0x1800221e0`
- `0x180022394`
- `0x18002a6cc`
- `0x18002b564`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002090e`
- `msvcrt!_wcsicmp` at `0x180020bd4`
- `msvcrt!_wcsicmp` at `0x180020cad`
- `msvcrt!_wcsicmp` at `0x180020cc5`
- `msvcrt!_wcsicmp` at `0x180020cdd`
- `msvcrt!_wcsicmp` at `0x180020d58`
- `msvcrt!_wcsicmp` at `0x18002090e`
- `msvcrt!_wcsicmp` at `0x180020bd4`
- `msvcrt!_wcsicmp` at `0x180020cad`
- `msvcrt!_wcsicmp` at `0x180020cc5`
- `msvcrt!_wcsicmp` at `0x180020cdd`
- `msvcrt!_wcsicmp` at `0x180020d58`

## string_xrefs

- `0x180020c10`: `ProtocolSupportModule`
- `0x180020cd3`: `DynamicCompressionModule`

## pseudocode

```c
__int64 __fastcall MODULE_OBJECT_EXTENSION::DoAdd(
        MODULE_OBJECT_EXTENSION *this,
        struct ICommandParameterList *a2,
        struct IExtensionContext *a3,
        struct ICommandObjectList *a4,
        struct IXMLDOMDocument *a5)
{
  struct ICommandObjectList *v7; // r13
  struct INativeConfigurationElement *v8; // r12
  MODULE_OBJECT *v9; // rsi
  APP_OBJECT_UTILS *v10; // rcx
  int ModulesConfigurationForApp; // ebx
  int v12; // eax
  APP_OBJECT_UTILS *v13; // rcx
  int v14; // r9d
  const unsigned __int16 *v15; // r14
  unsigned __int16 *v16; // r15
  __int64 v17; // r8
  unsigned __int16 *v18; // rax
  __int64 v19; // rdx
  wchar_t *v20; // r14
  int GlobalModulesConfiguration; // eax
  MODULE_OBJECT_EXTENSION *v22; // rcx
  const unsigned __int16 *v23; // r8
  int CollectionElementByKey; // eax
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // rax
  MODULE_OBJECT *v28; // rax
  MODULE_OBJECT_EXTENSION *v29; // rcx
  const unsigned __int16 *v30; // r8
  int v31; // eax
  MODULE_OBJECT_EXTENSION *v32; // rcx
  const unsigned __int16 *v33; // r8
  unsigned int v34; // ebx
  int v35; // eax
  MODULE_OBJECT_EXTENSION *v36; // rcx
  const unsigned __int16 *v37; // r8
  unsigned int v38; // r15d
  int v39; // eax
  unsigned int v40; // ecx
  MODULE_OBJECT_EXTENSION *v41; // rcx
  const unsigned __int16 *v42; // r8
  const unsigned __int16 *v43; // r9
  int v44; // eax
  __int64 v45; // rax
  unsigned int v46; // r8d
  struct INativePropertyException *v47; // r14
  struct INativeConfigurationElement **v49; // [rsp+20h] [rbp-E0h]
  struct INativeConfigurationElement **v50; // [rsp+20h] [rbp-E0h]
  struct INativeConfigurationElement **v51; // [rsp+20h] [rbp-E0h]
  unsigned int v52; // [rsp+50h] [rbp-B0h] BYREF
  struct INativeConfigurationElementCollection *v53; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v54[2]; // [rsp+60h] [rbp-A0h] BYREF
  struct INativePropertyException *v55; // [rsp+70h] [rbp-90h] BYREF
  struct ICommandParameterList *v56; // [rsp+78h] [rbp-88h] BYREF
  __int64 v57; // [rsp+80h] [rbp-80h] BYREF
  struct INativeConfigurationElement *v58; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v59; // [rsp+90h] [rbp-70h] BYREF
  struct INativeConfigurationElement *v60; // [rsp+98h] [rbp-68h] BYREF
  struct INativeSectionException *v61; // [rsp+A0h] [rbp-60h] BYREF
  struct INativeConfigurationElement *v62; // [rsp+A8h] [rbp-58h] BYREF
  struct ICommandObjectList *v63; // [rsp+B0h] [rbp-50h]
  __int64 v64; // [rsp+B8h] [rbp-48h] BYREF
  struct INativeConfigurationElement *v65; // [rsp+C0h] [rbp-40h] BYREF
  struct INativeConfigurationElement **v66; // [rsp+C8h] [rbp-38h]
  _BYTE v67[32]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int64 v68; // [rsp+F0h] [rbp-10h]
  int v69; // [rsp+F8h] [rbp-8h]
  __int16 v70; // [rsp+FCh] [rbp-4h]
  int v71; // [rsp+100h] [rbp+0h]
  _BYTE v72[32]; // [rsp+108h] [rbp+8h] BYREF
  wchar_t *String1; // [rsp+128h] [rbp+28h]
  int v74; // [rsp+130h] [rbp+30h]
  __int16 v75; // [rsp+134h] [rbp+34h]
  int v76; // [rsp+138h] [rbp+38h]
  _BYTE v77[32]; // [rsp+140h] [rbp+40h] BYREF
  wchar_t *v78; // [rsp+160h] [rbp+60h]
  int v79; // [rsp+168h] [rbp+68h]
  __int16 v80; // [rsp+16Ch] [rbp+6Ch]
  int v81; // [rsp+170h] [rbp+70h]
  _BYTE v82[32]; // [rsp+178h] [rbp+78h] BYREF
  __int16 *v83; // [rsp+198h] [rbp+98h]
  int v84; // [rsp+1A0h] [rbp+A0h]
  __int16 v85; // [rsp+1A4h] [rbp+A4h]
  int v86; // [rsp+1A8h] [rbp+A8h]
  __int16 v87; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v88[510]; // [rsp+1B2h] [rbp+B2h] BYREF
  __int16 v89; // [rsp+3B0h] [rbp+2B0h] BYREF
  _BYTE v90[510]; // [rsp+3B2h] [rbp+2B2h] BYREF
  __int16 v91; // [rsp+5B0h] [rbp+4B0h] BYREF
  _BYTE v92[510]; // [rsp+5B2h] [rbp+4B2h] BYREF
  __int16 v93; // [rsp+7B0h] [rbp+6B0h] BYREF
  _BYTE v94[510]; // [rsp+7B2h] [rbp+6B2h] BYREF

  v63 = a4;
  v66 = (struct INativeConfigurationElement **)a5;
  v64 = 0;
  v7 = a4;
  memset_0(v88, 0, sizeof(v88));
  v80 = 256;
  v78 = (wchar_t *)&v87;
  v79 = 512;
  v81 = 0;
  v87 = 0;
  memset_0(v90, 0, sizeof(v90));
  v84 = 512;
  v83 = &v89;
  v85 = 256;
  v86 = 0;
  v89 = 0;
  memset_0(v92, 0, sizeof(v92));
  v74 = 512;
  String1 = (wchar_t *)&v91;
  v75 = 256;
  v76 = 0;
  v91 = 0;
  memset_0(v94, 0, sizeof(v94));
  v69 = 512;
  v68 = (unsigned __int64)&v93;
  v70 = 256;
  v8 = 0;
  v71 = 0;
  v9 = 0;
  v93 = 0;
  v65 = 0;
  v53 = 0;
  v60 = 0;
  v62 = 0;
  v58 = 0;
  v55 = 0;
  v57 = 0;
  v61 = 0;
  v52 = 0;
  v59 = 0;
  v56 = 0;
  *(_OWORD *)v54 = 0;
  if ( !a3 || !a2 || !v7 )
  {
    ModulesConfigurationForApp = -2147024809;
    goto LABEL_75;
  }
  ModulesConfigurationForApp = (*(__int64 (__fastcall **)(struct ICommandParameterList *, struct ICommandParameterList **))(*(_QWORD *)a2 + 80LL))(
                                 a2,
                                 &v56);
  if ( ModulesConfigurationForApp < 0 )
    goto LABEL_77;
  v12 = APP_OBJECT_UTILS::PopParameter(v10, a3, v56, L"MODULE.NAME", (struct STRU *)v77, 0, 1);
  ModulesConfigurationForApp = v12;
  if ( v12 == -2147023483 )
  {
    v12 = APP_OBJECT_UTILS::PopParameter(v13, a3, v56, L"name", (struct STRU *)v77, 1, 1);
    ModulesConfigurationForApp = v12;
  }
  if ( v12 < 0 )
    goto LABEL_77;
  ModulesConfigurationForApp = APP_OBJECT_UTILS::PopParameter(v13, a3, v56, L"APP.NAME", (struct STRU *)v67, 0, 1);
  if ( (int)(ModulesConfigurationForApp + 0x80000000) >= 0 && ModulesConfigurationForApp != -2147023483 )
    goto LABEL_77;
  v15 = (const unsigned __int16 *)(v68 & -(__int64)(v71 != 0));
  ModulesConfigurationForApp = MODULE_OBJECT_EXTENSION::GetModulesConfigurationForApp(
                                 (MODULE_OBJECT_EXTENSION *)0x80000000LL,
                                 v15,
                                 a3,
                                 v14,
                                 &v65,
                                 (struct STRU *)v82,
                                 &v60,
                                 (struct STRU *)v72,
                                 &v61);
  v16 = String1;
  if ( v76 && _wcsicmp(String1, v15) )
  {
    ModulesConfigurationForApp = -2147024846;
    v54[0] = L"APP";
    v17 = 3221226508LL;
    v18 = L"ADD";
LABEL_13:
    v54[1] = v18;
    v19 = (unsigned int)ModulesConfigurationForApp;
LABEL_14:
    (*(void (__fastcall **)(struct IExtensionContext *, __int64, __int64, unsigned __int16 **, _DWORD))(*(_QWORD *)a3 + 144LL))(
      a3,
      v19,
      v17,
      v54,
      0);
    goto LABEL_77;
  }
  if ( ModulesConfigurationForApp >= 0 )
  {
    ModulesConfigurationForApp = (*(__int64 (__fastcall **)(struct ICommandParameterList *, const unsigned __int16 *, __int64 *))(*(_QWORD *)v56 + 40LL))(
                                   v56,
                                   L"type",
                                   &v64);
    if ( (int)(ModulesConfigurationForApp + 0x80000000) >= 0 && ModulesConfigurationForApp != -2147023483 )
      goto LABEL_77;
    v20 = v78;
    if ( !v64 )
    {
      GlobalModulesConfiguration = MODULE_OBJECT_EXTENSION::GetGlobalModulesConfiguration(
                                     (MODULE_OBJECT_EXTENSION *)0x80000000LL,
                                     a3,
                                     &v62,
                                     &v61);
      v8 = v62;
      ModulesConfigurationForApp = GlobalModulesConfiguration;
      if ( GlobalModulesConfiguration < 0 )
        goto LABEL_77;
      ModulesConfigurationForApp = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, struct INativeConfigurationElementCollection **))(*(_QWORD *)v62 + 40LL))(
                                     v62,
                                     &v53);
      if ( ModulesConfigurationForApp < 0 )
        goto LABEL_77;
      CollectionElementByKey = MODULE_OBJECT_EXTENSION::FindCollectionElementByKey(v22, v53, v23, v20, v49, 0, &v55);
      v25 = 2147943568LL;
      ModulesConfigurationForApp = CollectionElementByKey;
      if ( CollectionElementByKey == -2147023728 )
      {
        v26 = 3221226500LL;
LABEL_29:
        v27 = *(_QWORD *)a3;
        LODWORD(v49) = 0;
        v54[1] = 0;
        v54[0] = v20;
        (*(void (__fastcall **)(struct IExtensionContext *, __int64, __int64, unsigned __int16 **, struct INativeConfigurationElement **))(v27 + 144))(
          a3,
          v25,
          v26,
          v54,
          v49);
        goto LABEL_75;
      }
      if ( CollectionElementByKey < 0 )
        goto LABEL_75;
      (*(void (__fastcall **)(struct INativeConfigurationElementCollection *))(*(_QWORD *)v53 + 16LL))(v53);
      v53 = 0;
    }
    ModulesConfigurationForApp = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, struct INativeConfigurationElementCollection **))(*(_QWORD *)v60 + 40LL))(
                                   v60,
                                   &v53);
    if ( ModulesConfigurationForApp >= 0 )
    {
      ModulesConfigurationForApp = (*(__int64 (__fastcall **)(struct INativeConfigurationElementCollection *, const unsigned __int16 *, struct INativeConfigurationElement **))(*(_QWORD *)v53 + 48LL))(
                                     v53,
                                     L"add",
                                     &v58);
      if ( ModulesConfigurationForApp >= 0 )
      {
        if ( !v58 )
        {
          ModulesConfigurationForApp = -2147467261;
          goto LABEL_75;
        }
        v28 = (MODULE_OBJECT *)operator new(0xD8u);
        if ( v28 && (v9 = MODULE_OBJECT::MODULE_OBJECT(v28, v58, v60)) != 0 )
        {
          ModulesConfigurationForApp = (*(__int64 (__fastcall **)(struct IExtensionContext *, struct INativeConfigurationElement *, const unsigned __int16 *, wchar_t *))(*(_QWORD *)a3 + 96LL))(
                                         a3,
                                         v58,
                                         L"name",
                                         v20);
          if ( ModulesConfigurationForApp >= 0 )
          {
            v49 = v66;
            ModulesConfigurationForApp = (*(__int64 (__fastcall **)(struct IExtensionContext *, MODULE_OBJECT *, struct ICommandParameterList *, _QWORD))(*(_QWORD *)a3 + 168LL))(
                                           a3,
                                           v9,
                                           v56,
                                           0);
            if ( ModulesConfigurationForApp >= 0 )
            {
              if ( !_wcsicmp(v20, L"IsapiFilterModule") )
              {
                v52 = 0;
                v31 = MODULE_OBJECT_EXTENSION::FindCollectionElementByKey(
                        v29,
                        v53,
                        v30,
                        L"BasicAuthenticationModule",
                        v49,
                        &v52,
                        &v55);
                v34 = v52;
                v52 = 0;
                if ( v31 < 0 )
                  v34 = -1;
                v35 = MODULE_OBJECT_EXTENSION::FindCollectionElementByKey(
                        v32,
                        v53,
                        v33,
                        L"ProtocolSupportModule",
                        v50,
                        &v52,
                        &v55);
                v38 = v52;
                v52 = 0;
                if ( v35 < 0 )
                  v38 = -1;
                v39 = MODULE_OBJECT_EXTENSION::FindCollectionElementByKey(
                        v36,
                        v53,
                        v37,
                        L"HttpLoggingModule",
                        v51,
                        &v52,
                        &v55);
                v40 = v52;
                if ( v39 < 0 )
                  v40 = -1;
                if ( v34 >= v38 )
                  v34 = v38;
                else
                  v38 = v34;
                v7 = v63;
                if ( v38 >= v40 )
                  v34 = v40;
                goto LABEL_59;
              }
              if ( _wcsicmp(v20, L"BasicAuthenticationModule") && _wcsicmp(v20, L"IsapiModule") )
              {
                if ( _wcsicmp(v20, L"DynamicCompressionModule") )
                {
                  if ( _wcsicmp(v20, L"WindowsAuthenticationModule") )
                    goto LABEL_65;
                  v43 = L"WindowsAuthentication";
                }
                else
                {
                  v43 = L"IsapiFilterModule";
                }
              }
              else
              {
                v43 = L"HttpLoggingModule";
              }
              if ( (int)MODULE_OBJECT_EXTENSION::FindCollectionElementByKey(v41, v53, v42, v43, v49, &v52, &v55) >= 0 )
              {
                v34 = v52;
LABEL_59:
                v44 = (*(__int64 (__fastcall **)(struct INativeConfigurationElementCollection *, struct INativeConfigurationElement *, _QWORD, __int64 *))(*(_QWORD *)v53 + 56LL))(
                        v53,
                        v58,
                        v34,
                        &v57);
                ModulesConfigurationForApp = v44;
                if ( v44 >= 0 )
                {
                  ModulesConfigurationForApp = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int16 *, _QWORD))(*(_QWORD *)a3 + 208LL))(
                                                 a3,
                                                 v83,
                                                 0);
                  if ( ModulesConfigurationForApp >= 0 )
                  {
                    v54[1] = v20;
                    v54[0] = L"MODULE";
                    ModulesConfigurationForApp = APP_OBJECT_UTILS::AddStatusObject(
                                                   (APP_OBJECT_UTILS *)L"MODULE",
                                                   v7,
                                                   v46,
                                                   (const unsigned __int16 **const)v54);
                    if ( ModulesConfigurationForApp >= 0 )
                      ModulesConfigurationForApp = 0;
                  }
                  goto LABEL_75;
                }
                v25 = 2147942583LL;
                if ( v44 != -2147024713 )
                {
                  if ( v57 )
                  {
                    (*(void (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v57 + 24LL))(v57, &v59);
                    if ( v59 )
                    {
                      v54[1] = v59;
                      v45 = *(_QWORD *)a3;
                      v54[0] = L"MODULE";
                      LODWORD(v49) = 0;
                      (*(void (__fastcall **)(struct IExtensionContext *, _QWORD, __int64, unsigned __int16 **, struct INativeConfigurationElement **))(v45 + 144))(
                        a3,
                        (unsigned int)ModulesConfigurationForApp,
                        3221226480LL,
                        v54,
                        v49);
                    }
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
                    v57 = 0;
                  }
                  goto LABEL_75;
                }
                v26 = 3221226483LL;
                goto LABEL_29;
              }
LABEL_65:
              v34 = -1;
              goto LABEL_59;
            }
          }
        }
        else
        {
          ModulesConfigurationForApp = -2147024888;
        }
      }
    }
LABEL_75:
    v47 = v55;
    if ( v55 )
    {
      LODWORD(v49) = 0;
      (*(void (__fastcall **)(struct IExtensionContext *, _QWORD, const wchar_t *, struct INativePropertyException *, struct INativeConfigurationElement **))(*(_QWORD *)a3 + 120LL))(
        a3,
        (unsigned int)ModulesConfigurationForApp,
        &Str,
        v55,
        v49);
      (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v47 + 16LL))(v47);
    }
    goto LABEL_77;
  }
  if ( v61 )
  {
    (*(void (__fastcall **)(struct IExtensionContext *, _QWORD, const wchar_t *, struct INativeSectionException *, _DWORD))(*(_QWORD *)a3 + 112LL))(
      a3,
      (unsigned int)ModulesConfigurationForApp,
      L"MODULE",
      v61,
      0);
  }
  else
  {
    if ( ModulesConfigurationForApp == -2147024828 )
    {
      ModulesConfigurationForApp = -2147467259;
      v54[0] = L"APP";
      v17 = 3221226475LL;
      v18 = L"SET";
      goto LABEL_13;
    }
    v19 = 2147942402LL;
    if ( ModulesConfigurationForApp == -2147024894 )
    {
      v54[1] = v16;
      v54[0] = L"APP";
      v17 = 3221226521LL;
      goto LABEL_14;
    }
  }
LABEL_77:
  if ( v57 )
  {
    (*(void (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v57 + 24LL))(v57, &v59);
    (*(void (__fastcall **)(struct IExtensionContext *, _QWORD, unsigned __int16 *, _QWORD))(*(_QWORD *)a3 + 128LL))(
      a3,
      (unsigned int)ModulesConfigurationForApp,
      v59,
      0);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
    v57 = 0;
  }
  if ( v53 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElementCollection *))(*(_QWORD *)v53 + 16LL))(v53);
    v53 = 0;
  }
  if ( v60 )
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v60 + 16LL))(v60);
  if ( v8 )
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v8 + 16LL))(v8);
  if ( v58 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v58 + 16LL))(v58);
    v58 = 0;
  }
  if ( v61 )
    (*(void (__fastcall **)(struct INativeSectionException *))(*(_QWORD *)v61 + 16LL))(v61);
  if ( v65 )
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v65 + 16LL))(v65);
  if ( v9 )
    (*(void (__fastcall **)(MODULE_OBJECT *))(*(_QWORD *)v9 + 16LL))(v9);
  if ( v56 )
  {
    (*(void (__fastcall **)(struct ICommandParameterList *))(*(_QWORD *)v56 + 16LL))(v56);
    v56 = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v67);
  BUFFER::~BUFFER((BUFFER *)v72);
  BUFFER::~BUFFER((BUFFER *)v82);
  BUFFER::~BUFFER((BUFFER *)v77);
  return (unsigned int)ModulesConfigurationForApp;
}

```

## disassembly

```asm
0x180020674  mov     [rsp-8+arg_0], rbx
0x180020679  push    rbp
0x18002067a  push    rsi
0x18002067b  push    rdi
0x18002067c  push    r12
0x18002067e  push    r13
0x180020680  push    r14
0x180020682  push    r15
0x180020684  lea     rbp, [rsp-8C0h]
0x18002068c  sub     rsp, 9C0h
0x180020693  mov     rax, cs:__security_cookie
0x18002069a  xor     rax, rsp
0x18002069d  mov     [rbp+8F0h+var_40], rax
0x1800206a4  mov     rax, [rbp+8F0h+arg_20]
0x1800206ab  lea     rcx, [rbp+8F0h+var_83E]; void *
0x1800206b2  mov     rdi, r8
0x1800206b5  mov     [rbp+8F0h+var_940], r9
0x1800206b9  mov     rbx, rdx
0x1800206bc  mov     [rbp+8F0h+var_928], rax
0x1800206c0  mov     r14d, 1FEh
0x1800206c6  xor     r15d, r15d
0x1800206c9  mov     r8d, r14d; Size
0x1800206cc  mov     [rbp+8F0h+var_938], r15
0x1800206d0  xor     edx, edx; Val
0x1800206d2  mov     r13, r9
0x1800206d5  call    memset_0
0x1800206da  lea     rax, [rbp+8F0h+var_840]
0x1800206e1  mov     [rbp+8F0h+var_884], 100h
0x1800206e7  lea     esi, [r14+2]
0x1800206eb  mov     [rbp+8F0h+var_890], rax
0x1800206ef  mov     r8d, r14d; Size
0x1800206f2  mov     [rbp+8F0h+var_888], esi
0x1800206f5  xor     edx, edx; Val
0x1800206f7  mov     [rbp+8F0h+var_880], r15d
0x1800206fb  lea     rcx, [rbp+8F0h+var_63E]; void *
0x180020702  mov     [rbp+8F0h+var_840], r15w
0x18002070a  call    memset_0
0x18002070f  lea     rax, [rbp+8F0h+var_640]
0x180020716  mov     [rbp+8F0h+var_850], esi
0x18002071c  mov     r8d, r14d; Size
0x18002071f  mov     [rbp+8F0h+var_858], rax
0x180020726  xor     edx, edx; Val
0x180020728  mov     [rbp+8F0h+var_84C], 100h
0x180020731  lea     rcx, [rbp+8F0h+var_43E]; void *
0x180020738  mov     [rbp+8F0h+var_848], r15d
0x18002073f  mov     [rbp+8F0h+var_640], r15w
0x180020747  call    memset_0
0x18002074c  lea     rax, [rbp+8F0h+var_440]
0x180020753  mov     [rbp+8F0h+var_8C0], esi
0x180020756  mov     r8d, r14d; Size
0x180020759  mov     [rbp+8F0h+String1], rax
0x18002075d  xor     edx, edx; Val
0x18002075f  mov     [rbp+8F0h+var_8BC], 100h
0x180020765  lea     rcx, [rbp+8F0h+var_23E]; void *
0x18002076c  mov     [rbp+8F0h+var_8B8], r15d
0x180020770  mov     [rbp+8F0h+var_440], r15w
0x180020778  call    memset_0
0x18002077d  mov     [rbp+8F0h+var_8F8], esi
0x180020780  lea     rax, [rbp+8F0h+var_240]
0x180020787  mov     [rbp+8F0h+var_900], rax
0x18002078b  xorps   xmm0, xmm0
0x18002078e  mov     [rbp+8F0h+var_8F4], 100h
0x180020794  mov     r12d, r15d
0x180020797  mov     [rbp+8F0h+var_8F0], r15d
0x18002079b  mov     esi, r15d
0x18002079e  mov     [rbp+8F0h+var_240], r15w
0x1800207a6  mov     [rbp+8F0h+var_930], r15
0x1800207aa  mov     [rsp+9F0h+var_998], r15
0x1800207af  mov     [rbp+8F0h+var_958], r15
0x1800207b3  mov     [rbp+8F0h+var_948], r15
0x1800207b7  mov     [rbp+8F0h+var_968], r15
0x1800207bb  mov     [rsp+9F0h+var_980], r15
0x1800207c0  mov     [rbp+8F0h+var_970], r15
0x1800207c4  mov     [rbp+8F0h+var_950], r15
0x1800207c8  mov     [rsp+9F0h+var_9A0], r15d
0x1800207cd  mov     [rbp+8F0h+var_960], r15
0x1800207d1  mov     [rsp+9F0h+var_978], r15
0x1800207d6  movups  xmmword ptr [rsp+9F0h+var_990], xmm0
0x1800207db  test    rdi, rdi
0x1800207de  jz      loc_180020E3F
0x1800207e4  test    rbx, rbx
0x1800207e7  jz      loc_180020E3F
0x1800207ed  test    r13, r13
0x1800207f0  jz      loc_180020E3F
0x1800207f6  mov     rax, [rbx]
0x1800207f9  lea     rdx, [rsp+9F0h+var_978]
0x1800207fe  mov     rcx, rbx
0x180020801  mov     rax, [rax+50h]
0x180020805  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002080a  mov     ebx, eax
0x18002080c  test    eax, eax
0x18002080e  js      loc_180020E82
0x180020814  mov     r8, [rsp+9F0h+var_978]; struct ICommandParameterList *
0x180020819  lea     rax, [rbp+8F0h+var_8B0]
0x18002081d  lea     r14d, [r15+1]
0x180020821  mov     rdx, rdi; struct IExtensionContext *
0x180020824  mov     dword ptr [rsp+9F0h+var_9C0], r14d; int
0x180020829  lea     r9, aModuleName_0; "MODULE.NAME"
0x180020830  mov     dword ptr [rsp+9F0h+var_9C8], r15d; int
0x180020835  mov     [rsp+9F0h+var_9D0], rax; struct STRU *
0x18002083a  call    ?PopParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAVSTRU@@HH@Z; APP_OBJECT_UTILS::PopParameter(IExtensionContext *,ICommandParameterList *,ushort const *,STRU *,int,int)
0x18002083f  mov     ebx, eax
0x180020841  cmp     eax, 80070585h
0x180020846  jnz     short loc_180020871
0x180020848  mov     r8, [rsp+9F0h+var_978]; struct ICommandParameterList *
0x18002084d  lea     rax, [rbp+8F0h+var_8B0]
0x180020851  mov     dword ptr [rsp+9F0h+var_9C0], r14d; int
0x180020856  lea     r9, aName_0; "name"
0x18002085d  mov     dword ptr [rsp+9F0h+var_9C8], r14d; int
0x180020862  mov     rdx, rdi; struct IExtensionContext *
0x180020865  mov     [rsp+9F0h+var_9D0], rax; struct STRU *
0x18002086a  call    ?PopParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAVSTRU@@HH@Z; APP_OBJECT_UTILS::PopParameter(IExtensionContext *,ICommandParameterList *,ushort const *,STRU *,int,int)
0x18002086f  mov     ebx, eax
0x180020871  test    eax, eax
0x180020873  js      loc_180020E82
0x180020879  mov     r8, [rsp+9F0h+var_978]; struct ICommandParameterList *
0x18002087e  lea     rax, [rbp+8F0h+var_920]
0x180020882  mov     dword ptr [rsp+9F0h+var_9C0], r14d; int
0x180020887  lea     r9, aAppName_0; "APP.NAME"
0x18002088e  mov     dword ptr [rsp+9F0h+var_9C8], r15d; int
0x180020893  mov     rdx, rdi; struct IExtensionContext *
0x180020896  mov     [rsp+9F0h+var_9D0], rax; struct STRU *
0x18002089b  call    ?PopParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAVSTRU@@HH@Z; APP_OBJECT_UTILS::PopParameter(IExtensionContext *,ICommandParameterList *,ushort const *,STRU *,int,int)
0x1800208a0  mov     ecx, 80000000h; this
0x1800208a5  mov     ebx, eax
0x1800208a7  add     eax, ecx
0x1800208a9  test    ecx, eax
0x1800208ab  jnz     short loc_1800208B9
0x1800208ad  cmp     ebx, 80070585h
0x1800208b3  jnz     loc_180020E82
0x1800208b9  mov     eax, [rbp+8F0h+var_8F0]
0x1800208bc  mov     r8, rdi; struct IExtensionContext *
0x1800208bf  neg     eax
0x1800208c1  lea     rax, [rbp+8F0h+var_950]
0x1800208c5  mov     [rsp+9F0h+var_9B0], rax; struct INativeSectionException **
0x1800208ca  sbb     r14, r14
0x1800208cd  and     r14, [rbp+8F0h+var_900]
0x1800208d1  lea     rax, [rbp+8F0h+var_8E8]
0x1800208d5  mov     [rsp+9F0h+var_9B8], rax; struct STRU *
0x1800208da  mov     rdx, r14; unsigned __int16 *
0x1800208dd  lea     rax, [rbp+8F0h+var_958]
0x1800208e1  mov     [rsp+9F0h+var_9C0], rax; struct INativeConfigurationElement **
0x1800208e6  lea     rax, [rbp+8F0h+var_878]
0x1800208ea  mov     [rsp+9F0h+var_9C8], rax; struct STRU *
0x1800208ef  lea     rax, [rbp+8F0h+var_930]
0x1800208f3  mov     [rsp+9F0h+var_9D0], rax; struct INativeConfigurationElement **
0x1800208f8  call    ?GetModulesConfigurationForApp@MODULE_OBJECT_EXTENSION@@AEAAJPEBGPEAVIExtensionContext@@HPEAPEAVINativeConfigurationSystem@@PEAVSTRU@@PEAPEAVINativeConfigurationElement@@3PEAPEAVINativeSectionException@@@Z; MODULE_OBJECT_EXTENSION::GetModulesConfigurationForApp(ushort const *,IExtensionContext *,int,INativeConfigurationSystem * *,STRU *,INativeConfigurationElement * *,STRU *,INativeSectionException * *)
0x1800208fd  mov     ebx, eax
0x1800208ff  mov     r15, [rbp+8F0h+String1]
0x180020903  cmp     [rbp+8F0h+var_8B8], esi
0x180020906  jz      short loc_180020961
0x180020908  mov     rdx, r14; String2
0x18002090b  mov     rcx, r15; String1
0x18002090e  call    cs:__imp__wcsicmp
0x180020914  test    eax, eax
0x180020916  jz      short loc_180020961
0x180020918  lea     rax, aApp_0; "APP"
0x18002091f  mov     ebx, 80070032h
0x180020924  mov     [rsp+9F0h+var_990], rax
0x180020929  mov     r8d, 0C000040Ch
0x18002092f  lea     rax, aAdd_0; "ADD"
0x180020936  mov     [rsp+9F0h+var_990+8], rax
0x18002093b  mov     edx, ebx
0x18002093d  mov     rax, [rdi]
0x180020940  lea     r9, [rsp+9F0h+var_990]
0x180020945  xor     r15d, r15d
0x180020948  mov     rcx, rdi
0x18002094b  mov     dword ptr [rsp+9F0h+var_9D0], r15d
0x180020950  mov     rax, [rax+90h]
0x180020957  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002095c  jmp     loc_180020E82
0x180020961  test    ebx, ebx
0x180020963  jns     loc_1800209EE
0x180020969  mov     rcx, [rbp+8F0h+var_950]
0x18002096d  test    rcx, rcx
0x180020970  jz      short loc_18002099A
0x180020972  mov     rax, [rdi]
0x180020975  lea     r8, aModule_0; "MODULE"
0x18002097c  xor     r15d, r15d
0x18002097f  mov     r9, rcx
0x180020982  mov     edx, ebx
0x180020984  mov     dword ptr [rsp+9F0h+var_9D0], r15d
0x180020989  mov     rcx, rdi
0x18002098c  mov     rax, [rax+70h]
0x180020990  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020995  jmp     loc_180020E82
0x18002099a  cmp     ebx, 80070044h
0x1800209a0  jnz     short loc_1800209C5
0x1800209a2  lea     rax, aApp_0; "APP"
0x1800209a9  mov     ebx, 80004005h
0x1800209ae  mov     [rsp+9F0h+var_990], rax
0x1800209b3  mov     r8d, 0C00003EBh
0x1800209b9  lea     rax, aSet_0; "SET"
0x1800209c0  jmp     loc_180020936
0x1800209c5  mov     edx, 80070002h
0x1800209ca  cmp     ebx, edx
0x1800209cc  jnz     loc_180020E7F
0x1800209d2  lea     rax, aApp_0; "APP"
0x1800209d9  mov     [rsp+9F0h+var_990+8], r15
0x1800209de  mov     [rsp+9F0h+var_990], rax
0x1800209e3  mov     r8d, 0C0000419h
0x1800209e9  jmp     loc_18002093D
0x1800209ee  mov     rcx, [rsp+9F0h+var_978]
0x1800209f3  lea     r8, [rbp+8F0h+var_938]
0x1800209f7  lea     rdx, aType; "type"
0x1800209fe  mov     rax, [rcx]
0x180020a01  mov     rax, [rax+28h]
0x180020a05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a0a  mov     ecx, 80000000h; this
0x180020a0f  mov     ebx, eax
0x180020a11  add     eax, ecx
0x180020a13  test    ecx, eax
0x180020a15  jnz     short loc_180020A23
0x180020a17  cmp     ebx, 80070585h
0x180020a1d  jnz     loc_180020E7F
0x180020a23  mov     r14, [rbp+8F0h+var_890]
0x180020a27  xor     r15d, r15d
0x180020a2a  cmp     [rbp+8F0h+var_938], r15
0x180020a2e  jnz     loc_180020AE7
0x180020a34  lea     r9, [rbp+8F0h+var_950]; struct INativeSectionException **
0x180020a38  mov     rdx, rdi; struct IExtensionContext *
0x180020a3b  lea     r8, [rbp+8F0h+var_948]; struct INativeConfigurationElement **
0x180020a3f  call    ?GetGlobalModulesConfiguration@MODULE_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEAPEAVINativeConfigurationElement@@PEAPEAVINativeSectionException@@@Z; MODULE_OBJECT_EXTENSION::GetGlobalModulesConfiguration(IExtensionContext *,INativeConfigurationElement * *,INativeSectionException * *)
0x180020a44  mov     r12, [rbp+8F0h+var_948]
0x180020a48  mov     ebx, eax
0x180020a4a  test    eax, eax
0x180020a4c  js      loc_180020E82
0x180020a52  mov     rax, [r12]
0x180020a56  lea     rdx, [rsp+9F0h+var_998]
0x180020a5b  mov     rcx, r12
0x180020a5e  mov     rax, [rax+28h]
0x180020a62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a67  mov     ebx, eax
0x180020a69  test    eax, eax
0x180020a6b  js      loc_180020E82
0x180020a71  mov     rdx, [rsp+9F0h+var_998]; struct INativeConfigurationElementCollection *
0x180020a76  lea     rax, [rsp+9F0h+var_980]
0x180020a7b  mov     [rsp+9F0h+var_9C0], rax; struct INativePropertyException **
0x180020a80  mov     r9, r14; unsigned __int16 *
0x180020a83  mov     [rsp+9F0h+var_9C8], r15; unsigned int *
0x180020a88  call    ?FindCollectionElementByKey@MODULE_OBJECT_EXTENSION@@AEAAJPEAVINativeConfigurationElementCollection@@PEBG1PEAPEAVINativeConfigurationElement@@PEAKPEAPEAVINativePropertyException@@@Z; MODULE_OBJECT_EXTENSION::FindCollectionElementByKey(INativeConfigurationElementCollection *,ushort const *,ushort const *,INativeConfigurationElement * *,ulong *,INativePropertyException * *)
0x180020a8d  mov     edx, 80070490h
0x180020a92  mov     ebx, eax
0x180020a94  cmp     eax, edx
0x180020a96  jnz     short loc_180020AC9
0x180020a98  mov     r8d, 0C0000404h
0x180020a9e  mov     rax, [rdi]
0x180020aa1  lea     r9, [rsp+9F0h+var_990]
0x180020aa6  mov     rcx, rdi
0x180020aa9  mov     dword ptr [rsp+9F0h+var_9D0], r15d
0x180020aae  mov     [rsp+9F0h+var_990+8], r15
0x180020ab3  mov     [rsp+9F0h+var_990], r14
0x180020ab8  mov     rax, [rax+90h]
0x180020abf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ac4  jmp     loc_180020E44
0x180020ac9  test    eax, eax
0x180020acb  js      loc_180020E44
0x180020ad1  mov     rcx, [rsp+9F0h+var_998]
0x180020ad6  mov     rax, [rcx]
0x180020ad9  mov     rax, [rax+10h]
0x180020add  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ae2  mov     [rsp+9F0h+var_998], r15
0x180020ae7  mov     rcx, [rbp+8F0h+var_958]
0x180020aeb  lea     rdx, [rsp+9F0h+var_998]
0x180020af0  mov     rax, [rcx]
0x180020af3  mov     rax, [rax+28h]
0x180020af7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020afc  mov     ebx, eax
0x180020afe  test    eax, eax
0x180020b00  js      loc_180020E44
0x180020b06  mov     rcx, [rsp+9F0h+var_998]
0x180020b0b  lea     r8, [rbp+8F0h+var_968]
0x180020b0f  lea     rdx, aAdd; "add"
0x180020b16  mov     rax, [rcx]
0x180020b19  mov     rax, [rax+30h]
0x180020b1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b22  mov     ebx, eax
0x180020b24  test    eax, eax
0x180020b26  js      loc_180020E44
0x180020b2c  cmp     [rbp+8F0h+var_968], r15
0x180020b30  jnz     short loc_180020B3C
0x180020b32  mov     ebx, 80004003h
0x180020b37  jmp     loc_180020E44
0x180020b3c  mov     ecx, 0D8h; Size
0x180020b41  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020b46  test    rax, rax
0x180020b49  jz      loc_180020E38
0x180020b4f  mov     r8, [rbp+8F0h+var_958]; struct INativeConfigurationElement *
0x180020b53  mov     rcx, rax; this
0x180020b56  mov     rdx, [rbp+8F0h+var_968]; struct INativeConfigurationElement *
0x180020b5a  call    ??0MODULE_OBJECT@@QEAA@PEAVINativeConfigurationElement@@0@Z; MODULE_OBJECT::MODULE_OBJECT(INativeConfigurationElement *,INativeConfigurationElement *)
0x180020b5f  mov     rsi, rax
0x180020b62  test    rax, rax
0x180020b65  jz      loc_180020E38
0x180020b6b  mov     rax, [rdi]
0x180020b6e  lea     r8, aName_0; "name"
0x180020b75  mov     rdx, [rbp+8F0h+var_968]
0x180020b79  mov     r9, r14
0x180020b7c  mov     rcx, rdi
0x180020b7f  mov     rax, [rax+60h]
  ... truncated ...
```
