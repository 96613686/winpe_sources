# APP_OBJECT_EXTENSION::FindApplication(IExtensionContext *,ICommandObject *,ushort const *,APP_OBJECT * *)

- ea: `0x180014a40`
- end: `0x180014f48`
- name: `?FindApplication@APP_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEAVICommandObject@@PEBGPEAPEAVAPP_OBJECT@@@Z`
- size: `1288`
- prototype: `int(APP_OBJECT_EXTENSION *__hidden this, struct IExtensionContext *, struct ICommandObject *, const unsigned __int16 *, struct APP_OBJECT **)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180014010`

## callees

- `0x180001044`
- `0x180001fb0`
- `0x180002e60`
- `0x180002e90`
- `0x1800049b0`
- `0x1800134b8`
- `0x180013d88`
- `0x180014a40`
- `0x18002bb20`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180014d49`
- `msvcrt!_wcsnicmp` at `0x180014d49`

## pseudocode

```c
__int64 __fastcall APP_OBJECT_EXTENSION::FindApplication(
        APP_OBJECT_EXTENSION *this,
        struct IExtensionContext *a2,
        struct ICommandObject *a3,
        const unsigned __int16 *a4,
        struct APP_OBJECT **a5)
{
  struct APP_OBJECT **v5; // r13
  struct INativeConfigurationElement *v9; // rdi
  APP_OBJECT_UTILS *v10; // rcx
  struct APP_OBJECT *v11; // rsi
  int v12; // ebx
  wchar_t *v13; // r12
  unsigned int v14; // r13d
  unsigned int i; // r15d
  __int64 v16; // rdx
  wchar_t *v17; // rbx
  __int64 v18; // r14
  int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // r8
  APP_OBJECT *v22; // rax
  APP_OBJECT *v23; // rax
  struct INativeConfigurationElement *v25; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v26; // [rsp+58h] [rbp-A8h] BYREF
  struct INativeConfigurationElement *v27; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v28; // [rsp+68h] [rbp-98h] BYREF
  __int64 v29; // [rsp+70h] [rbp-90h] BYREF
  __int64 v30; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v31; // [rsp+80h] [rbp-80h] BYREF
  wchar_t *String2; // [rsp+88h] [rbp-78h] BYREF
  __int64 v33; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v34; // [rsp+98h] [rbp-68h] BYREF
  struct APP_OBJECT **v35; // [rsp+A0h] [rbp-60h]
  _BYTE v36[32]; // [rsp+A8h] [rbp-58h] BYREF
  wchar_t *String1; // [rsp+C8h] [rbp-38h]
  int v38; // [rsp+D0h] [rbp-30h]
  __int16 v39; // [rsp+D4h] [rbp-2Ch]
  size_t MaxCount; // [rsp+D8h] [rbp-28h]
  _BYTE v41[32]; // [rsp+E0h] [rbp-20h] BYREF
  __int16 *v42; // [rsp+100h] [rbp+0h]
  int v43; // [rsp+108h] [rbp+8h]
  __int16 v44; // [rsp+10Ch] [rbp+Ch]
  int v45; // [rsp+110h] [rbp+10h]
  __int16 v46; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v47[510]; // [rsp+122h] [rbp+22h] BYREF
  __int16 v48; // [rsp+320h] [rbp+220h] BYREF
  _BYTE v49[510]; // [rsp+322h] [rbp+222h] BYREF

  v5 = a5;
  v35 = a5;
  v26 = 0;
  v25 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v9 = 0;
  v34 = 0;
  String2 = 0;
  v33 = 0;
  v31 = 0;
  memset_0(v47, 0, sizeof(v47));
  v39 = 256;
  String1 = (wchar_t *)&v46;
  v38 = 512;
  LODWORD(MaxCount) = 0;
  v46 = 0;
  memset_0(v49, 0, sizeof(v49));
  v43 = 512;
  v44 = 256;
  v42 = &v48;
  v11 = 0;
  v45 = 0;
  v48 = 0;
  if ( !a3 || !a4 || !a5 )
  {
    v12 = -2147024809;
    goto LABEL_48;
  }
  v12 = APP_OBJECT_UTILS::ResolveUrl(v10, a4, 0, (const unsigned __int16 **)&String2, 0);
  if ( v12 < 0 )
    goto LABEL_48;
  v13 = String2;
  if ( !String2 )
  {
    v12 = -2147024894;
    goto LABEL_48;
  }
  v12 = (*(__int64 (__fastcall **)(struct ICommandObject *, struct INativeConfigurationElement **))(*(_QWORD *)a3 + 48LL))(
          a3,
          &v27);
  if ( v12 >= 0 )
  {
    v12 = (*(__int64 (__fastcall **)(struct ICommandObject *, const unsigned __int16 *, __int64 *))(*(_QWORD *)a3 + 80LL))(
            a3,
            L"SITE.NAME",
            &v33);
    if ( v12 >= 0 )
    {
      v12 = (*(__int64 (__fastcall **)(struct ICommandObject *, unsigned __int16 **))(*(_QWORD *)a3 + 40LL))(a3, &v31);
      if ( v12 >= 0 )
      {
        v12 = (*(__int64 (__fastcall **)(struct IExtensionContext *, unsigned __int16 *, __int64 *))(*(_QWORD *)a2 + 80LL))(
                a2,
                v31,
                &v29);
        if ( v12 >= 0 )
        {
          v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v29 + 56LL))(v29, &v30);
          if ( v12 >= 0 )
          {
            v12 = (*(__int64 (__fastcall **)(__int64, __int64, wchar_t *, _QWORD, _QWORD, _QWORD, struct INativeConfigurationElement **, _QWORD))(*(_QWORD *)v30 + 40LL))(
                    v30,
                    v33,
                    v13,
                    0,
                    0,
                    0,
                    &v25,
                    0);
            if ( (int)(v12 + 0x80000000) < 0 || v12 == -2147024894 )
            {
              if ( !v25 )
              {
                v12 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 *))(*(_QWORD *)v27 + 40LL))(
                        v27,
                        &v28);
                if ( v12 < 0 )
                  goto LABEL_48;
                v14 = 0;
                (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v28 + 24LL))(v28, &v26);
                for ( i = 0; i < v26; ++i )
                {
                  v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct INativeConfigurationElement **))(*(_QWORD *)v28 + 32LL))(
                          v28,
                          i,
                          &v25);
                  if ( v12 < 0 )
                    goto LABEL_48;
                  v12 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v25 + 64LL))(
                          v25,
                          L"path",
                          &v34,
                          0,
                          0);
                  if ( v12 < 0 )
                    goto LABEL_48;
                  v12 = STRU::Copy((STRU *)v36, (const unsigned __int8 *)v34);
                  if ( v12 < 0 )
                    goto LABEL_48;
                  while ( 1 )
                  {
                    v17 = String1;
                    if ( (unsigned int)MaxCount <= 1 )
                      break;
                    v16 = (unsigned int)(MaxCount - 1);
                    if ( String1[v16] != 47 )
                      break;
                    STRU::SetLen((STRU *)v36, v16);
                  }
                  v18 = (unsigned int)MaxCount;
                  v19 = _wcsnicmp(String1, v13, (unsigned int)MaxCount);
                  v21 = 0;
                  if ( !v19 && (unsigned int)v18 > v14 )
                  {
                    v20 = (unsigned int)*v17 - 47;
                    if ( *v17 == 47 )
                      v20 = v17[1];
                    if ( !(_DWORD)v20 || !v13[v18] || v13[v18] == 47 )
                    {
                      if ( v9 )
                        (*(void (__fastcall **)(struct INativeConfigurationElement *, __int64, _QWORD))(*(_QWORD *)v9 + 16LL))(
                          v9,
                          v20,
                          0);
                      v9 = v25;
                      (*(void (__fastcall **)(struct INativeConfigurationElement *, __int64, __int64))(*(_QWORD *)v25 + 8LL))(
                        v25,
                        v20,
                        v21);
                      v12 = STRU::Copy((STRU *)v41, (const struct STRU *)v36);
                      if ( v12 < 0 )
                        goto LABEL_48;
                      v14 = v18;
                    }
                  }
                  (*(void (__fastcall **)(struct INativeConfigurationElement *, __int64, __int64))(*(_QWORD *)v25 + 16LL))(
                    v25,
                    v20,
                    v21);
                  v25 = 0;
                }
                v25 = v9;
                if ( !v9 )
                {
                  v12 = -2147024894;
LABEL_46:
                  v9 = 0;
                  goto LABEL_48;
                }
                v5 = v35;
              }
              v22 = (APP_OBJECT *)operator new(0xD8u);
              if ( v22 )
              {
                v23 = APP_OBJECT::APP_OBJECT(v22, v25, v27);
                v11 = v23;
                if ( v23 )
                {
                  v12 = APP_OBJECT::Create(v23, v31);
                  v9 = 0;
                  if ( v12 >= 0 )
                  {
                    *v5 = v11;
                    v12 = 0;
                    v11 = 0;
                  }
                  goto LABEL_48;
                }
              }
              else
              {
                v11 = 0;
              }
              v12 = -2147024888;
              goto LABEL_46;
            }
          }
        }
      }
    }
  }
LABEL_48:
  if ( v27 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v27 + 16LL))(v27);
    v27 = 0;
  }
  if ( v28 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    v28 = 0;
  }
  if ( v29 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    v29 = 0;
  }
  if ( v30 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    v30 = 0;
  }
  if ( v11 )
    (*(void (__fastcall **)(struct APP_OBJECT *))(*(_QWORD *)v11 + 16LL))(v11);
  if ( v9 )
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v9 + 16LL))(v9);
  if ( v25 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v25 + 16LL))(v25);
    v25 = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v41);
  BUFFER::~BUFFER((BUFFER *)v36);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180014a40  mov     [rsp-8+arg_0], rbx
0x180014a45  push    rbp
0x180014a46  push    rsi
0x180014a47  push    rdi
0x180014a48  push    r12
0x180014a4a  push    r13
0x180014a4c  push    r14
0x180014a4e  push    r15
0x180014a50  lea     rbp, [rsp-430h]
0x180014a58  sub     rsp, 530h
0x180014a5f  mov     rax, cs:__security_cookie
0x180014a66  xor     rax, rsp
0x180014a69  mov     [rbp+460h+var_40], rax
0x180014a70  mov     r13, [rbp+460h+arg_20]
0x180014a77  lea     rcx, [rbp+460h+var_43E]; void *
0x180014a7b  xor     eax, eax
0x180014a7d  mov     [rbp+460h+var_4C0], r13
0x180014a81  mov     r14, r8
0x180014a84  mov     [rsp+560h+var_508], eax
0x180014a88  mov     r15, rdx
0x180014a8b  mov     [rsp+560h+var_510], rax
0x180014a90  mov     r12d, 1FEh
0x180014a96  mov     [rsp+560h+var_500], rax
0x180014a9b  mov     r8d, r12d; Size
0x180014a9e  mov     [rsp+560h+var_4F8], rax
0x180014aa3  xor     edx, edx; Val
0x180014aa5  mov     [rsp+560h+var_4F0], rax
0x180014aaa  mov     rbx, r9
0x180014aad  mov     [rsp+560h+var_4E8], rax
0x180014ab2  mov     edi, eax
0x180014ab4  mov     [rbp+460h+var_4C8], rax
0x180014ab8  mov     [rbp+460h+String2], rax
0x180014abc  mov     [rbp+460h+var_4D0], rax
0x180014ac0  mov     [rbp+460h+var_4E0], rax
0x180014ac4  call    memset_0
0x180014ac9  lea     rax, [rbp+460h+var_440]
0x180014acd  mov     [rbp+460h+var_48C], 100h
0x180014ad3  mov     [rbp+460h+String1], rax
0x180014ad7  lea     esi, [r12+2]
0x180014adc  xor     eax, eax
0x180014ade  mov     [rbp+460h+var_490], esi
0x180014ae1  mov     r8d, r12d; Size
0x180014ae4  mov     dword ptr [rbp+460h+MaxCount], eax
0x180014ae7  xor     edx, edx; Val
0x180014ae9  mov     [rbp+460h+var_440], ax
0x180014aed  lea     rcx, [rbp+460h+var_23E]; void *
0x180014af4  call    memset_0
0x180014af9  xor     r12d, r12d
0x180014afc  mov     [rbp+460h+var_458], esi
0x180014aff  mov     [rbp+460h+var_454], 100h
0x180014b05  lea     rax, [rbp+460h+var_240]
0x180014b0c  mov     [rbp+460h+var_460], rax
0x180014b10  mov     esi, r12d
0x180014b13  mov     [rbp+460h+var_450], r12d
0x180014b17  mov     [rbp+460h+var_240], r12w
0x180014b1f  test    r14, r14
0x180014b22  jz      loc_180014E53
0x180014b28  test    rbx, rbx
0x180014b2b  jz      loc_180014E53
0x180014b31  test    r13, r13
0x180014b34  jz      loc_180014E53
0x180014b3a  lea     r9, [rbp+460h+String2]; unsigned __int16 **
0x180014b3e  mov     [rsp+560h+var_540], r12; int *
0x180014b43  xor     r8d, r8d; struct STRU *
0x180014b46  mov     rdx, rbx; unsigned __int16 *
0x180014b49  call    ?ResolveUrl@APP_OBJECT_UTILS@@QEAAJPEBGPEAVSTRU@@PEAPEBGPEAH@Z; APP_OBJECT_UTILS::ResolveUrl(ushort const *,STRU *,ushort const * *,int *)
0x180014b4e  mov     ebx, eax
0x180014b50  test    eax, eax
0x180014b52  js      loc_180014E58
0x180014b58  mov     r12, [rbp+460h+String2]
0x180014b5c  test    r12, r12
0x180014b5f  jnz     short loc_180014B6B
0x180014b61  mov     ebx, 80070002h
0x180014b66  jmp     loc_180014E58
0x180014b6b  mov     rax, [r14]
0x180014b6e  lea     rdx, [rsp+560h+var_500]
0x180014b73  mov     rcx, r14
0x180014b76  mov     rax, [rax+30h]
0x180014b7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b7f  mov     ebx, eax
0x180014b81  test    eax, eax
0x180014b83  js      loc_180014E58
0x180014b89  mov     rax, [r14]
0x180014b8c  lea     r8, [rbp+460h+var_4D0]
0x180014b90  lea     rdx, aSiteName; "SITE.NAME"
0x180014b97  mov     rcx, r14
0x180014b9a  mov     rax, [rax+50h]
0x180014b9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ba3  mov     ebx, eax
0x180014ba5  test    eax, eax
0x180014ba7  js      loc_180014E58
0x180014bad  mov     rax, [r14]
0x180014bb0  lea     rdx, [rbp+460h+var_4E0]
0x180014bb4  mov     rcx, r14
0x180014bb7  mov     rax, [rax+28h]
0x180014bbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014bc0  xor     r14d, r14d
0x180014bc3  mov     ebx, eax
0x180014bc5  test    eax, eax
0x180014bc7  js      loc_180014E58
0x180014bcd  mov     rax, [r15]
0x180014bd0  lea     r8, [rsp+560h+var_4F0]
0x180014bd5  mov     rdx, [rbp+460h+var_4E0]
0x180014bd9  mov     rcx, r15
0x180014bdc  mov     rax, [rax+50h]
0x180014be0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014be5  mov     ebx, eax
0x180014be7  test    eax, eax
0x180014be9  js      loc_180014E58
0x180014bef  mov     rcx, [rsp+560h+var_4F0]
0x180014bf4  lea     rdx, [rsp+560h+var_4E8]
0x180014bf9  mov     rax, [rcx]
0x180014bfc  mov     rax, [rax+38h]
0x180014c00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c05  mov     ebx, eax
0x180014c07  test    eax, eax
0x180014c09  js      loc_180014E58
0x180014c0f  mov     rcx, [rsp+560h+var_4E8]
0x180014c14  lea     rdx, [rsp+560h+var_510]
0x180014c19  mov     [rsp+560h+var_528], r14
0x180014c1e  xor     r9d, r9d
0x180014c21  mov     [rsp+560h+var_530], rdx
0x180014c26  mov     r8, r12
0x180014c29  mov     rdx, [rbp+460h+var_4D0]
0x180014c2d  mov     rax, [rcx]
0x180014c30  mov     [rsp+560h+var_538], r14
0x180014c35  mov     [rsp+560h+var_540], r14
0x180014c3a  mov     rax, [rax+28h]
0x180014c3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c43  mov     ecx, 80000000h
0x180014c48  mov     ebx, eax
0x180014c4a  add     eax, ecx
0x180014c4c  test    ecx, eax
0x180014c4e  jnz     short loc_180014C5C
0x180014c50  cmp     ebx, 80070002h
0x180014c56  jnz     loc_180014E58
0x180014c5c  cmp     [rsp+560h+var_510], r14
0x180014c61  jnz     loc_180014DFC
0x180014c67  mov     rcx, [rsp+560h+var_500]
0x180014c6c  lea     rdx, [rsp+560h+var_4F8]
0x180014c71  mov     rax, [rcx]
0x180014c74  mov     rax, [rax+28h]
0x180014c78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c7d  mov     ebx, eax
0x180014c7f  test    eax, eax
0x180014c81  js      loc_180014E58
0x180014c87  mov     rcx, [rsp+560h+var_4F8]
0x180014c8c  lea     rdx, [rsp+560h+var_508]
0x180014c91  mov     r13d, r14d
0x180014c94  mov     rax, [rcx]
0x180014c97  mov     rax, [rax+18h]
0x180014c9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ca0  mov     r15d, r14d
0x180014ca3  cmp     r15d, [rsp+560h+var_508]
0x180014ca8  jnb     loc_180014DE7
0x180014cae  mov     rcx, [rsp+560h+var_4F8]
0x180014cb3  lea     r8, [rsp+560h+var_510]
0x180014cb8  mov     edx, r15d
0x180014cbb  mov     rax, [rcx]
0x180014cbe  mov     rax, [rax+20h]
0x180014cc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014cc7  mov     ebx, eax
0x180014cc9  test    eax, eax
0x180014ccb  js      loc_180014E58
0x180014cd1  mov     rcx, [rsp+560h+var_510]
0x180014cd6  lea     r8, [rbp+460h+var_4C8]
0x180014cda  xor     r9d, r9d
0x180014cdd  mov     [rsp+560h+var_540], r14
0x180014ce2  lea     rdx, aPath_1; "path"
0x180014ce9  mov     rax, [rcx]
0x180014cec  mov     rax, [rax+40h]
0x180014cf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014cf5  mov     ebx, eax
0x180014cf7  test    eax, eax
0x180014cf9  js      loc_180014E58
0x180014cff  mov     rdx, [rbp+460h+var_4C8]; unsigned __int16 *
0x180014d03  lea     rcx, [rbp+460h+var_4B8]; this
0x180014d07  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180014d0c  mov     ebx, eax
0x180014d0e  test    eax, eax
0x180014d10  js      loc_180014E58
0x180014d16  jmp     short loc_180014D31
0x180014d18  lea     edx, [rcx-1]; unsigned int
0x180014d1b  mov     r8d, 2Fh ; '/'
0x180014d21  cmp     [rbx+rdx*2], r8w
0x180014d26  jnz     short loc_180014D3D
0x180014d28  lea     rcx, [rbp+460h+var_4B8]; this
0x180014d2c  call    ?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x180014d31  mov     ecx, dword ptr [rbp+460h+MaxCount]
0x180014d34  mov     rbx, [rbp+460h+String1]
0x180014d38  cmp     ecx, 1
0x180014d3b  ja      short loc_180014D18
0x180014d3d  mov     r14d, ecx
0x180014d40  mov     rdx, r12; String2
0x180014d43  mov     r8d, ecx; MaxCount
0x180014d46  mov     rcx, rbx; String1
0x180014d49  call    cs:__imp__wcsnicmp
0x180014d4f  xor     r8d, r8d
0x180014d52  test    eax, eax
0x180014d54  jnz     short loc_180014DC6
0x180014d56  cmp     r14d, r13d
0x180014d59  jbe     short loc_180014DC6
0x180014d5b  movzx   edx, word ptr [rbx]
0x180014d5e  lea     ecx, [rax+2Fh]
0x180014d61  sub     edx, ecx
0x180014d63  jnz     short loc_180014D72
0x180014d65  movzx   edx, word ptr [rbx+2]
0x180014d69  movzx   ecx, r8w
0x180014d6d  sub     edx, ecx
0x180014d6f  lea     ecx, [rax+2Fh]
0x180014d72  test    edx, edx
0x180014d74  jz      short loc_180014D84
0x180014d76  cmp     [r12+r14*2], r8w
0x180014d7b  jz      short loc_180014D84
0x180014d7d  cmp     [r12+r14*2], cx
0x180014d82  jnz     short loc_180014DC6
0x180014d84  test    rdi, rdi
0x180014d87  jz      short loc_180014D98
0x180014d89  mov     rax, [rdi]
0x180014d8c  mov     rcx, rdi
0x180014d8f  mov     rax, [rax+10h]
0x180014d93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d98  mov     rdi, [rsp+560h+var_510]
0x180014d9d  mov     rcx, rdi
0x180014da0  mov     rax, [rdi]
0x180014da3  mov     rax, [rax+8]
0x180014da7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014dac  lea     rdx, [rbp+460h+var_4B8]; struct STRU *
0x180014db0  lea     rcx, [rbp+460h+var_480]; this
0x180014db4  call    ?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x180014db9  mov     ebx, eax
0x180014dbb  test    eax, eax
0x180014dbd  js      loc_180014E58
0x180014dc3  mov     r13d, r14d
0x180014dc6  mov     rcx, [rsp+560h+var_510]
0x180014dcb  mov     rax, [rcx]
0x180014dce  mov     rax, [rax+10h]
0x180014dd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014dd7  xor     r14d, r14d
0x180014dda  mov     [rsp+560h+var_510], r14
0x180014ddf  inc     r15d
0x180014de2  jmp     loc_180014CA3
0x180014de7  mov     [rsp+560h+var_510], rdi
0x180014dec  test    rdi, rdi
0x180014def  jnz     short loc_180014DF8
0x180014df1  mov     ebx, 80070002h
0x180014df6  jmp     short loc_180014E4E
0x180014df8  mov     r13, [rbp+460h+var_4C0]
0x180014dfc  mov     ecx, 0D8h; Size
0x180014e01  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014e06  test    rax, rax
0x180014e09  jz      short loc_180014E46
0x180014e0b  mov     r8, [rsp+560h+var_500]; struct INativeConfigurationElement *
0x180014e10  mov     rcx, rax; this
0x180014e13  mov     rdx, [rsp+560h+var_510]; struct INativeConfigurationElement *
0x180014e18  call    ??0APP_OBJECT@@QEAA@PEAVINativeConfigurationElement@@0@Z; APP_OBJECT::APP_OBJECT(INativeConfigurationElement *,INativeConfigurationElement *)
0x180014e1d  mov     rsi, rax
0x180014e20  test    rax, rax
0x180014e23  jz      short loc_180014E49
0x180014e25  mov     rdx, [rbp+460h+var_4E0]; unsigned __int16 *
0x180014e29  mov     rcx, rax; this
0x180014e2c  call    ?Create@APP_OBJECT@@QEAAJPEBG@Z; APP_OBJECT::Create(ushort const *)
0x180014e31  mov     ebx, eax
0x180014e33  mov     rdi, r14
0x180014e36  test    eax, eax
0x180014e38  js      short loc_180014E58
0x180014e3a  mov     [r13+0], rsi
0x180014e3e  mov     ebx, r14d
0x180014e41  mov     rsi, r14
0x180014e44  jmp     short loc_180014E58
0x180014e46  mov     rsi, r14
0x180014e49  mov     ebx, 80070008h
0x180014e4e  mov     rdi, r14
0x180014e51  jmp     short loc_180014E58
0x180014e53  mov     ebx, 80070057h
0x180014e58  mov     rcx, [rsp+560h+var_500]
0x180014e5d  xor     r14d, r14d
0x180014e60  test    rcx, rcx
0x180014e63  jz      short loc_180014E76
0x180014e65  mov     rax, [rcx]
0x180014e68  mov     rax, [rax+10h]
0x180014e6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e71  mov     [rsp+560h+var_500], r14
0x180014e76  mov     rcx, [rsp+560h+var_4F8]
0x180014e7b  test    rcx, rcx
0x180014e7e  jz      short loc_180014E91
0x180014e80  mov     rax, [rcx]
0x180014e83  mov     rax, [rax+10h]
0x180014e87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e8c  mov     [rsp+560h+var_4F8], r14
0x180014e91  mov     rcx, [rsp+560h+var_4F0]
0x180014e96  test    rcx, rcx
0x180014e99  jz      short loc_180014EAC
0x180014e9b  mov     rax, [rcx]
0x180014e9e  mov     rax, [rax+10h]
0x180014ea2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ea7  mov     [rsp+560h+var_4F0], r14
0x180014eac  mov     rcx, [rsp+560h+var_4E8]
0x180014eb1  test    rcx, rcx
0x180014eb4  jz      short loc_180014EC7
  ... truncated ...
```
