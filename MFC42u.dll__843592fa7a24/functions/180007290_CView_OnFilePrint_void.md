# CView::OnFilePrint(void)

- ea: `0x180007290`
- end: `0x180007c76`
- name: `?OnFilePrint@CView@@IEAAXXZ`
- size: `2534`
- prototype: `void __fastcall(CView *__hidden this)`
- caller_count: `0`
- callee_count: `39`
- tags: `installer_update`

## callees

- `0x180007290`
- `0x180007c80`
- `0x180007cd0`
- `0x180007ee0`
- `0x180007f10`
- `0x180007f90`
- `0x18000a7d0`
- `0x18000c0a0`
- `0x18000c860`
- `0x18000c950`
- `0x18000d820`
- `0x18000d960`
- `0x18000e1a0`
- `0x18000e460`
- `0x180011e80`
- `0x180013330`
- `0x1800142a0`
- `0x180014420`
- `0x180014640`
- `0x180014a00`
- `0x180019290`
- `0x18002ac00`
- `0x18002afd0`
- `0x18002c270`
- `0x18002d490`
- `0x18002d540`
- `0x18002d5a0`
- `0x18002d700`
- `0x18002da20`
- `0x18002e0e0`
- `0x18002e1f0`
- `0x180059d20`
- `0x180059ec0`
- `0x180059fa0`
- `0x18005a5e0`
- `0x1800631c0`
- `0x1800d1f92`
- `0x1800d1fe0`
- `0x1800d7010`

## import_xrefs

- `msvcrt!free` at `0x1800075f4`
- `msvcrt!free` at `0x180007792`
- `msvcrt!free` at `0x1800078d0`
- `msvcrt!free` at `0x180007903`
- `msvcrt!free` at `0x18000792f`
- `msvcrt!free` at `0x18000794c`
- `msvcrt!free` at `0x1800075f4`
- `msvcrt!free` at `0x180007792`
- `msvcrt!free` at `0x1800078d0`
- `msvcrt!free` at `0x180007903`
- `msvcrt!free` at `0x18000792f`
- `msvcrt!free` at `0x18000794c`
- `msvcrt!swprintf_s` at `0x180007a97`
- `msvcrt!swprintf_s` at `0x180007a97`
- `USER32!UpdateWindow` at `0x180007833`
- `USER32!UpdateWindow` at `0x180007833`
- `USER32!SetRect` at `0x180007af8`
- `USER32!SetRect` at `0x180007af8`
- `USER32!SetDlgItemTextW` at `0x180007710`
- `USER32!SetDlgItemTextW` at `0x18000774e`
- `USER32!SetDlgItemTextW` at `0x1800077ef`
- `USER32!SetDlgItemTextW` at `0x180007710`
- `USER32!SetDlgItemTextW` at `0x18000774e`
- `USER32!SetDlgItemTextW` at `0x1800077ef`
- `USER32!ShowWindow` at `0x180007818`
- `USER32!ShowWindow` at `0x180007818`
- `GDI32!CreateDCW` at `0x18000730a`
- `GDI32!CreateDCW` at `0x18000730a`
- `GDI32!SetAbortProc` at `0x18000769a`
- `GDI32!SetAbortProc` at `0x18000769a`
- `GDI32!GetDeviceCaps` at `0x180007acd`
- `GDI32!GetDeviceCaps` at `0x180007adf`
- `GDI32!GetDeviceCaps` at `0x180007acd`
- `GDI32!GetDeviceCaps` at `0x180007adf`
- `GDI32!DeleteDC` at `0x180007973`
- `GDI32!DeleteDC` at `0x180007973`
- `GDI32!StartDocW` at `0x18000784f`
- `GDI32!StartDocW` at `0x18000784f`
- `GDI32!DPtoLP` at `0x180007b10`
- `GDI32!DPtoLP` at `0x180007b10`
- `GDI32!StartPage` at `0x180007b1b`
- `GDI32!StartPage` at `0x180007b1b`
- `GDI32!EndPage` at `0x180007b6f`
- `GDI32!EndPage` at `0x180007b6f`
- `GDI32!EndDoc` at `0x180007bac`
- `GDI32!EndDoc` at `0x180007bac`
- `GDI32!AbortDoc` at `0x180007bb4`
- `GDI32!AbortDoc` at `0x180007bb4`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
void __fastcall CView::OnFilePrint(CView *this)
{
  __int64 v2; // rcx
  HDC DCW; // rax
  const WCHAR *v4; // rdx
  WCHAR *v5; // rbx
  CString *p_lpString; // rcx
  __int64 PathName; // rax
  __int64 v8; // rdx
  CWnd *ParentFrame; // rax
  const WCHAR *v10; // rax
  WCHAR *v11; // rsi
  __int64 PortName; // rax
  UINT v13; // r15d
  wchar_t *v14; // rax
  CWnd *MainWnd; // rax
  wchar_t *v16; // r14
  const WCHAR *v17; // r8
  unsigned __int16 *v18; // rbx
  CWnd *v19; // rax
  wchar_t *v20; // rcx
  unsigned __int16 *v21; // rcx
  HDC v22; // rax
  unsigned __int16 *v23; // rcx
  unsigned int v24; // r9d
  unsigned int v25; // edx
  unsigned int v26; // ebx
  unsigned int v27; // eax
  int v28; // r14d
  int v29; // r15d
  int v30; // esi
  int v31; // eax
  int yBottom; // ebx
  int DeviceCaps; // eax
  CWnd *v34; // rax
  LPCWSTR lpString; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *Format; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v37; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v38; // [rsp+58h] [rbp-A8h] BYREF
  void **v39; // [rsp+60h] [rbp-A0h] BYREF
  HDC hdc[2]; // [rsp+68h] [rbp-98h]
  int v41; // [rsp+78h] [rbp-88h]
  LPCWSTR v42; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v43; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v44; // [rsp+90h] [rbp-70h] BYREF
  DOCINFOW v45; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v46[8]; // [rsp+C0h] [rbp-40h] BYREF
  HWND hDlg; // [rsp+100h] [rbp+0h]
  __int64 v48; // [rsp+130h] [rbp+30h]
  __int64 v49; // [rsp+138h] [rbp+38h]
  char v50[64]; // [rsp+140h] [rbp+40h] BYREF
  __int64 v51; // [rsp+180h] [rbp+80h] BYREF
  int v52; // [rsp+188h] [rbp+88h]
  int v53; // [rsp+190h] [rbp+90h]
  int v54; // [rsp+194h] [rbp+94h]
  unsigned int v55; // [rsp+198h] [rbp+98h]
  struct tagRECT rc; // [rsp+1B0h] [rbp+B0h] BYREF
  wchar_t Buffer[140]; // [rsp+1D0h] [rbp+D0h] BYREF
  unsigned __int16 *v58; // [rsp+2E8h] [rbp+1E8h]

  CPrintInfo::CPrintInfo((CPrintInfo *)&v51);
  if ( LOWORD(CWnd::GetCurrentMessage()->wParam) == 0xE108 )
  {
    v2 = *(_QWORD *)(*((_QWORD *)AfxGetModuleState() + 1) + 328LL);
    if ( v2 )
    {
      if ( *(_DWORD *)(v2 + 20) == 3 )
      {
        DCW = CreateDCW(*(LPCWSTR *)(v2 + 40), *(LPCWSTR *)(v2 + 32), *(LPCWSTR *)(v2 + 48), 0);
        *(_QWORD *)(*(_QWORD *)(v51 + 192) + 32LL) = DCW;
        if ( !*(_QWORD *)(*(_QWORD *)(v51 + 192) + 32LL) )
        {
          AfxMessageBox(0xF106u, 0, 0xFFFFFFFF);
          goto LABEL_96;
        }
      }
    }
    v53 = 1;
  }
  if ( !(*(unsigned int (__fastcall **)(CView *, __int64 *))(*(_QWORD *)this + 504LL))(this, &v51) )
    goto LABEL_96;
  v39 = &CDC::`vftable';
  *(_OWORD *)hdc = 0;
  v41 = 0;
  v4 = _afxPchNil;
  v5 = (WCHAR *)_afxPchNil;
  v42 = _afxPchNil;
  if ( (*(_BYTE *)(*(_QWORD *)(v51 + 192) + 40LL) & 0x20) != 0 && !v52 )
  {
    CString::CString((CString *)&v37, (const unsigned __int16 *)0xF045);
    CString::CString((CString *)&v43, (const unsigned __int16 *)0xF046);
    CString::CString((CString *)&Format, (const unsigned __int16 *)0xF047);
    CString::CString((CString *)&v38, (const unsigned __int16 *)0xF048);
    CFileDialog::CFileDialog((CFileDialog *)Buffer, 0, v37, v43, 6u, Format, 0);
    v58 = v38;
    if ( CFileDialog::DoModal((CFileDialog *)Buffer) != 1 )
    {
      (*(void (__fastcall **)(CView *, void ***, __int64 *))(*(_QWORD *)this + 528LL))(this, &v39, &v51);
      CFileDialog::~CFileDialog((CFileDialog *)Buffer);
      CString::~CString((CString *)&v38);
      CString::~CString((CString *)&Format);
      CString::~CString((CString *)&v43);
      p_lpString = (CString *)&v37;
LABEL_95:
      CString::~CString(p_lpString);
      CString::~CString((CString *)&v42);
      CDC::~CDC((CDC *)&v39);
      goto LABEL_96;
    }
    PathName = CFileDialog::GetPathName(Buffer, &v44);
    CString::operator=(&v42, PathName);
    CString::~CString((CString *)&v44);
    CFileDialog::~CFileDialog((CFileDialog *)Buffer);
    CString::~CString((CString *)&v38);
    CString::~CString((CString *)&Format);
    CString::~CString((CString *)&v43);
    CString::~CString((CString *)&v37);
    v5 = (WCHAR *)v42;
    v4 = _afxPchNil;
  }
  lpString = v4;
  v8 = *((_QWORD *)this + 16);
  if ( v8 )
  {
    CString::operator=(&lpString, v8 + 64);
  }
  else
  {
    if ( !CWnd::GetParentFrame(this) )
      AfxThrowInvalidArgException();
    ParentFrame = CWnd::GetParentFrame(this);
    CWnd::GetWindowTextW(ParentFrame, (struct CString *)&lpString);
  }
  v10 = lpString;
  if ( *((int *)lpString - 2) > 31 )
  {
    CString::ReleaseBuffer((CString *)&lpString, 31);
    v10 = lpString;
  }
  *(_QWORD *)&v45.cbSize = 40;
  memset(&v45.lpszOutput, 0, 24);
  v45.lpszDocName = v10;
  v38 = (unsigned __int16 *)_afxPchNil;
  v11 = v5 - 6;
  if ( *((_DWORD *)v5 - 2) )
  {
    v45.lpszOutput = v5;
    v14 = CString::GetBuffer((CString *)&v38, 260);
    AfxGetFileTitle(v5, v14, 0x104u);
    v13 = 61513;
  }
  else
  {
    PortName = CPrintDialog::GetPortName(v51, &v37);
    CString::operator=(&v38, PortName);
    if ( v37 - 6 != (unsigned __int16 *)&_afxInitData && _InterlockedDecrement((volatile signed __int32 *)v37 - 3) <= 0 )
      free(v37 - 6);
    v13 = 61504;
  }
  if ( !v52 )
  {
    CDC::Attach((CDC *)&v39, *(HDC *)(*(_QWORD *)(v51 + 192) + 32LL));
    v41 = 1;
  }
  if ( !hdc[1] )
    AfxThrowInvalidArgException();
  (*(void (__fastcall **)(CView *, void ***, __int64 *))(*(_QWORD *)this + 512LL))(this, &v39, &v51);
  if ( !v52 )
    SetAbortProc(hdc[0], AfxAbortProc);
  MainWnd = AfxGetMainWnd();
  CWnd::EnableWindow(MainWnd, 0);
  CWnd::CWnd((CWnd *)v46);
  memset_0(v50, 0, sizeof(v50));
  v46[0] = &CPrintingDialog::`vftable';
  CDialog::Create((CDialog *)v46, (LPCWSTR)0x7802, this);
  *(_DWORD *)(CProcessLocal<_AFX_WIN_STATE>::GetData() + 20) = 0;
  v16 = (wchar_t *)_afxPchNil;
  Format = (wchar_t *)_afxPchNil;
  if ( v48 )
    (*(void (__fastcall **)(__int64, __int64, LPCWSTR))(*(_QWORD *)v48 + 280LL))(v48, 201, lpString);
  else
    SetDlgItemTextW(hDlg, 201, lpString);
  v17 = *(const WCHAR **)CPrintDialog::GetDeviceName(v51, &v37);
  if ( v48 )
    (*(void (__fastcall **)(__int64, __int64, const WCHAR *))(*(_QWORD *)v48 + 280LL))(v48, 202, v17);
  else
    SetDlgItemTextW(hDlg, 202, v17);
  if ( v37 - 6 != (unsigned __int16 *)&_afxInitData && _InterlockedDecrement((volatile signed __int32 *)v37 - 3) <= 0 )
    free(v37 - 6);
  v18 = v38;
  v44 = v38;
  if ( (unsigned int)AfxLoadString(v13, Buffer, 0x100u) )
  {
    AfxFormatStrings((struct CString *)&Format, Buffer, (const unsigned __int16 *const *)&v44, 1);
    v16 = Format;
  }
  if ( v48 )
    (*(void (__fastcall **)(__int64, __int64, wchar_t *))(*(_QWORD *)v48 + 280LL))(v48, 203, v16);
  else
    SetDlgItemTextW(hDlg, 203, v16);
  if ( v49 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v49 + 336LL))(v49, 5);
  else
    ShowWindow(hDlg, 5);
  UpdateWindow(hDlg);
  if ( v52 || StartDocW(hdc[0], &v45) != -1 )
  {
    v23 = *(unsigned __int16 **)(v51 + 192);
    v24 = v23[24];
    v25 = v24;
    if ( v23[23] >= v24 )
      v25 = v23[23];
    v26 = v23[25];
    v27 = v26;
    if ( v25 <= v26 )
      v27 = v25;
    if ( v23[22] >= v24 )
      v24 = v23[22];
    if ( v24 <= v26 )
      v26 = v24;
    v28 = v27 < v26 ? -1 : 1;
    v29 = 0xFFFF;
    if ( v27 != 0xFFFF )
      v29 = v28 + v27;
    CString::LoadStringW((CString *)&Format, 0xF043u);
    v30 = 0;
    if ( v52 )
    {
      (*(void (__fastcall **)(CView *, void ***, __int64 *))(*(_QWORD *)this + 456LL))(this, &v39, &v51);
      (*(void (__fastcall **)(CView *, void ***, __int64 *))(*(_QWORD *)this + 520LL))(this, &v39, &v51);
    }
    else
    {
      while ( 1 )
      {
        v55 = v26;
        if ( v26 == v29 )
          break;
        (*(void (__fastcall **)(CView *, void ***, __int64 *))(*(_QWORD *)this + 456LL))(this, &v39, &v51);
        if ( !v54 )
          break;
        v31 = swprintf_s(Buffer, 0x50u, Format, v55);
        if ( v31 < 0 || v31 == 80 )
          Buffer[79] = 0;
        CWnd::SetDlgItemTextW((CWnd *)v46, 204, Buffer);
        yBottom = GetDeviceCaps(hdc[1], 10);
        DeviceCaps = GetDeviceCaps(hdc[1], 8);
        SetRect(&rc, 0, 0, DeviceCaps, yBottom);
        DPtoLP(hdc[1], (LPPOINT)&rc, 2);
        if ( StartPage(hdc[0]) < 0 )
          goto LABEL_89;
        if ( dword_180131A4C )
          (*(void (__fastcall **)(CView *, void ***, __int64 *))(*(_QWORD *)this + 456LL))(this, &v39, &v51);
        (*(void (__fastcall **)(CView *, void ***, __int64 *))(*(_QWORD *)this + 520LL))(this, &v39, &v51);
        if ( EndPage(hdc[0]) < 0 || !AfxAbortProc(hdc[0], 0) )
        {
LABEL_89:
          v30 = 1;
          break;
        }
        v26 = v28 + v55;
      }
    }
    if ( !v52 )
    {
      if ( v30 )
        AbortDoc(hdc[0]);
      else
        EndDoc(hdc[0]);
    }
    v34 = AfxGetMainWnd();
    CWnd::EnableWindow(v34, 1);
    (*(void (__fastcall **)(CView *, void ***, __int64 *))(*(_QWORD *)this + 528LL))(this, &v39, &v51);
    CWnd::DestroyWindow((CWnd *)v46);
    CDC::Detach((CDC *)&v39);
    CString::~CString((CString *)&Format);
    v46[0] = &CPrintingDialog::`vftable';
    CDialog::~CDialog((CDialog *)v46);
    CString::~CString((CString *)&v38);
    p_lpString = (CString *)&lpString;
    goto LABEL_95;
  }
  v19 = AfxGetMainWnd();
  CWnd::EnableWindow(v19, 1);
  (*(void (__fastcall **)(CView *, void ***, __int64 *))(*(_QWORD *)this + 528LL))(this, &v39, &v51);
  CWnd::DestroyWindow((CWnd *)v46);
  CDC::Detach((CDC *)&v39);
  AfxMessageBox(0xF106u, 0, 0xFFFFFFFF);
  v20 = v16 - 6;
  if ( v16 - 6 != (wchar_t *)&_afxInitData && _InterlockedDecrement((volatile signed __int32 *)v20) <= 0 )
    free(v20);
  v46[0] = &CPrintingDialog::`vftable';
  CDialog::~CDialog((CDialog *)v46);
  v21 = v18 - 6;
  if ( v18 - 6 != (unsigned __int16 *)&_afxInitData && _InterlockedDecrement((volatile signed __int32 *)v21) <= 0 )
    free(v21);
  if ( lpString - 6 != (LPCWSTR)&_afxInitData && _InterlockedDecrement((volatile signed __int32 *)lpString - 3) <= 0 )
    free((void *)(lpString - 6));
  if ( v11 != (WCHAR *)&_afxInitData && _InterlockedDecrement((volatile signed __int32 *)v11) <= 0 )
    free(v11);
  v39 = &CDC::`vftable';
  if ( hdc[0] )
  {
    v22 = CDC::Detach((CDC *)&v39);
    DeleteDC(v22);
  }
  v39 = &CObject::`vftable';
LABEL_96:
  CPrintInfo::~CPrintInfo((CPrintInfo *)&v51);
}

```

## disassembly

```asm
0x180007290  push    rbp
0x180007292  push    rbx
0x180007293  push    rsi
0x180007294  push    rdi
0x180007295  push    r12
0x180007297  push    r13
0x180007299  push    r14
0x18000729b  push    r15
0x18000729d  lea     rbp, [rsp-4D8h]
0x1800072a5  sub     rsp, 5D8h
0x1800072ac  mov     rax, cs:__security_cookie
0x1800072b3  xor     rax, rsp
0x1800072b6  mov     [rbp+510h+var_50], rax
0x1800072bd  mov     rdi, rcx
0x1800072c0  xor     r12d, r12d
0x1800072c3  lea     rcx, [rbp+510h+var_490]; this
0x1800072ca  call    ??0CPrintInfo@@QEAA@XZ; CPrintInfo::CPrintInfo(void)
0x1800072cf  nop
0x1800072d0  call    ?GetCurrentMessage@CWnd@@KAPEBUtagMSG@@XZ; CWnd::GetCurrentMessage(void)
0x1800072d5  mov     ecx, 0E108h
0x1800072da  cmp     [rax+10h], cx
0x1800072de  jnz     short loc_180007355
0x1800072e0  call    ?AfxGetModuleState@@YAPEAVAFX_MODULE_STATE@@XZ; AfxGetModuleState(void)
0x1800072e5  mov     rcx, [rax+8]
0x1800072e9  mov     rcx, [rcx+148h]
0x1800072f0  test    rcx, rcx
0x1800072f3  jz      short loc_18000734B
0x1800072f5  cmp     dword ptr [rcx+14h], 3
0x1800072f9  jnz     short loc_18000734B
0x1800072fb  xor     r9d, r9d; pdm
0x1800072fe  mov     r8, [rcx+30h]; pszPort
0x180007302  mov     rdx, [rcx+20h]; pwszDevice
0x180007306  mov     rcx, [rcx+28h]; pwszDriver
0x18000730a  call    cs:__imp_CreateDCW
0x180007310  mov     rcx, [rbp+510h+var_490]
0x180007317  mov     rdx, [rcx+0C0h]
0x18000731e  mov     [rdx+20h], rax
0x180007322  mov     rax, [rbp+510h+var_490]
0x180007329  mov     rcx, [rax+0C0h]
0x180007330  cmp     [rcx+20h], r12
0x180007334  jnz     short loc_18000734B
0x180007336  or      r8d, 0FFFFFFFFh; unsigned int
0x18000733a  xor     edx, edx; unsigned int
0x18000733c  mov     ecx, 0F106h; uID
0x180007341  call    ?AfxMessageBox@@YAHIII@Z; AfxMessageBox(uint,uint,uint)
0x180007346  jmp     loc_180007C47
0x18000734b  mov     [rbp+510h+var_480], 1
0x180007355  mov     rax, [rdi]
0x180007358  lea     rdx, [rbp+510h+var_490]
0x18000735f  mov     rcx, rdi
0x180007362  mov     rax, [rax+1F8h]
0x180007369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000736e  test    eax, eax
0x180007370  jz      loc_180007C47
0x180007376  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x18000737d  mov     [rsp+610h+var_5B0], rax
0x180007382  xorps   xmm0, xmm0
0x180007385  movdqu  xmmword ptr [rsp+610h+hdc], xmm0
0x18000738b  mov     [rsp+610h+var_598], r12d
0x180007390  mov     rdx, cs:?_afxPchNil@@3PEBGEB; ushort const * const _afxPchNil
0x180007397  mov     rbx, rdx
0x18000739a  mov     [rbp+510h+var_590], rdx
0x18000739e  mov     rax, [rbp+510h+var_490]
0x1800073a5  mov     rcx, [rax+0C0h]
0x1800073ac  test    byte ptr [rcx+28h], 20h
0x1800073b0  jz      loc_18000750F
0x1800073b6  cmp     [rbp+510h+var_488], r12d
0x1800073bd  jnz     loc_18000750F
0x1800073c3  mov     edx, 0F045h; unsigned __int16 *
0x1800073c8  lea     rcx, [rsp+610h+var_5C0]; this
0x1800073cd  call    ??0CString@@QEAA@PEBG@Z; CString::CString(ushort const *)
0x1800073d2  nop
0x1800073d3  mov     edx, 0F046h; unsigned __int16 *
0x1800073d8  lea     rcx, [rbp+510h+var_588]; this
0x1800073dc  call    ??0CString@@QEAA@PEBG@Z; CString::CString(ushort const *)
0x1800073e1  nop
0x1800073e2  mov     edx, 0F047h; unsigned __int16 *
0x1800073e7  lea     rcx, [rsp+610h+Format]; this
0x1800073ec  call    ??0CString@@QEAA@PEBG@Z; CString::CString(ushort const *)
0x1800073f1  nop
0x1800073f2  mov     edx, 0F048h; unsigned __int16 *
0x1800073f7  lea     rcx, [rsp+610h+var_5B8]; this
0x1800073fc  call    ??0CString@@QEAA@PEBG@Z; CString::CString(ushort const *)
0x180007401  nop
0x180007402  mov     [rsp+610h+var_5E0], r12; struct CWnd *
0x180007407  mov     rax, [rsp+610h+Format]
0x18000740c  mov     [rsp+610h+var_5E8], rax; unsigned __int16 *
0x180007411  mov     [rsp+610h+yBottom], 6; unsigned int
0x180007419  mov     r9, [rbp+510h+var_588]; unsigned __int16 *
0x18000741d  mov     r8, [rsp+610h+var_5C0]; unsigned __int16 *
0x180007422  xor     edx, edx; int
0x180007424  lea     rcx, [rbp+510h+Buffer]; this
0x18000742b  call    ??0CFileDialog@@QEAA@HPEBG0K0PEAVCWnd@@@Z; CFileDialog::CFileDialog(int,ushort const *,ushort const *,ulong,ushort const *,CWnd *)
0x180007430  nop
0x180007431  mov     rax, [rsp+610h+var_5B8]
0x180007436  mov     [rbp+510h+var_328], rax
0x18000743d  lea     rcx, [rbp+510h+Buffer]; this
0x180007444  call    ?DoModal@CFileDialog@@UEAA_JXZ; CFileDialog::DoModal(void)
0x180007449  cmp     rax, 1
0x18000744d  jz      short loc_1800074A5
0x18000744f  mov     rax, [rdi]
0x180007452  lea     r8, [rbp+510h+var_490]
0x180007459  lea     rdx, [rsp+610h+var_5B0]
0x18000745e  mov     rcx, rdi
0x180007461  mov     rax, [rax+210h]
0x180007468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000746d  nop
0x18000746e  lea     rcx, [rbp+510h+Buffer]; this
0x180007475  call    ??1CFileDialog@@UEAA@XZ; CFileDialog::~CFileDialog(void)
0x18000747a  nop
0x18000747b  lea     rcx, [rsp+610h+var_5B8]; this
0x180007480  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x180007485  nop
0x180007486  lea     rcx, [rsp+610h+Format]; this
0x18000748b  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x180007490  nop
0x180007491  lea     rcx, [rbp+510h+var_588]; this
0x180007495  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x18000749a  nop
0x18000749b  lea     rcx, [rsp+610h+var_5C0]
0x1800074a0  jmp     loc_180007C2C
0x1800074a5  lea     rdx, [rbp+510h+var_580]
0x1800074a9  lea     rcx, [rbp+510h+Buffer]
0x1800074b0  call    ?GetPathName@CFileDialog@@QEBA?AVCString@@XZ; CFileDialog::GetPathName(void)
0x1800074b5  nop
0x1800074b6  mov     rdx, rax
0x1800074b9  lea     rcx, [rbp+510h+var_590]
0x1800074bd  call    ??4CString@@QEAAAEBV0@AEBV0@@Z; CString::operator=(CString const &)
0x1800074c2  nop
0x1800074c3  lea     rcx, [rbp+510h+var_580]; this
0x1800074c7  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x1800074cc  nop
0x1800074cd  lea     rcx, [rbp+510h+Buffer]; this
0x1800074d4  call    ??1CFileDialog@@UEAA@XZ; CFileDialog::~CFileDialog(void)
0x1800074d9  nop
0x1800074da  lea     rcx, [rsp+610h+var_5B8]; this
0x1800074df  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x1800074e4  nop
0x1800074e5  lea     rcx, [rsp+610h+Format]; this
0x1800074ea  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x1800074ef  nop
0x1800074f0  lea     rcx, [rbp+510h+var_588]; this
0x1800074f4  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x1800074f9  nop
0x1800074fa  lea     rcx, [rsp+610h+var_5C0]; this
0x1800074ff  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x180007504  mov     rbx, [rbp+510h+var_590]
0x180007508  mov     rdx, cs:?_afxPchNil@@3PEBGEB; ushort const * const _afxPchNil
0x18000750f  mov     [rsp+610h+lpString], rdx
0x180007514  mov     rdx, [rdi+80h]
0x18000751b  test    rdx, rdx
0x18000751e  jz      short loc_180007530
0x180007520  add     rdx, 40h ; '@'
0x180007524  lea     rcx, [rsp+610h+lpString]
0x180007529  call    ??4CString@@QEAAAEBV0@AEBV0@@Z; CString::operator=(CString const &)
0x18000752e  jmp     short loc_180007558
0x180007530  mov     rcx, rdi; this
0x180007533  call    ?GetParentFrame@CWnd@@QEBAPEAVCFrameWnd@@XZ; CWnd::GetParentFrame(void)
0x180007538  test    rax, rax
0x18000753b  jnz     short loc_180007543
0x18000753d  call    ?AfxThrowInvalidArgException@@YAXXZ; AfxThrowInvalidArgException(void)
0x180007543  mov     rcx, rdi; this
0x180007546  call    ?GetParentFrame@CWnd@@QEBAPEAVCFrameWnd@@XZ; CWnd::GetParentFrame(void)
0x18000754b  lea     rdx, [rsp+610h+lpString]; struct CString *
0x180007550  mov     rcx, rax; this
0x180007553  call    ?GetWindowTextW@CWnd@@QEBAXAEAVCString@@@Z; CWnd::GetWindowTextW(CString &)
0x180007558  mov     edx, 1Fh; int
0x18000755d  mov     rax, [rsp+610h+lpString]
0x180007562  cmp     [rax-8], edx
0x180007565  jle     short loc_180007576
0x180007567  lea     rcx, [rsp+610h+lpString]; this
0x18000756c  call    ?ReleaseBuffer@CString@@QEAAXH@Z; CString::ReleaseBuffer(int)
0x180007571  mov     rax, [rsp+610h+lpString]
0x180007576  mov     qword ptr [rbp+510h+var_578.cbSize], 28h ; '('
0x18000757e  xorps   xmm0, xmm0
0x180007581  movdqu  xmmword ptr [rbp+510h+var_578.lpszOutput], xmm0
0x180007586  mov     qword ptr [rbp+510h+var_578.fwType], r12
0x18000758a  mov     [rbp+510h+var_578.lpszDocName], rax
0x18000758e  mov     rax, cs:?_afxPchNil@@3PEBGEB; ushort const * const _afxPchNil
0x180007595  mov     [rsp+610h+var_5B8], rax
0x18000759a  lea     rsi, [rbx-0Ch]
0x18000759e  lea     r14, ?_afxInitData@@3PAHA; int near * _afxInitData
0x1800075a5  or      r13d, 0FFFFFFFFh
0x1800075a9  cmp     [rsi+4], r12d
0x1800075ad  jnz     short loc_180007602
0x1800075af  lea     rdx, [rsp+610h+var_5C0]
0x1800075b4  mov     rcx, [rbp+510h+var_490]
0x1800075bb  call    ?GetPortName@CPrintDialog@@QEBA?AVCString@@XZ; CPrintDialog::GetPortName(void)
0x1800075c0  nop
0x1800075c1  mov     rdx, rax
0x1800075c4  lea     rcx, [rsp+610h+var_5B8]
0x1800075c9  call    ??4CString@@QEAAAEBV0@AEBV0@@Z; CString::operator=(CString const &)
0x1800075ce  nop
0x1800075cf  mov     rcx, [rsp+610h+var_5C0]
0x1800075d4  add     rcx, 0FFFFFFFFFFFFFFF4h
0x1800075d8  cmp     rcx, r14
0x1800075db  jz      short loc_1800075FA
0x1800075dd  mov     eax, r13d
0x1800075e0  lock xadd [rcx], eax
0x1800075e4  add     eax, r13d
0x1800075e7  test    eax, eax
0x1800075e9  jg      short loc_1800075FA
0x1800075eb  mov     rcx, [rsp+610h+var_5C0]
0x1800075f0  add     rcx, 0FFFFFFFFFFFFFFF4h; Block
0x1800075f4  call    cs:__imp_free
0x1800075fa  mov     r15d, 0F040h
0x180007600  jmp     short loc_18000762D
0x180007602  mov     [rbp+510h+var_578.lpszOutput], rbx
0x180007606  mov     r14d, 104h
0x18000760c  mov     edx, r14d; int
0x18000760f  lea     rcx, [rsp+610h+var_5B8]; this
0x180007614  call    ?GetBuffer@CString@@QEAAPEAGH@Z; CString::GetBuffer(int)
0x180007619  mov     r8d, r14d; SizeInWords
0x18000761c  mov     rdx, rax; Destination
0x18000761f  mov     rcx, rbx; Source
0x180007622  call    ?AfxGetFileTitle@@YAIPEBGPEAGI@Z; AfxGetFileTitle(ushort const *,ushort *,uint)
0x180007627  mov     r15d, 0F049h
0x18000762d  cmp     [rbp+510h+var_488], r12d
0x180007634  jnz     short loc_18000765A
0x180007636  mov     rax, [rbp+510h+var_490]
0x18000763d  mov     rdx, [rax+0C0h]
0x180007644  mov     rdx, [rdx+20h]; HDC
0x180007648  lea     rcx, [rsp+610h+var_5B0]; this
0x18000764d  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x180007652  mov     [rsp+610h+var_598], 1
0x18000765a  cmp     [rsp+610h+hdc+8], r12
0x18000765f  jnz     short loc_180007667
0x180007661  call    ?AfxThrowInvalidArgException@@YAXXZ; AfxThrowInvalidArgException(void)
0x180007667  mov     rax, [rdi]
0x18000766a  lea     r8, [rbp+510h+var_490]
0x180007671  lea     rdx, [rsp+610h+var_5B0]
0x180007676  mov     rcx, rdi
0x180007679  mov     rax, [rax+200h]
0x180007680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007685  cmp     [rbp+510h+var_488], r12d
0x18000768c  jnz     short loc_1800076A0
0x18000768e  lea     rdx, _AfxAbortProc; proc
0x180007695  mov     rcx, [rsp+610h+hdc]; hdc
0x18000769a  call    cs:__imp_SetAbortProc
0x1800076a0  call    ?AfxGetMainWnd@@YAPEAVCWnd@@XZ; AfxGetMainWnd(void)
0x1800076a5  xor     edx, edx; int
0x1800076a7  mov     rcx, rax; this
0x1800076aa  call    ?EnableWindow@CWnd@@QEAAHH@Z; CWnd::EnableWindow(int)
0x1800076af  lea     rcx, [rbp+510h+var_550]; this
0x1800076b3  call    ??0CWnd@@QEAA@XZ; CWnd::CWnd(void)
0x1800076b8  xor     edx, edx; Val
0x1800076ba  lea     r8d, [rdx+40h]; Size
0x1800076be  lea     rcx, [rbp+510h+var_4D0]; void *
0x1800076c2  call    memset_0
0x1800076c7  nop
0x1800076c8  lea     rax, ??_7CPrintingDialog@@6B@; const CPrintingDialog::`vftable'
0x1800076cf  mov     [rbp+510h+var_550], rax
0x1800076d3  mov     r8, rdi; struct CWnd *
0x1800076d6  mov     edx, 7802h; lpName
0x1800076db  lea     rcx, [rbp+510h+var_550]; this
0x1800076df  call    ?Create@CDialog@@QEAAHPEBGPEAVCWnd@@@Z; CDialog::Create(ushort const *,CWnd *)
0x1800076e4  call    ?GetData@?$CProcessLocal@V_AFX_WIN_STATE@@@@QEAAPEAV_AFX_WIN_STATE@@XZ; CProcessLocal<_AFX_WIN_STATE>::GetData(void)
0x1800076e9  mov     [rax+14h], r12d
0x1800076ed  mov     r14, cs:?_afxPchNil@@3PEBGEB; ushort const * const _afxPchNil
0x1800076f4  mov     [rsp+610h+Format], r14
0x1800076f9  mov     r8, [rsp+610h+lpString]; lpString
0x1800076fe  mov     rcx, [rbp+510h+var_4E0]
0x180007702  mov     edx, 0C9h; nIDDlgItem
0x180007707  test    rcx, rcx
0x18000770a  jnz     short loc_180007718
0x18000770c  mov     rcx, [rbp+510h+hDlg]; hDlg
0x180007710  call    cs:__imp_SetDlgItemTextW
0x180007716  jmp     short loc_180007727
0x180007718  mov     rax, [rcx]
0x18000771b  mov     rax, [rax+118h]
0x180007722  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007727  lea     rdx, [rsp+610h+var_5C0]
0x18000772c  mov     rcx, [rbp+510h+var_490]
0x180007733  call    ?GetDeviceName@CPrintDialog@@QEBA?AVCString@@XZ; CPrintDialog::GetDeviceName(void)
0x180007738  nop
0x180007739  mov     r8, [rax]; lpString
0x18000773c  mov     rcx, [rbp+510h+var_4E0]
0x180007740  mov     edx, 0CAh; nIDDlgItem
0x180007745  test    rcx, rcx
0x180007748  jnz     short loc_180007756
0x18000774a  mov     rcx, [rbp+510h+hDlg]; hDlg
0x18000774e  call    cs:__imp_SetDlgItemTextW
0x180007754  jmp     short loc_180007766
0x180007756  mov     rax, [rcx]
0x180007759  mov     rax, [rax+118h]
0x180007760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007765  nop
0x180007766  mov     rcx, [rsp+610h+var_5C0]
0x18000776b  add     rcx, 0FFFFFFFFFFFFFFF4h
0x18000776f  lea     rax, ?_afxInitData@@3PAHA; int near * _afxInitData
0x180007776  cmp     rcx, rax
0x180007779  jz      short loc_180007798
0x18000777b  mov     eax, r13d
0x18000777e  lock xadd [rcx], eax
0x180007782  add     eax, r13d
0x180007785  test    eax, eax
0x180007787  jg      short loc_180007798
0x180007789  mov     rcx, [rsp+610h+var_5C0]
0x18000778e  add     rcx, 0FFFFFFFFFFFFFFF4h; Block
0x180007792  call    cs:__imp_free
  ... truncated ...
```
