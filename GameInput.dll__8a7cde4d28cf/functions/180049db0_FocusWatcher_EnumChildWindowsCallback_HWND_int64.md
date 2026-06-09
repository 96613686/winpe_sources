# FocusWatcher::EnumChildWindowsCallback(HWND__ *,__int64)

- ea: `0x180049db0`
- end: `0x180049ded`
- name: `?EnumChildWindowsCallback@FocusWatcher@@CAHPEAUHWND__@@_J@Z`
- size: `61`
- prototype: `BOOL __stdcall(HWND, LPARAM)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x180049db0`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180049dc6`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180049dc6`

## pseudocode

```c
__int64 __fastcall FocusWatcher::EnumChildWindowsCallback(HWND a1, _DWORD *a2)
{
  DWORD dwProcessId; // [rsp+38h] [rbp+10h] BYREF

  dwProcessId = 0;
  GetWindowThreadProcessId(a1, &dwProcessId);
  if ( dwProcessId && dwProcessId != *a2 )
    a2[1] = dwProcessId;
  return 1;
}

```

## disassembly

```asm
0x180049db0  push    rbx
0x180049db2  sub     rsp, 20h
0x180049db6  mov     rbx, rdx
0x180049db9  mov     [rsp+28h+dwProcessId], 0
0x180049dc1  lea     rdx, [rsp+28h+dwProcessId]; lpdwProcessId
0x180049dc6  call    cs:__imp_GetWindowThreadProcessId
0x180049dcd  nop     dword ptr [rax+rax+00h]
0x180049dd2  mov     eax, [rsp+28h+dwProcessId]
0x180049dd6  test    eax, eax
0x180049dd8  jz      short loc_180049DE1
0x180049dda  cmp     eax, [rbx]
0x180049ddc  jz      short loc_180049DE1
0x180049dde  mov     [rbx+4], eax
0x180049de1  mov     eax, 1
0x180049de6  add     rsp, 20h
0x180049dea  pop     rbx
0x180049deb  retn
```
