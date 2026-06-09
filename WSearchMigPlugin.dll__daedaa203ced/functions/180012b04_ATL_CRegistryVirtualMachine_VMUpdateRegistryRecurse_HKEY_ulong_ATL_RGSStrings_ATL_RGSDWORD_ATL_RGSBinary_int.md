# ATL::CRegistryVirtualMachine::VMUpdateRegistryRecurse(HKEY__ *,ulong * &,ATL::RGSStrings *,ATL::RGSDWORD *,ATL::RGSBinary *,int)

- ea: `0x180012b04`
- end: `0x180013c49`
- name: `?VMUpdateRegistryRecurse@CRegistryVirtualMachine@ATL@@QEAAJPEAUHKEY__@@AEAPEAKPEAURGSStrings@2@PEAURGSDWORD@2@PEAURGSBinary@2@H@Z`
- size: `4421`
- prototype: `__int64 __fastcall(ATL::CRegistryVirtualMachine *this, HKEY, unsigned int **, struct ATL::RGSStrings *, struct ATL::RGSDWORD *, struct ATL::RGSBinary *, int)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, installer_update`

## callers

- `0x1800129f0`
- `0x180012b04`

## callees

- `0x1800026f0`
- `0x18000329c`
- `0x18000b410`
- `0x18000cfb4`
- `0x18000d75c`
- `0x18000d790`
- `0x18000ddf8`
- `0x18000e1bc`
- `0x18000fa28`
- `0x180010f84`
- `0x180012390`
- `0x180012b04`
- `0x180018010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180012d0e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180012e17`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180012e48`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800132eb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013330`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013352`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800134be`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013595`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800135c6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800135e8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800138d4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800138ef`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013933`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001395d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013992`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800139a9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013b23`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013b48`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013b6a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180012d0e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180012e17`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180012e48`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800132eb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013330`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013352`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800134be`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013595`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800135c6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800135e8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800138d4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800138ef`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013933`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001395d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013992`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800139a9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013b23`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013b48`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013b6a`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180013488`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180013488`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800137c7`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800137e3`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800137c7`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800137e3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800132b0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001357a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013899`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013b07`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800132b0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001357a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013899`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013b07`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012dd7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012dd7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012d41`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012deb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012e26`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012eeb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800134cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800139b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013bf1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012d41`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012deb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012e26`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012eeb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800134cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800139b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013bf1`

## pseudocode

```c
__int64 __fastcall ATL::CRegistryVirtualMachine::VMUpdateRegistryRecurse(
        ATL::CRegistryVirtualMachine *this,
        HKEY a2,
        unsigned int **a3,
        struct ATL::RGSStrings *a4,
        struct ATL::RGSDWORD *a5,
        struct ATL::RGSBinary *a6,
        int a7)
{
  struct ATL::RGSStrings *v7; // r11
  unsigned int **v8; // r15
  HKEY v9; // r13
  ATL::CRegistryVirtualMachine *v10; // r10
  struct ATL::RGSDWORD *v11; // r9
  struct ATL::RGSBinary *v12; // r8
  HKEY v13; // rsi
  signed int StringAtLoc; // r12d
  unsigned int v15; // ebx
  unsigned int v16; // r14d
  unsigned int v17; // eax
  unsigned int v18; // ebx
  int v19; // ebx
  HKEY v21; // rcx
  void *v22; // rbx
  const WCHAR *v23; // rdx
  LSTATUS v24; // eax
  unsigned int v25; // r14d
  void *v26; // r15
  WCHAR *v27; // r13
  DWORD v28; // ecx
  WCHAR *v29; // rax
  __int64 v30; // rcx
  size_t v31; // rbx
  HKEY v32; // rax
  void *v33; // rcx
  unsigned int v34; // r10d
  int v35; // r9d
  const BYTE *v36; // rbx
  LPWSTR v37; // r11
  unsigned int v38; // edx
  char v39; // r8
  HKEY v40; // rcx
  const WCHAR *v41; // rdx
  LSTATUS v42; // eax
  DWORD v43; // r8d
  _WORD *v44; // rbx
  __int64 v45; // r8
  HKEY v46; // rbx
  volatile signed __int32 *v47; // rdx
  HKEY v48; // rcx
  const WCHAR *v49; // rdx
  LSTATUS v50; // eax
  void *v51; // rcx
  WCHAR *v52; // r13
  const WCHAR *v53; // r15
  __int64 v54; // rax
  int v55; // eax
  BYTE *v56; // rbx
  const WCHAR *v57; // rax
  HKEY v58; // r10
  const WCHAR *v59; // r11
  DWORD cbData; // r9d
  BYTE *v61; // r8
  __int64 v62; // rcx
  __int64 v63; // rcx
  LSTATUS v64; // eax
  WCHAR *v65; // r15
  LPCWSTR v66; // r13
  HKEY v67; // r10
  const BYTE *v68; // rcx
  const WCHAR *v69; // rdx
  __int64 v70; // rax
  LSTATUS v71; // eax
  char v72; // [rsp+40h] [rbp-9D8h]
  char v73; // [rsp+40h] [rbp-9D8h]
  char v74; // [rsp+40h] [rbp-9D8h]
  char v75; // [rsp+40h] [rbp-9D8h]
  char v76; // [rsp+41h] [rbp-9D7h]
  HKEY phkResult; // [rsp+48h] [rbp-9D0h] BYREF
  unsigned int v78; // [rsp+50h] [rbp-9C8h]
  DWORD pulOut; // [rsp+54h] [rbp-9C4h] BYREF
  ATL::CRegistryVirtualMachine *v80; // [rsp+58h] [rbp-9C0h]
  struct ATL::RGSStrings *v81; // [rsp+60h] [rbp-9B8h]
  LPCWSTR v82; // [rsp+68h] [rbp-9B0h] BYREF
  HKEY v83; // [rsp+70h] [rbp-9A8h]
  struct ATL::RGSBinary *v84; // [rsp+78h] [rbp-9A0h]
  struct ATL::RGSDWORD *v85; // [rsp+80h] [rbp-998h]
  BYTE Data[8]; // [rsp+88h] [rbp-990h] BYREF
  unsigned int **v87; // [rsp+90h] [rbp-988h]
  HKEY v88[3]; // [rsp+98h] [rbp-980h] BYREF
  unsigned int v89; // [rsp+B0h] [rbp-968h]
  void *v90; // [rsp+B8h] [rbp-960h] BYREF
  __int64 v91; // [rsp+C0h] [rbp-958h]
  LPWSTR v92; // [rsp+C8h] [rbp-950h] BYREF
  void *Block; // [rsp+D0h] [rbp-948h] BYREF
  __int64 v94; // [rsp+D8h] [rbp-940h]
  LPCWSTR lpValueName; // [rsp+E0h] [rbp-938h] BYREF
  __int64 v96; // [rsp+E8h] [rbp-930h]
  void *v97; // [rsp+F0h] [rbp-928h] BYREF
  __int64 v98; // [rsp+F8h] [rbp-920h]
  WCHAR *v99; // [rsp+100h] [rbp-918h] BYREF
  __int64 v100; // [rsp+108h] [rbp-910h]
  unsigned int v101; // [rsp+110h] [rbp-908h]
  const WCHAR *v102; // [rsp+118h] [rbp-900h]
  void *v103; // [rsp+120h] [rbp-8F8h] BYREF
  __int64 v104; // [rsp+128h] [rbp-8F0h]
  void *v105; // [rsp+130h] [rbp-8E8h] BYREF
  __int64 v106; // [rsp+138h] [rbp-8E0h]
  WCHAR *v107; // [rsp+140h] [rbp-8D8h] BYREF
  __int64 v108; // [rsp+148h] [rbp-8D0h]
  void *v109; // [rsp+150h] [rbp-8C8h] BYREF
  __int64 v110; // [rsp+158h] [rbp-8C0h]
  HKEY v111; // [rsp+160h] [rbp-8B8h]
  ATL::CRegistryVirtualMachine *v112; // [rsp+168h] [rbp-8B0h]
  unsigned int **v113; // [rsp+170h] [rbp-8A8h]
  struct ATL::RGSStrings *v114; // [rsp+178h] [rbp-8A0h]
  __int64 v115; // [rsp+180h] [rbp-898h]
  HKEY v116; // [rsp+188h] [rbp-890h]
  __int64 v117; // [rsp+190h] [rbp-888h]
  __int64 v118; // [rsp+198h] [rbp-880h]
  __int64 v119; // [rsp+1A0h] [rbp-878h]
  __int64 v120; // [rsp+1A8h] [rbp-870h]
  void *v121; // [rsp+1B0h] [rbp-868h] BYREF
  _BYTE v122[1032]; // [rsp+1B8h] [rbp-860h] BYREF
  BYTE *lpData; // [rsp+5C0h] [rbp-458h] BYREF
  _BYTE v124[1032]; // [rsp+5C8h] [rbp-450h] BYREF

  v119 = -2;
  v7 = a4;
  v81 = a4;
  v8 = a3;
  v87 = a3;
  v9 = a2;
  v83 = a2;
  v10 = this;
  v80 = this;
  v112 = this;
  v111 = a2;
  v113 = a3;
  v114 = a4;
  v11 = a5;
  v85 = a5;
  v12 = a6;
  v84 = a6;
  v13 = 0;
  memset(v88, 0, sizeof(v88));
  StringAtLoc = 0;
  v76 = 0;
  v89 = 0;
  v120 = 0;
LABEL_2:
  v15 = **v8;
LABEL_3:
  v16 = (v15 >> 14) & 0x3FFF;
  v17 = v15 >> 28;
  v78 = v16;
  v18 = v15 & 0x3FFF;
  while ( 1 )
  {
    while ( 1 )
    {
      if ( v17 == 6 )
      {
        ++*v8;
        goto LABEL_264;
      }
      if ( v17 > 6 )
        break;
      switch ( v17 )
      {
        case 0u:
          if ( v13 )
            RegCloseKey(v13);
          return 0;
        case 1u:
          if ( !a7 )
          {
LABEL_53:
            v76 = 1;
            goto LABEL_54;
          }
          StringAtLoc = ATL::CRegistryVirtualMachine::AddKeyWithReplacement(v10, v9, v88, v16, v7);
          if ( StringAtLoc >= 0 )
          {
            v13 = v88[0];
            v10 = v80;
            v7 = v81;
            v12 = v84;
            v11 = v85;
            goto LABEL_53;
          }
LABEL_28:
          v21 = v88[0];
          if ( v88[0] )
LABEL_266:
            RegCloseKey(v21);
          return (unsigned int)StringAtLoc;
        case 2u:
          if ( !a7 )
            goto LABEL_18;
          v19 = ATL::CRegistryVirtualMachine::DeleteKeyWithReplacement(v10, v9, v16, v7);
          if ( v19 < 0 )
            goto LABEL_23;
          v10 = v80;
          v7 = v81;
LABEL_27:
          StringAtLoc = ATL::CRegistryVirtualMachine::AddKeyWithReplacement(v10, v9, v88, v16, v7);
          if ( StringAtLoc < 0 )
            goto LABEL_28;
          v13 = v88[0];
LABEL_48:
          v15 = *++*v8;
LABEL_49:
          v10 = v80;
          v7 = v81;
          v12 = v84;
          v11 = v85;
          goto LABEL_3;
        case 3u:
          if ( a7 )
            goto LABEL_27;
LABEL_18:
          phkResult = 0;
          Block = 0;
          v94 = 0;
          StringAtLoc = ATL::CRegistryVirtualMachine::GetStringAtLoc(
                          (__int64)v10,
                          (__int64)v7,
                          v16,
                          (__int64)&Block,
                          (LPWSTR *)&phkResult);
          if ( StringAtLoc >= 0 )
          {
            v22 = Block;
            if ( v9 )
            {
              v23 = (const WCHAR *)Block;
              if ( phkResult )
                v23 = (const WCHAR *)phkResult;
              phkResult = 0;
              v24 = RegOpenKeyExW(v9, v23, 0, 0x2001Fu, &phkResult);
              if ( !v24 )
              {
                v24 = 0;
                if ( v13 )
                  v24 = RegCloseKey(v13);
                v13 = phkResult;
                v88[0] = phkResult;
              }
              if ( (v24 & 0xFFFFFFFD) != 0 )
              {
                v25 = ATL::AtlHresultFromWin32(v24);
                goto LABEL_40;
              }
            }
            v89 = **v8;
            if ( v22 )
            {
              free(v22);
              Block = 0;
            }
            v94 = 0;
            goto LABEL_48;
          }
          if ( Block )
            free(Block);
LABEL_264:
          if ( v13 )
          {
            v21 = v13;
            goto LABEL_266;
          }
          return (unsigned int)StringAtLoc;
        case 5u:
          ++*v8;
          StringAtLoc = ATL::CRegistryVirtualMachine::VMUpdateRegistryRecurse(v10, v13, v8, v7, v11, v12, a7);
          if ( StringAtLoc >= 0 )
          {
            v15 = **v8;
            if ( a7 )
              goto LABEL_49;
            if ( v76 )
            {
              v76 = 0;
              goto LABEL_49;
            }
            StringAtLoc = ATL::CRegistryVirtualMachine::DeleteKeyWithReplacement(v80, v9, (v89 >> 14) & 0x3FFF, v81);
            if ( StringAtLoc >= 0 )
              goto LABEL_49;
          }
          goto LABEL_264;
      }
    }
    if ( v17 == 7 )
    {
      ++*v8;
      v19 = ATL::CRegistryVirtualMachine::VMUpdateRegistryRecurse(
              v10,
              (HKEY)(v16 | 0xFFFFFFFF80000000uLL),
              v8,
              v7,
              v11,
              v12,
              a7);
      goto LABEL_23;
    }
    if ( v17 == 8 )
      break;
    switch ( v17 )
    {
      case 9u:
        if ( !a7 )
          goto LABEL_54;
        v74 = 0;
        if ( !v13 )
        {
          v13 = v9;
          v88[0] = v9;
          v74 = 1;
        }
        v90 = 0;
        v91 = 0;
        v52 = 0;
        v99 = 0;
        v100 = 0;
        phkResult = 0;
        v82 = 0;
        StringAtLoc = ATL::CRegistryVirtualMachine::GetStringAtLoc(
                        (__int64)v10,
                        (__int64)v7,
                        v18,
                        (__int64)&v90,
                        (LPWSTR *)&phkResult);
        pulOut = StringAtLoc;
        if ( StringAtLoc >= 0 && v16 )
        {
          StringAtLoc = ATL::CRegistryVirtualMachine::GetStringAtLoc(
                          (__int64)v80,
                          (__int64)v81,
                          v16,
                          (__int64)&v99,
                          (LPWSTR *)&v82);
          pulOut = StringAtLoc;
          v52 = v99;
        }
        v53 = (const WCHAR *)v90;
        if ( phkResult )
          v53 = (const WCHAR *)phkResult;
        v102 = v53;
        v54 = -1;
        do
          ++v54;
        while ( v53[v54] );
        try
        {
          v55 = v54 + 2;
          lpData = 0;
          if ( !v55 )
            goto LABEL_191;
          if ( 0xFFFFFFFFFFFFFFFFuLL / v55 < 2 )
            ATL::AtlThrowImpl(-2147024809);
          if ( (unsigned __int64)(2LL * v55) > 0x400 )
          {
            ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, 2LL * v55);
            v56 = lpData;
          }
          else
          {
LABEL_191:
            v56 = v124;
            lpData = v124;
          }
        }
        catch ( ... )
        {
          v13 = v88[0];
          StringAtLoc = pulOut;
          v16 = v78;
          v52 = v99;
          v53 = v102;
          v56 = lpData;
          v83 = v111;
          v80 = v112;
          v87 = v113;
          v81 = v114;
        }
        if ( v56 )
        {
          if ( *v53 )
          {
            do
            {
              v57 = CharNextW(v53);
              if ( *v53 == 92 && *v57 == 48 )
              {
                *(_WORD *)v56 = 0;
                v53 = CharNextW(v57);
              }
              else
              {
                *(_WORD *)v56 = *v53++;
              }
              v56 += 2;
            }
            while ( *v53 );
            v52 = v99;
          }
          *(_DWORD *)v56 = 0;
          v117 = 0;
          v118 = 0;
          if ( v16 )
          {
            v58 = v83;
            v116 = v83;
            v59 = v52;
            if ( v82 )
              v59 = v82;
          }
          else
          {
            v58 = v13;
            v116 = v13;
            v59 = 0;
          }
          if ( !lpData )
            ATL::AtlThrowImpl(-2147467259);
          cbData = 0;
          v61 = lpData;
          do
          {
            v62 = -1;
            do
              ++v62;
            while ( *(_WORD *)&v61[2 * v62] );
            v63 = (unsigned int)(v62 + 1);
            v61 += 2 * v63;
            cbData += 2 * v63;
          }
          while ( (_DWORD)v63 != 1 );
          v64 = RegSetValueExW(v58, v59, 0, 7u, lpData, cbData);
          if ( !v64 )
          {
            if ( v74 )
              v13 = 0;
            v88[0] = v13;
            if ( lpData != v124 )
              ATL::CTempBuffer<unsigned char,1024,ATL::CCRTAllocator>::FreeHeap((void **)&lpData);
            if ( v52 )
            {
              free(v52);
              v99 = 0;
            }
            v100 = 0;
            if ( v90 )
            {
              free(v90);
              v90 = 0;
            }
            v91 = 0;
            goto LABEL_261;
          }
          v19 = ATL::AtlHresultFromWin32(v64);
          if ( lpData != v124 )
            ATL::CTempBuffer<unsigned char,1024,ATL::CCRTAllocator>::FreeHeap((void **)&lpData);
          if ( v52 )
            free(v52);
          if ( v90 )
          {
            v51 = v90;
LABEL_216:
            free(v51);
          }
LABEL_23:
          if ( v13 )
            RegCloseKey(v13);
          return (unsigned int)v19;
        }
        ATL::CTempBuffer<unsigned char,1024,ATL::CCRTAllocator>::FreeHeap((void **)&lpData);
        if ( v52 )
          free(v52);
        if ( v90 )
        {
          v33 = v90;
LABEL_230:
          free(v33);
        }
LABEL_231:
        if ( v13 )
          RegCloseKey(v13);
        return 2147942414LL;
      case 0xAu:
        if ( !a7 )
          goto LABEL_54;
        v73 = 0;
        if ( !v13 )
        {
          v13 = v9;
          v88[0] = v9;
          v73 = 1;
        }
        v26 = 0;
        v105 = 0;
        v106 = 0;
        v27 = 0;
        v103 = 0;
        v104 = 0;
        phkResult = 0;
        v82 = 0;
        v43 = *((_DWORD *)v11 + 2 * v18);
        pulOut = v43;
        if ( *((_BYTE *)v11 + 8 * v18 + 4) == 1 )
        {
          ATL::CRegistryVirtualMachine::GetStringAtLoc(
            (__int64)v10,
            (__int64)v7,
            v43,
            (__int64)&v105,
            (LPWSTR *)&phkResult);
          v26 = v105;
          v44 = v105;
          if ( phkResult )
            v44 = phkResult;
          phkResult = (HKEY)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
          if ( v44 )
          {
            if ( (unsigned __int64)v44 < 0x10000 )
            {
              ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::LoadStringW(
                &phkResult,
                (unsigned __int16)v44);
              goto LABEL_147;
            }
            v45 = -1;
            do
              ++v45;
            while ( v44[v45] );
          }
          else
          {
            v45 = 0;
          }
          ATL::CSimpleStringT<wchar_t,0>::SetString(&phkResult, v44, v45);
LABEL_147:
          v46 = phkResult;
          StringAtLoc = VarUI4FromStr((LPCOLESTR)phkResult, 0, 0, &pulOut);
          v47 = (volatile signed __int32 *)(v46 - 6);
          if ( StringAtLoc < 0 )
          {
            if ( _InterlockedExchangeAdd(v47 + 4, 0xFFFFFFFF) <= 1 )
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v47 + 8LL))(*(_QWORD *)v47);
            goto LABEL_150;
          }
          if ( _InterlockedExchangeAdd(v47 + 4, 0xFFFFFFFF) <= 1 )
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v47 + 8LL))(*(_QWORD *)v47);
          v10 = v80;
          v7 = v81;
        }
        else
        {
          StringAtLoc = 0;
        }
        if ( v16 )
        {
          StringAtLoc = ATL::CRegistryVirtualMachine::GetStringAtLoc(
                          (__int64)v10,
                          (__int64)v7,
                          v16,
                          (__int64)&v103,
                          (LPWSTR *)&v82);
          v48 = v83;
          v27 = (WCHAR *)v103;
        }
        else
        {
          v48 = v13;
        }
        v49 = v27;
        if ( v82 )
          v49 = v82;
        *(_DWORD *)Data = pulOut;
        v50 = RegSetValueExW(v48, v49, 0, 4u, Data, 4u);
        if ( v50 )
        {
          v19 = ATL::AtlHresultFromWin32(v50);
          if ( v27 )
            goto LABEL_166;
          goto LABEL_167;
        }
        if ( v73 )
          v13 = 0;
        v88[0] = v13;
        if ( v27 )
        {
          free(v27);
          v103 = 0;
        }
        v104 = 0;
        if ( v26 )
        {
          free(v26);
          v105 = 0;
        }
        v106 = 0;
        goto LABEL_261;
      case 0xBu:
        if ( !a7 )
          goto LABEL_54;
        v72 = 0;
        if ( !v13 )
        {
          v13 = v9;
          v88[0] = v9;
          v72 = 1;
        }
        v26 = 0;
        v97 = 0;
        v98 = 0;
        v27 = 0;
        lpValueName = 0;
        v96 = 0;
        v92 = 0;
        v82 = 0;
        v121 = 0;
        v28 = *((_DWORD *)v12 + 4 * v18 + 2);
        pulOut = v28;
        if ( *((_BYTE *)v12 + 16 * v18 + 12) != 1 )
        {
          v36 = (const BYTE *)*((_QWORD *)v12 + 2 * v18);
          StringAtLoc = 0;
          goto LABEL_113;
        }
        ATL::CRegistryVirtualMachine::GetStringAtLoc((__int64)v10, (__int64)v7, v28, (__int64)&v97, &v92);
        v26 = v97;
        v29 = v92;
        if ( !v92 )
          v29 = (WCHAR *)v97;
        v92 = v29;
        v30 = -1;
        do
          ++v30;
        while ( v29[v30] );
        v115 = v30;
        v101 = v30;
        if ( (v30 & 1) != 0 )
        {
          if ( v121 != v122 )
            ATL::CTempBuffer<unsigned char,1024,ATL::CCRTAllocator>::FreeHeap(&v121);
LABEL_150:
          if ( v26 )
            free(v26);
          if ( v13 )
            RegCloseKey(v13);
          return 2147500037LL;
        }
        try
        {
          pulOut = (int)v30 / 2;
          v31 = (unsigned int)((int)v30 / 2);
          v102 = (const WCHAR *)v31;
          if ( !((int)v30 / 2) )
            goto LABEL_78;
          if ( !(0xFFFFFFFFFFFFFFFFuLL / v31) )
            ATL::AtlThrowImpl(-2147024809);
          if ( v31 > 0x400 )
          {
            ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(&v121, v31);
            v32 = (HKEY)v121;
          }
          else
          {
LABEL_78:
            v32 = (HKEY)v122;
            v121 = v122;
          }
          phkResult = v32;
        }
        catch ( ... )
        {
          v13 = v88[0];
          v16 = v78;
          v26 = v97;
          v27 = (WCHAR *)lpValueName;
          v32 = (HKEY)v121;
          phkResult = (HKEY)v121;
          v115 = v101;
          v31 = (size_t)v102;
          v83 = v111;
          v80 = v112;
          v87 = v113;
          v81 = v114;
          pulOut = (unsigned int)v102;
        }
        if ( !v32 )
        {
          ATL::CTempBuffer<unsigned char,1024,ATL::CCRTAllocator>::FreeHeap(&v121);
          if ( v26 )
          {
            v33 = v26;
            goto LABEL_230;
          }
          goto LABEL_231;
        }
        StringAtLoc = 1;
        memset_0(v32, 0, v31);
        v34 = 0;
        v35 = v115;
        v36 = (const BYTE *)phkResult;
        if ( (int)v115 <= 0 )
          goto LABEL_112;
        v37 = v92;
        while ( 2 )
        {
          v38 = v37[v34];
          if ( v38 > 0x61 )
          {
            if ( v38 != 98 && v38 != 99 && v38 != 100 && v38 - 101 >= 2 )
              goto LABEL_108;
LABEL_109:
            v39 = v38 - 87;
            goto LABEL_110;
          }
          if ( v38 == 97 )
            goto LABEL_109;
          if ( v38 > 0x38 )
          {
            if ( v38 == 57 )
              goto LABEL_96;
            if ( v38 != 65 && v38 != 66 && v38 != 67 && v38 != 68 && v38 - 69 > 1 )
              goto LABEL_108;
            v39 = v38 - 55;
          }
          else
          {
            if ( v38 == 56
              || v38 == 48
              || v38 == 49
              || v38 == 50
              || v38 == 51
              || v38 == 52
              || v38 == 53
              || v38 - 54 <= 1 )
            {
LABEL_96:
              v39 = v38 - 48;
              goto LABEL_110;
            }
LABEL_108:
            v39 = 0;
          }
LABEL_110:
          v36[(unsigned __int64)v34 >> 1] |= v39 << (4 - 4 * (v34 & 1));
          if ( (int)++v34 < v35 )
            continue;
          break;
        }
        v26 = v97;
LABEL_112:
        v7 = v81;
        v10 = v80;
LABEL_113:
        if ( !v16 )
        {
          v40 = v13;
          goto LABEL_118;
        }
        StringAtLoc = ATL::CRegistryVirtualMachine::GetStringAtLoc(
                        (__int64)v10,
                        (__int64)v7,
                        v16,
                        (__int64)&lpValueName,
                        (LPWSTR *)&v82);
        v40 = v83;
        v41 = v82;
        v27 = (WCHAR *)lpValueName;
        if ( !v82 )
LABEL_118:
          v41 = v27;
        v42 = RegSetValueExW(v40, v41, 0, 3u, v36, pulOut);
        if ( v42 )
        {
          v19 = ATL::AtlHresultFromWin32(v42);
          if ( v121 != v122 )
            ATL::CTempBuffer<unsigned char,1024,ATL::CCRTAllocator>::FreeHeap(&v121);
          if ( v27 )
LABEL_166:
            free(v27);
LABEL_167:
          if ( v26 )
          {
            v51 = v26;
            goto LABEL_216;
          }
          goto LABEL_23;
        }
        if ( v72 )
          v13 = 0;
        v88[0] = v13;
        if ( v121 != v122 )
          ATL::CTempBuffer<unsigned char,1024,ATL::CCRTAllocator>::FreeHeap(&v121);
        if ( v27 )
        {
          free(v27);
          lpValueName = 0;
        }
        v96 = 0;
        if ( v26 )
        {
          free(v26);
          v97 = 0;
        }
        v98 = 0;
LABEL_261:
        v8 = v87;
        v9 = v83;
        v10 = v80;
        v7 = v81;
        v12 = v84;
        v11 = v85;
LABEL_54:
        ++*v8;
        goto LABEL_2;
    }
  }
  if ( !a7 )
    goto LABEL_54;
  v75 = 0;
  if ( !v13 )
  {
    v13 = v9;
    v88[0] = v9;
    v75 = 1;
  }
  v109 = 0;
  v110 = 0;
  v65 = 0;
  v107 = 0;
  v108 = 0;
  phkResult = 0;
  v66 = 0;
  v82 = 0;
  StringAtLoc = ATL::CRegistryVirtualMachine::GetStringAtLoc(
                  (__int64)v10,
                  (__int64)v7,
                  v18,
                  (__int64)&v109,
                  (LPWSTR *)&phkResult);
  if ( StringAtLoc >= 0 && v16 )
  {
    StringAtLoc = ATL::CRegistryVirtualMachine::GetStringAtLoc(
                    (__int64)v80,
                    (__int64)v81,
                    v16,
                    (__int64)&v107,
                    (LPWSTR *)&v82);
    v65 = v107;
    v66 = v82;
  }
  v117 = 0;
  v118 = 0;
  v67 = v83;
  if ( !v16 )
    v67 = v13;
  v116 = v67;
  v22 = v109;
  v68 = (const BYTE *)v109;
  if ( phkResult )
    v68 = (const BYTE *)phkResult;
  if ( v16 )
  {
    v69 = v65;
    if ( v66 )
      v69 = v66;
  }
  else
  {
    v69 = 0;
  }
  if ( !v68 )
    ATL::AtlThrowImpl(-2147467259);
  v70 = -1;
  do
    ++v70;
  while ( *(_WORD *)&v68[2 * v70] );
  v71 = RegSetValueExW(v67, v69, 0, 1u, v68, 2 * v70 + 2);
  if ( !v71 )
  {
    if ( v75 )
      v13 = 0;
    v88[0] = v13;
    if ( v65 )
    {
      free(v65);
      v107 = 0;
    }
    v108 = 0;
    if ( v22 )
    {
      free(v22);
      v109 = 0;
    }
    v110 = 0;
    goto LABEL_261;
  }
  v25 = ATL::AtlHresultFromWin32(v71);
  if ( v65 )
    free(v65);
LABEL_40:
  if ( v22 )
    free(v22);
  if ( v13 )
    RegCloseKey(v13);
  return v25;
}

```

## disassembly

```asm
0x180012b04  push    rbx
0x180012b06  push    rsi
0x180012b07  push    rdi
0x180012b08  push    r12
0x180012b0a  push    r13
0x180012b0c  push    r14
0x180012b0e  push    r15
0x180012b10  sub     rsp, 9E0h
0x180012b17  mov     [rsp+0A18h+var_878], 0FFFFFFFFFFFFFFFEh
0x180012b23  mov     rax, cs:__security_cookie
0x180012b2a  xor     rax, rsp
0x180012b2d  mov     [rsp+0A18h+var_48], rax
0x180012b35  mov     r11, r9
0x180012b38  mov     [rsp+0A18h+var_9B8], r9
0x180012b3d  mov     r15, r8
0x180012b40  mov     [rsp+0A18h+var_988], r8
0x180012b48  mov     r13, rdx
0x180012b4b  mov     [rsp+0A18h+var_9A8], rdx
0x180012b50  mov     r10, rcx
0x180012b53  mov     [rsp+0A18h+var_9C0], rcx
0x180012b58  mov     [rsp+0A18h+var_8B0], rcx
0x180012b60  mov     [rsp+0A18h+var_8B8], rdx
0x180012b68  mov     [rsp+0A18h+var_8A8], r8
0x180012b70  mov     [rsp+0A18h+var_8A0], r9
0x180012b78  mov     r9, [rsp+0A18h+arg_20]
0x180012b80  mov     [rsp+0A18h+var_998], r9
0x180012b88  mov     r8, [rsp+0A18h+arg_28]
0x180012b90  mov     [rsp+0A18h+var_9A0], r8
0x180012b95  xor     edi, edi
0x180012b97  mov     esi, edi
0x180012b99  mov     [rsp+0A18h+var_980], rdi
0x180012ba1  mov     [rsp+0A18h+var_978], rdi
0x180012ba9  mov     [rsp+0A18h+var_970], rdi
0x180012bb1  mov     r12d, edi
0x180012bb4  mov     [rsp+0A18h+var_9D7], dil
0x180012bb9  mov     [rsp+0A18h+var_968], edi
0x180012bc0  mov     [rsp+0A18h+var_870], rdi
0x180012bc8  mov     rax, [r15]
0x180012bcb  mov     ebx, [rax]
0x180012bcd  mov     r14d, ebx
0x180012bd0  mov     ecx, 3FFFh
0x180012bd5  shr     r14d, 0Eh
0x180012bd9  mov     eax, ebx
0x180012bdb  and     r14d, ecx
0x180012bde  shr     eax, 1Ch
0x180012be1  mov     [rsp+0A18h+var_9C8], r14d
0x180012be6  and     ebx, ecx
0x180012be8  cmp     eax, 6
0x180012beb  jz      loc_180013BE5
0x180012bf1  mov     ecx, eax
0x180012bf3  ja      loc_180012EF8
0x180012bf9  test    eax, eax
0x180012bfb  jz      loc_180012EE3
0x180012c01  sub     ecx, 1
0x180012c04  jz      loc_180012E87
0x180012c0a  sub     ecx, 1
0x180012c0d  jz      loc_180012D19
0x180012c13  sub     ecx, 1
0x180012c16  jz      loc_180012CAC
0x180012c1c  cmp     ecx, 2
0x180012c1f  jnz     short loc_180012BE8
0x180012c21  add     qword ptr [r15], 4
0x180012c25  mov     r14d, [rsp+0A18h+arg_30]
0x180012c2d  mov     [rsp+0A18h+var_9E8], r14d; int
0x180012c32  mov     qword ptr [rsp+0A18h+cbData], r8; struct ATL::RGSBinary *
0x180012c37  mov     [rsp+0A18h+phkResult], r9; struct ATL::RGSDWORD *
0x180012c3c  mov     r9, r11; struct ATL::RGSStrings *
0x180012c3f  mov     r8, r15; unsigned int **
0x180012c42  mov     rdx, rsi; HKEY
0x180012c45  mov     rcx, r10; this
0x180012c48  call    ?VMUpdateRegistryRecurse@CRegistryVirtualMachine@ATL@@QEAAJPEAUHKEY__@@AEAPEAKPEAURGSStrings@2@PEAURGSDWORD@2@PEAURGSBinary@2@H@Z; ATL::CRegistryVirtualMachine::VMUpdateRegistryRecurse(HKEY__ *,ulong * &,ATL::RGSStrings *,ATL::RGSDWORD *,ATL::RGSBinary *,int)
0x180012c4d  mov     r12d, eax
0x180012c50  test    eax, eax
0x180012c52  js      loc_180013BE9
0x180012c58  mov     rax, [r15]
0x180012c5b  mov     ebx, [rax]
0x180012c5d  test    r14d, r14d
0x180012c60  jnz     loc_180012E6B
0x180012c66  cmp     [rsp+0A18h+var_9D7], dil
0x180012c6b  jnz     short loc_180012CA2
0x180012c6d  mov     r8d, [rsp+0A18h+var_968]
0x180012c75  shr     r8d, 0Eh
0x180012c79  and     r8d, 3FFFh; unsigned int
0x180012c80  mov     r9, [rsp+0A18h+var_9B8]; struct ATL::RGSStrings *
0x180012c85  mov     rdx, r13; HKEY
0x180012c88  mov     rcx, [rsp+0A18h+var_9C0]; this
0x180012c8d  call    ?DeleteKeyWithReplacement@CRegistryVirtualMachine@ATL@@QEAAJPEAUHKEY__@@KPEAURGSStrings@2@@Z; ATL::CRegistryVirtualMachine::DeleteKeyWithReplacement(HKEY__ *,ulong,ATL::RGSStrings *)
0x180012c92  mov     r12d, eax
0x180012c95  test    eax, eax
0x180012c97  jns     loc_180012E6B
0x180012c9d  jmp     loc_180013BE9
0x180012ca2  mov     [rsp+0A18h+var_9D7], dil
0x180012ca7  jmp     loc_180012E6B
0x180012cac  cmp     [rsp+0A18h+arg_30], edi
0x180012cb3  jnz     loc_180012D58
0x180012cb9  mov     [rsp+0A18h+var_9D0], rdi
0x180012cbe  mov     [rsp+0A18h+Block], rdi
0x180012cc6  mov     [rsp+0A18h+var_940], 0
0x180012cd2  lea     rax, [rsp+0A18h+var_9D0]
0x180012cd7  mov     [rsp+0A18h+phkResult], rax
0x180012cdc  lea     r9, [rsp+0A18h+Block]
0x180012ce4  mov     r8d, r14d
0x180012ce7  mov     rdx, r11
0x180012cea  mov     rcx, r10
0x180012ced  call    ?GetStringAtLoc@CRegistryVirtualMachine@ATL@@QEAAJPEAURGSStrings@2@KAEAV?$CSimpleArray@_WV?$CSimpleArrayEqualHelper@_W@ATL@@@2@PEAPEA_W@Z; ATL::CRegistryVirtualMachine::GetStringAtLoc(ATL::RGSStrings *,ulong,ATL::CSimpleArray<wchar_t,ATL::CSimpleArrayEqualHelper<wchar_t>> &,wchar_t * *)
0x180012cf2  mov     r12d, eax
0x180012cf5  test    eax, eax
0x180012cf7  jns     loc_180012D9D
0x180012cfd  mov     rcx, [rsp+0A18h+Block]; Block
0x180012d05  test    rcx, rcx
0x180012d08  jz      loc_180013BE9
0x180012d0e  call    cs:__imp_free
0x180012d14  jmp     loc_180013BE9
0x180012d19  cmp     [rsp+0A18h+arg_30], edi
0x180012d20  jz      short loc_180012CB9
0x180012d22  mov     r9, r11; struct ATL::RGSStrings *
0x180012d25  mov     r8d, r14d; unsigned int
0x180012d28  mov     rdx, r13; HKEY
0x180012d2b  mov     rcx, r10; this
0x180012d2e  call    ?DeleteKeyWithReplacement@CRegistryVirtualMachine@ATL@@QEAAJPEAUHKEY__@@KPEAURGSStrings@2@@Z; ATL::CRegistryVirtualMachine::DeleteKeyWithReplacement(HKEY__ *,ulong,ATL::RGSStrings *)
0x180012d33  mov     ebx, eax
0x180012d35  test    eax, eax
0x180012d37  jns     short loc_180012D4E
0x180012d39  test    rsi, rsi
0x180012d3c  jz      short loc_180012D47
0x180012d3e  mov     rcx, rsi; hKey
0x180012d41  call    cs:__imp_RegCloseKey
0x180012d47  mov     eax, ebx
0x180012d49  jmp     loc_180013BFA
0x180012d4e  mov     r10, [rsp+0A18h+var_9C0]
0x180012d53  mov     r11, [rsp+0A18h+var_9B8]
0x180012d58  mov     [rsp+0A18h+phkResult], r11; struct ATL::RGSStrings *
0x180012d5d  mov     r9d, r14d; unsigned int
0x180012d60  lea     r8, [rsp+0A18h+var_980]; struct ATL::CRegKey *
0x180012d68  mov     rdx, r13; HKEY
0x180012d6b  mov     rcx, r10; this
0x180012d6e  call    ?AddKeyWithReplacement@CRegistryVirtualMachine@ATL@@QEAAJPEAUHKEY__@@AEAVCRegKey@2@KPEAURGSStrings@2@@Z; ATL::CRegistryVirtualMachine::AddKeyWithReplacement(HKEY__ *,ATL::CRegKey &,ulong,ATL::RGSStrings *)
0x180012d73  mov     r12d, eax
0x180012d76  test    eax, eax
0x180012d78  jns     short loc_180012D90
0x180012d7a  mov     rcx, [rsp+0A18h+var_980]
0x180012d82  test    rcx, rcx
0x180012d85  jz      loc_180013BF7
0x180012d8b  jmp     loc_180013BF1
0x180012d90  mov     rsi, [rsp+0A18h+var_980]
0x180012d98  jmp     loc_180012E62
0x180012d9d  mov     rbx, [rsp+0A18h+Block]
0x180012da5  test    r13, r13
0x180012da8  jz      loc_180012E34
0x180012dae  mov     rdx, rbx
0x180012db1  cmp     [rsp+0A18h+var_9D0], rdi
0x180012db6  cmovnz  rdx, [rsp+0A18h+var_9D0]; lpSubKey
0x180012dbc  mov     [rsp+0A18h+var_9D0], rdi
0x180012dc1  lea     rax, [rsp+0A18h+var_9D0]
0x180012dc6  mov     [rsp+0A18h+phkResult], rax; phkResult
0x180012dcb  mov     r9d, 2001Fh; samDesired
0x180012dd1  xor     r8d, r8d; ulOptions
0x180012dd4  mov     rcx, r13; hKey
0x180012dd7  call    cs:__imp_RegOpenKeyExW
0x180012ddd  test    eax, eax
0x180012ddf  jnz     short loc_180012DFE
0x180012de1  mov     eax, edi
0x180012de3  test    rsi, rsi
0x180012de6  jz      short loc_180012DF1
0x180012de8  mov     rcx, rsi; hKey
0x180012deb  call    cs:__imp_RegCloseKey
0x180012df1  mov     rsi, [rsp+0A18h+var_9D0]
0x180012df6  mov     [rsp+0A18h+var_980], rsi
0x180012dfe  test    eax, 0FFFFFFFDh
0x180012e03  jz      short loc_180012E34
0x180012e05  mov     ecx, eax; unsigned int
0x180012e07  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180012e0c  mov     r14d, eax
0x180012e0f  test    rbx, rbx
0x180012e12  jz      short loc_180012E1E
0x180012e14  mov     rcx, rbx; Block
0x180012e17  call    cs:__imp_free
0x180012e1d  nop
0x180012e1e  test    rsi, rsi
0x180012e21  jz      short loc_180012E2C
0x180012e23  mov     rcx, rsi; hKey
0x180012e26  call    cs:__imp_RegCloseKey
0x180012e2c  mov     eax, r14d
0x180012e2f  jmp     loc_180013BFA
0x180012e34  mov     rax, [r15]
0x180012e37  mov     ecx, [rax]
0x180012e39  mov     [rsp+0A18h+var_968], ecx
0x180012e40  test    rbx, rbx
0x180012e43  jz      short loc_180012E56
0x180012e45  mov     rcx, rbx; Block
0x180012e48  call    cs:__imp_free
0x180012e4e  mov     [rsp+0A18h+Block], rdi
0x180012e56  mov     [rsp+0A18h+var_940], 0
0x180012e62  add     qword ptr [r15], 4
0x180012e66  mov     rax, [r15]
0x180012e69  mov     ebx, [rax]
0x180012e6b  mov     r10, [rsp+0A18h+var_9C0]
0x180012e70  mov     r11, [rsp+0A18h+var_9B8]
0x180012e75  mov     r8, [rsp+0A18h+var_9A0]
0x180012e7a  mov     r9, [rsp+0A18h+var_998]
0x180012e82  jmp     loc_180012BCD
0x180012e87  cmp     [rsp+0A18h+arg_30], edi
0x180012e8e  jz      short loc_180012ED5
0x180012e90  mov     [rsp+0A18h+phkResult], r11; struct ATL::RGSStrings *
0x180012e95  mov     r9d, r14d; unsigned int
0x180012e98  lea     r8, [rsp+0A18h+var_980]; struct ATL::CRegKey *
0x180012ea0  mov     rdx, r13; HKEY
0x180012ea3  mov     rcx, r10; this
0x180012ea6  call    ?AddKeyWithReplacement@CRegistryVirtualMachine@ATL@@QEAAJPEAUHKEY__@@AEAVCRegKey@2@KPEAURGSStrings@2@@Z; ATL::CRegistryVirtualMachine::AddKeyWithReplacement(HKEY__ *,ATL::CRegKey &,ulong,ATL::RGSStrings *)
0x180012eab  mov     r12d, eax
0x180012eae  test    eax, eax
0x180012eb0  js      loc_180012D7A
0x180012eb6  mov     rsi, [rsp+0A18h+var_980]
0x180012ebe  mov     r10, [rsp+0A18h+var_9C0]
0x180012ec3  mov     r11, [rsp+0A18h+var_9B8]
0x180012ec8  mov     r8, [rsp+0A18h+var_9A0]
0x180012ecd  mov     r9, [rsp+0A18h+var_998]
0x180012ed5  mov     [rsp+0A18h+var_9D7], 1
0x180012eda  add     qword ptr [r15], 4
0x180012ede  jmp     loc_180012BC8
0x180012ee3  test    rsi, rsi
0x180012ee6  jz      short loc_180012EF1
0x180012ee8  mov     rcx, rsi; hKey
0x180012eeb  call    cs:__imp_RegCloseKey
0x180012ef1  xor     eax, eax
0x180012ef3  jmp     loc_180013BFA
0x180012ef8  sub     ecx, 7
0x180012efb  jz      loc_180013BAD
0x180012f01  sub     ecx, 1
0x180012f04  jz      loc_1800139C8
0x180012f0a  sub     ecx, 1
0x180012f0d  jz      loc_180013607
0x180012f13  sub     ecx, 1
0x180012f16  jz      loc_180013371
0x180012f1c  cmp     ecx, 1
0x180012f1f  jnz     loc_180012BE8
0x180012f25  cmp     [rsp+0A18h+arg_30], edi
0x180012f2c  jz      short loc_180012EDA
0x180012f2e  mov     [rsp+0A18h+var_9D8], dil
0x180012f33  test    rsi, rsi
0x180012f36  jnz     short loc_180012F47
0x180012f38  mov     rsi, r13
0x180012f3b  mov     [rsp+0A18h+var_980], r13
0x180012f43  mov     [rsp+0A18h+var_9D8], cl
0x180012f47  mov     r15, rdi
0x180012f4a  mov     [rsp+0A18h+var_928], rdi
0x180012f52  mov     [rsp+0A18h+var_920], 0
0x180012f5e  mov     r13, rdi
0x180012f61  mov     [rsp+0A18h+lpValueName], rdi
0x180012f69  mov     [rsp+0A18h+var_930], 0
0x180012f75  mov     [rsp+0A18h+var_950], rdi
0x180012f7d  mov     [rsp+0A18h+var_9B0], rdi
0x180012f82  mov     [rsp+0A18h+var_868], rdi
0x180012f8a  mov     eax, ebx
0x180012f8c  add     rax, rax
0x180012f8f  mov     ecx, [r8+rax*8+8]
0x180012f94  mov     [rsp+0A18h+pulOut], ecx
0x180012f98  cmp     byte ptr [r8+rax*8+0Ch], 1
0x180012f9e  jnz     loc_18001328B
0x180012fa4  lea     rax, [rsp+0A18h+var_950]
0x180012fac  mov     [rsp+0A18h+phkResult], rax
0x180012fb1  lea     r9, [rsp+0A18h+var_928]
0x180012fb9  mov     r8d, ecx
0x180012fbc  mov     rdx, r11
0x180012fbf  mov     rcx, r10
0x180012fc2  call    ?GetStringAtLoc@CRegistryVirtualMachine@ATL@@QEAAJPEAURGSStrings@2@KAEAV?$CSimpleArray@_WV?$CSimpleArrayEqualHelper@_W@ATL@@@2@PEAPEA_W@Z; ATL::CRegistryVirtualMachine::GetStringAtLoc(ATL::RGSStrings *,ulong,ATL::CSimpleArray<wchar_t,ATL::CSimpleArrayEqualHelper<wchar_t>> &,wchar_t * *)
0x180012fc7  mov     r15, [rsp+0A18h+var_928]
0x180012fcf  mov     rax, [rsp+0A18h+var_950]
0x180012fd7  test    rax, rax
0x180012fda  cmovz   rax, r15
0x180012fde  mov     [rsp+0A18h+var_950], rax
0x180012fe6  or      r8, 0FFFFFFFFFFFFFFFFh
0x180012fea  mov     rcx, r8
0x180012fed  inc     rcx
0x180012ff0  cmp     [rax+rcx*2], di
0x180012ff4  jnz     short loc_180012FED
0x180012ff6  mov     [rsp+0A18h+var_898], rcx
0x180012ffe  mov     [rsp+0A18h+var_908], ecx
0x180013005  test    cl, 1
0x180013008  jz      short loc_18001302F
0x18001300a  lea     rax, [rsp+0A18h+var_860]
0x180013012  cmp     [rsp+0A18h+var_868], rax
0x18001301a  jz      short loc_18001302A
0x18001301c  lea     rcx, [rsp+0A18h+var_868]
0x180013024  call    ?FreeHeap@?$CTempBuffer@E$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<uchar,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180013029  nop
0x18001302a  jmp     loc_1800134B6
0x18001302f  mov     eax, ecx
0x180013031  cdq
0x180013032  sub     eax, edx
0x180013034  sar     eax, 1
0x180013036  mov     ecx, eax
0x180013038  mov     [rsp+0A18h+pulOut], ecx
0x18001303c  mov     ebx, ecx
0x18001303e  mov     [rsp+0A18h+var_900], rcx
0x180013046  test    eax, eax
0x180013048  jz      short loc_18001307F
0x18001304a  xor     edx, edx
0x18001304c  mov     rax, r8
0x18001304f  div     rbx
  ... truncated ...
```
