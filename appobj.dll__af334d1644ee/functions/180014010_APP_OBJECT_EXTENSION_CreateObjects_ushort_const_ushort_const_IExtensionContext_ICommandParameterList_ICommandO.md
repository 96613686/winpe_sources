# APP_OBJECT_EXTENSION::CreateObjects(ushort const *,ushort const *,IExtensionContext *,ICommandParameterList *,ICommandObjectList *)

- ea: `0x180014010`
- end: `0x180014684`
- name: `?CreateObjects@APP_OBJECT_EXTENSION@@UEAAJPEBG0PEAVIExtensionContext@@PEAVICommandParameterList@@PEAVICommandObjectList@@@Z`
- size: `1652`
- prototype: `__int64 __fastcall(APP_OBJECT_EXTENSION *this, const unsigned __int16 *, unsigned __int16 *, struct IExtensionContext *, struct ICommandParameterList *, struct ICommandObjectList *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001044`
- `0x180001fb0`
- `0x1800134b8`
- `0x180013d88`
- `0x180014010`
- `0x180014a40`
- `0x18002b564`
- `0x18002bd3c`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## pseudocode

```c
__int64 __fastcall APP_OBJECT_EXTENSION::CreateObjects(
        APP_OBJECT_EXTENSION *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct IExtensionContext *a4,
        struct ICommandParameterList *a5,
        struct ICommandObjectList *a6)
{
  APP_OBJECT *v8; // rdi
  __int64 v10; // rcx
  int v11; // ebx
  int v12; // eax
  const wchar_t *v13; // r15
  int v14; // eax
  unsigned int v15; // r15d
  APP_OBJECT_EXTENSION *v16; // rcx
  int Application; // eax
  unsigned int v18; // esi
  __int64 v19; // rax
  APP_OBJECT *v20; // rax
  struct ICommandObject *v22; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v23; // [rsp+48h] [rbp-B8h] BYREF
  int v24; // [rsp+4Ch] [rbp-B4h] BYREF
  __int64 v25; // [rsp+50h] [rbp-B0h] BYREF
  struct INativeConfigurationElement *v26; // [rsp+58h] [rbp-A8h] BYREF
  __int64 *v27; // [rsp+60h] [rbp-A0h] BYREF
  struct INativeConfigurationElement *v28; // [rsp+68h] [rbp-98h] BYREF
  struct ICommandParameterList *v29; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v30; // [rsp+78h] [rbp-88h] BYREF
  struct APP_OBJECT *v31; // [rsp+80h] [rbp-80h] BYREF
  __int64 v32; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v33; // [rsp+90h] [rbp-70h] BYREF
  __int128 v34; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v35[32]; // [rsp+A8h] [rbp-58h] BYREF
  const wchar_t *v36; // [rsp+C8h] [rbp-38h]
  int v37; // [rsp+D0h] [rbp-30h]
  __int16 v38; // [rsp+D4h] [rbp-2Ch]
  int v39; // [rsp+D8h] [rbp-28h]
  _BYTE v40[32]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 *v41; // [rsp+100h] [rbp+0h]
  int v42; // [rsp+108h] [rbp+8h]
  __int16 v43; // [rsp+10Ch] [rbp+Ch]
  int v44; // [rsp+110h] [rbp+10h]
  __int16 v45; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v46[510]; // [rsp+122h] [rbp+22h] BYREF
  __int16 v47; // [rsp+320h] [rbp+220h] BYREF
  _BYTE v48[510]; // [rsp+322h] [rbp+222h] BYREF

  v22 = 0;
  v26 = 0;
  v28 = 0;
  v27 = 0;
  v23 = 0;
  v8 = 0;
  v30 = 0;
  v31 = 0;
  v25 = 0;
  v33 = 0;
  v24 = 0;
  memset_0(v46, 0, sizeof(v46));
  v43 = 256;
  v42 = 512;
  v41 = (unsigned __int16 *)&v45;
  v44 = 0;
  v45 = 0;
  memset_0(v48, 0, sizeof(v48));
  v37 = 512;
  v36 = (const wchar_t *)&v47;
  v38 = 256;
  v39 = 0;
  v47 = 0;
  v32 = 0;
  v29 = 0;
  v34 = 0;
  if ( !a2 || !a3 || !a4 || !a5 || !a6 )
  {
    v11 = -2147024809;
    goto LABEL_53;
  }
  v11 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, struct ICommandParameterList **))(*(_QWORD *)a5 + 80LL))(
          a5,
          &v29);
  if ( v11 < 0 )
    goto LABEL_53;
  if ( *a3 )
    goto LABEL_16;
  v12 = APP_OBJECT_UTILS::PopParameter((APP_OBJECT_UTILS *)v10, a4, v29, L"APP.NAME", (struct STRU *)v40, 0, 1);
  v10 = 0x80000000LL;
  v11 = v12;
  if ( (int)(v12 + 0x80000000) >= 0 && v12 != -2147023483 )
    goto LABEL_53;
  a3 = v41;
  if ( *v41 )
  {
LABEL_16:
    v11 = APP_OBJECT_UTILS::ValidateEmptyParameters((APP_OBJECT_UTILS *)v10, a4, v29);
    if ( v11 < 0 )
      goto LABEL_53;
    v13 = a3;
  }
  else
  {
    v11 = APP_OBJECT_UTILS::PopParameter(
            (APP_OBJECT_UTILS *)0x80000000LL,
            a4,
            v29,
            L"SITE.NAME",
            (struct STRU *)v35,
            0,
            1);
    if ( (int)(v11 + 0x80000000) >= 0 && v11 != -2147023483 )
      goto LABEL_53;
    if ( v11 < 0 )
      v13 = &Str;
    else
      v13 = v36;
  }
  v11 = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64 *))(*(_QWORD *)a4 + 184LL))(a4, &v25);
  if ( v11 >= 0 )
  {
    v11 = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64 *))(*(_QWORD *)a4 + 192LL))(a4, &v32);
    if ( v11 >= 0 )
    {
      v14 = (*(__int64 (__fastcall **)(struct IExtensionContext *, const unsigned __int16 *, const wchar_t *, __int64, __int64, int))(*(_QWORD *)a4 + 56LL))(
              a4,
              L"SITE",
              v13,
              v32,
              v25,
              4);
      v15 = 0;
      v11 = v14;
      if ( v14 >= 0 )
      {
        v11 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v25 + 32LL))(v25, &v23);
        if ( v11 >= 0 )
        {
          if ( *a3 )
          {
            if ( v23 > 1 )
            {
              *((_QWORD *)&v34 + 1) = a3;
              *(_QWORD *)&v34 = L"SITE";
              v11 = -2147024846;
              (*(void (__fastcall **)(struct IExtensionContext *, __int64, __int64, __int128 *, _DWORD))(*(_QWORD *)a4 + 144LL))(
                a4,
                2147942450LL,
                3221226516LL,
                &v34,
                0);
              goto LABEL_53;
            }
            if ( v23 )
            {
              v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct ICommandObject **))(*(_QWORD *)v25 + 40LL))(
                      v25,
                      0,
                      &v22);
              if ( v11 >= 0 )
              {
                Application = APP_OBJECT_EXTENSION::FindApplication(v16, a4, v22, a3, &v31);
                v8 = v31;
                v11 = Application;
                if ( Application == -2147024894 )
                  goto LABEL_28;
                if ( Application >= 0 )
                {
                  v11 = (*(__int64 (__fastcall **)(struct ICommandObjectList *, struct APP_OBJECT *))(*(_QWORD *)a6 + 24LL))(
                          a6,
                          v31);
                  if ( v11 >= 0 )
                    goto LABEL_28;
                }
              }
            }
          }
          else
          {
            v18 = 0;
LABEL_33:
            if ( v15 >= v23 )
            {
LABEL_28:
              v11 = 0;
              goto LABEL_53;
            }
            v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct ICommandObject **))(*(_QWORD *)v25 + 40LL))(
                    v25,
                    v15,
                    &v22);
            if ( v11 >= 0 )
            {
              v11 = (*(__int64 (__fastcall **)(struct ICommandObject *, struct INativeConfigurationElement **))(*(_QWORD *)v22 + 48LL))(
                      v22,
                      &v26);
              if ( v11 >= 0 )
              {
                v11 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 **))(*(_QWORD *)v26 + 40LL))(
                        v26,
                        &v27);
                if ( v11 >= 0 )
                {
                  (*(void (__fastcall **)(__int64 *, unsigned int *))(*v27 + 24))(v27, &v30);
                  while ( 1 )
                  {
                    v19 = *v27;
                    if ( v18 >= v30 )
                    {
                      (*(void (**)(void))(v19 + 16))();
                      v18 = 0;
                      v27 = 0;
                      (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v26 + 16LL))(v26);
                      v26 = 0;
                      (*(void (__fastcall **)(struct ICommandObject *))(*(_QWORD *)v22 + 16LL))(v22);
                      ++v15;
                      v22 = 0;
                      goto LABEL_33;
                    }
                    v11 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, struct INativeConfigurationElement **))(v19 + 32))(
                            v27,
                            v18,
                            &v28);
                    if ( v11 < 0 )
                      goto LABEL_53;
                    v20 = (APP_OBJECT *)operator new(0xD8u);
                    if ( !v20 )
                      break;
                    v8 = APP_OBJECT::APP_OBJECT(v20, v28, v26);
                    if ( !v8 )
                      goto LABEL_50;
                    v11 = (*(__int64 (__fastcall **)(struct ICommandObject *, unsigned __int16 **))(*(_QWORD *)v22 + 40LL))(
                            v22,
                            &v33);
                    if ( v11 < 0 )
                      goto LABEL_53;
                    v11 = APP_OBJECT::Create(v8, (const unsigned __int8 *)v33);
                    if ( v11 < 0 )
                      goto LABEL_53;
                    v24 = 0;
                    v11 = (*(__int64 (__fastcall **)(struct IExtensionContext *, APP_OBJECT *, struct ICommandParameterList *, int *))(*(_QWORD *)a4 + 152LL))(
                            a4,
                            v8,
                            a5,
                            &v24);
                    if ( v11 < 0 )
                      goto LABEL_53;
                    if ( v24 )
                    {
                      v11 = (*(__int64 (__fastcall **)(struct ICommandObjectList *, APP_OBJECT *))(*(_QWORD *)a6 + 24LL))(
                              a6,
                              v8);
                      if ( v11 < 0 )
                        goto LABEL_53;
                    }
                    (*(void (__fastcall **)(APP_OBJECT *))(*(_QWORD *)v8 + 16LL))(v8);
                    v8 = 0;
                    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v28 + 16LL))(v28);
                    ++v18;
                    v28 = 0;
                  }
                  v8 = 0;
LABEL_50:
                  v11 = -2147024888;
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_53:
  if ( v28 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v28 + 16LL))(v28);
    v28 = 0;
  }
  if ( v8 )
    (*(void (__fastcall **)(APP_OBJECT *))(*(_QWORD *)v8 + 16LL))(v8);
  if ( v25 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    v25 = 0;
  }
  if ( v22 )
  {
    (*(void (__fastcall **)(struct ICommandObject *))(*(_QWORD *)v22 + 16LL))(v22);
    v22 = 0;
  }
  if ( v26 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v26 + 16LL))(v26);
    v26 = 0;
  }
  if ( v27 )
  {
    (*(void (__fastcall **)(__int64 *))(*v27 + 16))(v27);
    v27 = 0;
  }
  if ( v32 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    v32 = 0;
  }
  if ( v29 )
  {
    (*(void (__fastcall **)(struct ICommandParameterList *))(*(_QWORD *)v29 + 16LL))(v29);
    v29 = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v35);
  BUFFER::~BUFFER((BUFFER *)v40);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180014010  mov     [rsp-8+arg_0], rbx
0x180014015  push    rbp
0x180014016  push    rsi
0x180014017  push    rdi
0x180014018  push    r12
0x18001401a  push    r13
0x18001401c  push    r14
0x18001401e  push    r15
0x180014020  lea     rbp, [rsp-430h]
0x180014028  sub     rsp, 530h
0x18001402f  mov     rax, cs:__security_cookie
0x180014036  xor     rax, rsp
0x180014039  mov     [rbp+460h+var_40], rax
0x180014040  mov     r13, [rbp+460h+arg_20]
0x180014047  lea     rcx, [rbp+460h+var_43E]; void *
0x18001404b  mov     r12, [rbp+460h+arg_28]
0x180014052  xor     eax, eax
0x180014054  mov     rsi, r8
0x180014057  mov     [rsp+560h+var_520], rax
0x18001405c  mov     rbx, rdx
0x18001405f  mov     [rsp+560h+var_508], rax
0x180014064  xor     edx, edx; Val
0x180014066  mov     [rsp+560h+var_4F8], rax
0x18001406b  mov     r8d, 1FEh; Size
0x180014071  mov     [rsp+560h+var_500], rax
0x180014076  mov     [rsp+560h+var_518], eax
0x18001407a  mov     edi, eax
0x18001407c  mov     [rsp+560h+var_4E8], eax
0x180014080  mov     r14, r9
0x180014083  mov     [rbp+460h+var_4E0], rax
0x180014087  mov     [rsp+560h+var_510], rax
0x18001408c  mov     [rbp+460h+var_4D0], rax
0x180014090  mov     [rsp+560h+var_514], eax
0x180014094  call    memset_0
0x180014099  mov     r15d, 200h
0x18001409f  mov     [rbp+460h+var_454], 100h
0x1800140a5  lea     rax, [rbp+460h+var_440]
0x1800140a9  mov     [rbp+460h+var_458], r15d
0x1800140ad  mov     [rbp+460h+var_460], rax
0x1800140b1  lea     rcx, [rbp+460h+var_23E]; void *
0x1800140b8  xor     eax, eax
0x1800140ba  xor     edx, edx; Val
0x1800140bc  lea     r8d, [r15-2]; Size
0x1800140c0  mov     [rbp+460h+var_450], eax
0x1800140c3  mov     [rbp+460h+var_440], ax
0x1800140c7  call    memset_0
0x1800140cc  mov     [rbp+460h+var_490], r15d
0x1800140d0  lea     rax, [rbp+460h+var_240]
0x1800140d7  xor     r15d, r15d
0x1800140da  mov     [rbp+460h+var_498], rax
0x1800140de  mov     [rbp+460h+var_48C], 100h
0x1800140e4  xorps   xmm0, xmm0
0x1800140e7  mov     [rbp+460h+var_488], r15d
0x1800140eb  mov     [rbp+460h+var_240], r15w
0x1800140f3  mov     [rbp+460h+var_4D8], r15
0x1800140f7  mov     [rsp+560h+var_4F0], r15
0x1800140fc  movups  [rbp+460h+var_4C8], xmm0
0x180014100  test    rbx, rbx
0x180014103  jz      loc_180014570
0x180014109  test    rsi, rsi
0x18001410c  jz      loc_180014570
0x180014112  test    r14, r14
0x180014115  jz      loc_180014570
0x18001411b  test    r13, r13
0x18001411e  jz      loc_180014570
0x180014124  test    r12, r12
0x180014127  jz      loc_180014570
0x18001412d  mov     rax, [r13+0]
0x180014131  lea     rdx, [rsp+560h+var_4F0]
0x180014136  mov     rcx, r13
0x180014139  mov     rax, [rax+50h]
0x18001413d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014142  mov     ebx, eax
0x180014144  test    eax, eax
0x180014146  js      loc_180014575
0x18001414c  cmp     [rsi], r15w
0x180014150  jnz     loc_1800141F9
0x180014156  mov     r8, [rsp+560h+var_4F0]; struct ICommandParameterList *
0x18001415b  lea     rax, [rbp+460h+var_480]
0x18001415f  mov     [rsp+560h+var_530], 1; int
0x180014167  lea     r9, aAppName_0; "APP.NAME"
0x18001416e  mov     [rsp+560h+var_538], r15d; int
0x180014173  mov     rdx, r14; struct IExtensionContext *
0x180014176  mov     [rsp+560h+var_540], rax; struct STRU *
0x18001417b  call    ?PopParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAVSTRU@@HH@Z; APP_OBJECT_UTILS::PopParameter(IExtensionContext *,ICommandParameterList *,ushort const *,STRU *,int,int)
0x180014180  mov     ecx, 80000000h; this
0x180014185  mov     ebx, eax
0x180014187  add     eax, ecx
0x180014189  test    ecx, eax
0x18001418b  jnz     short loc_180014199
0x18001418d  cmp     ebx, 80070585h
0x180014193  jnz     loc_180014575
0x180014199  mov     rsi, [rbp+460h+var_460]
0x18001419d  cmp     [rsi], r15w
0x1800141a1  jnz     short loc_1800141F9
0x1800141a3  mov     r8, [rsp+560h+var_4F0]; struct ICommandParameterList *
0x1800141a8  lea     rax, [rbp+460h+var_4B8]
0x1800141ac  mov     [rsp+560h+var_530], 1; int
0x1800141b4  lea     r9, aSiteName; "SITE.NAME"
0x1800141bb  mov     [rsp+560h+var_538], r15d; int
0x1800141c0  mov     rdx, r14; struct IExtensionContext *
0x1800141c3  mov     [rsp+560h+var_540], rax; struct STRU *
0x1800141c8  call    ?PopParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAVSTRU@@HH@Z; APP_OBJECT_UTILS::PopParameter(IExtensionContext *,ICommandParameterList *,ushort const *,STRU *,int,int)
0x1800141cd  mov     ecx, 80000000h
0x1800141d2  mov     ebx, eax
0x1800141d4  add     eax, ecx
0x1800141d6  test    ecx, eax
0x1800141d8  jnz     short loc_1800141E6
0x1800141da  cmp     ebx, 80070585h
0x1800141e0  jnz     loc_180014575
0x1800141e6  test    ebx, ebx
0x1800141e8  js      short loc_1800141F0
0x1800141ea  mov     r15, [rbp+460h+var_498]
0x1800141ee  jmp     short loc_180014213
0x1800141f0  lea     r15, Str
0x1800141f7  jmp     short loc_180014213
0x1800141f9  mov     r8, [rsp+560h+var_4F0]; struct ICommandParameterList *
0x1800141fe  mov     rdx, r14; struct IExtensionContext *
0x180014201  call    ?ValidateEmptyParameters@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@@Z; APP_OBJECT_UTILS::ValidateEmptyParameters(IExtensionContext *,ICommandParameterList *)
0x180014206  mov     ebx, eax
0x180014208  test    eax, eax
0x18001420a  js      loc_180014575
0x180014210  mov     r15, rsi
0x180014213  mov     rax, [r14]
0x180014216  lea     rdx, [rsp+560h+var_510]
0x18001421b  mov     rcx, r14
0x18001421e  mov     rax, [rax+0B8h]
0x180014225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001422a  mov     ebx, eax
0x18001422c  test    eax, eax
0x18001422e  js      loc_180014575
0x180014234  mov     rax, [r14]
0x180014237  lea     rdx, [rbp+460h+var_4D8]
0x18001423b  mov     rcx, r14
0x18001423e  mov     rax, [rax+0C0h]
0x180014245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001424a  mov     ebx, eax
0x18001424c  test    eax, eax
0x18001424e  js      loc_180014575
0x180014254  mov     rcx, [rsp+560h+var_510]
0x180014259  lea     rdx, aSite_0; "SITE"
0x180014260  mov     rax, [r14]
0x180014263  mov     r8, r15
0x180014266  mov     r9, [rbp+460h+var_4D8]
0x18001426a  mov     [rsp+560h+var_538], 4
0x180014272  mov     [rsp+560h+var_540], rcx
0x180014277  mov     rcx, r14
0x18001427a  mov     rax, [rax+38h]
0x18001427e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014283  xor     r15d, r15d
0x180014286  mov     ebx, eax
0x180014288  test    eax, eax
0x18001428a  js      loc_180014575
0x180014290  mov     rcx, [rsp+560h+var_510]
0x180014295  lea     rdx, [rsp+560h+var_518]
0x18001429a  mov     rax, [rcx]
0x18001429d  mov     rax, [rax+20h]
0x1800142a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142a6  mov     ebx, eax
0x1800142a8  test    eax, eax
0x1800142aa  js      loc_180014575
0x1800142b0  cmp     [rsi], r15w
0x1800142b4  jz      loc_18001437E
0x1800142ba  mov     eax, [rsp+560h+var_518]
0x1800142be  cmp     eax, 1
0x1800142c1  jbe     short loc_1800142FF
0x1800142c3  lea     rax, aSite_0; "SITE"
0x1800142ca  mov     qword ptr [rbp+460h+var_4C8+8], rsi
0x1800142ce  mov     qword ptr [rbp+460h+var_4C8], rax
0x1800142d2  lea     r9, [rbp+460h+var_4C8]
0x1800142d6  mov     rax, [r14]
0x1800142d9  mov     ebx, 80070032h
0x1800142de  mov     r8d, 0C0000414h
0x1800142e4  mov     dword ptr [rsp+560h+var_540], r15d
0x1800142e9  mov     edx, ebx
0x1800142eb  mov     rcx, r14
0x1800142ee  mov     rax, [rax+90h]
0x1800142f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142fa  jmp     loc_180014575
0x1800142ff  test    eax, eax
0x180014301  jz      loc_180014575
0x180014307  mov     rcx, [rsp+560h+var_510]
0x18001430c  lea     r8, [rsp+560h+var_520]
0x180014311  xor     edx, edx
0x180014313  mov     rax, [rcx]
0x180014316  mov     rax, [rax+28h]
0x18001431a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001431f  mov     ebx, eax
0x180014321  test    eax, eax
0x180014323  js      loc_180014575
0x180014329  mov     r8, [rsp+560h+var_520]; struct ICommandObject *
0x18001432e  lea     rax, [rbp+460h+var_4E0]
0x180014332  mov     r9, rsi; unsigned __int16 *
0x180014335  mov     [rsp+560h+var_540], rax; struct APP_OBJECT **
0x18001433a  mov     rdx, r14; struct IExtensionContext *
0x18001433d  call    ?FindApplication@APP_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEAVICommandObject@@PEBGPEAPEAVAPP_OBJECT@@@Z; APP_OBJECT_EXTENSION::FindApplication(IExtensionContext *,ICommandObject *,ushort const *,APP_OBJECT * *)
0x180014342  mov     rdi, [rbp+460h+var_4E0]
0x180014346  mov     ebx, eax
0x180014348  cmp     eax, 80070002h
0x18001434d  jnz     short loc_180014357
0x18001434f  mov     ebx, r15d
0x180014352  jmp     loc_180014575
0x180014357  test    eax, eax
0x180014359  js      loc_180014575
0x18001435f  mov     rax, [r12]
0x180014363  mov     rdx, rdi
0x180014366  mov     rcx, r12
0x180014369  mov     rax, [rax+18h]
0x18001436d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014372  mov     ebx, eax
0x180014374  test    eax, eax
0x180014376  js      loc_180014575
0x18001437c  jmp     short loc_18001434F
0x18001437e  xor     esi, esi
0x180014380  cmp     r15d, [rsp+560h+var_518]
0x180014385  jnb     loc_180014568
0x18001438b  mov     rcx, [rsp+560h+var_510]
0x180014390  lea     r8, [rsp+560h+var_520]
0x180014395  mov     edx, r15d
0x180014398  mov     rax, [rcx]
0x18001439b  mov     rax, [rax+28h]
0x18001439f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143a4  mov     ebx, eax
0x1800143a6  test    eax, eax
0x1800143a8  js      loc_180014575
0x1800143ae  mov     rcx, [rsp+560h+var_520]
0x1800143b3  lea     rdx, [rsp+560h+var_508]
0x1800143b8  mov     rax, [rcx]
0x1800143bb  mov     rax, [rax+30h]
0x1800143bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143c4  mov     ebx, eax
0x1800143c6  test    eax, eax
0x1800143c8  js      loc_180014575
0x1800143ce  mov     rcx, [rsp+560h+var_508]
0x1800143d3  lea     rdx, [rsp+560h+var_500]
0x1800143d8  mov     rax, [rcx]
0x1800143db  mov     rax, [rax+28h]
0x1800143df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143e4  mov     ebx, eax
0x1800143e6  test    eax, eax
0x1800143e8  js      loc_180014575
0x1800143ee  mov     rcx, [rsp+560h+var_500]
0x1800143f3  lea     rdx, [rsp+560h+var_4E8]
0x1800143f8  mov     rax, [rcx]
0x1800143fb  mov     rax, [rax+18h]
0x1800143ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014404  mov     rcx, [rsp+560h+var_500]
0x180014409  mov     rax, [rcx]
0x18001440c  cmp     esi, [rsp+560h+var_4E8]
0x180014410  jnb     loc_18001451A
0x180014416  mov     rax, [rax+20h]
0x18001441a  lea     r8, [rsp+560h+var_4F8]
0x18001441f  mov     edx, esi
0x180014421  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014426  mov     ebx, eax
0x180014428  test    eax, eax
0x18001442a  js      loc_180014575
0x180014430  mov     ecx, 0D8h; Size
0x180014435  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001443a  xor     ebx, ebx
0x18001443c  test    rax, rax
0x18001443f  jz      loc_18001455E
0x180014445  mov     r8, [rsp+560h+var_508]; struct INativeConfigurationElement *
0x18001444a  mov     rcx, rax; this
0x18001444d  mov     rdx, [rsp+560h+var_4F8]; struct INativeConfigurationElement *
0x180014452  call    ??0APP_OBJECT@@QEAA@PEAVINativeConfigurationElement@@0@Z; APP_OBJECT::APP_OBJECT(INativeConfigurationElement *,INativeConfigurationElement *)
0x180014457  mov     rdi, rax
0x18001445a  test    rax, rax
0x18001445d  jz      loc_180014561
0x180014463  mov     rcx, [rsp+560h+var_520]
0x180014468  lea     rdx, [rbp+460h+var_4D0]
0x18001446c  mov     rax, [rcx]
0x18001446f  mov     rax, [rax+28h]
0x180014473  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014478  mov     ebx, eax
0x18001447a  test    eax, eax
0x18001447c  js      loc_180014575
0x180014482  mov     rdx, [rbp+460h+var_4D0]; unsigned __int16 *
0x180014486  mov     rcx, rdi; this
0x180014489  call    ?Create@APP_OBJECT@@QEAAJPEBG@Z; APP_OBJECT::Create(ushort const *)
0x18001448e  mov     ebx, eax
0x180014490  xor     eax, eax
0x180014492  test    ebx, ebx
0x180014494  js      loc_180014575
0x18001449a  mov     [rsp+560h+var_514], eax
0x18001449e  lea     r9, [rsp+560h+var_514]
0x1800144a3  mov     rax, [r14]
0x1800144a6  mov     r8, r13
0x1800144a9  mov     rdx, rdi
0x1800144ac  mov     rcx, r14
0x1800144af  mov     rax, [rax+98h]
0x1800144b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144bb  mov     ebx, eax
0x1800144bd  xor     eax, eax
0x1800144bf  test    ebx, ebx
0x1800144c1  js      loc_180014575
0x1800144c7  cmp     [rsp+560h+var_514], eax
0x1800144cb  jz      short loc_1800144EA
0x1800144cd  mov     rax, [r12]
0x1800144d1  mov     rdx, rdi
  ... truncated ...
```
