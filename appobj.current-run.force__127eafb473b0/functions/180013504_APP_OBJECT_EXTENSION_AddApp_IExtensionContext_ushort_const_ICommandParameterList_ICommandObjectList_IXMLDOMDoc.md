# APP_OBJECT_EXTENSION::AddApp(IExtensionContext *,ushort const *,ICommandParameterList *,ICommandObjectList *,IXMLDOMDocument *)

- ea: `0x180013504`
- end: `0x180013d80`
- name: `?AddApp@APP_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEBGPEAVICommandParameterList@@PEAVICommandObjectList@@PEAUIXMLDOMDocument@@@Z`
- size: `2172`
- prototype: `int(APP_OBJECT_EXTENSION *__hidden this, struct IExtensionContext *, const unsigned __int16 *, struct ICommandParameterList *, struct ICommandObjectList *, struct IXMLDOMDocument *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180014690`

## callees

- `0x180001044`
- `0x180001fb0`
- `0x180002640`
- `0x180002e90`
- `0x1800134b8`
- `0x180013504`
- `0x180013d88`
- `0x180014ff0`
- `0x180015138`
- `0x18002a6cc`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800136f1`
- `msvcrt!_wcsicmp` at `0x180013729`
- `msvcrt!_wcsicmp` at `0x1800136f1`
- `msvcrt!_wcsicmp` at `0x180013729`

## string_xrefs

- `0x1800137a4`: `physicalPath`
- `0x1800137da`: `physicalPath`
- `0x180013b82`: `physicalPath`
- `0x180013b36`: `virtualDirectory`

## pseudocode

```c
__int64 __fastcall APP_OBJECT_EXTENSION::AddApp(
        APP_OBJECT_EXTENSION *this,
        struct IExtensionContext *a2,
        const unsigned __int16 *a3,
        struct ICommandParameterList *a4,
        struct ICommandObjectList *a5,
        struct IXMLDOMDocument *a6)
{
  struct APP_OBJECT *v8; // rdi
  int v10; // eax
  int v11; // ebx
  __int64 v12; // r8
  __int64 v13; // rdx
  int v14; // eax
  APP_OBJECT *v15; // rax
  APP_OBJECT *v16; // rax
  int v17; // eax
  APP_OBJECT_EXTENSION *v18; // rcx
  int v19; // eax
  int v20; // eax
  unsigned __int16 *v21; // rcx
  unsigned __int16 *v22; // rcx
  unsigned __int16 *v23; // rax
  __int64 v24; // rax
  APP_OBJECT_UTILS *v25; // rcx
  unsigned int v26; // r8d
  APP_OBJECT_UTILS *v27; // rcx
  unsigned int v28; // r8d
  __int64 v30; // [rsp+40h] [rbp-C0h] BYREF
  struct ICommandParameterList *v31; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v32[2]; // [rsp+50h] [rbp-B0h] BYREF
  struct INativeConfigurationElement *v33; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v34; // [rsp+68h] [rbp-98h] BYREF
  __int64 v35; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v36; // [rsp+78h] [rbp-88h] BYREF
  struct INativeConfigurationElement *v37; // [rsp+80h] [rbp-80h] BYREF
  __int64 v38; // [rsp+88h] [rbp-78h] BYREF
  __int64 v39; // [rsp+90h] [rbp-70h] BYREF
  wchar_t *String2; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v41; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v42; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 *v43; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 *v44; // [rsp+B8h] [rbp-48h] BYREF
  wchar_t *String1; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t *v46; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int16 *v47; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v48[32]; // [rsp+D8h] [rbp-28h] BYREF
  __int16 *v49; // [rsp+F8h] [rbp-8h]
  int v50; // [rsp+100h] [rbp+0h]
  __int16 v51; // [rsp+104h] [rbp+4h]
  int v52; // [rsp+108h] [rbp+8h]
  _BYTE v53[32]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 *v54; // [rsp+130h] [rbp+30h]
  int v55; // [rsp+138h] [rbp+38h]
  __int16 v56; // [rsp+13Ch] [rbp+3Ch]
  int v57; // [rsp+140h] [rbp+40h]
  __int16 v58; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v59[510]; // [rsp+152h] [rbp+52h] BYREF
  __int16 v60; // [rsp+350h] [rbp+250h] BYREF
  _BYTE v61[510]; // [rsp+352h] [rbp+252h] BYREF

  v34 = 0;
  v37 = 0;
  v33 = 0;
  v38 = 0;
  v30 = 0;
  v35 = 0;
  v8 = 0;
  v39 = 0;
  *(_OWORD *)v32 = 0;
  v41 = 0;
  v43 = 0;
  v47 = 0;
  v31 = 0;
  String2 = 0;
  String1 = 0;
  v42 = 0;
  v44 = 0;
  v46 = 0;
  v36 = 0;
  memset_0(v59, 0, sizeof(v59));
  v56 = 256;
  v54 = (unsigned __int16 *)&v58;
  v55 = 512;
  v58 = 0;
  v57 = 0;
  memset_0(v61, 0, sizeof(v61));
  v50 = 512;
  v49 = &v60;
  v51 = 256;
  v52 = 0;
  v60 = 0;
  if ( !a2 || !a3 || !a4 || !a5 )
  {
    v11 = -2147024809;
    goto LABEL_66;
  }
  v10 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, const unsigned __int16 *, wchar_t **))(*(_QWORD *)a4 + 40LL))(
          a4,
          L"SITE.NAME",
          &String2);
  v11 = v10;
  if ( v10 == -2147023483 )
  {
    v11 = -2147024894;
    v32[0] = L"SITE.NAME";
    v12 = 3221226486LL;
LABEL_7:
    v13 = (unsigned int)v11;
LABEL_8:
    (*(void (__fastcall **)(struct IExtensionContext *, __int64, __int64, unsigned __int16 **, _DWORD))(*(_QWORD *)a2 + 144LL))(
      a2,
      v13,
      v12,
      v32,
      0);
    goto LABEL_66;
  }
  if ( v10 < 0 )
    goto LABEL_66;
  v11 = (*(__int64 (__fastcall **)(struct IExtensionContext *, const unsigned __int16 *, wchar_t *, __int64 *, int))(*(_QWORD *)a2 + 64LL))(
          a2,
          L"SITE",
          String2,
          &v34,
          4);
  if ( v11 < 0 )
    goto LABEL_66;
  v11 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v34 + 80LL))(
          v34,
          L"SITE.NAME",
          &String1);
  if ( v11 < 0 )
    goto LABEL_66;
  if ( _wcsicmp(String1, String2) )
  {
    v11 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v34 + 80LL))(
            v34,
            L"SITE.ID",
            &v46);
    if ( v11 < 0 )
      goto LABEL_66;
    if ( _wcsicmp(v46, String2) )
    {
      v11 = -2147024846;
      v32[0] = L"SITE";
      v12 = 3221226508LL;
      v32[1] = L"ADD";
      goto LABEL_7;
    }
  }
  v11 = (*(__int64 (__fastcall **)(struct IExtensionContext *, struct ICommandParameterList **))(*(_QWORD *)a2 + 192LL))(
          a2,
          &v31);
  if ( v11 < 0 )
    goto LABEL_66;
  v11 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, struct ICommandParameterList *))(*(_QWORD *)a4 + 72LL))(
          a4,
          v31);
  if ( v11 < 0 )
    goto LABEL_66;
  v14 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, const unsigned __int16 *, unsigned __int16 **))(*(_QWORD *)v31 + 40LL))(
          v31,
          L"physicalPath",
          &v36);
  v11 = v14;
  if ( v14 < 0 )
  {
    if ( v14 != -2147023483 )
      goto LABEL_66;
  }
  else
  {
    v11 = STRU::Copy((STRU *)v53, v36);
    if ( v11 < 0 )
      goto LABEL_66;
    v11 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, const unsigned __int16 *))(*(_QWORD *)v31 + 48LL))(
            v31,
            L"physicalPath");
    if ( v11 < 0 )
      goto LABEL_66;
    v36 = v54;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, struct INativeConfigurationElement **))(*(_QWORD *)v34 + 48LL))(v34, &v37);
  if ( v11 < 0 )
    goto LABEL_66;
  v11 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 *))(*(_QWORD *)v37 + 40LL))(v37, &v38);
  if ( v11 < 0 )
    goto LABEL_66;
  v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, struct INativeConfigurationElement **))(*(_QWORD *)v38 + 48LL))(
          v38,
          L"application",
          &v33);
  if ( v11 < 0 )
    goto LABEL_66;
  v15 = (APP_OBJECT *)operator new(0xD8u);
  if ( !v15 || (v16 = APP_OBJECT::APP_OBJECT(v15, v33, v37), (v8 = v16) == 0) )
  {
    v11 = -2147024888;
    goto LABEL_66;
  }
  v11 = APP_OBJECT::Reset(v16);
  if ( v11 < 0 )
    goto LABEL_66;
  v17 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, const wchar_t *, __int64 *))(*(_QWORD *)v31 + 40LL))(
          v31,
          L"applicationPool",
          &v42);
  v11 = v17;
  if ( v17 == -2147023483 )
  {
    v19 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, const unsigned __int16 *, __int64 *))(*(_QWORD *)v31 + 40LL))(
            v31,
            L"APPPOOL.NAME",
            &v42);
    v11 = v19;
    if ( v19 < 0 )
    {
      if ( v19 != -2147023483 )
        goto LABEL_66;
      goto LABEL_35;
    }
    v17 = (*(__int64 (__fastcall **)(struct IExtensionContext *, struct INativeConfigurationElement *, const wchar_t *, __int64))(*(_QWORD *)a2 + 96LL))(
            a2,
            v33,
            L"applicationPool",
            v42);
    v11 = v17;
  }
  if ( v17 < 0 )
    goto LABEL_66;
LABEL_35:
  v11 = APP_OBJECT_EXTENSION::SetApp(v18, a2, v8, v31, 0, a6, 1);
  if ( v11 < 0 )
    goto LABEL_66;
  v20 = (*(__int64 (__fastcall **)(__int64, struct INativeConfigurationElement *, __int64, __int64 *))(*(_QWORD *)v38 + 56LL))(
          v38,
          v33,
          0xFFFFFFFFLL,
          &v30);
  v11 = v20;
  if ( v20 >= 0 )
  {
    v11 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v34 + 40LL))(v34, &v43);
    if ( v11 >= 0 )
    {
      v11 = APP_OBJECT::Create(v8, v43);
      if ( v11 >= 0 )
      {
        v11 = (*(__int64 (__fastcall **)(struct APP_OBJECT *, const unsigned __int16 *, unsigned __int16 **))(*(_QWORD *)v8 + 80LL))(
                v8,
                L"APP.NAME",
                &v44);
        if ( v11 >= 0 )
        {
          v11 = (*(__int64 (__fastcall **)(struct IExtensionContext *, unsigned __int16 *, _QWORD))(*(_QWORD *)a2 + 208LL))(
                  a2,
                  v43,
                  0);
          if ( v11 >= 0 )
          {
            v32[0] = L"APP";
            v32[1] = v44;
            v11 = APP_OBJECT_UTILS::AddStatusObject(v25, a5, v26, (const unsigned __int16 **const)v32);
            if ( v11 >= 0 )
            {
              if ( !v36 )
                goto LABEL_63;
              v11 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 *))(*(_QWORD *)v33 + 40LL))(
                      v33,
                      &v39);
              if ( v11 >= 0 )
              {
                v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v39 + 48LL))(
                        v39,
                        L"virtualDirectory",
                        &v35);
                if ( v11 >= 0 )
                {
                  v11 = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64, const unsigned __int16 *, const wchar_t *))(*(_QWORD *)a2 + 96LL))(
                          a2,
                          v35,
                          L"path",
                          L"/");
                  if ( v11 >= 0 )
                  {
                    v11 = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64, const unsigned __int16 *, unsigned __int16 *))(*(_QWORD *)a2 + 96LL))(
                            a2,
                            v35,
                            L"physicalPath",
                            v36);
                    if ( v11 >= 0 )
                    {
                      v11 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)v39 + 56LL))(
                              v39,
                              v35,
                              0xFFFFFFFFLL,
                              &v30);
                      if ( v11 < 0 )
                      {
                        if ( !v30 )
                          goto LABEL_66;
                        (*(void (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v30 + 24LL))(v30, &v41);
                        v22 = v41;
                        if ( v41 )
                        {
                          v23 = L"VDIR";
                          goto LABEL_44;
                        }
LABEL_45:
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
                        v30 = 0;
                        goto LABEL_66;
                      }
                      v11 = STRU::Copy((STRU *)v48, v44);
                      if ( v11 >= 0 )
                      {
                        v11 = STRU::Append((STRU *)v48, L"/");
                        if ( v11 >= 0 )
                        {
                          v32[0] = L"VDIR";
                          v11 = APP_OBJECT_UTILS::AddStatusObject(v27, a5, v28, (const unsigned __int16 **const)v32);
                          if ( v11 >= 0 )
LABEL_63:
                            v11 = 0;
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  else
  {
    if ( v20 == -2147024713 )
    {
      (*(void (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v33 + 64LL))(
        v33,
        L"path",
        &v47,
        0,
        0);
      v21 = L"Unknown";
      v32[1] = 0;
      v12 = 3221226483LL;
      v13 = 2147942583LL;
      if ( v47 )
        v21 = v47;
      v32[0] = v21;
      goto LABEL_8;
    }
    if ( v30 )
    {
      (*(void (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v30 + 24LL))(v30, &v41);
      v22 = v41;
      if ( v41 )
      {
        v23 = L"APP";
LABEL_44:
        v32[0] = v23;
        v24 = *(_QWORD *)a2;
        v32[1] = v22;
        (*(void (__fastcall **)(struct IExtensionContext *, _QWORD, __int64, unsigned __int16 **, _DWORD))(v24 + 144))(
          a2,
          (unsigned int)v11,
          3221226480LL,
          v32,
          0);
        goto LABEL_45;
      }
      goto LABEL_45;
    }
  }
LABEL_66:
  if ( v33 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v33 + 16LL))(v33);
    v33 = 0;
  }
  if ( v8 )
    (*(void (__fastcall **)(struct APP_OBJECT *))(*(_QWORD *)v8 + 16LL))(v8);
  if ( v34 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    v34 = 0;
  }
  if ( v37 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v37 + 16LL))(v37);
    v37 = 0;
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
  if ( v31 )
  {
    (*(void (__fastcall **)(struct ICommandParameterList *))(*(_QWORD *)v31 + 16LL))(v31);
    v31 = 0;
  }
  if ( v39 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    v39 = 0;
  }
  if ( v35 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    v35 = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v48);
  BUFFER::~BUFFER((BUFFER *)v53);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180013504  mov     [rsp-8+arg_0], rbx
0x180013509  push    rbp
0x18001350a  push    rsi
0x18001350b  push    rdi
0x18001350c  push    r12
0x18001350e  push    r13
0x180013510  push    r14
0x180013512  push    r15
0x180013514  lea     rbp, [rsp-460h]
0x18001351c  sub     rsp, 560h
0x180013523  mov     rax, cs:__security_cookie
0x18001352a  xor     rax, rsp
0x18001352d  mov     [rbp+490h+var_40], rax
0x180013534  mov     r15, [rbp+490h+arg_20]
0x18001353b  lea     rcx, [rbp+490h+var_43E]; void *
0x18001353f  mov     r12, [rbp+490h+arg_28]
0x180013546  xor     eax, eax
0x180013548  mov     rbx, r8
0x18001354b  mov     [rsp+590h+var_528], rax
0x180013550  mov     rsi, rdx
0x180013553  mov     [rbp+490h+var_510], rax
0x180013557  xorps   xmm0, xmm0
0x18001355a  mov     [rsp+590h+var_530], rax
0x18001355f  xor     edx, edx; Val
0x180013561  mov     [rbp+490h+var_508], rax
0x180013565  mov     r8d, 1FEh; Size
0x18001356b  mov     [rsp+590h+var_550], rax
0x180013570  mov     [rsp+590h+var_520], rax
0x180013575  mov     edi, eax
0x180013577  mov     [rbp+490h+var_500], rax
0x18001357b  mov     r14, r9
0x18001357e  movups  xmmword ptr [rsp+590h+var_540], xmm0
0x180013583  mov     [rbp+490h+var_4F0], rax
0x180013587  mov     [rbp+490h+var_4E0], rax
0x18001358b  mov     [rbp+490h+var_4C0], rax
0x18001358f  mov     [rsp+590h+var_548], rax
0x180013594  mov     [rbp+490h+String2], rax
0x180013598  mov     [rbp+490h+String1], rax
0x18001359c  mov     [rbp+490h+var_4E8], rax
0x1800135a0  mov     [rbp+490h+var_4D8], rax
0x1800135a4  mov     [rbp+490h+var_4C8], rax
0x1800135a8  mov     [rsp+590h+var_518], rax
0x1800135ad  call    memset_0
0x1800135b2  lea     rax, [rbp+490h+var_440]
0x1800135b6  mov     [rbp+490h+var_454], 100h
0x1800135bc  mov     r13d, 200h
0x1800135c2  mov     [rbp+490h+var_460], rax
0x1800135c6  xor     eax, eax
0x1800135c8  mov     [rbp+490h+var_458], r13d
0x1800135cc  xor     edx, edx; Val
0x1800135ce  mov     [rbp+490h+var_440], ax
0x1800135d2  lea     rcx, [rbp+490h+var_23E]; void *
0x1800135d9  mov     [rbp+490h+var_450], edi
0x1800135dc  lea     r8d, [r13-2]; Size
0x1800135e0  call    memset_0
0x1800135e5  mov     [rbp+490h+var_490], r13d
0x1800135e9  lea     rax, [rbp+490h+var_240]
0x1800135f0  xor     r13d, r13d
0x1800135f3  mov     [rbp+490h+var_498], rax
0x1800135f7  mov     [rbp+490h+var_48C], 100h
0x1800135fd  mov     [rbp+490h+var_488], r13d
0x180013601  mov     [rbp+490h+var_240], r13w
0x180013609  test    rsi, rsi
0x18001360c  jz      loc_180013C57
0x180013612  test    rbx, rbx
0x180013615  jz      loc_180013C57
0x18001361b  test    r14, r14
0x18001361e  jz      loc_180013C57
0x180013624  test    r15, r15
0x180013627  jz      loc_180013C57
0x18001362d  mov     rax, [r14]
0x180013630  lea     r8, [rbp+490h+String2]
0x180013634  lea     rdx, aSiteName; "SITE.NAME"
0x18001363b  mov     rcx, r14
0x18001363e  mov     rax, [rax+28h]
0x180013642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013647  mov     ebx, eax
0x180013649  cmp     eax, 80070585h
0x18001364e  jnz     short loc_18001368A
0x180013650  lea     rdx, aSiteName; "SITE.NAME"
0x180013657  mov     ebx, 80070002h
0x18001365c  mov     [rsp+590h+var_540], rdx
0x180013661  mov     r8d, 0C00003F6h
0x180013667  mov     edx, ebx
0x180013669  mov     rax, [rsi]
0x18001366c  lea     r9, [rsp+590h+var_540]
0x180013671  mov     rcx, rsi
0x180013674  mov     dword ptr [rsp+590h+var_570], r13d
0x180013679  mov     rax, [rax+90h]
0x180013680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013685  jmp     loc_180013C5C
0x18001368a  test    eax, eax
0x18001368c  js      loc_180013C5C
0x180013692  mov     rax, [rsi]
0x180013695  lea     r9, [rsp+590h+var_528]
0x18001369a  mov     r8, [rbp+490h+String2]
0x18001369e  lea     rdx, aSite_0; "SITE"
0x1800136a5  mov     rcx, rsi
0x1800136a8  mov     dword ptr [rsp+590h+var_570], 4
0x1800136b0  mov     rax, [rax+40h]
0x1800136b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800136b9  mov     ebx, eax
0x1800136bb  test    eax, eax
0x1800136bd  js      loc_180013C5C
0x1800136c3  mov     rcx, [rsp+590h+var_528]
0x1800136c8  lea     r8, [rbp+490h+String1]
0x1800136cc  lea     rdx, aSiteName; "SITE.NAME"
0x1800136d3  mov     rax, [rcx]
0x1800136d6  mov     rax, [rax+50h]
0x1800136da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800136df  mov     ebx, eax
0x1800136e1  test    eax, eax
0x1800136e3  js      loc_180013C5C
0x1800136e9  mov     rdx, [rbp+490h+String2]; String2
0x1800136ed  mov     rcx, [rbp+490h+String1]; String1
0x1800136f1  call    cs:__imp__wcsicmp
0x1800136f7  test    eax, eax
0x1800136f9  jz      short loc_18001375B
0x1800136fb  mov     rcx, [rsp+590h+var_528]
0x180013700  lea     r8, [rbp+490h+var_4C8]
0x180013704  lea     rdx, aSiteId; "SITE.ID"
0x18001370b  mov     rax, [rcx]
0x18001370e  mov     rax, [rax+50h]
0x180013712  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013717  mov     ebx, eax
0x180013719  test    eax, eax
0x18001371b  js      loc_180013C5C
0x180013721  mov     rdx, [rbp+490h+String2]; String2
0x180013725  mov     rcx, [rbp+490h+var_4C8]; String1
0x180013729  call    cs:__imp__wcsicmp
0x18001372f  test    eax, eax
0x180013731  jz      short loc_18001375B
0x180013733  lea     rax, aSite_0; "SITE"
0x18001373a  mov     ebx, 80070032h
0x18001373f  mov     [rsp+590h+var_540], rax
0x180013744  mov     r8d, 0C000040Ch
0x18001374a  lea     rax, aAdd_0; "ADD"
0x180013751  mov     [rsp+590h+var_540+8], rax
0x180013756  jmp     loc_180013667
0x18001375b  mov     rax, [rsi]
0x18001375e  lea     rdx, [rsp+590h+var_548]
0x180013763  mov     rcx, rsi
0x180013766  mov     rax, [rax+0C0h]
0x18001376d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013772  mov     ebx, eax
0x180013774  test    eax, eax
0x180013776  js      loc_180013C5C
0x18001377c  mov     rax, [r14]
0x18001377f  mov     rcx, r14
0x180013782  mov     rdx, [rsp+590h+var_548]
0x180013787  mov     rax, [rax+48h]
0x18001378b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013790  mov     ebx, eax
0x180013792  test    eax, eax
0x180013794  js      loc_180013C5C
0x18001379a  mov     rcx, [rsp+590h+var_548]
0x18001379f  lea     r8, [rsp+590h+var_518]
0x1800137a4  lea     rdx, aPhysicalpath; "physicalPath"
0x1800137ab  mov     rax, [rcx]
0x1800137ae  mov     rax, [rax+28h]
0x1800137b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137b7  mov     ebx, eax
0x1800137b9  test    eax, eax
0x1800137bb  js      short loc_180013808
0x1800137bd  mov     rdx, [rsp+590h+var_518]; unsigned __int16 *
0x1800137c2  lea     rcx, [rbp+490h+var_480]; this
0x1800137c6  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800137cb  mov     ebx, eax
0x1800137cd  test    eax, eax
0x1800137cf  js      loc_180013C5C
0x1800137d5  mov     rcx, [rsp+590h+var_548]
0x1800137da  lea     rdx, aPhysicalpath; "physicalPath"
0x1800137e1  mov     rax, [rcx]
0x1800137e4  mov     rax, [rax+30h]
0x1800137e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137ed  mov     ebx, eax
0x1800137ef  test    eax, eax
0x1800137f1  js      loc_180013C5C
0x1800137f7  mov     rax, [rbp+490h+var_460]
0x1800137fb  mov     r14d, 80070585h
0x180013801  mov     [rsp+590h+var_518], rax
0x180013806  jmp     short loc_180013817
0x180013808  mov     r14d, 80070585h
0x18001380e  cmp     eax, r14d
0x180013811  jnz     loc_180013C5C
0x180013817  mov     rcx, [rsp+590h+var_528]
0x18001381c  lea     rdx, [rbp+490h+var_510]
0x180013820  mov     rax, [rcx]
0x180013823  mov     rax, [rax+30h]
0x180013827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001382c  mov     ebx, eax
0x18001382e  test    eax, eax
0x180013830  js      loc_180013C5C
0x180013836  mov     rcx, [rbp+490h+var_510]
0x18001383a  lea     rdx, [rbp+490h+var_508]
0x18001383e  mov     rax, [rcx]
0x180013841  mov     rax, [rax+28h]
0x180013845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001384a  mov     ebx, eax
0x18001384c  test    eax, eax
0x18001384e  js      loc_180013C5C
0x180013854  mov     rcx, [rbp+490h+var_508]
0x180013858  lea     r8, [rsp+590h+var_530]
0x18001385d  lea     rdx, aApplication; "application"
0x180013864  mov     rax, [rcx]
0x180013867  mov     rax, [rax+30h]
0x18001386b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013870  mov     ebx, eax
0x180013872  test    eax, eax
0x180013874  js      loc_180013C5C
0x18001387a  mov     ecx, 0D8h; Size
0x18001387f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013884  test    rax, rax
0x180013887  jz      loc_180013C50
0x18001388d  mov     r8, [rbp+490h+var_510]; struct INativeConfigurationElement *
0x180013891  mov     rcx, rax; this
0x180013894  mov     rdx, [rsp+590h+var_530]; struct INativeConfigurationElement *
0x180013899  call    ??0APP_OBJECT@@QEAA@PEAVINativeConfigurationElement@@0@Z; APP_OBJECT::APP_OBJECT(INativeConfigurationElement *,INativeConfigurationElement *)
0x18001389e  mov     rdi, rax
0x1800138a1  test    rax, rax
0x1800138a4  jz      loc_180013C50
0x1800138aa  mov     rcx, rax; this
0x1800138ad  call    ?Reset@APP_OBJECT@@QEAAJXZ; APP_OBJECT::Reset(void)
0x1800138b2  mov     ebx, eax
0x1800138b4  test    eax, eax
0x1800138b6  js      loc_180013C5C
0x1800138bc  mov     rcx, [rsp+590h+var_548]
0x1800138c1  lea     r8, [rbp+490h+var_4E8]
0x1800138c5  lea     rdx, aApplicationpoo_1; "applicationPool"
0x1800138cc  mov     rax, [rcx]
0x1800138cf  mov     rax, [rax+28h]
0x1800138d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138d8  mov     ebx, eax
0x1800138da  cmp     eax, r14d
0x1800138dd  jnz     short loc_180013922
0x1800138df  mov     rcx, [rsp+590h+var_548]
0x1800138e4  lea     r8, [rbp+490h+var_4E8]
0x1800138e8  lea     rdx, aApppoolName; "APPPOOL.NAME"
0x1800138ef  mov     rax, [rcx]
0x1800138f2  mov     rax, [rax+28h]
0x1800138f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138fb  mov     ebx, eax
0x1800138fd  test    eax, eax
0x1800138ff  js      short loc_18001392B
0x180013901  mov     rax, [rsi]
0x180013904  lea     r8, aApplicationpoo_1; "applicationPool"
0x18001390b  mov     r9, [rbp+490h+var_4E8]
0x18001390f  mov     rcx, rsi
0x180013912  mov     rdx, [rsp+590h+var_530]
0x180013917  mov     rax, [rax+60h]
0x18001391b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013920  mov     ebx, eax
0x180013922  test    eax, eax
0x180013924  jns     short loc_180013934
0x180013926  jmp     loc_180013C5C
0x18001392b  cmp     eax, r14d
0x18001392e  jnz     loc_180013C5C
0x180013934  mov     r9, [rsp+590h+var_548]; struct ICommandParameterList *
0x180013939  mov     r8, rdi; struct APP_OBJECT *
0x18001393c  mov     [rsp+590h+var_560], 1; int
0x180013944  mov     rdx, rsi; struct IExtensionContext *
0x180013947  mov     [rsp+590h+var_568], r12; struct IXMLDOMDocument *
0x18001394c  mov     [rsp+590h+var_570], r13; struct ICommandObjectList *
0x180013951  call    ?SetApp@APP_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEAVAPP_OBJECT@@PEAVICommandParameterList@@PEAVICommandObjectList@@PEAUIXMLDOMDocument@@H@Z; APP_OBJECT_EXTENSION::SetApp(IExtensionContext *,APP_OBJECT *,ICommandParameterList *,ICommandObjectList *,IXMLDOMDocument *,int)
0x180013956  mov     ebx, eax
0x180013958  test    eax, eax
0x18001395a  js      loc_180013C5C
0x180013960  mov     rcx, [rbp+490h+var_508]
0x180013964  lea     r9, [rsp+590h+var_550]
0x180013969  mov     rdx, [rsp+590h+var_530]
0x18001396e  or      r14d, 0FFFFFFFFh
0x180013972  mov     r8d, r14d
0x180013975  mov     rax, [rcx]
0x180013978  mov     rax, [rax+38h]
0x18001397c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013981  mov     ebx, eax
0x180013983  test    eax, eax
0x180013985  jns     loc_180013A5B
0x18001398b  mov     r14d, 800700B7h
0x180013991  cmp     eax, r14d
0x180013994  jnz     short loc_1800139E4
0x180013996  mov     rcx, [rsp+590h+var_530]
0x18001399b  lea     r8, [rbp+490h+var_4C0]
0x18001399f  xor     r9d, r9d
0x1800139a2  mov     [rsp+590h+var_570], r13
0x1800139a7  lea     rdx, aPath_1; "path"
0x1800139ae  mov     rax, [rcx]
0x1800139b1  mov     rax, [rax+40h]
0x1800139b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800139ba  mov     rax, [rbp+490h+var_4C0]
0x1800139be  lea     rcx, aUnknown_0; "Unknown"
0x1800139c5  test    rax, rax
0x1800139c8  mov     [rsp+590h+var_540+8], r13
0x1800139cd  mov     r8d, 0C00003F3h
0x1800139d3  mov     edx, r14d
0x1800139d6  cmovnz  rcx, rax
0x1800139da  mov     [rsp+590h+var_540], rcx
0x1800139df  jmp     loc_180013669
0x1800139e4  mov     rcx, [rsp+590h+var_550]
0x1800139e9  test    rcx, rcx
  ... truncated ...
```
