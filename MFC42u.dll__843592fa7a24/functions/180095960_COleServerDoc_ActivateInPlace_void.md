# COleServerDoc::ActivateInPlace(void)

- ea: `0x180095960`
- end: `0x180095ef9`
- name: `?ActivateInPlace@COleServerDoc@@QEAAHXZ`
- size: `1433`
- prototype: `__int64 __fastcall(COleServerDoc *__hidden this)`
- caller_count: `2`
- callee_count: `18`
- tags: `installer_update`

## callers

- `0x18009b760`
- `0x1800b05a0`

## callees

- `0x18000a150`
- `0x18000ce50`
- `0x1800122f0`
- `0x180013330`
- `0x180019290`
- `0x18001a490`
- `0x18001fdf0`
- `0x180024410`
- `0x180026a40`
- `0x180029f20`
- `0x1800432c0`
- `0x180071bd0`
- `0x18008efd0`
- `0x180091af0`
- `0x180095960`
- `0x18009cf3c`
- `0x1800d1fe0`
- `0x1800d7010`

## import_xrefs

- `USER32!IsWindowVisible` at `0x1800959e5`
- `USER32!IsWindowVisible` at `0x1800959e5`
- `USER32!CopyRect` at `0x180095c79`
- `USER32!CopyRect` at `0x180095c8a`
- `USER32!CopyRect` at `0x180095c79`
- `USER32!CopyRect` at `0x180095c8a`
- `USER32!UpdateWindow` at `0x180095e1a`
- `USER32!UpdateWindow` at `0x180095e1a`
- `USER32!ReleaseDC` at `0x180095b9d`
- `USER32!ReleaseDC` at `0x180095b9d`
- `USER32!GetDC` at `0x180095b7d`
- `USER32!GetDC` at `0x180095b7d`
- `USER32!IsRectEmpty` at `0x180095c64`
- `USER32!IsRectEmpty` at `0x180095cbc`
- `USER32!IsRectEmpty` at `0x180095c64`
- `USER32!IsRectEmpty` at `0x180095cbc`
- `USER32!WindowFromDC` at `0x180095b8e`
- `USER32!WindowFromDC` at `0x180095b8e`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall COleServerDoc::ActivateInPlace(COleServerDoc *this)
{
  __int64 v2; // rcx
  __int64 v3; // rax
  struct CFrameWnd *FirstFrame; // rax
  unsigned __int16 *v6; // rbx
  struct AFX_MODULE_STATE *ModuleState; // rax
  struct IUnknown *Interface; // rax
  struct IUnknown *v9; // rsi
  struct CWnd *v10; // rax
  __int64 v11; // rax
  _QWORD *v12; // r14
  struct IUnknown *v13; // rcx
  _QWORD *v14; // r12
  _QWORD *v15; // r13
  HWND v16; // r15
  HDC DC; // rax
  HDC v18; // r13
  HWND v19; // rbx
  COleCntrFrameWnd *v20; // rax
  CWnd *v21; // rax
  __int64 v22; // rcx
  COleCntrFrameWnd *v23; // rax
  CWnd *v24; // rax
  BOOL v25; // eax
  RECT *p_rcSrc; // rdx
  BOOL v27; // eax
  RECT *p_rc; // rdx
  struct IUnknown *v29; // rbx
  __int64 v30; // rdx
  HWND hWnd; // [rsp+40h] [rbp-39h] BYREF
  LPCWSTR v32; // [rsp+48h] [rbp-31h] BYREF
  unsigned __int16 *v33; // [rsp+50h] [rbp-29h] BYREF
  HWND v34[2]; // [rsp+58h] [rbp-21h] BYREF
  RECT rcSrc; // [rsp+68h] [rbp-11h] BYREF
  RECT rc; // [rsp+78h] [rbp-1h] BYREF

  v2 = *((_QWORD *)this + 41);
  if ( !v2 )
    return 0;
  v3 = *((_QWORD *)this + 45);
  if ( v3 )
  {
    if ( *(_DWORD *)(v3 + 336) )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 48LL))(v2);
      return 1;
    }
    (*(void (__fastcall **)(COleServerDoc *))(*(_QWORD *)this + 544LL))(this);
  }
  FirstFrame = COleDocument::GetFirstFrame(this);
  if ( IsWindowVisible(*((HWND *)FirstFrame + 8)) )
    return 0;
  v33 = (unsigned __int16 *)_afxPchNil;
  v32 = _afxPchNil;
  if ( !(*(unsigned int (__fastcall **)(COleServerDoc *, unsigned __int16 **))(*(_QWORD *)this + 624LL))(this, &v33)
    || (v6 = v33,
        ModuleState = AfxGetModuleState(),
        AfxFormatString2((struct CString *)&v32, 0xE005u, *((const unsigned __int16 **)ModuleState + 4), v6),
        Interface = _AfxQueryInterface(*((struct IUnknown **)this + 41), &IID_IOleInPlaceSite),
        (v9 = Interface) == 0) )
  {
LABEL_47:
    CString::~CString((CString *)&v32);
    CString::~CString((CString *)&v33);
    return 0;
  }
  if ( ((unsigned int (__fastcall *)(struct IUnknown *))Interface->lpVtbl[1].Release)(Interface)
    || ((unsigned int (__fastcall *)(struct IUnknown *))v9->lpVtbl[2].QueryInterface)(v9) )
  {
    goto LABEL_46;
  }
  hWnd = 0;
  ((void (__fastcall *)(struct IUnknown *, HWND *))v9->lpVtbl[1].QueryInterface)(v9, &hWnd);
  v10 = CWnd::FromHandle(hWnd);
  v11 = (*(__int64 (__fastcall **)(COleServerDoc *, struct CWnd *))(*(_QWORD *)this + 600LL))(this, v10);
  v12 = (_QWORD *)v11;
  v13 = v9;
  if ( !v11 )
  {
LABEL_45:
    ((void (__fastcall *)(struct IUnknown *))v9->lpVtbl[3].Release)(v13);
    goto LABEL_46;
  }
  *((_QWORD *)this + 45) = v11;
  if ( ((unsigned int (__fastcall *)(struct IUnknown *))v9->lpVtbl[2].AddRef)(v9) )
  {
LABEL_43:
    if ( *((_QWORD *)this + 45) )
    {
      (*(void (__fastcall **)(COleServerDoc *, _QWORD *))(*(_QWORD *)this + 608LL))(this, v12);
      *((_QWORD *)this + 45) = 0;
      v13 = v9;
      goto LABEL_45;
    }
LABEL_46:
    ((void (__fastcall *)(struct IUnknown *))v9->lpVtbl->Release)(v9);
    goto LABEL_47;
  }
  rc = 0;
  rcSrc = 0;
  v14 = v12 + 48;
  v15 = v12 + 47;
  if ( ((unsigned int (__fastcall *)(struct IUnknown *, _QWORD *, _QWORD *, RECT *, RECT *, _QWORD *))v9->lpVtbl[2].Release)(
         v9,
         v12 + 47,
         v12 + 48,
         &rc,
         &rcSrc,
         v12 + 43)
    || !(*(unsigned int (__fastcall **)(_QWORD *))(*v12 + 536LL))(v12) )
  {
    goto LABEL_42;
  }
  (*(void (__fastcall **)(_QWORD, HWND *))(*(_QWORD *)*v15 + 24LL))(*v15, &hWnd);
  v16 = hWnd;
  if ( (unsigned __int64)hWnd <= 0xFFFF )
  {
    DC = GetDC(hWnd);
    v18 = DC;
    if ( DC )
    {
      v19 = WindowFromDC(DC);
      ReleaseDC(v16, v18);
      if ( v19 )
        v16 = v19;
    }
    v15 = v12 + 47;
  }
  hWnd = v16;
  v20 = (COleCntrFrameWnd *)operator new(0x158u);
  v34[0] = (HWND)v20;
  if ( v20 )
    v21 = COleCntrFrameWnd::COleCntrFrameWnd(v20, (struct COleIPFrameWnd *)v12);
  else
    v21 = 0;
  v12[49] = v21;
  CWnd::Attach(v21, hWnd);
  v22 = *v14;
  if ( *v14 )
  {
    v34[0] = 0;
    (*(void (__fastcall **)(__int64, HWND *))(*(_QWORD *)v22 + 24LL))(v22, v34);
    if ( v34[0] == hWnd )
    {
      _AfxRelease((struct IUnknown **)v12 + 48);
      *v14 = 0;
    }
    else
    {
      v23 = (COleCntrFrameWnd *)operator new(0x158u);
      v34[1] = (HWND)v23;
      if ( v23 )
        v24 = COleCntrFrameWnd::COleCntrFrameWnd(v23, (struct COleIPFrameWnd *)v12);
      else
        v24 = 0;
      v12[50] = v24;
      CWnd::Attach(v24, v34[0]);
    }
  }
  v25 = IsRectEmpty(&rc);
  p_rcSrc = &rcSrc;
  if ( !v25 )
    p_rcSrc = &rc;
  CopyRect((LPRECT)v12 + 28, p_rcSrc);
  CopyRect((LPRECT)v12 + 29, &rcSrc);
  if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, _QWORD))(*v12 + 504LL))(v12, v12[49], v12[50]) )
  {
LABEL_42:
    ((void (__fastcall *)(struct IUnknown *, _QWORD))v9->lpVtbl[3].AddRef)(v9, 0);
    goto LABEL_43;
  }
  v27 = IsRectEmpty(&rc);
  p_rc = &rcSrc;
  if ( !v27 )
    p_rc = &rc;
  (*(void (__fastcall **)(COleServerDoc *, RECT *, RECT *))(*(_QWORD *)this + 560LL))(this, p_rc, &rcSrc);
  v29 = CCmdTarget::GetInterface(this, &IID_IOleInPlaceActiveObject);
  (*(void (__fastcall **)(_QWORD, struct IUnknown *, LPCWSTR))(*(_QWORD *)*v15 + 64LL))(*v15, v29, v32);
  if ( *v14 )
    (*(void (__fastcall **)(_QWORD, struct IUnknown *, LPCWSTR))(*(_QWORD *)*v14 + 64LL))(*v14, v29, v32);
  (*(void (__fastcall **)(COleServerDoc *, _QWORD, __int64))(*(_QWORD *)this + 592LL))(
    this,
    *(_QWORD *)(*((_QWORD *)this + 45) + 392LL),
    1);
  v30 = *((_QWORD *)this + 45);
  if ( *(_QWORD *)(v30 + 384) )
    (*(void (__fastcall **)(COleServerDoc *, _QWORD, __int64))(*(_QWORD *)this + 592LL))(
      this,
      *(_QWORD *)(v30 + 400),
      1);
  CFrameWnd::ShowOwnedWindows(*((CFrameWnd **)this + 45), 1);
  (*(void (__fastcall **)(COleServerDoc *, _QWORD, _QWORD, __int64))(*(_QWORD *)this + 616LL))(this, 0, *v15, 1);
  if ( *v14 )
    (*(void (__fastcall **)(COleServerDoc *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)this + 616LL))(this, 0, *v14, 0);
  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)*v15 + 80LL))(*v15, v12[51], v12[55], v12[8]);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 41) + 48LL))(*((_QWORD *)this + 41));
  CWnd::ShowWindow((CWnd *)v12, 5);
  CWnd::SetFocus((CWnd *)v12);
  UpdateWindow((HWND)v12[8]);
  COleLinkingDoc::UpdateVisibleLock(this, 1, 0);
  (*(void (__fastcall **)(COleServerDoc *, __int64))(*(_QWORD *)this + 576LL))(this, 1);
  *((_DWORD *)v12 + 84) = 1;
  ((void (__fastcall *)(struct IUnknown *))v9->lpVtbl->Release)(v9);
  CString::~CString((CString *)&v32);
  CString::~CString((CString *)&v33);
  return 1;
}

```

## disassembly

```asm
0x180095960  push    rbp
0x180095962  push    rbx
0x180095963  push    rsi
0x180095964  push    rdi
0x180095965  push    r12
0x180095967  push    r13
0x180095969  push    r14
0x18009596b  push    r15
0x18009596d  lea     rbp, [rsp-1Fh]
0x180095972  sub     rsp, 98h
0x180095979  mov     rax, cs:__security_cookie
0x180095980  xor     rax, rsp
0x180095983  mov     [rbp+57h+var_48], rax
0x180095987  mov     rdi, rcx
0x18009598a  mov     rcx, [rcx+148h]
0x180095991  xor     r15d, r15d
0x180095994  test    rcx, rcx
0x180095997  jz      loc_180095ED7
0x18009599d  mov     rax, [rdi+168h]
0x1800959a4  test    rax, rax
0x1800959a7  jz      short loc_1800959D9
0x1800959a9  cmp     [rax+150h], r15d
0x1800959b0  jz      short loc_1800959C7
0x1800959b2  mov     rax, [rcx]
0x1800959b5  mov     rax, [rax+30h]
0x1800959b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800959be  lea     eax, [r15+1]
0x1800959c2  jmp     loc_180095ED9
0x1800959c7  mov     rax, [rdi]
0x1800959ca  mov     rcx, rdi
0x1800959cd  mov     rax, [rax+220h]
0x1800959d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800959d9  mov     rcx, rdi; this
0x1800959dc  call    ?GetFirstFrame@COleDocument@@QEAAPEAVCFrameWnd@@XZ; COleDocument::GetFirstFrame(void)
0x1800959e1  mov     rcx, [rax+40h]; hWnd
0x1800959e5  call    cs:__imp_IsWindowVisible
0x1800959eb  test    eax, eax
0x1800959ed  jnz     loc_180095ED7
0x1800959f3  mov     rax, cs:?_afxPchNil@@3PEBGEB; ushort const * const _afxPchNil
0x1800959fa  mov     [rbp+57h+var_80], rax
0x1800959fe  mov     [rbp+57h+var_88], rax
0x180095a02  mov     rax, [rdi]
0x180095a05  lea     rdx, [rbp+57h+var_80]
0x180095a09  mov     rcx, rdi
0x180095a0c  mov     rax, [rax+270h]
0x180095a13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095a18  test    eax, eax
0x180095a1a  jz      loc_180095EC4
0x180095a20  mov     rbx, [rbp+57h+var_80]
0x180095a24  call    ?AfxGetModuleState@@YAPEAVAFX_MODULE_STATE@@XZ; AfxGetModuleState(void)
0x180095a29  mov     r9, rbx; unsigned __int16 *
0x180095a2c  mov     r8, [rax+20h]; unsigned __int16 *
0x180095a30  mov     edx, 0E005h; unsigned int
0x180095a35  lea     rcx, [rbp+57h+var_88]; struct CString *
0x180095a39  call    ?AfxFormatString2@@YAXAEAVCString@@IPEBG1@Z; AfxFormatString2(CString &,uint,ushort const *,ushort const *)
0x180095a3e  lea     rdx, IID_IOleInPlaceSite; struct _GUID *
0x180095a45  mov     rcx, [rdi+148h]; struct IUnknown *
0x180095a4c  call    ?_AfxQueryInterface@@YAPEAUIUnknown@@PEAU1@AEBU_GUID@@@Z; _AfxQueryInterface(IUnknown *,_GUID const &)
0x180095a51  mov     rsi, rax
0x180095a54  test    rax, rax
0x180095a57  jz      loc_180095EC4
0x180095a5d  mov     rcx, [rax]
0x180095a60  mov     rax, [rcx+28h]
0x180095a64  mov     rcx, rsi
0x180095a67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095a6c  test    eax, eax
0x180095a6e  jnz     loc_180095EB4
0x180095a74  mov     rcx, [rsi]
0x180095a77  mov     rax, [rcx+30h]
0x180095a7b  mov     rcx, rsi
0x180095a7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095a83  test    eax, eax
0x180095a85  jnz     loc_180095EB4
0x180095a8b  mov     [rbp+57h+hWnd], r15
0x180095a8f  mov     rax, [rsi]
0x180095a92  lea     rdx, [rbp+57h+hWnd]
0x180095a96  mov     rcx, rsi
0x180095a99  mov     rax, [rax+18h]
0x180095a9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095aa2  mov     rcx, [rbp+57h+hWnd]; HWND
0x180095aa6  call    ?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandle(HWND__ *)
0x180095aab  mov     rcx, [rdi]
0x180095aae  mov     r8, [rcx+258h]
0x180095ab5  mov     rdx, rax
0x180095ab8  mov     rcx, rdi
0x180095abb  mov     rax, r8
0x180095abe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095ac3  mov     r14, rax
0x180095ac6  mov     rcx, rsi
0x180095ac9  test    rax, rax
0x180095acc  jz      loc_180095EA8
0x180095ad2  mov     [rdi+168h], rax
0x180095ad9  mov     rax, [rsi]
0x180095adc  mov     rax, [rax+38h]
0x180095ae0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095ae5  test    eax, eax
0x180095ae7  jnz     loc_180095E80
0x180095aed  xorps   xmm0, xmm0
0x180095af0  movups  xmmword ptr [rbp+57h+rc.left], xmm0
0x180095af4  xorps   xmm1, xmm1
0x180095af7  movups  xmmword ptr [rbp+57h+rcSrc.left], xmm1
0x180095afb  lea     r12, [r14+180h]
0x180095b02  lea     r13, [r14+178h]
0x180095b09  mov     rax, [rsi]
0x180095b0c  lea     rcx, [r14+158h]
0x180095b13  mov     [rsp+0D0h+var_A8], rcx
0x180095b18  lea     rcx, [rbp+57h+rcSrc]
0x180095b1c  mov     [rsp+0D0h+var_B0], rcx
0x180095b21  lea     r9, [rbp+57h+rc]
0x180095b25  mov     r8, r12
0x180095b28  mov     rdx, r13
0x180095b2b  mov     rcx, rsi
0x180095b2e  mov     rax, [rax+40h]
0x180095b32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095b37  test    eax, eax
0x180095b39  jnz     loc_180095E6F
0x180095b3f  mov     rax, [r14]
0x180095b42  mov     rcx, r14
0x180095b45  mov     rax, [rax+218h]
0x180095b4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095b51  test    eax, eax
0x180095b53  jz      loc_180095E6F
0x180095b59  mov     rcx, [r13+0]
0x180095b5d  mov     rax, [rcx]
0x180095b60  lea     rdx, [rbp+57h+hWnd]
0x180095b64  mov     rax, [rax+18h]
0x180095b68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095b6d  mov     r15, [rbp+57h+hWnd]
0x180095b71  cmp     r15, 0FFFFh
0x180095b78  ja      short loc_180095BB1
0x180095b7a  mov     rcx, r15; hWnd
0x180095b7d  call    cs:__imp_GetDC
0x180095b83  mov     r13, rax
0x180095b86  test    rax, rax
0x180095b89  jz      short loc_180095BAA
0x180095b8b  mov     rcx, rax; hDC
0x180095b8e  call    cs:__imp_WindowFromDC
0x180095b94  mov     rbx, rax
0x180095b97  mov     rdx, r13; hDC
0x180095b9a  mov     rcx, r15; hWnd
0x180095b9d  call    cs:__imp_ReleaseDC
0x180095ba3  test    rbx, rbx
0x180095ba6  cmovnz  r15, rbx
0x180095baa  lea     r13, [r14+178h]
0x180095bb1  mov     [rbp+57h+hWnd], r15
0x180095bb5  mov     ebx, 158h
0x180095bba  mov     ecx, ebx; Size
0x180095bbc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180095bc1  mov     [rbp+57h+var_78], rax
0x180095bc5  xor     r15d, r15d
0x180095bc8  test    rax, rax
0x180095bcb  jz      short loc_180095BDA
0x180095bcd  mov     rdx, r14; struct COleIPFrameWnd *
0x180095bd0  mov     rcx, rax; this
0x180095bd3  call    ??0COleCntrFrameWnd@@QEAA@PEAVCOleIPFrameWnd@@@Z; COleCntrFrameWnd::COleCntrFrameWnd(COleIPFrameWnd *)
0x180095bd8  jmp     short loc_180095BDD
0x180095bda  mov     rax, r15
0x180095bdd  mov     [r14+188h], rax
0x180095be4  mov     rdx, [rbp+57h+hWnd]; HWND
0x180095be8  mov     rcx, rax; this
0x180095beb  call    ?Attach@CWnd@@QEAAHPEAUHWND__@@@Z; CWnd::Attach(HWND__ *)
0x180095bf0  mov     rcx, [r12]
0x180095bf4  test    rcx, rcx
0x180095bf7  jz      short loc_180095C59
0x180095bf9  mov     [rbp+57h+var_78], r15
0x180095bfd  mov     rax, [rcx]
0x180095c00  lea     rdx, [rbp+57h+var_78]
0x180095c04  mov     rax, [rax+18h]
0x180095c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095c0d  mov     rax, [rbp+57h+hWnd]
0x180095c11  cmp     [rbp+57h+var_78], rax
0x180095c15  jz      short loc_180095C4D
0x180095c17  mov     rcx, rbx; Size
0x180095c1a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180095c1f  mov     [rbp+57h+var_70], rax
0x180095c23  test    rax, rax
0x180095c26  jz      short loc_180095C35
0x180095c28  mov     rdx, r14; struct COleIPFrameWnd *
0x180095c2b  mov     rcx, rax; this
0x180095c2e  call    ??0COleCntrFrameWnd@@QEAA@PEAVCOleIPFrameWnd@@@Z; COleCntrFrameWnd::COleCntrFrameWnd(COleIPFrameWnd *)
0x180095c33  jmp     short loc_180095C38
0x180095c35  mov     rax, r15
0x180095c38  mov     [r14+190h], rax
0x180095c3f  mov     rdx, [rbp+57h+var_78]; HWND
0x180095c43  mov     rcx, rax; this
0x180095c46  call    ?Attach@CWnd@@QEAAHPEAUHWND__@@@Z; CWnd::Attach(HWND__ *)
0x180095c4b  jmp     short loc_180095C59
0x180095c4d  mov     rcx, r12; struct IUnknown **
0x180095c50  call    ?_AfxRelease@@YAKPEAPEAUIUnknown@@@Z; _AfxRelease(IUnknown * *)
0x180095c55  mov     [r12], r15
0x180095c59  lea     rbx, [r14+1C0h]
0x180095c60  lea     rcx, [rbp+57h+rc]; lprc
0x180095c64  call    cs:__imp_IsRectEmpty
0x180095c6a  mov     rcx, rbx; lprcDst
0x180095c6d  test    eax, eax
0x180095c6f  lea     rdx, [rbp+57h+rcSrc]
0x180095c73  jnz     short loc_180095C79
0x180095c75  lea     rdx, [rbp+57h+rc]; lprcSrc
0x180095c79  call    cs:__imp_CopyRect
0x180095c7f  lea     rcx, [r14+1D0h]; lprcDst
0x180095c86  lea     rdx, [rbp+57h+rcSrc]; lprcSrc
0x180095c8a  call    cs:__imp_CopyRect
0x180095c90  mov     rax, [r14]
0x180095c93  mov     r8, [r14+190h]
0x180095c9a  mov     rdx, [r14+188h]
0x180095ca1  mov     rcx, r14
0x180095ca4  mov     rax, [rax+1F8h]
0x180095cab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095cb0  test    eax, eax
0x180095cb2  jz      loc_180095E6F
0x180095cb8  lea     rcx, [rbp+57h+rc]; lprc
0x180095cbc  call    cs:__imp_IsRectEmpty
0x180095cc2  mov     rcx, [rdi]
0x180095cc5  mov     r9, [rcx+230h]
0x180095ccc  lea     r8, [rbp+57h+rcSrc]
0x180095cd0  mov     rcx, rdi
0x180095cd3  test    eax, eax
0x180095cd5  mov     rax, r9
0x180095cd8  lea     rdx, [rbp+57h+rcSrc]
0x180095cdc  jnz     short loc_180095CE2
0x180095cde  lea     rdx, [rbp+57h+rc]
0x180095ce2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095ce7  lea     rdx, IID_IOleInPlaceActiveObject; void *
0x180095cee  mov     rcx, rdi; this
0x180095cf1  call    ?GetInterface@CCmdTarget@@QEAAPEAUIUnknown@@PEBX@Z; CCmdTarget::GetInterface(void const *)
0x180095cf6  mov     rbx, rax
0x180095cf9  mov     r9, [r13+0]
0x180095cfd  mov     rcx, [r9]
0x180095d00  mov     rax, [rcx+40h]
0x180095d04  mov     r8, [rbp+57h+var_88]
0x180095d08  mov     rdx, rbx
0x180095d0b  mov     rcx, r9
0x180095d0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095d13  mov     rcx, [r12]
0x180095d17  test    rcx, rcx
0x180095d1a  jz      short loc_180095D2F
0x180095d1c  mov     rax, [rcx]
0x180095d1f  mov     r8, [rbp+57h+var_88]
0x180095d23  mov     rdx, rbx
0x180095d26  mov     rax, [rax+40h]
0x180095d2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095d2f  mov     rax, [rdi]
0x180095d32  mov     rdx, [rdi+168h]
0x180095d39  mov     ebx, 1
0x180095d3e  mov     r8d, ebx
0x180095d41  mov     rdx, [rdx+188h]
0x180095d48  mov     rcx, rdi
0x180095d4b  mov     rax, [rax+250h]
0x180095d52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095d57  mov     rdx, [rdi+168h]
0x180095d5e  cmp     [rdx+180h], r15
0x180095d65  jz      short loc_180095D83
0x180095d67  mov     rax, [rdi]
0x180095d6a  mov     r8d, ebx
0x180095d6d  mov     rdx, [rdx+190h]
0x180095d74  mov     rcx, rdi
0x180095d77  mov     rax, [rax+250h]
0x180095d7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095d83  mov     edx, ebx; int
0x180095d85  mov     rcx, [rdi+168h]; this
0x180095d8c  call    ?ShowOwnedWindows@CFrameWnd@@QEAAXH@Z; CFrameWnd::ShowOwnedWindows(int)
0x180095d91  mov     rax, [rdi]
0x180095d94  mov     r9d, ebx
0x180095d97  mov     r8, [r13+0]
0x180095d9b  xor     edx, edx
0x180095d9d  mov     rcx, rdi
0x180095da0  mov     rax, [rax+268h]
0x180095da7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095dac  mov     r8, [r12]
0x180095db0  test    r8, r8
0x180095db3  jz      short loc_180095DCC
0x180095db5  mov     rax, [rdi]
0x180095db8  xor     r9d, r9d
0x180095dbb  xor     edx, edx
0x180095dbd  mov     rcx, rdi
0x180095dc0  mov     rax, [rax+268h]
0x180095dc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095dcc  mov     rcx, [r13+0]
0x180095dd0  mov     rax, [rcx]
0x180095dd3  mov     r9, [r14+40h]
0x180095dd7  mov     r8, [r14+1B8h]
0x180095dde  mov     rdx, [r14+198h]
0x180095de5  mov     rax, [rax+50h]
0x180095de9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095dee  mov     rcx, [rdi+148h]
0x180095df5  mov     rax, [rcx]
0x180095df8  mov     rax, [rax+30h]
0x180095dfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095e01  mov     edx, 5; int
0x180095e06  mov     rcx, r14; this
0x180095e09  call    ?ShowWindow@CWnd@@QEAAHH@Z; CWnd::ShowWindow(int)
0x180095e0e  mov     rcx, r14; this
0x180095e11  call    ?SetFocus@CWnd@@QEAAPEAV1@XZ; CWnd::SetFocus(void)
0x180095e16  mov     rcx, [r14+40h]; hWnd
0x180095e1a  call    cs:__imp_UpdateWindow
0x180095e20  xor     r8d, r8d; int
0x180095e23  mov     edx, ebx; int
0x180095e25  mov     rcx, rdi; this
0x180095e28  call    ?UpdateVisibleLock@COleLinkingDoc@@IEAAXHH@Z; COleLinkingDoc::UpdateVisibleLock(int,int)
0x180095e2d  mov     rax, [rdi]
  ... truncated ...
```
