# COleControl::OnPaint(CDC *)

- ea: `0x18000a210`
- end: `0x18000a3c9`
- name: `?OnPaint@COleControl@@IEAAXPEAVCDC@@@Z`
- size: `441`
- prototype: `void __fastcall(COleControl *__hidden this, struct CDC *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x18000a210`
- `0x18000a8e0`
- `0x18000e1a0`
- `0x180010c40`
- `0x180012eb0`
- `0x1800d1fe0`
- `0x1800d7010`

## import_xrefs

- `USER32!GetWindowRect` at `0x18000a273`
- `USER32!GetWindowRect` at `0x18000a273`
- `USER32!OffsetRect` at `0x18000a28a`
- `USER32!OffsetRect` at `0x18000a28a`
- `USER32!CopyRect` at `0x18000a33a`
- `USER32!CopyRect` at `0x18000a33a`
- `USER32!EndPaint` at `0x18000a36b`
- `USER32!EndPaint` at `0x18000a36b`
- `USER32!InflateRect` at `0x18000a2b6`
- `USER32!InflateRect` at `0x18000a2b6`
- `USER32!ValidateRect` at `0x18000a24a`
- `USER32!ValidateRect` at `0x18000a24a`
- `GDI32!DeleteDC` at `0x18000a399`
- `GDI32!DeleteDC` at `0x18000a399`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall COleControl::OnPaint(COleControl *this, struct CDC *a2)
{
  struct AFX_MODULE_THREAD_STATE *ModuleThreadState; // rax
  __int64 v5; // rax
  unsigned int v6; // ebx
  void (__fastcall *v7)(COleControl *, _QWORD *, _BYTE *, struct tagRECT *); // rbx
  HDC v8; // rax
  _BYTE v9[16]; // [rsp+30h] [rbp-59h] BYREF
  struct tagRECT rcDst; // [rsp+40h] [rbp-49h] BYREF
  _QWORD v11[5]; // [rsp+50h] [rbp-39h] BYREF
  PAINTSTRUCT Paint; // [rsp+78h] [rbp-11h] BYREF

  if ( (*((_DWORD *)this + 62) & 0x800000) != 0 )
  {
    ValidateRect(*((HWND *)this + 8), 0);
    *((_DWORD *)this + 62) &= ~0x800000u;
  }
  else
  {
    ModuleThreadState = AfxGetModuleThreadState();
    ++*((_DWORD *)ModuleThreadState + 8);
    GetWindowRect(*((HWND *)this + 8), (LPRECT)((char *)this + 200));
    OffsetRect((LPRECT)((char *)this + 200), -*((_DWORD *)this + 50), -*((_DWORD *)this + 51));
    if ( (*((_DWORD *)this + 62) & 0x2000) == 0 )
    {
      v5 = *((_QWORD *)this + 22);
      if ( v5 )
        InflateRect((LPRECT)((char *)this + 200), 1 - *(_DWORD *)(v5 + 36), 1 - *(_DWORD *)(v5 + 36));
    }
    (*(void (__fastcall **)(COleControl *, _BYTE *))(*(_QWORD *)this + 384LL))(this, v9);
    if ( a2 )
    {
      v6 = (*(__int64 (__fastcall **)(struct CDC *))(*(_QWORD *)a2 + 72LL))(a2);
      (*(void (__fastcall **)(COleControl *, struct CDC *, _BYTE *, _BYTE *))(*(_QWORD *)this + 408LL))(
        this,
        a2,
        v9,
        v9);
      (*(void (__fastcall **)(struct CDC *, _QWORD))(*(_QWORD *)a2 + 80LL))(a2, v6);
    }
    else
    {
      CPaintDC::CPaintDC((CPaintDC *)v11, this);
      v7 = *(void (__fastcall **)(COleControl *, _QWORD *, _BYTE *, struct tagRECT *))(*(_QWORD *)this + 408LL);
      CopyRect(&rcDst, &Paint.rcPaint);
      v7(this, v11, v9, &rcDst);
      v11[0] = &CPaintDC::`vftable';
      EndPaint((HWND)v11[4], &Paint);
      CDC::Detach((CDC *)v11);
      v11[0] = &CDC::`vftable';
      if ( v11[1] )
      {
        v8 = CDC::Detach((CDC *)v11);
        DeleteDC(v8);
      }
    }
    AfxUnlockTempMaps(1);
  }
}

```

## disassembly

```asm
0x18000a210  mov     [rsp-8+arg_10], rbx
0x18000a215  push    rbp
0x18000a216  push    rsi
0x18000a217  push    rdi
0x18000a218  lea     rbp, [rsp-47h]
0x18000a21d  sub     rsp, 0D0h
0x18000a224  mov     rax, cs:__security_cookie
0x18000a22b  xor     rax, rsp
0x18000a22e  mov     [rbp+57h+var_20], rax
0x18000a232  mov     rsi, rdx
0x18000a235  mov     rdi, rcx
0x18000a238  test    dword ptr [rcx+0F8h], 800000h
0x18000a242  jz      short loc_18000A25D
0x18000a244  xor     edx, edx; lpRect
0x18000a246  mov     rcx, [rcx+40h]; hWnd
0x18000a24a  call    cs:__imp_ValidateRect
0x18000a250  btr     dword ptr [rdi+0F8h], 17h
0x18000a258  jmp     loc_18000A3AA
0x18000a25d  call    ?AfxGetModuleThreadState@@YAPEAVAFX_MODULE_THREAD_STATE@@XZ; AfxGetModuleThreadState(void)
0x18000a262  inc     dword ptr [rax+20h]
0x18000a265  lea     rbx, [rdi+0C8h]
0x18000a26c  mov     rdx, rbx; lpRect
0x18000a26f  mov     rcx, [rdi+40h]; hWnd
0x18000a273  call    cs:__imp_GetWindowRect
0x18000a279  mov     r8d, [rdi+0CCh]
0x18000a280  neg     r8d; dy
0x18000a283  mov     edx, [rbx]
0x18000a285  neg     edx; dx
0x18000a287  mov     rcx, rbx; lprc
0x18000a28a  call    cs:__imp_OffsetRect
0x18000a290  test    dword ptr [rdi+0F8h], 2000h
0x18000a29a  jnz     short loc_18000A2BC
0x18000a29c  mov     rax, [rdi+0B0h]
0x18000a2a3  test    rax, rax
0x18000a2a6  jz      short loc_18000A2BC
0x18000a2a8  mov     edx, 1
0x18000a2ad  sub     edx, [rax+24h]; dx
0x18000a2b0  mov     r8d, edx; dy
0x18000a2b3  mov     rcx, rbx; lprc
0x18000a2b6  call    cs:__imp_InflateRect
0x18000a2bc  mov     rax, [rdi]
0x18000a2bf  lea     rdx, [rbp+57h+var_B0]
0x18000a2c3  mov     rcx, rdi
0x18000a2c6  mov     rax, [rax+180h]
0x18000a2cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2d2  test    rsi, rsi
0x18000a2d5  jz      short loc_18000A31B
0x18000a2d7  mov     rax, [rsi]
0x18000a2da  mov     rcx, rsi
0x18000a2dd  mov     rax, [rax+48h]
0x18000a2e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2e6  mov     ebx, eax
0x18000a2e8  mov     rdx, [rdi]
0x18000a2eb  mov     rax, [rdx+198h]
0x18000a2f2  lea     r9, [rbp+57h+var_B0]
0x18000a2f6  lea     r8, [rbp+57h+var_B0]
0x18000a2fa  mov     rdx, rsi
0x18000a2fd  mov     rcx, rdi
0x18000a300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a305  mov     rdx, [rsi]
0x18000a308  mov     rax, [rdx+50h]
0x18000a30c  mov     edx, ebx
0x18000a30e  mov     rcx, rsi
0x18000a311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a316  jmp     loc_18000A3A0
0x18000a31b  mov     rdx, rdi; struct CWnd *
0x18000a31e  lea     rcx, [rbp+57h+var_90]; this
0x18000a322  call    ??0CPaintDC@@QEAA@PEAVCWnd@@@Z; CPaintDC::CPaintDC(CWnd *)
0x18000a327  nop
0x18000a328  mov     rax, [rdi]
0x18000a32b  mov     rbx, [rax+198h]
0x18000a332  lea     rdx, [rbp+57h+Paint.rcPaint]; lprcSrc
0x18000a336  lea     rcx, [rbp+57h+rcDst]; lprcDst
0x18000a33a  call    cs:__imp_CopyRect
0x18000a340  lea     r9, [rbp+57h+rcDst]
0x18000a344  lea     r8, [rbp+57h+var_B0]
0x18000a348  lea     rdx, [rbp+57h+var_90]
0x18000a34c  mov     rcx, rdi
0x18000a34f  mov     rax, rbx
0x18000a352  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a357  nop
0x18000a358  lea     rax, ??_7CPaintDC@@6B@; const CPaintDC::`vftable'
0x18000a35f  mov     [rbp+57h+var_90], rax
0x18000a363  lea     rdx, [rbp+57h+Paint]; lpPaint
0x18000a367  mov     rcx, [rbp+57h+hWnd]; hWnd
0x18000a36b  call    cs:__imp_EndPaint
0x18000a371  lea     rcx, [rbp+57h+var_90]; this
0x18000a375  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x18000a37a  nop
0x18000a37b  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x18000a382  mov     [rbp+57h+var_90], rax
0x18000a386  cmp     [rbp+57h+var_88], 0
0x18000a38b  jz      short loc_18000A3A0
0x18000a38d  lea     rcx, [rbp+57h+var_90]; this
0x18000a391  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x18000a396  mov     rcx, rax; hdc
0x18000a399  call    cs:__imp_DeleteDC
0x18000a39f  nop
0x18000a3a0  mov     ecx, 1; int
0x18000a3a5  call    ?AfxUnlockTempMaps@@YAHH@Z; AfxUnlockTempMaps(int)
0x18000a3aa  mov     rcx, [rbp+57h+var_20]
0x18000a3ae  xor     rcx, rsp; StackCookie
0x18000a3b1  call    __security_check_cookie
0x18000a3b6  mov     rbx, [rsp+0E0h+arg_10]
0x18000a3be  add     rsp, 0D0h
0x18000a3c5  pop     rdi
0x18000a3c6  pop     rsi
0x18000a3c7  pop     rbp
0x18000a3c8  retn
```
