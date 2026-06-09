# FrameWindow::_ProcessWindowMessage(HWND__ *,uint,unsigned __int64,__int64,__int64 &,ulong)

- ea: `0x18002b910`
- end: `0x18002c49c`
- name: `?_ProcessWindowMessage@FrameWindow@@QEAAHPEAUHWND__@@I_K_JAEA_JK@Z`
- size: `2956`
- prototype: `_BOOL8 __fastcall(FrameWindow *this, struct tagCREATESTRUCTW *, unsigned __int64, char *, __int64 psz, __int64 *, unsigned int)`
- caller_count: `1`
- callee_count: `51`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180027d90`

## callees

- `0x180001800`
- `0x18000193c`
- `0x180001c84`
- `0x180002dd4`
- `0x180003858`
- `0x180003880`
- `0x1800045b4`
- `0x180005e44`
- `0x1800120e4`
- `0x180020528`
- `0x180020bac`
- `0x180022204`
- `0x1800227a0`
- `0x180022b8c`
- `0x180022f44`
- `0x18002319c`
- `0x180023220`
- `0x1800232e8`
- `0x1800234d8`
- `0x180023598`
- `0x180023660`
- `0x180023e1c`
- `0x180023f00`
- `0x180024010`
- `0x1800241cc`
- `0x180024ac4`
- `0x180024b9c`
- `0x180024d00`
- `0x180024fa8`
- `0x180025440`
- `0x1800255f0`
- `0x1800256c0`
- `0x1800257e0`
- `0x180025cac`
- `0x18002611c`
- `0x18002620c`
- `0x1800264a8`
- `0x18002670c`
- `0x180026810`
- `0x180027180`
- `0x1800283f0`
- `0x18002845c`
- `0x180028534`
- `0x180028834`
- `0x180028a60`
- `0x1800292c8`
- `0x18002b910`
- `0x18002f710`
- `0x1800328e0`
- `0x180032ac8`

## import_xrefs

- `GDI32!DeleteObject` at `0x18002ba9b`
- `GDI32!DeleteObject` at `0x18002ba9b`
- `OLEAUT32!__imp_SysAllocString` at `0x18002c061`
- `OLEAUT32!__imp_SysAllocString` at `0x18002c061`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c047`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c053`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c090`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c0ea`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c117`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c047`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c053`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c090`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c0ea`
- `OLEAUT32!__imp_SysFreeString` at `0x18002c117`
- `USER32!PostMessageW` at `0x18002bc43`
- `USER32!PostMessageW` at `0x18002c036`
- `USER32!PostMessageW` at `0x18002c3bb`
- `USER32!PostMessageW` at `0x18002bc43`
- `USER32!PostMessageW` at `0x18002c036`
- `USER32!PostMessageW` at `0x18002c3bb`
- `USER32!IsWindow` at `0x18002be69`
- `USER32!IsWindow` at `0x18002be69`
- `USER32!SendMessageW` at `0x18002be3c`
- `USER32!SendMessageW` at `0x18002c19f`
- `USER32!SendMessageW` at `0x18002c3d3`
- `USER32!SendMessageW` at `0x18002be3c`
- `USER32!SendMessageW` at `0x18002c19f`
- `USER32!SendMessageW` at `0x18002c3d3`
- `USER32!DestroyWindow` at `0x18002c354`
- `USER32!DestroyWindow` at `0x18002c354`
- `USER32!RedrawWindow` at `0x18002bae6`
- `USER32!RedrawWindow` at `0x18002bae6`
- `USER32!SetFocus` at `0x18002b9a9`
- `USER32!SetFocus` at `0x18002b9a9`
- `USER32!GetFocus` at `0x18002b98a`
- `USER32!GetFocus` at `0x18002b98a`
- `USER32!IsChild` at `0x18002b997`
- `USER32!IsChild` at `0x18002b997`
- `USER32!RegisterWindowMessageW` at `0x18002bb67`
- `USER32!RegisterWindowMessageW` at `0x18002bb67`
- `USER32!IsWindowVisible` at `0x18002bdd0`
- `USER32!IsWindowVisible` at `0x18002bdd0`
- `USER32!IsIconic` at `0x18002be86`
- `USER32!IsIconic` at `0x18002be86`
- `USER32!GetWindowRect` at `0x18002bace`
- `USER32!GetWindowRect` at `0x18002bace`
- `USER32!ShowWindow` at `0x18002be9c`
- `USER32!ShowWindow` at `0x18002be9c`
- `USER32!SetActiveWindow` at `0x18002bb32`
- `USER32!SetActiveWindow` at `0x18002bb32`
- `USER32!GetForegroundWindow` at `0x18002be13`
- `USER32!GetForegroundWindow` at `0x18002be13`
- `USER32!AllowSetForegroundWindow` at `0x18002bea8`
- `USER32!AllowSetForegroundWindow` at `0x18002bea8`

## string_xrefs

- `0x18002c2c3`: `http://go.microsoft.com/fwlink/?LinkID=285879`
- `0x18002c2de`: `http://go.microsoft.com/fwlink/?LinkID=285879`
- `0x18002bb60`: `WM_F12_PROC_COMMAND`

## pseudocode

```c
_BOOL8 __fastcall FrameWindow::_ProcessWindowMessage(
        FrameWindow *this,
        struct tagCREATESTRUCTW *a2,
        unsigned __int64 a3,
        char *a4,
        __int64 psz,
        __int64 *a6,
        unsigned int a7)
{
  int v8; // ebx
  int v9; // r12d
  FrameWindow *v10; // rdi
  HWND Focus; // rax
  __int64 v12; // r13
  bool v13; // zf
  unsigned __int64 v14; // rax
  int v15; // ecx
  __int64 v16; // rax
  UINT v17; // eax
  __int64 MinMaxInfo; // rax
  struct tagCOPYDATASTRUCT *v19; // r13
  unsigned __int64 v20; // rcx
  void *v21; // rax
  struct tagCOPYDATASTRUCT *v22; // r12
  void ***v24; // rcx
  void ***v25; // rdx
  char *v26; // rcx
  __int64 v27; // r14
  bool v28; // dl
  __int64 v29; // r14
  HWND ForegroundWindow; // rax
  F12 *v31; // rcx
  UINT v32; // eax
  LPARAM v33; // r9
  WPARAM v34; // r8
  UINT v35; // edx
  HWND v36; // rcx
  F12 *v37; // rcx
  unsigned int v38; // eax
  BSTR v39; // r15
  OLECHAR *v40; // rbx
  OLECHAR *v41; // rbx
  __int64 v42; // rcx
  int v43; // eax
  volatile signed __int32 *p_lpszName; // rdx
  _BOOL8 v45; // rbx
  char *v46; // r8
  __int64 *v47; // rdx
  __int64 *v48; // rax
  __int64 *v49; // rcx
  __int64 v50; // rcx
  LPCWSTR *v51; // rdx
  UINT v52; // eax
  int *v53; // [rsp+20h] [rbp-E0h]
  struct tagCREATESTRUCTW *v54; // [rsp+40h] [rbp-C0h] BYREF
  struct tagRECT Rect; // [rsp+48h] [rbp-B8h] BYREF
  void **v56; // [rsp+60h] [rbp-A0h] BYREF
  int v57; // [rsp+68h] [rbp-98h]
  void ***v58; // [rsp+98h] [rbp-68h]
  _QWORD v59[7]; // [rsp+A0h] [rbp-60h] BYREF
  void ***v60; // [rsp+D8h] [rbp-28h]
  _QWORD v61[7]; // [rsp+E0h] [rbp-20h] BYREF
  void ***v62; // [rsp+118h] [rbp+18h]
  _QWORD v63[7]; // [rsp+120h] [rbp+20h] BYREF
  void ***v64; // [rsp+158h] [rbp+58h]

  v8 = a3;
  v9 = (int)a2;
  v54 = a2;
  v10 = this;
  if ( a7 )
    return 0;
  switch ( (_DWORD)a3 )
  {
    case 1:
      *((_DWORD *)this + 28) = 1;
      *a6 = FrameWindow::OnCreate(this, a2);
LABEL_51:
      v13 = *((_DWORD *)v10 + 28) == 0;
LABEL_52:
      if ( !v13 )
        return 1;
      goto LABEL_38;
    case 0x21:
      *((_DWORD *)this + 28) = 0;
      Focus = GetFocus();
      if ( !IsChild(*((HWND *)v10 + 1), Focus) )
        SetFocus(*((HWND *)v10 + 1));
      goto LABEL_50;
    case 0x84:
      *((_DWORD *)this + 28) = 1;
LABEL_13:
      *a6 = 0;
LABEL_24:
      v13 = *((_DWORD *)this + 28) == 0;
      goto LABEL_52;
    case 0x83:
      *((_DWORD *)this + 28) = 1;
      if ( !(_DWORD)a4 || *((_BYTE *)this + 435) )
        *((_DWORD *)this + 28) = 0;
      goto LABEL_13;
    case 5:
      *((_DWORD *)this + 28) = 1;
      LODWORD(v54) = (__int16)psz;
      HIDWORD(v54) = SWORD1(psz);
      FrameWindow::OnSize(this, (unsigned int)a4, v54);
LABEL_50:
      *a6 = 0;
      goto LABEL_51;
    case 0x47:
      *((_DWORD *)this + 28) = 1;
      v12 = *((_QWORD *)this + 30);
      if ( v12 )
      {
        BorderWindow::Update((BorderWindow *)(v12 + 8));
        BorderWindow::Update((BorderWindow *)(v12 + 104));
        BorderWindow::Update((BorderWindow *)(v12 + 200));
        BorderWindow::Update((BorderWindow *)(v12 + 296));
      }
      *((_DWORD *)v10 + 28) = 0;
      goto LABEL_50;
    case 0xF:
      *((_DWORD *)this + 28) = 1;
      FrameWindow::OnPaint();
      goto LABEL_50;
    case 0x14:
      *((_DWORD *)this + 28) = 1;
      *a6 = 1;
      goto LABEL_24;
    case 0x85:
      *((_DWORD *)this + 28) = 1;
      if ( a4 )
        DeleteObject(a4);
      goto LABEL_50;
    case 0x86:
      *((_DWORD *)this + 28) = 1;
      *((_BYTE *)this + 688) = (_DWORD)a4 != 0;
      Rect = 0;
      GetWindowRect(*((HWND *)this + 1), &Rect);
      RedrawWindow(*((HWND *)v10 + 1), &Rect, 0, 0x505u);
      *a6 = 1;
      goto LABEL_51;
  }
  if ( (_DWORD)a3 != 32 )
  {
    switch ( (_DWORD)a3 )
    {
      case 0x10:
        *((_DWORD *)this + 28) = 1;
        FrameWindow::OnClose(this);
        goto LABEL_50;
      case 2:
        *((_DWORD *)this + 28) = 1;
        FrameWindow::OnDestroy(this);
        goto LABEL_50;
      case 0x82:
        *((_DWORD *)this + 28) = 1;
        FrameWindow::OnNcDestroy(this);
        goto LABEL_50;
      case 0x1C:
        *((_DWORD *)this + 28) = 1;
        FrameWindow::OnActivateApp(this, (int)a4, 0x1Cu);
        goto LABEL_50;
      case 0x4A:
        *((_DWORD *)this + 28) = 1;
        v19 = (struct tagCOPYDATASTRUCT *)operator new(0x18u);
        v19->dwData = *(_QWORD *)psz;
        v20 = *(unsigned int *)(psz + 8);
        v19->cbData = v20;
        v21 = operator new[](v20);
        v19->lpData = v21;
        memcpy_0(v21, *(const void **)(psz + 16), v19->cbData);
        v22 = 0;
        if ( !PostMessageW(*((HWND *)v10 + 1), 0x75Eu, 0, (LPARAM)v19) )
        {
          if ( (unsigned int)ATL::AtlHresultFromLastError() )
          {
            FreeCopyDataStructCopy(v19);
            goto LABEL_60;
          }
          v22 = v19;
        }
        if ( v22 )
          FreeCopyDataStructCopy(v22);
LABEL_60:
        *a6 = 0;
        if ( *((_DWORD *)v10 + 28) )
          return 1;
        goto LABEL_37;
      case 0x75E:
        MinMaxInfo = FrameWindow::OnCopyDataProcessing(this, (__int64)a2, a3, (struct tagCOPYDATASTRUCT *)psz);
        goto LABEL_65;
      case 0x798:
        MinMaxInfo = FrameWindow::OnBrowserToolCreated(this, (unsigned int)a2, (unsigned __int64)a4, psz, v53);
        goto LABEL_65;
      case 0x24:
        MinMaxInfo = FrameWindow::OnGetMinMaxInfo(this, (unsigned int)a2, a3, psz, v53);
        goto LABEL_65;
      case 0x15:
        v59[0] = &std::_Func_impl_no_alloc<_lambda_912adb59d255ce661602c36fa384397d_,void,enum PluginId,std::shared_ptr<BrowserToolThread>>::`vftable';
        v60 = (void ***)v59;
        FrameWindow::CallbackOnEachScriptPlugin(this, v59);
        v24 = v60;
        if ( v60 )
        {
          v25 = (void ***)v59;
LABEL_122:
          LOBYTE(v25) = v24 != v25;
          ((void (__fastcall *)(void ***, void ***))(*v24)[4])(v24, v25);
          goto LABEL_80;
        }
        goto LABEL_80;
      case 0x74D:
        v26 = (char *)this + 608;
        if ( psz )
        {
          v27 = -1;
          do
            ++v27;
          while ( *(_WORD *)(psz + 2 * v27) );
        }
        else
        {
          LODWORD(v27) = 0;
        }
        ATL::CSimpleStringT<unsigned short,0>::SetString(v26, psz, (unsigned int)v27);
        goto LABEL_80;
      case 0x740:
        MinMaxInfo = FrameWindow::OnSelectTabById(this, (unsigned int)a2, (unsigned __int64)a4, psz, v53);
        goto LABEL_65;
      case 0x741:
        FrameWindow::SwitchToolTab(this, (unsigned __int64)a4);
        goto LABEL_80;
      case 0x742:
        FrameWindow::SelectAdjacentTab(this, a4 != 0);
        goto LABEL_80;
      case 0x743:
        FrameWindow::SelectTabFromNavigationHistory(this, a4 != 0);
        goto LABEL_80;
      case 7:
        if ( *((_DWORD *)this + 137) != -1 )
          FrameWindow::SetPrimaryFocus();
        goto LABEL_80;
      case 6:
        *((_DWORD *)this + 28) = 0;
        if ( !*((_BYTE *)this + 435) )
        {
          if ( a4 )
          {
            if ( (unsigned __int64)(a4 - 1) <= 1 )
            {
              v28 = 1;
              goto LABEL_99;
            }
          }
          else if ( !IsWindowVisible(PopupWindow::s_popupWindowHwnd) )
          {
            v28 = 0;
            this = v10;
LABEL_99:
            FrameWindow::SetActiveWindowStyle(this, v28);
          }
        }
LABEL_100:
        v29 = -1;
LABEL_101:
        *a6 = v29;
        return 1;
      case 0x745:
        if ( !*((_QWORD *)this + 75) )
          goto LABEL_80;
        ForegroundWindow = GetForegroundWindow();
        if ( !ForegroundWindow || ForegroundWindow != *((HWND *)v10 + 75) )
        {
          v32 = F12::SiteCommandMessage(v31);
          SendMessageW(*((HWND *)v10 + 75), v32, 1u, 0);
        }
        v33 = 1;
        v34 = (WPARAM)a4;
        v35 = 1856;
        v36 = (HWND)*((_QWORD *)v10 + 1);
LABEL_163:
        SendMessageW(v36, v35, v34, v33);
        goto LABEL_80;
    }
    LODWORD(a2) = 1872;
    switch ( (_DWORD)a3 )
    {
      case 0x750:
        if ( !IsWindow(*((HWND *)this + 74)) )
          goto LABEL_80;
        FrameWindow::DismissPopupWindow(v10);
        if ( IsIconic(*((HWND *)v10 + 74)) )
          ShowWindow(*((HWND *)v10 + 74), 9);
        AllowSetForegroundWindow(*((_DWORD *)v10 + 146));
        v38 = F12::SiteCommandMessage(v37);
        v33 = 0;
        v34 = 6;
        goto LABEL_162;
      case 0x756:
        v61[0] = &std::_Func_impl_no_alloc<_lambda_ebfa53d128d1c5e6f643f38ba1d69d7a_,void,enum PluginId,std::shared_ptr<BrowserToolThread>>::`vftable';
        v62 = (void ***)v61;
        FrameWindow::CallbackOnEachScriptPlugin(this, v61);
        v24 = v62;
        if ( v62 )
        {
          v25 = (void ***)v61;
          goto LABEL_122;
        }
LABEL_80:
        *a6 = 0;
        return 1;
      case 0x746:
        *((_BYTE *)this + 673) = 1;
        *((_BYTE *)this + 674) = (_DWORD)psz != 0;
        v56 = &std::_Func_impl_no_alloc<_lambda_de70da299f23369cccd5f1dcfe9b7c5f_,void,enum PluginId,std::shared_ptr<BrowserToolThread>>::`vftable';
        v57 = psz;
        v58 = &v56;
        FrameWindow::CallbackOnEachScriptPlugin(this, &v56);
        v24 = v58;
        if ( v58 )
        {
          v25 = &v56;
          goto LABEL_122;
        }
        goto LABEL_80;
      case 0x747:
        *(_WORD *)((char *)this + 673) = 0;
        v63[0] = &std::_Func_impl_no_alloc<_lambda_9548aab9f55e79530eabfdaf9a5c049b_,void,enum PluginId,std::shared_ptr<BrowserToolThread>>::`vftable';
        v64 = (void ***)v63;
        FrameWindow::CallbackOnEachScriptPlugin(this, v63);
        v24 = v64;
        if ( v64 )
        {
          v25 = (void ***)v63;
          goto LABEL_122;
        }
        goto LABEL_80;
      case 0x748:
        MinMaxInfo = FrameWindow::OnNotifyStartProfiling(this, 0x750u, (unsigned __int64)a4, (__int64)a4, v53);
        goto LABEL_65;
      case 0x749:
        MinMaxInfo = FrameWindow::OnNotifyStopProfiling(this, 0x750u, (unsigned __int64)a4, (__int64)a4, v53);
        goto LABEL_65;
      case 0x74A:
        MinMaxInfo = FrameWindow::OnSendJsonMessage(this, 0x750u, (unsigned __int64)a4, psz, v53);
        goto LABEL_65;
      case 0x760:
        MinMaxInfo = FrameWindow::OnPostJsonMessage(this, 0x750u, (unsigned __int64)a4, psz, v53);
        goto LABEL_65;
      case 0x74F:
        MinMaxInfo = FrameWindow::OnNotifyKeydown(this, 0x750u, (unsigned __int64)a4, psz, v53);
        goto LABEL_65;
      case 0x74B:
        if ( psz )
        {
          v39 = SysAllocString((const OLECHAR *)psz);
          if ( !v39 )
            ATL::AtlThrowImpl(-2147024882);
        }
        else
        {
          v39 = 0;
        }
        v40 = 0;
        if ( !PostMessageW(*((HWND *)v10 + 1), 0x761u, (WPARAM)a4, (LPARAM)v39) && v39 )
        {
          SysFreeString(0);
          v40 = v39;
        }
        SysFreeString(v40);
        goto LABEL_80;
      case 0x761:
        v41 = 0;
        *(_QWORD *)&Rect.left = 0;
        if ( psz )
        {
          SysFreeString(0);
          v41 = (OLECHAR *)psz;
          *(_QWORD *)&Rect.left = psz;
        }
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &v54,
          v41);
        v43 = FrameWindow::OpenURLInBrowser(v42, &v54);
        v29 = -1;
        p_lpszName = (volatile signed __int32 *)&v54[-1].lpszName;
        if ( v43 )
        {
          if ( _InterlockedDecrement(p_lpszName + 4) <= 0 )
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)p_lpszName + 8LL))(*(_QWORD *)p_lpszName);
          SysFreeString(v41);
          goto LABEL_101;
        }
        if ( _InterlockedDecrement(p_lpszName + 4) <= 0 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)p_lpszName + 8LL))(*(_QWORD *)p_lpszName);
        SysFreeString(v41);
        break;
      default:
        switch ( (_DWORD)a3 )
        {
          case 0x74C:
            MinMaxInfo = FrameWindow::OnSetConsoleClientArea(this, 0x750u, (unsigned __int64)a4, psz, v53);
            goto LABEL_65;
          case 0x74E:
            FrameWindow::ShowHideConsole(this);
            goto LABEL_80;
          case 0x754:
            if ( *((_DWORD *)this + 140) != 1 || *((_BYTE *)this + 673) || !*((_BYTE *)this + 440) )
              goto LABEL_80;
            v45 = *((_BYTE *)this + 435) == 0;
            v38 = F12::SiteCommandMessage(this);
            v33 = v45;
            v34 = 3;
LABEL_162:
            v35 = v38;
            v36 = (HWND)*((_QWORD *)v10 + 75);
            goto LABEL_163;
        }
        if ( (_DWORD)a3 != 1873 )
        {
          switch ( (_DWORD)a3 )
          {
            case 0x752:
              MinMaxInfo = FrameWindow::OnBrowserActivated(this, 0x750u, (unsigned __int64)a4, (__int64)a4, v53);
              goto LABEL_65;
            case 0x753:
              MinMaxInfo = FrameWindow::OnTabOut(this, 0x750u, (unsigned __int64)a4, psz, v53);
              goto LABEL_65;
            case 0x755:
              MinMaxInfo = FrameWindow::OnMarkToolReady(this, 0x750u, (unsigned __int64)a4, (__int64)a4, v53);
              goto LABEL_65;
            case 0x37F:
              MinMaxInfo = FrameWindow::OnForwardMessage(this, 0x750u, (unsigned __int64)a4, psz, v53);
              goto LABEL_65;
            case 0x759:
              FrameWindow::DismissPopupWindow(this);
              v54 = (struct tagCREATESTRUCTW *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
              if ( !(unsigned __int8)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
                                       &v54,
                                       L"http://go.microsoft.com/fwlink/?LinkID=285879") )
                ATL::CSimpleStringT<unsigned short,0>::SetString(
                  &v54,
                  L"http://go.microsoft.com/fwlink/?LinkID=285879",
                  45);
              FrameWindow::OpenURLInBrowser(v50, &v54);
              v51 = &v54[-1].lpszName;
              if ( _InterlockedDecrement((volatile signed __int32 *)&v54[-1].dwExStyle) <= 0 )
                (*(void (__fastcall **)(LPCWSTR))(*(_QWORD *)*v51 + 8LL))(*v51);
              break;
            case 0x79C:
              if ( ++*((_DWORD *)this + 165) == *((_QWORD *)this + 57) )
                DestroyWindow(*((HWND *)this + 1));
              break;
            case 0x75B:
              FrameWindow::DismissPopupWindow(this);
              if ( !*((_BYTE *)v10 + 435) && !*((_BYTE *)v10 + 688) )
                FrameWindow::SetActiveWindowStyle(v10, 0);
              break;
            case 0x762:
              if ( *((_BYTE *)this + 435) )
              {
                v52 = F12::SiteCommandMessage(this);
                PostMessageW(*((HWND *)v10 + 75), v52, 4u, 0);
                MinMaxInfo = 0;
              }
              else
              {
                MinMaxInfo = SendMessageW(*((HWND *)this + 1), 0x750u, 0, 0);
              }
              goto LABEL_65;
            case 0x7A0:
              *((_DWORD *)this + 173) = (_DWORD)a4;
              *((_DWORD *)this + 174) = psz;
              break;
            case 0x7A1:
              *((_DWORD *)this + 175) = (_DWORD)a4;
              *((_DWORD *)this + 176) = psz;
              break;
            case 0x7A2:
              MinMaxInfo = FrameWindow::OnPopupShow(this, 0x750u, (unsigned __int64)a4, (__int64)a4, v53);
              goto LABEL_65;
            case 0x7A3:
              FrameWindow::HidePopupWindow(this);
              break;
            default:
              goto LABEL_37;
          }
          goto LABEL_80;
        }
        LODWORD(v54) = (_DWORD)a4;
        v46 = (char *)this + 448;
        v47 = (__int64 *)*((_QWORD *)this + 56);
        v48 = (__int64 *)v47[1];
        v49 = v47;
        while ( !*((_BYTE *)v48 + 25) )
        {
          if ( *((_DWORD *)v48 + 8) >= (int)a4 )
          {
            v49 = v48;
            v48 = (__int64 *)*v48;
          }
          else
          {
            v48 = (__int64 *)v48[2];
          }
        }
        if ( *((_BYTE *)v49 + 25) || (int)a4 < *((_DWORD *)v49 + 8) || v49 == v47 )
          goto LABEL_100;
        *(_BYTE *)(*(_QWORD *)std::map<enum PluginId,std::shared_ptr<BrowserToolThreadInfo>>::operator[](v46, &v54)
                 + 24LL) = 1;
        if ( (unsigned __int8)FrameWindow::IsPluginLoaded(v10, (unsigned int)v54) )
          FrameWindow::FirePendingMessages(v10);
        break;
    }
    v29 = 0;
    goto LABEL_101;
  }
  *((_DWORD *)this + 28) = 1;
  if ( (_WORD)psz == 2
    && (v14 = (unsigned __int64)psz >> 16, (unsigned __int16)(WORD1(psz) - 161) <= 6u)
    && (v15 = 73, LOWORD(v14) = WORD1(psz) - 161, _bittest(&v15, v14)) )
  {
    SetActiveWindow(*((HWND *)v10 + 1));
    v16 = 1;
  }
  else
  {
    *((_DWORD *)v10 + 28) = 0;
    v16 = 0;
  }
  *a6 = v16;
  if ( *((_DWORD *)v10 + 28) )
    return 1;
LABEL_37:
  v9 = (int)v54;
LABEL_38:
  v17 = message;
  if ( !message )
  {
    v17 = RegisterWindowMessageW(L"WM_F12_PROC_COMMAND");
    message = v17;
  }
  if ( v8 == v17 )
  {
    MinMaxInfo = FrameWindow::OnProcCommand(v10, (unsigned int)a2, (unsigned __int64)a4, psz, v53);
LABEL_65:
    *a6 = MinMaxInfo;
    return 1;
  }
  return (unsigned int)WTL::CFrameWindowImpl<FrameWindow,ATL::CWindow,ATL::CWinTraits<0,262144>>::ProcessWindowMessage(
                         (_DWORD)v10,
                         v9,
                         v8,
                         (_DWORD)a4,
                         psz,
                         (__int64)a6,
                         0) != 0;
}

```

## disassembly

```asm
0x18002b910  mov     [rsp-8+arg_8], rbx
0x18002b915  push    rbp
0x18002b916  push    rsi
0x18002b917  push    rdi
0x18002b918  push    r12
0x18002b91a  push    r13
0x18002b91c  push    r14
0x18002b91e  push    r15
0x18002b920  lea     rbp, [rsp-70h]
0x18002b925  sub     rsp, 170h
0x18002b92c  mov     rax, cs:__security_cookie
0x18002b933  xor     rax, rsp
0x18002b936  mov     [rbp+0A0h+var_40], rax
0x18002b93a  mov     r14, r9
0x18002b93d  mov     ebx, r8d
0x18002b940  mov     r12, rdx
0x18002b943  mov     [rsp+1A0h+var_160], rdx
0x18002b948  mov     rdi, rcx
0x18002b94b  mov     r15, [rbp+0A0h+psz]
0x18002b952  mov     rsi, [rbp+0A0h+arg_28]
0x18002b959  xor     r13d, r13d
0x18002b95c  cmp     [rbp+0A0h+arg_30], r13d
0x18002b963  jnz     loc_18002C468
0x18002b969  lea     eax, [r13+1]
0x18002b96d  cmp     ebx, eax
0x18002b96f  jnz     short loc_18002B981
0x18002b971  mov     [rcx+70h], eax
0x18002b974  call    ?OnCreate@FrameWindow@@QEAA_JPEAUtagCREATESTRUCTW@@@Z; FrameWindow::OnCreate(tagCREATESTRUCTW *)
0x18002b979  mov     [rsi], rax
0x18002b97c  jmp     loc_18002BBE1
0x18002b981  cmp     ebx, 21h ; '!'
0x18002b984  jnz     short loc_18002B9B4
0x18002b986  mov     [rcx+70h], r13d
0x18002b98a  call    cs:__imp_GetFocus
0x18002b990  mov     rdx, rax; hWnd
0x18002b993  mov     rcx, [rdi+8]; hWndParent
0x18002b997  call    cs:__imp_IsChild
0x18002b99d  test    eax, eax
0x18002b99f  jnz     loc_18002BBDE
0x18002b9a5  mov     rcx, [rdi+8]; hWnd
0x18002b9a9  call    cs:__imp_SetFocus
0x18002b9af  jmp     loc_18002BBDE
0x18002b9b4  cmp     ebx, 84h
0x18002b9ba  jnz     short loc_18002B9C1
0x18002b9bc  mov     [rcx+70h], eax
0x18002b9bf  jmp     short loc_18002B9DE
0x18002b9c1  cmp     ebx, 83h
0x18002b9c7  jnz     short loc_18002B9E6
0x18002b9c9  mov     [rcx+70h], eax
0x18002b9cc  test    r14d, r14d
0x18002b9cf  jz      short loc_18002B9DA
0x18002b9d1  cmp     [rcx+1B3h], r13b
0x18002b9d8  jz      short loc_18002B9DE
0x18002b9da  mov     [rcx+70h], r13d
0x18002b9de  mov     [rsi], r13
0x18002b9e1  jmp     loc_18002BA7B
0x18002b9e6  cmp     ebx, 5
0x18002b9e9  jnz     short loc_18002BA14
0x18002b9eb  mov     [rcx+70h], eax
0x18002b9ee  movsx   eax, r15w
0x18002b9f2  mov     dword ptr [rsp+1A0h+var_160], eax
0x18002b9f6  mov     rax, r15
0x18002b9f9  shr     rax, 10h
0x18002b9fd  cwde
0x18002b9fe  mov     dword ptr [rsp+1A0h+var_160+4], eax
0x18002ba02  mov     edx, r14d
0x18002ba05  mov     r8, [rsp+1A0h+var_160]
0x18002ba0a  call    ?OnSize@FrameWindow@@QEAAXIVCSize@@@Z; FrameWindow::OnSize(uint,CSize)
0x18002ba0f  jmp     loc_18002BBDE
0x18002ba14  cmp     ebx, 47h ; 'G'
0x18002ba17  jnz     short loc_18002BA5E
0x18002ba19  mov     [rcx+70h], eax
0x18002ba1c  mov     r13, [rcx+0F0h]
0x18002ba23  test    r13, r13
0x18002ba26  jz      short loc_18002BA52
0x18002ba28  lea     rcx, [r13+8]; this
0x18002ba2c  call    ?Update@BorderWindow@@QEAAXXZ; BorderWindow::Update(void)
0x18002ba31  lea     rcx, [r13+68h]; this
0x18002ba35  call    ?Update@BorderWindow@@QEAAXXZ; BorderWindow::Update(void)
0x18002ba3a  lea     rcx, [r13+0C8h]; this
0x18002ba41  call    ?Update@BorderWindow@@QEAAXXZ; BorderWindow::Update(void)
0x18002ba46  lea     rcx, [r13+128h]; this
0x18002ba4d  call    ?Update@BorderWindow@@QEAAXXZ; BorderWindow::Update(void)
0x18002ba52  xor     r13d, r13d
0x18002ba55  mov     [rdi+70h], r13d
0x18002ba59  jmp     loc_18002BBDE
0x18002ba5e  cmp     ebx, 0Fh
0x18002ba61  jnz     short loc_18002BA70
0x18002ba63  mov     [rcx+70h], eax
0x18002ba66  call    ?OnPaint@FrameWindow@@QEAAXV?$CDCT@$0A@@WTL@@@Z; FrameWindow::OnPaint(WTL::CDCT<0>)
0x18002ba6b  jmp     loc_18002BBDE
0x18002ba70  cmp     ebx, 14h
0x18002ba73  jnz     short loc_18002BA84
0x18002ba75  mov     [rcx+70h], eax
0x18002ba78  mov     [rsi], rax
0x18002ba7b  cmp     [rcx+70h], r13d
0x18002ba7f  jmp     loc_18002BBE5
0x18002ba84  cmp     ebx, 85h
0x18002ba8a  jnz     short loc_18002BAA6
0x18002ba8c  mov     [rcx+70h], eax
0x18002ba8f  test    r14, r14
0x18002ba92  jz      loc_18002BBDE
0x18002ba98  mov     rcx, r14; ho
0x18002ba9b  call    cs:__imp_DeleteObject
0x18002baa1  jmp     loc_18002BBDE
0x18002baa6  cmp     ebx, 86h
0x18002baac  jnz     short loc_18002BAF8
0x18002baae  mov     [rcx+70h], eax
0x18002bab1  test    r14d, r14d
0x18002bab4  setnz   al
0x18002bab7  mov     [rcx+2B0h], al
0x18002babd  xorps   xmm0, xmm0
0x18002bac0  movups  xmmword ptr [rsp+1A0h+Rect.left], xmm0
0x18002bac5  lea     rdx, [rsp+1A0h+Rect]; lpRect
0x18002baca  mov     rcx, [rcx+8]; hWnd
0x18002bace  call    cs:__imp_GetWindowRect
0x18002bad4  mov     r9d, 505h; flags
0x18002bada  xor     r8d, r8d; hrgnUpdate
0x18002badd  lea     rdx, [rsp+1A0h+Rect]; lprcUpdate
0x18002bae2  mov     rcx, [rdi+8]; hWnd
0x18002bae6  call    cs:__imp_RedrawWindow
0x18002baec  mov     qword ptr [rsi], 1
0x18002baf3  jmp     loc_18002BBE1
0x18002baf8  cmp     ebx, 20h ; ' '
0x18002bafb  jnz     loc_18002BB8E
0x18002bb01  mov     [rcx+70h], eax
0x18002bb04  lea     eax, [rbx-1Eh]
0x18002bb07  cmp     r15w, ax
0x18002bb0b  jnz     short loc_18002BB3D
0x18002bb0d  mov     rax, r15
0x18002bb10  shr     rax, 10h
0x18002bb14  mov     ecx, 0A1h
0x18002bb19  sub     ax, cx
0x18002bb1c  lea     r12d, [rbx-1Ah]
0x18002bb20  cmp     ax, r12w
0x18002bb24  ja      short loc_18002BB3D
0x18002bb26  lea     ecx, [rbx+29h]
0x18002bb29  bt      ecx, eax
0x18002bb2c  jnb     short loc_18002BB3D
0x18002bb2e  mov     rcx, [rdi+8]; hWnd
0x18002bb32  call    cs:__imp_SetActiveWindow
0x18002bb38  lea     eax, [rbx-1Fh]
0x18002bb3b  jmp     short loc_18002BB44
0x18002bb3d  mov     [rdi+70h], r13d
0x18002bb41  mov     rax, r13
0x18002bb44  mov     [rsi], rax
0x18002bb47  cmp     [rdi+70h], r13d
0x18002bb4b  jnz     loc_18002BC9B
0x18002bb51  mov     r12, [rsp+1A0h+var_160]
0x18002bb56  mov     eax, cs:message
0x18002bb5c  test    eax, eax
0x18002bb5e  jnz     short loc_18002BB73
0x18002bb60  lea     rcx, aWmF12ProcComma; "WM_F12_PROC_COMMAND"
0x18002bb67  call    cs:__imp_RegisterWindowMessageW
0x18002bb6d  mov     cs:message, eax
0x18002bb73  mov     rcx, rdi; this
0x18002bb76  cmp     ebx, eax
0x18002bb78  jnz     loc_18002C43F
0x18002bb7e  mov     r9, r15; __int64
0x18002bb81  mov     r8, r14; unsigned __int64
0x18002bb84  call    ?OnProcCommand@FrameWindow@@QEAA_JI_K_JAEAH@Z; FrameWindow::OnProcCommand(uint,unsigned __int64,__int64,int &)
0x18002bb89  jmp     loc_18002BC98
0x18002bb8e  cmp     ebx, 10h
0x18002bb91  jnz     short loc_18002BB9D
0x18002bb93  mov     [rcx+70h], eax
0x18002bb96  call    ?OnClose@FrameWindow@@QEAAXXZ; FrameWindow::OnClose(void)
0x18002bb9b  jmp     short loc_18002BBDE
0x18002bb9d  mov     eax, 2
0x18002bba2  cmp     ebx, eax
0x18002bba4  jnz     short loc_18002BBB4
0x18002bba6  mov     dword ptr [rcx+70h], 1
0x18002bbad  call    ?OnDestroy@FrameWindow@@QEAAXXZ; FrameWindow::OnDestroy(void)
0x18002bbb2  jmp     short loc_18002BBDE
0x18002bbb4  cmp     ebx, 82h
0x18002bbba  jnz     short loc_18002BBCA
0x18002bbbc  mov     dword ptr [rcx+70h], 1
0x18002bbc3  call    ?OnNcDestroy@FrameWindow@@QEAAXXZ; FrameWindow::OnNcDestroy(void)
0x18002bbc8  jmp     short loc_18002BBDE
0x18002bbca  cmp     ebx, 1Ch
0x18002bbcd  jnz     short loc_18002BBF0
0x18002bbcf  mov     dword ptr [rcx+70h], 1
0x18002bbd6  mov     edx, r14d; int
0x18002bbd9  call    ?OnActivateApp@FrameWindow@@QEAAXHK@Z; FrameWindow::OnActivateApp(int,ulong)
0x18002bbde  mov     [rsi], r13
0x18002bbe1  cmp     [rdi+70h], r13d
0x18002bbe5  jnz     loc_18002BC9B
0x18002bbeb  jmp     loc_18002BB56
0x18002bbf0  cmp     ebx, 4Ah ; 'J'
0x18002bbf3  jnz     loc_18002BC88
0x18002bbf9  mov     dword ptr [rcx+70h], 1
0x18002bc00  lea     ecx, [rbx-32h]; Size
0x18002bc03  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002bc08  mov     r13, rax
0x18002bc0b  mov     rcx, [r15]
0x18002bc0e  mov     [rax], rcx
0x18002bc11  mov     ecx, [r15+8]; unsigned __int64
0x18002bc15  mov     [rax+8], ecx
0x18002bc18  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002bc1d  mov     [r13+10h], rax
0x18002bc21  mov     r8d, [r13+8]; Size
0x18002bc25  mov     rdx, [r15+10h]; Src
0x18002bc29  mov     rcx, rax; void *
0x18002bc2c  call    memcpy_0
0x18002bc31  xor     r12d, r12d
0x18002bc34  mov     r9, r13; lParam
0x18002bc37  xor     r8d, r8d; wParam
0x18002bc3a  mov     edx, 75Eh; Msg
0x18002bc3f  mov     rcx, [rdi+8]; hWnd
0x18002bc43  call    cs:__imp_PostMessageW
0x18002bc49  test    eax, eax
0x18002bc4b  jnz     short loc_18002BC5A
0x18002bc4d  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002bc52  nop
0x18002bc53  test    eax, eax
0x18002bc55  jnz     short loc_18002BC7A
0x18002bc57  mov     r12, r13
0x18002bc5a  xor     r13d, r13d
0x18002bc5d  test    r12, r12
0x18002bc60  jz      short loc_18002BC6B
0x18002bc62  mov     rcx, r12; Block
0x18002bc65  call    ?FreeCopyDataStructCopy@@YAXPEAUtagCOPYDATASTRUCT@@@Z; FreeCopyDataStructCopy(tagCOPYDATASTRUCT *)
0x18002bc6a  nop
0x18002bc6b  mov     [rsi], r13
0x18002bc6e  cmp     [rdi+70h], r13d
0x18002bc72  jz      loc_18002BB51
0x18002bc78  jmp     short loc_18002BC9B
0x18002bc7a  mov     rcx, r13; Block
0x18002bc7d  call    ?FreeCopyDataStructCopy@@YAXPEAUtagCOPYDATASTRUCT@@@Z; FreeCopyDataStructCopy(tagCOPYDATASTRUCT *)
0x18002bc82  nop
0x18002bc83  xor     r13d, r13d
0x18002bc86  jmp     short loc_18002BC6B
0x18002bc88  cmp     ebx, 75Eh
0x18002bc8e  jnz     short loc_18002BCA5
0x18002bc90  mov     r9, r15; __int64
0x18002bc93  call    ?OnCopyDataProcessing@FrameWindow@@QEAA_JI_K_JAEAH@Z; FrameWindow::OnCopyDataProcessing(uint,unsigned __int64,__int64,int &)
0x18002bc98  mov     [rsi], rax
0x18002bc9b  mov     eax, 1
0x18002bca0  jmp     loc_18002C46A
0x18002bca5  cmp     ebx, 798h
0x18002bcab  jnz     short loc_18002BCBA
0x18002bcad  mov     r9, r15; __int64
0x18002bcb0  mov     r8, r14; unsigned __int64
0x18002bcb3  call    ?OnBrowserToolCreated@FrameWindow@@QEAA_JI_K_JAEAH@Z; FrameWindow::OnBrowserToolCreated(uint,unsigned __int64,__int64,int &)
0x18002bcb8  jmp     short loc_18002BC98
0x18002bcba  cmp     ebx, 24h ; '$'
0x18002bcbd  jnz     short loc_18002BCC9
0x18002bcbf  mov     r9, r15; __int64
0x18002bcc2  call    ?OnGetMinMaxInfo@FrameWindow@@QEAA_JI_K_JAEAH@Z; FrameWindow::OnGetMinMaxInfo(uint,unsigned __int64,__int64,int &)
0x18002bcc7  jmp     short loc_18002BC98
0x18002bcc9  cmp     ebx, 15h
0x18002bccc  jnz     short loc_18002BCFD
0x18002bcce  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_912adb59d255ce661602c36fa384397d_@@XW4PluginId@@V?$shared_ptr@VBrowserToolThread@@@std@@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_912adb59d255ce661602c36fa384397d_,void,PluginId,std::shared_ptr<BrowserToolThread>>::`vftable'
0x18002bcd5  mov     [rbp+0A0h+var_100], rax
0x18002bcd9  lea     rax, [rbp+0A0h+var_100]
0x18002bcdd  mov     [rbp+0A0h+var_C8], rax
0x18002bce1  lea     rdx, [rbp+0A0h+var_100]
0x18002bce5  call    ?CallbackOnEachScriptPlugin@FrameWindow@@AEAAXAEBV?$function@$$A6AXW4PluginId@@V?$shared_ptr@VBrowserToolThread@@@std@@@Z@std@@@Z; FrameWindow::CallbackOnEachScriptPlugin(std::function<void (PluginId,std::shared_ptr<BrowserToolThread>)> const &)
0x18002bcea  nop
0x18002bceb  mov     rcx, [rbp+0A0h+var_C8]
0x18002bcef  test    rcx, rcx
0x18002bcf2  jz      short loc_18002BD2F
0x18002bcf4  lea     rdx, [rbp+0A0h+var_100]
0x18002bcf8  jmp     loc_18002BF8B
0x18002bcfd  cmp     ebx, 74Dh
0x18002bd03  jnz     short loc_18002BD37
0x18002bd05  add     rcx, 260h
0x18002bd0c  test    r15, r15
0x18002bd0f  jnz     short loc_18002BD16
0x18002bd11  mov     r14d, r13d
0x18002bd14  jmp     short loc_18002BD24
0x18002bd16  or      r14, 0FFFFFFFFFFFFFFFFh
0x18002bd1a  inc     r14
0x18002bd1d  cmp     [r15+r14*2], r13w
0x18002bd22  jnz     short loc_18002BD1A
0x18002bd24  mov     r8d, r14d
0x18002bd27  mov     rdx, r15
0x18002bd2a  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18002bd2f  mov     [rsi], r13
0x18002bd32  jmp     loc_18002BC9B
0x18002bd37  cmp     ebx, 740h
0x18002bd3d  jnz     short loc_18002BD4F
0x18002bd3f  mov     r9, r15; __int64
0x18002bd42  mov     r8, r14; unsigned __int64
0x18002bd45  call    ?OnSelectTabById@FrameWindow@@QEAA_JI_K_JAEAH@Z; FrameWindow::OnSelectTabById(uint,unsigned __int64,__int64,int &)
0x18002bd4a  jmp     loc_18002BC98
0x18002bd4f  cmp     ebx, 741h
0x18002bd55  jnz     short loc_18002BD61
0x18002bd57  mov     rdx, r14; unsigned __int64
0x18002bd5a  call    ?SwitchToolTab@FrameWindow@@AEAA_N_K@Z; FrameWindow::SwitchToolTab(unsigned __int64)
0x18002bd5f  jmp     short loc_18002BD2F
0x18002bd61  cmp     ebx, 742h
0x18002bd67  jnz     short loc_18002BD79
0x18002bd69  mov     edx, r13d
0x18002bd6c  test    r14, r14
0x18002bd6f  setnz   dl; int
0x18002bd72  call    ?SelectAdjacentTab@FrameWindow@@AEAA_NH@Z; FrameWindow::SelectAdjacentTab(int)
0x18002bd77  jmp     short loc_18002BD2F
0x18002bd79  cmp     ebx, 743h
0x18002bd7f  jnz     short loc_18002BD91
0x18002bd81  mov     edx, r13d
  ... truncated ...
```
