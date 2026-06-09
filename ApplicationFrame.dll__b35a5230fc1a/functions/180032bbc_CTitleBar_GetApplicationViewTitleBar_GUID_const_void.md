# CTitleBar::_GetApplicationViewTitleBar(_GUID const &,void * *)

- ea: `0x180032bbc`
- end: `0x180032c34`
- name: `?_GetApplicationViewTitleBar@CTitleBar@@AEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `120`
- prototype: `int(CTitleBar *__hidden this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task`

## callers

- `0x180021be8`

## callees

- `0x180024184`
- `0x180032bbc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180032be2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180032be2`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180032bda`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180032bda`
- `TWINAPI!__imp_QueryWindowService` at `0x180032c0f`

## pseudocode

```c
__int64 __fastcall CTitleBar::_GetApplicationViewTitleBar(HWND *this, const struct _GUID *a2, void **a3)
{
  DWORD WindowThreadProcessId; // ebx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  WindowThreadProcessId = GetWindowThreadProcessId(this[63], 0);
  if ( GetCurrentThreadId() == WindowThreadProcessId )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x133F,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
      (const char *)0x80070057LL,
      v7);
  return QueryWindowService(
           this[63],
           &GUID_00924ac0_932b_4a6b_9c4b_dc38c82478ce,
           &GUID_00924ac0_932b_4a6b_9c4b_dc38c82478ce,
           a3);
}

```

## disassembly

```asm
0x180032bbc  mov     [rsp+arg_0], rbx
0x180032bc1  mov     [rsp+arg_8], rsi
0x180032bc6  push    rdi; int
0x180032bc7  sub     rsp, 20h
0x180032bcb  mov     rdi, rcx
0x180032bce  xor     edx, edx; lpdwProcessId
0x180032bd0  mov     rcx, [rcx+1F8h]; hWnd
0x180032bd7  mov     rsi, r8
0x180032bda  call    cs:__imp_GetWindowThreadProcessId
0x180032be0  mov     ebx, eax
0x180032be2  call    cs:__imp_GetCurrentThreadId
0x180032be8  cmp     eax, ebx
0x180032bea  jz      short loc_180032C16
0x180032bec  mov     rcx, [rdi+1F8h]
0x180032bf3  lea     rdx, _GUID_00924ac0_932b_4a6b_9c4b_dc38c82478ce
0x180032bfa  mov     r8, rdx
0x180032bfd  mov     r9, rsi
0x180032c00  mov     rbx, [rsp+28h+arg_0]
0x180032c05  mov     rsi, [rsp+28h+arg_8]
0x180032c0a  add     rsp, 20h
0x180032c0e  pop     rdi
0x180032c0f  jmp     cs:__imp_QueryWindowService
0x180032c16  mov     rcx, [rsp+28h]; this
0x180032c1b  lea     r8, aPcshellShellAp_12; "pcshell\\shell\\applicationframe\\frame"...
0x180032c22  mov     r9d, 80070057h; char *
0x180032c28  mov     edx, 133Fh; void *
0x180032c2d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180032c32  jmp     short loc_180032BEC
```
