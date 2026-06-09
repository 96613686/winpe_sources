# TRACE_OBJECT_EXTENSION::AddTraceRule(IExtensionContext *,ICommandObject *,ICommandParameterList *,ICommandObjectList *)

- ea: `0x180025748`
- end: `0x180025fde`
- name: `?AddTraceRule@TRACE_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEAVICommandObject@@PEAVICommandParameterList@@PEAVICommandObjectList@@@Z`
- size: `2198`
- prototype: `__int64 __fastcall(TRACE_OBJECT_EXTENSION *this, struct IExtensionContext *, struct ICommandObject *, struct ICommandParameterList *, struct ICommandObjectList *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180025fe4`

## callees

- `0x180001044`
- `0x180001fb0`
- `0x180002e90`
- `0x18000557c`
- `0x180006b6c`
- `0x180025748`
- `0x180027cc0`
- `0x18002b564`
- `0x18002bd3c`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180025b66`
- `msvcrt!_wcsicmp` at `0x180025b66`

## pseudocode

```c
__int64 __fastcall TRACE_OBJECT_EXTENSION::AddTraceRule(
        TRACE_OBJECT_EXTENSION *this,
        struct IExtensionContext *a2,
        struct ICommandObject *a3,
        struct ICommandParameterList *a4,
        struct ICommandObjectList *a5)
{
  STATUS_OBJECT *v8; // rsi
  int v9; // ebx
  APP_OBJECT_UTILS *v10; // rcx
  int v11; // eax
  APP_OBJECT_UTILS *v12; // rcx
  unsigned int v13; // r15d
  wchar_t *v14; // r12
  __int64 v15; // r8
  int TraceAreaEntries; // eax
  int v17; // eax
  STATUS_OBJECT *v18; // rax
  struct INativeConfigurationElement *v20; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v21; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v22; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v23; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v24; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v25; // [rsp+68h] [rbp-98h] BYREF
  __int64 v26; // [rsp+70h] [rbp-90h] BYREF
  va_list Arguments[2]; // [rsp+78h] [rbp-88h] BYREF
  wchar_t *String1; // [rsp+88h] [rbp-78h] BYREF
  __int64 v29; // [rsp+90h] [rbp-70h] BYREF
  va_list v30; // [rsp+98h] [rbp-68h] BYREF
  va_list v31; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v32; // [rsp+A8h] [rbp-58h] BYREF
  TRACE_OBJECT_EXTENSION *v33; // [rsp+B0h] [rbp-50h]
  _BYTE v34[32]; // [rsp+B8h] [rbp-48h] BYREF
  __int16 *v35; // [rsp+D8h] [rbp-28h]
  int v36; // [rsp+E0h] [rbp-20h]
  __int16 v37; // [rsp+E4h] [rbp-1Ch]
  int v38; // [rsp+E8h] [rbp-18h]
  _BYTE v39[32]; // [rsp+F0h] [rbp-10h] BYREF
  __int16 *v40; // [rsp+110h] [rbp+10h]
  int v41; // [rsp+118h] [rbp+18h]
  __int16 v42; // [rsp+11Ch] [rbp+1Ch]
  int v43; // [rsp+120h] [rbp+20h]
  _BYTE v44[32]; // [rsp+128h] [rbp+28h] BYREF
  __int16 *v45; // [rsp+148h] [rbp+48h]
  int v46; // [rsp+150h] [rbp+50h]
  __int16 v47; // [rsp+154h] [rbp+54h]
  int v48; // [rsp+158h] [rbp+58h]
  _BYTE v49[32]; // [rsp+160h] [rbp+60h] BYREF
  wchar_t *String2; // [rsp+180h] [rbp+80h]
  int v51; // [rsp+188h] [rbp+88h]
  __int16 v52; // [rsp+18Ch] [rbp+8Ch]
  int v53; // [rsp+190h] [rbp+90h]
  _BYTE v54[32]; // [rsp+198h] [rbp+98h] BYREF
  unsigned __int16 *v55; // [rsp+1B8h] [rbp+B8h]
  int v56; // [rsp+1C0h] [rbp+C0h]
  __int16 v57; // [rsp+1C4h] [rbp+C4h]
  int v58; // [rsp+1C8h] [rbp+C8h]
  __int16 v59; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE v60[126]; // [rsp+1D2h] [rbp+D2h] BYREF
  __int16 v61; // [rsp+250h] [rbp+150h] BYREF
  _BYTE v62[510]; // [rsp+252h] [rbp+152h] BYREF
  __int16 v63; // [rsp+450h] [rbp+350h] BYREF
  _BYTE v64[510]; // [rsp+452h] [rbp+352h] BYREF
  __int16 v65; // [rsp+650h] [rbp+550h] BYREF
  _BYTE v66[510]; // [rsp+652h] [rbp+552h] BYREF
  __int16 v67; // [rsp+850h] [rbp+750h] BYREF
  _BYTE v68[510]; // [rsp+852h] [rbp+752h] BYREF

  v33 = this;
  *(_OWORD *)Arguments = 0;
  memset_0(v62, 0, sizeof(v62));
  v52 = 256;
  String2 = (wchar_t *)&v61;
  v53 = 0;
  v51 = 512;
  v61 = 0;
  memset_0(v64, 0, sizeof(v64));
  v56 = 512;
  v55 = (unsigned __int16 *)&v63;
  v57 = 256;
  v58 = 0;
  v63 = 0;
  memset_0(v66, 0, sizeof(v66));
  v46 = 512;
  v45 = &v65;
  v47 = 256;
  v48 = 0;
  v65 = 0;
  memset_0(v68, 0, sizeof(v68));
  v41 = 512;
  v40 = &v67;
  v42 = 256;
  v43 = 0;
  v67 = 0;
  memset_0(v60, 0, sizeof(v60));
  v36 = 128;
  v35 = &v59;
  v8 = 0;
  v37 = 256;
  v38 = 0;
  v59 = 0;
  v26 = 0;
  v24 = 0;
  v32 = 0;
  v22 = 0;
  v29 = 0;
  v21 = 0;
  v20 = 0;
  v25 = 0;
  String1 = 0;
  v23 = 0;
  v30 = 0;
  v31 = 0;
  if ( !a2 || !a3 || !a4 || !a5 )
  {
    v9 = -2147024809;
    goto LABEL_60;
  }
  v9 = (*(__int64 (__fastcall **)(struct ICommandObject *, __int64 *))(*(_QWORD *)a3 + 48LL))(a3, &v26);
  if ( v9 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(struct ICommandObject *, __int64 *))(*(_QWORD *)a3 + 40LL))(a3, &v29);
    if ( v9 >= 0 )
    {
      v11 = APP_OBJECT_UTILS::PopParameter(v10, a2, a4, L"path", (struct STRU *)v49, 0, 1);
      v9 = v11;
      if ( v11 >= 0 || v11 == -2147023483 && (v9 = STRU::Copy((STRU *)v49, L"*"), v9 >= 0) )
      {
        v9 = APP_OBJECT_UTILS::PopParameter(v12, a2, a4, L"areas", (struct STRU *)v54, 0, 1);
        if ( (int)(v9 + 0x80000000) < 0 || v9 == -2147023483 )
        {
          v9 = APP_OBJECT_UTILS::PopParameter(
                 (APP_OBJECT_UTILS *)0x80000000LL,
                 a2,
                 a4,
                 L"statuscodes",
                 (struct STRU *)v44,
                 0,
                 1);
          if ( (int)(v9 + 0x80000000) < 0 || v9 == -2147023483 )
          {
            v9 = APP_OBJECT_UTILS::PopParameter(
                   (APP_OBJECT_UTILS *)0x80000000LL,
                   a2,
                   a4,
                   L"verbosity",
                   (struct STRU *)v39,
                   0,
                   1);
            if ( (int)(v9 + 0x80000000) < 0 || v9 == -2147023483 )
            {
              v9 = APP_OBJECT_UTILS::PopParameter(
                     (APP_OBJECT_UTILS *)0x80000000LL,
                     a2,
                     a4,
                     L"timetaken",
                     (struct STRU *)v34,
                     0,
                     1);
              if ( (int)(v9 + 0x80000000) < 0 || v9 == -2147023483 )
              {
                v9 = APP_OBJECT_UTILS::ValidateEmptyParameters((APP_OBJECT_UTILS *)0x80000000LL, a2, a4);
                if ( v9 >= 0 )
                {
                  v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v26 + 40LL))(v26, &v21);
                  if ( v9 >= 0 )
                  {
                    v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v21 + 24LL))(v21, &v23);
                    if ( v9 >= 0 )
                    {
                      v13 = 0;
                      v14 = String2;
                      while ( v13 < v23 )
                      {
                        v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct INativeConfigurationElement **))(*(_QWORD *)v21 + 32LL))(
                               v21,
                               v13,
                               &v20);
                        if ( v9 < 0 )
                          goto LABEL_60;
                        v9 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, wchar_t **, __int64 *, _QWORD))(*(_QWORD *)v20 + 64LL))(
                               v20,
                               L"path",
                               &String1,
                               &v25,
                               0);
                        if ( v9 < 0 )
                          goto LABEL_60;
                        if ( !_wcsicmp(String1, v14) )
                          break;
                        String1 = 0;
                        (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v20 + 16LL))(v20);
                        ++v13;
                        v20 = 0;
                      }
                      if ( v20 )
                      {
                        Arguments[0] = (va_list)v14;
                        v9 = -2147024713;
                        v15 = 3221226483LL;
LABEL_29:
                        (*(void (__fastcall **)(struct IExtensionContext *, _QWORD, __int64, va_list *, _DWORD))(*(_QWORD *)a2 + 144LL))(
                          a2,
                          (unsigned int)v9,
                          v15,
                          Arguments,
                          0);
                        goto LABEL_60;
                      }
                      v9 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, struct INativeConfigurationElement **))(*(_QWORD *)v21 + 48LL))(
                             v21,
                             L"add",
                             &v20);
                      if ( v9 >= 0 )
                      {
                        v9 = (*(__int64 (__fastcall **)(struct IExtensionContext *, struct INativeConfigurationElement *, const unsigned __int16 *, wchar_t *))(*(_QWORD *)a2 + 96LL))(
                               a2,
                               v20,
                               L"path",
                               v14);
                        if ( v9 >= 0 )
                        {
                          TraceAreaEntries = TRACE_OBJECT_EXTENSION::GenerateTraceAreaEntries(v33, a2, v20, v55);
                          v9 = TraceAreaEntries;
                          if ( TraceAreaEntries == -2147024883 )
                          {
                            v9 = -2147024809;
                            v15 = 3221226513LL;
                            Arguments[0] = (va_list)L"areas";
                            Arguments[1] = (va_list)L"provider1/area1,area2;provider2/area1;...";
                            goto LABEL_29;
                          }
                          if ( TraceAreaEntries >= 0 )
                          {
                            v9 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, __int64 *))(*(_QWORD *)v20 + 32LL))(
                                   v20,
                                   L"failureDefinitions",
                                   &v22);
                            if ( v9 >= 0 )
                            {
                              if ( v48 )
                                goto LABEL_43;
                              v17 = v38;
                              if ( v38 )
                                goto LABEL_46;
                              if ( v43 )
                              {
LABEL_45:
                                if ( !v17 )
                                {
LABEL_47:
                                  if ( !v43
                                    || (v9 = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64, const unsigned __int16 *, __int16 *))(*(_QWORD *)a2 + 96LL))(
                                               a2,
                                               v22,
                                               L"verbosity",
                                               v40),
                                        v9 >= 0) )
                                  {
                                    v9 = (*(__int64 (__fastcall **)(__int64, struct INativeConfigurationElement *, __int64, __int64 *))(*(_QWORD *)v21 + 56LL))(
                                           v21,
                                           v20,
                                           0xFFFFFFFFLL,
                                           &v24);
                                    if ( v9 >= 0 )
                                    {
                                      v9 = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64, _QWORD))(*(_QWORD *)a2 + 208LL))(
                                             a2,
                                             v29,
                                             0);
                                      if ( v9 >= 0 )
                                      {
                                        v18 = (STATUS_OBJECT *)operator new(0x110u);
                                        if ( v18 && (v8 = STATUS_OBJECT::STATUS_OBJECT(v18)) != 0 )
                                        {
                                          v9 = (*(__int64 (__fastcall **)(struct ICommandObject *, va_list *))(*(_QWORD *)a3 + 24LL))(
                                                 a3,
                                                 &v30);
                                          if ( v9 >= 0 )
                                          {
                                            v9 = (*(__int64 (__fastcall **)(struct ICommandObject *, va_list *))(*(_QWORD *)a3 + 32LL))(
                                                   a3,
                                                   &v31);
                                            if ( v9 >= 0 )
                                            {
                                              Arguments[0] = v30;
                                              Arguments[1] = v31;
                                              v9 = STATUS_OBJECT::Create(v8, 0x3EEu, Arguments);
                                              if ( v9 >= 0 )
                                                v9 = (*(__int64 (__fastcall **)(struct ICommandObjectList *, STATUS_OBJECT *))(*(_QWORD *)a5 + 24LL))(
                                                       a5,
                                                       v8);
                                            }
                                          }
                                        }
                                        else
                                        {
                                          v9 = -2147024888;
                                        }
                                      }
                                    }
                                  }
                                  goto LABEL_60;
                                }
LABEL_46:
                                v9 = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64, const wchar_t *, __int16 *))(*(_QWORD *)a2 + 96LL))(
                                       a2,
                                       v22,
                                       L"timeTaken",
                                       v35);
                                if ( v9 < 0 )
                                  goto LABEL_60;
                                goto LABEL_47;
                              }
                              v9 = STRU::Copy((STRU *)v44, L"500,400,401,403");
                              if ( v9 < 0 )
                                goto LABEL_60;
                              v9 = STRU::Copy((STRU *)v34, L"00:01:00");
                              if ( v9 < 0 )
                                goto LABEL_60;
                              v9 = STRU::Copy((STRU *)v39, L"Warning");
                              if ( v9 < 0 )
                                goto LABEL_60;
                              if ( v48 )
                              {
LABEL_43:
                                v9 = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64, const wchar_t *, __int16 *))(*(_QWORD *)a2 + 96LL))(
                                       a2,
                                       v22,
                                       L"statusCodes",
                                       v45);
                                if ( v9 < 0 )
                                  goto LABEL_60;
                              }
                              v17 = v38;
                              goto LABEL_45;
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
    }
  }
LABEL_60:
  if ( v24 )
  {
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v24 + 24LL))(v24, &v32);
    (*(void (__fastcall **)(struct IExtensionContext *, _QWORD, __int64, _QWORD))(*(_QWORD *)a2 + 128LL))(
      a2,
      (unsigned int)v9,
      v32,
      0);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    v24 = 0;
  }
  if ( v25 )
  {
    (*(void (__fastcall **)(struct IExtensionContext *, _QWORD, const wchar_t *))(*(_QWORD *)a2 + 120LL))(
      a2,
      (unsigned int)v9,
      &Str);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    v25 = 0;
  }
  if ( v26 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    v26 = 0;
  }
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    v21 = 0;
  }
  if ( v20 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v20 + 16LL))(v20);
    v20 = 0;
  }
  if ( v22 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    v22 = 0;
  }
  if ( v8 )
    (*(void (__fastcall **)(STATUS_OBJECT *))(*(_QWORD *)v8 + 16LL))(v8);
  BUFFER::~BUFFER((BUFFER *)v34);
  BUFFER::~BUFFER((BUFFER *)v39);
  BUFFER::~BUFFER((BUFFER *)v44);
  BUFFER::~BUFFER((BUFFER *)v54);
  BUFFER::~BUFFER((BUFFER *)v49);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180025748  push    rbp
0x18002574a  push    rbx
0x18002574b  push    rsi
0x18002574c  push    rdi
0x18002574d  push    r12
0x18002574f  push    r13
0x180025751  push    r14
0x180025753  push    r15
0x180025755  lea     rbp, [rsp-968h]
0x18002575d  sub     rsp, 0A68h
0x180025764  mov     rax, cs:__security_cookie
0x18002576b  xor     rax, rsp
0x18002576e  mov     [rbp+9A0h+var_50], rax
0x180025775  mov     r13, [rbp+9A0h+arg_20]
0x18002577c  mov     r14, r8
0x18002577f  mov     rdi, rdx
0x180025782  mov     [rbp+9A0h+var_9F0], rcx
0x180025786  xorps   xmm0, xmm0
0x180025789  lea     rcx, [rbp+9A0h+var_84E]; void *
0x180025790  mov     esi, 1FEh
0x180025795  xor     edx, edx; Val
0x180025797  mov     r8d, esi; Size
0x18002579a  mov     r15, r9
0x18002579d  movups  xmmword ptr [rsp+0AA0h+Arguments], xmm0
0x1800257a2  call    memset_0
0x1800257a7  lea     rax, [rbp+9A0h+var_850]
0x1800257ae  mov     [rbp+9A0h+var_914], 100h
0x1800257b7  xor     r12d, r12d
0x1800257ba  mov     [rbp+9A0h+String2], rax
0x1800257c1  lea     ebx, [rsi+2]
0x1800257c4  mov     [rbp+9A0h+var_910], r12d
0x1800257cb  mov     r8d, esi; Size
0x1800257ce  mov     [rbp+9A0h+var_918], ebx
0x1800257d4  xor     edx, edx; Val
0x1800257d6  mov     [rbp+9A0h+var_850], r12w
0x1800257de  lea     rcx, [rbp+9A0h+var_64E]; void *
0x1800257e5  call    memset_0
0x1800257ea  lea     rax, [rbp+9A0h+var_650]
0x1800257f1  mov     [rbp+9A0h+var_8E0], ebx
0x1800257f7  mov     r8d, esi; Size
0x1800257fa  mov     [rbp+9A0h+var_8E8], rax
0x180025801  xor     edx, edx; Val
0x180025803  mov     [rbp+9A0h+var_8DC], 100h
0x18002580c  lea     rcx, [rbp+9A0h+var_44E]; void *
0x180025813  mov     [rbp+9A0h+var_8D8], r12d
0x18002581a  mov     [rbp+9A0h+var_650], r12w
0x180025822  call    memset_0
0x180025827  lea     rax, [rbp+9A0h+var_450]
0x18002582e  mov     [rbp+9A0h+var_950], ebx
0x180025831  mov     r8d, esi; Size
0x180025834  mov     [rbp+9A0h+var_958], rax
0x180025838  xor     edx, edx; Val
0x18002583a  mov     [rbp+9A0h+var_94C], 100h
0x180025840  lea     rcx, [rbp+9A0h+var_24E]; void *
0x180025847  mov     [rbp+9A0h+var_948], r12d
0x18002584b  mov     [rbp+9A0h+var_450], r12w
0x180025853  call    memset_0
0x180025858  lea     rax, [rbp+9A0h+var_250]
0x18002585f  mov     [rbp+9A0h+var_988], ebx
0x180025862  xor     edx, edx; Val
0x180025864  mov     [rbp+9A0h+var_990], rax
0x180025868  lea     r8d, [r12+7Eh]; Size
0x18002586d  mov     [rbp+9A0h+var_984], 100h
0x180025873  lea     rcx, [rbp+9A0h+var_8CE]; void *
0x18002587a  mov     [rbp+9A0h+var_980], r12d
0x18002587e  mov     [rbp+9A0h+var_250], r12w
0x180025886  call    memset_0
0x18002588b  mov     [rbp+9A0h+var_9C0], 80h
0x180025892  lea     rax, [rbp+9A0h+var_8D0]
0x180025899  mov     [rbp+9A0h+var_9C8], rax
0x18002589d  mov     esi, r12d
0x1800258a0  mov     [rbp+9A0h+var_9BC], 100h
0x1800258a6  mov     [rbp+9A0h+var_9B8], r12d
0x1800258aa  mov     [rbp+9A0h+var_8D0], r12w
0x1800258b2  mov     [rsp+0AA0h+var_A30], r12
0x1800258b7  mov     [rsp+0AA0h+var_A40], r12
0x1800258bc  mov     [rbp+9A0h+var_9F8], r12
0x1800258c0  mov     [rsp+0AA0h+var_A50], r12
0x1800258c5  mov     [rbp+9A0h+var_A10], r12
0x1800258c9  mov     [rsp+0AA0h+var_A58], r12
0x1800258ce  mov     [rsp+0AA0h+var_A60], r12
0x1800258d3  mov     [rsp+0AA0h+var_A38], r12
0x1800258d8  mov     [rbp+9A0h+String1], r12
0x1800258dc  mov     [rsp+0AA0h+var_A48], r12d
0x1800258e1  mov     [rbp+9A0h+var_A08], r12
0x1800258e5  mov     [rbp+9A0h+var_A00], r12
0x1800258e9  test    rdi, rdi
0x1800258ec  jz      loc_180025E7C
0x1800258f2  test    r14, r14
0x1800258f5  jz      loc_180025E7C
0x1800258fb  test    r15, r15
0x1800258fe  jz      loc_180025E7C
0x180025904  test    r13, r13
0x180025907  jz      loc_180025E7C
0x18002590d  mov     rax, [r14]
0x180025910  lea     rdx, [rsp+0AA0h+var_A30]
0x180025915  mov     rcx, r14
0x180025918  mov     rax, [rax+30h]
0x18002591c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025921  mov     ebx, eax
0x180025923  test    eax, eax
0x180025925  js      loc_180025E81
0x18002592b  mov     rax, [r14]
0x18002592e  lea     rdx, [rbp+9A0h+var_A10]
0x180025932  mov     rcx, r14
0x180025935  mov     rax, [rax+28h]
0x180025939  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002593e  mov     ebx, eax
0x180025940  test    eax, eax
0x180025942  js      loc_180025E81
0x180025948  mov     [rsp+0AA0h+var_A70], 1; int
0x180025950  lea     rax, [rbp+9A0h+var_940]
0x180025954  mov     [rsp+0AA0h+var_A78], r12d; int
0x180025959  lea     r9, aPath_1; "path"
0x180025960  mov     r8, r15; struct ICommandParameterList *
0x180025963  mov     [rsp+0AA0h+var_A80], rax; struct STRU *
0x180025968  mov     rdx, rdi; struct IExtensionContext *
0x18002596b  call    ?PopParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAVSTRU@@HH@Z; APP_OBJECT_UTILS::PopParameter(IExtensionContext *,ICommandParameterList *,ushort const *,STRU *,int,int)
0x180025970  mov     ebx, eax
0x180025972  test    eax, eax
0x180025974  jns     short loc_18002599B
0x180025976  cmp     eax, 80070585h
0x18002597b  jnz     loc_180025E81
0x180025981  lea     rdx, asc_1800397FC; "*"
0x180025988  lea     rcx, [rbp+9A0h+var_940]; this
0x18002598c  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180025991  mov     ebx, eax
0x180025993  test    eax, eax
0x180025995  js      loc_180025E81
0x18002599b  mov     [rsp+0AA0h+var_A70], 1; int
0x1800259a3  lea     rax, [rbp+9A0h+var_908]
0x1800259aa  mov     [rsp+0AA0h+var_A78], r12d; int
0x1800259af  lea     r9, aAreas; "areas"
0x1800259b6  mov     r8, r15; struct ICommandParameterList *
0x1800259b9  mov     [rsp+0AA0h+var_A80], rax; struct STRU *
0x1800259be  mov     rdx, rdi; struct IExtensionContext *
0x1800259c1  call    ?PopParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAVSTRU@@HH@Z; APP_OBJECT_UTILS::PopParameter(IExtensionContext *,ICommandParameterList *,ushort const *,STRU *,int,int)
0x1800259c6  mov     ecx, 80000000h; this
0x1800259cb  mov     ebx, eax
0x1800259cd  add     eax, ecx
0x1800259cf  test    ecx, eax
0x1800259d1  jnz     short loc_1800259DF
0x1800259d3  cmp     ebx, 80070585h
0x1800259d9  jnz     loc_180025E81
0x1800259df  mov     [rsp+0AA0h+var_A70], 1; int
0x1800259e7  lea     rax, [rbp+9A0h+var_978]
0x1800259eb  mov     [rsp+0AA0h+var_A78], r12d; int
0x1800259f0  lea     r9, aStatuscodes_0; "statuscodes"
0x1800259f7  mov     r8, r15; struct ICommandParameterList *
0x1800259fa  mov     [rsp+0AA0h+var_A80], rax; struct STRU *
0x1800259ff  mov     rdx, rdi; struct IExtensionContext *
0x180025a02  call    ?PopParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAVSTRU@@HH@Z; APP_OBJECT_UTILS::PopParameter(IExtensionContext *,ICommandParameterList *,ushort const *,STRU *,int,int)
0x180025a07  mov     ecx, 80000000h; this
0x180025a0c  mov     ebx, eax
0x180025a0e  add     eax, ecx
0x180025a10  test    ecx, eax
0x180025a12  jnz     short loc_180025A20
0x180025a14  cmp     ebx, 80070585h
0x180025a1a  jnz     loc_180025E81
0x180025a20  mov     [rsp+0AA0h+var_A70], 1; int
0x180025a28  lea     rax, [rbp+9A0h+var_9B0]
0x180025a2c  mov     [rsp+0AA0h+var_A78], r12d; int
0x180025a31  lea     r9, aVerbosity; "verbosity"
0x180025a38  mov     r8, r15; struct ICommandParameterList *
0x180025a3b  mov     [rsp+0AA0h+var_A80], rax; struct STRU *
0x180025a40  mov     rdx, rdi; struct IExtensionContext *
0x180025a43  call    ?PopParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAVSTRU@@HH@Z; APP_OBJECT_UTILS::PopParameter(IExtensionContext *,ICommandParameterList *,ushort const *,STRU *,int,int)
0x180025a48  mov     ecx, 80000000h; this
0x180025a4d  mov     ebx, eax
0x180025a4f  add     eax, ecx
0x180025a51  test    ecx, eax
0x180025a53  jnz     short loc_180025A61
0x180025a55  cmp     ebx, 80070585h
0x180025a5b  jnz     loc_180025E81
0x180025a61  mov     [rsp+0AA0h+var_A70], 1; int
0x180025a69  lea     rax, [rbp+9A0h+var_9E8]
0x180025a6d  mov     [rsp+0AA0h+var_A78], r12d; int
0x180025a72  lea     r9, aTimetaken; "timetaken"
0x180025a79  mov     r8, r15; struct ICommandParameterList *
0x180025a7c  mov     [rsp+0AA0h+var_A80], rax; struct STRU *
0x180025a81  mov     rdx, rdi; struct IExtensionContext *
0x180025a84  call    ?PopParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAVSTRU@@HH@Z; APP_OBJECT_UTILS::PopParameter(IExtensionContext *,ICommandParameterList *,ushort const *,STRU *,int,int)
0x180025a89  mov     ecx, 80000000h; this
0x180025a8e  mov     ebx, eax
0x180025a90  add     eax, ecx
0x180025a92  test    ecx, eax
0x180025a94  jnz     short loc_180025AA2
0x180025a96  cmp     ebx, 80070585h
0x180025a9c  jnz     loc_180025E81
0x180025aa2  mov     r8, r15; struct ICommandParameterList *
0x180025aa5  mov     rdx, rdi; struct IExtensionContext *
0x180025aa8  call    ?ValidateEmptyParameters@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@@Z; APP_OBJECT_UTILS::ValidateEmptyParameters(IExtensionContext *,ICommandParameterList *)
0x180025aad  mov     ebx, eax
0x180025aaf  test    eax, eax
0x180025ab1  js      loc_180025E81
0x180025ab7  mov     rcx, [rsp+0AA0h+var_A30]
0x180025abc  lea     rdx, [rsp+0AA0h+var_A58]
0x180025ac1  mov     rax, [rcx]
0x180025ac4  mov     rax, [rax+28h]
0x180025ac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025acd  mov     ebx, eax
0x180025acf  test    eax, eax
0x180025ad1  js      loc_180025E81
0x180025ad7  mov     rcx, [rsp+0AA0h+var_A58]
0x180025adc  lea     rdx, [rsp+0AA0h+var_A48]
0x180025ae1  mov     rax, [rcx]
0x180025ae4  mov     rax, [rax+18h]
0x180025ae8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025aed  mov     ebx, eax
0x180025aef  test    eax, eax
0x180025af1  js      loc_180025E81
0x180025af7  mov     r15d, r12d
0x180025afa  mov     r12, [rbp+9A0h+String2]
0x180025b01  cmp     r15d, [rsp+0AA0h+var_A48]
0x180025b06  jnb     loc_180025B92
0x180025b0c  mov     rcx, [rsp+0AA0h+var_A58]
0x180025b11  lea     r8, [rsp+0AA0h+var_A60]
0x180025b16  mov     edx, r15d
0x180025b19  mov     rax, [rcx]
0x180025b1c  mov     rax, [rax+20h]
0x180025b20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b25  mov     ebx, eax
0x180025b27  test    eax, eax
0x180025b29  js      loc_180025E77
0x180025b2f  mov     rcx, [rsp+0AA0h+var_A60]
0x180025b34  lea     r9, [rsp+0AA0h+var_A38]
0x180025b39  lea     r8, [rbp+9A0h+String1]
0x180025b3d  mov     [rsp+0AA0h+var_A80], rsi
0x180025b42  lea     rdx, aPath_1; "path"
0x180025b49  mov     rax, [rcx]
0x180025b4c  mov     rax, [rax+40h]
0x180025b50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b55  mov     ebx, eax
0x180025b57  test    eax, eax
0x180025b59  js      loc_180025E77
0x180025b5f  mov     rcx, [rbp+9A0h+String1]; String1
0x180025b63  mov     rdx, r12; String2
0x180025b66  call    cs:__imp__wcsicmp
0x180025b6c  test    eax, eax
0x180025b6e  jz      short loc_180025B92
0x180025b70  mov     rcx, [rsp+0AA0h+var_A60]
0x180025b75  mov     [rbp+9A0h+String1], rsi
0x180025b79  mov     rax, [rcx]
0x180025b7c  mov     rax, [rax+10h]
0x180025b80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b85  inc     r15d
0x180025b88  mov     [rsp+0AA0h+var_A60], rsi
0x180025b8d  jmp     loc_180025B01
0x180025b92  cmp     [rsp+0AA0h+var_A60], rsi
0x180025b97  jz      short loc_180025BCF
0x180025b99  mov     [rsp+0AA0h+Arguments], r12
0x180025b9e  mov     ebx, 800700B7h
0x180025ba3  xor     r12d, r12d
0x180025ba6  mov     r8d, 0C00003F3h
0x180025bac  mov     rax, [rdi]
0x180025baf  lea     r9, [rsp+0AA0h+Arguments]
0x180025bb4  mov     edx, ebx
0x180025bb6  mov     dword ptr [rsp+0AA0h+var_A80], r12d
0x180025bbb  mov     rcx, rdi
0x180025bbe  mov     rax, [rax+90h]
0x180025bc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025bca  jmp     loc_180025E81
0x180025bcf  mov     rcx, [rsp+0AA0h+var_A58]
0x180025bd4  lea     r8, [rsp+0AA0h+var_A60]
0x180025bd9  lea     rdx, aAdd; "add"
0x180025be0  mov     rax, [rcx]
0x180025be3  mov     rax, [rax+30h]
0x180025be7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025bec  mov     ebx, eax
0x180025bee  test    eax, eax
0x180025bf0  js      loc_180025E77
0x180025bf6  mov     rax, [rdi]
0x180025bf9  lea     r8, aPath_1; "path"
0x180025c00  mov     rdx, [rsp+0AA0h+var_A60]
0x180025c05  mov     r9, r12
0x180025c08  mov     rcx, rdi
0x180025c0b  mov     rax, [rax+60h]
0x180025c0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c14  xor     r12d, r12d
0x180025c17  mov     ebx, eax
0x180025c19  test    eax, eax
0x180025c1b  js      loc_180025E81
0x180025c21  mov     r9, [rbp+9A0h+var_8E8]; unsigned __int16 *
0x180025c28  mov     rdx, rdi; struct IExtensionContext *
0x180025c2b  mov     r8, [rsp+0AA0h+var_A60]; struct INativeConfigurationElement *
0x180025c30  mov     rcx, [rbp+9A0h+var_9F0]; this
0x180025c34  call    ?GenerateTraceAreaEntries@TRACE_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEAVINativeConfigurationElement@@PEBG@Z; TRACE_OBJECT_EXTENSION::GenerateTraceAreaEntries(IExtensionContext *,INativeConfigurationElement *,ushort const *)
0x180025c39  mov     ebx, eax
0x180025c3b  cmp     eax, 8007000Dh
0x180025c40  jnz     short loc_180025C67
0x180025c42  lea     ebx, [rax+4Ah]
0x180025c45  mov     r8d, 0C0000411h
0x180025c4b  lea     rax, aAreas; "areas"
0x180025c52  mov     [rsp+0AA0h+Arguments], rax
0x180025c57  lea     rax, aProvider1Area1; "provider1/area1,area2;provider2/area1;."...
0x180025c5e  mov     [rbp+9A0h+Arguments+8], rax
0x180025c62  jmp     loc_180025BAC
0x180025c67  test    eax, eax
0x180025c69  js      loc_180025E81
0x180025c6f  mov     rcx, [rsp+0AA0h+var_A60]
  ... truncated ...
```
