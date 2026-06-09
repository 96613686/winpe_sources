# StructuredQuery1::QueryParser::RestateLeaf(ICondition *,StructuredQuery1::RESTATEMENT_CONTEXT,int,RESTATEMENT_OPTIONS,wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *)

- ea: `0x18002d5f4`
- end: `0x18002e541`
- name: `?RestateLeaf@QueryParser@StructuredQuery1@@AEAAJPEAUICondition@@W4RESTATEMENT_CONTEXT@2@HW4RESTATEMENT_OPTIONS@@PEA_W_KPEAPEA_WPEA_K@Z`
- size: `3917`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002f3e0`

## callees

- `0x180008a50`
- `0x180010620`
- `0x180010804`
- `0x180015a40`
- `0x18002664c`
- `0x18002d5f4`
- `0x18002e548`
- `0x18002e5c0`
- `0x18002e688`
- `0x18002e9ec`
- `0x18002ec44`
- `0x18002f298`
- `0x18002f3e0`
- `0x1800547ac`
- `0x180059be8`
- `0x18005daf0`
- `0x18006d610`
- `0x18006d824`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002dcc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002dd99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e46a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e474`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e47e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e49d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002dcc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002dd99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e46a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e474`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e47e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e49d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d8b5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002dcef`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002dcf9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002e4a7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002d8b5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002dcef`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002dcf9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002e4a7`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::QueryParser::RestateLeaf(
        __int64 a1,
        struct ICondition *a2,
        unsigned __int64 a3,
        unsigned int a4,
        unsigned int a5,
        StructuredQuery1 *a6,
        wchar_t *a7,
        _QWORD *a8,
        wchar_t **a9)
{
  _QWORD *v9; // rbx
  unsigned int v10; // r15d
  struct ICondition *v12; // r14
  unsigned int v13; // esi
  signed int CustomHandler; // edi
  wchar_t **v15; // r9
  struct IConditionVtbl *lpVtbl; // rax
  struct IConditionVtbl *v17; // rax
  int v18; // ebx
  const wchar_t *v19; // r8
  int v20; // eax
  char v21; // bl
  char v22; // al
  char v23; // bl
  char v24; // al
  int v25; // eax
  const struct IEntity *v26; // r14
  StructuredQuery1::QueryExpressionCustomization *v27; // rcx
  __int64 v28; // rsi
  wchar_t *v29; // rax
  LPVOID v30; // rax
  int v31; // eax
  StructuredQuery1::Solution *v32; // r14
  int v33; // eax
  enum tagCONDITION_OPERATION v34; // eax
  char v35; // si
  wchar_t *v36; // rdx
  unsigned __int64 v37; // rax
  wchar_t *v38; // r8
  wchar_t *v39; // rdx
  signed int v40; // eax
  StructuredQuery1 *v41; // r10
  unsigned __int64 v42; // rcx
  const WCHAR *v43; // r12
  __int64 v44; // r15
  unsigned __int64 v45; // r8
  int v46; // ecx
  __int64 v47; // rax
  const wchar_t *v48; // rcx
  unsigned __int64 v49; // r9
  StructuredQuery1 *v50; // r11
  __int64 v51; // rdi
  __int64 v52; // rdx
  StructuredQuery1 *v53; // rcx
  StructuredQuery1 *v54; // r11
  wchar_t *v55; // r8
  __int64 v56; // rax
  const wchar_t *v57; // rcx
  wchar_t *v58; // r9
  StructuredQuery1 *v59; // r10
  __int64 v60; // rdi
  __int64 v61; // rdx
  StructuredQuery1 *v62; // rcx
  __int64 v63; // rax
  StructuredQuery1 *v64; // r11
  wchar_t *v65; // r8
  wchar_t *v66; // r9
  StructuredQuery1 *v67; // r10
  __int64 v68; // rax
  __int64 v69; // rdx
  StructuredQuery1 *v70; // rcx
  __int64 v71; // rax
  int v72; // ebx
  __int64 v73; // rcx
  __int64 v74; // rcx
  __int64 v75; // rcx
  StructuredQuery1 *v77; // [rsp+28h] [rbp-D8h]
  unsigned __int64 *v78; // [rsp+28h] [rbp-D8h]
  unsigned __int64 *v79; // [rsp+28h] [rbp-D8h]
  int v80; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t v81[4]; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t *v82; // [rsp+60h] [rbp-A0h]
  struct ICondition2 *v83; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *v84; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v85; // [rsp+78h] [rbp-88h]
  enum tagCONDITION_OPERATION v86[3]; // [rsp+7Ch] [rbp-84h] BYREF
  LPVOID v87; // [rsp+88h] [rbp-78h] BYREF
  PCNZWCH lpString1; // [rsp+90h] [rbp-70h] BYREF
  int v89; // [rsp+98h] [rbp-68h] BYREF
  int v90; // [rsp+9Ch] [rbp-64h] BYREF
  unsigned int v91; // [rsp+A0h] [rbp-60h]
  wchar_t *v92; // [rsp+A8h] [rbp-58h] BYREF
  struct IInterval *v93; // [rsp+B0h] [rbp-50h] BYREF
  struct ICondition2 *v94; // [rsp+B8h] [rbp-48h] BYREF
  wchar_t *v95; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v96; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v97; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v98; // [rsp+D8h] [rbp-28h] BYREF
  PROPVARIANT v99[2]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD *v100; // [rsp+F0h] [rbp-10h]
  wchar_t **v101; // [rsp+F8h] [rbp-8h]
  struct ICondition *v102; // [rsp+100h] [rbp+0h]
  _QWORD *v103; // [rsp+108h] [rbp+8h]
  PROPVARIANT v104[2]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v105; // [rsp+120h] [rbp+20h]
  PROPVARIANT v106[2]; // [rsp+128h] [rbp+28h] BYREF
  __int64 v107; // [rsp+138h] [rbp+38h]
  PROPVARIANT pvar[2]; // [rsp+140h] [rbp+40h] BYREF
  __int64 v109; // [rsp+150h] [rbp+50h]

  v9 = a8;
  v10 = a4;
  v85 = a4;
  v12 = a2;
  v13 = a3;
  v102 = a2;
  *(_QWORD *)v81 = a6;
  v101 = a9;
  v91 = a3;
  v103 = a8;
  CustomHandler = StructuredQuery1::NullTerminateOutputBuffer(a6, a7, a3);
  if ( CustomHandler >= 0 )
  {
    lpVtbl = v12->lpVtbl;
    v96 = 0;
    v97 = 0;
    v98 = 0;
    CustomHandler = ((__int64 (__fastcall *)(struct ICondition *, __int64 *, __int64 *, __int64 *))lpVtbl->GetInputTerms)(
                      v12,
                      &v96,
                      &v97,
                      &v98);
    if ( CustomHandler < 0 )
    {
LABEL_226:
      v15 = v101;
      goto LABEL_227;
    }
    v95 = 0;
    v100 = 0;
    v17 = v12->lpVtbl;
    v86[0] = COP_IMPLICIT;
    *(_OWORD *)v99 = 0;
    CustomHandler = ((__int64 (__fastcall *)(struct ICondition *, wchar_t **, enum tagCONDITION_OPERATION *, PROPVARIANT *))v17->GetComparisonInfo)(
                      v12,
                      &v95,
                      v86,
                      v99);
    if ( CustomHandler < 0 )
    {
LABEL_220:
      v73 = v96;
      if ( v96 )
      {
        v96 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
      }
      v74 = v97;
      if ( v97 )
      {
        v97 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
      }
      v75 = v98;
      if ( v98 )
      {
        v98 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
      }
      goto LABEL_226;
    }
    v94 = 0;
    v18 = 0;
    v19 = (const wchar_t *)&cchOriginalDestLength;
    v80 = 0;
    if ( v86[0] == COP_VALUE_STARTSWITH )
    {
      v19 = L"~<";
    }
    else
    {
      if ( v86[0] <= COP_VALUE_STARTSWITH )
      {
        if ( v86[0] )
        {
          switch ( v86[0] )
          {
            case COP_EQUAL:
              v19 = L"=";
              break;
            case COP_NOTEQUAL:
              v19 = L"<>";
              break;
            case COP_LESSTHAN:
              v19 = L"<";
              break;
            case COP_GREATERTHAN:
              v19 = L">";
              break;
            case COP_LESSTHANOREQUAL:
              v19 = L"<=";
              break;
            case COP_GREATERTHANOREQUAL:
              v19 = L">=";
              break;
            default:
              goto LABEL_41;
          }
        }
        goto LABEL_19;
      }
      switch ( v86[0] )
      {
        case COP_VALUE_ENDSWITH:
          v19 = L"~>";
          break;
        case COP_VALUE_CONTAINS:
          v19 = L"~~";
          break;
        case COP_VALUE_NOTCONTAINS:
          v19 = L"~!";
          break;
        case COP_DOSWILDCARDS:
          v19 = L"~";
          break;
        case COP_WORD_EQUAL:
          v19 = L"$=";
          if ( (a5 & 1) == 0 )
            v19 = (const wchar_t *)&cchOriginalDestLength;
          break;
        case COP_WORD_STARTSWITH:
          if ( (a5 & 1) == 0 )
          {
            v18 = *(_BYTE *)(a1 + 92) != 0 ? 132 : 68;
            goto LABEL_20;
          }
          v19 = L"$<";
LABEL_19:
          v18 = 4;
LABEL_20:
          v80 = v18;
          goto LABEL_41;
        case COP_APPLICATION_SPECIFIC:
          v19 = L"##";
          goto LABEL_19;
        default:
LABEL_41:
          v92 = 0;
          if ( v97 )
            v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, wchar_t **, _QWORD))(*(_QWORD *)v97 + 24LL))(
                    v97,
                    0,
                    0,
                    &v92,
                    0);
          else
            v20 = _AllocString<CTCoAllocPolicy>(0, 1, (const size_t *)v19, &v92);
          CustomHandler = v20;
          if ( v20 < 0 )
          {
LABEL_219:
            CoTaskMemFree(v95);
            PropVariantClear(v99);
            v9 = v103;
            goto LABEL_220;
          }
          v84 = 0;
          v87 = 0;
          LODWORD(v82) = 1;
          if ( v98 )
          {
            v109 = 0;
            *(_OWORD *)pvar = 0;
            CustomHandler = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, wchar_t **, PROPVARIANT *))(*(_QWORD *)v98 + 24LL))(
                              v98,
                              0,
                              0,
                              &v84,
                              pvar);
            if ( CustomHandler < 0 )
              goto LABEL_217;
            if ( LOWORD(pvar[0]) == 3 )
            {
              if ( ((__int64)pvar[1] & 1) != 0 )
                v21 = v18 | 1;
              else
                v21 = v18 & 0xFE;
              v22 = v21;
              v23 = v21 | 8;
              v24 = v22 & 0xF7;
              if ( ((__int64)pvar[1] & 8) == 0 )
                v23 = v24;
              if ( ((__int64)pvar[1] & 2) != 0 )
                LOBYTE(v18) = v23 | 0x40;
              else
                LOBYTE(v18) = v23 & 0xBF;
            }
            PropVariantClear(pvar);
            goto LABEL_115;
          }
          lpString1 = 0;
          v25 = ((__int64 (__fastcall *)(struct ICondition *, PCNZWCH *))v12->lpVtbl->GetValueType)(v12, &lpString1);
          v26 = 0;
          CustomHandler = v25;
          if ( v25 < 0 )
            goto LABEL_217;
          if ( lpString1 )
            v26 = (const struct IEntity *)SemanticsUM::FindElementByName<SemanticsUM::Entity>(
                                            lpString1,
                                            *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 104) + 8LL) + 40LL),
                                            *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 104) + 8LL) + 32LL));
          v27 = *(StructuredQuery1::QueryExpressionCustomization **)(a1 + 112);
          *(_QWORD *)&v86[1] = 0;
          CustomHandler = StructuredQuery1::QueryExpressionCustomization::GetCustomHandler(
                            v27,
                            v26,
                            (struct IConditionGenerator **)&v86[1]);
          if ( CustomHandler < 0 )
          {
LABEL_113:
            CoTaskMemFree((LPVOID)lpString1);
            if ( CustomHandler < 0 )
              goto LABEL_217;
            v12 = v102;
LABEL_115:
            if ( v94 )
            {
              v33 = StructuredQuery1::QueryParser::RestateInternal(a1, v94, v13, v10, a5, *(_QWORD *)v81, a7, v81, &a7);
LABEL_216:
              CustomHandler = v33;
LABEL_217:
              CoTaskMemFree(v84);
              CoTaskMemFree(v87);
              CoTaskMemFree(v92);
              if ( v94 )
                ((void (__fastcall *)(struct ICondition2 *))v94->lpVtbl->Release)(v94);
              goto LABEL_219;
            }
            v34 = v86[0];
            if ( v86[0] == COP_VALUE_NOTCONTAINS && v13 == 2 )
            {
              CustomHandler = StructuredQuery1::RestatementStringCchCopy(
                                *(StructuredQuery1 **)v81,
                                a7,
                                (unsigned __int64)L"(",
                                v81,
                                &a7,
                                (unsigned __int64 *)v77);
              v35 = 1;
              if ( CustomHandler < 0 )
                goto LABEL_217;
              v34 = v86[0];
            }
            else
            {
              v35 = 0;
            }
            if ( v34 == COP_VALUE_NOTCONTAINS )
            {
              v77 = (StructuredQuery1 *)v81;
              CustomHandler = StructuredQuery1::QueryParser::RestateConnective(a1, 2, a5, *(_QWORD *)v81, a7);
              if ( CustomHandler < 0 )
                goto LABEL_217;
            }
            if ( !v10 )
            {
              v36 = v95;
              if ( v95 )
              {
                if ( StructuredQuery1::QueryParser::IsDefaultPropertyName((StructuredQuery1::QueryParser *)a1, v95, v12) )
                  v36 = 0;
                else
                  v36 = v95;
              }
              v77 = *(StructuredQuery1 **)v81;
              CustomHandler = StructuredQuery1::QueryParser::WritePropertyTextAndAfter(a1, v36, v96, a5, 0);
              if ( CustomHandler < 0 )
                goto LABEL_217;
            }
            v37 = -1;
            v38 = v92;
            v39 = a7;
            if ( *(_QWORD *)v81 )
            {
              v40 = StringCchCopyExW(
                      *(wchar_t **)v81,
                      (unsigned __int64)a7,
                      v92,
                      (wchar_t **)v81,
                      (unsigned __int64 *)&a7,
                      (unsigned int)v77);
              v38 = v92;
              CustomHandler = v40;
              v37 = (unsigned __int64)a7;
              v41 = *(StructuredQuery1 **)v81;
            }
            else
            {
              v41 = 0;
              *(_QWORD *)v81 = 0;
              v42 = -1;
              do
                ++v42;
              while ( v92[v42] );
              if ( (unsigned __int64)a7 >= v42 )
                v37 = (unsigned __int64)a7 - v42;
              a7 = (wchar_t *)v37;
              CustomHandler = (unsigned __int64)v39 < v42 ? 0x80070216 : 0;
            }
            if ( CustomHandler < 0 )
              goto LABEL_217;
            if ( *(_DWORD *)(a1 + 80) == 2 && *v38 )
            {
              CustomHandler = StructuredQuery1::RestatementStringCchCopy(
                                v41,
                                (wchar_t *)v37,
                                (unsigned __int64)L" ",
                                v81,
                                &a7,
                                (unsigned __int64 *)v77);
              if ( CustomHandler < 0 )
                goto LABEL_217;
              v37 = (unsigned __int64)a7;
              v41 = *(StructuredQuery1 **)v81;
            }
            v43 = L"*";
            if ( (v18 & 0x10) != 0 )
            {
              CustomHandler = StructuredQuery1::RestatementStringCchCopy(
                                v41,
                                (wchar_t *)v37,
                                (unsigned __int64)L"*",
                                v81,
                                &a7,
                                (unsigned __int64 *)v77);
              if ( CustomHandler < 0 )
                goto LABEL_217;
              v37 = (unsigned __int64)a7;
              v41 = *(StructuredQuery1 **)v81;
            }
            v44 = 2147483646;
            if ( (v18 & 1) == 0 )
            {
LABEL_165:
              CustomHandler = StructuredQuery1::_WriteValueText(
                                (wchar_t *)v41,
                                (wchar_t *)v37,
                                v84,
                                (const wchar_t *)(unsigned int)v82,
                                (wchar_t **)v81,
                                &a7);
              if ( CustomHandler < 0 )
                goto LABEL_217;
              if ( (v18 & 0x20) != 0 )
              {
                CustomHandler = StructuredQuery1::RestatementStringCchCopy(
                                  *(StructuredQuery1 **)v81,
                                  a7,
                                  (unsigned __int64)L"*",
                                  v81,
                                  &a7,
                                  v78);
                if ( CustomHandler < 0 )
                  goto LABEL_217;
              }
              if ( (v18 & 1) != 0 && (v18 & 8) == 0 )
              {
                v54 = *(StructuredQuery1 **)v81;
                v55 = a7;
                if ( *(_QWORD *)v81 )
                {
                  if ( a7 )
                  {
                    if ( (unsigned __int64)a7 <= 0x7FFFFFFF )
                    {
                      v56 = 2147483646;
                      v57 = L"\"";
                      v58 = a7;
                      v59 = *(StructuredQuery1 **)v81;
                      v60 = 0;
                      do
                      {
                        if ( !v56 )
                          break;
                        if ( !*v57 )
                          break;
                        *(_WORD *)v59 = *v57++;
                        v59 = (StructuredQuery1 *)((char *)v59 + 2);
                        --v56;
                        ++v60;
                        v58 = (wchar_t *)((char *)v58 - 1);
                      }
                      while ( v58 );
                      v61 = v60 - 1;
                      v62 = (StructuredQuery1 *)((char *)v59 - 2);
                      if ( v58 )
                        v61 = v60;
                      CustomHandler = v58 == 0 ? 0x8007007A : 0;
                      if ( v58 )
                        v62 = v59;
                      *(_WORD *)v62 = 0;
                      *(_QWORD *)v81 = (char *)v54 + 2 * v61;
                      a7 = (wchar_t *)((char *)v55 - v61);
                    }
                    else
                    {
                      CustomHandler = -2147024809;
                      **(_WORD **)v81 = 0;
                    }
                  }
                  else
                  {
                    CustomHandler = -2147024809;
                  }
                }
                else
                {
                  *(_QWORD *)v81 = 0;
                  v63 = (__int64)a7 - 1;
                  if ( !a7 )
                    v63 = -1;
                  CustomHandler = a7 == 0 ? 0x80070216 : 0;
                  a7 = (wchar_t *)v63;
                }
                if ( CustomHandler < 0 )
                  goto LABEL_217;
              }
              if ( (v18 & 0x40) != 0 )
              {
                v64 = *(StructuredQuery1 **)v81;
                v65 = a7;
                if ( *(_QWORD *)v81 )
                {
                  if ( a7 )
                  {
                    if ( (unsigned __int64)a7 <= 0x7FFFFFFF )
                    {
                      v66 = a7;
                      v67 = *(StructuredQuery1 **)v81;
                      v68 = 0;
                      do
                      {
                        if ( !v44 )
                          break;
                        if ( !*v43 )
                          break;
                        *(_WORD *)v67 = *v43++;
                        v67 = (StructuredQuery1 *)((char *)v67 + 2);
                        --v44;
                        ++v68;
                        v66 = (wchar_t *)((char *)v66 - 1);
                      }
                      while ( v66 );
                      v69 = v68 - 1;
                      v70 = (StructuredQuery1 *)((char *)v67 - 2);
                      if ( v66 )
                        v69 = v68;
                      CustomHandler = v66 == 0 ? 0x8007007A : 0;
                      if ( v66 )
                        v70 = v67;
                      *(_WORD *)v70 = 0;
                      *(_QWORD *)v81 = (char *)v64 + 2 * v69;
                      a7 = (wchar_t *)((char *)v65 - v69);
                    }
                    else
                    {
                      CustomHandler = -2147024809;
                      **(_WORD **)v81 = 0;
                    }
                  }
                  else
                  {
                    CustomHandler = -2147024809;
                  }
                }
                else
                {
                  *(_QWORD *)v81 = 0;
                  v71 = (__int64)a7 - 1;
                  if ( !a7 )
                    v71 = -1;
                  CustomHandler = a7 == 0 ? 0x80070216 : 0;
                  a7 = (wchar_t *)v71;
                }
                if ( CustomHandler < 0 )
                  goto LABEL_217;
              }
              if ( v87 )
              {
                CustomHandler = StructuredQuery1::RestatementStringCchCopy(
                                  *(StructuredQuery1 **)v81,
                                  a7,
                                  (unsigned __int64)L" .. ",
                                  v81,
                                  &a7,
                                  v78);
                if ( CustomHandler < 0 )
                  goto LABEL_217;
                v72 = v18 & 2;
                if ( v72 )
                {
                  CustomHandler = StructuredQuery1::RestatementStringCchCopy(
                                    *(StructuredQuery1 **)v81,
                                    a7,
                                    (unsigned __int64)L"\"",
                                    v81,
                                    &a7,
                                    v79);
                  if ( CustomHandler < 0 )
                    goto LABEL_217;
                }
                CustomHandler = StructuredQuery1::RestatementStringCchCopy(
                                  *(StructuredQuery1 **)v81,
                                  a7,
                                  (unsigned __int64)v87,
                                  v81,
                                  &a7,
                                  v79);
                if ( CustomHandler < 0 )
                  goto LABEL_217;
                if ( v72 )
                {
                  CustomHandler = StructuredQuery1::RestatementStringCchCopy(
                                    *(StructuredQuery1 **)v81,
                                    a7,
                                    (unsigned __int64)L"\"",
                                    v81,
                                    &a7,
                                    v78);
                  if ( CustomHandler < 0 )
                    goto LABEL_217;
                }
              }
              if ( !v35 )
                goto LABEL_217;
              v33 = StructuredQuery1::RestatementStringCchCopy(
                      *(StructuredQuery1 **)v81,
                      a7,
                      (unsigned __int64)L")",
                      v81,
                      &a7,
                      v78);
              goto LABEL_216;
            }
            v45 = v37;
            if ( v41 )
            {
              v46 = (int)v82;
              if ( !v37 )
              {
                CustomHandler = -2147024809;
                goto LABEL_164;
              }
              if ( v37 > 0x7FFFFFFF )
              {
                CustomHandler = -2147024809;
                *(_WORD *)v41 = 0;
                v37 = (unsigned __int64)a7;
                v41 = *(StructuredQuery1 **)v81;
                LODWORD(v82) = v46;
                goto LABEL_164;
              }
              v47 = 2147483646;
              v48 = L"\"";
              v49 = v45;
              v50 = v41;
              v51 = 0;
              do
              {
                if ( !v47 )
                  break;
                if ( !*v48 )
                  break;
                *(_WORD *)v50 = *v48++;
                v50 = (StructuredQuery1 *)((char *)v50 + 2);
                --v47;
                ++v51;
                --v49;
              }
              while ( v49 );
              v52 = v51 - 1;
              v53 = (StructuredQuery1 *)((char *)v50 - 2);
              if ( v49 )
                v52 = v51;
              CustomHandler = v49 != 0 ? 0 : 0x8007007A;
              v41 = (StructuredQuery1 *)((char *)v41 + 2 * v52);
              if ( v49 )
                v53 = v50;
              v37 = v45 - v52;
              *(_WORD *)v53 = 0;
              *(_QWORD *)v81 = v41;
            }
            else
            {
              --v37;
              *(_QWORD *)v81 = 0;
              v41 = 0;
              if ( !v45 )
                v37 = -1;
              CustomHandler = v45 == 0 ? 0x80070216 : 0;
            }
            a7 = (wchar_t *)v37;
LABEL_164:
            if ( CustomHandler < 0 )
              goto LABEL_217;
            goto LABEL_165;
          }
          v28 = *(_QWORD *)&v86[1];
          if ( *(_QWORD *)&v86[1] )
          {
            if ( LOWORD(v99[0]) == 4127 && LODWORD(v99[1]) == 2 )
            {
              CustomHandler = StructuredQuery1::DefaultPhraseFromNamedEntity(v26, *v100, a5, *(_QWORD *)&v86[1], &v84);
              if ( CustomHandler >= 0 )
              {
                if ( v84 )
                {
                  v18 &= ~1u;
                  LODWORD(v82) = 0;
                  v80 = v18;
                }
                CustomHandler = StructuredQuery1::DefaultPhraseFromNamedEntity(v26, v100[1], a5, v28, &v87);
              }
            }
            else if ( LOWORD(v99[0]) == 31 )
            {
              CustomHandler = StructuredQuery1::DefaultPhraseFromNamedEntity(v26, v99[1], a5, *(_QWORD *)&v86[1], &v84);
              if ( CustomHandler >= 0 )
              {
                if ( !v84 )
                  goto LABEL_69;
                v18 &= ~1u;
                LODWORD(v82) = 0;
                v80 = v18;
              }
            }
          }
          if ( v84 )
          {
LABEL_110:
            if ( v28 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
            v13 = v91;
            goto LABEL_113;
          }
LABEL_69:
          v93 = 0;
          if ( LOWORD(v99[0]) != 13
            || (**(int (__fastcall ***)(PROPVARIANT, GUID *, struct IInterval **))v99[1])(
                 v99[1],
                 &GUID_6bf0a714_3c18_430b_8b5d_83b1c234d3db,
                 &v93) < 0 )
          {
LABEL_103:
            if ( CustomHandler < 0
              || v84
              || v94
              || (LODWORD(v83) = 0,
                  CustomHandler = StructuredQuery1::ValueNormalization(v99, a5 & 1, 0, &v83, &v84),
                  CustomHandler < 0) )
            {
              v10 = v85;
            }
            else
            {
              StructuredQuery1::QueryParser::AddQuotesAsNeeded(a1, (unsigned int)v83, 1, &v80);
              LOBYTE(v18) = v80;
              v10 = v85;
              if ( (v80 & 0x81) == 0x81 )
                LOBYTE(v18) = v80 | 0x40;
            }
            goto LABEL_110;
          }
          v89 = 0;
          v105 = 0;
          v107 = 0;
          *(_OWORD *)v104 = 0;
          v90 = 0;
          *(_OWORD *)v106 = 0;
          CustomHandler = ((__int64 (__fastcall *)(struct IInterval *, int *, PROPVARIANT *, int *, PROPVARIANT *))v93->lpVtbl->GetLimits)(
                            v93,
                            &v89,
                            v104,
                            &v90,
                            v106);
          if ( CustomHandler < 0 )
          {
LABEL_102:
            ((void (__fastcall *)(struct IInterval *))v93->lpVtbl->Release)(v93);
            goto LABEL_103;
          }
          if ( v89 || v90 )
          {
            *(_QWORD *)&v86[1] = 0;
            CustomHandler = StructuredQuery1::Solution::Create((struct StructuredQuery1::Solution **)&v86[1]);
            if ( CustomHandler >= 0 )
            {
              v83 = 0;
              v31 = ((__int64 (__fastcall *)(struct ICondition *, GUID *, struct ICondition2 **))v102->lpVtbl->QueryInterface)(
                      v102,
                      &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
                      &v83);
              v32 = *(StructuredQuery1::Solution **)&v86[1];
              CustomHandler = v31;
              if ( v31 >= 0 )
              {
                LODWORD(v109) = 0;
                *(_OWORD *)pvar = 0;
                CustomHandler = ((__int64 (__fastcall *)(struct ICondition2 *, PROPVARIANT *, _QWORD, _QWORD))v83->lpVtbl->GetLeafConditionInfo)(
                                  v83,
                                  pvar,
                                  0,
                                  0);
                if ( CustomHandler >= 0 )
                {
                  *(_QWORD *)&v86[1] = 0;
                  CustomHandler = ((__int64 (__fastcall *)(struct ICondition2 *, enum tagCONDITION_OPERATION *))v83->lpVtbl->GetLocale)(
                                    v83,
                                    &v86[1]);
                  if ( CustomHandler >= 0 )
                  {
                    CustomHandler = StructuredQuery1::Solution::ResolveRange(
                                      v32,
                                      v93,
                                      v83,
                                      SQRO_DONT_REMOVE_UNRESTRICTED_KEYWORDS|SQRO_DONT_MAP_RELATIONS|SQRO_DONT_RESOLVE_DATETIME,
                                      (const struct _tagpropertykey *)pvar,
                                      v86[0],
                                      lpString1,
                                      *(const wchar_t **)&v86[1],
                                      &v94);
                    CoTaskMemFree(*(LPVOID *)&v86[1]);
                  }
                }
                ((void (__fastcall *)(struct ICondition2 *))v83->lpVtbl->Release)(v83);
              }
              (*(void (__fastcall **)(StructuredQuery1::Solution *))(*(_QWORD *)v32 + 16LL))(v32);
            }
            goto LABEL_101;
          }
          if ( v28 )
          {
            CustomHandler = (*(__int64 (__fastcall **)(__int64, PCNZWCH, PROPVARIANT *, _QWORD, wchar_t **))(*(_QWORD *)v28 + 48LL))(
                              v28,
                              lpString1,
                              v104,
                              a5,
                              &v84);
            if ( CustomHandler < 0 )
              goto LABEL_101;
            v29 = v84;
            if ( !v84 )
              goto LABEL_84;
            v18 &= ~1u;
            LODWORD(v82) = 0;
            v80 = v18;
          }
          else
          {
            v29 = v84;
          }
          if ( v29 )
          {
LABEL_86:
            if ( v28 )
            {
              CustomHandler = (*(__int64 (__fastcall **)(__int64, PCNZWCH, PROPVARIANT *, _QWORD, LPVOID *))(*(_QWORD *)v28 + 48LL))(
                                v28,
                                lpString1,
                                v106,
                                a5,
                                &v87);
              if ( CustomHandler < 0 )
                goto LABEL_101;
              v30 = v87;
              if ( !v87 )
                goto LABEL_92;
              v18 &= ~1u;
              LODWORD(v82) = 0;
              v80 = v18;
            }
            else
            {
              v30 = v87;
            }
            if ( !v30 )
            {
LABEL_92:
              LODWORD(v83) = 0;
              CustomHandler = StructuredQuery1::ValueNormalization(v106, a5 & 1, 0, &v83, &v87);
              if ( CustomHandler >= 0 )
              {
                StructuredQuery1::QueryParser::AddQuotesAsNeeded(a1, (unsigned int)v83, 2, &v80);
                LOBYTE(v18) = v80;
              }
            }
LABEL_101:
            PropVariantClear(v104);
            PropVariantClear(v106);
            goto LABEL_102;
          }
LABEL_84:
          LODWORD(v83) = 0;
          CustomHandler = StructuredQuery1::ValueNormalization(v104, a5 & 1, 0, &v83, &v84);
          if ( CustomHandler < 0 )
            goto LABEL_101;
          StructuredQuery1::QueryParser::AddQuotesAsNeeded(a1, (unsigned int)v83, 1, &v80);
          v18 = v80;
          goto LABEL_86;
      }
    }
    v80 = 1;
    v18 = 1;
    goto LABEL_41;
  }
LABEL_227:
  if ( v9 )
    *v9 = *(_QWORD *)v81;
  if ( v15 )
    *v15 = a7;
  return (unsigned int)CustomHandler;
}

```

## disassembly

```asm
0x18002d5f4  push    rbp
0x18002d5f6  push    rbx
0x18002d5f7  push    rsi
0x18002d5f8  push    rdi
0x18002d5f9  push    r12
0x18002d5fb  push    r13
0x18002d5fd  push    r14
0x18002d5ff  push    r15
0x18002d601  lea     rbp, [rsp-68h]
0x18002d606  sub     rsp, 168h
0x18002d60d  mov     rax, cs:__security_cookie
0x18002d614  xor     rax, rsp
0x18002d617  mov     [rbp+0A0h+var_48], rax
0x18002d61b  mov     rbx, [rbp+0A0h+arg_38]
0x18002d622  mov     r15d, r9d
0x18002d625  mov     [rsp+1A0h+var_128], r9d
0x18002d62a  mov     r13, rcx
0x18002d62d  mov     rcx, [rbp+0A0h+arg_28]; this
0x18002d634  mov     r14, rdx
0x18002d637  mov     r9, [rbp+0A0h+arg_40]
0x18002d63e  mov     esi, r8d
0x18002d641  mov     [rbp+0A0h+var_A0], rdx
0x18002d645  mov     rdx, [rbp+0A0h+arg_30]; wchar_t *
0x18002d64c  mov     qword ptr [rsp+1A0h+var_148], rcx
0x18002d651  mov     [rbp+0A0h+var_A8], r9
0x18002d655  mov     [rbp+0A0h+var_100], r8d
0x18002d659  mov     [rbp+0A0h+var_98], rbx
0x18002d65d  call    ?NullTerminateOutputBuffer@StructuredQuery1@@YAJPEA_W_K@Z; StructuredQuery1::NullTerminateOutputBuffer(wchar_t *,unsigned __int64)
0x18002d662  xor     r12d, r12d
0x18002d665  mov     edi, eax
0x18002d667  test    eax, eax
0x18002d669  js      loc_18002E503
0x18002d66f  mov     rax, [r14]
0x18002d672  lea     r9, [rbp+0A0h+var_C8]
0x18002d676  lea     r8, [rbp+0A0h+var_D0]
0x18002d67a  mov     [rbp+0A0h+var_D8], r12
0x18002d67e  lea     rdx, [rbp+0A0h+var_D8]
0x18002d682  mov     [rbp+0A0h+var_D0], r12
0x18002d686  mov     rcx, r14
0x18002d689  mov     [rbp+0A0h+var_C8], r12
0x18002d68d  mov     rax, [rax+68h]
0x18002d691  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d696  mov     edi, eax
0x18002d698  test    eax, eax
0x18002d69a  js      loc_18002E4FF
0x18002d6a0  xor     eax, eax
0x18002d6a2  mov     [rbp+0A0h+var_E0], r12
0x18002d6a6  mov     [rbp+0A0h+var_B0], rax
0x18002d6aa  lea     r9, [rbp+0A0h+var_C0]
0x18002d6ae  mov     rax, [r14]
0x18002d6b1  lea     r8, [rsp+1A0h+var_124]
0x18002d6b6  xorps   xmm0, xmm0
0x18002d6b9  mov     dword ptr [rsp+1A0h+var_124], r12d
0x18002d6be  lea     rdx, [rbp+0A0h+var_E0]
0x18002d6c2  mov     rcx, r14
0x18002d6c5  movups  xmmword ptr [rbp+0A0h+var_C0], xmm0
0x18002d6c9  mov     rax, [rax+50h]
0x18002d6cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d6d2  mov     edi, eax
0x18002d6d4  test    eax, eax
0x18002d6d6  js      loc_18002E4B4
0x18002d6dc  mov     ecx, dword ptr [rsp+1A0h+var_124]
0x18002d6e0  lea     edx, [r12+1]
0x18002d6e5  mov     [rbp+0A0h+var_E8], r12
0x18002d6e9  mov     ebx, r12d
0x18002d6ec  mov     r12d, [rbp+0A0h+arg_20]
0x18002d6f3  lea     r8, cchOriginalDestLength
0x18002d6fa  mov     [rsp+1A0h+var_150], ebx
0x18002d6fe  cmp     ecx, 7
0x18002d701  jz      short loc_18002D767
0x18002d703  jg      short loc_18002D770
0x18002d705  test    ecx, ecx
0x18002d707  jz      short loc_18002D759
0x18002d709  sub     ecx, edx
0x18002d70b  jz      short loc_18002D752
0x18002d70d  sub     ecx, edx
0x18002d70f  jz      short loc_18002D749
0x18002d711  sub     ecx, edx
0x18002d713  jz      short loc_18002D740
0x18002d715  sub     ecx, edx
0x18002d717  jz      short loc_18002D737
0x18002d719  sub     ecx, edx
0x18002d71b  jz      short loc_18002D72E
0x18002d71d  cmp     ecx, edx
0x18002d71f  jnz     loc_18002D7EF
0x18002d725  lea     r8, asc_1800A0768; ">="
0x18002d72c  jmp     short loc_18002D759
0x18002d72e  lea     r8, asc_1800A075C; "<="
0x18002d735  jmp     short loc_18002D759
0x18002d737  lea     r8, asc_1800A0764; ">"
0x18002d73e  jmp     short loc_18002D759
0x18002d740  lea     r8, asc_1800A0758; "<"
0x18002d747  jmp     short loc_18002D759
0x18002d749  lea     r8, asc_18009AA1C; "<>"
0x18002d750  jmp     short loc_18002D759
0x18002d752  lea     r8, asc_18009AA0C; "="
0x18002d759  mov     ebx, 4
0x18002d75e  mov     [rsp+1A0h+var_150], ebx
0x18002d762  jmp     loc_18002D7EF
0x18002d767  lea     r8, asc_18009B558; "~<"
0x18002d76e  jmp     short loc_18002D7E9
0x18002d770  sub     ecx, 8
0x18002d773  jz      short loc_18002D7E2
0x18002d775  sub     ecx, edx
0x18002d777  jz      short loc_18002D7D9
0x18002d779  sub     ecx, edx
0x18002d77b  jz      short loc_18002D7D0
0x18002d77d  sub     ecx, edx
0x18002d77f  jz      short loc_18002D7C7
0x18002d781  sub     ecx, edx
0x18002d783  jz      short loc_18002D7B4
0x18002d785  sub     ecx, edx
0x18002d787  jz      short loc_18002D796
0x18002d789  cmp     ecx, edx
0x18002d78b  jnz     short loc_18002D7EF
0x18002d78d  lea     r8, asc_1800A07A0; "##"
0x18002d794  jmp     short loc_18002D759
0x18002d796  test    dl, r12b
0x18002d799  jz      short loc_18002D7A4
0x18002d79b  lea     r8, asc_1800A078C; "$<"
0x18002d7a2  jmp     short loc_18002D759
0x18002d7a4  mov     al, [r13+5Ch]
0x18002d7a8  neg     al
0x18002d7aa  sbb     ebx, ebx
0x18002d7ac  and     ebx, 40h
0x18002d7af  add     ebx, 44h ; 'D'
0x18002d7b2  jmp     short loc_18002D75E
0x18002d7b4  mov     rax, r8
0x18002d7b7  test    dl, r12b
0x18002d7ba  lea     r8, asc_1800A0794; "$="
0x18002d7c1  cmovz   r8, rax
0x18002d7c5  jmp     short loc_18002D7E9
0x18002d7c7  lea     r8, asc_1800A0780; "~"
0x18002d7ce  jmp     short loc_18002D7E9
0x18002d7d0  lea     r8, asc_1800A0784; "~!"
0x18002d7d7  jmp     short loc_18002D7E9
0x18002d7d9  lea     r8, asc_1800A0770; "~~"
0x18002d7e0  jmp     short loc_18002D7E9
0x18002d7e2  lea     r8, asc_1800A0778; "~>"
0x18002d7e9  mov     [rsp+1A0h+var_150], edx
0x18002d7ed  mov     ebx, edx
0x18002d7ef  mov     rcx, [rbp+0A0h+var_D0]
0x18002d7f3  lea     r9, [rbp+0A0h+var_F8]
0x18002d7f7  mov     [rbp+0A0h+var_F8], 0
0x18002d7ff  test    rcx, rcx
0x18002d802  jz      short loc_18002D820
0x18002d804  mov     rax, [rcx]
0x18002d807  xor     r8d, r8d
0x18002d80a  xor     edx, edx
0x18002d80c  mov     [rsp+1A0h+var_180], 0
0x18002d815  mov     rax, [rax+18h]
0x18002d819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d81e  jmp     short loc_18002D825
0x18002d820  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEB_WPEAPEA_W@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,wchar_t const *,wchar_t * *)
0x18002d825  mov     edi, eax
0x18002d827  xor     eax, eax
0x18002d829  test    edi, edi
0x18002d82b  js      loc_18002E499
0x18002d831  mov     rcx, [rbp+0A0h+var_C8]
0x18002d835  mov     [rsp+1A0h+var_130], rax
0x18002d83a  mov     [rbp+0A0h+var_118], rax
0x18002d83e  mov     dword ptr [rsp+1A0h+var_140], 1
0x18002d846  test    rcx, rcx
0x18002d849  jz      short loc_18002D8C0
0x18002d84b  mov     [rbp+0A0h+var_50], rax
0x18002d84f  lea     rdx, [rbp+0A0h+pvar]
0x18002d853  xorps   xmm0, xmm0
0x18002d856  mov     [rsp+1A0h+var_180], rdx
0x18002d85b  movups  xmmword ptr [rbp+0A0h+pvar], xmm0
0x18002d85f  mov     rax, [rcx]
0x18002d862  lea     r9, [rsp+1A0h+var_130]
0x18002d867  xor     r8d, r8d
0x18002d86a  xor     edx, edx
0x18002d86c  mov     rax, [rax+18h]
0x18002d870  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d875  mov     edi, eax
0x18002d877  test    eax, eax
0x18002d879  js      loc_18002E465
0x18002d87f  cmp     word ptr [rbp+0A0h+pvar], 3
0x18002d884  jnz     short loc_18002D8B1
0x18002d886  mov     edx, dword ptr [rbp+0A0h+pvar+8]
0x18002d889  test    dl, 1
0x18002d88c  jz      short loc_18002D893
0x18002d88e  or      ebx, 1
0x18002d891  jmp     short loc_18002D896
0x18002d893  and     ebx, 0FFFFFFFEh
0x18002d896  mov     eax, ebx
0x18002d898  or      ebx, 8
0x18002d89b  and     eax, 0FFFFFFF7h
0x18002d89e  test    dl, 8
0x18002d8a1  cmovz   ebx, eax
0x18002d8a4  test    dl, 2
0x18002d8a7  jz      short loc_18002D8AE
0x18002d8a9  or      ebx, 40h
0x18002d8ac  jmp     short loc_18002D8B1
0x18002d8ae  and     ebx, 0FFFFFFBFh
0x18002d8b1  lea     rcx, [rbp+0A0h+pvar]; pvar
0x18002d8b5  call    cs:__imp_PropVariantClear
0x18002d8bb  jmp     loc_18002DDAB
0x18002d8c0  mov     [rbp+0A0h+lpString1], rax
0x18002d8c4  lea     rdx, [rbp+0A0h+lpString1]
0x18002d8c8  mov     rax, [r14]
0x18002d8cb  mov     rcx, r14
0x18002d8ce  mov     rax, [rax+58h]
0x18002d8d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d8d7  xor     r14d, r14d
0x18002d8da  mov     edi, eax
0x18002d8dc  test    eax, eax
0x18002d8de  js      loc_18002E465
0x18002d8e4  mov     rcx, [rbp+0A0h+lpString1]; lpString1
0x18002d8e8  test    rcx, rcx
0x18002d8eb  jz      short loc_18002D905
0x18002d8ed  mov     rax, [r13+68h]
0x18002d8f1  mov     rdx, [rax+8]
0x18002d8f5  mov     r8d, [rdx+20h]
0x18002d8f9  mov     rdx, [rdx+28h]
0x18002d8fd  call    ??$FindElementByName@VEntity@SemanticsUM@@@SemanticsUM@@YAPEBVEntity@0@PEB_WPEBV10@K@Z; SemanticsUM::FindElementByName<SemanticsUM::Entity>(wchar_t const *,SemanticsUM::Entity const *,ulong)
0x18002d902  mov     r14, rax
0x18002d905  mov     rcx, [r13+70h]; this
0x18002d909  lea     r8, [rbp+0A0h+var_124+4]; struct IConditionGenerator **
0x18002d90d  mov     rdx, r14; struct IEntity *
0x18002d910  mov     qword ptr [rbp+0A0h+var_124+4], 0
0x18002d918  call    ?GetCustomHandler@QueryExpressionCustomization@StructuredQuery1@@QEBAJPEBVIEntity@SemanticsUM@@PEAPEAUIConditionGenerator@@@Z; StructuredQuery1::QueryExpressionCustomization::GetCustomHandler(SemanticsUM::IEntity const *,IConditionGenerator * *)
0x18002d91d  mov     edi, eax
0x18002d91f  test    eax, eax
0x18002d921  js      loc_18002DD95
0x18002d927  mov     rsi, qword ptr [rbp+0A0h+var_124+4]
0x18002d92b  test    rsi, rsi
0x18002d92e  jz      short loc_18002D9A6
0x18002d930  mov     eax, 101Fh
0x18002d935  cmp     word ptr [rbp+0A0h+var_C0], ax
0x18002d939  jnz     loc_18002DA9B
0x18002d93f  cmp     dword ptr [rbp+0A0h+var_C0+8], 2
0x18002d943  jnz     loc_18002DA9B
0x18002d949  mov     rdx, [rbp+0A0h+var_B0]
0x18002d94d  lea     rax, [rsp+1A0h+var_130]
0x18002d952  mov     r9, rsi
0x18002d955  mov     [rsp+1A0h+var_180], rax
0x18002d95a  mov     r8d, r12d
0x18002d95d  mov     rcx, r14
0x18002d960  mov     rdx, [rdx]
0x18002d963  call    ?DefaultPhraseFromNamedEntity@StructuredQuery1@@YAJPEBVEntity@SemanticsUM@@PEB_WW4RESTATEMENT_OPTIONS@@PEAUIConditionGenerator@@PEAPEA_W@Z; StructuredQuery1::DefaultPhraseFromNamedEntity(SemanticsUM::Entity const *,wchar_t const *,RESTATEMENT_OPTIONS,IConditionGenerator *,wchar_t * *)
0x18002d968  mov     edi, eax
0x18002d96a  test    eax, eax
0x18002d96c  js      short loc_18002D9A6
0x18002d96e  cmp     [rsp+1A0h+var_130], 0
0x18002d974  jz      short loc_18002D985
0x18002d976  and     ebx, 0FFFFFFFEh
0x18002d979  mov     dword ptr [rsp+1A0h+var_140], 0
0x18002d981  mov     [rsp+1A0h+var_150], ebx
0x18002d985  mov     rdx, [rbp+0A0h+var_B0]
0x18002d989  lea     rax, [rbp+0A0h+var_118]
0x18002d98d  mov     r9, rsi
0x18002d990  mov     [rsp+1A0h+var_180], rax
0x18002d995  mov     r8d, r12d
0x18002d998  mov     rcx, r14
0x18002d99b  mov     rdx, [rdx+8]
0x18002d99f  call    ?DefaultPhraseFromNamedEntity@StructuredQuery1@@YAJPEBVEntity@SemanticsUM@@PEB_WW4RESTATEMENT_OPTIONS@@PEAUIConditionGenerator@@PEAPEA_W@Z; StructuredQuery1::DefaultPhraseFromNamedEntity(SemanticsUM::Entity const *,wchar_t const *,RESTATEMENT_OPTIONS,IConditionGenerator *,wchar_t * *)
0x18002d9a4  mov     edi, eax
0x18002d9a6  xor     r14d, r14d
0x18002d9a9  cmp     [rsp+1A0h+var_130], r14
0x18002d9ae  jnz     loc_18002DD7E
0x18002d9b4  mov     r15d, r12d
0x18002d9b7  mov     [rbp+0A0h+var_F0], r14
0x18002d9bb  and     r15d, 1
0x18002d9bf  cmp     word ptr [rbp+0A0h+var_C0], 0Dh
0x18002d9c4  jnz     loc_18002DD0F
0x18002d9ca  mov     rcx, [rbp+0A0h+var_C0+8]
0x18002d9ce  lea     r8, [rbp+0A0h+var_F0]
0x18002d9d2  lea     rdx, _GUID_6bf0a714_3c18_430b_8b5d_83b1c234d3db
0x18002d9d9  mov     rax, [rcx]
0x18002d9dc  mov     rax, [rax]
0x18002d9df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d9e4  test    eax, eax
0x18002d9e6  js      loc_18002DD0F
0x18002d9ec  mov     rcx, [rbp+0A0h+var_F0]
0x18002d9f0  lea     rdx, [rbp+0A0h+var_78]
0x18002d9f4  xor     eax, eax
0x18002d9f6  mov     [rbp+0A0h+var_108], r14d
0x18002d9fa  xorps   xmm0, xmm0
0x18002d9fd  mov     [rbp+0A0h+var_80], rax
0x18002da01  mov     [rbp+0A0h+var_68], rax
0x18002da05  lea     r9, [rbp+0A0h+var_104]
0x18002da09  movups  xmmword ptr [rbp+0A0h+var_90], xmm0
0x18002da0d  mov     [rbp+0A0h+var_104], r14d
0x18002da11  lea     r8, [rbp+0A0h+var_90]
0x18002da15  movups  xmmword ptr [rbp+0A0h+var_78], xmm0
0x18002da19  mov     rax, [rcx]
0x18002da1c  mov     [rsp+1A0h+var_180], rdx
0x18002da21  lea     rdx, [rbp+0A0h+var_108]
0x18002da25  mov     rax, [rax+18h]
0x18002da29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002da2e  mov     edi, eax
0x18002da30  test    eax, eax
0x18002da32  js      loc_18002DCFF
0x18002da38  cmp     [rbp+0A0h+var_108], r14d
0x18002da3c  jnz     loc_18002DBDF
0x18002da42  cmp     [rbp+0A0h+var_104], r14d
0x18002da46  jnz     loc_18002DBDF
0x18002da4c  test    rsi, rsi
  ... truncated ...
```
