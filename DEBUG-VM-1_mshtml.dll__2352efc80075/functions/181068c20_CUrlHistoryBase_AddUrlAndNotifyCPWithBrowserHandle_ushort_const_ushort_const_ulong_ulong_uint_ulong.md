# CUrlHistoryBase::AddUrlAndNotifyCPWithBrowserHandle(ushort const *,ushort const *,ulong,ulong,uint *,ulong *)

- ea: `0x181068c20`
- end: `0x1810693c6`
- name: `?AddUrlAndNotifyCPWithBrowserHandle@CUrlHistoryBase@@UEAAJPEBG0KKPEAIPEAK@Z`
- size: `1958`
- prototype: `__int64 __fastcall(CUrlHistoryBase *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x181068bb0`

## callees

- `0x1800b9fa0`
- `0x1802e5024`
- `0x1804f89cc`
- `0x18069ab38`
- `0x18072b37c`
- `0x18103af1c`
- `0x181068c20`
- `0x18106a124`
- `0x18106a1e4`
- `0x18106a2ec`
- `0x18106a540`
- `0x18106a754`
- `0x1810c2d60`
- `0x1810cd6c0`
- `0x1810d1010`

## import_xrefs

- `KERNEL32!SystemTimeToFileTime` at `0x181069101`
- `KERNEL32!SystemTimeToFileTime` at `0x181069101`
- `KERNEL32!GetLocalTime` at `0x1810690f3`
- `KERNEL32!GetLocalTime` at `0x1810690f3`
- `KERNEL32!GetCurrentThreadId` at `0x181068cae`
- `KERNEL32!GetCurrentThreadId` at `0x181068cae`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpIW` at `0x181068d36`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpIW` at `0x181068d36`
- `iertutil!__imp_IEGlobalCounterIncrement` at `0x181069363`
- `iertutil!__imp_IEGlobalCounterIncrement` at `0x181069363`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x181068e0f`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x181068e42`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x181068e75`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x181068eaa`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x181068edd`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x181068f3c`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x181068fd5`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x181069008`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x181069042`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x181069079`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x181069358`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x181068e0f`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x181068e42`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x181068e75`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x181068eaa`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x181068edd`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x181068f3c`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x181068fd5`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x181069008`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x181069042`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x181069079`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x181069358`
- `SHLWAPI!UrlIsNoHistoryW` at `0x1810691e0`
- `SHLWAPI!UrlIsNoHistoryW` at `0x1810691e0`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x181068cc2`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x181068cc2`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet@@YAJKK@Z` at `0x181068cd6`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet@@YAJKK@Z` at `0x181068cea`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet@@YAJKK@Z` at `0x181068cd6`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet@@YAJKK@Z` at `0x181068cea`
- `urlmon!CoInternetQueryInfo` at `0x181069252`
- `urlmon!CoInternetQueryInfo` at `0x181069252`

## pseudocode

```c
__int64 __fastcall CUrlHistoryBase::AddUrlAndNotifyCPWithBrowserHandle(
        CUrlHistoryBase *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        DWORD a5,
        unsigned int *a6,
        unsigned int *a7)
{
  DWORD CurrentThreadId; // eax
  int v12; // r14d
  const unsigned __int16 *v13; // r13
  struct IStream *v14; // rbx
  int v15; // eax
  const unsigned __int16 *v16; // rdx
  int v17; // ebx
  unsigned int v18; // ebx
  int v19; // ecx
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  unsigned int v24; // esi
  unsigned int v25; // edi
  CUrlHistoryBase *v26; // rbx
  CUrlHistoryBase *v27; // rcx
  int cbBuffer; // [rsp+28h] [rbp-E0h]
  struct IStream *v30; // [rsp+78h] [rbp-90h]
  struct IHistoryData *v31; // [rsp+88h] [rbp-80h] BYREF
  int pvBuffer; // [rsp+90h] [rbp-78h] BYREF
  unsigned int v33; // [rsp+94h] [rbp-74h] BYREF
  unsigned int v34; // [rsp+98h] [rbp-70h]
  DWORD pcbBuffer; // [rsp+9Ch] [rbp-6Ch] BYREF
  unsigned int v36; // [rsp+A0h] [rbp-68h] BYREF
  int v37; // [rsp+A4h] [rbp-64h]
  unsigned int v38; // [rsp+A8h] [rbp-60h] BYREF
  unsigned int v39; // [rsp+ACh] [rbp-5Ch]
  unsigned __int16 *v40; // [rsp+B0h] [rbp-58h] BYREF
  struct _FILETIME v41; // [rsp+B8h] [rbp-50h] BYREF
  struct _FILETIME FileTime; // [rsp+C0h] [rbp-48h] BYREF
  CUrlHistoryBase *v43; // [rsp+C8h] [rbp-40h]
  struct IStream *v44; // [rsp+D0h] [rbp-38h] BYREF
  unsigned int *v45; // [rsp+D8h] [rbp-30h]
  __int64 v46; // [rsp+E0h] [rbp-28h] BYREF
  PROPVARIANT v47[2]; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v48; // [rsp+F8h] [rbp-10h]
  __int128 v49; // [rsp+100h] [rbp-8h] BYREF
  __int64 v50; // [rsp+110h] [rbp+8h]
  __int128 v51; // [rsp+118h] [rbp+10h] BYREF
  __int64 v52; // [rsp+128h] [rbp+20h]
  PROPVARIANT pvar[2]; // [rsp+130h] [rbp+28h] BYREF
  __int64 v54; // [rsp+140h] [rbp+38h]
  unsigned __int16 v55[264]; // [rsp+148h] [rbp+40h] BYREF
  unsigned __int16 v56[264]; // [rsp+358h] [rbp+250h] BYREF
  unsigned __int16 v57[264]; // [rsp+568h] [rbp+460h] BYREF
  unsigned __int16 v58[2088]; // [rsp+778h] [rbp+670h] BYREF

  v43 = this;
  v45 = a7;
  if ( a6 )
    *a6 = 0;
  CurrentThreadId = a5;
  v36 = 0;
  if ( !a5 )
    CurrentThreadId = GetCurrentThreadId();
  if ( (int)LCIEGetTypedComponentFromThread(0x203u, CurrentThreadId, &v36, 0) >= 0
    && !LCIEIsComponentSharedFlagValueSet(v36, 0x1000000u)
    && !LCIEIsComponentSharedFlagValueSet(v36, 0x400000u) )
  {
    if ( a7 )
      *a7 = 0;
    return (unsigned int)CUrlHistoryBase::_CacheUrlForPrerender(this, a2, a3, a4);
  }
  if ( a2 && *a2 )
  {
    v13 = a3;
    if ( a3 && !StrCmpIW(a3, a2) )
      v13 = 0;
    v31 = 0;
    v55[0] = 0;
    v33 = 0;
    v14 = 0;
    v41 = 0;
    FileTime = 0;
    v57[0] = 0;
    v58[0] = 0;
    v39 = 0;
    LOBYTE(v37) = 0;
    v56[0] = 0;
    pvBuffer = 0;
    pcbBuffer = 0;
    v38 = 0;
    v44 = 0;
    v46 = 0;
    v34 = 0;
    v40 = 0;
    if ( (int)CUrlHistoryBase::_GetHistoryDataFromWinINetCache(this, a2, &v40, &v31) < 0 )
    {
      v40 = 0;
      v31 = 0;
      pvar[0] = 0;
      v12 = CUrlHistoryBase::_EnsureHistoryDataFactory(this, (struct IHistoryDataFactory **)pvar);
      if ( v12 >= 0 )
        v12 = (*(__int64 (__fastcall **)(PROPVARIANT, const unsigned __int16 *, unsigned __int16 **, struct IHistoryData **))(*(_QWORD *)pvar[0] + 24LL))(
                pvar[0],
                a2,
                &v40,
                &v31);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(pvar);
      if ( v12 < 0 )
        goto LABEL_92;
    }
    else
    {
      v12 = 0;
      if ( !a3 )
        (*(void (__fastcall **)(struct IHistoryData *, __int64, unsigned __int16 *, __int64))(*(_QWORD *)v31 + 56LL))(
          v31,
          16,
          v55,
          260);
      v54 = 0;
      *(_OWORD *)pvar = 0;
      if ( a6
        && (*(int (__fastcall **)(struct IHistoryData *, __int64, PROPVARIANT *))(*(_QWORD *)v31 + 24LL))(v31, 18, pvar) >= 0
        && LOWORD(pvar[0]) )
      {
        *a6 = (unsigned int)pvar[1];
        PropVariantClear(pvar);
      }
      if ( (*(int (__fastcall **)(struct IHistoryData *, __int64, PROPVARIANT *))(*(_QWORD *)v31 + 24LL))(v31, 6, pvar) >= 0
        && LOWORD(pvar[0]) )
      {
        v34 = (unsigned int)pvar[1];
        PropVariantClear(pvar);
      }
      if ( (*(int (__fastcall **)(struct IHistoryData *, __int64, PROPVARIANT *))(*(_QWORD *)v31 + 24LL))(v31, 23, pvar) >= 0
        && LOWORD(pvar[0]) )
      {
        v33 = (unsigned int)pvar[1];
        PropVariantClear(pvar);
      }
      if ( (*(int (__fastcall **)(struct IHistoryData *, __int64, PROPVARIANT *))(*(_QWORD *)v31 + 24LL))(v31, 24, pvar) >= 0
        && LOWORD(pvar[0]) )
      {
        v41 = (struct _FILETIME)pvar[1];
        PropVariantClear(pvar);
      }
      if ( (*(int (__fastcall **)(struct IHistoryData *, __int64, PROPVARIANT *))(*(_QWORD *)v31 + 24LL))(v31, 39, pvar) >= 0
        && LOWORD(pvar[0]) )
      {
        v39 = (unsigned int)pvar[1];
        PropVariantClear(pvar);
      }
      if ( (*(int (__fastcall **)(struct IHistoryData *, __int64, PROPVARIANT *))(*(_QWORD *)v31 + 24LL))(v31, 34, pvar) >= 0
        && LOWORD(pvar[0]) )
      {
        if ( (*(int (__fastcall **)(struct IHistoryData *, __int64, PROPVARIANT *))(*(_QWORD *)v31 + 24LL))(
               v31,
               40,
               pvar) >= 0 )
        {
          v15 = (unsigned __int8)v37;
          if ( !LOWORD(pvar[0]) )
            v15 = 1;
          v37 = v15;
        }
        PropVariantClear(pvar);
      }
      (*(void (__fastcall **)(struct IHistoryData *, __int64, unsigned __int16 *, __int64))(*(_QWORD *)v31 + 56LL))(
        v31,
        25,
        v57,
        260);
      (*(void (__fastcall **)(struct IHistoryData *, __int64, unsigned __int16 *, __int64))(*(_QWORD *)v31 + 56LL))(
        v31,
        26,
        v58,
        2084);
      (*(void (__fastcall **)(struct IHistoryData *, __int64, unsigned __int16 *, __int64))(*(_QWORD *)v31 + 56LL))(
        v31,
        27,
        v56,
        260);
      if ( (*(int (__fastcall **)(struct IHistoryData *, __int64, PROPVARIANT *))(*(_QWORD *)v31 + 24LL))(v31, 28, pvar) >= 0
        && LOWORD(pvar[0]) )
      {
        pcbBuffer = (DWORD)pvar[1];
        PropVariantClear(pvar);
      }
      if ( (*(int (__fastcall **)(struct IHistoryData *, __int64, PROPVARIANT *))(*(_QWORD *)v31 + 24LL))(v31, 32, pvar) >= 0
        && LOWORD(pvar[0]) )
      {
        pvBuffer = (int)pvar[1];
        PropVariantClear(pvar);
      }
      if ( (*(int (__fastcall **)(struct IHistoryData *, __int64, PROPVARIANT *))(*(_QWORD *)v31 + 24LL))(v31, 29, pvar) >= 0
        && LOWORD(pvar[0]) )
      {
        ATL::CComPtr<IStream>::operator=(&v44, pvar[1]);
        PropVariantClear(pvar);
        v14 = v44;
      }
      if ( (*(int (__fastcall **)(struct IHistoryData *, __int64, PROPVARIANT *))(*(_QWORD *)v31 + 24LL))(v31, 33, pvar) >= 0
        && LOWORD(pvar[0]) )
      {
        v38 = (unsigned int)pvar[1];
        PropVariantClear(pvar);
      }
    }
    if ( v13 )
      StringCchCopyW(v55, 0x104u, v13);
    *(_OWORD *)pvar = 0;
    GetLocalTime((LPSYSTEMTIME)pvar);
    if ( SystemTimeToFileTime((const SYSTEMTIME *)pvar, &FileTime) && !v33 )
      v41 = FileTime;
    if ( (int)CUrlHistoryBase::_UpdateHistoryData(
                (CUrlHistoryBase *)&v33,
                v16,
                v55,
                v31,
                v40,
                &v33,
                &v41,
                v57,
                v58,
                v56,
                &pvBuffer,
                &pcbBuffer,
                &v38,
                v14,
                v30) < 0 )
    {
LABEL_91:
      IEGlobalCounterIncrement(11);
LABEL_92:
      if ( v45 )
        *v45 = a4;
      CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v40);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v46);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v44);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v31);
      return (unsigned int)v12;
    }
    v48 = 0;
    *(_OWORD *)v47 = 0;
    v17 = 0;
    if ( (*(int (__fastcall **)(struct IHistoryData *, __int64, PROPVARIANT *))(*(_QWORD *)v31 + 24LL))(v31, 9, v47) >= 0
      && LOWORD(v47[0]) )
    {
      v17 = (int)v47[1];
    }
    if ( (a4 & 4) != 0 || (a4 & 1) != 0 && !UrlIsNoHistoryW(a2) )
      v18 = v17 | 0x10000000;
    else
      v18 = v17 & 0xEFFFFFFF;
    v19 = a4 | 4;
    if ( (v18 & 0x10000000) == 0 )
      v19 = a4;
    a4 = v19;
    if ( (unsigned int)IsSpartanApp() )
    {
      v20 = GetUrlSchemeW(a2) - 4;
      if ( !v20 )
        goto LABEL_82;
      v21 = v20 - 11;
      if ( !v21 )
        goto LABEL_82;
      v22 = v21 - 1;
      if ( !v22 )
        goto LABEL_82;
      v23 = v22 - 1;
      if ( !v23 )
      {
LABEL_81:
        v18 &= ~0x10000000u;
        goto LABEL_82;
      }
      if ( v23 == 1 )
      {
LABEL_82:
        v24 = v34;
        v25 = v18 & 0xFFFFFFFE;
        if ( (v18 & 1) == 0 )
          v25 = v18;
        if ( (a4 & 8) != 0 || (v25 & 0x10000000) == 0 )
        {
          v26 = v43;
        }
        else
        {
          v50 = 0;
          v49 = 0;
          LOWORD(v49) = 19;
          DWORD2(v49) = v34 + 1;
          (*(void (__fastcall **)(struct IHistoryData *, __int64, __int128 *))(*(_QWORD *)v31 + 32LL))(v31, 6, &v49);
          v26 = v43;
          LOBYTE(cbBuffer) = v37;
          (*(void (__fastcall **)(CUrlHistoryBase *, _QWORD, _QWORD, _QWORD, int, struct IHistoryData *, struct _FILETIME *, struct _FILETIME *))(*(_QWORD *)v43 + 216LL))(
            v43,
            a4,
            v33,
            v39,
            cbBuffer,
            v31,
            &v41,
            &FileTime);
        }
        v51 = 0;
        v52 = 0;
        LOWORD(v51) = 19;
        DWORD2(v51) = v25;
        (*(void (__fastcall **)(struct IHistoryData *, __int64, __int128 *))(*(_QWORD *)v31 + 32LL))(v31, 9, &v51);
        v12 = CUrlHistoryBase::_CommitUrlCacheEntry(v27, v31);
        if ( v12 >= 0 )
          (*(void (__fastcall **)(CUrlHistoryBase *, struct IHistoryData *, _QWORD))(*(_QWORD *)v26 + 224LL))(
            v26,
            v31,
            v24);
        PropVariantClear(v47);
        goto LABEL_91;
      }
    }
    pvBuffer = 0;
    pcbBuffer = 0;
    if ( CoInternetQueryInfo(a2, QUERY_USES_HISTORYFOLDER, 0, &pvBuffer, 4u, &pcbBuffer, 0) < 0 || pvBuffer )
      goto LABEL_82;
    goto LABEL_81;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x181068c20  mov     rax, rsp
0x181068c23  mov     [rax+20h], r9d
0x181068c27  mov     [rax+18h], r8
0x181068c2b  mov     [rax+10h], rdx
0x181068c2f  mov     [rax+8], rcx
0x181068c33  push    rbp
0x181068c34  push    rbx
0x181068c35  push    rsi
0x181068c36  push    rdi
0x181068c37  push    r12
0x181068c39  push    r13
0x181068c3b  push    r14
0x181068c3d  push    r15
0x181068c3f  lea     rbp, [rax-1718h]
0x181068c46  mov     eax, 17D8h
0x181068c4b  call    _alloca_probe
0x181068c50  sub     rsp, rax
0x181068c53  mov     rax, cs:__security_cookie
0x181068c5a  xor     rax, rsp
0x181068c5d  mov     [rbp+1710h+var_50], rax
0x181068c64  mov     r12, [rbp+1710h+arg_28]
0x181068c6b  xor     ecx, ecx
0x181068c6d  mov     r14, [rbp+1710h+arg_0]
0x181068c74  mov     rbx, [rbp+1710h+arg_30]
0x181068c7b  mov     r15d, [rbp+1710h+arg_18]
0x181068c82  mov     rsi, [rbp+1710h+psz2]
0x181068c89  mov     rdi, [rbp+1710h+psz1]
0x181068c90  mov     [rbp+1710h+var_1750], r14
0x181068c94  mov     [rbp+1710h+var_1740], rbx
0x181068c98  test    r12, r12
0x181068c9b  jz      short loc_181068CA1
0x181068c9d  mov     [r12], ecx
0x181068ca1  mov     eax, [rbp+1710h+arg_20]
0x181068ca7  mov     [rbp+1710h+var_1778], ecx
0x181068caa  test    eax, eax
0x181068cac  jnz     short loc_181068CB4
0x181068cae  call    cs:__imp_GetCurrentThreadId
0x181068cb4  xor     r9d, r9d
0x181068cb7  lea     r8, [rbp+1710h+var_1778]
0x181068cbb  mov     edx, eax
0x181068cbd  mov     ecx, 203h
0x181068cc2  call    cs:__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z; LCIEGetTypedComponentFromThread(ulong,ulong,ulong *,_IsoComponent * *)
0x181068cc8  xor     edx, edx
0x181068cca  test    eax, eax
0x181068ccc  js      short loc_181068D16
0x181068cce  mov     ecx, [rbp+1710h+var_1778]
0x181068cd1  mov     edx, 1000000h
0x181068cd6  call    cs:__imp_?LCIEIsComponentSharedFlagValueSet@@YAJKK@Z; LCIEIsComponentSharedFlagValueSet(ulong,ulong)
0x181068cdc  xor     edx, edx
0x181068cde  test    eax, eax
0x181068ce0  jnz     short loc_181068D16
0x181068ce2  mov     ecx, [rbp+1710h+var_1778]
0x181068ce5  mov     edx, 400000h
0x181068cea  call    cs:__imp_?LCIEIsComponentSharedFlagValueSet@@YAJKK@Z; LCIEIsComponentSharedFlagValueSet(ulong,ulong)
0x181068cf0  xor     edx, edx
0x181068cf2  test    eax, eax
0x181068cf4  jnz     short loc_181068D16
0x181068cf6  test    rbx, rbx
0x181068cf9  jz      short loc_181068CFD
0x181068cfb  mov     [rbx], edx
0x181068cfd  mov     r9d, r15d; unsigned int
0x181068d00  mov     r8, rdi; unsigned __int16 *
0x181068d03  mov     rdx, rsi; unsigned __int16 *
0x181068d06  mov     rcx, r14; this
0x181068d09  call    ?_CacheUrlForPrerender@CUrlHistoryBase@@IEAAJPEBG0K@Z; CUrlHistoryBase::_CacheUrlForPrerender(ushort const *,ushort const *,ulong)
0x181068d0e  mov     r14d, eax
0x181068d11  jmp     loc_181069399
0x181068d16  test    rsi, rsi
0x181068d19  jz      loc_18106939E
0x181068d1f  cmp     [rsi], dx
0x181068d22  jz      loc_18106939E
0x181068d28  mov     r13, rdi
0x181068d2b  test    rdi, rdi
0x181068d2e  jz      short loc_181068D44
0x181068d30  mov     rdx, rsi; psz2
0x181068d33  mov     rcx, rdi; psz1
0x181068d36  call    cs:__imp_StrCmpIW
0x181068d3c  xor     edx, edx
0x181068d3e  test    eax, eax
0x181068d40  cmovz   r13, rdx
0x181068d44  mov     [rbp+1710h+var_1790], rdx
0x181068d48  lea     r9, [rbp+1710h+var_1790]; struct IHistoryData **
0x181068d4c  mov     [rbp+1710h+var_16D0], dx
0x181068d50  lea     r8, [rbp+1710h+var_1768]; unsigned __int16 **
0x181068d54  mov     [rbp+1710h+var_1784], edx
0x181068d57  mov     rbx, rdx
0x181068d5a  mov     qword ptr [rbp+1710h+var_1760.dwLowDateTime], rdx
0x181068d5e  mov     rcx, r14; this
0x181068d61  mov     qword ptr [rbp+1710h+FileTime.dwLowDateTime], rdx
0x181068d65  mov     [rbp+1710h+var_12B0], dx
0x181068d6c  mov     [rbp+1710h+var_10A0], dx
0x181068d73  mov     [rbp+1710h+var_176C], edx
0x181068d76  mov     byte ptr [rbp+1710h+var_1774], dl
0x181068d79  mov     [rbp+1710h+var_14C0], dx
0x181068d80  mov     [rbp+1710h+pvBuffer], edx
0x181068d83  mov     [rbp+1710h+var_177C], edx
0x181068d86  mov     [rbp+1710h+var_1770], edx
0x181068d89  mov     [rbp+1710h+var_1748], rdx
0x181068d8d  mov     [rbp+1710h+var_1738], rdx
0x181068d91  mov     [rbp+1710h+var_1780], edx
0x181068d94  mov     [rbp+1710h+var_1768], rdx
0x181068d98  mov     rdx, rsi; unsigned __int16 *
0x181068d9b  call    ?_GetHistoryDataFromWinINetCache@CUrlHistoryBase@@IEAAJPEBGPEAPEAGPEAPEAUIHistoryData@@@Z; CUrlHistoryBase::_GetHistoryDataFromWinINetCache(ushort const *,ushort * *,IHistoryData * *)
0x181068da0  xor     ecx, ecx
0x181068da2  test    eax, eax
0x181068da4  js      loc_181069081
0x181068daa  mov     r14d, ecx
0x181068dad  test    rdi, rdi
0x181068db0  jnz     short loc_181068DCF
0x181068db2  mov     rcx, [rbp+1710h+var_1790]
0x181068db6  lea     r8, [rbp+1710h+var_16D0]
0x181068dba  mov     r9d, 104h
0x181068dc0  lea     edx, [rdi+10h]
0x181068dc3  mov     rax, [rcx]
0x181068dc6  mov     rax, [rax+38h]
0x181068dca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181068dcf  xor     eax, eax
0x181068dd1  xor     edi, edi
0x181068dd3  mov     [rbp+1710h+var_16D8], rax
0x181068dd7  xorps   xmm0, xmm0
0x181068dda  movups  xmmword ptr [rbp+1710h+pvar], xmm0
0x181068dde  test    r12, r12
0x181068de1  jz      short loc_181068E15
0x181068de3  mov     rcx, [rbp+1710h+var_1790]
0x181068de7  lea     r8, [rbp+1710h+pvar]
0x181068deb  lea     edx, [rdi+12h]
0x181068dee  mov     rax, [rcx]
0x181068df1  mov     rax, [rax+18h]
0x181068df5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181068dfa  test    eax, eax
0x181068dfc  js      short loc_181068E15
0x181068dfe  cmp     word ptr [rbp+1710h+pvar], di
0x181068e02  jz      short loc_181068E15
0x181068e04  mov     eax, dword ptr [rbp+1710h+pvar+8]
0x181068e07  lea     rcx, [rbp+1710h+pvar]; pvar
0x181068e0b  mov     [r12], eax
0x181068e0f  call    cs:__imp_PropVariantClear
0x181068e15  mov     rcx, [rbp+1710h+var_1790]
0x181068e19  lea     r8, [rbp+1710h+pvar]
0x181068e1d  mov     edx, 6
0x181068e22  mov     rax, [rcx]
0x181068e25  mov     rax, [rax+18h]
0x181068e29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181068e2e  test    eax, eax
0x181068e30  js      short loc_181068E48
0x181068e32  cmp     word ptr [rbp+1710h+pvar], di
0x181068e36  jz      short loc_181068E48
0x181068e38  mov     eax, dword ptr [rbp+1710h+pvar+8]
0x181068e3b  lea     rcx, [rbp+1710h+pvar]; pvar
0x181068e3f  mov     [rbp+1710h+var_1780], eax
0x181068e42  call    cs:__imp_PropVariantClear
0x181068e48  mov     rcx, [rbp+1710h+var_1790]
0x181068e4c  lea     r8, [rbp+1710h+pvar]
0x181068e50  mov     edx, 17h
0x181068e55  mov     rax, [rcx]
0x181068e58  mov     rax, [rax+18h]
0x181068e5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181068e61  test    eax, eax
0x181068e63  js      short loc_181068E7B
0x181068e65  cmp     word ptr [rbp+1710h+pvar], di
0x181068e69  jz      short loc_181068E7B
0x181068e6b  mov     eax, dword ptr [rbp+1710h+pvar+8]
0x181068e6e  lea     rcx, [rbp+1710h+pvar]; pvar
0x181068e72  mov     [rbp+1710h+var_1784], eax
0x181068e75  call    cs:__imp_PropVariantClear
0x181068e7b  mov     rcx, [rbp+1710h+var_1790]
0x181068e7f  lea     r8, [rbp+1710h+pvar]
0x181068e83  mov     edx, 18h
0x181068e88  mov     rax, [rcx]
0x181068e8b  mov     rax, [rax+18h]
0x181068e8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181068e94  test    eax, eax
0x181068e96  js      short loc_181068EB0
0x181068e98  cmp     word ptr [rbp+1710h+pvar], di
0x181068e9c  jz      short loc_181068EB0
0x181068e9e  mov     rax, [rbp+1710h+pvar+8]
0x181068ea2  lea     rcx, [rbp+1710h+pvar]; pvar
0x181068ea6  mov     qword ptr [rbp+1710h+var_1760.dwLowDateTime], rax
0x181068eaa  call    cs:__imp_PropVariantClear
0x181068eb0  mov     rcx, [rbp+1710h+var_1790]
0x181068eb4  lea     r8, [rbp+1710h+pvar]
0x181068eb8  mov     edx, 27h ; '''
0x181068ebd  mov     rax, [rcx]
0x181068ec0  mov     rax, [rax+18h]
0x181068ec4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181068ec9  test    eax, eax
0x181068ecb  js      short loc_181068EE3
0x181068ecd  cmp     word ptr [rbp+1710h+pvar], di
0x181068ed1  jz      short loc_181068EE3
0x181068ed3  mov     eax, dword ptr [rbp+1710h+pvar+8]
0x181068ed6  lea     rcx, [rbp+1710h+pvar]; pvar
0x181068eda  mov     [rbp+1710h+var_176C], eax
0x181068edd  call    cs:__imp_PropVariantClear
0x181068ee3  mov     rcx, [rbp+1710h+var_1790]
0x181068ee7  lea     r8, [rbp+1710h+pvar]
0x181068eeb  mov     edx, 22h ; '"'
0x181068ef0  mov     rax, [rcx]
0x181068ef3  mov     rax, [rax+18h]
0x181068ef7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181068efc  test    eax, eax
0x181068efe  js      short loc_181068F42
0x181068f00  cmp     word ptr [rbp+1710h+pvar], di
0x181068f04  jz      short loc_181068F42
0x181068f06  mov     rcx, [rbp+1710h+var_1790]
0x181068f0a  lea     r8, [rbp+1710h+pvar]
0x181068f0e  mov     edx, 28h ; '('
0x181068f13  mov     rax, [rcx]
0x181068f16  mov     rax, [rax+18h]
0x181068f1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181068f1f  test    eax, eax
0x181068f21  js      short loc_181068F38
0x181068f23  mov     eax, [rbp+1710h+var_1774]
0x181068f26  mov     ecx, 1
0x181068f2b  cmp     word ptr [rbp+1710h+pvar], di
0x181068f2f  movzx   eax, al
0x181068f32  cmovz   eax, ecx
0x181068f35  mov     [rbp+1710h+var_1774], eax
0x181068f38  lea     rcx, [rbp+1710h+pvar]; pvar
0x181068f3c  call    cs:__imp_PropVariantClear
0x181068f42  mov     rcx, [rbp+1710h+var_1790]
0x181068f46  lea     r8, [rbp+1710h+var_12B0]
0x181068f4d  mov     r9d, 104h
0x181068f53  mov     edx, 19h
0x181068f58  mov     rax, [rcx]
0x181068f5b  mov     rax, [rax+38h]
0x181068f5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181068f64  mov     rcx, [rbp+1710h+var_1790]
0x181068f68  lea     r8, [rbp+1710h+var_10A0]
0x181068f6f  mov     r9d, 824h
0x181068f75  mov     edx, 1Ah
0x181068f7a  mov     rax, [rcx]
0x181068f7d  mov     rax, [rax+38h]
0x181068f81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181068f86  mov     rcx, [rbp+1710h+var_1790]
0x181068f8a  lea     r8, [rbp+1710h+var_14C0]
0x181068f91  mov     r9d, 104h
0x181068f97  mov     edx, 1Bh
0x181068f9c  mov     rax, [rcx]
0x181068f9f  mov     rax, [rax+38h]
0x181068fa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181068fa8  mov     rcx, [rbp+1710h+var_1790]
0x181068fac  lea     r8, [rbp+1710h+pvar]
0x181068fb0  mov     edx, 1Ch
0x181068fb5  mov     rax, [rcx]
0x181068fb8  mov     rax, [rax+18h]
0x181068fbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181068fc1  test    eax, eax
0x181068fc3  js      short loc_181068FDB
0x181068fc5  cmp     word ptr [rbp+1710h+pvar], di
0x181068fc9  jz      short loc_181068FDB
0x181068fcb  mov     eax, dword ptr [rbp+1710h+pvar+8]
0x181068fce  lea     rcx, [rbp+1710h+pvar]; pvar
0x181068fd2  mov     [rbp+1710h+var_177C], eax
0x181068fd5  call    cs:__imp_PropVariantClear
0x181068fdb  mov     rcx, [rbp+1710h+var_1790]
0x181068fdf  lea     r8, [rbp+1710h+pvar]
0x181068fe3  mov     edx, 20h ; ' '
0x181068fe8  mov     rax, [rcx]
0x181068feb  mov     rax, [rax+18h]
0x181068fef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181068ff4  test    eax, eax
0x181068ff6  js      short loc_18106900E
0x181068ff8  cmp     word ptr [rbp+1710h+pvar], di
0x181068ffc  jz      short loc_18106900E
0x181068ffe  mov     eax, dword ptr [rbp+1710h+pvar+8]
0x181069001  lea     rcx, [rbp+1710h+pvar]; pvar
0x181069005  mov     [rbp+1710h+pvBuffer], eax
0x181069008  call    cs:__imp_PropVariantClear
0x18106900e  mov     rcx, [rbp+1710h+var_1790]
0x181069012  lea     r8, [rbp+1710h+pvar]
0x181069016  mov     edx, 1Dh
0x18106901b  mov     rax, [rcx]
0x18106901e  mov     rax, [rax+18h]
0x181069022  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181069027  test    eax, eax
0x181069029  js      short loc_18106904C
0x18106902b  cmp     word ptr [rbp+1710h+pvar], di
0x18106902f  jz      short loc_18106904C
0x181069031  mov     rdx, [rbp+1710h+pvar+8]
0x181069035  lea     rcx, [rbp+1710h+var_1748]
0x181069039  call    ??4?$CComPtr@UIStream@@@ATL@@QEAAPEAUIStream@@PEAU2@@Z; ATL::CComPtr<IStream>::operator=(IStream *)
0x18106903e  lea     rcx, [rbp+1710h+pvar]; pvar
0x181069042  call    cs:__imp_PropVariantClear
0x181069048  mov     rbx, [rbp+1710h+var_1748]
0x18106904c  mov     rcx, [rbp+1710h+var_1790]
0x181069050  lea     r8, [rbp+1710h+pvar]
0x181069054  mov     edx, 21h ; '!'
0x181069059  mov     rax, [rcx]
0x18106905c  mov     rax, [rax+18h]
0x181069060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181069065  test    eax, eax
0x181069067  js      short loc_1810690D2
0x181069069  cmp     word ptr [rbp+1710h+pvar], di
0x18106906d  jz      short loc_1810690D2
0x18106906f  mov     eax, dword ptr [rbp+1710h+pvar+8]
0x181069072  lea     rcx, [rbp+1710h+pvar]; pvar
0x181069076  mov     [rbp+1710h+var_1770], eax
0x181069079  call    cs:__imp_PropVariantClear
0x18106907f  jmp     short loc_1810690D2
0x181069081  xor     edi, edi
  ... truncated ...
```
