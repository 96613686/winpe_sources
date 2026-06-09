# CTouchSelectionHandle::UpdateLayeredWindow(tagPOINT *,int)

- ea: `0x1801ff9b8`
- end: `0x1801ffac6`
- name: `?UpdateLayeredWindow@CTouchSelectionHandle@@IEAAXPEAUtagPOINT@@H@Z`
- size: `270`
- prototype: `void __fastcall(CTouchSelectionHandle *__hidden this, POINT *pptDst, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1801fefb8`
- `0x1801ffacc`
- `0x1801ffbe8`

## callees

- `0x1801fb7e0`
- `0x1801ff9b8`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-1!UpdateLayeredWindow` at `0x1801ffa8a`
- `ext-ms-win-ntuser-window-l1-1-1!UpdateLayeredWindow` at `0x1801ffa8a`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x1801ffaac`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x1801ffaac`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x1801ffa0e`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x1801ffa0e`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801ffa26`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801ffaa3`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801ffa26`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801ffaa3`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!GetDC` at `0x1801ffa02`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!GetDC` at `0x1801ffa02`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!ReleaseDC` at `0x1801ffa97`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!ReleaseDC` at `0x1801ffa97`

## pseudocode

```c
void __fastcall CTouchSelectionHandle::UpdateLayeredWindow(CTouchSelectionHandle *this, POINT *pptDst, BYTE a3)
{
  __int64 v3; // r10
  int i; // r9d
  __int64 v8; // r8
  HDC DC; // rdi
  HDC hdcSrc; // rsi
  HGDIOBJ v11; // rax
  HWND v12; // rcx
  void *v13; // rbx
  POINT pptSrc; // [rsp+80h] [rbp+8h] BYREF
  BLENDFUNCTION pblend; // [rsp+90h] [rbp+18h] BYREF
  SIZE psize; // [rsp+98h] [rbp+20h] BYREF

  v3 = *((_QWORD *)this + 16);
  pptSrc = 0;
  for ( i = 0; i != 8; i += 4 )
  {
    v8 = i;
    *(LONG *)((char *)&psize.cx + v8) = *(_DWORD *)(v3 + 8);
  }
  DC = GetDC(*((HWND *)this + 9));
  hdcSrc = CreateCompatibleDC(DC);
  CTouchSelectionHandle::EnsureGripperBitmap(this);
  v11 = SelectObject(hdcSrc, *((HGDIOBJ *)this + 10));
  v12 = (HWND)*((_QWORD *)this + 9);
  v13 = v11;
  *(_WORD *)&pblend.BlendOp = 0;
  pblend.SourceConstantAlpha = a3;
  pblend.AlphaFormat = 1;
  UpdateLayeredWindow(v12, DC, pptDst, &psize, hdcSrc, &pptSrc, 0xFF00u, &pblend, 2u);
  ReleaseDC(*((HWND *)this + 9), DC);
  SelectObject(hdcSrc, v13);
  DeleteDC(hdcSrc);
}

```

## disassembly

```asm
0x1801ff9b8  mov     rax, rsp
0x1801ff9bb  mov     [rax+10h], rbx
0x1801ff9bf  push    rbp
0x1801ff9c0  push    rsi
0x1801ff9c1  push    rdi
0x1801ff9c2  push    r14
0x1801ff9c4  push    r15
0x1801ff9c6  sub     rsp, 50h
0x1801ff9ca  mov     r10, [rcx+80h]
0x1801ff9d1  mov     r14d, r8d
0x1801ff9d4  mov     r15, rdx
0x1801ff9d7  mov     qword ptr [rax+8], 0
0x1801ff9df  mov     rbp, rcx
0x1801ff9e2  xor     r9d, r9d
0x1801ff9e5  mov     eax, [r10+8]
0x1801ff9e9  movsxd  r8, r9d
0x1801ff9ec  add     r9d, 4
0x1801ff9f0  mov     [rsp+r8+78h+psize.cx], eax
0x1801ff9f8  cmp     r9d, 8
0x1801ff9fc  jnz     short loc_1801FF9E5
0x1801ff9fe  mov     rcx, [rcx+48h]; hWnd
0x1801ffa02  call    cs:__imp_GetDC
0x1801ffa08  mov     rcx, rax; hdc
0x1801ffa0b  mov     rdi, rax
0x1801ffa0e  call    cs:__imp_CreateCompatibleDC
0x1801ffa14  mov     rcx, rbp; this
0x1801ffa17  mov     rsi, rax
0x1801ffa1a  call    ?EnsureGripperBitmap@CTouchSelectionHandle@@IEAAXXZ; CTouchSelectionHandle::EnsureGripperBitmap(void)
0x1801ffa1f  mov     rdx, [rbp+50h]; h
0x1801ffa23  mov     rcx, rsi; hdc
0x1801ffa26  call    cs:__imp_SelectObject
0x1801ffa2c  mov     rcx, [rbp+48h]; hWnd
0x1801ffa30  lea     r9, [rsp+78h+psize]; psize
0x1801ffa38  mov     [rsp+78h+dwFlags], 2; dwFlags
0x1801ffa40  mov     rbx, rax
0x1801ffa43  lea     rax, [rsp+78h+arg_10]
0x1801ffa4b  mov     word ptr [rsp+78h+arg_10.BlendOp], 0
0x1801ffa55  mov     [rsp+78h+pblend], rax; pblend
0x1801ffa5a  mov     r8, r15; pptDst
0x1801ffa5d  lea     rax, [rsp+78h+arg_0]
0x1801ffa65  mov     [rsp+78h+crKey], 0FF00h; crKey
0x1801ffa6d  mov     [rsp+78h+pptSrc], rax; pptSrc
0x1801ffa72  mov     rdx, rdi; hdcDst
0x1801ffa75  mov     [rsp+78h+hdcSrc], rsi; hdcSrc
0x1801ffa7a  mov     [rsp+78h+arg_10.SourceConstantAlpha], r14b
0x1801ffa82  mov     [rsp+78h+arg_10.AlphaFormat], 1
0x1801ffa8a  call    cs:__imp_UpdateLayeredWindow
0x1801ffa90  mov     rcx, [rbp+48h]; hWnd
0x1801ffa94  mov     rdx, rdi; hDC
0x1801ffa97  call    cs:__imp_ReleaseDC
0x1801ffa9d  mov     rdx, rbx; h
0x1801ffaa0  mov     rcx, rsi; hdc
0x1801ffaa3  call    cs:__imp_SelectObject
0x1801ffaa9  mov     rcx, rsi; hdc
0x1801ffaac  call    cs:__imp_DeleteDC
0x1801ffab2  mov     rbx, [rsp+78h+arg_8]
0x1801ffaba  add     rsp, 50h
0x1801ffabe  pop     r15
0x1801ffac0  pop     r14
0x1801ffac2  pop     rdi
0x1801ffac3  pop     rsi
0x1801ffac4  pop     rbp
0x1801ffac5  retn
```
