# StructuredQuery1::CSchemaFromPropertySystem::ProcessProperty(IPropertyDescription *)

- ea: `0x18001c8c4`
- end: `0x18001cf70`
- name: `?ProcessProperty@CSchemaFromPropertySystem@StructuredQuery1@@AEAAJPEAUIPropertyDescription@@@Z`
- size: `1708`
- prototype: `__int64 __fastcall(StructuredQuery1::CSchemaFromPropertySystem *__hidden this, struct IPropertyDescription *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001b4a0`

## callees

- `0x180013cbc`
- `0x180015a40`
- `0x18001c5b4`
- `0x18001c8c4`
- `0x18001dd8c`
- `0x18001e110`
- `0x180051028`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001cc6d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001cc6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cc80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ccff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cd09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cd13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cea0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cc80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ccff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cd09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cd13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cea0`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::CSchemaFromPropertySystem::ProcessProperty(
        StructuredQuery1::CSchemaFromPropertySystem *this,
        struct IPropertyDescription *a2)
{
  struct IPropertyDescriptionVtbl *lpVtbl; // rax
  int v5; // ebx
  struct IPropertyDescriptionVtbl *v6; // rax
  struct IPropertyDescriptionVtbl *v7; // rax
  struct IPropertyDescriptionVtbl *v8; // rax
  struct IPropertyDescriptionVtbl *v9; // rax
  __int64 v10; // rdx
  wchar_t *v11; // r9
  __int64 v12; // rcx
  const WCHAR *v13; // r8
  const struct _GUID *v14; // rdx
  __int64 v15; // rcx
  void *v16; // r12
  __int64 v17; // rcx
  unsigned int i; // esi
  struct IPropertyDescriptionVtbl *v19; // rax
  int v20; // eax
  struct IPropertyDescriptionVtbl *v22; // rax
  bool v23; // zf
  unsigned int v24; // edi
  int v25; // eax
  LPVOID pv; // [rsp+40h] [rbp-49h] BYREF
  struct IMnemonics *v27; // [rsp+48h] [rbp-41h] BYREF
  wchar_t *v28; // [rsp+50h] [rbp-39h] BYREF
  int v29; // [rsp+58h] [rbp-31h] BYREF
  int v30; // [rsp+5Ch] [rbp-2Dh] BYREF
  __int64 v31; // [rsp+60h] [rbp-29h] BYREF
  wchar_t *v32; // [rsp+68h] [rbp-21h] BYREF
  __int64 v33; // [rsp+70h] [rbp-19h] BYREF
  __int64 v34; // [rsp+78h] [rbp-11h] BYREF
  __int64 v35; // [rsp+80h] [rbp-9h] BYREF
  PCNZWCH lpString1; // [rsp+88h] [rbp-1h] BYREF
  struct IPropertyEnumTypeList *v37; // [rsp+90h] [rbp+7h] BYREF
  __int64 v38; // [rsp+98h] [rbp+Fh] BYREF
  int v39; // [rsp+A0h] [rbp+17h] BYREF
  _QWORD v40[7]; // [rsp+A8h] [rbp+1Fh] BYREF
  unsigned __int16 v41; // [rsp+F8h] [rbp+6Fh] BYREF
  void *v42; // [rsp+100h] [rbp+77h] BYREF
  PROPDESC_DISPLAYTYPE v43; // [rsp+108h] [rbp+7Fh] BYREF

  lpVtbl = a2->lpVtbl;
  v38 = 0;
  v5 = 1;
  if ( ((__int64 (__fastcall *)(struct IPropertyDescription *, GUID *, __int64 *))lpVtbl->QueryInterface)(
         a2,
         &GUID_078f91bd_29a2_440f_924e_46a291524520,
         &v38) >= 0 )
  {
    v6 = a2->lpVtbl;
    v37 = 0;
    if ( ((int (__fastcall *)(struct IPropertyDescription *, GUID *, struct IPropertyEnumTypeList **))v6->GetEnumTypeList)(
           a2,
           &GUID_a99400f4_3d84_4557_94ba_1242fb2cc9a6,
           &v37) < 0 )
    {
LABEL_47:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
      return (unsigned int)v5;
    }
    v33 = 0;
    if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v38)(
           v38,
           &GUID_ca2fa078_4c76_418c_bedc_c85525f0915d,
           &v33) < 0 )
    {
LABEL_46:
      ((void (__fastcall *)(struct IPropertyEnumTypeList *))v37->lpVtbl->Release)(v37);
      goto LABEL_47;
    }
    v7 = a2->lpVtbl;
    v28 = 0;
    if ( ((int (__fastcall *)(struct IPropertyDescription *, wchar_t **))v7->GetCanonicalName)(a2, &v28) < 0 )
    {
LABEL_45:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
      goto LABEL_46;
    }
    v8 = a2->lpVtbl;
    v43 = PDDT_STRING;
    if ( ((int (__fastcall *)(struct IPropertyDescription *, PROPDESC_DISPLAYTYPE *))v8->GetDisplayType)(a2, &v43) < 0 )
    {
LABEL_44:
      CoTaskMemFree(v28);
      goto LABEL_45;
    }
    v32 = 0;
    (*(void (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v33 + 32LL))(v33, &v32);
    v9 = a2->lpVtbl;
    v41 = 0;
    if ( ((int (__fastcall *)(struct IPropertyDescription *, unsigned __int16 *))v9->GetPropertyType)(a2, &v41) < 0 )
      goto LABEL_43;
    v11 = v32;
    if ( v32 )
      goto LABEL_16;
    v12 = v41;
    if ( v41 > 0x40u )
    {
      if ( v41 > 0x1012u )
      {
        v12 = (unsigned int)v41 - 4115;
        if ( v41 == 4115 )
          goto LABEL_13;
        v12 = (unsigned int)v41 - 4116;
        if ( v41 == 4116 )
          goto LABEL_13;
        v12 = (unsigned int)v41 - 4117;
        if ( v41 == 4117 )
          goto LABEL_13;
        if ( v41 == 4160 )
          goto LABEL_71;
LABEL_59:
        v13 = L"System.StructuredQueryType.String";
        goto LABEL_14;
      }
      if ( v41 != 4114 )
      {
        v23 = v41 == 4098;
        v12 = (unsigned int)v41 - 4098;
LABEL_62:
        if ( v23 )
          goto LABEL_13;
        v12 = (unsigned int)(v12 - 1);
        if ( !(_DWORD)v12 )
          goto LABEL_13;
        v12 = (unsigned int)(v12 - 2);
        if ( !(_DWORD)v12 )
        {
          v13 = L"System.StructuredQueryType.FloatingPoint";
          goto LABEL_14;
        }
        if ( (_DWORD)v12 == 6 )
        {
          v13 = L"System.StructuredQueryType.Boolean";
LABEL_14:
          v5 = _AllocString<CTCoAllocPolicy>(v12, v10, (const size_t *)v13, &v32);
          if ( v5 >= 0 )
          {
            v11 = v32;
LABEL_16:
            lpString1 = 0;
            v5 = StructuredQuery1::CSchemaFromPropertySystem::ProcessNamedEntities(
                   this,
                   v28,
                   (unsigned int)v43,
                   v11,
                   v41,
                   v37,
                   (wchar_t **)&lpString1);
            if ( v5 >= 0 )
            {
              v42 = 0;
              v5 = StructuredQuery1::ConstantString::CreateInstance(lpString1, v14, &v42);
              if ( v5 >= 0 )
              {
                v15 = *((_QWORD *)this + 5);
                v16 = v42;
                v40[0] = 0;
                v5 = (*(__int64 (__fastcall **)(__int64, void *, GUID *, _QWORD *))(*(_QWORD *)v15 + 32LL))(
                       v15,
                       v42,
                       &GUID_e90f2096_c488_49bf_a9dd_62d7c84755e5,
                       v40);
                if ( v5 >= 0 )
                {
                  v17 = *((_QWORD *)this + 2);
                  v35 = 0;
                  v5 = (*(__int64 (__fastcall **)(__int64, wchar_t *, _QWORD, GUID *, __int64 *))(*(_QWORD *)v17 + 104LL))(
                         v17,
                         v28,
                         v40[0],
                         &GUID_ed956968_15f7_4b07_a79a_f0dc08b7a6b5,
                         &v35);
                  if ( v5 >= 0 )
                  {
                    v31 = 0;
                    v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v35)(
                           v35,
                           &GUID_0d5f4564_b150_41f9_927d_97b1e3c8e1b0,
                           &v31);
                    if ( v5 >= 0 )
                    {
                      v34 = 0;
                      v5 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v33 + 48LL))(
                             v33,
                             &GUID_1f9fc1d0_c39b_4b26_817f_011967d3440e,
                             &v34);
                      if ( v5 >= 0 )
                      {
                        LODWORD(v42) = 0;
                        v5 = (*(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v34 + 24LL))(v34, &v42);
                        for ( i = 0; v5 >= 0; ++i )
                        {
                          if ( i >= (unsigned int)v42 )
                            break;
                          pv = 0;
                          v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, LPVOID *))(*(_QWORD *)v34 + 32LL))(
                                 v34,
                                 i,
                                 &GUID_6f79d558_3e96_4549_a1d1_7d75d2288814,
                                 &pv);
                          if ( v5 >= 0 )
                          {
                            v27 = 0;
                            v5 = (*(__int64 (__fastcall **)(LPVOID, struct IMnemonics **))(*(_QWORD *)pv + 32LL))(
                                   pv,
                                   &v27);
                            if ( v5 >= 0 )
                            {
                              v5 = (*(__int64 (__fastcall **)(__int64, const WCHAR *, struct IMnemonics *))(*(_QWORD *)v35 + 96LL))(
                                     v35,
                                     L"mapsToRelation",
                                     v27);
                              CoTaskMemFree(v27);
                            }
                            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
                          }
                        }
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
                        if ( v5 >= 0 )
                        {
                          v39 = 0;
                          LODWORD(v42) = 0;
                          v5 = ((__int64 (__fastcall *)(struct IPropertyEnumTypeList *, int *))v37->lpVtbl->GetCount)(
                                 v37,
                                 &v39);
                          if ( v5 >= 0 )
                          {
                            v29 = 0;
                            v5 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v38 + 192LL))(v38, &v29);
                            if ( v5 >= 0 )
                            {
                              if ( (v29 & 0xA) == 0 )
                                goto LABEL_37;
                              v27 = 0;
                              v5 = (*(__int64 (__fastcall **)(__int64, GUID *, struct IMnemonics **))(*(_QWORD *)v33 + 24LL))(
                                     v33,
                                     &GUID_d6d9aabf_5336_425a_a4b1_d0ff94bddf75,
                                     &v27);
                              if ( v5 >= 0 )
                              {
                                v30 = 0;
                                v5 = StructuredQuery1::CSchemaFromPropertySystem::ProcessMnemonics(
                                       this,
                                       v27,
                                       &v42,
                                       &v30);
                                if ( v5 >= 0 )
                                {
                                  v19 = a2->lpVtbl;
                                  pv = 0;
                                  v20 = ((__int64 (__fastcall *)(struct IPropertyDescription *, LPVOID *))v19->GetDisplayName)(
                                          a2,
                                          &pv);
                                  v5 = 0;
                                  if ( v20 != -2147467259 )
                                    v5 = v20;
                                  if ( v5 >= 0 )
                                  {
                                    if ( pv && !v30 )
                                      v5 = StructuredQuery1::CSchemaFromPropertySystem::ProcessMnemonic(
                                             this,
                                             pv,
                                             &v42,
                                             1,
                                             v31);
                                    if ( CompareStringW(
                                           0x7Fu,
                                           1u,
                                           lpString1,
                                           -1,
                                           L"System.StructuredQueryType.Boolean",
                                           -1) == 2 )
                                    {
                                      v24 = 0;
                                      if ( v5 >= 0 )
                                      {
                                        do
                                        {
                                          if ( v24 >= 2 )
                                            break;
                                          if ( (unsigned __int64)v24 >= *((_QWORD *)this + 4) )
                                            break;
                                          v25 = StructuredQuery1::CSchemaFromPropertySystem::ProcessBooleanPrefix(
                                                  this,
                                                  off_18008CAB8[2 * v24],
                                                  *(struct StructuredQuery1::IEntityInfo **)(*((_QWORD *)this + 3)
                                                                                           + 8LL * v24),
                                                  v28,
                                                  v27,
                                                  (const wchar_t *)pv);
                                          ++v24;
                                          v5 = v25;
                                        }
                                        while ( v25 >= 0 );
                                      }
                                    }
                                    CoTaskMemFree(pv);
                                  }
                                }
                                (*(void (__fastcall **)(struct IMnemonics *))(*(_QWORD *)v27 + 16LL))(v27);
                                if ( v5 >= 0 )
LABEL_37:
                                  v5 = StructuredQuery1::CSchemaFromPropertySystem::ProcessMnemonic(
                                         this,
                                         v28,
                                         &v42,
                                         2,
                                         v31);
                              }
                            }
                          }
                        }
                      }
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
                    }
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
                  }
                  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v40[0] + 16LL))(v40[0]);
                }
                (*(void (__fastcall **)(void *))(*(_QWORD *)v16 + 16LL))(v16);
              }
              CoTaskMemFree((LPVOID)lpString1);
            }
          }
LABEL_43:
          CoTaskMemFree(v32);
          goto LABEL_44;
        }
        goto LABEL_59;
      }
      goto LABEL_13;
    }
    if ( v41 != 64 )
    {
      if ( v41 > 0x11u )
      {
        v12 = (unsigned int)v41 - 18;
        if ( v41 == 18 )
          goto LABEL_13;
        v12 = (unsigned int)v41 - 19;
        if ( v41 == 19 )
          goto LABEL_13;
        v12 = (unsigned int)v41 - 20;
        if ( v41 == 20 )
          goto LABEL_13;
      }
      else
      {
        if ( v41 == 17 )
          goto LABEL_13;
        if ( v41 != 1 )
        {
          v23 = v41 == 2;
          v12 = (unsigned int)v41 - 2;
          goto LABEL_62;
        }
        v22 = a2->lpVtbl;
        LODWORD(v42) = 0;
        if ( ((int (__fastcall *)(struct IPropertyDescription *, void **))v22->GetGroupingRange)(a2, &v42) < 0 )
          goto LABEL_59;
        v12 = (unsigned int)v42;
        if ( !(_DWORD)v42 )
          goto LABEL_59;
        v12 = (unsigned int)((_DWORD)v42 - 1);
        if ( (_DWORD)v42 == 1 )
          goto LABEL_59;
        v12 = (unsigned int)((_DWORD)v42 - 2);
        if ( (_DWORD)v42 == 2 )
        {
LABEL_13:
          v13 = L"System.StructuredQueryType.Integer";
          goto LABEL_14;
        }
        v12 = (unsigned int)((_DWORD)v42 - 3);
        if ( (_DWORD)v42 == 3 )
          goto LABEL_59;
        v12 = (unsigned int)((_DWORD)v42 - 4);
        if ( (_DWORD)v42 == 4 )
          goto LABEL_71;
      }
      if ( (_DWORD)v12 != 1 )
        goto LABEL_59;
      goto LABEL_13;
    }
LABEL_71:
    v13 = L"System.StructuredQueryType.DateTime";
    goto LABEL_14;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001c8c4  push    rbp
0x18001c8c6  push    rbx
0x18001c8c7  push    rsi
0x18001c8c8  push    rdi
0x18001c8c9  push    r12
0x18001c8cb  push    r13
0x18001c8cd  push    r15
0x18001c8cf  lea     rbp, [rsp-27h]
0x18001c8d4  sub     rsp, 0B0h
0x18001c8db  mov     rax, [rdx]
0x18001c8de  lea     r8, [rbp+57h+var_48]
0x18001c8e2  mov     rdi, rdx
0x18001c8e5  mov     r15, rcx
0x18001c8e8  xor     r13d, r13d
0x18001c8eb  lea     rdx, _GUID_078f91bd_29a2_440f_924e_46a291524520
0x18001c8f2  mov     rcx, rdi
0x18001c8f5  mov     [rbp+57h+var_48], r13
0x18001c8f9  mov     rax, [rax]
0x18001c8fc  mov     ebx, 1
0x18001c901  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c906  test    eax, eax
0x18001c908  js      loc_18001CD49
0x18001c90e  mov     rax, [rdi]
0x18001c911  lea     r8, [rbp+57h+var_50]
0x18001c915  lea     rdx, _GUID_a99400f4_3d84_4557_94ba_1242fb2cc9a6
0x18001c91c  mov     [rbp+57h+var_50], r13
0x18001c920  mov     rcx, rdi
0x18001c923  mov     rax, [rax+0A0h]
0x18001c92a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c92f  test    eax, eax
0x18001c931  js      loc_18001CD39
0x18001c937  mov     rcx, [rbp+57h+var_48]
0x18001c93b  lea     r8, [rbp+57h+var_70]
0x18001c93f  mov     [rbp+57h+var_70], r13
0x18001c943  lea     rdx, _GUID_ca2fa078_4c76_418c_bedc_c85525f0915d
0x18001c94a  mov     rax, [rcx]
0x18001c94d  mov     rax, [rax]
0x18001c950  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c955  test    eax, eax
0x18001c957  js      loc_18001CD29
0x18001c95d  mov     rax, [rdi]
0x18001c960  lea     rdx, [rbp+57h+var_90]
0x18001c964  mov     rcx, rdi
0x18001c967  mov     [rbp+57h+var_90], r13
0x18001c96b  mov     rax, [rax+20h]
0x18001c96f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c974  test    eax, eax
0x18001c976  js      loc_18001CD19
0x18001c97c  mov     rax, [rdi]
0x18001c97f  lea     rdx, [rbp+57h+arg_18]
0x18001c983  mov     rcx, rdi
0x18001c986  mov     [rbp+57h+arg_18], r13d
0x18001c98a  mov     rax, [rax+58h]
0x18001c98e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c993  test    eax, eax
0x18001c995  js      loc_18001CD0F
0x18001c99b  mov     rcx, [rbp+57h+var_70]
0x18001c99f  lea     rdx, [rbp+57h+var_78]
0x18001c9a3  mov     [rbp+57h+var_78], r13
0x18001c9a7  mov     rax, [rcx]
0x18001c9aa  mov     rax, [rax+20h]
0x18001c9ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c9b3  mov     rax, [rdi]
0x18001c9b6  lea     rdx, [rbp+57h+arg_8]
0x18001c9ba  mov     rcx, rdi
0x18001c9bd  mov     [rbp+57h+arg_8], r13w
0x18001c9c2  mov     rax, [rax+28h]
0x18001c9c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c9cb  test    eax, eax
0x18001c9cd  js      loc_18001CD05
0x18001c9d3  mov     r9, [rbp+57h+var_78]
0x18001c9d7  test    r9, r9
0x18001c9da  jnz     short loc_18001CA28
0x18001c9dc  movzx   ecx, [rbp+57h+arg_8]
0x18001c9e0  cmp     ecx, 40h ; '@'
0x18001c9e3  jbe     loc_18001CDC3
0x18001c9e9  mov     eax, 1012h
0x18001c9ee  cmp     ecx, eax
0x18001c9f0  jbe     loc_18001CE07
0x18001c9f6  sub     ecx, 1013h
0x18001c9fc  jz      short loc_18001CA0A
0x18001c9fe  sub     ecx, ebx
0x18001ca00  jz      short loc_18001CA0A
0x18001ca02  sub     ecx, ebx
0x18001ca04  jnz     loc_18001CF62
0x18001ca0a  lea     r8, aSystemStructur_14; "System.StructuredQueryType.Integer"
0x18001ca11  lea     r9, [rbp+57h+var_78]
0x18001ca15  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEB_WPEAPEA_W@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,wchar_t const *,wchar_t * *)
0x18001ca1a  mov     ebx, eax
0x18001ca1c  test    eax, eax
0x18001ca1e  js      loc_18001CD05
0x18001ca24  mov     r9, [rbp+57h+var_78]; wchar_t *
0x18001ca28  mov     r8d, [rbp+57h+arg_18]; enum PROPDESC_DISPLAYTYPE
0x18001ca2c  lea     rax, [rbp+57h+lpString1]
0x18001ca30  mov     rdx, [rbp+57h+var_90]; wchar_t *
0x18001ca34  mov     rcx, r15; this
0x18001ca37  mov     [rsp+0E0h+var_B0], rax; wchar_t **
0x18001ca3c  mov     rax, [rbp+57h+var_50]
0x18001ca40  mov     qword ptr [rsp+0E0h+cchCount2], rax; struct IPropertyEnumTypeList *
0x18001ca45  movzx   eax, [rbp+57h+arg_8]
0x18001ca49  mov     word ptr [rsp+0E0h+lpString2], ax; unsigned __int16
0x18001ca4e  mov     [rbp+57h+lpString1], r13
0x18001ca52  call    ?ProcessNamedEntities@CSchemaFromPropertySystem@StructuredQuery1@@AEAAJPEB_WW4PROPDESC_DISPLAYTYPE@@0GPEAUIPropertyEnumTypeList@@PEAPEA_W@Z; StructuredQuery1::CSchemaFromPropertySystem::ProcessNamedEntities(wchar_t const *,PROPDESC_DISPLAYTYPE,wchar_t const *,ushort,IPropertyEnumTypeList *,wchar_t * *)
0x18001ca57  mov     ebx, eax
0x18001ca59  test    eax, eax
0x18001ca5b  js      loc_18001CD05
0x18001ca61  mov     rcx, [rbp+57h+lpString1]; wchar_t *
0x18001ca65  lea     r8, [rbp+57h+arg_10]; void **
0x18001ca69  mov     [rbp+57h+arg_10], r13
0x18001ca6d  call    ?CreateInstance@ConstantString@StructuredQuery1@@SAJPEB_WAEBU_GUID@@PEAPEAX@Z; StructuredQuery1::ConstantString::CreateInstance(wchar_t const *,_GUID const &,void * *)
0x18001ca72  mov     ebx, eax
0x18001ca74  test    eax, eax
0x18001ca76  js      loc_18001CCFB
0x18001ca7c  mov     rcx, [r15+28h]
0x18001ca80  lea     r9, [rbp+57h+var_38]
0x18001ca84  mov     r12, [rbp+57h+arg_10]
0x18001ca88  lea     r8, _GUID_e90f2096_c488_49bf_a9dd_62d7c84755e5
0x18001ca8f  mov     [rbp+57h+var_38], r13
0x18001ca93  mov     rdx, r12
0x18001ca96  mov     rax, [rcx]
0x18001ca99  mov     rax, [rax+20h]
0x18001ca9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001caa2  mov     ebx, eax
0x18001caa4  test    eax, eax
0x18001caa6  js      loc_18001CCEB
0x18001caac  mov     rcx, [r15+10h]
0x18001cab0  lea     rdx, [rbp+57h+var_60]
0x18001cab4  mov     r8, [rbp+57h+var_38]
0x18001cab8  lea     r9, _GUID_ed956968_15f7_4b07_a79a_f0dc08b7a6b5
0x18001cabf  mov     [rbp+57h+var_60], r13
0x18001cac3  mov     [rsp+0E0h+lpString2], rdx
0x18001cac8  mov     rax, [rcx]
0x18001cacb  mov     rdx, [rbp+57h+var_90]
0x18001cacf  mov     rax, [rax+68h]
0x18001cad3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cad8  mov     ebx, eax
0x18001cada  test    eax, eax
0x18001cadc  js      loc_18001CCDB
0x18001cae2  mov     rcx, [rbp+57h+var_60]
0x18001cae6  lea     r8, [rbp+57h+var_80]
0x18001caea  mov     [rbp+57h+var_80], r13
0x18001caee  lea     rdx, _GUID_0d5f4564_b150_41f9_927d_97b1e3c8e1b0
0x18001caf5  mov     rax, [rcx]
0x18001caf8  mov     rax, [rax]
0x18001cafb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb00  mov     ebx, eax
0x18001cb02  test    eax, eax
0x18001cb04  js      loc_18001CCCB
0x18001cb0a  mov     rcx, [rbp+57h+var_70]
0x18001cb0e  lea     r8, [rbp+57h+var_68]
0x18001cb12  mov     [rbp+57h+var_68], r13
0x18001cb16  lea     rdx, _GUID_1f9fc1d0_c39b_4b26_817f_011967d3440e
0x18001cb1d  mov     rax, [rcx]
0x18001cb20  mov     rax, [rax+30h]
0x18001cb24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb29  mov     ebx, eax
0x18001cb2b  test    eax, eax
0x18001cb2d  js      loc_18001CCBB
0x18001cb33  mov     rcx, [rbp+57h+var_68]
0x18001cb37  lea     rdx, [rbp+57h+arg_10]
0x18001cb3b  mov     dword ptr [rbp+57h+arg_10], r13d
0x18001cb3f  mov     rax, [rcx]
0x18001cb42  mov     rax, [rax+18h]
0x18001cb46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb4b  mov     ebx, eax
0x18001cb4d  mov     esi, r13d
0x18001cb50  test    eax, eax
0x18001cb52  js      short loc_18001CB5D
0x18001cb54  cmp     esi, dword ptr [rbp+57h+arg_10]
0x18001cb57  jb      loc_18001CD89
0x18001cb5d  mov     rcx, [rbp+57h+var_68]
0x18001cb61  mov     rax, [rcx]
0x18001cb64  mov     rax, [rax+10h]
0x18001cb68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb6d  test    ebx, ebx
0x18001cb6f  js      loc_18001CCBB
0x18001cb75  mov     rcx, [rbp+57h+var_50]
0x18001cb79  lea     rdx, [rbp+57h+var_40]
0x18001cb7d  mov     [rbp+57h+var_40], r13d
0x18001cb81  mov     dword ptr [rbp+57h+arg_10], r13d
0x18001cb85  mov     rax, [rcx]
0x18001cb88  mov     rax, [rax+18h]
0x18001cb8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb91  mov     ebx, eax
0x18001cb93  test    eax, eax
0x18001cb95  js      loc_18001CCBB
0x18001cb9b  mov     rcx, [rbp+57h+var_48]
0x18001cb9f  lea     rdx, [rbp+57h+var_88]
0x18001cba3  mov     [rbp+57h+var_88], r13d
0x18001cba7  mov     rax, [rcx]
0x18001cbaa  mov     rax, [rax+0C0h]
0x18001cbb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cbb6  mov     ebx, eax
0x18001cbb8  test    eax, eax
0x18001cbba  js      loc_18001CCBB
0x18001cbc0  test    byte ptr [rbp+57h+var_88], 0Ah
0x18001cbc4  jz      loc_18001CC9A
0x18001cbca  mov     rcx, [rbp+57h+var_70]
0x18001cbce  lea     r8, [rbp+57h+var_98]
0x18001cbd2  mov     [rbp+57h+var_98], r13
0x18001cbd6  lea     rdx, _GUID_d6d9aabf_5336_425a_a4b1_d0ff94bddf75
0x18001cbdd  mov     rax, [rcx]
0x18001cbe0  mov     rax, [rax+18h]
0x18001cbe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cbe9  mov     ebx, eax
0x18001cbeb  test    eax, eax
0x18001cbed  js      loc_18001CCBB
0x18001cbf3  mov     rax, [rbp+57h+var_80]
0x18001cbf7  lea     r9, [rbp+57h+var_84]
0x18001cbfb  mov     rdx, [rbp+57h+var_98]
0x18001cbff  lea     r8, [rbp+57h+arg_10]
0x18001cc03  mov     rcx, r15
0x18001cc06  mov     qword ptr [rsp+0E0h+cchCount2], rax
0x18001cc0b  mov     [rbp+57h+var_84], r13d
0x18001cc0f  call    ?ProcessMnemonics@CSchemaFromPropertySystem@StructuredQuery1@@AEAAJPEAUIMnemonics@@PEAH1W4KEYWORD_PREPARATION_OPTIONS@@PEAUIIndicatorAccumulator@2@@Z; StructuredQuery1::CSchemaFromPropertySystem::ProcessMnemonics(IMnemonics *,int *,int *,KEYWORD_PREPARATION_OPTIONS,StructuredQuery1::IIndicatorAccumulator *)
0x18001cc14  mov     ebx, eax
0x18001cc16  test    eax, eax
0x18001cc18  js      short loc_18001CC86
0x18001cc1a  mov     rax, [rdi]
0x18001cc1d  lea     rdx, [rbp+57h+pv]
0x18001cc21  mov     rcx, rdi
0x18001cc24  mov     [rbp+57h+pv], r13
0x18001cc28  mov     rax, [rax+30h]
0x18001cc2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc31  cmp     eax, 80004005h
0x18001cc36  mov     ebx, r13d
0x18001cc39  cmovnz  ebx, eax
0x18001cc3c  test    ebx, ebx
0x18001cc3e  js      short loc_18001CC86
0x18001cc40  mov     rdx, [rbp+57h+pv]
0x18001cc44  test    rdx, rdx
0x18001cc47  jnz     loc_18001CD5D
0x18001cc4d  mov     r8, [rbp+57h+lpString1]; lpString1
0x18001cc51  lea     rax, aSystemStructur_13; "System.StructuredQueryType.Boolean"
0x18001cc58  or      r9d, 0FFFFFFFFh; cchCount1
0x18001cc5c  mov     [rsp+0E0h+cchCount2], r9d; cchCount2
0x18001cc61  mov     [rsp+0E0h+lpString2], rax; lpString2
0x18001cc66  lea     edx, [r9+2]; dwCmpFlags
0x18001cc6a  lea     ecx, [rdx+7Eh]; Locale
0x18001cc6d  call    cs:__imp_CompareStringW
0x18001cc73  cmp     eax, 2
0x18001cc76  jz      loc_18001CEBB
0x18001cc7c  mov     rcx, [rbp+57h+pv]; pv
0x18001cc80  call    cs:__imp_CoTaskMemFree
0x18001cc86  mov     rcx, [rbp+57h+var_98]
0x18001cc8a  mov     rax, [rcx]
0x18001cc8d  mov     rax, [rax+10h]
0x18001cc91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc96  test    ebx, ebx
0x18001cc98  js      short loc_18001CCBB
0x18001cc9a  mov     rax, [rbp+57h+var_80]
0x18001cc9e  lea     r8, [rbp+57h+arg_10]
0x18001cca2  mov     rdx, [rbp+57h+var_90]
0x18001cca6  mov     r9d, 2
0x18001ccac  mov     rcx, r15
0x18001ccaf  mov     [rsp+0E0h+lpString2], rax
0x18001ccb4  call    ?ProcessMnemonic@CSchemaFromPropertySystem@StructuredQuery1@@AEAAJPEB_WPEAHW4KEYWORD_PREPARATION_OPTIONS@@PEAUIIndicatorAccumulator@2@@Z; StructuredQuery1::CSchemaFromPropertySystem::ProcessMnemonic(wchar_t const *,int *,KEYWORD_PREPARATION_OPTIONS,StructuredQuery1::IIndicatorAccumulator *)
0x18001ccb9  mov     ebx, eax
0x18001ccbb  mov     rcx, [rbp+57h+var_80]
0x18001ccbf  mov     rax, [rcx]
0x18001ccc2  mov     rax, [rax+10h]
0x18001ccc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cccb  mov     rcx, [rbp+57h+var_60]
0x18001cccf  mov     rax, [rcx]
0x18001ccd2  mov     rax, [rax+10h]
0x18001ccd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ccdb  mov     rcx, [rbp+57h+var_38]
0x18001ccdf  mov     rax, [rcx]
0x18001cce2  mov     rax, [rax+10h]
0x18001cce6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cceb  mov     rax, [r12]
0x18001ccef  mov     rcx, r12
0x18001ccf2  mov     rax, [rax+10h]
0x18001ccf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ccfb  mov     rcx, [rbp+57h+lpString1]; pv
0x18001ccff  call    cs:__imp_CoTaskMemFree
0x18001cd05  mov     rcx, [rbp+57h+var_78]; pv
0x18001cd09  call    cs:__imp_CoTaskMemFree
0x18001cd0f  mov     rcx, [rbp+57h+var_90]; pv
0x18001cd13  call    cs:__imp_CoTaskMemFree
0x18001cd19  mov     rcx, [rbp+57h+var_70]
0x18001cd1d  mov     rax, [rcx]
0x18001cd20  mov     rax, [rax+10h]
0x18001cd24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd29  mov     rcx, [rbp+57h+var_50]
0x18001cd2d  mov     rax, [rcx]
0x18001cd30  mov     rax, [rax+10h]
0x18001cd34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd39  mov     rcx, [rbp+57h+var_48]
0x18001cd3d  mov     rax, [rcx]
0x18001cd40  mov     rax, [rax+10h]
0x18001cd44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd49  mov     eax, ebx
0x18001cd4b  add     rsp, 0B0h
0x18001cd52  pop     r15
0x18001cd54  pop     r13
0x18001cd56  pop     r12
0x18001cd58  pop     rdi
0x18001cd59  pop     rsi
0x18001cd5a  pop     rbx
  ... truncated ...
```
