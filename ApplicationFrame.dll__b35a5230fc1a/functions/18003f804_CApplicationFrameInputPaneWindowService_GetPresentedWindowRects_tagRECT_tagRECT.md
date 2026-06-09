# CApplicationFrameInputPaneWindowService::_GetPresentedWindowRects(tagRECT *,tagRECT *)

- ea: `0x18003f804`
- end: `0x18003f91d`
- name: `?_GetPresentedWindowRects@CApplicationFrameInputPaneWindowService@@AEAAJPEAUtagRECT@@0@Z`
- size: `281`
- prototype: `int(CApplicationFrameInputPaneWindowService *__hidden this, struct tagRECT *, struct tagRECT *)`
- caller_count: `3`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800128d0`
- `0x18002bc50`
- `0x18005df50`

## callees

- `0x18003f804`
- `0x18003fbc0`
- `0x180040270`
- `0x180043c30`
- `0x180072010`

## import_xrefs

- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x18003f82b`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x18003f834`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x18003f82b`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x18003f834`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x18003f8b5`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x18003f8b5`
- `ext-ms-win-ntuser-window-l1-1-0!GetClientRect` at `0x18003f841`
- `ext-ms-win-ntuser-window-l1-1-0!GetClientRect` at `0x18003f841`
- `ext-ms-win-ntuser-window-l1-1-2!MapWindowPoints` at `0x18003f8e5`
- `ext-ms-win-ntuser-window-l1-1-2!MapWindowPoints` at `0x18003f8e5`

## string_xrefs

- `0x18003f850`: `pcshell\shell\applicationframe\frame\lib\inputpanewindowservice.cpp`
- `0x18003f897`: `pcshell\shell\applicationframe\frame\lib\inputpanewindowservice.cpp`

## pseudocode

```c
__int64 __fastcall CApplicationFrameInputPaneWindowService::_GetPresentedWindowRects(
        HWND *this,
        struct tagRECT *a2,
        struct tagRECT *a3)
{
  const char *v6; // r9
  HWND v8; // rcx
  int v9; // eax
  unsigned int v10; // ebx
  int v11[4]; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  SetRectEmpty(a2);
  SetRectEmpty(a3);
  if ( !GetClientRect(this[7], a2) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x13E,
             (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\inputpanewindowservice.cpp",
             v6);
  v8 = this[6];
  if ( v8 )
  {
    *(_OWORD *)v11 = 0;
    v9 = (*(__int64 (__fastcall **)(HWND, int *))(*(_QWORD *)v8 + 120LL))(v8, v11);
    v10 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x143,
        (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\inputpanewindowservice.cpp",
        (const char *)(unsigned int)v9,
        v11[0]);
      return v10;
    }
    CopyRect(a3, a2);
    a3->left += v11[0];
    a3->top += v11[1];
    a3->right -= v11[2];
    a3->bottom -= v11[3];
    MapWindowPoints(this[7], 0, (LPPOINT)a3, 2u);
    a2->right -= v11[2] + v11[0];
    a2->bottom -= v11[3] + v11[1];
  }
  return 0;
}

```

## disassembly

```asm
0x18003f804  mov     [rsp+arg_18], rbx
0x18003f809  push    rbp
0x18003f80a  push    rsi
0x18003f80b  push    rdi
0x18003f80c  sub     rsp, 40h
0x18003f810  mov     rax, cs:__security_cookie
0x18003f817  xor     rax, rsp
0x18003f81a  mov     [rsp+58h+var_28], rax
0x18003f81f  mov     rbp, rcx
0x18003f822  mov     rdi, r8
0x18003f825  mov     rcx, rdx; lprc
0x18003f828  mov     rsi, rdx
0x18003f82b  call    cs:__imp_SetRectEmpty
0x18003f831  mov     rcx, rdi; lprc
0x18003f834  call    cs:__imp_SetRectEmpty
0x18003f83a  mov     rcx, [rbp+38h]; hWnd
0x18003f83e  mov     rdx, rsi; lpRect
0x18003f841  call    cs:__imp_GetClientRect
0x18003f847  test    eax, eax
0x18003f849  jnz     short loc_18003F866
0x18003f84b  mov     rcx, [rsp+58h]; this
0x18003f850  lea     r8, aPcshellShellAp_9; "pcshell\\shell\\applicationframe\\frame"...
0x18003f857  mov     edx, 13Eh; void *
0x18003f85c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003f861  jmp     loc_18003F903
0x18003f866  mov     rcx, [rbp+30h]
0x18003f86a  test    rcx, rcx
0x18003f86d  jz      loc_18003F901
0x18003f873  xorps   xmm0, xmm0
0x18003f876  lea     rdx, [rsp+58h+var_38]
0x18003f87b  movups  xmmword ptr [rsp+58h+var_38], xmm0; int
0x18003f880  mov     rax, [rcx]
0x18003f883  mov     rax, [rax+78h]
0x18003f887  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f88c  mov     ebx, eax
0x18003f88e  test    eax, eax
0x18003f890  jns     short loc_18003F8AF
0x18003f892  mov     rcx, [rsp+58h]; this
0x18003f897  lea     r8, aPcshellShellAp_9; "pcshell\\shell\\applicationframe\\frame"...
0x18003f89e  mov     r9d, eax; char *
0x18003f8a1  mov     edx, 143h; void *
0x18003f8a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f8ab  mov     eax, ebx
0x18003f8ad  jmp     short loc_18003F903
0x18003f8af  mov     rdx, rsi; lprcSrc
0x18003f8b2  mov     rcx, rdi; lprcDst
0x18003f8b5  call    cs:__imp_CopyRect
0x18003f8bb  mov     eax, [rsp+58h+var_38]
0x18003f8bf  mov     r9d, 2; cPoints
0x18003f8c5  add     [rdi], eax
0x18003f8c7  mov     r8, rdi; lpPoints
0x18003f8ca  mov     eax, [rsp+58h+var_38+4]
0x18003f8ce  xor     edx, edx; hWndTo
0x18003f8d0  add     [rdi+4], eax
0x18003f8d3  mov     eax, [rsp+58h+var_38+8]
0x18003f8d7  sub     [rdi+8], eax
0x18003f8da  mov     eax, [rsp+58h+var_38+0Ch]
0x18003f8de  sub     [rdi+0Ch], eax
0x18003f8e1  mov     rcx, [rbp+38h]; hWndFrom
0x18003f8e5  call    cs:__imp_MapWindowPoints
0x18003f8eb  mov     ecx, [rsp+58h+var_38]
0x18003f8ef  add     ecx, [rsp+58h+var_38+8]
0x18003f8f3  sub     [rsi+8], ecx
0x18003f8f6  mov     ecx, [rsp+58h+var_38+4]
0x18003f8fa  add     ecx, [rsp+58h+var_38+0Ch]
0x18003f8fe  sub     [rsi+0Ch], ecx
0x18003f901  xor     eax, eax
0x18003f903  mov     rcx, [rsp+58h+var_28]
0x18003f908  xor     rcx, rsp; StackCookie
0x18003f90b  call    __security_check_cookie
0x18003f910  mov     rbx, [rsp+58h+arg_18]
0x18003f915  add     rsp, 40h
0x18003f919  pop     rdi
0x18003f91a  pop     rsi
0x18003f91b  pop     rbp
0x18003f91c  retn
```
