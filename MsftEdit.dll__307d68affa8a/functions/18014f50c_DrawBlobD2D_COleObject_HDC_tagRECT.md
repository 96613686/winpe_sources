# DrawBlobD2D(COleObject *,HDC__ *,tagRECT *)

- ea: `0x18014f50c`
- end: `0x18014f819`
- name: `?DrawBlobD2D@@YAJPEAVCOleObject@@PEAUHDC__@@PEAUtagRECT@@@Z`
- size: `781`
- prototype: `__int64 __fastcall(struct COleObject *, HDC hdcDest, struct tagRECT *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18014fc60`

## callees

- `0x1800498d0`
- `0x18004bc78`
- `0x18006733c`
- `0x18006d590`
- `0x18006e770`
- `0x1800ee7e4`
- `0x18013bad0`
- `0x18014f50c`
- `0x1801a6970`
- `0x18027a010`

## import_xrefs

- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x18014f5d0`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x18014f5d0`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18014f5fa`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18014f7d7`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18014f5fa`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18014f7d7`
- `ext-ms-win-gdi-draw-l1-1-0!CreateCompatibleBitmap` at `0x18014f5ea`
- `ext-ms-win-gdi-draw-l1-1-0!CreateCompatibleBitmap` at `0x18014f5ea`
- `ext-ms-win-gdi-draw-l1-1-0!StretchBlt` at `0x18014f7ca`
- `ext-ms-win-gdi-draw-l1-1-0!StretchBlt` at `0x18014f7ca`
- `ext-ms-win-rtcore-gdi-devcaps-l1-1-0!GetDeviceCaps` at `0x18014f56d`
- `ext-ms-win-rtcore-gdi-devcaps-l1-1-0!GetDeviceCaps` at `0x18014f57d`
- `ext-ms-win-rtcore-gdi-devcaps-l1-1-0!GetDeviceCaps` at `0x18014f56d`
- `ext-ms-win-rtcore-gdi-devcaps-l1-1-0!GetDeviceCaps` at `0x18014f57d`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18014f7e1`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18014f7ea`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18014f7e1`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18014f7ea`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!GetDC` at `0x18014f55c`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!GetDC` at `0x18014f55c`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!ReleaseDC` at `0x18014f609`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!ReleaseDC` at `0x18014f609`

## pseudocode

```c
__int64 __fastcall DrawBlobD2D(struct COleObject *a1, HDC hdcDest, struct tagRECT *a3)
{
  CTxtEdit *v3; // r12
  HDC DC; // rdi
  int DeviceCaps; // ebx
  LONG v10; // eax
  LONG top; // ecx
  int v12; // r11d
  LONG v13; // eax
  LONG right; // ecx
  LONG v15; // eax
  LONG bottom; // ecx
  int v17; // r11d
  HDC hdcSrc; // r14
  struct ID2D1Factory *D2DFactory; // rax
  int v20; // eax
  struct ID2D1RenderTarget *v21; // rdx
  int v22; // ebx
  struct ITextRenderTarget *D2DTextRenderTarget; // rdi
  unsigned int BackColor; // eax
  CTextMarkContainer *v25; // rcx
  RichEdit *v26; // [rsp+60h] [rbp-49h] BYREF
  __int64 v27; // [rsp+68h] [rbp-41h] BYREF
  HGDIOBJ h; // [rsp+70h] [rbp-39h]
  HGDIOBJ ho; // [rsp+78h] [rbp-31h]
  struct tagRECT v30; // [rsp+80h] [rbp-29h] BYREF
  float v31[4]; // [rsp+90h] [rbp-19h] BYREF
  int v32; // [rsp+A0h] [rbp-9h] BYREF
  __int64 v33; // [rsp+A4h] [rbp-5h]
  __int64 v34; // [rsp+ACh] [rbp+3h]
  __int64 v35; // [rsp+B4h] [rbp+Bh]

  v3 = (CTxtEdit *)*((_QWORD *)a1 + 6);
  if ( !CTxtEdit::GetTextMarkContainer(v3) )
    return 2147500037LL;
  DC = GetDC(0);
  DeviceCaps = GetDeviceCaps(DC, 88);
  GetDeviceCaps(DC, 90);
  v10 = CW32System::MulDivFunc(a3->left, DeviceCaps, 2540);
  top = a3->top;
  v30.left = v10;
  v13 = CW32System::MulDivFunc(top, v12, 2540);
  right = a3->right;
  v30.top = v13;
  v15 = CW32System::MulDivFunc(right, DeviceCaps, 2540);
  bottom = a3->bottom;
  v30.right = v15;
  v30.bottom = CW32System::MulDivFunc(bottom, v17, 2540);
  hdcSrc = CreateCompatibleDC(DC);
  ho = CreateCompatibleBitmap(DC, v30.right - v30.left, v30.bottom - v30.top);
  h = SelectObject(hdcSrc, ho);
  ReleaseDC(0, DC);
  v27 = 0x300000057LL;
  v33 = 0x300000057LL;
  v32 = 0;
  v34 = 0;
  v35 = 0;
  D2DFactory = GetD2DFactory();
  v26 = 0;
  v20 = (*(__int64 (__fastcall **)(struct ID2D1Factory *, int *, RichEdit **))(*(_QWORD *)D2DFactory + 128LL))(
          D2DFactory,
          &v32,
          &v26);
  v27 = 0;
  v22 = v20;
  if ( v20 >= 0 )
  {
    D2DTextRenderTarget = RichEdit::CreateD2DTextRenderTarget(v26, v21);
    Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(&v27);
    v27 = (__int64)D2DTextRenderTarget;
    v22 = (*(__int64 (__fastcall **)(RichEdit *, HDC, struct tagRECT *))(*(_QWORD *)v26 + 456LL))(v26, hdcSrc, &v30);
    if ( v22 >= 0 )
    {
      (*(void (__fastcall **)(RichEdit *))(*(_QWORD *)v26 + 384LL))(v26);
      BackColor = CTxtEdit::TxGetBackColor(v3);
      v31[3] = 1.0;
      v31[0] = (float)BYTE2(BackColor) / 255.0;
      v31[1] = (float)BYTE1(BackColor) / 255.0;
      v31[2] = (float)(unsigned __int8)BackColor / 255.0;
      (*(void (__fastcall **)(RichEdit *, float *))(*(_QWORD *)v26 + 376LL))(v26, v31);
      v22 = CTextMarkContainer::DrawBlob(v25, a1, 0, &v30, D2DTextRenderTarget);
      if ( v22 >= 0 )
        v22 = (*(__int64 (__fastcall **)(RichEdit *, _QWORD, _QWORD))(*(_QWORD *)v26 + 392LL))(v26, 0, 0);
    }
  }
  if ( v26 )
    (*(void (__fastcall **)(RichEdit *))(*(_QWORD *)v26 + 16LL))(v26);
  Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(&v27);
  StretchBlt(
    hdcDest,
    0,
    0,
    a3->right - a3->left,
    a3->bottom - a3->top,
    hdcSrc,
    0,
    0,
    v30.right - v30.left,
    v30.bottom - v30.top,
    0xCC0020u);
  SelectObject(hdcSrc, h);
  DeleteObject(ho);
  DeleteObject(hdcSrc);
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x18014f50c  mov     [rsp-8+arg_18], rbx
0x18014f511  push    rbp
0x18014f512  push    rsi
0x18014f513  push    rdi
0x18014f514  push    r12
0x18014f516  push    r13
0x18014f518  push    r14
0x18014f51a  push    r15
0x18014f51c  lea     rbp, [rsp-27h]
0x18014f521  sub     rsp, 0D0h
0x18014f528  mov     rax, cs:__security_cookie
0x18014f52f  xor     rax, rsp
0x18014f532  mov     [rbp+57h+var_40], rax
0x18014f536  mov     r12, [rcx+30h]
0x18014f53a  mov     r15, rcx
0x18014f53d  mov     rcx, r12; this
0x18014f540  mov     rsi, r8
0x18014f543  mov     r13, rdx
0x18014f546  call    ?GetTextMarkContainer@CTxtEdit@@QEAAPEAVCTextMarkContainer@@XZ; CTxtEdit::GetTextMarkContainer(void)
0x18014f54b  test    rax, rax
0x18014f54e  jnz     short loc_18014F55A
0x18014f550  mov     eax, 80004005h
0x18014f555  jmp     loc_18014F7F2
0x18014f55a  xor     ecx, ecx; hWnd
0x18014f55c  call    cs:__imp_GetDC
0x18014f562  mov     rcx, rax; hdc
0x18014f565  mov     edx, 58h ; 'X'; index
0x18014f56a  mov     rdi, rax
0x18014f56d  call    cs:__imp_GetDeviceCaps
0x18014f573  mov     edx, 5Ah ; 'Z'; index
0x18014f578  mov     rcx, rdi; hdc
0x18014f57b  mov     ebx, eax
0x18014f57d  call    cs:__imp_GetDeviceCaps
0x18014f583  mov     ecx, [rsi]; int
0x18014f585  mov     r14d, 9ECh
0x18014f58b  mov     r8d, r14d; int
0x18014f58e  mov     edx, ebx; int
0x18014f590  mov     r11d, eax
0x18014f593  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x18014f598  mov     ecx, [rsi+4]; int
0x18014f59b  mov     r8d, r14d; int
0x18014f59e  mov     edx, r11d; int
0x18014f5a1  mov     [rbp+57h+var_80.left], eax
0x18014f5a4  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x18014f5a9  mov     ecx, [rsi+8]; int
0x18014f5ac  mov     r8d, r14d; int
0x18014f5af  mov     edx, ebx; int
0x18014f5b1  mov     [rbp+57h+var_80.top], eax
0x18014f5b4  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x18014f5b9  mov     ecx, [rsi+0Ch]; int
0x18014f5bc  mov     r8d, r14d; int
0x18014f5bf  mov     edx, r11d; int
0x18014f5c2  mov     [rbp+57h+var_80.right], eax
0x18014f5c5  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x18014f5ca  mov     rcx, rdi; hdc
0x18014f5cd  mov     [rbp+57h+var_80.bottom], eax
0x18014f5d0  call    cs:__imp_CreateCompatibleDC
0x18014f5d6  mov     r8d, [rbp+57h+var_80.bottom]
0x18014f5da  mov     rcx, rdi; hdc
0x18014f5dd  mov     edx, [rbp+57h+var_80.right]
0x18014f5e0  mov     r14, rax
0x18014f5e3  sub     r8d, [rbp+57h+var_80.top]; cy
0x18014f5e7  sub     edx, [rbp+57h+var_80.left]; cx
0x18014f5ea  call    cs:__imp_CreateCompatibleBitmap
0x18014f5f0  mov     rdx, rax; h
0x18014f5f3  mov     [rbp+57h+ho], rax
0x18014f5f7  mov     rcx, r14; hdc
0x18014f5fa  call    cs:__imp_SelectObject
0x18014f600  mov     rdx, rdi; hDC
0x18014f603  xor     ecx, ecx; hWnd
0x18014f605  mov     [rbp+57h+h], rax
0x18014f609  call    cs:__imp_ReleaseDC
0x18014f60f  xor     edi, edi
0x18014f611  mov     dword ptr [rbp+57h+var_98], 57h ; 'W'
0x18014f618  mov     dword ptr [rbp+57h+var_98+4], 3
0x18014f61f  mov     rcx, [rbp+57h+var_98]
0x18014f623  mov     [rbp+57h+var_5C], rcx
0x18014f627  mov     [rbp+57h+var_60], edi
0x18014f62a  mov     [rbp+57h+var_54], rdi
0x18014f62e  mov     [rbp+57h+var_4C], rdi
0x18014f632  call    ?GetD2DFactory@@YAPEAUID2D1Factory@@XZ; GetD2DFactory(void)
0x18014f637  mov     r9, rax
0x18014f63a  mov     [rbp+57h+var_A0], rdi
0x18014f63e  lea     r8, [rbp+57h+var_A0]
0x18014f642  lea     rdx, [rbp+57h+var_60]
0x18014f646  mov     rcx, [rax]
0x18014f649  mov     rax, [rcx+80h]
0x18014f650  mov     rcx, r9
0x18014f653  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014f658  mov     [rbp+57h+var_98], rdi
0x18014f65c  mov     ebx, eax
0x18014f65e  test    eax, eax
0x18014f660  js      loc_18014F767
0x18014f666  mov     rcx, [rbp+57h+var_A0]; this
0x18014f66a  call    ?CreateD2DTextRenderTarget@RichEdit@@YAPEAUITextRenderTarget@@PEAUID2D1RenderTarget@@@Z; RichEdit::CreateD2DTextRenderTarget(ID2D1RenderTarget *)
0x18014f66f  lea     rcx, [rbp+57h+var_98]; void *
0x18014f673  mov     rdi, rax
0x18014f676  call    ??1?$TCntPtr@UIDataObject@@@Resp@@QEAA@XZ; Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(void)
0x18014f67b  mov     r9, [rbp+57h+var_A0]
0x18014f67f  lea     r8, [rbp+57h+var_80]
0x18014f683  mov     rdx, r14
0x18014f686  mov     [rbp+57h+var_98], rdi
0x18014f68a  mov     rcx, [r9]
0x18014f68d  mov     rax, [rcx+1C8h]
0x18014f694  mov     rcx, r9
0x18014f697  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014f69c  mov     ebx, eax
0x18014f69e  test    eax, eax
0x18014f6a0  js      loc_18014F765
0x18014f6a6  mov     rcx, [rbp+57h+var_A0]
0x18014f6aa  mov     rax, [rcx]
0x18014f6ad  mov     rax, [rax+180h]
0x18014f6b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014f6b9  mov     rcx, r12; this
0x18014f6bc  call    ?TxGetBackColor@CTxtEdit@@QEBAKXZ; CTxtEdit::TxGetBackColor(void)
0x18014f6c1  movss   xmm1, cs:__real@437f0000
0x18014f6c9  lea     rdx, [rbp+57h+var_70]
0x18014f6cd  xorps   xmm0, xmm0
0x18014f6d0  mov     [rbp+57h+var_64], 3F800000h
0x18014f6d7  mov     ecx, eax
0x18014f6d9  shr     ecx, 10h
0x18014f6dc  movzx   ecx, cl
0x18014f6df  cvtsi2ss xmm0, rcx
0x18014f6e4  mov     ecx, eax
0x18014f6e6  movzx   eax, al
0x18014f6e9  shr     ecx, 8
0x18014f6ec  movzx   ecx, cl
0x18014f6ef  divss   xmm0, xmm1
0x18014f6f3  movss   [rbp+57h+var_70], xmm0
0x18014f6f8  xorps   xmm0, xmm0
0x18014f6fb  cvtsi2ss xmm0, rcx
0x18014f700  mov     rcx, [rbp+57h+var_A0]
0x18014f704  divss   xmm0, xmm1
0x18014f708  movss   [rbp+57h+var_6C], xmm0
0x18014f70d  xorps   xmm0, xmm0
0x18014f710  cvtsi2ss xmm0, rax
0x18014f715  divss   xmm0, xmm1
0x18014f719  movss   [rbp+57h+var_68], xmm0
0x18014f71e  mov     rax, [rcx]
0x18014f721  mov     rax, [rax+178h]
0x18014f728  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014f72d  lea     r9, [rbp+57h+var_80]; struct tagRECT *
0x18014f731  mov     qword ptr [rsp+100h+hDest], rdi; struct ITextRenderTarget *
0x18014f736  xor     r8d, r8d; HDC
0x18014f739  mov     rdx, r15; struct COleObject *
0x18014f73c  call    ?DrawBlob@CTextMarkContainer@@QEAAJAEBVCOleObject@@PEAUHDC__@@PEBUtagRECT@@PEAUITextRenderTarget@@@Z; CTextMarkContainer::DrawBlob(COleObject const &,HDC__ *,tagRECT const *,ITextRenderTarget *)
0x18014f741  xor     edi, edi
0x18014f743  mov     ebx, eax
0x18014f745  test    eax, eax
0x18014f747  js      short loc_18014F767
0x18014f749  mov     rcx, [rbp+57h+var_A0]
0x18014f74d  xor     r8d, r8d
0x18014f750  xor     edx, edx
0x18014f752  mov     rax, [rcx]
0x18014f755  mov     rax, [rax+188h]
0x18014f75c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014f761  mov     ebx, eax
0x18014f763  jmp     short loc_18014F767
0x18014f765  xor     edi, edi
0x18014f767  mov     rcx, [rbp+57h+var_A0]
0x18014f76b  test    rcx, rcx
0x18014f76e  jz      short loc_18014F77C
0x18014f770  mov     rax, [rcx]
0x18014f773  mov     rax, [rax+10h]
0x18014f777  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014f77c  lea     rcx, [rbp+57h+var_98]; void *
0x18014f780  call    ??1?$TCntPtr@UIDataObject@@@Resp@@QEAA@XZ; Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(void)
0x18014f785  mov     edx, [rbp+57h+var_80.bottom]
0x18014f788  mov     rcx, r13; hdcDest
0x18014f78b  sub     edx, [rbp+57h+var_80.top]
0x18014f78e  mov     eax, [rbp+57h+var_80.right]
0x18014f791  sub     eax, [rbp+57h+var_80.left]
0x18014f794  mov     r8d, [rsi+0Ch]
0x18014f798  sub     r8d, [rsi+4]
0x18014f79c  mov     r9d, [rsi+8]
0x18014f7a0  sub     r9d, [rsi]; wDest
0x18014f7a3  mov     [rsp+100h+rop], 0CC0020h; rop
0x18014f7ab  mov     [rsp+100h+hSrc], edx; hSrc
0x18014f7af  xor     edx, edx; xDest
0x18014f7b1  mov     [rsp+100h+wSrc], eax; wSrc
0x18014f7b5  mov     [rsp+100h+ySrc], edi; ySrc
0x18014f7b9  mov     [rsp+100h+xSrc], edi; xSrc
0x18014f7bd  mov     [rsp+100h+hdcSrc], r14; hdcSrc
0x18014f7c2  mov     [rsp+100h+hDest], r8d; hDest
0x18014f7c7  xor     r8d, r8d; yDest
0x18014f7ca  call    cs:__imp_StretchBlt
0x18014f7d0  mov     rdx, [rbp+57h+h]; h
0x18014f7d4  mov     rcx, r14; hdc
0x18014f7d7  call    cs:__imp_SelectObject
0x18014f7dd  mov     rcx, [rbp+57h+ho]; ho
0x18014f7e1  call    cs:__imp_DeleteObject
0x18014f7e7  mov     rcx, r14; ho
0x18014f7ea  call    cs:__imp_DeleteObject
0x18014f7f0  mov     eax, ebx
0x18014f7f2  mov     rcx, [rbp+57h+var_40]
0x18014f7f6  xor     rcx, rsp; StackCookie
0x18014f7f9  call    __security_check_cookie
0x18014f7fe  mov     rbx, [rsp+100h+arg_18]
0x18014f806  add     rsp, 0D0h
0x18014f80d  pop     r15
0x18014f80f  pop     r14
0x18014f811  pop     r13
0x18014f813  pop     r12
0x18014f815  pop     rdi
0x18014f816  pop     rsi
0x18014f817  pop     rbp
0x18014f818  retn
```
