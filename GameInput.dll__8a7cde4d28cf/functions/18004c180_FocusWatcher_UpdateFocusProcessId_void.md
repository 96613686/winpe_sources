# FocusWatcher::UpdateFocusProcessId(void)

- ea: `0x18004c180`
- end: `0x18004c286`
- name: `?UpdateFocusProcessId@FocusWatcher@@AEAAXXZ`
- size: `262`
- prototype: `void __fastcall(FocusWatcher *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18004aa90`
- `0x18004b780`

## callees

- `0x18004a864`
- `0x18004baec`
- `0x18004c128`
- `0x18004c180`
- `0x18004d010`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-0!GetForegroundWindow` at `0x18004c195`
- `ext-ms-win-ntuser-window-l1-1-0!GetForegroundWindow` at `0x18004c195`
- `ext-ms-win-ntuser-window-l1-1-0!EnumChildWindows` at `0x18004c224`
- `ext-ms-win-ntuser-window-l1-1-0!EnumChildWindows` at `0x18004c224`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18004c1b1`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18004c1b1`

## pseudocode

```c
void __fastcall FocusWatcher::UpdateFocusProcessId(FocusWatcher *this)
{
  HWND ForegroundWindow; // rax
  HWND v3; // rdi
  __int32 v4; // ecx
  __int64 v5; // rax
  __int64 v6; // rcx
  DWORD v7; // edx
  __int64 v8; // rax
  __int64 v9; // rcx
  DWORD dwProcessId; // [rsp+30h] [rbp+8h] BYREF
  DWORD lParam; // [rsp+38h] [rbp+10h] BYREF
  DWORD lParam_4; // [rsp+3Ch] [rbp+14h]

  dwProcessId = 0;
  ForegroundWindow = GetForegroundWindow();
  v3 = ForegroundWindow;
  if ( ForegroundWindow )
    GetWindowThreadProcessId(ForegroundWindow, &dwProcessId);
  v4 = _InterlockedExchange((volatile __int32 *)this + 4, dwProcessId);
  if ( v4 != dwProcessId )
  {
    v5 = *((_QWORD *)this + 1);
    *(_DWORD *)(v5 + 136) = dwProcessId;
    _mm_mfence();
    v6 = *(_QWORD *)(v5 + 24);
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 64LL))(v6);
    FocusWatcher::UnregisterProcessEventHooks(this);
    if ( (unsigned int)FocusWatcher::IsApplicationFrameWindow(v3) )
    {
      lParam = dwProcessId;
      lParam_4 = dwProcessId;
      EnumChildWindows(v3, FocusWatcher::EnumChildWindowsCallback, (LPARAM)&lParam);
      v7 = lParam_4;
      if ( lParam_4 == lParam || !lParam_4 )
      {
        FocusWatcher::RegisterProcessEventHooks(this, dwProcessId);
      }
      else if ( _InterlockedExchange((volatile __int32 *)this + 4, lParam_4) != v7 )
      {
        v8 = *((_QWORD *)this + 1);
        *(_DWORD *)(v8 + 136) = v7;
        _mm_mfence();
        v9 = *(_QWORD *)(v8 + 24);
        if ( v9 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 64LL))(v9);
      }
    }
  }
}

```

## disassembly

```asm
0x18004c180  mov     [rsp+arg_10], rbx
0x18004c185  push    rdi
0x18004c186  sub     rsp, 20h
0x18004c18a  mov     rbx, rcx
0x18004c18d  mov     [rsp+28h+dwProcessId], 0
0x18004c195  call    cs:__imp_GetForegroundWindow
0x18004c19c  nop     dword ptr [rax+rax+00h]
0x18004c1a1  mov     rdi, rax
0x18004c1a4  test    rax, rax
0x18004c1a7  jz      short loc_18004C1BD
0x18004c1a9  lea     rdx, [rsp+28h+dwProcessId]; lpdwProcessId
0x18004c1ae  mov     rcx, rax; hWnd
0x18004c1b1  call    cs:__imp_GetWindowThreadProcessId
0x18004c1b8  nop     dword ptr [rax+rax+00h]
0x18004c1bd  mov     ecx, [rsp+28h+dwProcessId]
0x18004c1c1  nop
0x18004c1c2  xchg    ecx, [rbx+10h]
0x18004c1c5  nop
0x18004c1c6  mov     edx, [rsp+28h+dwProcessId]
0x18004c1ca  cmp     ecx, edx
0x18004c1cc  jz      loc_18004C27A
0x18004c1d2  mov     rax, [rbx+8]
0x18004c1d6  nop
0x18004c1d7  mov     [rax+88h], edx
0x18004c1dd  mfence
0x18004c1e0  mov     rcx, [rax+18h]
0x18004c1e4  test    rcx, rcx
0x18004c1e7  jz      short loc_18004C1F5
0x18004c1e9  mov     rax, [rcx]
0x18004c1ec  mov     rax, [rax+40h]
0x18004c1f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c1f5  mov     rcx, rbx; this
0x18004c1f8  call    ?UnregisterProcessEventHooks@FocusWatcher@@AEAAXXZ; FocusWatcher::UnregisterProcessEventHooks(void)
0x18004c1fd  mov     rcx, rdi; HWND
0x18004c200  call    ?IsApplicationFrameWindow@FocusWatcher@@CAHPEAUHWND__@@@Z; FocusWatcher::IsApplicationFrameWindow(HWND__ *)
0x18004c205  test    eax, eax
0x18004c207  jz      short loc_18004C27A
0x18004c209  mov     eax, [rsp+28h+dwProcessId]
0x18004c20d  lea     r8, [rsp+28h+lParam]; lParam
0x18004c212  lea     rdx, ?EnumChildWindowsCallback@FocusWatcher@@CAHPEAUHWND__@@_J@Z; lpEnumFunc
0x18004c219  mov     dword ptr [rsp+28h+lParam], eax
0x18004c21d  mov     rcx, rdi; hWndParent
0x18004c220  mov     dword ptr [rsp+28h+lParam+4], eax
0x18004c224  call    cs:__imp_EnumChildWindows
0x18004c22b  nop     dword ptr [rax+rax+00h]
0x18004c230  mov     edx, dword ptr [rsp+28h+lParam+4]
0x18004c234  cmp     edx, dword ptr [rsp+28h+lParam]
0x18004c238  jz      short loc_18004C26E
0x18004c23a  test    edx, edx
0x18004c23c  jz      short loc_18004C26E
0x18004c23e  nop
0x18004c23f  mov     eax, edx
0x18004c241  xchg    eax, [rbx+10h]
0x18004c244  nop
0x18004c245  cmp     eax, edx
0x18004c247  jz      short loc_18004C27A
0x18004c249  mov     rax, [rbx+8]
0x18004c24d  nop
0x18004c24e  mov     [rax+88h], edx
0x18004c254  mfence
0x18004c257  mov     rcx, [rax+18h]
0x18004c25b  test    rcx, rcx
0x18004c25e  jz      short loc_18004C27A
0x18004c260  mov     rax, [rcx]
0x18004c263  mov     rax, [rax+40h]
0x18004c267  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c26c  jmp     short loc_18004C27A
0x18004c26e  mov     edx, [rsp+28h+dwProcessId]; unsigned int
0x18004c272  mov     rcx, rbx; this
0x18004c275  call    ?RegisterProcessEventHooks@FocusWatcher@@AEAAXK@Z; FocusWatcher::RegisterProcessEventHooks(ulong)
0x18004c27a  mov     rbx, [rsp+28h+arg_10]
0x18004c27f  add     rsp, 20h
0x18004c283  pop     rdi
0x18004c284  retn
```
