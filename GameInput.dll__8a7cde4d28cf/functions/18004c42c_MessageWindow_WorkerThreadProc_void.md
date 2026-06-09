# MessageWindow::WorkerThreadProc(void)

- ea: `0x18004c42c`
- end: `0x18004c78c`
- name: `?WorkerThreadProc@MessageWindow@@AEAAXXZ`
- size: `864`
- prototype: `void __fastcall(MessageWindow *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, installer_update`

## callers

- `0x18004c7a0`

## callees

- `0x180001008`
- `0x180049520`
- `0x18004aa90`
- `0x18004aba0`
- `0x18004acd0`
- `0x18004af00`
- `0x18004bd20`
- `0x18004bdf4`
- `0x18004c094`
- `0x18004c42c`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c6d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c6d5`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18004c772`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18004c772`
- `ext-ms-win-ntuser-message-l1-1-0!GetMessageW` at `0x18004c622`
- `ext-ms-win-ntuser-message-l1-1-0!GetMessageW` at `0x18004c622`
- `ext-ms-win-ntuser-message-l1-1-0!TranslateMessage` at `0x18004c636`
- `ext-ms-win-ntuser-message-l1-1-0!TranslateMessage` at `0x18004c636`
- `ext-ms-win-ntuser-message-l1-1-0!DispatchMessageW` at `0x18004c646`
- `ext-ms-win-ntuser-message-l1-1-0!DispatchMessageW` at `0x18004c646`
- `ext-ms-win-ntuser-window-l1-1-0!ShowWindow` at `0x18004c54a`
- `ext-ms-win-ntuser-window-l1-1-0!ShowWindow` at `0x18004c54a`
- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExW` at `0x18004c513`
- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExW` at `0x18004c513`
- `ext-ms-win-ntuser-window-l1-1-0!DestroyWindow` at `0x18004c6ac`
- `ext-ms-win-ntuser-window-l1-1-0!DestroyWindow` at `0x18004c6ac`
- `ext-ms-win-ntuser-windowclass-l1-1-0!SetWindowLongPtrW` at `0x18004c536`
- `ext-ms-win-ntuser-windowclass-l1-1-0!SetWindowLongPtrW` at `0x18004c536`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x18004c5e3`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x18004c5e3`
- `ext-ms-win-ntuser-windowstation-l1-1-0!CloseDesktop` at `0x18004c499`
- `ext-ms-win-ntuser-windowstation-l1-1-0!CloseDesktop` at `0x18004c6c4`
- `ext-ms-win-ntuser-windowstation-l1-1-0!CloseDesktop` at `0x18004c499`
- `ext-ms-win-ntuser-windowstation-l1-1-0!CloseDesktop` at `0x18004c6c4`
- `ext-ms-win-ntuser-windowstation-l1-1-0!SetThreadDesktop` at `0x18004c476`
- `ext-ms-win-ntuser-windowstation-l1-1-0!SetThreadDesktop` at `0x18004c476`
- `ext-ms-win-ntuser-windowstation-l1-1-1!OpenInputDesktop` at `0x18004c45b`
- `ext-ms-win-ntuser-windowstation-l1-1-1!OpenInputDesktop` at `0x18004c45b`

## string_xrefs

- `0x18004c4c9`: `GameInputServiceWindow`
- `0x18004c71d`: `CreateWindow failed`

## pseudocode

```c
void __fastcall MessageWindow::WorkerThreadProc(MessageWindow *this)
{
  char v2; // r12
  HDESK v3; // rsi
  HDESK v4; // rax
  HWND Window; // rax
  HWND v6; // r15
  struct Instance *v7; // rdi
  KeyboardLayoutWatcher *v8; // rdi
  char *v9; // rdi
  char *v10; // r14
  struct Instance *v11; // rdi
  char *v12; // rdi
  char *v13; // r14
  signed int LastError; // eax
  int v15; // r8d
  int v16; // r9d
  unsigned int v17; // ecx
  const char *v18; // [rsp+60h] [rbp-19h] BYREF
  const char *v19; // [rsp+68h] [rbp-11h] BYREF
  tagMSG Msg; // [rsp+70h] [rbp-9h] BYREF
  char pvInfo; // [rsp+E8h] [rbp+6Fh] BYREF
  unsigned int v22; // [rsp+F0h] [rbp+77h] BYREF
  int v23; // [rsp+F8h] [rbp+7Fh] BYREF

  v2 = 0;
  while ( 1 )
  {
    v3 = 0;
    if ( *((_BYTE *)this + 8) == 1 )
      break;
LABEL_8:
    Window = CreateWindowExW(0, L"GameInputServiceWindow", 0, 0, 0, 0, 0, 0, HWND_MESSAGE, 0, 0, 0);
    v6 = Window;
    if ( Window )
    {
      SetWindowLongPtrW(Window, -21, (LONG_PTR)this);
      ShowWindow(v6, 1);
      v7 = MessageWindow::s_instance;
      if ( this == *((MessageWindow **)MessageWindow::s_instance + 7) )
      {
        FocusWatcher::OnMessageWindowCreate(*((FocusWatcher **)MessageWindow::s_instance + 9), v6);
        RawInputWatcher::OnMessageWindowCreate(*((RawInputWatcher **)v7 + 10), v6);
        v8 = (KeyboardLayoutWatcher *)*((_QWORD *)v7 + 11);
        if ( (int)KeyboardLayoutWatcher::StartWinRTKeyboardLayoutWatcher(v8) < 0 )
          KeyboardLayoutWatcher::StartWinHookKeyboardLayoutWatcher(v8);
      }
      else if ( this == *((MessageWindow **)MessageWindow::s_instance + 8) )
      {
        v9 = (char *)MessageWindow::s_instance + 112;
        v10 = (char *)MessageWindow::s_instance + 136;
        while ( v9 != v10 )
        {
          (*(void (__fastcall **)(_QWORD, HWND))(**(_QWORD **)v9 + 8LL))(*(_QWORD *)v9, v6);
          v9 += 8;
        }
      }
      if ( v3 )
      {
        pvInfo = 0;
        GetUserObjectInformationW(v3, 6, &pvInfo, 1u, 0);
        *((_BYTE *)this + 9) = pvInfo;
        _mm_mfence();
      }
      memset(&Msg, 0, sizeof(Msg));
      while ( !*((_BYTE *)this + 8) || !*((_BYTE *)this + 9) )
      {
        if ( !GetMessageW(&Msg, 0, 0, 0) )
        {
          v2 = 1;
          break;
        }
        TranslateMessage(&Msg);
        DispatchMessageW(&Msg);
      }
      v11 = MessageWindow::s_instance;
      if ( this == *((MessageWindow **)MessageWindow::s_instance + 7) )
      {
        FocusWatcher::UnregisterEventHooks(*((FocusWatcher **)MessageWindow::s_instance + 9));
        RawInputWatcher::OnMessageWindowDestroy(*((RawInputWatcher **)v11 + 10));
        KeyboardLayoutWatcher::OnMessageWindowDestroy(*((KeyboardLayoutWatcher **)v11 + 11));
      }
      else if ( this == *((MessageWindow **)MessageWindow::s_instance + 8) )
      {
        v12 = (char *)MessageWindow::s_instance + 112;
        v13 = (char *)MessageWindow::s_instance + 136;
        while ( v12 != v13 )
        {
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v12 + 24LL))(*(_QWORD *)v12);
          v12 += 8;
        }
      }
      DestroyWindow(v6);
      if ( v3 )
        CloseDesktop(v3);
      goto LABEL_39;
    }
    LastError = GetLastError();
    v17 = LastError;
    if ( LastError > 0 )
      v17 = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)dword_180069000 > 2
      && (qword_180069010 & 0x400) != 0
      && (qword_180069018 & 0x400) == qword_180069018 )
    {
      v22 = v17;
      v18 = "CreateWindow failed";
      v23 = 269;
      v19 = "onecore\\xbox\\gameinput\\router\\MessageWindow.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v17,
        (unsigned int)byte_1800643FD,
        v15,
        v16,
        (__int64)&v19,
        (__int64)&v23,
        (__int64)&v18,
        (__int64)&v22);
    }
LABEL_38:
    Sleep(0x64u);
LABEL_39:
    if ( v2 )
      return;
  }
  v4 = OpenInputDesktop(0, 0, 0x2000000u);
  v3 = v4;
  if ( !v4 )
    goto LABEL_38;
  if ( SetThreadDesktop(v4) )
  {
    *((_BYTE *)this + 9) = 0;
    _mm_mfence();
    goto LABEL_8;
  }
  if ( (int)MessageWindow::CreateMessageOnlyThread(this) < 0 )
    goto LABEL_38;
  CloseDesktop(v3);
}

```

## disassembly

```asm
0x18004c42c  push    rbp
0x18004c42e  push    rbx
0x18004c42f  push    rsi
0x18004c430  push    rdi
0x18004c431  push    r12
0x18004c433  push    r14
0x18004c435  push    r15
0x18004c437  lea     rbp, [rsp-27h]
0x18004c43c  sub     rsp, 0A0h
0x18004c443  mov     rbx, rcx
0x18004c446  xor     r12b, r12b
0x18004c449  xor     esi, esi
0x18004c44b  cmp     byte ptr [rbx+8], 1
0x18004c44f  jnz     short loc_18004C4C0
0x18004c451  xor     edx, edx; fInherit
0x18004c453  xor     ecx, ecx; dwFlags
0x18004c455  mov     r8d, 2000000h; dwDesiredAccess
0x18004c45b  call    cs:__imp_OpenInputDesktop
0x18004c462  nop     dword ptr [rax+rax+00h]
0x18004c467  mov     rsi, rax
0x18004c46a  test    rax, rax
0x18004c46d  jz      loc_18004C76D
0x18004c473  mov     rcx, rax; hDesktop
0x18004c476  call    cs:__imp_SetThreadDesktop
0x18004c47d  nop     dword ptr [rax+rax+00h]
0x18004c482  test    eax, eax
0x18004c484  jnz     short loc_18004C4B8
0x18004c486  mov     rcx, rbx; this
0x18004c489  call    ?CreateMessageOnlyThread@MessageWindow@@AEAAJXZ; MessageWindow::CreateMessageOnlyThread(void)
0x18004c48e  test    eax, eax
0x18004c490  js      loc_18004C76D
0x18004c496  mov     rcx, rsi; hDesktop
0x18004c499  call    cs:__imp_CloseDesktop
0x18004c4a0  nop     dword ptr [rax+rax+00h]
0x18004c4a5  add     rsp, 0A0h
0x18004c4ac  pop     r15
0x18004c4ae  pop     r14
0x18004c4b0  pop     r12
0x18004c4b2  pop     rdi
0x18004c4b3  pop     rsi
0x18004c4b4  pop     rbx
0x18004c4b5  pop     rbp
0x18004c4b6  retn
0x18004c4b8  nop
0x18004c4b9  mov     byte ptr [rbx+9], 0
0x18004c4bd  mfence
0x18004c4c0  mov     [rsp+0D0h+lpParam], 0; lpParam
0x18004c4c9  lea     rdx, ClassName; "GameInputServiceWindow"
0x18004c4d0  mov     [rsp+0D0h+hInstance], 0; hInstance
0x18004c4d9  xor     r9d, r9d; dwStyle
0x18004c4dc  mov     [rsp+0D0h+hMenu], 0; hMenu
0x18004c4e5  xor     r8d, r8d; lpWindowName
0x18004c4e8  mov     [rsp+0D0h+hWndParent], 0FFFFFFFFFFFFFFFDh; hWndParent
0x18004c4f1  xor     ecx, ecx; dwExStyle
0x18004c4f3  mov     [rsp+0D0h+nHeight], 0; nHeight
0x18004c4fb  mov     [rsp+0D0h+nWidth], 0; nWidth
0x18004c503  mov     [rsp+0D0h+Y], 0; Y
0x18004c50b  mov     [rsp+0D0h+X], 0; X
0x18004c513  call    cs:__imp_CreateWindowExW
0x18004c51a  nop     dword ptr [rax+rax+00h]
0x18004c51f  mov     r15, rax
0x18004c522  test    rax, rax
0x18004c525  jz      loc_18004C6D5
0x18004c52b  mov     r8, rbx; dwNewLong
0x18004c52e  mov     edx, 0FFFFFFEBh; nIndex
0x18004c533  mov     rcx, rax; hWnd
0x18004c536  call    cs:__imp_SetWindowLongPtrW
0x18004c53d  nop     dword ptr [rax+rax+00h]
0x18004c542  mov     edx, 1; nCmdShow
0x18004c547  mov     rcx, r15; hWnd
0x18004c54a  call    cs:__imp_ShowWindow
0x18004c551  nop     dword ptr [rax+rax+00h]
0x18004c556  mov     rdi, cs:?s_instance@MessageWindow@@0PEAVInstance@@EA; Instance * MessageWindow::s_instance
0x18004c55d  cmp     rbx, [rdi+38h]
0x18004c561  jnz     short loc_18004C595
0x18004c563  mov     rcx, [rdi+48h]; this
0x18004c567  mov     rdx, r15; HWND
0x18004c56a  call    ?OnMessageWindowCreate@FocusWatcher@@UEAAXPEAUHWND__@@@Z; FocusWatcher::OnMessageWindowCreate(HWND__ *)
0x18004c56f  mov     rcx, [rdi+50h]; this
0x18004c573  mov     rdx, r15; HWND
0x18004c576  call    ?OnMessageWindowCreate@RawInputWatcher@@UEAAXPEAUHWND__@@@Z; RawInputWatcher::OnMessageWindowCreate(HWND__ *)
0x18004c57b  mov     rdi, [rdi+58h]
0x18004c57f  mov     rcx, rdi; this
0x18004c582  call    ?StartWinRTKeyboardLayoutWatcher@KeyboardLayoutWatcher@@AEAAJXZ; KeyboardLayoutWatcher::StartWinRTKeyboardLayoutWatcher(void)
0x18004c587  test    eax, eax
0x18004c589  jns     short loc_18004C5C0
0x18004c58b  mov     rcx, rdi; this
0x18004c58e  call    ?StartWinHookKeyboardLayoutWatcher@KeyboardLayoutWatcher@@AEAAJXZ; KeyboardLayoutWatcher::StartWinHookKeyboardLayoutWatcher(void)
0x18004c593  jmp     short loc_18004C5C0
0x18004c595  cmp     rbx, [rdi+40h]
0x18004c599  jnz     short loc_18004C5C0
0x18004c59b  add     rdi, 70h ; 'p'
0x18004c59f  lea     r14, [rdi+18h]
0x18004c5a3  jmp     short loc_18004C5BB
0x18004c5a5  mov     rcx, [rdi]
0x18004c5a8  mov     rdx, r15
0x18004c5ab  mov     rax, [rcx]
0x18004c5ae  mov     rax, [rax+8]
0x18004c5b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c5b7  add     rdi, 8
0x18004c5bb  cmp     rdi, r14
0x18004c5be  jnz     short loc_18004C5A5
0x18004c5c0  test    rsi, rsi
0x18004c5c3  jz      short loc_18004C5F9
0x18004c5c5  mov     r9d, 1; nLength
0x18004c5cb  mov     [rbp+57h+pvInfo], 0
0x18004c5cf  lea     r8, [rbp+57h+pvInfo]; pvInfo
0x18004c5d3  mov     qword ptr [rsp+0D0h+X], 0; lpnLengthNeeded
0x18004c5dc  mov     rcx, rsi; hObj
0x18004c5df  lea     edx, [r9+5]; nIndex
0x18004c5e3  call    cs:__imp_GetUserObjectInformationW
0x18004c5ea  nop     dword ptr [rax+rax+00h]
0x18004c5ef  mov     al, [rbp+57h+pvInfo]
0x18004c5f2  nop
0x18004c5f3  mov     [rbx+9], al
0x18004c5f6  mfence
0x18004c5f9  xorps   xmm0, xmm0
0x18004c5fc  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x18004c600  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x18004c604  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x18004c608  cmp     byte ptr [rbx+8], 0
0x18004c60c  jz      short loc_18004C616
0x18004c60e  mov     al, [rbx+9]
0x18004c611  nop
0x18004c612  test    al, al
0x18004c614  jnz     short loc_18004C657
0x18004c616  xor     r9d, r9d; wMsgFilterMax
0x18004c619  lea     rcx, [rbp+57h+Msg]; lpMsg
0x18004c61d  xor     r8d, r8d; wMsgFilterMin
0x18004c620  xor     edx, edx; hWnd
0x18004c622  call    cs:__imp_GetMessageW
0x18004c629  nop     dword ptr [rax+rax+00h]
0x18004c62e  test    eax, eax
0x18004c630  jz      short loc_18004C654
0x18004c632  lea     rcx, [rbp+57h+Msg]; lpMsg
0x18004c636  call    cs:__imp_TranslateMessage
0x18004c63d  nop     dword ptr [rax+rax+00h]
0x18004c642  lea     rcx, [rbp+57h+Msg]; lpMsg
0x18004c646  call    cs:__imp_DispatchMessageW
0x18004c64d  nop     dword ptr [rax+rax+00h]
0x18004c652  jmp     short loc_18004C608
0x18004c654  mov     r12b, 1
0x18004c657  mov     rdi, cs:?s_instance@MessageWindow@@0PEAVInstance@@EA; Instance * MessageWindow::s_instance
0x18004c65e  cmp     rbx, [rdi+38h]
0x18004c662  jnz     short loc_18004C681
0x18004c664  mov     rcx, [rdi+48h]; this
0x18004c668  call    ?UnregisterEventHooks@FocusWatcher@@AEAAXXZ; FocusWatcher::UnregisterEventHooks(void)
0x18004c66d  mov     rcx, [rdi+50h]; this
0x18004c671  call    ?OnMessageWindowDestroy@RawInputWatcher@@UEAAXXZ; RawInputWatcher::OnMessageWindowDestroy(void)
0x18004c676  mov     rcx, [rdi+58h]; this
0x18004c67a  call    ?OnMessageWindowDestroy@KeyboardLayoutWatcher@@UEAAXXZ; KeyboardLayoutWatcher::OnMessageWindowDestroy(void)
0x18004c67f  jmp     short loc_18004C6A9
0x18004c681  cmp     rbx, [rdi+40h]
0x18004c685  jnz     short loc_18004C6A9
0x18004c687  add     rdi, 70h ; 'p'
0x18004c68b  lea     r14, [rdi+18h]
0x18004c68f  jmp     short loc_18004C6A4
0x18004c691  mov     rcx, [rdi]
0x18004c694  mov     rax, [rcx]
0x18004c697  mov     rax, [rax+18h]
0x18004c69b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c6a0  add     rdi, 8
0x18004c6a4  cmp     rdi, r14
0x18004c6a7  jnz     short loc_18004C691
0x18004c6a9  mov     rcx, r15; hWnd
0x18004c6ac  call    cs:__imp_DestroyWindow
0x18004c6b3  nop     dword ptr [rax+rax+00h]
0x18004c6b8  test    rsi, rsi
0x18004c6bb  jz      loc_18004C77E
0x18004c6c1  mov     rcx, rsi; hDesktop
0x18004c6c4  call    cs:__imp_CloseDesktop
0x18004c6cb  nop     dword ptr [rax+rax+00h]
0x18004c6d0  jmp     loc_18004C77E
0x18004c6d5  call    cs:__imp_GetLastError
0x18004c6dc  nop     dword ptr [rax+rax+00h]
0x18004c6e1  mov     ecx, eax
0x18004c6e3  test    eax, eax
0x18004c6e5  jle     short loc_18004C6F0
0x18004c6e7  movzx   ecx, ax
0x18004c6ea  or      ecx, 80070000h
0x18004c6f0  mov     eax, cs:dword_180069000
0x18004c6f6  cmp     eax, 2
0x18004c6f9  jbe     short loc_18004C76D
0x18004c6fb  mov     rdx, cs:qword_180069018
0x18004c702  mov     rax, cs:qword_180069010
0x18004c709  bt      rax, 0Ah
0x18004c70e  jnb     short loc_18004C76D
0x18004c710  mov     rax, rdx
0x18004c713  and     eax, 400h
0x18004c718  cmp     rax, rdx
0x18004c71b  jnz     short loc_18004C76D
0x18004c71d  lea     rax, aCreatewindowFa; "CreateWindow failed"
0x18004c724  mov     [rbp+57h+arg_10], ecx
0x18004c727  mov     [rbp+57h+var_70], rax
0x18004c72b  lea     rdx, byte_1800643FD
0x18004c732  lea     rax, aOnecoreXboxGam_40; "onecore\\xbox\\gameinput\\router\\Messa"...
0x18004c739  mov     [rbp+57h+arg_18], 10Dh
0x18004c740  mov     [rbp+57h+var_68], rax
0x18004c744  lea     rax, [rbp+57h+arg_10]
0x18004c748  mov     qword ptr [rsp+0D0h+nHeight], rax
0x18004c74d  lea     rax, [rbp+57h+var_70]
0x18004c751  mov     qword ptr [rsp+0D0h+nWidth], rax
0x18004c756  lea     rax, [rbp+57h+arg_18]
0x18004c75a  mov     qword ptr [rsp+0D0h+Y], rax
0x18004c75f  lea     rax, [rbp+57h+var_68]
0x18004c763  mov     qword ptr [rsp+0D0h+X], rax
0x18004c768  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@34@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18004c76d  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18004c772  call    cs:__imp_Sleep
0x18004c779  nop     dword ptr [rax+rax+00h]
0x18004c77e  test    r12b, r12b
0x18004c781  jz      loc_18004C449
0x18004c787  jmp     loc_18004C4A5
```
