# CAppContainer::GetAppInfo(__MIDL___MIDL_itf_wtypes_0000_0001_0001 *,tagQUERYCONTEXT *,tagPACKAGEDISPINFO *)

- ea: `0x18001d240`
- end: `0x18001d96b`
- name: `?GetAppInfo@CAppContainer@@UEAAJPEAU__MIDL___MIDL_itf_wtypes_0000_0001_0001@@PEAUtagQUERYCONTEXT@@PEAUtagPACKAGEDISPINFO@@@Z`
- size: `1835`
- prototype: `__int64 __fastcall(CAppContainer *__hidden this, struct __MIDL___MIDL_itf_wtypes_0000_0001_0001 *, struct tagQUERYCONTEXT *, struct tagPACKAGEDISPINFO *)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x1800016d0`
- `0x180002024`
- `0x180008f58`
- `0x18001b1a0`
- `0x18001c0e0`
- `0x18001c6b0`
- `0x18001d240`
- `0x18001d974`
- `0x1800240b0`
- `0x180024458`
- `0x180024d54`
- `0x180024e04`
- `0x180025378`
- `0x18002ad30`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x18001d46a`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x18001d46a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d921`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d921`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d5be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d7c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d5be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d7c0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d4d4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d71e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d4d4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d71e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001d4de`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001d4de`
- `adsldpc!ADsEncodeBinaryData` at `0x18001d315`
- `adsldpc!ADsEncodeBinaryData` at `0x18001d315`
- `adsldpc!ADSIExecuteSearch` at `0x18001d64c`
- `adsldpc!ADSIExecuteSearch` at `0x18001d64c`
- `adsldpc!ADSICloseSearchHandle` at `0x18001d901`
- `adsldpc!ADSICloseSearchHandle` at `0x18001d901`
- `adsldpc!FreeADsMem` at `0x18001d34b`
- `adsldpc!FreeADsMem` at `0x18001d34b`

## string_xrefs

- `0x18001d5ed`: `cOMClassID`
- `0x18001d3ad`: `cOMProgID`

## pseudocode

```c
__int64 __fastcall CAppContainer::GetAppInfo(
        CAppContainer *this,
        struct __MIDL___MIDL_itf_wtypes_0000_0001_0001 *a2,
        struct tagQUERYCONTEXT *a3,
        struct tagPACKAGEDISPINFO *a4)
{
  unsigned __int16 *v6; // r12
  int v8; // r9d
  __int64 result; // rax
  DWORD tyspec; // ecx
  unsigned __int16 *v11; // r15
  unsigned int v12; // edi
  DWORD v13; // ecx
  DWORD v14; // ecx
  DWORD v15; // ecx
  int v16; // ebx
  const unsigned __int16 *pFileExt; // rcx
  LPOLESTR v18; // rax
  LPOLESTR v19; // rax
  unsigned __int64 v20; // rcx
  __int64 v21; // rdx
  _WORD *v22; // rcx
  __int64 v23; // r8
  _WORD *v24; // rdx
  unsigned int i; // edi
  __int64 v26; // rbx
  int v27; // ecx
  bool v28; // zf
  __int64 v29; // rcx
  const unsigned __int16 *v30; // rdx
  int v31; // ebx
  unsigned int InstallData; // eax
  CAppContainer *v33; // rcx
  unsigned int v34; // edi
  int v35; // r8d
  __int64 v36; // rax
  int v37; // eax
  _OWORD *v38; // rcx
  __int128 v39; // xmm1
  __int128 v40; // xmm0
  __int128 v41; // xmm1
  __int128 v42; // xmm0
  __int128 v43; // xmm1
  __int128 v44; // xmm0
  __int128 v45; // xmm1
  __int128 v46; // xmm0
  __int128 v47; // xmm1
  __int128 v48; // xmm0
  __int128 v49; // xmm1
  __int128 v50; // xmm0
  unsigned int v51; // r14d
  wchar_t v52; // [rsp+20h] [rbp-E0h]
  long double v53; // [rsp+28h] [rbp-D8h]
  unsigned int v54; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v55; // [rsp+64h] [rbp-9Ch] BYREF
  LPWSTR ppszDestData; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v57; // [rsp+70h] [rbp-90h] BYREF
  struct tagQUERYCONTEXT *v58; // [rsp+78h] [rbp-88h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+80h] [rbp-80h] BYREF
  void *v60; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v61; // [rsp+90h] [rbp-70h]
  unsigned int v62[10]; // [rsp+98h] [rbp-68h] BYREF
  _OWORD v63[130]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v64[32]; // [rsp+8E0h] [rbp+7E0h] BYREF
  unsigned __int16 v65[40]; // [rsp+900h] [rbp+800h] BYREF
  unsigned __int16 v66[1000]; // [rsp+950h] [rbp+850h] BYREF

  v58 = a3;
  SystemTimeAsFileTime = 0;
  v57 = 0;
  v6 = 0;
  memset_0(a4, 0, 0xD0u);
  if ( !*((_DWORD *)this + 134) )
    return 2147500037LL;
  tyspec = a2->tyspec;
  v11 = v66;
  v61 = 0;
  v12 = 1;
  v55 = 1;
  if ( tyspec )
  {
    v13 = tyspec - 1;
    if ( v13 )
    {
      v14 = v13 - 3;
      if ( v14 )
      {
        v15 = v14 - 1;
        if ( v15 )
        {
          if ( v15 != 1 )
            return 2147500033LL;
          if ( !(unsigned int)IsNullGuid(&a2->tagged_union.clsid) )
          {
            ppszDestData = 0;
            ADsEncodeBinaryData((PBYTE)&a2->tagged_union, 0x10u, &ppszDestData);
            v16 = StringCchPrintfW(v66, 0x3E8u, L"(%s=%s)", L"objectGUID", ppszDestData);
            FreeADsMem(ppszDestData);
            if ( v16 < 0 )
              return (unsigned int)v16;
LABEL_17:
            v12 = 0;
            goto LABEL_54;
          }
        }
        else
        {
          pFileExt = a2->tagged_union.pFileExt;
          if ( pFileExt && *pFileExt )
          {
            result = GetEscapedNameFilter(pFileExt, &v57);
            if ( (int)result < 0 )
              return result;
            v6 = v57;
            v11 = v57;
            goto LABEL_17;
          }
        }
        return 2147942487LL;
      }
      v18 = a2->tagged_union.pFileExt;
      if ( !v18 || !*v18 )
        return 2147942487LL;
      result = StringCchPrintfW(v66, 0x3E8u, L"(%s=%s)", L"cOMProgID", a2->tagged_union.pFileExt);
      if ( (int)result < 0 )
        return result;
LABEL_54:
      v29 = *((_QWORD *)this + 69);
      v54 = 0;
      v60 = 0;
      v31 = ADSIExecuteSearch(v29, v11, &pszInstallInfoAttrNames, 21, &v60);
      if ( gDebug )
        _DebugMsg(2, 0xC8Du, v11);
      if ( v31 < 0 )
        goto LABEL_78;
      InstallData = FetchInstallData(
                      *((void **)this + 69),
                      v60,
                      v58,
                      a2,
                      v61,
                      0xAu,
                      &v54,
                      (struct tagPACKAGEDISPINFO *)v63,
                      v62,
                      v12,
                      (struct _GUID *)this + 35,
                      *((unsigned __int16 **)this + 144));
      v31 = InstallData;
      if ( gDebug )
        _DebugMsg(2, 0xC8Eu, v54, InstallData);
      v34 = v54;
      if ( !v54 )
      {
        v31 = -2147221143;
        if ( !a2->tyspec )
        {
          EnterCriticalSection(&ClassStoreBindList);
          if ( *((_DWORD *)this + 286) < 0x13u )
          {
            *(CLSID *)((char *)this + 28 * *((unsigned int *)this + 285) + 576) = a2->tagged_union.clsid;
            *((_DWORD *)this + 7 * *((unsigned int *)this + 285) + 148) = v58->dwContext;
            *(_QWORD *)((char *)this + 28 * *((unsigned int *)this + 285) + 596) = *(_QWORD *)&SystemTimeAsFileTime
                                                                                 + 18000000000LL;
            v35 = *((_DWORD *)this + 285);
            ++*((_DWORD *)this + 286);
            *((_DWORD *)this + 285) = (v35 + 1) % 0x14u;
          }
          LeaveCriticalSection(&ClassStoreBindList);
        }
LABEL_74:
        v30 = (const unsigned __int16 *)v60;
        if ( v60 )
          ADSICloseSearchHandle(*((_QWORD *)this + 69));
        if ( v31 >= 0 )
          *(_OWORD *)((char *)a4 + 100) = *((_OWORD *)this + 35);
LABEL_78:
        if ( v6 )
          LocalFree(v6);
        if ( gDebug )
          _DebugMsg(2, 0xC8Fu, (unsigned int)v31);
        return RemapErrorCode(v31, v30);
      }
      v36 = 0;
      v55 = 0;
      if ( v54 > 1 )
      {
        if ( v54 > 0xA )
        {
          v37 = -2147024882;
          goto LABEL_68;
        }
        v37 = CAppContainer::ChooseBestFit(v33, (const FILETIME *)v63, v62, v54, &v55);
        v34 = v54;
        if ( v37 < 0 )
        {
LABEL_68:
          if ( v31 >= 0 )
            v31 = v37;
          goto LABEL_72;
        }
        v36 = v55;
      }
      v38 = &v63[13 * v36];
      v39 = v38[1];
      *(_OWORD *)a4 = *v38;
      v40 = v38[2];
      *((_OWORD *)a4 + 1) = v39;
      v41 = v38[3];
      *((_OWORD *)a4 + 2) = v40;
      v42 = v38[4];
      *((_OWORD *)a4 + 3) = v41;
      v43 = v38[5];
      *((_OWORD *)a4 + 4) = v42;
      v44 = v38[6];
      *((_OWORD *)a4 + 5) = v43;
      v45 = v38[7];
      *((_OWORD *)a4 + 6) = v44;
      v46 = v38[8];
      *((_OWORD *)a4 + 7) = v45;
      v47 = v38[9];
      *((_OWORD *)a4 + 8) = v46;
      v48 = v38[10];
      *((_OWORD *)a4 + 9) = v47;
      v49 = v38[11];
      *((_OWORD *)a4 + 10) = v48;
      v50 = v38[12];
      *((_OWORD *)a4 + 11) = v49;
      *((_OWORD *)a4 + 12) = v50;
      memset_0(v38, 0, 0xD0u);
LABEL_72:
      v51 = 0;
      if ( v34 )
      {
        do
          ReleasePackageInfo(&v63[13 * v51++]);
        while ( v51 < v54 );
      }
      goto LABEL_74;
    }
    v19 = a2->tagged_union.pFileExt;
    if ( !v19 )
      return 2147942487LL;
    if ( !*v19 )
      return 2147942487LL;
    v20 = -1;
    do
      ++v20;
    while ( v19[v20] );
    if ( v20 > 9 )
      return 2147942487LL;
    v21 = 2147483646;
    v22 = v64;
    v23 = 10;
    do
    {
      if ( !v21 )
        break;
      v8 = *v19;
      if ( !(_WORD)v8 )
        break;
      *v22 = v8;
      ++v19;
      ++v22;
      --v21;
      --v23;
    }
    while ( v23 );
    v24 = v22 - 1;
    result = v23 == 0 ? 0x8007007A : 0;
    if ( v23 )
      v24 = v22;
    *v24 = 0;
    if ( v23 )
    {
      o((wchar_t)v64, (char)v24, v23, v8, v52, v53);
      result = StringCchPrintfW(v66, 0x3E8u, L"(%s=%s*)", L"fileExtPriority", v64);
      if ( (int)result >= 0 )
      {
        v61 = (unsigned __int16 *)v64;
        goto LABEL_54;
      }
    }
  }
  else
  {
    if ( (unsigned int)IsNullGuid(&a2->tagged_union.clsid) )
      return 2147942487LL;
    EnterCriticalSection(&ClassStoreBindList);
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    for ( i = *((_DWORD *)this + 284); i != *((_DWORD *)this + 285); i = (i + 1) % 0x14 )
    {
      v26 = 28LL * i;
      if ( (unsigned int)IsExpired(&SystemTimeAsFileTime, (FILETIME *)((char *)this + v26 + 596)) )
      {
        v27 = *((_DWORD *)this + 284);
        --*((_DWORD *)this + 286);
        v28 = gDebug == 0;
        *((_DWORD *)this + 284) = (v27 + 1) % 0x14u;
        if ( !v28 )
          _DebugMsg(2, 0xC8Bu);
      }
      else if ( a2->tagged_union.pFileExt == *(LPOLESTR *)((char *)this + v26 + 576)
             && *(_QWORD *)a2->tagged_union.ByObjectId.ObjectId.Data4 == *(_QWORD *)((char *)this + v26 + 584)
             && v58->dwContext == *(_DWORD *)((char *)this + v26 + 592) )
      {
        if ( gDebug )
          _DebugMsg(2, 0xC8Cu);
        LODWORD(v6) = -2147221148;
        break;
      }
    }
    LeaveCriticalSection(&ClassStoreBindList);
    result = 2147746148LL;
    if ( (_DWORD)v6 != -2147221148 )
    {
      StringFromGUID(&a2->tagged_union.clsid, v65);
      result = StringCchPrintfW(v66, 0x3E8u, L"(%s=%s*)", L"cOMClassID", v65);
      if ( (int)result >= 0 )
      {
        v6 = v57;
        v11 = v66;
        v12 = v55;
        goto LABEL_54;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001d240  push    rbp
0x18001d242  push    rbx
0x18001d243  push    rsi
0x18001d244  push    rdi
0x18001d245  push    r12
0x18001d247  push    r13
0x18001d249  push    r14
0x18001d24b  push    r15
0x18001d24d  lea     rbp, [rsp-1038h]
0x18001d255  mov     eax, 1138h
0x18001d25a  call    _alloca_probe
0x18001d25f  sub     rsp, rax
0x18001d262  mov     rax, cs:__security_cookie
0x18001d269  xor     rax, rsp
0x18001d26c  mov     [rbp+1070h+var_50], rax
0x18001d273  xor     ebx, ebx
0x18001d275  mov     [rsp+1170h+var_10F8], r8
0x18001d27a  mov     r14, rdx
0x18001d27d  mov     qword ptr [rbp+1070h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x18001d281  mov     rsi, rcx
0x18001d284  mov     [rsp+1170h+var_1100], rbx
0x18001d289  xor     edx, edx; Val
0x18001d28b  mov     r8d, 0D0h; Size
0x18001d291  mov     rcx, r9; void *
0x18001d294  mov     r12d, ebx
0x18001d297  mov     r13, r9
0x18001d29a  call    memset_0
0x18001d29f  cmp     [rsi+218h], ebx
0x18001d2a5  jnz     short loc_18001D2B1
0x18001d2a7  mov     eax, 80004005h
0x18001d2ac  jmp     loc_18001D948
0x18001d2b1  mov     ecx, [r14]
0x18001d2b4  lea     r15, [rbp+1070h+var_820]
0x18001d2bb  mov     [rbp+1070h+var_10E0], rbx
0x18001d2bf  mov     edi, 1
0x18001d2c4  mov     [rsp+1170h+var_110C], edi
0x18001d2c8  test    ecx, ecx
0x18001d2ca  jz      loc_18001D4B3
0x18001d2d0  sub     ecx, edi
0x18001d2d2  jz      loc_18001D3DE
0x18001d2d8  sub     ecx, 3
0x18001d2db  jz      loc_18001D397
0x18001d2e1  sub     ecx, edi
0x18001d2e3  jz      short loc_18001D360
0x18001d2e5  cmp     ecx, edi
0x18001d2e7  jz      short loc_18001D2F3
0x18001d2e9  mov     eax, 80004001h
0x18001d2ee  jmp     loc_18001D948
0x18001d2f3  lea     rcx, [r14+8]; struct _GUID *
0x18001d2f7  call    ?IsNullGuid@@YAHAEBU_GUID@@@Z; IsNullGuid(_GUID const &)
0x18001d2fc  test    eax, eax
0x18001d2fe  jnz     loc_18001D4C3
0x18001d304  lea     r8, [rsp+1170h+ppszDestData]; ppszDestData
0x18001d309  mov     [rsp+1170h+ppszDestData], rbx
0x18001d30e  lea     edx, [rax+10h]; dwSrcLen
0x18001d311  lea     rcx, [r14+8]; pbSrcData
0x18001d315  call    cs:__imp_ADsEncodeBinaryData
0x18001d31b  mov     rax, [rsp+1170h+ppszDestData]
0x18001d320  lea     r9, aObjectguid; "objectGUID"
0x18001d327  lea     r8, aSS; "(%s=%s)"
0x18001d32e  mov     [rsp+1170h+var_1150], rax
0x18001d333  mov     edx, 3E8h; unsigned __int64
0x18001d338  lea     rcx, [rbp+1070h+var_820]; unsigned __int16 *
0x18001d33f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001d344  mov     rcx, [rsp+1170h+ppszDestData]; pMem
0x18001d349  mov     ebx, eax
0x18001d34b  call    cs:__imp_FreeADsMem
0x18001d351  test    ebx, ebx
0x18001d353  jns     short loc_18001D35C
0x18001d355  mov     eax, ebx
0x18001d357  jmp     loc_18001D948
0x18001d35c  xor     ebx, ebx
0x18001d35e  jmp     short loc_18001D390
0x18001d360  mov     rcx, [r14+8]; unsigned __int16 *
0x18001d364  test    rcx, rcx
0x18001d367  jz      loc_18001D4C3
0x18001d36d  cmp     [rcx], bx
0x18001d370  jz      loc_18001D4C3
0x18001d376  lea     rdx, [rsp+1170h+var_1100]; unsigned __int16 **
0x18001d37b  call    ?GetEscapedNameFilter@@YAJPEBGPEAPEAG@Z; GetEscapedNameFilter(ushort const *,ushort * *)
0x18001d380  test    eax, eax
0x18001d382  js      loc_18001D948
0x18001d388  mov     r12, [rsp+1170h+var_1100]
0x18001d38d  mov     r15, r12
0x18001d390  mov     edi, ebx
0x18001d392  jmp     loc_18001D624
0x18001d397  mov     rax, [r14+8]
0x18001d39b  test    rax, rax
0x18001d39e  jz      loc_18001D4C3
0x18001d3a4  cmp     [rax], bx
0x18001d3a7  jz      loc_18001D4C3
0x18001d3ad  lea     r9, aComprogid; "cOMProgID"
0x18001d3b4  mov     [rsp+1170h+var_1150], rax
0x18001d3b9  lea     r8, aSS; "(%s=%s)"
0x18001d3c0  mov     edx, 3E8h; unsigned __int64
0x18001d3c5  lea     rcx, [rbp+1070h+var_820]; unsigned __int16 *
0x18001d3cc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001d3d1  test    eax, eax
0x18001d3d3  jns     loc_18001D624
0x18001d3d9  jmp     loc_18001D948
0x18001d3de  mov     rax, [r14+8]
0x18001d3e2  test    rax, rax
0x18001d3e5  jz      loc_18001D4C3
0x18001d3eb  cmp     [rax], bx
0x18001d3ee  jz      loc_18001D4C3
0x18001d3f4  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001d3f8  inc     rcx
0x18001d3fb  cmp     [rax+rcx*2], bx
0x18001d3ff  jnz     short loc_18001D3F8
0x18001d401  cmp     rcx, 9
0x18001d405  ja      loc_18001D4C3
0x18001d40b  mov     edx, 7FFFFFFEh
0x18001d410  lea     rcx, [rbp+1070h+var_890]
0x18001d417  mov     r8d, 0Ah
0x18001d41d  test    rdx, rdx
0x18001d420  jz      short loc_18001D440
0x18001d422  movzx   r9d, word ptr [rax]
0x18001d426  test    r9w, r9w
0x18001d42a  jz      short loc_18001D440
0x18001d42c  mov     [rcx], r9w
0x18001d430  add     rax, 2
0x18001d434  add     rcx, 2
0x18001d438  dec     rdx
0x18001d43b  sub     r8, rdi
0x18001d43e  jnz     short loc_18001D41D
0x18001d440  mov     rax, r8
0x18001d443  lea     rdx, [rcx-2]
0x18001d447  neg     rax
0x18001d44a  sbb     eax, eax
0x18001d44c  not     eax
0x18001d44e  and     eax, 8007007Ah
0x18001d453  test    r8, r8
0x18001d456  cmovnz  rdx, rcx
0x18001d45a  mov     [rdx], bx
0x18001d45d  jz      loc_18001D948
0x18001d463  lea     rcx, [rbp+1070h+var_890]
0x18001d46a  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x18001d470  lea     rax, [rbp+1070h+var_890]
0x18001d477  mov     edx, 3E8h; unsigned __int64
0x18001d47c  lea     r9, aFileextpriorit; "fileExtPriority"
0x18001d483  mov     [rsp+1170h+var_1150], rax
0x18001d488  lea     r8, aSS_1; "(%s=%s*)"
0x18001d48f  lea     rcx, [rbp+1070h+var_820]; unsigned __int16 *
0x18001d496  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001d49b  test    eax, eax
0x18001d49d  js      loc_18001D948
0x18001d4a3  lea     rax, [rbp+1070h+var_890]
0x18001d4aa  mov     [rbp+1070h+var_10E0], rax
0x18001d4ae  jmp     loc_18001D624
0x18001d4b3  lea     r15, [r14+8]
0x18001d4b7  mov     rcx, r15; struct _GUID *
0x18001d4ba  call    ?IsNullGuid@@YAHAEBU_GUID@@@Z; IsNullGuid(_GUID const &)
0x18001d4bf  test    eax, eax
0x18001d4c1  jz      short loc_18001D4CD
0x18001d4c3  mov     eax, 80070057h
0x18001d4c8  jmp     loc_18001D948
0x18001d4cd  lea     rcx, ?ClassStoreBindList@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001d4d4  call    cs:__imp_EnterCriticalSection
0x18001d4da  lea     rcx, [rbp+1070h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001d4de  call    cs:__imp_GetSystemTimeAsFileTime
0x18001d4e4  mov     edi, [rsi+470h]
0x18001d4ea  jmp     loc_18001D58C
0x18001d4ef  mov     eax, edi
0x18001d4f1  lea     rdx, [rsi+254h]
0x18001d4f8  imul    rbx, rax, 1Ch
0x18001d4fc  lea     rcx, [rbp+1070h+SystemTimeAsFileTime]; lpFileTime1
0x18001d500  add     rdx, rbx; lpFileTime2
0x18001d503  call    ?IsExpired@@YAHPEAU_FILETIME@@0@Z; IsExpired(_FILETIME *,_FILETIME *)
0x18001d508  test    eax, eax
0x18001d50a  jz      short loc_18001D54B
0x18001d50c  mov     ecx, [rsi+470h]
0x18001d512  mov     eax, 0CCCCCCCDh
0x18001d517  dec     dword ptr [rsi+478h]
0x18001d51d  inc     ecx
0x18001d51f  mul     ecx
0x18001d521  xor     ebx, ebx
0x18001d523  shr     edx, 4
0x18001d526  lea     eax, [rdx+rdx*4]
0x18001d529  shl     eax, 2
0x18001d52c  sub     ecx, eax
0x18001d52e  cmp     cs:?gDebug@@3KA, ebx; ulong gDebug
0x18001d534  mov     [rsi+470h], ecx
0x18001d53a  jz      short loc_18001D578
0x18001d53c  mov     edx, 0C8Bh; unsigned int
0x18001d541  lea     ecx, [rbx+2]; unsigned int
0x18001d544  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18001d549  jmp     short loc_18001D578
0x18001d54b  mov     rax, [r15]
0x18001d54e  cmp     rax, [rbx+rsi+240h]
0x18001d556  jnz     short loc_18001D576
0x18001d558  mov     rax, [r15+8]
0x18001d55c  cmp     rax, [rbx+rsi+248h]
0x18001d564  jnz     short loc_18001D576
0x18001d566  mov     rcx, [rsp+1170h+var_10F8]
0x18001d56b  mov     eax, [rbx+rsi+250h]
0x18001d572  cmp     [rcx], eax
0x18001d574  jz      short loc_18001D59A
0x18001d576  xor     ebx, ebx
0x18001d578  inc     edi
0x18001d57a  mov     eax, 0CCCCCCCDh
0x18001d57f  mul     edi
0x18001d581  shr     edx, 4
0x18001d584  lea     eax, [rdx+rdx*4]
0x18001d587  shl     eax, 2
0x18001d58a  sub     edi, eax
0x18001d58c  cmp     edi, [rsi+474h]
0x18001d592  jnz     loc_18001D4EF
0x18001d598  jmp     short loc_18001D5B7
0x18001d59a  xor     ebx, ebx
0x18001d59c  cmp     cs:?gDebug@@3KA, ebx; ulong gDebug
0x18001d5a2  jz      short loc_18001D5B1
0x18001d5a4  mov     edx, 0C8Ch; unsigned int
0x18001d5a9  lea     ecx, [rbx+2]; unsigned int
0x18001d5ac  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18001d5b1  mov     r12d, 80040164h
0x18001d5b7  lea     rcx, ?ClassStoreBindList@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001d5be  call    cs:__imp_LeaveCriticalSection
0x18001d5c4  mov     eax, 80040164h
0x18001d5c9  cmp     r12d, eax
0x18001d5cc  jz      loc_18001D948
0x18001d5d2  lea     rdx, [rbp+1070h+var_870]; unsigned __int16 *
0x18001d5d9  mov     rcx, r15; struct _GUID *
0x18001d5dc  call    ?StringFromGUID@@YAHAEBU_GUID@@PEAG@Z; StringFromGUID(_GUID const &,ushort *)
0x18001d5e1  lea     rax, [rbp+1070h+var_870]
0x18001d5e8  mov     edx, 3E8h; unsigned __int64
0x18001d5ed  lea     r9, aComclassid; "cOMClassID"
0x18001d5f4  mov     [rsp+1170h+var_1150], rax
0x18001d5f9  lea     r8, aSS_1; "(%s=%s*)"
0x18001d600  lea     rcx, [rbp+1070h+var_820]; unsigned __int16 *
0x18001d607  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001d60c  test    eax, eax
0x18001d60e  js      loc_18001D948
0x18001d614  mov     r12, [rsp+1170h+var_1100]
0x18001d619  lea     r15, [rbp+1070h+var_820]
0x18001d620  mov     edi, [rsp+1170h+var_110C]
0x18001d624  mov     rcx, [rsi+228h]
0x18001d62b  lea     rax, [rbp+1070h+var_10E8]
0x18001d62f  mov     r9d, 15h
0x18001d635  mov     [rsp+1170h+var_1150], rax
0x18001d63a  lea     r8, ?pszInstallInfoAttrNames@@3PAPEAGA; ushort * near * pszInstallInfoAttrNames
0x18001d641  mov     [rsp+1170h+var_1110], ebx
0x18001d645  mov     rdx, r15
0x18001d648  mov     [rbp+1070h+var_10E8], rbx
0x18001d64c  call    cs:__imp_ADSIExecuteSearch
0x18001d652  cmp     cs:?gDebug@@3KA, 0; ulong gDebug
0x18001d659  mov     ebx, eax
0x18001d65b  jz      short loc_18001D66F
0x18001d65d  mov     r8, r15
0x18001d660  mov     edx, 0C8Dh; unsigned int
0x18001d665  mov     ecx, 2; unsigned int
0x18001d66a  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18001d66f  test    ebx, ebx
0x18001d671  js      loc_18001D917
0x18001d677  mov     rax, [rsi+480h]
0x18001d67e  lea     r15, [rsi+230h]
0x18001d685  mov     r8, [rsp+1170h+var_10F8]; struct tagQUERYCONTEXT *
0x18001d68a  mov     r9, r14; struct __MIDL___MIDL_itf_wtypes_0000_0001_0001 *
0x18001d68d  mov     rdx, [rbp+1070h+var_10E8]; void *
0x18001d691  mov     rcx, [rsi+228h]; void *
0x18001d698  mov     [rsp+1170h+var_1118], rax; unsigned __int16 *
0x18001d69d  lea     rax, [rbp+1070h+var_10D8]
0x18001d6a1  mov     [rsp+1170h+var_1120], r15; struct _GUID *
0x18001d6a6  mov     [rsp+1170h+var_1128], edi; int
0x18001d6aa  mov     [rsp+1170h+var_1130], rax; unsigned int *
0x18001d6af  lea     rax, [rbp+1070h+var_10B0]
0x18001d6b3  mov     [rsp+1170h+var_1138], rax; struct tagPACKAGEDISPINFO *
0x18001d6b8  lea     rax, [rsp+1170h+var_1110]
0x18001d6bd  mov     [rsp+1170h+var_1140], rax; unsigned int *
0x18001d6c2  mov     rax, [rbp+1070h+var_10E0]
0x18001d6c6  mov     dword ptr [rsp+1170h+var_1148], 0Ah; unsigned int
0x18001d6ce  mov     [rsp+1170h+var_1150], rax; unsigned __int16 *
0x18001d6d3  call    ?FetchInstallData@@YAJPEAX0PEAUtagQUERYCONTEXT@@PEAU__MIDL___MIDL_itf_wtypes_0000_0001_0001@@PEBGKPEAKPEAUtagPACKAGEDISPINFO@@PEAIHPEAU_GUID@@3@Z; FetchInstallData(void *,void *,tagQUERYCONTEXT *,__MIDL___MIDL_itf_wtypes_0000_0001_0001 *,ushort const *,ulong,ulong *,tagPACKAGEDISPINFO *,uint *,int,_GUID *,ushort const *)
0x18001d6d8  xor     edx, edx
0x18001d6da  mov     ebx, eax
0x18001d6dc  cmp     cs:?gDebug@@3KA, edx; ulong gDebug
0x18001d6e2  jz      short loc_18001D6FD
0x18001d6e4  mov     r8d, [rsp+1170h+var_1110]
0x18001d6e9  mov     r9d, eax
0x18001d6ec  mov     edx, 0C8Eh; unsigned int
0x18001d6f1  mov     ecx, 2; unsigned int
0x18001d6f6  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18001d6fb  xor     edx, edx
0x18001d6fd  mov     edi, [rsp+1170h+var_1110]
0x18001d701  test    edi, edi
0x18001d703  jnz     loc_18001D7CB
0x18001d709  mov     ebx, 80040169h
0x18001d70e  cmp     [r14], edx
0x18001d711  jnz     loc_18001D8EF
0x18001d717  lea     rcx, ?ClassStoreBindList@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001d71e  call    cs:__imp_EnterCriticalSection
0x18001d724  cmp     dword ptr [rsi+478h], 13h
0x18001d72b  jnb     loc_18001D7B9
0x18001d731  mov     eax, [rsi+474h]
0x18001d737  mov     r8, 430E23400h
0x18001d741  movups  xmm0, xmmword ptr [r14+8]
0x18001d746  imul    rcx, rax, 1Ch
0x18001d74a  movdqu  xmmword ptr [rcx+rsi+240h], xmm0
0x18001d753  mov     eax, [rsi+474h]
0x18001d759  imul    rcx, rax, 1Ch
0x18001d75d  mov     rax, [rsp+1170h+var_10F8]
  ... truncated ...
```
