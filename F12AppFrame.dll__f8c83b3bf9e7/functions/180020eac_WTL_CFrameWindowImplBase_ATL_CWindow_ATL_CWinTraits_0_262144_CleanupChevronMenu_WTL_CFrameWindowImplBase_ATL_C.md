# WTL::CFrameWindowImplBase<ATL::CWindow,ATL::CWinTraits<0,262144>>::CleanupChevronMenu(WTL::CFrameWindowImplBase<ATL::CWindow,ATL::CWinTraits<0,262144>>::_ChevronMenuInfo &)

- ea: `0x180020eac`
- end: `0x180020fb7`
- name: `?CleanupChevronMenu@?$CFrameWindowImplBase@VCWindow@ATL@@V?$CWinTraits@$0A@$0EAAAA@@2@@WTL@@QEAAXAEAU_ChevronMenuInfo@12@@Z`
- size: `267`
- prototype: `BOOL __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180027180`

## callees

- `0x180001800`
- `0x180020eac`

## import_xrefs

- `USER32!PeekMessageW` at `0x180020f5c`
- `USER32!PeekMessageW` at `0x180020f91`
- `USER32!PeekMessageW` at `0x180020f5c`
- `USER32!PeekMessageW` at `0x180020f91`
- `USER32!PtInRect` at `0x180020f70`
- `USER32!PtInRect` at `0x180020f70`
- `USER32!MapWindowPoints` at `0x180020f28`
- `USER32!MapWindowPoints` at `0x180020f28`
- `USER32!DestroyMenu` at `0x180020f04`
- `USER32!DestroyMenu` at `0x180020f04`
- `USER32!RemoveMenu` at `0x180020ef1`
- `USER32!RemoveMenu` at `0x180020ef1`
- `USER32!GetMenuItemCount` at `0x180020edc`
- `USER32!GetMenuItemCount` at `0x180020edc`

## pseudocode

```c
BOOL __fastcall WTL::CFrameWindowImplBase<ATL::CWindow,ATL::CWinTraits<0,262144>>::CleanupChevronMenu(
        __int64 a1,
        __int64 a2)
{
  HMENU v3; // rbx
  UINT i; // edi
  __int64 v6; // rax
  HWND v7; // rcx
  HWND v8; // rdx
  BOOL result; // eax
  tagMSG Msg; // [rsp+30h] [rbp-68h] BYREF
  struct tagPOINT Points[2]; // [rsp+60h] [rbp-38h] BYREF

  v3 = *(HMENU *)a2;
  if ( *(_BYTE *)(a2 + 16) )
  {
    for ( i = GetMenuItemCount(*(HMENU *)a2); (--i & 0x80000000) == 0; RemoveMenu(v3, i, 0x400u) )
      ;
  }
  if ( v3 )
    DestroyMenu(v3);
  v6 = *(_QWORD *)(a2 + 8);
  v7 = *(HWND *)v6;
  *(_OWORD *)&Points[0].x = *(_OWORD *)(v6 + 40);
  MapWindowPoints(v7, 0, Points, 2u);
  v8 = *(HWND *)(a1 + 8);
  memset(&Msg, 0, sizeof(Msg));
  result = PeekMessageW(&Msg, v8, 0x201u, 0x201u, 0);
  if ( result )
  {
    result = PtInRect((const RECT *)Points, Msg.pt);
    if ( result )
      return PeekMessageW(&Msg, *(HWND *)(a1 + 8), 0x201u, 0x201u, 1u);
  }
  return result;
}

```

## disassembly

```asm
0x180020eac  mov     [rsp+arg_10], rbx
0x180020eb1  push    rbp
0x180020eb2  push    rsi
0x180020eb3  push    rdi
0x180020eb4  sub     rsp, 80h
0x180020ebb  mov     rax, cs:__security_cookie
0x180020ec2  xor     rax, rsp
0x180020ec5  mov     [rsp+98h+var_28], rax
0x180020eca  cmp     byte ptr [rdx+10h], 0
0x180020ece  mov     rsi, rdx
0x180020ed1  mov     rbx, [rdx]
0x180020ed4  mov     rbp, rcx
0x180020ed7  jz      short loc_180020EFC
0x180020ed9  mov     rcx, rbx; hMenu
0x180020edc  call    cs:__imp_GetMenuItemCount
0x180020ee2  mov     edi, eax
0x180020ee4  jmp     short loc_180020EF7
0x180020ee6  mov     r8d, 400h; uFlags
0x180020eec  mov     edx, edi; uPosition
0x180020eee  mov     rcx, rbx; hMenu
0x180020ef1  call    cs:__imp_RemoveMenu
0x180020ef7  sub     edi, 1
0x180020efa  jns     short loc_180020EE6
0x180020efc  test    rbx, rbx
0x180020eff  jz      short loc_180020F0A
0x180020f01  mov     rcx, rbx; hMenu
0x180020f04  call    cs:__imp_DestroyMenu
0x180020f0a  mov     rax, [rsi+8]
0x180020f0e  lea     r8, [rsp+98h+Points]; lpPoints
0x180020f13  mov     r9d, 2; cPoints
0x180020f19  xor     edx, edx; hWndTo
0x180020f1b  movups  xmm0, xmmword ptr [rax+28h]
0x180020f1f  mov     rcx, [rax]; hWndFrom
0x180020f22  movdqu  xmmword ptr [rsp+98h+Points.x], xmm0
0x180020f28  call    cs:__imp_MapWindowPoints
0x180020f2e  mov     rdx, [rbp+8]; hWnd
0x180020f32  lea     rcx, [rsp+98h+Msg]; lpMsg
0x180020f37  xorps   xmm0, xmm0
0x180020f3a  mov     [rsp+98h+wRemoveMsg], 0; wRemoveMsg
0x180020f42  mov     ebx, 201h
0x180020f47  mov     r9d, ebx; wMsgFilterMax
0x180020f4a  mov     r8d, ebx; wMsgFilterMin
0x180020f4d  movups  xmmword ptr [rsp+98h+Msg.hwnd], xmm0
0x180020f52  movups  xmmword ptr [rsp+98h+Msg.wParam], xmm0
0x180020f57  movups  xmmword ptr [rsp+98h+Msg.time], xmm0
0x180020f5c  call    cs:__imp_PeekMessageW
0x180020f62  test    eax, eax
0x180020f64  jz      short loc_180020F97
0x180020f66  mov     rdx, qword ptr [rsp+98h+Msg.pt.x]; pt
0x180020f6b  lea     rcx, [rsp+98h+Points]; lprc
0x180020f70  call    cs:__imp_PtInRect
0x180020f76  test    eax, eax
0x180020f78  jz      short loc_180020F97
0x180020f7a  mov     rdx, [rbp+8]; hWnd
0x180020f7e  lea     rcx, [rsp+98h+Msg]; lpMsg
0x180020f83  mov     r9d, ebx; wMsgFilterMax
0x180020f86  mov     [rsp+98h+wRemoveMsg], 1; wRemoveMsg
0x180020f8e  mov     r8d, ebx; wMsgFilterMin
0x180020f91  call    cs:__imp_PeekMessageW
0x180020f97  mov     rcx, [rsp+98h+var_28]
0x180020f9c  xor     rcx, rsp; StackCookie
0x180020f9f  call    __security_check_cookie
0x180020fa4  mov     rbx, [rsp+98h+arg_10]
0x180020fac  add     rsp, 80h
0x180020fb3  pop     rdi
0x180020fb4  pop     rsi
0x180020fb5  pop     rbp
0x180020fb6  retn
```
