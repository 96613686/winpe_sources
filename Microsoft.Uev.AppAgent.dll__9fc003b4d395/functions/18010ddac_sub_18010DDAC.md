# sub_18010DDAC

- ea: `0x18010ddac`
- end: `0x18010e896`
- name: `sub_18010DDAC`
- size: `2794`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `27`
- tags: `broker_com_uri`

## callers

- `0x18007f208`
- `0x1800f0088`
- `0x1800f0284`
- `0x1800f0658`
- `0x18010bfec`

## callees

- `0x180004300`
- `0x1800048f0`
- `0x180004bec`
- `0x1800050ac`
- `0x1800057e4`
- `0x1800184a4`
- `0x18001916c`
- `0x18001c8f8`
- `0x18001d0f4`
- `0x18001d71c`
- `0x180020dcc`
- `0x180020e60`
- `0x180021c34`
- `0x18002857c`
- `0x180028810`
- `0x18002f068`
- `0x18003906c`
- `0x18003912c`
- `0x180039194`
- `0x1800458c0`
- `0x1800572d4`
- `0x18007ad10`
- `0x1800e40b4`
- `0x18010dc58`
- `0x18010dd84`
- `0x18010ddac`
- `0x180135010`

## import_xrefs

- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18010dfe9`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18010e065`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18010dfe9`
- `msvcp_win!?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z` at `0x18010e065`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010e12b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010e166`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010e12b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010e166`

## string_xrefs

- `0x18010e5e0`: `Invalid custom action URI format (4): %1%`
- `0x18010e64b`: `Invalid custom action URI format (1): %1%`
- `0x18010e721`: `Invalid custom action URI format (3): %1%`
- `0x18010e6b6`: `Invalid custom action URI format (2): %1%`
- `0x18010e78c`: `Invalid custom action URI format (duplicate parameter): %1% in URI: %2%`
- `0x18010e573`: `Invalid custom action URI format (5): %1%`
- `0x18010e812`: `Invalid custom action URI format (Missing value name: %1% in URI: %2%`

## pseudocode

```c
__int64 __fastcall sub_18010DDAC(__int64 a1, __int64 a2)
{
  char *v3; // r14
  char *v4; // rsi
  __int64 v5; // r15
  char *v6; // r13
  _QWORD *v7; // rdi
  __int64 v8; // rax
  _QWORD *v9; // rbx
  _WORD *v10; // rcx
  _QWORD *v11; // r15
  __int64 *v12; // r12
  __int64 *v13; // rsi
  _QWORD *v14; // rax
  __int64 v15; // r15
  __int64 v16; // r8
  unsigned __int64 v17; // rax
  struct std::locale::_Locimp *v18; // rdi
  void (__fastcall ***v19)(_QWORD, __int64); // rax
  struct std::locale::_Locimp *v20; // rdi
  void (__fastcall ***v21)(_QWORD, __int64); // rax
  _QWORD *v22; // rax
  _QWORD *v23; // rcx
  _QWORD *v24; // rcx
  __int64 v25; // r8
  unsigned __int64 v26; // r9
  unsigned __int64 v27; // rcx
  char *v28; // r15
  __int64 v29; // rsi
  __int64 v30; // rcx
  __int64 v31; // rax
  char *v32; // rdi
  __int64 v33; // rax
  unsigned __int64 v34; // r8
  char *v35; // rdi
  __int64 v36; // rdi
  __int64 v37; // r14
  __int64 v38; // rsi
  __int64 v39; // rcx
  _QWORD *v40; // rax
  __int64 v41; // rdi
  __int64 v42; // r15
  _QWORD *v43; // r12
  __int64 v44; // r14
  _QWORD *v45; // rax
  __int64 v46; // rsi
  __int64 v47; // rbx
  __int64 v48; // rdx
  __int64 v49; // rbx
  __int64 v51; // rax
  __int64 v52; // rax
  __int64 v53; // rax
  __int64 v54; // rax
  __int64 v55; // rax
  __int64 v56; // rax
  __int64 v57; // rax
  __int64 v58; // rax
  __int64 v59; // rax
  __int64 v60; // rax
  __int64 v61; // rax
  __int64 v62; // rax
  __int64 v63; // rax
  __int64 v64; // rax
  __int64 v65; // rax
  __int64 v66; // rax
  __int64 v67; // r8
  __int64 v68; // rax
  __int64 v69; // r9
  __int64 v70; // rax
  __int64 v71; // rax
  __int64 v72; // rax
  __int64 v73; // rax
  __int64 v74; // r8
  __int64 v75; // rax
  __int64 v76; // r9
  __int64 v77; // rax
  __int64 v78; // rax
  __int64 v79; // rax
  __int128 v80; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v81; // [rsp+30h] [rbp-D0h]
  __int64 v82; // [rsp+38h] [rbp-C8h]
  unsigned __int64 v83; // [rsp+40h] [rbp-C0h]
  _QWORD *v84; // [rsp+48h] [rbp-B8h]
  __int64 v85; // [rsp+50h] [rbp-B0h]
  __int128 v86; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v87; // [rsp+68h] [rbp-98h]
  __int64 v88; // [rsp+70h] [rbp-90h]
  __int64 v89; // [rsp+78h] [rbp-88h]
  __int128 v90; // [rsp+80h] [rbp-80h] BYREF
  __int64 v91; // [rsp+90h] [rbp-70h]
  __int64 v92; // [rsp+98h] [rbp-68h]
  unsigned __int64 v93; // [rsp+A0h] [rbp-60h]
  char *v94; // [rsp+A8h] [rbp-58h] BYREF
  struct std::locale::_Locimp *v95; // [rsp+B0h] [rbp-50h]
  char *v96; // [rsp+B8h] [rbp-48h]
  __int64 v97; // [rsp+C0h] [rbp-40h]
  __int64 v98; // [rsp+D0h] [rbp-30h]
  __int128 v99; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v100; // [rsp+F0h] [rbp-10h]
  __int64 v101; // [rsp+F8h] [rbp-8h]
  _QWORD pExceptionObject[2]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v103; // [rsp+110h] [rbp+10h]
  _QWORD v104[4]; // [rsp+120h] [rbp+20h] BYREF
  __int128 v105; // [rsp+140h] [rbp+40h] BYREF
  __int128 v106; // [rsp+150h] [rbp+50h]
  __int128 v107; // [rsp+160h] [rbp+60h] BYREF
  __int64 v108; // [rsp+170h] [rbp+70h]
  __int64 v109; // [rsp+178h] [rbp+78h]
  __int64 v110; // [rsp+180h] [rbp+80h]
  __int128 v111; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v112; // [rsp+1B0h] [rbp+B0h]
  __int64 v113; // [rsp+1B8h] [rbp+B8h]
  __int128 v114; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 v115; // [rsp+1D0h] [rbp+D0h]
  __int64 v116; // [rsp+1D8h] [rbp+D8h]
  _BYTE v117[272]; // [rsp+1E0h] [rbp+E0h] BYREF

  v85 = a2;
  v97 = a1;
  v98 = a1;
  *(_QWORD *)a1 = &Uev::CustomActionUri::`vftable';
  v3 = (char *)(a1 + 8);
  v94 = (char *)(a1 + 8);
  sub_18001D71C(a1 + 8, a2);
  v4 = (char *)(a1 + 40);
  v96 = (char *)(a1 + 40);
  *(_OWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 7;
  *(_WORD *)(a1 + 40) = 0;
  v5 = a1 + 72;
  *(_OWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 96) = 7;
  *(_WORD *)(a1 + 72) = 0;
  v6 = (char *)(a1 + 104);
  *(_OWORD *)(a1 + 104) = 0;
  *(_QWORD *)(a1 + 120) = 0;
  *(_QWORD *)(a1 + 128) = 7;
  *(_WORD *)(a1 + 104) = 0;
  v7 = (_QWORD *)(a1 + 136);
  v84 = (_QWORD *)(a1 + 136);
  *(_QWORD *)(a1 + 136) = 0;
  *(_QWORD *)(a1 + 144) = 0;
  v8 = sub_180004BEC(96);
  *(_QWORD *)v8 = v8;
  *(_QWORD *)(v8 + 8) = v8;
  *(_QWORD *)(v8 + 16) = v8;
  *(_WORD *)(v8 + 24) = 257;
  *(_QWORD *)(a1 + 136) = v8;
  v9 = (_QWORD *)(a1 + 152);
  *v9 = 0;
  v9[1] = 0;
  v9[2] = 0;
  v99 = 0;
  v100 = 0;
  v101 = 7;
  LOWORD(v99) = 0;
  v114 = 0;
  v115 = 0;
  v116 = 7;
  LOWORD(v114) = 0;
  v111 = 0;
  v112 = 0;
  v113 = 7;
  LOWORD(v111) = 0;
  *(_QWORD *)(v5 + 16) = 0;
  if ( *(_QWORD *)(v5 + 24) <= 7u )
    v10 = (_WORD *)v5;
  else
    v10 = *(_WORD **)v5;
  *v10 = 0;
  v11 = (_QWORD *)*v7;
  v12 = *(__int64 **)(*v7 + 8LL);
  if ( !*((_BYTE *)v12 + 25) )
  {
    do
    {
      sub_18003912C(v84, v84, v12[2]);
      v13 = v12;
      v12 = (__int64 *)*v12;
      sub_180028810(v13 + 8);
      sub_180028810(v13 + 4);
      j_j__o_free_0();
    }
    while ( !*((_BYTE *)v12 + 25) );
    v3 = v94;
    v4 = v96;
    v7 = v84;
  }
  v11[1] = v11;
  *v11 = v11;
  v11[2] = v11;
  v7[1] = 0;
  v90 = 0;
  v91 = 0;
  v92 = 0;
  v93 = 0;
  v14 = (_QWORD *)sub_180004BEC(16);
  v14[1] = 0;
  *(_QWORD *)&v90 = v14;
  *v14 = &v90;
  v15 = v85;
  sub_1800458C0(v85, 63, &v90);
  v17 = v93;
  if ( v93 > 2 )
  {
    v54 = sub_18001D0F4(v117, L"Invalid custom action URI format (4): %1%");
    v55 = sub_1800184A4(v54, v85);
    v56 = sub_18010DD84(pExceptionObject, v55);
    sub_18002F068(&v99, v56);
    sub_180020E60((__int64)pExceptionObject);
    sub_180020DCC((__int64)v117);
    sub_18007AD10(&v107, &v99);
    throw (Uev::ParseException *)&v107;
  }
  if ( v93 )
  {
    sub_180021C34((char *)&v114, *(char **)(*((_QWORD *)&v90 + 1) + 8 * (v92 & (v91 - 1))), v16);
    v18 = std::locale::_Init(1);
    v95 = v18;
    sub_18001C8F8(&v114, &v94);
    if ( v18 )
    {
      v19 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(struct std::locale::_Locimp *))(*(_QWORD *)v18 + 16LL))(v18);
      if ( v19 )
        (**v19)(v19, 1);
    }
    v17 = v93;
  }
  if ( v17 == 2 )
  {
    sub_180021C34((char *)&v111, *(char **)(*((_QWORD *)&v90 + 1) + 8 * ((v91 - 1) & (v92 + 1))), v16);
    v20 = std::locale::_Init(1);
    v95 = v20;
    sub_18001C8F8(&v111, &v94);
    if ( v20 )
    {
      v21 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(struct std::locale::_Locimp *))(*(_QWORD *)v20 + 16LL))(v20);
      if ( v21 )
        (**v21)(v21, 1);
    }
  }
  v80 = 0;
  v81 = 0;
  v82 = 0;
  v83 = 0;
  v22 = (_QWORD *)sub_180004BEC(16);
  v22[1] = 0;
  *(_QWORD *)&v80 = v22;
  *v22 = &v80;
  sub_1800458C0(&v114, 47, &v80);
  if ( v83 < 3 )
  {
    v57 = sub_18001D0F4(v117, L"Invalid custom action URI format (1): %1%");
    v58 = sub_1800184A4(v57, v15);
    v59 = sub_18010DD84(pExceptionObject, v58);
    sub_18002F068(&v99, v59);
    sub_180020E60((__int64)pExceptionObject);
    sub_180020DCC((__int64)v117);
    sub_18007AD10(&v107, &v99);
    throw (Uev::ParseException *)&v107;
  }
  v23 = *(_QWORD **)(*((_QWORD *)&v80 + 1) + 8 * (v82 & (v81 - 1)));
  if ( v23[3] > 7u )
    v23 = (_QWORD *)*v23;
  if ( (unsigned int)o__wcsicmp(v23, L"custom:") )
  {
    v60 = sub_18001D0F4(v117, L"Invalid custom action URI format (2): %1%");
    v61 = sub_1800184A4(v60, v15);
    v62 = sub_18010DD84(pExceptionObject, v61);
    sub_18002F068(&v99, v62);
    sub_180020E60((__int64)pExceptionObject);
    sub_180020DCC((__int64)v117);
    sub_18007AD10(&v107, &v99);
    throw (Uev::ParseException *)&v107;
  }
  v24 = *(_QWORD **)(*((_QWORD *)&v80 + 1) + 8 * ((v81 - 1) & (v82 + 1)));
  if ( v24[3] > 7u )
    v24 = (_QWORD *)*v24;
  if ( (unsigned int)o__wcsicmp(v24, &Data) )
  {
    v63 = sub_18001D0F4(v117, L"Invalid custom action URI format (3): %1%");
    v64 = sub_1800184A4(v63, v15);
    v65 = sub_18010DD84(pExceptionObject, v64);
    sub_18002F068(&v99, v65);
    sub_180020E60((__int64)pExceptionObject);
    sub_180020DCC((__int64)v117);
    sub_18007AD10(&v107, &v99);
    throw (Uev::ParseException *)&v107;
  }
  sub_180021C34(
    (char *)(v97 + 72),
    *(char **)(*((_QWORD *)&v80 + 1) + 8 * ((v81 - 1) & (v82 + 2))),
    (v81 - 1) & (v82 + 2));
  if ( v83 <= 3 )
  {
    sub_180021C34(v4, v3, v25);
  }
  else
  {
    sub_180021C34(v6, *(char **)(*((_QWORD *)&v80 + 1) + 8 * ((v81 - 1) & (v82 - 1 + v83))), v25);
    v26 = *((_QWORD *)v6 + 2);
    if ( *((_QWORD *)v6 + 3) > 7u )
      v6 = *(char **)v6;
    v27 = *((_QWORD *)v3 + 2);
    if ( *((_QWORD *)v3 + 3) <= 7u )
      v28 = v3;
    else
      v28 = *(char **)v3;
    v29 = -1;
    if ( v26 )
    {
      if ( v26 <= v27 )
      {
        v30 = v27 - v26;
        v31 = -1;
        if ( v30 != -1 )
          v31 = v30;
        v32 = &v28[2 * v26 + 2 * v31];
        v33 = sub_180004300(v28, v32, v6);
        if ( (char *)v33 != v32 )
          v29 = (v33 - (__int64)v28) >> 1;
      }
    }
    else if ( v27 != -1 )
    {
      v29 = *((_QWORD *)v3 + 2);
    }
    v105 = 0;
    v106 = 0u;
    v34 = *((_QWORD *)v3 + 2);
    if ( v34 >= v29 - 1 )
      v34 = v29 - 1;
    if ( *((_QWORD *)v3 + 3) > 7u )
      v3 = *(char **)v3;
    sub_18001916C(&v105, v3, v34);
    v35 = v96;
    if ( v96 != (char *)&v105 )
    {
      sub_180028810(v96);
      *(_OWORD *)v35 = v105;
      *((_OWORD *)v35 + 1) = v106;
      *(_QWORD *)&v106 = 0;
      *((_QWORD *)&v106 + 1) = 7;
      LOWORD(v105) = 0;
    }
    sub_180028810(&v105);
  }
  v36 = v82;
  v37 = v82 + v83;
  if ( (_QWORD)v80 )
    v38 = *(_QWORD *)v80;
  else
    v38 = 0;
  while ( v36 != v37 )
  {
    v39 = v36 & (*(_QWORD *)(v38 + 16) - 1LL);
    if ( v9[1] == v9[2] )
    {
      sub_1800572D4(v9, v9[1], *(_QWORD *)(*(_QWORD *)(v38 + 8) + 8 * v39));
    }
    else
    {
      sub_18001D71C(v9[1], *(_QWORD *)(*(_QWORD *)(v38 + 8) + 8 * v39));
      v9[1] += 32LL;
    }
    ++v36;
  }
  if ( v112 )
  {
    v107 = 0;
    v108 = 0;
    v109 = 0;
    v110 = 0;
    v40 = (_QWORD *)sub_180004BEC(16);
    v40[1] = 0;
    *(_QWORD *)&v107 = v40;
    *v40 = &v107;
    sub_1800458C0(&v111, 38, &v107);
    v41 = v109;
    v42 = v109 + v110;
    v43 = v84;
    while ( v41 != v42 )
    {
      v44 = *(_QWORD *)(*((_QWORD *)&v107 + 1) + 8 * (v41 & (v108 - 1)));
      v86 = 0;
      v87 = 0;
      v88 = 0;
      v89 = 0;
      v45 = (_QWORD *)sub_180004BEC(16);
      v45[1] = 0;
      *(_QWORD *)&v86 = v45;
      *v45 = &v86;
      sub_1800458C0(v44, 61, &v86);
      if ( v89 != 2 )
      {
        v51 = sub_18001D0F4(v117, L"Invalid custom action URI format (5): %1%");
        v52 = sub_1800184A4(v51, v85);
        v53 = sub_18010DD84(pExceptionObject, v52);
        sub_18002F068(&v99, v53);
        sub_180020E60((__int64)pExceptionObject);
        sub_180020DCC((__int64)v117);
        sub_18007AD10(pExceptionObject, &v99);
        throw (Uev::ParseException *)pExceptionObject;
      }
      v46 = *(_QWORD *)(*((_QWORD *)&v86 + 1) + 8 * (v88 & (v87 - 1)));
      sub_180039194(v43, pExceptionObject, v46);
      v47 = v103;
      if ( !*(_BYTE *)(v103 + 25) && !(unsigned __int8)sub_18003906C(v46, v103 + 32) && v47 != *v43 )
      {
        v66 = sub_18001D0F4(v117, L"Invalid custom action URI format (duplicate parameter): %1% in URI: %2%");
        v68 = sub_1800E40B4(&v86, 0, v67, v66);
        v70 = sub_1800184A4(v69, v68);
        v71 = sub_1800184A4(v70, v85);
        v72 = sub_18010DD84(pExceptionObject, v71);
        sub_18002F068(&v99, v72);
        sub_180020E60((__int64)pExceptionObject);
        sub_180020DCC((__int64)v117);
        sub_18007AD10(pExceptionObject, &v99);
        throw (Uev::ParseException *)pExceptionObject;
      }
      v48 = *(_QWORD *)(*((_QWORD *)&v86 + 1) + 8 * ((v87 - 1) & v88));
      if ( !*(_QWORD *)(v48 + 16) )
      {
        v73 = sub_18001D0F4(v117, L"Invalid custom action URI format (Missing value name: %1% in URI: %2%");
        v75 = sub_1800E40B4(&v86, 0, v74, v73);
        v77 = sub_1800184A4(v76, v75);
        v78 = sub_1800184A4(v77, v44);
        v79 = sub_18010DD84(pExceptionObject, v78);
        sub_18002F068(&v99, v79);
        sub_180020E60((__int64)pExceptionObject);
        sub_180020DCC((__int64)v117);
        sub_18007AD10(pExceptionObject, &v99);
        throw (Uev::ParseException *)pExceptionObject;
      }
      v49 = *(_QWORD *)(*((_QWORD *)&v86 + 1) + 8 * ((v87 - 1) & (v88 + 1)));
      sub_18001D71C((__int64)pExceptionObject, v48);
      sub_18001D71C((__int64)v104, v49);
      sub_18010DC58(v43, &v94, pExceptionObject);
      sub_180028810(v104);
      sub_180028810(pExceptionObject);
      sub_18002857C(&v86);
      *(_QWORD *)&v86 = 0;
      j_j__o_free_0();
      ++v41;
    }
    sub_18002857C(&v107);
    *(_QWORD *)&v107 = 0;
    j_j__o_free_0();
  }
  sub_18002857C(&v80);
  *(_QWORD *)&v80 = 0;
  j_j__o_free_0();
  sub_18002857C(&v90);
  *(_QWORD *)&v90 = 0;
  j_j__o_free_0();
  sub_180028810(&v111);
  sub_180028810(&v114);
  sub_180028810(&v99);
  return v97;
}

```

## disassembly

```asm
0x18010ddac  mov     [rsp-8+arg_10], rbx
0x18010ddb1  push    rbp
0x18010ddb2  push    rsi
0x18010ddb3  push    rdi
0x18010ddb4  push    r12
0x18010ddb6  push    r13
0x18010ddb8  push    r14
0x18010ddba  push    r15
0x18010ddbc  lea     rbp, [rsp-200h]
0x18010ddc4  sub     rsp, 300h
0x18010ddcb  mov     rax, cs:__security_cookie
0x18010ddd2  xor     rax, rsp
0x18010ddd5  mov     [rbp+230h+var_40], rax
0x18010dddc  mov     [rsp+330h+var_2E0], rdx
0x18010dde1  mov     rbx, rcx
0x18010dde4  mov     [rbp+230h+var_270], rcx
0x18010dde8  mov     [rbp+230h+var_260], rcx
0x18010ddec  xor     r12d, r12d
0x18010ddef  lea     rax, ??_7CustomActionUri@Uev@@6B@; const Uev::CustomActionUri::`vftable'
0x18010ddf6  mov     [rcx], rax
0x18010ddf9  lea     r14, [rcx+8]
0x18010ddfd  mov     [rbp+230h+var_288], r14
0x18010de01  mov     rcx, r14
0x18010de04  call    sub_18001D71C
0x18010de09  nop
0x18010de0a  lea     rsi, [rbx+28h]
0x18010de0e  mov     [rbp+230h+var_278], rsi
0x18010de12  xorps   xmm0, xmm0
0x18010de15  movups  xmmword ptr [rsi], xmm0
0x18010de18  mov     [rsi+10h], r12
0x18010de1c  lea     ecx, [r12+7]
0x18010de21  mov     [rsi+18h], rcx
0x18010de25  mov     [rsi], r12w
0x18010de29  lea     r15, [rbx+48h]
0x18010de2d  movups  xmmword ptr [r15], xmm0
0x18010de31  mov     [r15+10h], r12
0x18010de35  mov     [r15+18h], rcx
0x18010de39  mov     [r15], r12w
0x18010de3d  lea     r13, [rbx+68h]
0x18010de41  movups  xmmword ptr [r13+0], xmm0
0x18010de46  mov     [r13+10h], r12
0x18010de4a  mov     [r13+18h], rcx
0x18010de4e  mov     [r13+0], r12w
0x18010de53  lea     rdi, [rbx+88h]
0x18010de5a  mov     [rsp+330h+var_2E8], rdi
0x18010de5f  mov     [rdi], r12
0x18010de62  mov     [rdi+8], r12
0x18010de66  lea     ecx, [r12+60h]
0x18010de6b  call    sub_180004BEC
0x18010de70  mov     [rax], rax
0x18010de73  mov     [rax+8], rax
0x18010de77  mov     [rax+10h], rax
0x18010de7b  mov     word ptr [rax+18h], 101h
0x18010de81  mov     [rdi], rax
0x18010de84  add     rbx, 98h
0x18010de8b  mov     [rbx], r12
0x18010de8e  mov     [rbx+8], r12
0x18010de92  mov     [rbx+10h], r12
0x18010de96  xorps   xmm0, xmm0
0x18010de99  movups  [rbp+230h+var_250], xmm0
0x18010de9d  mov     [rbp+230h+var_240], r12
0x18010dea1  lea     ecx, [r12+7]
0x18010dea6  mov     [rbp+230h+var_238], rcx
0x18010deaa  mov     word ptr [rbp+230h+var_250], r12w
0x18010deaf  movups  [rbp+230h+var_170], xmm0
0x18010deb6  mov     [rbp+230h+var_160], r12
0x18010debd  mov     [rbp+230h+var_158], rcx
0x18010dec4  mov     word ptr [rbp+230h+var_170], r12w
0x18010decc  movups  [rbp+230h+var_190], xmm0
0x18010ded3  mov     [rbp+230h+var_180], r12
0x18010deda  mov     [rbp+230h+var_178], rcx
0x18010dee1  mov     word ptr [rbp+230h+var_190], r12w
0x18010dee9  mov     [r15+10h], r12
0x18010deed  cmp     [r15+18h], rcx
0x18010def1  jbe     short loc_18010DEF8
0x18010def3  mov     rcx, [r15]
0x18010def6  jmp     short loc_18010DEFB
0x18010def8  mov     rcx, r15
0x18010defb  mov     [rcx], r12w
0x18010deff  mov     r15, [rdi]
0x18010df02  mov     r12, [r15+8]
0x18010df06  cmp     byte ptr [r12+19h], 0
0x18010df0c  jnz     short loc_18010DF5E
0x18010df0e  mov     r14, [rsp+330h+var_2E8]
0x18010df13  mov     r8, [r12+10h]
0x18010df18  mov     rdx, r14
0x18010df1b  mov     rcx, r14
0x18010df1e  call    sub_18003912C
0x18010df23  mov     rsi, r12
0x18010df26  mov     r12, [r12]
0x18010df2a  lea     rcx, [rsi+40h]
0x18010df2e  call    sub_180028810
0x18010df33  lea     rcx, [rsi+20h]
0x18010df37  call    sub_180028810
0x18010df3c  mov     edx, 60h ; '`'
0x18010df41  mov     rcx, rsi
0x18010df44  call    j_j__o_free_0
0x18010df49  cmp     byte ptr [r12+19h], 0
0x18010df4f  jz      short loc_18010DF13
0x18010df51  mov     r14, [rbp+230h+var_288]
0x18010df55  mov     rsi, [rbp+230h+var_278]
0x18010df59  mov     rdi, [rsp+330h+var_2E8]
0x18010df5e  mov     [r15+8], r15
0x18010df62  mov     [r15], r15
0x18010df65  mov     [r15+10h], r15
0x18010df69  xor     r12d, r12d
0x18010df6c  mov     [rdi+8], r12
0x18010df70  xorps   xmm0, xmm0
0x18010df73  movdqu  [rbp+230h+var_2B0], xmm0
0x18010df78  mov     [rbp+230h+var_2A0], r12
0x18010df7c  mov     [rbp+230h+var_298], r12
0x18010df80  mov     [rbp+230h+var_290], r12
0x18010df84  lea     ecx, [r12+10h]
0x18010df89  call    sub_180004BEC
0x18010df8e  mov     [rax+8], r12
0x18010df92  mov     qword ptr [rbp+230h+var_2B0], rax
0x18010df96  lea     rcx, [rbp+230h+var_2B0]
0x18010df9a  mov     [rax], rcx
0x18010df9d  lea     edx, [r12+3Fh]
0x18010dfa2  lea     r8, [rbp+230h+var_2B0]
0x18010dfa6  mov     r15, [rsp+330h+var_2E0]
0x18010dfab  mov     rcx, r15
0x18010dfae  call    sub_1800458C0
0x18010dfb3  mov     rax, [rbp+230h+var_290]
0x18010dfb7  cmp     rax, 2
0x18010dfbb  ja      loc_18010E5E0
0x18010dfc1  cmp     rax, 1
0x18010dfc5  jb      short loc_18010E037
0x18010dfc7  mov     rax, [rbp+230h+var_2A0]
0x18010dfcb  dec     rax
0x18010dfce  and     rax, [rbp+230h+var_298]
0x18010dfd2  mov     rdx, qword ptr [rbp+230h+var_2B0+8]
0x18010dfd6  mov     rdx, [rdx+rax*8]
0x18010dfda  lea     rcx, [rbp+230h+var_170]
0x18010dfe1  call    sub_180021C34
0x18010dfe6  nop
0x18010dfe7  mov     cl, 1
0x18010dfe9  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x18010dfef  mov     rdi, rax
0x18010dff2  mov     [rbp+230h+var_280], rax
0x18010dff6  lea     rdx, [rbp+230h+var_288]
0x18010dffa  lea     rcx, [rbp+230h+var_170]
0x18010e001  call    sub_18001C8F8
0x18010e006  nop
0x18010e007  test    rdi, rdi
0x18010e00a  jz      short loc_18010E033
0x18010e00c  mov     rax, [rdi]
0x18010e00f  mov     rcx, rdi
0x18010e012  mov     rax, [rax+10h]
0x18010e016  call    j__guard_dispatch_icall
0x18010e01b  mov     rcx, rax
0x18010e01e  test    rax, rax
0x18010e021  jz      short loc_18010E033
0x18010e023  mov     rax, [rax]
0x18010e026  lea     edx, [r12+1]
0x18010e02b  mov     rax, [rax]
0x18010e02e  call    j__guard_dispatch_icall
0x18010e033  mov     rax, [rbp+230h+var_290]
0x18010e037  cmp     rax, 2
0x18010e03b  jnz     short loc_18010E0AF
0x18010e03d  mov     rcx, [rbp+230h+var_298]
0x18010e041  inc     rcx
0x18010e044  mov     rax, [rbp+230h+var_2A0]
0x18010e048  dec     rax
0x18010e04b  and     rcx, rax
0x18010e04e  mov     rdx, qword ptr [rbp+230h+var_2B0+8]
0x18010e052  mov     rdx, [rdx+rcx*8]
0x18010e056  lea     rcx, [rbp+230h+var_190]
0x18010e05d  call    sub_180021C34
0x18010e062  nop
0x18010e063  mov     cl, 1
0x18010e065  call    cs:__imp_?_Init@locale@std@@CAPEAV_Locimp@12@_N@Z; std::locale::_Init(bool)
0x18010e06b  mov     rdi, rax
0x18010e06e  mov     [rbp+230h+var_280], rax
0x18010e072  lea     rdx, [rbp+230h+var_288]
0x18010e076  lea     rcx, [rbp+230h+var_190]
0x18010e07d  call    sub_18001C8F8
0x18010e082  nop
0x18010e083  test    rdi, rdi
0x18010e086  jz      short loc_18010E0AF
0x18010e088  mov     rax, [rdi]
0x18010e08b  mov     rcx, rdi
0x18010e08e  mov     rax, [rax+10h]
0x18010e092  call    j__guard_dispatch_icall
0x18010e097  mov     rcx, rax
0x18010e09a  test    rax, rax
0x18010e09d  jz      short loc_18010E0AF
0x18010e09f  mov     rax, [rax]
0x18010e0a2  mov     edx, 1
0x18010e0a7  mov     rax, [rax]
0x18010e0aa  call    j__guard_dispatch_icall
0x18010e0af  xorps   xmm0, xmm0
0x18010e0b2  movdqu  [rsp+330h+var_310], xmm0
0x18010e0b8  mov     [rsp+330h+var_300], r12
0x18010e0bd  mov     [rsp+330h+var_2F8], r12
0x18010e0c2  mov     [rsp+330h+var_2F0], r12
0x18010e0c7  mov     ecx, 10h
0x18010e0cc  call    sub_180004BEC
0x18010e0d1  mov     [rax+8], r12
0x18010e0d5  mov     qword ptr [rsp+330h+var_310], rax
0x18010e0da  lea     rcx, [rsp+330h+var_310]
0x18010e0df  mov     [rax], rcx
0x18010e0e2  mov     edx, 2Fh ; '/'
0x18010e0e7  lea     r8, [rsp+330h+var_310]
0x18010e0ec  lea     rcx, [rbp+230h+var_170]
0x18010e0f3  call    sub_1800458C0
0x18010e0f8  cmp     [rsp+330h+var_2F0], 3
0x18010e0fe  jb      loc_18010E64B
0x18010e104  mov     rcx, [rsp+330h+var_300]
0x18010e109  dec     rcx
0x18010e10c  and     rcx, [rsp+330h+var_2F8]
0x18010e111  mov     rax, qword ptr [rsp+330h+var_310+8]
0x18010e116  mov     rcx, [rax+rcx*8]
0x18010e11a  cmp     qword ptr [rcx+18h], 7
0x18010e11f  jbe     short loc_18010E124
0x18010e121  mov     rcx, [rcx]
0x18010e124  lea     rdx, aCustom_0; "custom:"
0x18010e12b  call    cs:_o__wcsicmp
0x18010e131  test    eax, eax
0x18010e133  jnz     loc_18010E6B6
0x18010e139  mov     rcx, [rsp+330h+var_2F8]
0x18010e13e  inc     rcx
0x18010e141  mov     rax, [rsp+330h+var_300]
0x18010e146  dec     rax
0x18010e149  and     rcx, rax
0x18010e14c  mov     rax, qword ptr [rsp+330h+var_310+8]
0x18010e151  mov     rcx, [rax+rcx*8]
0x18010e155  cmp     qword ptr [rcx+18h], 7
0x18010e15a  jbe     short loc_18010E15F
0x18010e15c  mov     rcx, [rcx]
0x18010e15f  lea     rdx, Data
0x18010e166  call    cs:_o__wcsicmp
0x18010e16c  test    eax, eax
0x18010e16e  jnz     loc_18010E721
0x18010e174  mov     r8, [rsp+330h+var_2F8]
0x18010e179  add     r8, 2
0x18010e17d  mov     rax, [rsp+330h+var_300]
0x18010e182  dec     rax
0x18010e185  and     r8, rax
0x18010e188  mov     rdx, qword ptr [rsp+330h+var_310+8]
0x18010e18d  mov     rdx, [rdx+r8*8]
0x18010e191  mov     rcx, [rbp+230h+var_270]
0x18010e195  add     rcx, 48h ; 'H'
0x18010e199  call    sub_180021C34
0x18010e19e  mov     rcx, [rsp+330h+var_2F0]
0x18010e1a3  cmp     rcx, 3
0x18010e1a7  jbe     loc_18010E2B1
0x18010e1ad  mov     rax, [rsp+330h+var_2F8]
0x18010e1b2  dec     rax
0x18010e1b5  add     rcx, rax
0x18010e1b8  mov     rax, [rsp+330h+var_300]
0x18010e1bd  dec     rax
0x18010e1c0  and     rcx, rax
0x18010e1c3  mov     rdx, qword ptr [rsp+330h+var_310+8]
0x18010e1c8  mov     rdx, [rdx+rcx*8]
0x18010e1cc  mov     rcx, r13
0x18010e1cf  call    sub_180021C34
0x18010e1d4  mov     r9, [r13+10h]
0x18010e1d8  cmp     qword ptr [r13+18h], 7
0x18010e1dd  jbe     short loc_18010E1E3
0x18010e1df  mov     r13, [r13+0]
0x18010e1e3  mov     rcx, [r14+10h]
0x18010e1e7  cmp     qword ptr [r14+18h], 7
0x18010e1ec  jbe     short loc_18010E1F3
0x18010e1ee  mov     r15, [r14]
0x18010e1f1  jmp     short loc_18010E1F6
0x18010e1f3  mov     r15, r14
0x18010e1f6  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18010e1fa  test    r9, r9
0x18010e1fd  jnz     short loc_18010E208
0x18010e1ff  cmp     rcx, rsi
0x18010e202  cmovb   rsi, rcx
0x18010e206  jmp     short loc_18010E23D
0x18010e208  cmp     r9, rcx
0x18010e20b  ja      short loc_18010E23D
0x18010e20d  sub     rcx, r9
0x18010e210  mov     rax, rsi
0x18010e213  cmp     rcx, rsi
0x18010e216  cmovb   rax, rcx
0x18010e21a  add     rax, r9
0x18010e21d  lea     rdi, [r15+rax*2]
0x18010e221  mov     r8, r13
0x18010e224  mov     rdx, rdi
0x18010e227  mov     rcx, r15
0x18010e22a  call    sub_180004300
0x18010e22f  cmp     rax, rdi
0x18010e232  jz      short loc_18010E23D
0x18010e234  mov     rsi, rax
0x18010e237  sub     rsi, r15
0x18010e23a  sar     rsi, 1
0x18010e23d  xorps   xmm0, xmm0
0x18010e240  movups  [rbp+230h+var_1F0], xmm0
0x18010e244  mov     qword ptr [rbp+230h+var_1E0], r12
0x18010e248  mov     qword ptr [rbp+230h+var_1E0+8], r12
0x18010e24c  lea     rax, [rsi-1]
0x18010e250  mov     r8, [r14+10h]
0x18010e254  cmp     r8, rax
0x18010e257  cmovnb  r8, rax
0x18010e25b  cmp     qword ptr [r14+18h], 7
0x18010e260  jbe     short loc_18010E265
  ... truncated ...
```
