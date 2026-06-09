# CResProtocol::DoParseAndBind(ushort const *,CStr &,CStr &,CStr &,IStream * *,CResProtocol *)

- ea: `0x180779b1c`
- end: `0x18077a5e7`
- name: `?DoParseAndBind@CResProtocol@@SAJPEBGAEAVCStr@@11PEAPEAUIStream@@PEAV1@@Z`
- size: `2763`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct CStr *, struct CStr *, struct CStr *, struct IStream **, struct CResProtocol *)`
- caller_count: `2`
- callee_count: `23`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180777110`
- `0x180f49250`

## callees

- `0x1801c0b08`
- `0x1801cd614`
- `0x180282f30`
- `0x18030035c`
- `0x18043c328`
- `0x1804e223c`
- `0x180551cc0`
- `0x1805c1f68`
- `0x18066fee4`
- `0x1806a6c8c`
- `0x1806c9590`
- `0x1806ccf30`
- `0x180771400`
- `0x180779b1c`
- `0x18078b7f8`
- `0x1808395a4`
- `0x180839614`
- `0x180b440b8`
- `0x180f493a0`
- `0x180f49400`
- `0x1810c2cb6`
- `0x1810c2d60`
- `0x1810d1010`

## import_xrefs

- `msvcrt!_itow_s` at `0x180779cae`
- `msvcrt!_itow_s` at `0x180779cae`
- `msvcrt!memcpy_s` at `0x180779faf`
- `msvcrt!memcpy_s` at `0x180779fc6`
- `msvcrt!memcpy_s` at `0x18077a294`
- `msvcrt!memcpy_s` at `0x180779faf`
- `msvcrt!memcpy_s` at `0x180779fc6`
- `msvcrt!memcpy_s` at `0x18077a294`
- `KERNEL32!LoadLibraryExW` at `0x180779d47`
- `KERNEL32!LoadLibraryExW` at `0x180779d47`
- `KERNEL32!WriteFile` at `0x18077a3f3`
- `KERNEL32!WriteFile` at `0x18077a3f3`
- `KERNEL32!CreateFileW` at `0x18077a3cf`
- `KERNEL32!CreateFileW` at `0x18077a3cf`
- `KERNEL32!DeleteFileW` at `0x18077a462`
- `KERNEL32!DeleteFileW` at `0x18077a462`
- `KERNEL32!CompareStringW` at `0x18077a1cf`
- `KERNEL32!CompareStringW` at `0x18077a1cf`
- `KERNEL32!FreeLibrary` at `0x18077a531`
- `KERNEL32!FreeLibrary` at `0x18077a531`
- `KERNEL32!CloseHandle` at `0x18077a44f`
- `KERNEL32!CloseHandle` at `0x18077a559`
- `KERNEL32!CloseHandle` at `0x18077a44f`
- `KERNEL32!CloseHandle` at `0x18077a559`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x180779d76`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x180779dd5`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x180779d76`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x180779dd5`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180779d8e`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180779da2`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180779ded`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180779e01`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180779e15`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180779d8e`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180779da2`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180779ded`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180779e01`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpICW` at `0x180779e15`
- `iertutil!CreateUri` at `0x180779c35`
- `iertutil!CreateUri` at `0x18077a06f`
- `iertutil!CreateUri` at `0x180779c35`
- `iertutil!CreateUri` at `0x18077a06f`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x18077a3fd`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x18077a3fd`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18077a57d`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18077a57d`
- `urlmon!CoInternetCreateSecurityManager` at `0x180779c5e`
- `urlmon!CoInternetCreateSecurityManager` at `0x180779c5e`
- `urlmon!CreateAsyncBindCtxEx` at `0x180779ffd`
- `urlmon!CreateAsyncBindCtxEx` at `0x180779ffd`
- `urlmon!FindMimeFromData` at `0x18077a213`
- `urlmon!FindMimeFromData` at `0x18077a2c9`
- `urlmon!FindMimeFromData` at `0x18077a213`
- `urlmon!FindMimeFromData` at `0x18077a2c9`
- `urlmon!__imp_IECompatLogEventWithUrl` at `0x180779ce9`
- `urlmon!__imp_IECompatLogEventWithUrl` at `0x180779ce9`

## string_xrefs

- `0x180779d84`: `shdoclc.dll`
- `0x180779cd6`: `ResProtocolRestricted`
- `0x180779de3`: `apds.dll`

## pseudocode

```c
__int64 __fastcall CResProtocol::DoParseAndBind(
        const unsigned __int16 *a1,
        struct CStr *a2,
        struct CStr *a3,
        struct CStr *a4,
        struct IStream **a5,
        struct CResProtocol *a6)
{
  rsize_t v6; // r15
  struct IStream *v8; // rdi
  _QWORD *ThreadLocalStoragePointer; // rax
  __int64 v13; // rax
  HRESULT Uri; // ebx
  const WCHAR *v15; // rcx
  int v16; // ecx
  HMODULE v17; // r12
  const WCHAR *FileNameW; // rax
  const WCHAR *v19; // rbx
  const WCHAR *v20; // rax
  const WCHAR *v21; // rbx
  unsigned int v22; // eax
  HINSTANCE v23; // rcx
  __int64 v24; // r8
  _DWORD *Resource; // rsi
  __int64 v26; // rax
  __int64 v27; // r9
  unsigned int v28; // eax
  unsigned int v29; // r14d
  __int64 v30; // r8
  unsigned __int16 v31; // cx
  int v32; // edx
  unsigned int v33; // eax
  int v34; // edx
  void *v35; // rax
  _DWORD *v36; // rbx
  __int64 v37; // r8
  __int64 v38; // r9
  const WCHAR *v39; // rcx
  CResProtocol *v40; // r13
  IUri *v41; // r14
  int v42; // ebx
  const WCHAR *v43; // r8
  const WCHAR *i; // r9
  LPWSTR v45; // r12
  WCHAR v46; // cx
  unsigned __int16 v47; // r10
  WCHAR v48; // dx
  int v49; // eax
  HRESULT MimeFromData; // ebx
  char v51; // r14
  int v52; // eax
  DWORD v53; // ebx
  void *v54; // rax
  void *v55; // r14
  void *v56; // r8
  CResProtocol *v57; // rbx
  __int64 v58; // rcx
  HANDLE v59; // rax
  bool v60; // al
  __int64 v61; // rax
  __int64 v62; // rcx
  void *v63; // r8
  int Value[2]; // [rsp+58h] [rbp-B0h] BYREF
  IInternetSecurityManager *ppSM; // [rsp+60h] [rbp-A8h] BYREF
  CResProtocol *v67; // [rsp+68h] [rbp-A0h]
  HANDLE hObject; // [rsp+70h] [rbp-98h]
  IUri *ppURI; // [rsp+78h] [rbp-90h] BYREF
  LPBC pBC; // [rsp+80h] [rbp-88h] BYREF
  LPWSTR ppwzMimeOut; // [rsp+88h] [rbp-80h] BYREF
  HMODULE hLibModule; // [rsp+90h] [rbp-78h]
  void *v73; // [rsp+98h] [rbp-70h]
  _QWORD v74[2]; // [rsp+A0h] [rbp-68h] BYREF
  int v75; // [rsp+B0h] [rbp-58h]
  LPCWSTR pwzUrl[2]; // [rsp+B8h] [rbp-50h]
  int v77; // [rsp+C8h] [rbp-40h]
  struct IStream **v78; // [rsp+D0h] [rbp-38h]
  _QWORD Source[2]; // [rsp+D8h] [rbp-30h] BYREF
  wchar_t Buffer[4]; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v81; // [rsp+F0h] [rbp-18h]
  int v82; // [rsp+F8h] [rbp-10h]
  __int128 v83; // [rsp+100h] [rbp-8h]
  int v84; // [rsp+110h] [rbp+8h]
  WCHAR FileName; // [rsp+118h] [rbp+10h] BYREF
  _BYTE v86[526]; // [rsp+11Ah] [rbp+12h] BYREF

  LODWORD(v6) = 0;
  v8 = 0;
  v78 = a5;
  v67 = a6;
  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  Value[1] = 0;
  hLibModule = 0;
  v13 = ThreadLocalStoragePointer[(unsigned int)tls_index];
  v73 = 0;
  pBC = 0;
  ppwzMimeOut = 0;
  LODWORD(v13) = *(_DWORD *)(v13 + 12);
  hObject = (HANDLE)-1LL;
  if ( dword_181597418 > (int)v13 )
  {
    Init_thread_header(&dword_181597418);
    if ( dword_181597418 == -1 )
    {
      byte_18159741C = (unsigned int)CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::FEATURE_RESTRICT_RES_TO_LMZ) == 0;
      Init_thread_footer(&dword_181597418);
    }
  }
  Uri = CrackResUrl(a1, a2, a3, a4);
  if ( Uri )
    goto LABEL_120;
  if ( CStr::Length(a2) >= 0x104 )
  {
    Uri = -2147467259;
    goto LABEL_120;
  }
  if ( byte_18159741C )
  {
    v15 = *(const WCHAR **)a2;
    Value[0] = 0;
    ppURI = 0;
    Uri = CreateUri(v15, dwFlags, 0, &ppURI);
    if ( Uri < 0 )
    {
      if ( Uri == -2147024809 )
        Uri = 0;
LABEL_19:
      if ( ppURI )
      {
        ((void (__fastcall *)(IUri *))ppURI->lpVtbl->Release)(ppURI);
        ppURI = 0;
      }
      if ( Uri < 0 )
        goto LABEL_120;
      goto LABEL_22;
    }
    ppSM = 0;
    Value[0] = 4;
    if ( CoInternetCreateSecurityManager(0, &ppSM, 0) < 0
      || (Uri = ((__int64 (__fastcall *)(IInternetSecurityManager *, _QWORD, int *, __int64))ppSM->lpVtbl->MapUrlToZone)(
                  ppSM,
                  *(_QWORD *)a2,
                  Value,
                  2),
          Uri < 0) )
    {
      v16 = Value[0];
    }
    else
    {
      v16 = Value[0];
      if ( !Value[0] )
      {
LABEL_15:
        if ( ppSM )
        {
          ((void (__fastcall *)(IInternetSecurityManager *))ppSM->lpVtbl->Release)(ppSM);
          ppSM = 0;
        }
        goto LABEL_19;
      }
    }
    Uri = -2147024891;
    _itow_s(v16, Buffer, 0x10u, 10);
    if ( g_cmptlgs != 1 && (unsigned int)IECompatLoggingEnabled() )
      IECompatLogEventWithUrl(3221226517LL, L"ResProtocolRestricted", a1, Buffer, 0, 0, 0);
    goto LABEL_15;
  }
LABEL_22:
  hLibModule = LoadLibraryExW(*(LPCWSTR *)a2, 0, 0x60u);
  v17 = hLibModule;
  if ( !hLibModule )
  {
    Uri = -2147023739;
    goto LABEL_120;
  }
  if ( (unsigned int)CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::FEATURE_LOAD_SHDOCLC_RESOURCES)
    && (FileNameW = PathFindFileNameW(*(LPCWSTR *)a2), (v19 = FileNameW) != 0)
    && (!StrCmpICW(FileNameW, L"shdoclc.dll") || !StrCmpICW(v19, L"shdoclc"))
    && (unsigned int)CResProtocol::_IsInsecureHTML(a4)
    || (unsigned int)CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::FEATURE_ALLOW_APDS_REDIRECTION)
    && (v20 = PathFindFileNameW(*(LPCWSTR *)a2), (v21 = v20) != 0)
    && (!StrCmpICW(v20, L"apds.dll") || !StrCmpICW(v21, L"apds"))
    && !StrCmpICW(*(LPCWSTR *)a4, L"redirect.html") )
  {
    Uri = -2147024891;
    goto LABEL_120;
  }
  v22 = CStr::Length(a3);
  v23 = v17;
  if ( v22 )
  {
    v24 = *(_QWORD *)a3;
  }
  else
  {
    Resource = GetResource(
                 v17,
                 *(const unsigned __int16 **)a4,
                 (const unsigned __int16 *)0x17,
                 (unsigned int *)&Value[1]);
    if ( Resource )
      goto LABEL_41;
    v23 = v17;
    v24 = 2110;
  }
  Resource = GetResource(v23, *(const unsigned __int16 **)a4, (const unsigned __int16 *)v24, (unsigned int *)&Value[1]);
  if ( !Resource )
  {
    LODWORD(v6) = Value[1];
    Uri = -2147023739;
    goto LABEL_120;
  }
LABEL_41:
  v26 = *(_QWORD *)a3;
  if ( **(_WORD **)a3 == 35 && *(_WORD *)(v26 + 2) == 50 && !*(_WORD *)(v26 + 4) )
  {
    v6 = (unsigned int)Value[1];
    v27 = 12;
    v28 = 0;
    Value[0] = 0;
    memset(Source, 0, 14);
    if ( Value[1] >= 0x28u && *Resource == 40 )
    {
      v28 = Resource[8];
      v29 = 54;
      v30 = (unsigned int)Resource[4];
      v31 = *((_WORD *)Resource + 7);
LABEL_50:
      if ( v31 > 8u )
      {
        v32 = 0;
        if ( (_DWORD)v30 == 3 && ((v31 - 16) & 0xFFEF) == 0 )
          v32 = 12;
      }
      else
      {
        if ( !v28 )
          v28 = 1 << v31;
        Uri = ULongLongToULong(4LL * v28, (unsigned int *)Value);
        if ( Uri )
          goto LABEL_120;
        v32 = Value[0];
      }
      LOWORD(Source[0]) = 19778;
      if ( (unsigned int)v6 >= 0xFFFFFFF2 )
      {
        Uri = -2147024362;
        goto LABEL_120;
      }
      v33 = v29 + v32;
      *(_DWORD *)((char *)Source + 2) = v6 + 14;
      v34 = -1;
      *(_DWORD *)((char *)Source + 6) = 0;
      if ( v33 >= v29 )
        v34 = v33;
      Uri = v33 < v29 ? 0x80070216 : 0;
      if ( v33 >= v29 )
      {
        *(_DWORD *)((char *)&Source[1] + 2) = v34;
        v35 = (void *)MemoryProtection::HeapAlloc<1>(g_hProcessHeap, (unsigned int)(v6 + 14), v30, v27);
        v73 = v35;
        v36 = v35;
        if ( !v35 )
          goto LABEL_119;
        memcpy_s(v35, *(unsigned int *)((char *)Source + 2), Source, 0xEu);
        memcpy_s((char *)v36 + 14, *(unsigned int *)((char *)Source + 2) - 14LL, Resource, v6);
        LODWORD(v6) = *(_DWORD *)((char *)Source + 2);
        Resource = v36;
        goto LABEL_66;
      }
LABEL_120:
      v40 = v67;
      if ( v67 )
        goto LABEL_121;
      goto LABEL_126;
    }
    if ( Value[1] >= 0xCu && *Resource == 12 )
    {
      v31 = *((_WORD *)Resource + 5);
      v30 = 0;
      v29 = 26;
      goto LABEL_50;
    }
  }
  else
  {
    LODWORD(v6) = Value[1];
  }
LABEL_66:
  Uri = CreateAsyncBindCtxEx(0, 0, 0, 0, &pBC, 0);
  if ( Uri )
    goto LABEL_120;
  if ( !v67 )
    goto LABEL_115;
  v39 = (const WCHAR *)*((_QWORD *)v67 + 9);
  v74[0] = &CUString::`vftable';
  v75 = 11;
  *(_QWORD *)Buffer = &CUString::`vftable';
  *(_OWORD *)pwzUrl = 0;
  v82 = 11;
  v83 = 0;
  ppSM = 0;
  Value[0] = 0;
  v74[1] = 0;
  v77 = 0;
  v81 = 0;
  v84 = 0;
  Uri = CreateUri(v39, dwFlags, 0, (IUri **)&ppSM);
  if ( Uri < 0 )
  {
    *(_QWORD *)Buffer = &CUString::`vftable';
    CUString::Set((CUString *)Buffer, 0, Uri_PROPERTY_RAW_URI);
    v74[0] = &CUString::`vftable';
    CUString::Set((CUString *)v74, 0, Uri_PROPERTY_RAW_URI);
    v40 = v67;
    goto LABEL_121;
  }
  ((void (__fastcall *)(IInternetSecurityManager *, int *))ppSM->lpVtbl[2].GetSecuritySite)(ppSM, Value);
  CUString::Set((CUString *)v74, (struct IUri *)ppSM, Uri_PROPERTY_PATH);
  v41 = (IUri *)pwzUrl[1];
  v40 = v67;
  ppURI = (IUri *)pwzUrl[1];
  if ( !pwzUrl[1] )
  {
    v41 = (IUri *)*((_QWORD *)v67 + 9);
    ppURI = v41;
  }
  v42 = 0;
  v45 = (LPWSTR)L"text/html";
  if ( !(unsigned int)IsIEResourcePage((struct IUri *)ppSM, 1, 0)
    || (v42 = CUString::Set((CUString *)Buffer, (struct IUri *)ppSM, Uri_PROPERTY_EXTENSION)) != 0
    || (v43 = (const WCHAR *)*((_QWORD *)&v83 + 1)) == 0 )
  {
LABEL_91:
    if ( (Value[0] & 0x10) != 0 && !v42 )
    {
      MimeFromData = FindMimeFromData(pBC, (LPCWSTR)v41, 0, 0, 0, 0, &ppwzMimeOut, 0);
      v51 = 0;
      if ( MimeFromData >= 0 )
        goto LABEL_100;
    }
    v53 = 256;
    if ( (unsigned int)v6 < 0x100 )
      v53 = v6;
    v54 = (void *)MemoryProtection::HeapAlloc<1>(g_hProcessHeap, v53, v43, i);
    v55 = v54;
    if ( v54 )
    {
      memcpy_s(v54, v53, Resource, v53);
      v45 = (LPWSTR)L"text/html";
      MimeFromData = FindMimeFromData(pBC, (LPCWSTR)ppURI, v55, v53, L"text/html", 0, &ppwzMimeOut, 0);
      MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v55, v56);
      v51 = 0;
      goto LABEL_100;
    }
    Uri = -2147024882;
    goto LABEL_98;
  }
  for ( i = L".dlg"; ; ++i )
  {
    v48 = *v43;
    if ( !*v43 )
    {
      v49 = -(*i != 0);
      goto LABEL_86;
    }
    v46 = *i;
    if ( v48 != *i )
      break;
LABEL_83:
    ++v43;
  }
  v47 = v46 - 65;
  if ( (unsigned __int16)(v48 - 65) > 0x19u )
  {
    if ( v47 > 0x19u )
      goto LABEL_88;
  }
  else
  {
    v48 += 32;
    if ( v47 > 0x19u )
      goto LABEL_82;
  }
  v46 += 32;
LABEL_82:
  if ( v48 == v46 )
    goto LABEL_83;
LABEL_88:
  if ( ((v48 | v46) & 0xFF80) == 0 )
    goto LABEL_91;
  v52 = CompareStringW(0, 0x31001u, v43, -1, i, -1);
  if ( v52 <= 0 )
    goto LABEL_91;
  v49 = v52 - 2;
LABEL_86:
  if ( v49 )
    goto LABEL_91;
  MimeFromData = 0;
  v51 = 1;
LABEL_100:
  if ( ppSM )
  {
    ((void (__fastcall *)(IInternetSecurityManager *))ppSM->lpVtbl->Release)(ppSM);
    ppSM = 0;
  }
  if ( MimeFromData < 0 )
    goto LABEL_106;
  if ( !v51 )
    v45 = ppwzMimeOut;
  Uri = (*(__int64 (__fastcall **)(_QWORD, __int64, LPWSTR))(**((_QWORD **)v40 + 10) + 32LL))(
          *((_QWORD *)v40 + 10),
          22,
          v45);
  if ( !Uri )
  {
LABEL_106:
    *(_QWORD *)Buffer = &CUString::`vftable';
    CUString::Set((CUString *)Buffer, 0, Uri_PROPERTY_RAW_URI);
    v74[0] = &CUString::`vftable';
    CUString::Set((CUString *)v74, 0, Uri_PROPERTY_RAW_URI);
    v57 = v67;
    if ( (*((_BYTE *)v67 + 100) & 0x40) == 0 )
      goto LABEL_115;
    FileName = 0;
    memset_0(v86, 0, 0x208u);
    v58 = *((_QWORD *)v57 + 9);
    Value[1] = 0;
    if ( !(unsigned int)CreateUrlCacheEntryBugW(v58, (unsigned int)v6, 0, &FileName) )
      goto LABEL_112;
    v59 = CreateFileW(&FileName, 0x40000000u, 3u, 0, 2u, 0x80u, 0);
    hObject = v59;
    if ( v59 != (HANDLE)-1LL )
    {
      if ( WriteFile(v59, Resource, v6, (LPDWORD)&Value[1], 0) )
      {
        v60 = LCIEIsCurrentProcessInPrivate();
        if ( (unsigned int)CommitUrlCacheEntryBugW(
                             *((_QWORD *)v57 + 9),
                             (int)&FileName,
                             0,
                             0,
                             ((unsigned __int8)v60 << 17) + 1) )
        {
          (*(void (__fastcall **)(_QWORD, __int64, WCHAR *))(**((_QWORD **)v57 + 10) + 32LL))(
            *((_QWORD *)v57 + 10),
            14,
            &FileName);
          goto LABEL_115;
        }
      }
LABEL_112:
      v59 = hObject;
    }
    if ( FileName )
    {
      CloseHandle(v59);
      hObject = (HANDLE)-1LL;
      DeleteFileW(&FileName);
      DeleteUrlCacheEntryBugW(*((const unsigned __int16 **)v57 + 9));
    }
LABEL_115:
    v61 = MemoryProtection::HeapAlloc<1>(g_hProcessHeap, 40, v37, v38);
    v8 = (struct IStream *)v61;
    if ( v61 )
    {
      *(_QWORD *)(v61 + 32) = 0;
      *(_QWORD *)v61 = &CBaseROStmOnBuffer::`vftable';
      *(_DWORD *)(v61 + 8) = 1;
      *(_QWORD *)v61 = &CBaseROStmOnBuffer::`vftable';
      *(_QWORD *)(v61 + 16) = 0;
      *(_DWORD *)(v61 + 24) = 0;
      Uri = CBaseROStmOnBuffer::Init((CBaseROStmOnBuffer *)v61, (const unsigned __int8 *)Resource, v6);
      if ( !Uri )
      {
        *v78 = v8;
        (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v8 + 8LL))(v8);
      }
      goto LABEL_120;
    }
    v8 = 0;
LABEL_119:
    Uri = -2147024882;
    goto LABEL_120;
  }
LABEL_98:
  *(_QWORD *)Buffer = &CUString::`vftable';
  CUString::Set((CUString *)Buffer, 0, Uri_PROPERTY_RAW_URI);
  v74[0] = &CUString::`vftable';
  CUString::Set((CUString *)v74, 0, Uri_PROPERTY_RAW_URI);
LABEL_121:
  if ( (*((_BYTE *)v40 + 248) & 1) == 0 )
  {
    if ( !Uri )
      CResProtocol::_ReportData(v40, v6);
    v62 = *((_QWORD *)v40 + 10);
    if ( v62 )
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v62 + 48LL))(v62, (unsigned int)Uri, 0, 0);
  }
LABEL_126:
  if ( hLibModule )
    FreeLibrary(hLibModule);
  if ( v8 )
    (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v8 + 16LL))(v8);
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  ReleaseInterface((struct IUnknown *)pBC);
  MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, v73, v63);
  CoTaskMemFree(ppwzMimeOut);
  return (unsigned int)Uri;
}

```

## disassembly

```asm
0x180779b1c  mov     rax, rsp
0x180779b1f  mov     [rax+20h], r9
0x180779b23  mov     [rax+18h], r8
0x180779b27  mov     [rax+10h], rdx
0x180779b2b  mov     [rax+8], rcx
0x180779b2f  push    rbp
0x180779b30  push    rbx
0x180779b31  push    rsi
0x180779b32  push    rdi
0x180779b33  push    r12
0x180779b35  push    r13
0x180779b37  push    r14
0x180779b39  push    r15
0x180779b3b  lea     rbp, [rax-278h]
0x180779b42  sub     rsp, 338h
0x180779b49  mov     rax, cs:__security_cookie
0x180779b50  xor     rax, rsp
0x180779b53  mov     [rbp+270h+var_50], rax
0x180779b5a  mov     rax, [rbp+270h+arg_20]
0x180779b61  xor     ebx, ebx
0x180779b63  mov     ecx, cs:_tls_index
0x180779b69  mov     r15d, ebx
0x180779b6c  mov     r14, [rbp+270h+arg_18]
0x180779b73  mov     edi, ebx
0x180779b75  mov     r12, [rbp+270h+arg_0]
0x180779b7c  mov     rsi, [rbp+270h+arg_8]
0x180779b83  mov     r13, [rbp+270h+arg_10]
0x180779b8a  mov     [rbp+270h+var_2A8], rax
0x180779b8e  mov     rax, [rbp+270h+arg_28]
0x180779b95  mov     [rsp+370h+var_310], rax
0x180779b9a  mov     rax, gs:58h
0x180779ba3  mov     edx, 0Ch
0x180779ba8  mov     [rsp+370h+Value+4], ebx
0x180779bac  mov     [rbp+270h+hLibModule], rbx
0x180779bb0  mov     rax, [rax+rcx*8]
0x180779bb4  mov     [rbp+270h+var_2E0], rbx
0x180779bb8  mov     [rsp+370h+pBC], rbx
0x180779bbd  mov     [rbp+270h+var_2F0], rbx
0x180779bc1  mov     eax, [rax+rdx]
0x180779bc4  cmp     cs:dword_181597418, eax
0x180779bca  mov     [rsp+370h+hObject], 0FFFFFFFFFFFFFFFFh
0x180779bd3  jg      loc_18077A5A8
0x180779bd9  mov     r9, r14; struct CStr *
0x180779bdc  mov     r8, r13; struct CStr *
0x180779bdf  mov     rdx, rsi; struct CStr *
0x180779be2  mov     rcx, r12; unsigned __int16 *
0x180779be5  call    ?CrackResUrl@@YAJPEBGPEAVCStr@@11@Z; CrackResUrl(ushort const *,CStr *,CStr *,CStr *)
0x180779bea  mov     ebx, eax
0x180779bec  test    eax, eax
0x180779bee  jnz     loc_18077A4E5
0x180779bf4  mov     rcx, rsi; this
0x180779bf7  call    ?Length@CStr@@QEBAIXZ; CStr::Length(void)
0x180779bfc  cmp     eax, 104h
0x180779c01  jb      short loc_180779C0D
0x180779c03  mov     ebx, 80004005h
0x180779c08  jmp     loc_18077A4E5
0x180779c0d  xor     eax, eax
0x180779c0f  cmp     cs:byte_18159741C, al
0x180779c15  jz      loc_180779D3E
0x180779c1b  mov     edx, cs:dwFlags; dwFlags
0x180779c21  lea     r9, [rsp+370h+ppURI]; ppURI
0x180779c26  mov     rcx, [rsi]; pwzURI
0x180779c29  xor     r8d, r8d; dwReserved
0x180779c2c  mov     [rsp+370h+Value], eax
0x180779c30  mov     [rsp+370h+ppURI], rax
0x180779c35  call    cs:__imp_CreateUri
0x180779c3b  mov     ebx, eax
0x180779c3d  xor     eax, eax
0x180779c3f  test    ebx, ebx
0x180779c41  js      loc_180779D0F
0x180779c47  xor     r8d, r8d; dwReserved
0x180779c4a  mov     [rsp+370h+ppSM], rax
0x180779c4f  lea     rdx, [rsp+370h+ppSM]; ppSM
0x180779c54  mov     [rsp+370h+Value], 4
0x180779c5c  xor     ecx, ecx; pSP
0x180779c5e  call    cs:__imp_CoInternetCreateSecurityManager
0x180779c64  test    eax, eax
0x180779c66  js      short loc_180779C97
0x180779c68  mov     rcx, [rsp+370h+ppSM]
0x180779c6d  lea     r8, [rsp+370h+Value]
0x180779c72  mov     rdx, [rsi]
0x180779c75  mov     r9d, 2
0x180779c7b  mov     rax, [rcx]
0x180779c7e  mov     rax, [rax+28h]
0x180779c82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180779c87  mov     ebx, eax
0x180779c89  test    eax, eax
0x180779c8b  js      short loc_180779C97
0x180779c8d  mov     ecx, [rsp+370h+Value]
0x180779c91  test    ecx, ecx
0x180779c93  jz      short loc_180779CEF
0x180779c95  jmp     short loc_180779C9B
0x180779c97  mov     ecx, [rsp+370h+Value]; Value
0x180779c9b  mov     r9d, 0Ah; Radix
0x180779ca1  lea     rdx, [rbp+270h+Buffer]; Buffer
0x180779ca5  mov     ebx, 80070005h
0x180779caa  lea     r8d, [r9+6]; BufferCount
0x180779cae  call    cs:__imp__itow_s
0x180779cb4  cmp     cs:?g_cmptlgs@@3W4CMPTLGS@@A, 1; CMPTLGS g_cmptlgs
0x180779cbb  jz      short loc_180779CEF
0x180779cbd  call    ?IECompatLoggingEnabled@@YAHXZ; IECompatLoggingEnabled(void)
0x180779cc2  xor     ecx, ecx
0x180779cc4  test    eax, eax
0x180779cc6  jz      short loc_180779CEF
0x180779cc8  mov     [rsp+370h+ppwzMimeOut], rcx
0x180779ccd  lea     r9, [rbp+270h+Buffer]
0x180779cd1  mov     qword ptr [rsp+370h+reserved], rcx
0x180779cd6  lea     rdx, aResprotocolres; "ResProtocolRestricted"
0x180779cdd  mov     dword ptr [rsp+370h+ppBC], ecx
0x180779ce1  mov     r8, r12
0x180779ce4  mov     ecx, 0C0000415h
0x180779ce9  call    cs:__imp_IECompatLogEventWithUrl
0x180779cef  mov     rcx, [rsp+370h+ppSM]
0x180779cf4  xor     r12d, r12d
0x180779cf7  test    rcx, rcx
0x180779cfa  jz      short loc_180779D1B
0x180779cfc  mov     rax, [rcx]
0x180779cff  mov     rax, [rax+10h]
0x180779d03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180779d08  mov     [rsp+370h+ppSM], r12
0x180779d0d  jmp     short loc_180779D1B
0x180779d0f  cmp     ebx, 80070057h
0x180779d15  cmovz   ebx, eax
0x180779d18  xor     r12d, r12d
0x180779d1b  mov     rcx, [rsp+370h+ppURI]
0x180779d20  test    rcx, rcx
0x180779d23  jz      short loc_180779D36
0x180779d25  mov     rax, [rcx]
0x180779d28  mov     rax, [rax+10h]
0x180779d2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180779d31  mov     [rsp+370h+ppURI], r12
0x180779d36  test    ebx, ebx
0x180779d38  js      loc_18077A4E5
0x180779d3e  mov     rcx, [rsi]; lpLibFileName
0x180779d41  xor     edx, edx; hFile
0x180779d43  lea     r8d, [rdx+60h]; dwFlags
0x180779d47  call    cs:__imp_LoadLibraryExW
0x180779d4d  mov     [rbp+270h+hLibModule], rax
0x180779d51  mov     r12, rax
0x180779d54  test    rax, rax
0x180779d57  jnz     short loc_180779D63
0x180779d59  mov     ebx, 80070485h
0x180779d5e  jmp     loc_18077A4E5
0x180779d63  lea     rcx, ?FEATURE_LOAD_SHDOCLC_RESOURCES@FCK@@3VCFeatureControlKey@@A; this
0x180779d6a  call    ?_CoInternetIsFeatureEnabledInternal@CFeatureControlKey@@QEAAJXZ; CFeatureControlKey::_CoInternetIsFeatureEnabledInternal(void)
0x180779d6f  test    eax, eax
0x180779d71  jz      short loc_180779DC2
0x180779d73  mov     rcx, [rsi]; pszPath
0x180779d76  call    cs:__imp_PathFindFileNameW
0x180779d7c  mov     rbx, rax
0x180779d7f  test    rax, rax
0x180779d82  jz      short loc_180779DC2
0x180779d84  lea     rdx, aShdoclcDll; "shdoclc.dll"
0x180779d8b  mov     rcx, rax; pszStr1
0x180779d8e  call    cs:__imp_StrCmpICW
0x180779d94  test    eax, eax
0x180779d96  jz      short loc_180779DAC
0x180779d98  lea     rdx, aShdoclc; "shdoclc"
0x180779d9f  mov     rcx, rbx; pszStr1
0x180779da2  call    cs:__imp_StrCmpICW
0x180779da8  test    eax, eax
0x180779daa  jnz     short loc_180779DC2
0x180779dac  mov     rcx, r14; struct CStr *
0x180779daf  call    ?_IsInsecureHTML@CResProtocol@@CAHAEAVCStr@@@Z; CResProtocol::_IsInsecureHTML(CStr &)
0x180779db4  test    eax, eax
0x180779db6  jz      short loc_180779DC2
0x180779db8  mov     ebx, 80070005h
0x180779dbd  jmp     loc_18077A4E5
0x180779dc2  lea     rcx, ?FEATURE_ALLOW_APDS_REDIRECTION@FCK@@3VCFeatureControlKey@@A; this
0x180779dc9  call    ?_CoInternetIsFeatureEnabledInternal@CFeatureControlKey@@QEAAJXZ; CFeatureControlKey::_CoInternetIsFeatureEnabledInternal(void)
0x180779dce  test    eax, eax
0x180779dd0  jz      short loc_180779E1F
0x180779dd2  mov     rcx, [rsi]; pszPath
0x180779dd5  call    cs:__imp_PathFindFileNameW
0x180779ddb  mov     rbx, rax
0x180779dde  test    rax, rax
0x180779de1  jz      short loc_180779E1F
0x180779de3  lea     rdx, aApdsDll; "apds.dll"
0x180779dea  mov     rcx, rax; pszStr1
0x180779ded  call    cs:__imp_StrCmpICW
0x180779df3  test    eax, eax
0x180779df5  jz      short loc_180779E0B
0x180779df7  lea     rdx, aApds; "apds"
0x180779dfe  mov     rcx, rbx; pszStr1
0x180779e01  call    cs:__imp_StrCmpICW
0x180779e07  test    eax, eax
0x180779e09  jnz     short loc_180779E1F
0x180779e0b  mov     rcx, [r14]; pszStr1
0x180779e0e  lea     rdx, aRedirectHtml; "redirect.html"
0x180779e15  call    cs:__imp_StrCmpICW
0x180779e1b  test    eax, eax
0x180779e1d  jz      short loc_180779DB8
0x180779e1f  mov     rcx, r13; this
0x180779e22  call    ?Length@CStr@@QEBAIXZ; CStr::Length(void)
0x180779e27  lea     r9, [rsp+370h+Value+4]; unsigned int *
0x180779e2c  mov     rcx, r12; HINSTANCE
0x180779e2f  test    eax, eax
0x180779e31  jz      short loc_180779E39
0x180779e33  mov     r8, [r13+0]
0x180779e37  jmp     short loc_180779E5D
0x180779e39  mov     rdx, [r14]; unsigned __int16 *
0x180779e3c  mov     r8d, 17h; unsigned __int16 *
0x180779e42  call    ?GetResource@@YAPEAXPEAUHINSTANCE__@@PEBG1PEAK@Z; GetResource(HINSTANCE__ *,ushort const *,ushort const *,ulong *)
0x180779e47  mov     rsi, rax
0x180779e4a  test    rax, rax
0x180779e4d  jnz     short loc_180779E7C
0x180779e4f  mov     rcx, r12; HINSTANCE
0x180779e52  lea     r9, [rsp+370h+Value+4]; unsigned int *
0x180779e57  mov     r8d, 83Eh; unsigned __int16 *
0x180779e5d  mov     rdx, [r14]; unsigned __int16 *
0x180779e60  call    ?GetResource@@YAPEAXPEAUHINSTANCE__@@PEBG1PEAK@Z; GetResource(HINSTANCE__ *,ushort const *,ushort const *,ulong *)
0x180779e65  mov     rsi, rax
0x180779e68  test    rax, rax
0x180779e6b  jnz     short loc_180779E7C
0x180779e6d  mov     r15d, [rsp+370h+Value+4]
0x180779e72  mov     ebx, 80070485h
0x180779e77  jmp     loc_18077A4E5
0x180779e7c  mov     rax, [r13+0]
0x180779e80  mov     edx, 8
0x180779e85  xor     r13d, r13d
0x180779e88  cmp     word ptr [rax], 23h ; '#'
0x180779e8c  jnz     loc_180779FDF
0x180779e92  cmp     word ptr [rax+2], 32h ; '2'
0x180779e97  jnz     loc_180779FDF
0x180779e9d  cmp     [rax+4], r13w
0x180779ea2  jnz     loc_180779FDF
0x180779ea8  mov     r15d, [rsp+370h+Value+4]
0x180779ead  lea     r9d, [rdx+4]
0x180779eb1  xor     eax, eax
0x180779eb3  mov     [rsp+370h+Value], r13d
0x180779eb8  mov     [rbp+270h+Source], rax
0x180779ebc  mov     [rbp+270h+var_298], eax
0x180779ebf  mov     [rbp+270h+var_294], ax
0x180779ec3  cmp     r15d, 28h ; '('
0x180779ec7  jb      short loc_180779EDF
0x180779ec9  cmp     dword ptr [rsi], 28h ; '('
0x180779ecc  jnz     short loc_180779EDF
0x180779ece  mov     eax, [rsi+20h]
0x180779ed1  lea     r14d, [rdx+2Eh]
0x180779ed5  mov     r8d, [rsi+10h]
0x180779ed9  movzx   ecx, word ptr [rsi+0Eh]
0x180779edd  jmp     short loc_180779EFE
0x180779edf  cmp     r15d, r9d
0x180779ee2  jb      loc_180779FE4
0x180779ee8  cmp     [rsi], r9d
0x180779eeb  jnz     loc_180779FE4
0x180779ef1  movzx   ecx, word ptr [rsi+0Ah]
0x180779ef5  mov     r8d, r13d
0x180779ef8  mov     r14d, 1Ah
0x180779efe  cmp     cx, dx
0x180779f01  ja      short loc_180779F2E
0x180779f03  test    eax, eax
0x180779f05  jnz     short loc_180779F0E
0x180779f07  mov     eax, 1
0x180779f0c  shl     eax, cl
0x180779f0e  mov     ecx, eax
0x180779f10  lea     rdx, [rsp+370h+Value]; unsigned int *
0x180779f15  shl     rcx, 2; unsigned __int64
0x180779f19  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180779f1e  mov     ebx, eax
0x180779f20  test    eax, eax
0x180779f22  jnz     loc_18077A4E5
0x180779f28  mov     edx, [rsp+370h+Value]
0x180779f2c  jmp     short loc_180779F47
0x180779f2e  mov     edx, r13d
0x180779f31  cmp     r8d, 3
0x180779f35  jnz     short loc_180779F47
0x180779f37  sub     cx, 10h
0x180779f3b  mov     eax, 0FFEFh
0x180779f40  test    ax, cx
0x180779f43  cmovz   edx, r9d
0x180779f47  lea     ecx, [r15+0Eh]
0x180779f4b  mov     eax, 4D42h
0x180779f50  mov     word ptr [rbp+270h+Source], ax
0x180779f54  cmp     ecx, 0Eh
0x180779f57  jb      short loc_180779FD5
0x180779f59  lea     eax, [r14+rdx]
0x180779f5d  mov     dword ptr [rbp+270h+Source+2], ecx
0x180779f60  or      edx, 0FFFFFFFFh
0x180779f63  mov     dword ptr [rbp+270h+Source+6], r13d
0x180779f67  cmp     eax, r14d
0x180779f6a  cmovnb  edx, eax
0x180779f6d  sbb     ebx, ebx
0x180779f6f  and     ebx, 80070216h
0x180779f75  cmp     eax, r14d
0x180779f78  jb      loc_18077A4E5
0x180779f7e  mov     [rbp+270h+var_298+2], edx
0x180779f81  mov     edx, ecx
0x180779f83  mov     rcx, cs:g_hProcessHeap
0x180779f8a  call    ??$HeapAlloc@$00@MemoryProtection@@YAPEAXPEAX_K@Z; MemoryProtection::HeapAlloc<1>(void *,unsigned __int64)
0x180779f8f  mov     [rbp+270h+var_2E0], rax
0x180779f93  mov     rbx, rax
0x180779f96  test    rax, rax
0x180779f99  jz      loc_18077A4E0
0x180779f9f  mov     edx, dword ptr [rbp+270h+Source+2]; DestinationSize
0x180779fa2  lea     r8, [rbp+270h+Source]; Source
0x180779fa6  mov     r9d, 0Eh; SourceSize
0x180779fac  mov     rcx, rax; Destination
0x180779faf  call    cs:__imp_memcpy_s
0x180779fb5  mov     edx, dword ptr [rbp+270h+Source+2]
  ... truncated ...
```
