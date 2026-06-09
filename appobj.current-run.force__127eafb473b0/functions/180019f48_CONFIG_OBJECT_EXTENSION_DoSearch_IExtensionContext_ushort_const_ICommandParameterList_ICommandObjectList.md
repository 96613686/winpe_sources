# CONFIG_OBJECT_EXTENSION::DoSearch(IExtensionContext *,ushort const *,ICommandParameterList *,ICommandObjectList *)

- ea: `0x180019f48`
- end: `0x18001a841`
- name: `?DoSearch@CONFIG_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEBGPEAVICommandParameterList@@PEAVICommandObjectList@@@Z`
- size: `2297`
- prototype: `int(CONFIG_OBJECT_EXTENSION *__hidden this, struct IExtensionContext *, const unsigned __int16 *, struct ICommandParameterList *, struct ICommandObjectList *)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001a850`
- `0x18001b7e4`

## callees

- `0x180001044`
- `0x180001fb0`
- `0x180002640`
- `0x180002e90`
- `0x18001879c`
- `0x180018d80`
- `0x180019f48`
- `0x18001d714`
- `0x18002b564`
- `0x180034cbe`
- `0x180034cca`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!wcsstr` at `0x18001a1fc`
- `msvcrt!wcsstr` at `0x18001a1fc`
- `msvcrt!_wcsicmp` at `0x18001a112`
- `msvcrt!_wcsicmp` at `0x18001a3eb`
- `msvcrt!_wcsicmp` at `0x18001a4da`
- `msvcrt!_wcsicmp` at `0x18001a112`
- `msvcrt!_wcsicmp` at `0x18001a3eb`
- `msvcrt!_wcsicmp` at `0x18001a4da`

## pseudocode

```c
__int64 __fastcall CONFIG_OBJECT_EXTENSION::DoSearch(
        CONFIG_OBJECT_EXTENSION *this,
        struct IExtensionContext *a2,
        const unsigned __int16 *a3,
        struct ICommandParameterList *a4,
        struct ICommandObjectList *a5)
{
  int v5; // r13d
  CONFIG_SEARCH_OBJECT *v9; // rdi
  CONFIG_OBJECT_EXTENSION *v10; // rcx
  int v11; // ebx
  int v12; // eax
  wchar_t *v13; // r15
  CONFIG_OBJECT_EXTENSION *v14; // rcx
  char v15; // al
  const wchar_t *v16; // rdx
  __int64 v17; // r8
  unsigned int v18; // esi
  unsigned int i; // r12d
  unsigned int j; // r15d
  __int64 v21; // rax
  CONFIG_SEARCH_OBJECT *v22; // rax
  struct INativeConfigurationElement *v23; // rdx
  CONFIG_SEARCH_OBJECT *v24; // rax
  CONFIG_SEARCH_OBJECT *v25; // rax
  struct INativeConfigurationElement *v26; // rdx
  CONFIG_SEARCH_OBJECT *v27; // rax
  int v28; // eax
  int v30; // [rsp+40h] [rbp-C0h] BYREF
  struct INativeConfigSearchResult *v31; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v32; // [rsp+50h] [rbp-B0h] BYREF
  struct ICommandParameterList *v33; // [rsp+58h] [rbp-A8h] BYREF
  int v34; // [rsp+60h] [rbp-A0h] BYREF
  int v35; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v36; // [rsp+68h] [rbp-98h] BYREF
  int v37; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v38; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v39; // [rsp+78h] [rbp-88h] BYREF
  int v40; // [rsp+7Ch] [rbp-84h] BYREF
  int v41; // [rsp+80h] [rbp-80h]
  wchar_t *v42; // [rsp+88h] [rbp-78h] BYREF
  __int64 v43; // [rsp+90h] [rbp-70h] BYREF
  __int64 v44; // [rsp+98h] [rbp-68h] BYREF
  __int64 v45; // [rsp+A0h] [rbp-60h] BYREF
  const unsigned __int16 *v46; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v47; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t *String2; // [rsp+B8h] [rbp-48h] BYREF
  const unsigned __int16 *v49; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v50; // [rsp+C8h] [rbp-38h] BYREF
  wchar_t *v51; // [rsp+D0h] [rbp-30h] BYREF
  struct ICommandObjectList *v52; // [rsp+D8h] [rbp-28h]
  _BYTE v53[32]; // [rsp+E0h] [rbp-20h] BYREF
  wchar_t *String1; // [rsp+100h] [rbp+0h]
  int v55; // [rsp+108h] [rbp+8h]
  __int16 v56; // [rsp+10Ch] [rbp+Ch]
  int v57; // [rsp+110h] [rbp+10h]
  _BYTE v58[32]; // [rsp+118h] [rbp+18h] BYREF
  const unsigned __int16 *v59; // [rsp+138h] [rbp+38h]
  int v60; // [rsp+140h] [rbp+40h]
  __int16 v61; // [rsp+144h] [rbp+44h]
  int v62; // [rsp+148h] [rbp+48h]
  __int16 v63; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v64[510]; // [rsp+152h] [rbp+52h] BYREF
  __int16 v65; // [rsp+350h] [rbp+250h] BYREF
  _BYTE v66[510]; // [rsp+352h] [rbp+252h] BYREF
  wchar_t v67[512]; // [rsp+550h] [rbp+450h] BYREF

  v5 = 0;
  v52 = a5;
  v49 = 0;
  v51 = 0;
  v30 = 0;
  v40 = 512;
  v47 = 0;
  v43 = 0;
  v36 = 0;
  v9 = 0;
  v44 = 0;
  v46 = 0;
  v42 = 0;
  String2 = 0;
  v38 = 0;
  v39 = 0;
  v31 = 0;
  v32 = 0;
  v50 = 0;
  v35 = 0;
  v34 = 0;
  memset_0(v64, 0, sizeof(v64));
  v60 = 512;
  v59 = (const unsigned __int16 *)&v63;
  v61 = 256;
  v62 = 0;
  v63 = 0;
  v45 = 0;
  memset_0(v66, 0, sizeof(v66));
  v55 = 512;
  String1 = (wchar_t *)&v65;
  v56 = 256;
  v57 = 0;
  v65 = 0;
  v33 = 0;
  v37 = 0;
  if ( !a2 || !a4 || !a5 || !a3 )
  {
    v11 = -2147024809;
    goto LABEL_96;
  }
  v11 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, struct ICommandParameterList **))(*(_QWORD *)a4 + 80LL))(
          a4,
          &v33);
  if ( v11 < 0 )
    goto LABEL_96;
  v11 = CONFIG_OBJECT_EXTENSION::PopSectionNameFromParameters(v10, a2, v33, (const unsigned __int16 **)&v42, 0);
  if ( (int)(v11 + 0x80000000) >= 0 && v11 != -2147023483 )
    goto LABEL_96;
  v41 = 0;
  v12 = APP_OBJECT_UTILS::PopParameter((APP_OBJECT_UTILS *)0x80000000LL, a2, v33, L"status", (struct STRU *)v53, 0, 1);
  v11 = v12;
  if ( v12 < 0 )
  {
    if ( v12 != -2147023483 )
      goto LABEL_96;
    v13 = String1;
    goto LABEL_13;
  }
  v13 = String1;
  if ( _wcsicmp(String1, L"*") )
  {
LABEL_13:
    v5 = v57;
    goto LABEL_14;
  }
  v41 = 1;
  *v13 = 0;
  v57 = 0;
LABEL_14:
  if ( v42
    || (v11 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, int *))(*(_QWORD *)v33 + 24LL))(v33, &v37),
        v11 >= 0)
    && (!v37
     || (v11 = CONFIG_OBJECT_EXTENSION::PopSectionNameFromParameters(v14, a2, v33, (const unsigned __int16 **)&v42, 1),
         v11 >= 0)) )
  {
    if ( (*(unsigned int (__fastcall **)(struct IExtensionContext *))(*(_QWORD *)a2 + 40LL))(a2) == 1
      || (v15 = (*(__int64 (__fastcall **)(struct IExtensionContext *))(*(_QWORD *)a2 + 32LL))(a2),
          v16 = L"MACHINE/WEBROOT/APPHOST",
          (v15 & 8) != 0) )
    {
      v16 = &Str;
    }
    v11 = (*(__int64 (__fastcall **)(struct IExtensionContext *, const wchar_t *, __int64 *))(*(_QWORD *)a2 + 80LL))(
            a2,
            v16,
            &v43);
    if ( v11 >= 0 )
    {
      if ( *a3 )
      {
        if ( !wcsstr(a3, L"MACHINE/") && wcscmp_0(a3, L"MACHINE") )
        {
          v11 = STRU::Copy((STRU *)v58, L"MACHINE/WEBROOT/APPHOST");
          if ( v11 < 0 )
            goto LABEL_96;
          while ( *a3 == 47 )
            ++a3;
          v11 = STRU::Append((STRU *)v58, L"/");
          if ( v11 < 0 )
            goto LABEL_96;
          v11 = STRU::Append((STRU *)v58, a3);
          if ( v11 < 0 )
            goto LABEL_96;
          a3 = v59;
        }
      }
      else
      {
        a3 = L"MACHINE/WEBROOT/APPHOST";
      }
      v11 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64 *))(*(_QWORD *)v43 + 104LL))(
              v43,
              a3,
              &v44);
      if ( v11 < 0 )
      {
        v46 = a3;
        v17 = 3221226510LL;
        goto LABEL_35;
      }
      v18 = 0;
      v11 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v44 + 24LL))(v44, &v38);
      if ( v11 >= 0 )
      {
        v11 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, unsigned int *))(*(_QWORD *)v33 + 24LL))(
                v33,
                &v32);
        if ( v11 >= 0 )
        {
          for ( i = 0; i < v38; ++i )
          {
            v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct INativeConfigSearchResult **))(*(_QWORD *)v44 + 32LL))(
                    v44,
                    i,
                    &v31);
            if ( v11 < 0 )
              break;
            v11 = (*(__int64 (__fastcall **)(struct INativeConfigSearchResult *, unsigned int *))(*(_QWORD *)v31 + 48LL))(
                    v31,
                    &v39);
            if ( v11 < 0 )
              break;
            v11 = (*(__int64 (__fastcall **)(struct INativeConfigSearchResult *, __int64 *))(*(_QWORD *)v31 + 24LL))(
                    v31,
                    &v50);
            if ( v11 < 0 )
              break;
            v11 = (*(__int64 (__fastcall **)(struct INativeConfigSearchResult *, int *))(*(_QWORD *)v31 + 40LL))(
                    v31,
                    &v35);
            if ( v11 < 0 )
              break;
            if ( v35 >= 0 && (v42 || v32) )
            {
              v30 = 0;
              for ( j = 0; j < v39; ++j )
              {
                v11 = (*(__int64 (__fastcall **)(struct INativeConfigSearchResult *, _QWORD, wchar_t **))(*(_QWORD *)v31 + 56LL))(
                        v31,
                        j,
                        &String2);
                if ( v11 < 0 )
                  goto LABEL_96;
                if ( !v42 || !_wcsicmp(v42, String2) )
                {
                  v30 = 1;
                  if ( v32 )
                  {
                    v11 = (*(__int64 (__fastcall **)(__int64, wchar_t *, __int64, __int64 *, __int64 *, _QWORD, int))(*(_QWORD *)v43 + 112LL))(
                            v43,
                            String2,
                            v50,
                            &v36,
                            &v47,
                            0,
                            58);
                    if ( v11 < 0 )
                    {
                      if ( v47 )
                        (*(void (__fastcall **)(struct IExtensionContext *, _QWORD, const wchar_t *, __int64, _DWORD))(*(_QWORD *)a2 + 112LL))(
                          a2,
                          (unsigned int)v11,
                          &Str,
                          v47,
                          0);
                      goto LABEL_96;
                    }
                    while ( v18 < v32 )
                    {
                      v11 = (*(__int64 (__fastcall **)(struct ICommandParameterList *, _QWORD, const unsigned __int16 **, wchar_t **))(*(_QWORD *)v33 + 32LL))(
                              v33,
                              v18,
                              &v49,
                              &v51);
                      if ( v11 < 0 )
                        goto LABEL_96;
                      v34 = 0;
                      v21 = *(_QWORD *)a2;
                      v40 = 512;
                      v11 = (*(__int64 (__fastcall **)(struct IExtensionContext *, __int64, const unsigned __int16 *, wchar_t *, int *, int *))(v21 + 88))(
                              a2,
                              v36,
                              v49,
                              v67,
                              &v40,
                              &v34);
                      if ( v11 < 0 )
                      {
                        if ( v11 == -2147023483 )
                        {
                          v11 = -2147024809;
                          v46 = v49;
                          v17 = 3221226472LL;
LABEL_35:
                          (*(void (__fastcall **)(struct IExtensionContext *, _QWORD, __int64, const unsigned __int16 **, _DWORD))(*(_QWORD *)a2 + 144LL))(
                            a2,
                            (unsigned int)v11,
                            v17,
                            &v46,
                            0);
                        }
                        goto LABEL_96;
                      }
                      if ( v34 || *v51 && _wcsicmp(v67, v51) )
                      {
                        v18 = 0;
                        v30 = 0;
LABEL_63:
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
                        v36 = 0;
                        goto LABEL_64;
                      }
                      ++v18;
                    }
                    v18 = 0;
                    goto LABEL_63;
                  }
                }
LABEL_64:
                ;
              }
              if ( !v30 )
                goto LABEL_74;
              v22 = (CONFIG_SEARCH_OBJECT *)operator new(0xE0u);
              if ( !v22 )
                goto LABEL_93;
              v24 = CONFIG_SEARCH_OBJECT::CONFIG_SEARCH_OBJECT(v22, v23);
              v9 = v24;
              if ( !v24 )
                goto LABEL_94;
              v11 = CONFIG_SEARCH_OBJECT::Create(v24, v31);
              if ( v11 < 0 )
                break;
              if ( v5 )
              {
                v11 = (*(__int64 (__fastcall **)(CONFIG_SEARCH_OBJECT *, const unsigned __int16 *, __int64 *))(*(_QWORD *)v9 + 80LL))(
                        v9,
                        L"status",
                        &v45);
                if ( v11 < 0 )
                  break;
                v11 = (*(__int64 (__fastcall **)(struct IExtensionContext *, const unsigned __int16 *, wchar_t *, __int64, int *))(*(_QWORD *)a2 + 160LL))(
                        a2,
                        L"status",
                        String1,
                        v45,
                        &v30);
                if ( v11 < 0 )
                  break;
              }
              if ( v30 )
              {
                v11 = (*(__int64 (__fastcall **)(struct ICommandObjectList *, CONFIG_SEARCH_OBJECT *))(*(_QWORD *)v52 + 24LL))(
                        v52,
                        v9);
                if ( v11 < 0 )
                  break;
LABEL_74:
                if ( !v9 )
                  goto LABEL_88;
              }
            }
            else
            {
              v25 = (CONFIG_SEARCH_OBJECT *)operator new(0xE0u);
              if ( !v25 )
              {
LABEL_93:
                v9 = 0;
LABEL_94:
                v11 = -2147024888;
                break;
              }
              v27 = CONFIG_SEARCH_OBJECT::CONFIG_SEARCH_OBJECT(v25, v26);
              v9 = v27;
              if ( !v27 )
                goto LABEL_94;
              v11 = CONFIG_SEARCH_OBJECT::Create(v27, v31);
              if ( v11 < 0 )
                break;
              v28 = 1;
              v30 = 1;
              if ( v35 < 0 )
              {
                v28 = v41;
                v30 = v41;
              }
              if ( v5 )
              {
                v11 = (*(__int64 (__fastcall **)(CONFIG_SEARCH_OBJECT *, const unsigned __int16 *, __int64 *))(*(_QWORD *)v9 + 80LL))(
                        v9,
                        L"status",
                        &v45);
                if ( v11 < 0 )
                  break;
                v11 = (*(__int64 (__fastcall **)(struct IExtensionContext *, const unsigned __int16 *, wchar_t *, __int64, int *))(*(_QWORD *)a2 + 160LL))(
                        a2,
                        L"status",
                        v13,
                        v45,
                        &v30);
                if ( v11 < 0 )
                  break;
                v28 = v30;
              }
              if ( v28 )
              {
                v11 = (*(__int64 (__fastcall **)(struct ICommandObjectList *, CONFIG_SEARCH_OBJECT *))(*(_QWORD *)v52 + 24LL))(
                        v52,
                        v9);
                if ( v11 < 0 )
                  break;
              }
            }
            (*(void (__fastcall **)(CONFIG_SEARCH_OBJECT *))(*(_QWORD *)v9 + 16LL))(v9);
            v9 = 0;
LABEL_88:
            (*(void (__fastcall **)(struct INativeConfigSearchResult *))(*(_QWORD *)v31 + 16LL))(v31);
            v13 = String1;
            v31 = 0;
          }
        }
      }
    }
  }
LABEL_96:
  if ( v43 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    v43 = 0;
  }
  if ( v36 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    v36 = 0;
  }
  if ( v47 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    v47 = 0;
  }
  if ( v33 )
  {
    (*(void (__fastcall **)(struct ICommandParameterList *))(*(_QWORD *)v33 + 16LL))(v33);
    v33 = 0;
  }
  if ( v44 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    v44 = 0;
  }
  if ( v31 )
  {
    (*(void (__fastcall **)(struct INativeConfigSearchResult *))(*(_QWORD *)v31 + 16LL))(v31);
    v31 = 0;
  }
  if ( v9 )
    (*(void (__fastcall **)(CONFIG_SEARCH_OBJECT *))(*(_QWORD *)v9 + 16LL))(v9);
  BUFFER::~BUFFER((BUFFER *)v53);
  BUFFER::~BUFFER((BUFFER *)v58);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180019f48  mov     [rsp-8+arg_0], rbx
0x180019f4d  push    rbp
0x180019f4e  push    rsi
0x180019f4f  push    rdi
0x180019f50  push    r12
0x180019f52  push    r13
0x180019f54  push    r14
0x180019f56  push    r15
0x180019f58  lea     rbp, [rsp-860h]
0x180019f60  sub     rsp, 960h
0x180019f67  mov     rax, cs:__security_cookie
0x180019f6e  xor     rax, rsp
0x180019f71  mov     [rbp+890h+var_40], rax
0x180019f78  mov     r15, [rbp+890h+arg_20]
0x180019f7f  lea     rcx, [rbp+890h+var_83E]; void *
0x180019f83  xor     r13d, r13d
0x180019f86  mov     [rbp+890h+var_8B8], r15
0x180019f8a  mov     rsi, r8
0x180019f8d  mov     [rbp+890h+var_8D0], r13
0x180019f91  mov     r14, rdx
0x180019f94  mov     [rbp+890h+var_8C0], r13
0x180019f98  mov     r12d, 1FEh
0x180019f9e  mov     [rsp+990h+var_950], r13d
0x180019fa3  mov     r8d, r12d; Size
0x180019fa6  mov     [rsp+990h+var_914], 200h
0x180019fae  xor     edx, edx; Val
0x180019fb0  mov     [rbp+890h+var_8E0], r13
0x180019fb4  mov     rbx, r9
0x180019fb7  mov     [rbp+890h+var_900], r13
0x180019fbb  mov     [rsp+990h+var_928], r13
0x180019fc0  mov     edi, r13d
0x180019fc3  mov     [rbp+890h+var_8F8], r13
0x180019fc7  mov     [rbp+890h+var_8E8], r13
0x180019fcb  mov     [rbp+890h+var_908], r13
0x180019fcf  mov     [rbp+890h+String2], r13
0x180019fd3  mov     [rsp+990h+var_91C], r13d
0x180019fd8  mov     [rsp+990h+var_918], r13d
0x180019fdd  mov     [rsp+990h+var_948], r13
0x180019fe2  mov     [rsp+990h+var_940], r13d
0x180019fe7  mov     [rbp+890h+var_8C8], r13
0x180019feb  mov     [rsp+990h+var_92C], r13d
0x180019ff0  mov     [rsp+990h+var_930], r13d
0x180019ff5  call    memset_0
0x180019ffa  lea     rax, [rbp+890h+var_840]
0x180019ffe  mov     [rbp+890h+var_850], 200h
0x18001a005  mov     r8d, r12d; Size
0x18001a008  mov     [rbp+890h+var_858], rax
0x18001a00c  xor     edx, edx; Val
0x18001a00e  mov     [rbp+890h+var_84C], 100h
0x18001a014  lea     rcx, [rbp+890h+var_63E]; void *
0x18001a01b  mov     [rbp+890h+var_848], r13d
0x18001a01f  mov     [rbp+890h+var_840], r13w
0x18001a024  mov     [rbp+890h+var_8F0], r13
0x18001a028  call    memset_0
0x18001a02d  mov     [rbp+890h+var_888], 200h
0x18001a034  lea     rax, [rbp+890h+var_640]
0x18001a03b  mov     [rbp+890h+String1], rax
0x18001a03f  lea     r12d, [r13+1]
0x18001a043  mov     [rbp+890h+var_884], 100h
0x18001a049  mov     [rbp+890h+var_880], r13d
0x18001a04d  mov     [rbp+890h+var_640], r13w
0x18001a055  mov     [rsp+990h+var_938], r13
0x18001a05a  mov     [rsp+990h+var_920], r13d
0x18001a05f  test    r14, r14
0x18001a062  jz      loc_18001A74C
0x18001a068  test    rbx, rbx
0x18001a06b  jz      loc_18001A74C
0x18001a071  test    r15, r15
0x18001a074  jz      loc_18001A74C
0x18001a07a  test    rsi, rsi
0x18001a07d  jz      loc_18001A74C
0x18001a083  mov     rax, [rbx]
0x18001a086  lea     rdx, [rsp+990h+var_938]
0x18001a08b  mov     rcx, rbx
0x18001a08e  mov     rax, [rax+50h]
0x18001a092  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a097  mov     ebx, eax
0x18001a099  test    eax, eax
0x18001a09b  js      loc_18001A751
0x18001a0a1  mov     r8, [rsp+990h+var_938]; struct ICommandParameterList *
0x18001a0a6  lea     r9, [rbp+890h+var_908]; unsigned __int16 **
0x18001a0aa  mov     rdx, r14; struct IExtensionContext *
0x18001a0ad  mov     dword ptr [rsp+990h+var_970], r13d; int
0x18001a0b2  call    ?PopSectionNameFromParameters@CONFIG_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEAPEBGH@Z; CONFIG_OBJECT_EXTENSION::PopSectionNameFromParameters(IExtensionContext *,ICommandParameterList *,ushort const * *,int)
0x18001a0b7  mov     ecx, 80000000h; this
0x18001a0bc  mov     ebx, eax
0x18001a0be  add     eax, ecx
0x18001a0c0  mov     r15d, 80070585h
0x18001a0c6  test    ecx, eax
0x18001a0c8  jnz     short loc_18001A0D3
0x18001a0ca  cmp     ebx, r15d
0x18001a0cd  jnz     loc_18001A751
0x18001a0d3  mov     r8, [rsp+990h+var_938]; struct ICommandParameterList *
0x18001a0d8  lea     rax, [rbp+890h+var_8B0]
0x18001a0dc  mov     [rsp+990h+var_960], r12d; int
0x18001a0e1  lea     r9, aStatus; "status"
0x18001a0e8  mov     [rsp+990h+var_968], r13d; int
0x18001a0ed  mov     rdx, r14; struct IExtensionContext *
0x18001a0f0  mov     [rsp+990h+var_970], rax; struct STRU *
0x18001a0f5  mov     [rbp+890h+var_910], r13d
0x18001a0f9  call    ?PopParameter@APP_OBJECT_UTILS@@QEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEBGPEAVSTRU@@HH@Z; APP_OBJECT_UTILS::PopParameter(IExtensionContext *,ICommandParameterList *,ushort const *,STRU *,int,int)
0x18001a0fe  mov     ebx, eax
0x18001a100  test    eax, eax
0x18001a102  js      short loc_18001A12A
0x18001a104  mov     r15, [rbp+890h+String1]
0x18001a108  lea     rdx, asc_1800397FC; "*"
0x18001a10f  mov     rcx, r15; String1
0x18001a112  call    cs:__imp__wcsicmp
0x18001a118  test    eax, eax
0x18001a11a  jnz     short loc_18001A137
0x18001a11c  mov     [rbp+890h+var_910], r12d
0x18001a120  mov     [r15], r13w
0x18001a124  mov     [rbp+890h+var_880], r13d
0x18001a128  jmp     short loc_18001A13B
0x18001a12a  cmp     eax, r15d
0x18001a12d  jnz     loc_18001A751
0x18001a133  mov     r15, [rbp+890h+String1]
0x18001a137  mov     r13d, [rbp+890h+var_880]
0x18001a13b  xor     r12d, r12d
0x18001a13e  cmp     [rbp+890h+var_908], r12
0x18001a142  jnz     short loc_18001A18E
0x18001a144  mov     rcx, [rsp+990h+var_938]
0x18001a149  lea     rdx, [rsp+990h+var_920]
0x18001a14e  mov     rax, [rcx]
0x18001a151  mov     rax, [rax+18h]
0x18001a155  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a15a  mov     ebx, eax
0x18001a15c  test    eax, eax
0x18001a15e  js      loc_18001A751
0x18001a164  cmp     [rsp+990h+var_920], r12d
0x18001a169  jbe     short loc_18001A18E
0x18001a16b  mov     r8, [rsp+990h+var_938]; struct ICommandParameterList *
0x18001a170  lea     r9, [rbp+890h+var_908]; unsigned __int16 **
0x18001a174  mov     rdx, r14; struct IExtensionContext *
0x18001a177  mov     dword ptr [rsp+990h+var_970], 1; int
0x18001a17f  call    ?PopSectionNameFromParameters@CONFIG_OBJECT_EXTENSION@@AEAAJPEAVIExtensionContext@@PEAVICommandParameterList@@PEAPEBGH@Z; CONFIG_OBJECT_EXTENSION::PopSectionNameFromParameters(IExtensionContext *,ICommandParameterList *,ushort const * *,int)
0x18001a184  mov     ebx, eax
0x18001a186  test    eax, eax
0x18001a188  js      loc_18001A751
0x18001a18e  mov     rax, [r14]
0x18001a191  mov     rcx, r14
0x18001a194  mov     rax, [rax+28h]
0x18001a198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a19d  cmp     eax, 1
0x18001a1a0  jz      short loc_18001A1BC
0x18001a1a2  mov     rax, [r14]
0x18001a1a5  mov     rcx, r14
0x18001a1a8  mov     rax, [rax+20h]
0x18001a1ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a1b1  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x18001a1b8  test    al, 8
0x18001a1ba  jz      short loc_18001A1C3
0x18001a1bc  lea     rdx, Str
0x18001a1c3  mov     rax, [r14]
0x18001a1c6  lea     r8, [rbp+890h+var_900]
0x18001a1ca  mov     rcx, r14
0x18001a1cd  mov     rax, [rax+50h]
0x18001a1d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a1d6  mov     ebx, eax
0x18001a1d8  test    eax, eax
0x18001a1da  js      loc_18001A751
0x18001a1e0  cmp     [rsi], r12w
0x18001a1e4  jnz     short loc_18001A1F2
0x18001a1e6  lea     rsi, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x18001a1ed  jmp     loc_18001A276
0x18001a1f2  lea     rdx, aMachine_1; "MACHINE/"
0x18001a1f9  mov     rcx, rsi; Str
0x18001a1fc  call    cs:__imp_wcsstr
0x18001a202  test    rax, rax
0x18001a205  jnz     short loc_18001A276
0x18001a207  lea     rdx, aMachine_0; "MACHINE"
0x18001a20e  mov     rcx, rsi; String1
0x18001a211  call    wcscmp_0
0x18001a216  test    eax, eax
0x18001a218  jz      short loc_18001A276
0x18001a21a  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x18001a221  lea     rcx, [rbp+890h+var_878]; this
0x18001a225  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001a22a  mov     ebx, eax
0x18001a22c  test    eax, eax
0x18001a22e  js      loc_18001A751
0x18001a234  jmp     short loc_18001A23A
0x18001a236  add     rsi, 2
0x18001a23a  cmp     word ptr [rsi], 2Fh ; '/'
0x18001a23e  jz      short loc_18001A236
0x18001a240  lea     rdx, SubStr; "/"
0x18001a247  lea     rcx, [rbp+890h+var_878]; this
0x18001a24b  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001a250  mov     ebx, eax
0x18001a252  test    eax, eax
0x18001a254  js      loc_18001A751
0x18001a25a  mov     rdx, rsi; unsigned __int16 *
0x18001a25d  lea     rcx, [rbp+890h+var_878]; this
0x18001a261  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001a266  xor     esi, esi
0x18001a268  mov     ebx, eax
0x18001a26a  test    eax, eax
0x18001a26c  js      loc_18001A753
0x18001a272  mov     rsi, [rbp+890h+var_858]
0x18001a276  mov     rcx, [rbp+890h+var_900]
0x18001a27a  lea     r8, [rbp+890h+var_8F8]
0x18001a27e  mov     rdx, rsi
0x18001a281  mov     rax, [rcx]
0x18001a284  mov     rax, [rax+68h]
0x18001a288  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a28d  mov     ebx, eax
0x18001a28f  test    eax, eax
0x18001a291  jns     short loc_18001A2C0
0x18001a293  mov     [rbp+890h+var_8E8], rsi
0x18001a297  mov     r8d, 0C000040Eh
0x18001a29d  mov     rax, [r14]
0x18001a2a0  lea     r9, [rbp+890h+var_8E8]
0x18001a2a4  xor     esi, esi
0x18001a2a6  mov     edx, ebx
0x18001a2a8  mov     rcx, r14
0x18001a2ab  mov     dword ptr [rsp+990h+var_970], esi
0x18001a2af  mov     rax, [rax+90h]
0x18001a2b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a2bb  jmp     loc_18001A753
0x18001a2c0  mov     rcx, [rbp+890h+var_8F8]
0x18001a2c4  lea     rdx, [rsp+990h+var_91C]
0x18001a2c9  mov     rax, [rcx]
0x18001a2cc  mov     rax, [rax+18h]
0x18001a2d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a2d5  xor     esi, esi
0x18001a2d7  mov     ebx, eax
0x18001a2d9  test    eax, eax
0x18001a2db  js      loc_18001A753
0x18001a2e1  mov     rcx, [rsp+990h+var_938]
0x18001a2e6  lea     rdx, [rsp+990h+var_940]
0x18001a2eb  mov     rax, [rcx]
0x18001a2ee  mov     rax, [rax+18h]
0x18001a2f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a2f7  mov     ebx, eax
0x18001a2f9  test    eax, eax
0x18001a2fb  js      loc_18001A753
0x18001a301  mov     r12d, esi
0x18001a304  cmp     r12d, [rsp+990h+var_91C]
0x18001a309  jnb     loc_18001A753
0x18001a30f  mov     rcx, [rbp+890h+var_8F8]
0x18001a313  lea     r8, [rsp+990h+var_948]
0x18001a318  mov     edx, r12d
0x18001a31b  mov     rax, [rcx]
0x18001a31e  mov     rax, [rax+20h]
0x18001a322  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a327  mov     ebx, eax
0x18001a329  test    eax, eax
0x18001a32b  js      loc_18001A753
0x18001a331  mov     rcx, [rsp+990h+var_948]
0x18001a336  lea     rdx, [rsp+990h+var_918]
0x18001a33b  mov     rax, [rcx]
0x18001a33e  mov     rax, [rax+30h]
0x18001a342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a347  mov     ebx, eax
0x18001a349  test    eax, eax
0x18001a34b  js      loc_18001A753
0x18001a351  mov     rcx, [rsp+990h+var_948]
0x18001a356  lea     rdx, [rbp+890h+var_8C8]
0x18001a35a  mov     rax, [rcx]
0x18001a35d  mov     rax, [rax+18h]
0x18001a361  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a366  mov     ebx, eax
0x18001a368  test    eax, eax
0x18001a36a  js      loc_18001A753
0x18001a370  mov     rcx, [rsp+990h+var_948]
0x18001a375  lea     rdx, [rsp+990h+var_92C]
0x18001a37a  mov     rax, [rcx]
0x18001a37d  mov     rax, [rax+28h]
0x18001a381  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a386  mov     ebx, eax
0x18001a388  test    eax, eax
0x18001a38a  js      loc_18001A753
0x18001a390  cmp     [rsp+990h+var_92C], esi
0x18001a394  jl      loc_18001A5EE
0x18001a39a  cmp     [rbp+890h+var_908], rsi
0x18001a39e  jnz     short loc_18001A3AA
0x18001a3a0  cmp     [rsp+990h+var_940], esi
0x18001a3a4  jz      loc_18001A5EE
0x18001a3aa  mov     [rsp+990h+var_950], esi
0x18001a3ae  mov     r15d, esi
0x18001a3b1  cmp     r15d, [rsp+990h+var_918]
0x18001a3b6  jnb     loc_18001A513
0x18001a3bc  mov     rcx, [rsp+990h+var_948]
0x18001a3c1  lea     r8, [rbp+890h+String2]
0x18001a3c5  mov     edx, r15d
0x18001a3c8  mov     rax, [rcx]
0x18001a3cb  mov     rax, [rax+38h]
0x18001a3cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3d4  mov     ebx, eax
0x18001a3d6  test    eax, eax
0x18001a3d8  js      loc_18001A753
0x18001a3de  mov     rcx, [rbp+890h+var_908]; String1
0x18001a3e2  test    rcx, rcx
0x18001a3e5  jz      short loc_18001A3F9
0x18001a3e7  mov     rdx, [rbp+890h+String2]; String2
0x18001a3eb  call    cs:__imp__wcsicmp
0x18001a3f1  test    eax, eax
0x18001a3f3  jnz     loc_18001A50B
0x18001a3f9  mov     [rsp+990h+var_950], 1
0x18001a401  cmp     [rsp+990h+var_940], esi
  ... truncated ...
```
