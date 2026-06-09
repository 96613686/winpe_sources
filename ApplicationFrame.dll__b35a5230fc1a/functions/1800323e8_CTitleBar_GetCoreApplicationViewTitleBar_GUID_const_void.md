# CTitleBar::_GetCoreApplicationViewTitleBar(_GUID const &,void * *)

- ea: `0x1800323e8`
- end: `0x180032460`
- name: `?_GetCoreApplicationViewTitleBar@CTitleBar@@AEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `120`
- prototype: `int(CTitleBar *__hidden this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task`

## callers

- `0x180059230`

## callees

- `0x180024184`
- `0x1800323e8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003240e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003240e`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180032406`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180032406`
- `TWINAPI!__imp_QueryWindowService` at `0x18003243b`

## pseudocode

```c
__int64 __fastcall CTitleBar::_GetCoreApplicationViewTitleBar(HWND *this, const struct _GUID *a2, void **a3)
{
  DWORD WindowThreadProcessId; // ebx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  WindowThreadProcessId = GetWindowThreadProcessId(this[63], 0);
  if ( GetCurrentThreadId() == WindowThreadProcessId )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1347,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
      (const char *)0x80070057LL,
      v7);
  return QueryWindowService(
           this[63],
           &GUID_006d35e3_e1f1_431b_9508_29b96926ac53,
           &GUID_006d35e3_e1f1_431b_9508_29b96926ac53,
           a3);
}

```

## disassembly

```asm
0x1800323e8  mov     [rsp+arg_0], rbx
0x1800323ed  mov     [rsp+arg_8], rsi
0x1800323f2  push    rdi; int
0x1800323f3  sub     rsp, 20h
0x1800323f7  mov     rdi, rcx
0x1800323fa  xor     edx, edx; lpdwProcessId
0x1800323fc  mov     rcx, [rcx+1F8h]; hWnd
0x180032403  mov     rsi, r8
0x180032406  call    cs:__imp_GetWindowThreadProcessId
0x18003240c  mov     ebx, eax
0x18003240e  call    cs:__imp_GetCurrentThreadId
0x180032414  cmp     eax, ebx
0x180032416  jz      short loc_180032442
0x180032418  mov     rcx, [rdi+1F8h]
0x18003241f  lea     rdx, _GUID_006d35e3_e1f1_431b_9508_29b96926ac53
0x180032426  mov     r8, rdx
0x180032429  mov     r9, rsi
0x18003242c  mov     rbx, [rsp+28h+arg_0]
0x180032431  mov     rsi, [rsp+28h+arg_8]
0x180032436  add     rsp, 20h
0x18003243a  pop     rdi
0x18003243b  jmp     cs:__imp_QueryWindowService
0x180032442  mov     rcx, [rsp+28h]; this
0x180032447  lea     r8, aPcshellShellAp_12; "pcshell\\shell\\applicationframe\\frame"...
0x18003244e  mov     r9d, 80070057h; char *
0x180032454  mov     edx, 1347h; void *
0x180032459  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003245e  jmp     short loc_180032418
```
