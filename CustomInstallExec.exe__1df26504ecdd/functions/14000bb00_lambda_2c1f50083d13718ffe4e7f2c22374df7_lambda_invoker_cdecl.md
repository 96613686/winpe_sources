# _lambda_2c1f50083d13718ffe4e7f2c22374df7_::_lambda_invoker_cdecl_

- ea: `0x14000bb00`
- end: `0x14000bb46`
- name: `_lambda_2c1f50083d13718ffe4e7f2c22374df7_::_lambda_invoker_cdecl_`
- size: `70`
- prototype: `__int64 __fastcall(HWND, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x14000bb00`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetForegroundWindow` at `0x14000bb2c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetForegroundWindow` at `0x14000bb2c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x14000bb1d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x14000bb1d`

## pseudocode

```c
__int64 __fastcall lambda_2c1f50083d13718ffe4e7f2c22374df7_::_lambda_invoker_cdecl_(HWND a1, int a2)
{
  DWORD dwProcessId; // [rsp+38h] [rbp+10h] BYREF

  dwProcessId = 0;
  GetWindowThreadProcessId(a1, &dwProcessId);
  if ( dwProcessId != a2 )
    return 1;
  SetForegroundWindow(a1);
  return 0;
}

```

## disassembly

```asm
0x14000bb00  mov     [rsp+arg_0], rbx
0x14000bb05  push    rdi
0x14000bb06  sub     rsp, 20h
0x14000bb0a  mov     rbx, rdx
0x14000bb0d  mov     [rsp+28h+dwProcessId], 0
0x14000bb15  lea     rdx, [rsp+28h+dwProcessId]; lpdwProcessId
0x14000bb1a  mov     rdi, rcx
0x14000bb1d  call    cs:__imp_GetWindowThreadProcessId
0x14000bb23  cmp     [rsp+28h+dwProcessId], ebx
0x14000bb27  jnz     short loc_14000BB36
0x14000bb29  mov     rcx, rdi; hWnd
0x14000bb2c  call    cs:__imp_SetForegroundWindow
0x14000bb32  xor     eax, eax
0x14000bb34  jmp     short loc_14000BB3B
0x14000bb36  mov     eax, 1
0x14000bb3b  mov     rbx, [rsp+28h+arg_0]
0x14000bb40  add     rsp, 20h
0x14000bb44  pop     rdi
0x14000bb45  retn
```
