# VDIR_OBJECT_EXTENSION::CreateObjects(ushort const *,ushort const *,IExtensionContext *,ICommandParameterList *,ICommandObjectList *)

- ea: `0x180015ab0`
- end: `0x1800161ed`
- name: `?CreateObjects@VDIR_OBJECT_EXTENSION@@UEAAJPEBG0PEAVIExtensionContext@@PEAVICommandParameterList@@PEAVICommandObjectList@@@Z`
- size: `1853`
- prototype: `__int64 __fastcall(VDIR_OBJECT_EXTENSION *this, const unsigned __int16 *, unsigned __int16 *, struct IExtensionContext *, struct ICommandParameterList *, struct ICommandObjectList *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001044`
- `0x180001fb0`
- `0x18001534c`
- `0x180015844`
- `0x180015ab0`
- `0x1800165d8`
- `0x18002b564`
- `0x18002bd3c`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## pseudocode

```c
__int64 __fastcall VDIR_OBJECT_EXTENSION::CreateObjects(
        VDIR_OBJECT_EXTENSION *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct IExtensionContext *a4,
        struct ICommandParameterList *a5,
        struct ICommandObjectList *a6)
{
  VDIR_OBJECT *v8; // rdi
  unsigned int v10; // r15d
  __int64 v11; // rcx
  int DirElement; // ebx
  int v13; // eax
  int v14; // eax
  unsigned int i; // r12d
  __int64 v16; // rax
  VDIR_OBJECT *v17; // rax
  __int64 v18; // rax
  VDIR_OBJECT_EXTENSION *v19; // rcx
  VDIR_OBJECT *v20; // rax
  struct INativeConfigurationElement *v22; // [rsp+40h] [rbp-C0h] BYREF
  struct INativeConfigurationElement *v23; // [rsp+48h] [rbp-B8h] BYREF
  __int64 *v24; // [rsp+50h] [rbp-B0h] BYREF
  struct INativeConfigurationElementCollection *v25; // [rsp+58h] [rbp-A8h] BYREF
  int v26; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v27; // [rsp+68h] [rbp-98h] BYREF
  struct ICommandParameterList *v28; // [rsp+70h] [rbp-90h] BYREF
  __int64 v29; // [rsp+78h] [rbp-88h] BYREF
  __int64 v30; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v31; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v32; // [rsp+8Ch] [rbp-74h] BYREF
  unsigned __int16 *v33; // [rsp+90h] [rbp-70h] BYREF
  __int64 v34; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v35[32]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v36; // [rsp+C0h] [rbp-40h]
  int v37; // [rsp+C8h] [rbp-38h]
  __int16 v38; // [rsp+CCh] [rbp-34h]
  int v39; // [rsp+D0h] [rbp-30h]
  _BYTE v40[32]; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int16 *v41; // [rsp+F8h] [rbp-8h]
  int v42; // [rsp+100h] [rbp+0h]
  __int16 v43; // [rsp+104h] [rbp+4h]
  int v44; // [rsp+108h] [rbp+8h]
  __int16 v45; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v46[510]; // [rsp+112h] [rbp+12h] BYREF
  __int16 v47; // [rsp+310h] [rbp+210h] BYREF
  _BYTE v48[510]; // [rsp+312h] [rbp+212h] BYREF

  v29 = 0;
  v22 = 0;
  v23 = 0;
  v25 = 0;
  v32 = 0;
  v8 = 0;
  v31 = 0;
  v24 = 0;
  v30 = 0;
  v27 = 0;
  v33 = 0;
  v26 = 0;
  memset_0(v46, 0, sizeof(v46));
  v43 = 256;
  v42 = 512;
  v41 = (unsigned __int16 *)&v45;
  v44 = 0;
  v45 = 0;
  memset_0(v48, 0, sizeof(v48));
  v37 = 512;
  v38 = 256;
  v36 = (unsigned __int16 *)&v47;
  v39 = 0;
  v47 = 0;
  v34 = 0;
  v28 = 0;
  if ( !a2 || !a3 || !a4 || !a5 || !a6 )
  {
    DirElement = -2147024809;
    goto LABEL_55;
  }
  v10 = 0;
  DirElement = (*(__int64 (__fastcall **)(struct ICommandParameterList *, struct ICommandParameterList **))(*(_QWORD *)a5 + 80LL))(
                 a5,
                 &v28);
  if ( DirElement < 0 )
    goto LABEL_55;
  if ( *a3 )
    goto LABEL_15;
  v13 = APP_OBJECT_UTILS::PopParameter((APP_OBJECT_UTILS *)v11, a4, v28, L"VDIR.NAME", (struct STRU *)v40, 0, 1);
  v11 = 0x80000000LL;
  DirElement = v13;
  if ( (int)(v13 + 0x80000000) >= 0 && v13 != -2147023483 )
    goto LABEL_55;
  a3 = v41;
  if ( *v41 )
  {
LABEL_15:
    DirElement = APP_OBJECT_UTILS::ValidateEmptyParameters((APP_OBJECT_UTILS *)v11, a4, v28);
    if ( DirElement < 0 )
      goto LABEL_55;
    v27 = a3;
  }
  else
  {
    v27 = (unsigned __int16 *)&Str;
    v14 = APP_OBJECT_UTILS::PopParameter(
            (APP_OBJECT_UTILS *)0x80000000LL,
            a4,
            v28,
            L"APP.NAME",
            (struct STRU *)v35,
            0,
            1);
    DirElement = v14;
    if ( v14 < 0 )
    {
      if ( v14 != -2147023483 )
        goto LABEL_55;
    }
    else
    {
      v27 = v36;
    }
  }
  DirElement = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64 *))(*(_QWORD *)a4 + 184LL))(a4, &v30);
  if ( DirElement >= 0 )
  {
    DirElement = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64 *))(*(_QWORD *)a4 + 192LL))(a4, &v34);
    if ( DirElement >= 0 )
    {
      DirElement = (*(__int64 (__fastcall **)(struct IExtensionContext *, const unsigned __int16 *, unsigned __int16 *, __int64, __int64, _DWORD))(*(_QWORD *)a4 + 56LL))(
                     a4,
                     L"APP",
                     v27,
                     v34,
                     v30,
                     0);
      if ( DirElement >= 0 )
      {
        (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v30 + 32LL))(v30, &v31);
        for ( i = 0; ; ++i )
        {
          v8 = 0;
          if ( i >= v31 )
            break;
          DirElement = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 **))(*(_QWORD *)v30 + 40LL))(v30, i, &v24);
          if ( DirElement < 0 )
            break;
          DirElement = (*(__int64 (__fastcall **)(__int64 *, const unsigned __int16 *, unsigned __int16 **))(*v24 + 80))(
                         v24,
                         L"APP.NAME",
                         &v27);
          if ( DirElement < 0 )
            break;
          v16 = *v24;
          if ( !*a3 )
          {
            DirElement = (*(__int64 (__fastcall **)(__int64 *, struct INativeConfigurationElement **))(v16 + 48))(
                           v24,
                           &v22);
            if ( DirElement >= 0 )
            {
              DirElement = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, struct INativeConfigurationElementCollection **))(*(_QWORD *)v22 + 40LL))(
                             v22,
                             &v25);
              if ( DirElement >= 0 )
              {
                (*(void (__fastcall **)(struct INativeConfigurationElementCollection *, unsigned int *))(*(_QWORD *)v25 + 24LL))(
                  v25,
                  &v32);
                while ( 1 )
                {
                  if ( v10 >= v32 )
                  {
                    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v22 + 16LL))(v22);
                    v10 = 0;
                    v22 = 0;
                    goto LABEL_50;
                  }
                  DirElement = (*(__int64 (__fastcall **)(struct INativeConfigurationElementCollection *, _QWORD, struct INativeConfigurationElement **))(*(_QWORD *)v25 + 32LL))(
                                 v25,
                                 v10,
                                 &v23);
                  if ( DirElement < 0 )
                    break;
                  v17 = (VDIR_OBJECT *)operator new(0xD8u);
                  if ( !v17 )
                  {
                    v8 = 0;
                    goto LABEL_52;
                  }
                  v8 = VDIR_OBJECT::VDIR_OBJECT(v17, v23, v22);
                  if ( !v8 )
                    goto LABEL_52;
                  DirElement = (*(__int64 (__fastcall **)(__int64 *, unsigned __int16 **))(*v24 + 40))(v24, &v33);
                  if ( DirElement < 0 )
                    goto LABEL_55;
                  DirElement = VDIR_OBJECT::Create(v8, (const unsigned __int8 *)v27, (const unsigned __int8 *)v33);
                  if ( DirElement < 0 )
                    goto LABEL_55;
                  v18 = *(_QWORD *)a4;
                  v26 = 0;
                  DirElement = (*(__int64 (__fastcall **)(struct IExtensionContext *, VDIR_OBJECT *, struct ICommandParameterList *, int *))(v18 + 152))(
                                 a4,
                                 v8,
                                 v28,
                                 &v26);
                  if ( DirElement < 0 )
                    goto LABEL_55;
                  if ( v26 )
                  {
                    DirElement = (*(__int64 (__fastcall **)(struct ICommandObjectList *, VDIR_OBJECT *))(*(_QWORD *)a6 + 24LL))(
                                   a6,
                                   v8);
                    if ( DirElement < 0 )
                      goto LABEL_55;
                  }
                  (*(void (__fastcall **)(VDIR_OBJECT *))(*(_QWORD *)v8 + 16LL))(v8);
                  (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v23 + 16LL))(v23);
                  ++v10;
                  v23 = 0;
                }
                v8 = 0;
              }
            }
            break;
          }
          DirElement = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v16 + 56))(v24, &v29);
          if ( DirElement < 0 )
            break;
          DirElement = (*(__int64 (__fastcall **)(__int64, struct INativeConfigurationElementCollection **))(*(_QWORD *)v29 + 40LL))(
                         v29,
                         &v25);
          if ( DirElement < 0 )
            break;
          DirElement = VDIR_OBJECT_EXTENSION::FindDirElement(v19, v25, a3, &v22, &v23);
          if ( DirElement < 0 )
            break;
          if ( v23 )
          {
            v20 = (VDIR_OBJECT *)operator new(0xD8u);
            if ( !v20 || (v8 = VDIR_OBJECT::VDIR_OBJECT(v20, v23, v22)) == 0 )
            {
LABEL_52:
              DirElement = -2147024888;
              break;
            }
            DirElement = (*(__int64 (__fastcall **)(__int64 *, unsigned __int16 **))(*v24 + 40))(v24, &v33);
            if ( DirElement < 0 )
              break;
            DirElement = VDIR_OBJECT::Create(v8, (const unsigned __int8 *)v27, (const unsigned __int8 *)v33);
            if ( DirElement < 0 )
              break;
            DirElement = (*(__int64 (__fastcall **)(struct ICommandObjectList *, VDIR_OBJECT *))(*(_QWORD *)a6 + 24LL))(
                           a6,
                           v8);
            if ( DirElement < 0 )
              break;
            (*(void (__fastcall **)(VDIR_OBJECT *))(*(_QWORD *)v8 + 16LL))(v8);
            (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v23 + 16LL))(v23);
            v23 = 0;
            (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v22 + 16LL))(v22);
            v22 = 0;
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
          v29 = 0;
LABEL_50:
          (*(void (__fastcall **)(struct INativeConfigurationElementCollection *))(*(_QWORD *)v25 + 16LL))(v25);
          v25 = 0;
          (*(void (__fastcall **)(__int64 *))(*v24 + 16))(v24);
          v24 = 0;
        }
      }
    }
  }
LABEL_55:
  if ( v29 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    v29 = 0;
  }
  if ( v22 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v22 + 16LL))(v22);
    v22 = 0;
  }
  if ( v24 )
  {
    (*(void (__fastcall **)(__int64 *))(*v24 + 16))(v24);
    v24 = 0;
  }
  if ( v30 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    v30 = 0;
  }
  if ( v8 )
    (*(void (__fastcall **)(VDIR_OBJECT *))(*(_QWORD *)v8 + 16LL))(v8);
  if ( v23 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v23 + 16LL))(v23);
    v23 = 0;
  }
  if ( v25 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElementCollection *))(*(_QWORD *)v25 + 16LL))(v25);
    v25 = 0;
  }
  if ( v34 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    v34 = 0;
  }
  if ( v28 )
  {
    (*(void (__fastcall **)(struct ICommandParameterList *))(*(_QWORD *)v28 + 16LL))(v28);
    v28 = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v35);
  BUFFER::~BUFFER((BUFFER *)v40);
  return (unsigned int)DirElement;
}

```

## disassembly

```asm
0x180015ab0  mov     [rsp-8+arg_0], rbx
0x180015ab5  push    rbp
0x180015ab6  push    rsi
0x180015ab7  push    rdi
0x180015ab8  push    r12
0x180015aba  push    r13
0x180015abc  push    r14
0x180015abe  push    r15
0x180015ac0  lea     rbp, [rsp-420h]
0x180015ac8  sub     rsp, 520h
0x180015acf  mov     rax, cs:__security_cookie
0x180015ad6  xor     rax, rsp
0x180015ad9  mov     [rbp+450h+var_40], rax
0x180015ae0  mov     r15, [rbp+450h+arg_20]
0x180015ae7  lea     rcx, [rbp+450h+var_43E]; void *
0x180015aeb  mov     r13, [rbp+450h+arg_28]
0x180015af2  xor     eax, eax
0x180015af4  mov     rsi, r8
0x180015af7  mov     [rsp+550h+var_4D8], rax
0x180015afc  mov     rbx, rdx
0x180015aff  mov     [rsp+550h+var_510], rax
0x180015b04  xor     edx, edx; Val
0x180015b06  mov     [rsp+550h+var_508], rax
0x180015b0b  mov     r8d, 1FEh; Size
0x180015b11  mov     [rsp+550h+var_4F8], rax
0x180015b16  mov     [rbp+450h+var_4C4], eax
0x180015b19  mov     edi, eax
0x180015b1b  mov     [rbp+450h+var_4C8], eax
0x180015b1e  mov     r14, r9
0x180015b21  mov     [rsp+550h+var_500], rax
0x180015b26  mov     [rbp+450h+var_4D0], rax
0x180015b2a  mov     [rsp+550h+var_4E8], rax
0x180015b2f  mov     [rbp+450h+var_4C0], rax
0x180015b33  mov     [rsp+550h+var_4F0], eax
0x180015b37  call    memset_0
0x180015b3c  mov     r12d, 200h
0x180015b42  mov     [rbp+450h+var_44C], 100h
0x180015b48  lea     rax, [rbp+450h+var_440]
0x180015b4c  mov     [rbp+450h+var_450], r12d
0x180015b50  mov     [rbp+450h+var_458], rax
0x180015b54  lea     rcx, [rbp+450h+var_23E]; void *
0x180015b5b  xor     eax, eax
0x180015b5d  xor     edx, edx; Val
0x180015b5f  lea     r8d, [r12-2]; Size
0x180015b64  mov     [rbp+450h+var_448], eax
0x180015b67  mov     [rbp+450h+var_440], ax
0x180015b6b  call    memset_0
0x180015b70  xor     ecx, ecx
0x180015b72  mov     [rbp+450h+var_488], r12d
0x180015b76  mov     [rbp+450h+var_484], 100h
0x180015b7c  lea     rax, [rbp+450h+var_240]
0x180015b83  mov     [rbp+450h+var_490], rax
0x180015b87  mov     [rbp+450h+var_480], ecx
0x180015b8a  mov     [rbp+450h+var_240], cx
0x180015b91  mov     [rbp+450h+var_4B8], rcx
0x180015b95  mov     [rsp+550h+var_4E0], rcx
0x180015b9a  test    rbx, rbx
0x180015b9d  jz      loc_1800160BF
0x180015ba3  test    rsi, rsi
0x180015ba6  jz      loc_1800160BF
0x180015bac  test    r14, r14
0x180015baf  jz      loc_1800160BF
0x180015bb5  test    r15, r15
0x180015bb8  jz      loc_1800160BF
0x180015bbe  test    r13, r13
0x180015bc1  jz      loc_1800160BF
0x180015bc7  mov     rax, [r15]
0x180015bca  lea     rdx, [rsp+550h+var_4E0]
0x180015bcf  mov     rcx, r15
0x180015bd2  mov     rax, [rax+50h]
0x180015bd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015bdb  xor     r15d, r15d
0x180015bde  mov     ebx, eax
0x180015be0  test    eax, eax
0x180015be2  js      loc_1800160C7
0x180015be8  cmp     [rsi], r15w
0x180015bec  jnz     loc_180015C94
0x180015bf2  mov     r8, [rsp+550h+var_4E0]; struct ICommandParameterList *
0x180015bf7  lea     rax, [rbp+450h+var_478]
0x180015bfb  mov     [rsp+550h+var_520], 1; int
0x180015c03  lea     r9, aVdirName; "VDIR.NAME"
0x180015c0a  mov     [rsp+550h+var_528], r15d; int
0x180015c0f  mov     rdx, r14; struct IExtensionContext *
0x180015c12  mov     [rsp+550h+var_530], rax; struct STRU *
0x180015c17  call    ?PopParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAVSTRU@@HH@Z; APP_OBJECT_UTILS::PopParameter(IExtensionContext *,ICommandParameterList *,ushort const *,STRU *,int,int)
0x180015c1c  mov     ecx, 80000000h; this
0x180015c21  mov     ebx, eax
0x180015c23  add     eax, ecx
0x180015c25  mov     r12d, 80070585h
0x180015c2b  test    ecx, eax
0x180015c2d  jnz     short loc_180015C38
0x180015c2f  cmp     ebx, r12d
0x180015c32  jnz     loc_1800160C7
0x180015c38  mov     rsi, [rbp+450h+var_458]
0x180015c3c  cmp     [rsi], r15w
0x180015c40  jnz     short loc_180015C94
0x180015c42  mov     r8, [rsp+550h+var_4E0]; struct ICommandParameterList *
0x180015c47  lea     rax, Str
0x180015c4e  mov     [rsp+550h+var_4E8], rax
0x180015c53  lea     r9, aAppName_0; "APP.NAME"
0x180015c5a  lea     rax, [rbp+450h+var_4B0]
0x180015c5e  mov     [rsp+550h+var_520], 1; int
0x180015c66  mov     [rsp+550h+var_528], r15d; int
0x180015c6b  mov     rdx, r14; struct IExtensionContext *
0x180015c6e  mov     [rsp+550h+var_530], rax; struct STRU *
0x180015c73  call    ?PopParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAVSTRU@@HH@Z; APP_OBJECT_UTILS::PopParameter(IExtensionContext *,ICommandParameterList *,ushort const *,STRU *,int,int)
0x180015c78  mov     ebx, eax
0x180015c7a  test    eax, eax
0x180015c7c  js      short loc_180015C89
0x180015c7e  mov     rax, [rbp+450h+var_490]
0x180015c82  mov     [rsp+550h+var_4E8], rax
0x180015c87  jmp     short loc_180015CB0
0x180015c89  cmp     eax, r12d
0x180015c8c  jnz     loc_1800160C7
0x180015c92  jmp     short loc_180015CB0
0x180015c94  mov     r8, [rsp+550h+var_4E0]; struct ICommandParameterList *
0x180015c99  mov     rdx, r14; struct IExtensionContext *
0x180015c9c  call    ?ValidateEmptyParameters@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@@Z; APP_OBJECT_UTILS::ValidateEmptyParameters(IExtensionContext *,ICommandParameterList *)
0x180015ca1  mov     ebx, eax
0x180015ca3  test    eax, eax
0x180015ca5  js      loc_1800160C7
0x180015cab  mov     [rsp+550h+var_4E8], rsi
0x180015cb0  mov     rax, [r14]
0x180015cb3  lea     rdx, [rbp+450h+var_4D0]
0x180015cb7  mov     rcx, r14
0x180015cba  mov     rax, [rax+0B8h]
0x180015cc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015cc6  mov     ebx, eax
0x180015cc8  test    eax, eax
0x180015cca  js      loc_1800160C7
0x180015cd0  mov     rax, [r14]
0x180015cd3  lea     rdx, [rbp+450h+var_4B8]
0x180015cd7  mov     rcx, r14
0x180015cda  mov     rax, [rax+0C0h]
0x180015ce1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ce6  mov     ebx, eax
0x180015ce8  test    eax, eax
0x180015cea  js      loc_1800160C7
0x180015cf0  mov     rcx, [rbp+450h+var_4D0]
0x180015cf4  lea     rdx, aApp_0; "APP"
0x180015cfb  mov     rax, [r14]
0x180015cfe  mov     r9, [rbp+450h+var_4B8]
0x180015d02  mov     r8, [rsp+550h+var_4E8]
0x180015d07  mov     [rsp+550h+var_528], r15d
0x180015d0c  mov     rax, [rax+38h]
0x180015d10  mov     [rsp+550h+var_530], rcx
0x180015d15  mov     rcx, r14
0x180015d18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d1d  mov     ebx, eax
0x180015d1f  test    eax, eax
0x180015d21  js      loc_1800160C7
0x180015d27  mov     rcx, [rbp+450h+var_4D0]
0x180015d2b  lea     rdx, [rbp+450h+var_4C8]
0x180015d2f  mov     rax, [rcx]
0x180015d32  mov     rax, [rax+20h]
0x180015d36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d3b  mov     r12d, r15d
0x180015d3e  mov     rdi, r15
0x180015d41  cmp     r12d, [rbp+450h+var_4C8]
0x180015d45  jnb     loc_1800160C7
0x180015d4b  mov     rcx, [rbp+450h+var_4D0]
0x180015d4f  lea     r8, [rsp+550h+var_500]
0x180015d54  mov     edx, r12d
0x180015d57  mov     rax, [rcx]
0x180015d5a  mov     rax, [rax+28h]
0x180015d5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d63  mov     ebx, eax
0x180015d65  test    eax, eax
0x180015d67  js      loc_1800160C7
0x180015d6d  mov     rcx, [rsp+550h+var_500]
0x180015d72  lea     r8, [rsp+550h+var_4E8]
0x180015d77  lea     rdx, aAppName_0; "APP.NAME"
0x180015d7e  mov     rax, [rcx]
0x180015d81  mov     rax, [rax+50h]
0x180015d85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d8a  mov     ebx, eax
0x180015d8c  test    eax, eax
0x180015d8e  js      loc_1800160C7
0x180015d94  mov     rcx, [rsp+550h+var_500]
0x180015d99  mov     rax, [rcx]
0x180015d9c  cmp     [rsi], r15w
0x180015da0  jnz     loc_180015F2F
0x180015da6  mov     rax, [rax+30h]
0x180015daa  lea     rdx, [rsp+550h+var_510]
0x180015daf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015db4  mov     ebx, eax
0x180015db6  test    eax, eax
0x180015db8  js      loc_1800160C7
0x180015dbe  mov     rcx, [rsp+550h+var_510]
0x180015dc3  lea     rdx, [rsp+550h+var_4F8]
0x180015dc8  mov     rax, [rcx]
0x180015dcb  mov     rax, [rax+28h]
0x180015dcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015dd4  mov     ebx, eax
0x180015dd6  test    eax, eax
0x180015dd8  js      loc_1800160C7
0x180015dde  mov     rcx, [rsp+550h+var_4F8]
0x180015de3  lea     rdx, [rbp+450h+var_4C4]
0x180015de7  mov     rax, [rcx]
0x180015dea  mov     rax, [rax+18h]
0x180015dee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015df3  cmp     r15d, [rbp+450h+var_4C4]
0x180015df7  jnb     loc_180015F11
0x180015dfd  mov     rcx, [rsp+550h+var_4F8]
0x180015e02  lea     r8, [rsp+550h+var_508]
0x180015e07  mov     edx, r15d
0x180015e0a  mov     rax, [rcx]
0x180015e0d  mov     rax, [rax+20h]
0x180015e11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e16  mov     ebx, eax
0x180015e18  test    eax, eax
0x180015e1a  js      loc_1800160B7
0x180015e20  mov     ecx, 0D8h; Size
0x180015e25  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180015e2a  test    rax, rax
0x180015e2d  jz      loc_1800160A5
0x180015e33  mov     r8, [rsp+550h+var_510]; struct INativeConfigurationElement *
0x180015e38  mov     rcx, rax; this
0x180015e3b  mov     rdx, [rsp+550h+var_508]; struct INativeConfigurationElement *
0x180015e40  call    ??0VDIR_OBJECT@@QEAA@PEAVINativeConfigurationElement@@0@Z; VDIR_OBJECT::VDIR_OBJECT(INativeConfigurationElement *,INativeConfigurationElement *)
0x180015e45  mov     rdi, rax
0x180015e48  test    rax, rax
0x180015e4b  jz      loc_1800160AD
0x180015e51  mov     rcx, [rsp+550h+var_500]
0x180015e56  lea     rdx, [rbp+450h+var_4C0]
0x180015e5a  mov     rax, [rcx]
0x180015e5d  mov     rax, [rax+28h]
0x180015e61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e66  mov     ebx, eax
0x180015e68  test    eax, eax
0x180015e6a  js      loc_1800160C4
0x180015e70  mov     r8, [rbp+450h+var_4C0]; unsigned __int16 *
0x180015e74  mov     rcx, rdi; this
0x180015e77  mov     rdx, [rsp+550h+var_4E8]; unsigned __int16 *
0x180015e7c  call    ?Create@VDIR_OBJECT@@QEAAJPEBG0@Z; VDIR_OBJECT::Create(ushort const *,ushort const *)
0x180015e81  mov     ebx, eax
0x180015e83  test    eax, eax
0x180015e85  js      loc_1800160C4
0x180015e8b  mov     rax, [r14]
0x180015e8e  lea     r9, [rsp+550h+var_4F0]
0x180015e93  mov     r8, [rsp+550h+var_4E0]
0x180015e98  mov     rdx, rdi
0x180015e9b  mov     rcx, r14
0x180015e9e  mov     [rsp+550h+var_4F0], 0
0x180015ea6  mov     rax, [rax+98h]
0x180015ead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015eb2  mov     ebx, eax
0x180015eb4  test    eax, eax
0x180015eb6  js      loc_1800160C4
0x180015ebc  cmp     [rsp+550h+var_4F0], 0
0x180015ec1  jz      short loc_180015EE0
0x180015ec3  mov     rax, [r13+0]
0x180015ec7  mov     rdx, rdi
0x180015eca  mov     rcx, r13
0x180015ecd  mov     rax, [rax+18h]
0x180015ed1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ed6  mov     ebx, eax
0x180015ed8  test    eax, eax
0x180015eda  js      loc_1800160C4
0x180015ee0  mov     rax, [rdi]
0x180015ee3  mov     rcx, rdi
0x180015ee6  mov     rax, [rax+10h]
0x180015eea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015eef  mov     rcx, [rsp+550h+var_508]
0x180015ef4  mov     rax, [rcx]
0x180015ef7  mov     rax, [rax+10h]
0x180015efb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f00  inc     r15d
0x180015f03  mov     [rsp+550h+var_508], 0
0x180015f0c  jmp     loc_180015DF3
0x180015f11  mov     rcx, [rsp+550h+var_510]
0x180015f16  mov     rax, [rcx]
0x180015f19  mov     rax, [rax+10h]
0x180015f1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f22  xor     r15d, r15d
0x180015f25  mov     [rsp+550h+var_510], r15
0x180015f2a  jmp     loc_180016071
0x180015f2f  mov     rax, [rax+38h]
0x180015f33  lea     rdx, [rsp+550h+var_4D8]
0x180015f38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f3d  mov     ebx, eax
0x180015f3f  test    eax, eax
0x180015f41  js      loc_1800160C7
0x180015f47  mov     rcx, [rsp+550h+var_4D8]
0x180015f4c  lea     rdx, [rsp+550h+var_4F8]
0x180015f51  mov     rax, [rcx]
0x180015f54  mov     rax, [rax+28h]
0x180015f58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f5d  mov     ebx, eax
0x180015f5f  test    eax, eax
0x180015f61  js      loc_1800160C7
0x180015f67  mov     rdx, [rsp+550h+var_4F8]; struct INativeConfigurationElementCollection *
0x180015f6c  lea     rax, [rsp+550h+var_508]
0x180015f71  lea     r9, [rsp+550h+var_510]; struct INativeConfigurationElement **
0x180015f76  mov     [rsp+550h+var_530], rax; struct INativeConfigurationElement **
0x180015f7b  mov     r8, rsi; unsigned __int16 *
0x180015f7e  call    ?FindDirElement@VDIR_OBJECT_EXTENSION@@AEAAJPEAVINativeConfigurationElementCollection@@PEBGPEAPEAVINativeConfigurationElement@@2@Z; VDIR_OBJECT_EXTENSION::FindDirElement(INativeConfigurationElementCollection *,ushort const *,INativeConfigurationElement * *,INativeConfigurationElement * *)
0x180015f83  mov     ebx, eax
0x180015f85  test    eax, eax
0x180015f87  js      loc_1800160C7
  ... truncated ...
```
