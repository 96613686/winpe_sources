# SITE_OBJECT_EXTENSION::SetBindingInformation(IExtensionContext *,INativeConfigurationElement *,ushort const *,int)

- ea: `0x180012450`
- end: `0x180012acc`
- name: `?SetBindingInformation@SITE_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEAVINativeConfigurationElement@@PEBGH@Z`
- size: `1660`
- prototype: `int(SITE_OBJECT_EXTENSION *__hidden this, struct IExtensionContext *, struct INativeConfigurationElement *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000f234`
- `0x180012d34`

## callees

- `0x180001fb0`
- `0x180002640`
- `0x180002680`
- `0x180002e90`
- `0x180002ed0`
- `0x1800049b0`
- `0x180012450`
- `0x18002bb20`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!wcsstr` at `0x18001265e`
- `msvcrt!wcsstr` at `0x180012671`
- `msvcrt!wcsstr` at `0x180012725`
- `msvcrt!wcsstr` at `0x1800127dc`
- `msvcrt!wcsstr` at `0x180012837`
- `msvcrt!wcsstr` at `0x18001265e`
- `msvcrt!wcsstr` at `0x180012671`
- `msvcrt!wcsstr` at `0x180012725`
- `msvcrt!wcsstr` at `0x1800127dc`
- `msvcrt!wcsstr` at `0x180012837`

## string_xrefs

- `0x1800128b3`: `protocol`
- `0x1800129e1`: `protocol://domain:port | protocol/BindingInformation,...`

## pseudocode

```c
__int64 __fastcall SITE_OBJECT_EXTENSION::SetBindingInformation(
        SITE_OBJECT_EXTENSION *this,
        struct IExtensionContext *a2,
        struct INativeConfigurationElement *a3,
        wchar_t *a4,
        int a5)
{
  __int16 *v8; // r12
  int v9; // ebx
  unsigned int v10; // eax
  unsigned int i; // esi
  wchar_t *v12; // rsi
  wchar_t *v13; // rax
  wchar_t *v14; // r14
  int v15; // eax
  APP_OBJECT_UTILS *v16; // rcx
  wchar_t *v17; // r14
  wchar_t *v18; // rdi
  wchar_t *v19; // rax
  wchar_t *v20; // r14
  wchar_t *v21; // rax
  const unsigned __int16 *v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rax
  unsigned int v27; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v28; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v29; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v30; // [rsp+48h] [rbp-B8h] BYREF
  int v31; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v32; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v33; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v34; // [rsp+70h] [rbp-90h] BYREF
  __int64 v35; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v36[32]; // [rsp+80h] [rbp-80h] BYREF
  __int16 *v37; // [rsp+A0h] [rbp-60h]
  int v38; // [rsp+A8h] [rbp-58h]
  __int16 v39; // [rsp+ACh] [rbp-54h]
  unsigned int v40; // [rsp+B0h] [rbp-50h]
  _BYTE v41[32]; // [rsp+B8h] [rbp-48h] BYREF
  __int16 *v42; // [rsp+D8h] [rbp-28h]
  int v43; // [rsp+E0h] [rbp-20h]
  __int16 v44; // [rsp+E4h] [rbp-1Ch]
  int v45; // [rsp+E8h] [rbp-18h]
  _BYTE v46[32]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 *v47; // [rsp+110h] [rbp+10h]
  int v48; // [rsp+118h] [rbp+18h]
  __int16 v49; // [rsp+11Ch] [rbp+1Ch]
  int v50; // [rsp+120h] [rbp+20h]
  _BYTE v51[32]; // [rsp+128h] [rbp+28h] BYREF
  wchar_t *Str; // [rsp+148h] [rbp+48h]
  int v53; // [rsp+150h] [rbp+50h]
  __int16 v54; // [rsp+154h] [rbp+54h]
  int v55; // [rsp+158h] [rbp+58h]
  __int16 v56; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v57[510]; // [rsp+162h] [rbp+62h] BYREF
  __int16 v58; // [rsp+360h] [rbp+260h] BYREF
  _BYTE v59[510]; // [rsp+362h] [rbp+262h] BYREF
  __int16 v60; // [rsp+560h] [rbp+460h] BYREF
  _BYTE v61[510]; // [rsp+562h] [rbp+462h] BYREF
  __int16 v62; // [rsp+760h] [rbp+660h] BYREF
  _BYTE v63[510]; // [rsp+762h] [rbp+662h] BYREF

  v29 = 0;
  v32 = 0;
  v30 = 0;
  v28 = 0;
  v35 = 0;
  memset_0(v57, 0, sizeof(v57));
  v8 = &v56;
  v44 = 256;
  v42 = &v56;
  v43 = 512;
  v45 = 0;
  v56 = 0;
  memset_0(v59, 0, sizeof(v59));
  v38 = 512;
  v37 = &v58;
  v39 = 256;
  v40 = 0;
  v58 = 0;
  v33 = 0;
  v27 = 0;
  memset_0(v61, 0, sizeof(v61));
  v48 = 512;
  v47 = (unsigned __int16 *)&v60;
  v49 = 256;
  v50 = 0;
  v60 = 0;
  memset_0(v63, 0, sizeof(v63));
  v53 = 512;
  Str = (wchar_t *)&v62;
  v54 = 256;
  v55 = 0;
  v62 = 0;
  v34 = 0;
  v31 = 0;
  if ( !a2 || !a3 || !a4 )
  {
    v9 = -2147024809;
    goto LABEL_62;
  }
  v9 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, __int64 *))(*(_QWORD *)a3 + 32LL))(
         a3,
         L"bindings",
         &v32);
  if ( v9 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v32 + 40LL))(v32, &v28);
    if ( v9 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v28 + 24LL))(v28, &v27);
      if ( v9 >= 0 )
      {
        v10 = v27;
        if ( a5 && v27 )
        {
          v9 = 1;
          goto LABEL_62;
        }
        for ( i = 0; i < v10; ++i )
        {
          v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v28 + 64LL))(v28, 0, 0);
          if ( v9 < 0 )
            goto LABEL_62;
          v10 = v27;
        }
        while ( 1 )
        {
          while ( *a4 == 32 )
            ++a4;
          v12 = wcsstr(a4, L",");
          v13 = wcsstr(a4, L"://");
          v14 = v13;
          if ( !v13 )
            break;
          if ( v12 )
          {
            if ( v13 >= v12 )
              break;
            v15 = STRU::Copy((STRU *)v46, a4, v12 - a4);
          }
          else
          {
            v15 = STRU::Copy((STRU *)v46, a4);
          }
          v9 = v15;
          if ( v15 < 0 )
            goto LABEL_59;
          if ( APP_OBJECT_UTILS::ResolveUrl(v16, v47, (struct STRU *)v51, (const unsigned __int16 **)&v34, &v31) < 0
            || !v31
            || v34 )
          {
            goto LABEL_58;
          }
          v9 = STRU::Copy((STRU *)v41, a4, v14 - a4);
          if ( v9 < 0 )
            goto LABEL_59;
          v17 = Str;
          v18 = wcsstr(Str, L":");
          if ( !v18 )
          {
LABEL_58:
            v9 = -2147024809;
LABEL_59:
            v24 = 3221226513LL;
            *(_QWORD *)&v33 = L"bindings";
            v23 = (unsigned int)v9;
            *((_QWORD *)&v33 + 1) = L"protocol://domain:port | protocol/BindingInformation,...";
LABEL_60:
            (*(void (__fastcall **)(struct IExtensionContext *, __int64, __int64, __int128 *, _DWORD))(*(_QWORD *)a2 + 144LL))(
              a2,
              v23,
              v24,
              &v33,
              0);
            goto LABEL_62;
          }
          v9 = STRU::Copy((STRU *)v36, L"*:");
          if ( v9 < 0 )
            goto LABEL_59;
          v9 = STRU::Append((STRU *)v36, v18 + 1);
          if ( v9 < 0 )
            goto LABEL_59;
          v9 = STRU::Append((STRU *)v36, L":");
          if ( v9 < 0 )
            goto LABEL_59;
          v9 = STRU::Append((STRU *)v36, v17, v18 - v17);
          if ( v9 < 0 )
            goto LABEL_59;
          if ( v40 > 2 && v37[v40 - 1] == 42 )
            STRU::SetLen((STRU *)v36, v40 - 1);
          a4 = v12 + 1;
          if ( !v12 )
            a4 = 0;
LABEL_46:
          v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v28 + 48LL))(
                 v28,
                 L"binding",
                 &v30);
          if ( v9 < 0 )
            goto LABEL_62;
          v8 = v42;
          v9 = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64, const unsigned __int16 *, __int16 *))(*(_QWORD *)a2 + 96LL))(
                 a2,
                 v30,
                 L"protocol",
                 v42);
          if ( v9 < 0 )
            goto LABEL_62;
          v9 = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64, const wchar_t *, __int16 *))(*(_QWORD *)a2 + 96LL))(
                 a2,
                 v30,
                 L"bindingInformation",
                 v37);
          if ( v9 < 0 )
            goto LABEL_62;
          v9 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)v28 + 56LL))(
                 v28,
                 v30,
                 0xFFFFFFFFLL,
                 &v29);
          if ( v9 < 0 )
          {
            v23 = 2147942583LL;
            if ( v9 == -2147024713 )
            {
              v33 = (unsigned __int64)a4;
              v24 = 3221226483LL;
              goto LABEL_60;
            }
            if ( v29 )
            {
              (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v29 + 24LL))(v29, &v35);
              if ( v35 )
              {
                *((_QWORD *)&v33 + 1) = v35;
                v25 = *(_QWORD *)a2;
                *(_QWORD *)&v33 = L"binding";
                (*(void (__fastcall **)(struct IExtensionContext *, _QWORD, __int64, __int128 *, _DWORD))(v25 + 144))(
                  a2,
                  (unsigned int)v9,
                  3221226480LL,
                  &v33,
                  0);
              }
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
              v29 = 0;
            }
            goto LABEL_62;
          }
          if ( !a4 )
          {
            v9 = 0;
            goto LABEL_62;
          }
        }
        v19 = wcsstr(a4, L"/");
        v20 = v19;
        if ( !v19 || v19 == a4 || v12 && v19 > v12 )
          goto LABEL_58;
        *v8 = 0;
        v45 = 0;
        v9 = STRU::Copy((STRU *)v41, a4, v19 - a4);
        if ( v9 < 0 )
          goto LABEL_59;
        v21 = wcsstr(a4, L",");
        v22 = v20 + 1;
        v40 = 0;
        a4 = v21;
        *v37 = 0;
        if ( v21 )
        {
          v9 = STRU::Copy((STRU *)v36, v22, v21 - v22);
          if ( v9 < 0 )
            goto LABEL_59;
          ++a4;
        }
        else
        {
          v9 = STRU::Copy((STRU *)v36, v22);
          if ( v9 < 0 )
            goto LABEL_59;
        }
        goto LABEL_46;
      }
    }
  }
LABEL_62:
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
  if ( v32 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    v32 = 0;
  }
  if ( v30 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    v30 = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v51);
  BUFFER::~BUFFER((BUFFER *)v46);
  BUFFER::~BUFFER((BUFFER *)v36);
  BUFFER::~BUFFER((BUFFER *)v41);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180012450  mov     [rsp-8+arg_0], rbx
0x180012455  push    rbp
0x180012456  push    rsi
0x180012457  push    rdi
0x180012458  push    r12
0x18001245a  push    r13
0x18001245c  push    r14
0x18001245e  push    r15
0x180012460  lea     rbp, [rsp-870h]
0x180012468  sub     rsp, 970h
0x18001246f  mov     rax, cs:__security_cookie
0x180012476  xor     rax, rsp
0x180012479  mov     [rbp+8A0h+var_40], rax
0x180012480  xor     r13d, r13d
0x180012483  lea     rcx, [rbp+8A0h+var_83E]; void *
0x180012487  mov     rbx, r8
0x18001248a  mov     [rsp+9A0h+var_960], r13
0x18001248f  mov     r15, rdx
0x180012492  mov     [rsp+9A0h+var_948], r13
0x180012497  mov     r14d, 1FEh
0x18001249d  mov     [rsp+9A0h+var_958], r13
0x1800124a2  mov     r8d, r14d; Size
0x1800124a5  mov     [rsp+9A0h+var_968], r13
0x1800124aa  xor     edx, edx; Val
0x1800124ac  mov     [rsp+9A0h+var_928], r13
0x1800124b1  mov     rdi, r9
0x1800124b4  call    memset_0
0x1800124b9  lea     r12, [rbp+8A0h+var_840]
0x1800124bd  mov     [rbp+8A0h+var_8BC], 100h
0x1800124c3  lea     esi, [r14+2]
0x1800124c7  mov     [rbp+8A0h+var_8C8], r12
0x1800124cb  mov     r8d, r14d; Size
0x1800124ce  mov     [rbp+8A0h+var_8C0], esi
0x1800124d1  xor     edx, edx; Val
0x1800124d3  mov     [rbp+8A0h+var_8B8], r13d
0x1800124d7  lea     rcx, [rbp+8A0h+var_63E]; void *
0x1800124de  mov     [rbp+8A0h+var_840], r13w
0x1800124e3  call    memset_0
0x1800124e8  lea     rax, [rbp+8A0h+var_640]
0x1800124ef  mov     [rbp+8A0h+var_8F8], esi
0x1800124f2  xorps   xmm0, xmm0
0x1800124f5  mov     [rbp+8A0h+var_900], rax
0x1800124f9  mov     r8d, r14d; Size
0x1800124fc  mov     [rbp+8A0h+var_8F4], 100h
0x180012502  xor     edx, edx; Val
0x180012504  mov     [rbp+8A0h+var_8F0], r13d
0x180012508  lea     rcx, [rbp+8A0h+var_43E]; void *
0x18001250f  mov     [rbp+8A0h+var_640], r13w
0x180012517  movups  [rsp+9A0h+var_940], xmm0
0x18001251c  mov     [rsp+9A0h+var_970], r13d
0x180012521  call    memset_0
0x180012526  lea     rax, [rbp+8A0h+var_440]
0x18001252d  mov     [rbp+8A0h+var_888], esi
0x180012530  mov     r8d, r14d; Size
0x180012533  mov     [rbp+8A0h+var_890], rax
0x180012537  xor     edx, edx; Val
0x180012539  mov     [rbp+8A0h+var_884], 100h
0x18001253f  lea     rcx, [rbp+8A0h+var_23E]; void *
0x180012546  mov     [rbp+8A0h+var_880], r13d
0x18001254a  mov     [rbp+8A0h+var_440], r13w
0x180012552  call    memset_0
0x180012557  mov     [rbp+8A0h+var_850], esi
0x18001255a  lea     rax, [rbp+8A0h+var_240]
0x180012561  mov     [rbp+8A0h+Str], rax
0x180012565  mov     [rbp+8A0h+var_84C], 100h
0x18001256b  mov     [rbp+8A0h+var_848], r13d
0x18001256f  mov     [rbp+8A0h+var_240], r13w
0x180012577  mov     [rsp+9A0h+var_930], r13
0x18001257c  mov     [rsp+9A0h+var_950], r13d
0x180012581  test    r15, r15
0x180012584  jz      loc_180012A0B
0x18001258a  test    rbx, rbx
0x18001258d  jz      loc_180012A0B
0x180012593  test    rdi, rdi
0x180012596  jz      loc_180012A0B
0x18001259c  mov     rax, [rbx]
0x18001259f  lea     r8, [rsp+9A0h+var_948]
0x1800125a4  lea     rdx, aBindings_0; "bindings"
0x1800125ab  mov     rcx, rbx
0x1800125ae  mov     rax, [rax+20h]
0x1800125b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125b7  mov     ebx, eax
0x1800125b9  test    eax, eax
0x1800125bb  js      loc_180012A10
0x1800125c1  mov     rcx, [rsp+9A0h+var_948]
0x1800125c6  lea     rdx, [rsp+9A0h+var_968]
0x1800125cb  mov     rax, [rcx]
0x1800125ce  mov     rax, [rax+28h]
0x1800125d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125d7  mov     ebx, eax
0x1800125d9  test    eax, eax
0x1800125db  js      loc_180012A10
0x1800125e1  mov     rcx, [rsp+9A0h+var_968]
0x1800125e6  lea     rdx, [rsp+9A0h+var_970]
0x1800125eb  mov     rax, [rcx]
0x1800125ee  mov     rax, [rax+18h]
0x1800125f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125f7  mov     ebx, eax
0x1800125f9  test    eax, eax
0x1800125fb  js      loc_180012A10
0x180012601  mov     eax, [rsp+9A0h+var_970]
0x180012605  cmp     [rbp+8A0h+arg_20], r13d
0x18001260c  jz      short loc_18001261B
0x18001260e  test    eax, eax
0x180012610  jz      short loc_18001261B
0x180012612  lea     ebx, [r13+1]
0x180012616  jmp     loc_180012A10
0x18001261b  mov     esi, r13d
0x18001261e  cmp     esi, eax
0x180012620  jnb     short loc_18001264E
0x180012622  mov     rcx, [rsp+9A0h+var_968]
0x180012627  xor     r8d, r8d
0x18001262a  xor     edx, edx
0x18001262c  mov     rax, [rcx]
0x18001262f  mov     rax, [rax+40h]
0x180012633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012638  mov     ebx, eax
0x18001263a  test    eax, eax
0x18001263c  js      loc_180012A10
0x180012642  mov     eax, [rsp+9A0h+var_970]
0x180012646  inc     esi
0x180012648  jmp     short loc_18001261E
0x18001264a  add     rdi, 2
0x18001264e  cmp     word ptr [rdi], 20h ; ' '
0x180012652  jz      short loc_18001264A
0x180012654  lea     rdx, asc_18003991C; ","
0x18001265b  mov     rcx, rdi; Str
0x18001265e  call    cs:__imp_wcsstr
0x180012664  lea     rdx, asc_18003A618; "://"
0x18001266b  mov     rcx, rdi; Str
0x18001266e  mov     rsi, rax
0x180012671  call    cs:__imp_wcsstr
0x180012677  mov     r14, rax
0x18001267a  test    rax, rax
0x18001267d  jz      loc_1800127D2
0x180012683  test    rsi, rsi
0x180012686  jz      short loc_1800126A8
0x180012688  cmp     rax, rsi
0x18001268b  jnb     loc_1800127D2
0x180012691  mov     r8, rsi
0x180012694  lea     rcx, [rbp+8A0h+var_8B0]; this
0x180012698  sub     r8, rdi
0x18001269b  mov     rdx, rdi; unsigned __int16 *
0x18001269e  sar     r8, 1; unsigned int
0x1800126a1  call    ?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x1800126a6  jmp     short loc_1800126B4
0x1800126a8  mov     rdx, rdi; unsigned __int16 *
0x1800126ab  lea     rcx, [rbp+8A0h+var_8B0]; this
0x1800126af  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800126b4  mov     ebx, eax
0x1800126b6  test    eax, eax
0x1800126b8  js      loc_1800129CD
0x1800126be  mov     rdx, [rbp+8A0h+var_890]; unsigned __int16 *
0x1800126c2  lea     rax, [rsp+9A0h+var_950]
0x1800126c7  lea     r9, [rsp+9A0h+var_930]; unsigned __int16 **
0x1800126cc  mov     [rsp+9A0h+var_980], rax; int *
0x1800126d1  lea     r8, [rbp+8A0h+var_878]; struct STRU *
0x1800126d5  call    ?ResolveUrl@APP_OBJECT_UTILS@@QEAAJPEBGPEAVSTRU@@PEAPEBGPEAH@Z; APP_OBJECT_UTILS::ResolveUrl(ushort const *,STRU *,ushort const * *,int *)
0x1800126da  test    eax, eax
0x1800126dc  js      loc_1800129C8
0x1800126e2  cmp     [rsp+9A0h+var_950], r13d
0x1800126e7  jz      loc_1800129C8
0x1800126ed  cmp     [rsp+9A0h+var_930], r13
0x1800126f2  jnz     loc_1800129C8
0x1800126f8  sub     r14, rdi
0x1800126fb  lea     rcx, [rbp+8A0h+var_8E8]; this
0x1800126ff  sar     r14, 1
0x180012702  mov     rdx, rdi; unsigned __int16 *
0x180012705  mov     r8d, r14d; unsigned int
0x180012708  call    ?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18001270d  mov     ebx, eax
0x18001270f  test    eax, eax
0x180012711  js      loc_1800129CD
0x180012717  mov     r14, [rbp+8A0h+Str]
0x18001271b  lea     rdx, asc_18003A620; ":"
0x180012722  mov     rcx, r14; Str
0x180012725  call    cs:__imp_wcsstr
0x18001272b  mov     rdi, rax
0x18001272e  test    rax, rax
0x180012731  jz      loc_1800129C8
0x180012737  lea     rdx, asc_18003A624; "*:"
0x18001273e  lea     rcx, [rbp+8A0h+var_920]; this
0x180012742  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180012747  mov     ebx, eax
0x180012749  test    eax, eax
0x18001274b  js      loc_1800129CD
0x180012751  lea     rdx, [rdi+2]; unsigned __int16 *
0x180012755  lea     rcx, [rbp+8A0h+var_920]; this
0x180012759  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001275e  mov     ebx, eax
0x180012760  test    eax, eax
0x180012762  js      loc_1800129CD
0x180012768  lea     rdx, asc_18003A620; ":"
0x18001276f  lea     rcx, [rbp+8A0h+var_920]; this
0x180012773  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180012778  mov     ebx, eax
0x18001277a  test    eax, eax
0x18001277c  js      loc_1800129CD
0x180012782  sub     rdi, r14
0x180012785  lea     rcx, [rbp+8A0h+var_920]; this
0x180012789  sar     rdi, 1
0x18001278c  mov     rdx, r14; unsigned __int16 *
0x18001278f  mov     r8d, edi; unsigned int
0x180012792  call    ?Append@STRU@@QEAAJPEBGK@Z; STRU::Append(ushort const *,ulong)
0x180012797  mov     ebx, eax
0x180012799  test    eax, eax
0x18001279b  js      loc_1800129CD
0x1800127a1  mov     edx, [rbp+8A0h+var_8F0]
0x1800127a4  cmp     edx, 2
0x1800127a7  jbe     short loc_1800127C2
0x1800127a9  mov     rax, [rbp+8A0h+var_900]
0x1800127ad  lea     ecx, [rdx-1]
0x1800127b0  cmp     word ptr [rax+rcx*2], 2Ah ; '*'
0x1800127b5  jnz     short loc_1800127C2
0x1800127b7  dec     edx; unsigned int
0x1800127b9  lea     rcx, [rbp+8A0h+var_920]; this
0x1800127bd  call    ?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x1800127c2  test    rsi, rsi
0x1800127c5  lea     rdi, [rsi+2]
0x1800127c9  cmovz   rdi, rsi
0x1800127cd  jmp     loc_180012886
0x1800127d2  lea     rdx, SubStr; "/"
0x1800127d9  mov     rcx, rdi; Str
0x1800127dc  call    cs:__imp_wcsstr
0x1800127e2  mov     r14, rax
0x1800127e5  test    rax, rax
0x1800127e8  jz      loc_1800129C8
0x1800127ee  cmp     rax, rdi
0x1800127f1  jz      loc_1800129C8
0x1800127f7  test    rsi, rsi
0x1800127fa  jz      short loc_180012805
0x1800127fc  cmp     rax, rsi
0x1800127ff  ja      loc_1800129C8
0x180012805  mov     r8, r14
0x180012808  mov     [r12], r13w
0x18001280d  sub     r8, rdi
0x180012810  mov     [rbp+8A0h+var_8B8], r13d
0x180012814  sar     r8, 1; unsigned int
0x180012817  lea     rcx, [rbp+8A0h+var_8E8]; this
0x18001281b  mov     rdx, rdi; unsigned __int16 *
0x18001281e  call    ?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180012823  mov     ebx, eax
0x180012825  test    eax, eax
0x180012827  js      loc_1800129CD
0x18001282d  lea     rdx, asc_18003991C; ","
0x180012834  mov     rcx, rdi; Str
0x180012837  call    cs:__imp_wcsstr
0x18001283d  lea     rdx, [r14+2]; unsigned __int16 *
0x180012841  mov     [rbp+8A0h+var_8F0], r13d
0x180012845  mov     rdi, rax
0x180012848  lea     rcx, [rbp+8A0h+var_920]; this
0x18001284c  mov     rax, [rbp+8A0h+var_900]
0x180012850  mov     [rax], r13w
0x180012854  test    rdi, rdi
0x180012857  jz      short loc_180012877
0x180012859  mov     r8, rdi
0x18001285c  sub     r8, rdx
0x18001285f  sar     r8, 1; unsigned int
0x180012862  call    ?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180012867  mov     ebx, eax
0x180012869  test    eax, eax
0x18001286b  js      loc_1800129CD
0x180012871  add     rdi, 2
0x180012875  jmp     short loc_180012886
0x180012877  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001287c  mov     ebx, eax
0x18001287e  test    eax, eax
0x180012880  js      loc_1800129CD
0x180012886  mov     rcx, [rsp+9A0h+var_968]
0x18001288b  lea     rsi, aBinding_0; "binding"
0x180012892  lea     r8, [rsp+9A0h+var_958]
0x180012897  mov     rdx, rsi
0x18001289a  mov     rax, [rcx]
0x18001289d  mov     rax, [rax+30h]
0x1800128a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128a6  mov     ebx, eax
0x1800128a8  test    eax, eax
0x1800128aa  js      loc_180012A10
0x1800128b0  mov     rax, [r15]
0x1800128b3  lea     r8, aProtocol; "protocol"
0x1800128ba  mov     r12, [rbp+8A0h+var_8C8]
0x1800128be  mov     rcx, r15
0x1800128c1  mov     rdx, [rsp+9A0h+var_958]
0x1800128c6  mov     r9, r12
0x1800128c9  mov     rax, [rax+60h]
0x1800128cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128d2  mov     ebx, eax
0x1800128d4  test    eax, eax
0x1800128d6  js      loc_180012A10
0x1800128dc  mov     rax, [r15]
0x1800128df  lea     r8, aBindinginforma; "bindingInformation"
0x1800128e6  mov     r9, [rbp+8A0h+var_900]
0x1800128ea  mov     rcx, r15
0x1800128ed  mov     rdx, [rsp+9A0h+var_958]
0x1800128f2  mov     rax, [rax+60h]
0x1800128f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128fb  mov     ebx, eax
0x1800128fd  test    eax, eax
0x1800128ff  js      loc_180012A10
0x180012905  mov     rcx, [rsp+9A0h+var_968]
  ... truncated ...
```
