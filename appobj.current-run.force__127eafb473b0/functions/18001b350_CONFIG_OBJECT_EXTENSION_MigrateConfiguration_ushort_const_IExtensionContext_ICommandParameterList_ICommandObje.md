# CONFIG_OBJECT_EXTENSION::MigrateConfiguration(ushort const *,IExtensionContext *,ICommandParameterList *,ICommandObjectList *)

- ea: `0x18001b350`
- end: `0x18001b7de`
- name: `?MigrateConfiguration@CONFIG_OBJECT_EXTENSION@@AEAAJPEBGPEAVIExtensionContext@@PEAVICommandParameterList@@PEAVICommandObjectList@@@Z`
- size: `1166`
- prototype: `__int64 __usercall@<rax>(CONFIG_OBJECT_EXTENSION *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, struct IExtensionContext *@<r8>, struct ICommandParameterList *@<r9>, struct ICommandObjectList *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001a850`

## callees

- `0x180001fb0`
- `0x180002640`
- `0x180002e90`
- `0x1800049b0`
- `0x18001b350`
- `0x18001b7e4`
- `0x18001ca1c`
- `0x18001d714`
- `0x18002b0cc`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001b576`
- `msvcrt!_wcsicmp` at `0x18001b5c2`
- `msvcrt!_wcsicmp` at `0x18001b576`
- `msvcrt!_wcsicmp` at `0x18001b5c2`

## string_xrefs

- `0x18001b6ea`: `validateIntegratedModeConfiguration`

## pseudocode

```c
__int64 __fastcall CONFIG_OBJECT_EXTENSION::MigrateConfiguration(
        CONFIG_OBJECT_EXTENSION *this,
        const unsigned __int16 *a2,
        struct IExtensionContext *a3,
        struct ICommandParameterList *a4,
        struct ICommandObjectList *a5)
{
  int v5; // r15d
  CONFIG_OBJECT_EXTENSION *v10; // rcx
  int v11; // ebx
  APP_OBJECT_UTILS *v12; // rcx
  __int64 v13; // rdx
  unsigned __int16 *v14; // r14
  BOOL v15; // esi
  int v16; // eax
  int v17; // eax
  int v19; // [rsp+28h] [rbp-D8h]
  struct ICommandParameterList *v20; // [rsp+40h] [rbp-C0h] BYREF
  int v21; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *String1; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v23; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v24; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v25; // [rsp+68h] [rbp-98h] BYREF
  __int64 v26; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v27; // [rsp+78h] [rbp-88h] BYREF
  wchar_t *v28; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v29[32]; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v30; // [rsp+A8h] [rbp-58h]
  int v31; // [rsp+B0h] [rbp-50h]
  __int16 v32; // [rsp+B4h] [rbp-4Ch]
  unsigned int v33; // [rsp+B8h] [rbp-48h]
  __int16 v34; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v35[510]; // [rsp+C2h] [rbp-3Eh] BYREF

  v5 = 0;
  v28 = 0;
  String1 = 0;
  v21 = 0;
  memset_0(v35, 0, sizeof(v35));
  v31 = 512;
  v30 = (unsigned __int16 *)&v34;
  v32 = 256;
  v33 = 0;
  v34 = 0;
  v20 = 0;
  v25 = 0;
  v24 = 0;
  v23 = 0;
  v26 = 0;
  v27 = 0;
  if ( a2 && a3 && a4 && a5 )
  {
    v11 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, struct ICommandParameterList **))(*(_QWORD *)a4 + 80LL))(
            a4,
            &v20);
    if ( v11 >= 0 )
    {
      v11 = CONFIG_OBJECT_EXTENSION::PopSectionNameFromParameters(v10, a3, v20, (const unsigned __int16 **)&String1, 0);
      if ( (int)(v11 + 0x80000000) < 0 || v11 == -2147023483 )
      {
        v11 = APP_OBJECT_UTILS::PopBooleanParameter(v12, a3, v20, L"clear", &v21, v19, 0);
        if ( ((v11 + 0x80000000) & 0x80000000) != 0 || v11 == -2147023483 )
        {
          v11 = (*(__int64 (__fastcall **)(struct IExtensionContext *, const unsigned __int16 *, const unsigned __int16 *, __int64 *, int))(*(_QWORD *)a3 + 64LL))(
                  a3,
                  L"APP",
                  a2,
                  &v26,
                  4);
          if ( v11 >= 0 )
          {
            v11 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, unsigned __int16 **))(*(_QWORD *)v26 + 80LL))(
                    v26,
                    L"APP.NAME",
                    &v27);
            if ( v11 >= 0 )
            {
              v11 = STRU::Copy((STRU *)v29, L"MACHINE/WEBROOT/APPHOST");
              if ( v11 >= 0 )
              {
                v11 = STRU::Append((STRU *)v29, L"/");
                if ( v11 >= 0 )
                {
                  v11 = STRU::Append((STRU *)v29, v27);
                  if ( v11 >= 0 )
                  {
                    while ( 1 )
                    {
                      v14 = v30;
                      if ( v33 <= 1 )
                        break;
                      v13 = v33 - 1;
                      if ( v30[v13] != 47 )
                        break;
                      STRU::SetLen((STRU *)v29, v13);
                    }
                    if ( String1 && _wcsicmp(String1, L"system.web/httpModules") )
                    {
                      v15 = 0;
                    }
                    else
                    {
                      v16 = CONFIG_OBJECT_EXTENSION::MigrateHttpModulesSection(this, a3, v14, v20, a5);
                      v11 = v16;
                      if ( v16 < 0 )
                        goto LABEL_42;
                      v5 = 1;
                      v15 = v16 == 0;
                    }
                    if ( String1 && _wcsicmp(String1, L"system.web/httpHandlers") )
                    {
                      if ( !v5 )
                      {
                        v28 = String1;
                        v11 = -2147024846;
                        (*(void (__fastcall **)(struct IExtensionContext *, __int64, __int64, wchar_t **, _DWORD))(*(_QWORD *)a3 + 144LL))(
                          a3,
                          2147942450LL,
                          3221226514LL,
                          &v28,
                          0);
                      }
                    }
                    else
                    {
                      v17 = CONFIG_OBJECT_EXTENSION::MigrateHttpHandlersSection(this, a3, v14, v20, a5);
                      v11 = v17;
                      if ( v17 >= 0 )
                      {
                        if ( !v17 )
                          v15 = 1;
                        if ( v5 )
                        {
                          if ( !v21 )
                          {
                            if ( v15 )
                            {
                              v11 = (*(__int64 (__fastcall **)(struct IExtensionContext *, unsigned __int16 *, __int64 *))(*(_QWORD *)a3 + 80LL))(
                                      a3,
                                      v14,
                                      &v25);
                              if ( v11 >= 0 )
                              {
                                v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 *, __int64 *, __int64 *, _QWORD))(*(_QWORD *)v25 + 24LL))(
                                        v25,
                                        L"system.webServer/validation",
                                        v14,
                                        &v24,
                                        &v23,
                                        0);
                                if ( v11 >= 0 )
                                {
                                  v11 = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64, const wchar_t *, const wchar_t *))(*(_QWORD *)a3 + 96LL))(
                                          a3,
                                          v24,
                                          L"validateIntegratedModeConfiguration",
                                          L"false");
                                  if ( v11 >= 0 )
                                    v11 = (*(__int64 (__fastcall **)(struct IExtensionContext *, unsigned __int16 *, __int64))(*(_QWORD *)a3 + 208LL))(
                                            a3,
                                            v14,
                                            1);
                                }
                                else if ( v23 )
                                {
                                  (*(void (__fastcall **)(struct IExtensionContext *, _QWORD, const wchar_t *, __int64, _DWORD))(*(_QWORD *)a3 + 112LL))(
                                    a3,
                                    (unsigned int)v11,
                                    &Str,
                                    v23,
                                    0);
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
    }
  }
  else
  {
    v11 = -2147024809;
  }
LABEL_42:
  if ( v20 )
  {
    (*(void (__fastcall **)(struct ICommandParameterList *))(*(_QWORD *)v20 + 16LL))(v20);
    v20 = 0;
  }
  if ( v23 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v23 = 0;
  }
  if ( v24 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    v24 = 0;
  }
  if ( v25 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    v25 = 0;
  }
  if ( v26 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    v26 = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v29);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18001b350  push    rbp
0x18001b352  push    rbx
0x18001b353  push    rsi
0x18001b354  push    rdi
0x18001b355  push    r12
0x18001b357  push    r13
0x18001b359  push    r14
0x18001b35b  push    r15
0x18001b35d  lea     rbp, [rsp-1D8h]
0x18001b365  sub     rsp, 2D8h
0x18001b36c  mov     rax, cs:__security_cookie
0x18001b373  xor     rax, rsp
0x18001b376  mov     [rbp+210h+var_50], rax
0x18001b37d  mov     r12, [rbp+210h+arg_20]
0x18001b384  xor     r15d, r15d
0x18001b387  mov     rdi, r8
0x18001b38a  mov     [rbp+210h+var_290], r15
0x18001b38e  mov     rsi, rdx
0x18001b391  mov     [rsp+310h+String1], r15
0x18001b396  mov     r13, rcx
0x18001b399  mov     [rsp+310h+var_2C8], r15d
0x18001b39e  xor     edx, edx; Val
0x18001b3a0  lea     rcx, [rbp+210h+var_24E]; void *
0x18001b3a4  mov     r8d, 1FEh; Size
0x18001b3aa  mov     rbx, r9
0x18001b3ad  call    memset_0
0x18001b3b2  mov     [rbp+210h+var_260], 200h
0x18001b3b9  lea     rax, [rbp+210h+var_250]
0x18001b3bd  mov     [rbp+210h+var_268], rax
0x18001b3c1  mov     [rbp+210h+var_25C], 100h
0x18001b3c7  mov     [rbp+210h+var_258], r15d
0x18001b3cb  mov     [rbp+210h+var_250], r15w
0x18001b3d0  mov     [rsp+310h+var_2D0], r15
0x18001b3d5  mov     [rsp+310h+var_2A8], r15
0x18001b3da  mov     [rsp+310h+var_2B0], r15
0x18001b3df  mov     [rsp+310h+var_2B8], r15
0x18001b3e4  mov     [rsp+310h+var_2A0], r15
0x18001b3e9  mov     [rsp+310h+var_298], r15
0x18001b3ee  test    rsi, rsi
0x18001b3f1  jz      loc_18001B724
0x18001b3f7  test    rdi, rdi
0x18001b3fa  jz      loc_18001B724
0x18001b400  test    rbx, rbx
0x18001b403  jz      loc_18001B724
0x18001b409  test    r12, r12
0x18001b40c  jz      loc_18001B724
0x18001b412  mov     rax, [rbx]
0x18001b415  lea     rdx, [rsp+310h+var_2D0]
0x18001b41a  mov     rcx, rbx
0x18001b41d  mov     rax, [rax+50h]
0x18001b421  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b426  mov     ebx, eax
0x18001b428  test    eax, eax
0x18001b42a  js      loc_18001B729
0x18001b430  mov     r8, [rsp+310h+var_2D0]; struct ICommandParameterList *
0x18001b435  lea     r9, [rsp+310h+String1]; unsigned __int16 **
0x18001b43a  mov     rdx, rdi; struct IExtensionContext *
0x18001b43d  mov     dword ptr [rsp+310h+var_2F0], r15d; int
0x18001b442  call    ?PopSectionNameFromParameters@CONFIG_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEAPEBGH@Z; CONFIG_OBJECT_EXTENSION::PopSectionNameFromParameters(IExtensionContext *,ICommandParameterList *,ushort const * *,int)
0x18001b447  mov     r14d, 80000000h
0x18001b44d  mov     ebx, eax
0x18001b44f  add     eax, r14d
0x18001b452  test    r14d, eax
0x18001b455  jnz     short loc_18001B463
0x18001b457  cmp     ebx, 80070585h
0x18001b45d  jnz     loc_18001B729
0x18001b463  mov     r8, [rsp+310h+var_2D0]; struct ICommandParameterList *
0x18001b468  lea     rax, [rsp+310h+var_2C8]
0x18001b46d  mov     [rsp+310h+var_2E0], r15d; int
0x18001b472  lea     r9, aClear; "clear"
0x18001b479  mov     rdx, rdi; struct IExtensionContext *
0x18001b47c  mov     [rsp+310h+var_2F0], rax; int *
0x18001b481  call    ?PopBooleanParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAHHH@Z; APP_OBJECT_UTILS::PopBooleanParameter(IExtensionContext *,ICommandParameterList *,ushort const *,int *,int,int)
0x18001b486  mov     ebx, eax
0x18001b488  add     eax, r14d
0x18001b48b  test    r14d, eax
0x18001b48e  jnz     short loc_18001B49C
0x18001b490  cmp     ebx, 80070585h
0x18001b496  jnz     loc_18001B729
0x18001b49c  mov     rax, [rdi]
0x18001b49f  lea     r9, [rsp+310h+var_2A0]
0x18001b4a4  mov     r8, rsi
0x18001b4a7  mov     dword ptr [rsp+310h+var_2F0], 4
0x18001b4af  lea     rdx, aApp_0; "APP"
0x18001b4b6  mov     rcx, rdi
0x18001b4b9  mov     rax, [rax+40h]
0x18001b4bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b4c2  mov     ebx, eax
0x18001b4c4  test    eax, eax
0x18001b4c6  js      loc_18001B729
0x18001b4cc  mov     rcx, [rsp+310h+var_2A0]
0x18001b4d1  lea     r8, [rsp+310h+var_298]
0x18001b4d6  lea     rdx, aAppName_0; "APP.NAME"
0x18001b4dd  mov     rax, [rcx]
0x18001b4e0  mov     rax, [rax+50h]
0x18001b4e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b4e9  mov     ebx, eax
0x18001b4eb  test    eax, eax
0x18001b4ed  js      loc_18001B729
0x18001b4f3  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x18001b4fa  lea     rcx, [rbp+210h+var_288]; this
0x18001b4fe  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001b503  mov     ebx, eax
0x18001b505  test    eax, eax
0x18001b507  js      loc_18001B729
0x18001b50d  lea     rdx, SubStr; "/"
0x18001b514  lea     rcx, [rbp+210h+var_288]; this
0x18001b518  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001b51d  mov     ebx, eax
0x18001b51f  test    eax, eax
0x18001b521  js      loc_18001B729
0x18001b527  mov     rdx, [rsp+310h+var_298]; unsigned __int16 *
0x18001b52c  lea     rcx, [rbp+210h+var_288]; this
0x18001b530  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001b535  mov     ebx, eax
0x18001b537  test    eax, eax
0x18001b539  js      loc_18001B729
0x18001b53f  mov     esi, 1
0x18001b544  jmp     short loc_18001B55A
0x18001b546  lea     edx, [rax-1]; unsigned int
0x18001b549  cmp     word ptr [r14+rdx*2], 2Fh ; '/'
0x18001b54f  jnz     short loc_18001B565
0x18001b551  lea     rcx, [rbp+210h+var_288]; this
0x18001b555  call    ?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x18001b55a  mov     eax, [rbp+210h+var_258]
0x18001b55d  mov     r14, [rbp+210h+var_268]
0x18001b561  cmp     eax, esi
0x18001b563  ja      short loc_18001B546
0x18001b565  mov     rcx, [rsp+310h+String1]; String1
0x18001b56a  test    rcx, rcx
0x18001b56d  jz      short loc_18001B584
0x18001b56f  lea     rdx, aSystemWebHttpm; "system.web/httpModules"
0x18001b576  call    cs:__imp__wcsicmp
0x18001b57c  test    eax, eax
0x18001b57e  jz      short loc_18001B584
0x18001b580  xor     esi, esi
0x18001b582  jmp     short loc_18001B5B1
0x18001b584  mov     r9, [rsp+310h+var_2D0]; struct ICommandParameterList *
0x18001b589  mov     r8, r14; unsigned __int16 *
0x18001b58c  mov     rdx, rdi; struct IExtensionContext *
0x18001b58f  mov     [rsp+310h+var_2F0], r12; struct ICommandObjectList *
0x18001b594  mov     rcx, r13; this
0x18001b597  call    ?MigrateHttpModulesSection@CONFIG_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEBGPEAVICommandParameterList@@PEAVICommandObjectList@@@Z; CONFIG_OBJECT_EXTENSION::MigrateHttpModulesSection(IExtensionContext *,ushort const *,ICommandParameterList *,ICommandObjectList *)
0x18001b59c  mov     ebx, eax
0x18001b59e  test    eax, eax
0x18001b5a0  js      loc_18001B729
0x18001b5a6  mov     r15d, esi
0x18001b5a9  xor     esi, esi
0x18001b5ab  test    eax, eax
0x18001b5ad  setz    sil
0x18001b5b1  mov     rcx, [rsp+310h+String1]; String1
0x18001b5b6  test    rcx, rcx
0x18001b5b9  jz      short loc_18001B60E
0x18001b5bb  lea     rdx, aSystemWebHttph; "system.web/httpHandlers"
0x18001b5c2  call    cs:__imp__wcsicmp
0x18001b5c8  test    eax, eax
0x18001b5ca  jz      short loc_18001B60E
0x18001b5cc  test    r15d, r15d
0x18001b5cf  jnz     loc_18001B71F
0x18001b5d5  mov     rax, [rsp+310h+String1]
0x18001b5da  lea     r9, [rbp+210h+var_290]
0x18001b5de  mov     [rbp+210h+var_290], rax
0x18001b5e2  xor     r15d, r15d
0x18001b5e5  mov     rax, [rdi]
0x18001b5e8  mov     ebx, 80070032h
0x18001b5ed  mov     r8d, 0C0000412h
0x18001b5f3  mov     dword ptr [rsp+310h+var_2F0], r15d
0x18001b5f8  mov     edx, ebx
0x18001b5fa  mov     rcx, rdi
0x18001b5fd  mov     rax, [rax+90h]
0x18001b604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b609  jmp     loc_18001B729
0x18001b60e  mov     r9, [rsp+310h+var_2D0]; struct ICommandParameterList *
0x18001b613  mov     r8, r14; unsigned __int16 *
0x18001b616  mov     rdx, rdi; struct IExtensionContext *
0x18001b619  mov     [rsp+310h+var_2F0], r12; struct ICommandObjectList *
0x18001b61e  mov     rcx, r13; this
0x18001b621  call    ?MigrateHttpHandlersSection@CONFIG_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEBGPEAVICommandParameterList@@PEAVICommandObjectList@@@Z; CONFIG_OBJECT_EXTENSION::MigrateHttpHandlersSection(IExtensionContext *,ushort const *,ICommandParameterList *,ICommandObjectList *)
0x18001b626  mov     ebx, eax
0x18001b628  test    eax, eax
0x18001b62a  js      loc_18001B71F
0x18001b630  mov     r12d, 1
0x18001b636  cmovz   esi, r12d
0x18001b63a  test    r15d, r15d
0x18001b63d  jz      loc_18001B71F
0x18001b643  xor     r15d, r15d
0x18001b646  cmp     [rsp+310h+var_2C8], r15d
0x18001b64b  jnz     loc_18001B729
0x18001b651  test    esi, esi
0x18001b653  jz      loc_18001B729
0x18001b659  mov     rax, [rdi]
0x18001b65c  lea     r8, [rsp+310h+var_2A8]
0x18001b661  mov     rdx, r14
0x18001b664  mov     rcx, rdi
0x18001b667  mov     rax, [rax+50h]
0x18001b66b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b670  mov     ebx, eax
0x18001b672  test    eax, eax
0x18001b674  js      loc_18001B729
0x18001b67a  mov     rcx, [rsp+310h+var_2A8]
0x18001b67f  lea     rdx, [rsp+310h+var_2B8]
0x18001b684  mov     [rsp+310h+var_2E8], r15
0x18001b689  lea     r9, [rsp+310h+var_2B0]
0x18001b68e  mov     [rsp+310h+var_2F0], rdx
0x18001b693  mov     r8, r14
0x18001b696  lea     rdx, aSystemWebserve_8; "system.webServer/validation"
0x18001b69d  mov     rax, [rcx]
0x18001b6a0  mov     rax, [rax+18h]
0x18001b6a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b6a9  mov     ebx, eax
0x18001b6ab  test    eax, eax
0x18001b6ad  jns     short loc_18001B6DB
0x18001b6af  mov     rcx, [rsp+310h+var_2B8]
0x18001b6b4  test    rcx, rcx
0x18001b6b7  jz      short loc_18001B729
0x18001b6b9  mov     rax, [rdi]
0x18001b6bc  lea     r8, Str
0x18001b6c3  mov     r9, rcx
0x18001b6c6  mov     dword ptr [rsp+310h+var_2F0], r15d
0x18001b6cb  mov     edx, ebx
0x18001b6cd  mov     rcx, rdi
0x18001b6d0  mov     rax, [rax+70h]
0x18001b6d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b6d9  jmp     short loc_18001B729
0x18001b6db  mov     rax, [rdi]
0x18001b6de  lea     r9, aFalse; "false"
0x18001b6e5  mov     rdx, [rsp+310h+var_2B0]
0x18001b6ea  lea     r8, aValidateintegr; "validateIntegratedModeConfiguration"
0x18001b6f1  mov     rcx, rdi
0x18001b6f4  mov     rax, [rax+60h]
0x18001b6f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b6fd  mov     ebx, eax
0x18001b6ff  test    eax, eax
0x18001b701  js      short loc_18001B729
0x18001b703  mov     rax, [rdi]
0x18001b706  mov     r8d, r12d
0x18001b709  mov     rdx, r14
0x18001b70c  mov     rcx, rdi
0x18001b70f  mov     rax, [rax+0D0h]
0x18001b716  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b71b  mov     ebx, eax
0x18001b71d  jmp     short loc_18001B729
0x18001b71f  xor     r15d, r15d
0x18001b722  jmp     short loc_18001B729
0x18001b724  mov     ebx, 80070057h
0x18001b729  mov     rcx, [rsp+310h+var_2D0]
0x18001b72e  test    rcx, rcx
0x18001b731  jz      short loc_18001B744
0x18001b733  mov     rax, [rcx]
0x18001b736  mov     rax, [rax+10h]
0x18001b73a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b73f  mov     [rsp+310h+var_2D0], r15
0x18001b744  mov     rcx, [rsp+310h+var_2B8]
0x18001b749  test    rcx, rcx
0x18001b74c  jz      short loc_18001B75F
0x18001b74e  mov     rax, [rcx]
0x18001b751  mov     rax, [rax+10h]
0x18001b755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b75a  mov     [rsp+310h+var_2B8], r15
0x18001b75f  mov     rcx, [rsp+310h+var_2B0]
0x18001b764  test    rcx, rcx
0x18001b767  jz      short loc_18001B77A
0x18001b769  mov     rax, [rcx]
0x18001b76c  mov     rax, [rax+10h]
0x18001b770  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b775  mov     [rsp+310h+var_2B0], r15
0x18001b77a  mov     rcx, [rsp+310h+var_2A8]
0x18001b77f  test    rcx, rcx
0x18001b782  jz      short loc_18001B795
0x18001b784  mov     rax, [rcx]
0x18001b787  mov     rax, [rax+10h]
0x18001b78b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b790  mov     [rsp+310h+var_2A8], r15
0x18001b795  mov     rcx, [rsp+310h+var_2A0]
0x18001b79a  test    rcx, rcx
0x18001b79d  jz      short loc_18001B7B0
0x18001b79f  mov     rax, [rcx]
0x18001b7a2  mov     rax, [rax+10h]
0x18001b7a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b7ab  mov     [rsp+310h+var_2A0], r15
0x18001b7b0  lea     rcx, [rbp+210h+var_288]; this
0x18001b7b4  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18001b7b9  mov     eax, ebx
0x18001b7bb  mov     rcx, [rbp+210h+var_50]
0x18001b7c2  xor     rcx, rsp; StackCookie
0x18001b7c5  call    __security_check_cookie
0x18001b7ca  add     rsp, 2D8h
0x18001b7d1  pop     r15
0x18001b7d3  pop     r14
0x18001b7d5  pop     r13
0x18001b7d7  pop     r12
0x18001b7d9  pop     rdi
0x18001b7da  pop     rsi
0x18001b7db  pop     rbx
0x18001b7dc  pop     rbp
0x18001b7dd  retn
```
