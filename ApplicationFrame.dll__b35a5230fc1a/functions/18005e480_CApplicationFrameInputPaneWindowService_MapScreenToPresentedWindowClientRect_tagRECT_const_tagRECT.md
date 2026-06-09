# CApplicationFrameInputPaneWindowService::_MapScreenToPresentedWindowClientRect(tagRECT const *,tagRECT *)

- ea: `0x18005e480`
- end: `0x18005e52f`
- name: `?_MapScreenToPresentedWindowClientRect@CApplicationFrameInputPaneWindowService@@AEAAJPEBUtagRECT@@PEAU2@@Z`
- size: `175`
- prototype: `int(CApplicationFrameInputPaneWindowService *__hidden this, const struct tagRECT *, struct tagRECT *)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800128d0`
- `0x18002bc50`
- `0x18005df50`

## callees

- `0x180040270`
- `0x180043c30`
- `0x18005e480`
- `0x180072010`

## import_xrefs

- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x18005e4a2`
- `api-ms-win-ntuser-rectangle-l1-1-0!CopyRect` at `0x18005e4a2`
- `ext-ms-win-ntuser-window-l1-1-2!MapWindowPoints` at `0x18005e4b7`
- `ext-ms-win-ntuser-window-l1-1-2!MapWindowPoints` at `0x18005e4b7`

## string_xrefs

- `0x18005e4ea`: `pcshell\shell\applicationframe\frame\lib\inputpanewindowservice.cpp`

## pseudocode

```c
__int64 __fastcall CApplicationFrameInputPaneWindowService::_MapScreenToPresentedWindowClientRect(
        HWND *this,
        const struct tagRECT *a2,
        struct tagRECT *a3)
{
  HWND v5; // rcx
  int v6; // eax
  unsigned int v7; // ebx
  int v9; // ecx
  int v10; // eax
  int v11[4]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  CopyRect(a3, a2);
  MapWindowPoints(0, this[7], (LPPOINT)a3, 2u);
  v5 = this[6];
  if ( v5 )
  {
    *(_OWORD *)v11 = 0;
    v6 = (*(__int64 (__fastcall **)(HWND, int *))(*(_QWORD *)v5 + 120LL))(v5, v11);
    v7 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x165,
        (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\inputpanewindowservice.cpp",
        (const char *)(unsigned int)v6,
        v11[0]);
      return v7;
    }
    v9 = v11[0];
    v10 = v11[1];
    a3->left -= v11[0];
    a3->top -= v10;
    a3->right -= v9;
    a3->bottom -= v10;
  }
  return 0;
}

```

## disassembly

```asm
0x18005e480  mov     [rsp+arg_18], rbx
0x18005e485  push    rdi
0x18005e486  sub     rsp, 40h
0x18005e48a  mov     rax, cs:__security_cookie
0x18005e491  xor     rax, rsp
0x18005e494  mov     [rsp+48h+var_18], rax
0x18005e499  mov     rbx, rcx
0x18005e49c  mov     rdi, r8
0x18005e49f  mov     rcx, r8; lprcDst
0x18005e4a2  call    cs:__imp_CopyRect
0x18005e4a8  mov     rdx, [rbx+38h]; hWndTo
0x18005e4ac  mov     r9d, 2; cPoints
0x18005e4b2  mov     r8, rdi; lpPoints
0x18005e4b5  xor     ecx, ecx; hWndFrom
0x18005e4b7  call    cs:__imp_MapWindowPoints
0x18005e4bd  mov     rcx, [rbx+30h]
0x18005e4c1  test    rcx, rcx
0x18005e4c4  jz      short loc_18005E515
0x18005e4c6  xorps   xmm0, xmm0
0x18005e4c9  lea     rdx, [rsp+48h+var_28]
0x18005e4ce  movups  xmmword ptr [rsp+48h+var_28], xmm0; int
0x18005e4d3  mov     rax, [rcx]
0x18005e4d6  mov     rax, [rax+78h]
0x18005e4da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e4df  mov     ebx, eax
0x18005e4e1  test    eax, eax
0x18005e4e3  jns     short loc_18005E502
0x18005e4e5  mov     rcx, [rsp+48h]; this
0x18005e4ea  lea     r8, aPcshellShellAp_9; "pcshell\\shell\\applicationframe\\frame"...
0x18005e4f1  mov     r9d, eax; char *
0x18005e4f4  mov     edx, 165h; void *
0x18005e4f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e4fe  mov     eax, ebx
0x18005e500  jmp     short loc_18005E517
0x18005e502  mov     ecx, [rsp+48h+var_28]
0x18005e506  mov     eax, [rsp+48h+var_28+4]
0x18005e50a  sub     [rdi], ecx
0x18005e50c  sub     [rdi+4], eax
0x18005e50f  sub     [rdi+8], ecx
0x18005e512  sub     [rdi+0Ch], eax
0x18005e515  xor     eax, eax
0x18005e517  mov     rcx, [rsp+48h+var_18]
0x18005e51c  xor     rcx, rsp; StackCookie
0x18005e51f  call    __security_check_cookie
0x18005e524  mov     rbx, [rsp+48h+arg_18]
0x18005e529  add     rsp, 40h
0x18005e52d  pop     rdi
0x18005e52e  retn
```
