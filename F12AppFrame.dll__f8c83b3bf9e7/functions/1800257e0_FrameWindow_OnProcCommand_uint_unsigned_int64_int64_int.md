# FrameWindow::OnProcCommand(uint,unsigned __int64,__int64,int &)

- ea: `0x1800257e0`
- end: `0x180025ca3`
- name: `?OnProcCommand@FrameWindow@@QEAA_JI_K_JAEAH@Z`
- size: `1219`
- prototype: `__int64 __fastcall(FrameWindow *this, unsigned int, unsigned __int64, HWND)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002b910`

## callees

- `0x180001800`
- `0x1800120e4`
- `0x180020bac`
- `0x180020dcc`
- `0x180022204`
- `0x18002319c`
- `0x1800240e4`
- `0x1800257e0`
- `0x180025cac`
- `0x1800263e8`
- `0x1800264a8`
- `0x180027df8`
- `0x180028228`
- `0x1800283f0`
- `0x18002845c`
- `0x180028534`
- `0x1800292c8`
- `0x18002983c`
- `0x1800298b4`
- `0x180035010`

## import_xrefs

- `USER32!InvalidateRect` at `0x180025b23`
- `USER32!InvalidateRect` at `0x180025b23`
- `USER32!GetClientRect` at `0x1800259d4`
- `USER32!GetClientRect` at `0x1800259d4`
- `USER32!SetWindowPos` at `0x1800258bb`
- `USER32!SetWindowPos` at `0x1800258bb`
- `USER32!SetFocus` at `0x180025abe`
- `USER32!SetFocus` at `0x180025abe`
- `USER32!GetFocus` at `0x180025aa5`
- `USER32!GetFocus` at `0x180025aa5`
- `USER32!IsChild` at `0x180025ab1`
- `USER32!IsChild` at `0x180025ab1`
- `USER32!IsIconic` at `0x180025c1b`
- `USER32!IsIconic` at `0x180025c1b`
- `USER32!GetWindowRect` at `0x180025983`
- `USER32!GetWindowRect` at `0x180025983`
- `USER32!ShowWindow` at `0x1800259a3`
- `USER32!ShowWindow` at `0x180025c2e`
- `USER32!ShowWindow` at `0x1800259a3`
- `USER32!ShowWindow` at `0x180025c2e`
- `USER32!SetForegroundWindow` at `0x180025952`
- `USER32!SetForegroundWindow` at `0x180025c11`
- `USER32!SetForegroundWindow` at `0x180025952`
- `USER32!SetForegroundWindow` at `0x180025c11`
- `USER32!EnableWindow` at `0x1800259ed`
- `USER32!EnableWindow` at `0x180025a14`
- `USER32!EnableWindow` at `0x180025a21`
- `USER32!EnableWindow` at `0x180025a35`
- `USER32!EnableWindow` at `0x180025a45`
- `USER32!EnableWindow` at `0x1800259ed`
- `USER32!EnableWindow` at `0x180025a14`
- `USER32!EnableWindow` at `0x180025a21`
- `USER32!EnableWindow` at `0x180025a35`
- `USER32!EnableWindow` at `0x180025a45`
- `USER32!GetWindowPlacement` at `0x180025962`
- `USER32!GetWindowPlacement` at `0x180025962`
- `USER32!SetWindowPlacement` at `0x180025949`
- `USER32!SetWindowPlacement` at `0x180025949`
- `USER32!EqualRect` at `0x180025993`
- `USER32!EqualRect` at `0x180025993`
- `iertutil!__imp_SetValue` at `0x180025b54`
- `iertutil!__imp_SetValue` at `0x180025b54`

## pseudocode

```c
__int64 __fastcall FrameWindow::OnProcCommand(FrameWindow *this, unsigned int a2, unsigned __int64 a3, HWND a4)
{
  unsigned __int64 v6; // r8
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // r8
  unsigned __int64 v9; // r8
  HWND *v10; // rdi
  HWND *v11; // rbx
  BOOL v12; // r14d
  HWND Focus; // rax
  _QWORD *v14; // rdx
  int v15; // edx
  HWND v16; // rcx
  unsigned __int64 v17; // r8
  unsigned __int64 v18; // r8
  unsigned __int64 v19; // r8
  unsigned __int64 v20; // r8
  unsigned __int64 v21; // r8
  _QWORD *v23; // rdx
  int *v24; // [rsp+20h] [rbp-E0h]
  HWND *v25; // [rsp+40h] [rbp-C0h] BYREF
  struct tagRECT Rect; // [rsp+48h] [rbp-B8h] BYREF
  WINDOWPLACEMENT wndpl; // [rsp+58h] [rbp-A8h] BYREF
  struct tagRECT v28; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v29[7]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD *v30; // [rsp+D8h] [rbp-28h]
  _QWORD v31[7]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD *v32; // [rsp+118h] [rbp+18h]

  if ( a3 > 6 )
  {
    v17 = a3 - 7;
    if ( !v17 )
    {
      *((_BYTE *)this + 672) = 1;
      v31[0] = &std::_Func_impl_no_alloc<_lambda_edfe2245e28d28f5197bff3ac079bea6_,void,enum PluginId,std::shared_ptr<BrowserToolThread>>::`vftable';
      v32 = v31;
      FrameWindow::CallbackOnEachScriptPlugin(this, v31);
      if ( v32 )
      {
        v23 = v31;
        LOBYTE(v23) = v32 != v31;
        (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v32 + 32LL))(v32, v23);
      }
      return 0;
    }
    v18 = v17 - 1;
    if ( v18 )
    {
      v19 = v18 - 1;
      if ( !v19 )
      {
        FrameWindow::SelectAdjacentTab(this, (int)a4);
        return 0;
      }
      v20 = v19 - 1;
      if ( !v20 )
      {
        FrameWindow::SelectTabFromNavigationHistory(this, (int)a4);
        return 0;
      }
      v21 = v20 - 1;
      if ( !v21 )
      {
        FrameWindow::RefreshPage(this);
        return 0;
      }
      if ( v21 == 1 )
      {
        FrameWindow::OnActivateApp(this, (int)a4, 1u);
        return 0;
      }
      return -1;
    }
    SetForegroundWindow(*((HWND *)this + 1));
    if ( !IsIconic(*((HWND *)this + 1)) )
      return 0;
    v15 = 9;
    v16 = (HWND)*((_QWORD *)this + 1);
LABEL_54:
    ShowWindow(v16, v15);
    return 0;
  }
  if ( a3 == 6 )
  {
    FrameWindow::SwitchToolTab(this, (unsigned __int64)a4);
    return 0;
  }
  if ( !a3 )
  {
    FrameWindow::CleanUp(this);
    return 0;
  }
  v6 = a3 - 1;
  if ( !v6 )
  {
    switch ( (_DWORD)a4 )
    {
      case 0:
        FrameWindow::OnShowFrame(this);
        return 0;
      case 1:
        FrameWindow::OnHideFrame(this);
        return 0;
      case 2:
        v15 = 5;
        break;
      case 3:
        v15 = 0;
        break;
      default:
        return 0;
    }
    v16 = (HWND)*((_QWORD *)this + 1);
    goto LABEL_54;
  }
  v7 = v6 - 1;
  if ( !v7 )
  {
    FrameWindow::DismissPopupWindow(this);
    FrameWindow::UpdateWindowPos(this);
    if ( !FrameWindow::ReparentWindowForDocking(this, a4, (-(__int64)(a4 != 0) & 0xFFFFFFFFBFF10000uLL) + 2249129984u) )
    {
      v10 = (HWND *)((char *)this + 8);
      memset(&wndpl, 0, 32);
      v25 = (HWND *)((char *)this + 8);
      if ( a4 )
      {
        wndpl.rcNormalPosition = 0;
        if ( GetWindowPlacement(*v10, &wndpl)
          && wndpl.showCmd == 1
          && (Rect = 0, GetWindowRect(*v10, &Rect), !EqualRect(&Rect, &wndpl.rcNormalPosition)) )
        {
          ShowWindow(*v10, 9);
        }
        else
        {
          v25 = (HWND *)((char *)this + 8);
        }
      }
      else
      {
        wndpl.length = 44;
        wndpl.showCmd = *((_DWORD *)this + 33) != 0 ? 9 : 3;
        wndpl.rcNormalPosition = *(RECT *)((char *)this + 116);
        SetWindowPlacement(*v10, &wndpl);
        SetForegroundWindow(*v10);
      }
      *((_BYTE *)this + 435) = a4 != 0;
      *(_QWORD *)&Rect.left = 0;
      v28 = 0;
      GetClientRect(*v10, &v28);
      EnableWindow(*((HWND *)this + 19), *((_BYTE *)this + 435) == 0);
      v11 = (HWND *)*((_QWORD *)this + 30);
      if ( v11 )
      {
        v12 = *((_BYTE *)this + 435) == 0;
        EnableWindow(v11[2], v12);
        EnableWindow(v11[14], v12);
        EnableWindow(v11[26], v12);
        EnableWindow(v11[38], v12);
        BorderWindow::Update((BorderWindow *)(v11 + 1));
        BorderWindow::Update((BorderWindow *)(v11 + 13));
        BorderWindow::Update((BorderWindow *)(v11 + 25));
        BorderWindow::Update((BorderWindow *)(v11 + 37));
        v10 = v25;
      }
      if ( !*((_BYTE *)this + 435) )
      {
        v25 = *(HWND **)&v28.right;
        FrameWindow::OnSize(this, 0, *(_QWORD *)&v28.right);
        FrameWindow::UpdateTabLayout(this);
      }
      Focus = GetFocus();
      if ( !IsChild(*v10, Focus) )
        SetFocus(*v10);
      v29[0] = &std::_Func_impl_no_alloc<_lambda_c7a275d0ba3f00b6553a1b80e017d7f4_,void,enum PluginId,std::shared_ptr<BrowserToolThread>>::`vftable';
      v29[1] = this;
      v29[2] = *(_QWORD *)&Rect.left;
      v30 = v29;
      FrameWindow::CallbackOnEachScriptPlugin(this, v29);
      if ( v30 )
      {
        v14 = v29;
        LOBYTE(v14) = v30 != v29;
        (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v30 + 32LL))(v30, v14);
      }
      FrameWindow::SetActiveWindowStyle(this, 1);
      InvalidateRect(*v10, 0, 1);
      FrameWindow::UpdateWindowPos(this);
      LODWORD(v25) = 1;
      SetValue((__int64 *)SettingStore::IEVALUE_F12_DockStateChanged, 2, 0, &v25, 4);
      *((_BYTE *)this + 441) = 1;
    }
    return 0;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    SetWindowPos(*((HWND *)this + 1), 0, 0, 0, (__int16)a4, SWORD1(a4), 0x16u);
    return 0;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    SetWindowPos(*((HWND *)this + 1), 0, (__int16)a4, SWORD1(a4), 0, 0, 0x15u);
    return 0;
  }
  if ( v9 != 1 )
    return -1;
  FrameWindow::OnSelectTabById(this, a2, (int)a4, 0, v24);
  return 0;
}

```

## disassembly

```asm
0x1800257e0  mov     [rsp-8+arg_8], rbx
0x1800257e5  mov     [rsp-8+arg_10], rsi
0x1800257ea  push    rbp
0x1800257eb  push    rdi
0x1800257ec  push    r13
0x1800257ee  push    r14
0x1800257f0  push    r15
0x1800257f2  lea     rbp, [rsp-30h]
0x1800257f7  sub     rsp, 130h
0x1800257fe  mov     rax, cs:__security_cookie
0x180025805  xor     rax, rsp
0x180025808  mov     [rbp+50h+var_30], rax
0x18002580c  mov     rbx, r9
0x18002580f  mov     r13, rcx
0x180025812  cmp     r8, 6
0x180025816  ja      loc_180025BBB
0x18002581c  jz      loc_180025BAE
0x180025822  test    r8, r8
0x180025825  jz      loc_180025BA4
0x18002582b  sub     r8, 1
0x18002582f  jz      loc_180025B67
0x180025835  sub     r8, 1
0x180025839  jz      loc_1800258C6
0x18002583f  sub     r8, 1
0x180025843  jz      short loc_180025892
0x180025845  sub     r8, 1
0x180025849  jz      short loc_180025865
0x18002584b  cmp     r8, 1
0x18002584f  jnz     loc_180025BDF
0x180025855  movsxd  r8, ebx; unsigned __int64
0x180025858  xor     r9d, r9d; __int64
0x18002585b  call    ?OnSelectTabById@FrameWindow@@QEAA_JI_K_JAEAH@Z; FrameWindow::OnSelectTabById(uint,unsigned __int64,__int64,int &)
0x180025860  jmp     loc_180025C79
0x180025865  mov     rax, rbx
0x180025868  shr     rax, 10h
0x18002586c  movsx   r9d, ax
0x180025870  movsx   r8d, bx
0x180025874  mov     [rsp+150h+uFlags], 15h
0x18002587c  mov     [rsp+150h+cy], 0
0x180025884  mov     dword ptr [rsp+150h+var_130], 0
0x18002588c  mov     rcx, [rcx+8]
0x180025890  jmp     short loc_1800258B9
0x180025892  mov     rax, rbx
0x180025895  shr     rax, 10h
0x180025899  movsx   ecx, ax
0x18002589c  movsx   eax, bx
0x18002589f  mov     [rsp+150h+uFlags], 16h; uFlags
0x1800258a7  mov     [rsp+150h+cy], ecx; cy
0x1800258ab  mov     dword ptr [rsp+150h+var_130], eax; cx
0x1800258af  xor     r9d, r9d; Y
0x1800258b2  xor     r8d, r8d; X
0x1800258b5  mov     rcx, [r13+8]; hWnd
0x1800258b9  xor     edx, edx; hWndInsertAfter
0x1800258bb  call    cs:__imp_SetWindowPos
0x1800258c1  jmp     loc_180025C79
0x1800258c6  call    ?DismissPopupWindow@FrameWindow@@AEAAXXZ; FrameWindow::DismissPopupWindow(void)
0x1800258cb  mov     rcx, r13; this
0x1800258ce  call    ?UpdateWindowPos@FrameWindow@@AEAAXXZ; FrameWindow::UpdateWindowPos(void)
0x1800258d3  mov     rax, rbx
0x1800258d6  neg     rax
0x1800258d9  sbb     r8, r8
0x1800258dc  and     r8, 0FFFFFFFFBFF10000h
0x1800258e3  mov     eax, 860F0000h
0x1800258e8  add     r8, rax; __int64
0x1800258eb  mov     rdx, rbx; HWND
0x1800258ee  mov     rcx, r13; this
0x1800258f1  call    ?ReparentWindowForDocking@FrameWindow@@AEAAJPEAUHWND__@@_J@Z; FrameWindow::ReparentWindowForDocking(HWND__ *,__int64)
0x1800258f6  test    eax, eax
0x1800258f8  jnz     loc_180025C79
0x1800258fe  xorps   xmm0, xmm0
0x180025901  lea     rdi, [r13+8]
0x180025905  lea     rdx, [rsp+150h+wndpl]; lpwndpl
0x18002590a  movups  xmmword ptr [rsp+150h+wndpl.length], xmm0
0x18002590f  movups  xmmword ptr [rsp+150h+wndpl.ptMinPosition.y], xmm0
0x180025914  mov     [rsp+150h+var_110], rdi
0x180025919  test    rbx, rbx
0x18002591c  jnz     short loc_18002595A
0x18002591e  mov     [rsp+150h+wndpl.length], 2Ch ; ','
0x180025926  mov     eax, [r13+84h]
0x18002592d  neg     eax
0x18002592f  sbb     ecx, ecx
0x180025931  and     ecx, 6
0x180025934  add     ecx, 3
0x180025937  mov     [rsp+150h+wndpl.showCmd], ecx
0x18002593b  movups  xmm0, xmmword ptr [r13+74h]
0x180025940  movdqu  xmmword ptr [rsp+150h+wndpl.rcNormalPosition.left], xmm0
0x180025946  mov     rcx, [rdi]; hWnd
0x180025949  call    cs:__imp_SetWindowPlacement
0x18002594f  mov     rcx, [rdi]; hWnd
0x180025952  call    cs:__imp_SetForegroundWindow
0x180025958  jmp     short loc_1800259B0
0x18002595a  movups  xmmword ptr [rsp+150h+wndpl.rcNormalPosition.left], xmm0
0x18002595f  mov     rcx, [rdi]; hWnd
0x180025962  call    cs:__imp_GetWindowPlacement
0x180025968  test    eax, eax
0x18002596a  jz      short loc_1800259AB
0x18002596c  cmp     [rsp+150h+wndpl.showCmd], 1
0x180025971  jnz     short loc_1800259AB
0x180025973  xorps   xmm0, xmm0
0x180025976  movups  xmmword ptr [rsp+150h+Rect.left], xmm0
0x18002597b  lea     rdx, [rsp+150h+Rect]; lpRect
0x180025980  mov     rcx, [rdi]; hWnd
0x180025983  call    cs:__imp_GetWindowRect
0x180025989  lea     rdx, [rsp+150h+wndpl.rcNormalPosition]; lprc2
0x18002598e  lea     rcx, [rsp+150h+Rect]; lprc1
0x180025993  call    cs:__imp_EqualRect
0x180025999  test    eax, eax
0x18002599b  jnz     short loc_1800259AB
0x18002599d  lea     edx, [rax+9]; nCmdShow
0x1800259a0  mov     rcx, [rdi]; hWnd
0x1800259a3  call    cs:__imp_ShowWindow
0x1800259a9  jmp     short loc_1800259B0
0x1800259ab  mov     [rsp+150h+var_110], rdi
0x1800259b0  test    rbx, rbx
0x1800259b3  setnz   al
0x1800259b6  mov     [r13+1B3h], al
0x1800259bd  mov     qword ptr [rsp+150h+Rect.left], 0
0x1800259c6  xorps   xmm0, xmm0
0x1800259c9  movups  xmmword ptr [rbp+50h+var_C8.left], xmm0
0x1800259cd  lea     rdx, [rbp+50h+var_C8]; lpRect
0x1800259d1  mov     rcx, [rdi]; hWnd
0x1800259d4  call    cs:__imp_GetClientRect
0x1800259da  xor     edx, edx
0x1800259dc  cmp     [r13+1B3h], dl
0x1800259e3  setz    dl; bEnable
0x1800259e6  mov     rcx, [r13+98h]; hWnd
0x1800259ed  call    cs:__imp_EnableWindow
0x1800259f3  mov     rbx, [r13+0F0h]
0x1800259fa  test    rbx, rbx
0x1800259fd  jz      short loc_180025A76
0x1800259ff  xor     r14d, r14d
0x180025a02  cmp     [r13+1B3h], r14b
0x180025a09  setz    r14b
0x180025a0d  mov     edx, r14d; bEnable
0x180025a10  mov     rcx, [rbx+10h]; hWnd
0x180025a14  call    cs:__imp_EnableWindow
0x180025a1a  mov     edx, r14d; bEnable
0x180025a1d  mov     rcx, [rbx+70h]; hWnd
0x180025a21  call    cs:__imp_EnableWindow
0x180025a27  lea     rdi, [rbx+0C8h]
0x180025a2e  mov     edx, r14d; bEnable
0x180025a31  mov     rcx, [rdi+8]; hWnd
0x180025a35  call    cs:__imp_EnableWindow
0x180025a3b  mov     edx, r14d; bEnable
0x180025a3e  mov     rcx, [rbx+130h]; hWnd
0x180025a45  call    cs:__imp_EnableWindow
0x180025a4b  lea     rcx, [rbx+8]; this
0x180025a4f  call    ?Update@BorderWindow@@QEAAXXZ; BorderWindow::Update(void)
0x180025a54  lea     rcx, [rbx+68h]; this
0x180025a58  call    ?Update@BorderWindow@@QEAAXXZ; BorderWindow::Update(void)
0x180025a5d  mov     rcx, rdi; this
0x180025a60  call    ?Update@BorderWindow@@QEAAXXZ; BorderWindow::Update(void)
0x180025a65  lea     rcx, [rbx+128h]; this
0x180025a6c  call    ?Update@BorderWindow@@QEAAXXZ; BorderWindow::Update(void)
0x180025a71  mov     rdi, [rsp+150h+var_110]
0x180025a76  cmp     byte ptr [r13+1B3h], 0
0x180025a7e  jnz     short loc_180025AA5
0x180025a80  mov     eax, [rbp+50h+var_C8.right]
0x180025a83  mov     dword ptr [rsp+150h+var_110], eax
0x180025a87  mov     eax, [rbp+50h+var_C8.bottom]
0x180025a8a  mov     dword ptr [rsp+150h+var_110+4], eax
0x180025a8e  mov     r8, [rsp+150h+var_110]
0x180025a93  xor     edx, edx
0x180025a95  mov     rcx, r13
0x180025a98  call    ?OnSize@FrameWindow@@QEAAXIVCSize@@@Z; FrameWindow::OnSize(uint,CSize)
0x180025a9d  mov     rcx, r13; this
0x180025aa0  call    ?UpdateTabLayout@FrameWindow@@AEAAXXZ; FrameWindow::UpdateTabLayout(void)
0x180025aa5  call    cs:__imp_GetFocus
0x180025aab  mov     rdx, rax; hWnd
0x180025aae  mov     rcx, [rdi]; hWndParent
0x180025ab1  call    cs:__imp_IsChild
0x180025ab7  test    eax, eax
0x180025ab9  jnz     short loc_180025AC4
0x180025abb  mov     rcx, [rdi]; hWnd
0x180025abe  call    cs:__imp_SetFocus
0x180025ac4  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_c7a275d0ba3f00b6553a1b80e017d7f4_@@XW4PluginId@@V?$shared_ptr@VBrowserToolThread@@@std@@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_c7a275d0ba3f00b6553a1b80e017d7f4_,void,PluginId,std::shared_ptr<BrowserToolThread>>::`vftable'
0x180025acb  mov     [rbp+50h+var_B0], rax
0x180025acf  mov     [rbp+50h+var_A8], r13
0x180025ad3  mov     rax, qword ptr [rsp+150h+Rect.left]
0x180025ad8  mov     [rbp+50h+var_A0], rax
0x180025adc  lea     rax, [rbp+50h+var_B0]
0x180025ae0  mov     [rbp+50h+var_78], rax
0x180025ae4  lea     rdx, [rbp+50h+var_B0]
0x180025ae8  mov     rcx, r13
0x180025aeb  call    ?CallbackOnEachScriptPlugin@FrameWindow@@AEAAXAEBV?$function@$$A6AXW4PluginId@@V?$shared_ptr@VBrowserToolThread@@@std@@@Z@std@@@Z; FrameWindow::CallbackOnEachScriptPlugin(std::function<void (PluginId,std::shared_ptr<BrowserToolThread>)> const &)
0x180025af0  nop
0x180025af1  mov     rcx, [rbp+50h+var_78]
0x180025af5  test    rcx, rcx
0x180025af8  jz      short loc_180025B10
0x180025afa  mov     rax, [rcx]
0x180025afd  lea     rdx, [rbp+50h+var_B0]
0x180025b01  cmp     rcx, rdx
0x180025b04  setnz   dl
0x180025b07  mov     rax, [rax+20h]
0x180025b0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b10  mov     dl, 1; bool
0x180025b12  mov     rcx, r13; this
0x180025b15  call    ?SetActiveWindowStyle@FrameWindow@@AEAAX_N@Z; FrameWindow::SetActiveWindowStyle(bool)
0x180025b1a  xor     edx, edx; lpRect
0x180025b1c  lea     r8d, [rdx+1]; bErase
0x180025b20  mov     rcx, [rdi]; hWnd
0x180025b23  call    cs:__imp_InvalidateRect
0x180025b29  mov     rcx, r13; this
0x180025b2c  call    ?UpdateWindowPos@FrameWindow@@AEAAXXZ; FrameWindow::UpdateWindowPos(void)
0x180025b31  mov     dword ptr [rsp+150h+var_110], 1
0x180025b39  mov     dword ptr [rsp+150h+var_130], 4
0x180025b41  lea     r9, [rsp+150h+var_110]
0x180025b46  xor     r8d, r8d
0x180025b49  lea     edx, [r8+2]
0x180025b4d  mov     rcx, cs:?IEVALUE_F12_DockStateChanged@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_F12_DockStateChanged
0x180025b54  call    cs:__imp_SetValue
0x180025b5a  mov     byte ptr [r13+1B9h], 1
0x180025b62  jmp     loc_180025C79
0x180025b67  test    ebx, ebx
0x180025b69  jz      short loc_180025B9A
0x180025b6b  sub     ebx, 1
0x180025b6e  jz      short loc_180025B90
0x180025b70  sub     ebx, 1
0x180025b73  jz      short loc_180025B82
0x180025b75  cmp     ebx, 1
0x180025b78  jnz     loc_180025C79
0x180025b7e  xor     edx, edx
0x180025b80  jmp     short loc_180025B87
0x180025b82  mov     edx, 5
0x180025b87  mov     rcx, [rcx+8]; this
0x180025b8b  jmp     loc_180025C2E
0x180025b90  call    ?OnHideFrame@FrameWindow@@AEAAXXZ; FrameWindow::OnHideFrame(void)
0x180025b95  jmp     loc_180025C79
0x180025b9a  call    ?OnShowFrame@FrameWindow@@AEAAXXZ; FrameWindow::OnShowFrame(void)
0x180025b9f  jmp     loc_180025C79
0x180025ba4  call    ?CleanUp@FrameWindow@@AEAAXXZ; FrameWindow::CleanUp(void)
0x180025ba9  jmp     loc_180025C79
0x180025bae  mov     rdx, rbx; unsigned __int64
0x180025bb1  call    ?SwitchToolTab@FrameWindow@@AEAA_N_K@Z; FrameWindow::SwitchToolTab(unsigned __int64)
0x180025bb6  jmp     loc_180025C79
0x180025bbb  sub     r8, 7
0x180025bbf  jz      short loc_180025C36
0x180025bc1  sub     r8, 1
0x180025bc5  jz      short loc_180025C0D
0x180025bc7  sub     r8, 1
0x180025bcb  jz      short loc_180025C04
0x180025bcd  sub     r8, 1
0x180025bd1  jz      short loc_180025BFB
0x180025bd3  sub     r8, 1; unsigned int
0x180025bd7  jz      short loc_180025BF4
0x180025bd9  cmp     r8, 1
0x180025bdd  jz      short loc_180025BE8
0x180025bdf  or      rax, 0FFFFFFFFFFFFFFFFh
0x180025be3  jmp     loc_180025C7B
0x180025be8  mov     edx, ebx; int
0x180025bea  call    ?OnActivateApp@FrameWindow@@QEAAXHK@Z; FrameWindow::OnActivateApp(int,ulong)
0x180025bef  jmp     loc_180025C79
0x180025bf4  call    ?RefreshPage@FrameWindow@@AEAAXXZ; FrameWindow::RefreshPage(void)
0x180025bf9  jmp     short loc_180025C79
0x180025bfb  mov     edx, ebx; int
0x180025bfd  call    ?SelectTabFromNavigationHistory@FrameWindow@@AEAA_NH@Z; FrameWindow::SelectTabFromNavigationHistory(int)
0x180025c02  jmp     short loc_180025C79
0x180025c04  mov     edx, ebx; int
0x180025c06  call    ?SelectAdjacentTab@FrameWindow@@AEAA_NH@Z; FrameWindow::SelectAdjacentTab(int)
0x180025c0b  jmp     short loc_180025C79
0x180025c0d  mov     rcx, [rcx+8]; hWnd
0x180025c11  call    cs:__imp_SetForegroundWindow
0x180025c17  mov     rcx, [r13+8]; hWnd
0x180025c1b  call    cs:__imp_IsIconic
0x180025c21  test    eax, eax
0x180025c23  jz      short loc_180025C79
0x180025c25  mov     edx, 9; nCmdShow
0x180025c2a  mov     rcx, [r13+8]; hWnd
0x180025c2e  call    cs:__imp_ShowWindow
0x180025c34  jmp     short loc_180025C79
0x180025c36  mov     byte ptr [rcx+2A0h], 1
0x180025c3d  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_edfe2245e28d28f5197bff3ac079bea6_@@XW4PluginId@@V?$shared_ptr@VBrowserToolThread@@@std@@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_edfe2245e28d28f5197bff3ac079bea6_,void,PluginId,std::shared_ptr<BrowserToolThread>>::`vftable'
0x180025c44  mov     [rbp+50h+var_70], rax
0x180025c48  lea     rax, [rbp+50h+var_70]
0x180025c4c  mov     [rbp+50h+var_38], rax
0x180025c50  lea     rdx, [rbp+50h+var_70]
0x180025c54  call    ?CallbackOnEachScriptPlugin@FrameWindow@@AEAAXAEBV?$function@$$A6AXW4PluginId@@V?$shared_ptr@VBrowserToolThread@@@std@@@Z@std@@@Z; FrameWindow::CallbackOnEachScriptPlugin(std::function<void (PluginId,std::shared_ptr<BrowserToolThread>)> const &)
0x180025c59  nop
0x180025c5a  mov     rcx, [rbp+50h+var_38]
0x180025c5e  test    rcx, rcx
0x180025c61  jz      short loc_180025C79
0x180025c63  mov     rax, [rcx]
0x180025c66  lea     rdx, [rbp+50h+var_70]
0x180025c6a  cmp     rcx, rdx
0x180025c6d  setnz   dl
0x180025c70  mov     rax, [rax+20h]
0x180025c74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c79  xor     eax, eax
0x180025c7b  mov     rcx, [rbp+50h+var_30]
0x180025c7f  xor     rcx, rsp; StackCookie
0x180025c82  call    __security_check_cookie
0x180025c87  lea     r11, [rsp+150h+var_20]
0x180025c8f  mov     rbx, [r11+38h]
0x180025c93  mov     rsi, [r11+40h]
0x180025c97  mov     rsp, r11
0x180025c9a  pop     r15
0x180025c9c  pop     r14
0x180025c9e  pop     r13
0x180025ca0  pop     rdi
0x180025ca1  pop     rbp
  ... truncated ...
```
