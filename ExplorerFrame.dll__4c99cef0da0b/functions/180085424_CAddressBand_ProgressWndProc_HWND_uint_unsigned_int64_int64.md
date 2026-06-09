# CAddressBand::_ProgressWndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180085424`
- end: `0x180085905`
- name: `?_ProgressWndProc@CAddressBand@@AEAA_JPEAUHWND__@@I_K_J@Z`
- size: `1249`
- prototype: `__int64 __fastcall(CAddressBand *__hidden this, HWND hWnd, UINT Msg, HDC hdc, LPARAM lParam)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1800853a0`

## callees

- `0x180039718`
- `0x18003cbc8`
- `0x180045ce0`
- `0x180084a8c`
- `0x180085424`
- `0x18008590c`
- `0x1800859c4`
- `0x1800867b0`
- `0x1800872a4`
- `0x18012e0ac`
- `0x18013f7d0`
- `0x18014e2a8`
- `0x180210010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18008553c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18008564b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18008573c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800857e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800858d0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18008553c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18008564b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18008573c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800857e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800858d0`
- `USER32!EndPaint` at `0x1800856f5`
- `USER32!EndPaint` at `0x1800856f5`
- `USER32!BeginPaint` at `0x180085711`
- `USER32!BeginPaint` at `0x180085711`
- `USER32!SendMessageW` at `0x180085512`
- `USER32!SendMessageW` at `0x1800857ba`
- `USER32!SendMessageW` at `0x18008584e`
- `USER32!SendMessageW` at `0x180085512`
- `USER32!SendMessageW` at `0x1800857ba`
- `USER32!SendMessageW` at `0x18008584e`
- `USER32!KillTimer` at `0x180085736`
- `USER32!KillTimer` at `0x180085800`
- `USER32!KillTimer` at `0x1800858a4`
- `USER32!KillTimer` at `0x180085736`
- `USER32!KillTimer` at `0x180085800`
- `USER32!KillTimer` at `0x1800858a4`
- `USER32!SetTimer` at `0x18008575a`
- `USER32!SetTimer` at `0x18008575a`
- `USER32!GetClientRect` at `0x1800855cb`
- `USER32!GetClientRect` at `0x1800855cb`
- `USER32!SetRectEmpty` at `0x1800858c5`
- `USER32!SetRectEmpty` at `0x1800858c5`
- `GDI32!DeleteDC` at `0x1800856dc`
- `GDI32!DeleteDC` at `0x1800856dc`
- `GDI32!GdiAlphaBlend` at `0x1800856be`
- `GDI32!GdiAlphaBlend` at `0x1800856be`
- `GDI32!CreateCompatibleBitmap` at `0x1800855fd`
- `GDI32!CreateCompatibleBitmap` at `0x1800855fd`
- `GDI32!DeleteObject` at `0x1800856d3`
- `GDI32!DeleteObject` at `0x1800856d3`
- `GDI32!SelectObject` at `0x180085615`
- `GDI32!SelectObject` at `0x1800856ca`
- `GDI32!SelectObject` at `0x180085615`
- `GDI32!SelectObject` at `0x1800856ca`
- `GDI32!CreateCompatibleDC` at `0x1800855d5`
- `GDI32!CreateCompatibleDC` at `0x1800855d5`
- `GDI32!GetClipBox` at `0x180085587`
- `GDI32!GetClipBox` at `0x180085587`
- `UxTheme!DrawThemeParentBackground` at `0x1800855a8`
- `UxTheme!DrawThemeParentBackground` at `0x1800855a8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAddressBand::_ProgressWndProc(CAddressBand *this, HWND hWnd, UINT Msg, HDC hdc, LPARAM lParam)
{
  int IsProgressShowing; // r14d
  __int64 (__fastcall *v10)(HWND, _QWORD, HDC, LPARAM); // rax
  __int64 v12; // rdi
  HDC hdcSrc; // rsi
  HBITMAP CompatibleBitmap; // rax
  HBITMAP v16; // r14
  HGDIOBJ v17; // r12
  int v18; // r15d
  int v19; // ebx
  DWORD v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // ecx
  BLENDFUNCTION ftn; // [rsp+60h] [rbp-A0h]
  struct tagRECT Rect; // [rsp+68h] [rbp-98h] BYREF
  struct tagPAINTSTRUCT hdca; // [rsp+80h] [rbp-80h] BYREF
  HWND hwnd; // [rsp+C8h] [rbp-38h]
  _QWORD v27[42]; // [rsp+D0h] [rbp-30h] BYREF

  IsProgressShowing = CAddressBand::_IsProgressShowing(this);
  if ( Msg == 2 )
  {
    RemoveWindowSubclass(*((HWND *)this + 20), CAddressBand::s_ProgressWndProc, (UINT_PTR)this);
    goto LABEL_9;
  }
  if ( Msg != 15 )
  {
    switch ( Msg )
    {
      case 0x14u:
        return 1;
      case 0x4Eu:
      case 0x111u:
        return SendMessageW(*((HWND *)this + 9), Msg, (WPARAM)hdc, lParam);
      case 0x113u:
        if ( hdc == (HDC)10 )
        {
          KillTimer(*((HWND *)this + 20), 0xAu);
          if ( !*((_DWORD *)this + 79) )
          {
            SendMessageW(*((HWND *)this + 20), 0x402u, *((int *)this + 101), 0);
            if ( **((_DWORD **)this + 93) != 1 )
              CAddressBand::StartAddressGreenBarActivity(this);
          }
          *((_DWORD *)this + 79) = 1;
          CAddressBand::_ButtonSwitch(this, 1);
          *((_DWORD *)this + 99) = GetTickCount();
        }
        else if ( hdc == (HDC)11 )
        {
          KillTimer(*((HWND *)this + 20), 0xBu);
          *((_DWORD *)this + 100) = GetTickCount();
          SetTimer(*((HWND *)this + 20), 0xCu, 0x19u, 0);
        }
        else if ( hdc == (HDC)12 && GetTickCount() - *((_DWORD *)this + 100) > g_dwProgressFadeOutTime )
        {
          KillTimer(*((HWND *)this + 20), 0xCu);
          CAddressBand::_ButtonSwitch(this, 2);
          *((_DWORD *)this + 79) = 0;
          *(_QWORD *)((char *)this + 396) = 0;
          *((_DWORD *)this + 98) = 0;
          *((_DWORD *)this + 101) = 0;
          SendMessageW(*((HWND *)this + 20), 0x402u, 0, 0);
          if ( **((_DWORD **)this + 93) == 1 )
          {
            wil::ActivityBase<FileExplorerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FileExplorerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v27);
            v27[0] = &FileExplorerTelemetry::AddressGreenBar::`vftable';
            wil::ActivityBase<FileExplorerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v27);
            FileExplorerTelemetry::AddressGreenBar::~AddressGreenBar((FileExplorerTelemetry::AddressGreenBar *)v27);
          }
        }
        if ( IsProgressShowing )
          CAddressBand::_OnBackgroundStateChanged(this);
        goto LABEL_9;
      case 0x210u:
        return SendMessageW(*((HWND *)this + 9), Msg, (WPARAM)hdc, lParam);
    }
    if ( Msg != 792 )
    {
LABEL_9:
      v10 = (__int64 (__fastcall *)(HWND, _QWORD, HDC, LPARAM))qword_180291318;
      if ( qword_180291318 == -1 )
      {
        GetProcFromComCtl32(&qword_180291318, 413);
        v10 = (__int64 (__fastcall *)(HWND, _QWORD, HDC, LPARAM))qword_180291318;
      }
      if ( !v10 )
        return 0;
      return v10(hWnd, Msg, hdc, lParam);
    }
  }
  hwnd = hWnd;
  v12 = 1;
  if ( hdc )
  {
    hdca.hdc = hdc;
    if ( !GetClipBox(hdc, &hdca.rcPaint) )
      SetRectEmpty(&hdca.rcPaint);
    hdca.fRestore = 0;
  }
  else
  {
    BeginPaint(hWnd, &hdca);
    hdca.fRestore = 1;
  }
  DrawThemeParentBackground(hwnd, hdca.hdc, &hdca.rcPaint);
  if ( IsProgressShowing )
  {
    Rect = 0;
    GetClientRect(*((HWND *)this + 20), &Rect);
    hdcSrc = CreateCompatibleDC(hdca.hdc);
    if ( hdcSrc )
    {
      CompatibleBitmap = CreateCompatibleBitmap(hdca.hdc, Rect.right - Rect.left, Rect.bottom - Rect.top);
      v16 = CompatibleBitmap;
      if ( CompatibleBitmap )
      {
        v17 = SelectObject(hdcSrc, CompatibleBitmap);
        DefSubclassProc(hWnd, 0x318u, (WPARAM)hdcSrc, lParam);
        v18 = *((_DWORD *)this + 100);
        if ( v18 )
        {
          v22 = GetTickCount() - v18;
          if ( v22 <= g_dwProgressFadeOutTime )
            v21 = g_dwProgressAlpha * (g_dwProgressFadeOutTime - v22) / g_dwProgressFadeOutTime;
          else
            LOBYTE(v21) = 0;
        }
        else
        {
          v19 = *((_DWORD *)this + 98);
          v20 = GetTickCount() - v19 - g_dwProgressDelayUntilShow;
          if ( v20 <= g_dwProgressFadeInTime )
            v21 = g_dwProgressAlpha * v20 / g_dwProgressFadeInTime;
          else
            LOBYTE(v21) = g_dwProgressAlpha;
        }
        ftn = 0;
        ftn.SourceConstantAlpha = v21;
        GdiAlphaBlend(
          hdca.hdc,
          0,
          0,
          Rect.right - Rect.left,
          Rect.bottom - Rect.top,
          hdcSrc,
          0,
          0,
          Rect.right - Rect.left,
          Rect.bottom - Rect.top,
          ftn);
        SelectObject(hdcSrc, v17);
        DeleteObject(v16);
      }
      DeleteDC(hdcSrc);
    }
  }
  if ( hdca.fRestore )
    EndPaint(hwnd, &hdca);
  return v12;
}

```

## disassembly

```asm
0x180085424  push    rbp
0x180085426  push    rbx
0x180085427  push    rsi
0x180085428  push    rdi
0x180085429  push    r12
0x18008542b  push    r14
0x18008542d  push    r15
0x18008542f  lea     rbp, [rsp-130h]
0x180085437  sub     rsp, 230h
0x18008543e  mov     rax, cs:__security_cookie
0x180085445  xor     rax, rsp
0x180085448  mov     [rbp+160h+var_40], rax
0x18008544f  mov     rsi, r9
0x180085452  mov     r12d, r8d
0x180085455  mov     r15, rdx
0x180085458  mov     rbx, rcx
0x18008545b  call    ?_IsProgressShowing@CAddressBand@@AEAAHXZ; CAddressBand::_IsProgressShowing(void)
0x180085460  mov     r14d, eax
0x180085463  mov     ecx, r12d
0x180085466  sub     ecx, 2
0x180085469  jz      loc_180085765
0x18008546f  sub     ecx, 0Dh
0x180085472  jz      loc_18008556A
0x180085478  sub     ecx, 5
0x18008547b  jz      loc_180085700
0x180085481  sub     ecx, 3Ah ; ':'
0x180085484  jz      short loc_180085501
0x180085486  sub     ecx, 0C3h
0x18008548c  jz      short loc_180085501
0x18008548e  sub     ecx, 2
0x180085491  jz      loc_18008551A
0x180085497  sub     ecx, 0FDh
0x18008549d  jz      short loc_180085501
0x18008549f  cmp     ecx, 108h
0x1800854a5  jz      loc_18008556A
0x1800854ab  mov     rax, cs:qword_180291318
0x1800854b2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800854b6  jz      loc_180085787
0x1800854bc  test    rax, rax
0x1800854bf  jz      loc_180085780
0x1800854c5  mov     r9, [rbp+160h+lParam]
0x1800854cc  mov     r8, rsi
0x1800854cf  mov     edx, r12d
0x1800854d2  mov     rcx, r15
0x1800854d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800854da  mov     rdi, rax
0x1800854dd  mov     rax, rdi
0x1800854e0  mov     rcx, [rbp+160h+var_40]
0x1800854e7  xor     rcx, rsp; StackCookie
0x1800854ea  call    __security_check_cookie
0x1800854ef  add     rsp, 230h
0x1800854f6  pop     r15
0x1800854f8  pop     r14
0x1800854fa  pop     r12
0x1800854fc  pop     rdi
0x1800854fd  pop     rsi
0x1800854fe  pop     rbx
0x1800854ff  pop     rbp
0x180085500  retn
0x180085501  mov     r9, [rbp+160h+lParam]; lParam
0x180085508  mov     r8, rsi; wParam
0x18008550b  mov     edx, r12d; Msg
0x18008550e  mov     rcx, [rbx+48h]; hWnd
0x180085512  call    cs:__imp_SendMessageW
0x180085518  jmp     short loc_1800854DA
0x18008551a  mov     edx, 0Ah; uIDEvent
0x18008551f  cmp     rsi, rdx
0x180085522  jz      loc_18008589D
0x180085528  mov     edx, 0Bh; uIDEvent
0x18008552d  cmp     rsi, rdx
0x180085530  jz      loc_18008572F
0x180085536  cmp     rsi, 0Ch
0x18008553a  jnz     short loc_180085554
0x18008553c  call    cs:__imp_GetTickCount
0x180085542  sub     eax, [rbx+190h]
0x180085548  cmp     eax, cs:?g_dwProgressFadeOutTime@@3KA; ulong g_dwProgressFadeOutTime
0x18008554e  ja      loc_1800857F4
0x180085554  test    r14d, r14d
0x180085557  jz      loc_1800854AB
0x18008555d  mov     rcx, rbx; this
0x180085560  call    ?_OnBackgroundStateChanged@CAddressBand@@AEAAXXZ; CAddressBand::_OnBackgroundStateChanged(void)
0x180085565  jmp     loc_1800854AB
0x18008556a  mov     [rbp+160h+hwnd], r15
0x18008556e  mov     edi, 1
0x180085573  test    rsi, rsi
0x180085576  jz      loc_18008570A
0x18008557c  mov     [rbp+160h+hdc], rsi
0x180085580  lea     rdx, [rbp+160h+rect]; lprect
0x180085584  mov     rcx, rsi; hdc
0x180085587  call    cs:__imp_GetClipBox
0x18008558d  test    eax, eax
0x18008558f  jz      loc_1800858C1
0x180085595  mov     [rbp+160h+var_1C4], 0
0x18008559c  lea     r8, [rbp+160h+rect]; prc
0x1800855a0  mov     rdx, [rbp+160h+hdc]; hdc
0x1800855a4  mov     rcx, [rbp+160h+hwnd]; hwnd
0x1800855a8  call    cs:__imp_DrawThemeParentBackground
0x1800855ae  test    r14d, r14d
0x1800855b1  jz      loc_1800856E3
0x1800855b7  xorps   xmm0, xmm0
0x1800855ba  movups  xmmword ptr [rsp+260h+Rect.left], xmm0
0x1800855bf  lea     rdx, [rsp+260h+Rect]; lpRect
0x1800855c4  mov     rcx, [rbx+0A0h]; hWnd
0x1800855cb  call    cs:__imp_GetClientRect
0x1800855d1  mov     rcx, [rbp+160h+hdc]; hdc
0x1800855d5  call    cs:__imp_CreateCompatibleDC
0x1800855db  mov     rsi, rax
0x1800855de  test    rax, rax
0x1800855e1  jz      loc_1800856E3
0x1800855e7  mov     r8d, [rsp+260h+Rect.bottom]
0x1800855ec  sub     r8d, [rsp+260h+Rect.top]; cy
0x1800855f1  mov     edx, [rsp+260h+Rect.right]
0x1800855f5  sub     edx, [rsp+260h+Rect.left]; cx
0x1800855f9  mov     rcx, [rbp+160h+hdc]; hdc
0x1800855fd  call    cs:__imp_CreateCompatibleBitmap
0x180085603  mov     r14, rax
0x180085606  test    rax, rax
0x180085609  jz      loc_1800856D9
0x18008560f  mov     rdx, rax; h
0x180085612  mov     rcx, rsi; hdc
0x180085615  call    cs:__imp_SelectObject
0x18008561b  mov     r12, rax
0x18008561e  mov     r9, [rbp+160h+lParam]; lParam
0x180085625  mov     r8, rsi; wParam
0x180085628  mov     edx, 318h; uMsg
0x18008562d  mov     rcx, r15; hWnd
0x180085630  call    DefSubclassProc
0x180085635  mov     r15d, [rbx+190h]
0x18008563c  test    r15d, r15d
0x18008563f  jnz     loc_1800858D0
0x180085645  mov     ebx, [rbx+188h]
0x18008564b  call    cs:__imp_GetTickCount
0x180085651  sub     eax, ebx
0x180085653  sub     eax, cs:?g_dwProgressDelayUntilShow@@3KA; ulong g_dwProgressDelayUntilShow
0x180085659  mov     ecx, cs:?g_dwProgressFadeInTime@@3KA; ulong g_dwProgressFadeInTime
0x18008565f  cmp     eax, ecx
0x180085661  jbe     loc_18008571F
0x180085667  mov     eax, cs:?g_dwProgressAlpha@@3KA; ulong g_dwProgressAlpha
0x18008566d  mov     dword ptr [rsp+260h+var_200.BlendOp], 0
0x180085675  mov     [rsp+260h+var_200.SourceConstantAlpha], al
0x180085679  mov     ecx, [rsp+260h+Rect.bottom]
0x18008567d  sub     ecx, [rsp+260h+Rect.top]
0x180085681  mov     r9d, [rsp+260h+Rect.right]
0x180085686  sub     r9d, [rsp+260h+Rect.left]; wDest
0x18008568b  mov     eax, dword ptr [rsp+260h+var_200.BlendOp]
0x18008568f  mov     dword ptr [rsp+260h+ftn.BlendOp], eax; ftn
0x180085693  mov     [rsp+260h+hSrc], ecx; hSrc
0x180085697  mov     [rsp+260h+wSrc], r9d; wSrc
0x18008569c  mov     [rsp+260h+yoriginSrc], 0; yoriginSrc
0x1800856a4  mov     [rsp+260h+xoriginSrc], 0; xoriginSrc
0x1800856ac  mov     [rsp+260h+hdcSrc], rsi; hdcSrc
0x1800856b1  mov     [rsp+260h+hDest], ecx; hDest
0x1800856b5  xor     r8d, r8d; yoriginDest
0x1800856b8  xor     edx, edx; xoriginDest
0x1800856ba  mov     rcx, [rbp+160h+hdc]; hdcDest
0x1800856be  call    cs:__imp_GdiAlphaBlend
0x1800856c4  mov     rdx, r12; h
0x1800856c7  mov     rcx, rsi; hdc
0x1800856ca  call    cs:__imp_SelectObject
0x1800856d0  mov     rcx, r14; ho
0x1800856d3  call    cs:__imp_DeleteObject
0x1800856d9  mov     rcx, rsi; hdc
0x1800856dc  call    cs:__imp_DeleteDC
0x1800856e2  nop
0x1800856e3  cmp     [rbp+160h+var_1C4], 0
0x1800856e7  jz      loc_1800854DD
0x1800856ed  lea     rdx, [rbp+160h+hdc]; lpPaint
0x1800856f1  mov     rcx, [rbp+160h+hwnd]; hWnd
0x1800856f5  call    cs:__imp_EndPaint
0x1800856fb  jmp     loc_1800854DD
0x180085700  mov     edi, 1
0x180085705  jmp     loc_1800854DD
0x18008570a  lea     rdx, [rbp+160h+hdc]; lpPaint
0x18008570e  mov     rcx, r15; hWnd
0x180085711  call    cs:__imp_BeginPaint
0x180085717  mov     [rbp+160h+var_1C4], edi
0x18008571a  jmp     loc_18008559C
0x18008571f  imul    eax, cs:?g_dwProgressAlpha@@3KA; ulong g_dwProgressAlpha
0x180085726  xor     edx, edx
0x180085728  div     ecx
0x18008572a  jmp     loc_18008566D
0x18008572f  mov     rcx, [rbx+0A0h]; hWnd
0x180085736  call    cs:__imp_KillTimer
0x18008573c  call    cs:__imp_GetTickCount
0x180085742  mov     [rbx+190h], eax
0x180085748  xor     r9d, r9d; lpTimerFunc
0x18008574b  lea     edx, [r9+0Ch]; nIDEvent
0x18008574f  lea     r8d, [r9+19h]; uElapse
0x180085753  mov     rcx, [rbx+0A0h]; hWnd
0x18008575a  call    cs:__imp_SetTimer
0x180085760  jmp     loc_180085554
0x180085765  mov     r8, rbx; uIdSubclass
0x180085768  lea     rdx, ?s_ProgressWndProc@CAddressBand@@CA_JPEAUHWND__@@I_K_J11@Z; pfnSubclass
0x18008576f  mov     rcx, [rbx+0A0h]; hWnd
0x180085776  call    RemoveWindowSubclass
0x18008577b  jmp     loc_1800854AB
0x180085780  xor     edi, edi
0x180085782  jmp     loc_1800854DD
0x180085787  mov     edx, 19Dh
0x18008578c  lea     rcx, qword_180291318
0x180085793  call    _GetProcFromComCtl32
0x180085798  mov     rax, cs:qword_180291318
0x18008579f  jmp     loc_1800854BC
0x1800857a4  movsxd  r8, dword ptr [rbx+194h]; wParam
0x1800857ab  xor     r9d, r9d; lParam
0x1800857ae  mov     edx, 402h; Msg
0x1800857b3  mov     rcx, [rbx+0A0h]; hWnd
0x1800857ba  call    cs:__imp_SendMessageW
0x1800857c0  mov     rax, [rbx+2E8h]
0x1800857c7  cmp     [rax], edi
0x1800857c9  jz      short loc_1800857D3
0x1800857cb  mov     rcx, rbx; this
0x1800857ce  call    ?StartAddressGreenBarActivity@CAddressBand@@AEAAXXZ; CAddressBand::StartAddressGreenBarActivity(void)
0x1800857d3  mov     [rbx+13Ch], edi
0x1800857d9  mov     edx, edi
0x1800857db  mov     rcx, rbx
0x1800857de  call    ?_ButtonSwitch@CAddressBand@@AEAAXW4ENUMBUTTONTYPE@@@Z; CAddressBand::_ButtonSwitch(ENUMBUTTONTYPE)
0x1800857e3  call    cs:__imp_GetTickCount
0x1800857e9  mov     [rbx+18Ch], eax
0x1800857ef  jmp     loc_180085554
0x1800857f4  mov     edx, 0Ch; uIDEvent
0x1800857f9  mov     rcx, [rbx+0A0h]; hWnd
0x180085800  call    cs:__imp_KillTimer
0x180085806  mov     edx, 2
0x18008580b  mov     rcx, rbx
0x18008580e  call    ?_ButtonSwitch@CAddressBand@@AEAAXW4ENUMBUTTONTYPE@@@Z; CAddressBand::_ButtonSwitch(ENUMBUTTONTYPE)
0x180085813  mov     dword ptr [rbx+13Ch], 0
0x18008581d  mov     qword ptr [rbx+18Ch], 0
0x180085828  mov     dword ptr [rbx+188h], 0
0x180085832  mov     dword ptr [rbx+194h], 0
0x18008583c  xor     r9d, r9d; lParam
0x18008583f  xor     r8d, r8d; wParam
0x180085842  mov     edx, 402h; Msg
0x180085847  mov     rcx, [rbx+0A0h]; hWnd
0x18008584e  call    cs:__imp_SendMessageW
0x180085854  mov     rax, [rbx+2E8h]
0x18008585b  mov     edi, 1
0x180085860  cmp     [rax], edi
0x180085862  jnz     loc_180085554
0x180085868  lea     rdx, [rbx+1D8h]
0x18008586f  mov     r8b, dil
0x180085872  lea     rcx, [rbp+160h+var_190]; struct wil::details::IFailureCallback *
0x180085876  call    ??0?$ActivityBase@VFileExplorerLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@$$QEAV01@_N@Z; wil::ActivityBase<FileExplorerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<FileExplorerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<FileExplorerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType> &&,bool)
0x18008587b  lea     rax, ??_7AddressGreenBar@FileExplorerTelemetry@@6B@; const FileExplorerTelemetry::AddressGreenBar::`vftable'
0x180085882  mov     [rbp+160h+var_190], rax
0x180085886  lea     rcx, [rbp+160h+var_190]
0x18008588a  call    ?Stop@?$ActivityBase@VFileExplorerLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<FileExplorerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18008588f  lea     rcx, [rbp+160h+var_190]; this
0x180085893  call    ??1AddressGreenBar@FileExplorerTelemetry@@QEAA@XZ; FileExplorerTelemetry::AddressGreenBar::~AddressGreenBar(void)
0x180085898  jmp     loc_180085554
0x18008589d  mov     rcx, [rbx+0A0h]; hWnd
0x1800858a4  call    cs:__imp_KillTimer
0x1800858aa  mov     edi, 1
0x1800858af  cmp     dword ptr [rbx+13Ch], 0
0x1800858b6  jnz     loc_1800857D3
0x1800858bc  jmp     loc_1800857A4
0x1800858c1  lea     rcx, [rbp+160h+rect]; lprc
0x1800858c5  call    cs:__imp_SetRectEmpty
0x1800858cb  jmp     loc_180085595
0x1800858d0  call    cs:__imp_GetTickCount
0x1800858d6  mov     ecx, eax
0x1800858d8  sub     ecx, r15d
0x1800858db  mov     r8d, cs:?g_dwProgressFadeOutTime@@3KA; ulong g_dwProgressFadeOutTime
0x1800858e2  cmp     ecx, r8d
0x1800858e5  jbe     short loc_1800858EE
0x1800858e7  xor     eax, eax
0x1800858e9  jmp     loc_18008566D
0x1800858ee  mov     eax, r8d
0x1800858f1  sub     eax, ecx
0x1800858f3  imul    eax, cs:?g_dwProgressAlpha@@3KA; ulong g_dwProgressAlpha
0x1800858fa  xor     edx, edx
0x1800858fc  div     r8d
0x1800858ff  jmp     loc_18008566D
```
