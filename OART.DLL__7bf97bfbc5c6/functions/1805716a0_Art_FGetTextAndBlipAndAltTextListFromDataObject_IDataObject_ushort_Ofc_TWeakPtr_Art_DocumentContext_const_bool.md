# Art::FGetTextAndBlipAndAltTextListFromDataObject(IDataObject *,ushort,Ofc::TWeakPtr<Art::DocumentContext> const &,bool,bool,IMsoHTMLFileReferenceResolver *,IMetroProgress *,Ofc::TOwningPtr<Art::TextBody> &,Ofc::TOwnerPtrList<Art::BlipAndAltText> &,Art::TextAutofit &,Ofc::TOwningPtr<Art::ClipboardTextResolver> &,Ofc::CVarStr &,bool *,bool *,bool *)

- ea: `0x1805716a0`
- end: `0x180571f54`
- name: `?FGetTextAndBlipAndAltTextListFromDataObject@Art@@YA_NPEAUIDataObject@@GAEBV?$TWeakPtr@VDocumentContext@Art@@@Ofc@@_N2PEAUIMsoHTMLFileReferenceResolver@@PEAUIMetroProgress@@AEAV?$TOwningPtr@VTextBody@Art@@@4@AEAV?$TOwnerPtrList@VBlipAndAltText@Art@@@4@AEAVTextAutofit@1@AEAV?$TOwningPtr@VClipboardTextResolver@Art@@@4@AEAVCVarStr@4@PEA_NPEA_NPEA_N@Z`
- size: `2228`
- prototype: `__int64 __usercall@<rax>(struct IDataObject *@<rcx>, char, __int64, __int64, struct Ofc::CProxyPtrImpl **, __int64, __int64, __int64, Ofc::CVarStr *, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `29`
- tags: `file_ops, registry_config`

## callers

- `0x180571600`
- `0x18096f870`
- `0x18096ffe0`

## callees

- `0x18001df54`
- `0x180038460`
- `0x18006d020`
- `0x180070fe0`
- `0x180071720`
- `0x1801095e0`
- `0x18012737c`
- `0x180338e70`
- `0x180338ee0`
- `0x180338f50`
- `0x180339100`
- `0x1803866f0`
- `0x1803f6d7c`
- `0x18043e06c`
- `0x180463a60`
- `0x18049fd7c`
- `0x180550380`
- `0x1805716a0`
- `0x180577090`
- `0x18057e430`
- `0x1806418d4`
- `0x1806a5084`
- `0x1806a51d0`
- `0x1806a57c4`
- `0x1806bd54c`
- `0x180975f9c`
- `0x1809760b4`
- `0x1809764a0`
- `0x180a1b6bc`

## import_xrefs

- `KERNEL32!GlobalLock` at `0x180571d20`
- `KERNEL32!GlobalLock` at `0x180571e2b`
- `KERNEL32!GlobalLock` at `0x180571d20`
- `KERNEL32!GlobalLock` at `0x180571e2b`
- `KERNEL32!GlobalUnlock` at `0x180571d6a`
- `KERNEL32!GlobalUnlock` at `0x180571e5c`
- `KERNEL32!GlobalUnlock` at `0x180571d6a`
- `KERNEL32!GlobalUnlock` at `0x180571e5c`
- `Mso30Win32Client!__imp_?GetPolicyProtectionManagerFactory@EnterpriseDataProtection@Mso@@YAAEAUIPolicyProtectionManager@12@XZ` at `0x180571851`
- `Mso30Win32Client!__imp_?GetPolicyProtectionManagerFactory@EnterpriseDataProtection@Mso@@YAAEAUIPolicyProtectionManager@12@XZ` at `0x180571851`
- `Mso30Win32Client!__imp_?GetEnterpriseIdOfCurrentClipboardData@Clipboard@Mso@@YA?AVEnterpriseIdentity@EnterpriseDataProtection@2@XZ` at `0x180571916`
- `Mso30Win32Client!__imp_?GetEnterpriseIdOfCurrentClipboardData@Clipboard@Mso@@YA?AVEnterpriseIdentity@EnterpriseDataProtection@2@XZ` at `0x180571a96`
- `Mso30Win32Client!__imp_?GetEnterpriseIdOfCurrentClipboardData@Clipboard@Mso@@YA?AVEnterpriseIdentity@EnterpriseDataProtection@2@XZ` at `0x180571bbb`
- `Mso30Win32Client!__imp_?GetEnterpriseIdOfCurrentClipboardData@Clipboard@Mso@@YA?AVEnterpriseIdentity@EnterpriseDataProtection@2@XZ` at `0x180571eb5`
- `Mso30Win32Client!__imp_?GetEnterpriseIdOfCurrentClipboardData@Clipboard@Mso@@YA?AVEnterpriseIdentity@EnterpriseDataProtection@2@XZ` at `0x180571916`
- `Mso30Win32Client!__imp_?GetEnterpriseIdOfCurrentClipboardData@Clipboard@Mso@@YA?AVEnterpriseIdentity@EnterpriseDataProtection@2@XZ` at `0x180571a96`
- `Mso30Win32Client!__imp_?GetEnterpriseIdOfCurrentClipboardData@Clipboard@Mso@@YA?AVEnterpriseIdentity@EnterpriseDataProtection@2@XZ` at `0x180571bbb`
- `Mso30Win32Client!__imp_?GetEnterpriseIdOfCurrentClipboardData@Clipboard@Mso@@YA?AVEnterpriseIdentity@EnterpriseDataProtection@2@XZ` at `0x180571eb5`
- `Mso30Win32Client!__imp_?OleGetClipboardAndRequestAccessSynchronously@Clipboard@Mso@@YAJPEAPEAUIDataObject@@AEBVEnterpriseIdentity@EnterpriseDataProtection@2@PEAUHWND__@@W4EDPOverride@12@@Z` at `0x180571952`
- `Mso30Win32Client!__imp_?OleGetClipboardAndRequestAccessSynchronously@Clipboard@Mso@@YAJPEAPEAUIDataObject@@AEBVEnterpriseIdentity@EnterpriseDataProtection@2@PEAUHWND__@@W4EDPOverride@12@@Z` at `0x180571ac9`
- `Mso30Win32Client!__imp_?OleGetClipboardAndRequestAccessSynchronously@Clipboard@Mso@@YAJPEAPEAUIDataObject@@AEBVEnterpriseIdentity@EnterpriseDataProtection@2@PEAUHWND__@@W4EDPOverride@12@@Z` at `0x180571bee`
- `Mso30Win32Client!__imp_?OleGetClipboardAndRequestAccessSynchronously@Clipboard@Mso@@YAJPEAPEAUIDataObject@@AEBVEnterpriseIdentity@EnterpriseDataProtection@2@PEAUHWND__@@W4EDPOverride@12@@Z` at `0x180571ee8`
- `Mso30Win32Client!__imp_?OleGetClipboardAndRequestAccessSynchronously@Clipboard@Mso@@YAJPEAPEAUIDataObject@@AEBVEnterpriseIdentity@EnterpriseDataProtection@2@PEAUHWND__@@W4EDPOverride@12@@Z` at `0x180571952`
- `Mso30Win32Client!__imp_?OleGetClipboardAndRequestAccessSynchronously@Clipboard@Mso@@YAJPEAPEAUIDataObject@@AEBVEnterpriseIdentity@EnterpriseDataProtection@2@PEAUHWND__@@W4EDPOverride@12@@Z` at `0x180571ac9`
- `Mso30Win32Client!__imp_?OleGetClipboardAndRequestAccessSynchronously@Clipboard@Mso@@YAJPEAPEAUIDataObject@@AEBVEnterpriseIdentity@EnterpriseDataProtection@2@PEAUHWND__@@W4EDPOverride@12@@Z` at `0x180571bee`
- `Mso30Win32Client!__imp_?OleGetClipboardAndRequestAccessSynchronously@Clipboard@Mso@@YAJPEAPEAUIDataObject@@AEBVEnterpriseIdentity@EnterpriseDataProtection@2@PEAUHWND__@@W4EDPOverride@12@@Z` at `0x180571ee8`
- `USER32!GetDesktopWindow` at `0x180571871`
- `USER32!GetDesktopWindow` at `0x180571871`
- `USER32!CloseClipboard` at `0x180571d0e`
- `USER32!CloseClipboard` at `0x180571e1d`
- `USER32!CloseClipboard` at `0x180571d0e`
- `USER32!CloseClipboard` at `0x180571e1d`
- `USER32!GetClipboardData` at `0x180571d05`
- `USER32!GetClipboardData` at `0x180571e14`
- `USER32!GetClipboardData` at `0x180571d05`
- `USER32!GetClipboardData` at `0x180571e14`
- `ole32!ReleaseStgMedium` at `0x180571cd7`
- `ole32!ReleaseStgMedium` at `0x180571d79`
- `ole32!ReleaseStgMedium` at `0x180571e6b`
- `ole32!ReleaseStgMedium` at `0x180571cd7`
- `ole32!ReleaseStgMedium` at `0x180571d79`
- `ole32!ReleaseStgMedium` at `0x180571e6b`

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
        struct Ofc::CProxyPtrImpl **a8,
        struct IDataObject *a9,
        __int64 a10,
        struct Art::ClipboardStyleSheet *a11,
        Ofc::CVarStr *a12,
        _BYTE *a13,
        __int64 a14,
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
  int v64[2]; // [rsp+60h] [rbp-A0h] BYREF
  struct IDataObject *v65; // [rsp+68h] [rbp-98h] BYREF
  struct IDataObject *v66; // [rsp+70h] [rbp-90h] BYREF
  STGMEDIUM hMem; // [rsp+80h] [rbp-80h] BYREF
  int v68[2]; // [rsp+A0h] [rbp-60h] BYREF
  struct tagFORMATETC v69; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v70; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v71; // [rsp+D0h] [rbp-30h]
  struct Art::ClipboardStyleSheet *v72; // [rsp+D8h] [rbp-28h]
  int v73[2]; // [rsp+E0h] [rbp-20h]
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
  *(_QWORD *)v73 = a10;
  v75[0] = a12;
  *(_QWORD *)v64 = a14;
  v65 = a15;
  if ( a13 )
    *a13 = 0;
  Ofc::CVarStr::Reset(a12);
  Ofc::CProxyPtrImpl::StrongRelease(*a8);
  *a8 = (struct Ofc::CProxyPtrImpl *)&`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_proxyPtrSentinel;
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
        *(_QWORD *)v64 = 0;
        if ( !a1 )
        {
          v45 = Mso::Clipboard::GetEnterpriseIdOfCurrentClipboardData(v79);
          *(_QWORD *)v64 = 0;
          if ( (unsigned int)Mso::Clipboard::OleGetClipboardAndRequestAccessSynchronously(v64, v45, DesktopWindow, 0)
            || !*(_QWORD *)v64 )
          {
            v19 = 0;
          }
          std::wstring::~wstring(v80);
          if ( v19 )
          {
            v32 = Art::FGetTextFromGvmlStream((int)v64, (int)a3, (int)a8, v73[0], v72);
            v40 = *(struct IDataObject **)v64;
            goto LABEL_36;
          }
          v43 = *(struct IDataObject **)v64;
LABEL_55:
          if ( v43 )
            ((void (__fastcall *)(struct IDataObject *))v43->lpVtbl->Release)(v43);
          goto LABEL_57;
        }
        *(_QWORD *)v68 = a1;
        ((void (__fastcall *)(struct IDataObject *))a1->lpVtbl->AddRef)(a1);
        v19 = Art::FGetTextFromGvmlStream((int)v68, (int)a3, (int)a8, v73[0], v72);
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
          sub_18043E06C(a8);
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
              *(__int64 *)v64,
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
  *(_QWORD *)v68 = Mso::Clipboard::GetEnterpriseIdOfCurrentClipboardData(v79);
  v66 = 0;
  if ( (unsigned int)Mso::Clipboard::OleGetClipboardAndRequestAccessSynchronously(
                       &v66,
                       *(_QWORD *)v68,
                       DesktopWindow,
                       0)
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
            *(__int64 *)v64,
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
0x1805716a0  mov     [rsp-8+arg_18], rbx
0x1805716a5  push    rbp
0x1805716a6  push    rsi
0x1805716a7  push    rdi
0x1805716a8  push    r12
0x1805716aa  push    r13
0x1805716ac  push    r14
0x1805716ae  push    r15
0x1805716b0  lea     rbp, [rsp-0A0h]
0x1805716b8  sub     rsp, 1A0h
0x1805716bf  mov     rax, cs:__security_cookie
0x1805716c6  xor     rax, rsp
0x1805716c9  mov     [rbp+0D0h+var_38], rax
0x1805716d0  mov     [rsp+1D0h+var_180], r9b
0x1805716d5  mov     rsi, r8
0x1805716d8  movzx   r12d, dx
0x1805716dc  mov     rbx, rcx
0x1805716df  mov     rdi, [rbp+0D0h+arg_50]
0x1805716e6  mov     [rbp+0D0h+var_F8], rdi
0x1805716ea  mov     r14, [rbp+0D0h+arg_38]
0x1805716f1  mov     rax, [rbp+0D0h+arg_28]
0x1805716f8  mov     [rbp+0D0h+var_100], rax
0x1805716fc  mov     rax, [rbp+0D0h+arg_40]
0x180571703  mov     [rsp+1D0h+var_178], rax
0x180571708  mov     rax, [rbp+0D0h+arg_48]
0x18057170f  mov     qword ptr [rbp+0D0h+var_F0], rax
0x180571713  mov     rcx, [rbp+0D0h+arg_58]; this
0x18057171a  mov     [rbp+0D0h+var_E0], rcx
0x18057171e  mov     r15, [rbp+0D0h+arg_60]
0x180571725  mov     rax, [rbp+0D0h+arg_68]
0x18057172c  mov     qword ptr [rsp+1D0h+var_170], rax
0x180571731  mov     rax, [rbp+0D0h+arg_70]
0x180571738  mov     [rsp+1D0h+var_168], rax
0x18057173d  xor     eax, eax
0x18057173f  test    r15, r15
0x180571742  jz      short loc_180571747
0x180571744  mov     [r15], al
0x180571747  call    ?Reset@CVarStr@Ofc@@QEAAXXZ; Ofc::CVarStr::Reset(void)
0x18057174c  mov     rcx, [r14]; this
0x18057174f  call    ?StrongRelease@CProxyPtrImpl@Ofc@@IEAAXXZ; Ofc::CProxyPtrImpl::StrongRelease(void)
0x180571754  lea     r13, ?s_proxyPtrSentinel@?1??GetSentinel@CProxyPtrImpl@Ofc@@KAAEBQEAV23@XZ@4UProxyPtrSentinel@?1??123@KAAEBQEAV23@XZ@B; `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::ProxyPtrSentinel const `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::s_proxyPtrSentinel
0x18057175b  mov     [r14], r13
0x18057175e  mov     rcx, [rdi]; this
0x180571761  call    ?StrongRelease@CProxyPtrImpl@Ofc@@IEAAXXZ; Ofc::CProxyPtrImpl::StrongRelease(void)
0x180571766  mov     [rdi], r13
0x180571769  xor     r8d, r8d
0x18057176c  mov     dword ptr [rbp+0D0h+var_128+2], r8d
0x180571770  mov     word ptr [rbp+0D0h+var_128+6], r8w
0x180571775  mov     qword ptr [rbp+0D0h+var_128.tymed], 1
0x18057177d  mov     [rbp+0D0h+var_128.cfFormat], r12w
0x180571782  mov     [rbp+0D0h+var_128.ptd], r8
0x180571786  lea     edi, [r8+1]
0x18057178a  mov     [rbp+0D0h+var_128.dwAspect], edi
0x18057178d  mov     [rbp+0D0h+var_128.lindex], 0FFFFFFFFh
0x180571794  mov     r13d, r8d
0x180571797  mov     rcx, [rsi]; struct Ofc::CProxyPtrImpl *
0x18057179a  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x18057179f  mov     [rbp+0D0h+var_E8], rax
0x1805717a3  cmp     [rax+10h], r8
0x1805717a7  jz      loc_180571851
0x1805717ad  lea     rcx, ??_7HostParentWindowInfo@Art@@6B@; const Art::HostParentWindowInfo::`vftable'
0x1805717b4  mov     [rbp+0D0h+hMem], rcx
0x1805717b8  mov     [rbp+0D0h+hMem+8], r8
0x1805717bc  mov     rcx, rax; this
0x1805717bf  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1805717c4  mov     rcx, rax
0x1805717c7  mov     rax, [rax]
0x1805717ca  lea     rdx, [rbp+0D0h+hMem]
0x1805717ce  mov     rax, [rax+0A0h]
0x1805717d5  call    cs:__guard_dispatch_icall_fptr
0x1805717db  test    al, al
0x1805717dd  jz      short loc_18057182E
0x1805717df  mov     rcx, [rbp+0D0h+hMem+8]
0x1805717e3  test    rcx, rcx
0x1805717e6  jz      short loc_18057182E
0x1805717e8  lea     rdx, [rbp+0D0h+var_108]
0x1805717ec  call    ??$QueryObjectElseCrash@UIHWNDCanvas@PlatformCanvas@Mso@@$0A@@IObjectProxy@Mso@@QEAA?AV?$TCntPtr@UIHWNDCanvas@PlatformCanvas@Mso@@@1@XZ; Mso::IObjectProxy::QueryObjectElseCrash<Mso::PlatformCanvas::IHWNDCanvas,0>(void)
0x1805717f1  mov     rcx, rax
0x1805717f4  call    ??C?$TCntPtr@VAppAugmentationStatefulRuntime@AugLoop@Art@@@Mso@@QEBAPEAVAppAugmentationStatefulRuntime@AugLoop@Art@@XZ; Mso::TCntPtr<Art::AugLoop::AppAugmentationStatefulRuntime>::operator->(void)
0x1805717f9  mov     rcx, rax
0x1805717fc  mov     rax, [rax]
0x1805717ff  mov     rax, [rax+28h]
0x180571803  call    cs:__guard_dispatch_icall_fptr
0x180571809  mov     r13, rax
0x18057180c  mov     rdx, [rbp+0D0h+var_108]
0x180571810  test    rdx, rdx
0x180571813  jz      short loc_18057182E
0x180571815  mov     [rbp+0D0h+var_108], 0
0x18057181d  mov     rcx, [rdx]
0x180571820  mov     rax, [rcx+8]
0x180571824  mov     rcx, rdx
0x180571827  call    cs:__guard_dispatch_icall_fptr
0x18057182d  nop
0x18057182e  mov     rcx, [rbp+0D0h+hMem+8]
0x180571832  test    rcx, rcx
0x180571835  jz      short loc_18057184C
0x180571837  mov     [rbp+0D0h+hMem+8], 0
0x18057183f  mov     rax, [rcx]
0x180571842  mov     rax, [rax+8]
0x180571846  call    cs:__guard_dispatch_icall_fptr
0x18057184c  test    r13, r13
0x18057184f  jnz     short loc_18057187A
0x180571851  call    cs:__imp_?GetPolicyProtectionManagerFactory@EnterpriseDataProtection@Mso@@YAAEAUIPolicyProtectionManager@12@XZ; Mso::EnterpriseDataProtection::GetPolicyProtectionManagerFactory(void)
0x180571857  mov     rdx, rax
0x18057185a  mov     rcx, [rax]
0x18057185d  mov     rax, [rcx]
0x180571860  mov     rcx, rdx
0x180571863  call    cs:__guard_dispatch_icall_fptr
0x180571869  test    al, al
0x18057186b  jnz     loc_180571C51
0x180571871  call    cs:__imp_GetDesktopWindow
0x180571877  mov     r13, rax
0x18057187a  call    ?GetHTMLFormatInfo@Art@@YAAEBVFormatInfo@1@XZ; Art::GetHTMLFormatInfo(void)
0x18057187f  cmp     r12w, [rax+0Ch]
0x180571884  jnz     loc_180571A35
0x18057188a  mov     [rsp+1D0h+var_160], 0
0x180571893  test    rbx, rbx
0x180571896  jz      short loc_180571912
0x180571898  lea     r8, [rbp+0D0h+var_128]; struct tagFORMATETC *
0x18057189c  mov     rdx, rbx; struct IDataObject *
0x18057189f  lea     rcx, [rbp+0D0h+var_E0]; this
0x1805718a3  call    ??0TxStgMedium@Art@@QEAA@AEAUIDataObject@@AEBUtagFORMATETC@@@Z; Art::TxStgMedium::TxStgMedium(IDataObject &,tagFORMATETC const &)
0x1805718a8  lea     rdx, [rbp+0D0h+var_E0]
0x1805718ac  mov     rcx, rsi
0x1805718af  cmp     [rsp+1D0h+var_180], 0
0x1805718b4  jz      short loc_1805718FC
0x1805718b6  mov     rax, [rsp+1D0h+var_168]
0x1805718bb  mov     [rsp+1D0h+var_188], rax
0x1805718c0  mov     rax, qword ptr [rsp+1D0h+var_170]
0x1805718c5  mov     [rsp+1D0h+var_190], rax
0x1805718ca  mov     [rsp+1D0h+var_198], r15
0x1805718cf  mov     rax, [rsp+1D0h+var_178]
0x1805718d4  mov     [rsp+1D0h+var_1A0], rax
0x1805718d9  mov     [rsp+1D0h+var_1A8], r14
0x1805718de  mov     rax, [rbp+0D0h+arg_30]
0x1805718e5  mov     [rsp+1D0h+var_1B0], rax
0x1805718ea  mov     r9, [rbp+0D0h+var_100]
0x1805718ee  mov     r8b, [rbp+0D0h+arg_20]
0x1805718f5  call    ?FGetTextAndBlipAndAltTextListFromHtmlStream@Art@@YA_NAEBV?$TWeakPtr@VDocumentContext@Art@@@Ofc@@AEAVTxStgMedium@1@_NPEAUIMsoHTMLFileReferenceResolver@@PEAUIMetroProgress@@AEAV?$TOwningPtr@VTextBody@Art@@@3@AEAV?$TOwnerPtrList@VBlipAndAltText@Art@@@3@PEA_N77@Z; Art::FGetTextAndBlipAndAltTextListFromHtmlStream(Ofc::TWeakPtr<Art::DocumentContext> const &,Art::TxStgMedium &,bool,IMsoHTMLFileReferenceResolver *,IMetroProgress *,Ofc::TOwningPtr<Art::TextBody> &,Ofc::TOwnerPtrList<Art::BlipAndAltText> &,bool *,bool *,bool *)
0x1805718fa  jmp     short loc_180571907
0x1805718fc  mov     r9, r15
0x1805718ff  mov     r8, r14
0x180571902  call    ?FGetTextFromHtmlStream@Art@@YA_NAEBV?$TWeakPtr@VDocumentContext@Art@@@Ofc@@AEAVTxStgMedium@1@AEAV?$TOwningPtr@VTextBody@Art@@@3@PEA_N@Z; Art::FGetTextFromHtmlStream(Ofc::TWeakPtr<Art::DocumentContext> const &,Art::TxStgMedium &,Ofc::TOwningPtr<Art::TextBody> &,bool *)
0x180571907  mov     bl, al
0x180571909  lea     rcx, [rbp+0D0h+var_E0]
0x18057190d  jmp     loc_1805719F9
0x180571912  lea     rcx, [rbp+0D0h+var_68]
0x180571916  call    cs:__imp_?GetEnterpriseIdOfCurrentClipboardData@Clipboard@Mso@@YA?AVEnterpriseIdentity@EnterpriseDataProtection@2@XZ; Mso::Clipboard::GetEnterpriseIdOfCurrentClipboardData(void)
0x18057191c  mov     qword ptr [rbp+0D0h+var_130], rax
0x180571920  mov     rcx, [rsp+1D0h+var_160]
0x180571925  test    rcx, rcx
0x180571928  jz      short loc_18057193B
0x18057192a  mov     rdx, [rcx]
0x18057192d  mov     rax, [rdx+10h]
0x180571931  call    cs:__guard_dispatch_icall_fptr
0x180571937  mov     rax, qword ptr [rbp+0D0h+var_130]
0x18057193b  mov     [rsp+1D0h+var_160], 0
0x180571944  xor     r9d, r9d
0x180571947  mov     r8, r13
0x18057194a  mov     rdx, rax
0x18057194d  lea     rcx, [rsp+1D0h+var_160]
0x180571952  call    cs:__imp_?OleGetClipboardAndRequestAccessSynchronously@Clipboard@Mso@@YAJPEAPEAUIDataObject@@AEBVEnterpriseIdentity@EnterpriseDataProtection@2@PEAUHWND__@@W4EDPOverride@12@@Z; Mso::Clipboard::OleGetClipboardAndRequestAccessSynchronously(IDataObject * *,Mso::EnterpriseDataProtection::EnterpriseIdentity const &,HWND__ *,Mso::Clipboard::EDPOverride)
0x180571958  test    eax, eax
0x18057195a  jnz     short loc_180571969
0x18057195c  cmp     [rsp+1D0h+var_160], 0
0x180571962  mov     [rsp+1D0h+var_17F], dil
0x180571967  jnz     short loc_18057196E
0x180571969  mov     [rsp+1D0h+var_17F], 0
0x18057196e  lea     rcx, [rbp+0D0h+var_60]
0x180571972  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180571977  cmp     [rsp+1D0h+var_17F], 0
0x18057197c  jz      loc_180571A1E
0x180571982  lea     r8, [rbp+0D0h+var_128]; struct tagFORMATETC *
0x180571986  mov     rdx, [rsp+1D0h+var_160]; struct IDataObject *
0x18057198b  lea     rcx, [rbp+0D0h+var_A8]; this
0x18057198f  call    ??0TxStgMedium@Art@@QEAA@AEAUIDataObject@@AEBUtagFORMATETC@@@Z; Art::TxStgMedium::TxStgMedium(IDataObject &,tagFORMATETC const &)
0x180571994  lea     rdx, [rbp+0D0h+var_A8]
0x180571998  mov     rcx, rsi
0x18057199b  cmp     [rsp+1D0h+var_180], 0
0x1805719a0  jz      short loc_1805719E8
0x1805719a2  mov     rax, [rsp+1D0h+var_168]
0x1805719a7  mov     [rsp+1D0h+var_188], rax
0x1805719ac  mov     rax, qword ptr [rsp+1D0h+var_170]
0x1805719b1  mov     [rsp+1D0h+var_190], rax
0x1805719b6  mov     [rsp+1D0h+var_198], r15
0x1805719bb  mov     rax, [rsp+1D0h+var_178]
0x1805719c0  mov     [rsp+1D0h+var_1A0], rax
0x1805719c5  mov     [rsp+1D0h+var_1A8], r14
0x1805719ca  mov     rax, [rbp+0D0h+arg_30]
0x1805719d1  mov     [rsp+1D0h+var_1B0], rax
0x1805719d6  mov     r9, [rbp+0D0h+var_100]
0x1805719da  mov     r8b, [rbp+0D0h+arg_20]
0x1805719e1  call    ?FGetTextAndBlipAndAltTextListFromHtmlStream@Art@@YA_NAEBV?$TWeakPtr@VDocumentContext@Art@@@Ofc@@AEAVTxStgMedium@1@_NPEAUIMsoHTMLFileReferenceResolver@@PEAUIMetroProgress@@AEAV?$TOwningPtr@VTextBody@Art@@@3@AEAV?$TOwnerPtrList@VBlipAndAltText@Art@@@3@PEA_N77@Z; Art::FGetTextAndBlipAndAltTextListFromHtmlStream(Ofc::TWeakPtr<Art::DocumentContext> const &,Art::TxStgMedium &,bool,IMsoHTMLFileReferenceResolver *,IMetroProgress *,Ofc::TOwningPtr<Art::TextBody> &,Ofc::TOwnerPtrList<Art::BlipAndAltText> &,bool *,bool *,bool *)
0x1805719e6  jmp     short loc_1805719F3
0x1805719e8  mov     r9, r15
0x1805719eb  mov     r8, r14
0x1805719ee  call    ?FGetTextFromHtmlStream@Art@@YA_NAEBV?$TWeakPtr@VDocumentContext@Art@@@Ofc@@AEAVTxStgMedium@1@AEAV?$TOwningPtr@VTextBody@Art@@@3@PEA_N@Z; Art::FGetTextFromHtmlStream(Ofc::TWeakPtr<Art::DocumentContext> const &,Art::TxStgMedium &,Ofc::TOwningPtr<Art::TextBody> &,bool *)
0x1805719f3  mov     bl, al
0x1805719f5  lea     rcx, [rbp+0D0h+var_A8]; this
0x1805719f9  call    ??1TxStgMedium@Art@@QEAA@XZ; Art::TxStgMedium::~TxStgMedium(void)
0x1805719fe  mov     rcx, [rsp+1D0h+var_160]
0x180571a03  test    rcx, rcx
0x180571a06  jz      loc_180571F24
0x180571a0c  mov     rax, [rcx]
0x180571a0f  mov     rax, [rax+10h]
0x180571a13  call    cs:__guard_dispatch_icall_fptr
0x180571a19  jmp     loc_180571F24
0x180571a1e  mov     rcx, [rsp+1D0h+var_160]
0x180571a23  test    rcx, rcx
0x180571a26  jz      short loc_180571A35
0x180571a28  mov     rax, [rcx]
0x180571a2b  mov     rax, [rax+10h]
0x180571a2f  call    cs:__guard_dispatch_icall_fptr
0x180571a35  call    ?GetMathMLFormatInfo@Art@@YAAEBVFormatInfo@1@XZ; Art::GetMathMLFormatInfo(void)
0x180571a3a  cmp     r12w, [rax+0Ch]
0x180571a3f  jnz     loc_180571B2A
0x180571a45  xor     esi, esi
0x180571a47  mov     [rsp+1D0h+var_178], rsi
0x180571a4c  test    rbx, rbx
0x180571a4f  jz      short loc_180571A92
0x180571a51  lea     r8, [rbp+0D0h+var_128]; struct tagFORMATETC *
0x180571a55  mov     rdx, rbx; struct IDataObject *
0x180571a58  lea     rcx, [rbp+0D0h+var_88]; this
0x180571a5c  call    ??0TxStgMedium@Art@@QEAA@AEAUIDataObject@@AEBUtagFORMATETC@@@Z; Art::TxStgMedium::TxStgMedium(IDataObject &,tagFORMATETC const &)
0x180571a61  mov     r9, r15
0x180571a64  mov     r8, r14
0x180571a67  lea     rdx, [rbp+0D0h+var_88]
0x180571a6b  call    ?FGetTextFromMathMLStream@Art@@YA_NAEBV?$TWeakPtr@VDocumentContext@Art@@@Ofc@@AEAVTxStgMedium@1@AEAV?$TOwningPtr@VTextBody@Art@@@3@PEA_N@Z; Art::FGetTextFromMathMLStream(Ofc::TWeakPtr<Art::DocumentContext> const &,Art::TxStgMedium &,Ofc::TOwningPtr<Art::TextBody> &,bool *)
0x180571a70  mov     bl, al
0x180571a72  lea     rcx, [rbp+0D0h+var_88]; this
0x180571a76  call    ??1TxStgMedium@Art@@QEAA@XZ; Art::TxStgMedium::~TxStgMedium(void)
0x180571a7b  mov     rcx, [rsp+1D0h+var_178]
0x180571a80  test    rcx, rcx
0x180571a83  jz      loc_180571F24
0x180571a89  mov     rdx, [rcx]
0x180571a8c  mov     rax, [rdx+10h]
0x180571a90  jmp     short loc_180571A13
0x180571a92  lea     rcx, [rbp+0D0h+var_68]
0x180571a96  call    cs:__imp_?GetEnterpriseIdOfCurrentClipboardData@Clipboard@Mso@@YA?AVEnterpriseIdentity@EnterpriseDataProtection@2@XZ; Mso::Clipboard::GetEnterpriseIdOfCurrentClipboardData(void)
0x180571a9c  mov     rbx, rax
0x180571a9f  mov     rcx, [rsp+1D0h+var_178]
0x180571aa4  test    rcx, rcx
0x180571aa7  jz      short loc_180571AB6
0x180571aa9  mov     rdx, [rcx]
0x180571aac  mov     rax, [rdx+10h]
0x180571ab0  call    cs:__guard_dispatch_icall_fptr
0x180571ab6  mov     [rsp+1D0h+var_178], rsi
0x180571abb  xor     r9d, r9d
0x180571abe  mov     r8, r13
0x180571ac1  mov     rdx, rbx
0x180571ac4  lea     rcx, [rsp+1D0h+var_178]
0x180571ac9  call    cs:__imp_?OleGetClipboardAndRequestAccessSynchronously@Clipboard@Mso@@YAJPEAPEAUIDataObject@@AEBVEnterpriseIdentity@EnterpriseDataProtection@2@PEAUHWND__@@W4EDPOverride@12@@Z; Mso::Clipboard::OleGetClipboardAndRequestAccessSynchronously(IDataObject * *,Mso::EnterpriseDataProtection::EnterpriseIdentity const &,HWND__ *,Mso::Clipboard::EDPOverride)
0x180571acf  test    eax, eax
0x180571ad1  jnz     short loc_180571ADA
0x180571ad3  cmp     [rsp+1D0h+var_178], rsi
0x180571ad8  jnz     short loc_180571ADD
0x180571ada  mov     dil, sil
0x180571add  lea     rcx, [rbp+0D0h+var_60]
0x180571ae1  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180571ae6  test    dil, dil
0x180571ae9  jz      short loc_180571B20
0x180571aeb  lea     r8, [rbp+0D0h+var_128]; struct tagFORMATETC *
0x180571aef  mov     rdx, [rsp+1D0h+var_178]; struct IDataObject *
0x180571af4  lea     rcx, [rbp+0D0h+var_68]; this
0x180571af8  call    ??0TxStgMedium@Art@@QEAA@AEAUIDataObject@@AEBUtagFORMATETC@@@Z; Art::TxStgMedium::TxStgMedium(IDataObject &,tagFORMATETC const &)
0x180571afd  mov     r9, r15
0x180571b00  mov     r8, r14
0x180571b03  lea     rdx, [rbp+0D0h+var_68]
0x180571b07  nop     word ptr [rax+rax+00000000h]
0x180571b10  call    ?FGetTextFromMathMLStream@Art@@YA_NAEBV?$TWeakPtr@VDocumentContext@Art@@@Ofc@@AEAVTxStgMedium@1@AEAV?$TOwningPtr@VTextBody@Art@@@3@PEA_N@Z; Art::FGetTextFromMathMLStream(Ofc::TWeakPtr<Art::DocumentContext> const &,Art::TxStgMedium &,Ofc::TOwningPtr<Art::TextBody> &,bool *)
0x180571b15  mov     bl, al
0x180571b17  lea     rcx, [rbp+0D0h+var_68]
0x180571b1b  jmp     loc_180571A76
0x180571b20  mov     rcx, [rsp+1D0h+var_178]
0x180571b25  jmp     loc_180571C3E
0x180571b2a  call    ?GetNativeTextFormatInfo@Art@@YAAEBVFormatInfo@1@XZ; Art::GetNativeTextFormatInfo(void)
0x180571b2f  cmp     r12w, [rax+0Ch]
0x180571b34  jnz     loc_180571C86
0x180571b3a  mov     rax, [rsi]
0x180571b3d  xor     r15d, r15d
0x180571b40  cmp     [rax+10h], r15
0x180571b44  jz      loc_180571F21
0x180571b4a  mov     qword ptr [rsp+1D0h+var_170], r15
0x180571b4f  test    rbx, rbx
0x180571b52  jz      short loc_180571BB7
0x180571b54  mov     qword ptr [rbp+0D0h+var_130], rbx
0x180571b58  mov     rax, [rbx]
0x180571b5b  mov     rcx, rbx
0x180571b5e  mov     rax, [rax+8]
0x180571b62  call    cs:__guard_dispatch_icall_fptr
0x180571b68  mov     rax, [rbp+0D0h+var_F8]
0x180571b6c  mov     [rsp+1D0h+var_1B0], rax; struct Art::ClipboardStyleSheet *
0x180571b71  mov     r9, qword ptr [rbp+0D0h+var_F0]; int
0x180571b75  mov     r8, r14; int
0x180571b78  mov     rdx, rsi; int
0x180571b7b  lea     rcx, [rbp+0D0h+var_130]; int
0x180571b7f  nop
0x180571b80  call    ?FGetTextFromGvmlStream@Art@@YA_NAEBV?$TCntPtr@UIDataObject@@@Ofc@@AEBV?$TWeakPtr@VDocumentContext@Art@@@3@AEAV?$TOwningPtr@VTextBody@Art@@@3@AEAVTextAutofit@1@AEAV?$TOwningPtr@VClipboardTextResolver@Art@@@3@@Z; Art::FGetTextFromGvmlStream(Ofc::TCntPtr<IDataObject> const &,Ofc::TWeakPtr<Art::DocumentContext> const &,Ofc::TOwningPtr<Art::TextBody> &,Art::TextAutofit &,Ofc::TOwningPtr<Art::ClipboardTextResolver> &)
0x180571b85  mov     dil, al
0x180571b88  mov     rcx, [rbx]
  ... truncated ...
```
