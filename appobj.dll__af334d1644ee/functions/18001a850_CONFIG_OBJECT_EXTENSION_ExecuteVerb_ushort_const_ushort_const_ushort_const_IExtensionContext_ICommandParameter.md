# CONFIG_OBJECT_EXTENSION::ExecuteVerb(ushort const *,ushort const *,ushort const *,IExtensionContext *,ICommandParameterList *,ICommandObjectList *,IXMLDOMDocument *)

- ea: `0x18001a850`
- end: `0x18001afed`
- name: `?ExecuteVerb@CONFIG_OBJECT_EXTENSION@@UEAAJPEBG00PEAVIExtensionContext@@PEAVICommandParameterList@@PEAVICommandObjectList@@PEAUIXMLDOMDocument@@@Z`
- size: `1949`
- prototype: `__int64 __fastcall(CONFIG_OBJECT_EXTENSION *__hidden this, const unsigned __int16 *, wchar_t *String1, const unsigned __int16 *, struct IExtensionContext *, struct ICommandParameterList *, struct ICommandObjectList *, struct IXMLDOMDocument *)`
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001044`
- `0x180001fb0`
- `0x18000557c`
- `0x180006b6c`
- `0x180018fd0`
- `0x1800194e4`
- `0x180019948`
- `0x180019d30`
- `0x180019f48`
- `0x18001a850`
- `0x18001b188`
- `0x18001b350`
- `0x18001d714`
- `0x18001d8c0`
- `0x18001ded0`
- `0x18001e0f8`
- `0x18002b860`
- `0x18002bcd4`
- `0x18002bd3c`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001a954`
- `msvcrt!_wcsicmp` at `0x18001a9ab`
- `msvcrt!_wcsicmp` at `0x18001a9dc`
- `msvcrt!_wcsicmp` at `0x18001aae7`
- `msvcrt!_wcsicmp` at `0x18001ab67`
- `msvcrt!_wcsicmp` at `0x18001aba1`
- `msvcrt!_wcsicmp` at `0x18001abdb`
- `msvcrt!_wcsicmp` at `0x18001ad74`
- `msvcrt!_wcsicmp` at `0x18001ae48`
- `msvcrt!_wcsicmp` at `0x18001aeac`
- `msvcrt!_wcsicmp` at `0x18001aee8`
- `msvcrt!_wcsicmp` at `0x18001a954`
- `msvcrt!_wcsicmp` at `0x18001a9ab`
- `msvcrt!_wcsicmp` at `0x18001a9dc`
- `msvcrt!_wcsicmp` at `0x18001aae7`
- `msvcrt!_wcsicmp` at `0x18001ab67`
- `msvcrt!_wcsicmp` at `0x18001aba1`
- `msvcrt!_wcsicmp` at `0x18001abdb`
- `msvcrt!_wcsicmp` at `0x18001ad74`
- `msvcrt!_wcsicmp` at `0x18001ae48`
- `msvcrt!_wcsicmp` at `0x18001aeac`
- `msvcrt!_wcsicmp` at `0x18001aee8`

## string_xrefs

- `0x18001aabb`: `CONFIG.SECTION`

## pseudocode

```c
__int64 __fastcall CONFIG_OBJECT_EXTENSION::ExecuteVerb(
        CONFIG_OBJECT_EXTENSION *this,
        const unsigned __int16 *a2,
        wchar_t *String1,
        const unsigned __int16 *a4,
        struct IExtensionContext *a5,
        struct ICommandParameterList *a6,
        struct ICommandObjectList *a7,
        struct IXMLDOMDocument *a8)
{
  CONFIG_OBJECT_EXTENSION *v12; // rcx
  CONFIG_OBJECT_EXTENSION *v13; // rcx
  int ObjectsHelper; // ebx
  int v15; // eax
  APP_OBJECT_UTILS *v16; // rcx
  CONFIG_OBJECT_EXTENSION *v17; // rcx
  unsigned __int16 *v18; // r13
  CONFIG_OBJECT_EXTENSION *v19; // rcx
  CONFIG_OBJECT_EXTENSION *v20; // rcx
  CONFIG_OBJECT_EXTENSION *v21; // rcx
  __int64 v22; // r8
  __int64 v23; // rax
  STATUS_OBJECT *v24; // rax
  const unsigned __int16 **v25; // rax
  const unsigned __int16 **v26; // rdi
  APP_OBJECT_UTILS *v27; // rcx
  APP_OBJECT_UTILS *v28; // rcx
  CONFIG_OBJECT_EXTENSION *v29; // rcx
  APP_OBJECT_UTILS *v30; // rcx
  CONFIG_OBJECT_EXTENSION *v31; // rcx
  APP_OBJECT_UTILS *v32; // rcx
  CONFIG_OBJECT_EXTENSION *v33; // rcx
  int v35; // [rsp+30h] [rbp-D0h]
  struct ICommandParameterList *v36; // [rsp+50h] [rbp-B0h] BYREF
  struct CONFIG_OBJECT *v37; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v38; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v39; // [rsp+68h] [rbp-98h] BYREF
  __int64 v40; // [rsp+70h] [rbp-90h] BYREF
  __int64 v41; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v42; // [rsp+80h] [rbp-80h] BYREF
  struct INativeConfigurationElement *v43; // [rsp+88h] [rbp-78h] BYREF
  wchar_t *v44; // [rsp+90h] [rbp-70h] BYREF
  CONFIG_OBJECT_EXTENSION *v45; // [rsp+98h] [rbp-68h]
  struct IXMLDOMDocument *v46; // [rsp+A0h] [rbp-60h]
  _BYTE v47[32]; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 *v48; // [rsp+C8h] [rbp-38h]
  int v49; // [rsp+D0h] [rbp-30h]
  __int16 v50; // [rsp+D4h] [rbp-2Ch]
  int v51; // [rsp+D8h] [rbp-28h]
  va_list Arguments[2]; // [rsp+E0h] [rbp-20h] BYREF
  wchar_t *v53; // [rsp+F0h] [rbp-10h]
  __int16 v54; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v55[510]; // [rsp+102h] [rbp+2h] BYREF

  v46 = a8;
  v45 = this;
  v37 = 0;
  v41 = 0;
  v43 = 0;
  v44 = 0;
  v38 = 0;
  v39 = 0;
  memset_0(v55, 0, sizeof(v55));
  v49 = 512;
  v50 = 256;
  v48 = (unsigned __int16 *)&v54;
  v51 = 0;
  v54 = 0;
  v42 = 0;
  v53 = 0;
  v40 = 0;
  v36 = 0;
  *(_OWORD *)Arguments = 0;
  if ( !a2 || !String1 || !a4 || !a5 || !a6 || !a7 )
    goto LABEL_66;
  if ( !_wcsicmp(String1, L"LIST") )
  {
    ObjectsHelper = CONFIG_OBJECT_EXTENSION::CreateObjectsHelper(v12, a2, a4, a5, a6, 1, v35, a7);
    if ( ObjectsHelper >= 0 )
    {
      ObjectsHelper = CONFIG_OBJECT_EXTENSION::RequestConfigurationOutput(v13, a5);
      if ( ObjectsHelper >= 0 )
        ObjectsHelper = 0;
    }
    goto LABEL_67;
  }
  if ( !_wcsicmp(String1, L"SEARCH") )
  {
    v15 = CONFIG_OBJECT_EXTENSION::DoSearch(this, a5, (const unsigned __int8 *)a4, a6, a7);
LABEL_13:
    ObjectsHelper = v15;
    goto LABEL_67;
  }
  if ( !_wcsicmp(String1, L"MIGRATE") )
  {
    v15 = CONFIG_OBJECT_EXTENSION::MigrateConfiguration(this, a4, a5, a6, a7);
    goto LABEL_13;
  }
  ObjectsHelper = (*(__int64 (__fastcall **)(struct ICommandParameterList *, struct ICommandParameterList **))(*(_QWORD *)a6 + 80LL))(
                    a6,
                    &v36);
  if ( ObjectsHelper >= 0 )
  {
    ObjectsHelper = APP_OBJECT_UTILS::ResolveConfigPath(v16, a5, a4, (struct STRU *)v47, 0, 0);
    if ( ObjectsHelper >= 0 )
    {
      v18 = v48;
      v39 = v48;
      ObjectsHelper = CONFIG_OBJECT_EXTENSION::PopSectionNameFromParameters(
                        v17,
                        a5,
                        v36,
                        (const unsigned __int16 **)&v38,
                        1);
      if ( ObjectsHelper >= 0 )
      {
        ObjectsHelper = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64 *))(*(_QWORD *)a5 + 184LL))(
                          a5,
                          &v40);
        if ( ObjectsHelper >= 0 )
        {
          ObjectsHelper = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64 *))(*(_QWORD *)a5 + 192LL))(
                            a5,
                            &v41);
          if ( ObjectsHelper >= 0 )
          {
            ObjectsHelper = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, unsigned __int16 *))(*(_QWORD *)v41 + 56LL))(
                              v41,
                              L"CONFIG.SECTION",
                              v38);
            if ( ObjectsHelper >= 0 )
            {
              if ( _wcsicmp(String1, L"RESET")
                || (ObjectsHelper = (*(__int64 (__fastcall **)(CONFIG_OBJECT_EXTENSION *, const unsigned __int16 *, const wchar_t *, const unsigned __int16 *, struct IExtensionContext *, __int64, struct ICommandObjectList *, _QWORD))(*(_QWORD *)v45 + 40LL))(
                                      v45,
                                      a2,
                                      L"CLEAR",
                                      a4,
                                      a5,
                                      v41,
                                      a7,
                                      0),
                    ObjectsHelper >= 0)
                && (ObjectsHelper = (*(__int64 (__fastcall **)(struct IExtensionContext *, unsigned __int16 *, __int64))(*(_QWORD *)a5 + 208LL))(
                                      a5,
                                      v18,
                                      1),
                    ObjectsHelper >= 0) )
              {
                if ( !_wcsicmp(String1, L"CLEAR") )
                {
                  v15 = CONFIG_OBJECT_EXTENSION::DoClear(v19, a5, v39, v38, v36, a7);
                  goto LABEL_13;
                }
                if ( !_wcsicmp(String1, L"REGISTER") )
                {
                  v15 = CONFIG_OBJECT_EXTENSION::RegisterSection(v20, a5, v39, v38, v36, a7);
                  goto LABEL_13;
                }
                if ( !_wcsicmp(String1, L"DEREGISTER") )
                {
                  v15 = CONFIG_OBJECT_EXTENSION::DeregisterSection(v21, a5, v39, v38, v36, a7);
                  goto LABEL_13;
                }
                ObjectsHelper = (*(__int64 (__fastcall **)(struct IExtensionContext *, const unsigned __int16 *, const unsigned __int16 *, __int64, __int64, _DWORD))(*(_QWORD *)a5 + 56LL))(
                                  a5,
                                  a2,
                                  a4,
                                  v41,
                                  v40,
                                  0);
                if ( ObjectsHelper >= 0 )
                {
                  ObjectsHelper = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v40 + 32LL))(
                                    v40,
                                    &v42);
                  if ( ObjectsHelper >= 0 )
                  {
                    if ( !v42 )
                    {
                      ObjectsHelper = -2147024894;
                      Arguments[1] = (va_list)a4;
                      v22 = 3221226521LL;
LABEL_35:
                      v23 = *(_QWORD *)a5;
                      Arguments[0] = (va_list)a2;
                      (*(void (__fastcall **)(struct IExtensionContext *, _QWORD, __int64, va_list *, _DWORD))(v23 + 144))(
                        a5,
                        (unsigned int)ObjectsHelper,
                        v22,
                        Arguments,
                        0);
                      goto LABEL_67;
                    }
                    if ( v42 > 1 )
                    {
                      ObjectsHelper = -2147024846;
                      Arguments[1] = (va_list)String1;
                      v22 = 3221226475LL;
                      goto LABEL_35;
                    }
                    ObjectsHelper = (*(__int64 (__fastcall **)(__int64, _QWORD, struct CONFIG_OBJECT **))(*(_QWORD *)v40 + 40LL))(
                                      v40,
                                      0,
                                      &v37);
                    if ( ObjectsHelper >= 0 )
                    {
                      if ( !v37 )
                      {
                        ObjectsHelper = -2147467261;
                        goto LABEL_67;
                      }
                      ObjectsHelper = (*(__int64 (__fastcall **)(struct CONFIG_OBJECT *, struct INativeConfigurationElement **))(*(_QWORD *)v37 + 48LL))(
                                        v37,
                                        &v43);
                      if ( ObjectsHelper >= 0 )
                      {
                        if ( !v43 )
                        {
                          ObjectsHelper = -2147467261;
                          goto LABEL_69;
                        }
                        ObjectsHelper = (*(__int64 (__fastcall **)(struct CONFIG_OBJECT *, wchar_t **))(*(_QWORD *)v37 + 40LL))(
                                          v37,
                                          &v44);
                        if ( ObjectsHelper >= 0 )
                        {
                          if ( v44 )
                          {
                            ObjectsHelper = (*(__int64 (__fastcall **)(struct CONFIG_OBJECT *, const unsigned __int16 *, unsigned __int16 **))(*(_QWORD *)v37 + 80LL))(
                                              v37,
                                              L"path",
                                              &v39);
                            if ( ObjectsHelper >= 0 )
                            {
                              if ( !_wcsicmp(String1, L"SET") )
                              {
                                ObjectsHelper = (*(__int64 (__fastcall **)(struct IExtensionContext *, struct CONFIG_OBJECT *, struct ICommandParameterList *, _QWORD, struct IXMLDOMDocument *, int))(*(_QWORD *)a5 + 168LL))(
                                                  a5,
                                                  v37,
                                                  v36,
                                                  0,
                                                  v46,
                                                  1);
                                if ( ObjectsHelper >= 0 )
                                {
                                  Arguments[0] = (va_list)v38;
                                  Arguments[1] = (va_list)v39;
                                  v53 = v44;
                                  v24 = (STATUS_OBJECT *)operator new(0x110u);
                                  if ( v24
                                    && (v25 = (const unsigned __int16 **)STATUS_OBJECT::STATUS_OBJECT(v24),
                                        (v26 = v25) != 0) )
                                  {
                                    ObjectsHelper = STATUS_OBJECT::Create(v25, 0xC000042D, Arguments);
                                    if ( ObjectsHelper >= 0 )
                                      ObjectsHelper = (*(__int64 (__fastcall **)(struct ICommandObjectList *, const unsigned __int16 **))(*(_QWORD *)a7 + 24LL))(
                                                        a7,
                                                        v26);
                                    (*((void (__fastcall **)(const unsigned __int16 **))*v26 + 2))(v26);
                                  }
                                  else
                                  {
                                    ObjectsHelper = -2147024888;
                                  }
                                }
                                goto LABEL_67;
                              }
                              if ( _wcsicmp(String1, L"RESET") )
                              {
                                if ( _wcsicmp(String1, L"LOCK") )
                                {
                                  if ( _wcsicmp(String1, L"UNLOCK") )
                                  {
                                    ObjectsHelper = -2147024846;
                                  }
                                  else
                                  {
                                    ObjectsHelper = APP_OBJECT_UTILS::ValidateEmptyParameters(v32, a5, v36);
                                    if ( ObjectsHelper >= 0 )
                                    {
                                      v15 = CONFIG_OBJECT_EXTENSION::UnlockSection(v33, a5, v37, a7);
                                      goto LABEL_13;
                                    }
                                  }
                                }
                                else
                                {
                                  ObjectsHelper = APP_OBJECT_UTILS::ValidateEmptyParameters(v30, a5, v36);
                                  if ( ObjectsHelper >= 0 )
                                  {
                                    v15 = CONFIG_OBJECT_EXTENSION::LockSection(v31, a5, v37, a7);
                                    goto LABEL_13;
                                  }
                                }
                              }
                              else
                              {
                                ObjectsHelper = APP_OBJECT_UTILS::ValidateEmptyParameters(v27, a5, v36);
                                if ( ObjectsHelper >= 0 )
                                {
                                  ObjectsHelper = APP_OBJECT_UTILS::ValidateEmptyIdentifier(v28, a5, a4);
                                  if ( ObjectsHelper >= 0 )
                                  {
                                    v15 = CONFIG_OBJECT_EXTENSION::DoReset(v29, a5, v43, v38, v44, a7);
                                    goto LABEL_13;
                                  }
                                }
                              }
                            }
                            goto LABEL_67;
                          }
LABEL_66:
                          ObjectsHelper = -2147024809;
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
LABEL_67:
  if ( v43 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v43 + 16LL))(v43);
    v43 = 0;
  }
LABEL_69:
  if ( v40 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    v40 = 0;
  }
  if ( v37 )
  {
    (*(void (__fastcall **)(struct CONFIG_OBJECT *))(*(_QWORD *)v37 + 16LL))(v37);
    v37 = 0;
  }
  if ( v36 )
  {
    (*(void (__fastcall **)(struct ICommandParameterList *))(*(_QWORD *)v36 + 16LL))(v36);
    v36 = 0;
  }
  if ( v41 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    v41 = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v47);
  return (unsigned int)ObjectsHelper;
}

```

## disassembly

```asm
0x18001a850  push    rbp
0x18001a852  push    rbx
0x18001a853  push    rsi
0x18001a854  push    rdi
0x18001a855  push    r12
0x18001a857  push    r13
0x18001a859  push    r14
0x18001a85b  push    r15
0x18001a85d  lea     rbp, [rsp-218h]
0x18001a865  sub     rsp, 318h
0x18001a86c  mov     rax, cs:__security_cookie
0x18001a873  xor     rax, rsp
0x18001a876  mov     [rbp+250h+var_50], rax
0x18001a87d  mov     rax, [rbp+250h+arg_38]
0x18001a884  mov     rsi, r8
0x18001a887  mov     rdi, [rbp+250h+arg_20]
0x18001a88e  mov     r12, rdx
0x18001a891  mov     rbx, [rbp+250h+arg_28]
0x18001a898  mov     r13, rcx
0x18001a89b  mov     r14, [rbp+250h+arg_30]
0x18001a8a2  xor     edx, edx; Val
0x18001a8a4  mov     [rbp+250h+var_2B0], rax
0x18001a8a8  mov     r8d, 1FEh; Size
0x18001a8ae  xor     eax, eax
0x18001a8b0  mov     [rbp+250h+var_2B8], rcx
0x18001a8b4  lea     rcx, [rbp+250h+var_24E]; void *
0x18001a8b8  mov     [rsp+350h+var_2F8], rax
0x18001a8bd  mov     [rsp+350h+var_2D8], rax
0x18001a8c2  mov     r15, r9
0x18001a8c5  mov     [rbp+250h+var_2C8], rax
0x18001a8c9  mov     [rbp+250h+var_2C0], rax
0x18001a8cd  mov     [rsp+350h+var_2F0], rax
0x18001a8d2  mov     [rsp+350h+var_2E8], rax
0x18001a8d7  call    memset_0
0x18001a8dc  xor     ecx, ecx
0x18001a8de  mov     [rbp+250h+var_280], 200h
0x18001a8e5  lea     rax, [rbp+250h+var_250]
0x18001a8e9  mov     [rbp+250h+var_27C], 100h
0x18001a8ef  mov     [rbp+250h+var_288], rax
0x18001a8f3  xorps   xmm0, xmm0
0x18001a8f6  xor     eax, eax
0x18001a8f8  mov     [rbp+250h+var_278], ecx
0x18001a8fb  mov     [rbp+250h+var_250], cx
0x18001a8ff  mov     [rbp+250h+var_2D0], ecx
0x18001a902  mov     [rbp+250h+var_260], rax
0x18001a906  mov     [rsp+350h+var_2E0], rcx
0x18001a90b  mov     [rsp+350h+var_300], rcx
0x18001a910  movups  xmmword ptr [rbp+250h+Arguments], xmm0
0x18001a914  test    r12, r12
0x18001a917  jz      loc_18001AF21
0x18001a91d  test    rsi, rsi
0x18001a920  jz      loc_18001AF21
0x18001a926  test    r15, r15
0x18001a929  jz      loc_18001AF21
0x18001a92f  test    rdi, rdi
0x18001a932  jz      loc_18001AF21
0x18001a938  test    rbx, rbx
0x18001a93b  jz      loc_18001AF21
0x18001a941  test    r14, r14
0x18001a944  jz      loc_18001AF21
0x18001a94a  lea     rdx, aList; "LIST"
0x18001a951  mov     rcx, rsi; String1
0x18001a954  call    cs:__imp__wcsicmp
0x18001a95a  test    eax, eax
0x18001a95c  jnz     short loc_18001A9A1
0x18001a95e  mov     [rsp+350h+var_318], r14; struct ICommandObjectList *
0x18001a963  mov     r9, rdi; struct IExtensionContext *
0x18001a966  mov     dword ptr [rsp+350h+var_328], 1; int
0x18001a96e  mov     r8, r15; unsigned __int16 *
0x18001a971  mov     rdx, r12; unsigned __int16 *
0x18001a974  mov     [rsp+350h+String1], rbx; struct ICommandParameterList *
0x18001a979  call    ?CreateObjectsHelper@CONFIG_OBJECT_EXTENSION@@AEAAJPEBG0PEAVIExtensionContext@@PEAVICommandParameterList@@HHPEAVICommandObjectList@@@Z; CONFIG_OBJECT_EXTENSION::CreateObjectsHelper(ushort const *,ushort const *,IExtensionContext *,ICommandParameterList *,int,int,ICommandObjectList *)
0x18001a97e  mov     ebx, eax
0x18001a980  test    eax, eax
0x18001a982  js      loc_18001AF26
0x18001a988  mov     rdx, rdi; struct IExtensionContext *
0x18001a98b  call    ?RequestConfigurationOutput@CONFIG_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@@Z; CONFIG_OBJECT_EXTENSION::RequestConfigurationOutput(IExtensionContext *)
0x18001a990  mov     ebx, eax
0x18001a992  test    eax, eax
0x18001a994  js      loc_18001AF26
0x18001a99a  xor     ebx, ebx
0x18001a99c  jmp     loc_18001AF26
0x18001a9a1  lea     rdx, aSearch_0; "SEARCH"
0x18001a9a8  mov     rcx, rsi; String1
0x18001a9ab  call    cs:__imp__wcsicmp
0x18001a9b1  test    eax, eax
0x18001a9b3  jnz     short loc_18001A9D2
0x18001a9b5  mov     r9, rbx; struct ICommandParameterList *
0x18001a9b8  mov     [rsp+350h+String1], r14; struct ICommandObjectList *
0x18001a9bd  mov     r8, r15; unsigned __int16 *
0x18001a9c0  mov     rdx, rdi; struct IExtensionContext *
0x18001a9c3  mov     rcx, r13; this
0x18001a9c6  call    ?DoSearch@CONFIG_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEBGPEAVICommandParameterList@@PEAVICommandObjectList@@@Z; CONFIG_OBJECT_EXTENSION::DoSearch(IExtensionContext *,ushort const *,ICommandParameterList *,ICommandObjectList *)
0x18001a9cb  mov     ebx, eax
0x18001a9cd  jmp     loc_18001AF26
0x18001a9d2  lea     rdx, aMigrate; "MIGRATE"
0x18001a9d9  mov     rcx, rsi; String1
0x18001a9dc  call    cs:__imp__wcsicmp
0x18001a9e2  test    eax, eax
0x18001a9e4  jnz     short loc_18001A9FE
0x18001a9e6  mov     r9, rbx; struct ICommandParameterList *
0x18001a9e9  mov     [rsp+350h+String1], r14; struct ICommandObjectList *
0x18001a9ee  mov     r8, rdi; struct IExtensionContext *
0x18001a9f1  mov     rdx, r15; unsigned __int16 *
0x18001a9f4  mov     rcx, r13; this
0x18001a9f7  call    ?MigrateConfiguration@CONFIG_OBJECT_EXTENSION@@AEAAJPEBGPEAVIExtensionContext@@PEAVICommandParameterList@@PEAVICommandObjectList@@@Z; CONFIG_OBJECT_EXTENSION::MigrateConfiguration(ushort const *,IExtensionContext *,ICommandParameterList *,ICommandObjectList *)
0x18001a9fc  jmp     short loc_18001A9CB
0x18001a9fe  mov     rax, [rbx]
0x18001aa01  lea     rdx, [rsp+350h+var_300]
0x18001aa06  mov     rcx, rbx
0x18001aa09  mov     rax, [rax+50h]
0x18001aa0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa12  mov     ebx, eax
0x18001aa14  test    eax, eax
0x18001aa16  js      loc_18001AF26
0x18001aa1c  mov     [rsp+350h+var_328], 0; struct SITE_OBJECT **
0x18001aa25  lea     r9, [rbp+250h+var_2A8]; struct STRU *
0x18001aa29  mov     r8, r15; unsigned __int16 *
0x18001aa2c  mov     [rsp+350h+String1], 0; unsigned __int16 **
0x18001aa35  mov     rdx, rdi; struct IExtensionContext *
0x18001aa38  call    ?ResolveConfigPath@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEBGPEAVSTRU@@PEAPEBGPEAPEAVSITE_OBJECT@@@Z; APP_OBJECT_UTILS::ResolveConfigPath(IExtensionContext *,ushort const *,STRU *,ushort const * *,SITE_OBJECT * *)
0x18001aa3d  mov     ebx, eax
0x18001aa3f  test    eax, eax
0x18001aa41  js      loc_18001AF26
0x18001aa47  mov     r13, [rbp+250h+var_288]
0x18001aa4b  lea     r9, [rsp+350h+var_2F0]; unsigned __int16 **
0x18001aa50  mov     r8, [rsp+350h+var_300]; struct ICommandParameterList *
0x18001aa55  mov     rdx, rdi; struct IExtensionContext *
0x18001aa58  mov     [rsp+350h+var_2E8], r13
0x18001aa5d  mov     dword ptr [rsp+350h+String1], 1; int
0x18001aa65  call    ?PopSectionNameFromParameters@CONFIG_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEAPEBGH@Z; CONFIG_OBJECT_EXTENSION::PopSectionNameFromParameters(IExtensionContext *,ICommandParameterList *,ushort const * *,int)
0x18001aa6a  mov     ebx, eax
0x18001aa6c  test    eax, eax
0x18001aa6e  js      loc_18001AF26
0x18001aa74  mov     rax, [rdi]
0x18001aa77  lea     rdx, [rsp+350h+var_2E0]
0x18001aa7c  mov     rcx, rdi
0x18001aa7f  mov     rax, [rax+0B8h]
0x18001aa86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa8b  mov     ebx, eax
0x18001aa8d  test    eax, eax
0x18001aa8f  js      loc_18001AF26
0x18001aa95  mov     rax, [rdi]
0x18001aa98  lea     rdx, [rsp+350h+var_2D8]
0x18001aa9d  mov     rcx, rdi
0x18001aaa0  mov     rax, [rax+0C0h]
0x18001aaa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aaac  mov     ebx, eax
0x18001aaae  test    eax, eax
0x18001aab0  js      loc_18001AF26
0x18001aab6  mov     rcx, [rsp+350h+var_2D8]
0x18001aabb  lea     rdx, aConfigSection; "CONFIG.SECTION"
0x18001aac2  mov     r8, [rsp+350h+var_2F0]
0x18001aac7  mov     rax, [rcx]
0x18001aaca  mov     rax, [rax+38h]
0x18001aace  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aad3  mov     ebx, eax
0x18001aad5  test    eax, eax
0x18001aad7  js      loc_18001AF26
0x18001aadd  lea     rdx, aReset; "RESET"
0x18001aae4  mov     rcx, rsi; String1
0x18001aae7  call    cs:__imp__wcsicmp
0x18001aaed  test    eax, eax
0x18001aaef  jnz     short loc_18001AB5D
0x18001aaf1  mov     r10, [rbp+250h+var_2B8]
0x18001aaf5  lea     r8, aClear_0; "CLEAR"
0x18001aafc  mov     rcx, [rsp+350h+var_2D8]
0x18001ab01  mov     r9, r15
0x18001ab04  mov     [rsp+350h+var_318], 0
0x18001ab0d  mov     rdx, r12
0x18001ab10  mov     [rsp+350h+var_320], r14
0x18001ab15  mov     rax, [r10]
0x18001ab18  mov     [rsp+350h+var_328], rcx
0x18001ab1d  mov     rcx, r10
0x18001ab20  mov     [rsp+350h+String1], rdi
0x18001ab25  mov     rax, [rax+28h]
0x18001ab29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab2e  mov     ebx, eax
0x18001ab30  test    eax, eax
0x18001ab32  js      loc_18001AF26
0x18001ab38  mov     rax, [rdi]
0x18001ab3b  mov     r8d, 1
0x18001ab41  mov     rdx, r13
0x18001ab44  mov     rcx, rdi
0x18001ab47  mov     rax, [rax+0D0h]
0x18001ab4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab53  mov     ebx, eax
0x18001ab55  test    eax, eax
0x18001ab57  js      loc_18001AF26
0x18001ab5d  lea     rdx, aClear_0; "CLEAR"
0x18001ab64  mov     rcx, rsi; String1
0x18001ab67  call    cs:__imp__wcsicmp
0x18001ab6d  test    eax, eax
0x18001ab6f  jnz     short loc_18001AB97
0x18001ab71  mov     rax, [rsp+350h+var_300]
0x18001ab76  mov     rdx, rdi; struct IExtensionContext *
0x18001ab79  mov     r9, [rsp+350h+var_2F0]; unsigned __int16 *
0x18001ab7e  mov     r8, [rsp+350h+var_2E8]; unsigned __int16 *
0x18001ab83  mov     [rsp+350h+var_328], r14; struct ICommandObjectList *
0x18001ab88  mov     [rsp+350h+String1], rax; struct ICommandParameterList *
0x18001ab8d  call    ?DoClear@CONFIG_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEBG1PEAVICommandParameterList@@PEAVICommandObjectList@@@Z; CONFIG_OBJECT_EXTENSION::DoClear(IExtensionContext *,ushort const *,ushort const *,ICommandParameterList *,ICommandObjectList *)
0x18001ab92  jmp     loc_18001A9CB
0x18001ab97  lea     rdx, aRegister; "REGISTER"
0x18001ab9e  mov     rcx, rsi; String1
0x18001aba1  call    cs:__imp__wcsicmp
0x18001aba7  test    eax, eax
0x18001aba9  jnz     short loc_18001ABD1
0x18001abab  mov     rax, [rsp+350h+var_300]
0x18001abb0  mov     rdx, rdi; struct IExtensionContext *
0x18001abb3  mov     r9, [rsp+350h+var_2F0]; unsigned __int16 *
0x18001abb8  mov     r8, [rsp+350h+var_2E8]; unsigned __int16 *
0x18001abbd  mov     [rsp+350h+var_328], r14; struct ICommandObjectList *
0x18001abc2  mov     [rsp+350h+String1], rax; struct ICommandParameterList *
0x18001abc7  call    ?RegisterSection@CONFIG_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEBG1PEAVICommandParameterList@@PEAVICommandObjectList@@@Z; CONFIG_OBJECT_EXTENSION::RegisterSection(IExtensionContext *,ushort const *,ushort const *,ICommandParameterList *,ICommandObjectList *)
0x18001abcc  jmp     loc_18001A9CB
0x18001abd1  lea     rdx, aDeregister_0; "DEREGISTER"
0x18001abd8  mov     rcx, rsi; String1
0x18001abdb  call    cs:__imp__wcsicmp
0x18001abe1  test    eax, eax
0x18001abe3  jnz     short loc_18001AC0B
0x18001abe5  mov     rax, [rsp+350h+var_300]
0x18001abea  mov     rdx, rdi; struct IExtensionContext *
0x18001abed  mov     r9, [rsp+350h+var_2F0]; unsigned __int16 *
0x18001abf2  mov     r8, [rsp+350h+var_2E8]; unsigned __int16 *
0x18001abf7  mov     [rsp+350h+var_328], r14; struct ICommandObjectList *
0x18001abfc  mov     [rsp+350h+String1], rax; struct ICommandParameterList *
0x18001ac01  call    ?DeregisterSection@CONFIG_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEBG1PEAVICommandParameterList@@PEAVICommandObjectList@@@Z; CONFIG_OBJECT_EXTENSION::DeregisterSection(IExtensionContext *,ushort const *,ushort const *,ICommandParameterList *,ICommandObjectList *)
0x18001ac06  jmp     loc_18001A9CB
0x18001ac0b  mov     rcx, [rsp+350h+var_2E0]
0x18001ac10  mov     r8, r15
0x18001ac13  mov     rax, [rdi]
0x18001ac16  mov     rdx, r12
0x18001ac19  mov     r9, [rsp+350h+var_2D8]
0x18001ac1e  mov     dword ptr [rsp+350h+var_328], 0
0x18001ac26  mov     [rsp+350h+String1], rcx
0x18001ac2b  mov     rcx, rdi
0x18001ac2e  mov     rax, [rax+38h]
0x18001ac32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac37  mov     ebx, eax
0x18001ac39  test    eax, eax
0x18001ac3b  js      loc_18001AF26
0x18001ac41  mov     rcx, [rsp+350h+var_2E0]
0x18001ac46  lea     rdx, [rbp+250h+var_2D0]
0x18001ac4a  mov     rax, [rcx]
0x18001ac4d  mov     rax, [rax+20h]
0x18001ac51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac56  mov     ebx, eax
0x18001ac58  test    eax, eax
0x18001ac5a  js      loc_18001AF26
0x18001ac60  mov     eax, [rbp+250h+var_2D0]
0x18001ac63  test    eax, eax
0x18001ac65  jnz     short loc_18001AC9F
0x18001ac67  mov     ebx, 80070002h
0x18001ac6c  mov     [rbp+250h+Arguments+8], r15
0x18001ac70  mov     r8d, 0C0000419h
0x18001ac76  mov     rax, [rdi]
0x18001ac79  lea     r9, [rbp+250h+Arguments]
0x18001ac7d  mov     edx, ebx
0x18001ac7f  mov     dword ptr [rsp+350h+String1], 0
0x18001ac87  mov     rcx, rdi
0x18001ac8a  mov     [rbp+250h+Arguments], r12
0x18001ac8e  mov     rax, [rax+90h]
0x18001ac95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac9a  jmp     loc_18001AF26
0x18001ac9f  cmp     eax, 1
0x18001aca2  jbe     short loc_18001ACB5
0x18001aca4  mov     ebx, 80070032h
0x18001aca9  mov     [rbp+250h+Arguments+8], rsi
0x18001acad  mov     r8d, 0C00003EBh
0x18001acb3  jmp     short loc_18001AC76
0x18001acb5  mov     rcx, [rsp+350h+var_2E0]
0x18001acba  lea     r8, [rsp+350h+var_2F8]
0x18001acbf  xor     edx, edx
0x18001acc1  mov     rax, [rcx]
0x18001acc4  mov     rax, [rax+28h]
0x18001acc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001accd  mov     ebx, eax
0x18001accf  test    eax, eax
0x18001acd1  js      loc_18001AF26
0x18001acd7  cmp     [rsp+350h+var_2F8], 0
0x18001acdd  jnz     short loc_18001ACE9
0x18001acdf  mov     ebx, 80004003h
0x18001ace4  jmp     loc_18001AF26
0x18001ace9  mov     rcx, [rsp+350h+var_2F8]
0x18001acee  lea     rdx, [rbp+250h+var_2C8]
0x18001acf2  mov     rax, [rcx]
0x18001acf5  mov     rax, [rax+30h]
0x18001acf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001acfe  mov     ebx, eax
0x18001ad00  test    eax, eax
0x18001ad02  js      loc_18001AF26
0x18001ad08  cmp     [rbp+250h+var_2C8], 0
0x18001ad0d  jnz     short loc_18001AD19
0x18001ad0f  mov     ebx, 80004003h
0x18001ad14  jmp     loc_18001AF43
0x18001ad19  mov     rcx, [rsp+350h+var_2F8]
0x18001ad1e  lea     rdx, [rbp+250h+var_2C0]
0x18001ad22  mov     rax, [rcx]
0x18001ad25  mov     rax, [rax+28h]
0x18001ad29  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
