# BrowserToolThreadWindow::PreTranslateMessage(tagMSG *)

- ea: `0x1800087c0`
- end: `0x180008988`
- name: `?PreTranslateMessage@BrowserToolThreadWindow@@UEAAHPEAUtagMSG@@@Z`
- size: `456`
- prototype: `int(BrowserToolThreadWindow *__hidden this, struct tagMSG *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800087c0`
- `0x1800090e4`
- `0x1800111f4`
- `0x18002fa74`
- `0x1800300f0`
- `0x180035010`

## import_xrefs

- `USER32!PostMessageW` at `0x18000890d`
- `USER32!PostMessageW` at `0x18000895e`
- `USER32!PostMessageW` at `0x18000890d`
- `USER32!PostMessageW` at `0x18000895e`
- `USER32!SendMessageW` at `0x1800088c8`
- `USER32!SendMessageW` at `0x180008925`
- `USER32!SendMessageW` at `0x1800088c8`
- `USER32!SendMessageW` at `0x180008925`
- `USER32!GetKeyState` at `0x1800088ed`
- `USER32!GetKeyState` at `0x1800088ed`

## pseudocode

```c
__int64 __fastcall BrowserToolThreadWindow::PreTranslateMessage(
        BrowserToolThreadWindow *this,
        struct tagMSG *a2,
        const struct tagMSG *a3)
{
  int v5; // eax
  unsigned __int64 v6; // r8
  int v7; // ecx
  __int64 v8; // r14
  __int64 (__fastcall *v9)(__int64, _QWORD, _QWORD, __int16 *); // rsi
  BOOL v10; // edi
  unsigned __int64 v11; // r8
  BOOL v12; // ebx
  unsigned __int64 v13; // r8
  bool v14; // al
  bool v15; // zf
  LRESULT v16; // rbx
  UINT message; // edx
  unsigned __int16 KeyState; // ax
  WPARAM wParam; // r8
  __int16 v21; // [rsp+68h] [rbp+10h] BYREF

  if ( a2 && *((_QWORD *)this + 3) && a2->message - 256 <= 9 )
  {
    if ( F12::ProcessShortcutKeys(*((HWND *)this + 7), a2, a3)
      || BrowserToolThreadWindow::ShortcutKeyMapsToEvent((BrowserToolThreadWindow *)((char *)this - 72), a2) )
    {
      return 1;
    }
    v5 = BrowserToolWindow::TranslateAcceleratorW(*((BrowserToolWindow **)this + 3), a2);
    v7 = v5;
    if ( v5 == -2147483638 )
    {
      v8 = *((_QWORD *)this + 10);
      v21 = 0;
      v9 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int16 *))(*(_QWORD *)v8 + 56LL);
      v10 = F12::GestureContainsKey((F12 *)a2, (const struct tagMSG *)0x10, v6);
      v12 = F12::GestureContainsKey((F12 *)a2, (const struct tagMSG *)0x11, v11);
      v14 = F12::GestureContainsKey((F12 *)a2, (const struct tagMSG *)0x12, v13);
      v7 = v9(v8, LODWORD(a2->wParam), v10 | (2 * v12) | (4 * (unsigned int)v14), &v21);
      if ( !v7 )
      {
        if ( !v21 )
        {
          v15 = SendMessageW(*((HWND *)this + 7), 0x37Fu, *((int *)this + 12), (LPARAM)a2) == 0;
LABEL_16:
          v7 = v15;
        }
        return v7 == 0;
      }
    }
    else
    {
      v16 = 1;
      if ( v5 != 1 )
        return v7 == 0;
      message = a2->message;
      if ( message == 256 )
      {
        if ( a2->wParam == 9 )
        {
          KeyState = GetKeyState(16);
          PostMessageW(*((HWND *)this + 7), 0x753u, *((int *)this + 12), (KeyState ^ 0x8000uLL) >> 15);
        }
        else
        {
          v16 = SendMessageW(*((HWND *)this + 7), 0x37Fu, *((int *)this + 12), (LPARAM)a2);
        }
        v15 = v16 == 0;
        goto LABEL_16;
      }
      if ( message - 260 > 3 )
        return v7 == 0;
      wParam = a2->wParam;
      if ( wParam != 40 )
      {
        PostMessageW(*((HWND *)this + 7), message, wParam, a2->lParam);
        return 1;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800087c0  mov     [rsp+arg_0], rbx
0x1800087c5  mov     [rsp+arg_10], rbp
0x1800087ca  push    rsi
0x1800087cb  push    rdi
0x1800087cc  push    r12
0x1800087ce  push    r14
0x1800087d0  push    r15
0x1800087d2  sub     rsp, 30h
0x1800087d6  xor     r12d, r12d
0x1800087d9  mov     rbp, rdx
0x1800087dc  mov     r15, rcx
0x1800087df  test    rdx, rdx
0x1800087e2  jz      loc_18000896F
0x1800087e8  cmp     [rcx+18h], r12
0x1800087ec  jz      loc_18000896F
0x1800087f2  mov     eax, [rdx+8]
0x1800087f5  mov     edi, 100h
0x1800087fa  sub     eax, edi
0x1800087fc  cmp     eax, 9
0x1800087ff  ja      loc_18000896F
0x180008805  mov     rcx, [rcx+38h]; hWnd
0x180008809  call    ?ProcessShortcutKeys@F12@@YA_NQEAUHWND__@@PEBUtagMSG@@@Z; F12::ProcessShortcutKeys(HWND__ * const,tagMSG const *)
0x18000880e  test    al, al
0x180008810  jnz     loc_180008968
0x180008816  mov     rdx, rbp; struct tagMSG *
0x180008819  lea     rcx, [r15-48h]; this
0x18000881d  call    ?ShortcutKeyMapsToEvent@BrowserToolThreadWindow@@AEAA_NPEAUtagMSG@@@Z; BrowserToolThreadWindow::ShortcutKeyMapsToEvent(tagMSG *)
0x180008822  test    al, al
0x180008824  jnz     loc_180008968
0x18000882a  mov     rcx, [r15+18h]; this
0x18000882e  mov     rdx, rbp; struct tagMSG *
0x180008831  call    ?TranslateAcceleratorW@BrowserToolWindow@@QEAAJPEAUtagMSG@@@Z; BrowserToolWindow::TranslateAcceleratorW(tagMSG *)
0x180008836  mov     ecx, eax
0x180008838  cmp     eax, 8000000Ah
0x18000883d  jnz     loc_1800088D3
0x180008843  mov     r14, [r15+50h]
0x180008847  lea     edx, [r12+10h]; struct tagMSG *
0x18000884c  mov     [rsp+58h+arg_8], r12w
0x180008852  mov     rcx, rbp; this
0x180008855  mov     rax, [r14]
0x180008858  mov     rsi, [rax+38h]
0x18000885c  call    ?GestureContainsKey@F12@@YA_NPEBUtagMSG@@_K@Z; F12::GestureContainsKey(tagMSG const *,unsigned __int64)
0x180008861  lea     edx, [r12+11h]; struct tagMSG *
0x180008866  movzx   edi, al
0x180008869  mov     rcx, rbp; this
0x18000886c  call    ?GestureContainsKey@F12@@YA_NPEBUtagMSG@@_K@Z; F12::GestureContainsKey(tagMSG const *,unsigned __int64)
0x180008871  lea     edx, [r12+12h]; struct tagMSG *
0x180008876  movzx   ebx, al
0x180008879  mov     rcx, rbp; this
0x18000887c  call    ?GestureContainsKey@F12@@YA_NPEBUtagMSG@@_K@Z; F12::GestureContainsKey(tagMSG const *,unsigned __int64)
0x180008881  movzx   r8d, al
0x180008885  lea     r9, [rsp+58h+arg_8]
0x18000888a  shl     r8d, 2
0x18000888e  mov     edx, ebx
0x180008890  add     edx, edx
0x180008892  mov     rcx, r14
0x180008895  or      r8d, edx
0x180008898  mov     rax, rsi
0x18000889b  mov     edx, [rbp+10h]
0x18000889e  or      r8d, edi
0x1800088a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088a6  mov     ecx, eax
0x1800088a8  test    eax, eax
0x1800088aa  jnz     loc_18000896F
0x1800088b0  cmp     [rsp+58h+arg_8], r12w
0x1800088b6  jnz     short loc_180008937
0x1800088b8  movsxd  r8, dword ptr [r15+30h]; wParam
0x1800088bc  mov     r9, rbp; lParam
0x1800088bf  mov     rcx, [r15+38h]; hWnd
0x1800088c3  mov     edx, 37Fh; Msg
0x1800088c8  call    cs:__imp_SendMessageW
0x1800088ce  test    rax, rax
0x1800088d1  jmp     short loc_180008931
0x1800088d3  mov     ebx, 1
0x1800088d8  cmp     eax, ebx
0x1800088da  jnz     short loc_180008937
0x1800088dc  mov     edx, [rbp+8]; Msg
0x1800088df  cmp     edx, edi
0x1800088e1  jnz     short loc_180008941
0x1800088e3  cmp     qword ptr [rbp+10h], 9
0x1800088e8  jnz     short loc_180008915
0x1800088ea  lea     ecx, [rbx+0Fh]; nVirtKey
0x1800088ed  call    cs:__imp_GetKeyState
0x1800088f3  movsxd  r8, dword ptr [r15+30h]; wParam
0x1800088f7  mov     edx, 753h; Msg
0x1800088fc  mov     rcx, [r15+38h]; hWnd
0x180008900  movzx   r9d, ax
0x180008904  btc     r9, 0Fh
0x180008909  shr     r9, 0Fh; lParam
0x18000890d  call    cs:__imp_PostMessageW
0x180008913  jmp     short loc_18000892E
0x180008915  movsxd  r8, dword ptr [r15+30h]; wParam
0x180008919  mov     r9, rbp; lParam
0x18000891c  mov     rcx, [r15+38h]; hWnd
0x180008920  mov     edx, 37Fh; Msg
0x180008925  call    cs:__imp_SendMessageW
0x18000892b  mov     rbx, rax
0x18000892e  test    rbx, rbx
0x180008931  mov     ecx, r12d
0x180008934  setz    cl
0x180008937  test    ecx, ecx
0x180008939  mov     eax, r12d
0x18000893c  setz    al
0x18000893f  jmp     short loc_180008971
0x180008941  lea     eax, [rdx-104h]
0x180008947  cmp     eax, 3
0x18000894a  ja      short loc_180008937
0x18000894c  mov     r8, [rbp+10h]; wParam
0x180008950  cmp     r8, 28h ; '('
0x180008954  jz      short loc_18000896F
0x180008956  mov     r9, [rbp+18h]; lParam
0x18000895a  mov     rcx, [r15+38h]; hWnd
0x18000895e  call    cs:__imp_PostMessageW
0x180008964  mov     eax, ebx
0x180008966  jmp     short loc_180008971
0x180008968  mov     eax, 1
0x18000896d  jmp     short loc_180008971
0x18000896f  xor     eax, eax
0x180008971  mov     rbx, [rsp+58h+arg_0]
0x180008976  mov     rbp, [rsp+58h+arg_10]
0x18000897b  add     rsp, 30h
0x18000897f  pop     r15
0x180008981  pop     r14
0x180008983  pop     r12
0x180008985  pop     rdi
0x180008986  pop     rsi
0x180008987  retn
```
