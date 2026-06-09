# BasicHwndUtils::HwndSetFocus(HWND__ *)

- ea: `0x18007b984`
- end: `0x18007bb01`
- name: `?HwndSetFocus@BasicHwndUtils@@SAHPEAUHWND__@@@Z`
- size: `381`
- prototype: `__int64 __fastcall(HWND)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180067ca0`

## callees

- `0x180043680`
- `0x1800441ac`
- `0x18007b984`
- `0x18007c62c`

## import_xrefs

- `api-ms-win-rtcore-ntuser-synch-l1-1-0!MsgWaitForMultipleObjects` at `0x18007ba5c`
- `api-ms-win-rtcore-ntuser-synch-l1-1-0!MsgWaitForMultipleObjects` at `0x18007ba5c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!TranslateMessage` at `0x18007ba97`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!TranslateMessage` at `0x18007ba97`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DispatchMessageW` at `0x18007baa1`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DispatchMessageW` at `0x18007baa1`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18007bac3`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18007bac3`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomW` at `0x18007ba02`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomW` at `0x18007ba02`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetGUIThreadInfo` at `0x18007b9cf`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetGUIThreadInfo` at `0x18007b9cf`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetMessageW` at `0x18007ba89`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetMessageW` at `0x18007ba89`
- `ext-ms-win-ntuser-keyboard-l1-1-0!UnregisterHotKey` at `0x18007baba`
- `ext-ms-win-ntuser-keyboard-l1-1-0!UnregisterHotKey` at `0x18007baba`
- `ext-ms-win-ntuser-keyboard-l1-1-0!RegisterHotKey` at `0x18007ba30`
- `ext-ms-win-ntuser-keyboard-l1-1-0!RegisterHotKey` at `0x18007ba30`
- `ext-ms-win-ntuser-private-l1-3-3!__imp_SetForegroundWindowForApplication` at `0x18007b9ea`
- `ext-ms-win-ntuser-private-l1-3-3!__imp_SetForegroundWindowForApplication` at `0x18007bacc`
- `ext-ms-win-ntuser-private-l1-3-3!__imp_SetForegroundWindowForApplication` at `0x18007b9ea`
- `ext-ms-win-ntuser-private-l1-3-3!__imp_SetForegroundWindowForApplication` at `0x18007bacc`

## pseudocode

```c
__int64 __fastcall BasicHwndUtils::HwndSetFocus(HWND a1)
{
  BOOL GUIThreadInfo; // eax
  ATOM v3; // ax
  HWND v4; // rdi
  unsigned __int8 v6; // bl
  int i; // esi
  DWORD v8; // eax
  struct tagGUITHREADINFO pgui; // [rsp+30h] [rbp-29h] BYREF

  memset_0(&pgui, 0, sizeof(pgui));
  pgui.cbSize = 72;
  GUIThreadInfo = GetGUIThreadInfo(0, &pgui);
  if ( (HWND)((__int64)pgui.hwndFocus & -(__int64)GUIThreadInfo) == a1
    || (unsigned int)SetForegroundWindowForApplication(a1) )
  {
    return 1;
  }
  v3 = GlobalAddAtomW(L"FocusHotKey");
  v4 = (HWND)v3;
  if ( !v3 )
    return 0;
  v6 = -71;
  for ( i = 0; i < 10; ++i )
  {
    if ( RegisterHotKey(0, (int)v4, 0, v6) )
    {
      BasicHwndUtils::SendKeyboardPressUnmodified(v6);
      do
      {
        v8 = MsgWaitForMultipleObjects(0, 0, 0, 0x7D0u, 0x1CFFu);
        if ( v8 == -1 )
          break;
        if ( v8 == 258 )
          break;
        memset(&pgui, 0, 48);
        if ( !GetMessageW((LPMSG)&pgui, 0, 0, 0) )
          break;
        TranslateMessage((const MSG *)&pgui);
        DispatchMessageW((const MSG *)&pgui);
      }
      while ( LODWORD(pgui.hwndActive) != 786 || pgui.hwndFocus != v4 );
      UnregisterHotKey(0, (int)v4);
      break;
    }
    ++v6;
  }
  GlobalDeleteAtom((ATOM)v4);
  return SetForegroundWindowForApplication(a1);
}

```

## disassembly

```asm
0x18007b984  mov     [rsp-8+arg_8], rbx
0x18007b989  mov     [rsp-8+arg_10], rsi
0x18007b98e  push    rbp
0x18007b98f  push    rdi
0x18007b990  push    r12
0x18007b992  push    r14
0x18007b994  push    r15
0x18007b996  lea     rbp, [rsp-37h]
0x18007b99b  sub     rsp, 90h
0x18007b9a2  mov     rax, cs:__security_cookie
0x18007b9a9  xor     rax, rsp
0x18007b9ac  mov     [rbp+57h+var_30], rax
0x18007b9b0  mov     r14, rcx
0x18007b9b3  mov     ebx, 48h ; 'H'
0x18007b9b8  mov     r8d, ebx; Size
0x18007b9bb  lea     rcx, [rbp+57h+pgui]; void *
0x18007b9bf  xor     edx, edx; Val
0x18007b9c1  call    memset_0
0x18007b9c6  lea     rdx, [rbp+57h+pgui]; pgui
0x18007b9ca  mov     [rbp+57h+pgui.cbSize], ebx
0x18007b9cd  xor     ecx, ecx; idThread
0x18007b9cf  call    cs:__imp_GetGUIThreadInfo
0x18007b9d5  neg     eax
0x18007b9d7  sbb     rcx, rcx
0x18007b9da  and     rcx, [rbp+57h+pgui.hwndFocus]
0x18007b9de  cmp     rcx, r14
0x18007b9e1  jz      loc_18007BAD4
0x18007b9e7  mov     rcx, r14
0x18007b9ea  call    cs:__imp_SetForegroundWindowForApplication
0x18007b9f0  xor     r12d, r12d
0x18007b9f3  test    eax, eax
0x18007b9f5  jnz     loc_18007BAD4
0x18007b9fb  lea     rcx, aFocushotkey; "FocusHotKey"
0x18007ba02  call    cs:__imp_GlobalAddAtomW
0x18007ba08  movzx   edi, ax
0x18007ba0b  test    di, di
0x18007ba0e  jnz     short loc_18007BA17
0x18007ba10  xor     eax, eax
0x18007ba12  jmp     loc_18007BAD9
0x18007ba17  mov     bl, 0B9h
0x18007ba19  mov     esi, r12d
0x18007ba1c  cmp     esi, 0Ah
0x18007ba1f  jge     loc_18007BAC0
0x18007ba25  movzx   r9d, bl; vk
0x18007ba29  xor     r8d, r8d; fsModifiers
0x18007ba2c  mov     edx, edi; id
0x18007ba2e  xor     ecx, ecx; hWnd
0x18007ba30  call    cs:__imp_RegisterHotKey
0x18007ba36  test    eax, eax
0x18007ba38  jnz     short loc_18007BA40
0x18007ba3a  inc     bl
0x18007ba3c  inc     esi
0x18007ba3e  jmp     short loc_18007BA1C
0x18007ba40  mov     cl, bl; unsigned __int8
0x18007ba42  call    ?SendKeyboardPressUnmodified@BasicHwndUtils@@SAXE@Z; BasicHwndUtils::SendKeyboardPressUnmodified(uchar)
0x18007ba47  mov     r9d, 7D0h; dwMilliseconds
0x18007ba4d  mov     [rsp+0B0h+dwWakeMask], 1CFFh; dwWakeMask
0x18007ba55  xor     r8d, r8d; fWaitAll
0x18007ba58  xor     edx, edx; pHandles
0x18007ba5a  xor     ecx, ecx; nCount
0x18007ba5c  call    cs:__imp_MsgWaitForMultipleObjects
0x18007ba62  cmp     eax, 0FFFFFFFFh
0x18007ba65  jz      short loc_18007BAB6
0x18007ba67  cmp     eax, 102h
0x18007ba6c  jz      short loc_18007BAB6
0x18007ba6e  xorps   xmm0, xmm0
0x18007ba71  lea     rcx, [rbp+57h+pgui]; lpMsg
0x18007ba75  xor     r9d, r9d; wMsgFilterMax
0x18007ba78  xor     r8d, r8d; wMsgFilterMin
0x18007ba7b  xor     edx, edx; hWnd
0x18007ba7d  movups  xmmword ptr [rbp+57h+pgui.cbSize], xmm0
0x18007ba81  movups  xmmword ptr [rbp+57h+pgui.hwndFocus], xmm0
0x18007ba85  movups  xmmword ptr [rbp+57h+pgui.hwndMenuOwner], xmm0
0x18007ba89  call    cs:__imp_GetMessageW
0x18007ba8f  test    eax, eax
0x18007ba91  jz      short loc_18007BAB6
0x18007ba93  lea     rcx, [rbp+57h+pgui]; lpMsg
0x18007ba97  call    cs:__imp_TranslateMessage
0x18007ba9d  lea     rcx, [rbp+57h+pgui]; lpMsg
0x18007baa1  call    cs:__imp_DispatchMessageW
0x18007baa7  cmp     dword ptr [rbp+57h+pgui.hwndActive], 312h
0x18007baae  jnz     short loc_18007BA47
0x18007bab0  cmp     [rbp+57h+pgui.hwndFocus], rdi
0x18007bab4  jnz     short loc_18007BA47
0x18007bab6  mov     edx, edi; id
0x18007bab8  xor     ecx, ecx; hWnd
0x18007baba  call    cs:__imp_UnregisterHotKey
0x18007bac0  movzx   ecx, di; nAtom
0x18007bac3  call    cs:__imp_GlobalDeleteAtom
0x18007bac9  mov     rcx, r14
0x18007bacc  call    cs:__imp_SetForegroundWindowForApplication
0x18007bad2  jmp     short loc_18007BAD9
0x18007bad4  mov     eax, 1
0x18007bad9  mov     rcx, [rbp+57h+var_30]
0x18007badd  xor     rcx, rsp; StackCookie
0x18007bae0  call    __security_check_cookie
0x18007bae5  lea     r11, [rsp+0B0h+var_20]
0x18007baed  mov     rbx, [r11+38h]
0x18007baf1  mov     rsi, [r11+40h]
0x18007baf5  mov     rsp, r11
0x18007baf8  pop     r15
0x18007bafa  pop     r14
0x18007bafc  pop     r12
0x18007bafe  pop     rdi
0x18007baff  pop     rbp
0x18007bb00  retn
```
