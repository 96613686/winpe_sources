# _expandlocale

- ea: `0x1800547f0`
- end: `0x1800555b6`
- name: `_expandlocale`
- size: `3526`
- prototype: `__int64 __fastcall(HKEY, const WCHAR *, const void **, __int128 *, _QWORD **)`
- caller_count: `1`
- callee_count: `32`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180054454`

## callees

- `0x180002b00`
- `0x180002b24`
- `0x180002f14`
- `0x180003678`
- `0x180003690`
- `0x1800037f0`
- `0x180003980`
- `0x180003c14`
- `0x1800053ec`
- `0x180005454`
- `0x180007ab8`
- `0x18000b190`
- `0x18000b21c`
- `0x18000f9b0`
- `0x18000faf8`
- `0x18003de3c`
- `0x180050c84`
- `0x180050f58`
- `0x180050ff4`
- `0x180051090`
- `0x180052494`
- `0x180052528`
- `0x180052868`
- `0x1800547f0`
- `0x1800555bc`
- `0x18005586c`
- `0x180057528`
- `0x18005c8f0`
- `0x18005ccb4`
- `0x18005ce14`
- `0x18005d258`
- `0x18006a010`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x180054ab5`
- `ADVAPI32!RegQueryValueExW` at `0x180054bfb`
- `ADVAPI32!RegQueryValueExW` at `0x180054d3f`
- `ADVAPI32!RegQueryValueExW` at `0x180054ef6`
- `ADVAPI32!RegQueryValueExW` at `0x180055192`
- `ADVAPI32!RegQueryValueExW` at `0x1800551db`
- `ADVAPI32!RegQueryValueExW` at `0x180054ab5`
- `ADVAPI32!RegQueryValueExW` at `0x180054bfb`
- `ADVAPI32!RegQueryValueExW` at `0x180054d3f`
- `ADVAPI32!RegQueryValueExW` at `0x180054ef6`
- `ADVAPI32!RegQueryValueExW` at `0x180055192`
- `ADVAPI32!RegQueryValueExW` at `0x1800551db`
- `ADVAPI32!RegOpenKeyExW` at `0x180054850`
- `ADVAPI32!RegOpenKeyExW` at `0x180054850`
- `ADVAPI32!RegCloseKey` at `0x180055247`
- `ADVAPI32!RegCloseKey` at `0x18005554a`
- `ADVAPI32!RegCloseKey` at `0x180055247`
- `ADVAPI32!RegCloseKey` at `0x18005554a`

## string_xrefs

- `0x1800548d1`: `Streaming::Configuration::GetPackageRegInfo`
- `0x180054add`: `Streaming::Configuration::GetPackageRegInfo`
- `0x180054c21`: `Streaming::Configuration::GetPackageRegInfo`
- `0x180054d65`: `Streaming::Configuration::GetPackageRegInfo`
- `0x180054f1d`: `Streaming::Configuration::GetPackageRegInfo`
- `0x18005501b`: `PackageURI`

## pseudocode

```c
__int64 __fastcall expandlocale(HKEY a1, const WCHAR *a2, const void **a3, __int128 *a4, _QWORD **a5)
{
  const void **v6; // rsi
  volatile signed __int32 *v7; // rbx
  HKEY v8; // rdi
  __int64 v9; // r8
  char v10; // bl
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rsi
  _QWORD *v14; // rcx
  _QWORD *v15; // rbx
  __int64 v16; // rbx
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rbx
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rbx
  __int64 v27; // rcx
  __int64 v28; // rax
  __int64 v29; // rax
  _DWORD *v30; // rbx
  _QWORD *v31; // rcx
  _QWORD *v32; // rbx
  __int64 v33; // rcx
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rbx
  __int64 v38; // r8
  _WORD *v39; // r9
  unsigned __int64 v40; // rdx
  void **v41; // rsi
  __int64 v42; // rbx
  __int64 v43; // r8
  _WORD *v44; // r9
  unsigned __int64 v45; // rdx
  void **v46; // rsi
  __int64 v47; // rbx
  _WORD *v48; // rdx
  __int64 v49; // r8
  char v50; // bl
  int v51; // ebx
  __int64 v52; // rax
  _QWORD *v53; // rdx
  int v54; // esi
  __int64 v55; // r8
  volatile signed __int32 *v56; // rbx
  char *v58; // rsi
  _QWORD *i; // rbx
  const void *v60; // rax
  int v61; // eax
  __int64 v62; // rax
  __int64 v63; // rax
  __int64 v64; // rcx
  __int64 v65; // rax
  __int64 v66; // rax
  __int64 v67; // rcx
  __int64 v68; // rax
  _QWORD *v69; // rdx
  volatile signed __int32 *v70; // rbx
  char v71; // [rsp+60h] [rbp-A0h]
  DWORD Type; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cbData; // [rsp+68h] [rbp-98h] BYREF
  LSTATUS v74; // [rsp+6Ch] [rbp-94h] BYREF
  BYTE Data[8]; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  int v77; // [rsp+80h] [rbp-80h] BYREF
  __int128 v78; // [rsp+88h] [rbp-78h] BYREF
  BYTE v79[8]; // [rsp+98h] [rbp-68h] BYREF
  __int128 v80; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v81; // [rsp+B0h] [rbp-50h]
  __int64 v82; // [rsp+B8h] [rbp-48h]
  _QWORD v83[2]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v84[4]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v85; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v86; // [rsp+100h] [rbp+0h]
  __int64 v87; // [rsp+108h] [rbp+8h]
  void *Buf2[2]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v89; // [rsp+120h] [rbp+20h]
  __int64 v90; // [rsp+128h] [rbp+28h]
  __int128 v91; // [rsp+130h] [rbp+30h] BYREF
  __int64 v92; // [rsp+140h] [rbp+40h]
  __int64 v93; // [rsp+148h] [rbp+48h]
  int v94; // [rsp+150h] [rbp+50h]
  void *v95[2]; // [rsp+158h] [rbp+58h] BYREF
  unsigned __int64 v96; // [rsp+168h] [rbp+68h]
  unsigned __int64 v97; // [rsp+170h] [rbp+70h]
  void *v98[2]; // [rsp+178h] [rbp+78h] BYREF
  unsigned __int64 v99; // [rsp+188h] [rbp+88h]
  unsigned __int64 v100; // [rsp+190h] [rbp+90h]
  __int128 v101; // [rsp+198h] [rbp+98h] BYREF
  __int64 v102; // [rsp+1A8h] [rbp+A8h]
  __int64 v103; // [rsp+1B0h] [rbp+B0h]
  _QWORD v104[2]; // [rsp+1B8h] [rbp+B8h] BYREF
  _BYTE v105[16]; // [rsp+1C8h] [rbp+C8h] BYREF
  int v106; // [rsp+1D8h] [rbp+D8h]
  __int128 v107; // [rsp+1E8h] [rbp+E8h] BYREF
  __int128 v108; // [rsp+1F8h] [rbp+F8h] BYREF
  _QWORD v109[2]; // [rsp+208h] [rbp+108h] BYREF
  _BYTE v110[32]; // [rsp+218h] [rbp+118h] BYREF

  v6 = a3;
  *(_QWORD *)&v80 = a3;
  v84[0] = a2;
  v84[2] = a4;
  hKey = 0;
  if ( RegOpenKeyExW(a1, a2, 0, 9u, &hKey) )
  {
    v7 = (volatile signed __int32 *)*((_QWORD *)a4 + 1);
    if ( v7 )
    {
LABEL_101:
      if ( _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
        if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
      }
    }
    return 0;
  }
  v8 = hKey;
  v84[3] = hKey;
  v107 = 0;
  v85 = 0;
  v86 = 0;
  v87 = 0;
  v9 = -1;
  do
    ++v9;
  while ( *(_WORD *)(v84[0] + 2 * v9) );
  sub_180003980(&v85, v84[0]);
  v10 = sub_18003DE3C(&v85, &v107);
  sub_180005454(&v85);
  if ( !v10 )
  {
    sub_18005C8F0(&v91, "Streaming::Configuration::GetPackageRegInfo");
    v94 = 247;
    sub_180007AB8();
    v101 = 0;
    v102 = 0;
    v103 = 0;
    sub_180003980(&v101, L"Microsoft AppV Streaming Manager %2% error:  result %1%,  key name %3%.", 71);
    v12 = sub_18005CE14(v11, v104, &v101);
    v77 = -2147024809;
    v13 = sub_1800037F0(v12, &v77);
    ++*(_DWORD *)(v13 + 8);
    sub_18005D258(v13, &v78);
    v14 = (_QWORD *)v78;
    if ( (_QWORD)v78 )
    {
      v83[0] = v13;
      v83[1] = L"invalid key name";
      sub_180052868(Buf2, v78, 0, v83);
      v14 = (_QWORD *)v78;
    }
    *(_QWORD *)&v78 = 0;
    if ( v14 )
    {
      do
      {
        v15 = (_QWORD *)*v14;
        j_j__o_free(v14, 32);
        v14 = v15;
      }
      while ( v15 );
    }
    v16 = sub_18000B21C(v13, v84);
    v85 = 0;
    v86 = 0;
    v87 = 0;
    sub_180003980(&v85, L"StreamingManager", 16);
    sub_18005CCB4(&v91, 1, &v85, v16);
    sub_180005454(&v85);
    v104[0] = &AppV::LogFormatter::`vftable';
    sub_180005454(v105);
    sub_180005454(&v101);
    sub_1800053EC(&v91);
LABEL_100:
    RegCloseKey(v8);
    v7 = (volatile signed __int32 *)*((_QWORD *)a4 + 1);
    if ( v7 )
      goto LABEL_101;
    return 0;
  }
  *(_QWORD *)&v101 = 0;
  *(_OWORD *)v98 = 0;
  v99 = 0;
  v100 = 7;
  LOWORD(v98[0]) = 0;
  *(_OWORD *)v95 = 0;
  v96 = 0;
  v97 = 7;
  LOWORD(v95[0]) = 0;
  v108 = 0;
  cbData = 4;
  Type = 0;
  *(_DWORD *)Data = 0;
  *(_QWORD *)v79 = 0;
  v74 = RegQueryValueExW(hKey, L"PackageState", 0, &Type, Data, &cbData);
  if ( v74 || Type != 4 )
  {
    v77 = 0;
    sub_18005C8F0(&v91, "Streaming::Configuration::GetPackageRegInfo");
    v94 = 278;
    sub_180007AB8();
    *(_OWORD *)Buf2 = 0;
    v89 = 0;
    v90 = 0;
    sub_180003980(Buf2, L"Microsoft AppV Streaming Manager %2% error:  result %1%,  key name %3%.", 71);
    v18 = sub_18005CE14(v17, v104, Buf2);
    v19 = sub_18000B190(v18, &v74);
    v20 = sub_180052494(v19);
    v21 = sub_180052528(v20, L"PackageState");
    v85 = 0;
    v86 = 0;
    v87 = 0;
    sub_180003980(&v85, L"StreamingManager", 16);
    sub_18005CCB4(&v91, 1, &v85, v21);
    sub_180005454(&v85);
    v104[0] = &AppV::LogFormatter::`vftable';
    sub_180005454(v105);
    sub_180005454(Buf2);
    sub_1800053EC(&v91);
  }
  else
  {
    v77 = *(_DWORD *)Data;
  }
  cbData = 8;
  v74 = RegQueryValueExW(hKey, L"StreamedBytes", 0, &Type, v79, &cbData);
  if ( v74 || Type != 11 )
  {
    v82 = 0;
    sub_18005C8F0(&v91, "Streaming::Configuration::GetPackageRegInfo");
    v94 = 293;
    sub_180007AB8();
    *(_OWORD *)Buf2 = 0;
    v89 = 0;
    v90 = 0;
    sub_180003980(Buf2, L"Microsoft AppV Streaming Manager %2% error:  result %1%,  key name %3%.", 71);
    v23 = sub_18005CE14(v22, v104, Buf2);
    v24 = sub_18000B190(v23, &v74);
    v25 = sub_180052494(v24);
    v26 = sub_180052528(v25, L"StreamedBytes");
    v85 = 0;
    v86 = 0;
    v87 = 0;
    sub_180003980(&v85, L"StreamingManager", 16);
    sub_18005CCB4(&v91, 1, &v85, v26);
    sub_180005454(&v85);
    v104[0] = &AppV::LogFormatter::`vftable';
    sub_180005454(v105);
    sub_180005454(Buf2);
    sub_1800053EC(&v91);
  }
  else
  {
    v82 = *(_QWORD *)v79;
  }
  cbData = 8;
  v74 = RegQueryValueExW(hKey, L"PackageSize", 0, &Type, v79, &cbData);
  if ( v74 || Type != 11 )
  {
    v81 = 0;
    sub_18005C8F0(v104, "Streaming::Configuration::GetPackageRegInfo");
    v106 = 308;
    sub_180007AB8();
    v91 = 0;
    v92 = 0;
    v93 = 0;
    sub_180003980(&v91, L"Microsoft AppV Streaming Manager %2% error:  result %1%,  key name %3%.", 71);
    v28 = sub_18005CE14(v27, v109, &v91);
    v29 = sub_18000B190(v28, &v74);
    v30 = (_DWORD *)sub_180052494(v29);
    v83[0] = v30;
    ++v30[2];
    sub_18005D258(v30, &v78);
    v31 = (_QWORD *)v78;
    if ( (_QWORD)v78 )
    {
      Buf2[0] = v30;
      Buf2[1] = (void *)L"PackageSize";
      sub_180052868(&v85, v78, 0, Buf2);
      v31 = (_QWORD *)v78;
    }
    *(_QWORD *)&v78 = 0;
    if ( v31 )
    {
      do
      {
        v32 = (_QWORD *)*v31;
        j_j__o_free(v31, 32);
        v31 = v32;
      }
      while ( v32 );
      v6 = (const void **)v80;
      v30 = (_DWORD *)v83[0];
    }
    v85 = 0;
    v86 = 0;
    v87 = 0;
    sub_180003980(&v85, L"StreamingManager", 16);
    sub_18005CCB4(v104, 1, &v85, v30);
    sub_180005454(&v85);
    v109[0] = &AppV::LogFormatter::`vftable';
    sub_180005454(v110);
    sub_180005454(&v91);
    sub_1800053EC(v104);
  }
  else
  {
    v81 = *(_QWORD *)v79;
  }
  cbData = 4;
  v74 = RegQueryValueExW(hKey, L"PreviouslyUsed", 0, &Type, Data, &cbData);
  if ( v74 || Type != 4 )
  {
    v71 = 0;
    sub_18005C8F0(v104, "Streaming::Configuration::GetPackageRegInfo");
    v106 = 323;
    sub_180007AB8();
    v85 = 0;
    v86 = 0;
    v87 = 0;
    sub_180003980(&v85, L"Microsoft AppV Streaming Manager %2% error:  result %1%,  key name %3%.", 71);
    v34 = sub_18005CE14(v33, v109, &v85);
    v35 = sub_18000B190(v34, &v74);
    v36 = sub_180052494(v35);
    v37 = sub_180052528(v36, L"PreviouslyUsed");
    v91 = 0;
    v92 = 0;
    v93 = 0;
    sub_180003980(&v91, L"StreamingManager", 16);
    sub_18005CCB4(v104, 1, &v91, v37);
    sub_180005454(&v91);
    v109[0] = &AppV::LogFormatter::`vftable';
    sub_180005454(v110);
    sub_180005454(&v85);
    sub_1800053EC(v104);
  }
  else
  {
    v71 = *(_DWORD *)Data != 0;
  }
  if ( (unsigned __int8)sub_1800555BC(hKey) )
  {
    v39 = *v6;
    v40 = -1;
    do
      ++v40;
    while ( v39[v40] );
    if ( v40 > v100 )
    {
      sub_180003C14(v98, v40, v38, v39);
    }
    else
    {
      v41 = v98;
      if ( v100 > 7 )
        v41 = (void **)v98[0];
      v99 = v40;
      v42 = 2 * v40;
      memmove(v41, v39, 2 * v40);
      *(_WORD *)((char *)v41 + v42) = 0;
      v6 = (const void **)v80;
    }
  }
  if ( !(unsigned __int8)sub_1800555BC(hKey) )
    goto LABEL_99;
  v44 = *v6;
  v45 = -1;
  do
    ++v45;
  while ( v44[v45] );
  if ( v45 > v97 )
  {
    sub_180003C14(v95, v45, v43, v44);
  }
  else
  {
    v46 = v95;
    if ( v97 > 7 )
      v46 = (void **)v95[0];
    v96 = v45;
    v47 = 2 * v45;
    memmove(v46, v44, 2 * v45);
    *(_WORD *)((char *)v46 + v47) = 0;
    v6 = (const void **)v80;
  }
  if ( !(unsigned __int8)sub_1800555BC(hKey) )
    goto LABEL_99;
  v48 = *v6;
  v91 = 0;
  v92 = 0;
  v93 = 0;
  v49 = -1;
  do
    ++v49;
  while ( v48[v49] );
  sub_180003980(&v91, v48);
  v50 = sub_18003DE3C(&v91, &v108);
  sub_180005454(&v91);
  if ( !v50 )
  {
LABEL_99:
    sub_180005454(v95);
    sub_180005454(v98);
    goto LABEL_100;
  }
  v51 = 0;
  cbData = 8;
  v74 = RegQueryValueExW(hKey, L"Version", 0, &Type, v79, &cbData);
  if ( !v74 )
  {
    v52 = 0;
    if ( Type == 11 )
      v52 = *(_QWORD *)v79;
    *(_QWORD *)&v101 = v52;
  }
  v74 = RegQueryValueExW(hKey, L"Count", 0, &Type, Data, &cbData);
  if ( !v74 && Type == 4 )
    v51 = *(_DWORD *)Data;
  v78 = 0;
  if ( !v51 )
  {
    if ( !v99 )
      goto LABEL_99;
    v66 = sub_180002B24(168);
    v83[0] = v66;
    v80 = 0;
    v67 = *((_QWORD *)a4 + 1);
    if ( v67 )
      _InterlockedIncrement((volatile signed __int32 *)(v67 + 8));
    v80 = *a4;
    v68 = sub_180051090(
            v66,
            (unsigned int)&v108,
            (unsigned int)&v107,
            (unsigned int)v98,
            (__int64)v95,
            (__int64)&v80,
            (__int64)&v101,
            v77,
            v82,
            v81,
            v71,
            0);
    sub_180050FF4(&v78, v68);
    goto LABEL_90;
  }
  *(_OWORD *)Buf2 = 0;
  v89 = 0;
  v54 = sub_18005586C(hKey);
  v55 = 0;
  if ( v54 >= 0 )
  {
    v58 = (char *)Buf2[0];
    if ( ((char *)Buf2[1] - (char *)Buf2[0]) >> 4 != v51 )
    {
LABEL_68:
      sub_18000F9B0(Buf2);
      goto LABEL_99;
    }
    v85 = 0;
    v86 = 0;
    while ( v58 != Buf2[1] )
    {
      for ( i = *a5; ; i += 2 )
      {
        if ( i == a5[1] )
        {
          sub_18000FAF8(&v85);
          goto LABEL_68;
        }
        v60 = (const void *)(*(__int64 (__fastcall **)(_QWORD, _QWORD *, __int64))(*(_QWORD *)*i + 32LL))(*i, v53, v55);
        v61 = memcmp(v60, v58, 0x10u);
        v55 = 0;
        if ( !v61 )
          break;
      }
      v53 = (_QWORD *)*((_QWORD *)&v85 + 1);
      if ( *((_QWORD *)&v85 + 1) == v86 )
      {
        sub_180050C84(&v85, *((_QWORD *)&v85 + 1), i);
      }
      else
      {
        **((_QWORD **)&v85 + 1) = 0;
        v53[1] = 0;
        v62 = i[1];
        if ( v62 )
          _InterlockedIncrement((volatile signed __int32 *)(v62 + 8));
        *v53 = *i;
        v53[1] = i[1];
        *((_QWORD *)&v85 + 1) += 16LL;
      }
      v58 += 16;
    }
    v63 = sub_180002B24(200);
    v83[0] = v63;
    v101 = 0;
    v64 = *((_QWORD *)a4 + 1);
    if ( v64 )
      _InterlockedIncrement((volatile signed __int32 *)(v64 + 8));
    v101 = *a4;
    v65 = sub_180057528(
            v63,
            (unsigned int)&v108,
            (unsigned int)&v107,
            (unsigned int)v95,
            (unsigned int)&v101,
            (__int64)&v85,
            v77,
            v82,
            v81,
            v71);
    sub_180050F58(&v78, v65);
    sub_18000FAF8(&v85);
    sub_18000F9B0(Buf2);
LABEL_90:
    v69 = a5[1];
    if ( v69 == a5[2] )
    {
      sub_180050C84(a5, v69, &v78);
      v70 = (volatile signed __int32 *)*((_QWORD *)&v78 + 1);
    }
    else
    {
      *v69 = 0;
      v69[1] = 0;
      v70 = (volatile signed __int32 *)*((_QWORD *)&v78 + 1);
      if ( *((_QWORD *)&v78 + 1) )
        _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v78 + 1) + 8LL));
      *v69 = v78;
      v69[1] = v70;
      a5[1] += 2;
    }
    if ( v70 )
    {
      if ( _InterlockedExchangeAdd(v70 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v70)(v70);
        if ( _InterlockedExchangeAdd(v70 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v70 + 8LL))(v70);
      }
    }
    goto LABEL_99;
  }
  sub_18000F9B0(Buf2);
  sub_180005454(v95);
  sub_180005454(v98);
  RegCloseKey(v8);
  v56 = (volatile signed __int32 *)*((_QWORD *)a4 + 1);
  if ( v56 )
  {
    if ( _InterlockedExchangeAdd(v56 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v56)(v56);
      if ( _InterlockedExchangeAdd(v56 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v56 + 8LL))(v56);
    }
  }
  return (unsigned int)v54;
}

```

## disassembly

```asm
0x1800547f0  push    rbp
0x1800547f2  push    rbx
0x1800547f3  push    rsi
0x1800547f4  push    rdi
0x1800547f5  push    r12
0x1800547f7  push    r13
0x1800547f9  push    r14
0x1800547fb  push    r15
0x1800547fd  lea     rbp, [rsp-148h]
0x180054805  sub     rsp, 248h
0x18005480c  mov     rax, cs:__security_cookie
0x180054813  xor     rax, rsp
0x180054816  mov     [rbp+180h+var_48], rax
0x18005481d  mov     r15, r9
0x180054820  mov     rsi, r8
0x180054823  mov     qword ptr [rbp+180h+var_1E0], r8
0x180054827  mov     [rbp+180h+var_1B0], rdx
0x18005482b  mov     [rbp+180h+var_1A0], r9
0x18005482f  mov     r13, [rbp+180h+arg_20]
0x180054836  xor     r12d, r12d
0x180054839  mov     [rsp+280h+hKey], r12
0x18005483e  lea     rax, [rsp+280h+hKey]
0x180054843  mov     [rsp+280h+phkResult], rax; phkResult
0x180054848  lea     r9d, [r12+9]; samDesired
0x18005484d  xor     r8d, r8d; ulOptions
0x180054850  call    cs:RegOpenKeyExW
0x180054856  test    eax, eax
0x180054858  jz      short loc_180054870
0x18005485a  mov     rbx, [r15+8]
0x18005485e  test    rbx, rbx
0x180054861  jz      loc_180055591
0x180054867  or      r14, 0FFFFFFFFFFFFFFFFh
0x18005486b  jmp     loc_18005555A
0x180054870  mov     rdi, [rsp+280h+hKey]
0x180054875  mov     [rbp+180h+var_198], rdi
0x180054879  xorps   xmm0, xmm0
0x18005487c  movups  [rbp+180h+var_98], xmm0
0x180054883  mov     rdx, [rbp+180h+var_1B0]
0x180054887  movups  [rbp+180h+var_190], xmm0
0x18005488b  mov     [rbp+180h+var_180], r12
0x18005488f  mov     [rbp+180h+var_178], r12
0x180054893  or      r14, 0FFFFFFFFFFFFFFFFh
0x180054897  mov     r8, r14
0x18005489a  inc     r8
0x18005489d  cmp     [rdx+r8*2], r12w
0x1800548a2  jnz     short loc_18005489A
0x1800548a4  lea     rcx, [rbp+180h+var_190]
0x1800548a8  call    sub_180003980
0x1800548ad  nop
0x1800548ae  lea     rdx, [rbp+180h+var_98]
0x1800548b5  lea     rcx, [rbp+180h+var_190]
0x1800548b9  call    sub_18003DE3C
0x1800548be  mov     bl, al
0x1800548c0  lea     rcx, [rbp+180h+var_190]
0x1800548c4  call    sub_180005454
0x1800548c9  test    bl, bl
0x1800548cb  jnz     loc_180054A39
0x1800548d1  lea     rdx, aStreamingConfi_2
0x1800548d8  lea     rcx, [rbp+180h+var_150]
0x1800548dc  call    sub_18005C8F0
0x1800548e1  mov     [rbp+180h+var_130], 0F7h
0x1800548e8  call    sub_180007AB8
0x1800548ed  xorps   xmm0, xmm0
0x1800548f0  movups  [rbp+180h+var_E8], xmm0
0x1800548f7  mov     [rbp+180h+var_D8], r12
0x1800548fe  mov     [rbp+180h+var_D0], r12
0x180054905  mov     r8d, 47h ; 'G'
0x18005490b  lea     rdx, aMicrosoftAppvS_47
0x180054912  lea     rcx, [rbp+180h+var_E8]
0x180054919  call    sub_180003980
0x18005491e  nop
0x18005491f  lea     r8, [rbp+180h+var_E8]
0x180054926  lea     rdx, [rbp+180h+var_C8]
0x18005492d  call    sub_18005CE14
0x180054932  nop
0x180054933  mov     [rbp+180h+var_200], 80070057h
0x18005493a  lea     rdx, [rbp+180h+var_200]
0x18005493e  mov     rcx, rax
0x180054941  call    sub_1800037F0
0x180054946  mov     rsi, rax
0x180054949  mov     r8d, [rax+8]
0x18005494d  lea     ecx, [r8+1]
0x180054951  mov     [rax+8], ecx
0x180054954  lea     rdx, [rbp+180h+var_1F8]
0x180054958  mov     rcx, rax
0x18005495b  call    sub_18005D258
0x180054960  nop
0x180054961  mov     rcx, qword ptr [rbp+180h+var_1F8]
0x180054965  test    rcx, rcx
0x180054968  jz      short loc_180054990
0x18005496a  mov     r8, r12
0x18005496d  mov     [rbp+180h+var_1C0], rsi
0x180054971  lea     rax, aInvalidKeyName
0x180054978  mov     [rbp+180h+var_1B8], rax
0x18005497c  lea     r9, [rbp+180h+var_1C0]
0x180054980  mov     rdx, rcx
0x180054983  lea     rcx, [rbp+180h+Buf2]
0x180054987  call    sub_180052868
0x18005498c  mov     rcx, qword ptr [rbp+180h+var_1F8]
0x180054990  mov     qword ptr [rbp+180h+var_1F8], r12
0x180054994  test    rcx, rcx
0x180054997  jz      short loc_1800549AE
0x180054999  mov     rbx, [rcx]
0x18005499c  mov     edx, 20h ; ' '
0x1800549a1  call    j_j__o_free
0x1800549a6  mov     rcx, rbx
0x1800549a9  test    rbx, rbx
0x1800549ac  jnz     short loc_180054999
0x1800549ae  lea     rdx, [rbp+180h+var_1B0]
0x1800549b2  mov     rcx, rsi
0x1800549b5  call    sub_18000B21C
0x1800549ba  mov     rbx, rax
0x1800549bd  xorps   xmm0, xmm0
0x1800549c0  movups  [rbp+180h+var_190], xmm0
0x1800549c4  mov     [rbp+180h+var_180], r12
0x1800549c8  mov     [rbp+180h+var_178], r12
0x1800549cc  mov     r8d, 10h
0x1800549d2  lea     rdx, aStreamingmanag
0x1800549d9  lea     rcx, [rbp+180h+var_190]
0x1800549dd  call    sub_180003980
0x1800549e2  nop
0x1800549e3  mov     r9, rbx
0x1800549e6  lea     r8, [rbp+180h+var_190]
0x1800549ea  mov     edx, 1
0x1800549ef  lea     rcx, [rbp+180h+var_150]
0x1800549f3  call    sub_18005CCB4
0x1800549f8  nop
0x1800549f9  lea     rcx, [rbp+180h+var_190]
0x1800549fd  call    sub_180005454
0x180054a02  nop
0x180054a03  lea     rax, ??_7LogFormatter@AppV@@6B@
0x180054a0a  mov     [rbp+180h+var_C8], rax
0x180054a11  lea     rcx, [rbp+180h+var_B8]
0x180054a18  call    sub_180005454
0x180054a1d  nop
0x180054a1e  lea     rcx, [rbp+180h+var_E8]
0x180054a25  call    sub_180005454
0x180054a2a  nop
0x180054a2b  lea     rcx, [rbp+180h+var_150]
0x180054a2f  call    sub_1800053EC
0x180054a34  jmp     loc_180055547
0x180054a39  mov     qword ptr [rbp+180h+var_E8], 0
0x180054a44  xorps   xmm0, xmm0
0x180054a47  movups  xmmword ptr [rbp+180h+var_108], xmm0
0x180054a4b  xor     ebx, ebx
0x180054a4d  mov     [rbp+180h+var_F8], rbx
0x180054a54  lea     ecx, [rbx+7]
0x180054a57  mov     [rbp+180h+var_F0], rcx
0x180054a5e  mov     word ptr [rbp+180h+var_108], bx
0x180054a62  movups  xmmword ptr [rbp+180h+var_128], xmm0
0x180054a66  mov     [rbp+180h+var_118], rbx
0x180054a6a  mov     [rbp+180h+var_110], rcx
0x180054a6e  mov     word ptr [rbp+180h+var_128], bx
0x180054a72  movups  [rbp+180h+var_88], xmm0
0x180054a79  mov     [rsp+280h+cbData], 4
0x180054a81  mov     [rsp+280h+Type], ebx
0x180054a85  mov     dword ptr [rsp+280h+Data], ebx
0x180054a89  mov     qword ptr [rbp+180h+var_1E8], rbx
0x180054a8d  lea     rax, [rsp+280h+cbData]
0x180054a92  mov     [rsp+280h+lpcbData], rax; lpcbData
0x180054a97  lea     rax, [rsp+280h+Data]
0x180054a9c  mov     [rsp+280h+phkResult], rax; lpData
0x180054aa1  lea     r9, [rsp+280h+Type]; lpType
0x180054aa6  xor     r8d, r8d; lpReserved
0x180054aa9  lea     rdx, ValueName
0x180054ab0  mov     rcx, [rsp+280h+hKey]; hKey
0x180054ab5  call    cs:RegQueryValueExW
0x180054abb  mov     [rsp+280h+var_214], eax
0x180054abf  lea     r12d, [rbx+10h]
0x180054ac3  test    eax, eax
0x180054ac5  jnz     short loc_180054ADA
0x180054ac7  cmp     [rsp+280h+Type], 4
0x180054acc  jnz     short loc_180054ADA
0x180054ace  mov     eax, dword ptr [rsp+280h+Data]
0x180054ad2  mov     [rbp+180h+var_200], eax
0x180054ad5  jmp     loc_180054BCC
0x180054ada  mov     [rbp+180h+var_200], ebx
0x180054add  lea     rdx, aStreamingConfi_2
0x180054ae4  lea     rcx, [rbp+180h+var_150]
0x180054ae8  call    sub_18005C8F0
0x180054aed  mov     [rbp+180h+var_130], 116h
0x180054af4  call    sub_180007AB8
0x180054af9  xorps   xmm0, xmm0
0x180054afc  movups  xmmword ptr [rbp+180h+Buf2], xmm0
0x180054b00  mov     [rbp+180h+var_160], rbx
0x180054b04  mov     [rbp+180h+var_158], rbx
0x180054b08  mov     r8d, 47h ; 'G'
0x180054b0e  lea     rdx, aMicrosoftAppvS_47
0x180054b15  lea     rcx, [rbp+180h+Buf2]
0x180054b19  call    sub_180003980
0x180054b1e  nop
0x180054b1f  lea     r8, [rbp+180h+Buf2]
0x180054b23  lea     rdx, [rbp+180h+var_C8]
0x180054b2a  call    sub_18005CE14
0x180054b2f  nop
0x180054b30  lea     rdx, [rsp+280h+var_214]
0x180054b35  mov     rcx, rax
0x180054b38  call    sub_18000B190
0x180054b3d  mov     rcx, rax
0x180054b40  call    sub_180052494
0x180054b45  lea     rdx, ValueName
0x180054b4c  mov     rcx, rax
0x180054b4f  call    sub_180052528
0x180054b54  mov     rbx, rax
0x180054b57  xorps   xmm0, xmm0
0x180054b5a  movups  [rbp+180h+var_190], xmm0
0x180054b5e  xor     ecx, ecx
0x180054b60  mov     [rbp+180h+var_180], rcx
0x180054b64  mov     [rbp+180h+var_178], rcx
0x180054b68  mov     r8, r12
0x180054b6b  lea     rdx, aStreamingmanag
0x180054b72  lea     rcx, [rbp+180h+var_190]
0x180054b76  call    sub_180003980
0x180054b7b  nop
0x180054b7c  mov     r9, rbx
0x180054b7f  lea     r8, [rbp+180h+var_190]
0x180054b83  mov     edx, 1
0x180054b88  lea     rcx, [rbp+180h+var_150]
0x180054b8c  call    sub_18005CCB4
0x180054b91  nop
0x180054b92  lea     rcx, [rbp+180h+var_190]
0x180054b96  call    sub_180005454
0x180054b9b  nop
0x180054b9c  lea     rax, ??_7LogFormatter@AppV@@6B@
0x180054ba3  mov     [rbp+180h+var_C8], rax
0x180054baa  lea     rcx, [rbp+180h+var_B8]
0x180054bb1  call    sub_180005454
0x180054bb6  nop
0x180054bb7  lea     rcx, [rbp+180h+Buf2]
0x180054bbb  call    sub_180005454
0x180054bc0  nop
0x180054bc1  lea     rcx, [rbp+180h+var_150]
0x180054bc5  call    sub_1800053EC
0x180054bca  xor     ebx, ebx
0x180054bcc  mov     [rsp+280h+cbData], 8
0x180054bd4  lea     rax, [rsp+280h+cbData]
0x180054bd9  mov     [rsp+280h+lpcbData], rax; lpcbData
0x180054bde  lea     rax, [rbp+180h+var_1E8]
0x180054be2  mov     [rsp+280h+phkResult], rax; lpData
0x180054be7  lea     r9, [rsp+280h+Type]; lpType
0x180054bec  xor     r8d, r8d; lpReserved
0x180054bef  lea     rdx, aStreamedbytes
0x180054bf6  mov     rcx, [rsp+280h+hKey]; hKey
0x180054bfb  call    cs:RegQueryValueExW
0x180054c01  mov     [rsp+280h+var_214], eax
0x180054c05  test    eax, eax
0x180054c07  jnz     short loc_180054C1D
0x180054c09  cmp     [rsp+280h+Type], 0Bh
0x180054c0e  jnz     short loc_180054C1D
0x180054c10  mov     rax, qword ptr [rbp+180h+var_1E8]
0x180054c14  mov     [rbp+180h+var_1C8], rax
0x180054c18  jmp     loc_180054D10
0x180054c1d  mov     [rbp+180h+var_1C8], rbx
0x180054c21  lea     rdx, aStreamingConfi_2
0x180054c28  lea     rcx, [rbp+180h+var_150]
0x180054c2c  call    sub_18005C8F0
0x180054c31  mov     [rbp+180h+var_130], 125h
0x180054c38  call    sub_180007AB8
0x180054c3d  xorps   xmm0, xmm0
0x180054c40  movups  xmmword ptr [rbp+180h+Buf2], xmm0
0x180054c44  mov     [rbp+180h+var_160], rbx
0x180054c48  mov     [rbp+180h+var_158], rbx
0x180054c4c  mov     r8d, 47h ; 'G'
0x180054c52  lea     rdx, aMicrosoftAppvS_47
0x180054c59  lea     rcx, [rbp+180h+Buf2]
0x180054c5d  call    sub_180003980
0x180054c62  nop
0x180054c63  lea     r8, [rbp+180h+Buf2]
0x180054c67  lea     rdx, [rbp+180h+var_C8]
0x180054c6e  call    sub_18005CE14
0x180054c73  nop
0x180054c74  lea     rdx, [rsp+280h+var_214]
0x180054c79  mov     rcx, rax
0x180054c7c  call    sub_18000B190
0x180054c81  mov     rcx, rax
0x180054c84  call    sub_180052494
0x180054c89  lea     rdx, aStreamedbytes
0x180054c90  mov     rcx, rax
0x180054c93  call    sub_180052528
0x180054c98  mov     rbx, rax
0x180054c9b  xorps   xmm0, xmm0
0x180054c9e  movups  [rbp+180h+var_190], xmm0
0x180054ca2  xor     ecx, ecx
0x180054ca4  mov     [rbp+180h+var_180], rcx
0x180054ca8  mov     [rbp+180h+var_178], rcx
0x180054cac  mov     r8, r12
0x180054caf  lea     rdx, aStreamingmanag
0x180054cb6  lea     rcx, [rbp+180h+var_190]
0x180054cba  call    sub_180003980
0x180054cbf  nop
0x180054cc0  mov     r9, rbx
0x180054cc3  lea     r8, [rbp+180h+var_190]
0x180054cc7  mov     edx, 1
0x180054ccc  lea     rcx, [rbp+180h+var_150]
0x180054cd0  call    sub_18005CCB4
0x180054cd5  nop
0x180054cd6  lea     rcx, [rbp+180h+var_190]
0x180054cda  call    sub_180005454
0x180054cdf  nop
0x180054ce0  lea     rax, ??_7LogFormatter@AppV@@6B@
  ... truncated ...
```
