# MODULE_OBJECT_EXTENSION::DoInstall(ICommandParameterList *,IExtensionContext *,ICommandObjectList *,IXMLDOMDocument *)

- ea: `0x180020fd8`
- end: `0x18002164f`
- name: `?DoInstall@MODULE_OBJECT_EXTENSION@@AEAAJPEAVICommandParameterList@@PEAVIExtensionContext@@PEAVICommandObjectList@@PEAUIXMLDOMDocument@@@Z`
- size: `1655`
- prototype: `int(MODULE_OBJECT_EXTENSION *__hidden this, struct ICommandParameterList *, struct IExtensionContext *, struct ICommandObjectList *, struct IXMLDOMDocument *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180021b60`

## callees

- `0x180001044`
- `0x180001fb0`
- `0x180004a70`
- `0x180005440`
- `0x180012ad4`
- `0x180012ce0`
- `0x180020fd8`
- `0x1800221e0`
- `0x18002a6cc`
- `0x18002b0cc`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## pseudocode

```c
__int64 __fastcall MODULE_OBJECT_EXTENSION::DoInstall(
        MODULE_OBJECT_EXTENSION *this,
        struct ICommandParameterList *a2,
        struct IExtensionContext *a3,
        struct ICommandObjectList *a4,
        struct IXMLDOMDocument *a5)
{
  COMMAND_OBJECT *v5; // rdi
  struct INativeConfigurationElement *v9; // r14
  int GlobalModulesConfiguration; // ebx
  int v12; // eax
  unsigned __int16 *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // r8
  APP_OBJECT_UTILS *v16; // rcx
  COMMAND_OBJECT *v17; // rax
  struct INativeConfigurationElement *v18; // r9
  int v19; // eax
  APP_OBJECT_UTILS *v20; // rcx
  unsigned int v21; // r8d
  int v23; // [rsp+28h] [rbp-D8h]
  int v24; // [rsp+28h] [rbp-D8h]
  struct ICommandParameterList *v25; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v26; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v27; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v28; // [rsp+68h] [rbp-98h] BYREF
  int v29; // [rsp+70h] [rbp-90h] BYREF
  int v30; // [rsp+74h] [rbp-8Ch] BYREF
  __int64 v31; // [rsp+78h] [rbp-88h] BYREF
  struct INativeConfigurationElement *v32; // [rsp+80h] [rbp-80h] BYREF
  struct INativeSectionException *v33; // [rsp+88h] [rbp-78h] BYREF
  __int64 v34; // [rsp+90h] [rbp-70h] BYREF
  __int64 v35; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v36[32]; // [rsp+A0h] [rbp-60h] BYREF
  __int16 *v37; // [rsp+C0h] [rbp-40h]
  int v38; // [rsp+C8h] [rbp-38h]
  __int16 v39; // [rsp+CCh] [rbp-34h]
  int v40; // [rsp+D0h] [rbp-30h]
  _BYTE v41[32]; // [rsp+D8h] [rbp-28h] BYREF
  __int16 *v42; // [rsp+F8h] [rbp-8h]
  int v43; // [rsp+100h] [rbp+0h]
  __int16 v44; // [rsp+104h] [rbp+4h]
  int v45; // [rsp+108h] [rbp+8h]
  unsigned __int16 *v46[2]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v47; // [rsp+120h] [rbp+20h]
  __int16 v48; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v49[510]; // [rsp+132h] [rbp+32h] BYREF
  __int16 v50; // [rsp+330h] [rbp+230h] BYREF
  _BYTE v51[510]; // [rsp+332h] [rbp+232h] BYREF

  v5 = 0;
  v35 = 0;
  v34 = 0;
  v31 = 0;
  v32 = 0;
  v26 = 0;
  v47 = 0;
  v33 = 0;
  v29 = 1;
  *(_OWORD *)v46 = 0;
  v9 = 0;
  memset_0(v49, 0, sizeof(v49));
  v38 = 512;
  v37 = &v48;
  v39 = 256;
  v40 = 0;
  v48 = 0;
  v28 = 0;
  v27 = 0;
  v25 = 0;
  memset_0(v51, 0, sizeof(v51));
  v43 = 512;
  v44 = 256;
  v42 = &v50;
  v45 = 0;
  v50 = 0;
  v30 = 0;
  if ( a4 && a3 && a2 )
  {
    GlobalModulesConfiguration = (*(__int64 (__fastcall **)(struct ICommandParameterList *, struct ICommandParameterList **))(*(_QWORD *)a2 + 80LL))(
                                   a2,
                                   &v25);
    if ( GlobalModulesConfiguration < 0 )
      goto LABEL_45;
    v12 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, const unsigned __int16 *, unsigned __int16 **))(*(_QWORD *)v25 + 40LL))(
            v25,
            L"name",
            &v28);
    GlobalModulesConfiguration = v12;
    if ( v12 == -2147023483 )
    {
      if ( (*(int (__fastcall **)(struct ICommandParameterList *, const unsigned __int16 *, unsigned __int16 **))(*(_QWORD *)v25 + 40LL))(
             v25,
             L"MODULE.NAME",
             &v28) < 0 )
      {
        v13 = L"name";
LABEL_8:
        GlobalModulesConfiguration = -2147024809;
        v46[1] = 0;
        v14 = 2147942487LL;
        v15 = 3221226486LL;
LABEL_9:
        v46[0] = v13;
        (*(void (__fastcall **)(struct IExtensionContext *, __int64, __int64, unsigned __int16 **, _DWORD))(*(_QWORD *)a3 + 144LL))(
          a3,
          v14,
          v15,
          v46,
          0);
        goto LABEL_45;
      }
    }
    else if ( v12 < 0 )
    {
      goto LABEL_45;
    }
    if ( (*(int (__fastcall **)(struct ICommandParameterList *, const wchar_t *, __int64 *))(*(_QWORD *)v25 + 40LL))(
           v25,
           L"image",
           &v35) < 0 )
    {
      v13 = L"image";
      goto LABEL_8;
    }
    GlobalModulesConfiguration = APP_OBJECT_UTILS::PopBooleanParameter(v16, a3, v25, L"add", &v29, v23, 1);
    if ( (int)(GlobalModulesConfiguration + 0x80000000) < 0 || GlobalModulesConfiguration == -2147023483 )
    {
      GlobalModulesConfiguration = APP_OBJECT_UTILS::PopBooleanParameter(
                                     (APP_OBJECT_UTILS *)0x80000000LL,
                                     a3,
                                     v25,
                                     L"lock",
                                     &v30,
                                     v24,
                                     1);
      if ( (int)(GlobalModulesConfiguration + 0x80000000) < 0 || GlobalModulesConfiguration == -2147023483 )
      {
        GlobalModulesConfiguration = MODULE_OBJECT_EXTENSION::GetGlobalModulesConfiguration(
                                       (MODULE_OBJECT_EXTENSION *)0x80000000LL,
                                       a3,
                                       &v32,
                                       &v33);
        if ( GlobalModulesConfiguration >= 0 )
        {
          v9 = v32;
          GlobalModulesConfiguration = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 *))(*(_QWORD *)v32 + 40LL))(
                                         v32,
                                         &v31);
          if ( GlobalModulesConfiguration >= 0 )
          {
            GlobalModulesConfiguration = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64 *))(*(_QWORD *)v31 + 48LL))(
                                           v31,
                                           L"add",
                                           &v26);
            if ( GlobalModulesConfiguration >= 0 )
            {
              if ( v26 )
              {
                v17 = (COMMAND_OBJECT *)operator new(0xD8u);
                v5 = v17;
                if ( v17 )
                {
                  COMMAND_OBJECT::COMMAND_OBJECT(v17);
                  *(_QWORD *)v5 = &GLOBAL_MODULE_OBJECT::`vftable';
                  COMMAND_OBJECT::SetConfigElement(v5, v18);
                  COMMAND_OBJECT::SetParentElement(v5, v9);
                  GlobalModulesConfiguration = (*(__int64 (__fastcall **)(struct IExtensionContext *, const wchar_t *, __int16 *, __int64))(*(_QWORD *)a3 + 72LL))(
                                                 a3,
                                                 L"MACHINE/WEBROOT/APPHOST",
                                                 &v48,
                                                 256);
                  if ( GlobalModulesConfiguration >= 0 )
                  {
                    STRU::SyncWithBuffer((STRU *)v36);
                    GlobalModulesConfiguration = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64, const unsigned __int16 *, unsigned __int16 *))(*(_QWORD *)a3 + 96LL))(
                                                   a3,
                                                   v26,
                                                   L"name",
                                                   v28);
                    if ( GlobalModulesConfiguration >= 0 )
                    {
                      GlobalModulesConfiguration = (*(__int64 (__fastcall **)(struct IExtensionContext *, COMMAND_OBJECT *, struct ICommandParameterList *, _QWORD, struct IXMLDOMDocument *, int))(*(_QWORD *)a3 + 168LL))(
                                                     a3,
                                                     v5,
                                                     v25,
                                                     0,
                                                     a5,
                                                     1);
                      if ( GlobalModulesConfiguration >= 0 )
                      {
                        v19 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v31 + 56LL))(
                                v31,
                                v26,
                                0xFFFFFFFFLL,
                                0);
                        GlobalModulesConfiguration = v19;
                        if ( v19 >= 0 )
                        {
                          v46[0] = L"GLOBAL MODULE";
                          v46[1] = v28;
                          GlobalModulesConfiguration = APP_OBJECT_UTILS::AddStatusObject(
                                                         v20,
                                                         a4,
                                                         v21,
                                                         (const unsigned __int16 **const)v46);
                          if ( GlobalModulesConfiguration >= 0 )
                          {
                            GlobalModulesConfiguration = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int16 *, _QWORD))(*(_QWORD *)a3 + 208LL))(
                                                           a3,
                                                           v37,
                                                           0);
                            if ( GlobalModulesConfiguration >= 0 )
                            {
                              if ( !v29
                                || (GlobalModulesConfiguration = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64 *))(*(_QWORD *)a3 + 192LL))(
                                                                   a3,
                                                                   &v27),
                                    GlobalModulesConfiguration >= 0)
                                && (GlobalModulesConfiguration = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, unsigned __int16 *))(*(_QWORD *)v27 + 56LL))(
                                                                   v27,
                                                                   L"name",
                                                                   v28),
                                    GlobalModulesConfiguration >= 0)
                                && ((*(int (__fastcall **)(struct ICommandParameterList *, const wchar_t *, __int64 *))(*(_QWORD *)v25 + 40LL))(
                                      v25,
                                      L"preCondition",
                                      &v34) < 0
                                 || (GlobalModulesConfiguration = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64))(*(_QWORD *)v27 + 56LL))(
                                                                    v27,
                                                                    L"preCondition",
                                                                    v34),
                                     GlobalModulesConfiguration >= 0))
                                && (!v30
                                 || (GlobalModulesConfiguration = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *))(*(_QWORD *)v27 + 56LL))(
                                                                    v27,
                                                                    L"lockItem",
                                                                    L"true"),
                                     GlobalModulesConfiguration >= 0))
                                && (GlobalModulesConfiguration = (*(__int64 (__fastcall **)(MODULE_OBJECT_EXTENSION *, const wchar_t *, const wchar_t *, const wchar_t *, struct IExtensionContext *, __int64, struct ICommandObjectList *, _QWORD))(*(_QWORD *)this + 40LL))(
                                                                   this,
                                                                   L"MODULE",
                                                                   L"ADD",
                                                                   &Str,
                                                                   a3,
                                                                   v27,
                                                                   a4,
                                                                   0),
                                    GlobalModulesConfiguration >= 0) )
                              {
                                GlobalModulesConfiguration = 0;
                              }
                            }
                          }
                        }
                        else
                        {
                          v14 = 2147942583LL;
                          if ( v19 == -2147024713 )
                          {
                            v13 = v28;
                            v15 = 3221226483LL;
                            v46[1] = 0;
                            goto LABEL_9;
                          }
                        }
                      }
                    }
                  }
                }
                else
                {
                  GlobalModulesConfiguration = -2147024888;
                  v5 = 0;
                }
              }
              else
              {
                GlobalModulesConfiguration = -2147467261;
              }
            }
          }
        }
        else
        {
          if ( v33 )
            (*(void (__fastcall **)(struct IExtensionContext *, _QWORD, const wchar_t *, struct INativeSectionException *, _DWORD))(*(_QWORD *)a3 + 112LL))(
              a3,
              (unsigned int)GlobalModulesConfiguration,
              L"MODULE",
              v33,
              0);
          v9 = v32;
        }
      }
    }
  }
  else
  {
    GlobalModulesConfiguration = -2147024809;
  }
LABEL_45:
  if ( v31 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    v31 = 0;
  }
  if ( v9 )
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v9 + 16LL))(v9);
  if ( v26 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    v26 = 0;
  }
  if ( v33 )
    (*(void (__fastcall **)(struct INativeSectionException *))(*(_QWORD *)v33 + 16LL))(v33);
  if ( v27 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    v27 = 0;
  }
  if ( v5 )
    (*(void (__fastcall **)(COMMAND_OBJECT *))(*(_QWORD *)v5 + 16LL))(v5);
  if ( v25 )
  {
    (*(void (__fastcall **)(struct ICommandParameterList *))(*(_QWORD *)v25 + 16LL))(v25);
    v25 = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v41);
  BUFFER::~BUFFER((BUFFER *)v36);
  return (unsigned int)GlobalModulesConfiguration;
}

```

## disassembly

```asm
0x180020fd8  push    rbp
0x180020fda  push    rbx
0x180020fdb  push    rsi
0x180020fdc  push    rdi
0x180020fdd  push    r12
0x180020fdf  push    r13
0x180020fe1  push    r14
0x180020fe3  push    r15
0x180020fe5  lea     rbp, [rsp-448h]
0x180020fed  sub     rsp, 548h
0x180020ff4  mov     rax, cs:__security_cookie
0x180020ffb  xor     rax, rsp
0x180020ffe  mov     [rbp+480h+var_50], rax
0x180021005  mov     r12, [rbp+480h+arg_20]
0x18002100c  xor     edi, edi
0x18002100e  mov     rsi, r8
0x180021011  mov     [rbp+480h+var_4E8], rdi
0x180021015  mov     rbx, rdx
0x180021018  mov     [rbp+480h+var_4F0], rdi
0x18002101c  mov     r13, rcx
0x18002101f  mov     [rsp+580h+var_508], rdi
0x180021024  xorps   xmm0, xmm0
0x180021027  mov     [rbp+480h+var_500], rdi
0x18002102b  xor     eax, eax
0x18002102d  mov     [rsp+580h+var_528], rdi
0x180021032  xor     edx, edx; Val
0x180021034  mov     [rbp+480h+var_460], rax
0x180021038  mov     r8d, 1FEh; Size
0x18002103e  mov     [rbp+480h+var_4F8], rdi
0x180021042  lea     rcx, [rbp+480h+var_44E]; void *
0x180021046  mov     [rsp+580h+var_510], 1
0x18002104e  movups  xmmword ptr [rbp+480h+var_470], xmm0
0x180021052  mov     r14d, edi
0x180021055  mov     r15, r9
0x180021058  call    memset_0
0x18002105d  lea     rax, [rbp+480h+var_450]
0x180021061  mov     [rbp+480h+var_4B8], 200h
0x180021068  xor     edx, edx; Val
0x18002106a  mov     [rbp+480h+var_4C0], rax
0x18002106e  mov     r8d, 1FEh; Size
0x180021074  mov     [rbp+480h+var_4B4], 100h
0x18002107a  lea     rcx, [rbp+480h+var_24E]; void *
0x180021081  mov     [rbp+480h+var_4B0], edi
0x180021084  mov     [rbp+480h+var_450], di
0x180021088  mov     [rsp+580h+var_518], rdi
0x18002108d  mov     [rsp+580h+var_520], rdi
0x180021092  mov     [rsp+580h+var_530], rdi
0x180021097  call    memset_0
0x18002109c  xor     ecx, ecx
0x18002109e  mov     [rbp+480h+var_480], 200h
0x1800210a5  mov     [rbp+480h+var_47C], 100h
0x1800210ab  lea     rax, [rbp+480h+var_250]
0x1800210b2  mov     [rbp+480h+var_488], rax
0x1800210b6  mov     [rbp+480h+var_478], ecx
0x1800210b9  mov     [rbp+480h+var_250], cx
0x1800210c0  mov     [rsp+580h+var_50C], ecx
0x1800210c4  test    r15, r15
0x1800210c7  jz      loc_18002155A
0x1800210cd  test    rsi, rsi
0x1800210d0  jz      loc_18002155A
0x1800210d6  test    rbx, rbx
0x1800210d9  jz      loc_18002155A
0x1800210df  mov     rax, [rbx]
0x1800210e2  lea     rdx, [rsp+580h+var_530]
0x1800210e7  mov     rcx, rbx
0x1800210ea  mov     rax, [rax+50h]
0x1800210ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800210f3  mov     ebx, eax
0x1800210f5  test    eax, eax
0x1800210f7  js      loc_18002155F
0x1800210fd  mov     rcx, [rsp+580h+var_530]
0x180021102  lea     r8, [rsp+580h+var_518]
0x180021107  lea     rdx, aName_0; "name"
0x18002110e  mov     rax, [rcx]
0x180021111  mov     rax, [rax+28h]
0x180021115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002111a  mov     ebx, eax
0x18002111c  cmp     eax, 80070585h
0x180021121  jnz     short loc_18002117F
0x180021123  mov     rcx, [rsp+580h+var_530]
0x180021128  lea     r8, [rsp+580h+var_518]
0x18002112d  lea     rdx, aModuleName_0; "MODULE.NAME"
0x180021134  mov     rax, [rcx]
0x180021137  mov     rax, [rax+28h]
0x18002113b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021140  test    eax, eax
0x180021142  jns     short loc_180021187
0x180021144  lea     rax, aName_0; "name"
0x18002114b  mov     ebx, 80070057h
0x180021150  mov     [rbp+480h+var_470+8], rdi
0x180021154  mov     edx, ebx
0x180021156  mov     dword ptr [rsp+580h+var_560], edi
0x18002115a  mov     r8d, 0C00003F6h
0x180021160  mov     [rbp+480h+var_470], rax
0x180021164  lea     r9, [rbp+480h+var_470]
0x180021168  mov     rax, [rsi]
0x18002116b  mov     rcx, rsi
0x18002116e  mov     rax, [rax+90h]
0x180021175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002117a  jmp     loc_18002155F
0x18002117f  test    eax, eax
0x180021181  js      loc_18002155F
0x180021187  mov     rcx, [rsp+580h+var_530]
0x18002118c  lea     r8, [rbp+480h+var_4E8]
0x180021190  lea     rdx, aImage; "image"
0x180021197  mov     rax, [rcx]
0x18002119a  mov     rax, [rax+28h]
0x18002119e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800211a3  test    eax, eax
0x1800211a5  jns     short loc_1800211B0
0x1800211a7  lea     rax, aImage; "image"
0x1800211ae  jmp     short loc_18002114B
0x1800211b0  mov     r8, [rsp+580h+var_530]; struct ICommandParameterList *
0x1800211b5  lea     rax, [rsp+580h+var_510]
0x1800211ba  mov     [rsp+580h+var_550], 1; int
0x1800211c2  lea     r9, aAdd; "add"
0x1800211c9  mov     rdx, rsi; struct IExtensionContext *
0x1800211cc  mov     [rsp+580h+var_560], rax; int *
0x1800211d1  call    ?PopBooleanParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAHHH@Z; APP_OBJECT_UTILS::PopBooleanParameter(IExtensionContext *,ICommandParameterList *,ushort const *,int *,int,int)
0x1800211d6  mov     ecx, 80000000h; this
0x1800211db  mov     ebx, eax
0x1800211dd  add     eax, ecx
0x1800211df  test    ecx, eax
0x1800211e1  jnz     short loc_1800211EF
0x1800211e3  cmp     ebx, 80070585h
0x1800211e9  jnz     loc_18002155F
0x1800211ef  mov     r8, [rsp+580h+var_530]; struct ICommandParameterList *
0x1800211f4  lea     rax, [rsp+580h+var_50C]
0x1800211f9  mov     [rsp+580h+var_550], 1; int
0x180021201  lea     r9, aLock_0; "lock"
0x180021208  mov     rdx, rsi; struct IExtensionContext *
0x18002120b  mov     [rsp+580h+var_560], rax; int *
0x180021210  call    ?PopBooleanParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAHHH@Z; APP_OBJECT_UTILS::PopBooleanParameter(IExtensionContext *,ICommandParameterList *,ushort const *,int *,int,int)
0x180021215  mov     ecx, 80000000h; this
0x18002121a  mov     ebx, eax
0x18002121c  add     eax, ecx
0x18002121e  test    ecx, eax
0x180021220  jnz     short loc_18002122E
0x180021222  cmp     ebx, 80070585h
0x180021228  jnz     loc_18002155F
0x18002122e  lea     r9, [rbp+480h+var_4F8]; struct INativeSectionException **
0x180021232  mov     rdx, rsi; struct IExtensionContext *
0x180021235  lea     r8, [rbp+480h+var_500]; struct INativeConfigurationElement **
0x180021239  call    ?GetGlobalModulesConfiguration@MODULE_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEAPEAVINativeConfigurationElement@@PEAPEAVINativeSectionException@@@Z; MODULE_OBJECT_EXTENSION::GetGlobalModulesConfiguration(IExtensionContext *,INativeConfigurationElement * *,INativeSectionException * *)
0x18002123e  mov     ebx, eax
0x180021240  test    eax, eax
0x180021242  jns     short loc_180021275
0x180021244  mov     rcx, [rbp+480h+var_4F8]
0x180021248  test    rcx, rcx
0x18002124b  jz      short loc_18002126C
0x18002124d  mov     rax, [rsi]
0x180021250  lea     r8, aModule_0; "MODULE"
0x180021257  mov     r9, rcx
0x18002125a  mov     dword ptr [rsp+580h+var_560], edi
0x18002125e  mov     edx, ebx
0x180021260  mov     rcx, rsi
0x180021263  mov     rax, [rax+70h]
0x180021267  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002126c  mov     r14, [rbp+480h+var_500]
0x180021270  jmp     loc_18002155F
0x180021275  mov     r14, [rbp+480h+var_500]
0x180021279  lea     rdx, [rsp+580h+var_508]
0x18002127e  mov     rcx, r14
0x180021281  mov     rax, [r14]
0x180021284  mov     rax, [rax+28h]
0x180021288  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002128d  mov     ebx, eax
0x18002128f  test    eax, eax
0x180021291  js      loc_18002155F
0x180021297  mov     rcx, [rsp+580h+var_508]
0x18002129c  lea     r8, [rsp+580h+var_528]
0x1800212a1  lea     rdx, aAdd; "add"
0x1800212a8  mov     rax, [rcx]
0x1800212ab  mov     rax, [rax+30h]
0x1800212af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800212b4  mov     ebx, eax
0x1800212b6  test    eax, eax
0x1800212b8  js      loc_18002155F
0x1800212be  cmp     [rsp+580h+var_528], rdi
0x1800212c3  jnz     short loc_1800212CF
0x1800212c5  mov     ebx, 80004003h
0x1800212ca  jmp     loc_18002155F
0x1800212cf  mov     ecx, 0D8h; Size
0x1800212d4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800212d9  mov     rdi, rax
0x1800212dc  test    rax, rax
0x1800212df  jz      loc_180021551
0x1800212e5  mov     r9, [rsp+580h+var_528]
0x1800212ea  mov     rcx, rax; this
0x1800212ed  call    ??0COMMAND_OBJECT@@QEAA@XZ; COMMAND_OBJECT::COMMAND_OBJECT(void)
0x1800212f2  lea     rcx, ??_7GLOBAL_MODULE_OBJECT@@6B@; const GLOBAL_MODULE_OBJECT::`vftable'
0x1800212f9  mov     rdx, r9; struct INativeConfigurationElement *
0x1800212fc  mov     [rdi], rcx
0x1800212ff  mov     rcx, rdi; this
0x180021302  call    ?SetConfigElement@COMMAND_OBJECT@@QEAAXPEAVINativeConfigurationElement@@@Z; COMMAND_OBJECT::SetConfigElement(INativeConfigurationElement *)
0x180021307  mov     rdx, r14; struct INativeConfigurationElement *
0x18002130a  mov     rcx, rdi; this
0x18002130d  call    ?SetParentElement@COMMAND_OBJECT@@QEAAXPEAVINativeConfigurationElement@@@Z; COMMAND_OBJECT::SetParentElement(INativeConfigurationElement *)
0x180021312  mov     rax, [rsi]
0x180021315  lea     r8, [rbp+480h+var_450]
0x180021319  mov     r9d, 100h
0x18002131f  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180021326  mov     rcx, rsi
0x180021329  mov     rax, [rax+48h]
0x18002132d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021332  mov     ebx, eax
0x180021334  test    eax, eax
0x180021336  js      loc_18002155F
0x18002133c  lea     rcx, [rbp+480h+var_4E0]; this
0x180021340  call    ?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x180021345  mov     rax, [rsi]
0x180021348  lea     r8, aName_0; "name"
0x18002134f  mov     r9, [rsp+580h+var_518]
0x180021354  mov     rcx, rsi
0x180021357  mov     rdx, [rsp+580h+var_528]
0x18002135c  mov     rax, [rax+60h]
0x180021360  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021365  mov     ebx, eax
0x180021367  test    eax, eax
0x180021369  js      loc_18002155F
0x18002136f  mov     rax, [rsi]
0x180021372  xor     r9d, r9d
0x180021375  mov     r8, [rsp+580h+var_530]
0x18002137a  mov     rdx, rdi
0x18002137d  mov     dword ptr [rsp+580h+var_558], 1
0x180021385  mov     rcx, rsi
0x180021388  mov     [rsp+580h+var_560], r12
0x18002138d  mov     rax, [rax+0A8h]
0x180021394  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021399  mov     ebx, eax
0x18002139b  test    eax, eax
0x18002139d  js      loc_18002155F
0x1800213a3  mov     rcx, [rsp+580h+var_508]
0x1800213a8  xor     r9d, r9d
0x1800213ab  mov     rdx, [rsp+580h+var_528]
0x1800213b0  or      r8d, 0FFFFFFFFh
0x1800213b4  mov     rax, [rcx]
0x1800213b7  mov     rax, [rax+38h]
0x1800213bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800213c0  mov     ebx, eax
0x1800213c2  test    eax, eax
0x1800213c4  jns     short loc_1800213F3
0x1800213c6  mov     edx, 800700B7h
0x1800213cb  cmp     eax, edx
0x1800213cd  jnz     loc_18002155F
0x1800213d3  mov     rax, [rsp+580h+var_518]
0x1800213d8  mov     r8d, 0C00003F3h
0x1800213de  mov     [rbp+480h+var_470+8], 0
0x1800213e6  mov     dword ptr [rsp+580h+var_560], 0
0x1800213ee  jmp     loc_180021160
0x1800213f3  lea     rax, aGlobalModule; "GLOBAL MODULE"
0x1800213fa  mov     rdx, r15; struct ICommandObjectList *
0x1800213fd  mov     [rbp+480h+var_470], rax
0x180021401  lea     r9, [rbp+480h+var_470]; unsigned __int16 **
0x180021405  mov     rax, [rsp+580h+var_518]
0x18002140a  mov     [rbp+480h+var_470+8], rax
0x18002140e  call    ?AddStatusObject@APP_OBJECT_UTILS@@QEAAJPEAVICommandObjectList@@KQEAPEBG@Z; APP_OBJECT_UTILS::AddStatusObject(ICommandObjectList *,ulong,ushort const * * const)
0x180021413  mov     ebx, eax
0x180021415  test    eax, eax
0x180021417  js      loc_18002155F
0x18002141d  mov     rax, [rsi]
0x180021420  xor     r8d, r8d
0x180021423  mov     rdx, [rbp+480h+var_4C0]
0x180021427  mov     rcx, rsi
0x18002142a  mov     rax, [rax+0D0h]
0x180021431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021436  mov     ebx, eax
0x180021438  test    eax, eax
0x18002143a  js      loc_18002155F
0x180021440  cmp     [rsp+580h+var_510], 0
0x180021445  jz      loc_18002154D
0x18002144b  mov     rax, [rsi]
0x18002144e  lea     rdx, [rsp+580h+var_520]
0x180021453  mov     rcx, rsi
0x180021456  mov     rax, [rax+0C0h]
0x18002145d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021462  mov     ebx, eax
0x180021464  test    eax, eax
0x180021466  js      loc_18002155F
0x18002146c  mov     rcx, [rsp+580h+var_520]
0x180021471  lea     rdx, aName_0; "name"
0x180021478  mov     r8, [rsp+580h+var_518]
0x18002147d  mov     rax, [rcx]
0x180021480  mov     rax, [rax+38h]
0x180021484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021489  mov     ebx, eax
0x18002148b  test    eax, eax
0x18002148d  js      loc_18002155F
0x180021493  mov     rcx, [rsp+580h+var_530]
0x180021498  lea     r8, [rbp+480h+var_4F0]
0x18002149c  lea     rdx, aPrecondition; "preCondition"
0x1800214a3  mov     rax, [rcx]
0x1800214a6  mov     rax, [rax+28h]
0x1800214aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800214af  test    eax, eax
0x1800214b1  js      short loc_1800214D9
0x1800214b3  mov     rcx, [rsp+580h+var_520]
0x1800214b8  lea     rdx, aPrecondition; "preCondition"
0x1800214bf  mov     r8, [rbp+480h+var_4F0]
0x1800214c3  mov     rax, [rcx]
  ... truncated ...
```
