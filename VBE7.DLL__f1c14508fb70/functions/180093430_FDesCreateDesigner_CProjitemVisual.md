# FDesCreateDesigner(CProjitemVisual *)

- ea: `0x180093430`
- end: `0x18009373c`
- name: `?FDesCreateDesigner@@YAPEAUHWND__@@PEAVCProjitemVisual@@@Z`
- size: `780`
- prototype: `HWND __fastcall(struct CProjitemVisual *)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x18001d6b8`

## callees

- `0x18000458c`
- `0x180017944`
- `0x18001cf44`
- `0x18003fe18`
- `0x18007b868`
- `0x180093430`
- `0x180093b34`
- `0x1800973b0`
- `0x1800e15b8`
- `0x1800e15d0`
- `0x180379380`
- `0x180379520`
- `0x180379546`

## import_xrefs

- `USER32!EnableScrollBar` at `0x18009361d`
- `USER32!EnableScrollBar` at `0x18009361d`
- `USER32!CreateMDIWindowA` at `0x180093567`
- `USER32!CreateMDIWindowA` at `0x180093567`
- `USER32!LoadIconA` at `0x180093509`
- `USER32!LoadIconA` at `0x180093509`
- `USER32!SetWindowLongPtrA` at `0x180093581`
- `USER32!SetWindowLongPtrA` at `0x180093581`
- `USER32!LoadCursorA` at `0x1800934e0`
- `USER32!LoadCursorA` at `0x1800934e0`
- `USER32!GetClientRect` at `0x1800936bb`
- `USER32!GetClientRect` at `0x1800936bb`
- `USER32!PostMessageA` at `0x1800936f5`
- `USER32!PostMessageA` at `0x1800936f5`
- `USER32!SendMessageA` at `0x1800935b4`
- `USER32!SendMessageA` at `0x1800935d5`
- `USER32!SendMessageA` at `0x1800935b4`
- `USER32!SendMessageA` at `0x1800935d5`
- `USER32!IsRectEmpty` at `0x18009346f`
- `USER32!IsRectEmpty` at `0x18009346f`

## pseudocode

```c
HWND __fastcall FDesCreateDesigner(struct CProjitemVisual *a1)
{
  int *v1; // rsi
  int Y; // ebx
  int v4; // r15d
  int nHeight; // esi
  int nWidth; // r14d
  unsigned __int16 v7; // ax
  HWND MDIWindowA; // rax
  HWND v10; // rbx
  HICON v11; // rax
  HICON v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rdi
  unsigned int v16; // eax
  unsigned int v17; // eax
  _BYTE v18[8]; // [rsp+50h] [rbp-49h] BYREF
  __int64 (__fastcall *v19)(HWND, unsigned int, unsigned __int64, __int64); // [rsp+58h] [rbp-41h]
  int v20; // [rsp+64h] [rbp-35h]
  HINSTANCE v21; // [rsp+68h] [rbp-31h]
  HICON IconA; // [rsp+70h] [rbp-29h]
  HCURSOR CursorA; // [rsp+78h] [rbp-21h]
  __int64 v24; // [rsp+80h] [rbp-19h]
  const char *v25; // [rsp+90h] [rbp-9h]
  struct tagRECT Rect; // [rsp+A0h] [rbp+7h] BYREF
  _BYTE v27[8]; // [rsp+B0h] [rbp+17h] BYREF
  int v28; // [rsp+B8h] [rbp+1Fh]
  int v29; // [rsp+BCh] [rbp+23h]

  v1 = (int *)((char *)a1 + 152);
  if ( IsRectEmpty((const RECT *)((char *)a1 + 152)) )
  {
    Y = 0x80000000;
    v4 = 0x80000000;
    nHeight = 0x80000000;
    nWidth = 0x80000000;
  }
  else
  {
    v4 = *v1;
    Y = v1[1];
    nWidth = v1[2] - *v1;
    nHeight = v1[3] - Y;
  }
  v7 = word_1803FAC28;
  if ( !word_1803FAC28 )
  {
    memset_0(v18, 0, 0x48u);
    v21 = Rby_hinstExe;
    v19 = FDesignerWndProc;
    v20 = 8;
    CursorA = LoadCursorA(0, (LPCSTR)0x7F00);
    v25 = "DesignerWindow";
    v24 = 6;
    IconA = LoadIconA(Rby_hmodThun, (LPCSTR)0x4B1);
    v7 = IsolationAwareRegisterClassA(v18);
    word_1803FAC28 = v7;
    if ( !v7 )
      return 0;
  }
  MDIWindowA = CreateMDIWindowA((LPCSTR)v7, 0, 0x46CF0000u, v4, Y, nWidth, nHeight, Main_hwndMdi, Rby_hinstExe, 0);
  v10 = MDIWindowA;
  if ( MDIWindowA )
  {
    SetWindowLongPtrA(MDIWindowA, 0, (LONG_PTR)a1);
    if ( Sys_fWin95Shell )
    {
      v11 = HiconDefault(*(struct XMOD **)(*((_QWORD *)a1 + 7) + 104LL), 0);
      SendMessageA(v10, 0x80u, 1u, (LPARAM)v11);
      v12 = HiconDefault(*(struct XMOD **)(*((_QWORD *)a1 + 7) + 104LL), 1);
      SendMessageA(v10, 0x80u, 0, (LPARAM)v12);
    }
    ProjNotifyWinChanged(a1, v10, 0);
    v13 = *(_QWORD *)(*((_QWORD *)a1 + 7) + 104LL);
    if ( *(_BYTE *)(*(_QWORD *)v13 + 95LL) == 32 )
    {
      if ( *(_QWORD *)(v13 + 8) )
        v13 = *(_QWORD *)(v13 + 8);
      if ( (*(_WORD *)(v13 + 112) & 0x800) != 0 )
        EnableScrollBar(v10, 3u, 3u);
    }
    if ( *((_DWORD *)a1 + 53) == 3 )
    {
      v14 = *((_QWORD *)a1 + 7);
      if ( v14 )
      {
        if ( *(_QWORD *)(v14 + 168) )
        {
          v15 = *(_QWORD *)(*(_QWORD *)(v14 + 168) + 264LL);
          (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v15 + 200LL))(v15, v27);
          v16 = DPIMGR::DpiX((DPIMGR *)&g_dpiMgr);
          if ( !(unsigned int)RoundDiv(v28, 0x5A0 / v16) )
          {
            v17 = DPIMGR::DpiY((DPIMGR *)&g_dpiMgr);
            if ( !(unsigned int)RoundDiv(v29, 0x5A0 / v17) )
            {
              GetClientRect(v10, &Rect);
              Rect.right -= Rect.left;
              Rect.bottom -= Rect.top;
              *(_QWORD *)&Rect.left = 0;
              PLOT::SetRECT((PLOT *)(v15 + 624), &Rect);
            }
          }
        }
      }
    }
    PostMessageA(Main_hwndMainMenu, 0x1043u, 0, 0);
    FDesSetFormSelected(v10, 1);
    ExtIDEWindowsOnAddHwnd(v10, 1);
  }
  return v10;
}

```

## disassembly

```asm
0x180093430  mov     [rsp-8+arg_8], rbx
0x180093435  mov     [rsp-8+arg_10], rsi
0x18009343a  push    rbp
0x18009343b  push    rdi
0x18009343c  push    r12
0x18009343e  push    r14
0x180093440  push    r15
0x180093442  lea     rbp, [rsp-37h]
0x180093447  mov     eax, 0D0h
0x18009344c  call    _alloca_probe
0x180093451  sub     rsp, rax
0x180093454  mov     rax, cs:__security_cookie
0x18009345b  xor     rax, rsp
0x18009345e  mov     [rbp+57h+var_30], rax
0x180093462  lea     rsi, [rcx+98h]
0x180093469  mov     rdi, rcx
0x18009346c  mov     rcx, rsi; lprc
0x18009346f  call    cs:__imp_IsRectEmpty
0x180093475  xor     r12d, r12d
0x180093478  test    eax, eax
0x18009347a  jz      short loc_18009348B
0x18009347c  mov     ebx, 80000000h
0x180093481  mov     r15d, ebx
0x180093484  mov     esi, ebx
0x180093486  mov     r14d, ebx
0x180093489  jmp     short loc_18009349D
0x18009348b  mov     r15d, [rsi]
0x18009348e  mov     r14d, [rsi+8]
0x180093492  mov     ebx, [rsi+4]
0x180093495  mov     esi, [rsi+0Ch]
0x180093498  sub     r14d, r15d
0x18009349b  sub     esi, ebx
0x18009349d  movzx   eax, cs:word_1803FAC28
0x1800934a4  test    ax, ax
0x1800934a7  jnz     loc_18009352F
0x1800934ad  xor     edx, edx; Val
0x1800934af  lea     rcx, [rbp+57h+var_A0]; void *
0x1800934b3  lea     r8d, [rdx+48h]; Size
0x1800934b7  call    memset_0
0x1800934bc  mov     rax, cs:?Rby_hinstExe@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * Rby_hinstExe
0x1800934c3  lea     r11, ?FDesignerWndProc@@YA_JPEAUHWND__@@I_K_J@Z; FDesignerWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x1800934ca  mov     edx, 7F00h; lpCursorName
0x1800934cf  xor     ecx, ecx; hInstance
0x1800934d1  mov     [rbp+57h+var_88], rax
0x1800934d5  mov     [rbp+57h+var_98], r11
0x1800934d9  mov     [rbp+57h+var_8C], 8
0x1800934e0  call    cs:__imp_LoadCursorA
0x1800934e6  mov     rcx, cs:?Rby_hmodThun@@3PEAUHINSTANCE__@@EA; hInstance
0x1800934ed  mov     [rbp+57h+var_78], rax
0x1800934f1  lea     rax, aDesignerwindow; "DesignerWindow"
0x1800934f8  mov     edx, 4B1h; lpIconName
0x1800934fd  mov     [rbp+57h+var_60], rax
0x180093501  mov     [rbp+57h+var_70], 6
0x180093509  call    cs:__imp_LoadIconA
0x18009350f  lea     rcx, [rbp+57h+var_A0]
0x180093513  mov     [rbp+57h+var_80], rax
0x180093517  call    IsolationAwareRegisterClassA
0x18009351c  mov     cs:word_1803FAC28, ax
0x180093523  test    ax, ax
0x180093526  jnz     short loc_18009352F
0x180093528  xor     eax, eax
0x18009352a  jmp     loc_180093714
0x18009352f  mov     [rsp+0F0h+lParam], r12; lParam
0x180093534  movzx   ecx, ax; lpClassName
0x180093537  mov     rax, cs:?Rby_hinstExe@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * Rby_hinstExe
0x18009353e  mov     [rsp+0F0h+hInstance], rax; hInstance
0x180093543  mov     rax, cs:?Main_hwndMdi@@3PEAUHWND__@@EA; HWND__ * Main_hwndMdi
0x18009354a  mov     r9d, r15d; X
0x18009354d  mov     [rsp+0F0h+hWndParent], rax; hWndParent
0x180093552  mov     [rsp+0F0h+nHeight], esi; nHeight
0x180093556  xor     edx, edx; lpWindowName
0x180093558  mov     r8d, 46CF0000h; dwStyle
0x18009355e  mov     [rsp+0F0h+nWidth], r14d; nWidth
0x180093563  mov     [rsp+0F0h+Y], ebx; Y
0x180093567  call    cs:__imp_CreateMDIWindowA
0x18009356d  mov     rbx, rax
0x180093570  test    rax, rax
0x180093573  jz      loc_180093711
0x180093579  mov     r8, rdi; dwNewLong
0x18009357c  xor     edx, edx; nIndex
0x18009357e  mov     rcx, rax; hWnd
0x180093581  call    cs:__imp_SetWindowLongPtrA
0x180093587  cmp     cs:?Sys_fWin95Shell@@3HA, r12d; int Sys_fWin95Shell
0x18009358e  mov     r14d, 1
0x180093594  jz      short loc_1800935DB
0x180093596  mov     rcx, [rdi+38h]
0x18009359a  xor     edx, edx; int
0x18009359c  mov     rcx, [rcx+68h]; struct XMOD *
0x1800935a0  call    ?HiconDefault@@YAPEAUHICON__@@PEAUXMOD@@H@Z; HiconDefault(XMOD *,int)
0x1800935a5  lea     esi, [r14+7Fh]
0x1800935a9  mov     r8d, r14d; wParam
0x1800935ac  mov     r9, rax; lParam
0x1800935af  mov     edx, esi; Msg
0x1800935b1  mov     rcx, rbx; hWnd
0x1800935b4  call    cs:__imp_SendMessageA
0x1800935ba  mov     rcx, [rdi+38h]
0x1800935be  mov     edx, r14d; int
0x1800935c1  mov     rcx, [rcx+68h]; struct XMOD *
0x1800935c5  call    ?HiconDefault@@YAPEAUHICON__@@PEAUXMOD@@H@Z; HiconDefault(XMOD *,int)
0x1800935ca  xor     r8d, r8d; wParam
0x1800935cd  mov     edx, esi; Msg
0x1800935cf  mov     r9, rax; lParam
0x1800935d2  mov     rcx, rbx; hWnd
0x1800935d5  call    cs:__imp_SendMessageA
0x1800935db  xor     r8d, r8d; int
0x1800935de  mov     rdx, rbx; HWND
0x1800935e1  mov     rcx, rdi; struct Projitem *
0x1800935e4  call    ?ProjNotifyWinChanged@@YAXPEAVProjitem@@PEAUHWND__@@H@Z; ProjNotifyWinChanged(Projitem *,HWND__ *,int)
0x1800935e9  mov     rax, [rdi+38h]
0x1800935ed  mov     esi, 3
0x1800935f2  mov     rcx, [rax+68h]
0x1800935f6  mov     rax, [rcx]
0x1800935f9  cmp     byte ptr [rax+5Fh], 20h ; ' '
0x1800935fd  jnz     short loc_180093623
0x1800935ff  mov     rax, [rcx+8]
0x180093603  test    rax, rax
0x180093606  cmovnz  rcx, rax
0x18009360a  mov     eax, 800h
0x18009360f  test    [rcx+70h], ax
0x180093613  jz      short loc_180093623
0x180093615  mov     r8d, esi; wArrows
0x180093618  mov     edx, esi; wSBflags
0x18009361a  mov     rcx, rbx; hWnd
0x18009361d  call    cs:__imp_EnableScrollBar
0x180093623  cmp     [rdi+0D4h], esi
0x180093629  jnz     loc_1800936E3
0x18009362f  mov     rax, [rdi+38h]
0x180093633  test    rax, rax
0x180093636  jz      loc_1800936E3
0x18009363c  cmp     [rax+0A8h], r12
0x180093643  jz      loc_1800936E3
0x180093649  mov     rax, [rax+0A8h]
0x180093650  lea     rdx, [rbp+57h+var_40]
0x180093654  mov     rdi, [rax+108h]
0x18009365b  mov     rcx, rdi
0x18009365e  mov     rax, [rdi]
0x180093661  call    qword ptr [rax+0C8h]
0x180093667  lea     rcx, ?g_dpiMgr@@3VDPIMGR@@A; this
0x18009366e  call    ?DpiX@DPIMGR@@QEAAIXZ; DPIMGR::DpiX(void)
0x180093673  mov     ecx, [rbp+57h+var_38]; int
0x180093676  xor     edx, edx
0x180093678  mov     r11d, eax
0x18009367b  mov     esi, 5A0h
0x180093680  mov     eax, esi
0x180093682  div     r11d
0x180093685  mov     edx, eax; int
0x180093687  call    ?RoundDiv@@YAHJJ@Z; RoundDiv(long,long)
0x18009368c  test    eax, eax
0x18009368e  jnz     short loc_1800936E3
0x180093690  lea     rcx, ?g_dpiMgr@@3VDPIMGR@@A; this
0x180093697  call    ?DpiY@DPIMGR@@QEAAIXZ; DPIMGR::DpiY(void)
0x18009369c  mov     ecx, [rbp+57h+var_34]; int
0x18009369f  xor     edx, edx
0x1800936a1  mov     r11d, eax
0x1800936a4  mov     eax, esi
0x1800936a6  div     r11d
0x1800936a9  mov     edx, eax; int
0x1800936ab  call    ?RoundDiv@@YAHJJ@Z; RoundDiv(long,long)
0x1800936b0  test    eax, eax
0x1800936b2  jnz     short loc_1800936E3
0x1800936b4  lea     rdx, [rbp+57h+Rect]; lpRect
0x1800936b8  mov     rcx, rbx; hWnd
0x1800936bb  call    cs:__imp_GetClientRect
0x1800936c1  mov     r11d, [rbp+57h+Rect.left]
0x1800936c5  mov     eax, [rbp+57h+Rect.top]
0x1800936c8  sub     [rbp+57h+Rect.right], r11d
0x1800936cc  sub     [rbp+57h+Rect.bottom], eax
0x1800936cf  lea     rcx, [rdi+270h]; this
0x1800936d6  lea     rdx, [rbp+57h+Rect]; struct tagRECT *
0x1800936da  mov     qword ptr [rbp+57h+Rect.left], r12
0x1800936de  call    ?SetRECT@PLOT@@QEAAXPEBUtagRECT@@@Z; PLOT::SetRECT(tagRECT const *)
0x1800936e3  mov     rcx, cs:?Main_hwndMainMenu@@3PEAUHWND__@@EA; hWnd
0x1800936ea  xor     r9d, r9d; lParam
0x1800936ed  xor     r8d, r8d; wParam
0x1800936f0  mov     edx, 1043h; Msg
0x1800936f5  call    cs:__imp_PostMessageA
0x1800936fb  mov     edx, r14d; int
0x1800936fe  mov     rcx, rbx; HWND
0x180093701  call    ?FDesSetFormSelected@@YAXPEAUHWND__@@H@Z; FDesSetFormSelected(HWND__ *,int)
0x180093706  mov     edx, r14d
0x180093709  mov     rcx, rbx
0x18009370c  call    ExtIDEWindowsOnAddHwnd
0x180093711  mov     rax, rbx
0x180093714  mov     rcx, [rbp+57h+var_30]
0x180093718  xor     rcx, rsp; StackCookie
0x18009371b  call    __security_check_cookie
0x180093720  lea     r11, [rsp+0F0h+var_20]
0x180093728  mov     rbx, [r11+38h]
0x18009372c  mov     rsi, [r11+40h]
0x180093730  mov     rsp, r11
0x180093733  pop     r15
0x180093735  pop     r14
0x180093737  pop     r12
0x180093739  pop     rdi
0x18009373a  pop     rbp
0x18009373b  retn
```
