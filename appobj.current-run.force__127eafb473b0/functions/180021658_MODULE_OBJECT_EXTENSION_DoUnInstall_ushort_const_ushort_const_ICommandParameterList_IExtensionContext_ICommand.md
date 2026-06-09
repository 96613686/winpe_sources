# MODULE_OBJECT_EXTENSION::DoUnInstall(ushort const *,ushort const *,ICommandParameterList *,IExtensionContext *,ICommandObjectList *)

- ea: `0x180021658`
- end: `0x180021b54`
- name: `?DoUnInstall@MODULE_OBJECT_EXTENSION@@AEAAJPEBG0PEAVICommandParameterList@@PEAVIExtensionContext@@PEAVICommandObjectList@@@Z`
- size: `1276`
- prototype: `int(MODULE_OBJECT_EXTENSION *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct ICommandParameterList *, struct IExtensionContext *, struct ICommandObjectList *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180021b60`

## callees

- `0x180001044`
- `0x180001fb0`
- `0x180004a70`
- `0x18000557c`
- `0x180006b6c`
- `0x180021658`
- `0x180021f7c`
- `0x1800221e0`
- `0x18002b0cc`
- `0x18002b564`
- `0x18002bd3c`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## string_xrefs

- `0x180021959`: `DELETE`
- `0x180021811`: `remove`

## pseudocode

```c
__int64 __fastcall MODULE_OBJECT_EXTENSION::DoUnInstall(
        MODULE_OBJECT_EXTENSION *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct ICommandParameterList *a4,
        struct IExtensionContext *a5,
        struct ICommandObjectList *a6)
{
  struct INativeConfigurationElement *v8; // r14
  STATUS_OBJECT *v9; // rsi
  APP_OBJECT_UTILS *v11; // rcx
  int GlobalModulesConfiguration; // ebx
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rax
  MODULE_OBJECT_EXTENSION *v17; // rcx
  MODULE_OBJECT_EXTENSION *v18; // rcx
  const unsigned __int16 *v19; // r8
  int CollectionElementByKey; // eax
  int v21; // eax
  STATUS_OBJECT *v22; // rax
  STATUS_OBJECT *v23; // rax
  struct INativeConfigurationElement **v25; // [rsp+20h] [rbp-E0h]
  int v26; // [rsp+28h] [rbp-D8h]
  struct ICommandParameterList *v27; // [rsp+50h] [rbp-B0h] BYREF
  struct INativeConfigurationElement *v28; // [rsp+58h] [rbp-A8h] BYREF
  struct INativeConfigurationElementCollection *v29; // [rsp+60h] [rbp-A0h] BYREF
  struct INativeConfigurationElement *v30; // [rsp+68h] [rbp-98h] BYREF
  __int64 v31; // [rsp+70h] [rbp-90h] BYREF
  struct INativeSectionException *v32; // [rsp+78h] [rbp-88h] BYREF
  struct INativePropertyException *v33; // [rsp+80h] [rbp-80h] BYREF
  const unsigned __int16 *v34; // [rsp+88h] [rbp-78h]
  _BYTE v35[32]; // [rsp+90h] [rbp-70h] BYREF
  __int16 *v36; // [rsp+B0h] [rbp-50h]
  int v37; // [rsp+B8h] [rbp-48h]
  __int16 v38; // [rsp+BCh] [rbp-44h]
  int v39; // [rsp+C0h] [rbp-40h]
  _BYTE v40[32]; // [rsp+C8h] [rbp-38h] BYREF
  const unsigned __int16 *v41; // [rsp+E8h] [rbp-18h]
  int v42; // [rsp+F0h] [rbp-10h]
  __int16 v43; // [rsp+F4h] [rbp-Ch]
  int v44; // [rsp+F8h] [rbp-8h]
  va_list Arguments[2]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v46; // [rsp+110h] [rbp+10h]
  __int16 v47; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v48[510]; // [rsp+122h] [rbp+22h] BYREF
  __int16 v49; // [rsp+320h] [rbp+220h] BYREF
  _BYTE v50[510]; // [rsp+322h] [rbp+222h] BYREF

  v34 = a2;
  v46 = 0;
  v29 = 0;
  v30 = 0;
  v33 = 0;
  *(_OWORD *)Arguments = 0;
  v8 = 0;
  v32 = 0;
  v9 = 0;
  v31 = 0;
  v28 = (struct INativeConfigurationElement *)1;
  memset_0(v48, 0, sizeof(v48));
  v37 = 512;
  v39 = 0;
  v47 = 0;
  v27 = 0;
  v36 = &v47;
  v38 = 256;
  memset_0(v50, 0, sizeof(v50));
  v42 = 512;
  v43 = 256;
  v41 = (const unsigned __int16 *)&v49;
  v44 = 0;
  v49 = 0;
  if ( !a3 || !a5 || !a4 )
  {
    GlobalModulesConfiguration = -2147024809;
    goto LABEL_39;
  }
  GlobalModulesConfiguration = (*(__int64 (__fastcall **)(struct ICommandParameterList *, struct ICommandParameterList **))(*(_QWORD *)a4 + 80LL))(
                                 a4,
                                 &v27);
  if ( GlobalModulesConfiguration < 0 )
    goto LABEL_39;
  if ( !*a3 )
  {
    a3 = L"MODULE.NAME";
    v13 = APP_OBJECT_UTILS::PopParameter(v11, a5, v27, L"MODULE.NAME", (struct STRU *)v40, 0, 1);
    GlobalModulesConfiguration = v13;
    if ( v13 == -2147023483 )
    {
      GlobalModulesConfiguration = -2147024846;
      Arguments[0] = (va_list)L"MODULE";
      v14 = 2147942450LL;
      v15 = 3221226474LL;
LABEL_8:
      v16 = *(_QWORD *)a5;
      Arguments[1] = (va_list)a3;
      (*(void (__fastcall **)(struct IExtensionContext *, __int64, __int64, va_list *, _DWORD))(v16 + 144))(
        a5,
        v14,
        v15,
        Arguments,
        0);
      goto LABEL_39;
    }
    if ( v13 < 0 )
      goto LABEL_39;
    a3 = v41;
  }
  GlobalModulesConfiguration = APP_OBJECT_UTILS::PopBooleanParameter(v11, a5, v27, L"remove", (int *)&v28, v26, 1);
  if ( (int)(GlobalModulesConfiguration + 0x80000000) >= 0 && GlobalModulesConfiguration != -2147023483 )
    goto LABEL_39;
  GlobalModulesConfiguration = APP_OBJECT_UTILS::ValidateEmptyParameters((APP_OBJECT_UTILS *)0x80000000LL, a5, v27);
  if ( GlobalModulesConfiguration < 0 )
    goto LABEL_39;
  GlobalModulesConfiguration = MODULE_OBJECT_EXTENSION::GetGlobalModulesConfiguration(v17, a5, &v30, &v32);
  if ( GlobalModulesConfiguration < 0 )
  {
    if ( v32 )
      (*(void (__fastcall **)(struct IExtensionContext *, _QWORD, const wchar_t *, struct INativeSectionException *, _DWORD))(*(_QWORD *)a5 + 112LL))(
        a5,
        (unsigned int)GlobalModulesConfiguration,
        L"MODULE",
        v32,
        0);
    v8 = v30;
    goto LABEL_39;
  }
  v8 = v30;
  GlobalModulesConfiguration = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, struct INativeConfigurationElementCollection **))(*(_QWORD *)v30 + 40LL))(
                                 v30,
                                 &v29);
  if ( GlobalModulesConfiguration >= 0 )
  {
    CollectionElementByKey = MODULE_OBJECT_EXTENSION::FindCollectionElementByKey(
                               v18,
                               v29,
                               v19,
                               a3,
                               v25,
                               (unsigned int *)&v28 + 1,
                               &v33);
    v14 = 2147943568LL;
    GlobalModulesConfiguration = CollectionElementByKey;
    if ( CollectionElementByKey == -2147023728 )
    {
      v15 = 3221226521LL;
      Arguments[0] = (va_list)L"GLOBAL MODULE";
      goto LABEL_8;
    }
    if ( CollectionElementByKey >= 0 )
    {
      if ( (_DWORD)v28 )
      {
        GlobalModulesConfiguration = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64 *))(*(_QWORD *)a5 + 192LL))(
                                       a5,
                                       &v31);
        if ( GlobalModulesConfiguration < 0 )
          goto LABEL_39;
        v21 = (*(__int64 (__fastcall **)(MODULE_OBJECT_EXTENSION *, const unsigned __int16 *, const wchar_t *, const unsigned __int16 *, struct IExtensionContext *, __int64, struct ICommandObjectList *, _QWORD))(*(_QWORD *)this + 40LL))(
                this,
                v34,
                L"DELETE",
                a3,
                a5,
                v31,
                a6,
                0);
        GlobalModulesConfiguration = v21;
        if ( v21 == -2147024894 )
        {
          (*(void (__fastcall **)(struct IExtensionContext *))(*(_QWORD *)a5 + 136LL))(a5);
        }
        else if ( v21 < 0 )
        {
          goto LABEL_39;
        }
      }
      GlobalModulesConfiguration = (*(__int64 (__fastcall **)(struct INativeConfigurationElementCollection *, _QWORD, _QWORD))(*(_QWORD *)v29 + 64LL))(
                                     v29,
                                     HIDWORD(v28),
                                     0);
      if ( GlobalModulesConfiguration >= 0 )
      {
        GlobalModulesConfiguration = (*(__int64 (__fastcall **)(struct IExtensionContext *, const wchar_t *, __int16 *, __int64))(*(_QWORD *)a5 + 72LL))(
                                       a5,
                                       L"MACHINE/WEBROOT/APPHOST",
                                       &v47,
                                       256);
        if ( GlobalModulesConfiguration >= 0 )
        {
          STRU::SyncWithBuffer((STRU *)v35);
          GlobalModulesConfiguration = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int16 *, _QWORD))(*(_QWORD *)a5 + 208LL))(
                                         a5,
                                         v36,
                                         0);
          if ( GlobalModulesConfiguration >= 0 )
          {
            v22 = (STATUS_OBJECT *)operator new(0x110u);
            if ( v22 )
            {
              v23 = STATUS_OBJECT::STATUS_OBJECT(v22);
              v9 = v23;
              if ( v23 )
              {
                Arguments[0] = (va_list)a3;
                Arguments[1] = 0;
                GlobalModulesConfiguration = STATUS_OBJECT::Create(v23, 0x407u, Arguments);
                if ( GlobalModulesConfiguration >= 0 )
                {
                  GlobalModulesConfiguration = (*(__int64 (__fastcall **)(struct ICommandObjectList *, STATUS_OBJECT *))(*(_QWORD *)a6 + 24LL))(
                                                 a6,
                                                 v9);
                  if ( GlobalModulesConfiguration >= 0 )
                    GlobalModulesConfiguration = 0;
                }
                goto LABEL_39;
              }
            }
            else
            {
              v9 = 0;
            }
            GlobalModulesConfiguration = -2147024888;
          }
        }
      }
    }
  }
LABEL_39:
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
  if ( v8 )
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v8 + 16LL))(v8);
  if ( v33 )
    (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v33 + 16LL))(v33);
  if ( v32 )
    (*(void (__fastcall **)(struct INativeSectionException *))(*(_QWORD *)v32 + 16LL))(v32);
  if ( v9 )
    (*(void (__fastcall **)(STATUS_OBJECT *))(*(_QWORD *)v9 + 16LL))(v9);
  if ( v27 )
  {
    (*(void (__fastcall **)(struct ICommandParameterList *))(*(_QWORD *)v27 + 16LL))(v27);
    v27 = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v40);
  BUFFER::~BUFFER((BUFFER *)v35);
  return (unsigned int)GlobalModulesConfiguration;
}

```

## disassembly

```asm
0x180021658  push    rbp
0x18002165a  push    rbx
0x18002165b  push    rsi
0x18002165c  push    rdi
0x18002165d  push    r12
0x18002165f  push    r13
0x180021661  push    r14
0x180021663  push    r15
0x180021665  lea     rbp, [rsp-438h]
0x18002166d  sub     rsp, 538h
0x180021674  mov     rax, cs:__security_cookie
0x18002167b  xor     rax, rsp
0x18002167e  mov     [rbp+470h+var_50], rax
0x180021685  mov     rdi, [rbp+470h+arg_20]
0x18002168c  xor     eax, eax
0x18002168e  mov     r12, [rbp+470h+arg_28]
0x180021695  mov     r15, r8
0x180021698  mov     [rbp+470h+var_4E8], rdx
0x18002169c  mov     r13, rcx
0x18002169f  xorps   xmm0, xmm0
0x1800216a2  mov     [rbp+470h+var_460], rax
0x1800216a6  xor     edx, edx; Val
0x1800216a8  mov     [rsp+570h+var_510], rax
0x1800216ad  mov     r8d, 1FEh; Size
0x1800216b3  mov     [rsp+570h+var_508], rax
0x1800216b8  lea     rcx, [rbp+470h+var_44E]; void *
0x1800216bc  mov     [rbp+470h+var_4F0], rax
0x1800216c0  movups  xmmword ptr [rbp+470h+Arguments], xmm0
0x1800216c4  mov     r14d, eax
0x1800216c7  mov     [rsp+570h+var_4F8], rax
0x1800216cc  mov     esi, eax
0x1800216ce  mov     dword ptr [rsp+570h+var_518+4], eax
0x1800216d2  mov     [rsp+570h+var_500], rax
0x1800216d7  mov     rbx, r9
0x1800216da  mov     dword ptr [rsp+570h+var_518], 1
0x1800216e2  call    memset_0
0x1800216e7  xor     ecx, ecx
0x1800216e9  mov     [rbp+470h+var_4B8], 200h
0x1800216f0  mov     [rbp+470h+var_4B0], ecx
0x1800216f3  lea     rax, [rbp+470h+var_450]
0x1800216f7  mov     [rbp+470h+var_450], cx
0x1800216fb  xor     edx, edx; Val
0x1800216fd  mov     [rsp+570h+var_520], rcx
0x180021702  mov     r8d, 1FEh; Size
0x180021708  lea     rcx, [rbp+470h+var_24E]; void *
0x18002170f  mov     [rbp+470h+var_4C0], rax
0x180021713  mov     [rbp+470h+var_4B4], 100h
0x180021719  call    memset_0
0x18002171e  xor     ecx, ecx
0x180021720  mov     [rbp+470h+var_480], 200h
0x180021727  mov     [rbp+470h+var_47C], 100h
0x18002172d  lea     rax, [rbp+470h+var_250]
0x180021734  mov     [rbp+470h+var_488], rax
0x180021738  mov     [rbp+470h+var_478], ecx
0x18002173b  mov     [rbp+470h+var_250], cx
0x180021742  test    r15, r15
0x180021745  jz      loc_180021A72
0x18002174b  test    rdi, rdi
0x18002174e  jz      loc_180021A72
0x180021754  test    rbx, rbx
0x180021757  jz      loc_180021A72
0x18002175d  mov     rax, [rbx]
0x180021760  lea     rdx, [rsp+570h+var_520]
0x180021765  mov     rcx, rbx
0x180021768  mov     rax, [rax+50h]
0x18002176c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021771  mov     ebx, eax
0x180021773  xor     eax, eax
0x180021775  test    ebx, ebx
0x180021777  js      loc_180021A77
0x18002177d  cmp     [r15], ax
0x180021781  jnz     short loc_1800217FF
0x180021783  mov     r8, [rsp+570h+var_520]; struct ICommandParameterList *
0x180021788  lea     r15, aModuleName_0; "MODULE.NAME"
0x18002178f  mov     dword ptr [rsp+570h+var_540], 1; int
0x180021797  mov     r9, r15; unsigned __int16 *
0x18002179a  mov     dword ptr [rsp+570h+var_548], eax; int
0x18002179e  mov     rdx, rdi; struct IExtensionContext *
0x1800217a1  lea     rax, [rbp+470h+var_4A8]
0x1800217a5  mov     [rsp+570h+var_550], rax; struct STRU *
0x1800217aa  call    ?PopParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAVSTRU@@HH@Z; APP_OBJECT_UTILS::PopParameter(IExtensionContext *,ICommandParameterList *,ushort const *,STRU *,int,int)
0x1800217af  mov     ebx, eax
0x1800217b1  cmp     eax, 80070585h
0x1800217b6  jnz     short loc_1800217F3
0x1800217b8  lea     r8, aModule_0; "MODULE"
0x1800217bf  mov     ebx, 80070032h
0x1800217c4  mov     [rbp+470h+Arguments], r8
0x1800217c8  mov     edx, ebx
0x1800217ca  mov     r8d, 0C00003EAh
0x1800217d0  mov     rax, [rdi]
0x1800217d3  lea     r9, [rbp+470h+Arguments]
0x1800217d7  mov     rcx, rdi
0x1800217da  mov     dword ptr [rsp+570h+var_550], esi
0x1800217de  mov     [rbp+470h+Arguments+8], r15
0x1800217e2  mov     rax, [rax+90h]
0x1800217e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800217ee  jmp     loc_180021A77
0x1800217f3  test    eax, eax
0x1800217f5  js      loc_180021A77
0x1800217fb  mov     r15, [rbp+470h+var_488]
0x1800217ff  mov     r8, [rsp+570h+var_520]; struct ICommandParameterList *
0x180021804  lea     rax, [rsp+570h+var_518]
0x180021809  mov     dword ptr [rsp+570h+var_540], 1; int
0x180021811  lea     r9, aRemove; "remove"
0x180021818  mov     rdx, rdi; struct IExtensionContext *
0x18002181b  mov     [rsp+570h+var_550], rax; struct INativeConfigurationElement **
0x180021820  call    ?PopBooleanParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAHHH@Z; APP_OBJECT_UTILS::PopBooleanParameter(IExtensionContext *,ICommandParameterList *,ushort const *,int *,int,int)
0x180021825  mov     ecx, 80000000h; this
0x18002182a  mov     ebx, eax
0x18002182c  add     eax, ecx
0x18002182e  test    ecx, eax
0x180021830  jnz     short loc_18002183E
0x180021832  cmp     ebx, 80070585h
0x180021838  jnz     loc_180021A77
0x18002183e  mov     r8, [rsp+570h+var_520]; struct ICommandParameterList *
0x180021843  mov     rdx, rdi; struct IExtensionContext *
0x180021846  call    ?ValidateEmptyParameters@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@@Z; APP_OBJECT_UTILS::ValidateEmptyParameters(IExtensionContext *,ICommandParameterList *)
0x18002184b  mov     ebx, eax
0x18002184d  test    eax, eax
0x18002184f  js      loc_180021A77
0x180021855  lea     r9, [rsp+570h+var_4F8]; struct INativeSectionException **
0x18002185a  mov     rdx, rdi; struct IExtensionContext *
0x18002185d  lea     r8, [rsp+570h+var_508]; struct INativeConfigurationElement **
0x180021862  call    ?GetGlobalModulesConfiguration@MODULE_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEAPEAVINativeConfigurationElement@@PEAPEAVINativeSectionException@@@Z; MODULE_OBJECT_EXTENSION::GetGlobalModulesConfiguration(IExtensionContext *,INativeConfigurationElement * *,INativeSectionException * *)
0x180021867  mov     ebx, eax
0x180021869  test    eax, eax
0x18002186b  jns     short loc_1800218A0
0x18002186d  mov     rcx, [rsp+570h+var_4F8]
0x180021872  test    rcx, rcx
0x180021875  jz      short loc_180021896
0x180021877  mov     rax, [rdi]
0x18002187a  lea     r8, aModule_0; "MODULE"
0x180021881  mov     r9, rcx
0x180021884  mov     dword ptr [rsp+570h+var_550], esi
0x180021888  mov     edx, ebx
0x18002188a  mov     rcx, rdi
0x18002188d  mov     rax, [rax+70h]
0x180021891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021896  mov     r14, [rsp+570h+var_508]
0x18002189b  jmp     loc_180021A77
0x1800218a0  mov     r14, [rsp+570h+var_508]
0x1800218a5  lea     rdx, [rsp+570h+var_510]
0x1800218aa  mov     rcx, r14
0x1800218ad  mov     rax, [r14]
0x1800218b0  mov     rax, [rax+28h]
0x1800218b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218b9  mov     ebx, eax
0x1800218bb  test    eax, eax
0x1800218bd  js      loc_180021A77
0x1800218c3  mov     rdx, [rsp+570h+var_510]; struct INativeConfigurationElementCollection *
0x1800218c8  lea     rax, [rbp+470h+var_4F0]
0x1800218cc  mov     [rsp+570h+var_540], rax; struct INativePropertyException **
0x1800218d1  mov     r9, r15; unsigned __int16 *
0x1800218d4  lea     rax, [rsp+570h+var_518+4]
0x1800218d9  mov     [rsp+570h+var_548], rax; unsigned int *
0x1800218de  call    ?FindCollectionElementByKey@MODULE_OBJECT_EXTENSION@@AEAAJPEAVINativeConfigurationElementCollection@@PEBG1PEAPEAVINativeConfigurationElement@@PEAKPEAPEAVINativePropertyException@@@Z; MODULE_OBJECT_EXTENSION::FindCollectionElementByKey(INativeConfigurationElementCollection *,ushort const *,ushort const *,INativeConfigurationElement * *,ulong *,INativePropertyException * *)
0x1800218e3  mov     edx, 80070490h
0x1800218e8  mov     ebx, eax
0x1800218ea  cmp     eax, edx
0x1800218ec  jnz     short loc_180021904
0x1800218ee  lea     rax, aGlobalModule; "GLOBAL MODULE"
0x1800218f5  mov     r8d, 0C0000419h
0x1800218fb  mov     [rbp+470h+Arguments], rax
0x1800218ff  jmp     loc_1800217D0
0x180021904  test    eax, eax
0x180021906  js      loc_180021A77
0x18002190c  cmp     dword ptr [rsp+570h+var_518], esi
0x180021910  jz      short loc_180021989
0x180021912  mov     rax, [rdi]
0x180021915  lea     rdx, [rsp+570h+var_500]
0x18002191a  mov     rcx, rdi
0x18002191d  mov     rax, [rax+0C0h]
0x180021924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021929  mov     ebx, eax
0x18002192b  test    eax, eax
0x18002192d  js      loc_180021A77
0x180021933  mov     r8, [rsp+570h+var_500]
0x180021938  mov     r9, r15
0x18002193b  mov     rax, [r13+0]
0x18002193f  mov     rcx, r13
0x180021942  mov     rdx, [rbp+470h+var_4E8]
0x180021946  mov     [rsp+570h+var_538], rsi
0x18002194b  mov     [rsp+570h+var_540], r12
0x180021950  mov     rax, [rax+28h]
0x180021954  mov     [rsp+570h+var_548], r8
0x180021959  lea     r8, aDelete_0; "DELETE"
0x180021960  mov     [rsp+570h+var_550], rdi
0x180021965  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002196a  mov     ebx, eax
0x18002196c  cmp     eax, 80070002h
0x180021971  jnz     loc_180021A5C
0x180021977  mov     rax, [rdi]
0x18002197a  mov     rcx, rdi
0x18002197d  mov     rax, [rax+88h]
0x180021984  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021989  xor     r13d, r13d
0x18002198c  mov     rcx, [rsp+570h+var_510]
0x180021991  xor     r8d, r8d
0x180021994  mov     edx, dword ptr [rsp+570h+var_518+4]
0x180021998  mov     rax, [rcx]
0x18002199b  mov     rax, [rax+40h]
0x18002199f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800219a4  mov     ebx, eax
0x1800219a6  test    eax, eax
0x1800219a8  js      loc_180021A77
0x1800219ae  mov     rax, [rdi]
0x1800219b1  lea     r8, [rbp+470h+var_450]
0x1800219b5  mov     r9d, 100h
0x1800219bb  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x1800219c2  mov     rcx, rdi
0x1800219c5  mov     rax, [rax+48h]
0x1800219c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800219ce  mov     ebx, eax
0x1800219d0  test    eax, eax
0x1800219d2  js      loc_180021A77
0x1800219d8  lea     rcx, [rbp+470h+var_4E0]; this
0x1800219dc  call    ?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x1800219e1  mov     rax, [rdi]
0x1800219e4  xor     r8d, r8d
0x1800219e7  mov     rdx, [rbp+470h+var_4C0]
0x1800219eb  mov     rcx, rdi
0x1800219ee  mov     rax, [rax+0D0h]
0x1800219f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800219fa  mov     ebx, eax
0x1800219fc  test    eax, eax
0x1800219fe  js      short loc_180021A77
0x180021a00  mov     ecx, 110h; Size
0x180021a05  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021a0a  test    rax, rax
0x180021a0d  jz      short loc_180021A68
0x180021a0f  mov     rcx, rax; this
0x180021a12  call    ??0STATUS_OBJECT@@QEAA@XZ; STATUS_OBJECT::STATUS_OBJECT(void)
0x180021a17  mov     rsi, rax
0x180021a1a  test    rax, rax
0x180021a1d  jz      short loc_180021A6B
0x180021a1f  lea     r8, [rbp+470h+Arguments]; Arguments
0x180021a23  mov     [rbp+470h+Arguments], r15
0x180021a27  mov     edx, 407h; dwMessageId
0x180021a2c  mov     [rbp+470h+Arguments+8], r13
0x180021a30  mov     rcx, rax; this
0x180021a33  call    ?Create@STATUS_OBJECT@@QEAAJKQEAPEBG@Z; STATUS_OBJECT::Create(ulong,ushort const * * const)
0x180021a38  mov     ebx, eax
0x180021a3a  test    eax, eax
0x180021a3c  js      short loc_180021A77
0x180021a3e  mov     rax, [r12]
0x180021a42  mov     rdx, rsi
0x180021a45  mov     rcx, r12
0x180021a48  mov     rax, [rax+18h]
0x180021a4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a51  mov     ebx, eax
0x180021a53  test    eax, eax
0x180021a55  js      short loc_180021A77
0x180021a57  mov     ebx, r13d
0x180021a5a  jmp     short loc_180021A77
0x180021a5c  xor     r13d, r13d
0x180021a5f  test    eax, eax
0x180021a61  js      short loc_180021A77
0x180021a63  jmp     loc_18002198C
0x180021a68  mov     rsi, r13
0x180021a6b  mov     ebx, 80070008h
0x180021a70  jmp     short loc_180021A77
0x180021a72  mov     ebx, 80070057h
0x180021a77  mov     rcx, [rsp+570h+var_500]
0x180021a7c  xor     edi, edi
0x180021a7e  test    rcx, rcx
0x180021a81  jz      short loc_180021A94
0x180021a83  mov     rax, [rcx]
0x180021a86  mov     rax, [rax+10h]
0x180021a8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a8f  mov     [rsp+570h+var_500], rdi
0x180021a94  mov     rcx, [rsp+570h+var_510]
0x180021a99  test    rcx, rcx
0x180021a9c  jz      short loc_180021AAF
0x180021a9e  mov     rax, [rcx]
0x180021aa1  mov     rax, [rax+10h]
0x180021aa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021aaa  mov     [rsp+570h+var_510], rdi
0x180021aaf  test    r14, r14
0x180021ab2  jz      short loc_180021AC3
0x180021ab4  mov     rax, [r14]
0x180021ab7  mov     rcx, r14
0x180021aba  mov     rax, [rax+10h]
0x180021abe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ac3  mov     rcx, [rbp+470h+var_4F0]
0x180021ac7  test    rcx, rcx
0x180021aca  jz      short loc_180021AD8
0x180021acc  mov     rax, [rcx]
0x180021acf  mov     rax, [rax+10h]
0x180021ad3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ad8  mov     rcx, [rsp+570h+var_4F8]
0x180021add  test    rcx, rcx
0x180021ae0  jz      short loc_180021AEE
0x180021ae2  mov     rax, [rcx]
0x180021ae5  mov     rax, [rax+10h]
0x180021ae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021aee  test    rsi, rsi
0x180021af1  jz      short loc_180021B02
0x180021af3  mov     rax, [rsi]
0x180021af6  mov     rcx, rsi
0x180021af9  mov     rax, [rax+10h]
  ... truncated ...
```
