# GdipUtilPrivate::DrawDib(HDC__ *,HBITMAP__ *,tagRECT const &)

- ea: `0x180026d44`
- end: `0x180026ddb`
- name: `?DrawDib@GdipUtilPrivate@@YAXPEAUHDC__@@PEAUHBITMAP__@@AEBUtagRECT@@@Z`
- size: `151`
- prototype: `void __fastcall(HDC hdc, HDC h, HBITMAP, const struct tagRECT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180026370`

## callees

- `0x180026d44`
- `0x180039508`

## import_xrefs

- `GDI32!SelectObject` at `0x180026d72`
- `GDI32!SelectObject` at `0x180026dc3`
- `GDI32!SelectObject` at `0x180026d72`
- `GDI32!SelectObject` at `0x180026dc3`
- `GDI32!CreateCompatibleDC` at `0x180026d56`
- `GDI32!CreateCompatibleDC` at `0x180026d56`
- `GDI32!BitBlt` at `0x180026db7`
- `GDI32!BitBlt` at `0x180026db7`
- `GDI32!DeleteDC` at `0x180026dcc`
- `GDI32!DeleteDC` at `0x180026dcc`

## pseudocode

```c
void __fastcall GdipUtilPrivate::DrawDib(HDC hdc, HDC h, int *a3, const struct tagRECT *a4)
{
  HDC CompatibleDC; // rax
  HDC v8; // rdx
  HDC hdcSrc; // rbx
  HGDIOBJ v10; // rsi

  CompatibleDC = CreateCompatibleDC(hdc);
  hdcSrc = CompatibleDC;
  if ( CompatibleDC )
  {
    GdipUtilPrivate::TurnOffRtl(CompatibleDC, v8);
    v10 = SelectObject(hdcSrc, h);
    if ( v10 )
    {
      BitBlt(hdc, *a3, a3[1], a3[2] - *a3, a3[3] - a3[1], hdcSrc, 0, 0, 0xCC0020u);
      SelectObject(hdcSrc, v10);
    }
    DeleteDC(hdcSrc);
  }
}

```

## disassembly

```asm
0x180026d44  push    rbx
0x180026d46  push    rbp
0x180026d47  push    rsi
0x180026d48  push    rdi
0x180026d49  sub     rsp, 58h
0x180026d4d  mov     rdi, r8
0x180026d50  mov     rsi, rdx
0x180026d53  mov     rbp, rcx
0x180026d56  call    cs:__imp_CreateCompatibleDC
0x180026d5c  mov     rbx, rax
0x180026d5f  test    rax, rax
0x180026d62  jz      short loc_180026DD2
0x180026d64  mov     rcx, rax; hdc
0x180026d67  call    ?TurnOffRtl@GdipUtilPrivate@@YAXPEAUHDC__@@@Z; GdipUtilPrivate::TurnOffRtl(HDC__ *)
0x180026d6c  mov     rdx, rsi; h
0x180026d6f  mov     rcx, rbx; hdc
0x180026d72  call    cs:__imp_SelectObject
0x180026d78  mov     rsi, rax
0x180026d7b  test    rax, rax
0x180026d7e  jz      short loc_180026DC9
0x180026d80  mov     ecx, [rdi+0Ch]
0x180026d83  mov     r8d, [rdi+4]; y
0x180026d87  sub     ecx, r8d
0x180026d8a  mov     r9d, [rdi+8]
0x180026d8e  sub     r9d, [rdi]; cx
0x180026d91  mov     edx, [rdi]; x
0x180026d93  mov     [rsp+78h+rop], 0CC0020h; rop
0x180026d9b  mov     [rsp+78h+y1], 0; y1
0x180026da3  mov     [rsp+78h+x1], 0; x1
0x180026dab  mov     [rsp+78h+hdcSrc], rbx; hdcSrc
0x180026db0  mov     [rsp+78h+cy], ecx; cy
0x180026db4  mov     rcx, rbp; hdc
0x180026db7  call    cs:__imp_BitBlt
0x180026dbd  mov     rdx, rsi; h
0x180026dc0  mov     rcx, rbx; hdc
0x180026dc3  call    cs:__imp_SelectObject
0x180026dc9  mov     rcx, rbx; hdc
0x180026dcc  call    cs:__imp_DeleteDC
0x180026dd2  add     rsp, 58h
0x180026dd6  pop     rdi
0x180026dd7  pop     rsi
0x180026dd8  pop     rbp
0x180026dd9  pop     rbx
0x180026dda  retn
```
