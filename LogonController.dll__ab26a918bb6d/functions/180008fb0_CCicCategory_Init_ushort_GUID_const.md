# CCicCategory::Init(ushort *,_GUID const &)

- ea: `0x180008fb0`
- end: `0x18000a391`
- name: `?Init@CCicCategory@@QEAAXPEAGAEBU_GUID@@@Z`
- size: `5089`
- prototype: `void __fastcall(CCicCategory *__hidden this, unsigned __int16 *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008b40`

## callees

- `0x180008fb0`
- `0x18000a398`
- `0x18006c000`
- `0x18009b790`
- `0x18009b7a8`

## import_xrefs

- `KERNEL32!LocalReAlloc` at `0x180009e22`
- `KERNEL32!LocalReAlloc` at `0x180009e22`
- `KERNEL32!LocalAlloc` at `0x180009e8c`
- `KERNEL32!LocalAlloc` at `0x180009e8c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800090c9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000938a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800095ea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800090c9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000938a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800095ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800093aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009605`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800096d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009cb9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a116`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800093aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009605`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800096d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009cb9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a116`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180009d3b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a254`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a351`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180009d3b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a254`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a351`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180009f9f`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18000a2ed`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180009f9f`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18000a2ed`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180009136`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800093ee`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000965c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180009136`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800093ee`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000965c`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall CCicCategory::Init(CCicCategory *this, unsigned __int16 *a2, const struct _GUID *a3)
{
  const struct _GUID *v3; // rdi
  WCHAR *v4; // r8
  __int64 v5; // rax
  const WCHAR *v6; // rdx
  __int64 v7; // r9
  WCHAR *v8; // rcx
  __int64 v9; // rdx
  WCHAR *v10; // rax
  DWORD v11; // r14d
  __int64 v12; // rcx
  WCHAR *v13; // r8
  const unsigned __int16 *v14; // r9
  WCHAR *v15; // rcx
  LSTATUS v16; // eax
  HKEY v17; // rsi
  DWORD v18; // ebx
  LSTATUS v19; // eax
  const unsigned __int16 *v20; // r8
  __int64 v21; // rdx
  char *v22; // rcx
  int i; // edx
  int j; // edx
  int k; // edx
  int m; // edx
  int i1; // edx
  WCHAR *p_Name; // r8
  __int64 v29; // rdx
  WCHAR *v30; // r9
  __int64 v31; // r10
  WCHAR *v32; // rcx
  __int64 v33; // rax
  WCHAR *v34; // rcx
  __int64 v35; // rdx
  WCHAR *v36; // r9
  const unsigned __int16 *v37; // r8
  WCHAR *v38; // rcx
  HKEY v39; // rbx
  LSTATUS v40; // eax
  HKEY v41; // r13
  DWORD v42; // r12d
  LSTATUS v43; // eax
  __int64 v44; // rdx
  char *v45; // rcx
  unsigned int v46; // edx
  int v47; // r9d
  int v48; // r8d
  int v49; // edx
  int v50; // r9d
  int v51; // edx
  int v52; // r8d
  int v53; // r9d
  int v54; // r8d
  int v55; // edx
  int v56; // r8d
  int v57; // edx
  int v58; // r9d
  int v59; // r8d
  int v60; // edx
  __int64 v61; // rax
  HKEY v62; // rbx
  LSTATUS v63; // eax
  HKEY v64; // r15
  bool v65; // r13
  CCicCategory *v66; // r12
  LSTATUS v67; // eax
  __int64 v68; // rdx
  GUID v69; // xmm6
  unsigned int v70; // edx
  char *v71; // rcx
  int v72; // r9d
  int v73; // r8d
  int v74; // edx
  int v75; // r9d
  int v76; // edx
  int v77; // r8d
  int v78; // edx
  int v79; // r9d
  int v80; // edx
  int v81; // r8d
  int v82; // edx
  int v83; // r9d
  int v84; // edx
  int v85; // r8d
  int v86; // edx
  int v87; // r9d
  int v88; // edx
  int v89; // r8d
  int v90; // edx
  int v91; // r9d
  int v92; // edx
  int v93; // r8d
  int v94; // edx
  int v95; // r9d
  int v96; // edx
  int v97; // r8d
  int v98; // edx
  int v99; // r9d
  int v100; // edx
  int v101; // r8d
  int v102; // edx
  int n; // edx
  int ii; // edx
  int jj; // edx
  int kk; // edx
  int mm; // edx
  int nn; // edx
  unsigned __int16 *v109; // rcx
  int v110; // r9d
  int v111; // edx
  int v112; // r8d
  int v113; // r9d
  unsigned __int16 *v114; // rcx
  int v115; // r8d
  int v116; // r9d
  int v117; // edx
  int v118; // r8d
  unsigned __int16 *v119; // rcx
  int v120; // edx
  int v121; // r9d
  int v122; // r8d
  int v123; // edx
  int v124; // ebx
  int v125; // edi
  int v126; // esi
  unsigned __int64 v127; // rcx
  void *v128; // rax
  HLOCAL v129; // rax
  int v130; // edx
  int v131; // ecx
  int v132; // eax
  int v133; // ecx
  GUID *v134; // rdx
  int v135; // edx
  int v136; // r9d
  int v137; // r8d
  int v138; // edx
  unsigned __int16 *v139; // rcx
  int v140; // edx
  int v141; // r9d
  int v142; // r8d
  int v143; // edx
  int v144; // edx
  int v145; // r9d
  int v146; // r8d
  int v147; // edx
  int v148; // edx
  int v149; // r9d
  int v150; // r8d
  int v151; // edx
  int v152; // edx
  int v153; // r9d
  int v154; // r8d
  int v155; // edx
  int v156; // edx
  int v157; // r9d
  int v158; // r8d
  int v159; // edx
  int v160; // edx
  int v161; // r9d
  int v162; // r8d
  int v163; // edx
  GUID Buf1; // [rsp+50h] [rbp-B0h] BYREF
  bool IsTsf3OverrideEnabled; // [rsp+60h] [rbp-A0h]
  DWORD cchName; // [rsp+68h] [rbp-98h] BYREF
  DWORD dwDisposition; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  HKEY phkResult; // [rsp+80h] [rbp-80h] BYREF
  DWORD lpdwDisposition; // [rsp+88h] [rbp-78h] BYREF
  HKEY v171; // [rsp+90h] [rbp-70h] BYREF
  HKEY v172; // [rsp+98h] [rbp-68h]
  HKEY v173; // [rsp+A0h] [rbp-60h]
  CCicCategory *v174; // [rsp+A8h] [rbp-58h]
  const struct _GUID *v175; // [rsp+B0h] [rbp-50h]
  WCHAR Name; // [rsp+C0h] [rbp-40h] BYREF
  char v177; // [rsp+C2h] [rbp-3Eh] BYREF
  WCHAR v178; // [rsp+2C0h] [rbp+1C0h] BYREF
  char v179; // [rsp+2C2h] [rbp+1C2h] BYREF
  WCHAR SubKey[256]; // [rsp+4C0h] [rbp+3C0h] BYREF
  WCHAR v181[256]; // [rsp+6C0h] [rbp+5C0h] BYREF
  WCHAR v182; // [rsp+8C0h] [rbp+7C0h] BYREF
  char v183; // [rsp+8C2h] [rbp+7C2h] BYREF

  v3 = a3;
  v175 = a3;
  v4 = SubKey;
  v174 = this;
  v5 = 2147483646;
  v6 = L"Software";
  v7 = 256;
  do
  {
    if ( !v5 )
      break;
    if ( !*v6 )
      break;
    *v4++ = *v6++;
    --v5;
    --v7;
  }
  while ( v7 );
  v8 = v4 - 1;
  v9 = 256;
  v10 = SubKey;
  if ( v7 )
    v8 = v4;
  v11 = 0;
  *v8 = 0;
  while ( *v10 )
  {
    ++v10;
    if ( !--v9 )
      goto LABEL_18;
  }
  v12 = 2147483646;
  v13 = &v181[-v9];
  v14 = L"\\Microsoft\\CTF\\TIP";
  do
  {
    if ( !v12 )
      break;
    if ( !*v14 )
      break;
    *v13++ = *v14++;
    --v12;
    --v9;
  }
  while ( v9 );
  v15 = v13 - 1;
  if ( v9 )
    v15 = v13;
  *v15 = 0;
LABEL_18:
  hKey = 0;
  v16 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
  if ( !v16
    || (v173 = 0, v17 = 0, v16 == 5)
    && (cchName = 0, !RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 4u, 0x20019u, 0, &hKey, &cchName)) )
  {
    v17 = hKey;
    v173 = hKey;
  }
  v18 = 0;
  if ( v17 )
  {
    while ( 1 )
    {
      cchName = 256;
      v19 = RegEnumKeyExW(v17, v18, &Name, &cchName, 0, 0, 0, 0);
      v21 = 510;
      if ( v19 )
        v21 = 0;
      *(WCHAR *)((char *)&Name + v21) = 0;
      if ( v19 )
        break;
      cchName = v18 + 1;
      if ( Name == 123 )
      {
        v22 = &v177;
        for ( i = 0; ; ++i )
        {
          v20 = (const unsigned __int16 *)*(unsigned __int16 *)v22;
          if ( i >= 8 )
            break;
          if ( (unsigned __int16)((_WORD)v20 - 48) > 9u && (unsigned __int16)((_WORD)v20 - 65) > 5u )
          {
            LOWORD(v20) = (_WORD)v20 - 97;
            if ( (unsigned __int16)v20 > 5u )
              goto LABEL_59;
          }
          v22 += 2;
        }
        if ( (_WORD)v20 == 45 )
        {
          for ( j = 0; ; ++j )
          {
            v20 = (const unsigned __int16 *)*((unsigned __int16 *)v22 + 1);
            v22 += 2;
            if ( j >= 4 )
              break;
            if ( (unsigned __int16)((_WORD)v20 - 48) > 9u && (unsigned __int16)((_WORD)v20 - 65) > 5u )
            {
              LOWORD(v20) = (_WORD)v20 - 97;
              if ( (unsigned __int16)v20 > 5u )
                goto LABEL_59;
            }
          }
          if ( (_WORD)v20 == 45 )
          {
            for ( k = 0; ; ++k )
            {
              v20 = (const unsigned __int16 *)*((unsigned __int16 *)v22 + 1);
              v22 += 2;
              if ( k >= 4 )
                break;
              if ( (unsigned __int16)((_WORD)v20 - 48) > 9u && (unsigned __int16)((_WORD)v20 - 65) > 5u )
              {
                LOWORD(v20) = (_WORD)v20 - 97;
                if ( (unsigned __int16)v20 > 5u )
                  goto LABEL_59;
              }
            }
            if ( (_WORD)v20 == 45 )
            {
              for ( m = 0; ; ++m )
              {
                v22 += 2;
                if ( m >= 2 )
                  break;
                v20 = (const unsigned __int16 *)*(unsigned __int16 *)v22;
                if ( (unsigned __int16)((_WORD)v20 - 48) > 9u && (unsigned __int16)((_WORD)v20 - 65) > 5u )
                {
                  LOWORD(v20) = (_WORD)v20 - 97;
                  if ( (unsigned __int16)v20 > 5u )
                    goto LABEL_59;
                }
              }
              for ( n = 0; ; ++n )
              {
                v20 = (const unsigned __int16 *)*(unsigned __int16 *)v22;
                if ( n >= 2 )
                  break;
                if ( (unsigned __int16)((_WORD)v20 - 48) > 9u && (unsigned __int16)((_WORD)v20 - 65) > 5u )
                {
                  LOWORD(v20) = (_WORD)v20 - 97;
                  if ( (unsigned __int16)v20 > 5u )
                    goto LABEL_59;
                }
                v22 += 2;
              }
              if ( (_WORD)v20 == 45 )
              {
                for ( ii = 0; ; ++ii )
                {
                  v22 += 2;
                  if ( ii >= 2 )
                    break;
                  v20 = (const unsigned __int16 *)*(unsigned __int16 *)v22;
                  if ( (unsigned __int16)((_WORD)v20 - 48) > 9u && (unsigned __int16)((_WORD)v20 - 65) > 5u )
                  {
                    LOWORD(v20) = (_WORD)v20 - 97;
                    if ( (unsigned __int16)v20 > 5u )
                      goto LABEL_59;
                  }
                }
                for ( jj = 0; jj < 2; ++jj )
                {
                  v20 = (const unsigned __int16 *)*(unsigned __int16 *)v22;
                  if ( (unsigned __int16)((_WORD)v20 - 48) > 9u && (unsigned __int16)((_WORD)v20 - 65) > 5u )
                  {
                    LOWORD(v20) = (_WORD)v20 - 97;
                    if ( (unsigned __int16)v20 > 5u )
                      goto LABEL_59;
                  }
                  v22 += 2;
                }
                for ( kk = 0; kk < 2; ++kk )
                {
                  v20 = (const unsigned __int16 *)*(unsigned __int16 *)v22;
                  if ( (unsigned __int16)((_WORD)v20 - 48) > 9u && (unsigned __int16)((_WORD)v20 - 65) > 5u )
                  {
                    LOWORD(v20) = (_WORD)v20 - 97;
                    if ( (unsigned __int16)v20 > 5u )
                      goto LABEL_59;
                  }
                  v22 += 2;
                }
                for ( mm = 0; mm < 2; ++mm )
                {
                  v20 = (const unsigned __int16 *)*(unsigned __int16 *)v22;
                  if ( (unsigned __int16)((_WORD)v20 - 48) > 9u && (unsigned __int16)((_WORD)v20 - 65) > 5u )
                  {
                    LOWORD(v20) = (_WORD)v20 - 97;
                    if ( (unsigned __int16)v20 > 5u )
                      goto LABEL_59;
                  }
                  v22 += 2;
                }
                for ( nn = 0; nn < 2; ++nn )
                {
                  v20 = (const unsigned __int16 *)*(unsigned __int16 *)v22;
                  if ( (unsigned __int16)((_WORD)v20 - 48) > 9u && (unsigned __int16)((_WORD)v20 - 65) > 5u )
                  {
                    LOWORD(v20) = (_WORD)v20 - 97;
                    if ( (unsigned __int16)v20 > 5u )
                      goto LABEL_59;
                  }
                  v22 += 2;
                }
                for ( i1 = 0; i1 < 2; ++i1 )
                {
                  v20 = (const unsigned __int16 *)*(unsigned __int16 *)v22;
                  if ( (unsigned __int16)((_WORD)v20 - 48) > 9u && (unsigned __int16)((_WORD)v20 - 65) > 5u )
                  {
                    LOWORD(v20) = (_WORD)v20 - 97;
                    if ( (unsigned __int16)v20 > 5u )
                      break;
                  }
                  v22 += 2;
                }
              }
            }
          }
        }
      }
LABEL_59:
      IsTsf3OverrideEnabled = Tsf3OverrideUtil::IsTsf3OverrideEnabled((Tsf3OverrideUtil *)&Name, 0, v20);
      p_Name = &Name;
      v29 = 2147483646;
      v30 = v181;
      v31 = 256;
      do
      {
        if ( !v29 )
          break;
        if ( !*p_Name )
          break;
        *v30++ = *p_Name++;
        --v29;
        --v31;
      }
      while ( v31 );
      v32 = v30 - 1;
      v33 = 256;
      if ( v31 )
        v32 = v30;
      *v32 = 0;
      v34 = v181;
      while ( *v34 )
      {
        ++v34;
        if ( !--v33 )
          goto LABEL_76;
      }
      v35 = 2147483646;
      v36 = &v182 - v33;
      v37 = L"\\Category\\Category";
      do
      {
        if ( !v35 )
          break;
        if ( !*v37 )
          break;
        *v36++ = *v37++;
        --v35;
        --v33;
      }
      while ( v33 );
      v38 = v36 - 1;
      if ( v33 )
        v38 = v36;
      *v38 = 0;
LABEL_76:
      hKey = 0;
      v39 = v17;
      phkResult = 0;
      if ( v17 == HKEY_CURRENT_USER && !RegOpenCurrentUser(0x20019u, &phkResult) )
        v39 = phkResult;
      v40 = RegOpenKeyExW(v39, v181, 0, 0x20019u, &hKey);
      if ( !v40
        || (v172 = 0, v41 = 0, v40 == 5)
        && (dwDisposition = 0, !RegCreateKeyExW(v39, v181, 0, 0, 4u, 0x20019u, 0, &hKey, &dwDisposition)) )
      {
        v41 = hKey;
        v172 = hKey;
      }
      if ( phkResult )
        RegCloseKey(phkResult);
      v18 = cchName;
      v42 = 0;
      if ( v41 )
      {
        while ( 1 )
        {
          dwDisposition = 256;
          v43 = RegEnumKeyExW(v41, v42, &v178, &dwDisposition, 0, 0, 0, 0);
          v44 = 510;
          if ( v43 )
            v44 = 0;
          *(WCHAR *)((char *)&v178 + v44) = 0;
          if ( v43 )
            break;
          LODWORD(hKey) = ++v42;
          Buf1 = 0;
          if ( v178 != 123 )
            goto LABEL_119;
          v45 = &v179;
          v46 = 0;
          v47 = 0;
          while ( 1 )
          {
            v48 = *(unsigned __int16 *)v45;
            Buf1.Data1 = v46;
            if ( v47 >= 8 )
              break;
            if ( (unsigned __int16)(v48 - 48) <= 9u )
            {
              v49 = 16 * v46 - 48;
              goto LABEL_90;
            }
            if ( (unsigned __int16)(v48 - 65) > 5u )
            {
              if ( (unsigned __int16)(v48 - 97) > 5u )
                goto LABEL_119;
              v49 = 16 * v46 - 87;
LABEL_90:
              v46 = v48 + v49;
              ++v47;
              v45 += 2;
            }
            else
            {
              ++v47;
              v46 = v48 + 16 * v46 - 55;
              v45 += 2;
            }
          }
          if ( v48 != 45 )
            goto LABEL_119;
          v50 = 0;
          v51 = 0;
          while ( 1 )
          {
            v52 = *((unsigned __int16 *)v45 + 1);
            v45 += 2;
            if ( v51 >= 4 )
              break;
            if ( (unsigned __int16)(v52 - 48) <= 9u )
            {
              v53 = 16 * v50 - 48;
LABEL_98:
              v50 = v52 + v53;
              ++v51;
              continue;
            }
            if ( (unsigned __int16)(v52 - 65) > 5u )
            {
              if ( (unsigned __int16)(v52 - 97) > 5u )
                goto LABEL_119;
              v53 = 16 * v50 - 87;
              goto LABEL_98;
            }
            v50 = v52 + 16 * v50 - 55;
            ++v51;
          }
          if ( v52 != 45 )
            goto LABEL_119;
          Buf1.Data2 = v50;
          v54 = 0;
          v55 = 0;
          while ( 1 )
          {
            v45 += 2;
            if ( v55 >= 4 )
              break;
            if ( (unsigned __int16)(*(_WORD *)v45 - 48) <= 9u )
            {
              v56 = 16 * v54 - 48;
LABEL_106:
              v54 = *(unsigned __int16 *)v45 + v56;
              ++v55;
              continue;
            }
            if ( (unsigned __int16)(*(_WORD *)v45 - 65) > 5u )
            {
              if ( (unsigned __int16)(*(_WORD *)v45 - 97) > 5u )
                goto LABEL_119;
              v56 = 16 * v54 - 87;
              goto LABEL_106;
            }
            v54 = *(unsigned __int16 *)v45 + 16 * v54 - 55;
            ++v55;
          }
          if ( *(_WORD *)v45 != 45 )
            goto LABEL_119;
          Buf1.Data3 = v54;
          v57 = 0;
          v58 = 0;
          while ( 1 )
          {
            v45 += 2;
            if ( v58 >= 2 )
              break;
            v59 = *(unsigned __int16 *)v45;
            if ( (unsigned __int16)(v59 - 48) <= 9u )
            {
              v60 = 16 * v57 - 48;
LABEL_114:
              v57 = v59 + v60;
              ++v58;
              continue;
            }
            if ( (unsigned __int16)(v59 - 65) > 5u )
            {
              if ( (unsigned __int16)(v59 - 97) > 5u )
                goto LABEL_119;
              v60 = 16 * v57 - 87;
              goto LABEL_114;
            }
            v57 = v59 + 16 * v57 - 55;
            ++v58;
          }
          Buf1.Data4[0] = v57;
          v75 = 0;
          v76 = 0;
          while ( 1 )
          {
            v77 = *(unsigned __int16 *)v45;
            if ( v75 >= 2 )
              break;
            if ( (unsigned __int16)(v77 - 48) <= 9u )
            {
              v78 = 16 * v76 - 48;
LABEL_143:
              v76 = v77 + v78;
              ++v75;
              v45 += 2;
              continue;
            }
            if ( (unsigned __int16)(v77 - 65) > 5u )
            {
              if ( (unsigned __int16)(v77 - 97) > 5u )
                goto LABEL_119;
              v78 = 16 * v76 - 87;
              goto LABEL_143;
            }
            ++v75;
            v76 = v77 + 16 * v76 - 55;
            v45 += 2;
          }
          if ( v77 != 45 )
            goto LABEL_119;
          Buf1.Data4[1] = v76;
          v79 = 0;
          v80 = 0;
          while ( 1 )
          {
            v45 += 2;
            if ( v79 >= 2 )
              break;
            v81 = *(unsigned __int16 *)v45;
            if ( (unsigned __int16)(v81 - 48) <= 9u )
            {
              v82 = 16 * v80 - 48;
LABEL_151:
              v80 = v81 + v82;
              ++v79;
              continue;
            }
            if ( (unsigned __int16)(v81 - 65) > 5u )
            {
              if ( (unsigned __int16)(v81 - 97) > 5u )
                goto LABEL_119;
              v82 = 16 * v80 - 87;
              goto LABEL_151;
            }
            v80 = v81 + 16 * v80 - 55;
            ++v79;
          }
          Buf1.Data4[2] = v80;
          v83 = 0;
          v84 = 0;
          while ( v83 < 2 )
          {
            v85 = *(unsigned __int16 *)v45;
            if ( (unsigned __int16)(v85 - 48) <= 9u )
            {
              v86 = 16 * v84 - 48;
LABEL_158:
              v84 = v85 + v86;
              ++v83;
              v45 += 2;
              continue;
            }
            if ( (unsigned __int16)(v85 - 65) > 5u )
            {
              if ( (unsigned __int16)(v85 - 97) > 5u )
                goto LABEL_119;
              v86 = 16 * v84 - 87;
              goto LABEL_158;
            }
            ++v83;
            v84 = v85 + 16 * v84 - 55;
            v45 += 2;
          }
          Buf1.Data4[3] = v84;
          v87 = 0;
          v88 = 0;
          while ( v87 < 2 )
          {
            v89 = *(unsigned __int16 *)v45;
            if ( (unsigned __int16)(v89 - 48) <= 9u )
            {
              v90 = 16 * v88 - 48;
LABEL_165:
              v88 = v89 + v90;
              ++v87;
              v45 += 2;
              continue;
            }
            if ( (unsigned __int16)(v89 - 65) > 5u )
            {
              if ( (unsigned __int16)(v89 - 97) > 5u )
                goto LABEL_119;
              v90 = 16 * v88 - 87;
              goto LABEL_165;
            }
            ++v87;
            v88 = v89 + 16 * v88 - 55;
            v45 += 2;
          }
          Buf1.Data4[4] = v88;
          v91 = 0;
          v92 = 0;
          while ( v91 < 2 )
          {
            v93 = *(unsigned __int16 *)v45;
            if ( (unsigned __int16)(v93 - 48) <= 9u )
            {
              v94 = 16 * v92 - 48;
LABEL_172:
              v92 = v93 + v94;
              ++v91;
              v45 += 2;
              continue;
            }
            if ( (unsigned __int16)(v93 - 65) > 5u )
            {
              if ( (unsigned __int16)(v93 - 97) > 5u )
                goto LABEL_119;
              v94 = 16 * v92 - 87;
              goto LABEL_172;
            }
            ++v91;
            v92 = v93 + 16 * v92 - 55;
            v45 += 2;
          }
          Buf1.Data4[5] = v92;
          v95 = 0;
          v96 = 0;
          while ( v95 < 2 )
          {
            v97 = *(unsigned __int16 *)v45;
            if ( (unsigned __int16)(v97 - 48) <= 9u )
            {
              v98 = 16 * v96 - 48;
LABEL_182:
              v96 = v97 + v98;
              ++v95;
              v45 += 2;
              continue;
            }
            if ( (unsigned __int16)(v97 - 65) > 5u )
            {
              if ( (unsigned __int16)(v97 - 97) > 5u )
                goto LABEL_119;
              v98 = 16 * v96 - 87;
              goto LABEL_182;
            }
            ++v95;
            v96 = v97 + 16 * v96 - 55;
            v45 += 2;
          }
          Buf1.Data4[6] = v96;
          v99 = 0;
          v100 = 0;
          while ( 1 )
          {
            v101 = *(unsigned __int16 *)v45;
            if ( v99 >= 2 )
              break;
            if ( (unsigned __int16)(v101 - 48) <= 9u )
            {
              v102 = 16 * v100 - 48;
LABEL_189:
              v100 = v101 + v102;
              ++v99;
              v45 += 2;
              continue;
            }
            if ( (unsigned __int16)(v101 - 65) > 5u )
            {
              if ( (unsigned __int16)(v101 - 97) > 5u )
                goto LABEL_119;
              v102 = 16 * v100 - 87;
              goto LABEL_189;
            }
            ++v99;
            v100 = v101 + 16 * v100 - 55;
            v45 += 2;
          }
          if ( v101 == 125 )
            Buf1.Data4[7] = v100;
LABEL_119:
          v61 = *(_QWORD *)&Buf1.Data1 - *(_QWORD *)&v3->Data1;
          if ( *(_QWORD *)&Buf1.Data1 == *(_QWORD *)&v3->Data1 )
            v61 = *(_QWORD *)Buf1.Data4 - *(_QWORD *)v3->Data4;
          if ( !v61 )
          {
            phkResult = 0;
            v62 = v41;
            v171 = 0;
            if ( v41 == HKEY_CURRENT_USER && !RegOpenCurrentUser(0x20019u, &v171) )
              v62 = v171;
            v63 = RegOpenKeyExW(v62, &v178, 0, 0x20019u, &phkResult);
            if ( !v63
              || (v64 = 0, v63 == 5)
              && (lpdwDisposition = 0, !RegCreateKeyExW(v62, &v178, 0, 0, 4u, 0x20019u, 0, &phkResult, &lpdwDisposition)) )
            {
              v64 = phkResult;
            }
            if ( v171 )
              RegCloseKey(v171);
            if ( v64 )
            {
              v65 = IsTsf3OverrideEnabled;
              v66 = v174;
              while ( 1 )
              {
                dwDisposition = 256;
                v67 = RegEnumKeyExW(v64, v11, &v182, &dwDisposition, 0, 0, 0, 0);
                v68 = 510;
                if ( v67 )
                  v68 = 0;
                *(WCHAR *)((char *)&v182 + v68) = 0;
                if ( v67 )
                {
                  RegCloseKey(v64);
                  v42 = (unsigned int)hKey;
                  v41 = v172;
                  v3 = v175;
                  break;
                }
                ++v11;
                v69 = 0;
                Buf1 = 0;
                if ( v182 != 123 )
                  goto LABEL_289;
                v70 = 0;
                v71 = &v183;
                v72 = 0;
                while ( 1 )
                {
                  v73 = *(unsigned __int16 *)v71;
                  Buf1.Data1 = v70;
                  if ( v72 >= 8 )
                    break;
                  if ( (unsigned __int16)(v73 - 48) <= 9u )
                  {
                    v74 = 16 * v70 - 48;
                    goto LABEL_137;
                  }
                  if ( (unsigned __int16)(v73 - 65) > 5u )
                  {
                    if ( (unsigned __int16)(v73 - 97) > 5u )
                      goto LABEL_288;
                    v74 = 16 * v70 - 87;
LABEL_137:
                    v70 = v73 + v74;
                    ++v72;
                    v71 += 2;
                  }
                  else
                  {
                    ++v72;
                    v70 = v73 + 16 * v70 - 55;
                    v71 += 2;
                  }
                }
                if ( v73 != 45 )
                  goto LABEL_288;
                v109 = (unsigned __int16 *)(v71 + 2);
                v110 = 0;
                v111 = 0;
                while ( 1 )
                {
                  v112 = *v109;
                  if ( v111 >= 4 )
                    break;
                  if ( (unsigned __int16)(v112 - 48) <= 9u )
                  {
                    v113 = 16 * v110 - 48;
LABEL_248:
                    v110 = v112 + v113;
                    ++v111;
                    ++v109;
                    continue;
                  }
                  if ( (unsigned __int16)(v112 - 65) > 5u )
                  {
                    if ( (unsigned __int16)(v112 - 97) > 5u )
                      goto LABEL_288;
                    v113 = 16 * v110 - 87;
                    goto LABEL_248;
                  }
                  ++v111;
                  v110 = v112 + 16 * v110 - 55;
                  ++v109;
                }
                if ( v112 != 45 )
                  goto LABEL_288;
                v114 = v109 + 1;
                Buf1.Data2 = v110;
                v115 = 0;
                v116 = 0;
                while ( 1 )
                {
                  v117 = *v114;
                  if ( v116 >= 4 )
                    break;
                  if ( (unsigned __int16)(v117 - 48) <= 9u )
                  {
                    v118 = 16 * v115 - 48;
LABEL_262:
                    v115 = v117 + v118;
                    ++v116;
                    ++v114;
                    continue;
                  }
                  if ( (unsigned __int16)(v117 - 65) > 5u )
                  {
                    if ( (unsigned __int16)(v117 - 97) > 5u )
                      goto LABEL_288;
                    v118 = 16 * v115 - 87;
                    goto LABEL_262;
                  }
                  ++v116;
                  v115 = v117 + 16 * v115 - 55;
                  ++v114;
                }
                if ( v117 != 45 )
                  goto LABEL_288;
                v119 = v114 + 1;
                Buf1.Data3 = v115;
                v120 = 0;
                v121 = 0;
                while ( v121 < 2 )
                {
                  v122 = *v119;
                  if ( (unsigned __int16)(v122 - 48) <= 9u )
                  {
                    v123 = 16 * v120 - 48;
LABEL_283:
                    v120 = v122 + v123;
                    ++v121;
                    ++v119;
                    continue;
                  }
                  if ( (unsigned __int16)(v122 - 65) > 5u )
                  {
                    if ( (unsigned __int16)(v122 - 97) > 5u )
                      goto LABEL_288;
                    v123 = 16 * v120 - 87;
                    goto LABEL_283;
                  }
                  ++v121;
                  v120 = v122 + 16 * v120 - 55;
                  ++v119;
                }
                Buf1.Data4[0] = v120;
                v135 = 0;
                v136 = 0;
                while ( 1 )
                {
                  v137 = *v119;
                  if ( v136 >= 2 )
                    break;
                  if ( (unsigned __int16)(v137 - 48) <= 9u )
                  {
                    v138 = 16 * v135 - 48;
LABEL_311:
                    v135 = v137 + v138;
                    ++v136;
                    ++v119;
                    continue;
                  }
                  if ( (unsigned __int16)(v137 - 65) > 5u )
                  {
                    if ( (unsigned __int16)(v137 - 97) > 5u )
                      goto LABEL_288;
                    v138 = 16 * v135 - 87;
                    goto LABEL_311;
                  }
                  ++v136;
                  v135 = v137 + 16 * v135 - 55;
                  ++v119;
                }
                if ( v137 != 45 )
                  goto LABEL_288;
                Buf1.Data4[1] = v135;
                v139 = v119 + 1;
                v140 = 0;
                v141 = 0;
                while ( v141 < 2 )
                {
                  v142 = *v139;
                  if ( (unsigned __int16)(v142 - 48) <= 9u )
                  {
                    v143 = 16 * v140 - 48;
LABEL_319:
                    v140 = v142 + v143;
                    ++v141;
                    ++v139;
                    continue;
                  }
                  if ( (unsigned __int16)(v142 - 65) > 5u )
                  {
                    if ( (unsigned __int16)(v142 - 97) > 5u )
                      goto LABEL_288;
                    v143 = 16 * v140 - 87;
                    goto LABEL_319;
                  }
                  ++v141;
                  v140 = v142 + 16 * v140 - 55;
                  ++v139;
                }
                Buf1.Data4[2] = v140;
                v144 = 0;
                v145 = 0;
                while ( v145 < 2 )
                {
                  v146 = *v139;
                  if ( (unsigned __int16)(v146 - 48) <= 9u )
                  {
                    v147 = 16 * v144 - 48;
LABEL_326:
                    v144 = v146 + v147;
                    ++v145;
                    ++v139;
                    continue;
                  }
                  if ( (unsigned __int16)(v146 - 65) > 5u )
                  {
                    if ( (unsigned __int16)(v146 - 97) > 5u )
                      goto LABEL_288;
                    v147 = 16 * v144 - 87;
                    goto LABEL_326;
                  }
                  ++v145;
                  v144 = v146 + 16 * v144 - 55;
                  ++v139;
                }
                Buf1.Data4[3] = v144;
                v148 = 0;
                v149 = 0;
                while ( v149 < 2 )
                {
                  v150 = *v139;
                  if ( (unsigned __int16)(v150 - 48) <= 9u )
                  {
                    v151 = 16 * v148 - 48;
LABEL_336:
                    v148 = v150 + v151;
                    ++v149;
                    ++v139;
                    continue;
                  }
                  if ( (unsigned __int16)(v150 - 65) > 5u )
                  {
                    if ( (unsigned __int16)(v150 - 97) > 5u )
                      goto LABEL_288;
                    v151 = 16 * v148 - 87;
                    goto LABEL_336;
                  }
                  ++v149;
                  v148 = v150 + 16 * v148 - 55;
                  ++v139;
                }
                Buf1.Data4[4] = v148;
                v152 = 0;
                v153 = 0;
                while ( v153 < 2 )
                {
                  v154 = *v139;
                  if ( (unsigned __int16)(v154 - 48) <= 9u )
                  {
                    v155 = 16 * v152 - 48;
LABEL_343:
                    v152 = v154 + v155;
                    ++v153;
                    ++v139;
                    continue;
                  }
                  if ( (unsigned __int16)(v154 - 65) > 5u )
                  {
                    if ( (unsigned __int16)(v154 - 97) > 5u )
                      goto LABEL_288;
                    v155 = 16 * v152 - 87;
                    goto LABEL_343;
                  }
                  ++v153;
                  v152 = v154 + 16 * v152 - 55;
                  ++v139;
                }
                Buf1.Data4[5] = v152;
                v156 = 0;
                v157 = 0;
                while ( v157 < 2 )
                {
                  v158 = *v139;
                  if ( (unsigned __int16)(v158 - 48) <= 9u )
                  {
                    v159 = 16 * v156 - 48;
LABEL_350:
                    v156 = v158 + v159;
                    ++v157;
                    ++v139;
                    continue;
                  }
                  if ( (unsigned __int16)(v158 - 65) > 5u )
                  {
                    if ( (unsigned __int16)(v158 - 97) > 5u )
                      goto LABEL_288;
                    v159 = 16 * v156 - 87;
                    goto LABEL_350;
                  }
                  ++v157;
                  v156 = v158 + 16 * v156 - 55;
                  ++v139;
                }
                Buf1.Data4[6] = v156;
                v160 = 0;
                v161 = 0;
                while ( 1 )
                {
                  v162 = *v139;
                  if ( v161 >= 2 )
                    break;
                  if ( (unsigned __int16)(v162 - 48) <= 9u )
                  {
                    v163 = 16 * v160 - 48;
LABEL_357:
                    v160 = v162 + v163;
                    ++v161;
                    ++v139;
                    continue;
                  }
                  if ( (unsigned __int16)(v162 - 65) > 5u )
                  {
                    if ( (unsigned __int16)(v162 - 97) > 5u )
                      goto LABEL_288;
                    v163 = 16 * v160 - 87;
                    goto LABEL_357;
                  }
                  ++v161;
                  v160 = v162 + 16 * v160 - 55;
                  ++v139;
                }
                if ( v162 == 125 )
                  Buf1.Data4[7] = v160;
LABEL_288:
                v69 = Buf1;
LABEL_289:
                if ( v65 && !memcmp_0(&Buf1, &GUID_TFCAT_TIPCAP_DUALMODE, 0x10u) )
                  v69 = GUID_TFCAT_TIPCAP_TSF3;
                v124 = *((_DWORD *)v66 + 4);
                if ( v124 >= 0 )
                {
                  v125 = v124 + 1;
                  if ( !__OFSUB__(v124, v124 + 1) )
                  {
                    if ( *((_DWORD *)v66 + 6) >= v125 )
                      goto LABEL_300;
                    v126 = v124 / 2 + v124;
                    if ( v125 > v126 )
                      v126 = v124 + 1;
                    v127 = (unsigned int)v126 * (unsigned __int64)*((unsigned int *)v66 + 5);
                    if ( v127 <= 0xFFFFFFFF )
                    {
                      v128 = (void *)*((_QWORD *)v66 + 1);
                      v129 = v128 ? LocalReAlloc(v128, (unsigned int)v127, 0x42u) : LocalAlloc(0, (unsigned int)v127);
                      if ( v129 )
                      {
                        *((_QWORD *)v66 + 1) = v129;
                        *((_DWORD *)v66 + 6) = v126;
LABEL_300:
                        v130 = *((_DWORD *)v66 + 4);
                        if ( v124 < v130 )
                          memmove_0(
                            (void *)(*((_QWORD *)v66 + 1) + v125 * *((_DWORD *)v66 + 5)),
                            (const void *)(*((_QWORD *)v66 + 1) + *((_DWORD *)v66 + 5) * v124),
                            *((_DWORD *)v66 + 5) * (v130 - v124));
                        v131 = *((_DWORD *)v66 + 4);
                        v132 = v131 + 1;
                        v133 = *((_DWORD *)v66 + 5) * v131;
                        *((_DWORD *)v66 + 4) = v132;
                        v134 = (GUID *)(*((_QWORD *)v66 + 1) + v133);
                        if ( v134 )
                          *v134 = v69;
                      }
                    }
                  }
                }
              }
            }
            v11 = 0;
          }
        }
        RegCloseKey(v41);
        v18 = cchName;
        v17 = v173;
      }
    }
    RegCloseKey(v17);
  }
}

```

## disassembly

```asm
0x180008fb0  push    rbp
0x180008fb2  push    rbx
0x180008fb3  push    rsi
0x180008fb4  push    rdi
0x180008fb5  push    r14
0x180008fb7  lea     rbp, [rsp-9E0h]
0x180008fbf  sub     rsp, 0AE0h
0x180008fc6  mov     rax, cs:__security_cookie
0x180008fcd  xor     rax, rsp
0x180008fd0  mov     [rbp+0A00h+var_40], rax
0x180008fd7  mov     rdi, r8
0x180008fda  mov     [rbp+0A00h+var_A50], r8
0x180008fde  lea     r8, [rbp+0A00h+SubKey]
0x180008fe5  mov     [rbp+0A00h+var_A58], rcx
0x180008fe9  mov     eax, 7FFFFFFEh
0x180008fee  lea     rdx, aSoftware; "Software"
0x180008ff5  mov     r9d, 100h
0x180008ffb  nop     dword ptr [rax+rax+00h]
0x180009000  test    rax, rax
0x180009003  jz      short loc_180009022
0x180009005  movzx   ecx, word ptr [rdx]
0x180009008  test    cx, cx
0x18000900b  jz      short loc_180009022
0x18000900d  mov     [r8], cx
0x180009011  add     rdx, 2
0x180009015  add     r8, 2
0x180009019  dec     rax
0x18000901c  sub     r9, 1
0x180009020  jnz     short loc_180009000
0x180009022  test    r9, r9
0x180009025  lea     rcx, [r8-2]
0x180009029  mov     edx, 100h
0x18000902e  lea     rax, [rbp+0A00h+SubKey]
0x180009035  cmovnz  rcx, r8
0x180009039  xor     r14d, r14d
0x18000903c  mov     [rcx], r14w
0x180009040  cmp     [rax], r14w
0x180009044  jz      short loc_180009052
0x180009046  add     rax, 2
0x18000904a  sub     rdx, 1
0x18000904e  jnz     short loc_180009040
0x180009050  jmp     short loc_1800090A3
0x180009052  lea     rax, [rdx+rdx]
0x180009056  mov     ecx, 7FFFFFFEh
0x18000905b  lea     r8, [rbp+0A00h+var_440]
0x180009062  sub     r8, rax
0x180009065  lea     r9, ?c_szSoftwareCtfTip@@3QBGB; "\\Microsoft\\CTF\\TIP"
0x18000906c  test    rdx, rdx
0x18000906f  jz      short loc_180009094
0x180009071  test    rcx, rcx
0x180009074  jz      short loc_180009094
0x180009076  movzx   eax, word ptr [r9]
0x18000907a  test    ax, ax
0x18000907d  jz      short loc_180009094
0x18000907f  mov     [r8], ax
0x180009083  add     r9, 2
0x180009087  add     r8, 2
0x18000908b  dec     rcx
0x18000908e  sub     rdx, 1
0x180009092  jnz     short loc_180009071
0x180009094  test    rdx, rdx
0x180009097  lea     rcx, [r8-2]
0x18000909b  cmovnz  rcx, r8
0x18000909f  mov     [rcx], r14w
0x1800090a3  lea     rax, [rsp+0B00h+hKey]
0x1800090a8  mov     [rsp+0B00h+hKey], r14
0x1800090ad  mov     r9d, 20019h; samDesired
0x1800090b3  mov     [rsp+0B00h+phkResult], rax; phkResult
0x1800090b8  xor     r8d, r8d; ulOptions
0x1800090bb  lea     rdx, [rbp+0A00h+SubKey]; lpSubKey
0x1800090c2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800090c9  call    cs:__imp_RegOpenKeyExW
0x1800090cf  test    eax, eax
0x1800090d1  jnz     loc_18000A2FF
0x1800090d7  mov     rsi, [rsp+0B00h+hKey]
0x1800090dc  mov     [rbp+0A00h+var_A60], rsi
0x1800090e0  mov     ebx, r14d
0x1800090e3  test    rsi, rsi
0x1800090e6  jz      loc_18000A13C
0x1800090ec  mov     [rsp+0B00h+arg_8], r12
0x1800090f4  mov     [rsp+0B00h+arg_10], r13
0x1800090fc  mov     [rsp+0B00h+arg_18], r15
0x180009104  movaps  [rsp+0B00h+var_30], xmm6
0x18000910c  mov     [rsp+0B00h+lpftLastWriteTime], r14; lpftLastWriteTime
0x180009111  lea     r9, [rsp+0B00h+cchName]; lpcchName
0x180009116  mov     [rsp+0B00h+lpcchClass], r14; lpcchClass
0x18000911b  lea     r8, [rbp+0A00h+Name]; lpName
0x18000911f  mov     [rsp+0B00h+lpClass], r14; lpClass
0x180009124  mov     edx, ebx; dwIndex
0x180009126  mov     rcx, rsi; hKey
0x180009129  mov     [rsp+0B00h+phkResult], r14; lpReserved
0x18000912e  mov     [rsp+0B00h+cchName], 100h
0x180009136  call    cs:__imp_RegEnumKeyExW
0x18000913c  test    eax, eax
0x18000913e  mov     edx, 1FEh
0x180009143  cmovnz  rdx, r14
0x180009147  mov     [rbp+rdx+0A00h+Name], r14w
0x18000914d  jnz     loc_18000A113
0x180009153  inc     ebx
0x180009155  cmp     [rbp+0A00h+Name], 7Bh ; '{'
0x18000915a  mov     [rsp+0B00h+cchName], ebx
0x18000915e  jnz     loc_18000928E
0x180009164  lea     rcx, [rbp+0A00h+var_A3E]
0x180009168  mov     edx, r14d
0x18000916b  nop     dword ptr [rax+rax+00h]
0x180009170  movzx   r8d, word ptr [rcx]
0x180009174  cmp     edx, 8
0x180009177  jge     short loc_1800091A6
0x180009179  lea     eax, [r8-30h]
0x18000917d  cmp     ax, 9
0x180009181  ja      short loc_18000918B
0x180009183  inc     edx
0x180009185  add     rcx, 2
0x180009189  jmp     short loc_180009170
0x18000918b  lea     eax, [r8-41h]
0x18000918f  cmp     ax, 5
0x180009193  jbe     short loc_180009183
0x180009195  sub     r8w, 61h ; 'a'
0x18000919a  cmp     r8w, 5
0x18000919f  jbe     short loc_180009183
0x1800091a1  jmp     loc_18000928E
0x1800091a6  cmp     r8w, 2Dh ; '-'
0x1800091ab  jnz     loc_18000928E
0x1800091b1  mov     edx, r14d
0x1800091b4  movzx   r8d, word ptr [rcx+2]
0x1800091b9  add     rcx, 2
0x1800091bd  cmp     edx, 4
0x1800091c0  jge     short loc_1800091EB
0x1800091c2  lea     eax, [r8-30h]
0x1800091c6  cmp     ax, 9
0x1800091ca  ja      short loc_1800091D0
0x1800091cc  inc     edx
0x1800091ce  jmp     short loc_1800091B4
0x1800091d0  lea     eax, [r8-41h]
0x1800091d4  cmp     ax, 5
0x1800091d8  jbe     short loc_1800091CC
0x1800091da  sub     r8w, 61h ; 'a'
0x1800091df  cmp     r8w, 5
0x1800091e4  jbe     short loc_1800091CC
0x1800091e6  jmp     loc_18000928E
0x1800091eb  cmp     r8w, 2Dh ; '-'
0x1800091f0  jnz     loc_18000928E
0x1800091f6  mov     edx, r14d
0x1800091f9  movzx   r8d, word ptr [rcx+2]
0x1800091fe  add     rcx, 2
0x180009202  cmp     edx, 4
0x180009205  jge     short loc_18000922D
0x180009207  lea     eax, [r8-30h]
0x18000920b  cmp     ax, 9
0x18000920f  ja      short loc_180009215
0x180009211  inc     edx
0x180009213  jmp     short loc_1800091F9
0x180009215  lea     eax, [r8-41h]
0x180009219  cmp     ax, 5
0x18000921d  jbe     short loc_180009211
0x18000921f  sub     r8w, 61h ; 'a'
0x180009224  cmp     r8w, 5
0x180009229  jbe     short loc_180009211
0x18000922b  jmp     short loc_18000928E
0x18000922d  cmp     r8w, 2Dh ; '-'
0x180009232  jnz     short loc_18000928E
0x180009234  mov     edx, r14d
0x180009237  add     rcx, 2
0x18000923b  cmp     edx, 2
0x18000923e  jge     loc_18000995A
0x180009244  movzx   r8d, word ptr [rcx]
0x180009248  lea     eax, [r8-30h]
0x18000924c  cmp     ax, 9
0x180009250  ja      short loc_180009256
0x180009252  inc     edx
0x180009254  jmp     short loc_180009237
0x180009256  lea     eax, [r8-41h]
0x18000925a  cmp     ax, 5
0x18000925e  jbe     short loc_180009252
0x180009260  sub     r8w, 61h ; 'a'
0x180009265  cmp     r8w, 5
0x18000926a  jbe     short loc_180009252
0x18000926c  jmp     short loc_18000928E
0x18000926e  mov     edx, r14d
0x180009271  movzx   r8d, word ptr [rcx]; unsigned __int16 *
0x180009275  lea     eax, [r8-30h]
0x180009279  cmp     ax, 9
0x18000927d  ja      loc_180009886
0x180009283  inc     edx
0x180009285  add     rcx, 2
0x180009289  cmp     edx, 2
0x18000928c  jl      short loc_180009271
0x18000928e  xor     edx, edx; unsigned __int16 *
0x180009290  lea     rcx, [rbp+0A00h+Name]; this
0x180009294  call    ?IsTsf3OverrideEnabled@Tsf3OverrideUtil@@YA_NPEBG0@Z; Tsf3OverrideUtil::IsTsf3OverrideEnabled(ushort const *,ushort const *)
0x180009299  mov     [rsp+0B00h+var_AA0], al
0x18000929d  lea     r8, [rbp+0A00h+Name]
0x1800092a1  mov     edx, 7FFFFFFEh
0x1800092a6  lea     r9, [rbp+0A00h+var_440]
0x1800092ad  mov     r10d, 100h
0x1800092b3  test    rdx, rdx
0x1800092b6  jz      short loc_1800092D6
0x1800092b8  movzx   ecx, word ptr [r8]
0x1800092bc  test    cx, cx
0x1800092bf  jz      short loc_1800092D6
0x1800092c1  mov     [r9], cx
0x1800092c5  add     r8, 2
0x1800092c9  add     r9, 2
0x1800092cd  dec     rdx
0x1800092d0  sub     r10, 1
0x1800092d4  jnz     short loc_1800092B3
0x1800092d6  test    r10, r10
0x1800092d9  lea     rcx, [r9-2]
0x1800092dd  mov     eax, 100h
0x1800092e2  cmovnz  rcx, r9
0x1800092e6  mov     [rcx], r14w
0x1800092ea  lea     rcx, [rbp+0A00h+var_440]
0x1800092f1  cmp     word ptr [rcx], 0
0x1800092f5  jz      short loc_180009303
0x1800092f7  add     rcx, 2
0x1800092fb  sub     rax, 1
0x1800092ff  jnz     short loc_1800092F1
0x180009301  jmp     short loc_180009354
0x180009303  lea     rcx, [rax+rax]
0x180009307  mov     edx, 7FFFFFFEh
0x18000930c  lea     r9, [rbp+0A00h+var_240]
0x180009313  sub     r9, rcx
0x180009316  lea     r8, ?c_szCategory@@3QBGB; "\\Category\\Category"
0x18000931d  test    rax, rax
0x180009320  jz      short loc_180009345
0x180009322  test    rdx, rdx
0x180009325  jz      short loc_180009345
0x180009327  movzx   ecx, word ptr [r8]
0x18000932b  test    cx, cx
0x18000932e  jz      short loc_180009345
0x180009330  mov     [r9], cx
0x180009334  add     r8, 2
0x180009338  add     r9, 2
0x18000933c  dec     rdx
0x18000933f  sub     rax, 1
0x180009343  jnz     short loc_180009322
0x180009345  test    rax, rax
0x180009348  lea     rcx, [r9-2]
0x18000934c  cmovnz  rcx, r9
0x180009350  mov     [rcx], r14w
0x180009354  mov     [rsp+0B00h+hKey], r14
0x180009359  mov     rbx, rsi
0x18000935c  mov     [rbp+0A00h+var_A80], r14
0x180009360  cmp     rsi, 0FFFFFFFF80000001h
0x180009367  jz      loc_180009F96
0x18000936d  lea     rax, [rsp+0B00h+hKey]
0x180009372  mov     r9d, 20019h; samDesired
0x180009378  xor     r8d, r8d; ulOptions
0x18000937b  mov     [rsp+0B00h+phkResult], rax; phkResult
0x180009380  lea     rdx, [rbp+0A00h+var_440]; lpSubKey
0x180009387  mov     rcx, rbx; hKey
0x18000938a  call    cs:__imp_RegOpenKeyExW
0x180009390  test    eax, eax
0x180009392  jnz     loc_180009CED
0x180009398  mov     r13, [rsp+0B00h+hKey]
0x18000939d  mov     [rbp+0A00h+var_A68], r13
0x1800093a1  mov     rcx, [rbp+0A00h+var_A80]; hKey
0x1800093a5  test    rcx, rcx
0x1800093a8  jz      short loc_1800093B0
0x1800093aa  call    cs:__imp_RegCloseKey
0x1800093b0  mov     ebx, [rsp+0B00h+cchName]
0x1800093b4  mov     r12d, r14d
0x1800093b7  test    r13, r13
0x1800093ba  jz      loc_18000910C
0x1800093c0  mov     [rsp+0B00h+lpftLastWriteTime], r14; lpftLastWriteTime
0x1800093c5  lea     r9, [rsp+0B00h+dwDisposition]; lpcchName
0x1800093ca  mov     [rsp+0B00h+lpcchClass], r14; lpcchClass
0x1800093cf  lea     r8, [rbp+0A00h+var_840]; lpName
0x1800093d6  mov     [rsp+0B00h+lpClass], r14; lpClass
0x1800093db  mov     edx, r12d; dwIndex
0x1800093de  mov     rcx, r13; hKey
0x1800093e1  mov     [rsp+0B00h+phkResult], r14; lpReserved
0x1800093e6  mov     [rsp+0B00h+dwDisposition], 100h
0x1800093ee  call    cs:__imp_RegEnumKeyExW
0x1800093f4  test    eax, eax
0x1800093f6  mov     edx, 1FEh
0x1800093fb  cmovnz  rdx, r14
0x1800093ff  mov     [rbp+rdx+0A00h+var_840], r14w
0x180009408  jnz     loc_1800096D3
0x18000940e  inc     r12d
0x180009411  xorps   xmm0, xmm0
0x180009414  cmp     [rbp+0A00h+var_840], 7Bh ; '{'
0x18000941c  mov     dword ptr [rsp+0B00h+hKey], r12d
0x180009421  movups  [rsp+0B00h+Buf1], xmm0
0x180009426  jnz     loc_18000959A
0x18000942c  lea     rcx, [rbp+0A00h+var_83E]
0x180009433  mov     edx, r14d
0x180009436  mov     r9d, r14d
0x180009439  movzx   r8d, word ptr [rcx]
0x18000943d  mov     dword ptr [rsp+0B00h+Buf1], edx
0x180009441  cmp     r9d, 8
0x180009445  jge     short loc_180009483
0x180009447  lea     eax, [r8-30h]
0x18000944b  cmp     ax, 9
0x18000944f  ja      short loc_180009463
0x180009451  shl     edx, 4
0x180009454  add     edx, 0FFFFFFD0h
0x180009457  add     edx, r8d
0x18000945a  inc     r9d
0x18000945d  add     rcx, 2
  ... truncated ...
```
