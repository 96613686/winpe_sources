# SITE_OBJECT_EXTENSION::CreateObjects(ushort const *,ushort const *,IExtensionContext *,ICommandParameterList *,ICommandObjectList *)

- ea: `0x180010cc0`
- end: `0x18001137a`
- name: `?CreateObjects@SITE_OBJECT_EXTENSION@@UEAAJPEBG0PEAVIExtensionContext@@PEAVICommandParameterList@@PEAVICommandObjectList@@@Z`
- size: `1722`
- prototype: `int(SITE_OBJECT_EXTENSION *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct IExtensionContext *, struct ICommandParameterList *, struct ICommandObjectList *)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001044`
- `0x180001fb0`
- `0x18000efb0`
- `0x180010850`
- `0x180010cc0`
- `0x180011dc4`
- `0x180011fe0`
- `0x18002b250`
- `0x18002b564`
- `0x18002bb20`
- `0x18002bd3c`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!wcsstr` at `0x180010f0b`
- `msvcrt!wcsstr` at `0x180010f0b`

## pseudocode

```c
__int64 __fastcall SITE_OBJECT_EXTENSION::CreateObjects(
        SITE_OBJECT_EXTENSION *this,
        const unsigned __int16 *a2,
        wchar_t *a3,
        struct IExtensionContext *a4,
        struct ICommandParameterList *a5,
        struct ICommandObjectList *a6)
{
  SITE_OBJECT *v8; // rdi
  wchar_t *v10; // r15
  APP_OBJECT_UTILS *v11; // rcx
  int v12; // ebx
  bool v13; // zf
  __int64 v14; // rax
  const unsigned __int16 *v15; // r12
  APP_OBJECT_UTILS *v16; // rcx
  APP_OBJECT_UTILS *v17; // rcx
  unsigned int i; // r12d
  SITE_OBJECT *v19; // rax
  __int64 v20; // rax
  int v21; // ebx
  int v22; // eax
  int v23; // eax
  SITE_OBJECT *v24; // rax
  __int64 v25; // rax
  int v26; // r15d
  int v28; // [rsp+30h] [rbp-D0h]
  int v29; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v30; // [rsp+44h] [rbp-BCh] BYREF
  struct INativeConfigurationElement *v31; // [rsp+48h] [rbp-B8h] BYREF
  int v32; // [rsp+50h] [rbp-B0h] BYREF
  struct ICommandParameterList *v33; // [rsp+58h] [rbp-A8h] BYREF
  struct INativeConfigurationElement *v34; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v35; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v36; // [rsp+70h] [rbp-90h] BYREF
  __int64 v37; // [rsp+78h] [rbp-88h] BYREF
  __int64 v38; // [rsp+80h] [rbp-80h] BYREF
  __int64 v39; // [rsp+88h] [rbp-78h] BYREF
  SITE_OBJECT_EXTENSION *v40; // [rsp+90h] [rbp-70h]
  const unsigned __int16 *v41; // [rsp+98h] [rbp-68h]
  _BYTE v42[32]; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t *v43; // [rsp+C0h] [rbp-40h]
  int v44; // [rsp+C8h] [rbp-38h]
  __int16 v45; // [rsp+CCh] [rbp-34h]
  int v46; // [rsp+D0h] [rbp-30h]
  _BYTE v47[32]; // [rsp+D8h] [rbp-28h] BYREF
  wchar_t *Str; // [rsp+F8h] [rbp-8h]
  int v49; // [rsp+100h] [rbp+0h]
  __int16 v50; // [rsp+104h] [rbp+4h]
  int v51; // [rsp+108h] [rbp+8h]
  __int16 v52; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v53[510]; // [rsp+112h] [rbp+12h] BYREF
  __int16 v54; // [rsp+310h] [rbp+210h] BYREF
  _BYTE v55[510]; // [rsp+312h] [rbp+212h] BYREF

  v40 = this;
  v34 = 0;
  v31 = 0;
  v38 = 0;
  v39 = 0;
  v8 = 0;
  v35 = 0;
  v36 = 0;
  v32 = 0;
  memset_0(v53, 0, sizeof(v53));
  v50 = 256;
  v49 = 512;
  Str = (wchar_t *)&v52;
  v51 = 0;
  v52 = 0;
  memset_0(v55, 0, sizeof(v55));
  v44 = 512;
  v45 = 256;
  v43 = (wchar_t *)&v54;
  v46 = 0;
  v54 = 0;
  v30 = 0;
  v33 = 0;
  v37 = 0;
  v29 = 0;
  if ( !a2 || !a3 || !a4 || !a5 || !a6 )
  {
    v12 = -2147024809;
    goto LABEL_58;
  }
  v10 = 0;
  v12 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, struct ICommandParameterList **))(*(_QWORD *)a5 + 80LL))(
          a5,
          &v33);
  if ( v12 >= 0 )
  {
    if ( !*a3 && (APP_OBJECT_UTILS::PopParameter(v11, a4, v33, L"SITE.NAME", (struct STRU *)v47, 0, 1), a3 = Str, !*Str)
      || (v12 = APP_OBJECT_UTILS::ValidateEmptyParameters(v11, a4, v33), v12 >= 0) )
    {
      v13 = ((*(__int64 (__fastcall **)(struct IExtensionContext *))(*(_QWORD *)a4 + 32LL))(a4) & 8) == 0;
      v14 = *(_QWORD *)a4;
      v15 = &::Str;
      if ( v13 )
        v15 = L"MACHINE/WEBROOT/APPHOST";
      v41 = v15;
      v12 = (*(__int64 (__fastcall **)(struct IExtensionContext *, const unsigned __int16 *, __int64 *))(v14 + 80))(
              a4,
              v15,
              &v39);
      if ( v12 >= 0 )
      {
        v12 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, struct INativeConfigurationElement **, __int64 *))(*(_QWORD *)v39 + 24LL))(
                v39,
                L"system.applicationHost/sites",
                L"MACHINE/WEBROOT/APPHOST",
                &v34,
                &v35);
        if ( v12 < 0 )
        {
          if ( v35 )
            (*(void (__fastcall **)(struct IExtensionContext *, _QWORD, const wchar_t *, __int64, _DWORD))(*(_QWORD *)a4 + 112LL))(
              a4,
              (unsigned int)v12,
              &::Str,
              v35,
              0);
          goto LABEL_58;
        }
        if ( *a3 )
        {
          if ( wcsstr(a3, L"/") )
          {
            v12 = APP_OBJECT_UTILS::ResolveUrl(v17, a3, (struct STRU *)v42, 0, &v29);
            if ( v12 < 0 )
              goto LABEL_58;
            if ( v29 )
              goto LABEL_23;
            v10 = v43;
          }
          else
          {
            v10 = a3;
          }
          if ( !v10 )
          {
LABEL_23:
            v12 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 *))(*(_QWORD *)v34 + 40LL))(
                    v34,
                    &v38);
            if ( v12 >= 0 )
            {
              v12 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v38 + 24LL))(v38, &v36);
              if ( v12 >= 0 )
              {
                for ( i = (unsigned int)v10; ; ++i )
                {
                  v8 = 0;
                  if ( i >= v36 )
                    break;
                  v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct INativeConfigurationElement **))(*(_QWORD *)v38 + 32LL))(
                          v38,
                          i,
                          &v31);
                  if ( v12 < 0 )
                    break;
                  v19 = (SITE_OBJECT *)operator new(0xD8u);
                  if ( !v19 )
                    goto LABEL_50;
                  v8 = SITE_OBJECT::SITE_OBJECT(v19, v31, v34);
                  if ( !v8 )
                    goto LABEL_50;
                  v12 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, unsigned int *, _QWORD, _QWORD))(*(_QWORD *)v31 + 48LL))(
                          v31,
                          L"id",
                          &v30,
                          0,
                          0);
                  if ( v12 < 0 )
                    break;
                  v20 = *(_QWORD *)a4;
                  v21 = 4;
                  v29 = 4;
                  if ( ((*(__int64 (__fastcall **)(struct IExtensionContext *))(v20 + 32))(a4) & 4) == 0 )
                  {
                    SITE_OBJECT_EXTENSION::GetSiteState(v40, v30, (enum __MIDL___MIDL_itf_rscaps_0000_0003_0001 *)&v29);
                    v21 = v29;
                  }
                  v12 = SITE_OBJECT::Create(v8, v41, v21);
                  if ( v12 < 0 )
                    break;
                  v22 = *a3
                      ? SITE_OBJECT::MatchIdentifier(v8, a3, &v32)
                      : (*(unsigned __int64 (__fastcall **)(struct IExtensionContext *, SITE_OBJECT *, struct ICommandParameterList *, int *))(*(_QWORD *)a4 + 152LL))(
                          a4,
                          v8,
                          v33,
                          &v32);
                  v12 = v22;
                  if ( v22 < 0 )
                    break;
                  if ( v32 )
                  {
                    v12 = (*(__int64 (__fastcall **)(struct ICommandObjectList *, SITE_OBJECT *))(*(_QWORD *)a6 + 24LL))(
                            a6,
                            v8);
                    if ( v12 < 0 || *a3 )
                      break;
                  }
                  (*(void (__fastcall **)(SITE_OBJECT *))(*(_QWORD *)v8 + 16LL))(v8);
                  (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v31 + 16LL))(v31);
                  v31 = 0;
                }
              }
            }
            goto LABEL_58;
          }
        }
        else if ( (int)APP_OBJECT_UTILS::PopDwordParameter(v16, a4, v33, L"SITE.ID", &v30, 0, v28) < 0 )
        {
          goto LABEL_23;
        }
        v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v39 + 56LL))(v39, &v37);
        if ( v12 < 0 )
          goto LABEL_58;
        if ( !v10 )
          goto LABEL_77;
        v23 = (*(__int64 (__fastcall **)(__int64, wchar_t *, unsigned int *, __int64 *))(*(_QWORD *)v37 + 48LL))(
                v37,
                v10,
                &v30,
                &v35);
        v12 = v23;
        if ( v23 == -2147024894 )
        {
          v12 = 1;
          goto LABEL_58;
        }
        v10 = 0;
        if ( v23 >= 0 )
        {
LABEL_77:
          v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct INativeConfigurationElement **, __int64 *))(*(_QWORD *)v37 + 32LL))(
                  v37,
                  v30,
                  &v31,
                  &v35);
          if ( v12 >= 0 )
          {
            v24 = (SITE_OBJECT *)operator new(0xD8u);
            if ( v24 )
            {
              v8 = SITE_OBJECT::SITE_OBJECT(v24, v31, v34);
              if ( v8 )
              {
                v25 = *(_QWORD *)a4;
                v26 = 4;
                v29 = 4;
                if ( ((*(__int64 (__fastcall **)(struct IExtensionContext *))(v25 + 32))(a4) & 4) == 0 )
                {
                  SITE_OBJECT_EXTENSION::GetSiteState(v40, v30, (enum __MIDL___MIDL_itf_rscaps_0000_0003_0001 *)&v29);
                  v26 = v29;
                }
                v12 = SITE_OBJECT::Create(v8, v15, v26);
                if ( v12 >= 0 )
                  v12 = (*(__int64 (__fastcall **)(struct ICommandObjectList *, SITE_OBJECT *))(*(_QWORD *)a6 + 24LL))(
                          a6,
                          v8);
                goto LABEL_58;
              }
            }
            else
            {
              v8 = (SITE_OBJECT *)v10;
            }
LABEL_50:
            v12 = -2147024888;
          }
        }
      }
    }
  }
LABEL_58:
  if ( v37 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    v37 = 0;
  }
  if ( v8 )
    (*(void (__fastcall **)(SITE_OBJECT *))(*(_QWORD *)v8 + 16LL))(v8);
  if ( v31 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v31 + 16LL))(v31);
    v31 = 0;
  }
  if ( v38 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    v38 = 0;
  }
  if ( v34 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v34 + 16LL))(v34);
    v34 = 0;
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
  if ( v33 )
  {
    (*(void (__fastcall **)(struct ICommandParameterList *))(*(_QWORD *)v33 + 16LL))(v33);
    v33 = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v42);
  BUFFER::~BUFFER((BUFFER *)v47);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180010cc0  mov     [rsp-8+arg_8], rbx
0x180010cc5  push    rbp
0x180010cc6  push    rsi
0x180010cc7  push    rdi
0x180010cc8  push    r12
0x180010cca  push    r13
0x180010ccc  push    r14
0x180010cce  push    r15
0x180010cd0  lea     rbp, [rsp-420h]
0x180010cd8  sub     rsp, 520h
0x180010cdf  mov     rax, cs:__security_cookie
0x180010ce6  xor     rax, rsp
0x180010ce9  mov     [rbp+450h+var_40], rax
0x180010cf0  mov     r15, [rbp+450h+arg_20]
0x180010cf7  xor     eax, eax
0x180010cf9  mov     r13, [rbp+450h+arg_28]
0x180010d00  mov     rsi, r8
0x180010d03  mov     rbx, rdx
0x180010d06  mov     [rbp+450h+var_4C0], rcx
0x180010d0a  xor     edx, edx; Val
0x180010d0c  mov     [rsp+550h+var_4F0], rax
0x180010d11  mov     r8d, 1FEh; Size
0x180010d17  mov     [rsp+550h+var_508], rax
0x180010d1c  lea     rcx, [rbp+450h+var_43E]; void *
0x180010d20  mov     [rbp+450h+var_4D0], rax
0x180010d24  mov     [rbp+450h+var_4C8], rax
0x180010d28  mov     edi, eax
0x180010d2a  mov     [rsp+550h+var_4E8], rax
0x180010d2f  mov     r14, r9
0x180010d32  mov     [rsp+550h+var_4E0], eax
0x180010d36  mov     [rsp+550h+var_500], eax
0x180010d3a  call    memset_0
0x180010d3f  mov     r12d, 200h
0x180010d45  mov     [rbp+450h+var_44C], 100h
0x180010d4b  lea     rax, [rbp+450h+var_440]
0x180010d4f  mov     [rbp+450h+var_450], r12d
0x180010d53  mov     [rbp+450h+Str], rax
0x180010d57  lea     rcx, [rbp+450h+var_23E]; void *
0x180010d5e  xor     eax, eax
0x180010d60  xor     edx, edx; Val
0x180010d62  lea     r8d, [r12-2]; Size
0x180010d67  mov     [rbp+450h+var_448], eax
0x180010d6a  mov     [rbp+450h+var_440], ax
0x180010d6e  call    memset_0
0x180010d73  xor     ecx, ecx
0x180010d75  mov     [rbp+450h+var_488], r12d
0x180010d79  mov     [rbp+450h+var_484], 100h
0x180010d7f  lea     rax, [rbp+450h+var_240]
0x180010d86  mov     [rbp+450h+var_490], rax
0x180010d8a  mov     [rbp+450h+var_480], ecx
0x180010d8d  mov     [rbp+450h+var_240], cx
0x180010d94  mov     [rsp+550h+var_50C], ecx
0x180010d98  mov     [rsp+550h+var_4F8], rcx
0x180010d9d  mov     [rsp+550h+var_4D8], rcx
0x180010da2  mov     [rsp+550h+var_510], ecx
0x180010da6  test    rbx, rbx
0x180010da9  jz      loc_180011265
0x180010daf  test    rsi, rsi
0x180010db2  jz      loc_180011265
0x180010db8  test    r14, r14
0x180010dbb  jz      loc_180011265
0x180010dc1  test    r15, r15
0x180010dc4  jz      loc_180011265
0x180010dca  test    r13, r13
0x180010dcd  jz      loc_180011265
0x180010dd3  mov     rax, [r15]
0x180010dd6  lea     rdx, [rsp+550h+var_4F8]
0x180010ddb  mov     rcx, r15
0x180010dde  mov     rax, [rax+50h]
0x180010de2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010de7  xor     r15d, r15d
0x180010dea  mov     ebx, eax
0x180010dec  test    eax, eax
0x180010dee  js      loc_18001126A
0x180010df4  cmp     [rsi], r15w
0x180010df8  jnz     short loc_180010E2E
0x180010dfa  mov     r8, [rsp+550h+var_4F8]; struct ICommandParameterList *
0x180010dff  lea     rax, [rbp+450h+var_478]
0x180010e03  mov     [rsp+550h+var_520], 1; int
0x180010e0b  lea     r9, aSiteName; "SITE.NAME"
0x180010e12  mov     [rsp+550h+var_528], r15d; int
0x180010e17  mov     rdx, r14; struct IExtensionContext *
0x180010e1a  mov     [rsp+550h+var_530], rax; struct STRU *
0x180010e1f  call    ?PopParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAVSTRU@@HH@Z; APP_OBJECT_UTILS::PopParameter(IExtensionContext *,ICommandParameterList *,ushort const *,STRU *,int,int)
0x180010e24  mov     rsi, [rbp+450h+Str]
0x180010e28  cmp     [rsi], r15w
0x180010e2c  jz      short loc_180010E45
0x180010e2e  mov     r8, [rsp+550h+var_4F8]; struct ICommandParameterList *
0x180010e33  mov     rdx, r14; struct IExtensionContext *
0x180010e36  call    ?ValidateEmptyParameters@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@@Z; APP_OBJECT_UTILS::ValidateEmptyParameters(IExtensionContext *,ICommandParameterList *)
0x180010e3b  mov     ebx, eax
0x180010e3d  test    eax, eax
0x180010e3f  js      loc_18001126A
0x180010e45  mov     rax, [r14]
0x180010e48  mov     rcx, r14
0x180010e4b  mov     rax, [rax+20h]
0x180010e4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e54  test    al, 8
0x180010e56  lea     rcx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180010e5d  mov     rax, [r14]
0x180010e60  lea     r12, Str
0x180010e67  cmovz   r12, rcx
0x180010e6b  lea     r8, [rbp+450h+var_4C8]
0x180010e6f  mov     rdx, r12
0x180010e72  mov     [rbp+450h+var_4B8], r12
0x180010e76  mov     rcx, r14
0x180010e79  mov     rax, [rax+50h]
0x180010e7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e82  mov     ebx, eax
0x180010e84  test    eax, eax
0x180010e86  js      loc_18001126A
0x180010e8c  mov     rcx, [rbp+450h+var_4C8]
0x180010e90  lea     rdx, [rsp+550h+var_4E8]
0x180010e95  mov     qword ptr [rsp+550h+var_528], r15; int
0x180010e9a  lea     r9, [rsp+550h+var_4F0]
0x180010e9f  mov     [rsp+550h+var_530], rdx
0x180010ea4  lea     r8, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180010eab  lea     rdx, aSystemApplicat_2; "system.applicationHost/sites"
0x180010eb2  mov     rax, [rcx]
0x180010eb5  mov     rax, [rax+18h]
0x180010eb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ebe  mov     ebx, eax
0x180010ec0  test    eax, eax
0x180010ec2  jns     short loc_180010EF7
0x180010ec4  mov     rcx, [rsp+550h+var_4E8]
0x180010ec9  test    rcx, rcx
0x180010ecc  jz      loc_18001126A
0x180010ed2  mov     rax, [r14]
0x180010ed5  lea     r8, Str
0x180010edc  mov     r9, rcx
0x180010edf  mov     dword ptr [rsp+550h+var_530], r15d
0x180010ee4  mov     edx, ebx
0x180010ee6  mov     rcx, r14
0x180010ee9  mov     rax, [rax+70h]
0x180010eed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ef2  jmp     loc_18001126A
0x180010ef7  cmp     [rsi], r15w
0x180010efb  jz      loc_180011096
0x180010f01  lea     rdx, SubStr; "/"
0x180010f08  mov     rcx, rsi; Str
0x180010f0b  call    cs:__imp_wcsstr
0x180010f11  test    rax, rax
0x180010f14  jnz     short loc_180010F1B
0x180010f16  mov     r15, rsi
0x180010f19  jmp     short loc_180010F49
0x180010f1b  lea     rax, [rsp+550h+var_510]
0x180010f20  xor     r9d, r9d; unsigned __int16 **
0x180010f23  lea     r8, [rbp+450h+var_4B0]; struct STRU *
0x180010f27  mov     [rsp+550h+var_530], rax; int *
0x180010f2c  mov     rdx, rsi; unsigned __int16 *
0x180010f2f  call    ?ResolveUrl@APP_OBJECT_UTILS@@QEAAJPEBGPEAVSTRU@@PEAPEBGPEAH@Z; APP_OBJECT_UTILS::ResolveUrl(ushort const *,STRU *,ushort const * *,int *)
0x180010f34  mov     ebx, eax
0x180010f36  test    eax, eax
0x180010f38  js      loc_18001126A
0x180010f3e  cmp     [rsp+550h+var_510], r15d
0x180010f43  jnz     short loc_180010F52
0x180010f45  mov     r15, [rbp+450h+var_490]
0x180010f49  test    r15, r15
0x180010f4c  jnz     loc_1800110BC
0x180010f52  mov     rcx, [rsp+550h+var_4F0]
0x180010f57  lea     rdx, [rbp+450h+var_4D0]
0x180010f5b  mov     rax, [rcx]
0x180010f5e  mov     rax, [rax+28h]
0x180010f62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f67  mov     ebx, eax
0x180010f69  test    eax, eax
0x180010f6b  js      loc_18001126A
0x180010f71  mov     rcx, [rbp+450h+var_4D0]
0x180010f75  lea     rdx, [rsp+550h+var_4E0]
0x180010f7a  mov     rax, [rcx]
0x180010f7d  mov     rax, [rax+18h]
0x180010f81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f86  mov     ebx, eax
0x180010f88  test    eax, eax
0x180010f8a  js      loc_18001126A
0x180010f90  mov     r12d, r15d
0x180010f93  mov     r15d, 4
0x180010f99  xor     edi, edi
0x180010f9b  cmp     r12d, [rsp+550h+var_4E0]
0x180010fa0  jnb     loc_18001126A
0x180010fa6  mov     rcx, [rbp+450h+var_4D0]
0x180010faa  lea     r8, [rsp+550h+var_508]
0x180010faf  mov     edx, r12d
0x180010fb2  mov     rax, [rcx]
0x180010fb5  mov     rax, [rax+20h]
0x180010fb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010fbe  xor     ecx, ecx
0x180010fc0  mov     ebx, eax
0x180010fc2  test    eax, eax
0x180010fc4  js      loc_18001126A
0x180010fca  mov     ecx, 0D8h; Size
0x180010fcf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010fd4  xor     ebx, ebx
0x180010fd6  test    rax, rax
0x180010fd9  jz      loc_1800111DD
0x180010fdf  mov     r8, [rsp+550h+var_4F0]; struct INativeConfigurationElement *
0x180010fe4  mov     rcx, rax; this
0x180010fe7  mov     rdx, [rsp+550h+var_508]; struct INativeConfigurationElement *
0x180010fec  call    ??0SITE_OBJECT@@QEAA@PEAVINativeConfigurationElement@@0@Z; SITE_OBJECT::SITE_OBJECT(INativeConfigurationElement *,INativeConfigurationElement *)
0x180010ff1  mov     rdi, rax
0x180010ff4  test    rax, rax
0x180010ff7  jz      loc_1800111DD
0x180010ffd  mov     rcx, [rsp+550h+var_508]
0x180011002  lea     r8, [rsp+550h+var_50C]
0x180011007  xor     r9d, r9d
0x18001100a  mov     [rsp+550h+var_530], rbx
0x18001100f  lea     rdx, aId; "id"
0x180011016  mov     rax, [rcx]
0x180011019  mov     rax, [rax+30h]
0x18001101d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011022  mov     ebx, eax
0x180011024  test    eax, eax
0x180011026  js      loc_18001126A
0x18001102c  mov     rax, [r14]
0x18001102f  mov     ebx, r15d
0x180011032  mov     rcx, r14
0x180011035  mov     [rsp+550h+var_510], ebx
0x180011039  mov     rax, [rax+20h]
0x18001103d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011042  test    r15b, al
0x180011045  jnz     short loc_18001105D
0x180011047  mov     edx, [rsp+550h+var_50C]; unsigned int
0x18001104b  lea     r8, [rsp+550h+var_510]; enum __MIDL___MIDL_itf_rscaps_0000_0003_0001 *
0x180011050  mov     rcx, [rbp+450h+var_4C0]; this
0x180011054  call    ?GetSiteState@SITE_OBJECT_EXTENSION@@AEAAJKPEAW4__MIDL___MIDL_itf_rscaps_0000_0003_0001@@@Z; SITE_OBJECT_EXTENSION::GetSiteState(ulong,__MIDL___MIDL_itf_rscaps_0000_0003_0001 *)
0x180011059  mov     ebx, [rsp+550h+var_510]
0x18001105d  mov     rdx, [rbp+450h+var_4B8]
0x180011061  mov     r8d, ebx
0x180011064  mov     rcx, rdi
0x180011067  call    ?Create@SITE_OBJECT@@QEAAJPEBGW4__MIDL___MIDL_itf_rscaps_0000_0003_0001@@@Z; SITE_OBJECT::Create(ushort const *,__MIDL___MIDL_itf_rscaps_0000_0003_0001)
0x18001106c  xor     ecx, ecx
0x18001106e  mov     ebx, eax
0x180011070  test    eax, eax
0x180011072  js      loc_18001126A
0x180011078  cmp     [rsi], cx
0x18001107b  jz      loc_1800111E7
0x180011081  lea     r8, [rsp+550h+var_500]; int *
0x180011086  mov     rdx, rsi; unsigned __int16 *
0x180011089  mov     rcx, rdi; this
0x18001108c  call    ?MatchIdentifier@SITE_OBJECT@@QEAAJPEBGPEAH@Z; SITE_OBJECT::MatchIdentifier(ushort const *,int *)
0x180011091  jmp     loc_180011206
0x180011096  mov     r8, [rsp+550h+var_4F8]; struct ICommandParameterList *
0x18001109b  lea     rax, [rsp+550h+var_50C]
0x1800110a0  lea     r9, aSiteId; "SITE.ID"
0x1800110a7  mov     [rsp+550h+var_530], rax; unsigned int *
0x1800110ac  mov     rdx, r14; struct IExtensionContext *
0x1800110af  call    ?PopDwordParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAKHH@Z; APP_OBJECT_UTILS::PopDwordParameter(IExtensionContext *,ICommandParameterList *,ushort const *,ulong *,int,int)
0x1800110b4  test    eax, eax
0x1800110b6  js      loc_180010F52
0x1800110bc  mov     rcx, [rbp+450h+var_4C8]
0x1800110c0  lea     rdx, [rsp+550h+var_4D8]
0x1800110c5  mov     rax, [rcx]
0x1800110c8  mov     rax, [rax+38h]
0x1800110cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110d1  mov     ebx, eax
0x1800110d3  test    eax, eax
0x1800110d5  js      loc_18001126A
0x1800110db  test    r15, r15
0x1800110de  jz      short loc_18001111C
0x1800110e0  mov     rcx, [rsp+550h+var_4D8]
0x1800110e5  lea     r9, [rsp+550h+var_4E8]
0x1800110ea  lea     r8, [rsp+550h+var_50C]
0x1800110ef  mov     rdx, r15
0x1800110f2  mov     rax, [rcx]
0x1800110f5  mov     rax, [rax+30h]
0x1800110f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110fe  mov     ebx, eax
0x180011100  cmp     eax, 80070002h
0x180011105  jnz     short loc_180011111
0x180011107  mov     ebx, 1
0x18001110c  jmp     loc_18001126A
0x180011111  xor     r15d, r15d
0x180011114  test    eax, eax
0x180011116  js      loc_18001126A
0x18001111c  mov     rcx, [rsp+550h+var_4D8]
0x180011121  lea     r9, [rsp+550h+var_4E8]
0x180011126  mov     edx, [rsp+550h+var_50C]
0x18001112a  lea     r8, [rsp+550h+var_508]
0x18001112f  mov     rax, [rcx]
0x180011132  mov     rax, [rax+20h]
0x180011136  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001113b  mov     ebx, eax
0x18001113d  test    eax, eax
0x18001113f  js      loc_18001126A
0x180011145  mov     ecx, 0D8h; Size
0x18001114a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001114f  test    rax, rax
0x180011152  jz      loc_1800111DA
0x180011158  mov     r8, [rsp+550h+var_4F0]; struct INativeConfigurationElement *
0x18001115d  mov     rcx, rax; this
0x180011160  mov     rdx, [rsp+550h+var_508]; struct INativeConfigurationElement *
0x180011165  call    ??0SITE_OBJECT@@QEAA@PEAVINativeConfigurationElement@@0@Z; SITE_OBJECT::SITE_OBJECT(INativeConfigurationElement *,INativeConfigurationElement *)
0x18001116a  mov     rdi, rax
0x18001116d  test    rax, rax
0x180011170  jz      short loc_1800111DD
0x180011172  mov     rax, [r14]
0x180011175  mov     r15d, 4
0x18001117b  mov     rcx, r14
0x18001117e  mov     [rsp+550h+var_510], r15d
0x180011183  mov     rax, [rax+20h]
  ... truncated ...
```
