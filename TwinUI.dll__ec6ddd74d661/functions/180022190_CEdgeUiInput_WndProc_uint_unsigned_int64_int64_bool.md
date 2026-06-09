# CEdgeUiInput::_WndProc(uint,unsigned __int64,__int64,bool)

- ea: `0x180022190`
- end: `0x180022aec`
- name: `?_WndProc@CEdgeUiInput@@AEAA_JI_K_J_N@Z`
- size: `2396`
- prototype: `__int64 __fastcall(CEdgeUiInput *__hidden this, UINT Msg, WPARAM wParam, LPCWSTR pszStr1, bool)`
- caller_count: `2`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800220f0`
- `0x1801f7650`

## callees

- `0x180009dd0`
- `0x180009dfc`
- `0x18001f144`
- `0x180022190`
- `0x180022af4`
- `0x180023134`
- `0x1800ab4f8`
- `0x1800b1718`
- `0x1800b76c4`
- `0x1800c35f0`
- `0x180114f74`
- `0x1801151c8`
- `0x18013fb20`
- `0x18013fc38`
- `0x1801f7c28`
- `0x1801f7cd0`
- `0x1801f7df4`
- `0x1801f7f00`
- `0x1801f804c`
- `0x1801f82fc`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180022340`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180022340`
- `USER32!GetPhysicalCursorPos` at `0x18002292a`
- `USER32!GetPhysicalCursorPos` at `0x18002292a`
- `USER32!WindowFromPhysicalPoint` at `0x180022941`
- `USER32!WindowFromPhysicalPoint` at `0x180022941`
- `USER32!TrackMouseEvent` at `0x180022298`
- `USER32!TrackMouseEvent` at `0x180022298`
- `USER32!GetCapture` at `0x180022956`
- `USER32!GetCapture` at `0x180022956`
- `USER32!IsIconic` at `0x1800223ca`
- `USER32!IsIconic` at `0x1800223ca`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!ScreenToClient` at `0x180022523`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!ScreenToClient` at `0x180022616`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!ScreenToClient` at `0x1800226fd`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!ScreenToClient` at `0x180022523`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!ScreenToClient` at `0x180022616`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!ScreenToClient` at `0x1800226fd`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DefWindowProcW` at `0x18002222a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DefWindowProcW` at `0x18002222a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!ShowWindow` at `0x1800223ea`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!ShowWindow` at `0x1800223ea`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetPropW` at `0x18002243b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetPropW` at `0x18002243b`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180022392`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180022392`
- `ext-ms-win-ntuser-private-l1-1-1!SetWindowCompositionAttribute` at `0x1800229a3`
- `ext-ms-win-ntuser-private-l1-1-1!SetWindowCompositionAttribute` at `0x1800229a3`
- `dwmapi!DwmShowContact` at `0x18002256b`
- `dwmapi!DwmShowContact` at `0x18002256b`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18002235b`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18002235b`
- `ext-ms-win-com-ole32-l1-1-2!RegisterDragDrop` at `0x18002245b`
- `ext-ms-win-com-ole32-l1-1-2!RegisterDragDrop` at `0x18002245b`
- `ext-ms-win-com-ole32-l1-1-2!RevokeDragDrop` at `0x180022480`
- `ext-ms-win-com-ole32-l1-1-2!RevokeDragDrop` at `0x180022480`

## string_xrefs

- `0x180022333`: `SettingsCacheChangeMessage`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
LRESULT __fastcall CEdgeUiInput::_WndProc(
        CEdgeUiInput *this,
        UINT Msg,
        WPARAM wParam,
        unsigned __int64 pszStr1,
        bool a5)
{
  __int64 v9; // rsi
  void *v11; // rcx
  IDropTarget *v12; // rdx
  __int64 v13; // rcx
  bool v14; // bl
  unsigned int v15; // r12d
  unsigned __int64 v16; // r15
  char v17; // bl
  char *v18; // rdx
  char *v19; // rdx
  char *v20; // rdx
  HWND v21; // rbx
  char *v22; // rdx
  void *ppvOut; // [rsp+30h] [rbp-40h] BYREF
  _QWORD v24[3]; // [rsp+38h] [rbp-38h] BYREF
  struct tagTRACKMOUSEEVENT EventTrack; // [rsp+50h] [rbp-20h] BYREF
  int v26; // [rsp+A8h] [rbp+38h] BYREF

  v9 = 0;
  if ( Msg == 675 )
  {
    if ( *((_DWORD *)this + 34) == 8 )
    {
      v26 = 1;
      v24[0] = 17;
      v24[1] = &v26;
      v24[2] = 4;
      SetWindowCompositionAttribute(*((_QWORD *)this + 18), v24);
    }
    if ( *((_QWORD *)this + 14) && !*((_QWORD *)this + 22) )
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 112);
    *(_WORD *)((char *)this + 155) = 0;
    *(_QWORD *)&EventTrack.dwHoverTime = 0;
    EventTrack.cbSize = 24;
    EventTrack.dwFlags = -2147483645;
    EventTrack.hwndTrack = (HWND)*((_QWORD *)this + 18);
    TrackMouseEvent(&EventTrack);
    ppvOut = 0;
    if ( (int)Microsoft::WRL::ComPtr<IUnknown>::As<IEdgeUiInputCallback>((char *)this + 16, &ppvOut) >= 0 )
    {
      v22 = (char *)this + 24;
      if ( !this )
        v22 = 0;
      (*(void (__fastcall **)(void *, char *))(*(_QWORD *)ppvOut + 112LL))(ppvOut, v22);
    }
    v11 = ppvOut;
    if ( ppvOut )
    {
      ppvOut = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v11 + 16LL))(v11);
    }
    goto LABEL_11;
  }
  if ( Msg == 26 )
  {
    if ( !*((_DWORD *)this + 34)
      && pszStr1
      && (CompareStringOrdinal((LPCWCH)pszStr1, -1, L"SettingsCacheChangeMessage", -1, 1) == 2
       || !StrCmpICW((LPCWSTR)pszStr1, L"ConvertibleSlateMode")) )
    {
      ppvOut = 0;
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppvOut);
      if ( IUnknown_QueryService(
             *((IUnknown **)this + 2),
             (const GUID *const)&SID_EdgeUi,
             &GUID_6e6c3c52_5a5e_4b4b_a0f8_7fe12621a93e,
             &ppvOut) >= 0 )
        (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)ppvOut + 40LL))(ppvOut, 0);
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppvOut);
    }
    goto LABEL_11;
  }
  if ( Msg > 0x200 )
  {
    switch ( Msg )
    {
      case 0x201u:
        LODWORD(ppvOut) = (__int16)pszStr1;
        HIDWORD(ppvOut) = SWORD1(pszStr1);
        if ( (unsigned int)CEdgeUiInput::_IsCurrentInputFromMouseOrPen(this) )
        {
          if ( a5 && *((_DWORD *)this + 34) <= 1u )
          {
            CEdgeUiInput::_OnPointerDown(this, 1u, (struct tagPOINT)ppvOut, 1);
            ppvOut = 0;
            if ( (int)Microsoft::WRL::ComPtr<IUnknown>::As<IEdgeUiInputCallback>((char *)this + 16, &ppvOut) >= 0 )
            {
              v18 = (char *)this + 24;
              if ( !this )
                v18 = 0;
              (*(void (__fastcall **)(void *, char *))(*(_QWORD *)ppvOut + 48LL))(ppvOut, v18);
            }
LABEL_84:
            CEdgeUiInput::_CancelTouchDrag(this);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppvOut);
          }
          else
          {
            CEdgeUiInput::_OnMouseDown(this, (struct tagPOINT)ppvOut, a5);
          }
        }
        else
        {
          CEdgeUiInput::_OnMouseMove(this, (struct tagPOINT)ppvOut, 0, a5);
        }
        break;
      case 0x202u:
        if ( (unsigned int)CEdgeUiInput::_IsCurrentInputFromMouseOrPen(this) )
        {
          LODWORD(ppvOut) = (__int16)pszStr1;
          HIDWORD(ppvOut) = SWORD1(pszStr1);
          CEdgeUiInput::_OnMouseUp(this, (struct tagPOINT)ppvOut);
        }
        return v9;
      case 0x215u:
        if ( *((_BYTE *)this + 152) )
        {
          if ( *((_QWORD *)this + 14) )
          {
            ppvOut = 0;
            if ( (int)Microsoft::WRL::ComPtr<IUnknown>::As<IEdgeUiInputCallback>((char *)this + 16, &ppvOut) >= 0 )
            {
              v20 = (char *)this + 24;
              if ( !this )
                v20 = 0;
              (*(void (__fastcall **)(void *, char *))(*(_QWORD *)ppvOut + 96LL))(ppvOut, v20);
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppvOut);
          }
          CEdgeUiInput::_CancelMouseDrag(this);
        }
        return v9;
      case 0x23Du:
        CEdgeUiInput::_SetTemporaryDisableTimer(this, 1, (unsigned __int16)pszStr1);
        goto LABEL_11;
      case 0x241u:
      case 0x242u:
      case 0x243u:
      case 0x249u:
      case 0x24Au:
      case 0x24Bu:
      case 0x24Du:
      case 0x24Eu:
      case 0x24Fu:
        if ( !(unsigned int)CEdgeUiInput::_IsPointerForEdgeInputRegisteredDevice(this, (unsigned __int16)wParam) )
          goto LABEL_11;
        return v9;
      case 0x245u:
        v15 = (unsigned __int16)wParam;
        if ( !(unsigned int)CEdgeUiInput::_IsPointerForEdgeInputRegisteredDevice(this, (unsigned __int16)wParam)
          || (unsigned int)CEdgeUiInput::_GetCornerOrEdge(this, 0) != -1 )
        {
          goto LABEL_11;
        }
        LODWORD(ppvOut) = (__int16)pszStr1;
        v16 = pszStr1 >> 16;
        HIDWORD(ppvOut) = (__int16)v16;
        if ( *((_DWORD *)this + 50) != (_DWORD)ppvOut || *((_DWORD *)this + 51) != (__int16)v16 )
        {
          *((_QWORD *)this + 25) = ppvOut;
          ScreenToClient(*((HWND *)this + 18), (LPPOINT)&ppvOut);
          v17 = *((_BYTE *)this + 154);
          CEdgeUiInput::_OnPointerUpdate(this, (unsigned __int16)wParam, (struct tagPOINT)ppvOut);
          if ( *((_DWORD *)this + 34) == 2 && !v17 && *((_BYTE *)this + 154) && *((_QWORD *)this + 12) )
            goto LABEL_52;
        }
        return v9;
      case 0x246u:
        v15 = (unsigned __int16)wParam;
        if ( !(unsigned int)CEdgeUiInput::_IsPointerForEdgeInputRegisteredDevice(this, (unsigned __int16)wParam)
          || (unsigned int)CEdgeUiInput::_GetCornerOrEdge(this, 0) != -1 )
        {
          goto LABEL_11;
        }
        LODWORD(ppvOut) = (__int16)pszStr1;
        HIDWORD(ppvOut) = SWORD1(pszStr1);
        *((_DWORD *)this + 51) = 0x80000000;
        *((_DWORD *)this + 50) = 0x80000000;
        v14 = a5;
        if ( !a5 )
        {
          v13 = *((_QWORD *)this + 15);
          if ( v13 )
            v14 = (*(unsigned __int8 (__fastcall **)(__int64, void *))(*(_QWORD *)v13 + 40LL))(v13, ppvOut) != 0;
        }
        ScreenToClient(*((HWND *)this + 18), (LPPOINT)&ppvOut);
        CEdgeUiInput::_OnPointerDown(this, (unsigned __int16)wParam, (struct tagPOINT)ppvOut, v14);
        if ( *((_BYTE *)this + 153) && *((_QWORD *)this + 12) && *((_DWORD *)this + 34) <= 1u )
LABEL_52:
          DwmShowContact(v15, 0);
        return v9;
      case 0x247u:
        if ( !(unsigned int)CEdgeUiInput::_IsPointerForEdgeInputRegisteredDevice(this, (unsigned __int16)wParam)
          || (unsigned int)CEdgeUiInput::_GetCornerOrEdge(this, 0) != -1 )
        {
          goto LABEL_11;
        }
        LODWORD(ppvOut) = (__int16)pszStr1;
        HIDWORD(ppvOut) = SWORD1(pszStr1);
        ScreenToClient(*((HWND *)this + 18), (LPPOINT)&ppvOut);
        CEdgeUiInput::_OnPointerUp(this, (unsigned __int16)wParam, (struct tagPOINT)ppvOut);
        return v9;
      case 0x24Cu:
        if ( !*((_BYTE *)this + 153) )
          return v9;
        ppvOut = 0;
        if ( (int)Microsoft::WRL::ComPtr<IUnknown>::As<IEdgeUiInputCallback>((char *)this + 16, &ppvOut) >= 0 )
        {
          v19 = (char *)this + 24;
          if ( !this )
            v19 = 0;
          (*(void (__fastcall **)(void *, char *))(*(_QWORD *)ppvOut + 48LL))(ppvOut, v19);
        }
        goto LABEL_84;
      case 0x2A1u:
        LODWORD(ppvOut) = (__int16)pszStr1;
        HIDWORD(ppvOut) = SWORD1(pszStr1);
        CEdgeUiInput::_OnMouseHover(this, (struct tagPOINT)ppvOut);
        goto LABEL_11;
      case 0x2CCu:
        return 65537;
      default:
        goto LABEL_10;
    }
  }
  else if ( Msg == 512 )
  {
    if ( (unsigned int)CEdgeUiInput::_IsCurrentInputFromMouseOrPen(this)
      && (*((_BYTE *)this + 152) || (wParam & 0x13) == 0) )
    {
      LODWORD(ppvOut) = (__int16)pszStr1;
      HIDWORD(ppvOut) = SWORD1(pszStr1);
      CEdgeUiInput::_OnMouseMove(this, (struct tagPOINT)ppvOut, 1, a5);
    }
  }
  else
  {
    if ( Msg > 0x14 )
    {
      if ( Msg == 33 )
        return 3;
      if ( Msg == 275 )
      {
        if ( wParam == *((_QWORD *)this + 22) )
        {
          CEdgeUiInput::_SampleInput(this);
        }
        else if ( wParam == *((_QWORD *)this + 23) )
        {
          CEdgeUiInput::_SetTemporaryDisableTimer(this, 0, 0);
        }
        goto LABEL_11;
      }
    }
    else
    {
      switch ( Msg )
      {
        case 0x14u:
          return 1;
        case 1u:
          SetPropW(*((HWND *)this + 18), L"UIA_WindowVisibilityOverridden", HANDLE_FLAG_PROTECT_FROM_CLOSE);
          v12 = (IDropTarget *)((char *)this + 40);
          if ( !this )
            v12 = 0;
          RegisterDragDrop(*((HWND *)this + 18), v12);
          goto LABEL_11;
        case 2u:
          if ( *((_QWORD *)this + 22) )
            CEdgeUiInput::_SetInputObservation(this, 0);
          RevokeDragDrop(*((HWND *)this + 18));
          goto LABEL_11;
        case 5u:
          if ( IsIconic(*((HWND *)this + 18)) )
            ShowWindow(*((HWND *)this + 18), 4);
          goto LABEL_11;
      }
    }
LABEL_10:
    if ( Msg != CEdgeUiInput::s_WM_MouseLeftChildEdgy )
    {
LABEL_11:
      if ( !a5 )
        return DefWindowProcW(*((HWND *)this + 18), Msg, wParam, pszStr1);
      return v9;
    }
    ppvOut = 0;
    GetPhysicalCursorPos((LPPOINT)&ppvOut);
    v21 = (HWND)*((_QWORD *)this + 18);
    if ( v21 != WindowFromPhysicalPoint((POINT)ppvOut) && GetCapture() != v21 )
      CEdgeUiInput::_OnMouseLeave(this);
  }
  return v9;
}

```

## disassembly

```asm
0x180022190  mov     [rsp-28h+arg_0], rbx
0x180022195  mov     [rsp-28h+arg_10], rsi
0x18002219a  push    rbp
0x18002219b  push    rdi
0x18002219c  push    r12
0x18002219e  push    r14
0x1800221a0  push    r15
0x1800221a2  mov     rbp, rsp
0x1800221a5  sub     rsp, 70h
0x1800221a9  mov     r15, r9
0x1800221ac  mov     r14, r8
0x1800221af  mov     ebx, edx
0x1800221b1  mov     rdi, rcx
0x1800221b4  xor     esi, esi
0x1800221b6  cmp     edx, 2A3h
0x1800221bc  jz      loc_180022256
0x1800221c2  cmp     edx, 1Ah
0x1800221c5  jz      loc_180022310
0x1800221cb  cmp     edx, 200h
0x1800221d1  ja      loc_1800222E0
0x1800221d7  jz      loc_180022491
0x1800221dd  cmp     edx, 14h
0x1800221e0  ja      loc_1800223FB
0x1800221e6  jz      loc_18002259F
0x1800221ec  mov     eax, edx
0x1800221ee  sub     eax, 1
0x1800221f1  jz      loc_180022427
0x1800221f7  sub     eax, 1
0x1800221fa  jz      loc_18002246C
0x180022200  cmp     eax, 3
0x180022203  jz      loc_1800223C3
0x180022209  cmp     ebx, cs:?s_WM_MouseLeftChildEdgy@CEdgeUiInput@@0IA; jumptable 000000018002230A default case, cases 515-532,534-572,574-576,580,584,592-672,674-715
0x18002220f  jz      loc_180022922
0x180022215  cmp     [rbp+arg_20], 0
0x180022219  jnz     short loc_180022239
0x18002221b  mov     r9, r15; lParam
0x18002221e  mov     r8, r14; wParam
0x180022221  mov     edx, ebx; Msg
0x180022223  mov     rcx, [rdi+90h]; hWnd
0x18002222a  call    cs:__imp_DefWindowProcW
0x180022231  nop     dword ptr [rax+rax+00h]
0x180022236  mov     rsi, rax
0x180022239  mov     rax, rsi
0x18002223c  lea     r11, [rsp+70h+var_s0]
0x180022241  mov     rbx, [r11+30h]
0x180022245  mov     rsi, [r11+40h]
0x180022249  mov     rsp, r11
0x18002224c  pop     r15
0x18002224e  pop     r14
0x180022250  pop     r12
0x180022252  pop     rdi
0x180022253  pop     rbp
0x180022254  retn
0x180022256  cmp     dword ptr [rcx+88h], 8
0x18002225d  jz      loc_180022978
0x180022263  lea     rcx, [rdi+70h]
0x180022267  cmp     [rcx], rsi
0x18002226a  jnz     loc_1800229B4
0x180022270  mov     [rdi+9Bh], si
0x180022277  mov     qword ptr [rbp+EventTrack.dwHoverTime], rsi
0x18002227b  mov     [rbp+EventTrack.cbSize], 18h
0x180022282  mov     [rbp+EventTrack.dwFlags], 80000003h
0x180022289  mov     rax, [rdi+90h]
0x180022290  mov     [rbp+EventTrack.hwndTrack], rax
0x180022294  lea     rcx, [rbp+EventTrack]; lpEventTrack
0x180022298  call    cs:__imp_TrackMouseEvent
0x18002229f  nop     dword ptr [rax+rax+00h]
0x1800222a4  mov     [rbp+ppvOut], rsi
0x1800222a8  lea     rcx, [rdi+10h]
0x1800222ac  lea     rdx, [rbp+ppvOut]
0x1800222b0  call    ??$As@UIEdgeUiInputCallback@@@?$ComPtr@UIUnknown@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIEdgeUiInputCallback@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IUnknown>::As<IEdgeUiInputCallback>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IEdgeUiInputCallback>>)
0x1800222b5  test    eax, eax
0x1800222b7  jns     loc_1800229CB
0x1800222bd  mov     rcx, [rbp+ppvOut]
0x1800222c1  test    rcx, rcx
0x1800222c4  jz      short loc_1800222DB
0x1800222c6  mov     [rbp+ppvOut], 0
0x1800222ce  mov     rax, [rcx]
0x1800222d1  mov     rax, [rax+10h]
0x1800222d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800222da  nop
0x1800222db  jmp     loc_180022215
0x1800222e0  lea     eax, [rdx-201h]; switch 204 cases
0x1800222e6  cmp     eax, 0CBh
0x1800222eb  ja      def_18002230A; jumptable 000000018002230A default case, cases 515-532,534-572,574-576,580,584,592-672,674-715
0x1800222f1  lea     rdx, __ImageBase
0x1800222f8  movzx   eax, ds:(byte_180022A20 - 180000000h)[rdx+rax]
0x180022300  mov     ecx, ds:(jpt_18002230A - 180000000h)[rdx+rax*4]
0x180022307  add     rcx, rdx; this
0x18002230a  jmp     rcx; switch jump
0x180022310  cmp     [rcx+88h], esi
0x180022316  jnz     loc_180022215
0x18002231c  test    r15, r15
0x18002231f  jz      loc_180022215
0x180022325  mov     [rsp+70h+bIgnoreCase], 1; bIgnoreCase
0x18002232d  mov     r9d, 0FFFFFFFFh; cchCount2
0x180022333  lea     r8, lParam; "SettingsCacheChangeMessage"
0x18002233a  mov     edx, r9d; cchCount1
0x18002233d  mov     rcx, r15; lpString1
0x180022340  call    cs:__imp_CompareStringOrdinal
0x180022347  nop     dword ptr [rax+rax+00h]
0x18002234c  cmp     eax, 2
0x18002234f  jz      short loc_18002236F
0x180022351  lea     rdx, pszStr2; "ConvertibleSlateMode"
0x180022358  mov     rcx, r15; pszStr1
0x18002235b  call    cs:__imp_StrCmpICW
0x180022362  nop     dword ptr [rax+rax+00h]
0x180022367  test    eax, eax
0x180022369  jnz     loc_180022215
0x18002236f  mov     [rbp+ppvOut], rsi
0x180022373  lea     rcx, [rbp+ppvOut]
0x180022377  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18002237c  lea     r9, [rbp+ppvOut]; ppvOut
0x180022380  lea     r8, _GUID_6e6c3c52_5a5e_4b4b_a0f8_7fe12621a93e; riid
0x180022387  lea     rdx, SID_EdgeUi; guidService
0x18002238e  mov     rcx, [rdi+10h]; punk
0x180022392  call    cs:__imp_IUnknown_QueryService
0x180022399  nop     dword ptr [rax+rax+00h]
0x18002239e  test    eax, eax
0x1800223a0  js      short loc_1800223B5
0x1800223a2  mov     rcx, [rbp+ppvOut]
0x1800223a6  mov     rax, [rcx]
0x1800223a9  xor     edx, edx
0x1800223ab  mov     rax, [rax+28h]
0x1800223af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800223b4  nop
0x1800223b5  lea     rcx, [rbp+ppvOut]
0x1800223b9  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1800223be  jmp     loc_180022215
0x1800223c3  mov     rcx, [rcx+90h]; hWnd
0x1800223ca  call    cs:__imp_IsIconic
0x1800223d1  nop     dword ptr [rax+rax+00h]
0x1800223d6  test    eax, eax
0x1800223d8  jz      loc_180022215
0x1800223de  mov     edx, 4; nCmdShow
0x1800223e3  mov     rcx, [rdi+90h]; hWnd
0x1800223ea  call    cs:__imp_ShowWindow
0x1800223f1  nop     dword ptr [rax+rax+00h]
0x1800223f6  jmp     loc_180022215
0x1800223fb  cmp     ebx, 21h ; '!'
0x1800223fe  jz      loc_1800225C5
0x180022404  cmp     ebx, 113h
0x18002240a  jnz     def_18002230A; jumptable 000000018002230A default case, cases 515-532,534-572,574-576,580,584,592-672,674-715
0x180022410  cmp     r14, [rcx+0B0h]
0x180022417  jnz     loc_1800225A9
0x18002241d  call    ?_SampleInput@CEdgeUiInput@@AEAAXXZ; CEdgeUiInput::_SampleInput(void)
0x180022422  jmp     loc_180022215
0x180022427  mov     r8d, 2; hData
0x18002242d  lea     rdx, aUiaWindowvisib; "UIA_WindowVisibilityOverridden"
0x180022434  mov     rcx, [rcx+90h]; hWnd
0x18002243b  call    cs:__imp_SetPropW
0x180022442  nop     dword ptr [rax+rax+00h]
0x180022447  lea     rdx, [rdi+28h]
0x18002244b  xor     eax, eax
0x18002244d  test    rdi, rdi
0x180022450  cmovz   rdx, rax; pDropTarget
0x180022454  mov     rcx, [rdi+90h]; hwnd
0x18002245b  call    cs:__imp_RegisterDragDrop
0x180022462  nop     dword ptr [rax+rax+00h]
0x180022467  jmp     loc_180022215
0x18002246c  cmp     [rcx+0B0h], rsi
0x180022473  jnz     loc_180022593
0x180022479  mov     rcx, [rdi+90h]; hwnd
0x180022480  call    cs:__imp_RevokeDragDrop
0x180022487  nop     dword ptr [rax+rax+00h]
0x18002248c  jmp     loc_180022215
0x180022491  call    ?_IsCurrentInputFromMouseOrPen@CEdgeUiInput@@AEAAHXZ; CEdgeUiInput::_IsCurrentInputFromMouseOrPen(void)
0x180022496  test    eax, eax
0x180022498  jz      loc_180022239
0x18002249e  cmp     [rdi+98h], sil
0x1800224a5  jnz     short loc_1800224B1
0x1800224a7  test    r14b, 13h
0x1800224ab  jnz     loc_180022239
0x1800224b1  movsx   eax, r15w
0x1800224b5  mov     dword ptr [rbp+ppvOut], eax
0x1800224b8  shr     r15, 10h
0x1800224bc  movsx   eax, r15w
0x1800224c0  mov     dword ptr [rbp+ppvOut+4], eax
0x1800224c3  movzx   r9d, [rbp+arg_20]; bool
0x1800224c8  mov     r8b, 1; bool
0x1800224cb  mov     rdx, [rbp+ppvOut]; struct tagPOINT
0x1800224cf  mov     rcx, rdi; this
0x1800224d2  call    ?_OnMouseMove@CEdgeUiInput@@AEAAXUtagPOINT@@_N1@Z; CEdgeUiInput::_OnMouseMove(tagPOINT,bool,bool)
0x1800224d7  jmp     loc_180022239
0x1800224dc  movzx   edx, r14w; jumptable 000000018002230A cases 577-579,585-587,589-591
0x1800224e0  mov     rcx, rdi; this
0x1800224e3  call    ?_IsPointerForEdgeInputRegisteredDevice@CEdgeUiInput@@AEAAHI@Z; CEdgeUiInput::_IsPointerForEdgeInputRegisteredDevice(uint)
0x1800224e8  test    eax, eax
0x1800224ea  jnz     loc_180022239
0x1800224f0  jmp     loc_180022215
0x1800224f5  mov     rcx, [rdi+78h]
0x1800224f9  test    rcx, rcx
0x1800224fc  jz      short loc_180022518
0x1800224fe  mov     rax, [rcx]
0x180022501  mov     rdx, [rbp+ppvOut]
0x180022505  mov     rax, [rax+28h]
0x180022509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002250e  mov     ecx, 1
0x180022513  test    al, al
0x180022515  cmovnz  ebx, ecx
0x180022518  lea     rdx, [rbp+ppvOut]; lpPoint
0x18002251c  mov     rcx, [rdi+90h]; hWnd
0x180022523  call    cs:__imp_ScreenToClient
0x18002252a  nop     dword ptr [rax+rax+00h]
0x18002252f  movzx   r9d, bl; bool
0x180022533  mov     r8, [rbp+ppvOut]; struct tagPOINT
0x180022537  mov     edx, r12d; unsigned int
0x18002253a  mov     rcx, rdi; this
0x18002253d  call    ?_OnPointerDown@CEdgeUiInput@@AEAAXIUtagPOINT@@_N@Z; CEdgeUiInput::_OnPointerDown(uint,tagPOINT,bool)
0x180022542  cmp     [rdi+99h], sil
0x180022549  jz      loc_180022239
0x18002254f  cmp     [rdi+60h], rsi
0x180022553  jz      loc_180022239
0x180022559  cmp     dword ptr [rdi+88h], 1
0x180022560  ja      loc_180022239
0x180022566  xor     edx, edx
0x180022568  mov     ecx, r12d
0x18002256b  call    cs:__imp_DwmShowContact
0x180022572  nop     dword ptr [rax+rax+00h]
0x180022577  jmp     loc_180022239
0x18002257c  cmp     [rdi+70h], rsi
0x180022580  jnz     loc_1800228C4
0x180022586  mov     rcx, rdi; this
0x180022589  call    ?_CancelMouseDrag@CEdgeUiInput@@AEAAJXZ; CEdgeUiInput::_CancelMouseDrag(void)
0x18002258e  jmp     loc_180022239
0x180022593  xor     edx, edx; bool
0x180022595  call    ?_SetInputObservation@CEdgeUiInput@@AEAAX_N@Z; CEdgeUiInput::_SetInputObservation(bool)
0x18002259a  jmp     loc_180022479
0x18002259f  mov     esi, 1
0x1800225a4  jmp     loc_180022239
0x1800225a9  cmp     r14, [rcx+0B8h]
0x1800225b0  jnz     loc_180022215
0x1800225b6  xor     r8d, r8d; unsigned int
0x1800225b9  xor     edx, edx; bool
0x1800225bb  call    ?_SetTemporaryDisableTimer@CEdgeUiInput@@AEAAX_NI@Z; CEdgeUiInput::_SetTemporaryDisableTimer(bool,uint)
0x1800225c0  jmp     loc_180022215
0x1800225c5  mov     esi, 3
0x1800225ca  jmp     loc_180022239
0x1800225cf  movzx   r12d, r14w; jumptable 000000018002230A case 583
0x1800225d3  mov     edx, r12d; unsigned int
0x1800225d6  mov     rcx, rdi; this
0x1800225d9  call    ?_IsPointerForEdgeInputRegisteredDevice@CEdgeUiInput@@AEAAHI@Z; CEdgeUiInput::_IsPointerForEdgeInputRegisteredDevice(uint)
0x1800225de  test    eax, eax
0x1800225e0  jz      loc_180022215
0x1800225e6  xor     edx, edx
0x1800225e8  mov     rcx, rdi
0x1800225eb  call    ?_GetCornerOrEdge@CEdgeUiInput@@AEAA?AW4EDGEUI_CORNEROREDGE@@_N@Z; CEdgeUiInput::_GetCornerOrEdge(bool)
0x1800225f0  cmp     eax, 0FFFFFFFFh
0x1800225f3  jnz     loc_180022215
0x1800225f9  movsx   eax, r15w
0x1800225fd  mov     dword ptr [rbp+ppvOut], eax
0x180022600  shr     r15, 10h
0x180022604  movsx   eax, r15w
0x180022608  mov     dword ptr [rbp+ppvOut+4], eax
0x18002260b  lea     rdx, [rbp+ppvOut]; lpPoint
0x18002260f  mov     rcx, [rdi+90h]; hWnd
0x180022616  call    cs:__imp_ScreenToClient
0x18002261d  nop     dword ptr [rax+rax+00h]
0x180022622  mov     r8, [rbp+ppvOut]; struct tagPOINT
0x180022626  mov     edx, r12d; unsigned int
0x180022629  mov     rcx, rdi; this
0x18002262c  call    ?_OnPointerUp@CEdgeUiInput@@AEAAXIUtagPOINT@@@Z; CEdgeUiInput::_OnPointerUp(uint,tagPOINT)
0x180022631  jmp     loc_180022239
0x180022636  movzx   r12d, r14w; jumptable 000000018002230A case 582
0x18002263a  mov     edx, r12d; unsigned int
0x18002263d  mov     rcx, rdi; this
0x180022640  call    ?_IsPointerForEdgeInputRegisteredDevice@CEdgeUiInput@@AEAAHI@Z; CEdgeUiInput::_IsPointerForEdgeInputRegisteredDevice(uint)
0x180022645  test    eax, eax
0x180022647  jz      loc_180022215
0x18002264d  xor     edx, edx
0x18002264f  mov     rcx, rdi
0x180022652  call    ?_GetCornerOrEdge@CEdgeUiInput@@AEAA?AW4EDGEUI_CORNEROREDGE@@_N@Z; CEdgeUiInput::_GetCornerOrEdge(bool)
0x180022657  cmp     eax, 0FFFFFFFFh
0x18002265a  jnz     loc_180022215
0x180022660  movsx   eax, r15w
0x180022664  mov     dword ptr [rbp+ppvOut], eax
0x180022667  shr     r15, 10h
0x18002266b  movsx   eax, r15w
0x18002266f  mov     dword ptr [rbp+ppvOut+4], eax
0x180022672  mov     dword ptr [rdi+0CCh], 80000000h
0x18002267c  mov     dword ptr [rdi+0C8h], 80000000h
0x180022686  movzx   ebx, [rbp+arg_20]
0x18002268a  test    bl, bl
0x18002268c  jnz     loc_180022518
0x180022692  jmp     loc_1800224F5
0x180022697  movzx   r12d, r14w; jumptable 000000018002230A case 581
0x18002269b  mov     edx, r12d; unsigned int
0x18002269e  mov     rcx, rdi; this
0x1800226a1  call    ?_IsPointerForEdgeInputRegisteredDevice@CEdgeUiInput@@AEAAHI@Z; CEdgeUiInput::_IsPointerForEdgeInputRegisteredDevice(uint)
0x1800226a6  test    eax, eax
0x1800226a8  jz      loc_180022215
0x1800226ae  xor     edx, edx
0x1800226b0  mov     rcx, rdi
0x1800226b3  call    ?_GetCornerOrEdge@CEdgeUiInput@@AEAA?AW4EDGEUI_CORNEROREDGE@@_N@Z; CEdgeUiInput::_GetCornerOrEdge(bool)
0x1800226b8  cmp     eax, 0FFFFFFFFh
0x1800226bb  jnz     loc_180022215
0x1800226c1  movsx   eax, r15w
0x1800226c5  mov     dword ptr [rbp+ppvOut], eax
0x1800226c8  shr     r15, 10h
0x1800226cc  movsx   ecx, r15w
  ... truncated ...
```
