# ShieldProvider::QueryAndActionManager::QueryAllVolumesProtectionState(ulong *,Shield_DevVolumeInfo * *)

- ea: `0x180032464`
- end: `0x180032db7`
- name: `?QueryAllVolumesProtectionState@QueryAndActionManager@ShieldProvider@@QEAAJPEAKPEAPEAUShield_DevVolumeInfo@@@Z`
- size: `2387`
- prototype: `__int64 __fastcall(ShieldProvider::QueryAndActionManager *__hidden this, unsigned int *, struct Shield_DevVolumeInfo **)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180022a50`

## callees

- `0x180004710`
- `0x180004ae0`
- `0x18000517c`
- `0x18000d7fc`
- `0x180010ff0`
- `0x180015894`
- `0x1800158f4`
- `0x1800159a0`
- `0x180016d08`
- `0x180023648`
- `0x180029084`
- `0x18002e14c`
- `0x180030b28`
- `0x180032464`
- `0x180033f9c`
- `0x1800d3750`
- `0x1800e1690`
- `0x1800e1764`
- `0x1800e17e8`

## import_xrefs

- `KERNEL32!FindVolumeClose` at `0x180032d40`
- `KERNEL32!FindVolumeClose` at `0x180032d40`
- `KERNEL32!FindFirstVolumeW` at `0x180032537`
- `KERNEL32!FindFirstVolumeW` at `0x180032537`
- `KERNEL32!GetVolumeInformationW` at `0x18003272c`
- `KERNEL32!GetVolumeInformationW` at `0x18003272c`
- `KERNEL32!FindNextVolumeW` at `0x18003285e`
- `KERNEL32!FindNextVolumeW` at `0x18003285e`
- `ole32!CoTaskMemFree` at `0x180032bef`
- `ole32!CoTaskMemFree` at `0x180032c07`
- `ole32!CoTaskMemFree` at `0x180032c78`
- `ole32!CoTaskMemFree` at `0x180032c88`
- `ole32!CoTaskMemFree` at `0x180032cc5`
- `ole32!CoTaskMemFree` at `0x180032bef`
- `ole32!CoTaskMemFree` at `0x180032c07`
- `ole32!CoTaskMemFree` at `0x180032c78`
- `ole32!CoTaskMemFree` at `0x180032c88`
- `ole32!CoTaskMemFree` at `0x180032cc5`

## string_xrefs

- `0x1800324cb`: `SecurityHealthHost.exe`

## pseudocode

```c
__int64 __fastcall ShieldProvider::QueryAndActionManager::QueryAllVolumesProtectionState(
        ShieldProvider::QueryAndActionManager *this,
        unsigned int *a2,
        struct Shield_DevVolumeInfo **a3)
{
  unsigned int *v4; // rdi
  ShieldProvider *v5; // rcx
  unsigned __int16 *v6; // r8
  unsigned __int16 **v7; // rbx
  struct Shield_DevVolumeInfo *v8; // r13
  int LastFailure; // edi
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  HANDLE v12; // r14
  int v13; // eax
  const struct std::nothrow_t *v14; // rdx
  _QWORD *v15; // rcx
  int v16; // edx
  WCHAR *v17; // r9
  ShieldProvider::QueryAndActionManager *v18; // rcx
  int FirstVolumePathName; // eax
  unsigned __int16 *v20; // r8
  __int64 v21; // rax
  int v22; // eax
  wchar_t v23; // dx
  _QWORD *v24; // rcx
  __int64 v25; // rdx
  LPCWSTR v26; // rdi
  DWORD v27; // r10d
  unsigned __int16 *v28; // r8
  __int64 v29; // rax
  int v30; // eax
  unsigned __int64 v31; // rdx
  PVOID *v32; // r10
  __int64 v33; // rdx
  __int64 v34; // r9
  unsigned __int64 v35; // r8
  unsigned __int64 v36; // rcx
  int v37; // eax
  unsigned __int64 v38; // rcx
  __int64 v39; // rax
  unsigned __int64 v40; // r13
  struct Shield_DevVolumeInfo *v41; // r12
  __int64 v42; // r14
  unsigned __int16 **v43; // rdx
  __int64 v44; // rax
  CommonUtil *v45; // r12
  int v46; // eax
  struct Shield_DevVolumeInfo *v47; // rcx
  __int64 v48; // rax
  __int64 v49; // r12
  int v50; // eax
  unsigned __int64 v51; // r14
  void *v52; // rcx
  void *v53; // rcx
  unsigned __int64 v54; // r14
  __int64 v55; // r12
  void *v56; // rcx
  void *v57; // rcx
  __int128 v59; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v60; // [rsp+50h] [rbp-B0h]
  struct Shield_DevVolumeInfo *v61; // [rsp+58h] [rbp-A8h]
  int v62; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 **v63; // [rsp+68h] [rbp-98h] BYREF
  struct Shield_DevVolumeInfo *v64; // [rsp+70h] [rbp-90h] BYREF
  HANDLE hFindVolume; // [rsp+78h] [rbp-88h]
  LPCWSTR lpRootPathName[2]; // [rsp+80h] [rbp-80h] BYREF
  int v67; // [rsp+90h] [rbp-70h]
  int v68; // [rsp+94h] [rbp-6Ch]
  unsigned int *v69; // [rsp+98h] [rbp-68h]
  struct Shield_DevVolumeInfo **v70; // [rsp+A0h] [rbp-60h]
  WCHAR szVolumeName[264]; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t S[264]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v69 = a2;
  v70 = a3;
  v4 = a2;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_DefenderPerfModeUX>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_DefenderPerfModeUX>::GetImpl'::`2'::impl,
    a2);
  if ( !v4 || !a3 )
  {
    v10 = WPP_GLOBAL_Control;
    LastFailure = -2147024809;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return (unsigned int)LastFailure;
    v11 = 180;
LABEL_147:
    WPP_SF_d(v10[2], v11, WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids, (unsigned int)LastFailure);
    return (unsigned int)LastFailure;
  }
  LOBYTE(v5) = (_BYTE)g_fDevMode;
  v7 = 0;
  v61 = 0;
  v63 = 0;
  v8 = 0;
  v64 = 0;
  LastFailure = ShieldProvider::ValidateCaller(v5, (bool)L"SecurityHealthHost.exe", v6);
  if ( LastFailure < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return (unsigned int)LastFailure;
    v11 = 181;
    goto LABEL_147;
  }
  memset_0(szVolumeName, 0, 0x208u);
  hFindVolume = FindFirstVolumeW(szVolumeName, 0x104u);
  v12 = hFindVolume;
  if ( hFindVolume == (HANDLE)-1LL )
  {
    LastFailure = HrGetLastFailure();
    if ( LastFailure < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return (unsigned int)LastFailure;
      v11 = 182;
      goto LABEL_147;
    }
  }
  v60 = 0;
  v59 = 0;
  while ( 1 )
  {
    v62 = 0;
    v13 = MpQueryDevVolumeProtectionState(szVolumeName, &v62);
    if ( v13 < 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_18;
      v16 = 183;
      v17 = szVolumeName;
      goto LABEL_17;
    }
    v18 = (ShieldProvider::QueryAndActionManager *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        184,
        (unsigned int)WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids,
        (unsigned int)szVolumeName,
        v62);
    if ( v7 )
    {
      operator delete(v7, v14);
      v63 = 0;
    }
    FirstVolumePathName = ShieldProvider::QueryAndActionManager::GetFirstVolumePathName(
                            v18,
                            szVolumeName,
                            (unsigned __int16 **)&v63);
    LastFailure = FirstVolumePathName;
    if ( FirstVolumePathName < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          185,
          (unsigned int)WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids,
          (unsigned int)szVolumeName,
          FirstVolumePathName);
      v7 = v63;
      LastFailure = 0;
      goto LABEL_62;
    }
    v7 = v63;
    if ( !v63 )
      goto LABEL_151;
    v21 = -1;
    do
      ++v21;
    while ( *((_WORD *)v63 + v21) );
    if ( v21 )
    {
      v68 = 0;
      v67 = v62;
      *(_OWORD *)lpRootPathName = 0;
      v22 = CommonUtil::UtilCoDuplicateString((CommonUtil *)lpRootPathName, v63, v20);
      if ( v22 < 0 )
      {
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_18;
        v25 = 187;
        goto LABEL_37;
      }
      wmemset(S, v23, 0x104u);
      v26 = lpRootPathName[0];
      if ( !GetVolumeInformationW(lpRootPathName[0], S, v27, 0, 0, 0, 0, 0) )
      {
        LOBYTE(v13) = HrGetLastFailure();
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_18;
        v16 = 188;
        LODWORD(v17) = (_DWORD)v26;
LABEL_17:
        WPP_SF_Sd(v15[2], v16, (unsigned int)WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids, (_DWORD)v17, v13);
LABEL_18:
        LastFailure = 0;
        goto LABEL_62;
      }
      v29 = -1;
      do
        ++v29;
      while ( S[v29] );
      if ( v29 )
      {
        v22 = CommonUtil::UtilCoDuplicateString((CommonUtil *)&lpRootPathName[1], (unsigned __int16 **)S, v28);
        if ( v22 < 0 )
        {
          v24 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_18;
          v25 = 190;
LABEL_37:
          WPP_SF_d(v24[2], v25, WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids, (unsigned int)v22);
          goto LABEL_18;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 189, WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids, v26);
        lpRootPathName[1] = 0;
      }
      v30 = CommonUtil::HrStdPushBack<CommonUtil::CStdVector<Shield_DevVolumeInfo,std::allocator<Shield_DevVolumeInfo>>,Shield_DevVolumeInfo>(
              &v59,
              lpRootPathName);
      LastFailure = v30;
      if ( v30 < 0 )
      {
        v32 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_118;
        v33 = 191;
LABEL_53:
        v34 = (unsigned int)v30;
        goto LABEL_54;
      }
    }
    else
    {
LABEL_151:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          186,
          WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids,
          szVolumeName);
    }
LABEL_62:
    if ( FindNextVolumeW(v12, szVolumeName, 0x104u) )
      goto LABEL_65;
    v30 = HrGetLastFailure();
    LastFailure = v30;
    if ( v30 == -2147024878 )
      break;
    if ( v30 < 0 )
    {
      v32 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_118;
      v33 = 193;
      goto LABEL_53;
    }
LABEL_65:
    if ( LastFailure < 0 )
    {
      v32 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_67;
    }
  }
  v32 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 192, WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids);
    v32 = (PVOID *)WPP_GLOBAL_Control;
  }
  LastFailure = 0;
LABEL_67:
  v36 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v59 + 1) - v59) >> 3);
  if ( v36 )
  {
    v31 = 8 * ((__int64)(*((_QWORD *)&v59 + 1) - v59) >> 3) / 0x18uLL;
    if ( v31 != v36 )
    {
      LastFailure = -2147024809;
LABEL_78:
      if ( v32 == &WPP_GLOBAL_Control || (*((_BYTE *)v32 + 28) & 4) == 0 )
        goto LABEL_118;
      v33 = 194;
      v34 = (unsigned int)LastFailure;
LABEL_54:
      WPP_SF_d(v32[2], v33, WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids, v34);
      goto LABEL_117;
    }
    LOBYTE(v35) = 1;
    v37 = CommonUtil::UtilCoTaskMemAlloc(
            (CommonUtil *)&v64,
            (void **)(8 * ((__int64)(*((_QWORD *)&v59 + 1) - v59) >> 3)),
            v35,
            8 * ((__int64)(*((_QWORD *)&v59 + 1) - v59) >> 3));
    v32 = (PVOID *)WPP_GLOBAL_Control;
    LastFailure = v37;
    if ( v37 < 0 )
      goto LABEL_78;
    v8 = v64;
    v61 = v64;
  }
  if ( v32 != &WPP_GLOBAL_Control && (*((_BYTE *)v32 + 28) & 0x10) != 0 )
  {
    WPP_SF_d(
      v32[2],
      195,
      WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids,
      0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v59 + 1) - v59) >> 3));
    v32 = (PVOID *)WPP_GLOBAL_Control;
  }
  v38 = 0;
  if ( 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v59 + 1) - v59) >> 3) )
  {
    do
    {
      v39 = 3 * v38++;
      *((_QWORD *)v8 + v39) = 0;
      *((_QWORD *)v8 + v39 + 1) = 0;
    }
    while ( v38 < 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v59 + 1) - v59) >> 3) );
    v32 = (PVOID *)WPP_GLOBAL_Control;
  }
  v40 = 0;
  v41 = v61;
  if ( !(0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v59 + 1) - v59) >> 3)) )
  {
LABEL_116:
    *v69 = -1431655765 * ((__int64)(*((_QWORD *)&v59 + 1) - v59) >> 3);
    *v70 = v41;
    v8 = 0;
    goto LABEL_117;
  }
  while ( 2 )
  {
    if ( v32 != &WPP_GLOBAL_Control && (*((_BYTE *)v32 + 28) & 0x10) != 0 )
      WPP_SF_SS(
        (unsigned int)v32[2],
        196,
        (unsigned int)WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids,
        *(_QWORD *)(v59 + 24 * v40),
        *(_QWORD *)(v59 + 24 * v40 + 8));
    v42 = 3 * v40;
    v43 = *(unsigned __int16 ***)(v59 + 24 * v40);
    if ( !v43 )
      goto LABEL_98;
    v44 = -1;
    do
      ++v44;
    while ( *((_WORD *)v43 + v44) );
    if ( !v44 )
    {
LABEL_98:
      v47 = v61;
      *((_QWORD *)v61 + 3 * v40) = 0;
LABEL_99:
      v31 = *(_QWORD *)(v59 + 24 * v40 + 8);
      if ( !v31 )
        goto LABEL_108;
      v48 = -1;
      do
        ++v48;
      while ( *(_WORD *)(v31 + 2 * v48) );
      if ( v48 )
      {
        v49 = (__int64)v47 + 24 * v40;
        v50 = CommonUtil::UtilCoDuplicateString((CommonUtil *)(v49 + 8), (unsigned __int16 **)v31, 0);
        LastFailure = v50;
        if ( v50 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              198,
              WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids,
              (unsigned int)v50);
          *(_QWORD *)(v49 + 8) = 0;
          goto LABEL_115;
        }
      }
      else
      {
LABEL_108:
        *((_QWORD *)v47 + 3 * v40 + 1) = 0;
      }
      ++v40;
      v41 = v61;
      *((_DWORD *)v61 + 2 * v42 + 4) = *(_DWORD *)(v59 + 8 * v42 + 16);
      if ( v40 >= 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v59 + 1) - v59) >> 3) )
        goto LABEL_116;
      v32 = (PVOID *)WPP_GLOBAL_Control;
      continue;
    }
    break;
  }
  v45 = (struct Shield_DevVolumeInfo *)((char *)v41 + 24 * v40);
  v46 = CommonUtil::UtilCoDuplicateString(v45, v43, 0);
  LastFailure = v46;
  if ( v46 >= 0 )
  {
    v47 = v61;
    goto LABEL_99;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      197,
      WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids,
      (unsigned int)v46);
  *(_QWORD *)v45 = 0;
LABEL_115:
  v8 = v61;
LABEL_117:
  v32 = (PVOID *)WPP_GLOBAL_Control;
LABEL_118:
  v51 = 0;
  if ( 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v59 + 1) - v59) >> 3) )
  {
    do
    {
      v52 = *(void **)(v59 + 24 * v51);
      if ( v52 )
        CoTaskMemFree(v52);
      v53 = *(void **)(v59 + 24 * v51 + 8);
      if ( v53 )
        CoTaskMemFree(v53);
      ++v51;
    }
    while ( v51 < 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v59 + 1) - v59) >> 3) );
    v32 = (PVOID *)WPP_GLOBAL_Control;
    v7 = v63;
  }
  if ( v8 )
  {
    v54 = 0;
    if ( 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v59 + 1) - v59) >> 3) )
    {
      do
      {
        v55 = 3 * v54;
        v56 = (void *)*((_QWORD *)v8 + 3 * v54);
        if ( v56 )
          CoTaskMemFree(v56);
        v57 = (void *)*((_QWORD *)v8 + 3 * v54 + 1);
        if ( v57 )
          CoTaskMemFree(v57);
        *((_QWORD *)v8 + 3 * v54++) = 0;
        *((_QWORD *)v8 + v55 + 1) = 0;
      }
      while ( v54 < 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v59 + 1) - v59) >> 3) );
      v7 = v63;
    }
    CoTaskMemFree(v8);
    v32 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( LastFailure < 0 && v32 != &WPP_GLOBAL_Control && (*((_BYTE *)v32 + 28) & 1) != 0 )
    WPP_SF_d(v32[2], 199, WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids, (unsigned int)LastFailure);
  if ( (_QWORD)v59 )
  {
    std::_Deallocate<16>(v59, 8 * ((v60 - (__int64)v59) >> 3));
    v60 = 0;
    v59 = 0;
  }
  if ( hFindVolume != (HANDLE)-1LL )
    FindVolumeClose(hFindVolume);
  if ( v7 )
    operator delete(v7, (const struct std::nothrow_t *)v31);
  return (unsigned int)LastFailure;
}

```

## disassembly

```asm
0x180032464  mov     [rsp-8+arg_0], rbx
0x180032469  push    rbp
0x18003246a  push    rsi
0x18003246b  push    rdi
0x18003246c  push    r12
0x18003246e  push    r13
0x180032470  push    r14
0x180032472  push    r15
0x180032474  lea     rbp, [rsp-3E0h]
0x18003247c  sub     rsp, 4E0h
0x180032483  mov     rax, cs:__security_cookie
0x18003248a  xor     rax, rsp
0x18003248d  mov     [rbp+410h+var_40], rax
0x180032494  mov     rbx, r8
0x180032497  mov     [rbp+410h+var_478], rdx
0x18003249b  mov     [rbp+410h+var_470], rbx
0x18003249f  mov     rdi, rdx
0x1800324a2  mov     dl, 1
0x1800324a4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DefenderPerfModeUX@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DefenderPerfModeUX@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DefenderPerfModeUX> `wil::Feature<__WilFeatureTraits_Feature_DefenderPerfModeUX>::GetImpl(void)'::`2'::impl
0x1800324ab  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DefenderPerfModeUX@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DefenderPerfModeUX>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800324b0  xor     r12d, r12d
0x1800324b3  test    rdi, rdi
0x1800324b6  jz      loc_180032D55
0x1800324bc  test    rbx, rbx
0x1800324bf  jz      loc_180032D55
0x1800324c5  mov     cl, cs:?g_fDevMode@@3_NA; this
0x1800324cb  lea     rdx, aSecurityhealth_4; "SecurityHealthHost.exe"
0x1800324d2  mov     ebx, r12d
0x1800324d5  mov     [rsp+510h+var_4B8], r12
0x1800324da  mov     [rsp+510h+var_4A8], rbx
0x1800324df  mov     r13d, r12d
0x1800324e2  mov     [rsp+510h+var_4A0], r12
0x1800324e7  call    ?ValidateCaller@ShieldProvider@@YAJ_NPEAG@Z; ShieldProvider::ValidateCaller(bool,ushort *)
0x1800324ec  mov     edi, eax
0x1800324ee  test    eax, eax
0x1800324f0  jns     short loc_18003251D
0x1800324f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800324f9  lea     rsi, WPP_GLOBAL_Control
0x180032500  cmp     rcx, rsi
0x180032503  jz      loc_180032D8B
0x180032509  test    byte ptr [rcx+1Ch], 1
0x18003250d  jz      loc_180032D8B
0x180032513  mov     edx, 0B5h
0x180032518  jmp     loc_180032D78
0x18003251d  xor     edx, edx; Val
0x18003251f  lea     rcx, [rbp+410h+szVolumeName]; void *
0x180032523  mov     r8d, 208h; Size
0x180032529  call    memset_0
0x18003252e  mov     edx, 104h; cchBufferLength
0x180032533  lea     rcx, [rbp+410h+szVolumeName]; lpszVolumeName
0x180032537  call    cs:__imp_FindFirstVolumeW
0x18003253d  mov     [rsp+510h+hFindVolume], rax
0x180032542  mov     r14, rax
0x180032545  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180032549  jnz     short loc_180032581
0x18003254b  call    HrGetLastFailure
0x180032550  mov     edi, eax
0x180032552  test    eax, eax
0x180032554  jns     short loc_180032581
0x180032556  mov     rcx, cs:WPP_GLOBAL_Control
0x18003255d  lea     rsi, WPP_GLOBAL_Control
0x180032564  cmp     rcx, rsi
0x180032567  jz      loc_180032D8B
0x18003256d  test    byte ptr [rcx+1Ch], 1
0x180032571  jz      loc_180032D8B
0x180032577  mov     edx, 0B6h
0x18003257c  jmp     loc_180032D78
0x180032581  xorps   xmm0, xmm0
0x180032584  mov     [rsp+510h+var_4C0], r12
0x180032589  movdqu  [rsp+510h+var_4D0], xmm0
0x18003258f  lea     rsi, WPP_GLOBAL_Control
0x180032596  lea     r15, WPP_27b3114456253f3ac0ee88b7c60d6b14_Traceguids
0x18003259d  lea     rdx, [rsp+510h+var_4B0]
0x1800325a2  mov     [rsp+510h+var_4B0], r12d
0x1800325a7  lea     rcx, [rbp+410h+szVolumeName]
0x1800325ab  call    MpQueryDevVolumeProtectionState
0x1800325b0  test    eax, eax
0x1800325b2  jns     short loc_1800325E7
0x1800325b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800325bb  cmp     rcx, rsi
0x1800325be  jz      short loc_1800325DF
0x1800325c0  test    byte ptr [rcx+1Ch], 2
0x1800325c4  jz      short loc_1800325DF
0x1800325c6  mov     edx, 0B7h
0x1800325cb  lea     r9, [rbp+410h+szVolumeName]
0x1800325cf  mov     rcx, [rcx+10h]
0x1800325d3  mov     r8, r15
0x1800325d6  mov     dword ptr [rsp+510h+lpMaximumComponentLength], eax
0x1800325da  call    WPP_SF_Sd
0x1800325df  mov     edi, r12d
0x1800325e2  jmp     loc_180032851
0x1800325e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800325ee  cmp     rcx, rsi
0x1800325f1  jz      short loc_180032616
0x1800325f3  test    byte ptr [rcx+1Ch], 10h
0x1800325f7  jz      short loc_180032616
0x1800325f9  mov     eax, [rsp+510h+var_4B0]
0x1800325fd  lea     r9, [rbp+410h+szVolumeName]
0x180032601  mov     rcx, [rcx+10h]
0x180032605  mov     edx, 0B8h
0x18003260a  mov     r8, r15
0x18003260d  mov     dword ptr [rsp+510h+lpMaximumComponentLength], eax
0x180032611  call    WPP_SF_Sd
0x180032616  test    rbx, rbx
0x180032619  jz      short loc_180032628
0x18003261b  mov     rcx, rbx; void *
0x18003261e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180032623  mov     [rsp+510h+var_4A8], r12
0x180032628  lea     r8, [rsp+510h+var_4A8]; unsigned __int16 **
0x18003262d  lea     rdx, [rbp+410h+szVolumeName]; unsigned __int16 *
0x180032631  call    ?GetFirstVolumePathName@QueryAndActionManager@ShieldProvider@@QEAAJPEBGPEAPEAG@Z; ShieldProvider::QueryAndActionManager::GetFirstVolumePathName(ushort const *,ushort * *)
0x180032636  mov     edi, eax
0x180032638  test    eax, eax
0x18003263a  jns     short loc_180032674
0x18003263c  mov     rcx, cs:WPP_GLOBAL_Control
0x180032643  cmp     rcx, rsi
0x180032646  jz      short loc_180032667
0x180032648  test    byte ptr [rcx+1Ch], 2
0x18003264c  jz      short loc_180032667
0x18003264e  mov     rcx, [rcx+10h]
0x180032652  lea     r9, [rbp+410h+szVolumeName]
0x180032656  mov     edx, 0B9h
0x18003265b  mov     dword ptr [rsp+510h+lpMaximumComponentLength], eax
0x18003265f  mov     r8, r15
0x180032662  call    WPP_SF_Sd
0x180032667  mov     rbx, [rsp+510h+var_4A8]
0x18003266c  mov     edi, r12d
0x18003266f  jmp     loc_180032851
0x180032674  mov     rbx, [rsp+510h+var_4A8]
0x180032679  test    rbx, rbx
0x18003267c  jz      loc_18003282A
0x180032682  or      rax, 0FFFFFFFFFFFFFFFFh
0x180032686  inc     rax
0x180032689  cmp     [rbx+rax*2], r12w
0x18003268e  jnz     short loc_180032686
0x180032690  test    rax, rax
0x180032693  jz      loc_18003282A
0x180032699  mov     eax, [rsp+510h+var_4B0]
0x18003269d  lea     rcx, [rbp+410h+lpRootPathName]; this
0x1800326a1  xorps   xmm0, xmm0
0x1800326a4  mov     [rbp+410h+var_47C], r12d
0x1800326a8  mov     rdx, rbx; unsigned __int16 **
0x1800326ab  mov     [rbp+410h+var_480], eax
0x1800326ae  movdqu  xmmword ptr [rbp+410h+lpRootPathName], xmm0
0x1800326b3  call    ?UtilCoDuplicateString@CommonUtil@@YAJPEAPEAGPEAG@Z; CommonUtil::UtilCoDuplicateString(ushort * *,ushort *)
0x1800326b8  test    eax, eax
0x1800326ba  jns     short loc_1800326EF
0x1800326bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800326c3  cmp     rcx, rsi
0x1800326c6  jz      loc_1800325DF
0x1800326cc  test    byte ptr [rcx+1Ch], 2
0x1800326d0  jz      loc_1800325DF
0x1800326d6  mov     edx, 0BBh
0x1800326db  mov     rcx, [rcx+10h]
0x1800326df  mov     r9d, eax
0x1800326e2  mov     r8, r15
0x1800326e5  call    WPP_SF_d
0x1800326ea  jmp     loc_1800325DF
0x1800326ef  mov     r10d, 104h
0x1800326f5  lea     rcx, [rbp+410h+S]; S
0x1800326fc  mov     r8d, r10d; N
0x1800326ff  call    wmemset
0x180032704  mov     rdi, [rbp+410h+lpRootPathName]
0x180032708  lea     rdx, [rbp+410h+S]; lpVolumeNameBuffer
0x18003270f  mov     [rsp+510h+nFileSystemNameSize], r12d; nFileSystemNameSize
0x180032714  mov     rcx, rdi; lpRootPathName
0x180032717  mov     [rsp+510h+lpFileSystemNameBuffer], r12; lpFileSystemNameBuffer
0x18003271c  xor     r9d, r9d; lpVolumeSerialNumber
0x18003271f  mov     [rsp+510h+lpFileSystemFlags], r12; lpFileSystemFlags
0x180032724  mov     r8d, r10d; nVolumeNameSize
0x180032727  mov     [rsp+510h+lpMaximumComponentLength], r12; lpMaximumComponentLength
0x18003272c  call    cs:__imp_GetVolumeInformationW
0x180032732  test    eax, eax
0x180032734  jnz     short loc_180032762
0x180032736  call    HrGetLastFailure
0x18003273b  mov     rcx, cs:WPP_GLOBAL_Control
0x180032742  cmp     rcx, rsi
0x180032745  jz      loc_1800325DF
0x18003274b  test    byte ptr [rcx+1Ch], 2
0x18003274f  jz      loc_1800325DF
0x180032755  mov     edx, 0BCh
0x18003275a  mov     r9, rdi
0x18003275d  jmp     loc_1800325CF
0x180032762  lea     rcx, [rbp+410h+S]
0x180032769  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003276d  inc     rax
0x180032770  cmp     [rcx+rax*2], r12w
0x180032775  jnz     short loc_18003276D
0x180032777  test    rax, rax
0x18003277a  jnz     short loc_1800327F2
0x18003277c  mov     rcx, cs:WPP_GLOBAL_Control
0x180032783  cmp     rcx, rsi
0x180032786  jz      short loc_1800327A2
0x180032788  test    byte ptr [rcx+1Ch], 2
0x18003278c  jz      short loc_1800327A2
0x18003278e  mov     rcx, [rcx+10h]
0x180032792  mov     edx, 0BDh
0x180032797  mov     r9, rdi
0x18003279a  mov     r8, r15
0x18003279d  call    WPP_SF_S
0x1800327a2  mov     [rbp+410h+lpRootPathName+8], r12
0x1800327a6  lea     rdx, [rbp+410h+lpRootPathName]
0x1800327aa  lea     rcx, [rsp+510h+var_4D0]
0x1800327af  call    ??$HrStdPushBack@V?$CStdVector@UShield_DevVolumeInfo@@V?$allocator@UShield_DevVolumeInfo@@@std@@@CommonUtil@@UShield_DevVolumeInfo@@@CommonUtil@@YAJAEAV?$CStdVector@UShield_DevVolumeInfo@@V?$allocator@UShield_DevVolumeInfo@@@std@@@0@AEBUShield_DevVolumeInfo@@@Z; CommonUtil::HrStdPushBack<CommonUtil::CStdVector<Shield_DevVolumeInfo,std::allocator<Shield_DevVolumeInfo>>,Shield_DevVolumeInfo>(CommonUtil::CStdVector<Shield_DevVolumeInfo,std::allocator<Shield_DevVolumeInfo>> &,Shield_DevVolumeInfo const &)
0x1800327b4  mov     edi, eax
0x1800327b6  test    eax, eax
0x1800327b8  jns     loc_180032851
0x1800327be  mov     r10, cs:WPP_GLOBAL_Control
0x1800327c5  cmp     r10, rsi
0x1800327c8  jz      loc_180032BB6
0x1800327ce  test    byte ptr [r10+1Ch], 1
0x1800327d3  jz      loc_180032BB6
0x1800327d9  mov     edx, 0BFh
0x1800327de  mov     r9d, eax
0x1800327e1  mov     rcx, [r10+10h]
0x1800327e5  mov     r8, r15
0x1800327e8  call    WPP_SF_d
0x1800327ed  jmp     loc_180032BAF
0x1800327f2  lea     rdx, [rbp+410h+S]; unsigned __int16 **
0x1800327f9  lea     rcx, [rbp+410h+lpRootPathName+8]; this
0x1800327fd  call    ?UtilCoDuplicateString@CommonUtil@@YAJPEAPEAGPEAG@Z; CommonUtil::UtilCoDuplicateString(ushort * *,ushort *)
0x180032802  test    eax, eax
0x180032804  jns     short loc_1800327A6
0x180032806  mov     rcx, cs:WPP_GLOBAL_Control
0x18003280d  cmp     rcx, rsi
0x180032810  jz      loc_1800325DF
0x180032816  test    byte ptr [rcx+1Ch], 2
0x18003281a  jz      loc_1800325DF
0x180032820  mov     edx, 0BEh
0x180032825  jmp     loc_1800326DB
0x18003282a  mov     rcx, cs:WPP_GLOBAL_Control
0x180032831  cmp     rcx, rsi
0x180032834  jz      short loc_180032851
0x180032836  test    byte ptr [rcx+1Ch], 2
0x18003283a  jz      short loc_180032851
0x18003283c  mov     rcx, [rcx+10h]
0x180032840  lea     r9, [rbp+410h+szVolumeName]
0x180032844  mov     edx, 0BAh
0x180032849  mov     r8, r15
0x18003284c  call    WPP_SF_S
0x180032851  mov     r8d, 104h; cchBufferLength
0x180032857  lea     rdx, [rbp+410h+szVolumeName]; lpszVolumeName
0x18003285b  mov     rcx, r14; hFindVolume
0x18003285e  call    cs:__imp_FindNextVolumeW
0x180032864  test    eax, eax
0x180032866  jnz     short loc_18003287A
0x180032868  call    HrGetLastFailure
0x18003286d  mov     edi, eax
0x18003286f  cmp     eax, 80070012h
0x180032874  jz      short loc_1800328F1
0x180032876  test    eax, eax
0x180032878  js      short loc_1800328CC
0x18003287a  test    edi, edi
0x18003287c  jns     loc_18003259D
0x180032882  mov     r10, cs:WPP_GLOBAL_Control
0x180032889  mov     rcx, qword ptr [rsp+510h+var_4D0+8]
0x18003288e  mov     r14, 0AAAAAAAAAAAAAAABh
0x180032898  sub     rcx, qword ptr [rsp+510h+var_4D0]
0x18003289d  sar     rcx, 3
0x1800328a1  imul    rcx, r14
0x1800328a5  test    rcx, rcx
0x1800328a8  jz      loc_18003296C
0x1800328ae  lea     r9, [rcx+rcx*2]
0x1800328b2  mov     rax, r14
0x1800328b5  shl     r9, 3; bool
0x1800328b9  mul     r9
0x1800328bc  shr     rdx, 4
0x1800328c0  cmp     rdx, rcx
0x1800328c3  jz      short loc_180032924
0x1800328c5  mov     edi, 80070057h
0x1800328ca  jmp     short loc_180032941
0x1800328cc  mov     r10, cs:WPP_GLOBAL_Control
0x1800328d3  cmp     r10, rsi
0x1800328d6  jz      loc_180032BB6
0x1800328dc  test    byte ptr [r10+1Ch], 1
0x1800328e1  jz      loc_180032BB6
0x1800328e7  mov     edx, 0C1h
0x1800328ec  jmp     loc_1800327DE
0x1800328f1  mov     r10, cs:WPP_GLOBAL_Control
0x1800328f8  cmp     r10, rsi
0x1800328fb  jz      short loc_18003291C
0x1800328fd  test    byte ptr [r10+1Ch], 4
0x180032902  jz      short loc_18003291C
0x180032904  mov     rcx, [r10+10h]
0x180032908  mov     edx, 0C0h
0x18003290d  mov     r8, r15
0x180032910  call    WPP_SF_
0x180032915  mov     r10, cs:WPP_GLOBAL_Control
0x18003291c  mov     edi, r12d
0x18003291f  jmp     loc_180032889
0x180032924  mov     r8b, 1; unsigned __int64
0x180032927  lea     rcx, [rsp+510h+var_4A0]; this
0x18003292c  mov     rdx, r9; void **
0x18003292f  call    ?UtilCoTaskMemAlloc@CommonUtil@@YAJPEAPEAX_K_N@Z; CommonUtil::UtilCoTaskMemAlloc(void * *,unsigned __int64,bool)
0x180032934  mov     r10, cs:WPP_GLOBAL_Control
0x18003293b  mov     edi, eax
0x18003293d  test    eax, eax
0x18003293f  jns     short loc_180032962
0x180032941  cmp     r10, rsi
0x180032944  jz      loc_180032BB6
  ... truncated ...
```
