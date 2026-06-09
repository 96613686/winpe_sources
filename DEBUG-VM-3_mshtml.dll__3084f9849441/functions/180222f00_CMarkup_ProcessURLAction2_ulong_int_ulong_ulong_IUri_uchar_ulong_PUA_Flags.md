# CMarkup::ProcessURLAction2(ulong,int *,ulong,ulong *,IUri *,uchar *,ulong,PUA_Flags)

- ea: `0x180222f00`
- end: `0x180223a85`
- name: `?ProcessURLAction2@CMarkup@@UEAAJKPEAHKPEAKPEAUIUri@@PEAEKW4PUA_Flags@@@Z`
- size: `2949`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `broker_com_uri`

## callees

- `0x1800e2b60`
- `0x1800e4964`
- `0x180146f6c`
- `0x180154a54`
- `0x1801a194c`
- `0x1801bf528`
- `0x1801c0b08`
- `0x1801f8978`
- `0x180222728`
- `0x180222f00`
- `0x180223a8c`
- `0x1802cb7c0`
- `0x1802e5024`
- `0x1802eb020`
- `0x18030035c`
- `0x18043c328`
- `0x18068e828`
- `0x1806de738`
- `0x180771400`
- `0x180811274`
- `0x1808393c4`
- `0x180890800`
- `0x1810d1010`

## import_xrefs

- `iertutil!CreateUri` at `0x180223998`
- `iertutil!CreateUri` at `0x180223998`
- `iertutil!__imp_?IECompatLogLMZL2@@YAXPEAUIUri@@K@Z` at `0x1802239ce`
- `iertutil!__imp_?IECompatLogLMZL2@@YAXPEAUIUri@@K@Z` at `0x180223a3d`
- `iertutil!__imp_?IECompatLogLMZL2@@YAXPEAUIUri@@K@Z` at `0x1802239ce`
- `iertutil!__imp_?IECompatLogLMZL2@@YAXPEAUIUri@@K@Z` at `0x180223a3d`
- `urlmon!CoInternetIsFeatureEnabled` at `0x1802230bb`
- `urlmon!CoInternetIsFeatureEnabled` at `0x180223106`
- `urlmon!CoInternetIsFeatureEnabled` at `0x1802233c7`
- `urlmon!CoInternetIsFeatureEnabled` at `0x180223495`
- `urlmon!CoInternetIsFeatureEnabled` at `0x180223660`
- `urlmon!CoInternetIsFeatureEnabled` at `0x1802230bb`
- `urlmon!CoInternetIsFeatureEnabled` at `0x180223106`
- `urlmon!CoInternetIsFeatureEnabled` at `0x1802233c7`
- `urlmon!CoInternetIsFeatureEnabled` at `0x180223495`
- `urlmon!CoInternetIsFeatureEnabled` at `0x180223660`
- `urlmon!__imp_GetZoneFromUriPrivate` at `0x1802230f0`
- `urlmon!__imp_GetZoneFromUriPrivate` at `0x1802230f0`

## string_xrefs

- `0x180223932`: `about:security_`

## pseudocode

```c
__int64 __fastcall CMarkup::ProcessURLAction2(
        __int64 a1,
        unsigned int a2,
        _DWORD *a3,
        int a4,
        _DWORD *a5,
        IUri *a6,
        __int64 a7,
        int a8,
        char a9)
{
  __int64 v12; // rax
  HRESULT Uri; // esi
  int v14; // r12d
  __int64 v15; // rdx
  int v16; // ebx
  struct CDwnDoc *DwnDoc; // rax
  int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // rax
  CMarkup *v21; // r8
  CMarkup *v22; // rax
  HRESULT v23; // eax
  int v24; // ebx
  __int64 v25; // rax
  __int64 v26; // rcx
  int v27; // r12d
  int v28; // ebx
  HRESULT v29; // eax
  __int64 v30; // rcx
  __int64 v31; // rax
  int v32; // eax
  int v33; // ecx
  _DWORD *v34; // r14
  __int64 v35; // r8
  __int64 v36; // r9
  int v37; // ecx
  __int64 v38; // rax
  CDoc *v39; // rbx
  bool v40; // al
  unsigned int v41; // edx
  void *v42; // r8
  CMarkup *v44; // rcx
  struct COmWindowProxy *v45; // rax
  CWindow *v46; // rcx
  __int64 v47; // rax
  struct CElement *FrameSite; // rbx
  struct IFrameContentData *FrameContentData; // rax
  unsigned int v50; // r14d
  HRESULT v51; // eax
  __int64 v52; // rcx
  __int64 v53; // rax
  __int64 v54; // rax
  __int64 v55; // rcx
  HRESULT v56; // eax
  __int64 v57; // rcx
  __int64 v58; // rax
  HRESULT v59; // eax
  __int64 v60; // rcx
  __int64 v61; // rax
  __int64 v62; // rcx
  __int64 v63; // rax
  _DWORD *v64; // rax
  __int64 v65; // rax
  CDoc *v66; // rbx
  bool IsPendingRoot; // al
  __int64 v68; // rdx
  __int64 v69; // rcx
  __int64 v70; // rcx
  struct GWND *Gwnd; // rax
  unsigned __int64 v72; // r10
  __int64 v73; // rax
  __int64 v74; // rax
  __int64 v75; // rax
  __int64 v76; // rax
  __int64 v77; // rax
  unsigned int v78; // r8d
  unsigned __int64 v79; // r9
  __int64 v80; // rax
  unsigned __int64 v81; // rbx
  __int64 v82; // rax
  unsigned __int64 v83; // kr00_8
  IUri *ppURI; // [rsp+60h] [rbp-49h] BYREF
  unsigned int v85; // [rsp+68h] [rbp-41h] BYREF
  unsigned __int16 *v86; // [rsp+70h] [rbp-39h] BYREF
  struct IUnknown *v87; // [rsp+78h] [rbp-31h] BYREF
  int v88; // [rsp+80h] [rbp-29h] BYREF
  int v89; // [rsp+84h] [rbp-25h] BYREF
  int v90; // [rsp+88h] [rbp-21h] BYREF
  unsigned __int64 v91; // [rsp+90h] [rbp-19h] BYREF
  int v92; // [rsp+98h] [rbp-11h] BYREF
  int v93; // [rsp+9Ch] [rbp-Dh] BYREF
  LPCWSTR pwzURI; // [rsp+A0h] [rbp-9h]
  int v95; // [rsp+F8h] [rbp+4Fh] BYREF
  _DWORD *v96; // [rsp+100h] [rbp+57h]

  v96 = a3;
  v95 = 0;
  v87 = 0;
  pwzURI = 0;
  ppURI = 0;
  *a3 = 0;
  if ( a2 == 5120 && (*(_BYTE *)(a1 + 756) & 8) != 0 )
  {
    v64 = a5;
    Uri = 0;
    *a3 = 1;
    if ( v64 )
      *v64 = 0;
    goto LABEL_75;
  }
  v12 = *(_QWORD *)(a1 + 320);
  if ( !v12 || !*(_QWORD *)(v12 + 16) )
  {
    Uri = -2147467259;
    goto LABEL_74;
  }
  if ( *(__int64 (__fastcall **)())(*(_QWORD *)a1 + 984LL) != _vtguard )
    _report_securityfailure(1);
  Uri = (*(__int64 (__fastcall **)(__int64, struct IUnknown **))(*(_QWORD *)a1 + 1016LL))(a1, &v87);
  if ( Uri < 0 )
    goto LABEL_74;
  v14 = a9 & 1;
  v15 = 128;
  if ( a2 == 4608 )
  {
    v16 = 512;
  }
  else if ( a2 == 5120 )
  {
    if ( (a9 & 1) == 0 && (unsigned int)CMarkup::DontRunScripts((CMarkup *)a1) )
      goto LABEL_75;
    v16 = v15;
    if ( (*(_DWORD *)(a1 + 756) & 0x100) != 0 && !CMarkup::SandboxAllowScript((CMarkup *)a1) )
      goto LABEL_75;
  }
  else if ( a2 == 5637 || (v16 = 0, a2 == 7168) )
  {
    v16 = 256;
  }
  if ( (a9 & 2) == 0 && v16 )
  {
    DwnDoc = CMarkup::GetDwnDoc((CMarkup *)a1);
    v15 = 0;
    if ( DwnDoc )
    {
      v18 = *((_DWORD *)DwnDoc + 41);
    }
    else
    {
      v62 = *(_QWORD *)(a1 + 320);
      v63 = 0;
      if ( v62 )
        v63 = *(_QWORD *)(v62 + 16);
      v18 = *(_DWORD *)(v63 + 4448);
    }
    if ( (v18 & v16) != 0 && (!v14 || v16 != 128 || !(unsigned int)CMarkup::DontRunScripts((CMarkup *)a1)) )
      goto LABEL_74;
  }
  if ( a6 )
  {
    ppURI = a6;
    ((void (__fastcall *)(IUri *, __int64))a6->lpVtbl->AddRef)(a6, v15);
  }
  else
  {
    Uri = CMarkup::GetUri((const struct CMarkup *const)a1, &ppURI);
    if ( Uri < 0 || !ppURI )
      goto LABEL_75;
  }
  if ( g_IEHardened
    && !(unsigned int)CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::FEATURE_HARDENING_SHOW_SECURITY_URL_ON_ABOUT_BLANK)
    && IsEqualUri(ppURI, L"about:blank", v78, v79) )
  {
    v80 = -1;
    do
      ++v80;
    while ( g_tszModuleFileName[v80] );
    v81 = v80 + 16;
    v83 = v80 + 16;
    v82 = 2 * (v80 + 16);
    if ( !is_mul_ok(v83, 2u) )
      v82 = -1;
    pwzURI = (LPCWSTR)MemoryProtection::HeapAlloc<0>(g_hProcessHeap, v82);
    if ( !pwzURI )
    {
      Uri = -2147024882;
      goto LABEL_74;
    }
    v86 = 0;
    v91 = v81;
    Uri = StringCchCopyNExW((STRSAFE_LPWSTR)pwzURI, v81, L"about:security_", 0xFu, &v86, &v91, 0x900u);
    if ( Uri >= 0 )
      Uri = StringCchCopyW(v86, v91, g_tszModuleFileName);
    ((void (__fastcall *)(IUri *))ppURI->lpVtbl->Release)(ppURI);
    if ( Uri < 0 || (Uri = CreateUri(pwzURI, 0x3002B80u, 0, &ppURI), Uri < 0) )
    {
      ppURI = 0;
      goto LABEL_74;
    }
  }
  v19 = *(_QWORD *)(a1 + 320);
  v20 = 0;
  if ( v19 )
    v20 = *(_QWORD *)(v19 + 16);
  v21 = *(CMarkup **)(a1 + 144);
  LODWORD(v86) = *(_DWORD *)(v20 + 5560);
  v22 = (CMarkup *)a1;
  if ( v21 )
    v22 = v21;
  if ( (*((_DWORD *)v22 + 187) & 0x4000000) != 0 )
  {
    if ( (*(_DWORD *)(a1 + 748) & 0x8000000) == 0 )
    {
      v44 = (CMarkup *)a1;
      if ( v21 )
        v44 = v21;
      v45 = CMarkup::Window(v44);
      goto LABEL_82;
    }
  }
  else if ( (*(_DWORD *)(a1 + 748) & 0x8000000) == 0 )
  {
    goto LABEL_25;
  }
  v45 = *(struct COmWindowProxy **)(a1 + 352);
LABEL_82:
  if ( v45 )
  {
    v46 = (CWindow *)*((_QWORD *)v45 + 15);
    if ( (*((_BYTE *)v46 + 224) & 0x40) != 0 )
    {
      a4 |= 0x100u;
    }
    else if ( (*((_BYTE *)v45 + 168) & 2) != 0 )
    {
      a4 |= 0x40u;
    }
    v47 = 0;
    if ( v19 )
      v47 = *(_QWORD *)(v19 + 16);
    if ( (*(_BYTE *)(v47 + 4860) & 1) != 0 )
    {
      FrameSite = CWindow::GetFrameSite(v46);
      FrameContentData = GetFrameContentData(FrameSite);
      if ( !FrameSite
        || (*(unsigned __int8 (__fastcall **)(struct IFrameContentData *))(*(_QWORD *)FrameContentData + 16LL))(FrameContentData) )
      {
        a4 |= 0x40u;
      }
    }
  }
LABEL_25:
  if ( !v87 )
    goto LABEL_74;
  v88 = 0;
  v85 = -1;
  v90 = -1;
  v23 = CoInternetIsFeatureEnabled(FEATURE_PROTOCOL_LOCKDOWN, 2u) == 1
      ? GetZoneFromUriPrivate(v87, ppURI, &v85, 0, 0, 0, 0x40000000, 0)
      : ((__int64 (__fastcall *)(struct IUnknown *, IUri *, unsigned int *, _QWORD, _QWORD, _QWORD))v87->lpVtbl[4].QueryInterface)(
          v87,
          ppURI,
          &v85,
          0,
          0,
          0);
  Uri = v23;
  if ( v23 )
    goto LABEL_74;
  if ( CoInternetIsFeatureEnabled(FEATURE_LOCALMACHINE_LOCKDOWN, 2u) == 1 || (v24 = 1, v85) )
    v24 = 0;
  v25 = *(_QWORD *)(a1 + 320);
  v26 = 0;
  if ( v25 )
    v26 = *(_QWORD *)(v25 + 16);
  v27 = a8;
  if ( (*(_BYTE *)(v26 + 4872) & 2) != 0 )
  {
    a4 |= 0x10000u;
LABEL_35:
    Uri = 0;
    goto LABEL_36;
  }
  Uri = 0;
  if ( !v85 && CoInternetIsFeatureEnabled(FEATURE_LOCALMACHINE_LOCKDOWN, 2u) != 1 )
  {
    v50 = a4 & 0xFFFFFFFB;
    if ( g_cmptlgs != 1 && (unsigned int)IECompatLoggingEnabled() )
      IECompatLogLMZL2(ppURI, a2);
    v51 = ((__int64 (__fastcall *)(struct IUnknown *, IUri *, _QWORD, int *, int, __int64, int, unsigned int, _QWORD, int *))v87->lpVtbl[4].AddRef)(
            v87,
            ppURI,
            a2,
            &v90,
            4,
            a7,
            v27,
            v50 | 0x10001,
            0,
            &v88);
    v52 = *(_QWORD *)(a1 + 320);
    if ( v51 != 1 )
      Uri = v51;
    v53 = 0;
    if ( v52 )
      v53 = *(_QWORD *)(v52 + 16);
    if ( *(_DWORD *)(v53 + 5560) != (_DWORD)v86 )
      goto LABEL_142;
    if ( Uri )
      goto LABEL_74;
    a4 = v50 | 0x20001;
    goto LABEL_35;
  }
LABEL_36:
  LODWORD(v91) = 0;
  v89 = -1;
  v93 = -1;
  if ( v24 || CoInternetIsFeatureEnabled(FEATURE_PROTOCOL_LOCKDOWN, 2u) == 1 )
    goto LABEL_37;
  if ( v85 > 4 )
    goto LABEL_191;
  v54 = *(_QWORD *)(a1 + 320);
  v55 = 0;
  if ( v54 )
    v55 = *(_QWORD *)(v54 + 16);
  if ( *(_DWORD *)(v55 + 4LL * v85 + 4952) == 1 )
  {
LABEL_191:
    a4 |= 0x40000u;
LABEL_37:
    v28 = (int)v86;
    goto LABEL_38;
  }
  v56 = ((__int64 (__fastcall *)(struct IUnknown *, IUri *, __int64, int *, int, __int64, int, unsigned int, _QWORD, int *))v87->lpVtbl[4].AddRef)(
          v87,
          ppURI,
          8960,
          &v89,
          4,
          a7,
          v27,
          a4 & 0xFFFBFFFA | 0x40001,
          0,
          &v88);
  v57 = *(_QWORD *)(a1 + 320);
  if ( v56 != 1 )
    Uri = v56;
  v58 = 0;
  if ( v57 )
    v58 = *(_QWORD *)(v57 + 16);
  if ( *(_DWORD *)(v58 + 5560) != (_DWORD)v86 )
    goto LABEL_142;
  if ( Uri )
    goto LABEL_74;
  v59 = ((__int64 (__fastcall *)(struct IUnknown *, IUri *, _QWORD, int *, int, __int64, int, unsigned int, _QWORD, int *))v87->lpVtbl[4].AddRef)(
          v87,
          ppURI,
          a2,
          &v93,
          4,
          a7,
          v27,
          a4 & 0xFFFBFFFA | 0x40001,
          0,
          &v88);
  v60 = *(_QWORD *)(a1 + 320);
  Uri = 0;
  if ( v59 != 1 )
    Uri = v59;
  v61 = 0;
  if ( v60 )
    v61 = *(_QWORD *)(v60 + 16);
  v28 = (int)v86;
  if ( *(_DWORD *)(v61 + 5560) != (_DWORD)v86 )
  {
LABEL_142:
    Uri = -2147467260;
    goto LABEL_74;
  }
  if ( Uri )
    goto LABEL_74;
  a4 |= 0x80000u;
  LODWORD(v91) = 1;
  if ( v89 )
    a4 |= 0x100000u;
LABEL_38:
  v92 = 0;
  v29 = ((__int64 (__fastcall *)(struct IUnknown *, IUri *, _QWORD, int *, int, __int64, int, int, _QWORD, int *))v87->lpVtbl[4].AddRef)(
          v87,
          ppURI,
          a2,
          &v95,
          4,
          a7,
          v27,
          a4,
          0,
          &v92);
  v30 = *(_QWORD *)(a1 + 320);
  Uri = 0;
  if ( v29 != 1 )
    Uri = v29;
  v31 = 0;
  if ( v30 )
    v31 = *(_QWORD *)(v30 + 16);
  if ( *(_DWORD *)(v31 + 5560) != v28 )
  {
    Uri = -2147467260;
    goto LABEL_74;
  }
  if ( Uri )
  {
LABEL_74:
    *v96 = 0;
    goto LABEL_75;
  }
  v32 = v95;
  if ( a5 )
    *a5 = v95;
  v33 = 0;
  if ( a2 == 7168 )
    LOBYTE(v33) = v32 != 0;
  else
    LOBYTE(v33) = (v32 & 0xF) == 0;
  v34 = v96;
  v35 = 0;
  *v96 = v33;
  v36 = *(_QWORD *)(a1 + 320);
  if ( v36 )
    v35 = *(_QWORD *)(v36 + 16);
  if ( (*(_BYTE *)(v35 + 4872) & 2) != 0 || v85 )
    goto LABEL_51;
  if ( CoInternetIsFeatureEnabled(FEATURE_LOCALMACHINE_LOCKDOWN, 2u) == 1 )
  {
LABEL_132:
    v32 = v95;
    goto LABEL_51;
  }
  v32 = v95;
  if ( !v95 && !v90 || v95 == 3 && v90 == 3 )
    goto LABEL_51;
  if ( v95 )
  {
LABEL_201:
    if ( g_cmptlgs != 1 )
    {
      if ( (unsigned int)IECompatLoggingEnabled() )
        IECompatLogLMZL2(ppURI, a2);
      v32 = v95;
    }
    if ( (a9 & 4) != 0 )
      goto LABEL_51;
    v65 = *(_QWORD *)(a1 + 320);
    v66 = 0;
    if ( v65 )
      v66 = *(CDoc **)(v65 + 16);
    IsPendingRoot = CMarkup::IsPendingRoot((CMarkup *)a1);
    if ( (unsigned int)CDoc::OnPageActionBlocked(v66, 0x80u, IsPendingRoot, 0) == -2147221244
      && (unsigned int)CMarkup::IsPrimaryMarkup((CMarkup *)a1) )
    {
      v68 = *(_QWORD *)(a1 + 320);
      v69 = 0;
      if ( v68 )
        v69 = *(_QWORD *)(v68 + 16);
      if ( (*(_BYTE *)(v69 + 4872) & 4) == 0 )
      {
        v70 = 0;
        if ( v68 )
          v70 = *(_QWORD *)(v68 + 16);
        *(_DWORD *)(v70 + 4872) |= 4u;
        Gwnd = GetGwnd();
        _GWPostMethodCallEx(Gwnd, v72, (__int64)CDoc::ShowLMZLUnlockDialog, 0, 1, 0);
      }
    }
    goto LABEL_132;
  }
  if ( a2 != 7168 || v90 )
  {
    *v34 = 0;
    goto LABEL_201;
  }
LABEL_51:
  if ( !(_DWORD)v91 || (v92 & 1) == 0 || !v32 && !v93 || v32 == 3 && v93 == 3 || a2 == 7168 && !v32 && !v93 )
    goto LABEL_75;
  v37 = v89;
  if ( !v32 && v89 )
    *v34 = 0;
  if ( v37 == 1 )
  {
    if ( v85 )
    {
      switch ( v85 )
      {
        case 1u:
          v75 = *(_QWORD *)(a1 + 320);
          v39 = 0;
          if ( v75 )
            v39 = *(CDoc **)(v75 + 16);
          v40 = CMarkup::IsPendingRoot((CMarkup *)a1);
          v41 = 4096;
          break;
        case 2u:
          v74 = *(_QWORD *)(a1 + 320);
          v39 = 0;
          if ( v74 )
            v39 = *(CDoc **)(v74 + 16);
          v40 = CMarkup::IsPendingRoot((CMarkup *)a1);
          v41 = 2048;
          break;
        case 3u:
          v73 = *(_QWORD *)(a1 + 320);
          v39 = 0;
          if ( v73 )
            v39 = *(CDoc **)(v73 + 16);
          v40 = CMarkup::IsPendingRoot((CMarkup *)a1);
          v41 = 0x2000;
          break;
        case 4u:
          v38 = *(_QWORD *)(a1 + 320);
          v39 = 0;
          if ( v38 )
            v39 = *(CDoc **)(v38 + 16);
          v40 = CMarkup::IsPendingRoot((CMarkup *)a1);
          v41 = 0x4000;
          break;
        default:
          goto LABEL_75;
      }
    }
    else
    {
      v76 = *(_QWORD *)(a1 + 320);
      v39 = 0;
      if ( v76 )
        v39 = *(CDoc **)(v76 + 16);
      v40 = CMarkup::IsPendingRoot((CMarkup *)a1);
      v41 = 1024;
    }
    goto LABEL_72;
  }
  if ( v37 == 3 )
  {
    v77 = *(_QWORD *)(a1 + 320);
    v39 = 0;
    if ( v77 )
      v39 = *(CDoc **)(v77 + 16);
    v40 = CMarkup::IsPendingRoot((CMarkup *)a1);
    v41 = 0x8000;
LABEL_72:
    CDoc::OnPageActionBlocked(v39, v41, v40, 0);
  }
LABEL_75:
  ReleaseInterface(v87);
  ReleaseInterface((struct IUnknown *)ppURI);
  if ( pwzURI )
    MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, (void *)pwzURI, v42);
  return (unsigned int)Uri;
}

```

## disassembly

```asm
0x180222f00  mov     [rsp-8+arg_0], rbx
0x180222f05  mov     [rsp-8+arg_10], r8
0x180222f0a  push    rbp
0x180222f0b  push    rsi
0x180222f0c  push    rdi
0x180222f0d  push    r12
0x180222f0f  push    r13
0x180222f11  push    r14
0x180222f13  push    r15
0x180222f15  lea     rbp, [rsp-7]
0x180222f1a  sub     rsp, 0B0h
0x180222f21  xor     r12d, r12d
0x180222f24  mov     ebx, 1400h
0x180222f29  mov     [rbp+37h+arg_8], r12d
0x180222f2d  mov     r14d, r9d
0x180222f30  mov     [rbp+37h+var_68], r12
0x180222f34  mov     r13d, edx
0x180222f37  mov     [rbp+37h+pwzURI], r12
0x180222f3b  mov     rdi, rcx
0x180222f3e  mov     [rbp+37h+ppURI], r12
0x180222f42  mov     [r8], r12d
0x180222f45  cmp     edx, ebx
0x180222f47  jnz     short loc_180222F56
0x180222f49  test    byte ptr [rcx+2F4h], 8
0x180222f50  jnz     loc_1802236AF
0x180222f56  mov     rax, [rcx+140h]
0x180222f5d  test    rax, rax
0x180222f60  jz      loc_1802232D8
0x180222f66  cmp     [rax+10h], r12
0x180222f6a  jz      loc_1802232D8
0x180222f70  mov     rax, [rcx]
0x180222f73  lea     rcx, __vtguard
0x180222f7a  cmp     [rax+3D8h], rcx
0x180222f81  jnz     loc_180223A66
0x180222f87  mov     rax, [rax+3F8h]
0x180222f8e  lea     rdx, [rbp+37h+var_68]
0x180222f92  mov     rcx, rdi
0x180222f95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180222f9a  mov     esi, eax
0x180222f9c  test    eax, eax
0x180222f9e  js      loc_1802232DD
0x180222fa4  mov     r12d, [rbp+37h+arg_40]
0x180222fab  mov     r15d, 1
0x180222fb1  mov     eax, 100h
0x180222fb6  and     r12d, r15d
0x180222fb9  lea     edx, [rax-80h]
0x180222fbc  cmp     r13d, 1200h
0x180222fc3  jz      loc_180223871
0x180222fc9  cmp     r13d, ebx
0x180222fcc  jz      loc_1802235EB
0x180222fd2  cmp     r13d, 1605h
0x180222fd9  jz      loc_18022386A
0x180222fdf  xor     r8d, r8d
0x180222fe2  mov     ebx, r8d
0x180222fe5  cmp     r13d, 1C00h
0x180222fec  jz      loc_18022386A
0x180222ff2  test    byte ptr [rbp+37h+arg_40], 2
0x180222ff9  jnz     short loc_180223020
0x180222ffb  test    ebx, ebx
0x180222ffd  jz      short loc_180223020
0x180222fff  mov     rcx, rdi; this
0x180223002  call    ?GetDwnDoc@CMarkup@@QEAAPEAVCDwnDoc@@XZ; CMarkup::GetDwnDoc(void)
0x180223007  xor     edx, edx
0x180223009  test    rax, rax
0x18022300c  jz      loc_180223691
0x180223012  mov     eax, [rax+0A4h]
0x180223018  test    ebx, eax
0x18022301a  jnz     loc_18022387B
0x180223020  xor     r12d, r12d
0x180223023  mov     rcx, [rbp+37h+arg_28]
0x180223027  test    rcx, rcx
0x18022302a  jz      loc_180223629
0x180223030  mov     [rbp+37h+ppURI], rcx
0x180223034  mov     rax, [rcx]
0x180223037  mov     rax, [rax+8]
0x18022303b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180223040  cmp     cs:?g_IEHardened@@3HA, r12d; int g_IEHardened
0x180223047  jnz     loc_1802238A8
0x18022304d  mov     rdx, [rdi+140h]
0x180223054  mov     rax, r12
0x180223057  test    rdx, rdx
0x18022305a  jz      short loc_180223060
0x18022305c  mov     rax, [rdx+10h]
0x180223060  mov     eax, [rax+15B8h]
0x180223066  mov     r8, [rdi+90h]
0x18022306d  mov     dword ptr [rbp+37h+var_70], eax
0x180223070  test    r8, r8
0x180223073  mov     rax, rdi
0x180223076  cmovnz  rax, r8
0x18022307a  mov     eax, [rax+2ECh]
0x180223080  shr     eax, 1Ah
0x180223083  test    r15b, al
0x180223086  jnz     loc_180223320
0x18022308c  test    dword ptr [rdi+2ECh], 8000000h
0x180223096  jnz     loc_1802236E5
0x18022309c  cmp     [rbp+37h+var_68], r12
0x1802230a0  jz      loc_1802232DD
0x1802230a6  or      eax, 0FFFFFFFFh
0x1802230a9  mov     [rbp+37h+var_60], r12d
0x1802230ad  mov     edx, 2; dwFlags
0x1802230b2  mov     [rbp+37h+var_78], eax
0x1802230b5  mov     [rbp+37h+var_58], eax
0x1802230b8  lea     ecx, [rdx+0Ch]; FeatureEntry
0x1802230bb  call    cs:__imp_CoInternetIsFeatureEnabled
0x1802230c1  mov     rcx, [rbp+37h+var_68]
0x1802230c5  lea     r8, [rbp+37h+var_78]
0x1802230c9  mov     rdx, [rbp+37h+ppURI]
0x1802230cd  xor     r9d, r9d
0x1802230d0  cmp     eax, r15d
0x1802230d3  jnz     loc_180223472
0x1802230d9  mov     [rsp+0E0h+var_A8], r12
0x1802230de  mov     [rsp+0E0h+var_B0], 40000000h
0x1802230e6  mov     [rsp+0E0h+var_B8], r12
0x1802230eb  mov     [rsp+0E0h+var_C0], r12
0x1802230f0  call    cs:__imp_GetZoneFromUriPrivate
0x1802230f6  mov     esi, eax
0x1802230f8  test    eax, eax
0x1802230fa  jnz     loc_1802232DD
0x180223100  lea     edx, [rax+2]; dwFlags
0x180223103  lea     ecx, [rax+8]; FeatureEntry
0x180223106  call    cs:__imp_CoInternetIsFeatureEnabled
0x18022310c  mov     edx, [rbp+37h+var_78]
0x18022310f  cmp     eax, r15d
0x180223112  jnz     loc_180223677
0x180223118  mov     ebx, r12d
0x18022311b  mov     rax, [rdi+140h]
0x180223122  mov     rcx, r12
0x180223125  test    rax, rax
0x180223128  jz      short loc_18022312E
0x18022312a  mov     rcx, [rax+10h]
0x18022312e  test    byte ptr [rcx+1308h], 2
0x180223135  mov     r12d, [rbp+37h+arg_38]
0x180223139  jz      loc_1802233B7
0x18022313f  bts     r14d, 10h
0x180223144  xor     esi, esi
0x180223146  or      eax, 0FFFFFFFFh
0x180223149  mov     dword ptr [rbp+37h+var_50], esi
0x18022314c  mov     [rbp+37h+var_5C], eax
0x18022314f  mov     [rbp+37h+var_44], eax
0x180223152  test    ebx, ebx
0x180223154  jz      loc_18022348D
0x18022315a  mov     ebx, dword ptr [rbp+37h+var_70]
0x18022315d  mov     rcx, [rbp+37h+var_68]
0x180223161  lea     rdx, [rbp+37h+var_48]
0x180223165  mov     [rsp+0E0h+var_98], rdx
0x18022316a  lea     r9, [rbp+37h+arg_8]
0x18022316e  mov     rdx, [rbp+37h+arg_30]
0x180223172  mov     r8d, r13d
0x180223175  mov     [rsp+0E0h+var_A0], rsi
0x18022317a  mov     dword ptr [rsp+0E0h+var_A8], r14d
0x18022317f  mov     [rbp+37h+var_48], esi
0x180223182  mov     rax, [rcx]
0x180223185  mov     [rsp+0E0h+var_B0], r12d
0x18022318a  mov     [rsp+0E0h+var_B8], rdx
0x18022318f  mov     rdx, [rbp+37h+ppURI]
0x180223193  mov     rax, [rax+68h]
0x180223197  mov     dword ptr [rsp+0E0h+var_C0], 4
0x18022319f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802231a4  mov     rcx, [rdi+140h]
0x1802231ab  xor     r12d, r12d
0x1802231ae  cmp     eax, r15d
0x1802231b1  mov     esi, r12d
0x1802231b4  cmovnz  esi, eax
0x1802231b7  mov     eax, r12d
0x1802231ba  test    rcx, rcx
0x1802231bd  jz      short loc_1802231C3
0x1802231bf  mov     rax, [rcx+10h]
0x1802231c3  cmp     [rax+15B8h], ebx
0x1802231c9  jnz     loc_1802239E3
0x1802231cf  test    esi, esi
0x1802231d1  jnz     loc_1802232DD
0x1802231d7  mov     rcx, [rbp+37h+arg_20]
0x1802231db  mov     eax, [rbp+37h+arg_8]
0x1802231de  test    rcx, rcx
0x1802231e1  jnz     loc_1802236F1
0x1802231e7  mov     ecx, r12d
0x1802231ea  cmp     r13d, 1C00h
0x1802231f1  jz      loc_180223687
0x1802231f7  test    al, 0Fh
0x1802231f9  setz    cl
0x1802231fc  mov     r14, [rbp+37h+arg_10]
0x180223200  mov     r8, r12
0x180223203  mov     [r14], ecx
0x180223206  mov     r9, [rdi+140h]
0x18022320d  test    r9, r9
0x180223210  jz      short loc_180223216
0x180223212  mov     r8, [r9+10h]
0x180223216  test    byte ptr [r8+1308h], 2
0x18022321e  jz      loc_18022364E
0x180223224  cmp     dword ptr [rbp+37h+var_50], r12d
0x180223228  jz      loc_1802232E4
0x18022322e  test    byte ptr [rbp+37h+var_48], r15b
0x180223232  jz      loc_1802232E4
0x180223238  mov     ecx, [rbp+37h+var_44]
0x18022323b  test    eax, eax
0x18022323d  jnz     short loc_180223247
0x18022323f  test    ecx, ecx
0x180223241  jz      loc_1802232E4
0x180223247  cmp     eax, 3
0x18022324a  jnz     short loc_180223254
0x18022324c  cmp     ecx, eax
0x18022324e  jz      loc_1802232E4
0x180223254  cmp     r13d, 1C00h
0x18022325b  jnz     short loc_180223265
0x18022325d  test    eax, eax
0x18022325f  jnz     short loc_180223265
0x180223261  test    ecx, ecx
0x180223263  jz      short loc_1802232E4
0x180223265  mov     ecx, [rbp+37h+var_5C]
0x180223268  test    eax, eax
0x18022326a  jnz     short loc_180223273
0x18022326c  test    ecx, ecx
0x18022326e  jz      short loc_180223273
0x180223270  mov     [r14], r12d
0x180223273  cmp     ecx, r15d
0x180223276  jnz     loc_180223A58
0x18022327c  mov     eax, [rbp+37h+var_78]
0x18022327f  test    eax, eax
0x180223281  jz      loc_180223820
0x180223287  sub     eax, r15d
0x18022328a  jz      loc_1802237FB
0x180223290  sub     eax, r15d
0x180223293  jz      loc_1802237D6
0x180223299  sub     eax, r15d
0x18022329c  jz      loc_1802237B1
0x1802232a2  cmp     eax, r15d
0x1802232a5  jnz     short loc_1802232E4
0x1802232a7  mov     rax, [rdi+140h]
0x1802232ae  mov     rbx, r12
0x1802232b1  test    rax, rax
0x1802232b4  jz      short loc_1802232BA
0x1802232b6  mov     rbx, [rax+10h]
0x1802232ba  mov     rcx, rdi; this
0x1802232bd  call    ?IsPendingRoot@CMarkup@@QEAA_NXZ; CMarkup::IsPendingRoot(void)
0x1802232c2  mov     edx, 4000h; unsigned int
0x1802232c7  xor     r9d, r9d; struct BLOCKED_ACTION_DETAILS *
0x1802232ca  movzx   r8d, al; int
0x1802232ce  mov     rcx, rbx; this
0x1802232d1  call    ?OnPageActionBlocked@CDoc@@QEAAJKHPEAUBLOCKED_ACTION_DETAILS@@@Z; CDoc::OnPageActionBlocked(ulong,int,BLOCKED_ACTION_DETAILS *)
0x1802232d6  jmp     short loc_1802232E4
0x1802232d8  mov     esi, 80004005h
0x1802232dd  mov     r14, [rbp+37h+arg_10]
0x1802232e1  mov     [r14], r12d
0x1802232e4  mov     rcx, [rbp+37h+var_68]; struct IUnknown *
0x1802232e8  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x1802232ed  mov     rcx, [rbp+37h+ppURI]; struct IUnknown *
0x1802232f1  call    ?ReleaseInterface@@YAXPEAUIUnknown@@@Z; ReleaseInterface(IUnknown *)
0x1802232f6  mov     rax, [rbp+37h+pwzURI]
0x1802232fa  test    rax, rax
0x1802232fd  jnz     loc_180223A71
0x180223303  mov     rbx, [rsp+0E0h+arg_0]
0x18022330b  mov     eax, esi
0x18022330d  add     rsp, 0B0h
0x180223314  pop     r15
0x180223316  pop     r14
0x180223318  pop     r13
0x18022331a  pop     r12
0x18022331c  pop     rdi
0x18022331d  pop     rsi
0x18022331e  pop     rbp
0x18022331f  retn
0x180223320  test    dword ptr [rdi+2ECh], 8000000h
0x18022332a  jnz     loc_1802236E5
0x180223330  test    r8, r8
0x180223333  mov     rcx, rdi
0x180223336  cmovnz  rcx, r8; this
0x18022333a  call    ?Window@CMarkup@@QEBAPEAVCOmWindowProxy@@XZ; CMarkup::Window(void)
0x18022333f  test    rax, rax
0x180223342  jz      loc_18022309C
0x180223348  mov     rcx, [rax+78h]; this
0x18022334c  test    byte ptr [rcx+0E0h], 40h
0x180223353  jnz     loc_1802236CE
0x180223359  test    byte ptr [rax+0A8h], 2
0x180223360  jnz     loc_1802239B1
0x180223366  mov     rax, r12
0x180223369  test    rdx, rdx
0x18022336c  jz      short loc_180223372
0x18022336e  mov     rax, [rdx+10h]
0x180223372  test    [rax+12FCh], r15b
0x180223379  jz      loc_18022309C
0x18022337f  call    ?GetFrameSite@CWindow@@QEAAPEAVCFrameSite@@XZ; CWindow::GetFrameSite(void)
0x180223384  mov     rcx, rax; struct CElement *
0x180223387  mov     rbx, rax
0x18022338a  call    ?GetFrameContentData@@YAPEAUIFrameContentData@@PEAVCElement@@@Z; GetFrameContentData(CElement *)
0x18022338f  mov     rdx, rax
0x180223392  test    rbx, rbx
0x180223395  jz      short loc_1802233AE
0x180223397  mov     rcx, [rax]
0x18022339a  mov     rax, [rcx+10h]
0x18022339e  mov     rcx, rdx
0x1802233a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802233a6  test    al, al
0x1802233a8  jz      loc_18022309C
0x1802233ae  or      r14d, 40h
0x1802233b2  jmp     loc_18022309C
0x1802233b7  xor     esi, esi
0x1802233b9  test    edx, edx
0x1802233bb  jnz     loc_180223146
0x1802233c1  lea     edx, [rsi+2]; dwFlags
0x1802233c4  lea     ecx, [rsi+8]; FeatureEntry
  ... truncated ...
```
