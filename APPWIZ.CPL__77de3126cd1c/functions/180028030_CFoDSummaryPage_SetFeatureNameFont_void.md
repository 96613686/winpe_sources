# CFoDSummaryPage::SetFeatureNameFont(void)

- ea: `0x180028030`
- end: `0x180028122`
- name: `?SetFeatureNameFont@CFoDSummaryPage@@AEAAXXZ`
- size: `242`
- prototype: `void __fastcall(CFoDSummaryPage *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800269a4`

## callees

- `0x1800582a2`
- `0x1800582e0`

## import_xrefs

- `KERNEL32!MulDiv` at `0x1800280b2`
- `KERNEL32!MulDiv` at `0x1800280b2`
- `USER32!ReleaseDC` at `0x1800280fb`
- `USER32!ReleaseDC` at `0x1800280fb`
- `USER32!GetDC` at `0x180028066`
- `USER32!GetDC` at `0x180028066`
- `USER32!SendMessageW` at `0x180028080`
- `USER32!SendMessageW` at `0x1800280e4`
- `USER32!SendMessageW` at `0x180028080`
- `USER32!SendMessageW` at `0x1800280e4`
- `GDI32!GetDeviceCaps` at `0x1800280a1`
- `GDI32!GetDeviceCaps` at `0x1800280a1`
- `GDI32!CreateFontIndirectW` at `0x1800280c3`
- `GDI32!CreateFontIndirectW` at `0x1800280c3`
- `GDI32!GetObjectW` at `0x180028093`
- `GDI32!GetObjectW` at `0x180028093`

## pseudocode

```c
void __fastcall CFoDSummaryPage::SetFeatureNameFont(HWND *this)
{
  HDC DC; // rbx
  void *v3; // rax
  int DeviceCaps; // eax
  HFONT v5; // rax
  LOGFONTW pv; // [rsp+20h] [rbp-78h] BYREF

  memset_0(&pv, 0, sizeof(pv));
  DC = GetDC(this[1]);
  v3 = (void *)SendMessageW(this[24], 0x31u, 0, 0);
  GetObjectW(v3, 92, &pv);
  DeviceCaps = GetDeviceCaps(DC, 90);
  pv.lfHeight = -MulDiv(15, DeviceCaps, 96);
  v5 = CreateFontIndirectW(&pv);
  this[27] = (HWND)v5;
  SendMessageW(this[24], 0x30u, (WPARAM)v5, 1);
  *((_DWORD *)this + 56) = 1;
  ReleaseDC(this[1], DC);
}

```

## disassembly

```asm
0x180028030  mov     [rsp+arg_8], rbx
0x180028035  push    rdi
0x180028036  sub     rsp, 90h
0x18002803d  mov     rax, cs:__security_cookie
0x180028044  xor     rax, rsp
0x180028047  mov     [rsp+98h+var_18], rax
0x18002804f  xor     edx, edx; Val
0x180028051  mov     rdi, rcx
0x180028054  lea     rcx, [rsp+98h+pv]; void *
0x180028059  lea     r8d, [rdx+5Ch]; Size
0x18002805d  call    memset_0
0x180028062  mov     rcx, [rdi+8]; hWnd
0x180028066  call    cs:__imp_GetDC
0x18002806c  mov     rcx, [rdi+0C0h]; hWnd
0x180028073  xor     r9d, r9d; lParam
0x180028076  xor     r8d, r8d; wParam
0x180028079  mov     rbx, rax
0x18002807c  lea     edx, [r9+31h]; Msg
0x180028080  call    cs:__imp_SendMessageW
0x180028086  lea     r8, [rsp+98h+pv]; pv
0x18002808b  mov     edx, 5Ch ; '\'; c
0x180028090  mov     rcx, rax; h
0x180028093  call    cs:__imp_GetObjectW
0x180028099  mov     edx, 5Ah ; 'Z'; index
0x18002809e  mov     rcx, rbx; hdc
0x1800280a1  call    cs:__imp_GetDeviceCaps
0x1800280a7  mov     ecx, 0Fh; nNumber
0x1800280ac  mov     edx, eax; nNumerator
0x1800280ae  lea     r8d, [rcx+51h]; nDenominator
0x1800280b2  call    cs:__imp_MulDiv
0x1800280b8  neg     eax
0x1800280ba  lea     rcx, [rsp+98h+pv]; lplf
0x1800280bf  mov     [rsp+98h+pv.lfHeight], eax
0x1800280c3  call    cs:__imp_CreateFontIndirectW
0x1800280c9  mov     r9d, 1; lParam
0x1800280cf  mov     [rdi+0D8h], rax
0x1800280d6  mov     rcx, [rdi+0C0h]; hWnd
0x1800280dd  mov     r8, rax; wParam
0x1800280e0  lea     edx, [r9+2Fh]; Msg
0x1800280e4  call    cs:__imp_SendMessageW
0x1800280ea  mov     dword ptr [rdi+0E0h], 1
0x1800280f4  mov     rdx, rbx; hDC
0x1800280f7  mov     rcx, [rdi+8]; hWnd
0x1800280fb  call    cs:__imp_ReleaseDC
0x180028101  mov     rcx, [rsp+98h+var_18]
0x180028109  xor     rcx, rsp; StackCookie
0x18002810c  call    __security_check_cookie
0x180028111  mov     rbx, [rsp+98h+arg_8]
0x180028119  add     rsp, 90h
0x180028120  pop     rdi
0x180028121  retn
```
