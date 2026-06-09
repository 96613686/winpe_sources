# StructuredQuery1::ValueNormalization(tagPROPVARIANT const *,StructuredQuery1::VALUE_NORMALIZATION_STYLE,PROPDESC_FORMAT_FLAGS,StructuredQuery1::VALUE_NORMALIZATION_RESULT *,wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *)

- ea: `0x180024ea4`
- end: `0x180025404`
- name: `?ValueNormalization@StructuredQuery1@@YAJPEBUtagPROPVARIANT@@W4VALUE_NORMALIZATION_STYLE@1@W4PROPDESC_FORMAT_FLAGS@@PEAW4VALUE_NORMALIZATION_RESULT@1@PEA_W_KPEAPEA_WPEA_K@Z`
- size: `1376`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800243c0`
- `0x18002664c`

## callees

- `0x180023e60`
- `0x1800243c0`
- `0x180024ea4`
- `0x18002540c`
- `0x180025a9c`
- `0x18002e5c0`
- `0x18005daf0`
- `0x18007aa70`
- `0x18008b010`

## import_xrefs

- `OLEAUT32!__imp_VarDateFromUdate` at `0x180025202`
- `OLEAUT32!__imp_VarDateFromUdate` at `0x180025202`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800251e0`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800251e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002514c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800252d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002514c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800252d6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180089051`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18008905b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180089051`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18008905b`
- `PROPSYS!PropVariantToStringAlloc` at `0x18002529e`
- `PROPSYS!PropVariantToStringAlloc` at `0x180025302`
- `PROPSYS!PropVariantToStringAlloc` at `0x18002529e`
- `PROPSYS!PropVariantToStringAlloc` at `0x180025302`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::ValueNormalization(
        unsigned __int16 *a1,
        unsigned int a2,
        __int64 a3,
        _DWORD *a4,
        wchar_t *a5,
        unsigned __int64 a6,
        wchar_t **a7,
        unsigned __int64 *a8)
{
  wchar_t *v8; // rsi
  unsigned __int64 *v10; // r11
  bool v12; // zf
  __int64 v13; // rdx
  const wchar_t *v14; // rcx
  char v15; // r15
  unsigned __int64 v16; // rdi
  __int64 v17; // rax
  unsigned __int64 v18; // r8
  wchar_t *v19; // r9
  __int64 v20; // r10
  __int64 v21; // rdx
  wchar_t *v22; // rcx
  signed int v23; // ebx
  unsigned int v24; // ecx
  char v25; // r12
  const wchar_t *v26; // rcx
  unsigned __int64 v27; // r9
  wchar_t *v28; // r8
  int v29; // r13d
  signed int v30; // eax
  __int64 v31; // rdx
  wchar_t *v32; // rcx
  const wchar_t *v34; // rdx
  unsigned __int64 v35; // r8
  wchar_t *v36; // r9
  __int64 v37; // rax
  __int64 v38; // r10
  __int64 v39; // rcx
  __int64 v40; // r8
  signed int v41; // eax
  unsigned int v42; // ecx
  unsigned int v43; // ecx
  unsigned int v44; // ecx
  __int64 v45; // rdx
  __int64 v46; // r8
  int DoesBlurbNeedQuotes; // eax
  const wchar_t *v48; // r8
  const wchar_t *v49; // rax
  unsigned int v50; // ecx
  unsigned int v51; // ecx
  unsigned int v52; // ecx
  unsigned int v53; // ecx
  int (__fastcall ***v54)(_QWORD, GUID *, DATE *); // rcx
  signed int v55; // eax
  unsigned int v56; // [rsp+28h] [rbp-D8h]
  unsigned int v57; // [rsp+28h] [rbp-D8h]
  unsigned int v58; // [rsp+40h] [rbp-C0h]
  wchar_t *v59; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v61; // [rsp+58h] [rbp-A8h]
  unsigned __int64 *v62; // [rsp+60h] [rbp-A0h]
  DATE pdateOut; // [rsp+68h] [rbp-98h] BYREF
  int v64; // [rsp+70h] [rbp-90h] BYREF
  const wchar_t *v65; // [rsp+78h] [rbp-88h]
  _DWORD *v66; // [rsp+80h] [rbp-80h]
  wchar_t **v67; // [rsp+88h] [rbp-78h]
  PROPVARIANT pvar[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v69; // [rsp+A0h] [rbp-60h]
  struct _SYSTEMTIME SystemTime; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v71; // [rsp+B8h] [rbp-48h]
  _BYTE v72[528]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v73[528]; // [rsp+2D0h] [rbp+1D0h] BYREF

  v8 = a5;
  v10 = a8;
  v66 = a4;
  v12 = a2 == 2;
  v67 = a7;
  v13 = a2 == 2;
  v61 = a3;
  v59 = a5;
  v62 = a8;
  v14 = (const wchar_t *)&cchOriginalDestLength;
  *a4 = 0;
  v58 = v12;
  v65 = (const wchar_t *)&cchOriginalDestLength;
  if ( a2 - 2 > 1 )
  {
    v15 = 0;
  }
  else
  {
    v15 = 1;
    if ( a2 == 2 )
    {
      if ( *a1 == 2
        || *a1 == 3
        || *a1 == 5
        || *a1 == 11
        || *a1 == 17
        || *a1 == 18
        || *a1 == 19
        || (unsigned int)*a1 - 20 < 2 )
      {
        v14 = (const wchar_t *)&cchOriginalDestLength;
      }
      else
      {
        v14 = L"'";
        v65 = L"'";
      }
    }
  }
  v16 = a6;
  if ( !a6 )
  {
    v23 = -2147024809;
    goto LABEL_23;
  }
  if ( a6 <= 0x7FFFFFFF )
  {
    v17 = 2147483646;
    v18 = a6;
    v19 = a5;
    v20 = 0;
    do
    {
      if ( !v17 )
        break;
      if ( !*v14 )
        break;
      *v19++ = *v14++;
      --v17;
      ++v20;
      --v18;
    }
    while ( v18 );
    v21 = v20 - 1;
    v22 = v19 - 1;
    if ( v18 )
      v21 = v20;
    v23 = v18 == 0 ? 0x8007007A : 0;
    v8 = &a5[v21];
    v12 = v18 == 0;
    v59 = v8;
    a3 = v61;
    if ( !v12 )
      v22 = v19;
    v16 -= v21;
    v13 = v58;
    a6 = v16;
    *v22 = 0;
LABEL_23:
    if ( v23 < 0 )
      goto LABEL_39;
    v24 = *a1;
    v25 = 1;
    if ( v24 > 0x1F )
    {
      if ( v24 == 64 )
      {
        SystemTime = 0;
        LOWORD(v71) = 0;
        if ( FileTimeToSystemTime((const FILETIME *)a1 + 1, &SystemTime) )
        {
          pdateOut = 0.0;
          v23 = VarDateFromUdate((UDATE *)&SystemTime, 0, &pdateOut);
          if ( v23 < 0 )
            goto LABEL_38;
          v40 = v61;
          goto LABEL_56;
        }
LABEL_70:
        v29 = v58;
        goto LABEL_71;
      }
      if ( v24 != 4127 )
        goto LABEL_70;
      if ( *((_DWORD *)a1 + 2) == 2 )
      {
        v23 = StructuredQuery1::WriteSqlString(**((const wchar_t ***)a1 + 2), v13, v8, v16, &v59, &a6);
        if ( v23 < 0 || (v23 = StringCchCopyExW(v59, a6, L" .. ", &v59, &a6, v57), v23 < 0) )
        {
          v16 = a6;
          v8 = v59;
          goto LABEL_38;
        }
        v27 = a6;
        v28 = v59;
        v26 = *(const wchar_t **)(*((_QWORD *)a1 + 2) + 8LL);
        goto LABEL_29;
      }
    }
    else
    {
      if ( v24 == 31 )
      {
        if ( !v15 )
          *v66 = StructuredQuery1::DoesBlurbNeedQuotes(*((_QWORD *)a1 + 1), v13, a3);
        v26 = (const wchar_t *)*((_QWORD *)a1 + 1);
        v27 = v16;
        v28 = v8;
LABEL_29:
        v29 = v58;
        v30 = StructuredQuery1::WriteSqlString(v26, v58, v28, v27, &v59, &a6);
        v16 = a6;
        v23 = v30;
        v8 = v59;
        goto LABEL_30;
      }
      if ( v24 <= 0xB )
      {
        if ( v24 == 11 )
        {
          if ( a1[4] )
          {
            v49 = L"true";
            v48 = L"TRUE";
          }
          else
          {
            v48 = (const wchar_t *)L"FALSE";
            v49 = L"false";
          }
          if ( !v15 )
            v48 = v49;
        }
        else if ( *a1 )
        {
          v42 = v24 - 1;
          if ( v42 )
          {
            v43 = v42 - 1;
            if ( !v43 || (v44 = v43 - 1) == 0 || (v39 = v44 - 2, !(_DWORD)v39) )
            {
LABEL_67:
              pv = 0;
              v23 = PropVariantToStringAlloc((const PROPVARIANT *const)a1, (PWSTR *)&pv);
              if ( v23 < 0 )
                goto LABEL_38;
              v23 = StringCchCopyExW(v8, v16, (const wchar_t *)pv, &v59, &a6, v56);
              CoTaskMemFree(pv);
              goto LABEL_58;
            }
            if ( (_DWORD)v39 == 2 )
            {
              v40 = (unsigned int)a3 | 0x40;
LABEL_56:
              v41 = StructuredQuery1::WriteDateTime(v39, a2, v40, v8, v16, &v59, &a6);
LABEL_57:
              v23 = v41;
LABEL_58:
              v8 = v59;
              v16 = a6;
LABEL_59:
              v29 = v58;
LABEL_30:
              if ( v23 >= 0 )
                goto LABEL_31;
LABEL_38:
              v10 = v62;
              goto LABEL_39;
            }
            goto LABEL_70;
          }
          v48 = (const wchar_t *)&cchOriginalDestLength;
        }
        else
        {
          v48 = L"[]";
        }
        v41 = StringCchCopyExW(v8, v16, v48, &v59, &a6, v56);
        goto LABEL_57;
      }
      v50 = v24 - 13;
      if ( v50 )
      {
        v51 = v50 - 4;
        if ( !v51 )
          goto LABEL_67;
        v52 = v51 - 1;
        if ( !v52 )
          goto LABEL_67;
        v53 = v52 - 1;
        if ( !v53 || v53 - 1 <= 1 )
          goto LABEL_67;
        goto LABEL_70;
      }
      v54 = (int (__fastcall ***)(_QWORD, GUID *, DATE *))*((_QWORD *)a1 + 1);
      pdateOut = 0.0;
      if ( (**v54)(v54, &GUID_6bf0a714_3c18_430b_8b5d_83b1c234d3db, &pdateOut) >= 0 )
      {
        v64 = 0;
        v71 = 0;
        v69 = 0;
        SystemTime = 0;
        LODWORD(pv) = 0;
        *(_OWORD *)pvar = 0;
        v23 = (*(__int64 (__fastcall **)(_QWORD, int *, struct _SYSTEMTIME *, LPVOID *, PROPVARIANT *))(**(_QWORD **)&pdateOut + 24LL))(
                *(_QWORD *)&pdateOut,
                &v64,
                &SystemTime,
                &pv,
                pvar);
        if ( v23 >= 0 )
        {
          if ( v64 || (_DWORD)pv )
          {
            v25 = 0;
          }
          else
          {
            v23 = StructuredQuery1::ValueNormalization(&SystemTime, a2, v61, v73, 260, 0, 0);
            if ( v23 >= 0 )
            {
              v23 = StructuredQuery1::ValueNormalization(pvar, a2, v61, v72, 260, 0, 0);
              if ( v23 >= 0 )
              {
                v55 = StringCchPrintfExW(v8, v16, &v59, &a6, 0, L"%s .. %s", v73, v72);
                v16 = a6;
                v23 = v55;
                v8 = v59;
              }
            }
          }
          PropVariantClear((PROPVARIANT *)&SystemTime);
          PropVariantClear(pvar);
        }
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&pdateOut + 16LL))(*(_QWORD *)&pdateOut);
        goto LABEL_59;
      }
    }
    v29 = v58;
    v25 = 0;
LABEL_31:
    if ( v25 )
    {
LABEL_45:
      if ( v16 )
      {
        if ( v16 > 0x7FFFFFFF )
        {
          v23 = -2147024809;
          *v8 = 0;
        }
        else
        {
          v34 = v65;
          v35 = v16;
          v36 = v8;
          v37 = 0;
          v38 = 2147483646;
          do
          {
            if ( !v38 )
              break;
            if ( !*v34 )
              break;
            *v36++ = *v34++;
            --v38;
            ++v37;
            --v35;
          }
          while ( v35 );
          v31 = v37 - 1;
          v32 = v36 - 1;
          if ( v35 )
            v31 = v37;
          v8 += v31;
          v23 = v35 == 0 ? 0x8007007A : 0;
          if ( v35 )
            v32 = v36;
          v16 -= v31;
          *v32 = 0;
        }
      }
      else
      {
        v23 = -2147024809;
      }
      goto LABEL_38;
    }
LABEL_71:
    pv = 0;
    v23 = PropVariantToStringAlloc((const PROPVARIANT *const)a1, (PWSTR *)&pv);
    if ( v23 < 0 )
      goto LABEL_38;
    if ( !v15 )
    {
      DoesBlurbNeedQuotes = StructuredQuery1::DoesBlurbNeedQuotes(pv, v45, v46);
      *v66 = DoesBlurbNeedQuotes;
    }
    v23 = StructuredQuery1::WriteSqlString((const wchar_t *)pv, v29, v8, v16, &v59, &a6);
    CoTaskMemFree(pv);
    v16 = a6;
    v8 = v59;
    if ( v23 < 0 )
      goto LABEL_38;
    goto LABEL_45;
  }
  *a5 = 0;
  v23 = -2147024809;
LABEL_39:
  if ( v67 )
    *v67 = v8;
  if ( v10 )
    *v10 = v16;
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x180024ea4  push    rbp
0x180024ea6  push    rbx
0x180024ea7  push    rsi
0x180024ea8  push    rdi
0x180024ea9  push    r12
0x180024eab  push    r13
0x180024ead  push    r14
0x180024eaf  push    r15
0x180024eb1  lea     rbp, [rsp-3F8h]
0x180024eb9  sub     rsp, 4F8h
0x180024ec0  mov     rax, cs:__security_cookie
0x180024ec7  xor     rax, rsp
0x180024eca  mov     [rbp+430h+var_50], rax
0x180024ed1  mov     rsi, [rbp+430h+arg_20]
0x180024ed8  mov     r13d, edx
0x180024edb  mov     r11, [rbp+430h+arg_38]
0x180024ee2  xor     r12d, r12d
0x180024ee5  mov     r14, rcx
0x180024ee8  mov     [rbp+430h+var_4B0], r9
0x180024eec  mov     rcx, [rbp+430h+arg_30]
0x180024ef3  cmp     r13d, 2
0x180024ef7  mov     edx, r12d
0x180024efa  mov     [rbp+430h+var_4A8], rcx
0x180024efe  setz    dl
0x180024f01  mov     [rsp+530h+var_4D8], r8d
0x180024f06  lea     eax, [r13-2]
0x180024f0a  mov     [rsp+530h+var_4E8], rsi
0x180024f0f  mov     [rsp+530h+var_4D0], r11
0x180024f14  lea     rcx, cchOriginalDestLength
0x180024f1b  mov     [r9], r12d
0x180024f1e  mov     [rsp+530h+var_4F0], edx
0x180024f22  mov     [rsp+530h+var_4B8], rcx
0x180024f27  cmp     eax, 1
0x180024f2a  ja      loc_180025330
0x180024f30  mov     r15b, 1
0x180024f33  cmp     r13d, 2
0x180024f37  jnz     short loc_180024F9A
0x180024f39  movzx   ecx, word ptr [r14]
0x180024f3d  sub     ecx, r13d
0x180024f40  jz      loc_1800252E1
0x180024f46  sub     ecx, 1
0x180024f49  jz      loc_1800252E1
0x180024f4f  sub     ecx, r13d
0x180024f52  jz      loc_1800252E1
0x180024f58  sub     ecx, 6
0x180024f5b  jz      loc_1800252E1
0x180024f61  sub     ecx, 6
0x180024f64  jz      loc_1800252E1
0x180024f6a  sub     ecx, 1
0x180024f6d  jz      loc_1800252E1
0x180024f73  sub     ecx, 1
0x180024f76  jz      loc_1800252E1
0x180024f7c  sub     ecx, 1
0x180024f7f  jz      loc_1800252E1
0x180024f85  cmp     ecx, 1
0x180024f88  jz      loc_1800252E1
0x180024f8e  lea     rcx, asc_18009AA08; "'"
0x180024f95  mov     [rsp+530h+var_4B8], rcx
0x180024f9a  mov     rdi, [rbp+430h+arg_28]
0x180024fa1  mov     r9d, 80070057h
0x180024fa7  test    rdi, rdi
0x180024faa  jz      loc_180025344
0x180024fb0  cmp     rdi, 7FFFFFFFh
0x180024fb7  ja      loc_180025338
0x180024fbd  mov     eax, 7FFFFFFEh
0x180024fc2  mov     r8, rdi
0x180024fc5  mov     r9, rsi
0x180024fc8  mov     r10, r12
0x180024fcb  test    rax, rax
0x180024fce  jz      short loc_180024FF0
0x180024fd0  movzx   edx, word ptr [rcx]
0x180024fd3  test    dx, dx
0x180024fd6  jz      short loc_180024FF0
0x180024fd8  mov     [r9], dx
0x180024fdc  add     rcx, 2
0x180024fe0  add     r9, 2
0x180024fe4  dec     rax
0x180024fe7  inc     r10
0x180024fea  sub     r8, 1
0x180024fee  jnz     short loc_180024FCB
0x180024ff0  test    r8, r8
0x180024ff3  lea     rdx, [r10-1]
0x180024ff7  mov     rax, r8
0x180024ffa  lea     rcx, [r9-2]
0x180024ffe  cmovnz  rdx, r10
0x180025002  neg     rax
0x180025005  sbb     ebx, ebx
0x180025007  not     ebx
0x180025009  and     ebx, 8007007Ah
0x18002500f  lea     rsi, [rsi+rdx*2]
0x180025013  test    r8, r8
0x180025016  mov     [rsp+530h+var_4E8], rsi
0x18002501b  mov     r8d, [rsp+530h+var_4D8]
0x180025020  cmovnz  rcx, r9
0x180025024  sub     rdi, rdx
0x180025027  mov     edx, [rsp+530h+var_4F0]
0x18002502b  mov     [rbp+430h+arg_28], rdi
0x180025032  mov     [rcx], r12w
0x180025036  test    ebx, ebx
0x180025038  js      loc_1800250E3
0x18002503e  movzx   ecx, word ptr [r14]
0x180025042  mov     r12b, 1
0x180025045  cmp     ecx, 1Fh
0x180025048  ja      loc_1800251C2
0x18002504e  jnz     loc_18002525B
0x180025054  test    r15b, r15b
0x180025057  jz      loc_1800253D3
0x18002505d  mov     rcx, [r14+8]
0x180025061  mov     r9, rdi
0x180025064  mov     r8, rsi
0x180025067  mov     r13d, [rsp+530h+var_4F0]
0x18002506c  lea     rax, [rbp+430h+arg_28]
0x180025073  mov     [rsp+530h+var_508], rax
0x180025078  mov     edx, r13d
0x18002507b  lea     rax, [rsp+530h+var_4E8]
0x180025080  mov     [rsp+530h+var_510], rax
0x180025085  call    ?WriteSqlString@StructuredQuery1@@YAJPEB_WW4SQL_STRING_LEVEL@1@PEA_W_KPEAPEA_WPEA_K@Z; StructuredQuery1::WriteSqlString(wchar_t const *,StructuredQuery1::SQL_STRING_LEVEL,wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *)
0x18002508a  mov     rdi, [rbp+430h+arg_28]
0x180025091  mov     ebx, eax
0x180025093  mov     rsi, [rsp+530h+var_4E8]
0x180025098  test    ebx, ebx
0x18002509a  js      short loc_1800250DE
0x18002509c  test    r12b, r12b
0x18002509f  jz      loc_1800252F2
0x1800250a5  xor     r12d, r12d
0x1800250a8  jmp     loc_180025166
0x1800250ad  test    r8, r8
0x1800250b0  lea     rdx, [rax-1]
0x1800250b4  lea     rcx, [r9-2]
0x1800250b8  cmovnz  rdx, rax
0x1800250bc  mov     rax, r8
0x1800250bf  neg     rax
0x1800250c2  sbb     ebx, ebx
0x1800250c4  not     ebx
0x1800250c6  lea     rsi, [rsi+rdx*2]
0x1800250ca  and     ebx, 8007007Ah
0x1800250d0  test    r8, r8
0x1800250d3  cmovnz  rcx, r9
0x1800250d7  sub     rdi, rdx
0x1800250da  mov     [rcx], r12w
0x1800250de  mov     r11, [rsp+530h+var_4D0]
0x1800250e3  mov     rax, [rbp+430h+var_4A8]
0x1800250e7  test    rax, rax
0x1800250ea  jz      short loc_1800250EF
0x1800250ec  mov     [rax], rsi
0x1800250ef  test    r11, r11
0x1800250f2  jz      short loc_1800250F7
0x1800250f4  mov     [r11], rdi
0x1800250f7  mov     eax, ebx
0x1800250f9  mov     rcx, [rbp+430h+var_50]
0x180025100  xor     rcx, rsp; StackCookie
0x180025103  call    __security_check_cookie
0x180025108  add     rsp, 4F8h
0x18002510f  pop     r15
0x180025111  pop     r14
0x180025113  pop     r13
0x180025115  pop     r12
0x180025117  pop     rdi
0x180025118  pop     rsi
0x180025119  pop     rbx
0x18002511a  pop     rbp
0x18002511b  retn
0x18002511c  mov     rcx, [rsp+530h+pv]
0x180025121  lea     rax, [rbp+430h+arg_28]
0x180025128  mov     [rsp+530h+var_508], rax
0x18002512d  mov     r9, rdi
0x180025130  lea     rax, [rsp+530h+var_4E8]
0x180025135  mov     r8, rsi
0x180025138  mov     edx, r13d
0x18002513b  mov     [rsp+530h+var_510], rax
0x180025140  call    ?WriteSqlString@StructuredQuery1@@YAJPEB_WW4SQL_STRING_LEVEL@1@PEA_W_KPEAPEA_WPEA_K@Z; StructuredQuery1::WriteSqlString(wchar_t const *,StructuredQuery1::SQL_STRING_LEVEL,wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *)
0x180025145  mov     rcx, [rsp+530h+pv]; pv
0x18002514a  mov     ebx, eax
0x18002514c  call    cs:__imp_CoTaskMemFree
0x180025152  mov     rdi, [rbp+430h+arg_28]
0x180025159  mov     rsi, [rsp+530h+var_4E8]
0x18002515e  test    ebx, ebx
0x180025160  js      loc_1800250DE
0x180025166  test    rdi, rdi
0x180025169  jz      loc_1800253F1
0x18002516f  cmp     rdi, 7FFFFFFFh
0x180025176  ja      loc_1800253E7
0x18002517c  mov     rdx, [rsp+530h+var_4B8]
0x180025181  mov     r8, rdi
0x180025184  mov     r9, rsi
0x180025187  mov     rax, r12
0x18002518a  mov     r10d, 7FFFFFFEh
0x180025190  test    r10, r10
0x180025193  jz      loc_1800250AD
0x180025199  movzx   ecx, word ptr [rdx]
0x18002519c  test    cx, cx
0x18002519f  jz      loc_1800250AD
0x1800251a5  mov     [r9], cx
0x1800251a9  add     rdx, 2
0x1800251ad  add     r9, 2
0x1800251b1  dec     r10
0x1800251b4  inc     rax
0x1800251b7  sub     r8, 1
0x1800251bb  jnz     short loc_180025190
0x1800251bd  jmp     loc_1800250AD
0x1800251c2  cmp     ecx, 40h ; '@'
0x1800251c5  jnz     loc_180089078
0x1800251cb  xorps   xmm0, xmm0
0x1800251ce  lea     rcx, [r14+8]; lpFileTime
0x1800251d2  xor     eax, eax
0x1800251d4  lea     rdx, [rbp+430h+SystemTime]; lpSystemTime
0x1800251d8  movups  xmmword ptr [rbp+430h+SystemTime.wYear], xmm0
0x1800251dc  mov     word ptr [rbp+430h+var_478], ax
0x1800251e0  call    cs:__imp_FileTimeToSystemTime
0x1800251e6  test    eax, eax
0x1800251e8  jz      loc_1800252ED
0x1800251ee  xorps   xmm0, xmm0
0x1800251f1  lea     r8, [rsp+530h+pdateOut]; pdateOut
0x1800251f6  xor     edx, edx; dwFlags
0x1800251f8  movsd   [rsp+530h+pdateOut], xmm0
0x1800251fe  lea     rcx, [rbp+430h+SystemTime]; pudateIn
0x180025202  call    cs:__imp_VarDateFromUdate
0x180025208  mov     ebx, eax
0x18002520a  test    eax, eax
0x18002520c  js      loc_1800250DE
0x180025212  mov     r8d, [rsp+530h+var_4D8]
0x180025217  movsd   xmm0, [rsp+530h+pdateOut]
0x18002521d  lea     rax, [rbp+430h+arg_28]
0x180025224  mov     r9, rsi
0x180025227  mov     [rsp+530h+var_500], rax
0x18002522c  mov     edx, r13d
0x18002522f  lea     rax, [rsp+530h+var_4E8]
0x180025234  mov     [rsp+530h+var_508], rax
0x180025239  mov     [rsp+530h+var_510], rdi
0x18002523e  call    StructuredQuery1__WriteDateTime
0x180025243  mov     ebx, eax
0x180025245  mov     rsi, [rsp+530h+var_4E8]
0x18002524a  mov     rdi, [rbp+430h+arg_28]
0x180025251  mov     r13d, [rsp+530h+var_4F0]
0x180025256  jmp     loc_180025098
0x18002525b  cmp     ecx, 0Bh
0x18002525e  ja      loc_180025398
0x180025264  jz      loc_180025378
0x18002526a  test    ecx, ecx
0x18002526c  jz      loc_18002536C
0x180025272  sub     ecx, 1
0x180025275  jz      loc_180025360
0x18002527b  sub     ecx, 1
0x18002527e  jz      short loc_18002528E
0x180025280  sub     ecx, 1
0x180025283  jz      short loc_18002528E
0x180025285  sub     ecx, 2
0x180025288  jnz     loc_18002534C
0x18002528e  xor     r13d, r13d
0x180025291  lea     rdx, [rsp+530h+pv]; ppszOut
0x180025296  mov     rcx, r14; propvar
0x180025299  mov     [rsp+530h+pv], r13
0x18002529e  call    cs:__imp_PropVariantToStringAlloc
0x1800252a4  mov     ebx, eax
0x1800252a6  test    eax, eax
0x1800252a8  js      loc_1800250DE
0x1800252ae  mov     r8, [rsp+530h+pv]; wchar_t *
0x1800252b3  lea     rax, [rbp+430h+arg_28]
0x1800252ba  lea     r9, [rsp+530h+var_4E8]; wchar_t **
0x1800252bf  mov     [rsp+530h+var_510], rax; unsigned __int64 *
0x1800252c4  mov     rdx, rdi; unsigned __int64
0x1800252c7  mov     rcx, rsi; wchar_t *
0x1800252ca  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x1800252cf  mov     rcx, [rsp+530h+pv]; pv
0x1800252d4  mov     ebx, eax
0x1800252d6  call    cs:__imp_CoTaskMemFree
0x1800252dc  jmp     loc_180025245
0x1800252e1  lea     rcx, cchOriginalDestLength
0x1800252e8  jmp     loc_180024F9A
0x1800252ed  mov     r13d, [rsp+530h+var_4F0]
0x1800252f2  xor     r12d, r12d
0x1800252f5  lea     rdx, [rsp+530h+pv]; ppszOut
0x1800252fa  mov     rcx, r14; propvar
0x1800252fd  mov     [rsp+530h+pv], r12
0x180025302  call    cs:__imp_PropVariantToStringAlloc
0x180025308  mov     ebx, eax
0x18002530a  test    eax, eax
0x18002530c  js      loc_1800250DE
0x180025312  test    r15b, r15b
0x180025315  jnz     loc_18002511C
0x18002531b  mov     rcx, [rsp+530h+pv]
0x180025320  call    ?DoesBlurbNeedQuotes@StructuredQuery1@@YA?AW4VALUE_NORMALIZATION_RESULT@1@PEB_W@Z; StructuredQuery1::DoesBlurbNeedQuotes(wchar_t const *)
0x180025325  mov     rcx, [rbp+430h+var_4B0]
0x180025329  mov     [rcx], eax
0x18002532b  jmp     loc_18002511C
0x180025330  mov     r15b, r12b
0x180025333  jmp     loc_180024F9A
0x180025338  mov     [rsi], r12w
0x18002533c  mov     ebx, r9d
0x18002533f  jmp     loc_1800250E3
0x180025344  mov     ebx, r9d
0x180025347  jmp     loc_180025036
0x18002534c  cmp     ecx, 2
0x18002534f  jnz     short loc_1800252ED
0x180025351  movsd   xmm0, qword ptr [r14+8]
0x180025357  or      r8d, 40h
0x18002535b  jmp     loc_18002521D
0x180025360  lea     r8, cchOriginalDestLength
0x180025367  jmp     loc_180088EE5
0x18002536c  lea     r8, asc_1800A0348; "[]"
  ... truncated ...
```
