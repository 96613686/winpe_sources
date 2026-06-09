# CONFIG_OBJECT_EXTENSION::RegisterSection(IExtensionContext *,ushort const *,ushort const *,ICommandParameterList *,ICommandObjectList *)

- ea: `0x18001d8c0`
- end: `0x18001dec7`
- name: `?RegisterSection@CONFIG_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEBG1PEAVICommandParameterList@@PEAVICommandObjectList@@@Z`
- size: `1543`
- prototype: `int(CONFIG_OBJECT_EXTENSION *__hidden this, struct IExtensionContext *, const unsigned __int16 *, const unsigned __int16 *, struct ICommandParameterList *, struct ICommandObjectList *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001a850`

## callees

- `0x180001044`
- `0x180001fb0`
- `0x18000557c`
- `0x180006b6c`
- `0x18001882c`
- `0x18001aff4`
- `0x18001d8c0`
- `0x18002b304`
- `0x18002b564`
- `0x18002e76c`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001da65`
- `msvcrt!_wcsicmp` at `0x18001da65`
- `OLEAUT32!__imp_SysAllocString` at `0x18001dc59`
- `OLEAUT32!__imp_SysAllocString` at `0x18001dc59`
- `OLEAUT32!__imp_SysFreeString` at `0x18001de65`
- `OLEAUT32!__imp_SysFreeString` at `0x18001de65`

## string_xrefs

- `0x18001db00`: `overwrite`

## pseudocode

```c
__int64 __fastcall CONFIG_OBJECT_EXTENSION::RegisterSection(
        CONFIG_OBJECT_EXTENSION *this,
        struct IExtensionContext *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        struct ICommandParameterList *a5,
        struct ICommandObjectList *a6)
{
  int v8; // r14d
  OLECHAR *v10; // r13
  const unsigned __int16 **v11; // rdi
  int SectionNameHelper; // ebx
  __int64 v13; // rdx
  __int64 v14; // r8
  APP_OBJECT_UTILS *v15; // rcx
  int v16; // eax
  APP_OBJECT_UTILS *v17; // rcx
  int v18; // eax
  int v19; // eax
  APP_OBJECT_UTILS *v20; // rcx
  int v21; // eax
  APP_OBJECT_UTILS *v22; // rcx
  int v23; // eax
  BSTR v24; // rax
  struct IAppHostSectionGroup *v25; // rcx
  unsigned __int16 *v26; // r15
  int v27; // eax
  unsigned int v28; // r9d
  int v29; // eax
  STATUS_OBJECT *v30; // rax
  int v32; // [rsp+20h] [rbp-E0h]
  int v33; // [rsp+20h] [rbp-E0h]
  int v34; // [rsp+28h] [rbp-D8h]
  int v35; // [rsp+28h] [rbp-D8h]
  int v36; // [rsp+40h] [rbp-C0h]
  int v37; // [rsp+44h] [rbp-BCh]
  struct IAppHostSectionGroup *v38; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v39; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v40; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v41; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v42; // [rsp+68h] [rbp-98h] BYREF
  va_list Arguments[2]; // [rsp+70h] [rbp-90h] BYREF
  const wchar_t *v44; // [rsp+80h] [rbp-80h] BYREF
  const wchar_t *v45; // [rsp+88h] [rbp-78h]
  const wchar_t *v46; // [rsp+90h] [rbp-70h]
  const wchar_t *v47; // [rsp+98h] [rbp-68h]
  va_list v48; // [rsp+A0h] [rbp-60h]
  struct ICommandObjectList *v49; // [rsp+A8h] [rbp-58h]
  _QWORD v50[4]; // [rsp+B0h] [rbp-50h] BYREF
  const wchar_t *v51; // [rsp+D0h] [rbp-30h]
  int v52; // [rsp+D8h] [rbp-28h]
  __int16 v53; // [rsp+DCh] [rbp-24h]
  int v54; // [rsp+E0h] [rbp-20h]
  _QWORD v55[4]; // [rsp+E8h] [rbp-18h] BYREF
  const wchar_t *v56; // [rsp+108h] [rbp+8h]
  int v57; // [rsp+110h] [rbp+10h]
  __int16 v58; // [rsp+114h] [rbp+14h]
  int v59; // [rsp+118h] [rbp+18h]
  _QWORD v60[4]; // [rsp+120h] [rbp+20h] BYREF
  const wchar_t *v61; // [rsp+140h] [rbp+40h]
  int v62; // [rsp+148h] [rbp+48h]
  __int16 v63; // [rsp+14Ch] [rbp+4Ch]
  int v64; // [rsp+150h] [rbp+50h]
  _BYTE v65[32]; // [rsp+158h] [rbp+58h] BYREF
  va_list v66; // [rsp+178h] [rbp+78h]
  int v67; // [rsp+180h] [rbp+80h]
  __int16 v68; // [rsp+184h] [rbp+84h]
  int v69; // [rsp+188h] [rbp+88h]
  _BYTE v70[32]; // [rsp+190h] [rbp+90h] BYREF
  unsigned __int16 *v71; // [rsp+1B0h] [rbp+B0h]
  int v72; // [rsp+1B8h] [rbp+B8h]
  __int16 v73; // [rsp+1BCh] [rbp+BCh]
  int v74; // [rsp+1C0h] [rbp+C0h]
  __int16 v75; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE v76[510]; // [rsp+1D2h] [rbp+D2h] BYREF
  __int16 v77; // [rsp+3D0h] [rbp+2D0h] BYREF
  _BYTE v78[510]; // [rsp+3D2h] [rbp+2D2h] BYREF

  v49 = a6;
  v42 = 0;
  v61 = (const wchar_t *)v60;
  v8 = 1;
  v41 = 0;
  v56 = (const wchar_t *)v55;
  v40 = 0;
  v39 = 0;
  v10 = 0;
  v60[0] = 0;
  v64 = 0;
  v55[0] = 0;
  v59 = 0;
  v50[0] = 0;
  v54 = 0;
  v51 = (const wchar_t *)v50;
  v48 = (va_list)a4;
  *(_OWORD *)Arguments = 0;
  v62 = 32;
  v63 = 256;
  v57 = 32;
  v58 = 256;
  v52 = 32;
  v53 = 256;
  memset_0(v76, 0, sizeof(v76));
  v73 = 256;
  v71 = (unsigned __int16 *)&v75;
  v72 = 512;
  v75 = 0;
  v74 = 0;
  memset_0(v78, 0, sizeof(v78));
  v67 = 512;
  v66 = (va_list)&v77;
  v68 = 256;
  v69 = 0;
  v77 = 0;
  `vector constructor iterator'(
    &v44,
    0x20u,
    1u,
    (void *(*)(void *))IIS_CONFIG_SECTION_DEFINITION::IIS_CONFIG_SECTION_DEFINITION);
  v11 = 0;
  v44 = &Str;
  v45 = &Str;
  v46 = L"Deny";
  v47 = &Str;
  if ( !a2 || !a4 || !a5 )
  {
    SectionNameHelper = -2147024809;
    goto LABEL_47;
  }
  if ( _wcsicmp(a3, L"MACHINE/WEBROOT/APPHOST") )
  {
    SectionNameHelper = -2147024809;
    Arguments[0] = (va_list)a3;
    v13 = 2147942487LL;
    Arguments[1] = (va_list)L"MACHINE/WEBROOT/APPHOST";
    v14 = 3221226504LL;
LABEL_6:
    (*(void (__fastcall **)(struct IExtensionContext *, __int64, __int64, va_list *, _DWORD))(*(_QWORD *)a2 + 144LL))(
      a2,
      v13,
      v14,
      Arguments,
      0);
    goto LABEL_47;
  }
  SectionNameHelper = CONFIG_OBJECT_EXTENSION::ExtractSectionNameHelper(a4, (struct STRU *)v65, (struct STRU *)v70);
  if ( SectionNameHelper >= 0 )
  {
    v44 = (const wchar_t *)v66;
    v16 = APP_OBJECT_UTILS::PopEmptyParameter(v15, a2, a5, L"ignoreifexists", v32, v34);
    SectionNameHelper = v16;
    if ( v16 < 0 )
    {
      if ( v16 != -2147023483 )
        goto LABEL_47;
      v37 = 0;
      v18 = APP_OBJECT_UTILS::PopEmptyParameter(v17, a2, a5, L"overwrite", v33, v35);
      SectionNameHelper = v18;
      if ( v18 < 0 )
      {
        v36 = 0;
        if ( v18 != -2147023483 )
          goto LABEL_47;
      }
      else
      {
        v36 = 1;
      }
    }
    else
    {
      v37 = 1;
      v36 = 0;
    }
    v19 = APP_OBJECT_UTILS::PopParameter(v17, a2, a5, L"allowdefinition", (struct STRU *)v60, 0, 1);
    SectionNameHelper = v19;
    if ( v19 < 0 )
    {
      if ( v19 != -2147023483 )
        goto LABEL_47;
    }
    else
    {
      v45 = v61;
    }
    v21 = APP_OBJECT_UTILS::PopParameter(v20, a2, a5, L"overridemodedefault", (struct STRU *)v55, 0, 1);
    SectionNameHelper = v21;
    if ( v21 < 0 )
    {
      if ( v21 != -2147023483 )
        goto LABEL_47;
    }
    else
    {
      v46 = v56;
    }
    v23 = APP_OBJECT_UTILS::PopParameter(v22, a2, a5, L"allowlocation", (struct STRU *)v50, 0, 1);
    SectionNameHelper = v23;
    if ( v23 < 0 )
    {
      if ( v23 != -2147023483 )
        goto LABEL_47;
    }
    else
    {
      v47 = v51;
    }
    SectionNameHelper = (*(__int64 (__fastcall **)(struct IExtensionContext *, const unsigned __int16 *, __int64 *))(*(_QWORD *)a2 + 80LL))(
                          a2,
                          a3,
                          &v42);
    if ( SectionNameHelper >= 0 )
    {
      SectionNameHelper = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v42)(
                            v42,
                            &IID_IAppHostWritableAdminManager,
                            &v41);
      if ( SectionNameHelper >= 0 )
      {
        SectionNameHelper = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v41 + 48LL))(v41, &v40);
        if ( SectionNameHelper >= 0 )
        {
          v24 = SysAllocString(a3);
          v10 = v24;
          if ( !v24 )
          {
            SectionNameHelper = -2147024882;
            goto LABEL_47;
          }
          SectionNameHelper = (*(__int64 (__fastcall **)(__int64, BSTR, __int64 *))(*(_QWORD *)v40 + 24LL))(
                                v40,
                                v24,
                                &v39);
          if ( SectionNameHelper >= 0 )
          {
            v25 = 0;
            v38 = 0;
            if ( v39 && (v26 = v71) != 0 )
            {
              v27 = (*(__int64 (__fastcall **)(__int64, struct IAppHostSectionGroup **))(*(_QWORD *)v39 + 80LL))(
                      v39,
                      &v38);
              v25 = v38;
              SectionNameHelper = v27;
              if ( v27 >= 0 )
              {
                v29 = CONFIG_SECTION_DEFINITION_HELPER::RecursivelyAddSectionDefinitions(
                        v38,
                        v26,
                        (struct IIS_CONFIG_SECTION_DEFINITION *const)&v44,
                        v28,
                        v36);
                v25 = v38;
                SectionNameHelper = v29;
              }
            }
            else
            {
              SectionNameHelper = -2147024809;
            }
            if ( v25 )
              ((void (__fastcall *)(struct IAppHostSectionGroup *))v25->lpVtbl->Release)(v25);
            v13 = 2147942583LL;
            if ( SectionNameHelper == -2147024713 )
            {
              if ( v37 != 1 )
              {
                v14 = 3221226483LL;
                Arguments[0] = v66;
                Arguments[1] = 0;
                goto LABEL_6;
              }
            }
            else
            {
              if ( SectionNameHelper < 0 )
                goto LABEL_47;
              v8 = 0;
              SectionNameHelper = (*(__int64 (__fastcall **)(struct IExtensionContext *, const unsigned __int16 *, _QWORD))(*(_QWORD *)a2 + 208LL))(
                                    a2,
                                    a3,
                                    0);
              if ( SectionNameHelper < 0 )
                goto LABEL_47;
            }
            v30 = (STATUS_OBJECT *)operator new(0x110u);
            if ( v30 && (v11 = (const unsigned __int16 **)STATUS_OBJECT::STATUS_OBJECT(v30)) != 0 )
            {
              Arguments[0] = v48;
              Arguments[1] = 0;
              SectionNameHelper = STATUS_OBJECT::Create(v11, v8 != 0 ? 1073742899 : 1074, Arguments);
              if ( SectionNameHelper >= 0 )
                SectionNameHelper = (*(__int64 (__fastcall **)(struct ICommandObjectList *, const unsigned __int16 **))(*(_QWORD *)v49 + 24LL))(
                                      v49,
                                      v11);
            }
            else
            {
              SectionNameHelper = -2147024888;
            }
          }
        }
      }
    }
  }
LABEL_47:
  if ( v39 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    v39 = 0;
  }
  if ( v40 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    v40 = 0;
  }
  if ( v41 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    v41 = 0;
  }
  if ( v42 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    v42 = 0;
  }
  if ( v11 )
    (*((void (__fastcall **)(const unsigned __int16 **))*v11 + 2))(v11);
  if ( v10 )
    SysFreeString(v10);
  BUFFER::~BUFFER((BUFFER *)v65);
  BUFFER::~BUFFER((BUFFER *)v70);
  BUFFER::~BUFFER((BUFFER *)v50);
  BUFFER::~BUFFER((BUFFER *)v55);
  BUFFER::~BUFFER((BUFFER *)v60);
  return (unsigned int)SectionNameHelper;
}

```

## disassembly

```asm
0x18001d8c0  mov     [rsp-8+arg_0], rbx
0x18001d8c5  push    rbp
0x18001d8c6  push    rsi
0x18001d8c7  push    rdi
0x18001d8c8  push    r12
0x18001d8ca  push    r13
0x18001d8cc  push    r14
0x18001d8ce  push    r15
0x18001d8d0  lea     rbp, [rsp-4E0h]
0x18001d8d8  sub     rsp, 5E0h
0x18001d8df  mov     rax, cs:__security_cookie
0x18001d8e6  xor     rax, rsp
0x18001d8e9  mov     [rbp+510h+var_40], rax
0x18001d8f0  mov     rax, [rbp+510h+arg_28]
0x18001d8f7  xor     ecx, ecx
0x18001d8f9  mov     r15, [rbp+510h+arg_20]
0x18001d900  mov     rbx, r9
0x18001d903  mov     [rbp+510h+var_568], rax
0x18001d907  mov     r12, r8
0x18001d90a  lea     rax, [rbp+510h+var_4F0]
0x18001d90e  mov     [rsp+610h+var_5A8], rcx
0x18001d913  mov     [rbp+510h+var_4D0], rax
0x18001d917  lea     r14d, [rcx+1]
0x18001d91b  lea     rax, [rbp+510h+var_528]
0x18001d91f  mov     [rsp+610h+var_5B0], rcx
0x18001d924  mov     [rbp+510h+var_508], rax
0x18001d928  mov     rsi, rdx
0x18001d92b  lea     rax, [rbp+510h+var_560]
0x18001d92f  mov     [rsp+610h+var_5B8], rcx
0x18001d934  xorps   xmm0, xmm0
0x18001d937  mov     [rsp+610h+var_5C0], rcx
0x18001d93c  mov     r13d, ecx
0x18001d93f  mov     [rbp+510h+var_4F0], rcx
0x18001d943  mov     [rbp+510h+var_4C0], ecx
0x18001d946  xor     edx, edx; Val
0x18001d948  mov     [rbp+510h+var_528], rcx
0x18001d94c  mov     r8d, 1FEh; Size
0x18001d952  mov     [rbp+510h+var_4F8], ecx
0x18001d955  mov     [rbp+510h+var_560], rcx
0x18001d959  mov     [rbp+510h+var_530], ecx
0x18001d95c  lea     rcx, [rbp+510h+var_43E]; void *
0x18001d963  mov     [rbp+510h+var_540], rax
0x18001d967  mov     [rbp+510h+var_570], rbx
0x18001d96b  movups  xmmword ptr [rsp+610h+Arguments], xmm0
0x18001d970  mov     [rbp+510h+var_4C8], 20h ; ' '
0x18001d977  mov     [rbp+510h+var_4C4], 100h
0x18001d97d  mov     [rbp+510h+var_500], 20h ; ' '
0x18001d984  mov     [rbp+510h+var_4FC], 100h
0x18001d98a  mov     [rbp+510h+var_538], 20h ; ' '
0x18001d991  mov     [rbp+510h+var_534], 100h
0x18001d997  call    memset_0
0x18001d99c  lea     rax, [rbp+510h+var_440]
0x18001d9a3  mov     [rbp+510h+var_454], 100h
0x18001d9ac  mov     edi, 200h
0x18001d9b1  mov     [rbp+510h+var_460], rax
0x18001d9b8  xor     eax, eax
0x18001d9ba  mov     [rbp+510h+var_458], edi
0x18001d9c0  xor     edx, edx; Val
0x18001d9c2  mov     [rbp+510h+var_440], ax
0x18001d9c9  lea     rcx, [rbp+510h+var_23E]; void *
0x18001d9d0  mov     [rbp+510h+var_450], r13d
0x18001d9d7  lea     r8d, [rdi-2]; Size
0x18001d9db  call    memset_0
0x18001d9e0  lea     rax, [rbp+510h+var_240]
0x18001d9e7  mov     [rbp+510h+var_490], edi
0x18001d9ed  mov     [rbp+510h+var_498], rax
0x18001d9f1  lea     r9, ??0IIS_CONFIG_SECTION_DEFINITION@@QEAA@XZ; void *(*)(void *)
0x18001d9f8  xor     eax, eax
0x18001d9fa  mov     [rbp+510h+var_48C], 100h
0x18001da03  mov     r8d, r14d; unsigned __int64
0x18001da06  mov     [rbp+510h+var_488], r13d
0x18001da0d  lea     rcx, [rbp+510h+var_590]; void *
0x18001da11  mov     [rbp+510h+var_240], ax
0x18001da18  lea     edx, [rax+20h]; unsigned __int64
0x18001da1b  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x18001da20  lea     rcx, Str
0x18001da27  xor     edi, edi
0x18001da29  mov     [rbp+510h+var_590], rcx
0x18001da2d  lea     rax, aDeny; "Deny"
0x18001da34  mov     [rbp+510h+var_588], rcx
0x18001da38  mov     [rbp+510h+var_580], rax
0x18001da3c  mov     [rbp+510h+var_578], rcx
0x18001da40  test    rsi, rsi
0x18001da43  jz      loc_18001DDC8
0x18001da49  test    rbx, rbx
0x18001da4c  jz      loc_18001DDC8
0x18001da52  test    r15, r15
0x18001da55  jz      loc_18001DDC8
0x18001da5b  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x18001da62  mov     rcx, r12; String1
0x18001da65  call    cs:__imp__wcsicmp
0x18001da6b  test    eax, eax
0x18001da6d  jz      short loc_18001DAAD
0x18001da6f  mov     ebx, 80070057h
0x18001da74  mov     [rsp+610h+Arguments], r12
0x18001da79  lea     rax, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x18001da80  mov     edx, ebx
0x18001da82  mov     [rsp+610h+Arguments+8], rax
0x18001da87  mov     r8d, 0C0000408h
0x18001da8d  mov     rax, [rsi]
0x18001da90  lea     r9, [rsp+610h+Arguments]
0x18001da95  mov     rcx, rsi
0x18001da98  mov     dword ptr [rsp+610h+var_5F0], edi
0x18001da9c  mov     rax, [rax+90h]
0x18001daa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001daa8  jmp     loc_18001DDCD
0x18001daad  lea     r8, [rbp+510h+var_480]; struct STRU *
0x18001dab4  mov     rcx, rbx; unsigned __int16 *
0x18001dab7  lea     rdx, [rbp+510h+var_4B8]; this
0x18001dabb  call    ?ExtractSectionNameHelper@CONFIG_OBJECT_EXTENSION@@CAJPEBGPEAVSTRU@@1@Z; CONFIG_OBJECT_EXTENSION::ExtractSectionNameHelper(ushort const *,STRU *,STRU *)
0x18001dac0  mov     ebx, eax
0x18001dac2  test    eax, eax
0x18001dac4  js      loc_18001DDCD
0x18001daca  mov     rax, [rbp+510h+var_498]
0x18001dace  lea     r9, aIgnoreifexists; "ignoreifexists"
0x18001dad5  mov     r8, r15; struct ICommandParameterList *
0x18001dad8  mov     [rbp+510h+var_590], rax
0x18001dadc  mov     rdx, rsi; struct IExtensionContext *
0x18001dadf  call    ?PopEmptyParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGHH@Z; APP_OBJECT_UTILS::PopEmptyParameter(IExtensionContext *,ICommandParameterList *,ushort const *,int,int)
0x18001dae4  mov     ebx, eax
0x18001dae6  test    eax, eax
0x18001dae8  js      short loc_18001DAF5
0x18001daea  mov     [rsp+610h+var_5CC], r14d
0x18001daef  mov     [rsp+610h+var_5D0], edi
0x18001daf3  jmp     short loc_18001DB32
0x18001daf5  cmp     eax, 80070585h
0x18001dafa  jnz     loc_18001DDCD
0x18001db00  lea     r9, aOverwrite; "overwrite"
0x18001db07  mov     [rsp+610h+var_5CC], edi
0x18001db0b  mov     r8, r15; struct ICommandParameterList *
0x18001db0e  mov     rdx, rsi; struct IExtensionContext *
0x18001db11  call    ?PopEmptyParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGHH@Z; APP_OBJECT_UTILS::PopEmptyParameter(IExtensionContext *,ICommandParameterList *,ushort const *,int,int)
0x18001db16  mov     ebx, eax
0x18001db18  test    eax, eax
0x18001db1a  js      short loc_18001DB23
0x18001db1c  mov     [rsp+610h+var_5D0], r14d
0x18001db21  jmp     short loc_18001DB32
0x18001db23  mov     [rsp+610h+var_5D0], edi
0x18001db27  cmp     eax, 80070585h
0x18001db2c  jnz     loc_18001DDCD
0x18001db32  mov     [rsp+610h+var_5E0], r14d; int
0x18001db37  lea     rax, [rbp+510h+var_4F0]
0x18001db3b  mov     [rsp+610h+var_5E8], edi; int
0x18001db3f  lea     r9, aAllowdefinitio; "allowdefinition"
0x18001db46  mov     r8, r15; struct ICommandParameterList *
0x18001db49  mov     [rsp+610h+var_5F0], rax; struct STRU *
0x18001db4e  mov     rdx, rsi; struct IExtensionContext *
0x18001db51  call    ?PopParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAVSTRU@@HH@Z; APP_OBJECT_UTILS::PopParameter(IExtensionContext *,ICommandParameterList *,ushort const *,STRU *,int,int)
0x18001db56  mov     ebx, eax
0x18001db58  test    eax, eax
0x18001db5a  js      short loc_18001DB66
0x18001db5c  mov     rax, [rbp+510h+var_4D0]
0x18001db60  mov     [rbp+510h+var_588], rax
0x18001db64  jmp     short loc_18001DB71
0x18001db66  cmp     eax, 80070585h
0x18001db6b  jnz     loc_18001DDCD
0x18001db71  mov     [rsp+610h+var_5E0], r14d; int
0x18001db76  lea     rax, [rbp+510h+var_528]
0x18001db7a  mov     [rsp+610h+var_5E8], edi; int
0x18001db7e  lea     r9, aOverridemodede; "overridemodedefault"
0x18001db85  mov     r8, r15; struct ICommandParameterList *
0x18001db88  mov     [rsp+610h+var_5F0], rax; struct STRU *
0x18001db8d  mov     rdx, rsi; struct IExtensionContext *
0x18001db90  call    ?PopParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAVSTRU@@HH@Z; APP_OBJECT_UTILS::PopParameter(IExtensionContext *,ICommandParameterList *,ushort const *,STRU *,int,int)
0x18001db95  mov     ebx, eax
0x18001db97  test    eax, eax
0x18001db99  js      short loc_18001DBA5
0x18001db9b  mov     rax, [rbp+510h+var_508]
0x18001db9f  mov     [rbp+510h+var_580], rax
0x18001dba3  jmp     short loc_18001DBB0
0x18001dba5  cmp     eax, 80070585h
0x18001dbaa  jnz     loc_18001DDCD
0x18001dbb0  mov     [rsp+610h+var_5E0], r14d; int
0x18001dbb5  lea     rax, [rbp+510h+var_560]
0x18001dbb9  mov     [rsp+610h+var_5E8], edi; int
0x18001dbbd  lea     r9, aAllowlocation; "allowlocation"
0x18001dbc4  mov     r8, r15; struct ICommandParameterList *
0x18001dbc7  mov     [rsp+610h+var_5F0], rax; struct STRU *
0x18001dbcc  mov     rdx, rsi; struct IExtensionContext *
0x18001dbcf  call    ?PopParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAVSTRU@@HH@Z; APP_OBJECT_UTILS::PopParameter(IExtensionContext *,ICommandParameterList *,ushort const *,STRU *,int,int)
0x18001dbd4  mov     ebx, eax
0x18001dbd6  test    eax, eax
0x18001dbd8  js      short loc_18001DBE4
0x18001dbda  mov     rax, [rbp+510h+var_540]
0x18001dbde  mov     [rbp+510h+var_578], rax
0x18001dbe2  jmp     short loc_18001DBEF
0x18001dbe4  cmp     eax, 80070585h
0x18001dbe9  jnz     loc_18001DDCD
0x18001dbef  mov     rax, [rsi]
0x18001dbf2  lea     r8, [rsp+610h+var_5A8]
0x18001dbf7  mov     rdx, r12
0x18001dbfa  mov     rcx, rsi
0x18001dbfd  mov     rax, [rax+50h]
0x18001dc01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc06  mov     ebx, eax
0x18001dc08  test    eax, eax
0x18001dc0a  js      loc_18001DDCD
0x18001dc10  mov     rcx, [rsp+610h+var_5A8]
0x18001dc15  lea     r8, [rsp+610h+var_5B0]
0x18001dc1a  lea     rdx, IID_IAppHostWritableAdminManager
0x18001dc21  mov     rax, [rcx]
0x18001dc24  mov     rax, [rax]
0x18001dc27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc2c  mov     ebx, eax
0x18001dc2e  test    eax, eax
0x18001dc30  js      loc_18001DDCD
0x18001dc36  mov     rcx, [rsp+610h+var_5B0]
0x18001dc3b  lea     rdx, [rsp+610h+var_5B8]
0x18001dc40  mov     rax, [rcx]
0x18001dc43  mov     rax, [rax+30h]
0x18001dc47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc4c  mov     ebx, eax
0x18001dc4e  test    eax, eax
0x18001dc50  js      loc_18001DDCD
0x18001dc56  mov     rcx, r12; psz
0x18001dc59  call    cs:__imp_SysAllocString
0x18001dc5f  mov     r13, rax
0x18001dc62  test    rax, rax
0x18001dc65  jnz     short loc_18001DC71
0x18001dc67  mov     ebx, 8007000Eh
0x18001dc6c  jmp     loc_18001DDCD
0x18001dc71  mov     rcx, [rsp+610h+var_5B8]
0x18001dc76  lea     r8, [rsp+610h+var_5C0]
0x18001dc7b  mov     rdx, r13
0x18001dc7e  mov     rax, [rcx]
0x18001dc81  mov     rax, [rax+18h]
0x18001dc85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc8a  mov     ebx, eax
0x18001dc8c  test    eax, eax
0x18001dc8e  js      loc_18001DDCD
0x18001dc94  mov     r8, [rsp+610h+var_5C0]
0x18001dc99  xor     ecx, ecx
0x18001dc9b  mov     [rsp+610h+var_5C8], rcx
0x18001dca0  test    r8, r8
0x18001dca3  jz      short loc_18001DCED
0x18001dca5  mov     r15, [rbp+510h+var_460]
0x18001dcac  test    r15, r15
0x18001dcaf  jz      short loc_18001DCED
0x18001dcb1  mov     rax, [r8]
0x18001dcb4  lea     rdx, [rsp+610h+var_5C8]
0x18001dcb9  mov     rcx, r8
0x18001dcbc  mov     rax, [rax+50h]
0x18001dcc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dcc5  mov     rcx, [rsp+610h+var_5C8]; struct IAppHostSectionGroup *
0x18001dcca  mov     ebx, eax
0x18001dccc  test    eax, eax
0x18001dcce  js      short loc_18001DCF2
0x18001dcd0  mov     eax, [rsp+610h+var_5D0]
0x18001dcd4  lea     r8, [rbp+510h+var_590]; struct IIS_CONFIG_SECTION_DEFINITION *
0x18001dcd8  mov     rdx, r15; unsigned __int16 *
0x18001dcdb  mov     dword ptr [rsp+610h+var_5F0], eax; int
0x18001dcdf  call    ?RecursivelyAddSectionDefinitions@CONFIG_SECTION_DEFINITION_HELPER@@CAJPEAUIAppHostSectionGroup@@PEBGQEAUIIS_CONFIG_SECTION_DEFINITION@@KH@Z; CONFIG_SECTION_DEFINITION_HELPER::RecursivelyAddSectionDefinitions(IAppHostSectionGroup *,ushort const *,IIS_CONFIG_SECTION_DEFINITION * const,ulong,int)
0x18001dce4  mov     rcx, [rsp+610h+var_5C8]
0x18001dce9  mov     ebx, eax
0x18001dceb  jmp     short loc_18001DCF2
0x18001dced  mov     ebx, 80070057h
0x18001dcf2  test    rcx, rcx
0x18001dcf5  jz      short loc_18001DD03
0x18001dcf7  mov     rax, [rcx]
0x18001dcfa  mov     rax, [rax+10h]
0x18001dcfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd03  mov     edx, 800700B7h
0x18001dd08  cmp     ebx, edx
0x18001dd0a  jnz     short loc_18001DD2C
0x18001dd0c  cmp     [rsp+610h+var_5CC], r14d
0x18001dd11  jz      short loc_18001DD55
0x18001dd13  mov     rax, [rbp+510h+var_498]
0x18001dd17  mov     r8d, 0C00003F3h
0x18001dd1d  mov     [rsp+610h+Arguments], rax
0x18001dd22  mov     [rsp+610h+Arguments+8], rdi
0x18001dd27  jmp     loc_18001DA8D
0x18001dd2c  test    ebx, ebx
0x18001dd2e  js      loc_18001DDCD
0x18001dd34  mov     rax, [rsi]
0x18001dd37  xor     r8d, r8d
0x18001dd3a  mov     rdx, r12
0x18001dd3d  mov     rcx, rsi
0x18001dd40  xor     r14d, r14d
0x18001dd43  mov     rax, [rax+0D0h]
0x18001dd4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd4f  mov     ebx, eax
0x18001dd51  test    eax, eax
0x18001dd53  js      short loc_18001DDCD
0x18001dd55  mov     ecx, 110h; Size
0x18001dd5a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001dd5f  test    rax, rax
0x18001dd62  jz      short loc_18001DDC1
0x18001dd64  mov     rcx, rax; this
0x18001dd67  call    ??0STATUS_OBJECT@@QEAA@XZ; STATUS_OBJECT::STATUS_OBJECT(void)
0x18001dd6c  mov     rdi, rax
0x18001dd6f  test    rax, rax
0x18001dd72  jz      short loc_18001DDC1
0x18001dd74  mov     rax, [rbp+510h+var_570]
0x18001dd78  lea     r8, [rsp+610h+Arguments]; Arguments
0x18001dd7d  neg     r14d
0x18001dd80  mov     [rsp+610h+Arguments], rax
0x18001dd85  mov     rcx, rdi; this
0x18001dd88  mov     [rsp+610h+Arguments+8], 0
0x18001dd91  sbb     edx, edx
0x18001dd93  and     edx, 40000001h
  ... truncated ...
```
