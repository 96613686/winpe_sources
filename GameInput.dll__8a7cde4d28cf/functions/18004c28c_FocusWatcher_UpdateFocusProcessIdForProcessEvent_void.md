# FocusWatcher::UpdateFocusProcessIdForProcessEvent(void)

- ea: `0x18004c28c`
- end: `0x18004c363`
- name: `?UpdateFocusProcessIdForProcessEvent@FocusWatcher@@AEAAXXZ`
- size: `215`
- prototype: `void __fastcall(FocusWatcher *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18004b780`

## callees

- `0x18004a864`
- `0x18004c128`
- `0x18004c28c`
- `0x18004d010`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-0!GetForegroundWindow` at `0x18004c2aa`
- `ext-ms-win-ntuser-window-l1-1-0!GetForegroundWindow` at `0x18004c2aa`
- `ext-ms-win-ntuser-window-l1-1-0!EnumChildWindows` at `0x18004c303`
- `ext-ms-win-ntuser-window-l1-1-0!EnumChildWindows` at `0x18004c303`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18004c2c6`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18004c2c6`

## pseudocode

```c
void __fastcall FocusWatcher::UpdateFocusProcessIdForProcessEvent(FocusWatcher *this)
{
  FocusWatcher *v1; // rdi
  HWND ForegroundWindow; // rax
  HWND v3; // rbx
  DWORD v4; // edx
  __int64 v5; // rax
  __int64 v6; // rcx
  DWORD dwProcessId; // [rsp+30h] [rbp+8h] BYREF
  int v8; // [rsp+34h] [rbp+Ch]
  DWORD lParam; // [rsp+38h] [rbp+10h] BYREF
  DWORD lParam_4; // [rsp+3Ch] [rbp+14h]

  v8 = HIDWORD(this);
  v1 = FocusWatcher::s_singleton;
  dwProcessId = 0;
  ForegroundWindow = GetForegroundWindow();
  v3 = ForegroundWindow;
  if ( ForegroundWindow )
    GetWindowThreadProcessId(ForegroundWindow, &dwProcessId);
  if ( *((_DWORD *)v1 + 4) != dwProcessId || !(unsigned int)FocusWatcher::IsApplicationFrameWindow(v3) )
    goto LABEL_10;
  lParam = dwProcessId;
  lParam_4 = dwProcessId;
  EnumChildWindows(v3, FocusWatcher::EnumChildWindowsCallback, (LPARAM)&lParam);
  v4 = lParam_4;
  if ( lParam_4 != lParam && lParam_4 )
  {
    if ( _InterlockedExchange((volatile __int32 *)v1 + 4, lParam_4) != v4 )
    {
      v5 = *((_QWORD *)v1 + 1);
      *(_DWORD *)(v5 + 136) = v4;
      _mm_mfence();
      v6 = *(_QWORD *)(v5 + 24);
      if ( v6 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 64LL))(v6);
    }
LABEL_10:
    FocusWatcher::UnregisterProcessEventHooks(FocusWatcher::s_singleton);
  }
}

```

## disassembly

```asm
0x18004c28c  mov     [rsp+arg_10], rbx
0x18004c291  mov     qword ptr [rsp+dwProcessId], rcx
0x18004c296  push    rdi
0x18004c297  sub     rsp, 20h
0x18004c29b  mov     rdi, cs:?s_singleton@FocusWatcher@@0PEAV1@EA; FocusWatcher * FocusWatcher::s_singleton
0x18004c2a2  mov     [rsp+28h+dwProcessId], 0
0x18004c2aa  call    cs:__imp_GetForegroundWindow
0x18004c2b1  nop     dword ptr [rax+rax+00h]
0x18004c2b6  mov     rbx, rax
0x18004c2b9  test    rax, rax
0x18004c2bc  jz      short loc_18004C2D2
0x18004c2be  lea     rdx, [rsp+28h+dwProcessId]; lpdwProcessId
0x18004c2c3  mov     rcx, rax; hWnd
0x18004c2c6  call    cs:__imp_GetWindowThreadProcessId
0x18004c2cd  nop     dword ptr [rax+rax+00h]
0x18004c2d2  mov     ecx, [rdi+10h]
0x18004c2d5  nop
0x18004c2d6  cmp     ecx, [rsp+28h+dwProcessId]
0x18004c2da  jnz     short loc_18004C34B
0x18004c2dc  mov     rcx, rbx; HWND
0x18004c2df  call    ?IsApplicationFrameWindow@FocusWatcher@@CAHPEAUHWND__@@@Z; FocusWatcher::IsApplicationFrameWindow(HWND__ *)
0x18004c2e4  test    eax, eax
0x18004c2e6  jz      short loc_18004C34B
0x18004c2e8  mov     eax, [rsp+28h+dwProcessId]
0x18004c2ec  lea     r8, [rsp+28h+lParam]; lParam
0x18004c2f1  lea     rdx, ?EnumChildWindowsCallback@FocusWatcher@@CAHPEAUHWND__@@_J@Z; lpEnumFunc
0x18004c2f8  mov     dword ptr [rsp+28h+lParam], eax
0x18004c2fc  mov     rcx, rbx; hWndParent
0x18004c2ff  mov     dword ptr [rsp+28h+lParam+4], eax
0x18004c303  call    cs:__imp_EnumChildWindows
0x18004c30a  nop     dword ptr [rax+rax+00h]
0x18004c30f  mov     edx, dword ptr [rsp+28h+lParam+4]
0x18004c313  cmp     edx, dword ptr [rsp+28h+lParam]
0x18004c317  jz      short loc_18004C357
0x18004c319  test    edx, edx
0x18004c31b  jz      short loc_18004C357
0x18004c31d  nop
0x18004c31e  mov     eax, edx
0x18004c320  xchg    eax, [rdi+10h]
0x18004c323  nop
0x18004c324  cmp     eax, edx
0x18004c326  jz      short loc_18004C34B
0x18004c328  mov     rax, [rdi+8]
0x18004c32c  nop
0x18004c32d  mov     [rax+88h], edx
0x18004c333  mfence
0x18004c336  mov     rcx, [rax+18h]
0x18004c33a  test    rcx, rcx
0x18004c33d  jz      short loc_18004C34B
0x18004c33f  mov     rax, [rcx]
0x18004c342  mov     rax, [rax+40h]
0x18004c346  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c34b  mov     rcx, cs:?s_singleton@FocusWatcher@@0PEAV1@EA; this
0x18004c352  call    ?UnregisterProcessEventHooks@FocusWatcher@@AEAAXXZ; FocusWatcher::UnregisterProcessEventHooks(void)
0x18004c357  mov     rbx, [rsp+28h+arg_10]
0x18004c35c  add     rsp, 20h
0x18004c360  pop     rdi
0x18004c361  retn
```
