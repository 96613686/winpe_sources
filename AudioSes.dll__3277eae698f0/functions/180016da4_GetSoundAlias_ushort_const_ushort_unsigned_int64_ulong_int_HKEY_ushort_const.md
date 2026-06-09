# _GetSoundAlias(ushort const *,ushort *,unsigned __int64,ulong &,int,HKEY__ *,ushort const *)

- ea: `0x180016da4`
- end: `0x180017734`
- name: `?_GetSoundAlias@@YAHPEBGPEAG_KAEAKHPEAUHKEY__@@0@Z`
- size: `2448`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int *, int, HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180016d90`

## callees

- `0x1800165ac`
- `0x180016da4`
- `0x180017740`
- `0x18005d7cc`
- `0x180087e80`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180017683`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180017683`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180017670`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180017670`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800172e1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017508`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800175fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800172e1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017508`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800175fe`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180017292`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800174bb`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180017292`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800174bb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180016e5a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800172d4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180017329`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800174fb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800175ea`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180016e5a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800172d4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180017329`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800174fb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800175ea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800175b4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800175b4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180016e0a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180017554`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180016e0a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180017554`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180017474`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180017474`

## pseudocode

```c
__int64 __fastcall _GetSoundAlias(unsigned __int16 *a1, unsigned __int16 *a2, __int64 a3, unsigned int *a4)
{
  unsigned int v5; // edi
  unsigned __int16 *pvData; // r14
  unsigned int Registry; // r15d
  unsigned __int16 *v9; // r12
  WCHAR *v10; // rbx
  __int64 v11; // rcx
  unsigned __int16 *v12; // rax
  __int64 v13; // rdi
  __int64 v14; // r8
  WCHAR *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r9
  WCHAR *v19; // rcx
  WCHAR *v20; // r10
  unsigned __int64 v21; // r8
  unsigned __int64 v22; // r9
  __int64 v23; // rbx
  unsigned __int16 near **v24; // rcx
  WCHAR *v25; // r11
  __int64 v26; // rax
  unsigned __int64 v27; // r14
  __int64 v28; // rdx
  WCHAR *v29; // rcx
  __int64 v30; // r9
  unsigned int v31; // ebx
  unsigned __int64 v32; // r9
  __int64 v33; // rax
  unsigned __int16 near **v34; // rcx
  unsigned __int64 v35; // r14
  __int64 v36; // r10
  WCHAR *v37; // rbx
  __int64 v38; // rdx
  WCHAR *v39; // rcx
  __int64 v40; // r9
  unsigned int v41; // r10d
  unsigned __int64 v42; // r9
  unsigned __int16 near **v43; // r12
  __int64 v44; // r10
  unsigned __int16 near **v45; // rcx
  __int64 v46; // rax
  unsigned __int64 v47; // r14
  WCHAR *v48; // r11
  __int64 v49; // rdx
  WCHAR *v50; // rcx
  __int64 v51; // r9
  unsigned int v52; // r10d
  unsigned __int64 v53; // r9
  HKEY v54; // rcx
  __int64 v55; // rax
  unsigned __int64 v56; // r14
  __int64 v57; // r10
  __int64 v58; // rdx
  WCHAR *v59; // rcx
  __int64 v60; // r11
  __int64 v61; // r9
  unsigned int v62; // r10d
  __int64 v63; // rax
  unsigned __int16 near **v64; // rcx
  unsigned __int64 v65; // r14
  __int64 v66; // rdx
  WCHAR *v67; // rcx
  __int64 v68; // r9
  unsigned int v69; // r11d
  unsigned __int64 v70; // r8
  __int64 v71; // rax
  unsigned __int16 near **v72; // rcx
  WCHAR *v73; // rcx
  HKEY v74; // rcx
  LSTATUS ValueW; // ebx
  __int64 v76; // rdx
  WCHAR *v77; // rax
  __int64 v78; // r8
  WCHAR *v79; // rax
  __int64 v80; // rcx
  __int64 v81; // rdx
  WCHAR *v82; // rcx
  __int64 v83; // rdx
  WCHAR *v84; // rax
  __int64 v85; // r8
  WCHAR *v86; // rax
  unsigned __int16 near **v87; // rcx
  __int64 v88; // rsi
  WCHAR *v89; // rcx
  LSTATUS v91; // ebx
  HMODULE ModuleHandleW; // rax
  unsigned __int16 *v93; // rdx
  unsigned __int16 *v94; // r8
  bool v95; // zf
  unsigned __int16 *pdwType; // [rsp+20h] [rbp-E0h]
  HKEY pcbData; // [rsp+30h] [rbp-D0h]
  PVOID v98; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v99; // [rsp+48h] [rbp-B8h] BYREF
  int v100; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hkey; // [rsp+68h] [rbp-98h] BYREF
  __int64 v104; // [rsp+70h] [rbp-90h]
  WCHAR SubKey[304]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Filename[304]; // [rsp+2E0h] [rbp+1E0h] BYREF

  v104 = a3;
  v98 = a2;
  phkResult = 0;
  v5 = a3;
  pvData = a2;
  if ( a1 && a2 )
  {
    Registry = 0;
    v9 = (unsigned __int16 *)&szSystemDefaultSound;
    v99 = 256;
    if ( lstrcmpW(a1, gszDefaultBeepOldAlias) )
      v9 = a1;
    hKey = (HKEY)v9;
    v10 = gszSchemesRootKey;
    if ( !RegGetValueW(HKEY_CURRENT_USER, gszSchemesRootKey, 0, 2u, 0, SubKey, &v99)
      && !lstrcmpiW(SubKey, gszNoSoundsSchemeName) )
    {
      *a4 |= 2u;
    }
    v11 = 40;
    v12 = v9;
    do
    {
      if ( !*v12 )
        break;
      ++v12;
      --v11;
    }
    while ( v11 );
    if ( !v11 )
      return Registry;
    if ( *(char *)a4 < 0 )
    {
      SubKey[0] = 0;
      ModuleHandleW = GetModuleHandleW(0);
      if ( GetModuleFileNameW(ModuleHandleW, Filename, 0x12Eu) )
      {
        lsplitpath(Filename, v93, v94, SubKey, pdwType);
        if ( SubKey[0] )
        {
          Registry = sndQueryRegistry((const unsigned __int16 *)v11, SubKey, v9, pvData, v5, a4, pcbData);
          if ( Registry )
            return Registry;
        }
      }
    }
    if ( (*a4 & 0x400000) != 0 )
    {
      Registry = sndQueryRegistry((const unsigned __int16 *)v11, aszExplorer, v9, pvData, v5, a4, pcbData);
      if ( Registry )
        return Registry;
    }
    v13 = 2147483646;
    v100 = 0;
    v14 = 2147483646;
    v15 = SubKey;
    Registry = 0;
    v16 = 302;
    v17 = 0;
    do
    {
      if ( !v14 )
        break;
      if ( !*v10 )
        break;
      *v15++ = *v10++;
      --v14;
      ++v17;
      --v16;
    }
    while ( v16 );
    v18 = v17 - 1;
    if ( v16 )
      v18 = v17;
    v19 = v15 - 1;
    if ( v16 )
      v19 = v15;
    *v19 = 0;
    if ( !v16 )
    {
LABEL_107:
      if ( !Registry )
      {
        LODWORD(v98) = v104;
        hKey = 0;
        StringCchPrintfW(SubKey, 0x104u, c_szPathFormat, &PSZ_SOUNDS_REGKEY, v9);
        if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey) )
        {
          Registry = RegGetValueW(hKey, 0, PSZ_SOUNDS_SOUND, 2u, 0, pvData, (LPDWORD)&v98) == 0;
          RegCloseKey(hKey);
        }
      }
      return Registry;
    }
    v20 = &SubKey[v18];
    v21 = 2 * (302 - v18);
    v22 = v21 >> 1;
    if ( (v21 >> 1) - 1 > 0x7FFFFFFE )
    {
      v95 = v22 == 0;
      goto LABEL_142;
    }
    v23 = 0;
    v24 = &gszSchemeAppsKey;
    v25 = v20;
    v26 = 2147483646;
    v27 = v21 >> 1;
    do
    {
      if ( !v26 )
        break;
      if ( !*(_WORD *)v24 )
        break;
      *v20 = *(_WORD *)v24;
      v24 = (unsigned __int16 near **)((char *)v24 + 2);
      ++v20;
      --v26;
      ++v23;
      --v27;
    }
    while ( v27 );
    v28 = v23 - 1;
    v29 = v20 - 1;
    if ( v27 )
    {
      v28 = v23;
      v29 = v20;
    }
    v30 = v22 - v28;
    *v29 = 0;
    v31 = v27 == 0 ? 0x8007007A : 0;
    if ( v27 || v31 == -2147024774 )
    {
      v25 += v28;
      v21 = 2 * v30;
    }
    if ( v31 )
      goto LABEL_138;
    v32 = v21 >> 1;
    if ( (v21 >> 1) - 1 > 0x7FFFFFFE )
    {
      pvData = (unsigned __int16 *)v98;
      if ( v32 )
        *v25 = 0;
      goto LABEL_105;
    }
    v33 = 2147483646;
    v34 = &aszDefault;
    v35 = v21 >> 1;
    v36 = 0;
    v37 = v25;
    do
    {
      if ( !v33 )
        break;
      if ( !*(_WORD *)v34 )
        break;
      *v25 = *(_WORD *)v34;
      v34 = (unsigned __int16 near **)((char *)v34 + 2);
      ++v25;
      --v33;
      ++v36;
      --v35;
    }
    while ( v35 );
    v38 = v36 - 1;
    v39 = v25 - 1;
    if ( v35 )
    {
      v38 = v36;
      v39 = v25;
    }
    v40 = v32 - v38;
    *v39 = 0;
    v41 = v35 == 0 ? 0x8007007A : 0;
    if ( v35 || v41 == -2147024774 )
    {
      v37 += v38;
      v21 = 2 * v40;
    }
    if ( !v41 )
    {
      v42 = v21 >> 1;
      if ( (v21 >> 1) - 1 > 0x7FFFFFFE )
        goto LABEL_134;
      v43 = &gszSlash;
      v44 = 0;
      v45 = &gszSlash;
      v46 = 2147483646;
      v47 = v21 >> 1;
      v48 = v37;
      do
      {
        if ( !v46 )
          break;
        if ( *(_WORD *)v45 == (_WORD)phkResult )
          break;
        *v37 = *(_WORD *)v45;
        v45 = (unsigned __int16 near **)((char *)v45 + 2);
        ++v37;
        --v46;
        ++v44;
        --v47;
      }
      while ( v47 );
      v49 = v44 - 1;
      v50 = v37 - 1;
      if ( v47 )
      {
        v49 = v44;
        v50 = v37;
      }
      v51 = v42 - v49;
      *v50 = 0;
      v52 = v47 == 0 ? 0x8007007A : 0;
      if ( v47 || v52 == -2147024774 )
      {
        v48 += v49;
        v21 = 2 * v51;
      }
      if ( v52 )
      {
LABEL_138:
        pvData = (unsigned __int16 *)v98;
LABEL_105:
        v9 = (unsigned __int16 *)hKey;
        if ( v100 )
          *a4 |= v100;
        goto LABEL_107;
      }
      v53 = v21 >> 1;
      if ( (v21 >> 1) - 1 > 0x7FFFFFFE )
      {
        pvData = (unsigned __int16 *)v98;
        if ( v53 )
          *v48 = 0;
        goto LABEL_105;
      }
      v54 = hKey;
      v55 = 2147483646;
      v56 = v21 >> 1;
      v57 = 0;
      v37 = v48;
      do
      {
        if ( !v55 )
          break;
        if ( *(_WORD *)v54 == (_WORD)phkResult )
          break;
        *v48 = *(_WORD *)v54;
        v54 = (HKEY)((char *)v54 + 2);
        ++v48;
        --v55;
        ++v57;
        --v56;
      }
      while ( v56 );
      v58 = v57 - 1;
      v59 = v48 - 1;
      if ( v56 )
      {
        v58 = v57;
        v59 = v48;
      }
      v60 = 0;
      v61 = v53 - v58;
      *v59 = 0;
      v62 = v56 == 0 ? 0x8007007A : 0;
      if ( v56 || v62 == -2147024774 )
      {
        v37 += v58;
        v21 = (v21 & 1) + 2 * v61;
      }
      if ( !v62 )
      {
        v42 = v21 >> 1;
        if ( (v21 >> 1) - 1 <= 0x7FFFFFFE )
        {
          v63 = 2147483646;
          v64 = &gszSlash;
          v65 = v21 >> 1;
          v20 = v37;
          do
          {
            if ( !v63 )
              break;
            if ( *(_WORD *)v64 == (_WORD)phkResult )
              break;
            *v37 = *(_WORD *)v64;
            v64 = (unsigned __int16 near **)((char *)v64 + 2);
            ++v37;
            --v63;
            ++v60;
            --v65;
          }
          while ( v65 );
          v66 = v60 - 1;
          v67 = v37 - 1;
          if ( v65 )
          {
            v66 = v60;
            v67 = v37;
          }
          v68 = v42 - v66;
          *v67 = 0;
          v69 = v65 == 0 ? 0x8007007A : 0;
          if ( v65 || v69 == -2147024774 )
          {
            v20 += v66;
            v21 = 2 * v68;
          }
          if ( !v69 )
          {
            v70 = v21 >> 1;
            if ( v70 - 1 <= 0x7FFFFFFE )
            {
              v71 = 2147483646;
              v72 = &aszCurrent;
              do
              {
                if ( !v71 )
                  break;
                if ( !*(_WORD *)v72 )
                  break;
                *v20 = *(_WORD *)v72;
                v72 = (unsigned __int16 near **)((char *)v72 + 2);
                ++v20;
                --v71;
                --v70;
              }
              while ( v70 );
              pvData = (unsigned __int16 *)v98;
              v73 = v20 - 1;
              if ( v70 )
                v73 = v20;
              *v73 = 0;
              if ( v70 )
              {
                phkResult = 0;
                *pvData = 0;
                if ( !RegOpenCurrentUser(1u, &phkResult) )
                {
                  v74 = phkResult;
                  v99 = v104;
                  *pvData = 0;
                  ValueW = RegGetValueW(v74, SubKey, 0, 2u, 0, pvData, &v99);
                  RegCloseKey(phkResult);
                  if ( !ValueW )
                  {
                    LODWORD(phkResult) = 4;
                    if ( !RegGetValueW(HKEY_CURRENT_USER, SubKey, gszDefaultFlags, 0x10u, 0, &v100, (LPDWORD)&phkResult) )
                      v100 &= 0x380002u;
                    v76 = 302;
                    v77 = SubKey;
                    do
                    {
                      if ( !*v77 )
                        break;
                      ++v77;
                      --v76;
                    }
                    while ( v76 );
                    v78 = (302 - v76) & -(__int64)(v76 != 0);
                    if ( v76 )
                    {
                      v79 = &SubKey[v78];
                      v80 = 2147483646;
                      v81 = 302 - v78;
                      if ( v78 != 302 )
                      {
                        do
                        {
                          if ( !v80 )
                            break;
                          if ( !*(_WORD *)v43 )
                            break;
                          *v79 = *(_WORD *)v43;
                          v43 = (unsigned __int16 near **)((char *)v43 + 2);
                          ++v79;
                          --v80;
                          --v81;
                        }
                        while ( v81 );
                      }
                      v82 = v79 - 1;
                      if ( v81 )
                        v82 = v79;
                      *v82 = 0;
                      if ( v81 )
                      {
                        v83 = 302;
                        v84 = SubKey;
                        do
                        {
                          if ( !*v84 )
                            break;
                          ++v84;
                          --v83;
                        }
                        while ( v83 );
                        v85 = (302 - v83) & -(__int64)(v83 != 0);
                        if ( v83 )
                        {
                          v86 = &SubKey[v85];
                          v87 = &aszActiveKey;
                          v88 = 302 - v85;
                          if ( 302 != v85 )
                          {
                            do
                            {
                              if ( !v13 )
                                break;
                              if ( !*(_WORD *)v87 )
                                break;
                              *v86 = *(_WORD *)v87;
                              v87 = (unsigned __int16 near **)((char *)v87 + 2);
                              ++v86;
                              --v13;
                              --v88;
                            }
                            while ( v88 );
                          }
                          v89 = v86 - 1;
                          if ( v88 )
                            v89 = v86;
                          *v89 = 0;
                          if ( v88 )
                          {
                            v99 = 0;
                            hkey = 0;
                            if ( RegOpenCurrentUser(1u, &hkey)
                              || (LODWORD(v98) = 4,
                                  LOWORD(v99) = 0,
                                  v91 = RegGetValueW(hkey, SubKey, 0, 2u, 0, &v99, (LPDWORD)&v98),
                                  RegCloseKey(hkey),
                                  v91)
                              || !lstrcmpW((LPCWSTR)&v99, aszBoolOne) )
                            {
                              Registry = 1;
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
              goto LABEL_105;
            }
            pvData = (unsigned __int16 *)v98;
            v95 = v70 == 0;
LABEL_142:
            if ( !v95 )
              *v20 = 0;
            goto LABEL_105;
          }
          goto LABEL_138;
        }
LABEL_134:
        pvData = (unsigned __int16 *)v98;
        if ( v42 )
          *v37 = 0;
        goto LABEL_105;
      }
    }
    pvData = (unsigned __int16 *)v98;
    goto LABEL_105;
  }
  return 0;
}

```

## disassembly

```asm
0x180016da4  push    rbp
0x180016da6  push    rbx
0x180016da7  push    rsi
0x180016da8  push    rdi
0x180016da9  push    r12
0x180016dab  push    r13
0x180016dad  push    r14
0x180016daf  push    r15
0x180016db1  lea     rbp, [rsp-458h]
0x180016db9  sub     rsp, 558h
0x180016dc0  mov     rax, cs:__security_cookie
0x180016dc7  xor     rax, rsp
0x180016dca  mov     [rbp+490h+var_50], rax
0x180016dd1  xor     esi, esi
0x180016dd3  mov     [rsp+590h+var_520], r8
0x180016dd8  mov     [rsp+590h+var_550], rdx
0x180016ddd  mov     r13, r9
0x180016de0  mov     [rsp+590h+phkResult], rsi
0x180016de5  mov     rdi, r8
0x180016de8  mov     r14, rdx
0x180016deb  mov     rbx, rcx
0x180016dee  test    rcx, rcx
0x180016df1  jz      loc_180017609
0x180016df7  test    rdx, rdx
0x180016dfa  jz      loc_180017609
0x180016e00  lea     rdx, ?gszDefaultBeepOldAlias@@3PAGA; "SystemDefault"
0x180016e07  mov     r15d, esi
0x180016e0a  call    cs:__imp_lstrcmpW
0x180016e10  lea     r12, ?szSystemDefaultSound@@3PAGA; ".Default"
0x180016e17  mov     [rsp+590h+var_548], 100h
0x180016e1f  test    eax, eax
0x180016e21  lea     r9d, [rsi+2]; dwFlags
0x180016e25  lea     rax, [rsp+590h+var_548]
0x180016e2a  mov     rcx, 0FFFFFFFF80000001h; hkey
0x180016e31  cmovnz  r12, rbx
0x180016e35  mov     [rsp+590h+pcbData], rax; HKEY
0x180016e3a  lea     rax, [rbp+490h+SubKey]
0x180016e3e  mov     [rsp+590h+hKey], r12
0x180016e43  mov     [rsp+590h+pvData], rax; pvData
0x180016e48  lea     rbx, ?gszSchemesRootKey@@3PAGA; "AppEvents\\Schemes\\"
0x180016e4f  mov     rdx, rbx; lpSubKey
0x180016e52  mov     [rsp+590h+pdwType], rsi; unsigned __int16 *
0x180016e57  xor     r8d, r8d; lpValue
0x180016e5a  call    cs:__imp_RegGetValueW
0x180016e60  xor     r11d, r11d
0x180016e63  test    eax, eax
0x180016e65  jz      loc_180017469
0x180016e6b  mov     ecx, 28h ; '('
0x180016e70  mov     rax, r12
0x180016e73  cmp     [rax], r11w
0x180016e77  jz      short loc_180016E83
0x180016e79  add     rax, 2
0x180016e7d  sub     rcx, 1; unsigned __int16 *
0x180016e81  jnz     short loc_180016E73
0x180016e83  test    rcx, rcx
0x180016e86  jz      loc_180017443
0x180016e8c  test    byte ptr [r13+0], 80h
0x180016e91  mov     esi, 12Eh
0x180016e96  jnz     loc_180017669
0x180016e9c  test    dword ptr [r13+0], 400000h
0x180016ea4  jnz     loc_180017610
0x180016eaa  mov     edi, 7FFFFFFEh
0x180016eaf  mov     [rsp+590h+var_540], r11d
0x180016eb4  mov     r8d, edi
0x180016eb7  lea     rax, [rbp+490h+SubKey]
0x180016ebb  mov     r15d, r11d
0x180016ebe  mov     rdx, rsi
0x180016ec1  mov     rcx, r11
0x180016ec4  test    r8, r8
0x180016ec7  jz      short loc_180016EEB
0x180016ec9  movzx   r9d, word ptr [rbx]
0x180016ecd  test    r9w, r9w
0x180016ed1  jz      short loc_180016EEB
0x180016ed3  mov     [rax], r9w
0x180016ed7  add     rbx, 2
0x180016edb  add     rax, 2
0x180016edf  dec     r8
0x180016ee2  inc     rcx
0x180016ee5  sub     rdx, 1
0x180016ee9  jnz     short loc_180016EC4
0x180016eeb  lea     r9, [rcx-1]
0x180016eef  test    rdx, rdx
0x180016ef2  cmovnz  r9, rcx
0x180016ef6  lea     rcx, [rax-2]
0x180016efa  cmovnz  rcx, rax
0x180016efe  mov     [rcx], r11w
0x180016f02  jz      loc_18001743A
0x180016f08  mov     r8, rsi
0x180016f0b  lea     r10, [rbp+490h+SubKey]
0x180016f0f  sub     r8, r9
0x180016f12  lea     r10, [r10+r9*2]
0x180016f16  add     r8, r8
0x180016f19  mov     r9, r8
0x180016f1c  shr     r9, 1
0x180016f1f  lea     rax, [r9-1]
0x180016f23  cmp     rax, rdi
0x180016f26  ja      loc_180017719
0x180016f2c  mov     rbx, r11
0x180016f2f  lea     rcx, ?gszSchemeAppsKey@@3PAGA; "Apps\\"
0x180016f36  mov     r11, r10
0x180016f39  mov     rax, rdi
0x180016f3c  mov     r14, r9
0x180016f3f  xor     r12d, r12d
0x180016f42  test    rax, rax
0x180016f45  jz      short loc_180016F67
0x180016f47  movzx   edx, word ptr [rcx]
0x180016f4a  test    dx, dx
0x180016f4d  jz      short loc_180016F67
0x180016f4f  mov     [r10], dx
0x180016f53  add     rcx, 2
0x180016f57  add     r10, 2
0x180016f5b  dec     rax
0x180016f5e  inc     rbx
0x180016f61  sub     r14, 1
0x180016f65  jnz     short loc_180016F42
0x180016f67  test    r14, r14
0x180016f6a  lea     rdx, [rbx-1]
0x180016f6e  mov     rax, r14
0x180016f71  lea     rcx, [r10-2]
0x180016f75  cmovnz  rdx, rbx
0x180016f79  neg     rax
0x180016f7c  sbb     ebx, ebx
0x180016f7e  test    r14, r14
0x180016f81  not     ebx
0x180016f83  lea     rax, [r11+rdx*2]
0x180016f87  cmovnz  rcx, r10
0x180016f8b  sub     r9, rdx
0x180016f8e  mov     [rcx], r12w
0x180016f92  and     ebx, 8007007Ah
0x180016f98  jns     loc_18001748F
0x180016f9e  cmp     ebx, 8007007Ah
0x180016fa4  jz      loc_18001748F
0x180016faa  test    ebx, ebx
0x180016fac  jnz     loc_180017702
0x180016fb2  mov     r9, r8
0x180016fb5  shr     r9, 1
0x180016fb8  lea     rax, [r9-1]
0x180016fbc  cmp     rax, rdi
0x180016fbf  ja      loc_1800176F2
0x180016fc5  mov     rax, rdi
0x180016fc8  lea     rcx, ?aszDefault@@3PAGA; ".Default"
0x180016fcf  mov     r14, r9
0x180016fd2  mov     r10, r12
0x180016fd5  mov     rbx, r11
0x180016fd8  test    rax, rax
0x180016fdb  jz      short loc_180016FFD
0x180016fdd  movzx   edx, word ptr [rcx]
0x180016fe0  test    dx, dx
0x180016fe3  jz      short loc_180016FFD
0x180016fe5  mov     [r11], dx
0x180016fe9  add     rcx, 2
0x180016fed  add     r11, 2
0x180016ff1  dec     rax
0x180016ff4  inc     r10
0x180016ff7  sub     r14, 1
0x180016ffb  jnz     short loc_180016FD8
0x180016ffd  test    r14, r14
0x180017000  lea     rdx, [r10-1]
0x180017004  lea     rcx, [r11-2]
0x180017008  mov     rax, r14
0x18001700b  cmovnz  rdx, r10
0x18001700f  neg     rax
0x180017012  sbb     r10d, r10d
0x180017015  test    r14, r14
0x180017018  not     r10d
0x18001701b  lea     rax, [rbx+rdx*2]
0x18001701f  cmovnz  rcx, r11
0x180017023  xor     r11d, r11d
0x180017026  sub     r9, rdx
0x180017029  mov     [rcx], r11w
0x18001702d  and     r10d, 8007007Ah
0x180017034  jns     loc_18001749B
0x18001703a  cmp     r10d, 8007007Ah
0x180017041  jz      loc_18001749B
0x180017047  test    r10d, r10d
0x18001704a  jnz     loc_18001770F
0x180017050  mov     r9, r8
0x180017053  shr     r9, 1
0x180017056  lea     rax, [r9-1]
0x18001705a  cmp     rax, rdi
0x18001705d  ja      loc_1800176DB
0x180017063  lea     r12, ?gszSlash@@3PAGA; "\\"
0x18001706a  mov     r10, r11
0x18001706d  mov     rcx, r12
0x180017070  mov     rax, rdi
0x180017073  mov     r14, r9
0x180017076  mov     r11, rbx
0x180017079  test    rax, rax
0x18001707c  jz      short loc_18001709F
0x18001707e  movzx   edx, word ptr [rcx]
0x180017081  cmp     dx, word ptr [rsp+590h+phkResult]
0x180017086  jz      short loc_18001709F
0x180017088  mov     [rbx], dx
0x18001708b  add     rcx, 2
0x18001708f  add     rbx, 2
0x180017093  dec     rax
0x180017096  inc     r10
0x180017099  sub     r14, 1
0x18001709d  jnz     short loc_180017079
0x18001709f  test    r14, r14
0x1800170a2  lea     rdx, [r10-1]
0x1800170a6  mov     rax, r14
0x1800170a9  lea     rcx, [rbx-2]
0x1800170ad  cmovnz  rdx, r10
0x1800170b1  neg     rax
0x1800170b4  sbb     r10d, r10d
0x1800170b7  xor     eax, eax
0x1800170b9  test    r14, r14
0x1800170bc  not     r10d
0x1800170bf  cmovnz  rcx, rbx
0x1800170c3  sub     r9, rdx
0x1800170c6  mov     [rcx], ax
0x1800170c9  lea     rax, [r11+rdx*2]
0x1800170cd  xor     edx, edx
0x1800170cf  and     r10d, 8007007Ah
0x1800170d6  jns     loc_180017520
0x1800170dc  cmp     r10d, 8007007Ah
0x1800170e3  jz      loc_180017520
0x1800170e9  test    r10d, r10d
0x1800170ec  jnz     loc_180017702
0x1800170f2  mov     r9, r8
0x1800170f5  shr     r9, 1
0x1800170f8  lea     rax, [r9-1]
0x1800170fc  cmp     rax, rdi
0x1800170ff  ja      loc_1800176CB
0x180017105  mov     rcx, [rsp+590h+hKey]
0x18001710a  mov     rax, rdi
0x18001710d  mov     r14, r9
0x180017110  mov     r10, rdx
0x180017113  mov     rbx, r11
0x180017116  test    rax, rax
0x180017119  jz      short loc_18001713D
0x18001711b  movzx   edx, word ptr [rcx]
0x18001711e  cmp     dx, word ptr [rsp+590h+phkResult]
0x180017123  jz      short loc_18001713D
0x180017125  mov     [r11], dx
0x180017129  add     rcx, 2
0x18001712d  add     r11, 2
0x180017131  dec     rax
0x180017134  inc     r10
0x180017137  sub     r14, 1
0x18001713b  jnz     short loc_180017116
0x18001713d  test    r14, r14
0x180017140  lea     rdx, [r10-1]
0x180017144  lea     rcx, [r11-2]
0x180017148  mov     rax, r14
0x18001714b  cmovnz  rdx, r10
0x18001714f  neg     rax
0x180017152  sbb     r10d, r10d
0x180017155  test    r14, r14
0x180017158  not     r10d
0x18001715b  lea     rax, [rbx+rdx*2]
0x18001715f  cmovnz  rcx, r11
0x180017163  xor     r11d, r11d
0x180017166  sub     r9, rdx
0x180017169  mov     [rcx], r11w
0x18001716d  and     r10d, 8007007Ah
0x180017174  jns     loc_18001752C
0x18001717a  cmp     r10d, 8007007Ah
0x180017181  jz      loc_18001752C
0x180017187  test    r10d, r10d
0x18001718a  jnz     loc_18001770F
0x180017190  mov     r9, r8
0x180017193  shr     r9, 1
0x180017196  lea     rax, [r9-1]
0x18001719a  cmp     rax, rdi
0x18001719d  ja      loc_1800176DB
0x1800171a3  mov     rax, rdi
0x1800171a6  mov     rcx, r12
0x1800171a9  mov     r14, r9
0x1800171ac  mov     r10, rbx
0x1800171af  test    rax, rax
0x1800171b2  jz      short loc_1800171D5
0x1800171b4  movzx   edx, word ptr [rcx]
0x1800171b7  cmp     dx, word ptr [rsp+590h+phkResult]
0x1800171bc  jz      short loc_1800171D5
0x1800171be  mov     [rbx], dx
0x1800171c1  add     rcx, 2
0x1800171c5  add     rbx, 2
0x1800171c9  dec     rax
0x1800171cc  inc     r11
0x1800171cf  sub     r14, 1
0x1800171d3  jnz     short loc_1800171AF
0x1800171d5  test    r14, r14
0x1800171d8  lea     rdx, [r11-1]
0x1800171dc  lea     rcx, [rbx-2]
0x1800171e0  mov     rax, r14
0x1800171e3  cmovnz  rdx, r11
0x1800171e7  neg     rax
0x1800171ea  sbb     r11d, r11d
0x1800171ed  test    r14, r14
0x1800171f0  not     r11d
0x1800171f3  lea     rax, [r10+rdx*2]
0x1800171f7  cmovnz  rcx, rbx
0x1800171fb  xor     ebx, ebx
0x1800171fd  sub     r9, rdx
0x180017200  mov     [rcx], bx
0x180017203  and     r11d, 8007007Ah
0x18001720a  jns     loc_18001753C
0x180017210  cmp     r11d, 8007007Ah
  ... truncated ...
```
