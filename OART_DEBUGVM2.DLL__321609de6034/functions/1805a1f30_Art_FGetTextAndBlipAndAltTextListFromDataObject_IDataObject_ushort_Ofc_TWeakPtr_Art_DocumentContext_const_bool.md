# Art::FGetTextAndBlipAndAltTextListFromDataObject(IDataObject *,ushort,Ofc::TWeakPtr<Art::DocumentContext> const &,bool,bool,IMsoHTMLFileReferenceResolver *,IMetroProgress *,Ofc::TOwningPtr<Art::TextBody> &,Ofc::TOwnerPtrList<Art::BlipAndAltText> &,Art::TextAutofit &,Ofc::TOwningPtr<Art::ClipboardTextResolver> &,Ofc::CVarStr &,bool *,bool *,bool *)

- ea: `0x1805a1f30`
- end: `0x1805a27e4`
- name: `?FGetTextAndBlipAndAltTextListFromDataObject@Art@@YA_NPEAUIDataObject@@GAEBV?$TWeakPtr@VDocumentContext@Art@@@Ofc@@_N2PEAUIMsoHTMLFileReferenceResolver@@PEAUIMetroProgress@@AEAV?$TOwningPtr@VTextBody@Art@@@4@AEAV?$TOwnerPtrList@VBlipAndAltText@Art@@@4@AEAVTextAutofit@1@AEAV?$TOwningPtr@VClipboardTextResolver@Art@@@4@AEAVCVarStr@4@PEA_NPEA_NPEA_N@Z`
- size: `2228`
- prototype: `__int64 __usercall@<rax>(struct IDataObject *@<rcx>, char, __int64, __int64, __int64, __int64, __int64, __int64, Ofc::CVarStr *, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `29`
- tags: `file_ops, registry_config`

## callers

- `0x1805a1e90`
- `0x18097b160`
- `0x18097b8d0`

## callees

- `0x18000e858`
- `0x180019a9c`
- `0x180019f40`
- `0x1800740e0`
- `0x1801e4320`
- `0x180208ac0`
- `0x180279030`
- `0x180279050`
- `0x1802b8c50`
- `0x1802b8cc0`
- `0x1802b8e70`
- `0x1804378f0`
- `0x1804f5ebc`
- `0x18054b3e0`
- `0x180579390`
- `0x18059fa0c`
- `0x1805a1f30`
- `0x1805b36d0`
- `0x1805ff1b0`
- `0x18061b2c4`
- `0x18065e184`
- `0x1806bc4f0`
- `0x1806bc6a8`
- `0x1806d19bc`
- `0x1806d2118`
- `0x1809805dc`
- `0x1809806f4`
- `0x180980ae0`
- `0x180a2473c`

## import_xrefs

- `KERNEL32!GlobalLock` at `0x1805a25b0`
- `KERNEL32!GlobalLock` at `0x1805a26bb`
- `KERNEL32!GlobalLock` at `0x1805a25b0`
- `KERNEL32!GlobalLock` at `0x1805a26bb`
- `KERNEL32!GlobalUnlock` at `0x1805a25fa`
- `KERNEL32!GlobalUnlock` at `0x1805a26ec`
- `KERNEL32!GlobalUnlock` at `0x1805a25fa`
- `KERNEL32!GlobalUnlock` at `0x1805a26ec`
- `Mso30Win32Client!__imp_?GetPolicyProtectionManagerFactory@EnterpriseDataProtection@Mso@@YAAEAUIPolicyProtectionManager@12@XZ` at `0x1805a20e1`
- `Mso30Win32Client!__imp_?GetPolicyProtectionManagerFactory@EnterpriseDataProtection@Mso@@YAAEAUIPolicyProtectionManager@12@XZ` at `0x1805a20e1`
- `Mso30Win32Client!__imp_?GetEnterpriseIdOfCurrentClipboardData@Clipboard@Mso@@YA?AVEnterpriseIdentity@EnterpriseDataProtection@2@XZ` at `0x1805a21a6`
- `Mso30Win32Client!__imp_?GetEnterpriseIdOfCurrentClipboardData@Clipboard@Mso@@YA?AVEnterpriseIdentity@EnterpriseDataProtection@2@XZ` at `0x1805a2326`
- `Mso30Win32Client!__imp_?GetEnterpriseIdOfCurrentClipboardData@Clipboard@Mso@@YA?AVEnterpriseIdentity@EnterpriseDataProtection@2@XZ` at `0x1805a244b`
- `Mso30Win32Client!__imp_?GetEnterpriseIdOfCurrentClipboardData@Clipboard@Mso@@YA?AVEnterpriseIdentity@EnterpriseDataProtection@2@XZ` at `0x1805a2745`
- `Mso30Win32Client!__imp_?GetEnterpriseIdOfCurrentClipboardData@Clipboard@Mso@@YA?AVEnterpriseIdentity@EnterpriseDataProtection@2@XZ` at `0x1805a21a6`
- `Mso30Win32Client!__imp_?GetEnterpriseIdOfCurrentClipboardData@Clipboard@Mso@@YA?AVEnterpriseIdentity@EnterpriseDataProtection@2@XZ` at `0x1805a2326`
- `Mso30Win32Client!__imp_?GetEnterpriseIdOfCurrentClipboardData@Clipboard@Mso@@YA?AVEnterpriseIdentity@EnterpriseDataProtection@2@XZ` at `0x1805a244b`
- `Mso30Win32Client!__imp_?GetEnterpriseIdOfCurrentClipboardData@Clipboard@Mso@@YA?AVEnterpriseIdentity@EnterpriseDataProtection@2@XZ` at `0x1805a2745`
- `Mso30Win32Client!__imp_?OleGetClipboardAndRequestAccessSynchronously@Clipboard@Mso@@YAJPEAPEAUIDataObject@@AEBVEnterpriseIdentity@EnterpriseDataProtection@2@PEAUHWND__@@W4EDPOverride@12@@Z` at `0x1805a21e2`
- `Mso30Win32Client!__imp_?OleGetClipboardAndRequestAccessSynchronously@Clipboard@Mso@@YAJPEAPEAUIDataObject@@AEBVEnterpriseIdentity@EnterpriseDataProtection@2@PEAUHWND__@@W4EDPOverride@12@@Z` at `0x1805a2359`
- `Mso30Win32Client!__imp_?OleGetClipboardAndRequestAccessSynchronously@Clipboard@Mso@@YAJPEAPEAUIDataObject@@AEBVEnterpriseIdentity@EnterpriseDataProtection@2@PEAUHWND__@@W4EDPOverride@12@@Z` at `0x1805a247e`
- `Mso30Win32Client!__imp_?OleGetClipboardAndRequestAccessSynchronously@Clipboard@Mso@@YAJPEAPEAUIDataObject@@AEBVEnterpriseIdentity@EnterpriseDataProtection@2@PEAUHWND__@@W4EDPOverride@12@@Z` at `0x1805a2778`
- `Mso30Win32Client!__imp_?OleGetClipboardAndRequestAccessSynchronously@Clipboard@Mso@@YAJPEAPEAUIDataObject@@AEBVEnterpriseIdentity@EnterpriseDataProtection@2@PEAUHWND__@@W4EDPOverride@12@@Z` at `0x1805a21e2`
- `Mso30Win32Client!__imp_?OleGetClipboardAndRequestAccessSynchronously@Clipboard@Mso@@YAJPEAPEAUIDataObject@@AEBVEnterpriseIdentity@EnterpriseDataProtection@2@PEAUHWND__@@W4EDPOverride@12@@Z` at `0x1805a2359`
- `Mso30Win32Client!__imp_?OleGetClipboardAndRequestAccessSynchronously@Clipboard@Mso@@YAJPEAPEAUIDataObject@@AEBVEnterpriseIdentity@EnterpriseDataProtection@2@PEAUHWND__@@W4EDPOverride@12@@Z` at `0x1805a247e`
- `Mso30Win32Client!__imp_?OleGetClipboardAndRequestAccessSynchronously@Clipboard@Mso@@YAJPEAPEAUIDataObject@@AEBVEnterpriseIdentity@EnterpriseDataProtection@2@PEAUHWND__@@W4EDPOverride@12@@Z` at `0x1805a2778`
- `USER32!GetDesktopWindow` at `0x1805a2101`
- `USER32!GetDesktopWindow` at `0x1805a2101`
- `USER32!CloseClipboard` at `0x1805a259e`
- `USER32!CloseClipboard` at `0x1805a26ad`
- `USER32!CloseClipboard` at `0x1805a259e`
- `USER32!CloseClipboard` at `0x1805a26ad`
- `USER32!GetClipboardData` at `0x1805a2595`
- `USER32!GetClipboardData` at `0x1805a26a4`
- `USER32!GetClipboardData` at `0x1805a2595`
- `USER32!GetClipboardData` at `0x1805a26a4`
- `ole32!ReleaseStgMedium` at `0x1805a2567`
- `ole32!ReleaseStgMedium` at `0x1805a2609`
- `ole32!ReleaseStgMedium` at `0x1805a26fb`
- `ole32!ReleaseStgMedium` at `0x1805a2567`
- `ole32!ReleaseStgMedium` at `0x1805a2609`
- `ole32!ReleaseStgMedium` at `0x1805a26fb`

## pseudocode

```c
char __fastcall Art::FGetTextAndBlipAndAltTextListFromDataObject(
        struct IDataObject *a1,
        CLIPFORMAT a2,
        struct Ofc::CProxyPtrImpl **a3,
        char a4,
        char a5,
        __int64 a6,
        __int64 a7,
        Ofc::CProxyPtrImpl **a8,
        struct IDataObject *a9,
        __int64 a10,
        Art::ClipboardStyleSheet *a11,
        Ofc::CVarStr *a12,
        _BYTE *a13,
        struct IDataObject *a14,
        struct IDataObject *a15)
{
  Ofc::CProxyPtrImpl **v18; // r14
  char v19; // di
  HWND DesktopWindow; // r13
  struct Ofc::CProxyPtrImpl *v21; // rax
  Mso::EnterpriseDataProtection *hBitmap; // rcx
  HBITMAP v23; // r8
  void *Checked; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rdx
  struct Mso::EnterpriseDataProtection::IPolicyProtectionManager *PolicyProtectionManagerFactory; // rax
  struct IDataObject *v29; // rcx
  int v30; // r8d
  char v31; // al
  char v32; // bl
  STGMEDIUM *v33; // rcx
  int v34; // r8d
  char v35; // al
  void (*Release)(void); // rax
  Art *v37; // rcx
  __int64 v38; // rcx
  STGMEDIUM *v39; // rcx
  struct IDataObject *v40; // rcx
  __int64 EnterpriseIdOfCurrentClipboardData; // rbx
  __int64 v42; // rcx
  struct IDataObject *v43; // rcx
  Art *v44; // rcx
  __int64 v45; // rbx
  Art *v47; // rcx
  Ofc::CStr *ClipboardData; // rbx
  STGMEDIUM *p_hMem; // rcx
  Art *v50; // rcx
  const struct Art::FormatInfo *RTFFormatInfo; // rax
  Ofc::CStr *v52; // r15
  __int64 v53; // rax
  bool v54; // zf
  Art *v55; // rcx
  void *v56; // rsi
  Art *v57; // rcx
  const struct Art::FormatInfo *UnicodeTextFormatInfo; // rax
  void *v59; // rbx
  __int64 v60; // rbx
  char v61; // [rsp+50h] [rbp-B0h] BYREF
  char v62; // [rsp+51h] [rbp-AFh]
  struct IDataObject *v63; // [rsp+58h] [rbp-A8h] BYREF
  struct IDataObject *v64; // [rsp+60h] [rbp-A0h] BYREF
  struct IDataObject *v65; // [rsp+68h] [rbp-98h] BYREF
  struct IDataObject *v66; // [rsp+70h] [rbp-90h] BYREF
  STGMEDIUM hMem; // [rsp+80h] [rbp-80h] BYREF
  struct IDataObject *v68; // [rsp+A0h] [rbp-60h] BYREF
  struct tagFORMATETC v69; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v70; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v71; // [rsp+D0h] [rbp-30h]
  Art::ClipboardStyleSheet *v72; // [rsp+D8h] [rbp-28h]
  __int64 v73; // [rsp+E0h] [rbp-20h]
  struct Ofc::CProxyPtrImpl *v74; // [rsp+E8h] [rbp-18h] BYREF
  Ofc::CStr *v75[4]; // [rsp+F0h] [rbp-10h] BYREF
  STGMEDIUM v76; // [rsp+110h] [rbp+10h] BYREF
  STGMEDIUM v77; // [rsp+128h] [rbp+28h] BYREF
  STGMEDIUM v78; // [rsp+148h] [rbp+48h] BYREF
  _BYTE v79[8]; // [rsp+168h] [rbp+68h] BYREF
  _BYTE v80[40]; // [rsp+170h] [rbp+70h] BYREF

  v61 = a4;
  v72 = a11;
  v18 = a8;
  v71 = a6;
  v63 = a9;
  v73 = a10;
  v75[0] = a12;
  v64 = a14;
  v65 = a15;
  if ( a13 )
    *a13 = 0;
  Ofc::CVarStr::Reset(a12);
  Ofc::CProxyPtrImpl::StrongRelease(*a8);
  *a8 = (Ofc::CProxyPtrImpl *)&`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_proxyPtrSentinel;
  Ofc::CProxyPtrImpl::StrongRelease(*(Ofc::CProxyPtrImpl **)a11);
  *(_QWORD *)a11 = &`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_proxyPtrSentinel;
  *(_DWORD *)(&v69.cfFormat + 1) = 0;
  *(&v69.cfFormat + 3) = 0;
  *(_QWORD *)&v69.tymed = 1;
  v69.cfFormat = a2;
  v69.ptd = 0;
  v19 = 1;
  v69.dwAspect = 1;
  v69.lindex = -1;
  DesktopWindow = 0;
  v21 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(*a3);
  v74 = v21;
  if ( *((HBITMAP *)v21 + 2) == v23 )
    goto LABEL_11;
  *(_QWORD *)&hMem.tymed = &Art::HostParentWindowInfo::`vftable';
  hMem.hBitmap = v23;
  Checked = Ofc::CProxyPtrImpl::GetChecked(v21);
  if ( (*(unsigned __int8 (__fastcall **)(void *, STGMEDIUM *))(*(_QWORD *)Checked + 160LL))(Checked, &hMem) )
  {
    if ( hMem.hBitmap )
    {
      v25 = Mso::IObjectProxy::QueryObjectElseCrash<Mso::PlatformCanvas::IHWNDCanvas,0>(hMem.hBitmap, &v70);
      v26 = Mso::TCntPtr<Art::AugLoop::AppAugmentationStatefulRuntime>::operator->(v25);
      DesktopWindow = (HWND)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 40LL))(v26);
      v27 = v70;
      if ( v70 )
      {
        v70 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 8LL))(v27);
      }
    }
  }
  hBitmap = (Mso::EnterpriseDataProtection *)hMem.hBitmap;
  if ( hMem.hBitmap )
  {
    hMem.hBitmap = 0;
    (*(void (__fastcall **)(Mso::EnterpriseDataProtection *))(*(_QWORD *)hBitmap + 8LL))(hBitmap);
  }
  if ( !DesktopWindow )
  {
LABEL_11:
    PolicyProtectionManagerFactory = Mso::EnterpriseDataProtection::GetPolicyProtectionManagerFactory(hBitmap);
    if ( (**(unsigned __int8 (__fastcall ***)(struct Mso::EnterpriseDataProtection::IPolicyProtectionManager *))PolicyProtectionManagerFactory)(PolicyProtectionManagerFactory) )
      goto LABEL_57;
    DesktopWindow = GetDesktopWindow();
  }
  if ( a2 != *((_WORD *)Art::GetHTMLFormatInfo(hBitmap) + 6) )
  {
LABEL_32:
    if ( a2 == *((_WORD *)Art::GetMathMLFormatInfo((Art *)v29) + 6) )
    {
      v63 = 0;
      if ( a1 )
      {
        Art::TxStgMedium::TxStgMedium((Art::TxStgMedium *)&v78, a1, &v69);
        v32 = Art::FGetTextFromMathMLStream(v38, &v78, a8, a13);
        v39 = &v78;
LABEL_35:
        Art::TxStgMedium::~TxStgMedium(v39);
        v40 = v63;
LABEL_36:
        if ( !v40 )
          goto LABEL_108;
        Release = (void (*)(void))v40->lpVtbl->Release;
        goto LABEL_29;
      }
      EnterpriseIdOfCurrentClipboardData = Mso::Clipboard::GetEnterpriseIdOfCurrentClipboardData(v79);
      v63 = 0;
      if ( (unsigned int)Mso::Clipboard::OleGetClipboardAndRequestAccessSynchronously(
                           &v63,
                           EnterpriseIdOfCurrentClipboardData,
                           DesktopWindow,
                           0)
        || !v63 )
      {
        v19 = 0;
      }
      std::wstring::~wstring(v80);
      if ( v19 )
      {
        Art::TxStgMedium::TxStgMedium((Art::TxStgMedium *)v79, v63, &v69);
        v32 = Art::FGetTextFromMathMLStream(v42, v79, a8, a13);
        v39 = (STGMEDIUM *)v79;
        goto LABEL_35;
      }
      v43 = v63;
      goto LABEL_55;
    }
    if ( a2 == *((_WORD *)Art::GetNativeTextFormatInfo(v37) + 6) )
    {
      if ( *((_QWORD *)*a3 + 2) )
      {
        v64 = 0;
        if ( !a1 )
        {
          v45 = Mso::Clipboard::GetEnterpriseIdOfCurrentClipboardData(v79);
          v64 = 0;
          if ( (unsigned int)Mso::Clipboard::OleGetClipboardAndRequestAccessSynchronously(&v64, v45, DesktopWindow, 0)
            || !v64 )
          {
            v19 = 0;
          }
          std::wstring::~wstring(v80);
          if ( v19 )
          {
            v32 = Art::FGetTextFromGvmlStream((unsigned int)&v64, (_DWORD)a3, (_DWORD)a8, v73, v72);
            v40 = v64;
            goto LABEL_36;
          }
          v43 = v64;
LABEL_55:
          if ( v43 )
            ((void (__fastcall *)(struct IDataObject *))v43->lpVtbl->Release)(v43);
          goto LABEL_57;
        }
        v68 = a1;
        ((void (__fastcall *)(struct IDataObject *))a1->lpVtbl->AddRef)(a1);
        v19 = Art::FGetTextFromGvmlStream((unsigned int)&v68, (_DWORD)a3, (_DWORD)a8, v73, v72);
        ((void (__fastcall *)(struct IDataObject *))a1->lpVtbl->Release)(a1);
LABEL_48:
        v32 = v19;
        goto LABEL_108;
      }
      goto LABEL_107;
    }
    if ( a2 == *((_WORD *)Art::GetRTFFormatInfo(v44) + 6) )
    {
      memset(&v76, 0, sizeof(v76));
      DesktopWindow = 0;
      LOBYTE(a2) = 0;
      if ( a1 )
      {
        if ( ((unsigned int (__fastcall *)(struct IDataObject *, struct tagFORMATETC *, STGMEDIUM *))a1->lpVtbl->GetData)(
               a1,
               &v69,
               &v76) )
        {
          goto LABEL_57;
        }
        ClipboardData = (Ofc::CStr *)v76.hBitmap;
        if ( !v76.hBitmap )
        {
          p_hMem = &v76;
LABEL_63:
          ReleaseStgMedium(p_hMem);
          goto LABEL_57;
        }
        LOBYTE(a2) = 1;
        goto LABEL_67;
      }
      Art::SafeClipboard::SafeClipboard((Art::SafeClipboard *)&v61);
      if ( v61 )
      {
        RTFFormatInfo = Art::GetRTFFormatInfo(v50);
        ClipboardData = (Ofc::CStr *)GetClipboardData(*((unsigned __int16 *)RTFFormatInfo + 6));
        CloseClipboard();
LABEL_67:
        if ( ClipboardData )
        {
          v75[0] = ClipboardData;
          v52 = (Ofc::CStr *)GlobalLock(ClipboardData);
          v75[1] = v52;
          if ( v52 )
          {
            v53 = -1;
            do
              ++v53;
            while ( *((_BYTE *)v52 + v53) );
          }
          else
          {
            LODWORD(v53) = 0;
          }
          *(_QWORD *)&hMem.tymed = v52;
          hMem.hBitmap = (HBITMAP)(int)v53;
          sub_18061B2C4(a8);
          if ( v52 )
            GlobalUnlock(ClipboardData);
        }
        if ( (_BYTE)a2 )
          ReleaseStgMedium(&v76);
        v54 = ClipboardData == 0;
        goto LABEL_78;
      }
      Ofc::CLastErrorException::ThrowTag(0x1E1820C2u);
    }
    if ( a2 == *((_WORD *)Art::GetUnicodeTextFormatInfo(v47) + 6) )
    {
      memset(&hMem, 0, sizeof(hMem));
      a2 = 0;
      LOBYTE(v18) = 0;
      if ( a1 )
      {
        if ( ((unsigned int (__fastcall *)(struct IDataObject *, struct tagFORMATETC *, STGMEDIUM *))a1->lpVtbl->GetData)(
               a1,
               &v69,
               &hMem) )
        {
          goto LABEL_57;
        }
        v56 = hMem.hBitmap;
        if ( !hMem.hBitmap )
        {
          p_hMem = &hMem;
          goto LABEL_63;
        }
        LOBYTE(v18) = 1;
        goto LABEL_89;
      }
      Art::SafeClipboard::SafeClipboard((Art::SafeClipboard *)&v61);
      if ( v61 )
      {
        UnicodeTextFormatInfo = Art::GetUnicodeTextFormatInfo(v57);
        v56 = GetClipboardData(*((unsigned __int16 *)UnicodeTextFormatInfo + 6));
        CloseClipboard();
LABEL_89:
        if ( v56 )
        {
          v59 = GlobalLock(v56);
          Ofc::CStr::operator=(v75[0], v59);
          Ofc::CStr::Remove(v75[0], 0xAu, 0x7FFF);
          if ( v59 )
            GlobalUnlock(v56);
        }
        if ( (_BYTE)v18 )
          ReleaseStgMedium(&hMem);
        v54 = v56 == 0;
LABEL_78:
        if ( !v54 )
          goto LABEL_48;
        goto LABEL_57;
      }
      Ofc::CLastErrorException::ThrowTag(0x1E1820C1u);
    }
    if ( a2 == *((_WORD *)Art::GetHyperlinkFormatInfo(v55) + 6) )
    {
      if ( *((_QWORD *)*a3 + 2) )
      {
        v65 = 0;
        if ( !a1 )
        {
          v60 = Mso::Clipboard::GetEnterpriseIdOfCurrentClipboardData(v79);
          if ( v65 )
            ((void (__fastcall *)(struct IDataObject *))v65->lpVtbl->Release)(v65);
          v65 = 0;
          if ( !(unsigned int)Mso::Clipboard::OleGetClipboardAndRequestAccessSynchronously(&v65, v60, DesktopWindow, 0)
            && v65 )
          {
            v19 = 0;
          }
          std::wstring::~wstring(v80);
          if ( v19 )
          {
            if ( v65 )
              ((void (__fastcall *)(struct IDataObject *))v65->lpVtbl->Release)(v65);
            goto LABEL_107;
          }
          a1 = v65;
        }
        v32 = Art::FGetTextFromHlink(a3, a1, v18);
        v40 = v65;
        goto LABEL_36;
      }
LABEL_107:
      v32 = 0;
      goto LABEL_108;
    }
LABEL_57:
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v74);
    return 0;
  }
  v66 = 0;
  if ( a1 )
  {
    Art::TxStgMedium::TxStgMedium((Art::TxStgMedium *)v75, a1, &v69);
    if ( v61 )
    {
      LOBYTE(v30) = a5;
      v31 = Art::FGetTextAndBlipAndAltTextListFromHtmlStream(
              (_DWORD)a3,
              (unsigned int)v75,
              v30,
              v71,
              a7,
              (__int64)a8,
              (__int64)v63,
              (__int64)a13,
              (__int64)v64,
              (__int64)v65);
    }
    else
    {
      v31 = Art::FGetTextFromHtmlStream(a3, v75, a8, a13);
    }
    v32 = v31;
    v33 = (STGMEDIUM *)v75;
    goto LABEL_27;
  }
  v68 = (struct IDataObject *)Mso::Clipboard::GetEnterpriseIdOfCurrentClipboardData(v79);
  v66 = 0;
  if ( (unsigned int)Mso::Clipboard::OleGetClipboardAndRequestAccessSynchronously(&v66, v68, DesktopWindow, 0)
    || (v62 = 1, !v66) )
  {
    v62 = 0;
  }
  std::wstring::~wstring(v80);
  if ( !v62 )
  {
    v29 = v66;
    if ( v66 )
      ((void (__fastcall *)(struct IDataObject *))v66->lpVtbl->Release)(v66);
    goto LABEL_32;
  }
  Art::TxStgMedium::TxStgMedium((Art::TxStgMedium *)&v77, v66, &v69);
  if ( v61 )
  {
    LOBYTE(v34) = a5;
    v35 = Art::FGetTextAndBlipAndAltTextListFromHtmlStream(
            (_DWORD)a3,
            (unsigned int)&v77,
            v34,
            v71,
            a7,
            (__int64)a8,
            (__int64)v63,
            (__int64)a13,
            (__int64)v64,
            (__int64)v65);
  }
  else
  {
    v35 = Art::FGetTextFromHtmlStream(a3, &v77, a8, a13);
  }
  v32 = v35;
  v33 = &v77;
LABEL_27:
  Art::TxStgMedium::~TxStgMedium(v33);
  if ( v66 )
  {
    Release = (void (*)(void))v66->lpVtbl->Release;
LABEL_29:
    Release();
  }
LABEL_108:
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v74);
  return v32;
}

```

## disassembly

```asm
0x1805a1f30  mov     [rsp-8+arg_18], rbx
0x1805a1f35  push    rbp
0x1805a1f36  push    rsi
0x1805a1f37  push    rdi
0x1805a1f38  push    r12
0x1805a1f3a  push    r13
0x1805a1f3c  push    r14
0x1805a1f3e  push    r15
0x1805a1f40  lea     rbp, [rsp-0A0h]
0x1805a1f48  sub     rsp, 1A0h
0x1805a1f4f  mov     rax, cs:__security_cookie
0x1805a1f56  xor     rax, rsp
0x1805a1f59  mov     [rbp+0D0h+var_38], rax
0x1805a1f60  mov     [rsp+1D0h+var_180], r9b
0x1805a1f65  mov     rsi, r8
0x1805a1f68  movzx   r12d, dx
0x1805a1f6c  mov     rbx, rcx
0x1805a1f6f  mov     rdi, [rbp+0D0h+arg_50]
0x1805a1f76  mov     [rbp+0D0h+var_F8], rdi
0x1805a1f7a  mov     r14, [rbp+0D0h+arg_38]
0x1805a1f81  mov     rax, [rbp+0D0h+arg_28]
0x1805a1f88  mov     [rbp+0D0h+var_100], rax
0x1805a1f8c  mov     rax, [rbp+0D0h+arg_40]
0x1805a1f93  mov     [rsp+1D0h+var_178], rax
0x1805a1f98  mov     rax, [rbp+0D0h+arg_48]
0x1805a1f9f  mov     [rbp+0D0h+var_F0], rax
0x1805a1fa3  mov     rcx, [rbp+0D0h+arg_58]; this
0x1805a1faa  mov     [rbp+0D0h+var_E0], rcx
0x1805a1fae  mov     r15, [rbp+0D0h+arg_60]
0x1805a1fb5  mov     rax, [rbp+0D0h+arg_68]
0x1805a1fbc  mov     [rsp+1D0h+var_170], rax
0x1805a1fc1  mov     rax, [rbp+0D0h+arg_70]
0x1805a1fc8  mov     [rsp+1D0h+var_168], rax
0x1805a1fcd  xor     eax, eax
0x1805a1fcf  test    r15, r15
0x1805a1fd2  jz      short loc_1805A1FD7
0x1805a1fd4  mov     [r15], al
0x1805a1fd7  call    ?Reset@CVarStr@Ofc@@QEAAXXZ; Ofc::CVarStr::Reset(void)
0x1805a1fdc  mov     rcx, [r14]; this
0x1805a1fdf  call    ?StrongRelease@CProxyPtrImpl@Ofc@@IEAAXXZ; Ofc::CProxyPtrImpl::StrongRelease(void)
0x1805a1fe4  lea     r13, ?s_proxyPtrSentinel@?1??GetSentinel@CProxyPtrImpl@Ofc@@KAAEBQEAV23@XZ@4UProxyPtrSentinel@?1??123@KAAEBQEAV23@XZ@B; `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::ProxyPtrSentinel const `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::s_proxyPtrSentinel
0x1805a1feb  mov     [r14], r13
0x1805a1fee  mov     rcx, [rdi]; this
0x1805a1ff1  call    ?StrongRelease@CProxyPtrImpl@Ofc@@IEAAXXZ; Ofc::CProxyPtrImpl::StrongRelease(void)
0x1805a1ff6  mov     [rdi], r13
0x1805a1ff9  xor     r8d, r8d
0x1805a1ffc  mov     dword ptr [rbp+0D0h+var_128+2], r8d
0x1805a2000  mov     word ptr [rbp+0D0h+var_128+6], r8w
0x1805a2005  mov     qword ptr [rbp+0D0h+var_128.tymed], 1
0x1805a200d  mov     [rbp+0D0h+var_128.cfFormat], r12w
0x1805a2012  mov     [rbp+0D0h+var_128.ptd], r8
0x1805a2016  lea     edi, [r8+1]
0x1805a201a  mov     [rbp+0D0h+var_128.dwAspect], edi
0x1805a201d  mov     [rbp+0D0h+var_128.lindex], 0FFFFFFFFh
0x1805a2024  mov     r13d, r8d
0x1805a2027  mov     rcx, [rsi]; struct Ofc::CProxyPtrImpl *
0x1805a202a  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x1805a202f  mov     [rbp+0D0h+var_E8], rax
0x1805a2033  cmp     [rax+10h], r8
0x1805a2037  jz      loc_1805A20E1
0x1805a203d  lea     rcx, ??_7HostParentWindowInfo@Art@@6B@; const Art::HostParentWindowInfo::`vftable'
0x1805a2044  mov     [rbp+0D0h+hMem], rcx
0x1805a2048  mov     [rbp+0D0h+hMem+8], r8
0x1805a204c  mov     rcx, rax; this
0x1805a204f  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1805a2054  mov     rcx, rax
0x1805a2057  mov     rax, [rax]
0x1805a205a  lea     rdx, [rbp+0D0h+hMem]
0x1805a205e  mov     rax, [rax+0A0h]
0x1805a2065  call    cs:__guard_dispatch_icall_fptr
0x1805a206b  test    al, al
0x1805a206d  jz      short loc_1805A20BE
0x1805a206f  mov     rcx, [rbp+0D0h+hMem+8]
0x1805a2073  test    rcx, rcx
0x1805a2076  jz      short loc_1805A20BE
0x1805a2078  lea     rdx, [rbp+0D0h+var_108]
0x1805a207c  call    ??$QueryObjectElseCrash@UIHWNDCanvas@PlatformCanvas@Mso@@$0A@@IObjectProxy@Mso@@QEAA?AV?$TCntPtr@UIHWNDCanvas@PlatformCanvas@Mso@@@1@XZ; Mso::IObjectProxy::QueryObjectElseCrash<Mso::PlatformCanvas::IHWNDCanvas,0>(void)
0x1805a2081  mov     rcx, rax
0x1805a2084  call    ??C?$TCntPtr@VAppAugmentationStatefulRuntime@AugLoop@Art@@@Mso@@QEBAPEAVAppAugmentationStatefulRuntime@AugLoop@Art@@XZ; Mso::TCntPtr<Art::AugLoop::AppAugmentationStatefulRuntime>::operator->(void)
0x1805a2089  mov     rcx, rax
0x1805a208c  mov     rax, [rax]
0x1805a208f  mov     rax, [rax+28h]
0x1805a2093  call    cs:__guard_dispatch_icall_fptr
0x1805a2099  mov     r13, rax
0x1805a209c  mov     rdx, [rbp+0D0h+var_108]
0x1805a20a0  test    rdx, rdx
0x1805a20a3  jz      short loc_1805A20BE
0x1805a20a5  mov     [rbp+0D0h+var_108], 0
0x1805a20ad  mov     rcx, [rdx]
0x1805a20b0  mov     rax, [rcx+8]
0x1805a20b4  mov     rcx, rdx
0x1805a20b7  call    cs:__guard_dispatch_icall_fptr
0x1805a20bd  nop
0x1805a20be  mov     rcx, [rbp+0D0h+hMem+8]
0x1805a20c2  test    rcx, rcx
0x1805a20c5  jz      short loc_1805A20DC
0x1805a20c7  mov     [rbp+0D0h+hMem+8], 0
0x1805a20cf  mov     rax, [rcx]
0x1805a20d2  mov     rax, [rax+8]
0x1805a20d6  call    cs:__guard_dispatch_icall_fptr
0x1805a20dc  test    r13, r13
0x1805a20df  jnz     short loc_1805A210A
0x1805a20e1  call    cs:__imp_?GetPolicyProtectionManagerFactory@EnterpriseDataProtection@Mso@@YAAEAUIPolicyProtectionManager@12@XZ; Mso::EnterpriseDataProtection::GetPolicyProtectionManagerFactory(void)
0x1805a20e7  mov     rdx, rax
0x1805a20ea  mov     rcx, [rax]
0x1805a20ed  mov     rax, [rcx]
0x1805a20f0  mov     rcx, rdx
0x1805a20f3  call    cs:__guard_dispatch_icall_fptr
0x1805a20f9  test    al, al
0x1805a20fb  jnz     loc_1805A24E1
0x1805a2101  call    cs:__imp_GetDesktopWindow
0x1805a2107  mov     r13, rax
0x1805a210a  call    ?GetHTMLFormatInfo@Art@@YAAEBVFormatInfo@1@XZ; Art::GetHTMLFormatInfo(void)
0x1805a210f  cmp     r12w, [rax+0Ch]
0x1805a2114  jnz     loc_1805A22C5
0x1805a211a  mov     [rsp+1D0h+var_160], 0
0x1805a2123  test    rbx, rbx
0x1805a2126  jz      short loc_1805A21A2
0x1805a2128  lea     r8, [rbp+0D0h+var_128]; struct tagFORMATETC *
0x1805a212c  mov     rdx, rbx; struct IDataObject *
0x1805a212f  lea     rcx, [rbp+0D0h+var_E0]; this
0x1805a2133  call    ??0TxStgMedium@Art@@QEAA@AEAUIDataObject@@AEBUtagFORMATETC@@@Z; Art::TxStgMedium::TxStgMedium(IDataObject &,tagFORMATETC const &)
0x1805a2138  lea     rdx, [rbp+0D0h+var_E0]
0x1805a213c  mov     rcx, rsi
0x1805a213f  cmp     [rsp+1D0h+var_180], 0
0x1805a2144  jz      short loc_1805A218C
0x1805a2146  mov     rax, [rsp+1D0h+var_168]
0x1805a214b  mov     [rsp+1D0h+var_188], rax
0x1805a2150  mov     rax, [rsp+1D0h+var_170]
0x1805a2155  mov     [rsp+1D0h+var_190], rax
0x1805a215a  mov     [rsp+1D0h+var_198], r15
0x1805a215f  mov     rax, [rsp+1D0h+var_178]
0x1805a2164  mov     [rsp+1D0h+var_1A0], rax
0x1805a2169  mov     [rsp+1D0h+var_1A8], r14
0x1805a216e  mov     rax, [rbp+0D0h+arg_30]
0x1805a2175  mov     [rsp+1D0h+var_1B0], rax
0x1805a217a  mov     r9, [rbp+0D0h+var_100]
0x1805a217e  mov     r8b, [rbp+0D0h+arg_20]
0x1805a2185  call    ?FGetTextAndBlipAndAltTextListFromHtmlStream@Art@@YA_NAEBV?$TWeakPtr@VDocumentContext@Art@@@Ofc@@AEAVTxStgMedium@1@_NPEAUIMsoHTMLFileReferenceResolver@@PEAUIMetroProgress@@AEAV?$TOwningPtr@VTextBody@Art@@@3@AEAV?$TOwnerPtrList@VBlipAndAltText@Art@@@3@PEA_N77@Z; Art::FGetTextAndBlipAndAltTextListFromHtmlStream(Ofc::TWeakPtr<Art::DocumentContext> const &,Art::TxStgMedium &,bool,IMsoHTMLFileReferenceResolver *,IMetroProgress *,Ofc::TOwningPtr<Art::TextBody> &,Ofc::TOwnerPtrList<Art::BlipAndAltText> &,bool *,bool *,bool *)
0x1805a218a  jmp     short loc_1805A2197
0x1805a218c  mov     r9, r15
0x1805a218f  mov     r8, r14
0x1805a2192  call    ?FGetTextFromHtmlStream@Art@@YA_NAEBV?$TWeakPtr@VDocumentContext@Art@@@Ofc@@AEAVTxStgMedium@1@AEAV?$TOwningPtr@VTextBody@Art@@@3@PEA_N@Z; Art::FGetTextFromHtmlStream(Ofc::TWeakPtr<Art::DocumentContext> const &,Art::TxStgMedium &,Ofc::TOwningPtr<Art::TextBody> &,bool *)
0x1805a2197  mov     bl, al
0x1805a2199  lea     rcx, [rbp+0D0h+var_E0]
0x1805a219d  jmp     loc_1805A2289
0x1805a21a2  lea     rcx, [rbp+0D0h+var_68]
0x1805a21a6  call    cs:__imp_?GetEnterpriseIdOfCurrentClipboardData@Clipboard@Mso@@YA?AVEnterpriseIdentity@EnterpriseDataProtection@2@XZ; Mso::Clipboard::GetEnterpriseIdOfCurrentClipboardData(void)
0x1805a21ac  mov     [rbp+0D0h+var_130], rax
0x1805a21b0  mov     rcx, [rsp+1D0h+var_160]
0x1805a21b5  test    rcx, rcx
0x1805a21b8  jz      short loc_1805A21CB
0x1805a21ba  mov     rdx, [rcx]
0x1805a21bd  mov     rax, [rdx+10h]
0x1805a21c1  call    cs:__guard_dispatch_icall_fptr
0x1805a21c7  mov     rax, [rbp+0D0h+var_130]
0x1805a21cb  mov     [rsp+1D0h+var_160], 0
0x1805a21d4  xor     r9d, r9d
0x1805a21d7  mov     r8, r13
0x1805a21da  mov     rdx, rax
0x1805a21dd  lea     rcx, [rsp+1D0h+var_160]
0x1805a21e2  call    cs:__imp_?OleGetClipboardAndRequestAccessSynchronously@Clipboard@Mso@@YAJPEAPEAUIDataObject@@AEBVEnterpriseIdentity@EnterpriseDataProtection@2@PEAUHWND__@@W4EDPOverride@12@@Z; Mso::Clipboard::OleGetClipboardAndRequestAccessSynchronously(IDataObject * *,Mso::EnterpriseDataProtection::EnterpriseIdentity const &,HWND__ *,Mso::Clipboard::EDPOverride)
0x1805a21e8  test    eax, eax
0x1805a21ea  jnz     short loc_1805A21F9
0x1805a21ec  cmp     [rsp+1D0h+var_160], 0
0x1805a21f2  mov     [rsp+1D0h+var_17F], dil
0x1805a21f7  jnz     short loc_1805A21FE
0x1805a21f9  mov     [rsp+1D0h+var_17F], 0
0x1805a21fe  lea     rcx, [rbp+0D0h+var_60]
0x1805a2202  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1805a2207  cmp     [rsp+1D0h+var_17F], 0
0x1805a220c  jz      loc_1805A22AE
0x1805a2212  lea     r8, [rbp+0D0h+var_128]; struct tagFORMATETC *
0x1805a2216  mov     rdx, [rsp+1D0h+var_160]; struct IDataObject *
0x1805a221b  lea     rcx, [rbp+0D0h+var_A8]; this
0x1805a221f  call    ??0TxStgMedium@Art@@QEAA@AEAUIDataObject@@AEBUtagFORMATETC@@@Z; Art::TxStgMedium::TxStgMedium(IDataObject &,tagFORMATETC const &)
0x1805a2224  lea     rdx, [rbp+0D0h+var_A8]
0x1805a2228  mov     rcx, rsi
0x1805a222b  cmp     [rsp+1D0h+var_180], 0
0x1805a2230  jz      short loc_1805A2278
0x1805a2232  mov     rax, [rsp+1D0h+var_168]
0x1805a2237  mov     [rsp+1D0h+var_188], rax
0x1805a223c  mov     rax, [rsp+1D0h+var_170]
0x1805a2241  mov     [rsp+1D0h+var_190], rax
0x1805a2246  mov     [rsp+1D0h+var_198], r15
0x1805a224b  mov     rax, [rsp+1D0h+var_178]
0x1805a2250  mov     [rsp+1D0h+var_1A0], rax
0x1805a2255  mov     [rsp+1D0h+var_1A8], r14
0x1805a225a  mov     rax, [rbp+0D0h+arg_30]
0x1805a2261  mov     [rsp+1D0h+var_1B0], rax
0x1805a2266  mov     r9, [rbp+0D0h+var_100]
0x1805a226a  mov     r8b, [rbp+0D0h+arg_20]
0x1805a2271  call    ?FGetTextAndBlipAndAltTextListFromHtmlStream@Art@@YA_NAEBV?$TWeakPtr@VDocumentContext@Art@@@Ofc@@AEAVTxStgMedium@1@_NPEAUIMsoHTMLFileReferenceResolver@@PEAUIMetroProgress@@AEAV?$TOwningPtr@VTextBody@Art@@@3@AEAV?$TOwnerPtrList@VBlipAndAltText@Art@@@3@PEA_N77@Z; Art::FGetTextAndBlipAndAltTextListFromHtmlStream(Ofc::TWeakPtr<Art::DocumentContext> const &,Art::TxStgMedium &,bool,IMsoHTMLFileReferenceResolver *,IMetroProgress *,Ofc::TOwningPtr<Art::TextBody> &,Ofc::TOwnerPtrList<Art::BlipAndAltText> &,bool *,bool *,bool *)
0x1805a2276  jmp     short loc_1805A2283
0x1805a2278  mov     r9, r15
0x1805a227b  mov     r8, r14
0x1805a227e  call    ?FGetTextFromHtmlStream@Art@@YA_NAEBV?$TWeakPtr@VDocumentContext@Art@@@Ofc@@AEAVTxStgMedium@1@AEAV?$TOwningPtr@VTextBody@Art@@@3@PEA_N@Z; Art::FGetTextFromHtmlStream(Ofc::TWeakPtr<Art::DocumentContext> const &,Art::TxStgMedium &,Ofc::TOwningPtr<Art::TextBody> &,bool *)
0x1805a2283  mov     bl, al
0x1805a2285  lea     rcx, [rbp+0D0h+var_A8]; this
0x1805a2289  call    ??1TxStgMedium@Art@@QEAA@XZ; Art::TxStgMedium::~TxStgMedium(void)
0x1805a228e  mov     rcx, [rsp+1D0h+var_160]
0x1805a2293  test    rcx, rcx
0x1805a2296  jz      loc_1805A27B4
0x1805a229c  mov     rax, [rcx]
0x1805a229f  mov     rax, [rax+10h]
0x1805a22a3  call    cs:__guard_dispatch_icall_fptr
0x1805a22a9  jmp     loc_1805A27B4
0x1805a22ae  mov     rcx, [rsp+1D0h+var_160]
0x1805a22b3  test    rcx, rcx
0x1805a22b6  jz      short loc_1805A22C5
0x1805a22b8  mov     rax, [rcx]
0x1805a22bb  mov     rax, [rax+10h]
0x1805a22bf  call    cs:__guard_dispatch_icall_fptr
0x1805a22c5  call    ?GetMathMLFormatInfo@Art@@YAAEBVFormatInfo@1@XZ; Art::GetMathMLFormatInfo(void)
0x1805a22ca  cmp     r12w, [rax+0Ch]
0x1805a22cf  jnz     loc_1805A23BA
0x1805a22d5  xor     esi, esi
0x1805a22d7  mov     [rsp+1D0h+var_178], rsi
0x1805a22dc  test    rbx, rbx
0x1805a22df  jz      short loc_1805A2322
0x1805a22e1  lea     r8, [rbp+0D0h+var_128]; struct tagFORMATETC *
0x1805a22e5  mov     rdx, rbx; struct IDataObject *
0x1805a22e8  lea     rcx, [rbp+0D0h+var_88]; this
0x1805a22ec  call    ??0TxStgMedium@Art@@QEAA@AEAUIDataObject@@AEBUtagFORMATETC@@@Z; Art::TxStgMedium::TxStgMedium(IDataObject &,tagFORMATETC const &)
0x1805a22f1  mov     r9, r15
0x1805a22f4  mov     r8, r14
0x1805a22f7  lea     rdx, [rbp+0D0h+var_88]
0x1805a22fb  call    ?FGetTextFromMathMLStream@Art@@YA_NAEBV?$TWeakPtr@VDocumentContext@Art@@@Ofc@@AEAVTxStgMedium@1@AEAV?$TOwningPtr@VTextBody@Art@@@3@PEA_N@Z; Art::FGetTextFromMathMLStream(Ofc::TWeakPtr<Art::DocumentContext> const &,Art::TxStgMedium &,Ofc::TOwningPtr<Art::TextBody> &,bool *)
0x1805a2300  mov     bl, al
0x1805a2302  lea     rcx, [rbp+0D0h+var_88]; this
0x1805a2306  call    ??1TxStgMedium@Art@@QEAA@XZ; Art::TxStgMedium::~TxStgMedium(void)
0x1805a230b  mov     rcx, [rsp+1D0h+var_178]
0x1805a2310  test    rcx, rcx
0x1805a2313  jz      loc_1805A27B4
0x1805a2319  mov     rdx, [rcx]
0x1805a231c  mov     rax, [rdx+10h]
0x1805a2320  jmp     short loc_1805A22A3
0x1805a2322  lea     rcx, [rbp+0D0h+var_68]
0x1805a2326  call    cs:__imp_?GetEnterpriseIdOfCurrentClipboardData@Clipboard@Mso@@YA?AVEnterpriseIdentity@EnterpriseDataProtection@2@XZ; Mso::Clipboard::GetEnterpriseIdOfCurrentClipboardData(void)
0x1805a232c  mov     rbx, rax
0x1805a232f  mov     rcx, [rsp+1D0h+var_178]
0x1805a2334  test    rcx, rcx
0x1805a2337  jz      short loc_1805A2346
0x1805a2339  mov     rdx, [rcx]
0x1805a233c  mov     rax, [rdx+10h]
0x1805a2340  call    cs:__guard_dispatch_icall_fptr
0x1805a2346  mov     [rsp+1D0h+var_178], rsi
0x1805a234b  xor     r9d, r9d
0x1805a234e  mov     r8, r13
0x1805a2351  mov     rdx, rbx
0x1805a2354  lea     rcx, [rsp+1D0h+var_178]
0x1805a2359  call    cs:__imp_?OleGetClipboardAndRequestAccessSynchronously@Clipboard@Mso@@YAJPEAPEAUIDataObject@@AEBVEnterpriseIdentity@EnterpriseDataProtection@2@PEAUHWND__@@W4EDPOverride@12@@Z; Mso::Clipboard::OleGetClipboardAndRequestAccessSynchronously(IDataObject * *,Mso::EnterpriseDataProtection::EnterpriseIdentity const &,HWND__ *,Mso::Clipboard::EDPOverride)
0x1805a235f  test    eax, eax
0x1805a2361  jnz     short loc_1805A236A
0x1805a2363  cmp     [rsp+1D0h+var_178], rsi
0x1805a2368  jnz     short loc_1805A236D
0x1805a236a  mov     dil, sil
0x1805a236d  lea     rcx, [rbp+0D0h+var_60]
0x1805a2371  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1805a2376  test    dil, dil
0x1805a2379  jz      short loc_1805A23B0
0x1805a237b  lea     r8, [rbp+0D0h+var_128]; struct tagFORMATETC *
0x1805a237f  mov     rdx, [rsp+1D0h+var_178]; struct IDataObject *
0x1805a2384  lea     rcx, [rbp+0D0h+var_68]; this
0x1805a2388  call    ??0TxStgMedium@Art@@QEAA@AEAUIDataObject@@AEBUtagFORMATETC@@@Z; Art::TxStgMedium::TxStgMedium(IDataObject &,tagFORMATETC const &)
0x1805a238d  mov     r9, r15
0x1805a2390  mov     r8, r14
0x1805a2393  lea     rdx, [rbp+0D0h+var_68]
0x1805a2397  nop     word ptr [rax+rax+00000000h]
0x1805a23a0  call    ?FGetTextFromMathMLStream@Art@@YA_NAEBV?$TWeakPtr@VDocumentContext@Art@@@Ofc@@AEAVTxStgMedium@1@AEAV?$TOwningPtr@VTextBody@Art@@@3@PEA_N@Z; Art::FGetTextFromMathMLStream(Ofc::TWeakPtr<Art::DocumentContext> const &,Art::TxStgMedium &,Ofc::TOwningPtr<Art::TextBody> &,bool *)
0x1805a23a5  mov     bl, al
0x1805a23a7  lea     rcx, [rbp+0D0h+var_68]
0x1805a23ab  jmp     loc_1805A2306
0x1805a23b0  mov     rcx, [rsp+1D0h+var_178]
0x1805a23b5  jmp     loc_1805A24CE
0x1805a23ba  call    ?GetNativeTextFormatInfo@Art@@YAAEBVFormatInfo@1@XZ; Art::GetNativeTextFormatInfo(void)
0x1805a23bf  cmp     r12w, [rax+0Ch]
0x1805a23c4  jnz     loc_1805A2516
0x1805a23ca  mov     rax, [rsi]
0x1805a23cd  xor     r15d, r15d
0x1805a23d0  cmp     [rax+10h], r15
0x1805a23d4  jz      loc_1805A27B1
0x1805a23da  mov     [rsp+1D0h+var_170], r15
0x1805a23df  test    rbx, rbx
0x1805a23e2  jz      short loc_1805A2447
0x1805a23e4  mov     [rbp+0D0h+var_130], rbx
0x1805a23e8  mov     rax, [rbx]
0x1805a23eb  mov     rcx, rbx
0x1805a23ee  mov     rax, [rax+8]
0x1805a23f2  call    cs:__guard_dispatch_icall_fptr
0x1805a23f8  mov     rax, [rbp+0D0h+var_F8]
0x1805a23fc  mov     [rsp+1D0h+var_1B0], rax
0x1805a2401  mov     r9, [rbp+0D0h+var_F0]
0x1805a2405  mov     r8, r14
0x1805a2408  mov     rdx, rsi
0x1805a240b  lea     rcx, [rbp+0D0h+var_130]
0x1805a240f  nop
0x1805a2410  call    ?FGetTextFromGvmlStream@Art@@YA_NAEBV?$TCntPtr@UIDataObject@@@Ofc@@AEBV?$TWeakPtr@VDocumentContext@Art@@@3@AEAV?$TOwningPtr@VTextBody@Art@@@3@AEAVTextAutofit@1@AEAV?$TOwningPtr@VClipboardTextResolver@Art@@@3@@Z; Art::FGetTextFromGvmlStream(Ofc::TCntPtr<IDataObject> const &,Ofc::TWeakPtr<Art::DocumentContext> const &,Ofc::TOwningPtr<Art::TextBody> &,Art::TextAutofit &,Ofc::TOwningPtr<Art::ClipboardTextResolver> &)
0x1805a2415  mov     dil, al
0x1805a2418  mov     rcx, [rbx]
  ... truncated ...
```
