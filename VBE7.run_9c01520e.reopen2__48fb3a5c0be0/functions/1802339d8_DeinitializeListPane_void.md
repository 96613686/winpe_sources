# DeinitializeListPane(void)

- ea: `0x1802339d8`
- end: `0x180233b19`
- name: `?DeinitializeListPane@@YAXXZ`
- size: `321`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1801a9a40`
- `0x1801aa0e8`

## callees

- `0x1802339d8`

## import_xrefs

- `GDI32!DeleteObject` at `0x1802339f2`
- `GDI32!DeleteObject` at `0x180233a14`
- `GDI32!DeleteObject` at `0x180233a36`
- `GDI32!DeleteObject` at `0x180233a58`
- `GDI32!DeleteObject` at `0x180233a7a`
- `GDI32!DeleteObject` at `0x180233a9c`
- `GDI32!DeleteObject` at `0x180233abe`
- `GDI32!DeleteObject` at `0x180233ae0`
- `GDI32!DeleteObject` at `0x180233b02`
- `GDI32!DeleteObject` at `0x1802339f2`
- `GDI32!DeleteObject` at `0x180233a14`
- `GDI32!DeleteObject` at `0x180233a36`
- `GDI32!DeleteObject` at `0x180233a58`
- `GDI32!DeleteObject` at `0x180233a7a`
- `GDI32!DeleteObject` at `0x180233a9c`
- `GDI32!DeleteObject` at `0x180233abe`
- `GDI32!DeleteObject` at `0x180233ae0`
- `GDI32!DeleteObject` at `0x180233b02`

## pseudocode

```c
void DeinitializeListPane(void)
{
  if ( g_hfontLPANETitle )
  {
    DeleteObject(g_hfontLPANETitle);
    g_hfontLPANETitle = 0;
  }
  if ( g_hfontLPANEItem )
  {
    DeleteObject(g_hfontLPANEItem);
    g_hfontLPANEItem = 0;
  }
  if ( g_hfontLPANENoEditItem )
  {
    DeleteObject(g_hfontLPANENoEditItem);
    g_hfontLPANENoEditItem = 0;
  }
  if ( g_hbmpWatchExpr )
  {
    DeleteObject(g_hbmpWatchExpr);
    g_hbmpWatchExpr = 0;
  }
  if ( g_hbmpWatchBreak )
  {
    DeleteObject(g_hbmpWatchBreak);
    g_hbmpWatchBreak = 0;
  }
  if ( g_hbmpWatchChange )
  {
    DeleteObject(g_hbmpWatchChange);
    g_hbmpWatchChange = 0;
  }
  if ( g_hbmpLPaneExpand )
  {
    DeleteObject(g_hbmpLPaneExpand);
    g_hbmpLPaneExpand = 0;
  }
  if ( g_hbmpLPaneCollapse )
  {
    DeleteObject(g_hbmpLPaneCollapse);
    g_hbmpLPaneCollapse = 0;
  }
  if ( g_hbmpLPaneUnevaluated )
  {
    DeleteObject(g_hbmpLPaneUnevaluated);
    g_hbmpLPaneUnevaluated = 0;
  }
}

```

## disassembly

```asm
0x1802339d8  push    rbp
0x1802339da  mov     rbp, rsp
0x1802339dd  sub     rsp, 20h
0x1802339e1  cmp     cs:?g_hfontLPANETitle@@3PEAUHFONT__@@EA, 0; HFONT__ * g_hfontLPANETitle
0x1802339e9  jz      short loc_180233A03
0x1802339eb  mov     rcx, cs:?g_hfontLPANETitle@@3PEAUHFONT__@@EA; ho
0x1802339f2  call    cs:__imp_DeleteObject
0x1802339f8  mov     cs:?g_hfontLPANETitle@@3PEAUHFONT__@@EA, 0; HFONT__ * g_hfontLPANETitle
0x180233a03  cmp     cs:?g_hfontLPANEItem@@3PEAUHFONT__@@EA, 0; HFONT__ * g_hfontLPANEItem
0x180233a0b  jz      short loc_180233A25
0x180233a0d  mov     rcx, cs:?g_hfontLPANEItem@@3PEAUHFONT__@@EA; ho
0x180233a14  call    cs:__imp_DeleteObject
0x180233a1a  mov     cs:?g_hfontLPANEItem@@3PEAUHFONT__@@EA, 0; HFONT__ * g_hfontLPANEItem
0x180233a25  cmp     cs:?g_hfontLPANENoEditItem@@3PEAUHFONT__@@EA, 0; HFONT__ * g_hfontLPANENoEditItem
0x180233a2d  jz      short loc_180233A47
0x180233a2f  mov     rcx, cs:?g_hfontLPANENoEditItem@@3PEAUHFONT__@@EA; ho
0x180233a36  call    cs:__imp_DeleteObject
0x180233a3c  mov     cs:?g_hfontLPANENoEditItem@@3PEAUHFONT__@@EA, 0; HFONT__ * g_hfontLPANENoEditItem
0x180233a47  cmp     cs:?g_hbmpWatchExpr@@3PEAUHBITMAP__@@EA, 0; HBITMAP__ * g_hbmpWatchExpr
0x180233a4f  jz      short loc_180233A69
0x180233a51  mov     rcx, cs:?g_hbmpWatchExpr@@3PEAUHBITMAP__@@EA; ho
0x180233a58  call    cs:__imp_DeleteObject
0x180233a5e  mov     cs:?g_hbmpWatchExpr@@3PEAUHBITMAP__@@EA, 0; HBITMAP__ * g_hbmpWatchExpr
0x180233a69  cmp     cs:?g_hbmpWatchBreak@@3PEAUHBITMAP__@@EA, 0; HBITMAP__ * g_hbmpWatchBreak
0x180233a71  jz      short loc_180233A8B
0x180233a73  mov     rcx, cs:?g_hbmpWatchBreak@@3PEAUHBITMAP__@@EA; ho
0x180233a7a  call    cs:__imp_DeleteObject
0x180233a80  mov     cs:?g_hbmpWatchBreak@@3PEAUHBITMAP__@@EA, 0; HBITMAP__ * g_hbmpWatchBreak
0x180233a8b  cmp     cs:?g_hbmpWatchChange@@3PEAUHBITMAP__@@EA, 0; HBITMAP__ * g_hbmpWatchChange
0x180233a93  jz      short loc_180233AAD
0x180233a95  mov     rcx, cs:?g_hbmpWatchChange@@3PEAUHBITMAP__@@EA; ho
0x180233a9c  call    cs:__imp_DeleteObject
0x180233aa2  mov     cs:?g_hbmpWatchChange@@3PEAUHBITMAP__@@EA, 0; HBITMAP__ * g_hbmpWatchChange
0x180233aad  cmp     cs:?g_hbmpLPaneExpand@@3PEAUHBITMAP__@@EA, 0; HBITMAP__ * g_hbmpLPaneExpand
0x180233ab5  jz      short loc_180233ACF
0x180233ab7  mov     rcx, cs:?g_hbmpLPaneExpand@@3PEAUHBITMAP__@@EA; ho
0x180233abe  call    cs:__imp_DeleteObject
0x180233ac4  mov     cs:?g_hbmpLPaneExpand@@3PEAUHBITMAP__@@EA, 0; HBITMAP__ * g_hbmpLPaneExpand
0x180233acf  cmp     cs:?g_hbmpLPaneCollapse@@3PEAUHBITMAP__@@EA, 0; HBITMAP__ * g_hbmpLPaneCollapse
0x180233ad7  jz      short loc_180233AF1
0x180233ad9  mov     rcx, cs:?g_hbmpLPaneCollapse@@3PEAUHBITMAP__@@EA; ho
0x180233ae0  call    cs:__imp_DeleteObject
0x180233ae6  mov     cs:?g_hbmpLPaneCollapse@@3PEAUHBITMAP__@@EA, 0; HBITMAP__ * g_hbmpLPaneCollapse
0x180233af1  cmp     cs:?g_hbmpLPaneUnevaluated@@3PEAUHBITMAP__@@EA, 0; HBITMAP__ * g_hbmpLPaneUnevaluated
0x180233af9  jz      short loc_180233B13
0x180233afb  mov     rcx, cs:?g_hbmpLPaneUnevaluated@@3PEAUHBITMAP__@@EA; ho
0x180233b02  call    cs:__imp_DeleteObject
0x180233b08  mov     cs:?g_hbmpLPaneUnevaluated@@3PEAUHBITMAP__@@EA, 0; HBITMAP__ * g_hbmpLPaneUnevaluated
0x180233b13  add     rsp, 20h
0x180233b17  pop     rbp
0x180233b18  retn
```
