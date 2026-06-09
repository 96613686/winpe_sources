# CONFIG_OBJECT_EXTENSION::MigrateHttpHandlersSection(IExtensionContext *,ushort const *,ICommandParameterList *,ICommandObjectList *)

- ea: `0x18001b7e4`
- end: `0x18001bd47`
- name: `?MigrateHttpHandlersSection@CONFIG_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEBGPEAVICommandParameterList@@PEAVICommandObjectList@@@Z`
- size: `1379`
- prototype: `__int64 __usercall@<rax>(CONFIG_OBJECT_EXTENSION *__hidden this@<rcx>, struct IExtensionContext *@<rdx>, const unsigned __int16 *@<r8>, struct ICommandParameterList *@<r9>, struct ICommandObjectList *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001b350`

## callees

- `0x180001fb0`
- `0x180002640`
- `0x180002e90`
- `0x180019f48`
- `0x18001b7e4`
- `0x18001bd50`
- `0x18002b0cc`
- `0x18002bd3c`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!wcsstr` at `0x18001bbba`
- `msvcrt!wcsstr` at `0x18001bbba`

## string_xrefs

- `0x18001bb95`: `CONFIGSEARCH.PATH`

## pseudocode

```c
__int64 __fastcall CONFIG_OBJECT_EXTENSION::MigrateHttpHandlersSection(
        CONFIG_OBJECT_EXTENSION *this,
        struct IExtensionContext *a2,
        const unsigned __int16 *a3,
        struct ICommandParameterList *a4,
        struct ICommandObjectList *a5)
{
  int v5; // edi
  APP_OBJECT_UTILS *v10; // rcx
  int v11; // ebx
  APP_OBJECT_UTILS *v12; // rcx
  APP_OBJECT_UTILS *v13; // rcx
  int v14; // r15d
  int v15; // eax
  unsigned int i; // r14d
  wchar_t *v17; // rax
  int v18; // eax
  int v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+28h] [rbp-D8h]
  struct ICommandParameterList *v22; // [rsp+40h] [rbp-C0h] BYREF
  struct ICommandObjectList *v23; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v24; // [rsp+50h] [rbp-B0h] BYREF
  int v25; // [rsp+58h] [rbp-A8h] BYREF
  int v26; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v27; // [rsp+60h] [rbp-A0h] BYREF
  struct ICommandParameterList *v28; // [rsp+68h] [rbp-98h] BYREF
  struct INativeConfigurationElementCollection *v29; // [rsp+70h] [rbp-90h] BYREF
  __int64 v30; // [rsp+78h] [rbp-88h] BYREF
  __int64 v31; // [rsp+80h] [rbp-80h] BYREF
  __int64 v32; // [rsp+88h] [rbp-78h] BYREF
  wchar_t *Str; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v34[32]; // [rsp+98h] [rbp-68h] BYREF
  __int16 *v35; // [rsp+B8h] [rbp-48h]
  int v36; // [rsp+C0h] [rbp-40h]
  __int16 v37; // [rsp+C4h] [rbp-3Ch]
  int v38; // [rsp+C8h] [rbp-38h]
  _QWORD v39[4]; // [rsp+D0h] [rbp-30h] BYREF
  wchar_t *SubStr; // [rsp+F0h] [rbp-10h]
  int v41; // [rsp+F8h] [rbp-8h]
  __int16 v42; // [rsp+FCh] [rbp-4h]
  int v43; // [rsp+100h] [rbp+0h]
  __int16 v44; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v45[510]; // [rsp+112h] [rbp+12h] BYREF

  v5 = 0;
  v22 = 0;
  v28 = 0;
  v30 = 0;
  v31 = 0;
  v26 = 1;
  v32 = 0;
  v29 = 0;
  v25 = 0;
  memset_0(v45, 0, sizeof(v45));
  v36 = 512;
  v35 = &v44;
  v37 = 256;
  v38 = 0;
  v44 = 0;
  v24 = 0;
  v23 = 0;
  v27 = 0;
  Str = 0;
  if ( a2 && a3 && a4 && a5 )
  {
    v11 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, struct ICommandParameterList **))(*(_QWORD *)a4 + 80LL))(
            a4,
            &v22);
    if ( v11 >= 0 )
    {
      v11 = APP_OBJECT_UTILS::PopBooleanParameter(v10, a2, v22, L"clear", &v25, v20, 1);
      if ( (int)(v11 + 0x80000000) < 0 || v11 == -2147023483 )
      {
        v11 = APP_OBJECT_UTILS::PopBooleanParameter(v12, a2, v22, L"recurse", &v26, v21, 1);
        if ( ((v11 + 0x80000000) & 0x80000000) != 0 || v11 == -2147023483 )
        {
          v11 = APP_OBJECT_UTILS::ValidateEmptyParameters(v13, a2, v22);
          if ( v11 >= 0 )
          {
            v11 = (*(__int64 (__fastcall **)(struct IExtensionContext *, const wchar_t *, __int64 *))(*(_QWORD *)a2 + 80LL))(
                    a2,
                    L"MACHINE/WEBROOT/APPHOST",
                    &v30);
            if ( v11 >= 0 )
            {
              v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, __int64 *, __int64 *, _QWORD))(*(_QWORD *)v30 + 24LL))(
                      v30,
                      L"system.web/httpHandlers",
                      L"MACHINE/WEBROOT/APPHOST",
                      &v32,
                      &v31,
                      0);
              if ( v11 >= 0 )
              {
                v11 = (*(__int64 (__fastcall **)(__int64, struct INativeConfigurationElementCollection **))(*(_QWORD *)v32 + 40LL))(
                        v32,
                        &v29);
                if ( v11 >= 0 )
                {
                  v14 = v25;
                  v15 = CONFIG_OBJECT_EXTENSION::MigrateHttpHandlersSectionHelper(this, a2, a3, v29, L"v2.0", v25, a5);
                  v11 = v15;
                  if ( v15 >= 0 )
                  {
                    LOBYTE(v5) = v15 == 0;
                    if ( v26 )
                    {
                      v39[0] = 0;
                      SubStr = (wchar_t *)v39;
                      v41 = 32;
                      v42 = 256;
                      v43 = 0;
                      v11 = STRU::Copy((STRU *)v39, (const unsigned __int8 *)a3);
                      if ( v11 < 0
                        || (v11 = STRU::Append((STRU *)v39, (const unsigned __int8 *)L"/"), v11 < 0)
                        || (v11 = (*(__int64 (__fastcall **)(struct IExtensionContext *, struct ICommandObjectList **))(*(_QWORD *)a2 + 184LL))(
                                    a2,
                                    &v23),
                            v11 < 0)
                        || (v11 = (*(__int64 (__fastcall **)(struct IExtensionContext *, struct ICommandParameterList **))(*(_QWORD *)a2 + 192LL))(
                                    a2,
                                    &v28),
                            v11 < 0)
                        || (v11 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, const unsigned __int16 *, const wchar_t *))(*(_QWORD *)v28 + 56LL))(
                                    v28,
                                    L"section",
                                    L"system.web/httpHandlers"),
                            v11 < 0)
                        || (v11 = CONFIG_OBJECT_EXTENSION::DoSearch(this, a2, (const unsigned __int8 *)a3, v28, v23),
                            v11 < 0)
                        || (v11 = (*(__int64 (__fastcall **)(struct ICommandObjectList *, unsigned int *))(*(_QWORD *)v23 + 32LL))(
                                    v23,
                                    &v27),
                            v11 < 0) )
                      {
LABEL_36:
                        BUFFER::~BUFFER((BUFFER *)v39);
                        goto LABEL_38;
                      }
                      for ( i = 0; i < v27; ++i )
                      {
                        v11 = (*(__int64 (__fastcall **)(struct ICommandObjectList *, _QWORD, __int64 *))(*(_QWORD *)v23 + 40LL))(
                                v23,
                                i,
                                &v24);
                        if ( v11 < 0 )
                          goto LABEL_36;
                        v11 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v24 + 80LL))(
                                v24,
                                L"CONFIGSEARCH.PATH",
                                &Str);
                        if ( v11 < 0 )
                          goto LABEL_36;
                        v17 = wcsstr(Str, SubStr);
                        if ( v17 == Str )
                        {
                          v18 = CONFIG_OBJECT_EXTENSION::MigrateHttpHandlersSectionHelper(
                                  this,
                                  a2,
                                  Str,
                                  v29,
                                  L"v2.0",
                                  v14,
                                  a5);
                          v11 = v18;
                          if ( v18 < 0 )
                            goto LABEL_36;
                          if ( !v18 )
                            v5 = 1;
                        }
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
                        v24 = 0;
                      }
                      BUFFER::~BUFFER((BUFFER *)v39);
                    }
                    v11 = v5 == 0;
                  }
                }
              }
              else if ( v31 )
              {
                (*(void (__fastcall **)(struct IExtensionContext *, _QWORD, const wchar_t *, __int64, _DWORD))(*(_QWORD *)a2 + 112LL))(
                  a2,
                  (unsigned int)v11,
                  &::Str,
                  v31,
                  0);
              }
            }
          }
        }
      }
    }
  }
  else
  {
    v11 = -2147024809;
  }
LABEL_38:
  if ( v22 )
  {
    (*(void (__fastcall **)(struct ICommandParameterList *))(*(_QWORD *)v22 + 16LL))(v22);
    v22 = 0;
  }
  if ( v28 )
  {
    (*(void (__fastcall **)(struct ICommandParameterList *))(*(_QWORD *)v28 + 16LL))(v28);
    v28 = 0;
  }
  if ( v23 )
  {
    (*(void (__fastcall **)(struct ICommandObjectList *))(*(_QWORD *)v23 + 16LL))(v23);
    v23 = 0;
  }
  if ( v30 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    v30 = 0;
  }
  if ( v31 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    v31 = 0;
  }
  if ( v29 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElementCollection *))(*(_QWORD *)v29 + 16LL))(v29);
    v29 = 0;
  }
  if ( v32 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    v32 = 0;
  }
  if ( v24 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    v24 = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v34);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18001b7e4  push    rbp
0x18001b7e6  push    rbx
0x18001b7e7  push    rsi
0x18001b7e8  push    rdi
0x18001b7e9  push    r12
0x18001b7eb  push    r13
0x18001b7ed  push    r14
0x18001b7ef  push    r15
0x18001b7f1  lea     rbp, [rsp-228h]
0x18001b7f9  sub     rsp, 328h
0x18001b800  mov     rax, cs:__security_cookie
0x18001b807  xor     rax, rsp
0x18001b80a  mov     [rbp+260h+var_50], rax
0x18001b811  mov     r12, [rbp+260h+arg_20]
0x18001b818  xor     edi, edi
0x18001b81a  mov     r14, r8
0x18001b81d  mov     [rsp+360h+var_320], rdi
0x18001b822  mov     rsi, rdx
0x18001b825  mov     [rsp+360h+var_2F8], rdi
0x18001b82a  mov     r13, rcx
0x18001b82d  mov     [rsp+360h+var_2E8], rdi
0x18001b832  lea     r15d, [rdi+1]
0x18001b836  mov     [rbp+260h+var_2E0], rdi
0x18001b83a  xor     edx, edx; Val
0x18001b83c  mov     [rsp+360h+var_304], r15d
0x18001b841  mov     r8d, 1FEh; Size
0x18001b847  mov     [rbp+260h+var_2D8], rdi
0x18001b84b  lea     rcx, [rbp+260h+var_24E]; void *
0x18001b84f  mov     [rsp+360h+var_2F0], rdi
0x18001b854  mov     rbx, r9
0x18001b857  mov     [rsp+360h+var_308], edi
0x18001b85b  call    memset_0
0x18001b860  mov     [rbp+260h+var_2A0], 200h
0x18001b867  lea     rax, [rbp+260h+var_250]
0x18001b86b  mov     [rbp+260h+var_2A8], rax
0x18001b86f  mov     [rbp+260h+var_29C], 100h
0x18001b875  mov     [rbp+260h+var_298], edi
0x18001b878  mov     [rbp+260h+var_250], di
0x18001b87c  mov     [rsp+360h+var_310], rdi
0x18001b881  mov     [rsp+360h+var_318], rdi
0x18001b886  mov     [rsp+360h+var_300], edi
0x18001b88a  mov     [rbp+260h+Str], rdi
0x18001b88e  test    rsi, rsi
0x18001b891  jz      loc_18001BC3E
0x18001b897  test    r14, r14
0x18001b89a  jz      loc_18001BC3E
0x18001b8a0  test    rbx, rbx
0x18001b8a3  jz      loc_18001BC3E
0x18001b8a9  test    r12, r12
0x18001b8ac  jz      loc_18001BC3E
0x18001b8b2  mov     rax, [rbx]
0x18001b8b5  lea     rdx, [rsp+360h+var_320]
0x18001b8ba  mov     rcx, rbx
0x18001b8bd  mov     rax, [rax+50h]
0x18001b8c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b8c6  mov     ebx, eax
0x18001b8c8  test    eax, eax
0x18001b8ca  js      loc_18001BC43
0x18001b8d0  mov     r8, [rsp+360h+var_320]; struct ICommandParameterList *
0x18001b8d5  lea     rax, [rsp+360h+var_308]
0x18001b8da  mov     dword ptr [rsp+360h+var_330], r15d; int
0x18001b8df  lea     r9, aClear; "clear"
0x18001b8e6  mov     rdx, rsi; struct IExtensionContext *
0x18001b8e9  mov     [rsp+360h+var_340], rax; int *
0x18001b8ee  call    ?PopBooleanParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAHHH@Z; APP_OBJECT_UTILS::PopBooleanParameter(IExtensionContext *,ICommandParameterList *,ushort const *,int *,int,int)
0x18001b8f3  mov     r15d, 80000000h
0x18001b8f9  mov     ebx, eax
0x18001b8fb  add     eax, r15d
0x18001b8fe  test    r15d, eax
0x18001b901  jnz     short loc_18001B90F
0x18001b903  cmp     ebx, 80070585h
0x18001b909  jnz     loc_18001BC43
0x18001b90f  mov     r8, [rsp+360h+var_320]; struct ICommandParameterList *
0x18001b914  lea     rax, [rsp+360h+var_304]
0x18001b919  mov     dword ptr [rsp+360h+var_330], 1; int
0x18001b921  lea     r9, aRecurse; "recurse"
0x18001b928  mov     rdx, rsi; struct IExtensionContext *
0x18001b92b  mov     [rsp+360h+var_340], rax; int *
0x18001b930  call    ?PopBooleanParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAHHH@Z; APP_OBJECT_UTILS::PopBooleanParameter(IExtensionContext *,ICommandParameterList *,ushort const *,int *,int,int)
0x18001b935  mov     ebx, eax
0x18001b937  add     eax, r15d
0x18001b93a  test    r15d, eax
0x18001b93d  jnz     short loc_18001B94B
0x18001b93f  cmp     ebx, 80070585h
0x18001b945  jnz     loc_18001BC43
0x18001b94b  mov     r8, [rsp+360h+var_320]; struct ICommandParameterList *
0x18001b950  mov     rdx, rsi; struct IExtensionContext *
0x18001b953  call    ?ValidateEmptyParameters@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@@Z; APP_OBJECT_UTILS::ValidateEmptyParameters(IExtensionContext *,ICommandParameterList *)
0x18001b958  mov     ebx, eax
0x18001b95a  test    eax, eax
0x18001b95c  js      loc_18001BC43
0x18001b962  mov     rax, [rsi]
0x18001b965  lea     r8, [rsp+360h+var_2E8]
0x18001b96a  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x18001b971  mov     rcx, rsi
0x18001b974  mov     rax, [rax+50h]
0x18001b978  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b97d  mov     ebx, eax
0x18001b97f  test    eax, eax
0x18001b981  js      loc_18001BC43
0x18001b987  mov     rcx, [rsp+360h+var_2E8]
0x18001b98c  lea     rdx, [rbp+260h+var_2E0]
0x18001b990  mov     qword ptr [rsp+360h+var_338], rdi
0x18001b995  lea     r9, [rbp+260h+var_2D8]
0x18001b999  mov     [rsp+360h+var_340], rdx
0x18001b99e  lea     r8, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x18001b9a5  lea     rdx, aSystemWebHttph; "system.web/httpHandlers"
0x18001b9ac  mov     rax, [rcx]
0x18001b9af  mov     rax, [rax+18h]
0x18001b9b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b9b8  mov     ebx, eax
0x18001b9ba  test    eax, eax
0x18001b9bc  jns     short loc_18001B9EF
0x18001b9be  mov     rcx, [rbp+260h+var_2E0]
0x18001b9c2  test    rcx, rcx
0x18001b9c5  jz      loc_18001BC43
0x18001b9cb  mov     rax, [rsi]
0x18001b9ce  lea     r8, Str
0x18001b9d5  mov     r9, rcx
0x18001b9d8  mov     dword ptr [rsp+360h+var_340], edi
0x18001b9dc  mov     edx, ebx
0x18001b9de  mov     rcx, rsi
0x18001b9e1  mov     rax, [rax+70h]
0x18001b9e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b9ea  jmp     loc_18001BC43
0x18001b9ef  mov     rcx, [rbp+260h+var_2D8]
0x18001b9f3  lea     rdx, [rsp+360h+var_2F0]
0x18001b9f8  mov     rax, [rcx]
0x18001b9fb  mov     rax, [rax+28h]
0x18001b9ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba04  mov     ebx, eax
0x18001ba06  test    eax, eax
0x18001ba08  js      loc_18001BC43
0x18001ba0e  mov     r15d, [rsp+360h+var_308]
0x18001ba13  lea     rax, aV20; "v2.0"
0x18001ba1a  mov     r9, [rsp+360h+var_2F0]; struct INativeConfigurationElementCollection *
0x18001ba1f  mov     r8, r14; unsigned __int16 *
0x18001ba22  mov     [rsp+360h+var_330], r12; struct ICommandObjectList *
0x18001ba27  mov     rdx, rsi; struct IExtensionContext *
0x18001ba2a  mov     [rsp+360h+var_338], r15d; int
0x18001ba2f  mov     rcx, r13; this
0x18001ba32  mov     [rsp+360h+var_340], rax; unsigned __int16 *
0x18001ba37  call    ?MigrateHttpHandlersSectionHelper@CONFIG_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEBGPEAVINativeConfigurationElementCollection@@1HPEAVICommandObjectList@@@Z; CONFIG_OBJECT_EXTENSION::MigrateHttpHandlersSectionHelper(IExtensionContext *,ushort const *,INativeConfigurationElementCollection *,ushort const *,int,ICommandObjectList *)
0x18001ba3c  mov     ebx, eax
0x18001ba3e  test    eax, eax
0x18001ba40  js      loc_18001BC43
0x18001ba46  setz    dil
0x18001ba4a  cmp     [rsp+360h+var_304], 0
0x18001ba4f  jz      loc_18001BC28
0x18001ba55  lea     rax, [rbp+260h+var_290]
0x18001ba59  mov     [rbp+260h+var_290], 0
0x18001ba61  mov     rdx, r14; unsigned __int16 *
0x18001ba64  mov     [rbp+260h+SubStr], rax
0x18001ba68  lea     rcx, [rbp+260h+var_290]; this
0x18001ba6c  mov     [rbp+260h+var_268], 20h ; ' '
0x18001ba73  mov     [rbp+260h+var_264], 100h
0x18001ba79  mov     [rbp+260h+var_260], 0
0x18001ba80  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001ba85  mov     ebx, eax
0x18001ba87  test    eax, eax
0x18001ba89  js      loc_18001BC33
0x18001ba8f  lea     rdx, SubStr; "/"
0x18001ba96  lea     rcx, [rbp+260h+var_290]; this
0x18001ba9a  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001ba9f  mov     ebx, eax
0x18001baa1  test    eax, eax
0x18001baa3  js      loc_18001BC33
0x18001baa9  mov     rax, [rsi]
0x18001baac  lea     rdx, [rsp+360h+var_318]
0x18001bab1  mov     rcx, rsi
0x18001bab4  mov     rax, [rax+0B8h]
0x18001babb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bac0  mov     ebx, eax
0x18001bac2  test    eax, eax
0x18001bac4  js      loc_18001BC33
0x18001baca  mov     rax, [rsi]
0x18001bacd  lea     rdx, [rsp+360h+var_2F8]
0x18001bad2  mov     rcx, rsi
0x18001bad5  mov     rax, [rax+0C0h]
0x18001badc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bae1  mov     ebx, eax
0x18001bae3  test    eax, eax
0x18001bae5  js      loc_18001BC33
0x18001baeb  mov     rcx, [rsp+360h+var_2F8]
0x18001baf0  lea     r8, aSystemWebHttph; "system.web/httpHandlers"
0x18001baf7  lea     rdx, aSection; "section"
0x18001bafe  mov     rax, [rcx]
0x18001bb01  mov     rax, [rax+38h]
0x18001bb05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb0a  mov     ebx, eax
0x18001bb0c  test    eax, eax
0x18001bb0e  js      loc_18001BC33
0x18001bb14  mov     rax, [rsp+360h+var_318]
0x18001bb19  mov     r8, r14; unsigned __int16 *
0x18001bb1c  mov     r9, [rsp+360h+var_2F8]; struct ICommandParameterList *
0x18001bb21  mov     rdx, rsi; struct IExtensionContext *
0x18001bb24  mov     rcx, r13; this
0x18001bb27  mov     [rsp+360h+var_340], rax; struct ICommandObjectList *
0x18001bb2c  call    ?DoSearch@CONFIG_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEBGPEAVICommandParameterList@@PEAVICommandObjectList@@@Z; CONFIG_OBJECT_EXTENSION::DoSearch(IExtensionContext *,ushort const *,ICommandParameterList *,ICommandObjectList *)
0x18001bb31  mov     ebx, eax
0x18001bb33  test    eax, eax
0x18001bb35  js      loc_18001BC33
0x18001bb3b  mov     rcx, [rsp+360h+var_318]
0x18001bb40  lea     rdx, [rsp+360h+var_300]
0x18001bb45  mov     rax, [rcx]
0x18001bb48  mov     rax, [rax+20h]
0x18001bb4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb51  mov     ebx, eax
0x18001bb53  test    eax, eax
0x18001bb55  js      loc_18001BC33
0x18001bb5b  xor     r14d, r14d
0x18001bb5e  cmp     r14d, [rsp+360h+var_300]
0x18001bb63  jnb     loc_18001BC1F
0x18001bb69  mov     rcx, [rsp+360h+var_318]
0x18001bb6e  lea     r8, [rsp+360h+var_310]
0x18001bb73  mov     edx, r14d
0x18001bb76  mov     rax, [rcx]
0x18001bb79  mov     rax, [rax+28h]
0x18001bb7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb82  mov     ebx, eax
0x18001bb84  test    eax, eax
0x18001bb86  js      loc_18001BC33
0x18001bb8c  mov     rcx, [rsp+360h+var_310]
0x18001bb91  lea     r8, [rbp+260h+Str]
0x18001bb95  lea     rdx, aConfigsearchPa; "CONFIGSEARCH.PATH"
0x18001bb9c  mov     rax, [rcx]
0x18001bb9f  mov     rax, [rax+50h]
0x18001bba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bba8  mov     ebx, eax
0x18001bbaa  test    eax, eax
0x18001bbac  js      loc_18001BC33
0x18001bbb2  mov     rdx, [rbp+260h+SubStr]; SubStr
0x18001bbb6  mov     rcx, [rbp+260h+Str]; Str
0x18001bbba  call    cs:__imp_wcsstr
0x18001bbc0  mov     r8, [rbp+260h+Str]; unsigned __int16 *
0x18001bbc4  cmp     rax, r8
0x18001bbc7  jnz     short loc_18001BBFD
0x18001bbc9  mov     r9, [rsp+360h+var_2F0]; struct INativeConfigurationElementCollection *
0x18001bbce  lea     rax, aV20; "v2.0"
0x18001bbd5  mov     [rsp+360h+var_330], r12; struct ICommandObjectList *
0x18001bbda  mov     rdx, rsi; struct IExtensionContext *
0x18001bbdd  mov     [rsp+360h+var_338], r15d; int
0x18001bbe2  mov     rcx, r13; this
0x18001bbe5  mov     [rsp+360h+var_340], rax; unsigned __int16 *
0x18001bbea  call    ?MigrateHttpHandlersSectionHelper@CONFIG_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEBGPEAVINativeConfigurationElementCollection@@1HPEAVICommandObjectList@@@Z; CONFIG_OBJECT_EXTENSION::MigrateHttpHandlersSectionHelper(IExtensionContext *,ushort const *,INativeConfigurationElementCollection *,ushort const *,int,ICommandObjectList *)
0x18001bbef  mov     ebx, eax
0x18001bbf1  test    eax, eax
0x18001bbf3  js      short loc_18001BC33
0x18001bbf5  mov     eax, 1
0x18001bbfa  cmovz   edi, eax
0x18001bbfd  mov     rcx, [rsp+360h+var_310]
0x18001bc02  mov     rax, [rcx]
0x18001bc05  mov     rax, [rax+10h]
0x18001bc09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc0e  inc     r14d
0x18001bc11  mov     [rsp+360h+var_310], 0
0x18001bc1a  jmp     loc_18001BB5E
0x18001bc1f  lea     rcx, [rbp+260h+var_290]; this
0x18001bc23  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18001bc28  xor     ebx, ebx
0x18001bc2a  test    edi, edi
0x18001bc2c  jnz     short loc_18001BC43
0x18001bc2e  lea     ebx, [rdi+1]
0x18001bc31  jmp     short loc_18001BC43
0x18001bc33  lea     rcx, [rbp+260h+var_290]; this
0x18001bc37  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18001bc3c  jmp     short loc_18001BC43
0x18001bc3e  mov     ebx, 80070057h
0x18001bc43  mov     rcx, [rsp+360h+var_320]
0x18001bc48  xor     edi, edi
0x18001bc4a  test    rcx, rcx
0x18001bc4d  jz      short loc_18001BC60
0x18001bc4f  mov     rax, [rcx]
0x18001bc52  mov     rax, [rax+10h]
0x18001bc56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc5b  mov     [rsp+360h+var_320], rdi
0x18001bc60  mov     rcx, [rsp+360h+var_2F8]
0x18001bc65  test    rcx, rcx
0x18001bc68  jz      short loc_18001BC7B
0x18001bc6a  mov     rax, [rcx]
0x18001bc6d  mov     rax, [rax+10h]
0x18001bc71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc76  mov     [rsp+360h+var_2F8], rdi
0x18001bc7b  mov     rcx, [rsp+360h+var_318]
0x18001bc80  test    rcx, rcx
0x18001bc83  jz      short loc_18001BC96
0x18001bc85  mov     rax, [rcx]
0x18001bc88  mov     rax, [rax+10h]
0x18001bc8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc91  mov     [rsp+360h+var_318], rdi
0x18001bc96  mov     rcx, [rsp+360h+var_2E8]
0x18001bc9b  test    rcx, rcx
0x18001bc9e  jz      short loc_18001BCB1
0x18001bca0  mov     rax, [rcx]
0x18001bca3  mov     rax, [rax+10h]
0x18001bca7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bcac  mov     [rsp+360h+var_2E8], rdi
0x18001bcb1  mov     rcx, [rbp+260h+var_2E0]
0x18001bcb5  test    rcx, rcx
0x18001bcb8  jz      short loc_18001BCCA
  ... truncated ...
```
