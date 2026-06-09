# wil::details::RevertImpersonateToken(void *)

- ea: `0x180017dd0`
- end: `0x180017e02`
- name: `?RevertImpersonateToken@details@wil@@YAXPEAX@Z`
- size: `50`
- prototype: `void __fastcall(HANDLE hObject, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800162d8`
- `0x18001caf0`

## callees

- `0x180017dd0`
- `0x1800310d4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180017dde`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180017dde`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017df6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017df6`

## pseudocode

```c
void __fastcall wil::details::RevertImpersonateToken(HANDLE hObject, void *a2)
{
  wil::details::in1diag3 *v3; // rcx

  if ( !SetThreadToken(0, hObject) )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v3);
  if ( hObject )
    CloseHandle(hObject);
}

```

## disassembly

```asm
0x180017dd0  push    rbx
0x180017dd2  sub     rsp, 20h
0x180017dd6  mov     rbx, rcx
0x180017dd9  mov     rdx, rcx; Token
0x180017ddc  xor     ecx, ecx; Thread
0x180017dde  call    cs:__imp_SetThreadToken
0x180017de4  test    eax, eax
0x180017de6  jnz     short loc_180017DEE
0x180017de8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180017dee  test    rbx, rbx
0x180017df1  jz      short loc_180017DFC
0x180017df3  mov     rcx, rbx; hObject
0x180017df6  call    cs:__imp_CloseHandle
0x180017dfc  add     rsp, 20h
0x180017e00  pop     rbx
0x180017e01  retn
```
