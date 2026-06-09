# GetBundleApplicablePackages

- ea: `0x18008e850`
- end: `0x18008f32e`
- name: `GetBundleApplicablePackages`
- size: `2782`
- prototype: `__int64 __fastcall(_WORD *, _WORD *, _WORD *, _WORD *, __int64, _WORD *)`
- caller_count: `0`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callees

- `0x180008a1c`
- `0x18000b644`
- `0x1800174d0`
- `0x180039990`
- `0x18003f888`
- `0x180050bac`
- `0x180051870`
- `0x18006c574`
- `0x180078070`
- `0x18008666c`
- `0x1800867ac`
- `0x1800868ec`
- `0x180086bbc`
- `0x180086c04`
- `0x180086c48`
- `0x180089374`
- `0x18008e850`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008ee96`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008eea1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008f1a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008f1d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008f222`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008f22d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008f28a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008f295`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008ee96`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008eea1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008f1a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008f1d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008f222`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008f22d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008f28a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008f295`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18008e9c2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18008ea7b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18008e9c2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18008ea7b`
- `AppxApplicabilityEngine!CreateApplicabilityContext` at `0x18008f037`
- `AppxApplicabilityEngine!CreateApplicabilityContext` at `0x18008f037`
- `AppxApplicabilityEngine!GetApplicablePackages` at `0x18008f0e3`
- `AppxApplicabilityEngine!GetApplicablePackages` at `0x18008f0e3`

## pseudocode

```c
__int64 __fastcall GetBundleApplicablePackages(_WORD *a1, _WORD *a2, _WORD *a3, _WORD *a4, __int64 a5, _WORD *a6)
{
  char v6; // r12
  __int64 v8; // rdx
  __int64 v9; // rax
  __int64 v10; // r10
  unsigned int v11; // ebx
  int v12; // eax
  HRESULT v13; // eax
  LPVOID v14; // rdi
  __int64 (__fastcall *v15)(LPVOID, _WORD *, __int64, _QWORD, int, __int64 *); // rbx
  int v16; // eax
  HRESULT v17; // eax
  LPVOID v18; // rdi
  __int64 (__fastcall *v19)(LPVOID, __int64, __int64 *); // rbx
  int v20; // eax
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, __int64 *); // rbx
  int v23; // eax
  char v24; // r13
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, __int64 (__fastcall ****)(_QWORD, __int64 *, __int64 *)); // rbx
  int v27; // eax
  __int64 (__fastcall ***v28)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v29)(_QWORD, __int64 *, __int64 *); // rbx
  int v30; // eax
  __int64 (__fastcall ***v31)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v32)(_QWORD, __int64 *, __int64 *); // rdi
  int v33; // eax
  __int64 (__fastcall ***v34)(_QWORD, _QWORD, _QWORD); // rbx
  int v35; // esi
  __int64 (__fastcall *v36)(_QWORD, __int64 *, __int64 *); // rdi
  int v37; // eax
  unsigned int v38; // ecx
  unsigned int j; // ebx
  int v40; // edi
  unsigned int v41; // eax
  unsigned int i; // ebx
  __int64 v43; // rdx
  __int64 v44; // r9
  __int64 v45; // rdx
  __int64 v46; // rdx
  __int64 v47; // rdx
  __int64 v48; // rdx
  int v49; // eax
  int v50; // eax
  int v51; // eax
  int v52; // eax
  int v53; // eax
  __int64 v54; // rax
  __int64 v55; // rax
  int ApplicablePackages; // eax
  __int64 v57; // rdx
  __int64 v58; // rax
  __int64 v59; // rax
  unsigned int k; // esi
  __int64 v61; // rdi
  __int64 (__fastcall *v62)(__int64, __int64 *); // rbx
  int v63; // eax
  int v64; // eax
  __int64 v65; // rdx
  LPVOID ppv; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v68; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v69; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v70; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID v71; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-98h] BYREF
  LPVOID v73; // [rsp+70h] [rbp-90h] BYREF
  __int64 (__fastcall ***v74)(_QWORD, __int64 *, __int64 *); // [rsp+78h] [rbp-88h] BYREF
  __int64 (__fastcall ***v75)(_QWORD, __int64 *, __int64 *); // [rsp+80h] [rbp-80h] BYREF
  __int64 v76; // [rsp+88h] [rbp-78h] BYREF
  __int64 v77; // [rsp+90h] [rbp-70h] BYREF
  __int64 v78; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v79; // [rsp+A0h] [rbp-60h] BYREF
  LPVOID v80; // [rsp+A8h] [rbp-58h] BYREF
  int v81; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v82; // [rsp+B4h] [rbp-4Ch] BYREF
  int v83; // [rsp+B8h] [rbp-48h] BYREF
  int v84; // [rsp+BCh] [rbp-44h] BYREF
  int v85; // [rsp+C0h] [rbp-40h] BYREF
  int v86; // [rsp+C4h] [rbp-3Ch] BYREF
  __int64 v87; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v88[16]; // [rsp+D0h] [rbp-30h] BYREF
  int v89; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v90; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v91[24]; // [rsp+F0h] [rbp-10h] BYREF
  _WORD *v92; // [rsp+108h] [rbp+8h] BYREF
  __int128 v93; // [rsp+118h] [rbp+18h] BYREF
  void *retaddr; // [rsp+178h] [rbp+78h]

  v6 = 0;
  v80 = a3;
  v92 = a4;
  if ( !a1 || !*a1 )
  {
    v8 = 2253;
    goto LABEL_133;
  }
  if ( !a2 || !*a2 )
  {
    v8 = 2254;
    goto LABEL_133;
  }
  if ( !a3 || !*a3 )
  {
    v8 = 2255;
    goto LABEL_133;
  }
  if ( !a4 || !*a4 )
  {
    v8 = 2256;
    goto LABEL_133;
  }
  if ( !a5 )
  {
    v8 = 2257;
LABEL_133:
    v11 = -2147024809;
    goto LABEL_134;
  }
  if ( !a6 )
  {
    v8 = 2258;
    goto LABEL_133;
  }
  *a6 = 0;
  v89 = 4;
  v79 = 0;
  v93 = 0;
  v9 = sub_18003F888(v91, &v93, &v79, &v89);
  v11 = sub_1800867AC(v10, v9);
  if ( (v11 & 0x80000000) != 0 )
  {
    v8 = 2273;
LABEL_134:
    sub_180008A1C(retaddr, v8, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", v11);
    return v11;
  }
  LODWORD(v76) = v79;
  if ( !v79 )
  {
    v8 = 2275;
    goto LABEL_133;
  }
  v83 = -2147221008;
  v12 = sub_180089374(&v83);
  v11 = v12;
  if ( v12 < 0 )
  {
    sub_180008A1C(retaddr, 2283, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v12);
LABEL_127:
    sub_180086C48(&v83);
    return v11;
  }
  ppv = 0;
  sub_18000B644(&ppv);
  v13 = CoCreateInstance(&stru_18011FAF0, 0, 1u, &stru_18011FB10, &ppv);
  v11 = v13;
  if ( v13 < 0 )
  {
    sub_180008A1C(retaddr, 2286, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v13);
LABEL_126:
    sub_18000B644(&ppv);
    goto LABEL_127;
  }
  v14 = ppv;
  v68 = 0;
  v15 = *(__int64 (__fastcall **)(LPVOID, _WORD *, __int64, _QWORD, int, __int64 *))(*(_QWORD *)ppv + 40LL);
  sub_18000B644(&v68);
  v16 = v15(v14, a1, 1, 0, 128, &v68);
  v11 = v16;
  if ( v16 < 0 )
  {
    sub_180008A1C(retaddr, 2289, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v16);
LABEL_125:
    sub_18000B644(&v68);
    goto LABEL_126;
  }
  v71 = 0;
  sub_18000B644(&v71);
  v17 = CoCreateInstance(&stru_18011FAE0, 0, 1u, &stru_18011FB00, &v71);
  v11 = v17;
  if ( v17 < 0 )
  {
    sub_180008A1C(retaddr, 2292, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v17);
LABEL_124:
    sub_18000B644(&v71);
    goto LABEL_125;
  }
  v18 = v71;
  v70 = 0;
  v19 = *(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)v71 + 40LL);
  sub_18000B644(&v70);
  v20 = v19(v18, v68, &v70);
  v11 = v20;
  if ( v20 < 0 )
  {
    sub_180008A1C(retaddr, 2295, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v20);
LABEL_123:
    sub_18000B644(&v70);
    goto LABEL_124;
  }
  v21 = v70;
  v69 = 0;
  v22 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v70 + 32LL);
  sub_18000B644(&v69);
  v23 = v22(v21, &v69);
  v11 = v23;
  if ( v23 < 0 )
  {
    sub_180008A1C(retaddr, 2299, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v23);
LABEL_122:
    sub_18000B644(&v69);
    goto LABEL_123;
  }
  v24 = 0;
  v81 = 0;
  v73 = 0;
  pv = 0;
  (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v69 + 32LL))(v69, &v81);
  while ( 1 )
  {
    if ( !v81 )
      goto LABEL_66;
    v75 = 0;
    v25 = v69;
    v26 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, __int64 *, __int64 *)))(*(_QWORD *)v69 + 24LL);
    sub_18000B644(&v75);
    v27 = v26(v25, &v75);
    v11 = v27;
    if ( v27 < 0 )
    {
      v48 = 2307;
      goto LABEL_87;
    }
    v84 = 0;
    v27 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64 *, __int64 *), int *))(*v75)[3])(v75, &v84);
    v11 = v27;
    if ( v27 < 0 )
    {
      v48 = 2310;
LABEL_87:
      sub_180008A1C(retaddr, v48, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v27);
      goto LABEL_77;
    }
    if ( v84 )
      goto LABEL_70;
    v74 = 0;
    v28 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v75;
    v29 = (*v75)[4];
    sub_18000B644(&v74);
    v30 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD), __int64 (__fastcall ****)(_QWORD, __int64 *, __int64 *)))v29)(
            v28,
            &v74);
    v11 = v30;
    if ( v30 < 0 )
    {
      sub_180008A1C(retaddr, 2314, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v30);
LABEL_76:
      sub_18000B644(&v74);
LABEL_77:
      sub_18000B644(&v75);
      goto LABEL_121;
    }
    v31 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v74;
    v77 = 0;
    v32 = **v74;
    sub_18000B644(&v77);
    v33 = v32(v31, qword_18011FA78, &v77);
    v11 = v33;
    if ( v33 < 0 )
    {
      v47 = 2317;
LABEL_83:
      sub_180008A1C(retaddr, v47, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v33);
      goto LABEL_75;
    }
    v85 = 0;
    v33 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v77 + 88LL))(v77, &v85);
    v11 = v33;
    if ( v33 < 0 )
    {
      v47 = 2320;
      goto LABEL_83;
    }
    v34 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v75;
    v35 = v85;
    v78 = 0;
    v36 = **v75;
    sub_18000B644(&v78);
    v37 = v36(v34, qword_18011FA88, &v78);
    v11 = v37;
    if ( v37 < 0 )
    {
      v46 = 2324;
LABEL_74:
      sub_180008A1C(retaddr, v46, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v37);
      sub_18000B644(&v78);
LABEL_75:
      sub_18000B644(&v77);
      goto LABEL_76;
    }
    v86 = 0;
    v37 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v78 + 24LL))(v78, &v86);
    v11 = v37;
    if ( v37 < 0 )
    {
      v46 = 2327;
      goto LABEL_74;
    }
    if ( !v86 )
      break;
    if ( !v24 )
    {
      if ( v35 == (_DWORD)v93 || v35 == 11 )
      {
        v37 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64 *, __int64 *), LPVOID *))(*v74)[9])(
                v74,
                &pv);
        v11 = v37;
        if ( v37 < 0 )
        {
          v46 = 2356;
          goto LABEL_74;
        }
        v24 = 1;
      }
      else
      {
        v41 = v76;
        for ( i = 1; i < v41; ++i )
        {
          if ( *((_DWORD *)&v93 + i) == v35 )
          {
            v40 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64 *, __int64 *), LPVOID *))(*v74)[9])(
                    v74,
                    &pv);
            if ( v40 < 0 )
            {
              v45 = 2366;
LABEL_72:
              sub_180008A1C(
                retaddr,
                v45,
                "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp",
                (unsigned int)v40);
              sub_18000B644(&v78);
              sub_18000B644(&v77);
              sub_18000B644(&v74);
              sub_18000B644(&v75);
              CoTaskMemFree(pv);
              CoTaskMemFree(v73);
              sub_18000B644(&v69);
              sub_18000B644(&v70);
              sub_18000B644(&v71);
              sub_18000B644(&v68);
              sub_18000B644(&ppv);
              v11 = v40;
              goto LABEL_127;
            }
            v41 = i;
            LODWORD(v76) = i;
          }
          else
          {
            v41 = v76;
          }
        }
      }
    }
    if ( v6 )
      goto LABEL_64;
LABEL_69:
    sub_18000B644(&v78);
    sub_18000B644(&v77);
    sub_18000B644(&v74);
LABEL_70:
    sub_18000B644(&v75);
    (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v69 + 40LL))(v69, &v81);
  }
  if ( !v6 )
  {
    if ( v35 != (_DWORD)v93 && v35 != 11 )
    {
      v38 = v79;
      for ( j = 1; j < v38; ++j )
      {
        if ( *((_DWORD *)&v93 + j) == v35 )
        {
          v40 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64 *, __int64 *), LPVOID *))(*v74)[9])(
                  v74,
                  &v73);
          if ( v40 < 0 )
          {
            v45 = 2344;
            goto LABEL_72;
          }
          v38 = j;
          v79 = j;
        }
      }
      goto LABEL_69;
    }
    v37 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64 *, __int64 *), LPVOID *))(*v74)[9])(
            v74,
            &v73);
    v11 = v37;
    if ( v37 < 0 )
    {
      v46 = 2334;
      goto LABEL_74;
    }
    v6 = 1;
  }
LABEL_64:
  if ( !v24 )
    goto LABEL_69;
  sub_18000B644(&v78);
  sub_18000B644(&v77);
  sub_18000B644(&v74);
  sub_18000B644(&v75);
LABEL_66:
  if ( !v73 )
  {
    v11 = -2147024894;
    v43 = 2382;
    v44 = 2147942402LL;
    goto LABEL_68;
  }
  v49 = sub_1800174D0(a6, a5);
  v11 = v49;
  if ( v49 < 0 )
  {
    v44 = (unsigned int)v49;
    v43 = 2383;
    goto LABEL_68;
  }
  v50 = sub_1800174D0(a6, a5);
  v11 = v50;
  if ( v50 < 0 )
  {
    v44 = (unsigned int)v50;
    v43 = 2384;
    goto LABEL_68;
  }
  if ( pv )
  {
    v51 = sub_1800174D0(a6, a5);
    v11 = v51;
    if ( v51 < 0 )
    {
      v44 = (unsigned int)v51;
      v43 = 2389;
      goto LABEL_68;
    }
    v52 = sub_1800174D0(a6, a5);
    v11 = v52;
    if ( v52 < 0 )
    {
      v44 = (unsigned int)v52;
      v43 = 2390;
      goto LABEL_68;
    }
  }
  v87 = 0;
  v53 = CreateApplicabilityContext(&v87);
  v11 = v53;
  if ( v53 < 0 )
  {
    v44 = (unsigned int)v53;
    v43 = 2395;
LABEL_68:
    sub_180008A1C(retaddr, v43, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", v44);
LABEL_121:
    CoTaskMemFree(pv);
    CoTaskMemFree(v73);
    goto LABEL_122;
  }
  v54 = sub_180050BAC(&v76, &v87);
  sub_180039990(v88, v54);
  v55 = sub_180050BAC(&v76, &v87);
  ApplicablePackages = sub_18008666C(v80, v55);
  v11 = ApplicablePackages;
  if ( ApplicablePackages < 0 )
  {
    v57 = 2406;
    goto LABEL_102;
  }
  v58 = sub_180050BAC(&v80, &v87);
  ApplicablePackages = sub_1800868EC(v92, v58);
  v11 = ApplicablePackages;
  if ( ApplicablePackages < 0 )
  {
    v57 = 2415;
    goto LABEL_102;
  }
  v82 = 0;
  v90 = 0;
  ApplicablePackages = GetApplicablePackages(v70, v87, &v82, &v90);
  v11 = ApplicablePackages;
  if ( ApplicablePackages < 0 )
  {
    v57 = 2419;
LABEL_102:
    sub_180008A1C(
      retaddr,
      v57,
      "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp",
      (unsigned int)ApplicablePackages);
LABEL_120:
    sub_180086C04(v88);
    goto LABEL_121;
  }
  v59 = sub_18006C574(&v92, &v82, &v90);
  sub_180078070(v91, v59);
  for ( k = 0; k < v82; ++k )
  {
    v76 = 0;
    v61 = *(_QWORD *)(v90 + 8LL * k);
    v62 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v61 + 32LL);
    sub_18000B644(&v76);
    v63 = v62(v61, &v76);
    v11 = v63;
    if ( v63 < 0 )
    {
      sub_180008A1C(retaddr, 2428, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v63);
      goto LABEL_119;
    }
    v80 = 0;
    v64 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v76 + 72LL))(v76, &v80);
    v11 = v64;
    if ( v64 < 0 )
    {
      v65 = 2431;
LABEL_115:
      sub_180008A1C(retaddr, v65, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v64);
      CoTaskMemFree(v80);
LABEL_119:
      sub_18000B644(&v76);
      sub_180086BBC(v91);
      goto LABEL_120;
    }
    v64 = sub_1800174D0(a6, a5);
    v11 = v64;
    if ( v64 < 0 )
    {
      v65 = 2432;
      goto LABEL_115;
    }
    v64 = sub_1800174D0(a6, a5);
    v11 = v64;
    if ( v64 < 0 )
    {
      v65 = 2433;
      goto LABEL_115;
    }
    CoTaskMemFree(v80);
    sub_18000B644(&v76);
  }
  sub_180086BBC(v91);
  sub_180086C04(v88);
  CoTaskMemFree(pv);
  CoTaskMemFree(v73);
  sub_18000B644(&v69);
  sub_18000B644(&v70);
  sub_18000B644(&v71);
  sub_18000B644(&v68);
  sub_18000B644(&ppv);
  sub_180086C48(&v83);
  return 0;
}

```

## disassembly

```asm
0x18008e850  push    rbp
0x18008e852  push    rbx
0x18008e853  push    rsi
0x18008e854  push    rdi
0x18008e855  push    r12
0x18008e857  push    r13
0x18008e859  push    r14
0x18008e85b  push    r15
0x18008e85d  lea     rbp, [rsp-38h]
0x18008e862  sub     rsp, 138h
0x18008e869  mov     rax, cs:__security_cookie
0x18008e870  xor     rax, rsp
0x18008e873  mov     [rbp+70h+var_48], rax
0x18008e877  mov     r14, [rbp+70h+arg_28]
0x18008e87e  xor     r12d, r12d
0x18008e881  mov     [rbp+70h+var_C8], r8
0x18008e885  mov     rax, r9
0x18008e888  mov     [rbp+70h+var_68], rax
0x18008e88c  mov     r10, rdx
0x18008e88f  mov     rsi, rcx
0x18008e892  test    rcx, rcx
0x18008e895  jz      loc_18008F2EF
0x18008e89b  cmp     [rcx], r12w
0x18008e89f  jz      loc_18008F2EF
0x18008e8a5  test    rdx, rdx
0x18008e8a8  jz      loc_18008F2E8
0x18008e8ae  cmp     [rdx], r12w
0x18008e8b2  jz      loc_18008F2E8
0x18008e8b8  test    r8, r8
0x18008e8bb  jz      loc_18008F2E1
0x18008e8c1  cmp     [r8], r12w
0x18008e8c5  jz      loc_18008F2E1
0x18008e8cb  test    rax, rax
0x18008e8ce  jz      loc_18008F2DA
0x18008e8d4  cmp     [r9], r12w
0x18008e8d8  jz      loc_18008F2DA
0x18008e8de  mov     r15, [rbp+70h+arg_20]
0x18008e8e5  test    r15, r15
0x18008e8e8  jnz     short loc_18008E8F4
0x18008e8ea  mov     edx, 8D1h
0x18008e8ef  jmp     loc_18008F2F4
0x18008e8f4  test    r14, r14
0x18008e8f7  jnz     short loc_18008E903
0x18008e8f9  mov     edx, 8D2h
0x18008e8fe  jmp     loc_18008F2F4
0x18008e903  xorps   xmm0, xmm0
0x18008e906  mov     [r14], r12w
0x18008e90a  lea     r9, [rbp+70h+var_90]
0x18008e90e  mov     [rbp+70h+var_90], 4
0x18008e915  lea     r8, [rbp+70h+var_D0]
0x18008e919  mov     [rbp+70h+var_D0], r12d
0x18008e91d  lea     rdx, [rbp+70h+var_58]
0x18008e921  lea     rcx, [rbp+70h+var_80]
0x18008e925  movups  [rbp+70h+var_58], xmm0
0x18008e929  call    sub_18003F888
0x18008e92e  mov     rdx, rax
0x18008e931  mov     rcx, r10
0x18008e934  call    sub_1800867AC
0x18008e939  mov     ebx, eax
0x18008e93b  test    eax, eax
0x18008e93d  jns     short loc_18008E949
0x18008e93f  mov     edx, 8E1h
0x18008e944  jmp     loc_18008F2F9
0x18008e949  mov     eax, [rbp+70h+var_D0]
0x18008e94c  mov     dword ptr [rbp+70h+var_E8], eax
0x18008e94f  test    eax, eax
0x18008e951  jnz     short loc_18008E95D
0x18008e953  mov     edx, 8E3h
0x18008e958  jmp     loc_18008F2F4
0x18008e95d  lea     rcx, [rbp+70h+var_B8]
0x18008e961  mov     [rbp+70h+var_B8], 800401F0h
0x18008e968  call    sub_180089374
0x18008e96d  mov     ebx, eax
0x18008e96f  test    eax, eax
0x18008e971  jns     short loc_18008E990
0x18008e973  mov     rcx, [rbp+78h]
0x18008e977  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x18008e97e  mov     r9d, eax
0x18008e981  mov     edx, 8EBh
0x18008e986  call    sub_180008A1C
0x18008e98b  jmp     loc_18008F265
0x18008e990  lea     rcx, [rsp+170h+var_130]
0x18008e995  mov     [rsp+170h+var_130], r12
0x18008e99a  call    sub_18000B644
0x18008e99f  lea     rax, [rsp+170h+var_130]
0x18008e9a4  mov     r13d, 1
0x18008e9aa  mov     r8d, r13d; dwClsContext
0x18008e9ad  mov     [rsp+170h+ppv], rax; ppv
0x18008e9b2  lea     r9, stru_18011FB10; riid
0x18008e9b9  xor     edx, edx; pUnkOuter
0x18008e9bb  lea     rcx, stru_18011FAF0; rclsid
0x18008e9c2  call    cs:CoCreateInstance
0x18008e9c8  mov     ebx, eax
0x18008e9ca  test    eax, eax
0x18008e9cc  jns     short loc_18008E9EB
0x18008e9ce  mov     rcx, [rbp+78h]
0x18008e9d2  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x18008e9d9  mov     r9d, eax
0x18008e9dc  mov     edx, 8EEh
0x18008e9e1  call    sub_180008A1C
0x18008e9e6  jmp     loc_18008F25B
0x18008e9eb  mov     rdi, [rsp+170h+var_130]
0x18008e9f0  lea     rcx, [rsp+170h+var_128]
0x18008e9f5  mov     [rsp+170h+var_128], r12
0x18008e9fa  mov     rax, [rdi]
0x18008e9fd  mov     rbx, [rax+28h]
0x18008ea01  call    sub_18000B644
0x18008ea06  lea     rax, [rsp+170h+var_128]
0x18008ea0b  xor     r9d, r9d
0x18008ea0e  mov     [rsp+170h+var_148], rax
0x18008ea13  mov     r8d, r13d
0x18008ea16  mov     rax, rbx
0x18008ea19  mov     dword ptr [rsp+170h+ppv], 80h
0x18008ea21  mov     rdx, rsi
0x18008ea24  mov     rcx, rdi
0x18008ea27  call    j__guard_dispatch_icall
0x18008ea2c  mov     ebx, eax
0x18008ea2e  test    eax, eax
0x18008ea30  jns     short loc_18008EA4F
0x18008ea32  mov     rcx, [rbp+78h]
0x18008ea36  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x18008ea3d  mov     r9d, eax
0x18008ea40  mov     edx, 8F1h
0x18008ea45  call    sub_180008A1C
0x18008ea4a  jmp     loc_18008F251
0x18008ea4f  lea     rcx, [rsp+170h+var_110]
0x18008ea54  mov     [rsp+170h+var_110], r12
0x18008ea59  call    sub_18000B644
0x18008ea5e  lea     rax, [rsp+170h+var_110]
0x18008ea63  mov     r8d, r13d; dwClsContext
0x18008ea66  lea     r9, stru_18011FB00; riid
0x18008ea6d  mov     [rsp+170h+ppv], rax; ppv
0x18008ea72  xor     edx, edx; pUnkOuter
0x18008ea74  lea     rcx, stru_18011FAE0; rclsid
0x18008ea7b  call    cs:CoCreateInstance
0x18008ea81  mov     ebx, eax
0x18008ea83  test    eax, eax
0x18008ea85  jns     short loc_18008EAA4
0x18008ea87  mov     rcx, [rbp+78h]
0x18008ea8b  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x18008ea92  mov     r9d, eax
0x18008ea95  mov     edx, 8F4h
0x18008ea9a  call    sub_180008A1C
0x18008ea9f  jmp     loc_18008F247
0x18008eaa4  mov     rdi, [rsp+170h+var_110]
0x18008eaa9  lea     rcx, [rsp+170h+var_118]
0x18008eaae  mov     [rsp+170h+var_118], r12
0x18008eab3  mov     rax, [rdi]
0x18008eab6  mov     rbx, [rax+28h]
0x18008eaba  call    sub_18000B644
0x18008eabf  mov     rdx, [rsp+170h+var_128]
0x18008eac4  lea     r8, [rsp+170h+var_118]
0x18008eac9  mov     rcx, rdi
0x18008eacc  mov     rax, rbx
0x18008eacf  call    j__guard_dispatch_icall
0x18008ead4  mov     ebx, eax
0x18008ead6  test    eax, eax
0x18008ead8  jns     short loc_18008EAF7
0x18008eada  mov     rcx, [rbp+78h]
0x18008eade  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x18008eae5  mov     r9d, eax
0x18008eae8  mov     edx, 8F7h
0x18008eaed  call    sub_180008A1C
0x18008eaf2  jmp     loc_18008F23D
0x18008eaf7  mov     rdi, [rsp+170h+var_118]
0x18008eafc  lea     rcx, [rsp+170h+var_120]
0x18008eb01  mov     [rsp+170h+var_120], r12
0x18008eb06  mov     rax, [rdi]
0x18008eb09  mov     rbx, [rax+20h]
0x18008eb0d  call    sub_18000B644
0x18008eb12  lea     rdx, [rsp+170h+var_120]
0x18008eb17  mov     rcx, rdi
0x18008eb1a  mov     rax, rbx
0x18008eb1d  call    j__guard_dispatch_icall
0x18008eb22  xor     edi, edi
0x18008eb24  mov     ebx, eax
0x18008eb26  test    eax, eax
0x18008eb28  jns     short loc_18008EB47
0x18008eb2a  mov     rcx, [rbp+78h]
0x18008eb2e  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x18008eb35  mov     r9d, eax
0x18008eb38  mov     edx, 8FBh
0x18008eb3d  call    sub_180008A1C
0x18008eb42  jmp     loc_18008F233
0x18008eb47  mov     rcx, [rsp+170h+var_120]
0x18008eb4c  mov     r13b, dil
0x18008eb4f  mov     [rbp+70h+var_C0], edi
0x18008eb52  mov     [rsp+170h+var_100], rdi
0x18008eb57  mov     [rsp+170h+pv], rdi
0x18008eb5c  mov     rax, [rcx]
0x18008eb5f  mov     rax, [rax+20h]
0x18008eb63  lea     rdx, [rbp+70h+var_C0]
0x18008eb67  call    j__guard_dispatch_icall
0x18008eb6c  cmp     [rbp+70h+var_C0], edi
0x18008eb6f  jz      loc_18008EDEC
0x18008eb75  mov     [rbp+70h+var_F0], rdi
0x18008eb79  lea     rcx, [rbp+70h+var_F0]
0x18008eb7d  mov     rdi, [rsp+170h+var_120]
0x18008eb82  mov     rax, [rdi]
0x18008eb85  mov     rbx, [rax+18h]
0x18008eb89  call    sub_18000B644
0x18008eb8e  lea     rdx, [rbp+70h+var_F0]
0x18008eb92  mov     rcx, rdi
0x18008eb95  mov     rax, rbx
0x18008eb98  call    j__guard_dispatch_icall
0x18008eb9d  xor     edi, edi
0x18008eb9f  mov     ebx, eax
0x18008eba1  test    eax, eax
0x18008eba3  js      loc_18008EF99
0x18008eba9  mov     rcx, [rbp+70h+var_F0]
0x18008ebad  lea     rdx, [rbp+70h+var_B4]
0x18008ebb1  mov     [rbp+70h+var_B4], edi
0x18008ebb4  mov     rax, [rcx]
0x18008ebb7  mov     rax, [rax+18h]
0x18008ebbb  call    j__guard_dispatch_icall
0x18008ebc0  mov     ebx, eax
0x18008ebc2  test    eax, eax
0x18008ebc4  js      loc_18008EF7C
0x18008ebca  cmp     [rbp+70h+var_B4], edi
0x18008ebcd  jnz     loc_18008EE3A
0x18008ebd3  mov     [rsp+170h+var_F8], rdi
0x18008ebd8  lea     rcx, [rsp+170h+var_F8]
0x18008ebdd  mov     rdi, [rbp+70h+var_F0]
0x18008ebe1  mov     rax, [rdi]
0x18008ebe4  mov     rbx, [rax+20h]
0x18008ebe8  call    sub_18000B644
0x18008ebed  lea     rdx, [rsp+170h+var_F8]
0x18008ebf2  mov     rcx, rdi
0x18008ebf5  mov     rax, rbx
0x18008ebf8  call    j__guard_dispatch_icall
0x18008ebfd  mov     ebx, eax
0x18008ebff  test    eax, eax
0x18008ec01  js      loc_18008EF62
0x18008ec07  mov     rbx, [rsp+170h+var_F8]
0x18008ec0c  lea     rcx, [rbp+70h+var_E0]
0x18008ec10  mov     [rbp+70h+var_E0], 0
0x18008ec18  mov     rax, [rbx]
0x18008ec1b  mov     rdi, [rax]
0x18008ec1e  call    sub_18000B644
0x18008ec23  lea     r8, [rbp+70h+var_E0]
0x18008ec27  mov     rcx, rbx
0x18008ec2a  lea     rdx, qword_18011FA78
0x18008ec31  mov     rax, rdi
0x18008ec34  call    j__guard_dispatch_icall
0x18008ec39  mov     ebx, eax
0x18008ec3b  test    eax, eax
0x18008ec3d  js      loc_18008EF5B
0x18008ec43  mov     rcx, [rbp+70h+var_E0]
0x18008ec47  lea     rdx, [rbp+70h+var_B0]
0x18008ec4b  mov     [rbp+70h+var_B0], 0
0x18008ec52  mov     rax, [rcx]
0x18008ec55  mov     rax, [rax+58h]
0x18008ec59  call    j__guard_dispatch_icall
0x18008ec5e  mov     ebx, eax
0x18008ec60  test    eax, eax
0x18008ec62  js      loc_18008EF41
0x18008ec68  mov     rbx, [rbp+70h+var_F0]
0x18008ec6c  lea     rcx, [rbp+70h+var_D8]
0x18008ec70  mov     esi, [rbp+70h+var_B0]
0x18008ec73  mov     [rbp+70h+var_D8], 0
0x18008ec7b  mov     rax, [rbx]
0x18008ec7e  mov     rdi, [rax]
0x18008ec81  call    sub_18000B644
0x18008ec86  lea     r8, [rbp+70h+var_D8]
0x18008ec8a  mov     rcx, rbx
0x18008ec8d  lea     rdx, qword_18011FA88
0x18008ec94  mov     rax, rdi
0x18008ec97  call    j__guard_dispatch_icall
0x18008ec9c  xor     edi, edi
0x18008ec9e  mov     ebx, eax
0x18008eca0  test    eax, eax
0x18008eca2  js      loc_18008EF3A
0x18008eca8  mov     rcx, [rbp+70h+var_D8]
0x18008ecac  lea     rdx, [rbp+70h+var_AC]
0x18008ecb0  mov     [rbp+70h+var_AC], edi
0x18008ecb3  mov     rax, [rcx]
0x18008ecb6  mov     rax, [rax+18h]
0x18008ecba  call    j__guard_dispatch_icall
0x18008ecbf  mov     ebx, eax
0x18008ecc1  test    eax, eax
0x18008ecc3  js      loc_18008EF33
0x18008ecc9  cmp     [rbp+70h+var_AC], edi
0x18008eccc  jnz     short loc_18008ED45
0x18008ecce  test    r12b, r12b
0x18008ecd1  jnz     loc_18008EDC2
0x18008ecd7  cmp     esi, dword ptr [rbp+70h+var_58]
0x18008ecda  jz      short loc_18008ED20
0x18008ecdc  cmp     esi, 0Bh
0x18008ecdf  jz      short loc_18008ED20
0x18008ece1  mov     ecx, [rbp+70h+var_D0]
0x18008ece4  lea     ebx, [rdi+1]
0x18008ece7  cmp     ebx, ecx
0x18008ece9  jnb     loc_18008EE1C
0x18008ecef  mov     eax, ebx
0x18008ecf1  cmp     dword ptr [rbp+rax*4+70h+var_58], esi
0x18008ecf5  jnz     short loc_18008ED1C
0x18008ecf7  mov     rcx, [rsp+170h+var_F8]
0x18008ecfc  lea     rdx, [rsp+170h+var_100]
0x18008ed01  mov     rax, [rcx]
0x18008ed04  mov     rax, [rax+48h]
  ... truncated ...
```
