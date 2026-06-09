# FrameWindow::OnCreate(tagCREATESTRUCTW *)

- ea: `0x180023660`
- end: `0x180023e15`
- name: `?OnCreate@FrameWindow@@QEAA_JPEAUtagCREATESTRUCTW@@@Z`
- size: `1973`
- prototype: `__int64 __fastcall(FrameWindow *__hidden this, struct tagCREATESTRUCTW *)`
- caller_count: `1`
- callee_count: `20`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002b910`

## callees

- `0x180001800`
- `0x18000193c`
- `0x1800031a4`
- `0x180003858`
- `0x180003880`
- `0x1800039ec`
- `0x180006e00`
- `0x1800075d8`
- `0x180008efc`
- `0x18001e894`
- `0x18001ee28`
- `0x18001fbd8`
- `0x180021174`
- `0x180021e24`
- `0x180023660`
- `0x1800269a4`
- `0x180028a60`
- `0x180029664`
- `0x18002f710`
- `0x180035010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x180023810`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x180023810`
- `GDI32!SetLayout` at `0x18002372f`
- `GDI32!SetLayout` at `0x18002372f`
- `GDI32!CreateSolidBrush` at `0x18002373a`
- `GDI32!CreateSolidBrush` at `0x18002374c`
- `GDI32!CreateSolidBrush` at `0x18002375e`
- `GDI32!CreateSolidBrush` at `0x18002373a`
- `GDI32!CreateSolidBrush` at `0x18002374c`
- `GDI32!CreateSolidBrush` at `0x18002375e`
- `KERNEL32!EnterCriticalSection` at `0x18002377e`
- `KERNEL32!EnterCriticalSection` at `0x18002377e`
- `KERNEL32!LeaveCriticalSection` at `0x1800237b0`
- `KERNEL32!LeaveCriticalSection` at `0x1800237b0`
- `KERNEL32!GetCurrentThreadId` at `0x18002376b`
- `KERNEL32!GetCurrentThreadId` at `0x18002376b`
- `KERNEL32!GetLastError` at `0x1800236bf`
- `KERNEL32!GetLastError` at `0x1800236bf`
- `KERNEL32!SetLastError` at `0x180023699`
- `KERNEL32!SetLastError` at `0x180023709`
- `KERNEL32!SetLastError` at `0x180023699`
- `KERNEL32!SetLastError` at `0x180023709`
- `OLEAUT32!__imp_SysAllocString` at `0x180023c02`
- `OLEAUT32!__imp_SysAllocString` at `0x180023c02`
- `OLEAUT32!__imp_VariantClear` at `0x180023bec`
- `OLEAUT32!__imp_VariantClear` at `0x180023c55`
- `OLEAUT32!__imp_VariantClear` at `0x180023cad`
- `OLEAUT32!__imp_VariantClear` at `0x180023bec`
- `OLEAUT32!__imp_VariantClear` at `0x180023c55`
- `OLEAUT32!__imp_VariantClear` at `0x180023cad`
- `OLEAUT32!__imp_VariantCopy` at `0x180023c2a`
- `OLEAUT32!__imp_VariantCopy` at `0x180023c82`
- `OLEAUT32!__imp_VariantCopy` at `0x180023c2a`
- `OLEAUT32!__imp_VariantCopy` at `0x180023c82`
- `USER32!SendMessageW` at `0x180023b32`
- `USER32!SendMessageW` at `0x180023b6c`
- `USER32!SendMessageW` at `0x180023b8a`
- `USER32!SendMessageW` at `0x180023b32`
- `USER32!SendMessageW` at `0x180023b6c`
- `USER32!SendMessageW` at `0x180023b8a`
- `USER32!SetWindowLongPtrW` at `0x180023701`
- `USER32!SetWindowLongPtrW` at `0x180023701`
- `USER32!GetWindowLongPtrW` at `0x1800236aa`
- `USER32!GetWindowLongPtrW` at `0x180023715`
- `USER32!GetWindowLongPtrW` at `0x1800236aa`
- `USER32!GetWindowLongPtrW` at `0x180023715`
- `USER32!GetWindowLongW` at `0x1800238b0`
- `USER32!GetWindowLongW` at `0x1800238b0`
- `USER32!GetDC` at `0x180023724`
- `USER32!GetDC` at `0x180023724`
- `USER32!MoveWindow` at `0x180023a11`
- `USER32!MoveWindow` at `0x180023a11`
- `USER32!SetWindowPos` at `0x180023d9d`
- `USER32!SetWindowPos` at `0x180023d9d`
- `USER32!RegisterWindowMessageW` at `0x180023ac6`
- `USER32!RegisterWindowMessageW` at `0x180023ac6`
- `USER32!IsWindowVisible` at `0x180023a69`
- `USER32!IsWindowVisible` at `0x180023a69`
- `USER32!GetWindowRect` at `0x180023d6d`
- `USER32!GetWindowRect` at `0x180023d6d`
- `USER32!ShowWindow` at `0x180023a79`
- `USER32!ShowWindow` at `0x180023a85`
- `USER32!ShowWindow` at `0x180023a79`
- `USER32!ShowWindow` at `0x180023a85`
- `USER32!LoadImageW` at `0x180023b18`
- `USER32!LoadImageW` at `0x180023b55`
- `USER32!LoadImageW` at `0x180023b18`
- `USER32!LoadImageW` at `0x180023b55`
- `USER32!EnableWindow` at `0x1800238d4`
- `USER32!EnableWindow` at `0x1800238d4`
- `USER32!ChangeWindowMessageFilterEx` at `0x180023aaf`
- `USER32!ChangeWindowMessageFilterEx` at `0x180023ade`
- `USER32!ChangeWindowMessageFilterEx` at `0x180023af2`
- `USER32!ChangeWindowMessageFilterEx` at `0x180023aaf`
- `USER32!ChangeWindowMessageFilterEx` at `0x180023ade`
- `USER32!ChangeWindowMessageFilterEx` at `0x180023af2`

## string_xrefs

- `0x180023abf`: `WM_F12_PROC_COMMAND`

## pseudocode

```c
__int64 __fastcall FrameWindow::OnCreate(FrameWindow *this, struct tagCREATESTRUCTW *a2)
{
  LONG_PTR WindowLongPtrW; // rax
  unsigned __int64 v5; // rbx
  HDC DC; // rax
  DWORD CurrentThreadId; // ebx
  struct ATL::CAtlModule *v8; // rdi
  int v9; // edx
  int v10; // ecx
  __int64 v11; // rbx
  int v12; // edi
  unsigned int v13; // edi
  bool v14; // sf
  __int64 v15; // rax
  _QWORD *v16; // rdx
  __int64 v17; // r14
  HWND v18; // rcx
  CustomChromeBorders *v19; // rdi
  CustomChromeBorders *v20; // rbx
  volatile signed __int32 *v21; // rdi
  __int64 v22; // rdi
  HWND v23; // rcx
  double v24; // xmm1_8
  int v25; // eax
  UINT v26; // eax
  HANDLE ImageW; // rax
  HANDLE v28; // rax
  F12 *v29; // rcx
  LPARAM v30; // rbx
  UINT v31; // eax
  VARIANTARG *v32; // rbx
  HRESULT v33; // eax
  VARIANTARG *v34; // rbx
  HRESULT v35; // eax
  VARIANTARG **v36; // r8
  VARIANTARG *v37; // rdx
  VARIANTARG *v38; // rcx
  VARIANTARG *v39; // rax
  _QWORD *v40; // rdx
  unsigned __int16 v41; // [rsp+38h] [rbp-61h]
  int v42; // [rsp+38h] [rbp-61h]
  __int64 v43; // [rsp+50h] [rbp-49h] BYREF
  VARIANTARG *pvargDest[2]; // [rsp+58h] [rbp-41h] BYREF
  VARIANTARG *v45; // [rsp+68h] [rbp-31h]
  CustomChromeBorders *v46; // [rsp+70h] [rbp-29h] BYREF
  VARIANTARG pvarg; // [rsp+78h] [rbp-21h] BYREF
  CustomChromeBorders **v48; // [rsp+90h] [rbp-9h]
  struct tagRECT Rect; // [rsp+98h] [rbp-1h] BYREF

  *((_BYTE *)this + 434) = 1;
  SetLastError(0);
  WindowLongPtrW = GetWindowLongPtrW(*((HWND *)this + 1), -20);
  if ( !WindowLongPtrW
    || (WindowLongPtrW & 0x400000) != 0
    && (v5 = WindowLongPtrW & 0xFFFFFFFFFFBFFFFFuLL,
        SetWindowLongPtrW(*((HWND *)this + 1), -20, WindowLongPtrW & 0xFFFFFFFFFFBFFFFFuLL),
        SetLastError(0),
        GetWindowLongPtrW(*((HWND *)this + 1), -20) != v5) )
  {
    if ( GetLastError() )
      return -1;
  }
  DC = GetDC(*((HWND *)this + 1));
  SetLayout(DC, 0);
  *((_QWORD *)this + 32) = CreateSolidBrush(0xFFFFFFu);
  *((_QWORD *)this + 33) = CreateSolidBrush(0x1E1E1Eu);
  *((_QWORD *)this + 34) = CreateSolidBrush(0xB1B1B1u);
  CurrentThreadId = GetCurrentThreadId();
  v8 = ATL::_pAtlModule;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)ATL::_pAtlModule + 24));
  v9 = *((_DWORD *)qword_180050788 + 4);
  if ( v9 <= 0 )
    goto LABEL_10;
  v10 = 0;
  while ( *(_DWORD *)(*(_QWORD *)qword_180050788 + 4LL * v10) != CurrentThreadId )
  {
    if ( ++v10 >= v9 )
      goto LABEL_10;
  }
  if ( v10 == -1 )
  {
LABEL_10:
    v11 = 0;
  }
  else
  {
    if ( v10 < 0 || v10 >= v9 )
    {
      Microsoft::WRL::Details::RaiseException(
        (Microsoft::WRL::Details *)0xC000008CLL,
        v9,
        (unsigned int)qword_180050788);
      goto LABEL_68;
    }
    _mm_lfence();
    v11 = *(_QWORD *)(*((_QWORD *)qword_180050788 + 1) + 8LL * v10);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v8 + 24));
  if ( !v11 )
    return -1;
  v12 = *(_DWORD *)(v11 + 16);
  if ( v12 != *(_DWORD *)(v11 + 20) )
    goto LABEL_23;
  if ( *(_DWORD *)(v11 + 20) )
  {
    v14 = (v12 & 0x40000000) != 0;
    v13 = 2 * v12;
    if ( v14 )
      goto LABEL_26;
  }
  else
  {
    v13 = 1;
  }
  if ( v13 <= 0xFFFFFFFuLL )
  {
    v15 = _o__recalloc(*(_QWORD *)(v11 + 8), v13, 8);
    if ( v15 )
    {
      *(_DWORD *)(v11 + 20) = v13;
      *(_QWORD *)(v11 + 8) = v15;
LABEL_23:
      v16 = (_QWORD *)(*(_QWORD *)(v11 + 8) + 8LL * *(int *)(v11 + 16));
      if ( v16 )
        *v16 = (char *)this + 104;
      ++*(_DWORD *)(v11 + 16);
    }
  }
LABEL_26:
  v17 = *((_QWORD *)this + 1);
  if ( !qword_18004B5E0 )
    qword_18004B5E0 = (__int64)L"STATIC";
  v41 = ATL::_ATL_WNDCLASSINFOW::Register(
          &`ATL::CWindowImpl<CDragOverlayWindow,WTL::CStaticT<ATL::CWindow>,ATL::CWinTraits<1442840576,0>>::GetWndClassInfo'::`2'::wc,
          (__int64 (**)(HWND, unsigned int, unsigned __int64, __int64))this + 26);
  ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<1442840576,0>>::Create(
    (char *)this + 144,
    v17,
    &ATL::CWindow::rcDefault,
    &String,
    1342177280,
    32,
    0,
    v41);
  v18 = (HWND)*((_QWORD *)this + 1);
  *((_QWORD *)this + 28) = v18;
  if ( (GetWindowLongW(v18, -16) & 0x40000) == 0 )
    *((_BYTE *)this + 232) = 0;
  EnableWindow(*((HWND *)this + 19), *((_BYTE *)this + 435) == 0);
  v46 = (CustomChromeBorders *)operator new(0x188u);
  v19 = CustomChromeBorders::CustomChromeBorders(v46, *((HWND *)this + 1), *((_BYTE *)this + 435));
  v20 = (CustomChromeBorders *)operator new(0x18u);
  v46 = v20;
  *(_OWORD *)v20 = 0;
  *((_DWORD *)v20 + 2) = 1;
  *((_DWORD *)v20 + 3) = 1;
  *(_QWORD *)v20 = &std::_Ref_count<CustomChromeBorders>::`vftable';
  *((_QWORD *)v20 + 2) = v19;
  v43 = 0;
  std::_Temporary_owner<CustomChromeBorders>::~_Temporary_owner<CustomChromeBorders>(&v43);
  *((_QWORD *)this + 30) = v19;
  v21 = (volatile signed __int32 *)*((_QWORD *)this + 31);
  *((_QWORD *)this + 31) = v20;
  if ( v21 )
  {
    if ( _InterlockedExchangeAdd(v21 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
      if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
    }
  }
  v22 = *((_QWORD *)this + 1);
  if ( !qword_18004B6E0 )
    qword_18004B6E0 = 0;
  LOWORD(v42) = ATL::_ATL_WNDCLASSINFOW::Register(
                  &`CF12SplitterWindowT<0>::GetWndClassInfo'::`2'::wc,
                  (__int64 (**)(HWND, unsigned int, unsigned __int64, __int64))this + 43);
  ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<1442840576,0>>::Create(
    (char *)this + 280,
    v22,
    &ATL::CWindow::rcDefault,
    0,
    1140850688,
    0,
    349,
    v42);
  v23 = (HWND)*((_QWORD *)this + 36);
  if ( !v23 )
    return -1;
  MoveWindow(v23, 0, 0, 300, 300, 1);
  v24 = *((double *)this + 85);
  *((_DWORD *)this + 99) = (int)(v24 * 120.0);
  v25 = (int)(v24 * 0.0);
  *((_DWORD *)this + 98) = v25;
  *((_DWORD *)this + 100) = v25;
  *((_DWORD *)this + 105) = 4;
  *((_QWORD *)this + 45) = 0;
  WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::UpdateSplitterLayout((char *)this + 352);
  if ( !IsWindowVisible(*((HWND *)this + 44)) )
    ShowWindow(*((HWND *)this + 44), 5);
  ShowWindow(*((HWND *)this + 45), 0);
  if ( *((_DWORD *)this + 97) )
    *((_DWORD *)this + 97) = 0;
  *((_DWORD *)this + 106) = 0;
  WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::UpdateSplitterLayout((char *)this + 352);
  ChangeWindowMessageFilterEx(*((HWND *)this + 1), 0x4Au, 1u, 0);
  v26 = message;
  if ( !message )
  {
    v26 = RegisterWindowMessageW(L"WM_F12_PROC_COMMAND");
    message = v26;
  }
  ChangeWindowMessageFilterEx(*((HWND *)this + 1), v26, 1u, 0);
  ChangeWindowMessageFilterEx(*((HWND *)this + 1), 0x15u, 1u, 0);
  ImageW = LoadImageW(hInst, (LPCWSTR)0x67, 1u, 32, 32, 0);
  if ( ImageW )
    SendMessageW(*((HWND *)this + 1), 0x80u, 1u, (LPARAM)ImageW);
  v28 = LoadImageW(hInst, (LPCWSTR)0x67, 1u, 16, 16, 0);
  if ( v28 )
    SendMessageW(*((HWND *)this + 1), 0x80u, 0, (LPARAM)v28);
  v30 = *((_QWORD *)this + 1);
  v31 = F12::SiteCommandMessage(v29);
  SendMessageW(*((HWND *)this + 75), v31, 0, v30);
  if ( (unsigned int)FrameWindow::CreateHeaderTab(this)
    || (unsigned int)FrameWindow::CreateTabFromId(this, *((unsigned int *)this + 138)) )
  {
    return -1;
  }
  if ( *((_BYTE *)this + 432) && *((_DWORD *)this + 138) != 1 )
  {
    *((_BYTE *)this + 432) = 0;
    FrameWindow::ShowHideConsole(this);
  }
  *(_OWORD *)pvargDest = 0;
  v45 = 0;
  pvarg.vt = 0;
  VariantClear(&pvarg);
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(L"tabSelected");
  if ( !pvarg.llVal )
  {
LABEL_68:
    pvarg.vt = 10;
    pvarg.lVal = -2147024882;
    ATL::AtlThrowImpl(-2147024882);
  }
  v32 = pvargDest[1];
  if ( pvargDest[1] == v45 )
  {
    std::vector<ATL::CComVariant>::_Emplace_reallocate<ATL::CComVariant>(pvargDest, pvargDest[1], &pvarg);
  }
  else
  {
    pvargDest[1]->vt = 0;
    v33 = VariantCopy(v32, &pvarg);
    if ( v33 < 0 )
    {
      v32->vt = 10;
      v32->lVal = v33;
      ATL::AtlThrowImpl(v33);
    }
    ++pvargDest[1];
  }
  VariantClear(&pvarg);
  pvarg.vt = 3;
  pvarg.lVal = *((_DWORD *)this + 138);
  v34 = pvargDest[1];
  if ( pvargDest[1] == v45 )
  {
    std::vector<ATL::CComVariant>::_Emplace_reallocate<ATL::CComVariant>(pvargDest, pvargDest[1], &pvarg);
  }
  else
  {
    pvargDest[1]->vt = 0;
    v35 = VariantCopy(v34, &pvarg);
    if ( v35 < 0 )
    {
      v34->vt = 10;
      v34->lVal = v35;
      ATL::AtlThrowImpl(v35);
    }
    ++pvargDest[1];
  }
  VariantClear(&pvarg);
  v48 = &v46;
  v36 = (VARIANTARG **)operator new(0x18u);
  v37 = v45;
  v45 = 0;
  v38 = pvargDest[1];
  pvargDest[1] = 0;
  v39 = pvargDest[0];
  pvargDest[0] = 0;
  *v36 = v39;
  v36[1] = v38;
  v36[2] = v37;
  v46 = (CustomChromeBorders *)v36;
  v43 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  if ( !(unsigned __int8)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
                           &v43,
                           0) )
    ATL::CSimpleStringT<unsigned short,0>::Empty(&v43);
  FrameWindow::PostPluginMessage(this, 0, &v43, &v46);
  v40 = (_QWORD *)(v43 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v43 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v40 + 8LL))(*v40);
  Rect = 0;
  GetWindowRect(*((HWND *)this + 1), &Rect);
  SetWindowPos(*((HWND *)this + 1), 0, Rect.left, Rect.top, Rect.right - Rect.left, Rect.bottom - Rect.top, 0x234u);
  *((_BYTE *)this + 434) = 0;
  (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)this + 71) + 48LL))(*((_QWORD *)this + 71), 902, 0);
  std::vector<ATL::CComVariant>::~vector<ATL::CComVariant>(pvargDest);
  return 1;
}

```

## disassembly

```asm
0x180023660  push    rbp
0x180023662  push    rbx
0x180023663  push    rsi
0x180023664  push    rdi
0x180023665  push    r12
0x180023667  push    r13
0x180023669  push    r14
0x18002366b  push    r15
0x18002366d  lea     rbp, [rsp-1Fh]
0x180023672  sub     rsp, 0B8h
0x180023679  mov     rax, cs:__security_cookie
0x180023680  xor     rax, rsp
0x180023683  mov     [rbp+57h+var_48], rax
0x180023687  mov     rsi, rcx
0x18002368a  mov     r12d, 1
0x180023690  mov     [rcx+1B2h], r12b
0x180023697  xor     ecx, ecx; dwErrCode
0x180023699  call    cs:__imp_SetLastError
0x18002369f  lea     edi, [r12-15h]
0x1800236a4  mov     edx, edi; nIndex
0x1800236a6  mov     rcx, [rsi+8]; hWnd
0x1800236aa  call    cs:__imp_GetWindowLongPtrW
0x1800236b0  mov     rbx, rax
0x1800236b3  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800236b7  xor     r15d, r15d
0x1800236ba  test    rax, rax
0x1800236bd  jnz     short loc_1800236EC
0x1800236bf  call    cs:__imp_GetLastError
0x1800236c5  test    eax, eax
0x1800236c7  jz      short loc_180023720
0x1800236c9  mov     rax, r13
0x1800236cc  mov     rcx, [rbp+57h+var_48]
0x1800236d0  xor     rcx, rsp; StackCookie
0x1800236d3  call    __security_check_cookie
0x1800236d8  add     rsp, 0B8h
0x1800236df  pop     r15
0x1800236e1  pop     r14
0x1800236e3  pop     r13
0x1800236e5  pop     r12
0x1800236e7  pop     rdi
0x1800236e8  pop     rsi
0x1800236e9  pop     rbx
0x1800236ea  pop     rbp
0x1800236eb  retn
0x1800236ec  bt      rbx, 16h
0x1800236f1  jnb     short loc_180023720
0x1800236f3  btr     rbx, 16h
0x1800236f8  mov     r8, rbx; dwNewLong
0x1800236fb  mov     edx, edi; nIndex
0x1800236fd  mov     rcx, [rsi+8]; hWnd
0x180023701  call    cs:__imp_SetWindowLongPtrW
0x180023707  xor     ecx, ecx; dwErrCode
0x180023709  call    cs:__imp_SetLastError
0x18002370f  mov     edx, edi; nIndex
0x180023711  mov     rcx, [rsi+8]; hWnd
0x180023715  call    cs:__imp_GetWindowLongPtrW
0x18002371b  cmp     rax, rbx
0x18002371e  jnz     short loc_1800236BF
0x180023720  mov     rcx, [rsi+8]; hWnd
0x180023724  call    cs:__imp_GetDC
0x18002372a  xor     edx, edx; l
0x18002372c  mov     rcx, rax; hdc
0x18002372f  call    cs:__imp_SetLayout
0x180023735  mov     ecx, 0FFFFFFh; color
0x18002373a  call    cs:__imp_CreateSolidBrush
0x180023740  mov     [rsi+100h], rax
0x180023747  mov     ecx, 1E1E1Eh; color
0x18002374c  call    cs:__imp_CreateSolidBrush
0x180023752  mov     [rsi+108h], rax
0x180023759  mov     ecx, 0B1B1B1h; color
0x18002375e  call    cs:__imp_CreateSolidBrush
0x180023764  mov     [rsi+110h], rax
0x18002376b  call    cs:__imp_GetCurrentThreadId
0x180023771  mov     ebx, eax
0x180023773  mov     rdi, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18002377a  lea     rcx, [rdi+18h]; lpCriticalSection
0x18002377e  call    cs:__imp_EnterCriticalSection
0x180023784  mov     r8, cs:qword_180050788; unsigned int
0x18002378b  mov     edx, [r8+10h]; int
0x18002378f  test    edx, edx
0x180023791  jle     short loc_1800237A9
0x180023793  mov     ecx, r15d
0x180023796  mov     r9, [r8]
0x180023799  movsxd  rax, ecx
0x18002379c  cmp     [r9+rax*4], ebx
0x1800237a0  jz      short loc_1800237D2
0x1800237a2  add     ecx, r12d
0x1800237a5  cmp     ecx, edx
0x1800237a7  jl      short loc_180023799
0x1800237a9  mov     rbx, r15
0x1800237ac  lea     rcx, [rdi+18h]; lpCriticalSection
0x1800237b0  call    cs:__imp_LeaveCriticalSection
0x1800237b6  test    rbx, rbx
0x1800237b9  jz      loc_1800236C9
0x1800237bf  mov     edi, [rbx+10h]
0x1800237c2  cmp     edi, [rbx+14h]
0x1800237c5  jnz     short loc_180023822
0x1800237c7  cmp     [rbx+14h], r15d
0x1800237cb  jnz     short loc_1800237F7
0x1800237cd  mov     edi, r12d
0x1800237d0  jmp     short loc_1800237FB
0x1800237d2  cmp     ecx, r13d
0x1800237d5  jz      short loc_1800237A9
0x1800237d7  test    ecx, ecx
0x1800237d9  js      loc_180023DE5
0x1800237df  cmp     ecx, edx
0x1800237e1  jge     loc_180023DE5
0x1800237e7  lfence
0x1800237ea  movsxd  rcx, ecx
0x1800237ed  mov     rax, [r8+8]
0x1800237f1  mov     rbx, [rax+rcx*8]
0x1800237f5  jmp     short loc_1800237AC
0x1800237f7  add     edi, edi
0x1800237f9  js      short loc_18002383E
0x1800237fb  mov     edx, edi
0x1800237fd  cmp     rdx, 0FFFFFFFh
0x180023804  ja      short loc_18002383E
0x180023806  mov     r8d, 8
0x18002380c  mov     rcx, [rbx+8]
0x180023810  call    cs:__imp__o__recalloc
0x180023816  test    rax, rax
0x180023819  jz      short loc_18002383E
0x18002381b  mov     [rbx+14h], edi
0x18002381e  mov     [rbx+8], rax
0x180023822  movsxd  rcx, dword ptr [rbx+10h]
0x180023826  mov     rax, [rbx+8]
0x18002382a  lea     rdx, [rax+rcx*8]
0x18002382e  test    rdx, rdx
0x180023831  jz      short loc_18002383A
0x180023833  lea     rax, [rsi+68h]
0x180023837  mov     [rdx], rax
0x18002383a  add     [rbx+10h], r12d
0x18002383e  lea     rdi, [rsi+90h]
0x180023845  mov     r14, [rsi+8]
0x180023849  cmp     cs:qword_18004B5E0, r15
0x180023850  jnz     short loc_180023860
0x180023852  lea     rax, aStatic; "STATIC"
0x180023859  mov     cs:qword_18004B5E0, rax
0x180023860  lea     rdx, [rdi+40h]; __int64 (**)(HWND, unsigned int, unsigned __int64, __int64)
0x180023864  lea     rcx, ?wc@?1??GetWndClassInfo@?$CWindowImpl@VCDragOverlayWindow@@V?$CStaticT@VCWindow@ATL@@@WTL@@V?$CWinTraits@$0FGAAAAAA@$0A@@ATL@@@ATL@@SAAEAU_ATL_WNDCLASSINFOW@3@XZ@4U43@A; this
0x18002386b  call    ?Register@_ATL_WNDCLASSINFOW@ATL@@QEAAGPEAP6A_JPEAUHWND__@@I_K_J@Z@Z; ATL::_ATL_WNDCLASSINFOW::Register(__int64 (**)(HWND__ *,uint,unsigned __int64,__int64))
0x180023870  mov     word ptr [rsp+0F0h+var_B8], ax
0x180023875  mov     qword ptr [rsp+0F0h+uFlags], r15
0x18002387a  mov     [rsp+0F0h+bRepaint], 20h ; ' '
0x180023882  mov     [rsp+0F0h+nHeight], 50000000h
0x18002388a  lea     r9, String
0x180023891  lea     r8, ?rcDefault@CWindow@ATL@@2UtagRECT@@A; tagRECT ATL::CWindow::rcDefault
0x180023898  mov     rdx, r14
0x18002389b  mov     rcx, rdi
0x18002389e  call    ?Create@?$CWindowImplBaseT@VCWindow@ATL@@V?$CWinTraits@$0FGAAAAAA@$0A@@2@@ATL@@QEAAPEAUHWND__@@PEAU3@V_U_RECT@2@PEBGKKV_U_MENUorID@2@GPEAX@Z; ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<1442840576,0>>::Create(HWND__ *,ATL::_U_RECT,ushort const *,ulong,ulong,ATL::_U_MENUorID,ushort,void *)
0x1800238a3  mov     rcx, [rsi+8]; hWnd
0x1800238a7  mov     [rdi+50h], rcx
0x1800238ab  mov     edx, 0FFFFFFF0h; nIndex
0x1800238b0  call    cs:__imp_GetWindowLongW
0x1800238b6  bt      eax, 12h
0x1800238ba  jb      short loc_1800238C0
0x1800238bc  mov     [rdi+58h], r15b
0x1800238c0  mov     edx, r15d
0x1800238c3  cmp     [rsi+1B3h], r15b
0x1800238ca  setz    dl; bEnable
0x1800238cd  mov     rcx, [rsi+98h]; hWnd
0x1800238d4  call    cs:__imp_EnableWindow
0x1800238da  mov     ecx, 188h; Size
0x1800238df  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800238e4  mov     [rbp+57h+var_80], rax
0x1800238e8  mov     r8b, [rsi+1B3h]; bool
0x1800238ef  mov     rdx, [rsi+8]; HWND
0x1800238f3  mov     rcx, rax; this
0x1800238f6  call    ??0CustomChromeBorders@@QEAA@PEAUHWND__@@_N@Z; CustomChromeBorders::CustomChromeBorders(HWND__ *,bool)
0x1800238fb  mov     rdi, rax
0x1800238fe  mov     [rbp+57h+var_A0], rax
0x180023902  mov     r14d, 18h
0x180023908  mov     ecx, r14d; Size
0x18002390b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180023910  mov     rbx, rax
0x180023913  mov     [rbp+57h+var_80], rax
0x180023917  xorps   xmm0, xmm0
0x18002391a  movups  xmmword ptr [rax], xmm0
0x18002391d  mov     [rax+8], r12d
0x180023921  mov     [rax+0Ch], r12d
0x180023925  lea     rax, ??_7?$_Ref_count@VCustomChromeBorders@@@std@@6B@; const std::_Ref_count<CustomChromeBorders>::`vftable'
0x18002392c  mov     [rbx], rax
0x18002392f  mov     [rbx+10h], rdi
0x180023933  mov     [rbp+57h+var_A0], r15
0x180023937  lea     rcx, [rbp+57h+var_A0]
0x18002393b  call    ??1?$_Temporary_owner@VCustomChromeBorders@@@std@@QEAA@XZ; std::_Temporary_owner<CustomChromeBorders>::~_Temporary_owner<CustomChromeBorders>(void)
0x180023940  mov     [rsi+0F0h], rdi
0x180023947  mov     rdi, [rsi+0F8h]
0x18002394e  mov     [rsi+0F8h], rbx
0x180023955  test    rdi, rdi
0x180023958  jz      short loc_180023991
0x18002395a  mov     eax, r13d
0x18002395d  lock xadd [rdi+8], eax
0x180023962  add     eax, r13d
0x180023965  jnz     short loc_180023991
0x180023967  mov     rax, [rdi]
0x18002396a  mov     rcx, rdi
0x18002396d  mov     rax, [rax]
0x180023970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023975  mov     eax, r13d
0x180023978  lock xadd [rdi+0Ch], eax
0x18002397d  add     eax, r13d
0x180023980  jnz     short loc_180023991
0x180023982  mov     rax, [rdi]
0x180023985  mov     rcx, rdi
0x180023988  mov     rax, [rax+8]
0x18002398c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023991  lea     rbx, [rsi+118h]
0x180023998  mov     rdi, [rsi+8]
0x18002399c  cmp     cs:qword_18004B6E0, r15
0x1800239a3  jnz     short loc_1800239AC
0x1800239a5  mov     cs:qword_18004B6E0, r15
0x1800239ac  lea     rdx, [rbx+40h]; __int64 (**)(HWND, unsigned int, unsigned __int64, __int64)
0x1800239b0  lea     rcx, ?wc@?1??GetWndClassInfo@?$CF12SplitterWindowT@$0A@@@SAAEAU_ATL_WNDCLASSINFOW@ATL@@XZ@4U34@A; this
0x1800239b7  call    ?Register@_ATL_WNDCLASSINFOW@ATL@@QEAAGPEAP6A_JPEAUHWND__@@I_K_J@Z@Z; ATL::_ATL_WNDCLASSINFOW::Register(__int64 (**)(HWND__ *,uint,unsigned __int64,__int64))
0x1800239bc  mov     word ptr [rsp+0F0h+var_B8], ax
0x1800239c1  mov     qword ptr [rsp+0F0h+uFlags], 15Dh
0x1800239ca  mov     [rsp+0F0h+bRepaint], r15d
0x1800239cf  mov     [rsp+0F0h+nHeight], 44000000h
0x1800239d7  xor     r9d, r9d
0x1800239da  lea     r8, ?rcDefault@CWindow@ATL@@2UtagRECT@@A; tagRECT ATL::CWindow::rcDefault
0x1800239e1  mov     rdx, rdi
0x1800239e4  mov     rcx, rbx
0x1800239e7  call    ?Create@?$CWindowImplBaseT@VCWindow@ATL@@V?$CWinTraits@$0FGAAAAAA@$0A@@2@@ATL@@QEAAPEAUHWND__@@PEAU3@V_U_RECT@2@PEBGKKV_U_MENUorID@2@GPEAX@Z; ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<1442840576,0>>::Create(HWND__ *,ATL::_U_RECT,ushort const *,ulong,ulong,ATL::_U_MENUorID,ushort,void *)
0x1800239ec  mov     rcx, [rsi+120h]; hWnd
0x1800239f3  test    rcx, rcx
0x1800239f6  jz      loc_1800236C9
0x1800239fc  mov     [rsp+0F0h+bRepaint], r12d; bRepaint
0x180023a01  mov     r9d, 12Ch; nWidth
0x180023a07  mov     [rsp+0F0h+nHeight], r9d; nHeight
0x180023a0c  xor     r8d, r8d; Y
0x180023a0f  xor     edx, edx; X
0x180023a11  call    cs:__imp_MoveWindow
0x180023a17  movsd   xmm1, qword ptr [rsi+2A8h]
0x180023a1f  movaps  xmm0, xmm1
0x180023a22  mulsd   xmm0, cs:__real@405e000000000000
0x180023a2a  cvttsd2si eax, xmm0
0x180023a2e  mov     [rsi+18Ch], eax
0x180023a34  mulsd   xmm1, cs:__real@0000000000000000
0x180023a3c  cvttsd2si eax, xmm1
0x180023a40  mov     [rsi+188h], eax
0x180023a46  mov     [rsi+190h], eax
0x180023a4c  lea     rbx, [rsi+160h]
0x180023a53  mov     dword ptr [rbx+44h], 4
0x180023a5a  mov     [rbx+8], r15
0x180023a5e  mov     rcx, rbx
0x180023a61  call    ?UpdateSplitterLayout@?$CSplitterImpl@V?$CF12SplitterWindowT@$0A@@@$0A@@WTL@@QEAAXXZ; WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::UpdateSplitterLayout(void)
0x180023a66  mov     rcx, [rbx]; hWnd
0x180023a69  call    cs:__imp_IsWindowVisible
0x180023a6f  test    eax, eax
0x180023a71  jnz     short loc_180023A7F
0x180023a73  lea     edx, [rax+5]; nCmdShow
0x180023a76  mov     rcx, [rbx]; hWnd
0x180023a79  call    cs:__imp_ShowWindow
0x180023a7f  xor     edx, edx; nCmdShow
0x180023a81  mov     rcx, [rbx+8]; hWnd
0x180023a85  call    cs:__imp_ShowWindow
0x180023a8b  cmp     [rbx+24h], r15d
0x180023a8f  jz      short loc_180023A95
0x180023a91  mov     [rbx+24h], r15d
0x180023a95  mov     [rbx+48h], r15d
0x180023a99  mov     rcx, rbx
0x180023a9c  call    ?UpdateSplitterLayout@?$CSplitterImpl@V?$CF12SplitterWindowT@$0A@@@$0A@@WTL@@QEAAXXZ; WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::UpdateSplitterLayout(void)
0x180023aa1  xor     r9d, r9d; pChangeFilterStruct
0x180023aa4  mov     r8d, r12d; action
0x180023aa7  lea     edx, [r9+4Ah]; message
0x180023aab  mov     rcx, [rsi+8]; hwnd
0x180023aaf  call    cs:__imp_ChangeWindowMessageFilterEx
0x180023ab5  mov     eax, cs:message
0x180023abb  test    eax, eax
0x180023abd  jnz     short loc_180023AD2
0x180023abf  lea     rcx, aWmF12ProcComma; "WM_F12_PROC_COMMAND"
0x180023ac6  call    cs:__imp_RegisterWindowMessageW
0x180023acc  mov     cs:message, eax
0x180023ad2  xor     r9d, r9d; pChangeFilterStruct
0x180023ad5  mov     r8d, r12d; action
0x180023ad8  mov     edx, eax; message
0x180023ada  mov     rcx, [rsi+8]; hwnd
0x180023ade  call    cs:__imp_ChangeWindowMessageFilterEx
0x180023ae4  xor     r9d, r9d; pChangeFilterStruct
0x180023ae7  mov     r8d, r12d; action
0x180023aea  lea     edx, [r9+15h]; message
0x180023aee  mov     rcx, [rsi+8]; hwnd
0x180023af2  call    cs:__imp_ChangeWindowMessageFilterEx
0x180023af8  mov     [rsp+0F0h+bRepaint], r15d; fuLoad
0x180023afd  mov     r9d, 20h ; ' '; cx
0x180023b03  mov     [rsp+0F0h+nHeight], r9d; cy
0x180023b08  mov     r8d, r12d; type
0x180023b0b  lea     edi, [r9+47h]
0x180023b0f  mov     edx, edi; name
0x180023b11  mov     rcx, cs:hInst; hInst
0x180023b18  call    cs:__imp_LoadImageW
0x180023b1e  lea     ebx, [rdi+19h]
0x180023b21  test    rax, rax
0x180023b24  jz      short loc_180023B38
0x180023b26  mov     r9, rax; lParam
0x180023b29  mov     r8, r12; wParam
0x180023b2c  mov     edx, ebx; Msg
0x180023b2e  mov     rcx, [rsi+8]; hWnd
0x180023b32  call    cs:__imp_SendMessageW
  ... truncated ...
```
