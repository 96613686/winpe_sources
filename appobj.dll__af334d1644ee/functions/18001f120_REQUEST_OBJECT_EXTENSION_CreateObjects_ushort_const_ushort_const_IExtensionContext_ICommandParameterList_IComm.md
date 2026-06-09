# REQUEST_OBJECT_EXTENSION::CreateObjects(ushort const *,ushort const *,IExtensionContext *,ICommandParameterList *,ICommandObjectList *)

- ea: `0x18001f120`
- end: `0x18001f9fa`
- name: `?CreateObjects@REQUEST_OBJECT_EXTENSION@@UEAAJPEBG0PEAVIExtensionContext@@PEAVICommandParameterList@@PEAVICommandObjectList@@@Z`
- size: `2266`
- prototype: `__int64 __fastcall(REQUEST_OBJECT_EXTENSION *this, const unsigned __int16 *, char *, struct IExtensionContext *, struct ICommandParameterList *, struct ICommandObjectList *)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180001044`
- `0x180001fb0`
- `0x180005440`
- `0x180005ba8`
- `0x18001ed98`
- `0x18001f120`
- `0x18002b564`
- `0x18002bd3c`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!wcstoul` at `0x18001f4fc`
- `msvcrt!wcstoul` at `0x18001f4fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f85f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f8b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f85f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f8b2`

## pseudocode

```c
__int64 __fastcall REQUEST_OBJECT_EXTENSION::CreateObjects(
        REQUEST_OBJECT_EXTENSION *this,
        const unsigned __int16 *a2,
        char *a3,
        struct IExtensionContext *a4,
        struct ICommandParameterList *a5,
        struct ICommandObjectList *a6)
{
  COMMAND_OBJECT *v9; // rdi
  unsigned int v10; // r12d
  __int64 v11; // rcx
  int v12; // ebx
  int v13; // eax
  int v14; // eax
  APP_OBJECT_UTILS *v15; // rcx
  bool v16; // zf
  int v17; // eax
  unsigned int v18; // r15d
  int v19; // eax
  int v20; // eax
  COMMAND_OBJECT *v21; // rax
  __int64 v22; // r9
  unsigned __int16 *v23; // rax
  int v24; // edx
  int v25; // ecx
  int v26; // eax
  struct ICommandParameterList *v28; // [rsp+40h] [rbp-C0h] BYREF
  int v29; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v30; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v32; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v33; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v34; // [rsp+70h] [rbp-90h] BYREF
  int v35; // [rsp+74h] [rbp-8Ch] BYREF
  __int64 v36; // [rsp+78h] [rbp-88h] BYREF
  __int64 v37; // [rsp+80h] [rbp-80h] BYREF
  __int64 v38; // [rsp+88h] [rbp-78h] BYREF
  __int64 v39; // [rsp+90h] [rbp-70h] BYREF
  __int64 v40; // [rsp+98h] [rbp-68h] BYREF
  __int64 v41; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v42; // [rsp+A8h] [rbp-58h] BYREF
  char *v43; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v44[32]; // [rsp+B8h] [rbp-48h] BYREF
  __int16 *v45; // [rsp+D8h] [rbp-28h]
  int v46; // [rsp+E0h] [rbp-20h]
  __int16 v47; // [rsp+E4h] [rbp-1Ch]
  int v48; // [rsp+E8h] [rbp-18h]
  _BYTE v49[32]; // [rsp+F0h] [rbp-10h] BYREF
  __int16 *v50; // [rsp+110h] [rbp+10h]
  int v51; // [rsp+118h] [rbp+18h]
  __int16 v52; // [rsp+11Ch] [rbp+1Ch]
  int v53; // [rsp+120h] [rbp+20h]
  _BYTE v54[32]; // [rsp+128h] [rbp+28h] BYREF
  __int16 *v55; // [rsp+148h] [rbp+48h]
  int v56; // [rsp+150h] [rbp+50h]
  __int16 v57; // [rsp+154h] [rbp+54h]
  int v58; // [rsp+158h] [rbp+58h]
  _BYTE v59[32]; // [rsp+160h] [rbp+60h] BYREF
  const unsigned __int16 *v60; // [rsp+180h] [rbp+80h]
  int v61; // [rsp+188h] [rbp+88h]
  __int16 v62; // [rsp+18Ch] [rbp+8Ch]
  int v63; // [rsp+190h] [rbp+90h]
  _BYTE v64[32]; // [rsp+198h] [rbp+98h] BYREF
  wchar_t *String; // [rsp+1B8h] [rbp+B8h]
  int v66; // [rsp+1C0h] [rbp+C0h]
  __int16 v67; // [rsp+1C4h] [rbp+C4h]
  int v68; // [rsp+1C8h] [rbp+C8h]
  __int16 v69; // [rsp+1D0h] [rbp+D0h] BYREF
  char v70[126]; // [rsp+1D2h] [rbp+D2h] BYREF
  __int16 v71; // [rsp+250h] [rbp+150h] BYREF
  char v72[126]; // [rsp+252h] [rbp+152h] BYREF
  __int16 v73; // [rsp+2D0h] [rbp+1D0h] BYREF
  char v74[510]; // [rsp+2D2h] [rbp+1D2h] BYREF
  __int16 v75; // [rsp+4D0h] [rbp+3D0h] BYREF
  char v76[510]; // [rsp+4D2h] [rbp+3D2h] BYREF
  __int16 v77; // [rsp+6D0h] [rbp+5D0h] BYREF
  char v78[510]; // [rsp+6D2h] [rbp+5D2h] BYREF

  v29 = 0;
  v34 = 0;
  v30 = 0;
  v33 = 0;
  v36 = 0;
  v9 = 0;
  memset_0(v70, 0, sizeof(v70));
  v67 = 256;
  v68 = 0;
  v69 = 0;
  v35 = 0;
  v37 = 0;
  v41 = 0;
  v32 = 0;
  v42 = 0;
  String = (wchar_t *)&v69;
  v66 = 128;
  memset_0(v74, 0, sizeof(v74));
  v61 = 512;
  v60 = (const unsigned __int16 *)&v73;
  v62 = 256;
  v63 = 0;
  v73 = 0;
  memset_0(v72, 0, sizeof(v72));
  v56 = 128;
  v55 = &v71;
  v57 = 256;
  v58 = 0;
  v71 = 0;
  memset_0(v76, 0, sizeof(v76));
  v47 = 256;
  v46 = 512;
  v45 = &v75;
  v48 = 0;
  v75 = 0;
  memset_0(v78, 0, sizeof(v78));
  v51 = 512;
  v10 = 0;
  v50 = &v77;
  v53 = 0;
  v77 = 0;
  pv = 0;
  v28 = 0;
  v38 = 0;
  v43 = 0;
  v39 = 0;
  v40 = 0;
  v52 = 256;
  if ( !a2 || !a3 || !a4 || !a5 || !a6 )
  {
    v12 = -2147024809;
    goto LABEL_68;
  }
  v12 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, struct ICommandParameterList **))(*(_QWORD *)a5 + 80LL))(
          a5,
          &v28);
  if ( v12 < 0 )
    goto LABEL_68;
  if ( !*(_WORD *)a3 )
  {
    v13 = APP_OBJECT_UTILS::PopParameter((APP_OBJECT_UTILS *)v11, a4, v28, L"REQUEST.NAME", (struct STRU *)v59, 0, 1);
    v11 = 0x80000000LL;
    v12 = v13;
    if ( (int)(v13 + 0x80000000) >= 0 && v13 != -2147023483 )
      goto LABEL_68;
    a3 = (char *)v60;
  }
  v14 = APP_OBJECT_UTILS::PopParameter((APP_OBJECT_UTILS *)v11, a4, v28, L"SITE.NAME", (struct STRU *)v49, 0, 1);
  v12 = v14;
  if ( v14 >= 0 )
  {
    v17 = (*(__int64 (__fastcall **)(struct IExtensionContext *, const unsigned __int16 *, __int16 *, __int64 *, int))(*(_QWORD *)a4 + 64LL))(
            a4,
            L"SITE",
            v50,
            &v39,
            4);
    v12 = v17;
    if ( v17 >= 0 )
    {
      v12 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64 *))(*(_QWORD *)v39 + 80LL))(
              v39,
              L"SITE.ID",
              &v40);
      if ( v12 < 0 )
        goto LABEL_68;
      v12 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, const unsigned __int16 *, __int64))(*(_QWORD *)v28 + 56LL))(
              v28,
              L"SITE.ID",
              v40);
      if ( v12 < 0 )
        goto LABEL_68;
      goto LABEL_19;
    }
    v16 = v17 == -2147023728;
  }
  else
  {
    v16 = v14 == -2147023483;
  }
  if ( !v16 )
    goto LABEL_68;
LABEL_19:
  v12 = APP_OBJECT_UTILS::PopParameter(v15, a4, v28, L"WP.NAME", (struct STRU *)v54, 0, 1);
  if ( (int)(v12 + 0x80000000) < 0 || v12 == -2147023483 )
  {
    v12 = APP_OBJECT_UTILS::PopParameter(
            (APP_OBJECT_UTILS *)0x80000000LL,
            a4,
            v28,
            L"APPPOOL.NAME",
            (struct STRU *)v44,
            0,
            1);
    if ( (int)(v12 + 0x80000000) < 0 || v12 == -2147023483 )
    {
      v18 = 0;
      if ( *(_WORD *)a3 )
      {
        v12 = APP_OBJECT_UTILS::ValidateEmptyParameters((APP_OBJECT_UTILS *)0x80000000LL, a4, v28);
        if ( v12 < 0 )
          goto LABEL_68;
      }
      else
      {
        v19 = APP_OBJECT_UTILS::PopParameter(
                (APP_OBJECT_UTILS *)0x80000000LL,
                a4,
                v28,
                L"elapsed",
                (struct STRU *)v64,
                0,
                1);
        v12 = v19;
        if ( v19 < 0 )
        {
          if ( v19 != -2147023483 )
            goto LABEL_68;
        }
        else
        {
          v10 = wcstoul(String, 0, 10);
        }
      }
      v12 = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64 *))(*(_QWORD *)a4 + 192LL))(a4, &v38);
      if ( v12 >= 0 )
      {
        if ( !v48
          || (v12 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int16 *))(*(_QWORD *)v38 + 56LL))(
                      v38,
                      L"APPPOOL.NAME",
                      v45),
              v12 >= 0) )
        {
          v12 = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64 *))(*(_QWORD *)a4 + 184LL))(a4, &v33);
          if ( v12 >= 0 )
          {
            v12 = (*(__int64 (__fastcall **)(struct IExtensionContext *, const unsigned __int16 *, __int16 *, __int64, __int64, _DWORD))(*(_QWORD *)a4 + 56LL))(
                    a4,
                    L"WP",
                    v55,
                    v38,
                    v33,
                    0);
            if ( v12 >= 0 )
            {
              (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v33 + 32LL))(v33, &v34);
              while ( 1 )
              {
                if ( v18 >= v34 )
                  goto LABEL_68;
                v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v33 + 40LL))(v33, v18, &v30);
                if ( v12 < 0 )
                  goto LABEL_68;
                if ( !v30 )
                  goto LABEL_66;
                v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v30 + 96LL))(v30, &v36);
                if ( v12 < 0 )
                  goto LABEL_68;
                if ( !v36 )
                {
LABEL_66:
                  v12 = -2147467259;
                  goto LABEL_68;
                }
                v12 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v36 + 56LL))(v36, &pv);
                if ( v12 < 0 )
                  goto LABEL_68;
                v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, int *, __int64 *))(*(_QWORD *)v36 + 64LL))(
                        v36,
                        v10,
                        &v35,
                        &v37);
                if ( v12 < 0 )
                  goto LABEL_68;
                if ( v35 )
                  break;
LABEL_64:
                CoTaskMemFree(pv);
                pv = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
                ++v18;
                v30 = 0;
              }
              v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v37 + 32LL))(v37, &v41);
              if ( v12 >= 0 )
              {
                while ( 1 )
                {
                  v20 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v37 + 24LL))(v37, v41, &v32);
                  v12 = v20;
                  if ( v20 < 0 )
                    goto LABEL_68;
                  if ( v20 )
                    goto LABEL_64;
                  v21 = (COMMAND_OBJECT *)operator new(0xE0u);
                  v9 = v21;
                  if ( !v21 )
                  {
                    v12 = -2147024888;
                    v9 = 0;
                    goto LABEL_68;
                  }
                  COMMAND_OBJECT::COMMAND_OBJECT(v21);
                  *((_QWORD *)v9 + 27) = v22;
                  *(_QWORD *)v9 = &REQUEST_OBJECT::`vftable';
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 8LL))(v22);
                  v12 = REQUEST_OBJECT::Create(v9);
                  if ( v12 < 0 )
                    goto LABEL_68;
                  v12 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, unsigned __int16 **))(*(_QWORD *)v30 + 80LL))(
                          v30,
                          L"WP.NAME",
                          &v42);
                  if ( v12 < 0 )
                    goto LABEL_68;
                  v12 = COMMAND_OBJECT::AddAttribute(v9, L"WP.NAME", v42);
                  if ( v12 < 0 )
                    goto LABEL_68;
                  v12 = COMMAND_OBJECT::AddAttribute(v9, L"APPPOOL.NAME", (const unsigned __int16 *)pv);
                  if ( v12 < 0 )
                    goto LABEL_68;
                  v29 = 0;
                  if ( !*(_WORD *)a3 )
                    break;
                  v12 = (*(__int64 (__fastcall **)(COMMAND_OBJECT *, const unsigned __int16 *, char **))(*(_QWORD *)v9 + 80LL))(
                          v9,
                          L"REQUEST.NAME",
                          &v43);
                  if ( v12 < 0 )
                    goto LABEL_68;
                  v23 = (unsigned __int16 *)v43;
                  do
                  {
                    v24 = *(unsigned __int16 *)((char *)v23 + a3 - v43);
                    v25 = *v23 - v24;
                    if ( v25 )
                      break;
                    ++v23;
                  }
                  while ( v24 );
                  if ( v25 )
                    goto LABEL_59;
                  v26 = 1;
                  v29 = 1;
LABEL_60:
                  if ( v26 )
                  {
                    v12 = (*(__int64 (__fastcall **)(struct ICommandObjectList *, COMMAND_OBJECT *))(*(_QWORD *)a6 + 24LL))(
                            a6,
                            v9);
                    if ( v12 < 0 )
                      goto LABEL_68;
                    if ( *(_WORD *)a3 )
                      goto LABEL_64;
                  }
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
                  v32 = 0;
                }
                v12 = (*(__int64 (__fastcall **)(struct IExtensionContext *, COMMAND_OBJECT *, struct ICommandParameterList *, int *))(*(_QWORD *)a4 + 152LL))(
                        a4,
                        v9,
                        v28,
                        &v29);
                if ( v12 < 0 )
                  goto LABEL_68;
LABEL_59:
                v26 = v29;
                goto LABEL_60;
              }
            }
          }
        }
      }
    }
  }
LABEL_68:
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v32 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    v32 = 0;
  }
  if ( v9 )
    (*(void (__fastcall **)(COMMAND_OBJECT *))(*(_QWORD *)v9 + 16LL))(v9);
  if ( v33 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    v33 = 0;
  }
  if ( v30 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    v30 = 0;
  }
  if ( v36 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    v36 = 0;
  }
  if ( v37 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    v37 = 0;
  }
  if ( v28 )
  {
    (*(void (__fastcall **)(struct ICommandParameterList *))(*(_QWORD *)v28 + 16LL))(v28);
    v28 = 0;
  }
  if ( v38 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    v38 = 0;
  }
  if ( v39 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    v39 = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v49);
  BUFFER::~BUFFER((BUFFER *)v44);
  BUFFER::~BUFFER((BUFFER *)v54);
  BUFFER::~BUFFER((BUFFER *)v59);
  BUFFER::~BUFFER((BUFFER *)v64);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18001f120  push    rbp
0x18001f122  push    rbx
0x18001f123  push    rsi
0x18001f124  push    rdi
0x18001f125  push    r12
0x18001f127  push    r13
0x18001f129  push    r14
0x18001f12b  push    r15
0x18001f12d  lea     rbp, [rsp-7E8h]
0x18001f135  sub     rsp, 8E8h
0x18001f13c  mov     rax, cs:__security_cookie
0x18001f143  xor     rax, rsp
0x18001f146  mov     [rbp+820h+var_50], rax
0x18001f14d  mov     r15, [rbp+820h+arg_20]
0x18001f154  lea     rcx, [rbp+820h+var_74E]; void *
0x18001f15b  mov     r13, [rbp+820h+arg_28]
0x18001f162  xor     eax, eax
0x18001f164  mov     r14, r8
0x18001f167  mov     [rsp+920h+var_8D8], eax
0x18001f16b  mov     rbx, rdx
0x18001f16e  mov     [rsp+920h+var_8B0], eax
0x18001f172  xor     edx, edx; Val
0x18001f174  mov     [rsp+920h+var_8D0], rax
0x18001f179  lea     r8d, [rax+7Eh]; Size
0x18001f17d  mov     [rsp+920h+var_8B8], rax
0x18001f182  mov     rsi, r9
0x18001f185  mov     [rsp+920h+var_8A8], rax
0x18001f18a  mov     edi, eax
0x18001f18c  call    memset_0
0x18001f191  xor     ecx, ecx
0x18001f193  mov     [rbp+820h+var_75C], 100h
0x18001f19c  mov     [rbp+820h+var_758], ecx
0x18001f1a2  lea     rax, [rbp+820h+var_750]
0x18001f1a9  mov     [rbp+820h+var_750], cx
0x18001f1b0  mov     r12d, 80h
0x18001f1b6  mov     [rsp+920h+var_8AC], ecx
0x18001f1ba  xor     edx, edx; Val
0x18001f1bc  mov     [rbp+820h+var_8A0], rcx
0x18001f1c0  mov     r8d, 1FEh; Size
0x18001f1c6  mov     [rbp+820h+var_880], rcx
0x18001f1ca  mov     [rsp+920h+var_8C0], rcx
0x18001f1cf  mov     [rbp+820h+var_878], rcx
0x18001f1d3  lea     rcx, [rbp+820h+var_64E]; void *
0x18001f1da  mov     [rbp+820h+String], rax
0x18001f1e1  mov     [rbp+820h+var_760], r12d
0x18001f1e8  call    memset_0
0x18001f1ed  lea     rax, [rbp+820h+var_650]
0x18001f1f4  mov     [rbp+820h+var_798], 200h
0x18001f1fe  mov     [rbp+820h+var_7A0], rax
0x18001f205  lea     r8d, [rdi+7Eh]; Size
0x18001f209  xor     eax, eax
0x18001f20b  mov     [rbp+820h+var_794], 100h
0x18001f214  xor     edx, edx; Val
0x18001f216  mov     [rbp+820h+var_790], eax
0x18001f21c  lea     rcx, [rbp+820h+var_6CE]; void *
0x18001f223  mov     [rbp+820h+var_650], ax
0x18001f22a  call    memset_0
0x18001f22f  lea     rax, [rbp+820h+var_6D0]
0x18001f236  mov     [rbp+820h+var_7D0], r12d
0x18001f23a  mov     [rbp+820h+var_7D8], rax
0x18001f23e  lea     rcx, [rbp+820h+var_44E]; void *
0x18001f245  xor     eax, eax
0x18001f247  mov     [rbp+820h+var_7CC], 100h
0x18001f24d  xor     edx, edx; Val
0x18001f24f  mov     [rbp+820h+var_7C8], eax
0x18001f252  mov     r8d, 1FEh; Size
0x18001f258  mov     [rbp+820h+var_6D0], ax
0x18001f25f  call    memset_0
0x18001f264  mov     r12d, 200h
0x18001f26a  mov     [rbp+820h+var_83C], 100h
0x18001f270  lea     rax, [rbp+820h+var_450]
0x18001f277  mov     [rbp+820h+var_840], r12d
0x18001f27b  mov     [rbp+820h+var_848], rax
0x18001f27f  lea     rcx, [rbp+820h+var_24E]; void *
0x18001f286  xor     eax, eax
0x18001f288  xor     edx, edx; Val
0x18001f28a  lea     r8d, [r12-2]; Size
0x18001f28f  mov     [rbp+820h+var_838], eax
0x18001f292  mov     [rbp+820h+var_450], ax
0x18001f299  call    memset_0
0x18001f29e  mov     [rbp+820h+var_808], r12d
0x18001f2a2  lea     rax, [rbp+820h+var_250]
0x18001f2a9  xor     r12d, r12d
0x18001f2ac  mov     [rbp+820h+var_810], rax
0x18001f2b0  mov     [rbp+820h+var_800], r12d
0x18001f2b4  test    rbx, rbx
0x18001f2b7  mov     [rbp+820h+var_250], r12w
0x18001f2bf  mov     [rsp+920h+pv], r12
0x18001f2c4  mov     [rsp+920h+var_8E0], r12
0x18001f2c9  mov     [rbp+820h+var_898], r12
0x18001f2cd  mov     [rbp+820h+var_870], r12
0x18001f2d1  mov     [rbp+820h+var_890], r12
0x18001f2d5  mov     [rbp+820h+var_888], r12
0x18001f2d9  mov     [rbp+820h+var_804], 100h
0x18001f2df  jz      loc_18001F8A1
0x18001f2e5  test    r14, r14
0x18001f2e8  jz      loc_18001F8A1
0x18001f2ee  test    rsi, rsi
0x18001f2f1  jz      loc_18001F8A1
0x18001f2f7  test    r15, r15
0x18001f2fa  jz      loc_18001F8A1
0x18001f300  test    r13, r13
0x18001f303  jz      loc_18001F8A1
0x18001f309  mov     rax, [r15]
0x18001f30c  lea     rdx, [rsp+920h+var_8E0]
0x18001f311  mov     rcx, r15
0x18001f314  mov     rax, [rax+50h]
0x18001f318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f31d  mov     ebx, eax
0x18001f31f  test    eax, eax
0x18001f321  js      loc_18001F8A6
0x18001f327  mov     r15d, 80070585h
0x18001f32d  cmp     [r14], r12w
0x18001f331  jnz     short loc_18001F37A
0x18001f333  mov     r8, [rsp+920h+var_8E0]; struct ICommandParameterList *
0x18001f338  lea     rax, [rbp+820h+var_7C0]
0x18001f33c  mov     [rsp+920h+var_8F0], 1; int
0x18001f344  lea     r9, aRequestName; "REQUEST.NAME"
0x18001f34b  mov     [rsp+920h+var_8F8], r12d; int
0x18001f350  mov     rdx, rsi; struct IExtensionContext *
0x18001f353  mov     [rsp+920h+var_900], rax; struct STRU *
0x18001f358  call    ?PopParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAVSTRU@@HH@Z; APP_OBJECT_UTILS::PopParameter(IExtensionContext *,ICommandParameterList *,ushort const *,STRU *,int,int)
0x18001f35d  mov     ecx, 80000000h; this
0x18001f362  mov     ebx, eax
0x18001f364  add     eax, ecx
0x18001f366  test    ecx, eax
0x18001f368  jnz     short loc_18001F373
0x18001f36a  cmp     ebx, r15d
0x18001f36d  jnz     loc_18001F8A6
0x18001f373  mov     r14, [rbp+820h+var_7A0]
0x18001f37a  mov     r8, [rsp+920h+var_8E0]; struct ICommandParameterList *
0x18001f37f  lea     rax, [rbp+820h+var_830]
0x18001f383  mov     [rsp+920h+var_8F0], 1; int
0x18001f38b  lea     r9, aSiteName; "SITE.NAME"
0x18001f392  mov     [rsp+920h+var_8F8], r12d; int
0x18001f397  mov     rdx, rsi; struct IExtensionContext *
0x18001f39a  mov     [rsp+920h+var_900], rax; struct STRU *
0x18001f39f  call    ?PopParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAVSTRU@@HH@Z; APP_OBJECT_UTILS::PopParameter(IExtensionContext *,ICommandParameterList *,ushort const *,STRU *,int,int)
0x18001f3a4  mov     ebx, eax
0x18001f3a6  test    eax, eax
0x18001f3a8  jns     short loc_18001F3AF
0x18001f3aa  cmp     eax, r15d
0x18001f3ad  jmp     short loc_18001F3E0
0x18001f3af  mov     rax, [rsi]
0x18001f3b2  lea     r9, [rbp+820h+var_890]
0x18001f3b6  mov     r8, [rbp+820h+var_810]
0x18001f3ba  lea     rdx, aSite_0; "SITE"
0x18001f3c1  mov     rcx, rsi
0x18001f3c4  mov     dword ptr [rsp+920h+var_900], 4
0x18001f3cc  mov     rax, [rax+40h]
0x18001f3d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f3d5  mov     ebx, eax
0x18001f3d7  test    eax, eax
0x18001f3d9  jns     short loc_18001F3E8
0x18001f3db  cmp     eax, 80070490h
0x18001f3e0  jnz     loc_18001F8A6
0x18001f3e6  jmp     short loc_18001F433
0x18001f3e8  mov     rcx, [rbp+820h+var_890]
0x18001f3ec  lea     r8, [rbp+820h+var_888]
0x18001f3f0  lea     rdx, aSiteId; "SITE.ID"
0x18001f3f7  mov     rax, [rcx]
0x18001f3fa  mov     rax, [rax+50h]
0x18001f3fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f403  mov     ebx, eax
0x18001f405  test    eax, eax
0x18001f407  js      loc_18001F8A6
0x18001f40d  mov     rcx, [rsp+920h+var_8E0]
0x18001f412  lea     rdx, aSiteId; "SITE.ID"
0x18001f419  mov     r8, [rbp+820h+var_888]
0x18001f41d  mov     rax, [rcx]
0x18001f420  mov     rax, [rax+38h]
0x18001f424  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f429  mov     ebx, eax
0x18001f42b  test    eax, eax
0x18001f42d  js      loc_18001F8A6
0x18001f433  mov     r8, [rsp+920h+var_8E0]; struct ICommandParameterList *
0x18001f438  lea     rax, [rbp+820h+var_7F8]
0x18001f43c  mov     [rsp+920h+var_8F0], 1; int
0x18001f444  lea     r9, aWpName_0; "WP.NAME"
0x18001f44b  mov     [rsp+920h+var_8F8], r12d; int
0x18001f450  mov     rdx, rsi; struct IExtensionContext *
0x18001f453  mov     [rsp+920h+var_900], rax; struct STRU *
0x18001f458  call    ?PopParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAVSTRU@@HH@Z; APP_OBJECT_UTILS::PopParameter(IExtensionContext *,ICommandParameterList *,ushort const *,STRU *,int,int)
0x18001f45d  mov     ecx, 80000000h; this
0x18001f462  mov     ebx, eax
0x18001f464  add     eax, ecx
0x18001f466  test    ecx, eax
0x18001f468  jnz     short loc_18001F473
0x18001f46a  cmp     ebx, r15d
0x18001f46d  jnz     loc_18001F8A6
0x18001f473  mov     r8, [rsp+920h+var_8E0]; struct ICommandParameterList *
0x18001f478  lea     rax, [rbp+820h+var_868]
0x18001f47c  mov     [rsp+920h+var_8F0], 1; int
0x18001f484  lea     r9, aApppoolName; "APPPOOL.NAME"
0x18001f48b  mov     [rsp+920h+var_8F8], r12d; int
0x18001f490  mov     rdx, rsi; struct IExtensionContext *
0x18001f493  mov     [rsp+920h+var_900], rax; struct STRU *
0x18001f498  call    ?PopParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAVSTRU@@HH@Z; APP_OBJECT_UTILS::PopParameter(IExtensionContext *,ICommandParameterList *,ushort const *,STRU *,int,int)
0x18001f49d  mov     ecx, 80000000h; this
0x18001f4a2  mov     ebx, eax
0x18001f4a4  add     eax, ecx
0x18001f4a6  test    ecx, eax
0x18001f4a8  jnz     short loc_18001F4B3
0x18001f4aa  cmp     ebx, r15d
0x18001f4ad  jnz     loc_18001F8A6
0x18001f4b3  mov     r8, [rsp+920h+var_8E0]; struct ICommandParameterList *
0x18001f4b8  xor     r15d, r15d
0x18001f4bb  mov     rdx, rsi; struct IExtensionContext *
0x18001f4be  cmp     [r14], r15w
0x18001f4c2  jnz     short loc_18001F514
0x18001f4c4  mov     [rsp+920h+var_8F0], 1; int
0x18001f4cc  lea     rax, [rbp+820h+var_788]
0x18001f4d3  mov     [rsp+920h+var_8F8], r15d; int
0x18001f4d8  lea     r9, aElapsed; "elapsed"
0x18001f4df  mov     [rsp+920h+var_900], rax; struct STRU *
0x18001f4e4  call    ?PopParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAVSTRU@@HH@Z; APP_OBJECT_UTILS::PopParameter(IExtensionContext *,ICommandParameterList *,ushort const *,STRU *,int,int)
0x18001f4e9  mov     ebx, eax
0x18001f4eb  test    eax, eax
0x18001f4ed  js      short loc_18001F507
0x18001f4ef  mov     rcx, [rbp+820h+String]; String
0x18001f4f6  lea     r8d, [r15+0Ah]; Radix
0x18001f4fa  xor     edx, edx; EndPtr
0x18001f4fc  call    cs:__imp_wcstoul
0x18001f502  mov     r12d, eax
0x18001f505  jmp     short loc_18001F523
0x18001f507  cmp     eax, 80070585h
0x18001f50c  jnz     loc_18001F8A6
0x18001f512  jmp     short loc_18001F523
0x18001f514  call    ?ValidateEmptyParameters@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@@Z; APP_OBJECT_UTILS::ValidateEmptyParameters(IExtensionContext *,ICommandParameterList *)
0x18001f519  mov     ebx, eax
0x18001f51b  test    eax, eax
0x18001f51d  js      loc_18001F8A6
0x18001f523  mov     rax, [rsi]
0x18001f526  lea     rdx, [rbp+820h+var_898]
0x18001f52a  mov     rcx, rsi
0x18001f52d  mov     rax, [rax+0C0h]
0x18001f534  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f539  mov     ebx, eax
0x18001f53b  test    eax, eax
0x18001f53d  js      loc_18001F8A6
0x18001f543  cmp     [rbp+820h+var_838], r15d
0x18001f547  jz      short loc_18001F56E
0x18001f549  mov     rcx, [rbp+820h+var_898]
0x18001f54d  lea     rdx, aApppoolName; "APPPOOL.NAME"
0x18001f554  mov     r8, [rbp+820h+var_848]
0x18001f558  mov     rax, [rcx]
0x18001f55b  mov     rax, [rax+38h]
0x18001f55f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f564  mov     ebx, eax
0x18001f566  test    eax, eax
0x18001f568  js      loc_18001F8A6
0x18001f56e  mov     rax, [rsi]
0x18001f571  lea     rdx, [rsp+920h+var_8B8]
0x18001f576  mov     rcx, rsi
0x18001f579  mov     rax, [rax+0B8h]
0x18001f580  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f585  mov     ebx, eax
0x18001f587  test    eax, eax
0x18001f589  js      loc_18001F8A6
0x18001f58f  mov     rcx, [rsp+920h+var_8B8]
0x18001f594  lea     rdx, aWp; "WP"
0x18001f59b  mov     rax, [rsi]
0x18001f59e  mov     r9, [rbp+820h+var_898]
0x18001f5a2  mov     r8, [rbp+820h+var_7D8]
0x18001f5a6  mov     [rsp+920h+var_8F8], r15d
0x18001f5ab  mov     rax, [rax+38h]
0x18001f5af  mov     [rsp+920h+var_900], rcx
0x18001f5b4  mov     rcx, rsi
0x18001f5b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f5bc  mov     ebx, eax
0x18001f5be  test    eax, eax
0x18001f5c0  js      loc_18001F8A6
0x18001f5c6  mov     rcx, [rsp+920h+var_8B8]
0x18001f5cb  lea     rdx, [rsp+920h+var_8B0]
0x18001f5d0  mov     rax, [rcx]
0x18001f5d3  mov     rax, [rax+20h]
0x18001f5d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f5dc  cmp     r15d, [rsp+920h+var_8B0]
0x18001f5e1  jnb     loc_18001F8A6
0x18001f5e7  mov     rcx, [rsp+920h+var_8B8]
0x18001f5ec  lea     r8, [rsp+920h+var_8D0]
0x18001f5f1  mov     edx, r15d
0x18001f5f4  mov     rax, [rcx]
0x18001f5f7  mov     rax, [rax+28h]
0x18001f5fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f600  mov     ebx, eax
0x18001f602  test    eax, eax
0x18001f604  js      loc_18001F8A6
0x18001f60a  mov     rcx, [rsp+920h+var_8D0]
0x18001f60f  test    rcx, rcx
0x18001f612  jz      loc_18001F89A
0x18001f618  mov     rax, [rcx]
0x18001f61b  lea     rdx, [rsp+920h+var_8A8]
0x18001f620  mov     rax, [rax+60h]
0x18001f624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f629  mov     ebx, eax
0x18001f62b  test    eax, eax
0x18001f62d  js      loc_18001F8A6
0x18001f633  mov     rcx, [rsp+920h+var_8A8]
0x18001f638  test    rcx, rcx
  ... truncated ...
```
