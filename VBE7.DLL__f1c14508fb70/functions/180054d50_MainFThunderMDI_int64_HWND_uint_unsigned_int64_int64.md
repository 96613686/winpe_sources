# MainFThunderMDI(__int64 *,HWND__ * *,uint *,unsigned __int64 *,__int64 *)

- ea: `0x180054d50`
- end: `0x180054f44`
- name: `?MainFThunderMDI@@YAHPEA_JPEAPEAUHWND__@@PEAIPEA_K0@Z`
- size: `500`
- prototype: `__int64 __fastcall(__int64 *, HWND *, unsigned int *, unsigned __int64 *, __int64 *)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, service_task`

## callers

- `0x1800238cc`
- `0x18008ca88`
- `0x18009064c`

## callees

- `0x180054d50`
- `0x18005c870`
- `0x180379380`

## import_xrefs

- `USER32!SetForegroundWindow` at `0x180054f39`
- `USER32!SetForegroundWindow` at `0x180054f39`
- `USER32!GetDesktopWindow` at `0x180054e59`
- `USER32!GetDesktopWindow` at `0x180054e59`
- `USER32!ShowWindow` at `0x180054e44`
- `USER32!ShowWindow` at `0x180054e44`
- `USER32!IsWindowVisible` at `0x180054ea7`
- `USER32!IsWindowVisible` at `0x180054f10`
- `USER32!IsWindowVisible` at `0x180054ea7`
- `USER32!IsWindowVisible` at `0x180054f10`
- `USER32!SetFocus` at `0x180054e06`
- `USER32!SetFocus` at `0x180054e06`
- `USER32!GetWindow` at `0x180054e67`
- `USER32!GetWindow` at `0x180054e91`
- `USER32!GetWindow` at `0x180054eb6`
- `USER32!GetWindow` at `0x180054ee4`
- `USER32!GetWindow` at `0x180054f1f`
- `USER32!GetWindow` at `0x180054e67`
- `USER32!GetWindow` at `0x180054e91`
- `USER32!GetWindow` at `0x180054eb6`
- `USER32!GetWindow` at `0x180054ee4`
- `USER32!GetWindow` at `0x180054f1f`
- `USER32!SendMessageA` at `0x180054dc6`
- `USER32!SendMessageA` at `0x180054e21`
- `USER32!SendMessageA` at `0x180054dc6`
- `USER32!SendMessageA` at `0x180054e21`
- `USER32!GetWindowLongA` at `0x180054e82`
- `USER32!GetWindowLongA` at `0x180054e82`
- `USER32!IsIconic` at `0x180054deb`
- `USER32!IsIconic` at `0x180054e32`
- `USER32!IsIconic` at `0x180054deb`
- `USER32!IsIconic` at `0x180054e32`
- `USER32!GetWindowThreadProcessId` at `0x180054ec9`
- `USER32!GetWindowThreadProcessId` at `0x180054efb`
- `USER32!GetWindowThreadProcessId` at `0x180054ec9`
- `USER32!GetWindowThreadProcessId` at `0x180054efb`

## pseudocode

```c
__int64 __fastcall MainFThunderMDI(__int64 *a1, HWND *a2, unsigned int *a3, unsigned __int64 *a4, __int64 *a5)
{
  HWND DesktopWindow; // rax
  HWND Window; // rdi
  void *WindowThreadProcessId; // rbx
  HWND v11; // rdi
  void *v12; // rbx

  *a1 = 0;
  switch ( *a3 )
  {
    case 0x18u:
      if ( *a5 == 3 && IsIconic(*a2) )
      {
        ShowWindow(*a2, 7);
        return 0;
      }
      goto LABEL_15;
    case 0x20u:
LABEL_15:
      if ( *a5 != 33685502 )
        return 1;
      DesktopWindow = GetDesktopWindow();
      Window = GetWindow(DesktopWindow, 5u);
      if ( Window )
      {
        do
        {
          if ( (GetWindowLongA(Window, -20) & 8) == 0 )
            break;
          Window = GetWindow(Window, 2u);
        }
        while ( Window );
        for ( ; Window; Window = GetWindow(Window, 2u) )
        {
          if ( IsWindowVisible(Window) )
            break;
        }
      }
      WindowThreadProcessId = (void *)GetWindowThreadProcessId(Window, 0);
      if ( WindowThreadProcessId == GetThreadWinTask() )
        return 1;
      v11 = GetWindow(Window, 2u);
      if ( !v11 )
        return 1;
      do
      {
        v12 = (void *)GetWindowThreadProcessId(v11, 0);
        if ( v12 == GetThreadWinTask() && IsWindowVisible(v11) )
          break;
        v11 = GetWindow(v11, 2u);
      }
      while ( v11 );
      if ( !v11 )
        return 1;
      SetForegroundWindow(v11);
      return 0;
    case 0x106u:
      if ( *a4 == 45 && Main_hwndMdiHack == SendMessageA(Main_hwndMdi, 0x229u, 0, 0) )
        return 0;
      break;
    case 0x112u:
      break;
    default:
      return 1;
  }
  if ( (*(_DWORD *)a4 & 0xFFF0) != 0xF100 || IsIconic(*a2) )
    return 1;
  Main_fRestoreFocus = 1;
  SetFocus(Main_hwndMainMenu);
  SendMessageA(Main_hwndMainMenu, 0x112u, *a4, *a5);
  return 0;
}

```

## disassembly

```asm
0x180054d50  mov     [rsp+arg_0], rbx
0x180054d55  mov     [rsp+arg_8], rsi
0x180054d5a  push    rdi
0x180054d5b  mov     eax, 20h
0x180054d60  call    _alloca_probe
0x180054d65  sub     rsp, rax
0x180054d68  and     qword ptr [rcx], 0
0x180054d6c  mov     ecx, [r8]
0x180054d6f  mov     rsi, [rsp+28h+arg_20]
0x180054d74  mov     rbx, r9
0x180054d77  mov     rdi, rdx
0x180054d7a  sub     ecx, 18h
0x180054d7d  jz      loc_180054E29
0x180054d83  sub     ecx, 8
0x180054d86  jz      loc_180054E4C
0x180054d8c  sub     ecx, 0E6h
0x180054d92  jz      short loc_180054DAE
0x180054d94  cmp     ecx, 0Ch
0x180054d97  jz      short loc_180054DD9
0x180054d99  mov     eax, 1
0x180054d9e  mov     rbx, [rsp+28h+arg_0]
0x180054da3  mov     rsi, [rsp+28h+arg_8]
0x180054da8  add     rsp, 20h
0x180054dac  pop     rdi
0x180054dad  retn
0x180054dae  cmp     qword ptr [r9], 2Dh ; '-'
0x180054db2  jnz     short loc_180054DD9
0x180054db4  mov     rcx, cs:?Main_hwndMdi@@3PEAUHWND__@@EA; hWnd
0x180054dbb  xor     r9d, r9d; lParam
0x180054dbe  xor     r8d, r8d; wParam
0x180054dc1  mov     edx, 229h; Msg
0x180054dc6  call    cs:__imp_SendMessageA
0x180054dcc  cmp     cs:?Main_hwndMdiHack@@3PEAUHWND__@@EA, rax; HWND__ * Main_hwndMdiHack
0x180054dd3  jnz     short loc_180054DD9
0x180054dd5  xor     eax, eax
0x180054dd7  jmp     short loc_180054D9E
0x180054dd9  mov     eax, [rbx]
0x180054ddb  and     eax, 0FFF0h
0x180054de0  cmp     rax, 0F100h
0x180054de6  jnz     short loc_180054D99
0x180054de8  mov     rcx, [rdi]; hWnd
0x180054deb  call    cs:__imp_IsIconic
0x180054df1  test    eax, eax
0x180054df3  jnz     short loc_180054D99
0x180054df5  mov     rcx, cs:?Main_hwndMainMenu@@3PEAUHWND__@@EA; hWnd
0x180054dfc  mov     cs:?Main_fRestoreFocus@@3HA, 1; int Main_fRestoreFocus
0x180054e06  call    cs:__imp_SetFocus
0x180054e0c  mov     r8, [rbx]; wParam
0x180054e0f  mov     rcx, cs:?Main_hwndMainMenu@@3PEAUHWND__@@EA; hWnd
0x180054e16  mov     r9, rsi
0x180054e19  mov     r9, [rsi]; lParam
0x180054e1c  mov     edx, 112h; Msg
0x180054e21  call    cs:__imp_SendMessageA
0x180054e27  jmp     short loc_180054DD5
0x180054e29  cmp     qword ptr [rsi], 3
0x180054e2d  jnz     short loc_180054E4C
0x180054e2f  mov     rcx, [rdx]; hWnd
0x180054e32  call    cs:__imp_IsIconic
0x180054e38  test    eax, eax
0x180054e3a  jz      short loc_180054E4C
0x180054e3c  mov     rcx, [rdi]; hWnd
0x180054e3f  mov     edx, 7; nCmdShow
0x180054e44  call    cs:__imp_ShowWindow
0x180054e4a  jmp     short loc_180054DD5
0x180054e4c  cmp     qword ptr [rsi], 201FFFEh
0x180054e53  jnz     loc_180054D99
0x180054e59  call    cs:__imp_GetDesktopWindow
0x180054e5f  mov     edx, 5; uCmd
0x180054e64  mov     rcx, rax; hWnd
0x180054e67  call    cs:__imp_GetWindow
0x180054e6d  mov     esi, 2
0x180054e72  mov     rdi, rax
0x180054e75  test    rax, rax
0x180054e78  jz      short loc_180054EC4
0x180054e7a  mov     edx, 0FFFFFFECh; nIndex
0x180054e7f  mov     rcx, rdi; hWnd
0x180054e82  call    cs:__imp_GetWindowLongA
0x180054e88  test    al, 8
0x180054e8a  jz      short loc_180054E9F
0x180054e8c  mov     edx, esi; uCmd
0x180054e8e  mov     rcx, rdi; hWnd
0x180054e91  call    cs:__imp_GetWindow
0x180054e97  mov     rdi, rax
0x180054e9a  test    rax, rax
0x180054e9d  jnz     short loc_180054E7A
0x180054e9f  test    rdi, rdi
0x180054ea2  jz      short loc_180054EC4
0x180054ea4  mov     rcx, rdi; hWnd
0x180054ea7  call    cs:__imp_IsWindowVisible
0x180054ead  test    eax, eax
0x180054eaf  jnz     short loc_180054EC4
0x180054eb1  mov     edx, esi; uCmd
0x180054eb3  mov     rcx, rdi; hWnd
0x180054eb6  call    cs:__imp_GetWindow
0x180054ebc  mov     rdi, rax
0x180054ebf  test    rax, rax
0x180054ec2  jnz     short loc_180054EA4
0x180054ec4  xor     edx, edx; lpdwProcessId
0x180054ec6  mov     rcx, rdi; hWnd
0x180054ec9  call    cs:__imp_GetWindowThreadProcessId
0x180054ecf  mov     ebx, eax
0x180054ed1  call    ?GetThreadWinTask@@YAPEAXXZ; GetThreadWinTask(void)
0x180054ed6  cmp     rbx, rax
0x180054ed9  jz      loc_180054D99
0x180054edf  mov     edx, esi; uCmd
0x180054ee1  mov     rcx, rdi; hWnd
0x180054ee4  call    cs:__imp_GetWindow
0x180054eea  mov     rdi, rax
0x180054eed  test    rax, rax
0x180054ef0  jz      loc_180054D99
0x180054ef6  xor     edx, edx; lpdwProcessId
0x180054ef8  mov     rcx, rdi; hWnd
0x180054efb  call    cs:__imp_GetWindowThreadProcessId
0x180054f01  mov     ebx, eax
0x180054f03  call    ?GetThreadWinTask@@YAPEAXXZ; GetThreadWinTask(void)
0x180054f08  cmp     rbx, rax
0x180054f0b  jnz     short loc_180054F1A
0x180054f0d  mov     rcx, rdi; hWnd
0x180054f10  call    cs:__imp_IsWindowVisible
0x180054f16  test    eax, eax
0x180054f18  jnz     short loc_180054F2D
0x180054f1a  mov     edx, esi; uCmd
0x180054f1c  mov     rcx, rdi; hWnd
0x180054f1f  call    cs:__imp_GetWindow
0x180054f25  mov     rdi, rax
0x180054f28  test    rax, rax
0x180054f2b  jnz     short loc_180054EF6
0x180054f2d  test    rdi, rdi
0x180054f30  jz      loc_180054D99
0x180054f36  mov     rcx, rdi; hWnd
0x180054f39  call    cs:__imp_SetForegroundWindow
0x180054f3f  jmp     loc_180054DD5
```
