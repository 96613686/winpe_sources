# TRACE_OBJECT_EXTENSION::Configure(IExtensionContext *,ushort const *,ICommandParameterList *,ICommandObjectList *,IXMLDOMDocument *)

- ea: `0x180025fe4`
- end: `0x1800267ce`
- name: `?Configure@TRACE_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEBGPEAVICommandParameterList@@PEAVICommandObjectList@@PEAUIXMLDOMDocument@@@Z`
- size: `2026`
- prototype: `int(TRACE_OBJECT_EXTENSION *__hidden this, struct IExtensionContext *, const unsigned __int16 *, struct ICommandParameterList *, struct ICommandObjectList *, struct IXMLDOMDocument *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800279c0`

## callees

- `0x180001fb0`
- `0x180004560`
- `0x180025748`
- `0x180025fe4`
- `0x180028f50`
- `0x18002b304`
- `0x18002bd3c`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180026363`
- `msvcrt!_wcsicmp` at `0x18002637d`
- `msvcrt!_wcsicmp` at `0x180026363`
- `msvcrt!_wcsicmp` at `0x18002637d`

## string_xrefs

- `0x180026536`: `CONFIG`
- `0x1800265d6`: `CONFIGURE`

## pseudocode

```c
__int64 __fastcall TRACE_OBJECT_EXTENSION::Configure(
        TRACE_OBJECT_EXTENSION *this,
        struct IExtensionContext *a2,
        const unsigned __int16 *a3,
        struct ICommandParameterList *a4,
        struct ICommandObjectList *a5,
        struct IXMLDOMDocument *a6)
{
  const wchar_t *v6; // r13
  APP_OBJECT_UTILS *v9; // rcx
  int v10; // ebx
  int v11; // eax
  APP_OBJECT_UTILS *v12; // rcx
  int v13; // r14d
  int v14; // eax
  APP_OBJECT_UTILS *v15; // rcx
  int v16; // r12d
  int v17; // eax
  APP_OBJECT_UTILS *v18; // rcx
  int v19; // eax
  APP_OBJECT_UTILS *v20; // rcx
  int v21; // esi
  int v22; // eax
  BOOL v23; // esi
  BOOL v24; // r15d
  const unsigned __int16 *v25; // rax
  __int64 v26; // r8
  __int64 v27; // rdx
  BOOL v28; // r14d
  BOOL v29; // r12d
  int v30; // esi
  const wchar_t *v31; // r8
  TRACE_OBJECT_EXTENSION *v32; // rcx
  int v33; // eax
  int v35; // [rsp+20h] [rbp-E0h]
  int v36; // [rsp+20h] [rbp-E0h]
  int v37; // [rsp+20h] [rbp-E0h]
  int v38; // [rsp+20h] [rbp-E0h]
  int v39; // [rsp+20h] [rbp-E0h]
  int v40; // [rsp+28h] [rbp-D8h]
  int v41; // [rsp+28h] [rbp-D8h]
  int v42; // [rsp+28h] [rbp-D8h]
  int v43; // [rsp+28h] [rbp-D8h]
  int v44; // [rsp+28h] [rbp-D8h]
  struct ICommandParameterList *v45; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v46; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v47; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v48; // [rsp+70h] [rbp-90h] BYREF
  __int64 v49; // [rsp+78h] [rbp-88h] BYREF
  struct ICommandObject *v50; // [rsp+80h] [rbp-80h] BYREF
  __int64 v51; // [rsp+88h] [rbp-78h] BYREF
  struct ICommandObjectList *v52; // [rsp+90h] [rbp-70h] BYREF
  __int64 v53; // [rsp+98h] [rbp-68h] BYREF
  __int64 v54; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v55; // [rsp+A8h] [rbp-58h] BYREF
  int v56; // [rsp+ACh] [rbp-54h]
  __int64 v57; // [rsp+B0h] [rbp-50h] BYREF
  const unsigned __int16 *v58; // [rsp+B8h] [rbp-48h]
  APP_OBJECT_UTILS *v59; // [rsp+C0h] [rbp-40h]
  TRACE_OBJECT_EXTENSION *v60; // [rsp+C8h] [rbp-38h]
  _BYTE v61[32]; // [rsp+D0h] [rbp-30h] BYREF
  __int16 *v62; // [rsp+F0h] [rbp-10h]
  int v63; // [rsp+F8h] [rbp-8h]
  __int16 v64; // [rsp+FCh] [rbp-4h]
  int v65; // [rsp+100h] [rbp+0h]
  _QWORD v66[4]; // [rsp+108h] [rbp+8h] BYREF
  wchar_t *String1; // [rsp+128h] [rbp+28h]
  unsigned int v68; // [rsp+130h] [rbp+30h]
  __int16 v69; // [rsp+134h] [rbp+34h]
  int v70; // [rsp+138h] [rbp+38h]
  __int16 v71; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v72[510]; // [rsp+142h] [rbp+42h] BYREF

  v6 = a3;
  v58 = a3;
  v60 = this;
  v52 = a5;
  v59 = (APP_OBJECT_UTILS *)a6;
  v54 = 0;
  v45 = 0;
  v48 = 0;
  v51 = 0;
  v49 = 0;
  v50 = 0;
  v53 = 0;
  memset_0(v72, 0, sizeof(v72));
  v63 = 512;
  v62 = &v71;
  v64 = 256;
  v65 = 0;
  v71 = 0;
  v46 = 0;
  v57 = 0;
  v47 = 0;
  if ( !a2 || !v6 || !a4 || !a5 )
  {
    v10 = -2147024809;
    goto LABEL_84;
  }
  v10 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, struct ICommandParameterList **))(*(_QWORD *)a4 + 80LL))(
          a4,
          &v45);
  if ( v10 >= 0 )
  {
    v11 = APP_OBJECT_UTILS::PopEmptyParameter(v9, a2, v45, L"enable", v35, v40);
    v13 = v11;
    if ( v11 >= 0 || (v10 = v11, v11 == -2147023483) )
    {
      v14 = APP_OBJECT_UTILS::PopEmptyParameter(v12, a2, v45, L"disable", v36, v41);
      v16 = v14;
      if ( v14 >= 0 || (v10 = v14, v14 == -2147023483) )
      {
        v17 = APP_OBJECT_UTILS::PopEmptyParameter(v15, a2, v45, L"verbose", v37, v42);
        v56 = v17;
        if ( v17 >= 0 || (v10 = v17, v17 == -2147023483) )
        {
          v19 = APP_OBJECT_UTILS::PopEmptyParameter(v18, a2, v45, L"enablesite", v38, v43);
          v21 = v19;
          if ( v19 >= 0 || (v10 = v19, v19 == -2147023483) )
          {
            v22 = APP_OBJECT_UTILS::PopEmptyParameter(v20, a2, v45, L"disablesite", v39, v44);
            v10 = v22;
            if ( v22 >= 0 || v22 == -2147023483 )
            {
              v23 = v21 >= 0;
              v24 = v22 >= 0;
              if ( v23 && v22 >= 0 )
              {
                *(_QWORD *)&v47 = L"enablesite";
                v25 = L"disablesite";
LABEL_19:
                *((_QWORD *)&v47 + 1) = v25;
                v26 = 3221226545LL;
LABEL_20:
                v27 = 2147942450LL;
                v10 = -2147024846;
LABEL_21:
                (*(void (__fastcall **)(struct IExtensionContext *, __int64, __int64, __int128 *, _DWORD))(*(_QWORD *)a2 + 144LL))(
                  a2,
                  v27,
                  v26,
                  &v47,
                  0);
                goto LABEL_84;
              }
              v28 = v13 >= 0;
              v29 = v16 >= 0;
              if ( v28 && v29 )
              {
                *(_QWORD *)&v47 = L"enable";
                v25 = L"disable";
                goto LABEL_19;
              }
              if ( v23 || v22 >= 0 )
              {
                if ( !*v6 )
                {
                  v26 = 3221226522LL;
                  *(_QWORD *)&v47 = L"SITE";
                  goto LABEL_20;
                }
              }
              else if ( !*v6 )
              {
                goto LABEL_56;
              }
              v10 = (*(__int64 (__fastcall **)(struct IExtensionContext *, const unsigned __int16 *, const wchar_t *, __int64 *, int))(*(_QWORD *)a2 + 64LL))(
                      a2,
                      L"SITE",
                      v6,
                      &v53,
                      4);
              if ( v10 < 0 )
                goto LABEL_84;
              v10 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64 *))(*(_QWORD *)v53 + 80LL))(
                      v53,
                      L"SITE.NAME",
                      &v57);
              if ( v10 < 0 )
                goto LABEL_84;
              if ( v23 || v24 )
              {
                v10 = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64 *))(*(_QWORD *)a2 + 192LL))(
                        a2,
                        &v51);
                if ( v10 < 0 )
                  goto LABEL_84;
                if ( v23 )
                {
                  v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *))(*(_QWORD *)v51 + 56LL))(
                          v51,
                          L"traceFailedRequestsLogging.enabled",
                          L"true");
                  if ( v10 < 0 )
                    goto LABEL_84;
                  v30 = 1;
                }
                else
                {
                  v30 = 0;
                  if ( v24 )
                  {
                    v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *))(*(_QWORD *)v51 + 56LL))(
                            v51,
                            L"traceFailedRequestsLogging.enabled",
                            L"false");
                    if ( v10 < 0 )
                      goto LABEL_84;
                    v30 = 2;
                  }
                }
                v10 = (*(__int64 (__fastcall **)(struct IExtensionContext *, const unsigned __int16 *, const wchar_t *, __int64, __int64, struct ICommandObjectList **, _QWORD, _DWORD))(*(_QWORD *)a2 + 48LL))(
                        a2,
                        L"SITE",
                        L"SET",
                        v57,
                        v51,
                        &v52,
                        0,
                        0);
                if ( v10 < 0 )
                  goto LABEL_84;
                goto LABEL_52;
              }
              v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v53 + 48LL))(v53, &v54);
              if ( v10 < 0 )
                goto LABEL_84;
              v66[0] = 0;
              String1 = (wchar_t *)v66;
              v68 = 32;
              v69 = 256;
              v70 = 0;
              v10 = STRA::Resize((STRA *)v66, 0xAu);
              if ( v10 >= 0 )
              {
                v55 = v68 >> 1;
                v10 = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64, const wchar_t *, wchar_t *, unsigned int *, _QWORD))(*(_QWORD *)a2 + 88LL))(
                        a2,
                        v54,
                        L"traceFailedRequestsLogging.enabled",
                        String1,
                        &v55,
                        0);
                if ( v10 >= 0 )
                {
                  if ( !_wcsicmp(String1, L"true") )
                  {
                    v30 = 1;
LABEL_42:
                    BUFFER::~BUFFER((BUFFER *)v66);
LABEL_52:
                    if ( v30 == 2 && v28 )
                    {
                      v26 = 3221226531LL;
                      *(_QWORD *)&v47 = v57;
                      goto LABEL_20;
                    }
                    v6 = v58;
LABEL_56:
                    v10 = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64 *))(*(_QWORD *)a2 + 192LL))(
                            a2,
                            &v48);
                    if ( v10 >= 0 )
                    {
                      v10 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, const wchar_t *))(*(_QWORD *)v48 + 56LL))(
                              v48,
                              L"section",
                              L"system.webServer/tracing/traceFailedRequests");
                      if ( v10 >= 0 )
                      {
                        if ( v56 < 0
                          || (v10 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, const wchar_t *))(*(_QWORD *)v48 + 56LL))(
                                      v48,
                                      L"verbose",
                                      &Str),
                              v10 >= 0) )
                        {
                          v10 = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64 *))(*(_QWORD *)a2 + 184LL))(
                                  a2,
                                  &v49);
                          if ( v10 >= 0 )
                          {
                            v31 = *v6 ? v6 : L"MACHINE/WEBROOT/APPHOST";
                            v10 = (*(__int64 (__fastcall **)(struct IExtensionContext *, const unsigned __int16 *, const wchar_t *, __int64, __int64, _DWORD))(*(_QWORD *)a2 + 56LL))(
                                    a2,
                                    L"CONFIG",
                                    v31,
                                    v48,
                                    v49,
                                    0);
                            if ( v10 >= 0 )
                            {
                              v10 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v49 + 32LL))(
                                      v49,
                                      &v46);
                              if ( v10 >= 0 )
                              {
                                if ( !v46 )
                                {
                                  v10 = -2147024894;
                                  *(_QWORD *)&v47 = L"CONFIG";
                                  v27 = 2147942402LL;
                                  *((_QWORD *)&v47 + 1) = v6;
                                  v26 = 3221226521LL;
                                  goto LABEL_21;
                                }
                                if ( v46 > 1 )
                                {
                                  *(_QWORD *)&v47 = L"CONFIG";
                                  *((_QWORD *)&v47 + 1) = L"CONFIGURE";
                                  v26 = 3221226475LL;
                                  goto LABEL_20;
                                }
                                v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct ICommandObject **))(*(_QWORD *)v49 + 40LL))(
                                        v49,
                                        0,
                                        &v50);
                                if ( v10 >= 0 )
                                {
                                  if ( v28 )
                                  {
                                    v33 = TRACE_OBJECT_EXTENSION::AddTraceRule(v60, a2, v50, v45, v52);
LABEL_73:
                                    v10 = v33;
                                    goto LABEL_84;
                                  }
                                  if ( v29 )
                                  {
                                    v33 = TRACE_OBJECT_EXTENSION::RemoveTraceRule(v32, a2, v50, v45, v52);
                                    goto LABEL_73;
                                  }
                                  v10 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, unsigned int *))(*(_QWORD *)v45 + 24LL))(
                                          v45,
                                          &v46);
                                  if ( v10 >= 0 )
                                  {
                                    if ( v46 || v59 )
                                    {
                                      v33 = (*(__int64 (__fastcall **)(struct IExtensionContext *, struct ICommandObject *, struct ICommandParameterList *, struct ICommandObjectList *, APP_OBJECT_UTILS *, _DWORD))(*(_QWORD *)a2 + 168LL))(
                                              a2,
                                              v50,
                                              v45,
                                              v52,
                                              v59,
                                              0);
                                      goto LABEL_73;
                                    }
                                    v10 = APP_OBJECT_UTILS::ValidateEmptyParameters(0, a2, v45);
                                    if ( v10 >= 0 )
                                    {
                                      v33 = (*(__int64 (__fastcall **)(struct ICommandObjectList *, struct ICommandObject *))(*(_QWORD *)v52 + 24LL))(
                                              v52,
                                              v50);
                                      goto LABEL_73;
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                    goto LABEL_84;
                  }
                  if ( !_wcsicmp(String1, L"false") )
                  {
                    v30 = 2;
                    goto LABEL_42;
                  }
                  v10 = -2147024883;
                }
              }
              BUFFER::~BUFFER((BUFFER *)v66);
            }
          }
        }
      }
    }
  }
LABEL_84:
  if ( v45 )
  {
    (*(void (__fastcall **)(struct ICommandParameterList *))(*(_QWORD *)v45 + 16LL))(v45);
    v45 = 0;
  }
  if ( v48 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
    v48 = 0;
  }
  if ( v51 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    v51 = 0;
  }
  if ( v49 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
    v49 = 0;
  }
  if ( v50 )
  {
    (*(void (__fastcall **)(struct ICommandObject *))(*(_QWORD *)v50 + 16LL))(v50);
    v50 = 0;
  }
  if ( v54 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
    v54 = 0;
  }
  if ( v53 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
    v53 = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v61);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180025fe4  push    rbp
0x180025fe6  push    rbx
0x180025fe7  push    rsi
0x180025fe8  push    rdi
0x180025fe9  push    r12
0x180025feb  push    r13
0x180025fed  push    r14
0x180025fef  push    r15
0x180025ff1  lea     rbp, [rsp-258h]
0x180025ff9  sub     rsp, 358h
0x180026000  mov     rax, cs:__security_cookie
0x180026007  xor     rax, rsp
0x18002600a  mov     [rbp+290h+var_50], rax
0x180026011  mov     rax, [rbp+290h+arg_28]
0x180026018  xor     r15d, r15d
0x18002601b  mov     rsi, [rbp+290h+arg_20]
0x180026022  mov     r13, r8
0x180026025  mov     [rbp+290h+var_2D8], r8
0x180026029  mov     rdi, rdx
0x18002602c  mov     [rbp+290h+var_2C8], rcx
0x180026030  xor     edx, edx; Val
0x180026032  mov     r8d, 1FEh; Size
0x180026038  mov     [rbp+290h+var_300], rsi
0x18002603c  lea     rcx, [rbp+290h+var_24E]; void *
0x180026040  mov     [rbp+290h+var_2D0], rax
0x180026044  mov     [rbp+290h+var_2F0], r15
0x180026048  mov     rbx, r9
0x18002604b  mov     [rsp+390h+var_340], r15
0x180026050  mov     [rsp+390h+var_320], r15
0x180026055  mov     [rbp+290h+var_308], r15
0x180026059  mov     [rsp+390h+var_318], r15
0x18002605e  mov     [rbp+290h+var_310], r15
0x180026062  mov     [rbp+290h+var_2F8], r15
0x180026066  call    memset_0
0x18002606b  mov     [rbp+290h+var_298], 200h
0x180026072  lea     rax, [rbp+290h+var_250]
0x180026076  mov     [rbp+290h+var_2A0], rax
0x18002607a  xorps   xmm0, xmm0
0x18002607d  mov     [rbp+290h+var_294], 100h
0x180026083  mov     [rbp+290h+var_290], r15d
0x180026087  mov     [rbp+290h+var_250], r15w
0x18002608c  mov     [rsp+390h+var_338], r15d
0x180026091  mov     [rbp+290h+var_2E0], r15
0x180026095  movups  [rsp+390h+var_330], xmm0
0x18002609a  test    rdi, rdi
0x18002609d  jz      loc_1800266E6
0x1800260a3  test    r13, r13
0x1800260a6  jz      loc_1800266E6
0x1800260ac  test    rbx, rbx
0x1800260af  jz      loc_1800266E6
0x1800260b5  test    rsi, rsi
0x1800260b8  jz      loc_1800266E6
0x1800260be  mov     rax, [rbx]
0x1800260c1  lea     rdx, [rsp+390h+var_340]
0x1800260c6  mov     rcx, rbx
0x1800260c9  mov     rax, [rax+50h]
0x1800260cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800260d2  mov     ebx, eax
0x1800260d4  test    eax, eax
0x1800260d6  js      loc_1800266EB
0x1800260dc  mov     r8, [rsp+390h+var_340]; struct ICommandParameterList *
0x1800260e1  lea     r9, aEnable; "enable"
0x1800260e8  mov     rdx, rdi; struct IExtensionContext *
0x1800260eb  call    ?PopEmptyParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGHH@Z; APP_OBJECT_UTILS::PopEmptyParameter(IExtensionContext *,ICommandParameterList *,ushort const *,int,int)
0x1800260f0  mov     r14d, eax
0x1800260f3  mov     esi, 80070585h
0x1800260f8  test    eax, eax
0x1800260fa  jns     short loc_180026106
0x1800260fc  mov     ebx, eax
0x1800260fe  cmp     eax, esi
0x180026100  jnz     loc_1800266EB
0x180026106  mov     r8, [rsp+390h+var_340]; struct ICommandParameterList *
0x18002610b  lea     r9, aDisable; "disable"
0x180026112  mov     rdx, rdi; struct IExtensionContext *
0x180026115  call    ?PopEmptyParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGHH@Z; APP_OBJECT_UTILS::PopEmptyParameter(IExtensionContext *,ICommandParameterList *,ushort const *,int,int)
0x18002611a  mov     r12d, eax
0x18002611d  test    eax, eax
0x18002611f  jns     short loc_18002612B
0x180026121  mov     ebx, eax
0x180026123  cmp     eax, esi
0x180026125  jnz     loc_1800266EB
0x18002612b  mov     r8, [rsp+390h+var_340]; struct ICommandParameterList *
0x180026130  lea     r9, aVerbose_0; "verbose"
0x180026137  mov     rdx, rdi; struct IExtensionContext *
0x18002613a  call    ?PopEmptyParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGHH@Z; APP_OBJECT_UTILS::PopEmptyParameter(IExtensionContext *,ICommandParameterList *,ushort const *,int,int)
0x18002613f  mov     [rbp+290h+var_2E4], eax
0x180026142  test    eax, eax
0x180026144  jns     short loc_180026150
0x180026146  mov     ebx, eax
0x180026148  cmp     eax, esi
0x18002614a  jnz     loc_1800266EB
0x180026150  mov     r8, [rsp+390h+var_340]; struct ICommandParameterList *
0x180026155  lea     r9, aEnablesite; "enablesite"
0x18002615c  mov     rdx, rdi; struct IExtensionContext *
0x18002615f  call    ?PopEmptyParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGHH@Z; APP_OBJECT_UTILS::PopEmptyParameter(IExtensionContext *,ICommandParameterList *,ushort const *,int,int)
0x180026164  mov     esi, eax
0x180026166  test    eax, eax
0x180026168  jns     short loc_180026177
0x18002616a  mov     ebx, eax
0x18002616c  cmp     eax, 80070585h
0x180026171  jnz     loc_1800266EB
0x180026177  mov     r8, [rsp+390h+var_340]; struct ICommandParameterList *
0x18002617c  lea     r9, aDisablesite; "disablesite"
0x180026183  mov     rdx, rdi; struct IExtensionContext *
0x180026186  call    ?PopEmptyParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGHH@Z; APP_OBJECT_UTILS::PopEmptyParameter(IExtensionContext *,ICommandParameterList *,ushort const *,int,int)
0x18002618b  mov     ebx, eax
0x18002618d  test    eax, eax
0x18002618f  jns     short loc_18002619C
0x180026191  cmp     eax, 80070585h
0x180026196  jnz     loc_1800266EB
0x18002619c  not     esi
0x18002619e  not     ebx
0x1800261a0  shr     ebx, 1Fh
0x1800261a3  xor     eax, eax
0x1800261a5  shr     esi, 1Fh
0x1800261a8  mov     r15d, ebx
0x1800261ab  test    esi, esi
0x1800261ad  jz      short loc_1800261FC
0x1800261af  test    ebx, ebx
0x1800261b1  jz      short loc_1800261FC
0x1800261b3  lea     rax, aEnablesite; "enablesite"
0x1800261ba  mov     qword ptr [rsp+390h+var_330], rax
0x1800261bf  lea     rax, aDisablesite; "disablesite"
0x1800261c6  mov     qword ptr [rsp+390h+var_330+8], rax
0x1800261cb  mov     r8d, 0C0000431h
0x1800261d1  xor     r15d, r15d
0x1800261d4  mov     edx, 80070032h
0x1800261d9  mov     ebx, edx
0x1800261db  mov     rax, [rdi]
0x1800261de  lea     r9, [rsp+390h+var_330]
0x1800261e3  mov     rcx, rdi
0x1800261e6  mov     dword ptr [rsp+390h+var_370], r15d
0x1800261eb  mov     rax, [rax+90h]
0x1800261f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800261f7  jmp     loc_1800266EB
0x1800261fc  not     r14d
0x1800261ff  not     r12d
0x180026202  shr     r14d, 1Fh
0x180026206  shr     r12d, 1Fh
0x18002620a  test    r14d, r14d
0x18002620d  jz      short loc_180026229
0x18002620f  test    r12d, r12d
0x180026212  jz      short loc_180026229
0x180026214  lea     rax, aEnable; "enable"
0x18002621b  mov     qword ptr [rsp+390h+var_330], rax
0x180026220  lea     rax, aDisable; "disable"
0x180026227  jmp     short loc_1800261C6
0x180026229  test    esi, esi
0x18002622b  jnz     short loc_180026232
0x18002622d  test    r15d, r15d
0x180026230  jz      short loc_18002624D
0x180026232  cmp     [r13+0], ax
0x180026237  jnz     short loc_180026258
0x180026239  lea     r13, aSite_0; "SITE"
0x180026240  mov     r8d, 0C000041Ah
0x180026246  mov     qword ptr [rsp+390h+var_330], r13
0x18002624b  jmp     short loc_1800261D1
0x18002624d  cmp     [r13+0], ax
0x180026252  jz      loc_180026499
0x180026258  mov     rax, [rdi]
0x18002625b  lea     r9, [rbp+290h+var_2F8]
0x18002625f  mov     r8, r13
0x180026262  mov     dword ptr [rsp+390h+var_370], 4
0x18002626a  lea     r13, aSite_0; "SITE"
0x180026271  mov     rcx, rdi
0x180026274  mov     rdx, r13
0x180026277  mov     rax, [rax+40h]
0x18002627b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026280  mov     ebx, eax
0x180026282  test    eax, eax
0x180026284  js      loc_1800266E1
0x18002628a  mov     rcx, [rbp+290h+var_2F8]
0x18002628e  lea     r8, [rbp+290h+var_2E0]
0x180026292  lea     rdx, aSiteName; "SITE.NAME"
0x180026299  mov     rax, [rcx]
0x18002629c  mov     rax, [rax+50h]
0x1800262a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800262a5  mov     ebx, eax
0x1800262a7  test    eax, eax
0x1800262a9  js      loc_1800266E1
0x1800262af  test    esi, esi
0x1800262b1  jnz     loc_1800263A2
0x1800262b7  test    r15d, r15d
0x1800262ba  jnz     loc_1800263A2
0x1800262c0  mov     rcx, [rbp+290h+var_2F8]
0x1800262c4  lea     rdx, [rbp+290h+var_2F0]
0x1800262c8  mov     rax, [rcx]
0x1800262cb  mov     rax, [rax+30h]
0x1800262cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800262d4  xor     r15d, r15d
0x1800262d7  mov     ebx, eax
0x1800262d9  test    eax, eax
0x1800262db  js      loc_1800266EB
0x1800262e1  lea     rax, [rbp+290h+var_288]
0x1800262e5  mov     [rbp+290h+var_288], r15
0x1800262e9  lea     edx, [rsi+0Ah]; unsigned int
0x1800262ec  mov     [rbp+290h+String1], rax
0x1800262f0  lea     rcx, [rbp+290h+var_288]; this
0x1800262f4  mov     [rbp+290h+var_260], 20h ; ' '
0x1800262fb  mov     [rbp+290h+var_25C], 100h
0x180026301  mov     [rbp+290h+var_258], r15d
0x180026305  call    ?Resize@STRA@@QEAAJK@Z; STRA::Resize(ulong)
0x18002630a  mov     ebx, eax
0x18002630c  test    eax, eax
0x18002630e  jns     short loc_18002631E
0x180026310  lea     rcx, [rbp+290h+var_288]; this
0x180026314  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180026319  jmp     loc_1800266EB
0x18002631e  mov     eax, [rbp+290h+var_260]
0x180026321  lea     rcx, [rbp+290h+var_2E8]
0x180026325  mov     r9, [rbp+290h+String1]
0x180026329  lea     r8, aTracefailedreq_0; "traceFailedRequestsLogging.enabled"
0x180026330  mov     rdx, [rbp+290h+var_2F0]
0x180026334  shr     eax, 1
0x180026336  mov     [rbp+290h+var_2E8], eax
0x180026339  mov     rax, [rdi]
0x18002633c  mov     [rsp+390h+var_368], r15
0x180026341  mov     [rsp+390h+var_370], rcx
0x180026346  mov     rcx, rdi
0x180026349  mov     rax, [rax+58h]
0x18002634d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026352  mov     ebx, eax
0x180026354  test    eax, eax
0x180026356  js      short loc_180026310
0x180026358  mov     rcx, [rbp+290h+String1]; String1
0x18002635c  lea     rdx, aTrue; "true"
0x180026363  call    cs:__imp__wcsicmp
0x180026369  test    eax, eax
0x18002636b  jnz     short loc_180026372
0x18002636d  lea     esi, [rax+1]
0x180026370  jmp     short loc_18002638A
0x180026372  mov     rcx, [rbp+290h+String1]; String1
0x180026376  lea     rdx, aFalse; "false"
0x18002637d  call    cs:__imp__wcsicmp
0x180026383  test    eax, eax
0x180026385  jnz     short loc_180026398
0x180026387  lea     esi, [rax+2]
0x18002638a  lea     rcx, [rbp+290h+var_288]; this
0x18002638e  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180026393  jmp     loc_180026475
0x180026398  mov     ebx, 8007000Dh
0x18002639d  jmp     loc_180026310
0x1800263a2  mov     rax, [rdi]
0x1800263a5  lea     rdx, [rbp+290h+var_308]
0x1800263a9  mov     rcx, rdi
0x1800263ac  mov     rax, [rax+0C0h]
0x1800263b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800263b8  mov     ebx, eax
0x1800263ba  test    eax, eax
0x1800263bc  js      loc_1800266E1
0x1800263c2  test    esi, esi
0x1800263c4  jz      short loc_1800263F7
0x1800263c6  mov     rcx, [rbp+290h+var_308]
0x1800263ca  lea     r8, aTrue; "true"
0x1800263d1  lea     rdx, aTracefailedreq_0; "traceFailedRequestsLogging.enabled"
0x1800263d8  mov     rax, [rcx]
0x1800263db  mov     rax, [rax+38h]
0x1800263df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800263e4  xor     r15d, r15d
0x1800263e7  mov     ebx, eax
0x1800263e9  test    eax, eax
0x1800263eb  js      loc_1800266EB
0x1800263f1  lea     esi, [r15+1]
0x1800263f5  jmp     short loc_180026432
0x1800263f7  xor     esi, esi
0x1800263f9  test    r15d, r15d
0x1800263fc  jz      short loc_18002642F
0x1800263fe  mov     rcx, [rbp+290h+var_308]
0x180026402  lea     r8, aFalse; "false"
0x180026409  lea     rdx, aTracefailedreq_0; "traceFailedRequestsLogging.enabled"
0x180026410  mov     rax, [rcx]
0x180026413  mov     rax, [rax+38h]
0x180026417  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002641c  xor     r15d, r15d
0x18002641f  mov     ebx, eax
0x180026421  test    eax, eax
0x180026423  js      loc_1800266EB
0x180026429  lea     esi, [r15+2]
0x18002642d  jmp     short loc_180026432
0x18002642f  xor     r15d, r15d
0x180026432  mov     rax, [rdi]
0x180026435  lea     rcx, [rbp+290h+var_300]
0x180026439  mov     r9, [rbp+290h+var_2E0]
0x18002643d  lea     r8, aSet_0; "SET"
0x180026444  mov     [rsp+390h+var_358], r15d
0x180026449  mov     rdx, r13
0x18002644c  mov     [rsp+390h+var_360], r15
0x180026451  mov     rax, [rax+30h]
0x180026455  mov     [rsp+390h+var_368], rcx
0x18002645a  mov     rcx, [rbp+290h+var_308]
0x18002645e  mov     [rsp+390h+var_370], rcx
0x180026463  mov     rcx, rdi
0x180026466  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002646b  mov     ebx, eax
0x18002646d  test    eax, eax
0x18002646f  js      loc_1800266EB
0x180026475  cmp     esi, 2
0x180026478  jnz     short loc_180026493
0x18002647a  test    r14d, r14d
0x18002647d  jz      short loc_180026493
  ... truncated ...
```
