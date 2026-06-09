# VDIR_OBJECT_EXTENSION::AddDir(IExtensionContext *,ushort const *,ICommandParameterList *,ICommandObjectList *,IXMLDOMDocument *)

- ea: `0x180015398`
- end: `0x18001583b`
- name: `?AddDir@VDIR_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEBGPEAVICommandParameterList@@PEAVICommandObjectList@@PEAUIXMLDOMDocument@@@Z`
- size: `1187`
- prototype: `__int64 __fastcall(VDIR_OBJECT_EXTENSION *this, struct IExtensionContext *, const unsigned __int16 *, struct ICommandParameterList *, struct ICommandObjectList *, struct IXMLDOMDocument *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180016200`

## callees

- `0x180001044`
- `0x180015138`
- `0x18001534c`
- `0x180015398`
- `0x180015844`
- `0x180016cd0`
- `0x18002a6cc`
- `0x180036010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800154f0`
- `msvcrt!_wcsicmp` at `0x1800154f0`

## string_xrefs

- `0x180015564`: `virtualDirectory`

## pseudocode

```c
__int64 __fastcall VDIR_OBJECT_EXTENSION::AddDir(
        VDIR_OBJECT_EXTENSION *this,
        struct IExtensionContext *a2,
        const unsigned __int16 *a3,
        struct ICommandParameterList *a4,
        struct ICommandObjectList *a5,
        struct IXMLDOMDocument *a6)
{
  struct APP_OBJECT *v7; // rdi
  int v8; // ebx
  int v9; // eax
  __int64 v10; // r8
  __int64 v11; // rdx
  VDIR_OBJECT *v12; // rax
  VDIR_OBJECT *v13; // rax
  APP_OBJECT_EXTENSION *v14; // rcx
  int v15; // eax
  unsigned __int16 *v16; // rcx
  APP_OBJECT_UTILS *v17; // rcx
  unsigned int v18; // r8d
  unsigned __int16 *v20[2]; // [rsp+40h] [rbp-39h] BYREF
  struct ICommandParameterList *v21; // [rsp+50h] [rbp-29h] BYREF
  struct INativeConfigurationElement *v22; // [rsp+58h] [rbp-21h] BYREF
  __int64 v23; // [rsp+60h] [rbp-19h] BYREF
  __int64 v24; // [rsp+68h] [rbp-11h] BYREF
  wchar_t *String2; // [rsp+70h] [rbp-9h] BYREF
  unsigned __int16 *v26; // [rsp+78h] [rbp-1h] BYREF
  wchar_t *String1; // [rsp+80h] [rbp+7h] BYREF
  unsigned __int16 *v28; // [rsp+88h] [rbp+Fh] BYREF
  unsigned __int16 *v29; // [rsp+90h] [rbp+17h] BYREF
  unsigned __int16 *v30; // [rsp+98h] [rbp+1Fh] BYREF
  struct INativeConfigurationElement *v31; // [rsp+D0h] [rbp+57h] BYREF
  __int64 v32; // [rsp+D8h] [rbp+5Fh] BYREF

  v32 = 0;
  v22 = 0;
  v7 = 0;
  v31 = 0;
  v23 = 0;
  v24 = 0;
  v29 = 0;
  String2 = 0;
  String1 = 0;
  v26 = 0;
  v28 = 0;
  v30 = 0;
  v21 = 0;
  *(_OWORD *)v20 = 0;
  if ( a2 && a3 && a4 && a5 )
  {
    v8 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, struct ICommandParameterList **))(*(_QWORD *)a4 + 80LL))(
           a4,
           &v21);
    if ( v8 < 0 )
      goto LABEL_38;
    v9 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v21 + 40LL))(
           v21,
           L"APP.NAME",
           &String2);
    v8 = v9;
    if ( v9 == -2147023483 )
    {
      v8 = -2147024894;
      v20[0] = L"APP.NAME";
      v10 = 3221226486LL;
LABEL_8:
      v11 = (unsigned int)v8;
LABEL_9:
      (*(void (__fastcall **)(struct IExtensionContext *, __int64, __int64, unsigned __int16 **, _DWORD))(*(_QWORD *)a2 + 144LL))(
        a2,
        v11,
        v10,
        v20,
        0);
      goto LABEL_38;
    }
    if ( v9 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(struct IExtensionContext *, const unsigned __int16 *, wchar_t *, __int64 *, int))(*(_QWORD *)a2 + 64LL))(
             a2,
             L"APP",
             String2,
             &v32,
             4);
      if ( v8 >= 0 )
      {
        v8 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v32 + 80LL))(
               v32,
               L"APP.NAME",
               &String1);
        if ( v8 >= 0 )
        {
          if ( _wcsicmp(String1, String2) )
          {
            v8 = -2147024846;
            v20[0] = L"VDIR";
            v10 = 3221226508LL;
            v20[1] = L"ADD";
            goto LABEL_8;
          }
          v8 = (*(__int64 (__fastcall **)(__int64, struct INativeConfigurationElement **))(*(_QWORD *)v32 + 48LL))(
                 v32,
                 &v22);
          if ( v8 >= 0 )
          {
            v8 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 *))(*(_QWORD *)v22 + 40LL))(
                   v22,
                   &v23);
            if ( v8 >= 0 )
            {
              v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, struct INativeConfigurationElement **))(*(_QWORD *)v23 + 48LL))(
                     v23,
                     L"virtualDirectory",
                     &v31);
              if ( v8 >= 0 )
              {
                v12 = (VDIR_OBJECT *)operator new(0xD8u);
                if ( v12 && (v13 = VDIR_OBJECT::VDIR_OBJECT(v12, v31, v22), (v7 = v13) != 0) )
                {
                  v8 = VDIR_OBJECT::Reset(v13);
                  if ( v8 >= 0 )
                  {
                    v8 = APP_OBJECT_EXTENSION::SetApp(v14, a2, v7, v21, 0, a6, 1);
                    if ( v8 >= 0 )
                    {
                      v15 = (*(__int64 (__fastcall **)(__int64, struct INativeConfigurationElement *, __int64, __int64 *))(*(_QWORD *)v23 + 56LL))(
                              v23,
                              v31,
                              0xFFFFFFFFLL,
                              &v24);
                      v8 = v15;
                      if ( v15 >= 0 )
                      {
                        v8 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v32 + 40LL))(
                               v32,
                               &v26);
                        if ( v8 >= 0 )
                        {
                          v8 = VDIR_OBJECT::Create(v7, String2, v26);
                          if ( v8 >= 0 )
                          {
                            v8 = (*(__int64 (__fastcall **)(struct APP_OBJECT *, const unsigned __int16 *, unsigned __int16 **))(*(_QWORD *)v7 + 80LL))(
                                   v7,
                                   L"VDIR.NAME",
                                   &v30);
                            if ( v8 >= 0 )
                            {
                              v8 = (*(__int64 (__fastcall **)(struct IExtensionContext *, unsigned __int16 *, _QWORD))(*(_QWORD *)a2 + 208LL))(
                                     a2,
                                     v26,
                                     0);
                              if ( v8 >= 0 )
                              {
                                v20[0] = L"VDIR";
                                v20[1] = v30;
                                v8 = APP_OBJECT_UTILS::AddStatusObject(
                                       v17,
                                       a5,
                                       v18,
                                       (const unsigned __int16 **const)v20);
                              }
                            }
                          }
                        }
                      }
                      else
                      {
                        if ( v15 == -2147024713 )
                        {
                          (*(void (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v31 + 64LL))(
                            v31,
                            L"path",
                            &v28,
                            0,
                            0);
                          v16 = L"Unknown";
                          v20[1] = 0;
                          v11 = (unsigned int)v8;
                          v10 = 3221226483LL;
                          if ( v28 )
                            v16 = v28;
                          v20[0] = v16;
                          goto LABEL_9;
                        }
                        if ( v24 )
                        {
                          (*(void (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v24 + 24LL))(v24, &v29);
                          if ( v29 )
                          {
                            v20[1] = v29;
                            v20[0] = L"VDIR";
                            (*(void (__fastcall **)(struct IExtensionContext *, _QWORD, __int64, unsigned __int16 **, _DWORD))(*(_QWORD *)a2 + 144LL))(
                              a2,
                              (unsigned int)v8,
                              3221226480LL,
                              v20,
                              0);
                          }
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
                          v24 = 0;
                        }
                      }
                    }
                  }
                }
                else
                {
                  v8 = -2147024888;
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
    v8 = -2147024809;
  }
LABEL_38:
  if ( v21 )
  {
    (*(void (__fastcall **)(struct ICommandParameterList *))(*(_QWORD *)v21 + 16LL))(v21);
    v21 = 0;
  }
  if ( v31 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v31 + 16LL))(v31);
    v31 = 0;
  }
  if ( v7 )
    (*(void (__fastcall **)(struct APP_OBJECT *))(*(_QWORD *)v7 + 16LL))(v7);
  if ( v32 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    v32 = 0;
  }
  if ( v22 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v22 + 16LL))(v22);
    v22 = 0;
  }
  if ( v23 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v23 = 0;
  }
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180015398  mov     [rsp-8+arg_10], rbx
0x18001539d  mov     [rsp-8+arg_0], rcx
0x1800153a2  push    rbp
0x1800153a3  push    rsi
0x1800153a4  push    rdi
0x1800153a5  push    r12
0x1800153a7  push    r15
0x1800153a9  lea     rbp, [rsp-27h]
0x1800153ae  sub     rsp, 0A0h
0x1800153b5  xor     r15d, r15d
0x1800153b8  xorps   xmm0, xmm0
0x1800153bb  mov     [rbp+47h+arg_8], r15
0x1800153bf  mov     rsi, rdx
0x1800153c2  mov     [rbp+47h+var_68], r15
0x1800153c6  mov     edi, r15d
0x1800153c9  mov     [rbp+47h+arg_0], r15
0x1800153cd  mov     [rbp+47h+var_60], r15
0x1800153d1  mov     [rbp+47h+var_58], r15
0x1800153d5  mov     [rbp+47h+var_30], r15
0x1800153d9  mov     [rbp+47h+String2], r15
0x1800153dd  mov     [rbp+47h+String1], r15
0x1800153e1  mov     [rbp+47h+var_48], r15
0x1800153e5  mov     [rbp+47h+var_38], r15
0x1800153e9  mov     [rbp+47h+var_28], r15
0x1800153ed  mov     [rbp+47h+var_70], r15
0x1800153f1  movups  xmmword ptr [rbp+47h+var_80], xmm0
0x1800153f5  test    rdx, rdx
0x1800153f8  jz      loc_180015777
0x1800153fe  test    r8, r8
0x180015401  jz      loc_180015777
0x180015407  test    r9, r9
0x18001540a  jz      loc_180015777
0x180015410  cmp     [rbp+47h+arg_20], r15
0x180015414  jz      loc_180015777
0x18001541a  mov     rax, [r9]
0x18001541d  lea     rdx, [rbp+47h+var_70]
0x180015421  mov     rcx, r9
0x180015424  mov     rax, [rax+50h]
0x180015428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001542d  mov     ebx, eax
0x18001542f  test    eax, eax
0x180015431  js      loc_18001577C
0x180015437  mov     rcx, [rbp+47h+var_70]
0x18001543b  lea     r12, aAppName_0; "APP.NAME"
0x180015442  lea     r8, [rbp+47h+String2]
0x180015446  mov     rdx, r12
0x180015449  mov     rax, [rcx]
0x18001544c  mov     rax, [rax+28h]
0x180015450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015455  mov     ebx, eax
0x180015457  cmp     eax, 80070585h
0x18001545c  jnz     short loc_18001548F
0x18001545e  mov     ebx, 80070002h
0x180015463  mov     [rbp+47h+var_80], r12
0x180015467  mov     r8d, 0C00003F6h
0x18001546d  mov     edx, ebx
0x18001546f  mov     rax, [rsi]
0x180015472  lea     r9, [rbp+47h+var_80]
0x180015476  mov     rcx, rsi
0x180015479  mov     dword ptr [rsp+0C0h+var_A0], r15d
0x18001547e  mov     rax, [rax+90h]
0x180015485  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001548a  jmp     loc_18001577C
0x18001548f  test    eax, eax
0x180015491  js      loc_18001577C
0x180015497  mov     rax, [rsi]
0x18001549a  lea     r9, [rbp+47h+arg_8]
0x18001549e  mov     r8, [rbp+47h+String2]
0x1800154a2  lea     rdx, aApp_0; "APP"
0x1800154a9  mov     rcx, rsi
0x1800154ac  mov     dword ptr [rsp+0C0h+var_A0], 4
0x1800154b4  mov     rax, [rax+40h]
0x1800154b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154bd  mov     ebx, eax
0x1800154bf  test    eax, eax
0x1800154c1  js      loc_18001577C
0x1800154c7  mov     rcx, [rbp+47h+arg_8]
0x1800154cb  lea     r8, [rbp+47h+String1]
0x1800154cf  mov     rdx, r12
0x1800154d2  mov     rax, [rcx]
0x1800154d5  mov     rax, [rax+50h]
0x1800154d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154de  mov     ebx, eax
0x1800154e0  test    eax, eax
0x1800154e2  js      loc_18001577C
0x1800154e8  mov     rdx, [rbp+47h+String2]; String2
0x1800154ec  mov     rcx, [rbp+47h+String1]; String1
0x1800154f0  call    cs:__imp__wcsicmp
0x1800154f6  test    eax, eax
0x1800154f8  jz      short loc_180015520
0x1800154fa  lea     rax, aVdir; "VDIR"
0x180015501  mov     ebx, 80070032h
0x180015506  mov     [rbp+47h+var_80], rax
0x18001550a  mov     r8d, 0C000040Ch
0x180015510  lea     rax, aAdd_0; "ADD"
0x180015517  mov     [rbp+47h+var_80+8], rax
0x18001551b  jmp     loc_18001546D
0x180015520  mov     rcx, [rbp+47h+arg_8]
0x180015524  lea     rdx, [rbp+47h+var_68]
0x180015528  mov     rax, [rcx]
0x18001552b  mov     rax, [rax+30h]
0x18001552f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015534  mov     ebx, eax
0x180015536  test    eax, eax
0x180015538  js      loc_18001577C
0x18001553e  mov     rcx, [rbp+47h+var_68]
0x180015542  lea     rdx, [rbp+47h+var_60]
0x180015546  mov     rax, [rcx]
0x180015549  mov     rax, [rax+28h]
0x18001554d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015552  mov     ebx, eax
0x180015554  test    eax, eax
0x180015556  js      loc_18001577C
0x18001555c  mov     rcx, [rbp+47h+var_60]
0x180015560  lea     r8, [rbp+47h+arg_0]
0x180015564  lea     rdx, aVirtualdirecto; "virtualDirectory"
0x18001556b  mov     rax, [rcx]
0x18001556e  mov     rax, [rax+30h]
0x180015572  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015577  mov     ebx, eax
0x180015579  test    eax, eax
0x18001557b  js      loc_18001577C
0x180015581  mov     ecx, 0D8h; Size
0x180015586  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001558b  test    rax, rax
0x18001558e  jz      loc_180015770
0x180015594  mov     r8, [rbp+47h+var_68]; struct INativeConfigurationElement *
0x180015598  mov     rcx, rax; this
0x18001559b  mov     rdx, [rbp+47h+arg_0]; struct INativeConfigurationElement *
0x18001559f  call    ??0VDIR_OBJECT@@QEAA@PEAVINativeConfigurationElement@@0@Z; VDIR_OBJECT::VDIR_OBJECT(INativeConfigurationElement *,INativeConfigurationElement *)
0x1800155a4  mov     rdi, rax
0x1800155a7  test    rax, rax
0x1800155aa  jz      loc_180015770
0x1800155b0  mov     rcx, rax; this
0x1800155b3  call    ?Reset@VDIR_OBJECT@@QEAAJXZ; VDIR_OBJECT::Reset(void)
0x1800155b8  mov     ebx, eax
0x1800155ba  test    eax, eax
0x1800155bc  js      loc_18001577C
0x1800155c2  mov     rax, [rbp+47h+arg_28]
0x1800155c6  mov     r8, rdi; struct APP_OBJECT *
0x1800155c9  mov     r9, [rbp+47h+var_70]; struct ICommandParameterList *
0x1800155cd  mov     rdx, rsi; struct IExtensionContext *
0x1800155d0  mov     [rsp+0C0h+var_90], 1; int
0x1800155d8  mov     [rsp+0C0h+var_98], rax; struct IXMLDOMDocument *
0x1800155dd  mov     [rsp+0C0h+var_A0], r15; struct ICommandObjectList *
0x1800155e2  call    ?SetApp@APP_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEAVAPP_OBJECT@@PEAVICommandParameterList@@PEAVICommandObjectList@@PEAUIXMLDOMDocument@@H@Z; APP_OBJECT_EXTENSION::SetApp(IExtensionContext *,APP_OBJECT *,ICommandParameterList *,ICommandObjectList *,IXMLDOMDocument *,int)
0x1800155e7  mov     ebx, eax
0x1800155e9  test    eax, eax
0x1800155eb  js      loc_18001577C
0x1800155f1  mov     rcx, [rbp+47h+var_60]
0x1800155f5  lea     r9, [rbp+47h+var_58]
0x1800155f9  mov     rdx, [rbp+47h+arg_0]
0x1800155fd  or      r8d, 0FFFFFFFFh
0x180015601  mov     rax, [rcx]
0x180015604  mov     rax, [rax+38h]
0x180015608  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001560d  mov     ebx, eax
0x18001560f  test    eax, eax
0x180015611  jns     loc_1800156D9
0x180015617  cmp     eax, 800700B7h
0x18001561c  jnz     short loc_180015668
0x18001561e  mov     rcx, [rbp+47h+arg_0]
0x180015622  lea     r8, [rbp+47h+var_38]
0x180015626  xor     r9d, r9d
0x180015629  mov     [rsp+0C0h+var_A0], r15
0x18001562e  lea     rdx, aPath_1; "path"
0x180015635  mov     rax, [rcx]
0x180015638  mov     rax, [rax+40h]
0x18001563c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015641  mov     rax, [rbp+47h+var_38]
0x180015645  lea     rcx, aUnknown_0; "Unknown"
0x18001564c  test    rax, rax
0x18001564f  mov     [rbp+47h+var_80+8], r15
0x180015653  mov     edx, ebx
0x180015655  mov     r8d, 0C00003F3h
0x18001565b  cmovnz  rcx, rax
0x18001565f  mov     [rbp+47h+var_80], rcx
0x180015663  jmp     loc_18001546F
0x180015668  mov     rcx, [rbp+47h+var_58]
0x18001566c  test    rcx, rcx
0x18001566f  jz      loc_18001577C
0x180015675  mov     rax, [rcx]
0x180015678  lea     rdx, [rbp+47h+var_30]
0x18001567c  mov     rax, [rax+18h]
0x180015680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015685  mov     rcx, [rbp+47h+var_30]
0x180015689  test    rcx, rcx
0x18001568c  jz      short loc_1800156C0
0x18001568e  lea     rax, aVdir; "VDIR"
0x180015695  mov     [rbp+47h+var_80+8], rcx
0x180015699  mov     [rbp+47h+var_80], rax
0x18001569d  lea     r9, [rbp+47h+var_80]
0x1800156a1  mov     rax, [rsi]
0x1800156a4  mov     r8d, 0C00003F0h
0x1800156aa  mov     edx, ebx
0x1800156ac  mov     dword ptr [rsp+0C0h+var_A0], r15d
0x1800156b1  mov     rcx, rsi
0x1800156b4  mov     rax, [rax+90h]
0x1800156bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156c0  mov     rcx, [rbp+47h+var_58]
0x1800156c4  mov     rax, [rcx]
0x1800156c7  mov     rax, [rax+10h]
0x1800156cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156d0  mov     [rbp+47h+var_58], r15
0x1800156d4  jmp     loc_18001577C
0x1800156d9  mov     rcx, [rbp+47h+arg_8]
0x1800156dd  lea     rdx, [rbp+47h+var_48]
0x1800156e1  mov     rax, [rcx]
0x1800156e4  mov     rax, [rax+28h]
0x1800156e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156ed  mov     ebx, eax
0x1800156ef  test    eax, eax
0x1800156f1  js      loc_18001577C
0x1800156f7  mov     r8, [rbp+47h+var_48]; unsigned __int16 *
0x1800156fb  mov     rcx, rdi; this
0x1800156fe  mov     rdx, [rbp+47h+String2]; unsigned __int16 *
0x180015702  call    ?Create@VDIR_OBJECT@@QEAAJPEBG0@Z; VDIR_OBJECT::Create(ushort const *,ushort const *)
0x180015707  mov     ebx, eax
0x180015709  test    eax, eax
0x18001570b  js      short loc_18001577C
0x18001570d  mov     rax, [rdi]
0x180015710  lea     r8, [rbp+47h+var_28]
0x180015714  lea     rdx, aVdirName; "VDIR.NAME"
0x18001571b  mov     rcx, rdi
0x18001571e  mov     rax, [rax+50h]
0x180015722  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015727  mov     ebx, eax
0x180015729  test    eax, eax
0x18001572b  js      short loc_18001577C
0x18001572d  mov     rax, [rsi]
0x180015730  xor     r8d, r8d
0x180015733  mov     rdx, [rbp+47h+var_48]
0x180015737  mov     rcx, rsi
0x18001573a  mov     rax, [rax+0D0h]
0x180015741  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015746  mov     ebx, eax
0x180015748  test    eax, eax
0x18001574a  js      short loc_18001577C
0x18001574c  mov     rdx, [rbp+47h+arg_20]; struct ICommandObjectList *
0x180015750  lea     rax, aVdir; "VDIR"
0x180015757  mov     [rbp+47h+var_80], rax
0x18001575b  lea     r9, [rbp+47h+var_80]; unsigned __int16 **
0x18001575f  mov     rax, [rbp+47h+var_28]
0x180015763  mov     [rbp+47h+var_80+8], rax
0x180015767  call    ?AddStatusObject@APP_OBJECT_UTILS@@QEAAJPEAVICommandObjectList@@KQEAPEBG@Z; APP_OBJECT_UTILS::AddStatusObject(ICommandObjectList *,ulong,ushort const * * const)
0x18001576c  mov     ebx, eax
0x18001576e  jmp     short loc_18001577C
0x180015770  mov     ebx, 80070008h
0x180015775  jmp     short loc_18001577C
0x180015777  mov     ebx, 80070057h
0x18001577c  mov     rcx, [rbp+47h+var_70]
0x180015780  test    rcx, rcx
0x180015783  jz      short loc_180015795
0x180015785  mov     rax, [rcx]
0x180015788  mov     rax, [rax+10h]
0x18001578c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015791  mov     [rbp+47h+var_70], r15
0x180015795  mov     rcx, [rbp+47h+arg_0]
0x180015799  test    rcx, rcx
0x18001579c  jz      short loc_1800157AE
0x18001579e  mov     rax, [rcx]
0x1800157a1  mov     rax, [rax+10h]
0x1800157a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157aa  mov     [rbp+47h+arg_0], r15
0x1800157ae  test    rdi, rdi
0x1800157b1  jz      short loc_1800157C2
0x1800157b3  mov     rax, [rdi]
0x1800157b6  mov     rcx, rdi
0x1800157b9  mov     rax, [rax+10h]
0x1800157bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157c2  mov     rcx, [rbp+47h+arg_8]
0x1800157c6  test    rcx, rcx
0x1800157c9  jz      short loc_1800157DB
0x1800157cb  mov     rax, [rcx]
0x1800157ce  mov     rax, [rax+10h]
0x1800157d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157d7  mov     [rbp+47h+arg_8], r15
0x1800157db  mov     rcx, [rbp+47h+var_68]
0x1800157df  test    rcx, rcx
0x1800157e2  jz      short loc_1800157F4
0x1800157e4  mov     rax, [rcx]
0x1800157e7  mov     rax, [rax+10h]
0x1800157eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157f0  mov     [rbp+47h+var_68], r15
0x1800157f4  mov     rcx, [rbp+47h+var_60]
0x1800157f8  test    rcx, rcx
0x1800157fb  jz      short loc_18001580D
0x1800157fd  mov     rax, [rcx]
0x180015800  mov     rax, [rax+10h]
0x180015804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015809  mov     [rbp+47h+var_60], r15
0x18001580d  mov     rcx, [rbp+47h+var_58]
0x180015811  test    rcx, rcx
0x180015814  jz      short loc_180015822
0x180015816  mov     rax, [rcx]
0x180015819  mov     rax, [rax+10h]
0x18001581d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015822  mov     eax, ebx
0x180015824  mov     rbx, [rsp+0C0h+arg_10]
0x18001582c  add     rsp, 0A0h
  ... truncated ...
```
