# CBridgeWindow::v_WndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18005cd30`
- end: `0x18005d378`
- name: `?v_WndProc@CBridgeWindow@@EEAA_JPEAUHWND__@@I_K_J@Z`
- size: `1608`
- prototype: `__int64(CBridgeWindow *__hidden this, HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callees

- `0x180013244`
- `0x18003ef78`
- `0x18004f460`
- `0x180050ba0`
- `0x18005943c`
- `0x18005a4a8`
- `0x18005b624`
- `0x18005bdbc`
- `0x18005bf04`
- `0x18005c394`
- `0x18005c7bc`
- `0x18005cd30`
- `0x18005d3c0`
- `0x180061130`
- `0x1800613c0`
- `0x180061900`
- `0x1800d0cd0`
- `0x1800d996c`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005ce3d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005d328`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005ce3d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005d328`
- `USER32!RemovePropW` at `0x18005cfdf`
- `USER32!RemovePropW` at `0x18005cfdf`
- `USER32!ChangeWindowMessageFilterEx` at `0x18005d12d`
- `USER32!ChangeWindowMessageFilterEx` at `0x18005d142`
- `USER32!ChangeWindowMessageFilterEx` at `0x18005d157`
- `USER32!ChangeWindowMessageFilterEx` at `0x18005d12d`
- `USER32!ChangeWindowMessageFilterEx` at `0x18005d142`
- `USER32!ChangeWindowMessageFilterEx` at `0x18005d157`
- `USER32!SetPropW` at `0x18005d0eb`
- `USER32!SetPropW` at `0x18005d0eb`
- `USER32!GetAncestor` at `0x18005d075`
- `USER32!GetAncestor` at `0x18005d075`
- `USER32!GetWindow` at `0x18005d0d8`
- `USER32!GetWindow` at `0x18005d0d8`
- `USER32!SetWindowPos` at `0x18005cedc`
- `USER32!SetWindowPos` at `0x18005cedc`
- `USER32!ShowWindow` at `0x18005d10d`
- `USER32!ShowWindow` at `0x18005d10d`
- `USER32!DestroyWindow` at `0x18005d2d8`
- `USER32!DestroyWindow` at `0x18005d2d8`
- `USER32!DefWindowProcW` at `0x18005ce4f`
- `USER32!DefWindowProcW` at `0x18005ce4f`
- `SHELL32!SHGetPropertyStoreForWindow` at `0x18005d021`
- `SHELL32!SHGetPropertyStoreForWindow` at `0x18005d0a6`
- `SHELL32!SHGetPropertyStoreForWindow` at `0x18005d021`
- `SHELL32!SHGetPropertyStoreForWindow` at `0x18005d0a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005d067`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005d0ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005d067`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005d0ca`
- `UIAutomationCore!UiaReturnRawElementProvider` at `0x18005cf5a`
- `UIAutomationCore!UiaReturnRawElementProvider` at `0x18005cf5a`
- `DUI70!?DestroyMsg@NativeHWNDHost@DirectUI@@SAIXZ` at `0x18005d1d9`
- `DUI70!?DestroyMsg@NativeHWNDHost@DirectUI@@SAIXZ` at `0x18005d1d9`

## pseudocode

```c
LRESULT __fastcall CBridgeWindow::v_WndProc(CBridgeWindow *this, HWND a2, UINT a3, unsigned __int64 a4, LPARAM lParam)
{
  LONG_PTR v5; // rbx
  CBridgeWindow *v10; // rcx
  __int64 v11; // rcx
  void *v12; // rcx
  __int64 v13; // r8
  int v14; // edx
  int v15; // ecx
  HWND v16; // rcx
  const struct tagWINDOWPOS *const v17; // r8
  UIBridgeWindow *v18; // rax
  char v19; // r14
  UIBridgeWindow *v20; // rcx
  CallerIdentity *Ancestor; // rax
  unsigned __int16 **v22; // r8
  __int64 v23; // rdx
  HWND Window; // rax
  int v25; // ebx
  UIBridgeWindow *v26; // rcx
  unsigned int v27; // r15d
  UIBridgeWindow *v28; // rcx
  void *v29; // rcx
  unsigned int v30; // edx
  void *ppv; // [rsp+40h] [rbp-31h] BYREF
  IRawElementProviderSimple *el; // [rsp+48h] [rbp-29h] BYREF
  unsigned __int64 v34; // [rsp+50h] [rbp-21h] BYREF
  UIBridgeWindow *v35[2]; // [rsp+58h] [rbp-19h] BYREF
  __int64 v36; // [rsp+68h] [rbp-9h]

  v5 = 0;
  v34 = -1;
  if ( a3 > 0x32A )
  {
    switch ( a3 )
    {
      case 0x400u:
        v30 = 256;
        break;
      case 0x401u:
        v30 = 260;
        break;
      case 0x402u:
        v30 = 274;
        break;
      case 0x403u:
        v27 = 0;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_qd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            20,
            WPP_bb6e679c4fb53f067d151a3e1aef5ec7_Traceguids,
            a2,
            *((_QWORD *)this + 20) != 0);
        }
        if ( *((_QWORD *)this + 12) && (int)CBridgeWindow::_GetHostId((CBridgeWindow *)((char *)this - 104), &v34) >= 0 )
          (*(void (__fastcall **)(_QWORD, _QWORD, unsigned __int64, _QWORD, int))(**((_QWORD **)this + 28) + 24LL))(
            *((_QWORD *)this + 28),
            *((_QWORD *)this + 12),
            v34,
            *((_QWORD *)this + 11),
            1);
        v28 = (UIBridgeWindow *)*((_QWORD *)this + 20);
        *((_QWORD *)this + 11) = 0;
        if ( v28 )
          UIBridgeWindow::HideSplashScreen(v28);
        if ( !*((_BYTE *)this + 42) )
        {
          v27 = 1;
          CBridgeWindow::_ShowCrashText((CBridgeWindow *)((char *)this - 104));
        }
        DestroyWindow(*((HWND *)this + 1));
        ppv = 0;
        if ( *((_QWORD *)this + 25)
          && (int)WeakRefAs<Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IHostedApplicationEventSink>>>(
                    (char *)this + 200,
                    &ppv) >= 0
          && ppv )
        {
          (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)ppv + 40LL))(ppv, v27);
        }
        Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&ppv);
        v29 = (void *)*((_QWORD *)this + 34);
        if ( v29 )
          SetEvent(v29);
        return v5;
      case 0x404u:
        CBridgeWindow::_CloakWindow((CBridgeWindow *)((char *)this - 104), 1);
        *((_BYTE *)this + 38) = 1;
        return v5;
      default:
        goto LABEL_56;
    }
    return (int)CBridgeWindow::_TranslateAcceleratorFromHostedWindow(
                  (CBridgeWindow *)((char *)this - 104),
                  v30,
                  a4,
                  lParam);
  }
  switch ( a3 )
  {
    case 0x32Au:
      if ( lParam != 3 )
      {
        if ( *((_BYTE *)this + 40) )
        {
          CBridgeWindow::_RemoveOwner((CBridgeWindow *)((char *)this - 104), 0);
          *((_BYTE *)this + 40) = 0;
        }
        else if ( *((_BYTE *)this + 41) )
        {
          v26 = (UIBridgeWindow *)*((_QWORD *)this + 20);
          if ( v26 )
            UIBridgeWindow::HideSplashScreen(v26);
          *((_BYTE *)this + 41) = 0;
          CBridgeWindow::_MaybeNotifySplashScreenDismissed((CBridgeWindow *)((char *)this - 104));
        }
      }
      return DefWindowProcW(a2, a3, a4, lParam);
    case 1u:
      el = 0;
      CoTaskMemFree(0);
      Ancestor = (CallerIdentity *)GetAncestor(a2, 3u);
      if ( CallerIdentity::GetImmersiveAppIdFromWindow(Ancestor, (HWND)&el, v22) >= 0 )
      {
        ppv = 0;
        Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&ppv);
        if ( SHGetPropertyStoreForWindow(a2, &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppv) >= 0 )
          IPropertyStore_SetString(ppv, v23, el);
        Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&ppv);
      }
      CoTaskMemFree(el);
      Window = GetWindow(a2, 4u);
      SetPropW(a2, L"Shell_Logical_Owner_Window_Prop", Window);
      v25 = CBridgeWindow::_CloakWindow((CBridgeWindow *)((char *)this - 104), 1);
      ShowWindow(*((HWND *)this + 1), 4);
      CBridgeWindow::_RemoveOwner((CBridgeWindow *)((char *)this - 104), v25);
      ChangeWindowMessageFilterEx(*((HWND *)this + 1), 0x400u, 1u, 0);
      ChangeWindowMessageFilterEx(*((HWND *)this + 1), 0x401u, 1u, 0);
      ChangeWindowMessageFilterEx(*((HWND *)this + 1), 0x402u, 1u, 0);
      return DefWindowProcW(a2, a3, a4, lParam);
    case 2u:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_qd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          WPP_bb6e679c4fb53f067d151a3e1aef5ec7_Traceguids,
          a2,
          *((_QWORD *)this + 20) != 0);
      }
      RemovePropW(a2, L"Shell_Logical_Owner_Window_Prop");
      v20 = (UIBridgeWindow *)*((_QWORD *)this + 20);
      if ( v20 )
        UIBridgeWindow::SetBridgeWindow(v20, 0);
      if ( *((_QWORD *)this + 10) == *((_QWORD *)this + 1) )
        *((_QWORD *)this + 10) = 0;
      ppv = 0;
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&ppv);
      if ( SHGetPropertyStoreForWindow(a2, &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppv) >= 0 )
      {
        v36 = 0;
        *(_OWORD *)v35 = 0;
        (*(void (__fastcall **)(void *, const PROPERTYKEY *, UIBridgeWindow **))(*(_QWORD *)ppv + 48LL))(
          ppv,
          &PKEY_AppUserModel_ID,
          v35);
      }
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&ppv);
      return DefWindowProcW(a2, a3, a4, lParam);
    case 0x3Du:
      v18 = (UIBridgeWindow *)*((_QWORD *)this + 20);
      v19 = 0;
      ppv = 0;
      el = 0;
      v35[0] = v18;
      if ( v18 )
      {
        Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&ppv);
        if ( (int)UIBridgeWindow::GetElementProvider(v35[0], (struct IRawElementProviderFragment **)&ppv) >= 0 )
        {
          Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&el);
          if ( (int)CBridgeWindowRawElementProvider::Make(
                      (struct IRawElementProviderFragment *)ppv,
                      *((HWND *)this + 1),
                      &GUID_d6dd68d1_86fd_4332_8666_9abedea2d24c,
                      (void **)&el) >= 0 )
          {
            v5 = UiaReturnRawElementProvider(a2, a4, lParam, el);
            v19 = 1;
          }
        }
      }
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&el);
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&ppv);
      if ( !v19 )
        return DefWindowProcW(a2, a3, a4, lParam);
      return v5;
    case 0x46u:
      v13 = *((_QWORD *)this + 30);
      if ( v13 )
      {
        if ( (*(_BYTE *)(lParam + 32) & 3) != 3 )
        {
          v14 = *(_DWORD *)(lParam + 20);
          LODWORD(v35[0]) = *(_DWORD *)(lParam + 16);
          LODWORD(v35[1]) = *(_DWORD *)(lParam + 24) + LODWORD(v35[0]);
          v15 = *(_DWORD *)(lParam + 28);
          HIDWORD(v35[0]) = v14;
          HIDWORD(v35[1]) = v14 + v15;
          (*(void (__fastcall **)(__int64, UIBridgeWindow **))(*(_QWORD *)v13 + 24LL))(v13, v35);
        }
      }
      else
      {
        v16 = (HWND)*((_QWORD *)this + 11);
        if ( v16 )
        {
          SetWindowPos(
            v16,
            *(HWND *)(lParam + 8),
            *(_DWORD *)(lParam + 16),
            *(_DWORD *)(lParam + 20),
            *(_DWORD *)(lParam + 24),
            *(_DWORD *)(lParam + 28),
            *(_DWORD *)(lParam + 32) & 3 | 0x4454);
          ImmersiveOwnedWindowHelper::RepositionOwnedWindows(
            *((ImmersiveOwnedWindowHelper **)this + 11),
            (HWND)lParam,
            v17);
        }
      }
      return DefWindowProcW(a2, a3, a4, lParam);
    case 0x270u:
      v10 = (CBridgeWindow *)((char *)this - 104);
      if ( *((_QWORD *)v10 + 25) )
      {
        if ( (lParam & 8) == 0 && (int)CBridgeWindow::_GetHostId(v10, &v34) >= 0 )
        {
          (*(void (__fastcall **)(_QWORD, _QWORD, unsigned __int64, _QWORD, int))(**((_QWORD **)this + 28) + 24LL))(
            *((_QWORD *)this + 28),
            *((_QWORD *)this + 12),
            v34,
            *((_QWORD *)this + 11),
            !(lParam & 1) + 2);
          v11 = *((_QWORD *)this + 30);
          if ( v11 )
            (*(void (__fastcall **)(__int64, LPARAM))(*(_QWORD *)v11 + 32LL))(v11, lParam & 1);
        }
      }
      if ( (lParam & 1) == 0 )
      {
        v12 = (void *)*((_QWORD *)this + 35);
        if ( v12 )
          SetEvent(v12);
      }
      return DefWindowProcW(a2, a3, a4, lParam);
  }
LABEL_56:
  if ( a3 != (unsigned int)DirectUI::NativeHWNDHost::DestroyMsg() )
    return DefWindowProcW(a2, a3, a4, lParam);
  if ( *((_BYTE *)this + 36) )
    (*(void (__fastcall **)(char *, __int64))(*((_QWORD *)this - 7) + 112LL))((char *)this - 56, 1);
  return v5;
}

```

## disassembly

```asm
0x18005cd30  push    rbp
0x18005cd32  push    rbx
0x18005cd33  push    rsi
0x18005cd34  push    rdi
0x18005cd35  push    r12
0x18005cd37  push    r13
0x18005cd39  push    r14
0x18005cd3b  push    r15
0x18005cd3d  lea     rbp, [rsp-17h]
0x18005cd42  sub     rsp, 88h
0x18005cd49  mov     rax, cs:__security_cookie
0x18005cd50  xor     rax, rsp
0x18005cd53  mov     [rbp+4Fh+var_50], rax
0x18005cd57  mov     r15, [rbp+4Fh+lParam]
0x18005cd5b  xor     ebx, ebx
0x18005cd5d  mov     eax, 32Ah
0x18005cd62  mov     [rbp+4Fh+var_70], 0FFFFFFFFFFFFFFFFh
0x18005cd6a  mov     rdi, r9
0x18005cd6d  mov     r13d, r8d
0x18005cd70  mov     r12, rdx
0x18005cd73  mov     rsi, rcx
0x18005cd76  cmp     r8d, eax
0x18005cd79  ja      loc_18005D1AF
0x18005cd7f  jz      loc_18005D162
0x18005cd85  mov     eax, r8d
0x18005cd88  sub     eax, 1
0x18005cd8b  jz      loc_18005D061
0x18005cd91  sub     eax, 1
0x18005cd94  jz      loc_18005CF89
0x18005cd9a  sub     eax, 3Bh ; ';'
0x18005cd9d  jz      loc_18005CEF3
0x18005cda3  sub     eax, 9
0x18005cda6  jz      loc_18005CE5D
0x18005cdac  cmp     eax, 22Ah
0x18005cdb1  jnz     loc_18005D1D9
0x18005cdb7  add     rcx, 0FFFFFFFFFFFFFF98h; this
0x18005cdbb  lea     r14d, [rbx+1]
0x18005cdbf  cmp     [rcx+0C8h], rbx
0x18005cdc6  jz      short loc_18005CE2C
0x18005cdc8  test    r15b, 8
0x18005cdcc  jnz     short loc_18005CE2C
0x18005cdce  lea     rdx, [rbp+4Fh+var_70]; unsigned __int64 *
0x18005cdd2  call    ?_GetHostId@CBridgeWindow@@AEAAJPEA_K@Z; CBridgeWindow::_GetHostId(unsigned __int64 *)
0x18005cdd7  test    eax, eax
0x18005cdd9  js      short loc_18005CE2C
0x18005cddb  mov     r10, [rsi+0E0h]
0x18005cde2  mov     al, r15b
0x18005cde5  mov     r9, [rsi+58h]
0x18005cde9  and     al, r14b
0x18005cdec  mov     r8, [rbp+4Fh+var_70]
0x18005cdf0  mov     rdx, [rsi+60h]
0x18005cdf4  movzx   ebx, al
0x18005cdf7  mov     rax, [r10]
0x18005cdfa  mov     ecx, ebx
0x18005cdfc  xor     ecx, r14d
0x18005cdff  add     ecx, 2
0x18005ce02  mov     [rsp+0C0h+var_A0], ecx
0x18005ce06  mov     rcx, r10
0x18005ce09  mov     rax, [rax+18h]
0x18005ce0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ce12  mov     rcx, [rsi+0F0h]
0x18005ce19  test    rcx, rcx
0x18005ce1c  jz      short loc_18005CE2C
0x18005ce1e  mov     rax, [rcx]
0x18005ce21  mov     edx, ebx
0x18005ce23  mov     rax, [rax+20h]
0x18005ce27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ce2c  test    r14b, r15b
0x18005ce2f  jnz     short loc_18005CE43
0x18005ce31  mov     rcx, [rsi+118h]; hEvent
0x18005ce38  test    rcx, rcx
0x18005ce3b  jz      short loc_18005CE43
0x18005ce3d  call    cs:__imp_SetEvent
0x18005ce43  mov     r9, r15; lParam
0x18005ce46  mov     r8, rdi; wParam
0x18005ce49  mov     edx, r13d; Msg
0x18005ce4c  mov     rcx, r12; hWnd
0x18005ce4f  call    cs:__imp_DefWindowProcW
0x18005ce55  mov     rbx, rax
0x18005ce58  jmp     loc_18005D355
0x18005ce5d  mov     r8, [rcx+0F0h]
0x18005ce64  test    r8, r8
0x18005ce67  jz      short loc_18005CEA7
0x18005ce69  mov     eax, [r15+20h]
0x18005ce6d  and     eax, 3
0x18005ce70  cmp     al, 3
0x18005ce72  jz      short loc_18005CE43
0x18005ce74  mov     ecx, [r15+10h]
0x18005ce78  mov     edx, [r15+14h]
0x18005ce7c  mov     dword ptr [rbp+4Fh+var_68], ecx
0x18005ce7f  add     ecx, [r15+18h]
0x18005ce83  mov     dword ptr [rbp+4Fh+var_68+8], ecx
0x18005ce86  mov     ecx, [r15+1Ch]
0x18005ce8a  add     ecx, edx
0x18005ce8c  mov     dword ptr [rbp+4Fh+var_68+4], edx
0x18005ce8f  mov     dword ptr [rbp+4Fh+var_68+0Ch], ecx
0x18005ce92  lea     rdx, [rbp+4Fh+var_68]
0x18005ce96  mov     rax, [r8]
0x18005ce99  mov     rcx, r8
0x18005ce9c  mov     rax, [rax+18h]
0x18005cea0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cea5  jmp     short loc_18005CE43
0x18005cea7  mov     rcx, [rcx+58h]; hWnd
0x18005ceab  test    rcx, rcx
0x18005ceae  jz      short loc_18005CE43
0x18005ceb0  mov     eax, [r15+20h]
0x18005ceb4  mov     r9d, [r15+14h]; Y
0x18005ceb8  and     eax, 3
0x18005cebb  mov     r8d, [r15+10h]; X
0x18005cebf  or      eax, 4454h
0x18005cec4  mov     rdx, [r15+8]; hWndInsertAfter
0x18005cec8  mov     [rsp+0C0h+uFlags], eax; uFlags
0x18005cecc  mov     eax, [r15+1Ch]
0x18005ced0  mov     [rsp+0C0h+cy], eax; cy
0x18005ced4  mov     eax, [r15+18h]
0x18005ced8  mov     [rsp+0C0h+var_A0], eax; cx
0x18005cedc  call    cs:__imp_SetWindowPos
0x18005cee2  mov     rcx, [rsi+58h]; this
0x18005cee6  mov     rdx, r15; HWND
0x18005cee9  call    ?RepositionOwnedWindows@ImmersiveOwnedWindowHelper@@YAJPEAUHWND__@@QEBUtagWINDOWPOS@@@Z; ImmersiveOwnedWindowHelper::RepositionOwnedWindows(HWND__ *,tagWINDOWPOS const * const)
0x18005ceee  jmp     loc_18005CE43
0x18005cef3  mov     rax, [rcx+0A0h]
0x18005cefa  xor     r14b, r14b
0x18005cefd  mov     [rbp+4Fh+ppv], rbx
0x18005cf01  mov     [rbp+4Fh+el], rbx
0x18005cf05  mov     [rbp+4Fh+var_68], rax
0x18005cf09  test    rax, rax
0x18005cf0c  jz      short loc_18005CF69
0x18005cf0e  lea     rcx, [rbp+4Fh+ppv]
0x18005cf12  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18005cf17  mov     rcx, [rbp+4Fh+var_68]; this
0x18005cf1b  lea     rdx, [rbp+4Fh+ppv]; struct IRawElementProviderFragment **
0x18005cf1f  call    ?GetElementProvider@UIBridgeWindow@@QEAAJPEAPEAUIRawElementProviderFragment@@@Z; UIBridgeWindow::GetElementProvider(IRawElementProviderFragment * *)
0x18005cf24  test    eax, eax
0x18005cf26  js      short loc_18005CF69
0x18005cf28  lea     rcx, [rbp+4Fh+el]
0x18005cf2c  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18005cf31  mov     rdx, [rsi+8]; HWND
0x18005cf35  lea     r9, [rbp+4Fh+el]; void **
0x18005cf39  mov     rcx, [rbp+4Fh+ppv]; struct IRawElementProviderFragment *
0x18005cf3d  lea     r8, _GUID_d6dd68d1_86fd_4332_8666_9abedea2d24c; struct _GUID *
0x18005cf44  call    ?Make@CBridgeWindowRawElementProvider@@SAJPEAUIRawElementProviderFragment@@PEAUHWND__@@AEBU_GUID@@PEAPEAX@Z; CBridgeWindowRawElementProvider::Make(IRawElementProviderFragment *,HWND__ *,_GUID const &,void * *)
0x18005cf49  test    eax, eax
0x18005cf4b  js      short loc_18005CF69
0x18005cf4d  mov     r9, [rbp+4Fh+el]; el
0x18005cf51  mov     r8, r15; lParam
0x18005cf54  mov     rdx, rdi; wParam
0x18005cf57  mov     rcx, r12; hwnd
0x18005cf5a  call    cs:__imp_UiaReturnRawElementProvider
0x18005cf60  mov     rbx, rax
0x18005cf63  mov     r14d, 1
0x18005cf69  lea     rcx, [rbp+4Fh+el]
0x18005cf6d  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18005cf72  lea     rcx, [rbp+4Fh+ppv]
0x18005cf76  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18005cf7b  test    r14b, r14b
0x18005cf7e  jnz     loc_18005D355
0x18005cf84  jmp     loc_18005CE43
0x18005cf89  mov     rcx, cs:WPP_GLOBAL_Control
0x18005cf90  lea     rax, WPP_GLOBAL_Control
0x18005cf97  cmp     rcx, rax
0x18005cf9a  jz      short loc_18005CFD5
0x18005cf9c  mov     r14d, 1
0x18005cfa2  test    [rcx+1Ch], r14b
0x18005cfa6  jz      short loc_18005CFD5
0x18005cfa8  cmp     byte ptr [rcx+19h], 4
0x18005cfac  jb      short loc_18005CFD5
0x18005cfae  mov     rcx, [rcx+10h]
0x18005cfb2  lea     edx, [r14+12h]
0x18005cfb6  xor     eax, eax
0x18005cfb8  lea     r8, WPP_bb6e679c4fb53f067d151a3e1aef5ec7_Traceguids
0x18005cfbf  cmp     [rsi+0A0h], rax
0x18005cfc6  mov     r9, r12
0x18005cfc9  setnz   al
0x18005cfcc  mov     [rsp+0C0h+var_A0], eax
0x18005cfd0  call    WPP_SF_qd
0x18005cfd5  lea     rdx, String; "Shell_Logical_Owner_Window_Prop"
0x18005cfdc  mov     rcx, r12; hWnd
0x18005cfdf  call    cs:__imp_RemovePropW
0x18005cfe5  mov     rcx, [rsi+0A0h]; this
0x18005cfec  test    rcx, rcx
0x18005cfef  jz      short loc_18005CFF8
0x18005cff1  xor     edx, edx; HWND
0x18005cff3  call    ?SetBridgeWindow@UIBridgeWindow@@QEAAXPEAUHWND__@@@Z; UIBridgeWindow::SetBridgeWindow(HWND__ *)
0x18005cff8  mov     rax, [rsi+8]
0x18005cffc  cmp     [rsi+50h], rax
0x18005d000  jnz     short loc_18005D006
0x18005d002  mov     [rsi+50h], rbx
0x18005d006  lea     rcx, [rbp+4Fh+ppv]
0x18005d00a  mov     [rbp+4Fh+ppv], rbx
0x18005d00e  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18005d013  lea     r8, [rbp+4Fh+ppv]; ppv
0x18005d017  mov     rcx, r12; hwnd
0x18005d01a  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x18005d021  call    cs:__imp_SHGetPropertyStoreForWindow
0x18005d027  test    eax, eax
0x18005d029  js      short loc_18005D053
0x18005d02b  mov     rcx, [rbp+4Fh+ppv]
0x18005d02f  lea     r8, [rbp+4Fh+var_68]
0x18005d033  xor     eax, eax
0x18005d035  lea     rdx, PKEY_AppUserModel_ID
0x18005d03c  mov     [rbp+4Fh+var_58], rax
0x18005d040  xorps   xmm0, xmm0
0x18005d043  movups  xmmword ptr [rbp+4Fh+var_68], xmm0
0x18005d047  mov     rax, [rcx]
0x18005d04a  mov     rax, [rax+30h]
0x18005d04e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d053  lea     rcx, [rbp+4Fh+ppv]
0x18005d057  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18005d05c  jmp     loc_18005CE43
0x18005d061  xor     ecx, ecx; pv
0x18005d063  mov     [rbp+4Fh+el], rbx
0x18005d067  call    cs:__imp_CoTaskMemFree
0x18005d06d  mov     edx, 3; gaFlags
0x18005d072  mov     rcx, r12; hwnd
0x18005d075  call    cs:__imp_GetAncestor
0x18005d07b  mov     rcx, rax; this
0x18005d07e  lea     rdx, [rbp+4Fh+el]; HWND
0x18005d082  call    ?GetImmersiveAppIdFromWindow@CallerIdentity@@YAJPEAUHWND__@@PEAPEAG@Z; CallerIdentity::GetImmersiveAppIdFromWindow(HWND__ *,ushort * *)
0x18005d087  test    eax, eax
0x18005d089  js      short loc_18005D0C6
0x18005d08b  lea     rcx, [rbp+4Fh+ppv]
0x18005d08f  mov     [rbp+4Fh+ppv], rbx
0x18005d093  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18005d098  lea     r8, [rbp+4Fh+ppv]; ppv
0x18005d09c  mov     rcx, r12; hwnd
0x18005d09f  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x18005d0a6  call    cs:__imp_SHGetPropertyStoreForWindow
0x18005d0ac  test    eax, eax
0x18005d0ae  js      short loc_18005D0BD
0x18005d0b0  mov     r8, [rbp+4Fh+el]
0x18005d0b4  mov     rcx, [rbp+4Fh+ppv]
0x18005d0b8  call    IPropertyStore_SetString
0x18005d0bd  lea     rcx, [rbp+4Fh+ppv]
0x18005d0c1  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18005d0c6  mov     rcx, [rbp+4Fh+el]; pv
0x18005d0ca  call    cs:__imp_CoTaskMemFree
0x18005d0d0  mov     edx, 4; uCmd
0x18005d0d5  mov     rcx, r12; hWnd
0x18005d0d8  call    cs:__imp_GetWindow
0x18005d0de  lea     rdx, String; "Shell_Logical_Owner_Window_Prop"
0x18005d0e5  mov     rcx, r12; hWnd
0x18005d0e8  mov     r8, rax; hData
0x18005d0eb  call    cs:__imp_SetPropW
0x18005d0f1  mov     r14d, 1
0x18005d0f7  lea     rcx, [rsi-68h]; this
0x18005d0fb  mov     edx, r14d; int
0x18005d0fe  call    ?_CloakWindow@CBridgeWindow@@AEAAJH@Z; CBridgeWindow::_CloakWindow(int)
0x18005d103  mov     rcx, [rsi+8]; hWnd
0x18005d107  lea     edx, [r14+3]; nCmdShow
0x18005d10b  mov     ebx, eax
0x18005d10d  call    cs:__imp_ShowWindow
0x18005d113  mov     edx, ebx; int
0x18005d115  lea     rcx, [rsi-68h]; this
0x18005d119  call    ?_RemoveOwner@CBridgeWindow@@AEAAXJ@Z; CBridgeWindow::_RemoveOwner(long)
0x18005d11e  mov     rcx, [rsi+8]; hwnd
0x18005d122  xor     r9d, r9d; pChangeFilterStruct
0x18005d125  mov     r8d, r14d; action
0x18005d128  mov     edx, 400h; message
0x18005d12d  call    cs:__imp_ChangeWindowMessageFilterEx
0x18005d133  mov     rcx, [rsi+8]; hwnd
0x18005d137  xor     r9d, r9d; pChangeFilterStruct
0x18005d13a  mov     r8d, r14d; action
0x18005d13d  mov     edx, 401h; message
0x18005d142  call    cs:__imp_ChangeWindowMessageFilterEx
0x18005d148  mov     rcx, [rsi+8]; hwnd
0x18005d14c  xor     r9d, r9d; pChangeFilterStruct
0x18005d14f  mov     r8d, r14d; action
0x18005d152  mov     edx, 402h; message
0x18005d157  call    cs:__imp_ChangeWindowMessageFilterEx
0x18005d15d  jmp     loc_18005CE43
0x18005d162  cmp     r15, 3
0x18005d166  jz      loc_18005CE43
0x18005d16c  cmp     [rcx+28h], bl
0x18005d16f  jz      short loc_18005D184
0x18005d171  xor     edx, edx; int
0x18005d173  add     rcx, 0FFFFFFFFFFFFFF98h; this
0x18005d177  call    ?_RemoveOwner@CBridgeWindow@@AEAAXJ@Z; CBridgeWindow::_RemoveOwner(long)
0x18005d17c  mov     [rsi+28h], bl
0x18005d17f  jmp     loc_18005CE43
0x18005d184  cmp     [rcx+29h], bl
0x18005d187  jz      loc_18005CE43
0x18005d18d  mov     rcx, [rcx+0A0h]; this
0x18005d194  test    rcx, rcx
0x18005d197  jz      short loc_18005D19E
0x18005d199  call    ?HideSplashScreen@UIBridgeWindow@@QEAAXXZ; UIBridgeWindow::HideSplashScreen(void)
0x18005d19e  lea     rcx, [rsi-68h]; this
0x18005d1a2  mov     [rsi+29h], bl
0x18005d1a5  call    ?_MaybeNotifySplashScreenDismissed@CBridgeWindow@@AEAAXXZ; CBridgeWindow::_MaybeNotifySplashScreenDismissed(void)
0x18005d1aa  jmp     loc_18005CE43
0x18005d1af  mov     eax, r13d
0x18005d1b2  sub     eax, 400h
0x18005d1b7  jz      loc_18005D33E
0x18005d1bd  sub     eax, 1
0x18005d1c0  jz      loc_18005D337
0x18005d1c6  sub     eax, 1
0x18005d1c9  jz      loc_18005D330
0x18005d1cf  sub     eax, 1
0x18005d1d2  jz      short loc_18005D226
0x18005d1d4  cmp     eax, 1
  ... truncated ...
```
