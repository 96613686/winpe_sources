# HwndProxy::get_WindowInteractionState(WindowInteractionState *)

- ea: `0x18027e140`
- end: `0x18027e23f`
- name: `?get_WindowInteractionState@HwndProxy@@UEAAJPEAW4WindowInteractionState@@@Z`
- size: `255`
- prototype: `__int64 __fastcall(HwndProxy *__hidden this, enum WindowInteractionState *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x180080cc0`
- `0x1801334b8`
- `0x18027e140`

## import_xrefs

- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowLongW` at `0x18027e1e6`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowLongW` at `0x18027e1e6`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x18027e204`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x18027e204`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SendMessageTimeoutW` at `0x18027e1a1`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SendMessageTimeoutW` at `0x18027e1a1`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsWindow` at `0x18027e1c3`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsWindow` at `0x18027e1c3`
- `api-ms-win-rtcore-ntuser-private-l1-1-1!__imp_InternalEnumThreadWindows` at `0x18027e21a`
- `api-ms-win-rtcore-ntuser-private-l1-1-1!__imp_InternalEnumThreadWindows` at `0x18027e21a`

## pseudocode

```c
__int64 __fastcall HwndProxy::get_WindowInteractionState(HwndProxy *this, enum WindowInteractionState *a2)
{
  HWND v5; // rdi
  DWORD WindowThreadProcessId; // eax
  ULONG_PTR dwResult; // [rsp+50h] [rbp+8h] BYREF

  if ( *((_BYTE *)this + 60) )
    return 2147500033LL;
  if ( !a2 )
    return 2147500035LL;
  dwResult = 0;
  *a2 = WindowInteractionState_ReadyForUserInteraction;
  if ( SendMessageTimeoutW(*((HWND *)this + 4), 0, 0, 0, 2u, 1u, &dwResult) )
  {
    if ( (GetWindowLongW(*((HWND *)this + 4), -16) & 0x8000000) != 0 )
    {
      v5 = (HWND)*((_QWORD *)this + 4);
      if ( BasicUiaUtils::IsDesktop()
        && (WindowThreadProcessId = GetWindowThreadProcessId(v5, 0)) != 0
        && !(unsigned int)InternalEnumThreadWindows(WindowThreadProcessId, HasModalWindow_EnumProc, v5) )
      {
        *a2 = WindowInteractionState_BlockedByModalWindow;
      }
      else
      {
        *a2 = WindowInteractionState_Running;
      }
    }
  }
  else
  {
    Error::Win32Error(L"HwndProxy::get_WindowInteractionState", L"Call to SendMessageTimeout failed");
    if ( IsWindow(*((HWND *)this + 4)) )
      *a2 = WindowInteractionState_NotResponding;
    else
      *a2 = WindowInteractionState_Closing;
  }
  return 0;
}

```

## disassembly

```asm
0x18027e140  mov     [rsp+arg_8], rbx
0x18027e145  push    rdi
0x18027e146  sub     rsp, 40h
0x18027e14a  cmp     byte ptr [rcx+3Ch], 0
0x18027e14e  mov     rbx, rdx
0x18027e151  mov     rdi, rcx
0x18027e154  jz      short loc_18027E160
0x18027e156  mov     eax, 80004001h
0x18027e15b  jmp     loc_18027E234
0x18027e160  test    rbx, rbx
0x18027e163  jnz     short loc_18027E16F
0x18027e165  mov     eax, 80004003h
0x18027e16a  jmp     loc_18027E234
0x18027e16f  mov     ecx, 2
0x18027e174  mov     [rsp+48h+dwResult], 0
0x18027e17d  mov     [rdx], ecx
0x18027e17f  lea     rax, [rsp+48h+dwResult]
0x18027e184  mov     [rsp+48h+lpdwResult], rax; lpdwResult
0x18027e189  xor     r9d, r9d; lParam
0x18027e18c  mov     [rsp+48h+uTimeout], 1; uTimeout
0x18027e194  xor     r8d, r8d; wParam
0x18027e197  mov     [rsp+48h+fuFlags], ecx; fuFlags
0x18027e19b  xor     edx, edx; Msg
0x18027e19d  mov     rcx, [rdi+20h]; hWnd
0x18027e1a1  call    cs:__imp_SendMessageTimeoutW
0x18027e1a7  test    rax, rax
0x18027e1aa  jnz     short loc_18027E1DD
0x18027e1ac  lea     rdx, aCallToSendmess; "Call to SendMessageTimeout failed"
0x18027e1b3  lea     rcx, aHwndproxyGetWi; "HwndProxy::get_WindowInteractionState"
0x18027e1ba  call    ?Win32Error@Error@@SAJPEBG0@Z; Error::Win32Error(ushort const *,ushort const *)
0x18027e1bf  mov     rcx, [rdi+20h]; hWnd
0x18027e1c3  call    cs:__imp_IsWindow
0x18027e1c9  test    eax, eax
0x18027e1cb  jz      short loc_18027E1D5
0x18027e1cd  mov     dword ptr [rbx], 4
0x18027e1d3  jmp     short loc_18027E232
0x18027e1d5  mov     dword ptr [rbx], 1
0x18027e1db  jmp     short loc_18027E232
0x18027e1dd  mov     rcx, [rdi+20h]; hWnd
0x18027e1e1  mov     edx, 0FFFFFFF0h; nIndex
0x18027e1e6  call    cs:__imp_GetWindowLongW
0x18027e1ec  bt      eax, 1Bh
0x18027e1f0  jnb     short loc_18027E232
0x18027e1f2  mov     rdi, [rdi+20h]
0x18027e1f6  call    ?IsDesktop@BasicUiaUtils@@SA_NXZ; BasicUiaUtils::IsDesktop(void)
0x18027e1fb  test    al, al
0x18027e1fd  jz      short loc_18027E22C
0x18027e1ff  xor     edx, edx; lpdwProcessId
0x18027e201  mov     rcx, rdi; hWnd
0x18027e204  call    cs:__imp_GetWindowThreadProcessId
0x18027e20a  test    eax, eax
0x18027e20c  jz      short loc_18027E22C
0x18027e20e  mov     r8, rdi
0x18027e211  lea     rdx, ?HasModalWindow_EnumProc@@YAHPEAUHWND__@@_J@Z; HasModalWindow_EnumProc(HWND__ *,__int64)
0x18027e218  mov     ecx, eax
0x18027e21a  call    cs:__imp_InternalEnumThreadWindows
0x18027e220  test    eax, eax
0x18027e222  jnz     short loc_18027E22C
0x18027e224  mov     dword ptr [rbx], 3
0x18027e22a  jmp     short loc_18027E232
0x18027e22c  mov     dword ptr [rbx], 0
0x18027e232  xor     eax, eax
0x18027e234  mov     rbx, [rsp+48h+arg_8]
0x18027e239  add     rsp, 40h
0x18027e23d  pop     rdi
0x18027e23e  retn
```
