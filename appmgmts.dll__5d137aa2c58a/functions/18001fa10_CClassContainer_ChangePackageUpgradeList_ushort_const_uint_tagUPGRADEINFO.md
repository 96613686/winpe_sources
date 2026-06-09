# CClassContainer::ChangePackageUpgradeList(ushort const *,uint,tagUPGRADEINFO *)

- ea: `0x18001fa10`
- end: `0x180020171`
- name: `?ChangePackageUpgradeList@CClassContainer@@UEAAJPEBGIPEAUtagUPGRADEINFO@@@Z`
- size: `1889`
- prototype: `__int64 __fastcall(CClassContainer *this, const unsigned __int16 *, unsigned int, struct tagUPGRADEINFO *)`
- caller_count: `0`
- callee_count: `17`
- tags: `installer_update`

## callees

- `0x1800016d0`
- `0x180008f58`
- `0x18001d130`
- `0x18001e82c`
- `0x18001fa10`
- `0x180021fa0`
- `0x180023448`
- `0x18002350c`
- `0x180024218`
- `0x180024260`
- `0x18002435c`
- `0x180024458`
- `0x180024b90`
- `0x180024d54`
- `0x180024e04`
- `0x180026f3c`
- `0x18002c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18001fd0b`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18001fd0b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002008e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002009d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800200ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800200e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002010f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002011d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002012c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002013a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002008e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002009d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800200ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800200e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002010f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002011d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002012c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002013a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001fc50`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001fc6f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001fc81`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001feca`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ff28`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001fc50`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001fc6f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001fc81`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001feca`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ff28`
- `adsldpc!ADSIGetObjectAttributes` at `0x18001fb96`
- `adsldpc!ADSIGetObjectAttributes` at `0x18001fb96`
- `adsldpc!ADSICloseDSObject` at `0x1800200bf`
- `adsldpc!ADSICloseDSObject` at `0x1800200bf`
- `adsldpc!ADSISetObjectAttributes` at `0x180020056`
- `adsldpc!ADSISetObjectAttributes` at `0x180020056`
- `adsldpc!FreeADsMem` at `0x1800200fd`
- `adsldpc!FreeADsMem` at `0x1800200fd`

## string_xrefs

- `0x18001ffde`: `lastUpdateSequence`

## pseudocode

```c
__int64 __fastcall CClassContainer::ChangePackageUpgradeList(
        CClassContainer *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        struct tagUPGRADEINFO *a4)
{
  unsigned __int16 *v5; // r15
  unsigned int v6; // esi
  unsigned int v7; // r13d
  unsigned int v8; // r11d
  __int64 v9; // r10
  __int64 v10; // r10
  int v11; // r11d
  __int64 v12; // rax
  _QWORD *v13; // r14
  HLOCAL v14; // r12
  int v15; // eax
  const unsigned __int16 *v16; // rdx
  int ConsistentPackageFlags; // ebx
  int v19; // eax
  unsigned int PropertyFromAttr; // eax
  unsigned int v21; // edx
  __int64 v22; // rcx
  __int128 v23; // xmm1
  unsigned int v24; // eax
  __int64 v25; // rax
  HLOCAL v26; // rdi
  HLOCAL v27; // rax
  unsigned int v28; // r12d
  unsigned int v29; // edi
  _QWORD *v30; // rsi
  _QWORD *v31; // r15
  __int64 v32; // rcx
  __int64 v33; // r12
  __int64 v34; // r14
  __int64 v35; // rbx
  unsigned int i; // r8d
  unsigned int j; // ecx
  unsigned __int16 *v38; // rax
  __int64 v39; // rbx
  int v40; // r10d
  int v41; // r11d
  char *v42; // rax
  __int64 v43; // rcx
  unsigned int v44; // r8d
  char *v45; // r12
  unsigned int k; // ecx
  unsigned __int16 *v47; // rax
  __int64 v48; // rbx
  int v49; // r10d
  int v50; // r11d
  __int64 v51; // rcx
  unsigned __int16 **v52; // r14
  unsigned int v53; // esi
  unsigned int v54; // edi
  __int64 v55; // rax
  __int64 v56; // rbx
  __int64 v57; // rax
  unsigned int v58; // r13d
  unsigned __int16 *v59; // rax
  unsigned int m; // ebx
  unsigned int n; // edi
  __int64 v62; // [rsp+38h] [rbp-C8h]
  unsigned int v63; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v64; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v65; // [rsp+4Ch] [rbp-B4h] BYREF
  HLOCAL v66; // [rsp+50h] [rbp-B0h]
  unsigned int v67; // [rsp+58h] [rbp-A8h] BYREF
  HLOCAL v68; // [rsp+60h] [rbp-A0h]
  LPVOID pMem; // [rsp+68h] [rbp-98h] BYREF
  void *v70; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v71; // [rsp+78h] [rbp-88h]
  unsigned int v72; // [rsp+7Ch] [rbp-84h]
  int v73; // [rsp+80h] [rbp-80h] BYREF
  CClassContainer *v74; // [rsp+88h] [rbp-78h]
  HLOCAL hMem; // [rsp+90h] [rbp-70h] BYREF
  HLOCAL v76; // [rsp+98h] [rbp-68h] BYREF
  HLOCAL v77; // [rsp+A0h] [rbp-60h]
  unsigned __int16 *v78; // [rsp+A8h] [rbp-58h] BYREF
  wchar_t *EndPtr; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD v80[2]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v81[4]; // [rsp+E0h] [rbp-20h] BYREF
  struct _ads_attr_info v82; // [rsp+100h] [rbp+0h] BYREF
  struct _ads_attr_info v83; // [rsp+120h] [rbp+20h] BYREF
  struct _ads_attr_info v84; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int16 v85[24]; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int16 v86[264]; // [rsp+190h] [rbp+90h] BYREF

  v78 = (unsigned __int16 *)a4;
  v81[0] = L"canUpgradeScript";
  v71 = a3;
  v74 = this;
  v81[1] = L"objectGUID";
  v81[2] = L"packageFlags";
  v5 = (unsigned __int16 *)a4;
  v67 = a3;
  v6 = a3;
  v70 = 0;
  v7 = 0;
  hMem = 0;
  v76 = 0;
  pMem = 0;
  v73 = 0;
  v64 = 0;
  v63 = 0;
  v65 = 0;
  if ( !a2 || a3 && !a4 )
    return 2147942487LL;
  v8 = 0;
  if ( a3 )
  {
    while ( 1 )
    {
      v9 = 24LL * v8;
      if ( !*(_QWORD *)&v5[v9]
        || (unsigned int)IsNullGuid((const struct _GUID *)&v5[v9 + 4])
        || (*((_BYTE *)v5 + v10 + 40) & 7) == 0 )
      {
        return 2147942487LL;
      }
      v8 = v11 + 1;
      if ( v8 >= v6 )
      {
        this = v74;
        break;
      }
    }
  }
  v12 = *(_QWORD *)this;
  v13 = 0;
  v77 = 0;
  v14 = 0;
  v15 = (*(__int64 (__fastcall **)(CClassContainer *, const unsigned __int16 *, HLOCAL *))(v12 + 152))(this, a2, &hMem);
  ConsistentPackageFlags = v15;
  if ( v15 < 0 )
    goto LABEL_77;
  if ( v15 )
    return 2147746153LL;
  v19 = (gCsOptions & 1) != 0 ? GetADsOpenObjectFlags() | 0x21 : 101;
  ConsistentPackageFlags = DSServerOpenDSObject(
                             (CClassContainer *)((char *)v74 + 592),
                             (const unsigned __int16 *)hMem,
                             v19,
                             &v70);
  if ( ConsistentPackageFlags < 0
    || (ConsistentPackageFlags = ADSIGetObjectAttributes(v70, v81, 3, &pMem, &v63), ConsistentPackageFlags < 0) )
  {
LABEL_77:
    v53 = 0;
  }
  else
  {
    GetPropertyFromAttr((struct _ads_attr_info *)pMem, v63, L"objectGUID");
    PropertyFromAttr = GetPropertyFromAttr((struct _ads_attr_info *)pMem, v63, L"canUpgradeScript");
    v21 = v63;
    if ( PropertyFromAttr < v63 )
    {
      v22 = 32LL * PropertyFromAttr;
      v23 = *(_OWORD *)((char *)pMem + v22 + 16);
      v80[0] = *(_OWORD *)((char *)pMem + v22);
      v80[1] = v23;
      UnpackStrArrFrom<_ads_attr_info>((__int64)v80, &v76, &v64);
      v21 = v63;
      v7 = v64;
    }
    v24 = GetPropertyFromAttr((struct _ads_attr_info *)pMem, v21, L"packageFlags");
    if ( v24 < v63 )
    {
      v25 = 32LL * v24;
      if ( *(_DWORD *)((char *)pMem + v25 + 24) )
        v65 = *(_DWORD *)(*(_QWORD *)((char *)pMem + v25 + 16) + 8LL);
    }
    v66 = LocalAlloc(0, 48LL * v7);
    v13 = v66;
    v26 = LocalAlloc(0, 48LL * (v6 + v7));
    v77 = v26;
    v27 = LocalAlloc(0, 48LL * (v6 + v7));
    v68 = v27;
    v14 = v27;
    if ( v13 && v26 && v27 )
    {
      v72 = 0;
      v28 = 0;
      v64 = 0;
      v29 = 0;
      if ( v7 )
      {
        v30 = v76;
        v31 = v13;
        do
        {
          v32 = -1;
          EndPtr = 0;
          v33 = v30[v29];
          do
            ++v32;
          while ( *(_WORD *)(v33 + 2 * v32) );
          v34 = 6LL * v29;
          v31[v34] = v33;
          if ( (unsigned int)v32 > 0x29 )
          {
            v35 = (unsigned int)v32;
            *(_WORD *)(v33 + 2LL * (unsigned int)v32 - 6) = 0;
            LODWORD(v31[v34 + 5]) = wcstoul((const wchar_t *)(v33 + 2LL * (unsigned int)(v32 - 2)), &EndPtr, 16);
            *(_WORD *)(v33 + 2 * v35 - 82) = 0;
            GUIDFromString((const unsigned __int16 *)(v33 + 2 * (v35 - 39)), (struct _GUID *)&v31[v34 + 1]);
          }
          ++v29;
        }
        while ( v29 < v7 );
        v6 = v71;
        v5 = v78;
        v13 = v66;
        v28 = v72;
      }
      for ( i = 0; i < v6; ++i )
      {
        for ( j = 0; j < v29; ++j )
        {
          v38 = (unsigned __int16 *)v13[6 * j];
          v39 = *(_QWORD *)&v5[24 * i] - (_QWORD)v38;
          do
          {
            v40 = *(unsigned __int16 *)((char *)v38 + v39);
            v41 = *v38 - v40;
            if ( v41 )
              break;
            ++v38;
          }
          while ( v40 );
          if ( !v41 && v13[6 * j + 1] == *(_QWORD *)&v5[24 * i + 4] && v13[6 * j + 2] == *(_QWORD *)&v5[24 * i + 8] )
            break;
        }
        if ( j == v29 )
        {
          v42 = (char *)v77;
          v43 = 6LL * v28++;
          *(_OWORD *)((char *)v77 + 8 * v43) = *(_OWORD *)&v5[24 * i];
          *(_OWORD *)&v42[8 * v43 + 16] = *(_OWORD *)&v5[24 * i + 8];
          *(_OWORD *)&v42[8 * v43 + 32] = *(_OWORD *)&v5[24 * i + 16];
        }
      }
      v44 = 0;
      if ( v29 )
      {
        v45 = (char *)v68;
        do
        {
          for ( k = 0; k < v6; ++k )
          {
            v47 = (unsigned __int16 *)v13[6 * v44];
            v48 = *(_QWORD *)&v5[24 * k] - (_QWORD)v47;
            do
            {
              v49 = *(unsigned __int16 *)((char *)v47 + v48);
              v50 = *v47 - v49;
              if ( v50 )
                break;
              ++v47;
            }
            while ( v49 );
            if ( !v50
              && v13[6 * v44 + 1] == *(_QWORD *)&v5[24 * k + 4]
              && v13[6 * v44 + 2] == *(_QWORD *)&v5[24 * k + 8] )
            {
              break;
            }
          }
          if ( k == v6 )
          {
            v51 = 6LL * v64++;
            *(_OWORD *)&v45[8 * v51] = *(_OWORD *)&v13[6 * v44];
            *(_OWORD *)&v45[8 * v51 + 16] = *(_OWORD *)&v13[6 * v44 + 2];
            *(_OWORD *)&v45[8 * v51 + 32] = *(_OWORD *)&v13[6 * v44 + 4];
          }
          ++v44;
        }
        while ( v44 < v29 );
      }
      v52 = (unsigned __int16 **)LocalAlloc(0, 8LL * v6);
      if ( v52 )
      {
        v54 = 0;
        if ( !v6 )
        {
LABEL_69:
          PackStrArrToAttr(&v82, L"canUpgradeScript", v52, v6);
          GetCurrentUsn(v85);
          v78 = v85;
          PackStrArrToAttr(&v83, L"lastUpdateSequence", &v78, 1u);
          v53 = 2;
          ConsistentPackageFlags = GetConsistentPackageFlags(0, &v65, &v67, 0, 0, &v65, 0);
          if ( ConsistentPackageFlags >= 0 )
          {
            v67 = v65;
            PackDWArrToAttr(&v84, L"packageFlags", &v67, 1u);
            v53 = 3;
            ConsistentPackageFlags = ADSISetObjectAttributes(v70, &v82, 3, &v73);
            if ( ConsistentPackageFlags >= 0 )
              UpdateStoreUsn(*((void **)v74 + 69), v85);
          }
          v13 = v66;
          v14 = v68;
          goto LABEL_78;
        }
        while ( 1 )
        {
          v55 = -1;
          v56 = 24LL * v54;
          do
            ++v55;
          while ( *(_WORD *)(*(_QWORD *)&v5[v56] + 2 * v55) );
          v57 = (unsigned int)(v55 + 43);
          v58 = v57;
          v59 = (unsigned __int16 *)LocalAlloc(0, 2 * v57);
          v52[v54] = v59;
          if ( !v59 )
            break;
          StringFromGUID((const struct _GUID *)&v5[v56 + 4], v86);
          LODWORD(v62) = *(_DWORD *)&v5[v56 + 20] & 0xF;
          ConsistentPackageFlags = StringCchPrintfW(
                                     v52[v54],
                                     v58,
                                     L"%s%s%s%s%02x",
                                     *(_QWORD *)&v5[v56],
                                     L"\\\\",
                                     v86,
                                     L":",
                                     v62);
          if ( ConsistentPackageFlags < 0 )
            goto LABEL_61;
          if ( ++v54 >= v6 )
            goto LABEL_69;
        }
        for ( m = 0; m < v54; ++m )
          LocalFree(v52[m]);
        LocalFree(v52);
      }
      ConsistentPackageFlags = -2147024882;
LABEL_61:
      v13 = v66;
      v14 = v68;
    }
    else
    {
      ConsistentPackageFlags = -2147024882;
    }
    v53 = 0;
  }
LABEL_78:
  if ( v70 )
    ADSICloseDSObject(v70, v16);
  if ( hMem )
    LocalFree(hMem);
  for ( n = 0; n < v53; ++n )
    LocalFree(*((HLOCAL *)&v82.pADsValues + 4 * n));
  if ( pMem )
    FreeADsMem(pMem);
  if ( v76 )
    LocalFree(v76);
  if ( v13 )
    LocalFree(v13);
  if ( v77 )
    LocalFree(v77);
  if ( v14 )
    LocalFree(v14);
  return RemapErrorCode(ConsistentPackageFlags, v16);
}

```

## disassembly

```asm
0x18001fa10  push    rbp
0x18001fa12  push    rbx
0x18001fa13  push    rsi
0x18001fa14  push    rdi
0x18001fa15  push    r12
0x18001fa17  push    r13
0x18001fa19  push    r14
0x18001fa1b  push    r15
0x18001fa1d  lea     rbp, [rsp-2B8h]
0x18001fa25  sub     rsp, 3B8h
0x18001fa2c  mov     rax, cs:__security_cookie
0x18001fa33  xor     rax, rsp
0x18001fa36  mov     [rbp+2F0h+var_50], rax
0x18001fa3d  lea     rax, aCanupgradescri; "canUpgradeScript"
0x18001fa44  mov     [rbp+2F0h+var_348], r9
0x18001fa48  mov     [rbp+2F0h+var_310], rax
0x18001fa4c  mov     rbx, rdx
0x18001fa4f  xor     edx, edx
0x18001fa51  mov     [rsp+3F0h+var_378], r8d
0x18001fa56  mov     [rbp+2F0h+var_368], rcx
0x18001fa5a  lea     rax, aObjectguid; "objectGUID"
0x18001fa61  mov     [rbp+2F0h+var_308], rax
0x18001fa65  lea     rax, aPackageflags; "packageFlags"
0x18001fa6c  mov     [rbp+2F0h+var_300], rax
0x18001fa70  mov     r15, r9
0x18001fa73  mov     [rsp+3F0h+var_398], r8d
0x18001fa78  mov     esi, r8d
0x18001fa7b  mov     [rsp+3F0h+var_380], rdx
0x18001fa80  mov     r13d, edx
0x18001fa83  mov     [rbp+2F0h+hMem], rdx
0x18001fa87  mov     [rbp+2F0h+var_358], rdx
0x18001fa8b  mov     [rsp+3F0h+pMem], rdx
0x18001fa90  mov     [rbp+2F0h+var_370], edx
0x18001fa93  mov     [rsp+3F0h+var_3A8], edx
0x18001fa97  mov     [rsp+3F0h+var_3AC], edx
0x18001fa9b  mov     [rsp+3F0h+var_3A4], edx
0x18001fa9f  test    rbx, rbx
0x18001faa2  jz      loc_180020149
0x18001faa8  test    r8d, r8d
0x18001faab  jz      short loc_18001FAB6
0x18001faad  test    r9, r9
0x18001fab0  jz      loc_180020149
0x18001fab6  mov     r11d, edx
0x18001fab9  test    esi, esi
0x18001fabb  jz      short loc_18001FB00
0x18001fabd  mov     eax, r11d
0x18001fac0  lea     r10, [rax+rax*2]
0x18001fac4  shl     r10, 4
0x18001fac8  cmp     [r10+r15], rdx
0x18001facc  jz      loc_180020149
0x18001fad2  lea     rcx, [r15+8]
0x18001fad6  add     rcx, r10; struct _GUID *
0x18001fad9  call    ?IsNullGuid@@YAHAEBU_GUID@@@Z; IsNullGuid(_GUID const &)
0x18001fade  xor     edx, edx
0x18001fae0  test    eax, eax
0x18001fae2  jnz     loc_180020149
0x18001fae8  test    byte ptr [r10+r15+28h], 7
0x18001faee  jz      loc_180020149
0x18001faf4  inc     r11d
0x18001faf7  cmp     r11d, esi
0x18001fafa  jb      short loc_18001FABD
0x18001fafc  mov     rcx, [rbp+2F0h+var_368]
0x18001fb00  mov     rax, [rcx]
0x18001fb03  lea     r8, [rbp+2F0h+hMem]
0x18001fb07  mov     [rsp+3F0h+var_3B0], edx
0x18001fb0b  mov     r14, rdx
0x18001fb0e  mov     [rbp+2F0h+var_350], rdx
0x18001fb12  mov     r12, rdx
0x18001fb15  mov     rdx, rbx
0x18001fb18  mov     rax, [rax+98h]
0x18001fb1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb24  mov     ebx, eax
0x18001fb26  test    eax, eax
0x18001fb28  js      loc_1800200B2
0x18001fb2e  jz      short loc_18001FB3A
0x18001fb30  mov     eax, 80040169h
0x18001fb35  jmp     loc_18002014E
0x18001fb3a  test    byte ptr cs:?gCsOptions@@3KA, 1; ulong gCsOptions
0x18001fb41  jz      short loc_18001FB4D
0x18001fb43  call    ?GetADsOpenObjectFlags@@YAKXZ; GetADsOpenObjectFlags(void)
0x18001fb48  or      eax, 21h
0x18001fb4b  jmp     short loc_18001FB52
0x18001fb4d  mov     eax, 65h ; 'e'
0x18001fb52  mov     rcx, [rbp+2F0h+var_368]
0x18001fb56  lea     r9, [rsp+3F0h+var_380]; void **
0x18001fb5b  mov     rdx, [rbp+2F0h+hMem]; unsigned __int16 *
0x18001fb5f  add     rcx, 250h; struct CServerContext *
0x18001fb66  mov     r8d, eax; int
0x18001fb69  call    ?DSServerOpenDSObject@@YAJPEAVCServerContext@@PEBGJPEAPEAX@Z; DSServerOpenDSObject(CServerContext *,ushort const *,long,void * *)
0x18001fb6e  xor     edi, edi
0x18001fb70  mov     ebx, eax
0x18001fb72  test    eax, eax
0x18001fb74  js      loc_1800200B2
0x18001fb7a  mov     rcx, [rsp+3F0h+var_380]
0x18001fb7f  lea     rax, [rsp+3F0h+var_3AC]
0x18001fb84  lea     r9, [rsp+3F0h+pMem]
0x18001fb89  mov     [rsp+3F0h+var_3D0], rax
0x18001fb8e  lea     r8d, [rdi+3]
0x18001fb92  lea     rdx, [rbp+2F0h+var_310]
0x18001fb96  call    cs:__imp_ADSIGetObjectAttributes
0x18001fb9c  mov     ebx, eax
0x18001fb9e  test    eax, eax
0x18001fba0  js      loc_1800200B2
0x18001fba6  mov     edx, [rsp+3F0h+var_3AC]; unsigned int
0x18001fbaa  lea     r8, aObjectguid; "objectGUID"
0x18001fbb1  mov     rcx, [rsp+3F0h+pMem]; struct _ads_attr_info *
0x18001fbb6  call    ?GetPropertyFromAttr@@YAKPEAU_ads_attr_info@@KPEBG@Z; GetPropertyFromAttr(_ads_attr_info *,ulong,ushort const *)
0x18001fbbb  mov     edx, [rsp+3F0h+var_3AC]; unsigned int
0x18001fbbf  lea     r8, aCanupgradescri; "canUpgradeScript"
0x18001fbc6  mov     rcx, [rsp+3F0h+pMem]; struct _ads_attr_info *
0x18001fbcb  call    ?GetPropertyFromAttr@@YAKPEAU_ads_attr_info@@KPEBG@Z; GetPropertyFromAttr(_ads_attr_info *,ulong,ushort const *)
0x18001fbd0  mov     edx, [rsp+3F0h+var_3AC]
0x18001fbd4  cmp     eax, edx
0x18001fbd6  jnb     short loc_18001FC0F
0x18001fbd8  mov     ecx, eax
0x18001fbda  lea     r8, [rsp+3F0h+var_3A8]
0x18001fbdf  mov     rax, [rsp+3F0h+pMem]
0x18001fbe4  lea     rdx, [rbp+2F0h+var_358]
0x18001fbe8  shl     rcx, 5
0x18001fbec  movups  xmm0, xmmword ptr [rcx+rax]
0x18001fbf0  movups  xmm1, xmmword ptr [rcx+rax+10h]
0x18001fbf5  lea     rcx, [rbp+2F0h+var_330]
0x18001fbf9  movaps  [rbp+2F0h+var_330], xmm0
0x18001fbfd  movaps  [rbp+2F0h+var_320], xmm1
0x18001fc01  call    ??$UnpackStrArrFrom@U_ads_attr_info@@@@YAJU_ads_attr_info@@PEAPEAPEAGPEAK@Z; UnpackStrArrFrom<_ads_attr_info>(_ads_attr_info,ushort * * *,ulong *)
0x18001fc06  mov     edx, [rsp+3F0h+var_3AC]; unsigned int
0x18001fc0a  mov     r13d, [rsp+3F0h+var_3A8]
0x18001fc0f  mov     rcx, [rsp+3F0h+pMem]; struct _ads_attr_info *
0x18001fc14  lea     r8, aPackageflags; "packageFlags"
0x18001fc1b  call    ?GetPropertyFromAttr@@YAKPEAU_ads_attr_info@@KPEBG@Z; GetPropertyFromAttr(_ads_attr_info *,ulong,ushort const *)
0x18001fc20  cmp     eax, [rsp+3F0h+var_3AC]
0x18001fc24  jnb     short loc_18001FC43
0x18001fc26  mov     rcx, [rsp+3F0h+pMem]
0x18001fc2b  mov     eax, eax
0x18001fc2d  shl     rax, 5
0x18001fc31  cmp     [rax+rcx+18h], edi
0x18001fc35  jz      short loc_18001FC43
0x18001fc37  mov     rax, [rax+rcx+10h]
0x18001fc3c  mov     ecx, [rax+8]
0x18001fc3f  mov     [rsp+3F0h+var_3A4], ecx
0x18001fc43  mov     eax, r13d
0x18001fc46  xor     ecx, ecx; uFlags
0x18001fc48  lea     rdx, [rax+rax*2]
0x18001fc4c  shl     rdx, 4; uBytes
0x18001fc50  call    cs:__imp_LocalAlloc
0x18001fc56  lea     ecx, [rsi+r13]
0x18001fc5a  mov     [rsp+3F0h+var_3A0], rax
0x18001fc5f  mov     r14, rax
0x18001fc62  lea     rbx, [rcx+rcx*2]
0x18001fc66  xor     ecx, ecx; uFlags
0x18001fc68  shl     rbx, 4
0x18001fc6c  mov     rdx, rbx; uBytes
0x18001fc6f  call    cs:__imp_LocalAlloc
0x18001fc75  mov     rdx, rbx; uBytes
0x18001fc78  xor     ecx, ecx; uFlags
0x18001fc7a  mov     rdi, rax
0x18001fc7d  mov     [rbp+2F0h+var_350], rax
0x18001fc81  call    cs:__imp_LocalAlloc
0x18001fc87  xor     ebx, ebx
0x18001fc89  mov     [rsp+3F0h+var_390], rax
0x18001fc8e  mov     r12, rax
0x18001fc91  test    r14, r14
0x18001fc94  jz      loc_1800200A8
0x18001fc9a  test    rdi, rdi
0x18001fc9d  jz      loc_1800200A8
0x18001fca3  test    rax, rax
0x18001fca6  jz      loc_1800200A8
0x18001fcac  mov     [rsp+3F0h+var_374], ebx
0x18001fcb0  mov     r12d, ebx
0x18001fcb3  mov     [rsp+3F0h+var_3A8], ebx
0x18001fcb7  mov     edi, ebx
0x18001fcb9  test    r13d, r13d
0x18001fcbc  jz      loc_18001FD4D
0x18001fcc2  mov     rsi, [rbp+2F0h+var_358]
0x18001fcc6  mov     r15, r14
0x18001fcc9  mov     eax, edi
0x18001fccb  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001fccf  mov     [rbp+2F0h+EndPtr], rbx
0x18001fcd3  mov     r12, [rsi+rax*8]
0x18001fcd7  inc     rcx
0x18001fcda  cmp     [r12+rcx*2], bx
0x18001fcdf  jnz     short loc_18001FCD7
0x18001fce1  lea     r14, [rax+rax*2]
0x18001fce5  shl     r14, 4
0x18001fce9  mov     [r14+r15], r12
0x18001fced  cmp     ecx, 29h ; ')'
0x18001fcf0  jbe     short loc_18001FD34
0x18001fcf2  xor     edx, edx
0x18001fcf4  mov     ebx, ecx
0x18001fcf6  lea     eax, [rcx-2]
0x18001fcf9  lea     rcx, [r12+rax*2]; String
0x18001fcfd  mov     [r12+rbx*2-6], dx
0x18001fd03  lea     r8d, [rdx+10h]; Radix
0x18001fd07  lea     rdx, [rbp+2F0h+EndPtr]; EndPtr
0x18001fd0b  call    cs:__imp_wcstoul
0x18001fd11  mov     [r14+r15+28h], eax
0x18001fd16  lea     rdx, [r15+8]
0x18001fd1a  xor     eax, eax
0x18001fd1c  add     rdx, r14; struct _GUID *
0x18001fd1f  mov     [r12+rbx*2-52h], ax
0x18001fd25  add     rbx, 0FFFFFFFFFFFFFFD9h
0x18001fd29  lea     rcx, [r12+rbx*2]; unsigned __int16 *
0x18001fd2d  call    ?GUIDFromString@@YAXPEBGPEAU_GUID@@@Z; GUIDFromString(ushort const *,_GUID *)
0x18001fd32  xor     ebx, ebx
0x18001fd34  inc     edi
0x18001fd36  cmp     edi, r13d
0x18001fd39  jb      short loc_18001FCC9
0x18001fd3b  mov     esi, [rsp+3F0h+var_378]
0x18001fd3f  mov     r15, [rbp+2F0h+var_348]
0x18001fd43  mov     r14, [rsp+3F0h+var_3A0]
0x18001fd48  mov     r12d, [rsp+3F0h+var_374]
0x18001fd4d  mov     r8d, ebx
0x18001fd50  test    esi, esi
0x18001fd52  jz      loc_18001FE02
0x18001fd58  mov     ecx, ebx
0x18001fd5a  test    edi, edi
0x18001fd5c  jz      short loc_18001FDB8
0x18001fd5e  mov     eax, r8d
0x18001fd61  lea     rdx, [rax+rax*2]
0x18001fd65  add     rdx, rdx
0x18001fd68  mov     rbx, [r15+rdx*8]
0x18001fd6c  mov     eax, ecx
0x18001fd6e  lea     r9, [rax+rax*2]
0x18001fd72  add     r9, r9
0x18001fd75  mov     rax, [r14+r9*8]
0x18001fd79  sub     rbx, rax
0x18001fd7c  movzx   r11d, word ptr [rax]
0x18001fd80  movzx   r10d, word ptr [rax+rbx]
0x18001fd85  sub     r11d, r10d
0x18001fd88  jnz     short loc_18001FD93
0x18001fd8a  add     rax, 2
0x18001fd8e  test    r10d, r10d
0x18001fd91  jnz     short loc_18001FD7C
0x18001fd93  xor     ebx, ebx
0x18001fd95  test    r11d, r11d
0x18001fd98  jnz     short loc_18001FDB2
0x18001fd9a  mov     rax, [r14+r9*8+8]
0x18001fd9f  cmp     rax, [r15+rdx*8+8]
0x18001fda4  jnz     short loc_18001FDB2
0x18001fda6  mov     rax, [r14+r9*8+10h]
0x18001fdab  cmp     rax, [r15+rdx*8+10h]
0x18001fdb0  jz      short loc_18001FDB8
0x18001fdb2  inc     ecx
0x18001fdb4  cmp     ecx, edi
0x18001fdb6  jb      short loc_18001FD68
0x18001fdb8  cmp     ecx, edi
0x18001fdba  jnz     short loc_18001FDF6
0x18001fdbc  mov     eax, r8d
0x18001fdbf  lea     rdx, [rax+rax*2]
0x18001fdc3  mov     eax, r12d
0x18001fdc6  add     rdx, rdx
0x18001fdc9  lea     rcx, [rax+rax*2]
0x18001fdcd  mov     rax, [rbp+2F0h+var_350]
0x18001fdd1  movups  xmm0, xmmword ptr [r15+rdx*8]
0x18001fdd6  add     rcx, rcx
0x18001fdd9  inc     r12d
0x18001fddc  movups  xmmword ptr [rax+rcx*8], xmm0
0x18001fde0  movups  xmm1, xmmword ptr [r15+rdx*8+10h]
0x18001fde6  movups  xmmword ptr [rax+rcx*8+10h], xmm1
0x18001fdeb  movups  xmm0, xmmword ptr [r15+rdx*8+20h]
0x18001fdf1  movups  xmmword ptr [rax+rcx*8+20h], xmm0
0x18001fdf6  inc     r8d
0x18001fdf9  cmp     r8d, esi
0x18001fdfc  jb      loc_18001FD58
0x18001fe02  mov     r8d, ebx
0x18001fe05  test    edi, edi
0x18001fe07  jz      loc_18001FEC2
0x18001fe0d  mov     r12, [rsp+3F0h+var_390]
0x18001fe12  mov     ecx, ebx
0x18001fe14  test    esi, esi
0x18001fe16  jz      short loc_18001FE72
0x18001fe18  mov     eax, r8d
0x18001fe1b  lea     rdx, [rax+rax*2]
0x18001fe1f  add     rdx, rdx
0x18001fe22  mov     eax, ecx
0x18001fe24  lea     r9, [rax+rax*2]
0x18001fe28  mov     rax, [r14+rdx*8]
0x18001fe2c  add     r9, r9
0x18001fe2f  mov     rbx, [r15+r9*8]
0x18001fe33  sub     rbx, rax
0x18001fe36  movzx   r11d, word ptr [rax]
0x18001fe3a  movzx   r10d, word ptr [rax+rbx]
0x18001fe3f  sub     r11d, r10d
0x18001fe42  jnz     short loc_18001FE4D
0x18001fe44  add     rax, 2
0x18001fe48  test    r10d, r10d
0x18001fe4b  jnz     short loc_18001FE36
0x18001fe4d  xor     ebx, ebx
0x18001fe4f  test    r11d, r11d
0x18001fe52  jnz     short loc_18001FE6C
0x18001fe54  mov     rax, [r14+rdx*8+8]
0x18001fe59  cmp     rax, [r15+r9*8+8]
0x18001fe5e  jnz     short loc_18001FE6C
0x18001fe60  mov     rax, [r14+rdx*8+10h]
0x18001fe65  cmp     rax, [r15+r9*8+10h]
0x18001fe6a  jz      short loc_18001FE72
0x18001fe6c  inc     ecx
0x18001fe6e  cmp     ecx, esi
0x18001fe70  jb      short loc_18001FE22
0x18001fe72  cmp     ecx, esi
  ... truncated ...
```
