# Jot::FirstRun::CFirstRunDialog::SetWindowFont(void)

- ea: `0x1803d4904`
- end: `0x1803d4c1f`
- name: `?SetWindowFont@CFirstRunDialog@FirstRun@Jot@@AEAAXXZ`
- size: `795`
- prototype: `void __fastcall(Jot::FirstRun::CFirstRunDialog *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1803d4500`

## callees

- `0x180078ec0`
- `0x1801232d8`
- `0x1802e2251`
- `0x1802e5170`
- `0x1802e5190`
- `0x18039a2f0`
- `0x1803d13e8`
- `0x1803d14a8`
- `0x1803d4904`

## import_xrefs

- `KERNEL32!MulDiv` at `0x1803d4a10`
- `KERNEL32!MulDiv` at `0x1803d4a48`
- `KERNEL32!MulDiv` at `0x1803d4a80`
- `KERNEL32!MulDiv` at `0x1803d4ab8`
- `KERNEL32!MulDiv` at `0x1803d4a10`
- `KERNEL32!MulDiv` at `0x1803d4a48`
- `KERNEL32!MulDiv` at `0x1803d4a80`
- `KERNEL32!MulDiv` at `0x1803d4ab8`
- `GDI32!GetObjectW` at `0x1803d49e2`
- `GDI32!GetObjectW` at `0x1803d49e2`
- `GDI32!CreateFontIndirectW` at `0x1803d4a1f`
- `GDI32!CreateFontIndirectW` at `0x1803d4a57`
- `GDI32!CreateFontIndirectW` at `0x1803d4a8f`
- `GDI32!CreateFontIndirectW` at `0x1803d4ac7`
- `GDI32!CreateFontIndirectW` at `0x1803d4ad8`
- `GDI32!CreateFontIndirectW` at `0x1803d4a1f`
- `GDI32!CreateFontIndirectW` at `0x1803d4a57`
- `GDI32!CreateFontIndirectW` at `0x1803d4a8f`
- `GDI32!CreateFontIndirectW` at `0x1803d4ac7`
- `GDI32!CreateFontIndirectW` at `0x1803d4ad8`
- `USER32!SendMessageW` at `0x1803d4b07`
- `USER32!SendMessageW` at `0x1803d4b23`
- `USER32!SendMessageW` at `0x1803d4b3f`
- `USER32!SendMessageW` at `0x1803d4b5b`
- `USER32!SendMessageW` at `0x1803d4b77`
- `USER32!SendMessageW` at `0x1803d4b93`
- `USER32!SendMessageW` at `0x1803d4baf`
- `USER32!SendMessageW` at `0x1803d4bcb`
- `USER32!SendMessageW` at `0x1803d4be7`
- `USER32!SendMessageW` at `0x1803d4b07`
- `USER32!SendMessageW` at `0x1803d4b23`
- `USER32!SendMessageW` at `0x1803d4b3f`
- `USER32!SendMessageW` at `0x1803d4b5b`
- `USER32!SendMessageW` at `0x1803d4b77`
- `USER32!SendMessageW` at `0x1803d4b93`
- `USER32!SendMessageW` at `0x1803d4baf`
- `USER32!SendMessageW` at `0x1803d4bcb`
- `USER32!SendMessageW` at `0x1803d4be7`

## pseudocode

```c
void __fastcall Jot::FirstRun::CFirstRunDialog::SetWindowFont(
        MsoCF::CWindow **this,
        __int64 a2,
        const struct Mso::Telemetry::EventName *a3)
{
  __int64 v4; // rax
  void *v5; // rbx
  int DpiY; // ebx
  Jot::FirstRun::CFirstRunDialog *v7; // rcx
  float v8; // xmm0_4
  HFONT v9; // r14
  int v10; // ebx
  Jot::FirstRun::CFirstRunDialog *v11; // rcx
  float v12; // xmm0_4
  HFONT v13; // rdi
  int v14; // ebx
  Jot::FirstRun::CFirstRunDialog *v15; // rcx
  float v16; // xmm0_4
  HFONT v17; // r15
  int v18; // ebx
  Jot::FirstRun::CFirstRunDialog *v19; // rcx
  float v20; // xmm0_4
  HFONT v21; // rax
  WPARAM v22; // r12
  HFONT v23; // rbx
  HWND *v24; // rax
  HWND *v25; // rax
  HWND *v26; // rax
  HWND *v27; // rax
  HWND *v28; // rax
  HWND *v29; // rax
  HWND *v30; // rax
  HWND *v31; // rax
  HWND *v32; // rax
  unsigned int v33[2]; // [rsp+28h] [rbp-59h] BYREF
  const char *v34; // [rsp+30h] [rbp-51h]
  LOGFONTW pv; // [rsp+38h] [rbp-49h] BYREF

  if ( qword_181534870 )
  {
    MsoCF::CWindow::GetDpiX(this[43]);
    v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)qword_181534870 + 368LL))(qword_181534870);
    v5 = (void *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v4 + 16LL))(v4, 0);
    if ( v5 )
    {
      memset_0(&pv, 0, sizeof(pv));
      GetObjectW(v5, 92, &pv);
      DpiY = MsoCF::CWindow::GetDpiY((MsoCF::CWindow *)(this + 14));
      v8 = Jot::FirstRun::CFirstRunDialog::ScaleToFitDesktop(v7, 16.0);
      pv.lfHeight = -MulDiv((int)v8, DpiY, 72);
      v9 = CreateFontIndirectW(&pv);
      v10 = MsoCF::CWindow::GetDpiY((MsoCF::CWindow *)(this + 14));
      v12 = Jot::FirstRun::CFirstRunDialog::ScaleToFitDesktop(v11, 14.0);
      pv.lfHeight = -MulDiv((int)v12, v10, 72);
      v13 = CreateFontIndirectW(&pv);
      v14 = MsoCF::CWindow::GetDpiY((MsoCF::CWindow *)(this + 14));
      v16 = Jot::FirstRun::CFirstRunDialog::ScaleToFitDesktop(v15, 11.0);
      pv.lfHeight = -MulDiv((int)v16, v14, 72);
      v17 = CreateFontIndirectW(&pv);
      v18 = MsoCF::CWindow::GetDpiY((MsoCF::CWindow *)(this + 14));
      v20 = Jot::FirstRun::CFirstRunDialog::ScaleToFitDesktop(v19, 9.0);
      pv.lfHeight = -MulDiv((int)v20, v18, 72);
      v21 = CreateFontIndirectW(&pv);
      pv.lfUnderline = 1;
      v22 = (WPARAM)v21;
      v23 = CreateFontIndirectW(&pv);
      v24 = (HWND *)std::vector<MsoCF::CIPtr<Jot::IViewElement,Jot::IViewElement>>::operator[](this + 69, 0);
      SendMessageW(*v24, 0x30u, (WPARAM)v13, 1);
      v25 = (HWND *)std::vector<MsoCF::CIPtr<Jot::IViewElement,Jot::IViewElement>>::operator[](this + 69, 1);
      SendMessageW(*v25, 0x30u, (WPARAM)v9, 1);
      v26 = (HWND *)std::vector<MsoCF::CIPtr<Jot::IViewElement,Jot::IViewElement>>::operator[](this + 69, 2);
      SendMessageW(*v26, 0x30u, (WPARAM)v17, 1);
      v27 = (HWND *)std::vector<MsoCF::CIPtr<Jot::IViewElement,Jot::IViewElement>>::operator[](this + 69, 3);
      SendMessageW(*v27, 0x30u, v22, 1);
      v28 = (HWND *)std::vector<MsoCF::CIPtr<Jot::IViewElement,Jot::IViewElement>>::operator[](this + 69, 4);
      SendMessageW(*v28, 0x30u, (WPARAM)v23, 1);
      v29 = (HWND *)std::vector<MsoCF::CIPtr<Jot::IViewElement,Jot::IViewElement>>::operator[](this + 69, 5);
      SendMessageW(*v29, 0x30u, v22, 1);
      v30 = (HWND *)std::vector<MsoCF::CIPtr<Jot::IViewElement,Jot::IViewElement>>::operator[](this + 69, 7);
      SendMessageW(*v30, 0x30u, (WPARAM)v17, 1);
      v31 = (HWND *)std::vector<MsoCF::CIPtr<Jot::IViewElement,Jot::IViewElement>>::operator[](this + 69, 8);
      SendMessageW(*v31, 0x30u, v22, 1);
      v32 = (HWND *)std::vector<MsoCF::CIPtr<Jot::IViewElement,Jot::IViewElement>>::operator[](this + 69, 9);
      SendMessageW(*v32, 0x30u, v22, 1);
    }
  }
  else
  {
    *(_QWORD *)v33 = &off_18107D820;
    v34 = "CFirstRunDialogSetWindowFontMainAppNotAvailable";
    Jot::Logging::LogUnexpectedTag((Jot::Logging *)0x1E24F74C, (unsigned int)v33, a3);
  }
}

```

## disassembly

```asm
0x1803d4904  mov     rax, rsp
0x1803d4907  mov     [rax+10h], rbx
0x1803d490b  mov     [rax+18h], rsi
0x1803d490f  mov     [rax+20h], rdi
0x1803d4913  push    rbp
0x1803d4914  push    r12
0x1803d4916  push    r13
0x1803d4918  push    r14
0x1803d491a  push    r15
0x1803d491c  lea     rbp, [rax-5Fh]
0x1803d4920  sub     rsp, 0B0h
0x1803d4927  movaps  xmmword ptr [rax-38h], xmm6
0x1803d492b  mov     rax, cs:__security_cookie
0x1803d4932  xor     rax, rsp
0x1803d4935  mov     [rbp+57h+var_40], rax
0x1803d4939  cmp     cs:qword_181534870, 0
0x1803d4941  mov     r13, rcx
0x1803d4944  jnz     short loc_1803D496F
0x1803d4946  lea     rax, off_18107D820
0x1803d494d  mov     ecx, 1E24F74Ch; this
0x1803d4952  mov     qword ptr [rbp+57h+var_B0], rax
0x1803d4956  lea     rdx, [rbp+57h+var_B0]; unsigned int
0x1803d495a  lea     rax, aCfirstrundialo; "CFirstRunDialogSetWindowFontMainAppNotA"...
0x1803d4961  mov     [rbp+57h+var_A8], rax
0x1803d4965  call    ?LogUnexpectedTag@Logging@Jot@@YAXKAEBUEventName@Telemetry@Mso@@@Z; Jot::Logging::LogUnexpectedTag(ulong,Mso::Telemetry::EventName const &)
0x1803d496a  jmp     loc_1803D4BED
0x1803d496f  mov     rcx, [rcx+158h]; this
0x1803d4976  call    ?GetDpiX@CWindow@MsoCF@@QEBAHXZ; MsoCF::CWindow::GetDpiX(void)
0x1803d497b  mov     rcx, cs:qword_181534870
0x1803d4982  movd    xmm6, eax
0x1803d4986  mov     rax, [rcx]
0x1803d4989  cvtdq2pd xmm6, xmm6
0x1803d498d  mov     rax, [rax+170h]
0x1803d4994  divsd   xmm6, cs:__real@4058000000000000
0x1803d499c  call    cs:__guard_dispatch_icall_fptr
0x1803d49a2  movaps  xmm2, xmm6
0x1803d49a5  xor     edx, edx
0x1803d49a7  mov     r8, rax
0x1803d49aa  mov     rcx, [rax]
0x1803d49ad  mov     rax, [rcx+10h]
0x1803d49b1  mov     rcx, r8
0x1803d49b4  call    cs:__guard_dispatch_icall_fptr
0x1803d49ba  mov     rbx, rax
0x1803d49bd  test    rax, rax
0x1803d49c0  jz      loc_1803D4BED
0x1803d49c6  mov     edi, 5Ch ; '\'
0x1803d49cb  lea     rcx, [rbp+57h+pv]; void *
0x1803d49cf  mov     r8d, edi; Size
0x1803d49d2  xor     edx, edx; Val
0x1803d49d4  call    memset_0
0x1803d49d9  lea     r8, [rbp+57h+pv]; pv
0x1803d49dd  mov     edx, edi; c
0x1803d49df  mov     rcx, rbx; h
0x1803d49e2  call    cs:__imp_GetObjectW
0x1803d49e8  lea     rsi, [r13+70h]
0x1803d49ec  mov     rcx, rsi; this
0x1803d49ef  call    ?GetDpiY@CWindow@MsoCF@@QEBAHXZ; MsoCF::CWindow::GetDpiY(void)
0x1803d49f4  movss   xmm1, cs:__real@41800000; float
0x1803d49fc  mov     ebx, eax
0x1803d49fe  call    ?ScaleToFitDesktop@CFirstRunDialog@FirstRun@Jot@@AEAAMM@Z; Jot::FirstRun::CFirstRunDialog::ScaleToFitDesktop(float)
0x1803d4a03  cvttss2si ecx, xmm0; nNumber
0x1803d4a07  lea     r12d, [rdi-14h]
0x1803d4a0b  mov     edx, ebx; nNumerator
0x1803d4a0d  mov     r8d, r12d; nDenominator
0x1803d4a10  call    cs:__imp_MulDiv
0x1803d4a16  neg     eax
0x1803d4a18  lea     rcx, [rbp+57h+pv]; lplf
0x1803d4a1c  mov     [rbp+57h+pv], eax
0x1803d4a1f  call    cs:__imp_CreateFontIndirectW
0x1803d4a25  mov     rcx, rsi; this
0x1803d4a28  mov     r14, rax
0x1803d4a2b  call    ?GetDpiY@CWindow@MsoCF@@QEBAHXZ; MsoCF::CWindow::GetDpiY(void)
0x1803d4a30  movss   xmm1, cs:__real@41600000; float
0x1803d4a38  mov     ebx, eax
0x1803d4a3a  call    ?ScaleToFitDesktop@CFirstRunDialog@FirstRun@Jot@@AEAAMM@Z; Jot::FirstRun::CFirstRunDialog::ScaleToFitDesktop(float)
0x1803d4a3f  cvttss2si ecx, xmm0; nNumber
0x1803d4a43  mov     r8d, r12d; nDenominator
0x1803d4a46  mov     edx, ebx; nNumerator
0x1803d4a48  call    cs:__imp_MulDiv
0x1803d4a4e  neg     eax
0x1803d4a50  lea     rcx, [rbp+57h+pv]; lplf
0x1803d4a54  mov     [rbp+57h+pv], eax
0x1803d4a57  call    cs:__imp_CreateFontIndirectW
0x1803d4a5d  mov     rcx, rsi; this
0x1803d4a60  mov     rdi, rax
0x1803d4a63  call    ?GetDpiY@CWindow@MsoCF@@QEBAHXZ; MsoCF::CWindow::GetDpiY(void)
0x1803d4a68  movss   xmm1, cs:__real@41300000; float
0x1803d4a70  mov     ebx, eax
0x1803d4a72  call    ?ScaleToFitDesktop@CFirstRunDialog@FirstRun@Jot@@AEAAMM@Z; Jot::FirstRun::CFirstRunDialog::ScaleToFitDesktop(float)
0x1803d4a77  cvttss2si ecx, xmm0; nNumber
0x1803d4a7b  mov     r8d, r12d; nDenominator
0x1803d4a7e  mov     edx, ebx; nNumerator
0x1803d4a80  call    cs:__imp_MulDiv
0x1803d4a86  neg     eax
0x1803d4a88  lea     rcx, [rbp+57h+pv]; lplf
0x1803d4a8c  mov     [rbp+57h+pv], eax
0x1803d4a8f  call    cs:__imp_CreateFontIndirectW
0x1803d4a95  mov     rcx, rsi; this
0x1803d4a98  mov     r15, rax
0x1803d4a9b  call    ?GetDpiY@CWindow@MsoCF@@QEBAHXZ; MsoCF::CWindow::GetDpiY(void)
0x1803d4aa0  movss   xmm1, cs:__real@41100000; float
0x1803d4aa8  mov     ebx, eax
0x1803d4aaa  call    ?ScaleToFitDesktop@CFirstRunDialog@FirstRun@Jot@@AEAAMM@Z; Jot::FirstRun::CFirstRunDialog::ScaleToFitDesktop(float)
0x1803d4aaf  cvttss2si ecx, xmm0; nNumber
0x1803d4ab3  mov     r8d, r12d; nDenominator
0x1803d4ab6  mov     edx, ebx; nNumerator
0x1803d4ab8  call    cs:__imp_MulDiv
0x1803d4abe  neg     eax
0x1803d4ac0  lea     rcx, [rbp+57h+pv]; lplf
0x1803d4ac4  mov     [rbp+57h+pv], eax
0x1803d4ac7  call    cs:__imp_CreateFontIndirectW
0x1803d4acd  lea     rcx, [rbp+57h+pv]; lplf
0x1803d4ad1  mov     [rbp+57h+var_8B], 1
0x1803d4ad5  mov     r12, rax
0x1803d4ad8  call    cs:__imp_CreateFontIndirectW
0x1803d4ade  lea     rsi, [r13+228h]
0x1803d4ae5  xor     edx, edx
0x1803d4ae7  mov     rcx, rsi
0x1803d4aea  mov     rbx, rax
0x1803d4aed  call    ??A?$vector@V?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@V?$allocator@V?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@@std@@@std@@QEAAAEAV?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@_K@Z; std::vector<MsoCF::CIPtr<Jot::IViewElement,Jot::IViewElement>>::operator[](unsigned __int64)
0x1803d4af2  mov     r13d, 1
0x1803d4af8  mov     r8, rdi; wParam
0x1803d4afb  mov     r9d, r13d; lParam
0x1803d4afe  mov     rcx, [rax]; hWnd
0x1803d4b01  lea     edi, [r13+2Fh]
0x1803d4b05  mov     edx, edi; Msg
0x1803d4b07  call    cs:__imp_SendMessageW
0x1803d4b0d  mov     edx, r13d
0x1803d4b10  mov     rcx, rsi
0x1803d4b13  call    ??A?$vector@V?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@V?$allocator@V?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@@std@@@std@@QEAAAEAV?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@_K@Z; std::vector<MsoCF::CIPtr<Jot::IViewElement,Jot::IViewElement>>::operator[](unsigned __int64)
0x1803d4b18  mov     r9d, r13d; lParam
0x1803d4b1b  mov     r8, r14; wParam
0x1803d4b1e  mov     edx, edi; Msg
0x1803d4b20  mov     rcx, [rax]; hWnd
0x1803d4b23  call    cs:__imp_SendMessageW
0x1803d4b29  lea     edx, [rdi-2Eh]
0x1803d4b2c  mov     rcx, rsi
0x1803d4b2f  call    ??A?$vector@V?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@V?$allocator@V?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@@std@@@std@@QEAAAEAV?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@_K@Z; std::vector<MsoCF::CIPtr<Jot::IViewElement,Jot::IViewElement>>::operator[](unsigned __int64)
0x1803d4b34  mov     r9d, r13d; lParam
0x1803d4b37  mov     r8, r15; wParam
0x1803d4b3a  mov     edx, edi; Msg
0x1803d4b3c  mov     rcx, [rax]; hWnd
0x1803d4b3f  call    cs:__imp_SendMessageW
0x1803d4b45  lea     edx, [rdi-2Dh]
0x1803d4b48  mov     rcx, rsi
0x1803d4b4b  call    ??A?$vector@V?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@V?$allocator@V?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@@std@@@std@@QEAAAEAV?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@_K@Z; std::vector<MsoCF::CIPtr<Jot::IViewElement,Jot::IViewElement>>::operator[](unsigned __int64)
0x1803d4b50  mov     r9d, r13d; lParam
0x1803d4b53  mov     r8, r12; wParam
0x1803d4b56  mov     edx, edi; Msg
0x1803d4b58  mov     rcx, [rax]; hWnd
0x1803d4b5b  call    cs:__imp_SendMessageW
0x1803d4b61  lea     edx, [rdi-2Ch]
0x1803d4b64  mov     rcx, rsi
0x1803d4b67  call    ??A?$vector@V?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@V?$allocator@V?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@@std@@@std@@QEAAAEAV?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@_K@Z; std::vector<MsoCF::CIPtr<Jot::IViewElement,Jot::IViewElement>>::operator[](unsigned __int64)
0x1803d4b6c  mov     r9d, r13d; lParam
0x1803d4b6f  mov     r8, rbx; wParam
0x1803d4b72  mov     edx, edi; Msg
0x1803d4b74  mov     rcx, [rax]; hWnd
0x1803d4b77  call    cs:__imp_SendMessageW
0x1803d4b7d  lea     edx, [rdi-2Bh]
0x1803d4b80  mov     rcx, rsi
0x1803d4b83  call    ??A?$vector@V?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@V?$allocator@V?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@@std@@@std@@QEAAAEAV?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@_K@Z; std::vector<MsoCF::CIPtr<Jot::IViewElement,Jot::IViewElement>>::operator[](unsigned __int64)
0x1803d4b88  mov     r9d, r13d; lParam
0x1803d4b8b  mov     r8, r12; wParam
0x1803d4b8e  mov     edx, edi; Msg
0x1803d4b90  mov     rcx, [rax]; hWnd
0x1803d4b93  call    cs:__imp_SendMessageW
0x1803d4b99  lea     edx, [rdi-29h]
0x1803d4b9c  mov     rcx, rsi
0x1803d4b9f  call    ??A?$vector@V?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@V?$allocator@V?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@@std@@@std@@QEAAAEAV?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@_K@Z; std::vector<MsoCF::CIPtr<Jot::IViewElement,Jot::IViewElement>>::operator[](unsigned __int64)
0x1803d4ba4  mov     r9d, r13d; lParam
0x1803d4ba7  mov     r8, r15; wParam
0x1803d4baa  mov     edx, edi; Msg
0x1803d4bac  mov     rcx, [rax]; hWnd
0x1803d4baf  call    cs:__imp_SendMessageW
0x1803d4bb5  lea     edx, [rdi-28h]
0x1803d4bb8  mov     rcx, rsi
0x1803d4bbb  call    ??A?$vector@V?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@V?$allocator@V?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@@std@@@std@@QEAAAEAV?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@_K@Z; std::vector<MsoCF::CIPtr<Jot::IViewElement,Jot::IViewElement>>::operator[](unsigned __int64)
0x1803d4bc0  mov     r9d, r13d; lParam
0x1803d4bc3  mov     r8, r12; wParam
0x1803d4bc6  mov     edx, edi; Msg
0x1803d4bc8  mov     rcx, [rax]; hWnd
0x1803d4bcb  call    cs:__imp_SendMessageW
0x1803d4bd1  lea     edx, [rdi-27h]
0x1803d4bd4  mov     rcx, rsi
0x1803d4bd7  call    ??A?$vector@V?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@V?$allocator@V?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@@std@@@std@@QEAAAEAV?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@_K@Z; std::vector<MsoCF::CIPtr<Jot::IViewElement,Jot::IViewElement>>::operator[](unsigned __int64)
0x1803d4bdc  mov     r9d, r13d; lParam
0x1803d4bdf  mov     r8, r12; wParam
0x1803d4be2  mov     edx, edi; Msg
0x1803d4be4  mov     rcx, [rax]; hWnd
0x1803d4be7  call    cs:__imp_SendMessageW
0x1803d4bed  mov     rcx, [rbp+57h+var_40]
0x1803d4bf1  xor     rcx, rsp; StackCookie
0x1803d4bf4  call    __security_check_cookie
0x1803d4bf9  lea     r11, [rsp+0D0h+var_20]
0x1803d4c01  mov     rbx, [r11+38h]
0x1803d4c05  mov     rsi, [r11+40h]
0x1803d4c09  mov     rdi, [r11+48h]
0x1803d4c0d  movaps  xmm6, xmmword ptr [r11-10h]
0x1803d4c12  mov     rsp, r11
0x1803d4c15  pop     r15
0x1803d4c17  pop     r14
0x1803d4c19  pop     r13
0x1803d4c1b  pop     r12
0x1803d4c1d  pop     rbp
0x1803d4c1e  retn
```
