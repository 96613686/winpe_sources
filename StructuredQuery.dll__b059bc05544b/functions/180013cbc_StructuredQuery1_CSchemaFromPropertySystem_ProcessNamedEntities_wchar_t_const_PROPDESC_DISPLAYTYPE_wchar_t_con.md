# StructuredQuery1::CSchemaFromPropertySystem::ProcessNamedEntities(wchar_t const *,PROPDESC_DISPLAYTYPE,wchar_t const *,ushort,IPropertyEnumTypeList *,wchar_t * *)

- ea: `0x180013cbc`
- end: `0x180014556`
- name: `?ProcessNamedEntities@CSchemaFromPropertySystem@StructuredQuery1@@AEAAJPEB_WW4PROPDESC_DISPLAYTYPE@@0GPEAUIPropertyEnumTypeList@@PEAPEA_W@Z`
- size: `2202`
- prototype: `int(StructuredQuery1::CSchemaFromPropertySystem *__hidden this, const wchar_t *, enum PROPDESC_DISPLAYTYPE, const wchar_t *, unsigned __int16, struct IPropertyEnumTypeList *, wchar_t **)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001c8c4`

## callees

- `0x180012148`
- `0x180012310`
- `0x180013cbc`
- `0x180015a40`
- `0x18001c5b4`
- `0x18001dd8c`
- `0x18001e110`
- `0x180025c50`
- `0x180035e7c`
- `0x18005daf0`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013da6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013dd1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013dfc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013da6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013dd1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013dfc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014290`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014311`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001431d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014290`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014311`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001431d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001414c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014156`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014441`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001414c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014156`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180014441`

## string_xrefs

- `0x180013de7`: `System.StructuredQueryType.FilePath`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::CSchemaFromPropertySystem::ProcessNamedEntities(
        StructuredQuery1::CSchemaFromPropertySystem *this,
        wchar_t *a2,
        __int64 a3,
        wchar_t *a4,
        unsigned __int16 a5,
        struct IPropertyEnumTypeList *a6,
        wchar_t **a7)
{
  wchar_t **v8; // r15
  StructuredQuery1::CSchemaFromPropertySystem *v10; // r14
  signed int NamedEntityCanonicalName; // ebx
  struct IPropertyEnumTypeListVtbl *lpVtbl; // rax
  unsigned int v14; // esi
  int v15; // eax
  const wchar_t *v16; // rsi
  BOOL v17; // edi
  const struct _GUID *v18; // rdx
  __int64 v19; // rcx
  void *v20; // r13
  const struct _GUID *v21; // rdx
  __int64 v22; // rcx
  void *v23; // r15
  void *v24; // r13
  unsigned int v25; // r14d
  wchar_t *v26; // r15
  struct IPropertyEnumTypeListVtbl *v27; // rax
  __int64 v28; // rdx
  VARTYPE vt; // ax
  struct IPropertyEnumTypeListVtbl *v30; // rax
  unsigned __int64 v31; // rdx
  _WORD *v32; // r8
  __int64 v33; // rax
  const wchar_t *v34; // rcx
  _WORD *v35; // rcx
  int v36; // edx
  const struct _GUID *v37; // r8
  void *v38; // rsi
  wchar_t **v39; // r9
  int v40; // eax
  void *v41; // rdi
  int v42; // edi
  int v43; // ebx
  struct IPropertyEnumTypeListVtbl *v44; // rax
  int v45; // eax
  int v46; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v47; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v48; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v50; // [rsp+58h] [rbp-A8h] BYREF
  void *v51; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v52; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 v53; // [rsp+70h] [rbp-90h] BYREF
  int v54; // [rsp+78h] [rbp-88h] BYREF
  __int64 v55; // [rsp+80h] [rbp-80h] BYREF
  wchar_t *v56; // [rsp+88h] [rbp-78h] BYREF
  void *v57; // [rsp+90h] [rbp-70h] BYREF
  void *v58; // [rsp+98h] [rbp-68h] BYREF
  __int64 v59; // [rsp+A0h] [rbp-60h] BYREF
  struct tagPROPVARIANT v60; // [rsp+A8h] [rbp-58h] BYREF
  struct tagPROPVARIANT pvar; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t **v62; // [rsp+D8h] [rbp-28h]
  wchar_t v63[256]; // [rsp+E0h] [rbp-20h] BYREF
  wchar_t v64[1024]; // [rsp+2E0h] [rbp+1E0h] BYREF

  v8 = a7;
  v10 = this;
  v62 = a7;
  v56 = a2;
  v51 = this;
  if ( a5 == 11 && (_DWORD)a3 != 4 )
    return (unsigned int)_AllocString<CTCoAllocPolicy>((__int64)this, (__int64)a2, (const size_t *)a4, v8);
  lpVtbl = a6->lpVtbl;
  v14 = 0;
  v47 = 0;
  NamedEntityCanonicalName = ((__int64 (__fastcall *)(struct IPropertyEnumTypeList *, unsigned int *, __int64))lpVtbl->GetCount)(
                               a6,
                               &v47,
                               a3);
  if ( NamedEntityCanonicalName < 0 )
  {
LABEL_6:
    *v8 = 0;
    return (unsigned int)NamedEntityCanonicalName;
  }
  if ( v47 && CompareStringW(0x7Fu, 1u, a4, -1, L"System.StructuredQueryType.DateTime", -1) != 2 )
  {
    if ( CompareStringW(0x7Fu, 1u, a4, -1, L"System.StructuredQueryType.String", -1) == 2
      || CompareStringW(0x7Fu, 1u, a4, -1, L"System.StructuredQueryType.FilePath", -1) == 2 )
    {
      v43 = 0;
      this = 0;
      while ( v14 < v47 )
      {
        v44 = a6->lpVtbl;
        v50 = 0;
        v45 = ((__int64 (__fastcall *)(struct IPropertyEnumTypeList *, _QWORD, GUID *, __int64 *))v44->GetAt)(
                a6,
                v14,
                &GUID_11e1fbf9_2d56_4a6b_8db3_7cd193a471f2,
                &v50);
        this = 0;
        if ( v45 >= 0 )
        {
          v46 = 0;
          if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v50 + 24LL))(v50, &v46) >= 0 && !v46 )
            v43 = 1;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
          this = 0;
        }
        v15 = 1;
        ++v14;
        if ( v43 )
          goto LABEL_12;
      }
      return (unsigned int)_AllocString<CTCoAllocPolicy>((__int64)this, (__int64)a2, (const size_t *)a4, v8);
    }
    v15 = 0;
LABEL_12:
    v16 = L"System.StructuredQueryType.Object";
    if ( !v15 )
      v16 = a4;
    v17 = 0;
    NamedEntityCanonicalName = StringCchPrintfW(v63, 0x100u, L"System.StructuredQueryType.Implicit.%s", a2);
    if ( NamedEntityCanonicalName < 0 )
      goto LABEL_6;
    v58 = 0;
    NamedEntityCanonicalName = StructuredQuery1::ConstantString::CreateInstance(v16, v18, &v58);
    if ( NamedEntityCanonicalName < 0 )
      goto LABEL_6;
    v19 = *((_QWORD *)v10 + 5);
    v20 = v58;
    v59 = 0;
    NamedEntityCanonicalName = (*(__int64 (__fastcall **)(__int64, void *, GUID *, __int64 *))(*(_QWORD *)v19 + 32LL))(
                                 v19,
                                 v58,
                                 &GUID_e90f2096_c488_49bf_a9dd_62d7c84755e5,
                                 &v59);
    if ( NamedEntityCanonicalName >= 0 )
    {
      v57 = 0;
      NamedEntityCanonicalName = StructuredQuery1::ConstantString::CreateInstance(v63, v21, &v57);
      if ( NamedEntityCanonicalName >= 0 )
      {
        v22 = *((_QWORD *)v10 + 5);
        v23 = v57;
        v55 = 0;
        NamedEntityCanonicalName = (*(__int64 (__fastcall **)(__int64, void *, GUID *, __int64 *))(*(_QWORD *)v22 + 24LL))(
                                     v22,
                                     v57,
                                     &GUID_e90f2096_c488_49bf_a9dd_62d7c84755e5,
                                     &v55);
        if ( NamedEntityCanonicalName >= 0 )
        {
          if ( v55
            || (NamedEntityCanonicalName = (*(__int64 (__fastcall **)(_QWORD, void *, __int64, GUID *, __int64 *))(**((_QWORD **)v10 + 5) + 40LL))(
                                             *((_QWORD *)v10 + 5),
                                             v23,
                                             v59,
                                             &GUID_e90f2096_c488_49bf_a9dd_62d7c84755e5,
                                             &v55),
                NamedEntityCanonicalName >= 0) )
          {
            v24 = v51;
            v25 = 0;
            v26 = v56;
            while ( 1 )
            {
              if ( v25 >= v47 )
              {
LABEL_69:
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
                v23 = v57;
                v20 = v58;
                goto LABEL_70;
              }
              v27 = a6->lpVtbl;
              v52 = 0;
              NamedEntityCanonicalName = ((__int64 (__fastcall *)(struct IPropertyEnumTypeList *, _QWORD, GUID *, __int64 *))v27->GetAt)(
                                           a6,
                                           v25,
                                           &GUID_11e1fbf9_2d56_4a6b_8db3_7cd193a471f2,
                                           &v52);
              if ( NamedEntityCanonicalName >= 0 )
                break;
LABEL_68:
              ++v25;
              if ( NamedEntityCanonicalName < 0 )
                goto LABEL_69;
            }
            v50 = 0;
            NamedEntityCanonicalName = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v52)(
                                         v52,
                                         &GUID_bb776487_a7a1_425b_8983_31ed23455b68,
                                         &v50);
            if ( NamedEntityCanonicalName < 0 )
            {
LABEL_67:
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
              goto LABEL_68;
            }
            v54 = 0;
            NamedEntityCanonicalName = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v52 + 24LL))(v52, &v54);
            if ( NamedEntityCanonicalName < 0 )
              goto LABEL_66;
            if ( !v54 )
            {
              memset(&v60, 0, sizeof(v60));
              NamedEntityCanonicalName = (*(__int64 (__fastcall **)(__int64, struct tagPROPVARIANT *))(*(_QWORD *)v52 + 32LL))(
                                           v52,
                                           &v60);
              if ( NamedEntityCanonicalName < 0 )
                goto LABEL_66;
              v42 = StructuredQuery1::CSchemaFromPropertySystem::WritePropVariantForNamedEntity(
                      &v60,
                      L"=",
                      (const wchar_t *)&cchOriginalDestLength,
                      v64,
                      0x400u,
                      0,
                      0);
              PropVariantClear((PROPVARIANT *)&v60);
              v17 = v42 >= 0;
LABEL_48:
              if ( v17 )
              {
                v17 = 0;
                v51 = 0;
                NamedEntityCanonicalName = StructuredQuery1::RestrictionInfo::CreateInstance(v64, v36, v37, &v51);
                if ( NamedEntityCanonicalName >= 0 )
                {
                  v38 = v51;
                  v48 = 0;
                  NamedEntityCanonicalName = (**(__int64 (__fastcall ***)(void *, GUID *, __int64 *))v51)(
                                               v51,
                                               &GUID_0d5f4564_b150_41f9_927d_97b1e3c8e1b0,
                                               &v48);
                  if ( NamedEntityCanonicalName < 0 )
                  {
LABEL_65:
                    (*(void (__fastcall **)(void *))(*(_QWORD *)v38 + 16LL))(v38);
                    goto LABEL_66;
                  }
                  v51 = 0;
                  NamedEntityCanonicalName = (*(__int64 (__fastcall **)(__int64, GUID *, void **))(*(_QWORD *)v50 + 24LL))(
                                               v50,
                                               &GUID_d6d9aabf_5336_425a_a4b1_d0ff94bddf75,
                                               &v51);
                  if ( NamedEntityCanonicalName < 0 )
                  {
LABEL_64:
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
                    goto LABEL_65;
                  }
                  v56 = 0;
                  NamedEntityCanonicalName = (*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v50 + 32LL))(
                                               v50,
                                               &v56);
                  if ( NamedEntityCanonicalName < 0 )
                  {
LABEL_63:
                    (*(void (__fastcall **)(void *))(*(_QWORD *)v51 + 16LL))(v51);
                    goto LABEL_64;
                  }
                  v46 = 0;
                  LODWORD(v53) = 0;
                  NamedEntityCanonicalName = StructuredQuery1::CSchemaFromPropertySystem::ProcessMnemonics(
                                               v24,
                                               v51,
                                               &v46,
                                               &v53);
                  if ( NamedEntityCanonicalName >= 0 )
                  {
                    if ( (_DWORD)v53 )
                      goto LABEL_57;
                    pv = 0;
                    v40 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v52 + 56LL))(v52, &pv);
                    NamedEntityCanonicalName = v40;
                    if ( v40 < 0 )
                    {
                      if ( v40 == -2147467259 )
                      {
LABEL_57:
                        pv = 0;
                        NamedEntityCanonicalName = StructuredQuery1::MakeNamedEntityCanonicalName(
                                                     (StructuredQuery1 *)v26,
                                                     v56,
                                                     (const wchar_t *)&pv,
                                                     v39);
                        if ( NamedEntityCanonicalName >= 0 )
                        {
                          v41 = pv;
                          NamedEntityCanonicalName = (*(__int64 (__fastcall **)(void *, LPVOID))(*(_QWORD *)v38 + 40LL))(
                                                       v38,
                                                       pv);
                          if ( NamedEntityCanonicalName >= 0 )
                          {
                            NamedEntityCanonicalName = StructuredQuery1::CSchemaFromPropertySystem::ProcessMnemonic(
                                                         v24,
                                                         v41,
                                                         &v46,
                                                         2,
                                                         v48);
                            if ( NamedEntityCanonicalName >= 0 )
                              NamedEntityCanonicalName = (*(__int64 (__fastcall **)(__int64, void *))(*(_QWORD *)v55 + 112LL))(
                                                           v55,
                                                           v38);
                          }
                          CoTaskMemFree(v41);
                          v17 = 0;
                        }
                      }
                    }
                    else
                    {
                      NamedEntityCanonicalName = StructuredQuery1::CSchemaFromPropertySystem::ProcessMnemonic(
                                                   v24,
                                                   pv,
                                                   &v46,
                                                   1,
                                                   v48);
                      CoTaskMemFree(pv);
                      if ( NamedEntityCanonicalName >= 0 )
                        goto LABEL_57;
                    }
                  }
                  CoTaskMemFree(v56);
                  goto LABEL_63;
                }
LABEL_66:
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
                goto LABEL_67;
              }
LABEL_79:
              v17 = 0;
              goto LABEL_66;
            }
            if ( v54 != 1 )
              goto LABEL_66;
            memset(&v60, 0, sizeof(v60));
            NamedEntityCanonicalName = (*(__int64 (__fastcall **)(__int64, struct tagPROPVARIANT *))(*(_QWORD *)v52 + 40LL))(
                                         v52,
                                         &v60);
            if ( NamedEntityCanonicalName < 0 )
              goto LABEL_66;
            v53 = 1024;
            pv = v64;
            if ( StructuredQuery1::CSchemaFromPropertySystem::WritePropVariantForNamedEntity(
                   &v60,
                   L"[",
                   L"|",
                   v64,
                   0x400u,
                   (wchar_t **)&pv,
                   &v53) < 0 )
            {
LABEL_47:
              PropVariantClear((PROPVARIANT *)&v60);
              if ( NamedEntityCanonicalName < 0 )
                goto LABEL_79;
              goto LABEL_48;
            }
            v28 = v25 + 1;
            vt = 0;
            memset(&pvar, 0, sizeof(pvar));
            if ( (unsigned int)v28 < v47 )
            {
              v30 = a6->lpVtbl;
              v48 = 0;
              if ( ((int (__fastcall *)(struct IPropertyEnumTypeList *, __int64, GUID *, __int64 *))v30->GetAt)(
                     a6,
                     v28,
                     &GUID_11e1fbf9_2d56_4a6b_8db3_7cd193a471f2,
                     &v48) < 0 )
                goto LABEL_37;
              v46 = 0;
              NamedEntityCanonicalName = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v48 + 24LL))(v48, &v46);
              if ( NamedEntityCanonicalName >= 0 && (v46 == 1 || v46 == 3) )
                (*(void (__fastcall **)(__int64, struct tagPROPVARIANT *))(*(_QWORD *)v48 + 40LL))(v48, &pvar);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
              if ( NamedEntityCanonicalName < 0 )
                goto LABEL_37;
              vt = pvar.vt;
            }
            if ( vt )
            {
              v17 = StructuredQuery1::CSchemaFromPropertySystem::WritePropVariantForNamedEntity(
                      &pvar,
                      L"(",
                      L"|F",
                      (wchar_t *)pv,
                      v53,
                      0,
                      0) >= 0;
LABEL_46:
              PropVariantClear((PROPVARIANT *)&pvar);
              goto LABEL_47;
            }
LABEL_37:
            v31 = v53;
            v32 = pv;
            v17 = 1;
            if ( v53 )
            {
              if ( v53 > 0x7FFFFFFF )
              {
                NamedEntityCanonicalName = -2147024809;
                *(_WORD *)pv = 0;
              }
              else
              {
                v33 = 2147483646;
                v34 = L"+F";
                do
                {
                  if ( !v33 )
                    break;
                  if ( !*v34 )
                    break;
                  *v32++ = *v34++;
                  --v33;
                  --v31;
                }
                while ( v31 );
                v35 = v32 - 1;
                if ( v31 )
                  v35 = v32;
                NamedEntityCanonicalName = v31 == 0 ? 0x8007007A : 0;
                *v35 = 0;
              }
            }
            else
            {
              NamedEntityCanonicalName = -2147024809;
            }
            goto LABEL_46;
          }
        }
LABEL_70:
        (*(void (__fastcall **)(void *))(*(_QWORD *)v23 + 16LL))(v23);
        v8 = v62;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)v20 + 16LL))(v20);
    if ( NamedEntityCanonicalName < 0 )
      goto LABEL_6;
    a4 = v63;
  }
  return (unsigned int)_AllocString<CTCoAllocPolicy>((__int64)this, (__int64)a2, (const size_t *)a4, v8);
}

```

## disassembly

```asm
0x180013cbc  mov     [rsp-8+arg_10], rbx
0x180013cc1  push    rbp
0x180013cc2  push    rsi
0x180013cc3  push    rdi
0x180013cc4  push    r12
0x180013cc6  push    r13
0x180013cc8  push    r14
0x180013cca  push    r15
0x180013ccc  lea     rbp, [rsp-9F0h]
0x180013cd4  sub     rsp, 0AF0h
0x180013cdb  mov     rax, cs:__security_cookie
0x180013ce2  xor     rax, rsp
0x180013ce5  mov     [rbp+0A20h+var_40], rax
0x180013cec  cmp     [rbp+0A20h+arg_20], 0Bh
0x180013cf4  mov     rdi, r9
0x180013cf7  mov     r15, [rbp+0A20h+arg_30]
0x180013cfe  mov     r13, rdx
0x180013d01  mov     r12, [rbp+0A20h+arg_28]
0x180013d08  mov     r14, rcx
0x180013d0b  mov     [rbp+0A20h+var_A48], r15
0x180013d0f  mov     [rbp+0A20h+var_A98], rdx
0x180013d13  mov     [rsp+0B20h+var_AC0], rcx
0x180013d18  jnz     short loc_180013D59
0x180013d1a  cmp     r8d, 4
0x180013d1e  jz      short loc_180013D59
0x180013d20  mov     r9, r15
0x180013d23  mov     r8, rdi
0x180013d26  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEB_WPEAPEA_W@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,wchar_t const *,wchar_t * *)
0x180013d2b  mov     ebx, eax
0x180013d2d  mov     eax, ebx
0x180013d2f  mov     rcx, [rbp+0A20h+var_40]
0x180013d36  xor     rcx, rsp; StackCookie
0x180013d39  call    __security_check_cookie
0x180013d3e  mov     rbx, [rsp+0B20h+arg_10]
0x180013d46  add     rsp, 0AF0h
0x180013d4d  pop     r15
0x180013d4f  pop     r14
0x180013d51  pop     r13
0x180013d53  pop     r12
0x180013d55  pop     rdi
0x180013d56  pop     rsi
0x180013d57  pop     rbp
0x180013d58  retn
0x180013d59  mov     rax, [r12]
0x180013d5d  lea     rdx, [rsp+0B20h+var_ADC]
0x180013d62  xor     esi, esi
0x180013d64  mov     rcx, r12
0x180013d67  mov     [rsp+0B20h+var_ADC], esi
0x180013d6b  mov     rax, [rax+18h]
0x180013d6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d74  mov     ebx, eax
0x180013d76  test    eax, eax
0x180013d78  jns     short loc_180013D81
0x180013d7a  xor     edi, edi
0x180013d7c  mov     [r15], rdi
0x180013d7f  jmp     short loc_180013D2D
0x180013d81  cmp     [rsp+0B20h+var_ADC], esi
0x180013d85  jbe     short loc_180013D20
0x180013d87  or      ebx, 0FFFFFFFFh
0x180013d8a  lea     rax, aSystemStructur_17; "System.StructuredQueryType.DateTime"
0x180013d91  mov     [rsp+0B20h+cchCount2], ebx; cchCount2
0x180013d95  mov     r9d, ebx; cchCount1
0x180013d98  mov     r8, rdi; lpString1
0x180013d9b  mov     [rsp+0B20h+lpString2], rax; lpString2
0x180013da0  lea     edx, [rbx+2]; dwCmpFlags
0x180013da3  lea     ecx, [rdx+7Eh]; Locale
0x180013da6  call    cs:__imp_CompareStringW
0x180013dac  cmp     eax, 2
0x180013daf  jz      loc_180013D20
0x180013db5  lea     edx, [rbx+2]; dwCmpFlags
0x180013db8  mov     [rsp+0B20h+cchCount2], ebx; cchCount2
0x180013dbc  lea     rax, aSystemStructur_24; "System.StructuredQueryType.String"
0x180013dc3  mov     r9d, ebx; cchCount1
0x180013dc6  lea     ecx, [rdx+7Eh]; Locale
0x180013dc9  mov     [rsp+0B20h+lpString2], rax; lpString2
0x180013dce  mov     r8, rdi; lpString1
0x180013dd1  call    cs:__imp_CompareStringW
0x180013dd7  cmp     eax, 2
0x180013dda  jz      loc_1800144A1
0x180013de0  lea     edx, [rbx+2]; dwCmpFlags
0x180013de3  mov     [rsp+0B20h+cchCount2], ebx; cchCount2
0x180013de7  lea     rax, aSystemStructur_20; "System.StructuredQueryType.FilePath"
0x180013dee  mov     r9d, ebx; cchCount1
0x180013df1  lea     ecx, [rdx+7Eh]; Locale
0x180013df4  mov     [rsp+0B20h+lpString2], rax; lpString2
0x180013df9  mov     r8, rdi; lpString1
0x180013dfc  call    cs:__imp_CompareStringW
0x180013e02  cmp     eax, 2
0x180013e05  jz      loc_1800144A1
0x180013e0b  mov     eax, esi
0x180013e0d  test    eax, eax
0x180013e0f  lea     rsi, aSystemStructur_23; "System.StructuredQueryType.Object"
0x180013e16  mov     r9, r13
0x180013e19  lea     r8, aSystemStructur_0; "System.StructuredQueryType.Implicit.%s"
0x180013e20  mov     edx, 100h; unsigned __int64
0x180013e25  lea     rcx, [rbp+0A20h+var_A40]; wchar_t *
0x180013e29  cmovz   rsi, rdi
0x180013e2d  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180013e32  xor     edi, edi
0x180013e34  mov     ebx, eax
0x180013e36  test    eax, eax
0x180013e38  js      loc_180013D7C
0x180013e3e  lea     r8, [rbp+0A20h+var_A88]; void **
0x180013e42  mov     [rbp+0A20h+var_A88], rdi
0x180013e46  mov     rcx, rsi; wchar_t *
0x180013e49  call    ?CreateInstance@ConstantString@StructuredQuery1@@SAJPEB_WAEBU_GUID@@PEAPEAX@Z; StructuredQuery1::ConstantString::CreateInstance(wchar_t const *,_GUID const &,void * *)
0x180013e4e  mov     ebx, eax
0x180013e50  test    eax, eax
0x180013e52  js      loc_180013D7C
0x180013e58  mov     rcx, [r14+28h]
0x180013e5c  lea     rsi, _GUID_e90f2096_c488_49bf_a9dd_62d7c84755e5
0x180013e63  mov     r13, [rbp+0A20h+var_A88]
0x180013e67  lea     r9, [rbp+0A20h+var_A80]
0x180013e6b  mov     [rbp+0A20h+var_A80], rdi
0x180013e6f  mov     r8, rsi
0x180013e72  mov     rdx, r13
0x180013e75  mov     rax, [rcx]
0x180013e78  mov     rax, [rax+20h]
0x180013e7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e81  mov     ebx, eax
0x180013e83  test    eax, eax
0x180013e85  js      loc_1800143C1
0x180013e8b  lea     r8, [rbp+0A20h+var_A90]; void **
0x180013e8f  mov     [rbp+0A20h+var_A90], rdi
0x180013e93  lea     rcx, [rbp+0A20h+var_A40]; wchar_t *
0x180013e97  call    ?CreateInstance@ConstantString@StructuredQuery1@@SAJPEB_WAEBU_GUID@@PEAPEAX@Z; StructuredQuery1::ConstantString::CreateInstance(wchar_t const *,_GUID const &,void * *)
0x180013e9c  mov     ebx, eax
0x180013e9e  test    eax, eax
0x180013ea0  js      loc_1800143B1
0x180013ea6  mov     rcx, [r14+28h]
0x180013eaa  lea     r9, [rbp+0A20h+var_AA0]
0x180013eae  mov     r15, [rbp+0A20h+var_A90]
0x180013eb2  mov     r8, rsi
0x180013eb5  mov     [rbp+0A20h+var_AA0], rdi
0x180013eb9  mov     rdx, r15
0x180013ebc  mov     rax, [rcx]
0x180013ebf  mov     rax, [rax+18h]
0x180013ec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ec8  mov     ebx, eax
0x180013eca  test    eax, eax
0x180013ecc  js      loc_18001439E
0x180013ed2  cmp     [rbp+0A20h+var_AA0], rdi
0x180013ed6  jnz     short loc_180013F05
0x180013ed8  mov     rcx, [r14+28h]
0x180013edc  lea     rdx, [rbp+0A20h+var_AA0]
0x180013ee0  mov     r8, [rbp+0A20h+var_A80]
0x180013ee4  mov     r9, rsi
0x180013ee7  mov     [rsp+0B20h+lpString2], rdx
0x180013eec  mov     rdx, r15
0x180013eef  mov     rax, [rcx]
0x180013ef2  mov     rax, [rax+28h]
0x180013ef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013efb  mov     ebx, eax
0x180013efd  test    eax, eax
0x180013eff  js      loc_18001439E
0x180013f05  mov     r13, [rsp+0B20h+var_AC0]
0x180013f0a  mov     r14d, edi
0x180013f0d  mov     r15, [rbp+0A20h+var_A98]
0x180013f11  mov     esi, 400h
0x180013f16  cmp     r14d, [rsp+0B20h+var_ADC]
0x180013f1b  jnb     loc_180014386
0x180013f21  mov     rax, [r12]
0x180013f25  lea     r9, [rsp+0B20h+var_AB8]
0x180013f2a  lea     r8, _GUID_11e1fbf9_2d56_4a6b_8db3_7cd193a471f2
0x180013f31  mov     [rsp+0B20h+var_AB8], rdi
0x180013f36  mov     edx, r14d
0x180013f39  mov     rcx, r12
0x180013f3c  mov     rax, [rax+20h]
0x180013f40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f45  mov     ebx, eax
0x180013f47  test    eax, eax
0x180013f49  js      loc_18001437B
0x180013f4f  mov     rcx, [rsp+0B20h+var_AB8]
0x180013f54  lea     r8, [rsp+0B20h+var_AC8]
0x180013f59  mov     [rsp+0B20h+var_AC8], rdi
0x180013f5e  lea     rdx, _GUID_bb776487_a7a1_425b_8983_31ed23455b68
0x180013f65  mov     rax, [rcx]
0x180013f68  mov     rax, [rax]
0x180013f6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f70  mov     ebx, eax
0x180013f72  test    eax, eax
0x180013f74  js      loc_18001436A
0x180013f7a  mov     rcx, [rsp+0B20h+var_AB8]
0x180013f7f  lea     rdx, [rsp+0B20h+var_AA8]
0x180013f84  mov     [rsp+0B20h+var_AA8], edi
0x180013f88  mov     rax, [rcx]
0x180013f8b  mov     rax, [rax+18h]
0x180013f8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f94  mov     ebx, eax
0x180013f96  test    eax, eax
0x180013f98  js      loc_180014359
0x180013f9e  mov     ecx, [rsp+0B20h+var_AA8]
0x180013fa2  test    ecx, ecx
0x180013fa4  jz      loc_1800143E2
0x180013faa  cmp     ecx, 1
0x180013fad  jnz     loc_180014359
0x180013fb3  mov     rcx, [rsp+0B20h+var_AB8]
0x180013fb8  lea     rdx, [rbp+0A20h+var_A78]
0x180013fbc  xor     eax, eax
0x180013fbe  xorps   xmm0, xmm0
0x180013fc1  mov     [rbp+0A20h+var_A68], rax
0x180013fc5  movups  xmmword ptr [rbp+0A20h+var_A78], xmm0
0x180013fc9  mov     rax, [rcx]
0x180013fcc  mov     rax, [rax+28h]
0x180013fd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fd5  mov     ebx, eax
0x180013fd7  test    eax, eax
0x180013fd9  js      loc_180014359
0x180013fdf  lea     rax, [rbp+0A20h+var_840]
0x180013fe6  mov     [rsp+0B20h+var_AB0], rsi
0x180013feb  mov     [rsp+0B20h+pv], rax
0x180013ff0  lea     r9, [rbp+0A20h+var_840]; wchar_t *
0x180013ff7  lea     rax, [rsp+0B20h+var_AB0]
0x180013ffc  mov     [rsp+0B20h+var_AF0], rax; unsigned __int64 *
0x180014001  lea     r8, asc_18009A524; "|"
0x180014008  lea     rax, [rsp+0B20h+pv]
0x18001400d  mov     qword ptr [rsp+0B20h+cchCount2], rax; wchar_t **
0x180014012  lea     rdx, asc_18009A520; "["
0x180014019  lea     rcx, [rbp+0A20h+var_A78]; struct tagPROPVARIANT *
0x18001401d  mov     [rsp+0B20h+lpString2], rsi; unsigned __int64
0x180014022  call    ?WritePropVariantForNamedEntity@CSchemaFromPropertySystem@StructuredQuery1@@CAJAEBUtagPROPVARIANT@@PEB_W1PEA_W_KPEAPEA_WPEA_K@Z; StructuredQuery1::CSchemaFromPropertySystem::WritePropVariantForNamedEntity(tagPROPVARIANT const &,wchar_t const *,wchar_t const *,wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *)
0x180014027  test    eax, eax
0x180014029  js      loc_180014152
0x18001402f  xor     ecx, ecx
0x180014031  lea     edx, [r14+1]
0x180014035  xorps   xmm0, xmm0
0x180014038  mov     eax, edi
0x18001403a  movups  xmmword ptr [rbp+0A20h+pvar+2], xmm0
0x18001403e  mov     qword ptr [rbp+0A20h+pvar+10h], rcx
0x180014042  mov     word ptr [rbp+0A20h+pvar], ax
0x180014046  cmp     edx, [rsp+0B20h+var_ADC]
0x18001404a  jnb     loc_180014455
0x180014050  mov     rax, [r12]
0x180014054  lea     r9, [rsp+0B20h+var_AD8]
0x180014059  lea     r8, _GUID_11e1fbf9_2d56_4a6b_8db3_7cd193a471f2
0x180014060  mov     [rsp+0B20h+var_AD8], rdi
0x180014065  mov     rcx, r12
0x180014068  mov     rax, [rax+20h]
0x18001406c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014071  test    eax, eax
0x180014073  js      short loc_1800140D1
0x180014075  mov     rcx, [rsp+0B20h+var_AD8]
0x18001407a  lea     rdx, [rsp+0B20h+var_AE0]
0x18001407f  mov     [rsp+0B20h+var_AE0], edi
0x180014083  mov     rax, [rcx]
0x180014086  mov     rax, [rax+18h]
0x18001408a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001408f  mov     ebx, eax
0x180014091  test    eax, eax
0x180014093  js      short loc_1800140B8
0x180014095  mov     ecx, [rsp+0B20h+var_AE0]
0x180014099  sub     ecx, 1
0x18001409c  jz      short loc_1800140A3
0x18001409e  cmp     ecx, 2
0x1800140a1  jnz     short loc_1800140B8
0x1800140a3  mov     rcx, [rsp+0B20h+var_AD8]
0x1800140a8  lea     rdx, [rbp+0A20h+pvar]
0x1800140ac  mov     rax, [rcx]
0x1800140af  mov     rax, [rax+28h]
0x1800140b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140b8  mov     rcx, [rsp+0B20h+var_AD8]
0x1800140bd  mov     rax, [rcx]
0x1800140c0  mov     rax, [rax+10h]
0x1800140c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140c9  test    ebx, ebx
0x1800140cb  jns     loc_180014451
0x1800140d1  mov     rdx, [rsp+0B20h+var_AB0]
0x1800140d6  xor     r10d, r10d
0x1800140d9  mov     r8, [rsp+0B20h+pv]
0x1800140de  mov     r11d, 1
0x1800140e4  mov     edi, r11d
0x1800140e7  test    rdx, rdx
0x1800140ea  jz      loc_180014533
0x1800140f0  cmp     rdx, 7FFFFFFFh
0x1800140f7  ja      loc_180014529
0x1800140fd  mov     eax, 7FFFFFFEh
0x180014102  lea     rcx, asc_18009A534; "+F"
0x180014109  test    rax, rax
0x18001410c  jz      short loc_18001412C
0x18001410e  movzx   r9d, word ptr [rcx]
0x180014112  test    r9w, r9w
0x180014116  jz      short loc_18001412C
0x180014118  mov     [r8], r9w
0x18001411c  add     rcx, 2
0x180014120  add     r8, 2
0x180014124  sub     rax, r11
0x180014127  sub     rdx, r11
0x18001412a  jnz     short loc_180014109
0x18001412c  test    rdx, rdx
0x18001412f  lea     rcx, [r8-2]
0x180014133  cmovnz  rcx, r8
0x180014137  neg     rdx
0x18001413a  sbb     ebx, ebx
0x18001413c  not     ebx
0x18001413e  and     ebx, 8007007Ah
0x180014144  mov     [rcx], r10w
0x180014148  lea     rcx, [rbp+0A20h+pvar]; pvar
0x18001414c  call    cs:__imp_PropVariantClear
0x180014152  lea     rcx, [rbp+0A20h+var_A78]; pvar
0x180014156  call    cs:__imp_PropVariantClear
  ... truncated ...
```
