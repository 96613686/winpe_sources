# ScanRegKey(REGISTRY_SCAN_FUNC_ARGS *,HKEY__ *,RegQueItem,ushort const *,void *,bool)

- ea: `0x180024938`
- end: `0x18002526e`
- name: `?ScanRegKey@@YAJPEAUREGISTRY_SCAN_FUNC_ARGS@@PEAUHKEY__@@URegQueItem@@PEBGPEAX_N@Z`
- size: `2358`
- prototype: `__int64 __fastcall(struct REGISTRY_SCAN_FUNC_ARGS *, HKEY, const unsigned __int16 *, unsigned __int16 *, __int64, char)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002475c`

## callees

- `0x1800050f0`
- `0x18000563c`
- `0x180005c94`
- `0x18000eab8`
- `0x1800152d4`
- `0x180015bac`
- `0x180016f30`
- `0x18001f218`
- `0x18001f334`
- `0x18001f66c`
- `0x180020104`
- `0x18002057c`
- `0x180023aa4`
- `0x180023cdc`
- `0x180023e3c`
- `0x180024150`
- `0x18002415c`
- `0x180024200`
- `0x18002425c`
- `0x180024278`
- `0x1800244d4`
- `0x1800245a0`
- `0x180024660`
- `0x180024938`
- `0x180025274`
- `0x180025388`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800250b5`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18002512f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800250b5`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18002512f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180024ba6`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180024ba6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024de6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800251bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025235`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024de6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800251bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025235`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002501a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002501a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180024d6f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180024d6f`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180024fc3`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180024fc3`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180024c63`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180024c63`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024bed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024dc3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024bed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024dc3`

## pseudocode

```c
__int64 __fastcall ScanRegKey(
        struct REGISTRY_SCAN_FUNC_ARGS *a1,
        HKEY a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        __int64 a5,
        char a6)
{
  const unsigned __int16 *v6; // r14
  HKEY v7; // r15
  signed int v9; // esi
  __int64 v10; // rcx
  unsigned __int64 v11; // rdx
  __int64 v12; // rdi
  __int64 v13; // rbx
  __int64 v14; // rax
  __int64 v15; // rcx
  _OWORD *v16; // rax
  WCHAR *v17; // rcx
  __int64 v18; // rdx
  unsigned __int16 *v19; // rcx
  WCHAR *v20; // rax
  __int64 v21; // rdx
  int v22; // eax
  int v23; // eax
  LSTATUS v24; // eax
  LSTATUS v25; // eax
  bool v26; // sf
  DWORD i; // edi
  _OWORD *v28; // rcx
  WCHAR *v29; // rax
  __int64 v30; // rdx
  LSTATUS v31; // eax
  LSTATUS v32; // eax
  bool v33; // sf
  __int64 v34; // rdx
  unsigned __int64 v35; // rcx
  __int64 v36; // r14
  __int64 v37; // rbx
  __int64 v38; // rax
  __int64 v39; // rcx
  DWORD v40; // r14d
  wchar_t *v41; // rdi
  void *v42; // r15
  _OWORD *v43; // rcx
  WCHAR *v44; // rax
  __int64 v45; // rdx
  LSTATUS v46; // eax
  unsigned int v47; // r9d
  LSTATUS v48; // eax
  unsigned __int64 v49; // r9
  unsigned __int16 *v50; // rbx
  int v51; // eax
  int v52; // eax
  int v53; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  PHKEY phkResulta; // [rsp+20h] [rbp-E0h]
  PHKEY phkResultb; // [rsp+20h] [rbp-E0h]
  LPDWORD lpcbMaxSubKeyLen; // [rsp+28h] [rbp-D8h]
  LPDWORD lpcbMaxValueNameLen; // [rsp+40h] [rbp-C0h]
  unsigned __int16 *v60; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  DWORD cchName[2]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v63; // [rsp+78h] [rbp-88h] BYREF
  wchar_t *Source; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v65; // [rsp+88h] [rbp-78h] BYREF
  DWORD Type; // [rsp+90h] [rbp-70h] BYREF
  DWORD cSubKeys; // [rsp+94h] [rbp-6Ch] BYREF
  DWORD cValues; // [rsp+98h] [rbp-68h] BYREF
  HKEY v69; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v70; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v71; // [rsp+B8h] [rbp-48h]
  __int64 v72; // [rsp+C0h] [rbp-40h]
  __int64 v73; // [rsp+C8h] [rbp-38h]
  int v74; // [rsp+D0h] [rbp-30h]
  DWORD cchValueName; // [rsp+D4h] [rbp-2Ch] BYREF
  DWORD cbData; // [rsp+D8h] [rbp-28h] BYREF
  const unsigned __int16 *v77; // [rsp+E0h] [rbp-20h]
  HKEY v78; // [rsp+E8h] [rbp-18h]
  unsigned __int16 *v79; // [rsp+F0h] [rbp-10h]
  _BYTE v80[528]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 v81[264]; // [rsp+310h] [rbp+210h] BYREF
  WCHAR SubKey[264]; // [rsp+520h] [rbp+420h] BYREF
  unsigned __int16 v83[264]; // [rsp+730h] [rbp+630h] BYREF
  WCHAR Name[512]; // [rsp+940h] [rbp+840h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D98h] [rbp+C98h]

  v79 = a4;
  v6 = a3;
  v77 = a3;
  v7 = a2;
  v78 = a2;
  v74 = 0;
  v9 = 0;
  v70 = 0;
  v71 = 0;
  v72 = 0;
  v73 = 0;
  std::_Container_base12::_Alloc_proxy<std::allocator<std::_Container_proxy>>(&v70);
  v10 = v73;
  v11 = v71;
  if ( v71 <= v73 + 1 )
  {
    std::deque<RegQueItem>::_Growmap(&v70);
    v10 = v73;
    v11 = v71;
  }
  v72 &= v11 - 1;
  v12 = v72 + v10;
  v13 = std::deque<RegQueItem>::_Getblock(&v70, v72 + v10);
  if ( !*(_QWORD *)(*((_QWORD *)&v70 + 1) + 8 * v13) )
    *(_QWORD *)(*((_QWORD *)&v70 + 1) + 8 * v13) = std::_Allocate<16,std::_Default_allocate_traits>(520);
  v14 = std::_Deque_val<std::_Deque_simple_types<RegQueItem>>::_Address_subscript(&v70, v12);
  std::_Default_allocator_traits<std::allocator<RegQueItem>>::construct<RegQueItem,RegQueItem const &>(v15, v14, v6);
  ++v73;
  hKey = 0;
LABEL_6:
  while ( 2 )
  {
    if ( v73 )
    {
      std::make_unique<unsigned short [0],0>(&Source, 0x4000);
      std::make_unique<unsigned short [0],0>(&v60, 0x4000);
      v16 = (_OWORD *)std::queue<std::pair<DirQueItem,DirQueItem>>::front(&v70);
      v17 = SubKey;
      v18 = 4;
      do
      {
        *(_OWORD *)v17 = *v16;
        *((_OWORD *)v17 + 1) = v16[1];
        *((_OWORD *)v17 + 2) = v16[2];
        *((_OWORD *)v17 + 3) = v16[3];
        *((_OWORD *)v17 + 4) = v16[4];
        *((_OWORD *)v17 + 5) = v16[5];
        *((_OWORD *)v17 + 6) = v16[6];
        *((_OWORD *)v17 + 7) = v16[7];
        v17 += 64;
        v16 += 8;
        --v18;
      }
      while ( v18 );
      *(_QWORD *)v17 = *(_QWORD *)v16;
      memset_0(v81, 0, 0x208u);
      std::deque<DirQueItem>::pop_front(&v70);
      hKey = 0;
      v19 = v83;
      v20 = SubKey;
      v21 = 4;
      do
      {
        *(_OWORD *)v19 = *(_OWORD *)v20;
        *((_OWORD *)v19 + 1) = *((_OWORD *)v20 + 1);
        *((_OWORD *)v19 + 2) = *((_OWORD *)v20 + 2);
        *((_OWORD *)v19 + 3) = *((_OWORD *)v20 + 3);
        *((_OWORD *)v19 + 4) = *((_OWORD *)v20 + 4);
        *((_OWORD *)v19 + 5) = *((_OWORD *)v20 + 5);
        *((_OWORD *)v19 + 6) = *((_OWORD *)v20 + 6);
        *((_OWORD *)v19 + 7) = *((_OWORD *)v20 + 7);
        v19 += 64;
        v20 += 64;
        --v21;
      }
      while ( v21 );
      *(_QWORD *)v19 = *(_QWORD *)v20;
      v9 = CheckRegScanTaskCancelled(a5, a1, v83);
      if ( v9 >= 0 )
      {
        v69 = 0;
        v22 = CompactFullPath(SubKey, v6, v79, (unsigned __int16 **)&v69);
        if ( v22 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x22F,
            (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\regscanner.cpp",
            (const char *)(unsigned int)v22,
            (int)phkResult);
LABEL_15:
          std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v60);
          std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&Source);
          continue;
        }
        v23 = _o_wcscpy_s(v81, 512, v69);
        if ( (int)HrFromErrno(v23) < 0 )
          goto LABEL_15;
        v24 = RegOpenKeyExW(v7, SubKey, 0, 0x20019u, &hKey);
        v9 = v24;
        if ( v24 > 0 )
          v9 = (unsigned __int16)v24 | 0x80070000;
        if ( v9 < 0 )
        {
          RecordRegScanFailures(a1, v81, v9, 0x81u);
          goto LABEL_15;
        }
        cSubKeys = 0;
        cValues = 0;
        v25 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, &cValues, 0, 0, 0, 0);
        v26 = v25 < 0;
        if ( v25 > 0 )
          v26 = 1;
        if ( v26 )
          goto LABEL_15;
        if ( a6 )
        {
          for ( i = 0; i < cSubKeys; ++i )
          {
            memset_0(Name, 0, sizeof(Name));
            cchName[0] = 512;
            memset_0(v83, 0, 0x208u);
            v69 = 0;
            v28 = v80;
            v29 = SubKey;
            v30 = 4;
            do
            {
              *v28 = *(_OWORD *)v29;
              v28[1] = *((_OWORD *)v29 + 1);
              v28[2] = *((_OWORD *)v29 + 2);
              v28[3] = *((_OWORD *)v29 + 3);
              v28[4] = *((_OWORD *)v29 + 4);
              v28[5] = *((_OWORD *)v29 + 5);
              v28[6] = *((_OWORD *)v29 + 6);
              v28[7] = *((_OWORD *)v29 + 7);
              v28 += 8;
              v29 += 64;
              --v30;
            }
            while ( v30 );
            *(_QWORD *)v28 = *(_QWORD *)v29;
            v9 = CheckRegScanTaskCancelled(a5, a1, v80);
            if ( v9 < 0 )
              goto LABEL_75;
            v31 = RegEnumKeyExW(hKey, i, Name, cchName, 0, 0, 0, 0);
            v9 = v31;
            if ( v31 > 0 )
              v9 = (unsigned __int16)v31 | 0x80070000;
            if ( v9 >= 0 )
            {
              v32 = RegOpenKeyExW(hKey, Name, 0, 0x20019u, &v69);
              v33 = v32 < 0;
              if ( v32 > 0 )
                v33 = 1;
              if ( !v33 )
              {
                if ( v69 )
                {
                  RegCloseKey(v69);
                  v69 = 0;
                }
                if ( StringCchPrintfW(v83, 0x200u, L"%s\\%s", SubKey, Name) >= 0 )
                {
                  v34 = v73;
                  v35 = v71;
                  if ( v71 <= v73 + 1 )
                  {
                    std::deque<RegQueItem>::_Growmap(&v70);
                    v34 = v73;
                    v35 = v71;
                  }
                  v72 &= v35 - 1;
                  v36 = v72 + v34;
                  v37 = std::deque<RegQueItem>::_Getblock(&v70, v72 + v34);
                  if ( !*(_QWORD *)(*((_QWORD *)&v70 + 1) + 8 * v37) )
                    *(_QWORD *)(*((_QWORD *)&v70 + 1) + 8 * v37) = std::_Allocate<16,std::_Default_allocate_traits>(520);
                  v38 = std::_Deque_val<std::_Deque_simple_types<RegQueItem>>::_Address_subscript(&v70, v36);
                  std::_Default_allocator_traits<std::allocator<RegQueItem>>::construct<RegQueItem,RegQueItem const &>(
                    v39,
                    v38,
                    v83);
                  ++v73;
                }
              }
            }
            else
            {
              RecordRegScanFailures(a1, v81, v9, 0xA5u);
            }
          }
        }
        v40 = 0;
        v41 = Source;
        while ( 1 )
        {
          if ( v40 >= cValues )
          {
            phkResult = (PHKEY)L"@@";
            if ( StringCchPrintfW(v60, 0x4000u, L"%s%s%s", v81) >= 0
              && (int)RecordRegScan(a1, v60, cValues, cSubKeys) >= 0
              && hKey )
            {
              RegCloseKey(hKey);
              hKey = 0;
            }
            std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v60);
            std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&Source);
            v6 = v77;
            v7 = v78;
            goto LABEL_6;
          }
          v42 = operator new[](0x8000u);
          memset_0(v42, 0, 0x8000u);
          *(_QWORD *)cchName = v42;
          cbData = 0x8000;
          memset_0(Name, 0, sizeof(Name));
          cchValueName = 512;
          Type = 0;
          std::make_unique<unsigned short [0],0>(&v65, 0x4000);
          std::make_unique<unsigned short [0],0>(&v63, 0x4000);
          v43 = v80;
          v44 = SubKey;
          v45 = 4;
          do
          {
            *v43 = *(_OWORD *)v44;
            v43[1] = *((_OWORD *)v44 + 1);
            v43[2] = *((_OWORD *)v44 + 2);
            v43[3] = *((_OWORD *)v44 + 3);
            v43[4] = *((_OWORD *)v44 + 4);
            v43[5] = *((_OWORD *)v44 + 5);
            v43[6] = *((_OWORD *)v44 + 6);
            v43[7] = *((_OWORD *)v44 + 7);
            v43 += 8;
            v44 += 64;
            --v45;
          }
          while ( v45 );
          *(_QWORD *)v43 = *(_QWORD *)v44;
          v9 = CheckRegScanTaskCancelled(a5, a1, v80);
          if ( v9 < 0 )
          {
            std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v63);
            std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v65);
            std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(cchName);
            goto LABEL_75;
          }
          v74 |= 1u;
          v46 = RegEnumValueW(hKey, v40, Name, &cchValueName, 0, 0, 0, 0);
          v9 = v46;
          if ( v46 > 0 )
            v9 = (unsigned __int16)v46 | 0x80070000;
          if ( v9 < 0 )
            break;
          v48 = RegQueryValueExW(hKey, Name, 0, &Type, (LPBYTE)v42, &cbData);
          v9 = v48;
          if ( v48 > 0 )
            v9 = (unsigned __int16)v48 | 0x80070000;
          if ( v9 < 0 )
          {
            v47 = 204;
            goto LABEL_54;
          }
          v50 = v65;
          v51 = ParseValueToWchar(Type, (unsigned __int8 *)v42, v65, v49, (unsigned __int64)phkResulta);
          v9 = v51;
          if ( v51 >= 0 )
          {
            if ( !v40
              || !v41
              || !wcsnlen_s(v41, 0x4000u)
              || (v52 = _o_wcscat_s(v41, 0x4000, L"?"), (int)HrFromErrno(v52) >= 0) )
            {
              LODWORD(lpcbMaxValueNameLen) = 59;
              LODWORD(lpcbMaxSubKeyLen) = 59;
              LODWORD(phkResultb) = Type;
              if ( StringCchPrintfW(
                     v63,
                     0x4000u,
                     L"%s%d%c%s%s%c%s%s",
                     L"T:",
                     phkResultb,
                     lpcbMaxSubKeyLen,
                     L"K:",
                     Name,
                     lpcbMaxValueNameLen,
                     L"V:",
                     v50) >= 0 )
              {
                v53 = _o_wcscat_s(v41, 0x4000, v63);
                HrFromErrno(v53);
              }
            }
          }
          else
          {
            RecordRegScanFailures(a1, v81, v51, 0xCFu);
          }
LABEL_68:
          std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v63);
          std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v65);
          std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(cchName);
          ++v40;
        }
        v47 = 200;
LABEL_54:
        RecordRegScanFailures(a1, v81, v9, v47);
        goto LABEL_68;
      }
LABEL_75:
      std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v60);
      std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&Source);
    }
    break;
  }
  WriteRegDataBuffer(a1);
  WriteRegScanFailureBuffer(a1);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  std::deque<RegQueItem>::~deque<RegQueItem>(&v70);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180024938  push    rbp
0x18002493a  push    rbx
0x18002493b  push    rsi
0x18002493c  push    rdi
0x18002493d  push    r12
0x18002493f  push    r13
0x180024941  push    r14
0x180024943  push    r15
0x180024945  lea     rbp, [rsp-0C58h]
0x18002494d  sub     rsp, 0D58h
0x180024954  mov     rax, cs:__security_cookie
0x18002495b  xor     rax, rsp
0x18002495e  mov     [rbp+0C90h+var_50], rax
0x180024965  mov     [rbp+0C90h+var_CA0], r9
0x180024969  mov     r14, r8
0x18002496c  mov     [rbp+0C90h+var_CB0], r8
0x180024970  mov     r15, rdx
0x180024973  mov     [rbp+0C90h+var_CA8], rdx
0x180024977  mov     r12, rcx
0x18002497a  mov     r13, [rbp+0C90h+arg_20]
0x180024981  xor     eax, eax
0x180024983  mov     [rbp+0C90h+var_CC0], eax
0x180024986  mov     esi, eax
0x180024988  xorps   xmm0, xmm0
0x18002498b  movdqu  [rbp+0C90h+var_CE8], xmm0
0x180024990  mov     [rbp+0C90h+var_CD8], rax
0x180024994  mov     [rbp+0C90h+var_CD0], rax
0x180024998  mov     [rbp+0C90h+var_CC8], rax
0x18002499c  lea     rcx, [rbp+0C90h+var_CE8]
0x1800249a0  call    ??$_Alloc_proxy@V?$allocator@U_Container_proxy@std@@@std@@@_Container_base12@std@@QEAAX$$QEAV?$allocator@U_Container_proxy@std@@@1@@Z; std::_Container_base12::_Alloc_proxy<std::allocator<std::_Container_proxy>>(std::allocator<std::_Container_proxy> &&)
0x1800249a5  nop
0x1800249a6  mov     rcx, [rbp+0C90h+var_CC8]
0x1800249aa  lea     rax, [rcx+1]
0x1800249ae  mov     rdx, [rbp+0C90h+var_CD8]
0x1800249b2  cmp     rdx, rax
0x1800249b5  ja      short loc_1800249C8
0x1800249b7  lea     rcx, [rbp+0C90h+var_CE8]
0x1800249bb  call    ?_Growmap@?$deque@URegQueItem@@V?$allocator@URegQueItem@@@std@@@std@@AEAAX_K@Z; std::deque<RegQueItem>::_Growmap(unsigned __int64)
0x1800249c0  mov     rcx, [rbp+0C90h+var_CC8]
0x1800249c4  mov     rdx, [rbp+0C90h+var_CD8]
0x1800249c8  lea     rax, [rdx-1]
0x1800249cc  and     rax, [rbp+0C90h+var_CD0]
0x1800249d0  mov     [rbp+0C90h+var_CD0], rax
0x1800249d4  lea     rdi, [rax+rcx]
0x1800249d8  mov     rdx, rdi
0x1800249db  lea     rcx, [rbp+0C90h+var_CE8]
0x1800249df  call    ?_Getblock@?$deque@URegQueItem@@V?$allocator@URegQueItem@@@std@@@std@@AEBA_J_K@Z; std::deque<RegQueItem>::_Getblock(unsigned __int64)
0x1800249e4  mov     rbx, rax
0x1800249e7  mov     rax, qword ptr [rbp+0C90h+var_CE8+8]
0x1800249eb  cmp     qword ptr [rax+rbx*8], 0
0x1800249f0  jnz     short loc_180024A07
0x1800249f2  mov     ecx, 208h
0x1800249f7  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800249fc  mov     rcx, rax
0x1800249ff  mov     rax, qword ptr [rbp+0C90h+var_CE8+8]
0x180024a03  mov     [rax+rbx*8], rcx
0x180024a07  mov     rdx, rdi
0x180024a0a  lea     rcx, [rbp+0C90h+var_CE8]
0x180024a0e  call    ?_Address_subscript@?$_Deque_val@U?$_Deque_simple_types@URegQueItem@@@std@@@std@@QEAAPEAURegQueItem@@_K@Z; std::_Deque_val<std::_Deque_simple_types<RegQueItem>>::_Address_subscript(unsigned __int64)
0x180024a13  mov     r8, r14
0x180024a16  mov     rdx, rax
0x180024a19  call    ??$construct@URegQueItem@@AEBU1@@?$_Default_allocator_traits@V?$allocator@URegQueItem@@@std@@@std@@SAXAEAV?$allocator@URegQueItem@@@1@QEAURegQueItem@@AEBU3@@Z; std::_Default_allocator_traits<std::allocator<RegQueItem>>::construct<RegQueItem,RegQueItem const &>(std::allocator<RegQueItem> &,RegQueItem * const,RegQueItem const &)
0x180024a1e  inc     [rbp+0C90h+var_CC8]
0x180024a22  xor     ebx, ebx
0x180024a24  mov     [rsp+0D90h+hKey], rbx
0x180024a29  mov     edi, 4000h
0x180024a2e  cmp     [rbp+0C90h+var_CC8], rbx
0x180024a32  jz      loc_18002521B
0x180024a38  mov     rdx, rdi
0x180024a3b  lea     rcx, [rbp+0C90h+Source]
0x180024a3f  call    ??$make_unique@$$BY0A@G$0A@@std@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@0@_K@Z; std::make_unique<ushort [0],0>(unsigned __int64)
0x180024a44  nop
0x180024a45  mov     rdx, rdi
0x180024a48  lea     rcx, [rsp+0D90h+var_D30]
0x180024a4d  call    ??$make_unique@$$BY0A@G$0A@@std@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@0@_K@Z; std::make_unique<ushort [0],0>(unsigned __int64)
0x180024a52  nop
0x180024a53  lea     rcx, [rbp+0C90h+var_CE8]
0x180024a57  call    ?front@?$queue@U?$pair@UDirQueItem@@U1@@std@@V?$deque@U?$pair@UDirQueItem@@U1@@std@@V?$allocator@U?$pair@UDirQueItem@@U1@@std@@@2@@2@@std@@QEAAAEAU?$pair@UDirQueItem@@U1@@2@XZ; std::queue<std::pair<DirQueItem,DirQueItem>>::front(void)
0x180024a5c  lea     rcx, [rbp+0C90h+SubKey]
0x180024a63  mov     edx, 4
0x180024a68  lea     esi, [rdx+7Ch]
0x180024a6b  movups  xmm0, xmmword ptr [rax]
0x180024a6e  movups  xmmword ptr [rcx], xmm0
0x180024a71  movups  xmm1, xmmword ptr [rax+10h]
0x180024a75  movups  xmmword ptr [rcx+10h], xmm1
0x180024a79  movups  xmm0, xmmword ptr [rax+20h]
0x180024a7d  movups  xmmword ptr [rcx+20h], xmm0
0x180024a81  movups  xmm1, xmmword ptr [rax+30h]
0x180024a85  movups  xmmword ptr [rcx+30h], xmm1
0x180024a89  movups  xmm0, xmmword ptr [rax+40h]
0x180024a8d  movups  xmmword ptr [rcx+40h], xmm0
0x180024a91  movups  xmm1, xmmword ptr [rax+50h]
0x180024a95  movups  xmmword ptr [rcx+50h], xmm1
0x180024a99  movups  xmm0, xmmword ptr [rax+60h]
0x180024a9d  movups  xmmword ptr [rcx+60h], xmm0
0x180024aa1  movups  xmm1, xmmword ptr [rax+70h]
0x180024aa5  movups  xmmword ptr [rcx+70h], xmm1
0x180024aa9  add     rcx, rsi
0x180024aac  add     rax, rsi
0x180024aaf  sub     rdx, 1; Val
0x180024ab3  jnz     short loc_180024A6B
0x180024ab5  mov     rax, [rax]
0x180024ab8  mov     [rcx], rax
0x180024abb  mov     r8d, 208h; Size
0x180024ac1  lea     rcx, [rbp+0C90h+var_A80]; void *
0x180024ac8  call    memset_0
0x180024acd  lea     rcx, [rbp+0C90h+var_CE8]
0x180024ad1  call    ?pop_front@?$deque@UDirQueItem@@V?$allocator@UDirQueItem@@@std@@@std@@QEAAXXZ; std::deque<DirQueItem>::pop_front(void)
0x180024ad6  mov     [rsp+0D90h+hKey], rbx
0x180024adb  lea     rcx, [rbp+0C90h+var_660]
0x180024ae2  lea     rax, [rbp+0C90h+SubKey]
0x180024ae9  mov     edx, 4
0x180024aee  movups  xmm0, xmmword ptr [rax]
0x180024af1  movups  xmmword ptr [rcx], xmm0
0x180024af4  movups  xmm1, xmmword ptr [rax+10h]
0x180024af8  movups  xmmword ptr [rcx+10h], xmm1
0x180024afc  movups  xmm0, xmmword ptr [rax+20h]
0x180024b00  movups  xmmword ptr [rcx+20h], xmm0
0x180024b04  movups  xmm1, xmmword ptr [rax+30h]
0x180024b08  movups  xmmword ptr [rcx+30h], xmm1
0x180024b0c  movups  xmm0, xmmword ptr [rax+40h]
0x180024b10  movups  xmmword ptr [rcx+40h], xmm0
0x180024b14  movups  xmm1, xmmword ptr [rax+50h]
0x180024b18  movups  xmmword ptr [rcx+50h], xmm1
0x180024b1c  movups  xmm0, xmmword ptr [rax+60h]
0x180024b20  movups  xmmword ptr [rcx+60h], xmm0
0x180024b24  movups  xmm1, xmmword ptr [rax+70h]
0x180024b28  movups  xmmword ptr [rcx+70h], xmm1
0x180024b2c  add     rcx, rsi
0x180024b2f  add     rax, rsi
0x180024b32  sub     rdx, 1
0x180024b36  jnz     short loc_180024AEE
0x180024b38  mov     rax, [rax]
0x180024b3b  mov     [rcx], rax
0x180024b3e  lea     r8, [rbp+0C90h+var_660]
0x180024b45  mov     rdx, r12
0x180024b48  mov     rcx, r13
0x180024b4b  call    ?CheckRegScanTaskCancelled@@YAJPEAXPEAUREGISTRY_SCAN_FUNC_ARGS@@URegQueItem@@@Z; CheckRegScanTaskCancelled(void *,REGISTRY_SCAN_FUNC_ARGS *,RegQueItem)
0x180024b50  mov     esi, eax
0x180024b52  test    eax, eax
0x180024b54  js      loc_180025207
0x180024b5a  mov     [rbp+0C90h+var_CF0], rbx
0x180024b5e  lea     r9, [rbp+0C90h+var_CF0]; unsigned __int16 **
0x180024b62  mov     r8, [rbp+0C90h+var_CA0]; unsigned __int16 *
0x180024b66  mov     rdx, r14; unsigned __int16 *
0x180024b69  lea     rcx, [rbp+0C90h+SubKey]; unsigned __int16 *
0x180024b70  call    ?CompactFullPath@@YAJPEBG00PEAPEAG@Z; CompactFullPath(ushort const *,ushort const *,ushort const *,ushort * *)
0x180024b75  test    eax, eax
0x180024b77  jns     short loc_180024B96
0x180024b79  mov     rcx, [rbp+0C98h]; this
0x180024b80  mov     r9d, eax; char *
0x180024b83  lea     r8, aOnecoreDrivers_3; "onecore\\drivers\\storage\\storsvc\\sto"...
0x180024b8a  mov     edx, 22Fh; void *
0x180024b8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024b94  jmp     short loc_180024BB7
0x180024b96  mov     r8, [rbp+0C90h+var_CF0]
0x180024b9a  mov     edx, 200h
0x180024b9f  lea     rcx, [rbp+0C90h+var_A80]
0x180024ba6  call    cs:__imp__o_wcscpy_s
0x180024bac  mov     ecx, eax; int
0x180024bae  call    ?HrFromErrno@@YAJH@Z; HrFromErrno(int)
0x180024bb3  test    eax, eax
0x180024bb5  jns     short loc_180024BD0
0x180024bb7  lea     rcx, [rsp+0D90h+var_D30]
0x180024bbc  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x180024bc1  nop
0x180024bc2  lea     rcx, [rbp+0C90h+Source]
0x180024bc6  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x180024bcb  jmp     loc_180024A2E
0x180024bd0  lea     rax, [rsp+0D90h+hKey]
0x180024bd5  mov     [rsp+0D90h+phkResult], rax; phkResult
0x180024bda  mov     r9d, 20019h; samDesired
0x180024be0  xor     r8d, r8d; ulOptions
0x180024be3  lea     rdx, [rbp+0C90h+SubKey]; lpSubKey
0x180024bea  mov     rcx, r15; hKey
0x180024bed  call    cs:__imp_RegOpenKeyExW
0x180024bf3  mov     esi, eax
0x180024bf5  test    eax, eax
0x180024bf7  jle     short loc_180024C02
0x180024bf9  movzx   esi, ax
0x180024bfc  or      esi, 80070000h
0x180024c02  test    esi, esi
0x180024c04  jns     short loc_180024C20
0x180024c06  mov     r9d, 81h; unsigned int
0x180024c0c  mov     r8d, esi; int
0x180024c0f  lea     rdx, [rbp+0C90h+var_A80]; unsigned __int16 *
0x180024c16  mov     rcx, r12; struct REGISTRY_SCAN_FUNC_ARGS *
0x180024c19  call    ?RecordRegScanFailures@@YAJPEAUREGISTRY_SCAN_FUNC_ARGS@@PEBGJI@Z; RecordRegScanFailures(REGISTRY_SCAN_FUNC_ARGS *,ushort const *,long,uint)
0x180024c1e  jmp     short loc_180024BB7
0x180024c20  mov     [rbp+0C90h+cSubKeys], ebx
0x180024c23  mov     [rbp+0C90h+cValues], ebx
0x180024c26  mov     [rsp+0D90h+lpftLastWriteTime], rbx; lpftLastWriteTime
0x180024c2b  mov     [rsp+0D90h+lpcbSecurityDescriptor], rbx; lpcbSecurityDescriptor
0x180024c30  mov     [rsp+0D90h+lpcbMaxValueLen], rbx; lpcbMaxValueLen
0x180024c35  mov     [rsp+0D90h+lpcbMaxValueNameLen], rbx; lpcbMaxValueNameLen
0x180024c3a  lea     rax, [rbp+0C90h+cValues]
0x180024c3e  mov     [rsp+0D90h+lpcValues], rax; lpcValues
0x180024c43  mov     [rsp+0D90h+lpcbMaxClassLen], rbx; lpcbMaxClassLen
0x180024c48  mov     [rsp+0D90h+lpcbMaxSubKeyLen], rbx; lpcbMaxSubKeyLen
0x180024c4d  lea     rax, [rbp+0C90h+cSubKeys]
0x180024c51  mov     [rsp+0D90h+phkResult], rax; lpcSubKeys
0x180024c56  xor     r9d, r9d; lpReserved
0x180024c59  xor     r8d, r8d; lpcchClass
0x180024c5c  xor     edx, edx; lpClass
0x180024c5e  mov     rcx, [rsp+0D90h+hKey]; hKey
0x180024c63  call    cs:__imp_RegQueryInfoKeyW
0x180024c69  test    eax, eax
0x180024c6b  jle     short loc_180024C77
0x180024c6d  movzx   eax, ax
0x180024c70  or      eax, 80070000h
0x180024c75  test    eax, eax
0x180024c77  js      loc_180024BB7
0x180024c7d  cmp     [rbp+0C90h+arg_28], bl
0x180024c83  jz      loc_180024EAA
0x180024c89  mov     edi, ebx
0x180024c8b  mov     r15d, 80h
0x180024c91  cmp     edi, [rbp+0C90h+cSubKeys]
0x180024c94  jnb     loc_180024EAA
0x180024c9a  xor     edx, edx; Val
0x180024c9c  mov     r8d, 400h; Size
0x180024ca2  lea     rcx, [rbp+0C90h+Name]; void *
0x180024ca9  call    memset_0
0x180024cae  mov     r14d, 200h
0x180024cb4  mov     [rsp+0D90h+cchName], r14d
0x180024cb9  xor     edx, edx; Val
0x180024cbb  lea     r8d, [r14+8]; Size
0x180024cbf  lea     rcx, [rbp+0C90h+var_660]; void *
0x180024cc6  call    memset_0
0x180024ccb  mov     [rbp+0C90h+var_CF0], rbx
0x180024ccf  lea     rcx, [rbp+0C90h+var_C90]
0x180024cd3  lea     rax, [rbp+0C90h+SubKey]
0x180024cda  mov     edx, 4
0x180024cdf  movups  xmm0, xmmword ptr [rax]
0x180024ce2  movups  xmmword ptr [rcx], xmm0
0x180024ce5  movups  xmm1, xmmword ptr [rax+10h]
0x180024ce9  movups  xmmword ptr [rcx+10h], xmm1
0x180024ced  movups  xmm0, xmmword ptr [rax+20h]
0x180024cf1  movups  xmmword ptr [rcx+20h], xmm0
0x180024cf5  movups  xmm1, xmmword ptr [rax+30h]
0x180024cf9  movups  xmmword ptr [rcx+30h], xmm1
0x180024cfd  movups  xmm0, xmmword ptr [rax+40h]
0x180024d01  movups  xmmword ptr [rcx+40h], xmm0
0x180024d05  movups  xmm1, xmmword ptr [rax+50h]
0x180024d09  movups  xmmword ptr [rcx+50h], xmm1
0x180024d0d  movups  xmm0, xmmword ptr [rax+60h]
0x180024d11  movups  xmmword ptr [rcx+60h], xmm0
0x180024d15  movups  xmm1, xmmword ptr [rax+70h]
0x180024d19  movups  xmmword ptr [rcx+70h], xmm1
0x180024d1d  add     rcx, r15
0x180024d20  add     rax, r15
0x180024d23  sub     rdx, 1
0x180024d27  jnz     short loc_180024CDF
0x180024d29  mov     rax, [rax]
0x180024d2c  mov     [rcx], rax
0x180024d2f  lea     r8, [rbp+0C90h+var_C90]
0x180024d33  mov     rdx, r12
0x180024d36  mov     rcx, r13
0x180024d39  call    ?CheckRegScanTaskCancelled@@YAJPEAXPEAUREGISTRY_SCAN_FUNC_ARGS@@URegQueItem@@@Z; CheckRegScanTaskCancelled(void *,REGISTRY_SCAN_FUNC_ARGS *,RegQueItem)
0x180024d3e  mov     esi, eax
0x180024d40  test    eax, eax
0x180024d42  js      loc_180025207
0x180024d48  mov     [rsp+0D90h+lpcValues], rbx; lpftLastWriteTime
0x180024d4d  mov     [rsp+0D90h+lpcbMaxClassLen], rbx; lpcchClass
0x180024d52  mov     [rsp+0D90h+lpcbMaxSubKeyLen], rbx; lpClass
0x180024d57  mov     [rsp+0D90h+phkResult], rbx; lpReserved
0x180024d5c  lea     r9, [rsp+0D90h+cchName]; lpcchName
0x180024d61  lea     r8, [rbp+0C90h+Name]; lpName
0x180024d68  mov     edx, edi; dwIndex
0x180024d6a  mov     rcx, [rsp+0D90h+hKey]; hKey
0x180024d6f  call    cs:__imp_RegEnumKeyExW
0x180024d75  mov     esi, eax
0x180024d77  test    eax, eax
0x180024d79  jle     short loc_180024D84
0x180024d7b  movzx   esi, ax
0x180024d7e  or      esi, 80070000h
0x180024d84  test    esi, esi
0x180024d86  jns     short loc_180024DA5
0x180024d88  mov     r9d, 0A5h; unsigned int
0x180024d8e  mov     r8d, esi; int
0x180024d91  lea     rdx, [rbp+0C90h+var_A80]; unsigned __int16 *
0x180024d98  mov     rcx, r12; struct REGISTRY_SCAN_FUNC_ARGS *
0x180024d9b  call    ?RecordRegScanFailures@@YAJPEAUREGISTRY_SCAN_FUNC_ARGS@@PEBGJI@Z; RecordRegScanFailures(REGISTRY_SCAN_FUNC_ARGS *,ushort const *,long,uint)
0x180024da0  jmp     loc_180024EA3
0x180024da5  lea     rax, [rbp+0C90h+var_CF0]
0x180024da9  mov     [rsp+0D90h+phkResult], rax; phkResult
0x180024dae  mov     r9d, 20019h; samDesired
0x180024db4  xor     r8d, r8d; ulOptions
0x180024db7  lea     rdx, [rbp+0C90h+Name]; lpSubKey
0x180024dbe  mov     rcx, [rsp+0D90h+hKey]; hKey
0x180024dc3  call    cs:__imp_RegOpenKeyExW
0x180024dc9  test    eax, eax
0x180024dcb  jle     short loc_180024DD7
0x180024dcd  movzx   eax, ax
0x180024dd0  or      eax, 80070000h
0x180024dd5  test    eax, eax
0x180024dd7  js      loc_180024EA3
0x180024ddd  mov     rcx, [rbp+0C90h+var_CF0]; hKey
0x180024de1  test    rcx, rcx
0x180024de4  jz      short loc_180024DF0
0x180024de6  call    cs:__imp_RegCloseKey
  ... truncated ...
```
