# CFoDDetailedResultsPage::OnInitDialog(uint,unsigned __int64,__int64)

- ea: `0x180026778`
- end: `0x1800268ca`
- name: `?OnInitDialog@CFoDDetailedResultsPage@@QEAA_JI_K_J@Z`
- size: `338`
- prototype: `__int64 __fastcall(CFoDDetailedResultsPage *__hidden this, unsigned int, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180027760`

## callees

- `0x180025d10`
- `0x1800582a2`
- `0x1800582e0`

## import_xrefs

- `KERNEL32!MulDiv` at `0x180026818`
- `KERNEL32!MulDiv` at `0x180026818`
- `USER32!ReleaseDC` at `0x18002689a`
- `USER32!ReleaseDC` at `0x18002689a`
- `USER32!GetDC` at `0x1800267b6`
- `USER32!GetDC` at `0x1800267b6`
- `USER32!SendMessageW` at `0x1800267e6`
- `USER32!SendMessageW` at `0x18002684a`
- `USER32!SendMessageW` at `0x1800267e6`
- `USER32!SendMessageW` at `0x18002684a`
- `GDI32!GetDeviceCaps` at `0x180026807`
- `GDI32!GetDeviceCaps` at `0x180026807`
- `GDI32!CreateFontIndirectW` at `0x180026829`
- `GDI32!CreateFontIndirectW` at `0x180026829`
- `GDI32!GetObjectW` at `0x1800267f9`
- `GDI32!GetObjectW` at `0x1800267f9`

## pseudocode

```c
__int64 __fastcall CFoDDetailedResultsPage::OnInitDialog(HWND *this)
{
  HDC DC; // rbx
  HWND *DlgItem; // rax
  HWND v4; // rcx
  void *v5; // rax
  int DeviceCaps; // eax
  HFONT v7; // rax
  _BYTE v9[16]; // [rsp+20h] [rbp-88h] BYREF
  LOGFONTW pv; // [rsp+30h] [rbp-78h] BYREF

  memset_0(&pv, 0, sizeof(pv));
  DC = GetDC(this[1]);
  DlgItem = (HWND *)ATL::CWindow::GetDlgItem(this + 1, v9, 700);
  v4 = *DlgItem;
  this[28] = *DlgItem;
  v5 = (void *)SendMessageW(v4, 0x31u, 0, 0);
  GetObjectW(v5, 92, &pv);
  DeviceCaps = GetDeviceCaps(DC, 90);
  pv.lfHeight = -MulDiv(15, DeviceCaps, 96);
  v7 = CreateFontIndirectW(&pv);
  this[31] = (HWND)v7;
  SendMessageW(this[28], 0x30u, (WPARAM)v7, 1);
  this[29] = *(HWND *)ATL::CWindow::GetDlgItem(this + 1, v9, 707);
  this[30] = *(HWND *)ATL::CWindow::GetDlgItem(this + 1, v9, 703);
  *((_DWORD *)this + 64) = 1;
  ReleaseDC(this[1], DC);
  return 1;
}

```

## disassembly

```asm
0x180026778  mov     [rsp+arg_8], rbx
0x18002677d  mov     [rsp+arg_10], rsi
0x180026782  push    rdi
0x180026783  sub     rsp, 0A0h
0x18002678a  mov     rax, cs:__security_cookie
0x180026791  xor     rax, rsp
0x180026794  mov     [rsp+0A8h+var_18], rax
0x18002679c  xor     edx, edx; Val
0x18002679e  mov     rsi, rcx
0x1800267a1  lea     rcx, [rsp+0A8h+pv]; void *
0x1800267a6  lea     r8d, [rdx+5Ch]; Size
0x1800267aa  call    memset_0
0x1800267af  lea     rdi, [rsi+8]
0x1800267b3  mov     rcx, [rdi]; hWnd
0x1800267b6  call    cs:__imp_GetDC
0x1800267bc  mov     r8d, 2BCh
0x1800267c2  lea     rdx, [rsp+0A8h+var_88]
0x1800267c7  mov     rcx, rdi
0x1800267ca  mov     rbx, rax
0x1800267cd  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x1800267d2  xor     r9d, r9d; lParam
0x1800267d5  xor     r8d, r8d; wParam
0x1800267d8  mov     rcx, [rax]; hWnd
0x1800267db  lea     edx, [r9+31h]; Msg
0x1800267df  mov     [rsi+0E0h], rcx
0x1800267e6  call    cs:__imp_SendMessageW
0x1800267ec  lea     r8, [rsp+0A8h+pv]; pv
0x1800267f1  mov     edx, 5Ch ; '\'; c
0x1800267f6  mov     rcx, rax; h
0x1800267f9  call    cs:__imp_GetObjectW
0x1800267ff  mov     edx, 5Ah ; 'Z'; index
0x180026804  mov     rcx, rbx; hdc
0x180026807  call    cs:__imp_GetDeviceCaps
0x18002680d  mov     ecx, 0Fh; nNumber
0x180026812  mov     edx, eax; nNumerator
0x180026814  lea     r8d, [rcx+51h]; nDenominator
0x180026818  call    cs:__imp_MulDiv
0x18002681e  neg     eax
0x180026820  lea     rcx, [rsp+0A8h+pv]; lplf
0x180026825  mov     [rsp+0A8h+pv.lfHeight], eax
0x180026829  call    cs:__imp_CreateFontIndirectW
0x18002682f  mov     r9d, 1; lParam
0x180026835  mov     [rsi+0F8h], rax
0x18002683c  mov     rcx, [rsi+0E0h]; hWnd
0x180026843  mov     r8, rax; wParam
0x180026846  lea     edx, [r9+2Fh]; Msg
0x18002684a  call    cs:__imp_SendMessageW
0x180026850  mov     r8d, 2C3h
0x180026856  lea     rdx, [rsp+0A8h+var_88]
0x18002685b  mov     rcx, rdi
0x18002685e  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x180026863  mov     r8d, 2BFh
0x180026869  mov     rcx, rdi
0x18002686c  mov     rdx, [rax]
0x18002686f  mov     [rsi+0E8h], rdx
0x180026876  lea     rdx, [rsp+0A8h+var_88]
0x18002687b  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x180026880  mov     rdx, [rax]
0x180026883  mov     [rsi+0F0h], rdx
0x18002688a  mov     rdx, rbx; hDC
0x18002688d  mov     dword ptr [rsi+100h], 1
0x180026897  mov     rcx, [rdi]; hWnd
0x18002689a  call    cs:__imp_ReleaseDC
0x1800268a0  mov     eax, 1
0x1800268a5  mov     rcx, [rsp+0A8h+var_18]
0x1800268ad  xor     rcx, rsp; StackCookie
0x1800268b0  call    __security_check_cookie
0x1800268b5  lea     r11, [rsp+0A8h+var_8]
0x1800268bd  mov     rbx, [r11+18h]
0x1800268c1  mov     rsi, [r11+20h]
0x1800268c5  mov     rsp, r11
0x1800268c8  pop     rdi
0x1800268c9  retn
```
