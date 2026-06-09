# CSystemPopupWindow::ShowSystemDialog(ushort const *,ushort const *,void *,void *)

- ea: `0x140008124`
- end: `0x140008362`
- name: `?ShowSystemDialog@CSystemPopupWindow@@QEAAJPEBG0PEAX1@Z`
- size: `574`
- prototype: `__int64 __fastcall(CSystemPopupWindow *this, const unsigned __int16 *, const unsigned __int16 *, void *, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x140004f6c`

## callees

- `0x140001460`
- `0x1400080f4`
- `0x140008124`
- `0x14000849c`
- `0x140008698`
- `0x140008790`
- `0x140008a3c`
- `0x14000a010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x14000833c`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x14000833c`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x14000815b`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x14000815b`
- `USER32!PeekMessageW` at `0x140008314`
- `USER32!PeekMessageW` at `0x140008314`
- `USER32!MsgWaitForMultipleObjects` at `0x1400082ae`
- `USER32!MsgWaitForMultipleObjects` at `0x1400082ae`
- `USER32!DispatchMessageW` at `0x1400082fa`
- `USER32!DispatchMessageW` at `0x1400082fa`
- `USER32!TranslateMessage` at `0x1400082f0`
- `USER32!TranslateMessage` at `0x1400082f0`
- `DUI70!InitProcessPriv` at `0x14000819f`
- `DUI70!InitProcessPriv` at `0x14000819f`
- `DUI70!UnInitThread` at `0x140008236`
- `DUI70!UnInitThread` at `0x140008326`
- `DUI70!UnInitThread` at `0x140008236`
- `DUI70!UnInitThread` at `0x140008326`
- `DUI70!UnInitProcessPriv` at `0x1400081fd`
- `DUI70!UnInitProcessPriv` at `0x140008334`
- `DUI70!UnInitProcessPriv` at `0x1400081fd`
- `DUI70!UnInitProcessPriv` at `0x140008334`
- `DUI70!InitThread` at `0x1400081d1`
- `DUI70!InitThread` at `0x1400081d1`

## pseudocode

```c
__int64 __fastcall CSystemPopupWindow::ShowSystemDialog(
        CSystemPopupWindow *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        void *a4,
        void *a5)
{
  int v9; // eax
  __int64 v10; // r8
  unsigned int v11; // ebx
  int inited; // eax
  int v13; // eax
  int SystemPopupWindow; // eax
  __int64 v15; // rdx
  char v16; // bl
  DWORD v17; // eax
  DWORD dwWakeMask; // [rsp+20h] [rbp-51h]
  MSG Msg; // [rsp+40h] [rbp-31h] BYREF
  HANDLE pHandles[2]; // [rsp+70h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+57h]

  v9 = RoInitialize(0, a2, a3, a4);
  v11 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19,
      (unsigned int)"drivers\\mobilepc\\location\\product\\winactiondialog\\lib\\popupwindow.cpp",
      (const char *)(unsigned int)v9,
      dwWakeMask);
    return v11;
  }
  LOBYTE(dwWakeMask) = 1;
  LOBYTE(v10) = 1;
  inited = InitProcessPriv(14, 0x140000000uLL, v10);
  v11 = inited;
  if ( inited < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D,
      (unsigned int)"drivers\\mobilepc\\location\\product\\winactiondialog\\lib\\popupwindow.cpp",
      (const char *)(unsigned int)inited,
      dwWakeMask);
    goto LABEL_30;
  }
  v13 = InitThread(65538);
  v11 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x21,
      (unsigned int)"drivers\\mobilepc\\location\\product\\winactiondialog\\lib\\popupwindow.cpp",
      (const char *)(unsigned int)v13,
      dwWakeMask);
LABEL_7:
    UnInitProcessPriv(0x140000000uLL);
    goto LABEL_30;
  }
  SystemPopupWindow = CSystemPopupWindow::_CreateSystemPopupWindow(this, a2);
  v11 = SystemPopupWindow;
  if ( SystemPopupWindow < 0 )
  {
    v15 = 38;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"drivers\\mobilepc\\location\\product\\winactiondialog\\lib\\popupwindow.cpp",
      (const char *)(unsigned int)SystemPopupWindow,
      dwWakeMask);
    UnInitThread();
    goto LABEL_7;
  }
  SystemPopupWindow = CSystemPopupWindow::_SetContentElement(this, a3);
  v11 = SystemPopupWindow;
  if ( SystemPopupWindow < 0 )
  {
    v15 = 39;
    goto LABEL_10;
  }
  SystemPopupWindow = CSystemPopupWindow::_SetButtonsOnDialog(this);
  v11 = SystemPopupWindow;
  if ( SystemPopupWindow < 0 )
  {
    v15 = 40;
    goto LABEL_10;
  }
  SystemPopupWindow = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 272LL))(*(_QWORD *)this);
  v11 = SystemPopupWindow;
  if ( SystemPopupWindow < 0 )
  {
    v15 = 41;
    goto LABEL_10;
  }
  v16 = 0;
  do
  {
    pHandles[0] = a4;
    pHandles[1] = a5;
    v17 = MsgWaitForMultipleObjects(2u, pHandles, 0, 0xFFFFFFFF, 0x1CFFu);
    if ( !v17 )
    {
      *((_DWORD *)this + 2) = 2;
LABEL_22:
      CSystemPopupWindow::_DestroyWindow(this);
      goto LABEL_23;
    }
    if ( v17 == 1 )
    {
      *((_DWORD *)this + 2) = 3;
      goto LABEL_22;
    }
LABEL_23:
    memset(&Msg, 0, sizeof(Msg));
    while ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
    {
      if ( Msg.message == 18 )
      {
        v16 = 1;
      }
      else
      {
        TranslateMessage(&Msg);
        DispatchMessageW(&Msg);
      }
    }
  }
  while ( !v16 );
  UnInitThread();
  UnInitProcessPriv(0x140000000uLL);
  v11 = 0;
LABEL_30:
  RoUninitialize();
  return v11;
}

```

## disassembly

```asm
0x140008124  push    rbp
0x140008126  push    rbx
0x140008127  push    rsi
0x140008128  push    rdi
0x140008129  push    r12
0x14000812b  push    r14
0x14000812d  push    r15
0x14000812f  lea     rbp, [rsp-1Fh]
0x140008134  sub     rsp, 90h
0x14000813b  mov     rax, cs:__security_cookie
0x140008142  xor     rax, rsp
0x140008145  mov     [rbp+4Fh+var_40], rax
0x140008149  mov     r15, r9
0x14000814c  mov     r14, r8
0x14000814f  mov     rsi, rdx
0x140008152  mov     rdi, rcx
0x140008155  mov     r12, [rbp+4Fh+arg_20]
0x140008159  xor     ecx, ecx
0x14000815b  call    cs:__imp_RoInitialize
0x140008161  mov     ebx, eax
0x140008163  test    eax, eax
0x140008165  jns     short loc_140008184
0x140008167  mov     rcx, [rbp+57h]; this
0x14000816b  mov     r9d, eax; char *
0x14000816e  lea     r8, aDriversMobilep_1; "drivers\\mobilepc\\location\\product\\w"...
0x140008175  mov     edx, 19h; void *
0x14000817a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000817f  jmp     loc_140008342
0x140008184  mov     [rbp+4Fh+var_8F], 1
0x140008188  mov     byte ptr [rsp+0C0h+dwWakeMask], 1; int
0x14000818d  mov     r9b, 1
0x140008190  mov     r8b, r9b
0x140008193  lea     rdx, cs:140000000h
0x14000819a  mov     ecx, 0Eh
0x14000819f  call    cs:__imp_InitProcessPriv
0x1400081a5  mov     ebx, eax
0x1400081a7  test    eax, eax
0x1400081a9  jns     short loc_1400081C8
0x1400081ab  mov     rcx, [rbp+57h]; this
0x1400081af  mov     r9d, eax; char *
0x1400081b2  lea     r8, aDriversMobilep_1; "drivers\\mobilepc\\location\\product\\w"...
0x1400081b9  mov     edx, 1Dh; void *
0x1400081be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400081c3  jmp     loc_14000833C
0x1400081c8  mov     [rbp+4Fh+var_8B], 1
0x1400081cc  mov     ecx, 10002h
0x1400081d1  call    cs:__imp_InitThread
0x1400081d7  mov     ebx, eax
0x1400081d9  test    eax, eax
0x1400081db  jns     short loc_140008208
0x1400081dd  mov     rcx, [rbp+57h]; this
0x1400081e1  mov     r9d, eax; char *
0x1400081e4  lea     r8, aDriversMobilep_1; "drivers\\mobilepc\\location\\product\\w"...
0x1400081eb  mov     edx, 21h ; '!'; void *
0x1400081f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400081f5  nop
0x1400081f6  lea     rcx, cs:140000000h
0x1400081fd  call    cs:__imp_UnInitProcessPriv
0x140008203  jmp     loc_14000833C
0x140008208  mov     [rbp+4Fh+var_87], 1
0x14000820c  mov     rdx, rsi; unsigned __int16 *
0x14000820f  mov     rcx, rdi; this
0x140008212  call    ?_CreateSystemPopupWindow@CSystemPopupWindow@@AEAAJPEBG@Z; CSystemPopupWindow::_CreateSystemPopupWindow(ushort const *)
0x140008217  mov     ebx, eax
0x140008219  test    eax, eax
0x14000821b  jns     short loc_14000823E
0x14000821d  mov     edx, 26h ; '&'; void *
0x140008222  lea     r8, aDriversMobilep_1; "drivers\\mobilepc\\location\\product\\w"...
0x140008229  mov     r9d, eax; char *
0x14000822c  mov     rcx, [rbp+57h]; this
0x140008230  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008235  nop
0x140008236  call    cs:__imp_UnInitThread
0x14000823c  jmp     short loc_1400081F6
0x14000823e  mov     rdx, r14; unsigned __int16 *
0x140008241  mov     rcx, rdi; this
0x140008244  call    ?_SetContentElement@CSystemPopupWindow@@AEAAJPEBG@Z; CSystemPopupWindow::_SetContentElement(ushort const *)
0x140008249  mov     ebx, eax
0x14000824b  test    eax, eax
0x14000824d  jns     short loc_140008256
0x14000824f  mov     edx, 27h ; '''
0x140008254  jmp     short loc_140008222
0x140008256  mov     rcx, rdi; this
0x140008259  call    ?_SetButtonsOnDialog@CSystemPopupWindow@@AEAAJXZ; CSystemPopupWindow::_SetButtonsOnDialog(void)
0x14000825e  mov     ebx, eax
0x140008260  test    eax, eax
0x140008262  jns     short loc_14000826B
0x140008264  mov     edx, 28h ; '('
0x140008269  jmp     short loc_140008222
0x14000826b  mov     rcx, [rdi]
0x14000826e  mov     rax, [rcx]
0x140008271  mov     rax, [rax+110h]
0x140008278  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000827d  mov     ebx, eax
0x14000827f  test    eax, eax
0x140008281  jns     short loc_14000828A
0x140008283  mov     edx, 29h ; ')'
0x140008288  jmp     short loc_140008222
0x14000828a  xor     bl, bl
0x14000828c  mov     esi, 2
0x140008291  mov     [rbp+4Fh+pHandles], r15
0x140008295  mov     [rbp+4Fh+var_48], r12
0x140008299  mov     [rsp+0C0h+dwWakeMask], 1CFFh; dwWakeMask
0x1400082a1  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1400082a5  xor     r8d, r8d; fWaitAll
0x1400082a8  lea     rdx, [rbp+4Fh+pHandles]; pHandles
0x1400082ac  mov     ecx, esi; nCount
0x1400082ae  call    cs:__imp_MsgWaitForMultipleObjects
0x1400082b4  test    eax, eax
0x1400082b6  jnz     short loc_1400082BD
0x1400082b8  mov     [rdi+8], esi
0x1400082bb  jmp     short loc_1400082C9
0x1400082bd  cmp     eax, 1
0x1400082c0  jnz     short loc_1400082D1
0x1400082c2  mov     dword ptr [rdi+8], 3
0x1400082c9  mov     rcx, rdi; this
0x1400082cc  call    ?_DestroyWindow@CSystemPopupWindow@@AEAAXXZ; CSystemPopupWindow::_DestroyWindow(void)
0x1400082d1  xorps   xmm0, xmm0
0x1400082d4  movups  xmmword ptr [rbp+4Fh+Msg.hwnd], xmm0
0x1400082d8  movups  xmmword ptr [rbp+4Fh+Msg.wParam], xmm0
0x1400082dc  movups  xmmword ptr [rbp+4Fh+Msg.time], xmm0
0x1400082e0  jmp     short loc_140008300
0x1400082e2  cmp     [rbp+4Fh+Msg.message], 12h
0x1400082e6  jnz     short loc_1400082EC
0x1400082e8  mov     bl, 1
0x1400082ea  jmp     short loc_140008300
0x1400082ec  lea     rcx, [rbp+4Fh+Msg]; lpMsg
0x1400082f0  call    cs:__imp_TranslateMessage
0x1400082f6  lea     rcx, [rbp+4Fh+Msg]; lpMsg
0x1400082fa  call    cs:__imp_DispatchMessageW
0x140008300  mov     [rsp+0C0h+dwWakeMask], 1; wRemoveMsg
0x140008308  xor     r9d, r9d; wMsgFilterMax
0x14000830b  xor     r8d, r8d; wMsgFilterMin
0x14000830e  xor     edx, edx; hWnd
0x140008310  lea     rcx, [rbp+4Fh+Msg]; lpMsg
0x140008314  call    cs:__imp_PeekMessageW
0x14000831a  test    eax, eax
0x14000831c  jnz     short loc_1400082E2
0x14000831e  test    bl, bl
0x140008320  jz      loc_140008291
0x140008326  call    cs:__imp_UnInitThread
0x14000832c  nop
0x14000832d  lea     rcx, cs:140000000h
0x140008334  call    cs:__imp_UnInitProcessPriv
0x14000833a  xor     ebx, ebx
0x14000833c  call    cs:__imp_RoUninitialize
0x140008342  mov     eax, ebx
0x140008344  mov     rcx, [rbp+4Fh+var_40]
0x140008348  xor     rcx, rsp; StackCookie
0x14000834b  call    __security_check_cookie
0x140008350  add     rsp, 90h
0x140008357  pop     r15
0x140008359  pop     r14
0x14000835b  pop     r12
0x14000835d  pop     rdi
0x14000835e  pop     rsi
0x14000835f  pop     rbx
0x140008360  pop     rbp
0x140008361  retn
```
