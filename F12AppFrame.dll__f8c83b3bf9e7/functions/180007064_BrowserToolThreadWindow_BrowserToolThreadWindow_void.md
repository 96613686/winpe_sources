# BrowserToolThreadWindow::BrowserToolThreadWindow(void)

- ea: `0x180007064`
- end: `0x18000713f`
- name: `??0BrowserToolThreadWindow@@QEAA@XZ`
- size: `219`
- prototype: `BrowserToolThreadWindow *__fastcall(BrowserToolThreadWindow *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005e70`

## callees

- `0x180003858`
- `0x180007064`
- `0x1800075d8`
- `0x180008efc`

## import_xrefs

- `USER32!DefWindowProcW` at `0x180007089`

## pseudocode

```c
BrowserToolThreadWindow *__fastcall BrowserToolThreadWindow::BrowserToolThreadWindow(BrowserToolThreadWindow *this)
{
  unsigned __int16 v3; // [rsp+38h] [rbp-40h]

  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_DWORD *)this + 14) = 0;
  *((_QWORD *)this + 8) = DefWindowProcW;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *(_QWORD *)this = &BrowserToolThreadWindow::`vftable'{for `ATL::CWindowImpl<BrowserToolThreadWindow,ATL::CWindow,ATL::CWinTraits<1442840576,0>>'};
  *((_QWORD *)this + 9) = &BrowserToolThreadWindow::`vftable'{for `WTL::CMessageFilter'};
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_DWORD *)this + 30) = -1;
  *((_QWORD *)this + 16) = 0;
  *((_BYTE *)this + 136) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  if ( !qword_18004B050 )
    qword_18004B050 = 0;
  v3 = ATL::_ATL_WNDCLASSINFOW::Register(
         &`ATL::CWindowImpl<BrowserToolThreadWindow,ATL::CWindow,ATL::CWinTraits<1442840576,0>>::GetWndClassInfo'::`2'::wc,
         (__int64 (**)(HWND, unsigned int, unsigned __int64, __int64))this + 8);
  if ( !ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<1442840576,0>>::Create(this, -3, 0, 0, 1442840576, 0, 0, v3) )
    ATL::AtlThrowImpl(-2147418113);
  return this;
}

```

## disassembly

```asm
0x180007064  mov     [rsp+arg_0], rcx
0x180007069  push    rbx
0x18000706a  push    rbp
0x18000706b  push    rsi
0x18000706c  push    rdi
0x18000706d  sub     rsp, 58h
0x180007071  mov     rsi, rcx
0x180007074  xor     ebp, ebp
0x180007076  mov     [rcx+8], rbp
0x18000707a  mov     [rcx+28h], rbp
0x18000707e  mov     [rcx+30h], rbp
0x180007082  mov     [rcx+38h], ebp
0x180007085  lea     rdx, [rcx+40h]; __int64 (**)(HWND, unsigned int, unsigned __int64, __int64)
0x180007089  mov     rax, cs:__imp_DefWindowProcW
0x180007090  mov     [rdx], rax
0x180007093  mov     [rcx+50h], rbp
0x180007097  mov     [rcx+58h], rbp
0x18000709b  lea     rax, ??_7BrowserToolThreadWindow@@6B?$CWindowImpl@VBrowserToolThreadWindow@@VCWindow@ATL@@V?$CWinTraits@$0FGAAAAAA@$0A@@3@@ATL@@@; const BrowserToolThreadWindow::`vftable'{for `ATL::CWindowImpl<BrowserToolThreadWindow,ATL::CWindow,ATL::CWinTraits<1442840576,0>>'}
0x1800070a2  mov     [rcx], rax
0x1800070a5  lea     rax, ??_7BrowserToolThreadWindow@@6BCMessageFilter@WTL@@@; const BrowserToolThreadWindow::`vftable'{for `WTL::CMessageFilter'}
0x1800070ac  mov     [rcx+48h], rax
0x1800070b0  mov     [rcx+60h], rbp
0x1800070b4  mov     [rcx+68h], rbp
0x1800070b8  mov     [rcx+70h], rbp
0x1800070bc  mov     dword ptr [rcx+78h], 0FFFFFFFFh
0x1800070c3  mov     [rcx+80h], rbp
0x1800070ca  mov     [rcx+88h], bpl
0x1800070d1  mov     [rcx+90h], rbp
0x1800070d8  mov     [rcx+98h], rbp
0x1800070df  cmp     cs:qword_18004B050, rbp
0x1800070e6  jnz     short loc_1800070EF
0x1800070e8  mov     cs:qword_18004B050, rbp
0x1800070ef  lea     rcx, ?wc@?1??GetWndClassInfo@?$CWindowImpl@VBrowserToolThreadWindow@@VCWindow@ATL@@V?$CWinTraits@$0FGAAAAAA@$0A@@3@@ATL@@SAAEAU_ATL_WNDCLASSINFOW@3@XZ@4U43@A; this
0x1800070f6  call    ?Register@_ATL_WNDCLASSINFOW@ATL@@QEAAGPEAP6A_JPEAUHWND__@@I_K_J@Z@Z; ATL::_ATL_WNDCLASSINFOW::Register(__int64 (**)(HWND__ *,uint,unsigned __int64,__int64))
0x1800070fb  mov     [rsp+78h+var_40], ax
0x180007100  mov     [rsp+78h+var_48], rbp
0x180007105  mov     [rsp+78h+var_50], ebp
0x180007109  mov     [rsp+78h+var_58], 56000000h
0x180007111  xor     r9d, r9d
0x180007114  mov     r8, rbp
0x180007117  lea     rdx, [r9-3]
0x18000711b  mov     rcx, rsi
0x18000711e  call    ?Create@?$CWindowImplBaseT@VCWindow@ATL@@V?$CWinTraits@$0FGAAAAAA@$0A@@2@@ATL@@QEAAPEAUHWND__@@PEAU3@V_U_RECT@2@PEBGKKV_U_MENUorID@2@GPEAX@Z; ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<1442840576,0>>::Create(HWND__ *,ATL::_U_RECT,ushort const *,ulong,ulong,ATL::_U_MENUorID,ushort,void *)
0x180007123  test    rax, rax
0x180007126  jz      short loc_180007134
0x180007128  mov     rax, rsi
0x18000712b  add     rsp, 58h
0x18000712f  pop     rdi
0x180007130  pop     rsi
0x180007131  pop     rbp
0x180007132  pop     rbx
0x180007133  retn
0x180007134  mov     ecx, 8000FFFFh; int
0x180007139  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
